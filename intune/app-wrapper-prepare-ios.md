---
title: Opakowywanie aplikacji systemu iOS za pomocą narzędzia opakowującego aplikacje dostępnego w usłudze Intune
description: Dowiedz się, jak opakowywać aplikacje systemu iOS bez konieczności zmieniania kodu samej aplikacji. Przygotuj aplikacje tak, aby można było stosować zasady zarządzania aplikacjami mobilnymi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: edbd802b5f0482fc5dbaa801308447e2f8061189
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="prepare-ios-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Przygotowywanie aplikacji systemu iOS pod kątem zasad ochrony aplikacji za pomocą narzędzia opakowującego aplikacje usługi Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Za pomocą dostępnego w usłudze Microsoft Intune narzędzia opakowującego aplikacje dla systemu iOS można włączyć zasady ochrony aplikacji w usłudze Intune dla wewnętrznych aplikacji systemu iOS bez konieczności zmieniania kodu aplikacji.

Narzędzie to jest aplikacją wiersza polecenia systemu Mac OS, tworzącą „otokę” dla aplikacji. Po przetworzeniu aplikacji można zmienić funkcje aplikacji przez wdrożenie w niej [zasad ochrony aplikacji](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console).

Aby pobrać narzędzie, zobacz temat [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) (Narzędzie opakowujące aplikacje usługi Microsoft Intune dla systemu iOS) w serwisie GitHub.



## <a name="general-prerequisites-for-the-app-wrapping-tool"></a>Ogólne wymagania wstępne dotyczące narzędzia opakowującego aplikacje

Przed uruchomieniem narzędzia opakowującego aplikacje należy spełnić pewne ogólne wymagania wstępne:

* Pobierz [narzędzie opakowujące aplikacje usługi Microsoft Intune dla systemu iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) z witryny GitHub.

* Komputer z systemem macOS X 10.8.5 lub nowszym z zainstalowanym zestawem narzędzi Xcode w wersji 5 lub nowszej.

* Aplikacje wejściowe systemu iOS muszą być opracowane i podpisane przez Twoją firmę lub niezależnego dostawcę oprogramowania.

  * Plik aplikacji wejściowej musi mieć rozszerzenie **ipa** lub **app**.

  * Aplikacja wejściowa musi być skompilowana dla systemu iOS 8.0. lub nowsza wersja.

  * Aplikacja wejściowa nie może być zaszyfrowana.

  * Aplikacja wejściowa nie może mieć rozszerzonych atrybutów pliku.

  * Aplikacja wejściowa musi mieć ustawione uprawnienia, aby mogła zostać przetworzona przez narzędzie opakowujące aplikacje usługi Intune. [Uprawnienia](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/EntitlementKeyReference/Chapters/AboutEntitlements.html) zapewniają aplikacji dodatkowe możliwości poza tymi, które są zwykle przyznawane. Instrukcje można znaleźć w artykule [Ustawienie uprawnień dla aplikacji](#setting-app-entitlements).

## <a name="apple-developer-prerequisites-for-the-app-wrapping-tool"></a>Wymagania wstępne dotyczące narzędzia opakowującego aplikacje dla deweloperów firmy Apple

Aby można było rozpowszechniać opakowane aplikacje wyłącznie wśród użytkowników w organizacji, musisz mieć konto w ramach programu [Apple Developer Enterprise Program](https://developer.apple.com/programs/enterprise/) i jednostki podpisywania aplikacji połączone z kontem dewelopera firmy Apple.

Aby dowiedzieć się więcej na temat wewnętrznego rozpowszechniania aplikacji systemu iOS wśród użytkowników organizacji, przeczytaj oficjalny przewodnik [rozpowszechniania aplikacji w ramach programu Apple Developer Enterprise Program](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/DistributingEnterpriseProgramApps/DistributingEnterpriseProgramApps.html#//apple_ref/doc/uid/TP40012582-CH33-SW1).

Do rozpowszechniania aplikacji opakowanych przez usługę Intune są potrzebne następujące elementy:

* Konto dewelopera w ramach programu Apple Developer Enterprise Program.

* Certyfikat podpisywania dystrybucji wewnętrznej i tymczasowej z prawidłowym identyfikatorem zespołu.

  * Jako parametru narzędzia opakowującego aplikacje usługi Intune należy użyć skrótu SHA1 certyfikatu podpisywania.


* Profil aprowizacji dystrybucji wewnętrznej.

### <a name="steps-to-create-an-apple-developer-enterprise-account"></a>Procedura tworzenia konta programu Apple Developer Enterprise
1. Przejdź do [witryny programu Apple Developer Enterprise Program](https://developer.apple.com/programs/enterprise/).

2. W prawym górnym rogu strony kliknij przycisk **Enroll** (Zarejestruj).

3. Przeczytaj listę kontrolną z wymaganiami dotyczącymi rejestracji. Kliknij przycisk **Start Your Enrollment** (Rozpocznij rejestrację) u dołu strony.

4. **Zaloguj się** przy użyciu konta Apple ID organizacji. Jeśli nie masz konta, kliknij przycisk **Create Apple ID** (Utwórz konto Apple ID).

5. Wybierz wartość w polu **Entity Type** (Typ jednostki) i kliknij przycisk **Continue** (Kontynuuj).

6. Wypełnij formularz z informacjami o organizacji. Kliknij przycisk **Kontynuuj**. Firma Apple skontaktuje się z Tobą w celu potwierdzenia, że masz uprawnienia do rejestracji organizacji.

8. Po zakończeniu weryfikacji kliknij przycisk **Agree to License** (Akceptuj postanowienia licencyjne).

9. Po zaakceptowaniu postanowień licencji **kup i aktywuj program**, aby zakończyć.

10. Jeśli jesteś agentem zespołu (osobą, która dołącza do programu Apple Developer Enterprise Program w imieniu organizacji), najpierw zaproś członków zespołu i przypisz role, aby utworzyć zespół. Aby dowiedzieć się, jak zarządzać zespołem, zapoznaj się z dokumentacją firmy Apple dotyczącą [zarządzania zespołem konta dewelopera](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/ManagingYourTeam/ManagingYourTeam.html#//apple_ref/doc/uid/TP40012582-CH16-SW1).

### <a name="steps-to-create-an-apple-signing-certificate"></a>Procedura tworzenia certyfikatu podpisywania firmy Apple

1. Przejdź do [portalu dla deweloperów firmy Apple](https://developer.apple.com/).

2. W prawym górnym rogu strony kliknij pozycję **Account** (Konto).

3. **Zaloguj się** za pomocą konta Apple ID organizacji.

4. Kliknij pozycję **Certificates, IDs & Profiles** (Certyfikaty, identyfikatory i profile).

   ![Portal dla deweloperów firmy Apple](./media/iOS-signing-cert-1.png)

5. Kliknij kartę ![znak plus w portalu dla deweloperów firmy Apple](./media/iOS-signing-cert-2.png) w prawym górnym rogu, aby dodać certyfikat systemu iOS.

6. Utwórz certyfikat **wewnętrzny i tymczasowy** w obszarze **Production** (Produkcja).

   ![Wybieranie certyfikatu wewnętrznego i tymczasowego](./media/iOS-signing-cert-3.png)

   >[!NOTE]
   >Jeśli nie planujesz dystrybuować aplikacji i chcesz ją tylko przetestować wewnętrznie, możesz skorzystać z certyfikatu iOS App Development zamiast certyfikatu Production. Jeśli używasz certyfikatu deweloperskiego, upewnij się, że profil aprowizowania dla urządzeń przenośnych odwołuje się do urządzeń, na których aplikacja ma być instalowana.

7. Kliknij pozycję **Next** (Dalej) w dolnej części strony.

8. Przeczytaj instrukcje dotyczące tworzenia **żądania podpisania certyfikatu (CSR)** za pomocą aplikacji Dostęp do pęku kluczy na komputerze z systemem MacOS.

   ![Przeczytaj instrukcje dotyczące tworzenia żądania CSR](./media/iOS-signing-cert-4.png)

9. Postępuj zgodnie z powyższymi instrukcjami, aby utworzyć żądanie podpisania certyfikatu. Na komputerze z systemem MacOS uruchom aplikację **dostępu łańcucha kluczy**.

10. W menu systemu macOS u góry ekranu przejdź do pozycji **Dostęp do pęku kluczy > Asystent certyfikatów > Wniosek o wydanie certyfikatu z urzędu certyfikacji**.  

    ![Wniosek o wydanie certyfikatu z urzędu certyfikacji w aplikacji Dostęp do pęku kluczy](./media/iOS-signing-cert-5.png)

11. Postępuj zgodnie z powyższymi instrukcjami w witrynie dla deweloperów firmy Apple dotyczącymi tworzenia pliku CSR. Zapisz plik CSR na komputerze z systemem macOS.

    ![Wniosek o wydanie certyfikatu z urzędu certyfikacji w aplikacji Dostęp do pęku kluczy](./media/iOS-signing-cert-6.png)

12. Wróć do witryny dla deweloperów firmy Apple. Kliknij przycisk **Kontynuuj**. Następnie przekaż plik CSR.

13. Firma Apple wygeneruje certyfikat podpisywania. Pobierz i zapisz go w łatwej do zapamiętania lokalizacji na komputerze z systemem macOS.

    ![Pobieranie certyfikatu podpisywania](./media/iOS-signing-cert-7.png)

14. Kliknij dwukrotnie pobrany właśnie plik certyfikatu, aby dodać certyfikat do łańcucha kluczy.

15. Ponownie otwórz aplikację **Dostęp do pęku kluczy**. Zlokalizuj swój certyfikat, wyszukując jego nazwę na pasku wyszukiwania u góry z prawej strony. Kliknij element prawym przyciskiem myszy, aby wyświetlić menu, i kliknij pozycję **Informacje**. Na ekranach przykładowych używamy certyfikatu deweloperskiego zamiast certyfikatu produkcyjnego.

    ![Dodawanie certyfikatu do łańcucha kluczy](./media/iOS-signing-cert-8.png)

16. Zostanie wyświetlone okno z informacjami. Przewiń do dołu i przejdź do etykiety **Skróty kluczy**. Skopiuj ciąg **SHA1** (rozmyty) do użytku jako argument „-c” dla narzędzia opakowującego aplikacje.

    ![Dodawanie certyfikatu do łańcucha kluczy](./media/iOS-signing-cert-9.png)



### <a name="steps-to-create-an-in-house-distribution-provisioning-profile"></a>Procedura tworzenia profilu aprowizacji dystrybucji wewnętrznej

1. Wróć do [portalu konta dewelopera firmy Apple](https://developer.apple.com/account/) i **zaloguj się** przy użyciu konta Apple ID organizacji.

2. Kliknij pozycję **Certificates, IDs & Profiles** (Certyfikaty, identyfikatory i profile).

3. Kliknij kartę ![znak plus w portalu dla deweloperów firmy Apple](./media/iOS-signing-cert-2.png) w prawym górnym rogu, aby dodać profil aprowizacji systemu iOS.

4. Utwórz profil aprowizacji **In House** (Wewnętrzny) w obszarze **Distribution** (Dystrybucja).

   ![Wybieranie wewnętrznego profilu aprowizacji](./media/iOS-provisioning-profile-1.png)

5. Kliknij przycisk **Kontynuuj**. Upewnij się, że wcześniej wygenerowany certyfikat podpisywania zostanie połączony z profilem aprowizacji.

6. Wykonaj procedurę pobierania profilu (z rozszerzeniem mobileprovision) na komputer z systemem macOS.

7. Zapisz plik w łatwej do zapamiętania lokalizacji. Ten plik zostanie użyty jako parametr -p podczas korzystania z narzędzia opakowującego aplikacje.



## <a name="download-the-app-wrapping-tool"></a>Pobieranie narzędzia opakowującego aplikacje

1.  Pobierz pliki narzędzia opakowującego aplikacje z serwisu [GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) na komputer z systemem macOS.

2.  Kliknij dwukrotnie plik **Microsoft Intune App Wrapping Tool for iOS.dmg**. Zostanie wyświetlone okno zawierające Umowę licencyjną użytkownika oprogramowania (EULA). Zapoznaj się dokładnie z treścią dokumentu.

3. Wybierz pozycję **Zgadzam się**, aby zaakceptować umowę EULA, co spowoduje zainstalowanie pakietu na komputerze.

4.  Otwórz folder **IntuneMAMPackager** i zapisz jego zawartość na komputerze z systemem macOS. Można teraz uruchomić narzędzie opakowujące aplikacje.

> [!NOTE]
> Program Intune MAM Packager może zostać zainstalowany oddzielnie na komputerze z systemem macOS, co może spowodować błąd „Nie można odnaleźć pliku” podczas uruchamiania poleceń opakowywania. W związku z tym przeniesienie zawartości folderu IntuneMAMPackager pozwoli na znalezienie ścieżki do pakowarki podczas opakowywania.

## <a name="run-the-app-wrapping-tool"></a>Uruchamianie narzędzia opakowującego aplikacje

### <a name="use-terminal"></a>Korzystanie z terminala

W systemie macOS otwórz program Terminal i przejdź do folderu, w którym zostały zapisane pliki narzędzia opakowującego aplikacje. Plik wykonywalny narzędzia nosi nazwę IntuneMAMPackager i znajduje się w folderze IntuneMAMPackager/Contents/MacOS. Uruchom następujące polecenie:

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> Niektóre parametry są opcjonalne, jak pokazano w poniższej tabeli.

**Przykład:** następujące przykładowe polecenie uruchamia narzędzie opakowujące aplikacje w celu przetworzenia aplikacji o nazwie MyApp.ipa. Profil aprowizowania oraz skrót SHA-1 certyfikatu podpisywania zostaną określone i będą używane do podpisywania opakowanej aplikacji. Aplikacja wyjściowa (MyApp_Wrapped.ipa) zostanie utworzona i zapisana w folderze Desktop (Pulpit).

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c "12 A3 BC 45 D6 7E F8 90 1A 2B 3C DE F4 AB C5 D6 E7 89 0F AB"  -v true
```

### <a name="command-line-parameters"></a>Parametry wiersza polecenia
Z narzędziem opakowującym aplikacje można użyć następujących parametrów wiersza polecenia:

|Właściwość|Sposób użycia|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. Nazwa pliku musi mieć zakończenie .app lub .ipa. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Wyświetla szczegółowe informacje dotyczące użycia dostępnych właściwości wiersza polecenia dla narzędzia opakowującego aplikacje.|
|**-v**|(Opcjonalna) Zwraca pełne komunikaty wyjściowe do konsoli. Zaleca się użyć tej flagi w celu debugowania wszelkich błędów.|
|**-e**| (Opcjonalna) Użyj tej właściwości, aby narzędzie opakowujące aplikacje usuwało brakujące uprawnienia podczas przetwarzania aplikacji. Zobacz [Ustawianie uprawnień dla aplikacji](#setting-app-entitlements), aby uzyskać szczegółowe informacje.|
|**-xe**| (Opcjonalna) Wyświetla informacje na temat rozszerzeń systemu iOS w aplikacji oraz uprawnień wymaganych do ich używania. Zobacz [Ustawianie uprawnień dla aplikacji](#setting-app-entitlements), aby uzyskać szczegółowe informacje. |
|**-x**| (Opcjonalnie) `<An array of paths to extension provisioning profiles>`. Użyj tej właściwości, jeśli aplikacja wymaga profilów aprowizacji rozszerzeń.|
|**-f**|(Opcjonalna) `<Path to a plist file specifying arguments.>` Poprzedź tą flagą plik [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html), jeśli chcesz użyć szablonu pliku plist w celu określenia pozostałych właściwości aplikacji IntuneMAMPackager: -i, -o, -p itd. Zobacz temat Wprowadzanie argumentów przy użyciu pliku plist. |
|**-b**|(Opcjonalnie) Użyj właściwości -b bez argumentu, jeśli chcesz, aby opakowana aplikacja wyjściowa miała taką samą wersję pakietu jak aplikacja wejściowa (niezalecane). <br/><br/> Użyj właściwości `-b <custom bundle version>`, jeśli chcesz, aby opakowana aplikacja miała niestandardową wartość CFBundleVersion. Jeśli chcesz określić niestandardową wartość CFBundleVersion, zaleca się podwyższenie najmniej istotnego składnika wartości CFBundleVersion aplikacji natywnej, na przykład z 1.0.0 na 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Wprowadzanie argumentów przy użyciu pliku plist
Łatwym sposobem uruchamiania narzędzia opakowującego aplikacje jest wprowadzenie wszystkich argumentów polecenia w pliku [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html). Plist to format pliku podobny do formatu XML, umożliwiający wprowadzanie argumentów wiersza polecenia za pomocą interfejsu formularza.

Za pomocą edytora tekstu lub narzędzia Xcode otwórz plik `Parameters.plist`, pusty szablon pliku plist znajdujący się w folderze IntuneMAMPackager/Contents/MacOS. Wprowadź argumenty dla następujących kluczy:

| Klucz pliku plist |  Wartość domyślna| Uwagi |
|------------------|--------------|-----|
| Input Application Package Path (Ścieżka pakietu aplikacji wejściowej)  |puste| Odpowiada właściwości -i.|
| Output Application Package Path (Ścieżka pakietu aplikacji wyjściowej) |puste| Odpowiada właściwości -o.|
| Provisioning Profile Path (Ścieżka profilu aprowizacji) |puste| Odpowiada właściwości -p.|
| SHA-1 Certificate Hash (Skrót certyfikatu SHA-1) |puste| Odpowiada właściwości -c.|
| Verbose Enabled (Pełne komunikaty włączone) |fałsz| Odpowiada właściwości -v.|
| Remove Missing Entitlements (Usuwanie brakujących uprawnień) | fałsz| Odpowiada właściwości -c.|
| Prevent Default Build (Zapobieganie użyciu domyślnej kompilacji) |fałsz | Odpowiada właściwości -b bez argumentów.|
|Build String Override (Zastąpienie ciągu kompilacji) | puste| Niestandardowa wartość CFBundleVersion opakowanej aplikacji wyjściowej |
|Extension Provisioning Profile Paths (Ścieżki profilów aprowizacji rozszerzeń) | puste| Tablica profilów aprowizacji rozszerzeń dla aplikacji.


Uruchom aplikację IntuneMAMPackager, wprowadzając plik plist jako jedyny argument:

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>Czynności po opakowaniu

Po zakończeniu procesu opakowywania zostanie wyświetlony komunikat „The application was successfully wrapped” (Aplikacja została pomyślnie opakowana). W przypadku wystąpienia błędu zobacz [Komunikaty o błędach](#error-messages-and-log-files), aby uzyskać pomoc.

Przetworzona aplikacja zostanie zapisana we wskazanym wcześniej folderze wyjściowym. Możesz przekazać aplikację do konsoli administracyjnej usługi Intune i skojarzyć ją z zasadami zarządzania aplikacjami mobilnymi.

> [!IMPORTANT]
> Podczas przekazywania opakowanej aplikacji możesz spróbować zaktualizować starszą wersję aplikacji, jeśli starsza wersja (opakowana lub natywna) została już wdrożona w usłudze Intune. Jeśli wystąpi błąd, przekaż opakowaną aplikację jako nową aplikację, a następnie usuń starszą wersję.

Teraz możesz wdrożyć aplikację do grup użytkowników i przypisać zasady ochrony do aplikacji. Aplikacja będzie uruchamiana na urządzeniu przy użyciu wybranych zasad ochrony aplikacji.

## <a name="how-often-should-i-rewrap-my-ios-application-with-the-intune-app-wrapping-tool"></a>Jak często należy ponownie opakowywać aplikację systemu iOS za pomocą narzędzia opakowującego aplikacje usługi Intune?
Główne scenariusze, w których trzeba będzie ponownie opakować aplikacje:
* Sama aplikacja wydała nową wersję. Poprzednia wersja aplikacji została opakowana i przekazana do konsoli usługi Intune.
* Narzędzie opakowujące aplikacje usługi Intune dla systemu iOS wydało nową wersję, która oferuje kluczowe poprawki usterek i nowe funkcje zasad ochrony aplikacji, przeznaczone specjalnie dla usługi Intune. Taka sytuacja występuje co 6–8 tygodni za pośrednictwem repozytorium GitHub dla [narzędzia opakowującego aplikacje usługi Intune dla systemu iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios).

W przypadku systemu iOS, chociaż możliwe jest opakowywanie przy użyciu profilu aprowizacji/certyfikatu innego niż oryginalnie zastosowany do podpisania aplikacji, jeśli uprawnienia określone w aplikacji nie zostaną uwzględnione w nowym profilu aprowizacji, opakowywanie nie powiedzie się. Użycie opcji „-e” wiersza polecenia, która usuwa wszystkie brakujące uprawnienia z aplikacji, w celu wymuszenia zakończenia opakowywania powodzeniem w tym scenariuszu może spowodować uszkodzenie funkcjonalności aplikacji.

Niektóre najlepsze rozwiązania dotyczące ponownego opakowywania:
* Upewnienie się, że inny profil aprowizacji ma wszystkie wymagane uprawnienia dowolnego poprzedniego profilu aprowizacji. 

## <a name="error-messages-and-log-files"></a>Komunikaty o błędach i pliki dziennika
Skorzystaj z poniższych informacji przy rozwiązywaniu problemów z narzędziem opakowującym aplikacje.

### <a name="error-messages"></a>Komunikaty o błędach
Jeśli przetwarzanie aplikacji przez narzędzie opakowujące aplikacje nie powiedzie się, w konsoli zostanie wyświetlony jeden z następujących komunikatów o błędach:

|Komunikat o błędzie|Więcej informacji|
|-----------------|--------------------|
|Należy określić prawidłowy profil inicjowania obsługi administracyjnej systemu iOS.|Twój profil inicjowania obsługi administracyjnej może być nieprawidłowy. Upewnij się, że masz odpowiednie uprawnienia do urządzeń oraz że Twój profil prawidłowo wskazuje programowanie lub dystrybucję. Twój profil inicjowania obsługi administracyjnej mógł również wygasnąć.|
|Określ prawidłową nazwę aplikacji wejściowej.|Upewnij się, że podana nazwa aplikacji wejściowej jest prawidłowa.|
|Określ prawidłową ścieżkę do aplikacji wyjściowej.|Upewnij się, że podana ścieżka do aplikacji wyjściowej istnieje i że jest prawidłowa.|
|Określ prawidłowy wejściowy profil aprowizacji.|Upewnij się, że podana nazwa oraz rozszerzenie profilu aprowizacji są prawidłowe. Być może nie wprowadzono opcji wiersza poleceń –p lub w Twoim profilu aprowizacji brakuje uprawnień.|
|Nie odnaleziono wskazanej aplikacji wejściowej. Określ prawidłową nazwę i ścieżkę aplikacji wejściowej.|Upewnij się, że podana ścieżka do aplikacji wejściowej istnieje i że jest prawidłowa. Upewnij się, że aplikacja wejściowa znajduje się w tej lokalizacji.|
|Nie odnaleziono wskazanego wejściowego profilu inicjowania obsługi administracyjnej. Określ prawidłowy plik wejściowego profilu inicjowania obsługi administracyjnej.|Upewnij się, że podana ścieżka do pliku wejściowego profilu inicjowania obsługi administracyjnej jest prawidłowa i że podany plik istnieje.|
|Nie odnaleziono wskazanego folderu aplikacji wyjściowej. Określ prawidłową ścieżkę do aplikacji wyjściowej.|Upewnij się, że podana ścieżka wyjściowa istnieje i że jest prawidłowa.|
|Aplikacja wyjściowa nie ma rozszerzenia **.ipa**.|Narzędzie opakowujące aplikacje obsługuje wyłącznie aplikacje z rozszerzeniami **app** oraz **ipa**. Upewnij się, że plik wyjściowy ma właściwe rozszerzenie.|
|Określono nieprawidłowy certyfikat podpisywania. Określ prawidłowy certyfikat podpisywania firmy Apple.|Upewnij się, że pobrano prawidłowy certyfikat podpisywania z portalu dla deweloperów firmy Apple. Być może certyfikat wygasł albo brakuje klucza publicznego lub prywatnego. Jeśli do prawidłowego podpisania aplikacji w programie Xcode można użyć certyfikatu firmy Apple i profilu inicjowania obsługi administracyjnej, można ich użyć również w narzędziu opakowującym aplikacje.|
|Wskazana aplikacja wejściowa jest nieprawidłowa. Określ prawidłową aplikację.|Upewnij się, że masz prawidłową aplikację dla systemu iOS skompilowaną w formacie pliku .app lub .ipa.|
|Wskazana aplikacja wejściowa jest zaszyfrowana. Określ prawidłową niezaszyfrowaną aplikację.|Narzędzie opakowujące aplikacje nie obsługuje aplikacji zaszyfrowanych. Wprowadź aplikację niezaszyfrowaną.|
|Wskazana aplikacja wejściowa nie jest w formacie PIE (Position Independent Executable). Określ prawidłową aplikację w formacie PIE.|Aplikacje w formacie PIE mogą być uruchamiane w losowym adresie pamięci, co może korzystnie wpływać na bezpieczeństwo. Więcej informacji na ten temat zawiera dokumentacja dla deweloperów firmy Apple.|
|Wskazana aplikacja wejściowa jest już opakowana. Określ prawidłową nieopakowaną aplikację.|Nie można przetwarzać aplikacji, które zostały już przetworzone przez narzędzie. Jeśli chcesz ponownie przetworzyć aplikację, należy uruchomić narzędzie z oryginalną wersją aplikacji.|
|Wskazana aplikacja wejściowa nie jest podpisana. Określ prawidłową podpisaną aplikację.|Narzędzie opakowujące aplikacje wymaga, aby aplikacje były podpisane. Sposób podpisywania opakowanych aplikacji opisuje dokumentacja dla deweloperów.|
|Wskazana aplikacja wejściowa musi mieć format .ipa lub .app.|Narzędzie opakowujące aplikacje obsługuje wyłącznie pliki z rozszerzeniami .app oraz .ipa. Upewnij się, że plik wejściowy ma prawidłowe rozszerzenie i został skompilowany w formacie .app lub .ipa.|
|Wskazana aplikacja wejściowa jest już opakowana i korzysta z najnowszej wersji szablonu zasad.|Narzędzie opakowujące aplikacje nie opakuje ponownie istniejącej opakowanej aplikacji korzystającej z najnowszej wersji szablonu zasad.|
|OSTRZEŻENIE: nie określono skrótu SHA1 certyfikatu. Przed wdrożeniem upewnij się, że opakowana aplikacja jest podpisana.|Upewnij się, że po właściwości wiersza polecenia –c podano prawidłowy skrót SHA1. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Pliki dziennika narzędzia opakowującego aplikacje
Przetwarzanie aplikacji za pomocą narzędzia opakowującego aplikacje wiąże się z generowaniem dzienników zapisywanych w konsoli urządzenia klienta systemu iOS. Informacje te są przydatne w przypadku wystąpienia problemów z aplikacją, gdy konieczne jest ustalenie, czy problem jest związany z narzędziem opakowującym aplikacje. Aby uzyskać dostęp do tych informacji, wykonaj następujące czynności:

1.  Uruchom aplikację, aby problem wystąpił ponownie.

2.  Zbierz dane wyjściowe z konsoli zgodnie z instrukcjami [debugowania wdrożonych aplikacji dla systemu iOS](https://developer.apple.com/library/ios/qa/qa1747/_index.html)firmy Apple.

3.  Przefiltruj zapisane dzienniki, aby uzyskać wyniki związane z ograniczeniami aplikacji, wprowadzając w konsoli następujący skrypt:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Przefiltrowane dzienniki można przesłać do firmy Microsoft.

    > [!NOTE]
    > W pliku dziennika pozycja „build version” („wersja kompilacji”) oznacza wersję kompilacji narzędzia Xcode.

    Przetworzone aplikacje oferują również użytkownikom możliwość przesyłania dzienników pocztą e-mail bezpośrednio z urządzenia po awarii aplikacji. Dzienniki otrzymane od użytkowników możesz zbadać i w razie potrzeby przesłać do firmy Microsoft.


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Wymagania dotyczące certyfikatu, profilu inicjowania obsługi administracyjnej i uwierzytelniania

Pełna funkcjonalność narzędzia opakowującego aplikacje dla systemu iOS wymaga spełnienia pewnych wymagań.

|Wymaganie|Szczegóły|
|---------------|-----------|
|Profil aprowizacji systemu iOS|Przed wprowadzeniem profilu aprowizacji upewnij się, że jest on prawidłowy. Podczas przetwarzania aplikacji dla systemu iOS narzędzie opakowujące aplikacje nie sprawdza, czy profil nie wygasł. Jeśli zostanie wprowadzony wygasły profil aprowizacji, narzędzie opakowujące aplikacje uwzględni go, a problem zostanie zauważony dopiero po niepowodzeniu instalacji aplikacji na urządzeniu z systemem iOS.|
|Certyfikat podpisywania systemu iOS|Przed wprowadzeniem certyfikatu podpisywania upewnij się, że jest on prawidłowy. Narzędzie opakowujące aplikacje podczas przetwarzania aplikacji dla systemu iOS nie sprawdza, czy certyfikat nie wygasł. W przypadku wprowadzenia skrótu wygasłego certyfikatu aplikacja zostanie przetworzona i podpisana przez narzędzie, ale nie będzie można jej instalować na urządzeniach.<br /><br />Upewnij się, że certyfikat służący do podpisywania opakowanej aplikacji jest zgodny z profilem aprowizacji. Narzędzie nie sprawdza zgodności profilu i certyfikatu wprowadzonego w celu podpisania opakowanej aplikacji.|
|Uwierzytelnianie|Aby szyfrowanie działało, urządzenie musi mieć numer PIN. Na urządzeniach, na których wdrożono opakowaną aplikację, dotknięcie paska stanu spowoduje konieczność ponownego zalogowania użytkownika przy użyciu konta służbowego. Domyślne zasady opakowanej aplikacji to *uwierzytelnianie przy ponownym uruchamianiu*. System iOS obsługuje zewnętrzne powiadomienia (na przykład połączenie telefoniczne) podczas kończenia pracy aplikacji, a następnie jej ponownego uruchamiania.


## <a name="setting-app-entitlements"></a>Ustawianie uprawnień dla aplikacji
Przed opakowaniem aplikacji można przyznać *uprawnienia* w celu zapewnienia jej dodatkowych uprawnień i możliwości, którymi aplikacje zwykle nie dysponują. Aby określić dla aplikacji specjalne uprawnienia, takie jak dostęp do udostępnionego łańcucha kluczy, na etapie podpisywania kodu używany jest *plik uprawnień*. Usługi specyficzne dla aplikacji (nazywane *możliwościami*) są włączane w środowisku Xcode podczas opracowywania aplikacji. Po włączeniu te możliwości są odzwierciedlane w pliku uprawnień. Aby uzyskać więcej informacji dotyczących uprawnień i możliwości, zobacz [Dodawanie możliwości](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) w bibliotece deweloperów systemu iOS. Aby uzyskać pełną listę obsługiwanych możliwości, zobacz [Obsługiwane możliwości](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>Obsługiwane możliwości narzędzia opakowującego aplikacje dla systemu iOS

|Możliwość|Opis|Zalecane wskazówki|
|--------------|---------------|------------------------|
|Grupy aplikacji|Dzięki grupom aplikacji można umożliwić wielu aplikacjom dostęp do udostępnionych kontenerów i zezwolić na dodatkową komunikację międzyprocesową między aplikacjami.<br /><br />Aby włączyć grupy aplikacji, otwórz okienko **Możliwości** i kliknij przełącznik **WŁ.** w sekcji **Grupy aplikacji**. Można dodać grupy aplikacji lub wybrać istniejące.|Podczas korzystania z grup aplikacji należy używać odwrotnej notacji DNS:<br /><br />*grupa.com.nazwa_firmy.grupa_aplikacji*|
|Tryby tła|Włączenie trybów tła umożliwia aplikacji systemu iOS kontynuowanie działania w tle.||
|Ochrona danych|Ochrona danych dodaje poziom zabezpieczeń do plików przechowywanych na dysku przez aplikację systemu iOS. Ochrona danych korzysta z wbudowanego w konkretnym urządzeniu sprzętu do szyfrowania w celu przechowywania plików na dysku w postaci zaszyfrowanej. Twoja aplikacja powinna być przygotowana do korzystania z ochrony danych.||
|Zakup w aplikacji|Funkcja zakupu w aplikacji pozwala osadzić sklep bezpośrednio w aplikacji, co umożliwia nawiązanie połączenia ze sklepem i bezpieczne przetworzenie płatności użytkownika. Funkcji zakupu w aplikacji można użyć do zbierania płatności na potrzeby rozszerzenia funkcjonalności lub dodania zawartości możliwej do przetworzenia przez aplikację.||
|Udostępnianie pęku kluczy|Włączenie udostępniania pęku kluczy umożliwia aplikacji udostępnianie haseł przechowywanych w pęku kluczy innym aplikacjom opracowywanym przez dany zespół.|Podczas korzystania z udostępniania pęku kluczy należy używać odwrotnej notacji DNS:<br /><br />*com.nazwa_firmy.grupa_peku_kluczy*|
|Osobista sieć VPN|Włącz osobistą sieć VPN, aby umożliwić aplikacji tworzenie niestandardowej konfiguracji sieci VPN w systemie i sterowanie nią za pomocą środowiska rozszerzenia sieci.||
|Powiadomienia wypychane|Usługa Apple Push Notification Service (APNs) umożliwia aplikacji, która nie jest uruchomiona na pierwszym planie, powiadomienie użytkownika o oczekujących informacjach.|Aby powiadomienia wypychane mogły działać, należy użyć profilu inicjowania obsługi administracyjnej dla aplikacji.<br /><br />Postępuj zgodnie z instrukcjami znajdującymi się w [dokumentacji dla deweloperów firmy Apple](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Konfiguracja akcesoriów sieci bezprzewodowej|Włączenie konfiguracji akcesoriów sieci bezprzewodowej powoduje dodanie do projektu zewnętrznego środowiska akcesoriów i umożliwia aplikacji skonfigurowanie akcesoriów Wi-Fi MFi.||

### <a name="steps-to-enable-entitlements"></a>Kroki umożliwiające włączenie uprawnień

1.  Włącz możliwości w swojej aplikacji:

    a.  W środowisku Xcode przejdź do elementu docelowego aplikacji i kliknij okienko **Możliwości**.

    b.  Włącz odpowiednie możliwości. Aby uzyskać szczegółowe informacje dotyczące poszczególnych możliwości oraz sposobu określania poprawnych wartości, zobacz [Dodawanie możliwości](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) w bibliotece deweloperów systemu iOS.

    c.  Zanotuj wszystkie identyfikatory, które zostały utworzone podczas tego procesu.

    d.  Skompiluj i podpisz swoją aplikację w celu jej opakowania.

2.  Włącz uprawnień w Twoim profilu inicjowania obsługi administracyjnej:

    a.  Zaloguj się do witryny Member Center przeznaczonej dla deweloperów firmy Apple.

    b.  Utwórz profil inicjowania obsługi administracyjnej dla swojej aplikacji. Aby uzyskać instrukcje, zobacz [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Jak uzyskać wymagania wstępne dotyczące narzędzia opakowującego aplikacje dla systemu iOS w usłudze Intune).

    c.  W swoim profilu inicjowania obsługi administracyjnej włącz takie same uprawnienia, jakie ma Twoja aplikacja. Będzie konieczne podanie takich samych identyfikatorów, jakie zostały określone podczas opracowywania aplikacji.

    d.  Zakończ pracę Kreatora profilu aprowizacji i pobierz odpowiedni plik.

3.  Upewnij się, że zostały spełnione wszystkie wymagania wstępne, a następnie opakuj aplikację.

### <a name="troubleshoot-common-errors-with-entitlements"></a>Rozwiązywanie typowych problemów z uprawnieniami
Jeśli w narzędziu opakowującym aplikacje dla systemu iOS jest wyświetlany błąd uprawnień, spróbuj wykonać następujące kroki w celu rozwiązania problemu.

|Problem|Przyczyna|Rozwiązanie|
|---------|---------|--------------|
|Nie można przeanalizować uprawnień wygenerowanych z aplikacji wejściowej.|Narzędzie opakowujące aplikacje nie może odczytać pliku uprawnień, który został wyodrębniony z aplikacji. Plik uprawnień może być nieprawidłowo uformowany.|Sprawdź plik uprawnień dla swojej aplikacji. Postępuj zgodnie z poniższymi instrukcjami. Podczas sprawdzania pliku uprawnień sprawdź, czy nie zawiera on nieprawidłowo sformatowanej składni. Ten plik powinien być w formacie XML.|
|W profilu inicjowania obsługi administracyjnej brakuje uprawnień (brakujące uprawnienia są wymienione). Spakuj ponownie aplikację razem z profilem inicjowania obsługi administracyjnej, który zawiera te uprawnienia.|Wystąpiła niezgodność między uprawnieniami włączonymi w profilu inicjowania obsługi administracyjnej i możliwościami włączonymi w aplikacji. Ta niezgodność dotyczy także identyfikatorów skojarzonych z konkretnymi możliwościami (np. grupy aplikacji, dostęp do pęku kluczy itp.).|Ogólnie rzecz biorąc, można utworzyć nowy profil inicjowania obsługi administracyjnej z włączonymi takimi samymi możliwościami, jakie włączono w aplikacji. W przypadku wystąpienia niezgodności identyfikatorów w profilu i aplikacji narzędzie opakowujące aplikacje zastąpi te identyfikatory, jeśli będzie to możliwe. Jeśli ten błąd będzie nadal się pojawiać po utworzeniu nowego profilu aprowizacji, można spróbować usunąć uprawnienia z aplikacji przy użyciu parametru –e (zobacz poniższą sekcję „Usuwanie uprawnień z aplikacji za pomocą parametru –e”).|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>Wyszukiwanie istniejących uprawnień podpisanej aplikacji
Aby przejrzeć istniejące uprawnienia podpisanej aplikacji i profilu inicjowania obsługi administracyjnej:

1.  Znajdź plik ipa i zmień jego rozszerzenie na zip.

2.  Rozwiń plik zip. Spowoduje to utworzenie folderu Payload zawierającego pakiet app.

3.  Za pomocą narzędzia codesign sprawdź uprawnienia w pakiecie app, gdzie `YourApp.app` jest rzeczywistą nazwą pakietu app:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  Za pomocą narzędzia security sprawdź uprawnienia osadzonego w aplikacji profilu aprowizacji, gdzie `YourApp.app` jest rzeczywistą nazwą pakietu app.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Usuwanie uprawnień z aplikacji za pomocą parametru –e
To polecenie usuwa wszystkie włączone możliwości w aplikacji, które nie znajdują się w pliku uprawnień. Usunięcie możliwości używanych przez aplikację może spowodować nieprawidłowe działanie aplikacji. Na przykład można usunąć brakujące możliwości, jeśli w aplikacji opracowanej przez dostawcę są domyślnie włączone wszystkie możliwości.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Funkcje zabezpieczeń i ochrony prywatności narzędzia opakowującego aplikacje
Podczas korzystania z narzędzia opakowującego aplikacje należy stosować poniższe dobre praktyki dotyczące zabezpieczeń i ochrony prywatności.

-   Certyfikat podpisywania, profil aprowizacji oraz aplikacja biznesowa do przetworzenia muszą znajdować się na tym samym komputerze z systemem Mac OS, na którym jest uruchamiane narzędzie opakowujące aplikacje. Jeśli pliki znajdują się na ścieżce UNC, upewnij się, że są one dostępne z tego komputera z systemem Mac OS. Ścieżka musi być zabezpieczona za pomocą protokołu IPsec lub funkcji podpisywania protokołu SMB.

    Opakowana aplikacja zaimportowana do konsoli administracyjnej powinna znajdować się na tym samym komputerze, na którym jest uruchamiane narzędzie. Jeśli plik znajduje się w ścieżce UNC, upewnij się, że jest dostępny na komputerze, na którym uruchomiono konsolę administracyjną. Ścieżka musi być zabezpieczona za pomocą protokołu IPsec lub funkcji podpisywania protokołu SMB.

-   Środowisko, w którym narzędzie opakowujące aplikacje zostanie pobrane z repozytorium w witrynie GitHub, musi być zabezpieczone za pomocą protokołu IPsec lub funkcji podpisywania protokołu SMB.

-   W celu zabezpieczenia przed atakami przetwarzane aplikacje muszą pochodzić z zaufanego źródła.

-   Upewnij się, że folder wyjściowy wskazany w narzędziu opakowującym aplikacje jest zabezpieczony, zwłaszcza gdy jest to folder zdalny.

-   Aplikacje dla systemu iOS zawierające okno dialogowe przekazywania plików mogą umożliwiać użytkownikom obejście zastosowanych do aplikacji ograniczeń wycinania, kopiowania i wklejania. Użytkownik może na przykład użyć okna dialogowego przekazywania plików do przekazania zrzutu ekranu zawierającego dane aplikacji.

-   W przypadku monitorowania folderu dokumentów na urządzeniu przy użyciu opakowanej aplikacji może być widoczny folder o nazwie .msftintuneapplauncher. Modyfikacja lub usunięcie tego pliku może zakłócić działanie aplikacji z ograniczeniami.

## <a name="getting-logs-for-your-wrapped-applications"></a>Pobieranie dzienników opakowanych aplikacji
Wykonaj następujące kroki, aby podczas rozwiązywania problemów pobrać dzienniki opakowanych aplikacji.

1. Przejdź do aplikacji Ustawienia systemu iOS na urządzeniu i wybierz aplikację LOB.
2. Przełącz opcję **Diagnostics Console** (Konsola diagnostyczna) na ustawienie **On** (Włączona).
3. Uruchom aplikację LOB.
4. Kliknij link „Wprowadzenie”.
5. Możesz teraz udostępniać dzienniki za pośrednictwem poczty e-mail lub przez ich skopiowanie do lokalizacji usługi OneDrive.

> [!NOTE]
> Funkcja rejestrowania jest włączona dla aplikacji, które zostały opakowane za pomocą dostępnego w usłudze Intune narzędzia opakowującego aplikacje w wersji 7.1.13 lub nowszej.

### <a name="see-also"></a>Zobacz też
- [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](apps-prepare-mobile-application-management.md)</br>
- [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)</br>
- [Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
