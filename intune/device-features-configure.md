---
title: Tworzenie profilu urządzenia z systemem iOS lub macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil urządzenia z systemem iOS lub macOS, a następnie skonfiguruj ustawienia funkcji AirPrint i AirPlay, układu ekranu głównego, powiadomień aplikacji, urządzenia udostępnionego, logowania jednokrotnego i filtru zawartości internetowej w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 291ad9cb8b07893f538171c365110618ea376388
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/20/2018
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Dodawanie ustawień funkcji urządzenia z systemem iOS lub macOS w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkcje urządzenia umożliwiają sterowanie różnymi ustawieniami i funkcjami na urządzeniach z systemem iOS i macOS, takimi jak:

- Ustawienia funkcji AirPrint i AirPlay
- Układ ekranu głównego
- Powiadomienia z aplikacji
- Konfiguracja urządzenia udostępnianego
- Konfigurowanie logowania jednokrotnego
- Filtrowanie zawartości internetowej

W tym artykule przedstawiono podstawowe informacje na temat konfigurowania profilów funkcji urządzeń z systemem iOS. Następnie możesz przejrzeć dodatkowe artykuły, aby skonfigurować ustawienia specyficzne dla platformy na urządzeniach.

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Wprowadź następujące właściwości:

   - **Nazwa**: wprowadź opisową nazwę nowego profilu.
   - **Opis:** wprowadź opis profilu. (Jest to opcjonalne, ale zalecane).
   - **Platforma**: wybierz typ platformy:
     - **iOS**
     - **macOS**
   - **Typ profilu**: wybierz pozycję **Funkcje urządzenia**.
   - **Ustawienia**: ustawienia zależą od wybranej platformy. Ustawienia poszczególnych typów profilów opisano w następujących artykułach:

     - [Ustawienia funkcji AirPrint dla urządzeń z systemami iOS i MacOS](air-print-settings-ios-macos.md)
     - [Ustawienia funkcji AirPlay dla urządzeń z systemem iOS](airplay-settings-ios.md)
     - [Ustawienia układu ekranu głównego dla urządzeń z systemem iOS](home-screen-settings-ios.md)
     - [Ustawienia powiadomień aplikacji dla urządzeń z systemem iOS](app-notification-settings-ios.md)
     - [Ustawienia konfiguracji urządzenia udostępnianego dla urządzeń z systemem iOS](shared-device-settings-ios.md)
     - [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md)
     - [Ustawienia filtru zawartości sieci Web dla urządzeń z systemem iOS](web-content-filter-settings-ios.md)

5. Gdy wszystko będzie gotowe, wybierz przycisk **OK** i wybierz pozycję **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście.

## <a name="next-step"></a>Następny krok

Aby przypisać ten profil do grup, zobacz [Jak przypisywać profile urządzeń](device-profile-assign.md).