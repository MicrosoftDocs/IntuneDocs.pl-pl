---
title: Tworzenie zasad dostępu warunkowego programu Exchange
titleSuffix: Microsoft Intune
description: Konfigurowanie dostępu warunkowego do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej w usłudze Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 644297777e8a103d6ffdc5f025ebf8f29591fda8
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188468"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Tworzenie zasad dostępu warunkowego do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej w usłudze Intune

W tym artykule pokazano, jak skonfigurować dostęp warunkowy dla lokalnej instalacji programu Exchange w oparciu o zgodność urządzenia.

Jeśli masz środowisko usługi Exchange Online w wersji dedykowanej i chcesz sprawdzić, czy zawiera ono nową, czy starszą konfigurację, skontaktuj się z menedżerem ds. klientów. Aby kontrolować dostęp poczty e-mail do lokalnego programu Exchange lub do starszej wersji środowiska usługi Exchange Online w wersji dedykowanej, skonfiguruj dostęp warunkowy do lokalnego programu Exchange w usłudze Intune.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Przed skonfigurowaniem dostępu warunkowego należy się upewnić, że istnieje następująca konfiguracja:

- Program Exchange jest w wersji **Exchange 2010 SP1 lub nowszej**. Macierz serwerów dostępu klienta (CAS) serwera programu Exchange jest obsługiwana.

- Zainstalowany i używany jest [łącznik lokalny programu Exchange programu Exchange Active Sync](exchange-connector-install.md), który łączy usługę Intune z lokalnym programem Exchange.

    >[!IMPORTANT]  
    >Usługa Intune obsługuje wiele lokalnych łączników programu Exchange na subskrypcję.  Jednak każdy łącznik lokalnego programu Exchange jest przeznaczony dla pojedynczej dzierżawy usługi Intune i nie może być używany z innymi dzierżawami.  Jeśli masz więcej niż jedną lokalną organizację programu Exchange, możesz skonfigurować osobny łącznik dla każdej organizacji programu Exchange.

- Łącznik dla lokalnej organizacji programu Exchange można zainstalować na dowolnej maszynie, jeśli jest ona w stanie komunikować się z serwerem programu Exchange.

- Łącznik obsługuje **środowisko serwera CAS programu Exchange**. Usługa Intune obsługuje bezpośrednie instalowanie łącznika na serwerze CAS programu Exchange. Zalecamy zainstalowanie go na osobnym komputerze z powodu dodatkowego obciążenia umieszczanego na serwerze przez ten łącznik. Podczas konfigurowania łącznika należy ustawić go tak, aby komunikował się z jednym z serwerów CAS programu Exchange.

- Program **Exchange ActiveSync** należy skonfigurować przy użyciu uwierzytelniania opartego na certyfikatach lub wpisu poświadczeń użytkownika.

- Aby po skonfigurowaniu zasad dostępu warunkowego i skierowaniu ich do użytkownika mógł on połączyć się ze swoją pocztą e-mail, jego **urządzenie** musi:
  - Zostać **zarejestrowane** w usłudze Intune lub być komputerem przyłączonym do domeny.
  - **Zostać zarejestrowane w usłudze Azure Active Directory**. Ponadto identyfikator klienta programu Exchange ActiveSync musi być zarejestrowany w usłudze Azure Active Directory.

- Usługa rejestrowania urządzeń w usłudze Azure AD (DRS) zostanie aktywowana automatycznie dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestrowania urządzeń usług AD FS, nie widzą zarejestrowanych urządzeń w lokalnej usłudze Active Directory. **Nie dotyczy to komputerów z systemem Windows i urządzeń z systemem Windows Phone**.

- **Być zgodne** z zasadami zgodności urządzenia wdrożonymi na tym urządzeniu.

- Jeśli warunki dostępu warunkowego nie zostaną spełnione, podczas logowania zostanie wyświetlony jeden z następujących komunikatów:
  - Jeśli urządzenie nie zostało zarejestrowane w usłudze Intune lub Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy, rejestrowania urządzenia i aktywowania poczty e-mail. Ten proces powoduje również skojarzenie identyfikatora programu Exchange ActiveSync urządzenia z rekordem urządzenia w usłudze Azure Active Directory.
  - Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny internetowej Portal firmy usługi Intune lub aplikacji Portal firmy. W Portalu firmy można znaleźć informacje o problemie i sposobie jego rozwiązania.

### <a name="support-for-mobile-devices"></a>Obsługa urządzeń przenośnych

- System Windows Phone 8.1 lub nowszy
- Natywna aplikacja poczty e-mail w systemie iOS
- Klienci poczty korzystający z protokołu EAS (np. Gmail w systemie Android 4 lub nowszym).
- Klienci poczty korzystający z protokołu EAS na **urządzeniach z profilami służbowymi systemu Android:** na urządzeniach z profilami służbowymi systemu Android są obsługiwane tylko aplikacje **Gmail** i **Nine Work for Android Enterprise** w **profilu służbowym**. Aby dostęp warunkowy współdziałał z profilami służbowymi systemu Android, należy wdrożyć profil poczty e-mail dla aplikacji Gmail lub Nine Work for Android Enterprise, a także wdrożyć te aplikacje jako instalację wymaganą.

> [!NOTE]
> Program Microsoft Outlook dla systemów Android i iOS nie jest obsługiwany za pośrednictwem łącznika lokalnego programu Exchange. Jeśli chcesz korzystać z zasad dostępu warunkowego usługi Azure Active Directory i zasad rozwiązania Intune App Protection przy użyciu programu Outlook dla systemów iOS i Android dla skrzynek pocztowych w środowisku lokalnym, zobacz temat [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) (Używanie hybrydowego nowoczesnego uwierzytelniania w programie Outlook dla systemów iOS i Android).

### <a name="support-for-pcs"></a>Obsługa komputerów

Natywna aplikacja **do obsługi poczty** w systemie Windows 8.1 lub nowszym (w przypadku zarejestrowania do zarządzania urządzeniami przenośnymi w usłudze Intune)

## <a name="configure-exchange-on-premises-access"></a>Konfiguracja dostępu do lokalnego programu Exchange

Zanim zaczniesz korzystać z następującej procedury w celu skonfigurowania kontroli dostępu do lokalnego programu Exchange, musisz zainstalować i skonfigurować co najmniej jeden [łącznik lokalnego programu Exchange usługi Intune](exchange-connector-install.md) dla lokalnego programu Exchange.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Przejdź do pozycji **Administracja dzierżawą** > **Dostęp do programu Exchange**, a następnie wybierz pozycję **Dostęp do lokalnego wystąpienia programu Exchange**.

3. W okienku **Dostęp do lokalnego wystąpienia programu Exchange** wybierz pozycję **Tak**, aby *włączyć kontrolę dostępu do lokalnego programu Exchange*.

4. W obszarze **Przypisanie** wybierz pozycję **Wybierz grupy do uwzględnienia**, a następnie wybierz co najmniej jedną grupę w celu skonfigurowania dostępu.

   Do członków wybranych grup są stosowane zasady dostępu warunkowego dla dostępu lokalnego programu Exchange. Użytkownicy, którzy odbierają te zasady, muszą zarejestrować swoje urządzenia w usłudze Intune i zachować zgodność z profilami zgodności, zanim będą mogli uzyskać dostęp do lokalnego programu Exchange.

5. Aby wykluczyć grupy, wybierz pozycję **Wybierz grupy do wykluczenia**, a następnie wybierz co najmniej jedną grupę, która zostanie zwolniona z wymagań rejestracji urządzeń i zgodności z profilami zgodności przed uzyskaniem dostępu do lokalnego programu Exchange. 

6. Następnie skonfiguruj ustawienia lokalnego programu Exchange Connector w usłudze Intune.  W obszarze **Konfiguracja** w oknie *Dostęp do lokalnego wystąpienia programu Exchange* wybierz pozycję **Lokalny łącznik Exchange ActiveSync**, a następnie wybierz łącznik organizacji programu Exchange, którą chcesz skonfigurować.

7. W obszarze **Ustawienia** wybierz pozycję **Powiadomienia użytkownika**, aby zmodyfikować domyślną wiadomość e-mail, która jest wysyłana do użytkowników, jeśli ich urządzenia nie są zgodne, a chcą oni uzyskać dostęp do lokalnego programu Exchange. W szablonie wiadomości jest używany język znaczników.  Podczas pisania widać również podgląd wiadomości.
   > [!TIP]
   > Aby dowiedzieć się więcej o języku znaczników, zobacz ten [artykuł](https://en.wikipedia.org/wiki/Markup_language) w Wikipedii.
 
   Wybierz przycisk **OK**, aby zapisać zmiany w celu skonfigurowania dostępu do lokalnego programu Exchange.

8. Następnie wybierz pozycję **Zaawansowane ustawienia dostępu do programu Exchange ActiveSync**, aby otworzyć okienko *Zaawansowane ustawienia dostępu do programu Exchange Active Sync*, w którym skonfigurujesz reguły dostępu do urządzenia:  

   - W przypadku ustawienia **Dostęp do urządzeń niezarządzanych** ustaw globalną regułę domyślną dostępu z urządzeń, na które dostęp warunkowy lub inne reguły nie mają wpływu:

     - **Zezwalaj na dostęp** — wszystkie urządzenia będą mogły natychmiast uzyskać dostęp do lokalnego programu Exchange. Urządzenia, które należą do użytkowników w grupach skonfigurowanych zgodnie z poprzednią procedurą, będą blokowane, jeśli zostaną później ocenione jako niezgodne z zasadami zgodności lub niezarejestrowane w usłudze Intune.

     - **Blokuj dostęp** i **Kwarantanna** — początkowy dostęp wszystkich urządzeń do lokalnego programu Exchange zostanie natychmiast zablokowany. Urządzenia, które należą do użytkowników w grupach skonfigurowanych zgodnie z poprzednią procedurą, uzyskają dostęp po zarejestrowaniu urządzenia w usłudze Intune i jego ocenie jako zgodnego. 

       Urządzenia z systemem Android, na których *nie* uruchomiono systemu Samsung Knox Standard, nie obsługują tego ustawienia i są zawsze zablokowane.

   -  Dla ustawienia **Wyjątki platformy urządzeń** wybierz przycisk **Dodaj**, a następnie określ szczegóły platformy odpowiednio do potrzeb danego środowiska. 
   
      Jeśli ustawienie **Dostęp urządzeń niezarządzanych** zostało ustawione na wartość **Zablokowany**, urządzenia, które są zarejestrowane i zgodne, będą odblokowane, nawet jeśli występuje wyjątek platformy określający ich zablokowanie.  
   
   Wybierz przycisk **OK**, aby zapisać zmiany.

9. Wybierz pozycję **Zapisz**, aby zapisać zasady dostępu warunkowego do programu Exchange.

Następnie utwórz zasady zgodności i przypisz je do użytkowników, aby usługa Intune oceniła ich urządzenia przenośne. Zobacz temat [Set rules on devices to allow access to resources in your organization using Intune](device-compliance-get-started.md) (Ustawianie reguł na urządzeniach, aby zezwolić na dostęp do zasobów w organizacji przy użyciu usługi Intune).

## <a name="next-steps"></a>Następne kroki

[Troubleshooting Intune On-Premises Exchange Connector in Microsoft Intune](https://support.microsoft.com/help/4471887) (Rozwiązywanie problemów z lokalnym programem Exchange Connector w usłudze Microsoft Intune)
