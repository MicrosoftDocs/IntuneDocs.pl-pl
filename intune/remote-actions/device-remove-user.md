---
title: Usuwanie użytkownika z urządzenia z systemem iOS/iPadOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak usunąć użytkownika ze współdzielonego urządzenia z systemem iOS/iPadOS przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b6b2b3492b9edece6b69e4b302741c0443c0a3e
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415569"
---
# <a name="remove-a-user-from-a-shared-iosipados-device"></a>Usuwanie użytkownika z udostępnionego urządzenia z systemem iOS/iPadOS


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja **Usuń użytkownika** powoduje usunięcie wybranego użytkownika z lokalnej pamięci podręcznej na udostępnionym urządzeniu iPad. Urządzenie iPad należy skonfigurować do zarządzania aplikacją iOS/iPad Classroom przy użyciu [profilu Edukacja w systemie iOS/iPad](../fundamentals/education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — nieobsługiwana
- Windows Phone — nieobsługiwana
- iOS/iPadOS — obsługiwana w systemie iOS/iPadOS 9.3 lub nowszym (tylko udostępnione urządzenia iPad)
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="remove-a-user"></a>Usuwanie użytkownika

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
3. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS/iPadOS.
4. W okienku urządzenia wybierz pozycję **Użytkownicy**.
5. Na liście kliknij prawym przyciskiem myszy użytkownika, którego chcesz usunąć, a następnie wybierz polecenie **Usuń użytkownika**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan akcji **Usuń użytkownika**, wybierz pozycję **Urządzenia** > **Akcje urządzenia**.
