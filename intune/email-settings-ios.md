---
title: Ustawienia poczty e-mail dla urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz profil konfiguracji poczty e-mail urządzenia, który korzysta z serwerów programu Exchange i pobiera atrybuty z usługi Azure Active Directory. Możesz również włączyć protokół SSL, uwierzytelniać użytkowników przy użyciu certyfikatów lub nazwy użytkownika/hasła i synchronizować pocztę e-mail w urządzeniach z systemem iOS za pomocą usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b3aa3e7a4cd79ab990afe7f02a1d6960bc66494a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180191"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>Ustawienia profilu poczty e-mail dla urządzeń z systemem iOS — Intune

Ustawienia profilu poczty e-mail umożliwiają skonfigurowanie urządzeń z systemem iOS.

> [!IMPORTANT]
> Wprowadzamy ulepszenia funkcji szyfrowania S/MIME opisanej w tym artykule. W wyniku funkcja szyfrowania S/MIME jest tymczasowo usuwana w usłudze Intune. Po wydaniu tej funkcji usuniemy tę uwagę.

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

- **S/MIME**: wybierz pozycję **Włącz protokół S/MIME**, aby wysyłać wychodzącą pocztę e-mail przy użyciu podpisywania S/MIME. Po włączeniu można również zaszyfrować wiadomości e-mail do adresatów, którzy mogą odbierać zaszyfrowane wiadomości e-mail i odszyfrować wiadomości e-mail odbierane od nadawców.
  - Jeśli wybierzesz opcję **Certyfikat**, wybierz istniejący profil certyfikatu PKCS do uwierzytelniania połączenia z programem Exchange lub szyfrowania wymiany wiadomości e-mail.
- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail. Możesz też wybrać pozycję **Nieograniczone**, aby zsynchronizować wszystkie dostępne wiadomości e-mail.
- **Zezwalaj na przenoszenie wiadomości na inne konta poczty e-mail**: wybierz pozycję **Włącz**, aby umożliwić użytkownikom przenoszenie wiadomości e-mail między różnymi kontami skonfigurowanymi na ich urządzeniu.
- **Zezwalaj na wysyłanie wiadomości e-mail przy użyciu aplikacji innych firm**: wybierz pozycję **Włącz**, aby zezwalać użytkownikowi na wybranie jego profilu jako domyślnego konta do wysyłania poczty e-mail. Umożliwia to aplikacjom innych firm otwieranie wiadomości e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.
- **Synchronizuj ostatnio używane adresy e-mail**: wybierz pozycję **Włącz**, aby zezwalać użytkownikom na synchronizowanie z serwerem listy adresów e-mail, które były ostatnio używane na urządzeniu.

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)
