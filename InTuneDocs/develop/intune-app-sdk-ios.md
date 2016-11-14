---
title: "Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b998728b3db60d10cadbcd34b5412fa76cb586f
ms.openlocfilehash: ddc47ef5846bf448cf0de1e57b527e8ec4c562cc


---

# Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu iOS

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do przewodnika zestawu SDK aplikacji usługi Intune](intune-app-sdk-get-started.md), w którym omówiono sposoby przygotowania do integracji na poszczególnych obsługiwanych platformach.* 

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu iOS możesz wdrożyć funkcje zarządzania aplikacjami mobilnymi (MAM) w swojej aplikacji dla systemu iOS. Aplikacja z obsługą funkcji MAM jest zintegrowana z zestawem SDK aplikacji usługi Intune i pozwala administratorom IT wdrażać zasady w aplikacji mobilnej, gdy jest ona aktywnie zarządzana przez usługę Intune.


# Zawartość zestawu SDK 

Zestaw SDK aplikacji usługi Intune dla systemu iOS zawiera bibliotekę statyczną, pliki zasobów, nagłówki interfejsu API, listę właściwości ustawień debugowania i narzędzie Configurator. W większości konfiguracji wymuszania zasad wystarczy dołączyć pliki zasobów do aplikacji mobilnych, które będą statycznie łączyć się z bibliotekami. Zaawansowane funkcje MAM usługi Intune są wymuszane za pośrednictwem interfejsów API.

W tym przewodniku omówiono użycie następujących składników zestawu SDK aplikacji usługi Intune dla systemu iOS:

* **libIntuneMAM.a**: biblioteka statyczna zestawu SDK aplikacji usługi Intune. Jeśli aplikacja nie używa rozszerzeń, należy połączyć tę bibliotekę z projektem, aby umożliwić zarządzanie aplikacją za pomocą zarządzania aplikacjami mobilnymi w usłudze Intune. Instrukcje znajdują się w sekcji „Kompilowanie aplikacji za pomocą zestawu SDK aplikacji usługi Intune”.

* **IntuneMAM.framework**: struktura zestawu SDK aplikacji usługi Intune. Tę strukturę należy połączyć z projektem, aby umożliwić zarządzanie aplikacją za pomocą zarządzania aplikacjami mobilnymi w usłudze Intune. Jeśli aplikacja używa rozszerzeń, można użyć tej struktury zamiast biblioteki statycznej, aby projekt nie tworzył wielu kopii biblioteki statycznej.

* **IntuneMAMResources.Bundle**: pakiet zawierający zasoby, na których bazuje zestaw SDK. 

* **Nagłówki**: udostępnia interfejsy API zestawu SDK aplikacji usługi Intune. Jeśli korzystasz z interfejsu API, musisz uwzględnić plik nagłówka zawierający interfejs API. Następujące pliki nagłówków obejmują wywołania funkcji API wymagane do włączenia funkcji zestawu SDK aplikacji usługi Intune. 
    
    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h 


# Jak działa zestaw SDK aplikacji usługi Intune

Zestaw SDK aplikacji usługi Intune dla systemu iOS opracowano po to, aby umożliwić dodawanie funkcji zarządzania do aplikacji systemu iOS przy minimalnych zmianach w kodzie. Im mniej zmian w kodzie, tym krótszy czas wprowadzenia na rynek, ale nadal z zagwarantowaniem spójności i stabilności aplikacji mobilnej. 

Aplikacja musi być połączona z biblioteką statyczną i zawierać pakiet zasobów. Plik MAMDebugSettings.plist jest opcjonalny i może być uwzględniony w pakiecie w celu symulowania zasad MAM, stosowanych w odniesieniu do aplikacji bez konieczności wdrażania aplikacji za pomocą usługi Microsoft Intune. Ponadto w kompilacjach do debugowania zasady w pliku MAMDebugSettings.plist można stosować, przesyłając plik do katalogu dokumentów aplikacji za pomocą funkcji udostępniania plików programu iTunes.

# Kompilowanie aplikacji mobilnej przy użyciu zestawu SDK 

Wykonaj poniższe kroki, aby włączyć zestaw SDK aplikacji usługi Intune:

1. **Opcja 1**: ustanów połączenie z biblioteką `libIntuneMAM.a`, wykonując następujące czynności:

    Przeciągnij bibliotekę `libIntuneMAM.a` i upuść ją na liście „Linked Frameworks and Libraries” (Połączone struktury i biblioteki) obiektu docelowego projektu.
    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS — połączone struktury i biblioteki](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png) 

    **Uwaga**: Jeśli zamierzasz przekazać aplikację do sklepu z aplikacjami, użyj wersji biblioteki `libIntuneMAM.a`, która została skompilowana dla wersji wydanej, a nie wersji do debugowania. Wersja wydana będzie znajdować się w folderze „release” (wydanie). Wersja do debugowania generuje szczegółowe dane wyjściowe, co ułatwia rozwiązywanie problemów z zestawem SDK aplikacji usługi Intune.
    
    **Opcja 2**: połącz strukturę `IntuneMAM.framework` z projektem. Przeciągnij bibliotekę `IntuneMAM.framework` i upuść ją na liście „Linked Frameworks and Libraries” (Połączone struktury i biblioteki) obiektu docelowego projektu.
    
    **Uwaga**: W przypadku używania struktury należy ręcznie usunąć architektury symulatora z uniwersalnej struktury przed przesłaniem aplikacji do sklepu z aplikacjami. Zobacz sekcję o nazwie „Przesyłanie aplikacji do sklepu z aplikacjami”.

2. Dodaj następujące struktury systemu iOS do projektu:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    **Uwaga**: Jeśli aplikacja jest przeznaczona dla systemu iOS7, należy ustawić wartość „Optional” (Opcjonalne) atrybutu „Status” (Stan) struktury `LocalAuthentication.framework`. Jeśli wartość atrybutu „Status” (Stan) nie jest ustawiona, próba uruchomienia aplikacji w systemie iOS7 zakończy się niepowodzeniem.

    **Uwaga**: W środowisku Xcode 7 zastąpiono rozszerzenia nazw `.dylib` rozszerzeniami `.tbd`.

3. Dodaj pakiet zasobów `IntuneMAMResources.bundle` do projektu, przeciągając pakiet zasobów w obszarze „Copy Bundle Resources” (Kopiuj pakiety zasobów) w sekcji „Build Phases” (Fazy kompilacji).
![Zestaw SDK aplikacji usługi Intune dla systemu iOS — kopiowanie pakietów zasobów](../media/intune-app-sdk-ios-copy-bundle-resources.png)
 
4. Dodaj składnik `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do jednej z następujących pozycji, zastępując element `{PATH_TO_LIB}` lokalizacją zestawu SDK aplikacji usługi Intune:
    * ustawienie konfiguracji kompilacji `OTHER_LDFLAGS` projektu 
    * pozycja „Other Linker Flags” (Inne flagi konsolidatora) w interfejsie użytkownika<br>

    **Uwaga**: Aby ustalić wartość elementu `PATH_TO_LIB`, wybierz plik `libIntuneMAM.a` , a następnie wybierz polecenie „Get Info” (Pobierz informacje) z menu „File” (Plik). Skopiuj i wklej informacje z pola „Where” (Gdzie; ścieżka) z sekcji „General” (Ogólne) okna „Info” (Informacje).

5. Jeśli w pliku info.plist Twojej aplikacji mobilnej zdefiniowano główny obiekt Nib lub Storyboard, usuń pola pliku Main Storyboard lub Main Nib. Dodaj usunięte uprzednio wartości Storyboard lub Nib w nowym słowniku o nazwie IntuneMAMSettings z następującymi nazwami kluczy zgodnie z wymaganiami:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    
   **Uwaga:**Jeśli w pliku info.plist Twojej aplikacji mobilnej nie zdefiniowano głównego obiektu Nib lub Storyboard, te ustawienia **nie są wymagane**. 

    **Uwaga**: Można przeglądać plik info.plist w formacie nieprzetworzonym (aby zobaczyć nazwy kluczy), klikając prawym przyciskiem myszy w dowolnym miejscu w treści dokumentu i zmieniając typ widoku na „Show Raw Keys/Values” (Pokaż nieprzetworzone klucze/wartości).

6. Włącz udostępnianie łańcucha kluczy (jeśli nie zostało jeszcze włączone), klikając pozycję „Capabilities” (Możliwości) w każdym obiekcie docelowym projektu i włączając przełącznik „Keychain Sharing” (Udostępnianie łańcucha kluczy). Udostępnianie łańcucha kluczy jest wymagane do przejścia do następnego kroku.

    **Uwaga**: Twój plik inicjowania obsługi musi obsługiwać nowe wartości udostępniania łańcucha kluczy. Grupy dostępu łańcucha kluczy powinny obsługiwać symbol wieloznaczny. Można to sprawdzić, otwierając plik .mobileprovision w edytorze tekstów, wyszukując frazę „keychain-access-groups” i sprawdzając, czy używany jest symbol wieloznaczny, na przykład: 
    ```
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```
7. Po włączeniu udostępniania łańcucha kluczy wykonaj następujące kroki, aby utworzyć oddzielną grupę dostępu, w której będą przechowywane dane zestawu SDK aplikacji usługi Intune. Można utworzyć grupę dostępu łańcucha kluczy za pomocą interfejsu użytkownika lub pliku uprawnień:

    Tworzenie grupy dostępu łańcucha kluczy za pomocą interfejsu użytkownika: 
    
    * Jeśli dla Twojej aplikacji mobilnej nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako pierwszą grupę.
    * Dodaj udostępnioną grupę łańcucha kluczy `com.microsoft.intune.mam`. Ta grupa dostępu jest używana przez zestaw SDK aplikacji usługi Intune do przechowywania danych.  
    * Dodaj grupę `com.microsoft.adalcache` do Twoich istniejących grup dostępu. 

    ![Zestaw SDK aplikacji usługi Intune dla systemu iOS — udostępnianie łańcucha kluczy](../media/intune-app-sdk-ios-keychain-sharing.png) 

    Jeśli zamiast zwykłego interfejsu użytkownika używasz pliku uprawnień do utworzenia grupy dostępu łańcucha kluczy, konieczne będzie dołączenie wartości `$(AppIdentifierPrefix)` jako prefiksu grupy dostępu łańcucha kluczy w pliku uprawnień. Na przykład:  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam` 
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    **Uwaga**: Plik uprawnień jest plikiem XML unikatowym dla Twojej aplikacji mobilnej, używanym do określania specjalnych uprawnień i możliwości w aplikacji systemu iOS.

8. Jeśli w pliku info.plist aplikacji zdefiniowano schematy adresów URL, dodaj kolejny schemat z sufiksem `-intunemam` dla każdego schematu URL.

9. W przypadku aplikacji mobilnych opracowywanych dla systemu iOS 9 i nowszych wymagane jest uwzględnienie każdego protokołu, przekazywanego przez aplikację do procedury `UIApplication canOpenURL`, w tabeli `LSApplicationQueriesSchemes` pliku Info.plist file aplikacji. Ponadto dla każdego protokołu uwzględnionego na liście należy dodać nowy protokół i dołączyć do jego nazwy sufiks `-intunemam`. W tabeli należy również uwzględnić pozycje `http-intunemam`, `https-intunemam`i `ms-outlook-intunemam` . 

10. Jeśli w uprawnieniach aplikacji zdefiniowano grupy aplikacji, dodaj te grupy do słownika IntuneMAMSettings w kluczu `AppGroupIdentitifiers` jako tabelę ciągów.

11. Połącz swoją aplikację mobilną z biblioteką uwierzytelniania usługi Azure Directory (ADAL). Biblioteka ADAL dla języka Objective C jest [dostępna w serwisie Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Uwaga**: Zestaw SDK aplikacji usługi Intune był testowany z kodem ADAL broker branch w wersji z dnia 2015-06-19. Upewnij się, że połączenie jest ustanawiane z najnowszą/działającą wersją biblioteki ADAL.

12. Uwzględnij pakiet zasobów `ADALiOSBundle.bundle` w projekcie, przeciągając go do obszaru „Copy Bundle Resources” (Kopiuj pakiety zasobów) w sekcji „Build Phases” (Fazy kompilacji).

13. Użyj opcji konsolidatora `-force_load PATH_TO_ADAL_LIBRARY` podczas ustanawiania połączenia z biblioteką.

    Dodaj składnik `-force_load {PATH_TO_LIB}/libADALiOS.a` do ustawienia konfiguracji kompilacji `OTHER_LDFLAGS` lub pozycji „Other Linker Flags” (Inne flagi konsolidatora) w interfejsie użytkownika. `PATH_TO_LIB` należy zastąpić lokalizacją plików binarnych biblioteki ADAL. 

# Konfigurowanie ustawień biblioteki uwierzytelniania usługi Azure Directory (ADAL) w aplikacji 

Zestaw SDK aplikacji usługi Intune używa biblioteki ADAL dla swojego scenariusza uwierzytelniania i uruchamiania warunkowego. Używa również biblioteki ADAL do zarejestrowania tożsamości użytkownika w usłudze zarządzania aplikacjami mobilnymi dla scenariuszy zarządzania bez rejestracji urządzenia. 

Zazwyczaj biblioteka ADAL wymaga od aplikacji zarejestrowania się i uzyskania unikatowego identyfikatora (ClientID) oraz innych identyfikatorów w celu zagwarantowania bezpieczeństwa tokenów przyznanych aplikacji. Zestaw SDK aplikacji usługi Intune używa domyślnych wartości rejestracji podczas kontaktowania się z usługą Azure Active Directory.  

Jeśli aplikacja używa biblioteki ADAL w swoim scenariuszu uwierzytelniania, musi użyć jej istniejących wartości rejestracji i przesłonić wartości domyślne zestawu SDK aplikacji usługi Intune, aby zapobiec dwukrotnemu monitowaniu użytkowników o uwierzytelnienie (przez zestaw SDK aplikacji usługi Intune i przez aplikację). 

##Biblioteka ADAL — często zadawane pytania

**Z których plików binarnych biblioteki ADAL mam korzystać?** 

Zestaw SDK aplikacji Intune aktualnie używa gałęzi brokera [biblioteki ADAL w witrynie GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc) w celu obsługi aplikacji, które wymagają dostępu warunkowego (i w związku z tym korzystają z aplikacji Microsoft Authenticator). Zestaw SDK jest jednak nadal zgodny z główną gałęzią biblioteki ADAL. Skorzystaj z gałęzi, która jest odpowiednia dla danej aplikacji.

**Jak utworzyć połączenie z plikami binarnymi biblioteki ADAL?**

Dodaj składnik `-force_load {PATH_TO_LIB}/libADALiOS.a` do ustawienia konfiguracji kompilacji `OTHER_LDFLAGS` lub pozycji „Other Linker Flags” (Inne flagi konsolidatora) w interfejsie użytkownika. `PATH_TO_LIB` należy zastąpić lokalizacją plików binarnych biblioteki ADAL. Ponadto musisz skopiować pakiet ADAL do swojej aplikacji.  

Aby uzyskać więcej szczegółów, zobacz instrukcje dotyczące [biblioteki ADAL w witrynie Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).


**Jak udostępnić pamięć podręczną biblioteki ADAL innym aplikacjom podpisanym za pomocą tego samego profilu aprowizacji?**

Jeśli dla Twojej aplikacji nie zdefiniowano żadnych grup dostępu łańcucha kluczy, dodaj identyfikator pakietu aplikacji jako pierwszą grupę.
Włącz logowanie jednokrotne do biblioteki ADAL, dodając grupy dostępu `com.microsoft.adalcache` i `com.microsoft.workplacejoin` w uprawnieniach do łańcucha kluczy. 

W przypadku ustawiania w sposób jawny grupy łańcucha kluczy udostępnionej pamięci podręcznej biblioteki ADAL upewnij się, że jest ona ustawiona na wartość `<app_id_prefix>.com.microsoft.adalcache`. Biblioteka ADAL ustawi tę grupę za Ciebie, chyba że ją zastąpisz. Jeśli chcesz określić niestandardową grupę łańcucha kluczy w celu zastąpienia grupy `com.microsoft.adalcache`, określić ją w pliku Info.plist w obszarze „IntuneMAMSettings” przy użyciu klucza `ADALCacheKeychainGroupOverride`.

**Jak wymusić, aby zestaw SDK aplikacji Intune używał ustawień biblioteki ADAL, z których moja aplikacja już korzysta?** 

Jeśli aplikacja używa już biblioteki ADAL, zobacz poniższą sekcję dotyczącą słownika IntuneMAMSettings, aby uzyskać informacje o wprowadzaniu poniższych ustawień:  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**Jak przełączać się między środowiskiem produkcyjnym i wewnętrznym środowiskiem testowym usługi AAD?**

Ustawienie `AadAuthorityURI` w pliku `MAMPolicies.plist` może służyć do określania środowiska usługi AAD używanego dla wywołań biblioteki ADAL. Obecnie jest ono ustawione w celu domyślnego korzystania z wstępnego środowiska produkcyjnego, chyba że to ustawienie zostanie zastąpione.
    
Na potrzeby testowania wstępnego środowiska produkcyjnego można użyć przełącznika środowiska czasu kompilacji lub przełącznika środowiska uruchomieniowego. 

W przypadku przełącznika środowiska czasu kompilacji adresów URL i usługi AAD usługi zarządzania aplikacjami mobilnymi ustaw flagę wartości logicznej `UsePPE` na wartość true w pliku MAMEnvironment.plist (**uwaga**: nie można tego zrobić za pośrednictwem pliku Info.plist). 

W przypadku przełącznika środowiska wykonawczego ustaw `com.microsoft.intune.mam.useppe` w ustawieniach domyślnych użytkownika standardowego na wartość „1", aby użyć wstępnego środowiska produkcyjnego. Spowoduje to zastąpienie istniejącego ustawienia `com.microsoft.intune.mam.AADAuthorityEnvironment`. 

**Jak zastąpić adres URL urzędu usługi AAD adresem URL specyficznym dla dzierżawy dostarczonym w środowisku uruchomieniowym?** 

Ustaw właściwość `aadAuthorityUriOverride` w wystąpieniu klasy IntuneMAMPolicyManager.

**Uwaga**: będzie to konieczne w scenariuszu zarządzania aplikacjami mobilnymi (MAM) bez rejestracji urządzeń, aby umożliwić zestawowi SDK ponowne używanie tokenu odświeżania biblioteki ADAL pobranego przez aplikację.

**Uwaga:** zestaw SDK będzie nadal używał tego adresu URL urzędu na potrzeby odświeżania zasad i wszystkich kolejnych żądań rejestracji, chyba że jego wartość zostanie wyczyszczona lub zmieniona.  Dlatego ważne jest wyczyszczenie tej wartości po wylogowaniu się użytkownika firmowego z aplikacji i zresetowanie jej podczas logowania nowego użytkownika firmowego.


**Co zrobić, jeśli moja aplikacja sama korzysta z biblioteki ADAL do uwierzytelniania?**

Poniższe kroki są wymagane, jeśli aplikacja już używa biblioteki ADAL do uwierzytelniania. Jeśli aplikacja nie korzysta z biblioteki ADAL, przejrzyj sekcję dotyczącą sposobu rejestrowania przy użyciu usługi Intune, jeśli aplikacja nie używa biblioteki ADAL.

* W słowniku IntuneMAMSettings z nazwą klucza `ADALClientId` w pliku Info.plist projektu określ identyfikator ClientID, który ma być używany dla wywołań biblioteki ADAL. 

* W słowniku IntuneMAMSettings z nazwą klucza `ADALRedirectUri` w pliku Info.plist projektu określ identyfikator URI przekierowania, który ma być używany dla wywołań biblioteki ADAL. Konieczne może być również określenie schematu `ADALRedirectScheme` zależnie od formatu identyfikatora URI przekierowania aplikacji.



#Rejestrowanie aplikacji przy użyciu usługi zarządzania aplikacjami mobilnymi 

## Korzystanie z interfejsów API
Zestaw SDK aplikacji usługi Intune umożliwia teraz aplikacjom dla systemu iOS otrzymywanie zasad zarządzania aplikacjami mobilnymi z usługi Intune bez konieczności rejestracji w rozwiązaniu do zarządzania urządzeniami przenośnymi w usłudze Intune. Na potrzeby obsługi tej nowej funkcji zestaw SDK udostępnia nowe interfejsy API, które umożliwiają aplikacjom odbieranie zasad zarządzania aplikacjami mobilnymi. Aby korzystać z nowych interfejsów API, wykonaj następujące kroki:

1. Użyj najnowszej wersji zestawu SDK aplikacji usługi Intune, która obsługuje zarządzanie aplikacjami z lub bez rejestracji urządzeń. Jeśli aplikacja korzystała ze starszej wersji zestawu SDK bez tej funkcji, należy zaktualizować bibliotekę zarządzania aplikacjami mobilnymi usługi Intune, a także zaktualizować folder Headers (Nagłówki) przy użyciu nagłówków z najnowszego zestawu SDK.

2. Dodaj element IntuneMAMEnrollment.h do wszystkich plików, które będą wywoływać interfejsy API. 

3. Na potrzeby testowania wstępnego środowiska produkcyjnego można uwzględnić użycie przełącznika środowiska czasu kompilacji lub przełącznika środowiska uruchomieniowego. 

    W przypadku przełącznika środowiska czasu kompilacji adresów URL i usługi AAD usługi zarządzania aplikacjami mobilnymi ustaw flagę wartości logicznej `UsePPE` na wartość true w pliku MAMEnvironment.plist (**uwaga**: nie można tego zrobić za pośrednictwem pliku Info.plist). 

    W przypadku przełącznika środowiska wykonawczego ustaw `com.microsoft.intune.mam.useppe` w ustawieniach domyślnych użytkownika standardowego na wartość „1", aby użyć wstępnego środowiska produkcyjnego. Spowoduje to zastąpienie istniejącego ustawienia `com.microsoft.intune.mam.AADAuthorityEnvironment`. 


##Rejestrowanie kont 

Aplikacja może odbierać zasady zarządzania aplikacjami mobilnymi z usługi Intune, jeśli jest zarejestrowana w imieniu określonego konta użytkownika.  Aplikacja odpowiada za zarejestrowanie każdego nowo zalogowanego użytkownika w zestawie SDK aplikacji usługi Intune.  Po uwierzytelnieniu nowego konta użytkownika aplikacja powinna wywołać metodę `registerAndEnrollAccount` znalezioną w elemencie Headers/IntuneMAMEnrollment.h: 

```
/** 


 *  This method will add the account to the list of registered accounts. 
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK 
 */ 

(void)registerAndEnrollAccount:(NSString *)identity; 

```
Przez wywołanie powyższej metody zestaw SDK zarejestruje konto użytkownika i spróbuje zarejestrować aplikację w imieniu tego konta.  Jeśli z jakiegokolwiek powodu rejestracja nie powiedzie się, zestaw SDK automatycznie ponowi próbę rejestracji po upływie 24 godzin.  Dla celów debugowania aplikacja może odbierać powiadomienia, za pośrednictwem delegata, o wynikach żądań rejestracji (zobacz szczegółowy poniżej).

Po wywołaniu tego interfejsu API aplikacja może kontynuować normalne działanie.  Jeśli rejestracja powiedzie się, zestaw SDK powiadomi użytkownika, że wymagane jest ponowne uruchomienie aplikacji.  Wtedy użytkownik może natychmiast ponownie uruchomić aplikację.


##Wyrejestrowywanie kont 


Przed wylogowaniem użytkownika z aplikacji aplikacja powinna wyrejestrować użytkownika z zestawu SDK.  Dzięki temu: 

1. Nie będą już podejmowane ponowne próby rejestracji dla tego konta użytkownika. 
2. Jeśli użytkownik pomyślnie zarejestrował aplikację, użytkownik i aplikacja zostaną wyrejestrowani z usługi zarządzania aplikacjami mobilnymi usługi Intune, a zasady zarządzania aplikacjami mobilnymi zostaną usunięte.
3. Opcjonalnie można zainicjować selektywne czyszczenie danych, aby zapewnić usunięcie wszelkich danych związanych z miejscem pracy lub szkołą. 

Zanim użytkownik zostanie wylogowany, aplikacja powinna wywołać następujący interfejs API znaleziony w elemencie Headers/IntuneMAMEnrollment.h: 

```
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

Ta metoda musi być wywoływana przed usunięciem tokenów usługi AAD konta użytkownika.  Zestaw SDK potrzebuje tokenu aplikacji użytkownika, aby wysyłać określone żądania do usługi zarządzania aplikacjami mobilnymi w usłudze Intune w imieniu użytkownika. 

Jeśli aplikacja usunie dane służbowe użytkownika samodzielnie, flagę `doWipe` można ustawić na wartość false.  W przeciwnym razie zestaw SDK może inicjować dla aplikacji selektywne czyszczenie danych, co spowoduje wywołanie delegata selektywnego czyszczenia danych aplikacji. 

```
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES]; 
```


##Rejestrowanie bez wcześniejszego zalogowania 

Aplikacja, która nie loguje użytkownika za pomocą usługi Azure Active Directory, może nadal otrzymywać zasady zarządzania aplikacjami mobilnymi z usługi Intune, wywołując poniższy interfejs API, aby zestaw SDK obsłużył to uwierzytelnianie. Aplikacja powinna używać tego interfejsu, jeśli nie uwierzytelniła użytkownika za pomocą usługi AAD, ale nadal musi on pobrać zasady zarządzania aplikacjami mobilnymi, aby chronić swoje dane w aplikacji — na przykład jeśli do logowania w aplikacji jest używana inna usługa uwierzytelniania albo aplikacja w ogóle nie obsługuje logowania. Aby to zrobić, aplikacja powinna wywołać metodę `loginAndEnrollAccount` znalezioną w elemencie Headers/IntuneMAMEnrollment.h:

```
/** 
 *  Creates an enrollment request which is started immediately. 
 *  If no token can be retrieved for the identity, the user will be prompted 
 *  to enter their credentials, after which enrollment will be retried. 
 *  @param identity The UPN of the account to be logged in and enrolled. 
 */ 
 (void)loginAndEnrollAccount: (NSString *)identity; 

```
Przez wywołanie tej metody zestaw SDK będzie monitował użytkownika o poświadczenia, jeśli nie można znaleźć istniejącego tokenu, a następnie spróbuje zarejestrować aplikację w imieniu tego konta. Metoda może być wywoływana z tożsamością „zero” — w tym przypadku zestaw SDK zarejestruje istniejącego użytkownika zarządzania aplikacjami mobilnymi na urządzeniu lub będzie monitować użytkownika o nazwę użytkownika, jeśli nie znajdzie istniejącego użytkownika. 

W razie niepowodzenia rejestracji aplikacja powinna rozważyć wywołanie tego interfejsu API ponownie w przyszłości, w zależności od szczegółów błędu. Aplikacja może otrzymywać powiadomienia, za pośrednictwem delegata, o wynikach żądań rejestracji (zobacz szczegóły). 

Po wywołaniu tego interfejsu API aplikacja może kontynuować normalne działanie.  Jeśli rejestracja powiodła się, zestaw SDK powiadomi użytkownika, że wymagane jest ponowne uruchomienie aplikacji, tak jak pokazano w powyższej sekcji dotyczącej rejestrowania kont. 

##Informacje o debugowaniu 

Aplikacja może odbierać powiadomienia debugowania dotyczące następujących żądań do usługi zarządzania aplikacjami mobilnymi usługi Intune: 

 - żądania rejestracji 
 - żądania aktualizacji zasad 
 - żądania wyrejestrowania 

Powiadomienia są prezentowane za pomocą metod obiektów delegowanych, które znajdują się w elemencie Headers/IntuneMAMEnrollmentDelegate.h: 

```
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

Te metody obiektów delegowanych zwracają obiekt ```IntuneMAMEnrollmentStatus```, który zawiera następujące informacje: 

- Tożsamość konta skojarzona z żądaniem 
- Kod stanu wskazujący wynik żądania 
- Ciąg błędu z opisem kodu stanu 
- Obiekt NSError 

Ten obiekt jest zdefiniowany w elemencie Headers/IntuneMAMEnrollmentStatus.h wraz z konkretnymi kodami stanu, które mogą być zwrócone. 

Należy zauważyć, że te informacje służą do celów debugowania i żadna logika biznesowa aplikacji nie powinna być oparta na tych powiadomieniach.  Chodzi o to, że aplikacja może wysyłać te informacje do usługi telemetrii na potrzeby debugowania lub monitorowania. 


##Przykładowy kod 

Poniżej przedstawiono przykładowe implementacje metod delegata: 

```
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


##Ponowne uruchomienie aplikacji 

Po pierwszym odebraniu zasad zarządzania aplikacjami mobilnymi aplikacja będzie musiała zostać ponownie uruchomiona, aby zastosować wymagane punkty zaczepienia.  W celu powiadamiania aplikacji o konieczności wykonania ponownego uruchomienia zestaw SDK udostępnia metody delegata w elemencie Headers/IntuneMAMPolicyDelegate.h. 
```
 - (BOOL) restartApplication 
```
Wartość zwracana przez tę metodę poinformuje zestaw SDK, czy aplikacja będzie obsługiwać wymagane ponowne uruchomienie.   

 - Jeśli zwracana jest wartość true, aplikacja będzie odpowiedzialna za obsługę ponownego uruchomienia.   
 - Jeśli zwracana jest wartość false, zestaw SDK uruchomi ponownie aplikację po powrocie tej metody.  Zestaw SDK natychmiast wywoła okno dialogowe informujące użytkownika, że aplikacja musi zostać ponownie uruchomiona. 

#Implementowanie kontrolek Zapisz jako

Usługa Intune umożliwia administratorom IT wybieranie lokalizacji przechowywania, w których zarządzana aplikacja może zapisywać dane. Aplikacje mogą wysyłać zapytania do zestawu SDK aplikacji usługi Intune przy użyciu interfejsu API **isSaveToAllowedForLocation**.

Przed zapisaniem zarządzanych danych w magazynie w chmurze lub lokalizacji lokalnej aplikacje muszą sprawdzić interfejs API **isSaveToAllowedForLocation**, aby dowiedzieć się, czy administrator IT zezwolił na zapisywanie danych w tym miejscu.

W przypadku korzystania z interfejsu API **isSaveToAllowedForLocation** aplikacje muszą przekazać nazwę UPN używaną dla lokalizacji przechowywania, jeśli jest ona dostępna.

##Obsługiwane lokalizacje

Interfejs API **isSaveToAllowedForLocation** zapewnia stałe do sprawdzania następujących lokalizacji:

* IntuneMAMSaveLocationOther 
* IntuneMAMSaveLocationOneDriveForBusiness 
* IntuneMAMSaveLocationSharePoint 
* IntuneMAMSaveLocationBox 
* IntuneMAMSaveLocationDropbox 
* IntuneMAMSaveLocationGoogleDrive 
* IntuneMAMSaveLocationLocalDrive 

Aplikacje powinny używać stałych w interfejsie API **isSaveToAllowedForLocation**, aby sprawdzać, czy można zapisywać dane w lokalizacjach uznawanych za „zarządzane”, np. w usłudze OneDrive dla Firm, lub „osobiste”. Ponadto należy używać interfejsu API w sytuacjach, w których aplikacja nie może określić, czy lokalizacja jest „zarządzana”, czy „osobista”. 

Jeśli lokalizacja jest znana jako „osobista”, aplikacje powinny używać wartości **IntuneMAMSaveLocationOther**. 

Stałej **IntuneMAMSaveLocationLocalDrive** należy używać, gdy aplikacja zapisuje dane w dowolnej lokalizacji na urządzeniu lokalnym.



# Konfigurowanie ustawień zestawu SDK aplikacji usługi Intune

Słownik IntuneMAMSettings umieszczony w pliku info.plist aplikacji jest używany do konfigurowania zestawu SDK aplikacji usługi Intune. Na poniższej liście uwzględniono wszystkie obsługiwane ustawienia: 

Niektóre z tych ustawień mogły zostać omówione w poprzednich sekcjach, a niektóre nie dotyczą wszystkich aplikacji. 

Ustawienie  | Typ  | Definicja | Wymagane?
--       |  --   |   --       |  --
ADALClientId  | String  | Identyfikator klienta usługi AAD aplikacji. | Wymagane, jeśli aplikacja korzysta z biblioteki ADAL.
ADALRedirectUri  | String  | Identyfikator URI przekierowania usługi AAD aplikacji. | Ustawienie ADALRedirectUri lub ADALRedirectScheme jest wymagane, jeśli aplikacja korzysta z biblioteki ADAL. 
ADALRedirectScheme  | String  | Schemat przekierowania usługi AAD aplikacji. Może być używany zamiast ustawienia ADALRedirectUri, jeśli identyfikator URI przekierowania aplikacji ma format `scheme://bundle_id`. | Ustawienie ADALRedirectUri lub ADALRedirectScheme jest wymagane, jeśli aplikacja korzysta z biblioteki ADAL. 
ADALLogOverrideDisabled | Boolean  | Określa, czy zestaw SDK będzie przekierowywać wszystkie dzienniki biblioteki ADAL (łącznie z ewentualnymi wywołaniami biblioteki ADAL z aplikacji) do własnego pliku dziennika. Wartość domyślna to NO (Nie). Wybierz wartość YES (Tak), jeśli aplikacja powinna ustawiać własne wywołanie zwrotne dziennika biblioteki ADAL. | Opcjonalny.
ADALCacheKeychainGroupOverride | String  | Określa grupę łańcucha kluczy do użycia dla pamięci podręcznej biblioteki ADAL zamiast „com.microsoft.adalcache”. Należy zauważyć, że ta grupa nie zawiera prefiksu app-id. Zostanie on umieszczony jako prefiks w podanym ciągu w środowisku uruchomieniowym. | Opcjonalny.
AppGroupIdentifiers | Tablica ciągów  | Tablica grup aplikacji z sekcji uprawnień aplikacji com.apple.security.application-groups. | Wymagane, jeśli aplikacja używa grup aplikacji.
ContainingAppBundleId | String | Określa identyfikator pakietu rozszerzenia zawierającego aplikację. | Wymagane w przypadku rozszerzeń dla systemu iOS.
DebugSettingsEnabled| Boolean | W przypadku ustawienia na wartość YES (TAK) zasady testu w pakiecie ustawień mogą być stosowane. Aplikacje **nie** powinny być dostarczane z włączonym tym ustawieniem. | Opcjonalny.
MainNibFile<br>MainNibFile~ipad  | String  | To ustawienie powinno zawierać nazwę pliku głównego nib aplikacji.  | Wymagane, jeśli w pliku Info.plist aplikacji zdefiniowano ustawienie MainNibFile.
MainStoryboardFile<br>MainStoryboardFile~ipad  | String  | To ustawienie powinno zawierać nazwę pliku głównego storyboard aplikacji. | Wymagane, jeśli w pliku Info.plist aplikacji zdefiniowano ustawienie UIMainStoryboardFile.
MAMPolicyRequired| Boolean| Określa, czy uruchamianie aplikacji będzie blokowane, jeśli aplikacja nie ma zasad zarządzania aplikacjami mobilnymi usługi Intune. Wartość domyślna to „no” (nie). 
MAMPolicyWarnAbsent | Boolean| Określa, czy użytkownik będzie ostrzegany podczas uruchamiania aplikacji, jeśli aplikacja nie ma zasad zarządzania aplikacjami mobilnymi usługi Intune. Uwaga: aplikacje nie mogą być przesłane do sklepu z tym ustawieniem ustawionym na wartość YES (Tak) | Opcjonalny.
MultiIdentity | Boolean| Określa, czy aplikacja obsługuje wiele tożsamości | Opcjonalny.
SplashIconFile <br>SplashIconFile~ipad | String  | Określa plik ikony powitalnej usługi Intune. Aby uzyskać więcej informacji, zobacz sekcję „Pliki obrazów podczas uruchamiania”. | Opcjonalny.
SplashDuration | Liczba | Minimalny czas w sekundach, przez który ekran powitalny usługi Intune będzie wyświetlany podczas uruchamiania aplikacji. Wartość domyślna to 1,5. | Opcjonalny.
BackgroundColor| String| Określa kolor tła ekranu powitalnego i ekranu numeru PIN. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.   | Opcjonalne, domyślnie jasnoszary.
ForegroundColor| String| Określa kolor pierwszego planu ekranu powitalnego i ekranu numeru PIN, na przykład kolor tekstu. Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.  | Opcjonalne, domyślnie czarny.
AccentColor | String| Określa kolor akcentu dla ekranu numeru PIN, na przykład kolor tekstu przycisku i kolor wyróżnienia pola.  Akceptuje ciąg szesnastkowy RGB w postaci „#XXXXXX”, gdzie „X” może być znakiem z zakresu 0–9 lub A–F. Znak # można pominąć.| Opcjonalne, domyślnie systemowy niebieski.
MAMTelemetryDisabled| Boolean| Określa, czy zestaw SDK będzie wysyłał dane telemetryczne z powrotem do swojej wewnętrznej bazy danych| Opcjonalny.
MAMTelemetryUsePPE | Boolean | Określa, czy zestaw SDK będzie wysyłać dane do wewnętrznej bazy danych wstępnego środowiska produkcyjnego. Użyj tego ustawienia podczas testowania aplikacji za pomocą zasad usługi Intune, aby dane telemetryczne testu nie mieszały się z danymi klienta. | Opcjonalny.

## Telemetria 

Domyślnie zestaw SDK aplikacji usługi Intune dla systemu iOS rejestruje dane telemetryczne zdarzeń użycia, które są przesyłane do usługi Microsoft Intune. Rejestrowane są dane następujących zdarzeń użycia: 

1. **Uruchomienie aplikacji**: w celu ułatwienia usłudze Microsoft Intune ustalenia użycia aplikacji z obsługą funkcji MAM zależnie od typu zarządzania (zarządzanie aplikacjami mobilnymi w rozwiązaniu MDM, zarządzanie aplikacjami mobilnymi bez rejestracji w rozwiązaniu MDM itp.).

2. **Wywołanie interfejsu API EnrollApplication**: w celu ułatwienia usłudze Microsoft Intune ustalenia współczynnika operacji zakończonych powodzeniem i różnych innych metryk wydajności wywołań metody `enrollApplication` po stronie klienta.

**Uwaga**: w przypadku zrezygnowania z wysyłania danych telemetrycznych zestawu SDK aplikacji usługi Intune do usługi Microsoft Intune z aplikacji mobilnej należy wyłączyć funkcję przechwytywania danych telemetrycznych w zestawie SDK aplikacji usługi Intune przez wybranie dla właściwości `MAMTelemetryDisabled` ustawienia „YES” (Tak) w słowniku IntuneMAMSettings.


## Kompilowanie rozszerzenia przy użyciu zestawu SDK (opcjonalnie) 

Podczas kompilowania rozszerzeń należy postępować według tych samych instrukcji, jak w przypadku kompilowania aplikacji mobilnej, które zostały podane w sekcji „Kompilowanie aplikacji mobilnej przy użyciu zestawu SDK”. Ponadto należy zaktualizować plik info.plist każdego rozszerzenia przez dodanie klucza `ContainingAppBundleId` w obszarze słownika IntuneMAMSettings z wartością identyfikatora nadrzędnego pakietu aplikacji.

## Kompilowanie struktury przy użyciu zestawu SDK (opcjonalnie)

Dzięki ostatnim aktualizacjom zestawu SDK aplikacji usługi Intune kompilowanie aplikacji mobilnej przy użyciu określonych flag konsolidatora, jeśli aplikacja mobilna zawiera osadzone struktury aplikacji, nie jest konieczne. 

## Pliki obrazów podczas uruchamiania (opcjonalne)

Gdy aplikacja z obsługą funkcji MAM jest aktywnie zarządzana przez usługę Microsoft Intune, zestaw SDK aplikacji usługi Intune wyświetla ekran startowy podczas uruchamiania aplikacji, aby poinformować użytkownika, że aplikacja jest zarządzana. Możesz opcjonalnie dodać pliki obrazów do wyświetlania na stronie startowej „Zarządzane przez firmę”. Uwzględnij następujące zalecenia dotyczące obrazów:

* Dodaj nazwy plików w słowniku IntuneMAMSettings w pliku Info.plist z nazwami kluczy `SplashIconFile` i `SplashIconFile~ipad`. 

* Rozmiary obrazów i wymagania:

    * 180x180 w przypadku telefonów iPhone 6s Plus oraz iPhone 6 Plus, 120x120 w przypadku innych modeli telefonów iPhone oraz 152x152 w przypadku tabletów iPad. 
    
    * Usuń rozszerzenie .png z nazw plików. 
    
    * Użyj opcji konsolidatora `@2x` dla wersji plików obrazów w skali 2x i sufiksu `@3x` dla wersji plików obrazów w skali 3x. Jeśli rozmiar obrazów jest nieodpowiedni, będą one skalowane w celu dopasowania. Jeśli nie określono wartości SplashIconFile, zestaw SDK aplikacji usługi Intune wybiera jedną z ikon aplikacji (60x60 dla wszystkich telefonów iPhone, 76x76 dla tabletów iPad).

**Uwaga**: Ten ekran jest wyświetlany podczas uruchamiania, ale może być trwale ukryty przez użytkownika.



#Włączanie wielu tożsamości (opcjonalnie)

Domyślnie zestaw SDK będzie stosować zasady do aplikacji jako całości. Wiele tożsamości to funkcja zarządzania aplikacjami mobilnymi, którą można włączyć w celu zezwolenia na stosowanie zasad na poziomie poszczególnych tożsamości.  Wymaga to pełniejszego uczestnictwa aplikacji niż inne funkcje zarządzania aplikacjami mobilnymi. 

Aplikacja musi poinformować zestaw SDK aplikacji, gdy zamierza zmienić aktywną tożsamość. Zestaw SDK powiadomi również aplikację, kiedy zmiana tożsamości jest wymagana. Aktualnie obsługiwana jest tylko jedna tożsamość zarządzana. Po zarejestrowaniu urządzenia lub aplikacji przez użytkownika zestaw SDK używa tej tożsamości i uznaje ją za podstawową tożsamość zarządzaną. Inni użytkownicy w aplikacji są traktowani jako niezarządzani z nieograniczonymi ustawieniami zasad. 

Należy zauważyć, że tożsamość jest definiowana po prostu jako ciąg. W tożsamościach nie jest rozróżniana wielkość liter, dlatego żądania tożsamości wysyłane do zestawu SDK mogą nie zwracać jej z tą samą wielkością liter, której pierwotnie użyto podczas ustawiania tożsamości.


##Informacje o tożsamościach 
  
Tożsamość jest po prostu nazwą użytkownika konta (np. user@contoso.com). Deweloperzy mogą ustawić tożsamość aplikacji na następujących różnych poziomach: 

* **Przetwarzanie tożsamości**: tożsamość procesu ustawia tożsamość dla całego procesu i jest używana głównie dla aplikacji z obsługą jednej tożsamości. Ta tożsamość ma wpływ na wszystkie operacje, pliki i interfejs użytkownika.
* **Tożsamość interfejsu użytkownika**: określa, jakie zasady są stosowane do operacji interfejsu użytkownika w głównym wątku, takich jak wytnij/kopiuj/wklej, kod PIN, uwierzytelnianie, udostępnianie danych itp. Tożsamość interfejsu użytkownika nie ma wpływu na operacje na plikach (szyfrowanie, kopie zapasowe itp.).
* **Tożsamość wątku**: tożsamość wątku wpływa na to, jakie zasady są stosowane w bieżącym wątku. Ma to wpływ na wszystkie operacje, pliki i interfejs użytkownika.

To aplikacja odpowiada za odpowiednie ustawienie tożsamości bez względu na to, czy użytkownik jest zarządzany.

W dowolnym momencie każdy wątek ma obowiązującą tożsamość dla operacji interfejsu użytkownika i operacji na plikach. Jest to tożsamość używana do ustalenia, jakie zasady powinny być stosowane. Jeśli tożsamość jest określona jako „brak tożsamości” lub użytkownik nie jest zarządzany, nie są stosowane żadne zasady. 
 
 

##Kolejki wątków
 
Aplikacje często wysyłają synchroniczne i asynchroniczne zadania do kolejek wątków. Zestaw SDK przechwytuje wywołania GCD (Grand Central Dispatch) i kojarzy bieżącą tożsamość wątku z wysłanymi zadaniami. Gdy wykonywane są zadania, zestaw SDK tymczasowo zmienia tożsamość wątku na tożsamość skojarzoną z zadaniem, wykonuje zadania, a następnie przywraca oryginalną tożsamość wątku. Ponieważ klasa `NSOperationQueue` jest zbudowana na bazie GCD, operacje `NSOperations` będą uruchamiane z tożsamością wątku podczas dodawania ich do kolejki `NSOperationQueue`. `NSOperations` lub funkcje wysyłane bezpośrednio za pomocą GCD mają również możliwość zmiany bieżącej tożsamości wątku podczas ich uruchomienia. Ta tożsamość zastąpi tożsamość odziedziczoną z wysyłającego wątku. 

##Właściciel pliku
 
Zestaw SDK śledzi informacje o tożsamości właściciela pliku lokalnego i zgodnie z tym stosuje zasady. Właściciel pliku jest ustanawiany podczas tworzenia pliku lub po otwarciu pliku w trybie truncate. Właściciel jest ustawiany na obowiązująca tożsamość operacji pliku wątku wykonującego operację. Aplikacje mogą także ustawić tożsamość pliku w sposób jawny przy użyciu elementu `IntuneMAMFilePolicyManager`. Aplikacje mogą używać `IntuneMAMFilePolicyManager` do pobrania właściciela pliku i ustawienia tożsamości interfejsu użytkownika przed wyświetleniem zawartości pliku.


##Pliki danych udostępnionych
 
Jeśli aplikacja tworzy pliki zawierające dane od użytkowników zarządzanych i niezarządzanych, odpowiada za szyfrowanie danych użytkowników zarządzanych. Dane mogą być szyfrowane przy użyciu interfejsów API `protect` i `unprotect` klasy `IntuneMAMDataProtectionManager`. Metoda `protect` akceptuje tożsamość, która może być użytkownikiem zarządzanym lub niezarządzanym. Jeśli użytkownik jest zarządzany, dane będą szyfrowane. Jeśli użytkownik jest niezarządzany, do danych kodujących tożsamość zostanie dodany nagłówek, ale dane nie będą szyfrowane.  Metoda `protectionInfo` może służyć do pobierania właściciela danych.

##Rozszerzenia udostępniania
 
Jeśli aplikacja zawiera rozszerzenie udostępniania, właściciela udostępnianego elementu można pobrać przy użyciu metody `protectionInfoForItemProvider` w `IntuneMAMDataProtectionManager`. Jeśli udostępniony element jest plikiem, zestaw SDK obsłuży ustawianie właściciela pliku. Jeśli udostępnionym elementem są dane, aplikacja odpowiada za ustawienie właściciela pliku, jeśli te dane są zachowywane w pliku, oraz wywołanie interfejsu API `setUIPolicyIdentity` (opisanego poniżej) przed wyświetleniem danych w interfejsie użytkownika.
 
##Włączanie wielu tożsamości
 
Domyślnie aplikacje są traktowane jako aplikacje z obsługą jednej tożsamości, a zestaw SDK ustawia tożsamość procesu na zarejestrowanego użytkownika. Aby włączyć obsługę wielu tożsamości, należy dodać ustawienie typu wartość logiczna o nazwie `MultiIdentity` z wartością „YES” (Tak) do słownika **IntuneMAMSettings** w pliku Info.plist aplikacji. 

> [!NOTE]
> W przypadku włączenia obsługi wielu tożsamości tożsamość procesu, tożsamość interfejsu użytkownika i tożsamości wątku będą ustawione na wartość zero. Za ich odpowiednie ustawienie odpowiada aplikacja.

 
##Przełączanie tożsamości
 
###Przełączanie tożsamości inicjowane przez aplikację
Przy uruchomieniu aplikacje z obsługą wielu tożsamości są traktowane jako uruchomione przy użyciu nieznanego, niezarządzanego konta. Interfejs użytkownika z warunkowym uruchamianiem nie zostanie uruchomiony, a w aplikacji nie będą wymuszane żadne zasady. Aplikacja odpowiada za powiadamianie zestawu SDK za każdym razem, kiedy tożsamość powinna zostać zmieniona. Zwykle dzieje się tak, gdy aplikacja ma wyświetlać dane dla określonego konta użytkownika.

Są to na przykład sytuacje, kiedy użytkownik próbuje otworzyć dokument, skrzynkę pocztową lub kartę w Notatniku. Aplikacja musi powiadomić zestaw SDK, zanim plik, skrzynka pocztowa lub karta zostaną faktycznie otwarte. Robi to za pomocą interfejsu API `setUIPolicyIdentity` w obiekcie `IntuneMAMPolicyManager`. Ten interfejs API powinien być wywoływany bez względu na to, czy użytkownik jest zarządzany. Jeśli użytkownik jest zarządzany, zestaw SDK przeprowadzi kontrole warunkowego uruchamiania (wykrywanie zdjęcia zabezpieczeń systemu, numer PIN, uwierzytelnianie itp.). Wynik przełączenia tożsamości jest zwracana do aplikacji asynchronicznie za pomocą procedury obsługi zakończenia. Aplikacja powinna odłożyć otwarcie dokumentu, skrzynki pocztowej, karty itp., dopóki nie zostanie zwrócony kod wyniku „sukces”. W przypadku niepowodzenia przełączania tożsamości aplikacja powinna anulować operację. 

###Przełączanie tożsamości inicjowane przez zestaw SDK
Istnieją przypadki, w których zestaw SDK prosi aplikację o przełączenie do określonej tożsamości. Aplikacje z obsługą wielu tożsamości muszą implementować metodę `identitySwitchRequired` w `IntuneMAMPolicyDelegate` w celu obsługi tego żądania. Gdy zostanie wywołana, jeśli aplikacja jest w stanie obsłużyć żądanie przełączenia do określonej tożsamości, powinna przekazać `IntuneMAMAddIdentityResultSuccess` do procedury obsługi zakończenia. Jeśli aplikacja nie może obsłużyć przełączenia tożsamości, powinna przekazać wartość `IntuneMAMAddIdentityResultFailed` do procedury obsługi zakończenia. Aplikacja nie musi wywoływać metody `setUIPolicyIdentity` w odpowiedzi na to wywołanie. Jeśli zestawu SDK wymaga od aplikacji przełączenia się na konto użytkownika niezarządzanego, do wywołania metody `identitySwitchRequired` zostanie przekazany pusty ciąg. 
 
###Selektywne czyszczenie danych
W przypadku selektywnego czyszczenia danych aplikacji zestaw SDK wywoła metodę `wipeDataForAccount` w elemencie `IntuneMAMPolicyDelegate`. Aplikacja odpowiada za usunięcie konta określonego użytkownika i wszelkich skojarzonych z nim danych. Zestaw SDK jest w stanie usunąć wszystkie pliki należące do użytkownika i zrobi to, jeśli aplikacja zwróci wartość „FALSE” z wywołania metody `wipeDataForAccount`. Należy zauważyć, że ta metoda jest wywoływana z wątku w tle i aplikacja nie powinna być zwracana, dopóki wszystkie dane użytkownika nie zostaną usunięte (z wyjątkiem plików, jeśli aplikacja zwróci wartość „FALSE”).

# Debugowanie zestawu SDK aplikacji usługi Intune w środowisku Xcode

Przed ręcznym testowaniem aplikacji z obsługą funkcji MAM w usłudze Microsoft Intune można użyć pliku **Settings.bundle** w środowisku Xcode. Umożliwi to określenie zasad testowania bez konieczności ustanawiania połączenia z usługą Intune. Aby włączyć ten element:

* Dodaj plik Settings.bundle, klikając prawym przyciskiem myszy folder najwyższego poziomu w projekcie. Wybierz polecenie „Add -> New File” (Dodaj -> Nowy plik) z menu. Wybierz szablon „Settings Bundle” (Pakiet ustawień) w obszarze „Resources” (Zasoby), aby dodać ten szablon.

* Tylko w przypadku kompilacji do debugowania skopiuj plik MAMDebugSettings.plist do pakietu Settings.bundle.

* W pliku Root.plist (w pakiecie Settings.bundle) dodaj preferencję z wartościami „Type” (Typ) = Child Pane (Okienko podrzędne) i „FileName” (Nazwa pliku) = MAMDebugSettings.

* W obszarze **Settings -> Your-App-Name** (Ustawienia -> Twoja nazwa aplikacji) włącz ustawienie „Enable Test Policies” (Włącz zasady testu).

* Uruchom aplikację (wewnątrz lub na zewnątrz środowiska Xcode). 

* W obszarze **Settings -> Your-App-Name -> Enable Test Policies** (Ustawienia -> Twoja nazwa aplikacji -> Włącz zasady testu) włącz zasady, na przykład „PIN”.

* Uruchom aplikację (wewnątrz lub na zewnątrz środowiska Xcode). Sprawdź, czy numer PIN działa zgodnie z oczekiwaniami.

> [!NOTE]
> Po wykonaniu powyższych czynności można włączać i przełączać ustawienia w obszarze **Settings -> Your-App-Name -> Enable Test Policies** (Ustawienia -> Twoja nazwa aplikacji -> Włącz zasady testu).

# Zalecane najlepsze rozwiązania dla systemu iOS

Wdrażając aplikacje dla systemu iOS, należy stosować poniższe najlepsze rozwiązania:

W systemie plików iOS uwzględniana jest wielkość liter. Upewnij się, że wielkość liter jest poprawna w nazwach plików takich jak `libIntuneMAM.a` i `IntuneMAMResources.bundle`.

Jeśli środowisko Xcode nie może odnaleźć biblioteki `libIntuneMAM.a`, możesz rozwiązać ten problem, dodając ścieżkę do tej biblioteki do ścieżek wyszukiwania konsolidatora.



##Najczęściej zadawane pytania 

 **Czy wszyscy użytkownicy mojej aplikacji muszą być zarejestrowani w usłudze zarządzania aplikacjami mobilnymi (MAM)?**

Nie.  W rzeczywistości tylko konta służbowe powinny być rejestrowane przy użyciu zestawu SDK aplikacji usługi Intune.  Aplikacje są odpowiedzialne za określenie, czy konto jest używane w kontekście miejsca pracy lub nauki.   
 
**Co z użytkownikami, którzy już zalogowali się do aplikacji?  Czy muszą zostać zarejestrowani?** 

Aplikacja jest odpowiedzialna nie tylko za rejestrowanie użytkowników po ich pomyślnym uwierzytelnieniu, ale także za zarejestrowanie wszystkich istniejących kont, które mogły być obecne, zanim aplikacja obsługiwała funkcję zarządzania aplikacjami mobilnymi (bez zarządzania urządzeniami przenośnymi).   


W tym celu aplikacja powinna korzystać z metody `registeredAccounts:`.  Metoda ta zwraca klasę NSDictionary zawierającą wszystkie konta zarejestrowane w usłudze zarządzania aplikacjami mobilnymi w usłudze Intune.  Jeśli jakiekolwiek istniejące konta w aplikacji nie są obecne na liście, aplikacja powinna zarejestrować te konta za pomocą metody `registerAndEnrollAccount:`. 


 

**Jak często zestaw SDK ponawia próby rejestracji?** 

Zestaw SDK będzie automatycznie ponawiać próbę rejestracji dla wszystkich rejestracji wcześniej zakończonych niepowodzeniem co 24 godziny.  Robi to w celu upewnienia się, że jeśli organizacja użytkownika włączyła zarządzanie aplikacjami mobilnymi po zalogowaniu się użytkownika do aplikacji, użytkownik zostanie pomyślnie zarejestrowany i otrzyma zasady. 

Zestaw SDK przestanie ponawiać próby po wykryciu, że użytkownik pomyślnie zarejestrował aplikację.  Dzieje się tak, ponieważ w danym momencie tylko jeden użytkownik może zarejestrować aplikację. Jeśli użytkownik jest wyrejestrowany, ponowne próby rozpoczną się ponownie z tym samym 24-godzinnym interwałem. 


 
**Dlaczego użytkownik musi zostać wyrejestrowany?** 

Zestaw SDK będzie okresowo wykonywał następujące działania w tle:

 - Jeśli aplikacja nie jest jeszcze zarejestrowana, co 24 godziny będzie próbował zarejestrować wszystkie zarejestrowane konta. 
 - Jeśli aplikacja jest zarejestrowana, zestaw SDK co 8 godzin będzie sprawdzał dostępność aktualizacji zasad zarządzania aplikacjami mobilnymi. 

Wyrejestrowanie użytkownika powiadamia zestaw SDK, że użytkownik nie będzie już używał aplikacji i można zatrzymać wszystkie z powyższych zdarzeń okresowych dla konta tego użytkownika.  Spowoduje również wykonanie wyrejestrowania aplikacji i selektywnego czyszczenia danych, jeśli jest to konieczne. 

**Czy flagę doWipe należy ustawić na wartość true w metodzie deregister?** Ta metoda powinna być wywoływana przed wylogowaniem użytkownika z aplikacji.  Jeśli w ramach wylogowywania dane użytkownika są usuwane z aplikacji, można ustawić `doWipe` na wartość false.  Jednak jeśli aplikacja faktycznie nie usuwa danych użytkownika, należy ustawić to ustawienie na wartość true, aby zestaw SDK mógł ręcznie usunąć te dane. 

**Czy istnieją inne sposoby wyrejestrowania aplikacji?** Tak, administrator IT może wysłać do aplikacji polecenie selektywnego czyszczenia danych, co spowoduje wyrejestrowanie użytkownika i wyczyszczenie danych użytkownika.  Zestaw SDK automatycznie obsługuje ten scenariusz i będzie wysyłać powiadomienia za pośrednictwem metody delegata un-enroll. 

#Przesyłanie aplikacji do sklepu z aplikacjami
Biblioteki statyczne i kompilacje struktury zestawu SDK aplikacji usługi Intune są uniwersalnymi plikami binarnymi, co oznacza, że zawierają one kod dla wszystkich architektur urządzeń i symulatorów. Apple odrzuci aplikacje przesłane do sklepu App Store, jeśli zawierają one kod symulatora. Podczas kompilowania biblioteki statycznej na potrzeby kompilacji tylko dla urządzenia konsolidator automatycznie usunie kod symulatora.

Jeśli aplikacja używa **kompilacji struktury** zestawu SDK aplikacji usługi Intune, należy ręcznie usunąć architektury symulatora z uniwersalnej struktury przed przesłaniem aplikacji do sklepu z aplikacjami. Aby to zrobić, skorzystaj z poniższych instrukcji:

1. Upewnij się, że `IntuneMAM.framework` znajduje się na pulpicie.
2. Uruchom następujące polecenia:
    
    ```
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```
    Pierwsze polecenie usuwa architektury symulatora z biblioteki dylib struktury.
    ```
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM 
    ```
    Drugie polecenie kopiuje bibliotekę dylib tylko dla urządzenia do katalogu struktury.



<!--HONumber=Oct16_HO3-->


