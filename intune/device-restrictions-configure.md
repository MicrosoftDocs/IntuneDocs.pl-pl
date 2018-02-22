---
title: "Konfigurowanie ustawień ograniczeń dotyczących urządzeń w usłudze Intune"
titleSuffix: Azure portal
description: "Informacje dotyczące konfigurowania ustawień i funkcji na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 93b6a642f26ec6273853f75d063fd368698f3864
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia ograniczeń dotyczących urządzeń w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ograniczenia dotyczące urządzeń pozwalają na kontrolę szerokiego zakresu ustawień i funkcji, którymi można zarządzać w ramach wielu kategorii, takich jak:
- Zabezpieczenia
- Przeglądarka
- Sprzęt
- Ustawienia związane z udostępnianiem danych

Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia.

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów ograniczeń dotyczących urządzeń, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

Aby utworzyć profil urządzenia zawierający ustawienia ograniczeń dotyczących urządzeń:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu ograniczeń urządzenia.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia niestandardowe. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Ograniczenia dotyczące urządzeń**. Aby utworzyć profil ograniczeń dotyczących urządzeń z systemem Windows 10 Team, np. urządzeń Surface Hub, wybierz pozycję **Ograniczenia dotyczące urządzeń (Windows 10 Team)**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu Android](device-restrictions-android.md)
    - [Ustawienia systemu iOS](device-restrictions-ios.md)
    - [macOS settings](device-restrictions-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 settings](device-restrictions-windows-10.md) (Ustawienia systemu Windows 10)
    - [Windows 10 Team settings](device-restrictions-windows-10-teams.md) (Ustawienia systemu Windows 10 Team)
    - [Ustawienia systemu Windows Holographic for Business](device-restrictions-windows-holographic.md)
    - [Ustawienia programu Android for Work](device-restrictions-android-for-work.md)
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->