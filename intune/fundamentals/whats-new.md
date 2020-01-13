---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/06/2020
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
ms.openlocfilehash: b2bb9d921f30e343b309be60438f5318d7c66518
ms.sourcegitcommit: a66b5916eaab9cb537e483064efc584a6a63a390
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/07/2020
ms.locfileid: "75692258"
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz tu również znaleźć [ważne powiadomienia](#notices), [poprzednie wydania](whats-new-archive.md) oraz informacje na temat [sposobu wydawania aktualizacji usługi Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Wprowadzanie każdej [aktualizacji miesięcznej](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) może potrwać do trzech dni i będzie przeprowadzane w następującej kolejności:
>
> - 1\. dzień: Azja i Pacyfik
> - 2\. dzień: Europa, Bliski Wschód i Afryka
> - 3\. dzień: Ameryka Północna
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
## <a name="week-of-january-6-2020"></a>Tydzień 6 stycznia 2020 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="smime-support-for-microsoft-outlook-for-ios---2669398---"></a>Obsługa protokołu S/MIME dla programu Microsoft Outlook w systemie iOS<!-- 2669398 -->
Usługa Intune obsługuje dostarczanie certyfikatów podpisywania S/MIME i certyfikatów szyfrowania, które mogą być używane z programem Outlook dla systemu iOS na urządzeniach z systemem iOS. Aby uzyskać więcej informacji, zobacz temat [Sensitivity labeling and protection in Outlook for iOS and Android](https://aka.ms/omsmime) (Etykietowanie i ochrona poufności w programie Outlook dla systemów iOS i Android).

<!-- ########################## -->
## <a name="week-of-december-30-2019"></a>Tydzień 30 grudnia 2019 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>Pobieranie osobistego klucza odzyskiwania z urządzeń z systemem macOS zaszyfrowanych przy użyciu programu MEM<!-- 4851745 -->
Użytkownicy końcowi mogą pobrać osobisty klucz odzyskiwania (klucz FileVault) przy użyciu aplikacji Portal firmy dla systemu iOS. Urządzenie, które ma osobisty klucz odzyskiwania, musi zostać zarejestrowane w usłudze Intune i zaszyfrowane za pomocą usługi FileVault w usłudze Intune. Korzystając z aplikacji Portal firmy systemu iOS, użytkownik końcowy może pobrać osobisty klucz odzyskiwania na zaszyfrowanym urządzeniu z systemem macOS, klikając pozycję **Pobierz klucz odzyskiwania**. Możesz również pobrać klucz odzyskiwania z usługi Intune, wybierając pozycję **Urządzenia** > *zaszyfrowane i zarejestrowane urządzenie z systemem macOS* > **Pobierz klucz odzyskiwania**. Aby uzyskać więcej informacji na temat programu FileVault, zobacz [Szyfrowanie za pomocą programu FileVault w systemie macOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

#### <a name="ios-user-licensed-vpp-apps---5619268---"></a>Aplikacje programu VPP licencjonowane przez użytkownika systemu iOS<!-- 5619268 -->
W przypadku urządzeń z systemem iOS zarejestrowanych przez użytkownika użytkownicy końcowi nie będą już widzieć aplikacji programu VPP licencjonowanych na urządzeniu, które zostały wdrożone jako dostępne. Będą oni jednak nadal widzieć wszystkie aplikacje programu VPP licencjonowane przez użytkownika w aplikacji Portal firmy. Aby uzyskać więcej informacji o aplikacjach programu VPP, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemów iOS i macOS, które zostały zakupione w ramach programu zakupów zbiorczych firmy Apple](~/apps/vpp-apps-ios.md).

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

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352-wnready-----"></a>Zaktualizowaliśmy dwa ustawienia ograniczeń urządzenia dla urządzeń z systemem iOS i iPadOS, aby skorygować ich zachowanie<!-- 5701352 WNReady   -->
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
Teraz jest dostępna nowa licencja, która umożliwia klientom programu Configuration Manager z pakietem Software Assurance uzyskanie licencji współzarządzanych dla 10 komputerów z systemem Windows 10 bez konieczności zakupu dodatkowej licencji usługi Intune na potrzeby współzarządzania. Klienci nie muszą już przypisywać poszczególnych licencji usługi Intune/EMS do użytkowników końcowych w celu współzarządzania systemem Windows 10.
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

<!-- ########################## -->
## <a name="week-of-october-28-2019"></a>Tydzień 28 października 2019 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Ulepszony projekt listy kontrolnej w aplikacji Portal firmy dla systemu Android<!-- 5550857 -->  
Lista kontrolna konfiguracji w aplikacji Portal firmy dla systemu Android została zaktualizowana za pomocą przystępnego projektu i nowych ikon. Zmiany te idą w parze z najnowszymi aktualizacjami wprowadzonymi w aplikacji Portal firmy dla systemu iOS. Aby zapoznać się z dokładnym porównaniem zmian, zobacz [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md). Aby zapoznać się ze zaktualizowanymi krokami rejestracji, zobacz [Rejestracja przy użyciu profilu służbowego systemu Android](/intune-user-help/enroll-device-android-work-profile) i [Rejestracja urządzeń z systemem Android](/intune-user-help/enroll-device-android-company-portal).  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Aplikacje Win32 na urządzeniach trybu S systemu Windows 10<!-- 3747604 --> 
Aplikacje Win32 można instalować i uruchamiać na urządzeniach zarządzanych trybu S systemu Windows 10. W tym celu można utworzyć jedną lub kilka zasad uzupełniających dla trybu S przy użyciu narzędzi programu PowerShell dla Kontroli aplikacji usługi Windows Defender. Podpisz zasady uzupełniające za pomocą portalu Device Guard — podpisywanie, a następnie przekaż i rozpowszechnij zasady za pośrednictwem usługi Intune. W usłudze Intune tę funkcję można znaleźć, wybierając pozycję **Aplikacje klienckie** > **Zasady uzupełniające systemu Windows 10 S**. Aby uzyskać więcej informacji, zobacz [Włączanie obsługi aplikacji Win32 na urządzeniach trybu S](~/apps/apps-win32-s-mode.md).

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>Ustawianie dostępności aplikacji Win32 na podstawie daty i godziny<!-- 3510685 -->
Jako administrator możesz skonfigurować czas rozpoczęcia i termin ostateczny dla wymaganych aplikacji Win32. W czasie rozpoczęcia rozszerzenie do zarządzania usługi Intune rozpocznie pobieranie zawartości aplikacji i zapisze ją w pamięci podręcznej. Aplikacja zostanie zainstalowana w czasie określonym jako termin ostateczny. W przypadku dostępnych aplikacji czas rozpoczęcia będzie określać, kiedy aplikacja będzie widoczna w Portalu firmy. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami Win32 w usłudze Intune](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Wymaganie ponownego uruchomienia urządzenia na podstawie okresu prolongaty po zainstalowaniu aplikacji Win32<!-- 3136567 -->
Po pomyślnym zainstalowaniu aplikacji Win32 można wymagać ponownego uruchomienia urządzenia. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami Win32 — Konfigurowanie szczegółów instalacji aplikacji](~/apps/apps-win32-app-management.md#step-4-configure-app-installation-details).

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>Tryb ciemny dla aplikacji Portal firmy systemu iOS<!-- 4911422 -->
Tryb ciemny jest dostępny dla aplikacji Portal firmy systemu iOS. Użytkownicy mogą pobierać aplikacje firmowe, zarządzać swoimi urządzeniami i uzyskiwać pomoc techniczną w wybranym przez siebie schemacie kolorów na podstawie ustawień urządzenia. Aplikacja Portal firmy systemu iOS będzie automatycznie dopasowywać ustawienia urządzenia użytkownika końcowego dla trybu ciemnego lub jasnego. Aby uzyskać więcej informacji, zobacz [Wprowadzenie do trybu ciemnego w aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). Aby uzyskać więcej informacji na temat konfigurowania Portalu firmy dla systemu iOS, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>Wymuszanie minimalnej wersji aplikacji Portal firmy w systemie Android<!-- 2378776 -->
Korzystając z ustawienia **Minimalna wersja Portalu firmy** zasad ochrony aplikacji, można określić konkretną minimalną zdefiniowaną wersję aplikacji Portal firmy, która jest wymuszana na urządzeniu użytkownika końcowego. To ustawienie uruchamiania warunkowego umożliwia wykonanie akcji **Blokuj dostęp**, **Wyczyść dane** lub **Ostrzegaj**, kiedy warunek nie zostanie spełniony. Możliwe formaty dla tej wartości są zgodne ze wzorcem *[Wersja główna].[Wersja pomocnicza]* , *[Wersja główna].[Wersja pomocnicza].[Kompilacja]* lub *[Wersja główna].[Wersja pomocnicza].[Kompilacja].[Poprawka]* .

Jeśli ustawienie **Minimalna wersja Portalu firmy** zostanie skonfigurowane, będzie miało wpływ na wszystkich użytkowników końcowych, którzy będą korzystać z wersji 5.0.4560.0 aplikacji Portal firmy i z wszystkich kolejnych wersji. To ustawienie nie będzie miało wpływu na użytkowników korzystających z wersji aplikacji Portal firmy, które są starsze niż wersja, z którą ta funkcja została wydana. Użytkownikom końcowym, którzy na swoich urządzeniach korzystają z automatycznych aktualizacji aplikacji, prawdopodobnie nie zostanie wyświetlone żadne okno dialogowe dotyczące tej funkcji, ponieważ prawdopodobnie będą oni używać najnowszej wersji aplikacji Portal firmy. To ustawienie dotyczy tylko systemu Android z ochroną aplikacji dla zarejestrowanych i niezarejestrowanych urządzeń. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji systemu Android — uruchamianie warunkowe](~/apps/app-protection-policy-settings-android.md#conditional-launch).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->

### <a name="microsoft-365-device-management"></a>Zarządzanie urządzeniami na platformie Microsoft 365

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Wprowadzenie węzła Zabezpieczenia punktu końcowego w obszarze Zarządzanie urządzeniami na platformie Microsoft 365<!-- 5630102 -->

Węzeł **Zabezpieczenia punktu końcowego** jest teraz ogólnie dostępny w specjalistycznym obszarze roboczym Zarządzanie urządzeniami na platformie Microsoft 365 na stronie https://devicemanagement.microsoft.com. Grupuje on możliwości zabezpieczania punktów końcowych, takie jak:

- Punkty odniesienia zabezpieczeń:  Wstępnie skonfigurowana grupa ustawień, która pomaga stosować grupę znanych ustawień i wartości domyślnych zalecanych przez firmę Microsoft.

- Zadania zabezpieczeń: Skorzystaj z zalet funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach w ramach zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender i użyj usługi Intune, aby wyeliminować słabości punktów końcowych.

- Microsoft Defender ATP: Zapobiegaj naruszeniom zabezpieczeń za pomocą zintegrowanej zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender.

Te ustawienia będą nadal dostępne z innych węzłów, takich jak urządzenia, a bieżący skonfigurowany stan będzie taki sam, niezależnie od tego, gdzie będzie uzyskiwany dostęp do tych funkcji i gdzie będą one włączane.

Aby uzyskać więcej informacji na temat tych ulepszeń, zapoznaj się z [wpisem w blogu Sukces klientów usługi Intune](https://aka.ms/Endpoint_security_node) w witrynie społeczności technicznej firmy Microsoft.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>Usługa Intune obsługuje system iOS 11 i nowsze wersje<!-- 4665324  -->

Rejestracja w usłudze Intune i aplikacja Portal firmy obsługują teraz system iOS w wersji 11 lub nowszej. Starsze wersje nie są obsługiwane.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Punkt odniesienia programu Microsoft Edge (wersja zapoznawcza)<!--  3787164  -->

Dodaliśmy wersję zapoznawczą punktu odniesienia zabezpieczeń do [ustawień programu Microsoft Edge](../protect/security-baseline-settings-edge.md). 

<!-- ########################## -->
## <a name="week-of-october-21-2019-1910-service-release"></a>Tydzień 21 października 2019 r. (wersja usługi 1910)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Zarządzanie urządzeniami na platformie Microsoft 365

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Ulepszone środowisko administracyjne w obszarze Zarządzanie urządzeniami na platformie Microsoft 365<!-- 5551239 -->

Odświeżone i usprawnione środowisko administracyjne jest teraz ogólnie dostępne w specjalistycznym obszarze roboczym Zarządzanie urządzeniami na platformie Microsoft 365 na stronie [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com) i obejmuje m.in. następujące funkcje:

- **Zaktualizowana nawigacja**: Uproszczona nawigacja pierwszego poziomu z logicznie pogrupowanymi funkcjami.
- **Nowe filtry platformy**: Można wybrać jedną platformę, która wyświetla tylko zasady i aplikacje dla wybranej platformy, na stronach Urządzenia i Aplikacje.
- **Nowa strona główna**: Na nowej stronie głównej można szybko zobaczyć kondycję usługi, stan dzierżawy, wiadomości itp.

Aby uzyskać więcej informacji na temat tych ulepszeń, zapoznaj się z [wpisem w blogu Enterprise Mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) w witrynie społeczności technicznej firmy Microsoft.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Dodawanie aplikacji usługi Mobile Threat Defense do niezarejestrowanych urządzeń<!-- 3005337 -->
Można utworzyć zasady ochrony aplikacji usługi Intune, które mogą blokować lub selektywnie czyścić dane firmowe użytkownika na podstawie kondycji urządzenia. Kondycja urządzenia jest określana przy użyciu wybranego rozwiązania Mobile Threat Defense (MTD). Ta funkcja istnieje już w przypadku urządzeń zarejestrowanych w usłudze Intune jako ustawienie zgodności urządzenia. Dzięki tej nowej funkcji rozszerzamy wykrywanie zagrożeń od dostawcy rozwiązania Mobile Threat Defense na urządzenia niezarejestrowane. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy zainstalowanej na urządzeniu. W systemie iOS ta funkcja będzie dostępna do użycia, gdy aplikacje zintegrują najnowszy zestaw SDK usługi Intune (wersja 12.0.15+). Zaktualizujemy temat Co nowego, gdy pierwsza aplikacja zastosuje najnowszy zestaw SDK usługi Intune. Pozostałe aplikacje będą udostępniane na bieżąco. Aby uzyskać więcej informacji, zobacz [Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense za pomocą usługi Intune](~/protect/mtd-app-protection-policy.md).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Nowy profil interfejsu konfiguracji oprogramowania układowego urządzenia dla urządzeń z systemem Windows 10 lub nowszym (publiczna wersja zapoznawcza)<!-- 2266073  -->

W systemie Windows 10 i nowszych można utworzyć profil konfiguracji urządzenia w celu kontrolowania ustawień i funkcji (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 i późniejsze** dla platformy). W tej aktualizacji dostępny jest nowy typ profilu interfejsu konfiguracji oprogramowania układowego urządzenia, który umożliwia usłudze Intune zarządzanie ustawieniami interfejsu UEFI (BIOS).

Aby uzyskać więcej informacji na temat tej funkcji, zobacz [Używanie profilów DFCI na urządzeniach z systemem Windows w usłudze Microsoft Intune ](../configuration/device-firmware-configuration-interface-windows.md).

Dotyczy:

- System Windows 10 RS5 (1809) i nowsze z obsługiwanym oprogramowaniem układowym

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Przełączanie w celu wyświetlania tylko strony ze stanem rejestracji na urządzeniach, które są aprowizowane za pomocą środowiska OOBE (Out-of-Box Experience)<!--3959566-->
Teraz można wybrać opcję wyświetlania tylko strony ze stanem rejestracji na urządzeniach aprowizowanych za pomocą środowiska OOBE rozwiązania Autopilot.

Aby wyświetlić nowy przełącznik, wybierz pozycję **Intune** > **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Strona ze stanem rejestracji** > **Utwórz profil** > **Ustawienia** > **Pokaż stronę tylko urządzeniom aprowizowanym za pomocą środowiska out-of-box experience (OOBE)** .


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>Tydzień 14 października 2019 r.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami 

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android<!-- 3041956   -->
W przypadku dostępnych instalacji aplikacji na urządzeniach z profilem służbowym systemu Android Enterprise, dedykowanych i w pełni zarządzanych urządzeń można wyświetlić stan instalacji aplikacji, a także zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](~/apps/app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](~/enrollment/android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](~/apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Microsoft Edge w wersji 77 lub nowszej dla systemu Windows 10 i macOS (publiczna wersja zapoznawcza)<!-- 3872025, 4678761  -->
Program Microsoft Edge w wersji 77 lub nowszej będzie dostępny do wdrażania na komputerach z systemem Windows 10 i macOS. 

Publiczna wersja zapoznawcza oferuje kanały **Dev** oraz **Beta** dla systemu Windows 10 i kanał **Beta** dla systemu macOS. Wdrożenie jest tylko w języku angielskim (EN), jednak użytkownicy końcowi mogą zmienić język wyświetlania w przeglądarce w obszarze **Ustawienia** > **Języki**. Microsoft Edge jest aplikacją systemu Win32 instalowaną w kontekście systemu oraz na takich samych architekturach (aplikacja x86 w systemie operacyjnym x86, a aplikacja x64 w systemie operacyjnym x64). Ponadto automatyczne aktualizacje przeglądarki są domyślnie **Włączone** i programu Microsoft Edge nie można odinstalować. Aby uzyskać więcej informacji, zobacz [Dodawanie programu Microsoft Edge dla systemu Windows 10 do usługi Microsoft Intune](~/apps/apps-windows-edge.md) i [Dokumentacja programu Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823).

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Aktualizowanie do interfejsu użytkownika ochrony aplikacji i interfejsu użytkownika aprowizacji aplikacji systemu iOS<!-- 4102027, 4102029   -->
Interfejs użytkownika służący do tworzenia i edytowania zasad ochrony aplikacji oraz profilów aprowizacji aplikacji dla systemu iOS w usłudze Intune został zaktualizowany. Zmiany interfejsu użytkownika:
- Uproszczone środowisko dzięki użyciu formatu kreatorów skondensowanego w obrębie pojedynczego bloku. 
- Aktualizacja przepływu tworzenia w celu uwzględnienia przypisań.
- Strona podsumowania wszystkich elementów ustawionych podczas wyświetlania właściwości, przed utworzeniem nowych zasad lub podczas edytowania właściwości. Ponadto podczas edytowania właściwości podsumowanie będzie zawierać tylko listę elementów z kategorii właściwości, które są edytowane.

Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](~/apps/app-protection-policies.md) oraz [Korzystanie z profilów aprowizacji aplikacji systemu iOS](~/apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Scenariusze z przewodnikiem dotyczące usługi Intune<!-- 4850318, 4831296, 3610611  -->
Usługa Intune udostępnia teraz scenariusze z przewodnikiem ułatwiające ukończenie określonego zadania lub zestawu zadań w usłudze Intune. Scenariusz z przewodnikiem przedstawia serię dostosowanych kroków (przepływ pracy), które należy wykonać w jednym konkretnym przypadku użycia. Typowe scenariusze są definiowane na podstawie roli, jaką w Twojej organizacji odgrywa administrator, użytkownik lub urządzenie. Te przepływy pracy zwykle wymagają starannego zsynchronizowania profilów, ustawień, aplikacji i opcji zabezpieczeń, aby zapewnić jak najlepsze środowisko użytkownika i skuteczne zabezpieczenia. Nowe scenariusze z przewodnikiem:
- [Wdrażanie przeglądarki Microsoft Edge dla urządzeń przenośnych](~/fundamentals/guided-scenarios-edge.md)
- [Bezpieczne aplikacje mobilne Microsoft Office](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Komputer nowoczesny zarządzany przez chmurę](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Aby uzyskać więcej informacji, zobacz [Scenariusze z przewodnikiem dotyczące usługi Intune — omówienie](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Dostępna jest dodatkowa zmienna konfiguracyjna aplikacji<!-- 4969237   -->
Podczas tworzenia zasad konfiguracji aplikacji można uwzględnić zmienną konfiguracyjną `AAD Device ID` w ustawieniach konfiguracji. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** > **Dodaj**. Wprowadź szczegóły zasad konfiguracji i wybierz pozycję **Ustawienia konfiguracji**, aby wyświetlić blok **Ustawienia konfiguracji**. Aby uzyskać więcej informacji, zobacz [Zasady konfigurowania aplikacji dla zarządzanych urządzeń z systemem Android Enterprise — Korzystanie z projektanta konfiguracji](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>Tworzenie grup obiektów zarządzania nazywanych zestawami zasad<!-- 3762880  -->
Zestawy zasad umożliwiają tworzenie pakietu odwołań do już istniejących jednostek zarządzania, które muszą być identyfikowane, kierowane i monitorowane jako pojedyncza jednostka koncepcyjna. Zestawy zasad nie zastępują istniejących koncepcji ani obiektów. Można nadal przypisywać poszczególne obiekty w usłudze Intune, a także odwoływać się do nich w ramach zestawu zasad. W konsekwencji wszystkie zmiany tych pojedynczych obiektów zostaną odzwierciedlone w zestawie zasad.  W usłudze Intune wybierz pozycję **Zestawy zasad** > **Utwórz**, aby utworzyć nowy zestaw zasad. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Aktualizacja interfejsu użytkownika do tworzenia i edytowania pierścieni aktualizacji systemu Windows 10<!-- 4099089         -->
Zaktualizowaliśmy środowisko interfejsu użytkownika do [tworzenia i edytowania pierścieni aktualizacji systemu Windows 10 ](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) dla usługi Intune. Zmiany w interfejsie użytkownika:  
- Format kreatorów skondensowany w obrębie pojedynczego bloku konsoli, który pozwala pozbyć się natłoku widocznych wcześniej bloków podczas konfigurowania pierścieni aktualizacji.   
- Poprawiony przepływ pracy obejmuje przypisania przed ukończeniem początkowej konfiguracji pierścienia.
- Strona podsumowania, za pomocą której można przejrzeć wszystkie dokonane konfiguracje, przed zapisaniem i wdrożeniem nowego pierścienia aktualizacji. Podczas edytowania pierścienia aktualizacji podsumowanie pokazuje tylko listę elementów ustawionych w ramach kategorii właściwości, które są edytowane.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>Aktualizacja interfejsu użytkownika do tworzenia i edytowania zasad aktualizacji oprogramowania systemu iOS<!-- 4099090       --> 
Zaktualizowaliśmy środowisko interfejsu użytkownika do [tworzenia](../protect/software-updates-ios.md#configure-the-policy) i [edytowania](../protect/software-updates-ios.md#edit-a-policy) zasad aktualizacji oprogramowania systemu iOS dla usługi Intune.  Zmiany w interfejsie użytkownika:  
- Format kreatorów skondensowany w obrębie pojedynczego bloku konsoli, który pozwala pozbyć się natłoku widocznych wcześniej bloków podczas konfigurowania zasad aktualizacji.   
- Poprawiony przepływ pracy obejmuje przypisania przed ukończeniem początkowej konfiguracji zasad.
- Strona podsumowania, za pomocą której można przejrzeć wszystkie dokonane konfiguracje, przed zapisaniem i wdrożeniem nowych zasad. Podczas edytowania zasad podsumowanie pokazuje tylko listę elementów ustawionych w ramach kategorii właściwości, które są edytowane.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404--------"></a>Ustawienia ponownego uruchamiania są usuwane z pierścieni aktualizacji systemu Windows<!--  4464404      -->
Zgodnie z wcześniejszą zapowiedzią, pierścienie aktualizacji systemu Windows 10 w usłudze Intune [obsługują teraz ustawienia terminów ostatecznych](../protect/windows-update-settings.md) i nie obsługują już *ponownego uruchamiania wymagającego interwencji użytkownika*. Ustawienia *ponownego uruchamiania wymagającego interwencji użytkownika* nie są już dostępne podczas konfigurowania pierścieni aktualizacji lub zarządzania nimi w usłudze Intune.  

Ta zmiana jest powiązana z ostatnimi [zmianami obsługi systemu Windows](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing) i na urządzeniach z systemem Windows 10 1903 lub nowszym *terminy ostateczne* zastępują konfiguracje *ponownego uruchamiania wymagającego interwencji użytkownika*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Uniemożliwianie instalacji aplikacji z nieznanych źródeł na urządzeniach z profilami służbowymi systemu Android Enterprise<!-- 4760025   -->
Na urządzeniach z profilami służbowymi systemu Android Enterprise użytkownicy nie mogą instalować aplikacji z nieznanych źródeł. W tej aktualizacji jest dostępne nowe ustawienie — **Uniemożliwianie instalacji aplikacji z nieznanych źródeł w profilu osobistym**. Domyślnie to ustawienie uniemożliwia użytkownikom bezpośrednie ładowanie aplikacji z nieznanych źródeł do profilu osobistego na urządzeniu.

Aby wyświetlić ustawienie, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md).

Dotyczy:

- Android Enterprise — profil służbowy

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Tworzenie globalnego serwera proxy HTTP na urządzeniach właściciela urządzenia z systemem Android Enterprise<!-- 4816339   -->
Na urządzeniach z systemem Android Enterprise można skonfigurować globalny serwer proxy HTTP, aby spełniał standardy przeglądania Internetu w organizacji (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy > **Właściciel urządzenia > Ograniczenia dotyczące urządzeń** dla typu profilu > **Łączność**). Po skonfigurowaniu cały ruch HTTP będzie używać tego serwera proxy.

Aby skonfigurować tę funkcję i wyświetlić wszystkie ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md).

Dotyczy:

- Właściciel urządzenia z systemem Android Enterprise

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>Ustawienie Połącz automatycznie zostanie usunięte z profilów sieci Wi-Fi dla administratora urządzenia z systemem Android i systemu Android Enterprise<!-- 5021055   -->
W przypadku administratora urządzenia z systemem Android i urządzeń z systemem Android Enterprise można utworzyć profil sieci Wi-Fi w celu skonfigurowania różnych ustawień (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Administrator urządzenia z systemem Android** lub **Android Enterprise** dla platformy > **Wi-Fi** dla typu profilu). W ramach tej aktualizacji ustawienie **Połącz automatycznie** zostaje usunięte, ponieważ [nie jest obsługiwane przez system Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Jeśli to ustawienie jest używane w profilu sieci Wi-Fi, można zauważyć, że ustawienie**Połącz automatycznie**  nie działa. Nie trzeba podejmować żadnych działań, ale należy pamiętać, że to ustawienie zostaje usunięte z interfejsu użytkownika usługi Intune.

Aby wyświetlić bieżące ustawienia, przejdź do pozycji [Ustawienia sieci Wi-Fi systemu Android](../configuration/wi-fi-settings-android.md) lub [Ustawienia sieci Wi-Fi systemu Android Enterprise](../configuration/wi-fi-settings-android-enterprise.md).

Dotyczy:

- Administrator urządzenia z systemem Android 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Nowe ustawienia konfiguracji urządzenia dla urządzeń nadzorowanych z systemem iOS i iPadOS<!-- 5199328   -->
Na urządzeniach z systemem iOS i iPadOS można utworzyć profil, aby ograniczyć funkcje i ustawienia na urządzeniach (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). W tej aktualizacji dostępne są nowe ustawienia, którymi można sterować: 
- Dostęp do dysku sieciowego w aplikacji Pliki  
- Dostęp do dysku USB w aplikacji Pliki 
- Sieć Wi-Fi jest zawsze włączona 

Aby zobaczyć te ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:

- System iOS 13.0 i nowsze
- System iPadOS 13.0 i nowsze

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Określenie, które wersje systemu operacyjnego urządzeń z systemem Android rejestrują się przy użyciu profilu służbowego lub rejestracji administratora urządzenia<!-- 4350697   -->
Korzystając z ograniczeń typu urządzenia usługi Intune, można użyć wersji systemu operacyjnego urządzenia, aby określić, które urządzenia użytkownika będą używać rejestracji profilu służbowego systemu Android Enterprise lub rejestracji administratora urządzeń z systemem Android.  Aby uzyskać więcej informacji, zobacz [Konfigurowanie ograniczeń rejestracji](../enrollment/enrollment-restrictions-set.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Nowe ograniczenia dotyczące zmiany nazw urządzeń z systemem Windows<!-- 3478938  -->
Podczas zmiany nazwy urządzenia z systemem Windows należy przestrzegać nowych reguł:
- Może mieć maksymalnie 15 znaków (nie może zajmować więcej niż 63 bajty i na końcu nie może być znaku null)
- Nie może mieć wartości null ani być pustym ciągiem
- Dozwolone znaki ASCII: Litery (a–z, A–Z), cyfry (0–9) i łączniki
- Dozwolone znaki Unicode: znaki muszą mieć wartość co najmniej 0x80, muszą być prawidłowymi znakami UTF8, musi dać się je zamapować na nazwę IDN (tzn. funkcja RtlIdnToNameprepUnicode musi je pomyślnie przetworzyć; zobacz RFC 3492)
- Nazwy nie mogą zawierać samych cyfr
- W nazwie nie może być spacji
- Niedozwolone znaki: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)

 Aby uzyskać więcej informacji, zobacz [Zmienianie nazwy urządzenia w usłudze Intune](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Nowy raport systemu Android na stronie Przegląd urządzeń<!-- 4924364 -->
Nowy raport na stronie Przegląd urządzeń zawiera informacje o liczbie urządzeń z systemem Android zarejestrowanych w poszczególnych rozwiązaniach do zarządzania urządzeniami. Ten wykres przedstawia liczbę urządzeń z profilami służbowymi, w pełni zarządzanych, dedykowanych i zarejestrowanych przez administratora urządzeń. Aby wyświetlić raport, wybierz pozycję **Intune** > **Urządzenia** > **Przegląd**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>Certyfikaty PKCS dla systemu macOS<!-- 1333650       -->
Teraz można już [używać certyfikatów PKCS z ](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) systemem macOS. Certyfikat PKCS można wybrać jako typ profilu dla systemu macOS i wdrożyć certyfikaty użytkowników oraz urządzeń, które mają [niestandardowe pola podmiotu i alternatywnej nazwy podmiotu](../protect/certficates-pfx-configure.md#subject-name-format).  

Certyfikat PKCS dla systemu macOS obsługuje również nowe ustawienie _Zezwalaj na dostęp wszystkim aplikacjom_. Przy użyciu tego ustawienia można umożliwić wszystkim skojarzonym aplikacjom dostęp do klucza prywatnego certyfikatu.  Aby uzyskać więcej informacji na temat tego ustawienia, zobacz dokumentację firmy Apple dostępną po adresem https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>Pochodne poświadczenia do aprowizowania urządzeń przenośnych z systemem iOS przy użyciu certyfikatów<!--  1736036, 1736037, 1772050, 2777333         -->  
Usługa Intune obsługuje możliwość używania [poświadczeń pochodnych](../protect/derived-credentials.md) jako metody uwierzytelniania oraz do podpisywania i szyfrowania przy użyciu protokołu S/MIME dla urządzeń z systemem iOS. Poświadczenia pochodne to implementacja normy *NIST (National Institute of Standards and Technology) 800-157*  na potrzeby wdrażania certyfikatów na urządzeniach.  

Poświadczenia pochodne polegają na wykorzystaniu karty weryfikacji tożsamości osobistej (PIV) lub karty Common Access Card (CAC), takiej jak karta inteligentna. Aby uzyskać poświadczenie pochodne dla swojego urządzenia przenośnego, użytkownicy uruchamiają aplikację Portal firmy i postępują zgodnie z przepływem pracy rejestracji unikatowym dla wykorzystywanego dostawcy.  Wspólne dla wszystkich dostawców jest wymaganie dotyczące użycia karty inteligentnej na komputerze w celu uwierzytelnienia się u dostawcy poświadczeń pochodnych. Ten dostawca wystawia certyfikat dla urządzenia określonego na podstawie karty inteligentnej użytkownika.  

Usługa Intune obsługuje następujących dostawców poświadczeń pochodnych:
- DISA Purebred
- Entrust Datacard
- Intercede

Poświadczenia pochodne są używane jako metoda uwierzytelniania dla profilów konfiguracji urządzeń dla sieci VPN, sieci Wi-Fi i poczty e-mail. Można ich również używać do uwierzytelniania aplikacji oraz podpisywania i szyfrowania za pomocą protokołu S/MIME.  

Aby uzyskać więcej informacji na temat tej normy, zobacz [Poświadczenia pochodne PIV](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) pod adresem www.nccoe.nist.gov.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>Użyj interfejsu API programu Graph, aby określić nazwę główną użytkownika lokalnego jako zmienną dla certyfikatów SCEP<!--  5437939        -->  
W przypadku używania [interfejsu API programu Graph usługi Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) można określić onPremisesUserPrincipalName jako zmienną dla alternatywnej nazwy podmiotu (SAN) na potrzeby certyfikatów SCEP.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Tydzień od 23 września 2019 r.

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Rejestrowanie użytkownika systemu iOS w wersji zapoznawczej<!-- 4817900 -->
System iOS w wersji 13.1 firmy Apple obejmuje rejestrowanie użytkownika, nową formę uproszczonego zarządzania urządzeniami z systemem iOS. Można z niego korzystać zamiast z rejestrowania urządzeń lub automatycznego rejestrowania urządzeń (dawniej Device Enrollment Program) w przypadku urządzeń należących do użytkownika. Wersja zapoznawcza usługi Intune obsługuje ten zestaw funkcji, co pozwala na:

- Ukierunkowanie rejestrowania użytkownika na grupy użytkowników.
- Umożliwienie użytkownikom końcowym wyboru między uproszczonym rejestrowaniem użytkownika a silniejszym rejestrowaniem urządzeń podczas rejestrowania urządzeń.

Od 24 września 2019 r. wraz z wprowadzeniem systemu iOS w wersji 13.1 wdrażamy te aktualizacje dla wszystkich klientów. Przewidujemy, że proces ten zakończy się do końca przyszłego tygodnia.

Dotyczy:

- System iOS 13.1 lub nowszy

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Obsługa usługi Intune dla urządzeń z systemami iPadOS i iOS 13.1<!--5439574-->
Usługa Intune obsługuje obecnie zarządzanie zarówno urządzeniami z systemem iPadOS, jak i iOS 13.1. Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094).

<!-- ########################## -->

## <a name="week-of-september-16-2019-1909-service-release"></a>Tydzień 16 września 2019 r. (wersja usługi 1909)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Zarządzanie aplikacjami 

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Prywatne aplikacje biznesowe z zarządzanego sklepu Google Play<!-- 1464182  -->
Usługa Intune umożliwia teraz administratorom IT publikowanie prywatnych aplikacji biznesowych dla systemu Android w zarządzanym sklepie Google Play za pośrednictwem kontenera iframe osadzonego w konsoli usługi Intune.  Wcześniej administratorzy IT musieli publikować aplikacje biznesowe bezpośrednio w konsoli publikowania Google Play, co wymagało wykonania kilku kroków i było czasochłonne. Ta nowa funkcja umożliwia łatwe publikowanie aplikacji biznesowych przy minimalnej liczbie kroków do wykonania, bez konieczności opuszczania konsoli usługi Intune.  Administratorzy nie muszą już ręcznie rejestrować się jako deweloperzy w Google ani uiszczać za tę rejestrację opłaty w wysokości 25 USD.  Wszystkie scenariusze zarządzania dotyczące systemu Android Enterprise, które wykorzystują zarządzany sklep Google Play, mogą uwzględniać korzystanie z tej funkcji (urządzenia powiązane z profilem służbowym, dedykowane, w pełni zarządzane i nierejestrowane). W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Następnie wybierz pozycję **Zarządzany sklep Google Play** z listy **Typ aplikacji**. Aby uzyskać więcej informacji na temat aplikacji z zarządzanego sklepu Google Play, zobacz [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Korzystanie z aplikacji Portal firmy dla systemu Windows<!-- 1473353, 3598357 -->
Trwa aktualizowanie aplikacji Portal firmy dla systemu Windows. Na stronie Aplikacje w aplikacji Portal firmy dla systemu Windows będzie można używać wielu filtrów. Strona Szczegóły urządzenia także jest aktualizowana w celu zapewnienia udoskonalonego środowiska użytkownika. Wdrażamy te aktualizacje dla wszystkich klientów. Przewidujemy, że proces ten zakończy się do końca przyszłego tygodnia.

#### <a name="macos-support-for-web-apps---3174427---"></a>Obsługa aplikacji internetowych w systemie macOS<!-- 3174427 -->
Aplikacje internetowe umożliwiające dodanie skrótu do adresu URL w Internecie można zainstalować na Docku, używając aplikacji Portal firmy dla systemu macOS. Użytkownicy końcowi mogą uzyskać dostęp do akcji **Instaluj** na stronie szczegółów aplikacji internetowej w aplikacji Portal firmy dla systemu macOS. Aby uzyskać więcej informacji o aplikacjach typu **Link sieci Web**, zobacz artykuł [Dodawanie aplikacji do usługi Microsoft Intune](../apps/apps-add.md) i [Dodawanie aplikacji internetowych do usługi Microsoft Intune](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps---3173501----"></a>Obsługa aplikacji VPP w systemie macOS<!-- 3173501  -->
Aplikacje dla systemu macOS kupione przy użyciu usługi Apple Business Manager są wyświetlane w konsoli, jeśli tokeny programu VPP firmy Apple są synchronizowane w usłudze Intune. Za pomocą konsoli usługi Intune można przypisywać, odwoływać i ponownie przypisywać dotyczące urządzeń i użytkowników licencje dla grup. Usługa Microsoft Intune ułatwia zarządzanie aplikacjami z programu VPP kupionymi do użycia w firmie w następujący sposób:

- Raportowanie informacji o licencji ze sklepu z aplikacjami.
- Śledzenie liczby używanych licencji.
- Pomoc w zapobieganiu instalacji większej liczby kopii aplikacji niż posiadana.

Aby uzyskać więcej informacji na temat usługi Intune i programu VPP, zobacz [Zarządzanie aplikacjami i książkami kupionymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Obsługa kontenera iframe zarządzanego sklepu Google Play<!-- 2871756  -->
Usługa Intune umożliwia teraz dodawanie linków sieci Web i zarządzanie nimi bezpośrednio w konsoli usługi Intune za pośrednictwem kontenera iframe zarządzanego sklepu Google Play.  Dzięki temu administratorzy IT przesyłają adresy URL i grafiki ikon, a następnie wdrażają te linki na urządzeniach tak, jak zrobiliby to ze zwykłymi aplikacjami dla systemu Android. Wszystkie scenariusze zarządzania dotyczące systemu Android Enterprise, które wykorzystują zarządzany sklep Google Play, mogą uwzględniać korzystanie z tej funkcji (urządzenia powiązane z profilem służbowym, dedykowane, w pełni zarządzane i nierejestrowane). W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Następnie wybierz pozycję **Zarządzany sklep Google Play** z listy **Typ aplikacji**. Aby uzyskać więcej informacji na temat aplikacji z zarządzanego sklepu Google Play, zobacz [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>Instalowanie aplikacji biznesowych dla systemu Android na urządzeniach Zebra w trybie dyskretnym<!-- 4252734  -->
Podczas instalowania aplikacji biznesowych dla systemu Android na [urządzeniach Zebra](../configuration/android-zebra-mx-overview.md) nie są wyświetlane monity o pobranie i zainstalowanie aplikacji biznesowych, możliwe jest natomiast zainstalowanie aplikacji w trybie dyskretnym. W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune](../apps/lob-apps-android.md).

Obecnie po pobraniu aplikacji biznesowej na urządzeniu użytkownika zostaje wyświetlone powiadomienie o **pomyślnym pobraniu**. Powiadomienie można usunąć wyłącznie poprzez naciśnięcie przycisku **Wyczyść wszystko** w obszarze powiadomień. Wraz z nadchodzącym wydaniem ten problem z powiadomieniem zostanie rozwiązany, a instalacja stanie się w pełni dyskretna — będzie przebiegać bez jakichkolwiek sygnałów wizualnych.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Operacje odczytu i zapisu interfejsu API programu Graph dla aplikacji usługi Intune<!-- 5031704  -->
Aplikacje mogą wywoływać interfejs API programu Graph dla usługi Intune zarówno przy użyciu operacji odczytu, jak i zapisu, korzystając z tożsamości aplikacji bez poświadczeń użytkownika. Aby uzyskać więcej informacji na temat uzyskiwania dostępu do interfejsu API programu Microsoft Graph dla usługi Intune, zobacz [Praca z usługą Intune w programie Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>Udostępnianie i szyfrowanie chronionych danych na potrzeby zestawu Intune App SDK dla systemu iOS<!-- 3586942  -->
Zestaw SDK aplikacji usługi Intune dla systemu iOS będzie używać 256-bitowych kluczy szyfrowania po włączeniu szyfrowania przy użyciu zasad ochrony aplikacji. Wszystkie aplikacje muszą mieć wersję SDK 8.1.1, aby było w ich przypadku możliwe udostępnianie chronionych danych.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>Obsługa profilów sieci VPN protokołu IKEv2 dla systemu iOS<!-- 1943438   -->
W ramach tej aktualizacji można tworzyć profile sieci VPN dla natywnego klienta sieci VPN systemu iOS za pomocą protokołu IKEv2. IKEv2 to nowy typ połączenia w menu **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **VPN** dla typu profilu > **Typ połączenia**.

Te profile sieci VPN umożliwiają skonfigurowanie natywnego klienta sieci VPN, dzięki czemu żadne aplikacje klienckie sieci VPN nie są instalowane na zarządzanych urządzeniach ani na nie wypychane. Ta funkcja wymaga zarejestrowania urządzeń w usłudze Intune (rejestracji w oprogramowaniu MDM).

Aby wyświetlić bieżące ustawienia sieci VPN, które można skonfigurować, przejdź do pozycji [Konfigurowanie ustawień sieci VPN na urządzeniach z systemem iOS](../configuration/vpn-settings-ios.md).

Dotyczy:

- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>Funkcje urządzeń, ograniczenia dotyczące urządzeń oraz profile rozszerzeń dla ustawień systemu iOS i macOS są wyświetlane według typu rejestracji<!-- 4886161   -->

W usłudze Intune można utworzyć profile dla urządzeń z systemem iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** lub **macOS** dla platformy > **Funkcje urządzeń**, **Ograniczenia dotyczące urządzeń** lub **Rozszerzenia** dla typu profilu). 

W tej aktualizacji ustawienia dostępne w witrynie Intune Portal są podzielone na kategorie według typu rejestracji, którego dotyczą:

- iOS
  - Rejestrowanie użytkownika
  - Rejestrowanie urządzeń
  - Automatyczne rejestrowanie urządzeń (nadzorowane)
  - Wszystkie typy rejestracji

- macOS
  - Zatwierdzone przez użytkownika
  - Rejestrowanie urządzeń
  - Automatyczne rejestrowanie urządzeń
  - Wszystkie typy rejestracji

Dotyczy:

- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Nowe ustawienia sterowania głosowego dla nadzorowanych urządzeń z systemem iOS działających w trybie kiosku<!-- 4892835   -->
W usłudze Intune można tworzyć zasady dotyczące uruchamiania nadzorowanych urządzeń z systemem iOS jako kiosku lub dedykowanego urządzenia (**Konfigurowanie urządzenia** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu > **Kiosk**).

W tej aktualizacji dostępne są nowe ustawienia, którymi można sterować:
- **Sterowanie głosowe**: Pozwala włączyć sterowanie głosowe na urządzeniu działającym w trybie kiosku.
- **Modyfikacja sterowania głosowego**: Zezwól użytkownikom na zmianę ustawienia sterowania głosowego na urządzeniu działającym w trybie kiosku.

Aby wyświetlić bieżące ustawienia, przejdź do [ustawień trybu kiosku systemu iOS](../configuration/device-restrictions-ios.md#kiosk).

Dotyczy:

- System iOS 13.0 lub nowszy

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>Korzystanie z logowania jednokrotnego do aplikacji i witryn sieci Web na urządzeniach z systemem iOS i macOS<!-- 4893175   -->
W tej aktualizacji są dostępne nowe ustawienia logowania jednokrotnego dla urządzeń z systemem iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** lub **macOS** dla platformy > **Funkcje urządzeń** dla typu profilu).

Te ustawienia służą do konfigurowania logowania jednokrotnego, zwłaszcza do aplikacji i witryn sieci Web korzystających z uwierzytelniania Kerberos. Można wybierać pomiędzy rozszerzeniem aplikacji do logowania jednokrotnego przy użyciu poświadczeń rodzajowych a wbudowanym rozszerzeniem protokołu Kerberos firmy Apple.

Aby wyświetlić bieżące funkcje urządzenia, które można skonfigurować, wybierz [Funkcje urządzenia z systemem iOS](../configuration/ios-device-features-settings.md) lub [ Funkcje urządzenia z systemem macOS](../configuration/macos-device-features-settings.md).

Dotyczy:

- System iOS 13.0 i nowsze
- System macOS 10.15 i nowsze

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>Kojarzenie domen z aplikacjami na urządzeniach z systemem macOS w wersji 10.15 lub nowszej<!-- 4898079   -->
Na urządzeniach z systemem macOS można skonfigurować różne funkcje i wypchnąć je do urządzeń przy użyciu zasad (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **macOS** dla platformy > **Funkcje urządzeń** dla typu profilu). W tej aktualizacji można kojarzyć domeny z aplikacjami. Ta funkcja ułatwia udostępnianie poświadczeń witrynom sieci Web, które są powiązane z Twoją aplikacją, i może być używana z rozszerzeniem do logowania jednokrotnego firmy Apple, linkami uniwersalnymi i autowypełnianiem haseł. 

Aby wyświetlić bieżące funkcje, które można skonfigurować, wybierz pozycję [Ustawienia funkcji urządzenia z systemem macOS w usłudze Intune](../configuration/macos-device-features-settings.md).

Dotyczy:

- System macOS 10.15 i nowsze

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>Podczas wyświetlania lub ukrywania aplikacji na nadzorowanych urządzeniach z systemem iOS używaj ciągów „iTunes” i „apps” w adresie URL sklepu iTunes App Store<!-- 4928474   --> 
W usłudze Intune można tworzyć zasady dotyczące wyświetlania lub ukrywania aplikacji na nadzorowanych urządzeniach z systemem iOS (**Konfigurowanie urządzenia** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu > **Pokaż lub ukryj aplikacje**). 

Możesz wprowadzić adres URL sklepu iTunes App Store, na przykład `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. W tej aktualizacji w adresie URL można użyć zarówno ciągu `apps`, jak i `itunes`, na przykład:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Aby uzyskać więcej informacji na temat tych ustawień, zobacz temat [Wyświetlanie lub ukrywanie aplikacji](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Dotyczy:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Wartości typu hasła zasad zgodności systemu Windows 10 są jaśniejsze i spełniają wymogi zgodności dostawcy usług kryptograficznych.<!-- 5138985 -->
Na urządzeniach z systemem Windows 10 można utworzyć zasadę zgodności, która będzie wymagać określonych funkcji hasła (**Zgodność urządzenia** > **Zasady** > **Utwórz zasadę** > **Windows 10 i nowsze** dla platformy > **Zabezpieczenia systemu**). W ramach tej aktualizacji:
- Wartości opcji **Typ hasła** są jaśniejsze i zaktualizowane, a dzięki temu dopasowane do wartości [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- Ustawienie **Wygaśnięcie hasła (dni)** zostało zaktualizowane i umożliwia wybór wartości od 1 do 730 dni. 

Aby uzyskać więcej informacji na temat ustawień zgodności systemu Windows 10, zobacz [Ustawienia systemu Windows 10 i nowszych umożliwiające oznaczenie urządzeń jako zgodnych lub niezgodnych](../protect/compliance-policy-create-windows.md). 

Dotyczy:
- Windows 10 lub nowszym

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Zaktualizowany interfejs użytkownika do konfigurowania dostępu do lokalnego programu Microsoft Exchange<!-- 4092920 -->  
Zaktualizowaliśmy konsolę, w której następuje [konfiguracja dostępu do lokalnego programu Microsoft Exchange](../protect/conditional-access-exchange-create.md). Wszystkie konfiguracje dostępu do lokalnego programu Exchange są teraz dostępne w tym samym okienku konsoli, w którym można użyć opcji *Włącz kontrolę dostępu do lokalnego programu Exchange*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Zezwalanie lub ograniczanie dodawania widżetów aplikacji do ekranu głównego na urządzeniach z systemem Android Enterprise z profilem służbowym<!-- 1109650  --> 
Na urządzeniach z systemem Android Enterprise można skonfigurować funkcje w profilu służbowym (**Konfiguracja urządzenia** > **Profile** ** > Utwórz profil** > **Android Enterprise** dla platformy >  **Tylko profil służbowy > Ograniczenia dotyczące urządzeń** dla typu profilu). Dzięki tej aktualizacji można zezwolić użytkownikom na dodawanie widżetów udostępnionych przez aplikacje profilu służbowego na ekranie głównym urządzenia.

Aby wyświetlić ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md).

Dotyczy:
- Android Enterprise — profil służbowy

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Nowi dzierżawcy będą domyślnie odchodzić od zarządzania urządzeniami z systemem Android przez administratorów<!-- 4869790   -->
Możliwości administratora urządzeń z systemem Android zostały wyparte przez system Android Enterprise. W związku z tym zalecamy korzystanie na potrzeby nowych rejestracji z systemu Android Enterprise. W przyszłej aktualizacji nowi dzierżawcy będą musieli wykonać następujące czynności wstępne wymagane w ramach rejestracji w systemie Android, aby móc korzystać z zarządzania przy użyciu administratora: Wybierz kolejno **Intune** > **Rejestrowanie urządzeń** > **Rejestracja w systemie Android** > **Urządzenia prywatne i należące do firmy z uprawnieniami do administrowania urządzeniami** > **Zarządzaj urządzeniami za pomocą administratora urządzeń**.

W środowisku istniejących dzierżawców nie zostaną wprowadzone żadne zmiany.

Aby uzyskać więcej informacji na temat administratora urządzeń z systemem Android w usłudze Intune, zobacz [Rejestrowanie przy użyciu administratora urządzeń systemu Android](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045-idmiss---"></a>Lista urządzeń DEP skojarzonych z profilem<!-- 5012045 idmiss -->
Teraz można wyświetlić stronicowaną listę urządzeń z programu Automated Device Enrollment Program (DEP) firmy Apple skojarzonych z profilem. Listę można przeszukiwać z poziomu dowolnej strony znajdującej się na liście. Aby wyświetlić listę, wybierz kolejno pozycje **Intune** > **Rejestrowanie urządzeń** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Przypisane urządzenia** (w obszarze **Monitor**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Rozszerzona obsługa w pełni zarządzanych urządzeń z systemem Android<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Dodaliśmy następujące wsparcie dla w pełni zarządzanych urządzeń z systemem Android:

- Certyfikaty protokołu SCEP dla w pełni zarządzanych urządzeń z systemem Android są dostępne do uwierzytelniania z certyfikatem na urządzeniach zarządzanych jako Właściciel urządzenia. Certyfikaty protokołu SCEP są już obsługiwane na urządzeniach z profilami służbowymi.  Certyfikaty protokołu SCEP dla właściciela urządzenia dają następujące możliwości: <!-- 5227935 -->
    - Utworzenie profilu SCEP w sekcji właściciela urządzenia w systemie Android Enterprise
    - Połączenie certyfikatów protokołu SCEP z profilem Wi-Fi właściciela urządzenia na potrzeby uwierzytelniania
    - Połączenie certyfikatów protokołu SCEP z profilami VPN właściciela urządzenia na potrzeby uwierzytelniania
    - Połączenie certyfikatów protokołu SCEP z profilami e-mail właściciela urządzenia na potrzeby uwierzytelniania (przy użyciu pliku AppConfig)
- Aplikacje systemowe są obsługiwane na urządzeniach z systemem Android Enterprise. W usłudze Intune dodaj aplikację systemową dla systemu Android Enterprise, wybierając pozycje **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** wybierz **Aplikacja systemu Android Enterprise**. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji systemu Android Enterprise do usługi Microsoft Intune](../apps/apps-ae-system.md). <!-- 4062195 -->
- W obszarze **Zgodność urządzenia** > **Android Enterprise** > **Właściciel urządzenia** można utworzyć zasadę zgodności określającą poziom zaświadczania Google SafetyNET.   <!-- 4631425 -->
- Na w pełni zarządzanych urządzeniach z systemem Android Enterprise są obsługiwani dostawcy ochrony przed zagrożeniami dla urządzeń przenośnych. W obszarze **Zgodność urządzeń** > **Android Enterprise** > **Właściciel urządzenia** można wybrać akceptowalny poziom zagrożenia. <!-- 4631440 --> Listę bieżących ustawień można znaleźć w artykule [Ustawienia urządzeń z rozwiązaniem Android Enterprise umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune](../protect/compliance-policy-create-android-for-work.md#device-owner).
- Na w pełni zarządzanych urządzeniach z systemem Android Enterprise można teraz skonfigurować aplikację Microsoft Launcher przy użyciu zasad konfiguracji aplikacji w celu umożliwienia korzystania z ustandaryzowanego środowiska użytkownika końcowego na w pełni zarządzanym urządzeniu. Aplikacji Microsoft Launcher można użyć do spersonalizowania urządzenia z systemem Android. Używając aplikacji z kontem Microsoft lub kontem służbowym, można uzyskiwać dostęp do kalendarza, dokumentów i ostatnich działań w spersonalizowanym kanale informacyjnym. <!-- 5334044 -->

Wraz z udostępnieniem tej aktualizacji z przyjemnością ogłaszamy, że usługa Intune jest teraz ogólnodostępna dla w pełni zarządzanych urządzeń z systemem Android Enterprise.

Dotyczy:

- W pełni zarządzane urządzenia z rozwiązaniem Android Enterprise

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Wysyłanie powiadomień niestandardowych do pojedynczego urządzenia<!-- 4928910 -->
Teraz można wybrać jedno urządzenie, a następnie użyć akcji urządzenia zdalnego W celu [wysłania niestandardowego powiadomienia tylko do tego urządzenia](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>Operacje czyszczenia i resetowania kodu dostępu nie są dostępne dla urządzeń z systemem iOS rejestrowanych przy użyciu funkcji rejestracji użytkowników<!-- 4950491 -->
Rejestracja użytkowników to nowy typ rejestracji urządzeń firmy Apple. Dla urządzeń zarejestrowanych przy użyciu funkcji rejestracji użytkowników nie są dostępne akcje zdalnego czyszczenia i resetowania kodu dostępu.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>Obsługa usługi Intune na urządzeniach z systemem iOS 13 i macOS Catalina<!-- 4665317 -->
Usługa Intune obsługuje teraz zarządzanie zarówno urządzeniami z systemem iOS 13, jak i macOS Catalina.
Aby uzyskać więcej informacji, zobacz [wpis w blogu dotyczący obsługi usługi Microsoft Intune na urządzeniach z systemem iOS 13 oraz iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>Obsługa funkcji BitLocker dla sterowanego przez klienta obracania hasła odzyskiwania<!--  3444125 -->
Użyj ustawień usługi Intune Endpoint Protection w celu skonfigurowania [sterowanego przez klienta obracania hasła odzyskiwania](../protect/endpoint-protection-windows-10.md#windows-encryption) dla funkcji BitLocker na urządzeniach z systemem Windows w wersji 1909 lub nowszej.

To ustawienie powoduje zainicjowanie sterowanego przez klienta odświeżania hasła odzyskiwania po odzyskaniu dysku systemu operacyjnego (przy użyciu usługi bootmgr lub WinRE) i odblokowaniu hasła odzyskiwania na stałym dysku danych. To ustawienie powoduje odświeżenie określonego hasła odzyskiwania, które zostało użyte; inne nieużywane hasła z woluminu pozostają niezmienione. Aby uzyskać więcej informacji, zobacz dokumentację dostawcy usług kryptograficznych dotyczącą funkcji BitLocker odnoszącą się do funkcji [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Ochrona przed naruszeniami dla programu antywirusowego Windows Defender<!-- 4705448        -->
Usługi Intune można użyć do zarządzania funkcją *Ochrony przed naruszeniami* programu antywirusowego Windows Defender. [Ustawienie funkcji ochrony przed naruszeniami](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) znajduje się w grupie Centrum zabezpieczeń usługi Microsoft Defender i jest dostępne podczas korzystania z profilów konfiguracji urządzenia; umożliwia ono zapewnianie ochrony punktów końcowych w systemie Windows 10. Dla funkcji ochrony przed naruszeniami można wybrać wartość *Włączona*, aby włączyć ograniczenia ochrony przed naruszeniami, *Wyłączona*, aby wyłączyć funkcję, lub *Nie skonfigurowano*, aby zachować bieżącą konfigurację urządzenia.  

Aby uzyskać więcej informacji na temat ochrony przed naruszeniami, zobacz [Zapobieganie zmianom ustawień zabezpieczeń przy użyciu funkcji ochrony przed naruszeniami](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) w dokumentacji systemu Windows.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>Ustawienia zaawansowane zapory Windows Defender są teraz ogólnie dostępne<!--  5317392       -->  
[Niestandardowe reguły zapory programu Windows Defender](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), które należy skonfigurować w ramach profilu konfiguracji urządzenia, wyszły poza publiczną wersję zapoznawczą i są ogólnie dostępne (GA).  Można użyć tych reguł do określenia zachowania dotyczącego ruchu przychodzącego i wychodzącego na poziomie aplikacji, adresów sieciowych i portów. Te reguły zostały wydane w lipcu w trybie publicznej wersji zapoznawczej. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863-idmiss---"></a>Tagi zakresu obsługują teraz warunki użytkowania<!-- 2358863 idmiss -->
Można teraz przypisać [tagi zakresu](scope-tags.md) do warunków użytkowania. W tym celu wybierz kolejno pozycje **Intune** > **Rejestrowanie urządzeń** > **Warunki** > wybierz element na liście > **Właściwości** > **Tagi zakresu** > wybierz tag zakresu.

## <a name="week-of-september-9-2019"></a>Tydzień od 9 września 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Aktualizacje aplikacji Microsoft Intune<!-- 4997846 -->
Aplikacja Microsoft Intune dla systemu Android została zaktualizowana przy użyciu następujących ulepszeń:
- Zaktualizowano i udoskonalono układ tak, aby uwzględnić dolny obszar nawigacji na potrzeby najważniejszych akcji.
- Dodano dodatkową stronę pokazującą profil użytkownika.
- Dodano wyświetlanie powiadomień z możliwością wykonywania akcji w aplikacji dla użytkownika. Mogą one dotyczyć na przykład konieczności aktualizacji ustawień urządzenia.
- Dodano funkcję wyświetlania niestandardowych powiadomień push, dopasowując aplikację do funkcji pomocy technicznej ostatnio dodanej w aplikacji Portal firmy dla systemów iOS i Android. Aby uzyskać więcej informacji, zobacz [Wysyłanie powiadomień niestandardowych w usłudze Intune](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>Dostosowywanie ekranu prywatności wyświetlanego podczas rejestracji w aplikacji Portal firmy na urządzeniach z systemem iOS<!-- 4394993 -->
Przy użyciu języka Markdown można dostosować ekran prywatności w aplikacji Portal firmy, który użytkownicy końcowi widzą podczas rejestracji w systemie iOS. W tym celu można dostosować listę elementów i działań, których Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu. Aby uzyskać więcej informacji, zobacz artykuł [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>Tydzień od 2 września 2019 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Aktualizacja interfejsu użytkownika usługi Intune — pulpit nawigacyjny stanu dzierżawy<!-- 5273210  -->
Interfejs użytkownika pulpitu nawigacyjnego stanu dzierżawy został zaktualizowany w celu dostosowania do stylów interfejsu użytkownika platformy Azure. Aby uzyskać więcej informacji, zobacz temat [Stan dzierżawy](../tenant-status.md).

## <a name="week-of-august-26-2019"></a>Tydzień od 26 sierpnia 2019 r.

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Konfigurowanie ustawień przeglądarki Microsoft Edge przy użyciu szablonów administracyjnych dla systemu Windows 10 i nowszych<!-- 5228061 -->

Na urządzeniach z systemem Windows 10 lub nowszym można utworzyć szablony administracyjne w celu skonfigurowania ustawień zasad grupy w usłudze Intune. W tej aktualizacji można skonfigurować ustawienia, które mają zastosowanie do przeglądarki Microsoft Edge w wersji 77 lub nowszej.

Aby dowiedzieć się więcej na temat szablonów administracyjnych, zobacz [Konfigurowanie ustawień zasad grupy w usłudze Intune przy użyciu szablonów systemu Windows 10](../configuration/administrative-templates-windows.md).

Dotyczy:

- System Windows 10 i nowsze (Windows RS4 lub nowszy)

## <a name="week-of-august-12-2019-1908-service-release"></a>Tydzień 12 sierpnia 2019 r. (wersja usługi 1908)

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Kontrolowanie zachowania odinstalowywania aplikacji systemu iOS przy wyrejestrowywaniu urządzenia<!-- 3504144   -->
Administratorzy mogą zarządzać tym, czy aplikacja jest usuwana lub zachowywana na urządzeniu, gdy urządzenie jest wyrejestrowywane na poziomie grupy użytkowników lub grupy urządzeń. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Kategoryzowanie aplikacji ze sklepu Microsoft Store dla Firm<!-- 3926922 -->
Możesz kategoryzować aplikacje ze sklepu Microsoft Store dla Firm. W tym celu wybierz kolejno pozycje **Intune** > **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację ze sklepu Microsoft Store dla Firm > **Informacje o aplikacji** > **Kategoria**. W menu rozwijanym przypisz kategorię.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Dostosowane powiadomienia dla użytkowników aplikacji usługi Microsoft Intune<!-- 4843354  -->
Aplikacja usługi Microsoft Intune dla systemu Android obsługuje teraz wyświetlanie niestandardowych powiadomień push, dopasowując ją do funkcji pomocy technicznej ostatnio dodanej w aplikacjach Portal firmy dla systemów iOS i Android. Aby uzyskać więcej informacji, zobacz [Wysyłanie powiadomień niestandardowych w usłudze Intune](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Nowe funkcje dla dedykowanych urządzeń z systemem Android Enterprise w trybie kiosku z wieloma aplikacjami<!-- 3755304 3041943 3041946   -->

W usłudze Intune możesz kontrolować funkcje i ustawienia w środowisku w stylu kiosku na urządzeniach dedykowanych z systemem Android Enterprise (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia, ograniczenia dotyczące urządzeń** jako typ profilu).

W tej aktualizacji są dodawane następujące funkcje:

- **Urządzenia dedykowane** > **Wiele aplikacji**: **Wirtualny przycisk ekranu głównego** można wyświetlić przez szybkie przesunięcie ekranu w górę. Może również być on przyciskiem przestawnym, który użytkownicy mogą przenosić.
- **Urządzenia dedykowane** > **Wiele aplikacji**: **Dostęp do latarki** umożliwia użytkownikom korzystanie z latarki. 
- **Urządzenia dedykowane** > **Wiele aplikacji**: **Regulacja głośności multimediów** umożliwia użytkownikom kontrolowanie głośności multimediów urządzenia przy użyciu suwaka. 
- **Urządzenia dedykowane** > **Wiele aplikacji**:  **Włącz wygaszacz ekranu**, przekaż obraz niestandardowy i określ, kiedy zostanie wyświetlony wygaszacz ekranu.

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [Android Enterprise device settings to allow or restrict features using Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) (Ustawienia urządzeń z systemem Android Enterprise używane w celu zezwolenia na funkcje lub ich ograniczenia za pomocą usługi Intune).

Dotyczy:

- Dedykowane urządzenia z rozwiązaniem Android Enterprise

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Nowe profile aplikacji i konfiguracji dla w pełni zarządzanych urządzeń z systemem Android Enterprise<!-- 3574215 3574238 3574235 3574232   -->
Przy użyciu profilów można skonfigurować ustawienia, które stosują ustawienia sieci VPN, poczty e-mail i sieci Wi-Fi do urządzeń właściciela urządzenia z systemem Android Enterprise (w pełni zarządzanych). W tej aktualizacji możesz:

- Używać [zasad konfiguracji aplikacji](../apps/app-configuration-policies-use-android.md) w celu wdrożenia ustawień poczty e-mail dla programów Outlook, Gmail oraz Nine Work.
- Używać profilów konfiguracji urządzeń w celu wdrożenia [ustawień zaufanych certyfikatów głównych](../protect/certificates-configure.md).
- Używać profilów konfiguracji urządzeń w celu wdrożenia ustawień sieci [VPN](../configuration/vpn-settings-android-enterprise.md) i [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

> [!IMPORTANT]
> Dzięki tej funkcji użytkownicy uwierzytelniają się przy użyciu nazwy użytkownika i hasła na potrzeby profilów sieci VPN, Wi-Fi i poczty e-mail. Obecnie uwierzytelnianie oparte na certyfikatach jest niedostępne.

Dotyczy:  
- Właściciel urządzenia z systemem Android Enterprise (w pełni zarządzanego)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>Kontrolowanie aplikacji, plików, dokumentów i folderów, które są otwierane, gdy użytkownicy logują się do urządzeń z systemem macOS<!--3914202   -->
Na urządzeniach z systemem macOS można włączać i konfigurować funkcje (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **macOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu). 

W tej aktualizacji jest dostępne nowe ustawienie elementów logowania, które umożliwia kontrolowanie aplikacji, plików, dokumentów i folderów otwieranych, gdy użytkownik loguje się do zarejestrowanego urządzenia. 

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [macOS device feature settings in Intune](../configuration/macos-device-features-settings.md) (Ustawienia funkcji urządzeń z systemem macOS w usłudze Intune).

Dotyczy:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Terminy ostateczne zastępują ustawienia ponownego uruchamiania wymagającego interwencji użytkownika dla pierścieni witryny Windows Update<!-- 4464404        -->
W celu dostosowana do najnowszych [zmian obsługi systemu Windows](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing) pierścienie aktualizacji systemu Windows 10 w usłudze Intune [obsługują teraz ustawienia terminów ostatecznych](../protect/windows-update-settings.md). *Terminy ostateczne* określają, kiedy urządzenie instaluje aktualizacje dotyczące funkcji i zabezpieczeń.  Na urządzeniach z systemem Windows 10 1903 lub nowszym *terminy ostateczne* zastępują konfiguracje *ponownego uruchamiania wymagającego interwencji użytkownika*.  W przyszłości *terminy ostateczne* zastąpią również *ponowne uruchamianie wymagające interwencji użytkownika* w starszych wersjach systemu Windows 10.  

Jeśli nie skonfigurujesz *terminów ostatecznych*, urządzenia będą nadal używać ustawień *ponownego uruchamiania wymagającego interwencji użytkownika*, ale obsługa ustawień ponownego uruchamiania wymagającego interwencji użytkownika w usłudze Intune zostanie wycofana w przyszłej aktualizacji.  

Zaplanuj używanie *terminów ostatecznych* dla wszystkich urządzeń z systemem Windows 10. Po wprowadzeniu ustawień *terminów ostatecznych* można zmienić konfiguracje usługi Intune pod kątem *ponownego uruchamiania wymagającego interwencji użytkownika* na Nieskonfigurowane. Po ustawieniu opcji na Nieskonfigurowane usługa Intune przestanie zarządzać tymi ustawieniami na urządzeniach, ale nie usunie ostatnich konfiguracji ustawienia z urządzenia. Z tego względu ostatnie konfiguracje, które zostały ustawione na potrzeby *ponownego uruchamiania wymagającego interwencji użytkownika*, pozostają aktywne i są używane na urządzeniach, dopóki te ustawienia nie zostaną zmodyfikowane przy użyciu metody innej niż usługa Intune. Później w przypadku zmiany wersji systemu Windows lub rozszerzenia obsługi usługi Intune na potrzeby *terminów ostatecznych* na wersję systemu Windows urządzeń urządzenie rozpocznie korzystanie z nowych ustawień, które zostały już wprowadzone.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Obsługa łączników certyfikatów usługi Microsoft Intune<!--   4704642      -->
Usługa Intune obsługuje teraz instalowanie i używanie wielu [łączników certyfikatów usługi Microsoft Intune dla operacji PKCS](../protect/certficates-pfx-configure.md). Ta zmiana obsługuje równoważenie obciążenia i wysoką dostępność łącznika. Każde wystąpienie łącznika może przetwarzać żądania certyfikatów z usługi Intune.  Jeśli jeden łącznik jest niedostępny, inne łączniki kontynuują przetwarzanie żądań.

Aby używać wielu łączników, nie trzeba uaktualniać oprogramowania łącznika do najnowszej wersji.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>Nowe ustawienia i zmiany istniejących ustawień w celu ograniczenia funkcji na urządzeniach z systemem iOS i macOS<!-- 4867699 4867709   -->
Istnieje możliwość utworzenia profilów w celu ograniczenia niektórych ustawień i funkcji na urządzeniach z systemami iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** lub **macOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu). Ta aktualizacja obejmuje następujące funkcje:

- W obszarze **macOS** > **Ograniczenia urządzenia** > **Chmura i magazyn** użyj nowego ustawienia **Przekazanie**, aby blokować możliwość rozpoczynania pracy przez użytkowników na jednym urządzeniu z systemem macOS i kontynuowania na innym urządzeniu z systemem macOS lub iOS.

  Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-macos.md).

- W obszarze **iOS** > **Ograniczenia urządzenia** wprowadzono kilka zmian:

  - **Aplikacje wbudowane** > **Znajdź mój telefon iPhone (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje tę funkcję w funkcji Znajdź moją aplikację. 
  - **Aplikacje wbudowane** > **Znajdź moich znajomych (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje tę funkcję w funkcji Znajdź moją aplikację. 
  - **Bezprzewodowe** > **Modyfikacja stanu sieci Wi-Fi (tylko tryb nadzorowany)** : nowe ustawienie, które uniemożliwia użytkownikom włączanie lub wyłączanie sieci Wi-Fi na urządzeniu.
  - **Klawiatura i słownik** > **QuickPath (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje funkcję QuickPath.
  - **Chmura i magazyn**: nazwa opcji **Kontynuacja aktywności** została zmieniona na **Przekazanie**.

  Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:  
- System macOS 10.15 i nowsze
- System iOS 13 i nowsze

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Niektóre ograniczenia nienadzorowanego urządzenia z systemem iOS zostaną zmienione na tylko nadzorowane w przypadku wersji iOS 13.0<!-- 4867809   -->
W tej aktualizacji niektóre ustawienia mają zastosowanie tylko do nadzorowanych urządzeń z systemem iOS 13.0. Jeśli te ustawienia zostały skonfigurowane i przypisane do urządzeń nienadzorowanych przed wydaniem systemu iOS 13.0, ustawienia są nadal stosowane do tych urządzeń nienadzorowanych. Obowiązują one również po uaktualnieniu urządzeń do systemu iOS 13.0. Ograniczenia są usuwane na urządzeniach nienadzorowanych, których kopie zapasowe są tworzone i przywracane.

Należą do nich następujące ustawienia:

- Sklep App Store, wyświetlanie dokumentów, granie
  - App Store
  - Jawna zawartość programu iTunes — muzyka, podcasty lub wiadomości
  - Dodawanie znajomych do usługi Game Center
  - Gry dla wielu graczy
- Aplikacje wbudowane
  - Aparat fotograficzny
    - FaceTime
  - Safari
    - Autowypełnianie
- Chmura i magazyn
  - Tworzenie kopii zapasowych w usłudze iCloud
  - Blokuj synchronizowanie dokumentów z usługą iCloud
  - Blokuj synchronizowanie pęku kluczy z usługą iCloud

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:  
- System iOS 13.0 i nowsze

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>Ulepszony stan urządzenia na potrzeby szyfrowania FileVault w systemie macOS<!-- 4944983         -->
Zaktualizowaliśmy kilka [komunikatów dotyczących stanu urządzenia](../protect/encryption-monitor.md#device-encryption-status) na potrzeby szyfrowania przy użyciu programu FileVault na urządzeniach z systemem macOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Niektóre ustawienia skanowania programu antywirusowego Windows Defender raportach pokazują stan niepowodzenia<!-- 5119229 -->
W usłudze Intune możesz utworzyć zasady, aby używać programu antywirusowego Windows Defender do skanowania urządzeń z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Program antywirusowy Windows Defender**). Raporty **Godzina przeprowadzania codziennego szybkiego skanowania** i **Typ skanowania systemu do wykonania** pokazują stan niepowodzenia, gdy w rzeczywistości jest to stan sukcesu. 

W tej aktualizacji to zachowanie zostało naprawione. Oznacza to, że ustawienia **Godzina przeprowadzania codziennego szybkiego skanowania** i **Typ skanowania systemu do wykonania** mają stan sukcesu po pomyślnym ukończeniu skanowania i stan niepowodzenia, jeśli zastosowanie ustawień zakończy się niepowodzeniem.

Aby uzyskać więcej informacji na temat ustawień programu antywirusowego, zobacz [Ustawienia urządzeń z systemem Windows 10 (i nowszym) w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="default-scope-tags---3702875----"></a>Domyślne tagi zakresu<!-- 3702875  -->
Nowy, wbudowany domyślny tag zakresu jest teraz dostępny. Wszystkie nieotagowane obiekty usługi Intune, które obsługują tagi zakresu, są automatycznie przypisywane do domyślnego tagu zakresu. **Domyślny** tag zakresu jest dodawany do wszystkich istniejących przypisań ról w celu zapewnienia, że można już korzystać z funkcji administratora. Jeśli nie chcesz, aby administrator widział obiekty usługi Intune z domyślnym tagiem zakresu, usuń domyślny tag zakresu z przypisania roli. Ta funkcja jest podobna do funkcji zakresów zabezpieczeń w programie Configuration Manager. Aby uzyskać więcej informacji, zobacz [Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Obsługa rejestracji administratora urządzeń z systemem Android<!-- 4869749   -->
Opcja rejestracji administratora urządzenia z systemem Android została dodana do strony rejestracji systemu Android (**Intune** > **Rejestracja urządzenia** > **Rejestracja systemu Android**). Administrator urządzenia z systemem Android będzie nadal domyślnie włączony dla wszystkich dzierżaw.  Aby uzyskać więcej informacji, zobacz [Rejestracja administratora urządzeń z systemem Android](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Pomijanie większej liczby ekranów w Asystencie ustawień <!--4877451  -->
Można ustawić profile programu Device Enrollment Program, aby pomijać następujące ekrany Asystenta ustawień:
- Dla systemu iOS
    - Wygląd
    - Język ekspresowy
    - Preferowany język
    - Migracja między urządzeniami
- Dla systemu macOS
    - Czas korzystania z urządzenia
    - Konfiguracja funkcji Touch ID

Aby uzyskać więcej informacji na temat dostosowywania Asystenta ustawień, zobacz [Tworzenie profilu rejestracji Apple dla systemu iOS](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) i [Tworzenie profilu rejestracji Apple dla systemu macOS](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Dodawanie kolumny użytkownika do procesu przekazywania pliku CSV urządzeń rozwiązania Autopilot<!-- 3823054 -->
Teraz można dodać kolumnę użytkownika do procesu przekazywania pliku CSV dla urządzeń rozwiązania Android. Umożliwia to zbiorcze przypisywanie użytkowników w momencie importowania pliku CSV. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Windows w usłudze Intune za pomocą rozwiązania Windows Autopilot](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>Konfigurowanie automatycznego limitu czasu oczyszczania urządzenia na 30 dni<!--4231059  -->
Możesz ustawić automatyczny limit czasu oczyszczania urządzenia na tylko 30 dni (zamiast poprzedniego limitu wynoszącego 90 dni) po ostatnim zalogowaniu. W tym celu przejdź do pozycji **Intune** > **Urządzenia** > **Konfiguracja** > **Reguły czyszczenia urządzeń**.

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Numer kompilacji uwzględniony na stronie Sprzęt urządzenia z systemem Android<!-- 4461910   -->
Nowy wpis na stronie Sprzęt dla każdego urządzenia z systemem Android zawiera numer kompilacji systemu operacyjnego urządzenia. Aby uzyskać więcej informacji, zobacz [Wyświetlanie szczegółów urządzenia w usłudze Intune](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Tydzień od 5 sierpnia 2019 r.

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>Firma Zebra Technologies jest obsługiwanym producentem OEM aplikacji OEMConfig na urządzeniach z systemem Android Enterprise<!-- 4843713 -->

W usłudze Intune możesz utworzyć profile konfiguracji urządzenia i zastosować ustawienia do urządzeń z rozwiązaniem Android Enterprise przy użyciu aplikacji OEMConfig (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **OEMConfig** jako typ profilu).

W tej aktualizacji firma Zebra Technologies jest producentem oryginalnego sprzętu (OEM) dla aplikacji OEMConfig. Aby uzyskać więcej informacji o aplikacji OEMConfig, przejdź do tematu [Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig](../configuration/android-oem-configuration-overview.md).

Dotyczy:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019-1907-service-release"></a>Tydzień 22 lipca 2019 r. (wersja usługi 1907)

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Dostosowane powiadomienia dla użytkowników i grup<!-- 16766574          -->
Wysyłaj niestandardowe powiadomienia push z aplikacji Portal firmy do użytkowników na urządzeniach z systemami iOS i Android zarządzanych przy użyciu usługi Intune. Te mobilne powiadomienia push można w dużym stopniu dostosowywać za pomocą dowolnego tekstu i używać ich w różnorodnych celach. Możesz je kierować do różnych grup użytkowników w swojej organizacji. Aby uzyskać więcej informacji, zobacz [powiadomienia niestandardowe](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app---3041950----"></a>Aplikacja Device Policy Controller firmy Google<!-- 3041950  -->
Aplikacja Managed Home Screen umożliwia teraz dostęp do aplikacji Android Device Policy firmy Google. Aplikacja Managed Home Screen jest niestandardowym modułem uruchamiania używanym w przypadku urządzeń zarejestrowanych w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) w trybie kiosku z wieloma aplikacjami. Aplikacja Android Device Policy może być przydatna zarówno dla Ciebie, jak i Twoich użytkowników w celu uzyskania pomocy technicznej lub przeprowadzenia debugowania. Ta funkcja uruchamiania jest dostępna, gdy urządzenie zostanie zarejestrowane i zablokowane w aplikacji Managed Home Screen. Do korzystania z tej funkcji nie są konieczne żadne dodatkowe instalacje.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>Ustawienia ochrony programu Outlook dla urządzeń z systemami iOS i Android<!-- 3212619 -->
Teraz ogólne ustawienia konfiguracji aplikacji oraz ustawienia konfiguracji ochrony danych dla programu Outlook dla systemów iOS i Android można skonfigurować przy użyciu prostych kontrolek administratora usługi Intune bez rejestracji urządzeń. Ogólne ustawienia konfiguracji aplikacji zapewniają równoważność z ustawieniami, które mogą włączyć administratorzy w przypadku zarządzania programem Outlook dla systemów iOS i Android na urządzeniach zarejestrowanych. Aby uzyskać więcej informacji o ustawieniach programu Outlook, zobacz [Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready------"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 eeready    -->

Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma > **Reguły stosowania**). Dzięki tej aktualizacji będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Aby dodać regułę stosowania, zobacz [Reguły stosowania](../configuration/device-profile-create.md#applicability-rules).

Dotyczy: Windows 10 lub nowszym

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>Używanie tokenów w celu dodawania informacji dotyczących konkretnych urządzeń w profilach niestandardowych dla urządzeń z systemami iOS i macOS<!-- 3330008  -->
Przy użyciu profilów niestandardowych na urządzeniach z systemami iOS i macOS można skonfigurować ustawienia i funkcje, które nie są wbudowane w usłudze Intune (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** lub **macOS** jako platforma > **Niestandardowy** jako typ profilu). Dzięki tej aktualizacji możesz dodawać tokeny do plików `.mobileconfig`, aby dodać informacje dotyczące konkretnych urządzeń. Możesz na przykład dodać token `Serial Number: {{serialnumber}}` do pliku konfiguracji, aby pokazać numer seryjny urządzenia.

Aby utworzyć profil niestandardowy, zobacz [Ustawienia niestandardowe systemu iOS](../configuration/custom-settings-ios.md) lub [Ustawienia niestandardowe systemu macOS](../configuration/custom-settings-macos.md).

Dotyczy:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Nowy projektant konfiguracji podczas tworzenia profilu za pomocą aplikacji OEMConfig dla systemu Android Enterprise<!-- 3712769   -->
W usłudze Intune można utworzyć profil konfiguracji urządzenia, który używa aplikacji OEMConfig (Konfiguracja urządzeń > Profile > Utwórz profil > Android Enterprise jako platforma > OEMConfig jako typ profilu). Po wykonaniu tych czynności zostanie otwarty edytor JSON z szablonem i wartościami, które można zmienić. 

Ta aktualizacja zawiera projektanta konfiguracji z ulepszonym środowiskiem obsługi użytkownika, które pokazuje szczegóły osadzone w aplikacji, w tym tytuły, opisy i inne. Edytor JSON jest nadal dostępny i pokazuje wszelkie zmiany wprowadzone w projektancie konfiguracji.

Aby wyświetlić bieżące ustawienia, przejdź do tematu [Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig](../configuration/android-oem-configuration-overview.md).

Dotyczy: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Zaktualizowany interfejs użytkownika do konfigurowania funkcji Windows Hello<!-- 4089576            -->
Zaktualizowaliśmy konsolę, która służy do [konfigurowania usługi Intune pod kątem korzystania z usługi Windows Hello dla firm](../protect/windows-hello.md). Wszystkie ustawienia konfiguracji są teraz dostępne w tym samym okienku konsoli, w którym włącza się obsługę funkcji Windows Hello.

#### <a name="intune-powershell-sdk---4924113---"></a>Zestaw SDK programu PowerShell usługi Intune<!-- 4924113 --> 
Zestaw SDK programu PowerShell usługi Intune, który zapewnia obsługę interfejsu API usługi Intune za pośrednictwem programu Microsoft Graph, został zaktualizowany do wersji 6.1907.1.0. Zestaw SDK obsługuje teraz następujące funkcje:
- Współpraca z usługą Azure Automation.
- Obsługa operacji odczytu uwierzytelniania tylko aplikacji. 
- Obsługa przyjaznych skróconych nazw jako aliasów.
- Zgodność z konwencjami nazewnictwa programu PowerShell. W szczególności nazwa parametru `PSCredential` (w poleceniu cmdlet `Connect-MSGraph`) została zmieniona na `Credential`.
- Obsługa ręcznego określania wartości nagłówka `Content-Type` w przypadku używania polecenia cmdlet `Invoke-MSGraphRequest`.

Aby uzyskać więcej informacji, zobacz [Zestaw SDK programu PowerShell dla interfejsu API programu Graph usługi Microsoft Intune](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Aktualizacje ograniczeń rejestracji<!-- 2871968 -->
Ograniczenia rejestracji dla nowych dzierżawców zostały zaktualizowane, aby profile służbowe systemu Android Enterprise były domyślnie dozwolone. W przypadku istniejących dzierżawców nie zostaną wprowadzone żadne zmiany. Aby móc używać profilów służbowych systemu Android Enterprise, nadal trzeba [połączyć konto usługi Intune z kontem zarządzanego sklepu Google Play](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>Aktualizacje interfejsu użytkownika dotyczące rejestracji firmy Apple i ograniczeń rejestracji<!--4089575, 4089579  -->
W obu poniższych procesach używany jest interfejs użytkownika w stylu kreatora:
- Rejestracja urządzeń firmy Apple. Aby uzyskać więcej informacji, zobacz [Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program firmy Apple](../enrollment/device-enrollment-program-enroll-ios.md).
- Tworzenie ograniczeń rejestracji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie ograniczeń rejestracji](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509--idmiss---"></a>Obsługa wstępnej konfiguracji identyfikatorów urządzeń firmowych dla urządzeń z systemem Android Q<!-- 4711509  idmiss -->
W systemie Android Q (wersja 10) firma Google usunie możliwość zbierania informacji o identyfikatorze urządzenia przez agentów MDM na urządzeniach z systemem Android zarządzanych w starszy sposób (administrator urządzenia).  Usługa Intune zawiera funkcję, która umożliwia administratorom IT [wstępne skonfigurowanie listy numerów seryjnych lub numerów IMEI urządzeń](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) w celu automatycznego oznakowania tych urządzeń jako należących do firmy. Ta funkcja nie będzie działała w przypadku urządzeń z systemem Android Q, które są zarządzane przez administratora urządzenia.  Bez względu na to, czy numer seryjny lub kod IMEI dla urządzenia zostaną przekazane, będzie ono zawsze traktowane jako osobiste podczas rejestracji w usłudze Intune.  Po rejestracji można ręcznie przełączyć własność na firmę.  Ma to zastosowanie tylko do nowych rejestracji i nie dotyczy istniejących zarejestrowanych urządzeń.  Ta zmiana nie ma wpływu na urządzenia z systemem Android zarządzane przy użyciu profilów służbowych — te urządzenia będą nadal działać tak, jak obecnie.  Ponadto urządzenia z systemem Android Q zarejestrowane jako administrator urządzenia nie będą już mogły zgłaszać numeru seryjnego ani numeru IMEI w konsoli usługi Intune jako właściwości urządzenia.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Zmieniono ikony w procesie rejestracji systemu Android Enterprise (profile służbowe, urządzenia dedykowane i urządzenia w pełni zarządzane)<!-- 4977730 -->
Zmieniono ikony profilów rejestracji systemu Android Enterprise. Aby zobaczyć nowe ikony, wybierz pozycję **Intune** > **Rejestracja** > **Rejestracja systemu Android** i sprawdź w obszarze **Profile rejestracji**.


#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Zmiana zbierania danych diagnostycznych systemu Windows<!-- 4113859 -->
Dla urządzeń z systemem Windows 10 w wersji 1903 lub nowszej wartość domyślna zbierania danych diagnostycznych została zmieniona. Począwszy od systemu Windows 10 w wersji 1903, zbieranie danych diagnostycznych jest domyślnie włączone. Dane diagnostyczne systemu Windows to istotne dane techniczne zbierane z urządzeń z systemem Windows dotyczące urządzenia oraz działania systemu Windows i powiązanego oprogramowania. Aby uzyskać więcej informacji, zobacz [Konfigurowanie danych diagnostycznych systemu Windows w organizacji](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Urządzenia rozwiązania Autopilot również mają włączoną opcję „Full” (Pełne) dla danych telemetrycznych, chyba że w profilu rozwiązania Autopilot określono inaczej za pomocą polecenia [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="improve-device-location---3855417----"></a>Ulepszona lokalizacja urządzenia<!-- 3855417  -->
Przy użyciu akcji **Zlokalizuj urządzenie** można powiększyć lokalizację urządzenia, aby uzyskać jego dokładne współrzędne geograficzne. Aby uzyskać więcej informacji na temat lokalizowania utraconych urządzeń z systemem iOS, zobacz [Znajdowanie utraconych urządzeń z systemem iOS](../remote-actions/device-locate.md).

### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Zaawansowane ustawienia zapory Windows Defender (publiczna wersja zapoznawcza)<!--  1311949     -->  
Przy użyciu usługi Intune można zarządzać [niestandardowymi regułami zapory w ramach profilu konfiguracji urządzenia](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) na potrzeby ochrony punktu końcowego w systemie Windows 10. Reguły te mogą określać zachowanie dotyczące ruchu przychodzącego i wychodzącego na poziomie aplikacji, adresów sieciowych i portów. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Zaktualizowany interfejs użytkownika na potrzeby zarządzania punktami odniesienia zabezpieczeń<!-- 4091125     -->
Zaktualizowaliśmy [środowisko tworzenia i edytowania](../protect/security-baselines.md#create-the-profile) w konsoli usługi Intune dla naszych punktów odniesienia zabezpieczeń. Zmiany te obejmują:

Prostszy format w stylu kreatora, który został skondensowany do pojedynczego bloku. w jednym bloku. Ten nowy projekt pozwala pozbyć się natłoku widocznych jednocześnie bloków, który wymaga od specjalistów IT przechodzenia do szczegółów w kilku oddzielnych okienkach.  
Teraz przypisania można tworzyć w ramach środowiska tworzenia i edytowania, zamiast powracania później w celu przypisania punktów odniesienia. Dodaliśmy podsumowanie ustawień, które można wyświetlić przed utworzeniem nowego punktu odniesienia i podczas edytowania istniejącego punktu odniesienia. Podczas edycji podsumowanie pokazuje tylko listę elementów ustawionych w ramach jednej kategorii właściwości, które są edytowane.

<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Tydzień od 15 lipca 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Ikona aplikacji Managed Home Screen i ikona Ustawienia zarządzane<!-- 4918107 -->
Ikona aplikacji Managed Home Screen i ikona **Ustawienia zarządzane** zostały zaktualizowane. Aplikacja Managed Home Screen jest używana tylko przez urządzenia zarejestrowane w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) i działające w trybie kiosku z wieloma aplikacjami. Aby uzyskać więcej informacji na temat aplikacji Managed Home Screen, zobacz [Konfigurowanie aplikacji Microsoft Managed Home Screen dla rozwiązania Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Aplikacja Android Device Policy na dedykowanych urządzeniach z systemem Android Enterprise<!-- 4918136 -->
Dostęp do aplikacji Android Device Policy można uzyskać z poziomu ekranu debugowania aplikacji Managed Home Screen. Aplikacja Managed Home Screen jest używana tylko przez urządzenia zarejestrowane w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) i działające w trybie kiosku z wieloma aplikacjami. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji Microsoft Managed Home Screen dla rozwiązania Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates---3902931---"></a>Aktualizacje aplikacji Portal firmy w systemie iOS<!-- 3902931 -->
W monitach zarządzania aplikacjami w systemie iOS tekst „i.manage.microsoft.com” zostanie zastąpiony nazwą Twojej firmy. Na przykład użytkownicy będą widzieli nazwę firmy zamiast tekstu „i.manage.microsoft.com”, gdy będą próbować zainstalować aplikację dla systemu iOS z aplikacji Portal firmy lub gdy będą zezwalać na zarządzanie aplikacją. Ta zmiana zostanie wprowadzona u wszystkich klientów w ciągu kilku następnych dni.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>Zarządzanie programem FileVault dla systemu macOS<!--  3858502 + 4557986 + 1210104  -->
Przy użyciu usługi Intune można [zarządzać szyfrowaniem klucza programu FileVault dla urządzeń z systemem macOS](../protect/encrypt-devices.md). Aby szyfrować urządzenia, należy użyć profilu konfiguracji urządzenia ochrony punktu końcowego.

Obsługa programu FileVault obejmuje szyfrowanie niezaszyfrowanych urządzeń, depozyt osobistych kluczy odzyskiwania urządzeń, automatyczną lub ręczną rotację osobistych kluczy szyfrowania oraz pobieranie kluczy dla urządzeń firmowych. Użytkownicy końcowi mogą również przy użyciu witryny Portal firmy pobierać osobiste klucze odzyskiwania dla swoich zaszyfrowanych urządzeń.

Rozszerzyliśmy też raport szyfrowania, aby zawierał [informacje o programie FileVault](../protect/encryption-monitor.md) wraz z informacjami o funkcji BitLocker, dzięki czemu wszystkie szczegóły dotyczące szyfrowania urządzenia są widoczne w jednym miejscu.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>Resetowanie w programie Windows Autopilot usuwa podstawowego użytkownika urządzenia<!-- 4156123 -->
Użycie na urządzeniu resetowania w programie Autopilot spowoduje usunięcie użytkownika podstawowego urządzenia. Następny użytkownik, który zarejestruje się po zresetowaniu, zostanie ustawiony jako użytkownik podstawowy. Ta funkcja zostanie wprowadzona u wszystkich klientów w ciągu kilku następnych dni.

## <a name="week-of-july-8-2019"></a>Tydzień od 8 lipca 2019 r.

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nowe ustawienia pakietu Office, systemu Windows i usługi OneDrive w szablonach administracyjnych systemu Windows 10 <!-- 3510695 -->

W usłudze Intune można utworzyć szablony administracyjne, które naśladują zarządzanie zasadami grupy w środowisku lokalnym (**Zarządzanie urządzeniami** > **Profile** > **Utwórz profil** > **Windows 10 lub nowszy** jako platforma > **Szablon administracyjny** jako typ profilu).

Ta aktualizacja zawiera więcej ustawień pakietu Office, systemu Windows i usługi OneDrive, które można dodać do szablonów. Korzystając z tych nowych ustawień, można teraz skonfigurować ponad 2500 ustawień, które są w 100% oparte na chmurze.

Aby dowiedzieć się więcej na temat tej funkcji, zobacz [Konfigurowania ustawień zasad grupy w usłudze Intune przy użyciu szablonów systemu Windows 10](../configuration/administrative-templates-windows.md).

Dotyczy: Windows 10 lub nowszym

## <a name="week-of-july-1-2019"></a>Tydzień od 1 lipca 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="aad-and-app-on-android-enterprise-devices---3574267---"></a>Usługa AAD i zasady ochrony aplikacji (APP) na urządzeniach z systemem Android Enterprise<!-- 3574267 -->
W przypadku dołączania w pełni zarządzanych urządzeń z systemem Android Enterprise użytkownicy będą teraz rejestrowali się za pomocą usługi Azure Active Directory (AAD) podczas wstępnej konfiguracji nowego urządzenia lub urządzenia zresetowanego do ustawień fabrycznych. Wcześniej w przypadku w pełni zarządzanego urządzenia po zakończeniu konfiguracji użytkownik musiał ręcznie uruchomić aplikację Microsoft Intune, aby rozpocząć rejestrację usługi AAD. Teraz, kiedy po wstępnej konfiguracji zostanie wyświetlona strona główna urządzenia, urządzenie będzie włączone i zarejestrowane.

Poza aktualizacjami usługi AAD, na w pełni zarządzanych urządzeniach z systemem Android Enterprise są teraz obsługiwane zasady ochrony aplikacji usługi Intune (APP, app protection policies). Ta funkcja stanie się dostępna w miarę wdrażania. Aby uzyskać więcej informacji, zobacz [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019-1906-service-release"></a>Tydzień 24 czerwca 2019 r. (wersja usługi 1906)

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Konfigurowanie przeglądarki, którą można połączyć z danymi organizacji<!-- 3145939 -->
Zasady rozwiązania Intune App Protection na urządzeniach z systemami Android i iOS umożliwiają transferowanie linków internetowych organizacji do określonej przeglądarki poza programem Intune Managed Browser lub Microsoft Edge.  Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Strona Wszystkie aplikacje identyfikuje aplikacje w trybie online/offline ze sklepu Microsoft Store dla Firm<!--4089647 -->
Na stronie **Wszystkie aplikacje** jest teraz dostępna etykieta umożliwiająca identyfikację aplikacji ze sklepu Microsoft Store dla Firm (MSFB) jako aplikacji w trybie online lub offline. Każda aplikacja ze sklepu MSFB zawiera teraz sufiks określający tryb **online** lub **offline**. Strona szczegółów aplikacji zawiera również informacje o **typie licencji** i czy aplikacja **obsługuje instalację kontekstu urządzenia** (tylko aplikacje licencjonowane w trybie offline).

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Aplikacja Portal firmy na urządzeniach udostępnionych z systemem Windows<!--4393553 -->
Użytkownicy mogą teraz uzyskiwać dostęp do aplikacji Portal firmy na urządzeniach udostępnionych z systemem Windows. Użytkownicy końcowi będą widzieć etykietę **Udostępnione** na kafelku urządzenia. Dotyczy to aplikacji Portal firmy dla systemu Windows w wersji 10.3.45609.0 i nowszych.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Wyświetlanie wszystkich zainstalowanych aplikacji na nowej stronie internetowej Portal firmy<!-- 4224326 -->
Na nowej stronie **Zainstalowane aplikacje** w witrynie Portal firmy jest dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Oprócz typu przypisania użytkownicy mogą sprawdzić wydawcę, datę opublikowania i bieżący stan instalacji aplikacji. Jeśli nie określono żadnych aplikacji jako wymaganych lub dostępnych dla użytkowników, zobaczą oni komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Aby wyświetlić nową stronę w Internecie, przejdź do [witryny internetowej Portal firmy](https://portal.manage.microsoft.com) i kliknij pozycję **Zainstalowane aplikacje**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>Nowy widok umożliwia użytkownikom aplikacji wyświetlenie wszystkich zarządzanych aplikacji zainstalowanych na urządzeniu<!-- 2352913 -->  
W aplikacji Portal firmy dla systemu Windows jest dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy mogą również wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli nie określono aplikacji jako wymaganych lub dostępnych dla użytkowników, zobaczą oni komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Aby wyświetlić nowy widok, przejdź do okienka nawigacji w aplikacji Portal firmy, a następnie wybierz pozycję **Aplikacje** > **Zainstalowane aplikacje**.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>Konfigurowanie ustawień dotyczących rozszerzeń jądra na urządzeniach z systemem macOS<!-- 2043024 -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę). Ta aktualizacja zawiera nową grupę ustawień, która umożliwia konfigurowanie i używanie rozszerzeń jądra na urządzeniach. Można dodać określone rozszerzenia lub zezwolić na wszystkie rozszerzenia od określonego partnera lub dewelopera.

Aby dowiedzieć się więcej na temat tej funkcji, zobacz [omówienie rozszerzenia jądra](../configuration/kernel-extensions-overview-macos.md) i [ustawienia rozszerzenia jądra](../configuration/kernel-extensions-settings-macos.md).

Dotyczy: macOS 10.13.2 i nowsze

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>Ustawienie Aplikacje tylko ze sklepu dla urządzeń z systemem Windows 10 uwzględnia więcej opcji konfiguracji<!-- 2697002 -->
Podczas tworzenia profilu ograniczeń urządzenia dla urządzeń z systemem Windows można użyć ustawienia **Aplikacje tylko ze sklepu**, aby użytkownicy instalowali tylko aplikacje ze sklepu z aplikacjami dla systemu Windows (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Ograniczenia urządzenia** jako typ profilu). W tej aktualizacji to ustawienie zostało rozszerzone tak, aby obsługiwało więcej opcji.

Aby zobaczyć nowe ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem Windows 10 (i nowszym) umożliwiające działanie funkcji lub ich ograniczanie](../configuration/device-restrictions-windows-10.md#app-store).

Dotyczy: Windows 10 lub nowszym

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Wdrażanie wielu profilów urządzeń przy użyciu funkcji Zebra Mobility Extensions do urządzenia, tej samej grupy użytkowników lub tej samej grupy urządzeń<!-- 4089955 -->
W usłudze Intune przy użyciu funkcji Zebra Mobility Extensions (MX) w profilu konfiguracji urządzenia można dostosować ustawienia dla urządzeń Zebra, które nie są wbudowane w usłudze Intune. Obecnie można wdrożyć jeden profil do jednego urządzenia. W tej aktualizacji można wdrożyć wiele profili dla:
- Tej samej grupy użytkowników
- Tej samej grupy urządzeń
- Pojedynczego urządzenia

Temat [Używanie urządzeń Zebra i zarządzanie nimi za pomocą funkcji Zebra Mobility Extensions w usłudze Microsoft Intune](../configuration/android-zebra-mx-overview.md) przedstawia sposób używania rozszerzeń MX w usłudze Intune.

Dotyczy: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>Niektóre ustawienia kiosku na urządzeniach z systemem iOS są ustawiane przy użyciu pozycji „Blokuj” zastępującej pozycję „Zezwalaj”<!-- 4404075  -->
Po utworzeniu profilu ograniczeń urządzenia na urządzeniach z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Kiosk**) możesz zdefiniować ustawienia **Blokada automatyczna**, **Przełącznik dzwonka**, **Obrót ekranu**, **Przycisk usypiania ekranu** i **Przyciski głośności**.

W tej aktualizacji dostępnymi wartościami są: **Blokuj** (blokowanie funkcji) i **Nieskonfigurowane** (zezwalanie na funkcję). Aby zobaczyć ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie](../configuration/device-restrictions-ios.md#kiosk).

Dotyczy: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>Używanie funkcji Face ID do uwierzytelniania hasła na urządzeniach z systemem iOS<!-- 4490704 -->
Podczas tworzenia profilu ograniczeń urządzenia dla urządzeń z systemem iOS można użyć hasła w postaci odcisku palca. W tej aktualizacji ustawienia hasła w postaci odcisku palca zezwalają również na rozpoznawanie twarzy (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzeń** jak typ profilu > **Hasło**). W wyniku zmieniły się następujące ustawienia:

- **Odblokowywanie za pomocą odcisku palca** to teraz **Odblokowywanie za pomocą funkcji Touch ID i Face ID**.
- **Modyfikacja odcisku palca (tylko w trybie nadzorowanym)** to teraz **Modyfikacja funkcji Touch ID i Face ID (tylko w trybie nadzorowanym)** .

Funkcja Face ID jest dostępna w systemie iOS 11.0 i nowszych wersjach. Aby zobaczyć ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md#password).

Dotyczy: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>Ograniczanie funkcji gier i funkcji sklepu z aplikacjami na urządzeniach z systemem iOS jest teraz zależne od regionu klasyfikacji<!-- 4593948 -->
Na urządzeniach z systemem iOS można zezwolić na lub ograniczyć funkcje związane z grami, sklepem z aplikacjami i wyświetlaniem dokumentów (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Sklep App Store, wyświetlanie dokumentów, granie**). Można również wybrać region klasyfikacji, taki jak Stany Zjednoczone.

W tej aktualizacji funkcja **Aplikacje** została przeniesiona jako element podrzędny do **regionu klasyfikacji** i jest zależna od **regionu klasyfikacji**. Aby zobaczyć ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Dotyczy: iOS

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Obsługa funkcji Windows Autopilot dla dołączania do hybrydowej usługi Azure AD<!-- 4809146-->
Funkcja Windows Autopilot dla istniejących urządzeń obsługuje teraz dołączanie do hybrydowej usługi Azure AD (oprócz istniejącej obsługi dołączania do usługi Azure AD). Dotyczy urządzeń z systemem Windows 10 w wersji 1809 lub nowszej. Aby uzyskać więcej informacji, zobacz [Rozwiązanie Windows Autopilot dla istniejących urządzeń](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Wyświetlanie poziomu poprawki zabezpieczeń dla urządzeń z systemem Android<!-- 4461911 -->
Teraz można zobaczyć poziom poprawki zabezpieczeń dla urządzeń z systemem Android. Aby to zrobić, wybierz pozycję **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**.
Poziom poprawki jest wymieniony w sekcji **System operacyjny**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Przypisywanie tagów zakresu do wszystkich urządzeń zarządzanych w grupie zabezpieczeń<!-- 3173810 -->
Teraz można przypisać tagi zakresu do grupy zabezpieczeń i wszystkie urządzenia w grupie zabezpieczeń również zostaną skojarzone z tymi tagami zakresu. Tag zakresu zostanie również przypisany do wszystkich urządzeń w tych grupach. Tagi zakresu ustawione przy użyciu tej funkcji zastąpią tagi zakresu ustawione przy użyciu bieżącego przepływu tagów zakresu urządzenia. Aby uzyskać więcej informacji, zobacz [Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej](scope-tags.md).

### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="use-keyword-search-with-security-baselines------"></a>Używanie wyszukiwania słów kluczowych z punktami odniesienia zabezpieczeń<!--  -->
Gdy tworzysz lub edytujesz [profile punktu odniesienia zabezpieczeń](../protect/security-baselines.md#create-the-profile), możesz określić słowa kluczowe na nowym pasku *wyszukiwania*, aby odfiltrować dostępne grupy ustawień do tych, które zawierają kryteria wyszukiwania.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>Funkcja Punkty odniesienia zabezpieczeń jest teraz ogólnie dostępna<!-- 3785395 -->
Okres wersji zapoznawczej funkcji **Punkty odniesienia zabezpieczeń** zakończył się i jest ona ogólnie dostępna.  Oznacza to, że funkcja jest gotowa do użycia w środowisku produkcyjnym. Jednak poszczególne szablony punktów odniesienia mogą pozostawać w wersji zapoznawczej — są one oceniane i udostępniane ogólnie zgodnie z ich własnym harmonogramem.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>Szablon punktu odniesienia zabezpieczeń rozwiązania MDM jest teraz ogólnie dostępny<!-- 3794072, 4217151,  3534649 -->
Okres wersji zapoznawczej szablonu punktu odniesienia zabezpieczeń rozwiązania MDM zakończył się i jest on ogólnie dostępny. Ten ogólnie dostępny szablon został określony jako **MDM Security Baseline for May 2019** (Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019).  To jest nowy szablon, a nie uaktualnienie wersji zapoznawczej.  Ponieważ jest to nowy szablon, należy przejrzeć [zawarte w nim ustawienia](../protect/security-baseline-settings-mdm.md), a następnie utworzyć nowe profile, aby wdrożyć szablon na urządzeniu. Inne szablony punktów odniesienia zabezpieczeń mogą pozostać w wersji zapoznawczej. Aby uzyskać listę dostępnych punktów odniesienia, zobacz [Dostępne punkty odniesienia zabezpieczeń](../protect/security-baselines.md#available-security-baselines).  

Poza tym, że jest nowy, szablon *MDM Security Baseline for May 2019* (Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019) zawiera dwa ustawienia, o których informowaliśmy ostatnio w artykule W trakcie opracowywania:  
- Przy włączonej blokadzie: Głosowe aktywowanie aplikacji przy zablokowanym ekranie  
- DeviceGuard: Użycie zabezpieczeń opartych na wirtualizacji (VBS) podczas następnego rozruchu urządzeń.  

W szablonie *MDM Security Baseline for May 2019* (Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019) dodano również kilka nowych, dodatkowych ustawień, usunięto inne oraz zmieniono wartość domyślną jednego ustawienia. Aby uzyskać szczegółową listę zmian między wersją zapoznawczą i ogólnie dostępną, zobacz **Co zmieniło się w nowym szablonie**.

#### <a name="security-baseline-versioning---3194322---"></a>Przechowywanie wersji punktu odniesienia zabezpieczeń<!-- 3194322 -->
Punkty odniesienia zabezpieczeń dla usługi Intune obsługują przechowywanie wersji. Dzięki tej obsłudze, gdy są wydawane nowe wersje każdego punktu odniesienia zabezpieczeń, można zaktualizować istniejące profile punktu odniesienia zabezpieczeń, aby używać nowszej wersji punktu odniesienia, bez konieczności ponownego tworzenia i wdrażania nowego punktu odniesienia od podstaw. Ponadto w konsoli usługi Intune można wyświetlić informacje o poszczególnych punktach odniesienia, takie jak liczba poszczególnych profilów, które używają danego punktu odniesienia, liczba różnych wersji punktu odniesienia używanych przez profile oraz data ostatniego wydania określonego punktu odniesienia zabezpieczeń.  Aby uzyskać więcej informacji, zobacz **Punkty odniesienia zabezpieczeń**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>Ustawienie Użyj kluczy zabezpieczeń do logowania się zostało przeniesione<!-- 4501151 -->
Ustawienie konfiguracji urządzenia na potrzeby ochrony tożsamości o nazwie **Użyj kluczy zabezpieczeń do logowania się** nie jest już dostępne jako ustawienie podrzędne ustawienia *Skonfiguruj funkcję Windows Hello dla firm*. Jest to teraz ustawienie najwyższego poziomu, które jest zawsze dostępne, nawet jeśli nie włączono korzystania z funkcji Windows Hello dla firm. Aby uzyskać więcej informacji, zobacz [Ochrona tożsamości](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Nowe uprawnienia dla przypisanych administratorów grup<!-- 4504437   -->
Wbudowana rola administratora szkoły usługi Intune ma teraz uprawnienia tworzenia, odczytu, aktualizowania i usuwania (CRUD) do aplikacji zarządzanych. Ta aktualizacja oznacza, że jeśli użytkownik jest przypisany jako administrator grupy w usłudze Intune for Education, może teraz tworzyć, wyświetlać, aktualizować i usuwać certyfikat wypychania MDM systemu iOS, tokeny serwera MDM systemu iOS i tokeny programu VPP systemu iOS, a także [wszystkie istniejące posiadane uprawnienia](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Aby wykonać dowolną z tych akcji, przejdź do pozycji **Ustawienia dzierżawy** > **Zarządzanie urządzeniami z systemem iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Aplikacje mogą używać interfejsu API programu Graph do wywoływania operacji odczytu bez poświadczeń użytkownika<!-- 4655885 -->
Aplikacje mogą wywoływać operacje odczytu interfejsu API programu Graph w usłudze Intune przy użyciu tożsamości aplikacji bez poświadczeń użytkownika. Aby uzyskać więcej informacji na temat uzyskiwania dostępu do interfejsu API programu Microsoft Graph dla usługi Intune, zobacz [Praca z usługą Intune w programie Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Stosowanie tagów zakresu do aplikacji ze sklepu Microsoft Store dla Firm<!-- 4392555 -->
Teraz można stosować tagi zakresu do aplikacji ze sklepu Microsoft Store dla Firm. Więcej informacji na temat tagów zakresu można znaleźć w temacie [Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej](scope-tags.md).

## <a name="week-of-june-17-2019"></a>Tydzień od 17 czerwca 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="new-features-in-microsoft-intune-app"></a>Nowe funkcje w aplikacji Microsoft Intune
Dodaliśmy nowe funkcje do aplikacji Microsoft Intune (wersja zapoznawcza) dla systemu Android. Użytkownicy w pełni zarządzanych urządzeń z systemem Android mogą teraz wykonywać następujące czynności:  

* Wyświetlanie urządzeń zarejestrowanych za pomocą Portalu firmy usługi Intune lub aplikacji Microsoft Intune oraz zarządzanie nimi.
* Kontaktowanie się z organizacją w sprawie pomocy technicznej.
* Wysyłanie opinii do firmy Microsoft.
* Wyświetlanie warunków i postanowień, jeśli zostały określone przez organizację.

## <a name="week-of-june-10-2019"></a>Tydzień od 10 czerwca 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>Nowe przykładowe aplikacje przedstawiające integrację zestawu SDK usługi Intune dostępne w usłudze GitHub<!-- 2653471 -->
Do konta msintuneappsdk w usłudze GitHub dodano nowe przykładowe aplikacje dla systemu iOS (Swift), systemu Android, rozszerzenia Xamarin.iOS, rozwiązania Xamarin Forms i rozszerzenia Xamarin.Android. Te aplikacje mają uzupełniać naszą istniejącą dokumentację i oferować pokazy dotyczące integrowania zestawu SDK zasad ochrony aplikacji usługi Intune z własnymi aplikacjami mobilnymi. Jeśli jesteś deweloperem aplikacji, który potrzebuje dodatkowych wskazówek dotyczących zestawu SDK usługi Intune, zobacz poniższe linki do przykładów:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) — natywna aplikacja systemu iOS (Swift) do obsługi wiadomości błyskawicznych, która używa usługi biblioteki Azure Active Directory Authentication Library (ADAL) na potrzeby uwierzytelniania obsługiwanego przez brokera.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) — natywna aplikacja systemu Android do obsługi listy zadań do wykonania, która używa biblioteki ADAL na potrzeby uwierzytelniania obsługiwanego przez brokera.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) — aplikacja rozszerzenia Xamarin.Android do obsługi listy zadań do wykonania, która używa biblioteki ADAL na potrzeby uwierzytelniania obsługiwanego przez brokera. To repozytorium zawiera również aplikację Xamarin.Forms.
- [Przykładowa aplikacja rozszerzenia Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) — podstawowa przykładowa aplikacja rozszerzenia Xamarin.iOS.

## <a name="week-of-may-27-2019"></a>Tydzień od 27 maja 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Raporty dotyczące potencjalnie szkodliwych aplikacji na urządzeniach z systemem Android<!-- 4223162 -->
Usługa Intune udostępnia teraz dodatkowe raporty na temat potencjalnie szkodliwych aplikacji na urządzeniach z systemem Android. 

## <a name="week-of-may-20-2019"></a>Tydzień od 20 maja 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="windows-company-portal-app---3316993---"></a>Aplikacja Portal firmy dla systemu Windows<!-- 3316993 -->
Aplikacja Portal firmy w systemie Windows będzie teraz mieć nową stronę z etykietą **Urządzenia**. Strona **Urządzenia** przedstawia użytkowników końcowych wszystkich zarejestrowanych urządzeń. Użytkownicy zobaczą tę zmianę w Portalu firmy, jeśli korzystają z wersji 10.3.4291.0 lub nowszej. Aby uzyskać informacje na temat konfigurowania Portalu firmy, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Zmieniono nazwę atrybutu OrderID urządzenia rozwiązania Autopilot na tag grupy <!-- 4659453 -->

Aby zwiększyć intuicyjność, zmieniono nazwę atrybutu **OrderID** w urządzeniach rozwiązania Autopilot na **Tag grupy**. W przypadku przekazywania informacji o urządzeniu rozwiązania Autopilot za pomocą plików CSV jako nagłówka kolumny należy użyć tagu grupy, a nie atrybutu OrderID.  

## <a name="week-of-may-13-2019-1905-service-release"></a>Tydzień 13 maja 2019 r. (wersja usługi 1905)

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Zasady usługi Intune aktualizują metodę uwierzytelniania i instalację aplikacji Portal firmy<!-- 1927359  -->
Na urządzeniach, które zostały już zarejestrowane za pomocą Asystenta ustawień przy użyciu jednej z metod rejestracji urządzeń firmowych firmy Apple, usługa Intune nie będzie już obsługiwać aplikacji Portal firmy po jej ręcznym zainstalowaniu ze sklepu z aplikacjami przez użytkowników końcowych. Ta zmiana ma zastosowanie tylko w sytuacji, w której uwierzytelnianie jest przeprowadzane przy użyciu asystenta ustawień firmy Apple podczas rejestracji. Ta zmiana dotyczy tylko urządzeń z systemem iOS zarejestrowanych przy użyciu następujących rozwiązań:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Jeśli użytkownicy zainstalują aplikację Portal firmy ze sklepu z aplikacjami, a następnie podejmą próbę zarejestrowania urządzeń przy jej użyciu, wystąpi błąd. Oczekuje się, że te urządzenia będą używać aplikacji Portal firmy tylko w sytuacji, gdy nastąpi automatyczne wypchnięcie przez usługę Intune podczas rejestracji. Profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane tak, aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Jeśli chcesz, aby użytkownicy urządzenia DEP mieli aplikację Portal firmy, musisz określić swoje preferencje w profilu rejestracji. 

Ponadto ekran **Identyfikowanie urządzenia** w aplikacji Portal firmy dla systemu iOS jest usuwany. W związku z tym administratorzy, którzy chcą włączyć dostęp warunkowy lub wdrażać aplikacje firmowe, muszą zaktualizować profil rejestracji w programie DEP. To wymaganie ma zastosowanie tylko, jeśli rejestracja w programie DEP jest uwierzytelniana przy użyciu Asystenta ustawień. W takim przypadku należy wypchnąć aplikację Portal firmy do urządzenia. W tym celu wybierz pozycję **Intune** > **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Właściwości** > ustaw pozycję **Zainstaluj Portal firmy** na wartość **Tak**.

Aby zainstalować Portal firmy na już zarejestrowanych urządzeniach objętych programem DEP, należy przejść do usługi Intune > Aplikacje klienckie i wypchnąć ją jako aplikację zarządzaną przy użyciu zasad konfiguracji aplikacji. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Konfigurowanie sposobu aktualizowania aplikacji biznesowej (LOB) przez użytkowników końcowych przy użyciu zasad ochrony aplikacji<!-- 3568384 -->
Teraz w konfiguracji można określić, gdzie użytkownicy końcowi mogą uzyskać zaktualizowaną wersję aplikacji biznesowych (LOB). Użytkownicy końcowi będą widzieli tę funkcję w oknie dialogowym warunkowego uruchamiania **minimalnej wersji aplikacji**, które wyświetli monit o aktualizację do minimalnej wersji aplikacji LOB przez użytkownika końcowego. Te szczegółowe informacje dotyczące aktualizacji należy podać w ramach zasad ochrony aplikacji LOB. Ta funkcja jest dostępna w systemie iOS i Android. W systemie iOS ta funkcja wymaga zintegrowania aplikacji (lub opakowania za pomocą narzędzia opakowującego) z zestawem SDK usługi Intune dla systemu iOS w wersji 10.0.7 lub nowszej. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy. Aby skonfigurować sposób, w jaki użytkownik końcowy aktualizuje aplikację LOB, zasady konfiguracji aplikacji zarządzanej muszą zostać wysłane do aplikacji przy użyciu klucza, `com.microsoft.intune.myappstore`. Wysłana wartość określi, z którego sklepu użytkownik końcowy pobierze aplikację. Jeśli aplikacja jest wdrażana za pośrednictwem Portalu firmy, wartość musi być równa `CompanyPortal`. W przypadku każdego innego sklepu należy wprowadzić pełny adres URL.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Skrypty programu PowerShell rozszerzające zarządzanie w ramach usługi Intune<!-- 3734186  -->
Skrypty programu PowerShell można skonfigurować do uruchamiania z uprawnieniami administratora na urządzeniu. Aby uzyskać więcej informacji, zobacz [Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune](../apps/intune-management-extension.md) i [Zarządzanie aplikacjami Win32](../apps/app-management.md).

#### <a name="android-enterprise-app-management---4459905---"></a>Zarządzanie aplikacjami w usłudze Android Enterprise<!-- 4459905 -->
Aby ułatwić administratorom IT konfigurowanie i używanie zarządzania w usłudze Android Enterprise, cztery typowe aplikacje związane z usługą Android Enterprise zostaną automatycznie dodane do konsoli administracyjnej usługi Intune. Są to następujące cztery aplikacje w usłudze Android Enterprise:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** — używana w scenariuszach w pełni zarządzanych za pomocą Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** — pomaga zalogować się do kont w przypadku używania weryfikacji dwuskładnikowej.
- **[Intune — Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** — używana w przypadku scenariuszy obejmujących zasady ochrony aplikacji i profil służbowy Android Enterprise.
- [Zarządzany ekran główny](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) — używana w scenariuszach z użyciem Android Enterprise dla urządzeń dedykowanych/działających w trybie kiosku.

Wcześniej administratorzy IT musieli ręcznie znajdować i zatwierdzać te aplikacje w [zarządzanym sklepie Google Play](https://play.google.com/store/apps) w ramach procesu konfigurowania. Ta zmiana eliminuje te wcześniej wykonywane ręcznie kroki, aby klienci mogli łatwiej i szybciej zacząć korzystać z zarządzania w ramach usługi Android Enterprise.

Administratorzy zobaczą te cztery aplikacje automatycznie dodane do listy aplikacji usługi Intune podczas pierwszego połączenia swojego dzierżawcy usługi Intune z zarządzanym sklepem Google Play. Aby uzyskać więcej informacji, zobacz [Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play](../enrollment/connect-intune-android-enterprise.md). W przypadku dzierżawców, dla których już nawiązano połączenie lub rozpoczęto korzystanie z usługi Android Enterprise, administratorzy nie muszą nic robić. Te cztery aplikacje automatycznie staną się widoczne w ciągu 7 dni od ukończenia wdrożenia usługi w maju 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Zaktualizowany łącznik certyfikatów PFX dla usługi Microsoft Intune<!-- 1533038 -->
Udostępniliśmy aktualizację [łącznika certyfikatów PFX dla usługi Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors), aby rozwiązać problem polegający na tym, że istniejące certyfikaty PFX były nadal ponownie przetwarzane, co powodowało zatrzymywanie przetwarzania nowych żądań przez łącznik.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Zadania zabezpieczeń usługi Intune dotyczące zaawansowanej ochrony przed zagrożeniami usługi Defender (w publicznej wersji zapoznawczej)<!-- 3208597 -->
W publicznej wersji zapoznawczej można używać usługi Intune do zarządzania zadaniami zabezpieczeń dla [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](../protect/atp-manage-vulnerabilities.md). Dzięki integracji z Zaawansowaną ochroną przed zagrożeniami jest dodawane oparte na ryzyku podejście do odnajdywania, priorytetyzowania oraz korygowania luk w zabezpieczeniach i błędów konfiguracji punktów końcowych przy jednoczesnym skróceniu czasu między odnalezieniem i ograniczeniem ryzyka.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671-----"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10<!-- 3617671   -->
Wiele urządzeń z systemem Windows 10 lub nowszym zawiera mikroukład modułu TPM (Trusted Platform Module). Ta aktualizacja obejmuje nowe ustawienie zgodności, które sprawdza wersję mikroukładu modułu TPM na urządzeniu.

To ustawienie jest opisane w artykule [Ustawienia zasad zgodności urządzeń z systemem Windows 10 lub nowszym](../protect/compliance-policy-create-windows.md#device-security).

Dotyczy: Windows 10 lub nowszym

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Uniemożliwianie użytkownikom końcowym modyfikowania ich osobistego hotspotu i wyłączanie rejestrowania programu Siri na urządzeniach z systemem iOS<!-- 4097904   -->  
Dla urządzenia z systemem iOS można utworzyć profil ograniczeń urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia, które można skonfigurować:

- **Aplikacje wbudowane**: rejestrowanie po stronie serwera na potrzeby poleceń programu Siri
- **Sieć bezprzewodowa**: modyfikowanie osobistego hotspotu przez użytkownika (tylko tryb nadzorowany)

Aby wyświetlić te ustawienia, przejdź do [wbudowanych ustawień aplikacji dla systemu iOS](../configuration/device-restrictions-ios.md#built-in-apps) i [ustawień sieci bezprzewodowej dla systemu iOS](../configuration/device-restrictions-ios.md#wireless).

Dotyczy: system iOS 12.2 i nowsze

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>Nowe ustawienia ograniczeń urządzeń w aplikacji Klasa dotyczące urządzeń z systemem macOS<!-- 4097905   --> 
Na urządzeniach z systemem macOS można utworzyć profile konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia aplikacji Klasa, opcję blokowania zrzutów ekranu oraz opcję wyłączania biblioteki zdjęć iCloud.

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-macos.md).

Dotyczy: systemu macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Nazwa ustawienia Hasło dostępu do sklepu z aplikacjami w systemie iOS została zmieniona<!-- 4557891  -->
Nazwa ustawienia **Hasło dostępu do sklepu z aplikacjami** została zmieniona na **Wymagaj hasła sklepu iTunes dla wszystkich zakupów** (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzeń** jako typ profilu > **Sklep App Store, wyświetlanie dokumentów i granie**).

Aby wyświetlić dostępne ustawienia, przejdź do sekcji [Ustawienia systemu iOS dla sklepu App Store, wyświetlanie dokumentów i granie](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Dotyczy: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Punkty odniesienia usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (wersja zapoznawcza)<!--  3754134 -->
Dodaliśmy wersję zapoznawczą punktów odniesienia zabezpieczeń dla ustawień usługi [Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender](../protect/security-baseline-settings-defender-atp.md). Ten punkt odniesienia jest dostępny, jeśli środowisko spełnia wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>Strona ze stanem rejestracji w systemie Windows jest teraz ogólnie dostępna<!-- 3605348 -->
Okres obowiązywania wersji zapoznawczej strony ze stanem rejestracji zakończył się. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Aktualizacja interfejsu użytkownika usługi Intune — tworzenie profilu rejestracji rozwiązania Autopilot<!-- 4593669 -->
Interfejs użytkownika służący do tworzenia profilu rejestracji rozwiązania Autopilot został zaktualizowany w celu dostosowania do stylów interfejsu użytkownika platformy Azure. Aby uzyskać więcej informacji, zobacz [Create an Autopilot enrollment profile](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) (Tworzenie profilu rejestracji rozwiązania Autopilot). W przyszłości dodatkowe scenariusze usługi Intune zostaną zaktualizowane do tego nowego stylu interfejsu użytkownika.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Włączanie resetowania rozwiązania Autopilot dla wszystkich urządzeń z systemem Windows<!-- 4225665 -->
Resetowanie rozwiązania Autopilot działa teraz dla wszystkich urządzeń Windows, nawet tych, które nie zostały skonfigurowane do używania strony ze stanem rejestracji. Jeśli strona ze stanem rejestracji nie została skonfigurowana na tym urządzeniu podczas początkowej rejestracji urządzenia, po zalogowaniu do urządzenia nastąpi bezpośrednie przejście do pulpitu. Synchronizacja urządzenia i wyświetlenie go jako zgodnego w usłudze Intune może potrwać do ośmiu godzin. Aby uzyskać więcej informacji, zobacz [Resetowanie urządzeń przy użyciu zdalnego resetowania rozwiązania Autopilot w systemie Windows](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>Dokładny format numerów IMEI niewymagany w przypadku wyszukiwania wszystkich urządzeń<!--30407680 -->
W przypadku wyszukiwania **wszystkich urządzeń** nie trzeba uwzględniać spacji w numerach IMEI.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Usunięcie urządzenia w portalu firmy Apple zostanie odzwierciedlone w portalu usługi Intune<!--2489996 -->
Jeśli urządzenie zostanie usunięte z portalu usługi Device Enrollment Program firmy Apple lub portalu Apple Business Manager, to zostanie też automatycznie usunięte z usługi Intune podczas następnej synchronizacji.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>Strona Stan rejestracji śledzi teraz aplikacje Win32<!-- 2714451 -->
Dotyczy to tylko urządzeń z systemem Windows 10 w wersji 1903 lub nowszej. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Zbiorcze resetowanie i czyszczenie urządzeń za pomocą interfejsu API programu Graph<!-- 3295288 -->
Za pomocą interfejsu API programu Graph można teraz zbiorczo zresetować i wyczyścić do 100 urządzeń.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>Okres obowiązywania wersji zapoznawczej raportu szyfrowania zakończył się<!-- 4587546      -->
[Raport dotyczący szyfrowania funkcją BitLocker i szyfrowania urządzenia](../protect/encryption-monitor.md) jest teraz ogólnie dostępny i nie jest już częścią publicznej wersji zapoznawczej.

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>Ustawienia biometryczne i ustawienia podpisu programu Outlook dla urządzeń z systemami iOS i Android<!-- 4050557 -->
Teraz można określić, czy podpis domyślny jest włączony w programie Outlook na urządzeniach z systemem iOS i Android. Ponadto można zezwolić użytkownikom na zmianę ustawienia biometrycznego w programie Outlook w systemie iOS.

## <a name="week-of-may-6-2019"></a>Tydzień od 6 maja 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>Obsługa kontrolo dostępu do sieci (NAC) dla aplikacji F5 Access dla urządzeń z systemem iOS<!-- 4500808 -->

Firma F5 opublikowała aktualizację systemu BIG-IP 13 udostępniającą funkcje kontroli dostępu do sieci dla aplikacji F5 Access w systemie iOS w usłudze Intune. Aby użyć tej funkcji:

- Zaktualizuj system BIG-IP do odświeżonej wersji 13.1.1.5. System BIG-IP w wersji 14 nie jest obsługiwany.
- Zintegrować system BIG-IP z usługą Intune, aby móc korzystać z kontroli dostępu do sieci. Kroki opisano na stronie [Omówienie: Konfigurowanie programu APM pod kątem kontroli stanu urządzenia za pomocą systemów zarządzania punktem końcowym](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Sprawdź ustawienie **Włącz kontrolę dostępu do sieci (NAC)** w profilu sieci VPN w usłudze Intune.

Aby wyświetlić dostępne ustawienia, przejdź na stronę [Konfigurowanie ustawień sieci VPN w urządzeniach z systemem iOS](../configuration/vpn-settings-ios.md).

Dotyczy: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Zaktualizowany łącznik certyfikatów PFX dla usługi Microsoft Intune<!-- doc-vso 1521237  -->  
Udostępniliśmy aktualizację [łącznika certyfikatów PFX dla usługi Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors), która skraca odstęp czasu sondowania z 5 minut do 30 sekund.




## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
