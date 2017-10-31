---
title: "Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android"
description: "Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu Android można wdrożyć funkcje zarządzania aplikacjami mobilnymi (MAM, Mobile App Management) usługi Intune w swojej aplikacji systemu Android."
keywords: Zestaw SDK
author: mattbriggs
manager: angrobe
ms.author: mabriggs
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 27725d28ac621bae9500d0e6639a82d6f033e4dc
ms.sourcegitcommit: 42a0e4c83e33c1a25506ca75d673e861e9206945
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2017
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android

> [!NOTE]
> Warto najpierw przeczytać artykuł [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md), w którym opisano aktualne funkcje zestawu SDK oraz sposób przygotowania się do integracji na każdej z obsługiwanych platform.

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu Android możesz wdrożyć zasady ochrony aplikacji usługi Intune (nazywane również zasadami **APP** lub MAM) w swojej natywnej aplikacji dla systemu Android. Aplikacja obsługująca usługę Intune to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy usługi Intune mogą z łatwością wdrażać zasady ochrony aplikacji w aplikacji obsługującej usługę Intune, gdy usługa Intune aktywnie zarządza aplikacją.


## <a name="whats-in-the-sdk"></a>Zawartość zestawu SDK

Zestaw SDK aplikacji usługi Intune obejmuje następujące pliki:  

* **Microsoft.Intune.MAM.SDK.aar**: składniki zestawu SDK z wyjątkiem plików JAR Support.V4 i Support.V7. Tego pliku można użyć zamiast pojedynczych składników, jeśli system kompilacji obsługuje pliki AAR.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: interfejsy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 4. Aplikacje wymagające tej obsługi muszą odwoływać się bezpośrednio do pliku JAR.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: interfejsy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 7. Aplikacje wymagające tej obsługi muszą odwoływać się bezpośrednio do pliku JAR.
* **proguard.txt**: zawiera reguły ProGuard, które należy stosować w przypadku użycia narzędzia ProGuard.
* **CHANGELOG.txt**: zawiera rejestr zmian wprowadzonych w każdej z wersji zestawu SDK.
* **THIRDPARTYNOTICES.TXT**: informacje o uznaniu autorstwa dotyczące kodu innych firm lub typu „open source”, który zostanie skompilowany w ramach aplikacji.

Jeśli system kompilacji nie obsługuje plików AAR, zamiast pliku Microsoft.Intune.MAM.SDK.aar można użyć następujących plików.
* **Microsoft.Intune.MAM.SDK.jar**: interfejsy niezbędne do obsługi funkcji MAM i współdziałania z aplikacją Portal firmy usługi Intune. Aplikacje muszą określić go jako odwołanie do biblioteki systemu Android.
* **Katalog zasobów**: zasoby (na przykład ciągi), z których korzysta zestaw SDK.
* **AndroidManifest.xml**: dodatkowe punkty wejścia i wymagania dotyczące bibliotek.


## <a name="requirements"></a>Wymagania

Zestaw SDK aplikacji usługi Intune to skompilowany projekt systemu Android. Dlatego jest w dużym stopniu niezależny od wersji interfejsu API systemu Android określonych przez aplikację jako minimalna i docelowa. Zestaw SDK obsługuje interfejsy API systemu Android w wersjach od 19 (Android 4.4 i nowsze) do 25 (Android 7.1).



### <a name="company-portal-app"></a>Aplikacji Portal firmy
Zestaw SDK aplikacji usługi Intune dla systemu Android wymaga obecności na urządzeniu aplikacji [Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) umożliwiającej włączenie zasad ochrony aplikacji. Aplikacja Portal firmy pobiera zasady ochrony aplikacji z usługi Intune. Po uruchomieniu aplikacji zostają załadowane zasady i kod umożliwiający wymuszenie danej zasady z aplikacji Portal firmy.

> [!NOTE]
> Jeśli na urządzeniu nie ma aplikacji Portal firmy, aplikacja obsługująca usługę Intune działa tak samo jak zwykła aplikacja, która nie obsługuje zasad ochrony aplikacji usługi Intune.

W przypadku ochrony aplikacji bez rejestracji urządzeń _**nie**_ jest wymagane, aby użytkownik rejestrował urządzenie za pomocą aplikacji Portal firmy.

## <a name="sdk-integration"></a>Integracja zestawów SDK

### <a name="build-integration"></a>Integracja kompilacji

Zestaw SDK aplikacji usługi Intune to standardowa biblioteka systemu Android bez zewnętrznych zależności. Plik **Microsoft.Intune.MAM.SDK.jar** zawiera zarówno interfejsy niezbędne do włączenia zasad ochrony aplikacji, jak i kod wymagany do celów współpracy z aplikacją Portal firmy usługi Microsoft Intune.

Plik **Microsoft.Intune.MAM.SDK.jar** musi zostać wskazany jako odwołanie do biblioteki systemu Android. W tym celu otwórz swój projekt aplikacji w programie Android Studio, przejdź do menu **File > New > New module** (Plik > Nowy > Nowy moduł) i wybierz pozycję **Import .JAR/.AAR Package** (Importuj pakiet JAR/AAR). Wybierz pakiet archiwum systemu Android Microsoft.Intune.MAM.SDK.aar.

Ponadto pakiety **Microsoft.Intune.MAM.SDK.Support.v4** i **Microsoft.Intune.MAM.SDK.Support.v7** zawierają odpowiednio warianty plików `android.support.v4` i `android.support.v7` usługi Intune. Nie są one wbudowane w plik Microsoft.Intune.MAM.SDK.aar na wypadek, gdyby aplikacja nie miała uwzględniać bibliotek pomocy technicznej. To standardowe pliki JAR używane zamiast projektów biblioteki systemu Android.

#### <a name="proguard"></a>ProGuard

Jeśli narzędzie [ProGuard](http://proguard.sourceforge.net/) (lub jakikolwiek inny mechanizm zmniejszający/zaciemniający) stanowi krok kompilacji, należy wykluczyć klasy zestawu SDK usługi Intune. W przypadku narzędzia ProGuard można to zrobić, włączając reguły z pliku proguard.txt dostarczone z zestawem SDK.

Biblioteki uwierzytelniania usługi Azure Active Directory (ADAL, Active Directory Authentication Library) mogą mieć własne ograniczenia dotyczące narzędzia ProGuard. Jeśli aplikacja jest zintegrowana z biblioteką ADAL, postępowanie względem tych ograniczeń powinno być zgodne z dokumentacją ADAL.

### <a name="entry-points"></a>Punkty wejścia

Te uprawnienia są wymagane przez bibliotekę Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) w celu wykonania uwierzytelniania obsługiwanego przez brokera. Jeśli te uprawnienia nie zostaną przyznane dla aplikacji lub zostaną odwołane przez użytkownika, przepływy uwierzytelniania, które wymagają brokera (aplikacja Portal firmy), zostaną wyłączone.

Zestaw SDK aplikacji usługi Intune wymaga wprowadzenia zmian w kodzie źródłowym aplikacji w celu włączenia zasad ochrony aplikacji usługi Intune. Te zmiany wprowadza się przez zastąpienie klas podstawowych systemu Android równoważnymi klasami podstawowymi usługi Intune, których nazwy zawierają prefiks **MAM**. Klasy zestawu SDK są ulokowanie między klasami podstawowymi systemu Android a pochodnymi wersjami klas należącymi do aplikacji. Przykładowo w przypadku działania końcowa hierarchia dziedziczenia wygląda następująco: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Na przykład, jeśli element `AppSpecificActivity` wchodzi w interakcję ze swoim elementem nadrzędnym (na przykład przez wywołanie `super.onCreate()`), to klasa `MAMActivity` stanowi superklasę.

Na ogół aplikacje dla systemu Android mają tryb pojedynczy i mogą uzyskać dostęp do systemu za pośrednictwem ich obiektu [**Context**](https://developer.android.com/reference/android/content/Context.html). Z drugiej strony aplikacje ze zintegrowanym zestawem SDK aplikacji usługi Intune mają dwa tryby. Te aplikacje nadal uzyskują dostęp do systemu za pośrednictwem obiektu `Context`. W zależności od używanego podstawowego elementu `Activity` obiekt `Context` zostanie udostępniony przez system Android lub w sposób inteligentny będzie multipleksować ograniczony widok systemu i obiekt `Context` dostarczony przez system Android. Po utworzeniu klasy pochodnej z jednego z punktów wejścia funkcji MAM bezpiecznym rozwiązaniem jest użycie elementu `Context` w zwykły sposób, np. przez uruchomienie klas `Activity` i użycie elementu `PackageManager`.


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a>Zastąpienie klas, metod i działań ich równoważnikami funkcji MAM

Klasy podstawowe systemu Android muszą zostać przesłonięte odpowiednimi klasami równoważnymi funkcji MAM. W tym celu znajdź wszystkie wystąpienia klas wymienionych w poniższej tabeli i przesłoń je równoważnikami z zestawu SDK aplikacji usługi Intune.

| Klasa podstawowa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
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
| android.app.PendingIntent | MAMPendingIntent (patrz uwagi poniżej) |
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
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Funkcja MAM usługi Intune dla klasy systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


### <a name="renamed-methods"></a>Metody o zmienionej nazwie


W wielu przypadkach metoda dostępna w klasie systemu Android została oznaczona jako „final” w zastępczej klasie funkcji MAM. W takim przypadku klasa zastępcza funkcji MAM udostępnia metodę o podobnej nazwie (zazwyczaj z sufiksem `MAM`), która powinna zostać przesłonięta zamiast niej. Na przykład przy tworzeniu klasy pochodnej klasy `MAMActivity` zamiast przesłaniać metodę `onCreate()` i wywoływać metodę `super.onCreate()` działanie `Activity` należy przesłonić metodę `onMAMCreate()` i wywołać metodę `super.onMAMCreate()`. Kompilator języka Java powinien wymuszać ograniczenia specyfikacji final, aby zapobiec przypadkowemu przesłonięciu oryginalnej metody zamiast jej równoważnika funkcji MAM.

### <a name="pendingintent"></a>PendingIntent
Zamiast metody `PendingIntent.get*` należy użyć metody `MAMPendingIntent.get*`. Następnie można użyć otrzymanego elementu `PendingIntent` w zwykły sposób.

### <a name="manifest-replacements"></a>Zamiany w manifeście
Należy pamiętać, że konieczne może być przeprowadzenie niektórych z powyższych zamian klas w obrębie manifestu i kodu języka Java. Ważne:
* Odwołania manifestu do klasy `android.support.v4.content.FileProvider` muszą zostać zastąpione odwołaniami do klasy `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.
* Jeśli nie ma potrzeby, aby aplikacja posiadała własną pochodną klasę aplikacji, klasa `com.microsoft.intune.mam.client.app.MAMApplication` musi być ustawiona jako nazwa klasy aplikacji używanej w manifeście.

## <a name="sdk-permissions"></a>Uprawnienia zestawu SDK

Zestaw SDK aplikacji usługi Intune wymaga trzech [uprawnień systemu Android](https://developer.android.com/guide/topics/security/permissions.html) do aplikacji, które mają ten zestaw wbudowany:

* `android.permission.GET_ACCOUNTS` (żądane w czasie wykonywania, jeśli jest wymagane)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Te uprawnienia są wymagane przez bibliotekę Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) w celu wykonania uwierzytelniania obsługiwanego przez brokera. Jeśli te uprawnienia nie zostaną przyznane dla aplikacji lub zostaną odwołane przez użytkownika, przepływy uwierzytelniania, które wymagają brokera (aplikacja Portal firmy), zostaną wyłączone.

## <a name="logging"></a>Rejestrowanie

Rejestrowanie powinno zostać zainicjowane wcześnie, aby umożliwić optymalne wykorzystanie zarejestrowanych danych. Najlepszym miejsce do zainicjowania rejestrowania jest zwykle wywołanie `Application.onMAMCreate()`.

Aby otrzymać dzienniki funkcji MAM w aplikacji, należy utworzyć [program obsługi języka Java](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) i dodać go do elementu `MAMLogHandlerWrapper`. Spowoduje to wywołanie `publish()` w programie obsługi aplikacji dla każdego komunikatu dziennika.

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
MAMComponents.get(AppPolicy.class).getIsPinRequired();
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
MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

gdzie `service` to jedna z następujących lokalizacji zapisu (SaveLocations):


    * SaveLocation.ONEDRIVE_FOR_BUSINESS
    * SaveLocation.LOCAL
    * SaveLocation.SHAREPOINT

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

Interfejs `MAMNotificationReceiver` zgodny z definicją w zestawie SDK jest przedstawiony poniżej:

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

* **WIPE_USER_AUXILIARY_DATA**: aplikacje mogą zarejestrować odbieranie tego powiadomienia, jeśli zestaw SDK aplikacji usługi Intune ma wykonywać domyślne czyszczenie selektywne, ale aplikacja ma usuwać niektóre dane pomocnicze w ramach czyszczenia.

* **REFRESH_POLICY**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po otrzymaniu tego powiadomienia wszystkie zasady usługi Intune znajdujące się w pamięci podręcznej muszą zostać unieważnione i zaktualizowane. To działanie jest ogólnie obsługiwane przez zestaw SDK, jednak powinno zostać obsłużone przez aplikację, jeśli zasady są używane w jakikolwiek trwały sposób.

* **MANAGEMENT_REMOVED**: to powiadomienie jest wysyłane w klasie `MAMUserNotification` i informuje aplikację, że przestanie ona być zarządzana. Po wycofaniu z zarządzania aplikacja nie będzie już mieć możliwości odczytu zaszyfrowanych plików, odczytu danych zaszyfrowanych za pomocą klasy MAMDataProtectionManager, interakcji z zaszyfrowanym schowkiem i innego rodzaju uczestnictwa w ekosystemie zarządzanych aplikacji.


> [!NOTE]
> Aplikacja w żadnym wypadku nie może być zarejestrowana do otrzymywania jednocześnie powiadomień `WIPE_USER_DATA` i `WIPE_USER_AUXILIARY_DATA`.


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

* Wartość **Authority** odnosi się do aktualnie używanego urzędu usługi AAD. Jeśli jest dostępne własne środowisko, w którym skonfigurowano konta usługi AAD, należy go użyć. W przypadku braku tej wartości używana jest wartość domyślna usługi Intune.

* Wartość **ClientID** to identyfikator ClientID usługi AAD, który ma być użyty. Należy użyć własnego identyfikatora ClientID aplikacji, jeśli została ona zarejestrowana w usłudze Azure AD. W przypadku braku tej wartości używana jest wartość domyślna usługi Intune.

* **NonBrokerRedirectURI** to identyfikator URI przekierowania usługi AAD, który ma być używany w przypadkach braku obsługi przez brokera. W przypadku braku określenia wartości używana jest wartość domyślna `urn:ietf:wg:oauth:2.0:oob`. Ustawienie domyślne jest odpowiednie dla większości aplikacji.

* Wartość **SkipBroker** jest używana w przypadku, gdy nie skonfigurowano wartości ClientID do użycia przekierowania URI brokera. Wartość domyślna to „false”.
    * W przypadku aplikacji, które **nie są zintegrowane z biblioteką ADAL** i które **nie mają uczestniczyć w obsługiwanym przez brokera uwierzytelnianiu/logowaniu jednokrotnym obejmującym całe urządzenie**, ustawienie powinno mieć wartość „true”. W przypadku wartości „true” jedynym używanym identyfikatorem URI przekierowania będzie NonBrokerRedirectURI.

    * Dla aplikacji obsługujących pośrednictwo w zakresie rejestracji jednokrotnej na całym urządzeniu należy użyć wartości „false”. W przypadku wartości „false” zestaw SDK wybierze brokera spośród wyniku wywołania [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) i wartości NonBrokerRedirectURI, w zależności od dostępności brokera w systemie. Zasadniczo broker będzie dostępny w aplikacji Portal firmy lub aplikacji Azure Authenticator.

### <a name="common-adal-configurations"></a>Typowe konfiguracje biblioteki ADAL

Poniżej przedstawiono typowe sposoby konfiguracji aplikacji z uwzględnieniem bibliotek ADAL. Znajdź konfigurację odpowiednią dla aplikacji i upewnij się, że dla parametrów metadanych ADAL ustawiono wymagane wartości (objaśnione powyżej).

1. **Aplikacja nie jest zintegrowana z biblioteką ADAL:**

    | Wymagany parametr ADAL | Wartość |
    |--|--|
    | Authority | Żądane środowisko, w którym skonfigurowano konta usługi AAD |
    | SkipBroker | Prawda |

2. **Aplikacja jest zintegrowana z biblioteką ADAL:**

    |Wymagany parametr ADAL| Wartość |
    |--|--|
    | Authority | Żądane środowisko, w którym skonfigurowano konta usługi AAD |
    | ClientID | Identyfikator ClientID aplikacji (generowany przez usługę Azure AD podczas rejestracji aplikacji) |
    | NonBrokerRedirectURI | Prawidłowy identyfikator URI przekierowania lub wartość `urn:ietf:wg:oauth:2.0:oob` 
    . <br><br> Upewnij się, że konfiguracja uwzględnia wartość będącą dopuszczalnym identyfikatorem URI przekierowania dla wartości ClientID aplikacji.
   | SkipBroker | False |


3. **Aplikacja jest zintegrowana z biblioteką ADAL, ale nie obsługuje pośrednictwa w zakresie uwierzytelniania/rejestracji jednokrotnej na całym urządzeniu:**

    |Wymagany parametr ADAL| Wartość |
    |--|--|
    | Authority | Żądane środowisko, w którym skonfigurowano konta usługi AAD |
    | ClientID | Identyfikator ClientID aplikacji (generowany przez usługę Azure AD podczas rejestracji aplikacji) |
    | NonBrokerRedirectURI | Prawidłowy identyfikator URI przekierowania lub wartość domyślna `urn:ietf:wg:oauth:2.0:oob`. <br><br> Upewnij się, że konfiguracja uwzględnia wartość będącą dopuszczalnym identyfikatorem URI przekierowania dla wartości ClientID aplikacji.
    | SkipBroker | **True** |

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

3. Jeśli konto użytkownika zostało całkowicie usunięte, aplikacja powinna wykonać wywołanie `unregisterAccountForMAM()`, aby usunąć konto z procesu zarządzania w usłudze Intune.

    > [!NOTE]
    > W przypadku tymczasowego wylogowania użytkownika wywołanie `unregisterAccountForMAM()` przez aplikację nie jest wymagane. Wywołanie może zainicjować całkowite wyczyszczenie danych firmowych dla danego użytkownika.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Wszystkie niezbędne interfejsy API używane do uwierzytelniania i rejestracji można znaleźć w interfejsie `MAMEnrollmentManager`. Odwołanie do `MAMEnrollmentManager` można uzyskać w następujący sposób:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

Zwrócone wystąpienie `MAMEnrollmentManager` na pewno nie będzie puste. Metody interfejsu API można podzielić na dwie kategorie: metody **uwierzytelniania** i metody **rejestracji konta**.

> [!NOTE]
> Interfejs `MAMEnrollmentManager` zawiera pewne metody interfejsu API, które wkrótce staną się przestarzałe. W bloku kodu poniżej są przedstawione tylko właściwe metody i kody wynikowe.

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

1. Aplikacja musi zaimplementować interfejs `MAMServiceAuthenticationCallback`, aby możliwe było zażądanie tokenu ADAL dla danego identyfikatora użytkownika i zasobu przez zestaw SDK. Wystąpienie wywołania zwrotnego musi zostać przekazane do interfejsu `MAMEnrollmentManager` przez wywołanie odpowiedniej metody `registerAuthenticationCallback()`. Token może być wymagany na bardzo wczesnym etapie cyklu życia aplikacji w celu przeprowadzenia ponownych prób rejestracji lub ewidencjonowania odświeżenia zasad ochrony aplikacji, dlatego idealnym miejscem na zarejestrowanie wywołania zwrotnego jest metoda `onMAMCreate()` podklasy `MAMApplication` aplikacji.

2. Metoda `acquireToken()` powinna uzyskać token dostępu dla żądanego identyfikatora zasobu dla danego użytkownika. Jeśli uzyskanie żądanego tokenu jest niemożliwe, powinna zostać zwrócona wartość null.

3. Jeżeli aplikacja nie jest w stanie dostarczyć tokenu po wykonaniu wywołania `acquireToken()` przez zestaw SDK — na przykład gdy dyskretne uwierzytelnianie nie powiedzie się, a moment nie jest właściwy, aby wyświetlić interfejs użytkownika — aplikacja może dostarczyć token w późniejszym czasie przez wywołanie metody `updateToken()`. Ta sama nazwa UPN, identyfikator usługi AAD i identyfikator zasobu, których dotyczyło wcześniejsze wywołanie `acquireToken()`, muszą zostać przekazane do wywołania `updateToken()` wraz z tokenem, który został ostatecznie uzyskany. Aplikacja powinna wywołać tę metodę najszybciej, jak to możliwe po zwróceniu wartości „null” w wyniku podanego wywołania zwrotnego.

> [!NOTE]
> Zestaw SDK będzie okresowo wykonywać wywołania `acquireToken()` w celu uzyskania tokenu, dlatego wywołanie `updateToken()` nie jest bezwzględnie konieczne. Jest ono jednak zalecane, ponieważ może ułatwić terminowe rejestrowanie i ewidencjonowanie zasad ochrony aplikacji.


### <a name="account-registration"></a>Rejestracja konta

W tej sekcji opisano metody interfejsu API rejestrowania konta używane w interfejsie `MAMEnrollmentManager` oraz sposób ich użycia.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Aby zarejestrować konto do celów zarządzania, aplikacja musi wykonać wywołanie `registerAccountForMAM()`. Konto użytkownika jest identyfikowane z użyciem jego nazwy UPN i identyfikatora użytkownika usługi AAD. Wymagany jest również identyfikator dzierżawy umożliwiający powiązanie danych rejestracji z dzierżawą usługi AAD użytkownika. Zestaw SDK może próbować zarejestrować aplikację dla danego użytkownika w usłudze MAM. W przypadku niepowodzenia rejestracji zestaw będzie okresowo ponawiać próbę rejestracji do czasu wyrejestrowania konta. Próby są zwykle powtarzane co 12–24 godzin. Zestaw SDK dostarcza informacje o stanie kolejnych prób rejestracji w sposób asynchroniczny za pośrednictwem powiadomień.

2. Uwierzytelnienie w usłudze AAD jest wymagane, dlatego najkorzystniej jest zarejestrować konto użytkownika po tym, jak zalogował się on do aplikacji i został pomyślnie uwierzytelniony z użyciem biblioteki ADAL.
    * Identyfikator użytkownika usługi AAD i identyfikator dzierżawy są zwracane przez wywołanie uwierzytelniania biblioteki ADAL w ramach obiektu [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android). Identyfikator dzierżawy pochodzi z metody `AuthenticationResult.getTenantID()`.
    * Informacje o użytkowniku znajdują się w podobiekcie typu `UserInfo`, który pochodzi z klasy `AuthenticationResult.getUserInfo()`, a identyfikator użytkownika usługi AAD jest pobierany z tego obiektu przez wywołanie metody `UserInfo.getUserId()`.

3. Aby wyrejestrować konto z zarządzania przy użyciu usługi Intune, niezbędne jest wywołanie przez aplikację metody `unregisterAccountForMAM()`. Jeśli konto zostało pomyślnie zarejestrowane i jest zarządzane, zestaw SDK wyrejestruje konto i wyczyści powiązane z nim dane. Okresowe ponowne próby rejestracji konta zostaną wstrzymane. Zestaw SDK dostarcza informacje o stanie żądania wyrejestrowania w sposób asynchroniczny za pośrednictwem powiadomień.

### <a name="important-implementation-notes"></a>Ważne uwagi dotyczące implementacji

#### <a name="authentication"></a>Uwierzytelnianie

* Niedługo po wykonaniu wywołania `registerAccountForMAM()` aplikacja może za pośrednictwem interfejsu `MAMServiceAuthenticationCallback` otrzymać wywołanie zwrotne w innym wątku. Najkorzystniej jest, gdy aplikacja uzyska własny token z biblioteki ADAL przed zarejestrowaniem konta, co pozwoli przyśpieszyć uzyskanie **tokenu usługi MAMService**. Jeśli aplikacja zwróci prawidłowy token z wywołania zwrotnego, rejestracja będzie kontynuowana, a wynik końcowy zostanie przesłany do aplikacji za pośrednictwem powiadomienia.

* Jeśli aplikacja nie zwróci prawidłowego tokenu usługi AAD, ostatecznym wynikiem próby rejestracji będzie element `AUTHENTICATION_NEEDED`. Jeśli aplikacja otrzyma ten wynik za pośrednictwem powiadomienia, proces rejestracji będzie można przyspieszyć przez uzyskanie **tokenu usługi MAMService** i wywołanie metody `updateToken()` w celu ponownego zainicjowania procesu rejestracji. _Nie_ jest to jednak ściśle wymagane, ponieważ zestaw SDK okresowo ponawia próbę rejestracji i inicjuje wywołanie zwrotne w celu uzyskania tokenu.

* Zarejestrowana metoda `MAMServiceAuthenticationCallback` aplikacji również zostanie wywołana w celu uzyskania tokenu na potrzeby okresowego ewidencjonowania odświeżonych zasad ochrony aplikacji. Jeśli aplikacja nie dostarczy tokenu na żądanie, nie otrzyma powiadomienia, powinna jednak podjąć próbę uzyskania tokenu i wywołania metody `updateToken()` w następnym dogodnym momencie w celu przyspieszenia procesu ewidencjonowania. Jeśli token nie zostanie dostarczony, wywołanie zwrotne nadal będzie wykonywane podczas następnej próby ewidencjonowania.

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

Ta metoda zostaje wywołana zanim zestaw SDK wyświetli domyślny interfejs użytkownika z blokadą. Jeśli w wyniku próby nastąpi zmiana tożsamości działania lub wyrejestrowanie użytkownika, który podjął próbę rejestracji, zestaw SDK nie zablokuje działania. W tej sytuacji ochrona przed wyciekiem danych firmowych zależy od aplikacji.

### <a name="notifications"></a>Powiadomienia

Został dodany nowy typ metody `MAMNotification` umożliwiający przesyłanie do aplikacji informacji o tym, że żądanie rejestracji zostało zrealizowane.  Powiadomienie `MAMEnrollmentNotification` zostanie odebrane za pośrednictwem interfejsu `MAMNotificationReceiver` zgodnie z opisem w sekcji [Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK](#register-for-notifications-from-the-sdk).

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

Metoda `getEnrollmentResult()` zwraca wynik żądania rejestracji.  Ponieważ metoda `MAMEnrollmentNotification` stanowi rozszerzenie metody `MAMUserNotification`, tożsamość użytkownika, dla którego podjęto próbę rejestracji, także jest dostępna. Aby możliwe było odbieranie tych powiadomień, szczegółowo opisanych w sekcji [Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK](#Register-for-notifications-from-the-SDK), aplikacja musi zaimplementować interfejs `MAMNotificationReceiver`.

Stan zarejestrowanego konta użytkownika może ulec zmianie po odebraniu powiadomienia dotyczącego rejestracji, jednak w niektórych przypadkach nie zmieni się (np. w przypadku otrzymania powiadomienia `AUTHORIZATION_NEEDED` po uzyskaniu bardziej szczegółowego wyniku, takiego jak `WRONG_USER`, jako stan konta zostanie zachowany wynik bardziej szczegółowy).


## <a name="protecting-backup-data"></a>Ochrona danych kopii zapasowej

Począwszy od systemu Android Marshmallow (interfejs API w wersji 23), na potrzeby aplikacji są dostępne dwa sposoby tworzenia kopii zapasowych danych. Każda opcja jest dostępna dla aplikacji i wymaga różnych kroków w celu zapewnienia, że ochrona danych usługi Intune jest implementowana prawidłowo. Możesz przejrzeć tabelę poniżej dotyczącą odpowiednich akcji wymaganych do osiągnięcia poprawnego zachowania w zakresie ochrony danych.  Aby uzyskać więcej informacji na temat metod wykonywania kopii zapasowych, zobacz [Przewodnik po interfejsie API systemu Android](http://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Automatyczne wykonywanie kopii zapasowej dla aplikacji

System Android oferuje obecnie funkcję [automatycznego tworzenia pełnej kopii zapasowej](https://developer.android.com/guide/topics/data/autobackup.html) w usłudze Dysk Google dla aplikacji na urządzeniach z systemem Android Marshmallow, niezależnie od docelowego interfejsu API aplikacji. Jeśli w pliku AndroidManifest.xml dla elementu `android:allowBackup` została jawnie ustawiona wartość **false**, to aplikacja nigdy nie zostanie umieszczona w kolejce do wykonywania kopii zapasowej przez system Android i dane „firmowe” pozostaną w aplikacji. W takim przypadku nie są wymagane żadne dalsze działania.

Jednak domyślnie atrybut `android:allowBackup` ma wartość true, nawet jeśli atrybut `android:allowBackup` nie został określony w pliku manifestu. Oznacza to, że kopia zapasowa wszystkich danych aplikacji jest automatycznie tworzona na koncie usługi Dysk Google użytkownika. Jest to zachowanie domyślne, które stanowi **ryzyko przecieku danych**. Z tego powodu zestaw SDK wymaga wprowadzenia zmian przedstawionych poniżej w celu zapewnienia ochrony danych.  Zastosowanie poniższych wskazówek jest ważne, aby właściwie ochronić dane klienta, jeśli aplikacja ma działać na urządzeniach z systemem Android Marshmallow.  

Usługa Intune umożliwia korzystanie ze wszystkich [funkcji automatycznego tworzenia kopii zapasowych](https://developer.android.com/guide/topics/data/autobackup.html) dostępnych w systemie Android, w tym możliwość definiowania niestandardowych reguł w pliku XML, należy jednak wykonać poniższą procedurę, aby zabezpieczyć dane:

1. Jeśli aplikacja **nie** używa własnych niestandardowych klas BackupAgent, użyj domyślnej klasy MAMBackupAgent, aby zezwolić na automatyczne tworzenie pełnych kopii zapasowych zgodnych z zasadami usługi Intune. W takim przypadku możesz zignorować atrybut manifestu `android:fullBackupOnly`, ponieważ nie ma on zastosowania do naszego agenta kopii zapasowej. Umieść następujące wpisy w manifeście aplikacji:

    ```xml
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

Opcja [Kopie zapasowe typu klucz/wartość](https://developer.android.com/guide/topics/data/keyvaluebackup.html) jest dostępna dla wszystkich interfejsów API w wersji 8 i nowszych. Umożliwia ona przesyłanie danych aplikacji do usługi [Android Backup Service](https://developer.android.com/google/backup/index.html). Ilość danych na użytkownika aplikacji jest ograniczona do 5 MB. Jeśli korzystasz z opcji Kopie zapasowe typu klucz/wartość, użyj klasy **BackupAgentHelper** lub **BackupAgent**.

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

1.  Do przechodzenia między wpisami kopii zapasowej należy używać pętli `while(data.readNextHeader())`*.

2.  Jeśli metoda `data.getKey()`* nie odpowiada kluczowi wpisanemu w elemencie `onBackup`, należy użyć wywołania `data.skipEntityData()`*. Jeśli ten krok nie zostanie wykonany, przywrócenie danych może się nie powieść.

3.  Należy unikać cofania się podczas przetwarzania wpisów kopii zapasowej w ramach konstrukcji `while(data.readNextHeader())`*, ponieważ wpisy zapisywane automatycznie zostaną utracone.

* Gdzie `data` to lokalna nazwa zmiennej **BackupDataInput** przekazanej do aplikacji podczas przywracania.

## <a name="multi-identity-optional"></a>Wiele tożsamości (opcjonalnie)

### <a name="overview"></a>Przegląd
Domyślnie zestaw SDK aplikacji usługi Intune będzie stosować zasady względem aplikacji jako całości. Wiele tożsamości to opcjonalna funkcja ochrony aplikacji usługi Intune, którą można włączyć w celu zezwolenia na stosowanie zasad na poziomie poszczególnych tożsamości. Wymaga to znacznie pełniejszego uczestnictwa aplikacji niż inne funkcje ochrony aplikacji.

Aplikacja *musi* poinformować zestaw SDK aplikacji, gdy zamierza zmienić aktywną tożsamość. W niektórych przypadkach zestaw SDK również powiadomi aplikację, gdy wymagana jest zmiana tożsamości. Jednak w większości przypadków funkcja MAM nie ma informacji, jakie w określonym momencie dane są wyświetlane w interfejsie użytkownika lub używane w wątku, w związku z czym funkcja MAM korzysta z aplikacji, aby ustawić poprawną tożsamość w celu uniknięcia wycieku danych. W poniższych sekcjach zostaną przedstawione pewne konkretne scenariusze, w ramach których wymagana będzie akcja aplikacji.

> [!NOTE]
>  Brak odpowiedniego udziału aplikacji może spowodować wycieki danych i inne problemy z zabezpieczeniami.

Po zarejestrowaniu urządzenia lub aplikacji przez użytkownika zestaw SDK rejestruje tę tożsamość i uznaje ją za podstawową tożsamość zarządzaną w usłudze Intune. Inni użytkownicy w aplikacji są traktowani jako niezarządzani z nieograniczonymi ustawieniami zasad.

> [!NOTE]
> Aktualnie obsługiwana jest tylko jedna tożsamość zarządzana w usłudze Intune na urządzenie.

Należy zauważyć, że tożsamość jest definiowana po prostu jako ciąg. W tożsamościach **jest rozróżniana wielkość liter**, natomiast żądania tożsamości wysyłane do zestawu SDK mogą nie zwracać tej samej wielkości liter, której pierwotnie użyto podczas ustawiania tożsamości.

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
  2. Poziom kontekstu (zazwyczaj działania)
  3. Poziom procesu

Tożsamość ustawiona na poziomie wątku zastępuje tożsamość ustawioną na poziomie kontekstu, która zastępuje tożsamość ustawioną na poziomie procesu. Tożsamość ustawiona na poziomie kontekstu jest używana tylko w odpowiednio powiązanych scenariuszach. Na przykład operacje WE/WY plików nie mają skojarzonego kontekstu. Najczęściej aplikacja ustawia tożsamość kontekstu w ramach działania. Aplikacja *nie może* wyświetlać danych na potrzeby tożsamości zarządzanej, chyba że tożsamość działania jest ustawiona na tą samą tożsamość. Ogólnie rzecz biorąc tożsamość na poziomie procesu jest przydatna jedynie wtedy, gdy aplikacja pracuje tylko z jednym użytkownikiem jednocześnie w ramach wszystkich wątków. W przypadku wielu aplikacji korzystanie z tej funkcji może nie być konieczne.

Do ustawiania tożsamości i pobierania ustawionych wcześniej wartości tożsamości służą następujące metody w klasie `MAMPolicyManager`.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

  /**
   * Get the currently applicable app policy. Same as
   * MAMComponents.get(AppPolicy.class). This method does
   * not take the context identity into account.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
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
| NOT_ALLOWED | Zmiana tożsamości jest niedozwolona. Zmiana tożsamości jest niedozwolona. Ma to miejsce, jeśli zostanie podjęta próba ustawienia tożsamości interfejsu użytkownika (kontekstu), gdy dla bieżącego wątku jest już ustawiona inna tożsamość. |
| CANCELLED | Użytkownik anulował zmianę tożsamości, czyli prawdopodobnie nacisnął przycisk wstecz w monicie o podanie kodu PIN/uwierzytelnienie. |
| FAILED | Z nieokreślonego powodu nie można zmienić tożsamości.|

Przed wyświetleniem lub użyciem danych firmowych aplikacja *musi* zapewnić, że przełączenie tożsamości zakończyło się pomyślnie. Obecnie przełączanie tożsamości procesu i wątku zawsze powiedzie się dla aplikacji z włączoną obsługą wielu tożsamości, jednak firma Microsoft zastrzega sobie prawo do dodania warunków błędów. Przełączenie tożsamości interfejsu użytkownika może zakończyć się niepowodzeniem w przypadku podania nieprawidłowych argumentów, jeśli będą one powodowały konflikt z tożsamością wątku, lub jeśli użytkownik anulował wymagania dotyczące uruchamiania warunkowego (na przykład przez naciśnięcie przycisku Wstecz na ekranie numeru PIN).


W przypadku ustawienia tożsamości na poziomie kontekstu wynik jest raportowany asynchronicznie. Jeśli kontekst jest działaniem, zestaw SDK nie będzie w stanie określić, czy zmiana tożsamości powiodła się, dopóki nie zostanie wykonane warunkowe uruchomienie, co może wymagać od użytkownika wprowadzenia numeru PIN lub podania poświadczeń firmowych. Oczekuje się, że aplikacja zaimplementuje metodę `MAMSetUIIdentityCallback`, aby otrzymać ten wynik. Dla tego parametru jest dozwolone podanie wartości „null”.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Można również ustawić tożsamość działania bezpośrednio przy użyciu metody w klasie `MAMActivity`, zamiast wykonywać wywołanie `MAMPolicyManager.setUIPolicyIdentity`. W tym celu użyj następującej metody:

```java
     public final void switchMAMIdentity(final String newIdentity);
```

Możesz również zastąpić metodę w klasie `MAMActivity`, aby otrzymywać powiadomienia o wynikach prób zmiany tożsamości danego działania.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> Przełączenie tożsamości może wymagać ponownego utworzenia odpowiedniego działania. W takim przypadku wywołanie zwrotne metody `onSwitchMAMIdentityComplete` zostanie dostarczone do nowego wystąpienia tego działania.


### <a name="implicit-identity-changes"></a>Niejawne zmienianie tożsamości

Oprócz możliwości ustawiania tożsamości przez aplikację tożsamość wątku lub kontekstu może zostać zmieniona na podstawie transferu danych przychodzących od innej aplikacji obsługującej usługę Intune i objętej zasadą ochrony aplikacji.

#### <a name="examples"></a>Przykłady

  1. Jeśli działanie zostanie uruchomione z klasy `Intent` wysłanej przez inną aplikację z funkcją MAM, tożsamość tego działania zostanie ustawiona na podstawie obowiązującej tożsamości w drugiej aplikacji w chwili wysłania klasy `Intent`.

  2.  W przypadku usług tożsamość wątku zostanie ustawiona w podobny sposób na czas trwania wywołania metody `onStart` lub `onBind`. Wywołania do klasy `Binder` zwrócone z metody `onBind` także powodują tymczasowe ustawienie tożsamości wątku.

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

    Gdzie ```AppIdentitySwitchResult``` ma wartość SUCCESS lub FAILURE.

Metoda `onMAMIdentitySwitchRequired` jest wywoływana dla wszystkich niejawnych zmian tożsamości z wyjątkiem tych wykonywanych za pośrednictwem klasy Binder zwróconych z klasy `MAMService.onMAMBind`. Implementacje domyślne klasy `onMAMIdentitySwitchRequired` powodują natychmiastowe wywołanie metody:

*  `reportIdentitySwitchResult(FAILURE)`, gdy przyczyna ma wartość RESUME_CANCELLED;

*  `reportIdentitySwitchResult(SUCCESS)` we wszystkich innych przypadkach.

  Nie oczekuje się, że większość aplikacji będzie musiała blokować lub opóźniać przełączanie tożsamości w inny sposób. Jeśli jednak zajdzie taka potrzeba, należy rozważyć następujące kwestie:

  * Jeśli przełączanie tożsamości jest zablokowane, skutek jest taki sam, jak w przypadku uniemożliwienia transferu danych przychodzących przez ustawienia udostępniania `Receive`.

  * Jeśli usługa jest uruchomiona w wątku głównym, klasa `reportIdentitySwitchResult` **musi** być wywoływana synchronicznie, w przeciwnym razie wątek interfejsu użytkownika ulegnie zawieszeniu.

  * W przypadku utworzenia elementu **Działanie** klasa `onMAMIdentitySwitchRequired` zostanie wywołana przed metodą `onMAMCreate`. Jeśli aplikacja musi wyświetlić interfejs użytkownika w celu ustalenia, czy zezwolić na przełączenie tożsamości, ten interfejs użytkownika musi zostać pokazany przy użyciu *innego* działania.

  * W przypadku **działania**, dla którego żądanie przełączenia do pustej tożsamości ma przyczynę o wartości RESUME_CANCELLED, aplikacja musi zmodyfikować wznowione działanie tak, aby były wyświetlane dane spójne z tym przełączeniem tożsamości.  Jeśli nie jest to możliwe, aplikacja powinna odmówić przełączenia, a użytkownik zostanie ponownie poproszony o przestrzeganie zasad dla wznawianej tożsamości (np. przez wyświetlenie ekranu wprowadzania numeru PIN aplikacji).

    > [!NOTE]
    > Aplikacja z obsługą wielu tożsamości zawsze będzie otrzymywać dane przychodzące z aplikacji zarządzanych i niezarządzanych. Na aplikacji leży odpowiedzialność za to, aby traktować dane z zarządzanych tożsamości w zarządzany sposób.

  Jeśli żądana tożsamość jest zarządzana (w celu sprawdzenia można użyć metody `MAMPolicyManager.getIsIdentityManaged`), ale aplikacja nie może użyć danego konta (ponieważ na przykład konta, takie jak konta e-mail, muszą najpierw zostać skonfigurowane w aplikacji), to należy odmówić przełączenia tożsamości.



  ### <a name="file-protection"></a>Ochrona plików

  Każdy plik ma tożsamość skojarzoną z nim w momencie utworzenia na podstawie tożsamości procesu i wątku. Ta tożsamość będzie używana zarówno do szyfrowania, jak i selektywnego czyszczenia. Szyfrowane będą tylko pliki, których tożsamość jest zarządzana i ma zasady wymagające szyfrowania. Domyślna funkcja selektywnego czyszczenia danych zestawu SDK będzie czyściła tylko pliki skojarzone z zarządzaną tożsamością, dla której zażądano czyszczenia. Aplikacja może wysyłać zapytania dotyczące tożsamości pliku lub może zmieniać tę tożsamość przy użyciu klasy `MAMFileProtectionManager`.

  ```java
    public final class MAMFileProtectionManager {
    /**
         * Protect a file. This will synchronously trigger whatever protection is required for the 
           file, and will tag the file for future protection changes.

         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
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
        *       Identity to set.
        * @param file
        *       File to protect.
        *
        * @throws IOException
        *       If the file cannot be protected.

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
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```
#### <a name="app-responsibility"></a>Odpowiedzialność aplikacji
Funkcja MAM nie może automatycznie wywnioskować relacji między odczytywanymi plikami i danymi wyświetlanymi w obszarze `Activity`. Aplikacje *muszą* odpowiednio ustawić tożsamość interfejsu użytkownika przed wyświetleniem danych firmowych. Obejmuje to odczyt danych z plików. Jeśli plik pochodzi spoza aplikacji (z obiektu `ContentProvider` lub odczytu z publicznie zapisywalnej lokalizacji), aplikacja *musi* podjąć próbę określenia tożsamości pliku (przy użyciu metody `MAMFileProtectionManager.getProtectionInfo`) przed wyświetleniem informacji odczytanych z pliku. Jeśli metoda `getProtectionInfo` zgłosi niepustą tożsamość o wartości innej niż null, tożsamość interfejsu użytkownika *musi* zostać ustawiona w taki sposób, aby była zgodna z tą tożsamością (przy użyciu metody `MAMActivity.switchMAMIdentity` lub `MAMPolicyManager.setUIPolicyIdentity`). Jeśli przełączenie tożsamości nie powiedzie się, dane z pliku *nie mogą* zostać wyświetlone.

Przykładowy przepływ może wyglądać podobnie do poniższego:
  * Użytkownik wybiera dokument, który zostanie otworzony w aplikacji
  * Podczas przepływu otwierania, ale przed odczytaniem danych z dysku, aplikacja potwierdza tożsamość, która powinna zostać użyta do wyświetlenia zawartości
    * MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)
    * if(info) MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)
    * Aplikacja oczekuje na zgłoszenie wyniku do wywołania zwrotnego
    * Jeśli zgłoszony wynik oznacza niepowodzenie, aplikacja nie wyświetla dokumentu.
  * Aplikacja otwiera i renderuje plik

## <a name="offline-scenarios"></a>Scenariusze w trybie offline

Na znakowanie tożsamości pliku ma wpływ tryb offline. Należy uwzględnić następujące kwestie:

  * Jeśli nie zainstalowano aplikacji Portal firmy, nie można tagować tożsamości plików.

  * Jeśli aplikacja Portal firmy została zainstalowana, ale aplikacja nie ma zasad zarządzania aplikacjami mobilnymi usługi Intune, tagowanie tożsamości plików nie będzie niezawodne.

  * Po udostępnieniu tagowania tożsamości plików wszystkie wcześniej utworzone pliki będą traktowane jako osobiste/niezarządzane (należące do tożsamości o pustym ciągu), chyba że aplikacja została wcześniej zainstalowana jako aplikacja zarządzana z obsługą jednej tożsamości — w takim przypadku będą one traktowane jako należące do zarejestrowanego użytkownika.

### <a name="directory-protection"></a>Ochrona katalogu

Katalogi można chronić przy użyciu tej samej metody `protect`, której używa się do ochrony plików. Należy pamiętać, że ochrona katalogów ma charakter cykliczny i obejmuje wszystkie pliki i podkatalogi w danym katalogu, jak również nowe pliki tworzone w katalogu. Ponieważ ochrona katalogów jest stosowana cyklicznie, wywołanie `protect` może w przypadku bardzo dużych katalogów zająć sporo czasu. W związku z tym aplikacje zapewniające ochronę katalogów zawierających dużą liczbę plików mogą uruchamiać operację `protect` asynchronicznie w ramach wątku w tle.

### <a name="data-protection"></a>Ochrona danych

Nie jest możliwe tagowanie pliku jako należącego do wielu tożsamości. Aplikacje, które muszą przechowywać dane należące do różnych użytkowników w tym samym pliku, mogą robić to ręcznie przy użyciu funkcji oferowanych przez klasę `MAMDataProtectionManager`. Umożliwia to aplikacji szyfrowanie danych i powiązanie ich z określonym użytkownikiem. Zaszyfrowane dane można przechowywać na dysku w pliku. Można tworzyć zapytania dotyczące danych skojarzonych z tożsamością i dane te można później odszyfrować.

Aplikacje korzystające z klasy `MAMDataProtectionManager` powinny zaimplementować odbiornik powiadomień `MANAGEMENT_REMOVED`. Jeśli podczas zapewniania ochrony buforów zostało włączone szyfrowanie plików, po zakończeniu procesu powiadamiania bufory, które były chronione za pomocą tej klasy, nie będą już mogły zostać odczytane. Aplikacja może rozwiązać ten problem przez wywołanie podczas tego procesu powiadamiania metody MAMDataProtectionManager.unprotect dla wszystkich buforów. Należy zauważyć, że bezpieczne jest również wywoływanie ochrony podczas tego procesu powiadamiania, jeśli pożądane jest zachowanie informacji o tożsamości — szyfrowanie jest zawsze wyłączone w czasie powiadamiania.

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

Jeśli aplikacja dostarcza dane firmowe inne niż **ParcelFileDescriptor** za pośrednictwem elementu **ContentProvider**, musi wywołać metodę `isProvideContentAllowed(String)` w obiekcie `MAMContentProvider`, przekazując nazwę UPN tożsamości właściciela (główną nazwę użytkownika) danej zawartości. Jeśli ta funkcja zwróci wartość false, zawartość może *nie zostać* zwrócona do elementu wywołującego. Deskryptory plików zwrócone za pośrednictwem dostawcy zawartości są obsługiwane automatycznie na podstawie tożsamości plików.

### <a name="selective-wipe"></a>Selektywne czyszczenie

Jeśli aplikacja została zarejestrowana do odbierania powiadomień `WIPE_USER_DATA`, nie będzie ona otrzymywać korzyści związanych z domyślnym selektywnym czyszczeniem danych zestawu SDK. W przypadku aplikacji z obsługą wielu tożsamości taka utrata może być bardziej znacząca, ponieważ domyślne selektywne czyszczenie danych funkcji MAM będzie czyścić tylko pliki o określonej tożsamości.

Jeśli aplikacja obsługująca wiele tożsamości ma przeprowadzać domyślne selektywne czyszczenie danych funkcji MAM _**oraz**_ wykonywać własne działania w zakresie czyszczenia, wymagana jest rejestracja pod kątem otrzymywania powiadomień `WIPE_USER_AUXILIARY_DATA`. To powiadomienie zostanie wysyłane przez zestaw SDK bezpośrednio przed wykonaniem domyślnego selektywnego czyszczenia danych funkcji zarządzania aplikacjami mobilnymi. Aplikacja w żadnym wypadku nie może być zarejestrowana do otrzymywania jednocześnie powiadomień WIPE_USER_DATA i WIPE_USER_AUXILIARY_DATA.

## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a>Włączanie docelowej konfiguracji funkcji MAM dla aplikacji systemu Android (opcjonalnie)
Pary klucz-wartość specyficzne dla aplikacji można skonfigurować w konsoli usługi Intune. Te pary klucz-wartość nie są w ogóle interpretowane przez usługę Intune, ale są po prostu przekazywane do aplikacji. W tym celu aplikacje, które mają otrzymywać taką konfigurację, mogą użyć klas `MAMAppConfigManager` i `MAMAppConfig`. Jeśli wiele zasad jest przeznaczonych dla tej samej aplikacji, może istnieć wiele powodujących konflikt wartości dostępnych dla tego samego klucza.

### <a name="example"></a>Przykład
```
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
LOGGER.info("App Config Data = " + (appConfig == null ? "null" : appConfig.getFullData()));
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

### <a name="mamappconfig-reference"></a>Informacje dotyczące klasy MAMAppConfig

```
public interface MAMAppConfig {
    /**
     * Conflict resolution types for Boolean values.
     */
    enum BooleanQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns true if any of the values are true.
         */
        Or,
        /**
         * In case of conflict, returns false if any of the values are false.
         */
        And
    }

    /**
     * Conflict resolution types for integer and double values.
     */
    enum NumberQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the minimum Integer.
         */
        Min,
        /**
         * In case of conflict, returns the maximum Integer.
         */
        Max
    }

    /**
     * Conflict resolution types for Strings.
     */
    enum StringQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the first result ordered alphabetically.
         */
        Min,
        /**
         * In case of conflict, returns the last result ordered alphabetically.
         */
        Max
    }

    /**
     * Retrieve the List of Dictionaries containing all the custom
     *  config data sent by the MAMService. This will return every
     * Application Configuration setting available for this user, one
     *  mapping for each policy applied to the user.
     */
    List<Map<String, String>> getFullData();

    /**
     * Returns true if there is more than one targeted custom config setting for the key provided. 
     */
    boolean hasConflict(String key);

    /**
     * @return a Boolean value for the given key if it can be coerced into a Boolean, or 
     * null if none exists or it cannot be coerced.
     */
    Boolean getBooleanForKey(String key, BooleanQueryType queryType);

    /**
     * @return a Long value for the given key if it can be coerced into a Long, or null if none exists or it cannot be coerced.
     */
    Long getIntegerForKey(String key, NumberQueryType queryType);

    /**
     * @return a Double value for the given key if it can be coerced into a Double, or null if none exists or it cannot be coerced.
     */
    Double getDoubleForKey(String key, NumberQueryType queryType);

    /**
     * @return a String value for the given key, or null if none exists.
     */
    String getStringForKey(String key, StringQueryType queryType);

    /**
     * Like getBooleanForKey except returns all values if multiple are present.
     */
    List<Boolean> getAllBooleansForKey(String key);

    /**
     * Like getIntegerForKey except returns all values if multiple are present.
     */
    List<Long> getAllIntegersForKey(String key);

    /**
     * Like getDoubleForKey except returns all values if multiple are present.
     */
    List<Double> getAllDoublesForKey(String key);

    /**
     * Like getStringForKey except returns all values if multiple are present.
     */
    List<String> getAllStringsForKey(String key);
}
```

### <a name="notification"></a>Powiadomienie
Konfiguracja aplikacji wprowadza nowy typ powiadomienia:
* **REFRESH_APP_CONFIG**: to powiadomienie jest wysyłane w ramach obiektu `MAMUserNotification` i służy do informowania aplikacji, że nowe dane konfiguracji aplikacji są dostępne.

Aby uzyskać więcej informacji o możliwościach interfejsu API programu Graph w odniesieniu do wartości docelowej konfiguracji MAM, zobacz [Konfiguracja docelowej konfiguracji MAM w zakresie odwołań do interfejsu API programu Graph](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create). <br>

Więcej informacji na temat tworzenia zasad docelowej konfiguracji aplikacji funkcji MAM w systemie Android można znaleźć w sekcji poświęconej docelowej konfiguracji aplikacji funkcji MAM znajdującej się w artykule [How to use Microsoft Intune app configuration policies for Android](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-android) (Jak używać zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu Android).

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

## <a name="limitations"></a>Ograniczenia

### <a name="file-size-limitations"></a>Ograniczenia rozmiaru plików

Ograniczenia formatu pliku wykonywalnego dla platformy Dalvik mogą stać się problemem w przypadku uruchamiania dużych baz kodu bez narzędzia [ProGuard](http://proguard.sourceforge.net/). W szczególności mogą wystąpić następujące ograniczenia:

1.  Limit 65 000 dla pól.
2.  Limit 65 000 dla metod.

### <a name="policy-enforcement-limitations"></a>Ograniczenia wymuszania zasad

* **Przechwytywanie ekranu**: zestaw SDK nie może wymusić nowej wartości ustawienia przechwytywania ekranu w przypadku działań przetworzonych już przez metodę Activity.onCreate. Może to spowodować, że wystąpi okres, w którym dla aplikacji będzie wyłączone tworzenie zrzutów ekranu, ale wciąż będzie to możliwe.

* **Używanie elementów rozpoznawania zawartości**: zasady „transferu lub odbierania” usługi Intune mogą zablokować lub częściowo zablokować użycie elementu rozpoznawania zawartości na potrzeby dostępu do dostawcy zawartości w innej aplikacji. To spowoduje, że metody klasy ContentResolver będą zwracać wartość null lub zgłaszać wartość błędu (np. klasa `openOutputStream` będzie zgłaszać wyjątek `FileNotFoundException` , jeśli jest zablokowana). Aplikacja może określić, czy błąd zapisu danych przez element rozpoznawania zawartości został spowodowany przez zasady (lub może zostać spowodowany przez zasady) za pomocą wywołania:
    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```
    lub jeśli nie jest istnieje żadne skojarzone działanie

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    W tym drugim przypadku aplikacje z wieloma tożsamościami muszą odpowiednio ustawić tożsamość wątku (lub przekazać jawną tożsamość do wywołania metody `getPolicy`).
    
### <a name="exported-services"></a>Wyeksportowane usługi

 Plik AndroidManifest.xml dołączony do zestawu SDK aplikacji usługi Intune zawiera element **MAMNotificationReceiverService**. Musi to być wyeksportowana usługa umożliwiająca aplikacji Portal firmy wysyłanie powiadomień do usprawnionych aplikacji. Usługa sprawdza obiekt wywołujący, aby zapewnić, że tylko aplikacja Portal firmy ma zezwolenie na wysyłanie powiadomień.

## <a name="expectations-of-the-sdk-consumer"></a>Oczekiwania konsumentów korzystających z zestawu SDK

Zestaw SDK usługi Intune obsługuje kontrakt udostępniony przez interfejs API systemu Android, chociaż w wyniku wymuszania zasad warunki błędu mogą być wyzwalane częściej. Następujące najlepsze rozwiązania dla systemu Android zmniejszają prawdopodobieństwo wystąpienia błędu:

* W przypadku funkcji zestawu SDK systemu Android, które mogą zwrócić wartość null, prawdopodobieństwo zwrócenia wartości null jest teraz większe.  Aby zminimalizować problemy, upewnij się, że sprawdzenia wartości null znajdują się w odpowiednich miejscach.

* Funkcje, które można sprawdzić, muszą zostać sprawdzone za pomocą zastępczych interfejsów API funkcji MAM.

* Wszystkie funkcje pochodne muszą przywoływać swoje superklasy.

* Unikaj stosowania jakiegokolwiek interfejsu API w sposób niejednoznaczny. Na przykład użycie metody `Activity.startActivityForResult` bez sprawdzenia elementu requestCode spowoduje wystąpienie nietypowego zachowania.

## <a name="telemetry"></a>Telemetria

Zestaw SDK aplikacji usługi Intune dla systemu Android nie kontroluje zbierania danych z aplikacji. Aplikacja Portal firmy domyślnie rejestruje dane telemetryczne. Te dane są wysyłane do usługi Microsoft Intune. Zgodnie z zasadami firmy Microsoft nie zbieramy żadnych danych osobowych.

> [!NOTE]
> Jeśli użytkownicy końcowi chcą zrezygnować z wysyłania tych danych, muszą wyłączyć telemetrię w ustawieniach aplikacji portalu firmy. Aby dowiedzieć się więcej, zobacz artykuł [Wyłączanie zbierania danych użycia przez firmę Microsoft](https://docs.microsoft.com/en-us/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="recommended-android-best-practices"></a>Zalecane najlepsze rozwiązania dotyczące systemu Android

* Wszystkie projekty biblioteki powinny współużytkować ten sam element android:package tam, gdzie to możliwe. Nie spowoduje to sporadycznego występowania tego problemu podczas uruchamiania aplikacji, ponieważ występuje on tylko podczas kompilacji. Nowsze wersje zestawu SDK aplikacji usługi Intune częściowo usuwają nadmiarowość.

* Korzystaj z najnowszych narzędzi do kompilacji dostępnych w zestawie SDK dla systemu Android.

* Usuń wszystkie nieużywane i niepotrzebne biblioteki (np. android.support.v4).
