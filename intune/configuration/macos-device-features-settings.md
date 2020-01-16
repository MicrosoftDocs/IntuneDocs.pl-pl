---
title: Ustawienia funkcji urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z ustawieniami umożliwiającymi konfigurowanie urządzeń z systemem macOS pod kątem obsługi funkcji AirPrint i dostosowywanie okna logowania w celu wyświetlania lub ukrywania przycisków zasilania w usłudze Microsoft Intune. Zapoznaj się również z krokami wymaganymi do pobrania ustawień adresu IP, ścieżki i portu serwera funkcji AirPrint w sieci. Te ustawienia zastosowane w profilu konfiguracji urządzenia umożliwiają skonfigurowanie funkcji urządzeń z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2019
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
ms.openlocfilehash: 791e2a1313480bdf1ad95988d48664d6620ba0b3
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206350"
---
# <a name="macos-device-feature-settings-in-intune"></a>Ustawienia funkcji urządzenia z systemem macOS w usłudze Intune

Ustawienia wbudowane w usługę Intune umożliwiają dostosowanie funkcji na urządzeniach z systemem macOS. Administratorzy mogą na przykład dodawać AirPrint drukarki, decydować o sposobie logowania użytkowników, konfigurować sterowanie mocą, korzystać z uwierzytelniania jednokrotnego i nie tylko.

Z tych funkcji można korzystać w celu kontrolowania urządzeń z systemem macOS w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM).

Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień. Przedstawiono w nim również listę czynności wymaganych do uzyskania adresu IP, ścieżki i portu drukarek AirPrint przy użyciu aplikacji Terminal (emulatora). Aby uzyskać więcej informacji na temat funkcji urządzenia, przejdź do [Dodaj ustawienia funkcji urządzenia z systemem iOS lub macOS](device-features-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia sieci macOS](device-features-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji, z uwzględnieniem niektórych ustawień, które są stosowane do wszystkich opcji rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [rejestracji](../enrollment/macos-enroll.md)macOS.

## <a name="airprint"></a>Funkcja AirPrint

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Rejestracja urządzeń i automatyczna rejestracja urządzeń 

- **Adres IP**: wprowadź adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do drukarki w aplikacji Terminal. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Ścieżka**: wprowadź ścieżkę drukarki. W przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Port** (system iOS 11.0 i nowsze): wprowadź port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego.
- **TLS** (system iOS 11.0 i nowsze): Wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS).

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

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Rejestracja urządzeń i automatyczna rejestracja urządzeń

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

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji 

- **Typ rozszerzenia aplikacji SSO**: Wybierz typ rozszerzenia aplikacji SSO logowania jednokrotnego. Dostępne opcje:

  - **Nie skonfigurowano**: rozszerzenia aplikacji nie są używane. Aby wyłączyć rozszerzenie aplikacji, Zmień typ rozszerzenia aplikacji logowania jednokrotnego na **nieskonfigurowane**.
  - **Przekierowanie**: Użyj ogólnego, dostosowywalnego rozszerzenia aplikacji przekierowania, aby przeprowadzić Logowanie jednokrotne przy użyciu nowoczesnych przepływów uwierzytelniania. Upewnij się, że znasz rozszerzenie i identyfikator zespołu dla rozszerzenia aplikacji w organizacji.
  - **poświadczeń**: Użyj ogólnego, dostosowywalnego rozszerzenia aplikacji Credential, aby przeprowadzić Logowanie jednokrotne za pomocą przepływów uwierzytelniania typu wyzwanie-odpowiedź. Upewnij się, że znasz identyfikator rozszerzenia i identyfikator zespołu dla rozszerzenia aplikacji SSO w organizacji.  
  - **Kerberos**: Użyj wbudowanego rozszerzenia protokołu Kerberos firmy Apple, które jest dołączone do macOS Catalina 10,15 i nowszych. Ta opcja jest zależna od protokołu Kerberos wersja **poświadczenia** aplikacji.

  > [!TIP]
  > Za pomocą **przekierowania** i **typy** poświadczeń należy dodać własne wartości konfiguracyjne, aby przejść przez rozszerzenie. Jeśli używasz usługi **Credential**, rozważ użycie wbudowanych ustawień konfiguracji dostarczonych przez firmę Apple w typu **Kerberos**.

- **Identyfikator rozszerzenia** (przekierowanie i poświadczenie): Wprowadź identyfikator pakietu identyfikujący rozszerzenie aplikacji logowania jednokrotnego, takie jak `com.apple.ssoexample`.
- **Identyfikator zespołu** (przekierowanie i poświadczenie): Wprowadź identyfikator zespołu rozszerzenia aplikacji logowania jednokrotnego. Identyfikator zespołu to 10-znakowy ciąg alfanumeryczny (cyfry i litery) generowany przez firmę Apple, taki jak `ABCDE12345`. 

  [Znajdź identyfikator zespołu](https://help.apple.com/developer-account/#/dev55c3c710c) (otwiera witrynę firmy Apple), aby uzyskać więcej informacji.

- **obszaru** (poświadczenia i protokół Kerberos): Wprowadź nazwę obszaru uwierzytelniania. Nazwa obszaru powinna być Wielka litera, taka jak `CONTOSO.COM`. Zazwyczaj nazwa obszaru jest taka sama jak nazwa domeny DNS, ale w przypadku wszystkich wielkich liter.

- **Domeny** (Credential i Kerberos): Wprowadź nazwy domeny lub hosta witryn, które mogą być uwierzytelniane za pomocą logowania jednokrotnego. Na przykład jeśli witryna sieci Web jest `mysite.contoso.com`, `mysite` to nazwa hosta, a `contoso.com` to nazwa domeny. Gdy użytkownicy łączą się z dowolną z tych witryn, rozszerzenie aplikacji obsługuje wyzwanie uwierzytelniania. To uwierzytelnianie umożliwia użytkownikom logowanie się przy użyciu identyfikatora, Touch ID lub Apple pincode/kodu dostępu.

  - Wszystkie domeny w profilach usługi Intune rozszerzenia aplikacji logowania jednokrotnego muszą być unikatowe. Nie można powtórzyć domeny w dowolnym profilu rozszerzenia aplikacji logowania, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - W tych domenach nie jest rozróżniana wielkość liter.

- **Adresy URL** (tylko przekierowanie): wprowadź prefiksy adresów URL dostawców tożsamości, w których imieniu rozszerzenie aplikacji przekierowanie wykonuje Logowanie jednokrotne. Gdy użytkownik zostanie przekierowany do tych adresów URL, rozszerzenie aplikacji SSO będzie interweniować i monitować o Logowanie jednokrotne.

  - Wszystkie adresy URL w profilach rozszerzenia aplikacji logowania jednokrotnego usługi Intune muszą być unikatowe. Nie można powtórzyć domeny w żadnym profilu rozszerzenia aplikacji logowania jednokrotnego, nawet jeśli używasz różnych typów rozszerzeń aplikacji logowania jednokrotnego.
  - Adresy URL muszą zaczynać się od http://lub https://.

- **Dodatkowe** konfiguracji (przekierowanie i poświadczenie): wprowadź dodatkowe dane specyficzne dla rozszerzenia, które mają zostać przekazane do rozszerzenia aplikacji SSO:
  - **Klucz**: Wprowadź nazwę elementu, który chcesz dodać, np. `user name`.
  - **Typ**: wprowadź typ danych. Dostępne opcje:

    - String
    - Wartość logiczna: w **wartości konfiguracji**, wprowadź `True` lub `False`.
    - Liczba całkowita: w **wartość konfiguracji**wprowadź liczbę.
    
  - **Wartość**: Wprowadź dane.
  
  - **Dodaj**: Wybierz, aby dodać klucze konfiguracji.

- **użycia łańcucha kluczy** (tylko protokół Kerberos): wybierz pozycję **Blokuj**, aby uniemożliwić zapisywanie i przechowywanie haseł w łańcuchu kluczy. **Nieskonfigurowane** (domyślnie) umożliwia zapisywanie i przechowywanie haseł w pęku kluczy.  
- **Identyfikator urządzenia, Touch ID lub** kodu dostępu (tylko protokół Kerberos): **Wymagaj** wymusza, aby użytkownicy musieli wprowadzić swój identyfikator, Touch ID lub kod dostępu Apple, aby zalogować się do dodanych domen. **Nie skonfigurowano** (domyślnie) nie wymaga, aby użytkownicy używali biometrii ani kodu dostępu do logowania.
- **Domyślny** obszaru (tylko protokół Kerberos): wybierz pozycję **Włącz**, aby ustawić wartość **obszaru** wprowadzoną jako domyślny obszar. **Nie skonfigurowano** (domyślnie) nie ustawia obszaru domyślnego.

  > [!TIP]
  > - **Włącz** tego ustawienia, jeśli konfigurujesz wiele rozszerzeń aplikacji SSO protokołu Kerberos w organizacji.
  > - **Włącz** tego ustawienia, jeśli używasz wielu obszarów. Ustawia obszar **,** wartość wprowadzona jako domyślny obszar.
  > - Jeśli masz tylko jeden obszar, pozostaw **nie skonfigurowany** (domyślnie).

- **wykrywania** automatycznego (tylko protokół Kerberos): w przypadku ustawienia opcji **bloku**rozszerzenie protokołu Kerberos nie będzie automatycznie używać protokołu LDAP i DNS do określenia nazwy lokacji Active Directory. **Nie skonfigurowano** (domyślnie) pozwala rozszerzeniu na automatyczne Znajdowanie Active Directory nazwy lokacji.
- **Zmiany hasła** (tylko protokół Kerberos): **bloku** uniemożliwia użytkownikom zmianę haseł używanych do logowania się do wprowadzonych domen. **Nie skonfigurowano** (wartość domyślna) umożliwia zmianę hasła.  
- **synchronizacji haseł** (tylko protokół Kerberos): wybierz pozycję **Włącz**, aby synchronizować hasła lokalne użytkowników z usługą Azure AD. **Nie skonfigurowano** (domyślnie) powoduje wyłączenie synchronizacji haseł z usługą Azure AD. Użyj tego ustawienia jako alternatywy lub kopii zapasowej na potrzeby logowania jednokrotnego. To ustawienie nie działa, jeśli użytkownicy są zalogowani przy użyciu konta Apple Mobile.
- **Windows Server Active Directory złożoność hasła** (tylko protokół Kerberos): Wybierz **wymagać**, aby wymusić, że hasła użytkowników spełniają wymagania dotyczące złożoności hasła Active Directory. Aby uzyskać więcej informacji, zobacz [hasło musi spełniać](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) wymagania co do złożoności. **Nie skonfigurowano** (wartość domyślna) nie wymaga od użytkowników spełnienia wymagań dotyczących hasła Active Directory.
- **Minimalna długość hasła** (tylko protokół Kerberos): wprowadź minimalną liczbę znaków, które mogą wprowadzić hasło użytkownika. **Nie skonfigurowano** (wartość domyślna) nie wymusza minimalnej długości hasła dla użytkowników.
- **Limit ponownego użycia hasła** (tylko protokół Kerberos): wprowadź liczbę nowych haseł z 1-24, które muszą zostać użyte, dopóki nie będzie można ponownie użyć poprzedniego hasła w domenie. **Nie skonfigurowano** (wartość domyślna) nie wymusza ponownego użycia hasła.
- **Minimalny wiek hasła** (tylko protokół Kerberos): wprowadź liczbę dni, przez które hasło musi być używane w domenie, zanim użytkownik będzie mógł je zmienić. **Nie skonfigurowano** (wartość domyślna) nie wymusza minimalnego wieku hasła, zanim będzie można je zmienić.
- **Powiadomienie o wygaśnięciu hasła** (tylko protokół Kerberos): wprowadź liczbę dni, po których hasło wygasa, gdy użytkownicy otrzymają powiadomienie o wygaśnięciu hasła. **Nie skonfigurowano** (wartość domyślna) używa `15` dni.
- **Wygaśnięcie hasła** (tylko protokół Kerberos): wprowadź liczbę dni, po której należy zmienić hasło urządzenia. **Nie skonfigurowano** (wartość domyślna) oznacza, że hasła użytkowników nigdy nie wygasną.
- **Adres URL zmiany hasła** (tylko protokół Kerberos): wprowadź adres URL, który zostanie uruchomiony, gdy użytkownik zainicjuje zmianę hasła protokołu Kerberos.
- **Nazwa główna** (tylko protokół Kerberos): Wprowadź nazwę użytkownika podmiotu zabezpieczeń protokołu Kerberos. Nie trzeba dołączać nazwy obszaru. Na przykład w `user@contoso.com``user` jest nazwą główną, a `contoso.com` jest nazwą obszaru.

  > [!TIP]
  > - Można również użyć zmiennych w nazwie głównej, wprowadzając nawiasy klamrowe `{{ }}`. Na przykład, aby wyświetlić nazwę użytkownika, wprowadź `Username: {{username}}`. 
  > - Jednak należy zachować ostrożność przy użyciu podstawienia zmiennej, ponieważ zmienne nie są sprawdzane w interfejsie użytkownika i uwzględniają wielkość liter. Upewnij się, że wprowadzono prawidłowe informacje.
  
- **Active Directory** kodu lokacji (tylko protokół Kerberos): Wprowadź nazwę witryny Active Directory, której ma używać rozszerzenie protokołu Kerberos. Zmiana tej wartości może nie być konieczna, ponieważ rozszerzenie protokołu Kerberos może automatycznie znaleźć kod lokacji Active Directory.
- **Nazwa pamięci podręcznej** (tylko protokół Kerberos): Wprowadź nazwę Generic Security Services (GSS) pamięci podręcznej protokołu Kerberos. Najprawdopodobniej nie musisz ustawiać tej wartości.  
- **Komunikat wymagania dotyczącego hasła** (tylko protokół Kerberos): wprowadź wersję tekstową wymagań dotyczących hasła organizacji, które są widoczne dla użytkowników. Komunikat jest wyświetlany, jeśli nie są wymagane wymagania dotyczące złożoności hasła Active Directory lub nie wprowadzono minimalnej długości hasła.  
- **Identyfikatory pakietu aplikacji** (tylko protokół Kerberos): **Dodaj** identyfikatorów zbioru aplikacji, które powinny używać logowania jednokrotnego na urządzeniach. Te aplikacje otrzymują dostęp do biletu uprawniającego do przyznania biletu protokołu Kerberos, biletu uwierzytelniania i uwierzytelniania użytkowników do usług, do których mają dostęp.
- **Mapowanie obszaru domeny** (tylko protokół Kerberos): **Dodaj** sufiksy DNS domeny, które powinny być mapowane na obszar. Użyj tego ustawienia, jeśli nazwy DNS hostów nie pasują do nazwy obszaru. Najprawdopodobniej nie musisz tworzyć tego niestandardowego mapowania domeny-obszaru.
- **certyfikatów PKINIT** (tylko protokół Kerberos): **wybierz** kryptografii klucza publicznego dla certyfikatu uwierzytelniania początkowego (PKINIT), którego można użyć do uwierzytelniania Kerberos. Możesz wybrać jedną z [PKCS](../protect/certficates-pfx-configure.md) lub [SCEP](../protect/certificates-scep-configure.md) certyfikaty, które zostały dodane w usłudze Intune. Aby uzyskać więcej informacji o certyfikatach, zobacz [używać certyfikatów do uwierzytelniania w Microsoft Intune](../protect/certificates-configure.md).

## <a name="associated-domains"></a>Skojarzone domeny

W usłudze Intune:

- Dodaj wiele skojarzeń między aplikacjami.
- Skojarz wiele domen z tą samą aplikacją.

Ta funkcja ma zastosowanie do:

- System macOS 10.15 i nowsze

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Identyfikator aplikacji**: Wprowadź identyfikator aplikacji, która ma zostać skojarzona z witryną sieci Web. Identyfikator aplikacji zawiera identyfikator zespołu i identyfikator pakietu: `TeamID.BundleID`.

  Identyfikator zespołu to 10-znakowe znaki alfanumeryczne (litery i cyfry) wygenerowane przez firmę Apple dla deweloperów aplikacji, takie jak `ABCDE12345`. [Znajdź identyfikator zespołu](https://help.apple.com/developer-account/#/dev55c3c710c) (otwiera witrynę sieci Web firmy Apple), aby uzyskać więcej informacji.

  Identyfikator pakietu jednoznacznie identyfikuje aplikację i zazwyczaj jest formatowany w odwrotnej notacji nazwy domeny. Na przykład identyfikator pakietu wyszukiwania jest `com.apple.finder`. Aby znaleźć identyfikator pakietu, użyj programu AppleScript w terminalu:

  `osascript -e 'id of app "ExampleApp"'`

- **domeny**: Wprowadź domenę witryny sieci Web, która ma zostać skojarzona z aplikacją. Domena zawiera typ usługi i w pełni kwalifikowana nazwa hosta, takie jak `webcredentials:www.contoso.com`.

  Można dopasować wszystkie poddomeny skojarzonej domeny, wprowadzając `*.` (symbol wieloznaczny gwiazdki i kropkę) przed rozpoczęciem domeny. Okres wykorzystania jest wymagany Dokładne domeny mają wyższy priorytet niż w przypadku domen wieloznacznych. Dlatego wzorce z domen nadrzędnych są dopasowywane *, jeśli* dopasowanie nie zostanie znalezione w w pełni kwalifikowanej poddomenie.

  Typem usługi może być:

  - **authsrv**: Rozszerzenie aplikacji — rejestracja jednokrotna
  - **applink**: połączenie uniwersalne
  - **poświadczeń webcredentials**: Autowypełnianie hasła

- **Dodaj**: Wybierz, aby dodać aplikacje i skojarzone domeny.

> [!TIP]
> Aby rozwiązać problem, na urządzeniu macOS Otwórz **preferencji systemu** > **profile**. Potwierdź, że utworzony profil znajduje się na liście Profile urządzeń. Jeśli jest ona wyświetlana, upewnij się, że **konfiguracji skojarzonych domen** znajduje się w profilu i zawiera poprawne identyfikatory aplikacji i domen.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Możesz również skonfigurować funkcje urządzenia w [systemu iOS](ios-device-features-settings.md).
