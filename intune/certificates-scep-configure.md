---
title: Konfigurowanie infrastruktury do obsługi profilów certyfikatów SCEP przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Aby korzystać z protokołu SCEP w usłudze Microsoft Intune, skonfiguruj lokalną domenę usługi AD, utwórz urząd certyfikacji, skonfiguruj serwer usługi NDES i zainstaluj łącznik certyfikatów usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/28/2019
ms.topic: article
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 76cd6084815a9f63e653a63d36ba8265a7a0fbd6
ms.sourcegitcommit: cf40f641af4746a1e34edd980dc6ec96fd040126
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2019
ms.locfileid: "70122565"
---
# <a name="configure-infrastructure-to-support-scep-with-intune"></a>Konfigurowanie infrastruktury do obsługi protokołu SCEP w usłudze Intune  
  
Usługa Intune obsługuje używanie prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol) do [uwierzytelniania połączeń z aplikacjami i zasobami firmowymi](certificates-configure.md). Protokół SCEP używa certyfikatu urzędu certyfikacji (CA, Certification Authority) w celu zabezpieczenia wymiany komunikatów dla żądania podpisania certyfikatu (CSR, Certificate Signing Request). Jeśli Twoja infrastruktura obsługuje protokół SCEP, możesz wdrażać certyfikaty na urządzeniach za pomocą profilów *certyfikatów SCEP* usługi Intune (typu profilu urządzenia w usłudze Intune). Łącznik certyfikatów usługi Microsoft Intune jest wymagany do korzystania z profilów certyfikatów SCEP w usłudze Intune w przypadku korzystania z urzędu certyfikacji usług certyfikatów Active Directory. Łącznik nie jest wymagany w przypadku korzystania z [urzędów certyfikacji innych firm](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).  

Informacje przedstawione w tym artykule mogą ułatwić skonfigurowanie infrastruktury do obsługi protokołu SCEP w przypadku korzystania z usług certyfikatów Active Directory. Po skonfigurowaniu infrastruktury możesz [tworzyć i wdrażać profile certyfikatów SCEP](certificates-profile-scep.md) za pomocą usługi Intune.  

> [!TIP]  
> Usługa Intune obsługuje także używanie [certyfikatów PKCS #12](certficates-pfx-configure.md).  


## <a name="prerequisites-for-using-scep-for-certificates"></a>Wymagania wstępne dotyczące używania protokołu SCEP dla certyfikatów  
Przed kontynuowaniem upewnij się, że [utworzono i wdrożono profil *certyfikatu zaufanego*](certificates-configure.md#export-the-trusted-root-ca-certificate) na urządzeniach, które będą używać profilów certyfikatów SCEP. Profile certyfikatów SCEP bezpośrednio odwołują się do profilu certyfikatu zaufanego używanego do aprowizacji urządzeń przy użyciu certyfikatu zaufanego głównego urzędu certyfikacji.  

### <a name="servers-and-server-roles"></a>Serwery i role serwerów  
Następująca infrastruktura lokalna musi być uruchomiona na serwerach, które są przyłączone do domeny usługi Active Directory, z wyjątkiem serwera proxy aplikacji internetowej.  
- **Urząd certyfikacji** — użyj urzędu certyfikacji przedsiębiorstwa usług certyfikatów Microsoft Active Directory działającego w systemie Windows Server 2008 R2 z dodatkiem Service Pack 1 lub nowszym w wersji Enterprise. Używana wersja systemu Windows Server musi być obsługiwana przez firmę Microsoft. Autonomiczny urząd certyfikacji nie jest obsługiwany. Aby uzyskać więcej informacji, zobacz [Instalowanie urzędu certyfikacji](http://technet.microsoft.com/library/jj125375.aspx). Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2 SP1, należy [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).  

- **Rola serwera usługi NDES** — należy skonfigurować rolę usługi serwera rejestracji urządzeń sieciowych (NDES) w systemie Windows Server 2012 R2 lub nowszym. W dalszej części tego artykułu poznasz proces [instalowania usługi NDES](#set-up-ndes).  

  - Serwer, który hostuje usługę NDES, musi być przyłączony do domeny i znajdować się w tym samym lesie co urząd certyfikacji przedsiębiorstwa.  
  - Nie można użyć usługi NDES zainstalowanej na serwerze, który hostuje urząd certyfikacji przedsiębiorstwa.  
  - Łącznik certyfikatu usługi Microsoft Intune należy zainstalować na tym samym serwerze, który hostuje usługę NDES.  

  Aby uzyskać więcej informacji o usłudze NDES, zobacz [Wskazówki dotyczące usługi rejestracji urządzeń sieciowych](http://technet.microsoft.com/library/hh831498.aspx) w dokumentacji systemu Windows Server i [Używanie modułu zasad z usługą rejestracji urządzeń sieciowych](https://technet.microsoft.com/library/dn473016.aspx).  

- **Łącznik certyfikatów usługi Microsoft Intune** — jest wymagany do korzystania z profilów certyfikatów SCEP w usłudze Intune. Ten artykuł przeprowadzi Cię przez proces [instalowania tego łącznika](#install-the-intune-certificate-connector).  

  Łącznik obsługuje tryb Federal Information Processing Standard (FIPS). Tryb FIPS nie jest wymagany, ale gdy jest on włączony, umożliwia wystawianie i odwoływanie certyfikatów.  
  - Łącznik musi być uruchomiony na tym samym serwerze co rola serwera usługi NDES, na serwerze z systemem Windows Server 2012 R2 lub nowszym.  
  - Platforma .NET 4.5 jest wymagana przez łącznik i jest automatycznie dołączona do systemu Windows Server 2012 R2.  
  - Konfiguracja zwiększonych zabezpieczeń programu Internet Explorer [musi być wyłączona na serwerze hostującym usługę NDES](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) i w łączniku certyfikatów usługi Microsoft Intune.  

Następująca infrastruktura lokalna jest opcjonalna:  
  Aby zezwolić urządzeniom z Internetu na pobieranie certyfikatów, musisz opublikować adres URL usługi NDES spoza sieci firmowej. Możesz użyć serwera proxy aplikacji usługi Azure AD, serwera proxy aplikacji internetowej lub innego zwrotnego serwera proxy.
  
- **Serwer proxy aplikacji usługi Azure AD** (opcjonalnie) — serwera proxy aplikacji usługi Azure AD możesz używać zamiast dedykowanego serwera proxy aplikacji internetowej (WAP) w celu publikowania adresu URL usługi NDES w Internecie. Dzięki temu certyfikaty mogą uzyskiwać zarówno urządzenia połączone z intranetem, jak i Internetem. Aby uzyskać więcej informacji, zobacz [Zapewnianie bezpiecznego dostępu zdalnego do aplikacji lokalnych](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy). 

- **Serwer proxy aplikacji internetowej** (opcjonalnie) — jako serwera proxy aplikacji internetowej (WAP) użyj serwera z systemem Windows Server 2012 R2 lub nowszym, aby opublikować adres URL usługi NDES w Internecie.  Dzięki temu certyfikaty mogą uzyskiwać zarówno urządzenia połączone z intranetem, jak i Internetem.

  Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych. Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).  

  Serwer WAP musi mieć certyfikat SSL pasujący do nazwy opublikowanej dla klientów zewnętrznych oraz ufać certyfikatowi SSL używanemu na komputerze hostującym usługę NDES. Te certyfikaty umożliwiają serwerowi proxy aplikacji internetowej zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z usługą NDES.  

  Aby uzyskać więcej informacji, zobacz [Plan certificates for WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) (Planowanie certyfikatów protokołu WAP) i [ogólne informacje na temat serwerów WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="accounts"></a>Konta   
- **Konto usługi NDES** — przed rozpoczęciem konfigurowania usługi NDES zidentyfikuj konto użytkownika domeny, które ma być używane jako konto usługi NDES. To konto należy wskazać podczas konfiguracji szablonów w urzędzie wystawiającym certyfikaty przed konfiguracją usługi NDES.  

  To konto musi mieć następujące uprawnienia na serwerze, który hostuje usługę NDES:  
  - **Logowanie lokalne**  
  - **Logowanie jako usługa**  
  - **Logowanie w trybie wsadowym**  

  Aby uzyskać więcej informacji, zobacz [Tworzenie konta użytkownika domeny, które będzie służyć jako konto usługi NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11)#to-create-a-domain-user-account-to-act-as-the-ndes-service-account). 
- **Dostęp do komputera, który jest hostem usługi NDES** — potrzebne będzie konto użytkownika domeny z uprawnieniami do instalowania i konfigurowania ról systemu Windows Server na serwerze, na którym jest zainstalowana usługa NDES.  

- **Dostęp do urzędu certyfikacji** — potrzebne będzie konto użytkownika domeny z uprawnieniami do zarządzania urzędem certyfikacji.  

### <a name="network-requirements"></a>Wymagania dotyczące sieci

Zaleca się opublikowanie usługi NDES za pośrednictwem zwrotnego serwera proxy takiego jak [serwer proxy aplikacji usługi Azure AD, serwer proxy dostępu do Internetu](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/) lub serwer proxy innych firm. Jeśli nie używasz zwrotnego serwera proxy, zezwól na ruch TCP na porcie 443 ze wszystkich hostów i adresów IP w Internecie do usługi NDES.  

Zezwalaj na wszystkie porty i protokoły wymagane do komunikacji pomiędzy usługą NDES a dowolną infrastrukturą pomocniczą w Twoim środowisku. Komputer hostujący usługę NDES musi na przykład komunikować się z urzędem certyfikacji, serwerami DNS, kontrolerami domeny, a potencjalnie także innymi usługami lub serwerami w środowisku, na przykład serwerami programu Configuration Manager.

### <a name="certificates-and-templates"></a>Certyfikaty i szablony

Poniższe certyfikaty i szablony są używane w przypadku korzystania z protokołu SCEP.

|Obiekt    |Szczegóły    |
|----------|-----------|
|**Szablon certyfikatu SCEP**         |Szablon, który zostanie skonfigurowany w urzędzie wystawiającym certyfikaty w celu realizowania żądań protokołu SCEP urządzeń. |
|**Certyfikat uwierzytelniania klienta** |Żądany od urzędu wystawiającego certyfikaty lub publicznego urzędu certyfikacji.<br /> Ten certyfikat należy zainstalować na komputerze, który hostuje usługę NDES, i jest on używany przez łącznik certyfikatów usługi Intune.<br /> Jeśli certyfikat ma ustawione użycie kluczy *uwierzytelniania serwera* i *klienta* (**ulepszone użycie klucza**) w szablonie urzędu certyfikacji używanym do wystawienia tego certyfikatu. Następnie możesz użyć tego samego certyfikatu na potrzeby uwierzytelniania klienta i serwera. |
|**Certyfikat uwierzytelniania serwera** |Certyfikat serwera internetowego żądany od urzędu wystawiającego certyfikaty lub publicznego urzędu certyfikacji.<br /> Ten certyfikat protokołu SSL należy zainstalować i powiązać w usługach IIS na komputerze, który hostuje usługę NDES.<br />Jeśli certyfikat ma ustawione użycie kluczy *uwierzytelniania serwera* i *klienta* (**ulepszone użycie klucza**) w szablonie urzędu certyfikacji używanym do wystawienia tego certyfikatu. Następnie możesz użyć tego samego certyfikatu na potrzeby uwierzytelniania klienta i serwera. |
|**Certyfikat zaufanego głównego urzędu certyfikacji**       |Aby można było użyć profilu certyfikatu SCEP, urządzenia muszą ufać zaufanemu głównemu urzędowi certyfikacji (CA). Użyj *profilu zaufanego certyfikatu* w usłudze Intune, aby zaaprowizować certyfikat zaufanego głównego urzędu certyfikacji dla użytkowników i urządzeń. <br/><br/> **-** Użyj jednego certyfikatu zaufanego głównego urzędu certyfikacji dla każdej platformy systemu operacyjnego i powiąż ten certyfikat z poszczególnymi utworzonymi profilami zaufanych certyfikatów głównych. <br /><br /> **-** W razie potrzeby możesz użyć dodatkowych certyfikatów zaufanego głównego urzędu certyfikacji. Możesz na przykład użyć dodatkowych certyfikatów, aby urząd certyfikacji podpisujący certyfikaty uwierzytelniania serwera dla punktów dostępowych Wi-Fi był traktowany jako zaufany. Utwórz dodatkowe certyfikaty zaufanego głównego urzędu certyfikacji dla urzędów wystawiających certyfikaty.  Pamiętaj, aby w profilu certyfikatu SCEP utworzonym w usłudze Intune określić profil zaufanego głównego urzędu certyfikacji dla urzędu wystawiającego certyfikaty.<br/><br/> Aby uzyskać informacje o profilu certyfikatu zaufanego, zobacz [Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji](certificates-configure.md#export-the-trusted-root-ca-certificate) i [Tworzenie profilów zaufanych certyfikatów](certificates-configure.md#create-trusted-certificate-profiles) w temacie *Używanie certyfikatów do uwierzytelniania w usłudze Intune*. |

## <a name="configure-the-certification-authority"></a>Konfigurowanie urzędu certyfikacji

W poniższych sekcjach wykonasz następujące czynności:
- Konfigurowanie i publikowanie wymaganego szablonu dla usługi NDES. 
- Ustawianie uprawnień wymaganych do odwoływania certyfikatów. 

Poniższe sekcje wymagają znajomości systemu Windows Server 2012 R2 lub nowszego oraz usług certyfikatów Active Directory (AD CS).  

### <a name="access-your-issuing-ca"></a>Uzyskiwanie dostępu do urzędu wystawiającego certyfikaty

1. Zaloguj się do urzędu wystawiającego certyfikaty przy użyciu konta domeny z uprawnieniami wystarczającymi do zarządzania urzędem certyfikacji.  
2. Otwórz program Microsoft Management Console (MMC) urzędu certyfikacji. **Uruchom** plik „certsrv.msc” albo w **Menedżerze serwera** kliknij pozycję **Narzędzia**, a następnie **Urząd certyfikacji**.
3. Wybierz węzeł **Szablony certyfikatów**, a następnie kliknij pozycję **Akcja** > **Zarządzaj**.

### <a name="create-the-scep-certificate-template"></a>Tworzenie szablonu certyfikatu SCEP

1. Utwórz szablon certyfikatu w wersji 2 (z obsługą systemu Windows 2003) do użycia jako szablon certyfikatu SCEP. Można:  
   - za pomocą przystawki *Szablony certyfikatów* utworzyć nowy szablon niestandardowy,  
   - skopiować istniejący szablon (na przykład szablon Użytkownik), a następnie zaktualizować jego kopię tak, aby była używana jako szablon usługi NDES.
 
2. Skonfiguruj następujące ustawienia na określonych kartach szablonu:
   - **Ogólne**:
     - Usuń zaznaczenie pola **Publikuj certyfikat w usłudze Active Directory**.
     - Określ przyjazną **Nazwę wyświetlaną szablonu**, aby można było później zidentyfikować ten szablon.  

   - **Nazwa podmiotu**:  
     - Wybierz pozycję **Dostarcz w żądaniu**. Zabezpieczenia są wymuszane przez moduł zasad usługi Intune dla usługi NDES.  

     ![Szablon, karta nazwy podmiotu](./media/certificates-scep-configure/scep-ndes-subject-name.jpg)
   - **Rozszerzenia**:  
     - Upewnij się, że pozycja **Opis zasad aplikacji** uwzględnia pozycję **Uwierzytelnianie klienta**.  
       > [!IMPORTANT]  
       > Dodaj tylko te zasady aplikacji, które są wymagane. Należy uzgodnić wybrane opcje z administratorami zabezpieczeń.
 
     - W przypadku szablonów certyfikatów dla systemu iOS i macOS edytuj również pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

     ![Szablon, karta rozszerzeń](./media/certificates-scep-configure/scep-ndes-extensions.jpg)  

   - **Zabezpieczenia**:  
     - Dodaj **konto usługi NDES**. To konto wymaga uprawnień do **odczytu** i **rejestracji** w tym szablonie.

     - Dodaj kolejne konta dla administratorów usługi Intune, którzy będą tworzyć profile SCEP. Te konta wymagają uprawnień do **odczytu** szablonu, aby umożliwić administratorom przeglądanie tego szablonu podczas tworzenia profilów SCEP.  

     ![Szablon, karta zabezpieczeń](./media/certificates-scep-configure/scep-ndes-security.jpg)  

   - **Obsługiwanie żądań**:  
      Poniższy obraz jest przykładem. Twoja konfiguracja może się różnić.  

     ![Szablon, karta obsługi żądań](./media/certificates-scep-configure/scep-ndes-request-handling.png) 

   - **Wymagania wystawiania**:  
     Poniższy obraz jest przykładem. Twoja konfiguracja może się różnić.  

     ![Szablon, karta wymagań wystawiania](./media/certificates-scep-configure/scep-ndes-issuance-reqs.jpg)  

3. Zapisz szablon certyfikatu.  

### <a name="create-the-client-certificate-template"></a>Tworzenie szablonu certyfikatu klienta

Łącznik certyfikatów usługi Intune wymaga certyfikatu z ulepszonym użyciem klucza *uwierzytelniania klienta* i nazwą podmiotu równą nazwie FQDN maszyny, na której jest zainstalowany łącznik. Wymagany jest szablon z następującymi właściwościami:

- Obszar **Rozszerzenia** > **Zasady aplikacji** musi zawierać właściwość **Uwierzytelnienie klienta**
- **Nazwa podmiotu** > **Dostarcz w żądaniu**.

Jeśli masz już szablon, który zawiera te właściwości, możesz użyć go ponownie. W przeciwnym razie utwórz nowy szablon, duplikując istniejący lub tworząc szablon niestandardowy.

### <a name="create-the-server-certificate-template"></a>Tworzenie szablonu certyfikatu serwera

Komunikacja między zarządzanymi urządzeniami i usługami IIS na serwerze usługi NDES korzysta z protokołu HTTPS, który wymaga użycia certyfikatu. Do wystawienia tego certyfikatu możesz użyć szablonu certyfikatu **serwera internetowego**. Jeśli jednak wolisz korzystać z dedykowanego szablonu, wymagane są następujące właściwości:

- Obszar **Rozszerzenia** > **Zasady aplikacji** musi zawierać właściwość **Uwierzytelnienie serwera**
- **Nazwa podmiotu** > **Dostarcz w żądaniu**.

> [!NOTE]  
> Jeśli masz certyfikat spełniający oba wymagania z szablonów certyfikatów klienta i serwera, możesz użyć jednego certyfikatu zarówno dla łącznika certyfikatów usługi Intune, jak i usług IIS.

### <a name="grant-permissions-for-certificate-revocation"></a>Przyznawanie uprawnień do odwoływania certyfikatów

Aby usługa Intune mogła odwoływać certyfikaty, które nie są już wymagane, należy przyznać uprawnienia w urzędzie certyfikacji. 

W łączniku certyfikatów usługi Intune możesz użyć **konta systemowego** serwera usługi NDES albo określonego konta, takiego jak **konto usługi NDES**.

1. W konsoli urzędu certyfikacji kliknij prawym przyciskiem myszy nazwę urzędu certyfikacji i wybierz pozycję **Właściwości**.
2. Na karcie **Zabezpieczenia** kliknij pozycję **Dodaj**.
3. Przyznaj uprawnienie **Wystawianie certyfikatów i zarządzanie nimi**:
   - Jeśli zdecydujesz się używać **konta systemowego** serwera usługi NDES, podaj uprawnienia do serwera usługi NDES.
   - Jeśli zdecydujesz się używać **konta usługi NDES**, zamiast tego podaj uprawnienia dla tego konta.

### <a name="modify-the-validity-period-of-the-certificate-template"></a>Modyfikowanie okresu ważności szablonu certyfikatu

Modyfikowanie okresu ważności szablonu certyfikatu jest opcjonalne.  

Po [utworzeniu szablonu certyfikatu SCEP](#create-the-scep-certificate-template) możesz edytować szablon w celu sprawdzenia **okresu ważności** na karcie **Ogólne**.  

Domyślnie usługa Intune używa wartości skonfigurowanej w szablonie. Urząd certyfikacji można jednak skonfigurować tak, aby umożliwiał żądającemu podanie innej wartości, a wartość tę można ustawić przy użyciu konsoli usługi Intune.  

> [!IMPORTANT]  
> W przypadku systemów iOS i macOS zawsze używaj wartości ustawionej w szablonie.  

#### <a name="to-configure-a-value-that-can-be-set-from-within-the-intune-console"></a>Aby skonfigurować wartość, którą można ustawić z poziomu konsoli usługi Intune  
1. Uruchom w urzędzie certyfikacji następujące polecenia:  
   -**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**  
   -**net stop certsvc**  
   -**net start certsvc**  

2. Użyj przystawki Urząd certyfikacji dla wystawiającego urzędu certyfikacji, aby opublikować szablon certyfikatu. Zaznacz węzeł **Szablony certyfikatów**, wybierz pozycję **Akcja** > **Nowy** > **Szablon certyfikatu do wystawienia**, a następnie wybierz szablon certyfikatu utworzony w poprzedniej sekcji.  

3. Sprawdź, czy certyfikat został opublikowany, wyświetlając go w folderze **Szablony certyfikatów**.  

## <a name="set-up-ndes"></a>Konfigurowanie usługi NDES  
Poniższe procedury mogą ułatwić konfigurowanie usługi rejestracji urządzeń sieciowych (NDES) do użycia z usługą Intune. Aby uzyskać więcej informacji o usłudze NDES, zobacz [Wskazówki dotyczące usługi rejestracji urządzeń sieciowych](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v%3dws.11)).  

### <a name="install-the-ndes-service"></a>Instalowanie usługi NDES  
1. Na serwerze, który będzie hostował usługę NDES, zaloguj się jako **Administrator przedsiębiorstwa**, a następnie użyj [kreatora Dodaj role i funkcje](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) w celu instalacji usługi NDES:

   1. W kreatorze wybierz pozycję **Usługi certyfikatów Active Directory**, aby uzyskać dostęp do usług ról ADCS. Zaznacz pozycję **Usługa rejestracji urządzeń sieciowych**, wyczyść pole wyboru **Urząd certyfikacji**, a następnie zakończ pracę kreatora.  

      > [!TIP]  
      > W oknie **Postęp instalacji** nie zaznaczaj pozycji **Zamknij**. Zamiast tego wybierz link **Skonfiguruj usługi certyfikatów w usłudze Active Directory na serwerze docelowym**. Zostanie otwarty kreator **Konfiguracja usług AD CS**, przy użyciu którego wykonasz następną procedurę opisaną w tym artykule, czyli *konfigurowanie usługi NDES*. Po otwarciu kreatora Konfiguracja usług AD CS można zamknąć kreatora Dodaj role i funkcje.  

   2. Po dodaniu usługi NDES do serwera kreator przeprowadzi również instalację usług IIS. Upewnij się, że usługi IIS są skonfigurowane w następujący sposób:  

      - **Serwer sieci Web** > **Zabezpieczenia** > **Filtrowanie żądań**  
      - **Serwer sieci Web** > **Projektowanie aplikacji** > **ASP.NET 3.5**  

        Podczas instalacji programu ASP .NET 3.5 zostanie zainstalowany program .NET Framework 3.5. Podczas instalacji programu .NET Framework 3.5 należy zainstalować zarówno podstawowy składnik **.NET Framework 3.5**, jak i składnik **Aktywacja HTTP**.  
      - **Serwer sieci Web** > **Projektowanie aplikacji** > **ASP.NET 4.5**  

        Podczas instalacji programu ASP .NET 4.5 zostanie zainstalowany program .NET Framework 4.5. Podczas instalowania programu .NET Framework 4.5 należy zainstalować podstawowy składnik **.NET Framework 4.5**, składnik **ASP .NET 4.5** oraz składnik **Usługi WCF** > **Aktywacja HTTP**.  

      - **Narzędzia do zarządzania** > **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** > **Zgodność z metabazą usług IIS 6**  
      - **Narzędzia do zarządzania** > **Zgodność z narzędziami zarządzania usługami IIS w wersji 6** > **Zgodność z usługą WMI dla usług IIS 6**  
      - Na serwerze dodaj konto usługi NDES jako element członkowski grupy lokalnej **IIS_IUSR**.  

2. Na komputerze, który hostuje usługę NDES, uruchom następujące polecenie w wierszu polecenia z podwyższonym poziomem uprawnień. Następujące polecenie ustawia nazwę SPN konta usługi NDES:  

   `setspn -s http/<DNS name of the computer that hosts the NDES service> <Domain name>\<NDES Service account name>`
   
   Na przykład jeśli komputer hostujący usługę NDES nosi nazwę **Server01**, Twoja domena to **Contoso.com**, a konto usługi to **NDESService**, użyj następującego polecenia:  

   `setspn –s http/Server01.contoso.com contoso\NDESService`  

### <a name="configure-the-ndes-service"></a>Konfigurowanie usługi NDES  

1. Na komputerze hostującym usługę NDES otwórz kreatora **Konfiguracja usług AD CS**, a następnie wprowadź następujące aktualizacje:  

   > [!TIP]  
   > Jeśli wykonujesz ostatnią procedurę i kliknięto link **Konfiguruj usługi certyfikatów Active Directory na serwerze docelowym**, ten kreator powinien być już otwarty. W przeciwnym przypadku otwórz Menedżera serwera, aby przejść do konfiguracji powdrożeniowej usług certyfikatów Active Directory.  

   - W polu **Usługi ról** wybierz pozycję **Usługa rejestracji urządzeń sieciowych**.
   - Na stronie **Konto usługi dla usługi rejestracji urządzeń sieciowych** określ konto usługi NDES.
   - Na stronie **Urząd certyfikacji dla usługi rejestrowania urządzeń sieciowych** kliknij pozycję **Wybierz**, a następnie wybierz urząd wystawiający certyfikaty, w którym skonfigurowano szablon certyfikatu.
   - Na stronie **Kryptografia dla usługi rejestracji urządzeń sieciowych** ustaw długość klucza zgodnie z wymaganiami firmy.
   - Na stronie **Potwierdzenie** wybierz pozycję **Konfiguruj**, aby zakończyć pracę kreatora.

2. Po zakończeniu pracy kreatora zaktualizuj następujący klucz rejestru na komputerze hostującym usługę NDES:  
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`  

   Aby zaktualizować ten klucz, określ wartość **Przeznaczenie** dla szablonów certyfikatów (znajdującą się na karcie **Obsługiwanie żądań**). Następnie zaktualizuj odpowiedni wpis w rejestrze, zastępując istniejące dane nazwą szablonu certyfikatu (a nie nazwą wyświetlaną szablonu) określoną podczas [tworzenia szablonu certyfikatu](#create-the-scep-certificate-template).  

   Poniższa tabela zawiera mapowanie celów szablonu certyfikatu na wartości rejestru:
   
   |Cel szablonu certyfikatu (na karcie Obsługiwanie żądań)|Wartość rejestru do edycji|Wartość wyświetlona w konsoli administratora usługi Intune dla profilu SCEP|
   |------------------------|-------------------------|---|
   |Podpis               |SignatureTemplate        |Podpis cyfrowy |
   |Szyfrowanie              |EncryptionTemplate       |Szyfrowanie klucza  |
   |Podpis i szyfrowanie|GeneralPurposeTemplate   |Szyfrowanie klucza<br/>Podpis cyfrowy |  

   Na przykład jeśli Cel szablonu certyfikatu to **Szyfrowanie**, należy edytować wartość **EncryptionTemplate** i wprowadzić nazwę szablonu certyfikatu.  

3. Skonfiguruj filtrowanie żądań usług IIS w celu dodania obsługi w usługach IIS dla długich adresów URL (zapytań) odbieranych przez usługę NDES.
   1. W Menedżerze usług IIS wybierz pozycję **Domyślna witryna internetowa** > **Filtrowanie żądań** > **Edytuj ustawienia funkcji**, aby otworzyć stronę **Edytowanie ustawień filtrowania żądań**.  

   2. Skonfiguruj następujące ustawienia:  
      - **Maksymalna długość adresu URL (w bajtach)** = 65534  
      - **Maksymalna długość ciągu zapytania (w bajtach)** = 65534  
   3. Wybierz przycisk **OK**, aby zapisać tę konfigurację i zamknąć menedżera usług IIS.  
   4. Zweryfikuj tę konfigurację, wyświetlając następujący klucz rejestru w celu potwierdzenia, że ma on wskazane wartości:  

      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`    

      Następujące wartości są ustawione jako wpisy typu DWORD:  
      - Nazwa: **MaxFieldLength** o wartości dziesiętnej **65534**  
      - Nazwa: **MaxRequestBytes** o wartości dziesiętnej **65534**  
4. Uruchom ponownie serwer hostujący usługę NDES. Nie używaj polecenia **iisreset**; nie wprowadza ono wymaganych zmian.  

5. Przejdź do lokalizacji *http://* nazwa_FQDN_serwera */certsrv/mscep/mscep.dll.* Powinna zostać wyświetlona strona usługi NDES podobna do tej z poniższego obrazu:  

   ![Testowanie usługi NDES](./media/certificates-scep-configure/scep-ndes-url.png)
  
   Jeśli adres internetowy zwraca komunikat **503 usługa niedostępna**, sprawdź podgląd zdarzeń komputera. Ten błąd występuje często, gdy pula aplikacji zostanie zatrzymana z powodu braku [uprawnień dla konta usługi NDES](#accounts).  
  
### <a name="install-and-bind-certificates-on-the-server-that-hosts-ndes"></a>Instalowanie i powiązanie certyfikatów na serwerze hostującym usługę NDES  
> [!TIP]  
> W poniższej procedurze możesz użyć jednego certyfikatu zarówno na potrzeby *uwierzytelniania serwera*, jak i *uwierzytelniania klienta*, gdy ten certyfikat jest skonfigurowany tak, że spełnia kryteria obu zastosowań. Kryteria dla każdego zastosowania są opisane w krokach 1 i 3 poniższej procedury.  

1. Zażądaj certyfikatu **uwierzytelniania serwera** od wewnętrznego lub publicznego urzędu certyfikacji, a następnie zainstaluj ten certyfikat na serwerze.  

   Jeśli serwer używa nazwy zewnętrznej i wewnętrznej dla pojedynczego adresu sieciowego, certyfikat uwierzytelniania serwera musi spełniać następujące warunki:  

   - Pole **Nazwa podmiotu** zawiera zewnętrzną, publiczną nazwę serwera.
   - Pole **Alternatywna nazwa podmiotu** zawiera wewnętrzną nazwę serwera.  

2. Powiązanie certyfikatu uwierzytelniania serwera w usługach IIS:  
  
   1. Po zainstalowaniu certyfikatu uwierzytelniania serwera otwórz **Menedżera usług IIS** i wybierz pozycję **Domyślna witryna internetowa**. W okienku **Akcje** wybierz pozycję **Powiązania**.  
   1. Wybierz pozycję **Dodaj**, w polu **Typ** ustaw wartość **https** i potwierdź, że ustawiony port to **443**.  
   1. W polu **Certyfikat SSL**określ certyfikat uwierzytelniania serwera.  
 
3. Na serwerze usługi NDES zażądaj certyfikatu **uwierzytelniania klienta** od wewnętrznego lub publicznego urzędu certyfikacji i zainstaluj ten certyfikat.  

   Certyfikat uwierzytelniania klienta musi mieć następujące właściwości:  
   - **Ulepszone użycie klucza**: musi to być wartość **Uwierzytelnianie klienta**.  
   - **Nazwa podmiotu**: ta wartość musi być nazwą DNS serwera, na którym jest instalowany certyfikat (serwer usługi NDES).  

4. Serwer hostujący usługę NDES jest teraz gotowy do obsługi łącznika certyfikatów usługi Intune.  

## <a name="install-the-intune-certificate-connector"></a>Instalowanie łącznika certyfikatów usługi Intune  
Łącznik certyfikatów usługi Microsoft Intune jest instalowany na serwerze, na którym jest uruchomiona usługa NDES. Użycie usługi NDES lub łącznika certyfikatów usługi Intune na tym samym serwerze co urząd wystawiający certyfikaty (CA) nie jest obsługiwane.  

Aby zainstalować łącznik certyfikatów, wykonaj następujące czynności:  
1. Zaloguj się do [portalu usługi Intune](https://aka.ms/intuneportal) przy użyciu konta, które ma uprawnienia do usługi Intune.  

2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Urząd certyfikacji** > **Dodaj**.  

3. Pobierz i zapisz plik łącznika protokołu SCEP. Zapisz go w lokalizacji dostępnej z serwera, na którym zamierzasz zainstalować łącznik.

   ![ConnectorDownload](./media/certificates-scep-configure/download-certificates-connector.png)

4. Po zakończeniu pobierania przejdź do serwera hostującego rolę usługi rejestracji urządzeń sieciowych (NDES). Następnie:  

   1. Upewnij się, że jest zainstalowany program .NET 4.5 Framework, ponieważ jest on wymagany przez łącznik certyfikatów usługi Intune. Program .NET 4.5 Framework jest automatycznie dołączany do systemu Windows Server 2012 R2 i nowszych wersji.  
   2. Uruchom instalator (**NDESConnectorSetup.exe**). Instalator instaluje również moduł zasad dla usługi NDES oraz usługę internetową punktu rejestracji certyfikatu (CRP) usług IIS. Usługa internetowa CRP, *CertificateRegistrationSvc*, jest uruchamiana jako aplikacja w usługach IIS.  

      - Podczas instalacji usługi NDES dla autonomicznej usługi Intune usługa CRP jest instalowana automatycznie wraz z łącznikiem certyfikatów. 
      - W przypadku używania usługi Intune z programem Configuration Manager punkt rejestracji certyfikatu (CRP) jest instalowany jako rola systemu lokacji programu Configuration Manager.  
5. Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, wybierz pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany na serwerze usługi NDES w ramach kroku nr 3 procedury [Instalowanie i powiązanie certyfikatów na serwerze hostującym usługę NDES](#install-and-bind-certificates-on-the-server-that-hosts-ndes) we wcześniejszej części tego artykułu.  

   Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune**. Mimo że wybrany certyfikat nie jest wyświetlany, wybierz pozycję **Dalej**, aby wyświetlić właściwości certyfikatu. Wybierz pozycję **Dalej**, a następnie pozycję **Zainstaluj**.

6. Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.  

   Jeśli kreator zostanie zamknięty przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz uruchomić go za pomocą następującego polecenia: *<ścieżka_instalacji>\NDESConnectorUI\NDESConnectorUI.exe*

7. W interfejsie użytkownika **łącznika certyfikatów** :  
   1. Wybierz pozycję **Zaloguj** i podaj poświadczenia administratora usługi Intune lub administratora dzierżawy z uprawnieniami administratora globalnego.  
   2. Używane konto musi mieć przypisaną prawidłową licencję usługi Intune.  
   3. Po zalogowaniu łącznik certyfikatów usługi Intune pobierze certyfikat z usługi Intune. Ten certyfikat jest używany do uwierzytelniania pomiędzy łącznikiem a usługą Intune. Jeśli użyte konto nie ma licencji usługi Intune, łącznik (NDESConnectorUI.exe) nie będzie mógł pobrać certyfikatu z usługi Intune.  

      Jeśli Twoja organizacja korzysta z serwera proxy i serwer usługi NDES wymaga go na potrzeby dostępu do Internetu, wybierz pozycję **Użyj serwera proxy**. Następnie wprowadź nazwę serwera proxy, port oraz poświadczenia konta, aby nawiązać połączenie.  

    4. Wybierz kartę **Zaawansowane** i podaj poświadczenia konta z uprawnieniem **Wystawianie certyfikatów i zarządzanie nimi** dla wystawiającego urzędu certyfikacji. **Zastosuj** zmiany.  

    5. Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.  

8. Otwórz wiersz polecenia, wpisz **services.msc**, a następnie naciśnij klawisz **Enter**. Kliknij prawym przyciskiem myszy pozycję **Usługa łącznika usługi Intune** > **Uruchom ponownie**.


Aby sprawdzić, czy usługa jest uruchomiona, otwórz przeglądarkę i podaj następujący adres URL. Powinien zostać zwrócony błąd **403**: `http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`  

> [!NOTE]  
> Łącznik certyfikatów usługi Intune obsługuje protokół TLS 1.2. Jeśli serwer hostujący łącznik obsługuje protokół TLS 1.2, zostanie użyty protokół TLS 1.2. Jeśli serwer nie obsługuje protokołu TLS 1.2, jest używany protokół TLS 1.1. Obecnie protokół TLS 1.1 jest używany do uwierzytelniania między urządzeniami a serwerem.

## <a name="next-steps"></a>Następne kroki

[Tworzenie profilu certyfikatu protokołu SCEP](certificates-profile-scep.md)  
[Rozwiązywanie problemów dotyczących łącznika certyfikatów usługi Intune](troubleshoot-certificate-connector-events.md)
