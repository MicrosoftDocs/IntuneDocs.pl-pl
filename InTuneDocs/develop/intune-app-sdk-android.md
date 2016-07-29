---
title: "Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51f7734e2acced469ec3520d74a8079dac8223f2
ms.openlocfilehash: bcb62e9c99c1f5a5b53ada688ef39a59674dea04


---

# Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android

> [!NOTE]
> Warto najpierw przeczytać artykuł [Omówienie zestawu SDK aplikacji usługi Intune](intune-app-sdk.md), w którym opisano bieżące funkcje zestawu SDK oraz sposób przygotowania do integracji na każdej z obsługiwanych platform. 

# Zawartość zestawu SDK 

Zestaw SDK aplikacji usługi Intune dla systemu Android to standardowa biblioteka systemu Android bez zewnętrznych zależności. Zestaw SDK składa się z następujących plików:  

* **`Microsoft.Intune MAM.SDK.jar`**: interfejsy niezbędne do obsługi funkcji MAM w aplikacji (należy też włączyć współdziałanie z aplikacją Portal firmy usługi Microsoft Intune). Aplikacje muszą określić go jako odwołanie do biblioteki systemu Android.

*  **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: interfejsy niezbędne do włączenia funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 4.  Aplikacje potrzebujące tej obsługi muszą przywoływać plik jar bezpośrednio. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: interfejsy niezbędne do włączenia funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 7.   Aplikacje potrzebujące tej obsługi muszą przywoływać plik jar bezpośrednio.

* **Katalog zasobów**: zasoby (na przykład ciągi), z których korzysta zestaw SDK. 

* **`Microsoft.Intune.MAM.SDK.aar`**: składniki zestawu SDK z wyjątkiem plików jar Support.V4 i Support.V7. Tego pliku można użyć zamiast pojedynczych składników, jeśli system kompilacji obsługuje pliki AAR.

* **`AndroidManifest.xml`**: dodatkowe punkty wejścia i wymagania dotyczące bibliotek. 

* **`THIRDPARTYNOTICES.TXT`**: informacje o uznaniu autorstwa dla kodu innych firm lub typu „open source”, który zostanie skompilowany w ramach aplikacji. 

# Wymagania 

Zestaw SDK aplikacji usługi Intune to skompilowany projekt systemu Android. Dlatego jest w dużym stopniu niezależny od wersji interfejsu API systemu Android określonych przez aplikację jako minimalna i docelowa. Zestaw SDK obsługuje interfejsy API systemu Android w wersjach od 14 (system Android 4.0 i nowsze) do 24. 

# Jak działa zestaw SDK aplikacji usługi Intune 

Zestaw SDK aplikacji usługi Intune wymaga wprowadzenia zmian w kodzie źródłowym aplikacji w celu włączenia zasad zarządzania aplikacjami. Te zmiany wprowadza się przez zastąpienie klas podstawowych sytemu Android równoważnymi klasami zarządzanymi, które w tym dokumencie są przywoływane z prefiksem `MAM`. Klasy zestawu SDK są ulokowanie między klasami podstawowymi systemu Android a pochodnymi wersjami klas należącymi do aplikacji.  Na przykład w przypadku działania końcowa hierarchia dziedziczenia wygląda następująco: `Activity ->MAMActivity->AppSpecificActivity`.

Gdy element `AppSpecificActivity` wykonuje działanie obejmujące jego element nadrzędny, np. `super.onCreate())`, to klasa `MAMActivity` jest superklasą, mimo że znajduje się w hierarchii dziedziczenia i zastępuje kilka metod. Aplikacje dla systemu Android mają tryb pojedynczy i dostęp do całego systemu za pośrednictwem ich obiektu Context.  Z drugiej strony aplikacje z wbudowanym zestawem SDK aplikacji usługi Intune mają dwa tryby — jako aplikacje mogą nadal uzyskiwać dostęp do systemu za pośrednictwem obiektu Context, lecz w zależności od użytego podstawowego elementu Activity obiekt Context będzie udostępniany przez system Android lub w sposób inteligentny będzie multipleksował ograniczony widok systemu i obiekt Context udostępniony przez system Android.

Zestaw SDK aplikacji usługi Intune dla systemu Android zależy od obecności aplikacji Portal firmy na urządzeniu na potrzeby obsługi zasad funkcji MAM. Jeśli nie ma aplikacji Portal firmy, zachowanie aplikacji z włączoną funkcją MAM nie zostanie zmienione i będzie ona działać tak jak każda inna aplikacja mobilna. Jeśli aplikacja Portal firmy jest zainstalowana i zawiera zasady dla użytkownika, punkty wejścia zestawu SDK są inicjowane asynchronicznie. Inicjowanie jest wymagane tylko wtedy, gdy proces został początkowo utworzony przez system Android. Podczas inicjowania jest nawiązywane połączenie z aplikacją Portal firmy, a następnie są pobierane zasady ograniczeń.  

# Integrowanie z zestawem SDK aplikacji usługi Intune
 
Jak przedstawiono wcześniej, zestaw SDK wymaga zmian kodu źródłowego aplikacji w celu włączenia zasad zarządzania aplikacjami. Oto kroki konieczne do włączenia funkcji MAM w aplikacji: 

## Zastąpienie klas, metod i działań ich równoważnikami funkcji MAM (wymagane) 

* Klasy podstawowe systemu Android muszą zostać zastąpione ich klasami równoważnymi funkcji MAM. W tym celu znajdź wszystkie wystąpienia klas wymienionych w poniższej tabeli i zastąp je równoważnikami z zestawu SDK aplikacji usługi Intune.  

    | Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
    |--|--|
    | android.app.Activity | MAMActivity |
    | android.app.ActivityGroup | MAMActivityGroup |
    | android.app.AliasActivity | MAMAliasActivity |
    | android.app.Application | MAMApplication |
    | android.app.DialogFragment | MAMDialogFragment |
    | android.app.ExpandableListActivity | MAMExpandableListActivity |
    | android.app.Fragment | MAMFragment |
    | android.app.IntentService | MAMIntentService |
    | android.app.LauncherActivity | MAMLauncherActivity |
    | android.app.ListActivity | MAMListActivity |
    | android.app.NativeActivity | MAMNativeActivity |
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *Zastąpienie klasy Binder klasą MAMBinder jest wymagane tylko wtedy, gdy klasa Binder nie jest generowana z interfejsu AIDL.

    **Microsoft.Intune.MAM.SDK.Supplubt.v4.jar**:

    | Funkcja MAM usługi Intune dla klasy systemu Android | Klasa zastępcza z zestawu SDK |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Supplubt.v7.jar**:

    |Klasa systemu Android | Klasa zastępcza z zestawu SDK funkcji MAM usługi Intune |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* Korzystając z punktu wejścia systemu Android przesłoniętego przez równoważnik funkcji MAM, musisz użyć alternatywnej wersji cyklu życia punktu wejścia (z wyjątkiem klasy `MAMApplication`).

    Na przykład przy tworzeniu klasy pochodnej klasy `MAMActivity`zamiast przesłaniać metodę `onCreate` i wywoływać metodę `super.onCreate`, działanie musi przesłonić metodę `onMAMCreate` i wywołać metodę`uper.onMAMCreate`. Dzięki temu w niektórych przypadkach można ograniczyć uruchomienie działania (między innymi). 

# Włączanie funkcji wymagających udziału aplikacji 

Zestaw SDK nie może sam zaimplementować niektórych zasad. Aby umożliwić aplikacji kontrolowanie swojego zachowania w ramach tych funkcji, uwidaczniamy kilka interfejsów API, które znajdują się w interfejsie `AppPolicy` przedstawionym poniżej.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

## Jak umożliwić administratorowi IT kontrolowanie działania funkcji zapisywania w aplikacji

Wiele aplikacji implementuje funkcje, które umożliwiają użytkownikom końcowym zapisywanie plików lokalnie lub w innej usłudze. Zestaw SDK aplikacji usługi Intune pozwala administratorom IT chronić dane przed wyciekiem przez zastosowanie ograniczeń zasad w organizacji w dowolny sposób.  Jedne z zasad, które administrator może kontrolować, dotyczą tego, czy użytkownik końcowy może zapisywać w osobistym magazynie danych. Obejmuje to zapisywanie w lokalizacji lokalnej, na karcie SD i w usługach kopii zapasowej. Do włączenia tej funkcji wymagane jest współdziałanie ze strony aplikacji. Jeśli Twoja aplikacja umożliwia zapisywanie w lokalizacji osobistej lub w chmurze bezpośrednio z aplikacji, musisz zaimplementować tę funkcję, aby umożliwić administratorowi IT kontrolowanie, czy zapisywanie w lokalizacji jest dozwolone. Interfejs API przedstawiony poniżej umożliwia aplikacji określenie, czy zapisywanie w magazynie osobistym jest dozwolone przez bieżące zasady administratora. Aplikacja może wtedy wymusić zasady, ponieważ ma informacje o osobistym magazynie danych dostępnym dla użytkownika końcowego przez aplikację.  

Aby określić, czy zasady są wymuszane, aplikacja może wykonać następujące wywołanie: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Uwaga**: Wywołanie MAMComponents.get(AppPolicy.class) zawsze zwraca zasady aplikacji o wartości innej niż null, nawet jeśli urządzenie lub aplikacja nie jest zarządzana. 

## Zezwolenie aplikacji na wykrywanie, czy zasady numeru PIN są wymagane
 
 Istnieją dodatkowe zasady aplikacji, które umożliwiają aplikacji wyłączenie niektórych jej funkcji, aby nie duplikowały funkcji zestawu SDK aplikacji usługi Intune. Na przykład jeśli aplikacja ma własny interfejs użytkownika do obsługi numeru PIN, możesz go wyłączyć, gdy zestaw SDK jest skonfigurowany do żądania wprowadzenia numeru PIN przez użytkownika końcowego. 

Aby określić, czy zasady numeru PIN są skonfigurowane w taki sposób, że jest wymagane okresowe wprowadzanie numeru PIN, aplikacja może wykonać następujące wywołanie: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

## Rejestrowanie na potrzeby powiadomień z zestawu SDK  

Zestaw SDK aplikacji usługi Intune pozwala aplikacji na kontrolę zachowania, gdy niektóre zasady, takie jak zasady zdalnego wymazywania, zostaną użyte przez administratora IT. W tym celu musisz zarejestrować odbieranie powiadomień z zestawu SDK, tworząc klasę `MAMNotificationReceiver` i rejestrując ją za pomocą metody `MAMNotificationReceiverRegistry`. Należy to zrobić, podając odbiorcę i typ powiadomień, które odbiorca chce otrzymywać, w metodzie  `App.onCreate`, tak jak pokazano w przykładzie poniżej:
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` po prostu odbiera powiadomienia. Niektóre powiadomienia są bezpośrednio obsługiwane przez zestaw SDK, a inne wymagają współdziałania ze strony aplikacji. Aplikacja musi zwrócić wartość true lub false dla powiadomienia. Musi ona zawsze zwrócić wartość true, chyba że niektóre akcje, które próbowała wykonać w wyniku powiadomienia, nie powiodły się. Ten błąd może zostać zgłoszony do usługi Intune, na przykład jeśli aplikacja wskazuje, że czyszczenie danych użytkownika nie powiodło się. Blokowanie w metodzie `MAMNotificationReceiver.onReceive`jest bezpieczne. Jej wywołanie zwrotne nie jest uruchamiane w wątku interfejsu użytkownika. 

Interfejs MAMNotificationReceiver jest przedstawiony poniżej (w takiej postaci jest zdefiniowany w zestawie SDK): 

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

Następujące powiadomienia są wysyłane do aplikacji i niektóre z nich mogą wymagać współdziałania ze strony aplikacji: 

* **Powiadomienie `WIPE_USER_DATA`**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po odebraniu tego powiadomienia aplikacja powinna usunąć wszystkie dane skojarzone z tożsamością przekazaną za pomocą klasy `MAMUserNotification`. To powiadomienie jest aktualnie wysyłane podczas wyrejestrowywania z usługi Intune. Nazwa podstawowa użytkownika jest zazwyczaj określana podczas procesu rejestracji. Jeśli zarejestrujesz odbieranie tego powiadomienia, Twoja aplikacja musi zapewnić, że wszystkie dane użytkownika zostaną usunięte. Jeżeli nie zarejestrujesz jego odbierania, zostanie wykonane domyślne działanie czyszczenia selektywnego. 

* **Powiadomienie `WIPE_USER_AUXILIARY_DATA`**: aplikacje mogą zarejestrować odbieranie tego powiadomienia, jeśli zestaw SDK aplikacji usługi Intune ma wykonywać domyślne czyszczenie, ale aplikacja ma usuwać niektóre dane pomocnicze w ramach czyszczenia.  

* **Powiadomienie `REFRESH_POLICY`**: to powiadomienie jest wysyłane w klasie MAMNotification bez żadnych dodatkowych informacji. Po otrzymaniu tego powiadomienia wszystkie buforowane zasady muszą być traktowane jako nieważne i powinny zostać sprawdzone. To działanie jest ogólnie obsługiwane przez zestaw SDK, jednak powinno zostać obsłużone przez aplikację, jeśli zasady są używane w jakikolwiek trwały sposób. 

## Oczekujące intencje i metody 

Po utworzeniu elementu pochodnego dla jednego z punktów wejścia funkcji MAM możesz użyć obiektu Context w normalny sposób do uruchamiania działań za pomocą jego elementu `PackageManager`itp.  Elementy  `PendingIntents` są wyjątkiem od tej reguły. W przypadku wywoływania takich klas musisz zmienić nazwę klasy. Na przykład zamiast klasy `PendingIntent.get*` należy użyć klasy `MAMPendingIntents.get*`. 

W niektórych przypadkach metoda dostępna w klasie systemu Android została oznaczona jako final w zastępczej klasie funkcji MAM. W takim przypadku klasa zastępcza funkcji MAM udostępnia metodę o podobnej nazwie (zazwyczaj z sufiksem „MAM”), która powinna zostać przesłonięta zamiast tego. Na przykład zamiast przesłaniać metodę `ContentProvider.query`należy przesłonić metodę `MAMContentProvider.queryMAM`. Kompilator języka Java powinien wymuszać ograniczenia specyfikacji final, aby zapobiec przypadkowemu przesłonięciu oryginalnej metody zamiast jej równoważnika funkcji MAM. 

# Ochrona danych kopii zapasowej 

Począwszy od systemu Android Marshmallow (interfejs API w wersji 23), na potrzeby aplikacji są dostępne dwa sposoby tworzenia kopii zapasowych danych. Te opcje są dostępne do użycia w aplikacji i wymagają wykonania różnych kroków w celu zapewnienia, że ochrona danych funkcji MAM jest odpowiednio stosowana. Możesz przejrzeć tabelę poniżej, aby szybko zapoznać się z odpowiadającymi akcjami wymaganymi do osiągnięcia poprawnego zachowania w zakresie ochrony danych.  Więcej informacji na temat funkcji kopii zapasowej w systemie Android możesz także znaleźć w [przewodniku Kopia zapasowa danych dla deweloperów systemu Android](http://developer.android.com/guide/topics/data/backup.html). 

## Automatyczne wykonywanie pełnej kopii zapasowej

Od systemu Android M jest dostępna dla aplikacji funkcja pełnego, automatycznego tworzenia kopii zapasowej niezależnie od docelowego interfejsu API w przypadku uruchamiania na urządzeniu z systemem Android M. Tak długo, jak atrybut `android:allowBackup` ma wartość inną niż false, aplikacja będzie otrzymywać pełne, niefiltrowane kopie zapasowe aplikacji. W ten sposób powstaje zagrożenie wyciekiem danych, dlatego zestaw SDK wymaga wprowadzenia zmian przedstawionych w poniższej tabeli w celu zapewnienia ochrony danych.  Ważne jest, aby trzymać się wskazówek podanych poniżej w celu zapewnienia prawidłowej ochrony danych klienta.  Jeśli podasz ustawienie `android:allowBackup=false` , to aplikacja nigdy nie zostanie umieszczona w kolejce kopii zapasowych przez system operacyjny, a w funkcji MAM nie będą dostępne żadne dalsze akcje, ponieważ nie będzie żadnej kopii zapasowej.
 
 ## Kopie zapasowe typu „klucz/wartość”

Ta opcja jest dostępna dla wszystkich interfejsów API i używa klas `BackupAgent` oraz `BackupAgentHelper`. 

### Użycie klasy BackupAgentHelper

`BackupAgentHelper` jest znacznie prostsza do zaimplementowania niż klasa `BackupAgent`, zarówno w zakresie natywnych funkcji systemu Android, jak i integracji z funkcją MAM. `BackupAgentHelper` umożliwia deweloperowi zarejestrowanie całych plików i udostępnionych preferencji odpowiednio w klasie `FileBackupHelper` lub `SharedPreferencesBackupHelper`, która jest następnie dodawana do klasy `BackupAgentHelper` podczas tworzenia. 

### Użycie klasy BackupAgent

`BackupAgent` umożliwia o wiele dokładniejsze określenie danych, których kopie zapasowe mają być tworzone. Jednak te opcje oznaczają, że nie będzie możliwe korzystanie z platformy kopii zapasowych systemu Android.  Ponieważ odpowiedzialność za implementację leży po Twojej stronie, zapewnienie odpowiedniej ochrony danych przez funkcję MAM wymaga większej liczby kroków. Ponieważ większość pracy spoczywa na Tobie, deweloperze, integracja funkcji MAM wymaga nieco więcej wysiłku. 

#### Aplikacja nie ma agenta kopii zapasowej
  
Opcje dewelopera w przypadku ustawienia `Android:allowbBackup =true`:

##### Pełna kopia zapasowa zgodnie z plikiem konfiguracji: 

Podaj zasób w tagu metadanych `com.microsoft.intune.mam.FullBackupContent` w manifeście. Na przykład:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Dodaj następujący atrybut w tagu `<application>` : `android:fullBackupContent="@xml/my_scheme"`, gdzie `my_scheme` jest zasobem XML w aplikacji. 

##### Duplikacja pełnej kopii zapasowej bez wykluczeń 

Podaj tag w manifeście, taki jak `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Dodaj następujący atrybut w tagu `<application>`: `android:fullBackupContent="true"`.

#### Aplikacja ma agenta kopii zapasowej

Postępuj zgodnie z zaleceniami w sekcjach dotyczących klas `BackupAgent` oraz `BackupAgentHelper` powyżej. 

Rozważ przejście na klasę `MAMDefaultFullBackupAgent`, która umożliwia łatwą obsługę kopii zapasowych w systemie Android M. 

### Przed wykonaniem kopii zapasowej

Przed rozpoczęciem tworzenia kopii zapasowej musisz sprawdzić, czy jest to dozwolone dla plików lub buforów danych, których kopia zapasowa ma zostać utworzona. Udostępniliśmy funkcję `isBackupAllowed` w klasach `MAMFileProtectionManager` oraz `MAMDataProtectionManager` , która to umożliwia. Jeśli stworzenie kopii zapasowej pliku lub buforu danych nie jest dozwolone, nie należy próbować uwzględniać go w kopii zapasowej.

Jeśli w pewnym momencie podczas tworzenia kopii zapasowej chcesz utworzyć kopię zapasową tożsamości dla plików sprawdzonych w kroku 1, musisz użyć wywołania `backupMAMFileIdentity(BackupDataOutput data, File … files)`, podając pliki, z których dane mają zostać wyodrębnione. Spowoduje to automatyczne utworzenie nowych jednostek kopii zapasowej i zapisanie ich do elementu `BackupDataOutput` . Te jednostki zostaną automatycznie użyte podczas przywracania. 

## Konfigurowanie biblioteki uwierzytelniania usługi Azure Directory (ADAL)  

Zestaw SDK zależy od usługi ADAL w zakresie uwierzytelniania i warunkowego uruchamiania, co wymaga umieszczenia w aplikacji pewnej części konfiguracji usługi Azure Active Directory. Wartości konfiguracji są przekazywane do zestawu SDK przez metadane w pliku `AndroidManifest` . Aby skonfigurować aplikację i włączyć odpowiednie uwierzytelnianie, dodaj następujący element do węzła aplikacji w pliku `AndroidManifest`. Niektóre z tych konfiguracji są wymagane tylko wtedy, gdy aplikacja ogólnie używa biblioteki ADAL do uwierzytelniania. W takim przypadku potrzebujesz konkretnych wartości, których aplikacja użyła do zarejestrowania się w usłudze AAD. Ma to na celu zapewnienie, że użytkownik końcowy nie będzie monitowany dwukrotnie w ramach uwierzytelnienia z powodu rozpoznania przez usługę AAD dwóch odrębnych wartości rejestracji: jednej z aplikacji i jednej z zestawu SDK. 

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

Identyfikatory GUID nie mogą mieć nawiasu klamrowego na początku ani na końcu.

### Typowe konfiguracje biblioteki ADAL 

Poniżej przedstawiono typowe konfiguracje dla wartości przedstawionych powyżej. 

#### Aplikacja nie jest zintegrowana z biblioteką ADAL

* Urząd musi być ustawiony na wymagane środowisko, w którym skonfigurowano konta usługi AAD.

* Element SkipBroker musi być ustawiony na wartość true.

#### Aplikacja jest zintegrowana z biblioteką ADAL

* Urząd musi być ustawiony na wymagane środowisko, w którym skonfigurowano konta usługi AAD.

* Identyfikator klienta musi być ustawiony na identyfikator klienta aplikacji.

* `NonBrokerRedirectURI` powinien być ustawiony na prawidłowy identyfikator URI przekierowania dla aplikacji.
    * Or `urn:ietf:wg:oauth:2.0:oob` musi być skonfigurowany jako prawidłowy identyfikator URI przekierowania usługi AAD.

* Element SkipBroker musi być ustawiony na wartość false (lub nieobecny).

* Usługa AAD musi być skonfigurowana pod kątem akceptowania identyfikatora URI przekierowania brokera.

#### Aplikacja jest zintegrowana z biblioteką ADAL, lecz nie obsługuje aplikacji uwierzytelniania usługi AAD

* Urząd musi być ustawiony na wymagane środowisko, w którym skonfigurowano konta usługi AAD.

* Identyfikator klienta musi być ustawiony na identyfikator klienta aplikacji.

* `NonBrokerRedirectURI` musi być ustawiony na prawidłowy identyfikator URI przekierowania dla aplikacji.

    * Or `urn:ietf:wg:oauth:2.0:oob` powinien być skonfigurowany jako prawidłowy identyfikator URI przekierowania usługi AAD.

## Jak włączyć rejestrowanie w zestawie SDK 

Rejestrowanie odbywa się za pośrednictwem platformy `java.util.logging` . Aby odbierać dzienniki, skonfiguruj globalne rejestrowanie zgodnie z opisem w [podręczniku technicznym języka Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). W zależności od aplikacji metoda `App.onCreate` jest zwykle najlepszym miejscem, aby zainicjować rejestrowanie. Zwróć uwagę na to, że komunikaty w dzienniku mają klucze w postaci nazwy klasy, która może być zaciemniona.

# Znane ograniczenia dotyczące platformy 

## Ograniczenia rozmiaru plików 

W systemie Android ograniczenia formatu pliku wykonywalnego dla platformy Dalvik mogą stać się problemem w przypadku uruchamiania dużych baz kodu bez narzędzia ProGuard. W szczególności mogą wystąpić następujące ograniczenia: 

* Limit 65 000 dla pól.

* Limit 65 000 dla metod.

W przypadku dołączania wielu projektów każdy element android:package otrzyma kopię elementu R, co znacznie zwiększy liczbę pól w miarę dodawania bibliotek. Poniższe zalecenia mogą ułatwić złagodzenie tego ograniczenia:
 
* Wszystkie projekty biblioteki powinny współużytkować ten sam element android:package tam, gdzie to możliwe. Nie spowoduje to, że użytkownicy będą czasem napotykać ten problem, ponieważ występuje on tylko podczas kompilacji.   Ponadto nowsze wersje zestawu SDK systemu Android przetwarzają wstępnie pliki DEX w celu usunięcia części nadmiarowości. Zmniejsza to jeszcze bardziej odległość od pól.

* Użyj najnowszych dostępnych narzędzi do kompilacji z zestawu SDK systemu Android.

* Usuń wszystkie nieużywane i niepotrzebne biblioteki (np. `android.support.v4`).

## Ograniczenia wymuszania zasad

**Przechwytywanie ekranu**: zestaw SDK nie może wymusić nowej wartości ustawienia przechwytywania ekranu w przypadku działań przetworzonych już przez metodę Activity.onCreate. Może to spowodować, że wystąpi okres, w którym dla aplikacji będzie wyłączone tworzenie zrzutów ekranu, ale wciąż będzie to możliwe.

**Używanie elementów rozpoznawania zawartości*: zasady transferu lub odbierania mogą zablokować lub częściowo zablokować użycie elementu rozpoznawania zawartości na potrzeby dostępu do dostawcy zawartości w innej aplikacji. To spowoduje, że metody klasy ContentResolver będą zwracać wartość null lub zgłaszać wartość błędu (np. klasa `openOutputStream` będzie zgłaszać wyjątek `FileNotFoundException` , jeśli jest zablokowana). Aplikacja może określić, czy błąd zapisu danych przez element rozpoznawania zawartości został spowodowany przez zasady (lub może zostać spowodowany przez zasady) za pomocą wywołania:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Wyeksportowane usługi**: plik `AndroidManifest.xml` dołączony do zestawu SDK aplikacji usługi Intune zawiera klasę `MAMNotificationReceiverService`, która musi być wyeksportowaną usługą, aby umożliwić aplikacji Portal firmy wysyłanie powiadomień do usprawnionych aplikacji. Usługa sprawdza obiekt wywołujący, aby zapewnić, że tylko aplikacja Portal firmy ma zezwolenie na wysyłanie powiadomień. 

# Zalecane najlepsze rozwiązania dla systemu Android 

Zestaw SDK usługi Intune obsługuje kontrakt udostępniony przez interfejs API systemu Android, chociaż w wyniku wymuszania zasad warunki błędu mogą być wyzwalane częściej. Następujące najlepsze rozwiązania dla systemu Android zmniejszają prawdopodobieństwo wystąpienia błędu: 

* W przypadku funkcji zestawu SDK systemu Android, które mogą zwrócić wartość null, prawdopodobieństwo zwrócenia wartości null jest teraz większe.  Aby zminimalizować problemy, upewnij się, że sprawdzenia wartości null znajdują się w odpowiednich miejscach.

* Funkcje, które można sprawdzić, muszą zostać sprawdzone za pomocą ich interfejsów API zestawu SDK.

* Wszystkie funkcje pochodne muszą przywoływać swoje superklasy.

* Unikaj stosowania jakiegokolwiek interfejsu API w sposób niejednoznaczny. Na przykład nie używaj metod `Activity.startActivityForResult/onActivityResult` bez sprawdzenia, czy metoda requestCode spowoduje wystąpienie nietypowego zachowania.



<!--HONumber=Jul16_HO3-->


