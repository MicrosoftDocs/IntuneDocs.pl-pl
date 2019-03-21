---
title: Porównanie opcji zarządzania komputerem z systemem Windows
titlesuffix: Microsoft Intune
description: Rejestrowanie urządzeń firmowych z systemem iOS przy użyciu programu Apple Device Enrollment Program (DEP) lub narzędzia Apple Configurator.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c70dbee01c546f73052b8741ce339c7bfe92fc7
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461145"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Organizacje mogą użyć usługi Microsoft Intune do zarządzania komputerami z systemem Windows albo jako urządzeniami mobilnymi z wykorzystaniem zarządzania urządzeniami mobilnymi (MDM), albo jako komputerami z wykorzystaniem oprogramowania klienckiego usługi Intune.  Firma Microsoft zaleca, aby klienci używali rozwiązania MDM do zarządzania zawsze, gdy jest to możliwe. Aby lepiej zrozumieć różnice między tymi dwiema opcjami zarządzania, zapoznaj się z poniższą tabelą.

|**Możliwość / scenariusz** |**Komputer z systemem Windows jako komputer**<br>Oprogramowanie klienckie usługi Intune | **Komputer z systemem Windows jako urządzenie mobilne**<br>ZARZĄDZANIE URZĄDZENIAMI PRZENOŚNYMI |
|--------------|-------------------------------|-------------------------------|
|**Systemy operacyjne** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Pomoc techniczna portalu usługi Intune** |[Konsola programu Silverlight](https://manage.microsoft.com)|[Portal Azure](https://portal.azure.com) |
|**Dostęp warunkowy**|Niedostępne|Dostępne <br>[Co to jest dostęp warunkowy?](conditional-access.md)|
|**Rejestrowanie zbiorcze**|Niedostępne|Dostępne <br>[Rejestracja zbiorcza urządzeń z systemem Windows](windows-bulk-enroll.md)|
|**Profile urządzeń**|Niedostępne|Dostępne <br>[Co to są profile urządzeń w usłudze Microsoft Intune?](device-profiles.md)|
|**Rejestracja bez agenta**|Niedostępne |Dostępne<br>[Rejestrowanie urządzeń z systemem Windows](windows-enroll.md)|
|**Zarządzanie aktualizacjami oprogramowania**| Aktualizacje systemu Windows i aplikacji firmy Microsoft<br>[Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Sklep Microsoft dla firm z aktualizacjami zarówno systemu Windows 10, jak i aplikacji firmy Microsoft<br> [Konfigurowanie ustawień usługi Windows Update dla firm](windows-update-for-business-configure.md) |
|**Zarządzanie licencjami na oprogramowanie**|Dostępne <br>[Zarządzanie umowami licencyjnymi na oprogramowanie na komputerze z systemem Windows](manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|Sklep Microsoft dla firm (tylko aplikacje .appx)<br>[Zarządzanie aplikacjami zakupionymi w Sklepie Microsoft dla Firm](windows-store-for-business.md)|
|**Inventory** (Spis)|Dostępne <br>[Wyświetlanie spisu sprzętu i oprogramowania dla komputerów z systemem Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|Dostępne <br>[Monitorowanie informacji o aplikacji](apps-monitor.md)<br>[Co to jest zarządzanie urządzeniami](device-management.md)|
|**Zasady zapory systemu Windows**|Dostępne <br>[Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |Dostępne <br>[Zapora Windows Defender](endpoint-protection-windows-10.md#windows-defender-firewall)|
|**Ochrona przed złośliwym oprogramowaniem**|Ochrona punktu końcowego<br>[Ochrona komputerów z systemem Windows przy użyciu programu Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Usługa Windows Defender<br>[Włączanie usługi Windows Defender](advanced-threat-protection.md)|
|**Pomoc zdalna** |TeamViewer<br>[Żądanie i zapewnianie pomocy zdalnej dla komputerów z systemem Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [Używanie programu TeamViewer do zdalnego administrowania urządzeniami usługi Intune](device-profile-android-teamviewer.md) |
|**Wdrażanie aplikacji** | Niedostępne dla Sklepu Microsoft dla firm,<br>tylko pliki .exe, .appx i wieloplikowe instalatory .msi<br>[Dodawanie aplikacji dla komputerów z systemem Windows, na których jest uruchomione oprogramowanie klienckie usługi Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)|Dostępne dla aplikacji ze Sklepu Microsoft i aplikacji biznesowych<br>[Dodawanie aplikacji ze Sklepu Windows](store-apps-windows.md)<br>[Jak dodawać aplikacje biznesowe dla systemu Windows](lob-apps-windows.md)|
|**Ochrona aplikacji**|Niedostępne|Dostępne <br>[Co to są zasady ochrony aplikacji?](app-protection-policy.md)|
|**Zaświadczanie o kondycji**|Niedostępne|Dostępne|


### <a name="advantages-of-mdm-windows-pc-management"></a>Zalety zarządzania komputerami z systemem Windows z użyciem rozwiązania MDM
Zarządzanie komputerami z systemem Windows z użyciem nowoczesnego zarządzania urządzeniami mobilnymi ma następujące zalety:
- **Skalowalność** — zarządzanie MDM skaluje się dzięki zarządzaniu w chmurze w usłudze Intune. Oprogramowanie klienckie usługi Intune jest ograniczone do 7000 komputerów.
- **Prostota** — korzystanie z nowoczesnych możliwości zarządzania zawartych w systemie operacyjnym bez konieczności pobierania oprogramowania klienckiego
- **Spójność** — komputery z systemem Windows są zarządzane tak, jak wszystkie inne urządzenia mobilne w organizacji
<!-- - **Cloud optimization** - -->
