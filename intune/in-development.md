---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b96fa9fac25f6de4180d3dcc9ee4022a2cc43fe
ms.sourcegitcommit: 7484ef8006f6b81d8976c328dd704512a31872ec
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2019
ms.locfileid: "70190252"
---
# <a name="in-development-for-microsoft-intune---september-2019"></a>W trakcie opracowywania — Microsoft Intune — wrzesień 2019 r.

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

### <a name="managed-google-play-private-lob-apps----1464182----"></a>Zarządzane Google Play prywatnych aplikacjach LOB <!-- 1464182  -->
Usługa Intune umożliwia administratorom IT publikowanie prywatnych aplikacji LOB systemu Android w zarządzanych Google Play za pośrednictwem elementu IFRAME osadzonego w konsoli usługi Intune.  Obecnie Administratorzy IT muszą publikować aplikacje LOB bezpośrednio w konsoli publikowania w sklepie Google, która wymaga wielu kroków i jest bardzo czasochłonna.  Ta nowa funkcja umożliwia łatwe publikowanie aplikacji LOB z minimalnym zestawem kroków bez opuszczania konsoli usługi Intune.  Wszystkie scenariusze zarządzania przedsiębiorstwami z systemem Android, które używają zarządzanych Google Play, mogą korzystać z tej funkcji (profilu służbowego, dedykowanych, w pełni zarządzanych i niezarejestrowanych urządzeń).  W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Następnie wybierz pozycję **zarządzana Google Play** z listy **Typ aplikacji** . Aby uzyskać więcej informacji na temat zarządzanych aplikacji Google Play, zobacz [Dodawanie zarządzanych Google Play aplikacji do urządzeń z systemem Android Enterprise za pomocą usługi Intune](apps-add-android-for-work.md).

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Komunikaty o stanie instalacji aplikacji Portal firmy <!-- 2514416  -->
Aplikacja Portal firmy będzie wyświetlać dodatkowe komunikaty o stanie instalacji aplikacji dla użytkowników końcowych. Poniższe warunki dotyczą nowych funkcji zależności Win32:
- Instalowanie aplikacji nie powiodło się. Zależności zdefiniowane przez administratora nie zostały spełnione.
- Aplikacja została zainstalowana pomyślnie, ale wymaga ponownego uruchomienia.
- Aplikacja jest w trakcie instalacji, ale wymaga ponownego uruchomienia, aby kontynuować.

### <a name="managed-google-play-iframe-support----2871756----"></a>Obsługa zarządzanych Google Play iframe <!-- 2871756  -->
Usługa Intune zapewnia obsługę dodawania linków sieci Web i zarządzania nimi bezpośrednio w konsoli usługi Intune za pośrednictwem elementu Managed Google Play iframe.  Dzięki temu administratorzy IT przesyłają grafiki z adresem URL i ikoną, a następnie wdrażają te linki do urządzeń podobnie jak zwykłe aplikacje dla systemu Android. Wszystkie scenariusze zarządzania przedsiębiorstwami z systemem Android, które używają zarządzanych Google Play, mogą korzystać z tej funkcji (profilu służbowego, dedykowanych, w pełni zarządzanych i niezarejestrowanych urządzeń).  W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Następnie wybierz pozycję **zarządzana Google Play** z listy **Typ aplikacji** . Aby uzyskać więcej informacji na temat zarządzanych aplikacji Google Play, zobacz [Dodawanie zarządzanych Google Play aplikacji do urządzeń z systemem Android Enterprise za pomocą usługi Intune](apps-add-android-for-work.md).

### <a name="macos-support-for-vpp-apps----3173501----"></a>Obsługa macOS dla aplikacji programu VPP <!-- 3173501  -->
aplikacje macOS zakupione przy użyciu programu Apple Business Manager będą wyświetlane w konsoli programu, gdy tokeny programu VPP firmy Apple są synchronizowane w usłudze Intune. Za pomocą konsoli programu można przypisywać, odwoływać i ponownie przypisywać licencje oparte na urządzeniach i użytkownikach dla grup. Microsoft Intune ułatwia zarządzanie aplikacjami programu VPP zakupionymi do użycia w firmie przez:
- Raportowanie informacji o licencji ze sklepu z aplikacjami.
- Śledzenie liczby używanych licencji.
- Pomoc w zapobieganiu instalacji większej liczby kopii aplikacji niż posiadana.
Aby uzyskać więcej informacji na temat usługi Intune i programu VPP, zobacz [Zarządzanie aplikacjami i książkami kupionymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](vpp-apps.md).

### <a name="macos-support-for-web-apps----3174427----"></a>Obsługa macOS dla aplikacji sieci Web <!-- 3174427  -->
Będzie można instalować aplikacje sieci Web, które umożliwiają dodawanie skrótu do adresu URL w sieci Web, do dokowania przy użyciu Portal firmy macOS. Użytkownicy końcowi mogą uzyskać dostęp do akcji **Instaluj** na stronie szczegółów aplikacji dla aplikacji sieci web w Portal firmy macOS. Aby uzyskać więcej informacji na temat typu aplikacji **link sieci Web** , zobacz [dodawanie aplikacji do Microsoft Intune](apps-add.md).

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>Przypisywanie programu Microsoft Edge beta do macOS <!-- 4678761  -->
Można dodać i przypisać najnowszą wersję programu Microsoft Edge beta do usługi Intune dla urządzeń macOS. W usłudze Intune wybierz pozycję **aplikacje** > klienckie**aplikacje** > **Dodaj aplikację** > **Microsoft Edge-macOS**. Następnie przypisz program Microsoft Edge beta do odpowiednich grup. Program Microsoft AutoUpdate (MAU) zachowuje aktualność programu Microsoft Edge. Aby uzyskać więcej informacji na temat przeglądarki Microsoft Edge, zobacz [Zarządzanie dostępem do sieci Web za pomocą przeglądarki Microsoft Edge z Microsoft Intune](manage-microsoft-edge.md).

### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Operacje odczytu i zapisu interfejs API programu Graph dla aplikacji usługi Intune <!-- 5031704  -->
Aplikacje będą mogły wywoływać interfejs API programu Graph usługi Intune z operacjami odczytu i zapisu przy użyciu tożsamości aplikacji bez poświadczeń użytkownika. Aby uzyskać więcej informacji na temat uzyskiwania dostępu do interfejsu API programu Microsoft Graph dla usługi Intune, zobacz [Praca z usługą Intune w programie Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji <!-- 2576686 -->
Zasady ochrony aplikacji usługi Intune (aplikacje) na urządzeniach z systemem Android i iOS umożliwiają kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji z obsługą aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android <!-- 3041956  -->
W przypadku dostępnych instalacji aplikacji na urządzeniach z profilem służbowym systemu Android można wyświetlić stan instalacji aplikacji oraz zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161----"></a>Funkcje urządzenia, ograniczenia dotyczące urządzeń i profile rozszerzeń dla ustawień systemu iOS i macOS są wyświetlane według typu rejestracji <!-- 4886161  -->

W usłudze Intune tworzysz profile dla urządzeń z systemem iOS i macOS (**Profile** > **konfiguracji** > urządzeń**Tworzenie profilu** > **systemu iOS** lub **macOS** dla platform > **funkcje urządzenia** , **Ograniczenia dotyczące urządzeń**lub **rozszerzenia** dla typu profilu). Obecnie są wyświetlane dostępne ustawienia w tych profilach. 

W przyszłej aktualizacji dostępne ustawienia w portalu usługi Intune zostaną skategoryzowane według typu rejestracji, którego dotyczą:

- iOS
  - Wszystkie typy rejestracji
  - Rejestracja urządzeń i automatyczna rejestracja urządzeń
  - Automatyczna rejestracja urządzeń

- macOS
  - Wszystkie typy rejestracji
  - Rejestrowanie urządzeń
  - Zatwierdzona przez użytkownika i automatyczna rejestracja urządzeń
  - Automatyczna rejestracja urządzeń

Dotyczy:

- iOS
  - [Funkcje urządzenia](ios-device-features-settings.md)
  - [Ograniczenia dotyczące urządzeń](device-restrictions-ios.md)

- macOS
  - [Funkcje urządzenia](macos-device-features-settings.md)
  - [Ograniczenia dotyczące urządzeń](device-restrictions-macos.md)
  - [Rozszerzenia](kernel-extensions-settings-macos.md)

### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835----"></a>Nowe ustawienia kontrolki głosowej dla nadzorowanych urządzeń z systemem iOS działających w trybie kiosku <!-- 4892835  -->

W usłudze Intune można tworzyć zasady do uruchamiania nadzorowanych urządzeń z systemem iOS jako kiosku lub dedykowanego urządzenia (**Profile** > **konfiguracji** > urządzeń**Utwórz profil** > **systemu iOS** dla platformy >  **Ograniczenia dotyczące urządzeń** typu profil > **kiosk (tylko nadzorowany)** ). 

W przyszłej aktualizacji dostępne są nowe ustawienia, które można kontrolować:

- **Sterowanie głosem**: włącza kontrolę głosu na urządzeniu w trybie kiosku.
- **Modyfikacja kontrolki głosowej**: zezwól użytkownikom na zmianę ustawienia kontrolki głosowej na urządzeniu w trybie kiosku.

Aby wyświetlić bieżące ustawienia, przejdź do [ustawień kiosku systemu iOS (tylko tryb nadzorowany)](device-restrictions-ios.md#kiosk-supervised-only).

Dotyczy:

- System iOS 13.0 lub nowszy

### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175----"></a>Korzystanie z logowania jednokrotnego dla aplikacji i witryn sieci Web na urządzeniach z systemem iOS i macOS <!-- 4893175  -->
W przyszłej aktualizacji dostępne są nowe ustawienia logowania jednokrotnego dla urządzeń z systemem iOS i macOS (**Profile** > **konfiguracji** > urządzeń**Utwórz profil** > **systemu iOS** lub **macOS** dla funkcje platformy > **urządzeń** dla typu profilu).

Te ustawienia służą do konfigurowania logowania jednokrotnego, szczególnie w przypadku aplikacji i witryn sieci Web korzystających z uwierzytelniania Kerberos. Można wybrać jedno z rozszerzeń ogólnej aplikacji Logowanie jednokrotne, a wbudowane rozszerzenie protokołu Kerberos firmy Apple.

Aby wyświetlić bieżące funkcje urządzenia, które można skonfigurować, przejdź do [funkcji urządzenia z systemem iOS](ios-device-features-settings.md) i [funkcji urządzenia macOS](macos-device-features-settings.md).

Dotyczy:

- System iOS 13.0 i nowsze
- System macOS 10.15 i nowsze

### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079----"></a>Kojarzenie domen z aplikacjami na urządzeniach macOS 10.15 + <!-- 4898079  -->
Na urządzeniach macOS można skonfigurować różne funkcje i wypchnąć te funkcje do urządzeń przy użyciu zasad (**Profile** > **konfiguracji** > urządzeń**Utwórz profil** > **macOS** dla funkcje platformy > **urządzeń** dla typu profilu). W przyszłej aktualizacji będziesz mieć możliwość kojarzenia domen z aplikacjami. Ta funkcja ułatwia udostępnianie poświadczeń z witrynami sieci Web, które są powiązane z Twoją aplikacją, i może być używana z rozszerzeniem logowania jednokrotnego firmy Apple, łączami uniwersalnymi i autowypełnianiem hasła. 

Aby wyświetlić bieżące funkcje, które można skonfigurować, przejdź do pozycji [Ustawienia funkcji urządzenia macOS w usłudze Intune](macos-device-features-settings.md).

Dotyczy:

- System macOS 10.15 i nowsze

### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474----"></a>W przypadku wyświetlania lub ukrywania aplikacji na nadzorowanych urządzeniach z systemem iOS używaj "iTunes" i "Apps" w adresie URL sklepu iTunes App Store <!-- 4928474  --> 
Usługa Intune umożliwia tworzenie zasad w celu wyświetlania lub ukrywania aplikacji na nadzorowanych urządzeniach z systemem iOS (**Profile** > **konfiguracji** > urządzeń**Tworzenie profilu** > **systemu iOS** dla platformy > **urządzenia ograniczenia** dotyczące typu profilu > **pokazywania lub ukrywania aplikacji (tylko tryb nadzorowany)** . 

Możesz wprowadzić adres URL sklepu iTunes App Store, na `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`przykład. W przyszłej aktualizacji będzie można używać obu `apps` i `itunes` w adresie URL, takich jak:

- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Aby uzyskać więcej informacji na temat tych ustawień, zobacz [Wyświetlanie lub ukrywanie aplikacji (tylko tryb nadzorowany)](device-restrictions-ios.md#show-or-hide-apps-supervised-only).

Dotyczy:

- iOS

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Obsługa profilów sieci VPN protokołu IKEv2 dla systemu iOS <!-- 1943438 -->
Będzie można tworzyć profile sieci VPN dla natywnego klienta sieci VPN systemu iOS za pomocą protokołu IKEv2. Protokół IKEv2 to nowy typ połączenia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **VPN** jako typ profilu > **Ustawienia**.

Te profile sieci VPN konfigurują natywnego klienta sieci VPN. Dlatego żadne aplikacje klienta sieci VPN nie są instalowane ani wypychane do urządzeń zarządzanych. Ta funkcja wymaga zarejestrowania urządzeń w usłudze Intune (rejestracji w oprogramowaniu MDM).

Aby wyświetlić bieżące ustawienia sieci VPN, które możesz skonfigurować, przejdź do tematu [Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).

Dotyczy: iOS


<!-- ***********************************************-->
## <a name="device-enrollment"></a>Rejestrowanie urządzeń

### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790----"></a>Nowi dzierżawcy będą domyślnie odwracać od zarządzania administratorami urządzeń z systemem Android <!-- 4869790  -->
Możliwości administratora urządzeń z systemem Android zostały zastąpione przez system Android Enterprise. W związku z tym zalecamy korzystanie z systemu Android Enterprise dla nowych rejestracji. W przyszłej aktualizacji nowi dzierżawcy będą musieli wykonać następujące czynności wymagane w ramach rejestracji systemu Android w celu korzystania z funkcji zarządzania administratorami urządzeń: Przejdź do usługi **Intune** > Rejestracja**urządzeń** > z**systemem Android** Urządzenia osobiste **i należące do firmy z uprawnieniami** > administracyjnymi urządzenia**używają administratora urządzenia do zarządzania urządzeniami.**  > 

Istniejące dzierżawy nie będą miały żadnych zmian w swoich środowiskach. 

Aby uzyskać więcej informacji na temat administratora urządzeń z systemem Android w usłudze Intune, zobacz [Rejestrowanie administratora urządzeń z systemem Android](https://docs.microsoft.com/intune/android-enroll-device-administrator).

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>W przypadku urządzeń z systemem iOS Dostosuj ekran prywatność procesu rejestracji Portal firmy <!-- 4394993  -->
Korzystając z promocji, będziesz mieć możliwość dostosowania ekranu prywatności Portal firmy, który użytkownicy końcowi zobaczą podczas rejestracji systemu iOS. W tym celu można dostosować listę rzeczy, które Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu.

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Wdrażanie aktualizacji oprogramowania na urządzeniach macOS <!-- 3194876 -->
Będziesz w stanie wdrożyć aktualizacje oprogramowania w grupach urządzeń macOS. Ta funkcja obejmuje krytyczne, oprogramowanie układowe, plik konfiguracji i inne aktualizacje. Będziesz mieć możliwość wysyłania aktualizacji przy następnym zalogowaniu lub wybrania tygodniowego harmonogramu wdrożenia aktualizacji w ustawionym lub nieaktualnym systemie Windows. Pozwala to na aktualizowanie urządzeń poza standardowymi godzinami pracy lub w przypadku, gdy dział pomocy technicznej jest w pełni zatrudniony. Zostanie również wyświetlony szczegółowy raport dotyczący wszystkich urządzeń macOS z wdrożonymi aktualizacjami. Możesz przejść do szczegółów raportu dla poszczególnych urządzeń, aby zobaczyć stan poszczególnych aktualizacji.

### <a name="send-custom-notifications-to-a-device----4928910----"></a>Wysyłanie powiadomień niestandardowych do urządzenia <!-- 4928910  -->
Będziesz w stanie wysyłać niestandardowe powiadomienia do określonych urządzeń, na których zainstalowano Portal firmy lub aplikację usługi Intune. Aby to zrobić, przejdź do pozycji**urządzenia** > usługi **Intune** > **wszystkie urządzenia** > Wybierz urządzenie > **więcej** > **powiadomień niestandardowych**. 

### <a name="updates-to-android-enterprise-fully-managed-features----3464667-5227935-4062195-4631425-4631440---"></a>Aktualizacje w pełni zarządzane funkcje systemu Android Enterprise <!-- 3464667, 5227935, 4062195, 4631425, 4631440 -->

Będziemy mogli dodać następujące wsparcie dla urządzeń z systemem Android w pełni zarządzanych:

- Certyfikaty SCEP dla w pełni zarządzanego systemu Android będą dostępne do uwierzytelniania certyfikatów na urządzeniach zarządzanych jako właściciel urządzenia. Certyfikaty SCEP są już obsługiwane na urządzeniach profilów służbowych.  Przy użyciu certyfikatów protokołu SCEP dla właściciela urządzenia można: <!-- 5227935 -->
    - Tworzenie profilu SCEP w sekcji DO w systemie Android Enterprise
    - Łączenie certyfikatów protokołu SCEP z profilem Wi-Fi na potrzeby uwierzytelniania
    - Łączenie certyfikatów protokołu SCEP z profilami sieci VPN na potrzeby uwierzytelniania
    - Łączenie certyfikatów protokołu SCEP z profilami poczty E-mail na potrzeby uwierzytelniania (za pośrednictwem AppConfig)
- Aplikacje systemowe będą obsługiwane na urządzeniach z systemem Android Enterprise. W usłudze Intune dodasz aplikację systemową dla systemu Android, wybierając pozycję **Aplikacje klienckie** > **Aplikacja** > **Dodaj**. Na liście **Typ aplikacji** wybierz pozycję **aplikacja systemowa dla systemu Android**. Aby uzyskać więcej informacji na temat dodawania aplikacji do usługi Intune, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](apps-add.md). <!-- 4062195 -->
- W obszarze **zgodność** > urządzeń z**systemem Android Enterprise** > **właściciel urządzenia**można utworzyć zasady zgodności, które określają poziom zaświadczania usługi Google SafetyNET.   <!-- 4631425 -->
- W w pełni zarządzanych urządzeniach z systemem Android Enterprise są obsługiwane dostawcy ochrony przed zagrożeniami dla urządzeń przenośnych. W obszarze **zgodność** > urządzeń z**systemem Android Enterprise** > **właściciel urządzenia**można wybrać akceptowalny poziom zagrożenia. <!-- 4631440 --> Listę bieżących ustawień można znaleźć w artykule [Ustawienia urządzeń z rozwiązaniem Android Enterprise umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune](compliance-policy-create-android-for-work.md#device-owner).


Dotyczy: 
- W pełni zarządzane urządzenia z rozwiązaniem Android Enterprise

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

### <a name="updated-support-experience-------5012398------"></a>Zaktualizowane środowisko pomocy technicznej   <!--  5012398    -->
W ramach dalszych ulepszeń będziemy aktualizować środowisko pomocy technicznej w konsoli usługi Intune.  Będziemy ulepszać wyszukiwanie w konsoli i opinie dotyczące typowych problemów oraz usprawnić przepływ pracy, aby skontaktować się z pomocą techniczną.     

<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="tamper-protection-for-windows-defender-antivirus-----4705448---------"></a>Ochrona przed naruszeniem dla programu antywirusowego Windows Defender  <!-- 4705448       -->
Będziemy dodawani do *Tamper Protection* ustawień, które usługa Intune może zarządzać dla programu antywirusowego Windows Defender. Aby włączyć lub wyłączyć ochronę przed naruszeniem, będzie można użyć profilu konfiguracji urządzenia dla programu Endpoint Protection systemu Windows 10.  Aby uzyskać więcej informacji na temat ochrony przed manipulacją, zobacz [zapobieganie zmianom ustawień zabezpieczeń przy użyciu ochrony przed manipulacją](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) w dokumentacji systemu Windows. 


<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).




