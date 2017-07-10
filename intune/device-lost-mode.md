---
title: "Aktywowanie trybu zgubienia urządzenia z systemem iOS przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące używania usługi Intune do aktywowania trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a34d008ae76355578c6f24a932c9e1e501d5b46b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Aktywowanie trybu zgubienia na urządzeniach z systemem iOS


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Tryb zgubienia** ułatwia włączenie trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS. Ten tryb pozwala określić komunikat i numer telefonu, które będą wyświetlane na ekranie blokady urządzenia.

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, a następnie wybierz akcję zdalną **Tryb zgubienia**.
6. W bloku **Tryb utraty** włącz tryb utraty, wprowadź komunikat, który będzie wyświetlany, i opcjonalnie podaj numer telefonu kontaktowego.
7. Kliknij przycisk **OK**.

Po włączeniu trybu utraty wszystkie sposoby korzystania z urządzenia zostaną zablokowane. Użytkownik końcowy nie może uzyskać dostępu do urządzenia aż do momentu wyłączenia przez Ciebie trybu utraty. Przy włączonym trybie utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby dowiedzieć się, gdzie znajduje się urządzenie.
Aby skorzystać z trybu utraty, urządzenie musi być urządzeniem z systemem iOS,należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym.

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie utraty oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po włączeniu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w portalu Azure.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- Zalecamy, aby wprowadzony podczas konfigurowania trybu zgubienia komunikat, który będzie wyświetlany na ekranie blokady, zawierał informacje ułatwiające zwrot urządzenia przez osobę, która je znajdzie.

