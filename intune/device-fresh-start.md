---
title: "Resetowanie urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Aby usunąć lub odinstalować aplikacje na komputerach z systemem Windows 10 przy użyciu usługi Microsoft Intune, w tym również wstępnie zainstalowane aplikacje od producentów OEM, użyj funkcji Rozpoczęcie od nowa. Można również przechowywać zawartość folderu macierzystego przy użyciu ustawienia określającego, czy dane użytkownika są zachowywane."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d17c9dc11791f32f0c2c1e7faa88966c112fc6a5
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Użycie funkcji Rozpoczęcie od nowa do resetowania urządzeń z systemem Windows 10 przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja **Rozpoczęcie od nowa** urządzenia usuwa wszystkie aplikacje zainstalowane na komputerze z systemem Windows 10 z uruchomioną aktualizacją dla twórców. Następnie automatycznie aktualizuje komputer do najnowszej wersji systemu Windows.

Ta akcja ułatwia usunięcie wstępnie zainstalowanych aplikacji (OEM), które zwykle są zainstalowane na nowym komputerze. Aby zachować zawartość folderu macierzystego użytkownika i usunąć tylko aplikacje i ustawienia, użyj ustawienia `if user data is retained`.

> [!IMPORTANT]
> Rozpoczęcie od nowa powoduje wyrejestrowanie urządzenia z usługi Intune, ale urządzenie jest nadal przyłączone w usłudze Azure Active Directory.

## <a name="use-fresh-start"></a>Używanie funkcji Rozpoczęcie od nowa

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie z systemem Windows 10 Desktop, a następnie wybierz pozycję **Rozpoczęcie od nowa**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan tej akcji, wybierz pozycję **Akcje urządzenia** (**Microsoft Intune** > **Urządzenia**).