---
title: Ustawienia poczty e-mail dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz profil konfiguracji poczty e-mail urządzenia, który korzysta z serwerów programu Exchange i pobiera atrybuty z usługi Azure Active Directory. Możesz również włączyć protokół SSL i synchronizować pocztę e-mail oraz harmonogramy na urządzeniach z systemem Windows 10 za pomocą usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e2b3708b6b0c75a1384a7cdbdb524dff3f0627d
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565438"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>Ustawienia profilu poczty e-mail dla urządzeń z systemem Windows 10 — Intune

Ustawienia profilu poczty e-mail umożliwiają skonfigurowanie aplikacji Poczta na urządzeniach z systemem Windows 10.

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

## <a name="security-settings"></a>Ustawienia zabezpieczeń

- **Protokół SSL**: użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i odbierania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.

## <a name="synchronization-settings"></a>Ustawienia synchronizacji

- **Liczba wiadomości e-mail do synchronizacji**: wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail. Możesz też wybrać pozycję **Nieograniczone**, aby zsynchronizować wszystkie dostępne wiadomości e-mail.
- **Harmonogram synchronizacji**: wybierz harmonogram synchronizacji danych urządzeń z serwera programu Exchange. Możesz również wybrać pozycję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie zaraz po odebraniu, lub pozycję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.

## <a name="content-sync-settings"></a>Ustawienia synchronizacji zawartości

- **Typ zawartości do zsynchronizowania**: wybierz typ zawartości, który chcesz zsynchronizować z urządzeniami:
  - **Kontakty**
  - **Kalendarz**
  - **Zadania**

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)
