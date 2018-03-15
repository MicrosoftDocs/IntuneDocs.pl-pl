---
title: "Konfigurowanie ustawień ograniczeń urządzenia w usłudze Microsoft Intune"
titleSuffix: 
description: "Informacje dotyczące konfigurowania ustawień i funkcji na zarządzanych urządzeniach przy użyciu usługi Microsoft Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 62c12cde5ca128a26b10e0e4516e0bbf7e0f0bbb
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia ograniczeń dotyczących urządzeń w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ograniczenia dotyczące urządzeń pozwalają na kontrolę szerokiego zakresu ustawień i funkcji, którymi można zarządzać w ramach wielu kategorii, takich jak:
- Zabezpieczenia
- Przeglądarka
- Sprzęt
- Ustawienia związane z udostępnianiem danych

Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia.

Zapoznaj się z podstawowymi informacjami na temat profilów ograniczeń, a następnie przeczytaj kolejne artykuły dotyczące poszczególnych platform, aby dowiedzieć się więcej o konkretnych urządzeniach.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia ograniczeń dotyczących urządzeń

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Na stronie **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. Na stronie **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz opcję **Profile**.
3. Na stronie **Profile** wybierz pozycję **Utwórz profil**.
4. Na stronie **Utwórz profil** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu ograniczeń urządzenia.
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
8. Po zakończeniu wróć na stronę **Utwórz profil** i kliknij pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na stronie listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->