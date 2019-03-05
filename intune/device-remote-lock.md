---
title: Blokowanie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Zablokuj urządzenie chronione za pomocą kodu PIN lub hasła za pomocą akcji Zdalne blokowanie w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 328f196a61f26fa787495e515fb5de3e0d32f7b2
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231285"
---
# <a name="remotely-lock-devices-with-intune"></a>Zdalne blokowanie urządzeń przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Zdalne blokowanie** umożliwia zablokowanie urządzenia. Aby odblokować urządzenie, jego właściciel wprowadza swój kod dostępu. Możesz zdalnie zablokować urządzenia, które mają ustawiony numer PIN lub hasło. Nie można zdalnie zablokować urządzeń, które nie mają kodu PIN ani hasła.

## <a name="supported-platforms"></a>Obsługiwane platformy

**Zdalne blokowanie** jest obsługiwane na następujących platformach:

- Android
- Urządzenia kiosku w rozwiązaniu Android enterprise
- Urządzenia z profilami służbowymi w rozwiązaniu Android enterprise
- iOS
- macOS
- Windows 10 Mobile
- System Windows Phone 8.1 lub nowszy

**Zdalne blokowanie** nie jest obsługiwane na następujących platformach:
- Windows 10 Desktop

> [!NOTE]
> Dla urządzeń z systemem macOS należy ustawić 6-cyfrowy numer PIN na potrzeby odzyskiwania. Gdy urządzenie jest zablokowane, w obszarze **Przegląd urządzenia** do momentu wysłania innej akcji urządzenia jest wyświetlany kod PIN.

## <a name="remote-lock-a-device"></a>Zdalne blokowanie urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy urządzeń wybierz urządzenie, a następnie wybierz akcję **Zdalne blokowanie**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan tej akcji, wybierz pozycję **Microsoft Intune** > **Urządzenia** > **Akcje urządzenia**. 
- Aby uzyskać więcej akcji ułatwiających zarządzanie urządzeniami, zobacz [Dostępne akcje](device-management.md).
