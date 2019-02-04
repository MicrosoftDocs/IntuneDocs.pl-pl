---
title: Ustawienia poczty e-mail systemu Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Twórz profile konfiguracji poczty e-mail urządzeń, które korzystają z serwerów programu Exchange i pobierają atrybuty z usługi Azure Active Directory. Włącz protokół SSL lub S/MIME, uwierzytelniaj użytkowników przy użyciu certyfikatów lub nazwy użytkownika i hasła oraz synchronizuj pocztę e-mail i harmonogramy na urządzeniach z systemem Android Samsung Knox za pomocą usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 4336be8d24ac4a81ec6fca09f22d594000bbd9a5
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831395"
---
# <a name="android-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Ustawienia urządzeń z systemem Android do konfigurowania poczty e-mail, uwierzytelniania i synchronizacji w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia poczty e-mail, którymi można sterować na urządzeniach z systemem Android Samsung Knox w usłudze Intune. W ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM) możesz skorzystać z tych ustawień, aby skonfigurować serwer poczty e-mail lub użyć protokołu SSL do szyfrowania wiadomości e-mail oraz określić inne elementy.

Jako administrator usługi Intune możesz utworzyć i przypisać ustawienia poczty e-mail do urządzeń z systemem Android Samsung Knox Standard.

Aby dowiedzieć się więcej na temat profilów poczty e-mail w usłudze Intune, zobacz temat [Konfigurowanie ustawień poczty e-mail](email-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](email-settings-configure.md#create-a-device-profile).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera Exchange. Na przykład wprowadź `outlook.office365.com`.
- **Nazwa konta**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (Azure AD). Usługa Intune dynamicznie generuje nazwę użytkownika używaną przez ten profil. Dostępne opcje:
  - **Nazwa główna użytkownika**: pobiera nazwę, taką jak `user1` lub `user1@contoso.com`
  - **Nazwa użytkownika**: pobiera tylko nazwę, taką jak `user1`
  - **Nazwa konta sAM**: wymaga domeny, takiej jak `domain\user1`. Nazwa konta sAM jest używana tylko z urządzeniami z systemem Android.

    Wprowadź też następujące ustawienia:  
    - **Źródło nazwy domeny użytkownika**: wybierz pozycję **AAD** (Azure Active Directory) lub **Niestandardowe**.

      Podczas wybierania pobierania atrybutów z usługi **AAD** wprowadź następujące ustawienia:
      - **Atrybut nazwy domeny użytkownika z usługi AAD**: wybierz pobieranie atrybutu użytkownika **Pełna nazwa domeny** lub **Nazwa NetBIOS**

      Podczas wybierania atrybutów **Niestandardowe** wprowadź następujące ustawienia:
      - **Nazwa domeny niestandardowej do użycia**: wprowadź wartość używaną przez usługę Intune jako nazwa domeny, taką jak `contoso.com` lub `contoso`

- **Atrybut adresu e-mail z usługi AAD**: ta nazwa to atrybut adresu e-mail pobierany przez usługę Intune z usługi Azure AD. Usługa Intune dynamicznie generuje adres e-mail używany przez ten profil. Dostępne opcje:
  - **Główna nazwa użytkownika**:  używa pełnej nazwy głównej, takiej jak `user1@contoso.com` lub `user1`, jako adresu e-mail.
  - **Podstawowy adres SMTP**: używa podstawowego adresu SMTP, takiego jak `user1@contoso.com`, do logowania się do programu Exchange.

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

- **Typ zawartości do synchronizowania**: Wybierz typy zawartości, które chcesz synchronizować na urządzeniach. Wartość **Nieskonfigurowane** wyłącza to ustawienie. Jeśli w przypadku ustawienia wartości **Nieskonfigurowane** użytkownik końcowy włączy synchronizację na urządzeniu, to synchronizacja zostanie ponownie wyłączona podczas synchronizacji urządzenia z usługą Intune, ponieważ zasady zostały wzmocnione. 

  Można synchronizować następującą zawartość:  
  - **Kontakty**: wybierz pozycję **Włącz**, aby zezwolić użytkownikom końcowym na synchronizowanie kontaktów z urządzeniami.
  - **Kalendarz**: wybierz pozycję **Włącz**, aby zezwolić użytkownikom końcowym na synchronizowanie kalendarza z urządzeniami.
  - **Zadania**: wybierz pozycję **Włącz**, aby zezwolić użytkownikom końcowym na synchronizowanie dowolnych zadań z urządzeniami.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile poczty e-mail dla [profilu służbowego w systemie Android Enterprise](email-settings-android-enterprise.md) oraz systemów [iOS](email-settings-ios.md), [Windows 10 i nowszych](email-settings-windows-10.md) i [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
