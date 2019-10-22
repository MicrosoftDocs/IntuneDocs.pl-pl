---
title: Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS
description: Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu iOS możesz wdrożyć zasady ochrony aplikacji usługi Intune (nazywane również zasadami APP lub MAM) w swojej natywnej aplikacji dla systemu iOS.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/17/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93b48fd5f6482669da923e4c15dcb09c7d328197
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503456"
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS

> [!NOTE]
> Rozważ przeczytanie artykułu [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu iOS możesz wdrożyć zasady ochrony aplikacji usługi Intune (nazywane również zasadami APP lub MAM) w swojej natywnej aplikacji dla systemu iOS. Aplikacja obsługująca zarządzanie aplikacjami mobilnymi to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy IT mogą wdrażać zasady ochrony aplikacji w aplikacji mobilnej, gdy usługa Intune aktywnie zarządza aplikacją.

## <a name="prerequisites"></a>Wymagania wstępne

* Wymagany jest komputer z systemem Mac OS X 10.8.5 lub nowszym oraz z zainstalowanym programem Xcode 9 lub nowszym.

* Aplikacja musi być przeznaczona dla systemu iOS 11 lub nowszego.

* Należy zapoznać się z [postanowieniami licencyjnymi zestawu SDK aplikacji usługi Intune dla systemu iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS.pdf). Wydrukuj i zachowaj kopię postanowień licencyjnych. Pobranie i rozpoczęcie używania zestawu SDK aplikacji usługi Intune dla systemu iOS oznacza akceptację tych postanowień licencyjnych.  Jeśli nie akceptujesz tych postanowień, nie możesz używać tego oprogramowania.

* Pobierz pliki dla zestawu SDK aplikacji usługi Intune dla systemu iOS z serwisu [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk-repository"></a>Zawartość repozytorium zestawu SDK

Następujące pliki są istotne dla aplikacji/rozszerzeń, które nie zawierają kodu Swift lub są kompilowane przy użyciu wersji Xcode wcześniejszej niż 10.2:

* **IntuneMAM.framework**: struktura zestawu SDK aplikacji usługi Intune. Zalecane jest, aby połączyć tę strukturę z aplikacją/rozszerzeniami w celu umożliwienia zarządzania aplikacjami klienckimi usługi Intune. Niektórzy deweloperzy mogą jednak preferować zalety biblioteki statycznej. Zobacz poniżej.

* **libIntuneMAM.a**: biblioteka statyczna zestawu SDK aplikacji usługi Intune. Deweloperzy mogą wybrać opcję łączenia biblioteki statycznej, a nie platformy. Ze względu na to, że w czasie kompilacji biblioteki statyczne są osadzone bezpośrednio w pliku binarnym aplikacji/rozszerzenia, w przypadku korzystania z biblioteki statycznej istnieją pewne korzyści z wydajności w czasie uruchomienia. Integracja z aplikacją jest jednak bardziej skomplikowana. Jeśli aplikacja zawiera jakiekolwiek rozszerzenia, połączenie biblioteki statycznej z aplikacją i rozszerzeniami spowoduje zwiększenie rozmiaru pakietu aplikacji, ponieważ biblioteka statyczna zostanie osadzona w każdym pliku binarnym aplikacji/rozszerzenia. W przypadku korzystania z platformy aplikacje i rozszerzenia mogą współużytkować ten sam plik binarny zestawu SDK usługi Intune, co zmniejsza rozmiar aplikacji.

* **IntuneMAMResources.Bundle**: pakiet zawierający zasoby, na których bazuje zestaw SDK. Pakiet zasobów jest wymagany tylko w przypadku aplikacji, które integrują bibliotekę statyczną (libIntuneMAM.a).

Następujące pliki są istotne dla aplikacji/rozszerzeń, które zawierają kod Swift i są kompilowane przy użyciu Xcode 10.2 lub nowszej wersji:

* **IntuneMAMSwift.framework**: struktura Swift zestawu SDK aplikacji usługi Intune. Ta struktura zawiera wszystkie nagłówki interfejsów API, które będą wywoływane przez aplikację. Połącz tę strukturę z aplikacją/rozszerzeniami, aby włączyć zarządzanie aplikacjami klienckimi usługi Intune.

* **IntuneMAMSwiftStub.framework**: struktura zastępcza Swift zestawu SDK aplikacji usługi Intune. Jest to wymagana zależność IntuneMAMSwift.framework, z którą muszą się łączyć aplikacje/rozszerzenia.


Następujące pliki są istotne dla wszystkich aplikacji/rozszerzeń:

* **IntuneMAMConfigurator**: narzędzie używane do konfigurowania pliku Info.plist aplikacji lub rozszerzenia z minimalnymi wymaganymi zmianami dotyczącymi zarządzania usługą Intune. W zależności od funkcjonalności aplikacji lub rozszerzenia może zajść potrzeba ręcznego wprowadzenia dodatkowych zmian do pliku Info.plist.

* **Nagłówki**: uwidacznia publiczne interfejsy API zestawu SDK aplikacji usługi Intune. Te nagłówki są zawarte w strukturach IntuneMAM/IntuneMAMSwift, więc deweloperzy korzystający z tych platform nie muszą ręcznie dodawać nagłówków do projektów. Deweloperzy chcący łączyć się z biblioteką statyczną (libIntuneMAM.a) muszą ręcznie uwzględnić te nagłówki w projekcie.

Następujące pliki nagłówka zawierają interfejsy API, typy danych oraz protokoły, które zestaw SDK aplikacji usługi Intune udostępnia deweloperom:

-  IntuneMAMAppConfig.h
-  IntuneMAMAppConfigManager.h
-  IntuneMAMDataProtectionInfo.h
-  IntuneMAMDataProtectionManager.h
-  IntuneMAMDefs.h
-  IntuneMAMDiagnosticConsole.h
-  IntuneMAMEnrollmentDelegate.h
-  IntuneMAMEnrollmentManager.h
-  IntuneMAMEnrollmentStatus.h
-  IntuneMAMFileProtectionInfo.h
-  IntuneMAMFileProtectionManager.h
-  IntuneMAMLogger.h
-  IntuneMAMPolicy.h
-  IntuneMAMPolicyDelegate.h
-  IntuneMAMPolicyManager.h
-  IntuneMAMVersionInfo.h

Deweloperzy mogą udostępnić zawartość wszystkich poprzednich nagłówków, importując tylko plik IntuneMAM.h


## <a name="how-the-intune-app-sdk-works"></a>Jak działa zestaw SDK aplikacji usługi Intune

Zestaw SDK aplikacji usługi Intune dla systemu iOS opracowano po to, aby umożliwić dodawanie funkcji zarządzania do aplikacji systemu iOS przy minimalnych zmianach w kodzie. Im mniej zmian w kodzie, tym krótszy czas wprowadzenia na rynek, ale bez wpływu na spójność i stabilność aplikacji mobilnej.


## <a name="build-the-sdk-into-your-mobile-app"></a>Kompilowanie aplikacji mobilnej przy użyciu zestawu SDK

Aby włączyć zestaw SDK aplikacji usługi Intune, wykonaj następujące kroki:

1. **Opcja 1 — struktura (zalecane)** : jeśli używasz Xcode 10.2 lub nowszej wersji i Twoja aplikacja/rozszerzenie zawiera kod Swift, połącz `IntuneMAMSwift.framework` i `IntuneMAMSwiftStub.framework` z obiektem docelowym: przeciągnij `IntuneMAMSwift.framework` i `IntuneMAMSwiftStub.framework` do listy **osadzonych plików binarnych** obiektu docelowego projektu.

    W przeciwnym razie połącz `IntuneMAM.framework` z obiektem docelowym: przeciągnij `IntuneMAM.framework` do listy **osadzonych plików binarnych** elementu docelowego projektu.

   > [!NOTE]
   > W przypadku używania struktury należy ręcznie usunąć architektury symulatora z uniwersalnej struktury przed przesłaniem aplikacji do sklepu App Store. Więcej szczegółów można znaleźć w sekcji [Przesyłanie aplikacji do sklepu App Store](#submit-your-app-to-the-app-store).

   **Opcja 2 — biblioteka statyczna**: ta opcja jest dostępna tylko dla aplikacji/rozszerzeń, które nie zawierają kodu Swift lub zostały skompilowane przy użyciu Xcode w wersji wcześniejszej niż 10.2. utwórz połączenie z biblioteką `libIntuneMAM.a`. Przeciągnij bibliotekę `libIntuneMAM.a` na listę **Linked Frameworks and Libraries** (Połączone struktury i biblioteki) obiektu docelowego projektu.

    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: połączone struktury i biblioteki](./media/app-sdk-ios/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Dodaj składnik `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do jednej z następujących pozycji, zastępując element `{PATH_TO_LIB}` lokalizacją zestawu SDK aplikacji usługi Intune:
   * Ustawienie konfiguracji kompilacji `OTHER_LDFLAGS` projektu.
   * Opcja **Other Linker Flags** (Inne flagi konsolidatora) interfejsu użytkownika środowiska Xcode.

     > [!NOTE]
     > Aby ustalić wartość elementu `PATH_TO_LIB`, wybierz plik `libIntuneMAM.a`, a następnie wybierz polecenie **Get Info** (Pobierz informacje) z menu **File** (Plik). Skopiuj i wklej informacje z pola **Where** (Gdzie; ścieżka) z sekcji **General** (Ogólne) okna **Info** (Informacje).

     Dodaj pakiet zasobów `IntuneMAMResources.bundle` do projektu, przeciągając pakiet zasobów w obszarze **Copy Bundle Resources** (Kopiuj pakiety zasobów) w sekcji **Build Phases** (Fazy kompilacji).

     ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: kopiowanie zasobów pakietów](./media/app-sdk-ios/intune-app-sdk-ios-copy-bundle-resources.png)
         
2. Dodaj następujące struktury systemu iOS do projektu:  
-  MessageUI.framework  
-  Security.framework  
-  MobileCoreServices.framework  
-  SystemConfiguration.framework  
-  libsqlite3.tbd  
-  libc++.tbd  
-  ImageIO.framework  
-  LocalAuthentication.framework  
-  AudioToolbox.framework  
-  QuartzCore.framework  
-  WebKit.framework

3. Włącz udostępnianie łańcucha kluczy (jeśli nie zostało jeszcze włączone), wybierając pozycję **Capabilities** (Możliwości) w każdym obiekcie docelowym projektu i włączając przełącznik **Keychain Sharing** (Udostępnianie łańcucha kluczy). Udostępnianie łańcucha kluczy jest wymagane do przejścia do następnego kroku.

   > [!NOTE]
   > Twój profil aprowizacji musi obsługiwać nowe wartości udostępniania łańcucha kluczy. Grupy dostępu łańcucha kluczy powinny obsługiwać symbol wieloznaczny. Możesz to sprawdzić, otwierając plik mobileprovision w edytorze tekstów, wyszukując frazę **keychain-access-groups** i sprawdzając, czy używany jest symbol wieloznaczny. Przykład:
   >
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

4. Po włączeniu udostępniania łańcucha kluczy wykonaj następujące kroki, aby utworzyć oddzielną grupę dostępu, w której będą przechowywane dane zestawu SDK aplikacji usługi Intune. Grupę dostępu łańcucha kluczy możesz utworzyć za pomocą interfejsu użytkownika lub pliku uprawnień. Jeśli używasz interfejsu użytkownika do utworzenia grupy dostępu łańcucha kluczy, koniecznie wykonaj następujące czynności:

     a. Jeśli dla Twojej aplikacji mobilnej nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako **pierwszą** grupę.
    
    b. Dodaj udostępnioną grupę łańcucha kluczy `com.microsoft.intune.mam` do istniejących grup dostępu. Zestaw SDK aplikacji usługi Intune używa tej grupy dostępu do przechowywania danych.
    
    c. Dodaj grupę `com.microsoft.adalcache` do Twoich istniejących grup dostępu.
    
      ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: udostępnianie łańcucha kluczy](./media/app-sdk-ios/intune-app-sdk-ios-keychain-sharing.png)
    
    d. Jeśli edytujesz plik uprawnień bezpośrednio, a nie za pomocą przedstawionego powyżej interfejsu użytkownika środowiska Xcode, aby utworzyć grupy dostępu pęku kluczy, dołącz grupy dostępu pęku kluczy przy użyciu elementu `$(AppIdentifierPrefix)` (środowisko Xcode wykonuje tę czynność automatycznie). Przykład:
    
      - `$(AppIdentifierPrefix)com.microsoft.intune.mam`
      - `$(AppIdentifierPrefix)com.microsoft.adalcache`
    
      > [!NOTE]
      > Plik uprawnień to plik XML, który jest unikatowy dla Twojej aplikacji mobilnej. Służy do określania specjalnych uprawnień i możliwości w Twojej aplikacji dla systemu iOS. Jeśli aplikacja nie miała wcześniej pliku uprawnień, włączenie udostępniania pęku kluczy (krok 3) powinno spowodować wygenerowanie takiego pliku dla aplikacji w środowisku Xcode. Upewnij się, że identyfikator pakietu aplikacji jest pierwszym wpisem na liście.

5. Uwzględnij każdy protokół przekazywany przez aplikację do procedury `UIApplication canOpenURL`, w tablicy `LSApplicationQueriesSchemes` pliku Info.plist aplikacji. Pamiętaj o zapisaniu zmian przed przejściem do następnego kroku.

6. Jeśli Twoja aplikacja nie używa już identyfikatora FaceID, upewnij się, że klucz [NSFaceIDUsageDescription Info.plist](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW75) jest skonfigurowany z domyślnym komunikatem. Jest to wymagane, aby system iOS mógł poinformować użytkownika, jak aplikacja zamierza użyć identyfikatora FaceID. Ustawienie zasad ochrony aplikacji usługi Intune umożliwia używanie identyfikatora FaceID jako metody dostępu do aplikacji, gdy jest to skonfigurowane przez administratora IT.

7. Użyj narzędzia IntuneMAMConfigurator, które znajduje się w [repozytorium zestawu SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios), aby ukończyć konfigurowanie pliku Info.plist aplikacji. Narzędzie ma trzy parametry:

   |Właściwość|Sposób użycia|
   |---------------|--------------------------------|
   |- i |  `<Path to the input plist>` |
   |- e | `<Path to the entitlements file>` |
   |- o |  (Opcjonalnie) `<Path to the output plist>` |

Jeśli parametr „-o” nie zostanie określony, plik wejściowy zostanie zmodyfikowany w miejscu. Narzędzie jest idempotentne i wymaga ponownego uruchomienia po każdym wprowadzeniu zmian w pliku Info.plist lub uprawnieniach aplikacji. Należy również pobrać i uruchomić najnowszą wersję narzędzia podczas aktualizowania zestawu SDK usługi Intune w przypadku, gdy wymagania dotyczące konfiguracji pliku Info.plist zostały zmienione w najnowszej wersji.

## <a name="configure-adalmsal"></a>Konfigurowanie biblioteki ADAL/MSAL

Zestaw SDK aplikacji usługi Intune może korzystać z [biblioteki uwierzytelniania usługi Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) lub [biblioteki uwierzytelniania firmy Microsoft](https://github.com/AzureAD/microsoft-authentication-library-for-objc) na potrzeby scenariuszy uwierzytelniania i uruchamiania warunkowego. Korzysta on również z biblioteki ADAL/MSAL do rejestracji tożsamości użytkownika w usłudze MAM w celu zarządzania nieobejmującego scenariuszy rejestracji na urządzeniach.

Zazwyczaj biblioteka ADAL wymaga od aplikacji zarejestrowania się w usłudze Azure Active Directory (AAD) i uzyskania unikatowego identyfikatora klienta oraz identyfikatora URI przekierowania w celu zagwarantowania bezpieczeństwa tokenów przyznanych aplikacji. Jeśli aplikacja używa już biblioteki ADAL lub MSAL do uwierzytelniania użytkowników, musi używać istniejących wartości rejestracji i zastępować wartości domyślne zestawu SDK aplikacji usługi Intune. Dzięki temu użytkownicy nie będą monitowani o uwierzytelnienie dwukrotnie (raz przez zestaw SDK aplikacji usługi Intune i drugi raz przez aplikację).

Jeśli Twoja aplikacja nie korzysta już z biblioteki ADAL lub MSAL i nie musisz uzyskiwać dostępu do żadnych zasobów usługi AAD, nie musisz konfigurować rejestracji aplikacji klienta w usłudze AAD, jeśli zdecydujesz się na integrację biblioteki ADAL. W przypadku podjęcia decyzji o zintegrowaniu biblioteki MSAL należy skonfigurować rejestrację aplikacji i zastąpić domyślny identyfikator klienta usługi Intune oraz identyfikator URI przekierowania.  

Zaleca się, aby aplikacja łączyła się z najnowszą wersją biblioteki [ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) lub [MSAL](https://github.com/AzureAD/microsoft-authentication-library-for-objc/releases).

### <a name="link-to-adal-or-msal-binaries"></a>Link do plików binarnych biblioteki ADAL lub MSAL

**Opcja 1 —** Wykonaj następujące [kroki](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download), aby połączyć aplikację z plikami binarnymi biblioteki ADAL.

**Opcja 2 —** Alternatywnie można wykonać [te instrukcje](https://github.com/AzureAD/microsoft-authentication-library-for-objc#installation), aby połączyć aplikację z plikami binarnymi biblioteki MSAL.

1. Jeśli dla Twojej aplikacji nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako pierwszą grupę.

2. Włącz logowanie jednokrotne (SSO) ADAL/MSAL, dodając ciąg `com.microsoft.adalcache` do grup łańcuchów kluczy.

3. W przypadku ustawiania w sposób jawny grupy łańcucha kluczy udostępnionej pamięci podręcznej biblioteki ADAL upewnij się, że jest ona ustawiona na wartość `<appidprefix>.com.microsoft.adalcache`. Biblioteka ADAL ustawi tę grupę za Ciebie, chyba że ją zastąpisz. Jeśli chcesz określić niestandardową grupę łańcucha kluczy w celu zastąpienia grupy `com.microsoft.adalcache`, określ ją w pliku Info.plist w obszarze „IntuneMAMSettings” przy użyciu klucza `ADALCacheKeychainGroupOverride`.

### <a name="configure-adalmsal-settings-for-the-intune-app-sdk"></a>Konfigurowanie ustawień biblioteki ADAL/MSAL dla zestawu SDK aplikacji usługi Intune

Jeśli aplikacja używa już biblioteki ADAL lub MSAL do uwierzytelniania i ma swoje własne ustawienia usługi Azure Active Directory, można wymusić, by zestaw SDK aplikacji usługi Intune używał takich samych ustawień podczas uwierzytelniania w usłudze Azure Active Directory. Pozwala to zagwarantować, że aplikacja nie będzie dwukrotnie wyświetlać użytkownikowi monitu o uwierzytelnianie. Zobacz sekcję [Konfigurowanie ustawień zestawu SDK aplikacji usługi Intune](#configure-settings-for-the-intune-app-sdk), aby uzyskać informacje dotyczące wprowadzania poniższych ustawień:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Jeśli aplikacja korzysta już z biblioteki ADAL lub MSAL, wymagane są następujące konfiguracje:

1. W słowniku **IntuneMAMSettings** z nazwą klucza `ADALClientId` w pliku Info.plist projektu określ identyfikator klienta, który ma być używany dla wywołań biblioteki ADAL.

2. Również w słowniku **IntuneMAMSettings** z nazwą klucza `ADALAuthority` określ urząd usługi Azure AD.

3. Również w słowniku **IntuneMAMSettings** z nazwą klucza `ADALRedirectUri` określ identyfikator URI przekierowania, który ma być używany dla wywołań biblioteki ADAL. Alternatywnie można również określić element `ADALRedirectScheme`, jeśli identyfikator URI przekierowania aplikacji jest w formacie `scheme://bundle_id`.

Ponadto aplikacje mogą zastąpić te ustawienia usługi Azure AD w środowisku uruchomieniowym. W tym celu wystarczy ustawić właściwości `aadAuthorityUriOverride`, `aadClientIdOverride` oraz `aadRedirectUriOverride` dla wystąpienia `IntuneMAMPolicyManager`.

4. Upewnij się, że wykonano kroki udzielania uprawnień aplikacji iOS do usługi zasady ochrony aplikacji (APP). Postępuj zgodnie z instrukcjami w [przewodniku zawierającym wprowadzenie do SDK usługi Intune](app-sdk-get-started.md#next-steps-after-integration) w sekcji „[Udzielanie aplikacji dostępu do usługi ochrony aplikacji w usłudze Intune (opcjonalnie)](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)”.  

> [!NOTE]
> Metoda z użyciem pliku Info.plist jest zalecana dla wszystkich ustawień, które są statyczne i nie wymagają określania w środowisku uruchomieniowym. Wartości przypisane do właściwości `IntuneMAMPolicyManager` są nadrzędne wobec odpowiednich wartości określonych w pliku Info.plist i obowiązują nawet po ponownym uruchomieniu aplikacji. Zestaw SDK będzie w dalszym ciągu używać ich do zaewidencjonowania zasad, dopóki użytkownik nie zostanie wyrejestrowany lub wartości nie zostaną wyczyszczone lub zmienione.

### <a name="if-your-app-does-not-use-adal-or-msal"></a>Jeśli aplikacja nie używa biblioteki ADAL ani MSAL

Jak wspomniano wcześniej, zestaw SDK aplikacji usługi Intune może korzystać z [biblioteki uwierzytelniania Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) lub [biblioteki uwierzytelniania firmy Microsoft](https://github.com/AzureAD/microsoft-authentication-library-for-objc) na potrzeby scenariuszy uwierzytelniania i uruchamiania warunkowego. Korzysta on również z biblioteki ADAL/MSAL do rejestracji tożsamości użytkownika w usłudze MAM w celu zarządzania nieobejmującego scenariuszy rejestracji na urządzeniach. Jeśli **aplikacja nie używa biblioteki ADAL ani MSAL do własnego mechanizmu uwierzytelniania**, może być konieczne skonfigurowanie niestandardowych ustawień usługi AAD w zależności od wybranej biblioteki uwierzytelniania:   

ADAL — zestaw SDK aplikacji usługi Intune udostępni wartości domyślne parametrów biblioteki ADAL i obsłuży uwierzytelnianie w usłudze Azure AD. Deweloperzy nie muszą określać żadnych wartości dla wyżej wymienionych ustawień biblioteki ADAL. 

MSAL — deweloperzy muszą utworzyć rejestrację aplikacji w usłudze AAD przy użyciu niestandardowego identyfikatora URI przekierowania w formacie określonym [w tym miejscu](https://github.com/AzureAD/microsoft-authentication-library-for-objc/wiki/Migrating-from-ADAL-Objective-C-to-MSAL-Objective-C#app-registration-migration). Deweloperzy powinni ustawić wyżej wymienione ustawienia `ADALClientID` i `ADALRedirectUri` lub równoważne im właściwości `aadClientIdOverride` i `aadRedirectUriOverride` właściwości w wystąpieniu `IntuneMAMPolicyManager`. Deweloperzy powinni również upewnić się, że wykonali krok 4 w poprzedniej sekcji, aby udzielić aplikacji dostępu do rejestracji w usłudze Intune App Protection.

### <a name="special-considerations-when-using-msal"></a>Kwestie do uwzględnienia podczas korzystania z biblioteki MSAL 

1. **Sprawdź widok internetowy** — zaleca się, aby aplikacje nie korzystały z SFSafariViewController, SFAuthSession ani ASWebAuthSession jako widoku internetowego dla wszystkich zainicjowanych przez aplikację operacji uwierzytelniania interaktywnego biblioteki MSAL. Jeśli z jakiegoś powodu aplikacja musi korzystać z jednego z tych widoków internetowych dla każdej operacji uwierzytelniania interaktywnego biblioteki MSAL, parametr `SafariViewControllerBlockedOverride` w obszarze słownika `IntuneMAMSettings` musi również mieć wartość `true` w pliku Info.plist aplikacji. OSTRZEŻENIE: spowoduje to wyłączenie punktów zaczepienia SafariViewController usługi Intune w celu włączenia sesji uwierzytelniania. Powoduje to ryzyko wycieków danych w innym miejscu w aplikacji, jeśli aplikacja używa SafariViewController do wyświetlania danych firmowych, zatem aplikacja nie powinna wyświetlać danych firmowych w żadnym z tych typów widoków internetowych.
2. **Łączenie zarówno biblioteki ADAL, jak i MSAL** — deweloperzy muszą określić, czy chcą, aby usługa Intune preferowała bibliotekę MSAL w tym scenariuszu. Domyślnie usługa Intune będzie preferować obsługiwane wersje biblioteki ADAL, jeśli oba rodzaje bibliotek są połączone w czasie wykonywania. Usługa Intune będzie preferować obsługiwaną wersję biblioteki MSAL tylko wówczas, gdy podczas pierwszego uwierzytelniania w usłudze Intune wartość parametru `IntuneMAMUseMSALOnNextLaunch` wynosi `true` w `NSUserDefaults`. Jeśli wartość parametru `IntuneMAMUseMSALOnNextLaunch` wynosi `false` lub nie został on ustawiony, usługa Intune powróci do zachowania domyślnego. Jak sugeruje nazwa, zmiana na `IntuneMAMUseMSALOnNextLaunch` zacznie obowiązywać po następnym uruchomieniu.


## <a name="configure-settings-for-the-intune-app-sdk"></a>Konfigurowanie ustawień zestawu SDK aplikacji usługi Intune

Słownik **IntuneMAMSettings** umieszczony w pliku Info.plist aplikacji służy do instalowania i konfigurowania zestawu SDK aplikacji usługi Intune. Jeśli słownik IntuneMAMSettings nie jest widoczny w pliku Info.plist, należy go utworzyć.

W słowniku IntuneMAMSettings można dodać następujące obsługiwane ustawienia, aby skonfigurować zestaw SDK aplikacji usługi Intune.

Niektóre z tych ustawień mogły zostać omówione w poprzednich sekcjach, a niektóre nie dotyczą wszystkich aplikacji.

Ustawienie  | Typ  | Definicja | Wymagane?
--       |  --   |   --       |  --
ADALClientId  | String  | Identyfikator klienta usługi Azure AD aplikacji. | Wymagane dla wszystkich aplikacji korzystających z bibliotek MSAL i dowolnej aplikacji korzystającej z biblioteki ADAL, która uzyskuje dostęp do zasobu usługi AAD spoza usługi Intune. |
ADALAuthority | String | Urząd usługi Azure AD używany przez aplikację. Należy użyć własnego środowiska, w którym skonfigurowano konta usługi AAD. | Wymagane, jeśli aplikacja używa biblioteki ADAL lub MSAL w celu uzyskania dostępu do zasobu usługi AAD spoza usługi Intune. W przypadku braku tej wartości używana jest wartość domyślna usługi Intune.|
ADALRedirectUri  | String  | Identyfikator URI przekierowania usługi Azure AD aplikacji. | Ustawienie ADALRedirectUri lub ADALRedirectScheme jest wymagane dla wszystkich aplikacji korzystających z biblioteki MSAL i dowolnej aplikacji korzystającej z biblioteki ADAL, która uzyskuje dostęp do zasobu usługi AAD spoza usługi Intune.  |
ADALRedirectScheme  | String  | Schemat przekierowania usługi Azure AD aplikacji. Może być używany zamiast ustawienia ADALRedirectUri, jeśli identyfikator URI przekierowania aplikacji ma format `scheme://bundle_id`. | Ustawienie ADALRedirectUri lub ADALRedirectScheme jest wymagane dla wszystkich aplikacji korzystających z biblioteki MSAL i dowolnej aplikacji korzystającej z biblioteki ADAL, która uzyskuje dostęp do zasobu usługi AAD spoza usługi Intune. |
ADALLogOverrideDisabled | Boolean  | Określa, czy zestaw SDK będzie kierować wszystkie dzienniki bibliotek ADAL/MSAL (w tym wywołania biblioteki ADAL z aplikacji, jeśli występują) do własnego pliku dziennika. Wartość domyślna to NO (Nie). Ustaw wartość YES (Tak), jeśli aplikacja ustawi własne wywołanie zwrotne dzienników bibliotek ADAL/MSAL. | Opcjonalny. |
ADALCacheKeychainGroupOverride | String  | Określa grupę łańcucha kluczy do użycia dla pamięci podręcznej biblioteki ADAL/MSAL zamiast „com.microsoft.adalcache”. Zauważ, że ta grupa nie zawiera prefiksu app-id. Zostanie on umieszczony jako prefiks w podanym ciągu w środowisku uruchomieniowym. | Opcjonalny. |
AppGroupIdentifiers | Tablica ciągów  | Tablica grup aplikacji z sekcji uprawnień aplikacji com.apple.security.application-groups. | Wymagane, jeśli aplikacja używa grup aplikacji. |
ContainingAppBundleId | String | Określa identyfikator pakietu aplikacji zawierającej rozszerzenie. | Wymagane w przypadku rozszerzeń dla systemu iOS. |
DebugSettingsEnabled| Boolean | W przypadku ustawienia na wartość YES (TAK) zasady testu w pakiecie ustawień mogą być stosowane. Aplikacje *nie* powinny być dostarczane z włączonym tym ustawieniem. | Opcjonalny. Wartość domyślna to no (Nie). |
AutoEnrollOnLaunch| Boolean| Określa, czy aplikacja ma podejmować próbę automatycznego rejestrowania w momencie uruchomienia, jeśli wykryto istniejącą tożsamość zarządzaną i nie została ona jeszcze zarejestrowana. Wartość domyślna to NO (Nie). <br><br> Uwagi: Jeśli tożsamość zarządzana nie została znaleziona lub nie jest dostępny prawidłowy token tożsamości w pamięci podręcznej biblioteki ADAL/MSAL, próba rejestracji nie powiedzie się w trybie dyskretnym, bez monitowania o poświadczenia, chyba że aplikacja ma również ustawienie MAMPolicyRequired o wartości YES (Tak). | Opcjonalny. Wartość domyślna to no (Nie). |
MAMPolicyRequired| Boolean| Określa, czy uruchamianie aplikacji będzie blokowane, jeśli aplikacja nie ma zasad ochrony aplikacji usługi Intune. Wartość domyślna to NO (Nie). <br><br> Uwagi: Aplikacje nie mogą być przesyłane do sklepu z aplikacjami, jeśli mają ustawienie MAMPolicyRequired o wartości YES (Tak). W przypadku podania wartości YES (Tak) dla ustawienia MAMPolicyRequired ustawienie AutoEnrollOnLaunch również musi mieć wartość YES (Tak). | Opcjonalny. Wartość domyślna to no (Nie). |
MAMPolicyWarnAbsent | Boolean| Określa, czy użytkownik będzie ostrzegany podczas uruchamiania aplikacji, jeśli aplikacja nie ma zasad ochrony aplikacji usługi Intune. <br><br> Uwaga: użytkownicy będą mogli korzystać z aplikacji bez zasad po odrzuceniu ostrzeżenia. | Opcjonalny. Wartość domyślna to no (Nie). |
MultiIdentity | Boolean| Określa, czy aplikacja obsługuje wiele tożsamości. | Opcjonalny. Wartość domyślna to no (Nie). |
SafariViewControllerBlockedOverride | Boolean| Wyłącza punkty zaczepienia SafariViewController usługi Intune w celu włączenia uwierzytelniania MSAL za pośrednictwem SFSafariViewController, SFAuthSession lub ASWebAuthSession. | Opcjonalny. Wartość domyślna to no (Nie). OSTRZEŻENIE: może spowodować wyciek danych, jeśli jest używany nieprawidłowo. Włącz tylko w razie absolutnej konieczności. Aby uzyskać szczegółowe informacje, zobacz sekcję [Kwestie do uwzględnienia podczas korzystania z biblioteki MSAL](#special-considerations-when-using-msal).  |
SplashIconFile <br>SplashIconFile~ipad | String  | Określa plik ikony powitalnej (uruchamiania) usługi Intune. | Opcjonalny. |
SplashDuration | Liczba | Minimalny czas w sekundach, przez który ekran uruchamiania usługi Intune będzie wyświetlany podczas uruchamiania aplikacji. Wartość domyślna to 1,5. | Opcjonalny. |
BackgroundColor| String| Określa kolor tła składników interfejsu użytkownika zestawu SDK usługi Intune. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.   | Opcjonalny. Domyślny kolor tła systemu, który może się różnić w różnych wersjach systemu iOS i zgodnie z ustawieniem tryb ciemny systemu iOS. |
ForegroundColor| String| Określa kolor pierwszego planu dla składników interfejsu użytkownika zestawu SDK usługi Intune, takich jak kolor tekstu. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.  | Opcjonalny. Wartością domyślną jest kolor etykiety systemu, który może się różnić w różnych wersjach systemu iOS i zgodnie z ustawieniem trybu ciemnego systemu iOS. |
AccentColor | String| Określa kolor akcentu składników interfejsu użytkownika zestawu SDK usługi Intune, takich jak kolor tekstu przycisku i kolor wyróżnienia pola numeru PIN. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.| Opcjonalny. Domyślnie systemowy niebieski. |
SupportsDarkMode| Boolean | Określa, czy schemat kolorów interfejsu użytkownika zestawu SDK usługi Intune powinien obserwować ustawienie trybu ciemnego systemu, jeśli nie ustawiono żadnej wartości jawnej dla BackgroundColor/ForegroundColor/AccentColor | Opcjonalny. Wartość domyślna to yes (Tak). |
MAMTelemetryDisabled| Boolean| Określa, czy zestaw SDK będzie wysyłał dane telemetryczne do swojej wewnętrznej bazy danych.| Opcjonalny. Wartość domyślna to no (Nie). |
MAMTelemetryUsePPE | Boolean | Określa, czy zestaw SDK objęty zarządzaniem aplikacjami mobilnymi będzie wysyłał dane do wewnętrznej bazy danych telemetrii wstępnego środowiska produkcyjnego. Użyj tego ustawienia podczas testowania aplikacji za pomocą zasad usługi Intune, aby dane telemetryczne testu nie mieszały się z danymi klienta. | Opcjonalny. Wartość domyślna to no (Nie). |
MaxFileProtectionLevel | String | Opcjonalny. Umożliwia aplikacji określenie maksymalnej liczby elementów `NSFileProtectionType`, które może obsługiwać. Ta wartość będzie zastępować zasady wysyłane przez usługę, jeśli poziom będzie wyższy niż to, co może obsługiwać aplikacja. Możliwe wartości: `NSFileProtectionComplete`, `NSFileProtectionCompleteUnlessOpen`, `NSFileProtectionCompleteUntilFirstUserAuthentication`, `NSFileProtectionNone`.|
OpenInActionExtension | Boolean | Ustaw wartość YES (Tak) dla rozszerzenia akcji „Otwórz w”. Aby uzyskać więcej informacji, zobacz sekcję Udostępnianie danych przy użyciu kontrolera UIActivityViewController. |
WebViewHandledURLSchemes | Tablica ciągów | Określa schematy adresów URL obsługiwane przez widok internetowy Twojej aplikacji. | Wymagane, jeśli aplikacja używa widoku internetowego, który obsługuje adresy URL za pośrednictwem linków i/lub języka JavaScript. |

## <a name="receive-app-protection-policy"></a>Otrzymywanie zasad ochrony aplikacji

### <a name="overview"></a>Przegląd

Aby otrzymać zasady ochrony aplikacji usługi Intune, aplikacje muszą zainicjować żądanie rejestracji w usłudze MAM usługi Intune. W konsoli usługi Intune można skonfigurować aplikacje do otrzymywania zasad ochrony aplikacji po rejestracji urządzeń lub bez rejestracji. Zasady ochrony aplikacji bez rejestracji, określane również jako zasady **APP-WE** lub MAM-WE, umożliwiają zarządzanie aplikacjami przez usługę Intune bez konieczności rejestracji urządzenia do celów zarządzania urządzeniami mobilnymi (MDM) usługi Intune. W obu przypadkach do otrzymania zasad konieczna jest rejestracja w usłudze MAM usługi Intune.

> [!Important]
> Zestaw SDK aplikacji usługi Intune dla systemu iOS używa 256-bitowych kluczy szyfrowania po włączeniu szyfrowania przy użyciu zasad ochrony aplikacji. Wszystkie aplikacje muszą mieć aktualną wersję zestawu SDK, aby było możliwe udostępnianie chronionych danych.

### <a name="apps-that-already-use-adal-or-msal"></a>Aplikacje korzystające już z biblioteki ADAL lub MSAL

Aplikacje korzystające już z biblioteki ADAL lub MSAL powinny wywołać metodę `registerAndEnrollAccount` na wystąpieniu `IntuneMAMEnrollmentManager` po pomyślnym uwierzytelnieniu użytkownika:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```

Przez wywołanie metody `registerAndEnrollAccount` zestaw SDK zarejestruje konto użytkownika i spróbuje zarejestrować aplikację w imieniu tego konta. Jeśli z jakiegokolwiek powodu rejestracja nie powiedzie się, zestaw SDK automatycznie ponowi próbę rejestracji po upływie 24 godzin. Do celów debugowania aplikacja może odbierać [powiadomienia](#status-result-and-debug-notifications) o wynikach żądań rejestracji za pośrednictwem delegata.

Po wywołaniu tego interfejsu API aplikacja może kontynuować normalne działanie. Jeśli rejestracja powiedzie się, zestaw SDK powiadomi użytkownika, że wymagane jest ponowne uruchomienie aplikacji. Wtedy użytkownik może natychmiast ponownie uruchomić aplikację.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal-or-msal"></a>Aplikacje niekorzystające z biblioteki ADAL ani MSAL

Aplikacje niekorzystające z biblioteki ADAL ani MSAL w celu zalogowania użytkownika mogą uzyskać zasady ochrony aplikacji z usługi zarządzania aplikacjami mobilnymi w usłudze Intune, wywołując interfejs API, aby zestaw SDK obsłużył to uwierzytelnianie. Tej techniki należy używać w aplikacjach, jeśli nie uwierzytelniły one użytkownika w usłudze Azure AD, ale muszą pobierać zasady ochrony aplikacji w celu ochrony danych. Taka sytuacja może mieć miejsce na przykład wtedy, gdy na potrzeby logowania do aplikacji jest używana inna usługa uwierzytelniania lub gdy aplikacja w ogóle nie obsługuje logowania. W tym celu aplikacja może wywołać metodę `loginAndEnrollAccount` dla wystąpienia `IntuneMAMEnrollmentManager`:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

W przypadku wywołania tej metody zestaw SDK będzie monitował użytkownika o poświadczenia, jeśli nie można znaleźć istniejącego tokenu. Zestaw SDK podejmie następnie próbę zarejestrowania aplikacji przy użyciu usługi MAM w usłudze Intune w imieniu podanego konta użytkownika. Metodę można wywołać z tożsamością „zero”. W tym przypadku zestaw SDK zarejestruje istniejącego zarządzanego użytkownika na urządzeniu (w przypadku zarządzania urządzeniami mobilnymi) lub będzie monitować o nazwę użytkownika, jeśli istniejący użytkownik nie zostanie znaleziony.

W razie niepowodzenia rejestracji aplikacja powinna rozważyć wywołanie tego interfejsu API ponownie w przyszłości, w zależności od szczegółów błędu. Aplikacja może otrzymywać [powiadomienia](#status-result-and-debug-notifications) o wynikach żądań rejestracji (za pośrednictwem delegata).

Po wywołaniu tego interfejsu API aplikacja może kontynuować normalne działanie. Jeśli rejestracja powiedzie się, zestaw SDK powiadomi użytkownika, że wymagane jest ponowne uruchomienie aplikacji.

Przykład:

```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="let-intune-handle-authentication-and-enrollment-at-launch"></a>Umożliwienie usłudze Intune obsługiwania uwierzytelniania i rejestracji podczas uruchamiania

Jeśli chcesz, aby zestaw SDK usługi Intune obsługiwał całe uwierzytelnianie przy użyciu biblioteki ADAL/MSAL i rejestrację, zanim aplikacja skończy się uruchamiać, a Twoja aplikacja zawsze wymaga zasad aplikacji, nie musisz używać interfejsu API `loginAndEnrollAccount`. Wystarczy dla dwóch poniższych ustawień ustawić wartość YES (Tak) w słowniku IntuneMAMSettings w pliku Info.plist aplikacji.

Ustawienie  | Typ  | Definicja |
--       |  --   |   --       |  
AutoEnrollOnLaunch| Boolean| Określa, czy aplikacja ma podejmować próbę automatycznego rejestrowania w momencie uruchomienia, jeśli wykryto istniejącą tożsamość zarządzaną i nie została ona jeszcze zarejestrowana. Wartość domyślna to NO (Nie). <br><br> Uwaga: Jeśli tożsamość zarządzana nie została znaleziona lub nie jest dostępny prawidłowy token tożsamości w pamięci podręcznej biblioteki ADAL/MSAL, próba rejestracji nie powiedzie się w trybie dyskretnym, bez monitowania o poświadczenia, chyba że aplikacja ma również ustawienie MAMPolicyRequired o wartości YES (Tak). |
MAMPolicyRequired| Boolean| Określa, czy uruchamianie aplikacji będzie blokowane, jeśli aplikacja nie ma zasad ochrony aplikacji usługi Intune. Wartość domyślna to NO (Nie). <br><br> Uwaga: aplikacje nie mogą być przesłane do sklepu z aplikacjami z ustawieniem MAMPolicyRequired ustawionym na wartość YES (Tak). W przypadku podania wartości YES (Tak) dla ustawienia MAMPolicyRequired ustawienie AutoEnrollOnLaunch również musi mieć wartość YES (Tak). |

Jeśli wybierzesz tę opcję dla swojej aplikacji, nie musisz ponownie uruchamiać aplikacji po zarejestrowaniu.

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
 *  until the Intune APP AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Ta metoda musi być wywoływana przed usunięciem tokenów usługi Azure AD konta użytkownika. Zestaw SDK wymaga tokenu AAD konta użytkownika, aby wysyłać określone żądania do usługi MAM w usłudze Intune w imieniu użytkownika.

Jeśli aplikacja usunie dane firmowe użytkownika samodzielnie, flagę `doWipe` można ustawić na wartość false. W przeciwnym razie aplikacja może zainicjować selektywne czyszczenie za pomocą zestawu SDK. Spowoduje to wywołanie delegata selektywnego czyszczenia aplikacji.

Przykład:

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Stan, wynik i powiadomienia debugowania

Aplikacja może odbierać stan, wynik i powiadomienia debugowania dotyczące następujących żądań odnoszących się do usługi zarządzania aplikacjami mobilnymi usługi Intune:

* Żądania rejestracji
* Żądania aktualizacji zasad
* Żądania wyrejestrowania

Powiadomienia są prezentowane za pomocą metod delegatów w `IntuneMAMEnrollmentDelegate.h`:

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

* Tożsamość konta skojarzona z żądaniem
* Kod stanu wskazujący wynik żądania
* Ciąg błędu z opisem kodu stanu
* Obiekt `NSError`. Ten obiekt jest zdefiniowany w elemencie `IntuneMAMEnrollmentStatus.h` wraz z konkretnymi kodami stanu, które mogą być zwracane.

### <a name="sample-code"></a>Przykładowy kod

Poniżej przedstawiono przykładowe implementacje metod delegatów:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="application-restart"></a>Ponowne uruchamianie aplikacji

Po pierwszym odebraniu zasad zarządzania aplikacjami mobilnymi aplikacja będzie musiała zostać ponownie uruchomiona, aby zastosować wymagane punkty zaczepienia. W celu powiadomienia aplikacji o konieczności wykonania ponownego uruchomienia zestaw SDK udostępnia metodę delegata w elemencie `IntuneMAMPolicyDelegate.h`.

```objc
 - (BOOL) restartApplication
```

Wartość zwracana przez tę metodę poinformuje zestaw SDK, czy aplikacja musi obsłużyć wymagane ponowne uruchomienie:

* Jeśli zwracana jest wartość true, aplikacja musi obsłużyć ponowne uruchomienie.

* Jeśli zwracana jest wartość false, zestaw SDK uruchomi ponownie aplikację po zwróceniu wartości przez tę metodę. Zestaw SDK natychmiast wyświetli okno dialogowe z informacją, że użytkownik powinien ponownie uruchomić aplikację.

## <a name="customize-your-apps-behavior-with-apis"></a>Dostosowywanie zachowania aplikacji za pomocą interfejsów API

Zestaw SDK aplikacji usługi Intune zawiera kilka interfejsów API, które można wywołać, aby uzyskać informacje o zasadach aplikacji usługi Intune wdrożonych w aplikacji. Możesz użyć tych danych, aby dostosować zachowanie aplikacji. Następująca tabela zawiera informacje dotyczące niektórych podstawowych klas usługi Intune, których użyjesz.

Klasa | Opis
----- | -----------
IntuneMAMPolicyManager.h | Klasa IntuneMAMPolicyManager udostępnia zasady aplikacji usługi Intune wdrożone w aplikacji. W szczególności udostępnia interfejsy API przydatne do [włączania wielu tożsamości](app-sdk-ios.md#enable-multi-identity-optional). |
IntuneMAMPolicy.h | Klasa IntuneMAMPolicy udostępnia niektóre ustawienia zasad zarządzania aplikacjami mobilnymi, które mają zastosowanie do aplikacji. Te ustawienia zasad są udostępniane, aby aplikacja mogła dostosować swój interfejs użytkownika. Większość ustawień zasad jest wymuszanych przez zestaw SDK, a nie przez aplikację. Jedyne ustawienie, jakie musi zostać zaimplementowane w aplikacji, to kontrolka Zapisz jako. Ta klasa udostępnia niektóre interfejsy API potrzebne do zaimplementowania kontrolki Zapisz jako. |
IntuneMAMFileProtectionManager.h | Klasa IntuneMAMFileProtectionManager udostępnia interfejsy API, przy użyciu których aplikacja może jawnie zabezpieczać pliki i katalogi na podstawie podanej tożsamości. Tożsamość może być zarządzana przez usługę Intune lub niezarządzana, a zestaw SDK zastosuje odpowiednie zasady zarządzania aplikacjami mobilnymi. Użycie tej klasy jest opcjonalne. |
IntuneMAMDataProtectionManager.h | Klasa IntuneMAMDataProtectionManager udostępnia interfejsy API, przy użyciu których aplikacja może zabezpieczać bufory danych na podstawie podanej tożsamości. Tożsamość może być zarządzana przez usługę Intune lub niezarządzana, a zestaw SDK odpowiednio zastosuje szyfrowanie. |

## <a name="implement-save-as-controls"></a>Implementowanie kontrolek Zapisz jako

Usługa Intune umożliwia administratorom IT wybieranie lokalizacji przechowywania, w których zarządzana aplikacja może zapisywać dane. Aplikacje mogą wysyłać zapytania o dozwolone lokalizacje przechowywania do zestawu SDK aplikacji usługi Intune przy użyciu interfejsu API `isSaveToAllowedForLocation` zdefiniowanego w klasie `IntuneMAMPolicy.h`.

Przed zapisaniem danych zarządzanych w magazynie w chmurze lub lokalnie aplikacje muszą sprawdzić za pomocą interfejsu API `isSaveToAllowedForLocation`, czy administrator IT zezwolił na zapisywanie danych w tym miejscu.

W przypadku korzystania z interfejsu API `isSaveToAllowedForLocation` aplikacje muszą przekazać nazwę UPN używaną dla lokalizacji przechowywania, jeśli jest ona dostępna.

### <a name="supported-save-locations"></a>Obsługiwane lokalizacje zapisywania

Interfejs API `isSaveToAllowedForLocation` zawiera stałe umożliwiające sprawdzenie, czy administrator IT zezwolił na zapisywanie danych w następujących lokalizacjach zdefiniowanych w klasie `IntuneMAMPolicy.h`:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Aplikacje powinny używać stałych w elemencie `isSaveToAllowedForLocation`, aby sprawdzać, czy można zapisywać dane w lokalizacjach uznawanych za „zarządzane”, np. w usłudze OneDrive dla Firm, lub „osobiste”. Ponadto należy używać interfejsu API w sytuacjach, w których aplikacja nie może określić, czy lokalizacja jest „zarządzana”, czy „osobista”.

Lokalizacje znane jako „osobiste” są reprezentowane przez stałą `IntuneMAMSaveLocationOther`.

Stałej `IntuneMAMSaveLocationLocalDrive` należy używać, gdy aplikacja zapisuje dane w dowolnej lokalizacji na urządzeniu lokalnym.

## <a name="share-data-via-uiactivityviewcontroller"></a>Udostępnianie danych przy użyciu kontrolera UIActivityViewController

Począwszy od wersji 8.0.2, zestaw SDK aplikacji usługi Intune może filtrować akcje kontrolera `UIActivityViewController`, aby do wyboru były dostępne tylko lokalizacje udostępniania zarządzane przez usługę Intune. To zachowanie będzie uzależnione od zasad transferu danych aplikacji.

### <a name="copy-to-actions"></a>Akcje „Kopiuj do”

W przypadku udostępniania dokumentów przy użyciu kontrolerów `UIActivityViewController` i `UIDocumentInteractionController` system iOS wyświetla akcje „Kopiuj do” dla każdej aplikacji obsługującej otwieranie udostępnianego dokumentu. Aplikacje deklarują obsługiwane przez siebie typy dokumentów za pomocą ustawienia klucza `CFBundleDocumentTypes` w pliku Info.plist. Tej metody udostępniania nie będzie można już używać, jeśli zasady będą zabraniać udostępniania niezarządzanym aplikacjom. Zamiast tego użytkownik będzie musiał dodać do swoich aplikacji rozszerzenie akcji inne niż interfejsu użytkownika i połączyć je z zestawem SDK aplikacji usługi Intune. Rozszerzenie akcji jest jedynie klasą zastępczą. Zestaw SDK wdroży zachowanie udostępniania pliku. Wykonaj następujące czynności:

1. Aplikacja musi mieć zdefiniowany przynajmniej jeden parametr schemeURL w obszarze klucza `CFBundleURLTypes` w pliku Info.plist.

2. Aplikacja i rozszerzenie aplikacji muszą dzielić przynajmniej jedną grupę aplikacji z listy w obszarze tablicy `AppGroupIdentifiers` w obszarze słownika IntuneMAMSettings aplikacji i rozszerzeń.

3. Nazwij rozszerzenie akcji „Otwórz w”, dodając nazwę aplikacji. W zależności od potrzeb zlokalizuj plik Info.plist.

4. Podaj ikonę szablonu rozszerzenia zgodnie z opisem w [dokumentacji dla deweloperów firmy Apple](https://developer.apple.com/ios/human-interface-guidelines/extensions/sharing-and-actions/). Możesz też użyć narzędzia IntuneMAMConfigurator do wygenerowania tych obrazów z katalogu .app aplikacji. Aby to zrobić, uruchom:

    ```bash
    IntuneMAMConfigurator -generateOpenInIcons /path/to/app.app -o /path/to/output/directory
    ```

5. W obszarze IntuneMAMSettings w pliku Info.plist rozszerzenia dodaj ustawienie wartości logicznej o nazwie `OpenInActionExtension` z wartością YES (TAK).

6. Skonfiguruj regułę `NSExtensionActivationRule` do obsługi pojedynczego pliku oraz wszystkich typów z elementu `CFBundleDocumentTypes` aplikacji z prefiksem `com.microsoft.intune.mam`. Jeśli na przykład aplikacja obsługuje public.text i public.image, reguła aktywacji powinna wyglądać następująco:

    ```objc
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.text” ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image”).@count == 1
    ).@count == 1
    ```

### <a name="update-existing-share-and-action-extensions"></a>Aktualizowanie istniejących rozszerzeń udostępniania i akcji

Jeśli aplikacja zawiera już rozszerzenia udostępniania i akcji, regułę `NSExtensionActivationRule` trzeba będzie zmodyfikować, aby zezwolić na typy usługi Intune. Dla każdego typu obsługiwanego przez rozszerzenie dodaj dodatkowy typ poprzedzony prefiksem `com.microsoft.intune.mam`. Jeśli na przykład istniejąca reguła aktywacji wygląda w następujący sposób:  

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data"
    ).@count > 0
).@count > 0
```

Należy ją zmienić na:

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.data
    ).@count > 0
).@count > 0
```

> [!NOTE]
> Narzędzia IntuneMAMConfigurator można użyć do dodania typów usługi Intune do reguły aktywacji. Jeśli istniejąca reguła aktywacji korzysta ze wstępnie zdefiniowanych stałych ciągów (np. NSExtensionActivationSupportsFileWithMaxCount, NSExtensionActivationSupportsText, itp.), składnia predykatu może być dość złożona. Narzędzia IntuneMAMConfigurator można również użyć do konwersji reguły aktywacji ze stałych ciągów do ciągu predykatu podczas dodawania typów usługi Intune.

### <a name="what-the-ui-should-look-like"></a>Jak powinien wyglądać interfejsu użytkownika

Stary interfejs użytkownika:

![Udostępnianie danych — stary interfejs użytkownika udostępniania danych w systemie iOS](./media/app-sdk-ios/sharing-UI-old.png)

Nowy interfejs użytkownika:

![Udostępnianie danych — nowy interfejs użytkownika udostępniania danych w systemie iOS](./media/app-sdk-ios/sharing-UI-new.png)

## <a name="enable-targeted-configuration-appmam-app-config-for-your-ios-applications"></a>Włączanie konfiguracji docelowej (konfiguracja aplikacji APP/MAM) dla aplikacji systemu iOS

Docelowa konfiguracja MAM (znana także jako konfiguracja aplikacji MAM) umożliwia aplikacjom odbieranie danych konfiguracji za pośrednictwem zestawu SDK usługi Intune. Format i odmiany tych danych muszą zostać zdefiniowane i przekazane klientom usługi Intune przez właściciela/dewelopera aplikacji.

Administratorzy usługi Intune mogą przekazywać dane konfiguracji do miejsc docelowych i wdrażać te dane za pośrednictwem witryny Intune Azure Portal i interfejsu API programu Graph usługi Intune. Począwszy od wersji 7.0.1 zestawu SDK aplikacji usługi Intune dla systemu iOS, aplikacje uwzględnione w docelowej konfiguracji MAM mogą otrzymywać dane docelowej konfiguracji MAM za pośrednictwem usługi MAM. Dane konfiguracji aplikacji zostaną przypisane do aplikacji bezpośrednio za pośrednictwem naszej usługi MAM zamiast za pośrednictwem kanału zarządzania urządzeniami mobilnymi (MDM). Zestaw SDK aplikacji usługi Intune udostępnia klasę umożliwiającą uzyskanie dostępu do danych pobranych z tych konsol. Wymagania wstępne to następujące elementy:

* Aby można było uzyskać dostęp do interfejsu użytkownika docelowej konfiguracji MAM, aplikacja musi być zarejestrowana w usłudze MAM usługi Intune. Aby uzyskać więcej informacji, zobacz [Otrzymywanie zasad ochrony aplikacji](#receive-app-protection-policy).

* Uwzględnij element `IntuneMAMAppConfigManager.h` w pliku źródłowym aplikacji.

* Wywołaj element `[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]` w celu pobrania obiektu konfiguracji aplikacji.

* Wywołaj odpowiedni selektor w obiekcie `IntuneMAMAppConfig`. Jeśli na przykład klucz aplikacji jest ciągiem, możesz użyć elementu `stringValueForKey` lub `allStringsForKey`. Zobacz `IntuneMAMAppConfig.h`, aby uzyskać szczegółowy opis zwracanych wartości i warunków błędu.

Aby uzyskać więcej informacji o możliwościach interfejsu API programu Graph, zobacz [Dokumentacja interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/overview).

Więcej informacji na temat tworzenia zasad docelowej konfiguracji aplikacji MAM w systemie iOS można znaleźć w sekcji poświęconej docelowej konfiguracji aplikacji MAM w artykule opisującym [sposób używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](../apps/app-configuration-policies-use-ios.md).

## <a name="telemetry"></a>Telemetria

Domyślnie zestaw SDK aplikacji usługi Intune dla systemu iOS gromadzi dane telemetryczne następujących zdarzeń użycia:

* **Uruchomienie aplikacji**: w celu ułatwienia usłudze Microsoft Intune ustalenia użycia aplikacji z obsługą zarządzania aplikacjami mobilnymi zależnie od typu zarządzania (zarządzanie aplikacjami mobilnymi z zarządzaniem urządzeniami przenośnymi, zarządzanie aplikacjami mobilnymi bez rejestracji w rozwiązaniu do zarządzania urządzeniami przenośnymi itp.).

* **Wywołania rejestracji**: w celu ułatwienia usłudze Microsoft Intune ustalenia współczynnika operacji zakończonych powodzeniem i innych metryk wydajności wywołań rejestracji inicjowanych po stronie klienta.

* **Akcje usługi Intune**: aby ułatwić diagnozowanie problemów i zapewnić funkcjonalność usługi Intune, zbierane są informacje o akcjach zestawu SDK usługi Intune.

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

  ![Zestaw SDK aplikacji usługi Intune dla systemu iOS: proces ustalania tożsamości](./media/app-sdk-ios/ios-thread-identities.png)

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

### <a name="turn-on-multi-identity"></a>Włączanie wielu tożsamości

Domyślnie aplikacje są traktowane jako aplikacje mające jedną tożsamość. Zestaw SDK ustawia tożsamość procesu na zarejestrowanego użytkownika. Aby włączyć obsługę wielu tożsamości, dodaj ustawienie typu wartość logiczna o nazwie `MultiIdentity` z wartością „YES” (Tak) do słownika IntuneMAMSettings w pliku Info.plist aplikacji.

> [!NOTE]
> Po włączeniu obsługi wielu tożsamości tożsamość procesu, tożsamość interfejsu użytkownika i tożsamości wątku są ustawione na wartość zero. Aplikacja jest odpowiedzialna za ich odpowiednie ustawienie.

### <a name="switch-identities"></a>Przełączanie tożsamości

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

### <a name="are-all-of-the-apis-addressable-through-native-swift-or-the-objective-c-and-swift-interoperability"></a>Czy do wszystkich interfejsów API można odwoływać się za pomocą natywnego języka Swift lub współdziałania języków Objective-C i Swift?

Interfejsy API zestawu SDK aplikacji usługi Intune są dostępne wyłącznie w języku Objective-C i nie obsługują **natywnego** języka Swift. Wymagane jest współdziałanie języków Swift i Objective-C.

### <a name="do-all-users-of-my-application-need-to-be-registered-with-the-app-we-service"></a>Czy wszyscy użytkownicy mojej aplikacji muszą być zarejestrowani w usłudze APP-WE?

Nie. W rzeczywistości tylko konta służbowe powinny być rejestrowane przy użyciu zestawu SDK aplikacji usługi Intune. Aplikacje są odpowiedzialne za określenie, czy konto jest używane w kontekście miejsca pracy lub nauki.

### <a name="what-about-users-that-have-already-signed-in-to-the-application-do-they-need-to-be-enrolled"></a>Co z użytkownikami, którzy już zalogowali się do aplikacji? Czy muszą zostać zarejestrowani?

Aplikacja jest odpowiedzialna za rejestrowanie użytkowników po ich pomyślnym uwierzytelnieniu. Aplikacja jest również odpowiedzialna za zarejestrowanie wszelkich kont istniejących przed zaimplementowaniem w aplikacji funkcji zarządzania aplikacjami mobilnymi bez zarządzania urządzeniami przenośnymi.

W tym celu aplikacja powinna korzystać z metody `registeredAccounts:`. Ta metoda zwraca element NSDictionary zawierający wszystkie konta zarejestrowane w usłudze zarządzania aplikacjami mobilnymi w usłudze Intune. Jeśli jakiekolwiek konta istniejące w aplikacji nie są obecne na liście, aplikacja powinna zarejestrować te konta za pomocą metody `registerAndEnrollAccount:`.

### <a name="how-often-does-the-sdk-retry-enrollments"></a>Jak często zestaw SDK ponawia próby rejestracji?

Zestaw SDK będzie automatycznie ponawiać próbę rejestracji dla wszystkich rejestracji wcześniej zakończonych niepowodzeniem co 24 godziny. Robi to w celu upewnienia się, że jeśli organizacja użytkownika włączyła zarządzanie aplikacjami mobilnymi po zalogowaniu się użytkownika do aplikacji, użytkownik zostanie pomyślnie zarejestrowany i otrzyma zasady.

Zestaw SDK przestanie ponawiać próby po wykryciu, że użytkownik pomyślnie zarejestrował aplikację. Dzieje się tak, ponieważ w danym momencie tylko jeden użytkownik może zarejestrować aplikację. Jeśli użytkownik zostanie wyrejestrowany, ponowne próby rozpoczną się ponownie z tym samym 24-godzinnym interwałem.

### <a name="why-does-the-user-need-to-be-deregistered"></a>Dlaczego użytkownik musi zostać wyrejestrowany?

Zestaw SDK będzie okresowo wykonywał następujące akcje w tle:

* Jeśli aplikacja nie jest jeszcze zarejestrowana, co 24 godziny będzie próbował zarejestrować wszystkie zarejestrowane konta.
* Jeśli aplikacja jest zarejestrowana, zestaw SDK co 8 godzin będzie sprawdzał dostępność aktualizacji zasad zarządzania aplikacjami mobilnymi.

Wyrejestrowanie użytkownika powiadamia zestaw SDK, że użytkownik nie będzie już używał aplikacji i że można zatrzymać wszystkie zdarzenia okresowe dla konta tego użytkownika. Spowoduje to również wykonanie wyrejestrowania aplikacji i selektywnego czyszczenia danych, jeśli jest to konieczne.

### <a name="should-i-set-the-dowipe-flag-to-true-in-the-deregister-method"></a>Czy flagę doWipe należy ustawić na wartość true w metodzie deregister?

Ta metoda powinna być wywoływana przed wylogowaniem użytkownika z aplikacji.  Jeśli w ramach wylogowywania dane użytkownika są usuwane z aplikacji, można ustawić flagę `doWipe` na wartość false. Jednak jeśli aplikacja nie usuwa danych użytkownika, należy ustawić flagę `doWipe` na wartość true, aby zestaw SDK mógł usunąć te dane.

### <a name="are-there-any-other-ways-that-an-application-can-be-un-enrolled"></a>Czy istnieją inne sposoby wyrejestrowania aplikacji?

Tak, administrator IT może wysłać polecenie selektywnego czyszczenia danych do aplikacji. Spowoduje to wyrejestrowanie użytkownika i wyczyszczenie jego danych. Zestaw SDK automatycznie obsługuje ten scenariusz i wysyła powiadomienie za pośrednictwem metody delegata wyrejestrowania.

### <a name="is-there-a-sample-app-that-demonstrates-how-to-integrate-the-sdk"></a>Czy istnieje przykładowa aplikacja, która demonstruje sposób integracji zestawu SDK?

Tak! Niedawno odnowiliśmy naszą przykładową aplikację typu open-source [Wagr dla systemu iOS](https://github.com/Microsoft/Wagr-Sample-Intune-iOS-App). Aplikacja Wagr obsługuje teraz zasady ochrony aplikacji przy użyciu zestawu SDK aplikacji usługi Intune.

### <a name="how-can-i-troubleshoot-my-app"></a>Jak mogę rozwiązać problem z moją aplikacją?

Zestaw SDK usługi Intune dla systemu iOS 9.0.3 i nowszych wersji obsługuje możliwość dodawania konsoli diagnostyki w aplikacji mobilnej na potrzeby testowania zasad i błędów rejestrowania. `IntuneMAMDiagnosticConsole.h` definiuje interfejs klasy `IntuneMAMDiagnosticConsole`, którego deweloperzy mogą używać do wyświetlania konsoli diagnostyki usługi Intune. Umożliwia to użytkownikom końcowym lub deweloperom podczas testu zbieranie i udostępnianie dzienników usługi Intune w celu ułatwienia zdiagnozowania ewentualnych problemów. Ten interfejs API jest opcjonalny dla integratorów.

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
