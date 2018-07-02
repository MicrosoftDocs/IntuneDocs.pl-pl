---
title: Opakowywanie aplikacji systemu Android za pomocą narzędzia opakowującego aplikacje dostępnego w usłudze Intune
description: Dowiedz się, jak opakowywać aplikacje systemu Android bez konieczności zmieniania kodu samej aplikacji. Przygotuj aplikacje tak, aby można było stosować zasady zarządzania aplikacjami mobilnymi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bb94c5a0941dc4f4d626c6316f79d5e4b1f4b551
ms.sourcegitcommit: 91dc50d38be13c65e5d144d237d7c4358089f215
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2018
ms.locfileid: "35679448"
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Przygotowywanie aplikacji systemu Android pod kątem zasad ochrony aplikacji za pomocą narzędzia opakowującego aplikacje usługi Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Za pomocą narzędzia opakowującego aplikacje dla systemu Android w usłudze Microsoft Intune można zmieniać działanie wewnętrznych aplikacji dla systemu Android przez ograniczanie ich funkcji bez konieczności zmieniania kodu aplikacji.

Narzędzie to jest aplikacją wiersza polecenia systemu Windows działającą w programie PowerShell i tworzącą otokę wokół aplikacji dla systemu Android. Po opakowaniu wybranej aplikacji można modyfikować jej funkcje, konfigurując [zasady zarządzania aplikacjami mobilnymi](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) usługi Intune.


Przed uruchomieniem tego narzędzia należy zapoznać się z sekcją [Uwagi dotyczące zabezpieczeń przy uruchamianiu narzędzia opakowującego aplikacje](#security-considerations-for-running-the-app-wrapping-tool). Aby pobrać to narzędzie, przejdź do strony [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) (Narzędzie opakowujące aplikacje dla systemu Android w usłudze Microsoft Intune) w witrynie GitHub.

## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Spełnianie wymagań wstępnych do używania narzędzia opakowującego aplikacje

-   Narzędzie opakowujące aplikacje musi zostać uruchomione na komputerze z systemem Windows 7 lub nowszym.

-   Aplikacja wejściowa musi być prawidłowym pakietem aplikacji Android z rozszerzeniem pliku apk oraz:

    -   nie może być szyfrowana,
    -   nie może być wcześniej opakowana przez narzędzie opakowujące aplikacje usługi Intune,
    -   musi być napisana dla systemu Android 4.0 lub nowszego.

-   Aplikacja musi być opracowana przez Twoją firmę lub dla niej. To narzędzie nie może być używane do przetwarzania aplikacji pobranych ze sklepu Google Play.

-   Aby uruchomić narzędzie opakowujące aplikacje, należy zainstalować najnowszą wersję środowiska [Java Runtime Environment](http://java.com/download/) i upewnić się, że w zmiennych środowiskowych systemu Windows została ustawiona zmienna ścieżki Java C:\ProgramData\Oracle\Java\javapath. Aby uzyskać więcej informacji, zobacz [dokumentację środowiska Java](http://java.com/download/help/).

    > [!NOTE]
    > W pewnych sytuacjach 32-bitowa wersja programu Java może spowodować problemy z pamięcią. Warto zainstalować wersję 64-bitową.

- System Android wymaga, aby wszystkie pakiety aplikacji (apk) były podpisane. Aby uzyskać informacje dotyczące **ponownego używania** istniejących certyfikatów i ogólne wskazówki dotyczące certyfikatów podpisywania, zobacz [Ponowne używanie certyfikatów podpisywania i opakowywanie aplikacji](https://docs.microsoft.com/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps). Plik wykonywalny Java keytool.exe służy do generowania **nowych** poświadczeń wymaganych do podpisania opakowanej aplikacji wyjściowej. Wszelkie ustawiane hasła muszą być bezpieczne, ale zanotuj je, ponieważ będą potrzebne do uruchomienia narzędzia opakowującego aplikacje.

- (Opcjonalnie) Włącz Multidex w aplikacji wejściowej. Czasami aplikacja może osiągnąć limit rozmiaru pliku wykonywalnego Dalvik (DEX) z powodu klas zestawu Intune MAM SDK, które są dodawane podczas opakowywania. Pliki DEX są częścią kompilacji aplikacji systemu Android. W tym scenariuszu najlepszym rozwiązaniem jest włączenie obsługi Multidex w samej aplikacji. W niektórych organizacjach może to wymagać współpracy z osobami kompilującymi aplikację (tj. zespołem zajmującym się kompilacją aplikacji). 

## <a name="install-the-app-wrapping-tool"></a>Instalacja narzędzia opakowującego aplikacje

1.  Pobierz plik instalacyjny narzędzia opakowującego aplikacje dla systemu Android w usłudze Intune, InstallAWT.exe, z [repozytorium w witrynie GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) na komputer z systemem Windows. Otwórz plik instalacyjny.

2.  Zaakceptuj umowę licencyjną, a następnie zakończ instalację.

Zwróć uwagę na folder, w którym zostało zainstalowane narzędzie. Domyślna lokalizacja: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Uruchamianie narzędzia opakowującego aplikacje

1. Na komputerze z systemem Windows z zainstalowanym narzędziem opakowującym aplikacje otwórz okno programu PowerShell.

2. Z folderu, w którym zostało zainstalowane narzędzie, zaimportuj moduł programu PowerShell narzędzia opakowującego aplikacje:

   ```
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Uruchom narzędzie za pomocą polecenia **invoke-AppWrappingTool**, używając następującej składni:
   ```
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   W poniższej tabeli przedstawiono szczegółowo właściwości polecenia **invoke-AppWrappingTool**:

|Właściwość|Informacje|Przykład|
|-------------|--------------------|---------|
|**-InputPath**&lt;ciąg&gt;|Ścieżka źródłowej aplikacji systemu Android (.apk).| |
 |**-OutputPath**&lt;ciąg&gt;|Ścieżka do wyjściowej aplikacji systemu Android. Jeśli ta ścieżka katalogu będzie taka sama jak określona w parametrze InputPath, opakowywanie nie powiedzie się.| |
|**-KeyStorePath**&lt;ciąg&gt;|Ścieżka do pliku magazynu kluczy, który zawiera pary kluczy publicznych/prywatnych do podpisania.|Domyślnie pliki magazynu kluczy są przechowywane w folderze „C:\Program Files (x86)\Java\jreX.X.X_XX\bin”. |
|**-KeyStorePassword**&lt;ciąg_bezpieczny&gt;|Hasło używane do odszyfrowywania magazynu kluczy. System Android wymaga, aby wszystkie pakiety aplikacji (apk) były podpisane. Użyj narzędzia Java keytool do wygenerowania wartości KeyStorePassword. Uzyskaj więcej informacji o [magazynie kluczy](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) środowiska Java.| |
|**-KeyAlias**&lt;ciąg&gt;|Nazwa klucza, który ma być używany do podpisywania.| |
|**-KeyPassword**&lt;ciąg_bezpieczny&gt;|Hasło używane do odszyfrowania klucza prywatnego, który zostanie użyty do podpisywania.| |
|**-SigAlg**&lt;ciąg_bezpieczny&gt;| (Opcjonalnie) Nazwa algorytmu sygnatury używanego do podpisywania. Algorytm musi być zgodny z kluczem prywatnym.|Przykłady: SHA256withRSA, SHA1withRSA|
| **&lt;typowe_parametry&gt;** | (Opcjonalnie) To polecenie obsługuje typowe parametry programu PowerShell, takie jak verbose i debug. |


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
Uruchom narzędzie opakowujące aplikacje z aplikacją natywną HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Zostanie wyświetlony monit o hasła **KeyStorePassword** i **KeyPassword**. Wprowadź poświadczenia użyte do utworzenia pliku magazynu kluczy.

Opakowana aplikacja zostanie wygenerowana i zapisana wraz z plikiem dziennika w określonej ścieżce danych wyjściowych.

## <a name="how-often-should-i-rewrap-my-android-application-with-the-intune-app-wrapping-tool"></a>Jak często należy ponownie opakowywać aplikację systemu Android za pomocą narzędzia opakowującego aplikacje usługi Intune?
Główne scenariusze, w których trzeba będzie ponownie opakować aplikacje:
* Sama aplikacja wydała nową wersję. Poprzednia wersja aplikacji została opakowana i przekazana do konsoli usługi Intune.
* Narzędzie opakowujące aplikacje usługi Intune dla systemu Android wydało nową wersję, która oferuje kluczowe poprawki usterek i nowe funkcje zasad ochrony aplikacji, przeznaczone specjalnie dla usługi Intune. Taka sytuacja występuje co 6–8 tygodni za pośrednictwem repozytorium GitHub dla [narzędzia opakowującego aplikacje usługi Intune dla systemu Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android).

Niektóre najlepsze rozwiązania dotyczące ponownego opakowywania: 
* Obsługa certyfikatów podpisywania używanych podczas procesu kompilacji, zobacz [Ponowne używanie certyfikatów podpisywania i opakowywanie aplikacji](https://docs.microsoft.com/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps)

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>Ponowne używanie certyfikatów podpisywania i opakowywanie aplikacji
System Android wymaga podpisania wszystkich aplikacji za pomocą ważnego certyfikatu przed zainstalowaniem ich na urządzeniach z systemem Android.

Opakowane aplikacje mogą zostać podpisane podczas procesu opakowywania lub *po* tym procesie przy użyciu istniejących narzędzi do podpisywania. Wszystkie informacje dotyczące podpisywania znajdujące się w aplikacji przed jej opakowaniem zostaną odrzucone. Jeśli to możliwe, podczas procesu opakowywania należy użyć informacji dotyczących podpisywania, które zostały wcześniej użyte podczas procesu kompilacji. W niektórych organizacjach może to wymagać współpracy z właścicielami informacji o magazynie kluczy (tj. zespołem zajmującym się kompilacją aplikacji). 

Jeśli poprzedni certyfikat podpisywania nie może zostać użyty lub aplikacja nie została wcześniej wdrożona, możliwe jest utworzenie nowego certyfikatu podpisywania, zgodnie z instrukcjami znajdującymi się w [przewodniku dewelopera systemu Android](https://developer.android.com/studio/publish/app-signing.html#signing-manually).

Jeśli aplikacja została wcześniej wdrożona za pomocą innego certyfikatu podpisywania, nie można przekazać jej do usługi Intune po uaktualnieniu. Scenariusze uaktualniania aplikacji nie będą miały zastosowania, jeśli aplikacja została podpisana za pomocą innego certyfikatu niż ten, który został użyty podczas jej kompilacji. W związku z tym wszelkie nowe certyfikaty podpisywania powinny zostać zachowane na potrzeby uaktualnień aplikacji. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Uwagi dotyczące zabezpieczeń przy uruchamianiu narzędzia opakowującego aplikacje
Aby uniknąć potencjalnego fałszowania, ujawnienia informacji i ataków opartych na podniesieniu uprawnień:

-   Upewnij się, że wejściowa aplikacja biznesowa, aplikacja wyjściowa i magazyn kluczy środowiska Java są na tym samym komputerze, na którym jest uruchamiane narzędzie opakowujące aplikacje.

-   Zaimportuj aplikację wyjściową do usługi Intune na tym samym komputerze, na którym uruchomiono to narzędzie. Zobacz temat [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html), aby uzyskać więcej informacji o narzędziu Java keytool.

-   Jeśli aplikacja wyjściowa i narzędzie znajdują się w ścieżce Universal Naming Convention (UNC), a narzędzie i pliki wejściowe nie zostały uruchomione na tym samym komputerze, skonfiguruj zabezpieczenia środowiska, używając [zabezpieczeń protokołu internetowego (IPsec)](http://wikipedia.org/wiki/IPsec) lub [podpisywania bloku komunikatów serwera (SMB)](https://support.microsoft.com/kb/887429).

-   Upewnij się, że aplikacja pochodzi z zaufanego źródła.

-   Zabezpiecz katalog wyjściowy, który zawiera opakowaną aplikację. Rozważ użycie katalogu poziomu użytkownika dla produktu wyjściowego.

## <a name="requiring-user-login-prompt-for-an-automatic-app-we-service-enrollment-requiring-intune-app-protection-policies-in-order-to-use-your-wrapped-android-lob-app-and-enabling-adal-sso-optional"></a>Wymaganie monitu logowania użytkownika na potrzeby automatycznej rejestracji w usłudze APP-WE, wymaganie zasad ochrony aplikacji usługi Intune w celu korzystania z opakowanej aplikacji LOB dla systemu Android i włączanie logowania jednokrotnego do biblioteki ADAL (opcjonalnie)

Poniżej przedstawiono wskazówki dotyczące wymagania monitowania użytkownika podczas uruchamiania aplikacji w celu automatycznej rejestracji w usłudze APP-WE (w tej sekcji nazywanej **rejestracją domyślną**) oraz wymagania zasad ochrony aplikacji usługi Intune, aby umożliwić używanie opakowanej aplikacji LOB dla systemu Android tylko chronionym użytkownikom usługi Intune. Omówiono również sposób włączenia logowania jednokrotnego w przypadku opakowanej aplikacji LOB dla systemu Android. 

> [!NOTE] 
> Korzyści wynikające z **rejestracji domyślnej** obejmują uproszczone uzyskiwanie zasad z usługi APP-WE dla aplikacji na urządzeniu.

### <a name="general-requirements"></a>Wymagania ogólne
* Zespół zestawu SDK usługi Intune będzie wymagać identyfikatora Twojej aplikacji. Można go znaleźć za pośrednictwem witryny [Azure Portal](https://portal.azure.com/) w obszarze **Wszystkie aplikacje** w kolumnie **Identyfikator aplikacji**. Dobrym sposobem na skontaktowanie się z zespołem zestawu SDK usługi Intune jest wysłanie wiadomości e-mail na adres msintuneappsdk@microsoft.com.
     
### <a name="working-with-the-intune-sdk"></a>Korzystanie z zestawu SDK usługi Intune
Te instrukcje dotyczą wszystkich aplikacji Android i Xamarin, w przypadku których chcesz wymagać zasad ochrony aplikacji usługi Intune do użycia na urządzeniu użytkownika końcowego.

1. Skonfiguruj bibliotekę ADAL, korzystając z kroków zdefiniowanych w [przewodniku zestawu SDK usługi Intune dla systemu Android](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).

> [!NOTE]
> Termin „identyfikator klienta” związany z Twoją aplikacją jest taki sam jak termin „identyfikator aplikacji” w witrynie Azure Portal związany z Twoją aplikacją. 
> * Aby włączyć logowanie jednokrotne, skorzystaj z typowej konfiguracji biblioteki ADAL nr 2.

2. Włącz rejestrację domyślną przez umieszczenie w manifeście następującej wartości: ```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
   > [!NOTE] 
   > Musi to być jedyna integracja z usługą MAM-WE w aplikacji. Wszelkie inne próby wywołania interfejsów API MAMEnrollmentManager mogą powodować konflikty.

3. Włącz wymagane zasady zarządzania aplikacjami mobilnymi przez umieszczenie w manifeście następującej wartości: ```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
   > [!NOTE] 
   > Wymusi to na użytkowniku pobranie aplikacji Portal firmy na urządzenie i ukończenie przepływu rejestracji domyślnej przed użyciem.

### <a name="see-also"></a>Zobacz też
- [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](apps-prepare-mobile-application-management.md)

- [Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android](app-sdk-android.md)
