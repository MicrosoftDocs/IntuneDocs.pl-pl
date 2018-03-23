---
title: Składnik Xamarin zestawu SDK aplikacji usługi Microsoft Intune
description: Składnik Xamarin zestawu SDK aplikacji usługi Intune umożliwia korzystanie z zasad ochrony aplikacji usługi Intune w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin.
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
ms.openlocfilehash: b69cccca8c8be859de94ca8bdb50d6030439233a
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/20/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Składnik Xamarin zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.

## <a name="overview"></a>Przegląd
[Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umożliwia korzystanie z [zasad ochrony aplikacji usługi Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin. Składnik ten umożliwia deweloperom łatwe dołączanie funkcji ochrony aplikacji Intune do ich aplikacji opartych na środowisku Xamarin.

> [!NOTE]
> Obsługa zestawu SDK usługi Intune dla platformy Xamarin jest obecnie dostępna w wersji zapoznawczej. 

Składnik Xamarin zestawu Microsoft Intune App SDK pozwala wdrażać zasady ochrony aplikacji usługi Intune (nazywane również zasadami APP lub MAM) we własnych aplikacjach utworzonych w środowisku Xamarin. Aplikacja obsługująca zarządzanie aplikacjami mobilnymi to aplikacja zintegrowana z zestawem SDK aplikacji usługi Intune. Administratorzy IT mogą wdrażać zasady ochrony aplikacji w aplikacji mobilnej, gdy usługa Intune aktywnie zarządza aplikacją.

## <a name="whats-supported"></a>Co jest obsługiwane?

### <a name="developer-machines"></a>Maszyny deweloperów
* macOS


### <a name="mobile-app-platforms"></a>Platformy aplikacji mobilnych
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scenariusze zarządzanie aplikacjami mobilnymi w usłudze Intune

* Urządzenia zarejestrowane przez funkcję zarządzania urządzeniami przenośnymi w usłudze Intune
* Urządzenia zarejestrowane przez rozwiązanie EMM innej firmy
* Niezarządzane urządzenia (nie zarejestrowane za pomocą żadnego rozwiązania do zarządzania urządzeniami przenośnymi)

Aplikacje Xamarin utworzone za pomocą składnika Xamarin zestawu Intune App SDK mogą teraz odbierać zasady ochrony aplikacji usługi Intune zarówno na urządzeniach przenośnych zarejestrowanych w systemie zarządzania urządzeniami przenośnymi (MDM) usługi Intune, jak i na urządzeniach niezarejestrowanych.

## <a name="prerequisites"></a>Wymagania wstępne

* **[Tylko system Android]** Na urządzeniu musi być zainstalowana najnowsza aplikacja Portal firmy usługi Microsoft Intune.

## <a name="get-started"></a>Wprowadzenie

1. Zapoznaj się z [postanowieniami licencyjnymi](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) dla składnika Xamarin zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune.

2.  Pobierz pakiety NuGet składnika Xamarin zestawu SDK aplikacji usługi Intune z serwisu [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin). Te pakiety będą wkrótce dostępne w witrynie Nuget.org.  

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Włączenie zasad ochrony aplikacji usługi Intune w aplikacji mobilnej dla systemu iOS
1. Dodaj pakiet NuGet `Microsoft.Intune.MAM.Xamarin.iOS` do projektu Xamarin.iOS.
2.  Wykonaj ogólne kroki wymagane w celu integracji zestawu SDK aplikacji usługi Intune z aplikacją mobilną systemu iOS. Można rozpocząć od kroku 3 instrukcji dotyczących integracji znajdujących się w [przewodniku dewelopera dotyczącym zestawu SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Możesz pominąć ostatni krok w tej sekcji dotyczący uruchamiania narzędzia IntuneMAMConfigurator, ponieważ to narzędzie jest zawarte w pakiecie Microsoft.Intune.MAM.Xamarin.iOS i zostanie uruchomione automatycznie podczas kompilacji.
    **Ważne**: procedura włączania udostępniania pęku kluczy dla aplikacji w programie Visual Studio różni się nieco od analogicznej procedury dla środowiska Xcode. Otwórz plik Entitlements.plist aplikacji i upewnij się, że opcja „Włącz pęk kluczy” jest włączona i że dodano w tej sekcji odpowiednie grupy udostępniania pęku kluczy. Następnie upewnij się, że plik Entitlements.plist został podany w polu „Niestandardowe uprawnienia” opcji „Podpisywanie zbiorów systemu iOS” projektu dla wszystkich odpowiednich kombinacji konfiguracji i platformy.
3.  Po dodaniu składnika i odpowiednim skonfigurowaniu aplikacja może zacząć używać interfejsów API zestawu SDK usługi Intune. W tym celu należy uwzględnić następujące przestrzenie nazw:

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
Dodaj pakiet NuGet `Microsoft.Intune.MAM.Xamarin.Android` do projektu Xamarin.Android.

W przypadku aplikacji dla systemu Android bazujących na środowisku Xamarin, które nie korzystają z platform tworzenia interfejsu użytkownika, musisz zapoznać się z [Przewodnikiem dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android](app-sdk-android.md) i postępować zgodnie z nim. Aplikacja dla systemu Android bazująca na środowisku Xamarin wymaga zastąpienia klas, metod i działań ich odpowiednikami MAM zgodnie z [tabelą](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) zawartą w tym przewodniku. Jeśli Twoja aplikacja nie zawiera definicji klasy `android.app.Application`, musisz ją utworzyć i zagwarantować dziedziczenie z klasy `MAMApplication`.

W przypadku zestawu Xamarin Forms i innych platform tworzenia interfejsu użytkownika można skorzystać z narzędzia o nazwie `MAM.Remapper`. Narzędzie to automatycznie zastępuje klasy. Konieczne jest jednak wykonanie następujących kroków:

1.  Dodaj pakiet NuGet `Microsoft.Intune.MAM.Remapper.Tasks`.

2.  Dodaj następujący wiersz do projektu csproj systemu Android (zastąp ciąg „x.x.x.x” bieżącą wersją pakietu):
  ```xml
 <Import Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.x.x.x.x\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Ustaw akcję kompilacji dodanego pliku `remapping-config.json` na wartość **RemappingConfigFile**. Dołączony plik `remapping-config.json` współdziała tylko z zestawem Xamarin.Forms. W przypadku innych platform tworzenia interfejsu użytkownika zapoznaj się z plikiem Readme dołączonym do pakietu NuGet o nazwie Remapper.

## <a name="next-steps"></a>Następne kroki

Na tym kończy się podstawowa procedura dołączania składnika do aplikacji. Można teraz wykonać kroki zawarte w przykładowej aplikacji Xamarin Android. Dostępne są dwa przykłady — dla platformy Xamarin.Forms i systemu Android.
