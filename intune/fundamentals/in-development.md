---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e7c4e5ed45455dda941fb0c61c989c12c57135d
ms.sourcegitcommit: 29b1113dc04534c4c87c33c773c5a0e24266e042
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2019
ms.locfileid: "71999327"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>W trakcie opracowywania — Microsoft Intune — październik 2019 r.

Aby ułatwić Ci planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Ponadto:

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, opublikujemy również dodatkowy wpis w Centrum wiadomości usługi Office.
- Po wprowadzeniu funkcji w środowisku produkcyjnym — w wersji zapoznawczej lub ogólnie dostępnej — opis tej funkcji zostanie przeniesiony z tej strony na stronę [Co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!Note]
> Te elementy odzwierciedlają aktualne plany firmy Microsoft dotyczące funkcji usługi Intune, które zostaną wprowadzone w przyszłych wydaniach. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Nie wszystkie elementy będące w trakcie opracowywania zostały opisane na tej stronie.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Zarządzanie aplikacjami

### <a name="additional-app-configuration-variable-available----4969237----"></a>Dostępna jest dodatkowa zmienna konfiguracyjna aplikacji <!-- 4969237  -->
Podczas tworzenia zasad konfiguracji aplikacji będzie można uwzględnić zmienną konfiguracyjną `AAD Device ID` w ramach ustawień konfiguracji. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** > **Dodaj**. Wprowadź szczegóły zasad konfiguracji i wybierz pozycję **Ustawienia konfiguracji** , aby wyświetlić blok **Ustawienia konfiguracji** .

### <a name="dark-mode-for-ios-company-portal----4911422----"></a>Tryb ciemny dla Portal firmy systemu iOS <!-- 4911422  -->
Zaplanowano tryb ciemny dla Portal firmy systemu iOS. Pobierz aplikacje firmowe, Zarządzaj urządzeniami i uzyskaj pomoc techniczną w wybranym przez siebie schemacie kolorów. Aby uzyskać więcej informacji na temat konfigurowania Portalu firmy dla systemu iOS, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](../apps/company-portal-app.md).

### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-devices----4760025----"></a>Zapobiegaj instalacji aplikacji z nieznanych źródeł na urządzeniach z systemem Android Enterprise <!-- 4760025  -->
W przypadku urządzeń z profilem roboczym systemu Android Enterprise nie jest możliwe, że użytkownicy końcowi instalują aplikacje z nieznanych źródeł w profilu służbowym. Będzie można opcjonalnie rozszerzać to ograniczenie do profilu osobistego. Po włączeniu tego ograniczenia użytkownicy końcowi na urządzeniach profilu służbowego systemu Android nie będą również mogli korzystać z aplikacji do ładowania bezpośredniego z nieznanych źródeł do strony osobistej urządzenia. 

### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029----"></a>Aktualizowanie interfejsu użytkownika ochrony aplikacji i interfejsu użytkownika aprowizacji aplikacji systemu iOS <!-- 4102027, 4102029  -->
Interfejs użytkownika służący do tworzenia i edytowania zasad ochrony aplikacji oraz profilów aprowizacji aplikacji dla systemu iOS w usłudze Intune zostanie zaktualizowany. Zmiany interfejsu użytkownika:
- Uproszczone środowisko przy użyciu formatu stylu kreatora zagęszczone w obrębie jednego bloku. 
- Aktualizacja przepływu tworzenia w celu uwzględnienia przypisań.
- Strona podsumowania wszystkich elementów ustawionych podczas wyświetlania właściwości, przed utworzeniem nowych zasad lub podczas edytowania właściwości. Ponadto podczas edytowania właściwości podsumowanie będzie zawierać tylko listę elementów z kategorii właściwości, które są edytowane.

### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Tworzenie grup obiektów zarządzania o nazwie zbiory zasad <!-- 3762880  -->
Zestawy zasad umożliwiają tworzenie zbioru odwołań do już istniejących jednostek zarządzania, które muszą być identyfikowane, przeznaczone do użycia i monitorowane jako pojedynczą jednostkę koncepcyjną. Zestawy zasad nie zastępują istniejących koncepcji ani obiektów. Administrator może nadal przypisywać poszczególne obiekty, tak jak dzisiaj. Poszczególne obiekty są przywoływane przez zestaw zasad. W związku z tym wszystkie zmiany tych pojedynczych obiektów zostaną odzwierciedlone w zestawie zasad.  W usłudze Intune wybierzesz pozycję **zestawy zasad** > **Utwórz** , aby utworzyć nowy zestaw zasad. 

### <a name="win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Aplikacje Win32 na urządzeniach trybu Windows 10 S <!-- 3747604  --> 
Będziesz w stanie instalować i uruchamiać aplikacje Win32 na urządzeniach zarządzanych w trybie Windows 10 S. Będzie można utworzyć co najmniej jedną uzupełniającą zasadę dla trybu S przy użyciu narzędzi programu PowerShell usługi Windows Defender Application Control (WDAC). Podpisywanie zasad dodatkowych przy użyciu portalu podpisywania funkcji Device Guard, a następnie przekazywania i dystrybuowania zasad za pośrednictwem usługi Intune. W usłudze Intune można znaleźć tę możliwość, wybierając pozycję **aplikacje klienckie** > **zasady uzupełniania systemu Windows 10 S**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Ustawianie dostępności aplikacji na podstawie daty i godziny <!-- 3510685  -->
Jako administrator możesz skonfigurować godzinę rozpoczęcia i termin ostateczny dla wymaganej aplikacji. Po uruchomieniu rozszerzenie zarządzania usługi Intune rozpocznie pobieranie zawartości aplikacji i zapisuje ją w pamięci podręcznej. Aplikacja zostanie zainstalowana w ostatecznym terminie. W przypadku dostępnych aplikacji czas rozpoczęcia będzie określać, kiedy aplikacja jest widoczna w Portal firmy. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. Następnie wybierz określoną aplikację z listy lub wybierz pozycję **Dodaj** , aby dodać nową aplikację. W bloku aplikacja wybierz pozycję **przypisania** > **Dodaj grupę**. Ustaw wartość **Assignment Type** na **Required**, a następnie wybierz pozycję **Included Groups**. Ustaw ustawienie Ustaw **tę aplikację jako wymaganą dla wszystkich użytkowników** **, a następnie** wybierz pozycję **Edytuj** , aby zmodyfikować opcje **środowiska użytkownika końcowego** . W bloku **środowisko użytkownika końcowego** Ustaw **czas dostępności oprogramowania** zgodnie z wymaganiami. Aby uzyskać więcej informacji na temat dodawania aplikacji, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](../apps/apps-add.md).

### <a name="require-win32-apps-to-restart----3136567----"></a>Wymagaj ponownego uruchomienia aplikacji Win32 <!-- 3136567  -->
Po pomyślnej instalacji będzie można wymagać ponownego uruchomienia aplikacji Win32. Ponadto będzie można wybrać ilość czasu (okres prolongaty) przed ponownym uruchomieniem.

### <a name="company-portal-app-on-windows----1808082----"></a>Aplikacja Portal firmy w systemie Windows <!-- 1808082  -->
Aplikacja Portal firmy na urządzeniach z systemem Windows zostanie zaktualizowana tak, aby wyświetlała wyskakujące powiadomienia użytkownikom nawet po zamknięciu aplikacji. Aktualizacja będzie zawierać tylko powiadomienia o dostępnych aplikacjach, gdy stan instalacji zostanie ukończony lub zakończył się niepowodzeniem. Aplikacja Portal firmy nie będzie wyświetlać powiadomień dotyczących wymaganych aplikacji.

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Komunikaty o stanie instalacji aplikacji Portal firmy <!-- 2514416  -->
Aplikacja Portal firmy będzie wyświetlać dodatkowe komunikaty o stanie instalacji aplikacji dla użytkowników końcowych. Poniższe warunki dotyczą nowych funkcji zależności Win32:
- Instalowanie aplikacji nie powiodło się. Zależności zdefiniowane przez administratora nie zostały spełnione.
- Aplikacja została zainstalowana pomyślnie, ale wymaga ponownego uruchomienia.
- Aplikacja jest w trakcie instalacji, ale wymaga ponownego uruchomienia, aby kontynuować.

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>Przypisywanie programu Microsoft Edge beta do macOS <!-- 4678761  -->
Można dodać i przypisać najnowszą wersję programu Microsoft Edge beta do usługi Intune dla urządzeń macOS. Z usługi Intune wybierz pozycję **aplikacje klienckie** > **aplikacje** > **Dodaj aplikację** > **Microsoft Edge — macOS**. Następnie przypisz program Microsoft Edge beta do odpowiednich grup. Program Microsoft AutoUpdate (MAU) zachowuje aktualność programu Microsoft Edge. Aby uzyskać więcej informacji na temat przeglądarki Microsoft Edge, zobacz [Zarządzanie dostępem do sieci Web za pomocą przeglądarki Microsoft Edge z Microsoft Intune](../apps/manage-microsoft-edge.md).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji <!-- 2576686 -->
Zasady ochrony aplikacji usługi Intune (aplikacje) na urządzeniach z systemem Android i iOS umożliwiają kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji z obsługą aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android <!-- 3041956  -->
W przypadku dostępnych instalacji aplikacji na urządzeniach z profilem służbowym systemu Android można wyświetlić stan instalacji aplikacji oraz zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](../apps/app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](../enrollment/android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](../apps/apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia


### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328----"></a>Nowe ustawienia konfiguracji urządzenia dla nadzorowanych urządzeń z systemem iOS i iPadOS <!-- 5199328  -->
Na urządzeniach z systemem iOS i iPadOS można utworzyć profil, aby ograniczyć funkcje i ustawienia na urządzeniach (**Konfiguracja urządzenia** > **Profile** > **Tworzenie profilu** > **iOS/iPadOS** dla platformy **platform > ograniczenia** dotyczące typu profilu). Będą dostępne nowe ustawienia, które można kontrolować: 
- Dostęp do dysku sieciowego w aplikacji plików  
- Dostęp do dysku USB w aplikacji plików 
- Sieć Wi-Fi jest zawsze włączona 

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:
- System iOS 13.0 i nowsze
- System iPadOS 13.0 i nowsze

### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-and-android-enterprise----5021055----"></a>Ustawienie Połącz automatycznie zostanie usunięte w profilach sieci Wi-Fi w systemach Android i Android Enterprise <!-- 5021055  -->
Na urządzeniach z systemem Android i Android Enterprise można utworzyć profil sieci Wi-Fi w celu skonfigurowania różnych ustawień (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android** lub **Android Enterprise** w przypadku platformy > sieci **Wi-Fi** dla typu profilu). Ustawienie **Połącz automatycznie** zostanie usunięte, ponieważ [nie jest obsługiwane przez system Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Jeśli to ustawienie jest używane w profilu sieci Wi-Fi, może się okazać, że **połączenie** nie będzie działało. Nie musisz podejmować żadnych działań, ale należy pamiętać, że to ustawienie zostanie usunięte w interfejsie użytkownika usługi Intune.

Aby wyświetlić bieżące ustawienia, przejdź do [ustawień sieci Wi-Fi systemu Android](../configuration/wi-fi-settings-android.md) lub [ustawień sieci Wi-Fi systemu Android Enterprise](../configuration/wi-fi-settings-android-enterprise.md).

Dotyczy:
- Android
- Android Enterprise

### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices----4816339----"></a>Tworzenie globalnego serwera proxy HTTP na urządzeniach właścicieli urządzeń z systemem Android Enterprise <!-- 4816339  -->
Na urządzeniach z systemem Android Enterprise można skonfigurować globalny serwer proxy HTTP w taki sposób, aby spełniał standardy przeglądania sieci Web w organizacji (**Konfiguracja urządzenia** > **Profile** > **Tworzenie profilu** >  dla**systemu Android Enterprise** dla **właściciel urządzenia > platform > ograniczeń urządzenia** dla typu profilu > **łącznością**). Po skonfigurowaniu cały ruch HTTP będzie używać tego serwera proxy.

Dotyczy:
- właściciel urządzenia z systemem Android Enterprise

### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices----2266073----"></a>Nowy profil interfejsu konfiguracji oprogramowania układowego urządzenia dla urządzeń z systemem Windows 10 lub nowszym <!-- 2266073  -->
W systemie Windows 10 i nowszych można utworzyć profil konfiguracji urządzenia w celu kontrolowania ustawień i funkcji (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** dla platformy). Będzie dostępny nowy typ profilu interfejsu konfiguracji oprogramowania układowego urządzenia, który umożliwia usłudze Intune zarządzanie ustawieniami interfejsu UEFI (BIOS).

Aby zapoznać się z omówieniem wszystkich bieżących ustawień, które można skonfigurować, zobacz [stosowanie funkcji i ustawień na urządzeniach przy użyciu profilów urządzeń w Microsoft Intune](../configuration/device-profiles.md).

Dotyczy:
- Windows 10 RS5 (1809) i nowsze na wybranych urządzeniach

### <a name="pkcs-certificates-for-macos-----1333650------------------"></a>Certyfikaty PKCS dla macOS  <!-- 1333650                -->
Będziemy dodawaj pełną obsługę certyfikatów PKCS na urządzeniach z systemem macOS. Użytkownicy będą mogli wdrażać certyfikaty użytkowników i urządzeń za pomocą pól podmiotu dostosowania i alternatywnej nazwy podmiotu. Zostanie także udostępnione nowe ustawienie Zezwalaj wszystkim aplikacjom na dostęp, dzięki czemu wszystkie skojarzone aplikacje będą miały dostęp do klucza prywatnego. Więcej informacji na temat tego ustawienia można znaleźć w następującej dokumentacji firmy Apple: https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

###   <a name="derived-credentials-to-provision-mobile-devices-with-certificates----------1736036-1736037-1772050--------"></a>Pochodne poświadczenia do udostępniania urządzeń przenośnych za pomocą certyfikatów      <!--  1736036, 1736037, 1772050      --> 
Będziemy mogli dodać obsługę poświadczeń pochodnych, które obsługują standard Institute of *Standards and Technology (NIST) 800-157* na potrzeby wdrażania certyfikatów na urządzeniach.  Poświadczenia pochodne polegają na użyciu karty inteligentnej weryfikacyjnej tożsamości (standardem PIV) lub wspólnej karty dostępu (CAC), takiej jak karta inteligentna. Użytkownicy uwierzytelniają się za pomocą swojej karty inteligentnej na komputerze, a następnie przesyłają żądanie certyfikatu dla urządzenia zarządzanego zgodnie z procesem wymaganym przez pochodnego dostawcę poświadczeń.   

Proces używania poświadczeń pochodnych do uzyskiwania certyfikatu różni się od używania profilów certyfikatów protokołu SCEP lub PKCS, ale końcowy wynik jest taki sam — urządzenia przenośne z certyfikatami do uwierzytelniania, które mogą być używane na potrzeby uwierzytelniania aplikacji, sieci VPN, Wi-Fi lub poczty e-mail Profil.   

Aby uzyskać więcej informacji, zobacz [pochodne poświadczenia standardem PIV](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) w www.nccoe.nist.gov.

Początkowa wersja poświadczeń pochodnych będzie obsługiwać Entrust Datacard, intercede i DISA purebred w systemie iOS. Dodatkowe platformy i dostawcy poświadczeń pochodnych będą obsługiwane w nowszych wersjach.   

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Rejestrowanie urządzeń

### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment----4350697---"></a>Określ, które wersje systemu operacyjnego urządzeń z systemem Android są rejestrowane przy użyciu profilu służbowego lub rejestracji administratora urządzenia <!-- 4350697 -->
Przy użyciu ograniczeń typu urządzenia usługi Intune będzie można użyć wersji systemu operacyjnego urządzenia do określenia, które urządzenia użytkownika będą korzystać z rejestracji profilu służbowego systemu Android lub rejestracji administratora urządzeń z systemem Android. W tym celu przejdź do pozycji **Intune** > **rejestracja urządzeń** > **ograniczenia rejestracji** > **Tworzenie ograniczenia** > **typu urządzenia** >  **.**

### <a name="edit-device-name-value-for-autopilot-devices----4816775---"></a>Edytuj wartość nazwy urządzenia dla urządzeń z autopilotażem <!-- 4816775 -->
Będziesz w stanie edytować wartość nazwy urządzenia dla urządzeń z urządzeniami niewidocznymi w usłudze Azure AD. W tym celu przejdź do usługi **Intune** > **rejestracja urządzeń** > **rejestracja w systemie Windows** > **urządzeń** z**systemem windows autopilotaż** >  > wybierz urządzenie > zmienić wartość nazwy urządzenia w prawym okienku > **Zapisz** .

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Dostosowywanie ekranu prywatności wyświetlanego podczas rejestracji w aplikacji Portal firmy na urządzeniach z systemem iOS <!-- 4394993  -->
Przy użyciu języka markdown będzie można dostosować ekran prywatności w aplikacji Portal firmy, który użytkownicy końcowi widzą podczas rejestracji w systemie iOS. W tym celu można dostosować listę elementów i działań, których Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu.

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami


### <a name="edit-group-tag-value-for-autopilot-devices---4816775---"></a>Edytuj wartość tagu grupy dla urządzeń z autopilotażem<!-- 4816775 -->
Będziesz w stanie edytować wartość tagu grupy dla urządzeń z autopilotażem. W tym celu przejdź do usługi **Intune** > **rejestracja urządzeń** > **rejestracja w systemie Windows** > **urządzeń** z**systemem windows autopilotaż** >  > Wybierz urządzenie > zmienić wartość tagu grupy w okienku po prawej stronie > **Zapisz** .

### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089------------"></a>Aktualizacja interfejsu użytkownika do tworzenia i edytowania pierścieni aktualizacji systemu Windows 10  <!-- 4099089          -->   
Będziemy wdrażać zaktualizowane środowisko użytkownika tworzenia i edytowania dla pierścieni aktualizacji systemu Windows 10 dla usługi Intune.  Zmiany w interfejsie użytkownika będą obejmować:  
- Uprość istniejące środowisko przy użyciu formatu stylu kreatora zagęszczonego w obrębie jednego bloku. Ta aktualizacja interfejsu użytkownika będzie dołączana z użyciem bloku rozwojem, który wymaga od specjalistów IT przejścia do szczegółowej podróży w bloku.   
- Popraw przepływ tworzenia w celu uwzględnienia przypisań.  
- Dodanie strony podsumowującej wszystkich elementów ustawionych podczas wyświetlania właściwości, przed utworzeniem nowego pierścienia aktualizacji i podczas edycji właściwości. Podczas edycji podsumowanie będzie pokazywać tylko listę elementów ustawionych w ramach jednej kategorii właściwości, które są edytowane.

### <a name="ui-update-for-creating-and-editing-ios-software-updates-----4099090----------"></a>Aktualizacja interfejsu użytkownika do tworzenia i edytowania aktualizacji oprogramowania dla systemu iOS  <!-- 4099090        -->   
Będziemy wdrażać zaktualizowane środowisko interfejsu użytkownika dla aktualizacji oprogramowania dla systemu iOS w usłudze Intune. Zmiany w interfejsie użytkownika będą obejmować:
- Uprość istniejące środowisko przy użyciu formatu stylu kreatora zagęszczonego w obrębie jednego bloku. Ta aktualizacja interfejsu użytkownika będzie dołączana z użyciem bloku rozwojem, który wymaga od specjalistów IT przejścia do szczegółowej podróży w bloku.  
- Proces tworzenia przepływu zasad aktualizacji oprogramowania dla systemu iOS zostanie zaktualizowany w celu uwzględnienia przypisań 
- Zasady aktualizacji oprogramowania dla systemu iOS zawierają podsumowaną stronę wszystkich elementów ustawionych podczas wyświetlania właściwości, przed utworzeniem nowych zasad i podczas edycji właściwości. Podczas edycji podsumowanie będzie pokazywać tylko listę elementów ustawionych w ramach jednej kategorii właściwości, które są edytowane.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Docelowa Grupa użytkowników macOS do wymagania zarządzania Jamf <!-- 4061739 -->
Będziesz mieć możliwość nakierowania określonym grupom użytkowników, aby wymagać, aby ich urządzenia macOS były zarządzane przez Jamf. Ten element docelowy umożliwi zastosowanie integracji zgodności Jamf z podzbiorem urządzeń macOS, podczas gdy inne urządzenia będą nadal zarządzane przez usługę Intune. Pozwoli to również na stopniowe Migrowanie urządzeń użytkowników z jednego MDM do drugiego.

### <a name="new-restrictions-for-renaming-windows-devices----3478938---"></a>Nowe ograniczenia dotyczące zmiany nazw urządzeń z systemem Windows <!-- 3478938 -->
Nazwy urządzeń muszą być zgodne z następującymi regułami:
- 15 znaków lub mniej (musi być mniejsze lub równe 63 bajtów, bez końcowej wartości NULL)
- Niezerowy lub pusty ciąg
- Dozwolone znaki ASCII: litery (a-z, A-Z), cyfry (0-9) i łączniki
- Dozwolone wartości Unicode: characters > = 0x80, muszą być prawidłowym kodowaniem UTF8, musi być IDN-Mappable (RtlIdnToNameprepUnicode; patrz RFC 3492)
- Nazwy nie mogą zawierać tylko cyfr ani zaczynać się od cyfry
- Brak spacji w nazwie
- Niedozwolone znaki: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Wdrażanie aktualizacji oprogramowania na urządzeniach macOS <!-- 3194876 -->
Będziesz w stanie wdrożyć aktualizacje oprogramowania w grupach urządzeń macOS. Ta funkcja obejmuje krytyczne, oprogramowanie układowe, plik konfiguracji i inne aktualizacje. Będziesz mieć możliwość wysyłania aktualizacji przy następnym zalogowaniu lub wybrania tygodniowego harmonogramu wdrożenia aktualizacji w ustawionym lub nieaktualnym systemie Windows. Ta funkcja ułatwia aktualizowanie urządzeń poza standardowymi godzinami pracy lub w przypadku, gdy dział pomocy technicznej jest w pełni zatrudniony. Zostanie również wyświetlony szczegółowy raport dotyczący wszystkich urządzeń macOS z wdrożonymi aktualizacjami. Możesz przejść do szczegółów raportu dla poszczególnych urządzeń, aby zobaczyć stan poszczególnych aktualizacji.

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

### <a name="new-android-report-on-devices-overview-page----2984353----"></a>Strona przeglądu nowego raportu systemu Android na urządzeniach <!-- 2984353  -->
Na stronie przegląd urządzeń zostanie dodany nowy raport zawierający informacje o liczbie urządzeń z systemem Android zarejestrowanych w poszczególnych rozwiązaniach do zarządzania urządzeniami. Ten wykres przedstawia liczbę zarejestrowanych urządzeń z profilem służbowym, w pełni zarządzaną, dedykowaną i administratorem urządzeń. Aby wyświetlić raport, wybierz pozycję **Intune** > **Devices** > **Przegląd**.

### <a name="windows-autopilot-deployment-reports----3856172----"></a>Raporty wdrażania przy użyciu rozwiązania Windows Autopilot <!-- 3856172  -->
Nowy raport zawiera szczegółowe informacje o każdym urządzeniu wdrożonym za pomocą autopilotażu systemu Windows. Te dane będą dostępne przez 30 dni po wdrożeniu. Aby wyświetlić raport, przejdź do usługi **Intune** > **rejestracja urządzeń** > **Monitoruj** > **wdrożeń autopilotażu**.

### <a name="updated-support-experience-------5012398------"></a>Zaktualizowane środowisko pomocy technicznej   <!--  5012398    -->
W ramach dalszych ulepszeń będziemy aktualizować środowisko pomocy technicznej w konsoli usługi Intune.  Będziemy ulepszać wyszukiwanie w konsoli i opinie dotyczące typowych problemów oraz usprawnić przepływ pracy, aby skontaktować się z pomocą techniczną.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).




