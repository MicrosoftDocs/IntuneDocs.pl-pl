---
title: Zarządzanie dostępem do Internetu przy użyciu przeglądarki Microsoft Edge w usłudze Microsoft Intune
titleSuffix: ''
description: Używaj zasad ochrony aplikacji usługi Intune z przeglądarką Microsoft Edge, aby upewnić się, że dostęp do firmowych witryn internetowych będzie zawsze uzyskiwany z zastosowaniem środków bezpieczeństwa.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50574a2d3dc4ba5731b1a90f563ddd1a08e7f833
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529643"
---
# <a name="manage-web-access-using-microsoft-edge-with-microsoft-intune"></a>Zarządzanie dostępem do Internetu przy użyciu przeglądarki Microsoft Edge w usłudze Microsoft Intune

Używanie zasad ochrony aplikacji usługi Intune z przeglądarką Microsoft Edge może zapewnić, że dostęp do firmowych witryn internetowych będzie zawsze uzyskiwany z zastosowaniem środków bezpieczeństwa. W przedsiębiorstwie dostępne są następujące funkcje przeglądarki Microsoft Edge włączane przy użyciu zasad usługi Intune. Te funkcje przedsiębiorstwa to na przykład:

1. **Podwójna tożsamość** — użytkownicy mogą dodawać konta służbowe i osobiste na potrzeby przeglądania. Te dwie tożsamości są całkowicie oddzielone, co przypomina architekturę i środowisko usługi Office 365 oraz programu Outlook. Administratorzy usługi Intune będą mogli ustawić żądane zasady dla chronionego środowiska przeglądania w ramach konta służbowego.
2. **Integracja zasad ochrony aplikacji usługi Intune** — ponieważ przeglądarka Microsoft Edge jest zintegrowana z zestawem SDK usługi Intune, można określić zasady ochrony aplikacji, aby zapewnić ochronę przed utratą danych. Te możliwości obejmują kontrolowanie użycia funkcji wycinania, kopiowania i wklejania, zapobieganie przechwytywaniu ekranu oraz zapewnianie, że wybierane przez użytkowników linki są otwierane tylko w innych zarządzanych aplikacjach.
3. **Integracja serwera proxy aplikacji platformy Azure** — możesz kontrolować dostęp do aplikacji SaaS i aplikacji internetowych, co pomaga zagwarantować, że tylko aplikacje oparte na przeglądarce będą uruchamiane w bezpiecznej przeglądarce Microsoft Edge, bez względu na to, czy użytkownicy końcowi nawiązują połączenie z sieci firmowej, czy też z Internetu.
4. **Konfiguracja aplikacji** — można używać ustawień konfiguracji aplikacji w celu zwiększania poziomu bezpieczeństwa organizacji i konfigurowania łatwych w użyciu funkcji dla użytkowników końcowych. Można na przykład można zdefiniować zakładki, skrót do strony głównej, witryny dozwolone/zablokowane, serwer proxy aplikacji platformy Azure i inne elementy.
Zasady ochrony usługi Microsoft Intune dla przeglądarki Microsoft Edge pomagają w ochronie danych i zasobów organizacji. Użycie tych zasad z przeglądarką Microsoft Edge zapewnia, że zasoby firmy są chronione nie tylko w aplikacjach zainstalowanych natywnie, ale także gdy dostęp jest uzyskiwany za pośrednictwem przeglądarki internetowej.

## <a name="getting-started"></a>Wprowadzenie

Ty i Twoi użytkownicy końcowi możecie pobrać przeglądarkę Microsoft Edge z publicznych sklepów z aplikacjami i korzystać z niej w organizacji. Wymagania zasad przeglądarki dotyczące systemu operacyjnego:
- system Android (4 lub nowszy) lub
- System iOS 8.0 i nowsze

## <a name="application-protection-policies-for-microsoft-edge"></a>Zasady ochrony aplikacji dla przeglądarki Microsoft Edge

Przeglądarka Microsoft Edge jest zintegrowana z zestawem SDK usługi Intune, dlatego można do niej zastosować zasady ochrony aplikacji, takie jak:
- Kontrolowanie użycia funkcji wycinania, kopiowania i wklejania.
- Zapobieganie przechwytywaniu ekranu.
- Zapewnianie otwierania linków firmowych tylko w ramach zarządzanych aplikacji i przeglądarek.

Aby uzyskać szczegółowe informacje, zobacz temat Co to są zasady ochrony aplikacji?
Te ustawienia można zastosować do:
- Urządzeń zarejestrowanych w usłudze Intune
- Urządzeń zarejestrowanych w innym produkcie MDM
- Urządzeń niezarządzanych

Jeśli przeglądarka Microsoft Edge nie jest docelowym programem zasad usługi Intune, użytkownicy nie mogą używać jej do uzyskiwania dostępu do danych z innych aplikacji zarządzanych przez usługę Intune, takich jak aplikacje pakietu Office. 

## <a name="conditional-access-for-microsoft-edge"></a>Dostęp warunkowy dla przeglądarki Microsoft Edge

Możesz korzystać z dostępu warunkowego usługi Azure AD, aby przekierowywać użytkowników tak, aby uzyskiwali dostęp do zawartości firmowej tylko za pośrednictwem przeglądarki Microsoft Edge. Spowoduje to ograniczenie dostępu przeglądarki mobilnej do aplikacji internetowych połączonych z usługą Azure AD do przeglądarki Microsoft Edge chronionej przez zasady, po czym dostęp z innych niezabezpieczonych przeglądarek, takich jak Safari czy Chrome, zostanie zablokowany. Dostęp warunkowy można zastosować do zasobów platformy Azure, takich jak usługi Exchange Online i SharePoint Online, centrum administracyjne platformy Microsoft 365, a nawet witryny lokalne, które są dostępne dla użytkowników zewnętrznych za pośrednictwem [serwera proxy aplikacji usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Aby ograniczyć aplikacje internetowe połączone z usługą Azure AD w celu używania przeglądarki Microsoft Edge w systemach iOS i Android, wykonaj następujące czynności:
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W węźle usługi Intune wybierz kolejno pozycje **Dostęp warunkowy** > **Nowe zasady**.
3. Następnie wybierz pozycję **Udziel** w sekcji **Kontrole dostępów** bloku.
4. Kliknij pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**.
5. Kliknij pozycję **Wybierz** w bloku **Udziel**. Te zasady należy przypisać do aplikacji w chmurze, które mają być dostępne tylko dla aplikacji Intune Managed Browser.

    ![Zasady dostępu warunkowego — udzielanie](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. W sekcji Przypisania wybierz pozycję Warunki > Aplikacje klienckie. Zostanie wyświetlony blok Aplikacje klienckie.
7. Kliknij pozycję Tak w obszarze Konfiguruj, aby zastosować zasady do określonych aplikacji klienckich.
8. Sprawdź, czy jako aplikację kliencką wybrano pozycję Przeglądarka.

    ![Zasady dostępu warunkowego — wybieranie aplikacji klienckich](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Jeśli chcesz ograniczyć, które aplikacje natywne (aplikacje nie korzystające z przeglądarki) mają mieć dostęp do tych aplikacji w chmurze, możesz także zaznaczyć pozycję **Aplikacje mobilne i klienci stacjonarni**.

9. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**, a następnie wybierz użytkowników lub grupy, do których chcesz przypisać te zasady.

    > [!NOTE]
    > Użytkownicy muszą również zostać objęci zasadami Intune App Protection w celu odbierania zasad konfiguracji aplikacji. Aby uzyskać więcej informacji na temat tworzenia zasad ochrony aplikacji usługi Intune, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

10. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**, aby wybrać, które aplikacje mają być chronione przez te zasady.

Po skonfigurowaniu powyższych zasad użytkownicy będą musieli uzyskiwać dostęp do połączonych z usługą Azure AD aplikacji internetowych chronionych przez te zasady za pomocą przeglądarki Microsoft Edge. Jeśli użytkownicy spróbują użyć niezarządzanej przeglądarki w tym scenariuszu, zostanie wyświetlony komunikat o konieczności użycia przeglądarki Microsoft Edge.

> [!TIP]
> Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure Active Directory (Azure AD). Węzeł Dostęp warunkowy dostępny z usługi Intune jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Logowanie jednokrotne do aplikacji internetowych połączonych z usługą Azure AD w przeglądarkach zabezpieczonych przy użyciu zasad

Przeglądarka Microsoft Edge w systemach iOS i Android może teraz korzystać z logowania jednokrotnego do wszystkich aplikacji internetowych (SaaS i lokalnych), które są połączone z usługą Azure AD. Logowanie jednokrotne umożliwia użytkownikom dostęp do aplikacji internetowych połączonych z usługą Azure AD za pośrednictwem przeglądarki Microsoft Edge bez konieczności ponownego wprowadzania poświadczeń.

Logowanie jednokrotne wymaga, aby urządzenie było zarejestrowane przez aplikację Microsoft Authenticator dla urządzeń z systemem iOS lub przez aplikację Portal firmy usługi Intune w systemie Android. Jeśli użytkownicy mają aplikację Authenticator lub Portal firmy usługi Intune, otrzymają monit o zarejestrowanie urządzenia, gdy przejdą do aplikacji internetowej połączonej z usługą Azure AD w przeglądarce zabezpieczonej przy użyciu zasad, w przypadku gdy urządzenie nie zostało jeszcze zarejestrowane. Po zarejestrowaniu urządzenia przy użyciu konta użytkownika zarządzanego przez usługę Intune dla tego konta zostanie włączone logowanie jednokrotne dla aplikacji internetowych połączonych z usługą Azure AD.

> [!NOTE]
> Rejestracja urządzenia to proste zaewidencjonowanie go w usłudze Azure AD. Nie wymaga pełnej rejestracji urządzenia ani nie daje działowi IT żadnych dodatkowych uprawnień na urządzeniu.

## <a name="create-a-protected-browser-app-configuration"></a>Tworzenie konfiguracji aplikacji przeglądarki chronionej

Aby można było zastosować konfiguracje aplikacji, chroniona przeglądarka użytkownika lub inna aplikacja na urządzeniu musi być już zarządzana przez [zasady ochrony aplikacji usługi Intune](app-protection-policy.md).

Poniższe kroki umożliwiają tworzenie konfiguracji chronionych aplikacji przeglądarki:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** > **Dodaj**.
3. W bloku **Dodaj zasady konfiguracji** wypełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do ustawień konfiguracji aplikacji.
4. Jako typ **rejestracji urządzenia** wybierz **Aplikacje zarządzane**.
5. Wybierz pozycję **Wybierz wymagane aplikacje**, a następnie przejdź do bloku **Docelowe aplikacje** i wybierz pozycję **Managed Browser** i/lub **Microsoft Edge** dla systemu iOS, Android lub dla obu tych systemów.
6. Wybierz pozycję **OK**, aby powrócić do bloku **Dodaj zasady konfiguracji**.
7. Wybierz pozycję **Ustawienia konfiguracji**. W bloku **Konfiguracja** należy zdefiniować pary kluczy i wartości do dostarczania konfiguracji dla przeglądarki Microsoft Edge. Informacje na temat różnych par kluczy i wartości, które można zdefiniować, znajdują się w dalszych sekcjach tego artykułu.

    > [!NOTE]
    > Aplikacja Microsoft Edge używa tych samych par klucza i wartości co aplikacja Managed Browser. 

8. Gdy wszystko będzie gotowe, kliknij przycisk **OK**.
9. W bloku **Dodaj zasady konfiguracji** wybierz pozycję **Dodaj**.<br>
    Nowa konfiguracja zostanie utworzona i wyświetlona w bloku **Konfiguracja aplikacji**.

## <a name="assign-the-configuration-settings-you-created"></a>Przypisywanie utworzonych ustawień konfiguracji 

Ustawienia są przypisywane do grup użytkowników usługi Azure AD. Jeśli dany użytkownik ma zainstalowaną docelową aplikację przeglądarki chronionej, aplikacja jest zarządzana z uwzględnieniem określonych ustawień.

1. Przejdź do bloku **Aplikacje klienckie** pulpitu nawigacyjnego zarządzania aplikacjami mobilnymi usługi Intune i wybierz pozycję **Zasady konfiguracji aplikacji**.
2. Z listy konfiguracji aplikacji wybierz tę, która ma zostać przypisana.
3. W następnym bloku wybierz pozycję **Przypisania**.
4. W bloku **Przypisania** wybierz grupę usługi Azure AD, do której chcesz przypisać konfigurację aplikacji, a następnie wybierz przycisk **OK**.

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Jak skonfigurować ustawienia serwera proxy aplikacji dla przeglądarek chronionych

Przeglądarka Microsoft Edge i [serwer proxy aplikacji usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) mogą być używane razem, aby umożliwić użytkownikom dostęp do witryn intranetowych na ich urządzeniach przenośnych. 

Poniżej przedstawiono niektóre przykładowe scenariusze zastosowania serwer proxy aplikacji usługi Azure AD: 

- Użytkownik korzysta z aplikacji mobilnej Outlook, która jest chroniona przez usługę Intune. Następnie klika link do witryny intranetowej w wiadomości e-mail, a przeglądarka Microsoft Edge rozpoznaje, że dana witryna intranetowa została uwidoczniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Przed dotarciem do witryny intranetowej użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia za pomocą dowolnego obsługiwanego uwierzytelniania wieloskładnikowego i udzielenia dostępu warunkowego. Użytkownicy mogą teraz uzyskiwać dostęp do witryn wewnętrznych nawet na swoich urządzeniach przenośnych, a link w aplikacji Outlook działa zgodnie z oczekiwaniami.
- Użytkownik otwiera przeglądarkę Microsoft Edge na urządzeniu z systemem iOS lub Android. Jeśli przeglądarka Microsoft Edge jest chroniona za pomocą usługi Intune, a serwer proxy aplikacji został włączony, użytkownik może przejść do witryny intranetowej przy użyciu wewnętrznego adresu URL, do którego są przyzwyczajeni. Przeglądarka Microsoft Edge rozpoznaje, że dana witryna intranetowa została uwidoczniona użytkownikowi za pośrednictwem serwera proxy aplikacji, a użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia przed dotarciem do witryny intranetowej. 

### <a name="before-you-start"></a>Przed rozpoczęciem

- Skonfiguruj wewnętrzne aplikacje przy użyciu serwera proxy aplikacji usługi Azure AD.
    - Aby skonfigurować serwer proxy aplikacji i publikować aplikacje, zobacz [dokumentację dotyczącą konfiguracji](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Aplikacja Microsoft Edge musi mieć przypisane [zasady ochrony aplikacji usługi Intune](app-protection-policy.md).

> [!NOTE]
> Zanim zaktualizowane dane przekierowania serwera proxy aplikacji zaczną obowiązywać w aplikacji Managed Browser lub Microsoft Edge, może minąć do 24 godzin.

#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Krok 1. Włączenie automatycznego przekierowania do przeglądarki chronionej z poziomu programu Outlook
Program Outlook musi być skonfigurowany przy użyciu zasad ochrony aplikacji, które powodują włączenie ustawienia **Udostępniaj zawartość internetową za pomocą przeglądarek zarządzanych przez zasady**.

![Zasady ochrony aplikacji — udostępnianie zawartości internetowej za pomocą przeglądarek zarządzanych przez zasady](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Krok 2: Zdefiniowanie ustawienia konfiguracji aplikacji w celu włączenia serwera proxy aplikacji
W przeglądarce Microsoft Edge użyj poniższej pary klucz/wartość, aby włączyć serwer proxy aplikacji dla przeglądarki Microsoft Edge:

|    Klucz    |    Wartość    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true    |

Aby uzyskać więcej informacji o sposobie używania przeglądarki Microsoft Edge w połączeniu z serwerem proxy aplikacji usługi Azure AD w celu zapewnienia bezproblemowego (i bezpiecznego) dostępu do lokalnych aplikacji internetowych, zobacz wpis w blogu pakietu Enterprise Mobility + Security [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Razem lepiej: usługi Intune i Azure Active Directory łączą siły, aby zapewnić lepszy dostęp użytkownikom). Ten wpis w blogu odwołuje się do programu Intune Managed Browser, ale dotyczy również przeglądarki Microsoft Edge.

## <a name="how-to-configure-a-homepage-shortcut-for-microsoft-edge"></a>Jak skonfigurować skrót do strony głównej dla przeglądarki Microsoft Edge

To ustawienie umożliwia skonfigurowanie skrótu do strony głównej dla przeglądarki Microsoft Edge.  Skonfigurowany skrót do strony głównej będzie wyświetlany jako pierwsza ikona poniżej paska wyszukiwania po otwarciu nowej karty w przeglądarce Microsoft Edge. Użytkownik nie będzie mógł edytować ani usuwać tego skrótu w swoim kontekście zarządzanym. Wyświetlony skrót do strony głównej zostanie wyróżniony przy użyciu nazwy Twojej organizacji. 

Użyj poniższej pary klucz/wartość, aby skonfigurować skrót do strony głównej:

|    Klucz    |    Wartość    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Określ prawidłowy adres URL. Niepoprawne adresy URL są blokowane ze względów bezpieczeństwa.<br>**Przykład:** `<https://www.bing.com`>
    |

## <a name="how-to-configure-managed-bookmarks-for-microsoft-edge"></a>Jak skonfigurować zakładki zarządzane dla programu Microsoft Edge

W celu ułatwienia dostępu można skonfigurować zakładki, które mają być dostępne dla Twoich użytkowników, gdy będą korzystać z przeglądarki Microsoft Edge. Oto niektóre szczegóły:

- Te zakładki będą wyświetlane dla użytkowników tylko wtedy, gdy będą oni korzystać z trybu firmowego w przeglądarce Microsoft Edge. 
- Użytkownicy nie mogą usunąć ani zmodyfikować tych zakładek.
- Te zakładki są wyświetlane na początku listy. Wszystkie zakładki utworzone przez użytkowników są wyświetlane poniżej tych zakładek.
- Jeśli zostało włączone przekierowanie serwera proxy aplikacji, możesz dodać aplikacje internetowe serwera proxy aplikacji, używając ich wewnętrznego lub zewnętrznego adresu URL.

Użyj następujących par klucz/wartość w celu skonfigurowania zakładek zarządzanych:

|    Klucz    |    Wartość    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    Wartość dla tej konfiguracji to lista zakładek. Każda zakładka składa się z tytułu zakładki i jej adresu URL. Tytuł i adres URL oddziel za pomocą znaku `|`.      **Przykład:**<br>`Microsoft Bing|https://www.bing.com`<br>Aby skonfigurować wiele zakładek, każdą parę oddziel podwójnym znakiem `||`.<p>**Przykład:**<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="how-to-display-myapps-within-microsoft-edge-bookmarks"></a>Jak wyświetlić aplikację MyApps w ramach zakładek przeglądarki Microsoft Edge

Domyślnie użytkownicy będą widzieć witryny MyApps, które zostały dla nich skonfigurowane, w folderze wewnątrz zakładek przeglądarki Microsoft Edge. Folder będzie oznaczone etykietą z nazwą organizacji.

|    Klucz    |    Wartość    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    Wartość **true** powoduje wyświetlanie aplikacji MyApps w zakładkach przeglądarki Microsoft Edge.<p>Wartość **false** powoduje ukrywanie aplikacji MyApps w przeglądarce Microsoft Edge.    |

## <a name="how-to-specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Jak określić listę dozwolonych lub zablokowanych witryn przeglądarki Microsoft Edge
Do zdefiniowania witryn, do których Twoi użytkownicy będą mieć dostęp w profilu służbowym, możesz użyć konfiguracji aplikacji. Jeśli używasz listy dozwolonych, użytkownicy będą mieć dostęp tylko do witryn, które zostały jawnie wymienione. Jeśli używasz listy zablokowanych, użytkownicy będą mieć dostęp do wszystkich witryn z wyjątkiem jawnie zablokowanych. Należy zastosować listę dozwolonych lub listę zablokowanych, nie obydwie listy. Jeśli na urządzeniu zastosujesz obydwie listy, będzie uznawana lista dozwolonych.  

Możesz użyć poniższych par klucz/wartość, aby skonfigurować listę dozwolonych lub zablokowanych witryn dla przeglądarki Microsoft Edge. Kontynuuj czytanie, aby uzyskać więcej informacji o poprawnych formatach adresów URL. 

|    Klucz    |    Wartość    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Wybierz spośród opcji:<p>1. Określ dozwolone adresy URL (tylko te adresy URL są dozwolone; nie można uzyskać dostępu do żadnych innych witryn):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Określ zablokowane adresy URL (wszystkie inne witryny będą dostępne):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    Wartość klucza to lista adresów URL. Wszystkie adresy URL, które mają być dozwolone lub blokowane, należy wprowadzać jako pojedyncze wartości rozdzielane znakiem pionowej kreski `|`.<br>**Przykłady:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>Formaty adresów URL dla listy witryn dozwolonych i zablokowanych 
Możesz użyć różnych formatów adresów URL do tworzenia listy witryn dozwolonych/zablokowanych. Te dozwolone wzorce zostały szczegółowo opisane w poniższej tabeli. Przed rozpoczęciem pracy zapoznaj się z poniższymi uwagami: 
- Upewnij się, że wszystkie adresy URL dodawane do listy będą mieć prefiks **http** lub **https**.
- Symbol wieloznaczny (\*) może być używany zgodnie z regułami z poniższej listy dozwolonych wzorców.
- Symbol wieloznaczny może odpowiadać wyłącznie całemu składnikowi nazwy hosta (oddzielane kropkami) lub całym częściom ścieżki (oddzielane ukośnikami). Na przykład adres `http://*contoso.com` **nie** jest obsługiwany.
- W adresie można określić numery portów. Jeśli nie określisz numeru portu, będą używane następujące wartości:
    - Port 80 dla protokołu http
    - Port 443 dla protokołu https
- Symboli wieloznacznych **nie** można używać w numerze portu. Na przykład adresy `http://www.contoso.com:*` i `http://www.contoso.com:*/` nie są obsługiwane. 

    |    Adres URL    |    Szczegóły    |    Jest zgodny z    |    Nie jest zgodny z    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Zgodny z pojedynczą stroną    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Zgodny z pojedynczą stroną    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/&#42;`   |    Zgodny ze wszystkimi adresami URL rozpoczynającymi się od ciągu `www.contoso.com`    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Zgodny ze wszystkimi domenami podrzędnymi w domenie `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`    |
    |    `http://www.contoso.com/images`    |    Zgodny z pojedynczym folderem    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Zgodny z pojedynczą stroną z użyciem numeru portu    |    http://www.contoso.com:80    |         |
    |    `https://www.contoso.com`    |    Zgodny z pojedynczą, bezpieczną stroną    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Zgodny z pojedynczym folderem ze wszystkimi podfolderami    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Poniżej przedstawiono przykłady niektórych niedozwolonych wzorców:
    - `*.com`
    - `*.contoso/*`
    - `www.contoso.com/*images`
    - `www.contoso.com/*images*pigs`
    - `www.contoso.com/page*`
    - Adresy IP
    - `https://*`
    - `http://*`
    - `https://*contoso.com`
    - `http://www.contoso.com:*`
    - `http://www.contoso.com: /*`
  
## <a name="defining-behavior-when-users-try-to-access-a-blocked-site"></a>Definiowanie zachowania w sytuacji, gdy użytkownicy próbują uzyskać dostęp do zablokowanej witryny

Dzięki modelowi podwójnej tożsamości wbudowanemu w przeglądarce Microsoft Edge można jeszcze bardziej zwiększyć elastyczność środowiska dla użytkowników końcowych, co nie było możliwe w przypadku aplikacji Intune Managed Browser. Gdy użytkownicy trafią na zablokowaną witrynę w przeglądarce Microsoft Edge, może pojawić się monit o otwarcie linku w kontekście osobistym, zamiast w kontekście służbowym, co pozwoli na stałe objęcie ochroną przy jednoczesnym zachowaniu bezpieczeństwa zasobów firmowych. Jeśli na przykład użytkownik otrzyma link do artykułu z wiadomościami za pośrednictwem programu Outlook, będzie mógł otworzyć ten link w kontekście osobistym lub na karcie InPrivate zamiast w kontekście służbowym, który nie zezwala na używanie witryn internetowych z wiadomościami. Domyślnie takie przejścia są dozwolone.

Użyj poniższej pary klucz/wartość, aby wskazać, czy takie programowe przejścia są dozwolone:

|    Klucz    |    Wartość    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    Wartość **true** pozwala przeglądarce Microsoft Edge na przenoszenie użytkowników do ich kontekstu osobistego w celu otwarcia zablokowanych witryn<p>Wartość **Blokuj** uniemożliwia przeglądarce Microsoft Edge przenoszenie użytkowników. Użytkownicy zobaczą po prostu komunikat z informacją, że dostęp do wybranej witryny został zablokowany.    |

## <a name="directing-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Kierowanie użytkowników do Microsoft Edge zamiast do aplikacji Intune Managed Browser 

Obydwa programy — Intune Managed Browser i Microsoft Edge — mogą być obecnie traktowane jako przeglądarki zarządzane przez zasady. Aby upewnić się, że użytkownicy są kierowani do odpowiedniej przeglądarki, użyj we wszystkich aplikacjach zarządzanych przez usługę Intune (np. Outlook, OneDrive i SharePoint) następującego ustawienia konfiguracji:

|    Klucz    |    Wartość    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Wartość `true` spowoduje przekierowanie użytkowników tak, aby pobrali i używali przeglądarki Microsoft Edge.<br>Wartość `false` pozwoli użytkownikom na używanie aplikacji Intune Managed Browser.    |

Jeśli ta wartość konfiguracji aplikacji **nie** zostanie ustawiona, poniższa logika określi, która przeglądarka będzie służyć do otwierania linków firmowych.

W systemie Android:
- Program Intune Managed Browser będzie otwierany, jeśli użytkownik na swoim urządzeniu pobrane programy Intune Managed Browser i Microsoft Edge. 
- Przeglądarka Microsoft Edge będzie otwierana, jeśli na urządzenie została pobrana tylko ta przeglądarka i jest ona objęta zasadami usługi Intune.
- Program Managed Browser będzie otwierany, jeśli na urządzeniu znajduje się tylko ten program i jest on objęty zasadami usługi Intune.

W systemie iOS w przypadku aplikacji, które mają zintegrowany zestaw SDK usługi Intune dla systemu iOS w wersji 9.0.9+:
- Program Intune Managed Browser będzie uruchamiany, jeśli użytkownik ma na swoim urządzeniu programy Managed Browser i Microsoft Edge.  
- Przeglądarka Microsoft Edge będzie uruchamiana, tylko jeśli na urządzeniu znajduje się tylko ta przeglądarka i jest ona objęta zasadami usługi Intune.
- Program Managed Browser, jeśli na urządzeniu znajduje się tylko ta przeglądarka i jest ona objęta zasadami usługi Intune.

## <a name="using-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Używanie przeglądarki Microsoft Edge w systemie iOS do uzyskiwania dostępu do dzienników aplikacji zarządzanych 

Użytkownicy końcowi z przeglądarką Microsoft Edge zainstalowaną na urządzeniu z systemem iOS mogą wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft. Mogą one wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS.
1. Otwórz przeglądarkę Microsoft Edge na urządzeniu z systemem iOS.
2. Wpisz `about:intunehelp` w polu adresu. 
3. Z poziomu przeglądarki Microsoft Edge zostanie uruchomiony tryb rozwiązywania problemów.

Aby uzyskać listę ustawień przechowywanych w dziennikach aplikacji, zobacz temat [Przeglądanie dzienników ochrony aplikacji w programie Managed Browser](app-protection-policy-settings-log.md).

Aby dowiedzieć się, jak wyświetlać dzienniki na urządzeniach z systemem Android, zobacz [Wysyłanie dzienników do administratora IT pocztą e-mail](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Bezpieczeństwo i ochrona prywatności w przeglądarce Microsoft Edge

Dodatkowe zagadnienia dotyczące bezpieczeństwa i ochrony prywatności dla przeglądarki Microsoft Edge:

- Przeglądarka Microsoft Edge nie używa ustawień, które użytkownicy ustawiają dla natywnej przeglądarki na swoich urządzeniach, ponieważ przeglądarka Microsoft Edge nie ma dostępu do tych ustawień.
- Jeśli w zasadach ochrony aplikacji skojarzonych z przeglądarką Microsoft Edge są skonfigurowane opcje **Wymagaj prostego numeru PIN w celu udzielenia dostępu** lub **Wymagaj poświadczeń firmowych w celu udzielenia dostępu**, a użytkownik wybierze link Pomoc na stronie uwierzytelniania, umożliwi to przeglądanie dowolnych witryn internetowych bez względu na to, czy zostały one dodane w zasadach do listy blokowanych witryn.
- Przeglądarka Microsoft Edge może zablokować dostęp do witryn tylko w przypadku uzyskiwania do nich bezpośredniego dostępu. Dostęp do witryny nie jest blokowany, jeśli jest on uzyskiwany za pomocą usług pośrednich (na przykład usługi tłumaczenia).
- W celu umożliwienia uwierzytelniania i uzyskania dostępu do dokumentacji usługi Intune, witryna * **.microsoft.com** jest wyłączona z ustawień listy dozwolonych lub zablokowanych witryn. Jest ona zawsze dozwolona.
Wyłącz dane użycia Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z programu Managed Browser w celu ulepszania swoich produktów i usług. Użytkownicy mogą wyłączyć zbieranie danych przy użyciu ustawienia **Dane użycia** na swoich urządzeniach. Użytkownik nie kontroluje zbierania tych danych. Na urządzeniach z systemem iOS nie można otwierać odwiedzanych przez użytkowników witryn sieci Web z certyfikatem nieważnym lub niezaufanym.

## <a name="next-steps"></a>Następne kroki

- [Co to są zasady ochrony aplikacji?](app-protection-policy.md) 
