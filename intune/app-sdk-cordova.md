---
title: "Wtyczka Cordova zestawu SDK aplikacji usługi Microsoft Intune"
description: 
keywords: sdk, Cordova, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d42f8418e2f277dca0fbb2f01248f5a815606cb6
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2018
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Wtyczka Cordova zestawu SDK aplikacji usługi Microsoft Intune

> [!IMPORTANT]
> Usługa Intune kończy obsługę wtyczki zestawu SDK aplikacji usługi Intune Microsoft dla oprogramowania Cordova z dniem 1 maja 2018 r. Firma Microsoft zaleca, aby zamiast tej wtyczki używać narzędzia opakowującego aplikacje usługi Intune. Aby uzyskać więcej informacji o narzędziu do opakowywania aplikacji, zobacz [Narzędzie opakowujące aplikacje dla systemu iOS](app-wrapper-prepare-ios.md) i [Narzędzie opakowujące aplikacje dla systemu Android](app-wrapper-prepare-android.md). Aby uzyskać więcej informacji na temat tej zmiany, zobacz sekcję [Uwagi](whats-new.md#notices) w artykule [Co nowego w usłudze Microsoft Intune](whats-new.md).

## <a name="overview"></a>Przegląd

[Wtyczka Cordova zestawu SDK aplikacji usługi Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą struktury Cordova. Wtyczka ta pozwala deweloperom na integrowanie funkcji ochrony danych i aplikacji usługi Intune w ramach aplikacji opartych na platformie Cordova.

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

Funkcje zestawu SDK można włączyć bez zmiany zachowania aplikacji. Po wbudowaniu wtyczki do aplikacji dla systemu iOS lub Android administrator usługi Microsoft Intune będzie mógł wdrożyć zasady ochrony aplikacji usługi Intune, które obejmują różne funkcje ochrony danych. Wtyczka jest kompilowana w taki sposób, aby większość czynności było wykonywanych automatycznie podczas kompilacji aplikacji Cordova. Pozwala to na szybkie włączenie aplikacji w zakres ochrony aplikacji usługi Intune. Aby rozpocząć pracę, wykonaj poniższe kroki, odpowiadające platformie docelowej.

## <a name="supported-platforms"></a>Obsługiwane platformy

* Wtyczka działa w systemach operacyjnych Windows, Mac i Linux
* Wtyczka działa w aplikacjach dla systemu Android w wersjach `minSdkVersion` >= 14 i `targetSdkVersion` <= 24
* Wtyczka działa w aplikacjach dla systemu iOS przeznaczonych dla systemu iOS w wersji 9.0 lub nowszej.

## <a name="intune-mobile-application-management-scenarios"></a>Scenariusze zarządzanie aplikacjami mobilnymi w usłudze Intune

* Urządzenia zarejestrowane przez funkcję zarządzania urządzeniami przenośnymi w usłudze Intune
* Urządzenia zarejestrowane przez rozwiązanie EMM innej firmy
* Niezarządzane urządzenia (nie zarejestrowane za pomocą żadnego rozwiązania do zarządzania urządzeniami przenośnymi)

Aplikacje Cordova skompilowane za pomocą wtyczki Cordova zestawu SDK aplikacji usługi Intune mogą teraz odbierać zasady ochrony aplikacji usługi Intune zarówno w przypadku urządzeń zarejestrowanych na potrzeby zarządzania urządzeniami przenośnymi w usłudze Intune, jak i urządzeń niezarejestrowanych.

## <a name="prerequisites"></a>Wymagania wstępne

### <a name="android"></a>Android

* Na urządzeniu musi zawsze być zainstalowana najnowsza wersja aplikacji Portal firmy usługi Microsoft Intune.
* W ścieżce, w której będzie wykonywana kompilacja aplikacji Cordova podczas korzystania z wtyczki, musi znajdować się program Java przynajmniej w wersji 7.

### <a name="ios"></a>iOS

* Aby można było korzystać z funkcji MDM, na urządzeniu musi być zainstalowana najnowsza wersja aplikacji Portal firmy usługi Microsoft Intune. *Nie* jest ona wymagana dla zasad ochrony aplikacji usługi Intune bez funkcji rejestracji urządzeń.

### <a name="both-platforms"></a>Obie platformy

* Wymagana jest co najmniej wersja 0.8.0 [wtyczki bibliotek uwierzytelniania usługi Azure Active Directory (ADAL) dla platformy Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova).

> [!NOTE]
> Z powodu błędu platformy Apache Cordova opisanego [tutaj](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) w przypadku aplikacji, które mają już zależność wtyczki, wtyczka nie zostanie automatycznie uaktualniona do żądanej wersji.



## <a name="quickstart"></a>Szybki start

1. Zaktualizuj wersję bibliotek ADAL:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Dodaj zestaw SDK aplikacji usługi Intune dla wtyczki Cordova:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>Dołączanie wtyczki do aplikacji systemu iOS

Aby włączyć obsługę zasad ochrony aplikacji usługi Intune dla danej aplikacji, należy wykonać kilka kroków. Ze względów praktycznych kroki te są wykonywane automatycznie w procesie kompilacji aplikacji Cordova w ramach punktu zaczepienia przed kompilacją. Spowoduje to zmodyfikowanie plików `*.pbxproj`, `*-Info.plist` i `*.entitlements` skojarzonych z konfiguracją projektu. Jeśli projekt nie zawiera pliku uprawnień, plik ten zostanie automatycznie utworzony przez wtyczkę.

Ten instalator obsługuje tylko jeden element docelowy. Jeśli istnieje wiele obiektów docelowych, konfiguracja zostanie wykonana na pierwszym znalezionym obiekcie. Jeśli proces zakończy się niepowodzeniem, sprawdź, czy są spełnione następujące warunki:

1. Projekt Xcode aplikacji ma nazwę `[name].xcodeproj`, gdzie `[name]` jest wartością zdefiniowaną w pliku `config.xml`.
2. Projekt używa [standardowej struktury katalogów aplikacji Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="build-the-plugin-into-your-android-app"></a>Dołączanie wtyczki do aplikacji systemu Android

1. Zaimportuj tę wtyczkę przy użyciu najnowszych narzędzi platformy Cordova. Wtyczka zostanie automatycznie wywołana w kroku `after_compile`.

2. Pod koniec procesu kompilacji wtyczka utworzy skompilowany pakiet apk (interfejs API systemu Android w wersji 14 lub nowszej) z obsługą usługi Intune. Skompilowane dane wyjściowe będą zawierać pakiet `[Project]-intunewrapped-[Build_Configuration].apk` (np. `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> Wtyczka obsługuje tylko kompilacje wykonywane za pomocą narzędzia Gradle.

Platforma Cordova zawiera błąd opisany [tutaj](https://issues.apache.org/jira/browse/CB-9434), który powoduje, że niektóre punkty zaczepienia Cordova są ignorowane w poleceniu `cordova run`. Aby uruchomić opakowaną aplikację z wiersza polecenia, należy uruchomić następujące polecenia:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Podpisywanie aplikacji systemu Android

Wtyczka automatycznie rozpoznaje informacje o podpisywaniu podane na platformie Cordova w następujących lokalizacjach:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Aby uzyskać więcej informacji dotyczących oczekiwanego formatu, zobacz [informacje o podpisywaniu narzędzia Gradle aplikacji Cordova ](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle).

Obecnie firma Microsoft nie obsługuje udostępniania informacji o podpisywaniu w pliku `build.json` lub w dowolnych miejscach przekazanych za pośrednictwem parametrów do kompilacji aplikacji Cordova.

## <a name="debugging-from-visual-studio"></a>Debugowanie w programie Visual Studio

Przy pierwszym uruchomieniu aplikacji powinno pojawić się okno dialogowe z informacją, że aplikacja jest zarządzana przez usługę Intune. Należy wybrać opcję „Nie pokazuj ponownie” i ponownie kliknąć przycisk debugowania/uruchamiania w programie VS w celu wywołania punktów przerwania.

## <a name="known-limitations"></a>Znane ograniczenia

### <a name="android"></a>Android

* Obsługa klasy MultiDex jest niepełna.
* Wartość `minSdkVersion` musi wynosić 14, a wartość `targetSdkVersion` 24 lub mniej. Obecnie firma Microsoft nie obsługuje aplikacji interfejsu API 25
* Nie możemy ponownie podpisać aplikacji, które zostały podpisane przy użyciu schematu podpisu V2. Jeśli aplikacje podpisane przy użyciu schematu podpisu V2 zostaną opakowane przy użyciu wtyczki, podpis opakowanego wyjściowego pliku apk zostanie cofnięty.
*
  * Można wyłączyć domyślne podpisywanie przy użyciu schematu V2 aplikacji Cordova przez dodanie do pliku `build-extras.gradle`:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Każdorazowo podczas modyfikacji listy identyfikatorów UTI w węźle **CFBundleDocumentTypes** pliku **Info.plist** przed ponowną kompilacją należy usunąć identyfikatory UTI usługi Intune w sekcji zaimportowanych identyfikatorów UTI w tym samym pliku plist (w węźle **UTImportedTypeDeclarations**). Wszystkie identyfikatory UTI usługi Intune rozpoczynają się prefiksem `com.microsoft.intune.mam`.

* Jeśli chcesz usunąć zestaw SDK aplikacji usługi Intune dla wtyczki Cordova, musisz również usunąć platformę iOS i dodać ją ponownie w celu wycofania niektórych elementów konfiguracji usługi Intune w plikach xcodeproj i plist.
