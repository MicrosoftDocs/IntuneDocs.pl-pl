---
title: Jak używać usługi Azure AD do uzyskiwania dostępu do interfejsów API usługi Intune w programie Microsoft Graph
titlesuffix: Microsoft Intune
description: W tym artykule opisano kroki niezbędne do uzyskiwania przez aplikacje dostępu do interfejsów API usługi Intune w programie Microsoft Graph przy użyciu usługi Azure AD.
keywords: intune graphapi c# powershell role uprawnień
author: dougeby
manager: dougeby
ms.author: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ca5b09d415466d2ab6ce2f70a53f7fd8444d28f
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-azure-ad-to-access-the-intune-apis-in-microsoft-graph"></a>Jak używać usługi Azure AD do uzyskiwania dostępu do interfejsów API usługi Intune w programie Microsoft Graph

[Interfejs API programu Microsoft Graph](https://developer.microsoft.com/graph/) obsługuje teraz usługę Microsoft Intune za pomocą określonych interfejsów API i ról uprawnień.  Interfejs API programu Microsoft Graph używa usługi Azure Active Directory (Azure AD) do uwierzytelniania i kontroli dostępu.  
Dostęp do interfejsów API usługi Intune w programie Microsoft Graph wymaga elementów, takich jak:

- Identyfikator aplikacji z:

    - Uprawnieniem do wywołania usługi Azure AD i interfejsów API programu Microsoft Graph.
    - Zakresy uprawnień odpowiednich do określonych zadań aplikacji.

- Poświadczenia użytkownika z:

    - Uprawnieniem dostępu do dzierżawy usługi Azure AD skojarzonej z aplikacją.
    - Uprawnieniami roli wymaganymi do obsługi zakresów uprawnień aplikacji.

- Użytkownikiem końcowym z udzielonym uprawnieniem do aplikacji do wykonywania zadań aplikacji dla swojej dzierżawy Azure.

W tym artykule:

- Pokazano, jak zarejestrować aplikację za pośrednictwem dostępu do interfejsu API programu Microsoft Graph i odpowiednich ról uprawnień.

- Opisano role uprawnień interfejsu API usługi Intune.

- Zamieszczono przykłady uwierzytelniania interfejsu API usługi Intune dla języka C# i programu PowerShell.

- Opisano sposób obsługi wielu dzierżaw.

Aby dowiedzieć się więcej, zobacz następujące artykuły:

- [Autoryzacja dostępu do aplikacji sieci Web przy użyciu protokołu OAuth 2.0 i usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [Rozpoczęcie pracy z uwierzytelnianiem w usłudze Azure AD](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [Integrowanie aplikacji z usługą Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [Koncepcja protokołu OAuth 2.0](https://oauth.net/2/)

## <a name="register-apps-to-use-the-microsoft-graph-api"></a>Rejestrowanie aplikacji do korzystania z interfejsu API programu Microsoft Graph

Aby zarejestrować aplikację do korzystania z interfejsu API programu Microsoft Graph:

1.  Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) przy użyciu poświadczeń administracyjnych.

    Zgodnie z potrzebami możesz wykorzystać:
    - Konto administratora dzierżawy.
    - Konto użytkownika dzierżawy z włączonym ustawieniem **Użytkownicy mogą rejestrować aplikacje**.

2.  W menu wybierz opcję **Azure Active Directory** &gt; **Rejestracje aplikacji**.

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  Wybierz opcję **Rejestracja nowej aplikacji**, aby utworzyć nową aplikację, lub wybierz istniejącą aplikację.  (Jeśli wybierzesz istniejącą aplikację, pomiń następny krok).

4.  W bloku **Tworzenie** określ następujące pozycje:

    1.  **Nazwa** aplikacji (wyświetlana podczas logowania).

    2.  Wartości **Typ aplikacji** i **Identyfikator URI przekierowania**.

        Mogą się one różnić w zależności od wymagań. Na przykład, jeśli używasz biblioteki Azure AD [Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL), ustaw **Typ aplikacji** na `Native`, a **Identyfikator URI przekierowania** na `urn:ietf:wg:oauth:2.0:oob`.

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        Aby dowiedzieć się więcej, zobacz temat [Scenariusze uwierzytelniania dla usługi Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

5.  W bloku aplikacji:

    1.  Zanotuj wartość z pola **Identyfikator aplikacji**.

    2.  Wybierz kolejno opcje **Ustawienia** &gt; **Dostęp do interfejsu API** &gt; **Wymagane uprawnienia**.

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  W bloku **Wymagane uprawnienia** wybierz opcje **Dodaj** &gt; **Dodaj dostęp do interfejsu API** &gt; **Wybierz interfejs API**.

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  W bloku **Wybór interfejsu API** wybierz opcję **Microsoft Graph** &gt; **Wybierz**.  Zostanie otwarty blok **Włączanie dostępu** i wyświetlą się zakresy uprawnień dostępne dla aplikacji.

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    Wybierz role wymagane dla aplikacji, umieszczając znacznik wyboru z lewej strony odpowiednich nazw.  Aby dowiedzieć się więcej na temat zakresów uprawnień usługi Intune, zobacz temat [Zakresy uprawnień usługi Intune](#intune-permission-scopes).  Aby poznać inne zakresy uprawnień interfejsu API programu Graph, zobacz temat [Lista uprawnień w programie Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).

    Aby osiągnąć najlepsze rezultaty, wybierz jak najmniej ról wymaganych do wdrożenia aplikacji.

    Po zakończeniu wybierz opcję **Wybierz** i **Gotowe**, aby zapisać zmiany.

W tym momencie możesz również:

- Nadać uprawnienia dla wszystkich kont dzierżawy, aby można było korzystać z aplikacji bez konieczności podawania poświadczeń.  

    W tym celu wybierz opcję **Udziel uprawnień** i zaakceptuj monit o potwierdzenie.

    Po pierwszym uruchomieniu aplikacji wyświetli się monit o przyznanie uprawnień aplikacji do wykonania wybranych ról.

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- Udostępnić aplikację użytkownikom spoza dzierżawy.  (Zazwyczaj jest to wymagane tylko w przypadku partnerów obsługujących wielu dzierżawców lub wiele organizacji).  

    W tym celu:

  1. Wybierz opcję **Manifest** w bloku aplikacji, która otwiera blok **Edytowanie manifestu**.

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

  2. Zmień wartość ustawienia `availableToOtherTenants` na `true`.

  3. Zapisz zmiany.

## <a name="intune-permission-scopes"></a>Zakresy uprawnień usługi Intune

Usługa Azure AD i program Microsoft Graph używają zakresów uprawnień do kontrolowania dostępu do zasobów firmy.  

Zakresy uprawnień (nazywane również _zakresami uwierzytelniania protokołu OAuth_) kontrolują dostęp do konkretnych obiektów usługi Intune i ich właściwości. Ta sekcja zawiera podsumowanie informacji o zakresach uprawnień dla funkcji interfejsu API usługi Intune.

Dodatkowe informacje:
- [Uwierzytelnianie usługi Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [Zakresy uprawnień aplikacji](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

Przy udzielaniu uprawnienia do interfejsu API programu Microsoft Graph można określić wymienione poniżej zakresy umożliwiające kontrolę dostępu do funkcji usługi Intune. Poniższa tabela zawiera podsumowanie zakresów uprawnień interfejsu API usługi Intune.  W pierwszej kolumnie znajduje się nazwa funkcji wyświetlana w witrynie Azure Portal, a w drugiej — nazwa zakresu uprawnień.

Ustawienie _Włącz dostęp_ | Nazwa zakresu
:--|:--
__Wykonywanie akcji zdalnych mających wpływ na użytkownika na urządzeniach Microsoft Intune__ | [DeviceManagementManagedDevices.PrivilegedOperations.All](#mgd-po)
__Odczyt i zapis na urządzeniach Microsoft Intune__ | [DeviceManagementManagedDevices.ReadWrite.All](#mgd-rw)
__Odczyt z urządzeń Microsoft Intune__ | [DeviceManagementManagedDevices.Read.All](#mgd-ro)
__Odczyt i zapis ustawień kontroli RBAC usługi Microsoft Intune__ | [DeviceManagementRBAC.ReadWrite.All](#rac-rw)
__Odczyt ustawień kontroli RBAC usługi Microsoft Intune__ | [DeviceManagementRBAC.Read.All](#rac=ro)
__Odczyt i zapis aplikacji usługi Microsoft Intune__ | [DeviceManagementApps.ReadWrite.All](#app-rw)
__Odczyt aplikacji usługi Microsoft Intune__ | [DeviceManagementApps.Read.All](#app-ro)
__Odczyt i zapis konfiguracji i zasad urządzeń Microsoft Intune__ | [DeviceManagementConfiguration.ReadWrite.All](#cfg-rw)
__Odczyt konfiguracji i zasad urządzeń Microsoft Intune__ | [DeviceManagementConfiguration.Read.All](#cfg-ro)
__Odczyt i zapis konfiguracji usługi Microsoft Intune__ | [DeviceManagementServiceConfig.ReadWrite.All](#svc-rw)
__Odczyt konfiguracji usługi Microsoft Intune__ | [DeviceManagementServiceConfig.Read.All](#svc-ra)

W tabeli wymieniono ustawienia w takiej formie, w jakiej są wyświetlane w witrynie Azure Portal. W poniższych sekcjach opisano zakresy w kolejności alfabetycznej.

Aktualnie wszystkie zakresy uprawnień usługi Intune wymagają dostępu administratora.  Oznacza to, że gdy uruchamiane są aplikacje lub skrypty wymagające dostępu do zasobów interfejsu API usługi Intune, niezbędne są odpowiednie poświadczenia.

### <a name="app-ro"></a>DeviceManagementApps.Read.All

- Ustawienie **Włącz dostęp**: __odczyt aplikacji usługi Microsoft Intune__

- Zezwala na dostęp do właściwości i stanu następujących elementów w trybie do odczytu:
    - Aplikacje mobilne
    - Kategorie aplikacji mobilnych
    - Zasady ochrony aplikacji
    - Konfiguracje aplikacji

### <a name="app-rw"></a>DeviceManagementApps.ReadWrite.All

- Ustawienie **Włącz dostęp**: __odczyt i zapis aplikacji usługi Microsoft Intune__

- Umożliwia wykonywanie tych samych operacji co __DeviceManagementApps.Read.All__

- Dodatkowo umożliwia wprowadzanie zmian w następujących elementach:

    - Aplikacje mobilne
    - Kategorie aplikacji mobilnych
    - Zasady ochrony aplikacji
    - Konfiguracje aplikacji

### <a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All

- Ustawienie **Włącz dostęp**: __odczyt konfiguracji i zasad urządzeń Microsoft Intune__

- Zezwala na dostęp do właściwości i stanu następujących elementów w trybie do odczytu:
    - Konfiguracja urządzenia
    - Zasady zgodności urządzeń
    - Opcje komunikatów powiadomień

### <a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All

- Ustawienie **Włącz dostęp**: __odczyt i zapis konfiguracji i zasad urządzeń Microsoft Intune__

- Umożliwia wykonywanie tych samych operacji co __DeviceManagementConfiguration.Read.All__

- Aplikacje mogą również tworzyć, przypisywać, usuwać i wprowadzać zmiany w następujących elementach:
    - Konfiguracja urządzenia
    - Zasady zgodności urządzeń
    - Opcje komunikatów powiadomień

### <a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All

- Ustawienie **Włącz dostęp**: __wykonywanie akcji zdalnych wpływających na użytkownika na urządzeniach Microsoft Intune__

- Zezwala na wykonywanie następujących zdalnych akcji na zarządzanym urządzeniu:
    - Wycofaj
    - Czyszczenie danych
    - Resetowanie/odzyskiwanie kodu dostępu
    - Zdalne blokowanie
    - Włączenie/wyłączenie trybu zgubienia
    - Czyszczenie komputera
    - Ponowny rozruch
    - Usunięcie użytkownika z urządzenia udostępnionego

### <a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All

- Ustawienie **Włącz dostęp**: __odczyt z urządzeń Microsoft Intune__

- Zezwala na dostęp do właściwości i stanu następujących elementów w trybie do odczytu:
    - Zarządzane urządzenie
    - Kategoria urządzenia
    - Wykryta aplikacja
    - Akcje zdalne
    - Informacje o złośliwym oprogramowaniu

### <a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All

- Ustawienie **Włącz dostęp**: __odczyt i zapis na urządzeniach Microsoft Intune__

- Umożliwia wykonywanie tych samych operacji co __DeviceManagementManagedDevices.Read.All__

- Aplikacje mogą również tworzyć, usuwać i wprowadzać zmiany w następujących elementach:
    - Zarządzane urządzenie
    - Kategoria urządzenia

- Dozwolone jest również wykonywanie następujących akcji zdalnych:
    - Lokalizowanie urządzeń
    - Zastosowanie obejścia blokady aktywacji
    - Wysyłanie żądań pomocy zdalnej

### <a name="rac-ro"></a>DeviceManagementRBAC.Read.All

- Ustawienie **Włącz dostęp**: __odczyt ustawień kontroli RBAC usługi Microsoft Intune__

- Zezwala na dostęp do właściwości i stanu następujących elementów w trybie do odczytu:
    - Przypisania ról
    - Definicje ról
    - Operacje zasobów

### <a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All

- Ustawienie **Włącz dostęp**: __odczyt i zapis ustawień kontroli RBAC usługi Microsoft Intune__

- Umożliwia wykonywanie tych samych operacji co __DeviceManagementRBAC.Read.All__

- Aplikacje mogą również tworzyć, przypisywać, usuwać i wprowadzać zmiany w następujących elementach:
    - Przypisania ról
    - Definicje ról

### <a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All

- Ustawienie **Włącz dostęp**: __odczyt konfiguracji usługi Microsoft Intune__

- Zezwala na dostęp do właściwości i stanu następujących elementów w trybie do odczytu:
    - Rejestrowanie urządzenia
    - Certyfikat usługi Apple Push Notification
    - Program Device Enrollment Program firmy Apple
    - Program Apple Volume Purchase Program
    - Exchange Connector
    - Warunki i postanowienia
    - Zarządzanie kosztami telekomunikacji
    - Infrastruktura PKI w chmurze
    - Znakowanie
    - Usługa Mobile Threat Defense

### <a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All

- Ustawienie **Włącz dostęp**: __odczyt i zapis konfiguracji usługi Microsoft Intune__

- Umożliwia wykonywanie tych samych operacji co DeviceManagementServiceConfig.Read.All_

- Aplikacje mogą również konfigurować następujące funkcje:
    - Rejestrowanie urządzenia
    - Certyfikat usługi Apple Push Notification
    - Program Device Enrollment Program firmy Apple
    - Program Apple Volume Purchase Program
    - Exchange Connector
    - Warunki i postanowienia
    - Zarządzanie kosztami telekomunikacji
    - Infrastruktura PKI w chmurze
    - Znakowanie
    - Usługa Mobile Threat Defense

## <a name="azure-ad-authentication-examples"></a>Przykłady uwierzytelniania w usłudze Azure AD

W tej sekcji pokazano, jak dołączyć usługę Azure AD do projektów C# i programu PowerShell.

W każdym przykładzie musisz określić identyfikator aplikacji, która ma co najmniej zakres uprawnień `DeviceManagementManagedDevices.Read.All` (opisany wcześniej).

Podczas testowania dowolnego przykładu możesz otrzymać błędy stanu HTTP 403 (Zabroniony dostęp) podobne do następującego:

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

Jeśli tak się stanie, sprawdź, czy:

- Identyfikator aplikacji został zaktualizowany do jednego z dysponujących prawem do korzystania z interfejsu API programu Microsoft Graph i zakresu uprawnień `DeviceManagementManagedDevices.Read.All`.

- Twoje poświadczenia dzierżawy obsługują funkcje administracyjne.

- Kod jest podobny do wyświetlanych przykładów.


### <a name="authenticate-azure-ad-in-c"></a>Uwierzytelnianie usługi Azure AD w języku C\#

Ten przykład przedstawia pobieranie listy urządzeń skojarzonych z kontem usługi Intune w języku C#.

1.  Uruchom program Visual Studio, a następnie utwórz nowy projekt aplikacji konsoli (.NET Framework) Visual C#.

2.  Wprowadź nazwę projektu i podaj inne szczegóły zgodnie z potrzebami.

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  Za pomocą Eksploratora rozwiązań dodaj do projektu pakiet NuGet biblioteki ADAL firmy Microsoft.

    1.  Kliknij prawym przyciskiem myszy w Eksploratorze rozwiązań.
    2.  Wybierz opcję **Zarządzaj pakietami NuGet...** &gt; **Przeglądaj**.
    3.  Wybierz pozycję `Microsoft.IdentityModel.Clients.ActiveDirectory`, a następnie wybierz opcję **Zainstaluj**.

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  Na początku pliku **Program.cs** dodaj następujące instrukcje:

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  Dodaj metodę, która utworzy nagłówek autoryzacji:

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    Pamiętaj, aby zmienić wartość `application_ID` na odpowiadającą jednemu z przyznanych zakresów uprawnień co najmniej `DeviceManagementManagedDevices.Read.All`, zgodnie z wcześniejszym opisem.

6. Dodaj metodę, która pobierze listę urządzeń:

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  Zaktualizuj metodę **Main**, aby wywoływała metodę **GetMyManagedDevices**:

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  Skompiluj i uruchom program.  

Przy pierwszym uruchomieniu programu powinny zostać wyświetlone dwa monity.  Pierwszy dotyczy podania poświadczeń użytkownika, a drugi przyznaje uprawnienia do żądania `managedDevices`.  

Oto ukończony program (dla porównania):

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a>Uwierzytelnianie usługi Azure AD (PowerShell)

Poniższy skrypt programu PowerShell używa modułu AzureAD PowerShell do uwierzytelniania.  Aby dowiedzieć się więcej, zobacz temat [Azure Active Directory programu PowerShell w wersji 2](https://docs.microsoft.com/powershell/azure/install-adv2?view=azureadps-2.0) i [przykłady z programu Intune PowerShell](https://github.com/microsoftgraph/powershell-intune-samples).

W tym przykładzie zaktualizuj wartość `$clientID` na odpowiadającą prawidłowemu identyfikatorowi aplikacji.

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a>Obsługa wielu dzierżawców i partnerów

Jeśli Twoja organizacja obsługuje organizacje za pomocą ich własnych dzierżaw usługi Azure AD, można zezwolić klientom na używanie aplikacji z odpowiednimi dzierżawami.

W tym celu:

1.  Sprawdź, czy konto klienta istnieje w dzierżawie docelowej usługi Azure AD.

2.  Sprawdź, czy Twoje konto dzierżawy zezwala użytkownikom na rejestrowanie aplikacji (zobacz **Ustawienia użytkownika**).

3.  Ustanów relację między wszystkimi dzierżawcami.  

    W tym celu wykonaj jedno z poniższych działań:

    a. Użyj [Centrum partnerskiego firmy Microsoft](https://partnercenter.microsoft.com/), aby zdefiniować relację z klientem oraz jego adres e-mail.

    b. Zaproś użytkownika jako gościa Twojej dzierżawy.

Aby zaprosić użytkownika jako gościa dzierżawy:

1.  W panelu **Szybkie zadania** wybierz opcję **Dodaj gościa**.

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  Wprowadź adres e-mail klienta i (opcjonalnie) dodaj spersonalizowane zaproszenie.

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  Wybierz opcję **Zaproś**.

Spowoduje to wysłanie zaproszenia do użytkownika.

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   Użytkownik musi wybrać link **Rozpoczęto** umożliwiający zaakceptowanie zaproszenia.

Po ustanowieniu relacji (lub zaakceptowaniu zaproszenia) dodaj konto użytkownika do **Roli katalogu**.

Pamiętaj, aby dodać użytkownika do innych ról, zgodnie z potrzebami. Na przykład aby zezwolić użytkownikowi na zarządzanie ustawieniami usługi Intune, musi być on **Administratorem globalnym** lub **Administratorem usługi Intune**.

Ponadto:

- Aby przypisać licencję usługi Intune do konta użytkownika, skorzystaj z witryny https://portal.office.com.

- Zaktualizuj kod aplikacji do uwierzytelniania klienta domeny dzierżawy usługi Azure AD zamiast własnej.

    Załóżmy na przykład, że Twoja domena dzierżawy to `contosopartner.onmicrosoft.com`, a domena dzierżawy klienta to `northwind.onmicrosoft.com`. Należy zaktualizować swój kod, aby uwierzytelnić się do dzierżawy klienta.

    Aby to zrobić w aplikacji w języku C# opartej na wcześniejszym przykładzie, należy zmienić wartość zmiennej `authority`:

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    na wartość

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
