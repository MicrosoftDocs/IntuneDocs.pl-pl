---
title: "Pobieranie danych z interfejsu API magazynu danych za pomocą klienta REST"
description: "Pobieraj dane z magazynu danych usługi Intune za pomocą interfejsu API RESTful."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f1ffc07d87e98666a882415d63e11bd04bbd5461
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2017
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>Pobieranie danych z interfejsu API magazynu danych usługi Intune za pomocą klienta REST

Dostęp do modelu danych magazynu danych usługi Intune można uzyskać za pośrednictwem punktów końcowych RESTful. Aby uzyskać dostęp do danych, należy autoryzować klienta w usłudze Microsoft Azure Active Directory (Azure AD) przy użyciu protokołu OAuth 2.0. Aby włączyć dostęp, najpierw skonfiguruj aplikację natywną na platformie Azure i przyznaj uprawnienia do interfejsu API usługi Microsoft Intune. Klient lokalny uzyska autoryzację, a następnie będzie mógł komunikować się z punktami końcowymi magazynu danych za pośrednictwem aplikacji natywnej.

Te kroki dotyczące konfigurowania klienta do pobierania danych z interfejsu API magazynu danych wymagają, aby:

1. Utworzyć aplikację kliencką jako aplikację natywną na platformie Azure
3. Przyznać aplikacji klienckiej dostęp do interfejsu API usługi Microsoft Intune
3. Utworzyć lokalnego klienta REST do pobierania danych

Dzięki poniższym krokom dowiesz się, jak autoryzować narzędzie Postman i używać go jako klienta. Postman to powszechnie używane narzędzie służące do rozwiązywania problemów i umożliwiające pracę klientów REST z interfejsami API. Odwiedź witrynę narzędzia [Postman](https://www.getpostman.com), aby uzyskać o nim więcej informacji. Ten temat zawiera również przykładowy kod C#. Przykładowy kod dotyczy autoryzowania klienta i pobierania danych z interfejsu API.

## <a name="create-a-native-app-in-azure"></a>Tworzenie aplikacji natywnej na platformie Azure

Utwórz aplikację natywną na platformie Azure. Ta aplikacja natywna jest aplikacją kliencką. Klient uruchomiony na maszynie lokalnej odwołuje się do interfejsu API magazynu danych usługi Intune, gdy klient lokalny żąda poświadczeń. 

1. Zaloguj się do witryny Azure Portal dla swojej dzierżawy. Wybierz pozycję **Azure Active Directory** > **Rejestracje aplikacji**, aby otworzyć blok **Rejestracje aplikacji**.
2. Kliknij pozycję **Rejestracja nowej aplikacji**.
3. Wpisz szczegóły aplikacji.
    1.  W polu **Nazwa** wpisz przyjazną nazwę, na przykład Intune Data Warehouse Client.
    2.  W polu **Typ aplikacji** wybierz pozycję **Natywna**.
    3.  Wpisz adres URL w polu **Adres URL logowania**. Adres URL logowania zależy od konkretnego scenariusza, jeśli jednak zamierzasz korzystać z narzędzia Postman, wpisz `https://www.getpostman.com/oauth2/callback`. Podczas uwierzytelniania w usłudze Azure AD w kroku uwierzytelniania klienta użyj wywołania zwrotnego.
4.  Kliknij przycisk **Utwórz**.

     ![Interfejs API magazynu danych usługi Intune](media\reports-get_rest_data_client_overview.png)

5. Zanotuj wartość z pola **Identyfikator aplikacji** dla tej aplikacji. Identyfikatora użyjesz w następnej sekcji.
6. Dodaj klucz, jeśli zamierzasz korzystać z narzędzia Postman. Podczas uwierzytelniania w usłudze Azure AD ten klucz jest używany jako klucz tajny klienta. Aby dodać klucz:
    1.  Kliknij pozycję **Klucze** w obszarze **Dostęp do interfejsu API** w bloku ustawień aplikacji.
    2.  W polu **Opis** wpisz nazwę klucza, na przykład Klucz-tajny-klienta.
    3.  W polu Czas trwania wybierz pozycję **1 rok**.
    4.  Kliknij polecenie **Zapisz**. 
    5.  Skopiuj wartość klucza. Klucza nie będzie można pobrać po zamknięciu bloku **Ustawienia** kluczy.

## <a name="grant-the-native-app-access-to-the-microsoft-intune-api"></a>Przyznawanie aplikacji natywnej dostępu do interfejsu API usługi Microsoft Intune

Możesz teraz mieć aplikację zdefiniowaną na platformie Azure. Przyznaj aplikacji natywnej dostęp do interfejsu API usługi Microsoft Intune.

1.  Kliknij aplikację natywną. Aplikacji nadano nazwę taką jak na przykład **Intune Data Warehouse Client**.
2.  W bloku **Ustawienia** kliknij pozycję **Wymagane uprawnienia**.
3.  W bloku **Wymagane uprawnienia** kliknij pozycję **Dodaj**.
4.  Kliknij pozycję **Wybierz interfejs API**.
5.  Wyszukaj nazwę aplikacji internetowej. Ma nazwę **Microsoft Intune API**.
6.  Kliknij aplikację na liście.
7.  Kliknij pozycję **Wybierz**.
8.  Zaznacz pole **Uprawnienia delegowane**, aby dodać pozycję **Pobierz informacje magazynu danych z usługi Microsoft Intune**.

    ![Włączanie dostępu](media\reports-get_rest_data_client_access.png)

9.  Kliknij pozycję **Wybierz**.
10.  Kliknij pozycję **Gotowe**.
11.  Opcjonalnie kliknij pozycję **Udziel uprawnień** w bloku Wymagane uprawnienia. Spowoduje to zezwolenie na dostęp do wszystkich kont w bieżącym katalogu. Dzięki temu okno dialogowe zgody nie będzie wyświetlane dla każdego użytkownika w dzierżawie. Aby uzyskać więcej informacji, zobacz [Integrowanie aplikacji z usługą Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).
12.  Kliknij przycisk **Tak**.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Pobieranie danych z interfejsu API usługi Microsoft Intune przy użyciu narzędzia Postman

Możesz pracować z interfejsem API magazynu danych usługi Intune przy użyciu ogólnego klienta REST takiego jak narzędzie Postman. Narzędzie Postman może zapewniać wgląd w funkcje interfejsu API i źródłowy model danych OData oraz rozwiązywać problemy dotyczące połączenia z zasobami interfejsu API. W tej sekcji znajdziesz informacje dotyczące generowania tokenu OAuth 2.0 dla klienta lokalnego. Klient będzie potrzebował tokenu do uwierzytelnienia w usłudze Azure AD i uzyskania dostępu do zasobów interfejsu API.

### <a name="information-you-will-need-to-make-the-call"></a>Informacje potrzebne do wykonania wywołania

Do wykonania wywołania REST przy użyciu narzędzia Postman potrzebne są następujące informacje:

| Atrybut        | Opis                                                                                                                                                                          | Przykład                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Adres URL wywołania zwrotnego     | Ustaw ten adres jako adres URL wywołania zwrotnego na stronie ustawień aplikacji.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Nazwa tokenu       | Ciąg, przy użyciu którego poświadczenia są przekazywane do aplikacji platformy Azure. Ten proces wygeneruje token, aby możliwe było wywołanie interfejsu API magazynu danych.                          | Bearer                                                                                        |
| Adres URL uwierzytelniania         | To jest adres URL używany do uwierzytelniania. | https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com |
| Adres URL tokenu dostępu | To jest adres URL używany do przyznawania tokenu.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| Identyfikator klienta        | Został utworzony i zanotowany podczas tworzenia aplikacji natywnej na platformie Azure.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Klucz tajny klienta    | Został utworzony i zanotowany podczas dodawania klucza do aplikacji klienckiej na platformie Azure.                                                                                              | JZoRZGPmN9xwsUnfX9UW877dkV5Fn/qQClhr7SuyMUQ=                                                  |
| Zakres (opcjonalnie) | Pusty                                                                                                                                                                               | Pole może pozostać puste.                                                                     |
| Typ udzielenia       | Token jest kodem autoryzacji.                                                                                                                                                  | Kod autoryzacji                                                                            |

Potrzebny jest punkt końcowy. W tym przykładzie pobierzemy dane z obiektu **dates**. Obiekt **dates** ma następujący format: `https://fef.{aus}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`. Użyjesz swojego adresu URL zarządzania dzierżawą. Adresu URL zarządzania dzierżawą użyto podczas tworzenia aplikacji internetowej.

### <a name="make-the-rest-call"></a>Wykonywanie wywołania REST

Aby uzyskać nowy token dostępu dla narzędzia Postman, należy dodać adres URL autoryzacji usługi Azure AD, identyfikator klienta oraz klucz tajny klienta. Narzędzie Postman załaduje stronę autoryzacji, na której wpiszesz swoje poświadczenia.

#### <a name="add-the-information-used-to-request-the-token"></a>Dodawanie informacji używanych do żądania tokenu

1.  Pobierz narzędzie Postman, jeśli jeszcze nie masz go zainstalowanego. Aby pobrać narzędzie Postman, odwiedź stronę [www.getpostman.com](https://www.getpostman.com).
2.  Otwórz narzędzie Postman. Wybierz operację HTTP **GET**.
3.  Wklej adres URL punktu końcowego do adresu. Powinien wyglądać następująco:  

    `https://fef.msua06.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  Wybierz kartę **Authorization** (Autoryzacja) i z listy **Type** (Typ) wybierz pozycję **OAuth 2.0**.
5.  Kliknij pozycję **Get New Access Token** (Uzyskaj nowy token dostępu).
6.  Sprawdź, czy dodano już adresu URL wywołania zwrotnego do aplikacji na platformie Azure. Adres URL wywołania zwrotnego to `https://www.getpostman.com/oauth2/callback`.
7.  W polu **Token name** (Nazwa tokenu) wpisz Bearer.
8.  W polu **Auth URL** (Adres URL autoryzacji) wprowadź adres URL autoryzacji. Powinien wyglądać następująco:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com`
9.  W polu **Access Token URL** (Adres URL tokenu dostępu) wprowadź adres URL tokenu dostępu. Powinien wyglądać następująco:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. W polu **Client ID** (Identyfikator klienta) wprowadź identyfikator klienta z aplikacji natywnej o nazwie `Intune Data Warehouse Client` utworzonej na platformie Azure. Powinien wyglądać następująco:  

     `4184c61a-e324-4f51-83d7-022b6a81b991`

11. W polu **Client Secret** (Klucz tajny klienta) wprowadź klucz tajny klienta określony podczas tworzenia aplikacji natywnej na platformie Azure. Powinien wyglądać następująco: 

     `F360R69M0MS72OB6YAqTyXO9MsXZx/OJTgAE2HB4k2k=`

12. Wybierz pozycje **Authorization Code** (Kod autoryzacji) i Request access token locally (Zażądaj tokenu dostępu lokalnie).

13. Kliknij pozycję **Request Token** (Zażądaj tokenu).

    ![Informacje dla tokenu](media\reports-postman_getnewtoken.png)

14. Wpisz swoje poświadczenia na stronie autoryzacji usługi Azure AD. Lista istniejących tokenów w narzędziu Postman zawiera teraz token o nazwie `Bearer`.
16. Wybierz ten token. Wybierz **nagłówek** (header), do którego ma zostać dodany token.
17. Kliknij pozycję **Use token** (Użyj tokenu). Lista nagłówków zawiera nową wartość klucza autoryzacji i wartość `Bearer <your-authorization-token>`.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>Wysyłanie wywołania do punktu końcowego przy użyciu narzędzia Postman

1.  Kliknij pozycję **Wyślij**.
2.  Dane zwrotne zostaną wyświetlone w treści odpowiedzi narzędzia Postman.

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>Tworzenie klienta REST (C#) do pobierania danych z magazynu danych usługi Intune

Następujący przykład zawiera prostego klienta REST. W kodzie użyto klasy **httpClient** z biblioteki .Net. Gdy klient uzyska poświadczenia usługi Azure AD, konstruuje wywołanie GET REST w celu pobrania obiektu dates z interfejsu API magazynu danych.

> [!Note]  
> Możesz skorzystać z następującego [przykładowego kodu w serwisie GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs). Zapoznaj się z repozytorium GitHub, aby poznać najnowsze zmiany i aktualizacje w przykładzie.

1.  Otwórz program **Microsoft Visual Studio**.
2.  Wybierz pozycję **Plik** > **Nowy projekt**. Rozwiń pozycję **Visual C#** i wybierz pozycję **Aplikacja konsoli (.NET Framework)**. 
3.  Nadaj projektowi nazwę ` IntuneDataWarehouseSamples`, przejdź do lokalizacji, w której chcesz zapisać projekt, i kliknij przycisk **OK**.
4.  Kliknij prawym przyciskiem myszy nazwę rozwiązania w Eksploratorze rozwiązań, a następnie wybierz pozycję **Zarządzaj pakietami NuGet rozwiązania**. Kliknij pozycję **Przeglądaj**, a następnie wpisz `Microsoft.IdentityModel.Clients.ActiveDirectory` w polu wyszukiwania.
5. Wybierz pakiet, wybierz projekt **IntuneDataWarehouseSamples** w obszarze Zarządzaj pakietami dla rozwiązania, a następnie kliknij pozycję **Zainstaluj**. 
6. Kliknij pozycję **Akceptuję**, aby zaakceptować licencję pakietu NuGet.
7. Otwórz plik `Program.cs` z poziomu Eksploratora rozwiązań.

    ![Projekt w programie Visual Studio](media\reports-get_rest_data_in.png)

8.  Zastąp kod w pliku Program.cs następującym kodem:  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal.
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```

9.  Zaktualizuj elementy `TODO` w przykładowym kodzie.
10.  Naciśnij klawisze **Ctrl + F5**, aby skompilować i uruchomić klienta Intune.DataWarehouseAPIClient w trybie debugowania.

    ![Obiekt dates pobrany w formacie JSON.](media\reports-get_rest_data_output.png)

11.  Przejrzyj dane wyjściowe z konsoli. Dane wyjściowe zawierają dane w formacie JSON ściągniętym z obiektu **dates** w dzierżawie usługi Intune.

## <a name="next-steps"></a>Następne kroki

Szczegółowe informacje dotyczące autoryzacji, struktury adresu URL interfejsu API i punktów końcowych OData znajdziesz w artykule [Korzystanie z interfejsu API magazynu danych usługi Intune](reports-api-url.md). 

Możesz także zapoznać się z modelem danych magazynu danych usługi Intune, aby znaleźć jednostki danych zawarte w interfejsie API. Aby uzyskać więcej informacji, zobacz [Model danych interfejsu API magazynu danych usługi Intune](reports-ref-data-model.md)