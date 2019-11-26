---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 796439581ca0ae91e788a91ab0bc2ef8f6019626
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199338"
---
# <a name="in-development-for-microsoft-intune---december-2019"></a>W trakcie opracowywania dla usługi Microsoft Intune — grudzień 2019 r.

Aby ułatwić Ci przygotowanie i planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Oprócz informacji na tej stronie:

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, publikujemy również dodatkowy wpis w centrum wiadomości usługi Office.
- Gdy funkcja przechodzi do środowiska produkcyjnego, niezależnie od tego, czy jest to wersja zapoznawcza, czy ogólnie dostępna, opis funkcji zostanie przeniesiony z tej strony do [nowości](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!NOTE]
> Ta strona przedstawia nasze bieżące oczekiwania dotyczące możliwości usługi Intune w przyszłej wersji. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Ta strona nie zawiera opisu wszystkich funkcji programistycznych.

**Kanał informacyjny RSS**: dowiaduj się o aktualizacjach tej strony dzięki skopiowaniu i wklejeniu następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="ios-user-licensed-vpp-apps---5619268-idready---"></a>Aplikacje programu VPP licencjonowane przez użytkownika systemu iOS<!-- 5619268 idready -->
W przypadku rejestracji użytkowników urządzenia z systemem iOS użytkownicy końcowi nie będą już prezentowane za pomocą aplikacji VPP licencjonowanych przez urządzenia, które zostały wdrożone jako dostępne. Użytkownicy końcowi będą jednak nadal widzieć wszystkie aplikacje programu VPP licencjonowane przez użytkownika w ramach Portal firmy. Aby uzyskać więcej informacji o aplikacjach programu VPP, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemów iOS i macOS, które zostały zakupione w ramach programu zakupów zbiorczych firmy Apple](~/apps/vpp-apps-ios.md).

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745-idready---"></a>Pobieranie osobistego klucza odzyskiwania z usługi MEM zaszyfrowane urządzenia macOS<!-- 4851745 idready -->
Użytkownicy końcowi będą mogli pobrać własny klucz odzyskiwania (klucz FileVault) przy użyciu aplikacji Portal firmy systemu iOS. Urządzenie, które ma osobisty klucz odzyskiwania, musi być zarejestrowane w usłudze Intune i zaszyfrowane za pomocą usługi FileVault za pomocą usługi Intune. Korzystając z aplikacji Portal firmy systemu iOS, użytkownik końcowy może otworzyć widok sieci Web Safari i pobrać własny klucz odzyskiwania. W usłudze Intune wybierz pozycję **urządzenia** > *zaszyfrowanym i zarejestrowanym urządzeniem macOS* > **Pobierz klucz odzyskiwania**. Aby uzyskać więcej informacji na temat FileVault, zobacz [FileVault Encryption for macOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

### <a name="microsoft-app-icons-update--4677605--"></a>Aktualizacja ikon aplikacji firmy Microsoft<!--4677605-->
Ikony używane dla aplikacji firmy Microsoft w okienku określania wartości docelowej aplikacji dla zasad ochrony aplikacji i zasad konfiguracji aplikacji zostaną zaktualizowane.

### <a name="smime-support-for-microsoft-outlook-mobile---2669398----"></a>Obsługa protokołu S/MIME dla programu Microsoft Outlook Mobile<!-- 2669398  -->
Usługa Intune będzie obsługiwać dostarczanie certyfikatów podpisywania S/MIME i szyfrowania, które mogą być używane z programem Outlook Mobile w systemach iOS i Android. Aby uzyskać powiązane informacje, zobacz [Ustawienia poczty e-mail dla urządzeń z systemem iOS](~/configuration/email-settings-ios.md) i [Ustawienia poczty e-mail dla urządzeń z systemem Android](~/configuration/email-settings-android.md).

### <a name="custom-settings-support-for-macos-applications---4736278----"></a>Obsługa ustawień niestandardowych dla aplikacji macOS<!-- 4736278  -->
Usługa Intune będzie obsługiwać ustawienia niestandardowe, umożliwiając dodawanie określonych kluczy i wartości do istniejącego pliku listy właściwości preferencji (plist) w celu skonfigurowania aplikacji macOS i urządzenia. Nie wszystkie aplikacje obsługują preferencje zarządzane, a w niektórych przypadkach można zarządzać tylko określonymi ustawieniami. Ustawienia są wdrażane tylko za pośrednictwem kanału urządzenia. Należy przekazać tylko pliki listy właściwości lub pliki XML, które są przeznaczone dla ustawień kanału urządzenia.

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Wyświetl powiadomienia dla aplikacji Portal firmy w systemie Windows<!-- 1808082  -->
Zaktualizujemy aplikację Portal firmy na urządzeniach z systemem Windows, aby wyświetlać wyskakujące powiadomienia użytkownikom nawet po zamknięciu aplikacji. Aktualizacja będzie zawierać powiadomienia dotyczące dostępnych aplikacji tylko wtedy, gdy stan instalacji zostanie ukończony lub zakończył się niepowodzeniem. Aplikacja Portal firmy nie będzie zawierać powiadomień dotyczących wymaganych aplikacji.

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Wyświetlanie komunikatów o stanie instalacji dla aplikacji Portal firmy<!-- 2514416  -->
Aplikacja Portal firmy będzie wyświetlać dodatkowe komunikaty o stanie instalacji aplikacji dla użytkowników końcowych. Poniższe warunki dotyczą nowych funkcji zależności Win32:
- Instalowanie aplikacji nie powiodło się. Zależności zdefiniowane przez administratora nie zostały spełnione.

### <a name="configure-app-notification-content-for-organization-accounts---2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji<!-- 2576686 -->
Aplikacja usługi Intune na urządzeniach z systemem Android i iOS umożliwi kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji korzystających z aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji (APP), zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998-idready---"></a>Zablokuj użytkownikom możliwość konfigurowania poświadczeń certyfikatów w zarządzanym magazynie kluczy na urządzeniach właścicieli urządzeń z systemem Android Enterprise<!-- 3311998 idready -->
Na urządzeniach będących właścicielami urządzeń z systemem Android Enterprise istnieje nowe ustawienie służące do blokowania użytkownikom konfigurowania poświadczeń certyfikatów w zarządzanym magazynie kluczy (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **Android Enterprise** for platform > **tylko właściciel urządzenia > ograniczenia dotyczące urządzeń** dla typu profilu > **Użytkownicy i konta**).

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [Android Enterprise device settings to allow or restrict features using Intune](../configuration/device-restrictions-android-for-work.md) (Ustawienia urządzeń z systemem Android Enterprise używane w celu zezwolenia na funkcje lub ich ograniczenia za pomocą usługi Intune).

Dotyczy:
- Właściciel urządzenia z systemem Android Enterprise, w tym urządzenia dedykowane i w pełni zarządzane

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686-idready---"></a>Profile konfiguracji urządzeń sieci przewodowej dla urządzeń macOS<!-- 3508686 idready -->
W przypadku urządzeń z systemem macOS przyszła aktualizacja będzie zawierać nowy profil konfiguracji urządzenia, który konfiguruje sieci przewodowe (**Konfiguracja urządzeń** > **Profile** > **tworzenia profilu** > **macOS** dla platformy > **sieci przewodowej** dla typu profilu). Użyj tej funkcji, aby utworzyć profile 802.1 x w celu zarządzania sieciami przewodowymi i wdrożyć te sieci przewodowe na urządzeniach macOS.

Dotyczy:
- macOS

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Dodawanie automatycznych ustawień serwera proxy do profilów sieci Wi-Fi dla profilów służbowych systemu Android Enterprise<!-- 4490822 idready -->
Na urządzeniach profilu służbowego systemu Android Enterprise można tworzyć profile sieci Wi-Fi. Po wybraniu typu przedsiębiorstwa Wi-Fi można także wprowadzić typ protokołu uwierzytelniania rozszerzonego (EAP) używanego w sieci Wi-Fi.

W przyszłej aktualizacji, po wybraniu typu przedsiębiorstwa, będziesz mieć możliwość wprowadzenia automatycznych ustawień serwera proxy, w tym adresu URL serwera proxy, takiego jak `proxy.contoso.com`.

Aby wyświetlić bieżące ustawienia sieci Wi-Fi, które można skonfigurować, przejdź do pozycji [Dodaj ustawienia sieci Wi-Fi dla urządzeń z systemem Android Enterprise i kiosku dla systemu Android w Microsoft Intune](../configuration/wi-fi-settings-android-enterprise.md).

Dotyczy:
- Android Enterprise — profil służbowy

### <a name="enable-network-access-control-nac-with-cisco-anyconnect-vpn-on-ios-devices---4860111-idready---"></a>Włączanie kontroli dostępu do sieci (NAC) przy użyciu sieci VPN Cisco AnyConnect na urządzeniach z systemem iOS<!-- 4860111 idready -->
Na urządzeniach z systemem iOS można utworzyć profil sieci VPN i używać różnych typów połączeń, w tym Cisco AnyConnect (**Konfiguracja urządzeń** > **Profile** > **tworzenia profilu** > **iOS** dla platformy > **sieci VPN** dla typu profilu > **Cisco AnyConnect** dla typu połączenia). 

W przyszłej aktualizacji można włączyć funkcję kontroli dostępu do sieci (NAC) za pomocą programu Cisco AnyConnect. Aby użyć tej funkcji:

1. W [podręczniku administratora aparatu usług Cisco Identity Services](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)wykonaj kroki opisane w temacie **Konfigurowanie Microsoft INTUNE jako serwera MDM** , aby skonfigurować aparat usługi Cisco Identity Services (ISE) na platformie Azure.
2. W profilu konfiguracji urządzenia w usłudze Intune wybierz ustawienie **włącz Access Control sieci (NAC)** .

Aby wyświetlić wszystkie dostępne ustawienia sieci VPN, przejdź do pozycji [Konfigurowanie ustawień sieci VPN na urządzeniach z systemem iOS](../configuration/vpn-settings-ios.md).

Dotyczy:
- iOS

### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578-idready---"></a>Zaktualizowano środowisko logowania jednokrotnego dla aplikacji i witryn sieci Web na urządzeniach z systemami iOS, iPadOS i macOS<!-- 4999578 idready -->
Usługa Intune dodaje więcej ustawień logowania jednokrotnego dla urządzeń z systemem iOS, iPadOS i macOS. Obecnie można skonfigurować rozszerzenia aplikacji logowania jednokrotnego dla poświadczeń oraz wbudowane rozszerzenia protokołu Kerberos firmy Apple w usłudze Intune. W przyszłej aktualizacji będziesz mieć możliwość skonfigurowania przekierowywania rozszerzeń aplikacji logowania jednokrotnego przez Twoją organizację lub dostawcę tożsamości. 

Użyj tych ustawień, aby skonfigurować bezproblemowe środowisko logowania jednokrotnego dla aplikacji i witryn sieci Web korzystających z nowoczesnych metod uwierzytelniania, takich jak OAuth i SAML2. 

Aby wyświetlić ustawienia rozszerzenia aplikacji Logowanie jednokrotne, które można skonfigurować, przejdź do [logowania jednokrotnego w systemie iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) i logowanie [jednokrotne w systemie macOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Dotyczy:
- iOS/iPadOS
- macOS

### <a name="require-use-of-approved-keyboards-on-android--4761794-idready---"></a>Wymagaj użycia zatwierdzonych klawiatur w systemie Android<!--4761794 IDready -->
Będzie można określić listę zatwierdzonych klawiatur do użycia w zarządzanych aplikacjach systemu Android. W aplikacji zarządzanej użytkownik zostanie poproszony o przełączenie na jedną z zatwierdzonych klawiatur już zainstalowanych na urządzeniu lub, w razie potrzeby, będzie kierowany do Sklep Google Play, aby pobrać i skonfigurować jedną z zatwierdzonych klawiatur. Użytkownik będzie mógł edytować pola tekstowe w aplikacji zarządzanej, jeśli klawiatura aktywna jest jedną z zatwierdzonych klawiatur.

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices---3246388----"></a>Używanie certyfikatów PKCS z profilami sieci Wi-Fi na urządzeniach z systemem Windows 10 i nowszym<!-- 3246388  -->
Obecnie można uwierzytelniać profile sieci Wi-Fi systemu Windows przy użyciu certyfikatów protokołu SCEP (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **Windows 10 i nowszych** dla platformy > **Wi-Fi** dla Typ profilu > typ > **protokołu EAP** **przedsiębiorstwa** ). Będziesz mieć możliwość używania certyfikatów PKCS z profilami sieci Wi-Fi systemu Windows. Ta funkcja umożliwia użytkownikom uwierzytelnianie profilów sieci Wi-Fi przy użyciu nowych lub istniejących profilów certyfikatów PKCS w dzierżawie. 

Aby uzyskać więcej informacji o profilach sieci Wi-Fi, zobacz [Dodawanie ustawień Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Intune](../configuration/wi-fi-settings-windows.md).

Dotyczy:
- Windows 10 lub nowszym

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824----"></a>Nowe ustawienia ExchangeActiveSync podczas tworzenia profilu konfiguracji urządzenia poczty E-mail na urządzeniach z systemem iOS<!-- 4892824  --> 
Na urządzeniach z systemem iOS/iPadOS można skonfigurować łączność poczty e-mail w profilu konfiguracji urządzenia (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **iOS/iPadOS** dla platformy > **poczty e-mail** dla typu profilu). 

Dostępne będą nowe ustawienia ExchangeActiveSync, w tym:
- Wybierz usługi, które mają zostać zsynchronizowane (lub Zablokuj synchronizację), takie jak poczta e-mail, kalendarz i kontakty.
- Zezwalaj (lub Blokuj) użytkownikom na zmienianie ustawień synchronizacji dla tych usług na ich urządzeniach. 

Aby wyświetlić bieżące ustawienia, przejdź do [ustawień profilu poczty e-mail dla urządzeń z systemem iOS w usłudze Intune](../configuration/email-settings-ios.md).

Dotyczy:
- System iOS 13.0 i nowsze
- System iPadOS 13.0 i nowsze

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices---5353228----"></a>Uniemożliwiaj użytkownikom dodawanie osobistych kont Google do właściciela urządzenia z systemem Android Enterprise i urządzeń dedykowanych<!-- 5353228  -->
Będziesz mieć możliwość uniemożliwienia użytkownikom tworzenia osobistych kont Google na właścicielu urządzenia i dedykowanych urządzeniach z systemem Android (**Konfiguracja urządzeń** > **Profile** > **tworzenia profilu** > systemie **Android Enterprise** dla > **właściciel urządzenia tylko > ograniczenia dotyczące urządzeń** dla typu profilu > **Ustawienia użytkowników i kont**).

Aby wyświetlić bieżące ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md).

Dotyczy:
- Właściciel urządzenia z systemem Android Enterprise
- Dedykowane urządzenia z rozwiązaniem Android Enterprise

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile---5468501----"></a>Funkcja rejestrowania po stronie serwera dla poleceń Siri jest usuwana w profilu ograniczeń urządzenia z systemem iOS<!-- 5468501  -->
Na urządzeniach z systemem iOS można utworzyć profile ograniczeń dla urządzeń, które konfigurują rejestrowanie po stronie serwera dla poleceń Siri (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **iOS/iPadOS** dla platformy **Ograniczenia > urządzeń** dla typu profilu > **aplikacje wbudowane**). Ustawienie **Siri polecenia rejestrowania po stronie serwera** zostanie usunięte.

To ustawienie zostanie usunięte z konsoli administracyjnej usługi Intune. To ustawienie nie ma wpływu na urządzenie, mimo że istniejące zasady, które mają skonfigurowane to ustawienie, będą nadal wyświetlać ustawienie. Jeśli chcesz usunąć ustawienie z istniejących zasad, przejdź do zasad, wprowadź drobną edycję, Zapisz ją i zasady zostaną zaktualizowane.

Aby wyświetlić ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:
- iOS

<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami



### <a name="edit-device-name-value-for-autopilot-devices---2640074----"></a>Edytuj wartość nazwy urządzenia dla urządzeń z autopilotażem<!-- 2640074  -->
Będziesz w stanie edytować wartość nazwy urządzenia dla urządzeń z urządzeniami niewidocznymi w usłudze Azure AD. W tym celu przejdź do usługi **Intune** > **rejestracja urządzeń** > **rejestracja w systemie Windows** >  > **urządzeń** z **systemem Windows autopilotaż** > Wybierz urządzenie > zmienić wartość **nazwy urządzenia** w prawym okienku > **Zapisz**.

### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Edytuj wartość tagu grupy dla urządzeń z autopilotażem<!-- 4816775 -->
Będziesz w stanie edytować wartość **tagu grupy** dla urządzeń z autopilotażem:

1. Wybierz pozycję Usługa **Intune** > **rejestracja urządzeń** > **rejestracja w systemie Windows** >  > **urządzeń**z **systemem Windows** .
1. Wybierz urządzenie.
1. W okienku po prawej stronie Zmień wartość **tagu grupy** .
1. Wybierz pozycję **Zapisz**.

### <a name="target-macos-user-groups-to-require-jamf-management---4061739---"></a>Docelowa Grupa użytkowników macOS do wymagania zarządzania Jamf<!-- 4061739 -->
Będziesz mieć możliwość nawiązywania określonych grup użytkowników, aby wymagały zarządzania urządzeniami macOS przez Jamf. Ten element docelowy umożliwi zastosowanie integracji zgodności Jamf z podzbiorem urządzeń macOS, podczas gdy inne urządzenia będą nadal zarządzane przez usługę Intune. Określanie wartości docelowej umożliwia również stopniowe Migrowanie urządzeń użytkowników z jednego systemu zarządzania urządzeniami przenośnymi do drugiego.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Aplikacje usługi Intune

### <a name="improved-macos-enrollment-experience-in-company-portal---5074349----"></a>Ulepszona obsługa rejestracji macOS w Portal firmy<!-- 5074349  -->
Portal firmy dla środowiska rejestracji macOS będzie prostszy proces rejestracji, który będzie bardziej ściśle dopasowywany do Portal firmy środowiska rejestracji systemu iOS. Użytkownicy urządzeń będą widzieli następujące:  

* Elegancki interfejs użytkownika.  
* Ulepszona Lista kontrolna rejestracji.  
* Wyraźniejsze instrukcje dotyczące rejestrowania urządzeń.  
* Udoskonalone opcje rozwiązywania problemów.  

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorowanie i rozwiązywanie problemów

### <a name="centralized-audit-logs--5603185-5697164--"></a>Scentralizowane dzienniki inspekcji<!--5603185, 5697164-->
Nowe scentralizowane środowisko dziennika inspekcji zbiera dzienniki inspekcji dla wszystkich kategorii na jednej stronie. You'l być w stanie filtrować dzienniki, aby uzyskać dane, których szukasz. Aby wyświetlić dzienniki inspekcji, przejdź do obszaru **Administracja dzierżawy** > **dzienniki inspekcji**. Aby uzyskać więcej informacji, zobacz [nadchodzące zmiany w dziennikach inspekcji w usłudze Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Upcoming-change-to-Audit-logs-in-Intune/ba-p/1015858).

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

### <a name="duplicate-custom-or-built-in-roles---1081938---"></a>Zduplikowane role niestandardowe lub wbudowane<!-- 1081938 -->
Będziesz mieć możliwość kopiowania ról wbudowanych i niestandardowych. W tym celu przejdź do **ról** > usługi **Intune** > **wszystkie role** > wybierz rolę z listy > **Duplikuj**. Upewnij się, że wprowadzono nową nazwę, która jest unikatowa.

<!-- ***********************************************-->

## <a name="security"></a>Zabezpieczenia

### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529-idready---"></a>Używanie profilów certyfikatów PKCS do udostępniania urządzeń za pomocą certyfikatów<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529 IDready -->
Aby wystawiać certyfikaty dla urządzeń, będziesz mieć możliwość użycia profilu certyfikatu PKCS, rozszerzając na bieżącą obsługę certyfikatów opartych na użytkownikach. Certyfikaty oparte na urządzeniach będą obsługiwane na platformach z systemami Android, iOS i Windows oraz mogą być używane w profilach sieci Wi-Fi i VPN.

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


