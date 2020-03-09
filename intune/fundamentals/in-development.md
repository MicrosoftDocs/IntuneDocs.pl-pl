---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e099537bce6327e9a8991bc42f406e4abd3dfd2e
ms.sourcegitcommit: 6608dc70d01376e0cd90aa620a2fe01337f6a2f1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260235"
---
# <a name="in-development-for-microsoft-intune---march-2020"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — marzec 2020 r.

Aby ułatwić Ci przygotowanie i planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Oprócz informacji na tej stronie: 

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, publikujemy również dodatkowy wpis w centrum wiadomości usługi Office.
- Po wprowadzeniu funkcji w środowisku produkcyjnym — w wersji zapoznawczej lub ogólnie dostępnej — opis tej funkcji zostanie przeniesiony z tej strony na stronę [Co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!NOTE]
> Ta strona odzwierciedla nasze aktualne plany dotyczące funkcji usługi Intune, które zostaną wprowadzone w przyszłych wydaniach. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Ta strona nie zawiera opisu wszystkich funkcji będących w trakcie opracowywania.

**Kanał informacyjny RSS**: Dowiaduj się o aktualizacjach tej strony dzięki skopiowaniu i wklejeniu następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Przekierowywanie klipów internetowych do przeglądarki Microsoft Edge na urządzeniach z systemem iOS/iPadOS<!-- 5455276 -->
Klipy internetowe, które działają jako przypięte aplikacje internetowe na urządzeniach z systemem iOS/iPadOS, będą musiały zostać zaktualizowane. Nowo wdrożone klipy internetowe będą otwierane w przeglądarce Microsoft Edge, a nie w programie Intune Managed Browser, jeśli będzie to wymagane do otwarcia w chronionej przeglądarce. Istniejące klipy internetowe trzeba będzie skierować tak, aby były otwierane w przeglądarce Microsoft Edge, a nie Managed Browser.

### <a name="macos-and-ios-company-portal-updates---5779439-5780234----"></a>Aktualizacje aplikacji Portal firmy dla systemów macOS i iOS<!-- 5779439, 5780234  -->
Okienko Profil aplikacji Portal firmy dla systemów macOS i iOS zostanie zaktualizowane pod kątem obsługi przycisku wylogowania. Ponadto ta aktualizacja obejmie ulepszenia interfejsu użytkownika okienka Profil w aplikacji Portal firmy dla systemu macOS. Aby uzyskać więcej informacji na temat aplikacji Portal firmy, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).

### <a name="updates-to-branding-and-customization-pane---5236032---"></a>Aktualizacje okienka Znakowanie i dostosowywanie<!-- 5236032 -->
Ulepszamy okienko usługi Intune o obecnej nazwie „Znakowanie i dostosowywanie” w następujący sposób:

- Zmiana nazwy okienka na **Dostosowanie**.
- Ulepszenie organizacji i układu ustawień.
- Ulepszenie tekstu i etykietek narzędzi dla ustawień.

Aby znaleźć te ustawienia w usłudze Intune, przejdź do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), a następnie wybierz pozycję **Administracja dzierżawcza** > **Dostosowywanie**. Aby uzyskać więcej informacji na temat istniejących dostosowań, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).

### <a name="configure-the-ios-microsoft-azure-ad-sso-app-extension---567534----"></a>Konfigurowanie rozszerzenia aplikacji SSO usługi Microsoft Azure AD dla systemu iOS<!-- 567534  -->
Zespół usługi Microsoft Azure AD opracowuje rozszerzenie aplikacji do przekierowywania logowania jednokrotnego (SSO), aby umożliwić użytkownikom systemów iOS i iPadOS 13.0+ bezproblemowy dostęp do aplikacji i witryn internetowych firmy Microsoft za pomocą funkcji logowania jednokrotnego. Po wydaniu rozszerzenia aplikacji SSO dla usługi AAD rozszerzenie SSO będzie można skonfigurować paroma kliknięciami za pomocą profilu **Funkcje urządzenia** > **Rozszerzenie aplikacji logowania jednokrotnego** w konsoli administracyjnej. 

Aby uzyskać więcej informacji na temat rozszerzeń aplikacji SSO dla systemu iOS lub sposobu konfigurowania funkcji urządzenia, zobacz [Rozszerzenie aplikacji logowania jednokrotnego](~/configuration/device-features-configure.md#single-sign-on-app-extension).

### <a name="company-portal-for-ios-to-support-landscape-mode--6048329----"></a>Obsługa trybu poziomego w aplikacji Portal firmy dla systemu iOS<!--6048329  -->
Użytkownicy będą mogli rejestrować swoje urządzenia, znajdować aplikacje i uzyskiwać pomoc techniczną od działu IT przy użyciu wybranej orientacji ekranu. Aplikacja automatycznie wykrywa i dostosowuje ekrany do trybu pionowego lub poziomego, chyba że użytkownik zablokuje ekran w trybie pionowym. 

### <a name="configure-if-enrollment-is-available-in-company-portal-for-android-and-ios---4260128-idready-idstaged---"></a>Konfigurowanie dostępności rejestracji w aplikacji Portal firmy dla systemów Android i iOS<!-- 4260128 idready idstaged -->
Będzie dostępne nowe ustawienie, które umożliwia skonfigurowanie, czy rejestrowanie urządzeń w aplikacji Portal firmy na urządzeniach z systemem Android lub iOS jest dostępne z monitami, dostępne bez monitów, czy niedostępne dla użytkowników. Aby znaleźć te ustawienia w usłudze Intune, przejdź do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), a następnie wybierz pozycję **Administracja dzierżawcza** > **Dostosowywanie** > **Edytuj** > **Rejestracja urządzenia**. Aby uzyskać więcej informacji na temat istniejących dostosowań aplikacji Portal firmy, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).

### <a name="improved-sign-in-experience-in-company-portal-for-android---6103997----"></a>Ulepszone środowisko logowania w aplikacji Portal firmy dla systemu Android<!-- 6103997  -->
Aktualizujemy układ kilku ekranów logowania w aplikacji Portal firmy dla systemu Android, aby zapewnić użytkownikom nowocześniejsze, prostsze i czytelniejsze środowisko.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profile konfiguracji urządzeń sieci przewodowej dla urządzeń z systemem macOS<!-- 3508686  -->
Zostanie udostępniony nowy profil konfiguracji urządzenia z systemem macOS, który konfiguruje sieci przewodowe (**Konfiguracja urządzenia**  >  **Profile**  >  **Utwórz profil**  >  **macOS** dla platformy > **Sieć przewodowa** dla typu profilu). Użyj tej funkcji, aby utworzyć profile 802.1x w celu zarządzania sieciami przewodowymi, i wdróż te sieci przewodowe na urządzeniach z systemem macOS.

Dotyczy:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932----"></a>Profile sieci VPN z połączeniami sieci VPN z protokołem IKEv2 mogą używać funkcji Zawsze włączone na urządzeniach z systemem iOS/iPadOS <!-- 1947932  -->
Na urządzeniach z systemem iOS/iPadOS można utworzyć profil sieci VPN, który używa połączenia IKEv2 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** jako platforma > **VPN** jako typ profilu). W przyszłej aktualizacji będzie można skonfigurować funkcję Zawsze włączone przy użyciu protokołu IKEv2. Po skonfigurowaniu profile sieci VPN IKEv2 łączą się automatycznie i pozostają połączone (lub szybko ponownie nawiązują połączenie) z siecią VPN. Pozostają one połączone nawet podczas przechodzenia między sieciami lub ponownego uruchamiania urządzeń.

W systemie iOS/iPadOS zawsze włączona sieć VPN jest ograniczona do profilów IKEv2.

Aby wyświetlić bieżące ustawienia profilów IKEv2, które możesz skonfigurować, przejdź do tematu [Dodawanie ustawień sieci VPN na urządzeniach z systemem iOS/iPadOS w usłudze Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Dotyczy:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984----"></a>Ulepszony interfejs użytkownika podczas tworzenia profilów konfiguracji na urządzeniach z systemami iOS/iPadOS i macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984  -->
Środowisko tworzenia profilu dla urządzeń z systemem iOS/iPadOS lub macOS w centrum administracyjnym zarządzania punktem końcowym zostanie zaktualizowane. Ta zmiana ma wpływ na następujące profile konfiguracji urządzeń (**Urządzenia**  >  **Profile konfiguracji**  >  **Utwórz profil**  >  **iOS** lub **macOS** dla platformy):

- Niestandardowe: iOS/iPadOS, macOS
- Funkcje urządzenia: iOS/iPadOS, macOS
- Ograniczenia urządzeń: iOS/iPadOS, macOS
- Ochrona punktu końcowego: macOS
- Rozszerzenia: macOS
- Plik preferencji: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-----"></a>Ulepszony interfejs użytkownika podczas tworzenia profilów konfiguracji OEMConfig na urządzeniach z systemem Android Enterprise<!-- 5568645   -->
Zaktualizowano środowisko tworzenia i edytowania profilu OEMConfig dla urządzeń z systemem Android Enterprise w centrum administracyjnym zarządzania punktami końcowymi. Zaktualizowane środowisko zawiera podsumowanie ustawień, które zostały skonfigurowane. Ta zmiana ma wpływ na profil konfiguracji urządzenia OEMConfig (**Urządzenia**  >  **Profile konfiguracji**  >  **Utwórz profil**  >  **Android Enterprise** dla platformy > **OEMConfig** dla typu profilu).

Ta funkcja ma zastosowanie do:
- Android Enterprise 

### <a name="enterprise-app-trust-settings-modification-setting-will-be-removed-from-iosipados-device-restriction-profiles---6225131----"></a>Ustawienia zaufania aplikacji dla przedsiębiorstw zostaną usunięte z profilów ograniczeń urządzenia z systemem iOS/iPadOS<!-- 6225131  -->
Na urządzeniach z systemem iOS/iPadOS można utworzyć profil ograniczeń urządzenia (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil** > **System iOS/iPadOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ustawienie **Modyfikacja ustawień zaufania aplikacji dla przedsiębiorstw** zostanie usunięte przez firmę Apple i z usługi Intune. Jeśli obecnie używasz tego ustawienia w profilu, pozostanie ono bez zmian w profilu do momentu utworzenia nowego profilu. To ustawienie zostanie również usunięte ze wszystkich raportów w usłudze Intune.

Dotyczy:
- iOS/iPadOS

Aby wyświetlić ustawienia, które można ograniczyć, zobacz [Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie](../configuration/device-restrictions-ios.md).

### <a name="device-configuration-profile-settings-and-values-will-be-updated-for-windows-platforms---4091122---"></a>Ustawienia i wartości profilu konfiguracji urządzenia zostaną zaktualizowane dla platform systemu Windows<!-- 4091122 -->
Podczas tworzenia profilów konfiguracji urządzeń dla platform systemu Windows (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil** > dowolna opcja dla platformy systemu **Windows**) niektóre ustawienia i ich wartości różnią się w zależności od dostawcy usługi konfiguracji, co może być mylące. Nazwy ustawień i ich wartości zostaną zaktualizowane, tak aby były bardziej oczywiste.

Dotyczy:

- Profile konfiguracji urządzeń z systemem Windows 10 i nowszymi
- Profile konfiguracji urządzeń z systemem Windows Holographic for Business
- Profile konfiguracji urządzeń z systemem Windows 8.1
- Profile konfiguracji urządzeń z systemem Windows Phone 8.1

### <a name="improved-user-interface-experience-when-creating-device-restrictions-profiles-on-android-and-android-enterprise-devices---5841361---"></a>Ulepszony interfejs użytkownika podczas tworzenia profilów ograniczeń urządzenia na urządzeniach z systemem Android lub rozwiązaniem Android Enterprise<!-- 5841361 -->
Środowisko centrum administracyjnego zarządzania punktami końcowymi używane podczas tworzenia profilu dla urządzeń z systemem Android lub rozwiązaniem Android Enterprise zostanie zaktualizowane. Ta zmiana ma wpływ na następujące profile konfiguracji urządzenia (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil** > **Administrator urządzeń z systemem Android** lub **rozwiązaniem Android Enterprise** dla platformy):

- Ograniczenia dotyczące urządzeń: Administrator urządzenia z systemem Android
- Ograniczenia dotyczące urządzeń: Właściciel urządzenia z systemem Android Enterprise
- Ograniczenia dotyczące urządzeń: Android Enterprise — profil służbowy

Aby uzyskać więcej informacji na temat ograniczeń urządzeń, które można skonfigurować, zobacz [Administrator urządzeń z systemem Android](../configuration/device-restrictions-android.md) i [rozwiązaniem Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="delete-bundles-and-bundle-arrays-in-oemconfig-device-configuration-profiles-on-android-enterprise-devices---5550355----"></a>Usuwanie pakietów i tablic pakietów z profilów konfiguracji urządzeń OEMConfig na urządzeniach z rozwiązaniem Android Enterprise<!-- 5550355  -->
Na urządzeniach z rozwiązaniem Android Enterprise można tworzyć i aktualizować profile OEMConfig. Użytkownicy będą mogli usuwać pakiety i tablice pakietów przy użyciu **projektanta konfiguracji** w usłudze Intune.

Aby uzyskać więcej informacji o profilach OEMConfig, zobacz [Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig](../configuration/android-oem-configuration-overview.md) w usłudze Microsoft Intune.

Ta funkcja ma zastosowanie do:
- Android Enterprise

### <a name="support-for-wpa-and-wpa2-in-ios-enterprise-wi-fi-profiles--6215273-----"></a>Obsługa protokołów WPA i WPA2 w profilach sieci Wi-Fi w systemie iOS Enterprise<!--6215273   -->
Dodajemy pole *Typ zabezpieczeń* do pozycji [Profile sieci Wi-Fi dla firm w systemie iOS](../configuration/wi-fi-settings-ios.md) (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil** i wybierz opcję **iOS/iPadOS** dla pozycji *Platforma*, a następnie opcję **Sieć Wi-Fi** dla pozycji *Profil*). Jest ono podobne do opcji dostępnych dla pozycji Podstawowy profil sieci Wi-Fi dla systemu iOS. Dzięki tej zmianie będzie można utworzyć nowe profile określające typ zabezpieczeń dla pozycji **WPA-Enterprise** lub **WPA/WPA2-Enterprise**, a następnie określić wybór dla pozycji *Typ protokołu EAP*.

### <a name="new-user-experience-for-certificate-email-vpn-and-wi-fi-profiles---5615208-----"></a>Nowe środowisko użytkownika dla certyfikatów, poczty e-mail, sieci VPN i profilów sieci Wi-Fi<!-- 5615208   -->
Aktualizujemy [środowisko użytkownika](../configuration/device-profile-create.md) w centrum administracyjnym zarządzania punktami końcowymi (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil**) na potrzeby tworzenia i modyfikowania następujących typów profilów. Nowe środowisko będzie udostępniać te same ustawienia co wcześniejsze, lecz za pomocą interfejsu użytkownika przypominającego kreatora, który nie wymaga takiej ilości przewijania w poziomie. Nie trzeba będzie modyfikować istniejących konfiguracji przy użyciu nowego środowiska.
- Pochodne poświadczenia
- Poczta e-mail
- Certyfikat PKCS
- Zaimportowany certyfikat PKCS
- Certyfikat SCEP
- Zaufany certyfikat
- VPN
- Wi-Fi

(**Urządzenia** > **Profile konfiguracji** > **Utwórz profil**, a następnie dla pozycji *Typ profilu* wybierz dowolny z powyższych profilów).

### <a name="configure-the-microsoft-defender-atp-app-for-macos-----5520115----"></a>Konfigurowanie aplikacji Microsoft Defender ATP dla systemu macOS  <!-- 5520115  -->
Wkrótce będzie można skonfigurować [ustawienia](../protect/endpoint-protection-macos.md) dla aplikacji Microsoft Defender ATP na urządzeniach z systemem macOS w ramach profilu konfiguracji urządzenia z programem Endpoint Protection (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil**, wybierz opcję **macOS**dla pozycji *Platforma*, a następnie opcję **Endpoint Protection** dla pozycji *Typ profilu*). Dla konfiguracji urządzenia z systemem macOS będzie dostępnych osiem ustawień. 

Aplikacja Defender ATP jest obsługiwana w systemie macOS 10.13 (High Sierra) i nowszych, a aplikację [Microsoft Defender ATP](../apps/apps-advanced-threat-protection-macos.md) należy wdrożyć na urządzeniu *po* zastosowaniu tych ustawień. Ustawienia należy wysłać do urządzenia przed wdrożeniem aplikacji. Wersje beta systemu macOS nie będą obsługiwane.

### <a name="new-filevault-setting-for-macos-endpoint-protection-device-configuration-policy---5459801-----"></a>Nowe ustawienie programu FileVault dla zasad konfiguracji urządzeń z programem Endpoint Protection w systemie macOS<!-- 5459801   -->
Dodajemy nowe ustawienie do kategorii FileVault w szablonie [programu Endpoint Protection dla systemu macOS](../protect/endpoint-protection-macos.md): Ukryj klucz odzyskiwania. (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil**, wybierz opcję **macOS** dla pozycji *Platforma*, a następnie opcję **Ochrona punktu końcowego** dla pozycji *Typ profilu*). To ustawienie ukrywa klucz osobisty przed użytkownikiem końcowym podczas szyfrowania za pomocą programu FileVault 2. Użytkownik urządzenia może w dowolnym momencie wyświetlić swój osobisty klucz odzyskiwania dla zaszyfrowanego urządzenia z systemem macOS z poziomu aplikacji Portal firmy dla systemu iOS lub witryny internetowej portalu firmy. Aby wyświetlić osobisty klucz odzyskiwania, należy przejść do szczegółów urządzenia i kliknąć pozycję *Pobierz klucz odzyskiwania*.

To ustawienie nie będzie dostępne w zasadach utworzonych wcześniej. Należy utworzyć ponownie zasady programu FileVault, aby skonfigurować to ustawienie w celu jego użycia. 

###  <a name="ui-update-when-configuring-compliance-policy----3961639----"></a>Aktualizacja interfejsu użytkownika dla konfigurowania zasad zgodności <!-- 3961639  -->
Aktualizujemy interfejs użytkownika służący do konfigurowania zasad zgodności w programie Microsoft Endpoint Manager (**Urządzenia** > **Zasady zgodności** > **Zasady** > **Utwórz zasady**). Zobaczysz nowe środowisko użytkownika, które udostępnia te same ustawienia i szczegóły, co używane poprzednio. Nowe środowisko będzie obsługiwać proces podobny do kreatora na potrzeby tworzenia zasad zgodności, w tym stronę, na której można dodać *przypisania* dla zasad, a następnie stronę *Podsumowanie*, na której można przejrzeć konfigurację przed utworzeniem zasad. 

### <a name="configure-delivery-optimization-agent-when-downloading-win32-app-content---5410945----"></a>Konfigurowanie agenta optymalizacji dostarczania podczas pobierania zawartości aplikacji Win32<!-- 5410945  -->
Będzie można skonfigurować agenta optymalizacji dostarczania pod kątem pobierania zawartości aplikacji Win32 w tle lub na pierwszym planie na podstawie przypisania. W przypadku istniejących aplikacji Win32 zawartość będzie nadal pobierana w tle. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**. Wybierz pozycję **Windows 10 i nowsze** w polu **Platforma**. W polu **Typ profilu** wybierz pozycję **Optymalizacja dostarczania**. Aby uzyskać więcej informacji na temat optymalizacji dostarczania, zobacz [Zarządzanie aplikacjami Win32 — optymalizacja dostarczania](~/apps/apps-win32-app-management.md#delivery-optimization).


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Zmienianie użytkownika podstawowego dla urządzeń z systemem Windows <!-- 3794742 -->
Będzie można zmieniać użytkownika podstawowego dla urządzeń hybrydowych z systemem Windows i urządzeń przyłączonych do usługi Azure AD. Aby to zrobić, przejdź do pozycji **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości** > **Użytkownik podstawowy**. 

### <a name="new-android-report-on-android-devices-overview-page---5435435---"></a>Nowy raport systemu Android na stronie przeglądu urządzeń z systemem Android<!-- 5435435 -->
W konsoli administracyjnej programu Microsoft Endpoint Manager na stronie przeglądu urządzeń z systemem Android dodamy raport, który zawiera informację o liczbie urządzeń z systemem Android zarejestrowanych w poszczególnych rozwiązaniach do zarządzania urządzeniami. Ten wykres (tak jak ten sam wykres już dostępny w konsoli platformy Azure) przedstawia liczbę urządzeń z profilami służbowymi, w pełni zarządzanych, dedykowanych i zarejestrowanych przez administratora urządzeń. Aby wyświetlić raport, wybierz pozycję **Urządzenia** > **Android** > **Przegląd**.

### <a name="powershell-scripts-support-for-byod-devices---1862833----"></a>Obsługa skryptów programu PowerShell dla urządzeń BYOD<!-- 1862833  -->
Skrypty programu PowerShell będą obsługiwać urządzenia zarejestrowane w usłudze Azure AD w usłudze Intune. Aby uzyskać więcej informacji o programie PowerShell, zobacz [Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune](~/apps/intune-management-extension.md). Ta funkcja nie obsługuje urządzeń z systemem Windows 10 Home.

### <a name="additional-data-warehouse-device-inventory-properties---6125732----"></a>Dodatkowe właściwości spisu urządzeń usługi Data Warehouse<!-- 6125732  -->
Dodatkowe właściwości spisu urządzeń będą dostępne przy użyciu usługi Intune Data Warehouse. Następujące właściwości zostaną uwidocznione za pośrednictwem kolekcji [devices](~/developer/intune-data-warehouse-collections.md#devices):
- Pojemność magazynu 
- Pojemność pamięci
- Wersja pakietu Office 365
- Model urządzenia

Aby uzyskać więcej informacji na temat usługi Data Warehouse, zobacz [Interfejs API usługi Microsoft Intune Data Warehouse](~/developer/reports-nav-intune-data-warehouse.md).

### <a name="guide-users-from-android-device-administrator-management-to-work-profile-management--5857738--"></a>Przewodnik dla użytkowników dotyczący przejścia z zarządzania przez administratora urządzeń z systemem Android na zarządzanie przy użyciu profilów służbowych<!--5857738-->
Wydajemy nowe ustawienie dotyczące platformy administratora urządzeń z systemem Android. To ustawienie umożliwia określenie urządzenia jako niezgodnego, jeśli jest ono zarządzane przez administratora urządzeń.

Na tych niezgodnych urządzeniach na stronie **Aktualizowanie ustawień urządzenia** użytkownicy zobaczą komunikat **Przechodzenie na nową konfigurację zarządzania urządzeniem**. Jeśli użytkownik naciśnie przycisk **Rozwiąż**, zostanie przeprowadzony przez:

1. Wyrejestrowanie z funkcji zarządzania przez administratora urządzeń
2. Rejestrowanie w funkcji zarządzania za pomocą profilów służbowych
3. Rozwiązywanie problemów ze zgodnością 
 
Dążąc do przejścia do nowoczesnego, bardziej zaawansowanego i bezpieczniejszego zarządzania urządzeniami w rozwiązaniu Android Enterprise, firma Google ogranicza wsparcie administratora urządzeń w nowych wersjach systemu Android.  Usługa Intune będzie w stanie w pełni obsługiwać urządzenia z systemem Android 10 i nowszymi zarządzanym przez administratora urządzeń tylko do 2. kwartału 2020 r. Urządzenia zarządzane przez administratora urządzeń z systemem Android 10 lub nowszym (z wyjątkiem urządzeń firmy Samsung) po tym terminie nie będą mogły być już w pełni zarządzane. W szczególności objęte urządzenia nie będą otrzymywać nowych wymagań dotyczących haseł. Aby uzyskać więcej informacji, zobacz [uwagi](#decreasing-support-for-android-device-administrator).

### <a name="retire-noncompliant-devices---1827291---"></a>Wycofywanie niezgodnych urządzeń<!-- 1827291 -->
Dodajemy nową opcjonalną akcję zgodności w celu wycofania niezgodnego urządzenia (**Urządzenia** > **Zasady zgodności** > **Zasady** > **Utwórz zasady**, a następnie wyświetl dostępną pozycję *Akcje* na stronie *Akcje dotyczące niezgodności*).  Wycofanie niezgodnego urządzenia spowoduje usunięcie z niego wszystkich danych firmowych, a następnie usunięcie urządzenia z listy urządzeń zarządzanych przez usługę Intune. Ta akcja będzie uruchamiana po osiągnięciu skonfigurowanej wartości w dniach. Wartość minimalna to 30 dni.  Wycofanie urządzeń przy użyciu sekcji *Wycofywanie niezgodnych urządzeń*, gdzie administratorzy mogą wycofać wszystkie kwalifikujące się urządzenia, będzie wymagać jawnego zatwierdzenia przez administratora IT.

### <a name="new-information-in-device-details---5604099---"></a>Nowe informacje w obszarze szczegółów urządzenia<!-- 5604099 -->
Strona **Przegląd** dla urządzeń będzie zawierać następujące informacje:
- Pojemność magazynu (wielkość magazynu fizycznego w urządzeniu)
- Pojemność pamięci (ilość pamięci fizycznej w urządzeniu)

### <a name="script-support-for-macos-devices---4280361----"></a>Obsługa skryptów dla urządzeń z systemem macOS<!-- 4280361  -->
Będzie można dodawać i wdrażać skrypty na urządzeniach z systemem macOS. Ta obsługa rozszerza możliwości konfigurowania urządzeń z systemem macOS poza natywne możliwości MDM oferowane na urządzeniach z systemem macOS. 

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
## <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

### <a name="help-and-support-workflow-update-to-support-additional-services---5654170---"></a>Aktualizacja przepływu pracy pomocy i pomocy technicznej w celu obsługi dodatkowych usług<!-- 5654170 -->
Aktualizujemy stronę pomocy i pomocy technicznej w centrum administracyjnym programu Microsoft Endpoint Manager, dzięki czemu będzie można wybrać używany typ zarządzania, co pozwoli na lepsze zapewnianie pomocy technicznej (**Rozwiązywanie problemów i pomoc techniczna** >  **Pomoc i obsługa techniczna**). Dzięki tej zmianie będzie można wybrać spośród następujących typów zarządzania:
- Program Configuration Manager (obejmuje usługę Desktop Analytics)
- Intune
- Współzarządzanie

<!-- ***********************************************-->
<!--
## Role-based access control
-->

<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Obsługa poświadczeń pochodnych na urządzeniach z systemem Android COBO<!--4839592-->
W pełni zarządzane urządzenia z systemem Android Enterprise będą mogły korzystać z poświadczeń pochodnych. Obsługa zostanie uwzględniona w przypadku pobierania poświadczeń pochodnych dla firm Entrust Datacard, Intercede i DISA Purebred. Będzie można użyć poświadczeń pochodnych na potrzeby uwierzytelniania aplikacji, sieci Wi-Fi, sieci VPN lub podpisywania S/MIME i/lub szyfrowania przy użyciu aplikacji, które je obsługują.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Używanie zasad ochrony antywirusowej do zarządzania ustawieniami programu Microsoft Defender Antivirus i środowiskiem zabezpieczeń systemu Windows<!--6131401 -->
W węźle *Zabezpieczenia punktu końcowego* będzie można skonfigurować ustawienia **Ochrona antywirusowa**. Konfigurując zasady ochrony antywirusowej, można zdefiniować ustawienia dla urządzeń z systemem Windows 10 przy użyciu dwóch typów profilów:

- Program antywirusowy Microsoft Defender: zarządzanie ustawieniami ochrony chmury, wykluczeń ochrony antywirusowej, korygowania, opcji skanowania i innymi.
- Środowisko zabezpieczeń systemu Windows: zarządzanie sposobem korzystania przez użytkowników z ustawień zabezpieczeń systemu Windows na urządzeniach. Będzie można skonfigurować elementy, które użytkownicy końcowi mogą wyświetlać w Centrum zabezpieczeń usługi Microsoft Defender, i otrzymywane przez nich powiadomienia.

### <a name="users-personal-encrypted-recovery-key---6273943---"></a>Osobisty zaszyfrowany klucz odzyskiwania użytkownika<!-- 6273943 -->
Dostępna będzie nowa funkcja usługi Intune, która umożliwia użytkownikom pobranie ich osobistego zaszyfrowanego klucza odzyskiwania programu **FileVault** na urządzeniach Mac za pomocą aplikacji Portal firmy dla systemu Android lub aplikacji usługi Intune dla systemu Android. W aplikacji Portal firmy i aplikacji usługi Intune będzie dostępny link otwierający w przeglądarce Chrome internetowy portal firmy, gdzie użytkownik będzie mógł zobaczyć klucz odzyskiwania programu **FileVault** wymagany do uzyskania dostępu do urządzeń Mac. Aby uzyskać więcej informacji na temat szyfrowania, zobacz [Używanie szyfrowania urządzenia za pomocą usługi Intune](~/protect/encrypt-devices.md).

### <a name="privacy-preferences-settings-for-macos-devices---2934232---"></a>Ustawienia preferencji prywatności dla urządzeń z systemem macOS<!-- 2934232 --> 
Wraz z wydaniem systemu macOS Catalina 10.15 firma Apple dodała nowe ulepszenia zabezpieczeń i ochrony prywatności. Domyślnie aplikacje i procesy nie mogą uzyskać dostępu do określonych danych bez zgody użytkownika. Jeśli użytkownik nie udzieli zgody, aplikacje i procesy mogą nie działać. Usługa Intune dodaje obsługę ustawień, które umożliwiają administratorom IT zezwalanie na udzielanie zgody lub blokowanie udzielania zgody na dostęp do danych w imieniu użytkowników końcowych na urządzeniach z systemem macOS 10.14 lub nowszym. Te ustawienia zapewnią, że aplikacje i procesy będą nadal działać prawidłowo, oraz zmniejszą liczbę monitów wyświetlanych użytkownikom końcowym. 

### <a name="updated-ui-text-and-labels-for-windows-10-endpoint-protection-profile-settings---5983747---"></a>Zaktualizowano tekst i etykiety interfejsu użytkownika dla ustawień profilu programu Endpoint Protection w systemie Windows 10<!-- 5983747 -->
Aktualizujemy tekst dla różnych ustawień konfigurowanych w ramach profilów konfiguracji urządzeń z systemem Windows 10, aby ułatwić zrozumienie przeznaczenia i działania ustawień. 

Aktualizowane ustawienia obejmują profile konfiguracji urządzeń z systemem Windows 10 dla następujących elementów: 
- [Ograniczenia urządzeń](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) > program antywirusowy Microsoft Defender  
- [Endpoint Protection](../protect/endpoint-protection-windows-10.md) > program antywirusowy Microsoft Defender

Ustawienia obsługiwane przez usługę Intune nie są zmieniane. Jest to tylko aktualizacja tekstu interfejsu użytkownika w centrum administracyjnym programu Microsoft Endpoint Management. 


<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



