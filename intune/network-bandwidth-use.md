---
title: "Wykorzystanie przepustowości sieci przez usługę Intune"
description: "wykorzystanie przepustowości sieci przez usługę Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/16/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f2055a0949921b52937af18bf1cd73286bf046cf
ms.sourcegitcommit: d6dc1211e9128c2e0608542b72d1caa4d6ba691d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2018
---
# <a name="intune-network-bandwidth-use"></a>Wykorzystanie przepustowości sieci przez usługę Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Niniejsze wskazówki pomagają administratorom usługi Intune poznać wymagania sieciowe dla usługi Intune. Informacje te zawierają wymagania dotyczące przepustowości oraz adres IP i ustawienia portu potrzebne do ustawień serwera proxy.

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
Klienci usługi Intune mogą używać usługi BranchCache w celu zmniejszenia ruchu w sieci rozległej (WAN). Usługa BranchCache jest obsługiwana w następujących systemach operacyjnych:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Aby można było korzystać z usługi BranchCache, musi być ona włączona na komputerze klienckim, który musi być skonfigurowany pod kątem **trybu rozproszonej pamięci podręcznej**.

Po zainstalowaniu na komputerach klienta usługi Intune usługa BranchCache i tryb rozproszonej pamięci podręcznej są domyślnie włączone. Jednak jeśli zasady grupy spowodowały wyłączenie usługi BranchCache, usługa Intune nie zastępuje tej zasady i usługa BranchCache pozostaje wyłączona.

Jeśli chcesz używać usługi BranchCache, musisz skontaktować się z innymi administratorami w organizacji, aby zarządzać zasadami grupy i zasadami zapory usługi Intune. Upewnij się, że nie wdrażają oni zasad, które powodują wyłączenie wyjątków usługi BranchCache lub zapory. Aby uzyskać więcej informacji dotyczących usługi BranchCache, zobacz [Omówienie usługi BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Wymagania dotyczące komunikacji sieciowej

Włącz komunikację sieciową między urządzeniami zarządzanymi i witrynami internetowymi wymaganymi dla usług w chmurze.

Usługa Intune nie korzysta z infrastruktury lokalnej, takiej jak serwery z oprogramowaniem usługi Intune, ale można używać takiej infrastruktury, w tym narzędzi do synchronizowania programu Exchange i usługi Active Directory.

Aby zarządzać komputerami za zaporami i serwerami proxy, należy włączyć komunikację na potrzeby usługi Intune.

-   Serwer proxy musi obsługiwać zarówno protokół **HTTP (80)**, jak i **HTTPS (443)**, ponieważ klienci usługi Intune używają obu tych protokołów.
-   Usługa Intune wymaga nieautoryzowanego dostępu serwera proxy do witryny manage.microsoft.com w celu wykonywania pewnych zadań, takich jak pobieranie oprogramowania i aktualizacji

Można zmodyfikować ustawienia serwerów proxy na poszczególnych komputerach klienckich albo użyć zasad grupy w celu zmiany ustawień dla wszystkich komputerów klienckich znajdujących się za określonym serwerem proxy.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Zarządzane urządzenia wymagają zastosowania takiej konfiguracji, aby grupa **Wszyscy użytkownicy** miała dostęp do usług za pośrednictwem zapór.

Poniższe tabele zawierają listę portów i usług, do których uzyskuje dostęp klient usługi Intune:

|**Domeny**|**Adres IP**|
|---------------------|-----------|
|login.microsoftonline.com | Więcej informacji: [Adresy URL i zakresy adresów IP usługi Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
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
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|

### <a name="apple-device-network-information"></a>Informacje o sieci urządzeń firmy Apple
| Nazwa hosta  | Adres URL (adres IP/podsieć) | Protokół | Port | Urządzenie |
| --- | --- | --- | --- | --- |
|  Konsola administracyjna  | gateway.push.apple.com (17.0.0.0/8) | TCP | 2195 | Apple iOS i macOS |
| Konsola administracyjna  | feedback.push.apple.com(17.0.0.0/8) | TCP | 2196 | Apple iOS i macOS |
| Konsola administracyjna  | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple iOS i macOS  |
| Serwer PI  | gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8) | TCP | 2195, 2196 | Do obsługi wiadomości w chmurze dla systemu iOS i macOS firmy Apple. |
| Usługi urządzenia  | gateway.push.apple.com | TCP | 2195 | Apple  |
| Usługi urządzenia  | feedback.push.apple.com | TCP | 2196 | Apple  |
| Usługi urządzenia  | Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple  |
| Urządzenia (Internet/Wi-Fi) | #-courier.push.apple.com(17.0.0.0/8) | TCP | 5223 i 443 | Tylko Apple. &#39;#&#39; jest liczbę losową z zakresu od 0 do 200. |
| Urządzenia (Internet/Wi-Fi) | phobos.apple.comocsp.apple.comax.itunes.apple.com | HTTP/HTTPS | 80 lub 443 | Tylko Apple |
