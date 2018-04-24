---
title: Wymazywanie urządzenia z systemem macOS
titleSuffix: Microsoft Intune
description: Dowiedz się, jak wymazać wszystkie dane, łącznie z systemem operacyjnym, z urządzenia z systemem macOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d99bef78d635f98f9c888d8096247f314ade6a52
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="erase-all-data-from-a-macos-device"></a>Wymazywanie wszystkich danych z urządzenia z systemem macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Możesz wymazać wszystkie dane z urządzenia z systemem macOS, łącznie z systemem operacyjnym. Urządzenie zostanie również usunięte z zarządzania przez usługę Intune. Użytkownik końcowy nie otrzyma żadnego ostrzeżenia.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycje **Urządzenia** > **Wszystkie urządzenia** i wybierz urządzenie, które chcesz wymazać.
![Zrzut ekranu](./media/device-erase/choosedevice.png)
2. Kliknij przycisk **Więcej** > **Wymaż** > podaj 6-cyfrową liczbę dla **Numeru PIN odzyskiwania**. Jest to numer PIN, który musisz przekazać użytkownikowi, aby mógł on ponowne zainstalować system operacyjny na swoim urządzeniu. Pamiętaj, aby zanotować ten numer PIN, ponieważ nie będzie on widoczny po ukończeniu akcji wymazywania.
![Zrzut ekranu](./media/device-erase/providepin.png)
3. Kliknij przycisk **OK**, aby wymazać urządzenie.
