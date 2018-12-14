---
title: Ustawienia poczty e-mail dla urządzeń z systemem Android i rozwiązaniem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Twórz profile konfiguracji poczty e-mail urządzeń, które korzystają z serwerów programu Exchange i pobierają atrybuty z usługi Azure Active Directory. Włącz protokół SSL lub SMIME, uwierzytelniaj użytkowników przy użyciu certyfikatów lub nazwy użytkownika/hasła oraz synchronizuj pocztę e-mail i harmonogramy w urządzeniach z systemem Android i profilami służbowymi systemu Android za pomocą usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: ffe25f7e4870f2ea6969d1261f33c69362d75469
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032031"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Ustawienia urządzeń z systemem Android lub rozwiązaniem Android Enterprise do konfigurowania poczty e-mail, uwierzytelniania i synchronizacji w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia poczty e-mail, którymi można sterować na urządzeniach z systemem Android i rozwiązaniem Android Enterprise. W ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM) możesz skorzystać z tych ustawień, aby skonfigurować serwer poczty e-mail lub użyć protokołu SSL do szyfrowania wiadomości e-mail oraz określić inne elementy.

Jako administrator usługi Intune możesz utworzyć i przypisać ustawienia poczty e-mail do następujących urządzeń z systemem Android:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera Exchange.
- **Nazwa konta**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (AAD). Usługa Intune dynamicznie generuje nazwę użytkownika używaną przez ten profil. Dostępne opcje:
  - **Nazwa główna użytkownika**: pobiera nazwę, taką jak `user1` lub `user1@contoso.com`
  - **Nazwa użytkownika**: pobiera tylko nazwę, taką jak `user1`
  - **Nazwa konta sAM**: wymaga domeny, takiej jak `domain\user1`. Nazwy konta SAM można używać tylko z urządzeniami z systemem Android. Rozwiązanie Android Enterprise nie jest obsługiwane.

    Wprowadź też następujące ustawienia:  
    - **Źródło nazwy domeny użytkownika**: wybierz pozycję **AAD** (Azure Active Directory) lub **Niestandardowe**.

      Podczas wybierania pobierania atrybutów z usługi **AAD** wprowadź następujące ustawienia:
      - **Atrybut nazwy domeny użytkownika z usługi AAD**: wybierz pobieranie atrybutu użytkownika **Pełna nazwa domeny** lub **Nazwa NetBIOS**

      Podczas wybierania atrybutów **Niestandardowe** wprowadź następujące ustawienia:
      - **Nazwa domeny niestandardowej do użycia**: wprowadź wartość używaną przez usługę Intune jako nazwa domeny, taką jak `contoso.com` lub `contoso`

- **Atrybut adresu e-mail z usługi AAD**: Wybierz sposób generowania adresu e-mail użytkownika. Wybierz pozycję **Główna nazwa użytkownika** (`user1@contoso.com` lub `user1`), aby użyć pełnej głównej nazwy jako adresu e-mail, lub wybierz pozycję **Podstawowy adres SMTP** (`user1@contoso.com`), aby użyć podstawowego adresu SMTP do logowania do programu Exchange.

- **Metoda uwierzytelniania**: Wybierz metodę uwierzytelniania stosowaną w profilu poczty e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

### <a name="security-settings"></a>Ustawienia zabezpieczeń

- **SSL**: Użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania wiadomości e-mail, otrzymywania wiadomości e-mail i komunikacji z serwerem programu Exchange.
- **S/MIME**: Wyślij pocztę wychodzącą przy użyciu szyfrowania S/MIME.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

### <a name="synchronization-settings"></a>Ustawienia synchronizacji

- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni okresu, z którego chcesz synchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Harmonogram synchronizacji**: wybierz harmonogram, według którego urządzenia będą synchronizować dane z serwera programu Exchange. Możesz również wybrać opcję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie danych zaraz po odebraniu, lub opcję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.

### <a name="content-sync-settings"></a>Ustawienia synchronizacji zawartości

- **Typ zawartości do synchronizowania**: wybierz typy zawartości, które chcesz synchronizować z urządzeniami:
  - **Kontakty**
  - **Kalendarz**
  - **Zadania**

## <a name="android-enterprise"></a>Android Enterprise

- **Aplikacja poczty e-mail**: wybierz pozycję **Gmail** lub **Nine Work**
- **Serwer poczty e-mail**: nazwa hosta serwera programu Exchange.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut usługi Active Directory (AD) lub Azure AD, który jest używany do generowania nazwy użytkownika dla tego profilu poczty e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład user1@contoso.com, lub **Główna nazwa użytkownika**, na przykład użytkownik1 lub user1@contoso.com.
- **Atrybut adresu e-mail z usługi AAD**: Wybierz, jak jest generowany adres e-mail użytkownika na poszczególnych urządzeniach. Wybierz opcję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail, lub opcję **Nazwa użytkownika**.
- **Metoda uwierzytelniania**: Wybierz metodę uwierzytelniania stosowaną w profilu poczty e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.
- **SSL**: Użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania wiadomości e-mail, otrzymywania wiadomości e-mail i komunikacji z serwerem programu Exchange.
- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni okresu, z którego chcesz synchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Typ zawartości do synchronizowania** (tylko Nine Work): wybierz typy zawartości, które chcesz synchronizować z urządzeniami:
  - **Kontakty**
  - **Kalendarz**
  - **Zadania**

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)
