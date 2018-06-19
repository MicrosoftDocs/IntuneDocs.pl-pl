---
title: Wystawianie certyfikatów PKCS firmy Symantec w usłudze Microsoft Intune
titlesuffix: ''
description: Instalacja i konfiguracja łącznika certyfikatów usługi Intune w celu wystawiania certyfikatów PKCS przy użyciu usługi internetowej Symantec PKI Manager dla urządzeń zarządzanych przez usługę Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d9c9027964648ad83c552f7dd7067598cacf560e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31836529"
---
# <a name="set-up-intune-certificate-connector-for-symantec-pki-manager-web-service"></a>Konfiguracja łącznika certyfikatów usługi Intune dla usługi sieci Web Symantec PKI Manager

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule przedstawiono, jak zainstalować i skonfigurować łącznik certyfikatów usługi Intune, aby wystawiać certyfikaty PKCS przy użyciu usługi sieci Web Symantec PKI Manager dla urządzeń zarządzanych przez usługę Intune.

W tym artykule usługa sieci Web Symantec PKI Manager jest nazywana urzędem certyfikacji firmy Symantec. Jeśli łącznik certyfikatów usługi Intune został już skonfigurowany do wystawiania certyfikatów PKCS i SCEP z urzędu certyfikacji (CA) firmy Microsoft, tego samego łącznika można użyć do konfiguracji i wystawiania certyfikatów PKCS z urzędu certyfikacji firmy Symantec. W takim przypadku łącznik certyfikatów usługi Intune może wystawić następujące certyfikaty:

* Certyfikaty PKCS z urzędu certyfikacji firmy Microsoft
* Certyfikaty SCEP z urzędu certyfikacji firmy Microsoft
* Certyfikaty PKCS z urzędu certyfikacji firmy Symantec

Jeśli chcesz użyć Łącznika certyfikatów usługi Intune dla urzędów certyfikacji firm Microsoft i Symantec, musisz najpierw skonfigurować ten łącznik dla urzędu certyfikacji firmy Microsoft, a następnie wykonać czynności podane poniżej, aby skonfigurować go dla urzędu certyfikacji firmy Symantec.  Aby uzyskać więcej szczegółowych informacji dotyczących konfigurowania łącznika certyfikatów usługi Intune, zobacz temat [Jak skonfigurować certyfikaty w usłudze Microsoft Intune](certificates-configure.md).

## <a name="prepare-to-install-intune-certificate-connector"></a>Przygotowanie do instalacji łącznika certyfikatów usługi Intune

Jeśli korzystasz już z łącznika certyfikatów usługi Intune dla istniejącego urzędu certyfikacji firmy Microsoft i chcesz dodać obsługę urzędu certyfikacji firmy Symantec, pomiń ten krok i wykonaj pozostałe czynności po zainstalowaniu najnowszego łącznika certyfikatów usługi Intune z portalu administracyjnego usługi Intune. Ten krok jest wymagany tylko wtedy, gdy chcesz używać łącznika certyfikatów usługi Intune na potrzeby autonomicznego urzędu certyfikacji firmy Symantec.

1. Wybierz jedną z wersji systemu operacyjnego Windows z listy poniżej i zainstaluj ją na komputerze:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Utwórz użytkownika z uprawnieniami administracyjnymi i za jego pomocą wykonaj czynności podane poniżej.

3. Sprawdź najnowsze aktualizacje systemu Windows, a następnie, jeśli są dostępne, zainstaluj je.

   > [!IMPORTANT]
   > Po zainstalowaniu aktualizacji systemu Windows uruchom ponownie komputer.

4. Zainstaluj program .NET Framework 3.5:

    a. Wybierz kolejno opcje **Panel sterowania** > **Programy i funkcje** > **Włącz lub wyłącz funkcje systemu Windows**

    b. Wybierz pozycję **.NET Framework 3.5** i zainstaluj program.

## <a name="install-the-symantec-registration-authorization-certificate"></a>Instalacja certyfikatu urzędu rejestrowania firmy Symantec

Wykonaj czynności poniżej, aby pobrać certyfikat urzędu rejestrowania (RA) z urzędu certyfikacji firmy Symantec. Aby pobrać certyfikat urzędu rejestrowania, musisz mieć aktywną subskrypcję w urzędzie certyfikacji firmy Symantec.

1. Zapisz następujący fragment kodu w pliku o nazwie **certreq.ini** i zaktualizuj zgodnie z potrzebami (na przykład pozycję: *Subject name in CN format* (Nazwa podmiotu w formacie CN)).

   ```
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
   ```

2. Otwórz wiersz polecenia z podwyższonym poziomem uprawnień i wygeneruj zawartość CSR przy użyciu następującego polecenia:

   `Certreq.exe -new certreq.ini request.csr`

3. Otwórz plik request.csr w programie Notatnik i skopiuj zawartość CSR w formacie widocznym poniżej:

    ```
    -----BEGIN NEW CERTIFICATE REQUEST-----
    MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
    …
    …
    fzpeAWo=
    -----END NEW CERTIFICATE REQUEST-----
    ```

4. Zaloguj się do urzędu certyfikacji firmy Symantec i przejdź do opcji **Get an RA Cert** (Pobierz certyfikat urzędu rejestrowania) z zadań.

   a. Wklej zawartość CSR uzyskaną w kroku 3 w wyznaczonym polu tekstowym.

   b. Wpisz przyjazną nazwę certyfikatu w wyznaczonym polu tekstowym.

   c. Kliknij przycisk **Kontynuuj**.

      Zostanie wyświetlony link do pobrania certyfikatu urzędu rejestrowania.

   d. Pobierz certyfikat urzędu rejestrowania na komputer lokalny.

5. Zaimportuj certyfikat urzędu rejestrowania do magazynu certyfikatów systemu Windows:

    a. Otwórz konsolę MMC.

    b. Kliknij kolejno opcje **Plik** > **Dodawanie lub usuwanie przystawek** > **Certyfikat**, a następnie kliknij przycisk **Dodaj**.

    c. Wybierz opcję **Konto komputera**, a następnie kliknij przycisk **Dalej**.

    d. Wybierz opcję **Komputer lokalny**, a następnie kliknij przycisk **Zakończ**.

    e. Kliknij przycisk **OK** w oknie **Dodawanie lub usuwanie przystawek**. Rozwiń węzeł **Certyfikaty (Komputer lokalny)** > **Osobiste** > **Certyfikaty**.

    f. Kliknij prawym przyciskiem myszy węzeł **Certyfikaty**, a następnie wybierz kolejno opcje **Wszystkie zadania** > **Importuj**.

    g. Wybierz lokalizację certyfikatu urzędu rejestrowania pobranego z urzędu certyfikacji firmy Symantec i kliknij przycisk **Dalej**.

    h. Wybierz opcję **Osobisty magazyn certyfikatów**, a następnie kliknij przycisk **Dalej**.

    i. Kliknij przycisk **Finish** (Zakończ). Certyfikat urzędu rejestrowania zostanie zaimportowany do magazynu Komputer lokalny-Osobiste wraz z kluczem prywatnym.  

6. Wyeksportuj i zaimportuj certyfikat klucza prywatnego:

    a. Rozwiń węzeł **Certyfikaty (Komputer lokalny)** > **Osobiste** > **Certyfikaty**.

    b. Wybierz certyfikat, który został zaimportowany w poprzednim kroku.

    c. Kliknij prawym przyciskiem myszy certyfikat i wybierz kolejno opcje **Wszystkie zadania** > **Eksportuj**.

    d. Kliknij przycisk **Dalej** i wpisz hasło.

    e. Wybierz lokalizację eksportu i kliknij przycisk **Zakończ**.

    f. Wykonaj tę samą procedurę w kroku 5, aby zaimportować certyfikat klucza prywatnego do magazynu Komputer lokalny-Osobiste.

7. Skopiuj odcisk palca certyfikatu urzędu rejestrowania bez żadnych spacji.  Poniżej przedstawiono przykładowy odcisk palca:

   ```
   RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
   ```


   > [!NOTE]
   > Jeśli wystąpią problemy z pobraniem certyfikatu urzędu rejestrowania z urzędu certyfikacji firmy Symantec, skontaktuj się z pomocą techniczną firmy Symantec.

## <a name="install-intune-certificate-connector"></a>Instalacja łącznika certyfikatów usługi Intune

Jeśli już używasz najnowszego łącznika certyfikatów usługi Intune dla istniejącego urzędu certyfikacji firmy Microsoft i chcesz dodać obsługę urzędu certyfikacji firmy Symantec, pomiń ten krok. W przeciwnym razie pobierz najnowszy łącznik certyfikatów usługi Intune z portalu administracyjnego usługi Intune i wykonaj poniższe instrukcje.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzenia**.
4. W okienku **Konfiguracja urządzenia** wybierz pozycję **Urząd certyfikacji**.
5. Kliknij przycisk **Dodaj**, a następnie wybierz pozycję **Pobierz plik łącznika**. Zapisz pobraną zawartość w lokalizacji dostępnej z serwera, na którym zostanie ona zainstalowana. 
3. Uruchom plik NDESConnectorSetup.exe, używając podniesionego poziomu uprawnień.

    a. Na ekranie **Opcje instalacji** wybierz opcję **PFX Distribution** (Dystrybucja PFX), jak przedstawiono na zrzucie ekranu poniżej.  Wykonaj pozostałe czynności wymagane podczas konfiguracji, używając ustawień domyślnych.

   > [!IMPORTANT]
   > Jeśli chcesz skonfigurować łącznik certyfikatów usługi Intune do wystawiania certyfikatów z urzędu certyfikacji firmy Microsoft CA oraz urzędu certyfikacji firmy Symantec, wybierz opcję **Opis profilów SCEP i PFX**. Wykonaj pozostałe czynności wymagane podczas konfiguracji, używając ustawień domyślnych.

   ![InstallConnector][InstallConnector]
 
## <a name="configure-intune-certificate-connector"></a>Konfiguracja łącznika certyfikatów usługi Intune

Łącznik certyfikatów usługi Intune jest domyślnie instalowany w katalogu `%ProgramFiles%\Microsoft Intune`.

1. Otwórz plik %ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config w programie Notatnik.

    a. Zaktualizuj wartość klucza RACertThumbprint do wartości odcisku palca certyfikatu skopiowanej w poprzedniej sekcji.  Poniżej przedstawiono przykład:

   ```
   <add key="RACertThumbprint"
   value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   ```

    b. Zapisz i zamknij plik.

2. Otwórz plik services.msc.

    a. Wybierz opcję **Usługa łącznika usługi Intune**.

    b. Zatrzymaj usługę, a następnie uruchom usługę.

    c. Zamknij okno Usługi.

## <a name="setup-the-intune-administrator-account"></a>Konfiguracja konta administratora usługi Intune

Jeśli używasz już łącznika certyfikatów usługi Intune dla istniejącego urzędu certyfikacji firmy Microsoft i chcesz dodać obsługę urzędu certyfikacji firmy Symantec, pomiń ten krok i wykonaj pozostałe czynności. 

1. Uruchom interfejs użytkownika łącznika usługi NDES z pliku ` %ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe `

    a. Kliknij kartę **Rejestracja**, a następnie kliknij przycisk **Zaloguj**.

    b. Podaj poświadczenia administratora dzierżawy usługi Intune w wyznaczonych polach tekstowych.

    c. Kliknij przycisk **Zaloguj**.  Zostanie wyświetlone okno dialogowe potwierdzenia zawierające komunikat **Zarejestrowano pomyślnie**, jak pokazano na zrzucie ekranu poniżej.
2. Zamknij interfejs użytkownika łącznika usługi NDES.

![ConfigureConnector][ConfigureConnector]
 
## <a name="create-a-trusted-certificate-profile"></a>Tworzenie profilu zaufanego certyfikatu

Certyfikaty PKCS wdrożone dla urządzeń zarządzanych przez usługę Intune muszą być powiązane przy użyciu zaufanego certyfikatu głównego. Należy utworzyć profil zaufanego certyfikatu usługi Intune przy użyciu certyfikatu głównego uzyskanego z urzędu certyfikacji firmy Symantec.

1. Pobierz zaufany certyfikat główny z urzędu certyfikacji firmy Symantec:

    a. Zaloguj się do portalu administracyjnego urzędu certyfikacji firmy Symantec.

    b. Kliknij opcję Manage CAs (Zarządzaj urzędami certyfikacji) w obszarze Tasks (Zadania):

    c. Wybierz odpowiedni urząd certyfikacji z listy urzędów certyfikacji.

    d. Kliknij opcję Download root certificate (Pobierz certyfikat główny), aby pobrać zaufany certyfikat główny.

2. Utwórz profil zaufanego certyfikatu w portalu administracyjnym usługi Intune:

    a. Zaloguj się do witryny [Azure Portal](https://portal.azure.com) przy użyciu poświadczeń administratora dzierżawy usługi Intune i wyszukaj zasoby usługi Intune.

    b. Utwórz profil zaufanego certyfikatu, wybierając kolejno opcje **Microsoft Intune** > **Konfiguracja urządzenia** > **Profile**  > **Utwórz profil**.

    c. Podaj wymagane informacje w polach **Nazwa** i **Opis**, a następnie wybierz platformę docelową. 

    d. Z listy rozwijanej Typ profilu wybierz opcję Profil zaufanego certyfikatu.

    e. Przekaż zaufany certyfikat główny uzyskany z urzędu certyfikacji firmy Symantec w poprzednim kroku.

    f. Wykonaj pozostałe czynności wymagane podczas tworzenia profilu. 

    g. Kliknij opcję **Przypisania** i wybierz odpowiednią grupę.  Do przypisanej grupy musi należeć co najmniej jeden użytkownik lub jedno urządzenie.

## <a name="get-the-certificate-profile-oid"></a>Pobieranie identyfikatora OID profilu certyfikatu

Identyfikator OID profilu certyfikatu jest skojarzony z szablonem profilu certyfikatu w urzędzie certyfikacji firmy Symantec.  Aby utworzyć profil certyfikatu PKCS w portalu administracyjnym usługi Intune, należy podać nazwę szablonu certyfikatu w formie identyfikatora OID profilu certyfikatu, który jest skojarzony z szablonem certyfikatu w urzędzie certyfikacji firmy Symantec.

1. Zaloguj się do portalu administracyjnego urzędu certyfikacji firmy Symantec.
2. Kliknij opcję Manage Certificate Profiles (Zarządzaj profilami certyfikatów).
3. Wybierz profil certyfikatu, którego chcesz użyć.
4. Skopiuj identyfikator OID profilu certyfikatu. Będzie on podobny do poniższego przykładu:

   ```
   Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
   ```

   > [!NOTE]
   > Jeśli występują problemy z uzyskaniem identyfikatora OID profilu certyfikatu, skontaktuj się z pomocą techniczną firmy Symantec.

## <a name="create-a-pkcs-certificate-profile"></a>Tworzenie profilu certyfikatu PKCS

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com) przy użyciu poświadczeń administratora dzierżawy usługi Intune i wyszukaj zasoby usługi Intune.
2. Utwórz profil certyfikatu PKCS, wybierając kolejno opcje **Microsoft Intune** > **Konfiguracja urządzeń > Profile** > **Utwórz profil**.

    a. Podaj wymagane informacje w polach **Nazwa** i **Opis**, a następnie wybierz platformę docelową.

    b. Z listy rozwijanej **Typ profilu** wybierz opcję **Profil certyfikatu PKCS**.  

    c. Wykonaj pozostałe czynności, aby utworzyć profil.

   ![ConfigureProfile][ConfigureProfile]

   > [!IMPORTANT]
   > Następujące parametry profilu certyfikatu PKCS muszą być skonfigurowane przy użyciu określonych wartości z tabeli poniżej, jak pokazano na zrzucie ekranu, aby można było wystawiać certyfikaty PKCS za pośrednictwem łącznika certyfikatów usługi Intune z urzędu certyfikacji firmy Symantec. 

    |Parametr certyfikatu PKCS | Wartość | Opis |
    | --- | --- | --- |
    | Urząd certyfikacji | pki-ws.symauth.com | Ta wartość musi być nazwą FQDN usługi podstawowej urzędu certyfikacji firmy Symantec bez końcowych ukośników.  Jeśli nie masz pewności, czy jest to prawidłowa nazwa FQDN usługi podstawowej dla Twojej subskrypcji urzędu certyfikacji firmy Symantec, skontaktuj się z pomocą techniczną firmy Symantec. <br><br> Jeśli ta nazwa FQDN będzie niepoprawna, łącznik certyfikatów usługi Intune nie będzie wystawiać certyfikatów PKCS z urzędu certyfikacji firmy Symantec.| 
    | Nazwa urzędu certyfikacji | Symantec | Ta wartość musi być ciągiem **Symantec**. <br><br> Jeśli ta wartość zostanie zmieniona, łącznik certyfikatów usługi Intune nie będzie wystawiać certyfikatów PKCS z urzędu certyfikacji firmy Symantec.|
    | Nazwa szablonu certyfikatu | Identyfikator OID profilu certyfikatu z urzędu certyfikacji firmy Symantec. <br><br> Przykład: `2.16.840.1.113733.1.16.1.2.3.1.1.61904612`| Tą wartością musi być identyfikator OID profilu certyfikatu uzyskany w poprzedniej sekcji z szablonu profilu certyfikatu urzędu certyfikacji firmy Symantec. <br><br> Jeśli łącznik certyfikatów usługi Intune nie będzie mógł odnaleźć szablonu certyfikatu skojarzonego z tym identyfikatorem OID profilu certyfikatu w urzędzie certyfikacji firmy Symantec, nie będzie wystawiać certyfikatów PKCS z urzędu certyfikacji firmy Symantec.|

   > [!NOTE]
   > Profile certyfikatu PKCS dla platform systemu Windows nie muszą być skojarzone z profilem zaufanego certyfikatu. Jest to jednak wymagane dla profilów platform innych niż system Windows, np. dla systemu Android.

3. Kliknij opcję **Przypisania** i wybierz odpowiednią grupę.  Do przypisanej grupy musi należeć co najmniej jeden użytkownik lub jedno urządzenie.
 
Po wykonaniu poprzednich kroków łącznik certyfikatów usługi Intune będzie wystawiać certyfikaty PKCS z urzędu certyfikacji firmy Symantec dla urządzeń zarządzanych przez usługę Intune w przypisanej grupie. Te certyfikaty będą dostępne w magazynie osobistym magazynu certyfikatów bieżącego użytkownika na urządzeniu zarządzanym przez usługę Intune.

### <a name="pkcs-certificate-profile-supported-attributes"></a>Obsługiwane atrybuty profilu certyfikatu PKCS

|Atrybut | Formaty obsługiwane przez usługę Intune | Formaty obsługiwane przez urząd certyfikacji w chmurze firmy Symantec | Result |
| --- | --- | --- | --- |
| Nazwa podmiotu |Usługa Intune obsługuje nazwę podmiotu tylko w trzech formatach podanych poniżej: <br><br> 1. Nazwa pospolita <br> 2. Nazwa pospolita zawierająca adres e-mail <br> 3. Nazwa pospolita będąca adresem e-mail <br><br> Poniżej przedstawiono przykład: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | Urząd certyfikacji firmy Symantec obsługuje dodatkowe atrybuty.  Jeśli chcesz wybrać dodatkowe atrybuty, muszą one być zdefiniowane przy użyciu stałych wartości w szablonie profilu certyfikatu firmy Symantec.| Używamy nazwy pospolitej lub adresu e-mail z żądania certyfikatu PKCS. <br><br> Wszelkie niezgodności w wyborze atrybutów występujące między profilem certyfikatu usługi Intune i szablonem profilu certyfikatu firmy Symantec powodują, że z urzędu certyfikacji firmy Symantec nie zostają wystawione żadne certyfikaty.|
| SAN | Usługa Intune obsługuje tylko następujące wartości pola SAN: <br><br> AltNameTypeEmail <br><br> AltNameTypeUpn <br><br> AltNameTypeOtherName (wartość zakodowana) | Urząd certyfikacji w chmurze firmy Symantec również obsługuje te parametry. Jeśli chcesz wybrać dodatkowe atrybuty, muszą one być zdefiniowane przy użyciu stałych wartości w szablonie profilu certyfikatu firmy Symantec. <br><br> AltNameTypeEmail: jeśli ten typ nie zostanie odnaleziony w nazwie SAN, zostanie użyta wartość z AltNameTypeUpn.  Jeśli typ AltNameTypeUpn również nie zostanie odnaleziony w nazwie SAN, zostanie użyta wartość parametru Nazwa podmiotu, o ile jest w formacie adresu e-mail.  Jeśli wartość nadal nie zostanie odnaleziona, łącznik certyfikatów usługi Intune nie będzie mógł wystawiać certyfikatów. <br><br> Przykład: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> AltNameTypeUpn: jeśli ten typ nie zostanie odnaleziony w nazwie SAN, zostanie użyta wartość z AltNameTypeEmail. Jeśli typ AltNameTypeEmail również nie zostanie odnaleziony w nazwie SAN, zostanie użyta wartość parametru Nazwa podmiotu, o ile jest w formacie adresu e-mail.  Jeśli wartość nadal nie zostanie odnaleziona, łącznik certyfikatów usługi Intune nie będzie mógł wystawiać certyfikatów.  <br><br> Przykład: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> AltNameTypeOtherName: jeśli ten typ nie zostanie odnaleziony w nazwie SAN, łącznik certyfikatów usługi Intune nie będzie mógł wystawiać certyfikatów. <br><br> Przykład: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  **Ważna informacja:** Wartość tego pola jest obsługiwana przez urząd certyfikacji firmy Symantec tylko w formacie zakodowanym (wartość szesnastkowa). Tak więc dla wszystkich wartości w tym polu łącznik certyfikatów usługi Intune konwertuje ją na wartość szyfrowaną algorytmem Base-64 przed przesłaniem żądania certyfikatu. **Łącznik certyfikatów usługi Intune nie weryfikuje, czy ta wartość jest już zaszyfrowana czy nie.** | Brak |

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Dzienniki usługi łącznika certyfikatów usługi Intune są dostępne w katalogu `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs` na maszynie łącznika usługi NDES. Otwórz dzienniki w programie [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) i wyszukaj wyjątek lub komunikaty o błędach.

| Problem/Komunikat o błędzie | Kroki umożliwiające rozwiązanie problemów |
| --- | --- |
| Nie można zalogować się do konta administratora dzierżawcy usługi Intune w interfejsie użytkownika łącznika usługi NDES | Może się to zdarzyć, gdy lokalny łącznik certyfikatów nie został włączony w portalu administracyjnym usługi Intune. Aby rozwiązać ten problem, wykonaj następujące czynności: <br><br> W interfejsie użytkownika programu Silverlight : <br> 1. Zaloguj się do [portalu administracyjnego usługi Intune](https://admin.manage.microsoft.com). <br> 2. Kliknij przycisk ADMINISTRATOR. <br> 3. Wybierz kolejno opcje Zarządzanie urządzeniami przenośnymi > Łącznik certyfikatów. <br> 4. Kliknij opcję **Skonfiguruj lokalny łącznik certyfikatów**. <br> 5. Zaznacz pole wyboru **Włącz łącznik certyfikatów**. <br> 6. Kliknij przycisk **OK**. <br><br>lub <br><br> W interfejsie użytkownika witryny Azure Portal: <br> 1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com) <br> 2. Przejdź do usługi Microsoft Intune <br> 3. Wybierz kolejno opcje **Konfiguracja urządzeń** > **Urząd certyfikacji** <br> 4. Kliknij przycisk **Włącz**. <br><br> Po wykonaniu poprzednich kroków w interfejsie użytkownika programu Silverlight lub w witrynie Azure Portal spróbuj zalogować się do tego samego konta administratora dzierżawy usługi Intune w interfejsie użytkownika łącznika usługi NDES. |
| Nie można odnaleźć certyfikatu łącznika usługi NDES. <br><br> System.ArgumentNullException: Wartość nie może być zerowa. | Łącznik certyfikatów usługi Intune wyświetla ten błąd, jeśli konto administratora dzierżawy usługi Intune nigdy nie zostało użyte do logowania do interfejsu użytkownika łącznika usługi NDES. <br><br> Jeśli ten błąd będzie nadal występować, uruchom ponownie usługę łącznika usługi Intune. <br><br> 1. Otwórz plik services.msc. <br> 2. Wybierz opcję **Usługa łącznika usługi Intune**. <br> 3. Kliknij prawym przyciskiem myszy i wybierz polecenie **Uruchom ponownie**.|
| Łącznik usługi NDES — IssuePfx — Wyjątek ogólny: <br> System.NullReferenceException: Odwołanie do obiektu nie jest ustawione na wystąpienie obiektu. | Ten błąd jest przejściowy. Uruchom ponownie usługę łącznika usługi Intune. <br><br> 1. Otwórz plik services.msc. <br> 2. Wybierz opcję **Usługa łącznika usługi Intune**. <br> 3. Kliknij prawym przyciskiem myszy i wybierz polecenie **Uruchom ponownie**. |
| Dostawca firmy Symantec — nie można pobrać zasad firmy Symantec „Przekroczono limit czasu operacji” | Łącznik certyfikatów usługi Intune odebrał błąd limitu czasu operacji podczas komunikacji z urzędem certyfikacji firmy Symantec. Jeśli ten błąd będzie nadal występować, zwiększ wartość limitu czasu połączenia i spróbuj ponownie. <br><br> Aby zwiększyć limit czasu połączenia: <br> 1. Przejdź do komputera łącznika usługi NDES. <br>2. Otwórz plik `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config` w programie Notatnik. <br> 3. Zwiększ wartość limitu czasu dla następującego parametru: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Uruchom ponownie usługę łącznika usługi Intune. <br><br> Jeśli problem będzie nadal występować, skontaktuj się z pomocą techniczną firmy Symantec. |
| Dostawca firmy Symantec — nie można pobrać certyfikatu klienta. | Łącznik certyfikatów usługi Intune nie może pobrać certyfikatu autoryzacji zasobów z magazynu certyfikatów Komputer lokalny-Osobiste. Aby rozwiązać ten problem, zainstaluj certyfikat autoryzacji zasobów w magazynie certyfikatów Komputer lokalny-Osobiste wraz z kluczem prywatnym. <br><br> **Uwaga:** Certyfikat autoryzacji zasobów musi pochodzić od urzędu certyfikacji firmy Symantec. Aby uzyskać więcej szczegółowych informacji, skontaktuj się z pomocą techniczną firmy Symantec. | 
| Dostawca firmy Symantec — nie można pobrać zasad firmy Symantec „Żądanie zostało przerwane: nie można utworzyć bezpiecznego kanału SSL/TLS.” | Ten błąd występuje w następujących scenariuszach: <br><br> 1. Usługa łącznika certyfikatów usługi Intune nie ma wystarczających uprawnień do odczytu certyfikatu autoryzacji zasobów wraz z kluczem prywatnym z magazynu certyfikatów Komputer lokalny-Osobiste. Aby rozwiązać ten problem, sprawdź konto kontekstu, w którym jest uruchomiona usługa łącznika, w pliku services.msc. Usługa łącznika musi zostać uruchomiona w kontekście NT AUTHORITY\SYSTEM. <br><br> 2. Profil certyfikatu PKCS w portalu administracyjnym usługi Intune może być skonfigurowany przy użyciu nieprawidłowej nazwy FQDN usługi podstawowej urzędu certyfikacji firmy Symantec. Nazwa FQDN powinna być podobna do następującej: `pki-ws.symauth.com`. Aby rozwiązać ten problem, skontaktuj się z pomocą techniczną firmy Symantec i sprawdź, czy adres URL jest poprawny dla Twojej subskrypcji. <br><br> 3. Łącznik certyfikatów usługi Intune nie może uwierzytelniać przy użyciu urzędu certyfikacji firmy Symantec korzystającego z certyfikatu autoryzacji zasobów, ponieważ nie może pobrać jego klucza prywatnego. Aby rozwiązać ten problem, zainstaluj certyfikat autoryzacji zasobów wraz z kluczem prywatnym w magazynie certyfikatów Komputer lokalny-Osobiste. <br><br> Jeśli problem będzie nadal występować, skontaktuj się z pomocą techniczną firmy Symantec. |
| Dostawca firmy Symantec — nie można pobrać zasad firmy Symantec „Element żądania nie został zrozumiany.” | Łącznik certyfikatów usługi Intune nie może pobrać szablonu profilu certyfikatu firmy Symantec, ponieważ identyfikator OID profilu klienta nie jest zgodny z profilem certyfikatu usługi Intune. Może być też tak, że łącznik certyfikatów usługi Intune nie może odnaleźć szablonu profilu certyfikatu skojarzonego z danym identyfikatorem OID profilu klienta w urzędzie certyfikacji firmy Symantec. <br><br> Aby rozwiązać ten problem, uzyskaj prawidłowy identyfikator OID profilu klienta z szablonu certyfikatu firmy Symantec w urzędzie certyfikacji firmy Symantec. Następnie zaktualizuj profil certyfikatu PKCS w portalu administracyjnym usługi Intune. <br><br> Uzyskaj identyfikator OID profilu klienta z urzędu certyfikacji firmy Symantec: <br> 1. Zaloguj się do portalu administracyjnego urzędu certyfikacji firmy Symantec. <br> 2. Kliknij opcję Manage Certificate Profiles (Zarządzaj profilami certyfikatów). <br> 3. Wybierz profil certyfikatu, którego zamierzasz używać. <br> 4. Pobierz identyfikator OID profilu certyfikatu. Będzie on podobny do poniższego przykładu: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Zaktualizuj profil certyfikatu PKCS przy użyciu poprawnego identyfikatora OID profilu certyfikatu: <br>1. Zaloguj się do portalu administracyjnego usługi Intune. <br> 2. Przejdź do profilu certyfikatu PKCS i kliknij przycisk **Edytuj**. <br> 3. Zaktualizuj identyfikator OID profilu certyfikatu w aktualizacji w polu nazwy szablonu certyfikatu. <br> 4. Zapisz profil certyfikatu PKCS. |
| Dostawca firmy Symantec — nie można zweryfikować zasad. <br><br> Atrybut nie występuje na liście atrybutów szablonu certyfikatu obsługiwanych przez firmę Symantec. | Urząd certyfikacji firmy Symantec wyświetla ten komunikat, jeśli wystąpi rozbieżność między szablonem profilu certyfikatu firmy Symantec a profilem certyfikatu usługi Intune. Ten problem wynika najprawdopodobniej z niezgodności wartości atrybutów SubjectName lub SubjectAltName. <br><br> Aby rozwiązać ten problem, wybierz wartości obsługiwane przez usługę Intune dla atrybutów SubjectName i SubjectAltName w szablonie profilu certyfikatu firmy Symantec. Aby uzyskać więcej informacji, zobacz atrybuty obsługiwane przez usługę Intune w sekcji dotyczącej parametrów certyfikatu. |
| Niektóre urządzenia użytkownika nie odbierają certyfikatów PKCS z urzędu certyfikacji firmy Symantec. | Ten problem występuje, jeśli nazwa UPN użytkownika zawiera znaki specjalne, np. podkreślenie (przykład: `global_admin@intune.onmicrosoft.com`). <br><br> Urząd certyfikacji firmy Symantec nie obsługuje znaków specjalnych w typie mail_firstname i mail_lastname. <br><br> Aby rozwiązać ten problem, wykonaj następujące czynności: <br><br> 1.   Zaloguj się do portalu administracyjnego urzędu certyfikacji firmy Symantec. <br> 2. Przejdź do opcji Manage Certificate Profiles (Zarządzaj profilami certyfikatów). <br> 3.   Kliknij profil certyfikatu używany dla usługi Intune. <br> 4.  Kliknij link Customize options (Dostosuj opcje). <br> 5.   Kliknij przycisk Advanced options (Opcje zaawansowane). <br> 6.  W obszarze Certificate fields (Pola certyfikatu) — Subject DN (Nazwa wyróżniająca podmiotu) dodaj pole Common Name (CN) (Nazwa pospolita (CN)) i usuń istniejące pole Common Name (CN) (Nazwa pospolita (CN)). Dodawanie i usuwanie musi być wykonywane jednocześnie. <br> 7.    Kliknij przycisk Zapisz. <br><br> Po wykonaniu powyższej zmiany profil certyfikatu firmy Symantec żąda typu „CN=<upn>” zamiast mail_firstname i mail_lastname. |
| Użytkownik ręcznie usunął już wdrożony certyfikat z urządzenia. | Usługa Intune ponownie wdraża ten sam certyfikat podczas następnego zaewidencjonowania lub wymuszania zasad. W takim przypadku łącznik usługi NDES nie odbiera żądania certyfikatu PKCS. |

## <a name="next-steps"></a>Następne kroki

- Informacje zawarte w tym artykule oraz w temacie [Co to są profile urządzeń w usłudze Microsoft Intune?](device-profiles.md) są przydatne podczas zarządzania urządzeniami w organizacji oraz ich certyfikatami.

[InstallConnector]:  ./media/certificates-symantec-connector-install.png "Instalowanie łącznika certyfikatów usługi Intune i wybieranie opcji dystrybucji PFX"
[ConfigureConnector]: ./media/certificates-symantec-configure-connector-configure.png "Konfiguracja łącznika certyfikatów usługi Intune"
[ConfigureProfile]: ./media/certificates-symantec-pkcs-example.png "Tworzenie profilu certyfikatu PKCS w portalu Azure"
