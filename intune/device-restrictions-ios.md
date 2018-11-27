---
title: Ustawienia ograniczeń urządzenia z systemem iOS w usłudze Microsoft Intune
titleSuffix: ''
description: Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8f9e9533793a8792e9ad354392b9d8e911cd07f4
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188708"
---
# <a name="microsoft-intune-ios-device-restriction-settings"></a>Ustawienia ograniczeń urządzenia z systemem iOS w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia ograniczeń urządzeń, które można skonfigurować dla urządzeń z systemem iOS.

## <a name="general"></a>Ogólne

-   **Udostępnij dane użycia** — 	zezwala lub blokuje możliwość przesyłania danych diagnostycznych i danych telemetrycznych dotyczących użycia z urządzenia do firmy Apple.
-   **Przesyłanie danych diagnostycznych** — umożliwia lub blokuje przesyłanie danych diagnostycznych z urządzenia do firmy Apple.
-   **Przechwytywanie ekranu** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
    - **Zdalny podgląd ekranu za pomocą aplikacji Classroom (tylko nadzorowany)** — blokuje lub zezwala na podgląd ekranu na urządzeniach z systemem iOS za pomocą aplikacji Apple Classroom.
    - **Obserwacja ekranu bez monitowania za pomocą aplikacji Classroom (tylko nadzorowany)** — jeśli jest dozwolona, nauczyciele mogą dyskretnie obserwować ekrany urządzeń z systemem iOS przy użyciu aplikacji Classroom bez wiedzy studentów.
-   **Niezaufane certyfikaty protokołu TLS** — zezwala na niezaufane certyfikaty protokołu Transport Layer Security na urządzeniu.
-   **Zaufanie do aplikacji dla przedsiębiorstw** — umożliwia użytkownikowi wybranie zaufania do aplikacji, które nie zostały pobrane ze sklepu z aplikacjami.
- **Modyfikacja konta (tylko nadzorowany)** — w przypadku zablokowania uniemożliwia modyfikowanie przez użytkownika ustawień specyficznych dla urządzenia z poziomu ustawień aplikacji dla systemu iOS, takich jak tworzenie nowych kont urządzenia i zmiana nazwy użytkownika lub hasła.
Dotyczy to również ustawień dostępnych z poziomu ustawień takich aplikacji dla systemu iOS, jak Poczta, Kontakty, Kalendarz, Facebook i Twitter. Nie dotyczy to aplikacji z ustawieniami konta, których nie można skonfigurować z poziomu ustawień aplikacji dla systemu iOS, na przykład aplikacji Microsoft Outlook.
- **Włączenie ograniczeń w ustawieniach urządzenia (tylko nadzorowany)** — umożliwia użytkownikowi konfigurowanie ograniczeń dotyczących urządzenia (kontroli rodzicielskiej) na urządzeniu.
- **Użyj funkcji wymazania całej zawartości i wszystkich ustawień z urządzenia (tylko nadzorowany)** — umożliwia użytkownikowi korzystanie z opcji wymazywania całej zawartości i wszystkich ustawień z urządzenia.
- **Modyfikacja nazwy urządzenia (tylko nadzorowany)** — umożliwia użytkownikowi zmianę nazwy urządzenia.
- **Modyfikacja ustawień powiadamiania (tylko nadzorowany)** — umożliwia użytkownikowi zmianę ustawień powiadamiania na urządzeniu.
- **Modyfikacja ustawień zaufania dla aplikacji firmy (tylko nadzorowany)** — umożliwia użytkownikowi wybranie zaufania do aplikacji, które nie zostały pobrane ze sklepu z aplikacjami.
- **Zmiany profilu konfiguracji (tylko nadzorowany)** — umożliwia użytkownikowi instalowanie profilów konfiguracji.
- **Blokada aktywacji (tylko nadzorowany)** — umożliwia blokadę aktywacji na nadzorowanych urządzeniach z systemem iOS.

## <a name="configurations-requiring-supervision"></a>Konfiguracje wymagające nadzoru

Tryb nadzorowany systemu iOS można włączyć tylko podczas początkowego konfigurowania urządzenia za pośrednictwem programu Device Enrollment Program firmy Apple lub programu Apple Configurator. Po włączeniu trybu nadzorowanego na urządzeniu można skonfigurować następujące funkcje za pomocą usługi Intune:

- Blokada aplikacji (tryb jednej aplikacji) 
- Globalny serwer proxy HTTP 
- Obejście blokady aktywacji 
- Autonomiczny tryb jednej aplikacji 
- Filtr zawartości internetowej 
- Ustawianie tła i ekranu blokady 
- Dyskretne wypychanie aplikacji 
- Zawsze włączona sieć VPN 
- Zezwalanie wyłącznie na instalację zarządzanych aplikacji 
- iBookstore 
- iMessages 
- Centrum gier 
- AirDrop 
- AirPlay 
- Parowanie hostów 
- Synchronizacja z chmurą 
- Wyszukiwanie Spotlight 
- Handoff 
- Wymazywanie urządzenia 
- Interfejs użytkownika ograniczeń 
- Instalacja profilów konfiguracji przez interfejs użytkownika 
- News 
- Skróty klawiaturowe 
- Modyfikacje kodu dostępu 
- Zmiany nazwy urządzenia 
- Automatyczne pobieranie aplikacji 
- Zmiany zaufania aplikacji przedsiębiorstwa 
- Apple Music 
- Mail Drop 
- Parowanie z zegarkiem Apple Watch 

> [!NOTE]
> Firma Apple potwierdza, że w 2019 r. niektóre ustawienia będą dostępne wyłącznie w trybie nadzorowanym. Zalecamy wzięcie tego pod uwagę podczas używania tych ustawień zamiast czekania, aż firma Apple przeprowadzi ich migrację do trybu nadzorowanego:
> - Instalowanie aplikacji przez użytkowników końcowych
> - Usuwanie aplikacji
> - FaceTime
> - Safari
> - iTunes
> - Zawartość dla dorosłych
> - Dokumenty i dane iCloud
> - Gry dla wielu graczy
> - Dodaj przyjaciół centrum gier
> - Siri

## <a name="password"></a>Hasło
-   **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -   **Proste hasła** — zezwala na proste hasła, takie jak „0000” i „1234”.
    -   **Wymagany typ hasła** — określa wymagany typ hasła, na przykład alfanumeryczne lub wyłącznie numeryczne.
    -   **Liczba znaków innych niż alfanumeryczne w haśle** — określa liczbę znaków symboli (takich jak **#** lub **@**), którą musi zawierać hasło.
    -   **Minimalna długość hasła** — określa minimalną liczbę znaków w haśle.
    -   **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa dozwoloną liczbę zakończonych niepowodzeniem unikatowych prób wprowadzenia hasła przed wyczyszczeniem urządzenia.
    -   **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**<sup>1</sup> — określa, jak długo urządzenie może pozostawać bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło.
    -   **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**<sup>1</sup> — określa liczbę minut przed wyłączeniem ekranu urządzenia.
    -   **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
    -   **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.
    -   **Odblokowywanie za pomocą odcisku palca** — umożliwia użycie odcisku palca do odblokowania zgodnych urządzeń.
- **Modyfikacja kodu dostępu (tylko nadzorowany)** — uniemożliwia zmianę, dodanie i usunięcie kodu dostępu.
    - **Modyfikacja odcisku palca (tylko nadzorowany)** — uniemożliwia zmianę, dodanie i usunięcie ustawień identyfikatora TouchID.

<sup>1</sup>W przypadku skonfigurowania ustawień **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** i **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** są one stosowane jedno po drugim. Na przykład jeśli wartość obu ustawień zostanie ustawiona na **5** minut, ekran wyłączy się automatycznie po 5 minutach, a urządzenie zostanie zablokowane po kolejnych 5 minutach. Jednak jeśli użytkownik wyłączy ekranie ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie jeśli użytkownik wyłączy ekran, po 5 minutach urządzenie zostanie zablokowane.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

-   **Dostęp do centrum kontroli, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane.
-   **Powiadomienia, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi dostęp do widoku powiadomień bez odblokowywania urządzenia.
-   **Powiadomienia aplikacji Portfel, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane.
-   **Widok Dziś, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi wyświetlanie widoku Dzisiaj, gdy urządzenie jest zablokowane.

## <a name="app-store-doc-viewing-gaming"></a>Sklep App Store, wyświetlanie dokumentów, granie


-   **App Store** — blokuje dostęp do sklepu z aplikacjami na urządzeniach nadzorowanych.
    - **Instalowanie aplikacji ze sklepu App Store (tylko nadzorowany)** — blokuje sklep z aplikacjami na ekranie głównym urządzenia. Użytkownicy końcowi nadal mogą instalować aplikacje przy użyciu programu iTunes lub Apple Configurator.
    - **Automatyczne pobieranie aplikacji (tylko nadzorowany)** — uniemożliwia pobieranie aplikacji zakupionych na innym urządzeniu z systemem iOS na to urządzenie.
-   **Hasło dostępu do sklepu z aplikacjami** — wymaga od użytkownika wprowadzenia hasła przed odwiedzeniem sklepu z aplikacjami.
-   **Zakupy w aplikacji** — umożliwia dokonywanie zakupów w sklepie bezpośrednio z uruchomionej aplikacji.
-   **Jawna zawartość programu iTunes — muzyka, podkasty lub wiadomości (tylko w trybie nadzorowanym)** — zezwala urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych.
-   **Pobieranie zawartości oznaczonej jako „Erotyka” ze sklepu iBooks** — zezwalaj użytkownikom na pobieranie ze sklepu iBooks książek z kategorii „Erotyka”.
-   **Wyświetlanie dokumentów firmowych w niezarządzanych aplikacjach** — umożliwia wyświetlanie dokumentów firmowych w dowolnej aplikacji.<br>**Przykład:** chcesz uniemożliwić użytkownikom zapisywanie plików z aplikacji OneDrive w aplikacji Dropbox. Skonfiguruj to ustawienie jako „nie”. Gdy urządzenie otrzyma zasady (na przykład po ponownym uruchomieniu), nie będzie już miało możliwości zapisywania.
-   **Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych** — umożliwia wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.
-   **Traktuj usługę AirDrop jako niezarządzane miejsce docelowe** — uniemożliwia zarządzanym aplikacjom wysyłanie danych za pomocą funkcji. Airdrop.
-   **Dodawanie znajomych do usługi Game Center (tylko w trybie nadzorowanym)** — umożliwia użytkownikowi dodawanie przyjaciół do usługi Game Center.
-   **Game Center (tylko nadzorowany)** — blokuje lub umożliwia korzystanie z aplikacji Game Center.
-   **Gry dla wielu graczy (tylko w trybie nadzorowanym)** — umożliwia użytkownikowi granie na urządzeniu w gry dla wielu graczy.
-   **Region klasyfikacji** — wybierz region klasyfikacji, dla którego chcesz skonfigurować dozwolone pliki do pobrania, a następnie wybierz dozwoloną klasyfikację dla opcji **Filmy** i **Programy telewizyjne**.
-   **Aplikacje** — wybierz dozwoloną klasyfikację wiekową dla aplikacji, które użytkownicy mogą pobierać, lub wybierz opcję **Zezwalaj na wszystkie aplikacje**.

## <a name="built-in-apps"></a>Aplikacje wbudowane

-   **Aparat fotograficzny** — określa, czy można używać aparatu fotograficznego urządzenia.
    -   **FaceTime** — umożliwia korzystanie z aplikacji FaceTime na urządzeniu.
-   **Siri** — umożliwia korzystanie z asystenta głosowego Siri na urządzeniu.
    -   **Program Siri, gdy urządzenie jest zablokowane** — umożliwia korzystanie z asystenta głosowego Siri na zablokowanym urządzeniu.
    -   **Filtr wulgaryzmów Siri (tylko nadzorowane)** — uniemożliwia dyktowanie lub wypowiadanie wulgaryzmów przez Siri.
    -   **Wyszukiwanie zawartości wygenerowanej przez użytkowników z sieci Internet przez Siri (tylko nadzorowane)** —umożliwia programowi Siri dostęp do witryn sieci Web w celu udzielania odpowiedzi na pytania.
- **Apple News (tylko nadzorowany)** — umożliwia korzystanie z aplikacji Apple News.
- **Sklep iBooks (tylko nadzorowany)** — umożliwia użytkownikowi przeglądanie i kupowanie książek w sklepie iBooks.
- **Aplikacja Messages na urządzeniu (tylko nadzorowany)** — umożliwia wysyłanie i odbieranie wiadomości tekstowych przy użyciu aplikacji Messages.
- **Podcasts (tylko nadzorowany)** — umożliwia korzystanie z aplikacji Podcasts.
- **Usługa Music (tylko nadzorowany)** — umożliwia korzystanie z aplikacji Apple Music.
- **Usługa iTunes Radio (tylko nadzorowany)** — umożliwia korzystanie z aplikacji iTunes Radio.
- **Zmiany ustawień aplikacji Find My Friends (tylko nadzorowany)** — umożliwia użytkownikowi zmianę ustawień aplikacji Find My Friends.
- **Wyniki z sieci Internet w wyszukiwaniach funkcji Spotlight (tylko nadzorowane)** — umożliwia łączenie się funkcji wyszukiwania Spotlight z Internetem w celu dostarczania dodatkowych wyników.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

- Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać. Nie można zapobiec zainstalowaniu zabronionej aplikacji przez użytkowników, lecz jeśli to zrobią, ten fakt zostanie Tobie zgłoszony.
- Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Nie można zapobiec zainstalowaniu przez użytkowników aplikacji spoza listy aplikacji zatwierdzonych, lecz jeśli to zrobią, ten fakt zostanie Ci zgłoszony.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji, użyj następującego formatu:

Korzystając z wyszukiwarki, znajdź w sklepie iTunes aplikację, której chcesz użyć, i otwórz jej stronę.
Skopiuj adres URL strony i użyj go jako adresu URL do skonfigurowania listy aplikacji zatwierdzonych lub zabronionych bądź aplikacji działających w trybie kiosku.
Profile urządzeń zawierające ustawienia aplikacji z ograniczeniami należy przypisać do grup użytkowników.

Przykład: wyszukaj aplikację Microsoft Word dla tabletu iPad. Używany adres URL to https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć polecenia **Kopiuj link**, aby uzyskać adres URL aplikacji.

### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.

## <a name="show-or-hide-apps-supervised-only"></a>Pokaż lub ukryj aplikacje (tylko nadzorowany)

Na liście Pokaż lub ukryj aplikacje możesz skonfigurować jedną z następujących list (wymagane są urządzenia nadzorowane z systemem iOS 9.3 lub nowszym).

- Lista **Ukryte aplikacje** — określ listę aplikacji, które mają być ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
- Lista **Widoczne aplikacje** — określ listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji, użyj następującego formatu:

Korzystając z wyszukiwarki, znajdź w sklepie iTunes aplikację, której chcesz użyć, i otwórz jej stronę.
Skopiuj adres URL strony i użyj go jako adresu URL do skonfigurowania listy aplikacji zatwierdzonych lub zabronionych bądź aplikacji działających w trybie kiosku.

Przykład: wyszukaj aplikację Microsoft Word dla tabletu iPad. Używany adres URL to https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć polecenia **Kopiuj link**, aby uzyskać adres URL aplikacji.

### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę ukrytych lub widocznych aplikacji w tym samym formacie.


## <a name="wireless"></a>Sieć bezprzewodowa
-   **Roaming danych** — zezwala na roaming danych, gdy urządzenie korzysta z sieci komórkowej.
-   **Globalne pobieranie w tle podczas roamingu** — umożliwia pobieranie danych, np. wiadomości e-mail, przez urządzenie korzystające z roamingu w sieci komórkowej.
-   **Wybieranie głosowe** — umożliwia korzystanie z funkcji wybierania głosowego na urządzeniu.
-   **Roaming połączeń głosowych** — zezwala na roaming połączeń głosowych, gdy urządzenie znajduje się w sieci komórkowej.
-   **Zmiany ustawień użycia danych komórkowych aplikacji (tylko nadzorowany)** — umożliwia użytkownikowi kontrolowanie, które aplikacje mogą korzystać z danych komórkowych.
-   **Osobisty hotspot** — nie zezwalaj na używanie urządzenia jako osobistego hotspotu. To ustawienie może być niezgodne w przypadku niektórych operatorów.
-   **Dołączaj do sieci Wi-Fi wyłącznie za pomocą profilów konfiguracji (tylko nadzorowany)** — zezwalaj na dołączanie urządzenia tylko do sieci Wi-Fi, które zostały skonfigurowane przy użyciu profilu sieci Wi-Fi usługi Intune.

- **Zasady użycia danych komórkowych (tylko aplikacje zarządzane)** — umożliwia definiowanie typów danych, których aplikacje zarządzane mogą używać podczas pracy w sieciach komórkowych. Wybierz spośród opcji:
    - **Zablokuj użycie danych komórkowych** — możesz zablokować użycie danych komórkowych dla **wszystkich zarządzanych aplikacji** lub **wybrać określone aplikacje**.
    - **Zablokuj użycie danych komórkowych podczas roamingu** — możesz zablokować użycie danych komórkowych podczas roamingu dla **wszystkich zarządzanych aplikacji** lub **wybrać określone aplikacje**.

## <a name="connected-devices"></a>Połączone urządzenia

-   **AirDrop (tylko nadzorowane)** — umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
-   **Parowanie z urządzeniem Apple Watch (tylko nadzorowany)** — umożliwia parowanie urządzenia z urządzeniem Apple Watch.
-   **Wykrywanie nadgarstka przez sparowane urządzenie Apple Watch** — po włączeniu tego ustawienia urządzenie Apple Watch nie będzie wyświetlać powiadomień, jeśli nie znajduje się na nadgarstku użytkownika.
-   **Modyfikacja protokołu Bluetooth (tylko nadzorowany)** — blokuje zmianę ustawień protokołu Bluetooth na urządzeniu przez użytkownika końcowego.
-   **Parowanie hosta na potrzeby kontrolowania urządzeń, z którymi można parować urządzenie z systemem iOS (tylko nadzorowany)** — zezwala na parowanie hostów w celu umożliwienia administratorowi kontrolowania tego, z którymi urządzeniami może być sparowane urządzenie z systemem iOS.
-   **Wymagaj hasła parowania dla wychodzących żądań AirPlay** — umożliwia wymaganie hasła parowania, gdy użytkownik używa funkcji AirPlay do strumieniowego przesyłania zawartości do innych urządzeń firmy Apple.

## <a name="keyboard-and-dictionary"></a>Klawiatura i słownik

-   **Wyszukiwanie definicji słów (tylko nadzorowane)** — umożliwia używanie funkcji systemu iOS pozwalającej na wyróżnienie wyrazu i wyszukanie jego definicji.
-   **Klawiatury predykcyjne (tylko nadzorowane)** — umożliwia korzystanie z klawiatur predykcyjnych sugerujących wyrazy, które użytkownik może chcieć wpisać.
-   **Korekta automatyczna (tylko nadzorowane)** — pozwala na automatyczne poprawianie błędnie napisanych wyrazów przez urządzenie.
-   **Funkcja sprawdzania pisowni klawiatury (tylko nadzorowane)** — pozwala na korzystanie z modułu sprawdzania pisowni na urządzeniu.
-   **Skróty klawiaturowe (tylko nadzorowane)** — umożliwia używanie skrótów klawiaturowych.
-   **Dyktowanie (tylko nadzorowany)** — uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-   **Tworzenie kopii zapasowych w usłudze iCloud** — umożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud.
-   **Synchronizowanie dokumentów z usługą iCloud (tylko w trybie nadzorowanym)** — umożliwia synchronizowanie dokumentów i wartości kluczy w obszarze magazynu usługi iCloud.
-   **Synchronizowanie strumienia zdjęć z usługą iCloud** — umożliwia użytkownikom włączanie funkcji **Mój strumień zdjęć** na urządzeniach, co pozwala synchronizować zdjęcia z usługą iCloud i udostępniać je na wszystkich urządzeniach użytkownika.
-   **Szyfrowana kopia zapasowa** — wymaga szyfrowania wszystkich kopii zapasowych urządzenia.
-   **Biblioteka zdjęć usługi iCloud** — ustawienie wartości **Nie** powoduje wyłączenie możliwości korzystania z biblioteki zdjęć iCloud, która pozwala użytkownikom przechowywać zdjęcia i klipy wideo w chmurze.   W przypadku ustawienia wartości **Nie** wszelkie zdjęcia, które nie zostały w pełni pobrane z biblioteki zdjęć iCloud na urządzenie, są usuwane z urządzenia.
-   **Zarządzane aplikacje są synchronizowane z chmurą** — zezwala aplikacjom zarządzanym za pomocą usługi Intune na synchronizowanie danych z kontem użytkownika w usłudze iCloud.
-   **Udostępniony strumień zdjęć** — wybór ustawienia **Nie** powoduje wyłączenie funkcji **Udostępnianie zdjęć w usłudze iCloud** na urządzeniu.
-   **Kontynuacja aktywności** — umożliwia użytkownikowi kontynuowanie pracy rozpoczętej na urządzeniu z systemem iOS na innym urządzeniu z systemem iOS lub macOS (program Handoff).

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonomiczny tryb jednej aplikacji (tylko tryb nadzorowany)

Użyj tych ustawień w celu skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w autonomicznym trybie pojedynczej aplikacji. Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane, aby mogło uruchamiać wyłącznie tę aplikację. Opcję tę można przykładowo wykorzystać w przypadku konfigurowania aplikacji, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="settings"></a>Ustawienia

- **Nazwa aplikacji** — wprowadź nazwę aplikacji wyświetlaną na liście aplikacji w tym bloku.
- **Identyfikator pakietu aplikacji** — wprowadź identyfikator pakietu aplikacji. Aby uzyskać pomoc, zobacz **Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS** w tym temacie.

Po określeniu nazwy i identyfikatora pakietu każdej aplikacji wybierz pozycję **Dodaj**, aby dołączyć aplikację do listy.

- **Importuj** — umożliwia zaimportowanie pliku wartości rozdzielanych przecinkami (csv) zawierającego listę nazw aplikacji i powiązanych z nimi identyfikatorów pakietu.
- **Eksportuj** — umożliwia wyeksportowanie skonfigurowanych nazw aplikacji i powiązanych z nimi identyfikatorów pakietu do pliku wartości rozdzielanych przecinkami (csv).

## <a name="kiosk-supervised-only"></a>Kiosk (tylko nadzorowany)
-   **Aplikacja pracująca w trybie kiosku** — wybierz pozycję **Aplikacja zarządzana**, aby wybrać aplikację dodaną do usługi Intune, pozycję **Aplikacja ze Sklepu**, aby określić adres URL aplikacji w sklepie lub pozycję **Aplikacja wbudowana**, aby określić identyfikator pakietu aplikacji wbudowanej. Aby uzyskać więcej informacji, zobacz [Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS](device-restrictions-ios.md#bundle-id-reference-for-built-in-ios-apps) i [Jak określić adres URL aplikacji w sklepie](device-restrictions-ios.md#how-to-specify-the-url-to-an-app-in-the-store-1).
    -   **Dotyk wspomagający** — włącza lub wyłącza funkcję ułatwień dostępu **Dotyk wspomagający**, która ułatwia użytkownikom wykonywanie trudnych dla nich gestów na ekranie.
    -   **Odwróć kolory** — włącza lub wyłącza funkcję ułatwień dostępu Odwróć kolory, która umożliwia dostosowanie wyświetlanego obrazu do potrzeb użytkowników niedowidzących.
    -   **Dźwięk mono** — włącza lub wyłącza ustawienie ułatwień dostępu Dźwięk mono.
    -   **VoiceOver** — włącza lub wyłącza funkcję ułatwień dostępu **VoiceOver**, która odczytuje na głos tekst wyświetlany na ekranie urządzenia.
    -   **Powiększenie** — włącza lub wyłącza funkcję ułatwień dostępu **Powiększenie** umożliwiającą użytkownikowi powiększenie obrazu wyświetlanego na ekranie urządzenia za pomocą dotyku.
    -   **Blokada automatyczna** — włącza lub wyłącza automatyczną blokadę urządzenia.
    -   **Przełącznik dzwonka** — włącza lub wyłącza przełącznik dzwonka (wyciszenie) na urządzeniu.
    -   **Obrót ekranu** — włącza lub wyłącza zmianę orientacji ekranu przy obrocie urządzenia.
    -   **Przycisk usypiania ekranu** — włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.
    -   **Dotyk** — włącza lub wyłącza ekran dotykowy na urządzeniu.
    -   **Przyciski głośności** — włącza lub wyłącza przyciski regulacji głośności na urządzeniu.
    -   **Wspomagająca kontrola dotykowa** — włącza lub wyłącza ustawienia obsługi dotykowej z ułatwieniami, które umożliwiają użytkownikowi dostosowanie funkcji dotyku wspomagającego.
    -   **Odwróć kontrolę kolorów** — włącza lub wyłącza ustawienia funkcji Odwróć kolory, które umożliwiają użytkownikowi dostosowanie jej do swoich potrzeb.
    -   **Mów przy wybranym tekście** — włącza lub wyłącza ustawienia funkcji ułatwień dostępu Czytaj zaznaczenie, która umożliwia odczytanie na głos tekstu zaznaczonego przez użytkownika.
    -   **Kontrola VoiceOver** — włącza lub wyłącza ustawienia funkcji VoiceOver, które umożliwiają dostosowanie jej do swoich potrzeb (na przykład określenie tempa odczytywania tekstu na ekranie).
    -   **Ustawianie powiększenia** — włącza lub wyłącza ustawienia funkcji powiększenia, które umożliwiają użytkownikowi dostosowanie jej do swoich potrzeb.

>[!NOTE]
> Aby można było skonfigurować urządzenie z systemem iOS do obsługi trybu kiosku, należy najpierw użyć narzędzia Apple Configurator lub programu Apple Device Enrollment Program w przełączenia go do trybu nadzorowanego. Aby uzyskać więcej informacji o narzędziu Apple Configurator, skorzystaj z dokumentacji firmy Apple.
>Jeśli określona aplikacja dla systemu iOS zostanie zainstalowana po przypisaniu profilu, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS

Ta lista zawiera identyfikatory pakietu typowych wbudowanych aplikacji systemu iOS. Aby wyszukać identyfikatory pakietu innych aplikacji, skontaktuj się z dostawcą oprogramowania.

| Identyfikator pakietu                   | Nazwa aplikacji     | Wydawca |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | App Store    | Apple     |
| com.apple.calculator        | Kalkulator   | Apple     |
| com.apple.mobilecal         | Kalendarz     | Apple     |
| com.apple.camera            | Aparat fotograficzny       | Apple     |
| com.apple.mobiletimer       | Zegar        | Apple     |
| com.apple.compass           | Kompas      | Apple     |
| com.apple.MobileAddressBook | Kontakty     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.mobileme.fmf1     | Moi znajomi | Apple     |
| com.apple.mobileme.fmip1    | Znajdź mój iPhone  | Apple     |
| com.apple.gamecenter        | Centrum gier  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Kondycja       | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.MapsMaps          |              | Apple     |
| com.apple.MobileSMS         | Komunikaty     | Apple     |
| com.apple.Music             | Muzyka        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Uwagi        | Apple     |
| com.apple.Numbers           | Liczby      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Zdjęcia       | Apple     |
| com.apple.podcasts          | Podcasty     | Apple     |
| com.apple.reminders         | Przypomnienia    | Apple     |
| com.apple.MobileSafari      | Safari       | Apple     |
| com.apple.Preferences       | Ustawienia     | Apple     |
| com.apple.stocks            | Giełda       | Apple     |
| com.apple.tips              | Porady         | Apple     |
| com.apple.videos            | Filmy       | Apple     |
| com.apple.VoiceMemos        | Dyktafon   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Zegarek        | Apple     |
| com.apple.weather           | Pogoda      | Apple     |

## <a name="safari"></a>Safari
-   **Safari (tylko w trybie nadzorowanym)** — określa, czy na urządzeniu można używać przeglądarki Safari.
-   **Autowypełnianie** — umożliwia użytkownikowi zmianę ustawień autouzupełniania w przeglądarce.
-   **Pliki cookie** — umożliwia używanie plików cookie przez przeglądarkę.
-   **JavaScript** — umożliwia uruchamianie skryptów Java w przeglądarce.
-   **Ostrzeżenia przed oszustwem** — umożliwia wyświetlanie ostrzeżeń przed oszustwem w przeglądarce.
-   **Wyskakujące okienka** — włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.


## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nieoznaczone domeny poczty e-mail

W polu **Adres URL domeny poczty e-mail** dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy końcowi otrzymają wiadomość e-mail z domeny innej niż skonfigurowano, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu iOS jako niezaufana.


### <a name="managed-web-domains"></a>Zarządzane domeny sieci Web

W polu **Adres URL domeny sieci Web** dodaj do listy co najmniej jeden adres URL. Dokumenty pobierane ze wskazanych domen są uznawane za zarządzane. To ustawienie ma zastosowanie wyłącznie do dokumentów pobieranych przy użyciu przeglądarki Safari.


### <a name="safari-password-autofill-domains"></a>Domeny automatycznego wypełniania haseł w programie Safari

W polu **Adres URL domeny** dodaj do listy co najmniej jeden adres URL. Użytkownicy mogą zapisywać wyłącznie hasła witryn sieci Web dla adresów URL znajdujących się na tej liście. To ustawienie dotyczy wyłącznie przeglądarki Safari oraz urządzeń z systemem iOS w wersji 9.3 lub nowszym działających w trybie nadzorowanym. Jeśli nie podasz żadnych adresów URL, użytkownicy będą mogli zapisywać hasła ze wszystkich witryn sieci Web.
