---
title: Możliwości metod rejestracji usługi Intune dla urządzeń z systemem Windows
titleSuffix: Microsoft Intune
description: Możliwości każdej metody rejestracji dla urządzeń z systemem Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd1dbb3280fbbb93423796b18f6dd85a50a41f11
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567546"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Możliwości metod rejestracji usługi Intune dla urządzeń z systemem Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Istnieje kilka metod rejestrowania urządzeń pracowników w usłudze Intune. Każda metoda ma inne najlepsze rozwiązania oraz możliwości, jak pokazano w poniższych tabelach.

## <a name="best-practices-by-enrollment-method"></a>Najlepsze rozwiązania według metody rejestracji
| **Najlepsze rozwiązania** | **[Dołączone do usługi Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb sterowany przez użytkownika)](enrollment-autopilot.md)** |**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb samowdrażania)](enrollment-autopilot.md)** |**[Zbiorcze](windows-bulk-enroll.md)**|**[Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md)** | **[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Współzarządzanie](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Często używane w usłudze EDU|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Urządzenia mogą być używane jako urządzenia udostępnione|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Urządzenia osobiste muszą mieć dostęp do zasobów firmy|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Samoobsługa aplikacji|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Możliwości według metody rejestracji

| **Możliwości** | **[Dołączone do usługi Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb sterowany przez użytkownika)](enrollment-autopilot.md)** |**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb samowdrażania)](enrollment-autopilot.md)** |**[Zbiorcze](windows-bulk-enroll.md)**|**[Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md)** | **[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Współzarządzanie](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Dostęp warunkowy                                      |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Użytkownicy zostają skojarzeni z urządzeniem                    |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Wymaga usługi Azure AD — wersja Premium                               |![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Urządzenia mogą oceniać zasoby chronione przez urząd certyfikacji             |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Użytkownicy nie mogą być administratorami na swoich urządzeniach               |![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Możliwość skonfigurowania środowiska konfiguracji urządzenia        |![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Możliwość rejestrowania urządzeń bez interakcji z użytkownikiem      |![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Możliwość uruchamiania skryptów programu PowerShell                       |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Obsługuje automatyczne rejestrowanie po przyłączeniu do domeny usługi AD      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Obsługuje automatyczne rejestrowanie po dołączeniu hybrydowym do usługi Azure AD|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Obsługuje automatyczne rejestrowanie po dołączeniu do usługi Azure AD       |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie rejestracji dla systemu Windows](windows-enroll.md)

