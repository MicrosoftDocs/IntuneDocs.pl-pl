---
title: "Tworzenie projektu usługi Intune | Microsoft Docs"
description: "Ten artykuł jest pomocny w przypadku tworzenia projektu i implementacji tylko w chmurze usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 70be873367edccdefd724b6aa6959eb67b377bdd
ms.openlocfilehash: 92dedcd165ffec47f6c5b818533fce08ed04b1a0


---

# <a name="create-an-intune-design"></a>Tworzenie projektu usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Sekcji w tym przewodniku należy używać równolegle z innymi tematami w sekcji 2. Projekt będzie opierać się na zbieranych informacjach oraz decyzjach podejmowanych podczas kończenia poprzednich sekcji tego przewodnika. W tej sekcji dotyczącej projektu skupimy się na autonomicznej usłudze Intune, czyli opartej na chmurze usłudze firmy Microsoft znajdującej się w chmurze.

Mimo że wymagania dotyczące infrastruktury lokalnej są minimalne, nadal zalecane jest wykonanie pracy nad planem projektu, aby zapewnić, że istnieje prawidłowe rozwiązanie do zarządzania urządzeniami przenośnymi spełniające cele i wymagania.

Ponadto powszechne jest wprowadzanie zmian projektu podczas etapów wdrażania i testowania, w związku z czym należy upewnić się, że te zmiany zostaną udokumentowane wraz z uzasadnieniem ich wprowadzenia. Omawiane będą następujące zagadnienia:

-   Bieżące środowisko

-   Opcje wdrożenia usługi Intune

-   Wymagania dotyczące tożsamości dla zależności zewnętrznych

-   Uwagi dotyczące platform urządzeń

-   Wymagania do spełnienia  

Omówmy teraz każde z tych zagadnień w bardziej szczegółowy sposób. 

## <a name="record-your-environment"></a>Rejestrowanie środowiska

Pierwszym krokiem przed utworzeniem projektu jest zarejestrowanie bieżącego środowiska. Bieżące środowisko może mieć wpływ na decyzje projektowe i powinno być udokumentowane i sprawdzone w momencie podejmowania innych decyzji dotyczących projektu usługi Intune. Poniżej przedstawiono kilka przykładów sposobu rejestrowania bieżącego środowiska:

-   **Tożsamość w chmurze**

    -   Czy używasz narzędzia DirSync lub programu Azure Active Directory (AAD) Connect?

    -   Czy Twoje środowisko jest federacyjne?

    -   Czy włączone jest uwierzytelnianie wieloskładnikowe?

-   **Środowisko poczty e-mail**

    -   Czy używany jest program Exchange, a jeśli tak, to jego lokalna instalacja, czy wersja w chmurze?

    -   Czy jesteś w trakcie projektu migracji programu Exchange do chmury?

-   **Bieżące rozwiązanie do zarządzania urządzeniami przenośnymi**

    -   Czy obecnie używasz innych rozwiązań do zarządzania urządzeniami przenośnymi?

    -   Jakich rozwiązań do zarządzania urządzeniami przenośnymi używasz dla następujących scenariuszy przypadków użycia: firmowego i modelu „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)?

    -   Z jakich możliwości korzystasz (np. ustawienia urządzenia aplikacji, konfiguracja sieci Wi-Fi, inne)?

    -   Jakie platformy urządzeń są obsługiwane?

    -   Przez jakie grupy i ilu użytkowników używane jest rozwiązanie do zarządzania urządzeniami przenośnymi?

-   **Rozwiązanie związane z certyfikatem**

    -   Czy wdrożone zostało rozwiązanie związane z certyfikatem?

    -   Jakie typy certyfikatów są używane?

-   **Zarządzanie systemami**

    -   W jaki sposób zarządzasz środowiskiem komputera PC i serwera?

    -   Czy używany jest program System Center Configuration Manager? Czy używasz platformy zarządzania systemami innej firmy?

-   **Rozwiązanie sieci VPN**

    -   Jakie jest Twoje rozwiązanie sieci VPN?

    -   Czy jest ono używane w obu scenariuszach przypadków użycia: firmowym i BYOD?

Należy upewnić się, czy uwzględniono wszystkie istniejące projekty i inne plany, aby możliwe było wprowadzenie zmian w środowisku podczas rejestrowania bieżącego środowiska zarządzania urządzeniami przenośnymi. Poniżej przedstawiono przykładowy sposób rejestrowania bieżącego środowiska, który jest pomocny podczas tworzenia projektu usługi Intune:

| **Obszar rozwiązania** | **Bieżące środowisko** | **Komentarze** |
|:---:|:---:|:---:|
| **Tożsamość** | Usługa Azure AD, usługa Azure AD Connect, niefederacyjny, brak uwierzytelniania wieloskładnikowego | Istniejący projekt służący do włączenia uwierzytelniania wieloskładnikowego wraz z końcem roku |                 
| **Środowisko poczty e-mail** | Lokalna instalacja programu Exchange, usługa Exchange Online | Obecnie trwa migracja z lokalnej instalacji programu Exchange do usługi Exchange Online. Przeprowadzono migrację 75% skrzynek pocztowych. Pozostałe 25% zostanie zmigrowanych przed rozpoczęciem pilotażowego wdrożenia usługi Intune. |                
| **SharePoint** | Lokalna instalacja programu SharePoint | Nie jest planowane przejście do usługi SharePoint Online |  
| **Bieżące rozwiązanie do zarządzania urządzeniami przenośnymi** | Exchange ActiveSync |  |
| **Rozwiązanie związane z certyfikatem** | Microsoft Server 2012 R2, usługi certyfikatów AD | Infrastruktury PKI należy używać tylko na potrzeby serwerów witryn sieci Web |
| **Zarządzanie systemem** | System Center Configuration Manager CB 1606 | Konieczne jest zbadanie rozwiązań hybrydowych usługi Intune |
| **Rozwiązanie sieci VPN** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Wybieranie opcji wdrożenia usługi Intune

Usługa Intune oferuje dwie opcje wdrożenia: autonomiczną i hybrydową. Określ, która opcja spełnia Twoje wymagania biznesowe. Opcja autonomiczna dotyczy usługi Intune uruchamianej w chmurze, a opcja hybrydowa dotyczy integracji usługi Intune z programem System Center Configuration Manager.

- Dowiedz się więcej na temat [wybierania pomiędzy autonomiczną i hybrydową opcją zarządzania urządzeniami przenośnymi usługi Microsoft Intune za pomocą programu System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Lokalizacja dzierżawy usługi Intune

Jeśli Twoja organizacja działa na całym świecie, upewnij się, czy lokalizacja dzierżawy została zaplanowana w momencie subskrybowania usługi. Kraj jest definiowany podczas pierwszego logowania do subskrypcji usługi Intune i jest mapowany na regiony na całym świecie, które są wymienione poniżej:

-   Ameryka Północna

-   Europa, Bliski Wschód i Afryka

-   Azja i Pacyfik

>[!IMPORTANT]
> Zmiana lokalizacji kraju/dzierżawy nie jest później możliwa.

## <a name="external-dependencies"></a>Zależności zewnętrzne

Zależności zewnętrzne to usługi i produkty, które są niezależne od usługi Intune, ale są przez tą usługę wymagane lub mogą się z nią integrować. Istotne jest, aby zidentyfikować wymagania dotyczące tożsamości dla wszelkich zależności zewnętrznych oraz określić sposób ich konfiguracji. Poniżej przedstawiono kilka przykładów typowych zależności zewnętrznych.

-   Tożsamość

-   Grupy użytkowników i urządzeń

-   PKI

Poniżej przyjrzyjmy się bardziej szczegółowo tym typowym zależnościom zewnętrznym

### <a name="identity"></a>Tożsamość

Za pomocą tożsamości można zidentyfikować użytkowników należących do organizacji i rejestrujących urządzenie. Usługa Intune wymaga usługi Azure Active Directory (Azure AD) jako dostawcy tożsamości użytkowników. Jeśli ta usługa jest już używana, możliwe będzie wykorzystanie tożsamości istniejącej już w chmurze. Ponadto program Azure AD Connect to zalecane narzędzie do synchronizacji tożsamości lokalnych z usługami w chmurze firmy Microsoft. Jeśli Twoja organizacja używa już usługi Office 365, istotne jest, czy usługa Intune używa tego samego środowiska usługi Azure Active Directory.

Poniżej można znaleźć więcej informacji na temat wymagań tożsamości usługi Intune.

-   Dowiedz się więcej o [wymaganiach dotyczących tożsamości](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Dowiedz się więcej o [wymaganiach dotyczących synchronizacji katalogów](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Dowiedz się więcej o [wymaganiach dotyczących uwierzytelniania wieloskładnikowego](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### <a name="user-and-device-groups"></a>Grupy użytkowników i urządzeń

Grupy użytkowników i urządzeń służą do określenia celu wdrożenia. Może to obejmować wdrożenia przeznaczone dla zasad, aplikacji i profilów. Usługa Intune tylko w chmurze obsługuje grupy użytkowników i urządzeń; konieczne będzie określenie, które grupy użytkowników i urządzenia będą wymagane. Zalecane jest, aby wszystkie grupy zostały utworzone w lokalnej usłudze Active Directory, a następnie zsynchronizowane z usługą Azure Active Directory. Więcej informacji dotyczących planowania i tworzenia grup użytkowników i urządzeń można znaleźć poniżej.

-   Dowiedz się więcej na temat [planowania grup użytkowników i urządzeń](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Dowiedz się, [jak tworzyć grupy użytkowników i urządzeń](https://docs.microsoft.com/en-us/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### <a name="public-key-infrastructure-pki"></a>Infrastruktura kluczy publicznych (PKI, Public Key Infrastructure)

Infrastruktura kluczy publicznych dostarcza certyfikaty na urządzenia lub do użytkowników, które służą do bezpiecznego uwierzytelniania w usłudze. Usługa Intune obsługuje infrastrukturę PKI firmy Microsoft. Certyfikaty użytkowników i urządzeń mogą być wystawiane na urządzenie przenośne w celu spełnienia wymagań uwierzytelniania opartego na certyfikatach. Przed wdrożeniem certyfikatów należy określić, czy certyfikaty są wymagane, czy infrastruktura sieciowa może obsługiwać uwierzytelnianie oparte na certyfikatach oraz czy certyfikaty są aktualnie używane w istniejącym środowisku.

Jeśli planowane jest użycie certyfikatów wraz z profilami sieci VPN, sieci Wi-Fi lub poczty e-mail przy użyciu usługi Intune, należy upewnić się, że istnieje obsługiwana [infrastruktura PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles), za pomocą której można tworzyć i wdrażać profile certyfikatów.

Ponadto, jeśli będą wystawiane certyfikaty SCEP, należy określić, który serwer będzie hostem funkcji Usługi rejestracji urządzeń sieciowych (NDES, Network Device Enrollment Service) i w jaki sposób będzie odbywać się komunikacja.

Aby uzyskać więcej informacji o konfigurowaniu certyfikatów w usłudze Intune, zobacz:

-   [Jak skonfigurować infrastrukturę certyfikatów dla profilu SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [Jak skonfigurować infrastrukturę certyfikatów dla profilu PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Jak skonfigurować profile certyfikatów usługi Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Jak skonfigurować zasady dostępu do zasobów firmy](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="device-platform-considerations"></a>Uwagi dotyczące platform urządzeń

Należy dokładnie poznać urządzenia, aby zrozumieć, w jaki sposób używać ich poprawnie.

-   Określanie obsługiwanych platform urządzeń

-   Urządzenia

-   Własność urządzeń

-   Rejestrowanie zbiorcze

Omówmy teraz te zagadnienia w bardziej szczegółowy sposób.

### <a name="determine-supported-device-platforms"></a>Określanie obsługiwanych platform urządzeń

W momencie tworzenia projektu należy wiedzieć, jakie urządzenia będą znajdować się w środowisku, a następnie zweryfikować, czy są one obsługiwane przez usługę Intune. Usługa Intune obsługuje platformy iOS, Android i Windows.

-   Dowiedz się więcej na temat [urządzeń obsługiwanych przez usługę Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

### <a name="devices"></a>Urządzenia

Usługa Intune zarządza urządzeniami przenośnymi w celu zabezpieczenia danych firmowych i umożliwienia użytkownikom końcowym pracy z większej liczby lokalizacji. Usługa Intune obsługuje wiele platform urządzeń, dlatego zalecane jest dokumentowanie urządzeń i platform systemów operacyjnych, które będą obsługiwane w projekcie w organizacji. To zagadnienie zostanie rozwinięte pod kątem urządzeń i platform utworzonych w sekcji (wymagania przypadków użycia).

Zalecana jest również znajomość wersji, aby możliwe było uzyskanie informacji z listy podczas sprawdzania możliwości urządzeń pod kątem platformy systemu operacyjnego i wersji. Oto przykład:

| **Platforma urządzeń** | **Wersje systemu operacyjnego** |
|:---:|:---:|
| iOS — iPhone | 9.0+ |                
| iOS — iPad | 8.0+ |               
| Android — Samsung KNOX Standard | 4.0+ |
| Tablet z systemem Windows 10 | 10+ |

### <a name="device-ownership"></a>Własność urządzeń

Usługa Intune obsługuje zarówno własność firmową, jak i własność zgodną z modelem BYOD. Urządzenie jest określane jako należące do firmy, jeśli zostało zarejestrowane przez menedżera rejestracji urządzeń lub za pośrednictwem programu Device Enrollment Program. Na przykład urządzenie może być zarejestrowane za pośrednictwem programu DEP firmy Apple, oznaczone jako firmowe i umieszczone w grupie urządzeń, która otrzymuje docelowe zasady i aplikacje firmowe.

Aby uzyskać więcej informacji o firmowych i zgodnych z modelem BYOD przypadkach użycia, zobacz [Sekcja 3: Określanie wymagań scenariuszy przypadków użycia](section-3-determine-use-case-requirements.md).

### <a name="bulk-enrollment"></a>Rejestrowanie zbiorcze

Istnieje wiele dostępnych opcji rejestrowania urządzenia w usłudze Intune jako uzupełnienie samoobsługowej rejestracji za pośrednictwem portalu firmy. Rejestrowanie zbiorcze można wykonać na różne sposoby w zależności od platformy. Jeśli rejestrowanie zbiorcze będzie wymagane, należy najpierw określić metodę jego wykonania i uwzględnić ją w projekcie. Więcej informacji o różnych metodach rejestrowania zbiorczego można znaleźć poniżej.

-   Dowiedz się więcej na temat [rejestrowanie zbiorczego](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Wymagania dotyczące funkcji

W tych sekcjach omówimy następujące funkcje i możliwości dopasowane do wymagań scenariusza przypadków użycia:

-   Zasady dotyczące warunków i postanowień

-   Zasady konfiguracji

-   Profile zasobów

-   Aplikacje

-   Zasady zgodności

-   Dostęp warunkowy

Omówmy teraz każde z tych zagadnień w bardziej szczegółowy sposób.

### <a name="terms-and-conditions-policies"></a>Zasady dotyczące warunków i postanowień

Warunki i postanowienia mogą zostać użyte do wyjaśnienia zasad lub warunków, które użytkownik końcowy musi zaakceptować przed rejestracją. Usługa Intune obsługuje możliwość dodawania i wdrażania wielu zasad dotyczących warunków i postanowień na potrzeby grup użytkowników. Należy ustalić, czy zasady dotyczące warunków i postanowień są wymagane. Jeśli tak, to należy ustalić kto będzie odpowiedzialny za udostępnienie tych informacji w organizacji.

-   Dowiedz się, [jak tworzyć zasady dotyczące warunków i postanowień](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) w usłudze Intune. Przykład sposobu dokumentowania zasad dotyczących warunków i postanowień znajduje się poniżej.

| **Nazwa warunków i postanowień** | **Przypadek użycia** | **Grupa docelowa** |
|:---:|:---:|:---:|
| Firmowe warunki i postanowienia | Firmowe | Użytkownicy firmowi |                 
| Warunki i postanowienia dotyczące modelu BYOD | „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Użytkownicy modelu BYOD |                

### <a name="configuration-policies"></a>Zasady konfiguracji

Zasady konfiguracji są używane do zarządzania ustawieniami zabezpieczeń i funkcjami na urządzeniu. Podczas projektowania zasad konfiguracji należy zapoznać się z sekcją wymagań dotyczących przypadków użycia, aby określić konfiguracje wymagane dla urządzeń usługi Intune. Należy udokumentować wybrane ustawienia oraz sposób ich konfiguracji, a także użytkowników lub grupy urządzeń, dla których będą one przeznaczone.

Należy utworzyć co najmniej jeden zestaw zasad konfiguracji dla danej platformy. Dla danej platformy można utworzyć wiele zestawów zasad konfiguracji. Poniżej znajduje się przykład projektowania czterech różnych zestawów zasad konfiguracji dla różnych platform i scenariuszy przypadków użycia.

| **Nazwa zasad** | **Platforma urządzeń** | **Ustawienia** | **Grupa docelowa** |   
|:---:|:---:|:---:|:---:|
| Firmowe — system iOS | iOS | Wymagany jest numer PIN, długość: 6 znaków, nie ma możliwości tworzenia kopii zapasowej w chmurze | Urządzenia firmowe |                                                           
| Firmowe — system Android | Android | Wymagany jest numer PIN, długość: 6 znaków, nie ma możliwości tworzenia kopii zapasowej w chmurze | Urządzenia firmowe |                                                           
| Model BYOD — system iOS  | iOS | Wymagany jest numer PIN, długość: 4 znaki | Urządzenia BYOD |
| Model BYOD — system Android  | Android | Wymagany jest numer PIN, długość: 4 znaki | Urządzenia BYOD |

### <a name="profiles"></a>Profile

Profile ułatwiają połączenie użytkownika końcowego z danymi firmy. Usługa Intune obsługuje wiele typów profilów. Zobacz przypadki użycia i wymagania, aby określić, kiedy [profile](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) zostaną skonfigurowane. Wszystkie profile urządzeń są podzielone względem typu platformy i powinny zostać uwzględnione w dokumentacji projektu.

-   Profile certyfikatów

-   Profil sieci Wi-Fi

-   Profil sieci VPN

-   Profil e-mail

Omówmy teraz każdy typ profilu w bardziej szczegółowy sposób.

##### <a name="certificate-profiles"></a>Profile certyfikatów

Profile certyfikatów umożliwiają usłudze Intune wystawienie certyfikatu dla użytkownika lub urządzenia. Usługa Intune obsługuje następujące certyfikaty:

-   Prosty protokół rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol)

-   Zaufany certyfikat główny

-   Certyfikat PFX.

Zalecane jest, aby udokumentować, która grupa użytkowników potrzebuje certyfikatu, jak wiele profilów certyfikatów będzie potrzebnych i w których grupach użytkowników mają one zostać wdrożone.

>[!NOTE]
> Należy pamiętać, że zaufany certyfikat główny jest wymagany na potrzeby certyfikatu SCEP, więc należy upewnić się, że wszyscy użytkownicy, dla których przeznaczony jest certyfikat SCEP również otrzymają zaufany certyfikat główny. Jeśli wymagane są certyfikaty SCEP, należy zaprojektować potrzebne szablony certyfikatów SCEP i udokumentować je.

Oto przykład, jak można udokumentować certyfikaty podczas projektowania:

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |   
|:---:|:---:|:---:|:---:|
| Główny urząd certyfikacji | Firmowy główny urząd certyfikacji | Android, iOS i Windows Mobile | Firmowe, BYOD  |                                                           
| SCEP | Certyfikat użytkownika | Android, iOS i Windows Mobile | Firmowe, BYOD |                                                           

##### <a name="wi-fi-profile"></a>Profil sieci Wi-Fi

Profile sieci Wi-Fi są używane do automatycznego połączenia urządzenia przenośnego z siecią bezprzewodową. Usługa Intune obsługuje wdrażanie profilów sieci Wi-Fi na wszystkich obsługiwanych platformach.

-   Dowiedz się więcej na temat tego, [jak usługa Intune obsługuje profile sieci Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune).

Poniżej przedstawiono przykładowy projekt dla profilu sieci Wi-Fi:

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Profil sieci Wi-Fi (Azja) | Android | Firmowe, BYOD (region Azja)|                                                           
| Wi-Fi | Profil sieci Wi-Fi (Ameryka Północna) | Android, iOS i Windows 10 Mobile | Firmowe, BYOD (region Ameryka Północna) |                                                           

##### <a name="vpn-profile"></a>Profil sieci VPN

Profile sieci VPN umożliwiają użytkownikom bezpieczny dostęp do sieci z lokalizacji zdalnych. Usługa Intune obsługuje profile sieci VPN z macierzystych mobilnych połączeń sieci VPN i od innych dostawców.

-   Dowiedz się więcej o [profilach sieci VPN i dostawcach obsługiwanych przez usługę Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune).

Poniżej przedstawiono przykład dokumentowania projektu profilu sieci VPN.

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |   
|:---:|:---:|:---:|:---:|
| VPN | Profil Cisco AnyConnect sieci VPN | Android, iOS i Windows 10 Mobile | Firmowe, BYOD (region Ameryka Północna i Niemcy)|                                                           
| VPN | Pulse Secure | Android | Firmowe, BYOD (region Azja) |                                                           

##### <a name="email-profile"></a>Profil e-mail

Profile poczty e-mail pozwalają na automatyczne konfigurowanie klientów poczty e-mail za pomocą informacji dotyczących połączenia oraz na konfigurowanie poczty e-mail. Usługa Intune obsługuje profile poczty e-mail na niektórych urządzeniach.

-   Dowiedz się więcej o [profilach poczty e-mail](https://docs.microsoft.com/en-us/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) i obsługiwanych platformach.

Poniżej przedstawiono przykład dokumentowania projektu profilów poczty e-mail:

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |   
|:---:|:---:|:---:|:---:|
| Profil e-mail | Profil e-mail systemu iOS | iOS | Firmowy — model BYOD dla pracownika przetwarzającego informacje |                                                           
| Profil e-mail | Profil e-mail systemu Android Knox | Android Knox | „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) |

### <a name="apps"></a>Aplikacje

Usługa Intune obsługuje dostarczanie aplikacji do użytkowników lub na urządzenia na wiele sposobów. Typem dostarczanej aplikacji mogą być aplikacje instalatora oprogramowania, aplikacje z publicznego sklepu z aplikacjami, linki zewnętrzne lub zarządzane aplikacje dla systemu iOS. Oprócz pojedynczych wdrożeń aplikacje nabyte w ramach zakupów zbiorczych mogą być zarządzane i wdrażanie za pomocą programów zakupów zbiorczych dla systemu iOS i Windows. Poniżej znajduje się więcej informacji dotyczących sposobu obsługi przez usługę Intune aplikacji i programów zakupów zbiorczych.

-   Dowiedz się więcej o [typach aplikacji](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)

-   Dowiedz się więcej o programie [iOS Volume Purchase Program for Business (VPP)](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).

-   Dowiedz się więcej o [Sklepie Windows dla firm](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### <a name="app-type-requirements"></a>Wymagania dotyczące typu aplikacji

Ponieważ aplikacje można wdrożyć dla użytkowników i na urządzeniach, zaleca się podjęcie decyzji, które aplikacje będą zarządzane przez usługę Intune. Podczas wypełniania listy spróbuj odpowiedzieć na następujące pytania:

-   Czy aplikacje wymagają integracji z usługami w chmurze?

-   Czy wszystkie aplikacje będą dostępne dla użytkowników pracujących w modelu BYOD?

-   Jakie są opcje wdrażania dostępne dla tych aplikacji?

-   Czy firma musi zapewniać dostęp do danych aplikacji oprogramowania jako usługi (SaaS) swoim partnerom?

-   Czy aplikacje będą wymagały dostępu do Internetu na urządzeniach użytkowników?

-   Czy aplikacje są publicznie dostępne w sklepie z aplikacjami, czy są one niestandardowymi aplikacjami biznesowymi?


>[!TIP]
> Zapoznaj się z [różnymi typami aplikacji obsługiwanych przez usługę Intune](https://docs.microsoft.com/intune/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Zasady ochrony aplikacji minimalizują utratę danych przez zdefiniowanie sposobu, w jaki aplikacja zarządza danymi firmowymi. Usługa Intune obsługuje zasady ochrony aplikacji dla każdej aplikacji utworzonej w celu działania w ramach zarządzania aplikacjami mobilnymi. Podczas projektowania zasad ochrony aplikacji należy określić, jakie ograniczenia danych firmowych zostaną wprowadzone w danej aplikacji. Zalecane jest, aby przejrzeć sposób [działania zasad ochrony aplikacji](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Poniżej przedstawiono przykład sposobu dokumentowania istniejących aplikacji oraz przykład wymaganej ochrony.

| **Aplikacja** | **Cel** | **Platformy** | **Przypadek użycia** | **Zasady ochrony aplikacji** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Dostępne | iOS | Firmowe — Kierownicy | Nie może mieć złamanych zabezpieczeń producenta, szyfrowanie plików |                                                         
| Word | Dostępne | iOS, Android — system Samsung Knox, system inny niż Samsung Knox, Windows 10 Mobile | Firmowe, BYOD | Nie może mieć złamanych zabezpieczeń producenta, szyfrowanie plików |                                                         

#### <a name="compliance-policies"></a>Zasady zgodności

Zasady zgodności określają, czy urządzenie spełnia określone wymagania. Usługa Intune używa zasad zgodności do określenia, czy urządzenie jest zgodne, czy niezgodne. Stanu zgodności można następnie użyć do ograniczenia dostępu do zasobów firmy. Jeśli wymagany jest dostęp warunkowy, zalecane jest zaprojektowanie [zasad zgodności urządzeń](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Zapoznaj się z wymaganiami i przypadkami użycia, aby określić ilość wymaganych zasad zgodności urządzeń oraz docelowe grupy użytkowników. Ponadto należy określić, jak długo urządzenie może być w trybie offline bez zaewidencjonowania, zanim zostanie uznane za niezgodne.

Poniżej przedstawiono przykład sposobu projektowania zasad zgodności:

| **Nazwa zasad** | **Platforma urządzeń** | **Ustawienia** | **Grupa docelowa** |   
|:---:|:---:|:---:|:---:|
| Zasady zgodności | iOS, Android — system Samsung Knox, system inny niż Samsung Knox, Windows 10 Mobile | Wymagany jest numer PIN, nie może mieć złamanych zabezpieczeń producenta | Firmowe, BYOD |

#### <a name="conditional-access-policies"></a>Zasady dostępu warunkowego

Dostęp warunkowy służy do umożliwiania dostępu do zasobów firmy tylko zgodnym urządzeniom. Usługa Intune współdziała z całym pakietem Enterprise Mobility + Security (EMS) w celu kontrolowania dostępu do zasobów firmy. Konieczne będzie ustalenie, czy wymagany jest dostęp warunkowy, oraz określenie elementów, które muszą być chronione.

-   Dowiedz się więcej na temat [dostępu warunkowego](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

Na potrzeby dostępu online określ platformy i grupy użytkowników, których będą dotyczyć zasady dostępu warunkowego.

Ponadto należy określić, czy należy zainstalować lub skonfigurować łącznik Intune Service To Service Connector na potrzeby usługi Exchange Online lub lokalnej instalacji programu Exchange.

Dowiedz się więcej na temat sposobu konfigurowania łączników Intune Service to Service Connector:

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Lokalna instalacja programu Exchange](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Oto przykład sposobu dokumentowania zasad dostępu warunkowego:

| **Usługa** | **Platformy korzystające z nowoczesnych metod uwierzytelniania** | **Uwierzytelnianie podstawowe** | **Przypadki użycia** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Blokuj niezgodne urządzenia na platformach obsługiwanych przez usługę Intune | Firmowe, BYOD |
| SharePoint Online | iOS, Android |  | Firmowe, BYOD |

## <a name="next-section"></a>Następna sekcja

W następnej sekcji znajdują się wskazówki dotyczące [procesu implementowania usługi Intune](section-8-onboarding-process.md).



<!--HONumber=Jan17_HO3-->


