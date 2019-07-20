---
title: Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android
description: Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu Android można wdrożyć funkcje zarządzania aplikacjami mobilnymi (MAM, Mobile App Management) usługi Intune w swojej aplikacji systemu Android.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b033052ebd5d3d26976482ea2435c8a0d7314c8e
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885043"
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android

> [!NOTE]
> Warto najpierw przeczytać artykuł [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md), w którym opisano aktualne funkcje zestawu SDK oraz sposób przygotowania się do integracji na każdej z obsługiwanych platform.

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu Android możesz wdrożyć zasady ochrony aplikacji usługi Intune (nazywane również zasadami **APP** lub MAM) w swojej natywnej aplikacji dla systemu Android. Aplikacja zarządzana przez usługę Intune to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy usługi Intune mogą z łatwością wdrażać zasady ochrony aplikacji w aplikacji zarządzanej przez usługę Intune, gdy usługa Intune aktywnie zarządza aplikacją.


## <a name="whats-in-the-sdk"></a>Zawartość zestawu SDK

Zestaw SDK aplikacji usługi Intune obejmuje następujące pliki:

* **Microsoft.Intune.MAM.SDK.aar**: składniki zestawu SDK z wyjątkiem plików JAR biblioteki obsługi.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: klasy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 4.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: klasy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 7.
* **Microsoft.Intune.MAM.SDK.Support.v17.jar**: klasy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 17. 
* **Microsoft.Intune.MAM.SDK.Support.Text.jar**: klasy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z klas biblioteki obsługi systemu Android w pakiecie `android.support.text`.
* **Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: ten plik jar zawiera klasy zastępcze dla klas systemowych systemu Android, które istnieją wyłącznie w nowszych urządzeniach, ale są przywoływane przez metody w MAMActivity. Nowsze urządzenia będą ignorować te klasy zastępcze. Ten plik jar jest niezbędny tylko wtedy, gdy aplikacja wykonuje odbicie wobec klas pochodzących z MAMActivity. Większość aplikacji nie musi go uwzględniać. Jeśli używasz tego pliku jar, musisz pamiętać o wykluczeniu wszystkich jego klas z narzędzia ProGuard. Znajdują się one wszystkie w obszarze pakietu głównego „android”
* **com.microsoft.intune.mam.build.jar**: wtyczka programu Gradle, która [pomaga w integracji zestawu SDK](#build-tooling).
* **CHANGELOG.txt**: zawiera rejestr zmian wprowadzonych w każdej z wersji zestawu SDK.
* **THIRDPARTYNOTICES.TXT**: informacje o uznaniu autorstwa dotyczące kodu innych firm lub typu „open source”, który zostanie skompilowany w ramach aplikacji.

## <a name="requirements"></a>Wymagania

### <a name="android-versions"></a>Wersje systemu Android
Zestaw SDK obsługuje interfejsy API od wersji Android API 19 (Android 4.4 i nowsze) do wersji Android API 28 (Android 9.0).

### <a name="company-portal-app"></a>Aplikacji Portal firmy
Zestaw SDK aplikacji usługi Intune dla systemu Android wymaga obecności na urządzeniu aplikacji [Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) umożliwiającej włączenie zasad ochrony aplikacji. Aplikacja Portal firmy pobiera zasady ochrony aplikacji z usługi Intune. Po uruchomieniu aplikacji zostają załadowane zasady i kod umożliwiający wymuszenie danej zasady z aplikacji Portal firmy.

> [!NOTE]
> Jeśli na urządzeniu nie ma aplikacji Portal firmy, aplikacja zarządzana przez usługę Intune działa tak samo jak zwykła aplikacja, która nie obsługuje zasad ochrony aplikacji usługi Intune.

W przypadku ochrony aplikacji bez rejestracji urządzeń _**nie**_ jest wymagane, aby użytkownik rejestrował urządzenie za pomocą aplikacji Portal firmy.

## <a name="sdk-integration"></a>Integracja z zestawem SDK

### <a name="sample-app"></a>Przykładowa aplikacja
Przykład prawidłowego sposobu integrowania zestawu SDK aplikacji usługi Intune jest dostępny w witrynie [GitHub](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App). W tym przykładzie użyto [wtyczki kompilacji Gradle](#gradle-build-plugin).

### <a name="referencing-intune-app-libraries"></a>Odwoływanie się do bibliotek aplikacji usługi Intune

Zestaw SDK aplikacji usługi Intune to standardowa biblioteka systemu Android bez zewnętrznych zależności. Plik **Microsoft.Intune.MAM.SDK.aar** zawiera zarówno interfejsy niezbędne do włączenia zasad ochrony aplikacji, jak i kod wymagany do celów współpracy z aplikacją Portal firmy usługi Microsoft Intune.

Plik **Microsoft.Intune.MAM.SDK.aar** musi zostać wskazany jako odwołanie do biblioteki systemu Android. W tym celu otwórz swój projekt aplikacji w programie Android Studio, przejdź do menu **File > New > New module** (Plik > Nowy > Nowy moduł) i wybierz pozycję **Import .JAR/.AAR Package** (Importuj pakiet JAR/AAR). Następnie wybierz nasz pakiet archiwum systemu Android Microsoft.Intune.MAM.SDK.aar, aby utworzyć moduł dla naszych plików AAR. Kliknij prawym przyciskiem myszy moduł lub moduły zawierające Twój kod aplikacji, a następnie przejdź do pozycji **Ustawienia modułu** > **karta Zależności** > **ikona +**   >  **Zależności modułu** > Wybierz właśnie utworzony moduł AAR zestawu SDK Zarządzania aplikacjami mobilnymi > **OK**. Da to pewność, że Twój moduł skompiluje się przy użyciu zestawu SDK Zarządzania aplikacjami mobilnymi (MAM) podczas kompilowania Twojego projektu.

Ponadto biblioteki **Microsoft.Intune.MAM.SDK.Support.XXX.jar** zawierają warianty usługi Intune odpowiadających bibliotek `android.support.XXX`. Nie są one wbudowane w plik Microsoft.Intune.MAM.SDK.aar na wypadek, gdyby aplikacja nie musiała zależeć od bibliotek obsługi.

#### <a name="proguard"></a>ProGuard

Jeśli rozwiązanie [ProGuard](http://proguard.sourceforge.net/) (lub jakikolwiek inny mechanizm zmniejszający/zaciemniający) jest stosowane w ramach kroku kompilacji, zestaw SDK ma dodatkowe reguły konfiguracji, które należy uwzględnić. W przypadku dołączania pliku AAR do kompilacji nasze reguły są automatycznie integrowane w kroku narzędzia ProGuard, a wymagane pliki klas są zachowywane.

Biblioteki uwierzytelniania usługi Azure Active Directory (ADAL, Active Directory Authentication Library) mogą mieć własne ograniczenia dotyczące narzędzia ProGuard. Jeśli aplikacja jest zintegrowana z biblioteką ADAL, postępowanie względem tych ograniczeń powinno być zgodne z dokumentacją ADAL.

### <a name="build-tooling"></a>Narzędzia kompilacji
Zestaw SDK aplikacji usługi Intune to biblioteka systemu Android, która umożliwia aplikacji obsługę wymuszania zasad usługi Intune oraz udział w tym procesie. Niektóre zasady wymagają [jawnego udziału aplikacji w wymuszeniu](#enable-features-that-require-app-participation), jednak większość jest wymuszana półautomatycznie. To automatyczne wymuszenie wymaga, aby aplikacja zastąpiła dziedziczenie z kilku klas bazowych systemu Android dziedziczeniem z odpowiedników zarządzania aplikacjami mobilnymi i podobnie zastąpiła wywołania do pewnych klas usługi systemu Android wywołaniami do odpowiedników zarządzania aplikacjami mobilnymi. Określone wymagane zamiany podano [poniżej](#class-and-method-replacements).

Wykonywanie tych zamian ręcznie może być żmudnym procesem. Zamiast tego zestaw SDK zapewnia narzędzia do kompilacji (wtyczka dla kompilacji Gradle oraz narzędzie wiersza polecenia dla kompilacji innych niż kompilacje Gradle), które wykonują zastąpienia automatycznie. Te narzędzia przekształcają pliki klasy wygenerowane przez kompilację języka Java i nie modyfikują oryginalnego kodu źródłowego.

Narzędzia wykonują tylko [bezpośrednie zamiany](#class-and-method-replacements). Nie wykonują żadnych bardziej złożonych integracji zestawu SDK, takich jak [zasady Zapisz jako](#enable-features-that-require-app-participation), [wiele tożsamości](#multi-identity-optional), [rejestracja App-WE](#app-protection-policy-without-device-enrollment), [modyfikacje AndroidManifest](#manifest-replacements) lub [konfiguracja ADAL](#configure-azure-active-directory-authentication-library-adal), więc należy je wykonać przed ostatecznym włączeniem aplikacji w usłudze Intune. Dokładnie przejrzyj pozostałą część niniejszej dokumentacji w zakresie punktów integracji istotnych dla Twojej aplikacji.

> [!NOTE]
> Można uruchomić narzędzia dla projektu, który przeprowadził już częściową lub kompletną integrację źródła zestawu SDK zarządzania aplikacjami mobilnymi przy użyciu zamian ręcznych. Projekt nadal musi wymieniać zestaw SDK zarządzania aplikacjami mobilnymi jako zależność.

### <a name="gradle-build-plugin"></a>Wtyczka kompilacji Gradle
Jeśli Twoja aplikacja nie jest kompilowana przy użyciu narzędzia Gradle, przejdź do [integrowania przy użyciu narzędzia wiersza polecenia](#command-line-build-tool). 

Wtyczka zestawu SDK aplikacji jest dystrybuowana jako część zestawu SDK jako biblioteka **GradlePlugin/com.microsoft.intune.mam.build.jar**. Aby narzędzie Gradle mogło znaleźć wtyczkę, należy ją dodać do ścieżki klasy skryptu kompilacji. Wtyczka zależy od elementu [Javassist](https://jboss-javassist.github.io/javassist/), który również należy dodać. Aby dodać te elementy do ścieżki klasy, dodaj następujący kod do katalogu głównego `build.gradle`

```groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath "org.javassist:javassist:3.22.0-GA"
        classpath files("$PATH_TO_MAM_SDK/GradlePlugin/com.microsoft.intune.mam.build.jar")
    }
}
```

Następnie w pliku `build.gradle` projektu APK zastosuj wtyczkę jako

```groovy
apply plugin: 'com.microsoft.intune.mam'
```

Domyślnie wtyczka będzie działać **tylko** dla zależności `project`.
Nie ma to wpływu na kompilację testową. Konfiguracja może być dostarczona do listy
* Projekty do wykluczenia
* [Zależności zewnętrzne do uwzględnienia](#usage-of-includeexternallibraries) 
* Określone klasy do wykluczenia z przetwarzania
* Warianty do wykluczenia z przetwarzania. Mogą odwoływać się do kompletnej nazwy wariantu lub pojedynczej właściwości. Na przykład
  * jeśli Twoja aplikacja ma typy kompilacji `debug` i `release` z właściwościami {`savory`, `sweet`} oraz {`vanilla`, `chocolate`}, możesz określić
  * `savory`, aby wykluczyć wszystkie warianty z właściwością savory lub `savoryVanillaRelease`, aby wykluczyć tylko ten konkretny wariant.

#### <a name="example-partial-buildgradle"></a>Przykład częściowego rozwiązania build.gradle

```groovy

apply plugin: 'com.microsoft.intune.mam'

dependencies {
    implementation project(':product:FooLib')
    implementation project(':product:foo-project')
    implementation fileTree(dir: "libs", include: ["bar.jar"])
    implementation fileTree(dir: "libs", include: ["zap.jar"])
    implementation "com.contoso.foo:zap-artifact:1.0.0"
    implementation "com.microsoft.bar:baz:1.0.0"

    // Include the MAM SDK
    implementation files("$PATH_TO_MAM_SDK/Microsoft.Intune.MAM.SDK.aar")
}
intunemam {
    excludeProjects = [':product:FooLib']
    includeExternalLibraries = ['bar.jar', "com.contoso.foo:zap-artifact", "com.microsoft.*", "!com.microsoft.qux*"]
    excludeClasses = ['com.contoso.SplashActivity']
    excludeVariants=['savory']
}
```

Będzie to miało następujące skutki:
* `:product:FooLib` nie zostanie przepisany, ponieważ jest uwzględniony w `excludeProjects`
* `:product:foo-project` zostanie przepisany, poza elementem `com.contoso.SplashActivity`, który zostanie pominięty, ponieważ znajduje się w `excludeClasses`
* `bar.jar` zostanie przepisany, ponieważ jest uwzględniony w `includeExternalLibraries`
* `zap.jar` **nie** zostanie przepisany, ponieważ nie jest projektem i nie jest uwzględniony w `includeExternalLibraries`
* `com.contoso.foo:zap-artifact:1.0.0` zostanie przepisany, ponieważ jest uwzględniony w `includeExternalLibraries`
* `com.microsoft.bar:baz:1.0.0` zostanie przepisany, ponieważ jest uwzględniony `includeExternalLibraries` za pomocą symbolu wieloznacznego (`com.microsoft.*`).
* `com.microsoft.qux:foo:2.0` nie zostanie przepisany, chociaż jest zgodny z tym samym symbolem wieloznacznym co poprzedni element, ponieważ jest jawnie wykluczony za pomocą wzorca negacji.

#### <a name="usage-of-includeexternallibraries"></a>Użycie polecenia includeExternalLibraries

Ponieważ wtyczka działa domyślnie tylko względem zależności projektu (zazwyczaj podawanych przez funkcję `project()`), wszelkie zależności określone przez `fileTree(...)` lub pozyskane z narzędzia maven bądź innych źródeł pakietów (np. „`com.contoso.bar:baz:1.2.0`”) muszą być podane do właściwości `includeExternalLibraries`, jeśli wymagane jest przetwarzanie zarządzania aplikacjami mobilnymi, w oparciu o kryteria wyjaśnione poniżej. Symbole wieloznaczne („*”) są obsługiwane. Element rozpoczynający się od znaku `!` jest negacją i może służyć do wykluczania bibliotek, które w przeciwnym razie zostałyby włączone przez symbol wieloznaczny.

Podczas określania zależności zewnętrznych z notacją artefaktu zaleca się pominięcie składnika wersji w wartości `includeExternalLibraries`. Jeśli uwzględnisz wersję, musi to być dokładna wersja. Dynamiczne specyfikacje wersji (np. `1.+`) nie są obsługiwane.

Ogólna zasada, której należy użyć w celu określenia, czy wymagane jest uwzględnienie bibliotek w `includeExternalLibraries`, jest oparta na dwóch pytaniach:
1. Czy biblioteka ma klasy, dla których istnieją odpowiedniki zarządzania aplikacjami mobilnymi? Przykłady: `Activity`, `Fragment`, `ContentProvider`, `Service` itp.
2. Jeśli tak, czy aplikacja wykorzystuje te klasy?

Jeśli na oba pytania można odpowiedzieć „tak”, to trzeba uwzględnić tę bibliotekę w `includeExternalLibraries`. 

| Scenariusz | Czy należy uwzględnić bibliotekę? |
|--|--|
| Uwzględniasz bibliotekę przeglądarki plików PDF w aplikacji i używasz przeglądarki `Activity` w aplikacji, gdy użytkownicy próbują wyświetlić dokumenty PDF | Tak |
| Uwzględniasz bibliotekę HTTP w aplikacji, aby zapewniać lepszą wydajność w Internecie | Nie |
| Uwzględniasz bibliotekę, np. React Native, zawierającą klasy pochodne z `Activity`, `Application` i `Fragment` oraz używasz tych klas lub wprowadzasz kolejne elementy pochodne z tych klas w aplikacji | Tak |
| Uwzględniasz bibliotekę, np. React Native, zawierającą klasy pochodne z `Activity`, `Application` i `Fragment`, ale używasz tylko statycznych elementów pomocniczych lub klas narzędzi | Nie |
| Uwzględniasz bibliotekę zawierającą klasy widoku pochodne z `TextView` i używasz tych klas lub wprowadzasz kolejne elementy pochodne z tych klas w aplikacji | Tak |

#### <a name="reporting"></a>Raportowanie
Wtyczka kompilacji może wygenerować raport dokonywanych zmian w formacie HTML. Aby zażądać wygenerowania tego raportu, określ wartość `report = true` w bloku konfiguracji `intunemam`. Po wygenerowaniu raport zostanie zapisany w folderze `outputs/logs` w katalogu kompilacji.

```groovy
intunemam {
    report = true
}
```

#### <a name="dependencies"></a>Zależności

Wtyczka gradle ma zależność w [Javassist](https://jboss-javassist.github.io/javassist/), która musi być dostępna dla rozwiązywania zależności narzędzia Gradle (zgodnie z opisem powyżej). Kod Javassist jest używany wyłącznie w czasie kompilacji podczas uruchamiania wtyczki. Żaden kod Javassist nie zostanie dodany do aplikacji.

> [!NOTE] 
> Należy używać wersji 3.0 lub nowszej wtyczki Android Gradle oraz narzędzia Gradle w wersji 4.1 lub nowszej.

### <a name="command-line-build-tool"></a>Narzędzie kompilacji wiersza polecenia
Jeśli kompilacja używa narzędzia Gradle, przejdź do [następnej sekcji](#class-and-method-replacements).

Narzędzie kompilacji wiersza polecenia jest dostępne w folderze `BuildTool` zestawu SDK. Wykonuje taką samą funkcję jak wtyczka narzędzia Gradle opisana powyżej, ale może być zintegrowane w niestandardowych systemach kompilacji lub systemach innych niż systemy korzystające z narzędzia Gradle. Ponieważ narzędzie jest bardziej ogólne, jego wywołanie jest bardziej złożone, więc wtyczki narzędzia Gradle należy używać zawsze tam, gdzie jest to możliwe.

#### <a name="using-the-command-line-tool"></a>Używanie narzędzia wiersza polecenia

Narzędzie wiersza polecenia można wywołać przy użyciu zapewnionych skryptów pomocniczych znajdujących się w katalogu `BuildTool\bin`.

Narzędzie oczekuje następujących parametrów.

| Parametr | Opis |
| -- | -- |
| `--input` | Rozdzielana średnikami lista plików jar oraz katalogów plików klas do zmodyfikowania. Lista powinna obejmować wszystkie pliki jar/katalogi, które zamierzasz ponownie napisać. |
| `--output` | Rozdzielana średnikami lista plików jar oraz katalogów do przechowywania zmodyfikowanych klas. Powinien istnieć jeden wpis danych wyjściowych na jeden wpis danych wejściowych i powinny one być umieszczone na liście w kolejności. |
| `--classpath` | Ścieżka klasy kompilacji. Może zawierać pliki jar i katalogi klas. |
| `--excludeClasses`| Rozdzielana średnikami lista zawierająca nazwy klas, które powinny być wykluczone z ponownego zapisywania. |

Wszystkie parametry są wymagane, poza `--excludeClasses`, który jest opcjonalny.

> [!NOTE] 
> W systemach Unix separatorem poleceń jest znak średnika. Aby uniknąć dzielenia poleceń w powłoce, poprzedź każdy średnik znakiem ucieczki ’\' lub ujmij cały parametr w znaki cudzysłowu.

#### <a name="example-command-line-tool-invocation"></a>Przykład wywołania narzędzia wiersza polecenia

``` batch
> BuildTool\bin\BuildTool.bat --input build\product-foo-project;libs\bar.jar --output mam-build\product-foo-project;mam-build\libs\bar.jar --classpath build\zap.jar;libs\Microsoft.Intune.MAM.SDK\classes.jar;%ANDROID_SDK_ROOT%\platforms\android-27\android.jar --excludeClasses com.contoso.SplashActivity
```

Będzie to miało następujące skutki:

* Katalog `product-foo-project` zostanie przepisany do `mam-build\product-foo-project`
* `bar.jar` zostanie przepisany do `mam-build\libs\bar.jar`
* `zap.jar` **nie** zostanie przepisany, ponieważ jest uwzględniony tylko w `--classpath`
* Klasa `com.contoso.SplashActivity` **nie** zostanie przepisana, nawet jeśli znajduje się w `--input`

> [!NOTE] 
> Narzędzie kompilacji nie obsługuje obecnie plików aar. Jeśli system kompilacji nie wyodrębnia jeszcze `classes.jar` podczas pracy z plikami aar, należy to zrobić przed wywołaniem narzędzia kompilacji.


## <a name="class-and-method-replacements"></a>Zamiana klas i metod

Klasy bazowe systemu Android muszą zostać zastąpione odpowiednimi klasami równoważnymi funkcji MAM, aby umożliwić korzystanie z zarządzania w usłudze Intune. Klasy zestawu SDK są ulokowanie między klasami bazowymi systemu Android a pochodnymi wersjami klas należącymi do aplikacji. Przykładowo działanie aplikacji może doprowadzić do powstania końcowej hierarchii dziedziczenia wyglądającej następująco: `Activity` > `MAMActivity` >
`AppSpecificActivity`. Warstwa funkcji MAM filtruje wywołania do operacji systemu, aby bezproblemowo zapewniać aplikacji zarządzany widok świata.

Poza klasami bazowymi niektóre klasy, których może używać aplikacja bez stosowania dziedziczenia (np. `MediaPlayer`), również mają wymagane odpowiedniki funkcji MAM, a ponadto [niektóre wywołania metod również muszą być zastąpione](#wrapped-system-services). Poniżej podano dokładne informacje.

Wszystkie zamiany wymienione w tej sekcji można wykonać automatycznie przy użyciu [narzędzia kompilacji](#build-tooling) zestawu SDK. 



| Klasa bazowa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.Dialog | MAMDialog |
| android.app.AlertDialog.Builder | MAMAlertDialogBuilder |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.ListFragment | MAMListFragment |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | MAMPendingIntent (zobacz [Oczekiwanie zamierzone](#pendingintent)) |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder [wymagane tylko, jeżeli klasa Binder nie jest generowana z interfejsu AIDL (Android Interface Definition Language)] |
| android.media.MediaPlayer | MAMMediaPlayer |
| android.media.MediaMetadataRetriever | MAMMediaMetadataRetriever |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |
| android.support.multidex.MultiDexApplication | MAMMultiDexApplication |
| android.widget.TextView | MAMTextView |
| android.widget.AutoCompleteTextView | MAMAutoCompleteTextView |
| android.widget.CheckedTextView | MAMCheckedTextView |
| android.widget.EditText | MAMEditText |
| android.inputmethodservice.ExtractEditText | MAMExtractEditText |
| android.widget.MultiAutoCompleteTextView | MAMMultiAutoCompleteTextView |

> [!NOTE]
> Nawet jeżeli aplikacja nie potrzebuje własnej klasy pochodnej `Application`, [zobacz `MAMApplication` poniżej](#mamapplication)

### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.JobIntentService | MAMJobIntentService
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
| android.support.v4.content.WakefulBroadcastReceiver | MAMWakefulBroadcastReceiver

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.support.v7.app.AlertDialog.Builder | MAMAlertDialogBuilder |
| android.support.v7.app.AppCompatActivity | MAMAppCompatActivity |
| android.support.v7.widget.AppCompatAutoCompleteTextView | MAMAppCompatAutoCompleteTextView |
| android.support.v7.widget.AppCompatCheckedTextView | MAMAppCompatCheckedTextView |
| android.support.v7.widget.AppCompatEditText | MAMAppCompatEditText |
| android.support.v7.widget.AppCompatMultiAutoCompleteTextView | MAMAppCompatMultiAutoCompleteTextView |
| android.support.v7.widget.AppCompatTextView | MAMAppCompatTextView |

### <a name="microsoftintunemamsdksupportv17jar"></a>Microsoft.Intune.MAM.SDK.Support.v17.jar:
|Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.support.v17.leanback.widget.SearchEditText | MAMSearchEditText |

### <a name="microsoftintunemamsdksupporttextjar"></a>Microsoft.Intune.MAM.SDK.Support.Text.jar:
|Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.support.text.emoji.widget.EmojiAppCompatEditText | MAMEmojiAppCompatEditText |
| android.support.text.emoji.widget.EmojiAppCompatTextView | MAMEmojiAppCompatTextView |
| android.support.text.emoji.widget.EmojiEditText | MAMEmojiEditText |
| android.support.text.emoji.widget.EmojiTextView | MAMEmojiTextView |

### <a name="renamed-methods"></a>Metody o zmienionej nazwie
W wielu przypadkach metoda dostępna w klasie systemu Android została oznaczona jako „final” w zastępczej klasie funkcji MAM. W takim przypadku klasa zastępcza funkcji MAM udostępnia metodę o podobnej nazwie (zazwyczaj z sufiksem `MAM`), która powinna zostać przesłonięta zamiast niej. Na przykład przy tworzeniu klasy pochodnej klasy `MAMActivity` zamiast przesłaniać metodę `onCreate()` i wywoływać metodę `super.onCreate()` działanie `Activity` należy przesłonić metodę `onMAMCreate()` i wywołać metodę `super.onMAMCreate()`. Kompilator języka Java powinien wymuszać ograniczenia specyfikacji final, aby zapobiec przypadkowemu przesłonięciu oryginalnej metody zamiast jej równoważnika funkcji MAM.

### <a name="mamapplication"></a>MAMApplication
Jeśli Twoja aplikacja tworzy podklasę `android.app.Application`, wtedy **musisz** zamiast tego utworzyć podklasę `com.microsoft.intune.mam.client.app.MAMApplication`. Jeśli Twoja aplikacja nie tworzy podklasy `android.app.Application`, wtedy **musisz** ustawić `"com.microsoft.intune.mam.client.app.MAMApplication"` jako atrybut `"android:name"` w Twoim tagu AndroidManifest.xml `<application>`.

### <a name="pendingintent"></a>PendingIntent
Zamiast metody `PendingIntent.get*` należy użyć metody `MAMPendingIntent.get*`. Następnie można użyć otrzymanego elementu `PendingIntent` w zwykły sposób.

### <a name="wrapped-system-services"></a>Zapakowane usługi systemowe
W przypadku niektórych klas usług systemowych wymagane jest wywołanie metody statycznej w klasie otoki funkcji MAM, zamiast bezpośredniego wywoływania żądanej metody w wystąpieniu usługi. Na przykład wywołanie do `getSystemService(ClipboardManager.class).getPrimaryClip()` musi stać się wywołaniem do `MAMClipboardManager.getPrimaryClip(getSystemService(ClipboardManager.class)`. Nie zaleca się ręcznego wprowadzania tych zastąpień. Zamiast tego należy użyć wtyczki BuildPlugin.

| Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.content.ClipboardManager | MAMClipboard |
| android.content.ContentProviderClient | MAMContentProviderClientManagement |
| android.content.ContentResolver | MAMContentResolverManagement |
| android.content.pm.PackageManager | MAMPackageManagement |
| android.app.DownloadManager | MAMDownloadManagement |
| android.print.PrintManager | MAMPrintManagement |
| android.support.v4.print.PrintHelper | MAMPrintHelperManagement |
| android.view.View | MAMViewManagement |
| android.view.DragEvent | MAMDragEventManagement |

W niektórych klasach, takich jak `ClipboardManager`, `ContentProviderClient`, `ContentResolver` i `PackageManager`, większość metod jest opakowanych, podczas gdy w innych klasach, np. `DownloadManager`, `PrintManager`, `PrintHelper`, `View` i `DragEvent`, opakowane są tylko jedna lub dwie metody. Jeśli nie korzystasz z wtyczki BuildPlugin, opis dokładnej metody możesz znaleźć w dokumentacji interfejsów API udostępnianych przez klasy równoważne funkcji MAM. 

### <a name="manifest-replacements"></a>Zamiany w manifeście
Konieczne może być przeprowadzenie niektórych z powyższych zamian klas w obrębie manifestu i kodu języka Java. Ważne:
* Odwołania manifestu do klasy `android.support.v4.content.FileProvider` muszą zostać zastąpione odwołaniami do klasy `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.

## <a name="androidx-libraries"></a>Biblioteki AndroidX
Wraz z systemem Android P firma Google ogłosiła nowy zestaw (pod zmienioną nazwą) bibliotek obsługi zwany AndroidX. Wersja 28 jest głównym wydaniem istniejących bibliotek android.support.

W przeciwieństwie do bibliotek obsługi android, nie zapewniamy wariantów funkcji MAM bibliotek AndroidX. Zamiast tego bibliotekę AndroidX należy traktować jak każdą inną bibliotekę zewnętrzną i należy ją skonfigurować do przepisania przez wtyczkę/narzędzie kompilacji. W przypadku kompilacji narzędzia Gradle można to zrobić poprzez uwzględnienie `androidx.*` w polu `includeExternalLibraries` konfiguracji wtyczki. Wywołania narzędzia wiersza polecenia muszą jawnie wymieniać wszystkie pliki jar na liście.
## <a name="sdk-permissions"></a>Uprawnienia zestawu SDK

Zestaw SDK aplikacji usługi Intune wymaga trzech [uprawnień systemu Android](https://developer.android.com/guide/topics/security/permissions.html) do aplikacji, które mają ten zestaw wbudowany:

* `android.permission.GET_ACCOUNTS` (żądane w czasie wykonywania, jeśli jest niezbędne)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Te uprawnienia są wymagane przez bibliotekę Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) w celu wykonania uwierzytelniania obsługiwanego przez brokera. Jeśli te uprawnienia nie zostaną przyznane dla aplikacji lub zostaną odwołane przez użytkownika, przepływy uwierzytelniania, które wymagają brokera (aplikacja Portal firmy), zostaną wyłączone.

## <a name="logging"></a>Rejestrowanie

Rejestrowanie powinno zostać zainicjowane wcześnie, aby umożliwić optymalne wykorzystanie zarejestrowanych danych. Najlepszym miejsce do zainicjowania rejestrowania jest zwykle wywołanie `Application.onMAMCreate()`.

Aby otrzymać dzienniki funkcji MAM w aplikacji, należy utworzyć [program obsługi języka Java](https://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) i dodać go do elementu `MAMLogHandlerWrapper`. Spowoduje to wywołanie `publish()` w programie obsługi aplikacji dla każdego komunikatu dziennika.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a>Włączanie funkcji wymagających udziału aplikacji

Istnieje kilka zasad ochrony aplikacji, których zestaw SDK nie może samodzielnie zaimplementować. Aplikacja może kontrolować swoje zachowanie w celu uzyskania tych funkcji przy użyciu kilku interfejsów API, które znajdują się w interfejsie `AppPolicy` przedstawionym poniżej. Aby pobrać wystąpienie klasy `AppPolicy`, użyj metody `MAMPolicyManager.getPolicy`.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Checks whether any activities which could handle the given intent are allowed by policy. Returns false only if all
 * activities which could otherwise handle the intent are blocked. If there are no activities which could handle the intent
 * regardless of policy, returns true. If some activities are allowed and others blocked, returns true. Note that it is not
 * necessary to use this method for policy enforcement. If your app attempts to launch an intent for which there are no
 * allowed activities, MAM will display a dialog explaining the situation to the user.
 *
 * @param intent
 *         intent to check
 *
 * @return whether any activities which could handle this intent are allowed.
*/
boolean areIntentActivitiesAllowed(Intent intent);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether
 * file encryption is in use. File encryption is transparent to the app, and the app should not need
 * to make any business logic decisions based on this.
 * 
 * @return True if file encryption is in use.
 */
boolean diagnosticIsFileEncryptionInUse();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}
```

> [!NOTE]
> Wywołanie `MAMPolicyManager.getPolicy` zawsze zwraca zasady aplikacji o wartości innej niż null, nawet jeśli urządzenie lub aplikacja nie podlega zasadom zarządzania usługi Intune.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Przykład: ustalenie, czy dla aplikacji jest wymagany numer PIN

Jeśli aplikacja ma własne środowisko użytkownika uwzględniające użycie numeru PIN, można je wyłączyć, jeżeli administrator IT skonfigurował zestaw SDK w taki sposób, aby użytkownik otrzymywał monit o podanie numeru PIN aplikacji. Aby ustalić, czy administrator IT wdrożył w danej aplikacji zasadę dotyczącą numeru PIN aplikacji dla bieżącego użytkownika końcowego, należy wywołać następującą metodę:

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Przykład: określenie głównego użytkownika usługi Intune

Oprócz interfejsów API ujawnianych w zasadzie AppPolicy, interfejs API `getPrimaryUser()` zdefiniowany w obrębie interfejsu `MAMUserInfo` ujawnia także główną nazwę użytkownika (**UPN**). Aby uzyskać nazwę UPN, niezbędne jest wywołanie:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

Pełna definicja interfejsu MAMUserInfo znajduje się poniżej:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Przykład: ustalenie, czy jest dozwolone zapisywanie w pamięci urządzenia lub w magazynie w chmurze

Wiele aplikacji implementuje funkcje, które umożliwiają użytkownikom końcowym zapisywanie plików lokalnie lub w usłudze magazynu w chmurze. Zestaw SDK aplikacji usługi Intune pozwala administratorom IT chronić dane przed wyciekiem przez zastosowanie ograniczeń zasad w organizacji w dowolny sposób.  Jedne z zasad, które dział IT może kontrolować, dotyczą tego, czy użytkownik końcowy może zapisywać w „osobistym”, niezarządzanym magazynie danych. Obejmuje to zapisywanie w lokalizacji lokalnej, na karcie SD i w usługach kopii zapasowych innych firm.

**Do włączenia tej funkcji wymagane jest współdziałanie ze strony aplikacji.** Jeśli Twoja aplikacja umożliwia zapisywanie w lokalizacji osobistej lub w chmurze bezpośrednio z aplikacji, musisz zaimplementować tę funkcję, aby umożliwić administratorowi IT kontrolowanie, czy zapisywanie w lokalizacji jest dozwolone. Interfejs API przedstawiony poniżej umożliwia aplikacji określenie, czy zapisywanie w magazynie osobistym jest dozwolone przez bieżące zasady administratora usługi Intune. Aplikacja może wtedy wymusić zasady, ponieważ ma informacje o osobistym magazynie danych dostępnym dla użytkownika końcowego przez aplikację.  

Aby określić, czy zasada jest wymuszana, należy wykonać następujące wywołanie:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

Parametr `service` musi być jedną z następujących wartości `SaveLocation`:


- `SaveLocation.ONEDRIVE_FOR_BUSINESS`
- `SaveLocation.SHAREPOINT`
- `SaveLocation.LOCAL`
- `SaveLocation.OTHER`

Element `username` powinien być nazwą UPN, nazwą użytkownika lub adresem e-mail skojarzonym z usługą w chmurze, w której jest zapisywany dokument (*nie* musi to być nazwa użytkownika będącego właścicielem zapisywanego dokumentu). Użyj wartości null, jeśli nie istnieje mapowanie między nazwą UPN usługi AAD i nazwą użytkownika usługi w chmurze lub nazwa użytkownika jest nieznana.

Poprzednią metodą określania, czy zasada użytkownika pozwala na zapisywanie danych w różnych lokalizacjach, była metoda `getIsSaveToPersonalAllowed()` w tej samej klasie **AppPolicy**. Ta funkcja jest obecnie **przestarzała** i nie należy jej używać. Poniższe wywołanie jest równoważne wywołaniu `getIsSaveToPersonalAllowed()`:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> Użyj elementu `SaveLocation.OTHER`, jeśli dana lokalizacja nie jest wymieniona w wyliczeniu **SaveLocations**.


## <a name="register-for-notifications-from-the-sdk"></a>Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK

### <a name="overview"></a>Przegląd
Zestaw SDK aplikacji usługi Intune pozwala aplikacji na kontrolę zachowania niektórych zasad, takich jak selektywne czyszczenie, gdy są one wdrażane przez administratora IT. Kiedy administrator IT wdraża taką zasadę, usługa Intune wysyła powiadomienie do zestawu SDK.

Aplikacja musi zarejestrować się, aby otrzymywać powiadomienia z zestawu SDK, tworząc klasę `MAMNotificationReceiver` i dokonując rejestracji za pomocą metody `MAMNotificationReceiverRegistry`. Należy to zrobić, podając odbiorcę i typ odpowiednich powiadomień w metodzie `App.onCreate`, tak jak pokazano w przykładzie poniżej:

```java
@Override
public void onCreate() {
  super.onCreate();
  MAMComponents.get(MAMNotificationReceiverRegistry.class)
    .registerReceiver(
      new ToastNotificationReceiver(),
      MAMNotificationType.WIPE_USER_DATA);
  }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

Interfejs `MAMNotificationReceiver` po prostu odbiera powiadomienia z usługi Intune. Niektóre powiadomienia są obsługiwane bezpośrednio przez zestaw SDK, a inne wymagają współdziałania ze strony aplikacji. Aplikacja **musi** zwrócić wartość true lub false dla powiadomienia. Musi ona zawsze zwrócić wartość true, chyba że niektóre akcje, które próbowała wykonać w wyniku powiadomienia, nie powiodły się.

* To niepowodzenie może zostać zgłoszone do usługi Intune. Raport może zostać utworzony na przykład wtedy, kiedy czyszczenie danych użytkownika w aplikacji zakończy się niepowodzeniem po tym, gdy administrator IT zainicjuje takie czyszczenie.

>[!NOTE]
> Blokowanie w metodzie `MAMNotificationReceiver.onReceive` jest bezpieczne, ponieważ jej wywołanie zwrotne nie jest uruchamiane w wątku interfejsu użytkownika.

Interfejs `MAMNotificationReceiver` zgodny z definicją w zestawie SDK został przedstawiony poniżej:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}
```

### <a name="types-of-notifications"></a>Typy powiadomień

Następujące powiadomienia są wysyłane do aplikacji i niektóre z nich mogą wymagać współdziałania ze strony aplikacji:

* **WIPE_USER_DATA**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po odebraniu tego powiadomienia aplikacja powinna usunąć wszystkie dane skojarzone z tożsamością „firmową” przekazaną za pomocą klasy `MAMUserNotification`. To powiadomienie jest aktualnie wysyłane podczas wyrejestrowywania z usługi APP-WE. Nazwa podstawowa użytkownika jest zazwyczaj określana podczas procesu rejestracji. Jeśli zarejestrujesz odbieranie tego powiadomienia, Twoja aplikacja musi zapewnić, że wszystkie dane użytkownika zostaną usunięte. Jeżeli nie zarejestrujesz jego odbierania, zostanie wykonane domyślne działanie czyszczenia selektywnego.

* **WIPE_USER_AUXILIARY_DATA**: aplikacje mogą zarejestrować odbieranie tego powiadomienia, jeśli zestaw SDK aplikacji usługi Intune ma wykonywać domyślne czyszczenie selektywne, ale aplikacja ma usuwać niektóre dane pomocnicze w ramach czyszczenia. To powiadomienie jest niedostępne dla aplikacji z pojedynczą tożsamością i będzie wysyłane tylko do aplikacji mających wiele tożsamości.

* **REFRESH_POLICY**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po otrzymaniu tego powiadomienia wszystkie decyzje dotyczące zasad usługi Intune znajdujące się w pamięci podręcznej aplikacji muszą zostać unieważnione i zaktualizowane. Jeśli aplikacja nie przechowuje żadnych założeń dotyczących zasad, nie musi zostać zarejestrowana na potrzeby tego powiadomienia.

* **REFRESH_APP_CONFIG**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po otrzymaniu tego powiadomienia wszystkie dane konfiguracji aplikacji znajdujące się w pamięci podręcznej muszą zostać unieważnione i zaktualizowane.

* **MANAGEMENT_REMOVED**: to powiadomienie jest wysyłane w klasie `MAMUserNotification` i informuje aplikację, że przestanie ona być zarządzana. Po wycofaniu z zarządzania aplikacja nie będzie już mieć możliwości odczytu zaszyfrowanych plików, odczytu danych zaszyfrowanych za pomocą klasy MAMDataProtectionManager, interakcji z zaszyfrowanym schowkiem i innego rodzaju uczestnictwa w ekosystemie zarządzanych aplikacji. Poniżej znajdują się dalsze szczegóły.

* **MAM_ENROLLMENT_RESULT**: to powiadomienie jest wysyłane w klasie `MAMEnrollmentNotification`, aby poinformować aplikację, że próba rejestracji APP-WE została zakończona, i udostępnić stan tej próby.

* **COMPLIANCE_STATUS**: to powiadomienie jest wysyłane w klasie `MAMComplianceNotification`, aby poinformować aplikację o wyniku próby korygowania zgodności.

> [!NOTE]
> Aplikacja w żadnym wypadku nie może być zarejestrowana do otrzymywania jednocześnie powiadomień `WIPE_USER_DATA` i `WIPE_USER_AUXILIARY_DATA`.

### <a name="managementremoved"></a>MANAGEMENT_REMOVED

Powiadomienie `MANAGEMENT_REMOVED` oznacza, że użytkownik, który wcześniej był zarządzany przez zasady, już nie będzie zarządzany przez zasady zarządzania aplikacjami mobilnymi usługi Intune. Nie wymaga to czyszczenia danych użytkownika ani jego wylogowywania się (jeśli czyszczenie było wymagane, powinno zostać wysłane powiadomienie `WIPE_USER_DATA`). Wiele aplikacji może w ogóle nie musieć obsługiwać tego powiadomienia, jednak użytkownicy aplikacji korzystających z klasy `MAMDataProtectionManager` powinni [zwróć szczególną uwagę na to powiadomienie](#data-protection).

Kiedy funkcja MAM wywołuje odbiornik `MANAGEMENT_REMOVED` aplikacji, następujące stwierdzenia są prawdziwe:
* Funkcja MAM już odszyfrowała poprzednio zaszyfrowane pliki (z wyjątkiem chronionych buforów danych) należące do aplikacji. Pliki znajdujące się w lokalizacjach publicznych na karcie SD, które bezpośrednio nie należą do aplikacji (np. foldery Dokumenty lub Pobrane), nie są odszyfrowywane.
* Nowe pliki lub chronione bufory danych utworzone przez metodę odbiornika (lub inny kod uruchomiony po uruchomieniu odbiornika) nie będą szyfrowane.
* Aplikacja nadal ma dostęp do kluczy szyfrowania, więc operacje, takie jak odszyfrowywanie buforów danych, zostaną wykonane pomyślnie.

Kiedy metoda odbiornika zostanie zakończona, nie będzie miała ona już dostępu do kluczy szyfrowania.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurowanie biblioteki uwierzytelniania usługi Azure Active Directory (ADAL)

Najpierw należy przeczytać wskazówki dotyczące integracji usługi ADAL w [repozytorium ADAL w usłudze GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).

Zestaw SDK zależy od usługi [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) w zakresie [uwierzytelniania](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) i warunkowego uruchamiania, co wymaga konfiguracji aplikacji uwzględniającej usługę [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Wartości konfiguracji są przekazywane do zestawu SDK przez metadane w pliku AndroidManifest.

Aby skonfigurować aplikację i włączyć odpowiednie uwierzytelnianie, dodaj następujący element do węzła aplikacji w pliku AndroidManifest.xml. Niektóre z tych konfiguracji są wymagane tylko wtedy, gdy aplikacja ogólnie używa biblioteki ADAL do uwierzytelniania. W takim przypadku potrzebne są konkretne wartości, których aplikacja użyła do zarejestrowania się w usłudze AAD. Ma to na celu zapewnienie, że użytkownik końcowy nie będzie monitowany dwukrotnie w ramach uwierzytelnienia z powodu rozpoznania przez usługę AAD dwóch odrębnych wartości rejestracji: jednej z aplikacji i jednej z zestawu SDK.

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a>Metadane usługi ADAL

* Wartość **Authority** odnosi się do używanego urzędu usługi AAD. Jeśli ta wartość jest nieobecna, jest używane publiczne środowisko usługi AAD.
    > [!NOTE]
    > Nie należy ustawiać tego pola, jeśli aplikacja wie o suwerennej chmurze.

* Wartość **ClientID** to identyfikator klienta usługi AAD (znany także jako identyfikator aplikacji), który ma zostać użyty. Należy użyć własnego identyfikatora ClientID aplikacji, jeśli została ona zarejestrowana w usłudze Azure AD. W przypadku braku tej wartości używana jest wartość domyślna usługi Intune.

* **NonBrokerRedirectURI** to identyfikator URI przekierowania usługi AAD, który ma być używany w przypadkach braku obsługi przez brokera. W przypadku braku określenia wartości używana jest wartość domyślna `urn:ietf:wg:oauth:2.0:oob`. Ustawienie domyślne jest odpowiednie dla większości aplikacji.

  * Identyfikator NonBrokerRedirectURI jest używany tylko w sytuacji, gdy element SkipBroker ma wartość „true”.

* **Element SkipBroker** służy do zastępowania domyślnego zachowania udziału biblioteki ADAL logowania jednokrotnego. Parametr SkipBroker powinien zostać podany tylko dla aplikacji, które określają identyfikator ClientID **oraz** nie obsługują pośrednictwa w zakresie uwierzytelniania/logowania jednokrotnego na całym urządzeniu. W takim przypadku należy ustawić dla niego wartość „true”. W większości aplikacji nie należy ustawiać parametru SkipBroker.

  * Identyfikator ClientID **musi** zostać podany w manifeście, aby móc określić wartość parametru SkipBroker.

  * Jeśli zostanie podany identyfikator ClientID, wartość domyślna to „false”.

  * Jeśli parametr SkipBroker ma wartość „true”, zostanie użyty identyfikator NonBrokerRedirectURI. Aplikacje, które nie integrują się z biblioteką ADAL (i w związku z tym nie mają identyfikatora ClientID), będą również mieć wartość domyślną „true”.

### <a name="common-adal-configurations"></a>Typowe konfiguracje biblioteki ADAL

Poniżej przedstawiono typowe sposoby konfiguracji aplikacji z uwzględnieniem bibliotek ADAL. Znajdź konfigurację odpowiednią dla aplikacji i upewnij się, że dla parametrów metadanych ADAL ustawiono wymagane wartości (objaśnione powyżej). We wszystkich przypadkach urząd można w razie potrzeby określić dla środowisk innych niż domyślne. Jeśli urząd nie zostanie określony, będzie używany publiczny produkcyjny urząd usługi AAD.

#### <a name="1-app-does-not-integrate-adal"></a>1. Aplikacja nie jest zintegrowana z biblioteką ADAL
Metadane biblioteki ADAL **nie mogą** znajdować się w manifeście.

#### <a name="2-app-integrates-adal"></a>2. Aplikacja jest zintegrowana z biblioteką ADAL

|Wymagany parametr ADAL| Wartość |
|--|--|
| ClientID | Identyfikator ClientID aplikacji (generowany przez usługę Azure AD podczas rejestracji aplikacji) |

W razie potrzeby można określić urząd.

Aplikację należy zarejestrować w usłudze Azure AD i zapewnić jej dostęp do usługi zasady ochrony aplikacji:
* Zobacz [tutaj](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications), aby uzyskać informacje o rejestracji aplikacji przy użyciu usługi Azure AD.
* Upewnij się, że wykonano kroki udzielania uprawnień aplikacji systemu Android do usługi zasady ochrony aplikacji (APP). Postępuj zgodnie z instrukcjami w [przewodniku zawierającym wprowadzenie do SDK usługi Intune](https://docs.microsoft.com/intune/app-sdk-get-started#next-steps-after-integration) w sekcji „Udzielanie aplikacji dostępu do usługi ochrony aplikacji w usłudze Intune (opcjonalnie)”. 

Zobacz też wymagania dotyczące [dostępu warunkowego](#conditional-access) poniżej.


#### <a name="3-app-integrates-adal-but-does-not-support-brokered-authenticationdevice-wide-sso"></a>3. Aplikacja jest zintegrowana z biblioteką ADAL, ale nie obsługuje pośrednictwa w zakresie uwierzytelniania/logowania jednokrotnego na całym urządzeniu

|Wymagany parametr ADAL| Wartość |
|--|--|
| ClientID | Identyfikator ClientID aplikacji (generowany przez usługę Azure AD podczas rejestracji aplikacji) |
| SkipBroker | **True** |

W razie potrzeby można określić urząd i identyfikator NonBrokerRedirectURI.

### <a name="conditional-access"></a>Dostęp warunkowy

Warunkowy dostęp (CA) jest [funkcją](https://docs.microsoft.com/azure/active-directory/develop/active-directory-conditional-access-developer) usługi Azure Active Directory, której można użyć do kontrolowania dostępu do zasobów usługi AAD. [Administratorzy usługi Intune mogą zdefiniować reguły warunkowego dostępu](https://docs.microsoft.com/intune/conditional-access) umożliwiające dostęp do zasobów tylko z urządzeń lub aplikacji, które są zarządzane przez usługę Intune. W celu zapewnienia Twojej aplikacji możliwości uzyskania dostępu do zasobów, gdy jest to konieczne, należy wykonać poniższe czynności. Jeśli Twoja aplikacja nie uzyskuje tokenów dostępu usługi AAD lub uzyskuje dostęp tylko do tych zasobów, które nie mogą być chronione przez warunkowy dostęp, możesz pominąć te kroki.

1. Postępuj zgodnie z [wytycznymi integracji biblioteki ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-android#how-to-use-this-library). 
   Zobacz szczególnie krok 11 z opisem użycia brokera.
2. [Zarejestruj swoją aplikację w usłudze Azure Active Directory] (https://docs.microsoft.com/azure/active-directory/active-directory-app-registration). 
   Identyfikator URI przekierowania znajduje się powyżej we wskazówkach dotyczących integracji biblioteki ADAL.
3. Ustaw parametry metadanych manifestu na [Typowe konfiguracje biblioteki ADAL](#common-adal-configurations), element 2 powyżej.
4. Sprawdź, czy wszystko jest poprawnie skonfigurowane, włączając [warunkowy dostęp oparty na urządzeniach](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use) z witryny [Azure Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExchangeConnectorMenu/aad/connectorType/2) i potwierdzając
    - To logowanie do Twojej aplikacji monituje o zainstalowanie i rejestrację w Portalu firmy usługi Intune
    - Po rejestracji logowanie do Twojej aplikacji zakończy się pomyślnie.
5. Gdy Twoja aplikacja wyśle integrację zestawu SDK aplikacji usługi Intune, napisz na adres msintuneappsdk@microsoft.com, aby dodać aplikację do listy zatwierdzonych aplikacji dla [dostępu warunkowego na podstawie aplikacji](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use#app-based-conditional-access).
6. Po dodaniu aplikacji do listy zatwierdzonych przeprowadź weryfikację przez [skonfigurowanie dostępu warunkowego opartego na aplikacji](https://docs.microsoft.com/intune/app-based-conditional-access-intune-create) i sprawdzenie, czy można się pomyślnie zalogować do Twojej aplikacji.

## <a name="app-protection-policy-without-device-enrollment"></a>Zasady ochrony aplikacji bez rejestracji urządzeń

### <a name="overview"></a>Przegląd
Zasady ochrony aplikacji w usłudze Intune bez rejestracji urządzeń, znane również jako usługa APP-WE lub MAM-WE, umożliwiają zarządzanie aplikacjami przez usługę Intune bez konieczności rejestracji urządzenia w usłudze zarządzania urządzeniami przenośnymi (MDM) usługi Intune. Zasady APP-WE działają zarówno w przypadku rejestracji urządzeń, jak i braku rejestracji. Aplikacja Portal firmy musi być zainstalowana na urządzeniu, ale użytkownik nie musi logować się do niej i rejestrować urządzenia.

> [!NOTE]
> Zasady ochrony aplikacji bez rejestracji urządzeń muszą być obsługiwane przez wszystkie aplikacje.

### <a name="workflow"></a>Przepływ pracy

Podczas tworzenia nowego konta użytkownika w aplikacji konto powinno zostać zarejestrowane do zarządzania z użyciem zestawu SDK aplikacji usługi Intune. Zestaw SDK przeprowadzi rejestrację aplikacji w usłudze APP-WE. Jeśli wystąpią błędy, zestaw ponowi próbę rejestracji w odpowiednich odstępach czasu.

Aplikacja może również przesłać do zestawu SDK aplikacji usługi Intune zapytanie dotyczące stanu zarejestrowanego użytkownika w celu ustalenia, czy użytkownik powinien mieć zablokowany dostęp do zawartości firmowej. Do celów zarządzania można zarejestrować wiele kont, jednak obecnie w usłudze APP-WE w danym momencie może być aktywnie zarejestrowane tylko jedno konto. Oznacza to, że zasady ochrony aplikacji mogą być jednocześnie stosowane tylko dla jednego konta w aplikacji.

Aplikacja musi wykonać wywołanie zwrotne w celu uzyskania odpowiedniego tokenu dostępu z biblioteki uwierzytelniania usługi Azure Active Directory (ADAL) w imieniu zestawu SDK. Zakłada się, że aplikacja korzysta już z biblioteki ADAL w celu uwierzytelniania użytkowników i uzyskiwania własnych tokenów dostępu.

Po całkowitym usunięciu konta przez aplikację powinno ono zostać wyrejestrowane, aby wskazać, że aplikacja nie powinna już stosować zasad do danego użytkownika. Jeśli użytkownik został zarejestrowany w usłudze zarządzania aplikacjami mobilnymi (MAM), zostanie on wyrejestrowany, a aplikacja zostanie wyczyszczona.


### <a name="overview-of-app-requirements"></a>Przegląd wymagań dotyczących aplikacji

Aby możliwe było wdrożenie integracji z usługą APP-WE, aplikacja musi zarejestrować konto użytkownika z użyciem zestawu SDK usługi MAM:

1. Aplikacja _musi_ wdrożyć i zarejestrować wystąpienie interfejsu `MAMServiceAuthenticationCallback`. Wystąpienie wywołania zwrotnego powinno zostać zarejestrowane na możliwie najwcześniejszym etapie cyklu życia aplikacji (zwykle w ramach metody `onMAMCreate()` klasy aplikacji).

2. Po utworzeniu konta użytkownika i pomyślnym zalogowaniu się użytkownika w bibliotece ADAL aplikacja _musi_ wykonać wywołanie `registerAccountForMAM()`.

3. Jeśli konto użytkownika zostało usunięte, aplikacja powinna wykonać wywołanie `unregisterAccountForMAM()`, aby usunąć konto z procesu zarządzania w usłudze Intune.

    > [!NOTE]
    > W przypadku tymczasowego wylogowania użytkownika wywołanie `unregisterAccountForMAM()` przez aplikację nie jest wymagane. Wywołanie może zainicjować całkowite wyczyszczenie danych firmowych dla danego użytkownika.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Wszystkie niezbędne interfejsy API używane do uwierzytelniania i rejestracji można znaleźć w interfejsie `MAMEnrollmentManager`. Odwołanie do `MAMEnrollmentManager` można uzyskać w następujący sposób:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr
```

Zwrócone wystąpienie `MAMEnrollmentManager` na pewno nie będzie puste. Metody interfejsu API można podzielić na dwie kategorie: metody **uwierzytelniania** i metody **rejestracji konta**.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Uwierzytelnienie konta

W tej sekcji opisano metody interfejsu API uwierzytelniania stosowane w interfejsie `MAMEnrollmentManager` oraz sposób ich użycia.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. Aplikacja musi zaimplementować interfejs `MAMServiceAuthenticationCallback`, aby możliwe było zażądanie tokenu ADAL dla danego identyfikatora użytkownika i zasobu przez zestaw SDK. Wystąpienie wywołania zwrotnego musi zostać przekazane do interfejsu `MAMEnrollmentManager` przez wywołanie odpowiedniej metody `registerAuthenticationCallback()`. Token może być wymagany na wczesnym etapie cyklu życia aplikacji w celu przeprowadzenia ponownych prób rejestracji lub zaewidencjonowania odświeżenia zasad ochrony aplikacji, dlatego idealnym miejscem na zarejestrowanie wywołania zwrotnego jest metoda `onMAMCreate()` podklasy `MAMApplication` aplikacji.

2. Metoda `acquireToken()` powinna uzyskać token dostępu dla żądanego identyfikatora zasobu dla danego użytkownika. Jeśli uzyskanie żądanego tokenu jest niemożliwe, powinna zostać zwrócona wartość null.

    > [!NOTE]
    > Upewnij się, że Twoja aplikacja korzysta z parametrów `resourceId` i `aadId` przekazywanych do metody `acquireToken()`, aby był uzyskiwany prawidłowy token.

    ```java
    class MAMAuthCallback implements MAMServiceAuthenticationCallback {
        public String acquireToken(String upn, String aadId, String resourceId) {
            return mAuthContext.acquireTokenSilentSync(resourceId, ClientID, aadId).getAccessToken();
        }
    }
    ```

3. Jeżeli aplikacja nie jest w stanie dostarczyć tokenu po wykonaniu wywołania `acquireToken()` przez zestaw SDK — na przykład gdy dyskretne uwierzytelnianie nie powiedzie się, a moment nie jest właściwy, aby wyświetlić interfejs użytkownika — aplikacja może dostarczyć token w późniejszym czasie przez wywołanie metody `updateToken()`. Ta sama nazwa UPN, identyfikator usługi AAD i identyfikator zasobu, których dotyczyło wcześniejsze wywołanie `acquireToken()`, muszą zostać przekazane do wywołania `updateToken()` wraz z tokenem, który został ostatecznie uzyskany. Aplikacja powinna wywołać tę metodę najszybciej, jak to możliwe po zwróceniu wartości „null” w wyniku podanego wywołania zwrotnego.

    > [!NOTE]
    > Zestaw SDK będzie okresowo wykonywać wywołania `acquireToken()` w celu uzyskania tokenu, dlatego wywołanie `updateToken()` nie jest bezwzględnie konieczne. Jest ono jednak zdecydowanie zalecane, ponieważ może ułatwić terminowe rejestrowanie i ewidencjonowanie zasad ochrony aplikacji.


### <a name="account-registration"></a>Rejestracja konta

W tej sekcji opisano metody interfejsu API rejestrowania konta używane w interfejsie `MAMEnrollmentManager` oraz sposób ich użycia.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Aby zarejestrować konto do celów zarządzania, aplikacja musi wykonać wywołanie `registerAccountForMAM()`. Konto użytkownika jest identyfikowane z użyciem jego nazwy UPN i identyfikatora użytkownika usługi AAD. Wymagany jest również identyfikator dzierżawy umożliwiający powiązanie danych rejestracji z dzierżawą usługi AAD użytkownika. Urząd użytkownika może także zostać udostępniony w celu zezwolenia na rejestrację względem określonych suwerennych chmur. Aby uzyskać więcej informacji, zobacz [Rejestracja suwerennej chmury](#sovereign-cloud-registration).  Zestaw SDK może próbować zarejestrować aplikację dla danego użytkownika w usłudze MAM. W przypadku niepowodzenia rejestracji zestaw będzie okresowo ponawiać próbę rejestracji do czasu wyrejestrowania konta. Próby są zwykle powtarzane co 12–24 godzin. Zestaw SDK dostarcza informacje o stanie kolejnych prób rejestracji w sposób asynchroniczny za pośrednictwem powiadomień.

2. Uwierzytelnienie w usłudze AAD jest wymagane, dlatego najkorzystniej jest zarejestrować konto użytkownika po tym, jak zalogował się on do aplikacji i został pomyślnie uwierzytelniony z użyciem biblioteki ADAL. Identyfikator użytkownika usługi AAD i identyfikator dzierżawy są zwracane przez wywołanie uwierzytelniania biblioteki ADAL w ramach obiektu [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android).
    * Identyfikator dzierżawy pochodzi z metody `AuthenticationResult.getTenantID()`.
    * Informacje o użytkowniku znajdują się w podobiekcie typu `UserInfo`, który pochodzi z klasy `AuthenticationResult.getUserInfo()`, a identyfikator użytkownika usługi AAD jest pobierany z tego obiektu przez wywołanie metody `UserInfo.getUserId()`.

3. Aby wyrejestrować konto z zarządzania przy użyciu usługi Intune, niezbędne jest wywołanie przez aplikację metody `unregisterAccountForMAM()`. Jeśli konto zostało pomyślnie zarejestrowane i jest zarządzane, zestaw SDK wyrejestruje konto i wyczyści powiązane z nim dane. Okresowe ponowne próby rejestracji konta zostaną wstrzymane. Zestaw SDK dostarcza informacje o stanie żądania wyrejestrowania w sposób asynchroniczny za pośrednictwem powiadomienia.

### <a name="sovereign-cloud-registration"></a>Rejestracja suwerennej chmury

Aplikacje, które [wiedzą o suwerennej chmurze](https://www.microsoft.com/trustcenter/cloudservices/nationalcloud), **muszą** udostępniać element `authority` dla elementu `registerAccountForMAM()`.  Można to uzyskać, podając element `instance_aware=true` w parametrach extraQueryParameters elementu acquireToken biblioteki ADAL [1.14.0+](https://github.com/AzureAD/azure-activedirectory-library-for-android/releases/tag/v1.14.0), a następnie wywołując metodę `getAuthority()` dla wartości AuthenticationResult wywołania AuthenticationCallback.

```java
mAuthContext.acquireToken(this, RESOURCE_ID, CLIENT_ID, REDIRECT_URI, PromptBehavior.FORCE_PROMPT, "instance_aware=true",
        new AuthenticationCallback<AuthenticationResult>() {
            @Override
            public void onError(final Exception exc) {
                // authentication failed
            }

            @Override
            public void onSuccess(final AuthenticationResult result) {
                mAuthority = result.getAuthority();
                // handle other parts of the result
            }
        });
```

> [!NOTE]
> Nie ustawiaj elementu metadanych `com.microsoft.intune.mam.aad.Authority` w pliku AndroidManifest.xml.

> [!NOTE]
> Upewnij się, że urząd jest poprawnie ustawiony w Twojej metodzie `MAMServiceAuthenticationCallback::acquireToken()`.

#### <a name="currently-supported-sovereign-clouds"></a>Obecnie obsługiwane suwerenne chmury

1. Arlington

### <a name="important-implementation-notes"></a>Ważne uwagi dotyczące implementacji

#### <a name="authentication"></a>Uwierzytelnianie

* Niedługo po wykonaniu wywołania `registerAccountForMAM()` aplikacja może za pośrednictwem interfejsu `MAMServiceAuthenticationCallback` otrzymać wywołanie zwrotne w innym wątku. Najkorzystniej jest, gdy aplikacja uzyska własny token z biblioteki ADAL przed zarejestrowaniem konta, co pozwoli przyśpieszyć uzyskanie żądanego tokenu. Jeśli aplikacja zwróci prawidłowy token z wywołania zwrotnego, rejestracja będzie kontynuowana, a wynik końcowy zostanie przesłany do aplikacji za pośrednictwem powiadomienia.

* Jeśli aplikacja nie zwróci prawidłowego tokenu usługi AAD, ostatecznym wynikiem próby rejestracji będzie element `AUTHENTICATION_NEEDED`. Jeśli aplikacja otrzyma ten wynik za pośrednictwem powiadomienia, zdecydowanie zaleca się przyspieszenie procesu rejestracji przez uzyskanie tokenu dla użytkownika i zasobu wcześniej zażądanych z metody `acquireToken()` i wywołanie metody `updateToken()` w celu ponownego zainicjowania procesu rejestracji.

* Zarejestrowana metoda `MAMServiceAuthenticationCallback` aplikacji również zostanie wywołana w celu uzyskania tokenu na potrzeby okresowego ewidencjonowania odświeżonych zasad ochrony aplikacji. Jeśli aplikacja nie dostarczy tokenu na żądanie, nie otrzyma powiadomienia, powinna jednak podjąć próbę uzyskania tokenu i wywołania metody `updateToken()` w następnym dogodnym momencie w celu przyspieszenia procesu ewidencjonowania. Jeśli token nie zostanie dostarczony, wywołanie zwrotne nadal będzie wykonywane podczas następnej próby ewidencjonowania.

* Obsługa suwerennych chmur wymaga określenia urzędu.

#### <a name="registration"></a>Rejestracja

* Dla wygody użytkownika metody rejestracji są idempotentne. Na przykład metoda `registerAccountForMAM()` umożliwia zarejestrowanie konta i podjęcie próby rejestracji aplikacji tylko wówczas, gdy konto nie jest jeszcze zarejestrowane, a metoda `unregisterAccountForMAM()` powoduje wyrejestrowanie konta tylko, jeśli jest ono aktualnie zarejestrowane. Kolejne wywołania nie skutkują wykonaniem żadnych operacji, więc wielokrotne wywoływanie tych metod nie przynosi żadnych szkód. Ponadto nie ma gwarancji, że po każdym wywołaniu metody zostanie przesłane powiadomienie o wynikach. Oznacza to, że jeśli metoda `registerAccountForMAM` zostanie wywołana dla tożsamości, która jest już zarejestrowana, powiadomienie może nie zostać ponownie wysłane dla tej tożsamości. Istnieje możliwość, że będą wysyłane powiadomienia, które nie odpowiadają żadnym wywołaniom tych metod, ponieważ zestaw SDK może okresowo podejmować próby rejestracji w tle, a wyrejestrowania mogą być powodowane przez żądania wyczyszczenia danych odbierane z usługi Intune.

* Metody rejestracji można wywoływać dla dowolnej liczby różnych tożsamości, lecz obecnie możliwe jest pomyślne zarejestrowanie tylko jednego konta użytkownika. Jeśli wiele kont użytkowników, które są licencjonowane na potrzeby usługi Intune i podlegają zasadom ochrony aplikacji, zostało zarejestrowanych w tym samym lub zbliżonym czasie, nie ma żadnej gwarancji co do tego, które z nich zostanie zarejestrowane pomyślnie.

* Ponadto można wysłać zapytanie do klasy `MAMEnrollmentManager`, aby sprawdzić, czy określone konto jest zarejestrowane, i pobrać jego bieżący stan za pomocą metody `getRegisteredAccountStatus`. Jeśli dane konto nie jest zarejestrowane, metoda zwróci wynik **null**. Jeśli konto jest zarejestrowane, ta metoda zwróci jego stan jako jedną z pozycji wyliczenia `MAMEnrollmentManager.Result`.

### <a name="result-and-status-codes"></a>Kody wyników i stanu

Po pierwszej rejestracji konto ma stan `PENDING`, który wskazuje, że początkowa próba rejestracji w usłudze MAM była niekompletna. Po zakończeniu próby rejestracji zostaje wysłane powiadomienie zawierające jeden z kodów wyników przedstawionych w poniższej tabeli. Ponadto stan konta zostanie zwrócony przez metodę `getRegisteredAccountStatus()`, dzięki czemu aplikacja zawsze można określić, czy dla danego użytkownika jest zablokowany dostęp do zawartości firmowej. Jeśli próba rejestracji nie powiedzie się, stan konta może z czasem ulec zmianie, ponieważ zestaw SDK będzie podejmować ponowne próby rejestracji w tle.

|Kod wyniku | Objaśnienie |
| -- | -- |
|AUTHORIZATION_NEEDED | Wynik wskazuje, że token nie został dostarczony przez zarejestrowane wystąpienie `MAMServiceAuthenticationCallback` aplikacji lub że dostarczony token jest nieprawidłowy.  Jeśli jest to możliwe, aplikacja powinna uzyskać prawidłowy token i wywołać metodę `updateToken()`. |
| NOT_LICENSED | Użytkownik nie posiada licencji usługi Intune lub próba połączenia się z funkcją zarządzania aplikacjami mobilnymi usługi Intune nie powiodła się.  Aplikacja powinna działać dalej w stanie niezarządzanym (zwykłym), a użytkownik nie powinien być zablokowany.  Jeśli użytkownik uzyska w przyszłości licencję, okresowo odbywać się będą ponowne próby rejestracji. |
| ENROLLMENT_SUCCEEDED | Próba rejestracji zakończyła się pomyślnie lub użytkownik jest już zarejestrowany.  W przypadku pomyślnego przeprowadzenia rejestracji przed tym powiadomieniem zostanie wysłane powiadomienie o odświeżeniu zasad.  Dostęp do danych firmowych powinien być możliwy. |
| ENROLLMENT_FAILED | Próba rejestracji nie powiodła się.  Więcej szczegółowych informacji można znaleźć w dziennikach urządzenia.  Aplikacja nie powinna umożliwiać w tym stanie dostępu do danych firmowych, ponieważ wcześniej ustalono, że użytkownik ma licencję na usługę Intune.|
| WRONG_USER | Tylko jeden użytkownik na urządzenie może zarejestrować aplikację w usłudze zarządzania aplikacjami mobilnymi.  Aby możliwe było pomyślne przeprowadzenie rejestracji jako inny użytkownik, wszystkie zarejestrowane aplikacje muszą wcześniej zostać wyrejestrowane.  W przeciwnym razie bieżąca aplikacja będzie musiała zostać zarejestrowana jako użytkownik główny.  Ta czynność ma miejsce po sprawdzeniu licencji, dlatego użytkownik nie powinien mieć dostępu do danych firmowych do czasu, gdy aplikacja zostanie pomyślnie zarejestrowana.|
| UNENROLLMENT_SUCCEEDED | Wyrejestrowanie zakończyło się powodzeniem.|
| UNENROLLMENT_FAILED | Żądanie wyrejestrowania nie powiodło się.  Więcej szczegółowych informacji można znaleźć w dziennikach urządzenia. |
| PENDING | Próba rejestracji początkowej użytkownika jest w toku.  Aplikacja może zablokować dostęp do firmowych danych do czasu, gdy będzie znany wynik rejestracji, ale nie jest to wymagane. |
| COMPANY_PORTAL_REQUIRED | Użytkownik ma licencję na usługę Intune, ale nie można zarejestrować aplikacji, dopóki na urządzeniu nie zostanie zainstalowana aplikacja Portal firmy. Zestaw SDK aplikacji usługi Intune podejmie próbę zablokowania dostępu do aplikacji dla danego użytkownika i poinformowania go o konieczności instalacji aplikacji Portal firmy (szczegóły poniżej). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Przesłonięcie monitu dotyczącego wymogu instalacji aplikacji Portal firmy (opcjonalne)

Jeśli zostanie uzyskany wynik `COMPANY_PORTAL_REQUIRED`, zestaw SDK zablokuje możliwość wykonywania czynności korzystających z tożsamości, której dotyczyło żądanie rejestracji. Zamiast tego zestaw SDK spowoduje wyświetlenie monitu o pobranie aplikacji Portal firmy. Jeśli nie chcesz, aby w Twojej aplikacji był wyświetlany taki monit, działania mogą obejmować implementację metody `MAMActivity.onMAMCompanyPortalRequired`.

Ta metoda zostaje wywołana zanim zestaw SDK wyświetli domyślny interfejs użytkownika z blokadą. Jeśli w wyniku próby nastąpi zmiana tożsamości działania lub wyrejestrowanie użytkownika, który podjął próbę rejestracji, zestaw SDK nie zablokuje działania. W tej sytuacji ochrona przed wyciekiem danych firmowych zależy od aplikacji. Tylko aplikacje mające wiele tożsamości (omówione w dalszej części) będą mogły zmienić tożsamość działania.

Jeśli nie odziedziczysz `MAMActivity` jawnie (ponieważ narzędzie kompilacji wprowadzi tę zmianę), ale nadal potrzebujesz obsługiwać to powiadomienie, możesz zamiast tego wdrożyć `MAMActivityBlockingListener`.

### <a name="notifications"></a>Powiadomienia

Jeśli dla aplikacji zarejestrowano powiadomienia o typie **MAM_ENROLLMENT_RESULT**, zostanie wysłane powiadomienie `MAMEnrollmentNotification` w celu poinformowania aplikacji o zakończeniu żądania rejestracji. Powiadomienie `MAMEnrollmentNotification` zostanie odebrane za pośrednictwem interfejsu `MAMNotificationReceiver` zgodnie z opisem w sekcji [Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK](#register-for-notifications-from-the-sdk).

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}
```

Metoda `getEnrollmentResult()` zwraca wynik żądania rejestracji.  Ponieważ metoda `MAMEnrollmentNotification` stanowi rozszerzenie metody `MAMUserNotification`, tożsamość użytkownika, dla którego podjęto próbę rejestracji, także jest dostępna. Aby możliwe było odbieranie tych powiadomień, szczegółowo opisanych w sekcji [Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK](#register-for-notifications-from-the-sdk), aplikacja musi zaimplementować interfejs `MAMNotificationReceiver`.

Stan konta zarejestrowanego użytkownika może ulec zmianie po odebraniu powiadomienia dotyczącego rejestracji, jednak nie dzieje się tak zawsze (np. w przypadku otrzymania powiadomienia `AUTHORIZATION_NEEDED` po uzyskaniu bardziej szczegółowego wyniku, takiego jak `WRONG_USER`, jako stan konta zostanie zachowany wynik bardziej szczegółowy).  Po pomyślnym zarejestrowaniu konta stan będzie wyświetlany jako `ENROLLMENT_SUCCEEDED`, dopóki konto nie zostanie wyrejestrowane lub wyczyszczone.

Stan konta zarejestrowanego użytkownika może ulec zmianie po odebraniu powiadomienia dotyczącego rejestracji, jednak nie dzieje się tak zawsze (np. w przypadku otrzymania powiadomienia `AUTHORIZATION_NEEDED` po uzyskaniu bardziej szczegółowego wyniku, takiego jak `WRONG_USER`, jako stan konta zostanie zachowany wynik bardziej szczegółowy).  Po pomyślnym zarejestrowaniu konta stan będzie wyświetlany jako `ENROLLMENT_SUCCEEDED`, dopóki konto nie zostanie wyrejestrowane lub wyczyszczone.

## <a name="app-ca-with-policy-assurance"></a>Mechanizm APP CA z weryfikacją zasad

### <a name="overview"></a>Przegląd
Dzięki użyciu mechanizmu APP CA (dostęp warunkowy) z weryfikacją zasad, dostęp do zasobów jest uzależniony od zastosowanych zasad ochrony aplikacji usługi Intune.  Usługa AAD wymusza to, wymagając od aplikacji, aby była zarejestrowana i zarządzana przez mechanizm APP przed przyznaniem jej tokenu umożliwiającego dostęp do zasoby chronionego za pomocą mechanizmu APP CA z weryfikacją zasad.  Od aplikacji jest wymagane, aby używała brokera biblioteki ADAL na potrzeby uzyskiwania tokenu, a konfiguracja jest taka sama, jak ta opisana powyżej w sekcji [Dostęp warunkowy](#conditional-access)

### <a name="adal-changes"></a>Zmiany w bibliotece ADAL
Biblioteka ADAL ma nowy kod błędu informujący aplikację, że niepowodzenie uzyskania tokenu zostało spowodowane przez niezgodność z funkcją zarządzania APP.  Jeśli aplikacja otrzyma ten kod błędu, musi wywołać zestaw SDK w celu podjęcia próby naprawy zgodności przez zarejestrowanie aplikacji i zastosowanie zasad. Wyjątek zostanie odebrany przez metodę `onError()` biblioteki ADAL `AuthenticationCallback` i będzie zawierał kod błędu `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED`.  W takim przypadku może być rzutowany wyjątek `IntuneAppProtectionPolicyRequiredException`, z którego mogą zostać wyodrębnione dodatkowe parametry umożliwiające korygowanie zgodności (zobacz poniższy przykład kodu). Po pomyślnym przeprowadzeniu korygowania aplikacja można ponownie spróbować uzyskać token za pośrednictwem biblioteki ADAL.

> [!NOTE]
> Ten nowy kod błędu i inne wsparcie dla mechanizmu APP CA z weryfikacją zasad wymagają wersji 1.15.0 (lub nowszej) biblioteki ADAL.

### <a name="mamcompliancemanager"></a>MAMComplianceManager

Interfejs `MAMComplianceManager` jest używany, gdy z biblioteki ADAL zostanie odebrany błąd wymaganych zasad.  Zawiera on metodę `remediateCompliance()`, która powinna być wywoływana w celu podjęcia próby przełączenia aplikacji w stan zgodności. Odwołanie do `MAMComplianceManager` można uzyskać w następujący sposób:

```java
MAMComplianceManager mgr = MAMComponents.get(MAMComplianceManager.class);

// make use of mgr
```

Zwrócone wystąpienie `MAMComplianceManager` na pewno nie będzie puste.

```java
package com.microsoft.intune.mam.policy;

public interface MAMComplianceManager {
    void remediateCompliance(String upn, String aadId, String tenantId, String authority, boolean showUX);
}
```

Metoda `remediateCompliance()` jest wywoływana w celu podjęcia próby przełączenia aplikacji w stan zarządzania, aby spełnić warunki wymagane przez usługę AAD do udzielenia żądanego tokenu.  Pierwsze cztery parametry można wyodrębnić z wyjątku odebranego przez metodę `AuthenticationCallback.onError()` biblioteki ADAL (zobacz poniższy przykład kodu).  Ostatni parametr jest wartością logiczną, która kontroluje, czy środowisko użytkownika jest wyświetlane podczas próby uzyskania zgodności.  Jest to prosty interfejs blokowania postępu udostępniany jako interfejs domyślny dla aplikacji, które nie muszą wyświetlać dostosowanego środowiska użytkownika podczas wykonywania tej operacji.  Ten interfejs powoduje tylko zablokowanie postępu korygowania zgodności i nie wyświetla wyniku końcowego.  Do obsługi powodzenia lub niepowodzenia próby korygowania zgodności aplikacja powinna zarejestrować odbiornik powiadomień (patrz poniżej).

Metoda `remediateCompliance()` może wykonywać rejestrację MAM jako część ustanawiania zgodności.  Aplikacja może odbierać powiadomienia o rejestracji, jeśli zarejestrowała odbiornik powiadomień do obsługi powiadomień o rejestracji.  W zarejestrowanej klasie `MAMServiceAuthenticationCallback` aplikacji zostanie wywołana metoda `acquireToken()` w celu pobrania tokenu na potrzeby rejestracji MAM. Metoda `acquireToken()` zostanie wywołana, zanim aplikacja uzyska własny token, dlatego zadania tworzenia konta lub zadania księgowe wykonywane przez aplikację po pomyślnym uzyskaniu tokenu mogą jeszcze nie być wykonane.  W takim przypadku wywołanie zwrotne musi mieć możliwość uzyskania tokenu.  Jeśli nie można zwrócić tokenu z metody `acquireToken()`, próba korygowania zgodności nie powiedzie się.  Jeśli metoda `updateToken()` zostanie wywołana później z prawidłowym tokenem dla żądanego zasobu, korygowanie zgodności zostanie natychmiast ponowione z użyciem tego tokenu.

> [!NOTE]
> Dyskretne uzyskiwanie tokenu nadal będzie możliwe w metodzie `acquireToken()`, ponieważ użytkownik zostanie już poinstruowany o konieczności zainstalowania brokera i zarejestrowania urządzenia przed odebraniem błędu `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED`.  W wyniku tego broker będzie miał prawidłowy token odświeżania w swojej pamięci podręcznej, co umożliwi dyskretne uzyskanie żądanego tokenu wymaganego do pomyślnego zakończenia operacji.

Oto przykład odebrania błędu wymaganych zasad w metodzie `AuthenticationCallback.onError()` i wywołania klasy `MAMComplianceManager` do obsługi tego błędu.

```java
public void onError(@Nullable Exception exc) {
    if (exc instanceof AuthenticationException && 
        ((AuthenticationException) exc).getCode() == ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED) {

        final IntuneAppProtectionPolicyRequiredException policyRequiredException = 
            (IntuneAppProtectionPolicyRequiredException) ex;

        final String upn = policyRequiredException.getAccountUpn();
        final String aadId = policyRequiredException.getAccountUserId();
        final String tenantId = policyRequiredException.getTenantId();
        final String authority = policyRequiredException.getAuthorityURL();

        MAMComplianceManager complianceManager = MAMComponents.get(MAMComplianceManager.class);
        complianceManager.remediateCompliance(upn, aadId, tenantId, authority, showUX);
    }
}
```

### <a name="status-notifications"></a>Powiadomienia o stanie

Jeśli dla aplikacji zarejestrowano powiadomienia o typie **COMPLIANCE_STATUS**, zostanie wysłane powiadomienie `MAMComplianceNotification` w celu poinformowania aplikacji o końcowym stanie próby korygowania zgodności. Powiadomienie `MAMComplianceNotification` zostanie odebrane za pośrednictwem interfejsu `MAMNotificationReceiver` zgodnie z opisem w sekcji [Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK](#register-for-notifications-from-the-sdk).

```java
public interface MAMComplianceNotification extends MAMUserNotification {
    MAMCAComplianceStatus getComplianceStatus();
    String getComplianceErrorTitle();
    String getComplianceErrorMessage();
}
```

Metoda `getComplianceStatus()` zwraca wynik próby korygowania zgodności jako wartość z wyliczenia `MAMCAComplianceStatus`.

|Kod stanu | Objaśnienie |
| -- | -- |
| UNKNOWN | Stan jest nieznany. Może to wskazywać na nieprzewidzianą przyczynę niepowodzenia. Dodatkowe informacje można znaleźć w dziennikach portalu firmy. |
| COMPLIANT | Korygowanie zgodności zakończyło się pomyślnie i aplikacja jest teraz zgodna z zasadami. Powinna zostać ponowiona próba uzyskania tokenu biblioteki ADAL. |
| NOT_COMPLIANT | Próba skorygowania zgodności nie powiodła się.  Aplikacja nie jest zgodna i próba uzyskania tokenu biblioteki ADAL nie powinna być ponawiana do czasu naprawienia warunku błędu.  Dodatkowe informacje o błędzie są wysyłane za pomocą powiadomienia MAMComplianceNotification. |
| SERVICE_FAILURE | Wystąpiło niepowodzenie podczas próby pobrania danych zgodności z usługi Intune. Dodatkowe informacje można znaleźć w dziennikach portalu firmy. |
| NETWORK_FAILURE | Wystąpił błąd podczas nawiązywania połączenia z usługą Intune. Aplikacja powinna ponowić próbę uzyskania tokenu po przywróceniu połączenia sieciowego. |
| CLIENT_ERROR | Próba skorygowania zgodności nie powiodła się z jakiegoś powodu związanego z klientem.  Może to być na przykład brak tokenu lub nieprawidłowy użytkownik. Dodatkowe informacje o błędzie są wysyłane za pomocą powiadomienia MAMComplianceNotification. |
| PENDING | Próba skorygowania zgodności nie powiodła się, ponieważ z usługi nie otrzymano jeszcze odpowiedzi dotyczącej stanu pomimo przekroczenia limitu czasu. Aplikacja powinna spróbować później uzyskać swój token. |
| COMPANY_PORTAL_REQUIRED | Aby korygowanie zgodności zakończyło się powodzeniem, na urządzeniu musi być zainstalowany portal firmy.  Jeśli portal firmy został już zainstalowany na urządzeniu, aplikacja wymaga ponownego uruchomienia.  W takim przypadku zostanie wyświetlone okno dialogowe z prośbą o ponowne uruchomienie aplikacji. |

Jeśli stan zgodności ma wartość `MAMCAComplianceStatus.COMPLIANT`, aplikacja powinna ponownie zainicjować proces uzyskiwania swojego oryginalnego tokenu (dla własnego zasobu). Jeśli próba skorygowania zgodności zakończy się niepowodzeniem, metody `getComplianceErrorTitle()` i `getComplianceErrorMessage()` zwrócą zlokalizowane ciągi, które mogą być wyświetlone dla użytkownika końcowego w aplikacji (jeśli takie zachowanie zostanie skonfigurowane).  Większości błędów nie można naprawić za pomocą aplikacji, dlatego w ogólnych przypadkach najlepszym rozwiązaniem będzie zakończenie niepowodzeniem procesu tworzenia konta lub logowania i zezwolenie użytkownikowi na późniejsze ponowienie próby.  Jeśli niepowodzenie będzie się powtarzać, dzienniki funkcji MAM mogą pomóc w określeniu przyczyny.  Użytkownik końcowy może przesłać dzienniki, postępując według wskazówek zamieszczonych [tutaj](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android "Wysyłanie dzienników do działu pomocy technicznej Twojej firmy pocztą e-mail").

Ponieważ metoda `MAMComplianceNotification` rozszerza metodę `MAMUserNotification`, tożsamość użytkownika, dla którego podjęto próbę korygowania, jest także dostępna.

Oto przykład zarejestrowania odbiornika za pomocą anonimowej klasy, co umożliwia zaimplementowanie interfejsu MAMNotificationReceiver:

```java
final MAMNotificationReceiverRegistry notificationRegistry = MAMComponents.get(MAMNotificationReceiverRegistry.class);
// create a receiver
final MAMNotificationReceiver receiver = new MAMNotificationReceiver() {
    public boolean onReceive(MAMNotification notification) {
        if (notification.getType() == MAMNotificationType.COMPLIANCE_STATUS) {
            MAMComplianceNotification complianceNotification = (MAMComplianceNotification) notification;
            
            // take appropriate action based on complianceNotification.getComplianceStatus()
            
            // unregister this receiver if no longer needed
            notificationRegistry.unregisterReceiver(this, MAMNotificationType.COMPLIANCE_STATUS);
        }
        return true;
    }
};
// register the receiver
notificationRegistry.registerReceiver(receiver, MAMNotificationType.COMPLIANCE_STATUS);
```

> [!NOTE]
> Odbiornik powiadomień musi być zarejestrowany przed wywołaniem metody `remediateCompliance()` w celu uniknięcia sytuacji wyścigu, co może spowodować pominięcie powiadomienia.

### <a name="implementation-notes"></a>Uwagi dotyczące implementacji

> [!NOTE]
> Metoda `MAMServiceAuthenticationCallback.acquireToken()` aplikacji musi przekazać wartość *true* nowej flagi `forceRefresh` do metody `acquireTokenSilentSync()` w celu wymuszenia odświeżenia z brokera.  Jest to obejście problemu z buforowaniem tokenów w bibliotece ADAL, który może mieć wpływ na tokeny usługi zarządzania aplikacjami mobilnymi. Ogólnie rzecz biorąc, wygląda to następująco:
>
> ```java
> AuthenticationResult result = acquireTokenSilentSync(resourceId, clientId, userId, /* forceRefresh */ true);
> ```

> [!NOTE]
> Jeśli chcesz wyświetlić niestandardowe środowisko użytkownika blokowania podczas próby korygowania, musisz przekazać wartość *false* parametru showUX do metody `remediateCompliance()`. Przed wywołaniem metody `remediateCompliance()` należy się upewnić, że środowisko użytkownika jest wyświetlone i odbiornik powiadomień jest zarejestrowany.  Pozwoli to zapobiec sytuacji wyścigu, w której powiadomienie może zostać pominięte, jeśli metoda `remediateCompliance()` nie powiedzie się bardzo szybko.  Na przykład metoda `onCreate()` lub `onMAMCreate()` podklasy Activity to idealne miejsce do zarejestrowania odbiornika powiadomień, a następnie do wywołania metody `remediateCompliance()`.  Parametry metody `remediateCompliance()` mogą być przekazywane do Twojego środowiska użytkownika jako dodatkowe intencje.  Po odebraniu powiadomienia o stanie zgodności można wyświetlić wynik lub po prostu zakończyć działanie.

> [!NOTE]
> Metoda `remediateCompliance()` spowoduje zarejestrowanie konta i dokona próby rejestracji.  Po uzyskaniu głównego tokenu nie jest wymagane wywołanie metody `registerAccountForMAM()`, chociaż można to zrobić. Z drugiej strony jeśli uzyskanie tokenu przez aplikację nie powiedzie się i konieczne jest usunięcie konta użytkownika, musi zostać wywołana metoda `unregisterAccountForMAM()`, aby usunąć konto i zapobiec ponownym próbom rejestracji w tle.

## <a name="protecting-backup-data"></a>Ochrona danych kopii zapasowej

Począwszy od systemu Android Marshmallow (interfejs API w wersji 23), na potrzeby aplikacji są dostępne dwa sposoby tworzenia kopii zapasowych danych. Każda opcja jest dostępna dla aplikacji i wymaga różnych kroków w celu zapewnienia, że ochrona danych usługi Intune jest implementowana prawidłowo. Możesz przejrzeć tabelę poniżej dotyczącą odpowiednich akcji wymaganych do osiągnięcia poprawnego zachowania w zakresie ochrony danych.  Aby uzyskać więcej informacji na temat metod wykonywania kopii zapasowych, zobacz [Przewodnik po interfejsie API systemu Android](https://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Automatyczne wykonywanie kopii zapasowej dla aplikacji

System Android oferuje obecnie funkcję [automatycznego tworzenia pełnej kopii zapasowej](https://developer.android.com/guide/topics/data/autobackup.html) w usłudze Dysk Google dla aplikacji na urządzeniach z systemem Android Marshmallow, niezależnie od docelowego interfejsu API aplikacji. Jeśli w pliku AndroidManifest.xml dla elementu `android:allowBackup` została jawnie ustawiona wartość **false**, to aplikacja nigdy nie zostanie umieszczona w kolejce do wykonywania kopii zapasowej przez system Android i dane „firmowe” pozostaną w aplikacji. W takim przypadku nie są wymagane żadne dalsze działania.

Jednak domyślnie atrybut `android:allowBackup` ma wartość true, nawet jeśli atrybut `android:allowBackup` nie został określony w pliku manifestu. Oznacza to, że kopia zapasowa wszystkich danych aplikacji jest automatycznie tworzona na koncie usługi Dysk Google użytkownika. Jest to zachowanie domyślne, które stanowi **ryzyko przecieku danych**. Z tego powodu zestaw SDK wymaga wprowadzenia zmian przedstawionych poniżej w celu zapewnienia ochrony danych.  Zastosowanie poniższych wskazówek jest ważne, aby właściwie ochronić dane klienta, jeśli aplikacja ma działać na urządzeniach z systemem Android Marshmallow.  

Usługa Intune umożliwia korzystanie ze wszystkich [funkcji automatycznego tworzenia kopii zapasowych](https://developer.android.com/guide/topics/data/autobackup.html) dostępnych w systemie Android, w tym możliwość definiowania niestandardowych reguł w pliku XML, należy jednak wykonać poniższą procedurę, aby zabezpieczyć dane:

1. Jeśli aplikacja **nie** używa własnych niestandardowych klas BackupAgent, użyj domyślnej klasy MAMBackupAgent, aby zezwolić na automatyczne tworzenie pełnych kopii zapasowych zgodnych z zasadami usługi Intune. Umieść następujące wpisy w manifeście aplikacji:

    ```xml
    android:fullBackupOnly="true"
    android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```


2. **[Opcjonalnie]** Jeśli zaimplementowano opcjonalną niestandardową klasę BackupAgent, należy upewnić się, że jest używana klasa MAMBackupAgent lub MAMBackupAgentHelper. Zobacz sekcje poniżej. Rozważ zmianę na klasę **MAMDefaultFullBackupAgent** usługi Intune (opisaną w kroku 1), która umożliwia łatwe tworzenie kopii zapasowych w systemie Android w wersji M i nowszych.

3. Gdy zdecydujesz, który typ pełnej kopii zapasowej powinna otrzymać Twoja aplikacja (niefiltrowany, filtrowany lub żaden), musisz ustawić dla atrybutu `android:fullBackupContent` wartość true, false lub zasób XML w aplikacji.

4. Następnie _**musisz**_ skopiować całą zawartość elementu `android:fullBackupContent` do tagu metadanych o nazwie `com.microsoft.intune.mam.FullBackupContent` w manifeście.

    **Przykład 1**: jeśli aplikacja ma mieć możliwość tworzenia pełnych kopii zapasowych bez wykluczeń, dla atrybutu `android:fullBackupContent` i tagu metadanych `com.microsoft.intune.mam.FullBackupContent` należy ustawić wartość **true**:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Przykład 2**: jeśli aplikacja ma korzystać z niestandardowej klasy BackupAgent bez automatycznego wykonywania pełnych kopii zapasowych zgodnych z zasadami usługi Intune, musisz ustawić dla atrybutu i tagu metadanych wartość **false**:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Przykład 3**: jeśli chcesz, aby aplikacja umożliwiała tworzenie pełnych kopii zapasowych zgodnie z niestandardowymi zasadami określonymi w pliku XML, przypisz do atrybutu i tagu metadanych ten sam zasób XML:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Kopie zapasowe typu klucz/wartość

Opcja [Kopie zapasowe typu klucz/wartość](https://developer.android.com/guide/topics/data/keyvaluebackup.html) jest dostępna dla wszystkich interfejsów API w wersji 8 i nowszych. Umożliwia ona przesyłanie danych aplikacji do usługi [Android Backup Service](https://developer.android.com/google/backup/index.html). Ilość danych na użytkownika aplikacji jest ograniczona do 5 MB. Jeśli korzystasz z opcji Kopie zapasowe typu klucz/wartość, użyj klasy **BackupAgentHelper** lub **BackupAgent**.

### <a name="backupagenthelper"></a>BackupAgentHelper

Klasa BackupAgentHelper jest prostsza do zaimplementowania niż klasa BackupAgent zarówno w zakresie natywnych funkcji systemu Android, jak i integracji z funkcją MAM usługi Intune. Klasa BackupAgentHelper umożliwia deweloperowi zarejestrowanie całych plików i udostępnionych preferencji (odpowiednio) w klasach **FileBackupHelper** i **SharedPreferencesBackupHelper**, które są następnie dodawane do klasy BackupAgentHelper przy jej tworzeniu. Wykonaj poniższe kroki, aby użyć klasy BackupAgentHelper z funkcją zarządzania aplikacjami mobilnymi w usłudze Intune:

1. Aby użyć klasy BackupAgentHelper do tworzenia kopii zapasowych obejmujących wiele tożsamości, wykonaj kroki opisane w przewodniku dla użytkowników systemu Android poświęconym [rozszerzaniu klasy BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).

2. Klasa może rozszerzać odpowiednik klasy BackupAgentHelper, FileBackupHelper i SharedPreferencesBackupHelper w usłudze zarządzania aplikacjami mobilnymi.

|Klasa systemu Android | Odpowiednik w usłudze zarządzania aplikacjami mobilnymi |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Postępując zgodnie z poniższymi wskazówkami, można pomyślnie tworzyć i przywracać kopie zapasowe obejmujące wiele tożsamości.

### <a name="backupagent"></a>BackupAgent

Klasa BackupAgent umożliwia o wiele dokładniejsze określenie danych, których kopie zapasowe mają być tworzone. Ponieważ odpowiedzialność za implementację leży w znacznym stopniu po stronie programisty, zapewnienie odpowiedniej ochrony danych przez usługę Intune wymaga większej liczby kroków. Większa część pracy spoczywa na Tobie jako deweloperze, dlatego integracja usługi Intune wymaga nieco więcej wysiłku.

**Integracja usługi zarządzania aplikacjami mobilnymi:**

1. Dokładnie przeczytaj skierowany do użytkowników systemu Android przewodnik poświęcony funkcji [Kopie zapasowe typu klucz/wartość](https://developer.android.com/guide/topics/data/keyvaluebackup.html), zwłaszcza sekcję dotyczącą [rozszerzania klasy BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent), aby mieć pewność, że implementacja przebiega zgodnie z wytycznymi dla systemu Android.

2. Rozszerz klasę `MAMBackupAgent` przy użyciu odpowiedniej klasy.

**Kopie zapasowe obejmujące wiele tożsamości:**

1. Przed rozpoczęciem tworzenia kopii zapasowej upewnij się, że **administrator IT zezwolił na wykonywanie kopii zapasowych** plików lub innych buforów danych, których kopie zapasowe chcesz utworzyć, w scenariuszach obejmujących wiele tożsamości. Możesz to sprawdzić, korzystając z funkcji `isBackupAllowed` w klasach `MAMFileProtectionManager` i `MAMDataProtectionManager`. Jeśli utworzenie kopii zapasowej pliku lub buforu danych jest niedozwolone, nie należy próbować uwzględniać go w kopii zapasowej.

2. Jeśli w pewnym momencie podczas tworzenia kopii zapasowej chcesz utworzyć kopię zapasową tożsamości dla plików sprawdzonych w kroku 1, musisz użyć wywołania `backupMAMFileIdentity(BackupDataOutput data, File … files)` z użyciem plików, z których mają zostać wyodrębnione dane. Spowoduje to automatyczne utworzenie nowych jednostek kopii zapasowej i zapisanie ich do elementu `BackupDataOutput` . Te jednostki zostaną automatycznie użyte podczas przywracania.

**Przywracanie wielu tożsamości**

W podręczniku tworzenia kopii zapasowych danych opisano ogólny algorytm przywracania danych aplikacji oraz przedstawiono przykładowy kod w sekcji [Rozszerzanie klasy BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent). W celu pomyślnego przywrócenia kopii zapasowej obejmującej wiele tożsamości należy zastosować się do ogólnej struktury zaprezentowanej w przykładowym kodzie, zwracając szczególną uwagę na następujące kwestie:

1. Do przechodzenia między wpisami kopii zapasowej należy używać pętli `while(data.readNextHeader())`*.

2. Jeśli metoda `data.getKey()`* nie odpowiada kluczowi wpisanemu w elemencie `onBackup`, należy użyć wywołania `data.skipEntityData()`*. Jeśli ten krok nie zostanie wykonany, przywrócenie danych może się nie powieść.

3. Należy unikać cofania się podczas przetwarzania wpisów kopii zapasowej w ramach konstrukcji `while(data.readNextHeader())`*, ponieważ wpisy zapisywane automatycznie zostaną utracone.

* Gdzie `data` to lokalna nazwa zmiennej **MAMBackupDataInput** przekazanej do aplikacji podczas przywracania.

## <a name="multi-identity-optional"></a>Wiele tożsamości (opcjonalnie)

### <a name="overview"></a>Przegląd
Domyślnie zestaw SDK aplikacji usługi Intune będzie stosować zasady do aplikacji jako całości. Wiele tożsamości to opcjonalna funkcja ochrony aplikacji usługi Intune, którą można włączyć w celu zezwolenia na stosowanie zasad na poziomie poszczególnych tożsamości. Wymaga to znacznie pełniejszego uczestnictwa aplikacji niż inne funkcje ochrony aplikacji.

> [!NOTE]
> Brak odpowiedniego udziału aplikacji może spowodować wycieki danych i inne problemy z zabezpieczeniami.

Po zarejestrowaniu urządzenia lub aplikacji przez użytkownika zestaw SDK rejestruje tę tożsamość i uznaje ją za podstawową tożsamość zarządzaną w usłudze Intune. Inni użytkownicy w aplikacji są traktowani jako niezarządzani z nieograniczonymi ustawieniami zasad.

> [!NOTE]
> Aktualnie obsługiwana jest tylko jedna tożsamość zarządzana w usłudze Intune na urządzenie.

Tożsamość jest definiowana jako ciąg. W tożsamościach **jest rozróżniana wielkość liter**, natomiast żądania tożsamości wysyłane do zestawu SDK mogą nie zwracać tej samej wielkości liter, której pierwotnie użyto podczas ustawiania tożsamości.

Aplikacja *musi* poinformować zestaw SDK aplikacji, gdy zamierza zmienić aktywną tożsamość. W niektórych przypadkach zestaw SDK również powiadomi aplikację, gdy wymagana jest zmiana tożsamości. Jednak w większości przypadków funkcja MAM nie ma informacji, jakie w określonym momencie dane są wyświetlane w interfejsie użytkownika lub używane w wątku, w związku z czym funkcja MAM korzysta z aplikacji, aby ustawić poprawną tożsamość w celu uniknięcia wycieku danych. W poniższych sekcjach zostaną przedstawione pewne konkretne scenariusze, w ramach których wymagana będzie akcja aplikacji.

### <a name="enabling-multi-identity"></a>Włączanie wielu tożsamości

Domyślnie wszystkie aplikacje są traktowane jako aplikacje z obsługą jednej tożsamości. Możesz zadeklarować, że aplikacja obsługuje wiele tożsamości, umieszczając następujące metadane w pliku AndroidManifest.xml.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Ustawianie tożsamości

Deweloperzy mogą ustawić tożsamość użytkownika aplikacji na następujących poziomach (w kolejności od najwyższego):

  1. Poziom wątku
  2. Poziom `Context` (zwykle działania `Activity`)
  3. Poziom procesu

Tożsamość ustawiona na poziomie wątku zastępuje tożsamość ustawioną na poziomie `Context`, która zastępuje tożsamość ustawioną na poziomie procesu. Tożsamość ustawiona na poziomie `Context` jest używana tylko w odpowiednio powiązanych scenariuszach. Na przykład operacje we/wy na plikach nie mają skojarzonego elementu `Context`. Najczęściej aplikacje ustawią tożsamość `Context` w ramach działania `Activity`. Aplikacja *nie może* wyświetlać danych na potrzeby tożsamości zarządzanej, chyba że tożsamość `Activity` jest ustawiona na tę samą tożsamość. Ogólnie rzecz biorąc tożsamość na poziomie procesu jest przydatna jedynie wtedy, gdy aplikacja pracuje tylko z jednym użytkownikiem jednocześnie w ramach wszystkich wątków. W przypadku wielu aplikacji korzystanie z tej funkcji może nie być konieczne.

Jeśli aplikacja używa kontekstu `Application` w celu uzyskania usług systemowych, upewnij się, że ustawiono tożsamość wątku bądź procesu lub że ustawiono tożsamość interfejsu użytkownika w kontekście `Application` aplikacji.

Aby zapewnić obsługę szczególnych przypadków podczas aktualizowania tożsamości interfejsu użytkownika za pomocą elementu `setUIPolicyIdentity` lub `switchMAMIdentity`, do obu metod można przekazać zestaw wartości `IdentitySwitchOption`.

* `IGNORE_INTENT`: użyj w przypadku żądania przełączenia tożsamości, które powinno zignorować intencję skojarzoną z bieżącym działaniem.
  Przykład:

  1. Aplikacja otrzymuje intencję z tożsamości zarządzanej zawierającej zarządzany dokument i wyświetla ten dokument.
  2. Użytkownik przełącza się do swojej tożsamości osobistej, dzięki czemu Twoja aplikacja żąda przełączenia tożsamości interfejsu użytkownika. W tożsamości osobistej Twoja aplikacja już nie wyświetla dokumentu, więc używasz ustawienia `IGNORE_INTENT` podczas żądania przełączenia tożsamości.

  Jeśli nie zostanie to ustawione, zestaw SDK przyjmie założenie, że w aplikacji nadal jest używana najnowsza intencja. W takim przypadku zasady odbierania dla nowej tożsamości będą traktować intencję jako dane przychodzące i użyją jej tożsamości.

>[!NOTE]
> Ponieważ ustawienie `CLIPBOARD_SERVICE` jest używane na potrzeby operacji interfejsu użytkownika, zestaw SDK używa tożsamości interfejsu użytkownika działania pierwszego planu dla operacji `ClipboardManager`.
> Do ustawiania tożsamości i pobierania ustawionych wcześniej wartości tożsamości służą następujące metody w klasie `MAMPolicyManager`.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

/**
   * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This DOES take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use this function.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);
  ```

>[!NOTE]
> Tożsamość aplikacji można wyczyścić, ustawiając dla niej wartość „null”.
>
> Pusty ciąg może być używany jako tożsamość, w odniesieniu do której nigdy nie będzie mieć zastosowania zasada ochrony aplikacji.

#### <a name="results"></a>Wyniki
Wszystkie metody używane do ustawiania tożsamości raportują wynikowe wartości zwrotne za pośrednictwem klasy `MAMIdentitySwitchResult`. Istnieją cztery wartości, które mogą zostać zwrócone:

| Wartość zwracana | Scenariusz |
|--|--|
| SUCCEEDED | Zmiana tożsamości zakończyła się pomyślnie. |
| NOT_ALLOWED  | Zmiana tożsamości jest niedozwolona. Ma to miejsce, jeśli zostanie podjęta próba ustawienia tożsamości interfejsu użytkownika (kontekstu), gdy dla bieżącego wątku jest już ustawiona inna tożsamość. |
| CANCELLED | Użytkownik anulował zmianę tożsamości, czyli prawdopodobnie nacisnął przycisk Wstecz w monicie o podanie kodu PIN lub uwierzytelnienie. |
| FAILED | Z nieokreślonego powodu nie można zmienić tożsamości.|

Przed wyświetleniem lub użyciem danych firmowych aplikacja powinna upewnić się, że przełączenie tożsamości zakończyło się pomyślnie. Obecnie przełączanie tożsamości procesu i wątku zawsze powiedzie się dla aplikacji z włączoną obsługą wielu tożsamości, jednak firma Microsoft zastrzega sobie prawo do dodania warunków błędów. Przełączenie tożsamości interfejsu użytkownika może zakończyć się niepowodzeniem w przypadku podania nieprawidłowych argumentów, jeśli będą one powodowały konflikt z tożsamością wątku, lub jeśli użytkownik anulował wymagania dotyczące uruchamiania warunkowego (np. przez naciśnięcie przycisku Wstecz na ekranie numeru PIN).


W przypadku ustawienia tożsamości na poziomie kontekstu wynik jest raportowany asynchronicznie. Jeśli kontekst jest działaniem, zestaw SDK nie będzie w stanie określić, czy zmiana tożsamości powiodła się, dopóki nie zostanie wykonane warunkowe uruchomienie, co może wymagać od użytkownika wprowadzenia numeru PIN lub podania poświadczeń firmowych. Oczekuje się, że aplikacja zaimplementuje metodę `MAMSetUIIdentityCallback`, aby otrzymać ten wynik. Dla tego parametru jest dozwolone podanie wartości „null”.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Można również ustawić tożsamość działania bezpośrednio przy użyciu metody w klasie `MAMActivity`, zamiast wykonywać wywołanie `MAMPolicyManager.setUIPolicyIdentity`. W tym celu użyj następującej metody:

```java
     public final void switchMAMIdentity(final String newIdentity, final EnumSet<IdentitySwitchOption> options);
```

Możesz również zastąpić metodę w klasie `MAMActivity`, aby otrzymywać powiadomienia o wynikach prób zmiany tożsamości danego działania.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

Jeśli nie zastąpisz metody `onSwitchMAMIdentityComplete` (lub nie wywołasz metody `super`), zakończone niepowodzeniem przełączanie tożsamości w ramach działania spowoduje zakończenie działania. Jeśli zastąpisz metodę, musisz zadbać, aby dane firmowe nie były wyświetlane po zakończonym niepowodzeniem przełączaniu tożsamości.

>[!NOTE]
> Przełączenie tożsamości może wymagać ponownego utworzenia odpowiedniego działania. W takim przypadku wywołanie zwrotne metody `onSwitchMAMIdentityComplete` zostanie dostarczone do nowego wystąpienia tego działania.


### <a name="implicit-identity-changes"></a>Niejawne zmienianie tożsamości

Oprócz możliwości ustawiania tożsamości przez aplikację tożsamość wątku lub kontekstu może zostać zmieniona na podstawie transferu danych przychodzących od innej aplikacji zarządzanej przez usługę Intune i objętej zasadami ochrony aplikacji.

#### <a name="examples"></a>Przykłady

1. Jeśli działanie zostanie uruchomione z klasy `Intent` wysłanej przez inną aplikację z funkcją MAM, tożsamość tego działania zostanie ustawiona na podstawie obowiązującej tożsamości w drugiej aplikacji w chwili wysłania klasy `Intent`.

2. W przypadku usług tożsamość wątku zostanie ustawiona w podobny sposób na czas trwania wywołania metody `onStart` lub `onBind`. Wywołania do klasy `Binder` zwrócone z metody `onBind` także powodują tymczasowe ustawienie tożsamości wątku.

3. Wywołania do klasy `ContentProvider` podobnie ustawią tożsamość wątku na czas ich trwania.


    Ponadto interakcja użytkownika z działaniem może spowodować niejawne przełączenie tożsamości.

    **Przykład:** naciśnięcie przez użytkownika przycisku anulowania w monicie o uwierzytelnienie podczas operacji `Resume`, spowoduje niejawne przełączenie do pustej tożsamości.

    Aplikacja ma możliwość otrzymania powiadomienia o tych zmianach i może ich zabronić, jeśli będzie to konieczne. Klasy `MAMService` i `MAMContentProvider` prezentują następującą metodę, którą mogą zastąpić podklasy:

    ```java
    public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchResultCallback callback);
    ```

    W przypadku klasy `MAMActivity` dodatkowy parametr znajduje się w metodzie:

    ```java
    public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchReason reason,
      final AppIdentitySwitchResultCallback callback);
    ```

    * Parametr `AppIdentitySwitchReason` przechwytuje źródło niejawnego przełączenia i może akceptować wartości `CREATE`, `RESUME_CANCELLED` i `NEW_INTENT`.  Przyczyna `RESUME_CANCELLED` jest używana wówczas, gdy wznowienie działania powoduje wyświetlenie monitu o podanie kodu PIN, uwierzytelnienie lub innego interfejsu użytkownika zgodności i użytkownik próbuje anulować ten interfejs użytkownika, na ogół korzystając z przycisku Wstecz.


    * Metoda `AppIdentitySwitchResultCallback` wygląda następująco:

      ```java
      public interface AppIdentitySwitchResultCallback {
          /**
            * @param result
            *            whether the identity switch can proceed.
            */
          void reportIdentitySwitchResult(AppIdentitySwitchResult result);
        }
        ```

      Gdzie parametr ```AppIdentitySwitchResult``` ma wartość `SUCCESS` lub `FAILURE`.

Metoda `onMAMIdentitySwitchRequired` jest wywoływana dla wszystkich niejawnych zmian tożsamości z wyjątkiem tych wykonywanych za pośrednictwem klasy Binder zwróconych z klasy `MAMService.onMAMBind`. Implementacje domyślne klasy `onMAMIdentitySwitchRequired` powodują natychmiastowe wywołanie metody:

* `reportIdentitySwitchResult(FAILURE)`, gdy przyczyna to `RESUME_CANCELLED`.

* `reportIdentitySwitchResult(SUCCESS)` we wszystkich innych przypadkach.

  Nie oczekuje się, że większość aplikacji będzie musiała blokować lub opóźniać przełączanie tożsamości w inny sposób. Jeśli jednak zajdzie taka potrzeba, należy rozważyć następujące kwestie:

  * Jeśli przełączanie tożsamości jest zablokowane, skutek jest taki sam, jak w przypadku uniemożliwienia transferu danych przychodzących przez ustawienia udostępniania `Receive`.

  * Jeśli usługa jest uruchomiona w wątku głównym, klasa `reportIdentitySwitchResult` **musi** być wywoływana synchronicznie, w przeciwnym razie wątek interfejsu użytkownika ulegnie zawieszeniu.

  * W przypadku tworzenia obiektu **`Activity`** metoda `onMAMIdentitySwitchRequired` zostanie wywołana przed metodą `onMAMCreate`. Jeśli aplikacja musi wyświetlić interfejs użytkownika w celu ustalenia, czy zezwolić na przełączenie tożsamości, ten interfejs użytkownika musi zostać pokazany przy użyciu *innego* działania.

  * W przypadku obiektu **`Activity`** , dla którego żądanie przełączenia do pustej tożsamości ma przyczynę `RESUME_CANCELLED`, aplikacja musi zmodyfikować wznowione działanie, tak aby były wyświetlane dane spójne z tym przełączeniem tożsamości.  Jeśli nie jest to możliwe, aplikacja powinna odmówić przełączenia, a użytkownik zostanie ponownie poproszony o przestrzeganie zasad dla wznawianej tożsamości (np. przez wyświetlenie ekranu wprowadzania numeru PIN aplikacji).

    > [!NOTE]
    > Aplikacja z obsługą wielu tożsamości zawsze będzie otrzymywać dane przychodzące z aplikacji zarządzanych i niezarządzanych. Na aplikacji leży odpowiedzialność za to, aby traktować dane z zarządzanych tożsamości w zarządzany sposób.

  Jeśli żądana tożsamość jest zarządzana (w celu sprawdzenia można użyć metody `MAMPolicyManager.getIsIdentityManaged`), ale aplikacja nie może użyć danego konta (np. ponieważ konta, takie jak konta e-mail, muszą najpierw zostać skonfigurowane w aplikacji), to należy odmówić przełączenia tożsamości.

#### <a name="build-plugin--tool-considerations"></a>Zagadnienia dotyczące wtyczki/narzędzia kompilacji
Jeśli nie dziedziczysz jawnie z klasy `MAMActivity`, `MAMService` lub `MAMContentProvider` (ponieważ pozwalasz, aby narzędzie do kompilacji wprowadziło tę zmianę), lecz nadal potrzebujesz przetworzyć przełączniki tożsamości, możesz zamiast tego zaimplementować interfejs `MAMActivityIdentityRequirementListener` (w przypadku klasy `Activity`) lub `MAMIdentityRequirementListener` (w przypadku klas `Service` i `ContentProviders`).
Dostęp do zachowania domyślnego dla `MAMActivity.onMAMIdentitySwitchRequired` można uzyskać poprzez wywołanie metody statycznej `MAMActivity.defaultOnMAMIdentitySwitchRequired(activity, identity,
reason, callback)`.

Podobnie, jeśli musisz przesłonić `MAMActivity.onSwitchMAMIdentityComplete`, możesz wdrożyć `MAMActivityIdentitySwitchListener` bez jawnego dziedziczenia z `MAMActivity`.

### <a name="preserving-identity-in-async-operations"></a>Zachowywanie tożsamości w operacjach asynchronicznych
Typowym zachowaniem operacji w wątku interfejsu użytkownika jest wysyłanie zadań w tle do innego wątku. Aplikacja o wielu tożsamościach powinna upewnić się, że te zadania w tle działają z wykorzystaniem odpowiedniej tożsamości, która często jest taka sama, jak tożsamość używana przez działanie, które je wysłało. Zestaw SDK zarządzania aplikacjami mobilnymi zapewnia `MAMAsyncTask` i `MAMIdentityExecutors`, aby ułatwić zachowywanie tożsamości.
Te klasy muszą być używane, jeśli operacja asynchroniczna może zapisywać dane firmowe do pliku lub może komunikować się z innymi aplikacjami.

#### <a name="mamasynctask"></a>MAMAsyncTask

Aby użyć klasy `MAMAsyncTask`, skorzystaj z dziedziczenia z tej klasy zamiast z klasy `AsyncTask` i zastąp przesłonięcia metod `doInBackground` oraz `onPreExecute` odpowiednio przesłonięciami metod `doInBackgroundMAM` i `onPreExecuteMAM`. Konstruktor `MAMAsyncTask` pobiera kontekst działania. Przykład:

```java
  AsyncTask<Object, Object, Object> task = new MAMAsyncTask<Object, Object, Object>(thisActivity) {

    @Override
    protected Object doInBackgroundMAM(final Object[] params) {
        // Do operations.
    }

    @Override
    protected void onPreExecuteMAM() {
        // Do setup.
    };
```

### <a name="mamidentityexecutors"></a>MAMIdentityExecutors
`MAMIdentityExecutors` umożliwia zawinięcie istniejącego wystąpienia `Executor` lub `ExecutorService` w formie zachowującej tożsamość klasy `Executor`/`ExecutorService` z metodami `wrapExecutor` i `wrapExecutorService`. Na przykład

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```

### <a name="file-protection"></a>Ochrona plików

Każdy plik ma tożsamość skojarzoną z nim w momencie utworzenia na podstawie tożsamości procesu i wątku. Ta tożsamość będzie używana zarówno do szyfrowania, jak i selektywnego czyszczenia. Szyfrowane będą tylko pliki, których tożsamość jest zarządzana i ma zasady wymagające szyfrowania. Domyślna funkcja selektywnego czyszczenia danych zestawu SDK będzie czyściła tylko pliki skojarzone z zarządzaną tożsamością, dla której zażądano czyszczenia. Aplikacja może wysyłać zapytania dotyczące tożsamości pliku lub może zmieniać tę tożsamość przy użyciu klasy `MAMFileProtectionManager`.

```java
public final class MAMFileProtectionManager {

   /**
    * Protect a file or directory. This will synchronously trigger whatever protection is required for the file, and will tag the
    * file for future protection changes. If an identity is set on a directory, it is set recursively on all files and
    * subdirectories. New files or directories will inherit their parent directory's identity. If MAM is operating in offline mode,
    * this method will silently do nothing.
    *
    * @param identity
    *        Identity to set.
    * @param file
    *        File to protect.
    *
    * @throws IOException
    *         If the file cannot be protected.
    */
   public static void protect(final File file, final String identity) throws IOException;

   /**
     * Protect a file obtained from a content provider. This is intended to be used for
     * sdcard (whether internal or removable) files accessed through the Storage Access Framework.
     * It may also be used with descriptors referring to private files owned by this app.
     * It is not intended to be used for files owned by other apps and such usage will fail. If
     * creating a new file via a content provider exposed by another MAM-integrated app, the new
     * file identity will automatically be set correctly if the ContentResolver in use was
     * obtained via a Context with an identity or if the thread identity is set.
     *
     * This will synchronously trigger whatever protection is required for the file, and will tag
     * the file for future protection changes. If an identity is set on a directory, it is set
     * recursively on all files and subdirectories. If MAM is operating in offline mode, this
     * method will silently do nothing.
     *
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     *
     * @throws IOException
     *             If the file cannot be protected.
     */
    public static void protect(final ParcelFileDescriptor file, final String identity) throws IOException;

   /**
    * Get the protection info on a file.
    *
    * @param file
    *            File or directory to get information on.
    * @return File protection info, or null if there is no protection info.
    * @throws IOException
    *             If the file cannot be read or opened.
    */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;

   /**
    * Get the protection info on a file.
    *
    * @param file
    *            File or directory to get information on.
    * @return File protection info, or null if there is no protection info.
    * @throws IOException
    *             If the file cannot be read or opened.
    */
    public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

}

public interface MAMFileProtectionInfo {
    String getIdentity();
}
 ```

#### <a name="app-responsibility"></a>Odpowiedzialność aplikacji
Funkcja MAM nie może automatycznie wywnioskować relacji między odczytywanymi plikami i danymi wyświetlanymi w obszarze `Activity`. Aplikacje *muszą* odpowiednio ustawić tożsamość interfejsu użytkownika przed wyświetleniem danych firmowych. Obejmuje to odczyt danych z plików. Jeśli plik pochodzi spoza aplikacji (z obiektu `ContentProvider` lub odczytu z publicznie zapisywalnej lokalizacji), aplikacja *musi* podjąć próbę określenia tożsamości pliku (przy użyciu metody `MAMFileProtectionManager.getProtectionInfo`) przed wyświetleniem informacji odczytanych z pliku. Jeśli metoda `getProtectionInfo` zgłosi niepustą tożsamość o wartości innej niż null, tożsamość interfejsu użytkownika *musi* zostać ustawiona w taki sposób, aby była zgodna z tą tożsamością (przy użyciu metody `MAMActivity.switchMAMIdentity` lub `MAMPolicyManager.setUIPolicyIdentity`). Jeśli przełączenie tożsamości nie powiedzie się, dane z pliku *nie mogą* zostać wyświetlone.

Przykładowy przepływ może wyglądać podobnie do poniższego:
* Użytkownik wybiera dokument do otwarcia w aplikacji.
* Podczas przepływu otwierania, ale przed odczytaniem danych z dysku, aplikacja potwierdza tożsamość, która powinna zostać użyta do wyświetlenia zawartości
  * MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)
  * if(info) MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)
  * Aplikacja oczekuje na zgłoszenie wyniku do wywołania zwrotnego
  * Jeśli zgłoszony wynik oznacza niepowodzenie, aplikacja nie wyświetla dokumentu.
* Aplikacja otwiera i renderuje plik.
  
#### <a name="single-identity-to-multi-identity-transition"></a>Przejście z obsługi jednej tożsamości do obsługi wielu tożsamości
Jeśli aplikacja, która wcześniej została wydana z obsługą integracji jednej tożsamości usługi Intune, później integruje się z wieloma tożsamościami, względem wcześniej zainstalowanych aplikacji zostanie zastosowane przejście (nie jest to widoczne dla użytkownika, ponieważ nie istnieje skojarzone środowisko użytkownika). Dla aplikacji nie jest *wymagane* wykonanie żadnych czynności, aby mogła ona obsłużyć to przejście. Wszystkie pliki utworzone przed przejściem będą nadal traktowane jako zarządzane (dzięki czemu pozostaną zaszyfrowane, jeśli zasady szyfrowania są włączone). Jeśli jest to pożądane, można wykryć uaktualnienie i użyć klasy `MAMFileProtectionManager.protect` w celu otagowania określonych plików lub katalogów przy użyciu pustej tożsamości (spowoduje to usunięcie szyfrowania, jeśli te elementy były zaszyfrowane).

#### <a name="offline-scenarios"></a>Scenariusze w trybie offline

Na znakowanie tożsamości pliku ma wpływ tryb offline. Należy uwzględnić następujące kwestie:

* Jeśli nie zainstalowano aplikacji Portal firmy, nie można tagować tożsamości plików.

* Jeśli aplikacja Portal firmy została zainstalowana, ale aplikacja nie ma zasad zarządzania aplikacjami mobilnymi usługi Intune, tagowanie tożsamości plików nie będzie niezawodne.

* Po udostępnieniu tagowania tożsamości plików wszystkie wcześniej utworzone pliki będą traktowane jako osobiste/niezarządzane (należące do tożsamości o pustym ciągu), chyba że aplikacja została wcześniej zainstalowana jako aplikacja zarządzana z obsługą jednej tożsamości — w takim przypadku będą one traktowane jako należące do zarejestrowanego użytkownika.

### <a name="directory-protection"></a>Ochrona katalogu

Katalogi można chronić przy użyciu tej samej metody `protect`, której używa się do ochrony plików. Ochrona katalogów ma charakter cykliczny i obejmuje wszystkie pliki i podkatalogi w danym katalogu, jak również nowe pliki tworzone w katalogu. Ponieważ ochrona katalogów jest stosowana cyklicznie, wywołanie `protect` może w przypadku dużych katalogów zająć sporo czasu. W związku z tym aplikacje zapewniające ochronę katalogów zawierających dużą liczbę plików mogą uruchamiać operację `protect` asynchronicznie w ramach wątku w tle.

### <a name="data-protection"></a>Ochrona danych

Nie jest możliwe tagowanie pliku jako należącego do wielu tożsamości. Aplikacje, które muszą przechowywać dane należące do różnych użytkowników w tym samym pliku, mogą robić to ręcznie przy użyciu funkcji oferowanych przez klasę `MAMDataProtectionManager`. Umożliwia to aplikacji szyfrowanie danych i powiązanie ich z określonym użytkownikiem. Zaszyfrowane dane można przechowywać na dysku w pliku. Można tworzyć zapytania dotyczące danych skojarzonych z tożsamością. Dane te można później odszyfrować.

Aplikacje korzystające z klasy `MAMDataProtectionManager` powinny zaimplementować odbiornik powiadomień `MANAGEMENT_REMOVED`. Jeśli podczas zapewniania ochrony buforów zostało włączone szyfrowanie plików, po zakończeniu procesu powiadamiania bufory, które były chronione za pomocą tej klasy, nie będą już mogły zostać odczytane. Aplikacja może rozwiązać ten problem przez wywołanie podczas tego procesu powiadamiania metody `MAMDataProtectionManager.unprotect` dla wszystkich buforów. Bezpieczne jest również wywoływanie ochrony podczas tego procesu powiadamiania, jeśli pożądane jest zachowanie informacji o tożsamości — szyfrowanie jest zawsze wyłączone w czasie powiadamiania.


```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```

### <a name="content-providers"></a>Dostawcy zawartości

Jeśli aplikacja dostarcza dane firmowe inne niż `ParcelFileDescriptor` za pośrednictwem elementu `ContentProvider`, musi wywołać metodę `isProvideContentAllowed(String)` w obiekcie `MAMContentProvider`, przekazując nazwę UPN tożsamości właściciela (główną nazwę użytkownika) danej zawartości. Jeśli ta funkcja zwróci wartość false, zawartość *nie może* zostać zwrócona do elementu wywołującego. Deskryptory plików zwrócone za pośrednictwem dostawcy zawartości są obsługiwane automatycznie na podstawie tożsamości plików.

Jeśli nie dziedziczysz metody `MAMContentProvider` jawnie i zamiast tego w celu dokonania zmian zezwalasz na użycie narzędzi kompilacji, możesz wywołać statyczną wersję tej samej metody: `MAMContentProvider.isProvideContentAllowed(provider, contentIdentity)`.

### <a name="selective-wipe"></a>Selektywne czyszczenie

Jeśli aplikacja mająca wiele tożsamości rejestruje się w celu odbierania powiadomienia `WIPE_USER_DATA`, jest odpowiedzialna za usunięcie wszystkich danych czyszczonego użytkownika, w tym wszystkich plików, które zostały oznaczone tożsamością jako należące do tego użytkownika. Jeśli aplikacja usuwa dane użytkownika z pliku, ale chce pozostawić inne dane w pliku, *musi* zmienić tożsamość pliku (za pośrednictwem elementu `MAMFileProtectionManager.protect` na tożsamość osobistego użytkownika lub pustą). Jeśli są używane zasady szyfrowania, wszelkie pozostałe pliki należące do czyszczonego użytkownika nie zostaną odszyfrowane i staną się niedostępne dla aplikacji po wyczyszczeniu.

Jeśli aplikacja została zarejestrowana do odbierania powiadomienia `WIPE_USER_DATA`, nie będzie korzystać z domyślnego selektywnego czyszczenia danych z zestawu SDK. W przypadku aplikacji z obsługą wielu tożsamości taka utrata może być bardziej znacząca, ponieważ domyślne selektywne czyszczenie danych funkcji MAM będzie czyścić tylko pliki o określonej tożsamości. Jeśli aplikacja obsługująca wiele tożsamości ma przeprowadzać domyślne selektywne czyszczenie danych funkcji MAM _**oraz**_ wykonywać własne działania w zakresie czyszczenia, wymagana jest rejestracja pod kątem otrzymywania powiadomień `WIPE_USER_AUXILIARY_DATA`. To powiadomienie zostanie wysyłane przez zestaw SDK bezpośrednio przed wykonaniem domyślnego selektywnego czyszczenia danych funkcji zarządzania aplikacjami mobilnymi. Aplikacja w żadnym wypadku nie może być zarejestrowana do otrzymywania jednocześnie powiadomień `WIPE_USER_DATA` i `WIPE_USER_AUXILIARY_DATA`.

Domyślne selektywne czyszczenie danych spowoduje poprawne zamknięcie aplikacji, zakończenie działań i zabicie procesu aplikacji. Jeśli aplikacja zastępuje domyślne selektywne czyszczenie danych, warto wziąć pod uwagę ręczne zamknięcie aplikacji, aby uniemożliwić użytkownikowi uzyskiwanie dostępu do danych w pamięci w czasie trwania operacji czyszczenia.


## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a>Włączanie docelowej konfiguracji funkcji MAM dla aplikacji systemu Android (opcjonalnie)
Pary klucz-wartość specyficzne dla aplikacji można skonfigurować w konsoli usługi Intune na potrzeby aplikacji [MAM-WE](https://docs.microsoft.com/intune/app-configuration-policies-managed-app) i [aplikacji profilu służbowego systemu Android](https://docs.microsoft.com/intune/app-configuration-policies-use-android).
Te pary klucz-wartość nie są w ogóle interpretowane przez usługę Intune, ale są przekazywane do aplikacji. W tym celu aplikacje, które mają otrzymywać taką konfigurację, mogą użyć klas `MAMAppConfigManager` i `MAMAppConfig`. Jeśli wiele zasad jest przeznaczonych dla tej samej aplikacji, może istnieć wiele powodujących konflikt wartości dostępnych dla tego samego klucza.

> [!NOTE] 
> Ustawienia konfiguracji na potrzeby dostarczania za pomocą mechanizmu MAM-WE nie mogą być dostarczane w trybie `offline`.  W takim przypadku tylko ograniczenia aplikacji systemu Android Enterprise będą dostarczane za pośrednictwem metody `MAMUserNotification` w pustej tożsamości.

### <a name="example"></a>Przykład

```java
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
LOGGER.info("App Config Data = " + appConfig.getFullData());
String valueToUse = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    for (String value : values) {
        if (isCorrectValue(value)) {
            valueToUse = value;
        }
    }
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
LOGGER.info("Found value " + valueToUse);
```

### <a name="notification"></a>Powiadomienie
Konfiguracja aplikacji wprowadza nowy typ powiadomienia:
* **REFRESH_APP_CONFIG**: to powiadomienie jest wysyłane w ramach obiektu `MAMUserNotification` i służy do informowania aplikacji, że nowe dane konfiguracji aplikacji są dostępne.

### <a name="further-reading"></a>Dalsze informacje
Aby uzyskać więcej informacji o możliwościach interfejsu API programu Graph, zobacz [Dokumentacja interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/overview). <br>

Więcej informacji na temat tworzenia zasad docelowej konfiguracji aplikacji funkcji MAM w systemie Android można znaleźć w sekcji poświęconej docelowej konfiguracji aplikacji funkcji MAM znajdującej się w artykule [How to use Microsoft Intune app configuration policies for Android](https://docs.microsoft.com/intune/app-configuration-policies-use-android) (Jak używać zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu Android).

## <a name="style-customization-optional"></a>Dostosowywanie stylów (opcjonalne)

Widoki generowane przez zestaw SDK usługi MAM można dostosować wizualnie, aby dopasować je do aplikacji, z którą jest on zintegrowany. Można dostosować kolory podstawowe i drugorzędne oraz kolory tła, a także rozmiar logo aplikacji. Tego rodzaju dostosowanie stylu jest opcjonalne. Jeśli nie zostanie skonfigurowany styl niestandardowy, zostaną użyte ustawienia domyślne.


### <a name="how-to-customize"></a>Jak dostosować styl
Aby zastosować zmiany stylów do widoków funkcji MAM w usłudze Intune, należy najpierw utworzyć plik XML, który zastąpi istniejące ustawienia stylu. Plik należy umieścić w katalogu „/ res/xml” aplikacji. Można nadać mu dowolną nazwę. Poniżej znajduje się przykład wymaganego formatu pliku.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>
```

Wykorzystaj ponownie zasoby, które istnieją już w aplikacji. Na przykład dodaj odwołanie do koloru zielonego zdefiniowanego w pliku colors.xml. Nie można użyć szesnastkowego kodu koloru „#0000ff”. Maksymalny rozmiar logo aplikacji wynosi 110 dip (dp). Możesz użyć mniejszego obrazu logo, jednak użycie maksymalnego rozmiaru zapewnia najlepsze rezultaty. Jeśli przekroczysz limit rozmiaru 110 dip, obraz zostanie zmniejszony, co może spowodować jego rozmycie.

Poniżej znajduje się pełna lista dozwolonych atrybutów stylu, elementów interfejsu użytkownika, których one dotyczą, a także nazw elementów atrybutów XML i typów oczekiwanych zasobów.

|Atrybut stylu | Elementy interfejsu użytkownika, których dotyczy atrybut | Nazwa elementu atrybutu | Oczekiwany typ zasobu |
| -- | -- | -- | -- |
| Kolor tła | Kolor tła ekranu numeru PIN <Br>Kolor wypełnienia pola numeru PIN | background_color | Kolor |
| Kolor pierwszego planu | Kolor tekstu na pierwszym planie <br> Obramowanie pola numeru PIN w stanie domyślnym <br> Znaki (w tym znaki zaciemnione) w polu numeru PIN podczas wprowadzania przez użytkownika| foreground_color | Kolor|
| Kolor akcentu | Obramowanie wyróżnionego pola numeru PIN <br> Hiperlinki |accent_color | Kolor |
| Logo aplikacji | Duża ikona wyświetlana na ekranie numeru PIN aplikacji usługi Intune | logo_image | Obiekt rysowalny |

## <a name="default-enrollment-optional"></a>Rejestracja domyślna (opcjonalnie)

Poniżej przedstawiono wskazówki dotyczące wymagania monitowania użytkownika podczas uruchamiania aplikacji w celu automatycznej rejestracji w usłudze APP-WE (w tej sekcji nazywanej **rejestracją domyślną**) oraz wymagania zasad ochrony aplikacji usługi Intune, aby umożliwić używanie zintegrowanej z zestawem SDK aplikacji LOB dla systemu Android tylko chronionym użytkownikom usługi Intune. Omówiono również sposób włączenia logowania jednokrotnego w przypadku zintegrowanej z zestawem SDK aplikacji LOB dla systemu Android. Te możliwości **nie** są obsługiwane w przypadku aplikacji ze sklepu, których mogą używać użytkownicy niekorzystający z usługi Intune.

> [!NOTE] 
> Korzyści wynikające z **rejestracji domyślnej** obejmują uproszczone uzyskiwanie zasad z usługi APP-WE dla aplikacji na urządzeniu.

> [!NOTE] 
> **Rejestracja domyślna** wie o suwerennej chmurze.

Włącz rejestrację domyślną, wykonując następujące kroki:

1. Jeśli Twoja aplikacja jest zintegrowana z biblioteką ADAL lub musisz włączyć logowanie jednokrotne, [skonfiguruj bibliotekę ADAL](#configure-azure-active-directory-authentication-library-adal), wykonując punkt 2. opisany w sekcji [Typowe konfiguracje biblioteki ADAL](#common-adal-configurations). W przeciwnym razie możesz pominąć ten krok.
   
2. Włącz rejestrację domyślną przez umieszczenie w manifeście następującej wartości:

   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />
   ```

   > [!NOTE] 
   > Musi to być jedyna integracja z usługą MAM-WE w aplikacji. Wszelkie inne próby wywołania interfejsów API MAMEnrollmentManager spowodują konflikty.

3. Włącz wymagane zasady zarządzania aplikacjami mobilnymi przez umieszczenie w manifeście następującej wartości:

   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />
   ```

   > [!NOTE] 
   > Wymusi to na użytkowniku pobranie aplikacji Portal firmy na urządzenie i ukończenie przepływu rejestracji domyślnej przed użyciem.


## <a name="limitations"></a>Ograniczenia

### <a name="file-size-limitations"></a>Ograniczenia rozmiaru plików

Ograniczenia formatu pliku wykonywalnego dla platformy Dalvik mogą stać się problemem w przypadku uruchamiania dużych baz kodu bez narzędzia [ProGuard](http://proguard.sourceforge.net/). W szczególności mogą wystąpić następujące ograniczenia:

1. Limit 65 000 dla pól.
2. Limit 65 000 dla metod.

### <a name="policy-enforcement-limitations"></a>Ograniczenia wymuszania zasad

* **Używanie elementów rozpoznawania zawartości**: zasady „transferu lub odbierania” usługi Intune mogą zablokować lub częściowo zablokować użycie elementu rozpoznawania zawartości na potrzeby dostępu do dostawcy zawartości w innej aplikacji. Spowoduje to, że metody klasy `ContentResolver` będą zwracać wartość null lub zgłaszać wartość błędu (np. klasa `openOutputStream` będzie zgłaszać wyjątek `FileNotFoundException`, jeśli zostanie zablokowana). Aplikacja może określić, czy błąd zapisu danych przez element rozpoznawania zawartości został spowodowany przez zasady (lub może zostać spowodowany przez zasady) za pomocą wywołania:

    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```

    lub jeśli nie jest istnieje żadne skojarzone działanie

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    W tym drugim przypadku aplikacje z wieloma tożsamościami muszą odpowiednio ustawić tożsamość wątku (lub przekazać jawną tożsamość do wywołania metody `getPolicy`).

### <a name="exported-services"></a>Wyeksportowane usługi

 Plik AndroidManifest.xml dołączony do zestawu SDK aplikacji usługi Intune zawiera element **MAMNotificationReceiverService**. Musi to być wyeksportowana usługa, aby umożliwić aplikacji Portal firmy wysyłanie powiadomień do zarządzanej aplikacji. Usługa sprawdza obiekt wywołujący, aby zapewnić, że tylko aplikacja Portal firmy ma zezwolenie na wysyłanie powiadomień.

### <a name="reflection-limitations"></a>Ograniczenia odbicia
Niektóre z klas bazowych MAM (np. MAMActivity, MAMDocumentsProvider) zawierają metody (oparte na oryginalnych klasach bazowych systemu Android), które używają parametru lub zwracanych typów obecnych tylko powyżej określonych poziomów interfejsu API. Z tego powodu użycie odbicia w celu wyliczenia wszystkich metod składników aplikacji nie zawsze jest możliwe. To ograniczenie nie dotyczy tylko zarządzania aplikacjami mobilnymi. Będzie mieć również zastosowanie, jeśli aplikacja samodzielnie wdroży te metody na podstawie klas bazowych systemu Android.

### <a name="robolectric"></a>Robolectric
Testowanie zachowania zestawu SDK funkcji MAM w chmurze Robolectric nie jest obsługiwane. Istnieją znane problemy dotyczące działania zestawu SDK rozwiązania MAM w chmurze Robelectric spowodowane zachowaniami istniejącymi w chmurze Robelectric, które niedokładnie imitują zachowania w rzeczywistych urządzeniach lub emulatorach.

Jeśli chcesz przetestować swoją aplikację w chmurze Roboelectric, zalecanym obejściem jest przeniesienie logiki klasy aplikacji do pomocnika i utworzenie testów jednostkowych apk z klasą aplikacji, która nie dziedziczy z elementu MAMApplication.
## <a name="expectations-of-the-sdk-consumer"></a>Oczekiwania konsumentów korzystających z zestawu SDK

Zestaw SDK usługi Intune obsługuje kontrakt udostępniony przez interfejs API systemu Android, chociaż w wyniku wymuszania zasad warunki błędu mogą być wyzwalane częściej. Następujące najlepsze rozwiązania dla systemu Android zmniejszają prawdopodobieństwo wystąpienia błędu:

* W przypadku funkcji zestawu SDK systemu Android, które mogą zwrócić wartość null, prawdopodobieństwo zwrócenia wartości null jest teraz większe.  Aby zminimalizować problemy, upewnij się, że sprawdzenia wartości null znajdują się w odpowiednich miejscach.

* Funkcje, które można sprawdzić, muszą zostać sprawdzone za pomocą zastępczych interfejsów API funkcji MAM.

* Wszystkie funkcje pochodne muszą przywoływać swoje superklasy.

* Unikaj stosowania jakiegokolwiek interfejsu API w sposób niejednoznaczny. Na przykład użycie metody `Activity.startActivityForResult` bez sprawdzenia elementu requestCode spowoduje wystąpienie nietypowego zachowania.

## <a name="telemetry"></a>Telemetria

Zestaw SDK aplikacji usługi Intune dla systemu Android nie kontroluje zbierania danych z aplikacji. Aplikacja Portal firmy domyślnie rejestruje dane generowane przez system. Te dane są wysyłane do usługi Microsoft Intune. Zgodnie z zasadami firmy Microsoft nie zbieramy żadnych danych osobowych.

> [!NOTE]
> Jeśli użytkownicy końcowi chcą zrezygnować z wysyłania tych danych, muszą wyłączyć telemetrię w ustawieniach aplikacji portalu firmy. Aby dowiedzieć się więcej, zobacz artykuł [Wyłączanie zbierania danych użycia przez firmę Microsoft](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="recommended-android-best-practices"></a>Zalecane najlepsze rozwiązania dotyczące systemu Android

* Wszystkie projekty biblioteki powinny współużytkować ten sam element android:package tam, gdzie to możliwe. Nie spowoduje to sporadycznego występowania tego problemu podczas uruchamiania aplikacji, ponieważ występuje on tylko podczas kompilacji. Nowsze wersje zestawu SDK aplikacji usługi Intune częściowo usuwają nadmiarowość.

* Korzystaj z najnowszych narzędzi do kompilacji dostępnych w zestawie SDK dla systemu Android.

* Usuń wszystkie nieużywane i niepotrzebne biblioteki (np. android.support.v4).
