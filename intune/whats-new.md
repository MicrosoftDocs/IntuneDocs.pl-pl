---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titlesuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: e3049fe461553ad1ba2e714d2274e0d39d169852
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2018
ms.locfileid: "44254092"
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również dowiedzieć się o [nadchodzących zmianach](#whats-coming), [ważnych powiadomieniach](#notices) o usłudze oraz uzyskać informacje o [poprzednich wersjach](whats-new-archive.md). Niektóre funkcje mogą być wprowadzane przez kilka tygodni i nie być dostępne dla wszystkich klientów w pierwszym tygodniu.

> [!Note]
> Aby uzyskać informacje na temat nowych funkcji w ramach hybrydowego zarządzania urządzeniami przenośnymi, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   

## <a name="week-of-august-27-2018"></a>Tydzień od 27 sierpnia 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Obsługa tunelowania pakietów dla profilów sieci VPN aplikacji w systemie iOS dotycząca typów połączenia niestandardowego i Pulse Secure <!-- 1520957 -->
Korzystając z profilów sieci VPN dla aplikacji w systemie iOS, można używać tunelowania w warstwie aplikacji (app-proxy) lub w warstwie pakietów (packet-tunnel). Te opcje są dostępne dla następujących typów połączeń:
- Niestandardowa sieć VPN
- Pulse Secure Jeśli nie masz pewności, której wartości użyć, zapoznaj się z dokumentacją dostawcy sieci VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Opóźnienie przy wyświetlaniu aktualizacji oprogramowania systemu iOS na urządzeniu <!-- 1949583 -->
Pozycja Intune > **Aktualizacje oprogramowania** > **Zasady aktualizowania systemu iOS** umożliwia skonfigurowanie dni i godzin, podczas których urządzenia nie powinny instalować żadnych aktualizacji. W ramach przyszłej aktualizacji będzie można opóźnić widoczność aktualizacji oprogramowania na urządzeniu o okres od 1 do 90 dni. 
Obszar [Konfigurowanie zasad aktualizacji systemu iOS w usłudze Microsoft Intune](software-updates-ios.md) zawiera bieżące ustawienia.

#### <a name="office-365-proplus-version----2213968---"></a>Usługa Office 365 ProPlus w wersji <!-- 2213968 -->
Podczas przypisywania aplikacji usługi Office 365 ProPlus do urządzeń z systemem Windows 10 przy użyciu usługi Intune będzie można wybrać wersję pakietu Office. W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje** > **Dodaj aplikację**. Następnie wybierz pozycję **Pakiet Office 365 ProPlus (Windows 10)** z listy rozwijanej **Typ**. Wybierz pozycję **Ustawienia pakietu aplikacji**, aby wyświetlić skojarzony blok. Ustaw wartość pozycji **Aktualizuj kanał**, na przykład **Co miesiąc**. Opcjonalnie usuń inne wersje pakietu Office (pliki msi) z urządzeń użytkowników końcowych, wybierając pozycję **Tak**. Wybierz pozycję **Określona**, aby zainstalować określoną wersję pakietu Office dla wybranego kanału na urządzeniach użytkowników końcowych. Teraz możesz wybrać wartość **Określona wersja** dla pakietu Office. Dostępne wersje będą się zmieniać z upływem czasu. Dlatego podczas tworzenia nowego wdrożenia mogą być dostępne nowsze wersje, a pewne starsze wersje mogą być niedostępne. Bieżące wdrożenia będą nadal wdrażane przy użyciu starszej wersji, lecz lista dla kanału będzie stale aktualizowana. Aby uzyskać więcej informacji, zobacz [Overview of update channels for Office 365 ProPlus (Omówienie kanałów aktualizacji usługi Office 365 ProPlus)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Obsługa ustawienia rejestracji DNS dla sieci VPN systemu Windows 10 <!-- 2282852 -->
Dzięki tej aktualizacji będzie można skonfigurować profile sieci VPN systemu Windows 10 tak, aby dynamicznie rejestrowały adresy IP przypisane do interfejsu sieci VPN za pomocą wewnętrznej usługi DNS — bez konieczności korzystania z profilów niestandardowych.
Aby uzyskać informacje o bieżących dostępnych ustawieniach profilu sieci VPN, zobacz [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>Instalator aplikacji Portal firmy systemu macOS teraz zawiera numer wersji w nazwie pliku instalatora <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759-wnready---"></a>Automatyczne aktualizacje aplikacji systemu iOS <!-- 2729759 wnready -->
Automatyczne aktualizacje aplikacji działają zarówno w przypadku aplikacji licencjonowanych dla urządzenia, jak i użytkownika dla systemu iOS w wersji 11.0 i nowszej.




### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Funkcja Windows Hello będzie dotyczyć użytkowników i urządzeń <!-- 1106609 -->
Po utworzeniu zasad funkcji [Windows Hello dla firm](windows-hello.md) będą one stosowane do wszystkich użytkowników w organizacji (na poziomie dzierżawy). Dzięki tej aktualizacji zasady można także zastosować do konkretnych użytkowników lub urządzeń przy użyciu zasad konfiguracji urządzeń (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Identity Protection** > **Windows Hello dla firm**).
W witrynie Azure Portal usługi Intune konfiguracja i ustawienia funkcji Windows Hello są teraz dostępne w ramach pozycji **Rejestrowanie urządzenia** i **Konfiguracja urządzenia**. Pozycja **Rejestrowanie urządzenia** dotyczy całej organizacji (na poziomie dzierżawy) i obsługuje rozwiązanie Windows AutoPilot (OOBE). Pozycja **Konfiguracja urządzenia** dotyczy urządzeń i użytkowników objętych zasadami stosowanymi podczas ewidencjonowania.
Ta funkcja ma zastosowanie do:  
- System Windows 10 lub nowszy
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Połączenie Zscaler jest dostępne dla profilów sieci VPN w systemie iOS <!-- 1769858 eeready -->
Po utworzeniu profilu konfiguracji urządzenia sieci VPN w systemie iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** platforma > **Sieć VPN** typ profilu) będzie dostępnych kilka typów połączeń, w tym Cisco, Citrix i inne. Ta aktualizacja doda typ połączenia Zscaler. 
Pozycja [Ustawienia sieci VPN dla urządzeń z systemem iOS](vpn-settings-ios.md) zawiera dostępne typy połączeń.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077-eeready---"></a>Tryb FIPS dla profilów sieci Wi-Fi Enterprise w systemie Windows 10 <!-- 1879077 eeready -->
Możesz teraz włączyć tryb przetwarzania standardów FIPS dla profilów sieci Wi-Fi Enterprise w systemie Windows 10 w witrynie Azure Portal usługi Intune. Upewnij się, że jest włączony tryb FIPS dla Twojej infrastruktury sieci Wi-Fi, jeśli włączysz go w profilach sieci Wi-Fi.
[Ustawienia sieci Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Intune](wi-fi-settings-windows.md) pokażą, jak utworzyć profil sieci Wi-Fi.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Kontrolowanie trybu S na urządzeniach z systemem Windows 10 i nowszymi — publiczna wersja zapoznawcza <!-- 1958649 -->
Dzięki tej aktualizacji funkcji możesz utworzyć profil konfiguracji urządzenia, który wyłącza tryb S urządzenia z systemem Windows 10 lub uniemożliwia użytkownikom wyłączenie trybu S na urządzeniu. Ta funkcja znajduje się w pozycji Intune > **Konfiguracja urządzenia** > **Profile** >  **System Windows 10 i nowszy** > **Uaktualnienie wersji i przełączenie trybu**.
Artykuł [Wprowadzenie do systemu Windows 10 w trybie S](https://www.microsoft.com/windows/s-mode) zawiera więcej informacji na temat trybu S.
Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (w wersji zapoznawczej).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pakiet konfiguracji zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender jest automatycznie dodawany do profilu konfiguracji <!-- 2144658 -->
Przedtem w przypadku korzystania z [zaawansowanej ochrony przed zagrożeniami i dołączania](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) urządzeń w usłudze Intune konieczne było pobranie pakietu konfiguracyjnego i dodanie go do własnego profilu konfiguracji. Dzięki tej aktualizacji usługa Intune automatycznie pobierze pakiet z usługi Windows Defender Security Center i doda go do Twojego profilu.
Dotyczy systemu Windows 10 lub nowszych.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Wymaganie od użytkowników nawiązania połączenia podczas konfigurowania urządzenia <!--2311457-->
Możesz teraz ustawić profile urządzeń i wymagać, aby to urządzenie połączyło się z siecią przed przejściem poza stronę Sieć podczas konfigurowania systemu Windows 10. Chociaż ta funkcja jest obecnie w wersji zapoznawczej, niejawny program testów systemu Windows (kompilacja 1809 lub nowsza) jest wymagany, aby użyć tego ustawienia.
Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (w wersji zapoznawczej).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Ograniczanie aplikacji i blokowanie dostępu do zasobów firmy na urządzeniach z systemem iOS i Android Enterprise <!-- 2451462 -->
W pozycji **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **iOS** > **Zabezpieczenia systemu** jest nowe ustawienie **Aplikacje z ograniczeniami**. To nowe ustawienie używa zasad zgodności, aby zablokować dostęp do zasobów firmy, jeśli pewne aplikacje są zainstalowane na urządzeniu. Urządzenie jest uznawane za niezgodne, dopóki aplikacje z ograniczeniami nie zostaną usunięte z urządzenia.
Dotyczy: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Aktualizacje obsługi nowoczesnych sieci VPN dla systemu iOS <!-- 2459928, 1819876, and 2650856 -->
Ta aktualizacja dodaje obsługę następujących klientów sieci VPN dla systemu iOS: 
- F5 Access (w wersji 3.0.1 lub nowszej)
- Citrix SSO
- Palo Alto Networks GlobalProtect (w wersji 5.0 i nowszej) Także w tej aktualizacji:
- Nazwa istniejącego typu połączenia **F5 Access** jest zmieniana na **F5 Access Legacy** dla systemu iOS.
- Nazwa istniejącego typu połączenia **Palo Alto Networks GlobalProtect** jest zmieniana na **Palo Alto Networks GlobalProtect (starsza wersja)** dla systemu iOS.
Istniejące profile z tymi typami połączeń będą w dalszym ciągu działać z odpowiednim klientem sieci VPN w starszej wersji. Jeśli używasz programu Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN lub Palo Alto Networks GlobalProtect w wersji 4.1 lub wcześniejszej z systemem iOS, przejdź na nowe aplikacje. Należy to zrobić tak szybko, jak to możliwe, aby zapewnić dostęp do sieci VPN dla urządzeń z systemem iOS w miarę ich aktualizowania do systemu iOS 12.
Aby uzyskać więcej informacji na temat systemu iOS 12 i profilów sieci VPN, zobacz [blog zespołu pomocy technicznej usługi Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Eksportowanie zasad zgodności platformy klasycznego portalu platformy Azure, aby odtworzyć te zasady w witrynie Azure Portal usługi Intune <!-- 2469637 -->
Zasady zgodności utworzone w klasycznej witrynie Azure Portal będą przestarzałe. Możesz przejrzeć i usunąć wszelkie istniejące zasady zgodności, jednak nie możesz ich zaktualizować. Jeśli musisz migrować jakiekolwiek zasady zgodności do bieżącej witryny Azure Portal usługi Intune, możesz wyeksportować zasady w postaci pliku rozdzielanego przecinkami (pliku *CSV*). Następnie można użyć szczegółów w pliku, aby utworzyć ponownie zasady w witrynie Azure Portal usługi Intune.

> [!IMPORTANT]
> Po wycofaniu klasycznego portalu platformy Azure już nie będzie można uzyskać dostępu ani wyświetlić zasad zgodności. Dlatego należy się upewnić, że zasady zostały wyeksportowane, i odtworzyć je ponownie w witrynie Azure Portal przed wycofaniem klasycznego portalu platformy Azure.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile — nowy partner usługi Mobile Threat Defense <!-- 22662717 -->
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Better Mobile — rozwiązania usługi Mobile Threat Defense zintegrowanego z usługą Microsoft Intune.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Blokowanie aplikacji Portal firmy w trybie pojedynczej aplikacji do zalogowania użytkownika <!--1067692 --> 
Jest teraz dostępna możliwość uruchomienia aplikacji Portal firmy w trybie pojedynczej aplikacji, jeśli użytkownik zostanie uwierzytelniony za pomocą aplikacji Portal firmy zamiast za pomocą asystenta ustawień podczas rejestracji w programie DEP. Ta opcja umożliwia zablokowanie urządzenia natychmiast po zakończeniu pracy przez asystenta ustawień, dzięki czemu użytkownik musi zalogować się, aby uzyskać dostęp do urządzenia. Ten proces zapewnia, że dołączanie urządzenia zostanie zakończone i urządzenie nie pozostanie osierocone — bez powiązanego żadnego użytkownika.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Przypisywanie użytkownika i przyjaznej nazwy do urządzenia rozwiązania AutoPilot <!--1346521 -->
Możesz teraz [przypisać użytkownika do pojedynczego urządzenia rozwiązania Autopilot](enrollment-autopilot.md). Administratorzy będą także mogli nadać przyjazne nazwy witające użytkownika podczas konfigurowania urządzenia za pomocą rozwiązania Autopilot.
Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (w wersji zapoznawczej).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Korzystanie z licencji programu VPP do wstępnego aprowizowania aplikacji Portal firmy podczas rejestracji w programie DEP <!-- 1608345 -->
Można już używać licencji urządzeń zakupionych w ramach programu VPP (Volume Purchase Program) do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji w programie DEP (Device Enrollment Program). W tym celu podczas [tworzenia lub edytowania profilu rejestracji](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) należy określić token programu VPP, który zostanie użyty do zainstalowania aplikacji Portal firmy. Upewnij się, że token nie wygasł, i że masz wystarczającą liczbę licencji dla aplikacji Portal firmy. W przypadkach, gdy token wygaśnie lub zabraknie dla niego licencji, usługa Intune wypchnie aplikację Portal firmy ze sklepu App Store (spowoduje to wyświetlenie monitu o podanie identyfikatora Apple ID).

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Wymagane potwierdzenie w celu usunięcia tokenu programu VPP, który jest używany do wstępnej aprowizacji aplikacji Portal firmy <!-- 2237634 -->
Wymagane jest potwierdzenie w celu usunięcia tokenu programu Volume Purchase Program (VPP), jeśli jest on używany do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Blokowanie rejestracji osobistych urządzeń z systemem Windows <!-- 1849498 -->
Możesz [zablokować rejestrowanie urządzeń osobistych z systemem Windows](enrollment-restrictions-set.md#set-device-type-restrictions) za pomocą rozwiązania do [zarządzania urządzeniami mobilnymi](windows-enroll.md) w usłudze Intune. Za pomocą tej funkcji nie można zablokować urządzeń zarejestrowanych przy użyciu [agenta usługi Intune na komputerze](manage-windows-pcs-with-microsoft-intune.md). Ta funkcja będzie wprowadzana w ciągu kolejnych kilku tygodni, dlatego może nie być od razu widoczna w interfejsie użytkownika.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Określanie wzorców nazw maszyn w profilu rozwiązania AutoPilot <!--1849855-->
Możesz [określić szablon nazwy komputera](enrollment-autopilot.md#create-an-autopilot-deployment-profile), aby wygenerować i ustawić [nazwę komputera](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) podczas rejestrowania za pomocą rozwiązania AutoPilot. Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (w wersji zapoznawczej).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>W przypadku profilów rozwiązania Windows AutoPilot można ukryć opcje zmiany konta na stronach logowania firmy i błędu domeny <!--1901669 -->
Istnieją [nowe opcje profilu rozwiązania Windows Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile) przeznaczone dla administratorów i umożliwiające ukrycie opcji zmiany konta na stronach logowania firmy i błędu domeny. Ukrywanie tych opcji wymaga skonfigurowania znakowania firmowego w usłudze Azure Active Directory. Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (w wersji zapoznawczej).


#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Korzystanie z licencji programu VPP do wstępnego aprowizowania aplikacji Portal firmy podczas rejestracji w programie DEP <!-- 1608345 -->
Można już używać licencji urządzeń zakupionych w ramach programu VPP (Volume Purchase Program) do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji w programie DEP (Device Enrollment Program). W tym celu podczas [tworzenia lub edytowania profilu rejestracji](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) należy określić token programu VPP, który zostanie użyty do zainstalowania aplikacji Portal firmy. Upewnij się, że token nie wygasł, i że masz wystarczającą liczbę licencji dla aplikacji Portal firmy. W przypadkach, gdy token wygaśnie lub zabraknie dla niego licencji, usługa Intune wypchnie aplikację Portal firmy ze sklepu App Store (spowoduje to wyświetlenie monitu o podanie identyfikatora Apple ID).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="delete-jamf-devices----2653306--"></a>Usuwanie urządzeń Jamf <!-- 2653306-->
Możesz usuwać urządzenia zarządzane za pomocą oprogramowania JAMF, przechodząc do pozycji **Urządzenia** > wybierz urządzenie Jamf > **Usuń**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Zmiana terminologii na „wycofaj” i „wyczyść” <!-- 2175759 -->
Aby zachować spójność z interfejsem API programu Graph, w interfejsie użytkownika usługi Intune i w dokumentacji zmieniły się następujące terminy:
- **Usuń dane firmowe** zostanie zmieniony na „wycofaj”
- **Resetowanie do ustawień fabrycznych** zostanie zmieniony na **wyczyść**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Okno dialogowe potwierdzenia, jeśli administrator próbuje usunąć certyfikat wypychania MDM <!-- 297909500-->
Jeśli ktoś próbuje usunąć certyfikat wypychania MDM firmy Apple, w oknie dialogowym potwierdzenia jest wyświetlana liczba powiązanych urządzeń z systemem iOS i macOS. Jeśli certyfikat zostanie usunięty, te urządzenia będą wymagały ponownej rejestracji.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Dodatkowe ustawienia zabezpieczeń dla Instalatora Windows <!-- 2282430 -->
Można zezwolić użytkownikom na kontrolowanie instalacji aplikacji. Po włączeniu tej funkcji instalacje, które w przeciwnym razie mogły zostać zatrzymane z powodu naruszenia zabezpieczeń, będą kontynuowane. Można przekierować Instalatora Windows tak, aby używał podwyższonego poziomu uprawnień podczas instalowania dowolnego programu w systemie. Ponadto można włączyć indeksowanie elementów funkcji Windows Information Protection (WIP) oraz przechowywanie związanych z nimi metadanych w niezaszyfrowanej lokalizacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie są indeksowane i nie są wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Funkcje tych opcji są domyślnie wyłączone. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Aktualizacja nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968 -->
Na podstawie opinii klientów dodaliśmy nowe funkcje do witryny internetowej Portal firmy. Na swoich urządzeniach zobaczysz znaczące ulepszenia istniejących funkcji i poprawę użyteczności. Obszary witryny &ndash; takie jak szczegółowe informacje o urządzeniu, opinie i pomoc techniczna oraz przegląd urządzenia &ndash; zyskały nowy, nowoczesny i dynamiczny wygląd. Ponadto wprowadziliśmy następujące zmiany:

- Usprawnione przepływy pracy na wszystkich platformach urządzeń
- Ulepszone przepływy identyfikacji i rejestracji urządzeń
- Bardziej pomocne komunikaty o błędach
- Bardziej przyjazny język, mniej technicznego żargonu
- Możliwość udostępniania bezpośrednich linków do aplikacji
- Zwiększona wydajność dużych wykazów aplikacji
- Zwiększona dostępność dla wszystkich użytkowników  

[Dokumentacja witryny internetowej Portal firmy usługi Intune](https://docs.microsoft.com/en-us/intune-user-help/using-the-intune-company-portal-website) została zaktualizowana w celu odzwierciedlenia tych zmian. Aby wyświetlić przykład rozszerzeń aplikacji, zobacz [UI updates for Intune end-user apps (Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune)](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Rozszerzone wykrywanie zdjęcia zabezpieczeń systemu w raportowaniu zgodności<!-- 2198738 -->
Rozszerzone wykrywanie zdjęcia zabezpieczeń systemu dla ustawień stanów teraz pojawia się we wszystkich raportach zgodności w konsoli administracyjnej.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-policies---1081974-eeready--"></a>Tagi zakresu dla zasad <!--1081974 eeready-->
Możesz [tworzyć tagi zakresu](scope-tags.md) w celu ograniczenia dostępu do zasobów usługi Intune. Dodaj tag zakresu do przypisania roli, a następnie dodaj tag zakresu do profilu konfiguracji. Rola będzie miała wtedy dostęp tylko do zasobów z profilami konfiguracji ze zgodnymi tagami zakresu (lub bez tagów zakresu).

## <a name="week-of-august-14-2018"></a>Tydzień od 14 sierpnia 2018 r.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Obsługa systemu macOS w programie Device Enrollment Program firmy Apple <!-- 747651 -->
Usługa Intune obsługuje już rejestrowanie urządzeń z systemem macOS w programie Device Enrollment Program (DEP) firmy Apple. Aby uzyskać więcej informacji, zobacz [Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program firmy Apple](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>Tydzień od 23 lipca 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Obsługa aplikacji biznesowych dla systemu macOS <!-- 1895847 -->
Usługa Microsoft Intune umożliwia wdrażanie aplikacji biznesowych systemu macOS jako **wymaganych** lub **dostępnych z rejestracją**. Użytkownicy końcowi mogą wdrażać aplikacje jako **dostępne** przy użyciu aplikacji Portal firmy dla systemu macOS lub [witryny internetowej Portal firmy](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>wbudowana obsługa aplikacji systemu iOS na potrzeby trybu kiosku <!-- 2051098 -->
Oprócz aplikacji ze Sklepu i aplikacji zarządzanych można teraz wybrać aplikacje wbudowane (na przykład przeglądarkę Safari), które działają w trybie kiosku na urządzeniu z systemem iOS.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Edytowanie wdrożeń aplikacji usługi Office 365 Pro Plus <!-- 2150145 -->
Jako administrator usługi Microsoft Intune masz większe możliwości edycji wdrożeń aplikacji usługi Office 365 Pro Plus. Ponadto nie musisz już usuwać swoich wdrożeń, aby zmienić jakiekolwiek właściwości pakietu. W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje klienckie** > **Aplikacje**. Z listy aplikacji wybierz pakiet Office 365 Pro Plus.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Zaktualizowany zestaw Intune App SDK dla systemu Android jest teraz dostępny <!-- 2744271-->

Zaktualizowana wersja zestawu Intune App SDK dla systemu Android jest dostępna do obsługi wersji P systemu Android. Jeśli jesteś deweloperem aplikacji i używasz zestawu Intune SDK dla systemu Android, musisz zainstalować zaktualizowaną wersję zestawu Intune App SDK, aby zapewnić, że funkcje usługi Intune wykorzystywane w ramach Twoich aplikacji systemu Android będą nadal działać zgodnie z oczekiwaniami na urządzeniach z systemem Android P. Ta wersja zestawu Intune App SDK udostępnia wbudowany dodatek, który wykonuje aktualizacje zestawu SDK. Nie trzeba przepisywać istniejącego zintegrowanego kodu. Aby uzyskać szczegółowe informacje, zobacz temat [Zestaw Intune SDK dla systemu Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Jeśli używasz starego stylu ze wskaźnikami do usługi Intune, firma Microsoft zaleca użycie ikony Aktówka. Szczegóły dotyczące znakowania można znaleźć w [tym repozytorium GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Używanie szyfrowania S/MIME do szyfrowania i rejestrowania wielu urządzeń użytkownika <!-- 1333642 -->
Ta aktualizacja obejmuje szyfrowanie poczty e-mail za pomocą protokołu S/MIME z użyciem profilu nowo zaimportowanego certyfikatu (**Konfiguracja urządzenia** > **Profil** > **Utwórz profil** > wybierz platformę > typ profilu **Zaimportowany certyfikat PKCS**). W usłudze Intune można importować certyfikaty w formacie PFX. Usługa Intune może następnie dostarczać te same certyfikaty do wielu urządzeń zarejestrowanych przez jednego użytkownika. Obejmuje to również:

- Profil natywnej poczty e-mail systemu iOS obsługuje włączanie szyfrowania S/MIME przy użyciu importowanych certyfikatów w formacie PFX.
- Natywna aplikacja poczty na urządzeniach z systemem Windows Phone 10 automatycznie używa certyfikatu szyfrowania S/MIME.
- Certyfikaty prywatne mogą być dostarczane na wielu platformach. Jednak nie wszystkie aplikacje poczty e-mail obsługują szyfrowanie S/MIME.
- Na innych platformach może być konieczne ręczne skonfigurowanie aplikacji poczty, aby włączyć szyfrowanie S/MIME.  
- Aplikacje poczty e-mail, które obsługuje szyfrowanie S/MIME może obsługiwać pobieranie certyfikatów dla protokołu S/MIME szyfrowania wiadomości e-mail w sposób, który nie obsługuje zarządzania urządzeniami Przenośnymi, takie jak odczytywanie ich z magazynu certyfikatów ich wydawcy.

Obsługiwane w systemach: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Tworzenie zasad zgodności urządzeń za pomocą ustawień zapory na urządzeniach z systemem macOS <!-- 1497640 -->
Podczas tworzenia nowych zasad systemu macOS (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad**  >  **Platforma: macOS** > **Zabezpieczenia systemu**) dostępne są nowe ustawienia **Zapory**: 

- **Zapora**: skonfiguruj obsługę połączeń przychodzących w danym środowisku.
- **Połączenia przychodzące**: **blokuj** wszystkie połączenia przychodzące poza wymaganymi dla podstawowych usług internetowych, np. DHCP, Bonjour i IPSec. To ustawienie blokuje również wszystkie usługi udostępniania.
- **Tryb niewidzialności**: **włącz** tryb niewidzialności, aby zapobiegać odpowiadaniu przez komputer na żądania sondowania. Urządzenie nadal odpowiada na przychodzące żądania w przypadku autoryzowanych aplikacji.

Dotyczy: macOS 10.12 i nowsze

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nowy profil konfiguracji urządzenia sieci Wi-Fi dla systemu Windows 10 i nowszych <!-- 1879077 -->
Obecnie profile sieci Wi-Fi można importować i eksportować przy użyciu plików XML. Ta aktualizacja umożliwia utworzenie profilu konfiguracji urządzenia sieci Wi-Fi bezpośrednio w usłudze Intune, podobnie jak w przypadku niektórych innych platform.

Aby utworzyć profil, przejdź kolejno do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** > **Wi-Fi**. 

Dotyczy systemu Windows 10 lub nowszych.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998-eeready---"></a>Opcja Kiosk — przestarzałe jest wyszarzona i nie można jej zmienić <!-- 2149998 eeready -->
[Funkcja kiosku](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Konfiguracja urządzenia** > **Profil** > **Utwórz profil** > **System Windows 10 lub nowszy** > **Ograniczenia dotyczące urządzeń**) jest przestarzała i została zastąpiona [ustawieniami kiosku dla systemu Windows 10 i nowszych](kiosk-settings.md). W ramach tej aktualizacji funkcja **Kiosk — przestarzałe** została wyszarzona i nie można będzie zmienić ani zaktualizować interfejsu użytkownika. 

Aby włączyć tryb kiosku, zobacz [ustawienia kiosku dla systemu Windows 10 i nowszych](kiosk-settings.md).

Dotyczy systemu Windows 10 lub nowszych oraz systemu Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Interfejsy API umożliwiające korzystanie z urzędów certyfikacji innych firm<!-- 2184013 -->
W ramach tej aktualizacji dostępny jest interfejs API języka Java umożliwiający integrację urzędów certyfikacji innych firm z usługą Intune i protokołem SCEP. Następnie użytkownicy będą mogli dodać certyfikat protokołu SCEP do profilu i zastosować go do urządzeń za pomocą rozwiązania MDM.

Obecnie usługa Intune obsługuje [żądania protokołu SCEP za pomocą usług certyfikatów Active Directory](certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Przełączanie w celu wyświetlania lub niewyświetlania przycisku Zakończ sesję w przeglądarce kiosku <!-- 2455253 -->
Możliwe jest teraz skonfigurowanie, czy przycisk Zakończ sesję ma być wyświetlany w przeglądarce kiosku. Możesz zobaczyć kontrolkę, wybierając pozycje **Konfiguracja urządzenia** > **Kiosk (wersja zapoznawcza)** > **Przeglądarka internetowa kiosku**. Jeśli jest włączona, kiedy użytkownik kliknie przycisk, aplikacja wyświetli monit o potwierdzenie zakończenia sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania i powraca do domyślnego adresu URL.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Tworzenie profilu konfiguracji sieci komórkowej karty eSIM <!-- 2564077 -->
W **konfiguracji urządzenia** można utworzyć profil sieci komórkowej karty eSIM. Można zaimportować plik, który zawiera kody aktywacji sieci komórkowej dostarczone przez operatora sieci komórkowej. Następnie można wdrożyć te profile na urządzeniach z systemem Windows 10 z włączoną obsługą sieci LTE karty eSIM, takich jak urządzenia Surface Pro LTE i inne urządzenia obsługujące karty eSIM.

Sprawdź, czy Twoje [urządzenia obsługują profile karty eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Dotyczy systemu Windows 10 lub nowszych. 




### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Automatyczne oznaczanie urządzeń z systemem Android zarejestrowanych za pomocą programu Samsung Knox Mobile Enrollment jako „firmowe”. <!-- 2404851 -->
Domyślnie urządzenia z systemem Android zarejestrowane za pomocą programu Samsung Knox Mobile Enrollment są teraz oznaczone jako **firmowe** w obszarze **Własność urządzenia**. Nie musisz ręcznie identyfikować urządzeń firmowych przy użyciu numerów IMEI lub numerów seryjnych przed zarejestrowaniem ich za pomocą programu Knox Mobile Enrollment.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Zbiorcze usuwanie urządzeń w bloku urządzeń <!-- 1793693 -->

Możliwe jest teraz usunięcie wielu urządzeń naraz w bloku Urządzenia. Wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenia do usunięcia > **Usuń**. W przypadku urządzeń, których nie można usunąć, zostanie wyświetlony alert.

## <a name="week-of-july-16-2018"></a>Tydzień od 16 lipca 2018 r.  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Więcej możliwości synchronizacji w aplikacji Portal firmy dla systemu Windows  
Aplikacja Portal firmy dla systemu Windows umożliwia teraz zainicjowanie synchronizacji bezpośrednio z poziomu paska zadań i menu Start systemu Windows. Ta funkcja jest szczególnie przydatna, jeśli Twoim jedynym zadaniem jest synchronizowanie urządzeń i uzyskiwanie dostępu do zasobów firmy. Aby skorzystać z nowych funkcji, kliknij prawym przyciskiem myszy ikonę aplikacji Portal firmy przypiętą do paska zadań lub menu Start. W opcjach menu (nazywanych również listą szybkiego dostępu) wybierz pozycję **Synchronizuj to urządzenie**. Spowoduje to otwarcie aplikacji Portal firmy na stronie **Ustawienia** i zainicjowanie synchronizacji. Aby dowiedzieć się więcej o nowej funkcji, zobacz [Co nowego w interfejsie użytkownika](whats-new-app-ui.md).   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nowe środowisko przeglądania w aplikacji Portal firmy dla systemu Windows  

Teraz podczas przeglądania w poszukiwaniu aplikacji lub ich wyszukiwania w aplikacji Portal firmy dla systemu Windows możliwe jest przełączanie się między istniejącym widokiem **Kafelki** a nowo dodanym widokiem **Szczegóły**. W nowym widoku wyświetlane są szczegółowe informacje dotyczące aplikacji, takie jak nazwa, wydawca, data publikacji i stan instalacji.  

Na stronie **Aplikacje** w widoku **Zainstalowane** dostępne są szczegóły dotyczące zakończonych i trwających instalacji aplikacji. Aby dowiedzieć się, jak wygląda nowy widok, zobacz [Co nowego w interfejsie użytkownika](whats-new-app-ui.md).  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Ulepszone środowisko aplikacji Portal firmy dla menedżerów rejestracji urządzeń  
Gdy menedżer rejestracji urządzeń loguje się do aplikacji Portal firmy dla systemu Windows, w aplikacji będzie teraz wyświetlane tylko bieżące, uruchomione urządzenie menedżera rejestracji urządzeń. To ulepszenie ograniczy występowanie przekroczeń limitu czasu, które wcześniej miały miejsce, gdy aplikacja podejmowała próbę wyświetlenia wszystkich urządzeń zarejestrowanych w menedżerze rejestracji urządzeń.  


## <a name="week-of-july-9-2018"></a>Tydzień od 9 lipca 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokowanie dostępu do aplikacji dla niezatwierdzonych dostawców i modeli urządzeń <!-- 1425689 ! -->
Administrator IT usługi Intune może wymuszać określoną listę producentów urządzeń z systemem Android i/lub modeli urządzeń z systemem iOS za pomocą zasad ochrony aplikacji w usłudze Intune. Administrator IT może przedstawić rozdzielaną średnikami listę producentów zgodnych z zasadami systemu Android oraz modeli urządzeń zgodnych z zasadami systemu iOS. Zasady ochrony aplikacji w usłudze Intune są przeznaczone tylko dla systemów Android i iOS. Dla podanej listy można wykonać dwie oddzielne akcje:
- Blokowanie dostępu do aplikacji na urządzeniach, które nie zostały określone.
- Lub selektywne czyszczenie danych firmowych na urządzeniach, które nie zostały określone. 

Użytkownik nie będzie mógł uzyskiwać dostępu do aplikacji docelowej, jeśli wymagania zasad nie zostaną spełnione. Na podstawie ustawień użytkownik może zostać zablokowany albo jego dane firmowe mogą zostać selektywnie wyczyszczone z aplikacji. Na urządzeniach z systemem iOS ta funkcja wymaga udziału aplikacji (takich jak WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu Intune APP SDK, aby ta funkcja była wymuszana na docelowych aplikacjach. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy. 

Na urządzeniach użytkowników końcowych klient usługi Intune wykona akcję w oparciu o proste dopasowywanie ciągów określonych w bloku usługi Intune dla zasad ochrony aplikacji. Zależy to całkowicie od wartości zgłaszanej przez urządzenie. W takiej sytuacji administrator IT jest zachęcany do zapewniania, że założone zachowanie jest prawidłowe. Ten cel można osiągnąć, testując to ustawienie w oparciu o różnych producentów i modele urządzeń przeznaczone dla małej grupy użytkowników. W usłudze Microsoft Intune wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji**, aby wyświetlić i dodać zasady ochrony aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji](app-protection-policy.md) i [Selektywne czyszczenie danych przy użyciu akcji dostępu zasad ochrony aplikacji w usłudze Intune](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Dostęp do kompilacji wersji wstępnej Portalu firmy dla systemu macOS <!-- 1734766 -->
Za pomocą programu Microsoft AutoUpdate możesz zarejestrować się w celu wcześniejszego otrzymywania kompilacji przez dołączenie do niejawnego programu testów. Rejestracja umożliwi korzystanie ze zaktualizowanego Portalu firmy, zanim będzie on dostępny dla Twoich użytkowników końcowych. Aby uzyskać więcej informacji, zobacz [Blog usługi Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## <a name="week-of-july-2-2018"></a>Tydzień od 2 lipca 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Monitorowanie stanu konfiguracji aplikacji systemu iOS na poszczególnych urządzeniach <!-- 880037 -->
Jako administrator usługi Microsoft Intune możesz monitorować stan konfiguracji aplikacji systemu iOS dla każdego zarządzanego urządzenia. W usłudze **Microsoft Intune** w witrynie Azure Portal wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**. Z listy zarządzanych urządzeń wybierz konkretne urządzenie, aby wyświetlić blok dla tego urządzenia. W bloku urządzenia wybierz pozycję **Konfiguracja aplikacji**.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Akcje dotyczące uzyskiwania dostępu dla zasad ochrony aplikacji <!-- 1483510 -->
Można konfigurować zasady ochrony aplikacji w celu jawnego czyszczenia lub blokowania niezgodnych urządzeń albo ostrzegania o nich. Akcja *czyszczenia* powoduje usunięcie danych firmowych z urządzenia. W przypadku czyszczenia użytkownik urządzenia jest powiadamiany o przyczynie uruchomienia tego procesu oraz czynnościach korygujących. W przypadku niektórych ustawień, takich jak minimalna wersja systemu operacyjnego, można zastosować wiele akcji, takich jak blokowanie i czyszczenie. Należy zwrócić uwagę, że te akcje są wyzwalane po uruchomieniu aplikacji.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Selektywne czyszczenie danych organizacji z aplikacji <!-- 1507030 -->
Administratorzy mogą teraz konfigurować selektywne czyszczenie danych organizacji jako nową akcję, gdy nie są spełnione warunki ustawień dostępu zasad ochrony aplikacji.  Ta funkcja pomaga administratorom automatycznie chronić i usuwać poufne dane organizacji z aplikacji na podstawie wstępnie skonfigurowanych kryteriów.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Odwoływanie licencji aplikacji systemu iOS zakupionych w ramach programu VPP <!-- 1777384 -->
Jako administrator usługi Microsoft Intune możesz odwołać wszystkie licencje dla wybranej aplikacji systemu iOS zakupionej w ramach programu zakupów zbiorczych (programu VPP). Możesz powiadomić użytkowników, że aplikacja licencjonowana dla użytkownika nie jest już do nich przypisana. Odwołanie licencji aplikacji nie spowoduje odinstalowania powiązanych aplikacji VPP z urządzenia. Aby odinstalować aplikację VPP, należy zmienić akcję przypisywania na **Odinstaluj**. Liczba odzyskanych licencji zostanie odzwierciedlona w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje** usługi Intune. Aby uzyskać więcej informacji dotyczących aplikacji usługi VPP dla systemu iOS, zobacz temat [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-apps-ios.md).

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Aktualizacje komunikatów o niezgodności w aplikacji Portal firmy <!-- 1832222 -->
Zweryfikowaliśmy komunikaty, które użytkownicy urządzenia widzą, gdy urządzenie jest niezgodne. Komunikaty zachowują swoje oryginalne znaczenia, ale zostały napisane bardziej przyjaznym językiem i z mniejszą zawartością żargonu technicznego. Odświeżyliśmy również linki do dokumentacji i kroki rozwiązywania problemów w celu zapewnienia ich aktualności.
Następujący tekst „przed” i „po” jest przykładem ulepszenia komunikatów, które zobaczysz:
- **Przed**: *to urządzenie nie łączyło się z usługą Intune w określonym czasie wymaganym przez administratora IT. Aby rozwiązać ten problem, otwórz aplikację Portal firmy na swoim urządzeniu i kliknij przycisk Sprawdź zgodność.*
- **Po**: *urządzenie przez pewien czas nie było zaewidencjonowane w Twojej organizacji. Aby ponownie nawiązać połączenie, otwórz aplikację Portal firmy na swoim urządzeniu, a następnie naciśnij pozycję Sprawdź ustawienia dla urządzenia.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>Odwoływanie licencji aplikacji zakupionych w ramach programu VPP dla systemu iOS <!-- 1863797 -->
Jako administrator masz możliwość odzyskania licencji aplikacji programu VPP dla systemu iOS przypisanych do użytkownika lub urządzenia. Odinstalowanie aplikacji VPP dla systemu iOS pozwoli również na odzyskanie licencji aplikacji. Przed odinstalowaniem aplikacji należy usunąć użytkownika lub urządzenie z grupy, dla której jest przeznaczona aplikacja. Usunięcie użytkownika lub urządzenia z grupy pozwala uniknąć konieczności ponownej instalacji aplikacji. Po wykonaniu tych kroków można przypisać licencję aplikacji do innego użytkownika lub urządzenia. Aby uzyskać więcej informacji o licencjach aplikacji dla systemu iOS zakupionymi w ramach programu VPP, zobacz [Zarządzanie aplikacjami dla systemu iOS nabytymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](vpp-apps-ios.md).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Wybieranie kategorii urządzeń przy użyciu ustawień opcji Uzyskaj dostęp do miejsca pracy lub nauki <!-- 1058963 eenotready --> 
Jeśli włączono [mapowanie grup urządzeń](https://docs.microsoft.com/en-us/intune/device-group-mapping), w systemie Windows 10 po dokonaniu rejestracji przy użyciu przycisku **Połącz** w obszarze **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** zostanie teraz wyświetlony monit o wybranie kategorii urządzenia. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Używanie atrybutu SAMAccountName jako nazwy użytkownika konta dla profilów poczty e-mail <!-- 1500307 -->
Możesz używać lokalnego atrybutu **sAMAccountName** jako nazwy użytkownika konta w profilach poczty e-mail dla systemu Android, iOS i Windows 10. Możesz również pobrać domenę z atrybutu `domain` lub `ntdomain` w usłudze Azure Active Directory (Azure AD). Ewentualnie można wprowadzić niestandardową domenę statyczną.

Aby korzystać z tej funkcji, należy zsynchronizować atrybut `sAMAccountName` z lokalnego środowiska usługi Active Directory z usługą Azure AD.

Dotyczy: [Andoid](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 i nowsze](email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Wyświetlanie profilów konfiguracji urządzeń będących w konflikcie <!-- 1556983 -->
W sekcji **Konfiguracji urządzenia** jest wyświetlana lista istniejących profilów. Dzięki tej aktualizacji zostanie dodana nowa kolumna ze szczegółowymi informacjami o profilach, które są w konflikcie. Możesz wybrać wiersz z konfliktem, aby wyświetlić ustawienia i profil powodujące konflikt. 

Więcej na temat [zarządzania profilami konfiguracji](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Nowy stan dla urządzeń w obszarze zgodności urządzenia <!-- 2308882 -->
W obszarze **Zgodność urządzenia** > **Zasady** > wybierz zasady > **Przegląd** dodano następujące nowe stany:
- Sukces
- Błąd
- Konflikt
- Oczekiwanie
- Nie dotyczy. Wyświetlany jest również obraz, który informuje o liczbie urządzeń innych platform. Na przykład jeśli przeglądasz profil systemu iOS, nowy kafelek pokazuje liczbę urządzeń z systemem innym niż iOS, które także są przypisane do tego profilu. Zobacz [Zasady zgodności urządzeń](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Zasady zgodności urządzeń obsługują rozwiązania antywirusowe innych firm <!-- 2325484 -->
Podczas tworzenia nowych zasad zgodności urządzeń (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **Platforma: Windows 10 lub nowszy** > **Ustawienia** > **Zabezpieczenia systemu**) są dostępne nowe opcje **[zabezpieczeń urządzeń](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)**: 
- **Oprogramowanie antywirusowe**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antywirusowych zarejestrowanych w Centrum zabezpieczeń systemu Windows, na przykład rozwiązań firmy Symantec i usługi Windows Defender. 
- **Program antyszpiegowski**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antyszpiegowskich zarejestrowanych w Centrum zabezpieczeń systemu Windows, na przykład rozwiązań firmy Symantec i usługi Windows Defender. 

Dotyczy: system Windows 10 lub nowszy 

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Urządzenia bez kolumny profilów na liście tokenów programu rejestracji <!-- 1853904 -->
Lista tokenów programu rejestracji zawiera nową kolumnę, w której jest wyświetlana liczba urządzeń bez przypisanego profilu. Ułatwia ona administratorom przypisywanie profilów do tych urządzeń przed przekazaniem ich użytkownikom. Aby wyświetlić nową kolumnę, przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji**.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Zmiany nazw Google dla programu Android for Work i sklepu Play for Work <!--842873 -->
Usługa Intune zaktualizowała terminologię programu „Android for Work”, aby odzwierciedlić zmiany znakowania Google. Terminy „Android for Work” i „Play for Work” nie są już używane. Inna terminologia jest używana w zależności od kontekstu:
- „Android do pracy” odnosi się do ogólnego nowoczesnego stosu zarządzania systemu Android.
- „Profil służbowy” lub „Właściciel profilu” odnosi się do urządzeń BYOD zarządzanych za pomocą profilów służbowych.
- „Zarządzany sklep Google Play” odnosi się do sklepu z aplikacjami firmy Google.

#### <a name="rules-for-removing-devices----1609459---"></a>Reguły usuwania urządzeń <!-- 1609459 -->
Są dostępne nowe reguły umożliwiające automatyczne usuwanie urządzeń, które nie zostały zaewidencjonowane przez ustawioną liczbę dni. Aby wyświetlić nową regułę, przejdź do okienka **Intune**, wybierz pozycję **Urządzenia**, a następnie pozycję **Reguły czyszczenia urządzeń**.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Obsługa modelu firmowych urządzeń mających określone zastosowanie dla urządzeń z systemem Android <!-- 1630973 -->

Usługa Intune obsługuje teraz wysoce zarządzane, blokowane urządzenia z systemem Android działające w trybie kiosku. Umożliwia to administratorom dalsze blokowanie użycia urządzenia do jednej aplikacji lub małego zestawu aplikacji i uniemożliwia użytkownikom włączanie innych aplikacji lub wykonywanie innych działań na urządzeniu. Aby skonfigurować kiosk systemu Android, przejdź do usługi Intune > **Rejestracja urządzeń** > **Rejestracja urządzenia z systemem Android** > **Rejestracja urządzenia kiosku i zadań**. Aby uzyskać więcej informacji, zobacz [Konfigurowanie rejestracji urządzeń kiosku z rozwiązaniem Android enterprise](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Przegląd przekazanych zduplikowanych identyfikatorów urządzeń firmowych na poziomie wiersza <!-- 2203794-->
Podczas przekazywania identyfikatorów urządzeń firmowych usługa Intune udostępnia teraz listę duplikatów i zapewnia możliwość zastąpienia lub zachowania istniejących informacji. Raport będzie wyświetlany, jeśli po wybraniu pozycji **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych** > **Dodaj identyfikatory** istnieją duplikaty. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ręczne dodawanie identyfikatorów urządzeń firmowych <!-- 2203803 -->
Teraz można ręcznie dodawać identyfikatory urządzeń firmowych. Wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych** > **Dodaj**. 

## <a name="week-of-june-25-2018"></a>Tydzień od 25 czerwca 2018 r.

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo — nowy partner usługi Mobile Threat Defense <!-- 1169249 -->

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Pradeo — rozwiązania usługi Mobile Threat Defense zintegrowanego z usługą Microsoft Intune.

## <a name="week-of-june-18-2018"></a>Tydzień od 18 czerwca 2018 r.

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Obsługa zasad ochrony aplikacji usługi Intune w przeglądarce Edge dla urządzeń przenośnych <!-- 1817882 -->

Przeglądarka Microsoft Edge dla urządzeń przenośnych obsługuje teraz zasady ochrony aplikacji zdefiniowane w usłudze Intune.

## <a name="week-of-june-11-2018"></a>Tydzień od 11 czerwca 2018 r.

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Używanie trybu FIPS z łącznikiem certyfikatu usługi NDES <!-- 1333688 -->
Po zainstalowaniu łącznika certyfikatów usługi NDES na komputerze z włączonym trybem Federal Information Processing Standard (FIPS) wystawianie i odwoływanie certyfikatów nie działało zgodnie z oczekiwaniami. Dzięki tej aktualizacji łącznik certyfikatów usługi NDES obsługuje standard FIPS. 

Ta aktualizacja obejmuje również:

- Łącznik certyfikatów usługi NDES wymaga programu .NET 4.5 Framework, który jest automatycznie dołączany do systemów Windows Server 2016 i Windows Server 2012 R2. Wcześniej program .NET 3.5 Framework był minimalną wymaganą wersją.
- Obsługa protokołu TLS 1.2 jest dołączona do łącznika certyfikatów usługi NDES. Jeśli więc serwer z zainstalowanym łącznikiem certyfikatów usługi NDES obsługuje protokół TLS 1.2, jest używany protokół TLS 1.2. Jeśli serwer nie obsługuje protokołu TLS 1.2, jest używany protokół TLS 1.1. Obecnie protokół TLS 1.1 jest używany do uwierzytelniania między urządzeniami a serwerem.

Aby uzyskać więcej informacji, zobacz [Configure and use SCEP certificates (Konfigurowanie i używanie certyfikatów SCEP)](certificates-scep-configure.md) i [Configure and use PKCS certificates (Konfigurowanie i używanie certyfikatów PKCS)](certficates-pfx-configure.md).

## <a name="week-of-june-4-2018"></a>Tydzień od 4 czerwca 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Pobieranie skojarzonego identyfikatora modelu użytkownika aplikacji (AUMID) dla aplikacji ze sklepu Microsoft Store dla Firm w trybie kiosku <!-- 1560077 ! -->
Usługa Intune może teraz pobierać identyfikatory modelu użytkownika aplikacji (AUMID) dla aplikacji ze sklepu Microsoft Store dla Firm (WSfB) w celu udostępniania ulepszonej konfiguracji profilu kiosku.

Aby uzyskać więcej informacji na temat aplikacji ze sklepu Microsoft Store dla Firm, zobacz [Manage apps from Microsoft Store for Business](windows-store-for-business.md) (Zarządzanie aplikacjami ze sklepu Microsoft Store dla Firm).

#### <a name="new-company-portal-branding-page----1916370---"></a>Nowa strona znakowania Portalu firmy <!-- 1916370 -->
Strona znakowania Portalu firmy ma nowy układ, komunikaty i etykietki narzędzi.


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Obsługa profilów sieci VPN Palo Alto Networks GlobalProtect <!-- 1333680 eeready ! -->
Dzięki tej aktualizacji możesz wybrać sieć Palo Alto Networks GlobalProtect jako typ połączenia sieci VPN dla profilów sieci VPN w usłudze Intune (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Typ profilu** > **Sieć VPN**). W tej wersji obsługiwane są następujące platformy: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Dodatki dla ustawień opcji zabezpieczeń urządzenia lokalnego <!-- 1403702 -->
Obecnie możesz skonfigurować dodatkowe ustawienia opcji zabezpieczeń urządzenia lokalnego dla urządzeń z systemem Windows 10. Dodatkowe ustawienia są dostępne w następujących obszarach: klient sieci Microsoft, serwer sieci Microsoft, dostęp do sieci i zabezpieczenia oraz logowanie interakcyjne. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Włączanie trybu kiosku na urządzeniach z systemem Windows 10 <!-- 1560072 ! -->
Na urządzeniach z systemem Windows 10 można utworzyć profil konfiguracji i włączyć tryb kiosku (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10** > **Ograniczenia urządzenia** > **Kiosk**). W ramach tej aktualizacji nazwa ustawienia **Kiosk (wersja zapoznawcza)** została zmieniona na **Kiosk (przestarzałe)**. Używanie ustawienia **Kiosk (przestarzałe)** nie jest już zalecane, ale będzie ono działać do momentu wydania aktualizacji w lipcu. Ustawienie **Kiosk (przestarzałe)** zostało zastąpione przez nowy typ profilu **Kiosk** (**Utwórz profil** > **Windows 10** > **Kiosk (wersja zapoznawcza)**), który będzie zawierać ustawienia służące do konfigurowania kiosków w systemie Windows 10 RS4 lub nowszym.

Dotyczy systemu Windows 10 lub nowszych.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Graficzny wykres użytkowników profilu urządzeń jest ponownie dostępny <!-- 2160133 -->
W trakcie ulepszania sposobu wyświetlania liczb na graficznym wykresie profilu urządzenia (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Omówienie**) tymczasowo usunięto graficzny wykres użytkowników.

W ramach tej aktualizacji graficzny wykres użytkowników został ponownie udostępniony i jest wyświetlany w witrynie Azure Portal.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118-wnready---"></a>Obsługa rejestracji rozwiązania Windows Autopilot bez uwierzytelniania użytkownika <!-- 1165118 wnready -->
Usługa Intune obsługuje teraz rejestrację przy użyciu rozwiązania Windows Autopilot bez uwierzytelniania użytkownika. Jest to nowa opcja w profilu wdrażania programu Windows Autopilot „Tryb wdrażania rozwiązania Autopilot” ustawiona na wartość „Samodzielne wdrażanie”.  Aby pomyślnie ukończyć tego rodzaju rejestrację, na urządzeniu musi być uruchomiona kompilacja 17672 niejawnego programu testów systemu Windows 10 w wersji zapoznawczej lub nowsza i urządzenie musi być wyposażone w układ scalony TPM 2.0. Ponieważ żadne uwierzytelnianie użytkownika nie jest wymagane, tę opcję należy przypisywać tylko do urządzeń, nad którymi masz fizyczną kontrolę.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766-eeready---"></a>Nowe ustawienie języka/regionu podczas konfigurowania OOBE dla rozwiązania Autopilot <!-- 1821766 eeready -->
Dostępne jest nowe ustawienie konfiguracji umożliwiające ustawianie języka i regionu dla profilów rozwiązania Autopilot podczas uruchamiania typu Out of Box Experience. Aby wyświetlić nowe ustawienie, wybierz pozycję **Rejestrowanie urządzeń** > **Rejestracja urządzeń z systemem Windows** > **Profile wdrażania** > **Utwórz profil** > **Tryb wdrażania** = **Samodzielne wdrażanie** > **Skonfigurowane ustawienia domyślne**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nowe ustawienie służące do konfigurowania klawiatury urządzenia <!-- 1821768 -->
Zostanie udostępnione nowe ustawienie umożliwiające konfigurowanie klawiatury dla profilów rozwiązania Autopilot podczas uruchamiania typu Out of Box Experience. Aby wyświetlić nowe ustawienie, wybierz pozycję **Rejestrowanie urządzeń** > **Rejestracja urządzeń z systemem Windows** > **Profile wdrażania** > **Utwórz profil** > **Tryb wdrażania** = **Samodzielne wdrażanie** > **Skonfigurowane ustawienia domyślne**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Profile rozwiązania AutoPilot będą stosowane dla grup <!-- 1877935 -->
Profile wdrażania rozwiązania AutoPilot można przypisywać do grup usługi Azure AD zawierających urządzenia rozwiązania AutoPilot.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="set-compliance-by-device-location----851881----"></a>Ustawianie zgodności według lokalizacji urządzenia <!-- 851881 ! -->
W niektórych sytuacjach możesz ograniczyć dostęp do zasobów firmy do określonej lokalizacji zdefiniowanej przez połączenie sieciowe. Możesz teraz tworzyć zasady zgodności (**Zgodność urządzenia** > **Lokalizacje**) na podstawie adresu IP urządzenia. Jeśli urządzenie zostanie przeniesione poza zakres adresów IP, nie będzie miało dostępu do zasobów firmy.

Dotyczy: urządzeń z systemem Android 6.0 lub nowszym ze zaktualizowaną aplikacją Portal firmy

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokowanie aplikacji i środowisk konsumenckich na urządzeniach z rozwiązaniem AutoPilot w systemie Windows 10 Enterprise RS4<!-- 1621980 -->
Będzie można zablokować instalację aplikacji i środowisk konsumenckich na urządzeniach z systemem Windows 10 Enterprise RS4 i rozwiązaniem AutoPilot. Aby wyświetlić tę funkcję, przejdź do pozycji **Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Platforma** = **System Windows 10 lub nowszy** > **Typ profilu** = **Ograniczenia dotyczące urządzeń** > **Konfigurowanie** > **W centrum uwagi Windows** > **Funkcje dla konsumentów**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948-eeready---"></a>Odinstalowywanie najnowszych aktualizacji oprogramowania systemu Windows 10 <!-- 1732948 eeready -->
Jeśli wykryjesz problem powodujący awarię na maszynach z systemem Windows 10, możesz odinstalować (wycofać) najnowszą aktualizację funkcji lub najnowszą aktualizację jakości. Odinstalowywanie aktualizacji funkcji lub jakości jest dostępne tylko dla kanału obsługi dostępnego na urządzeniu. Odinstalowywanie wyzwoli zasady w celu przywrócenia poprzedniej aktualizacji na maszynach z systemem Windows 10. W przypadku aktualizacji funkcji można ograniczyć czas (od 2 do 60 dni), w którym można odinstalować najnowszą wersję. Aby ustawić opcje odinstalowywania aktualizacji oprogramowania, wybierz pozycję **Aktualizacje oprogramowania** w bloku **Microsoft Intune** w witrynie Azure Portal. Następnie wybierz pozycję **Pierścienie aktualizacji systemu Windows 10** w bloku **Aktualizacje oprogramowania**. Następnie możesz wybrać opcję **Odinstaluj** w sekcji **Przegląd**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Wyszukiwanie wszystkich urządzeń na podstawie numeru IMEI i numeru seryjnego <!-- 1793685 -->
Możesz teraz wyszukiwać numery IMEI i numery seryjne w bloku Wszystkie urządzenia (adres e-mail, nazwa UPN, nazwa urządzenia i nazwa zarządzania są nadal dostępne). W usłudze Intune wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wprowadź kryteria wyszukiwania w polu wyszukiwania.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Będzie można edytować pole Nazwa zarządzania <!-- 1875989 -->
Możesz teraz edytować pole Nazwa zarządzania w bloku **Właściwości** urządzenia. Aby edytować to pole, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości**. Pola nazwy zarządzania można używać do unikatowego identyfikowania urządzenia.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Nowy filtr listy Wszystkie urządzenia: Kategoria urządzeń <!-- 1878520 -->
Obecnie można filtrować listę **Wszystkie urządzenia** według kategorii urządzeń. Aby to zrobić, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > **Filtr** > **Kategoria urządzeń**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Używanie programu TeamViewer do udostępniania ekranów urządzeń z systemami iOS i MacOS<!-- 1985547 -->
Administratorzy mogą teraz łączyć się z programem [TeamViewer](device-profile-android-teamviewer.md), a następnie uruchamiać sesję udostępniania ekranu na urządzeniach z systemem iOS i macOS. Użytkownicy urządzeń iPhone i iPad oraz urządzeń z systemem macOS mogą na żywo udostępniać ekrany innemu urządzeniu stacjonarnemu lub przenośnemu. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Obsługa wielu programów Exchange Connector <!-- 2070451 -->
Nie ma już ograniczenia do jednego programu Microsoft Intune Exchange Connector na dzierżawę. Usługa Intune obsługuje teraz wiele programów Microsoft Intune Exchange Connector, dzięki czemu możliwe będzie skonfigurowanie dostępu warunkowego w usłudze Intune przy użyciu wielu lokalnych organizacji programu Exchange.

Dzięki lokalnemu łącznikowi programu Exchange w usłudze Intune możesz zarządzać dostępem urządzeń do lokalnych skrzynek pocztowych programu Exchange na podstawie tego, czy urządzenie jest zarejestrowane w usłudze Intune i jest zgodne z zasadami zgodności urządzeń usługi Intune. Aby skonfigurować łącznik, pobierz lokalny łącznik programu Exchange z witryny Azure Portal i zainstaluj go na serwerze w organizacji programu Exchange. Na pulpicie nawigacyjnym usługi Microsoft Intune wybierz pozycję **Dostęp lokalny**, a następnie w obszarze **Konfiguracja** wybierz pozycję **Łącznik Exchange ActiveSync**. Pobierz lokalny łącznik programu Exchange i zainstaluj go na serwerze w organizacji programu Exchange. Ponieważ nie ma już ograniczenia do jednego łącznika programu Exchange na dzierżawę, jeśli masz dodatkowe organizacje programu Exchange, możesz wykonać te same czynności, aby pobrać i zainstalować łącznik dla każdej dodatkowej organizacji programu Exchange.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Nowe szczegóły sprzętu urządzenia: CCID <!-- 2156657 -->
Informacje o specyfikacji CCID (Chip Card Interface Device) są teraz uwzględniane dla każdego urządzenia. Aby je wyświetlić, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**> sprawdź informacje w obszarze **Szczegóły sieci**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Przypisywanie wszystkich użytkowników i wszystkich urządzeń jako grup zakresu <!-- 2196803 -->
W grupach zakresu możesz teraz przypisywać wszystkich użytkowników, wszystkie urządzenia oraz wszystkich użytkowników i wszystkie urządzenia. Aby to zrobić, wybierz pozycję **Role usługi Intune** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > wybierz przypisanie > **Zakres (grupy)**.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806-wnready--"></a>Informacje o identyfikatorze UDID są teraz dostępne w przypadku urządzeń z systemem iOS i macOS <!-- 2219806 wnready-->
Aby wyświetlić unikatowy identyfikator urządzenia (UDID) dla urządzeń z systemem iOS i macOS, przejdź do pozycji **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**. Identyfikator UDID jest dostępny tylko dla urządzeń firmowych (zgodnie z ustawieniem w obszarze **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości** > **Własność urządzeń**).

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Ulepszone rozwiązywanie problemów z instalacją aplikacji <!-- 928990 -->
Na urządzeniach zarządzanych przez oprogramowanie MDM w usłudze Microsoft Intune czasami operacje instalacji aplikacji mogą zakończyć się niepowodzeniem. W takich sytuacjach zrozumienie przyczyny niepowodzenia lub rozwiązanie problemu może okazać się wyzwaniem. Udostępniamy publiczną wersję zapoznawczą naszej funkcji rozwiązywania problemów z aplikacjami. W obszarach poszczególnych urządzeń zauważysz nowy węzeł o nazwie **Aplikacje zarządzane**. Ta pozycja służy do wyświetlania listy aplikacji dostarczonych za pomocą oprogramowania MDM usługi Intune. Wewnątrz węzła znajduje się lista stanów instalacji aplikacji. Po wybraniu aplikacji zostanie wyświetlony widok rozwiązywania problemów związanych z tą aplikacją. W widoku rozwiązywania problemów zostanie przedstawiony cały cykl życia aplikacji, np. czas utworzenia i zmodyfikowania aplikacji, wybrania jej jako docelowej i dostarczenia do urządzenia. Ponadto jeśli instalacja aplikacji zakończyła się niepowodzeniem, zostanie wyświetlony kod błędu i użyteczny komunikat dotyczący przyczyny tego błędu. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Zasady ochrony aplikacji usługi Intune i przeglądarka Microsoft Edge <!-- 1818968 -->
Przeglądarka Microsoft Edge dla urządzeń przenośnych (iOS i Android) obsługuje teraz zasady ochrony aplikacji w usłudze Microsoft Intune. Użytkownicy urządzeń z systemami iOS i Android, którzy logują się przy użyciu kont firmowych usługi Azure AD w aplikacji Edge, będą chronieni przez usługę Intune. Na urządzeniach z systemem iOS zasady **Wymagaj programu Managed Browser dla zawartości internetowej** pozwolą użytkownikom na otwieranie linków w przeglądarce Edge, gdy jest ona zarządzana.

## <a name="week-of-may-14-2018"></a>Tydzień od 14 maja 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Wymagana instalacja zasad, aplikacji oraz profilów certyfikatów i sieciowych <!-- 1553555 -->

Administratorzy mogą zablokować dostęp użytkowników końcowych do pulpitu systemu Windows 10 RS4 do momentu zainstalowania zasad, aplikacji oraz profilów certyfikatów i sieciowych przez usługę Intune podczas aprowizowania urządzeń z rozwiązaniem AutoPilot. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Konfigurowanie zasad ochrony aplikacji <!-- 2144597 Part 2 -->

W witrynie Azure Portal zamiast przechodzenia do bloku usługi Intune App Protection możesz teraz po prostu przejść do usługi Intune. Teraz jest tylko jedna lokalizacja zasad ochrony aplikacji w ramach usługi Intune. Zapamiętaj, że wszystkie zasady ochrony aplikacji znajdują się w bloku **Aplikacja mobilna** w usłudze Intune w obszarze **Zasady ochrony aplikacji**. Ta integracja pomaga uprościć administrowanie chmurą. Pamiętaj, że wszystkie zasady ochrony aplikacji są już dostępne w usłudze Intune i możesz modyfikować dowolne wcześniej skonfigurowane zasady. Zasady ochrony aplikacji (APP) i zasady dostępu warunkowego (CA) w usłudze Intune znajdują się teraz w obszarze **Dostęp warunkowy**, który znajduje się w sekcji **Zarządzanie** w bloku **Microsoft Intune** lub w sekcji **Zabezpieczenia** w bloku **Azure Active Directory**. Aby uzyskać więcej informacji na temat modyfikowania zasad dostępu warunkowego, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Aby uzyskać dodatkowe informacje, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>Tydzień od 7 maja 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Pomoc techniczna dotycząca programu Samsung Knox Mobile Enrollment<!--1112863-->

Korzystając z usługi Intune z programem Samsung Knox Mobile Enrollment (KME) można zarejestrować dużą liczbę urządzeń firmowych z systemem Android. Użytkownicy korzystający z sieci komórkowej lub Wi-Fi mogą za pomocą kilku naciśnięć zarejestrować urządzenie przy jego pierwszym włączeniu. Podczas korzystania z aplikacji Knox Deployment urządzenia mogą być rejestrowane za pomocą funkcji Bluetooth lub NFC. Aby uzyskać więcej informacji, zobacz temat [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md) (Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Żądanie pomocy w aplikacji Portal firmy w systemie Windows 10 <!-- 1874137 -->

Gdy użytkownik zainicjuje przepływ pracy w celu uzyskania pomocy dotyczącej problemu, aplikacja Portal firmy w systemie Windows 10 wyśle dzienniki aplikacji bezpośrednio do firmy Microsoft. Ułatwia to rozwiązywanie i usuwanie problemów, które zostały zgłoszone firmie Microsoft.

## <a name="week-of-april-23-2018"></a>Tydzień od 23 kwietnia 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Obsługa kodu dostępu dla numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi w systemie Android<!-- 1438086 -->

Administratorzy usługi Intune mogą określić wymaganie dotyczące uruchamiania aplikacji w celu wymuszenia użycia kodu dostępu zamiast numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi. W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. Usługa Intune obsługuje kod dostępu podobnie jak istniejący liczbowy numer PIN, umożliwiając ustawienie minimalnej długości oraz reguł powtarzania znaków i sekwencji w konsoli administracyjnej. Ta funkcja wymaga najnowszej wersji aplikacji Portal firmy w systemie Android. Ta funkcja jest już dostępna dla systemu iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Obsługa aplikacji biznesowych dla systemu macOS <!-- 1473977 -->
Usługa Microsoft Intune będzie umożliwiać instalowanie aplikacji biznesowych (LOB) dla systemu macOS z witryny Azure Portal. Aplikację LOB dla systemu macOS będzie można dodać do usługi Intune po jej wstępnym przetworzeniu za pomocą narzędzia dostępnego w usłudze GitHub. W witrynie Azure Portal wybierz pozycję **Aplikacje klienckie** w bloku **Intune**. W bloku **Aplikacje klienckie** wybierz pozycję **Aplikacje** > **Dodaj**. W bloku **Dodaj aplikację** wybierz pozycję **Aplikacja biznesowa**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Wbudowane grupy Wszyscy użytkownicy i Wszystkie urządzenia na potrzeby przypisywania aplikacji Android for Work (AFW) <!-- 1813073 -->
Można użyć wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji AFW. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Usługa Intune zainstaluje wymagane aplikacje, które są odinstalowywane przez użytkowników <!-- 1947010 -->
Jeśli użytkownik końcowy odinstaluje wymaganą aplikację, usługa Intune automatycznie ponownie instaluje aplikację w ciągu 24 godzin, nie czekając na zakończenie 7-dniowego cyklu ponownej oceny.

### <a name="device-configuration"></a>Konfiguracja urządzenia

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Wykres profilów urządzeń i lista stanów obejmuje wszystkie urządzenia w grupie <!-- 1449153 eeready -->
Po skonfigurowaniu profilu urządzenia (**Konfiguracja urządzenia** > **Profile**) wybiera się profil urządzenia, taki jak dotyczący systemu iOS. Ten profil jest przypisywane do grupy, która zawiera urządzenia z systemem iOS i inne. Licznik na wykresie graficznym pokazuje, że profil jest stosowany do urządzeń z systemem iOS *i* innych (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Przegląd**). Po wybraniu wykresu graficznego na karcie **Przegląd** na liście **Stan urządzenia** zostaną wyświetlone wszystkie urządzenia w grupie zamiast tylko urządzeń z systemem iOS. 

Dzięki tej aktualizacji wykres graficzny (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Przegląd**) przedstawia tylko liczbę dla konkretnego profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy urządzeń z systemem iOS, wykres zawiera tylko liczbę urządzeń z systemem iOS. Po wybraniu wykresu graficznego i otwarciu pozycji **Stan urządzeń** zostaną wyświetlone tylko urządzenia z systemem iOS.

Podczas wprowadzania tej aktualizacji graficzny wykres użytkowników jest tymczasowo usuwany. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Zawsze włączona sieć VPN w systemie Windows 10 <!--1333666 -->

Obecnie opcji [Zawsze włączone](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) można używać na urządzeniach z systemem Windows 10 za pomocą niestandardowego profilu wirtualnej sieci prywatnej (VPN) utworzonego za pomocą identyfikatora URI OMA.

Dzięki tej aktualizacji administratorzy mogą włączyć ustawienie Zawsze włączone dla profilów sieci VPN systemu Windows 10 bezpośrednio w usłudze Intune za pomocą witryny Azure Portal. Zawsze włączone profile sieci VPN automatycznie nawiążą połączenie, gdy:

- Użytkownik zaloguje się na urządzeniu
- Sieć na urządzeniu zostanie zmieniona
- Ekran na urządzeniu zostanie włączony ponownie po wyłączeniu

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nowe ustawienia drukarek dla profili edukacyjnych <!-- 1308900 -->

W przypadku profilów edukacyjnych są dostępne nowe ustawienia w kategorii **Drukarki**: **Drukarki**, **Drukarka domyślna**, **Dodaj nowe drukarki**.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Pokazywanie identyfikatora rozmówcy w profilu osobistym — Android for Work <!--1098984 -->
Użytkownicy końcowy korzystający z profilu osobistego na urządzeniu mogą nie widzieć identyfikatora rozmówcy dla kontaktu służbowego. 

Ta aktualizacja wprowadza nowe ustawienie w obszarze **Android for Work** > **Ograniczenia dotyczące urządzeń** > **Ustawienia profilu służbowego**:
- Wyświetlanie identyfikatora rozmówcy dla kontaktu służbowego w profilu osobistym

Po włączeniu (bez konfigurowania) szczegóły rozmówcy dla kontaktu służbowego są wyświetlane w profilu osobistym. Po zablokowaniu numer rozmówcy dla kontaktu służbowego nie jest wyświetlany w profilu osobistym. 

Dotyczy: urządzenia z systemem Android w wersji 6.0 i nowszych z profilem służbowym

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Dodano nowe ustawienia funkcji Windows Defender Credential Guard do ustawień programu Endpoint Protection <!--1102252 --><!--from 1802 and 1804-->

Dzięki tej aktualizacji funkcja [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (obszar **Konfiguracja urządzenia** > **Profile** > **Endpoint Protection**) obejmuje następujące ustawienia: 

- **Windows Defender Credential Guard**: służy do włączania funkcji Credential Guard z zabezpieczeniami opartymi na wirtualizacji. Włączenie tej funkcji pomaga chronić poświadczenia przy następnym ponownym uruchomieniu, gdy obydwie opcje: **Poziom zabezpieczeń platformy z funkcją bezpiecznego rozruchu** i **Zabezpieczenia oparte na wirtualizacji** zostały włączone. Dostępne opcje:
  - **Wyłączone**: jeśli funkcja Credential Guard została wcześniej włączona za pomocą opcji **Włączone bez blokady**, ta opcja powoduje zdalne wyłączenie funkcji Credential Guard.

  - **Włączone z blokadą UEFI**: zapewnia, że funkcji Credential Guard nie będzie można wyłączyć za pomocą klucza rejestru ani przy użyciu zasad grupy. Aby wyłączyć funkcję Credential Guard po użyciu tego ustawienia, należy ustawić zasady grupy na „Wyłączone“. Następnie należy usunąć funkcje zabezpieczeń z każdego komputera — wymagana jest fizyczna obecność użytkownika. Te kroki spowodują wyczyszczenie konfiguracji utrwalonej w interfejsie UEFI. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

  - **Włączone bez blokady**: umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 (wersja 1511) lub nowszy.

Następujące technologie zależne są włączane automatycznie podczas konfigurowania funkcji Credential Guard: 

  - **Włącz zabezpieczenia oparte na wirtualizacji (VBS)**: włącza zabezpieczenia oparte na wirtualizacji (VBS) podczas następnego ponownego uruchomienia. Zabezpieczenia oparte na wirtualizacji używają funkcji hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń, i wymagają bezpiecznego rozruchu.
  - **Bezpieczny rozruch z bezpośrednim dostępem do pamięci (DMA)**: włącza zabezpieczenia VBS z funkcją bezpiecznego rozruchu i bezpośrednim dostępem do pamięci. Ochrona DMA wymaga obsługi sprzętowej i można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Użycie niestandardowej nazwy podmiotu w certyfikacie SCEP <!-- 2064190 -->
Istnieje możliwość użycia nazwy pospolitej **OnPremisesSamAccountName** w niestandardowej nazwie podmiotu dla profilu certyfikatu SCEP. Na przykład możesz użyć nazwy `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Blokowanie aparatu i przechwytywania ekranu w aplikacji Android for Work <!-- 1098977 eeready-->
Podczas konfigurowania ograniczeń urządzenia z systemem Android można zablokować dwie nowe właściwości: 
- Aparat: blokuje dostęp do wszystkich aparatów w urządzeniu
- Przechwytywanie ekranu: blokuje przechwytywanie ekranu i wyświetlanie zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo

Dotyczy aplikacji Android for Work.


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nowe kroki rejestracji dla użytkowników na urządzeniach z systemem macOS High Sierra 10.13.2+ <!--1734567 -->
W systemie macOS High Sierra 10.13.2 wprowadzono pojęcie rejestracji w rozwiązaniu MDM „zatwierdzonej przez użytkownika”. Zatwierdzone rejestracje umożliwiają usłudze Intune zarządzanie niektórymi ustawieniami istotnymi dla zabezpieczeń. Aby uzyskać więcej informacji, zobacz dokumentację pomocy technicznej firmy Apple: https://support.apple.com/HT208019.

Urządzenia zarejestrowane przy użyciu aplikacji Portal firmy dla systemu macOS są traktowane jako „niezatwierdzone przez użytkownika”, chyba że użytkownik końcowy otworzy preferencje systemu i ręcznie wykona zatwierdzenie. Dlatego aplikacja Portal firmy dla systemu macOS teraz kieruje użytkowników systemu macOS 10.13.2 i nowszych do kroków ręcznego zatwierdzenia rejestracji pod koniec procesu rejestracji. Konsola administracyjna usługi Intune zgłasza fakt zatwierdzenia zarejestrowanego urządzenia przez użytkownika.



### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>Zaawansowana ochrona przed zagrożeniami (ATP) i usługi Intune są w pełni zintegrowane <!-- EEready 1629303 -->

Funkcja [zaawansowanej ochrony przed zagrożeniami](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) pokazuje poziom ryzyka urządzeń z systemem Windows 10. W usłudze Windows Defender Security Center (portal ATP) można utworzyć połączenie z usługą Microsoft Intune. Po jego utworzeniu zostają użyte zasady zgodności z usługą Intune, aby określić dopuszczalny poziom zagrożenia. Jeśli poziom zagrożenia zostanie przekroczony, zasady dostępu warunkowego usługi Azure Active Directory (AD) mogą zablokować dostęp do różnych aplikacji w ramach danej organizacji.

Ta funkcja pozwala systemowi ATP skanować pliki, wykrywać zagrożenia oraz zgłaszać zdarzenia o podwyższonym ryzyku na urządzeniach z systemem Windows 10.

Zobacz temat [Enable ATP with conditional access in Intune](advanced-threat-protection.md) (Włączanie systemu ATP z dostępem warunkowym w usłudze Intune).

#### <a name="support-for-user-less-devices----1637553---"></a>Obsługa urządzeń bez użytkowników <!-- 1637553 -->
Usługa Intune oferuje możliwość oceny zgodności urządzenia bez użytkowników, takiego jak Microsoft Surface Hub. Zasady zgodności mogą stosować się do konkretnych urządzeń. Dzięki temu zgodność (i niezgodność) można określić dla urządzeń, które nie mają skojarzonego użytkownika.

#### <a name="delete-autopilot-devices----1713650---"></a>Usuwanie urządzeń z rozwiązaniem AutoPilot <!-- 1713650 -->
Administratorzy usługi Intune mogą [usuwać urządzenia z rozwiązaniem AutoPilot](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Ulepszona funkcja usuwania urządzeń <!--1832333 -->
Nie trzeba już wymagać usunięcia danych firmy ani resetować do ustawień fabrycznych przed [usunięciem urządzenia z usługi Intune](devices-wipe.md#delete-devices-from-the-intune-portal).

Aby zobaczyć nową funkcję, zaloguj się do usługi Intune i wybierz pozycje **Urządzenia** > **Wszystkie urządzenia** > nazwa urządzenia > **Usuń**.

Jeśli chcesz nadal otrzymywać powiadomienia o wyczyszczeniu lub wycofaniu, możesz użyć standardowego cyklu życia urządzenia, uruchamiając polecenie **Usuń dane firmy** oraz **Resetuj do ustawień fabrycznych**, a następnie polecenie **Usuń**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Odtwarzanie dźwięków w systemie iOS w trybie utraty <!-- 1947769 -->
Jeśli urządzenia z systemem iOS nadzorowane w rozwiązaniu do zarządzania urządzeniami przenośnymi są w [trybie utraty](device-lost-mode.md), możesz [odtwarzać dźwięk](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie z systemem iOS > **Przegląd** > **Więcej**). Dźwięk będzie odtwarzany w sposób ciągły aż do zakończenia trybu utraty na urządzeniu lub wyłączenia przez użytkownika dźwięku na urządzeniu. Dotyczy urządzeń z systemem iOS 9.3 lub nowszym.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Blokowanie wyników internetowych w wyszukiwaniach przeprowadzanych na urządzeniu usługi Intune lub zezwalanie na te wyniki <!--1972804-->

Administratorzy mogą teraz blokować internetowe wyniki wyszukiwań przeprowadzanych na urządzeniu.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Ulepszona obsługa komunikatów o błędach przekazywania certyfikatu wypychanego przez rozwiązanie MDM firmy Apple <!-- 2172331 -->

Komunikat o błędzie zawiera wyjaśnienie mówiące o tym, że podczas odnawiania istniejącego certyfikatu rozwiązania MDM należy użyć tego samego identyfikatora Apple ID.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testowanie Portalu firmy dla systemu macOS na maszynach wirtualnych <!-- 2216679 -->

Opublikowaliśmy wskazówki ułatwiające administratorom IT testowanie aplikacji Portal firmy dla systemu macOS na maszynach wirtualnych z programami Parallels Desktop i VMware Fusion. Dalsze informacje znajdują się w sekcji [Rejestrowanie maszyn wirtualnych z systemem macOS na potrzeby testowania](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### <a name="user-interface"></a>Interfejs użytkownika

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Ulepszone kafelki urządzenia w aplikacji Portal firmy dla systemu Windows 10 <!--2213364 -->

Kafelki zostały zaktualizowane pod kątem zwiększenia dostępności dla użytkowników z ograniczonymi możliwościami widzenia oraz poprawienia sposobu współdziałania z narzędziami do odczytywania ekranu.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Wysyłanie raportów diagnostycznych z aplikacji Portal firmy dla systemu macOS <!-- 2216677 -->
Aplikacja Portal firmy dla urządzeń z systemem macOS została zaktualizowana pod kątem ulepszenia sposobu raportowania błędów dotyczących usługi Intune przez użytkowników. W aplikacji Portal firmy pracownicy mogą:

- Przekazywać raporty diagnostyczne bezpośrednio do zespołu deweloperów firmy Microsoft.
- Wysłać wiadomość e-mail z identyfikatorem zdarzenia do zespołu pomocy technicznej IT firmy.

Aby uzyskać więcej informacji, zobacz [Wysyłanie błędów w przypadku systemu macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Usługa Intune dostosowuje się do systemu Fluent Design System w aplikacji Portal firmy dla systemu Windows 10 <!-- 1195010 WNready -->
Aplikacja Portal firmy usługi Intune dla systemu Windows 10 została zaktualizowana w celu dodania [widoku nawigacji systemu Fluent Design System](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Wzdłuż boku aplikacji znajduje się statyczna, pionowa lista wszystkich stron najwyższego poziomu. Kliknij dowolny link, aby szybko wyświetlać strony i przełączać się między nimi. Jest to pierwsza z kilku aktualizacji, które będą wprowadzane w ramach naszych ciągłych wysiłków mających na celu stworzenie bardziej adaptacyjnego, empatycznego, znanego środowiska pracy w usłudze Intune. Aby wyświetlić zaktualizowany wygląd, przejdź do obszaru [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Tydzień od 16 kwietnia 2018 r.

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Korzystanie z klienta Cisco AnyConnect dla systemu iOS <!-- EEready 1333708 -->

W przypadku tworzenia nowego profilu sieci VPN dla systemu iOS są teraz dostępne dwie opcje: **Cisco AnyConnect** i **Cisco Legacy AnyConnect**. Profile Cisco AnyConnect obsługują wersję 4.0.7x i nowsze. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x oraz jego starszymi wersjami, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS. W przypadku platform systemów Android i macOS oraz programu Android for Work nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Urządzenia z systemem macOS zarejestrowane w oprogramowaniu Jamf można obecnie zarejestrować w usłudze Intune <!-- 2370684 -->

W wersjach 1.3 i 1.4 portalu firmy systemu macOS nie można było pomyślnie rejestrować urządzeń z oprogramowaniem Jamf w usłudze Intune. W wersji 1.4.2 portalu macOS rozwiązano ten problem.


## <a name="week-of-april-9-2018"></a>Tydzień od 9 kwietnia 2018 r.  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Zaktualizowane środowisko pomocy w aplikacji Portal firmy dla systemu Android <!-- 1631531 -->

Zaktualizowaliśmy środowisko pomocy w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla platformy Android. Teraz, gdy użytkownik napotka problem w aplikacji, może nacisnąć pozycję **Menu** > **Pomoc**, a następnie:
- Przekazać dzienniki diagnostyczne do firmy Microsoft.
- Wysłać wiadomość e-mail z opisem problemu i identyfikatorem zdarzenia do osoby odpowiedzialnej za pomoc techniczną w firmie.  

Aby sprawdzić zaktualizowane środowisko pomocy, przejdź do obszaru [Wysyłanie dzienników pocztą e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android) i [Wysyłanie błędów do firmy Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nowy wykres trendu niepowodzeń rejestracji i tabela z przyczynami niepowodzeń <!-- 1471783 -->

Na stronie Przeglądu rejestracji można wyświetlić trend niepowodzeń rejestracji i pięć najczęstszych przyczyn niepowodzeń. Klikając wykres lub tabelę, można przejść do szczegółów, aby znaleźć porady dotyczące rozwiązywania problemów i sugestie dotyczące korygowania.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Aktualizowanie miejsca konfigurowania zasad ochrony aplikacji <!-- 2144597 -->

W witrynie Azure Portal w ramach usługi Microsoft Intune zostanie włączone tymczasowe przekierowanie z bloku usługi **Intune App Protection** do bloku **Aplikacja mobilna**. Uwaga: wszystkie zasady ochrony aplikacji znajdują się już w bloku **Aplikacja mobilna** w usłudze Intune w obszarze konfiguracji aplikacji. Zamiast przechodzić do usługi Intune App Protection, należy przejść do usługi Intune. W kwietniu 2018 r. zatrzymamy to przekierowywanie i całkowicie usuniemy blok usługi **Intune App Protection**, więc będzie istnieć tylko jedna lokalizacja z zasadami ochrony aplikacji w usłudze Intune. 

**Jak to wpłynie na mnie?**
Ta zmiana wpłynie zarówno na klientów z autonomiczną usługą Intune, jak i na klientów ze środowiskami hybrydowymi (usługą Intune z programem Configuration Manager). Ta integracja pomoże uprościć administrowanie chmurą.

**Co należy zrobić, aby przygotować się do tej zmiany?**
Otaguj usługę **Intune** jako ulubioną zamiast bloku usługi **Intune App Protection** i zapoznaj się z przepływem pracy zasad ochrony aplikacji w bloku **Aplikacja mobilna** w usłudze Intune. Przez krótki okres będzie działać przekierowanie, a następnie blok **App Protection** zostanie usunięty. Pamiętaj, że wszystkie zasady ochrony aplikacji są już dostępne w usłudze Intune i możesz modyfikować dowolne zasady dostępu warunkowego. Aby uzyskać więcej informacji na temat modyfikowania zasad dostępu warunkowego, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Aby uzyskać dodatkowe informacje, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>Tydzień od 2 kwietnia 2018 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Aktualizacja środowiska użytkownika aplikacji Portal firmy dla systemu iOS <!--1412866 -->
Wydaliśmy dużą aktualizację środowiska użytkownika w aplikacji Portal firmy dla systemu iOS. Aktualizacja obejmuje całkiem nowy projekt wizualny, który zapewnia zmodernizowany wygląd i działanie. Zachowaliśmy funkcjonalność aplikacji, ale zwiększyliśmy jej użyteczność i dostępność.  

Ponadto wprowadziliśmy następujące zmiany:
- Obsługa urządzenia iPhone X.
- Szybsze uruchamianie aplikacji i ładowanie, co oszczędza czas użytkowników.
- Dodatkowe paski postępu zapewniające użytkownikom najbardziej aktualne informacje o stanie.
- Ulepszenia sposobu przekazywania dzienników przez użytkowników — jeśli coś pójdzie nie tak, będzie łatwiej to zgłosić.  

Aby wyświetlić zaktualizowany wygląd, przejdź do obszaru [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Ochrona lokalnych danych programu Exchange przy użyciu rozwiązania Intune APP i dostępu warunkowego <!-- 1056954 -->
Teraz możesz użyć rozwiązania App Policy Protection (APP) i funkcji dostępu warunkowego usługi Intune w celu ochrony dostępu do lokalnych danych programu Exchange za pomocą programu Outlook Mobile. Aby dodać lub zmodyfikować zasady ochrony aplikacji w witrynie Azure Portal, wybierz pozycję **Microsoft Intune** > **Aplikacje klienckie** > **Zasady ochrony aplikacji**. Przed użyciem tej funkcji upewnij się, że spełnione są [Wymagania dotyczące programu Outlook dla systemów iOS i Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="week-of-march-26-2018"></a>Tydzień od 26 marca 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Alerty dotyczące wygasających aplikacji biznesowych (LOB) dla systemu iOS dla usługi Microsoft Intune <!-- 748789 -->

W witrynie Azure Portal usługa Intune powiadomi Cię o aplikacjach biznesowych dla systemu iOS, które wkrótce wygasną. Po przekazaniu nowej wersji aplikacji biznesowej dla systemu iOS usługa Intune usunie powiadomienie o wygaśnięciu z listy aplikacji. Powiadomienie o wygaśnięciu będzie aktywne tylko dla nowo przekazanych aplikacji biznesowych dla systemu iOS. Ostrzeżenie zostanie wyświetlone 30 dni przed wygaśnięciem profilu aprowizacji aplikacji biznesowych dla systemu iOS. Po jego wygaśnięciu stan alertu zostanie zmieniony na Wygasł.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Dostosowywanie motywów aplikacji Portal firmy za pomocą kodów szesnastkowych <!--1049561 -->

Kolor motywów w aplikacjach Portal firmy można dostosować przy użyciu kodów szesnastkowych. Po wprowadzeniu kodu szesnastkowego usługa Intune określa kolor tekstu, który zapewni najwyższy poziom kontrastu między tekstem a tłem. Podgląd koloru tekstu i logo firmy na tle wybranego koloru możesz wyświetlić, wybierając pozycję **Aplikacje klienckie** > **Portal firmy**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup dla programu Android Enterprise <!-- 1813081 -->

System Android Enterprise (wcześniej znany jako Android for Work) obsługuje dołączanie i wykluczanie grup, ale nie obsługuje wstępnie utworzonych grup wbudowanych **Wszyscy użytkownicy** i **Wszystkie urządzenia**. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Nowe usprawnienia zabezpieczeń w usłudze Intune <!-- 1637539 -->   

Wprowadziliśmy przełącznik w usłudze Intune na platformie Azure, którego klienci autonomicznej usługi Intune mogą użyć w celu traktowania urządzeń bez żadnych przypisanych zasad jako **zgodne** (wyłączona funkcja zabezpieczeń) lub **niezgodne** (włączona funkcja zabezpieczeń). W ten sposób dostęp do zasobów będzie możliwy dopiero po ocenie zgodności urządzenia.

Wpływ tej funkcji na klientów będzie zależeć od tego, czy zostały już przypisane zasady zgodności, czy nie.

- W przypadku nowych oraz istniejących kont i braku przypisanych do urządzeń zasad zgodności, przełącznik zostanie automatycznie ustawiony w na wartość **Zgodne**. Ta funkcja jest domyślnie wyłączona w konsoli. Nie wpływa to w żaden sposób na użytkowników końcowych.
- W przypadku istniejących kont i posiadania jakichkolwiek urządzeń z przypisanymi do nich zasad zgodności, przełącznik zostanie automatycznie ustawiony na wartość **Niezgodne**. Wraz z wprowadzeniem aktualizacji z marca ta funkcja jest domyślnie włączona.

W przypadku używania zasad zgodności z dostępem warunkowym i włączenia tej funkcji wszystkie urządzenia, które nie mają przypisanych jakichkolwiek zasad zgodności, zostaną zablokowane przez funkcję dostępu warunkowego. Skojarzeni z tymi urządzeniami użytkownicy końcowi, którzy wcześniej mieli dostęp do poczty e-mail, utracą ten dostęp, chyba że do wszystkich urządzeń zostaną przypisane jakiekolwiek zasady zgodności.   

Pamiętaj, że chociaż domyślny stan przełącznika jest wyświetlany w interfejsie użytkownika od razu po wprowadzeniu aktualizacji usługi Intune z marca, stan tego przełącznika nie jest od razu wymuszany. Wszelkie zmiany dotyczące tego przełącznika nie będą miały wpływu na zgodność urządzenia do momentu wprowadzenia pakietu testowego na koncie z działającym przełącznikiem. Poinformujemy Cię za pośrednictwem Centrum wiadomości o zakończeniu wprowadzania pakietu testowego na koncie. Może to potrwać kilka dni po zaktualizowaniu usługi Intune w marcu.

**Dodatkowe informacje**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Ulepszone wykrywanie zdjęcia zabezpieczeń systemu <!-- 846515 -->

Ulepszone wykrywanie zdjęcia zabezpieczeń systemu jest nowym ustawieniem zgodności, które usprawnia sposób, w jaki usługa Intune ocenia urządzenia ze zdjętymi zabezpieczeniami systemu. To ustawienie powoduje częstsze ewidencjonowanie urządzenia w usłudze Intune z wykorzystaniem usług lokalizacyjnych urządzenia, co ma wpływ na użycie baterii.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetowanie haseł dla urządzeń z systemem Android O <!-- 1238299 -->
Możliwe będzie resetowanie haseł zarejestrowanych urządzeń z systemem Android 8.0 z profilami służbowymi. Po wysłaniu żądania „Resetuj hasło” do urządzenia z systemem Android 8.0 ustawi ono nowe hasło odblokowania urządzenia lub wezwanie zarządzanego profilu dla bieżącego użytkownika. Hasło lub wezwanie jest wysyłane i zaczyna obowiązywać natychmiast.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Określanie zasad zgodności dla urządzeń w grupach urządzeń<!--1307012 -->

Możesz określać zasady zgodności dla użytkowników w grupach użytkowników. Ta aktualizacja wprowadza również możliwość określania zasad zgodności dla urządzeń w grupach urządzeń. Urządzenia określone jako część grupy urządzeń nie będą otrzymywać żadnych akcji dotyczących zgodności.

#### <a name="new-management-name-column----1333586---"></a>Nowa kolumna Nazwa zarządzania <!-- 1333586 -->
 W bloku urządzeń dostępna jest nowa kolumna **Nazwa zarządzania**. Jest to generowana automatycznie, nieedytowalna nazwa przypisywana każdemu urządzeniu na podstawnie następującego wzoru:
- Nazwa domyślna dla wszystkich urządzeń: <username><em><devicetype></em><enrollmenttimestamp>
- W przypadku urządzeń dodanych zbiorczo: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Jest to opcjonalna kolumna w bloku urządzeń. Domyślnie jest ona niedostępna i można do niej uzyskać dostęp tylko przy użyciu selektora kolumn. Ta nowa kolumna nie ma wpływu na nazwę urządzenia.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>W przypadku urządzeń z systemem iOS co 15 minut jest wyświetlany monit o ustawienie numeru PIN <!--1550837 -->
Po zastosowaniu zasad zgodności lub konfiguracji względem urządzenia z systemem iOS użytkownikom będzie wyświetlany co 15 minut monit o ustawienie numeru PIN. Monity będą wyświetlane, dopóki numer PIN nie zostanie ustawiony.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Planowanie aktualizacji automatycznych <!--1805514 -->
Usługa Intune zapewnia kontrolę nad instalowaniem aktualizacji automatycznych za pomocą [ustawień pierścienia aktualizacji systemu Windows](windows-update-for-business-configure.md). Ta aktualizacja wprowadza możliwość zaplanowania cyklicznych aktualizacji, w tym tygodnia, dnia i godziny.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Użyj pełnej nazwy wyróżniającej jako podmiotu dla certyfikatu protokołu SCEP <!--2221763 -->
Podczas tworzenia profilu certyfikatu SCEP należy wprowadzić nazwę podmiotu. Ta aktualizacja wprowadza możliwość używania pełnej nazwy wyróżniającej jako tematu. W obszarze **Nazwa podmiotu** wybierz pozycję **Niestandardowa** i wprowadź wartość `CN={{OnPrem_Distinguished_Name}}`. Aby użyć zmiennej `{{OnPrem_Distinguished_Name}}`, zsynchronizuj atrybut użytkownika `onpremisesdistingishedname` z usługą Azure AD za pomocą narzędzia [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Włączanie funkcji udostępniania kontaktów przy użyciu połączenia Bluetooth — Android for Work <!--1098983 -->
Domyślnie system Android uniemożliwia synchronizowanie kontaktów z profilu służbowego z urządzeniami Bluetooth. W związku z tym kontakty profilu służbowego nie są wyświetlane w identyfikatorze dzwoniącego w przypadku urządzeń Bluetooth.

Ta aktualizacja wprowadza nowe ustawienie w obszarze **Android for Work** > **Ograniczenia dotyczące urządzeń** > **Ustawienia profilu służbowego**:
- Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth

Administrator usługi Intune może skonfigurować te ustawienia, aby włączyć udostępnianie. Jest to przydatne podczas parowania urządzenia z samochodowym urządzeniem Bluetooth, które w sposób bezobsługowy wyświetla identyfikator dzwoniącego. Po włączeniu tej funkcji kontakty profilu służbowego są wyświetlane. Jeśli funkcja nie zostanie włączona, kontakty profilu służbowego nie będą wyświetlane.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Konfigurowanie programu Gatekeeper w celu kontrolowania źródła pobierania aplikacji systemu macOS <!-- 1690459 -->

Możliwe jest skonfigurowanie programu Gatekeeper do ochrony urządzeń przed aplikacjami przez kontrolowanie lokalizacji, z których można pobierać aplikacje. Można skonfigurować następujące źródła pobierania: **Sklep Mac App Store**, **Sklep Mac App Store i zidentyfikowani deweloperzy** lub **Dowolne**. Ponadto możliwe jest skonfigurowanie, czy użytkownicy mogą instalować aplikacje, przytrzymując klawisz Control i klikając przyciskiem myszy, aby przesłonić kontrolki programu Gatekeeper.

Te ustawienia można znaleźć w obszarze **Konfiguracja urządzenia** -> **Utwórz profil** -> **macOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurowanie zapory aplikacji dla komputerów Mac <!-- 1690461 -->

Możesz konfigurować zaporę aplikacji dla komputerów Mac. Dzięki temu można kontrolować połączenia dla poszczególnych aplikacji, a nie dla poszczególnych portów. Ułatwia to uzyskanie korzyści z ochrony zapewnianej przez zaporę oraz ułatwia uniemożliwianie niepożądanym aplikacjom przejmowania kontroli na portami sieciowymi otwartymi dla wiarygodnych aplikacji.

Tę funkcję można znaleźć w obszarze **Konfiguracja urządzenia** -> **Utwórz profil** -> **macOS** -> **Endpoint Protection**.

Po włączeniu ustawienia Zapora możesz skonfigurować zaporę przy pomocy dwóch strategii:

- Blokowanie wszystkich połączeń przychodzących

   Możesz zablokować wszystkie połączenia przychodzące dla urządzeń docelowych. Jeśli postanowisz to zrobić, połączenia przychodzące zostaną zablokowane dla wszystkich aplikacji.

- Zezwalanie na określone aplikacje lub ich blokowanie

   Możesz zezwalać określonym aplikacjom na odbieranie połączeń przychodzących lub blokować im tę możliwość. Możesz także włączyć tryb niewidzialności, aby uniemożliwić wysyłanie odpowiedzi na żądania sondowania.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Szczegółowe kody błędów i komunikaty <!-- 1376342 -->

W konfiguracji urządzenia są widoczne bardziej szczegółowe kody błędów i komunikaty o błędach. Dzięki ulepszonemu raportowaniu można zobaczyć ustawienia, stan tych ustawień oraz szczegóły dotyczące rozwiązywania problemów.

##### <a name="more-information"></a>Więcej informacji

- Blokowanie wszystkich połączeń przychodzących

   Uniemożliwia to wszystkim usługom udostępniania (takim jak Udostępnianie plików czy Udostępnianie ekranu) odbieranie połączeń przychodzących. Usługi systemu, które nadal mogą odbierać połączenia przychodzące, to:
  - configd — implementuje protokół DHCP oraz inne usługi konfiguracji sieci
  - mDNSResponder — implementuje usługę Bonjour
  - racoon — implementuje protokołu IPSec

    Aby móc korzystać z usług udostępniania, upewnij się, że ustawienie **Połączenia przychodzące** ma wartość **Nie skonfigurowano** (a nie **Zablokowane**).

- Tryb niewidzialności

   Włącz tę opcję, aby zapobiec odpowiadaniu przez komputer na żądania sondowania. Komputer nadal odpowiada na żądania przychodzące dla autoryzowanych aplikacji. Nieoczekiwane żądania, takie jak ICMP (ping), są ignorowane.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Wyłączenie testów po ponownym uruchomieniu urządzenia <!--1805490 -->
Usługa Intune zapewnia kontrolę nad [zarządzaniem aktualizacjami oprogramowania]](windows-update-for-business-configure.md). Ta aktualizacja udostępnia właściwość <strong>Testy po ponownym uruchomieniu</strong>, która jest domyślnie włączona. Aby pominąć typowe testy przeprowadzane po ponownym uruchomieniu urządzenia (takie jak aktywni użytkownicy, poziom naładowania baterii itp.), wybierz pozycję <strong>Pomiń</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nowe kanały systemu Windows 10 Insider Preview dostępne dla pierścieni wdrażania <!-- 1746293 -->
Masz teraz możliwość wybrania następujących kanałów obsługi systemu Windows 10 Insider Preview podczas tworzenia pierścienia wdrażania systemu Windows 10:
- Kompilacja Windows Insider &#8208; wersja szybka
- Kompilacja Windows Insider &#8208; wersja wolna
- Wydanie kompilacji Windows Insider 

Aby uzyskać więcej informacji o tych kanałach, zobacz [Manage Insider Preview Builds](https://insider.windows.com/en-us/for-business-organization-admin/) (Zarządzanie kompilacjami Insider Preview).   
Aby uzyskać więcej informacji na temat tworzenia kanałów wdrażania w usłudze Intune, zobacz [Zarządzanie aktualizacjami oprogramowania w usłudze Intune](windows-update-for-business-configure.md).

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Ulepszona rejestracja za pomocą aplikacji Portal firmy <!-- 1874230 eeready-->
Użytkownicy rejestrujący urządzenia za pomocą aplikacji Portal firmy w systemie Windows 10 (kompilacja 1703 i nowsza) mogą teraz wykonać pierwszy krok rejestracji bez wychodzenia z aplikacji.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>Urządzenia HoloLens i Surface Hub są teraz wyświetlane na liście urządzeń <!--1725868 -->
Dodaliśmy obsługę wyświetlania urządzeń HoloLens i Surface Hub zarejestrowanych w usłudze Intune do aplikacji Portal firmy dla systemu Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Niestandardowe kategorie książek dla książek elektronicznych programu zakupów zbiorczych (VPP) <!-- 1488911 -->
Możliwe jest tworzenie niestandardowych kategorii książek elektronicznych, a następnie przypisywanie do tych kategorii książek elektronicznych programu VPP. Użytkownicy końcowi będą mogli wtedy wyświetlać nowo utworzone kategorie książek elektronicznych oraz książki przypisane do tych kategorii. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami i książkami kupionymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Zmiana obsługi opcji wysyłania opinii w aplikacji Portal firmy dla systemu Windows <!-- 2070166 -->
Od dnia 30 kwietnia 2018 r. opcja **Prześlij opinię** w aplikacji Portal firmy dla systemu Windows działa tylko na urządzeniach z wersją Rocznicowa aktualizacja systemu Windows 10 (1607) lub nowszą. Opcja wysyłania opinii nie jest już obsługiwana podczas korzystania z aplikacji Portal firmy dla systemu Windows w przypadku systemu:  
- Windows 10, wersja 1507  
- Windows 10, wersja 1511  
- Windows Phone 8,1 

Jeśli na Twoim urządzeniu jest uruchomiony system Windows 10 RS1 lub nowszy, pobierz najnowszą wersję aplikacji Portal firmy systemu Windows dostępną w sklepie Store. Jeśli używasz nieobsługiwanej wersji, przekaż opinię za pośrednictwem następujących kanałów: 
- Aplikacja Centrum opinii w systemie Windows 10
- Wiadomość e-mail na adres WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nowe ustawienia funkcji Windows Defender Application Guard <!-- 1631890 -->

- **Włącz przyspieszanie grafiki**: administratorzy mogą włączyć wirtualny procesor graficzny dla funkcji Windows Defender Application Guard. To ustawienie umożliwia procesorowi CPU przekazanie renderowania grafiki do procesora vGPU. Może to poprawić wydajność podczas pracy z witrynami internetowymi bogatymi w grafikę lub podczas oglądania filmu wideo znajdującego się w kontenerze.

- **Zapisywanie plików na hoście**: Administratorzy mogą włączyć przekazywanie plików z przeglądarki Microsoft Edge działającej w kontenerze do systemu plików hosta. Włączenie tej opcji pozwala użytkownikom na pobieranie plików z przeglądarki Microsoft Edge w kontenerze do systemu plików hosta.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Zasady ochrony funkcji zarządzania aplikacjami mobilnymi określane na podstawie stanu zarządzania <!-- 1665993 -->
Możliwe jest określanie zasad zarządzania aplikacjami mobilnymi na podstawie stanu zarządzania urządzenia:
- **Urządzenia z systemem Android** — możliwe jest określanie urządzeń niezarządzanych, urządzeń zarządzanych w usłudze Intune oraz zarządzanych w usłudze Intune profilów programu Android Enterprise (znanego wcześniej jako Android for Work).
- **Urządzenia z systemem iOS** — możliwe jest określanie urządzeń niezarządzanych (tylko dla funkcji zarządzania aplikacjami mobilnymi) lub urządzeń zarządzanych w usłudze Intune.

    > [!NOTE]
    > - W kwietniu 2018 wprowadzona zostanie obsługa systemu iOS dla tej funkcji.

Aby uzyskać więcej informacji, zobacz [Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Ulepszenia języka aplikacji w aplikacji Portal firmy dla systemu Windows <!-- 1683758 -->
Poprawiliśmy język w aplikacji Portal firmy dla systemu Windows 10, aby była ona bardziej przyjazna dla użytkownika i właściwa dla Twojej firmy. Aby wyświetlić niektóre przykładowe obrazy przedstawiające wprowadzone aktualizacje, zobacz [Co nowego w aplikacji interfejsu użytkownika](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Nowości w naszej dokumentacji dotyczące ochrony prywatności użytkowników <!-- 1440709 -->
W ramach dążenia do zapewnienia użytkownikom końcowym większej kontroli nad ich danymi i ochroną prywatności zostały opublikowane aktualizacje dotyczące naszej dokumentacji, w których opisano sposób wyświetlania i usuwania danych przechowywanych lokalnie przy użyciu aplikacji Portal firmy. Te aktualizacje można znaleźć w następujących artykułach:

- **Android**: [Jak usunąć urządzenie z systemem Android z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android (jeśli użytkownik odrzucił warunki użytkowania**: [Usuwanie urządzenia z zarządzania w przypadku odrzucenia warunków użytkowania](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Usuwanie urządzenia z systemem iOS z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Usuwanie urządzenia z systemem Windows z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>Tydzień od 19 marca 2018 r.

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Eksportowanie wszystkich urządzeń do plików CSV w przeglądarce IE, Edge lub Chrome <!-- 2258071 -->
W obszarze **Urządzenia** > **Wszystkie urządzenia** możesz **wyeksportować** urządzenia do sformatowanej listy w pliku CSV. Użytkownicy przeglądarki Internet Explorer (IE) posiadający ponad 10 000 urządzeń mogą pomyślnie wyeksportować swoje urządzenia do wielu plików. Każdy plik może zawierać maksymalnie 10 000 urządzeń.

Użytkownicy przeglądarek Edge i Chrome posiadający ponad 30 000 urządzeń mogą pomyślnie wyeksportować swoje urządzenia do wielu plików. Każdy plik może zawierać maksymalnie 30 000 urządzeń.

Funkcja [zarządzania urządzeniami](device-management.md) zawiera bardziej szczegółowe informacje dotyczące działań, które można wykonać względem zarządzanych urządzeń.

## <a name="week-of-march-12-2018"></a>Tydzień od 12 marca 2018 r.

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->

Korzystając z usługi Azure Active Directory (Azure AD), można teraz ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure. Aby uzyskać dodatkowe informacje, zobacz [Access controls in Azure Active Directory conditional access (Elementy kontroli dostępu dla dostępu warunkowego w usłudze Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aktualizacje wizualne aplikacji Portal firmy dla systemu Android <!--976944 -->

Zaktualizowaliśmy aplikację Portal firmy dla systemu Android, aby była zgodna z wytycznymi [Material Design](https://material.io/) systemu Android. Obrazy nowych ikon możesz zobaczyć w artykule [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nowe ustawienia funkcji Windows Defender Exploit Guard <!-- 1631893 -->

Udostępniono sześć nowych ustawień funkcji <strong>Zmniejszenie obszaru ataków</strong> oraz rozszerzono możliwości funkcji <strong>Kontrolowany dostęp do folderów: Ochrona folderów</strong>. Te ustawienia można znaleźć w obszarze: Konfiguracja urządzenia\Profile\
Utwórz profil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków

|Nazwa ustawienia  |Opcje ustawienia  |Opis  |
|---------|---------|---------|
|Zaawansowana ochrona przed oprogramowaniem wymuszającym okup|Włączone, Inspekcja, Nieskonfigurowane|Użyj agresywnej ochrony przed oprogramowaniem wymuszającym okup.|
|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows|Włączone, Inspekcja, Nieskonfigurowane|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe).|
|Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI.|
|Niezaufane i niepodpisane procesy uruchamiane z dysku USB|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB.|
|Pliki wykonywalne, które nie spełniają kryteriów występowania, wieku lub listy zaufanych|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj uruchamianie plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych.|

#### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

|              Nazwa ustawienia               |                                                              Opcje ustawienia                                                              | Opis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrona folderów (już zaimplementowano) | Nieskonfigurowane, Włączone, Tylko inspekcja (już zaimplementowano)<br><br> <strong>Nowe</strong><br>Blokuj modyfikację dysku, Inspekcja modyfikacji dysku |             |

Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.<br><br>**Włącz**: zapobiegaj modyfikowaniu i usuwaniu plików w folderach chronionych oraz zapisywaniu danych w sektorach dysku przez niezaufane aplikacje.<br><br>
**Blokuj tylko modyfikowanie dysku**:<br>Blokuj zapisywanie danych w sektorach dysku przez niezaufane aplikacje. Niezaufane aplikacje nadal mogą modyfikować i usuwać pliki w folderach chronionych.

## <a name="week-of-february-19-2018"></a>Tydzień od 19 lutego 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 -->

Usługa Intune obsługuje teraz rejestrowanie urządzeń z maksymalnie 100 różnymi kontami usług [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) i [Apple School Manager](apple-school-manager-set-up-ios.md). Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Wyświetlanie ograniczeń rejestracji dla poszczególnych użytkowników <!-- 1634444 eeready wnready -->
W bloku **Rozwiązywanie problemów** możesz teraz wyświetlić [ograniczenia rejestracji](enrollment-restrictions-set.md) obowiązujące poszczególnych użytkowników, wybierając pozycję **Ograniczenia rejestracji** z listy **Przypisania**.

### <a name="device-management"></a>Zarządzanie urządzeniami
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Raporty dotyczące stanu zagrożenia i stanu kondycji programu Windows Defender <!--854704 -->

Zrozumienie stanu i kondycji programu Windows Defender ma kluczowe znaczenie w zarządzaniu komputerami z systemem Windows.  Dzięki tej aktualizacji usługa Intune dodaje nowe raporty i akcje do stanu i kondycji agenta programu Windows Defender. Za pomocą zbiorczego raportu stanu w obciążeniu [Zgodność urządzenia](compliance-policy-monitor.md) można wyświetlić urządzenia, dla których trzeba wykonać jedną z następujących czynności:
- Aktualizacja sygnatur
- Uruchom ponownie
- Ręczna interwencja
- Pełne skanowanie
- Inne stany agentów, które wymagają interwencji

Raport szczegółowy dla każdej kategorii stanu zawiera listę poszczególnych komputerów osobistych, które wymagają uwagi, lub takich, których stan jest zgłaszany jako **Czysty**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nowe ustawienia prywatności dla ograniczeń urządzenia <!--1308926 -->
Dla urządzeń dostępne są teraz [dwa nowe ustawienia prywatności](device-restrictions-windows-10.md#privacy):
- **Publikuj działania użytkownika**: ustaw tę pozycję na wartość **Blokuj**, aby uniemożliwić udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań.
- **Tylko działania lokalne**: ustaw tę pozycję na wartość **Blokuj**, aby uniemożliwić udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań jedynie na podstawie działań lokalnych.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nowe ustawienia przeglądarki Microsoft Edge <!--1469166 -->
Dla urządzeń z przeglądarką Microsoft Edge są dostępne [dwa nowe ustawienia](device-restrictions-windows-10.md#edge-browser): **Ścieżka do pliku ulubionych** i **Zmiany w ulubionych**.

### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Wyjątki protokołu dla aplikacji <!--1035509 -->

W zasadach transferu danych funkcji zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune można teraz tworzyć wyjątki, aby umożliwiać korzystanie z określonych aplikacji niezarządzanych. Takie aplikacje muszą być uznane za zaufane przez dział IT. Poza utworzonymi wyjątkami transfer danych nadal jest ograniczony do aplikacji, które są zarządzane przez usługę Intune, gdy zasady transferu danych mają ustawienie **Tylko aplikacje zarządzane**. Ograniczenia można tworzyć za pomocą protokołów (system iOS) lub pakietów (system Android).

Na przykład można dodać pakiet Webex jako wyjątek do zasad transferu danych MAM. Pozwoli to na otwieranie linków Webex w wiadomości e-mail zarządzanego programu Outlook bezpośrednio w aplikacji Webex. Transfer danych będzie w dalszym ciągu ograniczony w innych aplikacjach niezarządzanych. Aby uzyskać więcej informacji, zobacz [Wyjątki od zasad przesyłania danych dla aplikacji](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dane zaszyfrowane przy użyciu funkcji Windows Information Protection (WIP) w wynikach wyszukiwania systemu Windows <!-- 1469193 -->
Ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia teraz kontrolowanie, czy dane zaszyfrowane przy użyciu funkcji WIP będą uwzględniane w wynikach wyszukiwania systemu Windows. Ustaw tę opcję zasad ochrony aplikacji, wybierając pozycję **Zezwalaj indeksatorowi programu Microsoft Windows Search na wyszukiwanie zaszyfrowanych elementów** w obszarze **Ustawienia zaawansowane** zasad funkcji Windows Information Protection. Zasady ochrony aplikacji muszą być ustawione na platformę systemu *Windows 10*, a zasady aplikacji **Stan rejestracji** muszą być ustawione na wartość **Z rejestracją**. Aby uzyskać więcej informacji, zobacz [Zezwalanie indeksatorowi programu Microsoft Windows Search na wyszukiwanie zaszyfrowanych elementów](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurowanie mobilnej aplikacji MSI korzystającej z samoaktualizacji <!-- 1740840 -->
Znaną mobilną aplikację MSI, która korzysta z samoaktualizacji, można skonfigurować tak, aby ignorowała proces sprawdzania wersji. Ta możliwość jest przydatna, aby uniknąć sytuacji wyścigu. Sytuacja wyścigu może wystąpić na przykład wtedy, gdy aplikacja jest automatycznie aktualizowana przez dewelopera, a równocześnie jest aktualizowana przez usługę Intune. Obie aktualizacje mogą próbować wymusić na kliencie systemu Windows daną wersję aplikacji, co może powodować konflikt. W przypadku tych automatycznie aktualizowanych aplikacji MSI możesz skonfigurować ustawienie **Ignoruj wersję aplikacji** w bloku **Informacje o aplikacji**. Gdy to ustawienie zostanie przełączone na wartość **Tak**, usługa Microsoft Intune będzie ignorować wersję aplikacji zainstalowanej na kliencie systemu Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Powiązane zestawy licencji aplikacji obsługiwane w usłudze Intune <!-- 1864117 -->
Usługa Intune w witrynie Azure Portal obsługuje teraz powiązane zestawy licencji aplikacji jako jeden element aplikacji w interfejsie użytkownika. Ponadto wszelkie aplikacje licencjonowane w trybie offline synchronizowane ze sklepem Microsoft Store dla Firm zostaną skonsolidowane w jeden wpis aplikacji i wszelkie szczegóły wdrożenia z indywidualnych pakietów zostaną migrowane do tego pojedynczego wpisu. Aby wyświetlić powiązane zestawy licencji aplikacji w witrynie Azure Portal, wybierz pozycję **Licencje aplikacji** w bloku **Aplikacje klienckie**.

### <a name="device-configuration"></a>Konfiguracja urządzenia
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Rozszerzenia plików funkcji Windows Information Protection (WIP) do automatycznego szyfrowania <!-- 1463582 -->
Ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia teraz określenie, które rozszerzenia mają być automatycznie szyfrowane podczas kopiowania danych z udziału bloków komunikatu serwera (SMB) w obrębie firmy, jak określono w zasadach funkcji WIP.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Konfigurowanie ustawień kont zasobów dla urządzeń Surface Hub

Ustawienia kont zasobów dla urządzeń Surface Hub można teraz konfigurować zdalnie.

Konto zasobu jest używane przez urządzenie Surface Hub do uwierzytelniania względem programu Skype/Exchange, co pozwala przyłączyć je do spotkania.
Zaleca się utworzenie unikatowego konta zasobu, aby urządzenie Surface Hub było wyświetlane w ramach spotkania jako sala konferencyjna.
Na przykład konto zasobu takie jak **Sala konferencyjna B41/6233**.

> [!NOTE]
> - Jeśli pozostawisz puste pola, spowoduje to zastąpienie atrybutów skonfigurowanych wcześniej na urządzeniu.
>
> - Właściwości konta zasobu mogą się dynamicznie zmieniać na urządzeniu Surface Hub. Jeśli na przykład rotacja hasła jest włączona. W związku z tym możliwe jest, że minie trochę czasu, zanim wartości w konsoli platformy Azure będą odzwierciedlać rzeczywiste wartości na urządzeniu.
>
>   Aby poznać bieżącą konfigurację na urządzeniu Surface Hub, informacje o koncie zasobu mogą zostać uwzględnione w spisie sprzętu (który jest już wykonywany z 7-dniowym interwałem) lub jako właściwości tylko do odczytu. Aby poprawić dokładność danych po przeprowadzeniu akcji zdalnej, można pobrać stan parametrów natychmiast po wykonaniu akcji w celu zaktualizowania konta/parametrów na urządzeniu Surface Hub.


##### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków


|Nazwa ustawienia  |Opcje ustawienia  |Opis  |
|---------|---------|---------|
|Wykonywanie chronionej hasłem zawartości wykonywalnej z wiadomości e-mail|Blokuj, Inspekcja, Nieskonfigurowane|Nie zezwalaj na uruchamianie chronionych hasłem plików wykonywalnych pobranych z poczty e-mail.|
|Zaawansowana ochrona przed oprogramowaniem wymuszającym okup|Włączone, Inspekcja, Nieskonfigurowane|Użyj agresywnej ochrony przed oprogramowaniem wymuszającym okup.|
|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows|Włączone, Inspekcja, Nieskonfigurowane|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe).|
|Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI.|
|Niezaufane i niepodpisane procesy uruchamiane z dysku USB|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB.|
|Pliki wykonywalne, które nie spełniają kryteriów występowania, wieku lub listy zaufanych|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj uruchamianie plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych.|

##### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

|              Nazwa ustawienia               |                                                              Opcje ustawienia                                                              | Opis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrona folderów (już zaimplementowano) | Nieskonfigurowane, Włączone, Tylko inspekcja (już zaimplementowano)<br><br> <strong>Nowe</strong><br>Blokuj modyfikację dysku, Inspekcja modyfikacji dysku |             |

Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.<br><br>**Włącz**: zapobiegaj modyfikowaniu i usuwaniu plików w folderach chronionych oraz zapisywaniu danych w sektorach dysku przez niezaufane aplikacje.<br><br>
**Blokuj tylko modyfikowanie dysku**:<br>Blokuj zapisywanie danych w sektorach dysku przez niezaufane aplikacje. Niezaufane aplikacje nadal mogą modyfikować i usuwać pliki w folderach chronionych.

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Dodatki do ustawień zabezpieczeń systemu dla zasad zgodności systemu Windows 10 lub nowszego <!--1704133-->

Dostępne są teraz dodatki do ustawień zgodności systemu Windows 10, w tym możliwość wymagania zapory oraz programu antywirusowego Windows Defender.


### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach
### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Obsługa aplikacji offline ze Sklepu Microsoft dla Firm <!--1222672-->
Aplikacje offline zakupione w Sklepie Microsoft dla Firm są teraz synchronizowane z witryną Azure Portal. Można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, nie przez sklep.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Uniemożliwianie użytkownikom końcowym ręcznego dodawania i usuwania kont w profilu służbowym <!-- 1728700 -->

Podczas wdrażania aplikacji usługi Gmail w profilu programu Android for Work można teraz uniemożliwić użytkownikom końcowym ręczne dodawanie i usuwanie kont w profilu służbowym przy użyciu ustawienia **Dodawanie i usuwanie kont** w profilu ograniczeń programu Android for Work.

## <a name="week-of-february-5-2018"></a>Tydzień od 5 lutego 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nowa opcja uwierzytelniania użytkownika na potrzeby rejestracji zbiorczej firmy Apple <!-- 747625 eeready -->

> [!NOTE]
> Dla nowych dzierżawców jest to widoczne od razu. W przypadku istniejących dzierżaw wdrażanie tej funkcji potrwa do końca kwietnia. Do czasu ukończenia tego procesu możesz nie mieć dostępu do tych nowych funkcji.

Usługa Intune zapewnia teraz możliwość uwierzytelniania urządzeń przy użyciu aplikacji Portal firmy dla następujących metod rejestracji:

- Program Device Enrollment Program firmy Apple
- Apple School Manager
- Rejestracja programu Apple Configurator

Korzystając z opcji obejmującej Portal firmy, można wymusić uwierzytelnianie wieloskładnikowe usługi Azure Active Directory bez blokowania tych metod rejestracji.

W przypadku użycia opcji obejmującej Portal firmy usługa Intune pomija uwierzytelnianie użytkownika w Asystencie ustawień systemu iOS w celu rejestracji koligacji użytkownika. Oznacza to, że urządzenie zostaje początkowo zarejestrowane jako urządzenie bez użytkownika, dlatego nie otrzymuje konfiguracji ani zasad dotyczących grup użytkowników. Otrzymuje tylko konfiguracje i zasady dotyczące grup urządzeń. Jednak usługa Intune automatycznie zainstaluje aplikację Portal firmy na urządzeniu. Pierwszy użytkownik, który uruchomi aplikację Portal firmy i zaloguje się w niej, zostanie skojarzony z urządzeniem w usłudze Intune. Użytkownik otrzyma wówczas konfiguracje i zasady dotyczące grup użytkowników. Skojarzenia z użytkownikiem nie można zmienić bez ponownego wykonania rejestracji.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 eeready -->

Usługa Intune obsługuje teraz rejestrowanie urządzeń z maksymalnie 100 różnych kont usług Apple Device Enrollment Program (DEP) i Apple School Manager. Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Drukowanie zdalne za pośrednictwem sieci zabezpieczonej <!-- 1709994  -->
Rozwiązania bezprzewodowego drukowania mobilnego PrinterOn umożliwią użytkownikom drukowanie zdalne z dowolnego miejsca i w dowolnym czasie za pośrednictwem sieci zabezpieczonej. Rozwiązania PrinterOn będą zintegrowane z zestawem Intune APP SDK dla systemów iOS i Android. Możliwe będzie określenie zasad ochrony aplikacji dla danej aplikacji przy użyciu bloku **Zasady ochrony aplikacji** usługi Intune w konsoli administratora. Użytkownicy końcowi będą mogli pobrać aplikację „PrinterOn for Microsoft” za pośrednictwem sklepu Play lub iTunes i używać jej w środowisku usługi Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Obsługa rejestracji, które używają menedżera rejestracji urządzeń, w aplikacji Portal firmy dla systemu macOS <!-- 1352411 -->

Użytkownicy mogą teraz używać menedżera rejestracji urządzeń podczas rejestrowania za pomocą aplikacji Portal firmy dla systemu macOS.

## <a name="week-of-january-29-2018"></a>Tydzień od 29 stycznia 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną<!-- 1639263 -->
Strona przeglądu zawiera teraz alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną. Kliknięcie alertu dotyczącego pojedynczego tokenu spowoduje przejście do strony szczegółów tokenu.  Po kliknięciu alertu dotyczącego wielu tokenów nastąpi przejście do listy wszystkich tokenów z informacjami o ich stanie. Administratorzy powinni odnawiać tokeny przed datą wygaśnięcia.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Zdalna obsługa polecenia wymazywania dla urządzeń z systemem macOS <!-- 1438084 -->

Administratorzy mogą zdalnie wydać polecenie „Erase” („Wymaż”) dla urządzeń z systemem macOS.

> [!IMPORTANT]
> Polecenia wymazywania nie można cofnąć, dlatego należy korzystać z niego z rozwagą.

Polecenie wymazywania powoduje usunięcie wszystkich danych, w tym systemu operacyjnego, z urządzenia. Powoduje również usunięcie urządzenia z zarządzania przy użyciu usługi Intune. Ostrzeżenie dla użytkownika nie jest wyświetlane i wymazywanie następuje natychmiast po wykonaniu polecenia.

Musisz skonfigurować 6-cyfrowy numer PIN odzyskiwania. Za pomocą tego numeru PIN można odblokować wymazane urządzenie, po czym rozpocznie się ponowna instalacja systemu operacyjnego. Po rozpoczęciu operacji wymazywania numer PIN jest wyświetlany na pasku stanu, w bloku przeglądu urządzenia w usłudze Intune. Numer PIN jest widoczny podczas całego procesu wymazywania. Po zakończeniu wymazywania urządzenie całkowicie znika z zarządzania w usłudze Intune. Należy pamiętać, aby zarejestrować numer PIN odzyskiwania, dzięki czemu osoba przywracająca urządzenie będzie mogła go użyć.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odwołanie licencji dla tokenu programu zakupów zbiorczych dla systemu iOS <!-- 820870 -->
Możesz odwołać licencję wszystkich aplikacji dla systemu iOS zakupionych w ramach programu zakupów zbiorczych (VPP) dla danego tokenu programu VPP.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odwołanie aplikacji dla systemu iOS zakupionych w ramach programu zakupów zbiorczych  <!-- 820863 -->
Dla danego urządzenia z zainstalowaną przynajmniej jedną aplikacją dla systemu iOS zakupioną w ramach programu zakupów zbiorczych (Volume-Purchase Program — VPP) możesz odwołać skojarzoną licencję aplikacji urządzenia dla tego urządzenia. Odwołanie licencji aplikacji nie spowoduje odinstalowania powiązanych aplikacji VPP z urządzenia. Aby odinstalować aplikację VPP, należy zmienić akcję przypisywania na **Odinstaluj**. Aby uzyskać więcej informacji, zobacz temat [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Przypisywanie aplikacji mobilnych usługi Office 365 do urządzeń z systemami iOS i Android przy użyciu wbudowanego typu aplikacji <!-- 1332318 -->
**Wbudowany** typ aplikacji ułatwia tworzenie aplikacji usługi Office 365 oraz ich przypisywanie do zarządzanych urządzeń z systemami iOS i Android. Są to na przykład aplikacje usługi 0365, takie jak Word, Excel, PowerPoint i OneDrive. Do typu aplikacji można przypisać określone aplikacje, a następnie zmodyfikować konfigurację informacji o aplikacji.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup <!-- 1406920 -->

Podczas przypisywania aplikacji i po wybraniu typu przypisania możesz wybrać grupy, które mają być dołączone, a także grupy, które mają zostać wykluczone.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Zasady konfiguracji aplikacji możesz przypisywać do grup, dołączając i wykluczając przypisania <!-- 1480316 -->

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników i urządzeń za pomocą kombinacji dołączania i wykluczania przypisań. Przypisania można wybrać jako niestandardowy wybór grup albo jako grupę wirtualną. Grupa wirtualna może obejmować **wszystkich użytkowników**, **wszystkie urządzenia** lub **wszystkich użytkowników i wszystkie urządzenia**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10 <!-- 903672(archived), 1119689 -->  
Możesz tworzyć zasady uaktualniania wersji systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wersji systemu Windows 10, zobacz artykuł [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zasady dostępu warunkowego dla usługi Intune są dostępne tylko w witrynie Azure Portal <!-- 1737088 1634311 -->

Począwszy od tego wydania, musisz konfigurować zasady dostępu warunkowego i zarządzać nimi w witrynie [Azure Portal](https://portal.azure.com) w bloku **Azure Active Directory** > **Dostęp warunkowy**. Dla wygody możesz przejść do tego bloku z usługi Intune w witrynie Azure Portal w obszarze **Intune** > **Dostęp warunkowy**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizacje wiadomości e-mail dotyczących zgodności <!--1637547 -->

Wiadomość e-mail wysłana w celu zgłoszenia niezgodnego urządzenia zawiera szczegóły dotyczące niezgodnego urządzenia.


## <a name="week-of-january-22-2018"></a>Tydzień od 22 stycznia 2018 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nowa funkcja akcji „Rozwiąż” dla urządzeń z systemem Android <!--1583480-->

Aplikacja Portal firmy dla systemu Android rozwija akcję „Rozwiąż” dla pozycji **Zaktualizuj ustawienia urządzenia**, aby rozwiązać [problemy dotyczące szyfrowania urządzenia](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Zdalne blokowanie dostępne w aplikacji Portal firmy dla systemu Windows 10 <!--676506-->
Użytkownicy końcowi mogą teraz zdalnie blokować swoje urządzenia w aplikacji Portal firmy dla systemu Windows 10. Opcja nie będzie wyświetlana dla wybranego urządzenia lokalnego, którego aktywnie używają.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Łatwiejsze rozwiązywanie problemów ze zgodnością aplikacji Portal firmy dla systemu Windows 10<!--676546-->
Użytkownicy końcowi mający urządzenia z systemem Windows będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem.

## <a name="week-of-december-11-2017"></a>Tydzień 11 grudnia 2017 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nowe ustawienie automatycznego ponownego wdrażania<!-- 1469168 -->
Ustawienie **Automatyczne ponowne wdrażanie** pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania. To ustawienie można znaleźć w obszarze Windows 10 > Ograniczenia dotyczące urządzeń > Ogólne > Automatyczne ponowne wdrażanie. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 w usłudze Intune](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Obsługa dodatkowych wersji źródła w zasadach uaktualniania wersji systemu Windows 10 <!-- 903672,  1119689 -->
Zasady uaktualniania wersji systemu Windows 10 umożliwiają teraz uaktualnianie dodatkowych wersji systemu Windows 10 (Windows 10 Pro, Windows 10 Pro for Education, Windows 10 Cloud itp.). Przed tą wersją obsługiwane ścieżki uaktualniania wersji były bardziej ograniczone. Więcej szczegółów znajduje się w temacie [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nowe ustawienia profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center (WDSC)<!-- 1335507 -->

Usługa Intune została wzbogacona o nową sekcję ustawień profilu konfiguracji urządzenia w obszarze Ochrona punktu końcowego o nazwie **Windows Defender Security Center**. Administratorzy informatyczni mogą skonfigurować to, do których filarów aplikacji Windows Defender Security Center użytkownicy końcowi mogą uzyskać dostęp. Jeśli administrator IT ukrywa filar w aplikacji Windows Defender Security Center, wszystkie powiadomienia powiązane z ukrytym filarem nie będą wyświetlane na urządzeniu użytkownika.

Poniżej wymieniono filary, które administratorzy mogą ukryć w ustawieniach profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center:
- Ochrona przed wirusami i zagrożeniami
- Wydajność i kondycja urządzenia
- Zapora i ochrona sieci
- Kontrola aplikacji i przeglądarki
- Opcje rodziny

Administratorzy IT mogą również dostosować to, które powiadomienia będą otrzymywać użytkownicy. Na przykład można określić, czy użytkownicy będą otrzymywać wszystkie powiadomienia generowane w ramach widocznych filarów w aplikacji WDSC, czy tylko powiadomienia krytyczne. Powiadomienia niekrytyczne obejmują okresowe podsumowania działania programu antywirusowego Windows Defender i powiadomienia po zakończeniu skanowania. Wszystkie pozostałe powiadomienia są traktowane jako krytyczne. Ponadto można również dostosować zawartość powiadomień, na przykład można podać informacje kontaktowe do działu IT do osadzenia w powiadomieniach wyświetlanych na rządzeniach użytkowników.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Obsługa wielu łączników na potrzeby obsługi certyfikatów protokołu SCEP i PFX <!-- 1361755 -->

Klienci, którzy korzystają z lokalnego łącznika usługi NDES w celu dostarczania certyfikatów do urządzeń, mogą teraz skonfigurować wiele łączników w jednej dzierżawie.

Ta nowa możliwość obsługuje następujący scenariusz:

- **Wysoka dostępność**

Każdy łącznik usługi NDES ściąga żądania certyfikatu z usługi Intune.  Jeśli jeden łącznik usługi NDES przejdzie do trybu offline, inny łącznik może dalej przetwarzać żądania.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Nazwa podmiotu klienta może zawierać zmienną AAD_DEVICE_ID <!-- 1468599 -->

Tworząc profil certyfikatu SCEP w usłudze Intune, można teraz użyć zmiennej AAD_DEVICE_ID podczas kompilowania niestandardowej nazwy podmiotu.   Gdy żądanie certyfikatu jest przesyłane przy użyciu tego profilu SCEP, zmienna jest zastępowana identyfikatorem urządzenia usługi AAD należącym do urządzenia wysyłającego żądanie certyfikatu.


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Zarządzanie urządzeniami z systemem macOS zarejestrowanymi w programie Jamf przy użyciu aparatu zgodności urządzenia usługi Intune <!-- 1592747 -->
Korzystając z programu Jamf, można teraz wysyłać informacje o stanie urządzenia z systemem macOS do usługi Intune, która następnie oceni je pod kątem zgodności z zasadami określonymi w konsoli usługi Intune. W oparciu o stan zgodności urządzenia, a także pozostałe warunki (takie jak lokalizacja, ryzyko związane z użytkownikiem itp.) dostęp warunkowy będzie wymuszać zgodność dla urządzeń z systemem macOS uzyskujących dostęp do chmury i lokalnych aplikacji połączonych z usługą Azure Active Directory oraz usługą Office 365. Dowiedz się więcej o [konfigurowaniu integracji programu Jamf](conditional-access-integrate-jamf.md) i [wymuszaniu zgodności dla urządzeń zarządzanych przez program Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nowa akcja dotycząca urządzenia z systemem iOS <!-- 1424701 -->

Możliwe jest teraz zamykanie nadzorowanych urządzeń z systemem iOS 10.3. Ta akcja natychmiast wyłącza urządzenie bez ostrzeżenia dla użytkownika końcowego. Akcję **Wyłącz (tylko nadzorowane)** można znaleźć we właściwościach urządzenia po wybraniu urządzenia w obciążeniu **Urządzenie**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Blokowanie zmian daty/godziny na urządzeniach z systemem Samsung Knox<!-- 1468103 -->

Dodaliśmy nową funkcję, która pozwala na blokowanie zmian daty i godziny na urządzeniach z systemem Samsung Knox. Ta funkcja jest dostępna po wybraniu opcji **Profile konfiguracji urządzeń** > **Ograniczenia dotyczące urządzeń (Android)** > **Ogólne**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Obsługa konta zasobu Surface Hub <!-- 1566442  -->

Dodano nową akcję urządzenia, która umożliwia administratorom określanie i aktualizowanie konta zasobu skojarzonego z rozwiązaniem Surface Hub.

Konto zasobu jest używane przez rozwiązanie Surface Hub do uwierzytelniania w programie Skype/Exchange, co pozwala przyłączyć je do spotkania. Można utworzyć unikatowe konto zasobu, aby rozwiązanie Surface Hub było wyświetlane w spotkaniu jako sala konferencyjna. Na przykład konto zasobu może być widoczne jako *Sala konferencyjna B41/6233*. Konto zasobu (nazywane kontem urządzenia) dla rozwiązania Surface Hub zwykle trzeba skonfigurować dla lokalizacji sali konferencyjnej i gdy trzeba zmienić inne parametry konta zasobu.

Gdy administratorzy chcą zaktualizować konto zasobu na urządzeniu, muszą podać bieżące poświadczenia usługi Active Directory/Azure Active Directory skojarzone z tym urządzeniem. Jeśli dla urządzenia jest włączona funkcja rotacji haseł, administratorzy muszą przejść do usługi Azure Active Directory, aby znaleźć hasło.

> [!NOTE]
> Wszystkie pola są wysyłane w pakiecie i zastępują wszystkie pola skonfigurowane wcześniej. Puste pola również zastępują pola istniejące.

Poniżej przedstawiono ustawienia, które mogą skonfigurować administratorzy:

- **Konto zasobu**
   - **Użytkownik Active Directory**

      Nazwa_domeny\nazwa_użytkownika lub główna nazwa użytkownika (UPN): user@domainname.com

   - **Hasło**

- **Opcjonalne parametry konta zasobu** (trzeba je ustawić przy użyciu określonego konta zasobu)

   - **Okres rotacji hasła**

     Ze względów bezpieczeństwa zapewnia co tydzień automatyczną aktualizację hasła konta przez rozwiązanie Surface Hub. Aby skonfigurować jakiekolwiek parametry po włączeniu tej opcji, należy najpierw zresetować hasło konta w usłudze Azure Active Directory.

   - **Adres SIP (Session Initiation Protocol)**

     Używany tylko wtedy, gdy wykrywanie automatyczne zakończy się niepowodzeniem.

   - **Poczta e-mail**

     Adres e-mail konta urządzenia/zasobu.

   - **Serwer Exchange**

     Wymagany tylko wtedy, gdy wykrywanie automatyczne zakończy się niepowodzeniem.

   - **Synchronizacja kalendarza**

     Określa, czy jest włączona synchronizacja kalendarza oraz pozostałe usługi serwera Exchange. Na przykład: synchronizacja spotkania.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalacja aplikacji pakietu Office na urządzeniach z systemem macOS<!-- 1494311 -->
Można teraz instalować aplikacje pakietu Office na urządzeniach z systemem macOS. Ten nowy typ aplikacji umożliwi instalację programów Word, Excel, PowerPoint, Outlook i OneNote. Do aplikacji dołączony jest program Microsoft AutoUpdate (MAU), który pomaga zapewnić ich bezpieczeństwo i aktualność.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Usuwanie tokenu programu zakupów zbiorczych dla systemu iOS <!-- 820879 -->
Istnieje możliwość usunięcia tokenu programu Volume Purchasing Program (VPP) systemu iOS przy użyciu konsoli. Może to być konieczne w przypadku występowania zduplikowanych wystąpień tokenu programu VPP.

### <a name="intune-apps"></a>Aplikacje usługi Intune


### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nowa kolekcja jednostek o nazwie Bieżący użytkownik jest ograniczona do danych aktualnie aktywnych użytkowników <!-- 1667026 -->

Kolekcja jednostek **Users** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

Z kolei nowa kolekcja jednostek **Bieżący użytkownik** zawiera tylko tych użytkowników, którzy nie zostali usunięci. Kolekcja jednostek **Bieżący użytkownik** zawiera tylko aktualnie aktywnych użytkowników. Aby uzyskać informacje o kolekcji jednostek **bieżącego użytkownika**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Zaktualizowane interfejsy API programu Graph <!-- 1736360 -->

W tej wersji zaktualizowaliśmy kilka interfejsów API programu Graph dla usługi Intune, które są dostępne w wersji beta. Aby uzyskać więcej informacji, sprawdź miesięczny [dziennik zmian interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).

## <a name="week-of-december-4-2017"></a>Tydzień 4 grudnia 2017 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Usługa Intune obsługuje niedozwolone aplikacje rozwiązania Windows Information Protection <!-- 1479103 -->
Niedozwolone aplikacje można określić w usłudze Intune. Jeśli aplikacja zostanie ustawiona jako niedozwolona, nie może uzyskiwać dostępu do informacji firmowych. Jest to sytuacja odwrotna, co w przypadku listy dozwolonych aplikacji. Aby uzyskać więcej informacji, zobacz [Zalecana lista niedozwolonych aplikacji na potrzeby rozwiązania Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).



## <a name="notices"></a>Uwagi

### <a name="plan-for-change-new-intune-support-experience-for-premier-customers"></a>Planowana zmiana: nowe środowisko pomocy technicznej usługi Intune dla klientów wersji Premier 
Jako klient korzystający z pomocy technicznej Microsoft Premier możesz obecnie używać portalu Microsoft Premier Online (MPO) (premier.microsoft.com) oraz usługi Intune na platformie Azure (portal.azure.com) do tworzenia żądań pomocy technicznej dla usługi Intune. Od 3 grudnia 2018 r. żądania pomocy technicznej będzie można tworzyć tylko w usłudze Intune na platformie Azure, ponieważ kontynuujemy rozbudowę środowiska pomocy technicznej Premier.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po 3 grudnia nie będzie można tworzyć żądań pomocy technicznej w portalu MPO.  Po podjęciu takiej próby zobaczysz monit o przejście do usługi Intune na platformie Azure, którego nie będzie można odrzucić. W tym miejscu możesz utworzyć żądanie pomocy technicznej, które zostanie przekierowane do dedykowanego działu pomocy technicznej firmy Microsoft, który w odpowiednim czasie zdiagnozuje i rozwiąże problem. Żądań pomocy technicznej utworzonych w portalu MPO nie można wyświetlić w witrynie Azure Portal, dlatego nie należy już tworzyć żądań pomocy technicznej w portalu MPO.  

Jeśli korzystasz z hybrydowego oprogramowania do zarządzania urządzeniami mobilnymi (hybrydowe oprogramowanie MDM) lub współzarządzania, możesz nadal używać portalu MPO do tworzenia żądań pomocy technicznej dla programu ConfigMgr, ale żądania pomocy technicznej dla usługi Intune tworzyć w witrynie Azure Portal. Przypominamy, że hybrydowe zarządzanie urządzeniami mobilnymi jest przestarzałe i należy zaplanować jak najszybsze przejście do usługi Intune na platformie Azure. Aby uzyskać więcej informacji, zobacz artykuł dotyczący przechodzenia z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune na platformie Azure.

Zauważ, że tylko użytkownicy z rolami administratora globalnego, administratora usługi Intune i administratora pomocy technicznej usługi mogą tworzyć bilety pomocy technicznej w witrynie Azure Portal.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
- Nie korzystaj z portalu MPO, a do tworzenia wszystkich żądań pomocy technicznej usługi Intune i zarządzania nimi używaj usługi Intune na platformie Azure.  
- W razie potrzeby powiadom dział pomocy technicznej i zaktualizuj dokumentację.
- Jeśli użytkownicy bez ról administratora globalnego ani administratora usługi Intune aktualnie tworzą żądania pomocy technicznej w portalu MPO, przypisz im rolę administratora pomocy technicznej usługi Azure Active Directory, aby mogli nadal tworzyć bilety pomocy technicznej w witrynie Azure Portal.
- Kliknij pozycję Informacje dodatkowe, aby uzyskać więcej informacji i pomocne linki.

#### <a name="additional-information"></a>Dodatkowe informacje
[https://aka.ms/IntuneSupport_MPO_to_Azure](https://aka.ms/IntuneSupport_MPO_to_Azure)

### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Wymagana akcja: zaktualizuj ustawienia hasła zasad zgodności lub ograniczeń urządzenia z systemem Android w usłudze Intune
Usługa Intune będzie usuwać dostępny typ hasła „ustawienie domyślne urządzenia” dla systemu Android w wersji 4.4 i nowszej. Z powodu różnic między platformami Android i domyślnymi ustawieniami urządzeń ta zasada jest często traktowana jako opcjonalna przez urządzenie. Aby wyjaśnić nieporozumienia dotyczące wymuszania tego ustawienia w systemie Android, w przyszłym wydaniu usuniemy to ustawienie z interfejsu użytkownika. 
#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
- Jeśli chcesz wymagać hasła na urządzeniach, zalecamy, aby zamiast używania „ustawień domyślnych urządzenia” edytować profile platformy Android w celu jasnego określenia wymaganego typu hasła.
- Jeśli chcesz, aby to użytkownicy decydowali, czy tworzyć hasło, wybierz przycisk „Nieskonfigurowane”. Kiedy to ustawienie zostanie usunięte z interfejsu użytkownika, jeśli będzie ono nadal wybrane, zostanie wyświetlony monit o wybranie wartości innej niż „Ustawienia domyślne urządzenia” podczas kolejnej edycji profilu.
Co należy zrobić, aby przygotować się do tej zmiany?
Przejrzyj ustawienia dotyczące haseł w zasadach zgodności i ograniczeń urządzenia z systemem Android i Android dla firm. Znajdują się one w obszarze Zabezpieczenia systemu dla zasad zgodności oraz w obszarze Hasło urządzenia lub Ustawienia profilu służbowego dla ograniczeń urządzenia. Sekcja Dodatkowe informacje zawiera link do bardziej szczegółowych informacji i zrzutów ekranu przedstawiających, gdzie są konfigurowane te ustawienia.
####<a name="additional-information"></a>Dodatkowe informacje
https://aka.ms/PasswordSettings 

### <a name="plan-for-change-change-password-at-next-auth-added-to-intune---1873216---"></a>Planowanie zmian: dodano ustawienie Zmień hasło przy następnym uwierzytelnianiu do usługi Intune<!-- 1873216 -->
We wrześniowej wersji usługi Intune jest planowane zintegrowanie nowo udostępnionego przez firmę Apple ustawienia **Zmień hasło przy następnym uwierzytelnianiu** przeznaczonego dla urządzeń z systemem macOS w wersji 10.13 i nowszych. Przed wprowadzeniem tego ustawienia dostawcy rozwiązań MDM nie mogą zweryfikować, czy kod dostępu urządzenia został zmieniony na zgodny. Zasady konfiguracji i zgodności usługi Intune umożliwiają tylko zweryfikowanie, czy po następnej zmianie hasła urządzenia jest ono oznaczone jako zgodne. Po dodaniu tej nowej funkcji firmy Apple użytkownicy systemu macOS otrzymają żądanie aktualizacji hasła, nawet jeśli hasło jest zgodne.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Ma to wpływ na środowiska z zasadami urządzeń z systemem macOS korzystające z usługi Intune lub hybrydowego rozwiązania MDM. Teraz, gdy firma Apple udostępniła ustawienie **Zmień hasło przy następnym uwierzytelnianiu**, usługa Intune może wymusić na użytkownikach aktualizację haseł po wypchnięciu zasad haseł. Jeśli zablokujesz zasoby firmy aż do oznaczenia urządzenia jako zgodnego, użytkownicy końcowi mogą mieć zablokowany dostęp do zasobów firmy, takich jak wiadomości e-mail lub witryny programu SharePoint, do momentu zresetowania hasła. W przyszłości wszystkie aktualizacje zasad konfiguracji i zgodności haseł będą wymuszać na uwzględnionych użytkownikach zaktualizowanie haseł.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poinformuj dział pomocy technicznej w swojej firmie. Jeśli nie chcesz wymuszać tych zasad urządzeń z systemem macOS, zalecamy anulowanie przypisania lub usunięcie istniejących zasad systemu macOS. Badania wśród klientów sugerują, że większości z nich ta zmiana nie dotyczy. Większość użytkowników końcowych aktualizuje hasło po odebraniu żądania rejestracji przy użyciu hasła lub zresetowania hasła w celu zachowania zgodności.


### <a name="plan-for-change-intune-moving-to-support-ios-10-and-later-in-september----2454656---"></a>Planowanie zmian: w usłudze Intune nastąpi przejście do obsługi systemu iOS 10 i nowszych wersji we wrześniu <!-- 2454656 -->
Oczekuje się, że firma Apple wyda system iOS 12. Wkrótce po wydaniu przeniesiemy rejestrację w usłudze Intune, aplikację Portal firmy oraz program Managed Browser do obsługi systemu iOS 10 i jego nowszych wersji.  

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?  
Aplikacje mobilne usługi Office 365 są obsługiwane w systemie iOS 10 i nowszych wersji, więc może masz już uaktualniony system operacyjny lub urządzenia. Jeśli tak, to przeniesienie nie wpłynie na Ciebie.  

Jednak jeśli masz dowolne z wymienionych poniżej urządzeń lub chcesz zarejestrować dowolne z wymienionych poniżej urządzeń, pamiętaj, że obsługują one tylko system iOS 9 i jego wcześniejsze wersje.  Aby nadal korzystać z aplikacji Portal firmy usługi Intune, do września musisz uaktualnić te urządzenia do urządzeń obsługujących system iOS 10 lub nowszy:  

* iPhone 4S  
* iPod Touch  
* iPad 2  
* iPad (3. generacja)  
* iPad Mini (1. generacja)  

Od lipca urządzenia zarejestrowane w usłudze MDM z systemem iOS 9 i aplikacją Portal firmy będą otrzymywać monit o uaktualnienie systemu operacyjnego lub urządzenia. Jeśli używasz zasad ochrony aplikacji, możesz również zdefiniować ustawienie dostępu „Wymagaj minimalnej wersji systemu operacyjnego iOS (tylko ostrzeżenie)”.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?   
Sprawdź, których urządzeń lub użytkowników w Twojej organizacji ta zmiana dotyczy. W usłudze Intune w witrynie Azure Portal przejdź do pozycji Urządzenia > Wszystkie urządzenia i filtruj zawartość według systemu operacyjnego.  Kliknij pozycję Kolumny, aby wyświetlić szczegóły, takie jak wersja systemu operacyjnego. Poproś użytkowników, aby do września uaktualnili urządzenia do obsługiwanej wersji systemu operacyjnego.  

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Planowanie zmian: usługa Intune przechodzi na protokół TLS 1.2
Poczynając od 31 października 2018 r., usługa Intune będzie obsługiwać protokół TLS (Transport Layer Security) w wersji 1.2, aby zapewnić najlepsze w swojej klasie szyfrowanie, zagwarantować, że nasza usługa będzie domyślnie bezpieczniejsza, oraz dopasować ją do innych usług firmy Microsoft, takich jak Microsoft Office 365. Usługa Office poinformowała o tej zmianie w komunikacie MC128929.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Od 31 października 2018 r. usługa Intune już nie będzie obsługiwać protokołu TLS w wersjach 1.0 i 1.1. Wszystkie kombinacje klient-serwer i serwer-przeglądarka powinny używać protokołu TLS w wersji 1.2, aby zapewnić bezproblemowe połączenia z usługą Intune. Należy pamiętać, że ta zmiana będzie miała wpływ na urządzenia użytkowników końcowych, które nie są już obsługiwane przez usługę Intune, ale nadal odbierają zasady za pomocą usługi Intune i nie mogą korzystać z protokołu TLS w wersji 1.2. Obejmuje to urządzenia, na których działa system Android 4.3 lub starszy. Aby uzyskać listę objętych urządzeń i przeglądarek, zobacz poniższe informacje dodatkowe.

Jeśli po 31 października 2018 r. wystąpi problem związany z używaniem starszej wersji protokołu TLS, konieczna będzie aktualizacje do protokołu TLS 1.2 lub do urządzenia obsługującego protokół TLS 1.2 w ramach rozwiązania.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Zalecamy aktywne usunięcie zależności protokołu TLS 1.0 i 1.1 w swoich środowiskach oraz wyłączenie protokołu TLS 1.0 i 1.1 na poziomie systemu operacyjnego, jeśli to możliwe. Już dziś zacznij planowanie migracji do protokołu TLS 1.2. Sprawdź wpis w blogu na temat obsługi technicznej poniżej, gdzie znajduje się lista urządzeń, które dziś nie są obsługiwane przez usługę Intune, ale mogą nadal otrzymywać zasady, i które nie będą mogły nawiązać połączenia przy użyciu protokołu TLS w wersji 1.2. Może być konieczne powiadomienie tych użytkowników końcowych, że utracą oni dostęp do zasobów firmy.

**Dodatkowe informacje**: [Intune moving to TLS 1.2 for encryption (Przechodzenie do protokołu TLS 1.2 z powodu szyfrowania)](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Planowanie zmian: zmiany w obsłudze wtyczki zestawu SDK aplikacji usługi Microsoft Intune dla oprogramowania Cordova
Usługa Intune kończy obsługę [wtyczki zestawu Microsoft Intune App SDK dla oprogramowania Cordova](app-sdk-cordova.md) z dniem 1 maja 2018 r. W zamian zalecamy używanie dostępnego w usłudze Intune narzędzia opakowującego aplikacje, aby przygotować swoje aplikacje oparte na oprogramowaniu Cordova do zapewnienia zarządzania i dostępności w usłudze Intune. Gdy ta zmiana zacznie obowiązywać, wtyczka zestawu Microsoft Intune App SDK dla oprogramowania Cordova nie będzie już utrzymywana ani nie będzie otrzymywać aktualizacji. Deweloperzy aplikacji nie będą mogli używać tej wtyczki. Usługa Intune planuje kontynuowanie obsługi aplikacji skompilowanych przy użyciu oprogramowania Cordova. Jednak wszelkie aplikacje skompilowane z użyciem wtyczki zestawu Microsoft Intune App SDK dla oprogramowania Cordova będą miały ograniczoną funkcjonalność w usłudze Intune. Po opakowaniu za pomocą dostępnego w usłudze Intune narzędzia opakowującego aplikacje można wdrożyć aplikacje dla użytkowników końcowych w zwykły sposób. W przypadku aplikacji systemu Android opartych na oprogramowaniu Cordova, które są publikowane w sklepie Google Play:
- Użytkownicy końcowi zostaną poproszeni o podanie poświadczeń, aby uzyskać zasady usługi Intune przy pierwszym uruchomieniu.
- Aplikacje powinny zostać opublikowane w sklepie z aplikacjami przeznaczonym dla użytkowników usługi Intune, na przykład „Contoso App for Intune”.

Aby uzyskać więcej informacji o narzędziu do opakowywania aplikacji, zobacz [Narzędzie opakowujące aplikacje dla systemu iOS](app-wrapper-prepare-ios.md) i [Narzędzie opakowujące aplikacje dla systemu Android](app-wrapper-prepare-android.md). Wszelkie problemy lub pytania należy zgłaszać na adres [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com).

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Planowanie zmian: już teraz zacznij zarządzać urządzeniami przenośnymi za pomocą usługi Intune na platformie Azure <!-- 1227338 -->
Ponad rok temu ogłosiliśmy [publiczną wersję zapoznawczą usługi Intune na platformie Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/), a sześć miesięcy temu opublikowaliśmy [ogólnie dostępną wersję nowego środowiska pracy administratora](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) dla usługi Intune. 31 sierpnia 2018 r. wyłączymy funkcję zarządzania urządzeniami przenośnymi w klasycznej konsoli programu Silverlight dla klientów korzystających z autonomicznej usługi Intune. Zamiast tego na potrzeby zarządzania urządzeniami przenośnymi można używać [usługi Intune na platformie Azure](https://aka.ms/Intune_on_Azure). Jeśli nadal używasz konsoli klasycznej do zarządzania urządzeniami przenośnymi, zapoznaj się z usługą Intune na platformie Azure. Ta zmiana nie powinna mieć żadnego wpływu na użytkowników końcowych. Program Silverlight będzie nadal umożliwiał zarządzanie komputerami klasycznymi. Więcej informacji na temat tej zmiany i jej wpływu na Ciebie znajduje się [tutaj](https://aka.ms/Intune_on_Azure_mdm).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 roku wymagają przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Jeśli istniejące konto nie ma dostępu do witryny Azure Portal, zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska.

## <a name="whats-coming"></a>Wkrótce

### <a name="local-device-security-option-settings----1251887---"></a>Ustawienia opcji zabezpieczeń urządzenia lokalnego <!-- 1251887 -->
Na urządzeniach z systemem Windows 10 będzie można włączać ustawienia zabezpieczeń przy użyciu nowych ustawień opcji zabezpieczeń urządzenia lokalnego. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Aktualizacja nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968-->

W sierpniu wprowadzimy nowe środowisko witryny internetowej Portal firmy zawierające aktualizacje interfejsu użytkownika, usprawnione przepływy pracy i ulepszone ułatwienia dostępu. Będzie ono obejmować ulepszenia oparte na potrzebach klientów, takie jak udostępnianie aplikacji i lepsza ogólna wydajność, które zapewnią użytkownikom większy komfort pracy.
Na podstawie opinii klientów dodaliśmy nowe funkcje, które znacznie udoskonalą istniejącą funkcjonalność i użyteczność:

* Ulepszenia interfejsu użytkownika w całej witrynie internetowej
* Możliwość udostępniania bezpośrednich linków do aplikacji
* Zwiększona wydajność dużych wykazów aplikacji

Nie musisz niczego robić, aby przygotować się do tej zmiany. Powiadomimy Cię, gdy zaktualizowana witryna internetowa Portal firmy będzie dla Ciebie dostępna. Może być jednak konieczne zaktualizowanie zrzutów ekranu w dokumentach użytkownika końcowego. Pamiętaj, że może być też konieczne zaktualizowanie dokumentacji dla aplikacji Portal firmy w systemie iOS, ponieważ witryna internetowa obsługuje sekcję **Aplikacje** aplikacji systemu iOS. Przykładowy obraz jest widoczny na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. W naszym [blogu pomocy technicznej usługi Intune](https://aka.ms/compportalats) będziemy umieszczać szczegółowe informacje.



## <a name="see-also"></a>Zobacz też
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/cloud-platform/roadmap)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
