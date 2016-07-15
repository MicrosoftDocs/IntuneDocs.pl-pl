---
# required metadata

title: Przygotowanie aplikacji systemu iOS do zarządzania za pomocą narzędzia opakowującego aplikacje | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Przygotowanie aplikacji systemu iOS do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Intune
Za pomocą **narzędzia opakowującego aplikacje dla systemu iOS w usłudze Microsoft Intune** można modyfikować działanie wewnętrznych aplikacji dla systemu iOS przez ograniczanie ich funkcji bez konieczności zmieniania kodu aplikacji.

Jest to narzędzie wiersza poleceń systemu Mac OS tworzące „otokę” dla aplikacji. Po przetworzeniu wybranej aplikacji można modyfikować jej funkcje, korzystając ze skonfigurowanych przez siebie [zasad zarządzania aplikacjami mobilnymi](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) usługi.

Aby pobrać to narzędzie, zobacz [Narzędzie opakowujące aplikacje dla systemu iOS w usłudze Microsoft Intune](http://www.microsoft.com/en-us/download/details.aspx?id=45218).

## Krok 1 Spełnianie wymagań wstępnych dotyczących używania narzędzia opakowującego aplikacje

|Wymaganie|Więcej informacji|
|---------------|--------------------------------|
|Obsługiwany system operacyjny i zestaw narzędzi|Narzędzie opakowujące aplikacje można uruchomić na komputerze Mac z systemem OS X 10.8.5 lub nowszym z zainstalowanym zestawem narzędzi XCode w wersji 5 lub nowszej.|
|Certyfikat podpisywania i profil inicjowania obsługi administracyjnej|Wymagany jest profil inicjowania obsługi administracyjnej oraz certyfikat podpisywania firmy Apple. Przejrzyj [dokumentację dla deweloperów firmy Apple](https://developer.apple.com/).|
|Przetwarzanie aplikacji za pomocą narzędzia opakowującego aplikacje|Aplikacje muszą być opracowane i podpisane przez Twoją firmę lub niezależnego dostawcę oprogramowania. Za pomocą tego narzędzia nie można przetwarzać aplikacji ze sklepu Apple. Aplikacje muszą być napisane dla systemu iOS w wersji 7.0 lub nowszej. Aplikacje muszą również mieć format PIE (Position Independent Executable). Więcej informacji na temat formatu PIE zawiera dokumentacja dla deweloperów firmy Apple. Ponadto aplikacja musi mieć rozszerzenie **.app** lub **.ipa**.|
|Aplikacje, które nie mogą być przetworzone przez narzędzie opakowujące aplikacje|Aplikacje zaszyfrowane, aplikacje niepodpisane i aplikacje z rozszerzonymi atrybutami plików.|
|Aplikacje korzystające z biblioteki usługi Azure Active Directory (ADAL)|Jeśli aplikacja korzysta z biblioteki ADAL, musi mieć zintegrowaną bibliotekę ADAL w wersji 1.0.2 lub nowszej, a deweloper musi udzielić dostępu aplikacji do zasobu zarządzania aplikacjami mobilnymi usługi Intune.<br /><br />Zobacz [Informacje dotyczące aplikacji korzystających z bibliotek usługi Azure Active Directory (ADAL)](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library) w tym artykule, aby uzyskać szczegółowe informacje na temat sposobu użycia bibliotek ADAL.|
|Ustawianie uprawnień dla aplikacji|Przed opakowaniem aplikacji należy ustawić uprawnienia, które zapewnią aplikacji dodatkowe możliwości poza tymi, które są zwykle przyznawane. Instrukcje można znaleźć w artykule [Ustawienie uprawnień dla aplikacji](#setting-app-entitlements).|

## Krok 2 Instalowanie narzędzia opakowującego aplikacje

1.  Pobierz plik instalacyjny **narzędzia opakowującego aplikacje dla systemu iOS** ze strony narzędzia opakowującego aplikacje dla systemu iOS w usłudze Microsoft Intune w [Centrum pobierania Microsoft](https://www.microsoft.com/download/details.aspx?id=45218).

2.  Na komputerze Mac kliknij dwukrotnie plik instalacyjny **Microsoft Intune App Wrapping Tool for iOS.dmg**.

3.  Wybierz pozycję **Zgadzam się**, aby zaakceptować Umowę licencyjną użytkownika oprogramowania (EULA). Instalator zostanie zainstalowany i wyświetlony na komputerze Mac.

4.  Otwórz instalator i skopiuj wyświetlone pliki do nowego folderu na komputerze Mac. Teraz możesz odłączyć zainstalowany dysk instalatora.

    Można teraz uruchomić narzędzie opakowujące aplikacje.

## Krok 3 Uruchamianie narzędzia opakowującego aplikacje

1.  Na komputerze Mac otwórz okno Terminala i przejdź do folderu, w którym zostały zapisane pliki. Ponieważ plik wykonywalny znajduje się w pakiecie, należy uruchomić polecenie w następujący sposób:
```
    ./IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|Właściwość|Więcej informacji|
  |------------|--------------------|
  |**-h**|Wyświetla dostępne właściwości wiersza poleceń dla narzędzia opakowującego aplikacje.|
  |**-i**|Określa ścieżkę i nazwę aplikacji wejściowej.|
  |**-o**|Określa ścieżkę zapisu aplikacji przetworzonej.|
  |**-p**|Określa ścieżkę profilu inicjowania obsługi administracyjnej dla aplikacji systemu iOS.|
  |**-c**|Określa skrót SHA1 certyfikatu podpisywania.|
  |**-a**|Identyfikator klienta aplikacji wejściowej (w formacie GUID), jeśli aplikacja korzysta z bibliotek usługi Azure Active Directory (opcjonalnie).|
  |**-r**|Identyfikator URI przekierowania aplikacji wejściowej, jeśli aplikacja korzysta z bibliotek usługi Azure Active Directory (opcjonalnie).|
  |**-v**|Pełne komunikaty wyjściowe do konsoli (opcjonalnie).|

2. Po zakończeniu przetwarzania zostanie wyświetlony komunikat **Aplikacja została pomyślnie opakowana** .

    W przypadku wystąpienia błędu zobacz [Komunikaty o błędach](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages), aby uzyskać pomoc.

3.  Przetworzona aplikacja zostanie zapisana we wskazanym wcześniej folderze wyjściowym. Możesz teraz przekazać aplikację do usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i powiązać ją z zasadami zarządzania aplikacjami mobilnymi.

    > [!IMPORTANT]
    > Należy przekazać tę aplikację jako nową aplikację. Zaktualizowanie starszej wersji aplikacji bez otoki jest niemożliwe.

    Teraz można wdrożyć aplikację w grupach usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i aplikacja ta będzie uruchamiana na urządzeniu ze wskazanymi ograniczeniami.

## Komunikaty o błędach i pliki dziennika
Skorzystaj z poniższych informacji przy rozwiązywaniu problemów z narzędziem opakowującym aplikacje.

### Komunikaty o błędach
Jeśli przetwarzanie aplikacji przez narzędzie opakowujące aplikacje nie powiedzie się, zostanie wyświetlony jeden z następujących komunikatów o błędzie:

|Komunikat o błędzie|Więcej informacji|
|-----------------|--------------------|
|Należy określić prawidłowy profil inicjowania obsługi administracyjnej systemu iOS.|Twój profil inicjowania obsługi administracyjnej może być nieprawidłowy. Upewnij się, że masz odpowiednie uprawnienia do urządzeń, oraz że Twój profil prawidłowo wskazuje programowanie lub dystrybucję. Twój profil inicjowania obsługi administracyjnej mógł również wygasnąć.|
|Określ prawidłową nazwę aplikacji wejściowej.|Upewnij się, że podana nazwa aplikacji wejściowej jest prawidłowa.|
|Określ prawidłową ścieżkę do aplikacji wyjściowej.|Upewnij się, że podana ścieżka do aplikacji wyjściowej istnieje i że jest prawidłowa.|
|Określ prawidłowy wejściowy profil aprowizacji.|Upewnij się, że podana nazwa oraz rozszerzenie profilu aprowizacji są prawidłowe. Być może nie wprowadzono opcji wiersza poleceń **–p** lub w Twoim profilu aprowizacji brakuje uprawnień.|
|Nie odnaleziono wskazanej aplikacji wejściowej. Określ prawidłową nazwę i ścieżkę aplikacji wejściowej.|Upewnij się, że podana ścieżka do aplikacji wejściowej istnieje i że jest prawidłowa. Upewnij się, że aplikacja wejściowa znajduje się w tej lokalizacji.|
|Nie odnaleziono wskazanego wejściowego profilu inicjowania obsługi administracyjnej. Określ prawidłowy plik wejściowego profilu inicjowania obsługi administracyjnej.|Upewnij się, że podana ścieżka do pliku wejściowego profilu inicjowania obsługi administracyjnej jest prawidłowa i że podany plik istnieje.|
|Nie odnaleziono wskazanego folderu aplikacji wyjściowej. Określ prawidłową ścieżkę do aplikacji wyjściowej.|Upewnij się, że podana ścieżka wyjściowa istnieje i że jest prawidłowa.|
|Aplikacja wyjściowa nie ma rozszerzenia .ipa.|Narzędzie opakowujące aplikacje obsługuje wyłącznie aplikacje z rozszerzeniami **.app** oraz **.ipa** . Upewnij się, że plik wyjściowy ma właściwe rozszerzenie.|
|Określono nieprawidłowy certyfikat podpisywania. Określ prawidłowy certyfikat podpisywania firmy Apple.|Upewnij się, że pobrano prawidłowy certyfikat podpisywania z portalu dla deweloperów firmy Apple. Twój certyfikat mógł również wygasnąć. Jeśli można użyć certyfikatu firmy Apple i profilu inicjowania obsługi administracyjnej do prawidłowego podpisania aplikacji w programie Xcode, można ich użyć również w narzędziu opakowującym aplikacje.|
|Wskazana aplikacja wejściowa jest nieprawidłowa. Określ prawidłową aplikację.|Upewnij się, że masz prawidłową aplikację dla systemu iOS skompilowaną w formacie pliku .app lub .ipa.|
|Wskazana aplikacja wejściowa jest zaszyfrowana. Określ prawidłową niezaszyfrowaną aplikację.|Narzędzie opakowujące aplikacje nie obsługuje aplikacji zaszyfrowanych. Określ aplikację niezaszyfrowaną.|
|Wskazana aplikacja wejściowa nie jest w formacie PIE (Position Independent Executable). Określ prawidłową aplikację w formacie PIE.|Aplikacje w formacie PIE mogą być uruchamiane w losowym adresie pamięci, co może korzystnie wpływać na bezpieczeństwo. Więcej informacji zawiera dokumentacja dla deweloperów firmy Apple.|
|Wskazana aplikacja wejściowa jest już opakowana. Określ prawidłową nieopakowaną aplikację.|Nie można przetwarzać aplikacji, które zostały już przetworzone przez narzędzie. Jeśli chcesz ponownie przetworzyć aplikację, należy uruchomić narzędzie z oryginalną wersją aplikacji.|
|Wskazana aplikacja wejściowa nie jest podpisana. Określ prawidłową podpisaną aplikację.|Narzędzie opakowujące aplikacje wymaga, aby aplikacje były podpisane. Sposób podpisywania opakowanych aplikacji opisuje dokumentacja dla deweloperów.|
|Wskazana aplikacja wejściowa musi mieć format .ipa lub .app.|Narzędzie opakowujące aplikacje obsługuje wyłącznie pliki z rozszerzeniami .app oraz .ipa. Upewnij się, że plik wejściowy ma prawidłowe rozszerzenie i został skompilowany w formacie .app lub .ipa.|
|Wskazana aplikacja wejściowa jest już opakowana i korzysta z najnowszej wersji szablonu zasad.|Narzędzie opakowujące aplikacje nie opakuje ponownie istniejącej opakowanej aplikacji korzystającej z najnowszej wersji szablonu zasad.|
|Podany identyfikator klienta usługi Azure Active Directory nie jest poprawnie sformułowanym identyfikatorem GUID. Określ prawidłowy identyfikator klienta.|Jeśli korzystasz z parametru identyfikatora klienta, upewnij się, że podano prawidłowy identyfikator klienta w formacie GUID.|
|Podany identyfikator URI odpowiedzi usługi Azure Active Directory nie jest poprawnie sformułowanym identyfikatorem URI. Określ prawidłowy identyfikator URI odpowiedzi.|Jeśli korzystasz z parametru identyfikatora URI odpowiedzi, upewnij się, że podano prawidłowy identyfikator URI odpowiedzi.|
|OSTRZEŻENIE: nie określono skrótu SHA1 certyfikatu. Przed wdrożeniem upewnij się, że opakowana aplikacja jest podpisana.|Upewnij się, że podano prawidłowy skrót SHA (za pomocą właściwości wiersza poleceń **–c** ).|

### Pliki dziennika narzędzia opakowującego aplikacje
Przetwarzanie aplikacji za pomocą narzędzia opakowującego aplikacje wiąże się z generowaniem dzienników zapisywanych w konsoli urządzenia klienta systemu iOS. Informacje te są przydatne w przypadku wystąpienia problemów z aplikacją, gdy konieczne jest ustalenie, czy problem jest związany z narzędziem opakowującym aplikacje. Aby uzyskać dostęp do tych informacji, wykonaj następujące czynności:

1.  Uruchom aplikację, aby problem wystąpił ponownie.

2.  Zbierz dane wyjściowe z konsoli zgodnie z instrukcjami [debugowania wdrożonych aplikacji dla systemu iOS](https://developer.apple.com/library/ios/qa/qa1747/_index.html) firmy Apple..

3.  Przefiltruj zapisane dzienniki, aby uzyskać wyniki związane z ograniczeniami aplikacji, wprowadzając w konsoli następujący skrypt:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Przefiltrowane dzienniki można przesłać do firmy Microsoft.

    > [!NOTE]
    > W pliku dziennika pozycja „build version” („wersja kompilacji”) oznacza wersję kompilacji narzędzia Xcode.

    Przetworzone aplikacje oferują również użytkownikom możliwość przesyłania dzienników pocztą e-mail bezpośrednio z urządzenia po awarii aplikacji. Dzienniki otrzymane od użytkowników możesz zbadać i w razie potrzeby przesłać do firmy Microsoft.

## Informacje dotyczące aplikacji korzystających z bibliotek usługi Azure Active Directory
Informacje zawarte w tej sekcji dotyczą tylko aplikacji korzystających z bibliotek usługi Azure Active Directory (ADAL). Jeśli nie wiesz, czy Twoja aplikacja korzysta z tej biblioteki, skontaktuj się z deweloperem.

Aplikacja musi mieć zintegrowaną wersję bibliotek ADAL 1.0.2 lub nowszą.

W przypadku aplikacji korzystających z bibliotek ADAL muszą być spełnione następujące warunki:

-   Aplikacja musi mieć zintegrowaną wersję bibliotek ADAL 1.0.2 lub nowszą.

-   Deweloperzy muszą udzielić dostępu aplikacji do zasobu zarządzania aplikacjami mobilnymi usługi Intune zgodnie z opisem zamieszczonym w sekcji [Kroki, które należy wykonać w przypadku aplikacji korzystających z biblioteki ADAL](#steps-to-follow-for-apps-that-use-adal).

### Przegląd identyfikatorów koniecznych do uzyskania
W przypadku aplikacji korzystających z bibliotek ADAL konieczna jest rejestracja w portalu zarządzania platformy Azure w celu uzyskania dwóch unikatowych identyfikatorów dla aplikacji:

|Identyfikator|Więcej informacji|Wartość domyślna|
|--------------|--------------------|-----------------|
|**Identyfikator klienta**|Po zarejestrowaniu danej aplikacji w usłudze Azure Active Directory jest dla niej tworzony unikatowy identyfikator GUID.<br /><br />Jeśli znasz identyfikator klienta właściwy dla danej aplikacji, możesz podać tę wartość. W przeciwnym razie należy użyć wartości domyślnej.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Identyfikator URI przekierowania**|Wartość identyfikatora URI, którą deweloperzy mogą podać przy rejestracji aplikacji w usłudze Azure Active Directory w celu zapewnienia, że tokeny uwierzytelniania będą kierowane do określonego punktu końcowego.<br /><br />Podanie parametru identyfikatora URI przekierowania w narzędziu opakowującym aplikacje jest opcjonalne. Jeśli nie zostanie określony, będzie używany domyślny identyfikator URI.|urn:ietf:wg:oauth:2.0:oob|


### Kroki, które należy wykonać w przypadku aplikacji korzystających z biblioteki ADAL

1.  Przejrzyj sekcję [Przegląd identyfikatorów koniecznych do uzyskania](#overview-of-identifiers-you-need-to-get), aby zidentyfikować potrzebne wartości.

2.  Skonfiguruj dostęp do zarządzania aplikacjami mobilnymi w usłudze Azure Active Directory, wykonując następujące czynności:

    1. Zaloguj się do istniejącego konta usługi Azure Active Directory w portalu zarządzania platformy Azure.

    2.  Kliknij pozycję **Rejestracja istniejącej aplikacji LOB** w usłudze Azure Active Directory.

    3.  W sekcji konfiguracji wybierz opcję **Konfigurowanie dostępu do interfejsów API sieci Web w innych aplikacjach**.

    4.  W sekcji **Uprawnienia do innych aplikacji** wybierz pozycję **Zarządzenie aplikacjami mobilnymi w usłudze Intune** z pierwszej listy rozwijanej..

        Po wykonaniu tych czynności można użyć identyfikatora klienta aplikacji w narzędziu opakowującym aplikacje. Identyfikator klienta aplikacji można znaleźć w portalu zarządzania usługi Azure Active Directory zgodnie z opisem w sekcji [Przegląd identyfikatorów koniecznych do uzyskania](#overview-of-identifiers-you-need-to-get).

3.  Użyj wartości **identyfikatora klienta** (uzyskanych przy użyciu właściwości **–a**) i **identyfikatora URI przekierowania** jako właściwości wiersza polecenia w narzędziu opakowującym aplikacje. Jeśli nie podasz tych wartości, zostaną użyte wartości domyślne. Obie wartości muszą zostać określone — w przeciwnym razie użytkownik końcowy nie będzie mógł pomyślnie wykonać uwierzytelnienia w przetworzonej aplikacji.

### Wymagania dotyczące certyfikatu, profilu inicjowania obsługi administracyjnej i uwierzytelniania

|Wymaganie|Szczegóły|
|---------------|-----------|
|Profil aprowizacji|**Przed wprowadzeniem profilu aprowizacji upewnij się, że jest prawidłowy** — narzędzie opakowujące aplikacje nie sprawdza podczas przetwarzania aplikacji dla systemu iOS, czy profil nie wygasł. Jeśli zostanie wprowadzony wygasły profil aprowizacji, narzędzie opakowujące aplikacje uwzględni go, a problem zostanie zauważony dopiero po niepowodzeniu instalacji aplikacji na urządzeniu z systemem iOS.|
|Certyfikat|**Przed wprowadzeniem certyfikatu upewnij się, że jest prawidłowy** — narzędzie opakowujące aplikacje nie sprawdza podczas przetwarzania aplikacji dla systemu iOS, czy certyfikat nie wygasł. W przypadku wprowadzenia skrótu wygasłego certyfikatu aplikacja zostanie przetworzona i podpisana przez narzędzie, ale nie będzie można jej instalować na urządzeniach.<br /><br />**Upewnij się, że certyfikat do podpisania opakowanej aplikacji jest zgodny z profilem inicjowania obsługi administracyjnej** — narzędzie nie sprawdza zgodności profilu i certyfikatu wprowadzonego w celu podpisania opakowanej aplikacji.|
|Uwierzytelnianie|Aby szyfrowanie działało, urządzenie musi mieć ustawiony numer PIN. Na urządzeniach, na których wdrożono opakowaną aplikację, dotknięcie paska stanu spowoduje konieczność ponownego uwierzytelnienia użytkownika w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Domyślne zasady opakowanej aplikacji to *uwierzytelnianie przy ponownym uruchamianiu*. System iOS obsługuje zewnętrzne powiadomienia (na przykład połączenie telefoniczne) podczas kończenia pracy aplikacji, a następnie jej ponownego uruchamiania.<br /><br />W przypadku aplikacji opakowanych pierwszy użytkownik, który zaloguje się do dowolnej opakowanej aplikacji danego wydawcy, zostaje zapisany. Od tego momentu tylko ten użytkownik ma dostęp do tej aplikacji. Aby zresetować użytkownika, należy wyrejestrować, a następnie ponownie zarejestrować urządzenie.|

### Rozwiązywania problemów i uwagi techniczne dotyczące biblioteki ADAL

-   Jeśli nie zostaną znalezione zasoby bibliotek ADAL, narzędzie uwzględni bibliotekę dynamiczną ADAL. Narzędzie wyszuka w katalogu głównym bibliotekę ADAL o nazwie **ADALiOS.bundle** .

-   Narzędzie nie wyszukuje plików binarnych ADAL w aplikacji (nawet, jeśli istnieją). Jeśli aplikacja łączy się z nieaktualną wersją, a zasady uwierzytelniania są włączone, mogą wystąpić błędy w czasie wykonywania.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] dostarcza token usługi AAD do identyfikatora zasobu zarządzania aplikacjami mobilnymi w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu uwierzytelnienia. Nie jest on jednak używany w żadnym wywołaniu, które umożliwiłoby zweryfikowanie prawidłowości tokenu. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] odczytuje jedynie nazwę UPN zalogowanego użytkownika w celu określenia dostępu do aplikacji. Token usługi AAD nie jest używany w żadnych późniejszych wywołaniach usług.

-   Tokeny uwierzytelniania są wspólne dla aplikacji tego samego wydawcy, ponieważ są zapisywane we wspólnym łańcuchu kluczy. Jeśli chcesz wyizolować określoną aplikację, konieczne jest użycie dla niej innego certyfikatu podpisywania i profilu inicjowania obsługi administracyjnej.

-   Podanie identyfikatora klienta oraz identyfikatora URI przekierowania aplikacji zapobiega dwukrotnemu monitowaniu o zalogowanie. Zarejestrowanie tego identyfikatora klienta jest konieczne w celu uzyskania dostępu do opublikowanego identyfikatora zasobu zarządzania aplikacjami mobilnymi w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] na pulpicie nawigacyjnym usługi AAD. W przeciwnym razie po uruchomieniu aplikacji wystąpi błąd logowania.

## Ustawianie uprawnień dla aplikacji
Przed opakowaniem aplikacji można przyznać **uprawnienia** w celu zapewnienia aplikacji dodatkowych uprawnień i możliwości, którymi zwykle aplikacja nie dysponuje.  Aby określić dla aplikacji specjalne uprawnienia, takie jak dostęp do udostępnionego łańcucha kluczy, na etapie podpisywania kodu używany jest **plik uprawnień**. Usługi specyficzne dla aplikacji (nazywane **możliwościami**), są włączane w środowisku Xcode podczas jej opracowywania. Po włączeniu te możliwości są odzwierciedlane w pliku uprawnień. Aby uzyskać więcej informacji dotyczących uprawnień i możliwości, zobacz [Dodawanie możliwości](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) w bibliotece deweloperów systemu iOS. Aby uzyskać pełną listę obsługiwanych możliwości, zobacz [Obsługiwane możliwości](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html)..

### Obsługiwane możliwości narzędzia opakowującego aplikacje dla systemu iOS

|Możliwość|Opis|Zalecane wskazówki|
|--------------|---------------|------------------------|
|Grupy aplikacji|Dzięki grupom aplikacji można umożliwić wielu aplikacjom dostęp do udostępnionych kontenerów i zezwolić na dodatkową komunikację międzyprocesową między aplikacjami.<br /><br />Aby włączyć grupy aplikacji, otwórz okienko **Możliwości** i kliknij przełącznik **WŁ.** w sekcji **Grupy aplikacji**. Można dodać grupy aplikacji lub wybrać istniejące.|Podczas korzystania z grup aplikacji należy używać odwrotnej notacji DNS:<br /><br />*grupa.com.nazwa_firmy.grupa_aplikacji*|
|Tryby tła|Włączenie trybów tła umożliwia aplikacji systemu iOS kontynuowanie działania w tle.||
|Ochrona danych|Ochrona danych dodaje poziom zabezpieczeń do plików przechowywanych na dysku przez aplikację systemu iOS. Ochrona danych korzysta z wbudowanego w konkretnym urządzeniu sprzętu do szyfrowania w celu przechowywania plików na dysku w postaci zaszyfrowanej. Twoja aplikacja powinna być przygotowana do korzystania z ochrony danych.||
|Zakup w aplikacji|Funkcja zakupu w aplikacji osadza sklep bezpośrednio w aplikacji, umożliwiając nawiązanie połączenia ze sklepem i bezpieczne przetworzenie płatności od użytkownika. Funkcji zakupu w aplikacji można użyć do zbierania płatności na potrzeby rozszerzenia funkcjonalności lub dodania zawartości możliwej do przetworzenia przez aplikację.||
|Udostępnianie łańcucha kluczy|Włączenie udostępniania łańcucha kluczy umożliwia aplikacji udostępnianie haseł w łańcuchu kluczy innym aplikacjom opracowywanym przez Twój zespół.|Podczas korzystania z udostępniania łańcucha kluczy należy używać odwrotnej notacji DNS:<br /><br />*com.nazwa_firmy.grupa_lancucha_kluczy*|
|Osobista sieć VPN|Włącz osobistą sieć VPN, aby umożliwić aplikacji tworzenie niestandardowej konfiguracji sieci VPN w systemie i sterowanie nią za pomocą środowiska rozszerzenia sieci.||
|Powiadomienia wypychane|Usługa Apple Push Notification Service (APN) umożliwia aplikacji, która nie jest uruchomiona na pierwszym planie, powiadomienie użytkownika o oczekujących na niego informacjach.|Aby powiadomienia wypychane mogły działać, należy użyć profilu inicjowania obsługi administracyjnej dla aplikacji.<br /><br />Postępuj zgodnie z instrukcjami znajdującymi się w [dokumentacji dla deweloperów firmy Apple](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Konfiguracja akcesoriów sieci bezprzewodowej|Włączenie konfiguracji akcesoriów sieci bezprzewodowej powoduje dodanie do projektu zewnętrznego środowiska akcesoriów i umożliwia aplikacji skonfigurowanie akcesoriów Wi-Fi MFi.||

### Kroki umożliwiające włączenie uprawnień

1.  Włącz możliwości w swojej aplikacji:

    1.  W środowisku Xcode przejdź do elementu docelowego Twojej aplikacji i kliknij okienko **Możliwości**.

    2.  Włącz odpowiednie możliwości. Aby uzyskać szczegółowe informacje dotyczące poszczególnych możliwości oraz sposobu określania poprawnych wartości, zobacz [Dodawanie możliwości](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) w bibliotece deweloperów systemu iOS.

    3.  Zanotuj wszystkie identyfikatory, które zostały utworzone podczas tego procesu.

    4.  Skompiluj i podpisz swoją aplikację w celu jej opakowania.

2.  Włącz uprawnień w Twoim profilu inicjowania obsługi administracyjnej:

    1.  Zaloguj się do witryny Member Center przeznaczonej dla deweloperów firmy Apple.

    2.  Utwórz profil inicjowania obsługi administracyjnej dla swojej aplikacji. Aby uzyskać instrukcje, zobacz [Jak uzyskać wymagania wstępne dotyczące narzędzia opakowującego aplikacje dla systemu iOS w usłudze Intune](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx).

    3.  W swoim profilu inicjowania obsługi administracyjnej włącz takie same uprawnienia, jakie ma Twoja aplikacja. Będzie konieczne podanie takich samych identyfikatorów, jakie zostały określone podczas opracowywania aplikacji.

    4.  Zakończ pracę Kreatora profilu inicjowania obsługi administracyjnej i pobierz swój plik.

3.  Upewnij się, że zostały spełnione wszystkie wymagania wstępne, a następnie opakuj aplikację.

### Rozwiązywania typowych problemów z uprawnieniami
Jeśli w narzędziu opakowującym aplikacje dla systemu iOS jest wyświetlany błąd uprawnień, spróbuj wykonać następujące kroki w celu rozwiązania problemu.

|Problem|Przyczyna|Rozwiązanie|
|---------|---------|--------------|
|Nie można przeanalizować uprawnień wygenerowanych z aplikacji wejściowej.|Narzędzie opakowujące aplikacje nie może odczytać pliku uprawnień, który został wyodrębniony z aplikacji. Plik uprawnień może być nieprawidłowo uformowany.|Sprawdź plik uprawnień dla swojej aplikacji. W tym celu postępuj zgodnie z instrukcjami opisanymi poniżej. Podczas sprawdzania pliku uprawnień sprawdź, czy nie zawiera on nieprawidłowo sformatowanej składni. Ten plik powinien być w formacie XML.|
|W profilu inicjowania obsługi administracyjnej brakuje uprawnień (brakujące uprawnienia są wymienione). Spakuj ponownie aplikację razem z profilem inicjowania obsługi administracyjnej, który zawiera te uprawnienia.|Wystąpiła niezgodność między uprawnieniami włączonymi w profilu inicjowania obsługi administracyjnej i możliwościami włączonymi w aplikacji. Ta niezgodność dotyczy także identyfikatorów skojarzonych z konkretnymi możliwościami (np. grupy aplikacji, dostęp łańcucha kluczy itp.).|Ogólnie rzecz biorąc, można utworzyć nowy profil inicjowania obsługi administracyjnej z włączonymi takimi samymi możliwościami, jakie włączono w aplikacji. W przypadku wystąpienia niezgodności identyfikatorów w profilu i aplikacji narzędzie opakowujące aplikacje zastąpi te identyfikatory, jeśli będzie to możliwe. Jeśli ten błąd będzie nadal się pojawiać po utworzeniu nowego profilu aprowizacji, można spróbować usunąć uprawnienia z aplikacji przy użyciu parametru **–e** (zobacz sekcja „Usuwanie uprawnień z aplikacji za pomocą parametru –e” poniżej).|

### Wyszukiwanie istniejących uprawnień podpisanej aplikacji
Aby przejrzeć istniejące uprawnienia podpisanej aplikacji i profilu inicjowania obsługi administracyjnej:

1.  Znajdź plik ipa i zmień jego rozszerzenie na zip.

2.  Rozwiń plik zip. Spowoduje to utworzenie folderu Payload zawierającego pakiet app.

3.  Za pomocą narzędzia codesign sprawdź uprawnienia w pakiecie app w następujący sposób:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    gdzie `YourApp.app` jest rzeczywistą nazwą Twojego pakietu app.

4.  Za pomocą narzędzia security sprawdź uprawnienia osadzonego w aplikacji profilu inicjowania obsługi administracyjnej:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    gdzie `YourApp.app` jest rzeczywistą nazwą Twojego pakietu app.

### Usuwanie uprawnień z aplikacji za pomocą parametru –e
To polecenie usuwa wszystkie włączone możliwości w aplikacji, które nie znajdują się w pliku uprawnień. Usunięcie możliwości używanych przez aplikację może spowodować nieprawidłowe działanie aplikacji. Na przykład można usunąć brakujące możliwości, jeśli w aplikacji opracowanej przez dostawcę są domyślnie włączone wszystkie możliwości.

```
./IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Zabezpieczenia i ochrona prywatności podczas korzystania z narzędzia opakowującego aplikacje
Podczas korzystania z narzędzia opakowującego aplikacje należy stosować poniższe dobre praktyki dotyczące zabezpieczeń i ochrony prywatności.

-   Certyfikat podpisywania, profil inicjowania obsługi administracyjnej oraz aplikacja biznesowa do przetworzenia muszą znajdować się na tym samym komputerze Mac, na którym jest uruchamiane narzędzie opakowujące aplikacje. Jeśli pliki znajdują się w ścieżce UNC, upewnij się, że są one dostępne z tego komputera Mac. Ścieżka musi być zabezpieczona za pomocą protokołu IPsec lub funkcji podpisywania protokołu SMB.

    Opakowana aplikacja zaimportowana do konsoli [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] powinna znajdować się na tym samym komputerze, na którym jest uruchomione narzędzie. Jeśli plik znajduje się w ścieżce UNC, upewnij się, że jest dostępny z komputera, na którym uruchomiono konsolę usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Ścieżka musi być zabezpieczona za pomocą protokołu IPsec lub funkcji podpisywania protokołu SMB.

-   Środowisko, w którym narzędzie opakowujące aplikacje zostanie pobrane ze strony Centrum pobierania Microsoft, musi być zabezpieczone za pomocą protokołu IPsec lub funkcji podpisywania protokołu SMB.

-   W celu zabezpieczenia przed atakami przetwarzane aplikacje muszą pochodzić z zaufanego źródła.

-   Upewnij się, że folder wyjściowy wskazany w narzędziu opakowującym aplikacje jest zabezpieczony, zwłaszcza gdy jest to folder zdalny.

-   Aplikacje dla systemu iOS zawierające okno dialogowe przekazywania plików mogą umożliwiać użytkownikom obejście zastosowanych do aplikacji ograniczeń wycinania, kopiowania i wklejania. Użytkownik może na przykład użyć okna dialogowego przekazywania plików do przekazania zrzutu ekranu zawierającego dane aplikacji.

-   Użytkownicy monitorujący folder dokumentów na swoim urządzeniu przy użyciu opakowanej aplikacji mogą widzieć folder o nazwie **.msftintuneapplauncher**. Modyfikacja lub usunięcie tego folderu może zakłócić prawidłowe działanie aplikacji z ograniczeniami.

### Zobacz także
- [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


