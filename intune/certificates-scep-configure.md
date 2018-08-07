---
title: Używanie certyfikatów SCEP z usługą Microsoft Intune na platformie Azure | Microsoft Docs
description: Aby korzystać z certyfikatów SCEP w usłudze Microsoft Intune, skonfiguruj lokalną domenę usługi AD, utwórz urząd certyfikacji, skonfiguruj serwer usługi NDES i zainstaluj łącznik certyfikatów usługi Intune. Następnie utwórz profil certyfikatu SCEP i przypisz go do grup. Zapoznaj się też z różnymi identyfikatorami zdarzeń i ich opisami oraz kodami diagnostycznymi dla usługi łącznika Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce017f323ebbe4095f5aa31990878afce0116573
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321241"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Konfigurowanie certyfikatów SCEP i korzystanie z nich w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące konfigurowania infrastruktury oraz tworzenia i przypisywania profilów certyfikatów prostego protokołu rejestrowania certyfikatów (SCEP) za pomocą usługi Intune.

## <a name="configure-on-premises-infrastructure"></a>Konfigurowanie infrastruktury lokalnej

- **Domena usługi Active Directory:** wszystkie serwery wymienione w tej części (z wyjątkiem serwera proxy aplikacji internetowej) muszą należeć do Twojej domeny usługi Active Directory.

- **Urząd certyfikacji** (CA): wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. Aby uzyskać szczegółowe informacje, zobacz temat [Instalowanie urzędu certyfikacji](http://technet.microsoft.com/library/jj125375.aspx).
    Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2, należy najpierw [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).

- **Serwer usługi NDES**: na serwerze z systemem Windows Server 2012 R2 lub nowszym należy skonfigurować usługę rejestracji urządzeń sieciowych (NDES). Usługa Intune nie obsługuje usługi NDES uruchomionej na tym samym serwerze, na którym jest uruchomiony urząd certyfikacji przedsiębiorstwa. Temat [Wskazówki dotyczące usługi rejestracji urządzeń sieciowych](http://technet.microsoft.com/library/hh831498.aspx) zawiera instrukcje dotyczące sposobu konfiguracji systemu Windows Server 2012 R2 do hostowania usługi rejestracji urządzeń sieciowych.
Serwer usługi NDES musi być przyłączony do domeny hostującej urząd certyfikacji i nie może znajdować się na tym samym serwerze co ten urząd. Więcej informacji na temat wdrażania serwera usługi NDES w oddzielnym lesie, sieci izolowanej lub domenie wewnętrznej można znaleźć w temacie [Używanie modułu zasad z usługą rejestracji urządzeń sieciowych](https://technet.microsoft.com/library/dn473016.aspx).

- **Łącznik certyfikatów usługi Microsoft Intune**: używając witryny Azure Portal, pobierz instalator **łącznika certyfikatów** (**NDESConnectorSetup.exe**). Następnie możesz uruchomić program **NDESConnectorSetup.exe** na serwerze hostującym rolę usługi rejestracji urządzeń sieciowych (NDES), na którym chcesz zainstalować łącznik certyfikatów.

  - Łącznik certyfikatów usługi NDES obsługuje też tryb Federal Information Processing Standard (FIPS). Tryb FIPS nie jest wymagany, ale możesz wystawiać i odwoływać certyfikaty, gdy jest on włączony.

- **Serwer proxy aplikacji internetowej** (opcjonalnie): jako serwera proxy aplikacji internetowej (WAP) użyj serwera z systemem Windows Server 2012 R2 lub nowszym. Ta konfiguracja:
  - Umożliwia urządzeniom otrzymywanie certyfikatów przy użyciu połączenia internetowego.
  - Jest zalecana ze względów bezpieczeństwa w przypadku używania połączenia internetowego do pobierania i odnawiania certyfikatów przez urządzenia.

#### <a name="additional"></a>Dodatkowe

- Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych. Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).
- Serwer WAP musi mieć certyfikat SSL pasujący do nazwy opublikowanej dla klientów zewnętrznych oraz ufać certyfikatowi SSL używanemu na serwerze usługi NDES. Te certyfikaty umożliwiają serwerowi proxy aplikacji sieci Web zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z serwerem usługi NDES.

Aby uzyskać więcej informacji, zobacz [Plan certificates for WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) (Planowanie certyfikatów protokołu WAP) i [ogólne informacje na temat serwerów WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="network-requirements"></a>Wymagania dotyczące sieci

Z Internetu do sieci obwodowej — zezwól na ruch przez port 443 ze wszystkich hostów/adresów IP w Internecie do serwera usługi NDES.

Z sieci obwodowej do sieci zaufanej — zezwól na ruch dotyczący wszystkich portów i protokołów wymaganych do zapewnienia dostępu do domeny na serwerze usługi NDES przyłączonym do domeny. Serwer usługi NDES musi uzyskiwać dostęp do serwerów certyfikatów, serwerów DNS, serwerów programu Configuration Manager i kontrolerów domeny.

Zaleca się publikowanie serwera usługi NDES za pośrednictwem serwera proxy, takiego jak [serwer proxy aplikacji usługi Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [serwer proxy dostępu do sieci Web](https://technet.microsoft.com/library/dn584107.aspx) lub serwer proxy innych firm.

### <a name="certificates-and-templates"></a>Certyfikaty i szablony

|Obiekt|Szczegóły|
|----------|-----------|
|**Szablon certyfikatu**|Skonfiguruj ten szablon na serwerze urzędu wystawiającego certyfikaty.|
|**Certyfikat uwierzytelniania klienta**|Żądany od urzędu wystawiającego certyfikaty lub publicznego urzędu certyfikacji; instalowany na serwerze usługi NDES.|
|**Certyfikat uwierzytelniania serwera**|Żądany od urzędu wystawiającego certyfikaty lub publicznego urzędu certyfikacji; certyfikat SSL instalowany i powiązany w usługach IIS na serwerze usługi NDES.|
|**Certyfikat zaufanego głównego urzędu certyfikacji**|Ten certyfikat należy wyeksportować jako plik **.cer** z głównego urzędu certyfikacji lub dowolnego urządzenia uznającego główny urząd certyfikacji za zaufany, a następnie przypisać go do urządzeń, korzystając z profilu certyfikatu zaufanego urzędu certyfikacji.<br /><br />Należy użyć jednego certyfikatu zaufanego głównego urzędu certyfikacji dla każdej platformy systemu operacyjnego i powiązać te certyfikaty z poszczególnymi utworzonymi profilami zaufanych certyfikatów głównych.<br /><br />W razie potrzeby można użyć dodatkowych certyfikatów zaufanego głównego urzędu certyfikacji. Można na przykład zrobić to, aby urząd certyfikacji podpisujący certyfikaty uwierzytelniania serwera dla punktów dostępowych Wi-Fi był traktowany jako zaufany.|

### <a name="accounts"></a>Konta

|Nazwa|Szczegóły|
|--------|-----------|
|**Konto usługi NDES**|Podaj konto użytkownika domeny, które będzie używane jako konto usługi NDES.|

## <a name="configure-your-infrastructure"></a>Konfigurowanie infrastruktury
Aby można było skonfigurować profile certyfikatów, wykonaj poniższe kroki. Te kroki wymagają znajomości systemu Windows Server 2012 R2 i nowszego oraz usług certyfikatów Active Directory (ADCS):

#### <a name="step-1---create-an-ndes-service-account"></a>Krok 1 — Tworzenie konta usługi NDES

Utwórz konto użytkownika domeny, które będzie używane jako konto usługi NDES. To konto należy podać podczas konfigurowania szablonów w wystawiającym urzędzie certyfikacji przed instalacją i konfiguracją usługi NDES. Upewnij się, że użytkownik ma uprawnienia domyślne, **Logowanie lokalnie**, **Logowanie jako usługa** i **Logowanie w trybie wsadowym**. Niektóre organizacje mają zaostrzone zasady wykluczające te uprawnienia.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Krok 2 — Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji
To zadanie obejmuje:

- Konfigurowanie szablonu certyfikatu dla usługi NDES
- Publikowanie szablonu certyfikatu dla usługi NDES

##### <a name="configure-the-certification-authority"></a>Konfigurowanie urzędu certyfikacji

1. Zaloguj się jako administrator przedsiębiorstwa.

2. W przypadku wystawiającego urzędu certyfikacji użyj przystawki Szablony certyfikatów, aby utworzyć nowy szablon niestandardowy. Inna możliwość to skopiowanie istniejącego szablonu (na przykład szablonu Użytkownik), a następnie zaktualizowanie go pod kątem użycia na potrzeby usługi NDES.

   >[!NOTE]
   > Szablon certyfikatu usługi NDES musi być oparty na szablonie certyfikatu w wersji 2 (z obsługą systemu Windows 2003).

   Szablon wymaga następującej konfiguracji:

   - Podaj przyjazną **nazwę wyświetlaną szablonu**.

   - W obszarze **Nazwa podmiotu** wybierz pozycję **Podaj w żądaniu**. (Zabezpieczenia są wymuszane przez moduł zasad usługi Intune dla usługi NDES).

   - Na karcie **Rozszerzenia** potwierdź, że pozycja **Opis zasad aplikacji** obejmuje pozycję **Uwierzytelnianie klienta**.

     > [!IMPORTANT]
     > W przypadku szablonów certyfikatów dla systemów iOS i macOS na karcie **Rozszerzenia** otwórz do edycji pozycję **Użycie klucza** i potwierdź, że pozycja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

   - Na karcie **Zabezpieczenia** dodaj konto usługi NDES i nadaj mu uprawnienia **Rejestracja** do szablonu. Administratorzy usługi Intune, którzy tworzą profile SCEP, muszą mieć prawa **Odczyt**, aby mogli przechodzić do szablonu podczas tworzenia profilów SCEP.

     > [!NOTE]
     > Aby można było odwołać certyfikaty, konto usługi NDES musi mieć prawa *Wystawianie certyfikatów i zarządzanie nimi* do każdego szablonu certyfikatu używanego przez profil certyfikatu.

3. Sprawdź **Okres ważności** na karcie **Ogólne** szablonu. Domyślnie usługa Intune używa wartości skonfigurowanej w szablonie. Urząd certyfikacji można jednak skonfigurować tak, aby umożliwiał żądającemu podanie innej wartości, którą można następnie ustawić przy użyciu konsoli administratora usługi Intune. Jeśli chcesz, aby zawsze była używana wartość określona w szablonie, pomiń pozostałe czynności w tym kroku.

   > [!IMPORTANT]
   > W przypadku platform iOS i macOS wartość ustawiona w szablonie jest używana zawsze, niezależnie od innych ustawień.

Przykładowa konfiguracja szablonu:

![Szablon, karta obsługi żądań](./media/scep_ndes_request_handling.png)

![Szablon, karta nazwy podmiotu](./media/scep_ndes_subject_name.jpg)

![Szablon, karta zabezpieczeń](./media/scep_ndes_security.jpg)

![Szablon, karta rozszerzeń](./media/scep_ndes_extensions.jpg)

![Szablon, karta wymagań wystawiania](./media/scep_ndes_issuance_reqs.jpg)

> [!IMPORTANT]
> W przypadku zasad aplikacji należy dodać tylko wymagane zasady aplikacji. Należy uzgodnić wybrane opcje z administratorami zabezpieczeń.

Skonfiguruj urząd certyfikacji, tak aby umożliwiał żądającemu podanie okresu ważności:

1. Uruchom w urzędzie certyfikacji następujące polecenia:
   - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   - **net stop certsvc**
   - **net start certsvc**

2. Użyj przystawki Urząd certyfikacji dla wystawiającego urzędu certyfikacji, aby opublikować szablon certyfikatu.
   Zaznacz węzeł **Szablony certyfikatów**, kliknij pozycje **Akcja** > **Nowy** > **Szablon certyfikatu do wystawienia**, a następnie wybierz szablon utworzony w kroku 2.

3. Sprawdź, czy certyfikat został opublikowany, wyświetlając go w folderze **Szablony certyfikatów** .

#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Krok 3 — Konfigurowanie wymagań wstępnych na serwerze usługi NDES
To zadanie obejmuje:

- Dodawanie usługi NDES do systemu Windows Serwer oraz konfigurowanie usługi IIS do obsługi usługi NDES
- Dodawanie konta usługi NDES do grupy IIS_IUSR
- Ustawianie nazwy SPN dla konta usługi NDES

1. Na serwerze, na którym jest uruchomiona usługa NDES, zaloguj się jako **Administrator przedsiębiorstwa**, a następnie użyj [Kreatora dodawania ról i funkcji](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) do zainstalowania usługi NDES:

   1. W kreatorze wybierz pozycję **Usługi certyfikatów Active Directory**, aby uzyskać dostęp do usług ról ADCS. Zaznacz pozycję **Usługa rejestracji urządzeń sieciowych**, wyczyść pole wyboru **Urząd certyfikacji**, a następnie zakończ pracę kreatora.

      > [!TIP]
      > W oknie **Postęp instalacji** nie zaznaczaj pozycji **Zamknij**. Zamiast tego wybierz link **Skonfiguruj usługi certyfikatów w usłudze Active Directory na serwerze docelowym**. Zostanie otwarty kreator **Konfiguracja usług AD CS**, który będzie używany w ramach następnego zadania. Po otwarciu kreatora Konfiguracja usług AD CS można zamknąć kreatora Dodaj role i funkcje.

   2. Po dodaniu usługi NDES do serwera kreator przeprowadzi również instalację usług IIS. Upewnij się, że usługi IIS są skonfigurowane w następujący sposób:

   3. **Serwer sieci Web** > **Zabezpieczenia** > **Filtrowanie żądań**

   4. **Serwer sieci Web** > **Projektowanie aplikacji** > **ASP.NET 3.5**. Podczas instalacji programu ASP .NET 3.5 zostanie zainstalowany program .NET Framework 3.5. Podczas instalacji programu .NET Framework 3.5 należy zainstalować zarówno podstawowy składnik **.NET Framework 3.5**, jak i składnik **Aktywacja HTTP**.

   5. **Serwer sieci Web** > **Projektowanie aplikacji** > **ASP.NET 4.5**. Podczas instalacji programu ASP .NET 4.5 zostanie zainstalowany program .NET Framework 4.5. Podczas instalowania programu .NET Framework 4.5 należy zainstalować podstawowy składnik **.NET Framework 4.5**, składnik **ASP .NET 4.5** oraz składnik **Usługi WCF** > **Aktywacja HTTP**.

   6. **Narzędzia do zarządzania** > **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** > **Zgodność z metabazą usług IIS 6**

   7. **Narzędzia do zarządzania** > **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** > **Zgodność z usługą WMI dla usług IIS 6**

   8. Na serwerze dodaj konto usługi NDES jako element członkowski grupy **IIS_IUSR**.

2. Aby ustawić nazwę SPN konta usługi NDES, w oknie wiersza polecenia z podwyższonym poziomem uprawnień uruchom następujące polecenie:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Na przykład jeśli serwer usługi NDES nosi nazwę **Serwer01**, Twoja domena to **Contoso.com**, a konto usługi to **UslugaNDES**, użyj następującego polecenia:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Krok 4 — Konfigurowanie usługi NDES do użycia z usługą Intune
To zadanie obejmuje:

- Konfigurowanie usługi NDES do użycia z urzędem wystawiającym certyfikaty
- Powiązanie certyfikatu uwierzytelniania serwera (SSL) w usługach IIS
- Konfigurowanie filtrowania żądań w usługach IIS

1. Na serwerze usługi NDES otwórz kreatora Konfiguracja usług AD CS, a następnie wprowadź następujące aktualizacje:

    > [!TIP]
    > Jeśli w poprzednim zadaniu kliknięto odpowiedni link, kreator jest już otwarty. W przeciwnym przypadku otwórz Menedżera serwera, aby przejść do konfiguracji powdrożeniowej usług certyfikatów Active Directory.

   - W polu **Usługi ról** wybierz pozycję **Usługa rejestracji urządzeń sieciowych**.
   - Na stronie **Konto usługi dla usługi rejestracji urządzeń sieciowych** podaj konto usługi NDES.
   - Na stronie **Urząd certyfikacji dla usługi rejestrowania urządzeń sieciowych** kliknij pozycję **Wybierz**, a następnie wybierz wystawiający urząd certyfikacji, w którym skonfigurowano szablon certyfikatu.
   - Na stronie **Kryptografia dla usługi rejestracji urządzeń sieciowych** ustaw długość klucza zgodnie z wymaganiami firmy.
   - Na stronie **Potwierdzenie** wybierz pozycję **Konfiguruj**, aby zakończyć pracę kreatora.

2. Po zakończeniu pracy kreatora zaktualizuj następujący klucz rejestru na serwerze usługi NDES:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Aby zaktualizować ten klucz, określ wartość **Przeznaczenie** dla szablonu certyfikatu (znajdującą się na karcie **Obsługiwanie żądań**). Następnie zaktualizuj odpowiadający wpis w rejestrze, zastępując istniejące dane nazwą szablonu certyfikatu (a nie nazwą wyświetlaną szablonu) określonego w zadaniu 1. Poniższa tabela zawiera mapowanie celów szablonu certyfikatu na wartości rejestru:

    |Cel szablonu certyfikatu (na karcie Obsługiwanie żądań)|Wartość rejestru do edycji|Wartość wyświetlona w konsoli administratora usługi Intune dla profilu SCEP|
    |---|---|---|
    |Podpis|SignatureTemplate|Podpis cyfrowy|
    |Szyfrowanie|EncryptionTemplate|Szyfrowanie klucza|
    |Podpis i szyfrowanie|GeneralPurposeTemplate|Szyfrowanie klucza<br/>Podpis cyfrowy|

    Na przykład jeśli Cel szablonu certyfikatu to **Szyfrowanie**, należy edytować wartość **EncryptionTemplate** i wprowadzić nazwę szablonu certyfikatu.

3. Serwer usługi NDES odbiera długie adresy URL (zapytania), co wymaga dodania dwóch wpisów do rejestru:


   |                        Lokalizacja                        |      Wartość      | Typ  |      Dane       |
   |--------------------------------------------------------|-----------------|-------|-----------------|
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxFieldLength  | DWORD | 65534 (dziesiętnie) |
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxRequestBytes | DWORD | 65534 (dziesiętnie) |

4. W Menedżerze usług IIS wybierz pozycję **Domyślna witryna sieci Web** > **Filtrowanie żądań** > **Edytuj ustawienia funkcji**. Zmień wartości **Maksymalna długość adresu URL** i **Maksymalna długość ciągu zapytania** na *65534*, tak jak pokazano:

    ![Maksymalna długość adresu URL i zapytania w programie IIS](./media/SCEP_IIS_max_URL.png)

5. Uruchom ponownie serwer. Aby sfinalizować te zmiany, nie wystarczy uruchomić polecenie **iisreset** na serwerze.
6. Przejdź do pliku `http://*FQDN*/certsrv/mscep/mscep.dll`. Powinna zostać wyświetlona strona usługi NDES podobna do następującej:

    ![Testowanie usługi NDES](./media/SCEP_NDES_URL.png)

    Jeśli zostanie zwrócony komunikat **503 Usługa niedostępna**, sprawdź informacje w Podglądzie zdarzeń. Istnieje prawdopodobieństwo, że pula aplikacji jest zatrzymana z powodu braku prawa dla użytkownika usługi NDES. Te prawa opisano w zadaniu 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Instalowanie i powiązanie certyfikatów na serwerze usługi NDES

1. Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania serwera** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Następnie powiąż ten certyfikat SSL w usługach IIS.

    > [!TIP]
    > Po powiązaniu certyfikatu SSL w usługach IIS zainstaluj certyfikat uwierzytelniania klienta. Ten certyfikat może zostać wystawiony przez dowolny urząd certyfikacji traktowany jako zaufany przez serwer usługi NDES. Chociaż nie jest to zalecane, możesz użyć tego samego certyfikatu do uwierzytelniania serwera i klienta, o ile dany certyfikat ma obie wartości ulepszonego użycia klucza (EKU). Poniższe kroki zawierają informacje na temat tych certyfikatów uwierzytelniania.

   1. Po uzyskaniu certyfikatu uwierzytelniania serwera otwórz **Menedżera usług IIS** i wybierz pozycję **Domyślna witryna sieci Web**. W okienku **Akcje** wybierz pozycję **Powiązania**.

   2. Wybierz pozycję **Dodaj**, w polu **Typ** ustaw wartość **https** i potwierdź, że ustawiony port to **443**. W przypadku autonomicznej usługi Intune jest obsługiwany tylko port 443.

   3. W polu **Certyfikat SSL** podaj certyfikat uwierzytelniania serwera.

      > [!NOTE]
      > Jeśli serwer usługi NDES używa nazwy zewnętrznej i wewnętrznej dla pojedynczego adresu sieciowego, certyfikat uwierzytelniania serwera musi spełniać następujące warunki:
      > - Pole **Nazwa podmiotu** zawiera zewnętrzną, publiczną nazwę serwera.
      > - Pole **Alternatywna nazwa podmiotu** zawiera wewnętrzną nazwę serwera.

2. Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania klienta** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Może to być ten sam certyfikat, którego użyto jako certyfikatu uwierzytelniania serwera, o ile ma on obie funkcje.

    Certyfikat uwierzytelniania klienta musi mieć następujące właściwości:

    - **Ulepszone użycie klucza**: musi to być wartość **Uwierzytelnianie klienta**

    - **Nazwa podmiotu**: ta wartość musi być nazwą DNS serwera, na którym jest instalowany certyfikat (serwera usługi NDES).

##### <a name="configure-iis-request-filtering"></a>Konfigurowanie filtrowania żądań w usługach IIS

1. Na serwerze usługi NDES otwórz **Menedżera usług IIS**, kliknij pozycję **Domyślna witryna sieci Web** w okienku **Połączenia**, a następnie otwórz okno **Filtrowanie żądań**.

2. Wybierz pozycję **Edytuj ustawienia funkcji**, a następnie podaj następujące wartości:

    - **Długość ciągu zapytania (w bajtach)** = **65534**
    - **Maksymalna długość adresu URL (w bajtach)** = **65534**

3. Sprawdź następujący klucz rejestru:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Potwierdź, że następujące wartości są ustawione jako wpisy typu DWORD:

    - Nazwa: **MaxFieldLength**o wartości dziesiętnej **65534**
    - Nazwa: **MaxRequestBytes**o wartości dziesiętnej **65534**

4. Uruchom ponownie serwer usługi NDES. Teraz serwer jest gotowy do obsługi łącznika certyfikatów.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Krok 5 — Włączanie, instalowanie i konfigurowanie łącznika certyfikatów usługi Intune
To zadanie obejmuje:

- Włączanie obsługi usługi NDES w usłudze Intune.
- Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów na serwerze hostującym rolę usługi rejestracji urządzeń sieciowych (NDES) w środowisku. Aby zwiększyć skalę wdrożenia usługi NDES w organizacji, można zainstalować wiele serwerów usługi NDES z łącznikiem certyfikatów usługi Microsoft Intune na każdym z nich.

##### <a name="download-install-and-configure-the-certificate-connector"></a>Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów

![ConnectorDownload](./media/certificates-download-connector.png)

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzenia**, a następnie pozycję **Urząd certyfikacji**.
4. Wybierz pozycję **Dodaj**, a następnie pozycję **Pobierz plik łącznika**. Zapisz pobraną zawartość w lokalizacji dostępnej z serwera, na którym zostanie ona zainstalowana.
5. Po zakończeniu pobierania przejdź do serwera hostującego rolę usługi rejestracji urządzeń sieciowych (NDES). Następnie:

    1. Upewnij się, że jest zainstalowany program .NET 4.5 Framework, ponieważ jest on wymagany przez łącznik certyfikatów usługi NDES. Program .NET 4.5 Framework jest automatycznie dołączany do systemu Windows Server 2012 R2 i nowszych wersji.
    2. Uruchom instalator (**NDESConnectorSetup.exe**). Instalator zainstaluje też moduł zasad dla usługi NDES i usługę sieci Web CRP. Usługa internetowa CRP, CertificateRegistrationSvc, jest uruchamiana jako aplikacja w usługach IIS.

    > [!NOTE]
    > Podczas instalacji usługi NDES dla autonomicznej usługi Intune usługa CRP jest instalowana automatycznie wraz z łącznikiem certyfikatów. W przypadku używania usługi Intune z programem Configuration Manager punkt rejestracji certyfikatu (CRP) jest instalowany jako osobna rola systemu lokacji.

6. Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, kliknij pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany na serwerze usługi NDES w ramach Zadania 3.

    Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune** . Mimo że wybrany certyfikat nie jest wyświetlany, wybierz pozycję **Dalej**, aby wyświetlić właściwości certyfikatu. Wybierz pozycję **Dalej**, a następnie pozycję **Zainstaluj**.

    > [!IMPORTANT]
    > Nie można zarejestrować łącznika certyfikatów usługi Intune z włączoną opcją Konfiguracja zwiększonych zabezpieczeń programu Internet Explorer. Aby można było korzystać z łącznika certyfikatów usługi Intune, należy [wyłączyć opcję Konfiguracja zwiększonych zabezpieczeń programu IE](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx).

7. Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

    > [!TIP]
    > Jeśli kreator zostanie zamknięty przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz uruchomić go za pomocą następującego polecenia:
    >
    > <install_Path>\NDESConnectorUI\NDESConnectorUI.exe

8. W interfejsie użytkownika **łącznika certyfikatów** :

    Wybierz pozycję **Zaloguj** i podaj poświadczenia administratora usługi Intune lub administratora dzierżawy z uprawnieniami administratora globalnego.

    > [!IMPORTANT]
    > Konto użytkownika musi mieć przypisaną prawidłową licencję usługi Intune. Jeśli konto użytkownika nie ma prawidłowej licencji usługi Intune, działanie pliku NDESConnectorUI.exe zakończy się niepowodzeniem.

    Jeśli Twoja organizacja korzysta z serwera proxy i serwer usługi NDES wymaga go na potrzeby dostępu do Internetu, wybierz pozycję **Użyj serwera proxy**, a następnie podaj nazwę serwera proxy, port oraz poświadczenia konta, aby nawiązać połączenie.

    Wybierz kartę **Zaawansowane** i podaj poświadczenia konta z uprawnieniem **Wystawianie certyfikatów i zarządzanie nimi** dla wystawiającego urzędu certyfikacji. **Zastosuj** zmiany.

    Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.

9. Otwórz wiersz polecenia, wpisz **services.msc**, a następnie naciśnij klawisz **Enter**. Kliknij prawym przyciskiem myszy pozycję **Usługa łącznika usługi Intune** i wybierz polecenie **Uruchom ponownie**.

Aby sprawdzić, czy usługa jest uruchomiona, otwórz przeglądarkę i podaj następujący adres URL. Powinien zostać zwrócony błąd **403**:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> Obsługa protokołu TLS 1.2 jest dołączona do łącznika certyfikatów usługi NDES. Jeśli więc serwer z zainstalowanym łącznikiem certyfikatów usługi NDES obsługuje protokół TLS 1.2, jest używany protokół TLS 1.2. Jeśli serwer nie obsługuje protokołu TLS 1.2, jest używany protokół TLS 1.1. Obecnie protokół TLS 1.1 jest używany do uwierzytelniania między urządzeniami a serwerem.

## <a name="create-a-scep-certificate-profile"></a>Tworzenie profilu certyfikatu protokołu SCEP

1. W witrynie Azure Portal otwórz usługę Microsoft Intune.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu certyfikatu SCEP.
4. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego certyfikatu protokołu SCEP. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
   - **Android**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 lub nowszy**
   - **Windows 10 lub nowszy**
5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat SCEP**.
6. W okienku **Certyfikat SCEP** skonfiguruj następujące ustawienia:

   - **Okres ważności certyfikatu**: jeśli dla wystawiającego urzędu certyfikacji uruchomiono polecenie `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE`, które dopuszcza niestandardowy okres ważności, możesz określić ilość czasu pozostałego do wygaśnięcia certyfikatu.<br>Możesz podać okres krótszy niż okres ważności w szablonie certyfikatu, ale nie dłuższy. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić jeden rok, ale nie pięć lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty. 
   - **Dostawca magazynu kluczy (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): podaj miejsce przechowywania klucza certyfikatu. Można wybrać jedną z następujących opcji:
     - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie u dostawcy magazynu kluczy oprogramowania**
     - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie niepowodzenie**
     - **Zarejestruj w usłudze Passport, w przeciwnym razie niepowodzenie (system Windows 10 i nowsze)**
     - **Zarejestruj u dostawcy magazynu kluczy oprogramowania**

   - **Format nazwy podmiotu**: wybierz z listy sposób automatycznego tworzenia nazwy podmiotu w żądaniu certyfikatu przez usługę Intune. Jeśli certyfikat przeznaczony jest dla użytkownika, możesz również uwzględnić w nazwie podmiotu adres e-mail tego użytkownika. Wybierz spośród opcji:
     - **Nieskonfigurowany**
     - **Nazwa pospolita**
     - **Nazwa pospolita obejmująca adres e-mail**
     - **Nazwa pospolita jako adres e-mail**
     - **Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI)**
     - **Numer seryjny**
     - **Niestandardowy**: po wybraniu tej opcji jest wyświetlane kolejne pole listy rozwijanej. Użyj tego pola do podania niestandardowego formatu nazwy podmiotu. Format niestandardowy obsługuje dwie zmienne: **Nazwa pospolita (CN)** i **Adres e-mail (E)**. Dla wartości **Nazwa pospolita (CN)** można ustawić jedną z następujących zmiennych:
       - **CN={{UserName}}**: główna nazwa użytkownika, taka jak janedoe@contoso.com
       - **CN={{AAD_Device_ID}}**: identyfikator przypisany podczas rejestrowania urządzenia w usłudze Azure Active Directory (AD). Ten identyfikator jest zazwyczaj używany do uwierzytelniania za pomocą usługi Azure AD.
       - **CN={{SERIALNUMBER}}**: unikatowy numer seryjny (SN) używany zwykle przez producenta do identyfikowania urządzenia
       - **CN={{IMEINumber}}**: unikatowy numer IMEI (International Mobile Equipment Identity) używany do identyfikowania telefonu komórkowego
       - **CN={{OnPrem_Distinguished_Name}}**: sekwencja względnych nazw wyróżniających rozdzielonych przecinkami, taka jak `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

          Aby użyć zmiennej `{{OnPrem_Distinguished_Name}}`, zsynchronizuj atrybut użytkownika `onpremisesdistingishedname` z usługą Azure AD za pomocą programu [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

       - **CN = {{onPremisesSamAccountName}}**: administratorzy mogą synchronizować atrybut samAccountName z usługi Active Directory do usługi Azure AD za pomocą programu Azure AD Connect do atrybutu o nazwie `onPremisesSamAccountName`. Usługa Intune może podstawić zmienną jako część żądania wystawienia certyfikatu w podmiocie certyfikatu SCEP.  Atrybut samAccountName jest nazwą logowania użytkownika, która jest używana do obsługi klientów i serwerów z poprzedniej wersji systemu Windows (starszej niż Windows 2000). Nazwa logowania użytkownika ma format: `DomainName\testUser` lub tylko `testUser`.

          Aby użyć zmiennej `{{onPremisesSamAccountName}}`, zsynchronizuj atrybut użytkownika `onPremisesSamAccountName` z usługą Azure AD za pomocą programu [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

       Przy użyciu jednej z tych zmiennych lub ich kombinacji oraz ciągów statycznych możesz utworzyć niestandardowy format nazwy podmiotu, taki jak: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**. <br/> W tym przykładzie utworzono format nazwy podmiotu, który oprócz zmiennych CN i E używa ciągów dla wartości jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. Temat [Funkcja CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) zawiera opis tej funkcji i ciągi obsługiwane przez nią.

- **Nazwa alternatywna podmiotu**: określ sposób automatycznego tworzenia wartości dla nazwy alternatywnej podmiotu w żądaniu certyfikatu przez usługę Intune. Jeśli na przykład jako typ certyfikatu został wybrany typ użytkownika, w alternatywnej nazwie podmiotu można uwzględnić główną nazwę użytkownika (nazwę UPN). Jeśli certyfikat klienta jest używany do uwierzytelniania go wobec serwera zasad sieciowych, dla alternatywnej nazwy podmiotu musisz ustawić nazwę UPN.
- **Użycie klucza**: podaj opcje użycia klucza certyfikatu. Dostępne opcje:
  - **Szyfrowanie klucza**: zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest zaszyfrowany.
  - **Podpis cyfrowy**: zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest chroniony przy użyciu podpisu cyfrowego.
- **Rozmiar klucza (bity)**: wybierz liczbę bitów zawartych w kluczu.
- **Algorytm skrótu** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): wybierz jeden z dostępnych typów algorytmu wyznaczania wartości skrótu do użycia z tym certyfikatem. Wybierz najwyższy poziom zabezpieczeń obsługiwany przez podłączane urządzenia.
- **Certyfikat główny**: wybierz profil certyfikatu głównego urzędu certyfikacji, który został uprzednio skonfigurowany i przypisany do użytkownika lub urządzenia. Ten certyfikat urzędu certyfikacji musi być certyfikatem głównym urzędu certyfikacji wystawiającego certyfikat skonfigurowany w ramach danego profilu certyfikatu.
- **Rozszerzone użycie klucza**: użyj polecenia **Dodaj**, aby dodać wartości w zależności od przeznaczenia certyfikatu. W większości przypadków jest wymagane wprowadzenie wartości **Uwierzytelnianie klienta** dla certyfikatu, aby zapewnić użytkownikom lub urządzeniom możliwość uwierzytelnienia na serwerze. Można jednak dodać również inne użycia klucza, zgodnie z potrzebami.
- **Ustawienia rejestracji**
  - **Próg odnawiania (%)**: podaj wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
  - **Adresy URL serwerów SCEP**: podaj co najmniej jeden adres URL dla serwerów usługi NDES, które wystawiają certyfikaty za pośrednictwem protokołu SCEP.
  - Wybierz pozycję **OK**, a następnie **Utwórz**, aby utworzyć profil.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.

## <a name="assign-the-certificate-profile"></a>Przypisywanie profilu certyfikatu

Przed przypisaniem profilów certyfikatów do grup należy wziąć pod uwagę następujące kwestie:

- Podczas przypisywania profilów certyfikatów do grup na urządzeniu jest instalowany plik certyfikatu z profilu certyfikatu zaufanego urzędu certyfikacji. Profil certyfikatu protokołu SCEP jest wykorzystywany przez to urządzenie do tworzenia żądania certyfikatu.
- Profile certyfikatów mogą być instalowane wyłącznie na urządzeniach z platformą użytą podczas tworzenia profilu.
- Profile certyfikatów można również przypisywać do kolekcji użytkowników lub kolekcji urządzeń.
- Aby opublikować certyfikat dla urządzenia jak najszybciej po jego rejestracji, należy przypisać profil certyfikatu do grupy użytkowników, a nie do grupy urządzeń. W przypadku przypisania do grupy urządzeń wymagana jest pełna rejestracja urządzenia przed otrzymaniem przez nie zasad.
- Mimo że każdy profil należy przypisać osobno, konieczne jest również przypisanie profilu zaufanego certyfikatu głównego urzędu certyfikacji oraz profilu protokołu SCEP lub PKCS. W przeciwnym razie zasady certyfikatu protokołu SCEP lub PKCS nie będą działać.

    > [!NOTE]
    > W przypadku systemu iOS należy oczekiwać występowania wielu kopii certyfikatu w profilu zarządzania, jeśli wdrożono wiele profilów zasobu, które używają tego samego profilu certyfikatu.

Informacje dotyczące sposobu przypisywania profilów znajdują się w opisie [przypisywanie profilów urządzeń](device-profile-assign.md).

## <a name="intune-connector-setup-verification-and-troubleshooting"></a>Weryfikacja instalacji łącznika usługi Intune i rozwiązywanie problemów

Aby rozwiązać problemy i zweryfikować instalację łącznika usługi Intune, zobacz [Przykłady skryptów urzędu certyfikacji](https://aka.ms/intuneconnectorverificationscript)

## <a name="intune-connector-events-and-diagnostic-codes"></a>Zdarzenia łącznika usługi Intune i kody diagnostyczne

Począwszy od wersji 6.1806.x.x, usługa łącznika Intune rejestruje zdarzenia w **Podglądzie zdarzeń** (**Dzienniki aplikacji i usług** > **Łącznik usługi Microsoft Intune**). Użyj tych zdarzeń, aby w łatwiejszy sposób rozwiązywać potencjalne problemy związane z konfiguracją łącznika usługi Intune. Te zdarzenia rejestrują powodzenia i niepowodzenia operacji, a także zawierają kody diagnostyczne wraz z komunikatami, które ułatwiają administratorowi IT rozwiązywanie problemów.

### <a name="event-ids-and-descriptions"></a>Identyfikatory i opisy zdarzeń

> [!NOTE]
> Szczegółowe informacje dotyczące powiązanych kodów diagnostycznych dla poszczególnych zdarzeń zawiera tabela **Kody diagnostyczne** (w tym artykule).

| Identyfikator zdarzenia      | Nazwa zdarzenia    | Opis zdarzenia | Powiązane kody diagnostyczne |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Usługa łącznika została uruchomiona | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Usługa łącznika została zatrzymana | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Pomyślnie odnowiono certyfikat rejestracji łącznika | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Odnowienie certyfikatu rejestracji łącznika nie powiodło się. Ponownie zainstaluj łącznik. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Nie można pobrać certyfikatu rejestracji łącznika z rejestru. Przejrzyj szczegóły zdarzenia dla odcisku palca certyfikatu powiązanego z tym zdarzeniem. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Sprawdź informacje diagnostyczne w szczegółach zdarzenia. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Pomyślnie wystawiono certyfikat PKCS. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji, nazwa szablonu certyfikatu i odcisk palca certyfikatu. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Nie można wystawić certyfikatu PKCS. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji, nazwa szablonu certyfikatu i odcisk palca certyfikatu. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Pomyślnie odwołano certyfikat. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji i numer seryjny certyfikatu. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Nie można odwołać certyfikatu. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji i numer seryjny certyfikatu. Aby uzyskać dodatkowe informacje, zobacz Dzienniki SVC usługi NDES.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Pomyślnie przekazano żądanie certyfikatu lub dane dotyczące odwołania. Przejrzyj szczegóły zdarzenia, aby uzyskać informacje o przekazaniu. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Nie można przekazać żądania certyfikatu lub danych dotyczących odwołania. Przejrzyj stan przekazania w szczegółach zdarzenia, aby określić punkt awarii.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Pomyślnie pobrano żądanie podpisania certyfikatu, pobrania certyfikatu klienta lub odwołania certyfikatu. Aby uzyskać informacje o pobieraniu, przejrzyj szczegóły zdarzenia.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Nie można pobrać żądania podpisania certyfikatu, pobrać certyfikatu klienta lub odwołać certyfikatu. Aby uzyskać informacje o pobieraniu, przejrzyj szczegóły zdarzenia. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Zweryfikowanie wezwania klienta przez punkt rejestracji certyfikatu powiodło się | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Punkt rejestracji certyfikatu został ukończony, ale żądanie zostało odrzucone. Aby uzyskać więcej informacji, wyświetl kod diagnostyczny i komunikat. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Zweryfikowanie wezwania klienta przez punkt rejestracji certyfikatu nie powiodło się. Aby uzyskać więcej informacji, wyświetl kod diagnostyczny i komunikat. Wyświetl szczegóły komunikatu zdarzeń dla identyfikatora urządzenia odpowiadającego wezwaniu. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Punkt rejestracji certyfikatu pomyślnie ukończył proces powiadamiania i wysłał certyfikat na urządzenie klienckie. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Ukończenie procesu powiadamiania przez punkt rejestracji certyfikatu nie powiodło się. Aby uzyskać informacji dotyczące żądania, zobacz szczegóły komunikatu o zdarzeniu. Sprawdź połączenie między serwerem usługi NDES i urzędem certyfikacji. | 0x00000000, 0x0FFFFFFF |

### <a name="diagnostic-codes"></a>Kody diagnostyczne

| Kod diagnostyczny | Nazwa diagnostyki | Komunikatu diagnostyczny |
| -------------   | -------------   | -------------      |
| 0x00000000 | Powodzenie  | Powodzenie |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Urząd certyfikacji jest nieprawidłowy lub nieosiągalny. Sprawdź, czy urząd certyfikacji jest dostępny i Twój serwer może się z nim komunikować. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Nie odnaleziono certyfikatu autoryzacji klienta firmy Symantec w lokalnym magazynie certyfikatów. Aby uzyskać więcej informacji, zapoznaj się z artykułem [Instalacja certyfikatu autoryzacji firmy Symantec](https://docs.microsoft.com/en-us/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate).  |
| 0x00000402 | RevokeCert_AccessDenied  | Określone konto nie ma uprawnień do odwołania certyfikatu z urzędu certyfikacji. Zobacz pole Nazwa urzędu certyfikacji w szczegółach komunikatu o zdarzeniu, aby określić urząd certyfikacji.  |
| 0x00000403 | CertThumbprint_NotFound  | Nie można odnaleźć certyfikatu zgodnego z danymi wejściowymi. Zarejestruj łącznik certyfikatów i spróbuj ponownie. |
| 0x00000404 | Certificate_NotFound  | Nie można odnaleźć certyfikatu zgodnego z podanymi danymi wejściowymi. Ponownie zarejestruj łącznik certyfikatów i spróbuj ponownie. |
| 0x00000405 | Certificate_Expired  | Certyfikat wygasł. Ponownie zarejestruj łącznik certyfikatów, aby odnowić certyfikat, a następnie spróbuj ponownie. |
| 0x00000408 | CRPSCEPCert_NotFound  | Nie można odnaleźć certyfikatu szyfrowania CRP. Sprawdź, czy prawidłowo skonfigurowano usługę NDES i łącznik usługi Intune. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Nie można pobrać certyfikatu podpisywania. Sprawdź, czy usługa łącznika Intune jest poprawnie skonfigurowana i uruchomiona. Sprawdź również, czy zdarzenia pobierania certyfikatów zakończyły się pomyślnie. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Nie można zdeserializować żądania wezwania SCEP. Sprawdź, czy prawidłowo skonfigurowano usługę NDES i łącznik usługi Intune. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Wezwanie odrzucone z powodu wygasłego testu certyfikatu. Urządzenie klienckie może ponowić próbę po uzyskaniu nowego wezwania z serwera zarządzania. |
| 0x0FFFFFFFF | Unknown_Error  | Nie można wykonać żądania, ponieważ wystąpił błąd po stronie serwera. Spróbuj ponownie. |

## <a name="next-steps"></a>Następne kroki

- [Używanie certyfikatów PKCS](certficates-pfx-configure.md) lub [wystawianie certyfikatów PKCS z poziomu usługi internetowej Symantec PKI Manager](certificates-symantec-configure.md)
- [Dodawanie urzędu certyfikacji innej firmy w celu korzystania protokołu SCEP w usłudze Intune](certificate-authority-add-scep-overview.md)
