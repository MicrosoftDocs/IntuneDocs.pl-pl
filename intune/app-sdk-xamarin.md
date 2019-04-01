---
title: Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune
description: Powiązania Xamarin zestawu SDK aplikacji usługi Intune umożliwiają korzystanie z zasad ochrony aplikacji usługi Intune w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/16/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd162f6af256c104c04374290a695141cdcc26f6
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566203"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

## <a name="overview"></a>Przegląd
[Powiązania Xamarin zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umożliwiają korzystanie z [zasad ochrony aplikacji usługi Intune](app-protection-policy.md) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin. Powiązania te umożliwiają deweloperom łatwe dołączanie funkcji ochrony aplikacji Intune do ich aplikacji opartych na środowisku Xamarin.

Powiązania Xamarin zestawu Microsoft Intune App SDK pozwalają wdrażać zasady ochrony aplikacji usługi Intune (nazywane również zasadami APP lub MAM) we własnych aplikacjach utworzonych w środowisku Xamarin. Aplikacja obsługująca zarządzanie aplikacjami mobilnymi to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy IT mogą wdrażać zasady ochrony aplikacji w aplikacji mobilnej, gdy usługa Intune aktywnie zarządza aplikacją.

## <a name="whats-supported"></a>Co jest obsługiwane?

### <a name="developer-machines"></a>Maszyny deweloperów
* Windows (Visual Studio w wersji 15.7+)
* macOS

### <a name="mobile-app-platforms"></a>Platformy aplikacji mobilnych
* Android
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Scenariusze zarządzanie aplikacjami mobilnymi w usłudze Intune

* Zasady Intune APP-WE (bez rejestracji urządzeń)
* Urządzenia zarejestrowane przez funkcję zarządzania urządzeniami przenośnymi w usłudze Intune
* Urządzenia zarejestrowane przez rozwiązanie EMM innej firmy

Aplikacje Xamarin utworzone za pomocą powiązań Xamarin zestawu Intune App SDK mogą teraz odbierać zasady ochrony aplikacji usługi Intune zarówno na urządzeniach przenośnych zarejestrowanych w systemie zarządzania urządzeniami przenośnymi (MDM) usługi Intune, jak i na urządzeniach niezarejestrowanych.

## <a name="prerequisites"></a>Wymagania wstępne

Przejrzenie [postanowień licencyjnych](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Wydrukować i zachować kopię postanowień licencyjnych. Pobranie i rozpoczęcie używania powiązań Xamarin zestawu Intune App SDK oznacza akceptację tych postanowień licencyjnych. Jeśli użytkownik nie akceptuje niniejszych postanowień, nie może używać tego oprogramowania.

Zestaw SDK zależy od biblioteki [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) w zakresie scenariuszy [uwierzytelniania](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) i warunkowego uruchamiania, co wymaga skonfigurowania aplikacji przy użyciu usługi [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Jeśli aplikacja jest już skonfigurowana do używania biblioteki ADAL lub MSAL i ma własny niestandardowy identyfikator klienta używany do uwierzytelniania za pomocą usługi Azure Active Directory, upewnij się, że zostaną wykonane kroki, aby udzielić aplikacji platformy Xamarin uprawnień do usługi zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune. Postępuj zgodnie z instrukcjami w sekcji „[Udzielanie aplikacji dostępu do usługi ochrony aplikacji w usłudze Intune](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)” [przewodnika zawierającego wprowadzenie do zestawu Intune SDK](app-sdk-get-started.md).

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Włączenie zasad ochrony aplikacji usługi Intune w aplikacji mobilnej dla systemu iOS
1. Dodaj [pakiet NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) do projektu Xamarin.iOS.
2.  Wykonaj ogólne kroki wymagane w celu integracji zestawu SDK aplikacji usługi Intune z aplikacją mobilną systemu iOS. Można rozpocząć od kroku 3 instrukcji dotyczących integracji znajdujących się w [przewodniku dewelopera dotyczącym zestawu SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Możesz pominąć ostatni krok w tej sekcji dotyczący uruchamiania narzędzia IntuneMAMConfigurator, ponieważ to narzędzie jest zawarte w pakiecie Microsoft.Intune.MAM.Xamarin.iOS i zostanie uruchomione automatycznie podczas kompilacji.
    **Ważne**: procedura włączania udostępniania pęku kluczy dla aplikacji w programie Visual Studio różni się nieco od analogicznej procedury dla środowiska Xcode. Otwórz plik Entitlements.plist aplikacji i upewnij się, że opcja „Włącz pęk kluczy” jest włączona i że dodano w tej sekcji odpowiednie grupy udostępniania pęku kluczy. Następnie upewnij się, że plik Entitlements.plist został podany w polu „Niestandardowe uprawnienia” opcji „Podpisywanie zbiorów systemu iOS” projektu dla wszystkich odpowiednich kombinacji konfiguracji i platformy.
3.  Po dodaniu powiązań i odpowiednim skonfigurowaniu aplikacja może zacząć używać interfejsów API zestawu SDK usługi Intune. W tym celu należy uwzględnić następujące przestrzenie nazw:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Aby zacząć odbierać zasady ochrony aplikacji, aplikacja musi zostać zarejestrowana do celów zarządzania aplikacjami mobilnymi usługi Intune. Jeśli aplikacja nie korzysta z biblioteki [Active Directory Authentication Library platformy Azure](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) lub biblioteki [Microsoft Authentication Library](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) do uwierzytelniania użytkowników, a chcesz użyć zestawu SDK usługi Intune do obsługi uwierzytelniania, aplikacja powinna podać główną nazwę użytkownika do metody LoginAndEnrollAccount obiektu IntuneMAMEnrollmentManager:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Aplikacje mogą podać wartość null, jeśli główna nazwa użytkownika nie jest znana w momencie wywołania. W takim przypadku użytkownicy otrzymają monit o podanie zarówno adresu e-mail, jak i hasła.
      
      Jeśli aplikacja już korzysta z biblioteki ADAL lub MSAL do uwierzytelniania użytkowników, można skonfigurować logowanie jednokrotne pomiędzy aplikacją a zestawem SDK usługi Intune. Najpierw należy skonfigurować bibliotekę ADAL/MSAL do przechowywania tokenów w grupie dostępu łańcucha kluczy używanej przez powiązania platformy Xamarin usługi Intune dla systemu iOS (com.microsoft.adalcache). W przypadku biblioteki ADAL można to zrobić, [ustawiając właściwość KeychainSecurityGroup obiektu AuthenticationContext](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#enable-token-cache-sharing-across-ios-applications). W przypadku biblioteki MSAL należy [skonfigurować właściwość KeychainSecurityGroup obiektu PublicClientApplication](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/msal-net-2-released#you-can-now-enable-sso-between-adal-and-msal-apps-on-xamarinios). Następnie należy zastąpić domyślne ustawienia usługi AAD używane w zestawie SDK usługi Intune ustawieniami Twojej aplikacji. Można to zrobić za pomocą słownika IntuneMAMSettings w pliku Info.plist aplikacji, zgodnie z informacjami w [przewodniku dewelopera dotyczącym zestawu SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk). Możesz również użyć właściwości zastąpienia AAD wystąpienia IntuneMAMPolicyManager. Metoda z użyciem pliku Info.plist jest zalecana w przypadku aplikacji korzystających ze statycznych ustawień biblioteki ADAL, natomiast właściwości zastąpienia są rekomendowane dla aplikacji, które określają te wartości w środowisku uruchomieniowym. Gdy wszystkie ustawienia logowania jednokrotnego zostaną już skonfigurowane, aplikacja powinna przekazać nazwę główną użytkownika do metody RegisterAndEnrollAccount obiektu IntuneMAMEnrollmentManager po pomyślnym uwierzytelnieniu:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      Aplikacje mogą określić wynik próby rejestracji poprzez wdrożenie metody EnrollmentRequestWithStatus w podklasie IntuneMAMEnrollmentDelegate i ustawienie właściwości Delegate obiektu IntuneMAMEnrollmentManager na wystąpienie tej klasy. Zapoznaj się z naszą [przykładową aplikacją platformy Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios).

      Po pomyślnej rejestracji aplikacja może określić nazwę główną użytkownika zarejestrowanego konta (jeśli wcześniej była nieznana), wykonując zapytanie dotyczące następującej właściwości: 
      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
> [!NOTE] 
> Dla systemu iOS narzędzie remapper jest niedostępne. Integracja z aplikacją Xamarin.Forms powinna przebiegać tak samo, jak w przypadku normalnego projektu Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Włączanie zasad ochrony aplikacji usługi Intune w aplikacji mobilnej dla systemu Android

1. Dodaj [pakiet NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) do projektu Xamarin.Android.
    1. W przypadku aplikacji platformy Xamarin.Forms, dodać [pakietu Microsoft.Intune.MAM.Remapper.Tasks NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) do swojego projektu Xamarin.Android. 
2. Postępuj zgodnie z ogólną procedurę wymaganą do [integracji zestawu Intune App SDK](app-sdk-android.md) w aplikacji mobilnej systemu Android podczas odwoływania się do tego dokumentu, aby uzyskać więcej informacji.

### <a name="xamarinandroid-integration"></a>Integracja platformy Xamarin.Android

Pełne omówienie integracji zestawu SDK aplikacji usługi Intune można znaleźć w [Microsoft Intune App SDK for przewodnik dewelopera systemu Android](app-sdk-android.md). Zapoznaj się z artykułem przewodnika i integracja zestawu SDK aplikacji usługi Intune z aplikacją Xamarin sekcje są przeznaczone do wyróżnienia różnice między wdrożenia dla natywnych aplikacji dla systemu Android opracowanych w języku Java i aplikację Xamarin tworzone w C#. Sekcje te powinny być traktowane jako dodatkowe i nie może działać jako substytut Przeczytaj przewodnik w całości.

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Metody o zmienionej nazwie](app-sdk-android.md#renamed-methods)
W wielu przypadkach metoda dostępna w klasie systemu Android została oznaczona jako „final” w zastępczej klasie funkcji MAM. W takim przypadku klasa zastępcza funkcji MAM udostępnia metodę o podobnej nazwie (z sufiksem `MAM`), która powinna zostać przesłonięta zamiast niej. Na przykład przy tworzeniu klasy pochodnej klasy `MAMActivity` zamiast przesłaniać metodę `OnCreate()` i wywoływać metodę `base.OnCreate()` działanie `Activity` należy przesłonić metodę `OnMAMCreate()` i wywołać metodę `base.OnMAMCreate()`.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[Aplikacja do zarządzania aplikacjami Mobilnymi](app-sdk-android.md#mamapplication)
Aplikacja musi definiować `Android.App.Application` klasy dziedziczącej z klasy `MAMApplication`. Upewnij się, że do podklasy dodano prawidłowo atrybut `[Application]` i zastąpiono w niej konstruktor `(IntPtr, JniHandleOwnership)`.
```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

#### <a name="enable-features-that-require-app-participationapp-sdk-androidmdenable-features-that-require-app-participation"></a>[Włączanie funkcji wymagających udziału aplikacji](app-sdk-android.md#enable-features-that-require-app-participation)
Przykład: ustalenie, czy dla aplikacji jest wymagany numer PIN
```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```
Przykład: określenie głównego użytkownika usługi Intune
```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```
Przykład: ustalenie, czy jest dozwolone zapisywanie w pamięci urządzenia lub w magazynie w chmurze
```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdkapp-sdk-androidmdregister-for-notifications-from-the-sdk"></a>[Rejestrowanie się w celu otrzymywania powiadomień z zestawu SDK](app-sdk-android.md#register-for-notifications-from-the-sdk)
Aplikacja musi się zarejestrować w celu otrzymywania powiadomień z zestawu SDK, tworząc klasę `MAMNotificationReceiver` i dokonując rejestracji za pomocą metody `MAMNotificationReceiverRegistry`. W tym celu należy określić odbiorcę i typ żądanych powiadomień w metodzie `App.OnMAMCreate`, tak jak pokazano w przykładzie poniżej:
```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
    registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[Menedżer rejestracji zarządzania aplikacjami Mobilnymi](app-sdk-android.md#mamenrollmentmanager)
```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Integracja platformy Xamarin.Forms

Dla `Xamarin.Forms` aplikacje zostały zamieszczone `Microsoft.Intune.MAM.Remapper` pakiet w celu automatycznego wykonania zastąpienie klasy zarządzania aplikacjami Mobilnymi przez wprowadzenie `MAM` klas w hierarchii klasy często używane `Xamarin.Forms` klasy. 

> [!NOTE]
> Integracja zestawu narzędzi Xamarin.Forms ma odbywać się ponadto integracji platformy Xamarin.Android szczegóły przedstawiono powyżej.

Po dodaniu do projektu Remapper należy zastępowania równoważne zarządzania aplikacjami Mobilnymi. Na przykład `FormsAppCompatActivity` i `FormsApplicationActivity` mogą w dalszym ciągu można używać w swojej aplikacji, pod warunkiem zastąpień `OnCreate` i `OnResume` są zastępowane ich odpowiednikami MAM `OnMAMCreate` i `OnMAMResume` odpowiednio.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```
Jeśli zamiany nie zostały wprowadzone. następnie mogą wystąpić następujące błędy kompilacji dopóki nie zostaną wprowadzone zamiany:
* [Błąd kompilatora CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Ten błąd jest często spotykany w tym formularzu ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Jest to oczekiwane zachowanie, ponieważ kiedy narzędzie do ponownego mapowania modyfikuje dziedziczenie klas platformy Xamarin, stan niektórych funkcji jest zmieniany na `sealed` i zamiast tego do zastąpienia jest dodawany nowy wariant MAM.
* [Błąd kompilatora CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): ten błąd jest częsta w tym formularzu ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Kiedy narzędzie do ponownego mapowania zmienia dziedziczenie niektórych klas platformy Xamarin, stan niektórych funkcji członkowskich jest zmieniany na `public`. Jeśli możesz zastąpić dowolne z tych funkcji, konieczne będzie tych modyfikatorów dostępu dla osób, przesłonięć można zmienić `public` także.

> [!NOTE]
> Remapper ponownie zapisuje zależność, która korzysta z programu Visual Studio dla automatycznego uzupełniania IntelliSense. W związku z tym może być konieczne ponowne załadowanie i skompiluj ponownie projekt po dodaniu funkcji IntelliSense poprawnie zmiany Remapper.

## <a name="support"></a>Support
Jeśli Twoja organizacja jest istniejącym klientem usługi Intune, skontaktuj się z przedstawicielem pomocy technicznej firmy Microsoft, aby otworzyć bilet pomocy technicznej i utworzyć problem [na stronie problemów serwisu Github](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), a my pomożemy Ci tak szybko, jak to możliwe. 
