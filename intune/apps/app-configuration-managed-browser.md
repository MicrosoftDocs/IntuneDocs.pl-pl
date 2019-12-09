---
title: Zarządzanie dostępem do Internetu w firmie za pomocą przeglądarki zabezpieczonej przy użyciu zasad
titleSuffix: Microsoft Intune
description: Użyj przeglądarki zabezpieczonej przy użyciu zasad i przypisanej przez usługę Intune, aby zarządzać w firmie przeglądaniem oraz transferem danych w Internecie.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 52f907b8762322684ec9e21910745a197c3dbe4e
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564314"
---
# <a name="manage-web-access-using-a-microsoft-intune-policy-protected-browser"></a>Zarządzanie dostępem do Internetu za pomocą przeglądarki zabezpieczonej przy użyciu zasad w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Korzystając z przeglądarki zabezpieczonej przy użyciu zasad usługi Intune (Microsoft Edge lub Intune Managed Browser), możesz upewnić się, że do witryn internetowych zawsze uzyskuje się dostęp z zastosowanymi zabezpieczeniami.  W przypadku skonfigurowania przy użyciu usługi Intune przeglądarki chronione mogą korzystać z następujących funkcji:

- Zasady ochrony aplikacji
- Dostęp warunkowy
- Logowanie jednokrotne
- Ustawienia konfiguracji aplikacji
- Integracja serwera proxy aplikacji platformy Azure

## <a name="microsoft-edge-support"></a>Obsługa przeglądarki Microsoft Edge

Przeglądarki Microsoft Edge można używać do obsługi scenariuszy przedsiębiorstwa na urządzeniach z systemem iOS i Android. Przeglądarka Microsoft Edge obsługuje wszystkie te same scenariusze zarządzania, co program Intune Managed Browser, dodając ulepszenia środowiska użytkownika końcowego. Dostępne są następujące funkcje przeglądarki Microsoft Edge dla przedsiębiorstw włączane przy użyciu zasad usługi Intune:

- **Podwójna tożsamość** — użytkownicy mogą dodawać konta służbowe i osobiste na potrzeby przeglądania. Te dwie tożsamości są całkowicie oddzielone, co przypomina architekturę i środowisko usługi Office 365 oraz programu Outlook. Administratorzy usługi Intune będą mogli ustawić żądane zasady dla chronionego środowiska przeglądania w ramach konta służbowego. 
- **Integracja zasad ochrony aplikacji usługi Intune** — administratorzy mogą teraz używać zasad ochrony w przeglądarce Microsoft Edge, w tym kontrolować funkcje wycinania, kopiowania i wklejania, zapobiegać tworzeniu zrzutów ekranu oraz zapewniać, że linki wybrane przez użytkownika będzie można otwierać tylko w innych aplikacjach zarządzanych.
- **Integracja serwera proxy aplikacji platformy Azure** — administratorzy mogą kontrolować dostęp do aplikacji SaaS i aplikacji internetowych, co pomaga zagwarantować, że tylko aplikacje oparte na przeglądarce będą uruchamiane w bezpiecznej przeglądarce Microsoft Edge, bez względu na to, czy użytkownicy końcowi nawiązują połączenie z sieci firmowej, czy też z Internetu. 
- **Skróty do zarządzanych ulubionych i strony głównej** — w celu ułatwienia dostępu administratorzy mogą ustawić adresy URL tak, aby były wyświetlane w obszarze Ulubione, gdy użytkownicy końcowi będą pracować w kontekście firmy. Administratorzy mogą ustawić skrót do strony głównej, który będzie wyświetlany jako skrót podstawowy, gdy użytkownik firmowy otworzy nową stronę lub nową kartę w przeglądarce Microsoft Edge.

Zasady ochrony usługi Microsoft Intune dla przeglądarki Microsoft Edge pomagają w ochronie danych i zasobów organizacji. Chroniona przez usługę Intune przeglądarka Microsoft Edge zapewnia, że zasoby firmy są chronione nie tylko w aplikacjach zainstalowanych natywnie, ale także gdy dostęp jest uzyskiwany za pośrednictwem przeglądarki internetowej.

## <a name="getting-started"></a>Wprowadzenie

Microsoft Edge i Intune Managed Browser to aplikacje przeglądarki sieci Web przeznaczone do użytku w organizacji i dostępne do pobrania przez użytkowników końcowych z publicznych sklepów z aplikacjami. 

Wymagania zasad przeglądarki dotyczące systemu operacyjnego:
- system Android (4 lub nowszy) lub
- system iOS (8.0 lub nowszy).

Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.

>[!NOTE]
>Aplikacja Managed Browser nie obsługuje protokołu szyfrowania Secure Sockets Layer, wersja 3 (SSLv3).


## <a name="application-protection-policies-for-protected-browsers"></a>Zasady ochrony aplikacji dla chronionych przeglądarek

Aplikacje Microsoft Edge i Managed Browser są zintegrowane z zestawem SDK usługi Intune, dlatego można do nich również zastosować zasady ochrony aplikacji, takie jak:
- Kontrolowanie użycia funkcji wycinania, kopiowania i wklejania.
- Zapobieganie przechwytywaniu ekranu.
- Zapewnianie otwierania linków firmowych tylko w ramach zarządzanych aplikacji i przeglądarek.

Aby uzyskać szczegółowe informacje, zobacz [Co to są zasady ochrony aplikacji](app-protection-policy.md)?

Te ustawienia można zastosować do:

- Urządzeń zarejestrowanych w usłudze Intune
- Urządzeń zarejestrowanych w innym produkcie MDM
- Urządzeń niezarządzanych

>[!NOTE]
>Jeśli użytkownicy zainstalują aplikację Managed Browser ze sklepu z aplikacjami, a usługa Intune nie będzie nią zarządzać, to aplikacja ta może służyć jako podstawowa przeglądarka sieci Web z obsługą logowania jednokrotnego za pośrednictwem witryny Microsoft MyApps. Użytkownicy są przekierowywani bezpośrednio do witryny MyApps, w której mogą wyświetlić wszystkie aprowizowane aplikacje SaaS.
Kiedy aplikacje Managed Browser lub Microsoft Edge nie są zarządzane przez usługę Intune, nie mogą uzyskać dostępu do danych z innych aplikacji zarządzanych przez usługę Intune. 


## <a name="conditional-access-for-protected-browsers"></a>Dostęp warunkowy dla przeglądarek chronionych

Aplikacja Managed Browser jest teraz zatwierdzoną aplikacją kliencką dla dostępu warunkowego. Oznacza to, że możesz ograniczyć dostęp przeglądarki mobilnej do aplikacji internetowych połączonych z usługą Azure AD, aby użytkownicy mogli używać tylko aplikacji Managed Browser, a dostęp był zablokowany z innych niezabezpieczonych przeglądarek, takich jak Safari czy Chrome. Taką ochronę można zastosować do zasobów platformy Azure, takich jak usługi Exchange Online i SharePoint Online, centrum administracyjne platformy Microsoft 365, a nawet witryny lokalne, które są dostępne dla użytkowników zewnętrznych za pośrednictwem [serwera proxy aplikacji usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). 

Aby ograniczyć aplikacje internetowe usługi Azure AD do używania aplikacji Intune Managed Browser na platformach urządzeń przenośnych, możesz utworzyć zasady dostępu warunkowego wymagające zatwierdzonych aplikacji klienckich. 

> [!TIP]  
> Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure Active Directory (Azure AD). Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*.  

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Urządzenia** > **Dostęp warunkowy** > **Nowe zasady**.
3. Dodaj **nazwę** zasad. 
4. W sekcji **Przypisania** wybierz pozycję **Warunki** > **Aplikacje klienckie**. Zostanie wyświetlone okienko **Aplikacje klienckie**.
5. Kliknij pozycję **Tak** w obszarze **Konfiguruj**, aby zastosować zasady do określonych aplikacji klienckich.
6. Sprawdź, czy jako aplikację kliencką wybrano pozycję **Przeglądarka**.

    ![Azure AD — Managed Browser — wybieranie aplikacji klienckich](./media/app-configuration-managed-browser/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Jeśli chcesz ograniczyć, które aplikacje natywne (aplikacje nie korzystające z przeglądarki) mają mieć dostęp do tych aplikacji w chmurze, możesz także zaznaczyć pozycję **Aplikacje mobilne i klienci stacjonarni**.

7. Kliknij przycisk **Gotowe** > **Gotowe**.
8. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**, a następnie wybierz użytkowników lub grupy, do których chcesz przypisać te zasady. Kliknij pozycję **Gotowe**, aby zamknąć okienko.
9. W sekcji **Przypisania** wybierz pozycję **Aplikacje lub akcje w chmurze**, aby wybrać, które aplikacje mają być chronione przez te zasady. Kliknij pozycję **Gotowe**, aby zamknąć okienko.
10. Wybierz pozycję **Udziel** w sekcji **Kontrole dostępu** okienka. 
11. Kliknij **Udziel dostępu**, a następnie **Wymagaj zatwierdzonej aplikacji klienckiej**. 
12. Kliknij pozycję **Wybierz** w okienku **Udziel**. Te zasady należy przypisać do aplikacji w chmurze, które mają być dostępne tylko dla aplikacji Intune Managed Browser.

    ![Azure AD — zasady dostępu warunkowego aplikacji Managed Browser](./media/app-configuration-managed-browser/managed-browser-conditional-access-01.png)



Po skonfigurowaniu powyższych zasad użytkownicy będą musieli uzyskiwać dostęp do połączonych z usługą Azure AD aplikacji internetowych chronionych przez te zasady za pomocą aplikacji Intune Managed Browser. Jeśli użytkownicy spróbują użyć niezarządzanej przeglądarki w tym scenariuszu, zostanie wyświetlone powiadomienie o konieczności użycia aplikacji Intune Managed Browser.

Program Managed Browser nie obsługuje klasycznych zasad dostępu warunkowego. Aby uzyskać więcej informacji, zobacz artykuł [Migrate classic policies in the Azure portal (Migrowanie zasad klasycznych w witrynie Azure Portal)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration).

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Logowanie jednokrotne do aplikacji internetowych połączonych z usługą Azure AD w przeglądarkach zabezpieczonych przy użyciu zasad

Przeglądarka Microsoft Edge i Intune Managed Browser w systemach iOS i Android może teraz korzystać z logowania jednokrotnego do wszystkich aplikacji internetowych (SaaS i lokalnych), które są połączone z usługą Azure AD. Gdy w systemie iOS jest obecna aplikacja Microsoft Authenticator lub gdy w systemie Android jest obecna aplikacja Portal firmy usługi Intune, użytkownicy przeglądarki zabezpieczonej przy użyciu zasad mogą uzyskiwać dostęp do aplikacji internetowych połączonych z usługą Azure AD bez konieczności ponownego wprowadzania poświadczeń.

Logowanie jednokrotne wymaga, aby urządzenie było zarejestrowane przez aplikację Microsoft Authenticator w systemie iOS lub przez aplikację Portal firmy usługi Intune w systemie Android. Użytkownikom z aplikacją Authenticator lub Portal firmy usługi Intune zostanie wyświetlony monit o zarejestrowanie urządzenia, gdy przejdą do aplikacji internetowej połączonej z usługą Azure AD w przeglądarce zabezpieczonej przy użyciu zasad, a ich urządzenie nie zostało jeszcze zarejestrowane przez inną aplikację. Po zarejestrowaniu urządzenia przy użyciu konta zarządzanego przez usługę Intune dla tego konta zostanie włączone logowanie jednokrotne dla aplikacji internetowych połączonych z usługą Azure AD. 

> [!NOTE]
> Rejestracja urządzenia to proste zaewidencjonowanie go w usłudze Azure AD. Nie wymaga pełnej rejestracji urządzenia ani nie daje działowi IT żadnych dodatkowych uprawnień na urządzeniu.

## <a name="create-a-protected-browser-app-configuration"></a>Tworzenie konfiguracji aplikacji przeglądarki chronionej

>[!IMPORTANT]
>Aby można było zastosować konfiguracje aplikacji, chroniona przeglądarka użytkownika lub inna aplikacja na urządzeniu musi być już zarządzana przez [zasady ochrony aplikacji usługi Intune]( ../app-protection-policy.md).

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj** > **Aplikacje zarządzane**.
3. Na stronie **Podstawowe** w okienku **Tworzenie zasad konfiguracji aplikacji** wypełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do ustawień konfiguracji aplikacji.
4. Wybierz kolejno pozycje **Select the public app** (Wybierz aplikację publiczną) i **Managed Browser** i/lub **Edge** dla systemu iOS, Android lub dla obu tych systemów.
5. Kliknij pozycję **Wybierz**, aby wrócić do okienka **Tworzenie zasad konfiguracji aplikacji**.
6. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Ustawienia**.
7. Na stronie **Ustawienia** należy zdefiniować pary kluczy i wartości do dostarczania konfiguracji dla aplikacji. Informacje na temat różnych par kluczy i wartości, które można zdefiniować, znajdują się w dalszych sekcjach tego artykułu.
8. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisanie**, a następnie kliknij pozycję **Wybierz grupy do uwzględnienia** i/lub **Wybierz grupy do wykluczenia**.
9. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**.
10. Kliknij przycisk **Utwórz** po przejrzeniu zasad konfiguracji aplikacji.

Nowa konfiguracja zostanie utworzona i wyświetlona w okienku **Zasady konfiguracji aplikacji**.


## <a name="assign-the-configuration-settings-you-created"></a>Przypisywanie utworzonych ustawień konfiguracji

Ustawienia są przypisywane do grup użytkowników usługi Azure AD. Jeśli dany użytkownik ma zainstalowaną docelową aplikację przeglądarki chronionej, aplikacja jest zarządzana z uwzględnieniem określonych ustawień.

1. W okienku **Aplikacje** pulpitu nawigacyjnego zarządzania aplikacjami mobilnymi usługi Intune wybierz pozycję **Zasady konfiguracji aplikacji**.
2. Z listy konfiguracji aplikacji wybierz tę, która ma zostać przypisana.
3. W następnym okienku wybierz pozycję **Przypisania**.
4. W okienku **Przypisania** wybierz grupę usługi Azure AD, do której chcesz przypisać konfigurację aplikacji, a następnie kliknij przycisk **OK**.

## <a name="how-to-set-microsoft-edge-as-the-protected-browser-for-your-organization"></a>Ustawianie Microsoft Edge jako przeglądarki chronionej dla swojej organizacji

To ustawienie pozwala określić, czy użytkownicy będą przekierowywani do przeglądarki Microsoft Edge czy przeglądarki Intune Managed Browser, przy założeniu, że obie przeglądarki są objęte zasadami ochrony aplikacji. **To ustawienie zasad konfigurowania aplikacji powinno być stosowane w przypadku aplikacji zarządzanych przez usługę Intune, z których otwierane są łącza sieciowe.** 

Jeśli to ustawienie będzie miało wartość „True” (Prawda):

- Użytkownicy będą przekierowywani do przeglądarki Microsoft Edge podczas otwierania łączy z aplikacji zarządzanych przez usługę Intune oraz objętych tym ustawieniem. 
- Jeśli użytkownik nie będzie miał aplikacji, na ekranie jego urządzenia pojawi się komunikat z prośbą o pobranie przeglądarki Microsoft Edge ze sklepu, niezależnie od tego, czy pobrano przeglądarkę Intune Managed Browser.

Jeśli to ustawienie będzie miało wartość „False” (Fałsz):

- Jeśli użytkownik ma zainstalowaną **zarówno** przeglądarkę Managed Browser, jak i Microsoft Edge, zostanie uruchomiona przeglądarka Managed Browser. 
- Jeśli użytkownik ma pobraną przeglądarkę Managed Browser **lub** Microsoft Edge, zostanie uruchomiona pobrana przeglądarka. 
- Jeśli użytkownik nie pobrał przeglądarki, na ekranie jego urządzenia pojawi się komunikat z prośbą o pobranie przeglądarki Managed Browser.

Powyższą procedurę można wykorzystać do utworzenia konfiguracji przeglądarki Microsoft Edge. Podczas wybierania **ustawień konfiguracji** w okienku **Konfiguracja** podaj następującą parę klucz-wartość (krok 9):

| Klucz                              |  Wartość   |
|----------------------------------|----------|
| **com.microsoft.intune.useEdge** | **true** |

> [!NOTE]
> Upewnij się, że w zasadach ochrony aplikacji używanych do zarządzania przeglądarką Microsoft Edge i skojarzonymi aplikacjami określonymi w konfiguracji aplikacji wybrano następujące ustawienia zasad ochrony danych:
> - Wysyłanie danych organizacji do innych aplikacji: **Aplikacje zarządzane przy użyciu zasad**
> - Ogranicz transfer zawartości internetowej do innych aplikacji: **Przeglądarki zarządzane przez zasady**

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Jak skonfigurować ustawienia serwera proxy aplikacji dla przeglądarek chronionych

Aplikacje Microsoft Edge i Intune Managed Browser oraz [serwer proxy aplikacji usługi Azure AD]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) zapewniają wspólnie obsługę następujących scenariuszy możliwych w przypadku użytkowników urządzeń z systemami iOS oraz Android:

- Użytkownik pobiera aplikację Microsoft Outlook i loguje się w niej. Zasady ochrony aplikacji usługi Intune są stosowane automatycznie. Szyfrują one zapisane dane i uniemożliwiają użytkownikom przesyłanie plików firmowych do niezarządzanych aplikacji lub lokalizacji na urządzeniu. Kiedy użytkownik klika link do witryny intranetowej w aplikacji Outlook, można określić, aby link był otwierany w aplikacji przeglądarki chronionej, a nie w jakiejś innej przeglądarce. Przeglądarka chroniona rozpoznaje, że ta witryna intranetowa została udostępniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Przed dotarciem do witryny intranetowej użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia za pomocą dowolnego obsługiwanego uwierzytelniania wieloskładnikowego i udzielenia dostępu warunkowego. Dana lokalizacja (której wcześniej nie można było znaleźć, jeśli użytkownik był zdalny) jest teraz dostępna, a link w aplikacji Outlook działa prawidłowo.
- Użytkownik zdalny otwiera aplikację przeglądarki chronionej i przechodzi do witryny intranetowej przy użyciu wewnętrznego adresu URL. Przeglądarka chroniona rozpoznaje, że dana witryna intranetowa została udostępniona użytkownikowi za pośrednictwem serwera proxy aplikacji. Przed dotarciem do witryny intranetowej użytkownik jest automatycznie kierowany przez serwer proxy aplikacji w celu uwierzytelnienia za pomocą dowolnego obsługiwanego uwierzytelniania wieloskładnikowego i udzielenia dostępu warunkowego. Dana lokalizacja (której wcześniej nie można było znaleźć, jeśli użytkownik był zdalny) jest teraz dostępna.

### <a name="before-you-start"></a>Przed rozpoczęciem

- Skonfiguruj wewnętrzne aplikacje przy użyciu serwera proxy aplikacji usługi Azure AD.
  - Aby skonfigurować serwer proxy aplikacji i publikować aplikacje, zobacz [dokumentację dotyczącą konfiguracji](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy). 
  - [Użytkownicy muszą być przypisani](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application#add-a-user-for-testing) do aplikacji dla przedsiębiorstw, do której następuje przekierowanie. Należy to zrobić nawet wtedy, gdy aplikacja jest ustawiona w tryb przekazywania na potrzeby uwierzytelniania wstępnego oraz gdy wyłączono wymaganie przypisania użytkownika w ustawieniach serwera proxy aplikacji.
- Wymagana jest aplikacja Managed Browser w wersji 1.2.0 lub nowszej.
- Użytkownicy aplikacji Managed Browser lub Microsoft Edge mają przypisane do aplikacji [zasady ochrony aplikacji usługi Intune](app-protection-policy.md).

    > [!NOTE]
    > Zanim zaktualizowane dane przekierowania serwera proxy aplikacji zaczną obowiązywać w aplikacji Managed Browser lub Microsoft Edge, może minąć do 24 godzin.


#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Krok 1. Włączenie automatycznego przekierowania do przeglądarki chronionej z poziomu programu Outlook
Program Outlook musi być skonfigurowany przy użyciu zasad ochrony aplikacji, które powodują włączenie ustawienia **Ogranicz zawartość sieci Web wyświetlaną w programie Managed Browser**.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-protected-browser"></a>Krok 2: Przypisanie zasad konfiguracji aplikacji przypisanych do przeglądarki chronionej
Ta procedura umożliwia skonfigurowanie aplikacji Managed Browser lub Microsoft Edge, aby korzystała z przekierowywania serwera proxy aplikacji. 

Otwórz kartę **Edge** w ustawieniach konfiguracji zasad i wybierz opcję **Włącz** dla wartości przekierowania serwera proxy aplikacji. Włączenie tego ustawienia da użytkownikom dostęp do firmowych łączy i lokalnych aplikacji sieciowych publikowanych za pomocą serwera proxy aplikacji platformy Azure.

Aby uzyskać więcej informacji o sposobie używania aplikacji Managed Browser i Microsoft Edge w połączeniu z serwerem proxy aplikacji usługi Azure AD w celu zapewnienia bezproblemowego (i bezpiecznego) dostępu do lokalnych aplikacji internetowych, zobacz wpis w blogu pakietu Enterprise Mobility + Security [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Razem lepiej: usługi Intune i Azure Active Directory łączą siły, aby zapewnić lepszy dostęp użytkownikom).

## <a name="how-to-configure-the-homepage-for-a-protected-browser"></a>Jak skonfigurować stronę główną dla przeglądarki chronionej

To ustawienie pozwala skonfigurować stronę główną, którą widzą użytkownicy po uruchomieniu przeglądarki chronionej lub utworzeniu nowej karty. 
- To ustawienie spowoduje wyświetlenie strony internetowej w programie Managed Browser.  W programie Microsoft Edge w zamian będzie wyświetlany skrót do strony głównej.
- Ikona skrótu do strony głównej jest wyświetlana jako ikona pod kontrolką wyszukiwania.  Nie można jej edytować ani usuwać.
- Wyświetlony skrót do strony głównej zostanie wyróżniony przy użyciu nazwy Twojej organizacji.  Będzie on zawsze pojawiać się jako pierwsza ikona.

Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser lub Microsoft Edge, podaj następującą parę klucza i wartości:

|                                Klucz                                |                                                           Wartość                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Określ prawidłowy adres URL. Niepoprawne adresy URL są blokowane ze względów bezpieczeństwa.<br>Przykład: `https://www.bing.com` |

## <a name="how-to-configure-bookmarks-for-a-protected-browser"></a>Jak skonfigurować zakładki dla przeglądarki chronionej

To ustawienie służy do konfigurowania zestawu zakładek dostępnego dla użytkowników w aplikacji Microsoft Edge lub Managed Browser.

- Użytkownicy nie mogą usunąć ani zmodyfikować tych zakładek.
- Te zakładki są wyświetlane na początku listy. Wszystkie zakładki utworzone przez użytkowników są wyświetlane poniżej tych zakładek.
- Jeśli zostało włączone przekierowanie serwera proxy aplikacji, możesz dodać aplikacje internetowe serwera proxy aplikacji, używając ich wewnętrznego lub zewnętrznego adresu URL.

Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser lub Microsoft Edge, podaj następującą parę klucza i wartości:

|                                Klucz                                 |                                                                                                                                                                                                                                                         Wartość                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.bookmarks</strong> | Wartość dla tej konfiguracji to lista zakładek. Każda zakładka składa się z tytułu zakładki i jej adresu URL. Tytuł i adres URL oddziel za pomocą znaku <strong>&#124;</strong>.<br><br>Przykład:<br> <code>Microsoft Bing&#124;https://www.bing.com</code><br><br>Aby skonfigurować wiele zakładek, każdą parę należy rozdzielić podwójnym znakiem <strong>&#124;&#124;</strong><br><br>Przykład:<br> <code>Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com</code> |

## <a name="how-to-specify-allowed-and-blocked-urls-for-a-protected-browser"></a>Jak określać dozwolone i blokowane adresy URL przeglądarki chronionej

Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser lub Microsoft Edge, podaj następującą parę klucza i wartości:

|Klucz|Wartość|
|-|-|
|Wybierz spośród opcji:<br><ul><li>Określ dozwolone adresy URL (tylko te adresy URL są dozwolone; nie można uzyskać dostępu do żadnych innych witryn):<br> **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br></li><li>Określ zablokowane adresy URL (wszystkie inne witryny będą dostępne):<br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**</li></ul>|Wartość klucza to lista adresów URL. Wszystkie adresy URL, które mają być dozwolone lub blokowane, należy wprowadzać jako pojedyncze wartości rozdzielane znakiem pionowej kreski **&#124;** .<br><br>Przykłady:<br><br><code>URL1&#124;URL2&#124;URL3</code><br><code>http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com</code>|

>[!IMPORTANT]
>Należy zdefiniować tylko jeden z tych kluczy. Jeśli dla tego samego użytkownika zostaną zdefiniowane oba klucze, zostanie użyty tylko klucz określający dostępne adresy URL jako bardziej restrykcyjny.
>Ponadto należy upewnić się, że nie są blokowane ważne strony, takie jak firmowe witryny sieci Web.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Format adresu URL dla dozwolonych i zablokowanych adresów URL
Poniższe informacje dotyczą dopuszczalnych formatów i symboli wieloznacznych, których można używać podczas określania adresów URL na listach witryn dozwolonych i zablokowanych:

- Symbol wieloznaczny ( **&#42;** ) może być używany zgodnie z regułami z poniższej listy dozwolonych wzorców:

- Upewnij się, że wszystkie adresy URL dodawane do listy będą mieć prefiks **http** lub **https** .

- W adresie można określić numery portów. Jeśli nie określisz numeru portu, będą używane następujące wartości:

  - Port 80 dla protokołu http

  - Port 443 dla protokołu https

  Symboli wieloznacznych nie można używać w numerze portu. Na przykład adresy `http://www.contoso.com:;` i `http://www.contoso.com: /;` nie są obsługiwane.

- W poniższej tabeli przedstawiono dozwolone wzorce do użycia podczas określania adresów URL:

|                  Adres URL                  |                     Szczegóły                      |                                                Jest zgodny z                                                |                                Nie jest zgodny z                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        `http://www.contoso.com`         |              Zgodny z pojedynczą stroną               |                                            `www.contoso.com`                                            |  `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`contoso.com`/   |
|          `http://contoso.com`           |              Zgodny z pojedynczą stroną               |                                             `contoso.com/`                                              | `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com` |
|    `http://www.contoso.com/&#42;`     | Zgodny ze wszystkimi adresami URL rozpoczynającymi się od ciągu `www.contoso.com` |      `www.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com/videos/tvshows`      |              `host.contoso.com`<br /><br />`host.contoso.com/images`              |
|    `http://*.contoso.com/*`     |     Zgodny ze wszystkimi domenami podrzędnymi w domenie contoso.com     | `developer.contoso.com/resources`<br /><br />`news.contoso.com/images`<br /><br />`news.contoso.com/videos` |                               `contoso.host.com`                                |
|     `http://www.contoso.com/images`     |             Zgodny z pojedynczym folderem              |                                        `www.contoso.com/images`                                         |                          `www.contoso.com/images/dogs`                          |
|       `http://www.contoso.com:80`       |  Zgodny z pojedynczą stroną z użyciem numeru portu   |                                       `http://www.contoso.com:80`                                       |                                                                               |
|        `https://www.contoso.com`        |          Zgodny z pojedynczą, bezpieczną stroną           |                                        `https://www.contoso.com`                                        |                            `http://www.contoso.com`                             |
| `http://www.contoso.com/images/&#42;` |    Zgodny z pojedynczym folderem ze wszystkimi podfolderami    |                  `www.contoso.com/images/dogs`<br /><br />`www.contoso.com/images/cats`                   |                            `www.contoso.com/videos`                             |

- Poniżej przedstawiono przykłady niektórych niedozwolonych wzorców:

  - `*.com`

  - `*.contoso/*`

  - `www.contoso.com/*images`

  - `www.contoso.com/*images*pigs`

  - `www.contoso.com/page*`

  - Adresy IP

  - `https://*`

  - `http://*`

  - `http://www.contoso.com:*`

  - `http://www.contoso.com: /*`
  
## <a name="soft-transitions-from-work-to-personal-accounts"></a>Łatwe przełączanie z kont służbowych na osobiste

Podstawą środowiska mobilnego Microsoft Edge dla firm jest model podwójnej tożsamości. Oznacza to, że przeglądarka Microsoft Edge obsługuje zarówno tożsamość służbową, jak i osobistą. Podobnie jak w przypadku aplikacji pakietu Office 365 i programu Outlook, ten model pozwala użytkownikom końcowym korzystać z przeglądarki Microsoft Edge dla wszystkich potrzeb związanych z przeglądaniem oraz łatwo przełączać się pomiędzy tymi dwoma środowiskami w oparciu o zdefiniowane przez administratora zasady zawartości. Użytkownik może swobodnie przeglądać zawartość w kontekście osobistym, a informacje firmowe są dostępne w przeglądarce Microsoft Edge tylko w kontekście służbowym. 

Jedną z zalet tego modelu jest to, że gdy użytkownik spróbuje otworzyć łącze (np. artykuł prasowy) do strony zablokowanej przez organizację, będzie mógł ją wyświetlić w kontekście osobistym, który będzie całkowicie oddzielony od kontekstu służbowego. Te płynne przejścia są domyślnie włączone. 

Korzystając z procedury tworzenia konfiguracji aplikacji Managed Browser lub Microsoft Edge, podaj następującą parę klucza i wartości:

| Klucz                                                                | Wartość                                                 |
|--------------------------------------------------------------------|-------------------------------------------------------|
| **com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock** | Opcja **False** (Fałsz) blokuje te płynne przejścia |

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

- Ustawienia przeglądarki wbudowanej na urządzeniach użytkowników nie są używane w programie Managed Browser. Aplikacja Managed Browser nie ma dostępu do tych ustawień.

- Jeśli w zasadach ochrony aplikacji skojarzonych z programem Managed Browser są skonfigurowane opcje **Wymagaj prostego numeru PIN w celu udzielenia dostępu** lub **Wymagaj poświadczeń firmowych w celu udzielenia dostępu**, a użytkownik wybierze link Pomoc na stronie uwierzytelniania, umożliwi to przeglądanie dowolnych witryn internetowych bez względu na to, czy zostały one dodane w zasadach do listy blokowanych witryn.

- Program Managed Browser może zablokować dostęp do witryn tylko w przypadku uzyskiwania do nich bezpośredniego dostępu. Dostęp do witryny nie jest blokowany, jeśli jest on uzyskiwany za pomocą usług pośrednich (na przykład usługi tłumaczenia).

- W celu umożliwienia uwierzytelniania i uzyskania dostępu do dokumentacji usługi Intune, witryna **&#42;.microsoft.com** jest wyłączona z ustawień listy dozwolonych lub zablokowanych witryn. Jest ona zawsze dozwolona.

### <a name="turn-off-usage-data"></a>Wyłączanie danych użycia
Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z programu Managed Browser w celu ulepszania swoich produktów i usług. Użytkownicy mogą wyłączyć zbieranie danych przy użyciu ustawienia **Dane użycia** na swoich urządzeniach. Użytkownik nie kontroluje zbierania tych danych.

- Na urządzeniach z systemem iOS nie można otwierać odwiedzanych przez użytkowników witryn sieci Web z certyfikatem nieważnym lub niezaufanym.

## <a name="next-steps"></a>Następne kroki

- [Co to są zasady ochrony aplikacji?](app-protection-policy.md) 
