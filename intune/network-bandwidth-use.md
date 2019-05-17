---
title: Wymagania dotyczące sieci i szczegóły przepustowości dla usługi Microsoft Intune
titleSuffix: ''
description: Zapoznaj się z wymaganiami dotyczącymi konfiguracji sieci i szczegółami przepustowości dla usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40f9ada715570de7b5b2f95292b7ed0d238242d2
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/11/2019
ms.locfileid: "59570796"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

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

Więcej informacji na temat korzystania z usługi BITS na komputerach z systemem Windows można znaleźć w artykule [Usługa inteligentnego transferu w tle (BITS)](http://technet.microsoft.com/library/bb968799.aspx) dostępnym w bibliotece TechNet.

### <a name="use-branchcache-on-computers"></a>Korzystanie z usługi BranchCache na komputerach
Klienci usługi Intune mogą używać usługi BranchCache w celu zmniejszenia ruchu w sieci rozległej (WAN). Usługa BranchCache jest obsługiwana w następujących systemach operacyjnych:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Aby można było korzystać z usługi BranchCache, musi być ona włączona na komputerze klienckim, który musi być skonfigurowany pod kątem **trybu rozproszonej pamięci podręcznej**.

Po zainstalowaniu na komputerach klienta usługi Intune usługa BranchCache i tryb rozproszonej pamięci podręcznej są włączane domyślnie. Jednak jeśli zasady grupy spowodowały wyłączenie usługi BranchCache, usługa Intune nie zastępuje tej zasady i usługa BranchCache pozostaje wyłączona.

Jeśli chcesz używać usługi BranchCache, musisz skontaktować się z innymi administratorami w organizacji, aby zarządzać zasadami grupy i zasadami zapory usługi Intune. Upewnij się, że nie wdrażają oni zasad, które powodują wyłączenie wyjątków usługi BranchCache lub zapory. Aby uzyskać więcej informacji dotyczących usługi BranchCache, zobacz [Omówienie usługi BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Wymagania dotyczące komunikacji sieciowej

Włącz komunikację sieciową między urządzeniami zarządzanymi i punktami końcowymi wymaganymi dla usług w chmurze.

Jako usługa działająca tylko w chmurze usługa Intune nie wymaga lokalnej infrastruktury, takiej jak serwery lub bramy.

Aby zarządzać urządzeniami za zaporami i serwerami proxy, należy włączyć komunikację na potrzeby usługi Intune.

- Serwer proxy musi obsługiwać zarówno protokół **HTTP (80)**, jak i **HTTPS (443)**, ponieważ klienci usługi Intune używają obu tych protokołów.
- W celu wykonywania pewnych zadań (takich jak pobieranie aktualizacji oprogramowania) usługa Intune wymaga nieautoryzowanego dostępu serwera proxy do witryny manage.microsoft.com

Można modyfikować ustawienia serwera proxy na poszczególnych komputerach klienckich. Można również zmieniać ustawienia dla wszystkich komputerów klienckich znajdujących się za określonym serwerem proxy za pomocą ustawień zasad grupy.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Zarządzane urządzenia wymagają zastosowania takiej konfiguracji, aby grupa **Wszyscy użytkownicy** miała dostęp do usług za pośrednictwem zapór.

Poniższe tabele zawierają listę portów i usług, do których uzyskuje dostęp klient usługi Intune:

|**Domeny**|**Adres IP**|
|---------------------|-----------|
|login.microsoftonline.com | Więcej informacji: [Adresy URL i zakresy adresów IP usługi Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Informacje o sieci urządzeń firmy Apple


|Sposób użycia|Nazwa hosta (adres IP/podsieć)|Protokół|Port|
|-----|--------|------|-------|
|Odbieranie powiadomień wypychanych z usługi Intune za pośrednictwem usługi Apple Push Notification Service (APNS). Zapoznaj się dokumentacją firmy Apple [tutaj](https://support.apple.com/en-us/HT203609)|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|Wysyłanie opinii do usługi Intune za pośrednictwem usługi Apple Push Notification Service (APNS)|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Pobieranie i wyświetlanie zawartości z serwerów firmy Apple|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|Komunikacja z serwerami usługi APNS|#-courier.push.apple.com (17.0.0.0/8)<br>„#” jest liczbą losową z zakresu od 0 do 50.|    TCP     |  5223 i 443  |
|Różne funkcje, w tym dostęp do sieci World Wide Web, sklepu iTunes, sklepu z aplikacjami systemu macOS, usługi iCloud, obsługi komunikatów itp. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 lub 443   |

Aby uzyskać więcej informacji, zobacz tematy [Porty TCP i UDP używane przez produkty Apple](https://support.apple.com/en-us/HT202944), [Informacje o połączeniach z serwerami systemów macOS i iOS oraz aplikacji iTunes oraz o procesach aplikacji iTunes działających w tle](https://support.apple.com/en-us/HT201999) i [Jeśli urządzenia klienckie z systemem macOS lub iOS nie otrzymują powiadomień w trybie push Apple](https://support.apple.com/en-us/HT203609) w dokumentacji firmy Apple.
