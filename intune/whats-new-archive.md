---
title: Nowości w poprzednich miesiącach w usłudze Microsoft Intune — platforma Azure | Microsoft Docs
titleSuffix: ''
description: Przejrzyj starsze powiadomienia o nowościach w usłudze Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/25/2019
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8df4a1d7f929301c11f577a9b7e50ef1647dda11
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423717"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Nowości w usłudze Microsoft Intune — poprzednie miesiące

[!INCLUDE [azure_portal](./includes/azure_portal.md)]


<!-- ########################## -->
## <a name="september-2018"></a>Wrzesień 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Usunięto duplikowanie kafelków stanu ochrony aplikacji <!-- 3083391 -->
Kafelki **Stan użytkownika dla systemu iOS** i **Stan użytkownika dla systemu Android** znajdowały się zarówno na stronie **Aplikacje klienckie — Przegląd**, jak i na stronie **Aplikacje klienckie — Stan ochrony aplikacji**. Kafelki stanu zostały usunięte ze strony **Aplikacje klienckie — Przegląd**, aby uniknąć ich duplikowania. 

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Obsługa dodatkowych urzędów certyfikacji innych firm <!-- 3093107 -->
Przy użyciu prostego protokołu rejestrowania certyfikatów (SCEP) możesz teraz wystawiać nowe certyfikaty i odnawiać certyfikaty na urządzeniach przenośnych z systemami Windows, iOS, Android i macOS.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Usługa Intune teraz obsługuje system iOS 10 i nowsze <!-- 2454656 -->  
Rejestracja w usłudze Intune, aplikacja Portal firmy i program Managed Browser teraz obsługują tylko urządzenia systemu iOS z systemem iOS 10 lub nowszym. Aby sprawdzić, czy dotyczy to urządzeń lub użytkowników w Twojej organizacji, przejdź do usługi Intune w witrynie Azure Portal, a następnie do pozycji **Urządzenia** > **Wszystkie urządzenia**. Filtruj według systemu operacyjnego, a następnie kliknij pozycję **Kolumny**, aby udostępnić szczegóły wersji systemu operacyjnego. Zwróć się do tych użytkowników, aby uaktualnili swoje urządzenia do obsługiwanej wersji systemu operacyjnego.  

Jeśli masz dowolne z wymienionych poniżej urządzeń lub chcesz zarejestrować dowolne z wymienionych poniżej urządzeń, pamiętaj, że obsługują one tylko system iOS 9 i wcześniejsze.  Aby nadal korzystać z aplikacji Portal firmy usługi Intune, musisz uaktualnić te urządzenia do urządzeń obsługujących system iOS 10 lub nowszy:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3. generacja) 
* iPad Mini (1. generacja)  

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centrum administracyjne zarządzania urządzeniami rozwiązania Microsoft 365 <!-- 3078424 -->
Jedną z obietnic platformy Microsoft 365 jest uproszczona administracja, a w ciągu lat zintegrowaliśmy usługi zaplecza rozwiązania Microsoft 365 w celu dostarczania kompletnych scenariuszy, takich jak dostęp warunkowy w usłudze Intune i usłudze Azure AD. Nowe [Centrum administracyjne platformy Microsoft 365](http://devicemanagement.microsoft.com) umożliwia konsolidację, uproszczenie i integrację środowiska administracji. Obszar roboczy dla specjalistów ds. zarządzania urządzeniami zapewnia łatwy dostęp do wszystkich informacji i zadań związanych z zarządzaniem urządzeniami aplikacji i aplikacjami. Oczekujemy, że ten obszar roboczy stanie się podstawowym obszarem w chmurze dla zespołów informatycznych użytkowników końcowych przedsiębiorstwa.


<!-- ########################## -->
## <a name="august-2018"></a>Sierpień 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Obsługa tunelowania pakietów dla profilów sieci VPN aplikacji w systemie iOS dotycząca typów połączenia niestandardowego i Pulse Secure <!-- 1520957 -->
Korzystając z profilów sieci VPN dla aplikacji w systemie iOS, można używać tunelowania w warstwie aplikacji (app-proxy) lub w warstwie pakietów (packet-tunnel). Te opcje są dostępne dla następujących typów połączeń:
- Niestandardowa sieć VPN
- Pulse Secure Jeśli nie masz pewności, której wartości użyć, zapoznaj się z dokumentacją dostawcy sieci VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Opóźnienie przy wyświetlaniu aktualizacji oprogramowania systemu iOS na urządzeniu <!-- 1949583 -->
Pozycja Intune > **Aktualizacje oprogramowania** > **Zasady aktualizowania systemu iOS** umożliwia skonfigurowanie dni i godzin, podczas których urządzenia nie powinny instalować żadnych aktualizacji. W ramach przyszłej aktualizacji będzie można opóźnić widoczność aktualizacji oprogramowania na urządzeniu o okres od 1 do 90 dni. 
Obszar [Konfigurowanie zasad aktualizacji systemu iOS w usłudze Microsoft Intune](software-updates-ios.md) zawiera bieżące ustawienia.

#### <a name="office-365-proplus-version----2213968---"></a>Usługa Office 365 w wersji ProPlus <!-- 2213968 -->
Podczas przypisywania aplikacji usługi Office 365 ProPlus do urządzeń z systemem Windows 10 przy użyciu usługi Intune będzie można wybrać wersję pakietu Office. W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje** > **Dodaj aplikację**. Następnie wybierz pozycję **Pakiet Office 365 ProPlus (Windows 10)** z listy rozwijanej **Typ**. Wybierz pozycję **Ustawienia pakietu aplikacji**, aby wyświetlić skojarzony blok. Ustaw wartość pozycji **Aktualizuj kanał**, na przykład **Co miesiąc**. Opcjonalnie usuń inne wersje pakietu Office (pliki msi) z urządzeń użytkowników końcowych, wybierając pozycję **Tak**. Wybierz pozycję **Określona**, aby zainstalować określoną wersję pakietu Office dla wybranego kanału na urządzeniach użytkowników końcowych. Teraz możesz wybrać wartość **Określona wersja** dla pakietu Office. Dostępne wersje będą się zmieniać z upływem czasu. Dlatego podczas tworzenia nowego wdrożenia mogą być dostępne nowsze wersje, a pewne starsze wersje mogą być niedostępne. Bieżące wdrożenia będą nadal wdrażane przy użyciu starszej wersji, lecz lista dla kanału będzie stale aktualizowana. Aby uzyskać więcej informacji, zobacz [Overview of update channels for Office 365 ProPlus (Omówienie kanałów aktualizacji usługi Office 365 ProPlus)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Obsługa ustawienia rejestracji DNS dla sieci VPN systemu Windows 10 <!-- 2282852 -->
Dzięki tej aktualizacji będzie można skonfigurować profile sieci VPN systemu Windows 10 tak, aby dynamicznie rejestrowały adresy IP przypisane do interfejsu sieci VPN za pomocą wewnętrznej usługi DNS — bez konieczności korzystania z profilów niestandardowych.
Aby uzyskać informacje o bieżących dostępnych ustawieniach profilu sieci VPN, zobacz [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>Instalator aplikacji Portal firmy systemu macOS teraz zawiera numer wersji w nazwie pliku instalatora <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>Automatyczne aktualizacje aplikacji systemu iOS <!-- 2729759 -->
Automatyczne aktualizacje aplikacji działają zarówno w przypadku aplikacji licencjonowanych dla urządzenia, jak i użytkownika dla systemu iOS w wersji 11.0 i nowszej.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Funkcja Windows Hello będzie dotyczyć użytkowników i urządzeń <!-- 1106609 -->
Po utworzeniu zasad funkcji [Windows Hello dla firm](windows-hello.md) będą one stosowane do wszystkich użytkowników w organizacji (na poziomie dzierżawy). Dzięki tej aktualizacji zasady można także zastosować do konkretnych użytkowników lub urządzeń przy użyciu zasad konfiguracji urządzeń (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Identity Protection** > **Windows Hello dla firm**).
W witrynie Azure Portal usługi Intune konfiguracja i ustawienia funkcji Windows Hello są teraz dostępne w ramach pozycji **Rejestrowanie urządzenia** i **Konfiguracja urządzenia**. Pozycja **Rejestrowanie urządzenia** dotyczy całej organizacji (na poziomie dzierżawy) i obsługuje rozwiązanie Windows AutoPilot (OOBE). Pozycja **Konfiguracja urządzenia** dotyczy urządzeń i użytkowników objętych zasadami stosowanymi podczas ewidencjonowania.
Ta funkcja ma zastosowanie do:  
- System Windows 10 lub nowszy
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Połączenie Zscaler jest dostępne dla profilów sieci VPN w systemie iOS <!-- 1769858 -->
Po utworzeniu profilu konfiguracji urządzenia sieci VPN w systemie iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** platforma > **Sieć VPN** typ profilu) będzie dostępnych kilka typów połączeń, w tym Cisco, Citrix i inne. Ta aktualizacja doda typ połączenia Zscaler. 
Pozycja [Ustawienia sieci VPN dla urządzeń z systemem iOS](vpn-settings-ios.md) zawiera dostępne typy połączeń.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Tryb FIPS dla profilów sieci Wi-Fi Enterprise w systemie Windows 10 <!-- 1879077 -->
Możesz teraz włączyć tryb przetwarzania standardów FIPS dla profilów sieci Wi-Fi Enterprise w systemie Windows 10 w witrynie Azure Portal usługi Intune. Upewnij się, że jest włączony tryb FIPS dla Twojej infrastruktury sieci Wi-Fi, jeśli włączysz go w profilach sieci Wi-Fi.
[Ustawienia sieci Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Intune](wi-fi-settings-windows.md) pokażą, jak utworzyć profil sieci Wi-Fi.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Kontrolowanie trybu S na urządzeniach z systemem Windows 10 i nowszymi — publiczna wersja zapoznawcza <!-- 1958649 -->
Dzięki tej aktualizacji funkcji możesz utworzyć profil konfiguracji urządzenia, który wyłącza tryb S urządzenia z systemem Windows 10 lub uniemożliwia użytkownikom wyłączenie trybu S na urządzeniu. Ta funkcja znajduje się w pozycji Intune > **Konfiguracja urządzenia** > **Profile** >  **System Windows 10 i nowszy** > **Uaktualnienie wersji i przełączenie trybu**.
Artykuł [Wprowadzenie do systemu Windows 10 w trybie S](https://www.microsoft.com/windows/s-mode) zawiera więcej informacji na temat trybu S.
Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (w wersji zapoznawczej).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pakiet konfiguracji zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender jest automatycznie dodawany do profilu konfiguracji <!-- 2144658 -->
Przedtem w przypadku korzystania z [zaawansowanej ochrony przed zagrożeniami i dołączania](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) urządzeń w usłudze Intune konieczne było pobranie pakietu konfiguracyjnego i dodanie go do własnego profilu konfiguracji. Dzięki tej aktualizacji usługa Intune automatycznie pobierze pakiet z usługi Windows Defender Security Center i doda go do Twojego profilu.
Dotyczy systemu Windows 10 lub nowszych.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Wymaganie od użytkowników nawiązania połączenia podczas konfigurowania urządzenia <!--2311457-->
Możesz teraz ustawić profile urządzeń i wymagać, aby to urządzenie połączyło się z siecią przed przejściem poza stronę Sieć podczas konfigurowania systemu Windows 10. Chociaż ta funkcja jest obecnie w wersji zapoznawczej, niejawny program testów systemu Windows (kompilacja 1809 lub nowsza) jest wymagany, aby użyć tego ustawienia.
Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (w wersji zapoznawczej).

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
Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (w wersji zapoznawczej).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Korzystanie z licencji programu VPP do wstępnego aprowizowania aplikacji Portal firmy podczas rejestracji w programie DEP <!-- 1608345 -->
Można już używać licencji urządzeń zakupionych w ramach programu VPP (Volume Purchase Program) do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji w programie DEP (Device Enrollment Program). W tym celu podczas [tworzenia lub edytowania profilu rejestracji](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) należy określić token programu VPP, który zostanie użyty do zainstalowania aplikacji Portal firmy. Upewnij się, że token nie wygasł, i że masz wystarczającą liczbę licencji dla aplikacji Portal firmy. W przypadkach, gdy token wygaśnie lub zabraknie dla niego licencji, usługa Intune wypchnie aplikację Portal firmy ze sklepu App Store (spowoduje to wyświetlenie monitu o podanie identyfikatora Apple ID).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Wymagane potwierdzenie w celu usunięcia tokenu programu VPP, który jest używany do wstępnej aprowizacji aplikacji Portal firmy <!-- 2237634 -->
Wymagane jest potwierdzenie w celu usunięcia tokenu programu Volume Purchase Program (VPP), jeśli jest on używany do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Blokowanie rejestracji osobistych urządzeń z systemem Windows <!-- 1849498 -->
Możesz [zablokować rejestrowanie urządzeń osobistych z systemem Windows](enrollment-restrictions-set.md#set-device-type-restrictions) za pomocą rozwiązania do [zarządzania urządzeniami mobilnymi](windows-enroll.md) w usłudze Intune. Za pomocą tej funkcji nie można zablokować urządzeń zarejestrowanych przy użyciu [agenta usługi Intune na komputerze](manage-windows-pcs-with-microsoft-intune.md). Ta funkcja będzie wprowadzana w ciągu kolejnych kilku tygodni, dlatego może nie być od razu widoczna w interfejsie użytkownika.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Określanie wzorców nazw maszyn w profilu rozwiązania AutoPilot <!--1849855-->
Możesz [określić szablon nazwy komputera](enrollment-autopilot.md#create-an-autopilot-deployment-profile), aby wygenerować i ustawić [nazwę komputera](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) podczas rejestrowania za pomocą rozwiązania AutoPilot. Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (w wersji zapoznawczej).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>W przypadku profilów rozwiązania Windows AutoPilot można ukryć opcje zmiany konta na stronach logowania firmy i błędu domeny <!--1901669 -->
Istnieją [nowe opcje profilu rozwiązania Windows Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile) przeznaczone dla administratorów i umożliwiające ukrycie opcji zmiany konta na stronach logowania firmy i błędu domeny. Ukrywanie tych opcji wymaga skonfigurowania znakowania firmowego w usłudze Azure Active Directory. Dotyczy: najnowsza kompilacja [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (w wersji zapoznawczej).

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Obsługa systemu macOS w programie Device Enrollment Program firmy Apple <!-- 747651 -->
Usługa Intune obsługuje już rejestrowanie urządzeń z systemem macOS w programie Device Enrollment Program (DEP) firmy Apple. Aby uzyskać więcej informacji, zobacz [Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program firmy Apple](device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="delete-jamf-devices----2653306--"></a>Usuwanie urządzeń Jamf <!-- 2653306-->
Możesz usuwać urządzenia zarządzane za pomocą oprogramowania JAMF, przechodząc do pozycji **Urządzenia** > wybierz urządzenie Jamf > **Usuń**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Zmiana terminologii na „wycofaj” i „wyczyść” <!-- 2175759 -->
Aby zachować spójność z interfejsem API programu Graph, w interfejsie użytkownika usługi Intune i w dokumentacji zmieniły się następujące terminy:
- **Usuń dane firmowe** zostanie zmieniony na „wycofaj”
- **Resetowanie do ustawień fabrycznych** zostanie zmieniony na **wyczyść**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Okno dialogowe potwierdzenia, jeśli administrator próbuje usunąć certyfikat wypychania MDM <!-- 297909500-->
Jeśli ktoś próbuje usunąć certyfikat wypychania MDM firmy Apple, w oknie dialogowym potwierdzenia jest wyświetlana liczba powiązanych urządzeń z systemem iOS i macOS. Jeśli certyfikat zostanie usunięty, te urządzenia będą wymagały ponownej rejestracji.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Dodatkowe ustawienia zabezpieczeń dla Instalatora Windows <!-- 2282430 -->
Można zezwolić użytkownikom na kontrolowanie instalacji aplikacji. Po włączeniu tej funkcji instalacje, które w przeciwnym razie mogły zostać zatrzymane z powodu naruszenia zabezpieczeń, będą kontynuowane. Można przekierować Instalatora Windows tak, aby używał podwyższonego poziomu uprawnień podczas instalowania dowolnego programu w systemie. Ponadto można włączyć indeksowanie elementów funkcji Windows Information Protection (WIP) oraz przechowywanie związanych z nimi metadanych w niezaszyfrowanej lokalizacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie są indeksowane i nie są wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Funkcje tych opcji są domyślnie wyłączone. 

#### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Aktualizacja nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968 -->
Na podstawie opinii klientów dodaliśmy nowe funkcje do witryny internetowej Portal firmy. Na swoich urządzeniach zobaczysz znaczące ulepszenia istniejących funkcji i poprawę użyteczności. Obszary witryny &ndash; takie jak szczegółowe informacje o urządzeniu, opinie i pomoc techniczna oraz przegląd urządzenia &ndash; zyskały nowy, nowoczesny i dynamiczny wygląd. Ponadto wprowadziliśmy następujące zmiany:

- Usprawnione przepływy pracy na wszystkich platformach urządzeń
- Ulepszone przepływy identyfikacji i rejestracji urządzeń
- Bardziej pomocne komunikaty o błędach
- Bardziej przyjazny język, mniej technicznego żargonu
- Możliwość udostępniania bezpośrednich linków do aplikacji
- Zwiększona wydajność dużych wykazów aplikacji
- Zwiększona dostępność dla wszystkich użytkowników  

[Dokumentacja witryny internetowej Portal firmy usługi Intune](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) została zaktualizowana w celu odzwierciedlenia tych zmian. Aby wyświetlić przykład rozszerzeń aplikacji, zobacz [UI updates for Intune end-user apps (Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune)](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Rozszerzone wykrywanie zdjęcia zabezpieczeń systemu w raportowaniu zgodności<!-- 2198738 -->
Rozszerzone wykrywanie zdjęcia zabezpieczeń systemu dla ustawień stanów teraz pojawia się we wszystkich raportach zgodności w konsoli administracyjnej.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-policies---1081974---"></a>Tagi zakresu dla zasad <!--1081974 -->
Możesz [tworzyć tagi zakresu](scope-tags.md) w celu ograniczenia dostępu do zasobów usługi Intune. Dodaj tag zakresu do przypisania roli, a następnie dodaj tag zakresu do profilu konfiguracji. Rola będzie miała wtedy dostęp tylko do zasobów z profilami konfiguracji ze zgodnymi tagami zakresu (lub bez tagów zakresu).





<!-- ########################## -->
## <a name="july-2018"></a>Lipiec 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Obsługa aplikacji biznesowych (LOB) dla systemu macOS <!-- 1895847 -->
Usługa Microsoft Intune umożliwia wdrażanie aplikacji biznesowych systemu macOS jako **wymaganych** lub **dostępnych z rejestracją**. Użytkownicy końcowi mogą wdrażać aplikacje jako **dostępne** przy użyciu aplikacji Portal firmy dla systemu macOS lub [witryny internetowej Portal firmy](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Wbudowana obsługa aplikacji systemu iOS na potrzeby trybu kiosku <!-- 2051098 -->
Oprócz aplikacji ze Sklepu i aplikacji zarządzanych można teraz wybrać aplikacje wbudowane (na przykład przeglądarkę Safari), które działają w trybie kiosku na urządzeniu z systemem iOS.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Edytowanie wdrożeń aplikacji usługi Office 365 Pro Plus <!-- 2150145 -->
Jako administrator usługi Microsoft Intune masz większe możliwości edycji wdrożeń aplikacji usługi Office 365 Pro Plus. Ponadto nie musisz już usuwać swoich wdrożeń, aby zmienić jakiekolwiek właściwości pakietu. W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje klienckie** > **Aplikacje**. Z listy aplikacji wybierz pakiet Office 365 Pro Plus.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Zaktualizowany zestaw Intune App SDK dla systemu Android jest teraz dostępny <!-- 2744271-->
Zaktualizowana wersja zestawu Intune App SDK dla systemu Android jest dostępna do obsługi wersji P systemu Android. Jeśli jesteś deweloperem aplikacji i używasz zestawu Intune SDK dla systemu Android, musisz zainstalować zaktualizowaną wersję zestawu Intune App SDK, aby zapewnić, że funkcje usługi Intune wykorzystywane w ramach Twoich aplikacji systemu Android będą nadal działać zgodnie z oczekiwaniami na urządzeniach z systemem Android P. Ta wersja zestawu Intune App SDK udostępnia wbudowany dodatek, który wykonuje aktualizacje zestawu SDK. Nie trzeba przepisywać istniejącego zintegrowanego kodu. Aby uzyskać szczegółowe informacje, zobacz temat [Zestaw Intune SDK dla systemu Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Jeśli używasz starego stylu ze wskaźnikami do usługi Intune, firma Microsoft zaleca użycie ikony Aktówka. Szczegóły dotyczące znakowania można znaleźć w [tym repozytorium GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Więcej możliwości synchronizacji w aplikacji Portal firmy dla systemu Windows  
Aplikacja Portal firmy dla systemu Windows umożliwia teraz zainicjowanie synchronizacji bezpośrednio z poziomu paska zadań i menu Start systemu Windows. Ta funkcja jest szczególnie przydatna, jeśli Twoim jedynym zadaniem jest synchronizowanie urządzeń i uzyskiwanie dostępu do zasobów firmy. Aby skorzystać z nowych funkcji, kliknij prawym przyciskiem myszy ikonę aplikacji Portal firmy przypiętą do paska zadań lub menu Start. W opcjach menu (nazywanych również listą szybkiego dostępu) wybierz pozycję **Synchronizuj to urządzenie**. Spowoduje to otwarcie aplikacji Portal firmy na stronie **Ustawienia** i zainicjowanie synchronizacji. Aby dowiedzieć się więcej o nowej funkcji, zobacz [Co nowego w interfejsie użytkownika](whats-new-app-ui.md).   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nowe środowisko przeglądania w aplikacji Portal firmy dla systemu Windows  
Teraz podczas przeglądania w poszukiwaniu aplikacji lub ich wyszukiwania w aplikacji Portal firmy dla systemu Windows możliwe jest przełączanie się między istniejącym widokiem **Kafelki** a nowo dodanym widokiem **Szczegóły**. W nowym widoku wyświetlane są szczegółowe informacje dotyczące aplikacji, takie jak nazwa, wydawca, data publikacji i stan instalacji.  

Na stronie **Aplikacje** w widoku **Zainstalowane** dostępne są szczegóły dotyczące zakończonych i trwających instalacji aplikacji. Aby dowiedzieć się, jak wygląda nowy widok, zobacz [Co nowego w interfejsie użytkownika](whats-new-app-ui.md).  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Ulepszone środowisko aplikacji Portal firmy dla menedżerów rejestracji urządzeń  
Gdy menedżer rejestracji urządzeń loguje się do aplikacji Portal firmy dla systemu Windows, w aplikacji będzie teraz wyświetlane tylko bieżące, uruchomione urządzenie menedżera rejestracji urządzeń. To ulepszenie ograniczy występowanie przekroczeń limitu czasu, które wcześniej miały miejsce, gdy aplikacja podejmowała próbę wyświetlenia wszystkich urządzeń zarejestrowanych w menedżerze rejestracji urządzeń.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokowanie dostępu do aplikacji dla niezatwierdzonych dostawców i modeli urządzeń  <!-- 1425689 ! -->
Administrator IT usługi Intune może wymuszać określoną listę producentów urządzeń z systemem Android i/lub modeli urządzeń z systemem iOS za pomocą zasad ochrony aplikacji w usłudze Intune. Administrator IT może przedstawić rozdzielaną średnikami listę producentów zgodnych z zasadami systemu Android oraz modeli urządzeń zgodnych z zasadami systemu iOS. Zasady ochrony aplikacji w usłudze Intune są przeznaczone tylko dla systemów Android i iOS. Dla podanej listy można wykonać dwie oddzielne akcje:
- Blokowanie dostępu do aplikacji na urządzeniach, które nie zostały określone.
- Lub selektywne czyszczenie danych firmowych na urządzeniach, które nie zostały określone. 

Użytkownik nie będzie mógł uzyskiwać dostępu do aplikacji docelowej, jeśli wymagania zasad nie zostaną spełnione. Na podstawie ustawień użytkownik może zostać zablokowany albo jego dane firmowe mogą zostać selektywnie wyczyszczone z aplikacji. Na urządzeniach z systemem iOS ta funkcja wymaga udziału aplikacji (takich jak WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu Intune APP SDK, aby ta funkcja była wymuszana na docelowych aplikacjach. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy. 

Na urządzeniach użytkowników końcowych klient usługi Intune wykona akcję w oparciu o proste dopasowywanie ciągów określonych w bloku usługi Intune dla zasad ochrony aplikacji. Zależy to całkowicie od wartości zgłaszanej przez urządzenie. W takiej sytuacji administrator IT jest zachęcany do zapewniania, że założone zachowanie jest prawidłowe. Ten cel można osiągnąć, testując to ustawienie w oparciu o różnych producentów i modele urządzeń przeznaczone dla małej grupy użytkowników. W usłudze Microsoft Intune wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji**, aby wyświetlić i dodać zasady ochrony aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji](app-protection-policy.md) i [Selektywne czyszczenie danych przy użyciu akcji dostępu zasad ochrony aplikacji w usłudze Intune](app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Dostęp do kompilacji wersji wstępnej Portalu firmy dla systemu macOS <!-- 1734766 -->
Za pomocą programu Microsoft AutoUpdate możesz zarejestrować się w celu wcześniejszego otrzymywania kompilacji przez dołączenie do niejawnego programu testów. Rejestracja umożliwi korzystanie ze zaktualizowanego Portalu firmy, zanim będzie on dostępny dla Twoich użytkowników końcowych. Aby uzyskać więcej informacji, zobacz [Blog usługi Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

### <a name="device-configuration"></a>Konfiguracja urządzenia

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

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Opcja Kiosk — przestarzałe jest wyszarzona i nie można jej zmienić <!-- 2149998 -->
Funkcja kiosku (wersja zapoznawcza) (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** > **Ograniczenia dotyczące urządzeń**) jest przestarzała i została zastąpiona [ustawieniami kiosku dla systemu Windows 10 i nowszych](kiosk-settings.md). W ramach tej aktualizacji funkcja **Kiosk — przestarzałe** została wyszarzona i nie można będzie zmienić ani zaktualizować interfejsu użytkownika. 

Aby włączyć tryb kiosku, zobacz [ustawienia kiosku dla systemu Windows 10 i nowszych](kiosk-settings.md).

Dotyczy systemu Windows 10 lub nowszych oraz systemu Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Interfejsy API umożliwiające korzystanie z urzędów certyfikacji innych firm <!-- 2184013 -->
W ramach tej aktualizacji dostępny jest interfejs API języka Java umożliwiający integrację urzędów certyfikacji innych firm z usługą Intune i protokołem SCEP. Następnie użytkownicy będą mogli dodać certyfikat protokołu SCEP do profilu i zastosować go do urządzeń za pomocą rozwiązania MDM.

Obecnie usługa Intune obsługuje [żądania protokołu SCEP za pomocą usług certyfikatów Active Directory](certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Przełączanie w celu wyświetlania lub niewyświetlania przycisku Zakończ sesję w przeglądarce kiosku <!-- 2455253 -->
Możliwe jest teraz skonfigurowanie, czy przycisk Zakończ sesję ma być wyświetlany w przeglądarce kiosku. Możesz zobaczyć kontrolkę, wybierając pozycje **Konfiguracja urządzenia** > **Kiosk (wersja zapoznawcza)** > **Przeglądarka internetowa kiosku**. Jeśli jest włączona, kiedy użytkownik kliknie przycisk, aplikacja wyświetli monit o potwierdzenie zakończenia sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania i powraca do domyślnego adresu URL.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Tworzenie profilu konfiguracji sieci komórkowej karty eSIM <!-- 2564077 -->
W **konfiguracji urządzenia** można utworzyć profil sieci komórkowej karty eSIM. Można zaimportować plik, który zawiera kody aktywacji sieci komórkowej dostarczone przez operatora sieci komórkowej. Następnie można wdrożyć te profile na urządzeniach z systemem Windows 10 z włączoną obsługą sieci LTE karty eSIM, takich jak urządzenia Surface Pro LTE i inne urządzenia obsługujące karty eSIM.

Sprawdź, czy Twoje [urządzenia obsługują profile karty eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Dotyczy systemu Windows 10 lub nowszych. 

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Wybieranie kategorii urządzeń przy użyciu ustawień opcji Uzyskaj dostęp do miejsca pracy lub nauki <!-- 1058963 eenotready --> 
Jeśli włączono [mapowanie grup urządzeń](https://docs.microsoft.com/intune/device-group-mapping), w systemie Windows 10 po dokonaniu rejestracji przy użyciu przycisku **Połącz** w obszarze **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** zostanie teraz wyświetlony monit o wybranie kategorii urządzenia. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Używanie atrybutu sAMAccountName jako nazwy użytkownika konta dla profilów poczty e-mail <!-- 1500307 -->
Możesz używać lokalnego atrybutu **sAMAccountName** jako nazwy użytkownika konta w profilach poczty e-mail dla systemu Android, iOS i Windows 10. Możesz również pobrać domenę z atrybutu `domain` lub `ntdomain` w usłudze Azure Active Directory (Azure AD). Ewentualnie można wprowadzić niestandardową domenę statyczną.

Aby korzystać z tej funkcji, należy zsynchronizować atrybut `sAMAccountName` z lokalnego środowiska usługi Active Directory z usługą Azure AD.

Dotyczy: [Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 i nowsze wersje](email-settings-windows-10.md)

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
Podczas tworzenia nowych zasad zgodności urządzeń (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **Platforma: Windows 10 lub nowszy** > **Ustawienia** > **Zabezpieczenia systemu**) są dostępne nowe opcje **[zabezpieczeń urządzeń](compliance-policy-create-windows.md)**: 
- **Oprogramowanie antywirusowe**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antywirusowych zarejestrowanych w Centrum zabezpieczeń systemu Windows, na przykład rozwiązań firmy Symantec i usługi Windows Defender. 
- **Program antyszpiegowski**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antyszpiegowskich zarejestrowanych w Centrum zabezpieczeń systemu Windows, na przykład rozwiązań firmy Symantec i usługi Windows Defender. 

Dotyczy: system Windows 10 lub nowszy 

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Automatyczne oznaczanie urządzeń z systemem Android zarejestrowanych za pomocą programu Samsung Knox Mobile Enrollment jako „firmowe”. <!-- 2404851 -->
Domyślnie urządzenia z systemem Android zarejestrowane za pomocą programu Samsung Knox Mobile Enrollment są teraz oznaczone jako **firmowe** w obszarze **Własność urządzenia**. Nie musisz ręcznie identyfikować urządzeń firmowych przy użyciu numerów IMEI lub numerów seryjnych przed zarejestrowaniem ich za pomocą programu Knox Mobile Enrollment.

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Urządzenia bez kolumny profilów na liście tokenów programu rejestracji <!-- 1853904 -->
Lista tokenów programu rejestracji zawiera nową kolumnę, w której jest wyświetlana liczba urządzeń bez przypisanego profilu. Ułatwia ona administratorom przypisywanie profilów do tych urządzeń przed przekazaniem ich użytkownikom. Aby wyświetlić nową kolumnę, przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji**.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Zbiorcze usuwanie urządzeń w bloku urządzeń <!-- 1793693 -->
Możliwe jest teraz usunięcie wielu urządzeń naraz w bloku Urządzenia. Wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenia do usunięcia > **Usuń**. W przypadku urządzeń, których nie można usunąć, zostanie wyświetlony alert.

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


<!-- ########################## -->
## <a name="june-2018"></a>Czerwiec 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Obsługa zasad ochrony aplikacji usługi Intune w przeglądarce Microsoft Edge dla urządzeń przenośnych <!-- 1817882 -->
Przeglądarka Microsoft Edge dla urządzeń przenośnych obsługuje teraz zasady ochrony aplikacji zdefiniowane w usłudze Intune.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Pobieranie skojarzonego identyfikatora modelu użytkownika aplikacji (AUMID) dla aplikacji ze sklepu Microsoft Store dla Firm w trybie kiosku <!-- 1560077 ! -->
Usługa Intune może teraz pobierać identyfikatory modelu użytkownika aplikacji (AUMID) dla aplikacji ze sklepu Microsoft Store dla Firm (WSfB) w celu udostępniania ulepszonej konfiguracji profilu kiosku.

Aby uzyskać więcej informacji na temat aplikacji ze sklepu Microsoft Store dla Firm, zobacz [Manage apps from Microsoft Store for Business](windows-store-for-business.md) (Zarządzanie aplikacjami ze sklepu Microsoft Store dla Firm).

#### <a name="new-company-portal-branding-page----1916370---"></a>Nowa strona znakowania Portalu firmy <!-- 1916370 -->
Strona znakowania Portalu firmy ma nowy układ, komunikaty i etykietki narzędzi.


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo — nowy partner usługi Mobile Threat Defense <!-- 1169249 -->
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Pradeo — rozwiązania usługi Mobile Threat Defense zintegrowanego z usługą Microsoft Intune.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Używanie trybu FIPS z łącznikiem certyfikatu usługi NDES <!-- 1333688 -->
Po zainstalowaniu łącznika certyfikatów usługi NDES na komputerze z włączonym trybem Federal Information Processing Standard (FIPS) wystawianie i odwoływanie certyfikatów nie działało zgodnie z oczekiwaniami. Dzięki tej aktualizacji łącznik certyfikatów usługi NDES obsługuje standard FIPS. 

Ta aktualizacja obejmuje również:

- Łącznik certyfikatów usługi NDES wymaga programu .NET 4.5 Framework, który jest automatycznie dołączany do systemów Windows Server 2016 i Windows Server 2012 R2. Wcześniej program .NET 3.5 Framework był minimalną wymaganą wersją.
- Obsługa protokołu TLS 1.2 jest dołączona do łącznika certyfikatów usługi NDES. Jeśli więc serwer z zainstalowanym łącznikiem certyfikatów usługi NDES obsługuje protokół TLS 1.2, jest używany protokół TLS 1.2. Jeśli serwer nie obsługuje protokołu TLS 1.2, jest używany protokół TLS 1.1. Obecnie protokół TLS 1.1 jest używany do uwierzytelniania między urządzeniami a serwerem.

Aby uzyskać więcej informacji, zobacz [Configure and use SCEP certificates (Konfigurowanie i używanie certyfikatów SCEP)](certificates-scep-configure.md) i [Configure and use PKCS certificates (Konfigurowanie i używanie certyfikatów PKCS)](certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Obsługa profilów sieci VPN Palo Alto Networks GlobalProtect <!-- 1333680 ! -->
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

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Obsługa rejestracji rozwiązania Windows Autopilot bez uwierzytelniania użytkownika <!-- 1165118 -->
Usługa Intune obsługuje teraz rejestrację przy użyciu rozwiązania Windows Autopilot bez uwierzytelniania użytkownika. Jest to nowa opcja w profilu wdrażania programu Windows Autopilot „Tryb wdrażania rozwiązania Autopilot” ustawiona na wartość „Samodzielne wdrażanie”.  Aby pomyślnie ukończyć tego rodzaju rejestrację, na urządzeniu musi być uruchomiona kompilacja 17672 niejawnego programu testów systemu Windows 10 w wersji zapoznawczej lub nowsza i urządzenie musi być wyposażone w układ scalony TPM 2.0. Ponieważ żadne uwierzytelnianie użytkownika nie jest wymagane, tę opcję należy przypisywać tylko do urządzeń, nad którymi masz fizyczną kontrolę.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nowe ustawienie języka/regionu podczas konfigurowania OOBE dla rozwiązania Autopilot <!-- 1821766 -->
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

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>Odinstalowywanie najnowszych aktualizacji oprogramowania systemu Windows 10 <!-- 1732948 -->
Jeśli wykryjesz problem powodujący awarię na maszynach z systemem Windows 10, możesz odinstalować (wycofać) najnowszą aktualizację funkcji lub najnowszą aktualizację jakości. Odinstalowywanie aktualizacji funkcji lub jakości jest dostępne tylko dla kanału obsługi dostępnego na urządzeniu. Odinstalowywanie wyzwoli zasady w celu przywrócenia poprzedniej aktualizacji na maszynach z systemem Windows 10. W przypadku aktualizacji funkcji można ograniczyć czas (od 2 do 60 dni), w którym można odinstalować najnowszą wersję. Aby ustawić opcje odinstalowywania aktualizacji oprogramowania, wybierz pozycję **Aktualizacje oprogramowania** w bloku **Microsoft Intune** w witrynie Azure Portal. Następnie wybierz pozycję **Pierścienie aktualizacji systemu Windows 10** w bloku **Aktualizacje oprogramowania**. Następnie możesz wybrać opcję **Odinstaluj** w sekcji **Przegląd**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Wyszukiwanie wszystkich urządzeń na podstawie numeru IMEI i numeru seryjnego <!-- 1793685 -->
Możesz teraz wyszukiwać numery IMEI i numery seryjne w bloku Wszystkie urządzenia (adres e-mail, nazwa UPN, nazwa urządzenia i nazwa zarządzania są nadal dostępne). W usłudze Intune wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wprowadź kryteria wyszukiwania w polu wyszukiwania.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Będzie można edytować pole Nazwa zarządzania <!-- 1875989 -->
Możesz teraz edytować pole Nazwa zarządzania w bloku **Właściwości** urządzenia. Aby edytować to pole, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości**. Pola nazwy zarządzania można używać do unikatowego identyfikowania urządzenia.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Nowy filtr listy Wszystkie urządzenia: Kategoria urządzeń <!-- 1878520 -->
Obecnie można filtrować listę **Wszystkie urządzenia** według kategorii urządzeń. Aby to zrobić, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > **Filtr** > **Kategoria urządzeń**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Używanie programu TeamViewer do udostępniania ekranów urządzeń z systemami iOS i MacOS <!-- 1985547 -->
Administratorzy mogą teraz łączyć się z programem [TeamViewer](device-profile-android-teamviewer.md), a następnie uruchamiać sesję udostępniania ekranu na urządzeniach z systemem iOS i macOS. Użytkownicy urządzeń iPhone i iPad oraz urządzeń z systemem macOS mogą na żywo udostępniać ekrany innemu urządzeniu stacjonarnemu lub przenośnemu. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Obsługa wielu programów Exchange Connector <!-- 2070451 -->
Nie ma już ograniczenia do jednego programu Microsoft Intune Exchange Connector na dzierżawę. Usługa Intune obsługuje teraz wiele programów Microsoft Intune Exchange Connector, dzięki czemu możliwe będzie skonfigurowanie dostępu warunkowego w usłudze Intune przy użyciu wielu lokalnych organizacji programu Exchange.

Dzięki lokalnemu łącznikowi programu Exchange w usłudze Intune możesz zarządzać dostępem urządzeń do lokalnych skrzynek pocztowych programu Exchange na podstawie tego, czy urządzenie jest zarejestrowane w usłudze Intune i jest zgodne z zasadami zgodności urządzeń usługi Intune. Aby skonfigurować łącznik, pobierz lokalny łącznik programu Exchange z witryny Azure Portal i zainstaluj go na serwerze w organizacji programu Exchange. Na pulpicie nawigacyjnym usługi Microsoft Intune wybierz pozycję **Dostęp lokalny**, a następnie w obszarze **Konfiguracja** wybierz pozycję **Łącznik Exchange ActiveSync**. Pobierz lokalny łącznik programu Exchange i zainstaluj go na serwerze w organizacji programu Exchange. Ponieważ nie ma już ograniczenia do jednego łącznika programu Exchange na dzierżawę, jeśli masz dodatkowe organizacje programu Exchange, możesz wykonać te same czynności, aby pobrać i zainstalować łącznik dla każdej dodatkowej organizacji programu Exchange.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Nowe szczegóły sprzętu urządzenia: CCID <!-- 2156657 -->
Informacje o specyfikacji CCID (Chip Card Interface Device) są teraz uwzględniane dla każdego urządzenia. Aby je wyświetlić, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**> sprawdź informacje w obszarze **Szczegóły sieci**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Przypisywanie wszystkich użytkowników i wszystkich urządzeń jako grup zakresu <!-- 2196803 -->
W grupach zakresu możesz teraz przypisywać wszystkich użytkowników, wszystkie urządzenia oraz wszystkich użytkowników i wszystkie urządzenia. Aby to zrobić, wybierz pozycję **Role usługi Intune** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > wybierz przypisanie > **Zakres (grupy)**.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>Informacje o identyfikatorze UDID są teraz dostępne w przypadku urządzeń z systemem iOS i macOS <!-- 2219806 -->
Aby wyświetlić unikatowy identyfikator urządzenia (UDID) dla urządzeń z systemem iOS i macOS, przejdź do pozycji **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**. Identyfikator UDID jest dostępny tylko dla urządzeń firmowych (zgodnie z ustawieniem w obszarze **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości** > **Własność urządzeń**).

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Ulepszone rozwiązywanie problemów z instalacją aplikacji <!-- 928990 -->
Na urządzeniach zarządzanych przez oprogramowanie MDM w usłudze Microsoft Intune czasami operacje instalacji aplikacji mogą zakończyć się niepowodzeniem. W takich sytuacjach zrozumienie przyczyny niepowodzenia lub rozwiązanie problemu może okazać się wyzwaniem. Udostępniamy publiczną wersję zapoznawczą naszej funkcji rozwiązywania problemów z aplikacjami. W obszarach poszczególnych urządzeń zauważysz nowy węzeł o nazwie **Aplikacje zarządzane**. Ta pozycja służy do wyświetlania listy aplikacji dostarczonych za pomocą oprogramowania MDM usługi Intune. Wewnątrz węzła znajduje się lista stanów instalacji aplikacji. Po wybraniu aplikacji zostanie wyświetlony widok rozwiązywania problemów związanych z tą aplikacją. W widoku rozwiązywania problemów zostanie przedstawiony cały cykl życia aplikacji, np. czas utworzenia i zmodyfikowania aplikacji, wybrania jej jako docelowej i dostarczenia do urządzenia. Ponadto jeśli instalacja aplikacji zakończyła się niepowodzeniem, zostanie wyświetlony kod błędu i użyteczny komunikat dotyczący przyczyny tego błędu. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Zasady ochrony aplikacji usługi Intune i przeglądarka Microsoft Edge <!-- 1818968 -->
Przeglądarka Microsoft Edge dla urządzeń przenośnych (iOS i Android) obsługuje teraz zasady ochrony aplikacji w usłudze Microsoft Intune. Użytkownicy urządzeń z systemami iOS i Android, którzy logują się przy użyciu kont firmowych usługi Azure AD w aplikacji Microsoft Edge, będą chronieni przez usługę Intune. Na urządzeniach z systemem iOS zasady **Wymagaj programu Managed Browser dla zawartości internetowej** pozwolą użytkownikom na otwieranie linków w przeglądarce Microsoft Edge, gdy jest ona zarządzana.

<!-- ########################## -->
## <a name="may-2018"></a>Maj 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Konfigurowanie zasad ochrony aplikacji <!-- 2144597 Part 2 -->

W witrynie Azure Portal zamiast przechodzenia do bloku usługi Intune App Protection możesz teraz po prostu przejść do usługi Intune. Teraz jest tylko jedna lokalizacja zasad ochrony aplikacji w ramach usługi Intune. Zapamiętaj, że wszystkie zasady ochrony aplikacji znajdują się w bloku **Aplikacja mobilna** w usłudze Intune w obszarze **Zasady ochrony aplikacji**. Ta integracja pomaga uprościć administrowanie chmurą. Pamiętaj, że wszystkie zasady ochrony aplikacji są już dostępne w usłudze Intune i możesz modyfikować dowolne wcześniej skonfigurowane zasady. Zasady ochrony aplikacji (APP) i zasady dostępu warunkowego (CA) w usłudze Intune znajdują się teraz w obszarze **Dostęp warunkowy**, który znajduje się w sekcji **Zarządzanie** w bloku **Microsoft Intune** lub w sekcji **Zabezpieczenia** w bloku **Azure Active Directory**. Aby uzyskać więcej informacji na temat modyfikowania zasad dostępu warunkowego, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Aby uzyskać dodatkowe informacje, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Wymagana instalacja zasad, aplikacji oraz profilów certyfikatów i sieciowych <!-- 1553555 -->
Administratorzy mogą zablokować dostęp użytkowników końcowych do pulpitu systemu Windows 10 RS4 do momentu zainstalowania zasad, aplikacji oraz profilów certyfikatów i sieciowych przez usługę Intune podczas aprowizowania urządzeń z rozwiązaniem AutoPilot. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Pomoc techniczna dotycząca programu Samsung Knox Mobile Enrollment <!--1112863-->
Korzystając z usługi Intune z programem Samsung Knox Mobile Enrollment (KME) można zarejestrować dużą liczbę urządzeń firmowych z systemem Android. Użytkownicy korzystający z sieci komórkowej lub Wi-Fi mogą za pomocą kilku naciśnięć zarejestrować urządzenie przy jego pierwszym włączeniu. Podczas korzystania z aplikacji Knox Deployment urządzenia mogą być rejestrowane za pomocą funkcji Bluetooth lub NFC. Aby uzyskać więcej informacji, zobacz temat [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md) (Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów 

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Żądanie pomocy w aplikacji Portal firmy w systemie Windows 10 <!-- 1874137 -->
Gdy użytkownik zainicjuje przepływ pracy w celu uzyskania pomocy dotyczącej problemu, aplikacja Portal firmy w systemie Windows 10 wyśle dzienniki aplikacji bezpośrednio do firmy Microsoft. Ułatwia to rozwiązywanie i usuwanie problemów, które zostały zgłoszone firmie Microsoft.

<!-- ########################## -->
## <a name="april-2018"></a>Kwiecień 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Obsługa kodu dostępu dla numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi w systemie Android<!-- 1438086 -->

Administratorzy usługi Intune mogą określić wymaganie dotyczące uruchamiania aplikacji w celu wymuszenia użycia kodu dostępu zamiast numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi. W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. Usługa Intune obsługuje kod dostępu podobnie jak istniejący liczbowy numer PIN, umożliwiając ustawienie minimalnej długości oraz reguł powtarzania znaków i sekwencji w konsoli administracyjnej. Ta funkcja wymaga najnowszej wersji aplikacji Portal firmy w systemie Android. Ta funkcja jest już dostępna dla systemu iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Obsługa aplikacji biznesowych (LOB) dla systemu macOS <!-- 1473977 -->
Usługa Microsoft Intune będzie umożliwiać instalowanie aplikacji biznesowych (LOB) dla systemu macOS z witryny Azure Portal. Aplikację LOB dla systemu macOS będzie można dodać do usługi Intune po jej wstępnym przetworzeniu za pomocą narzędzia dostępnego w usłudze GitHub. W witrynie Azure Portal wybierz pozycję **Aplikacje klienckie** w bloku **Intune**. W bloku **Aplikacje klienckie** wybierz pozycję **Aplikacje** > **Dodaj**. W bloku **Dodaj aplikację** wybierz pozycję **Aplikacja biznesowa**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Wbudowane grupy Wszyscy użytkownicy i Wszystkie urządzenia na potrzeby przypisywania aplikacji profilu służbowego Android Enterprise <!-- 1813073 -->
Można użyć wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji profilu służbowego Android Enterprise. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Usługa Intune zainstaluje wymagane aplikacje, które są odinstalowywane przez użytkowników <!-- 1947010 -->
Jeśli użytkownik końcowy odinstaluje wymaganą aplikację, usługa Intune automatycznie ponownie instaluje aplikację w ciągu 24 godzin, nie czekając na zakończenie 7-dniowego cyklu ponownej oceny.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Aktualizowanie miejsca konfigurowania zasad ochrony aplikacji <!-- 2144597 -->

W witrynie Azure Portal w ramach usługi Microsoft Intune zostanie włączone tymczasowe przekierowanie z bloku usługi **Intune App Protection** do bloku **Aplikacja mobilna**. Uwaga: wszystkie zasady ochrony aplikacji znajdują się już w bloku **Aplikacja mobilna** w usłudze Intune w obszarze konfiguracji aplikacji. Zamiast przechodzić do usługi Intune App Protection, należy przejść do usługi Intune. W kwietniu 2018 r. zatrzymamy to przekierowywanie i całkowicie usuniemy blok usługi **Intune App Protection**, więc będzie istnieć tylko jedna lokalizacja z zasadami ochrony aplikacji w usłudze Intune. 

**Jak to wpłynie na mnie?**
Ta zmiana wpłynie zarówno na klientów z autonomiczną usługą Intune, jak i na klientów ze środowiskami hybrydowymi (usługą Intune z programem Configuration Manager). Ta integracja pomoże uprościć administrowanie chmurą.

**Co należy zrobić, aby przygotować się do tej zmiany?**
Otaguj usługę **Intune** jako ulubioną zamiast bloku usługi **Intune App Protection** i zapoznaj się z przepływem pracy zasad ochrony aplikacji w bloku **Aplikacja mobilna** w usłudze Intune. Przez krótki okres będzie działać przekierowanie, a następnie blok **App Protection** zostanie usunięty. Pamiętaj, że wszystkie zasady ochrony aplikacji są już dostępne w usłudze Intune i możesz modyfikować dowolne zasady dostępu warunkowego. Aby uzyskać więcej informacji na temat modyfikowania zasad dostępu warunkowego, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Aby uzyskać dodatkowe informacje, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md) 

### <a name="device-configuration"></a>Konfiguracja urządzenia

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Wykres profilów urządzeń i lista stanów obejmuje wszystkie urządzenia w grupie <!-- 1449153 -->
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

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Pokazywanie identyfikatora rozmówcy w profilu osobistym — profil służbowy Android Enterprise <!--1098984 -->
Użytkownicy końcowy korzystający z profilu osobistego na urządzeniu mogą nie widzieć identyfikatora rozmówcy dla kontaktu służbowego. 

Ta aktualizacja wprowadza nowe ustawienie w obszarze **Android Enterprise** > **Ograniczenia dotyczące urządzeń** > **Ustawienia profilu służbowego**:
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

####  <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Blokowanie aparatu i przechwytywania ekranu w profilach służbowych Android Enterprise <!-- 1098977 -->
Podczas konfigurowania ograniczeń urządzenia z systemem Android można zablokować dwie nowe właściwości: 
- Aparat: blokuje dostęp do wszystkich aparatów w urządzeniu
- Przechwytywanie ekranu: blokuje przechwytywanie ekranu i wyświetlanie zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo

Dotyczy profilów służbowych Android Enterprise.

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Korzystanie z klienta Cisco AnyConnect dla systemu iOS <!-- 1333708 -->

W przypadku tworzenia nowego profilu sieci VPN dla systemu iOS są teraz dostępne dwie opcje: **Cisco AnyConnect** i **Cisco Legacy AnyConnect**. Profile Cisco AnyConnect obsługują wersję 4.0.7x i nowsze. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x oraz jego starszymi wersjami, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS. W przypadku platform systemów Android i macOS oraz profilu służbowego Android Enterprise nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nowe kroki rejestracji dla użytkowników na urządzeniach z systemem macOS High Sierra 10.13.2+ <!--1734567 -->
W systemie macOS High Sierra 10.13.2 wprowadzono pojęcie rejestracji w rozwiązaniu MDM „zatwierdzonej przez użytkownika”. Zatwierdzone rejestracje umożliwiają usłudze Intune zarządzanie niektórymi ustawieniami istotnymi dla zabezpieczeń. Aby uzyskać więcej informacji, zobacz dokumentację pomocy technicznej firmy Apple: https://support.apple.com/HT208019.

Urządzenia zarejestrowane przy użyciu aplikacji Portal firmy dla systemu macOS są traktowane jako „niezatwierdzone przez użytkownika”, chyba że użytkownik końcowy otworzy preferencje systemu i ręcznie wykona zatwierdzenie. Dlatego aplikacja Portal firmy dla systemu macOS teraz kieruje użytkowników systemu macOS 10.13.2 i nowszych do kroków ręcznego zatwierdzenia rejestracji pod koniec procesu rejestracji. Konsola administracyjna usługi Intune zgłasza fakt zatwierdzenia zarejestrowanego urządzenia przez użytkownika.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Urządzenia z systemem macOS zarejestrowane w oprogramowaniu Jamf można obecnie zarejestrować w usłudze Intune <!-- 2370684 -->
W wersjach 1.3 i 1.4 portalu firmy systemu macOS nie można było pomyślnie rejestrować urządzeń z oprogramowaniem Jamf w usłudze Intune. W wersji 1.4.2 portalu macOS rozwiązano ten problem.

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Zaktualizowane środowisko pomocy w aplikacji Portal firmy dla systemu Android <!-- 1631531 -->
Zaktualizowaliśmy środowisko pomocy w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla platformy Android. Teraz, gdy użytkownik napotka problem w aplikacji, może nacisnąć pozycję **Menu** > **Pomoc**, a następnie:
- Przekazać dzienniki diagnostyczne do firmy Microsoft.
- Wysłać wiadomość e-mail z opisem problemu i identyfikatorem zdarzenia do osoby odpowiedzialnej za pomoc techniczną w firmie.  

Aby sprawdzić zaktualizowane środowisko pomocy, przejdź do obszaru [Wysyłanie dzienników pocztą e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android) i [Wysyłanie błędów do firmy Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nowy wykres trendu niepowodzeń rejestracji i tabela z przyczynami niepowodzeń <!-- 1471783 -->
Na stronie Przeglądu rejestracji można wyświetlić trend niepowodzeń rejestracji i pięć najczęstszych przyczyn niepowodzeń. Klikając wykres lub tabelę, można przejść do szczegółów, aby znaleźć porady dotyczące rozwiązywania problemów i sugestie dotyczące korygowania.


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Usługi Advanced Threat Protection (ATP) i Intune są w pełni zintegrowane <!-- 1629303 -->

Funkcja [zaawansowanej ochrony przed zagrożeniami](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) pokazuje poziom ryzyka urządzeń z systemem Windows 10. W usłudze Windows Defender Security Center (portal ATP) można utworzyć połączenie z usługą Microsoft Intune. Po jego utworzeniu zostają użyte zasady zgodności z usługą Intune, aby określić dopuszczalny poziom zagrożenia. Jeśli poziom zagrożenia zostanie przekroczony, zasady dostępu warunkowego usługi Azure Active Directory (AD) mogą zablokować dostęp do różnych aplikacji w ramach danej organizacji.

Ta funkcja pozwala systemowi ATP skanować pliki, wykrywać zagrożenia oraz zgłaszać zdarzenia o podwyższonym ryzyku na urządzeniach z systemem Windows 10.

Zobacz temat [Enable ATP with conditional access in Intune](advanced-threat-protection.md) (Włączanie systemu ATP z dostępem warunkowym w usłudze Intune).

#### <a name="support-for-user-less-devices----1637553---"></a>Obsługa urządzeń bez użytkowników <!-- 1637553 -->
Usługa Intune oferuje możliwość oceny zgodności urządzenia bez użytkowników, takiego jak Microsoft Surface Hub. Zasady zgodności mogą stosować się do konkretnych urządzeń. Dzięki temu zgodność (i niezgodność) można określić dla urządzeń, które nie mają skojarzonego użytkownika.

#### <a name="delete-autopilot-devices----1713650---"></a>Usuwanie urządzeń rozwiązania Autopilot <!-- 1713650 -->
Administratorzy usługi Intune mogą [usuwać urządzenia z rozwiązaniem AutoPilot](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Ulepszona funkcja usuwania urządzeń <!--1832333 -->
Nie trzeba już wymagać usunięcia danych firmy ani resetować do ustawień fabrycznych przed [usunięciem urządzenia z usługi Intune](devices-wipe.md#delete-devices-from-the-intune-portal).

Aby zobaczyć nową funkcję, zaloguj się do usługi Intune i wybierz pozycje **Urządzenia** > **Wszystkie urządzenia** > nazwa urządzenia > **Usuń**.

Jeśli chcesz nadal otrzymywać powiadomienia o wyczyszczeniu lub wycofaniu, możesz użyć standardowego cyklu życia urządzenia, uruchamiając polecenie **Usuń dane firmy** oraz **Resetuj do ustawień fabrycznych**, a następnie polecenie **Usuń**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Odtwarzanie dźwięków w systemie iOS w trybie utraty <!-- 1947769 -->
Jeśli urządzenia z systemem iOS nadzorowane w rozwiązaniu do zarządzania urządzeniami przenośnymi są w [trybie utraty](device-lost-mode.md), możesz [odtwarzać dźwięk](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie z systemem iOS > **Przegląd** > **Więcej**). Dźwięk będzie odtwarzany w sposób ciągły aż do zakończenia trybu utraty na urządzeniu lub wyłączenia przez użytkownika dźwięku na urządzeniu. Dotyczy urządzeń z systemem iOS 9.3 lub nowszym.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Blokowanie wyników internetowych w wyszukiwaniach przeprowadzanych na urządzeniu usługi Intune lub zezwalanie na te wyniki <!--1972804-->

Administratorzy mogą teraz blokować internetowe wyniki wyszukiwań przeprowadzanych na urządzeniu.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Ulepszona obsługa komunikatów o błędach przekazywania certyfikatu wypychania Apple MDM <!-- 2172331 -->

Komunikat o błędzie zawiera wyjaśnienie mówiące o tym, że podczas odnawiania istniejącego certyfikatu rozwiązania MDM należy użyć tego samego identyfikatora Apple ID.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testowanie Portalu firmy dla systemu macOS na maszynach wirtualnych <!-- 2216679 -->

Opublikowaliśmy wskazówki ułatwiające administratorom IT testowanie aplikacji Portal firmy dla systemu macOS na maszynach wirtualnych z programami Parallels Desktop i VMware Fusion. Dalsze informacje znajdują się w sekcji [Rejestrowanie maszyn wirtualnych z systemem macOS na potrzeby testowania](macos-enroll.md#enroll-virtual-macos-machines-for-testing).

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


### <a name="user-interface"></a>Interfejs użytkownika

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Ulepszone kafelki urządzenia w aplikacji Portal firmy dla systemu Windows 10 <!--2213364 -->

Kafelki zostały zaktualizowane pod kątem zwiększenia dostępności dla użytkowników z ograniczonymi możliwościami widzenia oraz poprawienia sposobu współdziałania z narzędziami do odczytywania ekranu.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Wysyłanie raportów diagnostycznych z aplikacji Portal firmy dla systemu macOS <!-- 2216677 -->
Aplikacja Portal firmy dla urządzeń z systemem macOS została zaktualizowana pod kątem ulepszenia sposobu raportowania błędów dotyczących usługi Intune przez użytkowników. W aplikacji Portal firmy pracownicy mogą:

- Przekazywać raporty diagnostyczne bezpośrednio do zespołu deweloperów firmy Microsoft.
- Wysłać wiadomość e-mail z identyfikatorem zdarzenia do zespołu pomocy technicznej IT firmy.

Aby uzyskać więcej informacji, zobacz [Wysyłanie błędów w przypadku systemu macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>Usługa Intune dostosowuje się do systemu Fluent Design System w aplikacji Portal firmy dla systemu Windows 10 <!-- 1195010 -->
Aplikacja Portal firmy usługi Intune dla systemu Windows 10 została zaktualizowana w celu dodania [widoku nawigacji systemu Fluent Design System](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Wzdłuż boku aplikacji znajduje się statyczna, pionowa lista wszystkich stron najwyższego poziomu. Kliknij dowolny link, aby szybko wyświetlać strony i przełączać się między nimi. Jest to pierwsza z kilku aktualizacji, które będą wprowadzane w ramach naszych ciągłych wysiłków mających na celu stworzenie bardziej adaptacyjnego, empatycznego, znanego środowiska pracy w usłudze Intune. Aby wyświetlić zaktualizowany wygląd, przejdź do obszaru [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="march-2018"></a>Marzec 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Alerty dotyczące wygasających aplikacji biznesowych (LOB) dla systemu iOS dla usługi Microsoft Intune <!-- 748789 -->

W witrynie Azure Portal usługa Intune powiadomi Cię o aplikacjach biznesowych dla systemu iOS, które wkrótce wygasną. Po przekazaniu nowej wersji aplikacji biznesowej dla systemu iOS usługa Intune usunie powiadomienie o wygaśnięciu z listy aplikacji. Powiadomienie o wygaśnięciu będzie aktywne tylko dla nowo przekazanych aplikacji biznesowych dla systemu iOS. Ostrzeżenie zostanie wyświetlone 30 dni przed wygaśnięciem profilu aprowizacji aplikacji biznesowych dla systemu iOS. Po jego wygaśnięciu stan alertu zostanie zmieniony na Wygasł.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Dostosowywanie motywów aplikacji Portal firmy za pomocą kodów szesnastkowych <!--1049561 -->

Kolor motywów w aplikacjach Portal firmy można dostosować przy użyciu kodów szesnastkowych. Po wprowadzeniu kodu szesnastkowego usługa Intune określa kolor tekstu, który zapewni najwyższy poziom kontrastu między tekstem a tłem. Podgląd koloru tekstu i logo firmy na tle wybranego koloru możesz wyświetlić, wybierając pozycję **Aplikacje klienckie** > **Portal firmy**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup dla programu Android Enterprise <!-- 1813081 -->

System Android Enterprise (wcześniej znany jako Android for Work) obsługuje dołączanie i wykluczanie grup, ale nie obsługuje wstępnie utworzonych grup wbudowanych **Wszyscy użytkownicy** i **Wszystkie urządzenia**. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome----2258071---"></a>Eksportowanie wszystkich urządzeń do plików CSV w przeglądarce IE, Microsoft Edge lub Chrome <!-- 2258071 -->
W obszarze **Urządzenia** > **Wszystkie urządzenia** możesz **wyeksportować** urządzenia do sformatowanej listy w pliku CSV. Użytkownicy przeglądarki Internet Explorer (IE) posiadający ponad 10 000 urządzeń mogą pomyślnie wyeksportować swoje urządzenia do wielu plików. Każdy plik może zawierać maksymalnie 10 000 urządzeń.

Użytkownicy przeglądarek Microsoft Edge oraz Chrome posiadający ponad 30 000 urządzeń mogą pomyślnie wyeksportować swoje urządzenia do wielu plików. Każdy plik może zawierać maksymalnie 30 000 urządzeń.

Funkcja [zarządzania urządzeniami](device-management.md) zawiera bardziej szczegółowe informacje dotyczące działań, które można wykonać względem zarządzanych urządzeń.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Nowe usprawnienia zabezpieczeń w usłudze Intune  <!-- 1637539 -->   

Wprowadziliśmy przełącznik w usłudze Intune na platformie Azure, którego klienci autonomicznej usługi Intune mogą użyć w celu traktowania urządzeń bez żadnych przypisanych zasad jako **zgodne** (wyłączona funkcja zabezpieczeń) lub **niezgodne** (włączona funkcja zabezpieczeń). W ten sposób dostęp do zasobów będzie możliwy dopiero po ocenie zgodności urządzenia.

Wpływ tej funkcji na klientów będzie zależeć od tego, czy zostały już przypisane zasady zgodności, czy nie.

- W przypadku nowych oraz istniejących kont i braku przypisanych do urządzeń zasad zgodności, przełącznik zostanie automatycznie ustawiony w na wartość **Zgodne**. Ta funkcja jest domyślnie wyłączona w konsoli. Nie wpływa to w żaden sposób na użytkowników końcowych.
- W przypadku istniejących kont i posiadania jakichkolwiek urządzeń z przypisanymi do nich zasad zgodności, przełącznik zostanie automatycznie ustawiony na wartość **Niezgodne**. Wraz z wprowadzeniem aktualizacji z marca ta funkcja jest domyślnie włączona.

W przypadku używania zasad zgodności z dostępem warunkowym i włączenia tej funkcji wszystkie urządzenia, które nie mają przypisanych jakichkolwiek zasad zgodności, zostaną zablokowane przez funkcję dostępu warunkowego. Skojarzeni z tymi urządzeniami użytkownicy końcowi, którzy wcześniej mieli dostęp do poczty e-mail, utracą ten dostęp, chyba że do wszystkich urządzeń zostaną przypisane jakiekolwiek zasady zgodności.   

Pamiętaj, że chociaż domyślny stan przełącznika jest wyświetlany w interfejsie użytkownika od razu po wprowadzeniu aktualizacji usługi Intune z marca, stan tego przełącznika nie jest od razu wymuszany. Wszelkie zmiany dotyczące tego przełącznika nie będą miały wpływu na zgodność urządzenia do momentu wprowadzenia pakietu testowego na koncie z działającym przełącznikiem. Poinformujemy Cię za pośrednictwem Centrum wiadomości o zakończeniu wprowadzania pakietu testowego na koncie. Może to potrwać kilka dni po zaktualizowaniu usługi Intune w marcu.

**Dodatkowe informacje**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Rozszerzone wykrywanie jailbreaku <!-- 846515 -->

Ulepszone wykrywanie zdjęcia zabezpieczeń systemu jest nowym ustawieniem zgodności, które usprawnia sposób, w jaki usługa Intune ocenia urządzenia ze zdjętymi zabezpieczeniami systemu. To ustawienie powoduje częstsze ewidencjonowanie urządzenia w usłudze Intune z wykorzystaniem usług lokalizacyjnych urządzenia, co ma wpływ na użycie baterii.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetowanie haseł dla urządzeń z systemem Android O <!-- 1238299 -->
Możliwe będzie resetowanie haseł zarejestrowanych urządzeń z systemem Android 8.0 z profilami służbowymi. Po wysłaniu żądania „Resetuj hasło” do urządzenia z systemem Android 8.0 ustawi ono nowe hasło odblokowania urządzenia lub wezwanie zarządzanego profilu dla bieżącego użytkownika. Hasło lub wezwanie jest wysyłane i zaczyna obowiązywać natychmiast.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Określanie zasad zgodności dla urządzeń w grupach urządzeń <!--1307012 -->

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
Usługa Intune zapewnia kontrolę nad [zarządzaniem aktualizacjami oprogramowania](windows-update-for-business-configure.md). Ta aktualizacja udostępnia właściwość <strong>Testy po ponownym uruchomieniu</strong>, która jest domyślnie włączona. Aby pominąć typowe testy przeprowadzane po ponownym uruchomieniu urządzenia (takie jak aktywni użytkownicy, poziom naładowania baterii itp.), wybierz pozycję <strong>Pomiń</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nowe kanały systemu Windows 10 Insider Preview dostępne dla pierścieni wdrażania <!-- 1746293 -->
Masz teraz możliwość wybrania następujących kanałów obsługi systemu Windows 10 Insider Preview podczas tworzenia pierścienia wdrażania systemu Windows 10:
- Kompilacja Windows Insider &#8208; wersja szybka
- Kompilacja Windows Insider &#8208; wersja wolna
- Wydanie kompilacji Windows Insider 

Aby uzyskać więcej informacji o tych kanałach, zobacz [Manage Insider Preview Builds](https://insider.windows.com/for-business-organization-admin/) (Zarządzanie kompilacjami Insider Preview).   
Aby uzyskać więcej informacji na temat tworzenia kanałów wdrażania w usłudze Intune, zobacz [Zarządzanie aktualizacjami oprogramowania w usłudze Intune](windows-update-for-business-configure.md).

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

### <a name="intune-apps"></a>Aplikacje usługi Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->

Korzystając z usługi Azure Active Directory (Azure AD), można teraz ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure. Aby uzyskać dodatkowe informacje, zobacz [Access controls in Azure Active Directory conditional access (Elementy kontroli dostępu dla dostępu warunkowego w usłudze Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aktualizacje wizualne aplikacji Portal firmy dla systemu Android <!--976944 -->

Zaktualizowaliśmy aplikację Portal firmy dla systemu Android, aby była zgodna z wytycznymi [Material Design](https://material.io/) systemu Android. Obrazy nowych ikon możesz zobaczyć w artykule [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

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

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Ulepszenia języka w aplikacji Portal firmy dla systemu Windows <!-- 1683758 -->
Poprawiliśmy język w aplikacji Portal firmy dla systemu Windows 10, aby była ona bardziej przyjazna dla użytkownika i właściwa dla Twojej firmy. Aby wyświetlić niektóre przykładowe obrazy przedstawiające wprowadzone aktualizacje, zobacz [Co nowego w aplikacji interfejsu użytkownika](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Nowości w naszej dokumentacji dotyczące ochrony prywatności użytkowników <!-- 1440709 -->
W ramach dążenia do zapewnienia użytkownikom końcowym większej kontroli nad ich danymi i ochroną prywatności zostały opublikowane aktualizacje dotyczące naszej dokumentacji, w których opisano sposób wyświetlania i usuwania danych przechowywanych lokalnie przy użyciu aplikacji Portal firmy. Te aktualizacje można znaleźć w następujących artykułach:

- **Android**: [Jak usunąć urządzenie z systemem Android z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android (jeśli użytkownik odrzucił warunki użytkowania**: [Usuwanie urządzenia z zarządzania w przypadku odrzucenia warunków użytkowania](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [Usuwanie urządzenia z systemem iOS z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [Usuwanie urządzenia z systemem Windows z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>Luty 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 -->

Usługa Intune obsługuje teraz rejestrowanie urządzeń z maksymalnie 100 różnymi kontami usług [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) i [Apple School Manager](apple-school-manager-set-up-ios.md). Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Wyświetlanie ograniczeń rejestracji dla poszczególnych użytkowników <!-- 1634444 eeready wnready -->
W bloku **Rozwiązywanie problemów** możesz teraz wyświetlić [ograniczenia rejestracji](enrollment-restrictions-set.md) obowiązujące poszczególnych użytkowników, wybierając pozycję **Ograniczenia rejestracji** z listy **Przypisania**.

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

#### <a name="new-settings-for-the-microsoft-edge-browser---1469166---"></a>Nowe ustawienia przeglądarki Microsoft Edge <!--1469166 -->
Dla urządzeń z przeglądarką Microsoft Edge są dostępne [dwa nowe ustawienia](device-restrictions-windows-10.md#microsoft-edge-browser): **Ścieżka do pliku ulubionych** i **Zmiany w ulubionych**.

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

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Obsługa aplikacji offline ze Sklepu Microsoft dla Firm <!--1222672-->
Aplikacje offline zakupione w Sklepie Microsoft dla Firm są teraz synchronizowane z witryną Azure Portal. Można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, nie przez sklep.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Uniemożliwianie użytkownikom końcowym ręcznego dodawania i usuwania kont w profilu służbowym <!-- 1728700 -->

Podczas wdrażania aplikacji usługi Gmail w profilu programu Android for Work można teraz uniemożliwić użytkownikom końcowym ręczne dodawanie i usuwanie kont w profilu służbowym przy użyciu ustawienia **Dodawanie i usuwanie kont** w profilu ograniczeń programu Android for Work.

<!-- ########################## -->
## <a name="january-2018"></a>Styczeń 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną <!-- 1639263 -->
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

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Zasady konfiguracji aplikacji możesz przypisywać do grup, dołączając i wykluczając przypisania  <!-- 1480316 -->

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników i urządzeń za pomocą kombinacji dołączania i wykluczania przypisań. Przypisania można wybrać jako niestandardowy wybór grup albo jako grupę wirtualną. Grupa wirtualna może obejmować **wszystkich użytkowników**, **wszystkie urządzenia** lub **wszystkich użytkowników i wszystkie urządzenia**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10   <!-- 903672(archived), 1119689 -->  
Możesz tworzyć zasady uaktualniania wersji systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wersji systemu Windows 10, zobacz artykuł [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zasady dostępu warunkowego dla usługi Intune są dostępne tylko w witrynie Azure Portal  <!-- 1737088 1634311 -->

Począwszy od tego wydania, musisz konfigurować zasady dostępu warunkowego i zarządzać nimi w witrynie [Azure Portal](https://portal.azure.com) w bloku **Azure Active Directory** > **Dostęp warunkowy**. Dla wygody możesz przejść do tego bloku z usługi Intune w witrynie Azure Portal w obszarze **Intune** > **Dostęp warunkowy**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizacje wiadomości e-mail dotyczących zgodności <!--1637547 -->

Wiadomość e-mail wysłana w celu zgłoszenia niezgodnego urządzenia zawiera szczegóły dotyczące niezgodnego urządzenia.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nowa funkcja akcji „Rozwiąż” dla urządzeń z systemem Android <!--1583480-->

Aplikacja Portal firmy dla systemu Android rozwija akcję „Rozwiąż” dla pozycji **Zaktualizuj ustawienia urządzenia**, aby rozwiązać [problemy dotyczące szyfrowania urządzenia](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Zdalne blokowanie dostępne w aplikacji Portal firmy dla systemu Windows 10 <!--676506-->
Użytkownicy końcowi mogą teraz zdalnie blokować swoje urządzenia w aplikacji Portal firmy dla systemu Windows 10. Opcja nie będzie wyświetlana dla wybranego urządzenia lokalnego, którego aktywnie używają.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Łatwiejsze rozwiązywanie problemów ze zgodnością aplikacji Portal firmy dla systemu Windows 10 <!--676546-->
Użytkownicy końcowi mający urządzenia z systemem Windows będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem.

<!-- ########################## -->
## <a name="december-2017"></a>Grudzień 2017

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nowe ustawienie automatycznego ponownego wdrażania <!-- 1469168 -->
Ustawienie **Automatyczne ponowne wdrażanie** pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania. To ustawienie można znaleźć w obszarze Windows 10 > Ograniczenia dotyczące urządzeń > Ogólne > Automatyczne ponowne wdrażanie. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 w usłudze Intune](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Obsługa dodatkowych wersji źródła w zasadach uaktualniania wersji systemu Windows 10  <!-- 903672,  1119689 -->
Zasady uaktualniania wersji systemu Windows 10 umożliwiają teraz uaktualnianie dodatkowych wersji systemu Windows 10 (Windows 10 Pro, Windows 10 Pro for Education, Windows 10 Cloud itp.). Przed tą wersją obsługiwane ścieżki uaktualniania wersji były bardziej ograniczone. Więcej szczegółów znajduje się w temacie [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nowe ustawienia profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center (WDSC) <!-- 1335507 -->

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

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Nazwa podmiotu klienta może zawierać zmienną AAD_DEVICE_ID  <!-- 1468599 -->

Tworząc profil certyfikatu SCEP w usłudze Intune, można teraz użyć zmiennej AAD_DEVICE_ID podczas kompilowania niestandardowej nazwy podmiotu.   Gdy żądanie certyfikatu jest przesyłane przy użyciu tego profilu SCEP, zmienna jest zastępowana identyfikatorem urządzenia usługi AAD należącym do urządzenia wysyłającego żądanie certyfikatu.


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Zarządzanie urządzeniami z systemem macOS zarejestrowanymi w programie Jamf przy użyciu aparatu zgodności urządzenia usługi Intune <!-- 1592747 -->
Korzystając z programu Jamf, można teraz wysyłać informacje o stanie urządzenia z systemem macOS do usługi Intune, która następnie oceni je pod kątem zgodności z zasadami określonymi w konsoli usługi Intune. W oparciu o stan zgodności urządzenia, a także pozostałe warunki (takie jak lokalizacja, ryzyko związane z użytkownikiem itp.) dostęp warunkowy będzie wymuszać zgodność dla urządzeń z systemem macOS uzyskujących dostęp do chmury i lokalnych aplikacji połączonych z usługą Azure Active Directory oraz usługą Office 365. Dowiedz się więcej o [konfigurowaniu integracji programu Jamf](conditional-access-integrate-jamf.md) i [wymuszaniu zgodności dla urządzeń zarządzanych przez program Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nowa akcja dotycząca urządzenia z systemem iOS   <!-- 1424701 -->

Możliwe jest teraz zamykanie nadzorowanych urządzeń z systemem iOS 10.3. Ta akcja natychmiast wyłącza urządzenie bez ostrzeżenia dla użytkownika końcowego. Akcję **Wyłącz (tylko nadzorowane)** można znaleźć we właściwościach urządzenia po wybraniu urządzenia w obciążeniu **Urządzenie**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Blokowanie zmian daty/godziny na urządzeniach z systemem Samsung Knox <!-- 1468103 -->

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

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalacja aplikacji pakietu Office na urządzeniach z systemem macOS <!-- 1494311 -->
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

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Usługa Intune obsługuje niedozwolone aplikacje rozwiązania Windows Information Protection <!-- 1479103 -->
Niedozwolone aplikacje można określić w usłudze Intune. Jeśli aplikacja zostanie ustawiona jako niedozwolona, nie może uzyskiwać dostępu do informacji firmowych. Jest to sytuacja odwrotna, co w przypadku listy dozwolonych aplikacji. Aby uzyskać więcej informacji, zobacz [Zalecana lista niedozwolonych aplikacji na potrzeby rozwiązania Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).

<!-- ########################## -->
## <a name="november-2017"></a>Listopad 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Rozwiązywanie problemów z rejestracją  <!-- 746324 -->

Problemy z rejestracją są teraz widoczne dla użytkownika w obszarze roboczym **Rozwiązywanie problemów**. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Ograniczenia rejestracji przypisane do grupy <!-- 747598 -->

Administratorzy usługi Intune będą mogli [tworzyć niestandardowe ograniczenia rejestracji dotyczące typu urządzeń i limitu urządzeń dla grup użytkowników](enrollment-restrictions-set.md).

Witryna Azure Portal usługi Intune pozwala utworzyć maksymalnie 25 wystąpień poszczególnych typów ograniczeń, które można przypisać do grup użytkowników. Ograniczenia przypisane do grupy zastępują ograniczenia domyślne.

Wszystkie wystąpienia typu ograniczenia są przechowywane na ściśle uporządkowanej liście. Porządek ten określa wartości priorytetów na potrzeby rozwiązywania konfliktów. Jeśli użytkownika dotyczy więcej niż jedno wystąpienie ograniczeń, pod uwagę brane jest tylko wystąpienie o najwyższej wartości priorytetu. Priorytet danego wystąpienia można zmienić, przeciągając je do innej pozycji na liście.

Funkcja ta zostanie udostępniona podczas migracji ustawień programu Android for Work z menu rejestracji programu Android for Work do menu ograniczeń rejestracji. Ponieważ ta migracja może zająć kilka dni, zanim zostanie włączone przypisanie grupy do ograniczeń rejestracji, konto może zostać uaktualnione o inne funkcje wprowadzane w wersji listopadowej.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Obsługa wielu łączników usługi rejestracji urządzeń sieciowych (NDES) <!-- 1528104 -->

Usługa rejestracji urządzeń sieciowych (Network Device Enrollment Service, NDES) umożliwia urządzeniom przenośnym działającym bez poświadczeń domeny uzyskiwanie certyfikatów przy użyciu dodatku Prosty protokół rejestrowania certyfikatów (Simple Certificate Enrollment Protocol, SCEP).
Aktualizacja wprowadza obsługę wielu łączników usługi NDES.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Zarządzanie urządzeniami programu Android for Work w sposób niezależny od urządzeń z systemem Android <!-- 1490731 EEready-->

Usługa Intune obsługuje zarządzanie rejestracją urządzeń programu Android for Work w sposób niezależny od platformy Android. Opcje zarządzania tymi ustawieniami są dostępne w obszarze **Rejestrowanie urządzenia** > **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń**. (Wcześniej znajdowały się one w obszarze **Rejestrowanie urządzeń** > **Rejestracja w programie Android for Work** > **Ustawienia rejestracji programu Android for Work**).

Domyślnie ustawienia urządzeń programu Android for Work są takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.

Jeśli zablokujesz rejestrację urządzeń osobistych w programie Android for Work, będzie można rejestrować tylko firmowe urządzenia z systemem Android.

Podczas pracy z nowymi ustawieniami zwróć uwagę na następujące kwestie:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Jeśli wcześniej nie dodano rejestracji w programie Android for Work

Nowa platforma Android for Work jest zablokowana w domyślnych ograniczeniach typów urządzeń. Po dodaniu tej funkcji możesz zezwolić urządzeniom na rejestrację w programie Android for Work. Aby to zrobić, zastąp domyślne ograniczenie typów urządzeń — zmień je lub utwórz nowe ograniczenie.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Jeśli dodano rejestrację w programie Android for Work

Jeśli wcześniej dołączono do programu, sytuacja zależy od wybranego ustawienia:

| Ustawienie | Stan programu Android for Work w domyślnym ograniczeniu typów urządzeń | Uwagi |
| --- | --- | --- |
| **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** | Zablokowane | Wszystkie urządzenia z systemem Android należy zarejestrować bez programu Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** | Dozwolone | Wszystkie urządzenia z systemem Android, które obsługują program Android for Work, należy zarejestrować w programie Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko dla użytkowników w tych grupach** | Zablokowane | Utworzono oddzielne zasady ograniczeń typów urządzeń, które przesłaniają domyślne zasady. Zasady te definiują wcześniej wybrane grupy, zezwalając na rejestrację w programie Android for Work. Użytkownicy z wybranych grup zachowają możliwość rejestrowania urządzeń programu Android for Work. Pozostali użytkownicy nie mogą rejestrować się w programie Android for Work. |

We wszystkich przypadkach zamierzone zasady są zachowywane. Nie są wymagane żadne działania użytkownika w celu zachowania możliwości korzystania z programu Android for Work w środowisku — zarówno w skali ogólnej, jak i w odniesieniu do poszczególnych grup.

### <a name="google-play-protect-support-on-android----908720---"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720 -->

Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje teraz funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet. Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania.
Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play. Jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect, dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy.

- Dowiedz się [Jak utworzyć zasady zgodności urządzenia w celu włączenia funkcji Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-android).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protokół tekstowy dostępny w aplikacjach zarządzanych <!-- 1414050  -->

Aplikacje zarządzane przez zestaw SDK aplikacji usługi Intune mogą wysyłać wiadomości SMS.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Raport instalacji aplikacji został zaktualizowany, aby obejmować stan Oczekująca instalacja <!-- 1249446 -->  

Raport **Stan instalacji aplikacji**, dostępny dla każdej aplikacji za pośrednictwem listy **Aplikacja** w obciążeniu **Aplikacje klienckie**, zawiera teraz licznik **Oczekująca instalacja** dla użytkowników i urządzeń.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Interfejs API spisu aplikacji dla systemu iOS 11 na potrzeby wykrywania zagrożeń mobilnych <!-- 1391759 -->

Usługa Intune zbiera informacje dotyczące spisu aplikacji z urządzeń osobistych i firmowych i udostępnia je dostawcom usługi wykrywania zagrożeń mobilnych, na przykład aplikacji Lookout for Work. Możesz zbierać informacje o spisie aplikacji z urządzeń z systemem iOS 11 lub nowszym.

**Spis aplikacji**  
Spisy pochodzące zarówno z urządzeń osobistych, jak i urządzeń firmowych z systemem iOS 11 lub nowszym są wysyłane do dostawcy usługi MTD. Spis aplikacji zawiera następujące dane:

 - Identyfikator aplikacji
 - Wersja aplikacji
 - Krótki numer wersji
 - Nazwa aplikacji
 - Rozmiar pakietu aplikacji
 - Dynamiczny rozmiar aplikacji
 - Wskazanie, czy aplikacja została zweryfikowana
 - Wskazanie, czy aplikacja jest zarządzana

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrowanie użytkowników i urządzeń z hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune <!-- 1463747 wnready -->
Dostępne są teraz nowe procesy i narzędzia służące do przenoszenia użytkowników i ich urządzeń z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune w witrynie Azure Portal, co umożliwia wykonywanie następujących zadań:
- Kopiowanie zasad i profilów z konsoli programu Configuration Manager do usługi Intune w witrynie Azure Portal
- Przenoszenie podzbioru użytkowników do usługi Intune w witrynie Azure Portal przy zachowaniu pozostałych w ramach hybrydowego zarządzania urządzeniami przenośnymi
- Migrowanie urządzeń do usługi Intune w witrynie Azure Portal bez konieczności ich ponownego rejestrowania

Aby uzyskać więcej informacji, zobacz [Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange  <!-- 676614 -->
Gdy łącznik programu Exchange utworzy połączenie z programem Exchange za pomocą określonego zabezpieczenia dostępu kodu, będzie mieć możliwość odnajdywania innych zabezpieczeń dostępu kodu. Jeśli podstawowe zabezpieczenia dostępu kodu będą niedostępne, łącznik przejdzie w tryb failover, korzystając z innych zabezpieczeń dostępu kodu (jeśli będą dostępne) do momentu przywrócenia dostępności podstawowych zabezpieczeń dostępu kodu. Szczegółowe informacje znajdują się w temacie [Obsługa wysokiej dostępności łącznika lokalnego programu Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Zdalne ponowne uruchamianie urządzenia z systemem iOS (tylko tryb nadzorowany) <!-- 1424595 -->

Przy użyciu akcji urządzenia możesz teraz wyzwolić ponowne uruchomienie nadzorowanego urządzenia z systemem iOS 10.3 lub nowszym. Aby uzyskać więcej informacji na temat używania akcji ponownego uruchamiania urządzenia, zobacz [Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune](device-restart.md).

> [!Note]
> To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS z blokadą opartą na kodzie dostępu nie połączą się z siecią Wi-Fi po ponownym uruchomieniu. Ponadto nawiązanie połączenia z serwerem może nie być możliwe.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Obsługa logowania jednokrotnego dla systemu iOS <!-- 1333645 -->  

Użytkownicy systemu iOS mogą korzystać z logowania jednokrotnego. Aplikacje dla systemu iOS, które poszukują poświadczeń użytkownika w ładunku logowania jednokrotnego, zachowują swoją funkcjonalność po zaktualizowaniu konfiguracji ładunku. Nazwę główną i obszar można również skonfigurować przy użyciu nazwy UPN i identyfikatora urządzenia w usłudze Intune. Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Dodanie aplikacji „Znajdź mój iPhone” dla urządzeń osobistych <!--1427287-->
Może teraz sprawdzić, czy urządzenia z systemem iOS mają włączoną blokadę aktywacji. Funkcja ta była wcześniej dostępna w klasycznym portalu usługi Intune.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Zdalne blokowanie urządzeń zarządzanych z systemem macOS przy użyciu usługi Intune <!-- 1437691 -->

Zgubione urządzenie z systemem macOS można zablokować przez ustawienie 6-cyfrowego numeru PIN odzyskiwania. Gdy blokada jest aktywna, do momentu wysłania innej akcji urządzenia na ekranie jest widoczny blok **Przegląd urządzenia** z monitem o numer PIN.

Aby uzyskać więcej informacji, zobacz [Zdalne blokowanie urządzeń zarządzanych przy użyciu usługi Intune](device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Obsługa nowych szczegółów profilu SCEP <!-- 1559808 -->

Administratorzy mogą teraz określić dodatkowe ustawienia podczas tworzenia profilu SCEP na platformach Windows, iOS, macOS i Android.  Można na przykład ustawić kod IMEI, numer seryjny lub nazwę pospolitą obejmującą adres e-mail w formacie nazwy podmiotu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachowywanie danych podczas resetowania do ustawień fabrycznych  <!--1588489 -->
W przypadku resetowania do ustawień fabrycznych systemu Windows 10 w wersji 1709 oraz nowszych dostępna jest nowa funkcja. Administratorzy mogą wskazać, czy informacje o rejestracji urządzenia i inne aprowizowane dane mają zostać zachowane podczas resetowania urządzenia do ustawień fabrycznych.

Podczas resetowania do ustawień fabrycznych są zachowywane następujące dane:
- Konta użytkowników skojarzone z urządzeniem
- Stan komputera (dołączenie do domeny, dołączenie do usługi Azure Active Directory)
- Rejestracja w usłudze zarządzania urządzeniami przenośnymi
- Aplikacje zainstalowane przez producenta OEM (aplikacje ze Sklepu i aplikacje Win32)
- Profil użytkownika
- Dane użytkownika przechowywane poza profilem użytkownika
- Informacje o logowaniu automatycznym użytkownika

Następujące dane nie są zachowywane:
- Pliki użytkownika
- Aplikacje zainstalowane przez użytkownika (aplikacje ze Sklepu i aplikacje Win32)
- Ustawienia urządzenia inne niż domyślne


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Wyświetlanie przypisań pierścienia aktualizacji systemu Windows 10 <!-- 1621837 -->
Podczas **rozwiązywania problemów** są widoczne wszystkie przypisania pierścieni aktualizacji systemu Windows 10 dla aktualnie wybranego użytkownika.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Ustawienia częstotliwości raportowania usługi Zaawansowana ochrona przed zagrożeniami usługi Windows Defender  <!-- 1455974  -->
Usługa Zaawansowana ochrona przed zagrożeniami usługi Windows Defender (WDATP, Windows Defender Advanced Threat Protection) pozwala administratorom zmieniać częstotliwość raportowania dla zarządzanych urządzeń. Nowa opcja — **Usprawnij częstotliwość raportowania danych telemetrycznych** — umożliwia usłudze WDATP częstsze zbieranie danych i ocenianie ryzyka. Domyślne ustawienie raportowania pozwala zoptymalizować szybkość i wydajność. Zwiększenie częstotliwości raportowania może być przydatne w przypadku urządzeń narażonych na wysokie ryzyko. To ustawienie znajduje się w profilu usługi **Windows Defender ATP** w **konfiguracji urządzeń**.

### <a name="audit-updates----1412961---"></a>Aktualizacje inspekcji <!-- 1412961 -->  
Inspekcje w usłudze Intune udostępniają rejestr operacji zmian dotyczących usługi Intune.  Wszystkie operacje tworzenia, aktualizowania, usuwania i zadań zdalnych są przechwytywane i przechowywane przez jeden rok.  Witryna Azure Portal udostępnia filtrowany widok danych inspekcji poszczególnych obciążeń z ostatnich 30 dni.  Dostępny jest odpowiedni interfejs API programu Graph, umożliwiający pobieranie danych inspekcji z ostatniego roku.

Inspekcje można znaleźć w grupie **MONITOR**. Dla każdego obciążenia dostępny jest element menu **Dzienniki inspekcji**.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Aplikacja Portal firmy dla systemu macOS jest dostępna <!--1541700-->
Aplikacja Portal firmy w usłudze Intune dla systemu macOS została zaktualizowana i zoptymalizowana, aby prawidłowo wyświetlać wszystkie informacje i powiadomienia o zgodności potrzebne użytkownikom do wszystkich zarejestrowanych urządzeń. Po wdrożeniu aplikacji Portal firmy w usłudze Intune na urządzeniu usługa Microsoft AutoUpdate dla systemu macOS zapewni jej aktualizacje. Nową wersję aplikacji Portal firmy w usłudze Intune dla systemu macOS można pobrać, logując się do witryny sieci Web aplikacji Portal firmy w usłudze Intune przy użyciu urządzenia z systemem macOS.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Aplikacja Microsoft Planner znajduje się obecnie na liście zarządzania aplikacjami mobilnymi (MAM) zawierającej zatwierdzone aplikacje  <!-- 1248473 -->
Aplikacja Microsoft Planner dla systemów iOS i Android należy obecnie do zatwierdzonych aplikacji funkcji zarządzania aplikacjami mobilnymi (MAM). Aplikację można skonfigurować za pomocą bloku Intune App Protection w witrynie Azure Portal na potrzeby wszystkich dzierżaw.
- Więcej informacji znajduje się na [liście zatwierdzonych aplikacji w funkcji zarządzania aplikacjami mobilnymi ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Częstotliwość aktualizacji wymagań dotyczących sieci VPN dla aplikacji na urządzeniach z systemem iOS   <!-- 1547061 -->  
Administratorzy mogą obecnie usuwać wymagania dotyczące sieci VPN dla aplikacji na urządzeniach z systemem iOS; operacja obejmie urządzenia po kolejnym zaewidencjonowaniu w usłudze Intune, które zwykle następuje w ciągu 15 minut.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Obsługa pakietu administracyjnego programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->
Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange jest obecnie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Dzięki tej funkcji dostępne są różne sposoby monitorowania usługi, jeśli trzeba rozwiązać problemy.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Współzarządzanie urządzeniami z systemem Windows 10  <!-- 1243445 -->
Współzarządzanie to rozwiązanie, które łączy zarządzanie tradycyjne z nowoczesnym i udostępnia ścieżkę umożliwiającą wprowadzanie zmian przy użyciu podejścia etapowego. Zasadniczo współzarządzanie jest rozwiązaniem, w którym urządzenia z systemem Windows 10 są jednocześnie zarządzane przez program Configuration Manager i usługę Microsoft Intune, a także połączone z usługami Active Directory (AD) i Azure Active Directory (Azure AD).  Taka konfiguracja umożliwia przyszłą modernizację w tempie odpowiednim dla organizacji, jeśli nie można przenieść wszystkiego naraz.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Ograniczanie rejestracji systemu Windows na podstawie wersji systemu operacyjnego <!-- 245498 -->
Jako administrator usługi Intune możesz teraz określić minimalną i maksymalną wersję systemu Windows 10 na potrzeby rejestracji urządzeń. Ograniczenia te można ustawić w bloku **Konfiguracja platformy**.

Usługa Intune będzie nadal obsługiwała rejestrowanie komputerów i telefonów z systemem Windows 8.1. Jednak tylko wersje systemu Windows 10 można ustawić z limitami minimalnym i maksymalnym. Aby zezwolić na rejestrowanie urządzeń z systemem w wersji 8.1, minimalny limit należy pozostawić pusty.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alerty dla urządzeń nieprzypisanych w rozwiązaniu Windows AutoPilot  <!-- 1631236 -->
Dostępny jest nowy alert dotyczący urządzeń nieprzypisanych w programie Windows AutoPilot na stronie **Microsoft Intune** > **Rejestracja urządzeń** > **Przegląd**. Ten alert pokazuje, ile urządzeń z programu AutoPilot nie ma przypisanych profilów wdrożenia programu AutoPilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń w programie Windows AutoPilot. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Przycisk Odśwież dla listy urządzeń    <!-- 1333581 -->
Ponieważ lista urządzeń nie jest odświeżana automatycznie, można teraz używać nowego przycisku Odśwież, który służy do aktualizowania urządzeń wyświetlanych na liście.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Obsługa urzędu certyfikacji (CA) Symantec Cloud  <!-- 1333638 -->    
Usługa Intune obsługuje teraz urząd certyfikacji Symantec Cloud, co pozwala łącznikowi Intune Certificate Connector na wystawianie certyfikatów PKCS z urzędu certyfikacji Symantec Cloud dla urządzeń zarządzanych przez usługę Intune. Jeśli łącznik certyfikatów usługi Intune jest już używany z urzędem certyfikacji (CA) firmy Microsoft, można wykorzystać istniejącą konfigurację łącznika certyfikatów usługi Intune w celu dodania obsługi urzędu certyfikacji firmy Symantec.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nowe elementy dodane do spisu urządzeń   <!--1404455 -->
Na potrzeby [spisu wykonywanego przez zarejestrowane urządzenia](device-inventory.md) są teraz dostępne następujące nowe elementy:

- Adres MAC sieci Wi-Fi
- Całkowita ilość miejsca
- Całkowita ilość wolnego miejsca
- MEID
- Nazwa operatora subskrybenta

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Ustawianie dostępu dla aplikacji według minimalnego poziomu poprawki zabezpieczeń systemu Android na urządzeniu<!-- 1278463 -->   
Administrator może zdefiniować minimalny poziom poprawki zabezpieczeń systemu Android, który musi być zainstalowany na urządzeniu, aby można było uzyskać dostęp do aplikacji zarządzanej na koncie zarządzanym.

> [!Note]  
> Ta funkcja ogranicza poprawki zabezpieczeń opublikowane przez firmę Google wyłącznie na urządzeniach z systemem Android 6.0 lub nowszym.

### <a name="app-conditional-launch-support----1193313---"></a>Obsługa uruchamiania warunkowego aplikacji <!-- 1193313 -->
Administratorzy IT mogą teraz określić za pośrednictwem portalu administracyjnego platformy Azure wymaganie, aby podczas uruchamiania aplikacji było wymuszane wprowadzenie hasła, zamiast wprowadzania kodu liczbowego PIN za pośrednictwem funkcji zarządzania aplikacjami mobilnymi (MAM). W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. W tej wersji usługi Intune ta funkcja jest dostępna **tylko w systemie iOS**. Usługa Intune obsługuje hasło w podobny sposób jak kod liczbowy PIN — określa minimalną długość, umożliwiając powtarzanie znaków i sekwencji. Funkcja ta wymaga udziału aplikacji (tj. WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu Intune App SDK przy użyciu kodu dla tej funkcji, dzięki czemu ustawienia kodu dostępu zostaną wymuszone w aplikacjach docelowych.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numery wersji aplikacji biznesowych w raporcie o stanie instalacji urządzenia <!-- 1233999 -->
W tej wersji w raporcie o stanie instalacji urządzenia wyświetlane są numery wersji aplikacji biznesowych dla systemów iOS i Android. Korzystając z tych informacji, można rozwiązywać problemy z aplikacjami lub znajdować urządzenia z nieaktualnymi wersjami aplikacji.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratorzy mogą teraz konfigurować ustawienia zapory na urządzeniu za pomocą profilu konfiguracji urządzenia <!-- 951708 -->   
Administratorzy mogą włączać zaporę dla urządzeń, a także konfigurować różne protokoły dla domeny oraz sieci prywatnych i publicznych.  Ustawienia zapory można znaleźć w profilu „Ochrona punktów końcowych”.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Funkcja Windows Defender Application Guard ułatwia ochronę urządzeń przed niezaufanymi witrynami w sposób zdefiniowany przez Twoją organizację <!-- 958257 -->   
Używając przepływu pracy funkcji Windows Information Protection lub nowego profilu „Granica sieci” w konfiguracjach urządzeń, administratorzy mogą definiować witryny jako „zaufane” lub „firmowe”. Wszystkie witryny wyświetlane w przeglądarce Microsoft Edge, które nie znajdują się w granicach zaufanej sieci na urządzeniu z 64-bitowym systemem Windows 10, są otwierane w przeglądarce na komputerze wirtualnym funkcji Hyper-V.

Funkcję Application Guard można znaleźć w profilach konfiguracji urządzeń w profilu „Ochrona punktów końcowych”. W tym miejscu administratorzy mogą skonfigurować interakcję między zwirtualizowaną przeglądarką a komputerem hosta, zaufanymi i niezaufanymi witrynami oraz danymi magazynowania generowanymi w zwirtualizowanej przeglądarce. Aby można było używać funkcji Application Guard na urządzeniu, najpierw należy skonfigurować granicę sieci. Dla jednego urządzenia należy określić tylko jedną granicę sieci.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Funkcja Windows Defender Application Control w systemie Windows 10 Enterprise udostępnia tryb ufania tylko autoryzowanym aplikacjom <!-- 1031096 -->    
Tysiące nowych, złośliwych plików tworzonych każdego dnia powodują, że walka ze złośliwym oprogramowaniem przy użyciu wykrywania wirusów w oparciu o ich sygnatury może nie zapewniać już odpowiedniej obrony przed nowymi atakami. Korzystając z funkcji Windows Defender Application Control w systemie Windows 10 Enterprise, można zmienić konfigurację urządzenia z trybu, w którym aplikacje są zaufane, dopóki nie zostaną zablokowane przez program antywirusowy lub inne rozwiązanie z zakresu zabezpieczeń, na tryb, w którym system operacyjny ufa tylko aplikacjom autoryzowanym przez przedsiębiorstwo. Zaufanie do aplikacji można przypisać za pomocą funkcji Windows Defender Application Control.

Korzystając z usługi Intune, można skonfigurować zasady kontroli aplikacji w trybie „tylko do inspekcji” lub w trybie wymuszania. Aplikacje działające w trybie „tylko do inspekcji” nie są blokowane. Tryb „tylko do inspekcji” rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta. Można również określić, czy mogą być uruchamiane wyłącznie składniki systemu Windows i aplikacje ze sklepu Microsoft Store, czy również inne aplikacje o dobrej reputacji zdefiniowane przez usługę Intelligent Security Graph.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard to nowy zestaw funkcji zapobiegania nieautoryzowanemu dostępowi do systemu Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard zawiera reguły niestandardowe, które ograniczają podatność aplikacji na wykorzystanie luk w zabezpieczeniach, zapobiega zagrożeniom w makrach i skryptach, automatycznie blokuje połączenia sieciowe z adresami IP o niskiej reputacji, a także umożliwia zabezpieczenie danych przed oprogramowaniem wymuszającym okup i nieznanymi zagrożeniami. Windows Defender Exploit Guard obejmuje następujące składniki:

- **Attack Surface Reduction** zawiera reguły, które pozwalają zapobiegać zagrożeniom występującym w makrach, skryptach i wiadomościach e-mail.
- **Controlled Folder Access** automatycznie blokuje dostęp do zawartości do folderów chronionych.
- **Network Filter** blokuje połączenie wychodzące z dowolnej aplikacji do adresu IP/domeny o niskiej reputacji.
- **Exploit Protection** zapewnia ograniczenia pamięci, przepływu sterowania i zasad, które umożliwiają ochronę aplikacji przed lukami w zabezpieczeniach.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10 <!-- 790537 -->

Rozszerzenie do zarządzania usługi Intune pozwala przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie uzupełnia możliwości funkcji zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10](intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nowe ustawienia ograniczeń urządzenia z systemem Windows 10      <!-- 1308850 -->
-    Wiadomości (tylko dla urządzeń przenośnych) — wyłączenie testowania lub wiadomości MMS
-    Hasło — ustawienia umożliwiające włączanie standardu FIPS i uwierzytelnianie za pomocą dodatkowych urządzeń z usługą Windows Hello 
-    Ekran — ustawienia umożliwiające włączanie i wyłączanie skalowania graficznego interfejsu użytkownika dla starszych aplikacji

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Ograniczenia urządzeń z systemem Windows 10 do trybu kiosku <!-- 1308872 -->   
Możesz ograniczyć użytkowników urządzeń z systemem Windows 10 do trybu kiosku, który ogranicza użytkownikom dostęp tylko do zestawu wstępnie zdefiniowanych aplikacji.  Aby to zrobić, należy utworzyć profil ograniczenia urządzenia z systemem Windows 10 i określić ustawienia kiosku.

Tryb kiosku obsługuje dwa tryby: **pojedynczej aplikacji** (pozwala użytkownikowi na uruchomienie tylko jednej aplikacji) lub **wielu aplikacji** (zezwala na dostęp do zestawu aplikacji).  Aby określić obsługiwane aplikacje, należy zdefiniować konto użytkownika i nazwę urządzenia.  Zalogowany użytkownik ma dostęp ograniczony do zdefiniowanych aplikacji.  Aby dowiedzieć się więcej, zobacz [AssignedAccess CSP (Dostawca usługi konfiguracji AssignedAccess)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Wymagania trybu kiosku:

- Usługa Intune musi być urzędem zarządzania urządzeniami przenośnymi.
- Aplikacje muszą być już zainstalowane na urządzeniu docelowym.
- Urządzenie musi być [poprawnie udostępniane](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nowy profil konfiguracji urządzeń do tworzenia granic sieci <!-- 1311967 -->   
Wśród profilów konfiguracji urządzeń można znaleźć nowy profil konfiguracji urządzeń o nazwie **Granica sieci**. Ten profil umożliwia zdefiniowanie zasobów online, które mają być uważane za firmowe i zaufane. Granicę sieci dla urządzenia należy zdefiniować *przed* użyciem na urządzeniu funkcji takich jak Windows Defender Application Guard i Windows Information Protection. Dla każdego urządzenia należy określić tylko jedną granicę sieci.

Jako zasoby, które mają zostać uznane za zaufane, można zdefiniować zasoby chmury przedsiębiorstwa, zakresy adresów IP i wewnętrzne serwery proxy. Zdefiniowana granica sieci może być używana przez inne funkcje, takie jak Windows Defender Application Guard i Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Dwa dodatkowe ustawienia usługi Windows Defender Antivirus <!-- 1338409 -->  
**Poziom blokowania plików**

| | |
|---|---|
| Nieskonfigurowane | **Nieskonfigurowane** używa domyślnego poziomu blokowania usługi Windows Defender Antivirus i zapewnia silne wykrywanie bez zwiększania ryzyka wykrywania prawidłowych plików. |
| Wysoki | **Wysoki** stosuje silny poziom wykrywania.
| Wysoki +  | **Wysoki +** zapewnia wysoki poziom z dodatkowymi środkami ochronnymi, które mogą mieć wpływ na wydajność klienta.
| Zero tolerancji  | **Zero tolerancji** blokuje wszystkie nieznane pliki wykonywalne. |

Chociaż jest to mało prawdopodobne, ustawienie **Wysoki** może powodować wykrywanie niektórych prawidłowych plików.
Zalecamy ustawienie domyślnego poziomu blokowania plików **Nieskonfigurowane**.

**Zwiększenie limitu czasu dla skanowania plików w chmurze**  

| | |
|--|--|
| Liczba sekund (0–50) | Należy określić maksymalny czas, przez który usługa Windows Defender Antivirus powinna blokować plik podczas oczekiwania na wynik z chmury. Wartość domyślna wynosi 10 sekund: dodatkowy czas określony w tym miejscu (maksymalnie 50 sekund) jest dodawany do tych 10 sekund. W większości przypadków skanowanie trwa znacznie krócej niż wartość maksymalna. Wydłużenie czasu pozwala chmurze na staranne zbadanie podejrzanych plików. Zalecamy włączenie tego ustawienia i określenie co najmniej 20 dodatkowych sekund. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Dodano sieć VPN Citrix dla urządzeń z systemem Windows 10 <!-- 1512457 -->  
Można skonfigurować sieć VPN Citrix dla swoich urządzeń z systemem Windows 10. Sieć VPN Citrix można wybrać na liście *Wybierz typ połączenia* w bloku **Podstawowa sieć VPN** podczas konfigurowania sieci VPN dla systemu Windows 10 i nowszych.

> [!Note]
> Konfiguracja serwera Citrix istniała dla systemów iOS i Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Połączenia sieci Wi-Fi obsługują klucze wstępne w systemie iOS <!-- 1550823 -->
Klienci mogą skonfigurować profile sieci Wi-Fi, aby używać kluczy wstępnych (PSK) dla połączeń WPA/WPA2 Personal na urządzeniach z systemem iOS. Te profile są wypychane na urządzenie użytkownika, kiedy urządzenie jest zarejestrowane w usłudze Intune.

Po wypchnięciu profilu do urządzenia następny krok zależy od konfiguracji profilu.  Jeśli ustawiono wartość Połącz automatycznie, połączenie z siecią jest nawiązywane automatycznie, kiedy jest potrzebne.  Jeśli w profilu ustawiono ręczne połączenie, użytkownik musi ręcznie uaktywnić połączenie.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Dostęp do dzienników zarządzanych aplikacji dla systemu iOS <!-- 1469920 -->
Użytkownicy końcowi z zainstalowanym programem Managed Browser mogą teraz wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft i wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS.

Dowiedz się, jak włączyć tryb rozwiązywania problemów w programie Managed Browser na urządzeniu z systemem iOS, zobacz [jak uzyskać dostęp do dzienników zarządzanych aplikacji przy użyciu programu Managed Browser w systemie iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS w wersji 2.9.0 <!-- 1417174 -->

Ulepszono przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS. Używany język jest bardziej przyjazny dla użytkownika i tam, gdzie było to możliwe, ekrany zostały połączone. Język jest lepiej dostosowany do Twojej firmy, ponieważ w tekście instalatora używana jest jej nazwa. Ten zaktualizowany przepływ pracy można wyświetlić na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Jednostka użytkownika zawiera najnowsze dane użytkownika w modelu danych usługi Data Warehouse <!-- 1544273 -->
Pierwsza wersja modelu danych magazynu danych usługi Intune zawierała tylko ostatnie, historyczne dane usługi Intune. Podczas tworzenia raportu nie było możliwe uchwycenie bieżącego stanu użytkownika. Po wprowadzeniu tej aktualizacji **jednostka użytkownika** jest wypełniana najnowszymi danymi użytkownika.

<!-- ########################## -->
## <a name="october-2017"></a>Październik 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Widoczny numer wersji aplikacji biznesowej dla systemu iOS lub Android <!-- 1380712 -->

W usłudze Intune są teraz wyświetlane numery wersji aplikacji biznesowych dla systemu iOS lub Android. W witrynie Azure Portal numer jest widoczny na liście aplikacji i w bloku przeglądu aplikacji. Użytkownicy końcowi widzą numer aplikacji w aplikacji Portal firmy i w portalu internetowym.

__Pełny numer wersji__ Pełny numer wersji identyfikuje określoną wersję aplikacji. Numer ma postać _wersja_(_kompilacja_), na przykład 2.2(2.2.17560800).

Pełny numer wersji ma dwa składniki:

 - **Wersja**  
   Numer wersji to zrozumiały dla użytkownika numer wydania aplikacji. Jest on używany przez użytkowników końcowych do identyfikowania różnych wydań aplikacji.

 - **Numer kompilacji**  
    Numer kompilacji to numer wewnętrzny, który może być używany do wykrywania aplikacji i programowego zarządzania nią. Numer kompilacji dotyczy iteracji aplikacji, która odnosi się do zmian w kodzie.

Temat [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers) zawiera więcej informacji o numerach wersji i tworzeniu aplikacji biznesowych.

### <a name="device-and-app-management-integration----677972---"></a>Integracja zarządzania urządzeniami i aplikacjami <!-- 677972 -->   
Teraz, gdy funkcje zarządzania urządzeniami przenośnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM) usługi Intune są już dostępne w witrynie Azure Portal, usługa Intune rozpoczęła integrowanie środowiska pracy administratora IT wokół zarządzania aplikacjami i urządzeniami. Zmiany mają na celu uproszczenie środowiska zarządzania urządzeniami i aplikacjami.

Dowiedz się więcej na temat zmian funkcji MDM i MAM ogłoszonych w [blogu zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nowe alerty rejestracji dla urządzeń firmy Apple <!-- 1471790 -->
Na stronie przeglądu rejestracji będą wyświetlane przydatne alerty dotyczące zarządzania urządzeniami firmy Apple, przeznaczone dla administratorów IT. Alerty na stronie przeglądu pojawią się, jeśli certyfikat wypychania MDM firmy Apple wkrótce wygaśnie bądź już wygasł lub token programu Device Enrollment Program wkrótce wygaśnie bądź już wygasł albo w programie Device Enrollment Program występują nieprzypisane urządzenia.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Obsługa zastępowania tokenu dla konfiguracji aplikacji bez rejestracji urządzeń <!-- 1080364 -->

Można używać tokenów dla wartości dynamicznych w konfiguracjach aplikacji na niezarejestrowanych urządzeniach. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Aktualizacje aplikacji Portal firmy dla systemu Windows 10 <!--1299474-->
Strona Ustawienia w aplikacji Portal firmy dla systemu Windows 10 została zaktualizowana, dzięki czemu ustawienia i spodziewane akcje użytkownika są bardziej spójne z pozostałymi ustawieniami. Zaktualizowany został również układ aplikacji, który teraz lepiej odpowiada układom innych aplikacji systemu Windows. Obrazy stanu przed i po aktualizacji znajdują się na stronie dotyczącej [nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Powiadamianie użytkowników końcowych o widocznych informacjach dotyczących urządzeń dla systemu Windows 10 <!--1337920-->
Dodaliśmy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu Windows 10. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie **Informacje**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Monity o opinię użytkownika aplikacji Portal firmy dla systemu Android <!--1165249-->
Aplikacja Portal firmy dla systemu Android wyświetla teraz prośbę o opinię użytkownika końcowego. Opinia ta jest wysyłana bezpośrednio do firmy Microsoft i zapewnia użytkownikom końcowym możliwość opublikowania recenzji aplikacji w publicznym sklepie Google Play. Opinia nie jest wymagana, więc prośbę można łatwo odrzucić i dalej używać aplikacji.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ułatwianie użytkownikom samodzielnego rozwiązywania problemów przy użyciu aplikacji Portal firmy dla systemu Android <!-- 1573324, 1573150, 1558616, 1564878 -->

Do aplikacji Portal firmy dla systemu Android zostały dodane instrukcje dla użytkowników końcowych zawierające opisy problemów i umożliwiające — o ile to możliwe — samodzielne rozwiązywanie nowych przypadków użycia.
- W przypadku dodania maksymalnej dozwolonej liczby urządzeń użytkownicy końcowi zostaną przekierowani do [portalu usługi Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) w celu usunięcia urządzenia.
- Użytkownicy otrzymają instrukcje ułatwiające [naprawienie błędów aktywacji na urządzeniach z systemem Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) lub [wyłączenie trybu oszczędzania energii](/intune-user-help/power-saving-mode-android). Jeśli żadne z tych rozwiązań nie pozwoli rozwiązać problemu, udostępnimy wskazówki dotyczące [przesyłania dzienników do firmy Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nowa akcja „Rozwiąż” dostępna dla urządzeń z systemem Android <!-- 1583480 -->

W aplikacji Portal firmy dla systemu Android zostanie wprowadzona akcja „Rozwiąż”, dostępna na stronie _aktualizacji ustawień urządzenia_. Wybranie tej opcji spowoduje przejście bezpośrednio do ustawienia powodującego niezgodność urządzenia z zasadami. Aktualnie aplikacja Portal firmy dla systemu Android obsługuje tę akcję dla ustawień dotyczących [kodu dostępu urządzenia](/intune-user-help/set-your-pin-or-password-android), [debugowania USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) i [nieznanych źródeł](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Wskaźnik postępu konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android <!-- 1565657 -->
Aplikacja Portal firmy dla systemu Android wyświetla wskaźnik postępu konfiguracji urządzenia, gdy użytkownik rejestruje swoje urządzenie. Wskaźnik przedstawia nowe stany, np. „Konfigurowanie urządzenia...”, następnie „Trwa rejestrowanie urządzenia...”, następnie „Kończenie rejestrowania urządzenia...”, następnie „Trwa kończenie konfigurowania urządzenia...”.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Obsługa uwierzytelniania opartego na certyfikatach w Portalu firmy dla systemu iOS <!--1029830-->
W aplikacji Portal firmy dla systemu iOS dodaliśmy obsługę uwierzytelniania opartego na certyfikatach (CBA). Użytkownicy korzystający z uwierzytelniania CBA wprowadzają swoją nazwę użytkownika, a następnie wybierają link „Zaloguj się przy użyciu certyfikatu”. Uwierzytelnianie CBA jest już obsługiwane w aplikacji Portal firmy dla systemów Android i Windows. Więcej informacji na ten temat można znaleźć na stronie [logowania się w aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikacje dostępne z rejestracją lub bez rejestracji można teraz instalować bez monitów o rejestrację. <!-- 1334712 -->

Aplikacje firmowe, które udostępniono z rejestracją lub bez rejestracji w aplikacji Portal firmy dla systemu Android, można teraz zainstalować bez monitu o rejestrację.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune----747617---"></a>Obsługa programu Windows AutoPilot Deployment w usłudze Microsoft Intune  <!-- 747617  -->
Przy użyciu programu usługi Microsoft Intune z programem Windows AutoPilot Deployment możesz umożliwiać użytkownikom aprowizację urządzeń firmowych bez angażowania w to działu IT. Możesz dostosować tryb OOBE i przeprowadzić użytkowników przez proces dołączania urządzenia do usługi Azure AD i jego rejestracji w usłudze Intune. Dzięki współdziałaniu usługi Microsoft Intune i programu Windows AutoPilot nie ma potrzeby wdrażania i utrzymywania obrazów systemu operacyjnego ani zarządzania nimi. Aby uzyskać szczegółowe informacje, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="quickstart-for-device-enrollment----1425655---"></a>Szybki start dla rejestracji urządzeń  <!-- 1425655 --> 
Szybki start jest teraz dostępny w **rejestracji urządzeń** i zawiera tabelę odwołań dla zarządzania platformami i konfigurowania procesu rejestracji. Krótki opis każdego elementu i linki do dokumentacji z instrukcjami krok po kroku ułatwiają rozpoczęcie pracy.

### <a name="device-categorization----1427491---"></a>Kategoryzacja urządzeń <!-- 1427491 -->
Zestawienie platform zarejestrowanych urządzeń w bloku **Urządzenia > Przegląd** organizuje urządzenia według platform, w tym systemów Android, iOS, macOS, Windows i Windows Mobile.  Urządzenia z innymi systemami operacyjnymi znajdują się w grupie „Inne”.  Są to urządzenia wyprodukowane przez firmy Blackberry, NOKIA i inne.  

Aby dowiedzieć się, których urządzeń w dzierżawie to dotyczy, wybierz pozycję **Zarządzaj > Wszystkie urządzenia**, a następnie przy użyciu funkcji **Filtruj** ogranicz pole **System operacyjny**.

### <a name="zimperium---new-mobile-threat-defense-partner-----954681---"></a>Zimperium — nowy partner usługi Mobile Threat Defense   <!-- 954681 -->  
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować przy użyciu dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10  <!--- 978575, 1308849, -->  
Dodajemy nowe ustawienia do profilu ograniczeń urządzenia z systemem Windows 10 w kategorii Windows Defender SmartScreen.

Aby uzyskać szczegółowe informacje o profilu ograniczeń urządzenia z systemem Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Zdalna pomoc techniczna dla urządzeń z systemem Windows i Windows Mobile   <!-- 1070473 -->  
Usługa Intune umożliwia teraz korzystanie z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Windows i Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988-1280990---"></a>Skanowanie urządzeń z użyciem usługi Windows Defender <!-- 1280988  1280990   -->
Na zarządzanych urządzeniach z systemem Windows 10 możliwe jest teraz uruchomienie **szybkiego skanowania** i **pełnego skanowania** oraz przeprowadzenie **aktualizacji sygnatur** z użyciem programu antywirusowego Windows Defender. W bloku przeglądu urządzenia wybierz akcję do przeprowadzenia na urządzeniu. Przed wysłaniem polecenia do urządzenia zostanie wyświetlony monit o potwierdzenie akcji. 

**Szybkie skanowanie**: szybkie skanowanie obejmuje lokalizacje, w których złośliwe oprogramowanie rejestruje się w celu umożliwienia jego uruchomienia, np. klucze rejestru i znane foldery uruchamiania systemu Windows. Szybkie skanowanie trwa średnio pięć minut. W połączeniu z ustawieniem **zawsze włączonej ochrony w czasie rzeczywistym**, które skanuje pliki, gdy są one otwierane i zamykane, a także za każdym razem, gdy użytkownik przejdzie do folderu, szybkie skanowanie pomaga chronić przed złośliwym oprogramowaniem, które może być obecne w systemie lub w jądrze. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Pełne skanowanie**: pełne skanowanie przydaje się w przypadku urządzeń, w których wystąpiło zagrożenie związane ze złośliwym oprogramowaniem, ponieważ pozwala określić, czy istnieją nieaktywne składniki, które wymagają dokładniejszego czyszczenia; funkcja umożliwia także uruchamianie skanowania na żądanie. Pełne skanowanie może trwać godzinę. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Zaktualizuj sygnatury**: polecenie aktualizacji sygnatur powoduje aktualizację definicji i sygnatur złośliwego oprogramowania programu antywirusowego Windows Defender. Można w ten sposób upewnić się, że program antywirusowy Windows Defender skutecznie wykrywa złośliwe oprogramowanie. Ta funkcja jest dostępna wyłącznie dla urządzeń z systemem Windows 10 i wymaga połączenia z Internetem. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Przycisk Włącz/Wyłącz został usunięty ze strony urzędu certyfikacji usługi Intune w witrynie Azure Portal usługi Intune  <!-- 1400455 -->
 Eliminujemy dodatkowy krok z konfiguracji łącznika certyfikatów w usłudze Intune. Obecnie należy pobrać łącznik certyfikatów, a następnie włączyć go w konsoli usługi Intune. Jeśli jednak wyłączysz łącznik w konsoli usługi Intune, łącznik wciąż wydaje certyfikaty.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Począwszy od października przycisk Włącz/Wyłącz nie będzie już wyświetlany na stronie urzędu certyfikacji w witrynie Azure Portal. Funkcje łącznika pozostają bez zmian. Certyfikaty są wciąż wdrażane na urządzeniach zarejestrowanych w usłudze Intune. Nadal możesz pobrać i zainstalować łącznik certyfikatów. Aby zatrzymać wydawanie certyfikatów, zamiast wyłączać łącznik certyfikatów należy go teraz odinstalować.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli łącznik certyfikatów jest obecnie wyłączony, należy go odinstalować.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 Team   <!--- 1308838 -->
W tym wydaniu dodaliśmy wiele nowych ustawień profilu ograniczeń urządzenia z systemem Windows 10 Team ułatwiających kontrolę urządzeń Surface Hub.

Aby uzyskać więcej informacji o tym profilu, zobacz artykuł [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md) (Ustawienia ograniczeń urządzenia z systemem Windows 10 Team).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time----1333292---"></a>Uniemożliwianie użytkownikom urządzeń z systemem Android zmiany daty i godziny ich urządzeń  <!-- 1333292 -->
Można użyć [niestandardowych zasad urządzeń z systemem Android](custom-settings-android.md), aby uniemożliwić użytkownikom urządzeń z systemem Android zmianę daty i godziny urządzenia.

W tym celu należy skonfigurować niestandardowe zasady systemu Android, korzystając z identyfikatora URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Dla powyższego identyfikatora URI należy wybrać wartość **TRUE**, a następnie przypisać go do wymaganych grup.

### <a name="bitlocker-device-configuration---1397398---"></a>Konfiguracja urządzenia z użyciem funkcji BitLocker <!-- 1397398 -->
Wybierając pozycję **Szyfrowanie systemu Windows > Ustawienia podstawowe**, można uzyskać dostęp do nowego ustawienia **Ostrzeżenie dotyczące innego szyfrowania dysku** pozwalającego wyłączyć [monit ostrzegawczy](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) dotyczący innego szyfrowania, które mogło zostać użyte na urządzeniu użytkownika.  Przed rozpoczęciem konfiguracji funkcji BitLocker na urządzeniu zostanie wyświetlony monit ostrzegawczy wymagający zgody użytkownika końcowego; konfiguracja funkcji BitLocker będzie blokowana do czasu potwierdzenia przez użytkownika końcowego.  Nowe ustawienie wyłącza ostrzeżenie użytkownika końcowego.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Aplikacje programu Volume Purchase Program for Business będą się teraz synchronizowały z dzierżawą usługi Intune <!-- 800882 -->  
Deweloperzy innych firm mogą prywatnie dystrybuować aplikacje do autoryzowanych członków programu Volume Purchase Program (VPP) for Business określonych w usłudze iTunes Connect. Ci członkowie programu VPP for Business mogą zalogować się do sklepu Volume Purchase Program App Store i zakupić ich aplikacje.

W tej wersji aplikacje programu VPP for Business zakupione przez użytkownika końcowego będą się teraz synchronizowały z ich dzierżawami usługi Intune.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Wybór krajowego sklepu Apple do synchronizacji aplikacji VPP  <!-- 1332311 -->  
Podczas przekazywania tokenu programu VPP można skonfigurować krajowy sklep do obsługi programu zakupów zbiorczych (VPP, ang. Volume Purchase Program). Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.

> [!NOTE]  
> Obecnie usługa Intune synchronizuje tylko aplikacje VPP z krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnego z ustawieniami regionalnymi usługi Intune dla lokalizacji, w której została utworzona dzierżawa usługi Intune.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokowanie kopiowania i wklejania między profilami służbowymi i osobistymi w aplikacji Android for Work <!-- 1098994 -->
W tej wersji można skonfigurować profil służbowy w programie Android for Work w taki sposób, aby kopiowanie i wklejanie danych między aplikacjami służbowymi i osobistymi było blokowane. To nowe ustawienie można znaleźć w profilu **Ograniczenia urządzenia** platformy **Android for Work** w obszarze **Ustawienia profilu służbowego**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Tworzenie aplikacji dla systemu iOS ograniczonych do określonych regionalnych sklepów Apple App Store <!-- 1281692 -->
Podczas tworzenia zarządzanej aplikacji przeznaczonej do sklepu Apple App Store można określić ustawienia regionalne dla kraju.

> [!Note]  
> Obecnie można tworzyć wyłącznie zarządzane aplikacje dla sklepu Apple App Store dostępne w amerykańskiej wersji strony sklepu.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizacja aplikacji VPP dla systemu iOS z licencją użytkownika i urządzenia  <!-- 1305564 -->  
Można skonfigurować token programu VPP systemu iOS pod kątem aktualizacji wszystkich aplikacji zakupionych dla danego tokenu za pośrednictwem usługi Intune. Usługa Intune wykryje aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypchnie je do urządzenia po jego zaewidencjonowaniu.

Aby poznać procedurę ustawiania tokenu VPP i włączania automatycznych aktualizacji, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych] (/intune/vpp-apps-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych usługi Data Warehouse usługi Intune <!-- 1187917 -->
Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Przegląd zasad zgodności pod kątem pierścieni aktualizacji systemu Windows 10 <!-- 1067886 -->
Można przejrzeć raport zasad odnoszący się do pierścieni aktualizacji systemu Windows 10, przechodząc do obszaru Aktualizacje oprogramowania > Stan wdrożenia według pierścienia aktualizacji. Raport zasad zawiera stan wdrożenia dla skonfigurowanych pierścieni aktualizacji. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions----1352223---"></a>Nowy raport, który zawiera listę urządzeń dla systemu iOS ze starszymi wersjami systemu iOS   <!-- 1352223 -->
Raport **Nieaktualne urządzenia z systemem iOS** jest dostępny z poziomu obszaru roboczego **Aktualizacje oprogramowania**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS i które mają dostępne aktualizacje. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting----1475003---"></a>Wyświetlanie przypisań zasad ochrony aplikacji w celu rozwiązywania problemów <!--  1475003 -->
W nadchodzącym wydaniu opcja **zasad ochrony aplikacji** zostanie dodana do listy rozwijanej **Przypisania** dostępnej w bloku rozwiązywania problemów. Teraz możesz wybrać zasady ochrony aplikacji, aby wyświetlić zasady ochrony aplikacji przypisane do wybranych użytkowników.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w Portalu firmy <!--1490692-->
Ulepszyliśmy przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android. Język jest bardziej przyjazny dla użytkownika i specyficzny dla Twojej firmy, a w miarę możliwości ekrany zostały połączone. Możesz to zobaczyć na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Ulepszone wskazówki dotyczące żądania dostępu do kontaktów na urządzeniach z systemem Android <!--1484985-->

Aplikacja Portal firmy dla systemu Android często wymaga od użytkownika końcowego zaakceptowania uprawnień do kontaktów. Jeśli użytkownik końcowy odmówi dostępu, zobaczy w aplikacji powiadomienie z alertem dotyczącym przyznania aplikacji dostępu warunkowego. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Korygowanie bezpiecznego uruchamiania dla systemu Android <!--1490712-->

Użytkownicy końcowi mający urządzenia z systemem Android będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Dodatkowe powiadomienia wypychane dla użytkowników końcowych w aplikacji Portal firmy dla systemu Android Oreo <!--1475932-->

Użytkownicy końcowi będą widzieli dodatkowe powiadomienia, gdy aplikacja Portal firmy dla systemu Android Oreo wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune. Powoduje to zwiększenie przejrzystości dla użytkowników końcowych przez informowanie ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na ich urządzeniach. Jest to część ogólnej [optymalizacji interfejsu użytkownika aplikacji Portal firmy](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) dla aplikacji Portal firmy dla systemu Android Oreo. 

Istnieją dodatkowe optymalizacje dla nowych elementów interfejsu użytkownika, które są włączone w systemie Android Oreo.  Użytkownicy końcowi zobaczą dodatkowe powiadomienia, które będą wskazywać im, kiedy Portal firmy wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune.  Powoduje to zwiększenie przejrzystości dla użytkowników końcowych dzięki informowaniu ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na urządzeniu.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nowe zachowanie aplikacji Portal firmy dla systemu Android z profilami służbowymi <!-- 1485783 -->

Po zarejestrowaniu urządzenia z programem Android for Work i z profilem służbowym to właśnie aplikacja Portal firmy w profilu służbowym wykonuje na urządzeniu zadania z zakresu zarządzania. 

Jeśli użytkownik nie korzysta w profilu osobistym z aplikacji z obsługą zasad zarządzania aplikacjami mobilnymi (MAM), aplikacja Portal firmy dla systemu Android nie pełni już żadnej roli. Aby ulepszyć środowisko pracy w profilu służbowym, po pomyślnej rejestracji profilu służbowego usługa Intune automatycznie ukrywa aplikację Portal firmy z profilu osobistego.

Aplikację Portal firmy dla systemu Android można w dowolnym momencie włączyć w profilu osobistym, wybierając [aplikację Portal firmy w Sklepie Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) i wybierając opcję **Włącz**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Utrzymanie aplikacji Portal firmy w systemach Windows 8.1 i Windows Phone 8.1 <!--1428681-->

Począwszy od października 2017 roku aplikacje Portal firmy zostaną utrzymane w systemach Windows 8.1 i Windows Phone 8.1. Oznacza to, że aplikacje i istniejące scenariusze, np. scenariusze rejestracji i zgodności, będą nadal obsługiwane przez te platformy. Aplikacje te będą nadal dostępne do pobrania za pośrednictwem istniejących kanałów, takich jak Sklep Microsoft. 

Po zatwierdzeniu utrzymania tych aplikacji będą dla nich udostępniane wyłącznie krytyczne aktualizacje zabezpieczeń. Nie będzie dla nich żadnych dodatkowych aktualizacji i nie będą w nich udostępniane żadne nowe funkcje. W celu skorzystania z nowych funkcji zalecamy aktualizację urządzenia do systemu Windows 10 lub Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment----1490695---"></a>Blokowanie nieobsługiwanej rejestracji urządzenia z systemem Samsung Knox  <!-- 1490695 -->

Aplikacja Portal firmy tylko próbuje zarejestrować obsługiwane urządzenia z systemem Samsung Knox. Aby uniknąć błędów aktywacji systemu Knox, które uniemożliwiają rejestrację w usłudze MDM, próba rejestracji urządzenia nastąpi tylko wtedy, gdy urządzenie znajduje się na [liście urządzeń opublikowanej przez firmę Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Urządzenia firmy Samsung z określonymi numerami modelu mogą obsługiwać system Knox, podczas gdy inne go nie obsługują. Sprawdź zgodność systemu Knox u odsprzedawcy urządzenia przed zakupem i wdrożeniem. Pełną listę zweryfikowanych urządzeń można znaleźć w [ustawieniach zasad systemu Android i systemu Samsung Knox Standard](supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!-- 1171126, 1326920 -->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Powiadamianie użytkowników końcowych o informacjach o urządzeniu widocznych na zarejestrowanych urządzeniach <!--1165314-->
Dodajemy element **Typ własności** do ekranu Szczegóły urządzenia we wszystkich aplikacjach Portal firmy. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z artykułu [Jakie informacje może wyświetlać Twoja firma?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Zostanie to wdrożone we wszystkich aplikacjach Portal firmy w najbliższej przyszłości. Zapowiedzieliśmy to dla systemu iOS we [wrześniu](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).

<!-- ########################## -->
## <a name="september-2017"></a>Wrzesień 2017

### <a name="intune-supports-ios-11---1428975--"></a>Usługa Intune obsługuje system iOS 11 <!--1428975-->
Usługa Intune obsługuje system iOS 11. Zostało to wcześniej zapowiedziane na [blogu dotyczącym pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!-- 1164477 -->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Dodanie akcji odświeżenia do aplikacji Portal firmy dla systemu Windows 10 <!--1132468-->
Aplikacja Portal firmy dla systemu Windows 10 pozwala użytkownikom odświeżać dane w aplikacji poprzez przeciągnięcie ekranu lub — w przypadku komputerów — naciśnięcie klawisza F5.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Powiadamianie użytkowników końcowych, o widocznych w systemie iOS informacjach o urządzeniu <!--739894-->

Dodaliśmy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu iOS. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie Informacje.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zezwalanie użytkownikom na dostęp do aplikacji Portal firmy dla systemu Android bez rejestracji <!---1169910--->

Wkrótce użytkownicy końcowi nie będą musieli rejestrować urządzeń, aby uzyskać dostęp do aplikacji Portal firmy dla systemu Android. Użytkownicy końcowi w organizacjach używających zasad ochrony aplikacji nie będą już otrzymywać monitów o zarejestrowanie swoich urządzeń po otwarciu aplikacji Portal firmy. Ponadto użytkownicy końcowi będą mogli instalować aplikacje z poziomu aplikacji Portal firmy bez konieczności rejestrowania urządzeń. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Bardziej zrozumiałe komunikaty w aplikacji Portal firmy dla systemu Android <!---1396349--->  

Proces rejestracji w aplikacji Portal firmy dla systemu Android został uproszczony poprzez dodanie nowego tekstu w celu ułatwienia użytkownikom końcowym przeprowadzenia procesu rejestracji. Jeśli masz dokumentację rejestracji niestandardowej, możesz ją zaktualizować, aby odzwierciedlić nowe ekrany. Przykładowe obrazy można znaleźć na naszej stronie [aktualizacji interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Dodanie aplikacji Portal firmy dla systemu Windows 10 do zasad zezwoleń funkcji Windows Information Protection <!-- 677129 -->

Aplikacja Portal firmy dla systemu Windows 10 została zaktualizowana w celu umożliwienia obsługi funkcji Windows Information Protection (WIP). Aplikację można dodać do zasad zezwoleń funkcji WIP. Dzięki tej zmianie nie trzeba dodawać żadnych aplikacji do listy **Wyklucz**.


<!-- ########################## -->
## <a name="august-2017"></a>Sierpień 2017

### <a name="improvements-to-device-overview----1404453---"></a>Ulepszenia w zakresie przeglądu urządzeń <!-- 1404453 -->  
Dzięki ulepszeniom przegląd urządzeń wyświetla teraz zarejestrowane urządzenia, ale pomija urządzenia zarządzane przez program Exchange ActiveSync. Urządzenia programu Exchange ActiveSync nie mają tych samych opcji zarządzania co zarejestrowane urządzenia. Aby wyświetlić liczbę zarejestrowanych urządzeń i liczbę zarejestrowanych urządzeń według platformy, w usłudze Intune w witrynie Azure Portal przejdź do pozycji **Urządzenia** > **Przegląd**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Ulepszenia dotyczące spisu urządzeń zebranego przez usługę Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
W tym przypadku wprowadziliśmy następujące ulepszenia dotyczące informacji o spisie zbieranych przez zarządzane urządzenia:
 
-   W przypadku urządzeń z systemem Android możesz teraz dodać do spisu urządzeń kolumnę wyświetlającą poziom ostatniej poprawki dla każdego urządzenia. Dodaj kolumnę **Poziom poprawek bezpieczeństwa** do listy urządzeń, aby to zobaczyć.
-   Podczas filtrowania widoku urządzeń możesz teraz filtrować urządzenia według daty ich zarejestrowania. Możesz na przykład wyświetlić tylko urządzenia, które zostały zarejestrowane po określonej dacie.
-   Wprowadziliśmy ulepszenia dotyczące filtra używanego przez element **Data ostatniego zaewidencjonowania**.
-   Na liście urządzeń możesz teraz wyświetlić numery telefonów urządzeń będących własnością firmy.
Ponadto przy użyciu okienka filtru możesz wyszukiwać urządzenia według numeru telefonu.

Aby uzyskać więcej informacji na temat spisu urządzeń, zobacz [Jak wyświetlać spis urządzeń usługi Intune](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Obsługa dostępu warunkowego w przypadku urządzeń z systemem macOS 
<!-- 720172 -->
Możesz teraz ustawić zasady dostępu warunkowego, które wymagają zarejestrowania urządzeń Mac w usłudze Intune i ich zgodności z zasadami zgodności urządzeń usługi Intune. Na przykład użytkownicy mogą pobrać aplikację Portal firmy w usłudze Intune dla systemu macOS i zarejestrować swoje urządzenia Mac w usłudze Intune. Usługa Intune ocenia, czy urządzenie Mac jest zgodne z wymaganiami, między innymi przez sprawdzenie numeru PIN, szyfrowania, wersji systemu operacyjnego i integralności systemu.

- Dowiedz się więcej o [obsłudze dostępu warunkowego w przypadku urządzeń z systemem macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikacja Portal firmy dla urządzeń z systemem macOS jest dostępna w publicznej wersji zapoznawczej <!---1484796--->
Aplikacja Portal firmy dla urządzeń z systemem macOS jest teraz dostępna w ramach publicznej wersji zapoznawczej dostępu warunkowego pakietu Enterprise Mobility + Security. Ta wersja obsługuje system macOS w wersji 10.11 i nowszych. Pobierz ją ze strony [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nowe ustawienia ograniczeń urządzenia z systemem Windows 10    
<!--1063965, 1308850  -->
W tej wersji dodano nowe ustawienia profilu [ograniczeń urządzenia z systemem Windows 10](/intune/device-restrictions-windows-10) w następujących kategoriach:

-   Windows Defender SmartScreen
-   App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizacje profilu urządzenia usługi Endpoint Protection dla systemu Windows 10 dla ustawień funkcji BitLocker
<!--1459533 -->     W tej wersji wprowadziliśmy następujące ulepszenia dotyczące sposobu działania ustawień funkcji BitLocker w profilu urządzenia usługi Endpoint Protection dla systemu Windows 10:
 
-   W obszarze **Ustawienia funkcji BitLocker dla dysku systemu operacyjnego** wybranie wartości **Blokuj** dla ustawienia **Funkcja BitLocker z niezgodnym modułem TPM** w rzeczywistości zezwalało na używanie funkcji BitLocker. Ten błąd został rozwiązany i funkcja BitLocker jest blokowana, gdy zostanie wybrane odpowiednie ustawienie.
-   W obszarze **Ustawienia funkcji BitLocker dla dysku systemu operacyjnego** w przypadku ustawienia **Agent odzyskiwania danych oparty na certyfikatach** możesz teraz jawnie blokować agenta odzyskiwania danych opartego na certyfikatach. Jednak domyślnie agent nie jest blokowany.
-   W obszarze **Ustawienia stałych dysków danych w funkcji BitLocker** w przypadku ustawienia **Agent odzyskiwania danych**  możesz teraz jawnie blokować agenta odzyskiwania danych.
Aby uzyskać więcej informacji, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nowe środowisko logowania dla użytkowników aplikacji Portal firmy w systemie Android i użytkowników zasady ochrony aplikacji <!-- 621669 -->
Użytkownicy końcowi mogą teraz przeglądać aplikacje, zarządzać urządzeniami i wyświetlać informacje kontaktowe dla działu IT przy użyciu aplikacji Portal firmy dla systemu Android bez rejestrowania urządzeń z systemem Android. Ponadto jeśli użytkownik końcowy używa aplikacji chronionej przez zasady usługi Intune App Protection i uruchamia Portal firmy dla systemu Android, nie otrzymuje już monitu o zarejestrowanie urządzenia.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nowe ustawienie w aplikacji Portal firmy dla systemu Android umożliwiające przełączanie optymalizacji baterii <!--1405990-->
Strona **Ustawienia** w aplikacji Portal firmy dla systemu Android zawiera nowe ustawienie, które umożliwia użytkownikom proste wyłączanie optymalizacji baterii dla aplikacji Portal firmy i Microsoft Authenticator. Nazwa aplikacji wyświetlana w ustawieniu będzie różnić się w zależności od aplikacji, która zarządza kontem służbowym. Zalecamy, aby użytkownicy wyłączali optymalizację baterii w celu poprawy wydajności aplikacji służbowych, które synchronizują pocztę e-mail i dane. 

### <a name="multi-identity-support-for-onenote-for-ios----1234281---"></a>Obsługa wielu tożsamości w programie OneNote dla systemu iOS      <!-- 1234281 -->
Użytkownicy końcowi mogą teraz używać w programie OneNote dla systemu iOS różnych kont (służbowych i osobistych). Zasady ochrony aplikacji można stosować do danych firmowych w notesach służbowych bez wpływu na notesy osobiste. Zasady mogą na przykład zezwalać użytkownikowi na wyszukiwanie informacji w notesie służbowym, ale uniemożliwią kopiowanie i wklejanie danych firmowych z notesu służbowego do notesu osobistego.
 
- Dowiedz się więcej o aplikacjach, które obsługują [ochronę aplikacji i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nowe ustawienia umożliwiające zezwalanie na działanie aplikacji i blokowanie ich na urządzeniach z systemem Samsung Knox Standard
<!-- 1305423 822899-->  
W tej wersji dodajemy nowe [ustawienia ograniczeń urządzeń](device-restrictions-android.md) pozwalające określić następujące listy aplikacji:
 
- Aplikacje, które użytkownicy mogą instalować
- Aplikacje, których użytkownicy nie mogą uruchamiać
- Aplikacje ukryte przed użytkownikiem na urządzeniu  
Możesz określić aplikacji przy użyciu adresu URL, nazwy pakietu lub zarządzanej przez Ciebie listy aplikacji.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link do nowego opartego na aplikacji interfejsu użytkownika zasad dostępu warunkowego usługi Azure AD z usługi Intune
<!-- 1016201 -->
Administratorzy IT mogą teraz ustawiać zasady dostępu warunkowego opartego na aplikacji za pomocą nowego interfejsu użytkownika zasad dostępu warunkowego w obciążeniu usługi Azure AD. Dostęp warunkowy oparty na aplikacji, który znajduje się w sekcji usługi Intune App Protection w witrynie Azure Portal, pozostanie w tym miejscu i będzie wymuszany równolegle. Wygodny link do nowego interfejsu użytkownika zasad dostępu warunkowego jest dostępny z poziomu obciążenia usługi Intune.

- Dowiedz się więcej o [dostępie warunkowym opartym na aplikacji w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).

<!-- ########################## -->
## <a name="july-2017"></a>Lipiec 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version-----1333256-1245463----"></a>Wprowadzanie ograniczeń rejestracji urządzeń z systemem Android lub iOS na podstawie wersji systemu operacyjnego  <!--- 1333256,  1245463 --->
Usługa Intune obsługuje teraz ograniczanie rejestracji urządzeń z systemem Android lub iOS na podstawie numeru wersji systemu operacyjnego. W obszarze **Ograniczenie typu urządzenia** administrator IT może teraz ustawić konfigurację platformy w taki sposób, aby ograniczyć rejestrację, podając minimalną i maksymalną dopuszczalną wartość systemu operacyjnego. Wersje systemu operacyjnego Android muszą być określone jako wersja_główna.wersja_pomocnicza.kompilacja.wydanie, gdzie wersja_pomocnicza, kompilacja i wydanie są opcjonalne. Wersje systemu operacyjnego iOS muszą być określone jako wersja_główna.wersja_pomocnicza.kompilacja, gdzie wersja_pomocnicza i kompilacja są opcjonalne. Dowiedz się więcej o [ograniczeniach rejestracji urządzenia](enrollment-restrictions-set.md).

>[!NOTE]
>Nie ograniczaj rejestracji za pomocą programów rejestracji firmy Apple lub narzędzia Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment-----1333272-1333275-1245709---"></a>Ograniczanie rejestracji urządzeń osobistych z systemem Android, iOS lub macOS  <!--- 1333272,  1333275, 1245709 --->
Usługa Intune może ograniczać rejestrację urządzenia osobistego, stosując białą listę numerów IMEI urządzeń firmowych. Ta funkcjonalność usługi Intune została teraz rozszerzona na systemy iOS, Android i macOS przy użyciu numerów seryjnych urządzeń. Przekazanie numerów seryjnych do usługi Intune pozwala wstępnie zadeklarować urządzenia jako firmowe. Ograniczenia rejestracji umożliwiają blokowanie urządzeń osobistych („Przynieś własne urządzenie” — BYOD), aby umożliwić rejestrację tylko dla urządzeń należących do firmy. Dowiedz się więcej o [ograniczeniach rejestracji urządzenia](enrollment-restrictions-set.md).

Aby zaimportować numery seryjne, przejdź do pozycji **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych** i kliknij pozycję **Dodaj**, a następnie przekaż plik CSV (bez nagłówka, dwie kolumny numeru seryjnego i szczegóły, takie jak numery IMEI). Aby ograniczyć urządzenia osobiste, przejdź do lokalizacji **Rejestracja urządzeń**  >  **Ograniczenia rejestracji**. W obszarze **Ograniczenia typu urządzeń** wybierz pozycję **Domyślne**, a następnie wybierz pozycję **Konfiguracje platform**. Możesz wybrać pozycję **Zezwalaj** lub **Blokuj** dla urządzeń osobistych z systemem iOS, Android lub macOS.


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nowa akcja urządzenia wymuszająca synchronizację urządzeń z usługą Intune <!-- 711369 -->
W tym wydaniu dodaliśmy nową akcję urządzenia, która wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady.  Ta akcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane ewidencjonowanie.
Aby uzyskać więcej informacji, zobacz [Synchronize device (Synchronizowanie urządzenia)](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS <!-- 777100 -->
W obszarze roboczym aktualizacji oprogramowania są dostępne nowe zasady, które umożliwiają wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS. Aby uzyskać więcej informacji, zobacz [Configure iOS update policies (Konfigurowanie zasad aktualizacji systemu iOS)](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner----954651-1172027---"></a>Check Point SandBlast Mobile — nowy partner usługi Mobile Threat Defense  <!-- 954651, 1172027 -->
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Checkpoint SandBlast Mobile. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzenia przenośne zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune?
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Checkpoint SandBlast Mobile. Zasady dostępu warunkowego usług EMS możesz skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Checkpoint SandBlast Mobile włączane przy użyciu zasad zgodności urządzeń usługi Intune. Możesz zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Wdrażanie aplikacji jako dostępnych w sklepie Microsoft Store dla Firm <!-- 748101 -->
W tej wersji administratorzy mogą teraz przypisać Sklep Microsoft dla Firm jako dostępny. W przypadku ustawienia jako dostępny użytkownicy końcowi mogą zainstalować aplikację z aplikacji Portal firmy lub witryny internetowej bez przekierowania do sklepu Microsoft.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizacje interfejsu użytkownika witryny internetowej Portal firmy <!--1313244 part 1-->
Wprowadziliśmy kilka aktualizacji interfejsu użytkownika [witryny internetowej Portal firmy](https://portal.manage.microsoft.com) w celu ulepszenia środowiska użytkownika końcowego.

- __Ulepszenia kafelków aplikacji__ — ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem określanym na podstawie dominującego koloru ikony (jeśli można będzie go wykryć). O ile będzie to miało zastosowanie, to tło zastąpi szare obramowanie, które było wcześniej widoczne na kafelkach aplikacji.

    Witryna internetowa Portal firmy wyświetla w nadchodzącej wersji duże ikony, jeśli tylko to możliwe. Zalecamy, aby administratorzy IT podczas publikowania aplikacji korzystali z ikon o wysokiej rozdzielczości o rozmiarze co najmniej 120 x 120 pikseli. 

- __Zmiany nawigacji__ — elementy paska nawigacji zostały przeniesione do menu typu „hamburger” znajdującego się w lewym górnym rogu. Strona Kategorie została usunięta. Użytkownicy mogą teraz filtrować zawartość według kategorii podczas przeglądania.

- __Aktualizacje sekcji Polecane aplikacje__ — do witryny dodaliśmy dedykowaną stronę, na której użytkownicy mogą przeglądać aplikacje wybrane przez Ciebie do polecania. Dostosowaliśmy również interfejs użytkownika w sekcji Polecane na stronie głównej.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Obsługa aplikacji iBooks w witrynie internetowej Portal firmy <!--1231841-->
Dodaliśmy dedykowaną stronę do witryny internetowej Portal firmy, która umożliwia użytkownikom przeglądanie i pobieranie plików iBooks. 


### <a name="additional-help-desk-troubleshooting-details-----applies-to-1263399-1326964-1341642----"></a>Dodatkowe szczegóły rozwiązywania problemów dla działu pomocy technicznej <!---  Applies to 1263399, 1326964, 1341642 --->
W usłudze Intune zaktualizowano sposób wyświetlania procesu rozwiązywania problemów i uzupełniono informacje widoczne dla administratorów i personelu pomocy technicznej. Można teraz przeglądać tabelę **Przypisania**, która zawiera podsumowanie wszystkich przypisań dla użytkownika na podstawie członkostwa w grupie. Lista zawiera następujące pozycje:
- Aplikacje mobilne
- Zasady zgodności
- Profile konfiguracji

Ponadto tabela **Urządzenia** zawiera teraz kolumny **Typ dołączenia do usługi Azure AD** i **Zgodne z usługą Azure AD**. Aby uzyskać więcej informacji, zobacz [Help users troubleshoot problems (Pomaganie użytkownikom w rozwiązywaniu problemów)](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Magazyn danych usługi Intune (publiczna wersja zapoznawcza)
Magazyn danych usługi Intune każdego dnia próbkuje dane, aby przedstawić widok historyczny Twojej dzierżawy. Możesz uzyskać dostęp do danych za pomocą pliku usługi Power BI (PBIX), linku usługi OData, która jest zgodna z wieloma narzędziami analitycznymi, lub interakcji z interfejsem API REST. Aby uzyskać więcej informacji, zobacz [Korzystanie z magazynu danych usługi Intune](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Tryb jasny i ciemny dostępne dla aplikacji Portal firmy dla systemu Windows 10 <!---676547--->
Użytkownicy końcowi będą mogli dostosować tryb kolorów aplikacji Portal firmy dla systemu Windows 10. Użytkownik będzie mógł wprowadzić zmiany w sekcji Ustawienia w aplikacji Portal firmy. Zmiana zostanie zastosowana po ponownym uruchomieniu aplikacji przez użytkownika. W przypadku systemu Windows 10 w wersji 1607 lub nowszej domyślnie będzie używany tryb aplikacji określony w ustawieniach systemowych. W przypadku systemu Windows 10 w wersji 1511 lub wcześniejszej domyślnie będzie używany jasny tryb aplikacji.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Umożliwianie użytkownikom tagowania grupy urządzeń w aplikacji Portal firmy dla systemu Windows 10 <!---807046-->
Użytkownicy końcowi mogą teraz wybrać grupę, do której ma należeć ich urządzenie, przez otagowanie jej bezpośrednio z poziomu aplikacji Portal firmy dla systemu Windows 10.

<!-- ########################## -->
## <a name="june-2017"></a>Czerwiec 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nowy dostęp administracji opartej na rolach dla administratorów usługi Intune   <!-- 1099990 -->  
Nowa rola administratora dostępu warunkowego jest dodawana w celu wyświetlania, tworzenia, modyfikowania i usuwania zasad dostępu warunkowego usługi Azure AD. Wcześniej uprawnienie to mieli tylko administratorzy globalni i administratorzy zabezpieczeń. Te uprawnienia roli mogą być nadane administratorom usługi Intune, aby mieli oni dostęp do zasad dostępu warunkowego.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Oznaczanie urządzeń należących do firmy przy użyciu numeru seryjnego <!-- 1215070 -->  
Usługa Intune obsługuje teraz przekazywanie numerów seryjnych systemów iOS, macOS i Android jako identyfikatorów urządzeń firmowych. Nie można używać numerów seryjnych do blokowania rejestracji urządzeń osobistych, ponieważ numery seryjne nie są weryfikowane podczas rejestracji. Blokowanie urządzeń osobistych za pomocą numerów seryjnych będzie obsługiwane w najbliższej przyszłości.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nowe akcje zdalne dla urządzeń z systemem iOS <!-- 854689 -->
W tej wersji dodano dwie nowe akcje zdalnego urządzenia dla udostępnionych urządzeń iPad, które zarządzają aplikacją Apple Classroom:

-   [Wyloguj bieżącego użytkownika](device-logout-user.md) — powoduje wylogowanie bieżącego użytkownika z wybranego urządzenia z systemem iOS.
-   [Usuń użytkownika](device-remove-user.md) — powoduje usunięcie wybranego użytkownika z lokalnej pamięci podręcznej na urządzeniu z systemem iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Obsługa udostępnionych urządzeń iPad przy użyciu aplikacji iOS Classroom <!-- 1044681 -->
W tej wersji rozszerzono obsługę funkcji zarządzania aplikacją Classroom dla systemu iOS w celu uwzględnienia uczniów logujących się na współużytkowanych tabletach iPad za pomocą zarządzanych identyfikatorów Apple ID.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Zmiany do wbudowanych aplikacji usługi Intune <!-- 1332306 -->
Wcześniej usługa Intune zawierała kilka wbudowanych aplikacji, które można było szybko przypisać. Na podstawie Twojej opinii usunęliśmy tę listę, a wbudowane aplikacje nie będą już dla Ciebie widoczne.
Jeśli jednak przypisano już jakiekolwiek wbudowane aplikacje, będą one nadal widoczne na liście aplikacji. W razie potrzeby te aplikacje mogą pozostać przypisane.
W nowszej wersji planujemy dodać łatwiejszy sposób wybierania i przypisywania wbudowanych aplikacji z witryny Azure Portal.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Łatwiejsza instalacja aplikacji usługi Office 365 <!--- 1121362 --->
Nowy typ aplikacji usługi **Office 365 ProPlus** ułatwia przypisywanie aplikacji usługi Office 365 ProPlus 2016 do zarządzanych przez Ciebie urządzeń z najnowszą wersją systemu Windows 10. Ponadto jeśli masz licencje na programy Microsoft Project i Microsoft Visio, masz możliwość ich zainstalowania. Potrzebne aplikacje są ze sobą powiązane i wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.
Aby uzyskać więcej informacji, zobacz [How to add Office 365 apps for Windows 10](apps-add-office365.md) (Jak dodawać aplikacje usługi Office 365 dla systemu Windows 10).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Obsługa aplikacji offline ze Sklepu Microsoft dla Firm <!--- 777044 --->
Aplikacje offline zakupione w Sklepie Microsoft dla Firm będą teraz synchronizowane z witryną Azure Portal. Następnie można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, a nie przez sklep.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Aplikacja Microsoft Teams znajduje się obecnie na zawierającej zatwierdzone aplikacje liście dostępu warunkowego na podstawie aplikacji   <!-- 1257019 -->
Aplikacja Microsoft Teams dla systemów iOS i Android stanowi teraz część zatwierdzonych aplikacji dla zasad dostępu warunkowego na podstawie aplikacji dla programów Exchange i SharePoint Online. Można skonfigurować tę aplikację za pomocą bloku Intune App Protection w witrynie Azure Portal do wszystkich dzierżawców używających obecnie dostępu warunkowego na podstawie aplikacji.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Integracja aplikacji Managed Browser i serwera proxy aplikacji <!-- 1287310 -->
Aplikację Intune Managed Browser można teraz zintegrować z usługą serwera proxy aplikacji usługi Azure AD, aby umożliwić użytkownikom dostęp do wewnętrznych witryn internetowych nawet wtedy, gdy pracują zdalnie. Użytkownicy przeglądarki wprowadzają adres URL witryny w normalny sposób, a aplikacja Managed Browser kieruje żądanie za pośrednictwem bramy internetowej serwera proxy aplikacji. Aby uzyskać więcej informacji, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nowe ustawienia konfiguracji aplikacji dla Intune Managed Browser <!-- 682951 -->
W tej wersji dodano dodatkowe konfiguracje dla aplikacji Intune Managed Browser dla systemów iOS i Android. Można teraz skonfigurować domyślną stronę główną i zakładki do przeglądarki przy użyciu zasad konfiguracji aplikacji.
Aby uzyskać więcej informacji, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser](app-configuration-managed-browser.md).

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Ustawienia funkcji BitLocker dla systemu Windows 10  <!-- 951707 -->
Teraz można skonfigurować ustawienia funkcji BitLocker dla urządzeń z systemem Windows 10 przy użyciu nowego profilu urządzeń usługi Intune. Można na przykład wymagać szyfrowania urządzeń, a także skonfigurować dodatkowe ustawienia, które są stosowane po włączeniu funkcji BitLocker.
Aby uzyskać więcej informacji, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
W tej wersji dodano nowe ustawienia profilu ograniczeń urządzenia z systemem Windows 10 w następujących kategoriach:

-  Usługa Windows Defender
-  Sieć komórkowa i łączność
-  Środowisko ekranu blokady
-  Ochrona prywatności
-  Wyszukaj
-  W centrum uwagi Windows
-  Przeglądarka Microsoft Edge

Aby uzyskać więcej informacji o ustawieniach systemu Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 i nowszym](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Aplikacja Portal firmy dla systemu Android ma teraz nowe środowisko użytkownika końcowego dla zasad ochrony aplikacji <!--1305217-->
Na podstawie opinii klientów zmodyfikowaliśmy aplikację Portal firmy dla systemu Android w celu wyświetlania przycisku **Dostęp do zawartości firmowej**. Ma to na celu zapobieganie niepotrzebnemu przechodzeniu przez użytkowników końcowych przez proces rejestracji, gdy potrzebują tylko dostępu do aplikacji obsługujących zasady ochrony aplikacji, czyli funkcję zarządzania aplikacjami mobilnymi usługi Intune. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nowa akcja menu do łatwego usuwania Portalu firmy <!--1164569-->
W odpowiedzi na opinie użytkowników w aplikacji Portal firmy dla systemu Android została dodana nowa akcja menu do inicjowania usunięcia Portalu firmy z urządzenia. Powoduje ona usunięcie urządzenia z zarządzania w usłudze Intune, dzięki czemu użytkownik może samodzielnie usunąć aplikację z urządzenia. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md) oraz w [dokumentacji użytkownika końcowego systemu Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Ulepszenia synchronizacji aplikacji w wersji Aktualizacja systemu Windows 10 dla twórców <!--676505-->
Aplikacja Portal firmy dla systemu Windows 10 będzie teraz automatycznie inicjować synchronizację żądań instalacji aplikacji dla urządzeń z systemem w wersji Aktualizacja systemu Windows 10 dla twórców (wersja 1703). Pozwoli to ograniczyć problem związany z zatrzymywaniem się instalacji aplikacji w stanie „Oczekiwanie na synchronizację”. Ponadto użytkownicy będą mogli ręcznie zainicjować synchronizację z poziomu aplikacji. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nowe środowisko z przewodnikiem dla Portalu firmy systemu Windows 10 <!---1058938--->
Aplikacja Portal firmy dla systemu Windows 10 będzie zawierać wskazówki przewodnika usługi Intune dla urządzeń, które nie zostały zidentyfikowane ani zarejestrowane. Nowe środowisko obejmuje instrukcje krok po kroku, które prowadzą użytkownika przez proces rejestracji w usłudze Azure Active Directory (wymaganej dla funkcji dostępu warunkowego) oraz rejestracji MDM (wymaganej dla funkcji zarządzania urządzeniami). Przewodnik obsługi będzie dostępny na stronie głównej Portalu firmy. Użytkownicy mogą nadal używać aplikacji, jeśli nie ukończą rejestracji, ale może wystąpić ograniczenie funkcjonalności.

Ta aktualizacja jest widoczna tylko na urządzeniach z Rocznicową aktualizacją systemu Windows 10 (kompilacją 1607) i nowszymi wersjami. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Konsole administracyjne usługi Microsoft Intune i dostępu warunkowego są ogólnie dostępne
Firma Microsoft informuje o ogólnej dostępności nowej usługi Intune w konsoli administracyjnej witryny Azure Portal i konsoli administracyjnej dostępu warunkowego. Za pomocą usługi Intune w witrynie Azure Portal można teraz zarządzać wszystkimi możliwościami MAM i MDM usługi Intune w jednym skonsolidowanym środowisku administratora oraz korzystać z funkcji grupowania i określania odbiorców docelowych w usłudze Azure AD. Dostęp warunkowy na platformie Azure oferuje zaawansowane możliwości w usługach Azure AD i Intune w jednej ujednoliconej konsoli. W środowisku administracyjnym przeniesienie na platformę Azure umożliwia korzystanie z nowoczesnych przeglądarek.

Usługa Intune jest teraz widoczna bez etykiety **wersji zapoznawczej** w witrynie Azure Portal pod adresem portal.azure.com.

Obecnie istniejący klienci nie muszą podejmować żadnych działań, chyba że użytkownik otrzyma jeden z serii komunikatów z centrum wiadomości z żądaniem podjęcia działania, dzięki któremu będziemy mogli migrować jego grupy. Użytkownik mógł również otrzymać powiadomienie z centrum wiadomości informujące o tym, że migracja trwa dłużej z powodu błędów występujących po naszej stronie. Firma Microsoft nadal usilnie pracuje nad tym, by przeprowadzić migrację wszystkich klientów, na których to miało wpływ.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Ulepszone kafelki aplikacji w Portalu firmy dla systemu iOS
Zaktualizowaliśmy wygląd kafelków aplikacji na stronie głównej, aby odpowiadał on kolorowi ustawionemu dla Portalu firmy. Aby uzyskać więcej informacji, zobacz temat [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Selektor konta już dostępny w aplikacji Portal firmy dla systemu iOS
Dla użytkowników urządzeń z systemem iOS nasz nowy selektor konta może być widoczny po zalogowaniu się do Portalu firmy, jeśli użyją konta służbowego do zalogowania się do innych aplikacji firmy Microsoft. Aby uzyskać więcej informacji, zobacz temat [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="may-2017"></a>Maj 2017 r.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Zmiana urzędu MDM bez wyrejestrowania zarządzanych urządzeń <!--1103950-->
Teraz będzie można zmienić urząd MDM bez konieczności kontaktowania się z działem pomocy technicznej firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. W konsoli programu Configuration Manager można [zmienić urząd MDM](/sccm/mdm/deploy-use/change-mdm-authority), wybierając opcję Ustaw Menedżera konfiguracji (hybrydowe) zamiast opcji Microsoft Intune (autonomiczne) lub odwrotnie.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Ulepszone powiadomienia dotyczące numerów PIN wymaganych do uruchomiania urządzeń z systemem Samsung Knox <!--1087143-->
W przypadku gdy użytkownicy końcowi muszą skonfigurować numer PIN wpisywany po uruchomieniu urządzenia z systemem Samsung Knox w celu zapewnienia zgodności z szyfrowaniem, dotknięcie wyświetlonego powiadomienia umożliwi przejście bezpośrednio do odpowiedniego ustawienia.  Wcześniej dotknięcie powiadomienia na urządzeniu użytkownika końcowego powodowało przejście do ekranu zmiany hasła.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Obsługa usługi Apple School Manager (ASM) w przypadku udostępnionego urządzenia iPad <!-- 748864, 770395-->

Usługa Intune obsługuje obecnie korzystanie z usługi Apple School Manager (ASM) zamiast z programu Device Enrollment Program firmy Apple w celu umożliwienia rejestracji urządzeń z systemem iOS przy pierwszym uruchomieniu. Dołączenie do usługi ASM jest wymagane w celu umożliwienia korzystania z aplikacji Classroom na udostępnionych urządzeniach iPad oraz włączenia synchronizacji danych pomiędzy usługą ASM i usługą Azure Active Directory za pośrednictwem usługi School Data Sync (SDS) firmy Microsoft. Aby uzyskać więcej informacji, zobacz [Włączanie rejestracji urządzeń z systemem iOS za pomocą usługi Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Konfigurowanie udostępnionych urządzeń iPad do pracy z aplikacją Classroom wymaga konfiguracji programu Education dla systemu iOS na platformie Azure, które nie są jeszcze dostępne.  Ta funkcja zostanie wkrótce dodana.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Zapewnienie pomocy zdalnej na urządzeniach z systemem Android przy użyciu programu TeamViewer <!-- 675418 -->

Usługa Intune może teraz korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Android. Więcej informacji można znaleźć w temacie [Zapewnienie pomocy zdalnej dla urządzeń z systemem Android zarządzanych przy użyciu usługi Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nowe warunki zasad ochrony aplikacji dla funkcji zarządzania aplikacjami mobilnymi (MAM) <!-- 679864 -->

Teraz można ustawić wymóg dotyczący funkcji MAM bez użytkowników rejestracji, co wymusza następujące zasady:

- Minimalna wersja aplikacji
- Minimalna wersja systemu operacyjnego
- Minimalna wersja zestawu SDK aplikacji usługi Intune dla docelowych aplikacji (tylko system iOS)

Funkcja ta jest dostępna w systemach Android i iOS. Usługa Intune obsługuje wymuszenie wersji minimalnej dla wersji platformy systemu operacyjnego, wersji aplikacji i zestawu SDK aplikacji usługi Intune. W systemie iOS dla aplikacji ze zintegrowanym zestawem SDK można również ustawić wymóg minimalnej wersji na poziomie zestawu SDK. Użytkownik nie będzie mógł uzyskać dostępu do docelowej aplikacji w przypadku, gdy nie zostaną spełnione wymogi dotyczące minimalnej wersji w ramach zasad ochrony aplikacji na trzech różnych poziomach wymienionych powyżej. W tym momencie użytkownik będzie mógł usunąć swoje konto (w przypadku aplikacji z obsługą wielu tożsamości), zamknąć aplikację lub zaktualizować wersję systemu operacyjnego lub aplikacji.

Można również skonfigurować dodatkowe ustawienia, aby wyświetlić na urządzeniu użytkownika powiadomienie z zaleceniem uaktualnienia systemu operacyjnego lub aplikacji niepowodujące blokady urządzenia. Takie powiadomienie można zamknąć, aby następnie korzystać z aplikacji w zwykły sposób.

Więcej informacji można znaleźć w tematach [Ustawienia zasad ochrony aplikacji dla systemu iOS](app-protection-policy-settings-ios.md) oraz [Ustawienia zasad ochrony aplikacji dla systemu Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurowanie ustawień aplikacji dla programu Android for Work <!-- 621621 -->
Niektóre aplikacje dla systemu Android ze sklepu obsługują opcje konfiguracji zarządzanych, które umożliwiają administratorowi IT kontrolowanie działania aplikacji w profilu służbowym. Przy użyciu usługi Intune można teraz wyświetlić konfiguracje obsługiwane przez aplikację i skonfigurować je w witrynie Azure Portal za pomocą projektanta konfiguracji lub edytora JSON. Aby uzyskać więcej informacji, zobacz artykuł [Use app configurations for Android for Work](app-configuration-policies-use-android.md) (Używanie konfiguracji aplikacji dla programu Android for Work).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nowe możliwości konfiguracji aplikacji dla funkcji MAM bez rejestracji <!-- 677969 -->
Teraz można tworzyć zasady konfiguracji aplikacji za pomocą funkcji MAM bez użycia kanału rejestracji. Ta funkcja jest odpowiednikiem zasad konfiguracji aplikacji dostępnych w konfiguracji aplikacji funkcji zarządzania urządzeniami mobilnymi (MDM). Przykład konfiguracji aplikacji przy użyciu funkcji MAM bez rejestracji znajduje się w temacie [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurowanie list dozwolonych i zablokowanych adresów URL dla programu Managed Browser <!-- 682960 -->
Teraz można skonfigurować listę dozwolonych i zablokowanych domen oraz adresów URL dla programu Managed Browser w usłudze Intune przy użyciu ustawień konfiguracji aplikacji w witrynie Azure Portal. Ustawienia te można skonfigurować niezależnie od tego, czy są one używane na urządzeniu zarządzanym, czy niezarządzanym. Aby uzyskać więcej informacji, zobacz temat [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Widok pomocy technicznej zasad ochrony aplikacji <!-- 1069473 -->
Użytkownicy pomocy technicznej z działu IT mogą teraz sprawdzić stan licencji użytkownika i stan aplikacji zasad ochrony aplikacji przypisane do użytkowników w bloku Rozwiązywanie problemów. Aby uzyskać szczegółowe informacje, zobacz temat [Rozwiązywanie problemów](./help-desk-operators.md).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Kontrola odwiedzin w witrynach internetowych na urządzeniach z systemem iOS <!-- 723832 -->
Teraz przy użyciu jednej z następujących dwóch metod można kontrolować, które witryny internetowe mogą odwiedzać użytkownicy urządzeń z systemem iOS:

- Dodaj dozwolone i zablokowane adresy URL przy użyciu wbudowanych filtrów zawartości sieci Web w urządzeniach firmy Apple.

- Zezwalaj tylko na dostęp do określonych witryn sieci Web za pośrednictwem przeglądarki Safari. Dla każdej określonej witryny jest tworzona zakładka w przeglądarce Safari.

Aby uzyskać więcej informacji, zobacz temat [Ustawienia filtru zawartości sieci Web dla urządzeń z systemem iOS](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Wstępna konfiguracja uprawnień urządzenia dla aplikacji Android for Work <!-- 621614 -->
W przypadku aplikacji wdrożonych w ramach profilów służbowych urządzenia z programem Android for Work można teraz skonfigurować stan uprawnień dla poszczególnych aplikacji.  Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika.  Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik końcowy otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu. Ta funkcja pozwala zdefiniować uprawnienia w imieniu użytkownika końcowego.  Można skonfigurować uprawnienia, aby a) automatycznie odmawiać bez powiadomienia użytkownika, b) automatycznie zatwierdzać bez powiadomienia użytkownika lub c) monitować użytkownika o zaakceptowanie lub odmówienie. Aby uzyskać więcej informacji, zobacz temat [Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Ustawienie numeru PIN dla aplikacji na urządzeniach z programem Android for Work <!-- 728976, 1102534 -->
Na urządzeniach z systemem Android w wersji 7.0 lub nowszej z profilem służbowym zarządzanym jako urządzenie z programem Android for Work możliwe będzie zdefiniowanie zasad kodu dostępu, które będą dotyczyć tylko aplikacji w profilu służbowym.  Dostępne opcje:

- Zdefiniowanie zasad kodu dostępu obejmujących całe urządzenie — jest to kod dostępu, którego użytkownik musi użyć w celu odblokowania całego urządzenia.
- Zdefiniowanie zasad kodu dostępu obejmujących wyłącznie profil służbowy — użytkownicy otrzymają monit o podanie kodu dostępu przy każdym otwarciu dowolnej aplikacji w profilu służbowym.
- Zdefiniowanie zasad kodu dostępu obejmujących zarówno urządzenie, jak i profil służbowy — administrator IT ma możliwość zdefiniowania zarówno zasad kodu dostępu dla urządzenia, jak i zasad kodu dostępu dotyczących profilu służbowego o różnej sile (np. 4-cyfrowy numer PIN do odblokowywania urządzenia i 6-cyfrowy numer PIN do otwierania dowolnej aplikacji w profilu służbowym).

Aby uzyskać więcej informacji, zobacz temat [Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Ta opcja jest dostępna wyłącznie w systemie Android w wersji 7.0 i nowszych.  Domyślnie użytkownik końcowy może używać dwóch różnych numerów PIN lub wybrać opcję połączenia dwóch zdefiniowanych numerów PIN w celu uzyskania numeru PIN o większej sile.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nowe ustawienia dla urządzeń z systemem Windows 10 <!-- 978585 -->
Dodaliśmy nowe [ustawienia ograniczeń dla urządzenia z systemem Windows](device-restrictions-windows-10.md), które kontrolują takie funkcje, jak ekrany bezprzewodowe, odnajdywanie urządzeń, przełączanie zadań i komunikaty o błędach karty SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Aktualizacje konfiguracji certyfikatu <!-- 918991 and 823198 -->
Podczas tworzenia profilu certyfikatu SCEP dla pozycji <strong>Format nazwy podmiotu</strong>, opcja <strong>Niestandardowy</strong> jest dostępna dla urządzeń z systemami iOS, Android i Windows. Przed tą aktualizacją pole <strong>Niestandardowy</strong> było dostępne tylko dla urządzeń z systemem iOS. Aby uzyskać więcej informacji, zobacz [Tworzenie profilu certyfikatu protokołu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile).

Podczas tworzenia profilu certyfikatu PKCS dla pozycji **Alternatywna nazwa podmiotu** dostępna jest opcja **Atrybut niestandardowy usługi Azure AD**. Opcja **Dział** jest dostępna po wybraniu opcji **Atrybut niestandardowy usługi Azure AD**. Aby uzyskać więcej informacji, zobacz [Tworzenie profilu certyfikatu protokołu PKCS](certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurowanie wielu aplikacji, które można uruchomić, gdy urządzenie z systemem Android jest w trybie kiosku <!-- 662059 -->
Wcześniej można było skonfigurować tylko jedną aplikację możliwą do uruchomienia, gdy urządzenie z systemem Android jest w trybie kiosku. Teraz można skonfigurować wiele aplikacji przy użyciu identyfikatora aplikacji, adres URL sklepu lub wybierając zarządzaną już aplikację systemu Android. Aby uzyskać więcej informacji, zobacz [Ustawienia trybu kiosku](device-restrictions-android.md#kiosk).



<!-- ########################## -->
## <a name="april-2017"></a>Kwiecień 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Obsługa zarządzania aplikacji Classroom firmy Apple
Teraz można zarządzać aplikacją Classroom dla systemu iOS na urządzeniach iPad. Skonfiguruj aplikację Classroom na tablecie iPad dla nauczycieli, podając poprawne dane dotyczące klasy i uczniów, następnie skonfiguruj tablety iPad dla uczniów zarejestrowane dla danej klasy, aby mieć możliwość sterowania nimi przy użyciu aplikacji.
Aby uzyskać szczegółowe informacje, zobacz temat [Konfigurowanie ustawień usług edukacyjnych dla urządzeń z systemem iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Obsługa opcji zarządzanych konfiguracji dla aplikacji systemu Android <!-- 621621 -->
Za pośrednictwem usługi Intune można teraz skonfigurować przeznaczone dla systemu Android aplikacje ze sklepu Play, które obsługują zarządzane opcje konfiguracji.  Ta funkcja umożliwia pracownikom działu IT wyświetlanie listy wartości konfiguracji obsługiwanych przez aplikację oraz zapewnia najwyższej klasy interfejs użytkownika z przewodnikiem, dzięki któremu można skonfigurować te wartości.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nowe zasady dla systemu Android dotyczące złożonych numerów PIN <!-- 722069 -->
W przypadku urządzeń z systemem Android 5.0 lub nowszym można teraz ustawić w profilu urządzenia wymagany typ [hasła](device-restrictions-android.md#password) na „Złożona wartość liczbowa”.  Użyj tego ustawienia, aby uniemożliwić użytkownikom tworzenie numerów PIN zawierających powtarzające się lub kolejne liczby, np. 1111 lub 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Dodatkowa obsługa urządzeń z programem Android for Work
- **Zarządzaj ustawieniami hasła i profilu służbowego** <!-- 612808 -->

  Te nowe zasady ograniczeń dla urządzeń z programem Android for Work umożliwiają teraz zarządzanie ustawieniami hasła i profilu służbowego na zarządzanych urządzeniach z programem Android for Work.

- **Zezwalaj na współużytkowanie danych między profilem służbowym i osobistym** <!-- 1045102 -->

Ten profil ograniczeń urządzenia z programem Android for Work oferuje teraz nowe opcje pozwalające skonfigurować udostępnianie danych między profilami służbowym i osobistym.

- **Ogranicz kopiowanie i wklejanie między profilami służbowymi i osobistymi** <!-- 1046094 -->

  Nowy niestandardowy profil urządzenia dla urządzeń z programem Android for Work umożliwia obecnie określenie, czy akcje kopiowania i wklejania między aplikacjami służbowymi i osobistymi mają być dozwolone.

Aby uzyskać więcej informacji, zobacz artykuł [Ograniczenia urządzenia z programem Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Przypisuj aplikacje LOB do urządzeń z systemem iOS lub Android <!-- 1057568 -->
Możesz teraz przypisywać różne aplikacje biznesowe (LOB) dla systemu [iOS](lob-apps-ios.md) (pliki ipa) lub [Android](lob-apps-android.md) (pliki apk) do użytkowników lub urządzeń.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nowe zasady dotyczące urządzeń dla systemu iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplikacje na ekranie głównym** — pozwala określić, które aplikacje użytkownik może zobaczyć na [ekranie głównym swojego urządzenia z systemem iOS](home-screen-settings-ios.md). Zasady te zmieniają układ ekranu głównego, ale nie wdrażają żadnych aplikacji.

- **Połączenia z urządzeniami AirPrint** — pozwala określić, z którymi [urządzeniami AirPrint](air-print-settings-ios-macos.md) (drukarkami sieciowymi) użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Połączenia z urządzeniami AirPlay** — pozwala określić, z którymi [urządzeniami AirPlay](airplay-settings-ios.md) (np. urządzeniami Apple TV) użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Niestandardowy komunikat ekranu blokady** — pozwala skonfigurować niestandardowy komunikat, który użytkownicy zobaczą na ekranie blokady urządzenia z systemem iOS zamiast domyślnego komunikatu ekranu blokady. Aby uzyskać więcej informacji, zobacz [Aktywowanie trybu zgubienia na urządzeniach z systemem iOS](device-lost-mode.md).

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Ogranicz powiadomienia wypychane dla aplikacji systemu iOS <!-- 723767 -->
W profilu ograniczeń urządzenia w usłudze Intune możesz teraz skonfigurować następujące [ustawienia powiadomień](app-notification-settings-ios.md) dla urządzeń z systemem iOS:

- W pełni włączyć lub wyłączyć powiadomienia dla określonej aplikacji.
- Włączyć lub wyłączyć powiadomienia w centrum powiadomień dla określonej aplikacji.
- Określić typ alertu: **Brak**, **Transparent** lub **Alert modalny**.
- Określić, czy identyfikatory są dozwolone dla tej aplikacji.
- Określić, czy dźwięki powiadomień są dozwolone.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Skonfiguruj aplikacje systemu iOS do autonomicznego uruchamiania w trybie pojedynczej aplikacji <!-- 737837 -->
Możesz teraz użyć profilu urządzenia w usłudze Intune do skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w [autonomicznym trybie pojedynczej aplikacji](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane, aby mogło uruchamiać wyłącznie tę aplikację. Opcję tę można przykładowo wykorzystać w przypadku konfigurowania aplikacji, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Skonfiguruj zaufane domeny dla poczty e-mail i przeglądania Internetu na urządzeniach z systemem iOS <!-- 723765 -->
W profilu ograniczeń urządzenia z systemem iOS możesz teraz skonfigurować następujące [ustawienia domen](device-restrictions-ios.md#domains):

- **Nieoznaczone domeny poczty e-mail** — wiadomości e-mail wysyłane lub odbierane przez użytkownika, które nie pasują do domen określonych w tym miejscu, będą oznaczone jako niezaufane.

- **Zarządzane domeny sieci Web** — dokumenty pobierane z adresów URL określonych w tym miejscu będą uznawane za zarządzane (tylko przeglądarka Safari).  

- **Domeny automatycznego uzupełniania haseł przeglądarki Safari** — użytkownicy mogą zapisywać hasła w przeglądarce Safari tylko w przypadku adresów URL spełniających wzorce określone w tym miejscu. Aby użyć tego ustawienia, urządzenie musi być w trybie nadzorowanym i nie może być skonfigurowane dla wielu użytkowników. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikacje VPP dostępne w aplikacji Portal firmy dla systemu iOS <!-- 748782 -->
Możesz teraz przypisać aplikacje dla systemu iOS zakupione zbiorczo (VPP) jako **Dostępne** instalacje do użytkowników końcowych. Użytkownicy końcowi potrzebują konta sklepu Apple Store, aby zainstalować aplikację.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizuj książki elektroniczne ze sklepu Apple VPP Store <!-- 800878 -->
Możesz teraz [synchronizować książki](vpp-apps-ios.md) zakupione w sklepie programu zakupów zbiorczych Apple przy użyciu usługi Intune i przypisywać je do użytkowników.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Zarządzanie wieloma użytkownikami na urządzeniach z systemem Samsung Knox Standard <!-- 971988 -->
Urządzenia z systemem Samsung Knox Standard obsługują teraz funkcję [zarządzania wieloma użytkownikami](android-enroll.md) przez usługę Intune. Oznacza to, że użytkownicy końcowi mogą zalogować się na urządzeniu przy użyciu poświadczeń usługi Azure Active Directory lub wylogować się z niego, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane.  Po zalogowaniu się użytkownicy końcowi otrzymują dostęp do aplikacji oraz zostają wobec nich zastosowane zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Dodatkowe ustawienia ograniczeń urządzeń z systemem Windows <!-- 818566 -->
Dodaliśmy obsługę dodatkowych [ustawień ograniczeń urządzeń z systemem Windows](device-restrictions-windows-10.md), między innymi dodatkową obsługę przeglądarki Microsoft Edge, dostosowywanie ekranu blokady na urządzeniu, dostosowywanie menu Start, tapetę zestawu wyszukiwania W centrum uwagi Windows oraz ustawienia serwera proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Obsługa wielu użytkowników w aktualizacji Windows 10 Creators Update <!-- 822547 -->
Dodaliśmy obsługę [zarządzania wieloma użytkownikami](windows-enroll.md) na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Oznacza to, że różni użytkownicy standardowi po zalogowaniu się do urządzenia przy użyciu poświadczeń usługi Azure AD otrzymują wszelkie aplikacje i zasady, które zostały przypisane do ich nazw użytkowników. Obecnie użytkownicy nie mogą używać witryny internetowej Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Świeży początek dla komputerów z systemem Windows 10<!-- 1004830 -->
Dla komputerów z systemem Windows 10 dostępna jest nowa [akcja odświeżonego uruchomienia urządzenia](device-fresh-start.md).  Po wykonaniu tej akcji wszelkie aplikacje zainstalowane na komputerze zostaną usunięte, a komputer zostanie automatycznie zaktualizowany do najnowszej wersji systemu Windows. Funkcja może być przydatna do usuwania wstępnie zainstalowanych aplikacji OEM, które są często dostarczane z nowymi komputerami. Możesz zdecydować, czy dane użytkownika zostaną zachowane w przypadku wykonania tej akcji dla urządzenia.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Dodatkowe ścieżki uaktualniania systemu Windows 10 <!-- 903672 -->
Można teraz tworzyć [zasady uaktualniania wersji umożliwiające uaktualnienie urządzeń](edition-upgrade-configure-windows-10.md) do następujących dodatkowych wersji systemu Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->
Teraz możesz łączyć dużą liczbę urządzeń z aktualizacją systemu Windows 10 dla twórców z usługami Azure Active Directory oraz Intune, korzystając z aplikacji Windows Configuration Designer (WCD). Aby włączyć [zbiorcze rejestrowanie w usłudze MDM](windows-bulk-enroll.md) dla dzierżawy usługi Azure AD, utwórz pakiet aprowizacyjny, który dołącza urządzenia do dzierżawy usługi Azure AD, przy użyciu aplikacji Windows Configuration Designer, i zastosuj pakiet do firmowych urządzeń, które chcesz zarejestrować i którymi chcesz zarządzać w sposób zbiorczy. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia aplikacji Portal firmy nie są obecnie obsługiwane.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nowe ustawienia MAM dla numerów PIN i zarządzanych lokalizacji przechowywania <!-- 581122, 736644 -->
Obecnie są dostępne dwa nowe ustawienia aplikacji, które pomagają w zarządzaniu aplikacjami mobilnymi (MAM):

- **Wyłącz numer PIN aplikacji, jeśli numer PIN urządzenia jest zarządzany** — wykrywa, czy numer PIN urządzenia jest obecny na zarejestrowanym urządzeniu; jeśli tak jest, pomija numer PIN aplikacji wyzwalany przez zasady ochrony aplikacji. Ustawienie to umożliwia zredukowanie liczby monitów o numer PIN wyświetlanych dla użytkowników podczas otwierania na zarejestrowanym urządzeniu aplikacji z włączonym zarządzaniem aplikacjami mobilnymi. Funkcja ta jest dostępna dla systemów Android i iOS.

- **Wybierz, w których usługach magazynu można zapisywać dane firmowe** — umożliwia określenie lokalizacji przechowywania, w której należy zapisywać dane firmowe. Użytkownicy mogą zapisywać w wybranych usługach służących do zarządzania lokalizacjami przechowywania. Oznacza to, że wszystkie inne usługi zarządzające lokalizacjami przechowywania, które nie znajdą się na liście, zostaną zablokowane.

  Lista obsługiwanych usług zarządzających lokalizacjami przechowywania:

  - OneDrive
  - Business SharePoint Online
  - Magazyn lokalny

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal pomocy technicznej służący do rozwiązywania problemów <!-- 907448 -->
Nowy [portal służący do rozwiązywania problemów](help-desk-operators.md) umożliwia operatorom pomocy technicznej i administratorom usługi Intune wyświetlać użytkowników i ich urządzenia oraz wykonywać zadania mające na celu rozwiązywanie problemów technicznych związanych z usługą Intune.

<!-- ########################## -->
## <a name="march-2017"></a>Marzec 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Obsługa trybu utraty w systemie iOS <!--431695-->
Dla urządzeń z systemem iOS w wersji 9.3 i późniejszych w usłudze Intune dodano obsługę **trybu utraty**. Teraz możesz zablokować urządzenie, aby uniemożliwić jego użycie w jakikolwiek sposób, oraz wyświetlić komunikat i numer telefonu kontaktowego na ekranie blokady urządzenia.

Użytkownik końcowy nie będzie mógł odblokować urządzenia aż do chwili, gdy administrator wyłączy tryb utraty. Po włączeniu trybu utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby wyświetlić w konsoli usługi Intune lokalizację geograficzną urządzenia na mapie.

Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym.

Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)

### <a name="improvements-to-device-actions-report---677150--"></a>Ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami <!--677150-->
Wprowadziliśmy ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami w celu zwiększenia wydajności. Ponadto raport można teraz filtrować według stanu. Można na przykład filtrować raport w taki sposób, aby wyświetlić tylko te akcje związane z urządzeniem, które zostały zakończone.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Przypisywanie aplikacji biznesowych do użytkowników z wyrejestrowanymi urządzeniami <!--748823-->
Użytkownikom można teraz przypisywać aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, w celu jej zainstalowania użytkownik musi przejść do witryny sieci Web Portal firmy zamiast do aplikacji Portal firmy.

### <a name="new-compliance-reports---846671--"></a>Nowe raporty dotyczące zgodności <!--846671-->
Można teraz korzystać z raportów zgodności, które dostarczają informacje na temat stanu zgodności urządzeń w Twojej firmie i pozwalają na szybkie rozwiązywanie problemów ze zgodnością napotykanych przez użytkowników. Możliwe jest wyświetlanie informacji dotyczących następujących kwestii:

- ogólny stan zgodności urządzeń,
- stan zgodności poszczególnych ustawień,
- stan zgodności poszczególnych zasad.

Raportów można także użyć do przechodzenia do informacji szczegółowych dotyczących poszczególnych urządzeń, aby wyświetlić konkretne ustawienia i zasady, które mają wpływ na to urządzenie.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w witrynie Azure Portal. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.


<!-- ########################## -->
## <a name="february-2017"></a>Luty 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych <!--747600, 795782-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.

* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.  
* Tylko w przypadku systemu iOS i Android istnieje dodatkowa opcja blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](device-enrollment.md).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Wyświetlanie wszystkich akcji na urządzeniach zarządzanych <!--677150-->
Nowy raport __Akcje urządzenia__ pokazuje, kto wykonał akcje zdalne, takie jak przywrócenie stanu fabrycznego na urządzeniach, a ponadto wyświetla stan takich akcji. Zobacz [Co to jest zarządzanie urządzeniami?](device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->
W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Wyświetlanie kategorii urządzeń <!--814654-->
Kategorię urządzenia można teraz wyświetlić jako kolumnę na liście urządzeń. Można także edytować kategorię z poziomu sekcji właściwości w bloku właściwości urządzenia. Zobacz [Jak dodać aplikację do usługi Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurowanie ustawień usługi Windows Update dla firm <!--776716-->

Windows jako usługa to nowy sposób udostępniania aktualizacji dla systemu Windows 10. Począwszy od systemu Windows 10, wszystkie nowe funkcjonalne i jakościowe aktualizacje będą obejmować zawartość wszystkich poprzednich aktualizacji. Oznacza to, że po zainstalowaniu najnowszej aktualizacji masz pewność, iż urządzenia systemu Windows 10 są całkowicie aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.

Za pomocą usługi Windows Update dla firm można uprościć zarządzanie aktualizacjami, dzięki czemu nie trzeba zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Nadal możesz zarządzać ryzykiem w swoich środowiskach, konfigurując strategię wdrażania aktualizacji, dzięki czemu usługa Windows Update zagwarantuje zainstalowanie aktualizacji w odpowiednim czasie. Usługa Microsoft Intune zapewnia możliwość konfigurowania ustawień aktualizacji na urządzeniach oraz odroczenia instalacji aktualizacji. Usługa Intune nie przechowuje aktualizacji, a jedynie przypisanie zasad aktualizacji. W celu aktualizacji urządzenia uzyskują dostęp bezpośrednio do witryny Windows Update. Użyj usługi Intune do konfigurowania **pierścieni aktualizacji systemu Windows 10** i zarządzania nimi. Pierścień aktualizacji zawiera grupę ustawień, które konfigurują, kiedy i w jaki sposób aktualizacje systemu Windows 10 mają zostać zainstalowane. Aby uzyskać szczegółowe informacje, zobacz sekcję [Konfigurowanie ustawień usługi Windows Update dla firm](windows-update-for-business-configure.md).
