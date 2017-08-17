---
title: "Zarządzanie urządzeniami w usłudze Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak wyświetlać urządzenia zarządzane w usłudze Intune i wykonywać na nich różne operacje."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0fc5337b92ac604a448038f685b27623b6153f9
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. Teraz możesz wykonać wymienione akcje zdalnego urządzenia. Dostępne akcje zależą od platformy urządzenia i konfiguracji urządzenia:

## <a name="available-device-actions"></a>Dostępne akcje urządzenia

- [Wyświetl spis urządzeń](device-inventory.md)
- Wykonaj akcje zdalne urządzenia:
    - [Usuń dane firmy](device-company-data-remove.md) 
    - [Resetuj do ustawień fabrycznych](device-factory-reset.md)
    - [Zdalne blokowanie](device-remote-lock.md)
    - [Zresetuj kod dostępu](device-passcode-reset.md)
    - [Zastosowanie obejścia blokady aktywacji](device-activation-lock-bypass.md)
    - [Rozpoczęcie od nowa](device-fresh-start.md)
    - [Tryb utraty](device-lost-mode.md)
    - [Zlokalizuj urządzenie](device-locate.md)
    - [Uruchom ponownie](device-restart.md)
    - [Resetowanie numeru PIN w systemie Windows 10](device-windows-pin-reset.md)
    - [Zdalne sterowanie dla systemu Android](device-profile-android-teamviewer.md)
    - [Synchronizowanie urządzenia](device-sync.md)


## <a name="next-steps"></a>Następne kroki

- Wybierz pozycję **Akcje urządzenia**, aby zobaczyć stan akcji podjętych na zarządzanych urządzeniach. 
![Monitoruj akcje urządzenia](./media/monitor-device-actions.png)
