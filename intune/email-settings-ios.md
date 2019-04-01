---
title: Ustawienia poczty e-mail dla urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień poczty e-mail, które możesz skonfigurować i dodać w przypadku urządzeń z systemem iOS w usłudze Microsoft Intune, w tym używanie serwerów programu Exchange i pobieranie atrybutów z usługi Azure Active Directory. Możesz również włączyć protokół SSL, uwierzytelniać użytkowników przy użyciu certyfikatów lub nazwy użytkownika/hasła i synchronizować pocztę e-mail na urządzeniach z systemem iOS za pomocą profilów konfiguracji urządzenia w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/11/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1cf1daf42d1dfcd8dd25304040e868581a056943
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566417"
---
# <a name="email-profile-settings-for-ios-devices-in-intune"></a>Ustawienia profilu poczty e-mail dla urządzeń z systemem iOS w usłudze Intune

W usłudze Microsoft Intune możesz utworzyć i skonfigurować profil poczty e-mail w celu nawiązywania połączenia z serwerem poczty e-mail, wybrać sposób uwierzytelniania użytkowników, użyć szyfrowania S/MIME na potrzeby szyfrowania i nie tylko.

W tym artykule wymieniono i opisano wszystkie ustawienia poczty e-mail dostępne dla urządzeń z systemem iOS. Możesz utworzyć profil konfiguracji urządzenia, aby wypchnąć lub wdrożyć te ustawienia poczty e-mail na urządzeniach z systemem iOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](email-settings-configure.md#create-a-device-profile).

## <a name="email-settings"></a>Ustawienia poczty e-mail

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera programu Exchange.
- **Nazwa konta**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (AAD). Usługa Intune dynamicznie generuje nazwę użytkownika używaną przez ten profil. Dostępne opcje:
  - **Główna nazwa użytkownika**: pobiera nazwę, taką jak `user1` lub `user1@contoso.com`
  - **Podstawowy adres SMTP**: pobiera nazwę w formacie adresu e-mail, takiego jak `user1@contoso.com`
  - **Nazwa konta SAM**: wymaga domeny, takiej jak `domain\user1`.

    Wprowadź też następujące ustawienia:  
    - **Źródło nazwy domeny użytkownika**: wybierz pozycję **AAD** (Azure Active Directory) lub **Niestandardowe**.

      Podczas wybierania pobierania atrybutów z usługi **AAD** wprowadź następujące ustawienia:
      - **Atrybut nazwy domeny użytkownika z usługi AAD**: wybierz pobieranie atrybutu użytkownika **Pełna nazwa domeny** lub **Nazwa NetBIOS**

      Podczas wybierania atrybutów **Niestandardowe** wprowadź następujące ustawienia:
      - **Nazwa domeny niestandardowej do użycia**: wprowadź wartość używaną przez usługę Intune jako nazwa domeny, taką jak `contoso.com` lub `contoso`

- **Atrybut adresu e-mail z usługi AAD**: określ sposób generowania adresu e-mail użytkownika. Wybierz pozycję **Główna nazwa użytkownika** (`user1@contoso.com` lub `user1`), aby użyć pełnej nazwy użytkownika jako adresu e-mail. Wybierz pozycję **Podstawowy adres SMTP** (`user1@contoso.com`), aby użyć podstawowego adresu SMTP do logowania się do programu Exchange.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**. Uwierzytelnianie Azure Multi-Factor Authentication nie jest obsługiwane.
  - W przypadku wybrania pozycji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który jest używany do uwierzytelniania połączenia z programem Exchange.
- **Protokół SSL**: wybierz pozycję **Włącz**, aby użyć protokołu SSL (Secure Sockets Layer) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **Protokół OAuth**: wybierz pozycję **Włącz**, aby użyć protokołu OAuth (Open Authorization) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z programem Exchange. Jeśli serwer OAuth korzysta z uwierzytelniania przy użyciu certyfikatu, wybierz opcję **Certyfikat** w obszarze **Metoda uwierzytelniania** i dołącz certyfikat do profilu. Możesz też wybrać opcję **Nazwa użytkownika i hasło** w obszarze **Metoda uwierzytelniania**. Jeśli korzystasz z protokołu OAuth, sprawdź następujące elementy:

  - Przed skierowaniem tego profilu do użytkowników upewnij się, że rozwiązanie poczty e-mail obsługuje protokół OAuth. Instalacja usługi Office 365 Exchange Online obsługuje uwierzytelnianie za pomocą protokołu OAuth. Instalacja lokalna programu Exchange i rozwiązania partnerów lub innych firm mogą nie obsługiwać protokołu OAuth. Instalacja lokalna programu Exchange może być skonfigurowana pod kątem obsługi nowoczesnego uwierzytelniania — zobacz wpis na blogu [Announcing Hybrid Modern Authentication for Exchange On-Premises](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) (Ogłoszenie hybrydowego nowoczesnego uwierzytelniania dla lokalnej instalacji programu Exchange).

    Jeśli profil poczty e-mail korzysta z uwierzytelniania Oauth, a usługa poczty e-mail go nie obsługuje, opcja **Wprowadź ponownie hasło** będzie wydawała się uszkodzona. Na przykład gdy użytkownik wybierze opcję **Wprowadź ponownie hasło** w ustawieniach urządzenia firmy Apple, nic się nie stanie.

  - Po włączeniu uwierzytelniania OAuth użytkownicy końcowi będą korzystać z innego środowiska logowania do konta e-mail z „nowoczesnym uwierzytelnianiem”, które obsługuje uwierzytelnianie wieloskładnikowe (MFA). 

  - W niektórych organizacjach użytkownicy końcowi nie mają możliwości skorzystania z [dostępu samoobsługowego do aplikacji](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). W tym scenariuszu logowanie za pomocą nowoczesnego uwierzytelniania może zakończyć się niepowodzeniem, jeśli administrator nie utworzy aplikacji firmowej „Konta systemu iOS” i nie przydzieli użytkownikom dostępu do aplikacji w usłudze Azure AD.

    Domyślną czynnością jest dodanie aplikacji przy użyciu funkcji **Dodaj aplikację** w [panelu dostępu do aplikacji](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **bez zatwierdzenia firmy**. Aby uzyskać więcej informacji, zobacz [Assign users to applications (Przypisywanie użytkowników do aplikacji)](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Włączenie uwierzytelniania OAuth będzie miało następujące skutki:  
  > 1. Urządzeniom, które są już wybrane jako docelowe, zostaną przypisane nowe profile.
  > 2. Użytkownikom końcowym wyświetli się monit o ponowne wprowadzenie swoich poświadczeń.

- **S/MIME**: **włącz protokół S/MIME**, aby zezwolić użytkownikom na podpisywanie i/lub szyfrowanie wiadomości e-mail w natywnej aplikacji pocztowej systemu iOS. 

  Gdy używasz protokołu S/MIME w wiadomościach e-mail, potwierdzasz autentyczność nadawcy oraz integralność i poufność wiadomości.

  - **Włączone podpisywanie S/MIME**: wybierz opcję **Włącz**, aby umożliwić użytkownikom cyfrowe podpisywanie wychodzących wiadomości e-mail dla podanego konta. Dzięki podpisywaniu użytkownicy odbierający wiadomości mogą być pewni, że wiadomość pochodzi od określonego nadawcy, a nie od kogoś, kto udaje, że jest tym nadawcą. Wybranie opcji **Wyłącz** powoduje, że użytkownicy nie mogą cyfrowo podpisywać wiadomości.
    - **Zezwalaj użytkownikom na zmianę ustawienia**: Wybierz **Włącz** umożliwia użytkownikom zmianę zachowania podpisywania S/MIME. Wybranie opcji **Wyłącz** uniemożliwia użytkownikom zmienianie skonfigurowanego ustawienia podpisywania S/MIME. Dostępne w systemie iOS 12 lub nowszym.

  - **Certyfikat podpisywania S/MIME**: wybierz istniejący profil certyfikatu PKCS lub SCEP, który jest używany do podpisywania wiadomości e-mail.
    - **Zezwalaj użytkownikom na zmianę ustawienia**: Wybierz **Włącz** umożliwia użytkownikom zmianę certyfikatu podpisywania. Wybranie opcji **Wyłącz** uniemożliwia użytkownikom zmienianie certyfikatu podpisywania i wymusza na użytkownikach stosowanie skonfigurowanego przez Ciebie certyfikatu. Dostępne w systemie iOS 12 lub nowszym.

  - **Szyfruj domyślnie**: **Włącz** szyfruje wszystkie wiadomości jako zachowanie domyślne. Wybranie opcji **Wyłącz** powoduje, że szyfrowanie wiadomości nie jest zachowaniem domyślnym.
    - **Zezwalaj użytkownikom na zmianę ustawienia**: Wybierz **Włącz** aby użytkownicy mogli zmienić domyślne zachowanie szyfrowania. Wybranie opcji **Wyłącz** uniemożliwia użytkownikom zmienianie domyślnego zachowania szyfrowania i wymusza na użytkownikach stosowanie skonfigurowanego przez Ciebie ustawienia. Dostępne w systemie iOS 12 lub nowszym.

  - **Wymuś szyfrowanie poszczególnych wiadomości**: funkcja szyfrowania poszczególnych wiadomości umożliwia użytkownikom wybranie, które wiadomości e-mail mają być szyfrowane przed wysłaniem. Wybierz opcję **Włącz**, aby wyświetlić opcję szyfrowania poszczególnych wiadomości podczas tworzenia nowej wiadomości e-mail. Dzięki temu użytkownicy mogą wybrać opcję zaszyfrowania wiadomości lub z niej zrezygnować. Wybranie opcji **Wyłącz** powoduje, że opcja szyfrowania poszczególnych wiadomości nie jest widoczna.

    Jeśli ustawienie **Szyfruj domyślnie** jest włączone, włączenie szyfrowania poszczególnych wiadomości umożliwia użytkownikom zrezygnowanie z szyfrowania pojedynczych wiadomości. Jeśli ustawienie **Szyfruj domyślnie** jest wyłączone, włączenie szyfrowania poszczególnych wiadomości umożliwia użytkownikom wybranie szyfrowania pojedynczych wiadomości.

  - **Certyfikat szyfrowania S/MIME**: wybierz istniejący profil certyfikatu PKCS lub SCEP, który jest używany do szyfrowania wiadomości e-mail.
    - **Zezwalaj użytkownikom na zmianę ustawienia**: Wybierz **Włącz** umożliwia użytkownikom zmianę certyfikatu szyfrowania. Wybranie opcji **Wyłącz** uniemożliwia użytkownikom zmienianie certyfikatu szyfrowania i wymusza na użytkownikach stosowanie skonfigurowanego przez Ciebie certyfikatu. Dostępne w systemie iOS 12 lub nowszym.
- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail. Możesz też wybrać pozycję **Nieograniczone**, aby zsynchronizować wszystkie dostępne wiadomości e-mail.
- **Zezwalaj na przenoszenie wiadomości na inne konta poczty e-mail**: wybierz pozycję **Włącz**, aby umożliwić użytkownikom przenoszenie wiadomości e-mail między różnymi kontami skonfigurowanymi na ich urządzeniu.
- **Zezwalaj na wysyłanie wiadomości e-mail przy użyciu aplikacji innych firm**: wybierz pozycję **Włącz**, aby zezwalać użytkownikowi na wybranie jego profilu jako domyślnego konta do wysyłania poczty e-mail. Umożliwia to aplikacjom innych firm otwieranie wiadomości e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.
- **Synchronizuj ostatnio używane adresy e-mail**: wybierz pozycję **Włącz**, aby zezwalać użytkownikom na synchronizowanie z serwerem listy adresów e-mail, które były ostatnio używane na urządzeniu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Konfigurowanie ustawień poczty e-mail na urządzeniach z systemami [Android](email-settings-android.md), [Windows 10](email-settings-windows-10.md) i [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
