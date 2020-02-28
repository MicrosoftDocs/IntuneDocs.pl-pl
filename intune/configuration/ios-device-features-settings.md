---
title: Ustawienia funkcji urządzeń z systemami iOS/iPadOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetl wszystkie ustawienia służące do konfigurowania ustawień urządzeń z systemami iOS i iPadOS na potrzeby funkcji AirPrint, układu ekranu głównego, powiadomień aplikacji, urządzenia udostępnionego, logowania jednokrotnego i filtru zawartości internetowej w usłudze Microsoft Intune. Używaj tych ustawień w profilu konfiguracji urządzenia w celu konfigurowania urządzeń z systemami iOS/iPadOS do korzystania z tych funkcji firmy Apple w organizacji.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f19ccfb6949dbfa0de62a8b711436ab9cde8c9c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512946"
---
# <a name="ios-and-ipados-device-settings-to-use-common-iosipados-features-in-intune"></a>Ustawienia urządzeń z systemem iOS oraz iPadOS dotyczące korzystania z typowych funkcji systemów iOS/iPadOS w usłudze Intune

Usługa Intune oferuje kilka wbudowanych ustawień umożliwiających użytkownikom systemów iOS/iPadOS korzystanie z różnych funkcji firmy Apple na urządzeniach. Na przykład administratorzy mogą kontrolować sposób używania drukarki AirPrint przez użytkowników systemów iOS/iPadOS, dodawać aplikacje i foldery do obszaru dokowania i do stron na ekranie głównym, pokazywać powiadomienia w aplikacji, pokazywać szczegóły tagu zasobu na ekranie blokady, korzystać z uwierzytelniania logowania jednokrotnego i uwierzytelniać użytkowników za pomocą certyfikatów.

Za pomocą tych funkcji możesz sterować urządzeniami z systemami iOS/iPadOS w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM).

Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień. Aby uzyskać więcej informacji na temat tych funkcji, przejdź do tematu [Dodawanie ustawień funkcji urządzeń z systemami iOS/iPadOS lub macOS](../device-features-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia z systemem iOS/iPadOS](../device-features-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji, a niektóre z nich dotyczą wszystkich opcji rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [Rejestracja systemu iOS/iPadOS](../ios-enroll.md).

## <a name="airprint"></a>Funkcja AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

> [!NOTE]
> Pamiętaj, aby wszystkie drukarki dodać do tego samego profilu. Firma Apple uniemożliwia stosowanie wielu profilów funkcji AirPrint na tym samym urządzeniu.

- **Adres IP**: wprowadź adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do terminala. Dalsze szczegółowe informacje można znaleźć w sekcji Uzyskiwanie adresu IP i ścieżki (w tym artykule).
- **Ścieżka**: W przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji Uzyskiwanie adresu IP i ścieżki (w tym artykule).
- **Port**: wprowadź port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego. Dostępne w systemie iOS 11.0 lub nowszym oraz w systemie iPadOS 13.0 lub nowszym.
- **TLS**: wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS). Dostępne w systemie iOS 11.0 lub nowszym oraz w systemie iPadOS 13.0 lub nowszym.

Dodawanie serwerów funkcji AirPrint:

- Opcja **Dodaj** powoduje dodanie serwera funkcji AirPrint do listy. Możesz dodać wiele serwerów funkcji AirPrint.
- **Zaimportuj** plik z wartościami rozdzielanymi przecinkami (.csv) z tymi informacjami. Możesz też użyć opcji **Eksportuj**, aby utworzyć listę dodanych serwerów funkcji AirPrint.

### <a name="get-server-ip-address-resource-path-and-port"></a>Uzyskanie adresu IP serwera, ścieżki zasobu i portu

Aby dodać serwery funkcji AirPrinter, potrzebujesz adresu IP drukarki, ścieżki zasobu i portu. Poniższe kroki przedstawiają sposób uzyskiwania tych informacji.

1. Na komputerze Mac podłączonym do tej samej sieci lokalnej (podsieci) co drukarki AirPrint otwórz **Terminal** (z folderu **/Applications/Utilities**).
2. W terminalu wpisz `ippfind`, a następnie wybierz klawisz Enter.

    Zanotuj informacje o drukarce. Zwrócone informacje mogą wyglądać podobnie do następujących: `ipp://myprinter.local.:631/ipp/port1`. Pierwsza część to nazwa drukarki. Ostatnia część (`ipp/port1`) to ścieżka zasobu.

3. W terminalu wpisz `ping myprinter.local`, a następnie wybierz klawisz Enter.

   Zanotuj adres IP. Zwrócone informacje mogą wyglądać podobnie do następujących: `PING myprinter.local (10.50.25.21)`.

4. Użyj wartości adresu IP i ścieżki zasobu. W tym przykładzie adres IP to `10.50.25.21`, a ścieżka zasobu to `/ipp/port1`.

## <a name="home-screen-layout"></a>Układ ekranu głównego

Ta funkcja ma zastosowanie do:

- System iOS 9.3 lub nowszy
- System iPadOS 13.0 i nowsze

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

### <a name="dock"></a>Dock

Ustawienia okienka **Dock** umożliwiają dodanie do sześciu elementów lub folderów do obszaru Dock na ekranie systemu iOS/iPadOS. Wiele urządzeń obsługuje mniejszą liczbę elementów. Na przykład urządzenia iPhone obsługują maksymalnie cztery elementy. W takim przypadku na urządzeniu wyświetlane są tylko pierwsze cztery dodane elementy.

Możesz dodać maksymalnie **sześć** elementów (łącznie aplikacji i folderów) w obszarze Dock urządzenia.

- **Dodaj**: Umożliwia dodanie aplikacji lub folderów do obszaru Dock urządzenia.
- **Typ**: Umożliwia dodanie **aplikacji** lub **folderu**:

  - **Aplikacja**: wybierz tę opcję, aby dodać aplikacje do obszaru Dock na ekranie. Wprowadź:

    - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS/iPadOS.
    - **Identyfikator pakietu aplikacji**: wprowadź identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemów iOS/iPadOS](bundle-ids-built-in-ios-apps.md).

  - **Folder**: wybierz tę opcję, aby dodać folder do obszaru Dock na ekranie.

    Aplikacje dodawane do strony w folderze są rozmieszczane od lewej do prawej i w takiej samej kolejności jak na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na inną stronę.

    - **Nazwa folderu**: Wprowadź nazwę folderu. Ta nazwa jest widoczna na urządzeniach użytkowników.
    - **Lista stron**: **Dodaj** stronę, a następnie wprowadź następujące właściwości:

      - **Nazwa strony**: wprowadź nazwę strony. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS/iPadOS.
      - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS/iPadOS.
      - **Identyfikator pakietu aplikacji**: wprowadź identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemów iOS/iPadOS](bundle-ids-built-in-ios-apps.md).

      Można dodać maksymalnie **20** stron do obszaru Dock urządzenia.

> [!NOTE]
> Gdy dodasz ikony za pomocą ustawień obszaru Dock, ikony na ekranie głównym i na stronach zostaną zablokowane i nie można będzie ich przenosić. Może to być celowe działanie zasad zarządzania urządzeniami mobilnymi firmy Apple i systemu iOS/iPadOS.

#### <a name="example"></a>Przykład

W poniższym przykładzie ekran Dock zawiera tylko aplikacje Safari, Poczta i Akcje. Aplikacja Poczta została wybrana, aby wyświetlić jej właściwości:

![Przykładowe ustawienia dokowania dla systemów iOS/iPadOS](./media/ios-device-features-settings/FfFiUcP.png)

Po przypisaniu zasad do telefonu iPhone wygląd Docka tego urządzenia jest zbliżony do poniższego obrazu:

![Przykładowy układ Docka telefonu iPhone z systemem iOS/iPadOS](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>Pages

Dodaj strony, które mają być wyświetlane na ekranie głównym, oraz aplikacje, które mają być wyświetlane na każdej ze stron. Aplikacje dodawane do strony są rozmieszczane od lewej do prawej i w takiej samej kolejności jak na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na inną stronę.

> [!TIP]
> Aby zmieniać kolejność elementów na dowolnych listach stron i ekranu głównego, można je przeciągać i upuszczać.

Możesz dodać maksymalnie **40** stron na urządzeniu.

- **Lista stron**: **Dodaj** stronę, a następnie wprowadź następujące właściwości:

  - **Nazwa strony**: wprowadź nazwę strony. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager i *nie jest* widoczna na urządzeniu z systemem iOS/iPadOS.

  Możesz dodać maksymalnie **60** elementów (łącznie aplikacji i folderów) na urządzeniu.

  - **Dodaj**: Umożliwia dodanie aplikacji lub folderów do strony na urządzeniu.

    - **Typ**: Umożliwia dodanie **aplikacji** lub **folderu**:

      - **Aplikacja**: wybierz tę opcję, aby dodać aplikacje do strony na ekranie. Wprowadź też następujące ustawienia:

        - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS/iPadOS.
        - **Identyfikator pakietu aplikacji**: wprowadź identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemów iOS/iPadOS](bundle-ids-built-in-ios-apps.md).

      - **Folder**: wybierz tę opcję, aby dodać folder do obszaru Dock na ekranie.

        Aplikacje dodawane do strony w folderze są rozmieszczane od lewej do prawej i w takiej samej kolejności jak na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na inną stronę.

        - **Nazwa folderu**: Wprowadź nazwę folderu. Ta nazwa jest widoczna na urządzeniach użytkowników.
        - **Dodaj**: Umożliwia dodanie stron do folderu. Wprowadź także następujące właściwości:

          - **Nazwa strony**: wprowadź nazwę strony. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS/iPadOS.
          - **Nazwa aplikacji**: wprowadź nazwę aplikacji. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu z systemem iOS/iPadOS.
          - **Identyfikator pakietu aplikacji**: wprowadź identyfikator pakietu aplikacji. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemów iOS/iPadOS](bundle-ids-built-in-ios-apps.md).

#### <a name="example"></a>Przykład

W poniższym przykładzie dodamy nową stronę o nazwie **Contoso**. Na stronie znajdują się aplikacje Moi znajomi i Ustawienia. Aplikacja Ustawienia została wybrana, aby wyświetlić jej właściwości:

![Przykład ustawień ekranu głównego systemu iOS/iPadOS w usłudze Intune](./media/ios-device-features-settings/Jc2OxyX.png)

Po przypisaniu zasad do telefonu iPhone wygląd strony tego urządzenia jest zbliżony do poniższego obrazu:

![Urządzenie z systemem iOS/iPadOS ze zmodyfikowanym ekranem głównym w usłudze Intune](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>Powiadomienia aplikacji

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Dodaj**: Umożliwia dodanie powiadomień dla aplikacji:

    ![Dodawanie powiadomienia w aplikacji w profilu systemu iOS/iPadOS w usłudze Intune](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **Identyfikator pakietu aplikacji**: wprowadź **Identyfikator pakietu aplikacji** dla aplikacji, którą chcesz dodać. Przykłady można znaleźć w artykule [Identyfikatory pakietów dla wbudowanych aplikacji systemów iOS/iPadOS](bundle-ids-built-in-ios-apps.md).
  - **Nazwa aplikacji**: wprowadź nazwę aplikacji, którą chcesz dodać. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu.
  - **Wydawca**: wprowadź wydawcę dodawanej aplikacji. Ta nazwa jest używana w celach referencyjnych w Centrum administracyjnym programu Microsoft Endpoint Manager. *Nie jest* ona wyświetlana na urządzeniu.
  - **Powiadomienia**: **włącz** lub **wyłącz** powiadomienia wysyłane z aplikacji do urządzenia.
    - **Pokaż w centrum powiadomień**: **włączenie** tego ustawienia powoduje zezwolenie aplikacji na wyświetlanie powiadomień w centrum powiadomień na urządzeniu. **Wyłączenie** tego ustawienia uniemożliwia aplikacji wyświetlanie powiadomień w centrum powiadomień.
    - **Pokaż na ekranie blokady**: **włączenie** tego ustawienia powoduje, że powiadomienia z aplikacji będą wyświetlane na ekranie blokady urządzenia. **Wyłączenie** uniemożliwia aplikacji wyświetlanie powiadomień na ekranie blokady.
    - **Typ alertu**: po odblokowaniu urządzenia wybierz sposób wyświetlania powiadomienia. Dostępne opcje:
      - **Brak**: powiadomienia nie są wyświetlane.
      - **Transparent**: wraz z powiadomieniem jest krótko wyświetlany transparent.
      - **Modalne**: zostanie wyświetlone powiadomienie, które użytkownik będzie musiał ręcznie zamknąć przed kontynuowaniem korzystania z urządzenia.
    - **Znaczek na ikonie aplikacji**: wybierz pozycję **Włącz**, aby dodać znaczek do ikony aplikacji. Znaczek oznacza, że aplikacja wysłała powiadomienie.
    - **Dźwięki**: wybierz pozycję **Włącz**, aby odtwarzać dźwięk po dostarczeniu powiadomienia.

## <a name="lock-screen-message"></a>Komunikat na ekranie blokady

Ta funkcja ma zastosowanie do:

- iOS 9.3 i nowsze
- System iPadOS 13.0 i nowsze

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Informacje dotyczące tagu zasobu**: wprowadź informacje o tagu zasobu urządzenia. Na przykład wprowadź adres `Owned by Contoso Corp` lub `Serial Number: {{serialnumber}}`.

  Wprowadzony tekst zostanie wyświetlony w oknie logowania i na ekranie blokady w urządzeniu.

- **Przypis dolny ekranu blokady**: wprowadź informację, która może ułatwić zwrot urządzenia w przypadku jego utraty lub kradzieży. Możesz podać dowolny tekst. Na przykład wpisz coś takiego: `If found, call Contoso at ...`.

  Możesz też dodać w tych polach informacje dotyczące konkretnych urządzeń za pomocą tokenów urządzeń. Aby na przykład wyświetlić numer seryjny, wprowadź `Serial Number: {{serialnumber}}`. Na ekranie blokady zostanie wyświetlony tekst podobny do tego: `Serial Number 123456789ABC`. Podczas wprowadzania zmiennych użyj nawiasów klamrowych `{{ }}`. [Tokeny konfiguracji aplikacji](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) zawierają listę zmiennych, których można użyć. Możesz też użyć wartości `deviceName` lub innej wartości specyficznej dla urządzenia.

  > [!NOTE]
  > Zmienne nie są weryfikowane w interfejsie użytkownika i uwzględniają wielkość liter. Dlatego mogą pojawić się profile zapisane z niepoprawnymi danymi wejściowymi. Na przykład jeśli podano wartość `{{DeviceID}}` zamiast `{{deviceid}}`, zostanie wyświetlony literał ciągu zamiast unikatowego identyfikatora urządzenia. Upewnij się, że wprowadzasz odpowiednie informacje.

## <a name="single-sign-on"></a>Rejestracja jednokrotna

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Atrybut nazwy użytkownika z usługi AAD**: usługa Intune szuka tego atrybutu dla każdego użytkownika w usłudze Azure AD. Następnie usługa Intune wypełnia odpowiednie pole (na przykład nazwę UPN) przed wygenerowaniem kodu XML instalowanego na urządzeniu. Dostępne opcje:

  - **Główna nazwa użytkownika**: nazwa UPN jest analizowana w następujący sposób:

    ![Atrybut logowania jednokrotnego nazwy użytkownika systemu iOS/iPadOS w usłudze Intune](./media/ios-device-features-settings/User-name-attribute.png)

    Można również zastąpić obszar tekstem wpisywanym w polu tekstowym **Obszar**.

    Na przykład firma Contoso ma kilka regionów, w tym takich jak Europa, Azja i Ameryka Północna. Firma Contoso chce, aby użytkownicy z regionu Azja korzystali z logowania jednokrotnego, natomiast aplikacja wymaga nazwy UPN w formacie `username@asia.contoso.com`. Jeśli zostanie wybrana wartość **Główna nazwa użytkownika**, obszar dla każdego użytkownika zostanie pobrany z usługi Azure AD i może on mieć wartość `contoso.com`. Dlatego dla użytkowników w Azji wybierz pozycję **Główna nazwa użytkownika**, a następnie wprowadź `asia.contoso.com`. Nazwa UPN użytkownika końcowego będzie miała wartość `username@asia.contoso.com` zamiast `username@contoso.com`.

  - **Identyfikator urządzenia usługi Intune**: usługa Intune automatycznie wybiera identyfikator urządzenia usługi Intune.

    Domyślnie dla aplikacji wymagany jest tylko identyfikator urządzenia. Jeśli natomiast aplikacja korzysta z obszaru oraz z identyfikatora urządzenia, możesz wpisać obszar w polu tekstowym Obszar.

    > [!NOTE]
    > Domyślnie nie wpisuj żadnej wartości w polu Obszar, jeśli używasz identyfikatora urządzenia.

  - **Identyfikator urządzenia usługi Azure AD**

- **Obszar**: wprowadź część adresu URL oznaczającą domenę. Na przykład wprowadź `contoso.com`.
- **Przedrostki adresów URL, które będą korzystały z logowania jednokrotnego**: **dodaj** wszystkie adresy URL w organizacji, które wymagają uwierzytelniania za pomocą logowania jednokrotnego użytkownika.

  Kiedy na przykład użytkownik nawiązuje połączenie z dowolną z tych witryn, urządzenie z systemem iOS/iPadOS używa poświadczeń logowania jednokrotnego. Użytkownik nie musi wprowadzać żadnych dodatkowych poświadczeń. Jeśli włączone jest uwierzytelnianie wieloskładnikowe, użytkownicy muszą wykonać drugie uwierzytelnianie.

  > [!NOTE]
  > Te adresy URL muszą być poprawnie sformatowanymi nazwami FQDN. Firma Apple wymaga, aby miały one format `http://<yourURL.domain>`.

  Wzorce dopasowań adresów URL muszą rozpoczynać się od ciągu `http://` lub `https://`. Uruchamiane jest proste dopasowanie ciągu, które wykaże, że prefiks adresu URL `http://www.contoso.com/` jest niezgodny z ciągiem `http://www.contoso.com:80/`. W przypadku systemów iOS 10.0 lub nowszych i iPadOS 13.0 lub nowszych można użyć pojedynczego symbolu wieloznacznego \*, aby wprowadzić wszystkie zgodne wartości. Na przykład wzorzec `http://*.contoso.com/` jest zgodny zarówno z adresem URL `http://store.contoso.com/`, jak i `http://www.contoso.com`.

  Wzorce `http://.com` i `https://.com` są zgodne odpowiednio ze wszystkimi adresami URL protokołów HTTP i HTTPS.

- **Aplikacje, które będą korzystały z logowania jednokrotnego**: **dodaj** aplikacje na urządzeniach użytkowników końcowych, które mogą używać logowania jednokrotnego.

  Tablica `AppIdentifierMatches` musi uwzględniać ciągi zgodne z identyfikatorami pakietu aplikacji. Te ciągi mogą być dokładnymi dopasowaniami (przykład: `com.contoso.myapp`) lub możesz wprowadzić dopasowanie prefiksu w ramach identyfikatora pakietu za pomocą symbolu wieloznacznego \*. Symbol wieloznaczny musi występować po znaku kropki (.) i może zostać użyty tylko raz — na końcu ciągu, na przykład: `com.contoso.*`. Jeśli symbol wieloznaczny zostanie użyty, to dowolna aplikacja o identyfikatorze pakietu rozpoczynającym się od prefiksu uzyskuje dostęp do konta.

  Użyj pola **Nazwa aplikacji**, aby wprowadzić przyjazną nazwę, która ułatwia rozpoznanie identyfikatora pakietu.

- **Certyfikat odnowienia poświadczeń**: w przypadku używania certyfikatów w celu uwierzytelniania (nie haseł) wybierz istniejący certyfikat SCEP lub PFX jako certyfikat uwierzytelniania. Zazwyczaj jest to ten sam certyfikat, który został wdrożony dla użytkownika na potrzeby innych profilów, takich jak profil sieci VPN lub Wi-Fi bądź profil poczty e-mail.

## <a name="web-content-filter"></a>Filtr zawartości sieci Web

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Typ filtru**: Wybierz, aby zezwolić na określone witryny internetowe. Dostępne opcje:

  - **Konfiguruj adresy URL**: użyj wbudowanego filtru internetowego firmy Apple, który wyszukuje język dla dorosłych, w tym przekleństwa i słowa o charakterze seksualnym. Ta funkcja ocenia każdą stronę internetową podczas ładowania oraz identyfikuje i blokuje nieodpowiednią zawartość. Możesz również dodać adresy URL, które nie mają być sprawdzane przez filtr. Ponadto możesz zablokować określone adresy URL, niezależnie od ustawień filtru firmy Apple.

    - **Dozwolone adresy URL**: **dodaj** adresy URL, na które chcesz zezwolić. Te adresy URL są pomijane przez filtr internetowy firmy Apple.

        > [!NOTE]
        > Wprowadzone adresy to adresy URL, które nie mają być oceniane przez filtr internetowy firmy Apple. Te adresy URL nie stanowią listy dozwolonych witryn internetowych. Aby utworzyć listę dozwolonych witryn internetowych, należy ustawić **typ filtru** na pozycję **Tylko określone witryny internetowe**.

    - **Zablokowane adresy URL**: **dodaj** adresy URL, których otwieranie ma zostać zatrzymane, niezależnie od ustawień filtru internetowego firmy Apple.

  - **Tylko określone witryny internetowe** (tylko przeglądarka internetowa Safari): Te adresy URL są dodawane do zakładek przeglądarki Safari. Użytkownik jest uprawniony **wyłącznie** do odwiedzania tych witryn internetowych; nie będzie można otwierać żadnych innych witryn. Użyj tej opcji tylko wtedy, gdy znasz dokładną listę adresów URL, do których użytkownicy mogą uzyskiwać dostęp.

    - **Adres URL**: wprowadź adres URL dozwolonej witryny internetowej. Na przykład wprowadź `https://www.contoso.com`.
    - **Ścieżka zakładki**: firma Apple zmieniła to ustawienie. Wszystkie zakładki są umieszczane w folderze **Zatwierdzone witryny**. Zakładki nie są umieszczane w lokalizacji wskazanej wprowadzoną ścieżką zakładki.
    - **Tytuł**: wprowadź opisowy tytuł zakładki.

    Jeśli nie wprowadzisz żadnych adresów URL, użytkownicy końcowi nie będą mogli uzyskiwać dostęp do żadnych witryn internetowych, z wyjątkiem `microsoft.com`, `microsoft.net`, i `apple.com`. Usługa Intune automatycznie zezwala na dostęp do tych adresów URL.

## <a name="single-sign-on-app-extension"></a>Rozszerzenie aplikacji — rejestracja jednokrotna

Ta funkcja ma zastosowanie do:

- System iOS 13.0 lub nowszy
- System iPadOS 13.0 lub nowszy

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Typ rozszerzenia aplikacji logowania jednokrotnego**: wybierz typ rozszerzenia aplikacji logowania jednokrotnego. Dostępne opcje:

  - **Nieskonfigurowane**: rozszerzenia aplikacji nie są używane. Aby wyłączyć rozszerzenie aplikacji, możesz przełączyć typ rozszerzenia aplikacji logowania jednokrotnego na wartość **Nieskonfigurowane**.
  - **Przekierowanie**: użyj ogólnego, dostosowywalnego rozszerzenia aplikacji przekierowania, aby przeprowadzać logowanie jednokrotne za pomocą nowoczesnych przepływów uwierzytelniania. Upewnij się, że znasz identyfikator rozszerzenia dla rozszerzenia aplikacji w organizacji.
  - **Poświadczenie**: użyj ogólnego, dostosowywalnego rozszerzenia aplikacji poświadczenia, aby przeprowadzać logowanie jednokrotne za pomocą przepływów uwierzytelniania typu wyzwanie-odpowiedź. Upewnij się, że znasz identyfikator rozszerzenia dla rozszerzenia aplikacji w organizacji.
  - **Kerberos**: użyj wbudowanego rozszerzenia protokołu Kerberos firmy Apple, które jest zawarte w systemach iOS 13.0 i nowszych oraz iPadOS 13.0 i nowszych. Ta opcja jest specyficzną dla protokołu Kerberos wersją rozszerzenia aplikacji **Poświadczenie**.

  > [!TIP]
  > W przypadku typów **Przekierowanie** i **Poświadczenie** dodajesz własne wartości konfiguracji w celu przekazania przez rozszerzenie. Jeśli używasz typu **Poświadczenie**, rozważ użycie wbudowanych ustawień konfiguracji dostarczonych przez firmę Apple w typie **Kerberos**.

- **Identyfikator rozszerzenia** (Przekierowanie i Poświadczenie): wprowadź identyfikator pakietu określający rozszerzenie aplikacji logowania jednokrotnego, na przykład `com.apple.extensiblesso`.

- **Identyfikator zespołu** (Przekierowanie i Poświadczenie): wprowadź identyfikator zespołu dla rozszerzenia aplikacji logowania jednokrotnego. Identyfikator zespołu to 10-znakowy ciąg alfanumeryczny (cyfry i litery) generowany przez firmę Apple, taki jak `ABCDE12345`. Identyfikator zespołu nie jest wymagany.

  Aby uzyskać więcej informacji, skorzystaj z linku [Locate your Team ID](https://help.apple.com/developer-account/#/dev55c3c710c) (Znajdź swój identyfikator zespołu) — zostanie otwarta witryna internetowa firmy Apple.

- **Obszar** (Poświadczenie i Kerberos): wprowadź nazwę obszaru uwierzytelniania. Nazwa obszaru powinna być pisana wielkimi literami, na przykład `CONTOSO.COM`. Zazwyczaj nazwa obszaru jest taka sama, jak nazwa domeny DNS, ale pisana w całości wielkimi literami.

- **Domeny** (Poświadczenie i Kerberos): wprowadź nazwy domen lub hostów witryn, które mogą być uwierzytelniane za pomocą logowania jednokrotnego. Jeśli na przykład witryna internetowa to `mysite.contoso.com`, nazwą hosta będzie `mysite`, a nazwą domeny będzie `contoso.com`. Gdy użytkownicy będą łączyć się z dowolną z tych witryn, rozszerzenie aplikacji obsłuży wyzwanie uwierzytelniania. To uwierzytelnianie umożliwia użytkownikom logowanie się przy użyciu funkcji Face ID, Touch ID lub kodu PIN/ kodu dostępu firmy Apple.

  - Wszystkie domeny w profilach usługi Intune rozszerzenia aplikacji logowania jednokrotnego muszą być unikatowe. Nie można powtórzyć domeny w żadnym profilu rozszerzenia aplikacji logowania, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - W tych domenach nie jest rozróżniana wielkość liter.

- **Adresy URL** (tylko Przekierowanie): wprowadź prefiksy adresów URL swoich dostawców tożsamości, w których imieniu rozszerzenie aplikacji przekierowania wykonuje logowanie jednokrotne. Gdy użytkownik zostanie przekierowany do tych adresów URL, rozszerzenie aplikacji logowana jednokrotnego będzie interweniować i monitować o logowanie jednokrotne.

  - Wszystkie adresy URL w profilach usługi Intune rozszerzenia aplikacji logowania jednokrotnego muszą być unikatowe. Nie można powtórzyć domeny w żadnym profilu rozszerzenia aplikacji logowania jednokrotnego, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - Adresy URL muszą zaczynać się od ciagu http:// lub https://.

- **Konfiguracja dodatkowa** (Przekierowanie i Poświadczenie): wprowadź dodatkowe dane specyficzne dla rozszerzenia, które mają zostać przekazane do rozszerzenia aplikacji logowania jednokrotnego:
  - **Klucz**: wprowadź nazwę elementu, który chcesz dodać, na przykład `user name`.
  - **Typ**: wprowadź typ danych. Dostępne opcje:

    - String
    - Wartość logiczna: w polu **Wartość konfiguracji** wprowadź wartość `True` lub `False`.
    - Liczba całkowita: w polu **Wartość konfiguracji** wprowadź liczbę.
    
  - **Wartość**: wprowadź dane.

  - **Dodaj**: wybierz, aby dodać klucze konfiguracji.

- **Użycie pęku kluczy** (tylko Kerberos): wybierz opcję **Blokuj**, aby uniemożliwić zapisywanie i przechowywanie haseł w pęku kluczy. Opcja **Nieskonfigurowane** (wartość domyślna) umożliwia zapisywanie i przechowywanie haseł w pęku kluczy.
- **Face ID, Touch ID lub kod dostępu** (tylko Kerberos): opcja **Wymagaj** zmusza użytkowników, aby wprowadzili identyfikator Face ID, Touch ID lub kod dostępu firmy Apple w celu zalogowania się do dodanych domen. Opcja **Nieskonfigurowane** (wartość domyślna) nie wymaga użycia danych biometrycznych ani kodu dostępu w celu zalogowania.
- **Obszar domyślny** (tylko Kerberos): wybierz opcję **Włącz**, aby ustawić wartość właściwości **Obszar** wprowadzoną jako obszar domyślny. Opcja **Nieskonfigurowane** (wartość domyślna) nie ustawia obszaru domyślnego.

  > [!TIP]
  > - **Włącz** to ustawienie, jeśli konfigurujesz wiele rozszerzeń aplikacji logowania jednokrotnego protokołu Kerberos w organizacji.
  > - **Włącz** to ustawienie, jeśli używasz wielu obszarów. Powoduje to ustawienie wartości **obszaru** wprowadzonej jako obszar domyślny.
  > - Jeśli masz tylko jeden obszar, pozostaw opcję **Nieskonfigurowane** (wartość domyślna).

- **Nazwa podmiotu zabezpieczeń** (tylko Kerberos): wprowadź nazwę użytkownika podmiotu zabezpieczeń protokołu Kerberos. Nie trzeba dołączać nazwy obszaru. Na przykład w adresie `user@contoso.com` `user` jest nazwą podmiotu zabezpieczeń, a `contoso.com` jest nazwą obszaru.

  > [!TIP]
  > - W nazwie podmiotu zabezpieczeń można również użyć zmiennych, wprowadzając nawiasy klamrowe `{{ }}`. Aby na przykład wyświetlić nazwę użytkownika, wprowadź `Username: {{username}}`. 
  > - Zachowaj ostrożność, używając podstawienia zmiennej, ponieważ zmienne nie są weryfikowanie w interfejsie użytkownika i uwzględniają wielkość liter. Upewnij się, że wprowadzasz odpowiednie informacje.

- **Kod lokacji usługi Active Directory** (tylko Kerberos): wprowadź nazwę lokacji usługi Active Directory, której ma użyć rozszerzenie protokołu Kerberos. Zmiana tej wartości może nie być konieczna, ponieważ rozszerzenie protokołu Kerberos może automatycznie znajdować kod lokacji usługi Active Directory.
- **Nazwa pamięci podręcznej** (tylko Kerberos): wprowadź nazwę usług Generic Security Services (GSS) pamięci podręcznej protokołu Kerberos. Najprawdopodobniej nie trzeba będzie ustawiać tej wartości.
- **Identyfikatory pakietów aplikacji** (tylko Kerberos): **Dodaj** identyfikatory pakietów aplikacji, które powinny używać logowania jednokrotnego na urządzeniach. Te aplikacje mogą uzyskiwać dostęp do biletu uprawniającego do przyznania biletu protokołu Kerberos, czyli do biletu uwierzytelniania, i uwierzytelniają użytkowników w usługach, do których mają dostęp.
- **Mapowanie obszaru domeny** (tylko Kerberos): **Dodaj** sufiksy DNS domeny, które powinny być mapowane na obszar. Użyj tego ustawienia, jeśli nazwy DNS hostów nie są zgodne z nazwą obszaru. Najprawdopodobniej nie trzeba będzie tworzyć tego niestandardowego mapowania domeny na obszar.
- **Certyfikat PKINIT** (tylko Kerberos): **Wybierz** certyfikat kryptografii klucza publicznego na użytek uwierzytelniania początkowego (PKINIT), którego można użyć na potrzeby uwierzytelniania protokołu Kerberos. Możesz wybrać spośród certyfikatów [PKCS](../protect/certficates-pfx-configure.md) lub [SCEP](../protect/certificates-scep-configure.md), które zostały dodane do usługi Intune. Aby uzyskać więcej informacji o certyfikatach, zobacz [Używanie certyfikatów do uwierzytelniania w usłudze Microsoft Intune](../protect/certificates-configure.md).

## <a name="wallpaper"></a>Tapeta

Jeśli profil bez obrazu zostanie przypisany do urządzeń z istniejącym obrazem, mogą wystąpić nieoczekiwane zachowania. Na przykład profil zostanie utworzony bez obrazu. Ten profil jest przypisany do urządzeń, które mają już obraz. W tym scenariuszu obraz może zostać zmieniony na obraz domyślny urządzenia lub oryginalny obraz może pozostać na urządzeniu. To zachowanie jest kontrolowane i ograniczane przez platformę MDM firmy Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Lokalizacja wyświetlania tapety**: wybierz lokalizację wyświetlania obrazu na urządzeniu. Dostępne opcje:
  - **Nieskonfigurowane**: obraz niestandardowy nie jest dodawany do urządzenia. Urządzenie używa wartości domyślnej systemu operacyjnego.
  - **Ekran blokady**: dodaje obraz do ekranu blokady.
  - **Ekran główny**: dodaje obraz do ekranu głównego.
  - **Ekran blokady i ekran główny**: używa tego samego obrazu na ekranie blokady i na ekranie głównym.
- **Obraz tapety**: przekaż istniejący obraz PNG, JPG lub JPEG, którego chcesz użyć. Upewnij się, że rozmiar pliku jest mniejszy niż 750 KB. Możesz również **usunąć** obraz, który został dodany.

> [!TIP]
> Aby wyświetlać różne obrazy na ekranie blokady i na ekranie głównym, utwórz profil przy użyciu obrazu ekranu blokady. Utwórz inny profil przy użyciu obrazu ekranu głównego. Przypisz obydwa profile do grup użytkowników lub urządzeń systemu iOS/iPadOS.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](../device-profile-monitor.md).

Można również utworzyć profile funkcji urządzenia dla urządzeń z systemem [macOS](macos-device-features-settings.md).
