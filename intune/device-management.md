---
title: "Zarządzanie urządzeniami przy użyciu usługi Microsoft Intune"
titleSuffix: 
description: "Przeglądaj urządzenia zarządzane w usłudze Intune i wykonuj na nich różne operacje."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/21/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e69f47e841cb44ab646431d5bd81b9c1d874c64
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator IT musisz się upewnić, że zarządzane urządzenia udostępniają zasoby, których użytkownicy końcowi potrzebują do wykonania swojej pracy, a jednocześnie chronić te dane przed ryzykiem.

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W obszarze **Intune** wybierz pozycję **Urządzenia**.
4. Możesz wyświetlać informacje na temat urządzeń i zdalnie wykonywać na urządzeniach następujące akcje:
    - **Przegląd** — migawka zarejestrowanych urządzeń, którymi możesz zarządzać.
    - **Wszystkie urządzenia** — lista zarejestrowanych urządzeń, którymi zarządzasz. Wybierz pozycję **Filtr** lub **Kolumny**, aby zawęzić wyświetlane informacje. Wybierz urządzenie, aby [wyświetlić spis urządzeń](device-inventory.md):
    - **Urządzenia w usłudze Azure AD** — lista urządzeń zarejestrowanych w usłudze Azure Active Directory (AD) lub dołączonych do tej usługi. Dowiedz się więcej o [zarządzaniu urządzeniami w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Akcje urządzenia** — historia zdalnych akcji wykonywanych na urządzeniach, obejmująca informacje o każdej akcji, jej stanie, osobie inicjującej i czasie akcji.

        ![Zrzut ekranu przedstawiający monitorowanie akcji urządzenia](./media/monitor-device-actions.png)

    - **Dzienniki inspekcji** — dzienniki inspekcji stanowią rekord działań, które generują zmiany w usłudze Microsoft Intune. Dowiedz się więcej o [dziennikach inspekcji](monitor-audit-logs.md).
    - **Łącznik usługi TeamViewer** — usługa TeamViewer umożliwia użytkownikom urządzeń z systemem Android zarządzanych przez usługę Intune uzyskiwanie pomocy zdalnej od administratora IT. Dowiedz się więcej o programie [TeamViewer](device-profile-android-teamviewer.md).
    - **Pomoc i obsługa techniczna** — rozwiązywanie problemów, wnioskowanie o pomoc techniczną lub wyświetlanie stanu usługi Intune.  
    
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
