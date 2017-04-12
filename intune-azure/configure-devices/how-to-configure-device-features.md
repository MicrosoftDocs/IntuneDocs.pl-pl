---
title: "Konfigurowanie ustawień funkcji urządzenia w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące konfigurowania funkcji na urządzeniach zarządzanych przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: dd53e547a8f834eff528e79cf2506be1e6c2dc2a
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia funkcji urządzeń w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ograniczenia urządzenia pozwalają sterować funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i konfiguracje udostępnianych urządzeń.

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów funkcji urządzeń, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia ograniczeń dotyczących urządzeń

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu funkcji urządzenia.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia. Obecnie dla funkcji urządzenia można wybrać jedną z następujących platform:
    - **iOS**
    - **macOS**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Funkcje urządzenia**. 
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu iOS](device-features-for-ios.md)
    - [macOS settings](device-features-for-macos.md) (Ustawienia systemu macOS)

8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).




