---
title: Usuwanie użytkownika z urządzenia z systemem iOS przy użyciu usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak usunąć użytkownika ze współdzielonego urządzenia z systemem iOS przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 00733600555118533ef2754d0b2b37184f93b309
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189221"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Usuwanie użytkownika ze współdzielonego urządzenia z systemem iOS


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja **Usuń użytkownika** powoduje usunięcie wybranego użytkownika z lokalnej pamięci podręcznej na udostępnionym urządzeniu iPad. Urządzenie iPad należy skonfigurować do zarządzania aplikacją iOS Classroom przy użyciu [profilu Edukacja w systemie iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS — obsługiwana w systemie iOS 9.3 lub nowszym (tylko współdzielone urządzenia iPad)
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="remove-a-user"></a>Usuwanie użytkownika

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Urządzenia**.
4. W okienku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS.
6. W okienku urządzenia wybierz pozycję **Użytkownicy**.
7. Na liście kliknij prawym przyciskiem myszy użytkownika, którego chcesz usunąć, a następnie wybierz polecenie **Usuń użytkownika**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan akcji **Usuń użytkownika**, wybierz pozycję **Urządzenia** > **Akcje urządzenia**.
