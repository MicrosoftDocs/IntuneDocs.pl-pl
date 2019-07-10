---
title: Używanie certyfikatów SCEP z usługą Microsoft Intune na platformie Azure | Microsoft Docs
description: Aby korzystać z certyfikatów SCEP w usłudze Microsoft Intune, skonfiguruj lokalną domenę usługi AD, utwórz urząd certyfikacji, skonfiguruj serwer usługi NDES i zainstaluj łącznik certyfikatów usługi Intune. Następnie utwórz profil certyfikatu SCEP i przypisz go do grup. Zapoznaj się też z różnymi identyfikatorami zdarzeń i ich opisami oraz kodami diagnostycznymi dla usługi łącznika Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/28/2019
ms.topic: article
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 22ce9ace7848ea1535b04ab6f0c0249c970e8c34
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67547368"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Konfigurowanie certyfikatów SCEP i korzystanie z nich w usłudze Intune

Ten artykuł zawiera informacje dotyczące konfigurowania infrastruktury oraz tworzenia i przypisywania profilów certyfikatów prostego protokołu rejestrowania certyfikatów (SCEP) za pomocą usługi Intune.

## <a name="configure-on-premises-infrastructure"></a>Konfigurowanie infrastruktury lokalnej

- **Domena usługi Active Directory**: Wszystkie serwery wymienione w tej części (z wyjątkiem serwera proxy aplikacji internetowych) muszą należeć do Twojej domeny usługi Active Directory.

- **Urząd certyfikacji**: wymagany jest urząd certyfikacji przedsiębiorstwa firmy Microsoft z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. Aby uzyskać szczegółowe informacje, zobacz temat [Instalowanie urzędu certyfikacji](https://technet.microsoft.com/library/jj125375.aspx).
    Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2, należy najpierw [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).

- **Serwer usługi NDES**: w systemie Windows Server 2012 R2 lub nowszym należy skonfigurować rolę serwera usługi rejestracji urządzeń sieciowych (NDES). Usługa Intune nie obsługuje usługi NDES na serwerze, na którym jest uruchomiony urząd certyfikacji przedsiębiorstwa. Temat [Wskazówki dotyczące usługi rejestracji urządzeń sieciowych](https://technet.microsoft.com/library/hh831498.aspx) zawiera instrukcje dotyczące sposobu konfiguracji systemu Windows Server 2012 R2 do hostowania usługi NDES.
Serwer usługi NDES musi być dołączony do domeny w tym samym lesie co urząd certyfikacji przedsiębiorstwa. Więcej informacji na temat wdrażania serwera usługi NDES w oddzielnym lesie, sieci izolowanej lub domenie wewnętrznej można znaleźć w temacie [Używanie modułu zasad z usługą rejestracji urządzeń sieciowych](https://technet.microsoft.com/library/dn473016.aspx). Nie jest możliwe użycie serwera usługi NDES, który jest już używany z inną usługą MDM.

- **Łącznik certyfikatów usługi Microsoft Intune**: W portalu usługi Intune przejdź do pozycji **Konfiguracja urządzenia** > **Łączniki certyfikatu** > **Dodaj** i postępuj zgodnie z *krokami instalowania łącznika protokołu SCEP*. Użyj linku pobierania w portalu, aby rozpocząć pobieranie instalatora łącznika certyfikatów w postaci pliku **NDESConnectorSetup.exe**.  Należy uruchomić ten instalator na serwerze z rolą usługi NDES.  

Łącznik certyfikatów usługi NDES obsługuje też tryb Federal Information Processing Standard (FIPS). Tryb FIPS nie jest wymagany, ale gdy jest on włączony, możesz wystawiać i odwoływać certyfikaty.

- **Serwer proxy aplikacji internetowej** (opcjonalnie): użyj serwera, na którym system Windows Server 2012 R2 lub nowszy działa jako serwer proxy aplikacji internetowej (WAP). Ta konfiguracja:
  - Umożliwia urządzeniom otrzymywanie certyfikatów przy użyciu połączenia internetowego.
  - Jest zalecana ze względów bezpieczeństwa w przypadku używania połączenia internetowego do pobierania i odnawiania certyfikatów przez urządzenia.
  
- **Serwer proxy aplikacji usługi Azure AD** (opcjonalnie): serwera proxy aplikacji usługi Azure AD można używać zamiast dedykowanego serwera proxy aplikacji internetowej (WAP) w celu publikowania serwera usługi NDES w Internecie. Aby uzyskać więcej informacji, zobacz [Zapewnianie bezpiecznego dostępu zdalnego do aplikacji lokalnych](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

#### <a name="additional"></a>Dodatkowe

- Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych. Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).
- Serwer WAP musi mieć certyfikat SSL pasujący do nazwy opublikowanej dla klientów zewnętrznych oraz ufać certyfikatowi SSL używanemu na serwerze usługi NDES. Te certyfikaty umożliwiają serwerowi proxy aplikacji sieci Web zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z serwerem usługi NDES.

Aby uzyskać więcej informacji, zobacz [Plan certificates for WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) (Planowanie certyfikatów protokołu WAP) i [ogólne informacje na temat serwerów WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="network-requirements"></a>Wymagania dotyczące sieci

Jeśli nie używasz odwrotnego serwera proxy, na przykład WAP lub Azure AD App Proxy, musisz zezwolić na ruch TCP na porcie 443 ze wszystkich hostów/adresów IP w Internecie do serwera usługi NDES.

Zezwalaj na wszystkie porty i protokoły wymagane na potrzeby ruchu pomiędzy serwerem usługi NDES a dowolną infrastrukturą pomocniczą. Serwer usługi NDES musi na przykład komunikować się z urzędem certyfikacji, serwerami DNS, serwerami programu Configuration Manager, kontrolerami domeny, a potencjalnie także innymi usługami w środowisku.

Zaleca się opublikowanie serwera usługi NDES za pośrednictwem odwrotnego serwera proxy, takiego jak [serwer proxy aplikacji usługi Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [serwer proxy dostępu do sieci Web](https://technet.microsoft.com/library/dn584107.aspx) lub serwer proxy innych firm.

### <a name="certificates-and-templates"></a>Certyfikaty i szablony  

|Obiekt|Szczegóły|
|----------|-----------|
|**Szablon certyfikatu**|Skonfiguruj ten szablon na serwerze urzędu wystawiającego certyfikaty.|
|**Certyfikat uwierzytelniania klienta**|Żądany od urzędu wystawiającego certyfikaty lub publicznego urzędu certyfikacji; instalowany na serwerze usługi NDES.|
|**Certyfikat uwierzytelniania serwera**|Żądany od urzędu wystawiającego certyfikaty lub publicznego urzędu certyfikacji; certyfikat SSL instalowany i powiązany w usługach IIS na serwerze usługi NDES. Jeśli certyfikat ma ustawione użycie kluczy uwierzytelniania klienta i serwera (**rozszerzenia EKU**), wówczas można użyć tego samego certyfikatu.|
|**Certyfikat zaufanego głównego urzędu certyfikacji**|Ten certyfikat należy wyeksportować w formacie pliku **cer** z głównego urzędu certyfikacji lub z dowolnego urządzenia traktującego główny urząd certyfikacji jako zaufany. Następnie należy przypisać go do użytkowników i/lub urządzeń, używając profilu certyfikatu zaufanego urzędu certyfikacji.<br /> **UWAGA:<br /> po przypisaniu profilu certyfikatu SCEP przypisz *profil zaufanego certyfikatu głównego*, którego dotyczy odwołanie w profilu certyfikatu SCEP, do tej samej grupy użytkowników lub urządzeń.  Aby utworzyć ten profil, zobacz sekcję [Tworzenie profilu zaufanego certyfikatu](certficates-pfx-configure.md#create-a-trusted-certificate-profile) w artykule dotyczącym profilów certyfikatów PKCS.** <br/><br />Należy użyć jednego certyfikatu zaufanego głównego urzędu certyfikacji dla każdej platformy systemu operacyjnego i powiązać te certyfikaty z poszczególnymi utworzonymi profilami zaufanych certyfikatów głównych. <br /><br />W razie potrzeby można użyć dodatkowych certyfikatów zaufanego głównego urzędu certyfikacji. Można na przykład zrobić to, aby urząd certyfikacji podpisujący certyfikaty uwierzytelniania serwera dla punktów dostępowych Wi-Fi był traktowany jako zaufany.|

### <a name="accounts"></a>Konta

|Nazwa|Szczegóły|
|--------|-----------|
|**Konto usługi NDES**|Podaj konto użytkownika domeny, które będzie używane jako konto usługi NDES. |

## <a name="configure-your-infrastructure"></a>Konfigurowanie infrastruktury
Aby można było skonfigurować profile certyfikatów, wykonaj poniższe kroki. Te kroki wymagają znajomości systemu Windows Server 2012 R2 lub nowszego oraz usług certyfikatów Active Directory (ADCS):

#### <a name="step-1---create-an-ndes-service-account"></a>Krok 1 — Tworzenie konta usługi NDES

Utwórz konto użytkownika domeny, które będzie używane jako konto usługi NDES. To konto należy podać podczas konfigurowania szablonów w wystawiającym urzędzie certyfikacji przed instalacją i konfiguracją usługi NDES. Upewnij się, że użytkownik ma uprawnienia domyślne, **Logowanie lokalnie**, **Logowanie jako usługa** i **Logowanie w trybie wsadowym**. Niektóre organizacje mają zaostrzone zasady wykluczające te uprawnienia.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Krok 2 — Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji
W tym kroku:

- Konfigurowanie szablonu certyfikatu dla usługi NDES
- Publikowanie szablonu certyfikatu dla usługi NDES

##### <a name="configure-the-certification-authority"></a>Konfigurowanie urzędu certyfikacji

1. Zaloguj się jako administrator przedsiębiorstwa.

2. W przypadku wystawiającego urzędu certyfikacji użyj przystawki Szablony certyfikatów, aby utworzyć nowy szablon niestandardowy. Inna możliwość to skopiowanie istniejącego szablonu (na przykład szablonu Użytkownik), a następnie zaktualizowanie go pod kątem użycia na potrzeby usługi NDES.

   >[!NOTE]
   > Szablon certyfikatu usługi NDES musi być oparty na szablonie certyfikatu w wersji 2 (z obsługą systemu Windows 2003).

   Szablon wymaga następującej konfiguracji:

   - W obszarze **Ogólne**:
   
       - Upewnij się, że właściwość **Publikuj certyfikat w usłudze Active Directory** **nie** jest zaznaczona.
       - Podaj przyjazną **nazwę wyświetlaną szablonu**.

   - W obszarze **Nazwa podmiotu** wybierz pozycję **Podaj w żądaniu**. (Zabezpieczenia są wymuszane przez moduł zasad usługi Intune dla usługi NDES).

   - Na karcie **Rozszerzenia** potwierdź, że pozycja **Opis zasad aplikacji** obejmuje pozycję **Uwierzytelnianie klienta**.

     > [!IMPORTANT]
     > W przypadku szablonów certyfikatów dla systemów iOS i macOS na karcie **Rozszerzenia** otwórz do edycji pozycję **Użycie klucza** i potwierdź, że pozycja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

   - Na karcie **Zabezpieczenia** dodaj konto usługi NDES i nadaj mu uprawnienia **Rejestracja** do szablonu. Administratorzy usługi Intune, którzy tworzą profile SCEP, muszą mieć prawa **Odczyt**, aby mogli przechodzić do szablonu podczas tworzenia profilów SCEP.

     > [!NOTE]
     > Aby można było odwołać certyfikaty, konto usługi NDES musi mieć prawa *Wystawianie certyfikatów i zarządzanie nimi* w urzędzie certyfikacji. Aby delegować to uprawnienie, otwórz konsolę zarządzania urzędu certyfikacji, a następnie kliknij prawym przyciskiem myszy nazwę urzędu certyfikacji. Następnie na karcie Zabezpieczenia dodaj lub wybierz konto i zaznacz pole wyboru **Wystawianie certyfikatów i zarządzanie nimi**.


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
W tym kroku:

- Dodawanie usługi NDES do systemu Windows Serwer oraz konfigurowanie usługi IIS do obsługi usługi NDES
- Dodawanie konta usługi NDES do grupy IIS_IUSR
- Ustawianie głównej nazwy usługi (SPN) dla konta usługi NDES

1. Na serwerze, na którym jest uruchomiona usługa NDES, zaloguj się jako **Administrator przedsiębiorstwa**, a następnie użyj [Kreatora dodawania ról i funkcji](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) do zainstalowania usługi NDES:

   1. W kreatorze wybierz pozycję **Usługi certyfikatów Active Directory**, aby uzyskać dostęp do usług ról ADCS. Zaznacz pozycję **Usługa rejestracji urządzeń sieciowych**, wyczyść pole wyboru **Urząd certyfikacji**, a następnie zakończ pracę kreatora.

      > [!TIP]
      > W oknie **Postęp instalacji** nie zaznaczaj pozycji **Zamknij**. Zamiast tego wybierz link **Skonfiguruj usługi certyfikatów w usłudze Active Directory na serwerze docelowym**. Zostanie otwarty kreator **Konfiguracja usług AD CS**, który będzie używany w ramach następnego kroku. Po otwarciu kreatora Konfiguracja usług AD CS można zamknąć kreatora Dodaj role i funkcje.

   2. Po dodaniu usługi NDES do serwera kreator przeprowadzi również instalację usług IIS. Upewnij się, że usługi IIS są skonfigurowane w następujący sposób:

       - **Serwer sieci Web** > **Zabezpieczenia** > **Filtrowanie żądań**

       - **Serwer sieci Web** > **Projektowanie aplikacji** > **ASP.NET 3.5** 

            Podczas instalacji programu ASP .NET 3.5 zostanie zainstalowany program .NET Framework 3.5. Podczas instalacji programu .NET Framework 3.5 należy zainstalować zarówno podstawowy składnik **.NET Framework 3.5**, jak i składnik **Aktywacja HTTP**.

       - **Serwer sieci Web** > **Projektowanie aplikacji** > **ASP.NET 4.5** 

            Podczas instalacji programu ASP .NET 4.5 zostanie zainstalowany program .NET Framework 4.5. Podczas instalowania programu .NET Framework 4.5 należy zainstalować podstawowy składnik **.NET Framework 4.5**, składnik **ASP .NET 4.5** oraz składnik **Usługi WCF** > **Aktywacja HTTP**.

       - **Narzędzia do zarządzania** > **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** > **Zgodność z metabazą usług IIS 6**

       - **Narzędzia do zarządzania** > **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** > **Zgodność z usługą WMI dla usług IIS 6**

       - Na serwerze dodaj konto usługi NDES jako element członkowski grupy lokalnej **IIS_IUSR**.

2. Aby ustawić nazwę SPN konta usługi NDES, w oknie wiersza polecenia z podwyższonym poziomem uprawnień uruchom następujące polecenie:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Na przykład jeśli serwer usługi NDES nosi nazwę **Serwer01**, Twoja domena to **Contoso.com**, a konto usługi to **UslugaNDES**, użyj następującego polecenia:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Krok 4 — Konfigurowanie usługi NDES do użycia z usługą Intune
W tym kroku:

- Konfigurowanie usługi NDES do użycia z urzędem wystawiającym certyfikaty
- Powiązanie certyfikatu uwierzytelniania serwera (SSL) w usługach IIS
- Konfigurowanie filtrowania żądań w usługach IIS

1. Na serwerze usługi NDES otwórz kreatora Konfiguracja usług AD CS, a następnie wprowadź następujące aktualizacje:

    > [!TIP]
    > Jeśli w poprzednim kroku kliknięto odpowiedni link, kreator jest już otwarty. W przeciwnym przypadku otwórz Menedżera serwera, aby przejść do konfiguracji powdrożeniowej usług certyfikatów Active Directory.

   - W polu **Usługi ról** wybierz pozycję **Usługa rejestracji urządzeń sieciowych**.
   - Na stronie **Konto usługi dla usługi rejestracji urządzeń sieciowych** podaj konto usługi NDES.
   - Na stronie **Urząd certyfikacji dla usługi rejestrowania urządzeń sieciowych** kliknij pozycję **Wybierz**, a następnie wybierz wystawiający urząd certyfikacji, w którym skonfigurowano szablon certyfikatu.
   - Na stronie **Kryptografia dla usługi rejestracji urządzeń sieciowych** ustaw długość klucza zgodnie z wymaganiami firmy.
   - Na stronie **Potwierdzenie** wybierz pozycję **Konfiguruj**, aby zakończyć pracę kreatora.

2. Po zakończeniu pracy kreatora zaktualizuj następujący klucz rejestru na serwerze usługi NDES:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Aby zaktualizować ten klucz, określ wartość **Przeznaczenie** dla szablonu certyfikatu (znajdującą się na karcie **Obsługiwanie żądań**). Następnie zaktualizuj odpowiedni wpis w rejestrze, zastępując istniejące dane nazwą szablonu certyfikatu (a nie nazwą wyświetlaną szablonu) określonego w kroku 2. Poniższa tabela zawiera mapowanie celów szablonu certyfikatu na wartości rejestru:

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

5. Uruchom ponownie serwer. Nie używaj polecenia **iisreset**; nie spowoduje ono sfinalizowania tych zmian.
6. Przejdź do pliku `http://*FQDN*/certsrv/mscep/mscep.dll`. Powinna zostać wyświetlona strona usługi NDES podobna do następującej:

    ![Testowanie usługi NDES](./media/SCEP_NDES_URL.png)

    Jeśli zostanie zwrócony komunikat **503 Usługa niedostępna**, sprawdź informacje w Podglądzie zdarzeń. Istnieje prawdopodobieństwo, że pula aplikacji jest zatrzymana z powodu braku prawa dla użytkownika usługi NDES. Te prawa opisano w kroku 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Instalowanie i powiązanie certyfikatów na serwerze usługi NDES

1. Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania serwera** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Następnie powiąż ten certyfikat SSL w usługach IIS.

    > [!TIP]
    > Po powiązaniu certyfikatu SSL w usługach IIS zainstaluj certyfikat uwierzytelniania klienta. Ten certyfikat może zostać wystawiony przez dowolny urząd certyfikacji traktowany jako zaufany przez serwer usługi NDES. Można użyć tego samego certyfikatu, jeśli certyfikat ma ustawione użycie kluczy uwierzytelniania klienta i serwera (**Rozszerzenia EKU**). Poniższe kroki zawierają informacje na temat tych certyfikatów uwierzytelniania.

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

    - **Nazwa podmiotu**: ta wartość musi być nazwą DNS serwera, na którym jest instalowany certyfikat (serwer usługi NDES)

##### <a name="configure-iis-request-filtering"></a>Konfigurowanie filtrowania żądań w usługach IIS

1. Na serwerze usługi NDES otwórz **Menedżera usług IIS**, kliknij pozycję **Domyślna witryna sieci Web** w okienku **Połączenia**, a następnie otwórz okno **Filtrowanie żądań**.

2. Wybierz pozycję **Edytuj ustawienia funkcji**, a następnie podaj następujące wartości:

    - **Długość ciągu zapytania (w bajtach)**  = **65534**
    - **Maksymalna długość adresu URL (w bajtach)**  = **65534**

3. Sprawdź następujący klucz rejestru:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Potwierdź, że następujące wartości są ustawione jako wpisy typu DWORD:

    - Nazwa: **MaxFieldLength** o wartości dziesiętnej **65534**
    - Nazwa: **MaxRequestBytes** o wartości dziesiętnej **65534**

4. Uruchom ponownie serwer usługi NDES. Teraz serwer jest gotowy do obsługi łącznika certyfikatów.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Krok 5 — Włączanie, instalowanie i konfigurowanie łącznika certyfikatów usługi Intune
W tym kroku:

- Włączanie obsługi usługi NDES w usłudze Intune.
- Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów na serwerze hostującym rolę usługi rejestracji urządzeń sieciowych (NDES) w środowisku. Aby zwiększyć skalę wdrożenia usługi NDES w organizacji, można zainstalować wiele serwerów usługi NDES z łącznikiem certyfikatów usługi Microsoft Intune na każdym z nich.

##### <a name="download-install-and-configure-the-certificate-connector"></a>Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów

> [!IMPORTANT] 
> Łącznik certyfikatów usługi Microsoft Intune **musi** zostać zainstalowany na osobnym serwerze systemu Windows. Nie można go zainstalować w wystawiającym urzędzie certyfikacji. **Musi** także być zainstalowany na tym samym serwerze jako rola usługi rejestracji urządzeń sieciowych (NDES).

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzenia** > **Łączniki certyfikatu** > **Dodaj**.
3. Pobierz i zapisz plik łącznika protokołu SCEP. Zapisz go w lokalizacji dostępnej z serwera usługi rejestracji urządzeń sieciowych (NDES), na którym zamierzasz zainstalować łącznik.

   ![ConnectorDownload](./media/certificates-scep-configure/download-certificates-connector.png)


4. Po zakończeniu pobierania przejdź do serwera NDES hostującego usługę rejestracji urządzeń sieciowych (NDES). Następnie:

    1. Upewnij się, że jest zainstalowany program .NET 4.5 Framework, ponieważ jest on wymagany przez łącznik certyfikatów usługi NDES. Program .NET 4.5 Framework jest automatycznie dołączany do systemu Windows Server 2012 R2 i nowszych wersji.
    2. Użyj konta z uprawnieniami administracyjnymi do serwera, aby uruchomić instalatora (**NDESConnectorSetup.exe**). Instalator zainstaluje też moduł zasad dla usługi NDES i usługę sieci Web CRP. Usługa internetowa CRP, CertificateRegistrationSvc, jest uruchamiana jako aplikacja w usługach IIS.

    > [!NOTE]
    > Podczas instalacji usługi NDES dla autonomicznej usługi Intune usługa CRP jest instalowana automatycznie wraz z łącznikiem certyfikatów. W przypadku używania usługi Intune z programem Configuration Manager punkt rejestracji certyfikatu (CRP) jest instalowany jako osobna rola systemu lokacji.

5. Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, kliknij pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany na serwerze usługi NDES w ramach kroku 4.

    Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune** . Mimo że wybrany certyfikat nie jest wyświetlany, wybierz pozycję **Dalej**, aby wyświetlić właściwości certyfikatu. Wybierz pozycję **Dalej**, a następnie pozycję **Zainstaluj**.

    > [!IMPORTANT]
    > Na serwerze NDES hostującym łącznik certyfikatów usługi Intune musi być [wyłączona](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) opcja Konfiguracja zwiększonych zabezpieczeń programu Internet Explorer.

6. Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

    > [!TIP]
    > Jeśli kreator zostanie zamknięty przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz uruchomić go za pomocą następującego polecenia:
    >
    > <ścieżka_instalacji>\NDESConnectorUI\NDESConnectorUI.exe

7. W interfejsie użytkownika **łącznika certyfikatów** :

    Wybierz pozycję **Zaloguj** i podaj poświadczenia administratora usługi Intune lub administratora dzierżawy z uprawnieniami administratora globalnego. Po zalogowaniu łącznik certyfikatu usługi Intune pobierze certyfikat z usługi Intune. Ten certyfikat jest używany do uwierzytelniania pomiędzy łącznikiem a usługą Intune.

    > [!IMPORTANT]
    > Konto użytkownika musi mieć przypisaną prawidłową licencję usługi Intune. Jeśli konto użytkownika nie ma prawidłowej licencji usługi Intune, działanie pliku NDESConnectorUI.exe zakończy się niepowodzeniem.

    Jeśli Twoja organizacja korzysta z serwera proxy i serwer usługi NDES wymaga go na potrzeby dostępu do Internetu, wybierz pozycję **Użyj serwera proxy**. Następnie wprowadź nazwę serwera proxy, port oraz poświadczenia konta, aby nawiązać połączenie.

    Wybierz kartę **Zaawansowane** i podaj poświadczenia konta z uprawnieniem **Wystawianie certyfikatów i zarządzanie nimi** dla wystawiającego urzędu certyfikacji. **Zastosuj** zmiany. Jeśli to uprawnienie zostało delegowane do konta usługi NDES podczas [konfigurowania urzędu certyfikacji](#configure-the-certification-authority), w tym miejscu wybierz to konto. 

    Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.

8. Otwórz wiersz polecenia, wpisz **services.msc**, a następnie naciśnij klawisz **Enter**. Kliknij prawym przyciskiem myszy pozycję **Usługa łącznika usługi Intune** > **Uruchom ponownie**.

Aby sprawdzić, czy usługa jest uruchomiona, otwórz przeglądarkę i podaj następujący adres URL. Powinien zostać zwrócony błąd **403**:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> Obsługa protokołu TLS 1.2 jest dołączona do łącznika certyfikatów usługi NDES. Jeśli więc serwer z zainstalowanym łącznikiem certyfikatów usługi NDES obsługuje protokół TLS 1.2, jest używany protokół TLS 1.2. Jeśli serwer nie obsługuje protokołu TLS 1.2, jest używany protokół TLS 1.1. Obecnie protokół TLS 1.1 jest używany do uwierzytelniania między urządzeniami a serwerem.

## <a name="create-a-scep-certificate-profile"></a>Tworzenie profilu certyfikatu protokołu SCEP

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu certyfikatu SCEP.
4. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego certyfikatu protokołu SCEP. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 lub nowszy**
   - **Windows 10 lub nowszy**
5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat SCEP**.
6. Podaj następujące ustawienia:

   - **Typ certyfikatu**: wybierz pozycję **Użytkownik** w przypadku certyfikatów użytkownika. Certyfikat typu **Użytkownik** może zawierać atrybuty użytkownika i urządzenia w temacie i nazwie SAN certyfikatu.  Wybierz opcję **Urządzenie** w przypadku scenariuszy obejmujących urządzenia bez użytkowników, takie jak kioski, lub urządzenia z systemem Windows, umieszczając certyfikat w magazynie certyfikatów Komputer lokalny. Certyfikaty typu **Urządzenie** mogą zawierać tylko atrybuty urządzenia w temacie i nazwie SAN certyfikatu.  Certyfikaty typu **Urządzenie** są dostępne dla następujących platform:  
     - Android Enterprise — profil służbowy
     - iOS
     - macOS
     - Windows 8.1 i nowsze
     - System Windows 10 lub nowszy


   - **Format nazwy podmiotu**: wybierz sposób automatycznego tworzenia nazwy podmiotu w żądaniu certyfikatu przez usługę Intune. Opcje zmienią się, jeśli wybierzesz typ certyfikatu **Użytkownik** lub typ certyfikatu **Urządzenie**. 

        **Typ certyfikatu Użytkownik**  

        W nazwie podmiotu można uwzględnić adres e-mail użytkownika. Wybierz spośród opcji:

        - **Nieskonfigurowany**
        - **Nazwa pospolita**
        - **Nazwa pospolita obejmująca adres e-mail**
        - **Nazwa pospolita jako adres e-mail**
        - **Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI)**
        - **Numer seryjny**
        - **Niestandardowy**: po wybraniu tej opcji zostanie również wyświetlone pole tekstowe **Niestandardowy**. Użyj tego pola do wprowadzenia niestandardowego formatu nazwy podmiotu, w tym zmiennych. Format niestandardowy obsługuje dwie zmienne: **Nazwa pospolita (CN)** i **Adres e-mail (E)** . Dla wartości **Nazwa pospolita (CN)** można ustawić jedną z następujących zmiennych:

            - **CN={{UserName}}** : główna nazwa użytkownika, taka jak janedoe@contoso.com
            - **CN={{AAD_Device_ID}}** : identyfikator przypisany podczas rejestrowania urządzenia w usłudze Azure Active Directory (AD). Ten identyfikator jest zazwyczaj używany do uwierzytelniania za pomocą usługi Azure AD.
            - **CN={{SERIALNUMBER}}** : unikatowy numer seryjny (SN) używany zwykle przez producenta do identyfikowania urządzenia
            - **CN={{IMEINumber}}** : unikatowy numer IMEI (International Mobile Equipment Identity) używany do identyfikowania telefonu komórkowego
            - **CN={{OnPrem_Distinguished_Name}}** : sekwencja względnych nazw wyróżniających rozdzielonych przecinkami, taka jak `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

                Aby użyć zmiennej `{{OnPrem_Distinguished_Name}}`, zsynchronizuj atrybut użytkownika `onpremisesdistingishedname` z usługą Azure AD za pomocą programu [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

            - **CN={{onPremisesSamAccountName}}** : administratorzy mogą synchronizować atrybut samAccountName z usługi Active Directory do usługi Azure AD za pomocą programu Azure AD Connect do atrybutu o nazwie `onPremisesSamAccountName`. Usługa Intune może podstawić zmienną jako część żądania wystawienia certyfikatu w podmiocie certyfikatu SCEP.  Atrybut samAccountName jest nazwą logowania użytkownika, która jest używana do obsługi klientów i serwerów z poprzedniej wersji systemu Windows (starszej niż Windows 2000). Nazwa logowania użytkownika ma format: `DomainName\testUser` lub tylko `testUser`.

                Aby użyć zmiennej `{{onPremisesSamAccountName}}`, zsynchronizuj atrybut użytkownika `onPremisesSamAccountName` z usługą Azure AD za pomocą programu [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

            Przy użyciu kombinacji jednej lub wielu spośród tych zmiennych i ciągów statycznych można utworzyć niestandardowy format nazwy podmiotu, na przykład:  

            **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

            W tym przykładzie utworzono format nazwy podmiotu, który oprócz zmiennych CN i E używa ciągów dla wartości jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. Temat [Funkcja CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) zawiera opis tej funkcji i ciągi obsługiwane przez nią.

        **Typ certyfikatu Urządzenie**  

        Jeśli używasz typu certyfikatu **Urządzenie**, możesz również używać następujących zmiennych certyfikatu urządzenia dla wartości:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Te zmienne można dodawać z tekstem statycznym w polu tekstowym wartości niestandardowej. Na przykład nazwę pospolitą można dodać jako `CN = {{DeviceName}}text`.

        > [!IMPORTANT]
        >  - W statycznym tekście podmiotu nawiasy klamrowe **{}** nie otaczające zmiennej spowodują błąd. 
        >  - W przypadku stosowania zmiennej certyfikatu urządzenia należy ją ująć w nawiasy klamrowe **{}** .
        >  - Zmienna `{{FullyQualifiedDomainName}}` działa tylko w przypadku urządzeń z systemem Windows i urządzeń przyłączonych do domeny. 
        >  - W przypadku korzystania z właściwości urządzenia, takich jak numer IMEI, numer seryjny i w pełni kwalifikowana nazwa domeny w obrębie podmiotu lub nazwy SAN dla certyfikatu urządzenia, należy pamiętać, że te właściwości mogą zostać sfałszowane przez osobę z dostępem do urządzenia.
        >  - Profil nie zostanie zainstalowany na urządzeniu, jeśli określone zmienne urządzenia nie są obsługiwane. Na przykład jeśli zmienna {{IMEI}} zostanie użyta w nazwie podmiotu profilu protokołu SCEP przypisanego do urządzenia, które nie ma numeru IMEI, instalacja profilu zakończy się niepowodzeniem. 


   - **Alternatywna nazwa podmiotu**: wprowadź informacje na temat sposobu, w jaki usługa Intune ma automatycznie tworzyć wartości alternatywnej nazwy podmiotu (SAN) w żądaniu certyfikatu. Opcje zmienią się, jeśli wybierzesz typ certyfikatu **Użytkownik** lub typ certyfikatu **Urządzenie**. 

        **Typ certyfikatu Użytkownik**  

        Następujące atrybuty są dostępne:

        - Adres e-mail
        - Główna nazwa użytkownika (UPN)

            Jeśli na przykład jako typ certyfikatu został wybrany typ użytkownika, w alternatywnej nazwie podmiotu można uwzględnić główną nazwę użytkownika (nazwę UPN). Jeśli certyfikat klienta będzie używany do uwierzytelniania go wobec serwera zasad sieciowych, dla alternatywnej nazwy podmiotu należy ustawić nazwę UPN. 

        **Typ certyfikatu Urządzenie**  

        Pole tekstowe formatu tabeli, które można dostosować. Następujące atrybuty są dostępne:

        - systemem DNS,

        W przypadku typu certyfikatu **Urządzenie** możesz używać następujących zmiennych certyfikatu urządzenia dla wartości:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Te zmienne można dodawać z tekstem statycznym w polu tekstowym wartości niestandardowej. Na przykład atrybut systemu DNS można dodać jako `DNS name = {{AzureADDeviceId}}.domain.com`.

        > [!IMPORTANT]
        >  - W tekście statycznym nazwy SAN nawiasy klamrowe **{ }** , symbole potoku **|** i średniki **;** nie będą działać. 
        >  - W przypadku stosowania zmiennej certyfikatu urządzenia należy ją ująć w nawiasy klamrowe **{}** .
        >  - Zmienna `{{FullyQualifiedDomainName}}` działa tylko w przypadku urządzeń z systemem Windows i urządzeń przyłączonych do domeny. 
        >  - W przypadku korzystania z właściwości urządzenia, takich jak numer IMEI, numer seryjny i w pełni kwalifikowana nazwa domeny w obrębie podmiotu lub nazwy SAN dla certyfikatu urządzenia, należy pamiętać, że te właściwości mogą zostać sfałszowane przez osobę z dostępem do urządzenia.
        >  - Profil nie zostanie zainstalowany na urządzeniu, jeśli określone zmienne urządzenia nie są obsługiwane. Na przykład jeśli zmienna {{IMEI}} zostanie użyta w alternatywnej nazwie podmiotu profilu protokołu SCEP przypisanego do urządzenia, które nie ma numeru IMEI, instalacja profilu zakończy się niepowodzeniem.  

   - **Okres ważności certyfikatu**: jeśli na urzędzie wystawiającym certyfikaty zostało uruchomione polecenie `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE`, które dopuszcza niestandardowy okres ważności, możesz określić ilość czasu pozostałego do wygaśnięcia certyfikatu.<br>Możesz podać okres krótszy niż okres ważności w szablonie certyfikatu, ale nie dłuższy. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić jeden rok, ale nie pięć lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty. 
   - **Dostawca magazynu kluczy (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): wprowadź lokalizację przechowywania klucza do certyfikatu. Można wybrać jedną z następujących opcji:
     - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie u dostawcy magazynu kluczy oprogramowania**
     - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie niepowodzenie**
     - **Zarejestruj w usłudze Passport, w przeciwnym razie niepowodzenie (system Windows 10 i nowsze)**
     - **Zarejestruj u dostawcy magazynu kluczy oprogramowania**

   - **Użycie klucza**: podaj opcje użycia klucza certyfikatu. Dostępne opcje:
     - **Szyfrowanie klucza**: zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest zaszyfrowany
     - **Podpis cyfrowy**: zezwalaj na wymianę kluczy tylko wtedy, gdy w ochronie klucza pomaga podpis cyfrowy
   - **Rozmiar klucza (bity)** : wybierz liczbę bitów zawartych w kluczu
   - **Algorytm wyznaczania wartości skrótu** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): Wybierz jeden z dostępnych typów algorytmu wyznaczania wartości skrótu do użycia z tym certyfikatem. Wybierz najwyższy poziom zabezpieczeń obsługiwany przez podłączane urządzenia.
   - **Certyfikat główny**: wybierz [profil zaufanego certyfikatu głównego](certficates-pfx-configure.md#create-a-trusted-certificate-profile), który został uprzednio utworzony i przypisany do użytkownika i/lub urządzenia. Ten certyfikat urzędu certyfikacji musi być certyfikatem głównym urzędu certyfikacji wystawiającego certyfikat skonfigurowany w ramach danego profilu certyfikatu. Przypisz ten profil zaufanego certyfikatu głównego do tej samej grupy, która jest przypisana w profilu certyfikatu SCEP.
   - **Rozszerzone użycie klucza**: **dodaj** wartości w zależności od celu certyfikatu. W większości przypadków jest wymagane wprowadzenie wartości **Uwierzytelnianie klienta** dla certyfikatu, aby zapewnić użytkownikom lub urządzeniom możliwość uwierzytelnienia na serwerze. Można jednak dodać również inne użycia klucza, zgodnie z potrzebami.
   - **Ustawienia rejestracji**
     - **Próg odnawiania (%)** : wprowadź wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać odnowienia certyfikatu.
     - **Adresy URL serwerów SCEP**: wprowadź co najmniej jeden adres URL dla serwerów usługi NDES, które wystawiają certyfikaty za pośrednictwem protokołu SCEP. Na przykład wprowadź adres podobny do następującego: `https://ndes.contoso.com/certsrv/mscep/mscep.dll`.
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
    > Na urządzeniu z systemem iOS, kiedy profil certyfikatu SCEP jest skojarzony z dodatkowym profilem, takim jak profil sieci Wi-Fi lub VPN, urządzenie otrzymuje certyfikat dla każdego z tych dodatkowych profilów. W wyniku urządzenie z systemem iOS ma wiele certyfikatów dostarczonych przez żądanie certyfikatu SCEP.  

- Jeśli używasz funkcji współzarządzania dla usługi Intune i programu Configuration Manager, w programie Configuration Manager [ustaw suwak obciążenia](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) dla *zasad dostępu do zasobów* na **usługę Intune** lub **pilotażową usługę Intune**. To ustawienie umożliwia klientom systemu Windows 10 uruchamianie procesu żądania certyfikatu.  

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
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Nie odnaleziono certyfikatu autoryzacji klienta firmy Symantec w lokalnym magazynie certyfikatów. Więcej informacji można znaleźć w artykule [Set up Intune Certificate Connector for DigiCert PKI Platform](https://docs.microsoft.com/intune/certificates-digicert-configure#troubleshooting) (Konfigurowanie łącznika certyfikatów usługi Intune dla platformy infrastruktury kluczy publicznych firmy DigiCert).  |
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
- [Dodawanie urzędu certyfikacji innej firmy w celu korzystania z protokołu SCEP w usłudze Intune](certificate-authority-add-scep-overview.md)
- Aby uzyskać dodatkową pomoc, skorzystaj z następujących przewodników:
  - [Troubleshooting SCEP certificate profile deployment in Microsoft Intune](https://support.microsoft.com/help/4457481) (Rozwiązywanie problemów z wdrażaniem profilu certyfikatu SCEP w usłudze Microsoft Intune)
  - [Troubleshooting NDES configuration for use with Microsoft Intune certificate profiles](https://support.microsoft.com/help/4459540) (Rozwiązywanie problemów z konfiguracją usługi NDES do użycia z profilami certyfikatów usługi Microsoft Intune)
