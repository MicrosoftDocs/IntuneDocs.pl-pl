---
title: "Użycie przepustowości sieci przez usługę Intune | Microsoft Docs"
description: "wykorzystanie przepustowości sieci przez usługę Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 5d32729fe5c7188b018e4baad99e4d35b8977086
ms.contentlocale: pl-pl
ms.lasthandoff: 05/04/2017


---

# <a name="intune-network-bandwidth-use"></a>Wykorzystanie przepustowości sieci przez usługę Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Niniejsze wskazówki pomagają administratorom usługi Intune poznać wymagania sieciowe dla usługi Intune. Informacje te zawierają wymagania dotyczące przepustowości oraz adres IP i ustawienia portu potrzebne do ustawień serwera proxy.

## <a name="average-network-traffic"></a>Średni ruch sieciowy
W tej tabeli przedstawiono częstotliwość przesyłania przez sieć typowych danych dla poszczególnych klientów oraz przybliżone ilości tych danych.

> [!NOTE]
> Komputery i urządzenia przenośne muszą co jakiś czas nawiązywać połączenie z Internetem, aby otrzymywać niezbędne aktualizacje i zawartość z usługi Intune. Czas potrzebny na pobranie aktualizacji lub zawartości jest różny, ale należy przyjąć, że urządzenia powinny być połączone z Internetem przez co najmniej godzinę każdego dnia.

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
Za pomocą serwera proxy umożliwiającego buforowanie zawartości można ograniczyć zduplikowane operacje pobierania plików. Pozwoli to na zmniejszenie obciążenia przepustowości sieci generowanego przez klientów, którzy wysyłają żądania pobrania zawartości z Internetu.

Serwer proxy pamięci podręcznej odbiera żądania zawartości od komputerów klienckich w sieci, pobiera tę zawartość z Internetu, a następnie buforuje zarówno odpowiedzi HTTP, jak i pobierane pliki binarne. Buforowane informacje są używane do obsługi kolejnych żądań wysyłanych z komputerów klienckich usługi Intune.

Poniżej przedstawiono typowe ustawienia serwera proxy, który buforuje zawartość dla klientów usługi Intune.

|Ustawienie|Zalecana wartość|Szczegóły|
|-----------|---------------------|-----------|
|Rozmiar pamięci podręcznej|Od 5 GB do 30 GB|Wartość zależy od liczby komputerów klienckich w sieci i używanej konfiguracji. Aby zapobiec przedwczesnemu usuwaniu plików, dostosuj rozmiar pamięci podręcznej środowiska.|
|Rozmiar pamięci podręcznej pojedynczego pliku|950 MB|To ustawienie może nie być dostępne na wszystkich serwerach proxy pamięci podręcznej.|
|Typy buforowanych obiektów|HTTP<br /><br />HTTPS<br /><br />BITS|Pakiety usługi Intune to pliki CAB pobierane przez Usługę inteligentnego transferu w tle (BITS) za pośrednictwem protokołu HTTP.|
Informacje dotyczące korzystania z serwera proxy w celu buforowania zawartości można znaleźć w dokumentacji serwera proxy.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Korzystanie z usługi inteligentnego transferu (BITS) w tle na komputerach
Usługa Intune obsługuje korzystanie z Usługi inteligentnego transferu w tle (BITS) na komputerach z systemem Windows w celu zmniejszenia obciążenia przepustowości sieci generowanego w konfigurowanych przedziałach czasowych. Zasady usługi BITS można skonfigurować na stronie **Przepustowość sieci** w obszarze zasad agenta usługi Intune.

Więcej informacji na temat korzystania z usługi BITS na komputerach z systemem Windows można znaleźć w artykule [Usługa inteligentnego transferu w tle (BITS)](http://technet.microsoft.com/library/bb968799.aspx) dostępnym w bibliotece TechNet.

### <a name="use-branchcache-on-computers"></a>Korzystanie z usługi BranchCache na komputerach
Klienci usługi Intune mogą używać usługi BranchCache w celu zmniejszenia ruchu w sieci rozległej (WAN). Usługa BranchCache jest obsługiwana w następujących systemach operacyjnych komputerów klienckich:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Aby można było korzystać z usługi BranchCache, musi być ona włączona na komputerze klienckim, który musi być skonfigurowany pod kątem **trybu rozproszonej pamięci podręcznej**.

Po zainstalowaniu na komputerze klienta usługi Intune usługa BranchCache i tryb rozproszonej pamięci podręcznej są domyślnie włączone. Jednak jeśli zasady grupy na komputerze klienckim wyłączają usługę BranchCache, nie zostaną one przesłonięte przez usługę Intune i usługa BranchCache pozostanie wyłączona na tym komputerze.

Jeśli chcesz używać usługi BranchCache, musisz skontaktować się z innymi administratorami w organizacji, którzy zarządzają zasadami grupy i zasadami zapory usługi Intune, aby zapobiec wdrażaniu przez nich zasad, które powodują wyłączenie usługi BranchCache lub wyjątków zapory. Aby uzyskać więcej informacji dotyczących usługi BranchCache, zobacz [Omówienie usługi BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Wymagania dotyczące komunikacji sieciowej

Należy włączyć komunikację sieciową między urządzeniami zarządzanymi i używanymi do zarządzania subskrypcją usługi Intune oraz witrynami sieci Web wymaganymi dla usług w chmurze.

Usługa Intune nie korzysta z infrastruktury lokalnej, takiej jak serwery z oprogramowaniem usługi Intune, ale można używać takiej infrastruktury, w tym narzędzi do synchronizowania programu Exchange i usługi Active Directory.

Aby zarządzać komputerami, które znajdują się za zaporami i serwerami proxy, należy skonfigurować zapory i serwery proxy w celu zezwalania na komunikację z usługą Intune. Aby zarządzać komputerami, które znajdują się za serwerem proxy:

-   Serwer proxy musi obsługiwać zarówno protokół **HTTP (80)**, jak i **HTTPS (443)**, ponieważ klienci usługi Intune używają obu tych protokołów.
-   Usługa Intune obsługuje nieuwierzytelnione serwery proxy.

Można zmodyfikować ustawienia serwerów proxy na poszczególnych komputerach klienckich albo użyć zasad grupy w celu zmiany ustawień dla wszystkich komputerów klienckich znajdujących się za określonym serwerem proxy.

Zarządzane urządzenia wymagają zastosowania takiej konfiguracji, aby grupa **Wszyscy użytkownicy** miała dostęp do usług za pośrednictwem zapór.

Poniższe tabele zawierają listę portów i usług, do których uzyskuje dostęp klient usługi Intune:

|**Domeny**|**Adres IP**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |    13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|

