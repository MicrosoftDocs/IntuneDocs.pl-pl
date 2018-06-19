---
title: Zrozumienie informacji o urządzeniach dzięki spisowi
description: Użyj usługi Intune do wyświetlenia informacji o sprzęcie zarządzanych urządzeń.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/05/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e50a7329512e6b57eb5486792669b7cd102eebdb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31023397"
---
# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a>Uzyskiwanie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune umożliwia przeglądanie spisu zarejestrowanych urządzeń i komputerów z systemem Windows, na których zostało uruchomione oprogramowanie klienckie usługi Intune.
Usługa Intune zwykle zbiera spis z zarządzanych urządzeń co 7 dni. W związku z tym może występować opóźnienie, zanim w raportach zostaną wyświetlone wyniki ostatnich zmian dotyczących urządzeń, na przykład zmiany nazwy urządzenia lub ilości wolnego miejsca.

## <a name="whats-collected-from-enrolled-devices"></a>Jakie informacje są zbierane z zarejestrowanych urządzeń?
Aby wyświetlić spis zebrany przez urządzenia przenośne, uruchom [raporty dotyczące spisu urządzeń przenośnych](understand-microsoft-intune-operations-by-using-reports.md). Usługa Intune zbiera następujący spis z zarejestrowanych urządzeń:

|Właściwość|Zbierane przez|
|------------|-----------------------|
|**Nazwa**|Wszystkie urządzenia|
|**System operacyjny**|Wszystkie urządzenia|
|**Producent**|Wszystkie urządzenia|
|**Model**|Wszystkie urządzenia|
|**Kanał zarządzania**|Wszystkie urządzenia|
|**Zarejestrowane w usłudze AAD**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Zgodne**|Wszystkie urządzenia|
|**Aktywowano program EAS**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Identyfikator aktywacji programu EAS**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Czas aktywacji programu EAS**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Stan zarządzania**|Wszystkie urządzenia|
|**Adres e-mail**|Wszystkie urządzenia|
|**Identyfikator programu Exchange ActiveSync**|Wszystkie urządzenia|
|**Urządzenia, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta administratora**|Tylko urządzenia z systemem iOS lub Android|
|**Unikatowy identyfikator urządzenia**|Wszystkie urządzenia z wyjątkiem urządzeń z programem Exchange ActiveSync|
|**Numer seryjny**|Urządzenia z systemami iOS, Mac OS X, Android, Windows 8.1 i Windows 10|
|**Całkowita ilość miejsca**|Urządzenia i urządzenia przenośne z systemami iOS, Mac OS X, Windows 8.1 i Windows 10|
|**Ilość wolnego miejsca**|Urządzenia z systemami iOS, Mac OS X, Windows 8.1 i Windows 10|
|**Numer telefonu**<br>Telefony skategoryzowane jako firmowe są identyfikowane przez pełny numer telefonu (na przykład przy uruchomieniu raportu dotyczącego spisu urządzeń przenośnych). Numery telefonów BYOD są maskowane symbolami &#42; i tylko 4 ostatnie cyfry są wyświetlane.|Urządzenia z systemami iOS, Android i Windows Phone|
|**IMEI**|Urządzenia z programem Exchange ActiveSync albo systemem iOS, Android lub Windows Phone|
|**MEID**<br>Identyfikator sprzętu przenośnego|Tylko urządzenia z systemem iOS|
|**Wi-Fi MAC**|Wszystkie urządzenia z wyjątkiem urządzeń z programem Exchange ActiveSync|
|**Nazwa operatora**|Tylko urządzenia z systemem iOS lub Android|
|**Technologia sieci komórkowej**|Tylko urządzenia z systemem iOS lub Android|
|**Nadzorowane**|Tylko urządzenia z systemem iOS|
|**Stan blokady aktywacji**|Tylko urządzenia z systemem iOS|
|**Data zarejestrowania**|Wszystkie urządzenia|
|**Ostatnia aktualizacja**|Wszystkie urządzenia|
|**Adres Ethernet MAC**|Tylko urządzenia z systemem Mac OS X|
|**Włączona blokada aktywacji**|Tylko urządzenia z systemem iOS|
|**Włączone szyfrowanie**|Wszystkie urządzenia|

>[!NOTE]
>Niektóre z powyższych elementów mogą nie być zbierane w zależności od operatora używanego z urządzeniem.

## <a name="whats-collected-from-windows-pcs"></a>Co jest zbierane z komputerów z systemem Windows?
> [!IMPORTANT]
> Ta sekcja dotyczy tylko komputerów z systemem Windows, na których uruchomiono oprogramowanie klienckie usługi Intune dla komputerów z systemem Windows.

Aby wyświetlić spis zebrany przez komputery z systemem Windows, uruchom [raporty dotyczące spisu komputerów](understand-microsoft-intune-operations-by-using-reports.md). Usługa Intune zbiera następujący spis z komputerów z systemem Windows:

-   **Nazwa**

-   **Typ podstawy**

-   **Producent**

-   **Model**

-   **System operacyjny**

-   **Wersja modułu TPM**

-   **Całkowite miejsce na dysku**

-   **Używane miejsce na dysku**

-   **Wolne miejsce na dysku**

-   **Nazwa dysku systemu operacyjnego**

-   **Miejsce na dysku systemu operacyjnego**

-   **Wolne miejsce na dysku systemu operacyjnego**

-   **Pamięć fizyczna**

-   **Nazwa procesora**

-   **Architektura procesora**

-   **Szybkość procesora CPU**

-   **Adres IP**

-   **Numer seryjny**

-   **Nazwa użytkownika, który ostatnio się logował**

-   **Przypisany użytkownik**

-   **Ostatnia aktualizacja**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
