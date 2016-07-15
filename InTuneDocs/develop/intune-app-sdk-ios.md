---
# required metadata

title: Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS

> [!NOTE] Warto najpierw przeczytać artykuł [Wprowadzenie do przewodnika zestawu SDK aplikacji usługi Intune](intune-app-sdk-get-started.md), w którym omówiono sposoby przygotowania do integracji na poszczególnych obsługiwanych platformach.* 

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu iOS możesz wdrożyć funkcje zarządzania aplikacjami mobilnymi (MAM) w swojej aplikacji dla systemu iOS. Aplikacja z obsługą funkcji MAM jest zintegrowana z zestawem SDK aplikacji usługi Intune i pozwala administratorom IT wdrażać zasady w aplikacji mobilnej, gdy jest ona aktywnie zarządzana.

# Zawartość zestawu SDK

Zestaw SDK aplikacji usługi Intune dla systemu iOS zawiera bibliotekę statyczną, pliki zasobów, nagłówki interfejsu API, listę właściwości ustawień debugowania i narzędzie Configurator. W większości konfiguracji wymuszania zasad wystarczy dołączyć pliki zasobów do aplikacji mobilnych, które będą statycznie łączyć się z bibliotekami. Zaawansowane funkcje MAM usługi Intune są wymuszane za pośrednictwem interfejsów API.
W tym przewodniku omówiono użycie następujących składników podczas integrowania zestawu SDK aplikacji usługi Intune dla systemu iOS:

* **`libIntuneMAM.a`**: biblioteka zestawu SDK aplikacji usługi Intune Połącz tę bibliotekę z projektem, aby zapewnić obsługę funkcji MAM w aplikacji. Instrukcje znajdują się w sekcji „Kompilowanie aplikacji za pomocą zestawu SDK aplikacji usługi Intune”.

* **`IntuneMAMResources.Bundle`**: pakiet zawierający zasoby, na których bazuje zestaw SDK. 

* **Nagłówki**: udostępnia interfejsy API zestawu SDK aplikacji usługi Intune. Jeśli korzystasz z interfejsu API, musisz uwzględnić plik nagłówka zawierający interfejs API. 

# Jak działa zestaw SDK aplikacji usługi Intune

Zestaw SDK aplikacji usługi Intune dla systemu iOS opracowano po to, aby umożliwić dodawanie funkcji zarządzania do aplikacji systemu iOS przy minimalnych zmianach w kodzie. Ograniczenie liczby zmian w kodzie pozwala szybciej wprowadzić aplikację mobilną na rynek, a jednocześnie zapewnia jej większą spójność i stabilność. 

Aplikacja musi być połączona z biblioteką statyczną i zawierać pakiet zasobów. Plik MAMDebugSettings.plist jest opcjonalny i może być uwzględniony w pakiecie w celu symulowania zasad MAM, stosowanych w odniesieniu do aplikacji bez konieczności wdrażania aplikacji za pomocą usługi Microsoft Intune. Ponadto w kompilacjach do debugowania zasady w pliku MAMDebugSettings.plist można stosować, przesyłając plik MAMDebugSettings.plist do katalogu dokumentów aplikacji za pomocą funkcji udostępniania plików programu iTunes.

# Kompilowanie aplikacji za pomocą zestawu SDK aplikacji usługi Intune 

Wykonaj poniższe kroki, aby włączyć zestaw SDK aplikacji usługi Intune:

1. Ustanów połączenie z biblioteką `libIntuneMAM.a` , wykonując następujące czynności:

    Przeciągnij bibliotekę libIntuneMAM.a i upuść ją na liście „Linked Frameworks and Libraries” (Połączone struktury i biblioteki) obiektu docelowego projektu.  

    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS — połączone struktury i biblioteki](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)
 
    **Uwaga**: Podczas przekazywania do sklepu z aplikacjami użyj wersji biblioteki libIntuneMAM.a, która została skompilowana dla wersji wydanej, a nie wersji do debugowania. Wersja wydana będzie znajdować się w folderze „release” (wydanie). Wersja do debugowania generuje szczegółowe dane wyjściowe, co ułatwia debugowanie problemów z zestawem SDK aplikacji usługi Intune.

2. Dodaj następujące struktury systemu iOS do projektu (jeśli nie zostały jeszcze dodane).
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **Uwaga**: Jeśli aplikacja jest przeznaczona dla systemu iOS7, należy ustawić wartość „Optional” (Opcjonalne) atrybutu „Status” (Stan) struktury `LocalAuthentication.Framework` . 

    Jeśli wartość atrybutu „Status” (Stan) nie jest ustawiona, próba uruchomienia aplikacji w systemie iOS7 zakończy się niepowodzeniem.

    **Uwaga**: W środowisku Xcode 7 zastąpiono rozszerzenia nazw `.dylib` rozszerzeniami `.tbd`.

3. Dodaj pakiet zasobów `IntuneMAMResources.bundle` do projektu, przeciągając pakiet zasobów w obszarze „Copy Bundle Resources” (Kopiuj pakiety zasobów) w sekcji „Build Phases” (Fazy kompilacji). 

    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS — kopiowanie pakietów zasobów](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Dodaj składnik `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do jednej z następujących pozycji, zastępując element `{PATH_TO_LIB}` lokalizacją zestawu SDK aplikacji usługi Intune:
    * ustawienie konfiguracji kompilacji OTHER_LDFLAGS projektu 
    * pozycja „Other Linker Flags” (Inne flagi konsolidatora) w interfejsie użytkownika<br>

    **Uwaga**: Aby ustalić wartość składnika `PATH_TO_LIB`, wybierz plik `libIntuneMAM.a` , a następnie wybierz polecenie „Get Info” (Pobierz informacje) z menu „File” (Plik). Skopiuj i wklej informacje z pola „Where” (Gdzie; ścieżka) z sekcji „General” (Ogólne) okna „Info” (Informacje).

5. Jeśli w pliku `info.plist`Twojej aplikacji mobilnej zdefiniowano główny obiekt Nib lub Storyboard, usuń pola pliku Main Storyboard lub Main Nib. Dodaj usunięte uprzednio wartości Storyboard lub Nib w nowym słowniku o nazwie `IntuneMAMSettings` z następującymi nazwami kluczy zgodnie z wymaganiami:
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    Jeśli w pliku `info.plist`Twojej aplikacji mobilnej nie zdefiniowano głównego obiektu Nib lub Storyboard, te ustawienia **nie są wymagane**. 

    **Uwaga**: Można przeglądać plik `info.plist` w formacie nieprzetworzonym (aby zobaczyć nazwy kluczy), klikając prawym przyciskiem myszy w dowolnym miejscu w treści dokumentu i zmieniając typ widoku na „Show Raw Keys/Values” (Pokaż nieprzetworzone klucze/wartości).

6. Włącz udostępnianie łańcucha kluczy (jeśli nie zostało jeszcze włączone), klikając pozycję „Capabilities” (Możliwości) w każdym obiekcie docelowym projektu i włączając przełącznik Keychain Sharing (Udostępnianie łańcucha kluczy). Udostępnianie łańcucha kluczy jest wymagane do przejścia do następnego kroku.

    **Uwaga**: Twój plik inicjowania obsługi musi obsługiwać nowe wartości udostępniania łańcucha kluczy. Grupy dostępu łańcucha kluczy powinny obsługiwać symbol wieloznaczny. Można to sprawdzić, otwierając plik `.mobileprovision` w edytorze tekstów, wyszukując frazę „keychain-access-groups” i sprawdzając, czy używany jest symbol wieloznaczny, na przykład: 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. Po włączeniu udostępniania łańcucha kluczy wykonaj następujące kroki, aby utworzyć oddzielną grupę dostępu, w której będą przechowywane dane zestawu SDK aplikacji usługi Intune. Można utworzyć grupę dostępu łańcucha kluczy za pomocą interfejsu użytkownika lub pliku uprawnień:

    Tworzenie grupy dostępu łańcucha kluczy za pomocą interfejsu użytkownika: 
    
    * Jeśli dla Twojej aplikacji mobilnej nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako pierwszą grupę.
    * Dodaj udostępnioną grupę łańcucha kluczy com.microsoft.intune.mam. Ta grupa dostępu jest używana przez zestaw SDK aplikacji usługi Intune do przechowywania danych.  
    * Dodaj pakiet zasobów `com.microsoft.adalcache` do Twoich istniejących grup dostępu. 
 
    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS — udostępnianie łańcucha kluczy](../media/intune-app-sdk-ios-keychain-sharing.png)

    Jeśli zamiast zwykłego interfejsu użytkownika używasz pliku uprawnień do utworzenia grupy dostępu łańcucha kluczy, konieczne będzie dołączenie wartości `$(AppIdentifierPrefix)` jako prefiksu grupy dostępu łańcucha kluczy w pliku uprawnień. Przykład: `$(AppIdentifierPrefix)com.microsoft.intune.mam` i `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **Uwaga**: Plik uprawnień jest plikiem XML unikatowym dla Twojej aplikacji mobilnej, używanym do określania specjalnych uprawnień i możliwości w aplikacji systemu iOS.

8. W przypadku aplikacji mobilnych opracowywanych dla systemu iOS 9 i nowszych wymagane jest uwzględnienie każdego protokołu, przekazywanego przez aplikację mobilną do procedury `UIApplication canOpenURL` , w tabeli `LSApplicationQueriesSchemes` pliku `info.plist` aplikacji mobilnej. Ponadto dla każdego protokołu uwzględnionego na liście należy dodać nowy protokół i dołączyć do jego nazwy sufiks `-intunemam`. W tabeli należy również uwzględnić pozycje `http-intunemam`, `https-intunemam`i `ms-outlook-intunemam` . 

9. Jeśli w pliku `info.plist file`aplikacji zdefiniowano schematy adresów URL, dodaj kolejny schemat z sufiksem `-intunemam` dla każdego schematu URL.

10. Jeśli w uprawnieniach aplikacji zdefiniowano grupy aplikacji, dodaj te grupy do słownika `IntuneMAMSettings` w kluczu `AppGroupIdentitifiers` jako tabelę ciągów.

11. Połącz swoją aplikację mobilną z biblioteką ADAL. Biblioteka ADAL dla języka Objective C jest [dostępna w serwisie Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Uwaga**: Zestaw SDK aplikacji usługi Intune był testowany z kodem ADAL broker branch w wersji z dnia 2015-06-19. Upewnij się, że połączenie jest ustanawiane z najnowszą/działającą wersją biblioteki ADAL.

12. Uwzględnij pakiet zasobów `ADALiOSBundle.bundle resource` w projekcie, przeciągając go do obszaru „Copy Bundle Resources” (Kopiuj pakiety zasobów) w sekcji „Build Phases” (Fazy kompilacji).

13. Użyj opcji konsolidatora `-force_load PATH_TO_ADAL_LIBRARY` podczas ustanawiania połączenia z biblioteką.

    Dodaj składnik `-force_load {PATH_TO_LIB}/libADALiOS.a` do ustawienia konfiguracji kompilacji OTHER_LDFLAGS lub pozycji „Other Linker Flags” (Inne flagi konsolidatora) w interfejsie użytkownika. Element „ŚCIEŻKA_DO_BIBLIOTEKI” należy zastąpić lokalizacją plików binarnych biblioteki ADAL. 

Jeśli Twoja aplikacja mobilna używa biblioteki ADAL do uwierzytelniania, przejrzyj sekcję „Konfigurowanie ustawień biblioteki uwierzytelniania usługi Azure Directory”.

## Telemetria 

Zestaw SDK aplikacji usługi Intune dla systemu iOS domyślnie rejestruje dane telemetryczne zdarzeń użycia, które są przesyłane do usługi Microsoft Intune.

Rejestrowane są dane następujących zdarzeń użycia: 

1. Uruchomienie aplikacji w celu ułatwienia usłudze Microsoft Intune ustalenia użycia aplikacji z obsługą funkcji MAM zależnie od typu zarządzania.

2. Wywołanie interfejsu API EnrollApplication w celu ułatwienia usłudze Microsoft Intune ustalenia współczynnika operacji zakończonych powodzeniem i różnych innych metryk wydajności wywołania enrollApplication po stronie klienta.

**Uwaga**: Jeśli zrezygnuje się z wysyłania danych telemetrycznych zestawu SDK aplikacji usługi Intune do usługi Microsoft Intune z aplikacji mobilnej, **musi zostać wyłączona** funkcja przechwytywania danych telemetrycznych w zestawie SDK aplikacji usługi Intune przez wybranie dla właściwości `MAMTelemetryDisabled` ustawienia „YES” (Tak) w obszarze `IntuneMAMSettings`.

## Konfigurowanie ustawień biblioteki uwierzytelniania usługi Azure Directory (ADAL) (opcjonalne)

Zestaw SDK aplikacji usługi Intune używa biblioteki ADAL dla swojego scenariusza uwierzytelniania i uruchamiania warunkowego. Zazwyczaj biblioteka ADAL wymaga od aplikacji zarejestrowania się i uzyskania unikatowego identyfikatora ( `ClientID`) oraz innych identyfikatorów w celu zagwarantowania bezpieczeństwa tokenów przyznanych aplikacji. Zestaw SDK aplikacji usługi Intune używa domyślnych wartości rejestracji podczas kontaktowania się z usługą Azure Active Directory.  Jeśli aplikacja używa biblioteki ADAL w swoim scenariuszu uwierzytelniania, musi użyć jej istniejących wartości rejestracji i przesłonić domyślny zestaw SDK aplikacji usługi Intune, aby zapobiec dwukrotnemu monitowaniu użytkowników o uwierzytelnienie (przez zestaw SDK aplikacji usługi Intune i przez aplikację). 

Poniższe kroki są wymagane, jeśli aplikacja używa biblioteki ADAL do uwierzytelniania. Jeśli Twoja aplikacja mobilna nie bazuje na bibliotece ADAL, żadne dalsze akcje nie są wymagane. 

1. W słowniku `Info.plist`z nazwą klucza `IntuneMAMSettings` w pliku `ADALClientId`projektu określ identyfikator `ClientID` , który ma być używany dla wywołań biblioteki ADAL. 

2. W słowniku `Info.plist`z nazwą klucza `IntuneMAMSettings` w pliku `ADALRedirectUri`projektu określ identyfikator URI przekierowania, który ma być używany dla wywołań biblioteki ADAL. Konieczne może być również określenie schematu `ADALRedirectScheme` zależnie od formatu identyfikatora URI przekierowania aplikacji.

## Kompilowanie własnych rozszerzeń (opcjonalne) 

Podczas kompilowania rozszerzeń należy postępować zgodnie z takimi samymi instrukcjami, jak w przypadku kompilowania aplikacji mobilnej, które zostały podane w sekcji „Kompilowanie aplikacji przy użyciu zestawu SDK aplikacji usługi Intune”. Ponadto należy zaktualizować plik info.plist każdego rozszerzenia, aby dodać klucz ContainingAppBundleId w obszarze słownika IntuneMAMSettings z wartością identyfikatora nadrzędnego pakietu aplikacji.

## Kompilowanie własnych struktur (opcjonalne)

Dzięki zmianom ostatnio wprowadzonym w zestawie SDK aplikacji usługi Intune kompilowanie aplikacji mobilnej przy użyciu określonych flag konsolidatora, jeśli aplikacja mobilna zawiera osadzone struktury aplikacji, nie jest konieczne. 

## Pliki obrazów podczas uruchamiania (opcjonalne)

Gdy aplikacja z obsługą funkcji MAM jest aktywnie zarządzana przez usługę Microsoft Intune, zestaw SDK aplikacji usługi Intune wyświetla ekran startowy podczas uruchamiania aplikacji, aby poinformować użytkownika, że aplikacja jest zarządzana. Możesz opcjonalnie dodać pliki obrazów do wyświetlania na stronie startowej „Zarządzane przez firmę”. Uwzględnij następujące zalecenia dotyczące obrazów:

* Dodaj nazwy plików w słowniku `IntuneMAMSettings` z nazwami kluczy `SplashIconFile` i `SplashIconFile~ipad`. 

* Rozmiary obrazów i wymagania:

    * 180x180 w przypadku telefonów iPhone 6s Plus oraz iPhone 6 Plus, 120x120 w przypadku innych modeli telefonów iPhone oraz 152x152 w przypadku tabletów iPad. 
    
    * Usuń rozszerzenie `.png` z nazw plików. 
    
    * Użyj opcji konsolidatora `@2x` dla wersji plików obrazów w skali 2x i sufiksu `@3x` dla wersji plików obrazów w skali 3x. Jeśli rozmiar obrazów jest nieodpowiedni, będą one skalowane w celu dopasowania. Jeśli nie określono wartości SplashIconFile, zestaw SDK aplikacji usługi Intune wybiera jedną z ikon aplikacji (60x60 dla wszystkich telefonów iPhone, 76x76 dla tabletów iPad).

**Uwaga**: Ten ekran jest wyświetlany podczas uruchamiania, ale może być trwale ukryty przez użytkownika.

# Konfigurowanie ustawień zestawu SDK aplikacji usługi Intune

Słownik `IntuneMAMSettings` umieszczony w pliku `info.plist` aplikacji jest używany do konfigurowania zestawu SDK aplikacji usługi Intune. Na poniższej liście uwzględniono wszystkie obsługiwane ustawienia: 

Niektóre z tych ustawień mogły zostać omówione w poprzednich sekcjach, a niektóre nie dotyczą wszystkich aplikacji. 

Ustawienie  | Typ  | Definicja | Wymagane?
--|--|--|--
ADALClientId  | String  | Identyfikator klienta usługi AAD aplikacji. | Wymagane, jeśli aplikacja używa biblioteki ADAL.
ADALRedirectUri  | String  | Identyfikator URI przekierowania usługi AAD aplikacji. | Wymagane, jeśli aplikacja używa biblioteki ADAL. 
AppGroupIdentifier | Tablica ciągów  | Tablica grup aplikacji z sekcji uprawnień aplikacji com.apple.security.application-groups. | Wymagane, jeśli aplikacja używa grup aplikacji.
ContainingAppBundleId  | String | Określa identyfikator pakietu rozszerzenia zawierającego aplikację. | Wymagane w przypadku rozszerzeń dla systemu iOS.
MainNibFile<br>MainNibFile~ipad  | String  | To ustawienie powinno zawierać nazwę pliku głównego nib aplikacji.  | Wymagane, jeśli w pliku info.plist aplikacji zdefiniowano ustawienie MainNibFile.
MainStoryboardFile<br>MainStoryboardFile~ipad  | String  | To ustawienie powinno zawierać nazwę pliku głównego storyboard aplikacji. | Wymagane, jeśli w pliku info.plist aplikacji zdefiniowano ustawienie UIMainStoryboardFile.
SplashIconFile <br>SplashIconFile~ipad  | String  | Określa plik ikony powitalnej usługi Intune. Aby uzyskać więcej informacji, zobacz sekcję „Pliki obrazów podczas uruchamiania”. | Opcjonalny.
SplashDuration | Liczba | Minimalny czas w sekundach, przez który ekran powitalny usługi Intune będzie wyświetlany podczas uruchamiania aplikacji. Wartość domyślna to 1,5. | Opcjonalny.
ADALLogOverrideDisabled | Boolean  | Określa, czy zestaw SDK będzie przekierowywać wszystkie dzienniki biblioteki ADAL (łącznie z ewentualnymi wywołaniami biblioteki ADAL z aplikacji) do własnego pliku dziennika. Wartość domyślna to NO (Nie). Wybierz wartość YES (Tak), jeśli aplikacja powinna ustawiać własne wywołanie zwrotne dziennika biblioteki ADAL. | Opcjonalny.

# Nagłówki dla zestawu SDK aplikacji usługi Intune 

Następujące nagłówki obejmują wywołania funkcji API wymagane do włączenia funkcji zestawu SDK aplikacji usługi Intune. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

# Debugowanie zestawu SDK aplikacji usługi Intune w środowisku Xcode

Przed testowaniem aplikacji z obsługą funkcji MAM w usłudze Microsoft Intune można użyć elementu `Settings.bundle` w środowisku Xcode. Umożliwi to określenie zasad testowania bez konieczności ustanawiania połączenia z usługą Intune. Aby włączyć ten element:

* Dodaj element `Settings.bundle` , klikając prawym przyciskiem myszy folder najwyższego poziomu w projekcie. Wybierz polecenie „Add -> New File” (Dodaj -> Nowy plik) z menu. Wybierz szablon „Settings Bundle” (Pakiet ustawień) w obszarze „Resources” (Zasoby), aby dodać ten szablon.

* Tylko w przypadku kompilacji do debugowania skopiuj plik `MAMDebugSettings.plist` do pakietu `Settings.bundle`.

* W pliku `Root.plist` (w pakiecie Settings.bundle) dodaj preferencję „Type” Child Pane (Typ; Okno podrzędne), „FileName” (Nazwa pliku) `MAMDebugSettings`.

* W obszarze „Settings -> Your-App-Name” (Ustawienia -> Twoja nazwa aplikacji) przełącz ustawienie „Enable Test Policies” (Włącz zasady testu).

* Uruchom aplikację (wewnątrz lub na zewnątrz środowiska Xcode). 

* W obszarze „Settings -> Your-App-Name -> Enable Test Policies” (Ustawienia -> Twoja nazwa aplikacji -> Włącz zasady testu) przełącz zasady, na przykład „PIN”.

* Uruchom aplikację (wewnątrz lub na zewnątrz środowiska Xcode). Sprawdź, czy numer PIN działa zgodnie z oczekiwaniami.

> [!NOTE] Po wykonaniu powyższych czynności można włączać i przełączać ustawienia w obszarze „Settings -> Your-App-Name -> Enable Test Policies” (Ustawienia -> Twoja nazwa aplikacji -> Włącz zasady testu).

# Zalecane najlepsze rozwiązania dla systemu iOS

Wdrażając aplikacje dla systemu iOS, należy stosować poniższe najlepsze rozwiązania:

W systemie plików iOS uwzględniana jest wielkość liter. Upewnij się, że wielkość liter jest poprawna w nazwach plików takich jak `libIntuneMAM.a` i `IntuneMAMResources.bundle`.

Jeśli środowisko Xcode nie może odnaleźć biblioteki `libIntuneMAM.a`, możesz rozwiązać ten problem, dodając ścieżkę do tej biblioteki do ścieżek wyszukiwania konsolidatora.



<!--HONumber=May16_HO2-->


