---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 969e7bc4804e1f66230c76d742bec2c67c2fa006
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670911"
---
# <a name="in-development-for-microsoft-intune---august-2019"></a>W trakcie opracowywania — Microsoft Intune — sierpień 2019 r.

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

### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144---"></a>Sterowanie zachowaniem odinstalowywania aplikacji dla systemu iOS przy wyrejestrowywaniu urządzenia <!-- 3504144 -->
Administratorzy będą mogli zarządzać tym, czy aplikacja zostanie usunięta czy zatrzymana na urządzeniu, gdy urządzenie zostanie wyrejestrowane na poziomie użytkownika lub grupy urządzeń. 

### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Kategoryzowanie aplikacji ze sklepu Microsoft Store dla Firm <!-- 3926922 -->
Będziesz mieć możliwość kategoryzowania Microsoft Store aplikacji dla firm. Aby to zrobić, wybierz opcję**aplikacje** **klienckie** > usługi **Intune** > > wybierz**kategorię**Microsoft Store dla aplikacji biznesowej > kategorii **informacji o** > aplikacji. Z menu rozwijanego Przypisz kategorię.
### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji <!-- 2576686 -->
Zasady ochrony aplikacji usługi Intune (aplikacje) na urządzeniach z systemem Android i iOS umożliwiają kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji z obsługą aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android <!-- 3041956  -->
W przypadku dostępnych instalacji aplikacji na urządzeniach z profilem służbowym systemu Android można wyświetlić stan instalacji aplikacji oraz zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809----"></a>Niektóre ograniczenia nienadzorowanego urządzenia z systemem iOS zostaną nadzorowane — tylko w przypadku wersji iOS 13,0 <!-- 4867809  -->
Niektóre ustawienia zostaną zastosowane tylko do nadzorowanych urządzeń z systemem iOS 13,0. Należą do nich następujące ustawienia:

- Sklep App Store, wyświetlanie dokumentów, granie
  - App Store
  - Jawna zawartość programu iTunes, muzyki, podkastów lub wiadomości
  - Dodawanie znajomych do usługi Game Center
  - Gry dla wielu graczy
- Aplikacje wbudowane
  - Aparat fotograficzny
    - FaceTime
  - Safari
    - Autowypełnianie
- Chmura i magazyn
  - Tworzenie kopii zapasowych w usłudze iCloud
  - Blokuj synchronizację dokumentów usługi iCloud
  - Blokuj synchronizowanie pęku kluczy z usługą iCloud

Jeśli te ustawienia zostały skonfigurowane i przypisane do urządzeń nienadzorowanych przed wydaniem systemu iOS 13,0, ustawienia są nadal stosowane do tych urządzeń nienadzorowanych. Nadal obowiązują również po uaktualnieniu urządzeń do systemu iOS 13,0. Ograniczenia te są usuwane na urządzeniach nienadzorowanych, których kopie zapasowe są tworzone i przywracane. 

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md).

Dotyczy:  
- iOS 13,0 i nowsze

### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709----"></a>Nowe ustawienia i zmiany istniejących ustawień w celu ograniczenia funkcji na urządzeniach z systemem iOS i macOS <!-- 4867699 4867709  -->
Można utworzyć profile, aby ograniczyć ustawienia na urządzeniach z systemem iOS i macOS (**Profile** > **konfiguracji** > urządzeń**Utwórz profil** > **systemu iOS** lub **macOS** dla platformy Wpisz > **ograniczenia dotyczące urządzeń**). Zostaną dodane następujące funkcje:

- W **przypadku** > **ograniczeń** > **dotyczącychurządzeń**z systemem macOS w chmurze i magazynieUżyj **ustawienia nowe przekazaniedo** Zablokuj użytkownikom możliwość rozpoczęcia pracy na jednym urządzeniu macOS i Kontynuuj pracę na innym urządzeniu macOS lub iOS.
  Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-macos.md).
- W przypadku**ograniczeń urządzenia**z **systemem iOS** > istnieje kilka zmian:
  - **Wbudowane aplikacje** > **Znajdź mój iPhone (tylko nadzorowany)** : nowe ustawienie, które blokuje tę funkcję w funkcji Znajdź moją aplikację. 
  - **Wbudowane aplikacje** > **Znajdź moich znajomych (tylko nadzorowany)** : nowe ustawienie, które blokuje tę funkcję w funkcji Znajdź moją aplikację. 
  - **Modyfikacja sieci bezprzewodowej** > **stanu Wi-Fi (tylko tryb nadzorowany)** : nowe ustawienie, które uniemożliwia użytkownikom włączanie lub wyłączanie sieci Wi-Fi na urządzeniu.
  - **Klawiatura i słownik** > **QuickPath (tylko tryb nadzorowany)** : nowe ustawienie, które blokuje funkcję QuickPath.
  - **Chmura i magazyn**: **nazwa** kontynuacji**działania została zmieniona na przekazanie.**

  Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-ios.md).

Dotyczy:  
- macOS 10,15 i nowsze
- System iOS 13 lub nowszy

### <a name="control-the-apps-files-documents-and-folders-that-open-when-user-signs-in-to-macos-devices---3914202----"></a>Kontrolowanie aplikacji, plików, dokumentów i folderów, które są otwierane, gdy użytkownik loguje się do urządzeń macOS <!--3914202  -->
Będziesz mieć możliwość włączania i konfigurowania funkcji na urządzeniach macOS (**Profile** > **konfiguracji** > urządzeń**Tworzenie profilu** > **macOS** dla funkcji platformy > **urządzeń** dla Typ profilu). 

Dostępne są nowe ustawienia elementów logowania, które umożliwiają kontrolowanie, które aplikacje, pliki, dokumenty i foldery są otwierane, gdy użytkownik zaloguje się do zarejestrowanego urządzenia. 

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [macOS device feature settings in Intune](macos-device-features-settings.md) (Ustawienia funkcji urządzeń z systemem macOS w usłudze Intune).

Dotyczy:  
- macOS

### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946----"></a>Nowe funkcje dla dedykowanych urządzeń z systemem Android Enterprise w trybie wielodostępności <!-- 3755304 3041943 3041946  -->
W przypadku urządzeń z systemem Android w wersji Enterprise można kontrolować funkcje i ustawienia w stylu kiosku. W tym celu wybierz kolejno pozycje **Konfiguracja** > urządzenia**Profile** > **Utwórz profil** > system**Android Enterprise** dla platformy > **tylko właściciel urządzenia, ograniczenia dotyczące urządzeń** dla typu profilu.

Zostaną dodane następujące funkcje:
- **Wiele aplikacji** > **dedykowanych**urządzeń :**wirtualnyprzycisk** Strona główna może być pokazywany przez szybkie przesuwanie na urządzeniu lub przepływanie na ekranie, aby użytkownicy mogli je przenieść.
- **Wiele aplikacji** > **dedykowanych**urządzeń :**dostępFlashlightumożliwiaużytkownikom** korzystanie z Flashlight. 
- **Dedykowane urządzenia** >  **— wiele aplikacji**: **sterowanie woluminem multimedialnym** umożliwia użytkownikom kontrolowanie woluminu multimedialnego urządzenia przy użyciu suwaka. 
- **Wiele aplikacji** > **dedykowanych urządzeń: Włącz wygaszacz ekranu, Przekaż obraz niestandardowy i określ, kiedy zostanie wyświetlony wygaszacz ekranu.**

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [Android Enterprise device settings to allow or restrict features using Intune](device-restrictions-android-for-work.md#dedicated-device-settings) (Ustawienia urządzeń z systemem Android Enterprise używane w celu zezwolenia na funkcje lub ich ograniczenia za pomocą usługi Intune).

Dotyczy:  
- Dedykowane urządzenia z rozwiązaniem Android Enterprise

### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215----"></a>Nowe profile aplikacji i konfiguracji dla urządzeń z w pełni zarządzanymi urządzeniami z systemem Android Enterprise <!-- 3574215  -->
Przy użyciu profilów można skonfigurować ustawienia, które stosują ustawienia sieci VPN, poczty e-mail i Wi-Fi w w pełni zarządzanych urządzeniach z systemem Android Enterprise. Będziesz w stanie:
- Użyj profilów aplikacji do wdrożenia ustawień poczty e-mail programu Outlook, usługi Gmail i dziewięciu służbowych.
- Użyj profilów konfiguracji urządzeń do wdrożenia ustawień zaufanych certyfikatów głównych.
- Użyj profilów konfiguracji urządzeń, aby wdrożyć ustawienia sieci VPN i Wi-Fi.

Użytkownicy będą uwierzytelniani przy użyciu nazwy użytkownika i hasła dla profilów sieci VPN, Wi-Fi i poczty e-mail. Obecnie uwierzytelnianie oparte na certyfikatach jest niedostępne. 

Dotyczy:  
- Urządzenia w pełni zarządzane w rozwiązaniu Android Enterprise

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Obsługa profilów sieci VPN protokołu IKEv2 dla systemu iOS <!-- 1943438 -->
Będzie można tworzyć profile sieci VPN dla natywnego klienta sieci VPN systemu iOS za pomocą protokołu IKEv2. Protokół IKEv2 to nowy typ połączenia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **VPN** jako typ profilu > **Ustawienia**.

Te profile sieci VPN konfigurują natywnego klienta sieci VPN. Dlatego żadne aplikacje klienta sieci VPN nie są instalowane ani wypychane do urządzeń zarządzanych. Ta funkcja wymaga zarejestrowania urządzeń w usłudze Intune (rejestracji w oprogramowaniu MDM).

Aby wyświetlić bieżące ustawienia sieci VPN, które możesz skonfigurować, przejdź do tematu [Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).

Dotyczy: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Rejestrowanie urządzeń

### <a name="skip-more-screens-in-setup-assistant---4877451---"></a>Pomiń więcej ekranów w Asystencie ustawień <!--4877451 -->
Można ustawić profile Device Enrollment Program, aby pominąć następujące ekrany Asystenta ustawień: 
- Czas korzystania z urządzenia
- Konfiguracja Touch ID

W tym celu przejdź do pozycji **Rejestrowanie** > urządzenia Rejestracja**Apple** > **tokeny programu rejestracji** > Wybierz > **Profile** , > Wybierz profil > **Właściwości** > **Edytuj** obok pozycji **dostosowanie Asystenta ustawień**.
Aby uzyskać więcej informacji na temat dostosowywania Asystenta ustawień, zobacz [Tworzenie profilu rejestracji firmy Apple ](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

### <a name="android-enrollment-device-administrator-support----4869749----"></a>Obsługa administratora urządzeń rejestracji w systemie Android <!-- 4869749  -->
Opcja rejestracji administratora urządzenia z systemem Android zostanie dodana do strony rejestracji systemu Android (Rejestracja**urządzeń** > z**systemem**Android w**usłudze Intune** > ). Administrator urządzenia z systemem Android będzie nadal domyślnie włączony dla wszystkich dzierżawców.  

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>W przypadku urządzeń z systemem iOS Dostosuj ekran prywatność procesu rejestracji Portal firmy <!-- 4394993  -->
Korzystając z promocji, będziesz mieć możliwość dostosowania ekranu prywatności Portal firmy, który użytkownicy końcowi zobaczą podczas rejestracji systemu iOS. W tym celu można dostosować listę rzeczy, które Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu.

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="build-number-included-on-android-device-hardware-page----4461910----"></a>Numer kompilacji uwzględniony na stronie sprzętowej urządzenia z systemem Android <!-- 4461910  -->
Nowy wpis na stronie sprzęt dla każdego urządzenia z systemem Android będzie zawierać numer kompilacji systemu operacyjnego urządzenia.

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Skonfiguruj automatyczny limit czasu oczyszczania urządzenia do 30 dni <!--4231059  -->
Możesz ustawić automatyczny limit czasu oczyszczania urządzenia jako krótszy niż 30 dni (zamiast bieżącego limitu 90 dni) od momentu ostatniego logowania. Aby to zrobić, przejdź do pozycji**urządzenia** > usługi **Intune** > **Konfiguracja** > **oczyszczania urządzenia reguły**.

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

### <a name="default-scope-tag----3702875---"></a>Domyślny tag zakresu <!-- 3702875 -->
Będzie dostępny nowy wbudowany tag zakresu domyślnego. Wszystkie nieoznakowane obiekty usługi Intune, które obsługują Tagi zakresu, zostaną automatycznie przypisane do domyślnego tagu zakresu. **Domyślny** tag zakresu zostanie dodany do wszystkich istniejących przypisań ról w celu zapewnienia, że w tym miejscu można korzystać z funkcji administratora. Jeśli nie chcesz, aby administrator widział obiekty usługi Intune z domyślnymi znacznikami zakresu, Usuń domyślny tag zakresu z przypisania roli. Ta funkcja jest podobna do funkcji zakresów zabezpieczeń w System Center Configuration Manager.

<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="import-and-export-security-baselines------3408610------------"></a>Importuj i Eksportuj linie bazowe zabezpieczeń    <!--3408610          -->  
Dodawana jest możliwość eksportowania i importowania linii bazowych zabezpieczeń. Ta funkcja umożliwi Ci dostosowanie własnych dostosowań i udostępnienie ich między środowiskami usługi Intune.

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).




