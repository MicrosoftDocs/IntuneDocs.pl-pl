---
title: "Składnik Xamarin zestawu SDK aplikacji usługi Microsoft Intune"
description: 
keywords: sdk, Xamarin, intune
author: mattbriggs
manager: angrobe
ms.author: mabriggs
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8ab9807d22aa1a5c232b595df2bd999c0c178b16
ms.sourcegitcommit: f3b8fb8c47fd2c9941ebbe2c047b7d0a093e5a83
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/11/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Składnik Xamarin zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.



## <a name="overview"></a>Przegląd
[Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://components.xamarin.com/view/microsoft.intune.mam) umożliwia korzystanie z [zasad ochrony aplikacji usługi Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin. Składnik ten umożliwia deweloperom łatwe dołączanie funkcji ochrony aplikacji Intune do ich aplikacji opartych na środowisku Xamarin.

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

1.  Pobierz plik **Xamarin-component.exe** z [tej](https://components.xamarin.com/submit/xpkg) lokalizacji i wyodrębnij jego zawartość.

2. Zapoznaj się z [postanowieniami licencyjnymi](https://components.xamarin.com/license/microsoft.intune.mam) dla składnika Xamarin zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune.

3.  Pobierz folder składnika Xamarin zestawu SDK aplikacji usługi Intune z witryny [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) lub [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) i wyodrębnij jego zawartość. Oba pliki pobrane w punktach 1 i 3 powinny znajdować się w katalogach tego samego poziomu.

4.  W wierszu polecenia uruchom polecenie `Xamarin.Component.exe install <.xam> file` z uprawnieniami administracyjnymi.

5.  W programie Visual Studio kliknij prawym przyciskiem myszy **składniki** we wcześniej utworzonym projekcie Xamarin.

6.  Wybierz pozycję **Edytuj składniki** i dodaj składnik zestawu SDK aplikacji usługi Intune, który został pobrany na komputer.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Włączenie zasad ochrony aplikacji usługi Intune w aplikacji mobilnej dla systemu iOS
1.  Aby zainicjować zestaw Intune App SDK, musisz wywołać dowolny interfejs API w klasie `AppDelegate.cs`. Na przykład:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Gdy składnik został dodany i zainicjowany, można wykonać ogólną procedurę wymaganą do dołączenia zestawu SDK aplikacji do aplikacji mobilnej systemu iOS. Pełną dokumentację dotyczącą włączania natywnych aplikacji systemu iOS można znaleźć w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md).
3. **Ważne**: istnieje kilka specyficznych modyfikacji dotyczących aplikacji systemu iOS opartych na środowisku Xamarin. Na przykład podczas włączania grup pęków kluczy musisz dodać następujące informacje, aby uwzględnić przykładową aplikację Xamarin, którą dodaliśmy do składnika. Poniżej podano przykładowe grupy, które muszą znaleźć się w grupach dostępu pęku kluczy:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Na tym kończy się procedura dołączania składnika do aplikacji systemu iOS opartej na platformie Xamarin. Jeśli do tworzenia projektu jest używany edytor Xcode, można użyć pakietu `Intune App SDK Settings.bundle`. Pozwala to włączać i wyłączać ustawienia zasad usługi Intune w trakcie tworzenia projektu na potrzeby testowania i debugowania. Aby skorzystać z tego pakietu, wykonaj czynności opisane w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md) i zapoznaj się z sekcją dotyczącą [debugowania w programie Xcode](app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Włączanie zasad ochrony aplikacji w Twojej aplikacji mobilnej dla systemu Android
W przypadku aplikacji dla systemu Android bazujących na środowisku Xamarin, które nie korzystają z platform tworzenia interfejsu użytkownika, musisz zapoznać się z [Przewodnikiem dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android](app-sdk-android.md) i postępować zgodnie z nim. Aplikacja dla systemu Android bazująca na środowisku Xamarin wymaga zastąpienia klas, metod i działań ich odpowiednikami MAM zgodnie z [tabelą](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) zawartą w tym przewodniku. Jeśli Twoja aplikacja nie zawiera definicji klasy `android.app.Application`, musisz ją utworzyć i zagwarantować dziedziczenie z klasy `MAMApplication`.

W przypadku zestawu Xamarin Forms i innych platform tworzenia interfejsu użytkownika można skorzystać z narzędzia o nazwie `MAM.Remapper`. Narzędzie to automatycznie zastępuje klasy. Konieczne jest jednak wykonanie następujących kroków:

1.  Dodaj odwołanie do pakietu NuGet `Microsoft.Intune.MAM.Remapper.Tasks` w wersji 0.1.0.0 lub nowszej.

2.  Dodaj następujący wiersz do pliku csproj aplikacji systemu Android:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Ustaw akcję kompilacji dodanego pliku `remapping-config.json` na wartość **RemappingConfigFile**. Dołączony plik `remapping-config.json` współdziała tylko z zestawem Xamarin.Forms. W przypadku innych platform tworzenia interfejsu użytkownika zapoznaj się z plikiem Readme dołączonym do pakietu NuGet o nazwie Remapper.

## <a name="next-steps"></a>Następne kroki

Na tym kończy się podstawowa procedura dołączania składnika do aplikacji. Można teraz wykonać kroki zawarte w przykładowej aplikacji Xamarin Android. Dostępne są dwa przykłady — dla platformy Xamarin.Forms i systemu Android.