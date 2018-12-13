---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titlesuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/30/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: ed6a79142c2bbe3bd93b02c17e92f4f11f2583f3
ms.sourcegitcommit: b93db06ba435555f5b126f97890931484372fcfb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2018
ms.locfileid: "52829202"
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również sprawdzić informacje o nadchodzących zmianach, [ważnych powiadomieniach](#notices) oraz [poprzednich wersjach](whats-new-archive.md). Niektóre funkcje mogą być wprowadzane przez kilka tygodni i nie być dostępne dla wszystkich klientów w pierwszym tygodniu.

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

## <a name="week-of-november-26-2018"></a>Tydzień 26 listopada 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Odinstalowywanie aplikacji na nadzorowanych urządzeniach z systemem iOS należących do firmy <!-- 1281677 -->

Można usunąć dowolną aplikację na nadzorowanych urządzeniach z systemem iOS należących do firmy. Dowolną aplikację można usunąć, określając jako cel grupę użytkowników lub urządzeń za pomocą typu przypisania **Odinstaluj**. W przypadku osobistych lub nienadzorowanych urządzeń z systemem iOS będzie można w dalszym ciągu usunąć tylko aplikacje zainstalowane przy użyciu usługi Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Pobieranie zawartości aplikacji usługi Intune Win32 <!-- 2617320 -->
System Windows 10 RS3 i nowsi klienci będą pobierać zawartość aplikacji Win32 w usłudze Intune przy użyciu składnika Optymalizacja dostarczania w obrębie klienta systemu Windows 10. Optymalizacja dostarczania udostępnia funkcję Sieć równorzędna, która jest włączana domyślnie. Optymalizację dostarczania można skonfigurować przy użyciu zasad grupy, a w przyszłości za oprogramowania MDM w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Delivery Optimization for Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) (Optymalizacja dostarczania w systemie Windows 10). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Manu kontekstowe na urządzeniach użytkowników końcowych i w aplikacjach <!-- 2771453 -->
Użytkownicy końcowi mogą teraz korzystać z menu kontekstowego na urządzeniach i aplikacjach w celu wyzwolenia typowych akcji, takich jak zmiana nazwy urządzenia lub sprawdzenie zgodności.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Ustawianie niestandardowego tła w aplikacji Managed Home Screen <!-- 3041945 -->
Dodajemy ustawienie, które umożliwia dostosowanie wyglądu tła aplikacji Managed Home Screen na urządzeniach z rozwiązaniem Android Enterprise pracujących w trybie kiosku z wieloma aplikacjami.  Aby skonfigurować **adres URL niestandardowego tła**, przejdź do usługi Intune za pomocą pozycji Konfiguracja urządzenia w witrynie Azure Portal. Wybierz bieżący profil konfiguracji urządzenia lub utwórz nowy profil, aby edytować ustawienia kiosku.
Aby zapoznać się z ustawieniami kiosku, zobacz temat [Ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Zapisywanie i stosowanie przypisania zasad ochrony aplikacji <!-- 3104570 -->
Będziesz mieć lepszą kontrolę nad [przypisaniami zasad ochrony aplikacji](app-protection-policies.md#deploy-a-policy-to-users). Jeśli wybierzesz pozycję *Przypisania* w celu ustawiania lub edytowania przypisań zasad, musisz najpierw **zapisać** konfigurację, aby zmiana została zastosowana. Użyj pozycji **Odrzuć**, aby wyczyścić wszystkie wprowadzone zmiany bez ich zapisywania na listach uwzględniania lub wykluczania.  Dzięki możliwości wymagania zapisania lub odrzucenia zasady ochrony aplikacji są przypisywane tylko do wybranych przez Ciebie użytkowników.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nowe ustawienia przeglądarki Microsoft Edge dla systemu Windows 10 i nowszych <!-- 3174639 -->
Ta aktualizacja obejmuje nowe ustawienia ułatwiające kontrolowanie przeglądarki Microsoft Edge na urządzeniach i zarządzanie nią. Aby uzyskać listę tych ustawień, zobacz [Ograniczenia urządzeń dla systemu Windows 10 (i nowszych)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Obsługa nowych aplikacji przy użyciu zasad ochrony aplikacji <!-- 3330037 -->
Teraz można zarządzać następującymi aplikacjami za pomocą [zasad ochrony aplikacji usługi Intune](app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Zasady ochrony aplikacji umożliwiają ochronę danych firmowych i kontrolowanie transferu danych dla tych aplikacji, podobnie jak w przypadku innych aplikacji zarządzanych przez zasady usługi Intune. Uwaga: jeśli usługa Flow nie jest jeszcze widoczna w konsoli, należy ją dodać podczas tworzenia lub edytowania zasad ochrony aplikacji. W tym celu należy użyć opcji **+ Więcej aplikacji** i podać *identyfikator aplikacji* dla usługi Flow w polu danych wejściowych. W przypadku systemu Android należy użyć wartości *com.microsoft.flow*, a w przypadku systemu iOS — wartości *com.microsoft.procsimo*.

#### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Aktualizacja interfejsu użytkownika zasad ochrony aplikacji usługi Intune <!-- 3251427 -->
Zmieniliśmy etykiety ustawień i przycisków funkcji ochrony aplikacji usługi Intune, aby ułatwić ich zrozumienie. Oto niektóre zmiany:  

- Kontrolki **tak** / **nie** zostały zmienione głównie na kontrolki **blokuj** / **zezwalaj ** oraz **wyłącz** / **włącz**. Etykiety również zostały aktualizowane.  
- Format ustawień został zmieniony, dzięki czemu ustawienie i jego etykieta znajdują się obok siebie w kontrolce, umożliwiając lepszą nawigację.   

Ustawienia domyślne i liczba ustawień pozostają takie same, lecz ta zmiana pozwala użytkownikowi lepiej zrozumieć i wykorzystać ustawienia w celu stosowania wybranych zasad ochrony aplikacji, a także łatwiej nawigować po nich.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>Są wyświetlane numery wersji i numery kompilacji systemów iOS i macOS <!-- 1892471 -->
W polu **Zgodność urządzenia** > **Zgodność urządzenia** są wyświetlane wersje systemów operacyjnych iOS oraz macOS i można ich używać w zasadach zgodności. Ta aktualizacja uwzględnia numer kompilacji, który można konfigurować na obydwu platformach.
Po wydaniu aktualizacji zabezpieczeń firma Apple zwykle pozostawia numer wersji bez zmian, lecz aktualizuje numer kompilacji. Na podstawie numeru kompilacji w zasadach zgodności można łatwo sprawdzić, czy została zainstalowana aktualizacja eliminująca luki w zabezpieczeniach.
Aby korzystać z tej funkcji, zapoznaj się z zasadami zgodności dla systemów [iOS](compliance-policy-create-ios.md#device-health) i [macOS](compliance-policy-create-mac-os.md#device-properties).

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Pierścienie aktualizacji są zastępowane ustawieniami optymalizacji dostarczania dla systemu Windows 10 i nowszych wersji <!-- 2753807 -->
Optymalizacja dostarczania to nowy profil konfiguracji dla systemu Windows 10 i nowszych wersji. Ta funkcja oferuje bardziej usprawnione środowisko dostarczania aktualizacji oprogramowania do urządzeń w organizacji. Ta aktualizacja pomaga też dostarczać ustawienia w nowych i istniejących pierścieniach aktualizacji przy użyciu profilu konfiguracji.
Aby skonfigurować profil konfiguracji optymalizacji dostarczania, zobacz [Windows 10 (and newer) delivery optimization settings](delivery-optimization-windows.md) (Ustawienia optymalizacji w systemie Windows 10 (i nowszych)).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Wybieranie śledzonych aplikacji na stronie stanu rejestracji <!-- 2531007 -->
Można wybrać śledzone aplikacje na stronie stanu rejestracji. Do momentu zainstalowania tych aplikacji użytkownik nie może korzystać z urządzenia. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Wyszukiwanie urządzenia rozwiązania Autopilot według numeru seryjnego <!--2595788 -->
Teraz można wyszukiwać urządzenia rozwiązania Autopilot według numeru seryjnego. W tym celu należy wybrać pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia** > wpisz numer seryjny w polu **Wyszukiwanie według numeru seryjnego** > naciśnij klawisz Enter.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Śledzenie instalacji pakietu Office ProPlus <!--2620217 -->
Użytkownicy mogą śledzić postęp instalacji pakietu [Office ProPlus](apps-add-office365.md) przy użyciu [strony stanu rejestracji](windows-enrollment-status.md). Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP używasz tokenu programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Obsługa programu Device Enrollment Program dla systemu macOS w przypadku kont usługi Apple School Manager <!--3006133 -->
Usługa Intune obsługuje teraz program Device Enrollment Program dla urządzeń z systemem macOS w przypadku kont usługi Apple School Manager.  Aby uzyskać więcej informacji, zobacz [Automatically enroll macOS devices with Apple School Manager or Device Enrollment Program](device-enrollment-program-enroll-macos.md) (Automatyczne rejestrowanie urządzeń z systemem macOS w ramach usługi Apple School Manager lub programu Device Enrollment Program).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Nowa wersja SKU <!--3312071--> subskrypcji usługi Intune dla urządzeń
W celu ułatwienia obniżania kosztów zarządzania urządzeniami w przedsiębiorstwach udostępniono nową wersję SKU subskrypcji opartej na urządzeniach. Ta wersja SKU subskrypcji usługi Intune dla urządzeń jest licencjonowana na urządzenie i jest subskrypcją miesięczną. Cena zależy od programu licencjonowania. Jest dostępna w kanałach sprzedaży Direct Channel, Enterprise Agreement (EA), Microsoft Products and Services Program (MPSA) oraz Open i Cloud Solution Provider (CSP).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Tymczasowe wstrzymanie trybu kiosku na urządzeniach z systemem Android w celu wprowadzenia zmian <!-- 3041935 -->
W przypadku urządzeń z systemem Android pracujących w trybie kiosku z wieloma aplikacjami administrator IT może potrzebować wprowadzić zmiany na urządzeniu. Ta aktualizacja obejmuje nowe ustawienia dla kiosku z wieloma aplikacjami, które pozwalają administratorowi IT na tymczasowe wstrzymanie trybu kiosku za pomocą numeru PIN i uzyskanie dostępu do całego urządzenia.
Aby zapoznać się z ustawieniami kiosku, zobacz temat [Ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Dostępność wirtualnego przycisku strony głównej na urządzeniach z rozwiązaniem Android Enterprise pracujących w trybie kiosku <!-- 3042021 -->
Nowe ustawienie umożliwi użytkownikom przełączanie się między aplikacją Managed Home Screen a innymi przypisanymi aplikacjami na urządzeniu kiosku z wieloma aplikacjami przez naciśnięcie przycisku programowego. To ustawienie jest szczególnie przydatne w sytuacjach, gdy aplikacja kiosku nie reaguje odpowiednio na przycisk „wstecz”. To ustawienie będzie można skonfigurować dla pojedynczych urządzeń z systemem Android należących do firmy. Aby włączyć lub wyłączyć **wirtualny przycisk strony głównej**, przejdź do usługi Intune za pomocą pozycji Konfiguracja urządzenia w witrynie Azure Portal. Wybierz bieżący profil konfiguracji urządzenia lub utwórz nowy profil, aby edytować ustawienia kiosku.
Aby zapoznać się z ustawieniami kiosku, zobacz temat [Ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

## <a name="week-of-november-12-2018"></a>Tydzień 12 listopada 2018 r.

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Obsługa kontroli dostępu do sieci (NAC) dla aplikacji Citrix SSO w systemie iOS <!-- 3259404 -->

Firma Citrix opublikowała aktualizację aplikacji Citrix Gateway, aby umożliwić kontrolę dostępu do sieci w aplikacji Citrix dla systemu iOS w usłudze Intune. Można wyrazić zgodę na uwzględnienie identyfikatora urządzenia w profilu sieci VPN w usłudze Intune, a następnie wypchnąć ten profil do urządzeń z systemem iOS. Aby używać tej funkcji, trzeba będzie zainstalować najnowszą aktualizację aplikacji Citrix Gateway.

Temat [Konfigurowanie ustawień sieci VPN na urządzeniach z systemem iOS](vpn-settings-ios.md#base-vpn-settings) zawiera dalsze informacje na temat używania kontroli dostępu do sieci, w tym opis niektórych dodatkowych wymagań. 

## <a name="week-of-november-5-2018"></a>Tydzień 5 listopada 2018 r.

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Obsługa uwierzytelniania OAuth z systemu iOS 12 w profilach poczty e-mail systemu iOS <!--2155106 -->

Profile poczty e-mail systemu iOS w usłudze Intune obsługują uwierzytelnianie OAuth (Open Authorization) z systemu iOS 12. Aby wyświetlić tę funkcję, utwórz nowy profil (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **E-mail** dla typu profilu) lub zaktualizuj istniejący profil poczty e-mail systemu iOS. Po włączeniu uwierzytelniania OAuth w profilu, który jest już wdrożony u użytkowników, użytkownicy ci są monitowani o ponowne uwierzytelnienie, a następnie o ponowne pobranie poczty e-mail.

Więcej informacji na temat korzystania z protokołu OAuth w profilu poczty e-mail podano w [artykule poświęconym profilom poczty e-mail systemu iOS](email-settings-ios.md).

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Obsługa rozwiązania Autopilot w przypadku urządzeń przyłączonych hybrydowo do usługi Azure Active Directory (wersja zapoznawcza) <!-- 1048100-->
Za pomocą rozwiązania Autopilot możesz teraz skonfigurować urządzenia przyłączone hybrydowo do usługi Azure Active Directory. Aby używać hybrydowego rozwiązania Autopilot, urządzenia muszą być przyłączone do sieci w organizacji. Aby uzyskać więcej informacji, zobacz [Wdrażanie hybrydowych urządzeń przyłączonych do usługi Active Directory przy użyciu usługi Intune i programu Windows Autopilot](windows-autopilot-hybrid.md).
Ta funkcja będzie stopniowo wprowadzana dla użytkowników w ciągu kilku następnych dni. W związku z tym wykonanie tych kroków może nie być możliwe do momentu wdrożenia jej na Twoim koncie.

## <a name="week-of-october-29-2018"></a>Tydzień 29 października 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Niebiometryczny numer PIN jest wymagany po upłynięciu określonego limitu czasu <!-- 1506985 -->
Wymagając niebiometrycznego numeru PIN po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) przez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia dotyczą użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia umożliwiają administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji** > **Dodaj zasady** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień. Aby uzyskać informacje dotyczące ustawień dostępu, zobacz [Ustawienia systemu iOS](app-protection-policy-settings-ios.md#access-settings) i [Ustawienia systemu Android](app-protection-policy-settings-android.md#access-settings).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Ustawienia transferu danych aplikacji usługi Intune w urządzeniach z systemem iOS zarejestrowanych w oprogramowaniu MDM <!-- 2244713 -->
Możesz oddzielić kontrolę ustawień transferu danych aplikacji usługi Intune na urządzeniach z systemem iOS zarejestrowanych w rozwiązaniu MDM od określania tożsamości zarejestrowanego użytkownika nazywanej także główną nazwa użytkownika (UPN). Administratorzy nieużywający narzędzia IntuneMAMUPN nie zaobserwują zmiany zachowania. Jeśli ta funkcja jest dostępna, administratorzy używający narzędzia IntuneMAMUPN do kontrolowania zachowania transferu danych na zarejestrowanych urządzeniach powinni przejrzeć nowe ustawienia i odpowiednio zaktualizować ustawienia aplikacji.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplikacje Win32 systemu Windows 10 <!-- 2617325 -->
Aplikacje Win32 można skonfigurować pod kątem instalowania w kontekście poszczególnych użytkowników w przeciwieństwie do instalowania aplikacji dla wszystkich użytkowników urządzenia.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplikacje Win32 systemu Windows i skrypty programu PowerShell <!-- 2617330 -->
Użytkownicy końcowi nie muszą już być zalogowani na urządzeniu, aby instalować aplikacje Win32 lub wykonywać skrypty programu PowerShell. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Rozwiązywanie problemów z instalacją aplikacji klienckiej <!-- 1363711 -->
Rozwiązywanie problemów z instalacją aplikacji klienckich można rozpocząć od zapoznania się z kolumną **Instalacja aplikacji** w bloku **Rozwiązywanie problemów**. Aby wyświetlić blok **Rozwiązywanie problemów**, w portalu usługi Intune wybierz pozycję **Rozwiązywanie problemów** w obszarze **Pomoc i obsługa techniczna**.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Obsługa kontroli dostępu do sieci na klientach sieci VPN z systemem iOS <!-- 1333693 -->
W tej aktualizacji udostępniono nowe ustawienie umożliwiające włączenie kontroli dostępu do sieci (NAC) po utworzeniu profilu konfiguracji sieci VPN dla oprogramowania Cisco AnyConnect, F5 Access i Citrix SSO for iOS. To ustawienie umożliwia dołączenie identyfikatora NAC urządzenia do profilu sieci VPN. Obecnie nie ma żadnych klientów sieci VPN ani rozwiązań partnerskich NAC obsługujących ten nowy identyfikator NAC, lecz gdy takie pojawią się, poinformujemy Cię za pośrednictwem [wpisów w naszym blogu obsługi technicznej](ttps://aka.ms/iOS12_and_vpn).

Aby korzystać z kontroli dostępu do sieci, należy:
1. Udzielić zgody, aby umożliwić usłudze Intune dołączanie identyfikatorów urządzeń do profilów sieci VPN
2. Zaktualizować oprogramowanie dostawcy NAC lub oprogramowanie układowe, korzystając ze wskazówek udostępnionych bezpośrednio przez dostawcę NAC

Aby uzyskać informacje na temat tego ustawienia dla profilu sieci VPN systemu iOS, zobacz [Dodawanie ustawień sieci VPN na urządzeniach z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md). Aby uzyskać więcej informacji na temat kontroli dostępu do sieci, zobacz [Integracja kontroli dostępu do sieci z usługą Intune](network-access-control-integrate.md). 

Dotyczy: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Usuwanie profilu poczty e-mail z urządzenia, nawet wtedy, gdy istnieje tylko jeden profil poczty e-mail <!-- 1818139 -->
Wcześniej nie można było usunąć profilu poczty e-mail z urządzenia, *jeśli* był to jedyny profil poczty e-mail. Dzięki tej aktualizacji to zachowanie zmieniło się. Teraz można usunąć profil poczty e-mail, nawet jeśli jest to jedyny profil poczty e-mail w urządzeniu. Zobacz [Add email settings to devices using Intune (Dodawanie ustawień poczty e-mail do urządzeń przy użyciu usługi Intune)](email-settings-configure.md), aby uzyskać szczegółowe informacje.

#### <a name="powershell-scripts-and-aad----2309469---"></a>Skrypty programu PowerShell i usługa AAD <!-- 2309469 -->
Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń urządzeń usługi AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nowe ustawienie domyślne „Wymagany typ hasła” dla systemów Android, Android Enterprise<!-- 2649963 -->
Podczas tworzenia nowych zasad zgodności (**Intune** > **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **Android** lub **Android enterprise** dla platformy > Zabezpieczenia systemu) wartość domyślna dla ustawienia **Wymagany typ hasła** ulega zmianie:

Z: Ustawienie domyślne urządzenia Na: Co najmniej numeryczne

Dotyczy: Android, Android Enterprise

Aby wyświetlić te ustawienia, przejdź do pozycji [Android](compliance-policy-create-android.md) i [Android Enterprise](compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Używanie klucza wstępnego w profilu sieci Wi-Fi systemu Windows 10 <!-- 2662938 -->
Dzięki tej aktualizacji będziesz mieć możliwość użycia klucza wstępnego (PSK) z protokołem zabezpieczeń WPA/WPA2-Personal do uwierzytelniania profilu konfiguracji sieci Wi-Fi dla systemu Windows 10. Będzie także możliwe określenie konfiguracji kosztów dla sieci taryfowej na potrzeby urządzeń z systemem Windows 10 z aktualizacją z października 2018 r.

Obecnie trzeba zaimportować profil sieci Wi-Fi lub utworzyć profil niestandardowy, aby korzystać z klucza wstępnego. Obszar [Ustawienia sieci Wi-Fi dla systemu Windows 10](wi-fi-settings-windows.md) zawiera listę bieżących ustawień. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Usuwanie certyfikatów PKCS i SCEP z urządzeń <!-- 3218390 -->
W niektórych scenariuszach certyfikaty PKCS i SCEP pozostawały w urządzeniach nawet po usunięciu zasad z grupy, usunięciu wdrożenia konfiguracji lub zgodności albo zaktualizowania istniejącego profilu certyfikatu SCEP lub PKCS. Ta aktualizacja zmienia to zachowanie. W pewnych scenariuszach certyfikaty PKCS i SCEP są usuwane z urządzeń, a w innych — pozostają w urządzeniu. Opis tych scenariuszy można znaleźć w temacie [Usuwanie certyfikatów SCEP i PKCS w usłudze Microsoft Intune](remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Użycie programu Gatekeeper na urządzeniach z systemem macOS na potrzeby zachowania zgodności <!-- 2504381 -->
Ta aktualizacja obejmuje program Gatekeeper dla systemu macOS umożliwiający ocenę urządzenia pod kątem zgodności. Aby ustawić właściwość programu Gatekeeper, zobacz [Dodawanie zasad zgodności dla urządzeń z systemem macOS](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="enrollment-abandonment-report----1382924---"></a>Raport porzucań rejestracji <!-- 1382924 -->
Nowy raport zawierający szczegółowe informacje dotyczące porzuconych rejestracji jest dostępny w obszarze **Rejestrowanie urządzeń** > **Monitorowanie**. Aby uzyskać więcej informacji, zobacz [Raport porzucania portalu firmy](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nowa funkcja warunków użytkowania usługi Azure Active Directory <!-- 2870393 -->
Usługa Azure Active Directory udostępnia funkcję warunków użytkowania, której można użyć zamiast istniejących warunków i postanowień usługi Intune. Funkcja warunków użytkowania usługi Azure AD zapewnia większą elastyczność w związku z tym, które warunki wyświetlić i kiedy, lepszą obsługę lokalizacji, większą kontrolę sposobu renderowania i ulepszone raportowanie. Funkcja warunków użytkowania usługi Azure AD wymaga usługi Azure Active Directory Premium P1, która jest również częścią pakietu Enterprise Mobility + Security E3. Aby dowiedzieć się więcej, zobacz artykuł [Zarządzanie warunkami i postanowieniami obowiązującymi w firmie na potrzeby dostępu użytkowników](terms-and-conditions-create.md).

### <a name="android-device-owner-mode-support---3188762--"></a>Obsługa trybu Właściciel urządzenia z systemem Android <!--3188762-->
W przypadku rejestracji w rozwiązaniu Samsung Knox Mobile Enrollment usługa Intune obsługuje teraz rejestrowanie urządzeń w trybie zarządzania Właściciel urządzenia z systemem Android. Użytkownicy korzystający z sieci komórkowej lub Wi-Fi mogą za pomocą kilku naciśnięć zarejestrować urządzenie przy jego pierwszym włączeniu. Aby uzyskać więcej informacji, zobacz temat [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md) (Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung).

### <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Grupowanie urządzeń zarejestrowanych w programie Windows Autopilot według identyfikatora korelatora <!-- 2075110 -->
Usługa Intune teraz obsługuje grupowanie urządzeń z systemem Windows według identyfikatora korelatora, jeśli urządzenia są zarejestrowane przy użyciu [rozwiązania Autopilot dla istniejących urządzeń](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) za pośrednictwem programu Configuration Manager. Identyfikator korelatora jest parametrem pliku konfiguracji rozwiązania Autopilot. Usługa Intune automatycznie ustawi [atrybut enrollmentProfileName urządzenia w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) na wartość „OfflineAutopilotprofile-<correlator ID>”. Dzięki temu można utworzyć dowolne grupy dynamiczne usługi Azure AD na podstawie identyfikatora korelatora za pomocą atrybutu enrollmentprofileName dla rejestracji rozwiązania Autopilot w trybie offline. Aby uzyskać więcej informacji, zobacz [Rozwiązanie Windows Autopilot dla istniejących urządzeń](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

### <a name="intune-app-protection-policies----2984657---"></a>Zasady ochrony aplikacji usługi Intune <!-- 2984657 -->
Zasady ochrony aplikacji usługi Intune pozwalają skonfigurować różne ustawienia ochrony danych dla chronionych aplikacji usługi Intune, takich jak Outlook i Word. Zmieniliśmy wygląd i działanie tych ustawień dla systemów [iOS](app-protection-policy-settings-ios.md) i [Android](app-protection-policy-settings-android.md), aby umożliwić łatwiejsze znalezienie poszczególnych ustawień. Istnieją trzy kategorie ustawień zasad:
- **Relokacja danych** — ta grupa obejmuje kontrolki ochrony przed utratą danych ograniczające działania takie jak wycinanie, kopiowanie, wklejanie i zapisywanie pod nową nazwą. Te ustawienia określają, jak użytkownicy używają danych w aplikacjach.
- **Wymagania dotyczące dostępu** — ta grupa zawiera opcje numeru PIN dla poszczególnych aplikacji, które określają, w jaki sposób użytkownik uzyskuje dostęp do aplikacji w kontekście służbowym.  
- **Uruchamianie warunkowe** — ta grupa zawiera ustawienia takie jak minimalna wersja systemu operacyjnego, wykrywanie urządzeń ze zdjętymi zabezpieczeniami systemu i z dostępem do konta root oraz okresy prolongaty trybu offline.  
  
Działanie ustawień nie ulega zmianie, ale będzie można je łatwiej znaleźć podczas pracy z przepływem tworzenia zasad.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Usługa Intune będzie obsługiwać pakiety o maksymalnym rozmiarze 8 GB w przypadku aplikacji biznesowych <!-- 1727158 -->
Usługa Intune zwiększyła maksymalny rozmiar pakietu do 8 GB dla aplikacji biznesowych. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Dodawanie obrazu niestandardowego marki dla aplikacji Portal firmy <!-- 1916266 -->
Jako administrator usługi Microsoft Intune masz możliwość przekazania obrazu niestandardowego marki, który będzie wyświetlany jako obraz tła na stronie profilu użytkownika w aplikacji Portal firmy dla systemu iOS. Aby uzyskać więcej informacji na temat konfigurowania aplikacji Portal firmy, zobacz artykuł [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Zachowanie lokalnego języka pakietu Office przez usługę Intune podczas aktualizowania pakietu Office na komputerach użytkowników końcowych <!-- 2971030 -->
Podczas instalowania pakietu Office na komputerach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, z których korzystali w przypadku poprzednich instalacji pakietu Office opartych na instalatorze MSI. Aby uzyskać więcej informacji, zobacz [Jak przypisać aplikacje usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nowe środowisko pomocy technicznej usługi Intune w portalu zarządzania urządzeniami na platformie Microsoft 365 <!-- 3076965 -->
Wprowadzamy nowe środowisko Pomoc i obsługa techniczna dla usługi Intune w [portalu zarządzania urządzeniami na platformie Microsoft 365]( http://devicemanagement.microsoft.com). Nowe środowisko pozwala opisać problem własnymi słowami i uzyskać szczegóły dotyczące rozwiązywania problemu oraz zawartość internetową dotyczącą korygowania. Te rozwiązania są oferowane za pośrednictwem algorytmu uczenia maszynowego opartego na regułach i sterowanego przez zapytania użytkownika.  

Oprócz korzystania ze wskazówek specyficznych dla problemu można także użyć nowego przepływu pracy tworzenia sprawy do otwarcia zgłoszenia do pomocy technicznej za pomocą poczty e-mail lub telefonu.  

Dla klientów objętych wdrożeniem to nowe środowisko zastępuje bieżące środowisko Pomoc i obsługa techniczna w postaci statycznego zestawu wstępnie wybranych opcji określonych na podstawie obszaru konsoli aktywnego podczas otwierania środowiska Pomoc i obsługa techniczna.  

*Nowe środowisko Pomoc i obsługa techniczna jest wdrażane dla niektórych, lecz nie wszystkich, dzierżaw i jest dostępne w portalu Zarządzanie urządzeniami. Użytkownicy nowego środowiska zostali wybrani losowo z dostępnych dzierżaw usługi Intune. Nowe dzierżawy będą dodawane w miarę postępów wdrażania.*  

Aby uzyskać więcej informacji, zobacz [Nowe środowisko Pomoc i obsługa techniczna](get-support.md#new-help-and-support-experience) na stronie Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Moduł programu PowerShell dla usługi Intune w wersji zapoznawczej dostępny<!-- 951068 -->
Nowy moduł programu PowerShell, który zapewnia obsługę interfejsu API usługi Intune za pośrednictwem programu Microsoft Graph, jest teraz dostępny w wersji zapoznawczej w serwisie [GitHub]( https://aka.ms/intunepowershell). Aby uzyskać szczegółowe informacje na temat korzystania z tego modułu, zobacz plik README w tej lokalizacji. 


## <a name="week-of-october-15-2018"></a>Tydzień 15 października 2018 r.

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Monit o podanie numeru PIN podczas zmieniania odcisków palców lub twarzy w funkcji Face ID na urządzeniu z systemem iOS  <!-- 2637704  -->
Użytkownicy są teraz monitowani o podanie numeru PIN po wprowadzeniu zmian biometrycznych na urządzeniu z systemem iOS. Obejmuje to zmiany zarejestrowanych odcisków palców lub twarzy w funkcji Face ID. Chronometraż monitu zależy od konfiguracji limitu czasu *Ponownie sprawdź wymagania dostępu po (minuty)*.  Jeśli numer PIN nie jest ustawiony, użytkownik jest monitowany o ustawienie go. 
 
Ta funkcja jest dostępna tylko dla systemów iOS i wymaga udziału aplikacji, w których zintegrowany jest zestaw SDK zasad ochrony aplikacji usługi Intune dla systemu iOS w wersji 9.0.1 lub nowszej. Integracja zestawu SDK jest konieczna, aby można było wymusić to zachowanie w aplikacjach docelowych. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. Dotyczy to między innymi aplikacji WXP, Outlook, Managed Browser i Yammer.


## <a name="week-of-october-1-2018"></a>Tydzień 1 października 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Dostęp do kluczowych właściwości profilu za pomocą aplikacji Portal firmy <!-- 772203 -->
Użytkownicy końcowi mogą teraz uzyskiwać dostęp do kluczowych właściwości konta i akcji takich jak resetowanie hasła z aplikacji Portal firmy. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Klawiatury innych firm mogą zostać zablokowane przez ustawienia aplikacji w systemie iOS <!-- 1248481 -->
Na urządzeniach z systemem iOS administratorzy usługi Intune mogą zablokować możliwość korzystania z klawiatur innych firm podczas uzyskiwania dostępu do danych organizacji w aplikacjach chronionych przez zasady. Gdy zasady ochrony aplikacji (APP) są ustawione na blokowanie klawiatur innych firm, użytkownik urządzenia otrzymuje komunikat podczas pierwszej próby interakcji z danymi firmowymi przy użyciu klawiatury innej firmy. Wszystkie opcje inne niż klawiatura macierzysta są zablokowane, a użytkownicy urządzenia nie będą ich widzieć. Użytkownicy urządzenia zobaczą tylko raz komunikat w oknie dialogowym. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Dostęp do konta użytkownika w przypadku aplikacji usługi Intune na zarządzanych urządzeniach z systemami Android i iOS <!-- 1248496 -->
Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Zasady konfiguracji aplikacji Outlook dla systemów iOS i Android <!--1828527 -->
Można teraz utworzyć zasady konfiguracji aplikacji Outlook dla systemów iOS i Android przeznaczone dla użytkowników lokalnych, którzy korzystają z uwierzytelniania podstawowego przy użyciu protokołu ActiveSync. Dodatkowe ustawienia konfiguracji będą dodawane w miarę ich włączania w aplikacji Outlook dla systemów iOS i Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pakiety językowe usługi Office 365 Pro Plus <!-- 1833450 -->
Jako administrator usługi Intune możesz wdrożyć dodatkowe języki dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w bloku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w bloku **Ustawienia pakietu aplikacji**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Rozszerzenia plików aplikacji biznesowych (LOB) dla systemu Windows <!-- 1884873 -->
Rozszerzenia plików aplikacji LOB dla systemu Windows obejmują teraz rozszerzenia *msi*, *appx*, *appxbundle*, *msix* i *msixbundle*. Aby dodać aplikację w usłudze Microsoft Intune, wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Zostanie wyświetlone okienko **Dodaj aplikację**, w którym możesz wybrać **Typ aplikacji**. Dla aplikacji LOB dla systemu Windows wybierz aplikację **Biznesowa** jako typ aplikacji, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny z odpowiednim rozszerzeniem.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Wdrażanie aplikacji systemu Windows 10 przy użyciu usługi Intune <!-- 2309001 -->
Korzystając z istniejącej obsługi aplikacji biznesowych i aplikacji z portalu Microsoft Store dla Firm, administratorzy mogą użyć usługi Intune do wdrożenia większości aplikacji używanych w organizacji dla użytkowników końcowych na urządzeniach z systemem Windows 10. Administratorzy mogą dodawać, instalować i deinstalować aplikacje dla użytkowników systemu Windows 10 w różnych formatach, takich jak MSI, Setup.exe lub MSP. Usługa Intune oceni reguły wymagań przed pobraniem i zainstalowaniem, powiadamiając użytkowników końcowych o stanie wymagań dotyczących ponownego uruchomienia za pomocą Centrum akcji systemu Windows 10. Ta funkcja skutecznie umożliwia zainteresowanym organizacjom przeniesienie obciążenia do usługi Intune i chmury. Jest ona obecnie dostępna w publicznej wersji zapoznawczej i planujemy dodanie do niej znaczących nowych możliwości w ciągu kilku następnych miesięcy. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Manu kontekstowe na urządzeniach użytkowników końcowych i w aplikacjach <!-- 2771453 -->
Użytkownicy końcowi mogą teraz korzystać z menu kontekstowego na urządzeniach i aplikacjach w celu wyzwolenia typowych akcji, takich jak zmiana nazwy urządzenia lub sprawdzenie zgodności. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Skróty klawiaturowe w aplikacji Portal firmy dla systemu Windows <!-- 2771518 -->
Użytkownicy końcowi będą teraz mogli wyzwalać akcje aplikacji i urządzeń w aplikacji Portal firmy dla systemu Windows za pomocą skrótów klawiaturowych (akceleratorów).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Tworzenie sufiksów DNS w profilach konfiguracji sieci VPN na urządzeniach z systemem Windows 10<!-- 1333668 -->
Podczas tworzenia profilu konfiguracji urządzenia sieci VPN (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** (platforma) > **VPN** (typ profilu)) wprowadzasz pewne ustawienia systemu DNS. Dzięki tej aktualizacji można również podać wiele **sufiksów DNS** w usłudze Intune. Korzystając z sufiksów DNS, możesz wyszukać zasób sieciowy za pomocą jego krótkiej nazwy, zamiast w pełni kwalifikowanej nazwy domeny (FQDN). Ta aktualizacja umożliwia również zmianę kolejności sufiksów DNS w usłudze Intune.
Pole [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md#dns-settings) zawiera aktualnie ustawienia systemu DNS.
Dotyczy urządzeń z systemem Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Obsługa zawsze włączonej sieci VPN dla profilów roboczych systemu Android dla firm <!-- 1333705 -->
Dzięki tej aktualizacji będziesz mieć możliwość używania zawsze włączonych połączeń sieci VPN na urządzeniach z systemem Android dla firm dzięki zarządzanym profilom służbowym. Zawsze włączone połączenia sieci VPN pozostają aktywne lub są natychmiast przywracane, gdy użytkownik odblokuje urządzenie, gdy urządzenie uruchomi się ponownie lub gdy zmieni się sieć bezprzewodowa. Połączenie można również przenieść do trybu „blokady”, który powoduje zablokowanie całego ruchu sieciowego do momentu uaktywnienia połączenia sieci VPN.
Zawsze włączoną sieć VPN możesz włączyć za pomocą ustawień **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Android dla firm** platforma > **Ograniczenia dotyczące urządzeń** > **Łączność**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Wystawianie certyfikatów protokołu SCEP dla urządzeń bez użytkowników <!-- 1744554 -->
Obecnie certyfikaty są wystawiane dla użytkowników. Dzięki tej aktualizacji certyfikaty protokołu SCEP można wystawiać dla urządzeń, w tym urządzeń bez użytkowników, takich jak kioski (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** platforma > **Certyfikat SCEP** dla profilu). Inne aktualizacje obejmują:
- Właściwość **Podmiot** w profilu SCEP jest teraz niestandardowym polem tekstowym i może zawierać nowe zmienne. 
- Właściwość **Alternatywna nazwa podmiotu (SAN)** w profilu SCEP ma teraz format tabeli i może zawierać nowe zmienne. W tabeli administrator może dodać atrybut i wypełnić wartość w niestandardowym polu tekstowym. Nazwa SAN będzie obsługiwać następujące atrybuty: 
  - systemem DNS,
  - Adres e-mail
  - UPN

  Te nowe zmienne można dodawać z tekstem statycznym w polu tekstowym wartości niestandardowej. Na przykład atrybut systemu DNS można dodać jako `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Nawiasy klamrowe, średniki i symbole potoku „{}; |” nie będą działać w tekście statycznym nazwy SAN. W nawiasy klamrowe należy ująć tylko jedną z nowych zmiennych certyfikatu urządzenia do zaakceptowania: `Subject` lub `Subject alternative name`. 

Nowe zmienne certyfikatu urządzenia:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - Zmienna `{{FullyQualifiedDomainName}}` działa tylko w przypadku urządzeń z systemem Windows i urządzeń przyłączonych do domeny. 
>  -  Podczas określania właściwości urządzenia, takich jak numer IMEI, numer seryjny i w pełni kwalifikowana nazwa domeny w obrębie podmiotu lub nazwy SAN dla certyfikatu urządzenia, należy pamiętać, że te właściwości mogą zostać sfałszowane przez osobę z dostępem do urządzenia. 

Podczas tworzenia profilu konfiguracji protokołu w obszarze [Tworzenie profilu certyfikatu protokołu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) będą znajdować się bieżące zmienne. 

Dotyczy: system Windows 10 i nowsze oraz system iOS, obsługiwane w sieci Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Zdalne blokowanie niezgodnych urządzeń <!-- 2064495 -->
Gdy urządzenie jest niezgodne, możesz utworzyć akcję dotyczącą zasad zgodności, która zdalnie zablokuje urządzenie. W obszarze Intune > **Zgodność urządzenia** utwórz nowe zasady lub wybierz istniejące zasady, a następnie wybierz pozycję **Właściwości**. Wybierz kolejno pozycje **Akcje dotyczące niezgodności** > **Dodaj** i wybierz opcję zdalnego blokowania urządzenia.
Obsługiwane na: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- System Windows Phone 8.1 lub nowszy 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>System Windows 10 i nowsze Ulepszenia profilu kiosku w witrynie Azure Portal <!-- 2748224 -->
Ta aktualizacja obejmuje następujące ulepszenia profilu konfiguracji urządzenia kiosku z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** platforma > **Kiosk (wersja zapoznawcza)** dla typu profilu): 
- Obecnie w jednym urządzeniu można utworzyć wiele profilów kiosku. Dzięki tej aktualizacji usługa Intune będzie obsługiwać tylko jeden profil kiosku na urządzenie. Jeśli nadal potrzebujesz wielu profilów kiosku w jednym urządzeniu, możesz użyć niestandardowego identyfikatora URI.
- W profilu **Kiosk z wieloma aplikacjami** można wybrać rozmiar kafelka aplikacji oraz porządek **układu menu Start** w siatce aplikacji. Jeśli wolisz szersze możliwości dostosowywania, możesz kontynuować przekazywanie pliku XML.
- Ustawienia przeglądarki kiosku są przenoszone do ustawień **kiosku**. Obecnie ustawienia **przeglądarki internetowej kiosku** mają własną kategorię w witrynie Azure Portal.
Dotyczy: system Windows 10 lub nowszy




### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Stosowanie profilu rozwiązania Autopilot do zarejestrowanych urządzeń z systemem Windows 10, które nie zostały jeszcze zarejestrowane w rozwiązaniu Autopilot <!-- 1558983 -->
Profil rozwiązania Autopilot możesz zastosować do zarejestrowanych urządzeń z systemem Windows 10, które nie zostały jeszcze zarejestrowane w rozwiązaniu Autopilot. W profilu rozwiązania Autopilot wybierz opcję **Convert all targeted devices to Autopilot** (Konwertuj wszystkie wybrane urządzenia na potrzeby rozwiązania Autopilot), aby automatycznie rejestrować urządzenia bez rozwiązania Autopilot w usłudze wdrażania rozwiązania Autopilot. Przetwarzanie rejestracji może potrwać do 48 godzin. Jeśli urządzenie nie zostało zarejestrowane i je zresetowano, rozwiązanie Autopilot przeprowadzi jego aprowizację.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Tworzenie i przypisywanie wielu profilów strony ze stanem rejestracji do grup usługi Azure AD <!-- 2526564 -->
Teraz możesz [utworzyć i przypisać](windows-enrollment-status.md) wiele profilów strony stanu rejestracji dla grup usługi Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migracja z programu Device Enrollment Program do usługi Apple Business Manager w usłudze Intune <!--2748613-->
Usługa Apple Business Manager (ABM) działa w usłudze Intune i można uaktualnić konto z programu Device Enrollment Program (DEP) do usługi ABM. Proces w usłudze Intune jest taki sam. Aby uaktualnić swoje konto Apple z programu DEP do usługi ABM, przejdź na stronę [ https://support.apple.com/en-us/HT208817 ]( https://support.apple.com/en-us/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Karty alertów i stanu rejestracji na stronie przeglądu rejestracji urządzenia <!--2748656-->
Alerty i błędy rejestracji pojawiają się teraz na osobnych kartach na stronie przeglądu rejestracji urządzenia.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Ograniczanie aplikacji i blokowanie dostępu do zasobów firmy na urządzeniach z systemem Android <!-- 2451462  -->  
W obszarze **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **Android** > **Zabezpieczenia systemu** w sekcji *Bezpieczeństwo urządzenia* znajduje się nowe ustawienie o nazwie **Aplikacje z ograniczeniami**. Ustawienie **Aplikacje z ograniczeniami** używa zasad zgodności, aby zablokować dostęp do zasobów firmy, jeśli pewne aplikacje są zainstalowane na urządzeniu. Urządzenie jest uznawane za niezgodne, dopóki aplikacje z ograniczeniami nie zostaną usunięte z urządzenia.
Dotyczy: 
- Android




## <a name="week-of-september-24-2018"></a>Tydzień od 24 września 2018 r.

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centrum administracyjne zarządzania urządzeniami rozwiązania Microsoft 365 <!-- 3078424 -->
Jedną z obietnic platformy Microsoft 365 jest uproszczona administracja, a w ciągu lat zintegrowaliśmy usługi zaplecza rozwiązania Microsoft 365 w celu dostarczania kompletnych scenariuszy, takich jak dostęp warunkowy w usłudze Intune i usłudze Azure AD. Nowe [Centrum administracyjne platformy Microsoft 365](http://devicemanagement.microsoft.com) umożliwia konsolidację, uproszczenie i integrację środowiska administracji. Obszar roboczy dla specjalistów ds. zarządzania urządzeniami zapewnia łatwy dostęp do wszystkich informacji i zadań związanych z zarządzaniem urządzeniami aplikacji i aplikacjami. Oczekujemy, że ten obszar roboczy stanie się podstawowym obszarem w chmurze dla zespołów informatycznych użytkowników końcowych przedsiębiorstwa.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Obsługa dodatkowych urzędów certyfikacji innych firm <!-- 3093107 -->
Przy użyciu prostego protokołu rejestrowania certyfikatów (SCEP) możesz teraz wystawiać nowe certyfikaty i odnawiać certyfikaty na urządzeniach przenośnych z systemami Windows, iOS, Android i macOS.

### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Usługa Intune teraz obsługuje system iOS 10 i nowsze <!-- 2454656 -->  
Rejestracja w usłudze Intune, aplikacja Portal firmy i program Managed Browser teraz obsługują tylko urządzenia systemu iOS z systemem iOS 10 lub nowszym. Aby sprawdzić, czy dotyczy to urządzeń lub użytkowników w Twojej organizacji, przejdź do usługi Intune w witrynie Azure Portal, a następnie do pozycji **Urządzenia** > **Wszystkie urządzenia**. Filtruj według systemu operacyjnego, a następnie kliknij pozycję **Kolumny**, aby udostępnić szczegóły wersji systemu operacyjnego. Zwróć się do tych użytkowników, aby uaktualnili swoje urządzenia do obsługiwanej wersji systemu operacyjnego.  

Jeśli masz dowolne z wymienionych poniżej urządzeń lub chcesz zarejestrować dowolne z wymienionych poniżej urządzeń, pamiętaj, że obsługują one tylko system iOS 9 i wcześniejsze.  Aby nadal korzystać z aplikacji Portal firmy usługi Intune, musisz uaktualnić te urządzenia do urządzeń obsługujących system iOS 10 lub nowszy:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3. generacja) 
* iPad Mini (1. generacja)  

## <a name="week-of-september-17-2018"></a>Tydzień od 17 września 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Usunięto duplikowanie kafelków stanu ochrony aplikacji <!-- 3083391 -->
Kafelki **Stan użytkownika dla systemu iOS** i **Stan użytkownika dla systemu Android** znajdowały się zarówno na stronie **Aplikacje klienckie — Przegląd**, jak i na stronie **Aplikacje klienckie — Stan ochrony aplikacji**. Kafelki stanu zostały usunięte ze strony **Aplikacje klienckie — Przegląd**, aby uniknąć ich duplikowania. 

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

[Dokumentacja witryny internetowej Portal firmy usługi Intune](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) została zaktualizowana w celu odzwierciedlenia tych zmian. Aby wyświetlić przykład rozszerzeń aplikacji, zobacz [UI updates for Intune end-user apps (Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune)](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Rozszerzone wykrywanie zdjęcia zabezpieczeń systemu w raportowaniu zgodności<!-- 2198738 -->
Rozszerzone wykrywanie zdjęcia zabezpieczeń systemu dla ustawień stanów teraz pojawia się we wszystkich raportach zgodności w konsoli administracyjnej.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-policies---1081974---"></a>Tagi zakresu dla zasad <!--1081974 -->
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
Jeśli włączono [mapowanie grup urządzeń](https://docs.microsoft.com/intune/device-group-mapping), w systemie Windows 10 po dokonaniu rejestracji przy użyciu przycisku **Połącz** w obszarze **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** zostanie teraz wyświetlony monit o wybranie kategorii urządzenia. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Używanie atrybutu SAMAccountName jako nazwy użytkownika konta dla profilów poczty e-mail <!-- 1500307 -->
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

### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Obsługa zasad ochrony aplikacji usługi Intune w przeglądarce Microsoft Edge dla urządzeń przenośnych <!-- 1817882 -->

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

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Używanie programu TeamViewer do udostępniania ekranów urządzeń z systemami iOS i MacOS<!-- 1985547 -->
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
Przeglądarka Microsoft Edge dla urządzeń przenośnych (iOS i Android) obsługuje teraz zasady ochrony aplikacji w usłudze Microsoft Intune. Użytkownicy urządzeń z systemami iOS i Android, którzy logują się przy użyciu kont firmowych usługi Azure AD w aplikacji Edge, będą chronieni przez usługę Intune. Na urządzeniach z systemem iOS zasady **Wymagaj programu Managed Browser dla zawartości internetowej** pozwolą użytkownikom na otwieranie linków w przeglądarce Microsoft Edge, gdy jest ona zarządzana.

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

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Wbudowane grupy Wszyscy użytkownicy i Wszystkie urządzenia na potrzeby przypisywania aplikacji profilu służbowego Android Enterprise <!-- 1813073 -->
Można użyć wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji profilu służbowego Android Enterprise. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Usługa Intune zainstaluje wymagane aplikacje, które są odinstalowywane przez użytkowników <!-- 1947010 -->
Jeśli użytkownik końcowy odinstaluje wymaganą aplikację, usługa Intune automatycznie ponownie instaluje aplikację w ciągu 24 godzin, nie czekając na zakończenie 7-dniowego cyklu ponownej oceny.

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


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nowe kroki rejestracji dla użytkowników na urządzeniach z systemem macOS High Sierra 10.13.2+ <!--1734567 -->
W systemie macOS High Sierra 10.13.2 wprowadzono pojęcie rejestracji w rozwiązaniu MDM „zatwierdzonej przez użytkownika”. Zatwierdzone rejestracje umożliwiają usłudze Intune zarządzanie niektórymi ustawieniami istotnymi dla zabezpieczeń. Aby uzyskać więcej informacji, zobacz dokumentację pomocy technicznej firmy Apple: https://support.apple.com/HT208019.

Urządzenia zarejestrowane przy użyciu aplikacji Portal firmy dla systemu macOS są traktowane jako „niezatwierdzone przez użytkownika”, chyba że użytkownik końcowy otworzy preferencje systemu i ręcznie wykona zatwierdzenie. Dlatego aplikacja Portal firmy dla systemu macOS teraz kieruje użytkowników systemu macOS 10.13.2 i nowszych do kroków ręcznego zatwierdzenia rejestracji pod koniec procesu rejestracji. Konsola administracyjna usługi Intune zgłasza fakt zatwierdzenia zarejestrowanego urządzenia przez użytkownika.



### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Zaawansowana ochrona przed zagrożeniami (ATP) i usługi Intune są w pełni zintegrowane <!-- 1629303 -->

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

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>Usługa Intune dostosowuje się do systemu Fluent Design System w aplikacji Portal firmy dla systemu Windows 10 <!-- 1195010 -->
Aplikacja Portal firmy usługi Intune dla systemu Windows 10 została zaktualizowana w celu dodania [widoku nawigacji systemu Fluent Design System](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Wzdłuż boku aplikacji znajduje się statyczna, pionowa lista wszystkich stron najwyższego poziomu. Kliknij dowolny link, aby szybko wyświetlać strony i przełączać się między nimi. Jest to pierwsza z kilku aktualizacji, które będą wprowadzane w ramach naszych ciągłych wysiłków mających na celu stworzenie bardziej adaptacyjnego, empatycznego, znanego środowiska pracy w usłudze Intune. Aby wyświetlić zaktualizowany wygląd, przejdź do obszaru [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Tydzień od 16 kwietnia 2018 r.

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Korzystanie z klienta Cisco AnyConnect dla systemu iOS <!-- 1333708 -->

W przypadku tworzenia nowego profilu sieci VPN dla systemu iOS są teraz dostępne dwie opcje: **Cisco AnyConnect** i **Cisco Legacy AnyConnect**. Profile Cisco AnyConnect obsługują wersję 4.0.7x i nowsze. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x oraz jego starszymi wersjami, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS. W przypadku platform systemów Android i macOS oraz profilu służbowego Android Enterprise nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.

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

## <a name="notices"></a>Uwagi

### <a name="plan-for-change-exchange-online-to-intune-connector-will-not-be-available-in-intune----3105122---"></a>Planowanie zmian: łącznik usługi Exchange Online z usługą Intune nie będzie dostępny w usłudze Intune <!-- 3105122 -->
Aby uprościć środowisko pracy z usługą Exchange Online i dostępem warunkowym, wyłączymy łącznik typu „usługa z usługą" między usługami Exchange Online i Intune. Ta zmiana rozpocznie się od grudniowej aktualizacji usługi i zostanie zakończona w aktualizacji usługi w lutym 2019 r.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Otrzymujesz tę wiadomość, ponieważ nasze rekordy wskazują, że używasz funkcji łącznika typu „usługa z usługą” w danym środowisku. Łącznik typu „usługa z usługą” obsługuje zarządzanie urządzeniami programu Exchange Active Sync Only w usłudze Intune dla usługi Exchange Online i nie obsługuje infrastruktury lokalnej. Ten łącznik— ze względu na sposób wyświetlania w konsoli — wydaje się być niezbędny w przypadku dostępu warunkowego, gdy w rzeczywistości nie jest potrzebny takiego dostępu. W aktualizacji usługi Intune z grudnia wyłączymy przycisk konfigurowania nowych łączników, aby to zagadnienie było jasne w konsoli. Następnie w lutym 2019 r. wszystkie istniejące łączniki usługi Exchange Online z usługą Intune zostaną wyłączone.

Jeśli używasz tych łączników w swoim środowisku, nie będziesz mieć możliwości monitorowania ani czyszczenia urządzeń programu Exchange Active Sync Only w usłudze Intune po wyłączeniu łączników w lutym. Nie przewidujemy, aby ta zmiana miała wpływ na użytkowników końcowych.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?

Jeśli masz skonfigurowany łącznik typu „usługa z usługą” i masz urządzenia programu Exchange Active Sync Only, przełącz się do innych metod zarządzania urządzeniami. Do wyboru są następujące opcje:

- Zarejestrowanie urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (MDM)
- Używanie zasad rozwiązania Intune App Protection do zarządzania urządzeniami
- Używanie kontrolek programu Exchange zgodnie z opisem w tej dokumentacji 

#### <a name="additional-information"></a>Dodatkowe informacje
[Konfiguracja łącznika usługi Exchange dla programów Intune i Exchange Online](https://docs.microsoft.com/intune/exchange-service-connector-configure)



### <a name="plan-for-change-performance-updates-to-intune-for-education---1750215--"></a>Planowanie pod kątem zmian: aktualizacje zwiększające wydajność dla usługi Intune for Education <!--1750215-->
Dodajemy kilka aktualizacji do usługi Intune for Education w celu zwiększenia szybkości i niezawodności podczas przypisywania ustawień do użytkowników lub urządzeń. W ramach tej zmiany pod koniec listopada przeniesiemy Twoje przypisania zasad lub ustawień do nowych grup.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?

Jako klient z usługą Intune for Education masz dwie grupy dynamiczne usługi Azure Active Directory (Azure AD): „Wszyscy użytkownicy” i „Wszystkie urządzenia”. Wskutek zastosowania tych aktualizacji te grupy usługi Azure AD „Wszyscy użytkownicy” i „Wszystkie urządzenia”nie będą widoczne w konsoli usługi Intune for Education. Jednak nadal będą widoczne w konsoli usługi Intune na platformie Azure pod zmienionymi nazwami „Wszyscy użytkownicy (przestarzałe, nie używaj)” i „Wszystkie urządzenia (przestarzałe, nie używaj)”.

Po wdrożeniu tych aktualizacji nie będzie już trzeba używać grup usługi Azure AD, aby przypisywać aplikacje i ustawienia w usłudze Intune. Zamiast tego przeniesiemy Twoje przypisania ustawień do nowych grup w konsoli usługi Intune for Education, które będą wyświetlane jako „Wszyscy użytkownicy” i „Wszystkie urządzenia”, tak jak wcześniej. Te zmiany zostaną wprowadzone na zapleczu, więc nie dostrzeżesz różnicy w konsoli usługi Intune for Education. Zmiany te nie powinny mieć żadnego wpływu na Twoich użytkowników końcowych ani na zarejestrowane urządzenia. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Nie musisz nic robić w związku z przenoszeniem przez nas Twoich przypisań zasad. Jeśli obecnie przypisujesz zasady w konsoli usługi Intune for Education, rób to nadal.

Jeśli obecnie przypisujesz zasady do grup usługi Azure AD wymienionych powyżej w usłudze Intune na platformie Azure, zamiast tego zacznij przypisywać je do grup „Wszyscy użytkownicy” i „Wszystkie urządzenia” w konsoli usługi Intune for Education. Gdy zobaczysz w konsoli grupy usługi Azure AD określone w ich nazwach jako przestarzałe, przestań przypisywać zasady w usłudze Azure AD. Jeśli obecnie nie używasz tych grup ze zmienionymi nazwami do żadnych celów, najlepiej je usuń.


### <a name="plan-for-change-intune-will-move-to-support-macos-1012-and-higher-in-december---2970975--"></a>Planowanie zmian: w grudniu usługa Intune przejdzie na obsługę systemu macOS w wersji 10.12 i nowszych <!--2970975--> 

Firma Apple właśnie wydała system macOS 10.14. W grudniu 2018 r. usługa Intune przejdzie na obsługę systemu macOS 10.12 i nowszych wersji. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?

Począwszy od grudnia, użytkownicy końcowi na urządzeniach z systemem macOS 10.11 lub wcześniejszym nie będą mogli korzystać z Portalu firmy w celu rejestracji w usłudze Intune. Będą musieli uaktualnić swoje urządzenia do systemu macOS 10.12 lub nowszego i uaktualnić aplikację Portal firmy do najnowszej wersji, aby nadal otrzymywać pomoc techniczną oraz nowe funkcje. 

System macOS 10.12 i jego nowsze wersje są obecnie obsługiwane na następujących urządzeniach: 
- MacBook (koniec 2009 roku i nowsze) 
- iMac (koniec 2009 roku i nowsze)
- MacBook Air (koniec 2010 roku i nowsze)  
- MacBook Pro (koniec 2010 roku i nowsze) 
- Mac Mini (koniec 2010 roku i nowsze) 
- Mac Pro (koniec 2010 roku i nowsze) 

Od grudnia użytkownicy końcowi, którzy mają urządzenia inne niż te wymienione powyżej, nie będą mogli uzyskać dostępu do najnowszej wersji aplikacji Portal firmy dla systemu macOS. Istniejące zarejestrowane urządzenia z nieobsługiwanymi wersjami systemu macOS starszymi niż macOS 10.12 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?

- Poproś użytkowników końcowych, aby do grudnia 2018 r. uaktualnili swoje urządzenia do obsługiwanej wersji systemu operacyjnego. 
- Sprawdź raporty usługi Intune w konsoli usługi Intune na platformie Azure, aby zobaczyć, na które urządzenia lub użytkowników może to mieć wpływ. Przejdź do pozycji Urządzenia > Wszystkie urządzenia i filtruj zawartość według systemu operacyjnego. Możesz dodać dodatkowe kolumny, które ułatwiają określenie, kto w organizacji ma urządzenia z systemem macOS 10.11. 
- Jeśli korzystasz z hybrydowego zarządzania urządzeniami mobilnymi (MDM), przejdź do pozycji Zasoby i zgodność > Urządzenia w konsoli programu Configuration Manager, kliknij prawym przyciskiem myszy kolumny, aby dodać kolumny System operacyjny i Wersja klienta, a następnie sortuj według systemu operacyjnego. Należy pamiętać, że hybrydowe zarządzanie urządzeniami mobilnymi jest przestarzałe i należy przejść na usługę Intune na platformie Azure najszybciej, jak to możliwe. 
 
#### <a name="additional-information"></a>Dodatkowe informacje
Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzenia z systemem macOS w usłudze Intune przy użyciu aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).
 

### <a name="plan-for-change-new-intune-support-experience-for-premier-customers"></a>Planowana zmiana: nowe środowisko pomocy technicznej usługi Intune dla klientów wersji Premier 
Jako klient korzystający z pomocy technicznej Microsoft Premier możesz obecnie używać portalu Microsoft Premier Online (MPO) (premier.microsoft.com) oraz usługi Intune na platformie Azure (portal.azure.com) do tworzenia żądań pomocy technicznej dla usługi Intune. Od 3 grudnia 2018 r. żądania pomocy technicznej będzie można tworzyć tylko w usłudze Intune na platformie Azure, ponieważ kontynuujemy rozbudowę środowiska pomocy technicznej Premier.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po 3 grudnia nie będzie można tworzyć żądań pomocy technicznej w portalu MPO.  Po podjęciu takiej próby zobaczysz monit o przejście do usługi Intune na platformie Azure, którego nie będzie można odrzucić. W tym miejscu możesz utworzyć żądanie pomocy technicznej, które zostanie przekierowane do dedykowanego działu pomocy technicznej firmy Microsoft, który w odpowiednim czasie zdiagnozuje i rozwiąże problem. Żądań pomocy technicznej utworzonych w portalu MPO nie można wyświetlić w witrynie Azure Portal, dlatego nie należy już tworzyć żądań pomocy technicznej w portalu MPO.  

Jeśli korzystasz z hybrydowego oprogramowania do zarządzania urządzeniami mobilnymi (hybrydowe oprogramowanie MDM) lub współzarządzania, możesz nadal używać portalu MPO do tworzenia żądań pomocy technicznej dla programu ConfigMgr, ale żądania pomocy technicznej dla usługi Intune tworzyć w witrynie Azure Portal. Przypominamy, że hybrydowe zarządzanie urządzeniami mobilnymi jest przestarzałe i należy zaplanować jak najszybsze przejście do usługi Intune na platformie Azure. Aby uzyskać więcej informacji, zobacz [Move from Hybrid Mobile Device Management to Intune on Azure](https://aka.ms/hybrid_notification) (Przechodzenie z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune na platformie Azure).

Zauważ, że tylko użytkownicy z rolami administratora globalnego, administratora usługi Intune i administratora pomocy technicznej usługi mogą tworzyć bilety pomocy technicznej w witrynie Azure Portal.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
- Nie korzystaj z portalu MPO, a do tworzenia wszystkich żądań pomocy technicznej usługi Intune i zarządzania nimi używaj usługi Intune na platformie Azure.  
- W razie potrzeby powiadom dział pomocy technicznej i zaktualizuj dokumentację.
- Jeśli użytkownicy bez ról administratora globalnego ani administratora usługi Intune aktualnie tworzą żądania pomocy technicznej w portalu MPO, przypisz im rolę administratora pomocy technicznej usługi Azure Active Directory, aby mogli nadal tworzyć bilety pomocy technicznej w witrynie Azure Portal.
- Kliknij pozycję Informacje dodatkowe, aby uzyskać więcej informacji i pomocne linki.

#### <a name="additional-information"></a>Dodatkowe informacje
Aby uzyskać więcej informacji, zobacz [wpis w blogu zespołu pomocy technicznej usługi Microsoft Intune](https://aka.ms/IntuneSupport_MPO_to_Azure).


### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Wymagana akcja: zaktualizuj ustawienia hasła zasad zgodności lub ograniczeń urządzenia z systemem Android w usłudze Intune
Usługa Intune będzie usuwać dostępny typ hasła „ustawienie domyślne urządzenia” dla systemu Android w wersji 4.4 i nowszej. Z powodu różnic między platformami Android i domyślnymi ustawieniami urządzeń ta zasada jest często traktowana jako opcjonalna przez urządzenie. Aby wyjaśnić nieporozumienia dotyczące wymuszania tego ustawienia w systemie Android, w przyszłym wydaniu usuniemy to ustawienie z interfejsu użytkownika. 
#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
- Jeśli chcesz wymagać hasła na urządzeniach, zalecamy, aby zamiast używania „ustawień domyślnych urządzenia” edytować profile platformy Android w celu jasnego określenia wymaganego typu hasła.
- Jeśli chcesz, aby to użytkownicy decydowali, czy tworzyć hasło, wybierz przycisk „Nieskonfigurowane”. Kiedy to ustawienie zostanie usunięte z interfejsu użytkownika, jeśli będzie ono nadal wybrane, zostanie wyświetlony monit o wybranie wartości innej niż „Ustawienia domyślne urządzenia” podczas kolejnej edycji profilu.
Co należy zrobić, aby przygotować się do tej zmiany?
Przejrzyj ustawienia dotyczące haseł w zasadach zgodności i ograniczeń urządzenia z systemem Android i Android dla firm. Znajdują się one w obszarze Zabezpieczenia systemu dla zasad zgodności oraz w obszarze Hasło urządzenia lub Ustawienia profilu służbowego dla ograniczeń urządzenia. Sekcja Dodatkowe informacje zawiera link do bardziej szczegółowych informacji i zrzutów ekranu przedstawiających, gdzie są konfigurowane te ustawienia.
#### <a name="additional-information"></a>Dodatkowe informacje
https://aka.ms/PasswordSettings 

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. W naszym [blogu pomocy technicznej usługi Intune](https://aka.ms/compportalats) będziemy umieszczać szczegółowe informacje.

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Planowanie zmian: usługa Intune przechodzi na protokół TLS 1.2
Poczynając od 31 października 2018 r., usługa Intune będzie obsługiwać protokół TLS (Transport Layer Security) w wersji 1.2, aby zapewnić najlepsze w swojej klasie szyfrowanie, zagwarantować, że nasza usługa będzie domyślnie bezpieczniejsza, oraz dopasować ją do innych usług firmy Microsoft, takich jak Microsoft Office 365. Usługa Office poinformowała o tej zmianie w komunikacie MC128929.

Aplikacja Portal firmy również przejdzie na obsługę protokołu TLS 1.2 od 31 października 2018 r.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Od 31 października 2018 r. usługa Intune już nie będzie obsługiwać protokołu TLS w wersjach 1.0 i 1.1. Wszystkie kombinacje klient-serwer i serwer-przeglądarka powinny używać protokołu TLS w wersji 1.2, aby zapewnić bezproblemowe połączenia z usługą Intune. Należy pamiętać, że ta zmiana będzie miała wpływ na urządzenia użytkowników końcowych, które nie są już obsługiwane przez usługę Intune, ale nadal odbierają zasady za pomocą usługi Intune i nie mogą korzystać z protokołu TLS w wersji 1.2. Obejmuje to urządzenia, na których działa system Android 4.3 lub starszy. Aby uzyskać listę objętych urządzeń i przeglądarek, zobacz poniższe informacje dodatkowe.

Jeśli po 31 października 2018 r. wystąpi problem związany z używaniem starszej wersji protokołu TLS, konieczna będzie aktualizacje do protokołu TLS 1.2 lub do urządzenia obsługującego protokół TLS 1.2 w ramach rozwiązania.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Zalecamy aktywne usunięcie zależności protokołu TLS 1.0 i 1.1 w swoich środowiskach oraz wyłączenie protokołu TLS 1.0 i 1.1 na poziomie systemu operacyjnego, jeśli to możliwe. Już dziś zacznij planowanie migracji do protokołu TLS 1.2. Sprawdź wpis w blogu na temat obsługi technicznej poniżej, gdzie znajduje się lista urządzeń, które dziś nie są obsługiwane przez usługę Intune, ale mogą nadal otrzymywać zasady, i które nie będą mogły nawiązać połączenia przy użyciu protokołu TLS w wersji 1.2. Może być konieczne powiadomienie tych użytkowników końcowych, że utracą oni dostęp do zasobów firmy.

**Dodatkowe informacje**: [Intune moving to TLS 1.2 for encryption (Przechodzenie do protokołu TLS 1.2 z powodu szyfrowania)](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)



## <a name="see-also"></a>Zobacz też
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/cloud-platform/roadmap)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
