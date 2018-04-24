---
title: Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune
description: Powiązania Xamarin zestawu SDK aplikacji usługi Intune umożliwiają korzystanie z zasad ochrony aplikacji usługi Intune w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9f9cc117925f59c9fb7c55d0ff10aedf09d26f93
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Powiązania Xamarin zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

## <a name="overview"></a>Przegląd
[Powiązania Xamarin zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umożliwiają korzystanie z [zasad ochrony aplikacji usługi Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin. Powiązania te umożliwiają deweloperom łatwe dołączanie funkcji ochrony aplikacji Intune do ich aplikacji opartych na środowisku Xamarin.

Powiązania Xamarin zestawu Microsoft Intune App SDK pozwalają wdrażać zasady ochrony aplikacji usługi Intune (nazywane również zasadami APP lub MAM) we własnych aplikacjach utworzonych w środowisku Xamarin. Aplikacja obsługująca zarządzanie aplikacjami mobilnymi to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy IT mogą wdrażać zasady ochrony aplikacji w aplikacji mobilnej, gdy usługa Intune aktywnie zarządza aplikacją.

## <a name="whats-supported"></a>Co jest obsługiwane?

### <a name="developer-machines"></a>Maszyny deweloperów
* Windows
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

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Włączanie zasad ochrony aplikacji w Twojej aplikacji mobilnej dla systemu Android
Dodaj [pakiet NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) do projektu Xamarin.Android.

W przypadku aplikacji Xamarin.Android musisz dokładnie przeczytać [Przewodnik dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md) i przestrzegać zawartych w nim instrukcji, w tym dotyczących zastępowania klas, metod i działań przy użyciu ich równoważników funkcji zarządzania aplikacjami mobilnymi w oparciu o [tabelę](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) dołączoną do przewodnika. 

> [!NOTE]
> Jeśli Twoja aplikacja nie zawiera definicji klasy `android.app.Application`, musisz ją utworzyć i zagwarantować dziedziczenie z klasy `MAMApplication`.

> [!NOTE]
> W przypadku wyszukiwania równoważnych interfejsów API z [Przewodnika dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md) w powiązaniach `Microsoft.Intune.MAM.Xamarin.Android` lub konwertowania fragmentów kodu z przewodnika należy pamiętać, że generator powiązań Xamarin modyfikuje interfejsy API systemu Android w następujący, zauważalny sposób:
> * Wszystkie identyfikatory są konwertowane do notacji PascalCase (com.microsoft.foo -> Com.Microsoft.Foo)
> * Wszystkie operacje get/set są konwertowane do operacji właściwości (np. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Wszystkie interfejsy mają znak „I” dołączony na początku nazwy (FooInterface -> IFooInterface)

W przypadku aplikacji korzystających z zestawu Xamarin.Forms lub innych platform tworzenia interfejsu użytkownika można skorzystać z narzędzia o nazwie `Microsoft.Intune.MAM.Remapper`. Narzędzie to automatycznie zastępuje klasy. Aby użyć tego narzędzia, wykonaj następujące czynności:

1.  Dodaj pakiet NuGet [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) do projektu.

2.  Ustaw akcję kompilacji pliku `remapping-config.json` dołączonego do pakietu NuGet na wartość **RemappingConfigFile**. Dołączony plik `remapping-config.json` współdziała tylko z zestawem Xamarin.Forms. W przypadku innych platform tworzenia interfejsu użytkownika zapoznaj się z plikiem Readme dołączonym do pakietu NuGet o nazwie Remapper.

3.  Dodaj wywołanie do elementu Xamarin.Forms.Forms.Init(Context, Bundle) w funkcji OnMAMCreate aplikacji MAMApplication, ponieważ przy użyciu zarządzania w usłudze Intune aplikację można uruchomić w tle.

4.  Wykonaj pozostałe kroki opisane w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md), które mają zastosowanie do Twojej aplikacji.

> [!NOTE]
> Akcja kompilacji remapping-config.json może czasem zostać zresetowana podczas aktualizowania pakietu Microsoft.Intune.MAM.Remapper.Tasks, co będzie prowadzić do niepowodzenia kompilacji.

## <a name="next-steps"></a>Następne kroki

Wykonano podstawowe kroki związane z ustawianiem aplikacji pod kątem zarządzania w usłudze Intune. Teraz możesz wykonać kroki uwzględnione w przewodnikach dotyczących integracji dla każdej z wyżej wymienionych platform.

Jeśli Twoja organizacja jest istniejącym klientem usługi Intune, skontaktuj się z przedstawicielem pomocy technicznej firmy Microsoft, aby otworzyć bilet pomocy technicznej i utworzyć problem [na stronie problemów serwisu Github](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), a my pomożemy Ci tak szybko, jak to możliwe. 