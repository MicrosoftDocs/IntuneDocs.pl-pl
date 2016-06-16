---
# required metadata

title: Konfigurowanie infrastruktury certyfikatu | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurowanie infrastruktury certyfikatu
W tym temacie opisano elementy potrzebne do utworzenia i wdrożenia profilów certyfikatów.

Aby przeprowadzać uwierzytelnianie oparte na certyfikatach w organizacji, należy zastosować urząd certyfikacji przedsiębiorstwa.

Do korzystania z profilów certyfikatu SCEP w połączeniu z urzędem certyfikacji przedsiębiorstwa są wymagane również następujące elementy:

-   Serwer z uruchomioną usługą rejestracji urządzeń sieciowych (NDES)

-   Łącznik certyfikatów usługi Intune instalowany na serwerze z systemem Windows Server 2012 R2, na którym jest uruchamiana usługa NDES

Do korzystania z profilów certyfikatu PFX w połączeniu z urzędem certyfikacji przedsiębiorstwa są wymagane również następujące elementy:

-  Komputer, który może komunikować się z urzędem certyfikacji, lub komputer urzędu certyfikacji.

-  Łącznik certyfikatów usługi Intune uruchamiany na komputerze, który może komunikować się z urzędem certyfikacji.

## Infrastruktura lokalna


-    **Domena usługi Active Directory:** wszystkie serwery wymienione w tej części (z wyjątkiem serwera proxy aplikacji sieci Web) muszą należeć do Twojej domeny usługi Active Directory.

-  **Urząd certyfikacji (CA):** wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. Instrukcje dotyczące sposobu konfigurowania urzędu certyfikacji znajdują się w temacie [Instalacja urzędu certyfikacji](http://technet.microsoft.com/library/jj125375.aspx).
    Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2, należy najpierw [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Serwer NDES** (tylko SCEP): na serwerze z systemem Windows Server 2012 R2 lub nowszym należy skonfigurować usługę rejestracji urządzeń sieciowych (NDES). Usługa Intune nie obsługuje usługi NDES uruchomionej na tym samym serwerze, na którym jest uruchomiony urząd certyfikacji przedsiębiorstwa. Temat [Wskazówki dotyczące usługi rejestracji urządzeń sieciowych](http://technet.microsoft.com/library/hh831498.aspx) zawiera instrukcje dotyczące sposobu konfiguracji systemu Windows Server 2012 R2 do obsługi usługi rejestracji urządzeń sieciowych.|
-  **Komputer, który może komunikować się z urzędem certyfikacji** (tylko PFX): alternatywnie można użyć komputera urzędu certyfikacji.
-  **Łącznik certyfikatów usługi Microsoft Intune**: używając konsoli administracyjnej usługi Intune, możesz pobrać instalatora **łącznika certyfikatów** (**ndesconnectorssetup.exe**). Następnie możesz uruchomić plik **ndesconnectorssetup.exe** na komputerze, na którym chcesz zainstalować łącznik certyfikatów. W przypadku profilów certyfikatów PFX zainstaluj łącznik certyfikatów na komputerze, który komunikuje się z urzędem certyfikacji.
-  **Serwer proxy aplikacji sieci Web** (opcjonalnie): serwer z systemem Windows Server 2012 R2 lub nowszym może zostać użyty jako serwer proxy aplikacji sieci Web (WAP). Ta konfiguracja:
    -  Umożliwia urządzeniom otrzymywanie certyfikatów przy użyciu połączenia internetowego.
    -  Jest zalecana ze względów bezpieczeństwa w przypadku używania połączenia internetowego do pobierania i odnawiania certyfikatów przez urządzenia.

> [!NOTE]           
> -    Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych. Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Ponadto serwer, który jest hostem serwera WAP, musi mieć certyfikat SSL odpowiadający nazwie opublikowanej do zewnętrznych klientów oraz uznawać certyfikat SSL używany na serwerze usługi NDES za zaufany. Te certyfikaty umożliwiają serwerowi proxy aplikacji sieci Web zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z serwerem usługi NDES.
Informacje na temat certyfikatów wymaganych przez serwer proxy aplikacji sieci Web zawiera sekcja **Planowanie certyfikatów** w temacie [Planowanie publikowania aplikacji przy użyciu serwera proxy aplikacji sieci Web](https://technet.microsoft.com/library/dn383650.aspx). Ogólne informacje na temat serwerów proxy aplikacji sieci Web znajdują się w temacie [Praca z serwerem proxy aplikacji sieci Web](http://technet.microsoft.com/library/dn584113.aspx).|


### Certyfikaty i szablony

|Obiekt|Szczegóły|
|----------|-----------|
|**Szablon certyfikatu**|Ten szablon należy skonfigurować na serwerze wystawiającego urzędu certyfikacji.|
|**Certyfikat uwierzytelniania klienta**|Żądany od wystawiającego lub publicznego urzędu certyfikacji; instalowany na serwerze usługi NDES.|
|**Certyfikat uwierzytelniania serwera**|Żądany od wystawiającego lub publicznego urzędu certyfikacji; certyfikat SSL instalowany i powiązany w usługach IIS na serwerze usługi NDES.|
|**Certyfikat zaufanego głównego urzędu certyfikacji**|Ten certyfikat należy wyeksportować w pliku w formacie **.cer** z urzędu wystawiającego certyfikaty lub dowolnego urządzenia traktującego urząd wystawiający certyfikaty jako zaufany, a następnie wdrożyć go na urządzeniach, korzystając z profilu certyfikatu zaufanego urzędu certyfikacji.<br /><br />Należy użyć jednego certyfikatu zaufanego głównego urzędu certyfikacji dla każdej platformy systemu operacyjnego i powiązać te certyfikaty z poszczególnymi utworzonymi profilami zaufanych certyfikatów głównych.<br /><br />W razie potrzeby można użyć dodatkowych certyfikatów zaufanego głównego urzędu certyfikacji. Można na przykład zrobić to, aby urząd certyfikacji podpisujący certyfikaty uwierzytelniania serwera dla punktów dostępowych Wi-Fi był traktowany jako zaufany.|

### Konta

|Nazwa|Szczegóły|
|--------|-----------|
|**Konto usługi NDES**|Należy wskazać konto użytkownika domeny, które będzie używane jako konto usługi NDES.|

## Konfigurowanie infrastruktury
Skonfigurowanie profili certyfikatów będzie możliwe po wykonaniu poniższych zadań wymagających znajomości systemu Windows Serwer 2012 R2 oraz usług certyfikatów Active Directory (ADCS):

**Zadanie 1** — Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji

**Zadanie 2** (tylko w przypadku profilu SCEP) — Konfigurowanie wymagań wstępnych na serwerze NDES

**Zadanie 3** (tylko w przypadku profilu SCEP) — Konfigurowanie usługi NDES do użycia z usługą Intune

**Zadanie 4** — Włączanie, instalacja i konfiguracja łącznika certyfikatów dla usługi Intune

## Zadanie 1 — Konfigurowanie szablonów certyfikatu w urzędzie certyfikacji
To zadanie obejmuje:

-   Tworzenie konta usługi NDES

    > [!NOTE] Aby można było odwołać certyfikaty, konto usługi NDES musi mieć prawa *Wystawianie certyfikatów i zarządzanie nimi* do każdego szablonu certyfikatu używanego przez profil certyfikatu.

-   Konfigurowanie szablonu certyfikatu dla usługi NDES

-   Publikowanie szablonu certyfikatu dla usługi NDES

##### Aby skonfigurować urząd certyfikacji

1.  Utwórz konto użytkownika domeny, które będzie używane jako konto usługi NDES. To konto należy wskazać podczas konfiguracji szablonów w urzędzie wystawiającym certyfikaty przed instalacją i konfiguracją usługi NDES.

2.  Za pomocą przystawki Szablony certyfikatów dla wystawiającego urzędu certyfikacji utwórz nowy szablon niestandardowy lub skopiuj istniejący szablon, a następnie edytuj go (na przykład szablon użytkownika), aby używać go w usłudze NDES.

    Szablon wymaga następującej konfiguracji:

    -   Określ przyjazną **nazwę wyświetlaną szablonu** .

    -   Na karcie **Nazwa podmiotu** zaznacz opcję **Dostarcz w żądaniu**. (Zabezpieczenia są realizowane przez moduł zasad usługi Intune dla usługi NDES).

    -   Na karcie **Rozszerzenia** upewnij się, że **Opis zasad aplikacji** obejmuje pozycję **Uwierzytelnianie klienta**.

        > [!IMPORTANT] W przypadku szablonów certyfikatów dla systemów iOS i Mac OS X na karcie **Rozszerzenia** zmodyfikuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

    -   Na karcie **Zabezpieczenia** dodaj konto usługi NDES i przypisz do niego uprawnienia **Rejestracja** dla szablonu.

3.  Sprawdź **Okres ważności** na karcie **Ogólne** szablonu. Domyślnie usługa Intune korzysta z wartości ustawionej w szablonie. Można jednak skonfigurować urząd certyfikacji tak, aby umożliwiał żądającemu określenie innej wartości, którą można następnie ustawić przy użyciu konsoli administratora w usłudze Intune. Jeśli chcesz, aby zawsze była używana wartość określona w szablonie, pomiń pozostałe czynności w tym kroku.

    > [!IMPORTANT] W przypadku platform iOS i Mac OS X wartość ustawiona w szablonie jest używana zawsze, niezależnie od innych ustawień.

    W celu skonfigurowania urzędu certyfikacji tak, aby umożliwiał żądającemu określenie okresu ważności, uruchom następujące polecenia w urzędzie certyfikacji:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Użyj przystawki Urząd certyfikacji dla wystawiającego urzędu certyfikacji, aby opublikować szablon certyfikatu.

    1.  Zaznacz węzeł **Szablony certyfikatów**, kliknij pozycję **Akcja**-&gt; **Nowy** &gt; **Szablon certyfikatu do wystawienia**, a następnie wybierz szablon utworzony w kroku 2.

    2.  Sprawdź, czy certyfikat został opublikowany, wyświetlając go w folderze **Szablony certyfikatów** .

5.  W przypadku profilów PFX: na komputerze urzędu certyfikacji sprawdź, czy komputer obsługujący łącznik certyfikatów usługi Intune ma uprawnienia do rejestracji, dzięki czemu może uzyskiwać dostęp do szablonu używanego podczas tworzenia profilu PFX. Ustaw to uprawnienie na karcie **Zabezpieczenia** właściwości komputera urzędu certyfikacji.

## Zadanie 2 (tylko w przypadku profilu SCEP) — Konfigurowanie warunków wstępnych na serwerze usługi NDES
To zadanie obejmuje:

-   Dodawanie usługi NDES do systemu Windows Serwer oraz konfigurowanie usługi IIS do obsługi usługi NDES

-   Dodawanie konta usługi NDES do grupy IIS_IUSR

-   Ustawianie nazwy SPN dla konta usługi NDES

##### Aby skonfigurować wymagania wstępne dla serwera usługi NDES

1.  Na serwerze, na którym będzie uruchomiona usługa NDES, należy zalogować się jako **Administrator przedsiębiorstwa**, a następnie użyć [kreatora Dodaj role i funkcje](https://technet.microsoft.com/library/hh831809.aspx) w celu instalacji usługi NDES:

    1.  W kreatorze wybierz pozycję **Usługi certyfikatów Active Directory** , aby uzyskać dostęp do usług ról ADCS. Zaznacz pozycję **Usługa rejestracji urządzeń sieciowych**, wyczyść pole wyboru **Urząd certyfikacji**, a następnie zakończ pracę kreatora.

        > [!TIP]
        > Na stronie kreatora **Postęp instalacji** nie klikaj pozycji **Zamknij**. Zamiast tego kliknij link **Skonfiguruj usługi certyfikatów w usłudze Active Directory na serwerze docelowym**. Spowoduje to otwarcie kreatora **Konfiguracja usług AD CS** , przy użyciu którego wykonasz następne zadanie. Po otwarciu kreatora Konfiguracja usług AD CS można zamknąć kreatora Dodaj role i funkcje.

    2.  Po dodaniu usługi NDES do serwera kreator przeprowadzi również instalację usług IIS. Upewnij się, że usługi IIS są skonfigurowane w następujący sposób:

        -   **Serwer sieci Web** &gt; **Zabezpieczenia** &gt; **Filtrowanie żądań**

        -   **Serwer sieci Web** &gt; **Projektowanie aplikacji** &gt; **ASP.NET 3.5**. Podczas instalacji programu ASP .NET 3.5 zostanie zainstalowany program .NET Framework 3.5. Podczas instalacji programu .NET Framework 3.5 należy zainstalować zarówno podstawowy składnik **.NET Framework 3.5** , jak i składnik **Aktywacja HTTP**.

        -   **Serwer sieci Web** &gt; **Projektowanie aplikacji** &gt; **ASP.NET 4.5**. Podczas instalacji programu ASP .NET 4.5 zostanie zainstalowany program .NET Framework 4.5. Podczas instalacji programu .NET Framework 4.5 należy zainstalować podstawową funkcję **.NET Framework 4.5**, **ASP.NET 4.5** oraz funkcję **Usługi WCF** &gt; **Aktywacja HTTP**.

        -   **Narzędzia do zarządzania** &gt; **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** &gt; **Zgodność z metabazą usług IIS 6**

        -   **Narzędzia do zarządzania** &gt; **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** &gt; **Zgodność z narzędziami WMI usług IIS w wersji 6**

2.  Na serwerze dodaj konto usługi NDES jako członka grupy **IIS_IUSR**.

3.  Aby ustawić nazwę SPN konta usługi NDES, uruchom następujące polecenie:

    -   **setspn -s http/&lt;Nazwa DNS serwera usługi NDES&gt; &lt;Nazwa domeny&gt;\&lt;Nazwa konta usługi NDES&gt;**

    Na przykład jeśli serwer usługi NDES nosi nazwę **Serwer01**, Twoja domena to **Contoso.com**, a konto usługi to **UslugaNDES**, użyj następującego polecenia:

    -   **setspn –s http/Serwer01.contoso.com contoso\UslugaNDES**

## Zadanie 3 (tylko w przypadku profilu SCEP) — Konfigurowanie usługi NDES do użycia z usługą Microsoft Intune 
To zadanie obejmuje:

-   Konfigurowanie usługi NDES do użycia z urzędem wystawiającym certyfikaty

-   Powiązanie certyfikatu uwierzytelniania serwera (SSL) w usługach IIS

-   Konfigurowanie filtrowania żądań w usługach IIS

##### Aby skonfigurować usługę NDES do użycia z usługą Intune

1.  Na serwerze NDES otwórz kreatora Konfiguracja usług AD CS, a następnie wprowadź następujące ustawienia.

    > [!TIP]
    > Jeśli w poprzednim zadaniu kliknięto odpowiedni link, kreator jest już otwarty. W przeciwnym przypadku otwórz Menedżera serwera, aby przejść do konfiguracji powdrożeniowej usług certyfikatów Active Directory.

    -   Na stronie **Usługi ról** wybierz pozycję **Usługa rejestracji urządzeń sieciowych**.

    -   Na stronie **Konto usługi dla usługi rejestracji urządzeń sieciowych** określ konto usługi NDES.

    -   Na stronie **Urząd certyfikacji dla usługi rejestrowania urządzeń sieciowych** kliknij pozycję **Wybierz**, a następnie wybierz urząd wystawiający certyfikaty, dla którego skonfigurowano szablon certyfikatu.

    -   Na stronie **Kryptografia dla usługi rejestracji urządzeń sieciowych** ustaw długość klucza zgodnie z wymaganiami firmy.

    Na stronie **Potwierdzenie** kliknij pozycję **Konfiguruj** , aby zakończyć pracę kreatora.

2.  Po zakończeniu pracy kreatora edytuj następujący klucz rejestru na serwerze usługi NDES:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Aby edytować ten klucz, określ **przeznaczenie** szablonu certyfikatu znajdujące się na karcie **Obsługiwanie żądań**, a następnie zmodyfikuj odpowiadający mu wpis w rejestrze, zamieniając istniejące dane na nazwę szablonu certyfikatu określoną w ramach zadania 1 (nie nazwę wyświetlaną szablonu). Poniższa tabela zawiera mapowanie celów szablonu certyfikatu na wartości rejestru:

    |Cel szablonu certyfikatu (na karcie Obsługiwanie żądań)|Wartość rejestru do edycji|Wartość wyświetlona w konsoli administratora usługi Intune dla danego profilu protokołu SCEP|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Podpis|SignatureTemplate|Podpis cyfrowy|
    |Szyfrowanie|EncryptionTemplate|Szyfrowanie klucza|
    |Podpis i szyfrowanie|GeneralPurposeTemplate|Szyfrowanie klucza<br /><br />Podpis cyfrowy|
    Na przykład jeśli Cel szablonu certyfikatu to **Szyfrowanie**, należy edytować wartość **EncryptionTemplate** i wprowadzić nazwę szablonu certyfikatu.

3.  Po modyfikacji rejestru uruchom polecenie **iisreset** na serwerze, aby wymusić wykrycie ostatnich zmian konfiguracji.

##### Aby zainstalować i powiązać certyfikaty na serwerze usługi NDES

1.  Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania serwera** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Następnie powiąż ten certyfikat SSL w usługach IIS.

    > [!TIP]
    > Po powiązaniu certyfikatu SSL w usługach IIS zainstaluj również certyfikat uwierzytelniania klienta. Ten certyfikat może zostać wystawiony przez dowolny urząd certyfikacji traktowany jako zaufany przez serwer usługi NDES. Chociaż nie jest to zalecane, możesz użyć tego samego certyfikatu do uwierzytelniania serwera i klienta, o ile dany certyfikat ma obie wartości ulepszonego użycia klucza (EKU). Poniższe kroki zawierają informacje na temat tych certyfikatów uwierzytelniania.

    1.  Po uzyskaniu certyfikatu uwierzytelniania serwera otwórz **Menedżera usług IIS**, kliknij pozycję **Domyślna witryna sieci Web** w okienku **Połączenia** , a następnie kliknij pozycję **Powiązania** w okienku **Akcje** .

    2.  Kliknij pozycję **Dodaj**, ustaw wartość **https** w polu **Typ**i upewnij się, że ustawiony port to **443**. (W przypadku autonomicznej usługi Intune jest obsługiwany wyłącznie port 443).

    3.  W polu **Certyfikat SSL**określ certyfikat uwierzytelniania serwera.

        > [!NOTE] Jeśli serwer NDES używa zarówno nazwy zewnętrznej, jak i wewnętrznej dla jednego adresu sieciowego, **Nazwa podmiotu** dla certyfikatu uwierzytelniania serwera musi zawierać zewnętrzną nazwę serwera publicznego, a **Alternatywna nazwa podmiotu** musi zawierać wewnętrzną nazwę serwera.

2.  Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania klienta** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat. Może to być ten sam certyfikat, którego użyto jako certyfikatu uwierzytelniania serwera, o ile ma on obie funkcje.

    Certyfikat uwierzytelniania klienta musi mieć następujące właściwości:

    **Ulepszone użycie klucza** — musi zawierać wartość **Uwierzytelnianie klienta**.

    **Nazwa podmiotu** — musi być taka sama jak nazwa DNS serwera, na którym jest instalowany certyfikat (serwer usługi NDES).

##### Aby skonfigurować filtrowanie żądań w usługach IIS

1.  Na serwerze NDES otwórz **Menedżera usług IIS**, kliknij pozycję **Domyślna witryna sieci Web** w okienku **Połączenia** , a następnie otwórz **Filtrowanie żądań**.

2.  Kliknij pozycję **Edytuj ustawienia funkcji**, a następnie wprowadź następujące ustawienia:

    **długość ciągu zapytania (w bajtach)** = **65534**

    **Maksymalna długość adresu URL (w bajtach)** = **65534**

3.  Sprawdź następujący klucz rejestru:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Upewnij się, że następujące wartości są ustawione jako wpisy typu DWORD:

    Nazwa: **MaxFieldLength**o wartości dziesiętnej **65534**

    Nazwa: **MaxRequestBytes**o wartości dziesiętnej **65534**

4.  Uruchom ponownie serwer usługi NDES. Teraz serwer jest gotowy do obsługi łącznika certyfikatów.

## Zadanie 4 — Włączanie, instalowanie i konfigurowanie łącznika certyfikatów usługi Intune (w przypadku certyfikatów SCEP i PFX).
To zadanie obejmuje:

Włączanie obsługi usługi NDES w usłudze Intune

Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów na serwerze usługi NDES

##### Aby włączyć obsługę łącznika certyfikatów

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com) i kliknij pozycję **Administracja** &gt; **Łącznik certyfikatów**.

2.  Kliknij pozycję **Skonfiguruj lokalny łącznik certyfikatów**.

3.  Kliknij pozycję **Włącz łącznik certyfikatów**, a następnie kliknij przycisk **OK**.

##### Aby pobrać, zainstalować i skonfigurować łącznik certyfikatów

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com), a następnie kliknij kolejno pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Łącznik certyfikatów** &gt; **Pobierz łącznik certyfikatów**.

2.  Po zakończeniu uruchom pobrany program instalacyjny (**ndesconnectorssetup.exe**):

    -   W przypadku certyfikatów PFX uruchom instalatora na komputerze, który może połączyć się z urzędem certyfikacji. Wybierz opcję dystrybucji certyfikatu PFX i kliknij pozycję Zainstaluj. Po ukończeniu instalacji utwórz profil certyfikatu zgodnie z opisem w sekcji [Konfigurowanie profilów certyfikatów](configure-intune-certificate-profiles.md).

    -   W przypadku certyfikatów SCEP uruchom instalatora na serwerze Windows Server 2012 R2.

    W przypadku opcji SCEP instalator instaluje również moduł zasad dla usługi NDES oraz usługę sieci Web CRP. (Usługa sieci Web CRP, CertificateRegistrationSvc, jest uruchamiana jako aplikacja w usługach IIS.)

    > [!NOTE]
    > Podczas instalacji usługi NDES dla autonomicznej usługi Intune usługa CRP zostaje zainstalowana automatycznie wraz z łącznikiem certyfikatów. W przypadku korzystania z usługi Intune z programem Configuration Manager punkt rejestracji certyfikatu (CRP) jest instalowany jako osobna rola systemu lokacji.

3.  Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, kliknij pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany na serwerze usługi NDES w ramach Zadania 3.

    Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune** . Chociaż wybrany certyfikat nie jest wyświetlany, kliknij przycisk **Dalej** , aby wyświetlić właściwości certyfikatu. Kliknij przycisk **Dalej**, a następnie kliknij przycisk **Zainstaluj**.

4.  Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

    > [!TIP] Jeśli zamkniesz kreatora przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz otworzyć go ponownie za pomocą następującego polecenia:
    >
    > **&lt;ścieżka_instalacji&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  W interfejsie użytkownika **łącznika certyfikatów** :

    Kliknij pozycję **Zaloguj** i wprowadź swoje poświadczenia administratora usługi Intune lub poświadczenia administratora dzierżawy z uprawnieniami administratora globalnego.

    Jeśli Twoja organizacja korzysta z serwera proxy i jest on wymagany do połączenia serwera usługi NDES z Internetem, kliknij pozycję **Użyj serwera proxy**, a następnie wprowadź nazwę serwera proxy, port oraz poświadczenia konta, aby nawiązać połączenie.

    Wybierz kartę **Zaawansowane** , wprowadź poświadczenia konta, do którego przypisano uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** w urzędzie wystawiającym certyfikaty, a następnie kliknij pozycję **Zastosuj**.

    Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.

6.  Otwórz wiersz polecenia, wpisz **services.msc**, a następnie naciśnij klawisz **Enter**, kliknij prawym przyciskiem myszy pozycję **Usługa łącznika certyfikatów usługi Intune** i kliknij polecenie **Uruchom ponownie**.

Aby sprawdzić, czy usługa jest uruchomiona, otwórz przeglądarkę i wprowadź następujący adres URL, co powinno spowodować zwrócenie błędu **403** :

**http:// &lt;nazwa_FQDN_serwera_usługi_NDES&gt;/certsrv/mscep/mscep.dll**

### Następne kroki
Teraz można skonfigurować profile certyfikatów zgodnie z opisem w sekcji [Konfigurowanie profilów certyfikatów](configure-intune-certificate-profiles.md).


<!--HONumber=Jun16_HO1-->


