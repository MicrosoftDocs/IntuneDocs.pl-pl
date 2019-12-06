---
title: Korzystanie z maszyn wirtualnych systemu Windows 10 z usługą Microsoft Intune
titleSuffix: ''
description: Wskazówki dotyczące korzystania z maszyn wirtualnych systemu Windows 10 z usługą Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9afaf2c8a63bfaed1fdb593baf42c8fa258d7893
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2019
ms.locfileid: "74263120"
---
# <a name="using-windows-10-virtual-machines-with-intune"></a>Korzystanie z maszyn wirtualnych systemu Windows 10 z usługą Intune

Usługa Intune obsługuje zarządzanie maszynami wirtualnymi z systemem Windows 10 Enterprise — z pewnymi ograniczeniami. Zarządzanie w ramach usługi Intune nie zależy od zarządzania tą samą maszyną wirtualną za pomocą usługi zarządzania Windows Virtual Desktop ani nie wpływa na nie.

Zarządzając maszynami wirtualnymi systemu Windows 10 za pomocą usługi Intune, należy wziąć pod uwagę następujące zagadnienia:

## <a name="enrollment"></a>Rejestrowanie
- Nie zalecamy zarządzania maszynami wirtualnymi hosta sesji na żądanie za pomocą usługi Intune. Po utworzeniu każdą maszynę wirtualną należy zarejestrować. Należy również [czyścić](../remote-actions/devices-wipe.md#automatically-delete-devices-with-cleanup-rules) osierocone rekordy urządzeń w usłudze Intune pozostałe po regularnym usuwaniu maszyn wirtualnych. 
- Tryb samodzielnej rejestracji w ramach rozwiązania Windows Autopilot nie jest obsługiwany, ponieważ wymaga modułu Trusted Platform Module (TPM). 
- Rejestrowanie Out of Box Experience (OOBE) nie jest obsługiwane na maszynach wirtualnych, do których można uzyskać dostęp tylko za pośrednictwem protokołu RDP (takich jak maszyny wirtualne hostowane na platformie Azure). Konsekwencje tego ograniczenia są następujące:
    - Rozwiązanie Windows Autopilot ani komercyjne rozwiązania OOBE nie są obsługiwane.
    - Opcje strony stanu rejestracji dotyczące zasad w kontekście urządzenia nie są obsługiwane.

## <a name="configuration"></a>Konfiguracja
Usługa Intune nie obsługuje konfiguracji korzystających z modułu Trusted Platform Module ani zarządzania sprzętowego, takich jak:
- [ustawienia funkcji BitLocker](../configuration/device-profiles.md#endpoint-protection),
- [ustawienia interfejsu konfiguracji oprogramowania układowego urządzenia](../configuration/device-profiles.md#device-firmware-configuration-interface).

## <a name="reporting"></a>Raportowanie
Usługa Intune automatycznie wykrywa maszyny wirtualne i wyświetla je pod nazwą „Maszyna wirtualna” w polu **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Przegląd** > **Model**. 

Maszyny wirtualne, którym cofnięto przydział, mogą się przyczynić do powstania niezgodnych raportów o urządzeniach, ponieważ nie mogą one [zostać zaewidencjonowane w usłudze Intune](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

## <a name="retirement"></a>Wycofanie
Jeśli masz tylko dostęp RDP, nie korzystaj z [akcji Wyczyść](../remote-actions/devices-wipe.md#wipe). Akcja Wyczyść usuwa ustawienia RDP maszyny wirtualnej i uniemożliwia ponowne nawiązanie połączenia.


