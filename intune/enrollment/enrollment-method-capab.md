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
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30b46fcbb7ec6963e855c79478dbdef5b5cd8b90
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723141"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Możliwości metod rejestracji usługi Intune dla urządzeń z systemem Windows
[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Istnieje kilka metod rejestrowania urządzeń pracowników w usłudze Intune. Każda metoda ma inne najlepsze rozwiązania oraz możliwości, jak pokazano w poniższych tabelach.

## <a name="best-practices-by-enrollment-method"></a>Najlepsze rozwiązania według metody rejestracji
| **Najlepsze rozwiązania** | **[Dołączone do usługi Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb sterowany przez użytkownika)](enrollment-autopilot.md)** |**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb samowdrażania)](enrollment-autopilot.md)** |**[Zbiorcze](windows-bulk-enroll.md)**|**[Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md)** | **[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Współzarządzanie](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Często używane w usłudze EDU|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Urządzenia mogą być używane jako urządzenia udostępnione|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Urządzenia osobiste muszą mieć dostęp do zasobów firmy|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Samoobsługa aplikacji|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Możliwości według metody rejestracji

| **Możliwości** | **[Dołączone do usługi Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb sterowany przez użytkownika)](enrollment-autopilot.md)** |**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot (tryb samowdrażania)](enrollment-autopilot.md)** |**[Zbiorcze](windows-bulk-enroll.md)**|**[Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md)** | **[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Współzarządzanie](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Dostęp warunkowy                                      |![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Użytkownicy zostają skojarzeni z urządzeniem                    |![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Wymaga usługi Azure AD — wersja Premium                               |![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Urządzenia mogą oceniać zasoby chronione przez urząd certyfikacji             |![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Użytkownicy nie mogą być administratorami na swoich urządzeniach               |![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Możliwość skonfigurowania środowiska konfiguracji urządzenia        |![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Możliwość rejestrowania urządzeń bez interakcji z użytkownikiem      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Możliwość uruchamiania skryptów programu PowerShell                       |![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/checkmark.png)\*| 
|Obsługuje automatyczne rejestrowanie po przyłączeniu do domeny usługi AD      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Obsługuje automatyczne rejestrowanie po dołączeniu hybrydowym do usługi Azure AD|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|
|Obsługuje automatyczne rejestrowanie po dołączeniu do usługi Azure AD       |![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![Znacznik wyboru](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|

\* Pakiety robocze aplikacji klienckich w aplikacji Configuration Manager muszą zostać przeniesione do usługi Intune Pilot lub Intune.

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie rejestracji dla systemu Windows](windows-enroll.md)

