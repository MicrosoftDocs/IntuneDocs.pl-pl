---
title: "Zasady dostępu warunkowego do lokalnego programu Exchange | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: jak konfigurować dostęp warunkowy do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej w usłudze Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581f9be824ea883fd0208abc3b2ecc09174cb911
ms.openlocfilehash: a80d6a19948291cc80e42ad5a9a2f016effb2f37


---

# <a name="how-to-create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Tworzenie zasad dostępu warunkowego do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej w wersji zapoznawczej usługi Microsoft Azure Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

W tym temacie opisano proces konfigurowania dostępu warunkowego do lokalnego programu Exchange w oparciu o zgodność urządzeń.

Jeśli masz środowisko usługi Exchange Online w wersji dedykowanej i chcesz sprawdzić, czy zawiera ono nową, czy starą konfigurację, skontaktuj się z menedżerem konta. Aby kontrolować dostęp poczty e-mail do lokalnego programu Exchange lub do starszej wersji środowiska usługi Exchange Online w wersji dedykowanej, skonfiguruj dostęp warunkowy do lokalnego programu Exchange w usłudze Intune.

## <a name="prerequisites"></a>Wymagania wstępne

**Przed** skonfigurowaniem dostępu warunkowego zweryfikuj następujące kwestie:

- Program Exchange musi być w wersji **Exchange 2010 lub nowszej**. Macierz serwerów dostępu klienta (CAS) serwera programu Exchange jest obsługiwana.
- Należy użyć **łącznika lokalnego programu Exchange programu Exchange Active Sync**, który łączy usługę Intune z lokalnym programem Microsoft Exchange. Szczegółowe informacje dotyczące łącznika znajdują się w temacie <link>

  - Łącznik lokalnego programu Exchange dostępny w konsoli usługi Intune jest przeznaczony dla Twojej dzierżawy usługi Intune i nie może być używany z innymi dzierżawami. Ponadto upewnij się, że łącznik programu Exchange dla Twojej dzierżawy został zainstalowany **tylko na jednym komputerze**.

Ten łącznik powinien zostać pobrany z poziomu konsoli administracyjnej usługi Intune. Opis konfiguracji łącznika lokalnego programu Exchange znajduje się w temacie <link to new topic>

Łącznik można zainstalować na dowolnym komputerze, jeśli komputer ten jest w stanie komunikować się z programem Exchange Server.

- Łącznik obsługuje **środowisko serwera CAS programu Exchange**. Z technicznego punktu widzenia można bezpośrednio zainstalować łącznik na serwerze CAS programu Exchange, ale nie jest to zalecane, ponieważ spowoduje to zwiększenie obciążenia serwera. Podczas konfigurowania łącznika należy ustawić go tak, aby komunikował się z jednym z serwerów CAS programu Exchange.
- Program **Exchange ActiveSync** należy skonfigurować przy użyciu uwierzytelniania opartego na certyfikatach lub wpisu poświadczeń użytkownika.

Aby po skonfigurowaniu zasad dostępu warunkowego i skierowaniu ich do użytkownika mógł on połączyć się ze swoją pocztą e-mail, jego **urządzenie** musi:

- Zostać **zarejestrowane** w usłudze Intune lub być komputerem przyłączonym do domeny.
- **Zostać zarejestrowane w usłudze Azure Active Directory**. Ponadto identyfikator klienta programu Exchange ActiveSync musi być zarejestrowany w usłudze Azure Active Directory.

Usługa AAD DRS zostanie automatycznie uaktywniona dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestrowania urządzeń usług AD FS, nie będą widzieć zarejestrowanych urządzeń w lokalnej usłudze Active Directory. **Nie dotyczy to komputerów z systemem Windows i urządzeń z systemem Windows Phone**.

- Być **zgodne** z zasadami zgodności usługi Intune wdrożonymi na tym urządzeniu.

Jeśli warunki dostępu warunkowego nie są spełnione, podczas logowania zostanie wyświetlony jeden z następujących komunikatów:

- Jeśli urządzenie nie zostało zarejestrowane w usłudze Intune ani Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy, rejestrowania urządzenia i aktywowania poczty e-mail. Ten proces powoduje również skojarzenie identyfikatora programu Exchange ActiveSync urządzenia z rekordem urządzenia w usłudze Azure Active Directory.
- Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny sieci Web portalu firmy usługi Intune lub aplikacji portalu firmy, gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.

## <a name="support-for-mobile-devices"></a>Obsługa urządzeń przenośnych

- System Windows Phone 8.1 lub nowszy
- Natywna aplikacja poczty e-mail w systemie iOS
- Klienci poczty korzystający z protokołu EAS (np. Gmail w systemie Android 4 lub nowszym).
- Klienci poczty korzystający z protokołu EAS **Urządzenia z programem Android for Work:** na urządzeniach z programem Android for Work są obsługiwane tylko aplikacje **Gmail** i **Nine Work** w **profilu służbowym**. Aby dostęp warunkowy współdziałał z programem Android for Work, należy wdrożyć profil poczty e-mail dla aplikacji Gmail lub Nine Work, a także wdrożyć te aplikacje jako instalację wymaganą.

>[!NOTE]
>Aplikacja Microsoft Outlook dla systemów Android i iOS nie jest obsługiwana.

> Program Android for Work będzie przez najbliższe kilka miesięcy wdrażany u dzierżawców usługi Intune.

Aby uzyskać dodatkowe informacje o stanie pomocy technicznej dla programu Android for Work, zapoznaj się z zawiadomieniem dotyczącym programu Android for Work w temacie [Co nowego w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/whats-new/whats-new-archive#october-2016) w wersji z października 2016 r.

## <a name="support-for-pcs"></a>Obsługa komputerów

Aplikacja **do obsługi poczty** w systemie Windows 8.1 lub nowszym (w przypadku zarejestrowania w usłudze Intune)


## <a name="configure-exchange-on-premises-access"></a>Konfiguracja dostępu do lokalnego programu Exchange

1. Wybierz obciążenie **Dostęp warunkowy** w portalu Azure Portal, aby otworzyć blok lokalny.
2. W bloku **Lokalny** wyświetlany jest stan zasad dostępu warunkowego oraz urządzenia, których to dotyczy.
3. W obszarze **Zarządzaj** wybierz pozycję **Dostęp do lokalnego programu Exchange**.
4. W bloku **Dostęp do lokalnego programu Exchange** wybierz przycisk **Tak**, aby włączyć kontrolę dostępu do lokalnego programu Exchange.

  >[!NOTE]
  >Jeśli łącznik lokalnego programu Exchange Active Sync nie został skonfigurowany, opcja ta będzie wyłączona.  Należy najpierw zainstalować i skonfigurować ten łącznik, a potem włączyć dostęp warunkowy do lokalnego programu Exchange. Więcej szczegółowych informacji znajduje się w temacie [Install the Intune On-premises Exchange Connector](install-intune-on-premises-exchange-connector.md) (Instalowanie łącznika lokalnego programu Exchange w usłudze Intune)

5. W obszarze **Przypisanie** wybierz pozycję **Objęte grupy**.  Użyj grupy zabezpieczeń użytkowników, która powinna mieć przypisany dostęp warunkowy.  Użytkownicy będą musieli zarejestrować swoje urządzenia w usłudze Intune i zachować zgodność z profilami zgodności.
6. Jeśli chcesz wykluczyć niektóre grupy użytkowników, możesz to zrobić, wybierając pozycję **Wykluczone grupy** i grupy użytkowników, które nie będą wymagać rejestracji urządzeń i zgodności.
7. W obszarze **Ustawienia** wybierz pozycję **Powiadomienia użytkowników**, aby zmodyfikować domyślną wiadomość e-mail. Ta wiadomość jest wysyłana do użytkownika, jeśli urządzenie nie jest zgodne, a chce on uzyskać dostęp do lokalnego programu Exchange. W szablonie wiadomości jest używany język znaczników.  Podczas pisania będzie również widoczny podgląd wiadomości. Aby dowiedzieć się więcej o języku znaczników, zobacz ten [artykuł](https://en.wikipedia.org/wiki/Markup_language) w Wikipedii.
8. W bloku **Zaawansowane ustawienia dostępu do programu Exchange Active Sync** ustaw globalną zasadę domyślną dostępu z urządzeń, które nie są zarządzane przez usługę Intune, oraz zasady platformy zgodnie z opisem w dwóch następnych krokach.
9. Urządzeniom, których nie dotyczy dostęp warunkowy ani inne zasady, można zezwolić na dostęp do programu Exchange lub go zablokować.
  - Po ustawieniu zezwolenia na dostęp wszystkie urządzenia będą mogły natychmiast uzyskać dostęp do lokalnego programu Exchange.  Urządzenia, które należą do użytkowników w pozycji **Objęte grupy**, są blokowane, jeśli zostaną później ocenione jako niezgodne ze zgodnymi zasadami lub niezarejestrowane w usłudze Intune.
  - Po ustawieniu zablokowania dostępu początkowy dostęp wszystkich urządzeń do lokalnego programu Exchange zostanie natychmiast zablokowany.  Urządzenia, które należą do użytkowników w pozycji **Objęte grupy**, uzyskają dostęp po zarejestrowaniu urządzenia w usłudze Intune i ocenieniu go jako zgodne. Na urządzeniach z systemem Android nieobsługujących systemu Samsung KNOX Standard dostęp będzie zawsze zablokowany, gdyż nie obsługują one tego ustawienia.
10. W obszarze **Wyjątki dla platform urządzeń** wybierz przycisk **Dodaj**, aby określić platformy. Jeśli ustawienie **dostęp do urządzeń niezarządzanych** zostało ustawione na wartość **zablokowany**, urządzenia, które są zarejestrowane i zgodne będą odblokowane, nawet jeśli występuje wyjątek dla platformy określający ich zablokowanie. Wybierz przycisk **Ok**, aby zapisać ustawienia.
11. W bloku **Lokalne** kliknij przycisk **Zapisz**, aby zapisać zasady dostępu warunkowego.



<!--HONumber=Feb17_HO1-->


