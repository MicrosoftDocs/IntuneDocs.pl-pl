---
title: Tworzenie zasad dostępu warunkowego programu Exchange
titlesuffix: Microsoft Intune
description: Konfigurowanie dostępu warunkowego do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej w usłudze Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b1e07bd67d4bf8b776500be01571deddb1e5e58f
ms.sourcegitcommit: 630dfe1413c1819f35aa941ffc888a7084771a55
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2018
ms.locfileid: "51709142"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Tworzenie zasad dostępu warunkowego do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule pokazano, jak skonfigurować dostęp warunkowy dla lokalnej instalacji programu Exchange w oparciu o zgodność urządzenia.

Jeśli masz środowisko usługi Exchange Online w wersji dedykowanej i chcesz sprawdzić, czy zawiera ono nową, czy starą konfigurację, skontaktuj się z menedżerem konta. Aby kontrolować dostęp poczty e-mail do lokalnego programu Exchange lub do starszej wersji środowiska usługi Exchange Online w wersji dedykowanej, skonfiguruj dostęp warunkowy do lokalnego programu Exchange w usłudze Intune.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Przed skonfigurowaniem dostępu warunkowego zweryfikuj następujące kwestie:

- Program Exchange musi być w wersji **Exchange 2010 SP1 lub nowszej**. Macierz serwerów dostępu klienta (CAS) serwera programu Exchange jest obsługiwana.

- Należy użyć [łącznika lokalnego programu Exchange programu Exchange Active Sync](exchange-connector-install.md), który łączy usługę Intune z lokalnym programem Exchange.

    >[!IMPORTANT]
    >Łącznik lokalnego programu Exchange jest przeznaczony dla Twojej dzierżawy usługi Intune i nie może być używany z innymi dzierżawami. Usługa Intune obsługuje teraz wiele lokalnych łączników programu Exchange na subskrypcję. Jeśli masz więcej niż jedną lokalną organizację programu Exchange, możesz skonfigurować osobny łącznik dla każdej organizacji programu Exchange.

- Łącznik dla lokalnej organizacji programu Exchange można zainstalować na dowolnej maszynie, jeśli jest ona w stanie komunikować się z programem Exchange Server.

- Łącznik obsługuje **środowisko serwera CAS programu Exchange**. Z technicznego punktu widzenia można bezpośrednio zainstalować łącznik na serwerze CAS programu Exchange, ale nie jest to zalecane, ponieważ zwiększa to obciążenie serwera. Podczas konfigurowania łącznika należy ustawić go tak, aby komunikował się z jednym z serwerów CAS programu Exchange.

- Program **Exchange ActiveSync** należy skonfigurować przy użyciu uwierzytelniania opartego na certyfikatach lub wpisu poświadczeń użytkownika.

- Aby po skonfigurowaniu zasad dostępu warunkowego i skierowaniu ich do użytkownika mógł on połączyć się ze swoją pocztą e-mail, jego **urządzenie** musi:
    - Zostać **zarejestrowane** w usłudze Intune lub być komputerem przyłączonym do domeny.
    - **Zostać zarejestrowane w usłudze Azure Active Directory**. Ponadto identyfikator klienta programu Exchange ActiveSync musi być zarejestrowany w usłudze Azure Active Directory.
<br></br>
- Usługa rejestrowania urządzeń w usłudze Azure AD (DRS) zostanie aktywowana automatycznie dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestrowania urządzeń usług AD FS, nie widzą zarejestrowanych urządzeń w lokalnej usłudze Active Directory. **Nie dotyczy to komputerów z systemem Windows i urządzeń z systemem Windows Phone**.

- **Być zgodne** z zasadami zgodności urządzenia wdrożonymi na tym urządzeniu.

- Jeśli warunki dostępu warunkowego nie zostaną spełnione, podczas logowania zostanie wyświetlony jeden z następujących komunikatów:
    - Jeśli urządzenie nie zostało zarejestrowane w usłudze Intune ani Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy, rejestrowania urządzenia i aktywowania poczty e-mail. Ten proces powoduje również skojarzenie identyfikatora programu Exchange ActiveSync urządzenia z rekordem urządzenia w usłudze Azure Active Directory.
    - Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny sieci Web portalu firmy usługi Intune lub aplikacji portalu firmy, gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.

### <a name="support-for-mobile-devices"></a>Obsługa urządzeń przenośnych

- System Windows Phone 8.1 lub nowszy
- Natywna aplikacja poczty e-mail w systemie iOS
- Klienci poczty korzystający z protokołu EAS (np. Gmail w systemie Android 4 lub nowszym).
- Klienci poczty korzystający z protokołu EAS na **urządzeniach z profilami służbowymi systemu Android:** na urządzeniach z profilami służbowymi systemu Android są obsługiwane tylko aplikacje **Gmail** i **Nine Work for Android Enterprise** w **profilu służbowym**. Aby dostęp warunkowy współdziałał z profilami służbowymi systemu Android, należy wdrożyć profil poczty e-mail dla aplikacji Gmail lub Nine Work for Android Enterprise, a także wdrożyć te aplikacje jako instalację wymaganą.

> [!NOTE]
> Program Microsoft Outlook dla systemów Android i iOS nie jest obsługiwany za pośrednictwem łącznika lokalnego programu Exchange. Jeśli chcesz korzystać z zasad dostępu warunkowego usługi Azure Active Directory i zasad rozwiązania Intune App Protection przy użyciu programu Outlook dla systemów iOS i Android dla skrzynek pocztowych w środowisku lokalnym, zobacz temat [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) (Używanie hybrydowego nowoczesnego uwierzytelniania w programie Outlook dla systemów iOS i Android). 

### <a name="support-for-pcs"></a>Obsługa komputerów

Natywna aplikacja **do obsługi poczty** w systemie Windows 8.1 lub nowszym (w przypadku zarejestrowania w usłudze Intune)


## <a name="configure-exchange-on-premises-access"></a>Konfiguracja dostępu do lokalnego programu Exchange

1. Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

1. Po pomyślnym zalogowaniu zostanie wyświetlony **pulpit nawigacyjny platformy Azure**.

1. W menu po lewej stronie wybierz pozycję  **Wszystkie usługi** i wpisz  **Intune** w filtrze pola tekstowego.

1. Wybierz pozycję  **Intune**, aby wyświetlić **pulpit nawigacyjny usługi Intune**.

1. Wybierz pozycję **Dostęp lokalny**. W okienku **Dostęp lokalny** wyświetlany jest stan zasad dostępu warunkowego oraz urządzeń, których dotyczą.

1. W obszarze **Zarządzaj** wybierz pozycję **Dostęp do lokalnego programu Exchange**.

1. W okienku **Dostęp do lokalnego programu Exchange** wybierz pozycję **Tak**, aby włączyć kontrolę dostępu do lokalnego programu Exchange.

    > [!NOTE]
    > Jeśli łącznik lokalnego programu Exchange Active Sync nie został skonfigurowany, opcja ta będzie wyłączona.  Należy najpierw zainstalować i skonfigurować co najmniej jeden łącznik przed włączeniem dostępu warunkowego do lokalnego programu Exchange. Więcej szczegółowych informacji znajduje się w temacie [Install the Intune On-premises Exchange Connector](exchange-connector-install.md) (Instalowanie łącznika lokalnego programu Exchange w usłudze Intune)

1. W obszarze **Przypisanie** wybierz pozycję **Objęte grupy**.  Użyj grupy zabezpieczeń użytkowników, która powinna mieć przypisany dostęp warunkowy. W wyniku tej akcji użytkownicy będą musieli zarejestrować swoje urządzenia w usłudze Intune i zachować zgodność z profilami zgodności.

1. Jeśli chcesz wykluczyć niektóre grupy użytkowników, możesz to zrobić, wybierając pozycję **Wykluczone grupy** i grupy użytkowników, które nie będą wymagać rejestracji urządzeń i zgodności.

1. W obszarze **Ustawienia** wybierz pozycję **Powiadomienia użytkowników**, aby zmodyfikować domyślną wiadomość e-mail. Ta wiadomość jest wysyłana do użytkownika, jeśli urządzenie nie jest zgodne, a chce on uzyskać dostęp do lokalnego programu Exchange. W szablonie wiadomości jest używany język znaczników.  Podczas pisania widać również podgląd wiadomości.
    > [!TIP]
    > Aby dowiedzieć się więcej o języku znaczników, zobacz ten [artykuł](https://en.wikipedia.org/wiki/Markup_language) w Wikipedii.

1. W okienku **Zaawansowane ustawienia dostępu do programu Exchange Active Sync** ustaw globalną zasadę domyślną dostępu z urządzeń, które nie są zarządzane przez usługę Intune, oraz zasady platformy zgodnie z opisem w dwóch następnych krokach.

1. Urządzeniom, których nie dotyczy dostęp warunkowy ani inne zasady, można zezwolić na dostęp do programu Exchange lub go zablokować.

   - Po ustawieniu zezwolenia na dostęp wszystkie urządzenia będą mogły natychmiast uzyskać dostęp do lokalnego programu Exchange.  Urządzenia, które należą do użytkowników w pozycji **Objęte grupy**, są blokowane, jeśli zostaną później ocenione jako niezgodne ze zgodnymi zasadami lub niezarejestrowane w usłudze Intune.
   - Po ustawieniu zablokowania dostępu początkowy dostęp wszystkich urządzeń do lokalnego programu Exchange zostanie natychmiast zablokowany.  Urządzenia, które należą do użytkowników w pozycji **Objęte grupy**, uzyskają dostęp po zarejestrowaniu urządzenia w usłudze Intune i ocenieniu go jako zgodnego. Na urządzeniach z systemem Android nieobsługujących systemu Samsung Knox Standard dostęp będzie zawsze zablokowany, gdyż nie obsługują one tego ustawienia.

1. W obszarze **Wyjątki dla platform urządzeń** wybierz przycisk **Dodaj**, aby określić platformy. Jeśli ustawienie **dostęp do urządzeń niezarządzanych** zostało ustawione na wartość **zablokowany**, urządzenia, które są zarejestrowane i zgodne, będą odblokowane, nawet jeśli występuje wyjątek dla platformy określający ich zablokowanie. Wybierz przycisk **Ok**, aby zapisać ustawienia.

1. W okienku **Lokalne** kliknij pozycję **Zapisz**, aby zapisać zasady dostępu warunkowego.

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a>Tworzenie zasad dostępu warunkowego usługi Azure AD w usłudze Intune

Począwszy od usługi Intune w wersji 1704, administratorzy mogą tworzyć zasady dostępu warunkowego usługi Azure AD w witrynie Azure Portal usługi Intune. Zapewnia to wygodę, gdyż nie ma konieczności przełączania między obciążeniami usług Azure i Intune.

> [!IMPORTANT]
> Aby utworzyć zasady dostępu warunkowego usługi Azure AD w portalu Intune Azure, potrzebna jest licencja usługi Azure AD w wersji Premium.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego usługi Azure AD

1. Na **pulpicie nawigacyjnym Intune** wybierz pozycję **Dostęp warunkowy**.

2. W okienku **Zasady** wybierz pozycję **Nowe zasady**, aby utworzyć nowe zasady dostępu warunkowego usługi Azure AD.

## <a name="see-also"></a>Zobacz też

[Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access) (Dostęp warunkowy w usłudze Azure Active Directory)
