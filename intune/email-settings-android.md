---
title: Ustawienia poczty e-mail usługi Microsoft Intune na urządzeniach z systemem Android i programem Android for Work
titleSuffix: ''
description: Dowiedz się więcej o ustawieniach usługi Microsoft Intune, których możesz użyć do konfigurowania ustawień poczty e-mail na urządzeniach z systemem Android i programem Android for Work.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d492e107fffe730d36c662b9187fc9c6faced907
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Ustawienia profilu poczty e-mail w usłudze Microsoft Intune na urządzeniach z systemem Android i programem Android for Work

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia profilu poczty e-mail, które możesz skonfigurować dla urządzeń z systemem Android.

Jako administrator usługi Intune możesz utworzyć i przypisać ustawienia poczty e-mail do następujących urządzeń z systemem Android:
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Ustawienia poczty e-mail w systemie Android Samsung Knox Standard
- **Serwer poczty e-mail** — nazwa hosta serwera programu Exchange.
- **Nazwa konta** — nazwa wyświetlana dla konta e-mail, jaka będzie wyświetlana użytkownikom na ich urządzeniach.
- **Atrybut Nazwa użytkownika z usługi AAD** — jest to atrybut usługi Active Directory (AD) lub Azure AD używany do generowania nazwy użytkownika dla danego profilu e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład user1@contoso.com, lub **Główna nazwa użytkownika**, na przykład użytkownik1 lub user1@contoso.com.
- **Atrybut adresu e-mail z usługi AAD** — określa, jak adres e-mail użytkownika jest generowany na poszczególnych urządzeniach. Wybierz opcję **Podstawowy adres SMTP**, aby użyć podstawowego adresu SMTP do logowania do programu Exchange, lub wybierz opcję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
    - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

### <a name="security-settings"></a>Ustawienia zabezpieczeń

- **Protokół SSL** — użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i otrzymywania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **S/MIME** — umożliwia wysyłanie wychodzącej poczty e-mail przy użyciu szyfrowania S/MIME.
    - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

### <a name="synchronization-settings"></a>Ustawienia synchronizacji

- **Liczba wiadomości e-mail do synchronizacji** — wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Harmonogram synchronizacji** — wybierz harmonogram, według którego urządzenia będą synchronizować dane z serwera programu Exchange. Możesz również wybrać opcję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie danych zaraz po odebraniu, lub opcję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.

### <a name="content-sync-settings"></a>Ustawienia synchronizacji zawartości

- **Typ zawartości do zsynchronizowania** — wybierz typ zawartości, który chcesz zsynchronizować z urządzeniem:
    - **Kontakty**
    - **Kalendarz**
    - **Zadania**

## <a name="android-for-work-email-settings"></a>Ustawienia poczty e-mail w usłudze Android for Work

- **Aplikacja poczty e-mail** — wybierz opcję **Gmail** lub **Nine Work**
- **Serwer poczty e-mail** — nazwa hosta serwera programu Exchange.
- **Atrybut Nazwa użytkownika z usługi AAD** — jest to atrybut usługi Active Directory (AD) lub Azure AD używany do generowania nazwy użytkownika dla danego profilu e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład user1@contoso.com, lub **Główna nazwa użytkownika**, na przykład użytkownik1 lub user1@contoso.com.
- **Atrybut adresu e-mail z usługi AAD** — określa, jak adres e-mail użytkownika jest generowany na poszczególnych urządzeniach. Wybierz opcję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail, lub opcję **Nazwa użytkownika**.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
    - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.
- **Protokół SSL** — użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i otrzymywania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **Liczba wiadomości e-mail do synchronizacji** — wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Typ zawartości do zsynchronizowania** (tylko Nine Work) — wybierz typy zawartości, które chcesz zsynchronizować z urządzeniem:
    - **Kontakty**
    - **Kalendarz**
    - **Zadania**
