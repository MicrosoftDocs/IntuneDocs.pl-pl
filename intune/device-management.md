---
title: "Zarządzanie urządzeniami w usłudze Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak wyświetlać urządzenia zarządzane w usłudze Intune i wykonywać na nich różne operacje."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.

Teraz można wykonywać poniższe akcje:

- [Wyświetl spis urządzeń](device-inventory.md)
- Wykonaj akcje zdalne urządzenia:
    - [Usuń dane firmy](device-company-data-remove.md) 
    - [Resetuj do ustawień fabrycznych](device-factory-reset.md)
    - [Zdalne blokowanie](device-remote-lock.md)
    - [Zresetuj kod dostępu](device-passcode-reset.md)
    - [Zastosowanie obejścia blokady aktywacji](device-activation-lock-bypass.md)
    - [Rozpoczęcie od nowa](device-fresh-start.md)
    - [Tryb utraty](device-lost-mode.md)
    - [Zlokalizuj urządzenie](device-locate.md)
    - [Uruchom ponownie](device-restart.md)
    - [Resetowanie numeru PIN w systemie Windows 10](device-windows-pin-reset.md)
    - [Zdalne sterowanie dla systemu Android](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>Obsługa poszczególnych akcji urządzeń

Poniższa tabela pozwala zapoznać się z platformami urządzeń obsługiwanymi przez poszczególne akcje.

|||||||
|-|-|-|-|-|-|
|Akcja urządzenia|Windows|Windows Phone|iOS|macOS|Android|
|**Usuń dane firmy**|Tak|Tak|Tak|Tak|Tak|
|**Resetuj do ustawień fabrycznych**|Windows 8.1 i nowsze (urządzenia niezarządzane przez program EAS)|Tak|Tak|Nie|Program Android for Work nie jest obsługiwany|
|**Usuwanie**|Tak|Tak|Tak|Tak|Tak|
|**Zdalne blokowanie**|Nie|System Windows Phone 8.1 lub nowszy|Tak|Nie|Tak|
|**Zresetuj kod dostępu**|Nie|Systemy od Windows Phone 8.1 do Windows 10 z aktualizacją systemu Windows 10 dla twórców nieprzyłączone do usługi Azure AD, aktualizacja systemu Windows 10 dla twórców i nowsze wersje — wszystkie|Tak|Nie|Wcześniejsze niż Android 7, program Android for Work nie jest obsługiwany|
|**Nowy kod dostępu** (w przypadku urządzeń z systemem Windows 10)|Nie|Aktualizacja systemu Windows 10 dla twórców i nowsze wersje (z przyłączeniem do usługi Azure AD)|Nie|Nie|Program Android for Work nie jest obsługiwany|
|**Zastosowanie obejścia blokady aktywacji**|Nie|Nie|Tylko urządzenia należące do firmy|Nie|Nie|
|**Tryb utraty**|Nie|Nie|Z systemem iOS 9.3 lub nowszą wersją, nadzorowane i należące do firmy|Nie|Nie|
|**Zlokalizuj urządzenie**|Nie|Nie|Tryb utraty Z systemem iOS 9.3 lub nowszą wersją, nadzorowane i należące do firmy|Nie|Nie|
|**Wyloguj bieżącego użytkownika**|Nie|Nie|Z systemem iOS 9.3 lub nowszą wersją (tylko współdzielone urządzenia iPad)|Nie|Nie|
|**Uruchom ponownie**|Windows 8.1 i nowsze|System Windows Phone 8.1 lub nowszy|Nie|Nie|Nie|
|**Rozpoczęcie od nowa**|Aktualizacja systemu Windows 10 dla twórców i nowsze wersje|Nie|Nie|Nie|Nie|
|**Nowa sesja pomocy zdalnej**|Nie|Nie|Nie|Nie|Tak|
|**Usuń użytkownika**|Nie|Nie|Z systemem iOS 9.3 lub nowszą wersją (tylko współdzielone urządzenia iPad)|Nie|Nie|

## <a name="next-steps"></a>Następne kroki

- Wybierz pozycję **Akcje urządzenia**, aby zobaczyć stan akcji podjętych na zarządzanych urządzeniach. 
![Monitoruj akcje urządzenia](./media/monitor-device-actions.png)