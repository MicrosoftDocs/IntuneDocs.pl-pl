---
title: "Składnik Xamarin zestawu SDK aplikacji usługi Microsoft Intune | Dokumentacja firmy Microsoft"
description: 
keywords: sdk, Xamarin, intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c59707ba2967b069dc30aee71d2642e91d71b23b
ms.openlocfilehash: 74607fc704234e6ac85eae3bf55c186000c6e68a


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Składnik Xamarin zestawu SDK aplikacji usługi Microsoft Intune

> [!NOTE]
> Warto najpierw przeczytać artykuł [Wprowadzenie do zestawu SDK aplikacji usługi Intune](intune-app-sdk-get-started.md), w którym omówiono przygotowanie do integracji na poszczególnych obsługiwanych platformach.



## <a name="overview"></a>Przegląd
[Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://components.xamarin.com/view/microsoft.intune.mam) umożliwia korzystanie z [funkcji zarządzania aplikacjami mobilnymi usługi Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) w aplikacjach dla systemów iOS i Android utworzonych za pomocą platformy Xamarin. Składnik ten umożliwia deweloperom łatwe dołączanie funkcji ochrony aplikacji Intune do ich aplikacji opartych na środowisku Xamarin.

Funkcje zestawu SDK można włączyć bez zmiany zachowania aplikacji. Po dołączeniu składnika do aplikacji mobilnej dla systemu iOS lub Android administrator IT może za pośrednictwem zarządzania aplikacjami mobilnymi (MAM) w usłudze Microsoft Intune wdrożyć zasady obsługujące różne funkcje ochrony danych.

## <a name="whats-supported"></a>Co jest obsługiwane?

### <a name="developer-machines"></a>Maszyny deweloperów
* Windows


### <a name="mobile-app-platforms"></a>Platformy aplikacji mobilnych
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scenariusze zarządzanie aplikacjami mobilnymi w usłudze Intune

* Urządzenia zarejestrowane przez funkcję zarządzania urządzeniami przenośnymi w usłudze Intune
* Urządzenia zarejestrowane przez rozwiązanie EMM innej firmy
* Niezarządzane urządzenia (nie zarejestrowane za pomocą żadnego rozwiązania do zarządzania urządzeniami przenośnymi)

Aplikacje Xamarin skompilowane za pomocą składnika Xamarin zestawu SDK aplikacji usługi Intune mogą teraz podlegać zasadom zarządzania aplikacjami mobilnymi usługi Intune zarówno w przypadku urządzeń zarejestrowanych na potrzeby zarządzania urządzeniami przenośnymi w usłudze Intune, jak i niezarejestrowanych urządzeń.

## <a name="prerequisites"></a>Wymagania wstępne

* **[Dotyczy tylko systemu Android]** Na urządzeniu musi zawsze być zainstalowana najnowsza wersja aplikacji Portal firmy usługi Microsoft Intune.

## <a name="get-started"></a>Wprowadzenie

1.    Pobierz plik **Xamarin-component.exe** z [tej](https://components.xamarin.com/submit/xpkg) lokalizacji i wyodrębnij jego zawartość.

2. Zapoznaj się z [postanowieniami licencyjnymi](https://components.xamarin.com/license/microsoft.intune.mam) dla składnika Xamarin zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune.

3.    Pobierz folder składnika Xamarin zestawu SDK aplikacji usługi Intune z witryny [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) lub [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) i wyodrębnij jego zawartość. Oba pliki pobrane w punktach 1 i 2 powinny znajdować się w katalogach tego samego poziomu.

4.    W wierszu polecenia uruchom polecenie `Xamain.Component.exe install <.xam> file` z uprawnieniami administracyjnymi.

5.    W programie Visual Studio kliknij prawym przyciskiem myszy **składniki** utworzonego wcześniej projektu Xamarin.

6.    Wybierz pozycję **Edytuj składniki** i dodaj składnik zestawu SDK aplikacji usługi Intune, który został pobrany na komputer.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Włączanie obsługi zarządzania aplikacjami mobilnymi w usłudze Intune w aplikacji mobilnej systemu iOS
1.    Aby zainicjować zestaw SDK aplikacji usługi Intune, należy wywołać dowolny interfejs API klasy `AppDelegate.cs`. Na przykład:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.    Gdy składnik został dodany i zainicjowany, można wykonać ogólną procedurę wymaganą do dołączenia zestawu SDK aplikacji do aplikacji mobilnej systemu iOS. Pełną dokumentację dotyczącą włączania natywnych aplikacji systemu iOS można znaleźć w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](intune-app-sdk-ios.md).
3. **Ważne**: istnieje kilka specyficznych modyfikacji dotyczących aplikacji systemu iOS opartych na środowisku Xamarin. Na przykład podczas włączania grup pęku kluczy należy dodać następujący kod, aby dołączyć przykładową aplikację Xamarin, która jest częścią składnika. Poniżej podano przykładowe grupy, które muszą znaleźć się w grupach dostępu pęku kluczy:

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

Na tym kończy się procedura dołączania składnika do aplikacji systemu iOS opartej na platformie Xamarin. Jeśli do tworzenia projektu jest używany edytor Xcode, można użyć pakietu `Intune App SDK Settings.bundle`. Pozwoli to włączać i wyłączać ustawienia zasad usługi Intune na potrzeby testowania i debugowania podczas tworzenia projektu. Aby skorzystać z tego pakietu, wykonaj czynności opisane w [Przewodniku dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](intune-app-sdk-ios.md) i zapoznaj się z sekcją dotyczącą [debugowania w programie Xcode](intune-app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-mam-in-your-android-mobile-app"></a>Włączanie obsługi zarządzania aplikacjami mobilnymi w aplikacji mobilnej systemu Android
W przypadku aplikacji systemu Android opartych na środowisku Xamarin, które nie korzystają z platformy tworzenia interfejsu użytkownika, należy zapoznać się z treścią dokumentu [Przewodnik dewelopera po zestawie SDK aplikacji usługi Intune dla systemu Android] i postępować zgodnie z zawartymi w nim wytycznymi. W przypadku aplikacji systemu Android opartej na środowisku Xamarin musisz zastąpić klasę, metody i działania odpowiednimi ekwiwalentami z obsługą zarządzania aplikacjami mobilnymi, korzystając z [tabeli](intune-app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent-required) zawartej w tym przewodniku. Jeśli w danej aplikacji nie zdefiniowano klasy `android.app.Application`, musisz ją utworzyć i zapewnić jej dziedziczenie po `MAMApplication`.

W przypadku zestawu Xamarin Forms i innych platform tworzenia interfejsu użytkownika można skorzystać z narzędzia o nazwie `MAM.Remapper`. Narzędzie to umożliwia automatyczne zastąpienie klasy. Musisz jednak wykonać następujące czynności:

1.    Dodaj odwołanie do pakietu Nuget ` Microsoft.Intune.MAM.Remapper.Tasks` w wersji 0.1.0.0 lub nowszej.

2.    Dodaj następujący wiersz do pliku csproj aplikacji systemu Android:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.    Ustaw akcję kompilacji dodanego pliku `remapping-config.json` na wartość **RemappingConfigFile**. Dołączony plik `remapping-config.json` współdziała tylko z zestawem Xamarin.Forms. Informacje dotyczące innych platform tworzenia interfejsu użytkownika można znaleźć w pliku Readme dołączonym do pakietu Nuget Remapper.

## <a name="test-your-app"></a>Testowanie aplikacji

Na tym kończy się podstawowa procedura dołączania składnika do aplikacji. Można teraz wykonać kroki zawarte w przykładowej aplikacji Xamarin Android. Dostępne są dwa przykłady — dla platformy Xamarin.Forms i systemu Android.



<!--HONumber=Dec16_HO2-->


