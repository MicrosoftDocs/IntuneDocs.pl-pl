---
title: Tworzenie projektu usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Ten artykuł jest pomocny w przypadku tworzenia projektu i implementacji tylko w chmurze usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c18f3e8fb14d8592789b39856ec420790fad286
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547551"
---
# <a name="create-a-design"></a>Tworzenie projektu

Twój projekt usługi Intune będzie opierać się na zbieranych przez Ciebie informacjach oraz decyzjach podejmowanych podczas wykonywania innych [sekcji tego przewodnika](../planning-guide.md). Będzie on pomocny podczas przygotowywania następujących elementów:

- Bieżące środowisko

- Opcje wdrożenia usługi Intune

- Wymagania dotyczące tożsamości dla zależności zewnętrznych

- Uwagi dotyczące platform urządzeń

- Wymagania do spełnienia  

Chociaż wymagania dotyczące infrastruktury lokalnej są minimalne, plan projektu jest nadal pomocny, aby zapewnić istnienie prawidłowego rozwiązania do zarządzania urządzeniami mobilnymi spełniającego Twoje cele, zamierzenia i wymagania.

Omówmy teraz każde z tych zagadnień w bardziej szczegółowy sposób. 

## <a name="record-your-current-environment"></a>Rejestrowanie bieżącego środowiska
Ponadto często mają miejsce zmiany projektu w fazach wdrażania i testowania. Użyj swojego planu projektu do dokumentowania tych zmian i ich uzasadnień w miarę ich występowania.

Twoje bieżące środowisko może mieć wpływ na decyzje projektowe i powinno być udokumentowane i sprawdzane w momencie podejmowania innych decyzji dotyczących projektu usługi Intune. Poniżej przedstawiono kilka przykładów sposobu rejestrowania bieżącego środowiska:

- **Tożsamość w chmurze**

  - Czy używasz narzędzia DirSync lub programu Azure Active Directory (AAD) Connect?

  - Czy Twoje środowisko jest federacyjne?

  - Czy włączono uwierzytelnianie wieloskładnikowe (MFA)?

- **Środowisko poczty e-mail**

  - Czy używasz programu Exchange? Czy działa on lokalnie, czy w chmurze?

  - Czy jesteś w trakcie projektu migracji programu Exchange do chmury?

- **Bieżące rozwiązanie do zarządzania urządzeniami mobilnymi (MDM)**

  - Czy obecnie używasz innych rozwiązań do zarządzania urządzeniami przenośnymi?

  - Jakich rozwiązań MDM używasz dla następujących scenariuszy przypadków użycia: firmowego i modelu „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)?

  - Z jakich możliwości korzystasz (na przykład: ustawienia urządzenia aplikacji, konfiguracje sieci Wi-Fi)?

  - Jakie platformy urządzeń są obsługiwane?

  - Przez jakie grupy i ilu użytkowników używane jest rozwiązanie do zarządzania urządzeniami przenośnymi?

- **Rozwiązanie związane z certyfikatem**

  - Czy wdrożone zostało rozwiązanie związane z certyfikatem?

  - Jakie typy certyfikatów są używane?

- **Zarządzanie systemami**

  - W jaki sposób zarządzasz środowiskiem komputera PC i serwera?

  - Korzystasz z programu Microsoft Endpoint Configuration Manager? Czy używasz platformy zarządzania systemami innej firmy?

- **Rozwiązanie sieci VPN**

  - Jakie jest Twoje rozwiązanie sieci VPN?

  - Czy używasz go w obu scenariuszach przypadków użycia: firmowym i BYOD?

Upewnij się, że uwzględniono wszystkie istniejące projekty i inne plany, które mogłyby wpłynąć na Twoje środowisko podczas rejestrowania bieżącego środowiska zarządzania urządzeniami mobilnymi. Poniżej przedstawiono przykładowy sposób rejestrowania bieżącego środowiska podczas tworzenia projektu usługi Intune:

| **Obszar rozwiązania** | **Bieżące środowisko** | **Komentarze** |
|---|---|---|
| **Tożsamość** | Usługa Azure AD, usługa Azure AD Connect, niefederacyjny, brak uwierzytelniania wieloskładnikowego | Istniejący projekt służący do włączenia uwierzytelniania wieloskładnikowego wraz z końcem roku |                 
| **Środowisko poczty e-mail** | Lokalna instalacja programu Exchange, usługa Exchange Online | Obecnie trwa migracja z lokalnej instalacji programu Exchange do usługi Exchange Online. Przeprowadzono migrację 75% skrzynek pocztowych. Pozostałe 25% zostanie zmigrowanych przed rozpoczęciem pilotażowego wdrożenia usługi Intune. |                
| **SharePoint** | Lokalna instalacja programu SharePoint | Nie jest planowane przejście do usługi SharePoint Online |  
| **Bieżące rozwiązanie do zarządzania urządzeniami przenośnymi** | Exchange ActiveSync |  |
| **Rozwiązanie związane z certyfikatem** | Microsoft Server 2012 R2, usługi certyfikatów AD | Infrastruktury PKI należy używać tylko na potrzeby serwerów witryn sieci Web |
| **Zarządzanie systemem** | Configuration Manager CB 1606 | Konieczne jest zbadanie rozwiązań hybrydowych usługi Intune |
| **Rozwiązanie sieci VPN** | Cisco AnyConnect |  |


W celu opracowania własnego planu projektu usługi Intune możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

## <a name="choose-an-intune-deployment-option"></a>Wybieranie opcji wdrożenia usługi Intune

Usługa Intune oferuje dwie opcje wdrożenia: autonomiczną i hybrydową. Opcja autonomiczna dotyczy usługi Intune uruchamianej w chmurze, a opcja hybrydowa dotyczy integracji usługi Intune z programem Configuration Manager. Ten przewodnik jest przeznaczony głównie do użycia opcji autonomicznej. [Określ, która opcja spełnia Twoje wymagania biznesowe](https://docs.microsoft.com/configmgr/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

> [!Important]
>Funkcja dołączania nowych klientów hybrydowego rozwiązania MDM jest przestarzała. Aby uzyskać więcej informacji, zobacz wpis w blogu [Move from Hybrid Mobile Device Management to Intune on Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) (Przechodzenie z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune na platformie Azure).


## <a name="intune-tenant-location"></a>Lokalizacja dzierżawy usługi Intune

Jeśli Twoja organizacja działa na całym świecie, upewnij się, że lokalizacja dzierżawy została zaplanowana w momencie subskrybowania usługi. Kraj/region jest definiowany podczas pierwszego logowania do subskrypcji usługi Intune i jest mapowany na kraje/regiony na całym świecie, które zostały wymienione poniżej:

- Ameryka Północna

- Europa, Bliski Wschód i Afryka

- Azja i Pacyfik

>[!IMPORTANT]
> Zmiana kraju/regionu lub lokalizacji dzierżawy nie jest później możliwa.

## <a name="external-dependencies"></a>Zależności zewnętrzne

Zależności zewnętrzne to usługi i produkty, które są niezależne od usługi Intune, ale są przez tę usługę wymagane lub mogą się z nią integrować. Istotne jest, aby zidentyfikować wymagania dotyczące tożsamości dla wszelkich zależności zewnętrznych oraz określić sposób ich konfiguracji. Do niektórych przykładów typowych zależności zewnętrznych należą:

- Tożsamość

- Grupy użytkowników i urządzeń

- Infrastruktura kluczy publicznych (PKI, Public Key Infrastructure)

Poniżej omówimy bardziej szczegółowo te typowe zależności zewnętrzne.

### <a name="identity"></a>Tożsamość

Za pomocą tożsamości można zidentyfikować użytkowników należących do organizacji i rejestrujących urządzenie. Usługa Intune wymaga usługi Azure Active Directory (Azure AD) jako dostawcy tożsamości użytkowników. Jeśli już używasz tej usługi, możesz użyć swojej tożsamości już istniejącej w chmurze. Ponadto program Azure AD Connect to zalecane narzędzie do synchronizacji tożsamości lokalnych z usługami w chmurze firmy Microsoft. Jeśli Twoja organizacja używa już usługi Office 365, istotne jest, aby usługa Intune używała tego samego środowiska usługi Azure AD.

Dowiedz się więcej o następujących wymaganiach dotyczących tożsamości usługi Intune:

- [Wymagania dotyczące tożsamości](https://docs.microsoft.com/azure/active-directory/understand-azure-identity-solutions).

- [Wymagania dotyczące synchronizacji katalogu](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

- [Wymagania dotyczące uwierzytelniania wieloskładnikowego](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).

### <a name="user-and-device-groups"></a>Grupy użytkowników i urządzeń

Grupy użytkowników i urządzeń określają cel wdrożenia, a w tym zasady, aplikacje i profile. Musisz ustalić, jakie grupy użytkowników i urządzeń będą wymagane.

Zalecamy utworzenie wszystkich grup w lokalnej usłudze Active Directory, a następnie zsynchronizowanie z usługą Azure AD. Dowiedz się więcej na temat planowania i tworzenia grup użytkowników i urządzeń:

- [Planowanie własnych grup użytkowników i urządzeń](users-add.md).

- [Sposoby tworzenia grup użytkowników i urządzeń](groups-add.md).

### <a name="public-key-infrastructure-pki"></a>Infrastruktura kluczy publicznych (PKI, Public Key Infrastructure)
Infrastruktura kluczy publicznych dostarcza na urządzenia lub użytkownikom certyfikaty, które służą do bezpiecznego uwierzytelniania w usłudze. Usługa Intune obsługuje infrastrukturę PKI firmy Microsoft. Certyfikaty użytkowników i urządzeń mogą być wystawiane na urządzenie przenośne w celu spełnienia wymagań uwierzytelniania opartego na certyfikatach. Przed użyciem certyfikatów określ, czy są one potrzebne, czy infrastruktura sieciowa może obsługiwać uwierzytelnianie oparte na certyfikatach oraz czy certyfikaty są aktualnie używane w istniejącym środowisku.

Jeśli planujesz użycie certyfikatów wraz z profilami sieci VPN, sieci Wi-Fi lub poczty e-mail przy użyciu usługi Intune, upewnij się, że istnieje obsługiwana [infrastruktura PKI](../protect/certificates-configure.md), za pomocą której można tworzyć i wdrażać profile certyfikatów.

Ponadto, jeśli będą używane profile certyfikatów SCEP, określ, który serwer będzie hostem funkcji Usługi rejestracji urządzeń sieciowych (NDES, Network Device Enrollment Service) i w jaki sposób będzie odbywać się komunikacja.

Dowiedz się więcej na następujące tematy:

- [Jak skonfigurować profile certyfikatów usługi Intune](../protect/certificates-configure.md)

- [Jak skonfigurować infrastrukturę certyfikatów dla profilu SCEP](../protect/certificates-scep-configure.md)

- [Jak skonfigurować infrastrukturę certyfikatów dla profilu PFX](../protect/certficates-pfx-configure.md)




## <a name="device-platform-considerations"></a>Uwagi dotyczące platform urządzeń

Przyjrzyj się bliżej następującym aspektom swoich urządzeń, aby zrozumieć sposób poprawnego zarządzania nimi.

- Obsługiwane platformy urządzeń

- Devices

- Własność urządzeń

- Rejestrowanie zbiorcze

Omówmy teraz te zagadnienia w bardziej szczegółowy sposób.

### <a name="determine-supported-device-platforms"></a>Określanie obsługiwanych platform urządzeń

W momencie tworzenia projektu należy wiedzieć, jakie urządzenia będą znajdować się w środowisku, a następnie zweryfikować, czy są one obsługiwane przez usługę Intune. Usługa Intune obsługuje platformy iOS, Android i Windows.

[Pełna lista urządzeń obsługiwanych przez usługę Intune](supported-devices-browsers.md).

### <a name="devices"></a>Devices

Usługa Intune zarządza urządzeniami przenośnymi w celu zabezpieczenia danych firmowych i umożliwienia użytkownikom końcowym pracy z większej liczby lokalizacji. Usługa Intune obsługuje wiele platform urządzeń, dlatego zalecane jest dokumentowanie urządzeń oraz platform i wersji systemów operacyjnych, które będą obsługiwane w projekcie w organizacji. Przykład:

| **Platforma urządzeń** | **Wersje systemu operacyjnego** |
|:---:|:---:|
| iOS — iPhone | 10.0+ |                
| iOS — iPad | 10.0+ |               
| Android — Samsung KNOX Standard | 4.0+ |
| Tablet z systemem Windows 10 | 10+ |


W celu opracowania własnej listy urządzeń możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
### <a name="device-ownership"></a>Własność urządzeń

Usługa Intune obsługuje zarówno urządzenia należące do firmy, jak i urządzenia osobiste. Urządzenie jest uważane za należące do firmy, jeśli rejestrujesz je przez menedżera rejestracji urządzeń lub za pośrednictwem programu Device Enrollment Program. Na przykład urządzenie zarejestrowane za pośrednictwem programu Device Enrollment Program (DEP) firmy Apple, oznaczone jako firmowe i umieszczone w grupie urządzeń, która otrzymuje docelowe zasady i aplikacje firmowe.

Zobacz [Sekcja 3: Określanie wymagań scenariuszy przypadków użycia](planning-guide-requirements.md), aby uzyskać więcej informacji o firmowych i zgodnych z modelem BYOD przypadkach użycia.

### <a name="bulk-enrollment"></a>Rejestrowanie zbiorcze

 Możesz zarejestrować urządzenia w trybie zbiorczym na różne sposoby w zależności od platformy. Jeśli rejestrowanie zbiorcze będzie wymagane, najpierw [określ metodę rejestrowania zbiorczego](../enrollment/device-enrollment.md), a następnie uwzględnij ją w swoim projekcie.

## <a name="feature-requirements"></a>Wymagania dotyczące funkcji

W tych sekcjach omówimy następujące funkcje i możliwości dopasowane do wymagań Twojego scenariusza przypadków użycia:

- Zasady dotyczące warunków i postanowień

- Zasady konfiguracji

- Profile zasobów

- Aplikacje

- Zasady zgodności

- Dostęp warunkowy

Omówmy teraz każde z tych zagadnień w bardziej szczegółowy sposób.

### <a name="terms-and-conditions-policies"></a>Zasady dotyczące warunków i postanowień

[Warunków i postanowień](../enrollment/terms-and-conditions-create.md) możesz użyć do wyjaśnienia zasad lub warunków, które użytkownik końcowy musi zaakceptować, zanim będzie mógł zarejestrować urządzenie. Usługa Intune obsługuje możliwość dodawania i wdrażania wielu zasad dotyczących warunków i postanowień na potrzeby grup użytkowników.

Należy ustalić, czy zasady dotyczące warunków i postanowień są wymagane. Jeśli tak, to należy ustalić kto będzie odpowiedzialny za udostępnienie tych informacji w organizacji. Przykład sposobu dokumentowania zasad dotyczących warunków i postanowień znajduje się poniżej.

| **Nazwa warunków i postanowień** | **Przypadek użycia** | **Grupa docelowa** |
|:---:|:---:|:---:|
| Firmowe warunki i postanowienia | Firmowe | Użytkownicy firmowi |                 
| Warunki i postanowienia dotyczące modelu BYOD | „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Użytkownicy modelu BYOD |                


Aby zmapować swoje warunki i postanowienia na grupy użytkowników, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

### <a name="configuration-policies"></a>Zasady konfiguracji

Użyj zasad konfiguracji do zarządzania ustawieniami zabezpieczeń i funkcjami na urządzeniu. Podczas projektowania zasad konfiguracji należy zapoznać się z sekcją wymagań dotyczących przypadków użycia, aby określić konfiguracje wymagane dla urządzeń usługi Intune. Udokumentuj ustawienia i sposób, w jaki powinny zostać skonfigurowane. Udokumentuj również, które grupy użytkowników lub urządzeń będą grupami docelowymi.

Należy utworzyć co najmniej jeden zestaw zasad konfiguracji dla danej platformy. Dla danej platformy możesz w razie potrzeby utworzyć kilka zestawów zasad konfiguracji. Poniżej znajduje się przykład projektowania czterech różnych zestawów zasad konfiguracji dla różnych platform i scenariuszy przypadków użycia.

| **Nazwa zasad** | **Platforma urządzeń** | **Ustawienia** | **Grupa docelowa** |   
|:---:|:---:|:---:|:---:|
| Firmowe — system iOS | iOS | Wymagany jest numer PIN, długość: 6, Ograniczenie możliwości tworzenia kopii zapasowej w chmurze | Urządzenia firmowe |                                                           
| Firmowe — system Android | Android | Wymagany jest numer PIN, długość: 6, Ograniczenie możliwości tworzenia kopii zapasowej w chmurze | Urządzenia firmowe |                                                           
| Model BYOD — system iOS  | iOS | Wymagany jest numer PIN, długość: 4 | Urządzenia BYOD |
| Model BYOD — system Android  | Android | Wymagany jest numer PIN, długość: 4 | Urządzenia BYOD |


Aby zidentyfikować potrzeby swojego zestawu zasad konfiguracji, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

### <a name="profiles"></a>Profile

Użycie profilów ułatwia połączenie użytkownika końcowego z danymi firmy. Usługa Intune obsługuje wiele typów profilów. Zobacz przypadki użycia i wymagania, aby określić, kiedy profile zostaną skonfigurowane. Wszystkie profile urządzeń są podzielone na kategorie według typu platformy i powinny zostać uwzględnione w dokumentacji projektu.

- Profile certyfikatów

- Profil sieci Wi-Fi

- Profil sieci VPN

- Profil e-mail

Omówmy teraz każdy typ profilu w bardziej szczegółowy sposób.

#### <a name="certificate-profiles"></a>Profile certyfikatów

Profile certyfikatów umożliwiają usłudze Intune wystawienie certyfikatu dla użytkownika lub urządzenia. Usługa Intune obsługuje następujące certyfikaty:

- Prosty protokół rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol)

- Zaufany certyfikat główny

- Certyfikat PFX.

Zalecamy udokumentowanie, która grupa użytkowników potrzebuje certyfikatu, jak wiele profilów certyfikatów będzie potrzebnych i w których grupach użytkowników mają one zostać wdrożone.

>[!NOTE]
> Należy pamiętać, że zaufany certyfikat główny jest wymagany na potrzeby profilu certyfikatu SCEP, więc należy upewnić się, że wszyscy użytkownicy, dla których przeznaczony jest profil certyfikatu SCEP również otrzymają zaufany certyfikat główny. Jeśli wymagane są certyfikaty SCEP, zaprojektuj potrzebne szablony certyfikatów SCEP i udokumentuj je.

Oto przykład, jak można udokumentować certyfikaty podczas projektowania:

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |   
|:---:|:---:|:---:|:---:|
| Główny urząd certyfikacji | Firmowy główny urząd certyfikacji | Android, iOS i Windows Mobile | Firmowe, BYOD  |                                                           
| SCEP | Certyfikat użytkownika | Android, iOS i Windows Mobile | Firmowe, BYOD |                                                           


Aby zidentyfikować potrzeby swojego profilu certyfikatu, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

#### <a name="wi-fi-profile"></a>Profil sieci Wi-Fi

Profile sieci Wi-Fi są używane do automatycznego łączenia urządzenia przenośnego z siecią bezprzewodową. Usługa Intune obsługuje wdrażanie profilów sieci Wi-Fi na wszystkich obsługiwanych platformach. Dowiedz się więcej na temat tego, [jak usługa Intune obsługuje profile sieci Wi-Fi](../configuration/wi-fi-settings-configure.md).

Poniżej przedstawiono przykładowy projekt dla profilu sieci Wi-Fi:

| **Wpisz** | **Nazwa profilu** | **Platforma urządzenia** | **Przypadki użycia** | | Sieć Wi-Fi | Profil sieci Wi-Fi (Azja) | Android | Firmowe, BYOD (region Azja)| | Sieć Wi-Fi | Profil sieci Wi-Fi (Ameryka Północna) | Android, iOS, Windows 10 Mobile | Firmowe, BYOD (region Ameryka Północna) |

Aby zidentyfikować potrzeby swojego profilu sieci Wi-Fi, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

#### <a name="vpn-profile"></a>Profil sieci VPN

Profile sieci VPN umożliwiają użytkownikom bezpieczny dostęp do sieci z lokalizacji zdalnych. Usługa Intune obsługuje profile sieci VPN z natywnych mobilnych połączeń sieci VPN i od innych dostawców. Dowiedz się więcej o [profilach sieci VPN i dostawcach obsługiwanych przez usługę Intune](../configuration/vpn-settings-configure.md).

Poniżej przedstawiono przykład dokumentowania projektu profilu sieci VPN.

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |
|:---:|:---:|:---:|:---:|
| VPN | Profil Cisco AnyConnect sieci VPN | Android, iOS i Windows 10 Mobile | Firmowe, BYOD (region Ameryka Północna i Niemcy)|
| VPN | Pulse Secure | Android | Firmowe, BYOD (region Azja) |

Aby zidentyfikować potrzeby swojego profilu sieci VPN, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

#### <a name="email-profile"></a>Profil e-mail

Profile poczty e-mail pozwalają na automatyczne konfigurowanie klientów poczty e-mail za pomocą informacji dotyczących połączenia oraz na konfigurowanie poczty e-mail. Usługa Intune obsługuje profile poczty e-mail na niektórych urządzeniach. Dowiedz się więcej o [profilach poczty e-mail i obsługiwanych platformach](../configuration/email-settings-configure.md).

Poniżej przedstawiono przykład dokumentowania projektu profilów poczty e-mail:

| **Typ** | **Nazwa profilu** | **Platforma urządzeń** | **Przypadki użycia** |
|:---:|:---:|:---:|:---:|
| Profil e-mail | Profil e-mail systemu iOS | iOS | Firmowy — model BYOD dla pracownika przetwarzającego informacje |
| Profil e-mail | Profil e-mail systemu Android Knox | Android Knox | „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) |

Aby zidentyfikować potrzeby swojego profilu poczty e-mail, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
### <a name="apps"></a>Aplikacje

Usługi Intune możesz użyć do dostarczania aplikacji użytkownikom lub do urządzeń na kilka sposobów. Typy aplikacji obejmują aplikacje instalatora oprogramowania, aplikacje z publicznego sklepu z aplikacjami, linki zewnętrzne lub zarządzane aplikacje dla systemu iOS. Oprócz pojedynczych wdrożeń aplikacji możesz zarządzać aplikacjami nabytymi w ramach zakupów zbiorczych i wdrażać je za pomocą programów zakupów zbiorczych dla systemu iOS i Windows. Dowiedz się więcej na następujące tematy:

- [Typy aplikacji, które możesz dostarczać](../apps/app-management.md)

- [iOS Volume Purchase Program for Business (VPP)](../apps/vpp-apps-ios.md)

- [Aplikacje ze sklepu Microsoft Store dla Firm](../apps/windows-store-for-business.md)

#### <a name="app-type-requirements"></a>Wymagania dotyczące typu aplikacji

Ponieważ aplikacje można wdrożyć dla użytkowników i na urządzeniach, zalecamy podjęcie decyzji, które aplikacje będą zarządzane przez usługę Intune. Podczas wypełniania listy spróbuj odpowiedzieć na następujące pytania:

- Czy aplikacje wymagają integracji z usługami w chmurze?

- Czy wszystkie aplikacje będą dostępne dla użytkowników pracujących w modelu BYOD?

- Jakie są opcje wdrażania dostępne dla tych aplikacji?

- Czy Twoja firma musi zapewniać dostęp do danych aplikacji oprogramowania jako usługi (SaaS) swoim partnerom?

- Czy aplikacje będą wymagały dostępu do Internetu na urządzeniach użytkowników?

- Czy aplikacje są publicznie dostępne w sklepie z aplikacjami, czy też są one niestandardowymi aplikacjami biznesowymi (LOB)?


#### <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Zasady ochrony aplikacji minimalizują utratę danych przez zdefiniowanie sposobu, w jaki aplikacja zarządza danymi firmowymi. Usługa Intune obsługuje zasady ochrony aplikacji dla każdej aplikacji utworzonej w celu działania w ramach zarządzania aplikacjami mobilnymi. Podczas projektowania zasad ochrony aplikacji zdecyduj, jakie ograniczenia danych firmowych mają zostać wprowadzone w danej aplikacji. Zalecamy przejrzenie sposobu działania [zasad ochrony aplikacji](../apps/app-protection-policy.md). Poniżej przedstawiono przykład sposobu dokumentowania istniejących aplikacji oraz przykład wymaganej ochrony.

| **Aplikacja** | **Cel** | **Platformy** | **Przypadek użycia** | **Zasady ochrony aplikacji** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Dostępne | iOS | Firmowe — Kierownicy | Nie może mieć złamanych zabezpieczeń producenta, szyfrowanie plików |                                                         
| Word | Dostępne | iOS, Android — system Samsung Knox, system inny niż Samsung Knox, Windows 10 Mobile | Firmowe, BYOD | Nie może mieć złamanych zabezpieczeń producenta, szyfrowanie plików |                                                         


Aby zidentyfikować potrzeby swoich zasad ochrony aplikacji, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
#### <a name="compliance-policies"></a>Zasady zgodności

Zasady zgodności określają, czy urządzenie spełnia określone wymagania. Usługa Intune używa zasad zgodności do określenia, czy urządzenie jest zgodne, czy niezgodne. Stanu zgodności można następnie użyć do ograniczenia lub umożliwienia dostępu do zasobów firmy. Jeśli wymagany jest dostęp warunkowy, zalecamy zaprojektowanie [zasad zgodności urządzeń](../protect/device-compliance-get-started.md).

Zapoznaj się z wymaganiami i przypadkami użycia, aby określić liczbę wymaganych zasad zgodności urządzeń oraz docelowe grupy użytkowników. Ponadto musisz określić, jak długo urządzenie może być w trybie offline bez zaewidencjonowania, zanim zostanie uznane za niezgodne.

Poniżej przedstawiono przykład sposobu projektowania zasad zgodności:

| **Nazwa zasad** | **Platforma urządzeń** | **Ustawienia** | **Grupa docelowa** |
|:---:|:---:|:---:|:---:|
| Zasady zgodności | iOS, Android — system Samsung Knox, system inny niż Samsung Knox, Windows 10 Mobile | Wymagany jest numer PIN, nie może mieć złamanych zabezpieczeń producenta | Firmowe, BYOD |


Aby zidentyfikować potrzeby swoich zasad zgodności, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
#### <a name="conditional-access-policies"></a>Zasady dostępu warunkowego

Dostęp warunkowy służy do umożliwiania dostępu do poczty e-mail i innych zasobów firmy tylko zgodnym urządzeniom. Usługa Intune współdziała z pakietem Enterprise Mobility + Security (EMS) w celu kontrolowania dostępu do zasobów firmy. Zdecyduj, czy potrzebujesz dostępu warunkowego, oraz określ elementy, które muszą być chronione. Dowiedz się więcej na temat [dostępu warunkowego](../protect/conditional-access.md).

Na potrzeby dostępu online zdecyduj, których platform i grup użytkowników będą dotyczyć zasady dostępu warunkowego. Ponadto określ, czy należy zainstalować lub skonfigurować łącznik usługi Intune dla lokalnego programu Exchange: 

- [Lokalna instalacja programu Exchange](../protect/exchange-connector-install.md)

Oto przykład sposobu dokumentowania zasad dostępu warunkowego:

| **Usługa** | **Platformy korzystające z nowoczesnych metod uwierzytelniania** | **Uwierzytelnianie podstawowe** | **Przypadki użycia** |
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Blokuj niezgodne urządzenia na platformach obsługiwanych przez usługę Intune | Firmowe, BYOD |
| SharePoint Online | iOS, Android |  | Firmowe, BYOD |

Aby zidentyfikować potrzeby swoich zasad dostępu warunkowego, możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

## <a name="next-steps"></a>Następne kroki

W następnej sekcji znajdują się wskazówki dotyczące [procesu implementowania usługi Intune](planning-guide-onboarding.md).
