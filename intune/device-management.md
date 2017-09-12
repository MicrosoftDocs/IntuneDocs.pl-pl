---
title: "Zarządzanie urządzeniami w usłudze Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak wyświetlać urządzenia zarządzane w usłudze Intune i wykonywać na nich różne operacje."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca40eee8a53fa3e8b2610ce414f0037180d4beaf
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. Możesz wyświetlać informacje na temat urządzeń i zdalnie wykonywać na urządzeniach wymienione akcje.

## <a name="available-device-actions"></a>Dostępne akcje urządzenia
Dostępne akcje zależą od platformy urządzenia i jego konfiguracji.

- [Wyświetl spis urządzeń](device-inventory.md)
- Wykonaj akcje zdalne urządzenia:
    - [Usuń dane firmy](devices-wipe.md#remove-company-data)
    - [Resetuj do ustawień fabrycznych](devices-wipe.md#factory-reset)
    - [Zdalne blokowanie](device-remote-lock.md)
    - [Zresetuj kod dostępu](device-passcode-reset.md)
    - [Obchodzenie blokady aktywacji](device-activation-lock-bypass.md) (tylko system iOS)
    - [Zaczynanie od początku](device-fresh-start.md) (tylko system Windows)
    - [Tryb zgubienia](device-lost-mode.md) (tylko system iOS)
    - [Lokalizowanie urządzenia](device-locate.md) (tylko system iOS)
    - [Ponowne uruchamianie](device-restart.md) (tylko system Windows)
    - [Resetowanie numeru PIN w systemie Windows 10](device-windows-pin-reset.md)
    - [Zdalne sterowanie dla systemu Android](device-profile-android-teamviewer.md)
    - [Synchronizowanie urządzenia](device-sync.md)


## <a name="next-steps"></a>Następne kroki

- Wybierz pozycję **Akcje urządzenia**, aby zobaczyć stan akcji podjętych na zarządzanych urządzeniach.
![Monitoruj akcje urządzenia](./media/monitor-device-actions.png)
