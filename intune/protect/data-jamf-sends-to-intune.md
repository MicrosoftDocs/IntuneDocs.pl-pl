---
title: Dane wysyłane do usługi Intune przez narzędzie JAMF Pro
titleSuffix: Microsoft Intune
description: Przejrzyj listę danych wysyłanych przez narzędzie Jamf Pro do usługi Microsoft Intune podczas integrowania narzędzia Jamf Pro w celu zarządzania komputerami Mac w usłudze Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 449e799dfc0531958c1578179cf07440d348ecf8
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71813952"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Dane wysyłane do usługi Intune przez narzędzie Jamf Pro

Kiedy używasz narzędzia [Jamf Pro](https://www.jamf.com) do zarządzania komputerami Mac użytkowników końcowych w usłudze Intune, narzędzie Jamf Pro przechwytuje informacje dotyczące spisu zarządzanych urządzeń z systemem macOS. 

## <a name="data"></a>Dane  
Aby uzyskać listę danych, które narzędzie Jamf Pro udostępnia usłudze Intune, zobacz [Appendix: Inventory Information Shared with Microsoft Intune](https://docs.jamf.com/technical-papers/jamf-pro/microsoft-intune/10.9.0/Appendix__Inventory_Information_Shared_with_Microsoft_Intune.html) (Informacje o spisie udostępniane usłudze Microsoft Intune) w dokumentacji technicznej narzędzia Jamf Pro. 

<!--  
Jamf Pro reports the following information to Intune:  

* Device Azure AD ID
* JAMF Inventory State (inventory state of a computer checked in with Jamf Pro within the last 24 hours)
* OS Version
* User Azure AD ID
* Encrypted (FileVault 2)
* Gatekeeper Status
* Password: minimum number of character sets
* Password expiration (days)
* Password Type - simple, alphanumeric, or unknown
* Prevent Auto Login
* Required Passcode Length
* Password: number of previous passwords to prevent reuse
* System Integrity Protection
* Last Check-In Time
* Architecture Type
* Available RAM Slots
* Battery Capacity
* Boot ROM
* Bus Speed
* Cache Size
* Device Name
* Domain Join
* Jamf ID
* MAC address
* Make
* Model
* Model Identifier
* NIC Speed
* Number of Cores
* Number of Processors
* OS
* Platform
* Processor Speed
* Processor Type
* Secondary MAC Address
* Serial Number
* SMC Version
* Total RAM
* UDID
* User Email
--> 

<!-- 
You can remove a Jamf-managed device from the Intune console by selecting **Delete** in the **All devices** view. Bulk device deletion can be enabled by selecting multiple devices and clicking **Delete**.
-->

## <a name="next-steps"></a>Następne kroki
Zapoznaj się z informacjami na temat [usuwania urządzenia zarządzanego za pomocą narzędzia Jamf w dokumentacji programu Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Możesz również wypełnić bilet pomocy technicznej dla [obsługi Jamf](https://www.jamf.com/support/) w celu uzyskania dodatkowej pomocy. 

