---
# required metadata

title: Ustawienia zasad systemu Windows 10 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune

Ustawienia zasad wymienione w tym temacie ułatwiają konfigurowanie ustawień dla zarejestrowanych urządzeń z systemem Windows 10 Desktop lub Windows 10 Mobile.

## Ustawienia ogólnych zasad konfiguracji

**Ogólne zasady konfiguracji** usługi Microsoft Intune dla systemu Windows 10 umożliwiają konfigurowanie ogólnych ustawień dla zarejestrowanych urządzeń z systemem Windows 10 Desktop lub Windows 10 Mobile:


### Hasło

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|
|**Wymagaj hasła w celu odblokowania urządzeń**|Wymagaj hasła na obsługiwanych urządzeniach.|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|
|**Wymagany typ hasła** - **Minimalna liczba zestawów znaków**|Istnieją cztery zestawów znaków: małe litery, wielkie litery, cyfry oraz symbole. To ustawienie określa, z ilu różnych zestawów znaków muszą pochodzić znaki zawarte w haśle.|
|**Minimalna długość hasła**|Określa minimalną liczbę znaków, które musi zawierać hasło urządzenia.<br>(Tylko Windows 10 Mobile)|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Czyści urządzenie po określonej liczbie prób logowania zakończonych niepowodzeniem.|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa czas bezczynności urządzenia, po upływie którego ekran jest blokowany.|
|**Wygaśnięcie hasła (dni)**|Określa czas, po jakim hasło urządzenia musi zostać zmienione.|
|**Pamiętaj historię haseł**|Określa, czy chcesz ograniczyć użytkownikowi końcowemu możliwość tworzenia poprzednio używanych haseł.|
|**Pamiętaj historię haseł** - **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednio używanych haseł zapamiętywanych przez urządzenie.|
|**Zezwalaj na hasło obrazkowe i numer PIN**|Umożliwia logowanie się przy użyciu prostych gestów na obrazie lub prostego numeru PIN.<br>(Tylko Windows 10 Desktop)|
|**Wymagaj hasła po przywróceniu urządzenia ze stanu bezczynności**|Jeśli ta opcja jest włączona, użytkownik musi wprowadzić hasło, aby odblokować urządzenie, które przeszło w stan bezczynności.<br>(Tylko Windows 10 Mobile)|

### Encryption

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**|Włącza szyfrowanie na urządzeniach docelowych.<br>(Tylko Windows 10 Mobile)|

### System

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|
|**Zezwalaj na przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie ekranu urządzenia w formie obrazu.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na ręczne wyrejestrowanie**|Umożliwia użytkownikowi ręczne usunięcie z urządzenia konta w miejscu pracy.|
|**Zezwalaj na ręczną instalację certyfikatu głównego**|Określa, czy użytkownik może ręcznie instalować certyfikaty główne.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na wysyłanie danych diagnostycznych i danych dotyczących użycia do firmy Microsoft**|Określa ilość danych diagnostycznych i danych użycia, które są wysyłane do firmy Microsoft przez urządzenia.<br><br>**Brak** — żadne dane nie są wysyłane do firmy Microsoft<br>**Podstawowe** — urządzenie wysyła tylko ograniczone informacje do firmy Microsoft<br>**Rozszerzone** — urządzenie wysyła rozszerzone dane diagnostyczne do firmy Microsoft<br>**Pełne (zalecane)** — urządzenie wysyła te same dane, które są wysyłane w przypadku opcji **Rozszerzone**, oraz dodatkowe dane dotyczące stanu urządzenia|


### Konto i synchronizacja

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|---------------------|
|**Zezwalaj na konto Microsoft**|Zezwala użytkownikowi na skojarzenie konta Microsoft z urządzeniem.|
|**Zezwalaj na ręczne dodawanie kont innych niż konta Microsoft**|Zezwala użytkownikowi na dodanie na urządzeniu kont e-mail, które nie są skojarzone z kontem Microsoft.|
|**Zezwalaj na synchronizację ustawień kont Microsoft**|Zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między urządzeniami.|

### Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|---------------------|
|**Ustaw konto Microsoft jako opcjonalne w aplikacji Windows Mail**|Skonfiguruj tę opcję, aby usunąć wymaganie konta Microsoft w programie Windows Mail.<br>Tylko Windows 10 Desktop|



### Microsoft Edge

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Zezwala na korzystanie z przeglądarki Edge na urządzeniu.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na sugestie dotyczące wyszukiwania na pasku adresu**|Umożliwia wyszukiwarce sugerowanie witryn podczas wpisywania fraz do wyszukania.|
|**Zezwalaj na wysyłanie ruchu intranetowego do programu Internet Explorer**|Zezwala użytkownikom na otwieranie intranetowych witryn sieci Web w programie Internet Explorer.<br>(Tylko Windows 10 Desktop)|
|**Zezwalaj na żądania Nie śledź**|Konfiguruje przeglądarkę Edge, aby wysyłała nagłówki „Nie śledź” do witryn sieci Web odwiedzanych przez użytkowników.|
|**Włącz filtr SmartScreen**|Włącza ustawienie przeglądarki SmartScreen na urządzeniach.|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Zezwala na uruchamianie skryptów, takich jak skrypty JavaScript, w przeglądarce Edge.|
|**Zezwalaj na wyskakujące okienka**|Włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.<br>(Tylko Windows 10 Desktop)|
|**Zezwalaj na pliki cookie**|Zezwala na pliki cookie lub wyłącza je.|
|**Zezwalaj na autowypełnianie**|Zezwala użytkownikom na zmianę ustawienia autowypełniania w przeglądarce.<br>(Tylko Windows 10 Desktop)|
|**Zezwalaj na działanie menedżera haseł**|Włącza lub wyłącza funkcję menedżera haseł przeglądarki Edge.|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Określa lokalizację listy witryn, które będą otwierane w trybie przedsiębiorstwa. Użytkownicy nie mogą edytować tej listy.<br>(Tylko Windows 10 Desktop)|

### Aplikacje

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|---------------------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Umożliwia użytkownikowi dostęp do sklepu z aplikacjami na urządzeniu.<br>(Tylko Windows 10 Mobile)|



### Komórkowe

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|---------------------|
|**Zezwalaj na roaming danych**|Umożliwia roaming między sieciami przy dostępie do danych.|
|**Zezwalaj na połączenia VPN przez sieć komórkową**|Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku połączenia z siecią komórkową.|
|**Zezwalaj na roaming połączeń VPN przez sieć komórkową**|Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.|

### Sprzęt

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|
|**Zezwalaj na używanie aparatu**|Określa, czy można używać aparatu urządzenia.|
|**Zezwalaj na używanie magazynu wymiennego**|Określa, czy z urządzeniem można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD.|
|**Zezwalaj na połączenia Wi-Fi**|Zezwala na korzystanie z funkcji Wi-Fi urządzenia.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na udostępnianie Internetu**|Zezwala na udostępnianie połączenia internetowego na urządzeniu.|
|**Zezwalaj na ręczną konfigurację sieci Wi-Fi**|Określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Umożliwia urządzeniu automatyczne łączenie się z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.|
|**Zezwalaj na używanie funkcji geolokalizacji**|Określa, czy urządzenie może używać informacji z usług lokalizacyjnych.|
|**Zezwalaj na komunikację NFC**|Zezwala urządzeniu na korzystanie z funkcji Near Field Communications.|
|**Zezwalaj na połączenia Bluetooth**|Umożliwia korzystanie z funkcji Bluetooth na urządzeniu.|
|**Zezwalaj na tryb wykrywania urządzeń Bluetooth**|Umożliwia wykrycie urządzenia przez inne urządzenia Bluetooth.|
|**Zezwalaj na reklamy przez sieć Bluetooth**|Umożliwia urządzeniom odbieranie reklam przez sieć Bluetooth.|
|**Zezwalaj na tryb łączności Bluetooth**|**Ważne:** to ustawienie nie jest już obsługiwane w systemie Windows 10 i zostanie usunięte w przyszłości.|
|**Zezwalaj na resetowanie telefonu**|Określa, czy użytkownik może resetować urządzenie do ustawień fabrycznych.|
|**Zezwalaj na połączenie USB**|Określa, czy urządzenia mają dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.|
|**Zezwalaj na tryb antykradzieżowy**|Pozwala określić, czy jest włączony tryb antykradzieżowy systemu Windows.|

### Funkcje

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------|---------------------|
|**Zezwalaj na kopiowanie i wklejanie**|Włącza lub wyłącza możliwość kopiowania i wklejania na urządzeniu.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na nagrywanie głosu**|Włącza lub wyłącza funkcje nagrywania głosu na urządzeniu.<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na funkcję Cortana**|Włącza lub wyłącza asystenta głosowego Cortana.|
|**Zezwalaj na powiadomienia w Centrum akcji**|Włącza lub wyłącza powiadomienia centrum akcji na ekranie blokady urządzenia.<br>(Tylko Windows 10 Mobile)|

### Usługa Defender

Wszystkie ustawienia dotyczą wyłącznie systemu Windows 10 Desktop.

|Nazwa ustawienia|Szczegóły|
|-|-|
|**Zezwalaj na monitorowanie w czasie rzeczywistym**|Włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.|
|**Zezwalaj na monitorowanie zachowania**|Umożliwia usłudze Defender sprawdzanie określonych wzorców podejrzanej aktywności na urządzeniach.|
|**Włącz system inspekcji sieci**|System inspekcji sieci (NIS, Network Inspection System) ułatwia ochronę urządzenia przed atakami sieciowymi wykorzystującymi luki w zabezpieczeniach, używając sygnatur znanych luk w zabezpieczeniach z centrum programu Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch.|
|**Skanuj wszystkie pobrane pliki**|Określa, czy usługa Defender skanuje wszystkie pliki pobierane z Internetu.|
|**Zezwalaj na skanowanie skryptów**|Umożliwia usłudze Defender skanowanie skryptów używanych przez program Internet Explorer.|
|**Monitoruj działania plików i programów**|Włącz to ustawienie, aby usługa Defender mogła monitorować działania plików i programów na urządzeniach.|
|**Liczba dni śledzenia wykrytego złośliwego oprogramowania**|Umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane. |
|**Zezwalaj na dostęp do interfejsu użytkownika klienta**|Określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych.<br>Jeśli to ustawienie zostanie zmienione, zmiany zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika końcowego.|
|**Zaplanuj codzienne szybkie skanowanie**|Umożliwia zaplanowanie szybkiego skanowania, które będzie odbywać się codziennie o wybranej porze.|
|**Zaplanuj skanowanie systemu**|Umożliwia zaplanowanie pełnego lub szybkiego skanowania systemu wykonywanego regularnie w wybranym dniu o wybranej godzinie.|
|**Ogranicz użycie procesora podczas skanowania**|Pozwala ograniczyć moc procesora CPU, jakiej mogą używać procesy skanowania (od **1** do **100**).|
|**Skanuj pliki archiwum**|Zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.|
|**Skanuj wiadomości e-mail**|Zezwala usłudze Defender na skanowanie wiadomości e-mail podczas ich dostarczania do urządzenia.|
|**Skanuj dyski wymienne**|Umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.|
|**Skanuj zamapowane dyski sieciowe**|Umożliwia usłudze Defender skanowanie plików na zamapowanym dysku sieciowym.<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.|
|**Skanuj pliki otwierane z udostępnionych folderów sieciowych**|Umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach z dostępem za pośrednictwem ścieżki UNC).<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.|
|**Interwał aktualizacji sygnatur**|Określa interwał, z jakim usługa Defender będzie sprawdzać dostępność nowych plików sygnatur.|
|**Zezwalaj na ochronę w chmurze**|Zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.|
|**Pytaj użytkowników o przesyłane próbki**|Określa, czy do firmy Microsoft są automatycznie wysyłane pliki, które mogą wymagać dalszej analizy ze strony firmy Microsoft w celu określenia, czy są złośliwe.|
|**Pliki i foldery do wykluczenia w trakcie skanowania lub używania ochrony w czasie rzeczywistym**|Dodaj do listy wykluczeń jeden lub więcej plików i folderów, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|
|**Rozszerzenia plików, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym**|Dodaj do listy wykluczeń jedno lub więcej rozszerzeń plików, na przykład **jpg** lub **txt**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|
|**Procesy, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym**|Dodaj jeden lub więcej procesów typu **exe**, **com** lub **scr** do listy wykluczeń. Te procesy nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.| 


### Ustawienia aktualizacji

|Nazwa ustawienia|Szczegóły|
|----------------|---------------|
|**Zezwalaj na aktualizacje automatyczne**|Włącz to ustawienie, aby zezwalać na aktualizacje automatyczne. Następnie skonfiguruj jedno z następujących ustawień kontrolowania zachowania aktualizacji:<br /><br />**Powiadamiaj o pobieraniu**<br /><br />**Instaluj automatycznie podczas konserwacji**<br /><br />**Automatycznie instaluj i uruchamiaj ponownie podczas konserwacji**<br /><br />**Automatycznie zainstaluj i uruchom ponownie w zaplanowanym czasie** **Uwaga:** jeśli ta opcja jest wybrana, możesz również skonfigurować następujące ustawienia: **Pomiń powiadamianie użytkownika końcowego** i **Zdefiniuj dzień instalacji zaplanowanych aktualizacji**.<br>(Tylko Windows 10 Desktop)|

## Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji** usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwiają wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), za pomocą których można sterować funkcjami na urządzeniach z systemami Windows 10 i Windows 10 Mobile. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić wdrażanie ustawień systemu Windows 10, których nie można skonfigurować przy użyciu ogólnych zasad konfiguracji usługi Intune.



### Ustawienia ogólne zasad niestandardowych

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę zasad, która ułatwi ich identyfikację w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad oraz inne istotne informacje ułatwiające ich wyszukanie.|

### Ustawienia niestandardowych zasad OMA-URI

|Nazwa ustawienia|Szczegóły|
    |--------|--------------------|
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację  na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz spośród opcji:<br /><br />-   **String**<br />-   **Ciąg (XML)**<br />-   **Data i godzina**<br />-   **Integer**<br />-   **Liczba zmiennoprzecinkowa**<br />-   **Boolean**|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|


## Niestandardowe ustawienia identyfikatorów URI dla urządzeń z systemem Windows 10
Ten temat zawiera listę ustawień, które można skonfigurować dla urządzeń z systemami Windows 10 i Windows 10 Mobile w **niestandardowych zasadach systemu Windows 10** usługi Microsoft Intune.

Aby korzystać z niestandardowych zasad identyfikatorów URI systemu Windows, wszystkie urządzenia muszą być zarejestrowane w usłudze Intune.

### Ustawienia identyfikatorów URI zasad

|Nazwa zasad|Szczegóły|
|---------------|------------|-----------|
|**​Zezwalaj na automatyczne aktualizacje**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** - **5** (domyślnie: **1**)|
|**Planowany dzień instalacji**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — codziennie (ustawienie domyślne)<br>**1** — niedziela<br>**2** — poniedziałek<br>**3** — wtorek<br>**4** — środa<br>**5** — czwartek<br>**6** — piątek<br>**7** — sobota|
|**Planowana godzina instalacji**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**–**23** godz. (**0** oznacza północ) (domyślnie: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — użytkownik nie może ustawić czasomierza okresu karencji hasła, a wartość jest ustawiana jako „za każdym razem”<br>**1** — użytkownik może ustawić czasomierz okresu karencji hasła (ustawienie domyślne)|
|**WiFi/AllowWiFi**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj na **używanie połączenia Wi-Fi**<br>**1** — **zezwalaj na używanie połączenia Wi-Fi** (ustawienie domyślne)|
|**WiFi/AllowInternetSharing**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj na udostępnianie Internetu.<br>**1** — zezwalaj na udostępnianie Internetu (ustawienie domyślne)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**WiFi/AllowManualWiFiConfiguration**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie jest dozwolone żadne połączenie Wi-Fi poza aprowizowanym przez rozwiązanie MDM.<br>**1** — dodawanie nowych identyfikatorów SSID sieci poza już aprowizowanymi przez rozwiązanie MDM jest dozwolone (ustawienie domyślne)|
|**System/AllowLocation**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**System/AllowTelemetry**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone (ustawienie tylko dla wersji Enterprise)<br>**1** — ograniczone<br>**2** — pełne (ustawienie domyślne)<br>**3** — pełne i informacje diagnostyczne|
|**System/AllowExperimentation**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — tylko ustawienia (ustawienie domyślne)<br>**2** — ustawienia i eksperymenty|
|**Security/AntiTheftMode**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj na tryb antykradzieżowy<br>**1** — preferencja użytkownika (ustawienie domyślne)|
|**Connectivity/AllowUSBConnection**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**System/AllowUserToResetPhone**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Connectivity/AllowCellularDataRoaming**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Connectivity/AllowVPNOverCellular**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — używanie sieci VPN z połączeniem komórkowym jest niedozwolone<br>**1** — sieć VPN może używać dowolnego połączenia, w tym komórkowego (ustawienie domyślne)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Connectivity/AllowBluetooth**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj użytkownikowi na włączanie funkcji Bluetooth.<br>**1** — zastrzeżone. Użytkownik może włączać i konfigurować funkcję Bluetooth (nieobsługiwane w przypadku protokołu EAS oraz systemów Windows Phone 8.1 dla rozwiązania MDM, Windows 10 Desktop i Windows 10 Mobile).<br>**2** — dozwolone. Użytkownik może włączać i konfigurować funkcję Bluetooth (ustawienie domyślne)|
|**Experience/AllowScreenCapture**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Experience/AllowTaskSwitcher**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Experience/AllowVoiceRecording**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Experience/AllowSyncMySettings**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj na roaming<br>**1** — zezwalaj na roaming (ustawienie domyślne)|
|**Experience/AllowManualMDMUnenrollment**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Security/AllowManualRootCertificateInstallation**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Security/AllowAddProvisioningPackages**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Search/DisableBackoff**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** (ustawienie domyślne)<br>**1**|
|**Search/PreventRemoteQueries**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**<br>**1** (ustawienie domyślne)|
|**Search/AllowUsingDiacritics**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br> **0** (ustawienie domyślne)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** (ustawienie domyślne)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** (ustawienie domyślne)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**<br>**1** (ustawienie domyślne)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** (ustawienie domyślne)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Security/RequireProvisioningPackageSignature**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** (ustawienie domyślne)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**TextInput/AllowIMENetworkAccess**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj<br>Otwarty słownik rozszerzony jest wyłączony.<br>Użytkownik nie może:<br>dodać nowego otwartego słownika rozszerzonego,<br /><br />dodać nowego pliku konfiguracji integracji wyszukiwania,<br>używać funkcji kandydata z chmury,<br>wysłać zastrzeżonego słowa użytkownika.<br>Dodatkowo:<br>Otwarty słownik rozszerzony dodany przed włączeniem tego ustawienia zasad nie będzie używany na potrzeby konwersji.<br>Plik konfiguracji integracji wyszukiwania zainstalowany przed włączeniem tego ustawienia zasad nie będzie używany.<br>**1** — zezwalaj<br>Otwarty słownik rozszerzony może być dodany i używany domyślnie. Domyślnie można również używać funkcji integracji wyszukiwania.<br>Użytkownik może:<br>używać funkcji kandydata z chmury,<br>wysłać zastrzeżone słowo użytkownika.|
|**TextInput/AllowIMELogging**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — rejestrowanie błędów konwersji jest wyłączone. Automatycznie dopasowane dane i historyczne dane wejściowe nie są zapisywane w pliku.<br>**1** — rejestrowanie błędów konwersji jest włączone. Automatycznie dopasowane dane i historyczne dane wejściowe są zapisywane w pliku (ustawienie domyślne).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**TextInput/AllowJapaneseUserDictionary**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — żadne znaki nie są filtrowane (ustawienie domyślne)<br>**1** — wszystkie znaki oprócz znaków Shift JIS są filtrowane|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — żadne znaki nie są filtrowane (ustawienie domyślne)<br>**1** — wszystkie znaki oprócz znaków JIS0208 są filtrowane|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — żadne znaki nie są filtrowane (ustawienie domyślne)<br>**1** — wszystkie znaki oprócz znaków JIS0208 lub EUDC są filtrowane|
|**TextInput/AllowInputPanel**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Bluetooth/AllowDiscoverableMode**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Bluetooth/AllowAdvertising**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowDataSense**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowVPN**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowWorkplace**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowDateTime**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowLanguage**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowRegion**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowSignInOptions**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowYourAccount**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowPowerSleep**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Settings/AllowAutoPlay**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Experience/AllowCortana**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Search/SafeSearchPermissions**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — ścisłe, najwyższy poziom filtrowania pod kątem blokowania treści dla dorosłych<br>**1** — umiarkowane, średni poziom filtrowania pod kątem blokowania treści dla dorosłych (prawidłowe wyniki wyszukiwania nie będą filtrowane — ustawienie domyślne)|
|**Experience/AllowCopyPaste**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**Wymuś początkowy rozmiar**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — zezwalaj na zmianę rozmiaru przez użytkownika (ustawienie domyślne)<br>**1** — wymuś niepełny ekran<br>**2** — wymuś pełny ekran|
|**Update/RequireDeferUpgrade**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**: nie odraczaj uaktualnienia (pozostań w wersji Current Branch — ustawienie domyślne)<br>**1**: zezwalaj na odraczanie aktualizacji i uaktualnień (urządzenie pozostaje zgodne z regułami wersji Current Branch dla firm)<br /><br />Aby uzyskać więcej informacji, zobacz:<br>[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(wersje Desktop i Mobile)|**Opis:** zasady umożliwiające odroczenie aktualizacji oprogramowania na maksymalnie 4 tygodnie<br /><br />**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br> **0**: zastosuj aktualizacje od razu (ustawienie domyślne)<br>**1**-**4**: liczba tygodni, przez które mają być odroczone aktualizacje oprogramowania<br /><br />Aby uzyskać więcej informacji, zobacz:<br>[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(wersje Desktop i Mobile)|**Opis:** zasady umożliwiające odroczenie uaktualnień funkcji na maksymalnie 8 miesięcy<br /><br />**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**: zastosuj aktualizacje od razu (ustawienie domyślne)<br>**1**-**8**: liczba miesięcy, przez które mają być odroczone uaktualnienia funkcji<br /><br />Aby uzyskać więcej informacji, zobacz:<br>[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(wersje Desktop i Mobile)|**Opis:** zezwala na zatrzymanie otrzymywania aktualizacji i uaktualnień przez komputer korzystający z wersji Current Branch dla firm na okres maksymalnie 5 tygodni. Tej opcji należy używać w przypadku, gdy występuje problem z aktualizacją.<br /><br />**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**: zastosuj aktualizacje od razu (ustawienie domyślne)<br>**1**: wstrzymaj aktualizacje i uaktualnienia (wygasa po 5 tygodniach)|

### Ustawienia identyfikatorów URI usługi Windows Defender

|Nazwa zasad|Szczegóły|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowBehaviorMonitoring**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowIntrusionPreventionSystem**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowIOAVProtection**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowScriptScanning**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowOnAccessProtection**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**RealTimeScanDirection**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — monitoruj wszystkie pliki (dwukierunkowo — ustawienie domyślne)<br>**1** — monitoruj pliki przychodzące<br>**2** — monitoruj pliki wychodzące|
|**DaysToRetainCleanedMalware**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** - **90** — reprezentuje czas zachowywania złośliwego oprogramowania<br>**Wartość domyślna:** **0** — elementy w folderze kwarantanny będą przechowywane w nieskończoność i nie będą usuwane automatycznie|
|**AllowUserUIAccess**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**ScanParameter**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**1** — szybkie skanowanie (ustawienie domyślne)<br>**2** — pełne skanowanie|
|**ScheduleScanDay**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — codziennie (ustawienie domyślne)<br>**1** — poniedziałek<br>**2** — wtorek<br>**3** — środa<br>**4** — czwartek<br>**5** — piątek<br>**6** — sobota<br>**7** — niedziela<br>**8** — brak zaplanowanego skanowania|
|**ScheduleScanTime**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — 0:00<br>**60** — 1:00<br>**120** — 2:00 (ustawienie domyślne)<br>**180** — 3:00<br>**240** — 4:00<br>**300** — 5:00<br>**360** — 6:00<br>**420** — 7:00<br>**480** — 8:00<br>**540** — 9:00<br>**600** — 10:00<br>**660** — 11:00<br>**720** — 12:00<br>**780** — 13:00<br>**840** — 14:00<br>**900** — 15:00<br>**960** — 16:00<br>**1020** — 17:00<br>**1080** — 18:00<br>**1140** — 19:00<br>**1200** — 20:00<br>**1260** — 21:00<br>**1320** — 22:00<br>**1381** — okno obsługi|
|**ScheduleQuickScanTime**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — 0:00<br>**60** — 1:00<br>**120** — 2:00 (ustawienie domyślne)<br>**180** — 3:00<br>**240** — 4:00<br>**300** — 5:00<br>**360** — 6:00<br>**420** — 7:00<br>**480** — 8:00<br>**540** — 9:00<br>**600** — 10:00<br>**660** — 11:00<br>**720** — 12:00<br>**780** — 13:00<br>**840** — 14:00<br>**900** — 15:00<br>**960** — 16:00<br>**1020** — 17:00<br>**1080** — 18:00<br>**1140** — 19:00<br>**1200** — 20:00<br>**1260** — 21:00<br>**1320** — 22:00<br>**1380** — 23:00|
|**AVGCPULoadFactor**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** - **100** (domyślnie: **50**)|
|**AllowArchiveScanning**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowEmailScanning**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Typ danych:** liczba całkowita<br>**Dozwolone wartości:**<br>**0** — niedozwolone (ustawienie domyślne)<br>**1** — dozwolone|
|**AllowFullScanRemovableDriveScanning**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone (ustawienie domyślne)<br>**1** — dozwolone|
|**AllowFullScanOnMappedNetworkDrives**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**AllowScanningNetworkFiles**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne) — jeśli dozwolone, jest również uruchamiane przy włączonej ochronie czasu rzeczywistego|
|**SignatureUpdateInterval**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — bez sprawdzania podpisów co określony czas<br>**1** — sprawdzaj sygnatury co godzinę<br>**2** — sprawdzaj podpisy co 2 godziny itd.<br>**24** — sprawdzaj podpisy codziennie<br>**Wartość domyślna:** 8 — sprawdzaj podpisy co 8 godzin|
|**AllowCloudProtection**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — niedozwolone<br>**1** — dozwolone (ustawienie domyślne)|
|**SubmitSamplesConsent**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — zawsze pytaj (ustawienie domyślne)<br>**1** — automatycznie wyślij bezpieczne próbki<br>**2** — nigdy nie wysyłaj<br>**3** — wyślij wszystkie próbki automatycznie|
|**ExcludedExtensions**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości:**<br>*&lt;lista rozszerzeń rozdzielonych średnikami&gt;*, na przykład **obj;lib**<br>**Ustawienie domyślne:** brak wykluczonych rozszerzeń|
|**ExcludedPaths**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości:**<br /><br />*&lt;lista ścieżek rozdzielonych średnikami&gt;*<br /><br />Przykład: **c:\test;c:\test1.exe**<br /><br />**Wartość domyślna:** brak wykluczonych ścieżek|
|**ExcludedProcesses**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości:**<br>*&lt;lista ścieżek rozdzielonych średnikami&gt;*<br>Przykład: **c:\test.exe;c:\test1.exe**<br>**Wartość domyślna:** brak wykluczonych procesów|

### Ustawienia identyfikatorów URI przeglądarki Edge

|Nazwa zasad|Szczegóły|
|---------------|------------|-----------|
|**Zezwalaj na przeglądarkę**<br>(tylko wersja Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**: przeglądanie wyłączone<br>**1**: przeglądanie włączone (ustawienie domyślne)|
|**AllowSearchSuggestionsinAddressBar**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**: nie pokazuj sugestii dotyczących wyszukiwania<br>**1**: pokaż sugestie dotyczące wyszukiwania (ustawienie domyślne)|
|**SendIntranetTraffictoInternetExplorer**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0**: wyłączone (otwieraj witryny intranetowe w przeglądarce Edge — ustawienie domyślne)<br>**1**: włączone (otwieraj witryny intranetowe w programie Internet Explorer)|
|**Zezwalaj na żądania Nie śledź**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — wyłączone (bez wysyłania żądań „Nie śledź” — ustawienie domyślne)<br>**1** — włączone (wysyłaj żądania „Nie śledź”)|
|**Skonfiguruj funkcję SmartScreen**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie zezwalaj<br>**1** — zezwalaj (ustawienie domyślne)|
|**Zezwalaj na wyskakujące okienka**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — blokuj wyskakujące okienka (ustawienie domyślne)<br>**1** — zezwalaj na wyskakujące okienka|
|**Zezwalaj na pliki cookie**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — nie blokuj. Zezwalaj na pliki cookie z wszystkich witryn sieci Web (ustawienie domyślne).<br>**1** — blokuj tylko pliki cookie innych firm<br>**2** — blokuj wszystkie pliki cookie|
|**Zezwalaj na zapisywanie haseł**<br>(wersje Desktop i Mobile)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — menedżer haseł jest wyłączony; <br>**1** — menedżer haseł jest włączony (ustawienie domyślne)|
|**Zezwalaj na autowypełnianie**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br>**0** — wyłączone (ustawienie domyślne)<br>**1** — włączone|
|**Skonfiguruj listę witryn przedsiębiorstwa**<br>(tylko wersja Desktop)|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości: <br>0** — nieskonfigurowane<br>**1** — użyj listy witryn trybu przedsiębiorstwa programu IE, jeśli skonfigurowano (ustawienie domyślne)<br>**2** — określ lokalizację listy witryn przedsiębiorstwa|

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO1-->


