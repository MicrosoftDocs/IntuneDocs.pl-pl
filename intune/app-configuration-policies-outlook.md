---
title: Ustawienia programu Outlook dla urządzeń z systemami iOS i Android w programie Microsoft Intune
description: Utwórz zasady konfiguracji, aby określić ustawienia programu Microsoft Outlook uruchomionego na urządzeniach z systemami iOS i Android.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 691029cc7b9fd8880c5440a84b95bbf2462920d6
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180327"
---
# <a name="microsoft-outlook-configuration-settings"></a>Ustawienia konfiguracji programu Microsoft Outlook 

Skorzystaj z zasad konfiguracji, aby określić ustawienia programu Microsoft Outlook uruchomionego na urządzeniach z systemami iOS i Android. 

Aby utworzyć zasady konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md). Aby utworzyć zasady konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Ustawienia konfiguracji

Podczas dodawania zasad konfiguracji w usłudze Intune możesz wprowadzić określone ustawienia, aby skonfigurować program Microsoft Outlook. W okienku **Ustawienia konfiguracji** możesz określić konfigurację konta poczty e-mail.

### <a name="basic-authentication-email-account-settings"></a>Ustawienia konta e-mail w przypadku uwierzytelniania podstawowego
Program Outlook dla systemów iOS i Android umożliwia administratorom programu Exchange „wypychanie” konfiguracji kont do ich lokalnych użytkowników, którzy korzystają z uwierzytelniania podstawowego przy użyciu protokołu ActiveSync. Aby uzyskać więcej informacji, zobacz [Account setup in Outlook for iOS and Android using Basic authentication](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup) (Konfiguracja kont w programie Outlook dla systemów iOS i Android przy użyciu uwierzytelniania podstawowego). Aby włączyć konfigurację konta, można skonfigurować następujące ustawienia:

- **Serwer poczty e-mail**: wprowadź nazwę hosta serwera programu Exchange w środowisku lokalnym (np. mail.contoso.com).
- **Nazwa konta e-mail**: wprowadź nazwę wyświetlaną konta e-mail. Ta nazwa jest widoczna na urządzeniach użytkowników.
- **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (Azure AD). Usługa Intune dynamicznie generuje nazwę użytkownika używaną przez ten profil. Dostępne opcje:
  - **Główna nazwa użytkownika**: pobiera nazwę, taką jak `user1` lub `user1@contoso.com`
  - **Podstawowy adres SMTP**: pobiera nazwę w formacie adresu e-mail, takiego jak `user1@contoso.com`
- **Atrybut adresu e-mail z usługi AAD**: określ sposób generowania adresu e-mail użytkownika. Wybierz pozycję **Główna nazwa użytkownika** (`user1@contoso.com` lub `user1`), aby użyć pełnej głównej nazwy jako adresu e-mail, lub wybierz pozycję **Podstawowy adres SMTP** (`user1@contoso.com`), aby użyć podstawowego adresu SMTP do logowania do programu Exchange. Zalecane jest wybranie pozycji **Podstawowy adres SMTP**.
- **Domena konta**: (opcjonalnie) domena konta.

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień poczty e-mail w usłudze Intune](email-settings-configure.md)

