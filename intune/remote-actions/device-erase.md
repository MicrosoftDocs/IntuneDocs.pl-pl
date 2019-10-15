---
title: Wymazywanie urządzenia z systemem macOS
titleSuffix: Microsoft Intune
description: Dowiedz się, jak wymazać wszystkie dane, łącznie z systemem operacyjnym, z urządzenia z systemem macOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e2f4ce1295d4a3f2250988d25246c532ff2cdd73
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728237"
---
# <a name="erase-all-data-from-a-macos-device"></a>Wymazywanie wszystkich danych z urządzenia z systemem macOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Możesz wymazać wszystkie dane z urządzenia z systemem macOS, łącznie z systemem operacyjnym. Urządzenie zostanie również usunięte z zarządzania przez usługę Intune. Użytkownik końcowy nie otrzyma żadnego ostrzeżenia.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycje **Urządzenia** > **Wszystkie urządzenia** i wybierz urządzenie, które chcesz wymazać.
![Zrzut ekranu](./media/device-erase/choosedevice.png)
2. Kliknij przycisk **Więcej** > **Wymaż** > podaj 6-cyfrową liczbę dla **Numeru PIN odzyskiwania**. Jest to numer PIN, który musisz przekazać użytkownikowi, aby mógł on ponowne zainstalować system operacyjny na swoim urządzeniu. Pamiętaj, aby zanotować ten numer PIN, ponieważ nie będzie on widoczny po ukończeniu akcji wymazywania.
![Zrzut ekranu](./media/device-erase/providepin.png)
3. Kliknij przycisk **OK**, aby wymazać urządzenie.