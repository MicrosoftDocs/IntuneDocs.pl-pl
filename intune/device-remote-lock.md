---
title: Blokowanie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Zablokuj urządzenie chronione za pomocą kodu PIN lub hasła za pomocą akcji Zdalne blokowanie w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45ab6434245c0dd412b2e9d23e394f72871a459a
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31829768"
---
# <a name="remotely-lock-devices-with-intune"></a>Zdalne blokowanie urządzeń przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Zdalne blokowanie** umożliwia zablokowanie urządzenia. Aby odblokować urządzenie, jego właściciel wprowadza swój kod dostępu. Możesz zdalnie zablokować urządzenia, które mają ustawiony numer PIN lub hasło. Nie można zdalnie zablokować urządzeń, które nie mają kodu PIN ani hasła.

## <a name="supported-platforms"></a>Obsługiwane platformy

**Zdalne blokowanie** jest obsługiwane na następujących platformach:

- Android
- iOS
- macOS
- Windows 10 Mobile
- System Windows Phone 8.1 lub nowszy

**Zdalne blokowanie** *nie* jest obsługiwane na następujących platformach:
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
