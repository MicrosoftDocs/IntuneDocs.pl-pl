---
title: "Wylogowywanie użytkownika z urządzenia z systemem iOS przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak wylogować bieżącego użytkownika z urządzenia z systemem iOS przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1de2069b7b25ee5e5c21a8e4caa7512f13d4ca0e
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/09/2017
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Wylogowywanie bieżących użytkowników z urządzeń z systemem iOS zarządzanych przez usługę Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Akcja **Wyloguj bieżącego użytkownika** wylogowuje bieżącego użytkownika na udostępnionym urządzeniu iPad, które jest skonfigurowane w celu zarządzania aplikacją Classroom systemu iOS przy użyciu [profilu systemu iOS dla instytucji edukacyjnych](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS — obsługiwana w systemie iOS 9.3 lub nowszym (tylko współdzielone urządzenia iPad)
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="how-to-logout-the-current-user"></a>Jak wylogować bieżącego użytkownika

1.  Zaloguj się do portalu Azure Portal.
2.  Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3.  W bloku **Intune** wybierz opcję **Urządzenia**.
4.  W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5.  Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, a następnie wybierz akcję zdalną **Wyloguj bieżącego użytkownika**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
