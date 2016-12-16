---
title: "Dodatek Cordova do zestawu SDK aplikacji usługi Microsoft Intune | Dokumentacja firmy Microsoft"
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 9ef09f43e6c878af689a500457bab578149de499


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Wtyczka Cordova zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](intune-app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.


## <a name="overview"></a>Przegląd

[Wtyczka Cordova zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) umożliwia korzystanie z [funkcji zarządzania aplikacjami mobilnymi usługi Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Cordova. Wtyczka ta pozwala deweloperom na integrowanie funkcji ochrony danych i aplikacji usługi Intune w ramach aplikacji opartych na platformie Cordova.

Funkcje zestawu SDK można włączyć bez zmiany zachowania aplikacji. Po dołączeniu wtyczki do aplikacji mobilnej dla systemu iOS lub Android administrator IT może za pośrednictwem zarządzania aplikacjami mobilnymi (MAM) w usłudze Microsoft Intune wdrożyć zasady obsługujące różne funkcje ochrony danych. Wtyczka została tak zaprojektowana, aby większość etapów kompilacji aplikacji Cordova odbywało się automatycznie. Pozwala to na szybkie rozpoczęcie zarządzania aplikacją. Aby rozpocząć pracę, wykonaj poniższe kroki, odpowiadające platformie docelowej.




## <a name="whats-supported"></a>Co jest obsługiwane?

### <a name="developer-machines"></a>Maszyny deweloperów
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Platformy aplikacji mobilnych
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Scenariusze zarządzanie aplikacjami mobilnymi w usłudze Intune

* Urządzenia zarejestrowane przez funkcję zarządzania urządzeniami przenośnymi w usłudze Intune
* Urządzenia zarejestrowane przez rozwiązanie EMM innej firmy
* Niezarządzane urządzenia (nie zarejestrowane za pomocą żadnego rozwiązania do zarządzania urządzeniami przenośnymi)

Aplikacje Cordova skompilowane za pomocą wtyczki Cordova zestawu SDK aplikacji usługi Intune mogą teraz podlegać zasadom zarządzania aplikacjami mobilnymi usługi Intune zarówno w przypadku urządzeń zarejestrowanych na potrzeby zarządzania urządzeniami przenośnymi w usłudze Intune, jak i niezarejestrowanych urządzeń.



## <a name="prerequisites"></a>Wymagania wstępne

### <a name="technical-prerequisites"></a>Techniczne wymagania wstępne

* **[Dotyczy tylko systemu Android]** Na urządzeniu musi zawsze być zainstalowana najnowsza wersja aplikacji Portal firmy usługi Microsoft Intune.


* Wymagana jest co najmniej wersja 0.8.0 [wtyczki bibliotek uwierzytelniania usługi Azure Active Directory (ADAL) dla platformy Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova).
  * **Ważne:** z powodu błędu platformy Apache Cordova opisanego [tutaj](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) w przypadku aplikacji, które mają już zależność wtyczki, wtyczka nie zostanie automatycznie uaktualniona do żądanej wersji.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Przed zainstalowaniem i rozpoczęciem używania wtyczki Cordova zestawu SDK aplikacji usługi Microsoft Intune, **musisz wykonać następujące czynności**:

* Zapoznać się z [postanowieniami licencyjnymi wtyczki Cordova zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf).

* Wydrukować i zachować kopię postanowień licencyjnych. Pobranie i rozpoczęcie używania wtyczki Cordova zestawu SDK aplikacji usługi Intune oznacza akceptację tych postanowień licencyjnych.  Jeśli użytkownik nie akceptuje niniejszych postanowień, nie może używać tego oprogramowania.


## <a name="quick-start"></a>Szybki start

1. Zaktualizuj wersję bibliotek ADAL:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Dodaj zestaw SDK aplikacji usługi Intune dla wtyczki Cordova:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>Jak dołączyć wtyczkę do aplikacji systemu iOS

Aby włączyć obsługę zarządzania aplikacjami mobilnymi w usłudze Intune dla danej aplikacji, należy wykonać kilka kroków. Ze względów praktycznych kroki te są wykonywane automatycznie w procesie kompilacji aplikacji Cordova w ramach punktu zaczepienia przed kompilacją. Spowoduje to zmodyfikowanie plików `*.pbxproj`, `*-Info.plist` i `*.entitlements` skojarzonych z konfiguracją projektu. Jeśli projekt nie zawiera pliku uprawnień, plik ten zostanie automatycznie utworzony przez wtyczkę.

Ten instalator obsługuje tylko jeden element docelowy. Jeśli istnieje wiele obiektów docelowych, konfiguracja zostanie wykonana na pierwszym znalezionym obiekcie. Jeśli proces zakończy się niepowodzeniem, sprawdź, czy są spełnione następujące warunki:

1. Projekt Xcode aplikacji ma nazwę `[name].xcodeproj`, gdzie `[name]` jest wartością zdefiniowaną w pliku `config.xml`.
2. Projekt używa [standardowej struktury katalogów aplikacji Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="how-to-build-the-plugin-into-your-android-app"></a>Jak dołączyć wtyczkę do aplikacji systemu Android

1. Zaimportuj tę wtyczkę przy użyciu najnowszych narzędzi platformy Cordova. Wtyczka zostanie automatycznie wywołana w kroku `after_compile`.

2. Pod koniec procesu kompilacji wtyczka utworzy skompilowany pakiet apk z obsługą zarządzania aplikacjami mobilnymi (interfejs API systemu Android w wersji 14 lub nowszej). Skompilowane dane wyjściowe będą zawierać pakiet `[Project]-intunewrapped-[Build_Configuration].apk` (np. `helloWorld-intunewrapped-debug.apk`).

Wtyczka obsługuje tylko kompilacje wykonywane za pomocą narzędzia Gradle.

Platforma Cordova zawiera błąd opisany [tutaj](https://issues.apache.org/jira/browse/CB-9434), który powoduje, że niektóre punkty zaczepienia Cordova są ignorowane w poleceniu `cordova run`. Aby uruchomić opakowaną aplikację z wiersza polecenia, należy uruchomić następujące polecenia:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Podpisywanie aplikacji systemu Android
Aby dodać informacje o podpisie do opakowanego pakietu apk, należy zmodyfikować plik `build.json`, podobnie jak podczas rutynowego dodawania informacji o podpisie. Na przykład:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Kompilacja tylko na potrzeby testu w systemie Android

1. Dodaj wpis `android:testOnly="true"` do węzła aplikacji w pliku `AndroidManifest.xml`.


2. **Cordova 6.x.x:** w pliku `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js`, zmień wiersz 60 z

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    na wartość
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Ma to na celu uruchomienie polecenia `adb install` z flagą „-t”, która umożliwia zainstalowanie aplikacji `testOnly`.

### <a name="debugging-from-visual-studio"></a>Debugowanie w programie Visual Studio
Przy pierwszym uruchomieniu aplikacji powinno pojawić się okno dialogowe z informacją, że aplikacja jest zarządzana przez usługę Intune. Należy wybrać opcję „Nie pokazuj ponownie” i ponownie kliknąć przycisk debugowania/uruchamiania w programie VS w celu wywołania punktów przerwania.

## <a name="known-limitations"></a>Znane ograniczenia
### <a name="android"></a>Android
* Obsługa klasy MultiDex jest niepełna.
* Aplikacja musi być przeznaczona dla systemu Android 4.0 (z interfejsem API systemu Android w wersji 14) lub nowszego.

### <a name="ios"></a>iOS
* Każdorazowo podczas modyfikacji listy identyfikatorów UTI w węźle **CFBundleDocumentTypes** pliku **Info.plist** przed ponowną kompilacją należy usunąć identyfikatory UTI usługi Intune w sekcji zaimportowanych identyfikatorów UTI w tym samym pliku plist (w węźle **UTImportedTypeDeclarations**). Wszystkie identyfikatory UTI usługi Intune rozpoczynają się prefiksem `com.microsoft.intune.mam`.

* Jeśli chcesz usunąć wtyczkę Intune z projektu Cordova, musisz również usunąć platformę iOS i dodać ją ponownie w celu wycofania niektórych elementów konfiguracji usługi Intune w plikach xcodeproj i plist.



<!--HONumber=Dec16_HO2-->


