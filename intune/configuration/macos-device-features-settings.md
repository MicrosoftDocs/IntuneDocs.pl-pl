---
title: Ustawienia funkcji urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z ustawieniami umożliwiającymi konfigurowanie urządzeń z systemem macOS pod kątem obsługi funkcji AirPrint i dostosowywanie okna logowania w celu wyświetlania lub ukrywania przycisków zasilania w usłudze Microsoft Intune. Zapoznaj się również z krokami wymaganymi do pobrania ustawień adresu IP, ścieżki i portu serwera funkcji AirPrint w sieci. Te ustawienia zastosowane w profilu konfiguracji urządzenia umożliwiają skonfigurowanie funkcji urządzeń z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/02/2019
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
ms.openlocfilehash: 17d0baeeb6b193be6acf8d6087c26a66b18642c5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506673"
---
# <a name="macos-device-feature-settings-in-intune"></a>Ustawienia funkcji urządzenia z systemem macOS w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Ustawienia wbudowane w usługę Intune umożliwiają dostosowanie funkcji na urządzeniach z systemem macOS. Administratorzy mogą na przykład dodawać AirPrint drukarki, decydować o sposobie logowania użytkowników, konfigurować sterowanie mocą, korzystać z uwierzytelniania jednokrotnego i nie tylko.

Z tych funkcji można korzystać w celu kontrolowania urządzeń z systemem macOS w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM).

Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień. Przedstawiono w nim również listę czynności wymaganych do uzyskania adresu IP, ścieżki i portu drukarek AirPrint przy użyciu aplikacji Terminal (emulatora). Aby uzyskać więcej informacji na temat funkcji urządzenia, przejdź do pozycji [Dodaj ustawienia funkcji urządzenia z systemem iOS lub macOS](device-features-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia sieci macOS](device-features-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji, z uwzględnieniem niektórych ustawień, które są stosowane do wszystkich opcji rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [Rejestrowanie macOS](../enrollment/macos-enroll.md).

## <a name="airprint"></a>Funkcja AirPrint

### <a name="settings-apply-to-device-enrollment"></a>Ustawienia dotyczą: Rejestracja urządzenia

- **Adres IP**: podaj adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do drukarki w aplikacji Terminal. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Ścieżka**: wprowadź ścieżkę drukarki. W przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Port** (system iOS 11.0 i nowsze): podaj port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego.
- **TLS** (system iOS 11.0 i nowsze): wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS).

- **Dodaj** serwer funkcji AirPrint. Można dodać wiele serwerów z funkcją AirPrint.

Można również **zaimportować** plik rozdzielany przecinkami (CSV) zawierający listę drukarek z funkcją AirPrint. Po dodaniu drukarek z funkcją AirPrint w usłudze Intune można również **wyeksportować** tę listę.

### <a name="get-the-ip-address-and-path"></a>Uzyskiwanie adresu IP i ścieżki

Aby dodać serwery funkcji AirPrinter, potrzebujesz adresu IP drukarki, ścieżki zasobu i portu. Poniższe kroki przedstawiają sposób uzyskiwania tych informacji.

1. Na komputerze Mac podłączonym do tej samej sieci lokalnej (podsieci) co drukarki AirPrint otwórz **Terminal** (z folderu **/Applications/Utilities**).
2. W aplikacji Terminal wpisz `ippfind`, a następnie wybierz klawisz Enter.

    Zanotuj informacje o drukarce. Zwrócone informacje mogą wyglądać podobnie do następujących: `ipp://myprinter.local.:631/ipp/port1`. Pierwsza część to nazwa drukarki. Ostatnia część (`ipp/port1`) to ścieżka zasobu.

3. W terminalu wpisz `ping myprinter.local`, a następnie wybierz klawisz Enter.

   Zanotuj adres IP. Zwrócone informacje mogą wyglądać podobnie do następujących: `PING myprinter.local (10.50.25.21)`.

4. Użyj wartości adresu IP i ścieżki zasobu. W tym przykładzie adres IP to `10.50.25.21`, a ścieżka zasobu to `/ipp/port1`.

## <a name="login-items"></a>Elementy logowania

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Pliki, foldery i aplikacje niestandardowe**: **Dodaj** ścieżkę do pliku, folderu, aplikacji niestandardowej lub aplikacji systemowej, którą chcesz otworzyć, gdy użytkownik zaloguje się na urządzeniu. Aplikacje systemowe lub aplikacje skompilowane lub dostosowane do organizacji zwykle znajdują się w folderze `Applications` ze ścieżką podobną do `/Applications/AppName.app`. 

  Można dodać wiele plików, folderów i aplikacji. Wprowadź na przykład:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Podczas dodawania dowolnej aplikacji, folderu lub pliku upewnij się, że została wprowadzona poprawna ścieżka. Nie wszystkie elementy znajdują się w folderze `Applications`. Jeśli Użytkownik przeniesie element z jednej lokalizacji do drugiej, zmieni się ścieżka. Ten przeniesiony element nie zostanie otwarty po zalogowaniu się użytkownika.

## <a name="login-window"></a>Okno logowania

### <a name="settings-apply-to-device-enrollment"></a>Ustawienia dotyczą: Rejestracja urządzenia

#### <a name="window-layout"></a>Układ okna

- **Pokaż dodatkowe informacje na pasku menu**: jeśli obszar czasu na pasku menu jest zaznaczony, wybranie opcji **Zezwalaj** powoduje wyświetlenie nazwy hosta i wersji systemu macOS. W przypadku wybrania opcji **Nie skonfigurowano** (ustawienie domyślne) informacje te nie są wyświetlane na pasku menu.
- **Baner**: wprowadź komunikat, który ma być wyświetlany na ekranie logowania urządzenia. Na przykład możesz wprowadzić komunikat powitalny, informacje o swojej organizacji lub informacje o rzeczach zgubionych i znalezionych.
- **Wybierz format logowania**: wybierz sposób logowania się użytkowników do urządzenia. Dostępne opcje:
  - **Monituj o nazwę użytkownika i hasło** (ustawienie domyślne): użytkownik musi wprowadzić nazwę użytkownika i hasło.
  - **Wyświetl listę wszystkich użytkowników i monituj o podanie hasła**: użytkownik musi wybrać swoją nazwę użytkownika z listy, a następnie wprowadzić hasło. Należy również skonfigurować poniższe ustawienia:

    - **Użytkownicy lokalni**: w przypadku wybrania opcji **Ukryj** konta użytkowników lokalnych, np. konto standardowe i konto administratora, nie są wyświetlane na liście użytkowników. Widoczne są tylko konta sieciowe i konta użytkowników systemu. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont użytkowników lokalnych na liście użytkowników.
    - **Konta mobilne**: w przypadku wybrania opcji **Ukryj** konta mobilne nie są wyświetlane na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont mobilnych na liście użytkowników. Niektóre konta mobilne mogą być widoczne jako użytkownicy sieciowi.
    - **Użytkownicy sieciowi**: wybranie opcji **Pokaż** powoduje wyświetlenie nazw użytkowników sieciowych na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje, że konta użytkowników sieciowych nie są wyświetlane.
    - **Administratorzy**: wybranie opcji **Ukryj** powoduje, że konta administratorów nie są wyświetlane na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont administratorów na liście użytkowników.
    - **Inni użytkownicy**: wybranie opcji **Pokaż** powoduje wyświetlenie nazw użytkowników z kategorii **Inni...** na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje, że konta innych użytkowników nie są wyświetlane.

#### <a name="login-screen-power-settings"></a>Ustawienia zasilania ekranu logowania

- **Przycisk Wyłącz**: wybranie opcji **Ukryj** powoduje ukrycie przycisku wyłączania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku wyłączania.
- **Przycisk Uruchom ponownie**: wybranie opcji **Ukryj** powoduje ukrycie przycisku ponownego uruchamiania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku ponownego uruchamiania.
- **Przycisk Uśpij**: wybranie opcji **Ukryj** powoduje ukrycie przycisku usypiania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku usypiania.

#### <a name="other"></a>Inne

- **Wyłącz logowanie użytkownika z konsoli**: wybranie opcji **Wyłącz** powoduje ukrycie wiersza polecenia systemu macOS używanego do logowania. W przypadku typowych użytkowników należy wybrać opcję **Wyłącz**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) umożliwia zaawansowanym użytkownikom zalogowanie się przy użyciu wiersza polecenia systemu macOS. Aby przejść do trybu konsoli, użytkownicy muszą wprowadzić ciąg `>console` w polu Nazwa użytkownika, a następnie uwierzytelnić się w oknie konsoli.

#### <a name="apple-menu"></a>Menu Apple

Za pomocą następujących ustawień można konfigurować zakres czynności dostępnych dla użytkowników zalogowanych do swoich urządzeń.

- **Wyłącz polecenie Wyłącz**: wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Zamknij**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Zamknij** w menu na urządzeniu.
- **Wyłącz polecenie Uruchom ponownie**: wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Uruchom ponownie**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Uruchom ponownie** w menu na urządzeniu.
- **Wyłącz polecenie Wyłącz zasilanie**: wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Wyłącz zasilanie**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Wyłącz zasilanie** w menu na urządzeniu.
- **Wyłącz polecenie Wyloguj** (system macOS 10.13 i nowsze): wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Wyloguj**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Wyloguj** w menu na urządzeniu.
- **Wyłącz pozycję Zablokuj ekran** (system macOS 10.13 i nowsze): wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Zablokuj ekran**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Zablokuj ekran** w menu na urządzeniu.

## <a name="single-sign-on-app-extension"></a>Rozszerzenie aplikacji — rejestracja jednokrotna

Ta funkcja ma zastosowanie do:

- System macOS 10.15 i nowsze

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji 

- **Typ rozszerzenia aplikacji SSO**: Wybierz typ rozszerzenia aplikacji SSO logowania jednokrotnego. Po zapisaniu profilu rozszerzenia aplikacji SSO nie można zmienić typu rozszerzenia aplikacji logowania jednokrotnego. Dostępne opcje:

  - **Nie skonfigurowano**: rozszerzenia aplikacji nie są używane. Aby wyłączyć rozszerzenie aplikacji logowania jednokrotnego, przełącz typ rozszerzenia aplikacji SSO z **protokołu Kerberos** lub **poświadczenia** na **Nieskonfigurowane**.
  - **Poświadczenie**: Użyj ogólnego, dostosowywalnego rozszerzenia aplikacji poświadczeń do korzystania z logowania jednokrotnego. Upewnij się, że znasz identyfikator rozszerzenia i identyfikator zespołu dla rozszerzenia aplikacji SSO w organizacji.  
  - **Kerberos**: Użyj wbudowanego rozszerzenia protokołu Kerberos firmy Apple, które jest dołączone do macOS Catalina 10,15 i nowszych. Ta opcja jest specyficzną dla protokołu Kerberos wersją rozszerzenia aplikacji **Credential** .

  > [!TIP]
  > Przy użyciu typu **poświadczenia** należy dodać własne wartości konfiguracji, aby przejść przez rozszerzenie. Zamiast tego należy rozważyć użycie wbudowanych ustawień konfiguracji dostarczonych przez firmę Apple w typie **Kerberos** .

- **Identyfikator rozszerzenia** (tylko poświadczenia): Wprowadź identyfikator pakietu identyfikujący rozszerzenie aplikacji logowania jednokrotnego, takie jak `com.apple.ssoexample`.
- **Identyfikator zespołu** (tylko poświadczenia): Wprowadź identyfikator zespołu rozszerzenia aplikacji logowania jednokrotnego. Identyfikator zespołu to 10-znakowy ciąg alfanumeryczny (cyfry i litery) generowany przez firmę Apple, taki jak `ABCDE12345`. 

  [Znajdź swój identyfikator zespołu](https://help.apple.com/developer-account/#/dev55c3c710c) (otwiera witrynę sieci Web firmy Apple), aby uzyskać więcej informacji.

- **Obszar**: Wprowadź nazwę obszaru protokołu Kerberos. Nazwa obszaru powinna być Wielka litera, taka jak `CONTOSO.COM`. Zazwyczaj nazwa obszaru jest taka sama jak nazwa domeny DNS, ale w przypadku wszystkich wielkich liter.
- **Domeny**: Wprowadź nazwy domen lub hostów witryn, które mogą być uwierzytelniane za pomocą logowania jednokrotnego. Na przykład jeśli witryna sieci Web jest `mysite.contoso.com`, wówczas `mysite` jest nazwą hosta, a `contoso.com` jest nazwą domeny. Gdy użytkownicy łączą się z dowolną z tych witryn, rozszerzenie aplikacji obsługuje wyzwanie uwierzytelniania. To uwierzytelnianie umożliwia użytkownikom logowanie się przy użyciu identyfikatora, Touch ID lub Apple pincode/kodu dostępu.

  - Wszystkie domeny w profilach usługi Intune rozszerzenia aplikacji logowania jednokrotnego muszą być unikatowe. Nie można powtórzyć domeny w dowolnym profilu rozszerzenia aplikacji logowania, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - W tych domenach nie jest rozróżniana wielkość liter.

- **Dodatkowa konfiguracja** (tylko poświadczenia): wprowadź dodatkowe dane specyficzne dla rozszerzenia, które mają zostać przekazane do rozszerzenia aplikacji SSO:
  - **Klucz konfiguracji**: Wprowadź nazwę elementu, który chcesz dodać, na przykład `user name`.
  - **Typ wartości**: wprowadź typ danych. Dostępne opcje:

    - String
    - Wartość logiczna: w **wartości konfiguracji**wprowadź `True` lub `False`.
    - Liczba całkowita: w polu **wartość konfiguracji**wprowadź liczbę.
    
  - **Wartość konfiguracji**: Wprowadź dane.
  
  - **Dodaj**: Wybierz, aby dodać klucze konfiguracji.

- **Użycie łańcucha kluczy** (tylko Kerberos): wybierz opcję **Blokuj** , aby uniemożliwić zapisywanie i przechowywanie haseł w łańcuchu kluczy. **Nie skonfigurowano** (domyślnie) umożliwia zapisywanie i przechowywanie haseł w pęku kluczy.  
- **Identyfikator ekranu, Touch ID lub kod dostępu** (tylko protokół Kerberos): **Wymagaj od** użytkowników, aby wprowadzali identyfikator swojej firmy, identyfikator dotykowy lub kod dostępu firmy Apple w celu zalogowania się do dodanych domen. **Nie skonfigurowano** (domyślnie) nie wymaga, aby użytkownicy korzystali z biometrii lub kodu dostępu do logowania.
- **Obszar domyślny** (tylko Kerberos): wybierz opcję **Włącz** , aby ustawić wartość **obszaru** wprowadzoną jako domyślny obszar. **Nieskonfigurowane** (domyślnie) nie ustawia obszaru domyślnego.

  > [!TIP]
  > - **Włącz** to ustawienie, jeśli konfigurujesz wiele rozszerzeń aplikacji SSO protokołu Kerberos w organizacji.
  > - **Włącz** to ustawienie, jeśli używasz wielu obszarów. Ustawia wartość **obszaru** wprowadzoną jako domyślny obszar.
  > - Jeśli masz tylko jeden obszar, pozostaw go **nieskonfigurowanym** (domyślnie).

- **Wykrywanie** automatyczne (tylko Kerberos): po ustawieniu opcji **Blokuj**rozszerzenie protokołu Kerberos nie używa protokołu LDAP i DNS do określenia jego nazwy Active Directory lokacji. **Nie skonfigurowano** (wartość domyślna) umożliwia rozszerzeniu automatyczne Znajdowanie nazwy lokacji Active Directory.
- **Zmiany hasła** (tylko Kerberos): **blokowanie** uniemożliwia użytkownikom zmianę haseł używanych do logowania się do wprowadzonych domen. **Nie skonfigurowano** (wartość domyślna) umożliwia zmianę hasła.  
- **Synchronizacja haseł** (tylko Kerberos): wybierz opcję **Włącz** , aby synchronizować hasła lokalne użytkowników z usługą Azure AD. **Nie skonfigurowano** (domyślnie) powoduje wyłączenie synchronizacji haseł z usługą Azure AD. Użyj tego ustawienia jako alternatywy lub kopii zapasowej na potrzeby logowania jednokrotnego. To ustawienie nie działa, jeśli użytkownicy są zalogowani przy użyciu konta Apple Mobile.
- **Złożoność hasła dla systemu Windows Server Active Directory** (tylko protokół Kerberos): wybierz opcję **Wymagaj** , aby wymusić spełnienie hasła przez użytkownika Active Directory wymagania dotyczące złożoności haseł. Aby uzyskać więcej informacji, zobacz [hasło musi spełniać wymagania dotyczące złożoności](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) . **Nie skonfigurowano** (wartość domyślna) nie wymaga od użytkowników spełnienia wymagań dotyczących hasła Active Directory.
- **Minimalna długość hasła** (tylko Kerberos): wprowadź minimalną liczbę znaków, które mogą wprowadzać hasło użytkownika. **Nie skonfigurowano** (wartość domyślna) nie wymusza minimalnej długości hasła dla użytkowników.
- **Limit ponownego użycia hasła** (tylko protokół Kerberos): wprowadź liczbę nowych haseł z 1-24, które muszą zostać użyte, dopóki nie będzie można ponownie użyć poprzedniego hasła w domenie. **Nie skonfigurowano** (wartość domyślna) nie wymusza ponownego użycia hasła.
- **Minimalny wiek hasła** (tylko protokół Kerberos): wprowadź liczbę dni, przez które hasło musi być używane w domenie, zanim użytkownik będzie mógł je zmienić. **Nie skonfigurowano** (wartość domyślna) nie wymusza minimalnego wieku hasła, zanim będzie można je zmienić.
- **Powiadomienie o wygaśnięciu hasła** (tylko protokół Kerberos): wprowadź liczbę dni, po upływie których hasło zostanie powiadomione przez użytkowników o wygaśnięciu hasła. **Nie skonfigurowano** (wartość domyślna) używa `15` dni.
- **Wygaśnięcie hasła** (tylko protokół Kerberos): wprowadź liczbę dni, po upływie których należy zmienić hasło. **Nie skonfigurowano** (wartość domyślna) oznacza, że hasła użytkowników nigdy nie wygasną.
- **Nazwa podmiotu zabezpieczeń** (tylko protokół Kerberos): Wprowadź nazwę użytkownika podmiotu zabezpieczeń protokołu Kerberos. Nie trzeba dołączać nazwy obszaru. Na przykład w `user@contoso.com`, `user` jest nazwą główną, a `contoso.com` jest nazwą obszaru.
- **Kod lokacji Active Directory** (tylko protokół Kerberos): Wprowadź nazwę witryny Active Directory, która ma być używana przez rozszerzenie protokołu Kerberos. Zmiana tej wartości może nie być konieczna, ponieważ rozszerzenie protokołu Kerberos może automatycznie znaleźć kod lokacji Active Directory.
- **Nazwa pamięci podręcznej** (tylko protokół Kerberos): Wprowadź nazwę Generic Security Services (GSS) pamięci podręcznej protokołu Kerberos. Najprawdopodobniej nie musisz ustawiać tej wartości.  
- **Komunikat wymagania dotyczącego hasła** (tylko protokół Kerberos): wprowadź wersję tekstową wymagań dotyczących hasła organizacji, które są widoczne dla użytkowników. Komunikat jest wyświetlany, jeśli nie są wymagane wymagania dotyczące złożoności hasła Active Directory lub nie wprowadzono minimalnej długości hasła.  
- **Identyfikatory pakietu aplikacji** (tylko Kerberos): **Dodaj** identyfikatory zbioru aplikacji, które powinny używać logowania jednokrotnego na urządzeniach. Te aplikacje otrzymują dostęp do biletu uprawniającego do przyznania biletu protokołu Kerberos, biletu uwierzytelniania i uwierzytelniania użytkowników do usług, do których mają dostęp.
- **Mapowanie obszaru domeny** (tylko Kerberos): **Dodaj** sufiksy DNS domeny, które powinny być mapowane na obszar. Użyj tego ustawienia, jeśli nazwy DNS hostów nie pasują do nazwy obszaru. Najprawdopodobniej nie musisz tworzyć tego niestandardowego mapowania domeny-obszaru.

## <a name="associated-domains"></a>Skojarzone domeny

W usłudze Intune:

- Dodaj wiele skojarzeń między aplikacjami.
- Skojarz wiele domen z tą samą aplikacją.

Ta funkcja ma zastosowanie do:

- System macOS 10.15 i nowsze

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Identyfikator aplikacji**: Wprowadź identyfikator aplikacji, która ma zostać skojarzona z witryną sieci Web. Identyfikator aplikacji zawiera identyfikator zespołu i identyfikator pakietu: `TeamID.BundleID`.

  Identyfikator zespołu to 10-znakowe znaki alfanumeryczne (litery i cyfry) wygenerowane przez firmę Apple dla deweloperów aplikacji, takie jak `ABCDE12345`. [Znajdź identyfikator zespołu](https://help.apple.com/developer-account/#/dev55c3c710c)   (otwiera witrynę sieci Web firmy Apple), aby uzyskać więcej informacji.

  Identyfikator pakietu jednoznacznie identyfikuje aplikację i zazwyczaj jest formatowany w odwrotnej notacji nazwy domeny. Na przykład identyfikator pakietu wyszukiwania jest `com.apple.finder`. Aby znaleźć identyfikator pakietu, użyj programu AppleScript w terminalu:

  `osascript -e 'id of app "ExampleApp"'`

- **Domena**: Wprowadź domenę witryny sieci Web, która ma zostać skojarzona z aplikacją. Domena zawiera typ usługi i w pełni kwalifikowana nazwa hosta, takie jak `webcredentials:www.contoso.com`.

  Można dopasować wszystkie poddomeny skojarzonej domeny, wprowadzając `*.` (symbol wieloznaczny gwiazdki i kropkę) przed rozpoczęciem domeny. Okres jest wymagany. Dokładne domeny mają wyższy priorytet niż w przypadku domen wieloznacznych. Dlatego wzorce z domen nadrzędnych są dopasowywane, *Jeśli* w pełni kwalifikowana poddomena nie zostanie znaleziona.

  Typem usługi może być:

  - **authsrv**: rozszerzenie aplikacji — logowanie jednokrotne
  - **applink**: połączenie uniwersalne
  - **poświadczenia webcredentials**: Autowypełnianie hasła

- **Dodaj**: Wybierz, aby dodać aplikacje i skojarzone domeny.

> [!TIP]
> Aby rozwiązać problem, na urządzeniu macOS Otwórz aplet **Preferencje systemowe**  > **Profile**. Potwierdź, że utworzony profil znajduje się na liście Profile urządzeń. Jeśli jest ona wyświetlana, upewnij się, że **Konfiguracja skojarzonych domen** znajduje się w profilu i zawiera poprawne identyfikatory aplikacji i domen.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Możesz również skonfigurować funkcje urządzenia w systemie [iOS](ios-device-features-settings.md).
