---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 633bf52084ad261f768cb4e59aaf4ce0ab5cd5bc
ms.sourcegitcommit: 46f4d3d160e18aeab9de7477eedc8351fbb78c85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2019
ms.locfileid: "67468725"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — lipiec 2019 r.

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
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Zarządzanie aplikacjami

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Użytkownicy urządzeń mogą wyświetlać wszystkie zarządzane aplikacje, które zainstalowali lub próbowali zainstalować <!-- 2352913 -->
W aplikacji Portal firmy dla systemu Windows będzie dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy będą mogli wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli organizacja nie określa aplikacji jako wymagane lub dostępne, użytkownicy zobaczą komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Użytkownicy będą również mogli sortować lub filtrować swoje aplikacje według stanu instalacji.

### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Niestandardowe powiadomienia dla użytkowników i grup    <!-- 16766574   -->
Wkrótce będzie można wysyłać powiadomienia wypychane ad-hoc niestandardowego z aplikacji Portal firmy dla użytkowników w systemach iOS i urządzenia z systemem Android, którymi można zarządzać za pomocą usługi Intune. Te niestandardowe powiadomienia nie są związane z określonych funkcji usługi Intune i może służyć do jakiegokolwiek celu, które wymagają, w tym ogólne powiadomienia, które chcesz wysyłać do niektórych lub wszystkich pracowników.  

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurowanie zawartość powiadomień aplikacji dla kont organizacji <!-- 2576686 -->
Zasady ochrony aplikacji usługi Intune (aplikacja) na urządzeniach z systemami Android i iOS pozwoli określić zawartość powiadomień aplikacji kontroli dla kont organizacji. Ta funkcja wymaga pomocy technicznej z poziomu aplikacji i mogą nie być dostępne dla wszystkich aplikacji włączenie aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android <!-- 3041956  -->
W przypadku dostępnych instalacji aplikacji na urządzeniach z profilem służbowym systemu Android można wyświetlić stan instalacji aplikacji, a także zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia


### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Obsługa profilów sieci VPN protokołu IKEv2 dla systemu iOS <!-- 1943438 -->
Będzie można tworzyć profile sieci VPN dla natywnego klienta sieci VPN systemu iOS za pomocą protokołu IKEv2. Protokół IKEv2 to nowy typ połączenia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **VPN** jako typ profilu > **Ustawienia**.

Te profile sieci VPN konfigurują natywnego klienta sieci VPN. Dlatego żadne aplikacje klienta sieci VPN nie są instalowane ani wypychane do urządzeń zarządzanych. Ta funkcja wymaga zarejestrowania urządzeń w usłudze Intune (rejestracji w oprogramowaniu MDM).

Aby wyświetlić bieżące ustawienia sieci VPN, które możesz skonfigurować, przejdź do tematu [Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).

Dotyczy: iOS

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 -->
Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma). W przyszłości będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Dotyczy: 
- System Windows 10 lub nowszy

### <a name="administrative-templates-for-group-policy---------3510695---"></a>Szablony administracyjne zasad grupy     <!--  3510695 -->
Aby pomóc udoskonalać zabezpieczenia urządzeń w chmurze, wydamy szablony administracyjne, które pozwolą na konfigurowanie ustawień wybierania zasad grupy dla komputerów z systemem Windows przy użyciu usługi Intune.  Te szablony umożliwiają dostawcy usługi konfiguracji zasad (CSP, Configuration Service Provider) udostępnianie aż do 2500 dodatkowych ustawień pakietu Office, systemu Windows i usługi OneDrive.

### <a name="manage-filevault-for-macos-------3858502--1210104-----"></a>Zarządzanie FileVault dla systemu macOS   <!--  3858502 + 1210104   -->
Będzie można zarządzać FileVault klucza szyfrowania dla urządzeń z systemem macOS przy użyciu usługi Intune urządzenie konfiguracji profil programu endpoint protection. Dotyczy to również depozytu wyświetlanie i rotację kluczy szyfrowania urządzeń firmowych. Użytkownicy końcowi będą mogli pobierać tych kluczy za pośrednictwem witryny internetowej Portal firmy.

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Zaawansowane ustawienia zapory Windows Defender   <!--  1311949     -->
Wkrótce w okresie obowiązywania publicznej wersji zapoznawczej będzie można zarządzać niestandardowymi regułami zapory usługi Windows Defender na komputerach klienckich za pomocą usługi Intune.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Podczas tworzenia profilu OEMConfig dla programu Android Enterprise nowym configuration designer <!-- 3712769  -->
W usłudze Intune, można utworzyć profil konfiguracji urządzeń, w którym wykorzystano aplikację OEMConfig (Konfiguracja urządzeń > Profile > Utwórz profil > przedsiębiorstwa z systemem Android dla platformy > OEMConfig dla typu profilu). Gdy to zrobisz, za pomocą szablonu i możesz zmienić wartości zostanie otwarty Edytor JSON. Ta aktualizacja obejmuje projektanta konfiguracji za pomocą ulepszone środowisko użytkownika zawierający szczegółowe informacje osadzone w aplikacji, w tym tytułów, opisów i innych. Edytor JSON jest nadal dostępna i wyświetla wszystkie zmiany wprowadzone w oknie projektanta konfiguracji.

Aby wyświetlić bieżące ustawienia, przejdź do [korzystanie i zarządzanie urządzeniami przedsiębiorstwa z systemem Android za pomocą OEMConfig](android-oem-configuration-overview.md).

Dotyczy: Android Enterprise


<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="improve-device-location---3855417---"></a>Poprawa lokalizacji urządzenia<!-- 3855417 -->
Będzie można powiększyć do współrzędnymi z urządzeniem przy użyciu **zlokalizuj urządzenie** akcji. Aby uzyskać więcej informacji o lokalizacji urządzenia utraty z systemem iOS, zobacz [znajdowanie zgubionych urządzeń z systemem iOS](device-locate.md).

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Konfigurowanie limitu czasu czyszczenia urządzenia automatycznego do 30 dni <!--4231059  -->
Będzie można tak krótka jak (zamiast bieżącego limitu wynoszącego 90 dni) do ciągu 30 dni od ostatniego logowania limit czasu czyszczenia urządzenia automatycznego. Aby to zrobić, przejdź do **Intune** > **urządzeń** > **instalacji** > **czystego zapasowej reguł urządzenia**.


<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="import-and-export-security-baselines------3408610------------"></a>Importowanie i eksportowanie podstawy zabezpieczeń    <!--3408610          -->  
Dodajemy możliwość eksportowania i importowania wartości bazowych zabezpieczeń, dzięki czemu można podjąć dostosowania Tobie i udostępniać je między środowiskami usługi Intune.



<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


