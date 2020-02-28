---
title: Konfigurowanie ustawień poczty e-mail dla urządzeń z systemem iOS/iPadOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień poczty e-mail, które możesz skonfigurować i dodać w przypadku urządzeń z systemem iOS lub iPadOS w usłudze Microsoft Intune, takich jak używanie serwerów programu Exchange i pobieranie atrybutów z usługi Azure Active Directory. Możesz również włączyć protokół SSL, uwierzytelniać użytkowników przy użyciu certyfikatów lub nazwy użytkownika/hasła i synchronizować pocztę e-mail na urządzeniach z systemem iOS/iPadOS za pomocą profilów konfiguracji urządzenia w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ea06c50b1da237d4a822e80a8085b3b51913cec
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512810"
---
# <a name="add-e-mail-settings-for-ios-and-ipados-devices-in-microsoft-intune"></a>Dodawanie ustawień poczty e-mail dla urządzeń z systemem iOS i iPadOS w usłudze Microsoft Intune

W usłudze Microsoft Intune możesz utworzyć i skonfigurować profil poczty e-mail w celu nawiązywania połączenia z serwerem poczty e-mail, wybrać sposób uwierzytelniania użytkowników, użyć szyfrowania S/MIME na potrzeby szyfrowania i nie tylko.

W tym artykule wymieniono i opisano wszystkie ustawienia poczty e-mail dostępne dla urządzeń z systemem iOS/iPadOS. Możesz utworzyć profil konfiguracji urządzenia, aby wypchnąć lub wdrożyć te ustawienia poczty e-mail na urządzeniach z systemem iOS/iPadOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](../email-settings-configure.md).

> [!NOTE]
> Te ustawienia są dostępne dla wszystkich typów rejestracji. Aby uzyskać więcej informacji na temat typów rejestracji, zobacz [Rejestracja systemu iOS/iPadOS](../ios-enroll.md).

## <a name="exchange-activesync-account-settings"></a>Ustawienia konta programu Exchange ActiveSync

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera Exchange.
- **Nazwa konta**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (AAD). Usługa Intune dynamicznie generuje nazwę użytkownika używaną przez ten profil. Dostępne opcje:
  - **Nazwa główna użytkownika**: pobiera nazwę, taką jak `user1` lub `user1@contoso.com`
  - **Podstawowy adres SMTP**: Pobiera nazwę w formacie adresu e-mail, na przykład `user1@contoso.com`
  - **Nazwa konta sAM**: wymaga domeny, takiej jak `domain\user1`. Wprowadź też następujące ustawienia:  
    - **Źródło nazwy domeny użytkownika**: wybierz pozycję **AAD** (Azure Active Directory) lub **Niestandardowe**.
      - **AAD**: pobiera atrybuty z usługi Azure AD. Wprowadź też następujące ustawienia:
        - **Atrybut nazwy domeny użytkownika z usługi AAD**: wybierz pobieranie atrybutu użytkownika **Pełna nazwa domeny** (`contoso.com`) lub **Nazwa NetBIOS** (`contoso`).

      - **Niestandardowe**: pobiera atrybuty z nazwy domeny niestandardowej. Wprowadź też następujące ustawienia:
        - **Nazwa domeny niestandardowej do użycia**: wprowadź wartość używaną przez usługę Intune jako nazwa domeny, taką jak `contoso.com` lub `contoso`.

- **Atrybut adresu e-mail z usługi AAD**: Wybierz sposób generowania adresu e-mail użytkownika. Dostępne opcje:
  - **Główna nazwa użytkownika**: jako adresu e-mail używa pełnej nazwy głównej, takiej jak `user1@contoso.com` lub `user1`.
  - **Podstawowy adres SMTP**: używa podstawowego adresu SMTP, takiego jak `user1@contoso.com`, do logowania się do programu Exchange.
- **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania użytkowników na serwerze poczty e-mail. Dostępne opcje:
  - **Certyfikat**: Wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS, który będzie używany do uwierzytelniania połączenia z programem Exchange. Ta opcja zapewnia najbezpieczniejsze i bezproblemowe środowisko dla użytkowników.
  - **Nazwa użytkownika i hasło**: Użytkownicy są monitowani o wprowadzenie nazwy użytkownika i hasła.
  - **Poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Aby uzyskać więcej informacji, zobacz [Korzystanie z poświadczeń pochodnych w usłudze Microsoft Intune](../protect/derived-credentials.md).

  >[!NOTE]
  > Uwierzytelnianie Azure Multi-Factor Authentication nie jest obsługiwane.
  
- **SSL**: Wybierz pozycję **Włącz**, aby użyć protokołu SSL (Secure Sockets Layer) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **OAuth**: Wybierz pozycję **Włącz**, aby użyć protokołu OAuth (Open Authorization) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z programem Exchange. Jeśli serwer OAuth korzysta z uwierzytelniania przy użyciu certyfikatu, wybierz opcję **Certyfikat** w obszarze **Metoda uwierzytelniania** i dołącz certyfikat do profilu. Możesz też wybrać opcję **Nazwa użytkownika i hasło** w obszarze **Metoda uwierzytelniania**. Jeśli korzystasz z protokołu OAuth, sprawdź następujące elementy:

  - Przed skierowaniem tego profilu do użytkowników upewnij się, że rozwiązanie poczty e-mail obsługuje protokół OAuth. Instalacja usługi Office 365 Exchange Online obsługuje uwierzytelnianie za pomocą protokołu OAuth. Instalacja lokalna programu Exchange i rozwiązania partnerów lub innych firm mogą nie obsługiwać protokołu OAuth. Instalacja lokalna programu Exchange może być skonfigurowana pod kątem obsługi nowoczesnego uwierzytelniania — zobacz wpis na blogu [Announcing Hybrid Modern Authentication for Exchange On-Premises](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) (Ogłoszenie hybrydowego nowoczesnego uwierzytelniania dla lokalnej instalacji programu Exchange).

    Jeśli profil poczty e-mail korzysta z uwierzytelniania Oauth, a usługa poczty e-mail go nie obsługuje, opcja **Wprowadź ponownie hasło** będzie wydawała się uszkodzona. Na przykład gdy użytkownik wybierze opcję **Wprowadź ponownie hasło** w ustawieniach urządzenia firmy Apple, nic się nie stanie.

  - Po włączeniu uwierzytelniania OAuth użytkownicy końcowi będą korzystać z innego środowiska logowania do konta e-mail z „nowoczesnym uwierzytelnianiem”, które obsługuje uwierzytelnianie wieloskładnikowe (MFA). 

  - W niektórych organizacjach użytkownicy końcowi nie mają możliwości skorzystania z [dostępu samoobsługowego do aplikacji](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). W tym scenariuszu logowanie za pomocą nowoczesnego uwierzytelniania może zakończyć się niepowodzeniem, jeśli administrator nie utworzy aplikacji firmowej „Konta systemu iOS” i nie przydzieli użytkownikom dostępu do aplikacji w usłudze Azure AD.

    Domyślną czynnością jest dodanie aplikacji przy użyciu funkcji **Dodaj aplikację** w [panelu dostępu do aplikacji](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **bez zatwierdzenia firmy**. Aby uzyskać więcej informacji, zobacz [Assign users to applications (Przypisywanie użytkowników do aplikacji)](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Włączenie uwierzytelniania OAuth będzie miało następujące skutki:  
  > 1. Urządzeniom, które są już wybrane jako docelowe, zostaną przypisane nowe profile.
  > 2. Użytkownikom końcowym wyświetli się monit o ponowne wprowadzenie swoich poświadczeń.

## <a name="exchange-activesync-profile-configuration"></a>Konfiguracja profilu programu Exchange ActiveSync

> [!IMPORTANT]
> Skonfigurowanie tych ustawień powoduje wdrożenie nowego profilu na urządzeniu, nawet w przypadku zaktualizowania istniejącego profilu poczty e-mail w celu uwzględnienia tych ustawień. Użytkownicy są monitowani o wprowadzenie hasła do konta programu Exchange ActiveSync. Te ustawienia obowiązują po wprowadzeniu hasła.

- **Dane programu Exchange do synchronizacji**: w przypadku korzystania z programu Exchange ActiveSync wybierz usługi programu Exchange, które mają być synchronizowane na urządzeniu: kalendarz, kontakty, przypomnienia, notatki i poczta e-mail. Dostępne opcje:
  - **Wszystkie dane** (wartość domyślna): synchronizacja jest włączona dla wszystkich usług.
  - **Tylko poczta e-mail**: synchronizacja jest włączona tylko dla poczty e-mail. Synchronizacja jest wyłączona dla innych usług.
  - **Tylko kalendarz**: synchronizacja jest włączona tylko dla kalendarza. Synchronizacja jest wyłączona dla innych usług.
  - **Tylko kalendarz i kontakty**: synchronizacja jest włączona tylko dla kalendarza i kontaktów. Synchronizacja jest wyłączona dla innych usług.
  - **Tylko kontakty**: synchronizacja jest włączona tylko dla kontaktów. Synchronizacja jest wyłączona dla innych usług.

  Ta funkcja ma zastosowanie do:  
  - System iOS 13.0 i nowsze
  - System iPadOS 13.0 i nowsze

- **Zezwalaj użytkownikom na zmianę ustawień synchronizacji**: wybierz, czy użytkownicy mogą zmieniać ustawienia programu Exchange ActiveSync dla usług programu Exchange na urządzeniu: kalendarz, kontakty, przypomnienia, notatki i poczta e-mail. Dostępne opcje:

  - **Tak** (wartość domyślna): użytkownicy mogą zmieniać zachowanie synchronizacji dla wszystkich usług. Wybranie opcji **Tak** umożliwia zmianę *wszystkich* usług.
  - **Nie**: użytkownicy nie mogą zmieniać ustawień synchronizacji dla wszystkich usług. Wybranie opcji **Nie** blokuje zmienianie ustawień dla *wszystkich* usług.

  > [!TIP]
  > Jeśli ustawienie **Dane programu Exchange do synchronizacji** skonfigurowano na potrzeby synchronizowania tylko niektórych usług, zalecamy wybranie opcji **Nie** dla tego ustawienia. Wybranie opcji **Nie** uniemożliwia użytkownikom zmienianie synchronizowanej usługi programu Exchange.

  Ta funkcja ma zastosowanie do:  
  - System iOS 13.0 i nowsze
  - System iPadOS 13.0 i nowsze

## <a name="exchange-activesync-email-settings"></a>Ustawienia poczty e-mail programu Exchange ActiveSync

- **S/MIME**: Protokół S/MIME używa certyfikatów poczty e-mail, które zapewniają dodatkowe zabezpieczenia wiadomości e-mail za pomocą podpisywania, szyfrowania i odszyfrowywania. Gdy używasz protokołu S/MIME w wiadomościach e-mail, potwierdzasz autentyczność nadawcy oraz integralność i poufność wiadomości.

  Dostępne opcje:

  - **Wyłącz protokół S/MIME** (wartość domyślna): nie używa certyfikatu poczty e-mail protokołu S/MIME do podpisywania, szyfrowania i odszyfrowywania wiadomości e-mail.
  - **Włącz protokół S/MIME**: umożliwia użytkownikom podpisywanie lub szyfrowanie wiadomości e-mail w natywnej aplikacji pocztowej systemu iOS/iPadOS. Wprowadź też następujące ustawienia:

    - **Włączone podpisywanie S/MIME**: Opcja **Wyłącz** (wartość domyślna) nie zezwala użytkownikom na cyfrowe podpisywanie wiadomości. Wybierz opcję **Włącz**, aby umożliwić użytkownikom cyfrowe podpisywanie wychodzących wiadomości e-mail dla wprowadzonego konta. Dzięki podpisywaniu użytkownicy odbierający wiadomości mogą być pewni, że wiadomość pochodzi od określonego nadawcy, a nie od kogoś, kto udaje, że jest tym nadawcą.
      - **Zezwalaj użytkownikowi na zmianę ustawienia**: Opcja **Włącz** umożliwia użytkownikom zmianę opcji podpisywania. Opcja **Wyłącz** (wartość domyślna) uniemożliwia użytkownikom zmianę podpisywania i zmusza użytkowników do korzystania z skonfigurowanego podpisywania.
      - **Typ certyfikatu podpisywania**: dostępne opcje:
        - **Nieskonfigurowane**: Usługa Intune nie zmienia ani nie aktualizuje tego ustawienia.
        - **Brak**: Jako administrator nie wymuszasz określonego certyfikatu. Wybierz tę opcję, aby użytkownicy mogli wybrać własny certyfikat.
        - **Poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Aby uzyskać więcej informacji, zobacz [Korzystanie z poświadczeń pochodnych w usłudze Microsoft Intune](../protect/derived-credentials.md).
        - **Certyfikaty**: Wybierz istniejący profil certyfikatu PKCS lub SCEP, który jest używany do podpisywania wiadomości e-mail.
      - **Zezwalaj użytkownikowi na zmianę ustawienia**: Opcja **Włącz** umożliwia użytkownikom zmianę certyfikatu podpisywania. Wybranie opcji **Wyłącz** (domyślnej) uniemożliwia użytkownikom zmienianie certyfikatu podpisywania i wymusza na nich stosowanie certyfikatu skonfigurowanego przez Ciebie.

        Ta funkcja ma zastosowanie do:  
        - iOS 12 i nowsze wersje
        - iPadOS 12 i nowsze wersje

    - **Szyfruj domyślnie**: Wybranie opcji **Włącz** powoduje domyślne szyfrowanie wszystkich wiadomości. Wybranie opcji **Wyłącz** (domyślnej) powoduje, że szyfrowanie wszystkich wiadomości nie jest zachowaniem domyślnym.
      - **Zezwalaj użytkownikowi na zmianę ustawienia**: Opcja **Włącz** umożliwia użytkownikom zmienianie domyślnego zachowania szyfrowania. Wybranie opcji **Wyłącz** uniemożliwia użytkownikom zmienianie domyślnego zachowania szyfrowania i wymusza na nich stosowanie ustawienia skonfigurowanego przez Ciebie.

        Ta funkcja ma zastosowanie do:  
        - iOS 12 i nowsze wersje
        - iPadOS 12 i nowsze wersje

    - **Wymuś szyfrowanie poszczególnych wiadomości**: Szyfrowanie poszczególnych wiadomości umożliwia użytkownikom wybranie, które wiadomości e-mail mają być szyfrowane przed wysłaniem.

      Wybierz opcję **Włącz**, aby wyświetlić opcję szyfrowania poszczególnych wiadomości podczas tworzenia nowej wiadomości e-mail. Użytkownicy mogą w ten sposób wybrać opcję zaszyfrowania wiadomości lub z niej zrezygnować. Jeśli także ustawienie **Szyfruj domyślnie** jest włączone, włączenie szyfrowania poszczególnych wiadomości umożliwia użytkownikom zrezygnowanie z szyfrowania pojedynczych wiadomości.

      Wybranie opcji **Wyłącz** (domyślnej) powoduje, że opcja szyfrowania poszczególnych wiadomości nie jest widoczna. Jeśli również opcja **Szyfruj domyślnie** jest wyłączona, włączenie szyfrowania poszczególnych wiadomości umożliwia użytkownikom skorzystanie z szyfrowania pojedynczych wiadomości.

      - **Typ certyfikatu szyfrowania**: dostępne opcje:
        - **Nieskonfigurowane**: Usługa Intune nie zmienia ani nie aktualizuje tego ustawienia.
        - **Brak**: Jako administrator nie wymuszasz określonego certyfikatu. Wybierz tę opcję, aby użytkownicy mogli wybrać własny certyfikat.
        - **Poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Aby uzyskać więcej informacji, zobacz [Korzystanie z poświadczeń pochodnych w usłudze Microsoft Intune](../protect/derived-credentials.md).
        - **Certyfikaty**: Wybierz istniejący profil certyfikatu PKCS lub SCEP, który jest używany do podpisywania wiadomości e-mail.
      - **Zezwalaj użytkownikowi na zmianę ustawienia**: Opcja **Włącz** umożliwia użytkownikom zmianę certyfikatu szyfrowania. Wybranie opcji **Wyłącz** (domyślnej) uniemożliwia użytkownikom zmienianie certyfikatu szyfrowania i wymusza na użytkownikach stosowanie certyfikatu skonfigurowanego przez Ciebie.

        Ta funkcja ma zastosowanie do:  
        - iOS 12 i nowsze wersje
        - iPadOS 12 i nowsze wersje

- **Liczba wiadomości e-mail do synchronizacji**: Wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail. Możesz też wybrać pozycję **Nieograniczone**, aby zsynchronizować wszystkie dostępne wiadomości e-mail.
- **Zezwalaj na przenoszenie wiadomości na inne konta e-mail**: Opcja **Włącz** (wartość domyślna) zezwala użytkownikom na przenoszenie wiadomości e-mail między innymi kontami, które użytkownicy skonfigurowali na swoich urządzeniach.
- **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**: Opcja **Włącz** (wartość domyślna) zezwala użytkownikom na wybranie tego profilu jako domyślnego konta do wysyłania poczty e-mail. Umożliwia to aplikacjom innych firm otwieranie wiadomości e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.
- **Synchronizuj ostatnio używane adresy e-mail**: Opcja **Włącz** (wartość domyślna) zezwala użytkownikom na synchronizowanie z serwerem listy adresów e-mail, które były ostatnio używane na urządzeniu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](../device-profile-monitor.md).

Skonfiguruj ustawienia poczty e-mail na urządzeniach z systemami [Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md) i [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
