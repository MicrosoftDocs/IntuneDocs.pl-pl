---
title: "Zdalne blokowanie urządzeń zarządzanych przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Informacje dotyczące zdalnego blokowania zarządzanych urządzeń przy użyciu usługi Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Zdalne blokowanie urządzeń zarządzanych przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Zdalne blokowanie** urządzenia umożliwia zablokowanie wybranego urządzenia. W celu odblokowania urządzenia jego właściciel musi użyć swojego kodu dostępu. Można zdalnie zablokować tylko urządzenie, które ma ustawiony numer PIN lub hasło.

## <a name="supported-platforms"></a>Obsługiwane platformy

Zdalne blokowanie jest obsługiwane na następujących platformach:

|Platforma|Stan obsługi|
|---|---|
|Android|Tak|
|iOS|Tak|
|macOS|Tak|
|Windows 10|Tak|
|Windows 10 Mobile|Tak|
|Windows Phone|Tak, w przypadku systemu Windows Phone 8.1 i nowszych|

> [!NOTE]  
> Dla urządzeń z systemem macOS należy ustawić 6-cyfrowy numer PIN na potrzeby odzyskiwania. Gdy blokada jest aktywna, do momentu wysłania innej akcji urządzenia na ekranie jest widoczny blok **Przegląd urządzenia** z monitem o numer PIN.

## <a name="how-to-remote-lock-a-device"></a>Jak zdalnie zablokować urządzenie

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną **Zdalne blokowanie** urządzenia.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
