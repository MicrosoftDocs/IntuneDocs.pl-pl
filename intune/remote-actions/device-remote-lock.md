---
title: Blokowanie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Zablokuj urządzenie chronione za pomocą kodu PIN lub hasła za pomocą akcji Zdalne blokowanie w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26d0f2cf08786a36f51982901094969d4d014755
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509385"
---
# <a name="remotely-lock-devices-with-intune"></a>Zdalne blokowanie urządzeń przy użyciu usługi Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

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

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy urządzeń wybierz urządzenie, a następnie wybierz akcję **Zdalne blokowanie**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan tej akcji, wybierz pozycję **Microsoft Intune** > **Urządzenia** > **Akcje urządzenia**. 
- Aby uzyskać więcej akcji ułatwiających zarządzanie urządzeniami, zobacz [Dostępne akcje](device-management.md).
