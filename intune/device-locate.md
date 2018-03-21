---
title: "Znajdowanie zgubionych urządzeń z systemem iOS za pomocą usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Znajdź lub zlokalizuj zgubione albo skradzione urządzenie z systemem iOS, korzystając z funkcji Zlokalizuj urządzenie w usłudze Microsoft Intune; uzyskaj szczegółowe informacje dotyczące zabezpieczeń i ochrony prywatności podczas korzystania z akcji Zlokalizuj urządzenie."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Znajdowanie zgubionych lub skradzionych urządzeń z systemem iOS przy użyciu usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja **Zlokalizuj urządzenie** umożliwia wyświetlenie na mapie lokalizacji zgubionego lub skradzionego urządzenia z systemem iOS. Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w programie Device Enrollment Program (DEP) i objętym trybem nadzorowanym. Przed użyciem tej akcji należy się upewnić, że urządzenie jest w [trybie zgubienia](device-lost-mode.md).

## <a name="supported-platforms"></a>Obsługiwane platformy

- iOS 9.3 i nowsze

Ta funkcja **nie jest** obsługiwana w następujących systemach: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Lokalizowanie zgubionego lub skradzionego urządzenia

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną **Zlokalizuj urządzenie**.
5. Po zlokalizowaniu urządzenia jego lokalizacja będzie wyświetlana w bloku **Zlokalizuj urządzenie**.
    ![Lokalizowanie urządzenia przy użyciu usługi Intune na platformie Azure](./media/locate-device.png)

>[!NOTE]
>W celu zachowania prywatności stopień powiększenia mapy jest ograniczony.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie zgubienia oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji żadne informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po włączeniu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w portalu Azure.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- Po skonfigurowaniu trybu zgubienia można dostosować komunikat wyświetlany na ekranie blokady. W tym komunikacie, aby pomóc znalazcy urządzenia, należy podać szczegółowe informacje umożliwiające zwrot zgubionego urządzenia.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan włączania lokalizowania urządzenia, otwórz obszar **Urządzenia** i wybierz pozycję **Akcje urządzenia**.
