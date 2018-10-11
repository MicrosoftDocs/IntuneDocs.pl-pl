---
title: Możliwości usługi Intune według metody rejestracji dla urządzeń z systemem Windows
titlesuffix: Microsoft Intune
description: Zobacz możliwości obsługiwane przez poszczególne metody rejestracji dla urządzeń z systemem Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c9e440aef7f434cbe675506fd6f22a9bd26b2c31
ms.sourcegitcommit: 528d2bc70bfd25803a2d9f0fe9372c8a5f5e7dad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2018
ms.locfileid: "47446824"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Możliwości według metody rejestracji dla urządzeń z systemem Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune umożliwia zarządzanie urządzeniami i aplikacjami pracowników oraz sposobem uzyskiwania przez nich dostępu do danych firmy. Urządzenia muszą najpierw zostać zarejestrowane w usłudze Intune. Istnieje kilka metod rejestrowania urządzeń pracowników. Każda metoda ma inne najlepsze rozwiązania oraz możliwości, jak pokazano w poniższych tabelach.

## <a name="best-practices-by-enrollment-method"></a>Najlepsze rozwiązania według metody rejestracji
| **Najlepsze rozwiązania** | **[Dołączone do usługi Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot](enrollment-autopilot.md)** |**[Zbiorcze](windows-bulk-enroll.md)**|**[Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md)** | **[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](device-enrollment.md#bring-your-own-device)** | **Obiekt zasad grupy** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Często używane w usłudze EDU|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Urządzenia mogą być używane jako urządzenia udostępnione|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Urządzenia osobiste muszą mieć dostęp do zasobów firmy|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|
|Samoobsługa aplikacji|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Możliwości według metody rejestracji

| **Możliwości** | **[Dołączone do usługi Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Dołączone do usługi Azure AD za pomocą rozwiązania Autopilot](enrollment-autopilot.md)** |**[Zbiorcze](windows-bulk-enroll.md)**|**[Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md)** | **[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](device-enrollment.md#bring-your-own-device)** | **Obiekt zasad grupy** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Dostęp warunkowy                                      |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Użytkownicy zostają skojarzeni z urządzeniem                    |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Wymaga usługi Azure AD — wersja Premium                               |![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Urządzenia mogą oceniać zasoby chronione przez urząd certyfikacji             |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Użytkownicy nie mogą być administratorami na swoich urządzeniach               |![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Możliwość skonfigurowania środowiska konfiguracji urządzenia        |![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Możliwość rejestrowania urządzeń bez interakcji z użytkownikiem      |![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Możliwość uruchamiania skryptów programu PowerShell                       |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Obsługuje automatyczne rejestrowanie po przyłączeniu do domeny usługi AD      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Obsługuje automatyczne rejestrowanie po dołączeniu hybrydowym do usługi Azure AD|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Znacznik wyboru](media/checkmark.png)|
|Obsługuje automatyczne rejestrowanie po dołączeniu do usługi Azure AD       |![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![Znacznik wyboru](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Następne kroki

[Opcje rejestracji](enrollment-options.md)

