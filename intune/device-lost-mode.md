---
title: "Aktywowanie trybu zgubienia urządzenia z systemem iOS przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Informacje dotyczące używania usługi Intune do aktywowania trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fcdd5e6fa844d4c475462cd0b2a4883f8ff9ba90
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="activate-lost-mode-on-ios-devices"></a>Aktywowanie trybu zgubienia na urządzeniach z systemem iOS


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Tryb zgubienia** ułatwia włączenie trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS. Ten tryb pozwala określić komunikat i numer telefonu, który jest wyświetlany na ekranie blokady urządzenia.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS — obsługiwana w systemie iOS 9.3 lub nowszym, nadzorowanym i należącym do firmy
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="how-to-activate-lost-mode"></a>Jak uaktywnić tryb zgubienia

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną **Tryb zgubienia**.
6. W bloku **Tryb zgubienia** włącz tryb zgubienia. Następnie wprowadź komunikat, który ma być wyświetlany, i, opcjonalnie, numer telefonu do kontaktu.
7. Kliknij przycisk **OK**.

Po włączeniu trybu utraty wszystkie sposoby korzystania z urządzenia zostaną zablokowane. Użytkownik końcowy nie może uzyskać dostępu do urządzenia aż do momentu wyłączenia przez Ciebie trybu utraty. Przy włączonym trybie utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby dowiedzieć się, gdzie znajduje się urządzenie.
Aby użyć trybu zgubienia, urządzenie musi być urządzeniem z systemem iOS należącym do firmy i objętym trybem nadzorowanym.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie utraty oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji żadne informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po włączeniu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w portalu Azure.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- Zalecamy, aby wprowadzony komunikat, który będzie wyświetlany na ekranie blokady, zawierał informacje ułatwiające zwrot urządzenia przez osobę, która je znajdzie.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, w bloku **Urządzenia** wybierz pozycję **Akcje urządzenia**.

