---
title: Porównanie opcji zarządzania komputerem z systemem Windows
titleSuffix: Microsoft Intune
description: Rejestrowanie urządzeń firmowych z systemem iOS przy użyciu programu Apple Device Enrollment Program (DEP) lub narzędzia Apple Configurator.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/13/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: d8fd53e9d12dd38639d204e214aea03d733e584b
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059195"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Organizacje mogą użyć usługi Microsoft Intune do zarządzania komputerami z systemem Windows albo jako urządzeniami mobilnymi z wykorzystaniem zarządzania urządzeniami mobilnymi (MDM), albo jako komputerami z wykorzystaniem oprogramowania klienckiego usługi Intune.  Firma Microsoft zaleca, aby klienci używali rozwiązania MDM do zarządzania zawsze, gdy jest to możliwe. Aby lepiej zrozumieć różnice między tymi dwiema opcjami zarządzania, zapoznaj się z poniższą tabelą.

|**Możliwość / scenariusz** |**Komputer z systemem Windows jako komputer**<br>Oprogramowanie klienckie usługi Intune | **Komputer z systemem Windows jako urządzenie mobilne**<br>ZARZĄDZANIE URZĄDZENIAMI PRZENOŚNYMI |
|--------------|-------------------------------|-------------------------------|
|**Systemy operacyjne** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Pomoc techniczna portalu usługi Intune** |[Konsola programu Silverlight](https://manage.microsoft.com)|[Portal Azure](https://portal.azure.com) |
|**Dostęp warunkowy**|Niedostępne|Dostępne <br>[Co to jest dostęp warunkowy?](../protect/conditional-access.md)|
|**Rejestrowanie zbiorcze**|Niedostępne|Dostępne <br>[Rejestracja zbiorcza urządzeń z systemem Windows](../enrollment/windows-bulk-enroll.md)|
|**Profile urządzeń**|Niedostępne|Dostępne <br>[Co to są profile urządzeń w usłudze Microsoft Intune?](../configuration/device-profiles.md)|
|**Rejestracja bez agenta**|Niedostępne |Dostępne<br>[Rejestrowanie urządzeń z systemem Windows](../enrollment/windows-enroll.md)|
|**Zarządzanie aktualizacjami oprogramowania**| Aktualizacje systemu Windows i aplikacji firmy Microsoft<br>[Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Sklep Microsoft dla firm z aktualizacjami zarówno systemu Windows 10, jak i aplikacji firmy Microsoft<br> [Konfigurowanie ustawień usługi Windows Update dla firm](../protect/windows-update-for-business-configure.md) |
|**Zarządzanie licencjami na oprogramowanie**|Dostępne <br>[Zarządzanie umowami licencyjnymi na oprogramowanie na komputerze z systemem Windows](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|Sklep Microsoft dla firm (tylko aplikacje .appx)<br>[Zarządzanie aplikacjami zakupionymi w Sklepie Microsoft dla Firm](../apps/windows-store-for-business.md)|
|**Inventory** (Spis)|Dostępne <br>[Wyświetlanie spisu sprzętu i oprogramowania dla komputerów z systemem Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|Dostępne <br>[Monitorowanie informacji o aplikacji](../apps/apps-monitor.md)<br>[Co to jest zarządzanie urządzeniami](../remote-actions/device-management.md)|
|**Zasady zapory systemu Windows**|Dostępne <br>[Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |Dostępne <br>[Zapora Microsoft Defender](../protect/endpoint-protection-windows-10.md#microsoft-defender-firewall)|
|**Ochrona przed złośliwym oprogramowaniem**|Ochrona punktu końcowego<br>[Ochrona komputerów z systemem Windows przy użyciu programu Endpoint Protection](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Usługa Microsoft Defender<br>[Włączanie programu Microsoft Defender](../protect/advanced-threat-protection.md)|
|**Pomoc zdalna** |TeamViewer<br>[Żądanie i zapewnianie pomocy zdalnej dla komputerów z systemem Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [Używanie programu TeamViewer do zdalnego administrowania urządzeniami usługi Intune](../remote-actions/teamviewer-support.md) |
|**Wdrażanie aplikacji** | Niedostępne dla Sklepu Microsoft dla firm,<br>tylko pliki .exe, .appx i wieloplikowe instalatory .msi<br>[Dodawanie aplikacji dla komputerów z systemem Windows, na których jest uruchomione oprogramowanie klienckie usługi Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)|Dostępne dla aplikacji ze Sklepu Microsoft i aplikacji biznesowych<br>[Dodawanie aplikacji ze Sklepu Windows](../apps/store-apps-windows.md)<br>[Jak dodawać aplikacje biznesowe dla systemu Windows](../apps/lob-apps-windows.md)|
|**Ochrona aplikacji**|Niedostępne|Dostępne <br>[Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)|
|**Zaświadczanie o kondycji**|Niedostępne|Dostępne|


## <a name="advantages-of-mdm-windows-pc-management"></a>Zalety zarządzania komputerami z systemem Windows z użyciem rozwiązania MDM
Zarządzanie komputerami z systemem Windows z użyciem nowoczesnego zarządzania urządzeniami mobilnymi ma następujące zalety:
- **Skalowalność** — zarządzanie MDM skaluje się dzięki zarządzaniu w chmurze w usłudze Intune. Oprogramowanie klienckie usługi Intune jest ograniczone do 7000 komputerów.
- **Prostota** — korzystanie z nowoczesnych możliwości zarządzania zawartych w systemie operacyjnym bez konieczności pobierania oprogramowania klienckiego
- **Spójność** — komputery z systemem Windows są zarządzane tak, jak wszystkie inne urządzenia mobilne w organizacji
<!-- - **Cloud optimization** - -->
