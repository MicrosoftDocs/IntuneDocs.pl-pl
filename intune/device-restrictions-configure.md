---
title: Konfiguracja ustawień ograniczeń urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie profilu urządzenia w celu ograniczenia funkcji w urządzeniach z systemem Android, macOS, iOS, Windows Phone oraz Windows 10 w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e040743975a482c702e0c0168a4fd6315a2dac8
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57387925"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Konfiguracja ustawień ograniczeń urządzeń w usłudze Microsoft Intune

Ograniczenia dotyczące urządzeń pozwalają na kontrolę szerokiego zakresu ustawień i funkcji, którymi można zarządzać w ramach wielu kategorii, takich jak:
- Zabezpieczenia
- Przeglądarka
- Sprzęt
- Ustawienia związane z udostępnianiem danych

Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia.

Zapoznaj się z podstawowymi informacjami na temat profilów ograniczeń, a następnie przeczytaj kolejne artykuły dotyczące poszczególnych platform, aby dowiedzieć się więcej o konkretnych urządzeniach.

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > wpisz nazwę usługi **Intune** w filtrze > wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj **nazwę** i **opis** profilu ograniczenia urządzenia.
4. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia niestandardowe. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:

    - **Android**
    - **Android enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**

5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Ograniczenia dotyczące urządzeń**. Aby utworzyć profil ograniczeń dotyczących urządzeń z systemem Windows 10 Team, np. urządzeń Surface Hub, wybierz pozycję **Ograniczenia dotyczące urządzeń (Windows 10 Team)**.
6. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Wybierz platformę dla ustawień szczegółowych:

    - [Ustawienia systemu Android](device-restrictions-android.md)
    - [Ustawienia systemu Android Enterprise](device-restrictions-android-for-work.md)
    - [Ustawienia systemu iOS](device-restrictions-ios.md)
    - [macOS settings](device-restrictions-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 settings](device-restrictions-windows-10.md) (Ustawienia systemu Windows 10)
    - [Windows 10 Team settings](device-restrictions-windows-10-teams.md) (Ustawienia systemu Windows 10 Team)
    - [Ustawienia systemu Windows Holographic for Business](device-restrictions-windows-holographic.md)

7. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil został utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
