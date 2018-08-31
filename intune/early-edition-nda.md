---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e24414d28b8adeae7dfbedb606ca1a7d21497a3f
ms.sourcegitcommit: 698af815f6de2c4f003f6da428bbfb0680daafa0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2018
ms.locfileid: "43093201"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>Wczesna wersja usługi Microsoft Intune — sierpień 2018

> [!Note]
> Powiadomienie dotyczące umowy o zachowaniu poufności: dla usługi Intune opracowywane są następujące zmiany. Te informacje są udostępniane pod rygorem umowy o zachowaniu poufności w bardzo ograniczonym zakresie. Nie wolno publikować żadnych tych informacji w mediach społecznościowych ani w publicznych witrynach internetowych, takich jak Twitter, UserVoice, Reddit itd. 

**Wczesna wersja** zawiera listę funkcji udostępnianych w ramach umowy o zachowaniu poufności, które zostaną wprowadzone w przyszłych wydaniach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie publikuj tweetów, wpisów na platformie UserVoice ani w inny sposób nie udostępniaj tych informacji poza swoją firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Funkcja Windows Hello będzie dotyczyć użytkowników i urządzeń <!-- 1106609 -->
Po utworzeniu zasad funkcji [Windows Hello dla firm](windows-hello.md) będą one stosowane do wszystkich użytkowników w organizacji (na poziomie dzierżawy). Dzięki tej aktualizacji zasady można także zastosować do konkretnych użytkowników lub urządzeń przy użyciu zasad konfiguracji urządzeń (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Identity Protection** > **Windows Hello dla firm**).

W witrynie Azure Portal dla usługi Intune konfiguracja i ustawienia są dostępne w ramach pozycji **Rejestrowanie urządzenia** i **Konfiguracja urządzenia**. Pozycja **Rejestrowanie urządzenia** dotyczy całej organizacji (na poziomie dzierżawy) i obsługuje rozwiązanie Windows AutoPilot (OOBE). Pozycja **Konfiguracja urządzenia** dotyczy urządzeń i użytkowników objętych zasadami stosowanymi podczas ewidencjonowania.

Dotyczy:  
- System Windows 10 lub nowszy
- Windows Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Kontrolowanie trybu S na urządzeniach z systemem Windows 10 i nowszymi — publiczna wersja zapoznawcza <!-- 1958649 -->
Będzie można utworzyć profil konfiguracji urządzenia, który wyłącza tryb S urządzenia z systemem Windows 10 lub uniemożliwia użytkownikom wyłączenie trybu S na urządzeniu. Ta funkcja będzie dostępna w ramach pozycji Intune > **Konfiguracja urządzenia** > **Profile** >  **System Windows 10 i nowsze** > **Uaktualnienie wersji i przełączenie trybu**.
Artykuł [Wprowadzenie do systemu Windows 10 w trybie S](https://www.microsoft.com/windows/s-mode) zawiera więcej informacji na temat trybu S.
Dotyczy: Windows 10 i nowsze (1809 i nowsze)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Aktualizacje obsługi nowoczesnych sieci VPN dla systemu iOS <!-- 2459928, 1819876, and 2650856 -->
Przyszła aktualizacja obejmie obsługę następujących klientów sieci VPN dla systemu iOS: 
- F5 Access (w wersji 3.0.1 lub nowszej)
- Citrix SSO
- Palo Alto Networks GlobalProtect (w wersji 5.0 i nowszych) Także w ramach przyszłej aktualizacji:
- Nazwy istniejących typów połączeń **F5 Access** zostaną zmienione na **F5 Access Legacy** (zgodnie ze zmianami znakowania wprowadzonymi przez firmę F5)
- Nazwy istniejących typów połączeń **Palo Alto Networks GlobalProtect** zostaną zmienione na **Legacy Palo Alto Networks GlobalProtect** (zgodnie ze zmianami znakowania wprowadzonymi przez firmę Palo Alto). 

Istniejące profile z tymi typami połączeń będą w dalszym ciągu działać z klientem sieci VPN w starszej wersji. Jeśli używasz programu Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN lub Legacy Palo Alto Networks GlobalProtect with iOS, przejdź na nową aplikację. Należy to zrobić tak szybko, jak to możliwe, aby zapewnić dostęp do sieci VPN dla urządzeń z systemem iOS w miarę ich aktualizowania do systemu iOS 12.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Blokowanie aplikacji Portal firmy w trybie pojedynczej aplikacji do zalogowania użytkownika <!--1067692 --> 
Będzie dostępna możliwość uruchomienia aplikacji Portal firmy w trybie pojedynczej aplikacji, jeśli użytkownik zostanie uwierzytelniony za pomocą aplikacji Portal firmy zamiast za pomocą asystenta ustawień podczas rejestracji w programie DEP. Ta opcja umożliwia zablokowanie urządzenia natychmiast po zakończeniu pracy przez asystenta ustawień, dzięki czemu użytkownik musi zalogować się, aby uzyskać dostęp do urządzenia. Ten proces zapewnia, że dołączanie urządzenia zostanie zakończone i urządzenie nie pozostanie osierocone — bez powiązanego żadnego użytkownika.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>Tagi zakresu dla zasad <!--1081974 eeready-->

Będzie możliwe tworzenie tagów zakresu w celu ograniczenia dostępu do zasobów usługi Intune. Dodaj tag zakresu do przypisania roli, a następnie dodaj tag zakresu do profilu konfiguracji. Rola będzie miała wtedy dostęp tylko do zasobów z profilami konfiguracji ze zgodnymi tagami zakresu (lub bez tagów zakresu).
Aby utworzyć tag zakresu, wybierz pozycję **Role usługi Intune** > **Zakres (tagi)** > **Utwórz**.
Aby dodać tag zakresu do przypisania roli, wybierz pozycję **Role usługi Intune** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > **Zakres (tagi)**.
Aby dodać tag zakresu do profilu konfiguracji, wybierz pozycję **Konfiguracja urządzenia** > **Profile** > wybierz profil > **Właściwości** > **Zakres (tagi)**.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Przypisywanie użytkownika i przyjaznej nazwy do urządzenia rozwiązania AutoPilot <!--1346521 -->
Przyszła publiczna wersja zapoznawcza będzie umożliwiać administratorom przypisanie użytkownika do pojedynczego urządzenia rozwiązania Autopilot.  Administratorzy będą także mogli nadać przyjazne nazwy witające użytkownika podczas konfigurowania urządzenia za pomocą rozwiązania Autopilot.

Dotyczy: Windows Insider 1809 lub nowsza kompilacja (w ramach wersji zapoznawczej).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token VPP firmy Apple używany przez inne rozwiązanie MDM <!-- 1488946 -->
Usługa Intune wykryje i wyświetli szczegółowe informacje, jeśli token programu VPP (Volume Purchase Program) jest używany zarówno przez usługę Intune, jak i inne rozwiązanie MDM.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Obsługa tunelowania pakietów dla profilów sieci VPN aplikacji w systemie iOS dotycząca typów połączenia niestandardowego i Pulse Secure <!-- 1520957 -->
Korzystając z profilów sieci VPN dla aplikacji w systemie iOS, będzie można używać tunelowania w warstwie aplikacji (app-proxy) lub w warstwie pakietów (packet-tunnel). Te opcje będą dostępne dla następujących typów połączeń:
- Niestandardowa sieć VPN
- Pulse Secure Jeśli nie masz pewności, której wartości użyć, zapoznaj się z dokumentacją dostawcy sieci VPN.
Dotyczy: iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Połączenie Zscaler jest dostępne dla profilów sieci VPN w systemie iOS <!-- 1769858 eeready -->
Po utworzeniu profilu konfiguracji urządzenia sieci VPN w systemie iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** platforma > **Sieć VPN** typ profilu) będzie dostępnych kilka typów połączeń, w tym Cisco, Citrix i inne. Przyszła aktualizacja doda typ połączenia Zscaler. 
Pozycja [Ustawienia sieci VPN dla urządzeń z systemem iOS](vpn-settings-ios.md) zawiera dostępne typy połączeń.

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Blokowanie rejestracji osobistych urządzeń z systemem Windows <!-- 1849498 -->
Będzie można zablokować rejestrowanie urządzeń osobistych z systemem Windows za pomocą rozwiązania do [zarządzania urządzeniami mobilnymi](windows-enroll.md) w usłudze Intune. Za pomocą tej funkcji nie można zablokować urządzeń zarejestrowanych przy użyciu [agenta usługi Intune na komputerze](manage-windows-pcs-with-microsoft-intune.md).
Aby wyświetlić tę funkcję, wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia urządzenia**.
Włączenie tego ograniczenia nie ma wpływu na już zarejestrowane urządzenia.
Po włączeniu ograniczenia usługa Intune będzie sprawdzać, czy każde żądanie nowej rejestracji systemu Windows zostało autoryzowane jako rejestracja firmowa. Następujące metody kwalifikują się do autoryzacji jako rejestracja firmowa:
- Rejestrujący użytkownik korzysta z [konta menedżera rejestracji urządzeń]( device-enrollment-manager-enroll.md).
- Urządzenie jest rejestrowane za pomocą rozwiązania [Windows AutoPilot](enrollment-autopilot.md).
- Numer IMEI urządzenia znajduje się w polu **Rejestrowanie urządzenia** > **[Identyfikatory urządzeń firmowych]( corporate-identifiers-add.md)**).
- Urządzenie jest rejestrowane za pomocą [pakietu aprowizacji zbiorczej](windows-bulk-enroll.md).
- Urządzenie jest rejestrowane za pomocą [funkcji automatycznego rejestrowania z programu SCCM dla współzarządzania](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management).

Nieautoryzowane rejestracje będą blokowane. Następujące rejestracje są oznaczone jako firmowe przez usługę Intune, ale ponieważ nie umożliwiają administratorowi usługi Intune kontroli na poziomie urządzenia, będą zablokowane:
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) przez [przyłączenie do usługi Azure Active Directory podczas konfigurowania systemu Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) przez [przyłączenie do usługi Azure Active Directory z instalatora systemu Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).

Następujące metody rejestracji urządzeń osobistych będą także blokowane:
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) za pomocą polecenia [Dodaj konto służbowe w oknie Ustawienia systemu Windows](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).
- Opcja [Tylko rejestracja w rozwiązaniu MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) w oknie Ustawienia systemu Windows.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Określanie wzorców nazw maszyn w profilu rozwiązania AutoPilot <!--1849855-->
Będzie można określić szablon nazw komputerów, aby wygenerować i ustawić [nazwę komputera](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) podczas rejestrowania za pomocą rozwiązania AutoPilot. Należy to określić w profilu rozwiązania AutoPilot znajdującym się w pozycji **Rejestrowanie urządzenia** > **Rejestracja systemu Windows** > **Usługa wdrażania rozwiązania Windows Autopilot** > **Profile**. Są obsługiwane tylko znaki alfanumeryczne i łącznik.
Dotyczy: Windows Insider 1809 lub nowsza kompilacja (w ramach wersji zapoznawczej).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>Numer wersji i numer kompilacji systemu iOS są wyświetlane <!-- 1892471 -->
W polu **Zgodność urządzenia** > **Zgodność urządzenia** jest wyświetlana wersja systemu operacyjnego iOS. W ramach przyszłej aktualizacji będzie także wyświetlany numer kompilacji.
Po wydaniu aktualizacji zabezpieczeń firma Apple zwykle pozostawia numer wersji bez zmian, lecz aktualizuje numer kompilacji. Wyświetlając numer kompilacji, można łatwo sprawdzić, czy aktualizacja luk w zabezpieczeniach została zainstalowana.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>W przypadku profilów rozwiązania Windows AutoPilot można ukryć opcje zmiany konta na stronach logowania firmy i błędu domeny <!--1901669 -->
Publiczna wersja zapoznawcza będzie zawierać nowe opcje profilu rozwiązania Windows AutoPilot przeznaczone dla administratorów i umożliwiające ukrycie opcji zmiany konta na stronach logowania firmy i błędu domeny. Ukrywanie tych opcji wymaga skonfigurowania znakowania firmowego w usłudze Azure Active Directory. Dotyczy: Windows Insider 1809 lub nowsza kompilacja (w wersji zapoznawczej).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Opóźnienie przy wyświetlaniu aktualizacji oprogramowania systemu iOS na urządzeniu <!-- 1949583 -->
Pozycja Intune > **Aktualizacje oprogramowania** > **Zasady aktualizowania systemu iOS** umożliwia skonfigurowanie dni i godzin, podczas których urządzenia nie powinny instalować żadnych aktualizacji. W ramach przyszłej aktualizacji będzie można opóźnić widoczność aktualizacji oprogramowania na urządzeniu o okres od 1 do 90 dni. 
Obszar [Konfigurowanie zasad aktualizacji systemu iOS w usłudze Microsoft Intune](software-updates-ios.md) zawiera bieżące ustawienia.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Wycofane urządzenia na pulpicie nawigacyjnym zgodności urządzeń <!-- 1981119 -->
W ramach przyszłej aktualizacji wycofane urządzenia zostaną usunięte z pulpitu nawigacyjnego zgodności urządzeń. Spowoduje to zmianę liczb dotyczących zgodności.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Aktualizacja nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968 -->
Na podstawie opinii klientów dodajemy nowe funkcje do witryny internetowej Portal firmy. Na urządzeniach z systemami Android, iOS i Windows zobaczysz znaczące ulepszenia istniejących funkcji i poprawę użyteczności. Obszary witryny — takie jak szczegółowe informacje o urządzeniu, opinie i pomoc techniczna oraz przegląd urządzenia — zyskają nowy, nowoczesny i dynamiczny wygląd. Ponadto wprowadziliśmy następujące zmiany:
- Usprawnione przepływy pracy na wszystkich platformach urządzeń
- Ulepszone przepływy identyfikacji i rejestracji urządzeń
- Bardziej pomocne komunikaty o błędach
- Bardziej przyjazny język, mniej technicznego żargonu
- Możliwość udostępniania bezpośrednich linków do aplikacji
- Zwiększona wydajność dużych wykazów aplikacji
- Zwiększona dostępność dla wszystkich użytkowników

### <a name="office-365-proplus-version----2213968-eeready---"></a>Usługa Office 365 ProPlus w wersji <!-- 2213968 eeready -->
Podczas przypisywania aplikacji usługi Office 365 ProPlus do urządzeń z systemem Windows 10 przy użyciu usługi Intune będzie można wybrać wersję pakietu Office. W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje** > **Dodaj aplikację**. Następnie wybierz pozycję **Pakiet Office 365 ProPlus (Windows 10)** z listy rozwijanej **Typ**. Wybierz pozycję **Ustawienia pakietu aplikacji**, aby wyświetlić skojarzony blok. Ustaw wartość pozycji **Aktualizuj kanał**, na przykład **Co miesiąc**. Opcjonalnie usuń inne wersje pakietu Office (pliki msi) z urządzeń użytkowników końcowych, wybierając pozycję **Tak**. Wybierz pozycję **Określona**, aby zainstalować określoną wersję pakietu Office dla wybranego kanału na urządzeniach użytkowników końcowych. Teraz możesz wybrać wartość **Określona wersja** dla pakietu Office. Dostępne wersje będą się zmieniać z upływem czasu. Dlatego podczas tworzenia nowego wdrożenia mogą być dostępne nowsze wersje, a pewne starsze wersje mogą być niedostępne. Bieżące wdrożenia będą nadal wdrażane przy użyciu starszej wersji, lecz lista dla kanału będzie stale aktualizowana. Aby uzyskać więcej informacji, zobacz [Overview of update channels for Office 365 ProPlus (Omówienie kanałów aktualizacji usługi Office 365 ProPlus)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Konfigurowanie profilu pod kątem pominięcia niektórych ekranów asystenta ustawień <!-- 2276470 -->
Podczas tworzenia profilu rejestracji systemu macOS będzie można skonfigurować go tak, aby pominąć dowolny z następujących ekranów, gdy użytkownik będzie korzystać z asystenta ustawień:
- Migracja systemu Android
- Wyświetlanie sygnału
- Ochrona prywatności
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Zmiana w procesie aktualizacji łączników lokalnych <!-- 2277554 -->
Na podstawie opinii klientów zmienimy sposób aktualizacji łączników lokalnych. Po początkowej instalacji łącznika lokalnego aktualizacje będą wykonywane automatycznie. Ta zmiana rozpocznie się od nowego łącznika certyfikatów PFX usługi Microsoft Intune, a następnie będzie wdrażana dla innych typów łączników lokalnych. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Obsługa ustawienia rejestracji DNS dla sieci VPN systemu Windows 10 <!-- 2282852 -->
Będzie można skonfigurować profile sieci VPN systemu Windows 10 tak, aby dynamicznie rejestrowały adresy IP przypisane do interfejsu sieci VPN za pomocą wewnętrznej usługi DNS — bez konieczności korzystania z profilów niestandardowych.
Pole [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md) zawiera aktualnie dostępne ustawienia profilu sieci VPN. 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>Ograniczanie aplikacji i blokowanie dostępu do zasobów firmy z urządzeń z systemem iOS i Android for Work: <!-- 2451462 -->
W polu **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **Android for Work** > **Zabezpieczenia systemu** będzie dostępne nowe ustawienie **Aplikacje z ograniczeniami**. To nowe ustawienie używa zasad zgodności, aby zablokować dostęp do zasobów firmy, jeśli pewne aplikacje są zainstalowane na urządzeniu. Urządzenie jest uznawane za niezgodne, dopóki aplikacje z ograniczeniami nie zostaną usunięte z urządzenia.
Dotyczy: 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>Eksportowanie zasad zgodności z klasycznej witryny Azure Portal do pliku CSV <!-- 2469637 -->
Zasady zgodności utworzone w klasycznej witrynie Azure Portal będą przestarzałe.  Gdy to się stanie, będzie można przeglądać i usuwać dowolne istniejące zasady, ale nie będzie można ich aktualizować. Zasady można wyeksportować w postaci pliku rozdzielanego przecinkami (pliku CSV). Szczegółów w pliku można użyć, aby utworzyć ponownie zasady w witrynie Azure Portal dla usługi Intune.
> [!IMPORTANT]
> Po wycofaniu klasycznej witryny Azure Portal nie będzie dostępu do zasad — nawet w celu ich wyświetlenia. Dlatego należy się upewnić, że zostały wyeksportowane, i utworzyć je ponownie w witrynie Azure Portal przed wycofaniem klasycznej witryny Azure Portal.

### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Zmiana terminologii na „wycofaj” i „wyczyść” <!-- 2175759 -->
Aby zachować spójność z interfejsem API programu Graph, w interfejsie użytkownika usługi Intune i w dokumentacji zmienią się następujące terminy:
- **Usuń dane firmowe** zostanie zmieniony na **wycofaj**
- **Resetowanie do ustawień fabrycznych** zostanie zmieniony na **wyczyść**

### <a name="delete-jamf-devices----2653306---"></a>Usuwanie urządzeń Jamf <!-- 2653306 -->
Urządzenia zarządzane za pomocą oprogramowania JAMF będzie można usuwać, przechodząc do obszaru **Urządzenia**, wybierając urządzenie Jamf i wybierając pozycję **Usuń**.

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Więcej możliwości synchronizacji w aplikacji Portal firmy dla systemu Windows <!-- 2683177 -->
Aplikacja Portal firmy dla systemu Windows dodaje akcję synchronizacji urządzeń do paska zadań systemu Windows i list szybkiego dostępu w menu Start. Kliknięcie tej akcji w dowolnej lokalizacji umożliwia szybkie zsynchronizowanie urządzeń i uzyskanie dostępu do zasobów firmy.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Resetowanie kodów dostępu urządzeń w aplikacji Portal firmy dla systemu Windows 10 <!-- 2101282 --> 
Twoi pracownicy będą wkrótce mogli resetować numer PIN lub kod dostępu dla swoich urządzeń bezpośrednio w aplikacji Portal firmy dla systemu Windows 10. Ta funkcja będzie dostępna na urządzeniach zdalnych i lokalnych zarządzanych przez usługę Intune, które obsługują resetowanie kodu dostępu. W zależności od rodzaju urządzenia żądanie wykonane dla urządzenia zdalnego spowoduje usunięcie bieżącego kodu dostępu urządzenia lub utworzenie tymczasowego kodu dostępu. Użytkownicy, którzy zażądają zresetowania dla urządzenia lokalnego, zostaną przekierowani do aplikacji Ustawienia urządzenia.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nowe środowisko przeglądania w aplikacji Portal firmy dla systemu Windows <!-- 2317227 -->  
Podczas przeglądania w poszukiwaniu aplikacji lub ich wyszukiwania w aplikacji Portal firmy dla systemu Windows możliwe będzie przełączanie się między istniejącym widokiem **Kafelki** a nowo dodanym widokiem **Szczegóły**. W nowym widoku wyświetlane są szczegółowe informacje dotyczące aplikacji, takie jak nazwa, wydawca, data publikacji i stan instalacji.  

Na stronie **Aplikacje** zostanie wprowadzony widok **Zainstalowane**, w którym będą dostępne szczegóły dotyczące zakończonych i trwających instalacji aplikacji. Chcesz udostępnić opinię lub swoje przemyślenia dotyczące nowych zmian? Wyślij nam swoją opinię w aplikacji Portal firmy.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Ulepszone środowisko aplikacji Portal firmy dla użytkowników menedżera rejestracji urządzeń <!-- 675800 -->
Gdy menedżer rejestracji urządzeń loguje się do aplikacji Portal firmy dla systemu Windows, w aplikacji będzie wyświetlane tylko bieżące, uruchomione urządzenie menedżera rejestracji urządzeń. To ulepszenie ograniczy występowanie przekroczeń limitu czasu, które wcześniej miały miejsce, gdy aplikacja podejmowała próbę załadowania wszystkich urządzeń zarejestrowanych w menedżerze rejestracji urządzeń.  

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pakiet konfiguracji zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender jest automatycznie dodawany do profilu konfiguracji <!-- 2144658 -->
Obecnie w przypadku korzystania z [zaawansowanej ochrony przed zagrożeniami i dołączania](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) urządzeń w usłudze Intune pobierasz pakiet konfiguracyjny i dodajesz go do swojego profilu konfiguracji. W ramach przyszłej aktualizacji usługa Intune automatycznie pobierze pakiet z usługi Windows Defender Security Center i doda go do Twojego profilu.

Dotyczy systemu Windows 10 lub nowszych.

### <a name="check-for-sccm-compliance----2192052---"></a>Sprawdzanie zgodności programu SCCM <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (SCCM) (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad**  > **System Windows 10**). Program SCCM wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu SCCM zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie SCCM to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP jest używany token programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Wymagane potwierdzenie w celu usunięcia tokenu programu VPP, który jest używany do wstępnej aprowizacji aplikacji Portal firmy <!-- 2237634 -->
Wymagane będzie potwierdzenie w celu usunięcia tokenu programu Volume Purchase Program (VPP), jeśli jest on używany do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Dodatkowe ustawienia zabezpieczeń dla Instalatora Windows <!-- 2282430 -->
Możliwe będzie zezwolenie użytkownikom na kontrolowanie instalacji aplikacji. Po włączeniu tej funkcji instalacje, które w przeciwnym razie mogły zostać zatrzymane z powodu naruszenia zabezpieczeń, będą kontynuowane. Możliwe będzie przekierowanie Instalatora Windows tak, aby używał podwyższonego poziomu uprawnień podczas instalowania dowolnego programu w systemie. Ponadto możliwe będzie indeksowanie elementów funkcji Windows Information Protection (WIP) oraz przechowywanie związanych z nimi metadanych w niezaszyfrowanej lokalizacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie będą indeksowane i nie będą wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Funkcje tych opcji będą domyślnie wyłączone. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Klawiatury innych firm mogą zostać zablokowane przez ustawienia aplikacji w systemie iOS <!-- 1248481 -->
Na urządzeniach z systemem iOS administratorzy usługi Intune będą mogli zablokować możliwość korzystania z klawiatur innych firm podczas uzyskiwania dostępu do danych organizacji w aplikacjach chronionych przez zasady. Gdy zasady ochrony aplikacji są ustawione na blokowanie klawiatur innych firm, użytkownik urządzenia otrzyma komunikat podczas pierwszej próby interakcji z danymi firmowymi przy użyciu klawiatury innej firmy. Wszystkie opcje inne niż klawiatura macierzysta zostaną zablokowane, a użytkownicy urządzenia nie będą ich widzieć. Użytkownicy urządzenia zobaczą tylko raz komunikat w oknie dialogowym. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Wymaganie niebiometrycznego kodu dostępu podczas uruchamiania aplikacji i po upłynięciu limitu czasu <!-- 1506985 -->

Wymagając niebiometrycznego kodu dostępu podczas uruchamiania aplikacji i po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) poprzez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia będą miały wpływ na użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia te umożliwią administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji** > **Dodaj zasadę** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pakiety językowe usługi Office 365 Pro Plus <!-- 1833450 -->
Jako administrator usługi Intune możesz wdrożyć dodatkowe języki dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje mobilne** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w bloku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w bloku **Ustawienia pakietu aplikacji**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Wersja zapoznawcza nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968 -->
Na podstawie opinii klientów dodajemy nowe funkcje do witryny internetowej Portal firmy/katalogu aplikacji systemu iOS. Na urządzeniach z systemami Android, iOS i Windows zobaczysz znaczące ulepszenia istniejących funkcji i poprawę użyteczności. Obszary witryny — takie jak szczegółowe informacje o urządzeniu, opinie i pomoc techniczna oraz przegląd urządzenia — zyskają nowy, nowoczesny i dynamiczny wygląd. Ponadto wprowadziliśmy następujące zmiany:

- Usprawnione przepływy pracy na wszystkich platformach urządzeń
- Ulepszone przepływy identyfikacji i rejestracji urządzeń
- Bardziej pomocne komunikaty o błędach
- Bardziej przyjazny język, mniej technicznego żargonu
- Możliwość udostępniania bezpośrednich linków do aplikacji
- Zwiększona wydajność dużych wykazów aplikacji
- Zwiększona dostępność dla wszystkich użytkowników

Aktualizacja jest obecnie w wersji zapoznawczej. Możesz zarejestrować się, aby dołączyć do wersji zapoznawczej w http://aka.ms/webcpflighting

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Wymaganie niebiometrycznego kodu dostępu podczas zimnego uruchamiania aplikacji i po upłynięciu limitu czasu <!-- 1506985 --> 

Wymagając niebiometrycznego kodu dostępu podczas zimnego uruchamiania aplikacji i po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) poprzez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia będą miały wpływ na użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia te umożliwią administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji** > **Dodaj zasadę** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Możliwość wdrożenia wymaganych aplikacji biznesowych (LOB) dla wszystkich użytkowników urządzeń z systemem Windows 10 Desktop <!-- 1627835 RS4 -->
Klienci będą mogli wdrażać wymagane aplikacje biznesowe systemu Windows 10 oraz instalować je w kontekstach urządzeń. Umożliwi to udostępnienie tych aplikacji wszystkim użytkownikom urządzenia. Dotyczy to tylko urządzeń z systemem Windows 10 Desktop.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android zostanie zaktualizowane, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy aplikacja Portal firmy dla systemu Android zostanie zaktualizowana, aby podzielić element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



