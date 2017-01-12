---
title: "Użycie przepustowości sieci przez usługę Intune | Microsoft Docs"
description: "wykorzystanie przepustowości sieci przez usługę Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e13a9c426e07ebb2443bd403d1a5c7274afd387e
ms.openlocfilehash: 213e2e43635dd64cd64c850d74f7fd05f649bd64


---

# <a name="intune-network-bandwidth-use"></a>Wykorzystanie przepustowości sieci przez usługę Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Przed skonfigurowaniem usługi Microsoft Intune przejrzyj ten temat i inne wymagania wymienione w artykule [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md) (Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune).

Informacje zawarte w poniższych sekcjach ułatwią zaplanowanie ruchu sieciowego dla klientów usługi Microsoft Intune.

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

Aby zarządzać komputerami, które znajdują się za zaporami i serwerami proxy, należy skonfigurować zapory i serwery proxy w celu zezwalania na komunikację z usługą Intune.

### <a name="requirements-for-proxy-servers"></a>Wymagania dotyczące serwerów proxy
Aby zarządzać komputerami, które znajdują się za serwerem proxy:

-   Serwer proxy musi obsługiwać zarówno protokół **HTTP**, jak i **HTTPS**, ponieważ klienci usługi Intune używają obu tych protokołów.
-   Usługa Intune obsługuje nieuwierzytelnione serwery proxy.

Można zmodyfikować ustawienia serwerów proxy na poszczególnych komputerach klienckich albo użyć zasad grupy w celu zmiany ustawień dla wszystkich komputerów klienckich znajdujących się za określonym serwerem proxy.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Wymagania dotyczące zapór, portów i domen
Zarządzane urządzenia wymagają zastosowania takiej konfiguracji, aby grupa **Wszyscy użytkownicy** miała dostęp do usług za pośrednictwem zapór.

Poniższa tabela zawiera listę portów i usług, do których uzyskuje dostęp klient usługi Intune.

|**Domeny**|**Porty**|**Adres IP**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 i 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 i 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 i 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 i 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 i 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 i 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 i 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 i 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 i 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 i 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 i 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 i 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 i 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 i 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 i 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 i 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 i 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 i 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 i 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 i 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 i 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 i 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 i 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 i 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 i 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 i 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 i 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 i 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 i 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 i 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 i 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 i 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 i 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 i 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 i 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 i 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 i 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 i 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 i 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 i 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 i 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 i 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 i 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 i 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 i 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 i 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 i 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 i 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 i 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 i 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 i 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 i 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 i 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 i 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 i 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 i 443|111.221.76.60
|msua01.manage.microsoft.com|80 i 443|157.55.50.182
|msua02.manage.microsoft.com|80 i 443|134.170.49.121
|msua04.manage.microsoft.com|80 i 443|134.170.49.126
|msua05.manage.microsoft.com|80 i 443|157.55.240.190
|msub01.manage.microsoft.com|80 i 443|94.245.121.50
|msub02.manage.microsoft.com|80 i 443|94.245.121.58
|msub03.manage.microsoft.com|80 i 443|94.245.121.56
|msub05.manage.microsoft.com|80 i 443|157.56.113.123
|msuc01.manage.microsoft.com|80 i 443|104.44.84.187
|msuc02.manage.microsoft.com|80 i 443|104.44.84.188
|msuc03.manage.microsoft.com|80 i 443|104.44.84.189
|msuc05.manage.microsoft.com|80 i 443|111.221.76.60
|msua06.manage.microsoft.com|80 i 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 i 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 i 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 i 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 i 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 i 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 i 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 i 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 i 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 i 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 i 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 i 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 i 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 i 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 i 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 i 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 i 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 i 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 i 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 i 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 i 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 i 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 i 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 i 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 i 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 i 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 i 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 i 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 i 443|134.170.49.114
|ssu2.manage.microsoft.com|80 i 443|157.55.99.181
|status.manage.microsoft.com|80 i 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 i 443|93.184.215.200
|*.microsoftonline-p.com|80 i 443||
|has.spserv.microsoft.com<br>Wymagana dla usługi zaświadczania o kondycji urządzeń|443||
|*.microsoftonline-p.net|80 i 443||
|*.portal.office.com|80 i 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 i 443||
|c1.microsoft.com|80 i 443||
|blob.core.windows.net|80 i 443||
|ajax.aspnetcdn.com|80 i 443||
|*.googleapis.com<br>Ta domena jest wymagana do obsługi technologii JQuery podczas korzystania z witryny sieci Web Portalu firmy.|80 i 443||
|wustat.microsoft.com|80 i 443||
|Microsoft Update Services|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 i 443|
|Żądania wyszukiwania DNS|manage.microsoft.com.nsatc.net|80|
|Komunikacja przez zaporę z urządzeniem Samsung KNOX Standard|Aby umożliwić urządzeniom Samsung KNOX Standard kontaktowanie się przez zaporę z serwerami KNOX Standard, postępuj zgodnie z instrukcjami dostępnymi w sekcji często zadawanych pytań dotyczących systemu Samsung KNOX Standard.||
|Komunikacja z dostępem warunkowym|443|204.79.197.200|
|Dokumentacja, pomoc i obsługa techniczna:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||

>[!div class="step-by-step"]

>[&larr; **Wymagania wstępne**](what-to-know-before-you-start-microsoft-intune.md)     [**Subskrypcja** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  



<!--HONumber=Dec16_HO3-->


