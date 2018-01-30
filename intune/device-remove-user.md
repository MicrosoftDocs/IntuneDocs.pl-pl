---
title: "Usuwanie użytkownika z urządzenia z systemem iOS przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak usunąć użytkownika ze współdzielonego urządzenia z systemem iOS przy użyciu usługi Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 979614aaa450493ea0b5cc2a1baaccc10a6dd028
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Usuwanie użytkownika ze współdzielonego urządzenia z systemem iOS przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja **Usuń użytkownika** usuwa wybranego użytkownika z lokalnej pamięci podręcznej na udostępnionym urządzeniu iPad, które zostało skonfigurowane w celu zarządzania aplikacją Classroom systemu iOS przy użyciu [profilu systemu iOS dla instytucji edukacyjnych](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS — obsługiwana w systemie iOS 9.3 lub nowszym (tylko współdzielone urządzenia iPad)
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="how-to-remove-a-user"></a>Jak usunąć użytkownika

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS.
6. W bloku tego urządzenia wybierz pozycję **Użytkownicy**.
7. Na liście kliknij prawym przyciskiem myszy użytkownika, którego chcesz usunąć, a następnie wybierz polecenie **Usuń użytkownika**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
