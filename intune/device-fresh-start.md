---
title: "Resetowanie urządzeń z systemem Windows 10 przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak korzystać z funkcji Rozpoczęcie od nowa, aby zresetować komputery z systemem Windows 10 zarejestrowane w usłudze Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff6198cb42d5c96ed4e4c4e0009a8bbd6f6a0dec
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Użycie funkcji Rozpoczęcie od nowa do resetowania urządzeń z systemem Windows 10 przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Rozpoczęcie od nowa** usuwa wszystkie aplikacje, które zostały zainstalowane na komputerze z systemem Windows 10 z aktualizacją dla twórców, a następnie automatycznie aktualizuje komputer do najnowszej wersji systemu Windows.
Funkcja może być przydatna do usuwania wstępnie zainstalowanych aplikacji OEM, które są często dostarczane z nowymi komputerami. Możesz zdecydować, czy dane użytkownika zostaną zachowane w przypadku wykonania tej akcji dla urządzenia. W takim przypadku aplikacje i ustawienia są usuwane, ale zawartość folderów macierzystych zostaje zachowana.

## <a name="how-to-use-fresh-start"></a>Jak używać funkcji Rozpoczęcie od nowa

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie komputerowe z systemem Windows 10, a następnie wybierz akcję zdalną urządzenia **Rozpoczęcie od nowa**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.

