---
title: "Opakowywanie aplikacji systemu Android za pomocą narzędzia opakowującego aplikacje | Microsoft Intune"
description: "Ten temat przedstawia informacje o sposobie opakowywania aplikacji systemu Android bez konieczności modyfikacji kodu samej aplikacji. Przygotuj aplikacje tak, aby można było stosować zasady zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 15d0877f799c89e2a8af65c416c0e914f898641f


---

# Przygotowanie aplikacji systemu Android do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Intune
Za pomocą **narzędzia opakowującego aplikacje dla systemu Android w usłudze Microsoft Intune** można modyfikować działanie wewnętrznych aplikacji dla systemu Android, aby umożliwić konfigurację funkcji aplikacji bez konieczności modyfikacji kodu samej aplikacji.

Narzędzie to jest aplikacją wiersza polecenia systemu Windows działającą w programie PowerShell i tworzy „otokę” wokół aplikacji. Po przetworzeniu wybranej aplikacji można modyfikować jej funkcje, korzystając ze skonfigurowanych przez siebie [zasad zarządzania aplikacjami mobilnymi usługi](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

Jeśli aplikacja używa biblioteki Azure Active Directory Authentication Library (ADAL), przed opakowaniem aplikacji należy wykonać czynności podane w sekcji [Jak opakowywać aplikacje korzystające z biblioteki usługi Azure Active Directory](#how-to-wrap-apps-that-use-the-azure-active-directory-library). Jeśli nie wiesz, czy Twoja aplikacja korzysta z tej biblioteki, skontaktuj się z deweloperem.

Przed uruchomieniem tego narzędzia należy zapoznać się z sekcją [Uwagi dotyczące zabezpieczeń przy uruchamianiu narzędzia opakowującego aplikacje](#security-considerations-for-running-the-app-wrapping-tool). Aby pobrać to narzędzie, zobacz [Microsoft Intune App Wrapping Tool for Android](https://www.microsoft.com/download/details.aspx?id=47267) (Narzędzie opakowujące aplikacje dla systemu Android w usłudze Microsoft Intune).

## Krok 1 Spełnianie wymagań wstępnych dotyczących używania narzędzia opakowującego aplikacje

-   Narzędzie opakowujące aplikacje musi zostać uruchomione na komputerze z systemem Windows 7 lub nowszym.

-   Aplikacja wejściowa musi być prawidłowym pakietem aplikacji Android z plikiem o rozszerzeniu **.apk** oraz:

    -   nie może być szyfrowana,

    -   nie może wcześniej być opakowana przez narzędzie opakowujące aplikacje,

    -   musi być napisana dla systemu Android 4.0 lub nowszego,

-   aplikacja musi być opracowana przez Twoją firmę lub dla niej. To narzędzie nie może być używane do przetwarzania aplikacji pobranych ze sklepu Google Play.

-   Aby uruchomić narzędzie opakowujące aplikacje, należy zainstalować najnowszą wersję programu [Java Runtime Environment](http://java.com/download/) i upewnić się, że w zmiennych środowiskowych systemu Windows została ustawiona zmienna ścieżki Java **C:\ProgramData\Oracle\Java\javapath**. Aby uzyskać więcej informacji, zobacz [dokumentację programu Java](http://java.com/download/help/).

    > [!NOTE]
    > W pewnych sytuacjach 32-bitowa wersja programu Java może spowodować problemy z pamięcią. Zaleca się zainstalowanie wersji 64-bitowej.

## Krok 2 Instalowanie narzędzia opakowującego aplikacje

1.  Pobierz plik instalacyjny narzędzia opakowującego aplikacje z Centrum pobierania Microsoft, a następnie otwórz go na komputerze z systemem Windows.

2.  Zaakceptuj umowę licencyjną, a następnie ukończ instalację.

Zwróć uwagę na folder, w którym zostało zainstalowane narzędzie. Domyślna lokalizacja: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Krok 3 Uruchamianie narzędzia opakowującego aplikacje

1.  Na komputerze z systemem Windows, na którym zainstalowano narzędzie opakowujące aplikacje, otwórz okno programu PowerShell w trybie administratora.

2.  Z folderu, w którym zostało zainstalowane narzędzie, importuj moduł programu PowerShell narzędzia opakowującego aplikacje:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Uruchom narzędzie przy użyciu polecenia **invoke-AppWrappingTool** wraz z następującymi parametrami. Parametry oznaczone jako opcjonalne są przeznaczone dla aplikacji, które używają biblioteki Azure Active Directory Authentication Library (ADAL). Aby uzyskać więcej informacji, zobacz [Jak opakowywać aplikacje korzystające z biblioteki usługi Azure Active Directory](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

|Parametr|Więcej informacji|Przykłady|
|-------------|--------------------|---------|
|**-InputPath**&lt;ciąg&gt;|Ścieżka źródłowej aplikacji systemu Android (.apk).| |
|**-OutputPath**&lt;ciąg&gt;|Ścieżka do „wyjściowej” aplikacji systemu Android. Jeśli ta ścieżka katalogu będzie taka sama jak określona w parametrze InputPath, opakowywanie nie powiedzie się.| |
|**-KeyStorePath**&lt;ciąg&gt;|Ścieżka do pliku magazynu kluczy, który zawiera pary kluczy publicznych/prywatnych do podpisania.| |
|**-KeyStorePassword**&lt;ciąg bezpieczny&gt;|Hasło używane do odszyfrowywania magazynu kluczy. System Android wymaga, aby wszystkie pakiety aplikacji (apk) były podpisane. Użyj narzędzia Java Key Tool do wygenerowania klucza KeyStorePassword, jak pokazano w przykładzie. Więcej informacji o [magazynie kluczy](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;ciąg&gt;|Nazwa klucza, który ma być używany do podpisywania.| |
|**-KeyPassword**&lt;ciąg bezpieczny&gt;|Hasło używane do odszyfrowania klucza prywatnego, który zostanie użyty do podpisywania.| |
|**-SigAlg**&lt;ciąg bezpieczny&gt;|Nazwa algorytmu sygnatury używanego do podpisywania. Algorytm musi być zgodny z kluczem prywatnym.|Przykłady: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;identyfikator GUID&gt;|Identyfikator klienta usługi Azure Active Directory aplikacji wejściowej (opcjonalnie).| |
|**-AuthorityURI**&lt;identyfikator URI&gt;|Identyfikator URI uwierzytelniania usługi Azure Active Directory aplikacji wejściowej (opcjonalnie).| |
|**-SkipBroker**&lt;wartość logiczna&gt;|Wskazuje, czy aplikacja wejściowa obsługuje na całym urządzeniu funkcję jednokrotnego logowania obsługiwanego przez brokera (opcjonalnie). |Wartość **true** — aplikacja wejściowa nie obsługuje jednokrotnego logowania obsługiwanego przez brokera na całym urządzeniu. Użyj parametru NonBrokerRedirectURI. Wartość **false** — aplikacja wejściowa obsługuje jednokrotne logowanie obsługiwane przez brokera na całym urządzeniu|
|**-NonBrokerRedirectURI**&lt;identyfikator URI&gt;|Identyfikator URI przekierowania usługi Azure Active Directory do użycia, jeśli parametr SkipBroker ma wartość true (opcjonalnie).|  |


**&lt;CommonParameters&gt;**
 (opcjonalne — obsługuje typowe parametry programu PowerShell, takie jak verbose, debug itp.)

- Listę typowych parametrów można znaleźć w [Centrum skryptów Microsoft](https://technet.microsoft.com/library/hh847884.aspx).

- Aby wyświetlić pomoc dla tego narzędzia, wpisz polecenie:

    ```
    Help Invoke-AppWrappingTool
    ```
- Aby dowiedzieć się więcej o integracji z usługą Azure Active Directory (AAD), zobacz [Jak opakowywać aplikacje korzystające z biblioteki usługi Azure Active Directory](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Przykład:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

Następnie zostanie wyświetlony monit o hasła **KeyStorePassword** i **KeyPassword**.

Opakowana aplikacja zostaje wygenerowana i zapisana wraz z plikiem dziennika w określonej ścieżce danych wyjściowych.

## Uwagi dotyczące zabezpieczeń przy uruchamianiu narzędzia opakowującego aplikacje
Aby uniknąć potencjalnego fałszowania, ujawnienia informacji i ataków opartych na podniesieniu uprawnień:

-   Upewnij się, że wejściowa aplikacja LOB, aplikacja wyjściowa i Java KeyStore są na tym samym komputerze, na którym jest uruchomione narzędzie opakowujące aplikacje.

-   Importuj aplikację wyjściową do konsoli usługi Intune na tym samym komputerze, na którym uruchomiono to narzędzie. Zobacz temat [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html), aby uzyskać więcej informacji dotyczących narzędzia Java keytool.

-   Jeśli aplikacja wyjściowa i narzędzie znajdują się na ścieżce Universal Naming Convention (UNC), a narzędzie i pliki wejściowe nie zostały uruchomione na tym samym komputerze, skonfiguruj środowisko do zabezpieczenia przy użyciu [zabezpieczeń protokołu internetowego (IPsec)](http://en.wikipedia.org/wiki/IPsec) lub [podpisywania bloku komunikatów serwera (SMB)](https://support.microsoft.com/en-us/kb/887429).

-   Upewnij się, czy aplikacja jest pochodzi z zaufanego źródła, zwłaszcza, jeśli używasz usługi Azure Active Directory (AAD), która może umożliwić aplikacji dostęp do tokenu AAD w czasie wykonywania.

-   Zabezpiecz katalog wyjściowy, który zawiera opakowaną aplikację. Rozważ użycie katalogu poziomu użytkownika dla produktu wyjściowego.

## Jak opakowywać aplikacje korzystające z biblioteki usługi Azure Active Directory
Jeśli aplikacja korzysta z biblioteki Azure Active Directory Authentication Library (ADAL), przed opakowaniem aplikacji należy wykonać następujące kroki:

### Krok 1 Upewnienie się, że spełnione są wymagania dotyczące biblioteki ADAL
W przypadku aplikacji korzystających z bibliotek ADAL muszą być spełnione następujące warunki:

-   Aplikacja musi mieć zintegrowaną wersję bibliotek ADAL 1.0.2 lub nowszą.

-   Deweloperzy muszą udzielić dostępu aplikacji do zasobu zarządzania aplikacjami mobilnymi usługi Intune zgodnie z opisem zamieszczonym w sekcji [Krok 3 Konfigurowanie dostępu do zarządzania aplikacjami mobilnymi w usłudze Azure Active Directory (AAD)](#step-3-configure-access-to-mobile-app-management-in-aad).

### Krok 2 Przeglądanie identyfikatorów, które należy uzyskać podczas rejestrowania aplikacji
W następnym kroku portal zarządzania platformy Azure będzie używany do rejestrowania aplikacji (które korzystają z bibliotek ADAL w usłudze Azure Active Directory, AAD) w celu uzyskania unikatowych identyfikatorów wymienionych w tabeli poniżej. Następnie przekażesz identyfikatory deweloperowi po zintegrowaniu biblioteki ADAL z aplikacją.

|Identyfikator|Więcej informacji|Wartość domyślna|
|--------------|--------------------|-----------------|
|**Identyfikator klienta**|Unikatowy identyfikator GUID generowany dla aplikacji po jej zarejestrowaniu w usłudze AAD.<br /><br />Jeśli znasz identyfikator klienta aplikacji, podaj tę wartość. W przeciwnym razie użyj wartości domyślnej.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Identyfikator URI urzędu**|Wartości identyfikatora URI urzędu dla obiektów usługi AAD (na przykład użytkowników i grup).<br /><br />Parametr AuthorityURI jest opcjonalny dla  narzędzia opakowującego aplikacje. Jeśli parametr nie zostanie użyty, używany będzie domyślny identyfikator URI.||
|**SkipBroker**|Wartość wskazująca, czy portal firmy będzie używana jako broker.<br /><br />**True** — portal firmy nie będzie używany do uwierzytelniania ADAL.<br /><br />**False** — portal firmy będzie używany do uwierzytelniania ADAL. Portal firmy korzysta z zarejestrowanego użytkownika do celów logowania jednokrotnego.||
|**Identyfikator URI przekierowania bez brokera**|Identyfikator URI do użycia, kiedy biblioteka ADAL nie korzysta z aplikacji brokera (portalu firmy w usłudze Intune).|urn:ietf:wg:oauth:2.0:oob|
|**Identyfikator zasobu**|Wskaźnik do zasobów aplikacji w usłudze AAD.||

### Krok 3 Konfigurowanie dostępu do zarządzania aplikacjami mobilnymi w usłudze AAD
Zanim będzie możliwe użycie w narzędziu opakowującym aplikacje wartości uzyskanych przy rejestracji aplikacji w usłudze AAD, deweloper aplikacji musi umożliwić tej aplikacji dostęp do zasobu zarządzania aplikacjami mobilnymi w usłudze Intune, wykonując następujące kroki:

1.  Zaloguj się do istniejącego konta usługi AAD w portalu zarządzania platformy Azure.

2.  Wybierz pozycję **Rejestracja istniejącej aplikacji LOB**.

3.  W sekcji **konfiguracji** wybierz opcję **Konfigurowanie dostępu do interfejsów API sieci Web w innych aplikacjach**.

4.  Z pierwszej listy rozwijanej w sekcji **Uprawnienia do innych aplikacji** wybierz pozycję **Zarządzanie aplikacjami mobilnymi w usłudze Intune**.

Po wykonaniu tych czynności można użyć identyfikatora klienta aplikacji w narzędziu opakowującym aplikacje. Identyfikator klienta można znaleźć w portalu zarządzania usługi Azure Active Directory zgodnie z opisem w tabeli [Krok 2 Przeglądanie identyfikatorów, które należy uzyskać podczas rejestrowania aplikacji](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app).

### Krok 4 Używanie wartości identyfikatorów usługi AAD w narzędziu opakowującym aplikacje
Używając wartości identyfikatora otrzymanych w procesie rejestracji, wprowadź wartości jako właściwości wiersza polecenia w narzędziu opakowującym aplikacje. Należy określić wszystkie wartości w tabeli, aby użytkownicy końcowi mogli pomyślnie uwierzytelnić aplikację. Jeśli wartość nie zostanie określona, używane będą wartości domyślne.

|Identyfikator|Parametr|
|--------------|-------------|
|Identyfikator klienta|ClientID|
|Identyfikator URI urzędu|Authority-URI|
|SkipBroker|SkipBroker|
|Identyfikator URI przekierowania bez brokera|NonBrokerRedirectURI|
|Identyfikator zasobu|ResourceID|
Podczas opakowywania aplikacji trzeba mieć na uwadze następujące kwestie:

-   Aby sprawdzić, czy uwierzytelnianie zakończyło się powodzeniem, usługa [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pobiera token AAD skojarzony z identyfikatorem zasobu zarządzania aplikacjami mobilnymi. Nie jest on jednak używany w żadnym wywołaniu, które umożliwiłoby zweryfikowanie prawidłowości tokenu. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] odczytuje jedynie nazwę UPN zalogowanego użytkownika w celu określenia dostępu do aplikacji. Token usługi AAD nie jest używany w żadnych późniejszych wywołaniach usług.

-   Podanie identyfikatora klienta oraz identyfikatora URI uwierzytelniania aplikacji zapobiega dwukrotnemu monitowaniu o zalogowanie. Zarejestrowanie tego identyfikatora klienta jest konieczne w celu uzyskania dostępu do opublikowanego identyfikatora zasobu zarządzania aplikacjami mobilnymi w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] na pulpicie nawigacyjnym usługi AAD. Jeśli nie zarejestrujesz identyfikatora klienta, użytkownicy zobaczą błąd logowania po uruchomieniu aplikacji.


### Zobacz także
- [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


