---
title: Konfiguracja ustawień ograniczeń urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie profilu urządzenia w celu ograniczenia funkcji w urządzeniach z systemem Android, macOS, iOS, Windows Phone oraz Windows 10 w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9b84877d37d26dababda2987801fc7267cb3c2e6
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181211"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Konfiguracja ustawień ograniczeń urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ograniczenia dotyczące urządzeń pozwalają na kontrolę szerokiego zakresu ustawień i funkcji, którymi można zarządzać w ramach wielu kategorii, takich jak:
- Zabezpieczenia
- Przeglądarka
- Sprzęt
- Ustawienia związane z udostępnianiem danych

Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia.

Zapoznaj się z podstawowymi informacjami na temat profilów ograniczeń, a następnie przeczytaj kolejne artykuły dotyczące poszczególnych platform, aby dowiedzieć się więcej o konkretnych urządzeniach.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia ograniczeń dotyczących urządzeń

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Podaj **nazwę** i **opis** profilu ograniczenia urządzenia.
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
    - [Ustawienia profilu służbowego w systemie Android](device-restrictions-android-for-work.md)
8. Po zakończeniu wróć na stronę **Utwórz profil** i kliknij pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na stronie listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
