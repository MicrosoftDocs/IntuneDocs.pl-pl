---
title: "Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS"
description: "Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu iOS możesz wdrożyć zasady ochrony aplikacji usługi Intune, w postaci funkcji zarządzania aplikacjami mobilnymi (MAM, mobile app management), w swojej aplikacji dla systemu iOS."
keywords: 
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 031ae18fb88a04cd02ca3ced5c39a33e49610bef
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2018
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu iOS możesz wdrożyć zasady ochrony aplikacji usługi Intune (nazywane również zasadami **APP** lub **MAM**) w swojej natywnej aplikacji dla systemu iOS. Aplikacja obsługująca zarządzanie aplikacjami mobilnymi to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy IT mogą wdrażać zasady ochrony aplikacji w aplikacji mobilnej, gdy usługa Intune aktywnie zarządza aplikacją.

## <a name="prerequisites"></a>Wymagania wstępne

* Wymagany jest komputer z systemem Mac OS X 10.8.5 lub nowszym z zainstalowanym programem Xcode 8 lub nowszym.

* Aplikacja jest zgodna z systemem iOS 9 lub nowszym.

* Należy zapoznać się z [postanowieniami licencyjnymi zestawu SDK aplikacji usługi Intune dla systemu iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Wydrukuj i zachowaj kopię postanowień licencyjnych. Pobranie i rozpoczęcie używania zestawu SDK aplikacji usługi Intune dla systemu iOS oznacza akceptację tych postanowień licencyjnych.  Jeśli nie akceptujesz tych postanowień, nie możesz używać tego oprogramowania.

* Pobierz pliki dla zestawu SDK aplikacji usługi Intune dla systemu iOS z serwisu [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Zawartość zestawu SDK

Zestaw SDK aplikacji usługi Intune dla systemu iOS zawiera bibliotekę statyczną, pliki zasobów, nagłówki interfejsu API, plik plist z ustawieniami debugowania i narzędzie Configurator. W większości konfiguracji wymuszania zasad wystarczy dołączyć pliki zasobów do aplikacji mobilnych, które będą statycznie łączyć się z bibliotekami. Zaawansowane funkcje MAM usługi Intune są wymuszane za pośrednictwem interfejsów API.

W tym przewodniku omówiono użycie następujących składników zestawu SDK aplikacji usługi Intune dla systemu iOS:

* **libIntuneMAM.a**: biblioteka statyczna zestawu SDK aplikacji usługi Intune. Jeśli aplikacja nie używa rozszerzeń, należy połączyć tę bibliotekę z projektem, aby umożliwić zarządzanie aplikacją za pomocą zarządzania aplikacjami mobilnymi w usłudze Intune.

* **IntuneMAM.framework**: struktura zestawu SDK aplikacji usługi Intune. Tę strukturę należy połączyć z projektem, aby umożliwić zarządzanie aplikacją za pomocą zarządzania aplikacjami mobilnymi w usłudze Intune. Jeśli aplikacja używa rozszerzeń, można użyć tej struktury zamiast biblioteki statycznej, aby projekt nie tworzył wielu kopii biblioteki statycznej.

* **IntuneMAMResources.bundle**: pakiet zawierający zasoby, na których bazuje zestaw SDK.

* **Nagłówki**: udostępnia interfejsy API zestawu SDK aplikacji usługi Intune. Jeśli korzystasz z interfejsu API, musisz uwzględnić plik nagłówka zawierający interfejs API. Następujące pliki nagłówka zawierają interfejsy API, typy danych oraz protokoły, które zestaw SDK aplikacji usługi Intune udostępnia deweloperom:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h
    
Deweloperzy mogą udostępnić zawartość wszystkich powyższych nagłówków, importując tylko plik IntuneMAM.h


## <a name="how-the-intune-app-sdk-works"></a>Jak działa zestaw SDK aplikacji usługi Intune

Zestaw SDK aplikacji usługi Intune dla systemu iOS opracowano po to, aby umożliwić dodawanie funkcji zarządzania do aplikacji systemu iOS przy minimalnych zmianach w kodzie. Im mniej zmian w kodzie, tym krótszy czas wprowadzenia na rynek, ale bez wpływu na spójność i stabilność aplikacji mobilnej.


## <a name="build-the-sdk-into-your-mobile-app"></a>Kompilowanie aplikacji mobilnej przy użyciu zestawu SDK

Aby włączyć zestaw SDK aplikacji usługi Intune, wykonaj następujące kroki:

1. **Opcja 1 (zalecana)**: połącz strukturę `IntuneMAM.framework` z projektem. Przeciągnij element `IntuneMAM.framework` na listę **Embedded Binaries** (Osadzone pliki binarne) obiektu docelowego projektu.

    > [!NOTE]
    > W przypadku używania struktury należy ręcznie usunąć architektury symulatora z uniwersalnej struktury przed przesłaniem aplikacji do sklepu App Store. Więcej szczegółów można znaleźć w sekcji [Przesyłanie aplikacji do sklepu App Store](#Submit-your-app-to-the-App-Store).

2. **Opcja 2**: połącz z biblioteką `libIntuneMAM.a`. Przeciągnij bibliotekę `libIntuneMAM.a` na listę **Linked Frameworks and Libraries** (Połączone struktury i biblioteki) obiektu docelowego projektu.

    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: połączone struktury i biblioteki](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Dodaj składnik `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do jednej z następujących pozycji, zastępując element `{PATH_TO_LIB}` lokalizacją zestawu SDK aplikacji usługi Intune:
      * Ustawienie konfiguracji kompilacji `OTHER_LDFLAGS` projektu
      * Opcja **Other Linker Flags** (Inne flagi konsolidatora) interfejsu użytkownika środowiska Xcode

        > [!NOTE]
        > Aby ustalić wartość elementu `PATH_TO_LIB`, wybierz plik `libIntuneMAM.a`, a następnie wybierz polecenie **Get Info** (Pobierz informacje) z menu **File** (Plik). Skopiuj i wklej informacje z pola **Where** (Gdzie; ścieżka) z sekcji **General** (Ogólne) okna **Info** (Informacje).

    Dodaj pakiet zasobów `IntuneMAMResources.bundle` do projektu, przeciągając pakiet zasobów w obszarze **Copy Bundle Resources** (Kopiuj pakiety zasobów) w sekcji **Build Phases** (Fazy kompilacji).

    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: kopiowanie zasobów pakietów](./media/intune-app-sdk-ios-copy-bundle-resources.png)

    Dodaj następujące struktury systemu iOS do projektu:          * MessageUI.framework          * Security.framework          * MobileCoreServices.framework          * SystemConfiguration.framework          * libsqlite3.tbd          * libc++.tbd          * ImageIO.framework          * LocalAuthentication.framework          * AudioToolbox.framework          * QuartzCore.framework          * WebKit.framework

3. Włącz udostępnianie łańcucha kluczy (jeśli nie zostało jeszcze włączone), wybierając pozycję **Capabilities** (Możliwości) w każdym obiekcie docelowym projektu i włączając przełącznik **Keychain Sharing** (Udostępnianie łańcucha kluczy). Udostępnianie łańcucha kluczy jest wymagane do przejścia do następnego kroku.

  > [!NOTE]
    > Twój profil aprowizacji musi obsługiwać nowe wartości udostępniania łańcucha kluczy. Grupy dostępu łańcucha kluczy powinny obsługiwać symbol wieloznaczny. Możesz to sprawdzić, otwierając plik mobileprovision w edytorze tekstów, wyszukując frazę **keychain-access-groups** i sprawdzając, czy używany jest symbol wieloznaczny. Przykład:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

4. Po włączeniu udostępniania łańcucha kluczy wykonaj następujące kroki, aby utworzyć oddzielną grupę dostępu, w której będą przechowywane dane zestawu SDK aplikacji usługi Intune. Grupę dostępu łańcucha kluczy możesz utworzyć za pomocą interfejsu użytkownika lub pliku uprawnień. Jeśli używasz interfejsu użytkownika do utworzenia grupy dostępu łańcucha kluczy, koniecznie wykonaj następujące czynności:

    1. Jeśli dla Twojej aplikacji mobilnej nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako pierwszą grupę.

    2. Dodaj udostępnioną grupę łańcucha kluczy `com.microsoft.intune.mam` do istniejących grup dostępu. Zestaw SDK aplikacji usługi Intune używa tej grupy dostępu do przechowywania danych.

    3. Dodaj grupę `com.microsoft.adalcache` do Twoich istniejących grup dostępu.

        ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: udostępnianie łańcucha kluczy](./media/intune-app-sdk-ios-keychain-sharing.png)

    4. Jeśli edytujesz plik uprawnień bezpośrednio, a nie za pomocą przedstawionego powyżej interfejsu użytkownika środowiska Xcode, aby utworzyć grupy dostępu pęku kluczy, dołącz grupy dostępu pęku kluczy przy użyciu elementu `$(AppIdentifierPrefix)` (środowisko Xcode wykonuje tę czynność automatycznie). Przykład:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Plik uprawnień to plik XML, który jest unikatowy dla Twojej aplikacji mobilnej. Służy do określania specjalnych uprawnień i możliwości w Twojej aplikacji dla systemu iOS. Jeśli aplikacja nie miała wcześniej pliku uprawnień, włączenie udostępniania pęku kluczy (krok 3) powinno spowodować wygenerowanie takiego pliku dla aplikacji w środowisku Xcode.

5. Uwzględnij każdy protokół przekazywany przez aplikację do procedury `UIApplication canOpenURL`, w tablicy `LSApplicationQueriesSchemes` pliku Info.plist aplikacji. Pamiętaj o zapisaniu zmian przed przejściem do następnego kroku.

6. Użyj narzędzia IntuneMAMConfigurator, które znajduje się w [repozytorium zestawu SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios), aby ukończyć konfigurowanie pliku Info.plist aplikacji. Narzędzie ma trzy parametry:
|Właściwość|Sposób użycia|
|---------------|--------------------------------|
|- i |  `<Path to the input plist>` |
|- e | `<Path to the entitlements file>` |
|- o |  (Opcjonalnie:) `<Path to the output plist>` |

Jeśli parametr „-o” nie zostanie określony, plik wejściowy zostanie zmodyfikowany w miejscu. Narzędzie jest idempotentne i wymaga ponownego uruchomienia po każdym wprowadzeniu zmian w pliku Info.plist lub uprawnieniach aplikacji. Należy również pobrać i uruchomić najnowszą wersję narzędzia podczas aktualizowania zestawu SDK usługi Intune w przypadku, gdy wymagania dotyczące konfiguracji pliku Info.plist zostały zmienione w najnowszej wersji.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurowanie biblioteki uwierzytelniania usługi Azure Active Directory (ADAL)

Zestaw SDK aplikacji usługi Intune używa [biblioteki uwierzytelniania usługi Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) na potrzeby scenariuszy uwierzytelniania i uruchamiania warunkowego. Używa również biblioteki ADAL do zarejestrowania tożsamości użytkownika w usłudze zarządzania aplikacjami mobilnymi dla scenariuszy zarządzania bez rejestracji urządzenia.

Zazwyczaj biblioteka ADAL wymaga od aplikacji zarejestrowania się w usłudze Azure Active Directory (AAD) i uzyskania unikatowego identyfikatora (identyfikatora klienta) oraz innych identyfikatorów w celu zagwarantowania bezpieczeństwa tokenów przyznanych aplikacji. Jeżeli nie określono inaczej, zestaw SDK aplikacji usługi Intune używa domyślnych wartości rejestracji podczas kontaktowania się z usługą Azure AD.  

Jeśli aplikacja używa już biblioteki ADAL do uwierzytelniania użytkowników, musi używać istniejących wartości rejestracji i zastępować wartości domyślne zestawu SDK aplikacji usługi Intune. Dzięki temu użytkownicy nie będą monitowani o uwierzytelnienie dwukrotnie (raz przez zestaw SDK aplikacji usługi Intune i drugi raz przez aplikację).

### <a name="recommendations"></a>Zalecenia

Zaleca się, by aplikacja łączyła się z [najnowszą wersją biblioteki ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) na jej głównej gałęzi. Zestaw SDK aplikacji usługi Intune aktualnie używa gałęzi brokera biblioteki ADAL w celu obsługi aplikacji, które wymagają dostępu warunkowego. (Te aplikacje są w związku z tym zależne od aplikacji Microsoft Authenticator). Zestaw SDK jest jednak nadal zgodny z główną gałęzią biblioteki ADAL. Skorzystaj z gałęzi, która jest odpowiednia dla danej aplikacji.

### <a name="link-to-adal-binaries"></a>Tworzenie połączenia z plikami binarnymi biblioteki ADAL

Wykonaj następujące czynności, aby połączyć aplikację z plikami binarnymi biblioteki ADAL:

1. Pobierz [Azure Active Directory Authentication Library (ADAL) dla Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) z witryny GitHub, następnie postępuj zgodnie z [instrukcjami](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) pobierania biblioteki ADAL przy użyciu modułów podrzędnych Git lub narzędzia CocoaPods.

2. Dodaj do projektu strukturę ADAL (opcja 1) lub bibliotekę statyczną (opcja 2):
    
    **Opcja 1 (zalecana)**: przeciągnij element `ADAL.framework` na listę **Embedded Binaries** (Osadzone pliki binarne) obiektu docelowego projektu.
    
    **Opcja 2**: przeciągnij bibliotekę `libADALiOS.a` na listę **Linked Frameworks and Libraries** (Połączone struktury i biblioteki) obiektu docelowego projektu. Dodaj polecenie `-force_load {PATH_TO_LIB}/libADALiOS.a` do ustawienia konfiguracji kompilacji `OTHER_LDFLAGS` projektu lub pozycji **Other Linker Flags** (Inne flagi konsolidatora) w interfejsie użytkownika środowiska Xcode. Element `PATH_TO_LIB` należy zastąpić lokalizacją plików binarnych biblioteki ADAL.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Udostępnić pamięć podręczną tokenu biblioteki ADAL innym aplikacjom podpisanym za pomocą tego samego profilu aprowizacji?**

Postępuj zgodnie z instrukcjami poniżej, jeśli chcesz udostępnić tokeny biblioteki ADAL między aplikacjami podpisanymi za pomocą tego samego profilu aprowizacji:

1. Jeśli dla Twojej aplikacji nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako pierwszą grupę.

2. Włącz logowanie jednokrotne do biblioteki ADAL, dodając element `com.microsoft.adalcache` do grup dostępu pęku kluczy.

3. Jeśli chcesz określić niestandardową grupę łańcucha kluczy w celu zastąpienia grupy `com.microsoft.adalcache`, określ ją w pliku Info.plist w obszarze „IntuneMAMSettings” przy użyciu klucza `ADALCacheKeychainGroupOverride`.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Konfigurowanie ustawień biblioteki ADAL dla zestawu SDK aplikacji usługi Intune

Jeśli aplikacja używa już biblioteki ADAL do uwierzytelniania i ma swoje własne ustawienia biblioteki ADAL, można wymusić, by zestaw SDK aplikacji usługi Intune używał takich samych ustawień podczas uwierzytelniania w usłudze Azure Active Directory. Pozwala to zagwarantować, że aplikacja nie będzie dwukrotnie wyświetlać użytkownikowi monitu o uwierzytelnianie. Zobacz sekcję [Konfigurowanie ustawień zestawu SDK aplikacji usługi Intune](#configure-settings-for-the-intune-app-sdk), aby uzyskać informacje dotyczące wprowadzania poniższych ustawień:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Jeśli aplikacja korzysta już z biblioteki ADAL, wymagane są następujące konfiguracje:

1. W słowniku **IntuneMAMSettings** z nazwą klucza `ADALClientId` w pliku Info.plist projektu określ identyfikator klienta, który ma być używany dla wywołań biblioteki ADAL.

2. Również w słowniku **IntuneMAMSettings** z nazwą klucza `ADALAuthority` określ urząd usługi Azure AD.

3. Również w słowniku **IntuneMAMSettings** z nazwą klucza `ADALRedirectUri` określ identyfikator URI przekierowania, który ma być używany dla wywołań biblioteki ADAL. Alternatywnie można również określić element `ADALRedirectScheme`, jeśli identyfikator URI przekierowania aplikacji jest w formacie `scheme://bundle_id`.


Ponadto aplikacje mogą zastąpić te ustawienia usługi Azure AD w środowisku uruchomieniowym. W tym celu wystarczy ustawić właściwości `aadAuthorityUriOverride`, `aadClientIdOverride` oraz `aadRedirectUriOverride` dla wystąpienia `IntuneMAMPolicyManager`.

> [!NOTE]
    > Metoda z użyciem pliku Info.plist jest zalecana dla wszystkich ustawień, które są statyczne i nie wymagają określania w środowisku uruchomieniowym. Wartości przypisane do właściwości `IntuneMAMPolicyManager` są nadrzędne wobec odpowiednich wartości określonych w pliku Info.plist i obowiązują nawet po ponownym uruchomieniu aplikacji. Zestaw SDK będzie w dalszym ciągu używać ich do zaewidencjonowania zasad, dopóki użytkownik nie zostanie wyrejestrowany lub wartości nie zostaną wyczyszczone lub zmienione.

### <a name="if-your-app-does-not-use-adal"></a>Jeśli aplikacja nie używa biblioteki ADAL

Jeśli aplikacja nie używa biblioteki ADAL, zestaw SDK aplikacji usługi Intune udostępni wartości domyślne parametrów biblioteki ADAL i obsłuży uwierzytelnianie w usłudze Azure AD. Nie trzeba określać żadnych wartości dla ustawień biblioteki ADAL wymienionych powyżej.

## <a name="receiving-app-protection-policy"></a>Otrzymywanie zasad ochrony aplikacji

### <a name="overview"></a>Przegląd
Aby otrzymać zasady ochrony aplikacji usługi Intune, aplikacje muszą zainicjować żądanie rejestracji w usłudze Intune. W konsoli usługi Intune można skonfigurować aplikacje do otrzymywania zasad ochrony aplikacji po rejestracji urządzeń lub bez rejestracji. Zasady ochrony aplikacji bez rejestracji, określane również jako zasady **APP-WE** lub MAM-WE, umożliwiają zarządzanie aplikacjami przez usługę Intune bez konieczności rejestracji urządzenia do celów zarządzania urządzeniami mobilnymi (MDM) usługi Intune. W obu przypadkach do otrzymania zasad konieczna jest rejestracja w usłudze Intune.

### <a name="apps-that-use-adal"></a>Aplikacje korzystające z biblioteki ADAL

Aplikacje, które używają już biblioteki ADAL, powinny po pomyślnym uwierzytelnieniu użytkownika wywoływać metodę `registerAndEnrollAccount` dla wystąpienia `IntuneMAMEnrollmentManager`:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```

Przez wywołanie metody `registerAndEnrollAccount` zestaw SDK zarejestruje konto użytkownika i spróbuje zarejestrować aplikację w imieniu tego konta. Jeśli z jakiegokolwiek powodu rejestracja nie powiedzie się, zestaw SDK automatycznie ponowi próbę rejestracji po upływie 24 godzin. Do celów debugowania aplikacja może odbierać [powiadomienia](#Status-result-and-debug-notifications) o wynikach żądań rejestracji za pośrednictwem delegata.

Po wywołaniu tego interfejsu API aplikacja może kontynuować normalne działanie. Jeśli rejestracja powiedzie się, zestaw SDK powiadomi użytkownika, że wymagane jest ponowne uruchomienie aplikacji. Wtedy użytkownik może natychmiast ponownie uruchomić aplikację.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal"></a>Aplikacje, które nie korzystają z bibliotek ADAL

Aplikacje, które nie logują użytkownika za pomocą biblioteki ADAL, mogą mimo to otrzymywać zasady ochrony aplikacji z usługi Intune, wywołując interfejs API, aby zestaw SDK obsłużył to uwierzytelnianie. Tej techniki należy używać w aplikacjach, jeśli nie uwierzytelniły one użytkownika w usłudze Azure AD, ale muszą pobierać zasady ochrony aplikacji w celu ochrony danych. Taka sytuacja może mieć miejsce na przykład wtedy, gdy na potrzeby logowania do aplikacji jest używana inna usługa uwierzytelniania lub gdy aplikacja w ogóle nie obsługuje logowania. W tym celu aplikacja powinna wywołać metodę `loginAndEnrollAccount` dla wystąpienia `IntuneMAMEnrollmentManager`:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

W przypadku wywołania tej metody zestaw SDK będzie monitował użytkownika o poświadczenia, jeśli nie można znaleźć istniejącego tokenu. Zestaw SDK podejmie następnie próbę zarejestrowania aplikacji przy użyciu usługi Intune w imieniu podanego konta użytkownika. Metodę można wywołać z tożsamością „zero”. W tym przypadku zestaw SDK zarejestruje istniejącego zarządzanego użytkownika na urządzeniu (w przypadku zarządzania urządzeniami mobilnymi) lub będzie monitować o nazwę użytkownika, jeśli istniejący użytkownik nie zostanie znaleziony.

W razie niepowodzenia rejestracji aplikacja powinna rozważyć wywołanie tego interfejsu API ponownie w przyszłości, w zależności od szczegółów błędu. Aplikacja może otrzymywać [powiadomienia](#Status-result-and-debug-notifications) o wynikach żądań rejestracji (za pośrednictwem delegata).

Po wywołaniu tego interfejsu API aplikacja może kontynuować normalne działanie. Jeśli rejestracja powiedzie się, zestaw SDK powiadomi użytkownika, że wymagane jest ponowne uruchomienie aplikacji.

Przykład:
```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="deregister-user-accounts"></a>Wyrejestrowanie kont użytkowników

Przed wylogowaniem użytkownika z aplikacji aplikacja powinna wyrejestrować użytkownika z zestawu SDK. Dzięki temu:

1. Nie będą już podejmowane ponowne próby rejestracji dla tego konta użytkownika.

2. Zasady ochrony aplikacji zostaną usunięte.

3. Jeśli aplikacja zainicjuje selektywne czyszczenie danych (opcjonalnie), wszelkie dane firmowe zostaną usunięte.

Przed wylogowaniem użytkownika aplikacja powinna wywołać następującą metodę dla wystąpienia `IntuneMAMEnrollmentManager`:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;

```

Ta metoda musi być wywoływana przed usunięciem tokenów usługi Azure AD konta użytkownika. Zestaw SDK wymaga tokenu AAD konta użytkownika, aby wysyłać określone żądania do usługi Intune w imieniu użytkownika.

Jeśli aplikacja usunie dane firmowe użytkownika samodzielnie, flagę `doWipe` można ustawić na wartość false. W przeciwnym razie aplikacja może zainicjować selektywne czyszczenie za pomocą zestawu SDK. Spowoduje to wywołanie delegata selektywnego czyszczenia aplikacji.

Przykład:
```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Stan, wynik i powiadomienia debugowania

Aplikacja może odbierać stan, wynik i powiadomienia debugowania dotyczące następujących żądań odnoszących się do usługi zarządzania aplikacjami mobilnymi usługi Intune:

 - Żądania rejestracji
 - Żądania aktualizacji zasad
 - Żądania wyrejestrowania

Powiadomienia są prezentowane za pomocą metod delegatów w `Headers/IntuneMAMEnrollmentDelegate.h`:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

Te metody delegatów zwracają obiekt `IntuneMAMEnrollmentStatus`, który zawiera następujące informacje:

- Tożsamość konta skojarzona z żądaniem
- Kod stanu wskazujący wynik żądania
- Ciąg błędu z opisem kodu stanu
- Obiekt `NSError`

Ten obiekt jest zdefiniowany w elemencie `IntuneMAMEnrollmentStatus.h` wraz z konkretnymi kodami stanu, które mogą być zwracane.


### <a name="sample-code"></a>Przykładowy kod

Poniżej przedstawiono przykładowe implementacje metod delegatów:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>Ponowne uruchomienie aplikacji

Po pierwszym odebraniu zasad ochrony aplikacji aplikacja będzie musiała zostać ponownie uruchomiona, aby zastosować wymagane punkty zaczepienia. W celu powiadomienia aplikacji o konieczności wykonania ponownego uruchomienia zestaw SDK udostępnia metodę delegata w pliku Headers/IntuneMAMPolicyDelegate.h.

```objc
 - (BOOL) restartApplication
```
Wartość zwracana przez tę metodę poinformuje zestaw SDK, czy aplikacja musi obsłużyć wymagane ponowne uruchomienie:   

 - Jeśli zwracana jest wartość true, aplikacja musi obsłużyć ponowne uruchomienie.   

 - Jeśli zwracana jest wartość false, zestaw SDK uruchomi ponownie aplikację po zwróceniu wartości przez tę metodę. Zestaw SDK natychmiast wyświetli okno dialogowe z informacją, że użytkownik powinien ponownie uruchomić aplikację.

## <a name="customize-your-apps-behavior"></a>Dostosowywanie zachowania aplikacji

Zestaw SDK aplikacji usługi Intune zawiera kilka interfejsów API, które można wywołać, aby uzyskać informacje o zasadach ochrony aplikacji usługi Intune wdrożonych w aplikacji. Możesz użyć tych danych, aby dostosować zachowanie aplikacji. Większość ustawień zasad ochrony aplikacji jest automatycznie wymuszanych przez zestaw SDK, a nie aplikację. Jedyne ustawienie, jakie musi zostać zaimplementowane w aplikacji, to kontrolka Zapisz jako.

### <a name="get-app-protection-policy"></a>Pobieranie zasad ochrony aplikacji

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
Klasa IntuneMAMPolicyManager udostępnia zasady ochrony aplikacji usługi Intune wdrożone w aplikacji. W szczególności udostępnia interfejsy API przydatne do [włączania wielu tożsamości](#-enable-multi-identity-optional).

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
Klasa IntuneMAMPolicy udostępnia zasady ochrony aplikacji usługi Intune wdrożone w aplikacji. Większość ustawień zasad ujawnianych przez tę klasę jest wymuszanych przez zestaw SDK, ale zawsze można dostosować zachowanie aplikacji na podstawie sposobu wymuszenia ustawień zasad.

Ta klasa udostępnia niektóre interfejsy API potrzebne do zaimplementowania kontrolek Zapisz jako opisanych szczegółowo w następnej sekcji.

### <a name="implement-save-as-controls"></a>Implementowanie kontrolek Zapisz jako

Usługa Intune umożliwia administratorom IT wybieranie lokalizacji przechowywania, w których zarządzana aplikacja może zapisywać dane. Aplikacje mogą wysyłać zapytania o dozwolone lokalizacje przechowywania do zestawu SDK aplikacji usługi Intune przy użyciu interfejsu API **isSaveToAllowedForLocation** zdefiniowane w elemencie **IntuneMAMPolicy.h**.

Przed zapisaniem zarządzanych danych w magazynie w chmurze lub lokalizacji lokalnej aplikacje muszą sprawdzić, za pomocą interfejsu API **isSaveToAllowedForLocation**, czy administrator IT zezwolił na zapisywanie danych w tym miejscu.

W przypadku korzystania z interfejsu API **isSaveToAllowedForLocation** aplikacje muszą przekazać nazwę UPN używaną dla lokalizacji przechowywania, jeśli jest ona dostępna.

#### <a name="supported-save-locations"></a>Obsługiwane lokalizacje zapisywania

Interfejs API **isSaveToAllowedForLocation** zawiera stałe umożliwiające sprawdzenie, czy administrator IT zezwolił na zapisywanie danych w następujących lokalizacjach zdefiniowanych w elemencie IntuneMAMPolicy.h:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Aplikacje powinny używać stałych w interfejsie API **isSaveToAllowedForLocation**, aby sprawdzać, czy można zapisywać dane w lokalizacjach uznawanych za „zarządzane”, np. w usłudze OneDrive dla Firm, lub „osobiste”. Ponadto należy używać interfejsu API w sytuacjach, w których aplikacja nie może określić, czy lokalizacja jest „zarządzana”, czy „osobista”.

Lokalizacje znane jako „osobiste” są reprezentowane przez stałą `IntuneMAMSaveLocationOther`.

Stałej `IntuneMAMSaveLocationLocalDrive` należy używać, gdy aplikacja zapisuje dane w dowolnej lokalizacji na urządzeniu lokalnym.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Konfigurowanie ustawień zestawu SDK aplikacji usługi Intune

Słownik **IntuneMAMSettings** umieszczony w pliku Info.plist aplikacji służy do instalowania i konfigurowania zestawu SDK aplikacji usługi Intune. Jeśli słownik IntuneMAMSettings nie jest widoczny w pliku Info.plist, należy w pliku Info.plist aplikacji utworzyć słownik z polem o nazwie „IntuneMAMSettings”.

W słowniku IntuneMAMSettings można dodać wiersze klucza/wartości ustawień konfiguracji, aby skonfigurować zestaw SDK. W poniższej tabeli uwzględniono wszystkie obsługiwane ustawienia.

Niektóre z tych ustawień mogły zostać omówione w poprzednich sekcjach, a niektóre nie dotyczą wszystkich aplikacji.

Ustawienie  | Typ  | Definicja | Wymagane?
--       |  --   |   --       |  --
ADALClientId  | String  | Identyfikator klienta usługi Azure AD aplikacji. | Wymagane, jeśli aplikacja korzysta z biblioteki ADAL. |
ADALAuthority | String | Urząd usługi Azure AD używany przez aplikację. Należy użyć własnego środowiska, w którym skonfigurowano konta usługi AAD. | Wymagane, jeśli aplikacja korzysta z biblioteki ADAL. W przypadku braku tej wartości używana jest wartość domyślna usługi Intune.|
ADALRedirectUri  | String  | Identyfikator URI przekierowania usługi Azure AD aplikacji. | Ustawienie ADALRedirectUri lub ADALRedirectScheme jest wymagane, jeśli aplikacja korzysta z biblioteki ADAL.  |
ADALRedirectScheme  | String  | Schemat przekierowania usługi Azure AD aplikacji. Może być używany zamiast ustawienia ADALRedirectUri, jeśli identyfikator URI przekierowania aplikacji ma format `scheme://bundle_id`. | Ustawienie ADALRedirectUri lub ADALRedirectScheme jest wymagane, jeśli aplikacja korzysta z biblioteki ADAL. |
ADALLogOverrideDisabled | Boolean  | Określa, czy zestaw SDK będzie przekierowywać wszystkie dzienniki biblioteki ADAL (łącznie z ewentualnymi wywołaniami biblioteki ADAL z aplikacji) do własnego pliku dziennika. Wartość domyślna to NO (Nie). Wybierz wartość YES (Tak), jeśli aplikacja będzie ustawiać własne wywołanie zwrotne dziennika biblioteki ADAL. | Opcjonalny. |
ADALCacheKeychainGroupOverride | String  | Określa grupę łańcucha kluczy do użycia dla pamięci podręcznej biblioteki ADAL zamiast „com.microsoft.adalcache”. Zauważ, że ta grupa nie zawiera prefiksu app-id. Zostanie on umieszczony jako prefiks w podanym ciągu w środowisku uruchomieniowym. | Opcjonalny. |
AppGroupIdentifiers | Tablica ciągów  | Tablica grup aplikacji z sekcji uprawnień aplikacji com.apple.security.application-groups. | Wymagane, jeśli aplikacja używa grup aplikacji. |
ContainingAppBundleId | String | Określa identyfikator pakietu aplikacji zawierającej rozszerzenie. | Wymagane w przypadku rozszerzeń dla systemu iOS. |
DebugSettingsEnabled| Boolean | W przypadku ustawienia na wartość YES (TAK) zasady testu w pakiecie ustawień mogą być stosowane. Aplikacje *nie* powinny być dostarczane z włączonym tym ustawieniem. | Opcjonalny. |
MainNibFile<br>MainNibFile~ipad  | String  | To ustawienie powinno zawierać nazwę pliku głównego nib aplikacji.  | Wymagane, jeśli w pliku Info.plist aplikacji zdefiniowano ustawienie MainNibFile. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | String  | To ustawienie powinno zawierać nazwę pliku głównego storyboard aplikacji. | Wymagane, jeśli w pliku Info.plist aplikacji zdefiniowano ustawienie UIMainStoryboardFile. |
AutoEnrollOnLaunch| Boolean| Określa, czy aplikacja ma podejmować próbę automatycznego rejestrowania w momencie uruchomienia, jeśli wykryto istniejącą tożsamość zarządzaną i nie została ona jeszcze zarejestrowana. Wartość domyślna to NO (Nie). <br><br> Uwagi: jeśli tożsamość zarządzana nie została znaleziona lub nie jest dostępny prawidłowy token tożsamości w pamięci podręcznej biblioteki ADAL, próba rejestracji nie powiedzie się w sposób cichy bez monitowania o poświadczenia, chyba że aplikacja ma również ustawienie MAMPolicyRequired o wartości YES (Tak). | Opcjonalny. |
MAMPolicyRequired| Boolean| Określa, czy uruchamianie aplikacji będzie blokowane, jeśli aplikacja nie ma zasad ochrony aplikacji usługi Intune. Wartość domyślna to NO (Nie). <br><br> Uwagi: Aplikacje nie mogą być przesyłane do sklepu z aplikacjami, jeśli mają ustawienie MAMPolicyRequired o wartości YES (Tak). W przypadku podania wartości YES (Tak) dla ustawienia MAMPolicyRequired ustawienie AutoEnrollOnLaunch również musi mieć wartość YES (Tak). | Opcjonalny. |
MAMPolicyWarnAbsent | Boolean| Określa, czy użytkownik będzie ostrzegany podczas uruchamiania aplikacji, jeśli aplikacja nie ma zasad ochrony aplikacji usługi Intune. <br><br> Uwaga: użytkownicy będą mogli korzystać z aplikacji bez zasad po odrzuceniu ostrzeżenia. | Opcjonalny. |
MultiIdentity | Boolean| Określa, czy aplikacja obsługuje wiele tożsamości. | Opcjonalny. |
SplashIconFile <br>SplashIconFile~ipad | String  | Określa plik ikony powitalnej (uruchamiania) usługi Intune. | Opcjonalny. |
SplashDuration | Liczba | Minimalny czas w sekundach, przez który ekran uruchamiania usługi Intune będzie wyświetlany podczas uruchamiania aplikacji. Wartość domyślna to 1,5. | Opcjonalny. |
BackgroundColor| String| Określa kolor tła ekranu uruchamiania i ekranu numeru PIN. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.   | Opcjonalny. Domyślnie jasnoszary. |
ForegroundColor| String| Określa kolor pierwszego planu ekranu uruchamiania i ekranu numeru PIN, np. kolor tekstu. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.  | Opcjonalny. Domyślnie czarny. |
AccentColor | String| Określa kolor akcentu dla ekranu numeru PIN, na przykład kolor tekstu przycisku i kolor wyróżnienia pola. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.| Opcjonalny. Domyślnie systemowy niebieski. |
MAMTelemetryDisabled| Boolean| Określa, czy zestaw SDK będzie wysyłał dane telemetryczne do swojej wewnętrznej bazy danych.| Opcjonalny. |
WebViewHandledURLSchemes | Tablica ciągów | Określa schematy adresów URL obsługiwane przez widok internetowy Twojej aplikacji. | Wymagane, jeśli aplikacja używa widoku internetowego, który obsługuje adresy URL za pośrednictwem linków i/lub języka JavaScript. |  

> [!NOTE]
> Jeśli aplikacja zostanie udostępniona w sklepie App Store, ustawienie `MAMPolicyRequired` musi być ustawione na wartość „NO” (Nie) zgodnie ze standardami sklepu App Store.

## <a name="enabling-mam-targeted-configuration-for-your-ios-applications"></a>Włączanie docelowej konfiguracji MAM dla aplikacji systemu iOS
Docelowa konfiguracja MAM umożliwia aplikacjom odbieranie danych konfiguracji za pośrednictwem zestawu SDK aplikacji usługi Intune. Format i odmiany tych danych muszą zostać zdefiniowane i przekazane klientom usługi Intune przez właściciela/dewelopera aplikacji. Administratorzy usługi Intune mogą przekazywać dane konfiguracji do miejsc docelowych i wdrażać te dane za pośrednictwem witryny Intune Azure Portal. Począwszy od zestawu SDK aplikacji usługi Intune dla systemu iOS (w wersji 7.0.1), aplikacje uwzględnione w docelowej konfiguracji MAM mogą otrzymywać dane docelowej konfiguracji MAM za pośrednictwem usługi MAM. Dane konfiguracji aplikacji zostaną przypisane do aplikacji bezpośrednio za pośrednictwem naszej usługi MAM zamiast za pośrednictwem kanału zarządzania urządzeniami mobilnymi (MDM). Zestaw SDK aplikacji usługi Intune udostępnia klasę umożliwiającą uzyskanie dostępu do danych pobranych z tych konsol. Rozważ poniższe kwestie w charakterze wymagań wstępnych: <br>
* Aby można było korzystać z interfejsu użytkownika docelowej konfiguracji MAM, aplikacja musi być zarejestrowana w rozwiązaniu MAM-WE. Więcej informacji o rozwiązaniu MAM-WE można znaleźć w [przewodniku po zasadach zabezpieczania aplikacji bez rejestrowania urządzeń w zestawie SDK aplikacji usługi Intune](https://docs.microsoft.com/en-us/intune/app-sdk-ios#app-protection-policy-without-device-enrollment).
* Uwzględnij element ```IntuneMAMAppConfigManager.h``` w pliku źródłowym aplikacji.
* Wywołaj element ```[[IntuneMAMAppConfig instance] appConfigForIdentity:]``` w celu pobrania obiektu konfiguracji aplikacji.
* Wywołaj odpowiedni selektor w obiekcie ```IntuneMAMAppConfig```. Jeśli na przykład klucz aplikacji jest ciągiem, możesz użyć elementu ```stringValueForKey``` lub ```allStringsForKey```. Plik ```IntuneMAMAppConfig.h header``` dotyczy wartości zwracanych/warunków błędów.

Aby uzyskać więcej informacji o możliwościach interfejsu API programu Graph w odniesieniu do wartości docelowej konfiguracji MAM, zobacz [Konfiguracja docelowej konfiguracji MAM w zakresie odwołań do interfejsu API programu Graph](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create). <br>

Więcej informacji na temat tworzenia zasad docelowej konfiguracji aplikacji MAM w systemie iOS można znaleźć w sekcji poświęconej docelowej konfiguracji aplikacji MAM w artykule opisującym [sposób używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-ios).

## <a name="telemetry"></a>Telemetria

Domyślnie zestaw SDK aplikacji usługi Intune dla systemu iOS rejestruje dane telemetryczne następujących zdarzeń użycia. Te dane są wysyłane do usługi Microsoft Intune.

* **Uruchomienie aplikacji**: w celu ułatwienia usłudze Microsoft Intune ustalenia użycia aplikacji z obsługą zarządzania aplikacjami mobilnymi zależnie od typu zarządzania (zarządzanie aplikacjami mobilnymi z zarządzaniem urządzeniami przenośnymi, zarządzanie aplikacjami mobilnymi bez rejestracji w rozwiązaniu do zarządzania urządzeniami przenośnymi itp.).

* **Wywołania rejestracji**: w celu ułatwienia usłudze Microsoft Intune ustalenia współczynnika operacji zakończonych powodzeniem i innych metryk wydajności wywołań rejestracji inicjowanych po stronie klienta.

> [!NOTE]
> Jeśli zrezygnujesz z wysyłania danych telemetrycznych zestawu SDK aplikacji usługi Intune do usługi Microsoft Intune z aplikacji mobilnej, musisz wyłączyć funkcję przechwytywania danych telemetrycznych w zestawie SDK aplikacji usługi Intune. Ustaw właściwość `MAMTelemetryDisabled` na wartość YES (Tak) w słowniku IntuneMAMSettings.

## <a name="enable-multi-identity-optional"></a>Włączanie wielu tożsamości (opcjonalnie)

Domyślnie zestaw SDK stosuje zasady do aplikacji jako całości. Wiele tożsamości to funkcja zarządzania aplikacjami mobilnymi, którą możesz włączyć, aby stosować zasady na poziomie poszczególnych tożsamości. Wymaga to pełniejszego uczestnictwa aplikacji niż inne funkcje zarządzania aplikacjami mobilnymi.

Aplikacja musi poinformować zestaw SDK aplikacji, gdy zamierza zmienić aktywną tożsamość. Zestaw SDK również powiadomi aplikację, kiedy zmiana tożsamości jest wymagana. Aktualnie obsługiwana jest tylko jedna tożsamość zarządzana. Po zarejestrowaniu urządzenia lub aplikacji przez użytkownika zestaw SDK używa tej tożsamości i uznaje ją za podstawową tożsamość zarządzaną. Inni użytkownicy w aplikacji są traktowani jako niezarządzani z nieograniczonymi ustawieniami zasad.

Należy zauważyć, że tożsamość jest definiowana po prostu jako ciąg. W tożsamościach nie jest rozróżniana wielkość liter. Żądania tożsamości wysyłane do zestawu SDK mogą nie zwracać jej z tą samą wielkością liter, której pierwotnie użyto podczas ustawiania tożsamości.

### <a name="identity-overview"></a>Przegląd tożsamości

Tożsamość jest po prostu nazwą użytkownika konta (np. user@contoso.com). Deweloperzy mogą ustawić tożsamość aplikacji na następujących poziomach:

* **Tożsamość procesu**: ustawia tożsamość dla całego procesu i jest używana głównie dla aplikacji z jedną tożsamością. Ta tożsamość ma wpływ na wszystkie zadania i pliki oraz interfejs użytkownika.

* **Tożsamość interfejsu użytkownika**: określa, jakie zasady są stosowane do zadań interfejsu użytkownika w głównym wątku, takich jak wytnij/kopiuj/wklej, kod PIN, uwierzytelnianie i udostępnianie danych. Tożsamość interfejsu użytkownika nie ma wpływu na zadania na plikach (np. szyfrowanie i kopie zapasowe).

* **Tożsamość wątku**: wpływa na to, jakie zasady są stosowane w bieżącym wątku. Ta tożsamość ma wpływ na wszystkie zadania i pliki oraz interfejs użytkownika.

Aplikacja odpowiada za odpowiednie ustawienie tożsamości bez względu na to, czy użytkownik jest zarządzany.

W dowolnym momencie każdy wątek ma obowiązującą tożsamość dla zadań interfejsu użytkownika i zadań na plikach. Jest to tożsamość używana do sprawdzenia, jakie zasady (jeśli w ogóle) powinny być stosowane. Jeśli tożsamość jest określona jako „brak tożsamości” lub użytkownik nie jest zarządzany, nie są stosowane żadne zasady. Na poniższych diagramach przedstawiono sposób określania obowiązujących tożsamości.

  ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: połączone struktury i biblioteki](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>Kolejki wątków

Aplikacje często wysyłają synchroniczne i asynchroniczne zadania do kolejek wątków. Zestaw SDK przechwytuje wywołania GCD (Grand Central Dispatch) i kojarzy bieżącą tożsamość wątku z wysłanymi zadaniami. Podczas kończenia zadań zestaw SDK tymczasowo zmienia tożsamość wątku na tożsamość skojarzoną z zadaniami, kończy zadania, a następnie przywraca oryginalną tożsamość wątku.


Ponieważ klasa `NSOperationQueue` jest zbudowana na bazie GCD, operacje `NSOperations` będą uruchamiane z tożsamością wątku podczas dodawania zadań do kolejki `NSOperationQueue`. Operacje `NSOperations` lub funkcje wysyłane bezpośrednio za pomocą GCD mają również możliwość zmiany bieżącej tożsamości wątku podczas działania. Ta tożsamość zastąpi tożsamość odziedziczoną z wysyłającego wątku.

### <a name="file-owner"></a>Właściciel pliku

Zestaw SDK śledzi tożsamości właścicieli plików lokalnych i zgodnie z tym stosuje zasady. Właściciel pliku jest ustanawiany podczas tworzenia pliku lub po otwarciu pliku w trybie obcinania. Właściciel jest ustawiany na obowiązującą tożsamość zadania na pliku dla wątku wykonującego zadanie.

Aplikacje mogą także ustawić tożsamość właściciela pliku w sposób jawny przy użyciu elementu `IntuneMAMFilePolicyManager`. Aplikacje mogą używać elementu `IntuneMAMFilePolicyManager` do pobierania właściciela pliku i ustawiania tożsamości interfejsu użytkownika przed wyświetleniem zawartości pliku.

### <a name="shared-data"></a>Dane udostępnione

Jeśli aplikacja tworzy pliki zawierające dane od użytkowników zarządzanych i niezarządzanych, odpowiada za szyfrowanie danych użytkowników zarządzanych. Dane można szyfrować przy użyciu interfejsów API `protect` i `unprotect` w elemencie `IntuneMAMDataProtectionManager`.

Metoda `protect` akceptuje tożsamość, która może być użytkownikiem zarządzanym lub niezarządzanym. Jeśli użytkownik jest zarządzany, dane będą szyfrowane. Jeśli użytkownik jest niezarządzany, do danych kodujących tożsamość zostanie dodany nagłówek, ale dane nie będą szyfrowane. Za pomocą metody `protectionInfo` możesz pobierać właściciela danych.

### <a name="share-extensions"></a>Rozszerzenia udostępniania

Jeśli aplikacja zawiera rozszerzenie udostępniania, właściciela udostępnianego elementu można pobrać przy użyciu metody `protectionInfoForItemProvider` w elemencie `IntuneMAMDataProtectionManager`. Jeśli udostępniony element jest plikiem, zestaw SDK obsłuży ustawianie właściciela pliku. Jeśli udostępniony element to dane, aplikacja jest odpowiedzialna za ustawienie właściciela pliku, gdy te dane są utrwalane w pliku, i wywołanie interfejsu API `setUIPolicyIdentity` przed wyświetleniem tych danych w interfejsie użytkownika.

### <a name="turning-on-multi-identity"></a>Włączanie wielu tożsamości

Domyślnie aplikacje są traktowane jako aplikacje mające jedną tożsamość. Zestaw SDK ustawia tożsamość procesu na zarejestrowanego użytkownika. Aby włączyć obsługę wielu tożsamości, dodaj ustawienie typu wartość logiczna o nazwie `MultiIdentity` z wartością „YES” (Tak) do słownika IntuneMAMSettings w pliku Info.plist aplikacji.

> [!NOTE]
> Po włączeniu obsługi wielu tożsamości tożsamość procesu, tożsamość interfejsu użytkownika i tożsamości wątku są ustawione na wartość zero. Aplikacja jest odpowiedzialna za ich odpowiednie ustawienie.

### <a name="switching-identities"></a>Przełączanie tożsamości

* **Przełączanie tożsamości inicjowane przez aplikację**:

    Przy uruchomieniu aplikacje z obsługą wielu tożsamości są traktowane jako uruchomione przy użyciu nieznanego, niezarządzanego konta. Interfejs użytkownika z warunkowym uruchamianiem nie zostanie uruchomiony, a w aplikacji nie będą wymuszane żadne zasady. Aplikacja odpowiada za powiadamianie zestawu SDK za każdym razem, kiedy tożsamość powinna zostać zmieniona. Zwykle dzieje się tak wtedy, gdy aplikacja ma wyświetlić dane dla określonego konta użytkownika.

    Są to na przykład sytuacje, kiedy użytkownik próbuje otworzyć dokument, skrzynkę pocztową lub kartę w notesie. Aplikacja musi powiadomić zestaw SDK, zanim plik, skrzynka pocztowa lub karta zostaną faktycznie otwarte. Robi to za pomocą interfejsu API `setUIPolicyIdentity` w obiekcie `IntuneMAMPolicyManager`. Ten interfejs API powinien być wywoływany bez względu na to, czy użytkownik jest zarządzany. Jeśli użytkownik jest zarządzany, zestaw SDK przeprowadzi kontrole warunkowego uruchamiania (np. wykrywanie zdjęcia zabezpieczeń systemu, numer PIN i uwierzytelnianie).

    Wynik przełączenia tożsamości jest zwracana do aplikacji asynchronicznie za pomocą procedury obsługi zakończenia. Aplikacja powinna odłożyć otworzenie dokumentu, skrzynki pocztowej lub karty, dopóki nie zostanie zwrócony kod wyniku wskazujący powodzenie. W przypadku niepowodzenia przełączania tożsamości aplikacja powinna anulować zadanie.

* **Przełączanie tożsamości inicjowane przez zestaw SDK**:

    Czasami zestaw SDK prosi aplikację o przełączenie do określonej tożsamości. Aplikacje z obsługą wielu tożsamości muszą implementować metodę `identitySwitchRequired` w `IntuneMAMPolicyDelegate` w celu obsługi tego żądania.

    Gdy ta metoda zostanie wywołana, jeśli aplikacja jest w stanie obsłużyć żądanie przełączenia do określonej tożsamości, powinna przekazać wartość `IntuneMAMAddIdentityResultSuccess` do procedury obsługi zakończenia. Jeśli aplikacja nie może obsłużyć przełączenia tożsamości, powinna przekazać wartość `IntuneMAMAddIdentityResultFailed` do procedury obsługi zakończenia.

    Aplikacja nie musi wywoływać metody `setUIPolicyIdentity` w odpowiedzi na to wywołanie. Jeśli zestawu SDK wymaga od aplikacji przełączenia się na konto użytkownika niezarządzanego, do wywołania metody `identitySwitchRequired` zostanie przekazany pusty ciąg.

* **Selektywne czyszczenie danych**:

    W przypadku selektywnego czyszczenia danych aplikacji zestaw SDK wywoła metodę `wipeDataForAccount` w elemencie `IntuneMAMPolicyDelegate`. Aplikacja odpowiada za usunięcie konta określonego użytkownika i wszelkich skojarzonych z nim danych. Zestaw SDK jest w stanie usunąć wszystkie pliki należące do użytkownika i zrobi to, jeśli aplikacja zwróci wartość „FALSE” z wywołania metody `wipeDataForAccount`.

    Zauważ, że ta metoda jest wywoływana z wątku w tle. Aplikacja nie powinna zwracać wartości, dopóki nie zostaną usunięte wszystkie dane użytkownika (z wyjątkiem plików, jeśli aplikacja zwraca wartość FALSE).

## <a name="ios-best-practices"></a>Najlepsze rozwiązania dla systemu iOS

Opracowując aplikacje dla systemu iOS, należy stosować poniższe najlepsze rozwiązania:

* W systemie plików iOS uwzględniana jest wielkość liter. Upewnij się, że wielkość liter w nazwach plików, takich jak `libIntuneMAM.a` i `IntuneMAMResources.bundle`, jest prawidłowa.

* Jeśli środowisko Xcode nie może odnaleźć biblioteki `libIntuneMAM.a`, możesz rozwiązać ten problem, dodając ścieżkę do tej biblioteki do ścieżek wyszukiwania konsolidatora.

## <a name="faqs"></a>Często zadawane pytania


**Czy do wszystkich interfejsów API można odwoływać się za pomocą natywnego języka Swift lub współdziałania języków Objective-C i Swift?**

Interfejsy API zestawu SDK aplikacji usługi Intune są dostępne wyłącznie w języku Objective-C i nie obsługują **natywnego** języka Swift. Wymagane jest współdziałanie języków Swift i Objective-C.


**Czy wszyscy użytkownicy mojej aplikacji muszą być zarejestrowani w usłudze APP-WE?**

Nie. W rzeczywistości tylko konta służbowe powinny być rejestrowane przy użyciu zestawu SDK aplikacji usługi Intune. Aplikacje są odpowiedzialne za określenie, czy konto jest używane w kontekście miejsca pracy lub nauki.   

**Co z użytkownikami, którzy już zalogowali się do aplikacji? Czy muszą zostać zarejestrowani?**

Aplikacja jest odpowiedzialna za rejestrowanie użytkowników po ich pomyślnym uwierzytelnieniu. Aplikacja jest również odpowiedzialna za zarejestrowanie wszelkich kont istniejących przed zaimplementowaniem w aplikacji funkcji zarządzania aplikacjami mobilnymi bez zarządzania urządzeniami przenośnymi.   

W tym celu aplikacja powinna korzystać z metody `registeredAccounts:`. Ta metoda zwraca element NSDictionary zawierający wszystkie konta zarejestrowane w usłudze zarządzania aplikacjami mobilnymi w usłudze Intune. Jeśli jakiekolwiek konta istniejące w aplikacji nie są obecne na liście, aplikacja powinna zarejestrować te konta za pomocą metody `registerAndEnrollAccount:`.

**Jak często zestaw SDK ponawia próby rejestracji?**

Zestaw SDK będzie automatycznie ponawiać próbę rejestracji dla wszystkich rejestracji wcześniej zakończonych niepowodzeniem co 24 godziny. Robi to w celu upewnienia się, że jeśli organizacja użytkownika włączyła zarządzanie aplikacjami mobilnymi po zalogowaniu się użytkownika do aplikacji, użytkownik zostanie pomyślnie zarejestrowany i otrzyma zasady.

Zestaw SDK przestanie ponawiać próby po wykryciu, że użytkownik pomyślnie zarejestrował aplikację. Dzieje się tak, ponieważ w danym momencie tylko jeden użytkownik może zarejestrować aplikację. Jeśli użytkownik zostanie wyrejestrowany, ponowne próby rozpoczną się ponownie z tym samym 24-godzinnym interwałem.

**Dlaczego użytkownik musi zostać wyrejestrowany?**

Zestaw SDK będzie okresowo wykonywał następujące akcje w tle:

 - Jeśli aplikacja nie jest jeszcze zarejestrowana, co 24 godziny będzie próbował zarejestrować wszystkie zarejestrowane konta.
 - Jeśli aplikacja jest zarejestrowana, zestaw SDK co 8 godzin będzie sprawdzał dostępność aktualizacji zasad ochrony aplikacji.

Wyrejestrowanie użytkownika powiadamia zestaw SDK, że użytkownik nie będzie już używał aplikacji i że można zatrzymać wszystkie zdarzenia okresowe dla konta tego użytkownika. Spowoduje to również wykonanie wyrejestrowania aplikacji i selektywnego czyszczenia danych, jeśli jest to konieczne.

**Czy flagę doWipe należy ustawić na wartość true w metodzie deregister?**

Ta metoda powinna być wywoływana przed wylogowaniem użytkownika z aplikacji.  Jeśli w ramach wylogowywania dane użytkownika są usuwane z aplikacji, można ustawić flagę `doWipe` na wartość false. Jednak jeśli aplikacja nie usuwa danych użytkownika, należy ustawić flagę `doWipe` na wartość true, aby zestaw SDK mógł usunąć te dane.

**Czy istnieją inne sposoby wyrejestrowania aplikacji?**

Tak, administrator IT może wysłać polecenie selektywnego czyszczenia danych do aplikacji. Spowoduje to wyrejestrowanie użytkownika i wyczyszczenie jego danych. Zestaw SDK automatycznie obsługuje ten scenariusz i wysyła powiadomienie za pośrednictwem metody delegata wyrejestrowania.



## <a name="submit-your-app-to-the-app-store"></a>Przesyłanie aplikacji do sklepu App Store

Zarówno kompilacje biblioteki statycznej, jak i struktury zestawu SDK aplikacji usługi Intune są uniwersalnymi plikami binarnymi. Oznacza to, że zawierają kod dla wszystkich architektur urządzeń i symulatorów. Firma Apple odrzuci aplikacje przesłane do sklepu App Store, jeśli zawierają one kod symulatora. Podczas kompilowania biblioteki statycznej na potrzeby kompilacji tylko dla urządzenia konsolidator automatycznie usunie kod symulatora. Wykonaj poniższe kroki, aby upewnić się, że cały kod symulatora został usunięty przed przekazaniem aplikacji do sklepu App Store.

1. Upewnij się, że struktura `IntuneMAM.framework` znajduje się na pulpicie.

2. Uruchom następujące polecenia:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    Pierwsze polecenie usuwa architektury symulatorów z pliku DYLIB struktury. Drugie polecenie kopiuje plik DYLIB tylko dla urządzeń do katalogu struktury.
