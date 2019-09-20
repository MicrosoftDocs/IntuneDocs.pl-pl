---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7b7b4453d441d2f2367b19a6bf0505dabd8e6e48
ms.sourcegitcommit: 27e63a96d15bc4062af68c2764905631bd928e7b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2019
ms.locfileid: "71061679"
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz tu również znaleźć [ważne powiadomienia](#notices), [poprzednie wydania](whats-new-archive.md) oraz informacje na temat [sposobu wydawania aktualizacji usługi Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Wprowadzanie każdej [aktualizacji miesięcznej](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) może potrwać do trzech dni i będzie przeprowadzane w następującej kolejności:
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

## <a name="week-of-september-16-2019"></a>Tydzień od 16 września 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="macos-support-for-web-apps----3174427---"></a>Obsługa aplikacji internetowych w systemie macOS <!-- 3174427 -->
Aplikacje internetowe umożliwiające dodanie skrótu do adresu URL w Internecie można zainstalować na Docku, używając aplikacji Portal firmy dla systemu macOS. Użytkownicy końcowi mogą uzyskać dostęp do akcji **Instaluj** na stronie szczegółów aplikacji internetowej w aplikacji Portal firmy dla systemu macOS. Aby uzyskać więcej informacji o aplikacjach typu **Link sieci Web**, zobacz artykuł [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md) i [Dodawanie aplikacji internetowych do usługi Microsoft Intune](web-app.md).

#### <a name="macos-support-for-vpp-apps----3173501----"></a>Obsługa aplikacji VPP w systemie macOS <!-- 3173501  -->
Aplikacje dla systemu macOS kupione przy użyciu usługi Apple Business Manager są wyświetlane w konsoli, jeśli tokeny programu VPP firmy Apple są synchronizowane w usłudze Intune. Za pomocą konsoli usługi Intune można przypisywać, odwoływać i ponownie przypisywać dotyczące urządzeń i użytkowników licencje dla grup. Usługa Microsoft Intune ułatwia zarządzanie aplikacjami z programu VPP kupionymi do użycia w firmie w następujący sposób:
- Raportowanie informacji o licencji ze sklepu z aplikacjami.
- Śledzenie liczby używanych licencji.
- Pomoc w zapobieganiu instalacji większej liczby kopii aplikacji, niż jest posiadana.

Aby uzyskać więcej informacji na temat usługi Intune i programu VPP, zobacz [Zarządzanie aplikacjami i książkami kupionymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](vpp-apps.md).

## <a name="week-of-september-9-2019"></a>Tydzień od 9 września 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="updates-to-microsoft-intune-app----4997846---"></a>Aktualizacje aplikacji Microsoft Intune <!-- 4997846 -->
Aplikacja Microsoft Intune dla systemu Android została zaktualizowana przy użyciu następujących ulepszeń:
- Zaktualizowano i udoskonalono układ tak, aby uwzględnić dolny obszar nawigacji na potrzeby najważniejszych akcji.
- Dodano dodatkową stronę pokazującą profil użytkownika.
- Dodano wyświetlanie powiadomień z możliwością wykonywania akcji w aplikacji dla użytkownika. Mogą one dotyczyć na przykład konieczności aktualizacji ustawień urządzenia.
- Dodano funkcję wyświetlania niestandardowych powiadomień push, dopasowując aplikację do funkcji pomocy technicznej ostatnio dodanej w aplikacji Portal firmy dla systemów iOS i Android. Aby uzyskać więcej informacji, zobacz [Wysyłanie powiadomień niestandardowych w usłudze Intune](custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993---"></a>Dostosowywanie ekranu prywatności wyświetlanego podczas rejestracji w aplikacji Portal firmy na urządzeniach z systemem iOS <!-- 4394993 -->
Przy użyciu języka Markdown można dostosować ekran prywatności w aplikacji Portal firmy, który użytkownicy końcowi widzą podczas rejestracji w systemie iOS. W tym celu można dostosować listę elementów i działań, których Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu. Aby uzyskać więcej informacji, zobacz artykuł [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>Tydzień od 2 września 2019 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-user-interface-update--tenant-status-dashboard-----5273210----"></a>Aktualizacja interfejsu użytkownika usługi Intune — pulpit nawigacyjny stanu dzierżawy  <!-- 5273210  -->
Interfejs użytkownika pulpitu nawigacyjnego stanu dzierżawy został zaktualizowany w celu dostosowania do stylów interfejsu użytkownika platformy Azure. Aby uzyskać więcej informacji, zobacz temat [Stan dzierżawy](tenant-status.md).


## <a name="week-of-august-26-2019"></a>Tydzień od 26 sierpnia 2019 r.

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer----5228061---"></a>Konfigurowanie ustawień przeglądarki Microsoft Edge przy użyciu szablonów administracyjnych dla systemu Windows 10 i nowszych <!-- 5228061 -->

Na urządzeniach z systemem Windows 10 lub nowszym można utworzyć szablony administracyjne w celu skonfigurowania ustawień zasad grupy w usłudze Intune. W tej aktualizacji można skonfigurować ustawienia, które mają zastosowanie do przeglądarki Microsoft Edge w wersji 77 lub nowszej.

Aby dowiedzieć się więcej na temat szablonów administracyjnych, zobacz [Konfigurowanie ustawień zasad grupy w usłudze Intune przy użyciu szablonów systemu Windows 10](administrative-templates-windows.md).

Dotyczy:

- System Windows 10 i nowsze (Windows RS4 lub nowszy)

## <a name="week-of-august-12-2019"></a>Tydzień od 12 sierpnia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144-----"></a>Kontrolowanie zachowania odinstalowywania aplikacji systemu iOS przy wyrejestrowywaniu urządzenia <!-- 3504144   -->
Administratorzy mogą zarządzać tym, czy aplikacja jest usuwana lub zachowywana na urządzeniu, gdy urządzenie jest wyrejestrowywana na poziomie grupy użytkowników lub grupy urządzeń. 

#### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Kategoryzowanie aplikacji ze sklepu Microsoft Store dla Firm <!-- 3926922 -->
Możesz kategoryzować aplikacje ze sklepu Microsoft Store dla Firm. W tym celu wybierz kolejno pozycje **Intune** > **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację ze sklepu Microsoft Store dla Firm > **Informacje o aplikacji** > **Kategoria**. W menu rozwijanym przypisz kategorię.

#### <a name="customized-notifications-for-microsoft-intune-app-users----4843354----"></a>Dostosowane powiadomienia dla użytkowników aplikacji usługi Microsoft Intune <!-- 4843354  -->
Aplikacja usługi Microsoft Intune dla systemu Android obsługuje teraz wyświetlanie niestandardowych powiadomień push, dopasowując ją do funkcji pomocy technicznej ostatnio dodanej w aplikacjach Portal firmy dla systemów iOS i Android. Aby uzyskać więcej informacji, zobacz [Wysyłanie powiadomień niestandardowych w usłudze Intune](custom-notifications.md).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946-----"></a>Nowe funkcje dla dedykowanych urządzeń z systemem Android Enterprise w trybie kiosku z wieloma aplikacjami <!-- 3755304 3041943 3041946   -->
W usłudze Intune możesz kontrolować funkcje i ustawienia w środowisku w stylu kiosku na urządzeniach dedykowanych z systemem Android Enterprise (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia, ograniczenia dotyczące urządzeń** jako typ profilu).

W tej aktualizacji są dodawane następujące funkcje:

- **Urządzenia dedykowane** > **Wiele aplikacji**: **Wirtualny przycisk ekranu głównego** można wyświetlić przez szybkie przesunięcie ekranu w górę. Może również być on przyciskiem przestawnym, który użytkownicy mogą przenosić.
- **Urządzenia dedykowane** > **Wiele aplikacji**: **Dostęp do latarki** umożliwia użytkownikom korzystanie z latarki. 
- **Urządzenia dedykowane** > **Wiele aplikacji**: **Regulacja głośności multimediów** umożliwia użytkownikom kontrolowanie głośności multimediów urządzenia przy użyciu suwaka. 
- **Urządzenia dedykowane** > **Wiele aplikacji**:  **Włącz wygaszacz ekranu**, przekaż obraz niestandardowy i określ, kiedy zostanie wyświetlony wygaszacz ekranu.

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [Android Enterprise device settings to allow or restrict features using Intune](device-restrictions-android-for-work.md#dedicated-device-settings) (Ustawienia urządzeń z systemem Android Enterprise używane w celu zezwolenia na funkcje lub ich ograniczenia za pomocą usługi Intune).

Dotyczy:  
- Dedykowane urządzenia z rozwiązaniem Android Enterprise

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215-3574238-3574235-3574232-----"></a>Nowe profile aplikacji i konfiguracji dla w pełni zarządzanych urządzeń z systemem Android Enterprise <!-- 3574215 3574238 3574235 3574232   -->
Przy użyciu profilów można skonfigurować ustawienia, które stosują ustawienia sieci VPN, poczty e-mail i sieci Wi-Fi do urządzeń właściciela urządzenia z systemem Android Enterprise (w pełni zarządzanych). W tej aktualizacji możesz:

- Używać [zasad konfiguracji aplikacji](app-configuration-policies-use-android.md) w celu wdrożenia ustawień poczty e-mail dla programów Outlook, Gmail oraz Nine Work.
- Używać profilów konfiguracji urządzeń w celu wdrożenia [ustawień zaufanych certyfikatów głównych](certificates-configure.md).
- Używać profilów konfiguracji urządzeń w celu wdrożenia ustawień sieci [VPN](vpn-settings-android-enterprise.md) i [Wi-Fi](wi-fi-settings-android-enterprise.md).

> [!IMPORTANT]
> Dzięki tej funkcji użytkownicy uwierzytelniają się przy użyciu nazwy użytkownika i hasła na potrzeby profilów sieci VPN, Wi-Fi i poczty e-mail. Obecnie uwierzytelnianie oparte na certyfikatach jest niedostępne. 

Dotyczy:  
- Właściciel urządzenia z systemem Android Enterprise (w pełni zarządzanego)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices---3914202-----"></a>Kontrolowanie aplikacji, plików, dokumentów i folderów, które są otwierane, gdy użytkownicy logują się do urządzeń z systemem macOS <!--3914202   -->
Na urządzeniach z systemem macOS można włączać i konfigurować funkcje (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **macOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu). 

W tej aktualizacji jest dostępne nowe ustawienie elementów logowania, które umożliwia kontrolowanie aplikacji, plików, dokumentów i folderów otwieranych, gdy użytkownik loguje się do zarejestrowanego urządzenia. 

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [macOS device feature settings in Intune](macos-device-features-settings.md) (Ustawienia funkcji urządzeń z systemem macOS w usłudze Intune).

Dotyczy:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings------4464404----------"></a>Terminy ostateczne zastępują ustawienia ponownego uruchamiania wymagającego interwencji użytkownika dla pierścieni witryny Windows Update   <!-- 4464404        -->
W celu dostosowana do najnowszych [zmian obsługi systemu Windows](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing) pierścienie aktualizacji systemu Windows 10 w usłudze Intune [obsługują teraz ustawienia terminów ostatecznych](windows-update-settings.md). *Terminy ostateczne* określają, kiedy urządzenie instaluje aktualizacje dotyczące funkcji i zabezpieczeń.  Na urządzeniach z systemem Windows 10 1903 lub nowszym *terminy ostateczne* zastępują konfiguracje *ponownego uruchamiania wymagającego interwencji użytkownika*.  W przyszłości *terminy ostateczne* zastąpią również *ponowne uruchamianie wymagające interwencji użytkownika* w starszych wersjach systemu Windows 10.  

Jeśli nie skonfigurujesz *terminów ostatecznych*, urządzenia będą nadal używać ustawień *ponownego uruchamiania wymagającego interwencji użytkownika*, ale [obsługa ustawień ponownego uruchamiania wymagającego interwencji użytkownika w usłudze Intune zostanie wycofana](whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) w przyszłej aktualizacji.  

Zaplanuj używanie *terminów ostatecznych* dla wszystkich urządzeń z systemem Windows 10. Po wprowadzeniu ustawień *terminów ostatecznych* można zmienić konfiguracje usługi Intune pod kątem *ponownego uruchamiania wymagającego interwencji użytkownika* na Nieskonfigurowane. Po ustawieniu opcji na Nieskonfigurowane usługa Intune przestanie zarządzać tymi ustawieniami na urządzeniach, ale nie usunie ostatnich konfiguracji ustawienia z urządzenia. Z tego względu ostatnie konfiguracje, które zostały ustawione na potrzeby *ponownego uruchamiania wymagającego interwencji użytkownika*, pozostają aktywne i są używane na urządzeniach, dopóki te ustawienia nie zostaną zmodyfikowane przy użyciu metody innej niż usługa Intune. Później w przypadku zmiany wersji systemu Windows lub rozszerzenia obsługi usługi Intune na potrzeby *terminów ostatecznych* na wersję systemu Windows urządzeń urządzenie rozpocznie korzystanie z nowych ustawień, które zostały już wprowadzone.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors--------4704642--------"></a>Obsługa łączników certyfikatów usługi Microsoft Intune   <!--   4704642      -->
Usługa Intune obsługuje teraz instalowanie i używanie wielu [łączników certyfikatów usługi Microsoft Intune dla operacji PKCS](certficates-pfx-configure.md). Ta zmiana obsługuje równoważenie obciążenia i wysoką dostępność łącznika. Każde wystąpienie łącznika może przetwarzać żądania certyfikatów z usługi Intune.  Jeśli jeden łącznik jest niedostępny, inne łączniki kontynuują przetwarzanie żądań. 

Aby używać wielu łączników, nie trzeba uaktualniać oprogramowania łącznika do najnowszej wersji.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709-----"></a>Nowe ustawienia i zmiany istniejących ustawień w celu ograniczenia funkcji na urządzeniach z systemem iOS i macOS <!-- 4867699 4867709   -->
Istnieje możliwość utworzenia profilów w celu ograniczenia niektórych ustawień i funkcji na urządzeniach z systemami iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** lub **macOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu). Ta aktualizacja obejmuje następujące funkcje:

- W obszarze **macOS** > **Ograniczenia urządzenia** > **Chmura i magazyn** użyj nowego ustawienia **Przekazanie**, aby blokować możliwość rozpoczynania pracy przez użytkowników na jednym urządzeniu z systemem macOS i kontynuowania na innym urządzeniu z systemem macOS lub iOS.

  Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-macos.md).

- W obszarze **iOS** > **Ograniczenia urządzenia** wprowadzono kilka zmian:

  - **Aplikacje wbudowane** > **Znajdź mój telefon iPhone (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje tę funkcję w funkcji Znajdź moją aplikację. 
  - **Aplikacje wbudowane** > **Znajdź moich znajomych (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje tę funkcję w funkcji Znajdź moją aplikację. 
  - **Bezprzewodowe** > **Modyfikacja stanu sieci Wi-Fi (tylko tryb nadzorowany)** : nowe ustawienie, które uniemożliwia użytkownikom włączanie lub wyłączanie sieci Wi-Fi na urządzeniu.
  - **Klawiatura i słownik** > **QuickPath (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje funkcję QuickPath.
  - **Chmura i magazyn**: nazwa opcji **Kontynuacja aktywności** została zmieniona na **Przekazanie**.

  Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md).

Dotyczy:  
- System macOS 10.15 i nowsze
- System iOS 13 i nowsze

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809-----"></a>Niektóre ograniczenia nienadzorowanego urządzenia z systemem iOS zostaną zmienione na tylko nadzorowane w przypadku wersji iOS 13.0 <!-- 4867809   -->
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

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md).

Dotyczy:  
- System iOS 13.0 i nowsze

#### <a name="improved-device-status-for-macos-filevault-encryption-----4944983-----------"></a>Ulepszony stan urządzenia na potrzeby szyfrowania FileVault w systemie macOS  <!-- 4944983         -->
Zaktualizowaliśmy kilka [komunikatów dotyczących stanu urządzenia](encryption-monitor.md#device-encryption-status) na potrzeby szyfrowania przy użyciu programu FileVault na urządzeniach z systemem macOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status----5119229---"></a>Niektóre ustawienia skanowania programu antywirusowego Windows Defender raportach pokazują stan niepowodzenia <!-- 5119229 -->
W usłudze Intune możesz utworzyć zasady, aby używać programu antywirusowego Windows Defender do skanowania urządzeń z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Program antywirusowy Windows Defender**). Raporty **Godzina przeprowadzania codziennego szybkiego skanowania** i **Typ skanowania systemu do wykonania** pokazują stan niepowodzenia, gdy w rzeczywistości jest to stan sukcesu. 

W tej aktualizacji to zachowanie zostało naprawione. Oznacza to, że ustawienia **Godzina przeprowadzania codziennego szybkiego skanowania** i **Typ skanowania systemu do wykonania** mają stan sukcesu po pomyślnym ukończeniu skanowania i stan niepowodzenia, jeśli zastosowanie ustawień zakończy się niepowodzeniem. 

Aby uzyskać więcej informacji na temat ustawień programu antywirusowego, zobacz [Ustawienia urządzeń z systemem Windows 10 (i nowszym) w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](device-restrictions-windows-10.md#microsoft-defender-antivirus). 

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="default-scope-tags----3702875----"></a>Domyślne tagi zakresu <!-- 3702875  -->
Nowy, wbudowany domyślny tag zakresu jest teraz dostępny. Wszystkie nieotagowane obiekty usługi Intune, które obsługują tagi zakresu, są automatycznie przypisywane do domyślnego tagu zakresu. **Domyślny** tag zakresu jest dodawany do wszystkich istniejących przypisań ról w celu zapewnienia, że można już korzystać z funkcji administratora. Jeśli nie chcesz, aby administrator widział obiekty usługi Intune z domyślnym tagiem zakresu, usuń domyślny tag zakresu z przypisania roli. Ta funkcja jest podobna do funkcji zakresów zabezpieczeń w programie System Center Configuration Manager. Aby uzyskać więcej informacji, zobacz [Use RBAC and scope tags to for distributed IT](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

#### <a name="android-enrollment-device-administrator-support----4869749-----"></a>Obsługa rejestracji administratora urządzeń z systemem Android <!-- 4869749   -->
Opcja rejestracji administratora urządzenia z systemem Android została dodana do strony rejestracji systemu Android (**Intune** > **Rejestracja urządzenia** > **Rejestracja systemu Android**). Administrator urządzenia z systemem Android będzie nadal domyślnie włączony dla wszystkich dzierżaw.  Aby uzyskać więcej informacji, zobacz [Rejestracja administratora urządzeń z systemem Android](android-enroll-device-administrator.md).

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

Aby uzyskać więcej informacji na temat dostosowywania Asystenta ustawień, zobacz [Tworzenie profilu rejestracji Apple dla systemu iOS](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) i [Tworzenie profilu rejestracji Apple dla systemu macOS](device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process----3823054---"></a>Dodawanie kolumny użytkownika do procesu przekazywania pliku CSV urządzeń rozwiązania Autopilot <!-- 3823054 -->
Teraz można dodać kolumnę użytkownika do procesu przekazywania pliku CSV dla urządzeń rozwiązania Android. Umożliwia to zbiorcze przypisywanie użytkowników w momencie importowania pliku CSV. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Windows w usłudze Intune za pomocą rozwiązania Windows Autopilot](enrollment-autopilot.md).


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Konfigurowanie automatycznego limitu czasu oczyszczania urządzenia na 30 dni <!--4231059  -->
Możesz ustawić automatyczny limit czasu oczyszczania urządzenia na tylko 30 dni (zamiast poprzedniego limitu wynoszącego 90 dni) po ostatnim zalogowaniu. W tym celu przejdź do pozycji **Intune** > **Urządzenia** > **Konfiguracja** > **Reguły czyszczenia urządzeń**.

#### <a name="build-number-included-on-android-device-hardware-page----4461910-----"></a>Numer kompilacji uwzględniony na stronie Sprzęt urządzenia z systemem Android <!-- 4461910   -->
Nowy wpis na stronie Sprzęt dla każdego urządzenia z systemem Android zawiera numer kompilacji systemu operacyjnego urządzenia. Aby uzyskać więcej informacji, zobacz [Wyświetlanie szczegółów urządzenia w usłudze Intune](device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Tydzień od 5 sierpnia 2019 r.

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices-----4843713---"></a>Firma Zebra Technologies jest obsługiwanym producentem OEM aplikacji OEMConfig na urządzeniach z systemem Android Enterprise  <!-- 4843713 -->

W usłudze Intune możesz utworzyć profile konfiguracji urządzenia i zastosować ustawienia do urządzeń z rozwiązaniem Android Enterprise przy użyciu aplikacji OEMConfig (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **OEMConfig** jako typ profilu).

W tej aktualizacji firma Zebra Technologies jest producentem oryginalnego sprzętu (OEM) dla aplikacji OEMConfig. Aby uzyskać więcej informacji o aplikacji OEMConfig, przejdź do tematu [Use and manage Android Enterprise devices with OEMConfig](android-oem-configuration-overview.md) (Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig).

Dotyczy:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019"></a>Tydzień od 22 lipca 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="customized-notifications-for-users-and-groups-------16766574------------"></a>Dostosowane powiadomienia dla użytkowników i grup    <!-- 16766574          -->
Wysyłaj niestandardowe powiadomienia push z aplikacji Portal firmy do użytkowników na urządzeniach z systemami iOS i Android zarządzanych przy użyciu usługi Intune. Te mobilne powiadomienia push można w dużym stopniu dostosowywać za pomocą dowolnego tekstu i używać ich w różnorodnych celach. Możesz je kierować do różnych grup użytkowników w swojej organizacji. Aby uzyskać więcej informacji, zobacz [powiadomienia niestandardowe](custom-notifications.md).

#### <a name="googles-device-policy-controller-app----3041950----"></a>Aplikacja Device Policy Controller firmy Google <!-- 3041950  -->
Aplikacja Managed Home Screen umożliwia teraz dostęp do aplikacji Android Device Policy firmy Google. Aplikacja Managed Home Screen jest niestandardowym modułem uruchamiania używanym w przypadku urządzeń zarejestrowanych w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) w trybie kiosku z wieloma aplikacjami. Aplikacja Android Device Policy może być przydatna zarówno dla Ciebie, jak i Twoich użytkowników w celu uzyskania pomocy technicznej lub przeprowadzenia debugowania. Ta funkcja uruchamiania jest dostępna, gdy urządzenie zostanie zarejestrowane i zablokowane w aplikacji Managed Home Screen. Do korzystania z tej funkcji nie są konieczne żadne dodatkowe instalacje.

#### <a name="outlook-protection-settings-for-ios-and-android-devices----3212619---"></a>Ustawienia ochrony programu Outlook dla urządzeń z systemami iOS i Android <!-- 3212619 -->
Teraz ogólne ustawienia konfiguracji aplikacji oraz ustawienia konfiguracji ochrony danych dla programu Outlook dla systemów iOS i Android można skonfigurować przy użyciu prostych kontrolek administratora usługi Intune bez rejestracji urządzeń. Ogólne ustawienia konfiguracji aplikacji zapewniają równoważność z ustawieniami, które mogą włączyć administratorzy w przypadku zarządzania programem Outlook dla systemów iOS i Android na urządzeniach zarejestrowanych. Aby uzyskać więcej informacji o ustawieniach programu Outlook, zobacz [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 eeready   idstaged -->

Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma > **Reguły stosowania**). Dzięki tej aktualizacji będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Aby dodać regułę stosowania, zobacz [Reguły stosowania](device-profile-create.md#applicability-rules).

Dotyczy: System Windows 10 lub nowszy

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices----3330008----"></a>Używanie tokenów w celu dodawania informacji dotyczących konkretnych urządzeń w profilach niestandardowych dla urządzeń z systemami iOS i macOS <!-- 3330008  -->
Przy użyciu profilów niestandardowych na urządzeniach z systemami iOS i macOS można skonfigurować ustawienia i funkcje, które nie są wbudowane w usłudze Intune (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** lub **macOS** jako platforma > **Niestandardowy** jako typ profilu). Dzięki tej aktualizacji możesz dodawać tokeny do plików `.mobileconfig`, aby dodać informacje dotyczące konkretnych urządzeń. Możesz na przykład dodać token `Serial Number: {{serialnumber}}` do pliku konfiguracji, aby pokazać numer seryjny urządzenia.

Aby utworzyć profil niestandardowy, zobacz [Ustawienia niestandardowe systemu iOS](custom-settings-ios.md) lub [Ustawienia niestandardowe systemu macOS](custom-settings-macos.md).

Dotyczy:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769-----"></a>Nowy projektant konfiguracji podczas tworzenia profilu za pomocą aplikacji OEMConfig dla systemu Android Enterprise <!-- 3712769   -->
W usłudze Intune można utworzyć profil konfiguracji urządzenia, który używa aplikacji OEMConfig (Konfiguracja urządzeń > Profile > Utwórz profil > Android Enterprise jako platforma > OEMConfig jako typ profilu). Po wykonaniu tych czynności zostanie otwarty edytor JSON z szablonem i wartościami, które można zmienić. 

Ta aktualizacja zawiera projektanta konfiguracji z ulepszonym środowiskiem obsługi użytkownika, które pokazuje szczegóły osadzone w aplikacji, w tym tytuły, opisy i inne. Edytor JSON jest nadal dostępny i pokazuje wszelkie zmiany wprowadzone w projektancie konfiguracji.

Aby wyświetlić bieżące ustawienia, przejdź do tematu [Use and manage Android Enterprise devices with OEMConfig](android-oem-configuration-overview.md) (Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig).

Dotyczy: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello-----4089576--------------"></a>Zaktualizowany interfejs użytkownika do konfigurowania funkcji Windows Hello  <!-- 4089576            -->
Zaktualizowaliśmy konsolę, która służy do [konfigurowania usługi Intune pod kątem korzystania z usługi Windows Hello dla firm](windows-hello.md). Wszystkie ustawienia konfiguracji są teraz dostępne w tym samym okienku konsoli, w którym włącza się obsługę funkcji Windows Hello. 


#### <a name="intune-powershell-sdk----4924113---"></a>Zestaw SDK programu PowerShell usługi Intune <!-- 4924113 --> 
Zestaw SDK programu PowerShell usługi Intune, który zapewnia obsługę interfejsu API usługi Intune za pośrednictwem programu Microsoft Graph, został zaktualizowany do wersji 6.1907.1.0. Zestaw SDK obsługuje teraz następujące funkcje:
- Współpraca z usługą Azure Automation.
- Obsługa operacji odczytu uwierzytelniania tylko aplikacji. 
- Obsługa przyjaznych skróconych nazw jako aliasów.
- Zgodność z konwencjami nazewnictwa programu PowerShell. W szczególności nazwa parametru `PSCredential` (w poleceniu cmdlet `Connect-MSGraph`) została zmieniona na `Credential`.
- Obsługa ręcznego określania wartości nagłówka `Content-Type` w przypadku używania polecenia cmdlet `Invoke-MSGraphRequest`.

Aby uzyskać więcej informacji, zobacz [Zestaw SDK programu PowerShell dla interfejsu API programu Graph usługi Microsoft Intune](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="updates-for-enrollment-restrictions-----2871968---"></a>Aktualizacje ograniczeń rejestracji  <!-- 2871968 -->
Ograniczenia rejestracji dla nowych dzierżawców zostały zaktualizowane, aby profile służbowe systemu Android Enterprise były domyślnie dozwolone. W przypadku istniejących dzierżawców nie zostaną wprowadzone żadne zmiany. Aby móc używać profilów służbowych systemu Android Enterprise, nadal trzeba [połączyć konto usługi Intune z kontem zarządzanego sklepu Google Play](https://docs.microsoft.com/intune/connect-intune-android-enterprise).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions---4089575-4089579----"></a>Aktualizacje interfejsu użytkownika dotyczące rejestracji firmy Apple i ograniczeń rejestracji <!--4089575, 4089579  -->
W obu poniższych procesach używany jest interfejs użytkownika w stylu kreatora:
- Rejestracja urządzeń firmy Apple. Aby uzyskać więcej informacji, zobacz [Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program firmy Apple](device-enrollment-program-enroll-ios.md).
- Tworzenie ograniczeń rejestracji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie ograniczeń rejestracji](enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices----4711509--idmiss---"></a>Obsługa wstępnej konfiguracji identyfikatorów urządzeń firmowych dla urządzeń z systemem Android Q <!-- 4711509  idmiss -->
W systemie Android Q (wersja 10) firma Google usunie możliwość zbierania informacji o identyfikatorze urządzenia przez agentów MDM na urządzeniach z systemem Android zarządzanych w starszy sposób (administrator urządzenia).  Usługa Intune zawiera funkcję, która umożliwia administratorom IT [wstępne skonfigurowanie listy numerów seryjnych lub numerów IMEI urządzeń](https://docs.microsoft.com/intune/corporate-identifiers-add#identify-corporate-owned-devices-with-imei-or-serial-number) w celu automatycznego oznakowania tych urządzeń jako należących do firmy. Ta funkcja nie będzie działała w przypadku urządzeń z systemem Android Q, które są zarządzane przez administratora urządzenia.  Bez względu na to, czy numer seryjny lub kod IMEI dla urządzenia zostaną przekazane, będzie ono zawsze traktowane jako osobiste podczas rejestracji w usłudze Intune.  Po rejestracji można ręcznie przełączyć własność na firmę.  Ma to zastosowanie tylko do nowych rejestracji i nie dotyczy istniejących zarejestrowanych urządzeń.  Ta zmiana nie ma wpływu na urządzenia z systemem Android zarządzane przy użyciu profilów służbowych — te urządzenia będą nadal działać tak, jak obecnie.  Ponadto urządzenia z systemem Android Q zarejestrowane jako administrator urządzenia nie będą już mogły zgłaszać numeru seryjnego ani numeru IMEI w konsoli usługi Intune jako właściwości urządzenia.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices----4977730---"></a>Zmieniono ikony w procesie rejestracji systemu Android Enterprise (profile służbowe, urządzenia dedykowane i urządzenia w pełni zarządzane) <!-- 4977730 -->
Zmieniono ikony profilów rejestracji systemu Android Enterprise. Aby zobaczyć nowe ikony, wybierz pozycję **Intune** > **Rejestracja** > **Rejestracja systemu Android** i sprawdź w obszarze **Profile rejestracji**.


#### <a name="windows-diagnostic-data-collection-change----4113859---"></a>Zmiana zbierania danych diagnostycznych systemu Windows <!-- 4113859 -->
Dla urządzeń z systemem Windows 10 w wersji 1903 lub nowszej wartość domyślna zbierania danych diagnostycznych została zmieniona. Począwszy od systemu Windows 10 w wersji 1903, zbieranie danych diagnostycznych jest domyślnie włączone. Dane diagnostyczne systemu Windows to istotne dane techniczne zbierane z urządzeń z systemem Windows dotyczące urządzenia oraz działania systemu Windows i powiązanego oprogramowania. Aby uzyskać więcej informacji, zobacz [Konfigurowanie danych diagnostycznych systemu Windows w organizacji](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Urządzenia rozwiązania Autopilot również mają włączoną opcję „Full” (Pełne) dla danych telemetrycznych, chyba że w profilu rozwiązania Autopilot określono inaczej za pomocą polecenia [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="improve-device-location---3855417----"></a>Ulepszona lokalizacja urządzenia<!-- 3855417  -->
Przy użyciu akcji **Zlokalizuj urządzenie** można powiększyć lokalizację urządzenia, aby uzyskać jego dokładne współrzędne geograficzne. Aby uzyskać więcej informacji na temat lokalizowania utraconych urządzeń z systemem iOS, zobacz [Znajdowanie utraconych urządzeń z systemem iOS](device-locate.md).


### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview------1311949-------"></a>Zaawansowane ustawienia zapory Windows Defender (publiczna wersja zapoznawcza)  <!--  1311949     -->  
Przy użyciu usługi Intune można zarządzać [niestandardowymi regułami zapory w ramach profilu konfiguracji urządzenia](endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) na potrzeby ochrony punktu końcowego w systemie Windows 10. Reguły te mogą określać zachowanie dotyczące ruchu przychodzącego i wychodzącego na poziomie aplikacji, adresów sieciowych i portów. 

#### <a name="updated-ui-for-managing-security-baselines------4091125-------"></a>Zaktualizowany interfejs użytkownika na potrzeby zarządzania punktami odniesienia zabezpieczeń   <!-- 4091125     -->
Zaktualizowaliśmy [środowisko tworzenia i edytowania](security-baselines.md#create-the-profile) w konsoli usługi Intune dla naszych punktów odniesienia zabezpieczeń. Zmiany te obejmują:

Prostszy format w stylu kreatora, który został skondensowany do pojedynczego bloku. w jednym bloku. Ten nowy projekt pozwala pozbyć się natłoku widocznych jednocześnie bloków, który wymaga od specjalistów IT przechodzenia do szczegółów w kilku oddzielnych okienkach.  
Teraz przypisania można tworzyć w ramach środowiska tworzenia i edytowania, zamiast powracania później w celu przypisania punktów odniesienia. Dodaliśmy podsumowanie ustawień, które można wyświetlić przed utworzeniem nowego punktu odniesienia i podczas edytowania istniejącego punktu odniesienia. Podczas edycji podsumowanie pokazuje tylko listę elementów ustawionych w ramach jednej kategorii właściwości, które są edytowane.



<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Tydzień od 15 lipca 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="managed-home-screen-and-managed-settings-icons----4918107---"></a>Ikona aplikacji Managed Home Screen i ikona Ustawienia zarządzane <!-- 4918107 -->
Ikona aplikacji Managed Home Screen i ikona **Ustawienia zarządzane** zostały zaktualizowane. Aplikacja Managed Home Screen jest używana tylko przez urządzenia zarejestrowane w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) i działające w trybie kiosku z wieloma aplikacjami. Aby uzyskać więcej informacji na temat aplikacji Managed Home Screen, zobacz [Konfigurowanie aplikacji Microsoft Managed Home Screen dla rozwiązania Android Enterprise](app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices----4918136---"></a>Aplikacja Android Device Policy na dedykowanych urządzeniach z systemem Android Enterprise <!-- 4918136 -->
Dostęp do aplikacji Android Device Policy można uzyskać z poziomu ekranu debugowania aplikacji Managed Home Screen. Aplikacja Managed Home Screen jest używana tylko przez urządzenia zarejestrowane w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) i działające w trybie kiosku z wieloma aplikacjami. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji Microsoft Managed Home Screen dla rozwiązania Android Enterprise](app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates----3902931---"></a>Aktualizacje aplikacji Portal firmy w systemie iOS <!-- 3902931 -->
W monitach zarządzania aplikacjami w systemie iOS tekst „i.manage.microsoft.com” zostanie zastąpiony nazwą Twojej firmy. Na przykład użytkownicy będą widzieli nazwę firmy zamiast tekstu „i.manage.microsoft.com”, gdy będą próbować zainstalować aplikację dla systemu iOS z aplikacji Portal firmy lub gdy będą zezwalać na zarządzanie aplikacją. Ta zmiana zostanie wprowadzona u wszystkich klientów w ciągu kilku następnych dni.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="manage-filevault-for-macos-------3858502--4557986--1210104----"></a>Zarządzanie programem FileVault dla systemu macOS   <!--  3858502 + 4557986 + 1210104  -->
Przy użyciu usługi Intune można [zarządzać szyfrowaniem klucza programu FileVault dla urządzeń z systemem macOS](encrypt-devices.md). Aby szyfrować urządzenia, należy użyć profilu konfiguracji urządzenia ochrony punktu końcowego.

Obsługa programu FileVault obejmuje szyfrowanie niezaszyfrowanych urządzeń, depozyt osobistych kluczy odzyskiwania urządzeń, automatyczną lub ręczną rotację osobistych kluczy szyfrowania oraz pobieranie kluczy dla urządzeń firmowych. Użytkownicy końcowi mogą również przy użyciu witryny Portal firmy pobierać osobiste klucze odzyskiwania dla swoich zaszyfrowanych urządzeń. 

Rozszerzyliśmy też raport szyfrowania, aby zawierał [informacje o programie FileVault](encryption-monitor.md) wraz z informacjami o funkcji BitLocker, dzięki czemu wszystkie szczegóły dotyczące szyfrowania urządzenia są widoczne w jednym miejscu. 

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user----4156123---"></a>Resetowanie w programie Windows Autopilot usuwa podstawowego użytkownika urządzenia <!-- 4156123 -->
Użycie na urządzeniu resetowania w programie Autopilot spowoduje usunięcie użytkownika podstawowego urządzenia. Następny użytkownik, który zarejestruje się po zresetowaniu, zostanie ustawiony jako użytkownik podstawowy. Ta funkcja zostanie wprowadzona u wszystkich klientów w ciągu kilku następnych dni.

## <a name="week-of-july-8-2019"></a>Tydzień od 8 lipca 2019 r.

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nowe ustawienia pakietu Office, systemu Windows i usługi OneDrive w szablonach administracyjnych systemu Windows 10 <!-- 3510695 -->

W usłudze Intune można utworzyć szablony administracyjne, które naśladują zarządzanie zasadami grupy w środowisku lokalnym (**Zarządzanie urządzeniami** > **Profile** > **Utwórz profil** > **Windows 10 lub nowszy** jako platforma > **Szablon administracyjny** jako typ profilu).

Ta aktualizacja zawiera więcej ustawień pakietu Office, systemu Windows i usługi OneDrive, które można dodać do szablonów. Korzystając z tych nowych ustawień, można teraz skonfigurować ponad 2500 ustawień, które są w 100% oparte na chmurze.

Aby dowiedzieć się więcej na temat tej funkcji, zobacz [Konfigurowania ustawień zasad grupy w usłudze Intune przy użyciu szablonów systemu Windows 10](administrative-templates-windows.md).

Dotyczy: System Windows 10 lub nowszy

## <a name="week-of-july-1-2019"></a>Tydzień od 1 lipca 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="aad-and-app-on-android-enterprise-devices----3574267---"></a>Usługa AAD i zasady ochrony aplikacji (APP) na urządzeniach z systemem Android Enterprise <!-- 3574267 -->
W przypadku dołączania w pełni zarządzanych urządzeń z systemem Android Enterprise użytkownicy będą teraz rejestrowali się za pomocą usługi Azure Active Directory (AAD) podczas wstępnej konfiguracji nowego urządzenia lub urządzenia zresetowanego do ustawień fabrycznych. Wcześniej w przypadku w pełni zarządzanego urządzenia po zakończeniu konfiguracji użytkownik musiał ręcznie uruchomić aplikację Microsoft Intune, aby rozpocząć rejestrację usługi AAD. Teraz, kiedy po wstępnej konfiguracji zostanie wyświetlona strona główna urządzenia, urządzenie będzie włączone i zarejestrowane.

Poza aktualizacjami usługi AAD, na w pełni zarządzanych urządzeniach z systemem Android Enterprise są teraz obsługiwane zasady ochrony aplikacji usługi Intune (APP, app protection policies). Ta funkcja stanie się dostępna w miarę wdrażania. Aby uzyskać więcej informacji, zobacz [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](apps-add-android-for-work.md).

## <a name="week-of-june-24-2019"></a>Tydzień od 24 czerwca 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Konfigurowanie przeglądarki, którą można połączyć z danymi organizacji <!-- 3145939 -->
Zasady rozwiązania Intune App Protection na urządzeniach z systemami Android i iOS umożliwiają transferowanie linków internetowych organizacji do określonej przeglądarki poza programem Intune Managed Browser lub Microsoft Edge.  Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Strona Wszystkie aplikacje identyfikuje aplikacje w trybie online/offline ze sklepu Microsoft Store dla Firm<!--4089647 -->
Na stronie **Wszystkie aplikacje** jest teraz dostępna etykieta umożliwiająca identyfikację aplikacji ze sklepu Microsoft Store dla Firm (MSFB) jako aplikacji w trybie online lub offline. Każda aplikacja ze sklepu MSFB zawiera teraz sufiks określający tryb **online** lub **offline**. Strona szczegółów aplikacji zawiera również informacje o **typie licencji** i czy aplikacja **obsługuje instalację kontekstu urządzenia** (tylko aplikacje licencjonowane w trybie offline).

#### <a name="company-portal-app-on-windows-shared-devices---4393553---"></a>Aplikacja Portal firmy na urządzeniach udostępnionych z systemem Windows <!--4393553 -->
Użytkownicy mogą teraz uzyskiwać dostęp do aplikacji Portal firmy na urządzeniach udostępnionych z systemem Windows. Użytkownicy końcowi będą widzieć etykietę **Udostępnione** na kafelku urządzenia. Dotyczy to aplikacji Portal firmy dla systemu Windows w wersji 10.3.45609.0 i nowszych.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page----4224326---"></a>Wyświetlanie wszystkich zainstalowanych aplikacji na nowej stronie internetowej Portal firmy <!-- 4224326 -->
Na nowej stronie **Zainstalowane aplikacje** w witrynie Portal firmy jest dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Oprócz typu przypisania użytkownicy mogą sprawdzić wydawcę, datę opublikowania i bieżący stan instalacji aplikacji. Jeśli nie określono żadnych aplikacji jako wymaganych lub dostępnych dla użytkowników, zobaczą oni komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Aby wyświetlić nową stronę w Internecie, przejdź do [witryny internetowej Portal firmy](https://portal.manage.microsoft.com) i kliknij pozycję **Zainstalowane aplikacje**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device----2352913---"></a>Nowy widok umożliwia użytkownikom aplikacji wyświetlenie wszystkich zarządzanych aplikacji zainstalowanych na urządzeniu <!-- 2352913 -->  
W aplikacji Portal firmy dla systemu Windows jest dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy mogą również wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli nie określono aplikacji jako wymaganych lub dostępnych dla użytkowników, zobaczą oni komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Aby wyświetlić nowy widok, przejdź do okienka nawigacji w aplikacji Portal firmy, a następnie wybierz pozycję **Aplikacje** > **Zainstalowane aplikacje**.    

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Konfigurowanie ustawień dotyczących rozszerzeń jądra na urządzeniach z systemem macOS <!-- 2043024 -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę). Ta aktualizacja zawiera nową grupę ustawień, która umożliwia konfigurowanie i używanie rozszerzeń jądra na urządzeniach. Można dodać określone rozszerzenia lub zezwolić na wszystkie rozszerzenia od określonego partnera lub dewelopera.

Aby dowiedzieć się więcej na temat tej funkcji, zobacz [omówienie rozszerzenia jądra](kernel-extensions-overview-macos.md) i [ustawienia rozszerzenia jądra](kernel-extensions-settings-macos.md).

Dotyczy: macOS 10.13.2 i nowsze

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002---"></a>Ustawienie Aplikacje tylko ze sklepu dla urządzeń z systemem Windows 10 uwzględnia więcej opcji konfiguracji <!-- 2697002 -->
Podczas tworzenia profilu ograniczeń urządzenia dla urządzeń z systemem Windows można użyć ustawienia **Aplikacje tylko ze sklepu**, aby użytkownicy instalowali tylko aplikacje ze sklepu z aplikacjami dla systemu Windows (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Ograniczenia urządzenia** jako typ profilu). W tej aktualizacji to ustawienie zostało rozszerzone tak, aby obsługiwało więcej opcji. 

Aby zobaczyć nowe ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem Windows 10 (i nowszym) umożliwiające działanie funkcji lub ich ograniczanie](device-restrictions-windows-10.md#app-store).

Dotyczy: System Windows 10 lub nowszy

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Wdrażanie wielu profilów urządzeń przy użyciu funkcji Zebra Mobility Extensions do urządzenia, tej samej grupy użytkowników lub tej samej grupy urządzeń <!-- 4089955 -->
W usłudze Intune przy użyciu funkcji Zebra Mobility Extensions (MX) w profilu konfiguracji urządzenia można dostosować ustawienia dla urządzeń Zebra, które nie są wbudowane w usłudze Intune. Obecnie można wdrożyć jeden profil do jednego urządzenia. W tej aktualizacji można wdrożyć wiele profili dla:
- Tej samej grupy użytkowników
- Tej samej grupy urządzeń
- Pojedynczego urządzenia

Temat [Używanie urządzeń Zebra i zarządzanie nimi za pomocą funkcji Zebra Mobility Extensions w usłudze Microsoft Intune](android-zebra-mx-overview.md) przedstawia sposób używania rozszerzeń MX w usłudze Intune.

Dotyczy: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Niektóre ustawienia kiosku na urządzeniach z systemem iOS są ustawiane przy użyciu pozycji „Blokuj” zastępującej pozycję „Zezwalaj” <!-- 4404075  -->
Po utworzeniu profilu ograniczeń urządzenia na urządzeniach z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Kiosk**) możesz zdefiniować ustawienia **Blokada automatyczna**, **Przełącznik dzwonka**, **Obrót ekranu**, **Przycisk usypiania ekranu** i **Przyciski głośności**. 

W tej aktualizacji dostępnymi wartościami są: **Blokuj** (blokowanie funkcji) i **Nieskonfigurowane** (zezwalanie na funkcję). Aby zobaczyć ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie](device-restrictions-ios.md#kiosk-supervised-only). 

Dotyczy: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704---"></a>Używanie funkcji Face ID do uwierzytelniania hasła na urządzeniach z systemem iOS <!-- 4490704 -->
Podczas tworzenia profilu ograniczeń urządzenia dla urządzeń z systemem iOS można użyć hasła w postaci odcisku palca. W tej aktualizacji ustawienia hasła w postaci odcisku palca zezwalają również na rozpoznawanie twarzy (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzeń** jak typ profilu > **Hasło**). W wyniku zmieniły się następujące ustawienia:

- **Odblokowywanie za pomocą odcisku palca** to teraz **Odblokowywanie za pomocą funkcji Touch ID i Face ID**.
- **Modyfikacja odcisku palca (tylko w trybie nadzorowanym)** to teraz **Modyfikacja funkcji Touch ID i Face ID (tylko w trybie nadzorowanym)** .

Funkcja Face ID jest dostępna w systemie iOS 11.0 i nowszych wersjach. Aby zobaczyć ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md#password).

Dotyczy: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region----4593948---"></a>Ograniczanie funkcji gier i funkcji sklepu z aplikacjami na urządzeniach z systemem iOS jest teraz zależne od regionu klasyfikacji <!-- 4593948 -->
Na urządzeniach z systemem iOS można zezwolić na lub ograniczyć funkcje związane z grami, sklepem z aplikacjami i wyświetlaniem dokumentów (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzenia** jako typ profilu > **Sklep App Store, wyświetlanie dokumentów, granie**). Można również wybrać region klasyfikacji, taki jak Stany Zjednoczone. 

W tej aktualizacji funkcja **Aplikacje** została przeniesiona jako element podrzędny do **regionu klasyfikacji** i jest zależna od **regionu klasyfikacji**. Aby zobaczyć ustawienia, przejdź do tematu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Dotyczy: iOS

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join----4809146--"></a>Obsługa funkcji Windows Autopilot dla dołączania do hybrydowej usługi Azure AD <!-- 4809146-->
Funkcja Windows Autopilot dla istniejących urządzeń obsługuje teraz dołączanie do hybrydowej usługi Azure AD (oprócz istniejącej obsługi dołączania do usługi Azure AD). Dotyczy urządzeń z systemem Windows 10 w wersji 1809 lub nowszej. Aby uzyskać więcej informacji, zobacz [Rozwiązanie Windows Autopilot dla istniejących urządzeń](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).



### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="see-the-security-patch-level-for-android-devices----4461911---"></a>Wyświetlanie poziomu poprawki zabezpieczeń dla urządzeń z systemem Android <!-- 4461911 -->
Teraz można zobaczyć poziom poprawki zabezpieczeń dla urządzeń z systemem Android. Aby to zrobić, wybierz pozycję **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**.
Poziom poprawki jest wymieniony w sekcji **System operacyjny**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Przypisywanie tagów zakresu do wszystkich urządzeń zarządzanych w grupie zabezpieczeń <!-- 3173810 -->
Teraz można przypisać tagi zakresu do grupy zabezpieczeń i wszystkie urządzenia w grupie zabezpieczeń również zostaną skojarzone z tymi tagami zakresu. Tag zakresu zostanie również przypisany do wszystkich urządzeń w tych grupach. Tagi zakresu ustawione przy użyciu tej funkcji zastąpią tagi zakresu ustawione przy użyciu bieżącego przepływu tagów zakresu urządzenia. Aby uzyskać więcej informacji, zobacz [Use RBAC and scope tags for distributed IT](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

### <a name="device-security"></a>Zabezpieczenia urządzeń

#### <a name="use-keyword-search-with-security-baselines-------"></a>Używanie wyszukiwania słów kluczowych z punktami odniesienia zabezpieczeń <!--  -->
Gdy tworzysz lub edytujesz [profile punktu odniesienia zabezpieczeń](security-baselines.md#create-the-profile), możesz określić słowa kluczowe na nowym pasku *wyszukiwania*, aby odfiltrować dostępne grupy ustawień do tych, które zawierają kryteria wyszukiwania. 

#### <a name="the-security-baselines-feature-is-now-generally-available-----3785395---"></a>Funkcja Punkty odniesienia zabezpieczeń jest teraz ogólnie dostępna  <!-- 3785395 -->
Okres wersji zapoznawczej funkcji **Punkty odniesienia zabezpieczeń** zakończył się i jest ona ogólnie dostępna.  Oznacza to, że funkcja jest gotowa do użycia w środowisku produkcyjnym. Jednak poszczególne szablony punktów odniesienia mogą pozostawać w wersji zapoznawczej — są one oceniane i udostępniane ogólnie zgodnie z ich własnym harmonogramem.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available------3794072-4217151--3534649---"></a>Szablon punktu odniesienia zabezpieczeń rozwiązania MDM jest teraz ogólnie dostępny   <!-- 3794072, 4217151,  3534649 -->
Okres wersji zapoznawczej szablonu punktu odniesienia zabezpieczeń rozwiązania MDM zakończył się i jest on ogólnie dostępny. Ten ogólnie dostępny szablon został określony jako **MDM Security Baseline for May 2019** (Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019).  To jest nowy szablon, a nie uaktualnienie wersji zapoznawczej.  Ponieważ jest to nowy szablon, należy przejrzeć [zawarte w nim ustawienia](security-baseline-settings-windows.md), a następnie utworzyć nowe profile, aby wdrożyć szablon na urządzeniu. Inne szablony punktów odniesienia zabezpieczeń mogą pozostać w wersji zapoznawczej. Aby uzyskać listę dostępnych punktów odniesienia, zobacz [Dostępne punkty odniesienia zabezpieczeń](security-baselines.md#available-security-baselines).  

Poza tym, że jest nowy, szablon *MDM Security Baseline for May 2019* (Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019) zawiera dwa ustawienia, o których informowaliśmy ostatnio w artykule W trakcie opracowywania:  
- Przy włączonej blokadzie: Głosowe aktywowanie aplikacji przy zablokowanym ekranie  
- DeviceGuard: Użycie zabezpieczeń opartych na wirtualizacji (VBS) podczas następnego rozruchu urządzeń.  

W szablonie *MDM Security Baseline for May 2019* (Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019) dodano również kilka nowych, dodatkowych ustawień, usunięto inne oraz zmieniono wartość domyślną jednego ustawienia. Aby uzyskać szczegółową listę zmian między wersją zapoznawczą i ogólnie dostępną, zobacz **Co zmieniło się w nowym szablonie**.

#### <a name="security-baseline-versioning-----3194322---"></a>Przechowywanie wersji punktu odniesienia zabezpieczeń  <!-- 3194322 -->
Punkty odniesienia zabezpieczeń dla usługi Intune obsługują przechowywanie wersji. Dzięki tej obsłudze, gdy są wydawane nowe wersje każdego punktu odniesienia zabezpieczeń, można zaktualizować istniejące profile punktu odniesienia zabezpieczeń, aby używać nowszej wersji punktu odniesienia, bez konieczności ponownego tworzenia i wdrażania nowego punktu odniesienia od podstaw. Ponadto w konsoli usługi Intune można wyświetlić informacje o poszczególnych punktach odniesienia, takie jak liczba poszczególnych profilów, które używają danego punktu odniesienia, liczba różnych wersji punktu odniesienia używanych przez profile oraz data ostatniego wydania określonego punktu odniesienia zabezpieczeń.  Aby uzyskać więcej informacji, zobacz **Punkty odniesienia zabezpieczeń**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved-----4501151---"></a>Ustawienie Użyj kluczy zabezpieczeń do logowania się zostało przeniesione  <!-- 4501151 -->
Ustawienie konfiguracji urządzenia na potrzeby ochrony tożsamości o nazwie **Użyj kluczy zabezpieczeń do logowania się** nie jest już dostępne jako ustawienie podrzędne ustawienia *Skonfiguruj funkcję Windows Hello dla firm*. Jest to teraz ustawienie najwyższego poziomu, które jest zawsze dostępne, nawet jeśli nie włączono korzystania z funkcji Windows Hello dla firm. Aby uzyskać więcej informacji, zobacz [Ochrona tożsamości](identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="new-permissions-for-assigned-group-admins------4504437-----"></a>Nowe uprawnienia dla przypisanych administratorów grup   <!-- 4504437   -->
Wbudowana rola administratora szkoły usługi Intune ma teraz uprawnienia tworzenia, odczytu, aktualizowania i usuwania (CRUD) do aplikacji zarządzanych. Ta aktualizacja oznacza, że jeśli użytkownik jest przypisany jako administrator grupy w usłudze Intune for Education, może teraz tworzyć, wyświetlać, aktualizować i usuwać certyfikat wypychania MDM systemu iOS, tokeny serwera MDM systemu iOS i tokeny programu VPP systemu iOS, a także [wszystkie istniejące posiadane uprawnienia](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Aby wykonać dowolną z tych akcji, przejdź do pozycji **Ustawienia dzierżawy** > **Zarządzanie urządzeniami z systemem iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials----4655885---"></a>Aplikacje mogą używać interfejsu API programu Graph do wywoływania operacji odczytu bez poświadczeń użytkownika <!-- 4655885 -->
Aplikacje mogą wywoływać operacje odczytu interfejsu API programu Graph w usłudze Intune przy użyciu tożsamości aplikacji bez poświadczeń użytkownika. Aby uzyskać więcej informacji na temat uzyskiwania dostępu do interfejsu API programu Microsoft Graph dla usługi Intune, zobacz [Praca z usługą Intune w programie Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps----4392555---"></a>Stosowanie tagów zakresu do aplikacji ze sklepu Microsoft Store dla Firm <!-- 4392555 -->
Teraz można stosować tagi zakresu do aplikacji ze sklepu Microsoft Store dla Firm. Więcej informacji na temat tagów zakresu można znaleźć w temacie [Use role-based access control (RBAC) and scope tags for distributed IT](scope-tags.md) (Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej).

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

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>Nowe przykładowe aplikacje przedstawiające integrację zestawu SDK usługi Intune dostępne w usłudze GitHub <!-- 2653471 -->
Do konta msintuneappsdk w usłudze GitHub dodano nowe przykładowe aplikacje dla systemu iOS (Swift), systemu Android, rozszerzenia Xamarin.iOS, rozwiązania Xamarin Forms i rozszerzenia Xamarin.Android. Te aplikacje mają uzupełniać naszą istniejącą dokumentację i oferować pokazy dotyczące integrowania zestawu SDK zasad ochrony aplikacji usługi Intune z własnymi aplikacjami mobilnymi. Jeśli jesteś deweloperem aplikacji, który potrzebuje dodatkowych wskazówek dotyczących zestawu SDK usługi Intune, zobacz poniższe linki do przykładów:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) — natywna aplikacja systemu iOS (Swift) do obsługi wiadomości błyskawicznych, która używa usługi biblioteki Azure Active Directory Authentication Library (ADAL) na potrzeby uwierzytelniania obsługiwanego przez brokera.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) — natywna aplikacja systemu Android do obsługi listy zadań do wykonania, która używa biblioteki ADAL na potrzeby uwierzytelniania obsługiwanego przez brokera.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) — aplikacja rozszerzenia Xamarin.Android do obsługi listy zadań do wykonania, która używa biblioteki ADAL na potrzeby uwierzytelniania obsługiwanego przez brokera. To repozytorium zawiera również aplikację Xamarin.Forms.
- [Przykładowa aplikacja rozszerzenia Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) — podstawowa przykładowa aplikacja rozszerzenia Xamarin.iOS.

## <a name="week-of-may-27-2019"></a>Tydzień od 27 maja 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Raporty dotyczące potencjalnie szkodliwych aplikacji na urządzeniach z systemem Android <!-- 4223162 -->
Usługa Intune udostępnia teraz dodatkowe raporty na temat potencjalnie szkodliwych aplikacji na urządzeniach z systemem Android. 

## <a name="week-of-may-20-2019"></a>Tydzień od 20 maja 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="windows-company-portal-app----3316993---"></a>Aplikacja Portal firmy dla systemu Windows <!-- 3316993 -->
Aplikacja Portal firmy w systemie Windows będzie teraz mieć nową stronę z etykietą **Urządzenia**. Strona **Urządzenia** przedstawia użytkowników końcowych wszystkich zarejestrowanych urządzeń. Użytkownicy zobaczą tę zmianę w Portalu firmy, jeśli korzystają z wersji 10.3.4291.0 lub nowszej. Aby uzyskać informacje na temat konfigurowania Portalu firmy, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Zmieniono nazwę atrybutu OrderID urządzenia rozwiązania Autopilot na tag grupy <!-- 4659453 -->

Aby zwiększyć intuicyjność, zmieniono nazwę atrybutu **OrderID** w urządzeniach rozwiązania Autopilot na **Tag grupy**. W przypadku przekazywania informacji o urządzeniu rozwiązania Autopilot za pomocą plików CSV jako nagłówka kolumny należy użyć tagu grupy, a nie atrybutu OrderID.  

## <a name="week-of-may-13-2019"></a>Tydzień od 13 maja 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359----"></a>Zasady usługi Intune aktualizują metodę uwierzytelniania i instalację aplikacji Portal firmy  <!-- 1927359  -->
Na urządzeniach, które zostały już zarejestrowane za pomocą Asystenta ustawień przy użyciu jednej z metod rejestracji urządzeń firmowych firmy Apple, usługa Intune nie będzie już obsługiwać aplikacji Portal firmy po jej ręcznym zainstalowaniu ze sklepu z aplikacjami przez użytkowników końcowych. Ta zmiana ma zastosowanie tylko w sytuacji, w której uwierzytelnianie jest przeprowadzane przy użyciu asystenta ustawień firmy Apple podczas rejestracji. Ta zmiana dotyczy tylko urządzeń z systemem iOS zarejestrowanych przy użyciu następujących rozwiązań:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Jeśli użytkownicy zainstalują aplikację Portal firmy ze sklepu z aplikacjami, a następnie podejmą próbę zarejestrowania urządzeń przy jej użyciu, wystąpi błąd. Oczekuje się, że te urządzenia będą używać aplikacji Portal firmy tylko w sytuacji, gdy nastąpi automatyczne wypchnięcie przez usługę Intune podczas rejestracji. Profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane tak, aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Jeśli chcesz, aby użytkownicy urządzenia DEP mieli aplikację Portal firmy, musisz określić swoje preferencje w profilu rejestracji. 

Ponadto ekran **Identyfikowanie urządzenia** w aplikacji Portal firmy dla systemu iOS jest usuwany. W związku z tym administratorzy, którzy chcą włączyć dostęp warunkowy lub wdrażać aplikacje firmowe, muszą zaktualizować profil rejestracji w programie DEP. To wymaganie ma zastosowanie tylko, jeśli rejestracja w programie DEP jest uwierzytelniana przy użyciu Asystenta ustawień. W takim przypadku należy wypchnąć aplikację Portal firmy do urządzenia. W tym celu wybierz pozycję **Intune** > **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Właściwości** > ustaw pozycję **Zainstaluj Portal firmy** na wartość **Tak**.

Aby zainstalować Portal firmy na już zarejestrowanych urządzeniach objętych programem DEP, należy przejść do usługi Intune > Aplikacje klienckie i wypchnąć ją jako aplikację zarządzaną przy użyciu zasad konfiguracji aplikacji. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Konfigurowanie sposobu aktualizowania aplikacji biznesowej (LOB) przez użytkowników końcowych przy użyciu zasad ochrony aplikacji <!-- 3568384 -->
Teraz w konfiguracji można określić, gdzie użytkownicy końcowi mogą uzyskać zaktualizowaną wersję aplikacji biznesowych (LOB). Użytkownicy końcowi będą widzieli tę funkcję w oknie dialogowym warunkowego uruchamiania **minimalnej wersji aplikacji**, które wyświetli monit o aktualizację do minimalnej wersji aplikacji LOB przez użytkownika końcowego. Te szczegółowe informacje dotyczące aktualizacji należy podać w ramach zasad ochrony aplikacji LOB. Ta funkcja jest dostępna w systemie iOS i Android. W systemie iOS ta funkcja wymaga zintegrowania aplikacji (lub opakowania za pomocą narzędzia opakowującego) z zestawem SDK usługi Intune dla systemu iOS w wersji 10.0.7 lub nowszej. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy. Aby skonfigurować sposób, w jaki użytkownik końcowy aktualizuje aplikację LOB, zasady konfiguracji aplikacji zarządzanej muszą zostać wysłane do aplikacji przy użyciu klucza, `com.microsoft.intune.myappstore`. Wysłana wartość określi, z którego sklepu użytkownik końcowy pobierze aplikację. Jeśli aplikacja jest wdrażana za pośrednictwem Portalu firmy, wartość musi być równa `CompanyPortal`. W przypadku każdego innego sklepu należy wprowadzić pełny adres URL.

#### <a name="intune-management-extension-powershell-scripts-----3734186----"></a>Skrypty programu PowerShell rozszerzające zarządzanie w ramach usługi Intune  <!-- 3734186  -->
Skrypty programu PowerShell można skonfigurować do uruchamiania z uprawnieniami administratora na urządzeniu. Aby uzyskać więcej informacji, zobacz [Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune](intune-management-extension.md) i [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Zarządzanie aplikacjami w usłudze Android Enterprise <!-- 4459905 -->
Aby ułatwić administratorom IT konfigurowanie i używanie zarządzania w usłudze Android Enterprise, cztery typowe aplikacje związane z usługą Android Enterprise zostaną automatycznie dodane do konsoli administracyjnej usługi Intune. Są to następujące cztery aplikacje w usłudze Android Enterprise:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  — używana w scenariuszach w pełni zarządzanych za pomocą Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** — pomaga zalogować się do kont w przypadku używania weryfikacji dwuskładnikowej.
- **[Intune — Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  — używana w przypadku scenariuszy obejmujących zasady ochrony aplikacji i profil służbowy Android Enterprise.
- [Zarządzany ekran główny](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) — używana w scenariuszach z użyciem Android Enterprise dla urządzeń dedykowanych/działających w trybie kiosku.

Wcześniej administratorzy IT musieli ręcznie znajdować i zatwierdzać te aplikacje w [zarządzanym sklepie Google Play](https://play.google.com/store/apps) w ramach procesu konfigurowania. Ta zmiana eliminuje te wcześniej wykonywane ręcznie kroki, aby klienci mogli łatwiej i szybciej zacząć korzystać z zarządzania w ramach usługi Android Enterprise.

Administratorzy zobaczą te cztery aplikacje automatycznie dodane do listy aplikacji usługi Intune podczas pierwszego połączenia swojego dzierżawcy usługi Intune z zarządzanym sklepem Google Play. Aby uzyskać więcej informacji, zobacz [Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play](connect-intune-android-enterprise.md). W przypadku dzierżawców, dla których już nawiązano połączenie lub rozpoczęto korzystanie z usługi Android Enterprise, administratorzy nie muszą nic robić. Te cztery aplikacje automatycznie staną się widoczne w ciągu 7 dni od ukończenia wdrożenia usługi w maju 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Zaktualizowany łącznik certyfikatów PFX dla usługi Microsoft Intune  <!-- 1533038 -->
Udostępniliśmy aktualizację [łącznika certyfikatów PFX dla usługi Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors), aby rozwiązać problem polegający na tym, że istniejące certyfikaty PFX były nadal ponownie przetwarzane, co powodowało zatrzymywanie przetwarzania nowych żądań przez łącznik.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Zadania zabezpieczeń usługi Intune dotyczące zaawansowanej ochrony przed zagrożeniami usługi Defender (w publicznej wersji zapoznawczej)     <!-- 3208597 -->
W publicznej wersji zapoznawczej można używać usługi Intune do zarządzania zadaniami zabezpieczeń dla [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](atp-manage-vulnerabilities.md). Dzięki integracji z Zaawansowaną ochroną przed zagrożeniami jest dodawane oparte na ryzyku podejście do odnajdywania, priorytetyzowania oraz korygowania luk w zabezpieczeniach i błędów konfiguracji punktów końcowych przy jednoczesnym skróceniu czasu między odnalezieniem i ograniczeniem ryzyka.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10 <!-- 3617671   idstaged-->
Wiele urządzeń z systemem Windows 10 lub nowszym zawiera mikroukład modułu TPM (Trusted Platform Module). Ta aktualizacja obejmuje nowe ustawienie zgodności, które sprawdza wersję mikroukładu modułu TPM na urządzeniu. 

To ustawienie jest opisane w artykule [Ustawienia zasad zgodności urządzeń z systemem Windows 10 lub nowszym](compliance-policy-create-windows.md#device-security).

Dotyczy: System Windows 10 lub nowszy

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Uniemożliwianie użytkownikom końcowym modyfikowania ich osobistego hotspotu i wyłączanie rejestrowania programu Siri na urządzeniach z systemem iOS <!-- 4097904   -->  
Dla urządzenia z systemem iOS można utworzyć profil ograniczeń urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia, które można skonfigurować:

- **Aplikacje wbudowane**: rejestrowanie po stronie serwera na potrzeby poleceń programu Siri
- **Sieć bezprzewodowa**: modyfikowanie osobistego hotspotu przez użytkownika (tylko tryb nadzorowany)

Aby wyświetlić te ustawienia, przejdź do [wbudowanych ustawień aplikacji dla systemu iOS](device-restrictions-ios.md#built-in-apps) i [ustawień sieci bezprzewodowej dla systemu iOS](device-restrictions-ios.md#wireless).

Dotyczy: system iOS 12.2 i nowsze

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Nowe ustawienia ograniczeń urządzeń w aplikacji Klasa dotyczące urządzeń z systemem macOS <!-- 4097905   --> 
Na urządzeniach z systemem macOS można utworzyć profile konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia aplikacji Klasa, opcję blokowania zrzutów ekranu oraz opcję wyłączania biblioteki zdjęć iCloud.

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-macos.md).

Dotyczy: systemu macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Nazwa ustawienia Hasło dostępu do sklepu z aplikacjami w systemie iOS została zmieniona<!-- 4557891  -->
Nazwa ustawienia **Hasło dostępu do sklepu z aplikacjami** została zmieniona na **Wymagaj hasła sklepu iTunes dla wszystkich zakupów** (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzeń** jako typ profilu > **Sklep App Store, wyświetlanie dokumentów i granie**).

Aby wyświetlić dostępne ustawienia, przejdź do sekcji [Ustawienia systemu iOS dla sklepu App Store, wyświetlanie dokumentów i granie](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Dotyczy: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Punkty odniesienia usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (wersja zapoznawcza)  <!--  3754134 -->
Dodaliśmy wersję zapoznawczą punktów odniesienia zabezpieczeń dla ustawień usługi [Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender](security-baseline-settings-defender-atp.md). Ten punkt odniesienia jest dostępny, jeśli środowisko spełnia wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Strona ze stanem rejestracji w systemie Windows jest teraz ogólnie dostępna <!-- 3605348 -->
Okres obowiązywania wersji zapoznawczej strony ze stanem rejestracji zakończył się. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Aktualizacja interfejsu użytkownika usługi Intune — tworzenie profilu rejestracji rozwiązania Autopilot  <!-- 4593669 -->
Interfejs użytkownika służący do tworzenia profilu rejestracji rozwiązania Autopilot został zaktualizowany w celu dostosowania do stylów interfejsu użytkownika platformy Azure. Aby uzyskać więcej informacji, zobacz [Create an Autopilot enrollment profile](https://docs.microsoft.com/intune/enrollment-autopilot#create-an-autopilot-deployment-profile) (Tworzenie profilu rejestracji rozwiązania Autopilot). W przyszłości dodatkowe scenariusze usługi Intune zostaną zaktualizowane do tego nowego stylu interfejsu użytkownika.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Włączanie resetowania rozwiązania Autopilot dla wszystkich urządzeń z systemem Windows <!-- 4225665 -->
Resetowanie rozwiązania Autopilot działa teraz dla wszystkich urządzeń Windows, nawet tych, które nie zostały skonfigurowane do używania strony ze stanem rejestracji. Jeśli strona ze stanem rejestracji nie została skonfigurowana na tym urządzeniu podczas początkowej rejestracji urządzenia, po zalogowaniu do urządzenia nastąpi bezpośrednie przejście do pulpitu. Synchronizacja urządzenia i wyświetlenie go jako zgodnego w usłudze Intune może potrwać do ośmiu godzin. Aby uzyskać więcej informacji, zobacz [Reset devices with remote Windows Autopilot Reset](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote) (Resetowanie urządzeń przy użyciu zdalnego resetowania rozwiązania Autopilot w systemie Windows).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Dokładny format numerów IMEI niewymagany w przypadku wyszukiwania wszystkich urządzeń <!--30407680 -->
W przypadku wyszukiwania **wszystkich urządzeń** nie trzeba uwzględniać spacji w numerach IMEI.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Usunięcie urządzenia w portalu firmy Apple zostanie odzwierciedlone w portalu usługi Intune <!--2489996 -->
Jeśli urządzenie zostanie usunięte z portalu usługi Device Enrollment Program firmy Apple lub portalu Apple Business Manager, to zostanie też automatycznie usunięte z usługi Intune podczas następnej synchronizacji.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Strona Stan rejestracji śledzi teraz aplikacje Win32 <!-- 2714451 -->
Dotyczy to tylko urządzeń z systemem Windows 10 w wersji 1903 lub nowszej. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Zbiorcze resetowanie i czyszczenie urządzeń za pomocą interfejsu API programu Graph <!-- 3295288 -->
Za pomocą interfejsu API programu Graph można teraz zbiorczo zresetować i wyczyścić do 100 urządzeń.


### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Okres obowiązywania wersji zapoznawczej raportu szyfrowania zakończył się   <!-- 4587546      -->
[Raport dotyczący szyfrowania funkcją BitLocker i szyfrowania urządzenia](encryption-monitor.md) jest teraz ogólnie dostępny i nie jest już częścią publicznej wersji zapoznawczej. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Ustawienia biometryczne i ustawienia podpisu programu Outlook dla urządzeń z systemami iOS i Android <!-- 4050557 -->
Teraz można określić, czy podpis domyślny jest włączony w programie Outlook na urządzeniach z systemem iOS i Android. Ponadto można zezwolić użytkownikom na zmianę ustawienia biometrycznego w programie Outlook w systemie iOS.

## <a name="week-of-may-6-2019"></a>Tydzień od 6 maja 2019 r. 

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Obsługa kontrolo dostępu do sieci (NAC) dla aplikacji F5 Access dla urządzeń z systemem iOS <!-- 4500808 -->

Firma F5 opublikowała aktualizację systemu BIG-IP 13 udostępniającą funkcje kontroli dostępu do sieci dla aplikacji F5 Access w systemie iOS w usłudze Intune. Aby użyć tej funkcji:

- Zaktualizuj system BIG-IP do odświeżonej wersji 13.1.1.5. System BIG-IP 14 nie jest obsługiwany.
- Zintegruj system BIG-IP z usługą Intune, aby móc korzystać z kontroli dostępu do sieci. Kroki opisano na stronie [Overview: Configuring APM for device posture checks with endpoint management systems](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html) (Omówienie: Konfigurowania programu APM pod kątem kontroli stanu urządzenia za pomocą systemów zarządzania punktem końcowym).
- Sprawdź ustawienie **Włącz kontrolę dostępu do sieci (NAC)** w profilu sieci VPN w usłudze Intune.

Aby wyświetlić dostępne ustawienia, przejdź na stronę [Konfigurowanie ustawień sieci VPN w urządzeniach z systemem iOS](vpn-settings-ios.md).

Dotyczy: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Zaktualizowany łącznik certyfikatów PFX dla usługi Microsoft Intune <!-- doc-vso 1521237  -->  
Udostępniliśmy aktualizację [łącznika certyfikatów PFX dla usługi Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors), która skraca odstęp czasu sondowania z 5 minut do 30 sekund.

## <a name="week-of-april-22-2019"></a>Tydzień od 22 kwietnia 2019 r.

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Używanie Menedżera zgodności do tworzenia ocen usługi Microsoft Intune<!-- 4404750 -->

[Menedżer zgodności](https://servicetrust.microsoft.com/ComplianceManager) (powoduje otwarcie innej witryny firmy Microsoft) to oparte na przepływie pracy narzędzie do oceny ryzyka w portalu Service Trust Portal firmy Microsoft. Umożliwia ono śledzenie, przypisywanie i weryfikowanie działań Twojej organizacji związanych z zapewnianiem zgodności z przepisami dotyczących usług firmy Microsoft. Możesz utworzyć własną ocenę zgodności przy użyciu usługi Office 365, platformy Azure, systemu Dynamics, usług Professional Services i usługi Intune. W przypadku usługi Intune dostępne są dwie oceny — FFIEC i RODO.

Menedżer zgodności ułatwia odpowiednie ukierunkowanie podejmowanych wysiłków, dzieląc kontrole na zarządzane przez firmę Microsoft i zarządzane przez Twoją organizację. Możesz ukończyć oceny, a następnie wyeksportować je i wydrukować.

Zgodność z [Federal Financial Institutions Examination Council (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (powoduje otwarcie innej witryny firmy Microsoft) to zbiór standardów dla bankowości internetowej wydany przez FFIEC. To najbardziej pożądana ocena dla instytucji finansowych, które korzystają z usługi Intune. Interpretuje ona, jak usługa Intune pomaga spełnić wytyczne FFIEC dotyczące cyberbezpieczeństwa związane z obciążeniami w chmurze publicznej. Ocena FFIEC usługi Intune jest drugą oceną FFIEC w Menedżerze zgodności.

W poniższym przykładzie można zobaczyć podział kontroli FFIEC. Firma Microsoft zarządza 64 kontrolami. Ty odpowiadasz za pozostałe 12 kontroli.

![Zobacz przykładową ocenę usługi Intune dla FFIEC, uwzględniającą działania klienta i działania firmy Microsoft](./media/intune-ffiec-assessment-status.png)

[Ogólne rozporządzenie o ochronie danych (RODO)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (powoduje otwarcie innej witryny firmy Microsoft) to prawo Unii Europejskiej, które pomaga chronić prawa osób i ich dane. RODO jest najbardziej pożądaną oceną, aby zapewnić zgodność z przepisami dotyczącymi ochrony prywatności. 

W poniższym przykładzie zostanie wyświetlony podział kontroli RODO. Firma Microsoft obsługuje 49 kontroli. Ty odpowiadasz za pozostałe 66 kontroli.

![Zobacz przykładową ocenę usługi Intune dla RODO, uwzględniającą działania klienta i działania firmy Microsoft](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Tydzień od 15 kwietnia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Szyfrowanie OpenSSL dla zasad ochrony aplikacji systemu Android <!-- 3747362 -->
Zasady ochrony aplikacji usługi Intune na urządzeniach z systemem Android używają teraz biblioteki szyfrowania OpenSSL zgodnej ze standardem FIPS 140-2. Aby uzyskać więcej informacji, zobacz sekcję [szyfrowanie](app-protection-policy-settings-android.md#encryption) w artykule [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Włączanie zależności aplikacji Win32 <!-- 2617348  -->
Jako administrator możesz wymagać zainstalowania innych aplikacji jako zależności przed zainstalowaniem aplikacji Win32. W szczególności na urządzeniu muszą zostać zainstalowane aplikacje zależne przed zainstalowaniem aplikacji Win32. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**, aby wyświetlić blok **Dodaj aplikację**. Wybierz pozycję **Aplikacja systemu Windows (Win32)** jako **typ aplikacji**. Po dodaniu aplikacji możesz wybrać pozycję **Zależności**, aby dodać aplikacje zależne, które należy zainstalować przed zainstalowaniem aplikacji Win32. Aby uzyskać więcej informacji, zobacz [Autonomiczna usługa Intune — zarządzanie aplikacjami Win32](apps-win32-app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Informacje o instalacji wersji aplikacji dla aplikacji ze sklepu Microsoft Store dla Firm <!-- 3537391   -->
Raporty dotyczące instalacji aplikacji obejmują informacje o wersji aplikacji w przypadku aplikacji ze sklepu Microsoft Store dla Firm. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. Wybierz pozycję **Microsoft Store dla firm**, a następnie wybierz pozycję **Stan instalacji urządzenia** w sekcji **Monitorowanie**.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Dodatki do reguł wymagań aplikacji Win32 <!-- 3676883   -->
Możesz utworzyć reguły wymagań na podstawie skryptów programu PowerShell, wartości rejestru i informacji o systemie plików. W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Następnie wybierz pozycję **Aplikacja systemu Windows (Win32)** jako **typ aplikacji** w bloku **Dodaj aplikację**.  Wybierz pozycję **Wymagania** > **Dodaj**, aby skonfigurować dodatkowe reguły wymagań. Następnie wybierz opcję **Typ pliku**, **Rejestr** lub **Skrypt** jako **Typ wymagania**. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Konfigurowanie aplikacji Win32 pod kątem instalowania na urządzeniach dołączonych do usługi Azure AD zarejestrowanych w usłudze Intune <!-- 3695227  -->
Można przypisać aplikacje Win32, które mają być instalowane na urządzeniach dołączonych do usługi Azure AD zarejestrowanych w usłudze Intune. Aby uzyskać więcej informacji o aplikacjach Win32 w usłudze Intune, zobacz [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

#### <a name="device-overview-shows-primary-user---3794259----"></a>Na stronie przeglądu urządzenia jest wyświetlany użytkownik podstawowy <!--3794259  -->
Na stronie Przegląd urządzenia będzie wyświetlany użytkownik podstawowy, nazywany również użytkownikiem koligacji urządzenia użytkownika (UDA). Aby zobaczyć użytkownika podstawowego dla urządzenia, wybierz pozycję **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie. Użytkownik podstawowy będzie wyświetlany w górnej części strony **Przegląd**.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Dodatkowe raportowanie aplikacji z zarządzanego sklepu Google Play dla urządzeń z profilem służbowym rozwiązania Android Enterprise <!-- 4105925  -->
W przypadku aplikacji z zarządzanego sklepu Google Play wdrożonych na urządzeniach z profilem służbowym rozwiązania Android Enterprise można wyświetlić numer wersji aplikacji zainstalowanej na urządzeniu. Dotyczy to tylko wymaganych aplikacji.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>Klawiatury innych firm dla systemu iOS <!-- 4111843   -->
Obsługa zasad ochrony aplikacji usługi Intune dla ustawienia **Klawiatury innych firm** dotyczącego systemu iOS zostanie zakończona z powodu zmiany na platformie iOS. Nie będzie można skonfigurować tego ustawienia w konsoli administracyjnej usługi Intune i nie będzie ono wymuszane na kliencie w zestawie SDK aplikacji usługi Intune.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Określanie ustawień logowania i kontrolowanie opcji ponownego uruchamiania na urządzeniach z systemem macOS <!-- 1210083  -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę > **Funkcje urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia okna logowania, takie jak wyświetlanie niestandardowego transparentu, wybór sposobu logowania użytkowników, pokazywanie lub ukrywanie ustawień zasilania i inne.

Aby zapoznać się z tymi ustawieniami, zobacz artykuł [Ustawienia funkcji urządzeń z systemem macOS](macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Konfigurowanie sieci Wi-Fi na dedykowanych urządzeniach z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia uruchamianych w trybie kiosku z wieloma aplikacjami <!--3041940  -->
Możesz włączyć ustawienia na urządzeniu z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia, kiedy jest ono uruchamiane jako dedykowane urządzenie w trybie kiosku z wieloma aplikacjami. W ramach tej aktualizacji możesz umożliwić użytkownikom konfigurowanie i nawiązywanie połączenia z sieciami Wi-Fi (**Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia, Ograniczenia dotyczące urządzeń** dla typu profilu > **Urządzenia dedykowane** > **Tryb kiosku**: **Kiosk z wieloma aplikacjami** > **Konfiguracja sieci Wi-Fi**). 

Aby wyświetlić wszystkie ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: Dedykowane urządzenia z rozwiązaniem Android Enterprise działające w trybie kiosku z wieloma aplikacjami


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Konfigurowanie połączenia Bluetooth i parowanie na dedykowanych urządzeniach z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia działających w trybie kiosku z wieloma aplikacjami <!-- 3041941  -->
Możesz włączyć ustawienia na urządzeniu z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia, kiedy jest ono uruchamiane jako dedykowane urządzenie w trybie kiosku z wieloma aplikacjami. W ramach tej aktualizacji można zezwolić użytkownikom końcowym na włączenie funkcji Bluetooth i parowanie urządzeń za pośrednictwem połączenia Bluetooth (**Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia, Ograniczenia dotyczące urządzeń** dla typu profilu > **Urządzenia dedykowane** > **Tryb kiosku**: **Kiosk z wieloma aplikacjami** > **Konfiguracja połączenia Bluetooth**). 

Aby wyświetlić wszystkie ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: Dedykowane urządzenia z rozwiązaniem Android Enterprise działające w trybie kiosku z wieloma aplikacjami

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Tworzenie i używanie profilów konfiguracji urządzeń za pomocą aplikacji OEMConfig w usłudze Intune <!-- 3305883  -->
W ramach tej aktualizacji usługa Intune obsługuje konfigurowanie urządzeń z rozwiązaniem Android Enterprise za pomocą aplikacji OEMConfig. Możesz utworzyć profil konfiguracji urządzenia i zastosować ustawienia do urządzeń z rozwiązaniem Android Enterprise przy użyciu aplikacji OEMConfig (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy).

Obsługa producentów OEM jest obecnie dostępna dla poszczególnych producentów OEM. Jeśli aplikacja OEMConfig nie jest dostępna na liście aplikacji OEMConfig, skontaktuj się z `IntuneOEMConfig@microsoft.com`.

Aby dowiedzieć się więcej na temat tej funkcji, zobacz artykuł [Use and manage Android Enterprise devices with OEMConfig in Microsoft Intune](android-oem-configuration-overview.md) (Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig w usłudze Microsoft Intune).

Dotyczy: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Powiadomienia usługi Windows Update  <!-- 3316758, 3316782  -->
Dodaliśmy dwa *ustawienia środowiska użytkownika* do konfiguracji pierścienia usługi Windows Update, którymi można zarządzać z poziomu konsoli usługi Intune. Teraz możesz:
- Blokować lub zezwalać użytkownikom na [skanowanie w poszukiwaniu aktualizacji systemu Windows](windows-update-settings.md).
- Zarządzać [poziomem powiadomień witryny Windows Update](windows-update-settings.md) widocznym dla użytkowników.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Nowe ustawienia ograniczeń urządzeń dla rozwiązania Android Enterprise w trybie Właściciel urządzenia <!-- 3574254  -->
Na urządzeniach z rozwiązaniem Android Enterprise można utworzyć profil ograniczeń urządzenia, aby zezwolić na funkcje lub ograniczyć je, ustawić reguły haseł i nie tylko (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz **Android Enterprise** jako platformę > **Tylko właściciel urządzenia > Ograniczenia dotyczące urządzeń** dla typu profilu). 

Ta aktualizacja obejmuje nowe ustawienia hasła, umożliwia pełny dostęp do aplikacji w sklepie Google Play dla w pełni zarządzanych urządzeń i nie tylko. Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md). 

Dotyczy: W pełni zarządzane urządzenia z rozwiązaniem Android Enterprise

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10 <!-- 3617671 -->

Ta funkcja jest opóźniona, a jej wdrożenie zaplanowano na później.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Zaktualizowano zmiany interfejsu użytkownika dla przeglądarki Microsoft Edge na urządzeniach z systemem Windows 10 lub nowszym <!-- 3775833   -->
Podczas tworzenia profilu konfiguracji urządzenia można umożliwić lub ograniczyć działanie funkcji przeglądarki Microsoft Edge na urządzeniach z systemem Windows 10 lub nowszym (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu > **Przeglądarka Microsoft Edge**). Po wprowadzeniu tej aktualizacji ustawienia przeglądarki Microsoft Edge są bardziej opisowe i łatwiejsze do zrozumienia. 

Aby wyświetlić te funkcje, przejdź do [ustawień ograniczeń dotyczących urządzeń w przeglądarce Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

Dotyczy: System Windows 10 lub nowszy

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Rozszerzona obsługa w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise (wersja zapoznawcza)  <!--   3903241, 3903244, 3903246   -->
Nadal w publicznej wersji zapoznawczej rozszerzyliśmy naszą obsługę w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise ([po raz pierwszy przedstawioną w styczniu 2019](whats-new.md#week-of-january-14-2019) w celu uwzględnienia następujących elementów: 

- Na w pełni zarządzanych i dedykowanych urządzeniach można utworzyć [zasady zgodności](compliance-policy-create-android-for-work.md), aby uwzględnić reguły dotyczące haseł i wymagania dotyczące systemu operacyjnego (**Zgodność urządzeń** > **Zasady** > **Utwórz zasady** > **Android Enterprise** dla platformy > **Właściciel urządzenia** dla typu profilu). 

  Na dedykowanych urządzeniach urządzenie może być wyświetlane jako **Niezgodne**. Dostęp warunkowy nie jest obsługiwany na dedykowanych urządzeniach. Pamiętaj, aby wykonać zadania lub akcje służące zapewnieniu zgodności dedykowanych urządzeń z przypisanymi zasadami.

- [Dostęp warunkowy](conditional-access.md) — zasady dostępu warunkowego, które mają zastosowanie do systemu Android, są stosowane również do w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise. Użytkownicy mogą teraz zarejestrować swoje w pełni zarządzane urządzenia w usłudze Azure Active Directory przy użyciu **aplikacji usługi Microsoft Intune**. Następnie można wyświetlić i rozwiązać wszelkie problemy ze zgodnością, aby uzyskać dostęp do zasobów organizacji.

- Nowa aplikacja użytkownika końcowego (aplikacja usługi Microsoft Intune) — istnieje nowa aplikacja użytkownika końcowego dla w pełni zarządzanych urządzeń z systemem Android o nazwie **Microsoft Intune**. Ta nowa aplikacja jest lekka, nowoczesna i zapewnia podobne funkcje jak aplikacja Portal firmy, ale dla w pełni zarządzanych urządzeń. Aby uzyskać więcej informacji, zobacz [aplikację Microsoft Intune w sklepie Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

W celu skonfigurowania w pełni zarządzanych urządzeń z systemem Android przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja w systemie Android** > **Firmowe, w pełni zarządzane urządzenia użytkowników**. Obsługa w pełni zarządzanych urządzeń z systemem Android pozostaje w wersji zapoznawczej i niektóre funkcje usługi Intune mogą nie być w pełni funkcjonalne.  

Aby dowiedzieć się więcej na temat tej wersji zapoznawczej, zapoznaj się z naszym blogiem: [Usługa Microsoft Intune — wersja zapoznawcza 2 dla w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Konfigurowanie profilu pod kątem pominięcia niektórych ekranów asystenta ustawień <!-- 2276470  -->
Podczas tworzenia profilu rejestracji systemu macOS możesz skonfigurować go tak, aby pominąć dowolny z następujących ekranów, gdy użytkownik będzie korzystać z asystenta ustawień:
- Wygląd
- Wyświetlanie sygnału
- iCloudStorage Jeśli tworzysz nowy profil lub edytujesz profil, wybrane pomijane ekrany muszą być synchronizowane z serwerem MDM firmy Apple.  Użytkownicy mogą wydać ręczną synchronizację urządzeń, aby nie było ma żadnego opóźnienia podczas pobierania zmian profilu.
Aby uzyskać więcej informacji, zobacz [Automatically enroll macOS devices with the Device Enrollment Program or Apple School Manager](device-enrollment-program-enroll-macos.md) (Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program lub usługi Apple School Manager).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Zbiorcze nadawanie nazw urządzeniom podczas rejestrowania urządzeń firmowych z systemem iOS<!--3566569  -->
Korzystając z jednej z metod rejestracji firmowej Apple (DEP/ABM/ASM), można ustawić format nazwy urządzenia w celu automatycznego nadawania nazw przychodzącym urządzeniom z systemem iOS. Możesz określić format, który zawiera typ urządzenia i numer seryjny w szablonie. Aby to zrobić, wybierz pozycję **Intune** > **Rejestrowanie urządzeń** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **wybierz token** >**Utwórz profil** > **Format nazewnictwa urządzeń**. Można edytować istniejące profile, ale nazwa będzie stosowana tylko dla nowo synchronizowanych urządzeń.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Zaktualizowano domyślny komunikat limitu czasu na stronie ze stanem rejestracji <!-- 3959331 -->
Zaktualizowaliśmy domyślny komunikat limitu czasu wyświetlany dla użytkowników, gdy strona ze stanem rejestracji przekroczy wartość limitu czasu określoną w profilu strony ze stanem rejestracji. Nowy komunikat domyślny jest widoczny dla użytkowników i pomaga im zrozumieć następne akcje do wykonania w odniesieniu do ich wdrożenia strony ze stanem rejestracji.  

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Wycofywanie niezgodnych urządzeń  <!-- 1827291   -->
Ta funkcja została odroczona, a jej wdrożenie jest planowane w przyszłej wersji.


### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Zmiany magazynu danych usługi Intune w wersji 1.0 są odzwierciedlane wstecznie w wersji beta <!-- 4403765 -->
Gdy wersja 1.0 zadebiutowała w wydaniu 1808, różniła się pod pewnymi istotnymi względami od wersji beta interfejsu API. W wydaniu 1903 te zmiany zostaną odzwierciedlone z powrotem w wersji beta interfejsu API. Jeśli masz ważne raporty korzystające z wersji beta interfejsu API, zdecydowanie zalecamy przełączenie tych raportów do wersji 1.0 w celu uniknięcia zmian powodujących niezgodności. Aby uzyskać więcej informacji, zobacz [Dziennik zmian dla interfejsu API magazynu danych usługi Intune](reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorowanie stanu punktów odniesienia zabezpieczeń (publiczna wersja zapoznawcza) <!-- 3082047 --> 
Dodaliśmy [widok według kategorii](security-baselines-monitor.md#per-category-view) do monitorowania punktów odniesienia zabezpieczeń. (Punkty odniesienia zabezpieczeń pozostają w wersji zapoznawczej). W widoku według kategorii wyświetlane są poszczególne kategorie z punktu odniesienia wraz z odsetkiem urządzeń należących do poszczególnych grup stanów dla danej kategorii. Teraz można zobaczyć, ile urządzeń nie pasuje do poszczególnych kategorii, jest nieprawidłowo skonfigurowanych lub nie ma zastosowania.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Tagi zakresu dla tokenów VPP firmy Apple <!--2371886  -->
Teraz możesz dodać tagi zakresu do tokenów VPP firmy Apple. Tylko użytkownicy z przypisanym tym samym tagiem zakresu będą mieli dostęp do tokenu VPP firmy Apple z tym tagiem. Aplikacje programu VPP i książki elektroniczne zakupione przy użyciu tego tokenu dziedziczą jego tagi zakresu. Aby uzyskać więcej informacji na temat tagów zakresu, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).







## <a name="week-of-april-1-2019"></a>Tydzień od 1 kwietnia 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Zaktualizowane łączniki certyfikatów  <!-- ICM 113304612 -->
Wydaliśmy aktualizacje dla [łącznika certyfikatów usługi Intune i łącznika certyfikatów PFX dla usługi Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors). Nowe wersje rozwiązują kilka znanych problemów.  

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Aktualizacja środowiska użytkownika aplikacji Portal firmy dla systemu iOS <!-- 2536024 -->
Strona główna aplikacji Portal firmy dla urządzeń z systemem iOS została przeprojektowana. Dzięki tej zmianie strona główna będzie bardziej zgodna z wzorcami interfejsu użytkownika systemu iOS, a także będzie zapewniać lepsze możliwości odnajdywania aplikacji i książek elektronicznych.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Zmiany dotyczące rejestracji za pomocą aplikacji Portal firmy dla użytkowników urządzeń z systemem iOS 12 <!--3448635 -->  
Ekrany i kroki rejestracji urządzeń z systemem iOS za pomocą aplikacji Portal firmy zostały zaktualizowane, aby były zgodne ze zmianami rejestracji w rozwiązaniu MDM wydanymi w systemie iOS 12.2 firmy Apple. Zaktualizowany przepływ pracy monituje użytkowników o:  

* Zezwolenie przeglądarce Safari na otwarcie witryny internetowej Portal firmy i pobranie profilu zarządzania przed powrotem do aplikacji Portal firmy.  
* Otwarcie aplikacji Ustawienia w celu zainstalowania profilu zarządzania na urządzeniu użytkownika.
* Powrót do aplikacji Portal firmy w celu ukończenia procesu rejestracji.  

Aby zapoznać się ze zaktualizowanymi krokami i ekranami rejestracji, zobacz [Rejestrowanie urządzenia z systemem iOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>Tydzień od 25 marca 2019 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Obsługa aplikacji Power BI Compliance z poziomu bloku Magazyn danych w usłudze Microsoft Intune <!-- 4260871 -->
Wcześniej link **Pobierz plik usługi Power BI** w bloku **Magazyn danych usługi Intune** umożliwiał pobranie raportu magazynu danych usługi Intune (pliku pbix). Ten raport został zastąpiony aplikacją Power BI Compliance. Aplikacja Power BI Compliance nie wymaga specjalnego ładowania ani konfiguracji. Będzie ona otwierana bezpośrednio w portalu usługi Power BI w trybie online i będzie wyświetlać dane dla Twojej dzierżawy usługi Intune na podstawie Twoich poświadczeń. W usłudze Intune wybierz link **Skonfiguruj magazyn danych usługi Intune** po prawej stronie bloku usługi Intune. Następnie kliknij pozycję **Pobierz aplikację Power BI**. Aby uzyskać więcej informacji, zobacz [Nawiązywanie połączenia z magazynem danych przy użyciu usługi Power BI](reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>Tydzień od 18 marca 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Wdrażanie programu Microsoft Visio i programu Microsoft Project <!-- 3725386  -->
Teraz możesz wdrożyć klienta klasycznego usługi Microsoft Project Online i program Microsoft Visio Pro dla usługi Office 365 jako niezależne aplikacje na urządzeniach z systemem Windows 10 przy użyciu usługi Microsoft Intune, jeśli jesteś właścicielem licencji dla tych aplikacji. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**, aby wyświetlić blok **Dodaj aplikację**. W bloku **Dodaj aplikację** wybierz **System Windows 10** jako **Typ aplikacji**. Następnie wybierz pozycję **Konfiguruj pakiet aplikacji**, aby wybrać aplikacje do zainstalowania. Aby uzyskać więcej informacji na temat aplikacji usługi Office 365 dla urządzeń z systemem Windows 10, zobacz [Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Zmiana nazwy produktu Microsoft Visio Pro dla usługi Office 365 <!-- 3593653  -->
Produkt **Microsoft Visio Pro dla usługi Office 365** teraz będzie nosił nazwę **Microsoft Visio Online Plan 2**.  Aby uzyskać więcej informacji na temat programu Microsoft Visio, zobacz [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Aby uzyskać więcej informacji na temat aplikacji usługi Office 365 dla urządzeń z systemem Windows 10, zobacz [Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Ustawienie limitu znaków w zasadach ochrony aplikacji usługi Intune <!-- 3291302  -->
Administratorzy usługi Intune mogą określić wyjątek od ustawienia zasad **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** w zasadach ochrony aplikacji usługi Intune.  Jako administrator możesz określić liczbę znaków, które mogą być wycinane lub kopiowane z zarządzanej aplikacji. To ustawienie umożliwia udostępnienie określonej liczby znaków w dowolnej aplikacji niezależnie od ustawienia „Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach”. Pamiętaj, że wersja aplikacji Portal firmy usługi Intune dla systemu Android wymaga wersji 5.0.4364.0 lub nowszej. Aby uzyskać więcej informacji, zobacz [Ochrona danych w systemie iOS](app-protection-policy-settings-ios.md#data-protection), [Ochrona danych w systemie Android](app-protection-policy-settings-android.md#data-protection), i [Przeglądanie dzienników ochrony aplikacji klienta](app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Plik XML narzędzia wdrażania pakietu Office dla wdrożenia pakietu Office ProPlus <!-- 3192477   -->
Można będzie udostępnić plik XML narzędzia wdrażania pakietu Office podczas tworzenia wystąpienia pakietu Office Pro Plus w konsoli administracyjnej usługi Intune. Zapewni to większe możliwości dostosowywania, jeśli istniejące opcje interfejsu użytkownika usługi Intune nie odpowiadają Twoim potrzebom. Aby uzyskać więcej informacji, zobacz [Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365) i [Opcje konfiguracji narzędzia wdrażania pakietu Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem <!-- 1429026  -->
W aplikacji Portal firmy dla systemu Windows ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem określanym na podstawie dominującego koloru ikony (jeśli można będzie go wykryć). O ile będzie to miało zastosowanie, to tło zastąpi szare obramowanie, które było wcześniej widoczne na kafelkach aplikacji. Użytkownicy zobaczą tę zmianę w wersjach aplikacji Portal firmy późniejszych niż 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Instalowanie dostępnych aplikacji przy użyciu aplikacji Portal firmy po rejestracji zbiorczej urządzeń z systemem Windows <!-- 2751523   -->
Urządzenia z systemem Windows zarejestrowane w usłudze Intune przy użyciu [rejestracji zbiorczej systemu Windows](windows-bulk-enroll.md) (pakietów aprowizacji) będą mogły instalować dostępne aplikacje przy użyciu aplikacji Portal firmy. Aby uzyskać więcej informacji na temat aplikacji Portal firmy, zobacz [Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10](store-apps-company-portal-app.md) i [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>Aplikację Microsoft Teams można wybrać jako część pakietu aplikacji pakietu Office <!-- 3828932  -->
Aplikację Microsoft Teams można dołączyć lub wykluczyć w ramach instalacji pakietu aplikacji pakietu Office Pro Plus. Ta funkcja działa w przypadku pakietu Office Pro Plus o numerze kompilacji 16.0.11328.20116. W celu ukończenia instalacji użytkownik musi się wylogować, a następnie ponownie zalogować na urządzeniu. W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Wybierz jeden z typów aplikacji **pakietu Office 365**, a następnie wybierz pozycję **Konfiguruj pakiet aplikacji**.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Automatyczne uruchamianie aplikacji podczas uruchamiania wielu aplikacji w trybie kiosku na urządzeniach z systemem Windows 10 lub nowszym <!-- 2351390 -->

Na urządzeniach z systemem Windows 10 lub nowszym możesz uruchomić urządzenie w trybie kiosku i uruchamiać wiele aplikacji. W ramach tej aktualizacji dostępne jest ustawienie **Automatyczne uruchamianie** (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** dla platformy > **Kiosku** dla typu profilu > **Kiosk z wieloma aplikacjami**). To ustawienie służy do automatycznego uruchamiania aplikacji, gdy użytkownik zaloguje się do urządzenia.

Aby wyświetlić listę i opis wszystkich ustawień kiosku, zobacz [Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk w usłudze Intune](kiosk-settings-windows.md).

Dotyczy: System Windows 10 lub nowszy

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Dzienniki operacyjne pokazują również informacje dotyczące niezgodnych urządzeń <!-- 4063755  -->
Podczas przekierowywania dzienników do funkcji usługi Azure Monitor można kierować również dzienniki operacyjne. W ramach tej aktualizacji dzienniki operacyjne zawierają również informacje dotyczące niezgodnych urządzeń. 

Więcej informacji na temat tej funkcji zawiera artykuł [Send log data to storage, event hubs, or log analytics in Intune](review-logs-using-azure-monitor.md) (Wysyłanie danych dziennika do magazynu, centrów zdarzeń lub analizy dzienników w usłudze Intune).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Przekierowywanie dzienników do usługi Azure Monitor dla dodatkowych obciążeń w usłudze Intune <!-- 3804627 -->
W usłudze Intune można przekierowywać dzienniki inspekcji i operacyjne do centrów zdarzeń, magazynu i analizy dzienników w usłudze Azure Monitor (**Intune** > **Monitorowanie** > **Ustawienia diagnostyki**). Dzięki tej aktualizacji można przekierowywać te dzienniki w dodatkowych obciążeniach usługi Intune, w tym obciążeniach zgodności, konfiguracji, aplikacji klienckich i innych. 

Aby dowiedzieć się więcej na temat przekierowywania dzienników do usługi Azure Monitor, zobacz [Wysyłanie danych dzienników do magazynu, centrów zdarzeń lub analizy dzienników](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Tworzenie i używanie rozszerzeń dla mobilności na urządzeniach Zebra z systemem Android w usłudze Intune <!-- 3305880   -->
W ramach tej aktualizacji usługa Intune obsługuje konfigurowanie urządzeń Zebra z systemem Android. Ściślej mówiąc, możesz utworzyć profil konfiguracji urządzenia i zastosować ustawienia do urządzeń Zebra z systemem Android przy użyciu profilów rozszerzeń dla mobilności (MX) generowanych przez rozwiązanie StageNow (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android** dla platformy > **Profil MX (tylko urządzenia Zebra)** dla typu profilu).

Aby uzyskać więcej informacji na temat tej funkcji, zobacz [Korzystanie z urządzeń Zebra i zarządzanie nimi za pomocą rozszerzeń dla mobilności w usłudze Intune](android-zebra-mx-overview.md).

Dotyczy: Android

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Raport szyfrowania urządzeń z systemem Windows 10 (w publicznej wersji zapoznawczej)<!-- 2351538 -->  
Nowy [raport szyfrowania (wersja zapoznawcza)](encryption-monitor.md) umożliwia wyświetlenie szczegółów dotyczących stanu szyfrowania urządzeń z systemem Windows 10. Dostępne szczegóły obejmują wersję modułu TPM urządzenia, gotowość szyfrowania i stan szyfrowania, raportowanie błędów i inne informacje.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Dostęp do kluczy odzyskiwania funkcji BitLocker z portalu usługi Intune (w publicznej wersji zapoznawczej) <!-- 2351547   -->  
Teraz możesz używać usługi Intune do [wyświetlania szczegółów](encryption-monitor.md) identyfikatora klucza funkcji BitLocker i kluczy odzyskiwania funkcji BitLocker z usługi Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Obsługa przeglądarki Microsoft Edge dla scenariuszy usługi Intune na urządzeniach z systemem Android i iOS <!-- 3411007 -->
Przeglądarka Microsoft Edge będzie obsługiwać wszystkie te same scenariusze zarządzania, co program Intune Managed Browser, dodając ulepszenia środowiska użytkownika końcowego. Funkcje dla przedsiębiorstw przeglądarki Microsoft Edge włączane przez zasady usługi Intune obejmują podwójną tożsamość, integrację zasad ochrony aplikacji, integrację serwera proxy aplikacji platformy Azure oraz zarządzane elementy ulubione i skróty do strony głównej. Aby uzyskać więcej informacji, zobacz [Obsługa przeglądarki Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Usługa Exchange Online/łącznik usługi Intune wycofują obsługę urządzeń tylko z programem EAS <!--3105122  -->
Konsola usługi Intune nie obsługuje już wyświetlania urządzeń typu „tylko EAS” podłączonych do usługi Exchange Online za pomocą łącznika usługi Intune ani zarządzania tymi urządzeniami. Zamiast tego do masz następujące opcje:
- Zarejestrowanie urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (MDM)
- Używanie zasad rozwiązania Intune App Protection do zarządzania urządzeniami
- Używanie kontrolek programu Exchange zgodnie z opisem w artykule [Clients and mobile in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) (Klienci i urządzenia przenośne w usłudze Exchange Online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Wyszukiwanie dokładnej nazwy urządzenia na stronie Wszystkie urządzenia przy użyciu elementu [name] <!--4254930 -->
Możesz teraz wyszukać dokładną nazwę urządzenia. Przejdź do strony **Intune** > **Urządzenia** > **Wszystkie urządzenia** > w polu wyszukiwania wprowadź nazwę urządzenia ujętą w nawiasy {}, aby wyszukać dokładne dopasowanie. Na przykład **{Urządzenie12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Obsługa dodatkowych łączników na stronie Stan dzierżawy <!-- 3617202  -->
Na [stronie Stan dzierżawy](tenant-status.md) są teraz wyświetlane informacje o stanie dodatkowych łączników, w tym *zaawansowanej ochrony przed zagrożeniami programu Windows Defender* (ATP) i innych łączników Mobile Threat Defense.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Udzielenie dostępu tylko do odczytu do usługi Intune niektórym rolom usługi Azure Active Directory <!-- 3637917  -->
Dostęp tylko do odczytu do usługi Intune został udzielony poniższym rolom usługi Azure AD. Uprawnienia przyznane przy użyciu ról usługi Azure AD zastępują uprawnienia przyznane przy użyciu kontroli dostępu na podstawie ról (RBAC) usługi Intune.

Dostęp tylko do odczytu do danych inspekcji usługi Intune:

- Administrator zgodności
- Administrator danych zgodności

Dostęp tylko do odczytu do wszystkich danych usługi Intune:

- Administrator zabezpieczeń
- Operator zabezpieczeń
- Czytelnik zabezpieczeń

Aby uzyskać więcej informacji, zobacz [Kontrola dostępu na podstawie ról](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Tagi zakresu dla profilów aprowizacji aplikacji systemu iOS <!--2934430   -->
Możesz dodać tag zakresu do profilu aprowizacji aplikacji systemu iOS, tak aby tylko osoby z rolami przypisanymi do tego tagu zakresu miały dostęp do profilu aprowizacji aplikacji systemu iOS. Aby uzyskać więcej informacji, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Tagi zakresu dla zasad konfiguracji aplikacji <!--2371891   -->
Możesz dodać tag zakresu do zasad konfiguracji aplikacji, tak aby tylko osoby z rolami przypisanymi do tego tagu zakresu miały dostęp do zasad konfiguracji aplikacji. Zasady konfiguracji aplikacji mogą być przeznaczone tylko dla lub skojarzone tylko z aplikacjami przypisanymi do tego samego tagu zakresu. Aby uzyskać więcej informacji, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Obsługa przeglądarki Microsoft Edge dla scenariuszy usługi Intune na urządzeniach z systemem Android i iOS <!-- 3411007 -->
Przeglądarka Microsoft Edge będzie obsługiwać wszystkie te same scenariusze zarządzania, co program Intune Managed Browser, dodając ulepszenia środowiska użytkownika końcowego. Funkcje dla przedsiębiorstw przeglądarki Microsoft Edge włączane przez zasady usługi Intune obejmują podwójną tożsamość, integrację zasad ochrony aplikacji, integrację serwera proxy aplikacji platformy Azure oraz zarządzane elementy ulubione i skróty do strony głównej. Aby uzyskać więcej informacji, zobacz [Obsługa przeglądarki Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>Tydzień od 25 lutego 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="intune-powershell-module----951068----"></a>Moduł programu Intune PowerShell <!-- 951068  -->
Moduł programu Intune PowerShell, który zapewnia obsługę interfejsu API usługi Intune za pośrednictwem programu Microsoft Graph, jest teraz dostępny w [Galerii programu Microsoft PowerShell](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Szczegółowe informacje na temat sposobu korzystania z tego modułu](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Przykłady scenariuszy z użyciem tego modułu](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Ulepszona obsługa optymalizacji dostarczania  <!--3183757  -->
Rozszerzyliśmy obsługę konfigurowania optymalizacji dostarczania w usłudze Intune. Teraz możesz skonfigurować rozszerzoną listę [ustawień optymalizacji dostarczania](delivery-optimization-settings.md) i zastosować ją do urządzeń z bezpośrednio z poziomu konsoli usługi Intune.


## <a name="week-of-february-18-2019"></a>Tydzień od 18 lutego 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Usługa Intune będzie korzystać z interfejsów API usługi Google Play Protect na urządzeniach z systemem Android <!-- 2577355   -->
Niektórzy administratorzy IT muszą radzić sobie ze środowiskiem BYOD, w którym użytkownicy końcowi mogą rootować swoje telefony komórkowe lub wykonywać ich jailbreak. To zachowanie, choć czasem podejmowane bez złych zamiarów, powoduje obejście wielu zasad usługi Intune określonych w celu ochrony danych organizacji na urządzeniach użytkowników końcowych. W związku z tym usługa Intune udostępnia funkcję wykrywania rootingu i jailbreaku dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. W tej wersji usługa Intune wykorzysta interfejsy API usługi Google Play do dodania sprawdzeń dotyczących wykrywania rootingu dla urządzeń niezarejestrowanych. Mimo że firma Google nie udostępnia wszystkich wykonywanych sprawdzeń dotyczących rootingu, oczekujemy, że te interfejsy API wykrywają użytkowników, którzy wykonali rooting swojego urządzenia z dowolnej przyczyny — od dostosowania urządzenia do umożliwienia pobierania nowszych aktualizacji systemu operacyjnego na starszych urządzeniach. Następnie można zablokować dostęp tych użytkowników do danych firmowych lub wyczyścić ich konta firmowe z aplikacji obsługujących zasady. Dodatkowo administratorzy IT otrzymają kilka aktualizacji raportowania w bloku Intune App Protection — raport „Użytkownicy z flagą” pokazuje użytkowników wykrytych za pomocą skanowania przy użyciu interfejsu API SafetyNet usługi Google Play Protect, a raport „Potencjalnie szkodliwe aplikacje” pokazuje aplikacje wykryte za pomocą skanowania przy użyciu interfejsu API Verify Apps firmy Google. Ta funkcja jest dostępna w systemie Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informacje o aplikacji Win32 dostępne w bloku Rozwiązywanie problemów <!-- 2617342   -->
Masz teraz możliwość zbierania plików dziennika błędów dla instalacji aplikacji Win32 w bloku **Rozwiązywanie problemów** aplikacji usługi Intune. Aby uzyskać więcej informacji na temat rozwiązywania problemów z instalacją aplikacji, zobacz [Rozwiązywanie problemów z instalacją aplikacji](troubleshoot-app-install.md) i [Rozwiązywanie problemów z aplikacjami Win32](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Szczegóły stanu aplikacji systemu iOS <!-- 3761235   -->
Wprowadzono nowe komunikaty o błędzie dla instalacji aplikacji związane z następującymi sytuacjami:
- Błąd aplikacji programu VPP podczas instalowania na współużytkowanym urządzeniu iPad
- Błąd, jeśli sklep App Store jest wyłączony
- Błąd szukania licencji programu VPP dla aplikacji
- Błąd instalacji aplikacji systemowych za pomocą dostawcy rozwiązania MDM
- Błąd instalacji aplikacji, gdy urządzenie jest w trybie zgubienia lub kiosku
- Błąd instalacji aplikacji, gdy użytkownik nie jest zalogowany do sklepu App Store

W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > „Nazwa aplikacji” > **Stan instalacji urządzenia**. Nowe komunikaty o błędzie będą dostępne w kolumnie **Szczegóły stanu**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Nowy ekran Kategorie aplikacji w aplikacji Portal firmy dla systemu Windows 10<!-- 3834780  -->
Dodano nowy ekran o nazwie **Kategorie aplikacji** w celu poprawy środowiska przeglądania i wyboru aplikacji w aplikacji Portal firmy dla systemu Windows 10. Użytkownicy będą teraz widzieli aplikacje posortowane w ramach kategorii, takich jak **Polecane**, **Edukacja** i **Produktywność**. Ta zmiana pojawia się w aplikacji Portal firmy w wersji 10.3.3451.0 i nowszych. Aby wyświetlić nowy ekran, zobacz [co nowego w interfejsie użytkownika aplikacji](https://docs.microsoft.com/intune/whats-new-app-ui). Aby uzyskać więcej informacji na temat aplikacji w Portalu firmy, zobacz [Instalowanie i udostępnianie aplikacji na urządzeniu](/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Aplikacja Power BI Compliance <!-- 1455231 doc-work-item -->
Można uzyskiwać dostęp do magazynu danych usługi Intune w usłudze Power BI Online przy użyciu aplikacji [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Za pomocą tej aplikacji usługi Power BI możesz teraz uzyskiwać dostęp do wstępnie utworzonych raportów i udostępniać je bez żadnej konfiguracji i bez opuszczania przeglądarki internetowej. Aby uzyskać więcej informacji, zobacz [Dziennik zmian — aplikacja Power BI Compliance](reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>Skrypty programu PowerShell można uruchomić w ramach 64-bitowego hosta na urządzeniach 64-bitowych <!-- 1862675   -->
Po dodaniu skryptu programu PowerShell do profilu konfiguracji urządzenia skrypt jest zawsze wykonywany jako 32-bitowy nawet w 64-bitowych systemach operacyjnych. Dzięki tej aktualizacji administrator może uruchomić skrypt w ramach 64-bitowego hosta programu PowerShell na urządzeniach 64-bitowych (**Konfiguracja urządzenia** > **Skrypty PowerShell** > **Dodaj** > **Konfiguruj** > **Uruchom skrypt w 64-bitowym hoście programu PowerShell**).

Aby uzyskać więcej informacji na temat korzystania z programu PowerShell, zobacz [Skrypty programu PowerShell w usłudze Intune](intune-management-extension.md).

Dotyczy: System Windows 10 lub nowszy

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>Użytkownicy systemu macOS otrzymują monit o zaktualizowanie swojego hasła <!-- 1873216 -->
Usługa Intune wymusza ustawienie **ChangeAtNextAuth** na urządzeniach z systemem macOS. To ustawienie ma wpływ na użytkowników końcowych i urządzenia, które mają zasady zgodności haseł lub profile haseł w ograniczeniach dotyczących urządzenia. Użytkownicy końcowi są monitowani raz o zaktualizowanie swojego hasła. Ten monit jest wyświetlany zawsze, gdy użytkownik po raz pierwszy uruchamia zadanie, które wymaga uwierzytelniania, na przykład logowanie się na urządzeniu. Użytkownicy mogą również otrzymywać monit o zaktualizowanie swojego hasła podczas wykonywania czegokolwiek, co wymaga uprawnień administracyjnych, na przykład podczas żądania dostępu do pęku kluczy. 

Wszelkie zmiany nowych lub istniejących zasad haseł przez administratora powodują ponowne monitowanie użytkowników końcowych o zaktualizowanie swojego hasła.

Dotyczy:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521------"></a>Przypisywanie certyfikatów SCEP do urządzenia z systemem macOS bez użytkowników    <!-- 2340521    -->
Możesz przypisać certyfikaty protokołu Simple Certificate Enrollment Protocol (SCEP) przy użyciu atrybutów urządzenia do urządzeń z systemem macOS, w tym urządzeń bez koligacji użytkownika, i skojarzyć profil certyfikatu z profilami sieci Wi-Fi lub sieci VPN. Powoduje rozszerzenie obsługi [przypisywania certyfikatów protokołu SCEP na urządzeniach z lub bez koligacji użytkownika](certificates-profile-scep.md) z systemem Windows, iOS i Android.  Ta aktualizacja dodaje opcję wyboru typu certyfikatu *Urządzenie* podczas konfigurowania profilu certyfikatu protokołu SCEP dla systemu macOS.

Dotyczy: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Aktualizacja interfejsu użytkownika dostępu warunkowego usługi Intune   <!-- 2432313   -->
Wprowadziliśmy ulepszenia interfejsu użytkownika dla dostępu warunkowego w konsoli usługi Intune. Należą do nich następujące elementy:
- Zastąpienie bloku *Dostęp warunkowy* usługi Intune blokiem z usługi Azure Active Directory. Dzięki temu będziesz mieć dostęp do pełnego zakresu ustawień i konfiguracji dotyczących [dostępu warunkowego](conditional-access.md) (który pozostaje technologią usługi Azure AD) z poziomu konsoli usługi Intune. 
- Nazwa bloku *Dostęp lokalny* została zmieniona na *Dostęp do programu Exchange* i przenieśliśmy konfigurację *łącznika usługi Exchange* do tego bloku.  Ta zmiana umieszcza w jednym miejscu [konfigurowanie i monitorowanie szczegółów dotyczących usługi Exchange online i lokalnej](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Aplikacje Kiosk Browser i Microsoft Edge mogą pracować na urządzeniach z systemem Windows 10 w trybie kiosku <!-- 2935135   -->
Urządzenia z systemem Windows 10 pracujące w trybie kiosku umożliwiają uruchamianie jednej lub wielu aplikacji. Ta aktualizacja obejmuje kilka zmian dotyczących korzystania z aplikacji w trybie kiosku, w tym:

- Możliwość uruchamiania przeglądarek Microsoft Edge i Kiosk Browser jako aplikacji na urządzeniu kiosku (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **System Windows 10 i nowsze** dla platformy > **Kiosk** dla typu profilu).
- Dostępne są nowe funkcje i ustawienia służące do zezwalania na nie lub ich ograniczania (**Konfiguracja urządzenia** > **Profile** > **Nowy profil**  > **System Windows 10 i nowsze**dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu), w tym:

- Przeglądarka Microsoft Edge:
  - Użyj trybu kiosku przeglądarki Microsoft Edge
  - Odśwież przeglądarkę po czasie bezczynności

- Ulubione i wyszukiwanie:
  - Zezwalaj na zmiany aparatu wyszukiwania

Aby uzyskać listę tych ustawień zobacz:

- [Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk](kiosk-settings-windows.md)
- [Ograniczenia urządzeń z przeglądarką Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Ograniczenia urządzeń dotyczące ulubionych i wyszukiwania](device-restrictions-windows-10.md##favorites-and-search)

Dotyczy: System Windows 10 lub nowszy

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Nowe ustawienia ograniczeń urządzeń z systemami iOS i macOS <!-- 3448774   -->
Istnieje możliwość ograniczenia niektórych ustawień i funkcji na urządzeniach z systemami iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **iOS** lub **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja dodaje kolejne funkcje i ustawienia, które można kontrolować, w tym ustawianie czasu korzystania z urządzenia, zmienianie ustawień karty eSIM, planów komórkowych i nie tylko na urządzeniach z systemem iOS. Ponadto umożliwia opóźnianie widoczności aktualizacji oprogramowania dla użytkownika i blokowanie buforowania zawartości na urządzeniach z systemem macOS. 

Aby wyświetlić funkcje i ustawienia, które można ograniczyć, zobacz:

- [Ustawienia ograniczeń dotyczących urządzeń z systemem iOS](device-restrictions-ios.md)
- [Ustawienia ograniczeń dotyczących urządzeń z systemem macOS](device-restrictions-macos.md)

Dotyczy:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Urządzenia typu „kiosk” są teraz nazywane „urządzeniami dedykowanymi” na urządzeniach z rozwiązaniem Android Enterprise <!-- 3598402   -->
W celu dopasowania do terminologii systemu Android określenie **kiosk** zostało zmienione na **urządzenia dedykowane** dla urządzeń z rozwiązaniem Android Enterprise (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > ** Android Enterprise jako platforma > **Tylko właściciel urządzenia** > **Ograniczenia dotyczące urządzeń** > **Urządzenia dedykowane**).

Aby zobaczyć dostępne ustawienia, przejdź do artykułu [Ustawienia urządzeń w celu zezwolenia na funkcje lub ich ograniczenie](device-restrictions-android-for-work.md#dedicated-device-settings).

Dotyczy:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Ustawienia systemu iOS dotyczące przeglądarki Safari i opóźniania widoczności aktualizacji oprogramowania użytkownika są przenoszone w interfejsie użytkownika usługi Intune <!-- 3640850, 3803313   -->
W przypadku urządzeń z systemem iOS można skonfigurować ustawienia przeglądarki Safari i aktualizacje oprogramowania. W ramach tej aktualizacji wymienione ustawienia są przenoszone do różnych części interfejsu użytkownika usługi Intune:

- Ustawienia przeglądarki Safari zostały przeniesione z pozycji **Safari**(**Konfiguracja urządzenia** > **Profile** > **Nowy profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu) do pozycji **[Aplikacje wbudowane](device-restrictions-ios.md#built-in-apps)** .
- Ustawienie **Opóźnianie widoczności aktualizacji oprogramowania użytkownika dla urządzeń z systemem iOS w trybie nadzorowanym** (**Aktualizacje oprogramowania** > **Aktualizuj zasady dla systemu iOS**) jest przenoszone do obszaru **Ograniczenia urządzeń** >  **[Ogólne](device-restrictions-ios.md#general)** .  Aby uzyskać szczegółowe informacje o wpływie na istniejące zasady, zobacz [aktualizacje oprogramowania systemu iOS](software-updates-ios.md#configure-the-policy). 

Aby uzyskać listę ustawień, zobacz:

- [Ograniczenia dotyczące urządzeń z systemem iOS](device-restrictions-ios.md) 
- [Aktualizacje oprogramowania systemu iOS](software-updates-ios.md)

Ta funkcja ma zastosowanie do: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Nazwa opcji Włączanie ograniczeń w ustawieniach urządzenia zostanie zmieniona na Czas korzystania z urządzenia na urządzeniach z systemem iOS <!-- 3699164   -->
Istnieje możliwość skonfigurowania pozycji **Włączanie ograniczeń w ustawieniach urządzenia** na urządzeniach nadzorowanych z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu > **Ogólne**). W ramach tej aktualizacji nazwa tego ustawienia zostanie zmieniona na **Czas korzystania z urządzenia (tylko nadzorowane)** . 

Zachowanie jest takie samo. W szczególności: 

- System iOS 11.4.1 i starsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie własnych ograniczeń w ustawieniach urządzenia. 
- System iOS 12.0 i nowsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie pozycji **Czas korzystania z urządzenia** w ustawieniach urządzenia, w tym ograniczeń dotyczących zawartości i prywatności. Na urządzeniach uaktualnionych do systemu iOS 12.0 karta ograniczeń nie będzie już widoczna w ustawieniach urządzenia. Te ustawienia znajdują się teraz w obszarze **Czas korzystania z urządzenia**. 

Aby uzyskać listę ustawień, zobacz [Ograniczenia urządzeń z systemem iOS](device-restrictions-ios.md#general).

Dotyczy: 
- iOS


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Zmiana nazwy zarejestrowanego urządzenia z systemem Windows <!-- 1911112  -->
Teraz można zmienić nazwę zarejestrowanego urządzenia z systemem Windows 10 (RS4 lub nowszym). Aby to zrobić, wybierz pozycje **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Zmień nazwę urządzenia**. Ta funkcja nie obsługuje obecnie zmiany nazw urządzeń z systemem Windows dołączonych hybrydowo do usługi Azure AD.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Automatyczne przypisywanie tagów zakresu do zasobów utworzonych przez administratora przy użyciu danego zakresu <!-- 3173823  -->
Gdy administrator utworzy zasób, wszelkie tagi zakresu przypisane do administratora zostaną automatycznie przypisane do nowych zasobów.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Raport rejestracji zakończonych niepowodzeniem został przeniesiony do bloku Rejestrowanie urządzeń <!-- 3560202  -->
Raport **Rejestracje zakończone niepowodzeniem** został przeniesiony do sekcji **Monitorowanie** bloku **Rejestrowanie urządzeń**. Dodano również dwie nowe kolumny (Metoda rejestracji i Wersja systemu operacyjnego).

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Nazwa raportu porzucania portalu firmy została zmieniona na Niekompletne rejestracje użytkownika <!--3815076 eemiss -->
Nazwa raportu **Porzucanie portalu firmy** została zmieniona na **Niekompletne rejestracje użytkownika**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Tydzień od 4 lutego 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Tryb ciemny Portalu firmy usługi Intune w systemie macOS <!-- 3300524  -->
Portal firmy usługi Intune w systemie macOS obsługuje teraz tryb ciemny systemu macOS. Po włączeniu trybu ciemnego na urządzeniu z systemem macOS w wersji 10.14 lub nowszej aplikacja Portal firmy dostosuje swój wygląd do kolorów używanych w tym trybie.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>Tydzień od 21 stycznia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Wyskakujące powiadomienia dla aplikacji Win32 <!-- 3136566   -->
Można pominąć wyświetlanie wyskakujących powiadomień dla użytkownika końcowego podczas przypisywania aplikacji. W usłudze Intune wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację > **Przypisania** > **Uwzględnij grupy**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Aktualizacja interfejsu użytkownika zasad ochrony aplikacji usługi Intune <!-- 3251427  -->
Zmieniliśmy etykiety ustawień i przycisków funkcji ochrony aplikacji usługi Intune, aby ułatwić ich zrozumienie. Oto niektóre zmiany:  
- Kontrolki **tak** / **nie** zostały zmienione głównie na kontrolki **blokuj** / **zezwalaj** oraz  **wyłącz** / **włącz**. Etykiety również zostały aktualizowane.  
- Format ustawień został zmieniony, dzięki czemu ustawienie i jego etykieta znajdują się obok siebie w kontrolce, umożliwiając lepszą nawigację.   

Ustawienia domyślne i liczba ustawień pozostają takie same, lecz ta zmiana pozwala użytkownikowi lepiej zrozumieć i wykorzystać ustawienia w celu stosowania wybranych zasad ochrony aplikacji, a także łatwiej nawigować po nich. Aby uzyskać informacje, zobacz [Ustawienia systemu iOS](app-protection-policy-settings-ios.md) i [Ustawienia systemu Android](app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Dodatkowe ustawienia dla programu Outlook <!-- 3301182  -->
Teraz za pomocą usługi Intune można skonfigurować następujące dodatkowe ustawienia dla programu Outlook w systemach iOS i Android:

- Zezwalanie na użycie wyłącznie kont służbowych w programie Outlook dla systemów iOS i Android
- Wdrażanie nowoczesnego uwierzytelniania dla usługi Office 365 oraz kont lokalnych nowoczesnego uwierzytelniania hybrydowego
- Używanie wartości `SAMAccountName` dla pola nazwy użytkownika w profilu poczty e-mail, gdy jest wybrane uwierzytelnianie podstawowe
- Zezwalanie na zapisywanie kontaktów
- Konfigurowanie porad dotyczących poczty adresatów zewnętrznych
- Konfigurowanie **priorytetowej skrzynki odbiorczej**
- Wymaganie danych biometrycznych w celu uzyskania dostępu do programu Outlook dla systemu iOS
- Blokowanie obrazów zewnętrznych

> [!NOTE]
> Jeśli do zarządzania dostępem do tożsamości firmowych są używane zasady rozwiązania Intune App Protection, warto rozważyć wyłączenie **wymagania danych biometrycznych**. Aby uzyskać więcej informacji, zobacz **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** dla [ustawień dotyczących dostępu systemu iOS](app-protection-policy-settings-ios.md#access-requirements) i [ustawień dotyczących dostępu systemu Android](app-protection-policy-settings-android.md#access-requirements).

Aby uzyskać więcej informacji, zobacz [ustawienia konfiguracji programu Microsoft Outlook](app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Usuwanie aplikacji systemu Android Enterprise <!-- 1352553 -->
Możesz usuwać aplikacje z zarządzanego sklepu Google Play z poziomu usługi Microsoft Intune. Aby usunąć aplikację z zarządzanego sklepu Google Play, otwórz usługę Microsoft Intune w witrynie Azure Portal i wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje**. Na liście aplikacji wybierz wielokropek (...) po prawej stronie aplikacji z zarządzanego sklepu Google Play, a następnie wybierz pozycję **Usuń** z wyświetlonej listy. Po usunięciu aplikacji zarządzanej ze sklepu Google Play z listy aplikacji ta aplikacja zarządzana stanie się automatycznie aplikacją niezatwierdzoną.

#### <a name="managed-google-play-app-type----1352580---"></a>Typ aplikacji zarządzanej ze sklepu Google Play <!-- 1352580 -->
Dzięki zastosowaniu typów aplikacji **zarządzanych ze sklepu Google Play** będzie można wybiórczo dodawać [aplikacje zarządzane ze sklepu Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do usługi Intune. Administratorzy usługi Intune mogą przeglądać, wyszukiwać, zatwierdzać, synchronizować i przypisywać zatwierdzone aplikacje zarządzane ze sklepu Google Play z poziomu usługi Intune.  Nie jest już konieczne przechodzenie do zarządzanej konsoli Google Play i dokonywanie ponownego uwierzytelniania.  W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Natomiast na liście **Typ aplikacji** będzie trzeba wybrać pozycję **Zarządzany sklep Google Play**.

### <a name="default-android-pin-keyboard----3802457---"></a>Domyślna klawiatura systemu Android dla numeru PIN <!-- 3802457 -->
Użytkownicy końcowi, którzy ustawili numer PIN dla zasad ochrony aplikacji usługi Intune na swoich urządzeniach z systemem Android przy użyciu typu „Numeryczne”, będą teraz widzieć domyślną klawiaturę systemu Android zamiast stałego interfejsu użytkownika klawiatury systemu Android zaprojektowanego wcześniej. Tę zmianę wprowadzono w celu wprowadzenia spójności podczas korzystania z klawiatur domyślnych w systemach Android i iOS dla typów numeru PIN „Numeryczne” i/lub „Kod dostępu”. Aby uzyskać więcej informacji na temat ustawień dostępu użytkownika końcowego w systemie Android, takich dotyczących numeru PIN zasad ochrony aplikacji, zobacz [Wymagania dostępu dla systemu Android](app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Używanie ustawień zalecanych przez firmę Microsoft z punktami odniesienia zabezpieczeń (publiczna wersja zapoznawcza) <!-- 2055484   -->

Usługa Intune umożliwia integrację z innymi usługami koncentrującymi się na zabezpieczeniach, w tym z usługą Windows Defender ATP i usługą Office 365 ATP. Klienci pytają o typową strategię i spójny zestaw kompleksowych przepływów pracy zabezpieczeń w usługach Microsoft 365. Naszym celem jest dopasowanie strategii w celu utworzenia rozwiązań, które łączą operacje zabezpieczeń i typowe zadania administratora. W usłudze Intune staramy się osiągnąć ten cel, publikując zestaw „punktów odniesienia zabezpieczeń” zalecanych przez firmę Microsoft (**Intune** > **Punkty odniesienia zabezpieczeń**).  Administrator może tworzyć zasady zabezpieczeń bezpośrednio z tych punktów odniesienia, a następnie wdrażać je dla użytkowników. Możesz również dostosować rekomendacje dotyczące najlepszych rozwiązań do potrzeb organizacji. Usługa Intune zapewnia, że urządzenia pozostają w zgodności z tymi punktami odniesienia, i powiadamia administratorów użytkowników lub urządzeń, które nie są zgodne.

Ta funkcja jest dostępna w publicznej wersji zapoznawczej, więc wszystkie profile utworzone teraz nie zostaną przeniesione do ogólnie dostępnych szablonów punktów odniesienia zabezpieczeń. Nie należy planować używania szablonów dostępnych w wersji zapoznawczej w środowisku produkcyjnym.

Aby dowiedzieć się więcej na temat punktów odniesienia zabezpieczeń, zobacz temat [Create a Windows 10 security baseline in Intune](security-baselines-monitor.md) (Tworzenie punktu odniesienia zabezpieczeń systemu Windows 10 w usłudze Intune).

Ta funkcja ma zastosowanie do: System Windows 10 lub nowszy

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Użytkownicy inni niż administratorzy mogą włączyć funkcję BitLocker na urządzeniach z systemem Windows 10 dołączonych do usługi Azure AD<!-- 2147379   -->
Włączenie ustawień funkcji BitLocker na urządzeniach z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Endpoint Protection** jako typ profilu > **Szyfrowanie systemu Windows**) oznacza dodanie ustawień funkcji BitLocker. 

Ta aktualizacja obejmuje nowe ustawienie funkcji BitLocker, które zezwala użytkownikom standardowym (innym niż administratorzy) na włączanie szyfrowania. 

Aby wyświetlić te ustawienia, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052  eepublished  -->
Ta aktualizacja zawiera nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **System Windows 10 i nowsze** > **Zgodność z programem Configuration Manager**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu tego ustawienia można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie jest niezgodne w usłudze Intune.

To ustawienie opisano w sekcji [Zgodność z programem Configuration Manager](compliance-policy-create-windows.md#configuration-manager-compliance).

Dotyczy: System Windows 10 lub nowszy

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Dostosowywanie tapety na urządzeniach nadzorowanych z systemem iOS przy użyciu profilu konfiguracji urządzenia <!-- 2809324   -->
Podczas tworzenia profilu konfiguracji urządzenia dla urządzeń z systemem iOS można dostosowywać niektóre funkcje (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Funkcje urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia obszaru **Tapeta**, które umożliwiają administratorowi użycie obrazu PNG, JPG lub JPEG na ekranie głównym lub ekranie blokady. Te ustawienia dotyczące tapety mają zastosowanie tylko na urządzeniach nadzorowanych. 

Listę tych ustawień można znaleźć w temacie [iOS device feature settings](ios-device-features-settings.md) (Ustawienia funkcji urządzeń z systemem iOS).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Kiosk systemu Windows 10 jest ogólnie dostępny <!-- 3594661  -->
W tej aktualizacji funkcja kiosku jest udostępniana ogólnie na urządzeniach z systemem Windows 10 i nowszych. Aby zapoznać się ze wszystkimi ustawieniami, które można dodać i skonfigurować, zobacz temat [Ustawienia kiosku dla systemu Windows 10 (i nowszego)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth zostało usunięte z obszaru Ograniczenia dotyczące urządzeń > Właściciel urządzenia w systemie Android Enterprise <!-- 3598396   -->
Podczas tworzenia profilu ograniczeń dotyczących urządzeń z systemem Android Enterprise widoczne jest ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**. W ramach tej aktualizacji ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth** zostało usunięte (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy > **Ograniczenia dotyczące urządzeń > Właściciel urządzenia** dla typu profilu > **Ogólne**). 

Ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth** nie jest obsługiwane w przypadku zarządzania właścicielami urządzeń w systemie Android Enterprise. Po usunięciu tego ustawienia nie będzie ono miało wpływu na jakiekolwiek urządzenia czy dzierżawy, nawet jeśli to ustawienie zostało włączone i skonfigurowane w środowisku.

Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: właściciel urządzenia z systemem Android Enterprise

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Obsługa selektywnego czyszczenia danych dla urządzeń usługi WIP bez rejestracji <!-- 1434452 -->
Usługa Windows Information Protection Without Enrollment (WIP-WE) umożliwia klientom ochronę danych firmowych na urządzeniach z systemem Windows 10 bez konieczności pełnej rejestracji w rozwiązaniu MDM. Gdy dokumenty są chronione za pomocą zasad funkcji WIP-WE, chronione dane mogą być selektywnie czyszczone przez administratora usługi Intune. Wybierając użytkownika i urządzenie oraz wysyłając żądanie czyszczenia, wszystkie dane chronione za pomocą zasad funkcji WIP-WE staną się bezużyteczne. Z usługi Intune w witrynie Azure Portal wybierz pozycję **Aplikacja mobilna** > **Selektywne czyszczenie aplikacji**.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Nowe dzienniki operacyjne i możliwość wysyłania dzienników do usług Azure Monitor <!-- 3762211  -->
Usługa Intune ma wbudowaną funkcję rejestrowania inspekcji, która śledzi zdarzenia w miarę wprowadzania zmian. Ta aktualizacja obejmuje nowe funkcje rejestrowania, w tym: 
- Dzienniki operacyjne (wersja zapoznawcza), które pokazują szczegóły użytkowników i zarejestrowanych urządzeń, łącznie z próbami udanymi i nieudanymi.
- Dzienniki inspekcji i dzienniki operacyjne można wysyłać do usługi Azure Monitor, łącznie z informacjami na temat kont magazynu, centrów zdarzeń i analizy dzienników. Usługi te pozwalają na przechowywanie danych rejestrowania, korzystanie z analiz, takich jak Splunk i QRadar, oraz uzyskiwanie wizualizacji danych rejestrowania.

Więcej informacji na temat tej funkcji zawiera artykuł [Send log data to storage, event hubs, or log analytics in Intune](review-logs-using-azure-monitor.md) (Wysyłanie danych dziennika do magazynu, centrów zdarzeń lub analizy dzienników w usłudze Intune).

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Pomijanie większej liczby ekranów Asystenta ustawień na urządzeniu DEP z systemem iOS <!-- 2687509  -->
Oprócz ekranów, które obecnie możesz pominąć, możesz skonfigurować urządzenia z systemem iOS objęte programem DEP tak, aby następujące ekrany Asystenta ustawień były pomijane podczas rejestracji urządzenia przez użytkownika: Ton wyświetlacza, Prywatność, Migracja systemu Android, Przycisk Strona główna, iMessage i FaceTime, Przechodzenie do usługi, Migracja urządzenia Watch, Wygląd, Czas korzystania z urządzenia, Aktualizacja oprogramowania, Instalator SIM.
Aby wybrać ekrany do pominięcia, przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Właściwości** > **Dostosowywanie Asystenta ustawień** > wybierz pozycję **Ukryj**  dla ekranów do pominięcia > **OK**.
Jeśli tworzysz nowy profil lub edytujesz profil, wybrane pomijane ekrany muszą być synchronizowane z serwerem MDM firmy Apple. Użytkownicy mogą wydać ręczną synchronizację urządzeń, aby nie było ma żadnego opóźnienia podczas pobierania zmian profilu.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Wdrażanie aplikacji APP-WE dla systemu Android Enterprise <!-- 1171203 -->
Dla urządzeń z systemem Android w scenariuszu wdrażania zasad ochrony aplikacji bez rejestracji (APP-WE) możesz teraz używać zarządzanego sklepu Google Play w celu wdrażania aplikacji ze sklepu i aplikacji biznesowych dla użytkowników. Mówiąc ściślej, możesz udostępnić użytkownikom końcowym środowisko katalogu i instalacji aplikacji, które nie wymaga już od użytkowników końcowych obniżenia poziomu zabezpieczeń urządzeń przez umożliwienie instalacji z nieznanych źródeł. Ponadto ten scenariusz wdrażania zapewni ulepszone środowisko pracy użytkownika końcowego.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>Tydzień od 14 stycznia 2019 r.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Obsługa należących do firmy, w pełni zarządzanych urządzeń z systemem Android — wersja zapoznawcza <!-- 1574342  -->
Usługa Intune obsługuje teraz w pełni zarządzane, należące do firmy urządzenia z systemem Android w scenariuszu „właściciel urządzenia”, w którym urządzenia są ściśle zarządzane przez dział IT i są powiązane z poszczególnymi użytkownikami. Pozwala to administratorom na zarządzanie całym urządzeniem, wymuszanie rozszerzonej gamy opcji kontroli zasad niedostępnych dla profilów służbowych oraz ograniczanie możliwości instalowania aplikacji przez użytkowników tylko do aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz [Konfigurowanie rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android](android-fully-managed-enroll.md) i [Rejestracja urządzeń dedykowanych i w pełni zarządzanych](android-dedicated-devices-fully-managed-enroll.md).  Należy pamiętać, że ta funkcja jest dostępna w wersji zapoznawczej. Niektóre funkcje usługi Intune, takie jak certyfikaty, zgodność i dostęp warunkowy, nie są obecnie dostępne dla w pełni zarządzanych urządzeń użytkowników z systemem Android.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>Tydzień od 7 stycznia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-app-pin----2298397---"></a>Numer PIN aplikacji usługi Intune <!-- 2298397 -->
Jako administrator IT masz teraz możliwość skonfigurowania, ile dni użytkownik końcowy może czekać, aż będzie musiał zmienić numer PIN aplikacji usługi Intune. Nowe ustawienie, czyli *resetowanie numeru PIN po określonej liczbie dni*, jest dostępne w witrynie Azure Portal w obszarze **Intune** > **Aplikacje klienckie** > **Zasady ochrony aplikacji** > **Utwórz zasady** > **Ustawienia** > **Wymagania dotyczące dostępu**. Ta funkcja jest dostępne dla urządzeń z systemami [iOS](app-protection-policy-settings-ios.md) i [Android](app-protection-policy-settings-android.md) i obsługuje dodatnie liczby całkowite.


#### <a name="intune-device-reporting-fields----2748738---"></a>Pola raportów dotyczących urządzeń w usłudze Intune <!-- 2748738 -->
Usługa Intune udostępnia dodatkowe pola raportów dotyczących urządzeń, takie jak na przykład identyfikator rejestracji aplikacji, producent systemu Android, model i wersja poprawki zabezpieczeń, a także model urządzenia z systemem iOS. W usłudze Intune te pola są dostępne po wybraniu opcji **Aplikacje klienckie** > **Stan ochrony aplikacji** i wybraniu pozycji **Raport ochrony aplikacji: iOS, Android**. Ponadto te parametry będą pomocne w przypadku konfigurowania listy **dozwolonych** dla producenta urządzenia (Android), listy **dozwolonych** dla modelu urządzenia (Android i iOS) oraz ustawienia minimalnej wersji poprawki zabezpieczeń systemu Android. 


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Szablony administracyjne są dostępne w publicznej wersji zapoznawczej i zostały przeniesione do własnego profilu konfiguracji <!-- 3322847 -->

Szablony administracyjne w usłudze Intune (**Konfiguracja urządzenia** > **Szablony administracyjne**) są obecnie dostępne w publicznej wersji zapoznawczej. Dzięki tej aktualizacji

- Szablony administracyjne obejmują około 300 ustawień, którymi można zarządzać w usłudze Intune. Wcześniej ustawienia te istniały tylko w edytorze zasad grupy.
- Szablony administracyjne są dostępne w publicznej wersji zapoznawczej.
- Szablony administracyjne są przenoszone z obszaru **Konfiguracja urządzenia** > **Szablony administracyjne** do obszaru **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz pozycję  **Windows 10 i nowsze** > w polu **Typ profilu** wybierz pozycję **Szablony administracyjne**.
- Funkcja Raportowanie jest włączona

Aby dowiedzieć się więcej na temat tej funkcji, zobacz [szablony systemu Windows 10 służące do konfigurowania ustawień zasad grupy](administrative-templates-windows.md).

Dotyczy: System Windows 10 lub nowszy

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Używanie protokołu S/MIME do szyfrowania i rejestrowania wielu urządzeń użytkownika  <!-- 1333642 -->
Ta aktualizacja obejmuje szyfrowanie poczty e-mail za pomocą protokołu S/MIME z użyciem profilu nowo zaimportowanego certyfikatu (**Konfiguracja urządzenia** > **Profil** > **Utwórz profil** > wybierz platformę > typ profilu **Zaimportowany certyfikat PKCS**). W usłudze Intune można importować certyfikaty w formacie PFX. Usługa Intune może następnie dostarczać te same certyfikaty do wielu urządzeń zarejestrowanych przez jednego użytkownika. Obejmuje to również:
- Profil natywnej poczty e-mail systemu iOS obsługuje włączanie szyfrowania S/MIME przy użyciu importowanych certyfikatów w formacie PFX.
- Natywna aplikacja poczty na urządzeniach z systemem Windows Phone 10 automatycznie używa certyfikatu szyfrowania S/MIME.
- Certyfikaty prywatne mogą być dostarczane na wielu platformach. Jednak nie wszystkie aplikacje poczty e-mail obsługują szyfrowanie S/MIME.
- Na innych platformach może być konieczne ręczne skonfigurowanie aplikacji poczty, aby włączyć szyfrowanie S/MIME.  
- Aplikacje poczty e-mail, które obsługuje szyfrowanie S/MIME może obsługiwać pobieranie certyfikatów dla protokołu S/MIME szyfrowania wiadomości e-mail w sposób, który nie obsługuje zarządzania urządzeniami Przenośnymi, takie jak odczytywanie ich z magazynu certyfikatów ich wydawcy.
Aby uzyskać więcej informacji na temat tej funkcji, zapoznaj się z [omówieniem protokołu S/MIME do podpisywania i szyfrowania wiadomości e-mail](certificates-s-mime-encryption-sign.md).
Obsługiwane na: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nowe opcje automatycznego łączenia i utrzymywania reguł w przypadku korzystania z ustawień systemu DNS w systemie Windows 10 lub nowszym <!-- 1333665, 2999078 -->
Na urządzeniach z systemem Windows 10 lub nowszym możesz utworzyć profil konfiguracji sieci VPN z listą serwerów DNS, która pozwala na rozpoznawanie domen, np. contoso.com. Ta aktualizacja obejmuje nowe ustawienia funkcji rozpoznawania nazw (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **Windows 10 i nowsze** > wybierz typ profilu **VPN** > **Ustawienia DNS** >**Dodaj**): 
- **Połącz automatycznie**: po wybraniu pozycji **Włączone** urządzenie automatycznie łączy się z siecią VPN po nawiązaniu kontaktu z wprowadzoną domeną, np. contoso.com.
- **Trwałe**: domyślnie wszystkie reguły tabeli zasad rozpoznawania nazw (NRPT) są aktywne reguły tak długo, jak długo urządzenie jest połączone za pomocą tego profilu sieci VPN. Gdy to ustawienie jest **włączone** dla reguły tabeli NRPT, reguła pozostanie aktywna na urządzeniu, nawet wtedy gdy połączenie sieci VPN zostanie rozłączone. Reguła pozostaje aktywna do momentu usunięcia profilu sieci VPN lub ręcznego usunięcia reguły, co można wykonać w programie PowerShell.
W temacie [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md) opisano te ustawienia. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Korzystanie z wykrywania zaufanych sieci na użytek profilów sieci VPN na urządzeniach z systemem Windows 10 <!-- 1500165 -->
W przypadku korzystania z wykrywania zaufanych sieci możesz wyłączyć automatyczne tworzenie połączenia sieci VPN w profilach sieci VPN, gdy użytkownik będzie już w zaufanej sieci. Dzięki tej aktualizacji masz możliwość dodawania sufiksów DNS w celu włączenia wykrywania zaufanych sieci na urządzeniach z systemem Windows 10 i nowszych (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **VPN** jako typ profilu).
Aktualną listę ustawień sieci VPN można znaleźć w temacie [Windows 10 VPN settings](vpn-settings-windows-10.md) (Ustawienia sieci VPN w systemie Windows 10).

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Zarządzanie urządzeniami z systemem Windows Holographic for Business używanymi przez wielu użytkowników <!-- 1907917, 1063203 -->
Obecnie można konfigurować ustawienia komputera udostępnionego na urządzeniach z systemem Windows 10 i Windows Holographic for Business przy użyciu niestandardowego ustawienia OMA-URI. W ramach tej aktualizacji dodawany jest nowy profil służący do konfigurowania ustawień komputera udostępnionego (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** > **Urządzenie udostępnione wielu użytkownikom**).
Aby dowiedzieć się więcej na temat tej funkcji, zobacz [ustawienia usługi Intune do zarządzania urządzeniami udostępnionymi](shared-user-device-settings.md).
Dotyczy: system Windows 10 lub nowsze oraz system Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Nowe ustawienia aktualizacji systemu Windows 10 <!--2626030  2512994  -->
W przypadku [pierścieni aktualizacji systemu Windows 10](windows-update-for-business-configure.md) możesz skonfigurować:
- **Zachowanie automatycznych aktualizacji**: użyj nowej opcji *Resetuj do domyślnych* w celu przywrócenia oryginalnych ustawień automatycznych aktualizacji na maszynie z systemem Windows 10 z *aktualizacją z października 2018 r.*
- **Blokowanie wstrzymywania aktualizacji systemu Windows przez użytkownika**: skonfiguruj nowe ustawienie aktualizacji oprogramowania, które umożliwia zezwalanie użytkownikom na wstrzymywanie instalacji aktualizacji lub blokowanie tej możliwości w obszarze *Ustawienia* ich komputerów. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>Profile poczty e-mail w systemie iOS mogą używać szyfrowania i podpisywania protokołu S/MIME <!-- 2662949 -->
Masz możliwość tworzenia profilu poczty e-mail z różnymi ustawieniami. Ta aktualizacja obejmuje między innymi ustawienia protokołu S/MIME, których można używać do podpisywania i szyfrowania wiadomości e-mail na urządzeniach z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **iOS** > wybierz typ profilu **E-mail**).
Lista ustawień znajduje się w obszarze [ustawień konfiguracji poczty e-mail systemu iOS](email-settings-ios.md).

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Niektóre ustawienia funkcji BitLocker obsługują wersję systemu Windows 10 Pro<!-- 2727036 -->
Możesz utworzyć profil konfiguracji, który definiuje ustawienia programu Endpoint Protection na urządzeniach z systemem Windows 10, w tym ustawienia funkcji BitLocker. W tej aktualizacji dodano obsługę systemu Windows 10 Professional dla niektórych ustawień funkcji BitLocker. Aby wyświetlić te ustawienia ochrony, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Nazwa konfiguracji urządzenia udostępnionego została zmieniona na Komunikat ekranu blokady dla urządzeń z systemem iOS w witrynie Azure Portal<!-- 2809362 -->
W przypadku tworzenia profilu konfiguracji dla urządzeń z systemem iOS możesz dodać ustawienia obszaru **Konfiguracja urządzenia udostępnianego** w celu wyświetlania określonego tekstu na ekranie blokady. Ta aktualizacja obejmuje następujące zmiany: 
- Ustawienia **Konfiguracja urządzenia udostępnianego** w witrynie Azure Portal są zmieniane na „Komunikat ekranu blokady (tylko tryb nadzorowany)” (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **iOS** > wybierz typ profilu **Funkcje urządzenia** > **Komunikat ekranu blokady**).
- Podczas dodawania wiadomości ekranu blokady można wstawić numer seryjny, nazwę urządzenia lub inną wartość specyficzną dla urządzenia w obszarze **Informacje dotyczące tagu zasobu** i **Przypis dolny ekranu blokady**. Na przykład można wprowadzić wartości `Device name: {{devicename}}` lub `Serial number is {{serialnumber}}`, używając nawiasów klamrowych. Listę dostępnych tokenów do użycia można znaleźć w sekcje [iOS tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) (Tokeny systemu iOS).
Listę ustawień można znaleźć w temacie dotyczącym [ustawień wyświetlania komunikatów na ekranie blokady](shared-device-settings-ios.md).

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Do urządzeń z systemem iOS dodano nowe ustawienia ograniczeń urządzenia obejmujące sklep App Store, wyświetlanie dokumentów i gry <!-- 2827760-->
W obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** >  **iOS** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu > **App Store, wyświetlanie dokumentów, gry** dodano następujące ustawienia: Zezwalanie aplikacjom zarządzanym na zapisywanie kontaktów na kontach niezarządzanych kontaktów. Zezwalanie niezarządzanym aplikacjom na odczytywanie z kont kontaktów zarządzanych. Aby wyświetlić te ustawienia, zobacz [ograniczenia urządzeń z systemem iOS](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nowe ustawienia powiadomień, wskazówek i funkcji blokowania klawiatury na urządzeniach właściciela urządzenia z systemem Android Enterprise <!-- 3201839 3201843 -->
Ta aktualizacja obejmuje kilka nowych funkcji dotyczących urządzeń z systemem Android Enterprise uruchamianych jako właściciel urządzenia. Aby korzystać z tych funkcji, przejdź do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz wartość **Android Enterprise** > w polu **Typ profilu** wybierz wartość **Tylko właściciel urządzenia** > **Ograniczenia urządzenia**.

Nowe funkcje obejmują: 

- Wyłączanie wyświetlania powiadomień systemowych, w tym połączeń przychodzących, alertów systemowych, błędów systemu i innych.
- Sugerowanie pomijania samouczków i wskazówek dotyczących aplikacji otwieranych po raz pierwszy.
- Wyłączanie zaawansowanych ustawień funkcji blokady klawiatury, takich jak aparat, powiadomienia, odblokowywanie odciskiem palca i inne.


Aby zapoznać się z tymi ustawieniami, zobacz [ustawienia ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Urządzenia właściciela urządzenia z systemem Android Enterprise mogą używać zawsze włączonych połączeń VPN <!-- 3202194 -->
Dzięki tej aktualizacji będziesz mieć możliwość używania zawsze włączonych połączeń sieci VPN na urządzeniach właściciela urządzenia z systemem Android Enterprise. Zawsze włączone połączenia sieci VPN pozostają aktywne lub są natychmiast przywracane, gdy użytkownik odblokuje urządzenie, gdy urządzenie uruchomi się ponownie lub gdy zmieni się sieć bezprzewodowa. Połączenie można również przenieść do trybu „blokady”, który powoduje zablokowanie całego ruchu sieciowego do momentu uaktywnienia połączenia sieci VPN.
Zawsze włączoną sieć VPN możesz włączyć za pomocą ustawień **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Ograniczenia dotyczące urządzeń** dla opcji Tylko właściciel urządzenia > **Łączność**. Aby zapoznać się z tymi ustawieniami, zobacz [ustawienia ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nowe ustawienie służące do kończenia procesów w Menedżerze zadań na urządzeniach z systemem Windows 10 <!-- 3285177 --> 
Ta aktualizacja obejmuje nowe ustawienie służące do kończenia procesów w Menedżerze zadań na urządzeniach z systemem Windows 10. Używając profilu konfiguracji urządzenia (ustawienia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz wartość **Windows 10** > w polu **Typ profilu** wybierz wartość **Ograniczenia dotyczące urządzeń** > **Ogólne**), możesz zezwolić na to ustawienie lub je zablokować.
Aby zapoznać się z bieżącymi ustawieniami, zobacz [ustawienia ograniczeń urządzeń z systemem Windows 10](device-restrictions-windows-10.md).
Dotyczy: System Windows 10 lub nowszy


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Bardziej szczegółowe komunikaty dotyczące błędów ograniczeń rejestracji <!-- 3111564 -->
Bardziej szczegółowe komunikaty o błędach będą dostępne, gdy ograniczenia rejestracji nie zostaną spełnione. Aby wyświetlić te komunikaty, przejdź do obszaru **Intune** > **Rozwiązywanie problemów** i zapoznaj się z tabelą błędów rejestracji. Aby uzyskać więcej informacji, zobacz [listę błędów rejestracji](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="tenant-status-dashboard-----1124854---"></a>Pulpit nawigacyjny stanu dzierżawy  <!-- 1124854 -->
Nowa [strona stanu dzierżawy](tenant-status.md) to jedna lokalizacja, w której można wyświetlać stan i powiązane szczegóły dzierżawy.  Pulpit nawigacyjny jest podzielony na cztery obszary:
- **Szczegóły dzierżawy**: zawiera informacje takie jak nazwa i lokalizacja dzierżawy, urząd zarządzania urządzeniami przenośnymi, łączna liczba zarejestrowanych urządzeń w Twojej dzierżawie i liczba licencji. Ta sekcja zawiera także bieżącą wersję usługi dla Twojej dzierżawy.
- **Stan łącznika**: zawiera informacje na temat dostępnych skonfigurowanych łączników, może również zawierać te, które nie zostały jeszcze włączone.  
   Na podstawie bieżącego stanu łączniki są oznaczane flagami Dobra kondycja, Ostrzeżenie lub Zła kondycja. Wybierz łącznik, aby przejść do szczegółów lub skonfigurować dla niego dodatkowe informacje.
- **Kondycja usługi Intune**: zawiera szczegółowe informacje dotyczące aktywnych zdarzeń lub awarii w dzierżawie. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office.
- **Wiadomości w usłudze Intune**: zawiera aktywne wiadomości dla Twojej dzierżawy. Wiadomości obejmują takie elementy jak na przykład powiadomienia o tym, że dzierżawa otrzymała najnowsze funkcje usługi Intune.  Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nowe środowisko pomocy i obsługi technicznej w aplikacji Portal firmy w systemie Windows 10 <!-- 1488939-->
Nowa strona pomocy i obsługi technicznej w aplikacji Portal firmy umożliwia użytkownikom rozwiązywanie problemów i zwracanie się o pomoc w zakresie aplikacji i problemów z dostępem. Na nowej stronie użytkownicy mogą wysłać wiadomość e-mail zawierającą szczegóły błędu oraz informacje z dziennika diagnostycznego, a także znaleźć kontakt do pomocy technicznej organizacji. Mają również dostęp do sekcji z często zadawanymi pytaniami i linkami do odpowiedniej dokumentacji usługi Intune. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nowe środowisko pomocy i obsługi technicznej dla usługi Intune   <!-- #3307080 -->
W ciągu kilku najbliższych dni wprowadzimy nowe środowisko pomocy i obsługi technicznej dla wszystkich dzierżaw. Nowe środowisko jest dostępne dla usługi Intune i można uzyskać do niego dostęp, korzystając z bloków usługi Intune w witrynie [Azure Portal](https://portal.azure.com/).
Nowe środowisko pozwala opisać problem własnymi słowami i uzyskać szczegóły dotyczące rozwiązywania problemu oraz zawartość internetową dotyczącą korygowania. Te rozwiązania są oferowane za pośrednictwem algorytmu uczenia maszynowego opartego na regułach i sterowanego przez zapytania użytkownika. Oprócz korzystania ze wskazówek specyficznych dla problemu możesz użyć nowego przepływu pracy tworzenia sprawy do otwarcia zgłoszenia do pomocy technicznej za pomocą poczty e-mail lub telefonu. To nowe środowisko zastępuje poprzednie środowisko Pomocy i obsługi technicznej w postaci statycznego zestawu wstępnie wybranych opcji określonych na podstawie obszaru konsoli aktywnego podczas otwierania środowiska Pomoc i obsługa techniczna. Aby uzyskać więcej informacji, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-apps----1081941---"></a>Tagi zakresu dla aplikacji <!-- 1081941 -->
Możesz tworzyć tagi zakresu w celu ograniczenia dostępu do ról i aplikacji. Możesz dodać tag zakresu do aplikacji, tak aby tylko osoby z rolą przypisaną do tego tagu zakresu miały dostęp do aplikacji. Obecnie do aplikacji dodanych do usługi Intune z zarządzanego sklepu Google Play lub aplikacji kupionych w ramach programu Apple Volume Purchase Program (VPP) nie można przypisywać tagów zakresu. Planowane jest wprowadzenie tej funkcji w przyszłości. Aby uzyskać więcej informacji, zobacz [Używanie tagów zakresu do filtrowania zasad](scope-tags.md).

## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]
