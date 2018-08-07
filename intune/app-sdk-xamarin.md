---
title: Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune
description: Powiązania Xamarin zestawu SDK aplikacji usługi Intune umożliwiają korzystanie z zasad ochrony aplikacji usługi Intune w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1cfbaa0cbdcc2263f6e8d1d3fc8562678e410537
ms.sourcegitcommit: e8aaa0955d13fa6c9d5f35a730ad06509ce88d0b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2018
ms.locfileid: "39400321"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

## <a name="overview"></a>Przegląd
[Powiązania Xamarin zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umożliwiają korzystanie z [zasad ochrony aplikacji usługi Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin. Powiązania te umożliwiają deweloperom łatwe dołączanie funkcji ochrony aplikacji Intune do ich aplikacji opartych na środowisku Xamarin.

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

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Włączenie zasad ochrony aplikacji usługi Intune w aplikacji mobilnej dla systemu iOS
1. Dodaj [pakiet NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) do projektu Xamarin.iOS.
2.  Wykonaj ogólne kroki wymagane w celu integracji zestawu SDK aplikacji usługi Intune z aplikacją mobilną systemu iOS. Można rozpocząć od kroku 3 instrukcji dotyczących integracji znajdujących się w [przewodniku dewelopera dotyczącym zestawu SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Możesz pominąć ostatni krok w tej sekcji dotyczący uruchamiania narzędzia IntuneMAMConfigurator, ponieważ to narzędzie jest zawarte w pakiecie Microsoft.Intune.MAM.Xamarin.iOS i zostanie uruchomione automatycznie podczas kompilacji.
    **Ważne**: procedura włączania udostępniania pęku kluczy dla aplikacji w programie Visual Studio różni się nieco od analogicznej procedury dla środowiska Xcode. Otwórz plik Entitlements.plist aplikacji i upewnij się, że opcja „Włącz pęk kluczy” jest włączona i że dodano w tej sekcji odpowiednie grupy udostępniania pęku kluczy. Następnie upewnij się, że plik Entitlements.plist został podany w polu „Niestandardowe uprawnienia” opcji „Podpisywanie zbiorów systemu iOS” projektu dla wszystkich odpowiednich kombinacji konfiguracji i platformy.
3.  Po dodaniu powiązań i odpowiednim skonfigurowaniu aplikacja może zacząć używać interfejsów API zestawu SDK usługi Intune. W tym celu należy uwzględnić następujące przestrzenie nazw:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Aby zacząć odbierać zasady ochrony aplikacji, aplikacja musi zostać zarejestrowana do celów zarządzania aplikacjami mobilnymi usługi Intune. Jeśli aplikacja używa już biblioteki ADAL (Active Directory Authentication Library) platformy Azure do uwierzytelniania użytkowników, aplikacja powinna dostarczyć nazwę UPN użytkownika do metody registerAndEnrollAccount obiektu IntuneMAMEnrollmentManager po jej pomyślnym uwierzytelnieniu:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Ważne**: należy pamiętać o zastąpieniu domyślnych ustawień biblioteki ADAL zestawu SDK aplikacji usługi Intune przy użyciu ustawień danej aplikacji. Można to zrobić za pomocą słownika IntuneMAMSettings w pliku Info.plist aplikacji, zgodnie z informacjami w [przewodniku dewelopera dotyczącym zestawu SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk). Możesz również użyć właściwości zastąpienia AAD wystąpienia IntuneMAMPolicyManager. Metoda z użyciem pliku Info.plist jest zalecana w przypadku aplikacji korzystających ze statycznych ustawień biblioteki ADAL, natomiast właściwości zastąpienia są rekomendowane dla aplikacji, które określają te wartości w środowisku uruchomieniowym. 
      
      Jeśli aplikacja nie korzysta z biblioteki ADAL, a chcesz obsługiwać uwierzytelnianie przy użyciu zestawu SDK usługi Intune, aplikacja powinna wywołać metodę loginAndEnrollAccount obiektu IntuneMAMEnrollmentManager:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      
> [!NOTE] 
> Dla systemu iOS narzędzie remapper jest niedostępne. Integracja z aplikacją Xamarin.Forms powinna przebiegać tak samo, jak w przypadku normalnego projektu Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Włączanie zasad ochrony aplikacji usługi Intune w aplikacji mobilnej dla systemu Android

W przypadku aplikacji dla systemu Android bazujących na środowisku Xamarin, które nie korzystają z platform tworzenia interfejsu użytkownika, musisz zapoznać się z [Przewodnikiem dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android](app-sdk-android.md) i postępować zgodnie z nim. Aplikacja dla systemu Android bazująca na środowisku Xamarin wymaga zastąpienia klas, metod i działań ich odpowiednikami MAM zgodnie z [tabelą](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) zawartą w tym przewodniku. Jeśli Twoja aplikacja nie zawiera definicji klasy `android.app.Application`, musisz ją utworzyć i zagwarantować dziedziczenie z klasy `MAMApplication`.

### <a name="xamarinandroid-integration"></a>Integracja platformy Xamarin.Android

1. Dodaj najnowszą wersję [pakietu NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) do projektu Xamarin.Android. Dzięki temu otrzymasz odwołania wymagane do włączenia obsługi aplikacji w usłudze Intune.

2. Przeczytaj i wykonaj instrukcje zawarte w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md), zwracając szczególną uwagę na:
    1. [Całą sekcję dotyczącą zastępowania klas i metod](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
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

2.  Dodaj wywołanie `Xamarin.Forms.Forms.Init(Context, Bundle)` do funkcji `OnMAMCreate` w klasie `MAMApplication` utworzonej w kroku 2.2. Jest to wymagane, ponieważ aplikacja zarządzana w usłudze Intune może być uruchamiana w tle.

> [!NOTE]
> Ponieważ ta operacja ponownie zapisuje zależność używaną w programie Visual Studio na potrzeby automatycznego uzupełniania Intellisense, po pierwszym uruchomieniu narzędzia remapper może być konieczne ponowne uruchomienie programu Visual Studio w celu zapewnienia prawidłowego rozpoznania zmian przez funkcję Intellisense. 


## <a name="support"></a>Support

Na tym kończy się podstawowa procedura dołączania składnika do aplikacji. Można teraz wykonać kroki zawarte w przykładowej aplikacji Xamarin Android. Dostępne są dwa przykłady — dla platformy Xamarin.Forms i systemu Android.

## <a name="requiring-intune-app-protection-policies-in-order-to-use-your-xamarin-based-android-lob-app-optional"></a>Wymaganie zasad ochrony aplikacji usługi Intune w celu korzystania z aplikacji biznesowej systemu Android opartej na środowisku Xamarin (opcjonalnie) 

Poniżej przedstawiono wskazówki dotyczące zapewniania, że aplikacje biznesowe systemu Android oparte na środowisku Xamarin mogą być używane tylko przez użytkowników chronionych przez usługę Intune na ich urządzeniach. 

### <a name="general-requirements"></a>Wymagania ogólne
* Zespół zestawu SDK usługi Intune będzie wymagać identyfikatora Twojej aplikacji. Można go znaleźć w witrynie [Azure Portal](https://portal.azure.com/) w obszarze **Wszystkie aplikacje** w kolumnie **Identyfikator aplikacji**. Dobrym sposobem na skontaktowanie się z zespołem zestawu SDK usługi Intune jest wysłanie wiadomości e-mail na adres msintuneappsdk@microsoft.com.
     
### <a name="working-with-the-intune-sdk"></a>Korzystanie z zestawu SDK usługi Intune
Te instrukcje dotyczą wszystkich aplikacji Android i Xamarin, w przypadku których chcesz wymagać zasad ochrony aplikacji usługi Intune do użycia na urządzeniu użytkownika końcowego.

1. Skonfiguruj bibliotekę ADAL, korzystając z kroków zdefiniowanych w [przewodniku zestawu SDK usługi Intune dla systemu Android](https://docs.microsoft.com/en-us/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).
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
> [!NOTE] 
> Oczekuje się, że wersja biblioteki .NET ADAL, która zostanie wydana jako następna (3.17.4), będzie zawierać poprawkę wymaganą do działania tej funkcji.

Jeśli Twoja organizacja jest istniejącym klientem usługi Intune, skontaktuj się z przedstawicielem pomocy technicznej firmy Microsoft, aby otworzyć bilet pomocy technicznej i utworzyć problem [na stronie problemów serwisu Github](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), a my pomożemy Ci tak szybko, jak to możliwe. 

