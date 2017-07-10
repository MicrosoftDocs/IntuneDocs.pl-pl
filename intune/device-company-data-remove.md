---
title: "Usuwanie danych firmowych z urządzeń przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące usuwania tylko danych firmowych z urządzeń zarządzanych przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Usuwanie danych firmowych z urządzeń zarządzanych przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Polecenie **Usuń dane firmowe** usuwa tylko dane firmowe z urządzeń zarządzanych przy użyciu usługi Intune. Nie usuwa z urządzenia danych osobistych. Urządzenie nie będzie już zarządzane przez usługę Intune i nie będzie mogło uzyskać dostępu do zasobów firmy (nieobsługiwane w przypadku urządzeń z systemem Windows, które są połączone z usługą Azure Active Directory).

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną **Usuń dane firmowe** dla urządzenia.

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
