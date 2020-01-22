---
title: Korzystanie z zaimportowanych certyfikatów PFX w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zaimportowane certyfikaty standardów kryptografii klucza publicznego (PKCS) są używane w usłudze Microsoft Intune w celu importowania certyfikatów, konfigurowania szablonu certyfikatu, instalacji łącznika zaimportowanego certyfikatu PFX usługi Intune i utworzenia zaimportowanego pliku PKCS profilu certyfikatu.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda; rimarram
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1bad86e561c8695d58296c8f473815a203ef210a
ms.sourcegitcommit: 665be113b593c3bc7d46b99599e720f781037dcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2020
ms.locfileid: "76258493"
---
# <a name="configure-and-use-imported-pkcs-certificates-with-intune"></a>Konfigurowanie zaimportowanych certyfikatów PKCS i korzystanie z nich w usłudze Intune

Microsoft Intune obsługuje zaimportowane certyfikaty pary kluczy publicznych (PKCS), powszechnie używane do szyfrowania S/MIME z profilami poczty e-mail. Niektóre profile poczty e-mail w usłudze Intune obsługują opcję włączenia protokołu S/MIME, w której można zdefiniować certyfikat podpisywania S/MIME i certyfikat szyfrowania S/MIME.

Szyfrowanie S/MIME jest trudne, ponieważ poczta e-mail jest szyfrowana przy użyciu określonego certyfikatu. Musisz mieć klucz prywatny certyfikatu, który zaszyfrował wiadomość e-mail na urządzeniu, na którym odczytujesz wiadomość e-mail, aby można było ją odszyfrować. Certyfikaty szyfrowania są regularnie odnawiane, co oznacza, że do odczytania starszych wiadomości e-mail może być potrzebna historia szyfrowania na wszystkich urządzeniach.  Ponieważ na obu urządzeniach musi być użyty ten sam certyfikat, nie można użyć do tego celu profilu certyfikatu [SCEP](certificates-scep-configure.md) ani [PKCS](certficates-pfx-configure.md), ponieważ te mechanizmy dostarczania certyfikatów dostarczają unikatowy certyfikat do każdego urządzenia.

Więcej informacji o korzystaniu z protokołu S/MIME w usłudze Intune — zobacz [Korzystanie z protokołu S/MIME do szyfrowania poczty e-mail](certificates-s-mime-encryption-sign.md).

## <a name="requirements"></a>Wymagania

Aby korzystać z zaimportowanych certyfikatów PKCS w usłudze Intune, musisz mieć następującą infrastrukturę:

- **Łącznik certyfikatów PFX dla usługi Microsoft Intune**:

  Każda dzierżawa usługi Intune obsługuje pojedyncze wystąpienie tego łącznika. Możesz zainstalować ten łącznik na tym samym serwerze jako wystąpienie łącznika certyfikatu usługi Microsoft Intune.

  Ten łącznik obsługuje żądania dotyczące plików PFX zaimportowanych do usługi Intune na potrzeby szyfrowania wiadomości e-mail za pomocą protokołu S/MIME dla określonego użytkownika.

  Ten łącznik może zaktualizować się automatycznie po udostępnieniu nowej wersji. Aby skorzystać z tej funkcji, upewnij się, że zapory są otwarte i umożliwiają łącznikowi komunikację z hostem **autoupdate.msappproxy.net** na porcie **443**.

  Więcej informacji o wszystkich punktach końcowych sieci, do których uzyskuje dostęp łącznik — zobacz [Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune](../fundamentals/network-bandwidth-use.md).

- **Windows Server**:

  używasz systemu Windows Server do hostowania programu Łącznik certyfikatów PFX dla usługi Microsoft Intune.  Łącznik służy do przetwarzania żądań dotyczących certyfikatów zaimportowanych do usługi Intune.

  W usłudze Intune możesz zainstalować oba łączniki (*Łącznik certyfikatów usługi Microsoft Intune* i *Łącznik certyfikatów PFX dla usługi Microsoft Intune*) na tym samym serwerze.

  Aby można było obsługiwać łącznik, na serwerze musi być zainstalowany program .NET Framework w wersji 4.6 lub nowszej. Jeśli program .NET Framework 4.6 nie jest zainstalowany, instalator łącznika zainstaluje go automatycznie.

- **Visual Studio 2015 lub nowszy** (opcjonalnie):

  Program Visual Studio służy do kompilowania modułu pomocnika programu PowerShell za pomocą poleceń cmdlet do importowania certyfikatów PFX do usługi Microsoft Intune. Aby uzyskać polecenia cmdlet pomocnika programu PowerShell, zobacz [Projekt PFXImport PowerShell w usłudze GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="how-it-works"></a>Jak to działa

W przypadku korzystania z usługi Intune do wdrażania **zaimportowanego certyfikatu PFX** dla użytkownika, poza urządzeniem w grę wchodzą dwa składniki:

- **Usługa Intune**: Przechowuje zaszyfrowane certyfikaty PFX i obsługuje wdrożenie certyfikatu na urządzeniu użytkownika.  Hasła chroniące klucze prywatne certyfikatów są przed przekazaniem szyfrowane za pomocą sprzętowego modułu zabezpieczeń (HSM) lub kryptografii systemu Windows, aby usługa Intune w żadnym razie nie mogła uzyskać dostępu do kluczy prywatnych.

- **Łącznik certyfikatów PFX dla usługi Microsoft Intune**: Gdy urządzenie wymaga certyfikatu PFX zaimportowanego do usługi Intune, do łącznika są wysyłane: zaszyfrowane hasło, certyfikat oraz klucz publiczny urządzenia.  Łącznik odszyfrowuje hasło za pomocą lokalnego klucza prywatnego, po czym szyfruje je ponownie (wraz ze wszystkimi profilami plist w przypadku użycia systemu iOS) za pomocą klucza urządzenia i przesyła z powrotem do usługi Intune.  Usługa Intune dostarcza certyfikat do urządzenia, które może go odszyfrować za pomocą swojego klucza prywatnego i zainstalować.

## <a name="download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune"></a>Pobieranie, instalowanie i konfigurowanie programu Łącznik certyfikatów PFX dla usługi Microsoft Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Administracja dzierżawą** > **Łączniki i tokeny** > **Łączniki certyfikatu** > **Dodaj**.

   ![Pobieranie Łącznika certyfikatów dla usługi Microsoft Intune](./media/certificates-imported-pfx-configure/download-imported-pfxconnector.png)

3. Postępuj zgodnie ze wskazówkami w celu pobrania programu *Łącznik certyfikatów PFX dla usługi Microsoft Intune* do lokalizacji dostępnej z serwera, na którym ma zostać zainstalowany łącznik.

4. Po zakończeniu pobierania zaloguj się do serwera i uruchom instalator (PfxCertificateConnectorBootstrapper.exe).  
   - Po zaakceptowaniu domyślnej lokalizacji instalacji łącznik zostanie zainstalowany w ścieżce `Program Files\Microsoft Intune\PFXCertificateConnector`.
   - Usługa łącznika jest uruchamiana na koncie systemu lokalnego. Jeśli na potrzeby dostępu do Internetu jest wymagany serwer proxy, potwierdź, że konto usługi lokalnej może uzyskać dostęp do ustawień serwera proxy na serwerze.

5. Łącznik certyfikatów PFX dla usługi Microsoft Intune otwiera kartę **Rejestracja** po zakończeniu instalacji. Aby włączyć połączenie z usługą Intune, **zaloguj się** i wprowadź nazwę konta z globalnymi uprawnieniami administratora platformy Azure lub uprawnieniami administratora usługi Intune.

   > [!WARNING]
   > Domyślnie w systemie Windows Server opcja **Konfiguracja zwiększonych zabezpieczeń programu Internet Explorer** jest **włączona**,co może spowodować problemy z logowaniem do usługi Office 365.

6. Zamknij okno.

7. W centrum administracyjnym programu Microsoft Endpoint Manager wybierz pozycję **Administracja dzierżawą** > **Łączniki i tokeny** > **Łączniki certyfikatu**. Po kilku chwilach zostanie wyświetlony zielony znacznik wyboru, a stan połączenia zostanie zaktualizowany. Serwer łącznika może się teraz komunikować z usługą Intune.

## <a name="import-pfx-certificates-to-intune"></a>Importowanie certyfikatów PFX do usługi Intune

Do importowania certyfikatów PFX użytkowników do usługi Intune służy program [Microsoft Graph](https://docs.microsoft.com/graph). Pomocnik [PFXImport PowerShell Project at GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) zapewnia polecenia cmdlet ułatwiające wykonanie operacji.

Jeśli wolisz skorzystać z własnego rozwiązania w programie Graph, użyj typu zasobu [userPFXCertificate](https://docs.microsoft.com/graph/api/resources/intune-raimportcerts-userpfxcertificate?view=graph-rest-beta).

### <a name="build-pfximport-powershell-project-cmdlets"></a>Kompilowanie poleceń cmdlet „PFXImport PowerShell Project”

Aby korzystać z poleceń cmdlet programu PowerShell, należy samodzielnie skompilować projekt za pomocą programu Visual Studio. Proces jest prosty i chociaż można go uruchomić na serwerze, zalecamy uruchomienie go na stacji roboczej.  

1. Przejdź do katalogu głównego repozytorium [Intune-Resource-Access](https://github.com/microsoft/Intune-Resource-Access) w usłudze GitHub, po czym pobierz lub sklonuj repozytorium do swojego komputera za pomocą usługi Git.

   ![Przycisk pobierania w usłudze GitHub](./media/certificates-imported-pfx-configure/github-download.png)

2. Przejdź do lokalizacji `.\Intune-Resource-Access-develop\src\PFXImportPowershell\` i otwórz projekt w programie Visual Studio, korzystając z pliku **PFXImportPS.sln**.

3. W górnej części okna zmień opcję **Debug** na **Release**.

4. Przejdź do menu **Kompilacja** i wybierz opcję **Kompiluj plik PFXImportPS**. Po kilku chwilach w lewej dolnej części okna programu Visual Studio zostanie wyświetlone potwierdzenie **Kompilacja udana**.

   ![Opcja menu Kompilacja w programie Visual Studio](./media/certificates-imported-pfx-configure/vs-build-release.png)

5. Proces kompilacji tworzy nowy folder w module PowerShell w lokalizacji `.\Intune-Resource-Access-develop\src\PFXImportPowershell\PFXImportPS\bin\Release`.

   Ten folder **Release** zostanie użyty w kolejnych krokach.

### <a name="create-the-encryption-public-key"></a>Tworzenie klucza publicznego szyfrowania

Certyfikaty PFX wraz z ich kluczami publicznymi należy zaimportować do usługi Intune. Hasło chroniące klucze prywatne jest szyfrowane za pomocą przechowywanego lokalnie klucza publicznego. W celu wygenerowania i przechowywania par kluczy publiczny-prywatny można użyć kryptografii systemu Windows, sprzętowego modułu zabezpieczeń lub innego typu kryptografii.  W zależności od użytej kryptografii pary kluczy publiczny-prywatny można wyeksportować jako pliki w celu utworzenia kopii zapasowej.

Moduł PowerShell zapewnia metody tworzenia kluczy za pomocą kryptografii systemu Windows. Do utworzenia klucza można też użyć innych narzędzi.  

#### <a name="to-create-the-encryption-key-using-windows-cryptography"></a>Aby utworzyć klucz szyfrowania za pomocą kryptografii systemu Windows

1. Skopiuj folder *Release* utworzony w programie Visual Studio na serwer, na którym zainstalowano **Łącznik certyfikatów PFX dla usługi Microsoft Intune**. Ten folder zawiera moduł programu PowerShell.

2. Na serwerze otwórz program *PowerShell* jako administrator, po czym przejdź do folderu *Release* zawierającego moduł programu PowerShell.

3. Aby zaimportować moduł, uruchom polecenie `Import-Module .\IntunePfxImport.psd1`.

4. Następnie uruchom `Add-IntuneKspKey "Microsoft Software Key Storage Provider" "PFXEncryptionKey"`

   > [!TIP]
   > Użytego dostawcę należy wybrać ponownie po zaimportowaniu certyfikatów PFX. Możesz użyć **dostawcy magazynu kluczy funkcji oprogramowania Microsoft**, choć obsługiwani są również inni dostawcy. Podano również przykładową nazwę klucza; możesz użyć innej.

   Jeśli chcesz zaimportować certyfikat ze stacji roboczej, możesz wyeksportować klucz do pliku za pomocą następującego polecenia: `Export-IntunePublicKey -ProviderName "<ProviderName>" -KeyName "<KeyName>" -FilePath "<File path\Filename.PFX>"`

   Klucz prywatny należy zaimportować na serwer, na którym zainstalowano Łącznik certyfikatów PFX dla usługi Microsoft Intune, aby można było pomyślnie przetworzyć zaimportowane certyfikaty PFX.

#### <a name="to-use-a-hardware-security-module-hsm"></a>Aby skorzystać ze sprzętowego modułu zabezpieczeń (HSM)

W celu utworzenia i przechowywania pary kluczy publiczny-prywatny można użyć sprzętowego modułu zabezpieczeń (HSM). Aby uzyskać więcej informacji, zapoznaj się z dokumentacją dostawcy modułu HSM.

### <a name="import-pfx-certificates"></a>Importowanie certyfikatów PFX

Poniższy przykładowy proces importowania certyfikatów PFX korzysta z poleceń cmdlet programu PowerShell. Możesz wybrać różne opcje stosownie do swoich wymagań.

Dostępne opcje:

- Przeznaczenie (grupuje certyfikaty na podstawie znacznika):
  - nieprzypisane
  - smimeEncryption
  - smimeSigning

- Schemat uzupełniania:
  - oaepSha256
  - oaepSha384
  - oaepSha512

Wybierz dostawcę magazynu kluczy odpowiadającego dostawcy użytemu do utworzenia klucza.

#### <a name="to-import-the-pfx-certificate"></a>Aby zaimportować certyfikat PFX  

1. Wyeksportuj certyfikaty dowolnego urzędu certyfikacji (CA), wykonując instrukcje zawarte w dokumentacji dostawcy.  W przypadku Usług certyfikatów w usłudze Active Directory Microsoft możesz użyć [tego przykładowego skryptu](https://gallery.technet.microsoft.com/Export-CMPfxCertificatesFro-d55f687b).

2. Na serwerze otwórz program *PowerShell* jako administrator, po czym przejdź do folderu *Release* zawierającego moduł programu PowerShell.

3. Aby zaimportować moduł, uruchom polecenie `Import-Module .\IntunePfxImport.psd1`

4. Aby uwierzytelnić się w programie Intune Graph, uruchom polecenie `$authResult = Get-IntuneAuthenticationToken -AdminUserName "<Admin-UPN>"`

   > [!NOTE]
   > Ponieważ uwierzytelnianie przebiega w programie Graph, musisz podać uprawnienia do identyfikatora aplikacji. Jeśli jest to pierwsze użycie tego narzędzia, wymagany jest *administrator globalny*. Polecenia cmdlet programu PowerShell korzystają z tego samego identyfikatora aplikacji, którego użyto w repozytorium [powershell-intune-samples](https://github.com/microsoftgraph/powershell-intune-samples).

5. Przekonwertuj hasło dla każdego importowanego pliku PFX na bezpieczny ciąg, używając polecenia `$SecureFilePassword = ConvertTo-SecureString -String "<PFXPassword>" -AsPlainText -Force`.

6. Aby utworzyć obiekt **UserPFXCertificate**, uruchom polecenie `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>"`

   Na przykład: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "C:\temp\userA.pfx" $SecureFilePassword "userA@contoso.com" "Microsoft Software Key Storage Provider" "PFXEncryptionKey" "smimeEncryption" "pkcs1"`

   > [!NOTE]
   > W przypadku importowania certyfikatu z systemu innego niż serwer, na którym zainstalowano łącznik, należy użyć następującego polecenia zawierającego ścieżkę pliku klucza: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>" "<File path to public key file>"`

7. Zaimportuj obiekt **UserPFXCertificate** do usługi Intune, uruchamiając polecenie `Import-IntuneUserPfxCertificate -AuthenticationResult $authResult -CertificateList $userPFXObject`

8. Aby sprawdzić poprawność zaimportowanego certyfikatu, uruchom polecenie `Get-IntuneUserPfxCertificate -AuthenticationResult $authResult -UserList "<UserUPN>"`

Więcej informacji o innych dostępnych poleceniach można znaleźć w pliku readme [projektu PFXImport PowerShell w usłudze GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Tworzenie profilu zaimportowanego certyfikatu PKCS

Po zaimportowaniu certyfikatów do usługi Intune należy utworzyć profil **zaimportowanego certyfikatu PKCS** i przypisać go do grup usługi Azure Active Directory.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.

3. Wprowadź następujące właściwości:

   - **Nazwa** profilu
   - Opcjonalne określenie opisu
   - **Platforma**, na której ma być wdrożony profil
   - Ustawianie wartości pola **Typ profilu** na **Zaimportowany certyfikat PKCS**

4. Wybierz pozycję **Ustawienia**, a następnie wprowadź następujące właściwości:

   - **Przeznaczenie**: Określ przeznaczenie certyfikatów importowanych na potrzeby tego profilu. Administratorzy mogą importować certyfikaty o różnym przeznaczeniu (np. podpisywanie za pomocą protokołu S/MIME lub szyfrowanie za pomocą protokołu S/MIME). Przeznaczenie wybrane w profilu certyfikatu służy do dopasowywania profilu certyfikatu do odpowiednich zaimportowanych certyfikatów. Przeznaczenie to znacznik, według którego są grupowane zaimportowane certyfikaty. Nie gwarantuje przydatności zaimportowanych certyfikatów do określonego celu.  
   - **Okres ważności certyfikatu**: Jeśli nie zmieniono okresu ważności w szablonie certyfikatu, domyślnie wynosi on jeden rok.
   - **Dostawca magazynu kluczy**: W przypadku systemu Windows wybierz miejsce przechowywania kluczy na urządzeniu.

5. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać profil.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. [Przypisz](../configuration/device-profile-assign.md) nowy profil urządzenia.
