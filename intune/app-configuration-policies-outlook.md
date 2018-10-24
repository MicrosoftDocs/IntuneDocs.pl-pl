---
title: Ustawienia programu Outlook dla urządzeń z systemami iOS i Android w programie Microsoft Intune
description: Utwórz zasady konfiguracji, aby określić ustawienia programu Microsoft Outlook uruchomionego na urządzeniach z systemami iOS i Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7fc9f34bbd3d14ac4291582247b1e45169c2cccc
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828935"
---
# <a name="microsoft-outlook-configuration-settings"></a>Ustawienia konfiguracji programu Microsoft Outlook 

Skorzystaj z zasad konfiguracji, aby określić ustawienia programu Microsoft Outlook uruchomionego na urządzeniach z systemami iOS i Android. 

Aby utworzyć zasady konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md). Aby utworzyć zasady konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Ustawienia konfiguracji

Podczas dodawania zasad konfiguracji w usłudze Intune możesz wprowadzić określone ustawienia, aby skonfigurować program Microsoft Outlook. W okienku **Ustawienia konfiguracji** możesz określić konfigurację konta poczty e-mail.

### <a name="email-account-settings"></a>Ustawienia konta e-mail

Poniższe ustawienia konfiguracji są specyficzne dla programu Microsoft Outlook.

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera programu Exchange.
- **Nazwa konta e-mail**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
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
- **Domena konta**: (opcjonalnie) domena konta.

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)

