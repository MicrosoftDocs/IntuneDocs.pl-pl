---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f46b8c7f0f57ab7831d6487495946aa9326b2d5
ms.sourcegitcommit: 24487f078349795922dc497c952e8358cf767a1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "76977788"
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz tu również znaleźć [ważne powiadomienia](#notices), [poprzednie wydania](whats-new-archive.md) oraz informacje na temat [sposobu wydawania aktualizacji usługi Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Wprowadzanie każdej [aktualizacji miesięcznej](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) może potrwać do trzech dni i będzie przeprowadzane w następującej kolejności:
>
> - 1\. dzień: Azja i Pacyfik
> - 2\. dzień: Europa, Bliski Wschód i Afryka
> - 3\. dzień: Ameryka Północna
> - 4\. dzień i kolejne: Usługa Intune dla instytucji rządowych
>
> Niektóre funkcje mogą być wprowadzane przez kilka tygodni i nie być dostępne dla wszystkich klientów w pierwszym tygodniu.
>
> Listę przyszłych funkcji w wydaniu można znaleźć na stronie [W trakcie opracowywania](in-development.md).

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control
-->  

<!-- ########################## -->
## <a name="week-of-february-03-2020"></a>Tydzień od 03 lutego 2020 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="company-portal-app-improved-performance---6178652---"></a>Ulepszona wydajność aplikacji Portal firmy<!-- 6178652 -->
Aplikacja Portal firmy została zaktualizowana w celu obsługi ulepszonej wydajności urządzeń z procesorami ARM64, takich jak Surface Pro X. Wcześniej aplikacja Portal firmy działała w trybie emulacji procesora ARM32. Teraz aplikacja Portal firmy jest natywnie skompilowana dla procesora ARM64. Aby uzyskać więcej informacji na temat aplikacji Portal firmy, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).

<!-- ########################## -->
## <a name="week-of-january-27-2020"></a>Tydzień od 27 stycznia 2020 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="new-setting-to-remove-specific-windows-built-in-apps---6184390---"></a>Nowe ustawienie do usuwania określonych wbudowanych aplikacji systemu Windows<!-- 6184390 -->
Używając nowego ustawienia zasad konfiguracji urządzenia z systemem Windows 10, można usunąć następujące wbudowane aplikacje systemu Windows:

- Przeglądarka rzeczywistości mieszanej
- MSN Pogoda
- Instalator aplikacji
- Wskazówki Microsoft
- Mój Office
- Microsoft Solitaire Collection 
- Plany komórkowe
- Centrum opinii 
- Xbox 
- Muzyka Groove
- Mail
- Kalendarz

W centrum administracyjnym programu Microsoft Endpoint Manager wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**. Następnie wybierz pozycję **Windows 10 i nowsze** w polu **Platforma**. Wybierz pozycję **Ograniczenia dotyczące urządzeń** w polu **Typ profilu**. Wybierz pozycję **App Store** w okienku **Ograniczenia dotyczące urządzeń**. W dolnej części okienka obok pozycji **Usuń aplikacje wbudowane** wybierz pozycję **Usuń**. Aby uzyskać więcej informacji na temat aplikacji wbudowanych, zobacz [Dodawanie aplikacji wbudowanych do usługi Microsoft Intune](~/apps/apps-add-built-in.md).

#### <a name="intune-support-for-additional-microsoft-edge-version-77-deployment-channel-for-macos---5983950----"></a>Obsługa usługi Intune dla dodatkowego kanału wdrażania programu Microsoft Edge w wersji 77 dla systemu macOS<!-- 5983950  -->
Usługa Microsoft Intune obsługuje teraz dodatkowy kanał wdrażania **Stabilne** dla aplikacji Microsoft Edge dla systemu macOS. Kanał **Stabilne** to zalecany kanał do szerokiego wdrażania programu Microsoft Edge w środowisku przedsiębiorstwa. Jest aktualizowany co sześć tygodni, a każda wersja zawiera ulepszenia z kanału **Beta**. Oprócz kanałów **Stabilne** i **Beta**, usługa Intune obsługuje kanał **Deweloperzy**. Publiczna wersja zapoznawcza oferuje kanał stabilny i kanał dla deweloperów dla aplikacji Microsoft Edge w wersji 77 lub nowszej dla systemu macOS. Automatyczne aktualizacje przeglądarki są domyślnie włączone. Aby uzyskać więcej informacji, zobacz [Dodawanie przeglądarki Microsoft Edge na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune](~/apps/apps-edge-macos.md).

#### <a name="retirement-of-intune-managed-browser--5728447---"></a>Wycofanie przeglądarki Intune Managed Browser<!--5728447 -->
Przeglądarka Intune Managed Browser zostanie wycofana. W celu zapewnienia chronionego środowiska przeglądarki w usłudze Intune należy używać przeglądarki Microsoft Edge. Aby uzyskać więcej informacji, zobacz wpis „[Wymagane działanie: W celu zapewnienia chronionego środowiska przeglądarki w usłudze Intune należy używać przeglądarki Microsoft Edge](~/fundamentals/whats-new.md#take-action-use-microsoft-edge-for-your-protected-intune-browser-experience)” w sekcji [Uwagi](~/fundamentals/whats-new.md#notices) poniżej.

<!-- ########################## -->
## <a name="week-of-january-20-2020-2001-service-release"></a>Tydzień od 20 stycznia 2020 r. (wersja usługi 2001)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="user-experience-change-when-adding-apps-to-intune---4705829-----"></a>Zmiana środowiska użytkownika podczas dodawania aplikacji do usługi Intune<!-- 4705829   -->
Podczas dodawania aplikacji do usługi Intune dostępne jest nowe środowisko użytkownika. To środowisko zawiera te same ustawienia i szczegółowe informacje, które były używane wcześniej, jednak nowe środowisko korzysta z procesu przypominającego kreator przed dodaniem aplikacji do usługi Intune. To nowe środowisko udostępnia również stronę przeglądu przed dodaniem aplikacji. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](~/apps/apps-add.md).

#### <a name="require-win32-apps-to-restart----5622282-----"></a>Wymaganie ponownego uruchomienia aplikacji Win32 <!-- 5622282   -->
Po pomyślnym zainstalowaniu aplikacji Win32 można wymagać jej ponownego uruchomienia. Ponadto można wybrać czas (okres prolongaty), jaki może upłynąć, zanim nastąpi ponowne uruchomienie.

#### <a name="user-experience-change-when-configuring-apps-in-intune---4207990-----"></a>Zmiana środowiska użytkownika podczas konfigurowania aplikacji w usłudze Intune<!-- 4207990   -->
Podczas tworzenia zasad konfiguracji aplikacji w usłudze Intune dostępne jest nowe środowisko użytkownika. To środowisko zawiera te same ustawienia i szczegółowe informacje, które były używane wcześniej, jednak nowe środowisko korzysta z procesu przypominającego kreator przed dodaniem zasad do usługi Intune. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj**. Aby uzyskać więcej informacji, zobacz [Zasady konfiguracji aplikacji usługi Microsoft Intune](~/apps/app-configuration-policies-overview.md). 

#### <a name="intune-support-for-additional-microsoft-edge-for-windows-10-deployment-channel---5861774---"></a>Obsługa usługi Intune dla dodatkowego kanału wdrażania programu Microsoft Edge dla systemu Windows 10<!-- 5861774 -->
Usługa Microsoft Intune obsługuje teraz dodatkowy kanał wdrażania **Stabilne** dla aplikacji Microsoft Edge (w wersji 77 lub nowszej) dla aplikacji systemu Windows 10. Kanał **Stabilne** to zalecany kanał do szerokiego wdrażania programu Microsoft Edge dla systemu Windows 10 w środowisku przedsiębiorstwa. Ten kanał jest aktualizowany co sześć tygodni, a każda wersja zawiera ulepszenia z kanału **Beta**. Oprócz kanałów **Stabilne** i **Beta**, usługa Intune obsługuje kanał **Deweloperzy**. Aby uzyskać więcej informacji, zobacz [Microsoft Edge dla systemu Windows 10 — Konfigurowanie ustawień aplikacji](~/apps/apps-windows-edge.md#configure-app-settings).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="improved-user-interface-experience-when-configuring-exchange-activesync-on-premises-connector-ui---5695492-----"></a>Ulepszone środowisko interfejsu użytkownika podczas konfigurowania interfejsu użytkownika lokalnego łącznika programu Exchange ActiveSync<!-- 5695492   -->
Zaktualizowaliśmy środowisko dla [konfigurowania lokalnego łącznika programu Exchange ActiveSync](../protect/exchange-connector-install.md). Zaktualizowane środowisko używa jednego okienka do konfigurowania, edytowania i podsumowywania szczegółów łączników lokalnych. 

#### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-----"></a>Dodawanie automatycznych ustawień serwera proxy do profilów sieci Wi-Fi dla profilów służbowych systemu Android Enterprise<!-- 4490822   -->
Na urządzeniach z profilami służbowymi systemu Android Enterprise można tworzyć profile sieci Wi-Fi. Po wybraniu typu firmowej sieci Wi-Fi można także wprowadzić typ protokołu uwierzytelniania rozszerzonego (EAP, Extensible Authentication Protocol) używanego w sieci Wi-Fi.

Teraz po wybraniu typu firmowego można także wprowadzić automatyczne ustawienia serwera proxy, w tym adres URL serwera proxy, taki jak `proxy.contoso.com`.

Aby zobaczyć bieżące ustawienia sieci Wi-Fi, które można skonfigurować, przejdź do tematu [Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem Android Enterprise i kiosku systemu Android w usłudze Microsoft Intune](../configuration/wi-fi-settings-android-enterprise.md).

Dotyczy:
- Android Enterprise — profil służbowy

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="block-android-enrollments-by-device-manufacturer--5197392----"></a>Blokowanie rejestrowania systemu Android według producenta urządzenia<!--5197392  -->
Można zablokować możliwość rejestrowania urządzeń na podstawie producenta urządzenia. Dotyczy to administratora urządzenia z systemem Android i urządzeń z profilem służbowym systemu Android Enterprise. Aby zobaczyć ograniczenia rejestrowania, przejdź do obszaru [Centrum administracyjne usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Urządzenia** > **Ograniczenia rejestracji**.

#### <a name="improvements-to-the-iosipados-create-enrollment-type-profile-ui---6055005---"></a>Ulepszenia interfejsu użytkownika tworzenia profilu typu rejestracji systemów iOS/iPadOS<!-- 6055005 -->
W przypadku rejestracji użytkowników w systemach iOS/iPadOS uproszczono stronę **Tworzenie profilu typu rejestracji** **Ustawienia** w celu ulepszenia procesu wyboru **typu rejestracji** przy zachowaniu tej samej funkcjonalności. Aby zobaczyć nowy interfejs użytkownika, wybierz pozycję [Centrum administracyjne programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Urządzenia** > **iOS** > **Rejestracja systemu iOS** > **Typy rejestracji** > **Utwórz profil** > **Ustawienia**. Aby uzyskać więcej informacji, zobacz [Tworzenie profilu rejestracji użytkownika w usłudze Intune](../enrollment/ios-user-enrollment.md#create-a-user-enrollment-profile-in-intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="new-information-in-device-details---4471759-5604099----"></a>Nowe informacje w obszarze szczegółów urządzenia<!-- 4471759 5604099  -->
Strona **Przegląd** dla urządzeń zawiera teraz następujące informacje:
- Pojemność pamięci (ilość pamięci fizycznej w urządzeniu)
- Pojemność magazynu (ilość magazynu fizycznego w urządzeniu) 
- Architektura procesora


#### <a name="ios-bypass-activation-lock-remote-action-renamed-to-disable-activation-lock---5904591----"></a>Zmiana nazwy akcji Zastosuj obejście blokady aktywacji w systemie iOS na Wyłącz blokadę aktywacji <!--5904591  -->
Nazwa akcji zdalnej **Zastosuj obejście blokady aktywacji** została zmieniona na **Wyłącz blokadę aktywacji**. Aby uzyskać więcej informacji, zobacz [Wyłączanie blokady aktywacji systemu iOS przy użyciu usługi Intune](../remote-actions/device-activation-lock-bypass.md).

#### <a name="windows-10-feature-update-deployment-support-for-autopilot-devices---5948137-----"></a>Obsługa wdrażania aktualizacji funkcji systemu Windows 10 dla urządzeń rozwiązania Autopilot<!-- 5948137   -->
Usługa Intune obsługuje teraz wybieranie urządzeń zarejestrowanych w rozwiązaniu Autopilot przy użyciu [wdrożeń aktualizacji funkcji systemu Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates).

Zasady aktualizacji funkcji systemu Windows 10 nie mogą być stosowane w trybie OOBE (out-of-box experience) rozwiązania Autopilot. Zostaną one zastosowane tylko podczas pierwszego skanowania funkcji Windows Update po ukończeniu aprowizacji urządzenia (zazwyczaj trwa to jeden dzień).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="windows-autopilot-deployment-reports-preview----3856172-----"></a>Raporty wdrażania przy użyciu rozwiązania Windows Autopilot (wersja zapoznawcza) <!-- 3856172   -->
Nowy raport wyszczególnia wszystkie urządzenia wdrożone przy użyciu rozwiązania Windows Autopilot. Aby uzyskać więcej informacji, zobacz [Raport wdrażania dla rozwiązania Autopilot](../enrollment/enrollment-autopilot.md#autopilot-deployments-report).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-----"></a>Nowa wbudowana rola usługi Intune — Menedżer zabezpieczeń punktu końcowego<!--4253397   -->
Dostępna jest nowa wbudowana rola usługi Intune: Menedżer zabezpieczeń punktu końcowego. Ta nowa rola zapewnia administratorom pełny dostęp do węzła Menedżer punktu końcowego w usłudze Intune i dostęp tylko do odczytu do innych obszarów. Ta rola to rozszerzenie roli „Administrator zabezpieczeń” z usługi Azure AD. Jeśli obecnie używasz tylko ról administratorów globalnych, nie musisz wprowadzać żadnych zmian. Jeśli używasz ról i chcesz korzystać ze stopnia szczegółowości, który zapewnia rola Menedżer zabezpieczeń punktu końcowego, przypisz tę rolę, gdy zostanie udostępniona. Aby uzyskać więcej informacji o rolach wbudowanych, zobacz [Kontrola dostępu na podstawie ról](role-based-access-control.md).

<!-- ########################## -->
## <a name="week-of-january-6-2020"></a>Tydzień 6 stycznia 2020 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="smime-support-for-microsoft-outlook-for-ios---2669398---"></a>Obsługa protokołu S/MIME dla programu Microsoft Outlook w systemie iOS<!-- 2669398 -->
Usługa Intune obsługuje dostarczanie certyfikatów podpisywania S/MIME i certyfikatów szyfrowania, które mogą być używane z programem Outlook dla systemu iOS na urządzeniach z systemem iOS. Aby uzyskać więcej informacji, zobacz temat [Sensitivity labeling and protection in Outlook for iOS and Android](https://aka.ms/omsmime) (Etykietowanie i ochrona poufności w programie Outlook dla systemów iOS i Android).

#### <a name="cache-win32-app-content-using-microsoft-connected-cache-server---6030314---"></a>Buforowanie zawartości aplikacji Win32 przy użyciu serwera Microsoft Connected Cache<!-- 6030314 -->
Możesz zainstalować serwer Microsoft Connected Cache w punktach dystrybucji programu Configuration Manager, aby buforować zawartość aplikacji Win32 w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Serwer Microsoft Connected Cache w programie Configuration Manager — obsługa aplikacji Win32 w usłudze Intune](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="windows-10-administrative-templates-admx-profiles-now-support-scope-tags---5137390---"></a>Profile szablonów administracyjnych systemu Windows 10 (ADMX) obsługują teraz tagi zakresu <!--5137390 -->
Możesz teraz przypisywać tagi zakresu do profilów szablonów administracyjnych (ADMX). W tym celu przejdź do pozycji **Intune** > **Urządzenia** > **Profile konfiguracji** > wybierz profil szablonów administracyjnych na liście > **Właściwości** > **Tagi zakresu**. Aby uzyskać więcej informacji na temat tagów zakresu, zobacz sekcję [Przypisywanie tagów zakresu do innych obiektów](../fundamentals/scope-tags.md#assign-scope-tags-to-other-objects).

<!-- ########################## -->
## <a name="week-of-december-30-2019"></a>Tydzień 30 grudnia 2019 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>Pobieranie osobistego klucza odzyskiwania z urządzeń z systemem macOS zaszyfrowanych przy użyciu programu MEM<!-- 4851745 -->
Użytkownicy końcowi mogą pobrać osobisty klucz odzyskiwania (klucz FileVault) przy użyciu aplikacji Portal firmy dla systemu iOS. Urządzenie, które ma osobisty klucz odzyskiwania, musi zostać zarejestrowane w usłudze Intune i zaszyfrowane za pomocą usługi FileVault w usłudze Intune. Korzystając z aplikacji Portal firmy systemu iOS, użytkownik końcowy może pobrać osobisty klucz odzyskiwania na zaszyfrowanym urządzeniu z systemem macOS, klikając pozycję **Pobierz klucz odzyskiwania**. Możesz również pobrać klucz odzyskiwania z usługi Intune, wybierając pozycję **Urządzenia** > *zaszyfrowane i zarejestrowane urządzenie z systemem macOS* > **Pobierz klucz odzyskiwania**. Aby uzyskać więcej informacji na temat programu FileVault, zobacz [Szyfrowanie za pomocą programu FileVault w systemie macOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

#### <a name="ios-and-ipados-user-licensed-vpp-apps---5619268---"></a>Aplikacje programu VPP dla systemu iOS i iPadOS licencjonowane przez użytkownika<!-- 5619268 -->
W przypadku urządzeń z systemem iOS i iPadOS zarejestrowanych przez użytkownika użytkownicy końcowi nie będą już widzieć nowo utworzonych aplikacji programu VPP licencjonowanych na urządzeniu, które zostały wdrożone jako dostępne. Będą oni jednak nadal widzieć wszystkie aplikacje programu VPP licencjonowane przez użytkownika w aplikacji Portal firmy. Aby uzyskać więcej informacji o aplikacjach programu VPP, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemów iOS i macOS, które zostały zakupione w ramach programu zakupów zbiorczych firmy Apple](~/apps/vpp-apps-ios.md).

<!-- ########################## -->
## <a name="week-of-december-23-2019"></a>Tydzień 23 grudnia 2019 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="notice---windows-10-1703-rs2-will-be-moving-out-of-support----5026679---"></a>Powiadomienie — wsparcie systemu Windows 10 1703 (RS2) zostanie zakończone <!-- 5026679 -->
Od 9 października 2018 r. zakończyło się wsparcie platformy firmy Microsoft dla systemu Windows 10 1703 (RS2) w wersji Home, Pro i Pro for Workstations. W przypadku wersji Windows 10 Enterprise i Education wsparcie platformy dla systemu Windows 10 1703 (RS2) zakończyło się 8 października 2019 r. Od 26 grudnia 2019 r. będziemy aktualizować minimalną wersję aplikacji Portal firmy dla systemu Windows do systemu Windows 10 1709 (RS3). Komputery z wersjami wcześniejszymi niż 1709 nie będą już otrzymywać zaktualizowanych wersji aplikacji ze sklepu Microsoft Store. Informacje o tej zmianie zostały wcześniej przekazane klientom, którzy zarządzają starszymi wersjami systemu Windows 10 za pośrednictwem centrum wiadomości. Więcej informacji można znaleźć w temacie [Zestawienie dotyczące cyklu życia systemu Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

<!-- ########################## -->

## <a name="week-of-december-16-2019"></a>Tydzień 16 grudnia 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="updates-to-administrative-templates-for-windows-10-devices----5941568---"></a>Aktualizacje szablonów administracyjnych dla urządzeń z systemem Windows 10 <!-- 5941568 -->

Szablonów ADMX można używać w usłudze Microsoft Intune do kontrolowania ustawień programu Microsoft Edge, pakietu Office i systemu Windows oraz zarządzania nimi. Szablony administracyjne w usłudze Intune obejmują następujące aktualizacje ustawień zasad:

- Dodano obsługę programu Microsoft Edge w wersjach 78 i 79.
- Obejmuje pliki ADMX z 11 listopada 2019 r. wchodzące w skład [plików szablonów administracyjnych (ADMX/ADML) i narzędzia dostosowywania pakietu Office dla pakietu Office 365 ProPlus, Office 2019 i Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Aby uzyskać więcej informacji o szablonach ADMX w usłudze Intune, zobacz temat [Korzystanie z szablonów systemu Windows 10 umożliwiających konfigurowanie ustawień zasad grupy w usłudze Microsoft Intune](../configuration/administrative-templates-windows.md).

Dotyczy:

- Windows 10 lub nowszym

## <a name="week-of-december-9-2019-1912-service-release"></a>Tydzień 9 grudnia 2019 r. (wersja usługi 1912)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="migrating-to-microsoft-edge-for-managed-browsing-scenarios---5173762---"></a>Migrowanie do przeglądarki Microsoft Edge na potrzeby scenariuszy przeglądania zarządzanego<!-- 5173762 -->
W miarę zbliżania się terminu wycofania programu Intune Managed Browser wprowadziliśmy zmiany w zasadach ochrony aplikacji w celu uproszczenia kroków potrzebnych do przeniesienia użytkowników do przeglądarki Edge. Zaktualizowaliśmy opcje ustawienia zasad ochrony aplikacji **Ogranicz transfer zawartości internetowej dla innych aplikacji** na jedną z następujących wartości:

- Dowolna aplikacja
- Intune Managed Browser
- Microsoft Edge
- Przeglądarka niezarządzana 

Po wybraniu programu **Microsoft Edge** użytkownicy końcowi zobaczą komunikat dotyczący dostępu warunkowego z informacją o tym, że przeglądarka Microsoft Edge jest wymagana w przypadku scenariuszy przeglądania zarządzanego. Zostanie wyświetlony monit o pobranie przeglądarki Microsoft Edge i zalogowanie się do niej przy użyciu konta usługi AAD, jeśli jeszcze tego nie zrobiono.  Będzie to odpowiednik zastosowania dla aplikacji z obsługą zarządzania aplikacjami mobilnymi ustawienia konfiguracji `com.microsoft.intune.useEdge` o wartości **True**. Istniejące zasady ochrony aplikacji, które używały **przeglądarek zarządzanych za pomocą zasad**, teraz będą mieć wybrany program **Intune Managed Browser** i nie wystąpią żadne zmiany w zachowaniu. Oznacza to, że użytkownicy zobaczą komunikat dotyczący użycia przeglądarki Microsoft Edge, jeśli dla ustawienia konfiguracji aplikacji **useEdge** określono wartość **True**. Zachęcamy wszystkich klientów korzystających ze scenariuszy przeglądania zarządzanego do zaktualizowania zasad ochrony aplikacji za pomocą opcji **Ogranicz transfer zawartości internetowej dla innych aplikacji**, aby użytkownicy mogli zobaczyć odpowiednie wskazówki dotyczące przejścia do przeglądarki Microsoft Edge niezależnie od tego, z której aplikacji otwierają linki. 

#### <a name="configure-app-notification-content-for-organization-accounts---2576686----"></a>Konfigurowanie zawartości powiadomień aplikacji dla kont organizacji<!-- 2576686  -->
Zasady ochrony aplikacji usługi Intune (APP, app protection policies) na urządzeniach z systemem Android i iOS umożliwiają kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Możesz wybrać opcję (Zezwalaj, Blokuj dane organizacji lub Zablokowane), aby określić sposób wyświetlania powiadomień dotyczących konta organizacji dla wybranej aplikacji. Ta funkcja wymaga obsługi aplikacji i może być niedostępna dla wszystkich aplikacji z włączonymi zasadami APP. Program Outlook dla systemu iOS 4.15.0 (lub nowszego) oraz program Outlook dla systemu Android 4.83.0 (lub nowszego) będzie obsługiwać to ustawienie. To ustawienie jest dostępne w konsoli, ale funkcja zacznie działać po 16 grudnia 2019 r. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)

#### <a name="microsoft-app-icons-update--4677605----"></a>Aktualizacja ikon aplikacji firmy Microsoft<!--4677605  -->
Ikony używane dla aplikacji firmy Microsoft w okienku określania docelowej aplikacji dla zasad ochrony aplikacji i zasad konfiguracji aplikacji zostały zaktualizowane.

#### <a name="require-use-of-approved-keyboards-on-android--4761794----"></a>Wymagane użycie zatwierdzonych klawiatur w systemie Android<!--4761794  -->
W ramach zasad ochrony aplikacji można określić ustawienie [**Zatwierdzone klawiatury**](../apps/app-protection-policy-settings-android.md#data-protection), aby zarządzać klawiaturami systemu Android, które mogą być używane z zarządzanymi aplikacjami dla systemu Android. Gdy użytkownik otworzy zarządzaną aplikację i nie będzie już używać zatwierdzonej klawiatury dla tej aplikacji, zostanie wyświetlony monit o przełączenie na jedną z zatwierdzonych klawiatur zainstalowanych na urządzeniu. W razie potrzeby pojawi się link umożliwiający pobranie ze sklepu Google Play zatwierdzonej klawiatury, którą można zainstalować i skonfigurować. Użytkownik może tylko edytować pola tekstowe w zarządzanej aplikacji, gdy klawiatura aktywna nie jest jedną z zatwierdzonych klawiatur.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578----"></a>Zaktualizowane środowisko logowania jednokrotnego do aplikacji i witryn internetowych na urządzeniach z systemem iOS, iPadOS i macOS<!-- 4999578  -->
Usługa Intune dodała więcej ustawień logowania jednokrotnego dla urządzeń z systemami iOS, iPadOS i macOS. Teraz można skonfigurować przekierowywanie rozszerzeń aplikacji logowania jednokrotnego napisanych przez organizację lub dostawcę tożsamości. Te ustawienia służą do konfigurowania środowiska bezproblemowego logowania jednokrotnego do aplikacji i witryn internetowych korzystających z nowoczesnych metod uwierzytelniania, takich jak OAuth i SAML2. 

Te nowe ustawienia stanowią rozszerzenie poprzednich ustawień dla rozszerzeń aplikacji logowania jednokrotnego i wbudowanego rozszerzenia protokołu Kerberos firmy Apple (**Urządzenia** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** lub **macOS** jako typ platformy > **Funkcje urządzenia** jako typ profilu). 

Pełen zakres ustawień rozszerzenia aplikacji logowania jednokrotnego, które można skonfigurować można znaleźć w tematach dotyczących [logowania jednokrotnego w systemie iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) i [logowania jednokrotnego w systemie macOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Dotyczy:

- iOS/iPadOS
- macOS

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352------"></a>Zaktualizowaliśmy dwa ustawienia ograniczeń urządzenia dla urządzeń z systemem iOS i iPadOS, aby skorygować ich zachowanie<!-- 5701352    -->
W przypadku urządzeń z systemem iOS można utworzyć profile ograniczeń urządzeń, które **zezwalają na bezprzewodowe aktualizacje infrastruktury PKI** i **blokują tryb ograniczony USB** (**Urządzenia** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu). Przed tą wersją ustawienia i opisy interfejsu użytkownika dla następujących ustawień były nieprawidłowe i zostały teraz poprawione. Począwszy od tej wersji, zachowanie ustawień jest następujące:

**Blokuj bezprzewodowe aktualizacje infrastruktury PKI**: pozycja **Blokuj** uniemożliwia użytkownikom otrzymywanie aktualizacji oprogramowania, chyba że urządzenie zostało podłączone do komputera. Pozycja **Nie skonfigurowano** (wartość domyślna) umożliwia urządzeniu otrzymywanie aktualizacji oprogramowania bez połączenia z komputerem.
- Wcześniej to ustawienie można było skonfigurować w następujący sposób: pozycja **Zezwalaj** pozwala użytkownikom na otrzymywanie aktualizacji oprogramowania bez podłączania urządzeń do komputera.
**Zezwalaj na akcesoria USB, gdy urządzenie jest zablokowane**: pozycja **Zezwalaj** umożliwia akcesoriom USB wymianę danych z urządzeniem, które było zablokowane przez dłużej niż godzinę. Pozycja **Nie skonfigurowano** (wartość domyślna) nie aktualizuje trybu ograniczonego USB na urządzeniu, a akcesoria USB nie mogą przesyłać danych z urządzenia zablokowanego przez ponad godzinę.
- Wcześniej to ustawienie można było skonfigurować w następujący sposób: pozycja **Blokuj**, aby wyłączyć tryb ograniczony USB na urządzeniach w trybie nadzorowanym.

Aby uzyskać więcej informacji na temat ustawień, które można skonfigurować, zobacz artykuł [Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Ta funkcja ma zastosowanie do:

- OS/iPadOS

#### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profile konfiguracji urządzeń sieci przewodowej dla urządzeń z systemem macOS<!-- 3508686  -->
   > [!NOTE]
   > Ta funkcja jest opóźniona, lecz zostanie wydana wkrótce.

#### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998---"></a>Blokowanie możliwości konfigurowania przez użytkowników poświadczeń certyfikatów w zarządzanym magazynie kluczy na urządzeniach właścicieli urządzeń z systemem Android Enterprise<!-- 3311998 -->
Na urządzeniach właścicieli urządzeń z systemem Android Enterprise możesz skonfigurować nowe ustawienie, które uniemożliwia użytkownikom konfigurowanie poświadczeń certyfikatów w zarządzanym magazynie kluczy (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia > Ograniczenia urządzenia** jako typ profilu > **Użytkownicy i konta**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="protected-wipe-action-now-available--51150000---"></a>Akcja chronionego czyszczenia teraz dostępna<!--51150000 -->
Możesz teraz użyć akcji Wyczyść urządzenie, aby przeprowadzić chronione czyszczenie urządzenia. Operacje czyszczenia chronionego są takie same jak operacje czyszczenia standardowego, z tą różnicą, że nie można ich obejść przez wyłączenie urządzenia. Funkcja chronionego czyszczenia będzie ponawiać próby zresetowania urządzenia do momentu pomyślnego przeprowadzenia czyszczenia. W przypadku niektórych konfiguracji ta akcja może pozostawić urządzenie w stanie, który uniemożliwia jego ponowne uruchomienie. Aby uzyskać więcej informacji, zobacz artykuł [Wycofywanie lub czyszczenie urządzeń](../remote-actions/devices-wipe.md).

#### <a name="device-ethernet-mac-address-added-to-devices-overview-page--5562275---"></a>Adres MAC sieci Ethernet urządzenia dodany do strony omówienia urządzenia<!--5562275 -->
Na stronie szczegółów urządzenia można teraz sprawdzić adres MAC sieci Ethernet urządzenia (**Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Omówienie**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="improved-experience-on-a-shared-device-when-device-based-conditional-access-policies-are-enabled---1734096----"></a>Ulepszone środowisko pracy na urządzeniu udostępnionym w przypadku włączenia zasad dostępu warunkowego opartych na urządzeniach<!-- 1734096  -->
Ulepszyliśmy środowisko na urządzeniu udostępnionym z wieloma użytkownikami, których dotyczą zasady dostępu warunkowego oparte na urządzeniach, dzięki funkcji sprawdzania najnowszej oceny zgodności dla użytkownika podczas wymuszania zasad. Więcej informacji znajduje się w poniższych artykułach z omówieniem:
- [Omówienie platformy Azure pod kątem dostępu warunkowego](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Omówienie zgodności urządzeń w usłudze Intune](../protect/device-compliance-get-started.md)

#### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529----"></a>Używanie profilów certyfikatów PKCS do aprowizowania urządzeń z certyfikatami<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529  -->
Profile certyfikatów PKCS umożliwiają teraz wystawianie certyfikatów *urządzeń* z systemem Android for Work, iOS i Windows, jeśli zostały one skojarzone z profilami, takimi jak profile dotyczące sieci Wi-Fi i VPN. Wcześniej te trzy platformy obsługiwały tylko certyfikaty oparte na użytkownikach, a obsługa oparta na urządzeniach była ograniczona do systemu macOS.

> [!NOTE]
> Profile certyfikatów PKCS nie są obsługiwane przy użyciu profilów sieci Wi-Fi. W zamian użyj profilów certyfikatów SCEP w przypadku korzystania z [typu EAP](../configuration/wi-fi-settings-windows.md#enterprise-profile).

Aby używać certyfikatu opartego na urządzeniu, podczas [tworzenia profilu certyfikatu PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) dla obsługiwanych platform wybierz pozycję **Ustawienia**. Będziesz teraz widzieć ustawienie **Typ certyfikatu**, który obsługuje opcje dla urządzenia lub użytkownika.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="centralized-audit-logs--5603185-5697164---"></a>Scentralizowane dzienniki inspekcji<!--5603185, 5697164 -->
Nowe scentralizowane środowisko dzienników inspekcji zbiera teraz dzienniki inspekcji dla wszystkich kategorii na jednej stronie. Dzienniki możesz filtrować, aby pobrać dane, których szukasz. Aby wyświetlić dzienniki inspekcji, przejdź do pozycji **Administracja dzierżawą** > **Dzienniki inspekcji**. 

#### <a name="scope-tag-information-included-in-audit-log-activity-details--5763534---"></a>Informacje o tagach zakresu zawarte w szczegółach działania dziennika inspekcji<!--5763534 -->
Szczegóły działania dziennika inspekcji zawierają teraz informacje o tagach zakresu (dla obiektów usługi Intune, które obsługują tagi zakresu). Aby uzyskać więcej informacji na temat dzienników inspekcji, zobacz artykuł [Śledzenie i monitorowanie zdarzeń w usłudze za pomocą dzienników inspekcji](monitor-audit-logs.md).


<!-- ########################## -->
## <a name="week-of-december-2-2019"></a>Tydzień 2 grudnia 2019 r.

#### <a name="new-microsoft-endpoint-configuration-manager-co-management-licensing--5027281--"></a>Nowe licencjonowanie współzarządzane programu Microsoft Endpoint Configuration Manager<!--5027281-->
Klienci programu Configuration Manager z pakietem Software Assurance mogą uzyskać licencje współzarządzane dla komputerów z systemem Windows 10 bez konieczności zakupu dodatkowej licencji usługi Intune na potrzeby współzarządzania. Klienci nie muszą już przypisywać poszczególnych licencji usługi Intune/EMS do użytkowników końcowych w celu współzarządzania systemem Windows 10.
- Urządzenia zarządzane przez program Configuration Manager i zarejestrowane w ramach współzarządzania mają niemal takie same prawa jak komputery zarządzane za pomocą funkcji zarządzania urządzeniami mobilnymi usługi Intune. Jednak po zresetowaniu nie można ich aprowizować ponownie przy użyciu programu Autopilot.
- Urządzenia z systemem Windows 10 zarejestrowane w usłudze Intune przy użyciu innych metod wymagają pełnych licencji usługi Intune.
- Urządzenia na innych platformach nadal wymagają pełnych licencji usługi Intune.

Aby uzyskać więcej informacji, zobacz [postanowienia licencyjne](https://www.microsoft.com/en-us/Licensing/product-licensing/products).


<!-- ########################## -->
## <a name="week-of-november-18-2019-1911-service-release"></a>Tydzień 18 listopada 2019 r. (wersja usługi 1911)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Aktualizowanie interfejsu użytkownika podczas selektywnego czyszczenia danych aplikacji<!-- 4102028 -->
Interfejs użytkownika służący do selektywnego czyszczenia danych aplikacji w usłudze Intune został zaktualizowany. Zmiany interfejsu użytkownika:
- Uproszczone środowisko dzięki użyciu formatu kreatorów skondensowanego w obrębie pojedynczego okienka.
- Aktualizacja przepływu tworzenia w celu uwzględnienia przypisań.
- Strona podsumowania wszystkich elementów ustawionych podczas wyświetlania właściwości, przed utworzeniem nowych zasad lub podczas edytowania właściwości. Ponadto podczas edytowania właściwości podsumowanie będzie zawierać tylko listę elementów z kategorii właściwości, które są edytowane.

Aby uzyskać więcej informacji, zobacz [Jak czyścić z aplikacji usługi Intune tylko dane firmowe](~/apps/apps-selective-wipe.md).

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>Obsługa klawiatur innych firm w systemach iOS i iPadOS<!-- 4922950 -->
W marcu 2019 r. ogłosiliśmy zakończenie obsługi ustawienia zasad ochrony aplikacji systemu iOS „Klawiatury innych firm”. Funkcja wraca do usługi Intune i oferuje obsługę systemów iOS oraz iPadOS. Aby włączyć to ustawienie, przejdź na kartę **Ochrona danych** nowych lub istniejących zasad ochrony aplikacji dla systemu iOS/iPadOS i znajdź ustawienie **Klawiatury innych firm** w obszarze **Transfer danych**.

Zachowanie tego ustawienia zasad różni się nieco od poprzedniej implementacji. W przypadku aplikacji z obsługą wielu tożsamości używających zestawu SDK w wersji 12.0.16 lub nowszej, które zostały objęte zasadami ochrony aplikacji z tym ustawieniem skonfigurowanym jako **Blokuj**, użytkownicy końcowi nie będą mogli zrezygnować z używania klawiatur innych firm na kontach organizacyjnych ani osobistych. Aplikacje korzystające z zestawu SDK w wersji 12.0.12 i starszych będą nadal zachowywać się w sposób udokumentowany w następującym wpisie w blogu: [Known issue: Third party keyboards are not blocked in iOS for personal accounts](https://aka.ms/3rdparty_iOS_Intune) (Znany problem: klawiatury innych firm nie są blokowane w systemie iOS dla kont osobistych).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>Docelowe grupy użytkowników systemu macOS mogą wymagać zarządzania przy użyciu oprogramowania Jamf<!-- 4061739  --> 
Można wybierać określone grupy użytkowników, których [urządzenia z systemem macOS będą zarządzane przez oprogramowanie Jamf](../protect/conditional-access-integrate-jamf.md). Pozwala to na stosowanie integracji zgodności Jamf z podzbiorem urządzeń z systemem macOS, gdy inne urządzenia będą zarządzane przez usługę Intune. Jeśli już używasz integracji z oprogramowaniem Jamf, wszyscy użytkownicy będą domyślnie objęci tą integracją.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>Nowe ustawienia protokołu Exchange ActiveSync podczas tworzenia profilu konfiguracji urządzenia poczty e-mail na urządzeniach z systemem iOS<!-- 4892824   --> 
Na urządzeniach z systemem iOS/iPadOS można skonfigurować łączność z pocztą e-mail w profilu konfiguracji urządzenia (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** jako platforma > **Poczta e-mail** jako typ profilu). 

Istnieją nowe dostępne ustawienia protokołu Exchange ActiveSync, w tym:
- **Dane programu Exchange do synchronizacji**: wybierz usługi programu Exchange do zsynchronizowania (lub zablokowania synchronizacji) dla kalendarza, kontaktów, przypomnień, notatek i poczty e-mail.
- **Zezwalaj użytkownikom na zmianę ustawień synchronizacji**: zezwalaj użytkownikom na zmienianie ustawień synchronizacji dla tych usług na ich urządzeniach (lub blokuj tę możliwość).  

Aby uzyskać więcej informacji na temat tych ustawień, przejdź do tematu [Ustawienia profilu poczty e-mail dla urządzeń z systemem iOS w usłudze Intune](../configuration/email-settings-ios.md). 

Dotyczy:

- System iOS 13.0 i nowsze
- System iPadOS 13.0 i nowsze

#### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-fully-managed-and-dedicated-devices---5353228-----"></a>Uniemożliwianie użytkownikom dodawania osobistych kont Google do w pełni zarządzanych i dedykowanych urządzeń z systemem Android Enterprise<!-- 5353228   -->
Na w pełni zarządzanych i dedykowanych urządzeniach z systemem Android Enterprise istnieje nowe ustawienie, które uniemożliwia użytkownikom tworzenie osobistych kont Google (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia > Ograniczenia urządzenia** jako typ profilu > **Ustawienia użytkowników i kont** > **Osobiste konta Google**).

Aby wyświetlić ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md).

Dotyczy:

- W pełni zarządzane urządzenia z rozwiązaniem Android Enterprise
- Dedykowane urządzenia z rozwiązaniem Android Enterprise

#### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-iosipados-device-restrictions-profile----5468501-----"></a>Ustawienie rejestrowania poleceń Siri po stronie serwera zostało usunięte z profilu ograniczeń urządzenia z systemem iOS/iPadOS <!-- 5468501   -->
Na urządzeniach z systemami iOS i iPadOS ustawienie **Rejestrowanie poleceń Siri po stronie serwera** zostało usunięte z konsoli administracyjnej programu Microsoft Endpoint Manager (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** jako platforma > **Ograniczenia ustawienia** jako typ profilu > **Aplikacje wbudowane**). 

To ustawienie nie ma wpływu na urządzenia. Aby usunąć ustawienie z istniejących profilów, otwórz profil, wprowadź dowolną zmianę, a następnie zapisz profil. Profil zostanie zaktualizowany, a ustawienie zostanie usunięte z urządzeń.

Aby wyświetlić wszystkie ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:

- iOS/iPadOS

#### <a name="windows-10-feature-updates-public-preview---2384877---"></a>Aktualizacje funkcji systemu Windows 10 (publiczna wersja zapoznawcza)<!-- 2384877 -->
Można teraz wdrażać [aktualizacje funkcji systemu Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates) na urządzeniach z systemem Windows 10. Aktualizacje funkcji systemu Windows 10 to nowe zasady aktualizacji oprogramowania ustawiające wersję systemu Windows 10, która ma być instalowana przez urządzenia i która ma na nich pozostać. Tego nowego typu zasad można używać wraz z istniejącymi pierścieniami aktualizacji systemu Windows 10.

Urządzenia, na których są odbierane zasady aktualizacji funkcji systemu Windows 10, zainstalują określoną wersję systemu Windows, a następnie pozostaną w tej wersji do momentu edytowania lub usunięcia zasad. Urządzenia z nowszą wersją systemu Windows pozostają w bieżącej wersji. Urządzenia, na których jest zachowana określona wersja systemu Windows, mogą nadal instalować aktualizacje jakości i zabezpieczeń dla tej wersji z poziomu pierścieni aktualizacji systemu Windows 10.

Ten nowy typ zasad będzie dostępny dla dzierżaw w tym tygodniu. Jeśli te zasady nie są jeszcze dostępne dla Twojej dzierżawy, udostępnimy je wkrótce.

#### <a name="add-and-change-key-information-in-plist-files-for-macos-applications---4736278---"></a>Dodawanie i zmienia informacji dotyczących kluczy w plikach plist dla aplikacji systemu macOS<!-- 4736278 -->
Na urządzeniach z systemem macOS można teraz utworzyć profil konfiguracji urządzenia, który przekazuje plik listy właściwości (plist) skojarzony z aplikacją lub z urządzeniem (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil** > **macOS** jako platforma > **Plik preferencji** jako typ profilu).

Tylko niektóre aplikacje obsługują preferencje zarządzane. Aplikacje te mogą nie zezwalać na zarządzanie wszystkimi ustawieniami. Pamiętaj, aby przekazać plik listy właściwości, który konfiguruje ustawienia kanału urządzenia, a nie ustawienia kanału użytkownika.

Aby uzyskać więcej informacji na temat tej funkcji, zobacz temat [Dodawanie pliku listy właściwości do urządzeń z systemem macOS za pomocą usługi Microsoft Intune](../configuration/preference-file-settings-macos.md).

Dotyczy:

- Urządzenia z systemem macOS 10.7 i nowszym

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="edit-device-name-value-for-autopilot-devices---2640074---"></a>Edytowanie wartości nazwy urządzenia dla urządzeń z rozwiązaniem Autopilot<!-- 2640074 -->
Można edytować wartość nazwy urządzenia dla urządzeń z rozwiązaniem Autopilot, które dołączono do usługi Azure AD.  Aby uzyskać więcej informacji, zobacz temat [Edytowanie atrybutów urządzenia z rozwiązaniem Autopilot](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

#### <a name="edit-group-tag-value-for-autopilot-devices---4816775-----"></a>Edytowanie wartości tagu grupy dla urządzeń z rozwiązaniem Autopilot<!-- 4816775   -->
Można edytować wartość tagu grupy dla urządzeń z rozwiązaniem Autopilot. Aby uzyskać więcej informacji, zobacz temat [Edytowanie atrybutów urządzenia z rozwiązaniem Autopilot](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="updated-support-experience---5012398---"></a>Zaktualizowane środowisko pomocy technicznej<!-- 5012398 -->

Od dzisiaj zaktualizowane i usprawnione środowisko w konsoli służące do [uzyskiwania pomocy i obsługi technicznej usługi Intune](get-support.md) jest dostępne dla dzierżaw. Jeśli jeszcze nie masz dostępu do nowego środowiska, udostępnimy je wkrótce.

Usprawniliśmy wyszukiwanie i obsługę opinii w konsoli dotyczące typowych problemów oraz przepływ pracy używany do kontaktowania się z pomocą techniczną. Podczas otwierania problemu pomocy technicznej będą wyświetlane oszacowania w czasie rzeczywistym dotyczące terminu spodziewanego kontaktu telefonicznego lub odpowiedzi za pośrednictwem wiadomości e-mail, a klienci usług Premier i Unified Support mogą łatwo określić ważność problemu, aby szybciej uzyskać pomoc techniczną.

#### <a name="improved-intune-reporting-experience-public-preview----3791418---"></a>Udoskonalone środowisko raportowania usługi Intune (publiczna wersja zapoznawcza) <!-- 3791418 -->
Usługa Intune oferuje teraz udoskonalone środowisko raportowania, w tym nowe typy raportów, lepszą organizację raportów, bardziej ukierunkowane widoki, ulepszone funkcje raportów, a także spójniejsze i aktualniejsze dane. Nowe typy raportów koncentrują się na następujących kwestiach:
- **Operacyjne** — oferują nowe rekordy skoncentrowane na złej kondycji. 
- **Organizacyjne** — zawierają szersze podsumowanie ogólnego stanu.
- **Historyczne** — przedstawiają wzorce i trendy w wybranym okresie.
- **Specjalistyczne** — umożliwiają tworzenie własnych niestandardowych raportów przy użyciu danych pierwotnych.

Pierwszy zestaw nowych raportów koncentruje się na zgodności urządzeń. Aby uzyskać więcej informacji, zobacz tematy [Blog - Microsoft Intune reporting framework](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) (Blog — platforma raportowania w usłudze Microsoft Intune) i [Intune reports](~/fundamentals/reports.md) (Raporty usługi Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="duplicate-custom-or-built-in-roles----1081938-----"></a>Zduplikowane role niestandardowe lub wbudowane <!-- 1081938   -->
Teraz można kopiować role wbudowane i niestandardowe. Aby uzyskać więcej informacji, zobacz sekcję [Kopiowanie roli](../fundamentals/create-custom-role.md#copy-a-role).

#### <a name="new-permissions-for-school-administrator-role----5621805----"></a>Nowe uprawnienia roli administratora szkoły <!-- 5621805  -->  
Dwa nowe uprawnienia: **Przypisywanie profilu** i **Synchronizowane urządzenia** zostały dodane do roli administratora szkoły > **Uprawnienia** > **Programy rejestracji**. Uprawnienie Profil synchronizacji umożliwia administratorom grup synchronizowanie urządzeń z rozwiązaniem Windows Autopilot. Uprawnienie Przypisywanie profilu umożliwia im usuwanie inicjowanych przez użytkownika profilów rejestracji firmy Apple. Jest to również uprawnienie do zarządzania przypisaniami urządzeń z rozwiązaniem Autopilot i przypisaniami profilów wdrażania rozwiązania Autopilot. Aby uzyskać listę wszystkich uprawnień administratora szkoły/administratora grupy, zobacz temat [Przypisywanie administratorów grup](https://docs.microsoft.com/intune-education/group-admin-delegate). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="security"></a>Zabezpieczenia

#### <a name="bitlocker-key-rotation---2564951----"></a>Obracanie kluczy funkcji BitLocker<!-- 2564951  -->
Za pomocą akcji urządzenia usługi Intune można zdalnie [obracać klucze odzyskiwania funkcji BitLocker](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) dla zarządzanych urządzeń z systemem Windows w wersji 1909 lub nowszej. Aby kwalifikować się do obracania kluczy odzyskiwania, urządzenia muszą zostać skonfigurowane do obsługi obracania kluczy odzyskiwania.  

#### <a name="updates-to-dedicated-device-enrollment-to-support-scep-device-certificate-deployment----5198878----"></a>Aktualizacje rejestracji urządzeń dedykowanych w celu obsługi wdrażania certyfikatu urządzenia SCEP <!-- 5198878  -->
Usługa Intune obsługuje teraz wdrażanie certyfikatów urządzeń SCEP dla dedykowanych urządzeń z systemem Android Enterprise, aby uzyskiwać dostęp oparty na certyfikatach do profilów sieci Wi-Fi. Aby wdrożenie działało, aplikacja Microsoft Intune musi być znajdować się na urządzeniu. W związku z tym zaktualizowaliśmy środowisko rejestracji dla urządzeń dedykowanych z systemem Android Enterprise. Nowe rejestracje nadal rozpoczynają się tak samo (od identyfikatora QR, NFC, wdrożenia bezobsługowego lub urządzenia), ale teraz obejmują krok wymagający od użytkowników zainstalowania aplikacji usługi Intune. Istniejące urządzenia rozpoczną automatyczne instalowanie aplikacji w sposób ciągły.

#### <a name="intune-audit-logs-for-business-to-business-collaboration--5670211---"></a>Dzienniki inspekcji usługi Intune na potrzeby obsługi współpracy między firmami (B2B)<!--5670211 -->
Współpraca między firmami (B2B, Business-to-Business) umożliwia bezpieczne udostępnianie firmowych aplikacji i usług użytkownikom-gościom z innych organizacji przy zachowaniu kontroli nad własnymi danymi firmowymi. Usługa Intune obsługuje teraz dzienniki inspekcji dla użytkowników-gości B2B. Na przykład w przypadku wprowadzenia zmian przez użytkowników-gości usługa Intune będzie mogła przechwycić te dane za pośrednictwem dzienników inspekcji. Aby uzyskać więcej informacji, zobacz temat [Co to jest dostęp gościa w usłudze Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)


<!-- ########################## -->
## <a name="week-of-november-11-2019"></a>Tydzień 11 listopada 2019 r.  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami  

#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Udoskonalone środowisko rejestracji systemu macOS w aplikacji Portal firmy <!-- 5074349  -->  
Środowisko rejestracji systemu macOS w aplikacji Portal firmy oferuje prostszy proces rejestracji, który jest lepiej dopasowany do środowiska rejestracji systemu iOS w aplikacji Portal firmy. Użytkownicy urządzeń widzą teraz:  

* Bardziej elegancki interfejs użytkownika.  
* Udoskonaloną listę kontrolną rejestracji.  
* Łatwiejsze do zrozumienia instrukcje dotyczące sposobu rejestrowania urządzeń.  
* Udoskonalone opcje rozwiązywania problemów.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Aplikacje internetowe uruchamiane z poziomu aplikacji Portal firmy systemu Windows<!-- 5030972 -->
Użytkownicy końcowi mogą teraz uruchamiać aplikacje internetowe bezpośrednio z poziomu aplikacji Portal firmy systemu Windows. Użytkownicy końcowi mogą wybrać aplikację internetową, a następnie wybrać opcję **Otwórz w przeglądarce**. Opublikowany internetowy adres URL zostanie otwarty bezpośrednio w przeglądarce. Ta funkcja zostanie udostępniona w następnym tygodniu. Aby uzyskać więcej informacji na temat aplikacji internetowych, zobacz [Dodawanie aplikacji internetowych do usługi Microsoft Intune](~/apps/web-app.md).  


#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950----"></a>Nowa kolumna typu przypisania w aplikacji Portal firmy dla systemu Windows 10 <!-- 5459950  -->
Nazwa kolumny w obszarze Portal firmy > **Zainstalowane aplikacje** > **Typ przypisania** została zmieniona na **Wymagane przez organizację**.  W tej kolumnie użytkownicy zobaczą wartość **Tak** lub **Nie**, która wskaże, czy aplikacja jest wymagana przez organizację, czy też została oznaczona jako opcjonalna. Te zmiany zostały wprowadzone, ponieważ koncepcja dostępnych aplikacji nie była jasna dla użytkowników urządzeń. Użytkownicy mogą znaleźć więcej informacji na temat instalowania aplikacji z Portalu firmy w temacie [Instalowanie i udostępnianie aplikacji na urządzeniu](/intune-user-help/install-apps-cpapp-windows). Aby uzyskać więcej informacji na temat konfigurowania aplikacji Portal firmy dla użytkowników, zobacz artykuł [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).  

<!-- ########################## -->
## <a name="week-of-november-4-2019"></a>Tydzień 4 listopada 2019 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>Punkty odniesienia zabezpieczeń są obsługiwane w usłudze Microsoft Azure Government<!-- 4062552 -->

Wystąpienia usługi Intune hostowane w usłudze *Microsoft Azure Government* mogą teraz używać [punktów odniesienia zabezpieczeń](../protect/security-baselines.md), aby pomóc w zabezpieczeniu i ochronie użytkowników i urządzeń.

## <a name="whats-new-archive"></a>Archiwum Co nowego
Aby zapoznać się z poprzednimi miesiącami, zobacz [Archiwum Co nowego](whats-new-archive.md).

## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
