---
title: Uwierzytelnianie tylko aplikacji w magazynie danych usługi Intune
titleSuffix: Microsoft Intune
description: W tym temacie opisano uwierzytelnianie tylko aplikacji w magazynie danych usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d7166563-6bb5-4624-b8c8-6b300a997c3a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f70ca7d8d85853c38e2e8e88d06bae966431989
ms.sourcegitcommit: 6c74ff568267d85fd1d44fda75e3e24ead87cb2b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062980"
---
# <a name="intune-data-warehouse-application-only-authentication"></a>Uwierzytelnianie tylko aplikacji w magazynie danych usługi Intune

Aplikację można skonfigurować przy użyciu usługi Azure Active Directory (Azure AD) i uwierzytelnić w magazynie danych usługi Intune. Przydaje się to w przypadku witryn sieci Web, aplikacji i procesów w tle, gdy aplikacja nie powinna mieć dostępu do poświadczeń użytkownika. Wykonując poniższe kroki, autoryzujesz aplikację w usłudze Azure AD przy użyciu protokołu OAuth 2.0.

## <a name="authorization"></a>Autoryzacja

Przy użyciu protokołu OAuth 2.0 usługa Azure Active Directory (Azure AD) umożliwia autoryzację dostępu do aplikacji internetowych i internetowych interfejsów API w dzierżawie usługi Azure AD. W tym przewodniku przedstawiono sposób uwierzytelniania aplikacji przy użyciu języka C#. Kod autoryzacji OAuth 2.0 opisano w sekcji 4.1 specyfikacji protokołu OAuth 2.0. Aby uzyskać więcej informacji, zobacz [Autoryzacja dostępu do aplikacji internetowych przy użyciu protokołu OAuth 2.0 i usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).


## <a name="azure-keyvault"></a>Azure KeyVault

Następujący proces używa prywatnej metody do przetwarzania i konwersji klucza aplikacji. Ta prywatna metoda nosi nazwę SecureString. Do przechowywania klucza aplikacji można też użyć usługi Azure KeyVault. Aby uzyskać więcej informacji, zobacz temat [Key Vault](https://azure.microsoft.com/services/key-vault/).

## <a name="create-a-web-app"></a>Tworzenie aplikacji internetowej

W tej sekcji musisz podać szczegółowe informacje o aplikacji internetowej, którą chcesz wskazać w usłudze Intune. Aplikacja internetowa to aplikacja typu klient/serwer. Serwer udostępnia aplikację internetową, która obejmuje interfejs użytkownika, zawartość i funkcje. Aplikacje tego typu są oddzielnie obsługiwane w Internecie. Usługa Intune służy do udzielania aplikacji internetowej dostępu do usługi Intune. Przepływ danych jest inicjowany przez aplikację internetową. 

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Przy użyciu pola **Wyszukaj zasoby, usługi i dokumenty** w górnej części witryny Azure Portal wyszukaj pozycję **Azure Active Directory**.
3. Z menu rozwijanego wybierz pozycję **Azure Active Directory** w obszarze **Usługi**.
4. Wybierz pozycję **Rejestracje aplikacji**.
5. Kliknij pozycję **Rejestracja nowej aplikacji**, aby wyświetlić blok **Utwórz**.
6. W bloku **Utwórz** dodaj informacje dotyczące aplikacji:

    - Nazwę aplikacji, np. *Uwierzytelnianie tylko aplikacji w usłudze Intune*.
    - **Typ aplikacji**. Wybierz pozycję **Interfejs API/aplikacja sieci Web**, aby dodać aplikację internetową, internetowy interfejs API lub oba te elementy.
    - **Adres URL logowania** aplikacji. Jest to lokalizacja, do której użytkownicy automatycznie przechodzą w trakcie uwierzytelniania. Muszą oni udowodnić, że są tymi osobami, za które się podają. Aby uzyskać więcej informacji, zobacz temat [Co to jest dostęp do aplikacji i logowanie jednokrotne z usługą Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

7. Kliknij przycisk **Utwórz** w dolnej części bloku **Utwórz**.

    >[!NOTE] 
    > Skopiuj **Identyfikator aplikacji** z bloku **Zarejestrowana aplikacja**, aby go później użyć.

## <a name="create-a-key"></a>Tworzenie klucza

W tej sekcji usługa Azure AD generuje wartość klucza dla aplikacji.

1. W bloku **Rejestracje aplikacji** wybierz nowo utworzoną aplikację, aby wyświetlić blok aplikacji.
2. Wybierz pozycję **Ustawienia** w górnej części bloku, aby wyświetlić blok **Ustawienia**.
3. W bloku **Ustawienia** wybierz pozycję **Klucze**.
4. Dodaj opis klucza w polu **Opis**, podaj czas wygaśnięcia w polu **Wygasa** oraz wpisz **Wartość** klucza.
5. Kliknij przycisk **Zapisz**, aby zapisać i zaktualizować klucze aplikacji.
6. Należy skopiować wartość wygenerowanego klucza (kodowanie base64).

    >[!NOTE] 
    > Wartość klucza zniknie po wyjściu z bloku **Klucze**. Później nie będzie można pobrać klucza z tego bloku. Skopiuj go, aby mieć możliwość jego użycia w przyszłości.

## <a name="grant-application-permissions"></a>Przyznawanie uprawnień aplikacji

W tej sekcji opisano przyznawanie uprawnień do aplikacji.

1. W bloku **Ustawienia** wybierz pozycję **Wymagane uprawnienia**.
2. Kliknij pozycję **Dodaj**.
3. Wybierz pozycję **Dodaj interfejs API**, aby wyświetlić blok **Wybierz interfejs API**.
4. Wybierz pozycję **Interfejs API usługi Microsoft Intune (MicrosoftIntuneAPI)** , a następnie kliknij pozycję **Wybierz** w bloku **Wybierz interfejs API**. Zostanie wybrany krok **Wybierz uprawnienia** i wyświetli się blok **Włącz dostęp**.
5. Wybierz opcję **Uzyskaj dane magazynu danych z programu Microsoft Intune** w sekcji **Uprawnienia aplikacji**.
6. Kliknij przycisk **Wybierz** w bloku **Włącz dostęp**.
7. Kliknij przycisk **Gotowe** w bloku **Dodaj dostęp do interfejsu API**.
8. Kliknij pozycję **Udziel uprawnienia** w bloku **Wymagane uprawnienia** i kliknij przycisk **Tak** po podwyższeniu poziomu, aby zaktualizować istniejące uprawnienia, które ta aplikacja już ma.

## <a name="generate-token"></a>Generowanie tokenu

Za pomocą programu Visual Studio utwórz projekt aplikacji konsoli (.NET Framework), który obsługuje program .NET Framework i używa języka C#.

1. Wybierz kolejno pozycje **Plik** > **Nowe** > **Projekt**, aby wyświetlić okno dialogowe **Nowy projekt**.
2. Po lewej stronie wybierz pozycję **Visual C#** , aby wyświetlić wszystkie projekty programu .NET Framework.
3. Wybierz pozycję **Aplikacja konsoli (.NET Framework)** , dodaj nazwę aplikacji, a następnie kliknij przycisk **OK**, aby utworzyć aplikację.
4. W **Eksploratorze rozwiązań** wybierz pozycję **Program.cs**, aby wyświetlić kod.
5. W Eksploratorze rozwiązań dodaj odwołanie do zestawu `System.Configuration`.
6. W menu podręcznym wybierz pozycje **Dodaj** > **Nowy element**. Zostanie wyświetlone okno dialogowe **Dodaj nowy element**.
7. Po lewej stronie w obszarze **Visual C#** wybierz pozycję **Kod**.
8. Wybierz pozycję **Klasa**, zmień nazwę klasy na *IntuneDataWarehouseClass.cs* i kliknij przycisk **Dodaj**.
9. Dodaj następujący kod do metody <code>Main</code>:

    ``` csharp
         var applicationId = ConfigurationManager.AppSettings["appId"].ToString();
         SecureString applicationSecret = ConvertToSecureStr(ConfigurationManager.AppSettings["appKey"].ToString()); // Load as SecureString from configuration file or secret store (i.e. Azure KeyVault)
         var tenantDomain = ConfigurationManager.AppSettings["tenantDomain"].ToString();
         var adalContext = new AuthenticationContext($"https://login.windows.net/" + tenantDomain + "/oauth2/token");
    
         AuthenticationResult authResult = adalContext.AcquireTokenAsync(
             resource: "https://api.manage.microsoft.com/",
             clientCredential: new ClientCredential(
                 applicationId,
                 new SecureClientSecret(applicationSecret))).Result;
    ``` 

10. Dodaj dodatkowe przestrzenie nazw, dodając następujący kod w górnej części pliku kodu:

    ``` csharp
     using System.Security;
     using Microsoft.IdentityModel.Clients.ActiveDirectory;
     using System.Configuration;
    ``` 

11. Po metodzie <code>Main</code> dodaj następującą prywatną metodę do przetwarzania i konwersji klucza aplikacji:

    ``` csharp
    private static SecureString ConvertToSecureStr(string appkey)
    {
        if (appkey == null)
            throw new ArgumentNullException("AppKey must not be null.");
    
        var secureAppKey = new SecureString();
    
        foreach (char c in appkey)
            secureAppKey.AppendChar(c);
    
        secureAppKey.MakeReadOnly();
        return secureAppKey;
    }
    ```

12. W **Eksploratorze rozwiązań** kliknij prawym przyciskiem myszy pozycję **Odwołania**, a następnie wybierz pozycję **Zarządzaj pakietami NuGet**.
13. Wyszukaj pozycję *Microsoft.IdentityModel.Clients.ActiveDirectory* i zainstaluj powiązany pakiet Microsoft NuGet.
14. W **Eksploratorze rozwiązań** wybierz i otwórz plik *App.config*.
15. Dodaj sekcję <code>appSettings</code>, aby plik xml wyglądał następująco:

    ``` xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup> 
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <appSettings>
          <add key="appId" value="App ID created from 'Create a Web App' procedure"/>
          <add key="appKey" value="Key created from 'Create a key' procedure" />
          <add key="tenantDomain" value="contoso.onmicrosoft.com"/>
        </appSettings>
    </configuration>
    ``` 

16. Zaktualizuj wartości <code>appId</code>, <code>appKey</code> i <code>tenantDomain</code> odpowiadające unikatowym wartościom aplikacji.
17. Skompiluj aplikację.

    >[!NOTE] 
    > Aby wyświetlić dodatkowy kod implementacji, zobacz [przykładowy kod magazynu danych usługi Intune](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/CSharp ).

## <a name="next-steps"></a>Następne kroki
Aby dowiedzieć się więcej o usłudze Azure Key Vault, zobacz temat [Co to jest usługa Azure Key Vault?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)

