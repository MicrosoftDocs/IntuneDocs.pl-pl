---
title: "Resetowanie i usuwanie kodów dostępu urządzeń w usłudze Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak zresetować lub usunąć kod dostępu na urządzeniach zarządzanych za pomocą usługi Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfa94d11f978bbe4d23b6672423c849e1f061986
ms.sourcegitcommit: 474a24ba67f6bf4f00268bf9e4eba52331a6b82d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2017
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Resetowanie i usuwanie kodu dostępu na urządzeniach zarządzanych przez usługę Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Terminy *usuwanie* i *resetowanie* są używane zamiennie w tym artykule.

Akcja **Resetuj kod dostępu** generuje nowy kod dostępu do urządzenia, wyświetlany w bloku <*nazwa urządzenia*> **Przegląd**.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — obsługiwana w systemach od Windows Phone 8.1 do Windows 10 z aktualizacją systemu Windows 10 dla twórców nieprzyłączonych do usługi Azure AD, aktualizacja systemu Windows 10 dla twórców i nowsze wersje
- iOS — obsługiwana
- macOS — nieobsługiwana
- Android — obsługiwana w wersjach wcześniejszych niż Android 7. Program Android for Work nie jest obsługiwany.

## <a name="how-to-reset-a-passcode"></a>Jak zresetować kod dostępu

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną urządzenia **Resetuj kod dostępu**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
