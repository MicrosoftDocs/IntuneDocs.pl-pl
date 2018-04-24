---
title: Resetowanie urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Usuń lub odinstaluj aplikacje na komputerach z systemem Windows 10 przy użyciu funkcji Rozpoczęcie od nowa usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5658bf2e1ee250ef9fd405b3f7ec1772b166f338
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Użycie funkcji Rozpoczęcie od nowa do resetowania urządzeń z systemem Windows 10 przy użyciu usługi Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Rozpoczęcie od nowa** usuwa wszystkie aplikacje zainstalowane na komputerze z systemem Windows 10 z aktualizacją dla twórców. Następnie automatycznie aktualizuje komputer do najnowszej wersji systemu Windows.

Ta akcja ułatwia usunięcie wstępnie zainstalowanych aplikacji (OEM), które zwykle są zainstalowane na nowym komputerze. Aby zachować zawartość folderu macierzystego użytkownika i usunąć tylko aplikacje i ustawienia, użyj ustawienia `if user data is retained`.

> [!IMPORTANT]
> Rozpoczęcie od nowa powoduje wyrejestrowanie urządzenia z usługi Intune, ale urządzenie jest nadal przyłączone w usłudze Azure Active Directory.

## <a name="use-fresh-start"></a>Używanie funkcji Rozpoczęcie od nowa

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie z systemem Windows 10 Desktop, a następnie wybierz pozycję **Rozpoczęcie od nowa**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan tej akcji, wybierz pozycję **Akcje urządzenia** (**Microsoft Intune** > **Urządzenia**).