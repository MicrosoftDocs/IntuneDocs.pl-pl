---
title: "Zarządzanie urządzeniami w usłudze Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak wyświetlać urządzenia zarządzane w usłudze Intune i wykonywać na nich różne operacje."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b034e144aa43d239874b484acb2a40be12aff7c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator IT musisz się upewnić, że zarządzane urządzenia udostępniają zasoby, których użytkownicy końcowi potrzebują do wykonania swojej pracy, a jednocześnie chronić te dane przed ryzykiem.

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W obszarze **Intune** wybierz pozycję **Urządzenia**.
4. Możesz wyświetlać informacje na temat urządzeń i zdalnie wykonywać na urządzeniach następujące akcje:
    - **Przegląd** — migawka zarejestrowanych urządzeń, którymi możesz zarządzać.
    - **Wszystkie urządzenia** — lista zarejestrowanych urządzeń, którymi zarządzasz. Wybierz pozycję **Filtr** lub **Kolumny**, aby zawęzić wyświetlane informacje. Wybierz urządzenie, aby [wyświetlić spis urządzeń](device-inventory.md):
    - **Urządzenia w usłudze Azure AD** — lista urządzeń zarejestrowanych w usłudze Azure Active Directory (AD) lub dołączonych do tej usługi. Dowiedz się więcej o [zarządzaniu urządzeniami w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Akcje urządzenia** — historia zdalnych akcji wykonywanych na urządzeniach, obejmująca informacje o każdej akcji, jej stanie, osobie inicjującej i czasie akcji.

    ![Monitorowanie akcji urządzenia](./media/monitor-device-actions.png)

    - **TeamViewer** — usługa TeamViewer umożliwia użytkownikom urządzeń z systemem Android zarządzanych przez usługę Intune uzyskiwanie pomocy zdalnej od administratora IT. Dowiedz się więcej o programie [TeamViewer](device-profile-android-teamviewer.md).

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
