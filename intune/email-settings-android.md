---
title: Ustawienia poczty e-mail dla urządzeń z systemem Android i profilami służbowymi systemu Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz profil konfiguracji poczty e-mail urządzenia, który korzysta z serwerów programu Exchange i pobiera atrybuty z usługi Azure Active Directory. Możesz również włączyć protokół SSL lub SMIME, uwierzytelniać użytkowników przy użyciu certyfikatów lub nazwy użytkownika/hasła oraz synchronizować pocztę e-mail i harmonogramy w urządzeniach z systemem Android i profilami służbowymi systemu Android za pomocą usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b8ab8dfadb113d81922119a54aefcac43d15b5a1
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187433"
---
# <a name="email-profile-settings-for-devices-running-android-and-android-enterprise---intune"></a>Ustawienia profilu poczty e-mail dla urządzeń z systemem Android i rozwiązaniem Android Enterprise — Intune

Ustawienia profilu poczty e-mail umożliwiają skonfigurowanie urządzeń z systemem Android.

Jako administrator usługi Intune możesz utworzyć i przypisać ustawienia poczty e-mail do następujących urządzeń z systemem Android:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera programu Exchange.
- **Nazwa konta**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (AAD). Usługa Intune dynamicznie generuje nazwę użytkownika używaną przez ten profil. Dostępne opcje:
  - **Główna nazwa użytkownika**: pobiera nazwę, taką jak `user1` lub `user1@contoso.com`
  - **Nazwa użytkownika**: pobiera tylko nazwę, taką jak `user1`
  - **Nazwa konta SAM**: wymaga domeny, takiej jak `domain\user1`. Nazwy konta SAM można używać tylko z urządzeniami z systemem Android. Rozwiązanie Android Enterprise nie jest obsługiwane.

    Wprowadź też następujące ustawienia:  
    - **Źródło nazwy domeny użytkownika**: wybierz pozycję **AAD** (Azure Active Directory) lub **Niestandardowe**.

      Podczas wybierania pobierania atrybutów z usługi **AAD** wprowadź następujące ustawienia:
      - **Atrybut nazwy domeny użytkownika z usługi AAD**: wybierz pobieranie atrybutu użytkownika **Pełna nazwa domeny** lub **Nazwa NetBIOS**

      Podczas wybierania atrybutów **Niestandardowe** wprowadź następujące ustawienia:
      - **Nazwa domeny niestandardowej do użycia**: wprowadź wartość używaną przez usługę Intune jako nazwa domeny, taką jak `contoso.com` lub `contoso`

- **Atrybut adresu e-mail z usługi AAD**: określ sposób generowania adresu e-mail użytkownika. Wybierz pozycję **Główna nazwa użytkownika** (`user1@contoso.com` lub `user1`), aby użyć pełnej głównej nazwy jako adresu e-mail, lub wybierz pozycję **Podstawowy adres SMTP** (`user1@contoso.com`), aby użyć podstawowego adresu SMTP do logowania do programu Exchange.

- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

### <a name="security-settings"></a>Ustawienia zabezpieczeń

- **Protokół SSL**: użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **S/MIME**: umożliwia wysyłanie wychodzącej poczty e-mail przy użyciu szyfrowania S/MIME.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

### <a name="synchronization-settings"></a>Ustawienia synchronizacji

- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Harmonogram synchronizacji**: wybierz harmonogram, według którego urządzenia będą synchronizować dane z serwera programu Exchange. Możesz również wybrać opcję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie danych zaraz po odebraniu, lub opcję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.

### <a name="content-sync-settings"></a>Ustawienia synchronizacji zawartości

- **Typ zawartości do zsynchronizowania**: wybierz typ zawartości, który chcesz zsynchronizować z urządzeniami:
  - **Kontakty**
  - **Kalendarz**
  - **Zadania**

## <a name="android-enterprise"></a>Android Enterprise

- **Aplikacja poczty e-mail**: wybierz pozycję **Gmail** lub **Nine Work**
- **Serwer poczty e-mail**: nazwa hosta serwera programu Exchange.
- **Atrybut nazwy użytkownika z usługi AAD**: jest to atrybut usługi Active Directory (AD) lub Azure AD używany do generowania nazwy użytkownika dla danego profilu e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład user1@contoso.com, lub **Główna nazwa użytkownika**, na przykład użytkownik1 lub user1@contoso.com.
- **Atrybut adresu e-mail z usługi AAD**: określa, jak adres e-mail użytkownika jest generowany na poszczególnych urządzeniach. Wybierz opcję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail, lub opcję **Nazwa użytkownika**.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.
- **Protokół SSL**: użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Typ zawartości do zsynchronizowania** (tylko Nine Work): wybierz typy zawartości, które chcesz zsynchronizować z urządzeniem:
  - **Kontakty**
  - **Kalendarz**
  - **Zadania**

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)
