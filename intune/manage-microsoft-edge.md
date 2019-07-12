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
ms.openlocfilehash: 147547577615c6e74a9c5b3dd8b200ba387bad79
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/08/2019
ms.locfileid: "67648462"
---
# <a name="manage-web-access-by-using-microsoft-edge-with-microsoft-intune"></a>Zarządzanie dostępem do Internetu przy użyciu przeglądarki Microsoft Edge w usłudze Microsoft Intune

Używanie zasad ochrony aplikacji usługi Intune z przeglądarką Microsoft Edge pomaga zapewnić, że dostęp do firmowych witryn internetowych będzie zawsze uzyskiwany z zastosowaniem środków bezpieczeństwa. W przedsiębiorstwie dostępne są następujące funkcje przeglądarki Microsoft Edge włączane przy użyciu zasad usługi Intune:

- **Podwójna tożsamość.** Użytkownicy mogą dodawać konta służbowe i osobiste na potrzeby przeglądania. Te dwie tożsamości są całkowicie oddzielone, co przypomina architekturę i środowisko usługi Office 365 oraz programu Outlook. Administratorzy usługi Intune mogą ustawić żądane zasady dla chronionego środowiska przeglądania w ramach konta służbowego.
- **Zasady ochrony aplikacji w usłudze Intune.** Przeglądarka Microsoft Edge jest zintegrowana z zestawem SDK usługi Intune, dlatego do ochrony przez utratą danych można docelowo zastosować zasady ochrony aplikacji. Te możliwości obejmują kontrolowanie użycia funkcji wycinania, kopiowania i wklejania, zapobieganie przechwytywaniu ekranu oraz zapewnianie, że wybierane przez użytkowników linki są otwierane tylko w innych zarządzanych aplikacjach.
- **Integracja serwera proxy aplikacji platformy Azure.** Można kontrolować dostęp do aplikacji oprogramowania jako usługi (SaaS) i aplikacji internetowych. Pomaga to zagwarantować, że tylko aplikacje oparte na przeglądarce będą uruchamiane w bezpiecznej przeglądarce Microsoft Edge, bez względu na to, czy użytkownicy końcowi nawiązują połączenie z sieci firmowej, czy też z Internetu.
- **Konfiguracja aplikacji.** Można używać ustawień konfiguracji aplikacji w celu zwiększania poziomu bezpieczeństwa organizacji i konfigurowania łatwych w użyciu funkcji dla użytkowników końcowych. Można na przykład można zdefiniować zakładki, skrót do strony głównej, witryny dozwolone lub zablokowane oraz serwer proxy aplikacji usługi Azure Active Directory (Azure AD).

Zasady ochrony usługi Microsoft Intune dla przeglądarki Microsoft Edge pomagają w ochronie danych i zasobów organizacji. Użycie tych zasad z przeglądarką Microsoft Edge zapewnia, że zasoby firmy są chronione nie tylko w aplikacjach zainstalowanych natywnie, ale także gdy dostęp jest uzyskiwany za pośrednictwem przeglądarki internetowej.

## <a name="getting-started"></a>Wprowadzenie

Ty i Twoi użytkownicy końcowi możecie pobrać przeglądarkę Microsoft Edge z publicznych sklepów z aplikacjami i korzystać z niej w organizacji. W przypadku zasad przeglądarki jest wymagany jeden z następujących systemów operacyjnych:
- System Android 4 lub nowszy
- System iOS 8.0 i nowsze

## <a name="application-protection-policies-for-microsoft-edge"></a>Zasady ochrony aplikacji dla przeglądarki Microsoft Edge

Przeglądarka Microsoft Edge jest zintegrowana z zestawem SDK usługi Intune, dlatego można do niej zastosować zasady ochrony aplikacji.

Te ustawienia można zastosować do:
- Urządzeń zarejestrowanych w usłudze Intune.
- Urządzeń zarejestrowanych przy użyciu innego rozwiązania do zarządzania urządzeniami mobilnymi.
- Urządzeń niezarządzanych.

Jeśli przeglądarka Microsoft Edge nie jest docelowym programem zasad usługi Intune, użytkownicy nie mogą używać jej do uzyskiwania dostępu do danych z innych aplikacji zarządzanych przez usługę Intune, takich jak aplikacje pakietu Office. 

## <a name="conditional-access-for-microsoft-edge"></a>Dostęp warunkowy dla przeglądarki Microsoft Edge

Możesz używać dostępu warunkowego usługi Azure AD, aby przekierowywać użytkowników tak, aby uzyskiwali dostęp do zawartości firmowej tylko za pośrednictwem przeglądarki Microsoft Edge. Ogranicza to dostęp przeglądarki mobilnej do połączonej z usługą Azure AD aplikacji internetowej do przeglądarki Microsoft Edge chronionej przez zasady. W wyniku dostęp z innych niezabezpieczonych przeglądarek, takich jak Safari czy Chrome, zostaje zablokowany. Możesz zastosować dostęp warunkowy do zasobów platformy Azure, takich jak usługi Exchange Online i SharePoint Online, centrum administracyjne platformy Microsoft 365, a nawet witryny lokalne, które są dostępne dla użytkowników zewnętrznych za pośrednictwem [serwera proxy aplikacji usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Aby ograniczyć aplikacje internetowe połączone z usługą Azure AD w celu używania przeglądarki Microsoft Edge w systemach iOS i Android:
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W węźle usługi Intune wybierz kolejno pozycje **Dostęp warunkowy** > **Nowe zasady**.
3. Wybierz pozycję **Udziel** w sekcji **Kontrole dostępu** bloku.
4. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**.
5. Wybierz pozycję **Wybierz** w bloku **Udziel**. Te zasady należy przypisać do aplikacji w chmurze, które mają być dostępne tylko dla aplikacji Intune Managed Browser.

    ![Zrzut ekranu przedstawiający obszar Zasady dostępu warunkowego — udzielanie](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. W sekcji Przypisania wybierz pozycję **Warunki** > **Aplikacje klienckie**. Pojawi się blok **Aplikacje klienckie**.
7. W obszarze **Konfiguruj** wybierz pozycję **Tak**, aby zastosować zasady do określonych aplikacji klienckich.
8. Sprawdź, czy jako aplikację kliencką wybrano pozycję **Przeglądarka**.

    ![Zrzut ekranu przedstawiający obszar Zasady dostępu warunkowego — wybieranie aplikacji klienckich](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Jeśli chcesz ograniczyć, które aplikacje natywne (aplikacje nie korzystające z przeglądarki) mają mieć dostęp do tych aplikacji w chmurze, możesz także zaznaczyć pozycję **Aplikacje mobilne i klienci stacjonarni**.

9. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**, a następnie wybierz użytkowników lub grupy, do których chcesz przypisać te zasady.

    > [!NOTE]
    > Użytkownicy muszą również zostać objęci zasadami Intune App Protection w celu odbierania zasad konfiguracji aplikacji. Aby uzyskać więcej informacji na temat tworzenia zasad ochrony aplikacji usługi Intune, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

10. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**, aby wybrać, które aplikacje mają być chronione przez te zasady.

Po skonfigurowaniu powyższych zasad użytkownicy muszą uzyskiwać dostęp do połączonych z usługą Azure AD aplikacji internetowych chronionych przez te zasady za pomocą przeglądarki Microsoft Edge. Jeśli użytkownicy próbują użyć niezarządzanej przeglądarki w tym scenariuszu, jest wyświetlany komunikat o konieczności użycia przeglądarki Microsoft Edge.

> [!TIP]
> Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure AD. Węzeł Dostęp warunkowy dostępny z usługi Intune jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Logowanie jednokrotne do aplikacji internetowych połączonych z usługą Azure AD w przeglądarkach zabezpieczonych przy użyciu zasad

Przeglądarka Microsoft Edge w systemach iOS i Android może teraz korzystać z logowania jednokrotnego do wszystkich aplikacji internetowych (SaaS i lokalnych), które zostały połączone z usługą Azure AD. Logowanie jednokrotne umożliwia użytkownikom dostęp do aplikacji internetowych połączonych z usługą Azure AD za pośrednictwem przeglądarki Microsoft Edge bez konieczności ponownego wprowadzania poświadczeń.

Logowanie jednokrotne wymaga, aby urządzenie było zarejestrowane przez aplikację Microsoft Authenticator dla urządzeń z systemem iOS lub przez aplikację Portal firmy usługi Intune w systemie Android. W przypadku korzystania z jednego z tych rozwiązań użytkownicy są monitowani o zarejestrowanie urządzenia po przejściu do połączonej z usługą Azure AD aplikacji internetowej w przeglądarce chronionej przez zasady. (To stwierdzenie jest prawdziwe tylko, jeśli urządzenie nie zostało jeszcze zarejestrowane). Po zarejestrowaniu urządzenia przy użyciu konta użytkownika zarządzanego przez usługę Intune dla tego konta jest włączane logowanie jednokrotne dla aplikacji internetowych połączonych z usługą Azure AD.

> [!NOTE]
> Rejestracja urządzenia to proste zaewidencjonowanie go w usłudze Azure AD. Nie wymaga pełnej rejestracji urządzenia ani nie daje działowi IT żadnych dodatkowych uprawnień na urządzeniu.

## <a name="create-a-protected-browser-app-configuration"></a>Tworzenie konfiguracji aplikacji przeglądarki chronionej

Aby można było zastosować konfiguracje aplikacji, chroniona przeglądarka użytkownika lub inna aplikacja na urządzeniu musi być już zarządzana przez [zasady ochrony aplikacji usługi Intune](app-protection-policy.md).

Aby utworzyć konfigurację aplikacji na potrzeby przeglądarki Microsoft Edge:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** > **Dodaj**.
3. W bloku **Dodaj zasady konfiguracji** wypełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do ustawień konfiguracji aplikacji.
4. Jako typ **rejestracji urządzenia** wybierz **Aplikacje zarządzane**.
5. Wybierz pozycję **Wybierz wymaganą aplikację**. Następnie przejdź do bloku **Docelowe aplikacje** i wybierz pozycję **Managed Browser** lub **Edge** dla systemu iOS lub Android bądź dla obu tych systemów.
6. Wybierz przycisk **OK**, aby wrócić do bloku **Dodaj zasady konfiguracji**.
7. Wybierz pozycję **Ustawienia konfiguracji**. W bloku **Konfiguracja** należy zdefiniować pary kluczy i wartości do dostarczania konfiguracji dla przeglądarki Microsoft Edge. Informacje na temat różnych par kluczy i wartości, które można zdefiniować, znajdują się w dalszych sekcjach tego artykułu.

    > [!NOTE]
    > Aplikacja Microsoft Edge używa tych samych par klucza i wartości co aplikacja Managed Browser. 

8. Gdy wszystko będzie gotowe, wybierz przycisk **OK**.
9. W bloku **Dodaj zasady konfiguracji** wybierz pozycję **Dodaj**.<br>
    Nowa konfiguracja zostanie utworzona i wyświetlona w bloku **Konfiguracja aplikacji**.

## <a name="assign-the-configuration-settings-you-created"></a>Przypisywanie utworzonych ustawień konfiguracji 

Ustawienia są przypisywane do grup użytkowników w usłudze Azure AD. Jeśli dany użytkownik ma zainstalowaną docelową aplikację przeglądarki chronionej, aplikacja jest zarządzana z uwzględnieniem określonych ustawień.

1. W bloku **Aplikacje klienckie** pulpitu nawigacyjnego zarządzania aplikacjami mobilnymi usługi Intune wybierz pozycję **Zasady konfiguracji aplikacji**.
2. Z listy konfiguracji aplikacji wybierz tę, która ma zostać przypisana.
3. W następnym bloku wybierz pozycję **Przypisania**.
4. W bloku **Przypisania** wybierz grupę usługi Azure AD, do której chcesz przypisać konfigurację aplikacji, a następnie wybierz przycisk **OK**.

## <a name="direct-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Kierowanie użytkowników do przeglądarki Microsoft Edge zamiast do programu Intune Managed Browser 

Obydwa programy — Intune Managed Browser i Microsoft Edge — mogą być używane jako przeglądarki chronione przez zasady. Aby upewnić się, że użytkownicy są kierowani do odpowiedniej przeglądarki, użyj we wszystkich aplikacjach zarządzanych przez usługę Intune (na przykład Outlook, OneDrive i SharePoint) następującego ustawienia konfiguracji:

|    Klucz    |    Wartość    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Wartość `true` spowoduje przekierowanie użytkowników tak, aby pobrali i używali przeglądarki Microsoft Edge.<br>Wartość `false` pozwoli użytkownikom na używanie aplikacji Intune Managed Browser.    |

Jeśli ta wartość konfiguracji aplikacji **nie** zostanie ustawiona, poniższa logika określi, która przeglądarka będzie służyć do otwierania linków firmowych.

W systemie Android:
- Program Intune Managed Browser jest uruchamiany, jeśli użytkownik na swoim urządzeniu ma pobrane programy Intune Managed Browser i Microsoft Edge. 
- Przeglądarka Microsoft Edge jest uruchamiana, jeśli na urządzenie została pobrana tylko ta przeglądarka i jest ona objęta zasadami usługi Intune.
- Program Managed Browser jest uruchamiany, jeśli na urządzeniu znajduje się tylko ten program i jest on objęty zasadami usługi Intune.

W systemie iOS w przypadku aplikacji, które mają zintegrowany zestaw SDK usługi Intune dla systemu iOS w wersji 9.0.9+:
- Program Intune Managed Browser jest uruchamiany, jeśli użytkownik ma na swoim urządzeniu programy Managed Browser i Microsoft Edge.  
- Przeglądarka Microsoft Edge jest uruchamiana, jeśli na urządzeniu znajduje się tylko ta przeglądarka i jest ona objęta zasadami usługi Intune.
- Program Managed Browser jest uruchamiany, jeśli na urządzeniu znajduje się tylko ten program i jest on objęty zasadami usługi Intune.

## <a name="configure-application-proxy-settings-for-microsoft-edge"></a>Konfigurowanie ustawień serwera proxy aplikacji dla przeglądarki Microsoft Edge

Możesz używać przeglądarki Microsoft Edge i [serwera proxy aplikacji usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) razem, aby umożliwić użytkownikom dostęp do witryn intranetowych na ich urządzeniach przenośnych. 

Poniżej przedstawiono niektóre przykładowe scenariusze zastosowania serwera proxy aplikacji usługi Azure AD: 

- Użytkownik korzysta z aplikacji mobilnej Outlook, która jest chroniona przez usługę Intune. Następnie klika link do witryny intranetowej w wiadomości e-mail, a przeglądarka Microsoft Edge rozpoznaje, że dana witryna intranetowa została uwidoczniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Przed dotarciem do witryny intranetowej użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia za pomocą dowolnego obsługiwanego uwierzytelniania wieloskładnikowego i udzielenia dostępu warunkowego. Użytkownik może teraz uzyskiwać dostęp do witryn wewnętrznych nawet na swoich urządzeniach przenośnych, a link w aplikacji Outlook działa zgodnie z oczekiwaniami.
- Użytkownik otwiera przeglądarkę Microsoft Edge na urządzeniu z systemem iOS lub Android. Jeśli przeglądarka Microsoft Edge jest chroniona za pomocą usługi Intune, a serwer proxy aplikacji został włączony, użytkownik może przejść do witryny intranetowej przy użyciu wewnętrznego adresu URL, do którego jest przyzwyczajony. Przeglądarka Microsoft Edge rozpoznaje, że ta witryna intranetowa została uwidoczniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia przed dotarciem do witryny intranetowej. 

### <a name="before-you-start"></a>Przed rozpoczęciem

- Skonfiguruj aplikacje wewnętrzne przy użyciu serwera proxy aplikacji usługi Azure AD.
    - Aby skonfigurować serwer proxy aplikacji i publikować aplikacje, zobacz [dokumentację dotyczącą konfiguracji](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Aplikacja Microsoft Edge musi mieć przypisane [zasady ochrony aplikacji usługi Intune](app-protection-policy.md).

> [!NOTE]
> Zanim zaktualizowane dane przekierowania serwera proxy aplikacji zaczną obowiązywać w aplikacji Managed Browser lub Microsoft Edge, może minąć do 24 godzin.

#### <a name="step-1-enable-automatic-redirection-to-microsoft-edge-from-outlook"></a>Krok 1. Włączenie automatycznego przekierowania do przeglądarki Microsoft Edge z poziomu programu Outlook
Skonfiguruj program Outlook przy użyciu zasad ochrony aplikacji, które powodują włączenie ustawienia **Udostępniaj zawartość internetową za pomocą przeglądarek zarządzanych przez zasady**.

![Zrzut ekranu przedstawiający obszar Zasady ochrony aplikacji — udostępnianie zawartości internetowej za pomocą przeglądarek zarządzanych przez zasady](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Krok 2: Zdefiniowanie ustawienia konfiguracji aplikacji w celu włączenia serwera proxy aplikacji
W przeglądarce Microsoft Edge użyj następującej pary klucz/wartość, aby włączyć serwer proxy aplikacji dla przeglądarki Microsoft Edge:

|    Klucz    |    Wartość    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true    |

Aby uzyskać więcej informacji o sposobie używania przeglądarki Microsoft Edge w połączeniu z serwerem proxy aplikacji usługi Azure AD w celu zapewnienia bezproblemowego (i bezpiecznego) dostępu do lokalnych aplikacji internetowych, zobacz [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Razem lepiej: usługi Intune i Azure Active Directory łączą siły, aby zapewnić lepszy dostęp użytkownikom). Ten wpis w blogu odwołuje się do programu Intune Managed Browser, ale dotyczy również przeglądarki Microsoft Edge.

## <a name="configure-a-homepage-shortcut-for-microsoft-edge"></a>Konfigurowanie skrótu do strony głównej dla przeglądarki Microsoft Edge

To ustawienie umożliwia skonfigurowanie skrótu do strony głównej dla przeglądarki Microsoft Edge. Skonfigurowany skrót do strony głównej jest wyświetlany jako pierwsza ikona poniżej paska wyszukiwania, gdy użytkownik otworzy nową kartę w przeglądarce Microsoft Edge. Użytkownik nie może edytować ani usuwać tego skrótu w swoim kontekście zarządzanym. Wyświetlony skrót do strony głównej jest wyróżniany przy użyciu nazwy Twojej organizacji. 

Użyj następującej pary klucz/wartość, aby skonfigurować skrót do strony głównej:

|    Klucz    |    Wartość    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Określ prawidłowy adres URL. Niepoprawne adresy URL są blokowane ze względów bezpieczeństwa.<br>**Przykład:**  <`https://www.bing.com`>
    |

## <a name="configure-managed-bookmarks-for-microsoft-edge"></a>Konfigurowanie zakładek zarządzanych dla przeglądarki Microsoft Edge

W celu ułatwienia dostępu można skonfigurować zakładki, które mają być dostępne dla Twoich użytkowników, gdy będą korzystać z przeglądarki Microsoft Edge. 

Oto niektóre szczegóły:

- Te zakładki są wyświetlane dla użytkowników tylko wtedy, gdy korzystają oni z trybu firmowego w przeglądarce Microsoft Edge. 
- Użytkownicy nie mogą usuwać ani modyfikować tych zakładek.
- Te zakładki są wyświetlane na początku listy. Wszystkie zakładki utworzone przez użytkowników pojawiają się poniżej tych zakładek.
- Jeśli zostało włączone przekierowanie serwera proxy aplikacji, możesz dodać aplikacje internetowe serwera proxy aplikacji, używając ich wewnętrznego lub zewnętrznego adresu URL.

Użyj następujących par klucz/wartość w celu skonfigurowania zakładek zarządzanych:

|    Klucz    |    Wartość    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    Wartość dla tej konfiguracji to lista zakładek. Każda zakładka składa się z tytułu zakładki i jej adresu URL. Tytuł i adres URL oddziel za pomocą znaku `|`.      Przykład:<br>`Microsoft Bing|https://www.bing.com`<br>Aby skonfigurować wiele zakładek, każdą parę oddziel podwójnym znakiem `||`.<p>Przykład:<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="display-myapps-within-microsoft-edge-bookmarks"></a>Wyświetlanie aplikacji MyApps w ramach zakładek przeglądarki Microsoft Edge

Domyślnie użytkownicy widzą witryny MyApps, które zostały dla nich skonfigurowane, w folderze wewnątrz zakładek przeglądarki Microsoft Edge. Folder jest oznaczony etykietą z nazwą organizacji.

|    Klucz    |    Wartość    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    Wartość **true** powoduje wyświetlanie aplikacji MyApps w zakładkach przeglądarki Microsoft Edge.<p>Wartość **false** powoduje ukrywanie aplikacji MyApps w przeglądarce Microsoft Edge.    |

## <a name="specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Określanie listy dozwolonych lub zablokowanych witryn przeglądarki Microsoft Edge
Do zdefiniowania witryn, do których Twoi użytkownicy będą mieć dostęp w profilu służbowym, możesz użyć konfiguracji aplikacji. Jeśli używasz listy dozwolonych, użytkownicy mają dostęp tylko do witryn, które zostały jawnie wymienione. Jeśli używasz listy zablokowanych, użytkownicy mogą mieć dostęp do wszystkich witryn z wyjątkiem jawnie zablokowanych. Należy zastosować listę dozwolonych lub listę zablokowanych, nie obydwie listy. W przypadku zastosowania obydwu list będzie przestrzegana lista dozwolonych.  

Użyj następujących par klucz/wartość, aby skonfigurować listę dozwolonych lub zablokowanych witryn dla przeglądarki Microsoft Edge. 

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
    |    `http://www.contoso.com:80`    |    Zgodny z pojedynczą stroną z użyciem numeru portu    |    `http://www.contoso.com:80`    |         |
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
  
## <a name="define-behavior-when-users-try-to-access-a-blocked-site"></a>Definiowanie zachowania w sytuacji, gdy użytkownicy próbują uzyskać dostęp do zablokowanej witryny

Dzięki modelowi podwójnej tożsamości wbudowanemu w przeglądarce Microsoft Edge można zwiększyć elastyczność środowiska dla użytkowników końcowych jeszcze bardziej niż było to możliwe w przypadku aplikacji Intune Managed Browser. Gdy użytkownicy przejdą do zablokowanej witryny w przeglądarce Microsoft Edge, możesz włączyć wyświetlanie monitu o otwarcie linku w kontekście osobistym, a nie kontekście służbowym. Dzięki temu użytkownicy będą chronieni, a zasoby firmowe pozostaną bezpieczne. Jeśli na przykład użytkownik wyśle link do artykułu z wiadomościami za pośrednictwem programu Outlook, będzie mógł otworzyć ten link w swoim kontekście osobistym lub na karcie InPrivate. Kontekst służbowy nie zezwala na korzystanie z witryn internetowych z wiadomościami. Domyślnie takie przejścia są dozwolone.

Użyj następującej pary klucz/wartość, aby wskazać, czy takie programowe przejścia są dozwolone:

|    Klucz    |    Wartość    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    Wartość **Prawda** pozwala przeglądarce Microsoft Edge na przenoszenie użytkowników do ich kontekstu osobistego w celu otwarcia zablokowanych witryn.<p>Wartość **Blokuj** uniemożliwia przeglądarce Microsoft Edge przenoszenie użytkowników. Użytkownicy widzą po prostu komunikat o zablokowaniu witryny, do której próbują uzyskać dostęp.    |

## <a name="use-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Używanie przeglądarki Microsoft Edge w systemie iOS do uzyskiwania dostępu do dzienników aplikacji zarządzanych 

Użytkownicy z przeglądarką Microsoft Edge zainstalowaną na urządzeniu z systemem iOS mogą wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft. Mogą one wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS. Oto jak:
1. Otwórz przeglądarkę Microsoft Edge na urządzeniu z systemem iOS.
2. Wpisz `about:intunehelp` w polu adresu. 
3. Przeglądarka Microsoft Edge zostanie uruchomiona w trybie rozwiązywania problemów.

Aby uzyskać listę ustawień przechowywanych w dziennikach aplikacji, zobacz temat [Przeglądanie dzienników ochrony aplikacji w programie Managed Browser](app-protection-policy-settings-log.md).

Aby dowiedzieć się, jak wyświetlać dzienniki na urządzeniach z systemem Android, zobacz [Wysyłanie dzienników do administratora IT pocztą e-mail](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Bezpieczeństwo i ochrona prywatności w przeglądarce Microsoft Edge

Poniżej zostały przedstawione dodatkowe zagadnienia dotyczące bezpieczeństwa i ochrony prywatności dla przeglądarki Microsoft Edge:

- Przeglądarka Microsoft Edge nie używa ustawień, które użytkownicy ustawiają dla natywnej przeglądarki na swoich urządzeniach, ponieważ przeglądarka Microsoft Edge nie ma dostępu do tych ustawień.
- Możesz skonfigurować opcję **Wymagaj prostego numeru PIN w celu udzielenia dostępu** lub **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** w zasadach ochrony aplikacji skojarzonych z przeglądarką Microsoft Edge. Jeśli użytkownik wybierze link do pomocy na stronie uwierzytelniania, będzie mógł przeglądać dowolne witryny internetowe, niezależnie od tego, czy zostały one dodane do listy zablokowanych w zasadach.
- Przeglądarka Microsoft Edge może zablokować dostęp do witryn tylko w przypadku uzyskiwania do nich bezpośredniego dostępu. Dostęp do witryny nie jest blokowany, jeśli użytkownicy używają usług pośrednich (na przykład usługi tłumaczenia).
- W celu umożliwienia uwierzytelniania i uzyskania dostępu do dokumentacji usługi Intune, witryna * **.microsoft.com** jest wyłączona z ustawień listy dozwolonych lub zablokowanych witryn. Jest ona zawsze dozwolona.
- Użytkownicy mogą wyłączyć zbieranie danych. Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z programu Managed Browser w celu ulepszania swoich produktów i usług. Użytkownicy mogą wyłączyć zbieranie danych przy użyciu ustawienia **Dane użycia** na swoich urządzeniach. Użytkownik nie kontroluje zbierania tych danych. Na urządzeniach z systemem iOS nie można otwierać odwiedzanych przez użytkowników witryn internetowych z certyfikatem nieważnym lub niezaufanym.

## <a name="next-steps"></a>Następne kroki

- [Co to są zasady ochrony aplikacji?](app-protection-policy.md) 
