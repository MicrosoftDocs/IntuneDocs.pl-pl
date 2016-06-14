---
# required metadata

title: Wykorzystanie przepustowości sieci przez usługę Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wykorzystanie przepustowości sieci przez usługę Intune

Przed skonfigurowaniem usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] przejrzyj ten temat i inne wymagania wymienione w artykule [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Informacje zawarte w następujących sekcjach ułatwią zaplanowanie ruchu sieciowego dla klientów usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)].

## Średni ruch sieciowy
W poniższej tabeli przedstawiono częstotliwość przesyłania przez sieć typowych danych dla poszczególnych klientów oraz przybliżone ilości tych danych.

> [!NOTE]
> Komputery i urządzenia przenośne muszą co jakiś czas nawiązywać połączenie z Internetem, aby mogły otrzymywać niezbędne aktualizacje i zawartość z usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Czas potrzebny na pobranie aktualizacji lub zawartości jest różny, ale należy przyjąć, że urządzenia powinny być połączone z Internetem przez co najmniej godzinę każdego dnia.

|Typ zawartości|Przybliżony rozmiar|Częstotliwość i szczegóły|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] instalacja klienta<br /><br />**Poniżej przedstawiono dodatkowe wymagania dotyczące instalacji klienta usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]**|125 MB|**Jednorazowo**<br /><br />Rozmiar pobieranych plików zależy od systemu operacyjnego komputera klienta.|
|Pakiet rejestracji klienta|15 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent programu Endpoint Protection|65 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent programu Operations Manager|11 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent zasad|3 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Agent Pomocy zdalnej w ramach usługi Microsoft Easy Assist|6 MB|**Jednorazowo**<br /><br />Gdy są dostępne aktualizacje dla tego typu zawartości, może wystąpić konieczność pobrania dodatkowych plików.|
|Codzienne operacje klienta|6 MB|**Codziennie**<br /><br />Klient usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] regularnie komunikuje się z usługą [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu sprawdzenia dostępności aktualizacji i zasad oraz zgłoszenia stanu klienta do usługi.|
|Aktualizacje definicji złośliwego oprogramowania dla programu Endpoint Protection|Różnie<br /><br />Zwykle od 40 KB do 2 MB|**Codziennie**<br /><br />Maksymalnie trzy razy dziennie.|
|Aktualizacja aparatu programu Endpoint Protection|5 MB|**Raz na miesiąc**|
|Aktualizacje oprogramowania|Różnie<br /><br />Rozmiar pobieranych plików zależy od wdrażanych aktualizacji.|**Raz na miesiąc**<br /><br />Aktualizacje oprogramowania są zwykle wydawane w drugi wtorek miesiąca.<br /><br />Nowo zarejestrowany lub wdrożony komputer może generować większe obciążenie przepustowości sieci podczas pobierania pełnego zestawu wydanych aktualizacji.|
|Dodatki Service Pack|Różnie<br /><br />Rozmiar pobieranych plików zależy od wdrażanego dodatku Service Pack.|**Różnie**<br /><br />Zależy od daty wdrażania dodatków Service Pack.|
|Dystrybucja oprogramowania|Różnie<br /><br />Rozmiar pobieranych plików zależy od wdrażanego oprogramowania.|**Różnie**<br /><br />Zależy od daty wdrażania oprogramowania.|

## Sposoby na zmniejszanie wykorzystania przepustowości sieci
Przy użyciu następujących metod można zmniejszyć obciążenie przepustowości sieci dla klientów usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

### Używanie serwera proxy w celu buforowania żądań zawartości
Za pomocą serwera proxy umożliwiającego buforowanie zawartości można ograniczyć zduplikowane operacje pobierania plików. Pozwoli to na zmniejszenie obciążenia przepustowości sieci generowanego przez klientów, którzy wysyłają żądania pobrania zawartości z Internetu.

Serwer proxy pamięci podręcznej odbiera żądania zawartości od komputerów klienckich w sieci, pobiera tę zawartość z Internetu, a następnie buforuje zarówno odpowiedzi HTTP, jak i pobierane pliki binarne. Buforowane informacje są używane do obsługi kolejnych żądań wysyłanych z komputerów klienckich usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Poniżej przedstawiono typowe ustawienia serwera proxy, który buforuje zawartość dla klientów usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

|Ustawienie|Zalecana wartość|Szczegóły|
|-----------|---------------------|-----------|
|Rozmiar pamięci podręcznej|Od 5 GB do 30 GB|Wartość zależy od liczby komputerów klienckich w sieci i używanej konfiguracji. Aby zapobiec przedwczesnemu usuwaniu plików, dostosuj rozmiar pamięci podręcznej środowiska.|
|Rozmiar pamięci podręcznej pojedynczego pliku|950 MB|To ustawienie może nie być dostępne na wszystkich serwerach proxy pamięci podręcznej.|
|Typy buforowanych obiektów|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to pliki CAB pobierane przez usługę inteligentnego transferu w tle (Background Intelligent Transfer Service, BITS) za pośrednictwem protokołu HTTP.|
Informacje dotyczące korzystania z serwera proxy w celu buforowania zawartości można znaleźć w dokumentacji serwera proxy.

### Korzystanie z usługi inteligentnego transferu (BITS) w tle na komputerach
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] obsługuje korzystanie z usługi inteligentnego transferu w tle (BITS) na komputerach z systemem Windows w celu zmniejszenia obciążenia przepustowości sieci generowanego w określonych przedziałach czasowych. Zasady usługi BITS można skonfigurować na stronie **Przepustowość sieci** w obszarze zasad agenta usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Więcej informacji na temat korzystania z usługi BITS na komputerach z systemem Windows można znaleźć w artykule [Usługa inteligentnego transferu w tle (BITS)](http://technet.microsoft.com/library/bb968799.aspx) dostępnym w bibliotece TechNet.

### Korzystanie z usługi BranchCache na komputerach
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mogą używać usługi BranchCache w celu zmniejszenie ruchu w sieci rozległej (WAN). Usługa BranchCache jest obsługiwana w następujących systemach operacyjnych komputerów klienckich:

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

Aby można było korzystać z usługi BranchCache, musi być ona włączona na komputerze klienckim, który musi być skonfigurowany pod kątem **trybu rozproszonej pamięci podręcznej**..

Po zainstalowaniu na komputerze klienta usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] usługa BranchCache i tryb rozproszonej pamięci podręcznej są domyślnie włączane. Jednak jeśli zasady grupy na komputerze klienckim wyłączają usługę BranchCache, nie zostaną one przesłonione przez usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i usługa BranchCache pozostanie wyłączona na tym komputerze.

Jeśli chcesz używać usługi BranchCache, musisz skontaktować się z innymi administratorami w organizacji, którzy zarządzają zasadami grupy i zasadami zapory usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], aby zapobiec wdrażaniu przez nich zasad, które powodują wyłączenie usługi BranchCache lub wyjątków zapory. Aby uzyskać więcej informacji dotyczących usługi BranchCache, zobacz [Omówienie usługi BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

### Zobacz także
[Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)

<!--HONumber=May16_HO1-->


