---
title: "Znajdowanie zgubionych urządzeń z systemem iOS przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak znaleźć zgubione lub skradzione urządzenia z systemem iOS przy użyciu usługi Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 864d528091de7a6113485347304b0dc254af2c7d
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Znajdowanie zgubionych lub skradzionych urządzeń z systemem iOS przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Zlokalizuj urządzenie** umożliwia wyświetlenie na mapie lokalizacji zgubionego lub skradzionego urządzenia z systemem iOS. Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym. Przed użyciem tej akcji urządzenie musi znajdować się w [trybie zgubienia](device-lost-mode.md).

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS — obsługiwana w systemie iOS 9.3 lub nowszym (w trybie zgubienia), nadzorowanym i należącym do firmy
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Jak zlokalizować zgubione lub skradzione urządzenie

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną **Zlokalizuj urządzenie**.
6. Po zlokalizowaniu urządzenia jego lokalizacja jest wyświetlana w bloku **Zlokalizuj urządzenie**.
    Blok ![Zlokalizuj urządzenie](./media/locate-device.png)

>[!NOTE]
>W celu zachowania prywatności stopień powiększenia mapy jest ograniczony.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie utraty oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po włączeniu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w portalu Azure.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- Zalecamy, aby wprowadzony podczas konfigurowania trybu zgubienia komunikat, który będzie wyświetlany na ekranie blokady, zawierał informacje ułatwiające zwrot urządzenia przez osobę, która je znajdzie.


## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, w bloku **Urządzenia** wybierz pozycję **Akcje urządzenia**.