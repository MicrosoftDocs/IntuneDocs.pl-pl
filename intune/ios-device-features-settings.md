---
title: Ustawienia funkcji urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft DocsiOS device feature settings in Microsoft Intune - Azure | Microsoft Docs
description: Wyświetl wszystkie ustawienia służące do konfigurowania ustawień urządzeń z systemem iOS na potrzeby funkcji AirPrint, układu ekranu głównego, powiadomień aplikacji, urządzenia udostępnionego, logowania jednokrotnego i filtru zawartości internetowej w usłudze Microsoft Intune. Używaj tych ustawień w profilu konfiguracji urządzenia w celu konfigurowania urządzeń z systemem iOS, aby korzystać z różnych funkcji firmy Apple w organizacji.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b31c7778ea167b98468a0a9ad9e37047c30ce201
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66047183"
---
# <a name="ios-device-settings-to-use-common-ios-features-in-intune"></a>Ustawienia urządzeń z systemem iOS dotyczące korzystania z typowych funkcji systemu iOS w usłudze Intune

Usługa Intune ma niektóre wbudowane ustawienia umożliwiające użytkownikom systemu iOS korzystanie z różnych funkcji firmy Apple na urządzeniach. Na przykład administratorzy mogą kontrolować sposób używania drukarki AirPrint przez użytkowników systemu iOS, dodawać aplikacje i foldery do obszaru dokowania i stron na ekranie głównym, pokazywać powiadomienia w aplikacji, pokazywać szczegóły tagu zasobu na ekranie blokady, korzystać z uwierzytelniania logowania jednokrotnego i uwierzytelniać użytkowników za pomocą certyfikatów.

Za pomocą tych funkcji możesz sterować urządzeniami z systemem iOS w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM).

Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia z systemem iOS](device-features-configure.md#create-a-device-profile).

## <a name="airprint"></a>Funkcja AirPrint

- **Adres IP**: podaj adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do terminala. Dalsze szczegółowe informacje można znaleźć w sekcji Uzyskiwanie adresu IP i ścieżki (w tym artykule).
- **Ścieżka**: w przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji Uzyskiwanie adresu IP i ścieżki (w tym artykule).
- **Port**: podaj port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego. Ustawienie dostępne w systemie iOS 11.0 i jego nowszych wersjach.
- **TLS**: wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS). Ustawienie dostępne w systemie iOS 11.0 i jego nowszych wersjach.

Opcja **Dodaj** powoduje dodanie serwera funkcji AirPrint do listy. Można dodać wiele serwerów z funkcją AirPrint. Możesz również **zaimportować** plik rozdzielany przecinkami (CSV) z tymi informacjami. Po utworzeniu listy możesz także **wyeksportować** listę serwerów z funkcją AirPrint.

Wybierz przycisk **OK**, aby zapisać listę.

### <a name="get-server-ip-address-resource-path-and-port"></a>Uzyskanie adresu IP serwera, ścieżki zasobu i portu

Aby dodać serwery funkcji AirPrinter, potrzebujesz adresu IP drukarki, ścieżki zasobu i portu. Poniższe kroki przedstawiają sposób uzyskiwania tych informacji.

1. Na komputerze Mac podłączonym do tej samej sieci lokalnej (podsieci) co drukarki AirPrint otwórz **Terminal** (z folderu **/Applications/Utilities**).
2. W terminalu wpisz `ippfind`, a następnie wybierz klawisz Enter.

    Zanotuj informacje o drukarce. Zwrócone informacje mogą wyglądać podobnie do następujących: `ipp://myprinter.local.:631/ipp/port1`. Pierwsza część to nazwa drukarki. Ostatnia część (`ipp/port1`) to ścieżka zasobu.

3. W terminalu wpisz `ping myprinter.local`, a następnie wybierz klawisz Enter.

   Zanotuj adres IP. Zwrócone informacje mogą wyglądać podobnie do następujących: `PING myprinter.local (10.50.25.21)`.

4. Użyj wartości adresu IP i ścieżki zasobu. W tym przykładzie adres IP to `10.50.25.21`, a ścieżka zasobu to `/ipp/port1`.

## <a name="home-screen-layout-settings"></a>Ustawienia układu ekranu głównego

Te ustawienia umożliwiają konfigurowanie układu aplikacji i folderów w obszarze dokowania i na ekranie głównym urządzeń z systemem iOS. Aby używać tej funkcji, urządzenia z systemem iOS muszą działać w trybie nadzorowanym i mieć zainstalowany system iOS 9.3 lub nowszy.

### <a name="dock"></a>Dock

Ustawienia okienka **Dock** umożliwiają dodanie do sześciu elementów lub folderów do obszaru Dock na ekranie systemu iOS. Wiele urządzeń obsługuje mniejszą liczbę elementów. Na przykład urządzenia iPhone obsługują maksymalnie cztery elementy. W takim przypadku na urządzeniu wyświetlane są tylko pierwsze cztery dodane elementy.

Możesz dodać maksymalnie **sześć** elementów (łącznie aplikacji i folderów) w obszarze Dock urządzenia.

- **Dodaj**: umożliwia dodanie aplikacji lub folderów do obszaru Dock urządzenia.
- **Typ**: umożliwia dodanie **aplikacji** lub **folderu**:

  - **Aplikacja**: wybierz tę opcję, aby dodać aplikacje do obszaru Dock na ekranie. Wprowadź:

    - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS.
    - **Identyfikator pakietu aplikacji**: podaj identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemu iOS](bundle-ids-built-in-ios-apps.md).

    Wybierz przycisk **OK**, aby zapisać zmiany.

  - **Folder**: wybierz tę opcję, aby dodać folder do obszaru Dock na ekranie.

    Aplikacje dodawane do strony w folderze są rozmieszczane od lewej do prawej i w takiej samej kolejności jak na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na inną stronę.

    - **Nazwa folderu**: wprowadź nazwę folderu. Ta nazwa jest widoczna na urządzeniach użytkowników.
    - **Lista stron**: **dodaj** stronę, a następnie wprowadź następujące właściwości:

      - **Nazwa strony**: wprowadź nazwę strony. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS.
      - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS.
      - **Identyfikator pakietu aplikacji**: podaj identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemu iOS](bundle-ids-built-in-ios-apps.md).

      Można dodać maksymalnie **20** stron do obszaru Dock urządzenia.

    Wybierz przycisk **OK**, aby zapisać zmiany.

> [!NOTE]
> Gdy dodasz ikony za pomocą ustawień obszaru Dock, ikony na ekranie głównym i na stronach zostaną zablokowane i nie można będzie ich przenosić. Może to być celowe działanie zasad zarządzania urządzeniami mobilnymi firmy Apple i systemu iOS.

#### <a name="example"></a>Przykład

W poniższym przykładzie ekran Dock zawiera tylko aplikacje Safari, Poczta i Akcje. Aplikacja Poczta została wybrana, aby wyświetlić jej właściwości:

![Przykładowe ustawienia Docka w systemie iOS](./media/FfFiUcP.png)

Po przypisaniu zasad do telefonu iPhone wygląd Docka tego urządzenia jest zbliżony do poniższego obrazu:

![Przykładowy układ Docka telefonu iPhone z systemem iOS](./media/bAgCe8F.png)

### <a name="pages"></a>Pages

Dodaj strony, które mają być wyświetlane na ekranie głównym, oraz aplikacje, które mają być wyświetlane na każdej ze stron. Aplikacje dodawane do strony są rozmieszczane od lewej do prawej i w takiej samej kolejności jak na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na inną stronę.

> [!TIP]
> Aby zmieniać kolejność elementów na dowolnych listach stron i ekranu głównego, można je przeciągać i upuszczać.

Możesz dodać maksymalnie **40** stron na urządzeniu.

- **Lista stron**: **dodaj** stronę, a następnie wprowadź następujące właściwości:

  - **Nazwa strony**: wprowadź nazwę strony. Jest to nazwa, do której można się odwołać w witrynie Azure Portal, i która *nie jest* wyświetlana na urządzeniu z systemem iOS.

  Możesz dodać maksymalnie **60** elementów (łącznie aplikacji i folderów) na urządzeniu.

  - **Dodaj**: umożliwia dodanie aplikacji lub folderów do strony na urządzeniu.

    - **Typ**: umożliwia dodanie **aplikacji** lub **folderu**:

      - **Aplikacja**: wybierz tę opcję, aby dodać aplikacje do strony na ekranie. Wprowadź też następujące ustawienia:

        - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS.
        - **Identyfikator pakietu aplikacji**: podaj identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemu iOS](bundle-ids-built-in-ios-apps.md).

      Wybierz przycisk **OK**, aby zapisać zmiany.

      - **Folder**: wybierz tę opcję, aby dodać folder do obszaru Dock na ekranie.

        Aplikacje dodawane do strony w folderze są rozmieszczane od lewej do prawej i w takiej samej kolejności jak na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na inną stronę.

        - **Nazwa folderu**: wprowadź nazwę folderu. Ta nazwa jest widoczna na urządzeniach użytkowników.
        - **Dodaj**: umożliwia dodanie stron do folderu. Wprowadź także następujące właściwości:

          - **Nazwa strony**: wprowadź nazwę strony. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS.
          - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS.
          - **Identyfikator pakietu aplikacji**: podaj identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemu iOS](bundle-ids-built-in-ios-apps.md).

      Wybierz przycisk **OK**, aby zapisać zmiany.

#### <a name="example"></a>Przykład

W poniższym przykładzie dodamy nową stronę o nazwie **Contoso**. Na stronie znajdują się aplikacje Moi znajomi i Ustawienia. Aplikacja Ustawienia została wybrana, aby wyświetlić jej właściwości:

![Przykład ustawień ekranu głównego w systemie iOS](./media/Jc2OxyX.png)

Po przypisaniu zasad do telefonu iPhone wygląd strony tego urządzenia jest zbliżony do poniższego obrazu:

![Urządzenie z systemem iOS ze zmodyfikowanym ekranem głównym](./media/Bd37PHa.png)

## <a name="app-notifications-settings"></a>Ustawienia powiadomień aplikacji

Wybierz sposób, w jaki aplikacje na urządzeniu z systemem iOS wysyłają powiadomienia. Te ustawienia obsługują nadzorowane urządzenia z systemem iOS w wersji 9.3 i nowszych.

- **Dodaj**: umożliwia dodanie powiadomień dla aplikacji:

    ![Dodawanie powiadomienia w aplikacji w profilu systemu iOS w usłudze Intune](./media/ios-macos-app-notifications.png)

  - **Identyfikator pakietu aplikacji**: podaj **identyfikator pakietu aplikacji**, którą chcesz dodać. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemu iOS](bundle-ids-built-in-ios-apps.md).
  - **Nazwa aplikacji**: podaj nazwę aplikacji, którą chcesz dodać. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu.
  - **Wydawca**: podaj wydawcę dodawanej aplikacji. Ta nazwa jest używana w celach referencyjnych w witrynie Azure Portal. *Nie jest* ona wyświetlana na urządzeniu.
  - **Powiadomienia**: opcja **Włącz** lub **Wyłącz** określa, czy aplikacja wysyła powiadomienia do urządzenia.
    - **Pokaż w centrum powiadomień**: opcja **Włącz** zezwala aplikacji na wyświetlanie powiadomień w centrum powiadomień na urządzeniu. **Wyłączenie** tego ustawienia uniemożliwia aplikacji wyświetlanie powiadomień w centrum powiadomień.
    - **Pokaż na ekranie blokady**: opcja **Włącz** powoduje, że powiadomienia z aplikacji będą wyświetlane na ekranie blokady urządzenia. **Wyłączenie** uniemożliwia aplikacji wyświetlanie powiadomień na ekranie blokady.
    - **Typ alertu**: po odblokowaniu urządzenia wybierz sposób wyświetlania powiadomienia. Dostępne opcje:
      - **Brak**: powiadomienia nie są wyświetlane.
      - **Transparent**: wraz z powiadomieniem jest krótko wyświetlany transparent.
      - **Modalne**: zostanie wyświetlone powiadomienie, które użytkownik będzie musiał ręcznie zamknąć przed kontynuowaniem korzystania z urządzenia.
    - **Znaczek na ikonie aplikacji**: wybierz pozycję **Włącz**, aby dodać znaczek do ikony aplikacji. Znaczek oznacza, że aplikacja wysłała powiadomienie.
    - **Dźwięki**: wybierz opcję **Włącz**, aby odtwarzać dźwięk po dostarczeniu powiadomienia.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="lock-screen-message-settings"></a>Ustawienia komunikatów na ekranie blokady

Te ustawienia pozwalają wyświetlać niestandardowe komunikaty lub tekst w oknie logowania i na ekranie blokady. Można na przykład wprowadzić komunikat „W razie zgubienia zwróć do” oraz informacje dotyczące tagu zasobu. 

Ta funkcja obsługuje nadzorowane urządzenia z systemem iOS w wersji 9.3 i nowszych.

- **Informacje dotyczące tagu zasobu**: podaj informacje o tagu zasobu urządzenia. Na przykład wprowadź adres `Owned by Contoso Corp` lub `Serial Number: {{serialnumber}}`.

  Wprowadzony tekst zostanie wyświetlony w oknie logowania i na ekranie blokady w urządzeniu.

- **Przypis dolny ekranu blokady**: podaj informacje, które mogą ułatwić zwrot urządzenia w przypadku jego utraty lub kradzieży. Możesz podać dowolny tekst. Na przykład wpisz coś takiego: `If found, call Contoso at ...`.

  Możesz też dodać w tych polach informacje dotyczące konkretnych urządzeń za pomocą tokenów urządzeń. Aby na przykład wyświetlić numer seryjny, wprowadź `Serial Number: {{serialnumber}}`. Na ekranie blokady zostanie wyświetlony tekst podobny do tego: `Serial Number 123456789ABC`. Podczas wprowadzania zmiennych użyj nawiasów klamrowych `{{ }}`. [Tokeny konfiguracji aplikacji](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) zawierają listę zmiennych, których można użyć. Możesz też użyć wartości `deviceName` lub innej wartości specyficznej dla urządzenia.

  > [!NOTE]
  > Zmienne nie są weryfikowane w interfejsie użytkownika. Dlatego mogą pojawić się profile zapisane z niepoprawnymi danymi wejściowymi. Na przykład jeśli podano wartość `{{Devicename}}` zamiast `{{devicename}}`, to zostanie wyświetlony literał ciągu zamiast unikatowej nazwy urządzenia.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="single-sign-on-settings"></a>Ustawienia logowania jednokrotnego

Większość aplikacji biznesowych (LOB, Line of Business) wymaga pewnego poziomu uwierzytelniania użytkowników w celu obsługi zabezpieczeń. W wielu przypadkach to uwierzytelnianie oznacza to, że użytkownik musi wprowadzać te same poświadczenia wielokrotnie, co może być irytujące dla użytkowników. Aby ulepszyć środowisko użytkownika, deweloperzy mogą tworzyć aplikacje korzystające z logowania jednokrotnego. Użycie logowania jednokrotnego zmniejsza liczbę operacji wprowadzania poświadczeń przez użytkownika.

Aby korzystać z logowania jednokrotnego, upewnij się, że masz:

- Aplikację poszukującą magazynu poświadczeń użytkownika w logowaniu jednokrotnym na urządzeniu.
- Usługa Intune musi być skonfigurowana na potrzeby logowania jednokrotnego dla urządzeń z systemem iOS.

![Okienko Logowanie jednokrotne](./media/sso-blade.png)

- **Atrybut nazwy użytkownika z usługi AAD**: usługa Intune szuka tego atrybutu dla każdego użytkownika w usłudze Azure AD. Następnie usługa Intune wypełnia odpowiednie pole (na przykład nazwę UPN) przed wygenerowaniem kodu XML instalowanego na urządzeniu. Dostępne opcje:

  - **Główna nazwa użytkownika**: nazwa UPN jest analizowana w następujący sposób:

    ![Atrybut nazwy użytkownika](media/User-name-attribute.png)

    Można również zastąpić obszar tekstem wpisywanym w polu tekstowym **Obszar**.

    Na przykład firma Contoso ma kilka regionów, w tym takich jak Europa, Azja i Ameryka Północna. Firma Contoso chce, aby użytkownicy z regionu Azja korzystali z logowania jednokrotnego, natomiast aplikacja wymaga nazwy UPN w formacie `username@asia.contoso.com`. Jeśli zostanie wybrana wartość **Główna nazwa użytkownika**, obszar dla każdego użytkownika zostanie pobrany z usługi Azure AD i może on mieć wartość `contoso.com`. Dlatego dla użytkowników w Azji wybierz pozycję **Główna nazwa użytkownika**, a następnie wprowadź `asia.contoso.com`. Nazwa UPN użytkownika końcowego będzie miała wartość `username@asia.contoso.com` zamiast `username@contoso.com`.

  - **Identyfikator urządzenia usługi Intune**: usługa Intune automatycznie wybiera identyfikator urządzenia usługi Intune.

    Domyślnie dla aplikacji wymagany jest tylko identyfikator urządzenia. Jeśli natomiast aplikacja korzysta z obszaru oraz z identyfikatora urządzenia, możesz wpisać obszar w polu tekstowym Obszar.

    > [!NOTE]
    > Domyślnie nie wpisuj żadnej wartości w polu Obszar, jeśli używasz identyfikatora urządzenia.

  - **Identyfikator urządzenia usługi Azure AD**

- **Obszar**: podaj część adresu URL oznaczającą domenę. Na przykład wprowadź `contoso.com`.
- **Przedrostki adresów URL, które będą korzystały z logowania jednokrotnego**: **dodaj** wszystkie adresy URL w organizacji, które wymagają uwierzytelniania za pomocą logowania jednokrotnego użytkownika.

  Kiedy na przykład użytkownik nawiązuje połączenie z dowolną z tych witryn, urządzenie z systemem iOS używa poświadczeń logowania jednokrotnego. Użytkownik nie musi wprowadzać żadnych dodatkowych poświadczeń. Jeśli włączone jest uwierzytelnianie wieloskładnikowe, użytkownicy muszą wykonać drugie uwierzytelnianie.

  > [!NOTE]
  > Te adresy URL muszą być poprawnie sformatowanymi nazwami FQDN. Firma Apple wymaga, aby miały one format `http://<yourURL.domain>`.

  Wzorce dopasowań adresów URL muszą rozpoczynać się od ciągu `http://` lub `https://`. Uruchamiane jest proste dopasowanie ciągu, które wykaże, że prefiks adresu URL `http://www.contoso.com/` jest niezgodny z ciągiem `http://www.contoso.com:80/`. W przypadku systemów iOS 10.0 lub nowszych można użyć pojedynczego symbolu wieloznacznego \*, aby wprowadzić wszystkie zgodne wartości. Na przykład wzorzec `http://*.contoso.com/` jest zgodny zarówno z adresem URL `http://store.contoso.com/`, jak i `http://www.contoso.com`.

  Wzorce `http://.com` i `https://.com` są zgodne odpowiednio ze wszystkimi adresami URL protokołów HTTP i HTTPS.

- **Aplikacje, które będą korzystały z logowania jednokrotnego**: **dodaj** aplikacje na urządzeniach użytkowników końcowych, które mogą używać logowania jednokrotnego.

  Tablica `AppIdentifierMatches` musi uwzględniać ciągi zgodne z identyfikatorami pakietu aplikacji. Te ciągi mogą być dokładnymi dopasowaniami (przykład: `com.contoso.myapp`) lub możesz wprowadzić dopasowanie prefiksu w ramach identyfikatora pakietu za pomocą symbolu wieloznacznego \*. Symbol wieloznaczny musi występować po znaku kropki (.) i może zostać użyty tylko raz — na końcu ciągu, na przykład: `com.contoso.*`. Jeśli symbol wieloznaczny zostanie użyty, to dowolna aplikacja o identyfikatorze pakietu rozpoczynającym się od prefiksu uzyskuje dostęp do konta.

  Użyj pola **Nazwa aplikacji**, aby wprowadzić przyjazną nazwę, która ułatwia rozpoznanie identyfikatora pakietu.

- **Certyfikat odnowy poświadczeń**: w przypadku używania certyfikatów w celu uwierzytelniania (nie haseł) wybierz istniejący certyfikat SCEP lub PFX jako certyfikat uwierzytelniania. Zazwyczaj jest to ten sam certyfikat, który został wdrożony dla użytkownika na potrzeby innych profilów, takich jak profil sieci VPN lub Wi-Fi bądź profil poczty e-mail.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="web-content-filter-settings"></a>Ustawienia filtru zawartości internetowej

Te ustawienia kontrolują dostęp za pomocą adresu URL przeglądarki na urządzeniach z systemem iOS.

- **Typ filtru**: wybierz, aby zezwolić na określone witryny internetowe. Dostępne opcje:

  - **Konfiguruj adresy URL**: użyj wbudowanego filtru internetowego firmy Apple, który wyszukuje słownictwo przeznaczone dla osób dorosłych, w tym przekleństwa i słowa o charakterze seksualnym. Ta funkcja ocenia każdą stronę internetową podczas ładowania oraz identyfikuje i blokuje nieodpowiednią zawartość. Możesz również dodać adresy URL, które nie mają być sprawdzane przez filtr. Ponadto możesz zablokować określone adresy URL, niezależnie od ustawień filtru firmy Apple.

    - **Dozwolone adresy URL**: **dodaj** adresy URL, na które chcesz zezwolić. Te adresy URL są pomijane przez filtr internetowy firmy Apple.

      > [!NOTE]
        > Wprowadzone adresy to adresy URL, które nie mają być oceniane przez filtr internetowy firmy Apple. Te adresy URL nie stanowią listy dozwolonych witryn internetowych. Aby utworzyć listę dozwolonych witryn internetowych, należy ustawić **typ filtru** na pozycję **Tylko określone witryny internetowe**.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Zablokowane adresy URL**: użyj opcji **Dodaj**, aby dodać adresy URL, których otwieranie ma zostać zatrzymane niezależnie od ustawień filtru internetowego firmy Apple.

      Wybierz przycisk **OK**, aby zapisać zmiany.

  - **Tylko określone witryny internetowe** (dotyczy wyłącznie przeglądarki Safari): te adresy URL są dodawane do zakładek przeglądarki Safari. Użytkownik jest uprawniony **wyłącznie** do odwiedzania tych witryn internetowych; nie będzie można otwierać żadnych innych witryn. Użyj tej opcji tylko wtedy, gdy znasz dokładną listę adresów URL, do których użytkownicy mogą uzyskiwać dostęp.

    - **Adres URL**: podaj adres URL dozwolonej witryny internetowej. Na przykład wprowadź `https://www.contoso.com`.
    - **Ścieżka do zakładki**: wprowadź ścieżkę na potrzeby przechowywania zakładki. Na przykład wprowadź `/Contoso/Business Apps`. Jeśli nie dodasz ścieżki, zakładka zostanie dodana do domyślnego folderu zakładek na urządzeniu.
    - **Tytuł**: podaj opisowy tytuł zakładki.

    Jeśli nie wprowadzisz żadnych adresów URL, użytkownicy końcowi nie będą mogli uzyskiwać dostęp do żadnych witryn internetowych, z wyjątkiem `microsoft.com`, `microsoft.net`, i `apple.com`. Usługa Intune automatycznie zezwala na dostęp do tych adresów URL.

    Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="wallpaper-settings"></a>Ustawienia tapety

Dodaj niestandardowy obrazu PNG, JPG lub JPEG na urządzeniach nadzorowanych z systemem iOS. Na przykład użyj logo firmy na ekranie blokady.

Jeśli profil bez obrazu zostanie przypisany do urządzeń z istniejącym obrazem, mogą wystąpić nieoczekiwane zachowania. Na przykład profil zostanie utworzony bez obrazu. Ten profil jest przypisany do urządzeń, które mają już obraz. W tym scenariuszu obraz może zostać zmieniony na obraz domyślny urządzenia lub oryginalny obraz może pozostać na urządzeniu. To zachowanie jest kontrolowane i ograniczane przez platformę MDM firmy Apple.

- **Lokalizacja wyświetlania tapety**: wybierz lokalizację wyświetlania obrazu na urządzeniu. Dostępne opcje:
  - **Nieskonfigurowane**: obraz niestandardowy nie jest dodawany do urządzenia. Urządzenie używa wartości domyślnej systemu operacyjnego.
  - **Ekran blokady**: dodaje obraz do ekranu blokady.
  - **Ekran główny**: dodaje obraz do ekranu głównego.
  - **Ekran blokady i ekran główny**: używa tego samego obrazu na ekranie blokady i na ekranie głównym.
- **Obraz tapety**: przekaż istniejący obraz PNG, JPG lub JPEG, którego chcesz użyć. Upewnij się, że rozmiar pliku jest mniejszy niż 750 KB. Możesz również **usunąć** obraz, który został dodany.

> [!TIP]
> Aby wyświetlać różne obrazy na ekranie blokady i na ekranie głównym, utwórz profil przy użyciu obrazu ekranu blokady. Utwórz inny profil przy użyciu obrazu ekranu głównego. Przypisz obydwa profile do grup użytkowników lub urządzeń systemu iOS.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile funkcji urządzenia dla urządzeń z systemem [macOS](macos-device-features-settings.md).
