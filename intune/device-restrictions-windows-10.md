---
title: Ustawienia ograniczeń urządzeń dla systemu Windows 10 w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień dotyczących tworzenia ograniczeń dotyczących urządzeń z systemie Windows 10 lub nowszym oraz z ich opisami. Te ustawienia w profilu konfiguracji służą do kontrolowania zrzutów ekranu, wymagań dotyczących haseł, ustawień kiosku, aplikacji w sklepie, przeglądarki Microsoft Edge, usługi Windows Defender, dostępu do chmury, menu Start i innych elementów w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ca34826f3a235fe620b5ac0dcb95d57dabf4c71
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58395004"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem Windows 10 (i nowszym) w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune

W tym artykule wymieniono i opisano wszystkie różne ustawienia, którymi można sterować na urządzeniach z systemem Windows 10 i nowszym. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, dostosowywać ekran blokady, korzystać z programu Windows Defender i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem Windows 10.

> [!Note]
> Nie wszystkie opcje są dostępne we wszystkich wersjach systemu Windows. Aby wyświetlić obsługiwanych wersji, zapoznaj się [zasad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (otwiera innej witryny sieci web firmy Microsoft).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>App Store

- **App Store (tylko dla urządzeń przenośnych)**: umożliwia lub blokuje korzystanie ze sklepu z aplikacjami na urządzeniach z systemem Windows 10 Mobile.
- **Automatycznie aktualizuj aplikacje ze sklepu**: umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze Sklepu Microsoft.
- **Instalacja aplikacji zaufanej**: umożliwia ładowanie bezpośrednie aplikacji podpisanych za pomocą zaufanego certyfikatu.
- **Odblokowanie trybu deweloperskiego**: umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, np. z ustawienia umożliwiającego użytkownikowi końcowemu modyfikację aplikacji ładowanych bezpośrednio.
- **Współużytkowane dane aplikacji użytkownika**: umożliwia aplikacjom udostępnianie danych różnym użytkownikom na tym samym urządzeniu.
- **Używaj tylko sklepu prywatnego**: po włączeniu tego ustawienia użytkownicy końcowi będą mogli pobierać aplikacje wyłącznie z udostępnionego im sklepu prywatnego.
- **Uruchamianie aplikacji pochodzącej ze sklepu**: ustawienie pozwala wyłączyć wszystkie aplikacje, które zostały wcześniej zainstalowane na urządzeniu lub pobrane ze Sklepu Microsoft.
- **Instaluj dane aplikacji na woluminie systemowym**: uniemożliwia aplikacjom przechowywanie danych na woluminie systemowym urządzenia.
- **Instaluj aplikacje na dysku systemowym**: uniemożliwia aplikacjom przechowywanie danych na dysku systemowym urządzenia.
- **DVR z gry (tylko dla komputerów stacjonarnych)**: pozwala określić, czy nagrania i emisje z gier są dozwolone.
- **Tylko aplikacje ze sklepu**: określa, czy użytkownicy mogą instalować aplikacje z miejsc innych niż sklep z aplikacjami.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Kanał danych komórkowych**: uniemożliwia użytkownikom korzystanie z danych sieci komórkowej, na przykład przeglądanie Internetu. 
- **Roaming danych**: umożliwia roaming między sieciami podczas uzyskiwania dostępu do danych.
- **Sieć VPN przez sieć komórkową**: określa, czy urządzenie połączone z siecią komórkową może uzyskiwać dostęp do sieci VPN.
- **Roaming sieci VPN przez sieć komórkową**: określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.
- **Bluetooth**: określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
- **Odnajdowanie Bluetooth**: umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
- **Wstępne parowanie przy użyciu połączenia Bluetooth**: umożliwia skonfigurowanie automatycznego łączenia się określonych urządzeń Bluetooth z urządzeniem hosta.
- **Rozgłaszanie Bluetooth**: umożliwia odbieranie reklam przez urządzenie za pośrednictwem połączenia Bluetooth.
- **Usługa podłączonych urządzeń**: umożliwia wybranie, czy zezwalać na używanie usługi podłączonych urządzeń, która umożliwia odnajdowanie i nawiązywanie połączenia z innymi urządzeniami Bluetooth.
- **NFC**: umożliwia użytkownikowi włączanie i konfigurowanie funkcji komunikacji zbliżeniowej (NFC, Near Field Communications) na urządzeniu.
- **Wi-Fi**: umożliwia użytkownikowi włączanie i konfigurowanie sieci Wi-Fi na urządzeniu (tylko system Windows 10 Mobile).
- **Automatycznie łącz się z hotspotami Wi-Fi**: umożliwia automatyczne łączenie się przy użyciu urządzenia z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.
- **Ręczna konfiguracja sieci Wi-Fi**: określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi (tylko system Windows 10 Mobile).
- **Interwał skanowania sieci Wi-Fi**: wprowadź wartość określającą, jak często urządzenie ma wyszukiwać sieci Wi-Fi. Wprowadź wartość z zakresu od 1 (najczęściej) do 500 (najrzadziej).
- **Dozwolone usługi Bluetooth**: wprowadź listę dozwolonych usług i profilów Bluetooth w postaci ciągów szesnastkowych.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Konto Microsoft**: umożliwia użytkownikowi skojarzenie konta Microsoft z urządzeniem.
- **Konto inne niż Microsoft**: umożliwia użytkownikowi dodanie na urządzeniu kont poczty e-mail, które nie są skojarzone z kontem Microsoft.
- **Synchronizacja ustawień dla konta Microsoft**: zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między różnymi urządzeniami.
- **Asystent logowania za pomocą konta Microsoft**: wybierz opcję **Wyłącz**, aby uniemożliwić użytkownikom końcowym sterowanie usługą asystenta logowania firmy Microsoft (wlidsvc), na przykład ręczne zatrzymywanie lub uruchamianie usługi. Gdy ustawiona zostanie pozycja **Nie skonfigurowano**, usługa NT wlidsvc użyje domyślnego ustawienia systemu operacyjnego, które może pozwalać użytkownikom końcowym na uruchamianie i zatrzymywanie usługi. Ta usługa jest używana przez system operacyjny do umożliwiania użytkownikom logowania się na konta Microsoft.

## <a name="cloud-printer"></a>Drukarka w chmurze

- **Adres URL na potrzeby wykrywania drukarek**: wprowadź adres URL służący do wyszukiwania drukarek w chmurze.
- **Adres URL urzędu dostępu do drukarek**: wprowadź adres URL punktu końcowego uwierzytelniania na potrzeby pobierania tokenów OAuth. Na przykład wpisz coś takiego: `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **Identyfikator GUID aplikacji klienta natywnego platformy Azure**: wprowadź identyfikator GUID aplikacji klienckiej upoważnionej do pobierania tokenów OAuth z urzędu OAuthAuthority.
- **Identyfikator URI zasobu usługi drukowania**: wprowadź identyfikator URI zasobu OAuth dla usługi drukowania skonfigurowanej w witrynie Azure Portal. Na przykład wpisz coś takiego: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maksymalna liczba drukarek do uwzględnienia w zapytaniu (tylko wersja mobilna)**: wprowadź maksymalną liczbę drukarek, która powinna zostać uwzględniona w zapytaniu. Na przykład wprowadź `10`.
- **Identyfikator URI zasobu usługi wykrywania drukarek**: wprowadź identyfikator URI zasobu OAuth dla usługi wykrywania drukarek skonfigurowany w witrynie Azure Portal. Na przykład wpisz coś takiego: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Po skonfigurowaniu [hybrydowego drukowania w chmurze systemu Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview) można skonfigurować te ustawienia, a następnie wdrożyć je na urządzeniach z systemem Windows.

## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

- **Aplikacja Ustawienia**: blokuje dostęp do aplikacji Ustawienia systemu Windows.
  - **System**: blokuje dostęp do obszaru systemu w aplikacji Ustawienia.
    - **Modyfikowanie ustawień zasilania i uśpienia (tylko dla komputerów stacjonarnych)**: uniemożliwia zmianę ustawień zasilania i uśpienia na urządzeniu przez użytkownika końcowego.
  - **Urządzenia**: blokuje dostęp do obszaru urządzeń w aplikacji Ustawienia.
  - **Sieć i Internet**: blokuje dostęp do obszaru sieci i Internetu w aplikacji Ustawienia.
  - **Personalizacja**: blokuje dostęp do obszaru personalizacji w aplikacji Ustawienia.
  - **Konta**: blokuje dostęp do obszaru kont w aplikacji Ustawienia.
  - **Czas i język**: blokuje dostęp do obszaru czasu i języka w aplikacji Ustawienia.
    - **Modyfikowanie czasu systemowego**: uniemożliwia użytkownikowi końcowemu zmianę daty i godziny na urządzeniu.
    - **Modyfikowanie ustawień regionu (tylko komputer)**: uniemożliwia zmianę ustawień regionu na urządzeniu przez użytkownika końcowego.
    - **Modyfikowanie ustawień języka (tylko komputer)**: uniemożliwia zmianę ustawień języka na urządzeniu przez użytkownika.
  - **Gry**: blokuje dostęp do aplikacji Gry w obszarze Ustawienia.
  - **Ułatwienia dostępu**: blokuje dostęp do obszaru ułatwień dostępu w aplikacji Ustawienia.
  - **Prywatność**: blokuje dostęp do obszaru prywatności w aplikacji Ustawienia.
  - **Aktualizacja i zabezpieczenia**: blokuje dostęp do obszaru aktualizacji i zabezpieczeń w aplikacji Ustawienia.

## <a name="display"></a>Wyświetlanie

- **Włącz skalowanie z użyciem interfejsu GDI dla aplikacji**
- **Wyłącz skalowanie z użyciem interfejsu GDI dla aplikacji**

  Skalowanie DPI z użyciem interfejsu GDI umożliwia rozpoznawanie wartości DPI monitora tym aplikacjom, które jej nie rozpoznają. Wprowadź starsze aplikacje, które mają włączone skalowanie DPI z użyciem interfejsu GDI. Jeśli w aplikacji skonfigurowano włączanie i wyłączanie skalowania DPI z użyciem interfejsu GDI, skalowanie dla aplikacji jest wyłączone.

## <a name="general"></a>Ogólne

- **Przechwytywanie ekranu (tylko dla urządzeń przenośnych)**: umożliwia użytkownikowi przechwytywanie ekranu urządzenia w formie obrazu.
- **Kopiuj i wklej (tylko urządzenia przenośne)**: umożliwia kopiowanie i wklejanie między aplikacjami na urządzeniu.
- **Ręczne wyrejestrowanie**: umożliwia użytkownikowi ręczne usunięcie konta firmowego z urządzenia.
  - To ustawienie zasad nie jest stosowane, jeśli komputer jest przyłączony do usługi Azure AD i włączono automatyczne rejestrowanie. 
  - To ustawienie zasad nie ma zastosowania do komputerów z systemem Windows 10 Home.
- **Ręczne instalowanie certyfikatu głównego (tylko dla urządzeń przenośnych)**: uniemożliwia użytkownikowi ręczne instalowanie certyfikatów głównych i certyfikatów pośrednich urzędów certyfikacji.

- **Aparat fotograficzny**: umożliwia lub blokuje użycie aparatu fotograficznego urządzenia.
- **Synchronizacja plików w usłudze OneDrive**: uniemożliwia synchronizowanie plików z urządzenia z usługą OneDrive.
- **Magazyn wymienny**: określa, czy na urządzeniu można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD.
- **Geolokalizacja**: określa, czy urządzenie może używać informacji z usług lokalizacyjnych.
- **Udostępnianie Internetu**: umożliwia udostępnianie połączenia internetowego przy użyciu urządzenia.
- **Resetowanie telefonu**: określa, czy użytkownik może przeprowadzić czyszczenie swojego urządzenia.
- **Połączenie USB (tylko dla urządzeń przenośnych)**: określa, czy urządzenia mogą uzyskiwać dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.
- **Tryb ochrony przed kradzieżą (tylko na urządzeniach przenośnych)**: pozwala określić, czy jest włączony tryb przeciwkradzieżowy systemu Windows.
- **Cortana**: włącza lub wyłącza asystenta głosowego Cortana.
- **Nagrywanie głosu (tylko dla urządzeń przenośnych)**: umożliwia lub blokuje użycie rejestratora głosu w urządzeniu.
- **Modyfikacja nazwy urządzenia**: uniemożliwia użytkownikowi końcowemu zmianę nazwy urządzenia (tylko system Windows 10 Mobile)
- **Dodaj pakiety aprowizacji**: blokuje agenta konfiguracji środowiska uruchomieniowego, który instaluje pakiety aprowizacji.
- **Usuń pakiety aprowizacji**: blokuje agenta konfiguracji środowiska uruchomieniowego, który usuwa pakiety aprowizacji.
- **Odnajdywanie urządzeń**: blokuje wykrywanie urządzenia przez inne urządzenia.
- **Przełącznik zadań (tylko urządzenia przenośne)**: blokuje przełącznik zadań na urządzeniu.
- **Okno dialogowe błędu karty SIM (tylko urządzenia przenośne)**: w przypadku, gdy karta SIM nie zostanie wykryta, blokuje wyświetlanie komunikatu o błędzie na urządzeniu.
- **Obszar roboczy pisma odręcznego**: blokuje dostęp użytkowników do obszaru roboczego pisma odręcznego. Pozycja **Nieskonfigurowane** włącza obszar roboczy pisma odręcznego, a użytkownik może używać go na ekranie blokady urządzenia.
- **Automatyczne ponowne wdrażanie**: pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania.
- **Wymagaj od użytkowników nawiązania połączenia z siecią podczas konfigurowania urządzenia (tylko niejawny program testów systemu Windows)**: wybierz pozycję **Wymagane**, aby urządzenia łączyły się z siecią przed wyjściem poza stronę Sieć podczas instalacji systemu Windows 10. Chociaż ta funkcja jest obecnie w wersji zapoznawczej, niejawny program testów systemu Windows (kompilacja 1809 lub nowsza) jest wymagany, aby użyć tego ustawienia.
- **Bezpośredni dostęp do pamięci**: opcja **Blokuj** uniemożliwia bezpośredni dostęp do pamięci dla wszystkich podrzędnych portów PCI z możliwością podłączenia podczas pracy, dopóki użytkownik nie zaloguje się do systemu Windows. Pozycja **Włączone** (wartość domyślna) zezwala na bezpośredni dostęp do pamięci nawet wtedy, gdy użytkownik nie jest zalogowany.

  Dostawca usług kryptograficznych: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Kończyć procesy w Menedżerze zadań**: to ustawienie określa, czy użytkowników niebędących administratorami Menedżera zadań można użyć do zakończenia zadań. Pozycja **Blokuj** uniemożliwia użytkownikom standardowym (niebędącym administratorami) używanie Menedżera zadań do zakończenia procesu lub zadania na urządzeniu. **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom standardowym zakończenie procesu lub zadania za pomocą Menedżera zadań.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

- **Powiadomienia centrum akcji (tylko dla urządzeń przenośnych)**: włącza powiadomienia z centrum akcji na ekranie blokady urządzenia (tylko system Windows 10 Mobile).
- **Adres URL obrazu ekranu blokady (tylko dla komputerów stacjonarnych)**: wprowadź adres URL obrazu w formacie JPEG używany jako tapeta ekranu blokady systemu Windows. To ustawienie blokuje obraz. Obrazu nie można później zmienić.
- **Konfigurowany przez użytkownika limit czasu ekranu (tylko urządzenia przenośne)**: pozwala na ustawianie czasu przez użytkownika. 
- **Cortana na zablokowanym ekranie (tylko komputery stacjonarne)**: nie zezwala użytkownikowi na interakcję z funkcją Cortana, gdy jest wyświetlany ekran blokady (tylko system Windows 10 Desktop).
- **Wyskakujące powiadomienia na zablokowanym ekranie**: blokuje wyświetlanie alertów na ekranie blokady.
- **Limit czasu ekranu (tylko urządzenia przenośne)**: określa czas (w sekundach) wyświetlania ekranu blokady, po którym ekran zostanie wyłączony.

## <a name="messaging"></a>Obsługa wiadomości

- **Synchronizowanie wiadomości (tylko na urządzeniach przenośnych)**: wyłącz funkcję Wiadomości na wszystkich urządzeniach oraz tworzenie kopii zapasowych wiadomości SMS i ich przywracanie.
- **MMS (tylko na urządzeniach przenośnych)**: wyłącz funkcję wysyłania i odbierania wiadomości MMS na urządzeniu.
- **RCS (tylko na urządzeniach przenośnych)**: wyłącz funkcję wysyłania i odbierania wiadomości Rich Communication Services na urządzeniu.

## <a name="microsoft-edge-browser"></a>Przeglądarka Microsoft Edge

### <a name="use-microsoft-edge-kiosk-mode"></a>Użyj trybu kiosku Microsoft Edge

Zmienić dostępne ustawienia w zależności od dokonanego wyboru. Dostępne opcje:

- **Nie** (ustawienie domyślne): Microsoft Edge nie jest uruchomiony w trybie kiosku. Wszystkie ustawienia Microsoft Edge są dostępne dla Ciebie zmiany i skonfigurować.
- **Znakowania cyfrowego/Interactive (kiosk z pojedynczą aplikacją)**: ustawienia przeglądarki Microsoft Edge filtry, które są odpowiednie dla trybu kiosku krawędź firmy Microsoft znakowania cyfrowego/Interactive tylko na kioski pojedynczej aplikacji systemu Windows 10. Wybierz to ustawienie, aby otworzyć ekran pełny adres URL, a tylko Wyświetla zawartość w tej witrynie sieci Web. [Konfigurowanie cyfrowego podpisuje](https://docs.microsoft.com/windows/configuration/setup-digital-signage) zawiera więcej informacji na temat tej funkcji.
- **Publiczne przeglądania inPrivate (kiosk z pojedynczą aplikacją)**: ustawienia przeglądarki Microsoft Edge filtry, które są odpowiednie dla trybu InPrivate przeglądania Microsoft Edge kiosku publicznego do użycia na kioski pojedynczej aplikacji systemu Windows 10. Z wersją wieloma kartami Microsoft Edge.
- **Tryb normalny (kiosk z wieloma aplikacjami)**: ustawienia przeglądarki Microsoft Edge filtry, które są odpowiednie dla trybu kiosku krawędź firmy Microsoft normalny. Uruchamia pełnej wersji programu Microsoft Edge z wszystkich funkcji przeglądania.
- **Publiczne przeglądania (kiosk z wieloma aplikacjami)**: ustawienia przeglądarki Microsoft Edge filtry, które są odpowiednie dla publicznej przeglądania na kiosk z wieloma aplikacjami systemu Windows 10.  Z wersją wieloma kartami InPrivate przeglądarki Microsoft Edge.

> [!TIP]
> Aby uzyskać więcej informacji na temat działania tych opcji, zobacz [typów konfiguracji trybu kiosku Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Ten profil ograniczeń urządzenia są bezpośrednio związane z profilu kiosku możesz utworzyć przy użyciu [ustawienia kiosku Windows](kiosk-settings-windows.md). Podsumowując:

1. Tworzenie [ustawienia kiosku Windows](kiosk-settings-windows.md) profilu do uruchomienia urządzenia w trybie kiosku. Wybierz Microsoft Edge jako aplikacja i ustaw tryb kiosku programu Microsoft Edge w profilu kiosku.
2. Tworzenie profilu ograniczeń urządzenia, które są opisane w tym artykule i skonfiguruj określonych funkcji i ustawień w programie Microsoft Edge. Pamiętaj wybrać ten sam typ trybu kiosku Microsoft Edge wybierany w Twoim profilu kiosku ([ustawienia kiosku Windows](kiosk-settings-windows.md)). 

    [Obsługiwane ustawienia trybu kiosku](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) jest doskonałym zasobem.

> [!IMPORTANT] 
> Pamiętaj przypisać ten profil Microsoft Edge do tych samych urządzeń jako profilu kiosku ([ustawienia kiosku Windows](kiosk-settings-windows.md)).

[ConfigureKioskMode dostawcy usług Kryptograficznych](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Środowisko rozpoczynania pracy

- **Uruchom przeglądarkę Microsoft Edge przy użyciu**: wybierz strony otwierane po uruchomieniu przeglądarki Microsoft Edge. Dostępne opcje:
  - **Strony startowe**: przeglądarka Microsoft Edge jest uruchamiana z domyślną stroną startową zdefiniowaną przez system operacyjny
  - **Strona nowej karty**: przeglądarka Microsoft Edge ładuje adres zdefiniowany w obszarze **Adres URL nowej karty**
  - **Strona ostatniej sesji**: przeglądarka Microsoft Edge ładuje stronę ostatniej sesji 
  - **Niestandardowa strona startowa**: przeglądarka Microsoft Edge ładuje stronę startową zdefiniowaną przez administratora IT
- **Użytkownik może zmieniać strony startowe**: pozycja **Zezwalaj** umożliwia użytkownikom zmienianie stron startowych. Administratorzy mogą używać elementu `EdgeHomepageUrls` do wprowadzania stron startowych, które są widoczne domyślnie dla użytkowników po otwarciu przeglądarki Microsoft Edge. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom zmienianie stron startowych.
- **Adres URL nowej karty**: wprowadź adres URL do otwarcia na stronie nowej karty. Na przykład wprowadź `https://www.bing.com`.
- **Otwieranie zawartości internetowej na stronie nowej karty**: wybierz pozycję **Blokuj**, aby uniemożliwić przeglądarce Microsoft Edge otwieranie witryny internetowej na nowej karcie. Po zablokowaniu nowa karta jest otwierana jako pusta. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego na urządzeniu, dzięki czemu użytkownicy mogą wybierać zawartość do wyświetlenia.
- **Przycisk Strona główna**: wybierz, co się stanie po wybraniu przycisku Strona główna. Dostępne opcje:
  - **Strony startowe**: jest otwierana strona wybrana w ustawieniu **Uruchom przeglądarkę Microsoft Edge przy użyciu**
  - **Strona nowej karty**: jest otwierana opcja wybrana dla ustawienia **Adres URL nowej karty**
  - **Niestandardowy adres URL przycisku Strona główna**: jest otwierana opcja wybrana dla ustawienia **Adres URL przycisku Strona główna**
  - **Ukryj przycisk Strona główna**: ukrywa przycisk Strona główna
- **Użytkownik może zmieniać przycisk Strona główna**: pozycja **Zezwalaj** umożliwia użytkownikom zmienianie przycisku strony głównej. Zmiany wprowadzone przez użytkownika zastępują wszelkie ustawienia administratora, które dotyczą przycisku strony głównej. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego na urządzeniu, które może uniemożliwiać użytkownikom zmianę sposobu skonfigurowania przycisku Strona główna przez administratora.
- **Pokaż stronę pierwszego uruchomienia**: pozycja **Blokuj** blokuje wyświetlanie strony wprowadzenia przy pierwszym uruchomieniu przeglądarki Microsoft Edge. Ta funkcja umożliwia przedsiębiorstwom, takim jak organizacje zarejestrowane w konfiguracjach zeroemisyjnych, na blokowanie tej strony. Pozycja **Nieskonfigurowane** powoduje wyświetlanie strony wprowadzenia.
  - **Adres URL pierwszego uruchomienia**: wprowadź adres URL strony do wyświetlenia, gdy użytkownik po raz pierwszy uruchamia przeglądarkę Microsoft Edge (tylko system Windows 10 Mobile).
- **Odśwież przeglądarkę po bezczynności**: Wprowadź liczbę minut bezczynności, aż przeglądarka zostanie odświeżona, od 0 do 1440 minut. Wartość domyślna to `5` minut. Po ustawieniu `0` (zero), przeglądarka odświeżanie nie odbywa się po okresie bezczynności.

  To ustawienie jest dostępne tylko podczas uruchamiania w [(kiosk jednej aplikacji) na przeglądanie InPrivate publicznych](#use-microsoft-edge-kiosk-mode).

  Dostawcy usług Kryptograficznych: [ConfigureKioskResetAfterIdleTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)

- **Wyskakujące okienka**: wybierz pozycję **Blokuj**, aby uniemożliwić wyświetlanie wyskakujących okienek w przeglądarce. Dotyczy tylko systemu Windows 10 Desktop. Pozycja **Nieskonfigurowane** umożliwia wyświetlane wyskakujących okienek w przeglądarce internetowej.
- **Wysyłaj ruch intranetowy do programu Internet Explorer**: pozycja **Zezwalaj** umożliwia użytkownikom otwieranie intranetowych witryn internetowych w programie Internet Explorer zamiast w przeglądarce Microsoft Edge (tylko system Windows 10 Desktop). Pozycja **Nieskonfigurowane** pozwala użytkownikom na używanie przeglądarki Microsoft Edge.
- **Lokalizacja listy witryn trybu przedsiębiorstwa**: wprowadź adres URL lokalizację listy witryn internetowych, które można otwierać w trybie przedsiębiorstwa. Użytkownicy nie mogą zmieniać tej listy. Dotyczy tylko systemu Windows 10 Desktop.
- **Komunikat podczas otwierania witryn w programie Internet Explorer**: to ustawienie służy do konfigurowania przeglądarki Microsoft Edge w celu wyświetlania powiadomienia przed otwarciem witryny w programie Internet Explorer 11. Dostępne opcje:
  - **Nieskonfigurowane**: jest stosowane domyślne zachowanie systemu operacyjnego, co może sprawiać, że komunikat nie będzie wyświetlany.
  - **Pokaż komunikat bez opcji otwierania witryn w przeglądarce Microsoft Edge**: wyświetlanie komunikatu podczas otwierania witryn w programie IE. Witryny są otwierane w programie IE. Nie ma opcji otwierania witryn w przeglądarce Microsoft Edge.
  - **Pokaż komunikat podczas otwierania witryn w przeglądarce Microsoft Edge**: wyświetlanie komunikatu podczas otwierania witryn w programie IE. Komunikat zawiera link **Kontynuuj pracę w przeglądarce Microsoft Edge**, dzięki któremu użytkownicy mogą wybrać przeglądarkę Microsoft Edge zamiast programu Internet Explorer.

  > [!IMPORTANT]
  > To ustawienie wymaga włączenia ustawienia **Konfigurowanie listy witryn trybu przedsiębiorstwa**, ustawienie **Wysyłanie wszystkich witryn intranetowych do programu Internet Explorer 11** lub obydwa ustawienia.

- **Lista zgodności firmy Microsoft**: pozycja **Blokuj** uniemożliwia wyświetlanie listę zgodności firmy Microsoft w przeglądarce Microsoft Edge. Ta lista firmy Microsoft pomaga przeglądarce Microsoft Edge prawidłowo wyświetlać witryny ze znanymi problemami dotyczącymi zgodności. Pozycja **Nieskonfigurowane** zezwala na korzystanie z listy zgodności firmy Microsoft.
- **Wstępne ładowanie stron startowych i strony nowej karty**: wybierz pozycję **Blokuj**, aby uniemożliwić wstępne ładowanie stron startowych i strony nowej karty w przeglądarce Microsoft Edge. Wstępne ładowanie minimalizuje czas uruchamiania przeglądarce Microsoft Edge i powoduje załadowanie nowej karty. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować wstępne ładowanie tych stron.
- **Wstępne uruchamianie stron startowych i strony nowej karty**: wybierz pozycję **Blokuj**, aby uniemożliwić wstępne ładowanie stron startowych i strony nowej karty w przeglądarce Microsoft Edge. Wstępne uruchomienie zwiększa wydajność przeglądarki Microsoft Edge i minimalizuje czas wymagany do uruchomienia tej przeglądarki. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować wstępne uruchamianie tych stron.

### <a name="favorites-and-search"></a>Ulubione i wyszukiwanie

- **Pasek Ulubione**: wybierz, co się stanie z paskiem ulubionych na dowolnej stronie przeglądarki Microsoft Edge. Dostępne opcje:
  - Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować ukrywania paska ulubionych na wszystkich stronach. Użytkownik może zmieniać to ustawienie.
  - **Ukryj**: ukrywa pasek ulubionych na wszystkich stronach. Użytkownik nie może zmieniać tego ustawienia.
  - **Pokaż**: pokazuje pasek ulubionych na wszystkich stronach. Użytkownik nie może zmieniać tego ustawienia.
- **Lista Ulubione**: dodaj listę adresów URL do pliku ulubionych. Na przykład dodaj `http://contoso.com/favorites.html`.
- **Ograniczanie zmian ulubionych**: pozycja  **Blokuj** uniemożliwia użytkownikom dodawanie, importowanie, sortowanie lub edytowanie listy Ulubione. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może pozwolić użytkownikom na zmienianie listy.
- **Synchronizuj ulubione między przeglądarkami firmy Microsoft (tylko wersja klasyczna)**: pozycja **Wymagaj** wymusza synchronizowanie ulubionych między przeglądarkami Internet Explorer i Microsoft Edge w systemie Windows. Operacje dodawania, usuwania, modyfikacji i zmian kolejności w obszarze ulubionych będą udostępniane między przeglądarkami.  Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może dać użytkownikom opcję synchronizowania między przeglądarkami.
- **Domyślna wyszukiwarka**: wybierz domyślną wyszukiwarkę na urządzeniu. Użytkownicy końcowi mogą w dowolnym momencie zmienić tę wartość. Dostępne opcje:
  - Domyślny
  - Bing
  - Google
  - Yahoo
  - Wartość niestandardowa
- **Sugestie wyszukiwania**: pozycja **Nieskonfigurowane** umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz na pasku adresu. Pozycja **Blokuj** uniemożliwia użycie tej funkcji.
- **Zezwalaj na zmienianie aparatu wyszukiwania**: **tak** (ustawienie domyślne) umożliwia użytkownikom dodawanie nowych aparaty wyszukiwania lub zmienić domyślną wyszukiwarkę w programie Microsoft Edge. Wybierz **nie** aby uniemożliwić użytkownikom dostosowywanie aparatu wyszukiwania.

  To ustawienie jest dostępne tylko podczas uruchamiania w [(kiosk z wieloma aplikacjami) w trybie normalnym](#use-microsoft-edge-kiosk-mode).

  Dostawcy usług Kryptograficznych: [AllowSearchEngineCustomization](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)

### <a name="privacy-and-security"></a>Prywatność i zabezpieczenia

- **Przeglądanie InPrivate**: pozycja **Blokuj** uniemożliwia otwieranie sesji przeglądania InPrivate przez użytkowników końcowych. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Zapisywanie historii przeglądania**: pozycja **Blokuj** uniemożliwia zapisywanie historii przeglądania w programie Microsoft Edge. Pozycja **Nieskonfigurowane** umożliwia zapisywanie historii przeglądania.
- **Wyczyść dane przeglądania przy zamykaniu (tylko wersja Desktop)**: pozycja **Wymagaj** włącza czyszczenie historii i danych przeglądania przy zamykaniu przeglądarki Microsoft Edge. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować buforowanie danych przeglądania.
- **Synchronizuj ustawienia przeglądarki między urządzeniami użytkownika**: wybierz sposób synchronizowania ustawień przeglądarki między urządzeniami. Dostępne opcje:
  - **Zezwalaj**: zezwala na synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika.
  - **Blokuj i włącz nadpisywanie użytkownika**: blokuje synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika. Użytkownicy mogą przesłaniać to ustawienie.
  - **Blokuj**: blokuj synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika. Użytkownicy nie mogą przesłaniać tego ustawienia.
- **Menedżer haseł**: pozycja **Blokuj** wyłącza funkcję menedżera haseł w przeglądarce Microsoft Edge. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Pliki cookie**: wybierz sposób obsługi plików cookie w przeglądarce internetowej. Dostępne opcje:
  - **Zezwalaj**: pliki cookie są przechowywane na urządzeniu.
  - **Blokuj wszystkie pliki cookie**: pliki cookie nie są przechowywane na urządzeniu.
  - **Blokuj tylko pliki cookie innych firm**: pliki cookie innych firm lub partnerów nie są przechowywane na urządzeniu.
- **Autowypełnianie**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce (tylko system Windows 10 Desktop).
- **Wysyłanie nagłówków Nie śledź**: pozycja **Nieskonfigurowane** wymaga, aby urządzenia wysyłały nagłówki Nie śledź do witryn internetowych żądających informacji dotyczących śledzenia (zalecane). Wybierz pozycję **Blokuj**, aby uniemożliwić urządzeniu wysyłanie tych nagłówków, co pozwoli witrynom internetowym na śledzenie użytkownika.
- **Adres IP lokalnego hosta dla protokołu WebRtc**: pozycja **Blokuj** uniemożliwia wyświetlanie adresu IP lokalnego hosta użytkownika podczas nawiązywania połączeń telefonicznych przy użyciu protokołu internetowego RTC. Pozycja **Nieskonfigurowane** umożliwia wyświetlanie adres IP lokalnego hosta użytkowników podczas nawiązywania połączeń telefonicznych przy użyciu tego protokołu.
- **Zbieranie danych dynamicznych kafelków**: wybierz pozycję **Blokuj**, aby uniemożliwić systemowi Windows zbieranie informacji z dynamicznych kafelków podczas przypinania witryny z przeglądarki Microsoft Edge do menu Start. Pozycja **Nieskonfigurowane** umożliwia zbieranie tych informacji.
- **Użytkownik może nadpisywać błędy certyfikatów**: pozycja **Blokuj** uniemożliwia użytkownikom uzyskiwanie dostępu do witryn internetowych z błędami protokołu SSL lub TLS. Pozycja **Nieskonfigurowane** umożliwia użytkownikom uzyskiwanie dostępu do tych witryn.

### <a name="additional"></a>Dodatkowe

- **Przeglądarka Microsoft Edge (tylko urządzenia przenośne)**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie programu Microsoft Edge na urządzeniu. Jeśli zablokujesz przeglądarkę Microsoft Edge, poszczególne ustawienia będą dotyczyć tylko pulpitu. Pozycja **Nieskonfigurowane** umożliwia korzystanie z przeglądarki internetowej Microsoft Edge na urządzeniu.
- **Rozwijanie paska adresu (tylko wersja klasyczna)**: pozycja **Blokuj** uniemożliwia przeglądarce Microsoft Edge wyświetlanie sugestii na liście rozwijanej podczas wpisywania tekstu. Ta opcja pozwala zmniejszyć przepustowość sieci w ramach komunikacji między przeglądarką Microsoft Edge a usługami firmy Microsoft. Pozycja **Nieskonfigurowane** umożliwia wyświetlanie listy sugestii w przeglądarce Microsoft Edge.
- **Pełny ekran**: wybierz pozycję **Blokuj**, aby uniemożliwić przeglądarce Microsoft Edge wyświetlanie tylko zawartości internetowej i ukrywanie przeglądarki Microsoft Edge (trybie pełnoekranowy). Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które pozwala przeglądarce Microsoft Edge na pracę w trybie pełnoekranowym.
- **Flagi informacyjne**: pozycja **Blokuj** uniemożliwia użytkownikom uzyskiwanie dostępu do strony `about:flags` przeglądarki Microsoft Edge, która zawiera ustawienia deweloperskie i eksperymentalne. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może pozwolić uzyskiwanie dostępu do strony `about:flags`.
- **Narzędzia programistyczne**: pozycja **Blokuj** uniemożliwia użytkownikowi końcowemu otwieranie narzędzi programistycznych przeglądarki Microsoft Edge. Pozycja **Nieskonfigurowane** umożliwia użytkownikom otwieranie narzędzi programistycznych.
- **Rozszerzenia**: pozycja **Nieskonfigurowane** umożliwia użytkownikowi końcowemu instalowanie rozszerzeń przeglądarki Microsoft Edge na urządzeniu. Pozycja **Blokuj** uniemożliwia instalację.
- **Ładowanie bezpośrednie rozszerzeń dla deweloperów**: pozycja **Blokuj** uniemożliwia przeglądarce Microsoft Edge ładowanie bezpośrednie, które polega na instalowaniu i uruchamianiu niezweryfikowanych rozszerzeń przy użyciu funkcji **ładowania rozszerzeń**. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może pozwolić na ładowanie bezpośrednie.
- **Wymagane rozszerzenia**: wybierz rozszerzenia, których użytkownicy końcowi nie mogą wyłączać w przeglądarce Microsoft Edge. Wprowadź nazwy rodzin pakietów, a następnie wybierz pozycję **Dodaj**. Wskazówki można znaleźć w temacie [Find a package family name (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) (Znajdowanie nazwy rodziny pakietów (PFN)).

  Możesz również **zaimportować** plik CSV, który zawiera nazwy rodzin pakietów.

- **JavaScript**: wybierz pozycję **Blokuj**, aby uniemożliwić uruchamianie skryptów języka Java w przeglądarce na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia uruchamianie skryptów, takich jak JavaScript, w przeglądarce Microsoft Edge.

## <a name="network-proxy"></a>Serwer proxy sieci

- **Automatycznie wykrywaj ustawienia proxy**: po włączeniu tego ustawienia urządzenie spróbuje znaleźć ścieżkę do skryptu PAC.
- **Użyj skryptu serwera proxy**: wybierz tę opcję, jeśli chcesz określić ścieżkę do skryptu PAC, aby skonfigurować serwer proxy.
  - **Adres URL skryptu konfiguracji**: wprowadź adres URL skryptu PAC, którego chcesz użyć do skonfigurowania serwera proxy.
- **Użyj ręcznego serwera proxy**: wybierz tę opcję, jeśli chcesz ręcznie wprowadzać informacje o serwerze proxy.
  - **Adres**: wprowadź nazwę lub adres IP serwera proxy.
  - **Numer portu**: wprowadź numer portu serwera proxy.
  - **Wyjątki serwera proxy**: wprowadź wszystkie adresy URL, w przypadku których korzystanie z serwera proxy będzie zabronione. Rozdziel kolejne elementy średnikiem.
  - **Pomiń serwer proxy dla adresów lokalnych**: włącz tę opcję, jeśli nie chcesz używać serwera proxy dla adresów lokalnych w sieci intranet.

## <a name="password"></a>Hasło

- **Hasło**: wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
  - **Wymagany typ hasła**: określa, czy hasło musi być wyłącznie numeryczne, czy też alfanumeryczne.
  - **Minimalna długość hasła**: dotyczy tylko systemu Windows 10 Mobile.
  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: jeśli na urządzeniu z systemem Windows 10 została włączona funkcja BitLocker, po określonej liczbie nieudanych prób logowania zostanie ono przełączone w tryb odzyskiwania funkcji BitLocker. Jeśli na urządzeniu nie została włączona funkcja BitLocker, to ustawienie nie będzie miało zastosowania. Na urządzeniach z systemem Windows 10 Mobile: po wprowadzonej liczbie niepowodzeń logowania urządzenie zostanie wyczyszczone.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określa, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
  - **Wygaśnięcie hasła (dni)**: określa czas, po którym należy zmienić hasło urządzenia.
  - **Zapobiegaj ponownemu użyciu starych haseł**: określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.
  - **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności**: określa, że użytkownik musi wprowadzić hasło, aby odblokować urządzenie (tylko system Windows 10 Mobile).
  - **Proste hasła**: umożliwia korzystanie z prostych haseł, takich jak 1111 lub 1234. To ustawienie zezwala również na używanie haseł obrazkowych systemu Windows lub blokuje tę możliwość.

## <a name="per-app-privacy-exceptions"></a>Wyjątki prywatności dla aplikacji

Możesz dodawać aplikacje, dla których chcesz określić inne zachowanie dotyczące prywatności niż zachowanie zdefiniowane w domyślnym ustawieniu prywatności.

- **Nazwa pakietu**: nazwa rodziny pakietów aplikacji.
- **Nazwa aplikacji**: nazwa aplikacji.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie**: określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle**: określ, czy ta aplikacja może działać w tle.
- **Kalendarz**: określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń**: określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny**: określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty**: określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail**: określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości**: określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości tekstowe lub MMS.
- **Mikrofon**: określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia**: określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon**: określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe**: niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania**: określ, czy ta aplikacja może uzyskiwać dostęp do zadań.
- **Zaufane urządzenia**: Wybierz, jeśli ta aplikacja może używać zaufanych urządzeń. Zaufane urządzenia to sprzęt, z którym już nawiązano połączenie, lub sprzęt dołączony do urządzenia. Jako zaufanych urządzeń można na przykład użyć telewizorów, projektorów itd.
- **Opinie i diagnostyka**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami**: wybierz, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym urządzeniem.

## <a name="personalization"></a>Personalizacja

- **Adres URL obrazu tła pulpitu (tylko dla komputerów stacjonarnych)**: wprowadź adres URL obrazu w formacie JPEG, który będzie używany jako tapeta pulpitu systemu Windows. Użytkownicy nie mogą zmieniać obrazu.

## <a name="printer"></a>Drukarka

- **Drukarki**: lista dodanych drukarek lokalnych.
- **Drukarka lokalna**: ustaw tę drukarkę jako domyślną.
- **Dostęp użytkownika pozwalający na dodanie nowych drukarek**: zezwala na korzystanie z drukarek lokalnych lub je blokuje.

## <a name="privacy"></a>Ochrona prywatności

- **Personalizacja danych wejściowych**: nie zezwala na korzystanie z chmurowych usług przetwarzania mowy razem z aplikacją Cortana, funkcją dyktowania czy aplikacjami ze Sklepu Microsoft. Jeśli zezwolisz na te usługi, firma Microsoft może zbierać dane dotyczące głosu w celu usprawnienia świadczonej usługi.
- **Automatyczne akceptowanie w przypadku monitów o wyrażenie zgody przez użytkownika dotyczących parowania i prywatności**: zezwala systemowi Windows na automatyczne akceptowanie komunikatów dotyczących parowania i prywatności wyświetlanych w uruchamianych aplikacjach.
- **Publikuj działania użytkownika**: pozycja **Blokuj** uniemożliwia udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań.
- **Tylko działania lokalne**: pozycja **Blokuj** uniemożliwia udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań jedynie na podstawie działań lokalnych.

Można skonfigurować informacje, do których mogą uzyskiwać dostęp wszystkie aplikacje na urządzeniu. Ponadto należy zdefiniować wyjątki dla poszczególnych aplikacji, korzystając z opcji **Wyjątki prywatności dla aplikacji**.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie**: określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle**: określ, czy ta aplikacja może działać w tle.
- **Kalendarz**: określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń**: określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny**: określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty**: określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail**: określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości**: określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości tekstowe lub MMS.
- **Mikrofon**: określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia**: określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon**: określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe**: niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania**: określ, czy ta aplikacja może uzyskiwać dostęp do zadań.
- **Zaufane urządzenia**: Wybierz, jeśli ta aplikacja może używać zaufanych urządzeń. Zaufane urządzenia to sprzęt, z którym już nawiązano połączenie, lub sprzęt dołączony do urządzenia. Jako zaufanych urządzeń można na przykład użyć telewizorów, projektorów itd.
- **Opinie i diagnostyka**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami** — określ, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym komputerem, tabletem lub telefonem.

## <a name="projection"></a>Projekcja

- **Dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych**: blokuje dane wejściowe użytkownika z odbiorników wyświetlaczy bezprzewodowych.
- **Projekcja na tym komputerze**: uniemożliwia innym urządzeniom odnajdywanie tego komputera dla celów projekcji.
- **Wymagaj numeru PIN do parowania**: wybór powoduje, że podczas nawiązywania połączenia z urządzeniem do projekcji wymagane jest podanie numeru PIN.

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia**: wybierz poziom przesyłanych danych diagnostycznych. Dostępne opcje:
  - Zabezpieczenia
  - Podstawowe
  - Zaawansowane
  - Pełna
- **Wysyłanie danych przeglądania przeglądarki Microsoft Edge do usługi Microsoft 365 Analytics**: aby użyć tej funkcji, należy zdefiniować ustawienie **Udostępnij dane użycia** jako **Rozszerzone** lub **Pełne**. Ta funkcja kontroluje dane, które przeglądarka Microsoft Edge wysyła do usługi Microsoft 365 Analytics dla urządzeń firmowych przy użyciu skonfigurowanego identyfikatora komercyjnego. Dostępne opcje:
  - **Nieskonfigurowane**: używa domyślnego zachowania systemu operacyjnego, które może powodować, że żadne dane historii przeglądania nie będą wysyłane
  - **Wysyłaj tylko dane intranetowe**: umożliwia administratorowi wysyłanie historii danych intranetowych
  - **Wysyłaj tylko dane internetowe**: umożliwia administratorowi wysyłanie historii danych internetowych
  - **Wysyłaj dane intranetowe i internetowe**: umożliwia administratorowi wysyłanie historii danych intranetowych i internetowych
- **Serwer proxy telemetrii**: wprowadź w pełni kwalifikowaną nazwę domeny (FQDN) lub adres IP serwera proxy do przekazywania żądań środowisk i telemetrii połączonego użytkownika przy użyciu połączenia SSL (Secure Sockets Layer). Format dla tego ustawienia to: *serwer*:*port*. Jeśli nazwany serwer proxy ulegnie awarii lub jeśli serwer proxy nie zostanie wprowadzony w momencie włączenia tych zasad, dane środowisk i telemetrii połączonego użytkownika nie zostaną wysłane i pozostaną na urządzeniu lokalnym.

  Przykładowe formaty:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Wyszukaj

- **Bezpieczne wyszukiwanie (tylko urządzenia przenośne)**: pozwala określić sposób, w jaki Cortana filtruje treści dla dorosłych w wynikach wyszukiwania. Można wybrać opcję **Ścisłe** lub **Umiarkowane** albo zezwolić użytkownikom końcowym na wybór własnych ustawień.
- **Wyświetl wyniki internetowe w wyszukiwaniu**: umożliwia blokowanie lub akceptowanie wyświetlania wyników internetowych w wynikach wyszukiwania na urządzeniu.

## <a name="start"></a>Początek

- **Układ menu Start**: w celu dostosowania menu Start na urządzeniach stacjonarnych można przekazać plik XML zawierający dostosowania, w tym kolejność wyświetlania aplikacji i nie tylko. Użytkownicy nie mogą zmieniać wprowadzonego w ten sposób układu menu Start.
- **Przypinaj witryny internetowe do kafelków w menu Start**: zaimportuj obrazy z przeglądarki Microsoft Edge, które będą wyświetlane jako linki w menu Start systemu Windows dla urządzeń stacjonarnych.
- **Odpinanie aplikacji od paska zadań**: wybierz opcję **Blokuj**, aby uniemożliwić użytkownikom odpinanie aplikacji od paska zadań.
- **Szybkie przełączanie użytkowników**: wybierz pozycję **Blokuj**, aby uniemożliwić przełączanie się między zalogowanymi jednocześnie użytkownikami bez wylogowywania się.
- **Najczęściej używane aplikacje**: wybierz pozycję **Blokuj**, aby ukrywać najczęściej używane aplikacje w menu Start. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia.
- **Ostatnio dodane aplikacje**: wybierz pozycję **Blokuj**, aby ukrywać ostatnio dodane aplikacje w menu Start. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia.
- **Tryb ekranu startowego**: wybierz sposób wyświetlania ekranu startowego. Wybierz opcję wyświetlania **Pełny ekran** lub **Niepełny ekran**.
- **Ostatnio otwierane elementy list szybkiego dostępu**: wybierz pozycję **Blokuj**, aby ukrywać listy szybkiego dostępu do ostatnich elementów w menu Start i na pasku zadań. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia.
- **Lista aplikacji**: wybierz sposób wyświetlania aplikacji Ustawienia. Dostępne opcje: 
  - Zwiń
  - Zwiń i wyłącz aplikację Ustawienia 
  - Usuwa i wyłącza aplikację Ustawienia
- **Przycisk zasilania**: pozycja **Blokuj** powoduje ukrycie przycisku zasilania w menu Start.
- **Kafelek użytkownika**: pozycja **Blokuj** powoduje ukrycie kafelka użytkownika w menu Start.
  - **Blokada**: pozycja **Blokuj** powoduje ukrycie opcji `Lock` na kafelku użytkownika w menu Start.
  - **Wyloguj się**: pozycja **Blokuj** powoduje ukrycie opcji `Sign out` na kafelku użytkownika w menu Start.
- **Zamknij**: pozycja **Blokuj** powoduje ukrycie opcji `Update and shut down` i `Shut down` na przycisku zasilania w menu Start.
- **Uśpienie**: pozycja **Blokuj** powoduje ukrycie opcji `Sleep` na przycisku zasilania w menu Start.
- **Hibernacja**: pozycja **Blokuj** powoduje ukrycie opcji `Hibernate` na przycisku zasilania w menu Start.
- **Przełącz konto**: pozycja **Blokuj** powoduje ukrycie opcji `Switch account` na kafelku użytkownika w menu Start.
- **Opcje ponownego uruchamiania**: pozycja **Blokuj** powoduje ukrycie opcji `Update and restart` i `Restart` na przycisku zasilania w menu Start.
- **Folder Dokumenty w menu Start**: pozwala ukryć lub pokazać folder Dokumenty w menu Start systemu Windows.
- **Folder Pliki do pobrania w menu Start**: pozwala ukryć lub pokazać folder pobranych plików w menu Start systemu Windows.
- **Folder Eksplorator plików w menu Start**: pozwala ukryć lub pokazać aplikację Eksplorator plików w menu Start systemu Windows.
- **Folder Grupa domowa w menu Start**: pozwala ukryć lub pokazać folder Grupa domowa w menu Start systemu Windows.
- **Folder Muzyka w menu Start**: pozwala ukryć lub pokazać folder Muzyka w menu Start systemu Windows.
- **Folder Sieć w menu Start**: pozwala ukryć lub pokazać folder Sieć w menu Start systemu Windows.
- **Folder Osobiste w menu Start**: pozwala ukryć lub pokazać folder Osobiste w menu Start systemu Windows.
- **Folder Obrazy w menu Start**: pozwala ukryć lub pokazać folder obrazów w menu Start systemu Windows.
- **Folder Ustawienia w menu Start**: pozwala ukryć lub pokazać aplikację Ustawienia w menu Start systemu Windows.
- **Folder Wideo w menu Start**: pozwala ukryć lub pokazać folder Wideo w menu Start systemu Windows.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **Filtr SmartScreen dla przeglądarki Microsoft Edge**: włącz filtr SmartScreen dla przeglądarki Microsoft Edge używany podczas uzyskiwania dostępu do witryn i pobierania plików.
- **Dostęp do złośliwych witryn**: zablokuj użytkownikom możliwość ignorowania ostrzeżeń filtru Windows Defender SmartScreen oraz przechodzenia do witryny.
- **Pobieranie niezweryfikowanych plików**: zablokuj użytkownikom możliwość ignorowania ostrzeżeń filtru Windows Defender SmartScreen oraz pobierania niezweryfikowanych plików.

## <a name="windows-spotlight"></a>W centrum uwagi Windows

- **W centrum uwagi Windows**: to ustawienie umożliwia zablokowanie wszystkich funkcji W centrum uwagi Windows na urządzeniach z systemem Windows 10. Jeśli to ustawienie zostanie wyłączone, następujące ustawienia nie będą dostępne:
  - **Funkcja W centrum uwagi Windows na ekranie blokady**: wyłącza wyświetlanie informacji funkcji W centrum uwagi Windows na ekranie blokady urządzenia.
  - **Sugestie innych firm w funkcji W centrum uwagi Windows**: wyłącza sugerowanie zawartości niepochodzącej z firmy Microsoft przez funkcję W centrum uwagi Windows.
  - **Funkcje dla konsumentów**: umożliwia blokowanie funkcji dla konsumentów, takich jak sugestie w menu Start, powiadomienia dotyczące członkostwa itp.
  - **Porady dotyczące systemu Windows**: umożliwia zablokowanie wyskakujących okienek z poradami w systemie Windows.
  - **Funkcja W centrum uwagi Windows w Centrum akcji**: uniemożliwia wyświetlanie sugestii funkcji W centrum uwagi Windows, na przykład zawartości dotyczących nowych aplikacji lub zabezpieczeń, w Centrum akcji systemu Windows.
  - **Personalizacja funkcji W centrum uwagi Windows**: wyłącza personalizowanie opartych na użyciu urządzenia wyników przez funkcję W centrum uwagi Windows.
  - **Środowisko powitalne systemu Windows**: wyłącza wyświetlanie środowiska powitalnego systemu Windows, w którym są widoczne informacje o nowych lub zaktualizowanych funkcjach.

## <a name="windows-defender-antivirus"></a>Program antywirusowy Windows Defender

- **Monitorowanie w czasie rzeczywistym**: włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.
- **Monitorowanie zachowania**: umożliwia usłudze Defender sprawdzanie urządzeń pod kątem określonych wzorców podejrzanej aktywności.
- **Network Inspection System (NIS)**: pomaga w ochronie urządzeń przed sieciowymi atakami wykorzystującymi luki w zabezpieczeniach. System NIS korzysta z sygnatur znanych luk w zabezpieczeniach z centrum programu Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch.
- **Skanuj wszystkie pobrane pliki**: określa, czy usługa Defender ma skanować wszystkie pliki pobierane z Internetu.
- **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft**: umożliwia usłudze Defender skanowanie skryptów używanych przez przeglądarkę Internet Explorer.
- **Dostęp użytkownika końcowego do narzędzia Defender**: określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych. Zmiany tego ustawienia zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika.
- **Interwał aktualizacji sygnatur (w godzinach)**: wprowadź interwał sprawdzania dostępności nowych plików sygnatur przez usługę Defender.
- **Monitoruj działanie plików i programów**: zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach.
- **Dni przed usunięciem szkodliwego oprogramowania w kwarantannie**: kontynuować śledzenie usuniętego złośliwego oprogramowania liczbę dni, możesz wprowadzić, pozwala na ręczne sprawdzenie wcześniej wpływ na urządzenia. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane.
- **Limit wykorzystania procesora CPU podczas skanowania**: ogranicz użycie procesora dozwolone dla procesów skanowania w skali od **1** do **100**.
- **Skanuj pliki archiwów**: zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.
- **Skanuj przychodzące wiadomości e-mail**: zezwala usłudze Defender na skanowanie wiadomości e-mail dostarczanych do urządzenia.
- **Skanuj dyski wymienne podczas pełnego skanowania**: umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.
- **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania**: umożliwia usłudze Defender skanowanie plików na zamapowanych dyskach sieciowych.
  Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
- **Skanuj pliki otwierane z folderów sieciowych**: umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach dostępnych za pośrednictwem ścieżki UNC). Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
- **Ochrona w chmurze**: zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Tych informacji usprawnia usługi w przyszłości.
- **Monituj użytkowników przed przesłaniem próbki**: określa, czy do firmy Microsoft są automatycznie wysyłane potencjalnie złośliwe pliki, które mogą wymagać dalszej analizy.
- **Godzina przeprowadzania codziennego szybkiego skanowania**: Wybierz godzinę uruchamiaj codzienne szybkie skanowanie. **Nieskonfigurowane** codzienne skanowanie nie zostanie uruchomiona. Jeśli większym stopniu, należy skonfigurować **typ skanowania systemu do wykonania** ustawienie.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) (Zasady zabezpieczeń zawartości Defender/ScheduleQuickScanTime)
- **Typ skanowania systemu do wykonania**: Zaplanuj skanowanie systemu, w tym poziom skanowania i dzień i godzinę, aby uruchomić skanowanie. Dostępne opcje:
  - **Nieskonfigurowane**: nie Zaplanuj skanowanie systemu na urządzeniu. Użytkownicy końcowi mogą ręcznie uruchomić skanowania jako wymagane lub niepożądane, na swoich urządzeniach.
  - **Wyłącz**: wyłącza każdego systemu, skanowania na urządzeniu. Wybierz tę opcję, jeśli używasz rozwiązania partnerskiego oprogramowanie antywirusowe skanuje urządzeń.
  - **Szybkie skanowanie w poszukiwaniu**: typowe lokalizacje, w przypadku, gdy istnieje złośliwe oprogramowanie może być zarejestrowane, takie jak klucze rejestru i znane foldery uruchamiania Windows.
    - **Zaplanowany dzień**: Wybierz dzień, aby uruchomić skanowanie.
    - **Zaplanowana godzina**: Wybierz godzinę, aby uruchomić skanowanie.
  - **Pełne skanowanie w poszukiwaniu**: typowe lokalizacje, w których może być złośliwego oprogramowania rejestrowane i również przeskanuje każdego pliku i folderu na urządzeniu.
    - **Zaplanowany dzień**: Wybierz dzień, aby uruchomić skanowanie.
    - **Zaplanowana godzina**: Wybierz godzinę, aby uruchomić skanowanie.

  To ustawienie może spowodować konflikt z **godzina przeprowadzania codziennego szybkiego skanowania** ustawienie. Niektóre rekomendacje:

  - Aby uruchomić codzienne szybkie skanowanie, należy skonfigurować **godzina przeprowadzania codziennego szybkiego skanowania** ustawienie.
  - Aby uruchomić codziennego szybkiego skanowania i pełne skanowanie w poszukiwaniu co tydzień, następnie skonfiguruj **godzina przeprowadzania codziennego szybkiego skanowania**i ustaw **typ skanowania systemu do wykonania** do pełnego skanowania za pomocą datę i godzinę.
  - Nie należy konfigurować **godzina przeprowadzania codziennego szybkiego skanowania** ustawienie równocześnie z **typ skanowania systemu do wykonania** równa **szybkie skanowanie w poszukiwaniu**. Te ustawienia mogą powodować konflikt, a skanowanie może nie działać.
  - Aby uruchomić szybkie skanowanie każdy wtorek o 6: 00, należy skonfigurować **typ skanowania systemu do wykonania** ustawienie.

  [Usługa Defender/ScanParameter dostawcy usług Kryptograficznych](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Usługa Defender/ScheduleScanDay dostawcy usług Kryptograficznych](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Usługa Defender/ScheduleScanTime dostawcy usług Kryptograficznych](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- **Wykrywaj potencjalnie niepożądane aplikacje**: pozwala wybrać poziom ochrony w przypadku wykrycia potencjalnie niechcianych aplikacji przez system Windows:
  - **Zablokuj**
  - **Inspekcja** Aby uzyskać więcej informacji dotyczących potencjalnie niepożądanych aplikacji, zobacz temat [Detect and block potentially unwanted applications](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus) (Wykrywanie i blokowanie potencjalnie niepożądanych aplikacji).
- **Akcje do podjęcia wobec wykrytych zagrożeń związanych ze złośliwym oprogramowaniem**: wybierz akcje, które ma podejmować usługa Defender po wykryciu zagrożenia określonego poziomu, takiego jak: niski, umiarkowany, wysoki i poważny. Dostępne opcje:
  - **Wyczyść**
  - **Kwarantanna**
  - **Usuń**
  - **Zezwalaj**
  - **Zdefiniowane przez użytkownika**
  - **Zablokuj**

### <a name="windows-defender-antivirus-exclusions"></a>Wyjątki programu antywirusowego Windows Defender

- **Pliki i foldery do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: umożliwia dodanie do listy wykluczeń pojedynczych plików lub folderów lub większej ich liczby, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.
- **Rozszerzenia plików do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: umożliwia dodanie do listy wykluczeń pojedynczych rozszerzeń plików lub większej ich liczby, np. **JPG** lub **TXT**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym lub skanowania planowanego.
- **Procesy do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: umożliwia dodanie do listy wykluczeń pojedynczych procesów typu **EXE**, **COM** lub **SCR** lub większej ich liczby. Te procesy nie są uwzględniane podczas skanowania w czasie rzeczywistym ani podczas zaplanowanego skanowania.

## <a name="next-steps"></a>Następne kroki

Dodatkowe szczegóły techniczne poszczególnych ustawień oraz obsługiwanych wersji systemu Windows można znaleźć w [dokumentacji dotyczącej dostawcy usługi konfiguracji dla zasad systemu Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
