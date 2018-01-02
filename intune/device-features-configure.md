---
title: "Konfigurowanie ustawień funkcji urządzenia w usłudze Intune"
titleSuffix: Azure portal
description: "Informacje dotyczące konfigurowania funkcji na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ea280ac6858485aa4e3d64d11835f002c5bb35ca
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia funkcji urządzeń w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ograniczenia urządzenia pozwalają sterować funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i konfiguracje udostępnianych urządzeń.

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów funkcji urządzeń, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia ograniczeń dotyczących urządzeń

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu funkcji urządzenia.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia. Obecnie dla funkcji urządzenia można wybrać jedną z następujących platform:
    - **iOS**
    - **macOS**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Funkcje urządzenia**. 
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia funkcji AirPrint dla urządzeń z systemami iOS i MacOS](air-print-settings-ios-macos.md)
    - [Ustawienia funkcji AirPlay dla urządzeń z systemem iOS](airplay-settings-ios.md)
    - [Ustawienia układu ekranu głównego dla urządzeń z systemem iOS](home-screen-settings-ios.md)
    - [Ustawienia powiadomień aplikacji dla urządzeń z systemem iOS](app-notification-settings-ios.md)
    - [Ustawienia konfiguracji urządzenia udostępnianego dla urządzeń z systemem iOS](shared-device-settings-ios.md)
    - [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md)
    - [Ustawienia filtru zawartości sieci Web dla urządzeń z systemem iOS](web-content-filter-settings-ios.md)

8. Gdy skończysz, wróć do bloku **Utwórz profil** i kliknij pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).



