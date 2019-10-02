---
title: Usuwanie użytkownika z urządzenia z systemem iOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak usunąć użytkownika ze współdzielonego urządzenia z systemem iOS przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f418149d8640f7fd663f0bbf4b3151ffb428a75e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728484"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Usuwanie użytkownika ze współdzielonego urządzenia z systemem iOS


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja **Usuń użytkownika** powoduje usunięcie wybranego użytkownika z lokalnej pamięci podręcznej na udostępnionym urządzeniu iPad. Urządzenie iPad należy skonfigurować do zarządzania aplikacją iOS Classroom przy użyciu [profilu Edukacja w systemie iOS](../fundamentals/education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS — obsługiwana w systemie iOS 9.3 lub nowszym (tylko współdzielone urządzenia iPad)
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="remove-a-user"></a>Usuwanie użytkownika

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Urządzenia**.
4. W okienku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS.
6. W okienku urządzenia wybierz pozycję **Użytkownicy**.
7. Na liście kliknij prawym przyciskiem myszy użytkownika, którego chcesz usunąć, a następnie wybierz polecenie **Usuń użytkownika**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan akcji **Usuń użytkownika**, wybierz pozycję **Urządzenia** > **Akcje urządzenia**.
