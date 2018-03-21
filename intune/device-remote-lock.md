---
title: "Blokowanie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Aby zablokować urządzenie chronione za pomocą numeru PIN lub hasła, użyj akcji Zdalne blokowanie w usłudze Microsoft Intune."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Zdalne blokowanie urządzeń przy użyciu usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Zdalne blokowanie** urządzenia umożliwia zablokowanie urządzenia. Aby je odblokować, właściciel urządzenia wprowadza swój kod dostępu. Możesz zdalnie zablokować urządzenia, które mają ustawiony numer PIN lub hasło. Nie można zdalnie zablokować urządzeń, które nie mają numeru PIN ani kodu dostępu.

## <a name="supported-platforms"></a>Obsługiwane platformy

Zdalne blokowanie jest obsługiwane na następujących platformach:

- Android
- iOS
- macOS
- Windows 10 Mobile
- System Windows Phone 8.1 lub nowszy

**Nie jest** obsługiwane w przypadku:
- Windows 10 Desktop

> [!NOTE]
> Dla urządzeń z systemem macOS należy ustawić 6-cyfrowy numer PIN na potrzeby odzyskiwania. Gdy blokada jest aktywna, do momentu wysłania innej akcji urządzenia na ekranie jest widoczny blok **Przegląd urządzenia** z monitem o numer PIN.

## <a name="remote-lock-a-device"></a>Zdalne blokowanie urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy urządzeń wybierz urządzenie, a następnie wybierz akcję **Zdalne blokowanie**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan tej akcji, otwórz **Akcje urządzenia** (Microsoft Intune > Urządzenia). Zobacz [Dostępne akcje](device-management.md), aby uzyskać więcej akcji ułatwiających zarządzanie urządzeniami.