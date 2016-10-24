---
title: "Opakowywanie aplikacji systemu Android za pomocą narzędzia opakowującego aplikacje | Microsoft Intune"
description: "Ten temat przedstawia informacje o sposobie opakowywania aplikacji systemu Android bez konieczności modyfikacji kodu samej aplikacji. Przygotuj aplikacje tak, aby można było stosować zasady zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe3a9f2fd9ce9a3c3f776dcfd9ad3347a63d0fc1
ms.openlocfilehash: e623755cf926020bcb66d8a6d40e5cce9b46b0ae


---

# Przygotowanie aplikacji systemu Android do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Intune
Za pomocą **narzędzia opakowującego aplikacje dla systemu Android w usłudze Microsoft Intune** można modyfikować działanie wewnętrznych aplikacji dla systemu Android przez ograniczanie ich funkcji bez konieczności zmieniania kodu aplikacji.

Narzędzie to jest aplikacją wiersza polecenia systemu Windows działającą w programie PowerShell i tworzy „otokę” wokół aplikacji dla systemu Android. Po opakowaniu wybranej aplikacji można modyfikować jej funkcje, konfigurując [zasady zarządzania aplikacjami mobilnymi](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) usługi Intune.


Przed uruchomieniem tego narzędzia należy zapoznać się z sekcją [Uwagi dotyczące zabezpieczeń przy uruchamianiu narzędzia opakowującego aplikacje](#security-considerations-for-running-the-app-wrapping-tool). Aby pobrać to narzędzie, odwiedź stronę [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) (Narzędzie opakowujące aplikacje dla systemu Android w usłudze Microsoft Intune) w witrynie GitHub.



## Krok 1 Spełnianie wymagań wstępnych dotyczących używania narzędzia opakowującego aplikacje

-   Narzędzie opakowujące aplikacje musi zostać uruchomione na komputerze z systemem Windows 7 lub nowszym.

-   Aplikacja wejściowa musi być prawidłowym pakietem aplikacji Android z rozszerzeniem pliku **apk** oraz:

    -   nie może być szyfrowana,

    -   nie może wcześniej być opakowana przez narzędzie opakowujące aplikacje usługi Intune,
    -   musi być napisana dla systemu Android 4.0 lub nowszego,

-   aplikacja musi być opracowana przez Twoją firmę lub dla niej. To narzędzie nie może być używane do przetwarzania aplikacji pobranych ze sklepu Google Play.

-   Aby uruchomić narzędzie opakowujące aplikacje, należy zainstalować najnowszą wersję programu [Java Runtime Environment](http://java.com/download/) i upewnić się, że w zmiennych środowiskowych systemu Windows została ustawiona zmienna ścieżki Java **C:\ProgramData\Oracle\Java\javapath**. Aby uzyskać więcej informacji, zobacz [dokumentację środowiska Java](http://java.com/download/help/).

    > [!NOTE]
    > W pewnych sytuacjach 32-bitowa wersja programu Java może spowodować problemy z pamięcią. Zaleca się zainstalowanie wersji 64-bitowej.

- System Android wymaga, aby wszystkie pakiety aplikacji (apk) były podpisane. Użyj narzędzia Java Key Tool do wygenerowania poświadczeń wymaganych do podpisania opakowanej aplikacji wyjściowej. Na przykład poniższe polecenie umożliwia użycie pliku wykonywalnego Java **keytool.exe** do wygenerowania kluczy, za pomocą których narzędzie opakowujące aplikacje może podpisać opakowaną aplikację wyjściową.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    W tym przykładzie za pomocą algorytmu RSA generowana jest para kluczy (klucz publiczny oraz powiązany z nim klucz prywatny o rozmiarze 2048 bitów), a następnie klucz publiczny jest opakowywany w certyfikat z podpisem własnym X.509 v3 przechowywany jako jednoelementowy łańcuch certyfikatów. Ten łańcuch certyfikatów oraz klucz prywatny są przechowywane w nowym wpisie magazynu kluczy o nazwie „mykeystorefile”, określonym za pomocą aliasu „mykeyalias”. Okres ważności wpisu magazynu kluczy wynosi 50 000 dni.

    Polecenie wyświetli monit o wprowadzenie haseł magazynu kluczy oraz klucza. Użyj haseł bezpiecznych i trudnych do odgadnięcia, ale jednocześnie takich, które zapamiętasz, ponieważ będą one później potrzebne do uruchomienia narzędzia opakowującego aplikacje.

    Aby uzyskać więcej informacji, zapoznaj się ze szczegółową dokumentacją narzędzia Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) oraz [magazynu kluczy](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) środowiska Java w witrynie dokumentacji firmy Oracle.

## Krok 2 Instalowanie narzędzia opakowującego aplikacje

1.  Pobierz plik instalacyjny narzędzia opakowującego aplikacje dla systemu Android w usłudze Intune, **InstallAWT.exe**, z [repozytorium w witrynie GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) na komputer z systemem Windows.

2.  Zaakceptuj umowę licencyjną, a następnie ukończ instalację.

Zwróć uwagę na folder, w którym zostało zainstalowane narzędzie. Domyślna lokalizacja: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Krok 3 Uruchamianie narzędzia opakowującego aplikacje

1.  Na komputerze z systemem Windows, na którym zainstalowano narzędzie opakowujące aplikacje, otwórz okno programu PowerShell w trybie administratora.

2.  Z folderu, w którym zostało zainstalowane narzędzie, importuj moduł programu PowerShell narzędzia opakowującego aplikacje:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Uruchom narzędzie za pomocą polecenia **invoke-AppWrappingTool**, używając następującej składni:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 W poniższej tabeli przedstawiono szczegółowo właściwości polecenia **invoke-AppWrappingTool**:

|Właściwość|Informacje|Przykład|
|-------------|--------------------|---------|
|**-InputPath**&lt;ciąg&gt;|Ścieżka źródłowej aplikacji systemu Android (.apk).| |
|**-OutputPath**&lt;ciąg&gt;|Ścieżka do „wyjściowej” aplikacji systemu Android. Jeśli ta ścieżka katalogu będzie taka sama jak określona w parametrze InputPath, opakowywanie nie powiedzie się.| |
|**-KeyStorePath**&lt;ciąg&gt;|Ścieżka do pliku magazynu kluczy, który zawiera pary kluczy publicznych/prywatnych do podpisania.|Domyślnie pliki magazynu kluczy są przechowywane w folderze „C:\Program Files (x86)\Java\jreX.X.X_XX\bin”. |
|**-KeyStorePassword**&lt;ciąg bezpieczny&gt;|Hasło używane do odszyfrowywania magazynu kluczy. System Android wymaga, aby wszystkie pakiety aplikacji (apk) były podpisane. Użyj narzędzia Java Key Tool do wygenerowania klucza KeyStorePassword. Uzyskaj więcej informacji o [magazynie kluczy](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) środowiska Java.| |
|**-KeyAlias**&lt;ciąg&gt;|Nazwa klucza, który ma być używany do podpisywania.| |
|**-KeyPassword**&lt;ciąg bezpieczny&gt;|Hasło używane do odszyfrowania klucza prywatnego, który zostanie użyty do podpisywania.| |
|**-SigAlg**&lt;ciąg bezpieczny&gt;| (Opcjonalnie) Nazwa algorytmu sygnatury używanego do podpisywania. Algorytm musi być zgodny z kluczem prywatnym.|Przykłady: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Opcjonalnie) To polecenie obsługuje typowe parametry programu PowerShell, takie jak verbose, debug itp. |


- Listę typowych parametrów można znaleźć w [Centrum skryptów Microsoft](https://technet.microsoft.com/library/hh847884.aspx).

- Aby uzyskać szczegółowe informacje dotyczące używania tego narzędzia, wpisz polecenie:

    ```
    Help Invoke-AppWrappingTool
    ```

**Przykład:**

Zaimportuj moduł programu PowerShell.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1" 
```
Uruchom narzędzie opakowujące aplikacje z aplikacją natywną **HelloWorld.apk**. 
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Następnie zostanie wyświetlony monit o hasła **KeyStorePassword** i **KeyPassword**. Wprowadź poświadczenia użyte do utworzenia pliku magazynu kluczy.

Opakowana aplikacja zostaje wygenerowana i zapisana wraz z plikiem dziennika w określonej ścieżce danych wyjściowych.

## Uwagi dotyczące zabezpieczeń przy uruchamianiu narzędzia opakowującego aplikacje
Aby uniknąć potencjalnego fałszowania, ujawnienia informacji i ataków opartych na podniesieniu uprawnień:

-   Upewnij się, że wejściowa aplikacja biznesowa, aplikacja wyjściowa i magazyn kluczy Java są na tym samym komputerze, na którym jest uruchamiane narzędzie opakowujące aplikacje.

-   Zaimportuj aplikację wyjściową do konsoli usługi Intune na tym samym komputerze, na którym uruchomiono to narzędzie. Zobacz temat [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html), aby uzyskać więcej informacji dotyczących narzędzia Java keytool.

-   Jeśli aplikacja wyjściowa i narzędzie znajdują się na ścieżce Universal Naming Convention (UNC), a narzędzie i pliki wejściowe nie zostały uruchomione na tym samym komputerze, skonfiguruj środowisko do zabezpieczenia przy użyciu [zabezpieczeń protokołu internetowego (IPsec)](http://en.wikipedia.org/wiki/IPsec) lub [podpisywania bloku komunikatów serwera (SMB)](https://support.microsoft.com/en-us/kb/887429).

-   Upewnij się, że aplikacja pochodzi z zaufanego źródła.

-   Zabezpiecz katalog wyjściowy, który zawiera opakowaną aplikację. Rozważ użycie katalogu poziomu użytkownika dla produktu wyjściowego.



### Zobacz także
- [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


