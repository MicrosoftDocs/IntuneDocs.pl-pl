---
title: "Konfigurowanie ustawień funkcji urządzenia w usłudze Microsoft Intune"
titleSuffix: 
description: "Informacje dotyczące konfigurowania funkcji na zarządzanych urządzeniach przy użyciu usługi Microsoft Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Konfigurowanie ustawień funkcji urządzeń w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkcje urządzenia pozwalają sterować funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i udostępniane konfiguracje urządzeń.

Skorzystaj z informacji zawartych w tym artykule, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów funkcji urządzeń, a następnie zapoznaj się z artykułami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia funkcji dotyczących urządzeń

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. Na stronie **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. Na stronie **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz opcję **Profile**.
3. Na stronie profilów wybierz pozycję **Utwórz profil**.
4. Na stronie **Tworzenie profilu** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu funkcji urządzenia.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia. Obecnie dla funkcji urządzenia można wybrać jedną z następujących platform:
    - **iOS**
    - **macOS**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Funkcje urządzenia**. 
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących artykułach:
    - [Ustawienia funkcji AirPrint dla urządzeń z systemami iOS i MacOS](air-print-settings-ios-macos.md)
    - [Ustawienia funkcji AirPlay dla urządzeń z systemem iOS](airplay-settings-ios.md)
    - [Ustawienia układu ekranu głównego dla urządzeń z systemem iOS](home-screen-settings-ios.md)
    - [Ustawienia powiadomień aplikacji dla urządzeń z systemem iOS](app-notification-settings-ios.md)
    - [Ustawienia konfiguracji urządzenia udostępnianego dla urządzeń z systemem iOS](shared-device-settings-ios.md)
    - [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md)
    - [Ustawienia filtru zawartości sieci Web dla urządzeń z systemem iOS](web-content-filter-settings-ios.md)

8. Gdy skończysz, wybierz opcję **OK**, wróć do strony **Tworzenie profilu** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na stronie listy profilów.
## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [Jak przypisywać profile urządzeń](device-profile-assign.md).



