---
title: "Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune"
titlesuffix: Azure portal
description: "Informacje dotyczące konfigurowania infrastruktury oraz tworzenia i przypisywania profilów certyfikatów SCEP usługi Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5aea88aa8898380c54867090650bd16d8bf60f3c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="configure-and-manage-scep-certificates-with-intune"></a>Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ten temat zawiera informacje dotyczące konfigurowania infrastruktury oraz tworzenia i przypisywania profilów certyfikatów prostego protokołu rejestrowania certyfikatów (SCEP, ang. Simple Certificate Enrollment Protocol) za pomocą usługi Intune.

## <a name="configure-on-premises-infrastructure"></a>Konfigurowanie infrastruktury lokalnej

-    **Domena usługi Active Directory**: wszystkie serwery wymienione w tej sekcji (z wyjątkiem serwera proxy aplikacji sieci Web) muszą być przyłączone do Twojej domeny usługi Active Directory.

-  **Urząd certyfikacji** (CA): wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. Aby uzyskać szczegółowe informacje, zobacz temat [Instalowanie urzędu certyfikacji](http://technet.microsoft.com/library/jj125375.aspx).
    Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2, należy najpierw [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Serwer usługi NDES**: na serwerze z systemem Windows Server 2012 R2 lub nowszym należy skonfigurować usługę rejestracji urządzeń sieciowych (NDES). Usługa Intune nie obsługuje usługi NDES uruchomionej na tym samym serwerze, na którym jest uruchomiony urząd certyfikacji przedsiębiorstwa. Temat [Wskazówki dotyczące usługi rejestracji urządzeń sieciowych](http://technet.microsoft.com/library/hh831498.aspx) zawiera instrukcje dotyczące sposobu konfiguracji systemu Windows Server 2012 R2 do hostowania usługi rejestracji urządzeń sieciowych.
Serwer usługi NDES musi być przyłączony do domeny hostującej urząd certyfikacji i nie może znajdować się na tym samym serwerze co ten urząd. Więcej informacji na temat wdrażania serwera usługi NDES w oddzielnym lesie, sieci izolowanej lub domenie wewnętrznej można znaleźć w temacie [Używanie modułu zasad z usługą rejestracji urządzeń sieciowych](https://technet.microsoft.com/library/dn473016.aspx).

-  **Łącznik certyfikatów usługi Microsoft Intune**: używając witryny Azure Portal, pobierz instalator **łącznika certyfikatów** (**ndesconnectorssetup.exe**). Następnie możesz uruchomić plik **ndesconnectorssetup.exe** na komputerze, na którym chcesz zainstalować łącznik certyfikatów. 
-  **Serwer proxy aplikacji sieci Web** (opcjonalnie): jako serwera proxy aplikacji sieci Web (WAP) użyj serwera z systemem Windows Server 2012 R2 lub nowszym. Ta konfiguracja:
    -  Umożliwia urządzeniom otrzymywanie certyfikatów przy użyciu połączenia internetowego.
    -  Jest zalecana ze względów bezpieczeństwa w przypadku używania połączenia internetowego do pobierania i odnawiania certyfikatów przez urządzenia.

 > [!NOTE]           
> -    Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych. Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Ponadto serwer, który hostuje serwer proxy aplikacji sieci Web, musi mieć certyfikat SSL odpowiadający nazwie opublikowanej dla klientów zewnętrznych oraz uznawać certyfikat SSL używany na serwerze usługi NDES za zaufany. Te certyfikaty umożliwiają serwerowi proxy aplikacji sieci Web zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z serwerem usługi NDES.
    Informacje na temat certyfikatów dla serwera proxy aplikacji sieci Web zawiera sekcja **Planowanie certyfikatów** w temacie [Planowanie publikowania aplikacji przy użyciu serwera proxy aplikacji sieci Web](https://technet.microsoft.com/library/dn383650.aspx). Ogólne informacje na temat serwerów proxy aplikacji sieci Web znajdują się w temacie [Praca z serwerem proxy aplikacji sieci Web](http://technet.microsoft.com/library/dn584113.aspx).|

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
|**Konto usługi NDES**|Wskaż konto użytkownika domeny, które będzie używane jako konto usługi NDES.|

## <a name="configure-your-infrastructure"></a>Konfigurowanie infrastruktury
Skonfigurowanie profilów certyfikatów będzie możliwe po wykonaniu poniższych zadań wymagających znajomości systemu Windows Serwer 2012 R2 oraz usług certyfikatów Active Directory (ADCS):

**Krok 1**: Tworzenie konta usługi NDES

**Krok 2**: Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji

**Krok 3**: Konfigurowanie wymagań wstępnych na serwerze usługi NDES

**Krok 4**: Konfigurowanie usługi NDES do użycia z usługą Intune

**Krok 5**: Włączanie, instalowanie i konfigurowanie łącznika certyfikatów usługi Intune

#### <a name="step-1---create-an-ndes-service-account"></a>Krok 1 — Tworzenie konta usługi NDES

Utwórz konto użytkownika domeny, które będzie używane jako konto usługi NDES. To konto należy wskazać podczas konfiguracji szablonów w urzędzie wystawiającym certyfikaty przed instalacją i konfiguracją usługi NDES. Upewnij się, że użytkownik ma uprawnienia domyślne, **Logowanie lokalnie**, **Logowanie jako usługa** i **Logowanie w trybie wsadowym**. Niektóre organizacje mają zaostrzone zasady wykluczające te uprawnienia.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Krok 2 — Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji
To zadanie obejmuje:

-   Konfigurowanie szablonu certyfikatu dla usługi NDES

-   Publikowanie szablonu certyfikatu dla usługi NDES

##### <a name="to-configure-the-certification-authority"></a>Aby skonfigurować urząd certyfikacji

1.  Zaloguj się jako administrator przedsiębiorstwa.

2.  Za pomocą przystawki Szablony certyfikatów dla wystawiającego urzędu certyfikacji utwórz nowy szablon niestandardowy lub skopiuj istniejący szablon, a następnie edytuj go (na przykład szablon użytkownika), aby używać go w usłudze NDES.

    >[!NOTE]
    > Szablon certyfikatu usługi NDES musi być oparty na szablonie certyfikatu w wersji 2 (z obsługą systemu Windows 2003).

    Szablon wymaga następującej konfiguracji:

    -   Określ przyjazną **nazwę wyświetlaną szablonu** .

    -   Na karcie **Nazwa podmiotu** zaznacz opcję **Dostarcz w żądaniu**. (Zabezpieczenia są wymuszane przez moduł zasad usługi Intune dla usługi NDES).

    -   Na karcie **Rozszerzenia** upewnij się, że **Opis zasad aplikacji** obejmuje pozycję **Uwierzytelnianie klienta**.

        > [!IMPORTANT]
        > W przypadku szablonów certyfikatów dla systemu iOS i macOS na karcie **Rozszerzenia** edytuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

    -   Na karcie **Zabezpieczenia** dodaj konto usługi NDES i przypisz do niego uprawnienia **Rejestracja** dla szablonu. Administratorzy usługi Intune, którzy tworzą profile SCEP, muszą mieć prawa **Odczyt**, aby mogli przechodzić do szablonu podczas tworzenia profilów SCEP.

    > [!NOTE]
    > Aby można było odwołać certyfikaty, konto usługi NDES musi mieć prawa *Wystawianie certyfikatów i zarządzanie nimi* do każdego szablonu certyfikatu używanego przez profil certyfikatu.

3.  Sprawdź **Okres ważności** na karcie **Ogólne** szablonu. Domyślnie usługa Intune używa wartości skonfigurowanej w szablonie. Można jednak skonfigurować urząd certyfikacji tak, aby umożliwiał żądającemu określenie innej wartości, którą można następnie ustawić przy użyciu konsoli administratora w usłudze Intune. Jeśli chcesz, aby zawsze była używana wartość określona w szablonie, pomiń pozostałe czynności w tym kroku.

    > [!IMPORTANT]
    > W przypadku platform iOS i macOS wartość ustawiona w szablonie jest używana zawsze, niezależnie od innych ustawień.

Oto zrzuty ekranu przykładowej konfiguracji szablonów.

![Szablon, karta obsługi żądań](.\media\scep_ndes_request_handling.png)

![Szablon, karta nazwy podmiotu](.\media\scep_ndes_subject_name.jpg)

![Szablon, karta zabezpieczeń](.\media\scep_ndes_security.jpg)

![Szablon, karta rozszerzeń](.\media\scep_ndes_extensions.jpg)

![Szablon, karta wymagań wystawiania](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > W przypadku zasad aplikacji należy dodać tylko wymagane zasady aplikacji. Należy uzgodnić wybrane opcje z administratorami zabezpieczeń.



W celu skonfigurowania urzędu certyfikacji tak, aby umożliwiał żądającemu określenie okresu ważności:

1. Uruchom w urzędzie certyfikacji następujące polecenia:
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Użyj przystawki Urząd certyfikacji dla wystawiającego urzędu certyfikacji, aby opublikować szablon certyfikatu.
    Zaznacz węzeł **Szablony certyfikatów**, kliknij pozycję **Akcja**-&gt; **Nowy** &gt; **Szablon certyfikatu do wystawienia**, a następnie wybierz szablon utworzony w kroku 2.
3. Sprawdź, czy certyfikat został opublikowany, wyświetlając go w folderze **Szablony certyfikatów** .


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Krok 3 — Konfigurowanie wymagań wstępnych na serwerze usługi NDES
To zadanie obejmuje:

-   Dodawanie usługi NDES do systemu Windows Serwer oraz konfigurowanie usługi IIS do obsługi usługi NDES

-   Dodawanie konta usługi NDES do grupy IIS_IUSR

-   Ustawianie nazwy SPN dla konta usługi NDES




   1.  Na serwerze, na którym uruchomiona jest usługa NDES, zaloguj się jako **Administrator przedsiębiorstwa**, a następnie użyj [Kreatora dodawanie ról i funkcji](https://technet.microsoft.com/library/hh831809.aspx) w celu instalacji usługi NDES:

    1.  W kreatorze wybierz pozycję **Usługi certyfikatów Active Directory**, aby uzyskać dostęp do usług ról ADCS. Zaznacz pozycję **Usługa rejestracji urządzeń sieciowych**, wyczyść pole wyboru **Urząd certyfikacji**, a następnie zakończ pracę kreatora.

        > [!TIP]
        > Na stronie kreatora **Postęp instalacji** nie klikaj pozycji **Zamknij**. Zamiast tego kliknij link **Skonfiguruj usługi certyfikatów w usłudze Active Directory na serwerze docelowym**. Spowoduje to otwarcie kreatora **Konfiguracja usług AD CS**, przy użyciu którego wykonasz następne zadanie. Po otwarciu kreatora Konfiguracja usług AD CS można zamknąć kreatora Dodaj role i funkcje.

    2.  Po dodaniu usługi NDES do serwera kreator przeprowadzi również instalację usług IIS. Upewnij się, że usługi IIS są skonfigurowane w następujący sposób:

        -   **Serwer sieci Web** &gt; **Zabezpieczenia** &gt; **Filtrowanie żądań**

        -   **Serwer sieci Web** &gt; **Projektowanie aplikacji** &gt; **ASP.NET 3.5**. Podczas instalacji programu ASP .NET 3.5 zostanie zainstalowany program .NET Framework 3.5. Podczas instalacji programu .NET Framework 3.5 należy zainstalować zarówno podstawowy składnik **.NET Framework 3.5**, jak i składnik **Aktywacja HTTP**.

        -   **Serwer sieci Web** &gt; **Projektowanie aplikacji** &gt; **ASP.NET 4.5**. Podczas instalacji programu ASP .NET 4.5 zostanie zainstalowany program .NET Framework 4.5. Podczas instalacji programu .NET Framework 4.5 należy zainstalować podstawową funkcję **.NET Framework 4.5**, **ASP.NET 4.5** oraz funkcję **Usługi WCF** &gt; **Aktywacja HTTP**.

        -   **Narzędzia do zarządzania** &gt; **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** &gt; **Zgodność z metabazą usług IIS 6**

        -   **Narzędzia do zarządzania** &gt; **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** &gt; **Zgodność z narzędziami WMI usług IIS w wersji 6**

  2.  Na serwerze dodaj konto usługi NDES jako element członkowski grupy **IIS_IUSR**.

   3.  Aby ustawić nazwę SPN konta usługi NDES, w oknie wiersza polecenia z podwyższonym poziomem uprawnień uruchom następujące polecenie:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Na przykład jeśli serwer usługi NDES nosi nazwę **Serwer01**, Twoja domena to **Contoso.com**, a konto usługi to **UslugaNDES**, użyj następującego polecenia:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Krok 4 — Konfigurowanie usługi NDES do użycia z usługą Intune
To zadanie obejmuje:

-   Konfigurowanie usługi NDES do użycia z urzędem wystawiającym certyfikaty

-   Powiązanie certyfikatu uwierzytelniania serwera (SSL) w usługach IIS

-   Konfigurowanie filtrowania żądań w usługach IIS


1.  Na serwerze NDES otwórz kreatora Konfiguracja usług AD CS, a następnie wprowadź następujące ustawienia:

    > [!TIP]
    > Jeśli w poprzednim zadaniu kliknięto odpowiedni link, kreator jest już otwarty. W przeciwnym przypadku otwórz Menedżera serwera, aby przejść do konfiguracji powdrożeniowej usług certyfikatów Active Directory.

    -   Na stronie **Usługi ról** wybierz pozycję **Usługa rejestracji urządzeń sieciowych**.

    -   Na stronie **Konto usługi dla usługi rejestracji urządzeń sieciowych** określ konto usługi NDES.

    -   Na stronie **Urząd certyfikacji dla usługi rejestrowania urządzeń sieciowych** kliknij pozycję **Wybierz**, a następnie wybierz urząd wystawiający certyfikaty, dla którego skonfigurowano szablon certyfikatu.

    -   Na stronie **Kryptografia dla usługi rejestracji urządzeń sieciowych** ustaw długość klucza zgodnie z wymaganiami firmy.

    Na stronie **Potwierdzenie** kliknij pozycję **Konfiguruj**, aby zakończyć pracę kreatora.

2.  Po zakończeniu pracy kreatora edytuj następujący klucz rejestru na serwerze usługi NDES:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Aby edytować ten klucz, określ **przeznaczenie** szablonu certyfikatu znajdujące się na karcie **Obsługiwanie żądań**, a następnie zmodyfikuj odpowiadający mu wpis w rejestrze, zamieniając istniejące dane na nazwę szablonu certyfikatu określoną w ramach zadania 1 (nie nazwę wyświetlaną szablonu). Poniższa tabela zawiera mapowanie celów szablonu certyfikatu na wartości rejestru:

    |Cel szablonu certyfikatu (na karcie Obsługiwanie żądań)|Wartość rejestru do edycji|Wartość wyświetlona w konsoli administratora usługi Intune dla profilu SCEP|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Podpis|SignatureTemplate|Podpis cyfrowy|
    |Szyfrowanie|EncryptionTemplate|Szyfrowanie klucza|
    |Podpis i szyfrowanie|GeneralPurposeTemplate|Szyfrowanie klucza<br /><br />Podpis cyfrowy|
    Na przykład jeśli Cel szablonu certyfikatu to **Szyfrowanie**, należy edytować wartość **EncryptionTemplate** i wprowadzić nazwę szablonu certyfikatu.

3. Serwer usługi NDES odbiera bardzo długie adresy URL (zapytania), co wymaga dodania dwóch wpisów rejestru:

    |Lokalizacja|Wartość|Typ|Dane|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (dziesiętnie)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (dziesiętnie)|


4. W Menedżerze usług IIS wybierz pozycję **Domyślna witryna sieci Web** -> **Filtrowanie żądań** -> **Edytuj ustawienia funkcji**, a następnie zmień wartości **Maksymalna długość adresu URL** i **Maksymalna długość ciągu zapytania** na *65534* w przedstawiony sposób.

    ![Maksymalna długość adresu URL i zapytania w programie IIS](.\media\SCEP_IIS_max_URL.png)

5.  Uruchom ponownie serwer. Aby sfinalizować te zmiany, nie wystarczy uruchomić polecenie **iisreset** na serwerze.
6. Przejdź do lokalizacji http://*nazwa_FQDN*/certsrv/mscep/mscep.dll. Powinna zostać wyświetlona strona usługi NDES podobna do następującej:

    ![Testowanie usługi NDES](.\media\SCEP_NDES_URL.png)

    Jeśli zostanie zwrócony komunikat **503 Usługa niedostępna**, sprawdź informacje w Podglądzie zdarzeń. Istnieje prawdopodobieństwo, że pula aplikacji jest zatrzymana z powodu braku prawa dla użytkownika usługi NDES. Te prawa opisano w zadaniu 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Aby zainstalować i powiązać certyfikaty na serwerze usługi NDES

1.  Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania serwera** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Następnie powiąż ten certyfikat SSL w usługach IIS.

    > [!TIP]
    > Po powiązaniu certyfikatu SSL w usługach IIS zainstaluj certyfikat uwierzytelniania klienta. Ten certyfikat może zostać wystawiony przez dowolny urząd certyfikacji traktowany jako zaufany przez serwer usługi NDES. Chociaż nie jest to zalecane, możesz użyć tego samego certyfikatu do uwierzytelniania serwera i klienta, o ile dany certyfikat ma obie wartości ulepszonego użycia klucza (EKU). Poniższe kroki zawierają informacje na temat tych certyfikatów uwierzytelniania.

    1.  Po uzyskaniu certyfikatu uwierzytelniania serwera otwórz **Menedżera usług IIS**, kliknij pozycję **Domyślna witryna sieci Web** w okienku **Połączenia**, a następnie kliknij pozycję **Powiązania** w okienku **Akcje** .

    2.  Kliknij pozycję **Dodaj**, ustaw wartość **https** w polu **Typ**i upewnij się, że ustawiony port to **443**. (W przypadku autonomicznej usługi Intune jest obsługiwany wyłącznie port 443).

    3.  W polu **Certyfikat SSL**określ certyfikat uwierzytelniania serwera.

        > [!NOTE]
        > Jeśli serwer NDES używa zarówno nazwy zewnętrznej, jak i wewnętrznej dla jednego adresu sieciowego, **Nazwa podmiotu** dla certyfikatu uwierzytelniania serwera musi zawierać zewnętrzną nazwę serwera publicznego, a **Alternatywna nazwa podmiotu** musi zawierać wewnętrzną nazwę serwera.

2.  Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania klienta** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Może to być ten sam certyfikat, którego użyto jako certyfikatu uwierzytelniania serwera, o ile ma on obie funkcje.

    Certyfikat uwierzytelniania klienta musi mieć następujące właściwości:

    **Ulepszone użycie klucza** — musi zawierać wartość **Uwierzytelnianie klienta**.

    **Nazwa podmiotu** — musi być taka sama jak nazwa DNS serwera, na którym jest instalowany certyfikat (serwer usługi NDES).

##### <a name="to-configure-iis-request-filtering"></a>Aby skonfigurować filtrowanie żądań w usługach IIS

1.  Na serwerze NDES otwórz **Menedżera usług IIS**, kliknij pozycję **Domyślna witryna sieci Web** w okienku **Połączenia**, a następnie otwórz **Filtrowanie żądań**.

2.  Kliknij pozycję **Edytuj ustawienia funkcji**, a następnie wprowadź następujące wartości:

    **Długość ciągu zapytania (w bajtach)** = **65534**

    **Maksymalna długość adresu URL (w bajtach)** = **65534**

3.  Sprawdź następujący klucz rejestru:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Upewnij się, że następujące wartości są ustawione jako wpisy typu DWORD:

    Nazwa: **MaxFieldLength**o wartości dziesiętnej **65534**

    Nazwa: **MaxRequestBytes**o wartości dziesiętnej **65534**

4. Uruchom ponownie serwer usługi NDES. Teraz serwer jest gotowy do obsługi łącznika certyfikatów.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Krok 5 — Włączanie, instalowanie i konfigurowanie łącznika certyfikatów usługi Intune
To zadanie obejmuje:

- Włączanie obsługi usługi NDES w usłudze Intune.
- Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów na serwerze w danym środowisku. Aby zapewnić wysoką dostępność, możesz zainstalować wiele wystąpień łącznika certyfikatów na różnych serwerach.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Aby pobrać, zainstalować i skonfigurować łącznik certyfikatów
![ConnectorDownload](./media/certificates-download-connector.png)   
 
1. Zaloguj się do portalu Azure Portal. 
2. Wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguracja urządzenia**.
4. W bloku **Konfiguracja urządzenia** wybierz pozycję **Urząd certyfikacji**.
5. Kliknij przycisk **Dodaj**, a następnie wybierz pozycję **Pobierz plik łącznika**. Zapisz pobraną zawartość w lokalizacji dostępnej z serwera, na którym zostanie ona zainstalowana. 
6.  Po zakończeniu pobierania uruchom pobranego instalatora (**ndesconnectorssetup.exe**) na serwerze z systemem Windows Server 2012 R2. Instalator zainstaluje też moduł zasad dla usługi NDES i usługę sieci Web CRP. (Usługa sieci Web CRP, CertificateRegistrationSvc, jest uruchamiana jako aplikacja w usługach IIS.)

    > [!NOTE]
    > Podczas instalacji usługi NDES dla autonomicznej usługi Intune usługa CRP jest instalowana automatycznie wraz z łącznikiem certyfikatów. W przypadku używania usługi Intune z programem Configuration Manager punkt rejestracji certyfikatu (CRP) jest instalowany jako osobna rola systemu lokacji.

3.  Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, kliknij pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany na serwerze usługi NDES w ramach Zadania 3.

    Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune** . Chociaż wybrany certyfikat nie jest wyświetlany, kliknij przycisk **Dalej**, aby wyświetlić właściwości certyfikatu. Kliknij przycisk **Dalej**, a następnie kliknij przycisk **Zainstaluj**.

4.  Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

    > [!TIP]
    > Jeśli kreator zostanie zamknięty przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz uruchomić go za pomocą następującego polecenia:
    >
    > **&lt;ścieżka_instalacji&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  W interfejsie użytkownika **łącznika certyfikatów** :

    Kliknij pozycję **Zaloguj** i wprowadź swoje poświadczenia administratora usługi Intune lub poświadczenia administratora dzierżawy z uprawnieniami administratora globalnego.

    > [!IMPORTANT]
    > Konto użytkownika musi mieć przypisaną prawidłową licencję usługi Intune. Jeśli konto użytkownika nie ma prawidłowej licencji usługi Intune, działanie pliku NDESConnectorUI.exe zakończy się niepowodzeniem.

    Jeśli Twoja organizacja korzysta z serwera proxy i jest on wymagany do połączenia serwera usługi NDES z Internetem, kliknij pozycję **Użyj serwera proxy**, a następnie wprowadź nazwę serwera proxy, port oraz poświadczenia konta, aby nawiązać połączenie.

    Wybierz kartę **Zaawansowane**, wprowadź poświadczenia konta, do którego przypisano uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** w urzędzie wystawiającym certyfikaty, a następnie kliknij pozycję **Zastosuj**.

    Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.

6.  Otwórz wiersz polecenia, wpisz **services.msc**, a następnie naciśnij klawisz **Enter**, kliknij prawym przyciskiem myszy pozycję **Usługa łącznika usługi Intune** i kliknij polecenie **Uruchom ponownie**.

Aby sprawdzić, czy usługa jest uruchomiona, otwórz przeglądarkę i wprowadź następujący adres URL, co powinno spowodować zwrócenie błędu **403** :

**http://&lt;nazwa_FQDN_serwera_usługi_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>Tworzenie profilu certyfikatu protokołu SCEP

1. W witrynie Azure Portal wybierz obciążenie **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu certyfikatu protokołu SCEP.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego certyfikatu protokołu SCEP. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat SCEP**.
7. W bloku **Certyfikat SCEP** skonfiguruj następujące ustawienia:
    - **Okres ważności certyfikatu** — jeśli dla urzędu wystawiającego certyfikaty uruchomiono polecenie **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**, które dopuszcza niestandardowy okres ważności, możesz określić czas pozostały do wygaśnięcia certyfikatu.<br>Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty. 
    - **Dostawca magazynu kluczy (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) — określ miejsce przechowywania klucza certyfikatu. Można wybrać jedną z następujących opcji:
        - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie u dostawcy magazynu kluczy oprogramowania**
        - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie niepowodzenie**
        - **Zarejestruj w usłudze Passport, w przeciwnym razie niepowodzenie (system Windows 10 i nowsze)**
        - **Zarejestruj u dostawcy magazynu kluczy oprogramowania**
    - **Format nazwy podmiotu** — wybierz z listy sposób automatycznego tworzenia przez usługę Intune nazwy podmiotu w żądaniu certyfikatu. Jeśli certyfikat przeznaczony jest dla użytkownika, możesz również uwzględnić w nazwie podmiotu adres e-mail tego użytkownika. Wybierz spośród opcji:
        - **Nieskonfigurowany**
        - **Nazwa pospolita**
        - **Nazwa pospolita obejmująca adres e-mail**
        - **Nazwa pospolita jako adres e-mail**
        - **Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI)**
        - **Numer seryjny**
        - **Niestandardowy** — po wybraniu tej opcji wyświetlane jest inne pole listy rozwijanej. To pole służy do wprowadzania niestandardowego formatu nazwy podmiotu. Obsługiwane są dwie zmienne dla formatu niestandardowego: **Nazwa pospolita (CN)** i **Adres e-mail (E)**. Przy użyciu kombinacji co najmniej jednej z tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki: **CN={{NazwaUżytkownika}},E={{AdresEmail}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**. W tym przykładzie utworzono format nazwy podmiotu, w którym oprócz zmiennych CN i E użyto ciągów zmiennych Organizational Unit (Jednostka organizacyjna), Organization (Organizacja), Location (Lokalizacja), State (Stan) i Country (Kraj). [W tym temacie](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) omówiono funkcję **CertStrToName** i obsługiwane przez nią ciągi.
        
    - **Nazwa alternatywna podmiotu** — wybierz z listy sposób automatycznego tworzenia przez usługę Intune wartości nazwy alternatywnej podmiotu w żądaniu certyfikatu. Jeśli na przykład jako typ certyfikatu został wybrany typ użytkownika, w alternatywnej nazwie podmiotu można uwzględnić główną nazwę użytkownika (nazwę UPN). Jeśli certyfikat klienta jest używany do uwierzytelniania go wobec serwera zasad sieciowych, dla alternatywnej nazwy podmiotu musisz ustawić nazwę UPN. 
    - **Użycie klucza** — określ opcje użycia klucza certyfikatu. Można wybrać następujące opcje: 
        - **Szyfrowanie klucza** — zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest zaszyfrowany. 
        - **Podpis cyfrowy** — zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest chroniony przy użyciu podpisu cyfrowego. 
    - **Rozmiar klucza (bity)** —wybierz liczbę bitów zawartych w kluczu. 
    - **Algorytm skrótu** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) — wybierz jeden z dostępnych typów algorytmu wyznaczania wartości skrótu do użycia z tym certyfikatem. Wybierz najwyższy poziom zabezpieczeń obsługiwany przez podłączane urządzenia. 
    - **Certyfikat główny** — wybierz profil certyfikatu głównego urzędu certyfikacji, który został uprzednio skonfigurowany i przypisany do użytkownika lub urządzenia. Ten certyfikat urzędu certyfikacji musi być certyfikatem głównym urzędu certyfikacji wystawiającego certyfikat skonfigurowany w ramach danego profilu certyfikatu. 
    - **Rozszerzone użycie klucza** — wybierz pozycję **Dodaj**, aby dodać wartości w zależności od celu certyfikatu. W większości przypadków jest wymagane wprowadzenie wartości **Uwierzytelnianie klienta** dla certyfikatu, aby zapewnić użytkownikom lub urządzeniom możliwość uwierzytelnienia na serwerze. Można jednak dodać również inne użycia klucza, zgodnie z potrzebami. 
    - **Ustawienia rejestracji**
        - **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
        - **Adresy URL serwerów SCEP** — określ co najmniej jeden adres URL dla serwerów usługi NDES, które wystawiają certyfikaty za pośrednictwem protokołu SCEP. 
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="how-to-assign-the-certificate-profile"></a>Przypisywanie profilu certyfikatu

Przed przypisaniem profilów certyfikatów do grup należy wziąć pod uwagę następujące kwestie:

- Podczas przypisywania profilów certyfikatów do grup na urządzeniu jest instalowany plik certyfikatu z profilu certyfikatu zaufanego urzędu certyfikacji. Profil certyfikatu protokołu SCEP jest wykorzystywany przez to urządzenie do tworzenia żądania certyfikatu.
- Profile certyfikatów mogą być instalowane wyłącznie na urządzeniach z platformą użytą podczas tworzenia profilu.
- Profile certyfikatów można również przypisywać do kolekcji użytkowników lub kolekcji urządzeń.
- Aby opublikować certyfikat dla urządzenia jak najszybciej po jego rejestracji, należy przypisać profil certyfikatu do grupy użytkowników, a nie do grupy urządzeń. W przypadku przypisania do grupy urządzeń wymagana jest pełna rejestracja urządzenia przed otrzymaniem przez nie zasad.
- Mimo że każdy profil należy przypisać osobno, konieczne jest również przypisanie profilu zaufanego certyfikatu głównego urzędu certyfikacji oraz profilu protokołu SCEP lub PKCS. W przeciwnym razie zasady certyfikatu protokołu SCEP lub PKCS nie będą działać.

Informacje dotyczące sposobu przypisywania profilów znajdują się w temacie [Jak przypisywać profile urządzeń](device-profile-assign.md).

