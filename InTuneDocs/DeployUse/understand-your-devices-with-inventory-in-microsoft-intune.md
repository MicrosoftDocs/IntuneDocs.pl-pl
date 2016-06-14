---
# required metadata

title: Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune
Usługa Microsoft Intune umożliwia przeglądanie spisu zarejestrowanych urządzeń i komputerów z systemem Windows, na których zostało uruchomione oprogramowanie klienckie usługi Intune.

## Jakie informacje są zbierane z zarejestrowanych urządzeń?
Aby wyświetlić spis pobrany przez urządzenia przenośne, uruchom [raporty dotyczące spisu urządzeń przenośnych](understand-microsoft-intune-operations-by-using-reports.md). Usługa Intune zbiera następujący spis z urządzeń przenośnych:

|Właściwość|Zbierane przez|
|------------|-----------------------|
|**Nazwa**|Wszystkie urządzenia|
|**System operacyjny**|Wszystkie urządzenia|
|**Producent**|Wszystkie urządzenia|
|**Model**|Wszystkie urządzenia|
|**Kanał zarządzania**|Wszystkie urządzenia|
|**Rejestracja w usłudze AAD**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Zgodny**|Wszystkie urządzenia|
|**Aktywowano program EAS**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Identyfikator aktywacji EAS**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Godzina aktywacji EAS**|Wszystkie urządzenia z wyjątkiem systemu Mac OS X|
|**Stan zarządzania**|Wszystkie urządzenia|
|**Adres e-mail**|Wszystkie urządzenia|
|**Identyfikator programu Exchange ActiveSync**|Wszystkie urządzenia|
|**Urządzenia, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta administratora**|Tylko urządzenia z systemami iOS lub Android|
|**Unikatowy identyfikator urządzenia**|Wszystkie urządzenia z wyjątkiem urządzeń z programem Exchange ActiveSync|
|**Numer seryjny**|Urządzenia z systemami iOS, Mac OS X, Android, Windows 8.1 lub Windows 10|
|**Całkowita ilość miejsca**|Urządzenia z systemami iOS, Mac OS X, Windows 8.1 lub Windows 10|
|**Ilość wolnego miejsca**|Urządzenia z systemami iOS, Mac OS X, Windows 8.1 lub Windows 10|
|**Numer telefonu**<br>Telefony skategoryzowane jako firmowe są identyfikowane przez pełny numer telefonu na przykład przy uruchomieniu raportu inwentaryzacyjnego urządzenia przenośnego. Numery telefonów BYOD są nadal maskowane symbolami &#42;, wyświetlane są tylko 4 ostatnie cyfry.|Urządzenia z systemami iOS, Android lub Windows Phone|
|**IMEI**|Urządzenia z programem Exchange ActiveSync albo systemami iOS, Android lub Windows Phone|
|**MEID**<br>Identyfikator sprzętu przenośnego|Tylko urządzenia z systemem iOS|
|**Wi-Fi MAC**|Wszystkie urządzenia z wyjątkiem urządzeń z programem Exchange ActiveSync|
|**Nazwa operatora**|Tylko urządzenia z systemami iOS lub Android|
|**Technologia sieci komórkowej**|Tylko urządzenia z systemami iOS lub Android|
|**Nadzorowane**|Tylko urządzenia z systemem iOS|
|**Stan blokady aktywacji**|Tylko urządzenia z systemem iOS|
|**Data zarejestrowania**|Wszystkie urządzenia|
|**Ostatnia aktualizacja**|Wszystkie urządzenia|
|**Adres MAC Ethernet**|Tylko urządzenia z systemem Mac OS X|
|**Włączenie blokady aktywacji**|Tylko urządzenia z systemem iOS|
|**Włączenie szyfrowania**|Wszystkie urządzenia|

## Jakie informacje są zbierane z komputerów z systemem Windows?
> [!IMPORTANT]
> Ta sekcja dotyczy tylko komputerów z systemem Windows, na których uruchomiono oprogramowanie klienckie usługi Intune dla komputerów z systemem Windows.

Aby wyświetlić spis zebrany przez komputery z systemem Windows, uruchom [Raporty dotyczące spisu komputerów](understand-microsoft-intune-operations-by-using-reports.md). Usługa Intune zbiera następujący spis z komputerów z systemem Windows:

-   **Nazwa**

-   **Typ podstawy**

-   **Producent**

-   **Model**

-   **System operacyjny**

-   **Wersja modułu TPM**

-   **Całkowite miejsce na dysku**

-   **Zajęte miejsce na dysku**

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

### Zobacz też
[Monitorowanie i raporty w usłudze Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO1-->


