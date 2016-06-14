---
# required metadata

title: Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune | Microsoft Intune
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
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune

Ustawienia zasad wymienione w tym temacie umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Desktop lub Windows 10 Mobile.

## Ustawienia ogólnych zasad konfiguracji

**Ogólne zasady konfiguracji** firmy Microsoft dla systemu Windows 10 umożliwiają konfigurowanie ogólnych ustawień zarejestrowanych urządzeń z systemem Windows 10 Desktop lub Windows 10 Mobile:


### Hasło

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Wymagaj hasła w celu odblokowania urządzeń**|Wymagaj hasła na obsługiwanych urządzeniach.|Tak|Tak|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|Tak|Tak|
|**Wymagany typ hasła** - **Minimalna liczba zestawów znaków**|Istnieją cztery zestawów znaków: małe litery, wielkie litery, cyfry oraz symbole. To ustawienie określa, znaki z ilu zestawów znaków muszą być zawarte w haśle.|Tak|Tak|
|**Minimalna długość hasła**|Określa minimalną liczbę znaków, które musi zawierać hasło urządzenia.|Nie|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Czyści urządzenie po określonej liczbie prób logowania zakończonych niepowodzeniem.|Tak|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa czas bezczynności urządzenia, po upływie którego ekran jest blokowany.|Tak|Tak|
|**Wygaśnięcie hasła w dniach**|Określa czas, po jakim hasło urządzenia musi zostać zmienione.|Tak|Tak|
|**Pamiętaj historię haseł**|Określa, czy chcesz ograniczyć użytkownikowi końcowemu możliwość tworzenia uprzednio używanych haseł.|Tak|Tak|
|**Pamiętaj historię haseł** - **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.|Tak|Tak|
|**Zezwalaj na hasło obrazkowe i numer PIN**|Umożliwia logowanie się przy użyciu prostych gestów na obrazie lub prostego numeru PIN.|Tak|Nie|
|**Wymagaj hasła po przywróceniu urządzenia ze stanu bezczynności**|Jeśli opcja jest włączona, użytkownik musi wprowadzić hasło, aby odblokować urządzenie, które przeszło w stan bezczynności.|Nie|Tak|

### Szyfrowanie

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**|Włącza szyfrowanie na urządzeniach docelowych.|Nie|Tak|

### System

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie ekranu urządzenia w formie obrazu.|Nie|Tak|
|**Zezwalaj na ręczne wyrejestrowanie**|Umożliwia użytkownikowi ręczne usunięcie z urządzenia konta w miejscu pracy.|Tak|Tak|
|**Zezwalaj na ręczną instalację certyfikatu głównego**|Określa, czy użytkownik może ręcznie instalować certyfikaty główne|Nie|Tak|
|**Zezwalaj na wysyłanie danych diagnostycznych i danych dotyczących użycia do firmy Microsoft**|Określa ilość danych diagnostycznych i danych użycia, które są wysyłane do firmy Microsoft przez urządzenia.<br>**Brak** — żadne dane nie są wysyłane do firmy Microsoft.<br>**Podstawowe** — urządzenie wysyła tylko ograniczone informacje do firmy Microsoft.<br>**Rozszerzone** — urządzenie wysyła rozszerzone dane diagnostyczne do firmy Microsoft.<br>**Pełne (zalecane)** — wysyła te same dane, które są wysyłane w przypadku opcji **Rozszerzone** oraz dodatkowe dane dotyczące stanu urządzenia.|Tak|Tak|


### Konto i synchronizacja

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na konto Microsoft**|Pozwala użytkownikowi na skojarzenie konta Microsoft z urządzeniem.|Tak|Tak|
|**Zezwalaj na ręczne dodawanie kont innych niż konta Microsoft**|Pozwala użytkownikowi na dodanie na urządzeniu kont e-mail, które nie są skojarzone z kontem Microsoft.|Tak|Tak|
|**Zezwalaj na synchronizację ustawień kont Microsoft**|Zezwala na synchronizację ustawień urządzenia i aplikacji z kontem Microsoft, co umożliwia synchronizację między urządzeniami.|Tak|Tak|

### Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Ustaw konto Microsoft jako opcjonalne w aplikacji Windows Mail**|Skonfiguruj tę opcję, aby usunąć wymaganie konta Microsoft w programie Windows Mail.|Tak|Nie|



### Microsoft Edge

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Zezwala na używanie przeglądarki Edge na urządzeniu.|Nie|Tak|
|**Zezwalaj na sugestie dotyczące wyszukiwania na pasku adresu**|Umożliwia wyszukiwarkom podawanie sugestii dotyczących witryn podczas wpisywania fraz w polu wyszukiwania.|Tak|Tak|
|**Zezwalaj na wysyłanie ruchu intranetowego do programu Internet Explorer**|Zezwala użytkownikom na otwieranie witryn sieci Web w programie Internet Explorer.|Tak|Nie|
|**Zezwalaj na żądania Nie śledź**|Konfiguruje przeglądarkę Edge, aby wysyłała nagłówki Nie śledź do witryn sieci Web odwiedzanych przez użytkowników.|Tak|Tak|
|**Włącz filtr SmartScreen**|Umożliwia ustawienie przeglądarki SmartScreen na urządzeniach.|Tak|Tak|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Zezwala na uruchamianie skryptów, takich jak Javascript, w przeglądarce Edge.|Tak|Tak|
|**Zezwalaj na wyskakujące okienka**|Włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.|Tak|Nie|
|**Zezwalaj na pliki cookie**|Zezwala na pliki cookie lub wyłącza je.|Tak|Tak|
|**Zezwalaj na autowypełnianie**|Zezwala użytkownikom na zmianę ustawienia autowypełniania w przeglądarce.|Tak|Nie|
|**Zezwalaj na działanie menedżera haseł**|Włącza lub wyłącza funkcję menedżera haseł przeglądarki Edge.|Tak|Tak|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Określa lokalizację listy witryn, które będą otwierane w trybie przedsiębiorstwa. Użytkownicy nie mogą edytować tej listy.|Tak|Nie|

### Aplikacje

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Umożliwia użytkownikowi dostęp do sklepu z aplikacjami na urządzeniu.|Nie|Tak|



### Komórkowe

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na roaming danych**|Umożliwia roaming między sieciami przy dostępie do danych.|Tak|Tak|
|**Zezwalaj na połączenia VPN przez sieć komórkową**|Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku podłączenia z siecią komórkową.|Tak|Tak|
|**Zezwalaj na roaming połączeń VPN przez sieć komórkową**|Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.|Tak|Tak|

### Sprzęt

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na używanie aparatu**|Określa, czy można używać aparatu urządzenia.|Tak|Tak|
|**Zezwalaj na używanie magazynu wymiennego**|Określa, czy z urządzeniem można używać zewnętrznych urządzeń pamięci masowej, np. kart SD.|Tak|Tak|
|**Zezwalaj na połączenia Wi-Fi**|Zezwala na korzystanie z łączności Wi-Fi urządzenia.|Nie|Tak|
|**Zezwalaj na udostępnianie Internetu**|Zezwala na udostępnianie połączenia internetowego na urządzeniu.|Tak|Tak|
|**Zezwalaj na ręczną konfigurację sieci Wi-Fi**|Określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy też może używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi.|Nie|Tak|
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Zezwala urządzeniu na automatyczne łączenie się z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.|Tak|Tak|
|**Zezwalaj na używanie funkcji geolokalizacji**|Określa, czy urządzenie może używać informacji z usług lokalizacyjnych.|Tak|Tak|
|**Zezwalaj na komunikację NFC**|Umożliwia wykorzystanie łączności Near Field Communications urządzenia.|Tak|Tak|
|**Zezwalaj na połączenia Bluetooth**|Umożliwia korzystanie z łączności Bluetooth na urządzeniu.|Tak|Tak|
|**Zezwalaj na tryb wykrywania urządzeń Bluetooth**|Umożliwia wykrycie urządzenia przez inne urządzenia Bluetooth.|Tak|Tak|
|**Zezwalaj na reklamy przez sieć Bluetooth**|Umożliwia urządzeniom odbieranie reklam przez sieć Bluetooth.|Tak|Tak|
|**Zezwalaj na tryb łączności Bluetooth** **Ważne:** |To ustawienie nie jest już obsługiwane w systemie Windows 10 i zostanie usunięte w przyszłości.|Tak|Tak|
|**Zezwalaj na resetowanie telefonu**|Określa, czy użytkownik może wykonać reset urządzenia do ustawień fabrycznych.|Tak|Tak|
|**Zezwalaj na połączenie USB**|Określa, czy urządzenia mają dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.|Tak|Tak|
|**Zezwalaj na tryb antykradzieżowy**|Pozwala określić, czy jest włączony tryb antykradzieżowy systemu Windows.|Tak|Tak|

### Funkcje

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Zezwalaj na kopiowanie i wklejanie**|Włącza lub wyłącza możliwość użycia funkcji kopiowania i wklejania na urządzeniu.|Nie|Tak|
|**Zezwalaj na nagrywanie głosu**|Włącza lub wyłącza możliwość użycia funkcji nagrywania głosu na urządzeniu.|Nie|Tak|
|**Zezwalaj na funkcję Cortana**|Włącza lub wyłącza asystenta głosowego Cortana.|Tak|Tak|
|**Zezwalaj na powiadomienia w Centrum akcji**|Włącza lub wyłącza powiadomienia centrum akcji na ekranie blokady urządzenia.|Nie|Tak|

### Defender

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|-|-|
|**Zezwalaj na monitorowanie w czasie rzeczywistym**|Włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.|Tak|Nie|
|**Zezwalaj na monitorowanie zachowania**|Umożliwia usłudze Defender sprawdzanie określonych wzorców podejrzanej aktywności na urządzeniach.|Tak|Nie
|**Włącz system inspekcji sieci**|System inspekcji sieci (NIS, Network Inspection System) pomaga chronić urządzenia przed atakami sieciowymi wykorzystującymi luki w zabezpieczeniach poprzez wykorzystanie sygnatur znanych luk w zabezpieczeniach z centrum Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch.|Tak|Nie
|**Skanuj wszystkie pobrane pliki**|Określa, czy usługa Defender skanuje wszystkie pliki pobierane z Internetu.|Tak|Nie
|**Zezwalaj na skanowanie skryptów**|Umożliwia usłudze Defender skanowanie skryptów używanych przez przeglądarkę Internet Explorer.|Tak|Nie
|**Monitoruj działania plików i programów**|Włącz to ustawienie, aby usługa Defender mogła monitorować działania plików i programów na urządzeniach.|Tak|Nie
|**Liczba dni śledzenia wykrytego złośliwego oprogramowania**|Umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni. Dzięki temu możesz ręcznie sprawdzić urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane. |Tak|Nie
|**Zezwalaj na dostęp do interfejsu użytkownika klienta**|Określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych.<br>Jeśli ustawienie zostanie zmienione, zmiany zostaną wprowadzone po następnym ponownym uruchomieniu komputera przez użytkownika końcowego.|Tak|Nie
|**Zaplanuj codzienne szybkie skanowanie**|Umożliwia zaplanowanie szybkiego skanowania, które będzie odbywać się codziennie o wybranej porze.|Tak|Nie
|**Zaplanuj skanowanie systemu**|Umożliwia zaplanowanie pełnego lub szybkiego skanowania systemu wykonywanego regularnie w wybranym dniu o wybranej godzinie.|Tak|Nie
|**Ogranicz użycie procesora CPU podczas skanowania**|Pozwala ograniczyć moc procesora CPU, jakiej mogą używać procesy skanowania (od **1** do **100**.)|Tak|Nie
|**Skanuj pliki archiwum**|Zezwala usłudze Defender na skanowanie plików archiwów, np. plików zip lub cab.|Tak|Nie
|**Skanuj wiadomości e-mail**|Zezwala usłudze Defender na skanowanie wiadomości e-mail podczas ich dostarczania do urządzenia.|Tak|Nie
|**Skanuj dyski wymienne**|Zezwala usłudze Defender na skanowanie dysków wymiennych, np. dysków flash USB.|Tak|Nie
|**Skanuj zamapowane dyski sieciowe**|Zezwala usłudze Defender na skanowanie plików na zamapowanym dysku sieciowym.<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.|Tak|Nie
|**Skanuj pliki otwierane z udostępnionych folderów sieciowych**|Zezwala usłudze Defender na skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach z dostępem za pośrednictwem ścieżki UNC).<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.|Tak|Nie
|**Interwał aktualizacji sygnatur**|Określa interwał, z jakim usługa Defender będzie sprawdzać nowe pliki sygnatur.|Tak|Nie
|**Zezwalaj na ochronę w chmurze**|Zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.|Tak|Nie
|**Pytaj użytkowników o przesyłane próbki**|Określa, czy pliki, które mogą wymagać dalszej analizy ze strony firmy Microsoft w celu określenia, czy są one złośliwe, są automatycznie wysyłane do firmy Microsoft.|Tak|Nie
|**Pliki i foldery do wykluczenia w trakcie skanowania lub używania ochrony w czasie rzeczywistym**|Dodaj pliki i foldery, np. **C:\Ścieżka** lub **%ProgramFiles%\Ścieżka\nazwa_pliku.exe**, do listy wykluczeń. Te pliki i foldery nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|Tak|Nie
|**Rozszerzenia plików, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym**|Dodaj jedno lub większą liczbę rozszerzeń pliku, np. **jpg** lub **txt**, do listy wykluczeń. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|Tak|Nie
|**Procesy, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym**|Dodaj jeden lub większą liczbę procesów typu **exe**, **com** lub **scr** do listy wykluczeń. Te procesy nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|Tak|Nie| 


### Ustawienia aktualizacji

|Nazwa ustawienia|Szczegóły|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Zezwalaj na aktualizacje automatyczne**|Włącz to ustawienie, aby zezwalać na aktualizacje automatyczne. Następnie skonfiguruj jedno z następujących ustawień kontrolowania zachowania aktualizacji:<br /><br />**Powiadamiaj o pobieraniu**<br /><br />**Instaluj automatycznie podczas konserwacji**<br /><br />**Automatycznie instaluj i uruchamiaj ponownie podczas konserwacji**<br /><br />**Automatycznie zainstaluj i uruchom ponownie w zaplanowanym czasie** **Uwaga:** jeśli ta opcja jest wybrana, możesz również skonfigurować następujące ustawienia: **Pomiń powiadomienie dla użytkownika końcowego** i **Zdefiniuj dzień instalacji zaplanowanych aktualizacji**..|Tak|Nie|

## Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji** usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwiają wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), za pomocą których można kontrolować funkcje na urządzeniach z systemami Windows 10 i Windows 10 Mobile. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić wdrażanie ustawień systemu Windows 10, których nie można skonfigurować przy użyciu ogólnych zasad konfiguracji usługi Intune. Aby uzyskać informacje o ustawieniach, które można skonfigurować za pomocą tych zasad, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Aby sprawdzić listę ustawień OMA-URI, które można skonfigurować na zarejestrowanych urządzeniach z systemem Windows 10, zobacz Niestandardowe ustawienia identyfikatorów URI dla urządzeń z systemem Windows 10 poniżej w tym temacie.

### Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę zasad, która ułatwi ich identyfikację w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad oraz inne istotne informacje ułatwiające ich wyszukanie.|

### Ustawienia OMA-URI

|Nazwa ustawienia|Szczegóły|
    |--------|--------------------|
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację  na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz spośród opcji:<br /><br />-   **String**<br />-   **Ciąg (XML)**<br />-   **Data i godzina**<br />-   **Integer**<br />-   **Liczba zmiennoprzecinkowa**<br />-   **Boolean**|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|


## Niestandardowe ustawienia identyfikatorów URI dla urządzeń z systemem Windows 10
Ten temat zawiera listę ustawień, które można skonfigurować dla urządzeń z systemem Windows 10 i Windows 10 Mobile w **niestandardowych zasadach systemu Windows 10** usługi Microsoft Intune..


> [!NOTE]
> W kolumnie **Obsługuje** poniższej tabeli są używane następujące wartości:
> 
> -   **Komputery** — ustawienie obsługuje tylko komputery z systemem Windows 10 Professional i Enterprise zarejestrowane w usłudze Intune.
> -   **Urządzenia przenośne** — ustawienie obsługuje tylko urządzenia z systemem Windows 10 Mobile.
> -   **Oba** — ustawienie obsługuje komputery i urządzenia przenośne.
> 
> Aby korzystać z niestandardowych zasad identyfikatorów URI systemu Windows, wszystkie urządzenia muszą być zarejestrowane w usłudze Intune.

### Zasady

|Nazwa zasad|Obsługuje|Szczegóły|
|---------------|------------|-----------|
|**​Zezwalaj na automatyczne aktualizacje**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** - **5**<br /><br />**Wartość domyślna:** 1|
|**Planowany dzień instalacji**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — codziennie<br /><br />**1** — niedziela<br /><br />**2** — poniedziałek<br /><br />**3** — wtorek<br /><br />**4** — środa<br /><br />**5** — czwartek<br /><br />**6** — piątek<br /><br />**7** — sobota<br /><br />**Wartość domyślna:** 0|
|**Planowana godzina instalacji**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0**–**23** godz. (0 oznacza północ)<br /><br />**Wartość domyślna:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — użytkownik nie może ustawić czasomierza okresu karencji hasła, a wartość jest ustawiana jako „za każdym razem”.<br /><br />**1** — użytkownik może ustawić czasomierz okresu karencji hasła.<br /><br />**Wartość domyślna:** 1|
|**WiFi/AllowWiFi**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie zezwalaj na **używanie połączenia Wi-Fi**.<br /><br />**1** — **zezwalaj na używanie połączenia Wi-Fi**.<br /><br />**Wartość domyślna:** 1|
|**WiFi/AllowInternetSharing**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie zezwalaj na udostępnianie Internetu.<br /><br />**1** — zezwalaj na udostępnianie Internetu.<br /><br />**Wartość domyślna:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie jest dozwolone żadne połączenie Wi-Fi poza aprowizowanym przez oprogramowanie do zarządzania urządzeniami przenośnymi.<br /><br />**1** — dodawanie nowych identyfikatorów SSID sieci poza już skonfigurowanymi przez oprogramowanie MDM jest dozwolone.<br /><br />**Wartość domyślna:** 1|
|**System/AllowLocation**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**System/AllowTelemetry**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone (ustawienie tylko dla wersji Enterprise)<br /><br />**1** — ograniczone<br /><br />**2** — pełne<br /><br />**3** — informacje pełne i diagnostyczne<br /><br />**Wartość domyślna:** 2|
|**System/AllowExperimentation**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — tylko ustawienia<br /><br />**2** — ustawienia i eksperymenty<br /><br />**Wartość domyślna:** 1|
|**Security/AntiTheftMode**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie zezwalaj na tryb antykradzieżowy<br /><br />**1** — preferencja użytkownika<br /><br />**Wartość domyślna:** 1|
|**Connectivity/AllowUSBConnection**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**System/AllowUserToResetPhone**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Connectivity/AllowCellularDataRoaming**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Connectivity/AllowVPNOverCellular**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — używanie sieci VPN z połączeniem komórkowym jest niedozwolone.<br /><br />**1** — sieć VPN może używać dowolnego połączenia, w tym komórkowego.<br /><br />**Wartość domyślna:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Connectivity/AllowBluetooth**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie zezwalaj użytkownikowi na włączanie połączeń Bluetooth.<br /><br />**1** — zastrzeżone. Użytkownik może włączać i konfigurować połączenia Bluetooth (nieobsługiwane w przypadku protokołu EAS oraz systemów Windows Phone 8.1 dla rozwiązania MDM, Windows 10 Desktop i Windows 10 Mobile).<br /><br />**2** — dozwolone. Użytkownik może włączać i konfigurować połączenia Bluetooth.<br /><br />**Wartość domyślna:** 2|
|**Experience/AllowScreenCapture**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Experience/AllowTaskSwitcher**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Experience/AllowVoiceRecording**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Experience/AllowSyncMySettings**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie zezwalaj na roaming<br /><br />**1** — zezwalaj na roaming<br /><br />**Wartość domyślna:** 1|
|**Experience/AllowManualMDMUnenrollment**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Security/AllowManualRootCertificateInstallation**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Security/AllowAddProvisioningPackages**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Search/DisableBackoff**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 0|
|**Search/PreventRemoteQueries**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 1|
|**Search/AllowUsingDiacritics**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 0|
|**Search/AlwaysUseAutoLangDetection**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 0|
|**Search/DisableRemovableDriveIndexing**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 0|
|**Security/AllowRemoveProvisioningPackage**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Security/RequireProvisioningPackageSignature**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**<br /><br />**1**<br /><br />**Wartość domyślna:** 0|
|**AboveLock/AllowActionCenterNotifications**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowIMENetworkAccess**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — nie zezwalaj<br /><br />Otwarty słownik rozszerzony jest wyłączony.<br /><br />Użytkownik nie może:<br /><br />dodać nowego otwartego słownika rozszerzonego,<br /><br />dodać nowego pliku konfiguracji integracji wyszukiwania,<br /><br />używać funkcji kandydata z chmury,<br /><br />wysłać zastrzeżonego słowa użytkownika.<br /><br />Dodatkowo:<br /><br />Otwarty słownik rozszerzony dodany przed włączeniem tego ustawienia zasad nie będzie używany na potrzeby konwersji.<br /><br />Plik konfiguracji integracji wyszukiwania zainstalowany przed włączeniem tego ustawienia zasad nie będzie używany.<br /><br />**1** — zezwalaj<br /><br />Otwarty słownik rozszerzony może być dodany i używany domyślnie. Domyślnie można również używać funkcji integracji wyszukiwania.<br /><br />Użytkownik może:<br /><br />używać funkcji kandydata z chmury,<br /><br />wysłać zastrzeżonego słowa użytkownika.<br /><br />**Wartość domyślna:**|
|**TextInput/AllowKoreanExtendedHanja**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowIMELogging**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — rejestrowanie błędów konwersji jest wyłączone. Automatycznie dopasowane dane i historyczne dane wejściowe nie są zapisywane w pliku.<br /><br />**1** — rejestrowanie błędów konwersji jest włączone. Automatycznie dopasowane dane i historyczne dane wejściowe są zapisywane w pliku.<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowJapaneseUserDictionary**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — wszystkie znaki oprócz znaków JIS są filtrowane.<br /><br />**1** — żadne znaki nie są filtrowane.<br /><br />**Wartość domyślna:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — wszystkie znaki oprócz znaków JIS0208 są filtrowane.<br /><br />**1** — żadne znaki nie są filtrowane.<br /><br />**Wartość domyślna:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — wszystkie znaki oprócz znaków JIS0208 lub EUDC są filtrowane.<br /><br />**1** — żadne znaki nie są filtrowane.<br /><br />**Wartość domyślna:** 1|
|**TextInput/AllowInputPanel**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Bluetooth/AllowDiscoverableMode**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Bluetooth/AllowAdvertising**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowDataSense**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowVPN**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowWorkplace**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowDateTime**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowLanguage**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowRegion**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowSignInOptions**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowYourAccount**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowPowerSleep**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Settings/AllowAutoPlay**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Experience/AllowCortana**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Search/SafeSearchPermissions**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — ścisłe, najwyższy poziom filtrowania pod kątem blokowania treści dla dorosłych<br /><br />**1** — umiarkowane, średni poziom filtrowania pod kątem blokowania treści dla dorosłych (prawidłowe wyniki wyszukiwania nie będą filtrowane)<br /><br />**Wartość domyślna:** 1|
|**Experience/AllowCopyPaste**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**Wymuś początkowy rozmiar**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — zezwalaj na zmianę rozmiaru przez użytkownika<br /><br />**1** — wymuś niepełny ekran<br /><br />**2** — wymuś pełny ekran<br /><br />**Wartość domyślna:** 0|
|**Update/RequireDeferUpgrade**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**: nie odraczaj uaktualnienia (pozostań w wersji Current Branch)<br /><br />**1**: zezwalaj na odraczanie aktualizacji i uaktualnień (urządzenie pozostaje zgodne z regułami wersji Current Branch dla Firm)<br /><br />**Wartość domyślna: 0**<br /><br />Aby uzyskać więcej informacji, zobacz:<br /><br />[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Oba|**Opis:** zasady umożliwiające odroczenie aktualizacji oprogramowania na maksymalnie 4 tygodnie.<br /><br />**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:** 0: zastosuj aktualizacje od razu; 1–4: liczba tygodni odroczenia aktualizacji oprogramowania.<br /><br />**Wartość domyślna: 0**<br /><br /><br />Aby uzyskać więcej informacji, zobacz:<br /><br />[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Oba|**Opis:** zasady umożliwiające odroczenie uaktualnień funkcji na maksymalnie 8 miesięcy.<br /><br />**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:** 0: zastosuj aktualizacje od razu; 1–8: liczba miesięcy odroczenia uaktualnienia funkcji.<br /><br />**Wartość domyślna: 0**<br /><br />Aby uzyskać więcej informacji, zobacz:<br /><br />[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Oba|**Opis:** zezwala na zatrzymanie otrzymywania aktualizacji i uaktualnień przez maszynę z systemem Current Branch dla Firm na okres maksymalnie 5 tygodni. Tej opcji należy używać w przypadku, gdy występuje problem z aktualizacją.<br /><br />**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0**: zastosuj aktualizacje od razu (domyślnie)<br /><br />**1**: wstrzymaj aktualizacje i uaktualnienia (wygasa po 5 tygodniach)<br /><br />**Wartość domyślna: 0**|

### Usługa Windows Defender

|Nazwa zasad|Obsługuje|Szczegóły|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowBehaviorMonitoring**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowIntrusionPreventionSystem**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowIOAVProtection**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowScriptScanning**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowOnAccessProtection**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**RealTimeScanDirection**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — monitoruj wszystkie pliki (dwukierunkowo)<br /><br />**1** — monitoruj pliki przychodzące<br /><br />**2** — monitoruj pliki wychodzące<br /><br />**Wartość domyślna:** 0|
|**DaysToRetainCleanedMalware**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** - **90** — reprezentuje czas zachowywania złośliwego oprogramowania<br /><br />**Wartość domyślna:** 0 — elementy w folderze kwarantanny będą przechowywane bez ograniczeń i nie będą usuwane automatycznie|
|**AllowUserUIAccess**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**ScanParameter**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**1** — szybkie skanowanie<br /><br />**2** — pełne skanowanie<br /><br />**Wartość domyślna:** 1|
|**ScheduleScanDay**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — codzienne<br /><br />**1** — poniedziałek<br /><br />**2** — wtorek<br /><br />**3** — środa<br /><br />**4** — czwartek<br /><br />**5** — piątek<br /><br />**6** — sobota<br /><br />**7** — niedziela<br /><br />**8** — brak zaplanowanego skanowania<br /><br />**Wartość domyślna:** 0|
|**ScheduleScanTime**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — 12:00<br /><br />**60** — 1:00<br /><br />**120** — 2:00<br /><br />**180** — 3:00<br /><br />**240** — 4:00<br /><br />**300** — 5:00<br /><br />**360** — 6:00<br /><br />**420** — 7:00<br /><br />**480** — 8:00<br /><br />**540** — 9:00<br /><br />**600** — 10:00<br /><br />**660** — 11:00<br /><br />**720** — 12:00<br /><br />**780** — 13:00<br /><br />**840** — 14:00<br /><br />**900** — 15:00<br /><br />**960** — 16:00<br /><br />**1020** — 17:00<br /><br />**1080** — 18:00<br /><br />**1140** — 19:00<br /><br />**1200** — 20:00<br /><br />**1260** — 21:00<br /><br />**1320** — 22:00<br /><br />**1381** — okno obsługi<br /><br />**Wartość domyślna:** 120|
|**ScheduleQuickScanTime**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — 12:00<br /><br />**60** — 1:00<br /><br />**120** — 2:00<br /><br />**180** — 3:00<br /><br />**240** — 4:00<br /><br />**300** — 5:00<br /><br />**360** — 6:00<br /><br />**420** — 7:00<br /><br />**480** — 8:00<br /><br />**540** — 9:00<br /><br />**600** — 10:00<br /><br />**660** — 11:00<br /><br />**720** — 12:00<br /><br />**780** — 13:00<br /><br />**840** — 14:00<br /><br />**900** — 15:00<br /><br />**960** — 16:00<br /><br />**1020** — 17:00<br /><br />**1080** — 18:00<br /><br />**1140** — 19:00<br /><br />**1200** — 20:00<br /><br />**1260** — 21:00<br /><br />**1320** — 22:00<br /><br />**1380** — 23:00<br /><br />**Wartość domyślna:** 120|
|**AVGCPULoadFactor**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** - **100**<br /><br />**Wartość domyślna:** 50|
|**AllowArchiveScanning**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowEmailScanning**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 0|
|**AllowFullScanRemovableDriveScanning**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 0|
|**AllowFullScanOnMappedNetworkDrives**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**AllowScanningNetworkFiles**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1 — jeśli dozwolone, jest również uruchamiane przy włączonym RTP|
|**SignatureUpdateInterval**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — bez sprawdzania podpisów co określony czas<br /><br />**1** — sprawdzaj sygnatury co godzinę<br /><br />**2** — sprawdzaj podpisy co 2 godziny itd.<br /><br />**24** — sprawdzaj podpisy codziennie<br /><br />**Wartość domyślna:** 8 — sprawdzaj podpisy co 8 godzin|
|**AllowCloudProtection**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — niedozwolone<br /><br />**1** — dozwolone<br /><br />**Wartość domyślna:** 1|
|**SubmitSamplesConsent**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości:**<br /><br />**0** — zawsze pytaj<br /><br />**1** — automatycznie wyślij bezpieczne próbki<br /><br />**2** — nigdy nie wysyłaj<br /><br />**3** — wyślij wszystkie próbki automatycznie<br /><br />**Wartość domyślna:** 0|
|**ExcludedExtensions**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości:**<br /><br />*&lt;lista rozszerzeń rozdzielonych średnikami&gt;*, np. **obj;lib**<br /><br />**Wartość domyślna:** brak wykluczonych rozszerzeń|
|**ExcludedPaths**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości:**<br /><br />*&lt;lista ścieżek rozdzielonych średnikami&gt;*<br /><br />Przykład: **c:\test;c:\test1.exe**<br /><br />**Wartość domyślna:** brak wykluczonych ścieżek|
|**ExcludedProcesses**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości:**<br /><br />*&lt;lista ścieżek rozdzielonych średnikami&gt;*<br /><br />Przykład: **c:\test.exe;c:\test1.exe**<br /><br />**Wartość domyślna:** brak wykluczonych procesów|

### Przeglądarka Edge

|Nazwa zasad|Obsługuje|Szczegóły|
|---------------|------------|-----------|
|**Zezwalaj na przeglądarkę**|Urządzenia przenośne|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0**: przeglądanie wyłączone; **1**: przeglądanie włączone.<br /><br />**Wartość domyślna:** 1|
|**AllowSearchSuggestionsinAddressBar**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0**: nie pokazuj podpowiedzi podczas wyszukiwania; **1**: pokazuj podpowiedzi podczas wyszukiwania.<br /><br />**Wartość domyślna:** 1|
|**SendIntranetTraffictoInternetExplorer**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0**: wyłączone (otwieranie witryn intranetowych w przeglądarce Edge); **1**: włączone (otwieranie witryn intranetowych w przeglądarce Internet Explorer).<br /><br />**Wartość domyślna:** 0|
|**Zezwalaj na żądania Nie śledź**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** — wyłączone (identyfikator DNT nie jest wysyłany); **1** — włączone (wysyłaj identyfikator DNT)<br /><br />**Wartość domyślna:** 0|
|**Skonfiguruj funkcję SmartScreen**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** — nie zezwalaj; **1** — zezwalaj<br /><br />**Wartość domyślna:** 1|
|**Zezwalaj na wyskakujące okienka**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** — blokuj wyskakujące okienka; **1** — zezwalaj na wyskakujące okienka<br /><br />**Wartość domyślna:** 0|
|**Zezwalaj na pliki cookie**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** — nie blokuj. Zezwalaj na pliki cookie ze wszystkich witryn sieci Web; **1** — blokuj tylko pliki cookie innych firm; **2** — blokuj wszystkie pliki cookie<br /><br />**Wartość domyślna:** 0|
|**Zezwalaj na zapisywanie haseł**|Oba|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** — menedżer haseł jest wyłączony; <br />                        **1** — menedżer haseł jest włączony<br /><br />**Wartość domyślna:** 1|
|**Zezwalaj na autowypełnianie**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Typ danych:** liczba całkowita<br /><br />**Dozwolone wartości: 0** — wyłączone; **1** — włączone<br /><br />**Wartość domyślna:** 0|
|**Skonfiguruj listę witryn przedsiębiorstwa**|Komputery|**Pełna ścieżka identyfikatora URI:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Typ danych:** ciąg<br /><br />**Dozwolone wartości: 0** — nieskonfigurowane; **1** — użyj listy witryn trybu przedsiębiorstwa IE, jeśli jest skonfigurowana; **2** — określ lokalizację listy witryn przedsiębiorstwa<br /><br />**Wartość domyślna:** 1|

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


