---
title: Wystawianie certyfikatów PKCS DigiCert w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Instalowanie i konfigurowanie łącznika certyfikatów usługi Intune w celu wystawiania certyfikatów PKCS przy użyciu platformy PKI firmy DigiCert dla urządzeń zarządzanych przez usługę Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1679eb656e04296e53d8994dcd47144621c99d0c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721776"
---
# <a name="set-up-intune-certificate-connector-for-digicert-pki-platform"></a>Konfigurowanie łącznika certyfikatów usługi Intune dla platformy infrastruktury kluczy publicznych firmy DigiCert  

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Łącznik certyfikatów usługi Intune umożliwia wystawianie certyfikatów PKCS przy użyciu platformy PKI firmy DigiCert dla urządzeń zarządzanych przez usługę Intune. Łącznika można używać tylko z urzędem certyfikacji firmy DigiCert lub zarówno z urzędem certyfikacji firmy DigiCert, jak i urzędem certyfikacji firmy Microsoft.  
> [!TIP]  
> Firma DigiCert przejęła od firmy Symantec rozwiązania w zakresie zabezpieczania witryn internetowych oraz infrastruktury kluczy publicznych. Aby uzyskać więcej informacji na temat tej zmiany, zobacz [odpowiedni artykuł dotyczący pomocy technicznej firmy Symantec](https://support.symantec.com/en_US/article.INFO4722.html).

Jeśli łącznik certyfikatów usługi Intune jest już używany do wystawiania certyfikatów z urzędu certyfikacji firmy Microsoft przy użyciu protokołu PKCS lub ochrony punktu końcowego programu System Center, można użyć tego samego łącznika do konfigurowania i wystawiania certyfikatów PKCS z urzędu certyfikacji firmy DigiCert. Po zakończeniu konfiguracji w celu obsługi urzędu certyfikacji DigiCert łącznik certyfikatów usługi Intune może wydać następujące certyfikaty:

* Certyfikaty PKCS z urzędu certyfikacji firmy Microsoft
* Certyfikaty PKCS z urzędu certyfikacji firmy DigiCert
* Certyfikaty programu Endpoint Protection z urzędu certyfikacji firmy Microsoft

Jeśli nie masz zainstalowanego łącznika, ale planujesz użyć go zarówno dla urzędu certyfikacji firmy Microsoft, jak i urzędu certyfikacji firmy DigiCert, najpierw wykonaj konfigurację łącznika dla urzędu certyfikacji firmy Microsoft. Następnie wróć do tego artykułu, aby skonfigurować łącznik do obsługi firmy DigiCert. Aby uzyskać więcej informacji o profilach certyfikatów i łączniku, zobacz [Konfigurowanie profilu certyfikatu dla urządzeń w usłudze Microsoft Intune](certificates-configure.md).  

Jeśli będziesz używać użyjesz łącznika z tylko urzędem certyfikacji firmy DigiCert, możesz skorzystać z instrukcji przedstawionych w tym artykule, aby zainstalować, a następnie skonfigurować łącznik. 

## <a name="prerequisites"></a>Wymagania wstępne  
- **Aktywna subskrypcja w urzędzie certyfikacji DigiCert**: subskrypcja jest wymagana do uzyskania certyfikatu urzędu rejestrowania z urzędu certyfikacji firmy DigiCert.

## <a name="install-the-digicert-ra-certificate"></a>Instalowanie certyfikatu urzędu rejestrowania firmy DigiCert  
 
1. Zapisz następujący fragment kodu w pliku o nazwie **certreq.ini** i zaktualizuj go zgodnie z potrzebami (na przykład: *Subject name in CN format* (Nazwa podmiotu w formacie CN).
 
        [Version] 
        Signature="$Windows NT$" 
        
        [NewRequest] 
        ;Change to your,country code, company name and common name 
        Subject = "Subject Name in CN format"
        
        KeySpec = 1 
        KeyLength = 2048 
        Exportable = TRUE 
        MachineKeySet = TRUE 
        SMIME = False 
        PrivateKeyArchive = FALSE 
        UserProtected = FALSE 
        UseExistingKeySet = FALSE 
        ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
        ProviderType = 12 
        RequestType = PKCS10 
        KeyUsage = 0xa0 
        
        [EnhancedKeyUsageExtension] 
        OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication
        
        ;----------------------------------------------- 

2. Otwórz wiersz polecenia z podwyższonym poziomem uprawnień i wygeneruj żądanie podpisania certyfikatu (CSR) przy użyciu następującego polecenia:

   `Certreq.exe -new certreq.ini request.csr`

3. Otwórz plik request.csr w programie Notatnik i skopiuj zawartość żądania CSR w następującym formacie:


        -----BEGIN NEW CERTIFICATE REQUEST-----
        MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
        …
        …
        fzpeAWo=
        -----END NEW CERTIFICATE REQUEST-----


4. Zaloguj się do urzędu certyfikacji DigiCert i przejdź do zadania **Get an RA Cert** (Uzyskaj certyfikat RA).

   a. Wklej zawartość żądania CSR uzyskaną w kroku 3 w polu tekstowym. 

   b. Podaj przyjazną nazwę certyfikatu.

   c. Wybierz pozycję **Continue** (Kontynuuj). 

   d. Użyj podanego linku, aby pobrać certyfikat urzędu rejestrowania na komputer lokalny.

5. Zaimportuj certyfikat urzędu rejestrowania do magazynu certyfikatów systemu Windows:

   a. Otwórz konsolę MMC.

   b. Wybierz kolejno opcje **Plik** > **Dodawanie lub usuwanie przystawek** > **Certyfikat** > **Dodaj**. 

   c. Wybierz kolejno opcje **Konto komputera** > **Dalej**.

   d. Wybierz kolejno opcje **Komputer lokalny** > **Zakończ**. 

   e. W oknie dialogowym **Dodawanie lub usuwanie przystawek** wybierz przycisk **OK**. Rozwiń węzeł **Certyfikaty (Komputer lokalny)** > **Osobiste** > **Certyfikaty**.

   f. Kliknij prawym przyciskiem myszy węzeł **Certyfikaty**, a następnie wybierz kolejno opcje **Wszystkie zadania** > **Importuj**.  

   g. Wybierz lokalizację certyfikatu urzędu rejestrowania pobranego z urzędu certyfikacji firmy DigiCert i wybierz przycisk **Dalej**.

   h. Wybierz kolejno opcje **Osobisty magazyn certyfikatów** > **Dalej**. 

   i. Wybierz pozycję **Zakończ**, aby zaimportować certyfikat urzędu rejestrowania wraz z kluczem prywatnym do magazynu **Komputer lokalny-Osobiste**.  

6. Wyeksportuj i zaimportuj certyfikat klucza prywatnego: 

   a. Rozwiń węzeł **Certyfikaty (Komputer lokalny)** > **Osobiste** > **Certyfikaty**.

   b. Wybierz certyfikat, który został zaimportowany w poprzednim kroku.

   c. Kliknij prawym przyciskiem myszy certyfikat i wybierz kolejno pozycje **Wszystkie zadania** > **Eksportuj**.

   d. Wybierz pozycję **Dalej**, a następnie wprowadź hasło.

   e. Wybierz lokalizację eksportu i wybierz pozycję **Zakończ**.

   f. Wykonaj tę samą procedurę od kroku 5, aby zaimportować certyfikat klucza prywatnego do magazynu **Komputer lokalny-Osobiste**.

   g. Zarejestruj kopię odcisku palca certyfikatu urzędu rejestrowania bez żadnych spacji. Poniżej przedstawiono przykładowy odcisk palca: 

        RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
    
    > [!NOTE]
    > Aby uzyskać pomoc dotyczącą uzyskiwania certyfikatu urzędu rejestrowania z urzędu certyfikacji DigiCert, skontaktuj się z [działem obsługi klienta firmy DigiCert](mailto:enterprise-pkisupport@digicert.com).  

## <a name="prepare-to-install-intune-certificate-connector"></a>Przygotowanie do instalacji łącznika certyfikatów usługi Intune
> [!TIP]  
> Ta sekcja ma zastosowanie w przypadku używania łącznika certyfikatów usługi Intune z tylko urzędem certyfikacji DigiCert. Jeśli używasz łącznika certyfikatów usługi Intune z urzędem certyfikacji firmy Microsoft i chcesz dodać obsługę urzędu certyfikacji DigiCert, przejdź do sekcji [Konfigurowanie łącznika do obsługi urzędu certyfikacji DigiCert](#configure-the-connector-to-support-digicert).  

1. Wybierz jedną z wersji systemu operacyjnego Windows z listy poniżej i zainstaluj ją na komputerze:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Utwórz użytkownika z uprawnieniami administracyjnymi i za jego pomocą wykonaj czynności podane poniżej.

3. Sprawdź najnowsze aktualizacje systemu Windows, po czym zainstaluj je, jeśli są dostępne. Po zainstalowaniu aktualizacji systemu Windows uruchom ponownie komputer.

4. Zainstaluj program .NET Framework 3.5:

   a. Wybierz kolejno opcje **Panel sterowania** > **Programy i funkcje** > **Włącz lub wyłącz funkcje systemu Windows**.

   b. Wybierz pozycję **.NET Framework 3.5** i zainstaluj program.  

## <a name="install-intune-certificate-connector-for-use-with-digicert"></a>Instalowanie łącznika certyfikatów usługi Intune do obsługi urzędu certyfikacji DigiCert  

> [!TIP]  
> Jeśli używasz łącznika certyfikatów usługi Intune z urzędem certyfikacji firmy Microsoft i chcesz dodać obsługę urzędu certyfikacji DigiCert, przejdź do sekcji [Konfigurowanie łącznika do obsługi urzędu certyfikacji DigiCert](#configure-the-connector-to-support-digicert).  

Pobierz najnowszy łącznik certyfikatów usługi Intune z portalu administracyjnego usługi Intune i wykonaj poniższe instrukcje.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Łączniki certyfikatów** > **+ Dodaj**.  

3. Wybierz pozycję **Pobierz oprogramowanie łącznika certyfikatów**. Zapisz oprogramowanie w lokalizacji dostępnej z serwera, na którym ma ono zostać zainstalowane.  

   ![Pobieranie oprogramowania łącznika](./media/certificates-digicert-configure/connector-download.png)
   
4. Na serwerze, na którym chcesz zainstalować łącznik, uruchom plik **NDESConnectorSetup.exe** z podwyższonym poziomem uprawnień. 

5. Na stronie **Opcje instalacji** wybierz pozycję **Dystrybucja PFX**.  
   
   ![Wybieranie pozycji Dystrybucja PFX](./media/certificates-digicert-configure/digicert-ca-connector-install.png)

   > [!IMPORTANT]
   > Jeśli chcesz skonfigurować łącznik certyfikatów usługi Intune do wystawiania certyfikatów z urzędu certyfikacji firmy Microsoft oraz urzędu certyfikacji firmy DigiCert, wybierz pozycję **Dystrybucja profilów SCEP i PFX**. 

6. Użyj opcji domyślnych, aby ukończyć konfigurowanie łącznika.

## <a name="configure-the-connector-to-support-digicert"></a>Konfigurowanie łącznika do obsługi urzędu certyfikacji DigiCert

Domyślnie łącznik certyfikatów usługi Intune jest instalowany w ścieżce **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc**.

1. W folderze **NDESConnectorSvc** otwórz plik **NDESConnector.exe.config** w Notatniku.

   a. Zaktualizuj wartość klucza `RACertThumbprint` do wartości odcisku palca certyfikatu skopiowanej w poprzedniej sekcji. Przykład:

        <add key="RACertThumbprint"
        value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   
   b. Zapisz i zamknij plik.

2. Otwórz plik **services.msc**:

   a. Wybierz opcję **Usługa łącznika usługi Intune**.

   b. Zatrzymaj usługę, a następnie uruchom usługę.

   c. Zamknij okno usługi.

## <a name="set-up-the-intune-administrator-account"></a>Konfigurowanie konta administratora usługi Intune  

> [!TIP]  
> Jeśli używasz łącznika certyfikatów usługi Intune z urzędem certyfikacji firmy Microsoft i chcesz dodać obsługę urzędu certyfikacji DigiCert, przejdź do sekcji [Tworzenie profilu zaufanego certyfikatu](#create-a-trusted-certificate-profile).   
 
1. Otwórz interfejs użytkownika łącznika usługi NDES z pliku **%ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe**.  

2. Na karcie **Rejestracja** wybierz pozycję **Zaloguj się**.

3. Podaj poświadczenia administratora dzierżawy usługi Intune.

4. Wybierz pozycję **Zaloguj się**, a następnie wybierz pozycję **OK**, aby potwierdzić pomyślną rejestrację. Zamknij interfejs użytkownika łącznika usługi NDES.
   
   ![Interfejs łącznika usługi NDES z komunikatem o pomyślnym zarejestrowaniu](./media/certificates-digicert-configure/certificates-digicert-configure-connector-configure.png)



## <a name="create-a-trusted-certificate-profile"></a>Tworzenie profilu zaufanego certyfikatu

Certyfikaty PKCS wdrożone dla urządzeń zarządzanych przez usługę Intune muszą być powiązane przy użyciu zaufanego certyfikatu głównego. Aby ustanowić takie połączenie, należy utworzyć profil zaufanego certyfikatu usługi Intune przy użyciu certyfikatu głównego uzyskanego z urzędu certyfikacji firmy DigiCert.

1. Pobierz zaufany certyfikat główny z urzędu certyfikacji firmy DigiCert:

    a. Zaloguj się do portalu administracyjnego urzędu certyfikacji DigiCert.

    b. Wybierz pozycję **Manage CAs** (Zarządzaj urzędami certyfikacji) w obszarze **Tasks** (Zadania). 

    c. Wybierz z listy odpowiedni urząd certyfikacji.  

    d. Kliknij opcję **Download root certificate** (Pobierz certyfikat główny), aby pobrać zaufany certyfikat główny.

2. Utwórz profil zaufanego certyfikatu w portalu usługi Intune:

   a. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

   b. Wybierz pozycję **Konfiguracja urządzenia** > **Zarządzaj** > **Profile** > **Utwórz profil**.

   c. Wypełnij pola **Nazwa** i **Opis** dla profilu zaufanego certyfikatu.

   d. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego zaufanego certyfikatu.

   e. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat zaufany**.

   f. Przejdź do pliku CER zaufanego głównego urzędu certyfikacji uzyskanego w urzędzie certyfikacji DigiCert w poprzednim kroku, a następnie wybierz pozycję **OK**.

   g. Dotyczy wyłącznie urządzeń z systemem Windows 8.1 i Windows 10: wybierz dla zaufanego certyfikatu magazyn docelowy spośród wymienionych poniżej:    
      - **Magazyn certyfikatów komputera — główny**  
      - **Magazyn certyfikatów komputera — pośredni**  
      - **Magazyn certyfikatów użytkownika — pośredni** 

   h. Gdy skończysz, wybierz opcję **OK**, wróć do okienka **Tworzenie profilu** i wybierz pozycję **Utwórz**.  
 
Profil zostanie wyświetlony na liście profilów w okienku **Konfiguracja urządzenia — Profile** z typem profilu **Certyfikat zaufany**.  Przypisz ten profil do urządzeń, które będą otrzymywały certyfikaty. Aby przypisać profil do grup, zobacz [Przypisywanie profilów urządzeń](../configuration/device-profile-assign.md).


## <a name="get-the-certificate-profile-oid"></a>Pobieranie identyfikatora OID profilu certyfikatu  

Identyfikator OID profilu certyfikatu jest skojarzony z szablonem profilu certyfikatu w urzędzie certyfikacji firmy DigiCert. Aby utworzyć profil certyfikatu PKCS w usłudze Intune, należy podać nazwę szablonu certyfikatu w formie identyfikatora OID profilu certyfikatu, który jest skojarzony z szablonem certyfikatu w urzędzie certyfikacji firmy DigiCert.

1. Zaloguj się do portalu administracyjnego urzędu certyfikacji DigiCert.
2. Kliknij pozycję **Manage Certificate Profiles** (Zarządzaj profilami certyfikatów).
3. Wybierz profil certyfikatu, którego chcesz użyć.
4. Skopiuj identyfikator OID profilu certyfikatu. Będzie on podobny do poniższego przykładu:

 
       Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
 

> [!NOTE]
> Jeśli potrzebujesz pomocy w celu uzyskania identyfikatora OID profilu certyfikatu, skontaktuj się z [obsługą klienta firmy DigiCert](mailto:enterprise-pkisupport@digicert.com).

## <a name="create-a-pkcs-certificate-profile"></a>Tworzenie profilu certyfikatu PKCS

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Przejdź do pozycji **Konfiguracja urządzeń** >  **Profile** i wybierz pozycję **Utwórz profil**.

3. Wypełnij pola **Nazwa** i **Opis** dla profilu certyfikatu PKCS.  

4. Z listy rozwijanej **Platforma** wybierz obsługiwaną platformę urządzenia.

5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat PKCS**.
 
6. W okienku **Certyfikat PKCS** skonfiguruj parametry, korzystając z wartości z poniższej tabeli. Te wartości są wymagane do wystawiania certyfikatów PKCS z urzędu certyfikacji DigiCert za pośrednictwem łącznika certyfikatów usługi Intune. 

   |Parametr certyfikatu PKCS | Wartość | Opis |
   | --- | --- | --- |
   | Urząd certyfikacji | pki-ws.symauth.com | Ta wartość musi być nazwą FQDN usługi podstawowej urzędu certyfikacji firmy DigiCert bez końcowych ukośników. Jeśli nie masz pewności, czy jest to prawidłowa nazwa FQDN usługi podstawowej dla Twojej subskrypcji urzędu certyfikacji firmy DigiCert, skontaktuj się z pomocą techniczną tej firmy. <br><br>*Po zmianie z Symantec na DigiCert ten adres URL pozostaje niezmieniony*. <br><br> Jeśli ta nazwa FQDN będzie niepoprawna, łącznik certyfikatów usługi Intune nie będzie wystawiać certyfikatów PKCS z urzędu certyfikacji firmy DigiCert.| 
   | Nazwa urzędu certyfikacji | Symantec | Ta wartość musi być ciągiem **Symantec**. <br><br> Jeśli ta wartość zostanie zmieniona, łącznik certyfikatów usługi Intune nie będzie wystawiać certyfikatów PKCS z urzędu certyfikacji firmy DigiCert.|
   | Nazwa szablonu certyfikatu | Identyfikator OID profilu certyfikatu z urzędu certyfikacji firmy DigiCert. Przykład: **2.16.840.1.113733.1.16.1.2.3.1.1.61904612**| Tą wartością musi być identyfikator OID profilu certyfikatu [uzyskany w poprzedniej sekcji](#get-the-certificate-profile-oid) z szablonu profilu certyfikatu urzędu certyfikacji firmy DigiCert. <br><br> Jeśli łącznik certyfikatów usługi Intune nie będzie mógł odnaleźć szablonu certyfikatu skojarzonego z tym identyfikatorem OID profilu certyfikatu w urzędzie certyfikacji firmy DigiCert, nie będzie wystawiać certyfikatów PKCS z urzędu certyfikacji firmy DigiCert.|  

   ![Opcje wyboru urzędu certyfikacji i szablonu certyfikatu](./media/certificates-digicert-configure/certificates-digicert-pkcs-example.png)  

   > [!NOTE]
   > Profil certyfikatu PKCS dla platform systemu Windows nie musi być skojarzony z profilem zaufanego certyfikatu. Jest to jednak wymagane dla profilów platform innych niż system Windows, np. dla systemu Android.
7. Skonfiguruj profil tak, aby zaspokajał Twoje potrzeby biznesowe, a następnie wybierz przycisk **OK**, aby go zapisać. 

8. Wybierz pozycję **Przypisania** i skonfiguruj odpowiednią grupę, która będzie otrzymywać ten profil. Do przypisanej grupy musi należeć co najmniej jeden użytkownik lub jedno urządzenie.
 
Po wykonaniu poprzednich kroków łącznik certyfikatów usługi Intune będzie wystawiać certyfikaty PKCS z urzędu certyfikacji firmy DigiCert dla urządzeń zarządzanych przez usługę Intune w przypisanej grupie. Te certyfikaty będą dostępne w magazynie **osobistym** magazynu certyfikatów **bieżącego użytkownika** na urządzeniu zarządzanym przez usługę Intune.

### <a name="supported-attributes-for-the-pkcs-certificate-profile"></a>Obsługiwane atrybuty profilu certyfikatu PKCS

|Atrybut | Formaty obsługiwane przez usługę Intune | Formaty obsługiwane przez urząd certyfikacji w chmurze firmy DigiCert | result |
| --- | --- | --- | --- |
| Nazwa podmiotu |Usługa Intune obsługuje nazwę podmiotu tylko w trzech formatach podanych poniżej: <br><br> 1. Nazwa pospolita <br> 2. Nazwa pospolita zawierająca adres e-mail <br> 3. Nazwa pospolita będąca adresem e-mail <br><br> Przykład: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | Urząd certyfikacji DigiCert obsługuje więcej atrybutów.  Jeśli chcesz wybrać dodatkowe atrybuty, muszą one zostać zdefiniowane przy użyciu stałych wartości w szablonie profilu certyfikatu firmy DigiCert.| Używamy nazwy pospolitej lub adresu e-mail z żądania certyfikatu PKCS. <br><br> Wszelkie niezgodności w wyborze atrybutów występujące między profilem certyfikatu usługi Intune i szablonem profilu certyfikatu firmy DigiCert powodują, że urząd certyfikacji firmy DigiCert nie wystawia żadnych certyfikatów.|
| SAN | Usługa Intune obsługuje tylko następujące wartości pola SAN: <br><br> **AltNameTypeEmail** <br> **AltNameTypeUpn** <br> **AltNameTypeOtherName** (wartość zakodowana) | Urząd certyfikacji w chmurze firmy DigiCert również obsługuje te parametry. Jeśli chcesz wybrać dodatkowe atrybuty, muszą one zostać zdefiniowane przy użyciu stałych wartości w szablonie profilu certyfikatu firmy DigiCert. <br><br> **AltNameTypeEmail**: jeśli ten typ nie zostanie odnaleziony w nazwie SAN, łącznik certyfikatów usługi Intune używa wartości typu **AltNameTypeUpn**.  Jeśli typ **AltNameTypeUpn** również nie zostanie odnaleziony w nazwie SAN, łącznik certyfikatów usługi Intune używa wartości nazwy podmiotu, o ile jest ona w formacie adresu e-mail.  Jeśli typ nadal nie zostanie odnaleziony, łącznik certyfikatów usługi Intune nie będzie mógł wystawiać certyfikatów. <br><br> Przykład: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> **AltNameTypeUpn**: jeśli ten typ nie zostanie odnaleziony w nazwie SAN, łącznik certyfikatu usługi użyje wartości typu **AltNameTypeEmail**. Jeśli typ **AltNameTypeEmail** również nie zostanie odnaleziony w nazwie SAN, łącznik certyfikatów usługi Intune używa wartości nazwy podmiotu, o ile jest ona w formacie adresu e-mail. Jeśli typ nadal nie zostanie odnaleziony, łącznik certyfikatów usługi Intune nie będzie mógł wystawiać certyfikatów.  <br><br> Przykład: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> **AltNameTypeOtherName**: jeśli ten typ nie zostanie odnaleziony w nazwie SAN, łącznik certyfikatów usługi Intune nie będzie mógł wystawiać certyfikatów. <br><br> Przykład: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  Wartość tego pola jest obsługiwana przez urząd certyfikacji firmy DigiCert tylko w formacie zakodowanym (wartość szesnastkowa). Tak więc łącznik certyfikatów usługi Intune konwertuje wszystkie wartości w tym polu na wartość szyfrowaną przy użyciu kodowania base64 przed przesłaniem żądania certyfikatu. *Łącznik certyfikatów usługi Intune nie weryfikuje, czy ta wartość jest już zaszyfrowana czy nie.* | Brak |

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Dzienniki usługi łącznika certyfikatów w usłudze Intune są dostępne w folderze **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs** na maszynie łącznika usługi NDES. Otwórz dzienniki w programie [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) i wyszukaj wyjątki lub komunikaty o błędach.

| Komunikat o problemie/błędzie | Kroki umożliwiające rozwiązanie problemów |
| --- | --- |
| Nie można zalogować się do konta administratora dzierżawy usługi Intune w interfejsie użytkownika łącznika usługi NDES. | Może się to zdarzyć, gdy lokalny łącznik certyfikatów nie został włączony w portalu administracyjnym usługi Intune. Aby rozwiązać ten problem, użyj jednej z następujących procedur: <br><br> W interfejsie użytkownika programu Silverlight: <br> 1. Zaloguj się do [portalu administracyjnego usługi Intune](https://admin.manage.microsoft.com). <br> 2. Wybierz pozycję **ADMINISTRATOR**. <br> 3. Wybierz kolejno pozycje **Zarządzanie urządzeniami przenośnymi** > **Łącznik certyfikatów**. <br> 4. Wybierz pozycję **Skonfiguruj lokalny łącznik certyfikatów**. <br> 5. Zaznacz pole wyboru **Włącz łącznik certyfikatów**. <br> 6. Wybierz przycisk **OK**. <br><br> W interfejsie użytkownika witryny Azure Portal: <br> 1. Zaloguj się do [portalu Azure](https://portal.azure.com). <br> 2. Przejdź do usługi Microsoft Intune. <br> 3. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Urząd certyfikacji**. <br> 4. Wybierz pozycję **Włącz**. <br><br> Po wykonaniu poprzednich kroków w interfejsie użytkownika programu Silverlight lub w witrynie Azure Portal spróbuj zalogować się do tego samego konta administratora dzierżawy usługi Intune w interfejsie użytkownika łącznika usługi NDES. |
| Nie można odnaleźć certyfikatu łącznika usługi NDES. <br><br> System.ArgumentNullException: Wartość nie może być równa null. | Łącznik certyfikatów usługi Intune wyświetla ten błąd, jeśli konto administratora dzierżawy usługi Intune nigdy nie zostało użyte do logowania do interfejsu użytkownika łącznika usługi NDES. <br><br> Jeśli ten błąd będzie nadal występować, uruchom ponownie łącznik usługi Intune. <br><br> 1. Otwórz program **services.msc**. <br> 2. Wybierz opcję **Usługa łącznika usługi Intune**. <br> 3. Kliknij prawym przyciskiem myszy i wybierz polecenie **Uruchom ponownie**.|
| Łącznik usługi NDES — IssuePfx — Wyjątek ogólny: <br> System.NullReferenceException: odwołanie obiektu nie zostało ustawione na wystąpienie obiektu. | Ten błąd jest przejściowy. Uruchom ponownie łącznik usługi Intune. <br><br> 1. Otwórz program **services.msc**. <br> 2. Wybierz opcję **Usługa łącznika usługi Intune**. <br> 3. Kliknij prawym przyciskiem myszy i wybierz polecenie **Uruchom ponownie**. |
| Dostawca DigiCert — nie można pobrać zasad DigiCert. <br><br>„Upłynął limit czasu operacji”. | Łącznik certyfikatów usługi Intune odebrał błąd limitu czasu operacji podczas komunikacji z urzędem certyfikacji firmy DigiCert. Jeśli ten błąd będzie nadal występować, zwiększ wartość limitu czasu połączenia i spróbuj ponownie. <br><br> Aby zwiększyć limit czasu połączenia: <br> 1. Przejdź do komputera z łącznikiem usługi NDES. <br>2. Otwórz plik **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config** w Notatniku. <br> 3. Zwiększ wartość limitu czasu dla następującego parametru: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Uruchom ponownie usługę łącznika certyfikatów usługi Intune. <br><br> Jeśli problem będzie nadal występować, skontaktuj się z pomocą techniczną firmy DigiCert. |
| Dostawca DigiCert — nie można pobrać certyfikatu klienta. | Łącznik certyfikatów usługi Intune nie może pobrać certyfikatu autoryzacji zasobów z magazynu certyfikatów Komputer lokalny-Osobiste. Aby rozwiązać ten problem, zainstaluj certyfikat autoryzacji zasobów wraz z kluczem prywatnym w magazynie certyfikatów Komputer lokalny-Osobiste. <br><br> Certyfikat autoryzacji zasobów musi pochodzić z urzędu certyfikacji firmy DigiCert. Aby uzyskać więcej szczegółowych informacji, skontaktuj się z pomocą techniczną firmy DigiCert. | 
| Dostawca DigiCert — nie można pobrać zasad DigiCert. <br><br>„Żądanie zostało przerwane: nie można utworzyć bezpiecznego kanału SSL/TLS”. | Ten błąd występuje w następujących scenariuszach: <br><br> 1. Usługa łącznika certyfikatów usługi Intune nie ma uprawnień do odczytu certyfikatu autoryzacji zasobów wraz z kluczem prywatnym z magazynu certyfikatów Komputer lokalny-Osobiste. Aby rozwiązać ten problem, sprawdź konto kontekstu, w którym została uruchomiona usługa łącznika, w pliku services.msc. Usługa łącznika musi zostać uruchomiona w kontekście NT AUTHORITY\SYSTEM. <br><br> 2. Profil certyfikatu PKCS w portalu administracyjnym usługi Intune może zostać skonfigurowany przy użyciu nieprawidłowej nazwy FQDN usługi podstawowej urzędu certyfikacji firmy DigiCert. Nazwa FQDN jest podobna do następującej: **pki-ws.symauth.com**. Aby rozwiązać ten problem, skontaktuj się z pomocą techniczną firmy DigiCert i sprawdź, czy adres URL dla Twojej subskrypcji jest poprawny. <br><br> 3. Łącznik certyfikatów usługi Intune nie może uwierzytelniać przy użyciu urzędu certyfikacji firmy DigiCert korzystającego z certyfikatu autoryzacji zasobów, ponieważ nie może pobrać klucza prywatnego. Aby rozwiązać ten problem, zainstaluj certyfikat autoryzacji zasobów wraz z kluczem prywatnym w magazynie certyfikatów Komputer lokalny-Osobiste. <br><br> Jeśli problem będzie nadal występować, skontaktuj się z pomocą techniczną firmy DigiCert. |
| Dostawca DigiCert — nie można pobrać zasad DigiCert. <br><br>„Element żądania jest niezrozumiały”. | Łącznik certyfikatów usługi Intune nie może pobrać szablonu profilu certyfikatu firmy DigiCert, ponieważ identyfikator OID profilu klienta nie jest zgodny z profilem certyfikatu usługi Intune. Może być też tak, że łącznik certyfikatów usługi Intune nie może odnaleźć szablonu profilu certyfikatu skojarzonego z danym identyfikatorem OID profilu klienta w urzędzie certyfikacji firmy DigiCert. <br><br> Aby rozwiązać ten problem, uzyskaj prawidłowy identyfikator OID profilu klienta z szablonu certyfikatu firmy DigiCert w urzędzie certyfikacji firmy DigiCert. Następnie zaktualizuj profil certyfikatu PKCS w portalu administracyjnym usługi Intune. <br><br> Uzyskaj identyfikator OID profilu klienta z urzędu certyfikacji firmy DigiCert: <br> 1. Zaloguj się do portalu administracyjnego urzędu certyfikacji DigiCert. <br> 2. Kliknij pozycję **Manage Certificate Profiles** (Zarządzaj profilami certyfikatów). <br> 3. Wybierz profil certyfikatu, którego chcesz użyć. <br> 4. Pobierz identyfikator OID profilu certyfikatu. Będzie on podobny do poniższego przykładu: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Zaktualizuj profil certyfikatu PKCS przy użyciu poprawnego identyfikatora OID profilu certyfikatu: <br>1. Zaloguj się do portalu administracyjnego usługi Intune. <br> 2. Przejdź do profilu certyfikatu PKCS i wybierz pozycję **Edytuj**. <br> 3. Zaktualizuj identyfikator OID profilu certyfikatu w polu nazwy szablonu certyfikatu. <br> 4. Zapisz profil certyfikatu PKCS. |
| Dostawca DigiCert — nie można zweryfikować zasad. <br><br> Atrybut nie występuje na liście atrybutów szablonu certyfikatu obsługiwanych przez firmę DigiCert. | Urząd certyfikacji firmy DigiCert wyświetla ten komunikat, jeśli wystąpi rozbieżność między szablonem profilu certyfikatu firmy DigiCert a profilem certyfikatu usługi Intune. Ten problem wynika najprawdopodobniej z niezgodności atrybutów **SubjectName** lub **SubjectAltName**. <br><br> Aby rozwiązać ten problem, wybierz wartości obsługiwane przez usługę Intune dla atrybutów **SubjectName** i **SubjectAltName** w szablonie profilu certyfikatu firmy DigiCert. Aby uzyskać więcej informacji, zobacz atrybuty obsługiwane przez usługę Intune w sekcji **Parametry certyfikatu**. |
| Niektóre urządzenia użytkownika nie odbierają certyfikatów PKCS z urzędu certyfikacji firmy DigiCert. | Ten problem występuje, jeśli nazwa UPN użytkownika zawiera znaki specjalne, np. podkreślenie (przykład: `global_admin@intune.onmicrosoft.com`). <br><br> Urząd certyfikacji firmy DigiCert nie obsługuje znaków specjalnych w typach **mail_firstname** i **mail_lastname**. <br><br> Aby rozwiązać ten problem, wykonaj następujące czynności: <br><br> 1. Zaloguj się do portalu administracyjnego urzędu certyfikacji DigiCert. <br> 2. Przejdź do pozycji **Manage Certificate Profiles** (Zarządzaj profilami certyfikatów). <br> 3. Kliknij profil certyfikatu używany dla usługi Intune. <br> 4. Kliknij link **Customize options** (Dostosuj opcje). <br> 5. Kliknij przycisk **Advanced options** (Opcje zaawansowane). <br> 6. W obszarze **Certificate fields – Subject DN** (Pola certyfikatu — nazwa wyróżniająca podmiotu) dodaj pole **Common Name (CN)** (Nazwa pospolita (CN)) i usuń istniejące pole **Common Name (CN)** (Nazwa pospolita (CN)). Dodawanie i usuwanie musi być wykonywane jednocześnie. <br> 7. Wybierz pozycję **Zapisz**. <br><br> Po wykonaniu powyższej zmiany profil certyfikatu firmy DigiCert żąda typu **„CN=<upn>”** zamiast typów **mail_firstname** i **mail_lastname**. |
| Użytkownik ręcznie usunął już wdrożony certyfikat z urządzenia. | Usługa Intune ponownie wdraża ten sam certyfikat podczas następnego zaewidencjonowania lub wymuszania zasad. W takim przypadku łącznik usługi NDES nie odbiera żądania certyfikatu PKCS. |

## <a name="next-steps"></a>Następne kroki

Informacje zawarte w tym artykule oraz w temacie [Co to są profile urządzeń w usłudze Microsoft Intune?](../configuration/device-profiles.md) są przydatne podczas zarządzania urządzeniami w organizacji oraz ich certyfikatami.

