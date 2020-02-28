---
title: Ustawienia funkcji urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z ustawieniami umożliwiającymi konfigurowanie urządzeń z systemem macOS pod kątem obsługi funkcji AirPrint i dostosowywanie okna logowania w celu wyświetlania lub ukrywania przycisków zasilania w usłudze Microsoft Intune. Zapoznaj się również z krokami wymaganymi do pobrania ustawień adresu IP, ścieżki i portu serwera funkcji AirPrint w sieci. Te ustawienia zastosowane w profilu konfiguracji urządzenia umożliwiają skonfigurowanie funkcji urządzeń z systemem macOS.
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
ms.openlocfilehash: df5b53be159fd082090e61fd736e4c9329644c85
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512742"
---
# <a name="macos-device-feature-settings-in-intune"></a>Ustawienia funkcji urządzenia z systemem macOS w usłudze Intune

Ustawienia wbudowane w usługę Intune umożliwiają dostosowanie funkcji na urządzeniach z systemem macOS. Administratorzy mogą na przykład dodawać drukarki AirPrint, decydować o sposobie logowania użytkowników, konfigurować sterowanie zasilaniem, korzystać z uwierzytelniania za pomocą logowania jednokrotnego i nie tylko.

Z tych funkcji można korzystać w celu kontrolowania urządzeń z systemem macOS w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM).

Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień. Przedstawiono w nim również listę czynności wymaganych do uzyskania adresu IP, ścieżki i portu drukarek AirPrint przy użyciu aplikacji Terminal (emulatora). Aby uzyskać więcej informacji na temat funkcji urządzeń, przejdź do tematu [Dodawanie ustawień funkcji urządzeń z systemami iOS/iPadOS lub macOS](device-features-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia sieci macOS](device-features-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji, a niektóre z nich dotyczą wszystkich opcji rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [Rejestracja systemu macOS](../enrollment/macos-enroll.md).

## <a name="airprint"></a>Funkcja AirPrint

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia mają zastosowanie do: Rejestracja urządzeń i automatyczna rejestracja urządzeń 

- **Adres IP**: wprowadź adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do drukarki w aplikacji Terminal. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Ścieżka**: wprowadź ścieżkę drukarki. W przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Port** (iOS 11.0+, iPadOS 13.0+): wprowadź port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego.
- **TLS** (iOS 11.0+, iPadOS 13.0+): Wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS).

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

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Pliki, foldery i aplikacje niestandardowe**: **Dodaj** ścieżkę do pliku, folderu, aplikacji niestandardowej lub aplikacji systemowej, którą chcesz otworzyć, gdy użytkownik zaloguje się na urządzeniu. Aplikacje systemowe lub aplikacje opracowane bądź dostosowane dla organizacji zwykle znajdują się w folderze `Applications`, który ma ścieżkę podobną do `/Applications/AppName.app`. 

  Możesz dodać wiele plików, folderów i aplikacji. Wprowadź na przykład:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Podczas dodawania dowolnej aplikacji, folderu lub pliku upewnij się, że została wprowadzona poprawna ścieżka. Nie wszystkie elementy znajdują się w folderze `Applications`. Jeśli użytkownik przeniesie element z jednej lokalizacji do drugiej, ścieżka się zmieni. Ten przeniesiony element nie zostanie otwarty, gdy użytkownik się zaloguje.

## <a name="login-window"></a>Okno logowania

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia mają zastosowanie do: Rejestracja urządzeń i automatyczna rejestracja urządzeń

#### <a name="window-layout"></a>Układ okna

- **Pokaż dodatkowe informacje na pasku menu**: Jeśli obszar czasu na pasku menu jest zaznaczony, wybranie opcji **Zezwalaj** powoduje wyświetlenie nazwy hosta i wersji systemu macOS. W przypadku wybrania opcji **Nie skonfigurowano** (ustawienie domyślne) informacje te nie są wyświetlane na pasku menu.
- **Transparent**: Wprowadź komunikat, który ma być wyświetlany na ekranie logowania urządzenia. Na przykład możesz wprowadzić komunikat powitalny, informacje o swojej organizacji lub informacje o rzeczach zgubionych i znalezionych.
- **Wybierz format logowania**: Wybierz sposób logowania się użytkowników do urządzenia. Dostępne opcje:
  - **Monituj o nazwę użytkownika i hasło** (ustawienie domyślne): Użytkownik musi wprowadzić nazwę użytkownika i hasło.
  - **Wyświetl listę wszystkich użytkowników i monituj o podanie hasła**: Użytkownik musi wybrać swoją nazwę użytkownika z listy, a następnie wprowadzić hasło. Należy również skonfigurować poniższe ustawienia:

    - **Użytkownicy lokalni**: W przypadku wybrania opcji **Ukryj** konta użytkowników lokalnych, np. konto standardowe i konto administratora, nie są wyświetlane na liście użytkowników. Widoczne są tylko konta sieciowe i konta użytkowników systemu. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont użytkowników lokalnych na liście użytkowników.
    - **Konta mobilne**: W przypadku wybrania opcji **Ukryj** konta mobilne nie są wyświetlane na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont mobilnych na liście użytkowników. Niektóre konta mobilne mogą być widoczne jako użytkownicy sieciowi.
    - **Użytkownicy sieciowi**: Wybranie opcji **Pokaż** powoduje wyświetlenie nazw użytkowników sieciowych na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje, że konta użytkowników sieciowych nie są wyświetlane.
    - **Administratorzy**: Wybranie opcji **Ukryj** powoduje, że konta administratorów nie są wyświetlane na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont administratorów na liście użytkowników.
    - **Inni użytkownicy**: Wybranie opcji **Pokaż** powoduje wyświetlenie nazw użytkowników z kategorii **Inni...** na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje, że konta innych użytkowników nie są wyświetlane.

#### <a name="login-screen-power-settings"></a>Ustawienia zasilania ekranu logowania

- **Przycisk Wyłącz**: Wybranie opcji **Ukryj** powoduje ukrycie przycisku wyłączania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku wyłączania.
- **Przycisk Uruchom ponownie**: Wybranie opcji **Ukryj** powoduje ukrycie przycisku ponownego uruchamiania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku ponownego uruchamiania.
- **Przycisk Uśpij**: Wybranie opcji **Ukryj** powoduje ukrycie przycisku usypiania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku usypiania.

#### <a name="other"></a>Inne

- **Wyłącz logowanie użytkownika z konsoli**: Wybranie opcji **Wyłącz** powoduje ukrycie wiersza polecenia systemu macOS używanego do logowania. W przypadku typowych użytkowników należy wybrać opcję **Wyłącz**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) umożliwia zaawansowanym użytkownikom zalogowanie się przy użyciu wiersza polecenia systemu macOS. Aby przejść do trybu konsoli, użytkownicy muszą wprowadzić ciąg `>console` w polu Nazwa użytkownika, a następnie uwierzytelnić się w oknie konsoli.

#### <a name="apple-menu"></a>Menu Apple

Za pomocą następujących ustawień można konfigurować zakres czynności dostępnych dla użytkowników zalogowanych do swoich urządzeń.

- **Wyłącz polecenie Wyłącz**: Wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Zamknij**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Zamknij** w menu na urządzeniu.
- **Wyłącz polecenie Uruchom ponownie**: Wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Uruchom ponownie**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Uruchom ponownie** w menu na urządzeniu.
- **Wyłącz polecenie Wyłącz zasilanie**: Wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Wyłącz zasilanie**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Wyłącz zasilanie** w menu na urządzeniu.
- **Wyłącz polecenie Wyloguj** (system macOS 10.13 i nowsze): Wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Wyloguj**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Wyloguj** w menu na urządzeniu.
- **Wyłącz pozycję Zablokuj ekran** (system macOS 10.13 i nowsze): Wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Zablokuj ekran**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Zablokuj ekran** w menu na urządzeniu.

## <a name="single-sign-on-app-extension"></a>Rozszerzenie aplikacji — rejestracja jednokrotna

Ta funkcja ma zastosowanie do:

- System macOS 10.15 i nowsze

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji 

- **Typ rozszerzenia aplikacji logowania jednokrotnego**: wybierz typ rozszerzenia aplikacji poświadczeń logowania jednokrotnego. Dostępne opcje:

  - **Nieskonfigurowane**: rozszerzenia aplikacji nie są używane. Aby wyłączyć rozszerzenie aplikacji, przełącz typ rozszerzenia aplikacji logowania jednokrotnego na wartość **Nieskonfigurowane**.
  - **Przekierowanie**: użyj ogólnego, dostosowywalnego rozszerzenia aplikacji przekierowania, aby przeprowadzać logowanie jednokrotne za pomocą nowoczesnych przepływów uwierzytelniania. Upewnij się, że znasz identyfikator rozszerzenia i zespołu dla rozszerzenia aplikacji w organizacji.
  - **Poświadczenie**: użyj ogólnego, dostosowywalnego rozszerzenia aplikacji poświadczenia, aby przeprowadzać logowanie jednokrotne za pomocą przepływów uwierzytelniania typu wyzwanie-odpowiedź. Upewnij się, że znasz identyfikator rozszerzenia i identyfikator zespołu dla rozszerzenia aplikacji logowania jednokrotnego w organizacji.  
  - **Kerberos**: użyj wbudowanego rozszerzenia protokołu Kerberos firmy Apple, które jest zawarte w systemie macOS Catalina 10.15 i nowszych wersjach. Ta opcja jest specyficzną dla protokołu Kerberos wersją rozszerzenia aplikacji **Poświadczenie**.

  > [!TIP]
  > W przypadku typów **Przekierowanie** i **Poświadczenie** dodajesz własne wartości konfiguracji w celu przekazania przez rozszerzenie. Jeśli używasz typu **Poświadczenie**, rozważ użycie wbudowanych ustawień konfiguracji dostarczonych przez firmę Apple w typie **Kerberos**.

- **Identyfikator rozszerzenia** (Przekierowanie i Poświadczenie): wprowadź identyfikator pakietu określający rozszerzenie aplikacji logowania jednokrotnego, na przykład `com.apple.ssoexample`.
- **Identyfikator zespołu** (Przekierowanie i Poświadczenie): wprowadź identyfikator zespołu dla rozszerzenia aplikacji logowania jednokrotnego. Identyfikator zespołu to 10-znakowy ciąg alfanumeryczny (cyfry i litery) generowany przez firmę Apple, taki jak `ABCDE12345`. 

  Aby uzyskać więcej informacji, skorzystaj z linku [Locate your Team ID](https://help.apple.com/developer-account/#/dev55c3c710c) (Znajdź swój identyfikator zespołu) — zostanie otwarta witryna internetowa firmy Apple.

- **Obszar** (Poświadczenie i Kerberos): wprowadź nazwę obszaru uwierzytelniania. Nazwa obszaru powinna być pisana wielkimi literami, na przykład `CONTOSO.COM`. Zazwyczaj nazwa obszaru jest taka sama, jak nazwa domeny DNS, ale pisana w całości wielkimi literami.

- **Domeny** (Poświadczenie i Kerberos): wprowadź nazwy domen lub hostów witryn, które mogą być uwierzytelniane za pomocą logowania jednokrotnego. Jeśli na przykład witryna internetowa to `mysite.contoso.com`, nazwą hosta będzie `mysite`, a nazwą domeny będzie `contoso.com`. Gdy użytkownicy będą łączyć się z dowolną z tych witryn, rozszerzenie aplikacji obsłuży wyzwanie uwierzytelniania. To uwierzytelnianie umożliwia użytkownikom logowanie się przy użyciu funkcji Face ID, Touch ID lub kodu PIN/ kodu dostępu firmy Apple.

  - Wszystkie domeny w profilach usługi Intune rozszerzenia aplikacji logowania jednokrotnego muszą być unikatowe. Nie można powtórzyć domeny w żadnym profilu rozszerzenia aplikacji logowania, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - W tych domenach nie jest rozróżniana wielkość liter.

- **Adresy URL** (tylko Przekierowanie): wprowadź prefiksy adresów URL swoich dostawców tożsamości, w których imieniu rozszerzenie aplikacji przekierowania wykonuje logowanie jednokrotne. Gdy użytkownik zostanie przekierowany do tych adresów URL, rozszerzenie aplikacji logowana jednokrotnego będzie interweniować i monitować o logowanie jednokrotne.

  - Wszystkie adresy URL w profilach usługi Intune rozszerzenia aplikacji logowania jednokrotnego muszą być unikatowe. Nie można powtórzyć domeny w żadnym profilu rozszerzenia aplikacji logowania jednokrotnego, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - Adresy URL muszą zaczynać się od ciągu http:// lub https://.

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

- **Wykrywanie automatyczne** (tylko Kerberos): w przypadku ustawienia opcji **Blokuj** rozszerzenie protokołu Kerberos nie będzie automatycznie używać protokołu LDAP i usługi DNS do określenia swojej nazwy lokacji usługi Active Directory. Opcja **Nieskonfigurowane** (wartość domyślna) umożliwia rozszerzeniu automatyczne znajdowanie nazwy lokacji usługi Active Directory.
- **Zmiany hasła** (tylko Kerberos): opcja **Blokuj** uniemożliwia użytkownikom zmienianie haseł używanych do logowania się do wprowadzonych domen. Opcja **Nieskonfigurowane** (wartość domyślna) umożliwia zmianę hasła.  
- **Synchronizacja haseł** (tylko Kerberos): wybierz opcję **Włącz**, aby synchronizować lokalne hasła użytkowników z usługą Azure AD. Opcja **Nieskonfigurowane** (wartość domyślna) powoduje wyłączenie synchronizacji haseł z usługą Azure AD. Użyj tego ustawienia jako metody alternatywnej lub zapasowej dla logowania jednokrotnego. To ustawienie nie działa, jeśli użytkownicy są zalogowani przy użyciu konta urządzeń przenośnych firmy Apple.
- **Złożoność hasła w usłudze Active Directory systemu Windows Server** (tylko Kerberos): wybierz opcję **Wymagaj**, aby hasła użytkowników musiały spełniać wymagania dotyczące złożoności haseł usługi Active Directory. Aby uzyskać więcej informacji, zobacz [Hasło musi spełniać wymagania dotyczące złożoności](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements). Opcja **Nieskonfigurowane** (wartość domyślna) nie wymaga od użytkowników spełnienia wymagań dotyczących haseł usługi Active Directory.
- **Minimalna długość hasła** (tylko Kerberos): określ minimalną liczbę znaków, z których musi składać się hasło użytkownika. Opcja **Nieskonfigurowane** (wartość domyślna) nie wymusza minimalnej długości hasła użytkownika.
- **Limit ponownego użycia hasła** (tylko Kerberos): wprowadź liczbę nowych haseł z zakresu od 1 do 24, których należy użyć, zanim będzie można ponownie użyć poprzedniego hasła w domenie. Opcja **Nieskonfigurowane** (wartość domyślna) nie wymusza limitu ponownego użycia hasła.
- **Minimalny wiek hasła** (tylko Kerberos): wprowadź liczbę dni, przez które hasło musi być używane w domenie, zanim użytkownik będzie mógł je zmienić. Opcja **Nieskonfigurowane** (wartość domyślna) nie wymusza minimalnego wieku hasła, zanim będzie można je zmienić.
- **Powiadomienie o wygaśnięciu hasła** (tylko Kerberos): wprowadź liczbę dni pozostałych do wygaśnięcia hasła, kiedy użytkownik jest powiadamiany, że hasło wygaśnie. Opcja **Nieskonfigurowane** (wartość domyślna) używa wartości `15` dni.
- **Wygaśnięcie hasła** (tylko protokół Kerberos): wprowadź liczbę dni, po której należy zmienić hasło urządzenia. Opcja **Nieskonfigurowane** (wartość domyślna) oznacza, że hasła użytkowników nigdy nie wygasają.
- **Adres URL zmiany hasła** (tylko Kerberos): wprowadź adres URL, który zostanie uruchomiony, gdy użytkownik zainicjuje zmianę hasła protokołu Kerberos.
- **Nazwa podmiotu zabezpieczeń** (tylko Kerberos): wprowadź nazwę użytkownika podmiotu zabezpieczeń protokołu Kerberos. Nie trzeba dołączać nazwy obszaru. Na przykład w adresie `user@contoso.com` `user` jest nazwą podmiotu zabezpieczeń, a `contoso.com` jest nazwą obszaru.

  > [!TIP]
  > - W nazwie podmiotu zabezpieczeń można również użyć zmiennych, wprowadzając nawiasy klamrowe `{{ }}`. Aby na przykład wyświetlić nazwę użytkownika, wprowadź `Username: {{username}}`. 
  > - Zachowaj ostrożność, używając podstawienia zmiennej, ponieważ zmienne nie są weryfikowanie w interfejsie użytkownika i uwzględniają wielkość liter. Upewnij się, że wprowadzasz odpowiednie informacje.
  
- **Kod lokacji usługi Active Directory** (tylko Kerberos): wprowadź nazwę lokacji usługi Active Directory, której ma użyć rozszerzenie protokołu Kerberos. Zmiana tej wartości może nie być konieczna, ponieważ rozszerzenie protokołu Kerberos może automatycznie znajdować kod lokacji usługi Active Directory.
- **Nazwa pamięci podręcznej** (tylko Kerberos): wprowadź nazwę usług Generic Security Services (GSS) pamięci podręcznej protokołu Kerberos. Najprawdopodobniej nie trzeba będzie ustawiać tej wartości.  
- **Komunikat o wymaganiach dotyczących hasła** (tylko Kerberos): wprowadź wersję tekstową wymagań dotyczących haseł w organizacji, które są wyświetlane dla użytkowników. Ten komunikat jest wyświetlany, jeśli nie żądasz spełnienia wymagań dotyczących złożoności hasła usługi Active Directory ani nie wprowadzasz minimalnej długości hasła.  
- **Identyfikatory pakietów aplikacji** (tylko Kerberos): **Dodaj** identyfikatory pakietów aplikacji, które powinny używać logowania jednokrotnego na urządzeniach. Te aplikacje mogą uzyskiwać dostęp do biletu uprawniającego do przyznania biletu protokołu Kerberos, czyli do biletu uwierzytelniania, i uwierzytelniają użytkowników w usługach, do których mają dostęp.
- **Mapowanie obszaru domeny** (tylko Kerberos): **Dodaj** sufiksy DNS domeny, które powinny być mapowane na obszar. Użyj tego ustawienia, jeśli nazwy DNS hostów nie są zgodne z nazwą obszaru. Najprawdopodobniej nie trzeba będzie tworzyć tego niestandardowego mapowania domeny na obszar.
- **Certyfikat PKINIT** (tylko Kerberos): **Wybierz** certyfikat kryptografii klucza publicznego na użytek uwierzytelniania początkowego (PKINIT), którego można użyć na potrzeby uwierzytelniania protokołu Kerberos. Możesz wybrać spośród certyfikatów [PKCS](../protect/certficates-pfx-configure.md) lub [SCEP](../protect/certificates-scep-configure.md), które zostały dodane do usługi Intune. Aby uzyskać więcej informacji o certyfikatach, zobacz [Używanie certyfikatów do uwierzytelniania w usłudze Microsoft Intune](../protect/certificates-configure.md).

## <a name="associated-domains"></a>Skojarzone domeny

W usłudze Intune:

- Dodaj wiele skojarzeń aplikacji z domeną.
- Skojarz wiele domen z tą samą aplikacją.

Ta funkcja ma zastosowanie do:

- System macOS 10.15 i nowsze

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Identyfikator aplikacji**: wprowadź identyfikator aplikacji, która ma zostać skojarzona z witryną internetową. Identyfikator aplikacji zawiera identyfikator zespołu i identyfikator pakietu: `TeamID.BundleID`.

  Identyfikator zespołu to 10-znakowy ciąg alfanumeryczny (litery i cyfry) wygenerowany przez firmę Apple dla deweloperów aplikacji, na przykład `ABCDE12345`. Aby uzyskać więcej informacji, skorzystaj z linku [Locate your Team ID](https://help.apple.com/developer-account/#/dev55c3c710c)  (Znajdź swój identyfikator zespołu) — zostanie otwarta witryna internetowa firmy Apple.

  Identyfikator pakietu jednoznacznie identyfikuje aplikację i zazwyczaj jest formatowany w odwrotnej notacji nazwy domeny. Na przykład identyfikator pakietu aplikacji Finder to `com.apple.finder`. Aby znaleźć identyfikator pakietu, użyj funkcji AppleScript w programie Terminal:

  `osascript -e 'id of app "ExampleApp"'`

- **Domena**: wprowadź domenę witryny internetowej, która ma zostać skojarzona z aplikacją. Domena zawiera typ usługi i w pełni kwalifikowaną nazwę hosta, na przykład `webcredentials:www.contoso.com`.

  Możesz dopasować wszystkie poddomeny skojarzonej domeny, wprowadzając znaki `*.` (symbol wieloznaczny gwiazdki i kropkę) przed początkiem domeny. Okres jest wymagany. Dokładne domeny mają wyższy priorytet niż domeny wieloznaczne. Zatem wzorce z domen nadrzędnych są dopasowywane, *jeśli* nie zostanie znalezione dopasowanie dla w pełni kwalifikowanej poddomeny.

  Typ usługi może być następujący:

  - **authsrv**: Rozszerzenie aplikacji — rejestracja jednokrotna
  - **applink**: link uniwersalny
  - **webcredentials**: autowypełnianie hasła

- **Dodaj**: wybierz, aby dodać aplikacje i skojarzone domeny.

> [!TIP]
> W celu rozwiązania problemów na urządzeniu z systemem macOS wybierz pozycję **Preferencje systemowe** > **Profile**. Potwierdź, że utworzony profil znajduje się na liście profili urządzeń. Jeśli jest wymieniony, upewnij się, że zawiera on ustawienie **Konfiguracja skojarzonych domen** oraz że identyfikator aplikacji i domeny są prawidłowe.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Możesz również skonfigurować funkcje urządzenia w systemie [iOS/iPadOS](ios-device-features-settings.md).
