---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bc5ea7076e77e5071724168fab58fa78f59601c4
ms.sourcegitcommit: 7ceae61e036ccf8b33704751b0b39fee81944072
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744303"
---
# <a name="in-development-for-microsoft-intune---june-2019"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — czerwiec 2019 r.

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
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- ***********************************************-->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Użytkownicy urządzeń mogą wyświetlać wszystkie zarządzane aplikacje, które zainstalowali lub próbowali zainstalować <!-- 2352913 -->
W aplikacji Portal firmy dla systemu Windows będzie dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy będą mogli wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli organizacja nie określa aplikacji jako wymagane lub dostępne, użytkownicy zobaczą komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Użytkownicy będą również mogli sortować lub filtrować swoje aplikacje według stanu instalacji.

#### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956---"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android <!-- 3041956 -->
W przypadku dostępnych aplikacji na urządzeniach z profilem służbowym systemu Android można wyświetlić stan instalacji aplikacji, a także zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Konfigurowanie przeglądarki, którą można połączyć z danymi organizacji <!-- 3145939 -->
Zasady rozwiązania Intune App Protection na urządzeniach z systemami Android i iOS umożliwią transferowanie linków internetowych organizacji do określonej przeglądarki poza programem Intune Managed Browser lub Microsoft Edge.  Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

#### <a name="installed-apps-page-on-the-company-portal-website-----4224326---"></a>Strona zainstalowanych aplikacji w witrynie internetowej Portalu firmy  <!-- 4224326 -->
[Witryna internetowa Portalu firmy](https://portal.manage.microsoft.com/) będzie zawierać nową stronę, na której użytkownicy zobaczą aplikacje zainstalowane na ich urządzeniach. Ta lista obejmuje zarówno aplikacje dostępne, jak i aplikacje wymagane przez organizację. Na tej stronie użytkownicy będą mogli zobaczyć stan instalacji i stany wymagań aplikacji na urządzeniu. Aby uzyskać więcej informacji na temat witryny internetowej Portalu firmy, zobacz artykuły [Korzystanie z witryny Portal firmy usługi Intune](/intune-user-help/using-the-intune-company-portal-website.md) i [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

#### <a name="call-graph-api-read-operations-from-an-application-without-user-credentials----4655885---"></a>Wywoływanie operacji odczytu interfejsu API programu Graph z aplikacji bez poświadczeń użytkownika <!-- 4655885 -->
Aplikacje będą mogły wywoływać operacje odczytu interfejsu API programu Graph w usłudze Intune przy użyciu tożsamości aplikacji bez poświadczeń użytkownika. Aby dowiedzieć się więcej, zobacz [Get access without a user (Uzyskiwanie dostępu bez użytkownika)](https://docs.microsoft.com/graph/auth-v2-service).

<!-- ***********************************************-->
### <a name="device-configuration"></a>Konfiguracja urządzenia


#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Obsługa profilów sieci VPN protokołu IKEv2 dla systemu iOS <!-- 1943438 -->
Będzie można tworzyć profile sieci VPN dla natywnego klienta sieci VPN systemu iOS za pomocą protokołu IKEv2. Protokół IKEv2 to nowy typ połączenia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **VPN** jako typ profilu > **Ustawienia**.

Te profile sieci VPN konfigurują natywnego klienta sieci VPN. Dlatego żadne aplikacje klienta sieci VPN nie są instalowane ani wypychane do urządzeń zarządzanych. Ta funkcja wymaga zarejestrowania urządzeń w usłudze Intune (rejestracji w oprogramowaniu MDM).

Aby wyświetlić bieżące ustawienia sieci VPN, które możesz skonfigurować, przejdź do tematu [Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).

Dotyczy: iOS

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----20430240---"></a>Konfigurowanie ustawień dotyczących rozszerzeń jądra na urządzeniach z systemem macOS <!-- 20430240 -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę). Przyszła aktualizacja będzie zawierać nową grupę ustawień, która umożliwi konfigurowanie i używanie rozszerzeń jądra na urządzeniach.

Dotyczy: macOS 10.13.2 i nowsze

#### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Obsługa wyszukiwania punktów odniesienia według słów kluczowych  <!-- 3082036         -->
Podczas tworzenia lub edytowania profilu punktów odniesienia zabezpieczeń wkrótce będzie można używać *wyszukiwania* do filtrowania ustawień wyświetlanych w konsoli.   

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 -->
Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma). W przyszłości będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Dotyczy: 
- System Windows 10 lub nowszy

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002----"></a>Ustawienie Aplikacje tylko ze sklepu dla urządzeń z systemem Windows 10 uwzględnia więcej opcji konfiguracji <!-- 2697002  -->

Podczas tworzenia profilu ograniczeń urządzenia dla urządzeń z systemem Windows można użyć ustawienia **Aplikacje tylko ze sklepu**, aby użytkownicy instalowali tylko aplikacje ze sklepu z aplikacjami dla systemu Windows (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Ograniczenia urządzenia** jako typ profilu). W przyszłej aktualizacji to ustawienie zostanie rozszerzone tak, aby obsługiwało więcej opcji. 

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem Windows 10 (i nowszym) umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-windows-10.md#app-store).

Dotyczy: system Windows 10 lub nowszy

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Wdrażanie wielu profilów urządzeń przy użyciu funkcji Zebra Mobility Extensions do urządzenia, tej samej grupy użytkowników lub tej samej grupy urządzeń <!-- 4089955 -->
W usłudze Intune funkcja Zebra Mobility Extensions (MX) może być używana w profilu konfiguracji urządzenia w celu dostosowania ustawień lub dodania ustawień niewbudowanych w usłudze Intune. Obecnie można wdrożyć jeden profil do jednego urządzenia. W przyszłej aktualizacji będzie można wdrażać wiele profilów do:

- Tej samej grupy użytkowników
- Tej samej grupy urządzeń
- Pojedynczego urządzenia

Temat [Używanie urządzeń Zebra i zarządzanie nimi za pomocą funkcji Zebra Mobility Extensions w usłudze Microsoft Intune](android-zebra-mx-overview.md) przedstawia sposób używania rozszerzeń MX w usłudze Intune.

Dotyczy: system Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Niektóre ustawienia kiosku na urządzeniach z systemem iOS są ustawiane przy użyciu pozycji „Blokuj” zastępującej pozycję „Zezwalaj” <!-- 4404075  -->
Po utworzeniu profilu ograniczeń urządzenia na urządzeniach z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Kiosk**) możesz zdefiniować ustawienia **Blokada automatyczna**, **Przełącznik dzwonka**, **Obrót ekranu**, **Przycisk usypiania ekranu** i **Przyciski głośności**. 

Obecnie te ustawienia są konfigurowane przy użyciu pozycji **Zezwalaj** (blokowanie funkcji) lub **Nieskonfigurowane** (zezwalanie na funkcję). W przyszłej aktualizacji dostępnymi wartościami będą: **Blokuj** (blokowanie funkcji) i **Nieskonfigurowane** (zezwalanie na funkcję).

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie](device-restrictions-ios.md). 

Dotyczy: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704----"></a>Używanie funkcji Face ID do uwierzytelniania hasła na urządzeniach z systemem iOS <!-- 4490704  -->
Podczas tworzenia profilu ograniczeń urządzenia dla urządzeń z systemem iOS można użyć hasła w postaci odcisku palca. W przyszłej aktualizacji ustawienia hasła w postaci odcisku palca będą również zezwalać na rozpoznawanie twarzy (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzeń** jak typ profilu > **Hasło**). W wyniku są zmieniane następujące ustawienia:

- **Odblokowywanie za pomocą odcisku palca** to teraz **Odblokowywanie za pomocą funkcji Touch ID i Face ID**.
- **Modyfikacja odcisku palca (tylko w trybie nadzorowanym)** to teraz **Modyfikacja funkcji Touch ID i Face ID (tylko w trybie nadzorowanym)** .

Funkcja Face ID jest dostępna w systemie iOS 11.0 i nowszych wersjach. Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md#password).

Dotyczy: iOS

#### <a name="apps-feature-is-dependent-on-ratings-region-when-restricting-gaming-and-app-store-features-on-ios-devices----4593948----"></a>Funkcja aplikacji jest zależna od regionu klasyfikacji w przypadku ograniczania funkcji gier i sklepu z aplikacjami na urządzeniach z systemem iOS <!-- 4593948  -->
Na urządzeniach z systemem iOS można zezwolić na lub ograniczyć funkcje związane z grami, sklepem z aplikacjami i wyświetlaniem dokumentów (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Sklep App Store, wyświetlanie dokumentów, granie**). Można również wybrać region klasyfikacji, taki jak Stany Zjednoczone. W przyszłej aktualizacji funkcja **Aplikacje** zostanie przeniesiona jako element podrzędny do **regionu klasyfikacji** i jest zależna od **regionu klasyfikacji**.

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Dotyczy: iOS

#### <a name="administrative-templates-for-group-policy---------3510695---"></a>Szablony administracyjne zasad grupy     <!--  3510695 -->
Aby pomóc udoskonalać zabezpieczenia urządzeń w chmurze, wydamy szablony administracyjne, które pozwolą na konfigurowanie ustawień wybierania zasad grupy dla komputerów z systemem Windows przy użyciu usługi Intune.  Te szablony umożliwiają dostawcy usługi konfiguracji zasad (CSP, Configuration Service Provider) udostępnianie aż do 2500 dodatkowych ustawień pakietu Office, systemu Windows i usługi OneDrive.

####  <a name="new-settings-for-the-windows-security-baseline-----3534649-4217151------------"></a>Nowe ustawienia punktu odniesienia zabezpieczeń systemu Windows  <!-- 3534649, 4217151          -->
Dodajemy nowe ustawienia do punktu odniesienia zabezpieczeń systemu Windows. Pierwsze ustawienie dotyczy zabezpieczeń opartych na wirtualizacji, które wymagają bezpiecznego rozruchu. Drugie ustawienie umożliwi zarządzanie aktywowaniem głosem w aplikacjach systemu Windows, gdy ekran zostanie zablokowany.

#### <a name="security-baselines-will-be-generally-available------3785395---------"></a>Punkty odniesienia zabezpieczeń będą ogólnie dostępne  <!--  3785395       -->
Okres wersji zapoznawczej funkcji punktów odniesienia zabezpieczeń wkrótce zakończy się i funkcja ta będzie ogólnie dostępna. 

#### <a name="the-windows-security-baseline-template-will-be-generally-available-------3794072---------"></a>Szablon punktów odniesienia zabezpieczeń systemu Windows będzie ogólnie dostępny   <!--  3794072       -->
Okres wersji zapoznawczej szablonu punktów odniesienia zabezpieczeń systemu Windows wkrótce zakończy się i funkcja ta będzie ogólnie dostępna. Wersja zapoznawcza szablonu zostanie wycofana i udostępnimy nowy szablon.

<!-- ***********************************************-->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Przypisywanie tagów zakresu do wszystkich urządzeń zarządzanych w grupie zabezpieczeń <!-- 3173810 -->
Obecnie można przypisać tag zakresu do urządzenia, przechodząc na stronę **Właściwości** poszczególnych urządzeń i wybierając tagi zakresu. W ramach przyszłej aktualizacji będzie można przypisać tagi zakresu do grupy zabezpieczeń i wszystkie urządzenia w grupie zabezpieczeń również zostaną skojarzone z tymi tagami zakresu. Aby to zrobić, wybierz pozycję **Intune** > **Role** > **Zakres (tagi)**  > **Utwórz** > **Zakres (tagi)** > wybierz grupy, do których chcesz przypisać tag zakresu. Tag zakresu zostanie również przypisany do wszystkich urządzeń w tych grupach. Tagi zakresu ustawione przy użyciu tej funkcji zastąpią tagi zakresu ustawione przy użyciu bieżącego przepływu tagów zakresu urządzenia. (W ramach przyszłej aktualizacji bieżący przepływ służący do przypisywania tagów zakresu do urządzeń zostanie oznaczony jako tylko do odczytu).

#### <a name="see-the-security-patch-level-for-android-devices----4461911----"></a>Wyświetlanie poziomu poprawki zabezpieczeń dla urządzeń z systemem Android <!-- 4461911  -->
Będzie można wyświetlić poziom poprawki zabezpieczeń dla urządzeń z systemem Android. Aby to zrobić, wybierz pozycję **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Monitoruj** > **Sprzęt**.


<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


