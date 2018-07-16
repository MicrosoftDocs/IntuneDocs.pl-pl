---
title: Ustawienia poczty e-mail dla urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz profil konfiguracji poczty e-mail urządzenia, który korzysta z serwerów programu Exchange i pobiera atrybuty z usługi Azure Active Directory. Możesz również włączyć protokół SSL, uwierzytelniać użytkowników przy użyciu certyfikatów lub nazwy użytkownika/hasła i synchronizować pocztę e-mail w urządzeniach z systemem iOS za pomocą usługi Microsoft Intune.
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
ms.custom: intune-azure
ms.openlocfilehash: 3a231adf4e1f5687bc88c8c9b15241d3f89e711d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905343"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>Ustawienia profilu poczty e-mail dla urządzeń z systemem iOS — Intune

Ustawienia profilu poczty e-mail umożliwiają skonfigurowanie urządzeń z systemem iOS.

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

- **Atrybut adresu e-mail z usługi AAD**: określ sposób generowania adresu e-mail użytkownika. Wybierz pozycję **Główna nazwa użytkownika** (`user1@contoso.com` lub `user1`), aby użyć pełnej głównej nazwy jako adresu e-mail, lub wybierz pozycję **Podstawowy adres SMTP** (`user1@contoso.com`), aby użyć podstawowego adresu SMTP do logowania do programu Exchange.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**. Uwierzytelnianie Azure Multi-Factor Authentication nie jest obsługiwane.
  - W przypadku wybrania pozycji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który jest używany do uwierzytelniania połączenia z programem Exchange.
- **Protokół SSL**: użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **S/MIME**: wysyłaj wychodzącą pocztę e-mail przy użyciu podpisywania S/MIME.
  - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu PKCS, który będzie używany do uwierzytelniania połączenia z programem Exchange.
- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail. Możesz też wybrać pozycję **Nieograniczone**, aby zsynchronizować wszystkie dostępne wiadomości e-mail.
- **Zezwalaj na przenoszenie wiadomości na inne konta poczty e-mail**: umożliwia użytkownikom przenoszenie wiadomości e-mail między różnymi kontami skonfigurowanymi na ich urządzeniu.
- **Zezwalaj na wysyłanie wiadomości e-mail przy użyciu aplikacji innych firm**: zezwalaj użytkownikowi na wybranie jego profilu jako domyślnego konta wysyłania poczty e-mail i zezwalaj aplikacjom innych firm na otwieranie poczty e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.
- **Synchronizuj ostatnio używane adresy e-mail**: pozwala użytkownikom zsynchronizować listę adresów e-mail, które były ostatnio używane na urządzeniu, z serwerem.

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)
