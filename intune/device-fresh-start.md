---
title: Resetowanie urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Usuń lub odinstaluj aplikacje na komputerach z systemem Windows 10 przy użyciu funkcji Rozpoczęcie od nowa usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b66cd00f734cab3ca85f6d87f056f8c482a377d
ms.sourcegitcommit: 2811df0f851ca6b08f6ae8c926fb2e6971c41690
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2018
ms.locfileid: "40251646"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Użycie funkcji Rozpoczęcie od nowa do resetowania urządzeń z systemem Windows 10 przy użyciu usługi Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja **Rozpoczęcie od nowa** urządzenia usuwa wszystkie aplikacje zainstalowane na komputerze z systemem Windows 10 w wersji 1703 lub nowszej. Akcja Rozpoczęcie od nowa ułatwia usunięcie wstępnie zainstalowanych aplikacji (OEM), które zwykle są zainstalowane na nowym komputerze.  

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i przejdź do obszaru > **Microsoft Intune** > **Urządzenia** > **Wszystkie urządzenia**.
2. Z listy urządzeń zarządzanych wybierz urządzenie z systemem Windows 10 Desktop.
3. Kliknij pozycję **Rozpoczęcie od nowa**. 
4. Wybierz opcję **Zachowaj dane użytkownika na tym urządzeniu**, aby:
   * urządzenie pozostało dołączone do usługi Azure AD,
    * urządzenie pozostało zarejestrowane w usłudze zarządzania urządzeniami przenośnymi, 
    * zachować zawartość folderu macierzystego urządzenia użytkownika i usunąć aplikacje i ustawienia.  
  > [!IMPORTANT]
 > Jeśli nie zachowasz danych użytkownika, urządzenia zostanie przywrócone do stanu po zakupie. Zostanie ono wyrejestrowane z usługi Azure AD i z usługi zarządzania urządzeniami przenośnymi. 
 
5. Kliknij przycisk **OK**.   
6. Aby wyświetlić stan tej akcji, wróć do obszaru **Urządzenia** i kliknij przycisk **Akcje urządzenia**.  
