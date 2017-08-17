---
title: "Synchronizacja urządzeń w usłudze Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak synchronizować urządzenia w usłudze Intune, aby pobrać najnowsze zasady i akcje."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 870eb3bf255cda92952a908596485d7b53259fb4
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/09/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchronizacja urządzeń w usłudze Intune w celu pobrania najnowszych zasad i akcji


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Synchronizacja** wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady.  Ta akcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane ewidencjonowanie.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana
- Windows Phone — obsługiwana
- iOS — obsługiwana
- macOS — obsługiwana
- Android — obsługiwana

## <a name="how-to-sync-a-device"></a>Jak zsynchronizować urządzenie

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych przez Ciebie urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną **Synchronizacja**.
7. Kliknij przycisk **Tak**, aby potwierdzić akcję.

## <a name="next-steps"></a>Następne kroki

Wybierz pozycję **Akcje urządzeń**, aby zobaczyć stan akcji synchronizacji. 
