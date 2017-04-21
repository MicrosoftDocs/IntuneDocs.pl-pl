---
title: "Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android | Microsoft Docs"
description: "Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu Android można wdrożyć funkcje zarządzania aplikacjami mobilnymi (MAM, Mobile App Management) usługi Intune w swojej aplikacji systemu Android."
keywords: Zestaw SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 17fa23f1d04e22a2cb10452fe3a9425f7482a6de
ms.lasthandoff: 04/14/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android

> [!NOTE]
> Warto najpierw przeczytać artykuł [Omówienie zestawu SDK aplikacji usługi Intune](intune-app-sdk.md), w którym opisano aktualne funkcje zestawu SDK oraz sposób przygotowania się do integracji na każdej z obsługiwanych platform.

Dzięki zestawowi SDK aplikacji usługi Microsoft Intune dla systemu Android można wdrożyć funkcje zarządzania aplikacjami mobilnymi (MAM, Mobile App Management) usługi Intune w swojej aplikacji systemu Android. Aplikacja obsługująca zarządzanie aplikacjami mobilnymi to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Umożliwia ona administratorom IT wdrażanie zasad w aplikacji mobilnej, gdy usługa Intune aktywnie zarządza aplikacją.

## <a name="whats-in-the-sdk"></a>Zawartość zestawu SDK

Zestaw SDK aplikacji usługi Intune dla systemu Android to standardowa biblioteka systemu Android bez zewnętrznych zależności. Zestaw SDK zawiera:  

* **Microsoft.Intune.MAM.SDK.jar**: Interfejsy niezbędne do obsługi funkcji MAM i współdziałania z aplikacją Portal firmy usługi Intune. Aplikacje muszą określić go jako odwołanie do biblioteki systemu Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: interfejsy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 4. Aplikacje wymagające tej obsługi muszą odwoływać się bezpośrednio do pliku JAR.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: interfejsy niezbędne do obsługi funkcji MAM w aplikacjach korzystających z biblioteki obsługi systemu Android w wersji 7. Aplikacje wymagające tej obsługi muszą odwoływać się bezpośrednio do pliku JAR.

* **Katalog zasobów**: zasoby (na przykład ciągi), z których korzysta zestaw SDK.

* **Microsoft.Intune.MAM.SDK.aar**: składniki zestawu SDK z wyjątkiem plików JAR Support.V4 i Support.V7. Tego pliku można użyć zamiast pojedynczych składników, jeśli system kompilacji obsługuje pliki AAR.

* **AndroidManifest.xml**: Dodatkowe punkty wejścia i wymagania dotyczące bibliotek.

* **THIRDPARTYNOTICES.TXT**: informacje o uznaniu autorstwa dotyczące kodu innych firm lub typu „open source”, który zostanie skompilowany w ramach aplikacji.

## <a name="requirements"></a>Wymagania

Zestaw SDK aplikacji usługi Intune to skompilowany projekt systemu Android. Dlatego jest w dużym stopniu niezależny od wersji interfejsu API systemu Android określonych przez aplikację jako minimalna i docelowa. Zestaw SDK obsługuje interfejsy API systemu Android w wersjach od 14 (system Android 4.0 i nowsze) do 24.

Zestaw SDK aplikacji usługi Intune dla systemu Android zależy od obecności aplikacji [Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) na urządzeniu na potrzeby obsługi zasad funkcji MAM. W przypadku obsługi funkcji MAM bez rejestracji urządzeń *nie* jest wymagane, aby użytkownik rejestrował urządzenie za pomocą aplikacji Portal firmy.


## <a name="how-the-intune-app-sdk-works"></a>Jak działa zestaw SDK aplikacji usługi Intune

###<a name="entry-points"></a>Punkty wejścia

Zestaw SDK aplikacji usługi Intune wymaga wprowadzenia zmian w kodzie źródłowym aplikacji w celu włączenia zasad zarządzania aplikacjami usługi Intune. Te zmiany wprowadza się przez przesłonięcie klas podstawowych systemu Android równoważnymi klasami podstawowymi usługi Intune, których nazwy zawierają prefiks `MAM`. Klasy zestawu SDK są ulokowanie między klasami podstawowymi systemu Android a pochodnymi wersjami klas należącymi do aplikacji. Przykładowo w przypadku działania końcowa hierarchia dziedziczenia wygląda następująco: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Na przykład, jeśli element `AppSpecificActivity` wchodzi w interakcję ze swoim elementem nadrzędnym (na przykład przez wywołanie `super.onCreate()`), to klasa `MAMActivity` stanowi superklasę.

Na ogół aplikacje dla systemu Android mają tryb pojedynczy i mogą uzyskać dostęp do systemu za pośrednictwem ich obiektu [Context](https://developer.android.com/reference/android/content/Context.html). Z drugiej strony aplikacje z wbudowanym zestawem SDK aplikacji usługi Intune mają dwa tryby. Te aplikacje nadal uzyskują dostęp do systemu za pośrednictwem obiektu `Context`. W zależności od używanego podstawowego elementu `Activity` obiekt `Context` zostanie udostępniony przez system Android lub w sposób inteligentny będzie multipleksować ograniczony widok systemu i obiekt `Context` dostarczony przez system Android.

Jeśli [punkt wejścia](https://developer.android.com/guide/components/fundamentals.html) systemu Android został przesłonięty przez równoważnik funkcji MAM, należy użyć wersji MAM cyklu życia punktu wejścia (z wyjątkiem klasy `MAMApplication`).

Na przykład przy tworzeniu klasy pochodnej klasy `MAMActivity` zamiast przesłaniać metodę `onCreate` i wywoływać metodę `super.onCreate` działanie `Activity` należy przesłonić metodę `onMAMCreate` i wywołać metodę `super.onMAMCreate`. Umożliwia to usłudze Intune m.in. ograniczenie uruchamiania działania `Activity` w niektórych przypadkach.


###<a name="sdk-permissions"></a>Uprawnienia zestawu SDK

Zestaw SDK aplikacji usługi Intune wymaga trzech [uprawnień systemu Android](https://developer.android.com/guide/topics/security/permissions.html) do aplikacji, które mają ten zestaw wbudowany:

* `android.permission.GET_ACCOUNTS` (żądane w czasie wykonywania, jeśli jest wymagane)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Te uprawnienia są wymagane przez bibliotekę Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) w celu wykonania uwierzytelniania obsługiwanego przez brokera. Jeśli te uprawnienia nie zostaną przyznane dla aplikacji lub zostaną odwołane przez użytkownika, przepływy uwierzytelniania, które wymagają brokera (aplikacja Portal firmy), zostaną wyłączone.


###<a name="company-portal-app"></a>Aplikacji Portal firmy

Dlaczego aplikacja Portal firmy jest wymagana? Jeśli aplikacja Portal firmy zostanie zainstalowana na urządzeniu i pobierze zasady ograniczeń aplikacji dla użytkownika z usługi Intune, punkty wejścia zestawu SDK będą inicjowane asynchronicznie. Inicjowanie jest wymagane tylko wtedy, gdy system Android wstępnie tworzy proces. Podczas inicjowania zostaje nawiązane połączenie z aplikacją Portal firmy, a następnie zasady są pobierane z aplikacji.  

> [!NOTE]
> Jeśli na urządzeniu nie ma zainstalowanej aplikacji Portal firmy, zachowanie aplikacji z obsługą usługi Intune nie ulegnie zmianie i będzie ona działać jak normalna aplikacja.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Integrowanie z zestawem SDK aplikacji usługi Intune

Jak ustalono wcześniej, zestaw SDK wymaga zmian kodu źródłowego aplikacji w celu włączenia zasad zarządzania aplikacjami. Poniżej przedstawiono kroki konieczne do włączenia funkcji MAM w aplikacji.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Zastąpienie klas, metod i działań ich równoważnikami funkcji MAM (wymagane)

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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder [wymagane tylko wtedy, jeżeli klasa Binder nie jest generowana z interfejsu AIDL (Android Interface Definition Language)] |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Supplubt.v4.jar**:

| Funkcja MAM usługi Intune dla klasy systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Supplubt.v7.jar**:

|Klasa systemu Android | Klasa zastępcza z zestawu SDK aplikacji usługi Intune |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Pamiętaj: jeśli [punkt wejścia](https://developer.android.com/guide/components/fundamentals.html) systemu Android został przesłonięty przez równoważnik funkcji MAM, należy użyć wersji MAM cyklu życia punktu wejścia (z wyjątkiem klasy `MAMApplication`).
>
>Na przykład przy tworzeniu klasy pochodnej klasy `MAMActivity` zamiast przesłaniać metodę `onCreate` i wywoływać metodę `super.onCreate` działanie `Activity` należy przesłonić metodę `onMAMCreate` i wywołać metodę `super.onMAMCreate`. Umożliwia to usłudze Intune m.in. ograniczenie uruchamiania działania `Activity` w niektórych przypadkach.

#### <a name="pendingintent-classes-and-renamed-methods"></a>Klasy PendingIntent i metody o zmienionej nazwie

Po utworzeniu klasy pochodnej z jednego z punktów wejścia funkcji MAM bezpiecznym rozwiązaniem jest użycie elementu `Context` w zwykły sposób, np. przez uruchomienie klas `Activity` i użycie elementu `PackageManager`.  

Klasy `PendingIntent` są wyjątkiem od tej reguły. W przypadku wywoływania takich klas należy zmienić nazwę klasy. Na przykład zamiast metody `PendingIntent.get*` należy użyć metody `MAMPendingIntent.get*`. Następnie można użyć otrzymanego elementu `PendingIntent` w zwykły sposób.

W niektórych przypadkach metoda dostępna w klasie systemu Android została oznaczona jako final w zastępczej klasie funkcji MAM. W takim przypadku klasa zastępcza funkcji MAM udostępnia metodę o podobnej nazwie (zazwyczaj z sufiksem `MAM`), która powinna zostać przesłonięta zamiast niej. Na przykład zamiast przesłaniać metodę `ContentProvider.query`należy przesłonić metodę `MAMContentProvider.queryMAM`. Kompilator języka Java powinien wymuszać ograniczenia specyfikacji final, aby zapobiec przypadkowemu przesłonięciu oryginalnej metody zamiast jej równoważnika funkcji MAM.

###<a name="enable-features-that-require-app-participation"></a>Włączanie funkcji wymagających udziału aplikacji

Zestaw SDK nie może samodzielnie implementować niektórych zasad. Aplikacja może kontrolować swoje zachowanie w celu uzyskania tych funkcji przy użyciu kilku interfejsów API, które znajdują się w interfejsie `AppPolicy` przedstawionym poniżej.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
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
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
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

### <a name="enable-it-control-over-app-saving-behavior"></a>Włączanie kontroli IT nad działaniem zapisywania aplikacji

Wiele aplikacji implementuje funkcje, które umożliwiają użytkownikom zapisywanie plików lokalnie lub w usłudze magazynu w chmurze. Zestaw SDK aplikacji usługi Intune pozwala administratorom IT chronić dane przed wyciekiem przez zastosowanie ograniczeń zasad w sposób odpowiadający potrzebom organizacji.  Jedne z zasad, które dział IT może kontrolować, dotyczą zapisywania plików przez użytkownika w „osobistym”, niezarządzanym magazynie danych. Obejmuje to zapisywanie w lokalizacji lokalnej, na karcie SD i w usługach kopii zapasowych innych firm.

Do włączenia tej funkcji wymagane jest współdziałanie ze strony aplikacji. Jeśli aplikacja umożliwia zapisywanie w lokalizacji osobistej lub w chmurze bezpośrednio z aplikacji, musisz zaimplementować tę funkcję, aby umożliwić administratorowi IT kontrolowanie, czy zapisywanie w lokalizacji jest dozwolone.   

Aby określić, czy zasady są wymuszane, aplikacja może wykonać następujące wywołanie. Wywołanie to informuje aplikację o tym, czy bieżące zasady administratora usługi Intune pozwalają na zapisywanie w magazynie osobistym. Aplikacja może wówczas wymusić zasady, ponieważ ma informacje o osobistym magazynie danych dostępnym dla użytkownika za pośrednictwem aplikacji.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> Wywołanie `MAMComponents.get(AppPolicy.class)` zawsze zwraca zasady aplikacji o wartości innej niż null, nawet jeśli urządzenie lub aplikacja nie podlega zasadom zarządzania usługi Intune.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Zezwolenie aplikacji na wykrywanie, czy zasady numeru PIN są wymagane

W przypadku niektórych ograniczeń aplikacji usługi Intune warto, aby aplikacja wyłączyła niektóre swoje funkcje, aby nie duplikowały funkcji zestawu SDK aplikacji usługi Intune. Jeśli na przykład aplikacja ma własny interfejs użytkownika do obsługi numeru PIN, możesz go wyłączyć w przypadku, gdy zestaw SDK jest skonfigurowany do żądania wprowadzenia numeru PIN przez użytkownika.

Aby określić, czy zasada usługi Intune dotyczące numeru PIN są skonfigurowane w taki sposób, aby wymagać numeru PIN aplikacji przy uruchomieniu, aplikacja może wykonać następujące wywołanie:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>Rejestrowanie w celu otrzymywania powiadomień z zestawu SDK  

Zestaw SDK aplikacji usługi Intune pozwala aplikacji na kontrolę zachowania niektórych zasad, takich jak selektywne czyszczenie, w momencie ich wdrażania przez administratora IT. Kiedy administrator IT wdraża taką zasadę, usługa Intune wysyła powiadomienie do zestawu SDK.

Aplikacja musi zarejestrować się, aby otrzymywać powiadomienia z zestawu SDK, tworząc klasę `MAMNotificationReceiver` i dokonując rejestracji za pomocą metody `MAMNotificationReceiverRegistry`. W tym celu należy określić odbiorcę i typ powiadomienia dla metody `App.onCreate`, jak pokazano w przykładzie:

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

Klasa `MAMNotificationReceiver` po prostu odbiera powiadomienia z usługi Intune. Zestaw SDK obsługuje niektóre powiadomienia bezpośrednio. Inne powiadomienia wymagają udziału aplikacji.

Aplikacja *musi* zwrócić wartość true lub false dla powiadomienia. Wartość true jest zwracana zawsze, chyba że niektóre akcje, które aplikacja próbowała wykonać w wyniku powiadomienia, zakończyły się niepowodzeniem. To niepowodzenie może zostać zgłoszone do usługi Intune. Raport może zostać utworzony na przykład w sytuacji, gdy czyszczenie danych użytkownika przez aplikację zakończy się niepowodzeniem po zainicjowaniu przez administratora IT.

Blokowanie w metodzie `MAMNotificationReceiver.onReceive` jest bezpieczne, ponieważ jej wywołanie zwrotne nie jest uruchamiane w wątku interfejsu użytkownika.

Następujący interfejs klasy `MAMNotificationReceiver` jest definiowany w zestawie SDK:

```
/**
 * The SDK is signaling that a WG event has occurred.
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

###<a name="types-of-notifications"></a>Typy powiadomień

Do aplikacji są wysyłane następujące powiadomienia. Niektóre z nich mogą wymagać udziału aplikacji.

* **`WIPE_USER_DATA`**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po odebraniu tego powiadomienia aplikacja powinna usunąć wszystkie dane skojarzone z tożsamością „firmową” przekazaną za pomocą klasy `MAMUserNotification`. To powiadomienie jest aktualnie wysyłane podczas wyrejestrowywania z usługi Intune. Nazwa podstawowa użytkownika jest zazwyczaj określana podczas procesu rejestracji. Jeśli zarejestrujesz odbieranie tego powiadomienia, Twoja aplikacja musi zapewnić, że wszystkie dane użytkownika zostaną usunięte. Jeżeli nie zarejestrujesz jego odbierania, aplikacja wykona domyślne działanie czyszczenia selektywnego.

* **`WIPE_USER_AUXILIARY_DATA`**: aplikacje mogą zarejestrować się w celu otrzymywania tego powiadomienia, jeśli zestaw SDK aplikacji usługi Intune ma wykonywać domyślne czyszczenie selektywne, ale aplikacja ma usuwać niektóre dane pomocnicze w ramach czyszczenia.  

* **`REFRESH_POLICY`**: to powiadomienie jest wysyłane w klasie `MAMUserNotification`. Po otrzymaniu tego powiadomienia wszystkie zasady usługi Intune znajdujące się w pamięci podręcznej muszą zostać unieważnione i zaktualizowane. Zestaw SDK zazwyczaj obsługuje to zadanie. Aplikacja natomiast powinna obsługiwać to zadanie, jeśli zasady są używane w dowolny trwały sposób.



### <a name="protection-of-backup-data"></a>Ochrona danych kopii zapasowej

Począwszy od systemu Android Marshmallow (interfejs API w wersji 23), na potrzeby aplikacji są dostępne dwa sposoby tworzenia kopii zapasowych danych. Każda opcja jest dostępna dla aplikacji i wymaga różnych kroków w celu zapewnienia, że ochrona danych usługi Intune jest implementowana prawidłowo. Aby uzyskać więcej informacji na temat metod wykonywania kopii zapasowych, zobacz [Przewodnik po interfejsie API systemu Android](http://developer.android.com/guide/topics/data/backup.html).

#### <a name="automatic-backup-for-apps"></a>Automatyczne wykonywanie kopii zapasowej dla aplikacji

System Android zaczął oferować funkcję [pełnego i automatycznego tworzenia kopii zapasowej](https://developer.android.com/guide/topics/data/autobackup.html) dla aplikacji na urządzeniach z systemem Android Marshmallow, niezależnie od docelowego interfejsu API aplikacji. Jeśli w pliku AndroidManifest.xml dla elementu `android:allowBackup` została jawnie ustawiona wartość false, to aplikacja nigdy nie zostanie umieszczona w kolejce do wykonywania kopii zapasowej przez system Android i dane „firmowe” pozostaną w aplikacji. W takim przypadku nie są wymagane żadne dalsze działania.

Domyślnie atrybut `android:allowBackup` ma wartość true, nawet jeśli atrybut `android:allowBackup` nie został określony w pliku manifestu. Oznacza to, że kopia zapasowa wszystkich danych aplikacji jest automatycznie tworzona na koncie usługi Dysk Google użytkownika. Jest to zachowanie domyślne, które stanowi *ryzyko przecieku danych*. Zestaw SDK wymaga wprowadzenia następujących zmian w celu zapewnienia ochrony danych. Zastosowanie się do tych wskazówek jest ważne, aby właściwie chronić dane klienta, jeśli aplikacja ma działać na urządzeniach z systemem Android Marshmallow.  

W przypadku niezapisania agenta kopii zapasowej w celu tworzenia kopii zapasowej aplikacji przy użyciu metody `MAMBackupAgent` lub metody `MAMBackupAgentHelper` należy zastanowić się, jak funkcja automatycznego wykonywania kopii zapasowej ma przekazywać dane aplikacji oraz je kontrolować. Usługa Intune pozwala używać wszystkich [funkcji automatycznego wykonywania kopii zapasowej](https://developer.android.com/guide/topics/data/autobackup.html) dostępnych w systemie Android, m.in. definiowania reguł niestandardowych w formacie XML. Należy jednak wykonać następujące kroki, aby zabezpieczyć dane:

1. Użyj domyślnego agenta `MAMBackupAgent`, aby zezwolić na pełne, automatyczne kopie zapasowe zgodne z zasadami usługi Intune. Umieść ciąg `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` w manifeście aplikacji.

2. Gdy zdecydujesz, który typ pełnej kopii zapasowej powinna otrzymać Twoja aplikacja (niefiltrowany, filtrowany lub żaden), ustaw dla atrybutu `android:fullBackupContent` wartość true, false lub zasób XML w aplikacji. Wartość ustawioną dla atrybutu `android:fullBackupContent` skopiuj do tagu metadanych o nazwie `com.microsoft.intune.mam.FullBackupContent`.

    Na przykład jeśli chcesz, aby pełna kopia zapasowa aplikacji była tworzona zgodnie z niestandardowymi regułami umieszczonymi w pliku XML, podaj zasób dla tagu metadanych `com.microsoft.intune.mam.FullBackupContent` w manifeście w następujący sposób:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Kopie zapasowe typu klucz/wartość

Opcja kopii zapasowych typu klucz/wartość jest dostępna dla wszystkich interfejsów API i używa klas `BackupAgentHelper` oraz `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

Klasa `BackupAgentHelper` jest znacznie prostsza do zaimplementowania niż klasa `BackupAgent`, zarówno w zakresie natywnych funkcji systemu Android, jak i integracji z funkcją MAM. Klasa `BackupAgentHelper` umożliwia rejestrowanie całych plików i udostępnionych preferencji odpowiednio w klasie `FileBackupHelper` lub `SharedPreferencesBackupHelper`. Po utworzeniu są one następnie dodawane do klasy `BackupAgentHelper`.

##### <a name="backupagent"></a>BackupAgent

Klasa `BackupAgent` umożliwia o wiele dokładniejsze określenie danych, których kopie zapasowe mają być tworzone. Wybór tej opcji oznacza jednak, że nie będzie możliwe korzystanie z platformy kopii zapasowych systemu Android. Ponieważ odpowiedzialność za implementację leży po Twojej stronie, zapewnienie odpowiedniej ochrony danych przez funkcję MAM wymaga wykonania większej liczby kroków. Jako deweloper musisz wykonać większość pracy, dlatego integracja funkcji MAM wymaga nieco więcej wysiłku.

###### <a name="app-does-not-have-a-backup-agent"></a>Aplikacja nie ma agenta kopii zapasowej

W przypadku ustawienia `android:allowBackup =true` opcje dewelopera są następujące.

####### <a name="full-backup-according-to-a-configuration-file"></a>Pełna kopia zapasowa zgodnie z plikiem konfiguracji

Podaj zasób w tagu metadanych `com.microsoft.intune.mam.FullBackupContent` w manifeście. Na przykład:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Dodaj następujący atrybut w tagu `<application>` : `android:fullBackupContent="@xml/my_scheme"`, gdzie `my_scheme` jest zasobem XML w aplikacji.

####### <a name="full-backup-without-exclusions"></a>Pełna kopia zapasowa bez wykluczeń

Podaj tag w manifeście, taki jak `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Dodaj następujący atrybut w tagu `<application>`: `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>Aplikacja ma agenta kopii zapasowej

Postępuj zgodnie z zaleceniami dotyczącymi klas `BackupAgent` i `BackupAgentHelper` przedstawionymi we wcześniejszej części tego przewodnika.

Rozważ przejście na klasę `MAMDefaultFullBackupAgent`, która umożliwia łatwe tworzenie kopii zapasowych w systemie Android Marshmallow.

##### <a name="before-your-backup"></a>Przed wykonaniem kopii zapasowej

Przed rozpoczęciem tworzenia kopii zapasowej należy sprawdzić, czy jest to dozwolone dla plików lub buforów danych, których kopia zapasowa ma zostać utworzona. Firma Microsoft oferuje funkcję `isBackupAllowed` w klasach `MAMFileProtectionManager` oraz `MAMDataProtectionManager` umożliwiającą takie sprawdzenie. Jeśli utworzenie kopii zapasowej pliku lub buforu danych jest niedozwolone, nie należy próbować uwzględniać ich w kopii zapasowej.

Jeśli w pewnym momencie podczas tworzenia kopii zapasowej trzeba utworzyć kopię zapasową tożsamości dla plików sprawdzonych w kroku 1, należy użyć wywołania `backupMAMFileIdentity(BackupDataOutput data, File … files)`, podając pliki, z których dane mają zostać wyodrębnione. Spowoduje to automatyczne utworzenie nowych jednostek kopii zapasowej i zapisanie ich do elementu `BackupDataOutput` . Te jednostki zostaną automatycznie użyte podczas przywracania.

#### <a name="azure-directory-authentication-library-setup"></a>Konfigurowanie biblioteki uwierzytelniania usługi Azure Directory  

Zestaw SDK używa biblioteki ADAL na potrzeby scenariuszy uwierzytelniania i uruchamiania warunkowego. Scenariusze te wymagają, aby aplikacje zawierały pewną część konfiguracji usługi Azure Active Directory (Azure AD). Wartości konfiguracji są przekazywane do zestawu SDK przez metadane w pliku `AndroidManifest` .

Aby skonfigurować aplikację i włączyć odpowiednie uwierzytelnianie, dodaj następujący element do węzła aplikacji w pliku `AndroidManifest`. Niektóre z tych konfiguracji są wymagane tylko wtedy, gdy aplikacja generalnie korzysta z biblioteki ADAL podczas uwierzytelniania. W takim przypadku potrzebne będą określone wartości, które zostały użyte przez aplikację do wykonania rejestracji w usłudze Azure AD. Ma to na celu zapewnienie, że użytkownik nie będzie dwukrotnie monitowany w procesie uwierzytelnienia z powodu rozpoznania przez usługę AAD dwóch odrębnych wartości rejestracji: jednej z aplikacji i jednej z zestawu SDK.

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

##### <a name="common-adal-configurations"></a>Typowe konfiguracje biblioteki ADAL

Poniżej przedstawiono typowe konfiguracje dla wcześniej przedstawionych wartości.

###### <a name="app-does-not-integrate-adal"></a>Aplikacja nie jest zintegrowana z biblioteką ADAL

* Urząd musi być ustawiony na wymagane środowisko, w którym skonfigurowano konta usługi Azure AD.

* Element SkipBroker musi być ustawiony na wartość true.

###### <a name="app-integrates-adal"></a>Aplikacja jest zintegrowana z biblioteką ADAL

* Urząd musi być ustawiony na wymagane środowisko, w którym skonfigurowano konta usługi Azure AD.

* Identyfikator klienta musi być ustawiony na identyfikator klienta aplikacji.

* `NonBrokerRedirectURI` powinien być ustawiony na prawidłowy identyfikator URI przekierowania dla aplikacji. Alternatywnie element `urn:ietf:wg:oauth:2.0:oob` musi być skonfigurowany jako prawidłowy identyfikator URI przekierowania usługi Azure AD.

* Element SkipBroker musi być ustawiony na wartość false (lub nieobecny).

* Usługa Azure AD musi być skonfigurowana pod kątem akceptowania identyfikatora URI przekierowania brokera.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>Aplikacja jest zintegrowana z biblioteką ADAL, lecz nie obsługuje aplikacji Authenticator usługi Azure AD

* Urząd musi być ustawiony na wymagane środowisko, w którym skonfigurowano konta usługi Azure AD.

* Identyfikator klienta musi być ustawiony na identyfikator klienta aplikacji.

* `NonBrokerRedirectURI` musi być ustawiony na prawidłowy identyfikator URI przekierowania dla aplikacji. Alternatywnie element `urn:ietf:wg:oauth:2.0:oob` powinien być skonfigurowany jako prawidłowy identyfikator URI przekierowania usługi Azure AD.

#### <a name="logging-in-the-sdk"></a>Rejestrowanie w zestawie SDK

Rejestrowanie odbywa się za pośrednictwem platformy `java.util.logging` . Aby odbierać dzienniki, skonfiguruj globalne rejestrowanie zgodnie z opisem w [podręczniku technicznym języka Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). W zależności od aplikacji metoda `App.onCreate` jest zwykle najlepszym miejscem, aby zainicjować rejestrowanie. Należy zwrócić uwagę na to, że komunikaty dziennika są dostosowane przy użyciu nazwy klasy, która może być ukryta.

###<a name="multi-identity"></a>Wiele tożsamości

Domyślnie zestaw SDK aplikacji usługi Intune stosuje zasady do aplikacji jako całości. Wiele tożsamości to funkcja zarządzania aplikacjami mobilnymi, którą możesz włączyć, aby stosować zasady na poziomie poszczególnych tożsamości. Wymaga to znacznie pełniejszego uczestnictwa aplikacji niż inne funkcje zarządzania aplikacjami mobilnymi. Aplikacja musi poinformować zestaw SDK aplikacji, gdy zamierza zmienić aktywną tożsamość. Zestaw SDK musi również powiadomić aplikację, gdy zmiana tożsamości jest wymagana.

Aktualnie obsługiwana jest tylko jedna tożsamość zarządzana. Po zarejestrowaniu urządzenia lub aplikacji przez użytkownika zestaw SDK używa tej tożsamości i uznaje ją za podstawową tożsamość zarządzaną. Inni użytkownicy w aplikacji są traktowani jako niezarządzani z nieograniczonymi ustawieniami zasad.

Należy zauważyć, że tożsamość jest definiowana po prostu jako ciąg. W tożsamościach nie jest rozróżniana wielkość liter. Żądania tożsamości wysyłane do zestawu SDK mogą nie zwracać jej z tą samą wielkością liter, której pierwotnie użyto podczas ustawiania tożsamości.

####<a name="enabling-multi-identity"></a>Włączanie wielu tożsamości

Domyślnie wszystkie aplikacje są traktowane jako aplikacje z obsługą jednej tożsamości. Aby zadeklarować, że aplikacja obsługuje wiele tożsamości, należy umieścić następujące metadane w manifeście systemu Android.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Ustawianie tożsamości

Tożsamość aplikacji można ustawić na następujących poziomach:

1. Poziom procesu

2. Poziom kontekstu (zwykle działania `Activity`)

3. Poziom wątku

Tożsamość ustawiona na poziomie wątku zastępuje tożsamość ustawioną na poziomie `Context`, która zastępuje tożsamość ustawioną na poziomie procesu. Tożsamość ustawiona na poziomie `Context` jest używana tylko w odpowiednich przypadkach. Na przykład zadania we/wy plików nie mają skojarzonego elementu `Context`. Do ustawiania tożsamości i pobierania wartości tożsamości ustawionych wcześniej służą następujące metody w klasie `MAMPolicyManager`.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Tożsamość aplikacji można także wyczyścić, ustawiając dla niej wartość null. Pusty ciąg może być używany jako tożsamość, która nigdy nie będzie miała ograniczeń. Wszystkie metody służące do ustawiania tożsamości raportują wynikowe wartości zwrotne za pośrednictwem klasy ``` MAMIdentitySwitchResult```. Mogą zostać zwrócone cztery wartości:

* **SUCCEEDED**: zmiana tożsamości zakończyła się pomyślnie.

* **NOT_ALLOWED**: zmiana tożsamości jest niedozwolona. Sytuacja taka będzie miała miejsce, jeśli zostanie podjęta próba przełączenia się na innego użytkownika firmowego należącego do tej samej firmy, co zarejestrowany użytkownik. Wystąpi ona również w przypadku podjęcia próby ustawienia tożsamości interfejsu użytkownika (`Context`), gdy dla bieżącego wątku jest już ustawiona inna tożsamość.

* **CANCELLED**: użytkownik anulował zmianę tożsamości, zwykle przez naciśnięcie przycisku Wstecz w monicie o podanie numeru PIN/uwierzytelnienie.

* **FAILED**: z nieokreślonego powodu nie można zmienić tożsamości.

W przypadku ustawienia tożsamości na poziomie `Context` wynik jest raportowany asynchronicznie. Jeśli element `Context` jest klasą `Activity`, dopiero po uruchomieniu warunkowym będzie wiadomo, czy zmiana tożsamości zakończyła się pomyślnie. Uruchomienie warunkowe może wymagać wprowadzenia przez użytkownika numeru PIN lub pełnych poświadczeń firmowych. Oczekuje się, że aplikacja zaimplementuje klasę ```MAMSetUIIdentityCallback```, aby uzyskać ten wynik, chociaż dozwolone jest podanie wartości null dla tego parametru.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

Można również ustawić tożsamość działania bezpośrednio przy użyciu metody w klasie `MAMActivity`, zamiast wykonywać wywołanie ```MAMPolicyManager.setUIPolicyIdentity```. Można to zrobić za pomocą następującej metody:

 ```public final void switchMAMIdentity(final String newIdentity);```

Aplikacje mogą również zastępować metodę w klasie `MAMActivity`, aby otrzymywać powiadomienia o wynikach prób zmiany tożsamości tego działania.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Przełączenie tożsamości może wymagać ponownego utworzenia danego działania. W takim przypadku wywołanie zwrotne metody ```onSwitchMAMIdentityComplete``` zostanie dostarczone do nowego wystąpienia tego działania.


####<a name="implicit-identity-changes"></a>Niejawne zmiany tożsamości

Oprócz możliwości ustawiania tożsamości przez aplikację tożsamość wątku lub kontekstu może zostać zmieniona na podstawie transferu danych przychodzących z innej aplikacji z włączoną funkcją MAM. Jeśli na przykład działanie zostanie uruchomione z klasy `Intent` wysłanej przez inną aplikację z funkcją MAM, tożsamość tego działania zostanie ustawiona na podstawie obowiązującej tożsamości w tej innej aplikacji w chwili wysłania klasy `Intent`.

W przypadku usług tożsamość wątku zostanie ustawiona w podobny sposób na czas trwania wywołania metody `onStart` lub `onBind`. Wywołania do klasy `Binder` zwrócone z metody `onBind` także powoduje tymczasowe ustawienie tożsamości wątku. Wywołania do klasy ```ContentProvider``` podobnie ustawią tożsamość wątku na czas ich trwania.

Ponadto interakcja użytkownika z działaniem może spowodować niejawne przełączenie tożsamości. Jeśli na przykład użytkownik naciśnie przycisk anulowania w monicie o uwierzytelnienie podczas operacji ```Resume```, spowoduje to niejawne przełączenie do pustej tożsamości.
Aplikacja ma możliwość otrzymania powiadomienia o tych zmianach i w niektórych przypadkach może ich zabronić, jeśli jest to konieczne. Klasy ```MAMService``` i ```MAMContentProvider``` prezentują następującą metodę, którą może być zastąpiona przez podklasy:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
W przypadku klasy ```MAMActivity``` dodatkowy parametr znajduje się w metodzie:
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
Część elementu ```AppIdentitySwitchReason``` przechwytuje źródło przełączania niejawnego. Akceptowane wartości to ```CREATE```, ```RESUME_CANCELLED``` i ```NEW_INTENT```.  Przyczyna ```RESUME_CANCELLED``` jest używana w przypadku, gdy wznowienie działania powoduje wyświetlenie monitu o podanie numeru PIN lub uwierzytelnienie bądź innego interfejsu użytkownika dotyczącego zgodności, który użytkownik próbuje anulować, na ogół korzystając z przycisku Wstecz.
Metoda ```AppIdentitySwitchResultCallback``` wygląda następująco:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
Parametr ```AppIdentitySwitchResult``` ma wartość ```SUCCESS``` lub ```FAILURE```.

Metoda ```onMAMIdentitySwitchRequired``` jest wywoływana dla wszystkich niejawnych zmian tożsamości z wyjątkiem tych wykonywanych za pośrednictwem klasy `Binder` zwróconych z klasy ```MAMService.onMAMBind```. Domyślna implementacja klasy ```onMAMIdentitySwitchRequired``` natychmiast wywołuje parametr ```reportIdentitySwitchResult(FAILURE)```, gdy przyczyna ma wartość ```RESUME_CANCELLED```, oraz parametr ```reportIdentitySwitchResult(SUCCESS)``` we wszystkich innych przypadkach.

Większość aplikacji prawdopodobnie nie musi blokować ani opóźniać przełączania tożsamości w inny sposób. Jeśli jednak jest to wymagane przez aplikację, należy wziąć pod uwagę następujące kwestie:

* Jeśli przełączanie tożsamości jest zablokowane, skutek jest taki sam, jak w przypadku uniemożliwienia transferu danych przychodzących przez ustawienia udostępniania ```Receive```.

* Jeśli usługa jest uruchomiona w wątku głównym, klasa ```reportIdentitySwitchResult``` *musi* być wywoływana synchronicznie, w przeciwnym razie wątek interfejsu użytkownika ulegnie zawieszeniu.

* W przypadku tworzenia elementu ```Activity``` klasa ```onMAMIdentitySwitchRequired``` zostanie wywołana przed metodą ```onMAMCreate```. Jeśli aplikacja musi wyświetlić interfejs użytkownika w celu ustalenia, czy zezwolić na przełączenie tożsamości, ten interfejs użytkownika musi zostać pokazany przy użyciu innego działania.

* W przypadku działania ```Activity```, dla którego żądanie przełączenia do pustej tożsamości ma przyczynę o wartości ```RESUME_CANCELLED```, aplikacja musi zmodyfikować wznowione działanie tak, aby wyświetlane dane były spójne z tym przełączeniem tożsamości. Jeśli nie jest to możliwe, aplikacja powinna odmówić przełączenia. Użytkownik zostanie ponownie poproszony o zachowanie zgodności z zasadami dla wznawianej tożsamości (np. przez wyświetlenie ekranu wprowadzania numeru PIN).

> [!NOTE]
> Aplikacja z obsługą wielu tożsamości zawsze będzie otrzymywać dane przychodzące z aplikacji zarządzanych i niezarządzanych. Aplikacja odpowiada za zarządzanie danymi z zarządzanych tożsamości. Jeśli żądana tożsamość jest zarządzana ```(MAMPolicyManager.getIsIdentityManaged)```, ale aplikacja nie może użyć danego konta (na przykład z powodu konieczności wcześniejszego skonfigurowania kont, takich jak konta e-mail, w aplikacji), należy odmówić przełączenia tożsamości.

###<a name="file-protection"></a>Ochrona plików

Każdy plik ma tożsamość skojarzoną z nim w momencie utworzenia na podstawie tożsamości procesu i wątku. Ta tożsamość jest używana zarówno do szyfrowania, jak i selektywnego czyszczenia. Szyfrowane będą tylko pliki, których tożsamość ma zasady wymagające szyfrowania. Domyślne selektywne czyszczenie danych zestawu SDK będzie obejmować tylko pliki skojarzone z tożsamością, dla której zażądano czyszczenia. Aplikacja może wysyłać zapytania dotyczące tożsamości pliku lub może zmieniać tę tożsamość przy użyciu metody ```MAMFileProtectionManager```.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
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
     * Get the protection info on a file.
     *
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> Na znakowanie tożsamości pliku ma wpływ tryb offline. Należy uwzględnić następujące kwestie:
> * Jeśli nie zainstalowano aplikacji Portal firmy, nie można tagować plików pod kątem tożsamości.
>
> * Jeśli aplikacja Portal firmy została zainstalowana, ale aplikacja nie ma zasad, tagowanie plików pod kątem tożsamości nie będzie wiarygodne.
>
> * Po udostępnieniu tagowania plików pod kątem tożsamości wszystkie wcześniej utworzone pliki będą traktowane jako osobiste (należące do tożsamości o pustym ciągu), chyba że aplikacja została wcześniej zainstalowana jako aplikacja zarządzana z obsługą jednej tożsamości. W takim przypadku będą one traktowane jako należące do zarejestrowanego użytkownika.

####<a name="data-protection"></a>Ochrona danych

Nie jest możliwe tagowanie pliku jako należącego do wielu tożsamości. Aplikacje, które muszą przechowywać dane należące do różnych użytkowników w tym samym pliku, mogą robić to ręcznie przy użyciu funkcji oferowanych przez klasę ```MAMDataProtectionManager```. Umożliwia to aplikacji szyfrowanie danych i powiązanie ich z określonym użytkownikiem. Zaszyfrowane dane można przechowywać na dysku w pliku. Można tworzyć zapytania dotyczące danych skojarzonych z tożsamością. Dane te można później odszyfrować.

```
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
###<a name="content-providers"></a>Dostawcy zawartości

Jeśli aplikacja dostarcza potencjalnie firmowe dane inne niż element ```ParcelFileDescriptor``` za pośrednictwem elementu ```ContentProvider```, aplikacja musi wywoływać metodę ```isProvideContentAllowed(String)``` klasy ```MAMContentProvider```, przekazując element ```UPN``` właściciela jako zawartość. Jeśli ta funkcja zwróci wartość false, zawartość nie może zostać zwrócona do elementu wywołującego. Deskryptory plików zwrócone za pośrednictwem dostawcy zawartości są obsługiwane automatycznie na podstawie tożsamości plików.

###<a name="selective-wipe"></a>Selektywne czyszczenie danych

Jeśli dla aplikacji zarejestrowano powiadomienia ```WIPE_USER_DATA```, nie będzie ona otrzymywać korzyści wynikających z zachowania domyślnego selektywnego czyszczenia danych zestawu SDK. W przypadku aplikacji z obsługą wielu tożsamości może to być bardziej znaczące, ponieważ domyślne selektywne czyszczenie danych funkcji MAM będzie obejmować tylko pliki zgodne z tożsamością, która ma zostać wyczyszczona.

W przypadku tworzenia aplikacji z obsługą wielu tożsamości można zarejestrować się w celu otrzymywania powiadomienia ```WIPE_USER_AUXILIARY_DATA```. To powiadomienie pozwala korzystać z zalet domyślnego czyszczenia danych zestawu SDK. Powiadomienie będzie wysyłane bezpośrednio przed wykonaniem domyślnego selektywnego czyszczenia danych zestawu SDK. Należy pamiętać, że aplikacja w żadnym wypadku nie może być zarejestrowana do otrzymywania jednocześnie powiadomień ```WIPE_USER_DATA``` i ```WIPE_USER_AUXILIARY_DATA```.

### <a name="known-platform-limitations"></a>Znane ograniczenia dotyczące platformy

#### <a name="file-size-limitations"></a>Ograniczenia rozmiaru plików

W systemie Android ograniczenia formatu pliku wykonywalnego platformy Dalvik mogą stać się problemem w przypadku uruchamiania dużych baz kodu bez narzędzia ProGuard. W szczególności mogą wystąpić następujące ograniczenia:

* Limit 65 000 dotyczący pól

* Limit 65 000 dotyczący metod

W przypadku dołączania wielu projektów każdy element `android:package` otrzyma kopię elementu R, co drastycznie zwiększy liczbę pól w miarę dodawania bibliotek. Poniższe zalecenia mogą pomóc w złagodzeniu skutków tego ograniczenia:

* Wszystkie projekty bibliotek powinny współużytkować ten sam element `android:package`, jeśli jest to możliwe. Nie spowoduje to sporadycznego występowania problemu w polach, ponieważ występuje on tylko podczas kompilacji. Ponadto nowsze wersje zestawu SDK systemu Android będą wstępnie przetwarzać pliki DEX w celu usunięcia części nadmiarowości. Zmniejsza to jeszcze bardziej odległość od pól.

* Użyj najnowszych dostępnych narzędzi do kompilacji z zestawu SDK systemu Android.

* Usuń wszystkie nieużywane i niepotrzebne biblioteki (np. `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Ograniczenia wymuszania zasad

**Przechwytywanie ekranu**: zestaw SDK nie może wymusić nowej wartości ustawienia przechwytywania ekranu w klasach `Activity` przetworzonych już przez metodę `Activity.onCreate`. Może to spowodować, że wystąpi okres, w którym dla aplikacji będzie wyłączone tworzenie zrzutów ekranu, ale wciąż będzie to możliwe.

**Rozpoznawanie zawartości**: zasady transferu lub odbierania mogą zablokować lub częściowo zablokować użycie funkcji rozpoznawania zawartości na potrzeby dostępu do dostawcy zawartości w innej aplikacji. Spowoduje to zwracanie przez metody `ContentResolver` wartości null lub zgłaszanie wartości błędu. (Na przykład w przypadku zablokowania metoda `openOutputStream` zgłosi wyjątek `FileNotFoundException`). Aplikacja może wykonać to wywołanie, aby sprawdzić, czy zasady spowodowały (lub mogą spowodować) błąd zapisu danych przez funkcję rozpoznawania zawartości:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Wyeksportowane usługi**: plik `AndroidManifest.xml` dostępny w zestawie SDK aplikacji usługi Intune zawiera element `MAMNotificationReceiverService`. Musi to być wyeksportowana usługa umożliwiająca aplikacji Portal firmy wysyłanie powiadomień do usprawnionej aplikacji. Usługa sprawdza obiekt wywołujący, aby zapewnić, że tylko aplikacja Portal firmy ma zezwolenie na wysyłanie powiadomień.

### <a name="android-best-practices"></a>Najlepsze rozwiązania dotyczące systemu Android

Zestaw SDK usługi Intune obsługuje kontrakt udostępniony przez interfejs API systemu Android, chociaż w wyniku wymuszania zasad warunki błędu mogą być wyzwalane częściej. Następujące najlepsze rozwiązania dla systemu Android zmniejszają prawdopodobieństwo wystąpienia błędu:

* W przypadku funkcji zestawu SDK systemu Android, które mogą zwracać wartość null, prawdopodobieństwo zwrócenia wartości null jest teraz większe. Aby zminimalizować problemy, upewnij się, że kontrole wartości null znajdują się w odpowiednich miejscach.

* Sprawdź funkcje możliwe do sprawdzenia przy użyciu interfejsów API zestawu SDK.

* Wszystkie funkcje pochodne muszą wykonywać wywołania za pośrednictwem swoich wersji superklas.

* Unikaj stosowania jakiegokolwiek interfejsu API w sposób niejednoznaczny. Na przykład użycie metody `Activity.startActivityForResult/onActivityResult` bez sprawdzenia elementu `requestCode` spowoduje wystąpienie nietypowego zachowania.

