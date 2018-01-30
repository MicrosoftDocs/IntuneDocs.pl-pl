---
title: "Ustawienia ograniczeń urządzenia z systemem Windows 10 w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem Windows 10."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/8/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cd446310256a71e7306364b4142bfacce482fe4
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Ogólne
- **Przechwytywanie ekranu (tylko dla urządzeń przenośnych)** — umożliwia użytkownikowi przechwycenie ekranu urządzenia w formie obrazu.
- **Kopiuj i wklej (tylko urządzenia przenośne)** — umożliwia kopiowanie i wklejanie między aplikacjami na urządzeniu.
- **Ręczne wyrejestrowanie**— umożliwia użytkownikowi ręczne usunięcie konta firmowego z urządzenia.
- **Ręczne instalowanie certyfikatu głównego (tylko dla urządzeń przenośnych)** — uniemożliwia użytkownikowi ręczne instalowanie certyfikatów głównych i certyfikatów pośrednich urzędów certyfikacji.
- **Przesyłanie danych diagnostycznych** — możliwe wartości to:
    - **Brak** — do firmy Microsoft nie są wysyłane żadne dane.
    - **Podstawowe** — ograniczone informacje są wysyłane do firmy Microsoft
    - **Rozszerzone** — do firmy Microsoft są wysyłane rozszerzone dane diagnostyczne.
    - **Pełne** — wysyłane są te same dane, co w przypadku wartości Rozszerzone, oraz dodatkowe dane dotyczące stanu urządzenia.
- **Aparat fotograficzny** — umożliwia lub blokuje użycie aparatu fotograficznego urządzenia.
- **Synchronizacja plików w usłudze OneDrive** — uniemożliwia synchronizowanie plików z urządzenia z usługą OneDrive.
- **Magazyn wymienny** — określa, czy na urządzeniu można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD.
- **Geolokalizacja** — określa, czy urządzenie może używać informacji z usług lokalizacyjnych.
- **Udostępnianie Internetu** — umożliwia udostępnianie połączenia internetowego przy użyciu urządzenia.
- **Resetowanie telefonu** — określa, czy użytkownik może zresetować urządzenie do ustawień fabrycznych.
- **Połączenie USB (tylko dla urządzeń przenośnych)** — określa, czy urządzenia mogą uzyskiwać dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.
- **Tryb przeciwkradzieżowy (tylko na urządzeniach przenośnych)** — pozwala określić, czy jest włączony tryb przeciwkradzieżowy systemu Windows.
- **Cortana** — włącza lub wyłącza asystenta głosowego Cortana.
- **Nagrywanie głosu (tylko dla urządzeń przenośnych)** — umożliwia lub blokuje użycie rejestratora głosu w urządzeniu.
- **Modyfikacja nazwy urządzenia** — uniemożliwia użytkownikowi końcowemu zmianę nazwy urządzenia (tylko system Windows 10 Mobile)
- **Dodaj pakiety aprowizacji** — blokuje agenta konfiguracji środowiska uruchomieniowego, który instaluje pakiety aprowizacji.
- **Usuń pakiety aprowizacji** — blokuje agenta konfiguracji środowiska uruchomieniowego, który usuwa pakiety aprowizacji.
- **Odnajdywanie urządzeń** — blokuje wykrywanie urządzenia przez inne urządzenia.
- **Przełącznik zadań (tylko urządzenia przenośne)** — blokuje przełącznik zadań na urządzeniu.
- **Okno dialogowe błędu karty SIM (tylko urządzenia przenośne)** — w przypadku, gdy karta SIM nie zostanie wykryta, blokuje wyświetlanie komunikatu o błędzie na urządzeniu.
- **Automatyczne ponowne wdrażanie** — pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania.


## <a name="password"></a>Hasło
-   **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -   **Wymagany typ hasła** — określa, czy hasło musi być wyłącznie numeryczne, czy też alfanumeryczne.
    -   **Minimalna długość hasła** — dotyczy tylko systemu Windows 10 Mobile.
    -   **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — jeśli na urządzeniu z systemem Windows 10 jest włączona funkcja BitLocker, po określonej liczbie nieudanych prób logowania zostanie ono przełączone w tryb odzyskiwania funkcji BitLocker. Jeśli na urządzeniu nie jest włączona funkcja BitLocker, to ustawienie nie będzie miało zastosowania.
Na urządzeniach z systemem Windows 10 Mobile: po określonej liczbie niepowodzeń logowania urządzenie zostanie wyczyszczone.
    -   **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
    -   **Wygaśnięcie hasła (dni)** — określa czas, po którym należy zmienić hasło urządzenia.
    -   **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.
    -   **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności** — określa, że użytkownik musi wprowadzić hasło, aby odblokować urządzenie (tylko system Windows 10 Mobile).
    -   **Proste hasła** — umożliwia korzystanie z prostych haseł, takich jak 1111 lub 1234. To ustawienie zezwala również na używanie haseł obrazkowych systemu Windows lub blokuje tę możliwość.
-   **Szyfrowanie** — włącz szyfrowanie na urządzeniach docelowych.

## <a name="personalization"></a>Personalizacja

- **Adres URL obrazu tła pulpitu (tylko dla komputerów stacjonarnych)** — pozwala określić adres URL obrazu w formacie PNG, JPG lub JPEG, który będzie używany jako tapeta pulpitu systemu Windows. Użytkownicy nie mogą zmieniać tego ustawienia.

## <a name="privacy"></a>Ochrona prywatności

-   **Personalizacja danych wejściowych** — nie zezwala na korzystanie z chmurowych usług przetwarzania mowy razem z aplikacją Cortana, funkcją dyktowania czy aplikacjami ze Sklepu Microsoft. Jeśli zezwolisz na te usługi, firma Microsoft może zbierać dane dotyczące głosu w celu usprawnienia świadczonej usługi.
-   **Automatyczne akceptowanie w przypadku monitów o wyrażenie zgody przez użytkownika dotyczących parowania i prywatności** — zezwala systemowi Windows na automatyczne akceptowanie komunikatów dotyczących parowania i prywatności wyświetlanych w uruchamianych aplikacjach.

Można zdefiniować informacje, do których mogą uzyskiwać dostęp wszystkie aplikacje na urządzeniu. Można także zdefiniować wyjątki dla poszczególnych aplikacji, korzystając z opcji **Wyjątki prywatności dla aplikacji**.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie** — określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle** — określ, czy ta aplikacja można działać w tle.
- **Kalendarz** — określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń** — określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny** — określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty** — określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail** — określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja** — określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości** — określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości tekstowe lub MMS.
- **Mikrofon** — określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch** — określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia** — określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon** — określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe** — niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania** — określ, czy ta aplikacja może uzyskiwać dostęp do zadań użytkownika.
- **Zaufane urządzenia** — określ, czy ta aplikacja może używać zaufanych urządzeń (sprzętu, z którym już nawiązano połączenie lub dołączonego do tego komputera, tabletu lub telefonu), na przykład telewizorów, projektorów, itp.
- **Opinie i diagnostyka** — określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami** — określ, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym komputerem, tabletem lub telefonem.

## <a name="per-app-privacy-exceptions"></a>Wyjątki prywatności dla aplikacji

Możesz dodawać aplikacje, dla których chcesz określić inne zachowanie dotyczące prywatności niż zachowanie zdefiniowane w domyślnym ustawieniu prywatności.

- **Nazwa pakietu** — nazwa rodziny pakietów aplikacji.
- **Nazwa aplikacji** — nazwa aplikacji.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie** — określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle** — określ, czy ta aplikacja można działać w tle.
- **Kalendarz** — określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń** — określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny** — określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty** — określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail** — określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja** — określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości** — określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości tekstowe lub MMS.
- **Mikrofon** — określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch** — określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia** — określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon** — określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe** — niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania** — określ, czy ta aplikacja może uzyskiwać dostęp do zadań użytkownika.
- **Zaufane urządzenia** — określ, czy ta aplikacja może używać zaufanych urządzeń (sprzętu, z którym już nawiązano połączenie lub dołączonego do tego komputera, tabletu lub telefonu), na przykład telewizorów, projektorów, itp.
- **Opinie i diagnostyka** — określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami** — określ, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym komputerem, tabletem lub telefonem.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

- **Powiadomienia centrum akcji (tylko dla urządzeń przenośnych)** — włącza powiadomienia z centrum akcji na ekranie blokady urządzenia (tylko system Windows 10 Mobile).
- **Adres URL obrazu ekranu blokady (tylko dla komputerów stacjonarnych)** — pozwala określić adres URL obrazu w formacie PNG, JPG lub JPEG, który będzie używany jako tapeta ekranu blokady systemu Windows. Użytkownicy nie mogą zmieniać tego ustawienia.
-   **Konfigurowany przez użytkownika limit czasu ekranu (tylko urządzenia przenośne)** — pozwala na ustawienie czasu przez użytkownika. 
-   **Cortana na zablokowanym ekranie (tylko komputery stacjonarne)** — nie zezwala użytkownikowi na interakcję z funkcją Cortana, gdy jest wyświetlany ekran blokady (tylko system Windows 10 Desktop).
-   **Wyskakujące powiadomienia na zablokowanym ekranie** — blokuje wyświetlanie alertów na ekranie blokady.
-   **Limit czasu ekranu (tylko urządzenia przenośne)** — określa czas (w sekundach) wyświetlania ekranu blokady, po którym ekran zostanie wyłączony.



## <a name="app-store"></a>App Store

-   **App Store (tylko dla urządzeń przenośnych)** — umożliwia lub blokuje korzystanie ze sklepu z aplikacjami na urządzeniach z systemem Windows 10 Mobile.
-   **Automatycznie aktualizuj aplikacje ze sklepu** — umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze Sklepu Microsoft.
-   **Instalacja aplikacji zaufanej** — umożliwia ładowanie bezpośrednie aplikacji podpisanych za pomocą zaufanego certyfikatu.
-   **Odblokowanie trybu deweloperskiego** — umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, np. z ustawienia umożliwiającego użytkownikowi końcowemu modyfikację aplikacji ładowanych bezpośrednio.
-   **Współużytkowane dane aplikacji użytkownika** — umożliwia aplikacjom udostępnianie danych różnym użytkownikom na tym samym urządzeniu.
-   **Używaj tylko sklepu prywatnego** — po włączeniu tego ustawienia użytkownicy końcowi będą mogli pobierać aplikacje wyłącznie z udostępnionego im sklepu prywatnego.
-   **Uruchamianie aplikacji pochodzącej ze sklepu** — ustawienie pozwala wyłączyć wszystkie aplikacje, które zostały wcześniej zainstalowane na urządzeniu lub pobrane ze Sklepu Microsoft.
-   **Instaluj dane aplikacji na woluminie systemowym** — uniemożliwia aplikacjom przechowywanie danych na woluminie systemowym urządzenia.
-   **Instaluj aplikacje na dysku systemowym** — uniemożliwia aplikacjom przechowywanie danych na dysku systemowym urządzenia.
-   **DVR z gry (tylko dla komputerów stacjonarnych)** — pozwala określić, czy nagrania i emisje z gier są dozwolone.
-   **Tylko aplikacje ze sklepu** — Określa, czy użytkownicy mogą instalować aplikacje z miejsc innych niż sklep z aplikacjami.



## <a name="edge-browser"></a>Przeglądarka Microsoft Edge

-   **Przeglądarka Microsoft Edge (tylko urządzenia przenośne)** — umożliwia korzystanie z przeglądarki Edge na urządzeniu.
-   **Rozwijanie paska adresu (tylko wersja klasyczna)** — uniemożliwia przeglądarce Edge wyświetlanie sugestii na liście rozwijanej podczas wpisywania tekstu. Pozwala to zmniejszyć wykorzystanie przepustowości sieci w ramach komunikacji między przeglądarką Edge a usługami firmy Microsoft.
-   **Synchronizuj ulubione między przeglądarkami firmy Microsoft (tylko wersja klasyczna)** — umożliwia synchronizowanie ulubionych między przeglądarkami Internet Explorer i Edge.
-   **Wysyłaj nagłówki Nie śledź** — umożliwia skonfigurowanie przeglądarki Edge do wysyłania nagłówków „Nie śledź” do witryn sieci Web odwiedzanych przez użytkowników.
-   **Pliki cookie** — umożliwia przeglądarce na urządzeniu zapisywanie plików cookie z Internetu.
-   **JavaScript** — umożliwia uruchamianie skryptów (takich jak JavaScript) w przeglądarce Edge.
-   **Wyskakujące okienka** — umożliwia blokowanie wyskakujących okienek w przeglądarce (tylko system Windows 10 Desktop).
-   **Sugestie wyszukiwania** — umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz.
-   **Wysyłaj ruch intranetowy do programu Internet Explorer** — umożliwia użytkownikom otwieranie intranetowych witryn sieci Web w programie Internet Explorer (tylko system Windows 10 Desktop).
-   **Autowypełnianie** — umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce (tylko system Windows 10 Desktop).
-   **Menedżer haseł** — włącza lub wyłącza funkcję menedżera haseł w przeglądarce Edge.
-   **Lokalizacja listy witryn trybu przedsiębiorstwa** — określa lokalizację listy witryn sieci Web, które można otwierać w trybie przedsiębiorstwa. Użytkownicy nie mogą edytować tej listy.<br>(Tylko system Windows 10 Desktop).
-   **Narzędzia programistyczne** — uniemożliwia użytkownikowi końcowemu otwieranie narzędzi programistycznych przeglądarki Edge.
-   **Rozszerzenia** — umożliwia użytkownikowi końcowemu instalowanie rozszerzeń przeglądarki Edge na urządzeniu.
-   **Przeglądanie InPrivate** — uniemożliwia otwieranie sesji przeglądania InPrivate przez użytkownika końcowego.
-   **Pokaż stronę pierwszego uruchomienia** — wyłącza wyświetlanie strony wprowadzenia przy pierwszym uruchomieniu przeglądarki Edge.
    -   **Adres URL pierwszego uruchomienia** — umożliwia podanie adresu URL strony wyświetlanej przy pierwszym uruchomieniu przeglądarki Edge (tylko system Windows 10 Mobile).
-   **Strony główne** — umożliwia dodanie listy witryn, które mają być używane jako strony główne w przeglądarce Edge (tylko wersja Desktop).
-   **Zmiany strony startowej** — umożliwia użytkownikom zmienianie stron startowych wyświetlanych po otwarciu przeglądarki Edge. Użyj ustawienia Strony główne, aby wskazać stronę (lub listę stron) otwieraną podczas uruchamiania przeglądarki Edge.
-   **Blokuj dostęp do flag informacji** — uniemożliwia użytkownikowi końcowemu uzyskanie dostępu do strony about:flags przeglądarki Edge zawierającej ustawienia programistyczne i eksperymentalne.
-   **Adres IP lokalnego hosta dla protokołu WebRTC** — blokuje wyświetlanie adresu IP lokalnego hosta użytkownika podczas nawiązywania połączeń telefonicznych przy użyciu protokołu WebRTC.
-   **Domyślna wyszukiwarka** — pozwala określić domyślną wyszukiwarkę. Użytkownicy końcowi mogą w dowolnym momencie zmienić tę wartość.
-   **Wyczyść dane przeglądania przy zamykaniu** — włącza czyszczenie historii i danych przeglądania przy zamykaniu przeglądarki Edge.
-   **Zbieranie danych dynamicznych kafelków** — wyłącza zbieranie informacji z dynamicznych kafelków podczas przypinania witryn przez użytkowników z przeglądarki Edge do menu Start.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **Filtr SmartScreen dla przeglądarki Microsoft Edge** — włącz filtr SmartScreen dla przeglądarki Edge używany podczas uzyskiwania dostępu do witryn i pobierania plików.
- **Dostęp do złośliwych witryn** — zablokuj użytkownikom możliwość ignorowania ostrzeżeń filtru Windows Defender SmartScreen oraz przechodzenia do witryny.
- **Pobieranie niezweryfikowanych plików** — zablokuj użytkownikom możliwość ignorowania ostrzeżeń filtru Windows Defender SmartScreen oraz pobierania niezweryfikowanych plików.

## <a name="search"></a>Wyszukaj
- **Bezpieczne wyszukiwanie (tylko urządzenia przenośne)** — pozwala określić sposób, w jaki Cortana filtruje treści dla dorosłych w wynikach wyszukiwania. Można wybrać opcję **Ścisłe** lub **Umiarkowane** albo zezwolić użytkownikom końcowym na wybór własnych ustawień.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-   **Konto Microsoft** — umożliwia użytkownikowi skojarzenie konta Microsoft z urządzeniem.
-   **Konto inne niż Microsoft** — umożliwia użytkownikowi dodanie na urządzeniu kont poczty e-mail, które nie są skojarzone z kontem Microsoft.
-   **Synchronizacja ustawień dla konta Microsoft** — zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między różnymi urządzeniami.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

-   **Kanał danych komórkowych** — uniemożliwia użytkownikom korzystanie z danych sieci komórkowej, na przykład przeglądanie Internetu. 
-   **Roaming danych** — umożliwia roaming między sieciami podczas uzyskiwania dostępu do danych.
-   **Sieć VPN przez sieć komórkową** — określa, czy urządzenie połączone z siecią komórkową może uzyskiwać dostęp do sieci VPN.
-   **Roaming sieci VPN przez sieć komórkową** — określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.
-   **Bluetooth** — określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
-   **Odnajdowanie Bluetooth** — umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
-   **Wstępne parowanie przy użyciu połączenia Bluetooth** — umożliwia skonfigurowanie automatycznego łączenia się określonych urządzeń Bluetooth z urządzeniem hosta.
-   **Rozgłaszanie Bluetooth** — umożliwia odbieranie reklam przez urządzenie za pośrednictwem połączenia Bluetooth.
-   **Usługa podłączonych urządzeń** — określa, czy zezwalać na używanie usługi podłączonych urządzeń, która umożliwia odnajdowanie i nawiązywanie połączenia z innymi urządzeniami Bluetooth.
-   **NFC** — umożliwia użytkownikowi włączanie i konfigurowanie funkcji komunikacji zbliżeniowej na urządzeniu.
-   **Wi-Fi** — umożliwia użytkownikowi włączanie i konfigurowanie sieci Wi-Fi na urządzeniu (tylko system Windows 10 Mobile).
-   **Automatycznie łącz się z hotspotami Wi-Fi** — umożliwia automatyczne łączenie się przy użyciu urządzenia z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.
-   **Ręczna konfiguracja sieci Wi-Fi** — określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi (tylko system Windows 10 Mobile).
-   **Interwał skanowania sieci Wi-Fi** — pozwala określić, jak często urządzenie ma wyszukiwać sieci Wi-Fi. Podaj wartość z zakresu od 1 (najczęściej) do 500 (najrzadziej).
-   **Dozwolone usługi Bluetooth** — lista dozwolonych usług i profilów Bluetooth określana w postaci ciągów szesnastkowych.


## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

-   **Aplikacja Ustawienia** — blokuje dostęp do aplikacji Ustawienia systemu Windows.
    -   **System** — blokuje dostęp do obszaru systemu w aplikacji Ustawienia.
        -   **Modyfikowanie ustawień zasilania i uśpienia (tylko dla komputerów stacjonarnych)** — uniemożliwia zmianę ustawień zasilania i uśpienia na urządzeniu przez użytkownika końcowego.
    -   **Urządzenia** — blokuje dostęp do obszaru urządzeń w aplikacji Ustawienia.
    -   **Sieć i Internet** — blokuje dostęp do obszaru sieci i Internetu w aplikacji Ustawienia.
    -   **Personalizacja** — blokuje dostęp do obszaru personalizacji w aplikacji Ustawienia.
    -   **Konta** — blokuje dostęp do obszaru kont w aplikacji Ustawienia.
    -   **Czas i język** — blokuje dostęp do obszaru czasu i języka w aplikacji Ustawienia.
        -   **Modyfikowanie czasu systemowego** — uniemożliwia użytkownikowi końcowemu zmianę daty i godziny na urządzeniu.
        -   **Modyfikowanie ustawień regionu (tylko komputer)** — uniemożliwia zmianę ustawień regionu na urządzeniu przez użytkownika końcowego.
        -   **Modyfikowanie ustawień języka (tylko komputer)** — uniemożliwia zmianę ustawień języka na urządzeniu przez użytkownika.
    -   **Gry** — blokuje dostęp do aplikacji Gry w obszarze Ustawienia.
    -   **Ułatwienia dostępu** — blokuje dostęp do obszaru ułatwień dostępu w aplikacji Ustawienia.
    -   **Prywatność** — blokuje dostęp do obszaru prywatności w aplikacji Ustawienia.
    -   **Aktualizacja i zabezpieczenia** — blokuje dostęp do obszaru aktualizacji i zabezpieczeń w aplikacji Ustawienia.

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

## <a name="display"></a>Wyświetlanie

- **Włącz skalowanie z użyciem interfejsu GDI dla aplikacji**
- **Wyłącz skalowanie z użyciem interfejsu GDI dla aplikacji**

  Skalowanie DPI z użyciem interfejsu GDI umożliwia rozpoznawanie wartości DPI monitora tym aplikacjom, które jej nie rozpoznają. Określ starsze aplikacje, które mają włączone skalowanie DPI z użyciem interfejsu GDI. Jeśli w aplikacji skonfigurowano zarówno włączanie, jak i wyłączanie skalowania DPI z użyciem interfejsu GDI, skalowanie dla aplikacji jest wyłączone.

## <a name="kiosk-preview"></a>Kiosk (wersja zapoznawcza)

-   **Tryb kiosku** — wskazuje typ [tryb kiosku](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shared-pc) obsługiwany przez zasady. Dostępne opcje:

      - **Nieskonfigurowane** (domyślne) — zasady nie umożliwiają trybu kiosku. 
      - **Kiosk z pojedynczą aplikacją** — profil włącza urządzenie jako kiosk z pojedynczą aplikacją.
      - **Kiosk z wieloma aplikacjami** — profil włącza urządzenie jako kiosk z wieloma aplikacjami.

    Kioski z pojedynczą aplikacją wymagają następujących ustawień:

      - **Konto użytkownika** — określa lokalne (na urządzeniu) konto użytkownika lub dane logowanie konta usługi Azure AD skojarzonego z aplikacją kiosku. W przypadku kont przyłączonych do domeny usługi Azure AD należy określić konto w postaci `domain\\username@tenant.org`.

         Dla urządzeń w środowiskach publicznych należy użyć kont z minimalnymi uprawnieniami, aby uniemożliwić autoryzowane działanie.  

      - **Identyfikator modelu użytkownika aplikacji (AUMID) aplikacji** — określa identyfikator modelu użytkownika aplikacji (AUMID) aplikacji kiosku. Aby dowiedzieć się więcej, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

    Kioski z wieloma aplikacjami wymagają konfiguracji kiosku. Użyj przycisku **Dodaj**, aby utworzyć konfigurację kiosku, lub wybierz istniejącą konfigurację.

    Konfiguracje kiosku z wieloma aplikacjami obejmują następujące ustawienia:

    - **Nazwa konfiguracji kiosku** — przyjazna nazwa używana do identyfikowania danej konfiguracji.

    - Co najmniej jedna **aplikacja kiosku** składająca się z następujących elementów:

        - **Typ aplikacji** — określa typ aplikacji kiosku.  Obsługiwane wartości:   

            - **Aplikacja Win32** — tradycyjna aplikacja klasyczna. (Potrzebna jest ścieżka bezwzględna pliku wykonywalnego w odniesieniu do urządzenia).

            - **Aplikacja platformy UWP** — aplikacja uniwersalna systemu Windows. Potrzebny jest [identyfikator AUMID aplikacji](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

        - **Identyfikator aplikacji** — określa pełną nazwę ścieżki pliku wykonywalnego (aplikacji Win32) lub [identyfikatora AUMID aplikacji](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplikacji platformy UWP).

    - **Pasek zadań** — wskazuje, czy pasek zadań jest wyświetlany (**Włączone**), czy ukryty (**Nieskonfigurowane**) na kiosku.

    - **Układ menu Start** — określa plik XML, który opisuje sposób, w jaki aplikacje [są wyświetlane w menu Start](https://docs.microsoft.com/en-us/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).

    - **Przypisani użytkownicy** — określa co najmniej jedno konto użytkownika skojarzone z konfiguracją kiosku. Konto może być kontem lokalnym na urządzeniu lub danymi logowania konta usługi Azure AD skojarzonego z aplikacją kiosku. Konta przyłączonych do domeny należy określić w postaci `domain\\username@tenant.org`.

## <a name="windows-defender-antivirus"></a>Program antywirusowy Windows Defender

-   **Monitorowanie w czasie rzeczywistym** — włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.
-   **Monitorowanie zachowania** — umożliwia usłudze Defender sprawdzanie urządzeń pod kątem określonych wzorców podejrzanej aktywności.
-   **Network Inspection System (NIS)** — pomaga w ochronie urządzeń przed sieciowymi atakami wykorzystującymi luki w zabezpieczeniach. System NIS korzysta z sygnatur znanych luk w zabezpieczeniach z centrum programu Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch.
-   **Skanuj wszystkie pobrane pliki** — określa, czy usługa Defender ma skanować wszystkie pliki pobierane z Internetu.
-   **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft** — umożliwia usłudze Defender skanowanie skryptów używanych przez przeglądarkę Internet Explorer.
-   **Dostęp użytkownika końcowego do narzędzia Defender** —określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych.
Zmiany tego ustawienia zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika.
-   **Interwał aktualizacji sygnatur (w godzinach)** — określa interwał sprawdzania dostępności nowych plików sygnatur przez usługę Defender.
-   **Monitoruj działanie plików i programów** — zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach.
-   **Dni przed usunięciem złośliwego oprogramowania poddanego kwarantannie** — umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane.
-   **Limit wykorzystania procesora CPU podczas skanowania** —pozwala ograniczyć użycie procesora CPU dozwolone dla procesów skanowania (w skali od **1** do **100**).
-   **Skanuj pliki archiwów** — zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.
-   **Skanuj przychodzące wiadomości e-mail** — zezwala usłudze Defender na skanowanie wiadomości e-mail dostarczanych do urządzenia.
-   **Skanuj dyski wymienne podczas pełnego skanowania** —umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.
-   **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania** — umożliwia usłudze Defender skanowanie plików na zamapowanych dyskach sieciowych.<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
-   **Skanuj pliki otwierane z folderów sieciowych** — umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach dostępnych za pośrednictwem ścieżki UNC).
Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
-   **Ochrona w chmurze** — zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.
-   **Monituj użytkowników przed przesłaniem próbki** — określa, czy do firmy Microsoft są automatycznie wysyłane potencjalnie złośliwe pliki, które mogą wymagać dalszej analizy.
-   **Godzina przeprowadzania codziennego szybkiego skanowania** — umożliwia zaplanowanie szybkiego skanowania wykonywanego codziennie o wybranej godzinie.
-   **Typ skanowania systemu do wykonania** — pozwala określić poziom planowanego skanowania systemu.
-   **Wykrywaj potencjalnie niepożądane aplikacje** — pozwala wybrać poziom ochrony w przypadku wykrycia potencjalnie niechcianych aplikacji przez system Windows:
        - **Zablokuj**
        - **Inspekcja** Więcej informacji dotyczących potencjalnie niechcianych aplikacji można znaleźć w [tym temacie](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
-   **Akcje do podjęcia wobec wykrytych zagrożeń związanych ze złośliwym oprogramowaniem** — włączenie tej opcji umożliwia wskazanie akcji, które ma podejmować usługa Defender po wykryciu zagrożenia określonego poziomu (niski, umiarkowany, wysoki i poważny). Dostępne są następujące akcje:
    -   **Wyczyść**
    -   **Kwarantanna**
    -   **Usuń**
    -   **Zezwalaj**
    -   **Zdefiniowane przez użytkownika**
    -   **Zablokuj**



### <a name="windows-defender-antivirus-exclusions"></a>Wyjątki programu antywirusowego Windows Defender

-   **Pliki i foldery do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych plików lub folderów lub większej ich liczby, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.
-   **Rozszerzenia plików do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych rozszerzeń plików lub większej ich liczby, np. **JPG** lub **TXT**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym lub skanowania planowanego.
-   **Procesy do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych procesów typu **EXE**, **COM** lub **SCR** lub większej ich liczby. Te procesy nie są uwzględniane podczas skanowania w czasie rzeczywistym ani podczas zaplanowanego skanowania.


## <a name="network-proxy"></a>Serwer proxy sieci

-   **Automatycznie wykrywaj ustawienia proxy** — po włączeniu tego ustawienia urządzenie spróbuje znaleźć ścieżkę do skryptu PAC.
-   **Użyj skryptu serwera proxy** — zaznacz tę opcję, jeśli chcesz określić ścieżkę do skryptu PAC, aby skonfigurować serwer proxy.
    -   **Adres URL skryptu konfiguracji** — wprowadź adres URL skryptu PAC, którego chcesz użyć do skonfigurowania serwera proxy.
-   **Użyj ręcznego serwera proxy** — wybierz tę opcję, jeśli chcesz ręcznie wprowadzać informacje o serwerze proxy.
    -   **Adres** — wprowadź nazwę lub adres IP serwera proxy.
    -   **Numer portu** — wprowadź numer portu serwera proxy.
    -   **Wyjątki serwera proxy** — wprowadź wszystkie adresy URL, w przypadku których korzystanie z serwera proxy będzie zabronione. Rozdziel kolejne elementy średnikiem.
    -   **Pomiń serwer proxy dla adresów lokalnych** — włącz tę opcję, jeśli nie chcesz używać serwera proxy dla adresów lokalnych w sieci intranet.


## <a name="windows-spotlight"></a>W centrum uwagi Windows


- **W centrum uwagi Windows** — to ustawienie umożliwia zablokowanie wszystkich funkcji W centrum uwagi Windows na urządzeniach z systemem Windows 10. Jeśli to ustawienie zostanie wyłączone, następujące ustawienia nie będą dostępne.
    - **Funkcja W centrum uwagi Windows na ekranie blokady** — wyłącza wyświetlanie informacji funkcji W centrum uwagi Windows na ekranie blokady urządzenia.
    - **Sugestie innych firm w funkcji W centrum uwagi Windows** — wyłącza sugerowanie zawartości niepochodzącej z firmy Microsoft przez funkcję W centrum uwagi Windows.
    - **Funkcje dla konsumentów** — umożliwia blokowanie funkcji dla konsumentów, takich jak sugestie w menu Start, powiadomienia dotyczące członkostwa itp.
    - **Porady dotyczące systemu Windows** — umożliwia zablokowanie wyskakujących okienek z poradami w systemie Windows.
    - **Funkcja W centrum uwagi Windows w Centrum akcji** — uniemożliwia wyświetlanie sugestii funkcji W centrum uwagi Windows, na przykład zawartości dotyczących nowych aplikacji lub zabezpieczeń, w Centrum akcji systemu Windows.
    - **Personalizacja funkcji W centrum uwagi Windows** — wyłącza personalizowanie opartych na użyciu urządzenia wyników przez funkcję W centrum uwagi Windows.
    - **Środowisko powitalne systemu Windows** — wyłącza wyświetlanie środowiska powitalnego systemu Windows, w którym są widoczne informacje o nowych lub zaktualizowanych funkcjach.


## <a name="projection"></a>Projekcja

- **Dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych** — blokuje dane wejściowe użytkownika z odbiorników wyświetlaczy bezprzewodowych.
- **Projekcja na tym komputerze** — uniemożliwia innym urządzeniom odnajdywanie tego komputera dla celów projekcji.
- **Wymagaj numeru PIN do parowania** — wybór powoduje, że podczas nawiązywania połączenia z urządzeniem do projekcji wymagane jest podanie numeru PIN.

## <a name="cloud-printer"></a>Drukarka w chmurze

- **Adres URL na potrzeby wykrywania drukarek** — punkt końcowy służący do wykrywania drukarek w chmurze.
- **Adres URL urzędu dostępu do drukarek** — punkt końcowy uwierzytelniania na potrzeby pobierania tokenów OAuth.
- **Identyfikator GUID aplikacji klienta natywnego platformy Azure** — identyfikator GUID aplikacji klienckiej uprawnionej do pobierania tokenów OAuth z urzędu OAuthAuthority.
- **Identyfikator URI zasobu usługi drukowania** — identyfikator URI zasobu OAuth dla usługi drukowania skonfigurowanej w witrynie Azure Portal.
- **Maksymalna liczba drukarek do uwzględnienia w zapytaniu (tylko wersja mobilna)** — maksymalna liczba drukarek, która powinna zostać uwzględniona w zapytaniu z punktu końcowego wykrywania.
- **Identyfikator URI zasobu usługi wykrywania drukarek** — identyfikator URI zasobu OAuth dla usługi wykrywania drukarek skonfigurowany w witrynie Azure Portal.

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia** — wybierz poziom przesyłania danych diagnostycznych.
- **Serwer proxy telemetrii**

  Określ w pełni kwalifikowaną nazwę domeny (FQDN) lub adres IP serwera proxy do przekazywania żądań środowisk i telemetrii połączonego użytkownika przy użyciu połączenia SSL (Secure Sockets Layer). Format dla tego ustawienia to: *serwer*:*port*. Jeśli nazwany serwer proxy ulegnie awarii lub jeśli serwer proxy nie będzie określony w momencie włączenia tych zasad, dane środowisk i telemetrii połączonego użytkownika nie zostaną przesłane i pozostaną na urządzeniu lokalnym.

   Przykładowe formaty:

   IPv4: 192.246.246.106:100<br>
 IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100<br> FQDN: www.contoso.com:345

## <a name="messaging"></a>Obsługa wiadomości

- **Synchronizowanie wiadomości (tylko na urządzeniach przenośnych)** — wyłącz funkcję Wiadomości na wszystkich urządzeniach oraz tworzenie kopii zapasowych wiadomości SMS i ich przywracanie.
- **MMS (tylko na urządzeniach przenośnych)** — wyłącz funkcję wysyłania i odbierania wiadomości MMS na urządzeniu.
- **RCS (tylko na urządzeniach przenośnych)** — wyłącz funkcję wysyłania i odbierania wiadomości Rich Communication Services na urządzeniu.












