---
title: "Resetowanie kodów dostępu urządzenia za pomocą usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Usuwanie lub resetowanie kodu dostępu przy użyciu akcji kodu Usuń kod dostępu na urządzeniach zarządzanych i monitorowanych przy użyciu usługi Intune."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f23a79bbe72d12750ef642226aefd1e11dcac24
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetowanie lub usuwanie kodu dostępu urządzenia w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Aby utworzyć nowy kod dostępu urządzenia, użyj akcji **Resetuj kod dostępu**.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Systemy od Windows Phone 8.1 do Windows 10 z aktualizacją systemu Windows 10 dla twórców nieprzyłączone do usługi Azure AD, aktualizacja systemu Windows 10 dla twórców i nowsze wersje
- iOS
- Wersje systemu Android wcześniejsze niż Android 7

Ta funkcja **nie jest** obsługiwana w następujących systemach:

- Windows
- macOS
- Program Android for Work

## <a name="reset-a-passcode"></a>Resetowanie kodu dostępu

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną urządzenia **Resetuj kod dostępu**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan właśnie wykonanej akcji, w obszarze **Urządzenia** wybierz pozycję **Akcje urządzenia**.
