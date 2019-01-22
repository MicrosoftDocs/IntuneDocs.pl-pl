---
title: Ustawienia ograniczeń urządzeń dla systemu Windows 10 w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień dotyczących tworzenia ograniczeń dotyczących urządzeń z systemie Windows 10 lub nowszym oraz z ich opisami. Te ustawienia w profilu konfiguracji służą do kontrolowania zrzutów ekranu, wymagań dotyczących haseł, ustawień kiosku, aplikacji w sklepie, przeglądarki Microsoft Edge, usługi Windows Defender, dostępu do chmury, menu Start i innych elementów w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: f2b75eb5a87dbfd7a17aee83f173d3d472920428
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203641"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem Windows 10 (i nowszym) w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune

W tym artykule wymieniono i opisano wszystkie różne ustawienia, którymi można sterować na urządzeniach z systemem Windows 10 i nowszym. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, dostosowywać ekran blokady, korzystać z programu Windows Defender i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem Windows 10.

> [!Note]
> Nie wszystkie opcje są dostępne we wszystkich wersjach systemu Windows

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md).

## <a name="app-store"></a>App Store

- **App Store (tylko dla urządzeń przenośnych)**: Umożliwia lub blokuje korzystanie ze sklepu z aplikacjami na urządzeniach z systemem Windows 10 Mobile.
- **Automatycznie aktualizuj aplikacje ze sklepu**: Umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze sklepu Microsoft Store.
- **Instalacja aplikacji zaufanej**: Umożliwia ładowanie bezpośrednie aplikacji podpisanych za pomocą zaufanego certyfikatu.
- **Odblokowanie trybu deweloperskiego**: Umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, na przykład zezwolenie użytkownikowi końcowemu na modyfikację aplikacji ładowanych bezpośrednio.
- **Współużytkowane dane aplikacji użytkownika**: Umożliwia aplikacjom udostępnianie danych różnym użytkownikom na tym samym urządzeniu.
- **Używaj tylko sklepu prywatnego**: Po włączeniu tego ustawienia użytkownicy końcowi będą mogli pobierać aplikacje wyłącznie z udostępnionego im sklepu prywatnego.
- **Uruchamianie aplikacji pochodzącej ze sklepu**: Ustawienie pozwala wyłączyć wszystkie aplikacje, które zostały wcześniej zainstalowane na urządzeniu lub pobrane ze Sklepu Microsoft.
- **Instaluj dane aplikacji na woluminie systemowym**: Uniemożliwia aplikacjom przechowywanie danych na woluminie systemowym urządzenia.
- **Instaluj aplikacje na dysku systemowym**: Uniemożliwia aplikacjom przechowywanie danych na dysku systemowym urządzenia.
- **DVR z gry (tylko dla komputerów stacjonarnych)**: Pozwala określić, czy nagrania i emisje z gier są dozwolone.
- **Tylko aplikacje ze sklepu**: Określa, czy użytkownicy mogą instalować aplikacje z miejsc innych niż sklep z aplikacjami.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Kanał danych komórkowych**: Uniemożliwia użytkownikom korzystanie z danych sieci komórkowej, na przykład przeglądanie Internetu. 
- **Roaming danych**: Umożliwia roaming między sieciami przy dostępie do danych.
- **Sieć VPN przez sieć komórkową**: Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku połączenia z siecią komórkową.
- **Roaming sieci VPN przez sieć komórkową**: Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.
- **Bluetooth**: Określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
- **Odnajdowanie Bluetooth**: Umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
- **Wstępne parowanie przy Bluetooth**: Umożliwia skonfigurowanie automatycznego łączenia się określonych urządzeń Bluetooth z urządzeniem hosta.
- **Reklamy Bluetooth**: Umożliwia urządzeniu odbieranie reklam przez połączenie Bluetooth.
- **Usługa podłączonych urządzeń**: Określa, czy zezwalać na używanie usługi podłączonych urządzeń, która umożliwia odnajdowanie i nawiązywanie połączenia z innymi urządzeniami Bluetooth.
- **NFC**: Umożliwia użytkownikowi włączanie i konfigurowanie funkcji komunikacji zbliżeniowej (NFC) na urządzeniu.
- **Wi-Fi**: Umożliwia użytkownikowi włączanie i konfigurowanie sieci Wi-Fi na urządzeniu (tylko system Windows 10 Mobile).
- **Automatycznie łącz się z hotspotami Wi-Fi**: Umożliwia urządzeniu automatyczne łączenie się z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.
- **Ręczna konfiguracja sieci Wi-Fi**: Określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi (tylko system Windows 10 Mobile).
- **Interwał skanowania sieci Wi-Fi**: Pozwala określić, jak często urządzenie ma wyszukiwać sieci Wi-Fi. Podaj wartość z zakresu od 1 (najczęściej) do 500 (najrzadziej).
- **Dozwolone usługi Bluetooth**: Lista dozwolonych usług i profilów Bluetooth określana w postaci ciągów szesnastkowych.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Konto Microsoft**: Zezwala użytkownikowi na skojarzenie konta Microsoft z urządzeniem.
- **Konto inne niż Microsoft**: Umożliwia użytkownikowi dodanie na urządzeniu kont poczty e-mail, które nie są skojarzone z kontem Microsoft.
- **Synchronizacja ustawień dla konta Microsoft**: Zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między urządzeniami.

## <a name="cloud-printer"></a>Drukarka w chmurze

- **Adres URL na potrzeby wykrywania drukarek**: Wprowadź adres URL służący do wyszukiwania drukarek w chmurze.
- **Adres URL urzędu dostępu do drukarek**: Wprowadź adres URL punktu końcowego uwierzytelniania na potrzeby pobierania tokenów OAuth. Na przykład wpisz coś takiego: `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **Identyfikator GUID aplikacji klienta natywnego platformy Azure**: Wprowadź identyfikator GUID aplikacji klienckiej upoważnionej do pobierania tokenów OAuth z urzędu OAuthAuthority.
- **Identyfikator URI zasobu usługi drukowania**: Wprowadź identyfikator URI zasobu OAuth dla usługi drukowania skonfigurowanej w witrynie Azure Portal. Na przykład wpisz coś takiego: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maksymalna liczba drukarek do uwzględnienia w zapytaniu (tylko wersja mobilna)**: Wprowadź maksymalną liczbę drukarek, która powinna zostać uwzględniona w zapytaniu. Na przykład wprowadź `10`.
- **Identyfikator URI zasobu usługi wykrywania drukarek**: Wprowadź identyfikator URI zasobu OAuth dla usługi wykrywania drukarek skonfigurowany w witrynie Azure Portal. Na przykład wpisz coś takiego: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Po skonfigurowaniu [hybrydowego drukowania w chmurze systemu Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview) można skonfigurować te ustawienia, a następnie wdrożyć je na urządzeniach z systemem Windows.

## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

- **Aplikacja Ustawienia**: Blokuje dostęp do aplikacji Ustawienia systemu Windows.
  - **System**: Blokuje dostęp do obszaru systemu w aplikacji Ustawienia.
    - **Modyfikowanie ustawień zasilania i uśpienia (tylko dla komputerów stacjonarnych)**: Uniemożliwia użytkownikowi końcowemu zmianę ustawień zasilania i uśpienia na urządzeniu.
  - **Urządzenia**: Blokuje dostęp do obszaru urządzeń w aplikacji Ustawienia.
  - **Sieć i Internet**: Blokuje dostęp do obszaru sieci i Internetu w aplikacji Ustawienia.
  - **Personalizacja**: Blokuje dostęp do obszaru personalizacji w aplikacji Ustawienia.
  - **Konta:** Blokuje dostęp do obszaru kont w aplikacji Ustawienia.
  - **Czas i język**: Blokuje dostęp do obszaru czasu i języka w aplikacji Ustawienia.
    - **Modyfikowanie czasu systemowego**: Uniemożliwia użytkownikowi końcowemu zmianę daty i godziny na urządzeniu.
    - **Modyfikowanie ustawień regionu (tylko komputer)**: Uniemożliwia zmianę ustawień regionu na urządzeniu przez użytkownika końcowego.
    - **Modyfikowanie ustawień języka (tylko dla komputerów stacjonarnych):** Uniemożliwia zmianę ustawień języka na urządzeniu przez użytkownika.
  - **Gry**: Blokuje dostęp do aplikacji Gry w obszarze Ustawienia.
  - **Ułatwienia dostępu**: Blokuje dostęp do obszaru ułatwień dostępu w aplikacji Ustawienia.
  - **Prywatność**: Blokuje dostęp do obszaru prywatności w aplikacji Ustawienia.
  - **Aktualizacja i zabezpieczenia**: Blokuje dostęp do obszaru aktualizacji i zabezpieczeń w aplikacji Ustawienia.

## <a name="display"></a>Wyświetlanie

- **Włącz skalowanie z użyciem interfejsu GDI dla aplikacji**
- **Wyłącz skalowanie z użyciem interfejsu GDI dla aplikacji**

  Skalowanie DPI z użyciem interfejsu GDI umożliwia rozpoznawanie wartości DPI monitora tym aplikacjom, które jej nie rozpoznają. Wprowadź starsze aplikacje, które mają włączone skalowanie DPI z użyciem interfejsu GDI. Jeśli w aplikacji skonfigurowano włączanie i wyłączanie skalowania DPI z użyciem interfejsu GDI, skalowanie dla aplikacji jest wyłączone.

## <a name="general"></a>Ogólne

- **Przechwytywanie ekranu (tylko dla urządzeń przenośnych)**: Umożliwia użytkownikowi przechwytywanie ekranu urządzenia w formie obrazu.
- **Kopiuj i wklej (tylko urządzenia przenośne)**: Umożliwia kopiowanie i wklejanie między aplikacjami na urządzeniu.
- **Ręczne wyrejestrowanie**: Umożliwia użytkownikowi ręczne usunięcie z urządzenia konta w miejscu pracy.
  - To ustawienie zasad nie jest stosowane, jeśli komputer jest przyłączony do usługi Azure AD i włączono automatyczne rejestrowanie. 
  - To ustawienie zasad nie ma zastosowania do komputerów z systemem Windows 10 Home.
- **Ręczne instalowanie certyfikatu głównego (tylko dla urządzeń przenośnych)**: Uniemożliwia użytkownikowi ręczne instalowanie certyfikatów głównych i certyfikatów pośrednich urzędów certyfikacji.

- **Aparat fotograficzny**: Umożliwia lub blokuje użycie aparatu fotograficznego urządzenia.
- **Synchronizacja plików w usłudze OneDrive**: Uniemożliwia synchronizowanie plików z urządzenia z usługą OneDrive.
- **Magazyn wymienny**: Określa, czy na urządzeniu można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD.
- **Geolokalizacja**: Określa, czy urządzenie może używać informacji z usług lokalizacyjnych.
- **Udostępnianie Internetu**: Zezwala na udostępnianie połączenia internetowego na urządzeniu.
- **Resetowanie telefonu**: Określa, czy użytkownik może przeprowadzić czyszczenie swojego urządzenia.
- **Połączenie USB (tylko dla urządzeń przenośnych)**: Określa, czy urządzenia mają dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.
- **Tryb przeciwkradzieżowy (tylko na urządzeniach przenośnych)**: Pozwala określić, czy jest włączony tryb antykradzieżowy systemu Windows.
- **Cortana**: Włącza lub wyłącza asystenta głosowego Cortana.
- **Nagrywanie głosu (tylko dla urządzeń przenośnych)**: Umożliwia lub blokuje użycie rejestratora głosu w urządzeniu.
- **Modyfikacja nazwy urządzenia**: Uniemożliwia użytkownikowi końcowemu zmianę nazwy urządzenia (tylko system Windows 10 Mobile)
- **Dodaj pakiety aprowizacji**: Blokuje agenta konfiguracji środowiska uruchomieniowego, który instaluje pakiety aprowizacji.
- **Usuń pakiety aprowizacji**: Blokuje agenta konfiguracji środowiska uruchomieniowego, który usuwa pakiety aprowizacji.
- **Odnajdywanie urządzeń**: Blokuje wykrywanie urządzenia przez inne urządzenia.
- **Przełącznik zadań (tylko urządzenia przenośne)**: Blokuje przełącznik zadań na urządzeniu.
- **Okno dialogowe błędu karty SIM (tylko urządzenia przenośne)**: W przypadku, gdy karta SIM nie zostanie wykryta, blokuje wyświetlanie komunikatu o błędzie na urządzeniu.
- **Obszar roboczy pisma odręcznego**: Blokuje dostęp użytkowników do obszaru roboczego pisma odręcznego. Pozycja **Nieskonfigurowane** włącza obszar roboczy pisma odręcznego, a użytkownik może używać go na ekranie blokady urządzenia.
- **Automatyczne ponowne wdrażanie**: Pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania.
- **Wymagaj od użytkowników nawiązania połączenia z siecią podczas konfigurowania urządzenia (tylko niejawny program testów systemu Windows)**: Wybierz pozycję **Wymagane**, aby wymagać, żeby urządzenia łączyły się z siecią przed wyjściem poza stronę Sieć podczas instalacji systemu Windows 10. Chociaż ta funkcja jest obecnie w wersji zapoznawczej, niejawny program testów systemu Windows (kompilacja 1809 lub nowsza) jest wymagany, aby użyć tego ustawienia.
- **Kończ procesy z Menedżera zadań**: To ustawienie określa, czy użytkownicy niebędący administratorami mogą używać Menedżera zadań do kończenia zadań. Pozycja **Blokuj** uniemożliwia użytkownikom standardowym (niebędącym administratorami) używanie Menedżera zadań do zakończenia procesu lub zadania na urządzeniu. **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom standardowym zakończenie procesu lub zadania za pomocą Menedżera zadań.

## <a name="kiosk-preview---obsolete"></a>Kiosk (wersja zapoznawcza) — przestarzałe

Te ustawienia są przeznaczone tylko do odczytu i nie można ich zmienić. Aby skonfigurować tryb kiosku, zobacz [Ustawienia kiosku w systemie Windows 10 lub nowszym](kiosk-settings.md).

Kiosk to urządzenie, na którym jest zwykle uruchamiana jedna aplikacja lub zestaw konkretnych aplikacji. Użytkownicy nie mogą uzyskać na urządzeniu dostępu do funkcjonalności ani funkcji.

- **Tryb kiosku**: Wskazuje typ trybu kiosku obsługiwanego przez zasady. Dostępne opcje:

  - **Nieskonfigurowane** (wartość domyślna): Te zasady nie umożliwiają korzystania z trybu kiosku na urządzeniu.
  - **Kiosk z pojedynczą aplikacją**: Profil umożliwia uruchamianie tylko jednej aplikacji na urządzeniu. Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
  - **Kiosk z wieloma aplikacjami**: Profil umożliwia uruchamianie wielu aplikacji na urządzeniu. Tylko dodane aplikacje są dostępne dla użytkownika. Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje, a pozostałe są ukryte.

#### <a name="single-app-kiosks"></a>Kioski z pojedynczą aplikacją

Podaj następujące ustawienia:

- **Konto użytkownika**: Wprowadź lokalne (na urządzeniu) konto użytkownika, konto domeny usługi AD lub konto usługi Azure AD skojarzone z aplikacją kiosku.
  - Konto lokalne: wprowadź w formacie `devicename\accountname`, `.\accountname` lub `accountname`
  - Konto domeny: wprowadź w formacie `domain\accountname`
  - Konto usługi Azure AD: wprowadź w formacie `AzureAD\emailaddress`. Pamiętaj, aby wprowadzić nazwę „AzureAD”, ponieważ jest to ustalona nazwa domeny. Następnie podaj adres e-mail usługi Azure AD. Na przykład wprowadź `AzureAD\user@contoso.onmicrosoft.com`.

    W przypadku kiosków w miejscach publicznych z włączonym automatycznym logowaniem należy użyć typu użytkownika z najniższymi uprawnieniami (na przykład lokalnego standardowego konta użytkownika). W przypadku używania konta usługi Azure AD w trybie kiosku pamiętaj, aby wprowadzić wartość `AzureAD\user@yourorganization.com`.

- **Identyfikator modelu użytkownika aplikacji (AUMID) aplikacji**: Wprowadź identyfikator AUMID aplikacji kiosku. Aby dowiedzieć się więcej, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

#### <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami

[Kioski z wieloma aplikacjami](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) korzystają z konfiguracji kiosku zawierającej listę dozwolonych aplikacji i inne ustawienia. 

Użyj przycisku **Dodaj**, aby utworzyć konfigurację kiosku (lub wybierz istniejącą konfigurację). Następnie podaj następujące ustawienia:

- **Nazwa konfiguracji kiosku**: Wprowadź przyjazną nazwę używaną do identyfikowania konfiguracji.

- **Aplikacje kiosku**: Wprowadź aplikacje dostępne w menu Start. Dodane aplikacje to jedyne aplikacje, które użytkownik może otwierać.

  - **Typ aplikacji**: Wybierz typ aplikacji kiosku:
    - **Aplikacja Win32**: Tradycyjna aplikacja klasyczna. Potrzebna jest w pełni kwalifikowana nazwa ścieżki pliku wykonywalnego określona względem urządzenia.
    - **Aplikacja platformy UWP**: Aplikacja platformy uniwersalnej systemu Windows. Potrzebny jest [identyfikator AUMID aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

  - **Identyfikator**: Wprowadź w pełni kwalifikowaną nazwę ścieżki pliku wykonywalnego (aplikacje Win32) lub [identyfikator AUMID aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplikacje platformy UWP).

- **Pasek zadań**: Wybierz wartość **Włącz**, aby wyświetlać pasek zadań, lub wartość **Nieskonfigurowany**, aby go ukryć na kiosku.

- **Układ menu Start**: Wprowadź plik XML, który opisuje sposób, w jaki aplikacje są wyświetlane w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) zawiera wskazówki i przykładowy kod XML.

  Artykuł [Create a Windows 10 kiosk that runs apps (Tworzenie kiosku z systemem Windows 10 obsługującego aplikacje)](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) zawiera więcej szczegółowych informacji na temat używania i tworzenia plików XML.

- **Przypisani użytkownicy**: Dodaj co najmniej jedno konta użytkownika, które może używać dodanych aplikacji. Po zalogowaniu przy użyciu konta będą dostępne tylko aplikacje określone w konfiguracji. Konto może być kontem lokalnym na urządzeniu lub kontem usługi Azure AD skojarzonym z aplikacją kiosku.

    W przypadku kiosków w miejscach publicznych z włączonym automatycznym logowaniem należy użyć typu użytkownika z najniższymi uprawnieniami (na przykład lokalnego standardowego konta użytkownika). Aby skonfigurować konto usługi Azure Active Directory (AD) pod kątem trybu kiosku, użyj formatu `domain\user@tenant.com`.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

- **Powiadomienia centrum akcji (tylko dla urządzeń przenośnych)**: Włącza powiadomienia z centrum akcji na ekranie blokady urządzenia (tylko system Windows 10 Mobile).
- **Adres URL obrazu ekranu blokady (tylko dla komputerów stacjonarnych)**: Wprowadź adres URL obrazu w formacie JPEG używany jako tapeta ekranu blokady systemu Windows. Użytkownicy nie mogą zmieniać tego ustawienia.
- **Konfigurowany przez użytkownika limit czasu ekranu (tylko urządzenia przenośne)**: Pozwala użytkownikom na konfigurowanie ilości czasu 
- **Cortana na zablokowanym ekranie (tylko komputery stacjonarne)**: Nie zezwala użytkownikowi na interakcję z funkcją Cortana, gdy jest wyświetlany ekran blokady (tylko system Windows 10 Desktop).
- **Wyskakujące powiadomienia na zablokowanym ekranie**: Blokuje wyświetlanie alertów na ekranie blokady.
- **Limit czasu ekranu (tylko urządzenia przenośne)**: Określa czas (w sekundach) wyświetlania ekranu blokady, po którym ekran zostanie wyłączony.

## <a name="messaging"></a>Obsługa wiadomości

- **Synchronizowanie wiadomości (tylko na urządzeniach przenośnych)**: Wyłącz funkcję Wiadomości na wszystkich urządzeniach oraz tworzenie kopii zapasowych wiadomości SMS i ich przywracanie.
- **MMS (tylko na urządzeniach przenośnych)**: Wyłącz funkcję wysyłania i odbierania wiadomości MMS na urządzeniu.
- **RCS (tylko na urządzeniach przenośnych)**: Wyłącz funkcję wysyłania i odbierania wiadomości Rich Communication Services na urządzeniu.

## <a name="microsoft-edge-browser"></a>Przeglądarka Microsoft Edge

### <a name="start-experience"></a>Środowisko rozpoczynania pracy

- **Uruchom przeglądarkę Microsoft Edge przy użyciu**: Wybierz strony otwierane po uruchomieniu przeglądarki Microsoft Edge. Dostępne opcje:
  - **Strony startowe**: Przeglądarka Microsoft Edge jest uruchamiana z domyślną stroną startową zdefiniowaną przez system operacyjny
  - **Strona nowej karty**: Przeglądarka Microsoft Edge ładuje adres zdefiniowany w obszarze **Adres URL nowej karty**
  - **Strona ostatniej sesji**: Przeglądarka Microsoft Edge ładuje stronę ostatniej sesji 
  - **Niestandardowa strona startowa**: Przeglądarka Microsoft Edge ładuje stronę startową zdefiniowaną przez administratora IT
- **Użytkownik może zmieniać strony startowe**: Ustawienie **Zezwalaj** umożliwia użytkownikom zmienianie stron startowych. Administratorzy mogą używać elementu `EdgeHomepageUrls` do wprowadzania stron startowych, które są widoczne domyślnie dla użytkowników po otwarciu przeglądarki Microsoft Edge. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom zmienianie stron startowych.
- **Adres URL nowej karty**: Wprowadź adres URL do otwarcia na stronie nowej karty. Na przykład wprowadź `https://www.bing.com`.
- **Otwieranie zawartości internetowej na stronie nowej karty**: Wybierz pozycję **Blokuj**, aby uniemożliwić przeglądarce Microsoft Edge otwieranie witryny internetowej na nowej karcie. Po zablokowaniu nowa karta jest otwierana jako pusta. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego na urządzeniu, dzięki czemu użytkownicy mogą wybierać zawartość do wyświetlenia.
- **Przycisk Strona główna**: Wybierz, co się stanie po wybraniu przycisku Strona główna. Dostępne opcje:
  - **Strony startowe**: Jest otwierana strona wybrana w ustawieniu **Uruchom przeglądarkę Microsoft Edge przy użyciu**
  - **Strona nowej karty**: Jest otwierana opcja wybrana dla ustawienia **Adres URL nowej karty**
  - **Niestandardowy adres URL przycisku Strona główna**: Jest otwierana opcja wybrana dla ustawienia **Adres URL przycisku Strona główna**
  - **Ukryj przycisk Strona główna**: Ukrywa przycisk Strona główna
- **Użytkownik może zmienić przycisk Strona główna**: Ustawienie **Zezwalaj** umożliwia użytkownikom zmienianie przycisku Strona główna. Zmiany wprowadzone przez użytkownika zastępują wszelkie ustawienia administratora, które dotyczą przycisku strony głównej. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego na urządzeniu, które może uniemożliwiać użytkownikom zmianę sposobu skonfigurowania przycisku Strona główna przez administratora.
- **Pokaż stronę pierwszego uruchomienia**: Pozycja **Blokuj** blokuje wyświetlanie strony wprowadzenia przy pierwszym uruchomieniu przeglądarki Microsoft Edge. Ta funkcja umożliwia przedsiębiorstwom, takim jak zarejestrowane w konfiguracjach zeroemisyjnych, na blokowanie tej strony. Pozycja **Nieskonfigurowane** powoduje wyświetlanie strony wprowadzenia.
  - **Adres URL pierwszego uruchomienia**: Wprowadź adres URL strony do wyświetlenia, gdy użytkownik po raz pierwszy uruchamia przeglądarkę Microsoft Edge (tylko system Windows 10 Mobile).
- **Wyskakujące okienka**: Wybierz pozycję **Blokuj**, aby uniemożliwić wyświetlanie wyskakujących okienek w przeglądarce. Dotyczy tylko systemu Windows 10 Desktop. Pozycja **Nieskonfigurowane** umożliwia wyświetlane wyskakujących okienek w przeglądarce internetowej.
- **Wysyłaj ruch intranetowy do programu Internet Explorer**: Pozycja **Zezwalaj** umożliwia użytkownikom otwieranie intranetowych witryn internetowych w programie Internet Explorer zamiast w przeglądarce Microsoft Edge (tylko system Windows 10 Desktop). Pozycja **Nieskonfigurowane** pozwala użytkownikom na używanie przeglądarki Microsoft Edge.
- **Lokalizacja listy witryn trybu przedsiębiorstwa**: Wprowadź adres URL obejmujący listę witryn internetowych, które można otwierać w trybie przedsiębiorstwa. Użytkownicy nie mogą zmieniać tej listy. Dotyczy tylko systemu Windows 10 Desktop.
- **Komunikat podczas otwierania witryn w programie Internet Explorer**: To ustawienie służy do konfigurowania przeglądarki Microsoft Edge w celu wyświetlania powiadomienia przed otwarciem witryny w programie Internet Explorer 11. Dostępne opcje:
  - **Nieskonfigurowane**: Jest stosowane domyślne zachowanie systemu operacyjnego, co może sprawiać, że komunikat nie będzie wyświetlany.
  - **Pokaż komunikat bez opcji otwierania witryn w programie Microsoft Edge**: Pokaż komunikat podczas otwierania witryn w programie IE. Witryny są otwierane w programie IE. Nie ma opcji otwierania witryn w przeglądarce Microsoft Edge.
  - **Pokaż komunikat podczas otwierania witryn w programie Microsoft Edge**: Pokaż komunikat podczas otwierania witryn w programie IE. Komunikat zawiera link **Kontynuuj pracę w przeglądarce Microsoft Edge**, dzięki któremu użytkownicy mogą wybrać przeglądarkę Microsoft Edge zamiast programu Internet Explorer.

  > [!IMPORTANT]
  > To ustawienie wymaga włączenia ustawienia **Konfigurowanie listy witryn trybu przedsiębiorstwa**, ustawienie **Wysyłanie wszystkich witryn intranetowych do programu Internet Explorer 11** lub obydwa ustawienia.

- **Lista zgodności firmy Microsoft**: Pozycja **Blokuj** uniemożliwia użycie listy zgodności firmy Microsoft w przeglądarce Microsoft Edge. Ta lista firmy Microsoft pomaga przeglądarce Microsoft Edge prawidłowo wyświetlać witryny ze znanymi problemami dotyczącymi zgodności. Pozycja **Nieskonfigurowane** zezwala na korzystanie z listy zgodności firmy Microsoft.
- **Wstępne ładowanie stron startowych i strony nowej karty**: Wybierz pozycję **Blokuj**, aby uniemożliwić wstępne ładowanie stron startowych i strony nowej karty w przeglądarce Microsoft Edge. Wstępne ładowanie minimalizuje czas uruchamiania przeglądarce Microsoft Edge i powoduje załadowanie nowej karty. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować wstępne ładowanie tych stron.
- **Wstępne uruchamianie stron startowych i strony nowej karty**: Wybierz pozycję **Blokuj**, aby uniemożliwić wstępne ładowanie stron startowych i strony nowej karty w przeglądarce Microsoft Edge. Wstępne uruchomienie zwiększa wydajność przeglądarki Microsoft Edge i minimalizuje czas wymagany do uruchomienia tej przeglądarki. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować wstępne uruchamianie tych stron.

### <a name="favorites-and-search"></a>Ulubione i wyszukiwanie

- **Pasek Ulubione**: Wybierz, co się stanie z paskiem ulubionych na dowolnej stronie przeglądarki Microsoft Edge. Dostępne opcje:
  - **Nieskonfigurowane**: Używa domyślnego zachowania systemu operacyjnego, które może powodować ukrywania paska ulubionych na wszystkich stronach. Użytkownik może zmieniać to ustawienie.
  - **Ukryj**: Ukrywa pasek ulubionych na wszystkich stronach. Użytkownik nie może zmieniać tego ustawienia.
  - **Pokaż**: Pokazuje pasek ulubionych na wszystkich stronach. Użytkownik nie może zmieniać tego ustawienia.
- **Lista Ulubione**: Dodaj listę adresów URL do pliku ulubionych. Na przykład dodaj `http://contoso.com/favorites.html`.
- **Ograniczanie zmian ulubionych**: Wybierz ustawienie **Blokuj**, aby uniemożliwić użytkownikom dodawanie, importowanie, sortowanie lub edytowanie listy Ulubione. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może pozwolić użytkownikom na zmienianie listy.
- **Synchronizuj ulubione między przeglądarkami firmy Microsoft (tylko wersja klasyczna)**: Pozycja **Wymagaj** wymusza synchronizowanie ulubionych między przeglądarkami Internet Explorer i Microsoft Edge w systemie Windows. Operacje dodawania, usuwania, modyfikacji i zmian kolejności w obszarze ulubionych będą udostępniane między przeglądarkami.  Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może dać użytkownikom opcję synchronizowania między przeglądarkami.
- **Domyślna wyszukiwarka**: Wybierz domyślną wyszukiwarkę na urządzeniu. Użytkownicy końcowi mogą w dowolnym momencie zmienić tę wartość. Dostępne opcje:
  - Domyślny
  - Bing
  - Google
  - Yahoo
  - Wartość niestandardowa
- **Sugestie wyszukiwania**: Pozycja **Nieskonfigurowane** umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz na pasku adresu. Pozycja **Blokuj** uniemożliwia użycie tej funkcji.

### <a name="privacy-and-security"></a>Prywatność i zabezpieczenia

- **Przeglądanie InPrivate**: Pozycja **Blokuj** uniemożliwia otwieranie sesji przeglądania InPrivate przez użytkowników końcowych. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Zapisywanie historii przeglądania**: Pozycja **Blokuj** uniemożliwia zapisywanie historii przeglądania w programie Microsoft Edge. Pozycja **Nieskonfigurowane** umożliwia zapisywanie historii przeglądania.
- **Wyczyść dane przeglądania przy zamykaniu (tylko wersja Desktop)**: Pozycja **Wymagaj** włącza czyszczenie historii i danych przeglądania przy zamykaniu przeglądarki Microsoft Edge. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może powodować buforowanie danych przeglądania.
- **Synchronizuj ustawienia przeglądarki między urządzeniami użytkownika**: Wybierz, jak chcesz synchronizować ustawienia przeglądarki między urządzeniami. Dostępne opcje:
  - **Zezwalaj**: Zezwala na synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika.
  - **Blokuj i włącz nadpisywanie użytkownika**: Blokuje synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika. Użytkownicy mogą przesłaniać to ustawienie.
  - **Blokuj**: Blokuj synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika. Użytkownicy nie mogą przesłaniać tego ustawienia.
- **Menedżer haseł**: Pozycja **Blokuj** wyłącza funkcję menedżera haseł w przeglądarce Microsoft Edge. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Pliki cookie**: Wybierz sposób obsługi plików cookie w przeglądarce internetowej. Dostępne opcje:
  - **Zezwalaj**: Pliki cookie są przechowywane na urządzeniu.
  - **Blokuj wszystkie pliki cookie**: Pliki cookie nie są przechowywane na urządzeniu.
  - **Blokuj tylko pliki cookie innych firm**: Pliki cookie innych firm lub partnerów nie są przechowywane na urządzeniu.
- **Autowypełnianie**: Pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce (tylko system Windows 10 Desktop).
- **Wysyłaj nagłówki Nie śledź**: Pozycja **Nieskonfigurowane** wymaga, aby urządzenia wysyłały nagłówki Nie śledź do witryn internetowych żądających informacji dotyczących śledzenia (zalecane). Wybierz pozycję **Blokuj**, aby uniemożliwić urządzeniu wysyłanie tych nagłówków, co pozwoli witrynom internetowym na śledzenie użytkownika.
- **Adres IP lokalnego hosta dla protokołu WebRtc**: Pozycja **Blokuj** uniemożliwia wyświetlanie adresu IP lokalnego hosta użytkownika podczas nawiązywania połączeń telefonicznych przy użyciu protokołu internetowego RTC. Pozycja **Nieskonfigurowane** umożliwia wyświetlanie adres IP lokalnego hosta użytkowników podczas nawiązywania połączeń telefonicznych przy użyciu tego protokołu.
- **Zbieranie danych dynamicznych kafelków**: Wybierz pozycję **Blokuj**, aby uniemożliwić systemowi Windows zbieranie informacji z dynamicznych kafelków podczas przypinania witryny z przeglądarki Microsoft Edge do menu Start. Pozycja **Nieskonfigurowane** umożliwia zbieranie tych informacji.
- **Użytkownik może nadpisywać błędy certyfikatów**: Pozycja **Blokuj** uniemożliwia użytkownikom uzyskiwanie dostępu do witryn internetowych z błędami protokołu SSL lub TLS. Pozycja **Nieskonfigurowane** umożliwia użytkownikom uzyskiwanie dostępu do tych witryn.

### <a name="additional"></a>Dodatkowe

- **Przeglądarka Microsoft Edge (tylko urządzenia przenośne)**: Wybierz pozycję **Blokuj**, aby uniemożliwić używanie programu Microsoft Edge na urządzeniu. Jeśli zablokujesz przeglądarkę Microsoft Edge, poszczególne ustawienia będą dotyczyć tylko pulpitu. Pozycja **Nieskonfigurowane** umożliwia korzystanie z przeglądarki internetowej Microsoft Edge na urządzeniu.
- **Rozwijanie paska adresu (tylko wersja klasyczna)**: Pozycja **Blokuj** uniemożliwia przeglądarce Microsoft Edge wyświetlanie sugestii na liście rozwijanej podczas wpisywania tekstu. Ta opcja pozwala zmniejszyć przepustowość sieci w ramach komunikacji między przeglądarką Microsoft Edge a usługami firmy Microsoft. Pozycja **Nieskonfigurowane** umożliwia wyświetlanie listy sugestii w przeglądarce Microsoft Edge.
- **Pełny ekran**: Wybierz pozycję **Blokuj**, aby uniemożliwić przeglądarce Microsoft Edge wyświetlanie tylko zawartości internetowej i ukrywanie przeglądarki Microsoft Edge (tryb pełnoekranowy). Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które pozwala przeglądarce Microsoft Edge na pracę w trybie pełnoekranowym.
- **Flagi informacyjne**: Pozycja **Blokuj** uniemożliwia użytkownikom uzyskiwanie dostępu do strony `about:flags` przeglądarki Microsoft Edge, która zawiera ustawienia deweloperskie i eksperymentalne. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może pozwolić uzyskiwanie dostępu do strony `about:flags`.
- **Narzędzia programistyczne**: Pozycja **Blokuj** uniemożliwia użytkownikowi końcowemu otwieranie narzędzi programistycznych przeglądarki Microsoft Edge. Pozycja **Nieskonfigurowane** umożliwia użytkownikom otwieranie narzędzi programistycznych.
- **Rozszerzenia**: Pozycja **Nieskonfigurowane** umożliwia użytkownikowi końcowemu instalowanie rozszerzeń przeglądarki Microsoft Edge na urządzeniu. Pozycja **Blokuj** uniemożliwia instalację.
- **Ładowanie bezpośrednie rozszerzeń dla deweloperów**: Pozycja **Blokuj** uniemożliwia przeglądarce Microsoft Edge ładowanie bezpośrednie, które polega na instalowaniu i uruchamianiu niezweryfikowanych rozszerzeń przy użyciu funkcji **ładowania rozszerzeń**. Pozycja **Nieskonfigurowane** używa domyślnego zachowania systemu operacyjnego, które może pozwolić na ładowanie bezpośrednie.
- **Wymagane rozszerzenia**: Wybierz rozszerzenia, których użytkownicy końcowi nie mogą wyłączać w przeglądarce Microsoft Edge. Wprowadź nazwy rodzin pakietów, a następnie wybierz pozycję **Dodaj**. Wskazówki można znaleźć w temacie [Find a package family name (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) (Znajdowanie nazwy rodziny pakietów (PFN)).

  Możesz również **zaimportować** plik CSV, który zawiera nazwy rodzin pakietów.

- **JavaScript**: Wybierz pozycję **Blokuj**, aby uniemożliwić uruchamianie skryptów języka Java w przeglądarce na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia uruchamianie skryptów, takich jak JavaScript, w przeglądarce Microsoft Edge.

## <a name="network-proxy"></a>Serwer proxy sieci

- **Automatycznie wykrywaj ustawienia proxy**: Po włączeniu tego ustawienia urządzenie spróbuje znaleźć ścieżkę do skryptu PAC.
- **Użyj skryptu serwera proxy**: Wybierz tę opcję, jeśli chcesz określić ścieżkę do skryptu PAC, aby skonfigurować serwer proxy.
  - **Adres URL skryptu konfiguracji**: Wprowadź adres URL skryptu PAC, którego chcesz użyć do skonfigurowania serwera proxy.
- **Użyj ręcznego serwera proxy**: Wybierz tę opcję, jeśli chcesz ręcznie wprowadzać informacje o serwerze proxy.
  - **Adres**: Wprowadź nazwę lub adres IP serwera proxy.
  - **Numer portu**: Wprowadź numer portu serwera proxy.
  - **Wyjątki serwera proxy**: Wprowadź wszystkie adresy URL, w przypadku których korzystanie z serwera proxy będzie zabronione. Rozdziel kolejne elementy średnikiem.
  - **Pomiń serwer proxy dla adresów lokalnych**: Włącz tę opcję, jeśli nie chcesz używać serwera proxy dla adresów lokalnych w sieci intranet.

## <a name="password"></a>Hasło

- **Hasło**: Wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
  - **Wymagany typ hasła**: Określa, czy hasło musi być wyłącznie numeryczne lub alfanumeryczne.
  - **Minimalna długość hasła**: Dotyczy tylko systemu Windows 10 Mobile.
  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: W przypadku urządzeń z systemem Windows 10: jeśli na urządzeniu jest włączona funkcja BitLocker, zostanie ono przełączone do trybu odzyskiwania funkcji BitLocker po określonej liczbie nieudanych prób logowania. Jeśli na urządzeniu nie została włączona funkcja BitLocker, to ustawienie nie będzie miało zastosowania. Na urządzeniach z systemem Windows 10 Mobile: po określonej liczbie niepowodzeń logowania urządzenie zostanie wyczyszczone.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: Określa czas bezczynności urządzenia, po upływie którego ekran jest blokowany.
  - **Wygaśnięcie hasła (dni)**: Określa czas, po jakim hasło urządzenia musi zostać zmienione.
  - **Zapobiegaj ponownemu używaniu poprzednich haseł**: Określa liczbę poprzednich haseł, które są zapamiętywane przez urządzenie.
  - **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności (tylko urządzenia przenośne)**: Określa, czy użytkownik musi wprowadzić hasło, aby odblokować urządzenie (tylko system Windows 10 Mobile).
  - **Proste hasła**: Umożliwia korzystanie z prostych haseł, takich jak 1111 lub 1234. To ustawienie zezwala również na używanie haseł obrazkowych systemu Windows lub blokuje tę możliwość.
- **Szyfrowanie**: Włącza szyfrowanie na urządzeniach docelowych.

## <a name="per-app-privacy-exceptions"></a>Wyjątki prywatności dla aplikacji

Możesz dodawać aplikacje, dla których chcesz określić inne zachowanie dotyczące prywatności niż zachowanie zdefiniowane w domyślnym ustawieniu prywatności.

- **Nazwa pakietu**: nazwa rodziny pakietów aplikacji.
- **Nazwa aplikacji**: nazwa aplikacji.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie**: Określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle**: Określ, czy ta aplikacja może działać w tle.
- **Kalendarz**: Określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń**: Określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny**: Określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty**: Określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail**: Określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja**: Określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości**: Określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości SMS albo MMS.
- **Mikrofon**: Określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch**: Określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia**: Określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon**: Określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe**: Niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania**: Określ, czy ta aplikacja może uzyskiwać dostęp do zadań.
- **Zaufane urządzenia**: Określ, czy ta aplikacja może używać zaufanych urządzeń, czyli sprzętu, z którym już nawiązano połączenie, lub dołączonego do urządzenia. Jako zaufanych urządzeń można na przykład użyć telewizorów, projektorów itd.
- **Opinie i diagnostyka**: Określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami**: Wybierz, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym urządzeniem.

## <a name="personalization"></a>Personalizacja

- **Adres URL obrazu tła pulpitu (tylko dla komputerów stacjonarnych)**: Wprowadź adres URL obrazu w formacie JPEG, który będzie używany jako tapeta pulpitu systemu Windows. Użytkownicy nie mogą zmieniać obrazu.

## <a name="printer"></a>Drukarka

- **Drukarki**: Lista dodanych drukarek lokalnych.
- **Drukarka domyślna**: Ustaw drukarkę domyślną.
- **Dostęp użytkownika do dodawania nowych drukarek**: Zezwalaj na lub zablokuj korzystanie z drukarek lokalnych.

## <a name="privacy"></a>Ochrona prywatności

- **Personalizacja danych wejściowych**: Nie zezwalaj na korzystanie z chmurowych usług przetwarzania mowy razem z aplikacją Cortana, funkcją dyktowania czy aplikacjami ze sklepu Microsoft Store. Jeśli zezwolisz na te usługi, firma Microsoft może zbierać dane dotyczące głosu w celu usprawnienia świadczonej usługi.
- **Automatyczne akceptowanie w przypadku monitów o wyrażenie zgody przez użytkownika dotyczących parowania i prywatności**: Zezwalaj systemowi Windows na automatyczne akceptowanie komunikatów o wyrażenie zgody dotyczących parowania i prywatności podczas uruchamiania aplikacji.
- **Publikuj działania użytkownika**: Pozycja **Blokuj** uniemożliwia udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań.
- **Tylko działania lokalne**: Pozycja **Blokuj** uniemożliwia udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań jedynie na podstawie działań lokalnych.

Można skonfigurować informacje, do których mogą uzyskiwać dostęp wszystkie aplikacje na urządzeniu. Można także zdefiniować wyjątki dla poszczególnych aplikacji, korzystając z opcji **Wyjątki prywatności dla aplikacji**.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie**: Określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle**: Określ, czy ta aplikacja może działać w tle.
- **Kalendarz**: Określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń**: Określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny**: Określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty**: Określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail**: Określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja**: Określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości**: Określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości SMS albo MMS.
- **Mikrofon**: Określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch**: Określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia**: Określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon**: Określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe**: Niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania**: Określ, czy ta aplikacja może uzyskiwać dostęp do zadań.
- **Zaufane urządzenia**: Określ, czy ta aplikacja może używać zaufanych urządzeń. Zaufane urządzenia to sprzęt, z którym już nawiązano połączenie, lub dołączony do urządzenia. Jako zaufanych urządzeń można na przykład użyć telewizorów, projektorów itd.
- **Opinie i diagnostyka**: Określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami** — określ, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym komputerem, tabletem lub telefonem.

## <a name="projection"></a>Projekcja

- **Dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych**: Blokuje dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych.
- **Projekcja na tym komputerze**: Uniemożliwia innym urządzeniom odnajdywanie tego komputera dla celów projekcji.
- **Wymagaj numeru PIN do parowania**: Wybór powoduje, że podczas nawiązywania połączenia z urządzeniem do projekcji wymagane jest podanie numeru PIN.

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia**: Wybierz poziom przesyłanych danych diagnostycznych. Dostępne opcje:
  - Zabezpieczenia
  - Podstawowe
  - Zaawansowane
  - Pełna
- **Wysyłaj dane przeglądania programu Microsoft Edge do usługi Microsoft 365 Analytics**: Użyj tej funkcji, aby nadać ustawieniom **Udostępnij dane użycia** wartość **Rozszerzone** lub **Pełne**. Ta funkcja kontroluje dane, które przeglądarka Microsoft Edge wysyła do usługi Microsoft 365 Analytics dla urządzeń firmowych przy użyciu skonfigurowanego identyfikatora komercyjnego. Dostępne opcje:
  - **Nieskonfigurowane**: Używa domyślnego zachowania systemu operacyjnego, które może powodować, że żadne dane historii przeglądania nie będą wysyłane
  - **Wysyłaj tylko dane intranetowe**: Umożliwia administratorowi wysyłanie historii danych intranetowych
  - **Wysyłaj tylko dane internetowe**: Umożliwia administratorowi wysyłanie historii danych internetowych
  - **Wysyłaj dane intranetowe i internetowe**: Umożliwia administratorowi wysyłanie historii danych intranetowych i internetowych
- **Serwer proxy telemetrii**: Wprowadź w pełni kwalifikowaną nazwę domeny (FQDN) lub adres IP serwera proxy do przekazywania żądań środowisk i telemetrii połączonego użytkownika przy użyciu połączenia SSL (Secure Sockets Layer). Format dla tego ustawienia to: *serwer*:*port*. Jeśli nazwany serwer proxy ulegnie awarii lub jeśli serwer proxy nie będzie określony w momencie włączenia tych zasad, dane środowisk i telemetrii połączonego użytkownika nie zostaną przesłane i pozostaną na urządzeniu lokalnym.

  Przykładowe formaty:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Wyszukaj

- **Bezpieczne wyszukiwanie (tylko urządzenia przenośne)**: Pozwala określić sposób, w jaki Cortana filtruje treści dla dorosłych w wynikach wyszukiwania. Można wybrać opcję **Ścisłe** lub **Umiarkowane** albo zezwolić użytkownikom końcowym na wybór własnych ustawień.
- **Wyświetl wyniki internetowe w wyszukiwaniu**: Umożliwia blokowanie lub akceptowanie wyświetlania wyników internetowych w wynikach wyszukiwania na urządzeniu.

## <a name="start"></a>Początek

- **Układ menu Start**: W celu dostosowania menu Start na urządzeniach stacjonarnych można przekazać plik XML zawierający dostosowania, w tym kolejność wyświetlania aplikacji i nie tylko. Użytkownicy nie mogą zmieniać wprowadzonego w ten sposób układu menu Start.
- **Przypinaj witryny internetowe do kafelków w menu Start**: Zaimportuj obrazy z przeglądarki Microsoft Edge, które będą wyświetlane jako linki w menu Start systemu Windows dla urządzeń stacjonarnych.
- **Odpinanie aplikacji od paska zadań**: Wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom odpinanie aplikacji od menu Start.
- **Szybkie przełączanie użytkowników**: Wybierz pozycję **Blokuj**, aby uniemożliwić przełączanie się między zalogowanymi jednocześnie użytkownikami bez wylogowywania się.
- **Najczęściej używane aplikacje**: Wybierz pozycję **Blokuj**, aby ukrywać najczęściej używane aplikacje w menu Start. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia.
- **Ostatnio dodane aplikacje**: Wybierz pozycję **Blokuj**, aby ukrywać ostatnio dodane aplikacje w menu Start. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia.
- **Tryb ekranu startowego**: Określ sposób wyświetlania ekranu startowego. Wybierz opcję wyświetlania **Pełny ekran** lub **Niepełny ekran**.
- **Ostatnio otwierane elementy list szybkiego dostępu**: Wybierz pozycję **Blokuj**, aby ukrywać listy szybkiego dostępu do ostatnich elementów w menu Start i na pasku zadań. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia.
- **Lista aplikacji**: Wybierz sposób wyświetlania aplikacji Ustawienia. Dostępne opcje: 
  - Zwiń
  - Zwiń i wyłącz aplikację Ustawienia 
  - Usuwa i wyłącza aplikację Ustawienia
- **Przycisk zasilania**: Pozycja **Blokuj** powoduje ukrycie przycisku zasilania w menu Start.
- **Kafelek użytkownika**: Pozycja **Blokuj** powoduje ukrycie kafelka użytkownika w menu Start.
  - **Blokada**: Pozycja **Blokuj** powoduje ukrycie opcji `Lock` na kafelku użytkownika w menu Start.
  - **Wyloguj się**: Pozycja **Blokuj** powoduje ukrycie opcji `Sign out` na kafelku użytkownika w menu Start.
- **Zamknij**: Pozycja **Blokuj** powoduje ukrycie opcji `Update and shut down` i `Shut down` na przycisku zasilania w menu Start.
- **Uśpienie**: Pozycja **Blokuj** powoduje ukrycie opcji `Sleep` na przycisku zasilania w menu Start.
- **Hibernacja**: Pozycja **Blokuj** powoduje ukrycie opcji `Hibernate` na przycisku zasilania w menu Start.
- **Przełącz konto**: Pozycja **Blokuj** powoduje ukrycie opcji `Switch account` na kafelku użytkownika w menu Start.
- **Opcje ponownego uruchamiania**:  Pozycja **Blokuj** powoduje ukrycie opcji `Update and restart` i `Restart` na przycisku zasilania w menu Start.
- **Folder Dokumenty w menu Start**: Pozwala ukryć lub pokazać folder Dokumenty w menu Start systemu Windows.
- **Folder Pliki do pobrania w menu Start**: Pozwala ukryć lub pokazać folder pobranych plików w menu Start systemu Windows.
- **Folder Eksplorator plików w menu Start**: Pozwala ukryć lub pokazać aplikację Eksplorator plików w menu Start systemu Windows.
- **Folder Grupa domowa w menu Start**: Pozwala ukryć lub pokazać folder Grupa domowa w menu Start systemu Windows.
- **Folder Muzyka w menu Start**: Pozwala ukryć lub pokazać folder Muzyka w menu Start systemu Windows.
- **Folder Sieć w menu Start**: Pozwala ukryć lub pokazać folder Sieć w menu Start systemu Windows.
- **Folder Osobiste w menu Start**: Pozwala ukryć lub pokazać folder Osobiste w menu Start systemu Windows.
- **Folder Obrazy w menu Start**: Pozwala ukryć lub pokazać folder obrazów w menu Start systemu Windows.
- **Folder Ustawienia w menu Start**: Pozwala ukryć lub pokazać aplikację Ustawienia w menu Start systemu Windows.
- **Folder Wideo w menu Start**: Pozwala ukryć lub pokazać folder Wideo w menu Start systemu Windows.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **SmartScreen dla Microsoft Edge**: Włącz filtr SmartScreen dla przeglądarki Microsoft Edge używany podczas uzyskiwania dostępu do witryn i pobierania plików.
- **Dostęp do złośliwych witryn**: Zablokuj użytkownikom możliwość ignorowania ostrzeżeń filtru Windows Defender SmartScreen oraz przechodzenia do witryny.
- **Pobieranie niezweryfikowanych plików**: Zablokuj użytkownikom możliwość ignorowania ostrzeżeń filtru Windows Defender SmartScreen oraz pobierania niezweryfikowanych plików.

## <a name="windows-spotlight"></a>W centrum uwagi Windows

- **W centrum uwagi Windows**: To ustawienie umożliwia zablokowanie wszystkich funkcji W centrum uwagi Windows na urządzeniach z systemem Windows 10. Jeśli to ustawienie zostanie wyłączone, następujące ustawienia nie będą dostępne:
  - **Funkcja W centrum uwagi Windows na ekranie blokady**: Wyłącza wyświetlanie informacji funkcji W centrum uwagi Windows na ekranie blokady urządzenia.
  - **Sugestie innych firm w funkcji W centrum uwagi Windows**: Wyłącza sugerowanie zawartości niepochodzącej z firmy Microsoft przez funkcję W centrum uwagi Windows.
  - **Funkcje dla konsumentów**: Umożliwia blokowanie funkcji dla konsumentów, takich jak sugestie w menu Start, powiadomienia dotyczące członkostwa itp.
  - **Porady dotyczące systemu Windows**: Umożliwia zablokowanie wyskakujących okienek z poradami w systemie Windows.
  - **Funkcja W centrum uwagi Windows w Centrum akcji**: Uniemożliwia wyświetlanie sugestii funkcji W centrum uwagi Windows, na przykład zawartości dotyczących nowych aplikacji lub zabezpieczeń, w Centrum akcji systemu Windows.
  - **Personalizacja funkcji W centrum uwagi Windows**: Wyłącza personalizowanie opartych na użyciu urządzenia wyników przez funkcję W centrum uwagi Windows.
  - **Środowisko powitalne Windows**: Wyłącza wyświetlanie środowiska powitalnego systemu Windows, w którym są widoczne informacje o nowych lub zaktualizowanych funkcjach.

## <a name="windows-defender-antivirus"></a>Program antywirusowy Windows Defender

- **Monitorowanie w czasie rzeczywistym**: Włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.
- **Monitorowanie zachowania**: Umożliwia usłudze Defender sprawdzanie określonych wzorców podejrzanej aktywności na urządzeniach.
- **Network Inspection System (NIS)**: Pomaga w ochronie urządzeń przed sieciowymi atakami wykorzystującymi luki w zabezpieczeniach. System NIS korzysta z sygnatur znanych luk w zabezpieczeniach z centrum programu Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch.
- **Skanuj wszystkie pobierania**: Określa, czy usługa Defender skanuje wszystkie pliki pobierane z Internetu.
- **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft**: Umożliwia usłudze Defender skanowanie skryptów używanych przez program Internet Explorer.
- **Dostęp użytkownika końcowego do narzędzia Defender**: Określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych. Zmiany tego ustawienia zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika.
- **Interwał aktualizacji sygnatur (w godzinach)**: Określa interwał sprawdzania dostępności nowych plików sygnatur przez usługę Defender.
- **Monitoruj działania plików i programów**: Zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach.
- **Dni przed usunięciem złośliwego oprogramowania poddanego kwarantannie**: Umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane.
- **Limit wykorzystania procesora CPU podczas skanowania**: Pozwala ograniczyć moc procesora CPU, jakiej mogą używać procesy skanowania (od **1** do **100**).
- **Skanuj pliki archiwum**: Zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.
- **Skanuj przychodzące wiadomości e-mail**: Zezwala usłudze Defender na skanowanie wiadomości e-mail podczas ich dostarczania do urządzenia.
- **Skanuj dyski wymienne podczas pełnego skanowania**: Umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.
- **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania**: Umożliwia usłudze Defender skanowanie plików na zamapowanym dysku sieciowym.
  Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
- **Skanuj pliki otwierane z folderów sieciowych**: Umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach dostępnych za pośrednictwem ścieżki UNC). Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
- **Ochrona w chmurze**: Zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.
- **Monituj użytkowników przed przesłaniem próbki**: Określa, czy do firmy Microsoft są automatycznie wysyłane potencjalnie złośliwe pliki, które mogą wymagać dalszej analizy.
- **Godzina przeprowadzania codziennego szybkiego skanowania**: Umożliwia zaplanowanie szybkiego skanowania, które będzie odbywać się codziennie o wybranej porze.
- **Typ skanowania systemu do wykonania**: Wprowadź poziom skanowania uruchamianego w przypadku planowania skanowania systemu.
- **Wykrywaj potencjalnie niepożądane aplikacje**: Pozwala wybrać poziom ochrony w przypadku wykrycia potencjalnie niechcianych aplikacji przez system Windows:
  - **Zablokuj**
  - **Inspekcja** Aby uzyskać więcej informacji dotyczących potencjalnie niepożądanych aplikacji, zobacz temat [Detect and block potentially unwanted applications](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus) (Wykrywanie i blokowanie potencjalnie niepożądanych aplikacji).
- **Akcje do podjęcia wobec wykrytych zagrożeń związanych ze złośliwym oprogramowaniem**: Użyj tej opcji w celu wskazania akcji, które ma podejmować usługa Defender po wykryciu zagrożenia określonego poziomu (niski, umiarkowany, wysoki i poważny). Dostępne opcje:
  - **Wyczyść**
  - **Kwarantanna**
  - **Usuń**
  - **Zezwalaj**
  - **Zdefiniowane przez użytkownika**
  - **Zablokuj**

### <a name="windows-defender-antivirus-exclusions"></a>Wyjątki programu antywirusowego Windows Defender

- **Pliki i foldery do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: Dodaje do listy wykluczeń jeden lub więcej plików i folderów, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.
- **Rozszerzenia plików do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: Dodaj do listy wykluczeń jedno lub więcej rozszerzeń plików, na przykład **jpg** lub **txt**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym lub skanowania planowanego.
- **Procesy do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: Dodaj jeden lub więcej procesów typu **exe**, **com** lub **scr** do listy wykluczeń. Te procesy nie są uwzględniane podczas skanowania w czasie rzeczywistym ani podczas zaplanowanego skanowania.

## <a name="next-steps"></a>Następne kroki

Dodatkowe szczegóły techniczne poszczególnych ustawień oraz obsługiwanych wersji systemu Windows można znaleźć w [dokumentacji dotyczącej dostawcy usługi konfiguracji dla zasad systemu Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
