---
title: "Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące konfigurowania ustawień niestandardowych na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 769c566c7ebb91743fc0f18ebf8f3e76377ca847
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Kiedy użyć ustawień niestandardowych

Niestandardowe ustawienia urządzeń mogą okazać się przydatne, jeśli usługa Intune nie ma wbudowanych ustawień, które chcesz skonfigurować, i są one niedostępne z innych profilów urządzeń.
Konfiguracja ustawień niestandardowych przebiega różnie w zależności od platformy. Na przykład w przypadku urządzeń z systemem Android i Windows można określić wartości Open Mobile Alliance Uniform Resource Identifier (OMA-URI) w celu sterowania funkcjami urządzeń. W przypadku urządzeń firmy Apple można zaimportować plik utworzony za pomocą programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów z użyciem ustawień niestandardowych, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-custom-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia niestandardowe

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu niestandardowego.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia niestandardowe. Obecnie dla ustawień niestandardowych urządzenia można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu Android](custom-settings-android.md)
    - [Ustawienia systemu iOS](custom-settings-ios.md)
    - [macOS settings](custom-settings-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Windows 10 settings](custom-settings-windows-10.md) (Ustawienia systemu Windows 10)
    - [Ustawienia programu Android for Work](custom-settings-android-for-work.md)
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).
