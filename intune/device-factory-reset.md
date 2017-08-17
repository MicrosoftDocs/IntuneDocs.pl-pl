---
title: "Resetowanie urządzeń do ustawień fabrycznych przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Informacje na temat resetowania urządzeń zarządzanych przy użyciu usługi Intune to ustawień fabrycznych."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44f69179f76c8d5eeca1594485ca3a9c1b036188
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/09/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Resetowanie urządzeń zarządzanych przy użyciu usługi Intune do ustawień fabrycznych


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Opcja **Resetowanie do ustawień fabrycznych** przywraca na urządzeniu ustawienia domyślne. Urządzenie nie jest już zarządzane przez usługę Intune i zarówno dane firmy, jak i dane osobiste są usuwane. Nie można cofnąć tej akcji.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana w systemie Windows 8.1 i nowszym (urządzenia niezarządzane przez program EAS)
- Windows Phone — obsługiwana
- iOS — obsługiwana
- macOS — nieobsługiwana
- Android — obsługiwana (program Android for Work nie jest obsługiwany)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Jak można zresetować urządzenie do ustawień fabrycznych

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną **Resetowanie do ustawień fabrycznych** dla urządzenia.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.

