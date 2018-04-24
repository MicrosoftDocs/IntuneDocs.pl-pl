---
title: Porównanie opcji zarządzania komputerem z systemem Windows
description: Rejestrowanie urządzeń firmowych z systemem iOS przy użyciu programu Apple Device Enrollment Program (DEP) lub narzędzia Apple Configurator
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c760f9c76e54c0b5f9eb037414870ab1c8943803
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Organizacje mogą użyć usługi Microsoft Intune do zarządzania komputerami z systemem Windows albo jako urządzeniami mobilnymi z wykorzystaniem zarządzania urządzeniami mobilnymi (MDM), albo jako komputerami z wykorzystaniem oprogramowania klienckiego usługi Intune.  Firma Microsoft zaleca, aby klienci używali rozwiązania MDM do zarządzania zawsze, gdy jest to możliwe. Aby lepiej zrozumieć różnice między tymi dwiema opcjami zarządzania, zapoznaj się z poniższą tabelą.

|**Możliwość / scenariusz** |**Komputer z systemem Windows jako komputer**<br>Oprogramowanie klienckie usługi Intune | **Komputer z systemem Windows jako urządzenie mobilne**<br>ZARZĄDZANIE URZĄDZENIAMI PRZENOŚNYMI |
|--------------|-------------------------------|-------------------------------|
|**Systemy operacyjne** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Pomoc techniczna portalu usługi Intune** |[Konsola programu Silverlight](https://manage.microsoft.com)|[Portal Azure](https://portal.azure.com) |
|**Dostęp warunkowy**|Niedostępne|Dostępne <br>[Co to jest dostęp warunkowy?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Rejestrowanie zbiorcze**|Niedostępne|Dostępne <br>[Rejestracja zbiorcza urządzeń z systemem Windows](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Profile urządzeń**|Niedostępne|Dostępne <br>[Co to są profile urządzeń w usłudze Microsoft Intune?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Rejestracja bez agenta**|Niedostępne |Dostępne<br>[Rejestrowanie urządzeń z systemem Windows](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Zarządzanie aktualizacjami oprogramowania**| Aktualizacje systemu Windows i aplikacji firmy Microsoft<br>[Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Sklep Microsoft dla firm z aktualizacjami zarówno systemu Windows 10, jak i aplikacji firmy Microsoft<br> [Konfigurowanie ustawień usługi Windows Update dla firm](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Zarządzanie licencjami na oprogramowanie**|Dostępne <br>[Zarządzanie umowami licencyjnymi na oprogramowanie na komputerze z systemem Windows](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Sklep Microsoft dla firm (tylko aplikacje .appx)<br>[Zarządzanie aplikacjami zakupionymi w Sklepie Microsoft dla Firm](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Inventory** (Spis)|Dostępne <br>[Wyświetlanie spisu sprzętu i oprogramowania dla komputerów z systemem Windows](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Dostępne <br>[Monitorowanie informacji o aplikacji](https://docs.microsoft.com/intune/apps-monitor)<br>[Co to jest zarządzanie urządzeniami](https://docs.microsoft.com/intune/device-management)|
|**Zasady zapory systemu Windows**|Dostępne <br>[Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Niedostępne|
|**Ochrona przed złośliwym oprogramowaniem**|Ochrona punktu końcowego<br>[Ochrona komputerów z systemem Windows przy użyciu programu Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Usługa Windows Defender<br>[Ustawienia usługi Windows Defender](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Pomoc zdalna** |TeamViewer<br>[Żądanie i zapewnianie pomocy zdalnej dla komputerów z systemem Windows](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Niedostępne |
|**Wdrażanie aplikacji** | Niedostępne dla Sklepu Microsoft dla firm,<br>tylko pliki .exe, .appx i wieloplikowe instalatory .msi<br>[Dodawanie aplikacji dla komputerów z systemem Windows, na których jest uruchomione oprogramowanie klienckie usługi Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Dostępne dla aplikacji ze Sklepu Microsoft i aplikacji biznesowych<br>[Dodawanie aplikacji ze Sklepu Windows](https://docs.microsoft.com/intune/store-apps-windows)<br>[Jak dodawać aplikacje biznesowe dla systemu Windows](https://docs.microsoft.com/intune/lob-apps-windows)|
|**Ochrona aplikacji**|Niedostępne|Dostępne <br>[Co to są zasady ochrony aplikacji?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Zaświadczanie o kondycji**|Niedostępne|Dostępne|


### <a name="advantages-of-mdm-windows-pc-management"></a>Zalety zarządzania komputerami z systemem Windows z użyciem rozwiązania MDM
Zarządzanie komputerami z systemem Windows z użyciem nowoczesnego zarządzania urządzeniami mobilnymi ma następujące zalety:
- **Skalowalność** — zarządzanie MDM skaluje się dzięki zarządzaniu w chmurze w usłudze Intune. Oprogramowanie klienckie usługi Intune jest ograniczone do 7000 komputerów.
- **Prostota** — korzystanie z nowoczesnych możliwości zarządzania zawartych w systemie operacyjnym bez konieczności pobierania oprogramowania klienckiego
- **Spójność** — komputery z systemem Windows są zarządzane tak, jak wszystkie inne urządzenia mobilne w organizacji
<!-- - **Cloud optimization** - -->
