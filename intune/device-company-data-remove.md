---
title: "Usuwanie danych firmowych z urządzeń przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące usuwania tylko danych firmowych z urządzeń zarządzanych przy użyciu usługi Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8074d6e7cc0a061a6708f8c8bfae1a4dfcb6daa3
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Usuwanie danych firmowych z urządzeń zarządzanych przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Usuń dane firmowe** usuwa tylko dane firmy z urządzeń zarządzanych przez usługę Intune. Ta akcja nie usuwa z urządzenia danych osobistych. Po usunięciu urządzenie nie jest już zarządzane przez usługę Intune i nie będzie mieć już dostępu do zasobów firmy.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana (nie są obsługiwane urządzenia z systemem Windows, które są przyłączone do usługi Azure Active Directory)
- Windows Phone — obsługiwana
- iOS — obsługiwana
- macOS — obsługiwana
- Android — obsługiwana

## <a name="how-to-remove-company-data"></a>Jak usunąć dane firmy

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną **Usuń dane firmowe** dla urządzenia.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
