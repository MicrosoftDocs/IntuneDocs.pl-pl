---
title: "Znajdowanie zgubionych urządzeń z systemem iOS przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak znaleźć zgubione lub skradzione urządzenia z systemem iOS przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 80aa0e5afd1f8862b181d455ff6b545e462f90c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Znajdowanie zgubionych lub skradzionych urządzeń z systemem iOS przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Zlokalizuj urządzenie** umożliwia wyświetlenie na mapie lokalizacji zgubionego lub skradzionego urządzenia z systemem iOS. Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym. Przed użyciem tej akcji urządzenie musi znajdować się w [trybie zgubienia](/intune-azure/manage-devices/lost-mode.md).

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, a następnie wybierz akcję zdalną **Zlokalizuj urządzenie**.
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
