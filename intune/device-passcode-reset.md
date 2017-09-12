---
title: "Resetowanie kodu dostępu urządzenia przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak zresetować kod dostępu na urządzeniach zarządzanych przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7a292342000a4f60455aa44202a1bf0493ae66f0
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Resetowanie kodu dostępu na urządzeniach zarządzanych przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja **Resetuj kod dostępu** generuje nowy kod dostępu urządzenia, które jest wyświetlane w bloku <*nazwa urządzenia*> **Przegląd**.

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
