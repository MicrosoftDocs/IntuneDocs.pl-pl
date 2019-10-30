---
title: Używanie profilów certyfikatów SCEP z usługą Microsoft Intune na platformie Azure | Microsoft Docs
description: Twórz i przypisuj profile certyfikatów prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol) za pomocą usługi Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e28db0d24101ae65ff8c5e49febd0ff5dddc6e2
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585435"
---
# <a name="create-and-assign-scep-certificate-profiles-in-intune"></a>Tworzenie i przypisywanie profilów certyfikatów SCEP w usłudze Intune

Po [skonfigurowaniu infrastruktury](certificates-scep-configure.md) pod kątem obsługi prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol) możesz tworzyć profile certyfikatów SCEP, a następnie przypisywać je do użytkowników i urządzeń w usłudze Intune.

> [!IMPORTANT]  
> Przed utworzeniem profilów certyfikatów SCEP urządzenia, które będą używały profilu certyfikatu SCEP, muszą ufać Twojemu zaufanemu głównemu urzędowi certyfikacji. Użyj *profilu zaufanego certyfikatu* w usłudze Intune, aby zaprowizować certyfikat zaufanego głównego urzędu certyfikacji dla użytkowników i urządzeń. Aby uzyskać informacje o profilu zaufanego certyfikatu, zobacz [Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji](certificates-configure.md#export-the-trusted-root-ca-certificate) i [Tworzenie profilów zaufanych certyfikatów](certificates-configure.md#create-trusted-certificate-profiles) w temacie *Używanie certyfikatów do uwierzytelniania w usłudze Intune*.


## <a name="create-a-scep-certificate-profile"></a>Tworzenie profilu certyfikatu protokołu SCEP

1. Zaloguj się do [portalu usługi Intune](https://aka.ms/intuneportal).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu certyfikatu SCEP.
4. Z listy rozwijanej **Platforma** wybierz [obsługiwaną platformę urządzenia](certificates-configure.md#supported-platforms-and-certificate-profiles) dla tego certyfikatu SCEP. 
5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat SCEP**.  
   
   W przypadku platformy **Android Enterprise** *typ profilu* jest podzielony na dwie kategorie: *Tylko właściciel urządzenia* i *Tylko profil służbowy*. Upewnij się, że wybrano prawidłowy profil certyfikatu SCEP dla zarządzanych urządzeń.  

   Profile certyfikatów SCEP dla profilu *Tylko właściciel urządzenia* mają następujące ograniczenia:  

   1. Nie są obsługiwane następujące zmienne:  

      - CN={{OnPrem_Distinguished_Name}}  
      - CN={{onPremisesSamAccountName}}  

   2. W obszarze Monitorowanie funkcja raportowania certyfikatów nie jest dostępna w przypadku profilów certyfikatów SCEP właścicieli urządzeń.
   
   3. Nie można używać usługi Intune do odwoływania certyfikatów, które zostały aprowizowane przez profile certyfikatów SCEP dla właścicieli urządzeń. Odwołaniami można zarządzać za pomocą zewnętrznego procesu lub bezpośrednio przy użyciu urzędu certyfikacji. 

6. Wybierz pozycję **Ustawienia**, a następnie wykonaj następujące czynności konfiguracyjne:

   - **Typ certyfikatu**:   
     *(Dotyczy:  system Android, Android Enterprise, iOS, macOS, Windows 8.1 i nowszy oraz Windows 10 i nowszy).*  

      Wybierz typ w zależności od tego, w jaki sposób będzie używany profil certyfikatu:
      - **Użytkownik**: Certyfikaty typu *Użytkownik* mogą zawierać atrybuty użytkownika i urządzenia w podmiocie i nazwie SAN certyfikatu.  
      - **Urządzenie**:  Certyfikaty typu *Urządzenie* mogą zawierać tylko atrybuty urządzenia w temacie i nazwie SAN certyfikatu.  
      
        Używaj certyfikatów typu **Urządzenie** na potrzeby scenariuszy, takich jak urządzenia bez użytkowników, np. kioski, lub na potrzeby urządzeń z systemem Windows. Na urządzeniach z systemem Windows certyfikat zostanie umieszczony w magazynie certyfikatów na komputerze lokalnym.  

   - **Format nazwy podmiotu**:  
     wybierz sposób automatycznego tworzenia nazwy podmiotu w żądaniu certyfikatu przez usługę Intune. Opcje formatu nazwy podmiotu zależą od wybranego typu certyfikatu: **Użytkownik** lub **Urządzenie**.  

     > [!NOTE]  
     > Istnieje [znany problem](#avoid-certificate-signing-requests-with-escaped-special-characters) związany z używaniem protokołu SCEP do pobrania certyfikatów, gdy nazwa podmiotu w uzyskanym żądaniu podpisania certyfikatu (CSR) zawiera jeden z następujących znaków jako znak o zmienionym znaczeniu (poprzedzony ukośnikiem odwrotnym\\):
     > - \+
     > - ;
     > - ,
     > - =

     - **Typ certyfikatu Użytkownik**  
       Opcje formatu dla *formatu nazwy podmiotu* obejmują:  
       - **Nieskonfigurowany**
       - **Nazwa pospolita**
       - **Nazwa pospolita obejmująca adres e-mail**
       - **Nazwa pospolita jako adres e-mail**
       - **Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI)**
       - **Numer seryjny**
       - **Niestandardowy**: po wybraniu tej opcji zostanie również wyświetlone pole tekstowe **Niestandardowy**. Użyj tego pola do wprowadzenia niestandardowego formatu nazwy podmiotu, w tym zmiennych. Format niestandardowy obsługuje dwie zmienne: **Nazwa pospolita (CN)** i **Adres e-mail (E)** . Dla wartości **Nazwa pospolita (CN)** można ustawić jedną z następujących zmiennych:

         - **CN={{UserName}}** : główna nazwa użytkownika, taka jak janedoe@contoso.com.
         - **CN={{AAD_Device_ID}}** : identyfikator przypisany podczas rejestrowania urządzenia w usłudze Azure Active Directory (AD). Ten identyfikator jest zazwyczaj używany do uwierzytelniania za pomocą usługi Azure AD.
         - **CN={{SERIALNUMBER}}** : unikatowy numer seryjny (SN) używany zwykle przez producenta do identyfikowania urządzenia.
         - **CN={{IMEINumber}}** : unikatowy numer IMEI (International Mobile Equipment Identity) używany do identyfikowania telefonu komórkowego.
         - **CN={{OnPrem_Distinguished_Name}}** : sekwencja względnych nazw wyróżniających rozdzielonych przecinkami, taka jak *CN=Jan Nowak,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

           Aby użyć zmiennej *{{OnPrem_Distinguished_Name}}* , zsynchronizuj atrybut użytkownika *onpremisesdistinguishedname* z usługą Azure AD za pomocą programu [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

         - **CN={{onPremisesSamAccountName}}** : administratorzy mogą synchronizować atrybut samAccountName z usługi Active Directory do usługi Azure AD za pomocą programu Azure AD Connect do atrybutu o nazwie *onPremisesSamAccountName*. Usługa Intune może podstawić zmienną jako część żądania wystawienia certyfikatu w podmiocie certyfikatu. Atrybut samAccountName jest nazwą logowania użytkownika, która jest używana do obsługi klientów i serwerów z poprzedniej wersji systemu Windows (starszej niż Windows 2000). Format nazwy logowania użytkownika: *NazwaDomeny\użytkownikTestowy* lub tylko *użytkownikTestowy*.

            Aby użyć zmiennej *{{onPremisesSamAccountName}}* , zsynchronizuj atrybut użytkownika *onPremisesSamAccountName* z usługą Azure AD za pomocą programu [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

         Przy użyciu kombinacji jednej lub wielu spośród tych zmiennych i ciągów statycznych można utworzyć niestandardowy format nazwy podmiotu, na przykład:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
            
        W tym przykładzie uwzględniono format nazwy podmiotu, który używa zmiennych CN i E oraz ciągów dla wartości jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. Temat [Funkcja CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) zawiera opis tej funkcji i ciągi obsługiwane przez nią.

      - **Typ certyfikatu Urządzenie**  
        Opcje na potrzeby formatu nazwy podmiotu obejmują następujące zmienne: 
        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}** *(dotyczy tylko urządzeń z systemem Windows i urządzeń przyłączonych do domeny)*
        - **{{MEID}}**

        W polu tekstowym możesz określić te zmienne wraz z następującym po nich tekstem. Na przykład nazwa pospolita urządzenia o nazwie *Urządzenie1* może zostać dodana jako **CN={{DeviceName}}Urządzenie1**.

        > [!IMPORTANT]  
        > - Aby uniknąć błędu, po określeniu zmiennej należy ująć ją w nawiasy klamrowe { }, jak pokazano w przykładzie.  
        > - Właściwości urządzenia użyte w polach *temat* lub *Nazwa SAN* certyfikatu urządzenia, takie jak **IMEI**, **SerialNumber** i **FullyQualifiedDomainName**, są właściwościami, mogą zostać sfałszowane przez osobę z dostępem do urządzenia.
        > - Urządzenie musi obsługiwać wszystkie zmienne określone w profilu certyfikatu, aby dla tego profilu możliwe było instalowanie na urządzeniu.  Na przykład jeśli zmienna **{{IMEI}}** zostanie użyta w nazwie podmiotu profilu SCEP, a następnie zostanie przypisana do urządzenia, które nie ma numeru IMEI, instalacja profilu zakończy się niepowodzeniem.  

   - **Alternatywna nazwa podmiotu**:  
     wybierz sposób, w jaki usługa Intune automatycznie tworzy alternatywną nazwę podmiotu (SAN) w żądaniu certyfikatu. Opcje nazwy SAN zależą od wybranego typu certyfikatu: **Użytkownik** lub **Urządzenie**.  

      - **Typ certyfikatu Użytkownik**  
        Wybierz spośród dostępnych atrybutów:  
        - **Adres e-mail**
        - **Główna nazwa użytkownika (UPN)** 

        Na przykład typy certyfikatu Użytkownik mogą w alternatywnej nazwie podmiotu uwzględniać główną nazwę użytkownika (UPN). Jeśli certyfikat klienta będzie używany do uwierzytelniania go wobec serwera zasad sieciowych, dla alternatywnej nazwy podmiotu należy ustawić nazwę UPN.

      - **Typ certyfikatu Urządzenie**  
        Użyj listy rozwijanej **Atrybut** i wybierz atrybut, przypisz **wartość**, a następnie **dodaj** ją do profilu certyfikatu. Możesz dodać wiele wartości, wybierając dodatkowe atrybuty.  

        Dostępne są następujące atrybuty:
        - **Adres e-mail**
        - **Główna nazwa użytkownika (UPN)**
        - **DNS**

        W przypadku typu certyfikatu *Urządzenie* możesz używać następujących zmiennych certyfikatu urządzenia dla wartości:  

        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}**
        - **{{MEID}}**

        Aby określić wartość dla atrybutu, dołącz nazwę zmiennej w nawiasach klamrowych, po której następuje dotyczący jej tekst. Na przykład do wartości dla atrybutu DNS można dodać wartość **{{AzureADDeviceId}}.domena.com**, gdzie *.domena.com* jest tekstem. Dla użytkownika o nazwie *User1* adres e-mail może zostać wyświetlony jako {{FullyQualifiedDomainName}}User1@Contoso.com.  

        > [!IMPORTANT]  
        > - W przypadku stosowania zmiennej certyfikatu urządzenia należy ją ująć w nawiasy klamrowe { }.  
        > - Nie używaj nawiasów klamrowych **{ }** , symboli potoków **|** ani średników **;** w tekście następującym po zmiennej.  
        > - Właściwości urządzenia użyte w polach *temat* lub *Nazwa SAN* certyfikatu urządzenia, takie jak **IMEI**, **SerialNumber** i **FullyQualifiedDomainName**, są właściwościami, mogą zostać sfałszowane przez osobę z dostępem do urządzenia.  
        > - Urządzenie musi obsługiwać wszystkie zmienne określone w profilu certyfikatu, aby dla tego profilu możliwe było instalowanie na urządzeniu.  Na przykład jeśli zmienna **{{IMEI}}** zostanie użyta w nazwie SAN profilu SCEP, a następnie zostanie przypisana do urządzenia, które nie ma numeru IMEI, instalacja profilu zakończy się niepowodzeniem.

   - **Okres ważności certyfikatu**:  
     Możesz podać okres krótszy niż okres ważności w szablonie certyfikatu, ale nie dłuższy. Jeśli szablon certyfikatu został skonfigurowany pod kątem [obsługiwania wartości niestandardowej, którą można ustawić z poziomu konsoli usługi Intune](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template), użyj tego ustawienia, aby określić ilość czasu pozostałego do wygaśnięcia certyfikatu.  

     Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić jeden rok, ale nie pięć lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty.

   - **Dostawca magazynu kluczy**:  
     *(Dotyczy:  system Windows 8.1 i nowszy oraz Windows 10 i nowszy)*  
     
     Określ lokalizację przechowywania klucza do certyfikatu. Do wyboru są następujące wartości:  
     - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie u dostawcy magazynu kluczy oprogramowania**
     - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie niepowodzenie**
     - **Zarejestruj w usłudze Passport, w przeciwnym razie niepowodzenie (system Windows 10 i nowsze)**
     - **Zarejestruj u dostawcy magazynu kluczy oprogramowania**

   - **Użycie klucza**:  
     Wybierz opcje użycia klucza dla certyfikatu:

     - **Podpis cyfrowy**: zezwalaj na wymianę kluczy tylko wtedy, gdy w ochronie klucza pomaga podpis cyfrowy.
     - **Szyfrowanie klucza**: Zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest zaszyfrowany.  

   - **Rozmiar klucza (bity)** :  
     Wybierz liczbę bitów zawartych w kluczu.  

   - **Algorytm wyznaczania wartości skrótu**:  
     *(dotyczy systemów Android, Android Enterprise, Windows Phone 8,1, Windows 8.1 i nowszych oraz Windows 10 i nowszych)*  

     Wybierz jeden z dostępnych typów algorytmu wyznaczania wartości skrótu do użycia z tym certyfikatem. Wybierz najwyższy poziom zabezpieczeń obsługiwany przez podłączane urządzenia.

   - **Certyfikat główny**:  
     Wybierz *profil zaufanego certyfikatu*, który został wcześniej skonfigurowany i przypisany do odpowiednich użytkowników i urządzeń dla tego profilu certyfikatu SCEP. Profil zaufanego certyfikatu służy do aprowizowania certyfikatu zaufanego głównego urzędu certyfikacji dla użytkowników i urządzeń. Aby uzyskać informacje o profilu zaufanego certyfikatu, zobacz [Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji](certificates-configure.md#export-the-trusted-root-ca-certificate) i [Tworzenie profilów zaufanych certyfikatów](certificates-configure.md#create-trusted-certificate-profiles) w temacie *Używanie certyfikatów do uwierzytelniania w usłudze Intune*. Jeśli posiadasz główny urząd certyfikacji i urząd wystawiający certyfikaty, wybierz profil zaufanego certyfikatu głównego skojarzony z urzędem wystawiającym certyfikaty.

   - **Rozszerzone użycie klucza**:  
     dodaj wartości w zależności od celu certyfikatu. W większości przypadków jest wymagane *uwierzytelnienie klienta* dla certyfikatu, aby zapewnić użytkownikom lub urządzeniom możliwość uwierzytelnienia na serwerze. W razie potrzeby możesz dodać dodatkowe użycia klucza.

   - **Próg odnawiania (%)** :  
     wprowadź wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać odnowienia certyfikatu. Jeśli na przykład wprowadzisz wartość 20, próba odnowienia certyfikatu zostanie podjęta w przypadku, gdy certyfikat wygasł w 80%. Próby odnowienia będą kontynuowane, aż odnawianie zakończy się pomyślnie. Podczas odnawiania generowany jest nowy certyfikat, co powoduje utworzenie nowej pary kluczy publicznych/prywatnych.

   - **Adresy URL serwerów SCEP**:  
     wprowadź co najmniej jeden adres URL dla serwerów usługi NDES, które wystawiają certyfikaty za pośrednictwem protokołu SCEP. Na przykład wpisz coś takiego: *https://ndes.contoso.com/certsrv/mscep/mscep.dll* . W razie potrzeby można dodać dodatkowe adresy URL protokołu SCEP na potrzeby równoważenia obciążenia, ponieważ adresy URL są losowo wypychane do urządzenia przy użyciu profilu. Jeśli jeden z serwerów SCEP jest niedostępny, żądanie SCEP zakończy się niepowodzeniem i możliwe jest, że w przypadku późniejszych ewidencjonowań urządzeń zostanie wykonane żądanie certyfikatu względem serwera, który nie działa.

7. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**. Profil zostanie utworzony i wyświetlony na liście *Konfiguracja urządzenia — profile*.

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>Unikanie żądań podpisania certyfikatu ze znakami specjalnymi o zmienionym znaczeniu
Istnieje znany problem dotyczący żądań certyfikatów SCEP i PKCS, które zawierają nazwę podmiotu (CN) z co najmniej jednym z następujących znaków specjalnych jako znakiem ucieczki. Nazwy podmiotów, które zawierają jeden ze znaków specjalnych jako znak ucieczki, powodują wygenerowanie pliku CSR z nieprawidłową nazwą podmiotu. Niepoprawna nazwa podmiotu powoduje niepowodzenie weryfikacji wezwania SCEP usługi Intune i niemożność wydania certyfikatu.

Znaki specjalne, których dotyczy problem:
- \+
- ,
- ;
- =

Jeśli nazwa podmiotu zawiera jeden z tych znaków specjalnych, użyj jednej z następujących opcji, aby obejść to ograniczenie:  
- Hermetyzuj wartość CN, która zawiera znak specjalny, za pomocą cudzysłowów.  
- Usuń znak specjalny z wartości CN.  

**Przykładowo** masz nazwę podmiotu, która jest wyświetlana jako *Test user (TestCompany, LLC)* .  Problemem jest żądanie CSR zawierające nazwę CN, w której występuje przecinek między *TestCompany* i *LLC*.  Problemowi można zapobiec, umieszczając cudzysłowy wokół całej nazwy CN lub usuwając przecinek pomiędzy *TestCompany* i *LLC*:
- **Dodanie cudzysłowów**: *CN=* ”Test User (TestCompany, LLC)”,OU=UserAccounts,DC=corp,DC=contoso,DC=com*
- **Usunięcie przecinka**: *CN=Test User (TestCompany LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com*

 Natomiast próby zmiany znaczenia przecinka przy użyciu znaku ukośnika odwrotnego zakończą się niepowodzeniem i wystąpi błąd w dziennikach CRP:  
- **Przecinek o zmienionym znaczeniu**: *CN=Test User (TestCompany\\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com*

Błąd jest podobny do następującego: 

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```

## <a name="assign-the-certificate-profile"></a>Przypisywanie profilu certyfikatu
Przypisz profile certyfikatów SCEP w taki sam sposób, w jaki [wdrażasz profile urządzeń](../configuration/device-profile-assign.md) do innych celów. Jednak przed kontynuowaniem weź pod uwagę następujące kwestie:

- Podczas przypisywania profilów certyfikatów SCEP do grup na urządzeniu jest instalowany plik certyfikatu zaufanego urzędu certyfikacji (określony w *profilu zaufanego certyfikatu*). Urządzenie korzysta z profilu certyfikatu SCEP w celu utworzenia żądania certyfikatu na potrzeby tego certyfikatu zaufanego głównego urzędu certyfikacji.  

- Profil certyfikatu SCEP jest instalowany tylko na urządzeniach z uruchomioną platformą określoną podczas tworzenia profilu certyfikatu.

- Profile certyfikatów można również przypisywać do kolekcji użytkowników lub kolekcji urządzeń.

- Aby opublikować certyfikat dla urządzenia jak najszybciej po jego rejestracji, należy przypisać profil certyfikatu do grupy użytkowników, a nie do grupy urządzeń. W przypadku przypisania do grupy urządzeń wymagana jest pełna rejestracja urządzenia przed otrzymaniem przez nie zasad.  

- Jeśli używasz funkcji współzarządzania dla usługi Intune i programu Configuration Manager, w programie Configuration Manager [ustaw suwak obciążenia](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) dla zasad dostępu do zasobów na usługę **Intune** lub **pilotażową usługę Intune**. To ustawienie umożliwia klientom systemu Windows 10 uruchamianie procesu żądania certyfikatu.

- Chociaż profil zaufanego certyfikatu i profil certyfikatu SCEP są tworzone osobno, oba muszą zostać przypisane. Gdy oba te profile nie zostaną zainstalowane na urządzeniu, zasady certyfikatu SCEP nie będą działać. Upewnij się, że wszystkie profile zaufanych certyfikatów głównych zostały również wdrożone w tych samych grupach, co profil SCEP.


> [!NOTE]
> Na urządzeniu z systemem iOS, kiedy profil certyfikatu SCEP jest skojarzony z dodatkowym profilem, takim jak profil sieci Wi-Fi lub VPN, urządzenie otrzymuje certyfikat dla każdego z tych dodatkowych profilów. W wyniku urządzenie z systemem iOS ma wiele certyfikatów dostarczonych przez żądanie certyfikatu SCEP.  Jeśli potrzebny jest pojedynczy certyfikat, należy użyć certyfikatów PKCS zamiast certyfikatów SCEP.  Wynika to z różnic w sposobie dostarczania certyfikatów SCEP i PKCS na urządzenia.


## <a name="next-steps"></a>Następne kroki  

[Przypisywanie profilów](../configuration/device-profile-assign.md)  
