---
title: Wymagania dotyczące sieci i szczegóły przepustowości dla usługi Microsoft Intune
titleSuffix: ''
description: Zapoznaj się z wymaganiami dotyczącymi konfiguracji sieci i szczegółami przepustowości dla usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a3ecf2872832af6199620863a05b4275731db5c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505234"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Dzięki tym informacjom można zrozumieć wymagania dotyczące przepustowości odnoszące się do wdrożeń usługi Intune.

## <a name="average-network-traffic"></a>Średni ruch sieciowy
W tej tabeli przedstawiono częstotliwość przesyłania przez sieć typowych danych dla poszczególnych klientów oraz przybliżone ilości tych danych.

> [!NOTE]
> Aby zapewnić, że urządzenia będą otrzymywać aktualizacje i zawartość z usługi Intune, należy okresowo łączyć je z Internetem. Czas wymagany do pobrania aktualizacji lub zawartości jest różny, ale urządzenia powinny być połączone z Internetem przez co najmniej godzinę każdego dnia.

|Typ zawartości|Przybliżony rozmiar|Częstotliwość i szczegóły|
|----------------|--------------------|-------------------------|
|Instalacja klienta usługi Intune<br /><br />**Poniżej przedstawiono dodatkowe wymagania dotyczące instalacji klienta usługi Intune**|125 MB|**Jednorazowo**<br /><br />Rozmiar pobieranych plików zależy od systemu operacyjnego komputera klienta.|
|Pakiet rejestracji klienta|15 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent programu Endpoint Protection|65 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent programu Operations Manager|11 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent zasad|3 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent Pomocy zdalnej w ramach usługi Microsoft Easy Assist|6 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Codzienne operacje klienta|6 MB|**Codziennie**<br /><br />Klient usługi Intune regularnie komunikuje się z usługą Intune w celu sprawdzenia dostępności aktualizacji i zasad oraz zgłoszenia stanu klienta do usługi.|
|Aktualizacje definicji złośliwego oprogramowania dla programu Endpoint Protection|Różnie<br /><br />Zwykle od 40 KB do 2 MB|**Codziennie**<br /><br />Maksymalnie trzy razy dziennie.|
|Aktualizacja aparatu programu Endpoint Protection|5 MB|**Raz na miesiąc**|
|Aktualizacje oprogramowania|Różnie<br /><br />Rozmiar pobieranych plików zależy od wdrażanych aktualizacji.|**Raz na miesiąc**<br /><br />Aktualizacje oprogramowania są zwykle wydawane w drugi wtorek miesiąca.<br /><br />Nowo zarejestrowany lub wdrożony komputer może generować większe obciążenie przepustowości sieci podczas pobierania pełnego zestawu wydanych aktualizacji.|
|Dodatki Service Pack|Różnie<br /><br />Rozmiar pobieranych plików zależy od wdrażanego dodatku Service Pack.|**Różnie**<br /><br />Zależy od daty wdrażania dodatków Service Pack.|
|Dystrybucja oprogramowania|Różnie<br /><br />Rozmiar pobieranych plików zależy od wdrażanego oprogramowania.|**Różnie**<br /><br />Zależy od daty wdrażania oprogramowania.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Sposoby na zmniejszanie wykorzystania przepustowości sieci
Przy użyciu jednej lub kilku poniższych metod można zmniejszyć użycie przepustowości sieci dla klientów usługi Intune.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Używanie serwera proxy w celu buforowania żądań zawartości
Serwer proxy umożliwia buforowanie zawartości w celu ograniczenia zduplikowanych operacji pobierania plików i zmniejszenia obciążenia przepustowości sieci związanego z zawartością z Internetu.

Serwer proxy pamięci podręcznej, który odbiera żądania zawartości od klientów, może pobierać tę zawartość i buforować odpowiedzi i pliki do pobrania z Internetu. Serwer używa buforowanych danych do obsługi kolejnych żądań od klientów.

Poniżej przedstawiono typowe ustawienia serwera proxy, który buforuje zawartość dla klientów usługi Intune.


|          Ustawienie           |           Zalecana wartość           |                                                                                                  Szczegóły                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Rozmiar pamięci podręcznej         |             Od 5 GB do 30 GB             | Wartość zależy od liczby komputerów klienckich w sieci i używanej konfiguracji. Aby zapobiec przedwczesnemu usuwaniu plików, dostosuj rozmiar pamięci podręcznej środowiska. |
| Rozmiar pamięci podręcznej pojedynczego pliku |                950 MB                 |                                                                     To ustawienie może nie być dostępne na wszystkich serwerach proxy pamięci podręcznej.                                                                     |
|   Typy buforowanych obiektów    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Pakiety usługi Intune to pliki CAB pobierane przez Usługę inteligentnego transferu w tle (BITS) za pośrednictwem protokołu HTTP.                                               |
> [!NOTE]
> Jeśli używasz serwera proxy w celu buforowania żądań dotyczących zawartości, komunikacja jest szyfrowana tylko między klientem i serwerem proxy oraz od serwera proxy do usługi Intune. Połączenie od klienta do usługi Intune nie będzie kompleksowo szyfrowane.

Informacje dotyczące korzystania z serwera proxy w celu buforowania zawartości można znaleźć w dokumentacji serwera proxy.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Korzystanie z usługi inteligentnego transferu (BITS) w tle na komputerach
W trakcie skonfigurowanych godzin można użyć usługi BITS na komputerze z systemem Windows w celu zmniejszenia obciążenia przepustowości sieci. Zasady usługi BITS można skonfigurować na stronie **Przepustowość sieci** w obszarze zasad agenta usługi Intune.

> [!NOTE]
> W przypadku zarządzania oprogramowaniem MDM w systemie Windows tylko interfejs zarządzania systemem operacyjnym dla typu aplikacji MobileMSI używa usługi BITS do pobierania. Pakiet AppX/MsiX używa własnego stosu pobierania innego niż usługa BITS, a aplikacje Win32 w obrębie agenta usługi Intune używają optymalizacji dostarczania, a nie usługi BITS.

Więcej informacji na temat korzystania z usługi BITS na komputerach z systemem Windows można znaleźć w artykule [Usługa inteligentnego transferu w tle (BITS)](https://technet.microsoft.com/library/bb968799.aspx) dostępnym w bibliotece TechNet.

### <a name="delivery-optimization"></a>Optymalizacja dostarczania
Optymalizacja dostarczania umożliwia użycie usługi Intune w celu ograniczenia zużycia przepustowości podczas pobierania aplikacji i aktualizacji przez urządzenie z systemem Windows 10. W przypadku użycia samoorganizującego rozwiązania rozproszonej pamięci podręcznej pliki do pobrania mogą być pobierane z tradycyjnych serwerów oraz źródeł alternatywnych (takich jak sieci równorzędne).

Aby zapoznać się z pełną listą wersji systemu Windows 10 i typów zawartości obsługiwanych przez Optymalizację dostarczania, zobacz artykuł [Optymalizacja dostarczania aktualizacji systemu Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#requirements).

[Optymalizację dostarczania można skonfigurować](../configuration/delivery-optimization-settings.md) w ramach profilów konfiguracji urządzenia.


### <a name="use-branchcache-on-computers"></a>Korzystanie z usługi BranchCache na komputerach
Klienci usługi Intune mogą używać usługi BranchCache w celu zmniejszenia ruchu w sieci rozległej (WAN). Usługa BranchCache jest obsługiwana w następujących systemach operacyjnych:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Aby można było korzystać z usługi BranchCache, musi być ona włączona na komputerze klienckim, który musi być skonfigurowany pod kątem **trybu rozproszonej pamięci podręcznej**.

Po zainstalowaniu na komputerach klienta usługi Intune usługa BranchCache i tryb rozproszonej pamięci podręcznej są włączane domyślnie. Jednak jeśli zasady grupy spowodowały wyłączenie usługi BranchCache, usługa Intune nie zastępuje tej zasady i usługa BranchCache pozostaje wyłączona.

Jeśli chcesz używać usługi BranchCache, musisz skontaktować się z innymi administratorami w organizacji, aby zarządzać zasadami grupy i zasadami zapory usługi Intune. Upewnij się, że nie wdrażają oni zasad, które powodują wyłączenie wyjątków usługi BranchCache lub zapory. Aby uzyskać więcej informacji dotyczących usługi BranchCache, zobacz [Omówienie usługi BranchCache](https://technet.microsoft.com/library/hh831696.aspx).

> [!NOTE]
> Usługi Microsoft Intune można użyć do zarządzania komputerami z systemem Windows albo [jako urządzeniami mobilnymi z wykorzystaniem zarządzania urządzeniami mobilnymi (MDM)](../enrollment/windows-enroll.md), albo jako komputerami z wykorzystaniem oprogramowania klienckiego usługi Intune. Firma Microsoft zaleca, aby klienci [używali rozwiązania MDM do zarządzania](../enrollment/windows-enroll.md) zawsze, gdy jest to możliwe. Podczas zarządzania w ten sposób usługa BranchCache nie jest obsługiwana. Aby uzyskać więcej informacji, zobacz temat [Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi](../pc-management-comparison.md).


## <a name="next-steps"></a>Następne kroki

[Zapoznaj się z punktami końcowymi usługi Intune](../intune-endpoints.md)

