---
title: Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune
description: Powiązania Xamarin zestawu SDK aplikacji usługi Intune umożliwiają korzystanie z zasad ochrony aplikacji usługi Intune w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: 65a461928c377dd4a674f8f3f2eeeef148ab56b2
ms.sourcegitcommit: 912aee714432c4a1e8efeee253ca2be4f972adaa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316903"
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
    **Ważne**: Procedura włączania udostępniania pęku kluczy dla aplikacji w programie Visual Studio różni się nieco od analogicznej procedury dla środowiska Xcode. Otwórz plik Entitlements.plist aplikacji i upewnij się, że opcja „Włącz pęk kluczy” jest włączona i że dodano w tej sekcji odpowiednie grupy udostępniania pęku kluczy. Następnie upewnij się, że plik Entitlements.plist został podany w polu „Niestandardowe uprawnienia” opcji „Podpisywanie zbiorów systemu iOS” projektu dla wszystkich odpowiednich kombinacji konfiguracji i platformy.
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

W przypadku aplikacji dla systemu Android bazujących na środowisku Xamarin, które nie korzystają z platform tworzenia interfejsu użytkownika, musisz zapoznać się z [Przewodnikiem dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android](app-sdk-android.md) i postępować zgodnie z nim. Aplikacja dla systemu Android bazująca na środowisku Xamarin wymaga zastąpienia klas, metod i działań ich odpowiednikami MAM zgodnie z [tabelą dotyczącą zastępowania klas i metod](app-sdk-android.md#class-and-method-replacements) w tym przewodniku. Jeśli Twoja aplikacja nie zawiera definicji klasy `android.app.Application`, musisz ją utworzyć i zagwarantować dziedziczenie z klasy `MAMApplication`. Wartości konfiguracji biblioteki ADAL są przekazywane do zestawu SDK przez metadane w pliku AndroidManifest. Przeczytaj dokumentację dotyczącą [konfigurowania biblioteki ADAL dla aplikacji](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="xamarinandroid-integration"></a>Integracja platformy Xamarin.Android

1. Dodaj najnowszą wersję [pakietu NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) do projektu Xamarin.Android. Dzięki temu otrzymasz odwołania wymagane do włączenia obsługi aplikacji w usłudze Intune.

2. Przeczytaj i wykonaj instrukcje zawarte w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md), zwracając szczególną uwagę na:

    1. [Całą sekcję dotyczącą zastępowania klas i metod](app-sdk-android.md#class-and-method-replacements). 
    2. [Sekcję MAMApplication](app-sdk-android.md#mamapplication). Upewnij się, że do podklasy dodano prawidłowo atrybut `[Application]` i zastąpiono w niej konstruktor `(IntPtr, JniHandleOwnership)`.
    3. [Sekcję dotyczącą integracji usługi ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal), jeśli aplikacja przeprowadza uwierzytelnianie w usłudze AAD. 
    4. [Sekcję dotyczącą rejestracji w usłudze MAM-WE](app-sdk-android.md#app-protection-policy-without-device-enrollment), jeśli planujesz uzyskanie zasad z usługi MAM w aplikacji.

> [!NOTE]
> W przypadku wyszukiwania równoważnych interfejsów API z [Przewodnika dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md) w powiązaniach `Microsoft.Intune.MAM.Xamarin.Android` lub konwertowania fragmentów kodu z przewodnika należy pamiętać, że generator powiązań Xamarin modyfikuje interfejsy API systemu Android na następujące istotne sposoby:
> * Wszystkie identyfikatory są konwertowane na wielkość liter Pascal (com.foo.bar -> Com.Foo.Bar)
> * Wszystkie operacje get/set są konwertowane na operacje właściwości (np. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Wszystkie interfejsy mają znak „I” dołączony na początku nazwy (FooInterface -> IFooInterface)

### <a name="xamarinforms-integration"></a>Integracja platformy Xamarin.Forms

**Oprócz wykonania wszystkich powyższych czynności** w przypadku aplikacji `Xamarin.Forms` został udostępniony pakiet `Microsoft.Intune.MAM.Remapper`. Ten pakiet umożliwia automatyczne zastępowanie klas przez wprowadzenie klas `MAM` do hierarchii typowych klas `Xamarin.Forms`, takich jak `FormsAppCompatActivity` i `FormsApplicationActivity`, dzięki czemu możesz nadal używać tych klas, wprowadzając zastąpienia dla równoważnych funkcji MAM, takich jak `OnMAMCreate` i `OnMAMResume`. Aby użyć tego narzędzia, wykonaj następujące czynności:

1.  Dodaj pakiet NuGet [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) do projektu. To spowoduje automatyczne dodanie powiązań platformy Xamarin dla zestawu Intune App SDK, jeśli nie zostały jeszcze dodane.

2.  Dodaj wywołanie `Xamarin.Forms.Forms.Init(Context, Bundle)` do funkcji `OnMAMActivity` w klasie `MAMApplication` utworzonej w kroku 2.2. Jest to wymagane, ponieważ aplikacja zarządzana w usłudze Intune może być uruchamiana w tle.

> [!NOTE]
> Ponieważ ta operacja ponownie zapisuje zależność używaną w programie Visual Studio na potrzeby automatycznego uzupełniania Intellisense, po pierwszym uruchomieniu narzędzia remapper może być konieczne ponowne uruchomienie programu Visual Studio w celu zapewnienia prawidłowego rozpoznania zmian przez funkcję Intellisense. 

## <a name="requiring-intune-app-protection-policies-in-order-to-use-your-xamarin-based-android-lob-app-optional"></a>Wymaganie zasad ochrony aplikacji usługi Intune w celu korzystania z aplikacji biznesowej systemu Android opartej na środowisku Xamarin (opcjonalnie) 

Poniżej przedstawiono wskazówki dotyczące zapewniania, że aplikacje biznesowe systemu Android oparte na środowisku Xamarin mogą być używane tylko przez użytkowników chronionych przez usługę Intune na ich urządzeniach. 
    
### <a name="working-with-the-intune-sdk"></a>Korzystanie z zestawu SDK usługi Intune
Te instrukcje dotyczą wszystkich aplikacji Android i Xamarin, w przypadku których chcesz wymagać zasad ochrony aplikacji usługi Intune do użycia na urządzeniu użytkownika końcowego.

1. Skonfiguruj bibliotekę ADAL, korzystając z kroków zdefiniowanych w [przewodniku zestawu SDK usługi Intune dla systemu Android](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).
> [!NOTE] 
> Termin „identyfikator klienta” jest odpowiednikiem terminu „identyfikator aplikacji” w witrynie Azure Portal związanego z Twoją aplikacją. 
* Aby włączyć logowanie jednokrotne, skorzystaj z typowej konfiguracji biblioteki ADAL nr 2.

2. Włącz rejestrację domyślną przez umieszczenie w manifeście następującej wartości: ```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
> [!NOTE] 
> Musi to być jedyna integracja z usługą MAM-WE w aplikacji. Wszelkie inne próby wywołania interfejsów API MAMEnrollmentManager mogą powodować konflikty.

3. Włącz wymagane zasady zarządzania aplikacjami mobilnymi przez umieszczenie w manifeście następującej wartości: ```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
> [!NOTE] 
> Wymusi to na aplikacjach pobranie aplikacji Portal firmy na urządzenie i ukończenie przepływu rejestracji domyślnej przed użyciem.

### <a name="working-with-adal"></a>Praca z biblioteką ADAL
Te instrukcje stanowią wymaganie dla aplikacji platformy .NET/Xamarin, w przypadku których chcesz wymagać zasad ochrony aplikacji usługi Intune do użycia na urządzeniu użytkownika końcowego.

1. Wykonaj wszystkie kroki zdefiniowane w dokumentacji biblioteki ADAL w sekcji [Brokered Authentication for Android (Uwierzytelnianie obsługiwane przez brokera dla systemu Android)](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/tree/dev/adal#brokered-authentication-for-android).

## <a name="potential-compilation-errors"></a>Potencjalne błędy kompilacji
Poniżej przedstawiono niektóre błędy kompilacji spotykane najczęściej podczas opracowywania aplikacji opartej na środowisku Xamarin.

* [Błąd kompilatora CS0239](https://docs.microsoft.com/en-us/dotnet/csharp/misc/cs0239): Ten błąd jest często spotykany w tym formularzu ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Kiedy narzędzie do ponownego mapowania modyfikuje dziedziczenie klas platformy Xamarin, stan niektórych funkcji jest zmieniany na `sealed` i zamiast tego do zastąpienia jest dodawany nowy wariant MAM. Wystarczy zmienić nazwę zastąpień, jak opisano [tutaj](https://docs.microsoft.com/en-us/intune/app-sdk-android#renamed-methods). Na przykład nazwę elementu `MainActivity.OnCreate()` można zmienić na `MainActivity.OnMAMCreate()`

* [Błąd kompilatora CS0507](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-messages/cs0507): Ten błąd jest często spotykany w tym formularzu ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Kiedy narzędzie do ponownego mapowania zmienia dziedziczenie niektórych klas platformy Xamarin, stan niektórych funkcji członkowskich jest zmieniany na `public`. W przypadku zastąpienia którejkolwiek z tych funkcji może być konieczna także zmiana stanu zastąpienia na `public`.

## <a name="support"></a>Support
Jeśli Twoja organizacja jest istniejącym klientem usługi Intune, skontaktuj się z przedstawicielem pomocy technicznej firmy Microsoft, aby otworzyć bilet pomocy technicznej i utworzyć problem [na stronie problemów serwisu Github](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), a my pomożemy Ci tak szybko, jak to możliwe. 
