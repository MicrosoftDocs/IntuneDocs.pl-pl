---
title: "Ustawienia ograniczeń urządzenia z systemem Windows 10 w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji urządzeń z systemem Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 43c2c517dffbb6b2e7b654c5ca8a0ad9062683eb
ms.lasthandoff: 04/19/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Ogólne
-     **Przechwytywanie ekranu (tylko dla urządzeń przenośnych)** — umożliwia użytkownikowi przechwycenie ekranu urządzenia w formie obrazu.
-     **Kopiuj i wklej (tylko urządzenia przenośne)** — umożliwia kopiowanie i wklejanie między aplikacjami na urządzeniu.
-     **Ręczne wyrejestrowanie**— umożliwia użytkownikowi ręczne usunięcie konta firmowego z urządzenia.
-     **Ręczne instalowanie certyfikatu głównego (tylko dla urządzeń przenośnych)** — uniemożliwia użytkownikowi ręczne instalowanie certyfikatów głównych i certyfikatów pośrednich urzędów certyfikacji.
-     **Przesyłanie danych diagnostycznych** — możliwe wartości to:
    -         **Brak** — do firmy Microsoft nie są wysyłane żadne dane.
    -         **Podstawowe** — do firmy Microsoft są wysyłane ograniczone informacje.
    -         **Rozszerzone** — do firmy Microsoft są wysyłane rozszerzone dane diagnostyczne.
    -         **Pełne** — wysyłane są te same dane, co w przypadku wartości Rozszerzone, oraz dodatkowe dane dotyczące stanu urządzenia.
-     **Aparat fotograficzny** — umożliwia lub blokuje użycie aparatu fotograficznego urządzenia.
-     **Synchronizacja plików w usłudze OneDrive** — uniemożliwia synchronizowanie plików z urządzenia z usługą OneDrive.
-     **Magazyn wymienny** — określa, czy na urządzeniu można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD.
-     **Geolokalizacja** — określa, czy urządzenie może używać informacji z usług lokalizacyjnych.
-     **Udostępnianie Internetu** — umożliwia udostępnianie połączenia internetowego przy użyciu urządzenia.
-     **Resetowanie telefonu** — określa, czy użytkownik może zresetować urządzenie do ustawień fabrycznych.
-     **Połączenie USB (tylko dla urządzeń przenośnych)** — określa, czy urządzenia mogą uzyskiwać dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.
-     **Tryb przeciwkradzieżowy (tylko na urządzeniach przenośnych)** — pozwala określić, czy jest włączony tryb przeciwkradzieżowy systemu Windows.
-     **Powiadomienia centrum akcji (tylko dla urządzeń przenośnych)** — włącza lub wyłącza powiadomienia centrum akcji na ekranie blokady urządzenia (tylko system Windows 10 Mobile).
-     **Cortana** — włącza lub wyłącza asystenta głosowego Cortana.
-     **Nagrywanie głosu (tylko dla urządzeń przenośnych)** — umożliwia lub blokuje użycie rejestratora głosu na urządzeniu.
-     **Modyfikowanie ustawień zasilania i uśpienia (tylko dla komputerów stacjonarnych)** — uniemożliwia zmianę ustawień zasilania i uśpienia na urządzeniu przez użytkownika końcowego.
-     **Modyfikowanie ustawień regionu (tylko komputer)** — uniemożliwia zmianę ustawień regionu na urządzeniu przez użytkownika końcowego.
-     **Modyfikowanie ustawień języka (tylko komputer)** — uniemożliwia zmianę ustawień języka na urządzeniu przez użytkownika.
-     **Modyfikowanie czasu systemowego** — uniemożliwia użytkownikowi końcowemu zmianę daty i godziny na urządzeniu.
-     **Modyfikowanie nazwy urządzenia** — uniemożliwia użytkownikowi końcowemu zmianę nazwy urządzenia.
-     **Dodaj pakiety aprowizacji** — blokuje agenta konfiguracji środowiska uruchomieniowego, który instaluje pakiety aprowizacji.
-     **Usuń pakiety aprowizacji** — blokuje agenta konfiguracji środowiska uruchomieniowego, który usuwa pakiety aprowizacji.
-     **Odnajdywanie urządzeń** — blokuje wykrywanie urządzenia przez inne urządzenia.
-     **Przełącznik zadań (tylko urządzenia przenośne)** — blokuje przełącznik zadań na urządzeniu.
-     **Okno dialogowe błędu karty SIM (tylko urządzenia przenośne)** — w przypadku, gdy karta SIM nie zostanie wykryta, blokuje wyświetlanie komunikatu o błędzie na urządzeniu.


## <a name="password"></a>Hasło
-     **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -     **Wymagany typ hasła** — określa, czy hasło musi być wyłącznie numeryczne, czy też alfanumeryczne.
    -     **Minimalna długość hasła** — dotyczy tylko systemu Windows 10 Mobile.
    -     **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — jeśli na urządzeniu z systemem Windows 10 jest włączona funkcja BitLocker, po określonej liczbie nieudanych prób logowania zostanie ono przełączone w tryb odzyskiwania funkcji BitLocker. Jeśli na urządzeniu nie jest włączona funkcja BitLocker, to ustawienie nie będzie miało zastosowania.
Na urządzeniach z systemem Windows 10 Mobile: po określonej liczbie niepowodzeń logowania urządzenie zostanie wyczyszczone.
    -     **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
    -     **Wygaśnięcie hasła (dni)** — określa czas, po którym należy zmienić hasło urządzenia.
    -     **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.
    -     **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności** — określa, że użytkownik musi wprowadzić hasło, aby odblokować urządzenie (tylko system Windows 10 Mobile).
-     **Szyfrowanie** — włącza szyfrowanie na urządzeniach docelowych (tylko system Windows 10 Mobile).

## <a name="personalization"></a>Personalizacja

-     **Adres URL obrazu tła pulpitu (tylko dla komputerów stacjonarnych)** — pozwala określić adres URL obrazu w formacie PNG, JPG lub JPEG, który będzie używany jako tapeta pulpitu systemu Windows. Użytkownicy nie będą mogli zmienić tego ustawienia.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

-     **Adres URL obrazu ekranu blokady (tylko dla komputerów stacjonarnych)** — pozwala określić adres URL obrazu w formacie PNG, JPG lub JPEG, który będzie używany jako tapeta ekranu blokady systemu Windows. Użytkownicy nie będą mogli zmienić tego ustawienia.


## <a name="app-store"></a>App Store

-     **App Store (tylko dla urządzeń przenośnych)** — umożliwia lub blokuje korzystanie ze sklepu z aplikacjami na urządzeniach z systemem Windows 10 Mobile.
-     **Automatycznie aktualizuj aplikacje ze sklepu** — umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze Sklepu Windows.
-     **Instalacja aplikacji zaufanej** — umożliwia ładowanie bezpośrednie aplikacji podpisanych za pomocą zaufanego certyfikatu.
-     **Odblokowanie trybu deweloperskiego** — umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, np. z ustawienia umożliwiającego użytkownikowi końcowemu modyfikację aplikacji ładowanych bezpośrednio.
-     **Współużytkowane dane aplikacji użytkownika** — umożliwia aplikacjom udostępnianie danych różnym użytkownikom na tym samym urządzeniu.
-     **Używaj tylko sklepu prywatnego** — po włączeniu tego ustawienia użytkownicy końcowi będą mogli pobierać aplikacje wyłącznie z udostępnionego im sklepu prywatnego.
-     **Uruchamianie aplikacji pochodzącej ze sklepu** — ustawienie pozwala wyłączyć wszystkie aplikacje, które zostały wcześniej zainstalowane na urządzeniu lub pobrane ze Sklepu Windows.
-     **Instaluj dane aplikacji na woluminie systemowym** — uniemożliwia aplikacjom przechowywanie danych na woluminie systemowym urządzenia.
-     **Instaluj aplikacje na dysku systemowym** — uniemożliwia aplikacjom przechowywanie danych na dysku systemowym urządzenia.
-     **DVR z gry (tylko dla komputerów stacjonarnych)** — pozwala określić, czy nagrania i emisje z gier są dozwolone.



## <a name="edge-browser"></a>Przeglądarka Microsoft Edge
-     **Przeglądarka Microsoft Edge (tylko urządzenia przenośne)** — umożliwia korzystanie z przeglądarki Edge na urządzeniu.
-     **SmartScreen** — włącza lub wyłącza filtr SmartScreen, który blokuje fałszywe witryny sieci Web.
-     **Wysyłaj nagłówki Nie śledź** — umożliwia skonfigurowanie przeglądarki Edge do wysyłania nagłówków „Nie śledź” do witryn sieci Web odwiedzanych przez użytkowników.
-     **Pliki cookie** — umożliwia przeglądarce na urządzeniu zapisywanie plików cookie z Internetu.
-     **JavaScript** — umożliwia uruchamianie skryptów (takich jak JavaScript) w przeglądarce Edge.
-     **Wyskakujące okienka** — umożliwia blokowanie wyskakujących okienek w przeglądarce (tylko system Windows 10 Desktop).
-     **Sugestie wyszukiwania** — umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz.
-     **Wysyłaj ruch intranetowy do programu Internet Explorer** — umożliwia użytkownikom otwieranie intranetowych witryn sieci Web w programie Internet Explorer (tylko system Windows 10 Desktop).
-     **Autowypełnianie** — umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce (tylko system Windows 10 Desktop).
-     **Menedżer haseł** — włącza lub wyłącza funkcję menedżera haseł w przeglądarce Edge.
-     **Lokalizacja listy witryn trybu przedsiębiorstwa** — określa lokalizację listy witryn sieci Web, które można otwierać w trybie przedsiębiorstwa. Użytkownicy nie mogą edytować tej listy.<br>(Tylko system Windows 10 Desktop).
-     **Narzędzia programistyczne** — uniemożliwia użytkownikowi końcowemu otwieranie narzędzi programistycznych przeglądarki Edge.
-     **Rozszerzenia** — umożliwia użytkownikowi końcowemu instalowanie rozszerzeń przeglądarki Edge na urządzeniu.
-     **Przeglądanie InPrivate** — uniemożliwia otwieranie sesji przeglądania InPrivate przez użytkownika końcowego.
-     **Adres URL pierwszego uruchomienia** — umożliwia wpisanie adresu URL, który zostanie otwarty przy pierwszym uruchomieniu przeglądarki Edge (tylko urządzenia przenośne).
-     **Strony główne** — umożliwia dodanie listy witryn, które będą używane jako strony główne w przeglądarce Edge (tylko dla komputerów stacjonarnych).
-     **Blokuj dostęp do flag informacji** — uniemożliwia użytkownikowi końcowemu uzyskanie dostępu do strony about:flags przeglądarki Edge zawierającej ustawienia programistyczne i eksperymentalne.
-     **Przesłonięcie monitu filtru SmartScreen** — umożliwia użytkownikowi pominięcie ostrzeżeń filtru SmartScreen o potencjalnie złośliwych witrynach sieci Web.
-     **Przesłonięcie monitu filtru SmartScreen dla plików** — umożliwia użytkownikowi pominięcie ostrzeżeń filtru SmartScreen dotyczących pobierania potencjalnie złośliwych plików.
-     **Adres IP lokalnego hosta dla protokołu WebRTC** — blokuje wyświetlanie adresu IP lokalnego hosta użytkownika podczas nawiązywania połączeń telefonicznych przy użyciu protokołu WebRTC.
-     **Domyślna wyszukiwarka** — pozwala określić domyślną wyszukiwarkę. Użytkownicy końcowi mogą w dowolnym momencie zmienić tę wartość.

## <a name="search"></a>Wyszukaj
- **Bezpieczne wyszukiwanie (tylko urządzenia przenośne)** — pozwala określić sposób, w jaki Cortana filtruje treści dla dorosłych w wynikach wyszukiwania. Można wybrać opcję **Ścisłe** lub **Umiarkowane** albo zezwolić użytkownikom końcowym na wybór własnych ustawień.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-     **Konto Microsoft** — umożliwia użytkownikowi skojarzenie konta Microsoft z urządzeniem.
-     **Konto inne niż Microsoft** — umożliwia użytkownikowi dodanie na urządzeniu kont poczty e-mail, które nie są skojarzone z kontem Microsoft.
-     **Synchronizacja ustawień dla konta Microsoft** — zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między różnymi urządzeniami.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność
-     **Roaming danych** — umożliwia roaming między sieciami podczas uzyskiwania dostępu do danych.
-     **Sieć VPN przez sieć komórkową** — określa, czy urządzenie połączone z siecią komórkową może uzyskiwać dostęp do sieci VPN.
-     **Roaming sieci VPN przez sieć komórkową** — określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.
-     **Bluetooth** — określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
-     **Odnajdowanie Bluetooth** — umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
-     **Rozgłaszanie Bluetooth** — umożliwia odbieranie reklam przez urządzenie za pośrednictwem połączenia Bluetooth.
-     **Nazwa urządzenia Bluetooth** — pozwala określić nazwę urządzenia Bluetooth.
-     **NFC** — umożliwia użytkownikowi włączanie i konfigurowanie funkcji komunikacji zbliżeniowej na urządzeniu.
-     **Wi-Fi** — umożliwia użytkownikowi włączanie i konfigurowanie sieci Wi-Fi na urządzeniu (tylko system Windows 10 Mobile).
-     **Automatycznie łącz się z hotspotami Wi-Fi** — umożliwia automatyczne łączenie się przy użyciu urządzenia z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.
-     **Ręczna konfiguracja sieci Wi-Fi** — określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi (tylko system Windows 10 Mobile).
-     **Interwał skanowania sieci Wi-Fi** — pozwala określić, jak często urządzenie ma skanować w poszukiwaniu sieci Wi-Fi.

## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

-     **Aplikacja Ustawienia** — blokuje dostęp do aplikacji Ustawienia systemu Windows.
    -     **System** — blokuje dostęp do obszaru systemu w aplikacji Ustawienia.
    -     **Urządzenia** — blokuje dostęp do obszaru urządzeń w aplikacji Ustawienia.
    -     **Sieć i Internet** — blokuje dostęp do obszaru sieci i Internetu w aplikacji Ustawienia.
    -     **Personalizacja** — blokuje dostęp do obszaru personalizacji w aplikacji Ustawienia.
    -     **Konta** — blokuje dostęp do obszaru kont w aplikacji Ustawienia.
    -     **Czas i język** — blokuje dostęp do obszaru czasu i języka w aplikacji Ustawienia.
    -     **Ułatwienia dostępu** — blokuje dostęp do obszaru ułatwień dostępu w aplikacji Ustawienia.
    -     **Prywatność** — blokuje dostęp do obszaru prywatności w aplikacji Ustawienia.
    -     **Aktualizacja i zabezpieczenia** — blokuje dostęp do obszaru aktualizacji i zabezpieczeń w aplikacji Ustawienia.

## <a name="defender"></a>Usługa Defender

-     **Monitorowanie w czasie rzeczywistym** — włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.
-     **Monitorowanie zachowania** — umożliwia usłudze Defender sprawdzanie urządzeń pod kątem określonych wzorców podejrzanej aktywności.
-     **Network Inspection System (NIS)** — system inspekcji sieci (NIS, Network Inspection System) zapewnia ochronę urządzenia przed sieciowymi programami wykorzystującymi luki w zabezpieczeniach, używając sygnatur znanych luk w zabezpieczeniach z centrum Microsoft Endpoint Protection, co pomaga wykrywać i blokować ruch złośliwego oprogramowania.
-     **Skanuj wszystkie pobrane pliki** — określa, czy usługa Defender ma skanować wszystkie pliki pobierane z Internetu.
-     **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft** — umożliwia usłudze Defender skanowanie skryptów używanych przez przeglądarkę Internet Explorer.
-     **Dostęp użytkownika końcowego do narzędzia Defender** — określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych.
Jeśli to ustawienie zostanie zmienione, zmiany zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika końcowego.
-     **Interwał aktualizacji sygnatur (w godzinach)** — określa interwał sprawdzania dostępności nowych plików sygnatur przez usługę Defender.
-     **Monitoruj działanie plików i programów** — zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach.
-     **Dni przed usunięciem złośliwego oprogramowania poddanego kwarantannie** — umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane.
-     **Limit wykorzystania procesora CPU podczas skanowania** —pozwala ograniczyć użycie procesora CPU dozwolone dla procesów skanowania (w skali od **1** do **100**).
-     **Skanuj pliki archiwów** — zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.
-     **Skanuj przychodzące wiadomości e-mail** — zezwala usłudze Defender na skanowanie wiadomości e-mail dostarczanych do urządzenia.
-     **Skanuj dyski wymienne podczas pełnego skanowania** —umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.
-     **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania** — umożliwia usłudze Defender skanowanie plików na zamapowanych dyskach sieciowych.<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
-     **Skanuj pliki otwierane z folderów sieciowych** — umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach dostępnych za pośrednictwem ścieżki UNC).
Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
-     **Ochrona w chmurze** — zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.
-     **Monituj użytkowników przed przesłaniem próbki** — określa, czy do firmy Microsoft są automatycznie wysyłane pliki, które mogą wymagać dalszej analizy ze strony firmy Microsoft w celu określenia, czy są złośliwe.
-     **Godzina przeprowadzania codziennego szybkiego skanowania** — umożliwia zaplanowanie szybkiego skanowania wykonywanego codziennie o wybranej godzinie.
-     **Typ skanowania systemu do wykonania** — pozwala określić poziom skanowania wykonywanego w przypadku planowania skanowania systemu.

## <a name="defender-exclusions"></a>Wykluczenia programu Defender

-     **Pliki i foldery do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych plików lub folderów lub większej ich liczby, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.
-     **Rozszerzenia plików do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych rozszerzeń plików lub większej ich liczby, np. **JPG** lub **TXT**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym lub skanowania planowanego.
-     **Procesy do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych procesów typu **EXE**, **COM** lub **SCR** lub większej ich liczby. Te procesy nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.


## <a name="network-proxy"></a>Serwer proxy sieci

-     **Automatycznie wykrywaj ustawienia proxy** — po włączeniu tego ustawienia urządzenie spróbuje znaleźć ścieżkę do skryptu PAC.
-     **Użyj skryptu serwera proxy** — zaznacz tę opcję, jeśli chcesz określić ścieżkę do skryptu PAC, aby skonfigurować serwer proxy.
    -     **Adres URL skryptu konfiguracji** — wprowadź adres URL skryptu PAC, którego chcesz użyć do skonfigurowania serwera proxy.
-     **Użyj ręcznego serwera proxy** — wybierz tę opcję, jeśli chcesz ręcznie wprowadzać informacje o serwerze proxy.
    -     **Adres** — wprowadź nazwę lub adres IP serwera proxy.
    -     **Numer portu** — wprowadź numer portu serwera proxy.
    -     **Wyjątki serwera proxy** — wprowadź wszystkie adresy URL, w przypadku których korzystanie z serwera proxy będzie zabronione. Rozdziel kolejne elementy średnikiem.
    -     **Pomiń serwer proxy dla adresów lokalnych** — włącz tę opcję, jeśli nie chcesz używać serwera proxy dla adresów lokalnych w sieci intranet.


## <a name="windows-spotlight"></a>W centrum uwagi Windows

-     **W centrum uwagi Windows** — pozwala zezwolić na użycie funkcji W centrum uwagi Windows lub zablokować ją. Funkcja W centrum uwagi Windows zapewnia dostęp do porad i wskazówek, wiadomości na ekranie blokady systemu Windows itp.
    -     **Porady dotyczące systemu Windows** — umożliwia zablokowanie wyskakujących okienek z poradami w systemie Windows.
    -     **Funkcje dla konsumentów** — umożliwia blokowanie funkcji dla konsumentów, takich jak sugestie w menu Start, powiadomienia dotyczące członkostwa itp.

## <a name="display"></a>Wyświetlanie

- **Dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych** — blokuje dane wejściowe użytkownika z odbiorników wyświetlaczy bezprzewodowych.
- **Projekcja na tym komputerze** — uniemożliwia innym urządzeniom odnajdywanie tego komputera dla celów projekcji.
- **Wymagaj numeru PIN do parowania** — wybór powoduje, że podczas nawiązywania połączenia z urządzeniem do projekcji wymagane jest podanie numeru PIN.

## <a name="start"></a>Początek

- **Odpinanie aplikacji od paska zadań** — uniemożliwia użytkownikowi odpinanie aplikacji od menu Start.
- **Folder Dokumenty w menu Start** — pozwala ukryć lub pokazać folder Dokumenty w menu Start systemu Windows.
- **Folder Pliki do pobrania w menu Start** — pozwala ukryć lub pokazać folder pobranych plików w menu Start systemu Windows.
- **Folder Eksplorator plików w menu Start** — pozwala ukryć lub pokazać aplikację Eksplorator plików w menu Start systemu Windows.
- **Folder Grupa domowa w menu Start** — pozwala ukryć lub pokazać folder Grupa domowa w menu Start systemu Windows.
- **Folder Muzyka w menu Start** — pozwala ukryć lub pokazać folder Muzyka w menu Start systemu Windows.
- **Folder Sieć w menu Start** — pozwala ukryć lub pokazać folder Sieć w menu Start systemu Windows.
- **Folder Osobiste w menu Start** — pozwala ukryć lub pokazać folder Osobiste w menu Start systemu Windows.
- **Folder Obrazy w menu Start** — pozwala ukryć lub pokazać folder obrazów w menu Start systemu Windows.
- **Folder Ustawienia w menu Start** — pozwala ukryć lub pokazać aplikację Ustawienia w menu Start systemu Windows.
- **Folder Wideo w menu Start** — pozwala ukryć lub pokazać folder Wideo w menu Start systemu Windows.
