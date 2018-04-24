---
title: Zarządzanie dostępem do sieci Web za pomocą aplikacji Managed Browser
titlesuffix: Microsoft Intune
description: Informacje o wdrażaniu aplikacji Managed Browser w celu ograniczenia przeglądania sieci Web i transferu danych sieci Web do innych aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 10278dd48552e280ebe7399a61033dfb04fbbd74
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Managed Browser to aplikacja służąca do przeglądania zasobów internetowych przeznaczona do użytku w organizacji i dostępna do pobrania z publicznych sklepów z aplikacjami. W przypadku skonfigurowania przy użyciu usługi Intune program Managed Browser może:
- służyć do uzyskiwania dostępu do firmowych witryn i aplikacji SaaS z użyciem logowania jednokrotnego za pośrednictwem usługi MyApps, chroniąc jednocześnie dane internetowe;
- zostać wstępnie skonfigurowany z użyciem listy adresów URL i domen w celu ograniczenia witryn, do których użytkownik może przejść w kontekście firmowym;
- zostać wstępnie skonfigurowany przy użyciu określonej strony głównej i zakładek.

Ta aplikacja jest zintegrowana z zestawem SDK usługi Intune, dlatego można do niej również zastosować zasady ochrony aplikacji, takie jak:
- Kontrolowanie użycia funkcji wycinania, kopiowania i wklejania
- Zapobieganie przechwytywaniu ekranu
- Zapewnienie, że linki do zawartości wybierane przez użytkowników są otwierane tylko w innych aplikacjach zarządzanych.

Aby uzyskać szczegółowe informacje, zobacz [Co to są zasady ochrony aplikacji](/intune/app-protection-policy.md)?

Te ustawienia można zastosować do:

- Urządzeń zarejestrowanych w usłudze Intune
- Urządzeń zarejestrowanych w innym produkcie MDM
- Urządzeń niezarządzanych

Jeśli użytkownicy zainstalują aplikację Managed Browser ze sklepu z aplikacjami, a usługa Intune nie będzie nią zarządzać, to aplikacja ta może służyć jako podstawowa przeglądarka sieci Web z obsługą logowania jednokrotnego za pośrednictwem witryny Microsoft MyApps. Użytkownicy są przekierowywani bezpośrednio do witryny MyApps, w której mogą wyświetlić wszystkie aprowizowane aplikacje SaaS.
Kiedy aplikacja Managed Browser nie jest zarządzana przez usługę Intune, nie może uzyskać dostępu do danych z innych aplikacji zarządzanych przez usługę Intune. 

Aplikacja Managed Browser nie obsługuje protokołu szyfrowania Secure Sockets Layer, wersja 3 (SSLv3).

Zasady programu Managed Browser można tworzyć dla następujących typów urządzeń:

-   Urządzenia z systemem Android 4 i nowszym

-   Urządzenia z systemem iOS w wersji 8.0 lub nowszej

>[!IMPORTANT]
>Od października 2017 r. aplikacja Intune Managed Browser w aplikacji dla systemu Android obsługuje tylko urządzenia z systemem Android 4.4 lub nowszym. Aplikacja Intune Managed Browser dla systemu iOS będzie obsługiwać wyłącznie urządzenia z systemem iOS 9.0 i nowszym.
>Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.


Program Intune Managed Browser obsługuje otwieranie zawartości sieci Web od [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="conditional-access-for-the-intune-managed-browser"></a>Dostęp warunkowy dla aplikacji Intune Managed Browser

Aplikacja Managed Browser jest teraz zatwierdzoną aplikacją kliencką dla dostępu warunkowego. Oznacza to, że możesz ograniczyć dostęp przeglądarki mobilnej do aplikacji internetowych połączonych z usługą Azure AD, aby użytkownicy mogli używać tylko aplikacji Managed Browser, a dostęp był zablokowany z innych niezabezpieczonych przeglądarek, takich jak Safari czy Chrome. Taką ochronę można zastosować do zasobów platformy Azure, takich jak usługi Exchange Online i SharePoint Online, portal usługi Office, a nawet witryny lokalne, które są dostępne dla użytkowników zewnętrznych za pośrednictwem [serwera proxy aplikacji usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). 

Aby ograniczyć aplikacje internetowe usługi Azure AD do używania aplikacji Intune Managed Browser na platformach urządzeń przenośnych, możesz utworzyć zasady dostępu warunkowego usługi Azure AD wymagające zatwierdzonych aplikacji klienckich. 

1. W witrynie Azure Portal wybierz pozycję **Azure Active Directory** > **Aplikacje dla przedsiębiorstw** > **Dostęp warunkowy** > **Nowe zasady**. 
2. Następnie wybierz pozycję **Udziel** w sekcji **Kontrole dostępów** bloku. 
3. Kliknij pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**. 
4. Kliknij pozycję **Wybierz** w bloku **Udziel**. Te zasady należy przypisać do aplikacji w chmurze, które mają być dostępne tylko dla aplikacji Intune Managed Browser.

    ![Azure AD — zasady dostępu warunkowego aplikacji Managed Browser](./media/managed-browser-conditional-access-01.png)

5. W sekcji **Przypisania** wybierz pozycję **Warunki** > **Aplikacje klienckie**. Zostanie wyświetlony blok **Aplikacje klienckie**.
6. Kliknij pozycję **Tak** w obszarze **Konfiguruj**, aby zastosować zasady do określonych aplikacji klienckich.
7. Sprawdź, czy jako aplikację kliencką wybrano pozycję **Przeglądarka**.

    ![Azure AD — Managed Browser — wybieranie aplikacji klienckich](./media/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Jeśli chcesz ograniczyć, które aplikacje natywne (aplikacje nie korzystające z przeglądarki) mają mieć dostęp do tych aplikacji w chmurze, możesz także zaznaczyć pozycję **Aplikacje mobilne i klienci stacjonarni**.

8. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**, a następnie wybierz użytkowników lub grupy, do których chcesz przypisać te zasady. 

    > [!NOTE]
    > Użytkownicy muszą również zostać objęci zasadami ochrony aplikacji usługi Intune. Aby uzyskać więcej informacji na temat tworzenia zasad ochrony aplikacji usługi Intune, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

9. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**, aby wybrać, które aplikacje mają być chronione przez te zasady.

Po skonfigurowaniu powyższych zasad użytkownicy będą musieli uzyskiwać dostęp do połączonych z usługą Azure AD aplikacji internetowych chronionych przez te zasady za pomocą aplikacji Intune Managed Browser. Jeśli użytkownicy spróbują użyć niezarządzanej przeglądarki w tym scenariuszu, zostanie wyświetlone powiadomienie o konieczności użycia aplikacji Intune Managed Browser.

Program Managed Browser nie obsługuje klasycznych zasad dostępu warunkowego. Aby uzyskać więcej informacji, zobacz artykuł [Migrate classic policies in the Azure portal (Migrowanie zasad klasycznych w witrynie Azure Portal)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration).

##  <a name="single-sign-on-to-azure-ad-connected-web-apps-in-the-intune-managed-browser"></a>Logowanie jednokrotne do aplikacji internetowych połączonych z usługą Azure AD w aplikacji Intune Managed Browser

Aplikacja Intune Managed Browser w systemach iOS i Android może teraz korzystać z logowania jednokrotnego do wszystkich aplikacji internetowych (SaaS i lokalnych), które są połączone z usługą Azure AD. Gdy w systemie iOS jest obecna aplikacja Microsoft Authenticator lub gdy w systemie Android jest obecna aplikacja Portal firmy usługi Intune, użytkownicy aplikacji Intune Managed Browser mogą uzyskiwać dostęp do aplikacji internetowych połączonych z usługą Azure AD bez konieczności ponownego wprowadzania poświadczeń.

Logowanie jednokrotne w aplikacji Intune Managed Browser wymaga, aby urządzenie było zarejestrowane przez aplikację Microsoft Authenticator w systemie iOS lub przez aplikację Portal firmy usługi Intune w systemie Android. Użytkownikom z aplikacją Authenticator lub Portal firmy usługi Intune zostanie wyświetlony monit o zarejestrowanie urządzenia, gdy przejdą do aplikacji internetowej połączonej z usługą Azure AD w aplikacji Intune Managed Browser, a ich urządzenie nie zostało jeszcze zarejestrowane przez inną aplikację. Po zarejestrowaniu urządzenia przy użyciu konta zarządzanego przez usługę Intune dla tego konta zostanie włączone logowanie jednokrotne dla aplikacji internetowych połączonych z usługą Azure AD. 

> [!NOTE]
> Rejestracja urządzenia to proste zaewidencjonowanie go w usłudze Azure AD. Nie wymaga pełnej rejestracji urządzenia ani nie daje działowi IT żadnych dodatkowych uprawnień na urządzeniu.

## <a name="create-a-managed-browser-app-configuration"></a>Tworzenie konfiguracji aplikacji Managed Browser

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3.  W bloku **Aplikacje mobilne** listy Zarządzaj wybierz pozycję **Zasady konfiguracji aplikacji**.
4.  W bloku **Zasady konfiguracji aplikacji** wybierz pozycję **Dodaj**.
5.  W bloku **Dodaj zasady konfiguracji** wypełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do ustawień konfiguracji aplikacji.
6.  Jako typ **rejestracji urządzenia** wybierz **Aplikacje zarządzane**.
7.  Wybierz pozycję **Wybierz wymagane aplikacje**, a następnie przejdź do bloku **Docelowe aplikacje** i wybierz pozycję **Managed Browser** dla systemu iOS, Android lub dla obu tych systemów.
8.  Wybierz pozycję **OK**, aby powrócić do bloku **Dodaj zasady konfiguracji**.
9.  Wybierz pozycję **Ustawienia konfiguracji**. W bloku **Konfiguracja** należy zdefiniować pary kluczy i wartości do dostarczania konfiguracji dla programu Managed Browser. Informacje na temat różnych par kluczy i wartości, które można zdefiniować, znajdują się w dalszych sekcjach tego artykułu.
10. Gdy wszystko będzie gotowe, wybierz pozycję **OK**.
11. W bloku **Dodaj zasady konfiguracji** wybierz pozycję **Dodaj**.
12. Nowa konfiguracja zostanie utworzona i wyświetlona w bloku **Konfiguracja aplikacji**.

>[!IMPORTANT]
>Obecnie aplikacja Managed Browser stosuje rejestrację automatyczną. Aby można było zastosować konfiguracje aplikacji, inna aplikacja na urządzeniu musi być już zarządzana przez zasady ochrony aplikacji usługi Intune.

## <a name="assign-the-configuration-settings-you-created"></a>Przypisywanie utworzonych ustawień konfiguracji

Ustawienia są przypisywane do grup użytkowników usługi Azure AD. Jeśli dany użytkownik ma zainstalowaną aplikację Managed Browser, aplikacja jest zarządzana z uwzględnieniem określonych ustawień.

1. Przejdź do bloku **Aplikacje mobilne** pulpitu nawigacyjnego zarządzania aplikacjami mobilnymi usługi Intune i wybierz pozycję **Zasady konfiguracji aplikacji**.
2. Z listy konfiguracji aplikacji wybierz tę, która ma zostać przypisana.
3. W następnym bloku wybierz pozycję **Przypisania**.
4. W bloku **Przypisania** wybierz grupę usługi Azure AD, do której chcesz przypisać konfigurację aplikacji, a następnie wybierz przycisk **OK**.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Jak skonfigurować ustawienia serwera proxy aplikacji dla aplikacji Managed Browser

Aplikacja Intune Managed Browser i [serwer proxy aplikacji usługi Azure AD]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) zapewniają wspólnie obsługę następujących scenariuszy możliwych w przypadku użytkowników urządzeń z systemami iOS oraz Android:

- Użytkownik pobiera aplikację Microsoft Outlook i loguje się w niej. Zasady ochrony aplikacji usługi Intune są stosowane automatycznie. Szyfrują one zapisane dane i uniemożliwiają użytkownikom przesyłanie plików firmowych do niezarządzanych aplikacji lub lokalizacji na urządzeniu. Kiedy użytkownik klika link do witryny intranetowej w aplikacji Outlook, można określić, aby link był otwierany w aplikacji Managed Browser, a nie w jakiejś innej przeglądarce. Aplikacja Managed Browser rozpoznaje, że ta witryna intranetowa została udostępniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Przed dotarciem do witryny intranetowej użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia za pomocą dowolnego obsługiwanego uwierzytelniania wieloskładnikowego i udzielenia dostępu warunkowego. Dana lokalizacja (której wcześniej nie można było znaleźć, jeśli użytkownik był zdalny) jest teraz dostępna, a link w aplikacji Outlook działa prawidłowo.
- Użytkownik zdalny otwiera aplikację Managed Browser i przechodzi do witryny intranetowej przy użyciu wewnętrznego adresu URL. Aplikacja Managed Browser rozpoznaje, że dana witryna intranetowa została udostępniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Przed dotarciem do witryny intranetowej użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia za pomocą dowolnego obsługiwanego uwierzytelniania wieloskładnikowego i udzielenia dostępu warunkowego. Dana lokalizacja (której wcześniej nie można było znaleźć, jeśli użytkownik był zdalny) jest teraz dostępna.

### <a name="before-you-start"></a>Przed rozpoczęciem

- Skonfiguruj wewnętrzne aplikacje przy użyciu serwera proxy aplikacji usługi Azure AD.
    - Aby skonfigurować serwer proxy aplikacji i publikować aplikacje, zobacz [dokumentację dotyczącą konfiguracji]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
- Wymagana jest aplikacja Managed Browser w wersji 1.2.0 lub nowszej.
- Użytkownicy aplikacji Managed Browser mają przypisane do aplikacji [zasady ochrony aplikacji usługi Intune]( app-protection-policy.md).

    > [!NOTE]
    > Zanim zaktualizowane dane przekierowania serwera proxy aplikacji zaczną obowiązywać w aplikacji Managed Browser, może minąć do 24 godzin.


#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>Krok 1. Włączenie automatycznego przekierowania do aplikacji Managed Browser z poziomu programu Outlook
Program Outlook musi być skonfigurowany przy użyciu zasad ochrony aplikacji, które powodują włączenie ustawienia **Ogranicz zawartość sieci Web wyświetlaną w programie Managed Browser**.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>Krok 2. Przypisanie zasad konfiguracji aplikacji przypisanych do aplikacji Managed Browser.
Ta procedura umożliwia skonfigurowanie aplikacji Managed Browser, aby korzystała z przekierowywania serwera proxy aplikacji. Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser podaj następującą parę klucza i wartości:

|||
|-|-|
|Klucz|Wartość|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|

Aby uzyskać więcej informacji o sposobie używania aplikacji Managed Browser w połączeniu z serwerem proxy aplikacji usługi Azure AD w celu zapewnienia bezproblemowego (i bezpiecznego) dostępu do lokalnych aplikacji internetowych, zobacz wpis w blogu usług Enterprise Mobility + Security [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Razem lepiej: usługi Intune i Azure Active Directory łączą siły, aby zapewnić lepszy dostęp użytkownikom).

## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>Jak skonfigurować stronę główną dla aplikacji Managed Browser

To ustawienie pozwala skonfigurować stronę główną, którą widzą użytkownicy po uruchomieniu aplikacji Managed Browser lub utworzeniu nowej karty. Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser podaj następującą parę klucza i wartości:


|                                                                   |                                                                                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
|                                Klucz                                |                                                           Wartość                                                            |
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Określ prawidłowy adres URL. Niepoprawne adresy URL są blokowane ze względów bezpieczeństwa.<br>Przykład: <strong><https://www.bing.com></strong> |

## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>Jak skonfigurować zakładki dla aplikacji Managed Browser

To ustawienie służy do konfigurowania zestawu zakładek dostępnego dla użytkowników w aplikacji Managed Browser.

- Użytkownicy nie mogą usunąć ani zmodyfikować tych zakładek.
- Te zakładki są wyświetlane na początku listy. Wszystkie zakładki utworzone przez użytkowników są wyświetlane poniżej tych zakładek.
- Jeśli zostało włączone przekierowanie serwera proxy aplikacji, możesz dodać aplikacje internetowe serwera proxy aplikacji, używając ich wewnętrznego lub zewnętrznego adresu URL.

Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser podaj następującą parę klucza i wartości:


|                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                Klucz                                 |                                                                                                                                                                                                                                                         Wartość                                                                                                                                                                                                                                                          |
| <strong>com.microsoft.intune.mam.managedbrowser.bookmarks</strong> | Wartość dla tej konfiguracji to lista zakładek. Każda zakładka składa się z tytułu zakładki i jej adresu URL. Tytuł i adres URL oddziel za pomocą znaku <strong>&#124;</strong>.<br><br>Przykład: <strong>Microsoft Bing&#124;<https://www.bing.com></strong><br><br>Aby skonfigurować wiele zakładek, każdą parę należy rozdzielić podwójnym znakiem <strong>&#124;&#124;</strong><br><br>Przykład: <strong>Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;<https://www.contoso.com></strong> |

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Jak określać dozwolone i blokowane adresy URL programu Managed Browser

Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser podaj następującą parę klucza i wartości:


|                                                                                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                               Klucz                                                                                                                                                                |                                                                                                                                                                                    Wartość                                                                                                                                                                                    |
| Wybierz spośród opcji:<br><br>- Określ dozwolone adresy URL (dozwolone będą wyłącznie te i żadne inne adresy URL; tylko do nich będzie można uzyskać dostęp): <strong>com.microsoft.intune.mam.managedbrowser.AllowListURLs</strong><br><br>- Określ zablokowane adresy URL (wszystkie inne witryny będą dostępne): <br><br><strong>com.microsoft.intune.mam.managedbrowser.BlockListURLs</strong> | Wartość klucza to lista adresów URL. Wszystkie adresy URL, które mają być dozwolone lub blokowane, należy wprowadzać jako pojedyncze wartości rozdzielane znakiem pionowej kreski <strong>&#124;</strong>.<br><br>Przykłady:<br><br><strong>URL1&#124;URL2&#124;URL3</strong><br><strong>http://<em>.contoso.com/</em>&#124;https://<em>.bing.com/</em>&#124;<https://expenses.contoso.com></strong> |

>[!IMPORTANT]
>Należy zdefiniować tylko jeden z tych kluczy. Jeśli dla tego samego użytkownika zostaną zdefiniowane oba klucze, zostanie użyty tylko klucz określający dostępne adresy URL jako bardziej restrykcyjny.
>Ponadto należy upewnić się, że nie są blokowane ważne strony, takie jak firmowe witryny sieci Web.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Format adresu URL dla dozwolonych i zablokowanych adresów URL
Poniższe informacje dotyczą dopuszczalnych formatów i symboli wieloznacznych, których można używać podczas określania adresów URL na listach witryn dozwolonych i zablokowanych:

- Symbol wieloznaczny (**&#42;**) może być używany zgodnie z regułami z poniższej listy dozwolonych wzorców:

- Upewnij się, że wszystkie adresy URL dodawane do listy będą mieć prefiks **http** lub **https** .

- W adresie można określić numery portów. Jeśli nie określisz numeru portu, będą używane następujące wartości:

  -   Port 80 dla protokołu http

  -   Port 443 dla protokołu https

  Symboli wieloznacznych nie można używać w numerze portu. Na przykład adresy <strong>http&colon;//www&period;contoso&period;com:*;</strong> i <strong>http&colon;//www&period;contoso&period;com: /*;</strong> nie są obsługiwane.

- W poniższej tabeli przedstawiono dozwolone wzorce do użycia podczas określania adresów URL:

|                  Adres URL                  |                     Szczegóły                      |                                                Jest zgodny z                                                |                                Nie jest zgodny z                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        http://www.contoso.com         |              Zgodny z pojedynczą stroną               |                                            www.contoso.com                                            |  host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/   |
|          http://contoso.com           |              Zgodny z pojedynczą stroną               |                                             contoso.com/                                              | host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com |
|    <http://www.contoso.com/&#42>;     | Zgodny ze wszystkimi adresami URL rozpoczynającymi się od www.contoso.com |      www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows      |              host.contoso.com<br /><br />host.contoso.com/images              |
|    http://&#42;.contoso.com/&#42;     |     Zgodny ze wszystkimi domenami podrzędnymi w domenie contoso.com     | developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos |                               contoso.host.com                                |
|     http://www.contoso.com/images     |             Zgodny z pojedynczym folderem              |                                        www.contoso.com/images                                         |                          www.contoso.com/images/dogs                          |
|       http://www.contoso.com:80       |  Zgodny z pojedynczą stroną z użyciem numeru portu   |                                       http://www.contoso.com:80                                       |                                                                               |
|        https://www.contoso.com        |          Zgodny z pojedynczą, bezpieczną stroną           |                                        https://www.contoso.com                                        |                            http://www.contoso.com                             |
| <http://www.contoso.com/images/&#42>; |    Zgodny z pojedynczym folderem ze wszystkimi podfolderami    |                  www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats                   |                            www.contoso.com/videos                             |

- Poniżej przedstawiono przykłady niektórych niedozwolonych wzorców:

  - &#42;.com

  - &#42;.contoso/&#42;

  - www.contoso.com/&#42;images

  - www.contoso.com/&#42;images&#42;pigs

  - www.contoso.com/page&#42;

  - Adresy IP

  - https://&#42;

  - http://&#42;

  - http://www.contoso.com:&#42;

  - http://www.contoso.com: /&#42;

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>Jak uzyskać dostęp do dzienników zarządzanych aplikacji przy użyciu programu Managed Browser w systemie iOS

Użytkownicy końcowi z zainstalowanym programem Managed Browser na urządzeniu z systemem iOS mogą wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft. Mogą one wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS.

1. Otwórz **Ustawienia** systemu iOS.
2. Wybierz ustawienia aplikacji Managed **Browser**.
3. Przełącz opcję **Włącz diagnostykę usługi Intune**, aby ustawić przeglądarkę w trybie rozwiązywania problemów.
4. Otwórz program Managed **Browser**. Kliknij przycisk **Wyświetl stan aplikacji usługi Intune**, aby przejrzeć ustawienia zasad poszczególnych aplikacji.
5. Naciśnij pozycję **Rozpocznij pracę** i **Udostępnij dzienniki** lub **Wyślij dzienniki do firmy Microsoft**, aby wysłać dzienniki rozwiązywania problemów do firmy Microsoft lub administratora IT.

Możesz również otworzyć przeglądarkę w trybie rozwiązywania problemów z poziomu aplikacji.

1. Otwórz program Managed Browser.
2. Wpisz `about:intunehelp` w polu adresu.
Przeglądarka zostanie uruchomiona w trybie rozwiązywania problemów.

Aby uzyskać listę ustawień przechowywanych w dziennikach aplikacji, zobacz temat [Przeglądanie dzienników ochrony aplikacji w programie Managed Browser](app-protection-policy-settings-log.md).

## <a name="security-and-privacy-for-the-managed-browser"></a>Zabezpieczenia i prywatność programu Managed Browser

-   Ustawienia przeglądarki wbudowanej na urządzeniach użytkowników nie są używane w programie Managed Browser. Aplikacja Managed Browser nie ma dostępu do tych ustawień.

-   Jeśli w zasadach ochrony aplikacji skojarzonych z programem Managed Browser są skonfigurowane opcje **Wymagaj prostego numeru PIN w celu udzielenia dostępu** lub **Wymagaj poświadczeń firmowych w celu udzielenia dostępu**, a użytkownik wybierze link Pomoc na stronie uwierzytelniania, umożliwi to przeglądanie dowolnych witryn internetowych bez względu na to, czy zostały one dodane w zasadach do listy blokowanych witryn.

-   Program Managed Browser może zablokować dostęp do witryn tylko w przypadku uzyskiwania do nich bezpośredniego dostępu. Dostęp do witryny nie jest blokowany, jeśli jest on uzyskiwany za pomocą usług pośrednich (na przykład usługi tłumaczenia).

-   W celu umożliwienia uwierzytelniania i uzyskania dostępu do dokumentacji usługi Intune, witryna **&#42;.microsoft.com** jest wyłączona z ustawień listy dozwolonych lub zablokowanych witryn. Jest ona zawsze dozwolona.

### <a name="turn-off-usage-data"></a>Wyłączanie danych użycia
Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z programu Managed Browser w celu ulepszania swoich produktów i usług. Użytkownicy mogą wyłączyć zbieranie danych przy użyciu ustawienia **Dane użycia** na swoich urządzeniach. Użytkownik nie kontroluje zbierania tych danych.


-   Na urządzeniach z systemem iOS nie można otwierać odwiedzanych przez użytkowników witryn sieci Web z certyfikatem nieważnym lub niezaufanym.
-   Ustawienia przeglądarki wbudowanej na urządzeniach użytkowników nie są używane w programie Managed Browser. Aplikacja Managed Browser nie ma dostępu do tych ustawień.

-   Jeśli w zasadach ochrony aplikacji skojarzonych z programem Managed Browser są skonfigurowane opcje **Wymagaj prostego numeru PIN w celu udzielenia dostępu** lub **Wymagaj poświadczeń firmowych w celu udzielenia dostępu**, a użytkownik wybierze link Pomoc na stronie uwierzytelniania, umożliwi to przeglądanie dowolnych witryn internetowych bez względu na to, czy zostały one dodane w zasadach do listy blokowanych witryn.

-   Program Managed Browser może zablokować dostęp do witryn tylko w przypadku uzyskiwania do nich bezpośredniego dostępu. Dostęp do witryny nie jest blokowany, jeśli jest on uzyskiwany za pomocą usług pośrednich (na przykład usługi tłumaczenia).

-   W celu umożliwienia uwierzytelniania i uzyskania dostępu do dokumentacji usługi Intune, witryna **&#42;.microsoft.com** jest wyłączona z ustawień listy dozwolonych lub zablokowanych witryn. Jest ona zawsze dozwolona.

### <a name="turn-off-usage-data"></a>Wyłączanie danych użycia
Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z programu Managed Browser w celu ulepszania swoich produktów i usług. Użytkownicy mogą wyłączyć zbieranie danych przy użyciu ustawienia **Dane użycia** na swoich urządzeniach. Użytkownik nie kontroluje zbierania tych danych.

## <a name="next-steps"></a>Następne kroki

- [Co to są zasady ochrony aplikacji?](app-protection-policy.md)
