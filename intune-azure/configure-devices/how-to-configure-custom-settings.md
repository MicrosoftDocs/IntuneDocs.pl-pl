---
title: "Jak skonfigurować niestandardowe ustawienia urządzeń w usłudze Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące konfigurowania ustawień niestandardowych na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: d9da3f1c2ccade5391e2e874336802602a016700
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Kiedy użyć ustawień niestandardowych

Niestandardowe ustawienia urządzeń mogą okazać się przydatne, jeśli usługa Intune nie ma wbudowanych ustawień, które chcesz skonfigurować, i są one niedostępne z innych profilów urządzeń.
Konfiguracja ustawień niestandardowych przebiega różnie w zależności od platformy. Na przykład w przypadku urządzeń z systemem Android i Windows można określić wartości Open Mobile Alliance Uniform Resource Identifier (OMA-URI) w celu sterowania funkcjami urządzeń. W przypadku urządzeń firmy Apple można zaimportować plik utworzony za pomocą programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów z użyciem ustawień niestandardowych, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-custom-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia niestandardowe

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
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
    - [Ustawienia systemu Android](custom-for-android.md)
    - [Ustawienia systemu iOS](custom-for-ios.md)
    - [macOS settings](custom-for-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](custom-for-windows-phone-8-1.md)
    - [Windows 10 settings](custom-for-windows-10.md) (Ustawienia systemu Windows 10)
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).

