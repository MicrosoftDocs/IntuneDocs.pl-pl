---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titlesuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/08/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: 81e6dba8cabb9339c7c83a3ac95fd7cf7c0a1fa7
ms.sourcegitcommit: 698bd1488be3a269bb88c077eb8d99df6e552a9a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również dowiedzieć się o [nadchodzących zmianach](#whats-coming), [ważnych powiadomieniach](#notices) o usłudze oraz uzyskać informacje o [poprzednich wersjach](whats-new-archive.md). Niektóre funkcje mogą być wprowadzane przez kilka tygodni i nie być dostępne dla wszystkich klientów w pierwszym tygodniu.

> [!Note]
> Aby uzyskać informacje na temat nowych funkcji w ramach hybrydowego zarządzania urządzeniami przenośnymi, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### App management
  ### Device enrollment
  ### Device management
  ### Device configuration
  ### Intune apps
  ### Monitor and troubleshoot
  ### Role-based access control

-->   

## <a name="week-of-may-14-2018"></a>Tydzień od 14 maja 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Wymagana instalacja zasad, aplikacji oraz profilów certyfikatów i sieciowych <!-- 1553555 -->

Administratorzy mogą zablokować dostęp użytkowników końcowych do pulpitu systemu Windows 10 RS4 do momentu zainstalowania zasad, aplikacji oraz profilów certyfikatów i sieciowych przez usługę Intune podczas aprowizowania urządzeń z rozwiązaniem AutoPilot. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Konfigurowanie zasad ochrony aplikacji <!-- 2144597 Part 2 -->

W witrynie Azure Portal zamiast przechodzenia do bloku usługi Intune App Protection możesz teraz po prostu przejść do usługi Intune. Teraz jest tylko jedna lokalizacja zasad ochrony aplikacji w ramach usługi Intune. Zapamiętaj, że wszystkie zasady ochrony aplikacji znajdują się w bloku **Aplikacja mobilna** w usłudze Intune w obszarze **Zasady ochrony aplikacji**. Ta integracja pomaga uprościć administrowanie chmurą. Pamiętaj, że wszystkie zasady ochrony aplikacji są już dostępne w usłudze Intune i możesz modyfikować dowolne wcześniej skonfigurowane zasady. Zasady ochrony aplikacji (APP) i zasady dostępu warunkowego (CA) w usłudze Intune znajdują się teraz w obszarze **Dostęp warunkowy**, który znajduje się w sekcji **Zarządzanie** w bloku **Microsoft Intune** lub w sekcji **Zabezpieczenia** w bloku **Azure Active Directory**. Aby uzyskać więcej informacji na temat modyfikowania zasad dostępu warunkowego, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Aby uzyskać dodatkowe informacje, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>Tydzień od 7 maja 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Pomoc techniczna dotycząca programu Samsung Knox Mobile Enrollment<!--1112863-->

Korzystając z usługi Intune z programem Samsung Knox Mobile Enrollment (KME) można zarejestrować dużą liczbę urządzeń firmowych z systemem Android. Użytkownicy korzystający z sieci komórkowej lub Wi-Fi mogą za pomocą kilku naciśnięć zarejestrować urządzenie przy jego pierwszym włączeniu. Podczas korzystania z aplikacji Knox Deployment urządzenia mogą być rejestrowane za pomocą funkcji Bluetooth lub NFC. Aby uzyskać więcej informacji, zobacz temat [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md) (Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Żądanie pomocy w aplikacji Portal firmy w systemie Windows 10 <!-- 1874137 -->

Gdy użytkownik zainicjuje przepływ pracy w celu uzyskania pomocy dotyczącej problemu, aplikacja Portal firmy w systemie Windows 10 wyśle dzienniki aplikacji bezpośrednio do firmy Microsoft. Ułatwia to rozwiązywanie i usuwanie problemów, które zostały zgłoszone firmie Microsoft.

## <a name="week-of-april-23-2018"></a>Tydzień od 23 kwietnia 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Obsługa kodu dostępu dla numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi w systemie Android<!-- 1438086 -->

Administratorzy usługi Intune mogą określić wymaganie dotyczące uruchamiania aplikacji w celu wymuszenia użycia kodu dostępu zamiast numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi. W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. Usługa Intune obsługuje kod dostępu podobnie jak istniejący liczbowy numer PIN, umożliwiając ustawienie minimalnej długości oraz reguł powtarzania znaków i sekwencji w konsoli administracyjnej. Ta funkcja wymaga najnowszej wersji aplikacji Portal firmy w systemie Android. Ta funkcja jest już dostępna dla systemu iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Obsługa aplikacji biznesowych dla systemu macOS <!-- 1473977 -->
Usługa Microsoft Intune będzie umożliwiać instalowanie aplikacji biznesowych (LOB) dla systemu macOS z witryny Azure Portal. Aplikację LOB dla systemu macOS będzie można dodać do usługi Intune po jej wstępnym przetworzeniu za pomocą narzędzia dostępnego w usłudze GitHub. W witrynie Azure Portal wybierz pozycję **Aplikacje mobilne** w bloku **Intune**. W bloku **Aplikacje mobilne** wybierz pozycje **Aplikacje** > **Dodaj**. W bloku **Dodaj aplikację** wybierz pozycję **Aplikacja biznesowa**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Wbudowane grupy Wszyscy użytkownicy i Wszystkie urządzenia na potrzeby przypisywania aplikacji Android for Work (AFW) <!-- 1813073 -->
Można użyć wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji AFW. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Usługa Intune zainstaluje wymagane aplikacje, które są odinstalowywane przez użytkowników <!-- 1947010 -->
Jeśli użytkownik końcowy odinstaluje wymaganą aplikację, usługa Intune automatycznie ponownie instaluje aplikację w ciągu 24 godzin, nie czekając na zakończenie 7-dniowego cyklu ponownej oceny.

### <a name="device-configuration"></a>Konfiguracja urządzenia

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Wykres profilów urządzeń i lista stanów obejmuje wszystkie urządzenia w grupie <!-- 1449153 eeready -->
Po skonfigurowaniu profilu urządzenia (**Konfiguracja urządzenia** > **Profile**) wybiera się profil urządzenia, taki jak dotyczący systemu iOS. Ten profil jest przypisywane do grupy, która zawiera urządzenia z systemem iOS i inne. Licznik na wykresie graficznym pokazuje, że profil jest stosowany do urządzeń z systemem iOS *i* innych (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Przegląd**). Po wybraniu wykresu graficznego na karcie **Przegląd** na liście **Stan urządzenia** zostaną wyświetlone wszystkie urządzenia w grupie zamiast tylko urządzeń z systemem iOS. 

Dzięki tej aktualizacji wykres graficzny (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Przegląd**) przedstawia tylko liczbę dla konkretnego profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy urządzeń z systemem iOS, wykres zawiera tylko liczbę urządzeń z systemem iOS. Po wybraniu wykresu graficznego i otwarciu pozycji **Stan urządzeń** zostaną wyświetlone tylko urządzenia z systemem iOS.

Podczas wprowadzania tej aktualizacji graficzny wykres użytkowników jest tymczasowo usuwany. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Zawsze włączona sieć VPN w systemie Windows 10 <!--1333666 -->

Obecnie opcji [Zawsze włączone](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) można używać na urządzeniach z systemem Windows 10 za pomocą niestandardowego profilu wirtualnej sieci prywatnej (VPN) utworzonego za pomocą identyfikatora URI OMA.

Dzięki tej aktualizacji administratorzy mogą włączyć ustawienie Zawsze włączone dla profilów sieci VPN systemu Windows 10 bezpośrednio w usłudze Intune za pomocą witryny Azure Portal. Zawsze włączone profile sieci VPN automatycznie nawiążą połączenie, gdy:

- Użytkownik zaloguje się na urządzeniu
- Sieć na urządzeniu zostanie zmieniona
- Ekran na urządzeniu zostanie włączony ponownie po wyłączeniu

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nowe ustawienia drukarek dla profili edukacyjnych <!-- 1308900 -->

W przypadku profilów edukacyjnych są dostępne nowe ustawienia w kategorii **Drukarki**: **Drukarki**, **Drukarka domyślna**, **Dodaj nowe drukarki**.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Pokazywanie identyfikatora rozmówcy w profilu osobistym — Android for Work <!--1098984 -->
Użytkownicy końcowy korzystający z profilu osobistego na urządzeniu mogą nie widzieć identyfikatora rozmówcy dla kontaktu służbowego. 

Ta aktualizacja wprowadza nowe ustawienie w obszarze **Android for Work** > **Ograniczenia dotyczące urządzeń** > **Ustawienia profilu służbowego**:
- Wyświetlanie identyfikatora rozmówcy dla kontaktu służbowego w profilu osobistym

Po włączeniu (bez konfigurowania) szczegóły rozmówcy dla kontaktu służbowego są wyświetlane w profilu osobistym. Po zablokowaniu numer rozmówcy dla kontaktu służbowego nie jest wyświetlany w profilu osobistym. 

Dotyczy: urządzenia z systemem Android w wersji 6.0 i nowszych z profilem służbowym

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Dodano nowe ustawienia funkcji Windows Defender Credential Guard do ustawień programu Endpoint Protection <!--1102252 --><!--from 1802 and 1804-->

Dzięki tej aktualizacji funkcja [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (obszar **Konfiguracja urządzenia** > **Profile** > **Endpoint Protection**) obejmuje następujące ustawienia: 

- **Windows Defender Credential Guard**: służy do włączania funkcji Credential Guard z zabezpieczeniami opartymi na wirtualizacji. Włączenie tej funkcji pomaga chronić poświadczenia przy następnym ponownym uruchomieniu, gdy obydwie opcje: **Poziom zabezpieczeń platformy z funkcją bezpiecznego rozruchu** i **Zabezpieczenia oparte na wirtualizacji** zostały włączone. Dostępne opcje:
  - **Wyłączone**: jeśli funkcja Credential Guard została wcześniej włączona za pomocą opcji **Włączone bez blokady**, ta opcja powoduje zdalne wyłączenie funkcji Credential Guard.

  - **Włączone z blokadą UEFI**: zapewnia, że funkcji Credential Guard nie będzie można wyłączyć za pomocą klucza rejestru ani przy użyciu zasad grupy. Aby wyłączyć funkcję Credential Guard po użyciu tego ustawienia, należy ustawić zasady grupy na „Wyłączone“. Następnie należy usunąć funkcje zabezpieczeń z każdego komputera — wymagana jest fizyczna obecność użytkownika. Te kroki spowodują wyczyszczenie konfiguracji utrwalonej w interfejsie UEFI. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

  - **Włączone bez blokady**: umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 (wersja 1511) lub nowszy.

Następujące technologie zależne są włączane automatycznie podczas konfigurowania funkcji Credential Guard: 

  - **Włącz zabezpieczenia oparte na wirtualizacji (VBS)**: włącza zabezpieczenia oparte na wirtualizacji (VBS) podczas następnego ponownego uruchomienia. Zabezpieczenia oparte na wirtualizacji używają funkcji hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń, i wymagają bezpiecznego rozruchu.
  - **Bezpieczny rozruch z bezpośrednim dostępem do pamięci (DMA)**: włącza zabezpieczenia VBS z funkcją bezpiecznego rozruchu i bezpośrednim dostępem do pamięci. Ochrona DMA wymaga obsługi sprzętowej i można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Użycie niestandardowej nazwy podmiotu w certyfikacie SCEP <!-- 2064190 -->
Istnieje możliwość użycia nazwy pospolitej **OnPremisesSamAccountName** w niestandardowej nazwie podmiotu dla profilu certyfikatu SCEP. Na przykład możesz użyć nazwy `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Blokowanie aparatu i przechwytywania ekranu w aplikacji Android for Work <!-- 1098977 eeready-->
Podczas konfigurowania ograniczeń urządzenia z systemem Android można zablokować dwie nowe właściwości: 
- Aparat: blokuje dostęp do wszystkich aparatów w urządzeniu
- Przechwytywanie ekranu: blokuje przechwytywanie ekranu i wyświetlanie zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo

Dotyczy aplikacji Android for Work.


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nowe kroki rejestracji dla użytkowników na urządzeniach z systemem macOS High Sierra 10.13.2+ <!--1734567 -->
W systemie macOS High Sierra 10.13.2 wprowadzono pojęcie rejestracji w rozwiązaniu MDM „zatwierdzonej przez użytkownika”. Zatwierdzone rejestracje umożliwiają usłudze Intune zarządzanie niektórymi ustawieniami istotnymi dla zabezpieczeń. Aby uzyskać więcej informacji, zobacz dokumentację pomocy technicznej firmy Apple: https://support.apple.com/HT208019.

Urządzenia zarejestrowane przy użyciu aplikacji Portal firmy dla systemu macOS są traktowane jako „niezatwierdzone przez użytkownika”, chyba że użytkownik końcowy otworzy preferencje systemu i ręcznie wykona zatwierdzenie. Dlatego aplikacja Portal firmy dla systemu macOS teraz kieruje użytkowników systemu macOS 10.13.2 i nowszych do kroków ręcznego zatwierdzenia rejestracji pod koniec procesu rejestracji. Konsola administracyjna usługi Intune zgłasza fakt zatwierdzenia zarejestrowanego urządzenia przez użytkownika.



### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>Zaawansowana ochrona przed zagrożeniami (ATP) i usługi Intune są w pełni zintegrowane <!-- EEready 1629303 -->

Funkcja [zaawansowanej ochrony przed zagrożeniami](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) pokazuje poziom ryzyka urządzeń z systemem Windows 10. W usłudze Windows Defender Security Center (portal ATP) można utworzyć połączenie z usługą Microsoft Intune. Po jego utworzeniu zostają użyte zasady zgodności z usługą Intune, aby określić dopuszczalny poziom zagrożenia. Jeśli poziom zagrożenia zostanie przekroczony, zasady dostępu warunkowego usługi Azure Active Directory (AD) mogą zablokować dostęp do różnych aplikacji w ramach danej organizacji.

Ta funkcja pozwala systemowi ATP skanować pliki, wykrywać zagrożenia oraz zgłaszać zdarzenia o podwyższonym ryzyku na urządzeniach z systemem Windows 10.

Zobacz temat [Enable ATP with conditional access in Intune](advanced-threat-protection.md) (Włączanie systemu ATP z dostępem warunkowym w usłudze Intune).

#### <a name="support-for-user-less-devices----1637553---"></a>Obsługa urządzeń bez użytkowników <!-- 1637553 -->
Usługa Intune oferuje możliwość oceny zgodności urządzenia bez użytkowników, takiego jak Microsoft Surface Hub. Zasady zgodności mogą stosować się do konkretnych urządzeń. Dzięki temu zgodność (i niezgodność) można określić dla urządzeń, które nie mają skojarzonego użytkownika.

#### <a name="delete-autopilot-devices----1713650---"></a>Usuwanie urządzeń z rozwiązaniem AutoPilot <!-- 1713650 -->
Administratorzy usługi Intune mogą [usuwać urządzenia z rozwiązaniem AutoPilot](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Ulepszona funkcja usuwania urządzeń <!--1832333 -->
Nie trzeba już wymagać usunięcia danych firmy ani resetować do ustawień fabrycznych przed [usunięciem urządzenia z usługi Intune](devices-wipe.md#delete-devices-from-the-intune-portal).

Aby zobaczyć nową funkcję, zaloguj się do usługi Intune i wybierz pozycje **Urządzenia** > **Wszystkie urządzenia** > nazwa urządzenia > **Usuń**.

Jeśli chcesz nadal otrzymywać powiadomienia o wyczyszczeniu lub wycofaniu, możesz użyć standardowego cyklu życia urządzenia, uruchamiając polecenie **Usuń dane firmy** oraz **Resetuj do ustawień fabrycznych**, a następnie polecenie **Usuń**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Odtwarzanie dźwięków w systemie iOS w trybie utraty <!-- 1947769 -->
Jeśli urządzenia z systemem iOS nadzorowane w rozwiązaniu do zarządzania urządzeniami przenośnymi są w [trybie utraty](device-lost-mode.md), możesz [odtwarzać dźwięk](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie z systemem iOS > **Przegląd** > **Więcej**). Dźwięk będzie odtwarzany w sposób ciągły aż do zakończenia trybu utraty na urządzeniu lub wyłączenia przez użytkownika dźwięku na urządzeniu. Dotyczy urządzeń z systemem iOS 9.3 lub nowszym.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Blokowanie wyników internetowych w wyszukiwaniach przeprowadzanych na urządzeniu usługi Intune lub zezwalanie na te wyniki <!--1972804-->

Administratorzy mogą teraz blokować internetowe wyniki wyszukiwań przeprowadzanych na urządzeniu.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Ulepszona obsługa komunikatów o błędach przekazywania certyfikatu wypychanego przez rozwiązanie MDM firmy Apple <!-- 2172331 -->

Komunikat o błędzie zawiera wyjaśnienie mówiące o tym, że podczas odnawiania istniejącego certyfikatu rozwiązania MDM należy użyć tego samego identyfikatora Apple ID.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testowanie Portalu firmy dla systemu macOS na maszynach wirtualnych <!-- 2216679 -->

Opublikowaliśmy wskazówki ułatwiające administratorom IT testowanie aplikacji Portal firmy dla systemu macOS na maszynach wirtualnych z programami Parallels Desktop i VMware Fusion. Dalsze informacje znajdują się w sekcji [Rejestrowanie maszyn wirtualnych z systemem macOS na potrzeby testowania](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### <a name="user-interface"></a>Interfejs użytkownika

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Ulepszone kafelki urządzenia w aplikacji Portal firmy dla systemu Windows 10 <!--2213364 -->

Kafelki zostały zaktualizowane pod kątem zwiększenia dostępności dla użytkowników z ograniczonymi możliwościami widzenia oraz poprawienia sposobu współdziałania z narzędziami do odczytywania ekranu.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Wysyłanie raportów diagnostycznych z aplikacji Portal firmy dla systemu macOS <!-- 2216677 -->
Aplikacja Portal firmy dla urządzeń z systemem macOS została zaktualizowana pod kątem ulepszenia sposobu raportowania błędów dotyczących usługi Intune przez użytkowników. W aplikacji Portal firmy pracownicy mogą:

- Przekazywać raporty diagnostyczne bezpośrednio do zespołu deweloperów firmy Microsoft.
- Wysłać wiadomość e-mail z identyfikatorem zdarzenia do zespołu pomocy technicznej IT firmy.

Aby uzyskać więcej informacji, zobacz [Wysyłanie błędów w przypadku systemu macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Usługa Intune dostosowuje się do systemu Fluent Design System w aplikacji Portal firmy dla systemu Windows 10 <!-- 1195010 WNready -->
Aplikacja Portal firmy usługi Intune dla systemu Windows 10 została zaktualizowana w celu dodania [widoku nawigacji systemu Fluent Design System](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Wzdłuż boku aplikacji znajduje się statyczna, pionowa lista wszystkich stron najwyższego poziomu. Kliknij dowolny link, aby szybko wyświetlać strony i przełączać się między nimi. Jest to pierwsza z kilku aktualizacji, które będą wprowadzane w ramach naszych ciągłych wysiłków mających na celu stworzenie bardziej adaptacyjnego, empatycznego, znanego środowiska pracy w usłudze Intune. Aby wyświetlić zaktualizowany wygląd, przejdź do obszaru [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Tydzień od 16 kwietnia 2018 r.

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Korzystanie z klienta Cisco AnyConnect dla systemu iOS <!-- EEready 1333708 -->

W przypadku tworzenia nowego profilu sieci VPN dla systemu iOS są teraz dostępne dwie opcje: **Cisco AnyConnect** i **Cisco Legacy AnyConnect**. Profile Cisco AnyConnect obsługują wersję 4.0.7x i nowsze. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x oraz jego starszymi wersjami, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS. W przypadku platform systemów Android i macOS oraz programu Android for Work nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Urządzenia z systemem macOS zarejestrowane w oprogramowaniu Jamf można obecnie zarejestrować w usłudze Intune <!-- 2370684 -->

W wersjach 1.3 i 1.4 portalu firmy systemu macOS nie można było pomyślnie rejestrować urządzeń z oprogramowaniem Jamf w usłudze Intune. W wersji 1.4.2 portalu macOS rozwiązano ten problem.


## <a name="week-of-april-9-2018"></a>Tydzień od 9 kwietnia 2018 r.

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Zaktualizowane środowisko pomocy w aplikacji Portal firmy dla systemu Android <!-- 1631531 -->

Zaktualizowaliśmy środowisko pomocy w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla platformy Android. Teraz, gdy użytkownik napotka problem w aplikacji, może nacisnąć pozycję **Menu** > **Pomoc**, a następnie:
- Przekazać dzienniki diagnostyczne do firmy Microsoft.
- Wysłać wiadomość e-mail z opisem problemu i identyfikatorem zdarzenia do osoby odpowiedzialnej za pomoc techniczną w firmie.  

Aby sprawdzić zaktualizowane środowisko pomocy, przejdź do obszaru [Wysyłanie dzienników pocztą e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android) i [Wysyłanie błędów do firmy Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nowy wykres trendu niepowodzeń rejestracji i tabela z przyczynami niepowodzeń <!-- 1471783 -->

Na stronie Przeglądu rejestracji można wyświetlić trend niepowodzeń rejestracji i pięć najczęstszych przyczyn niepowodzeń. Klikając wykres lub tabelę, można przejść do szczegółów, aby znaleźć porady dotyczące rozwiązywania problemów i sugestie dotyczące korygowania.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Aktualizowanie miejsca konfigurowania zasad ochrony aplikacji <!-- 2144597 -->

W witrynie Azure Portal w ramach usługi Microsoft Intune zostanie włączone tymczasowe przekierowanie z bloku usługi **Intune App Protection** do bloku **Aplikacja mobilna**. Uwaga: wszystkie zasady ochrony aplikacji znajdują się już w bloku **Aplikacja mobilna** w usłudze Intune w obszarze konfiguracji aplikacji. Zamiast przechodzić do usługi Intune App Protection, należy przejść do usługi Intune. W kwietniu 2018 r. zatrzymamy to przekierowywanie i całkowicie usuniemy blok usługi **Intune App Protection**, więc będzie istnieć tylko jedna lokalizacja z zasadami ochrony aplikacji w usłudze Intune. 

**Jak to wpłynie na mnie?**
Ta zmiana wpłynie zarówno na klientów z autonomiczną usługą Intune, jak i na klientów ze środowiskami hybrydowymi (usługą Intune z programem Configuration Manager). Ta integracja pomoże uprościć administrowanie chmurą.

**Co należy zrobić, aby przygotować się do tej zmiany?**
Otaguj usługę **Intune** jako ulubioną zamiast bloku usługi **Intune App Protection** i zapoznaj się z przepływem pracy zasad ochrony aplikacji w bloku **Aplikacja mobilna** w usłudze Intune. Przez krótki okres będzie działać przekierowanie, a następnie blok **App Protection** zostanie usunięty. Pamiętaj, że wszystkie zasady ochrony aplikacji są już dostępne w usłudze Intune i możesz modyfikować dowolne zasady dostępu warunkowego. Aby uzyskać więcej informacji na temat modyfikowania zasad dostępu warunkowego, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Aby uzyskać dodatkowe informacje, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>Tydzień od 2 kwietnia 2018 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Aktualizacja środowiska użytkownika aplikacji Portal firmy dla systemu iOS <!--1412866 -->
Wydaliśmy dużą aktualizację środowiska użytkownika w aplikacji Portal firmy dla systemu iOS. Aktualizacja obejmuje całkiem nowy projekt wizualny, który zapewnia zmodernizowany wygląd i działanie. Zachowaliśmy funkcjonalność aplikacji, ale zwiększyliśmy jej użyteczność i dostępność.  

Ponadto wprowadziliśmy następujące zmiany:
- Obsługa urządzenia iPhone X.
- Szybsze uruchamianie aplikacji i ładowanie, co oszczędza czas użytkowników.
- Dodatkowe paski postępu zapewniające użytkownikom najbardziej aktualne informacje o stanie.
- Ulepszenia sposobu przekazywania dzienników przez użytkowników — jeśli coś pójdzie nie tak, będzie łatwiej to zgłosić.  

Aby wyświetlić zaktualizowany wygląd, przejdź do obszaru [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

#### <a name="protect-on-premise-exchange-data-using-intune-app-and-ca----1056954---"></a>Ochrona lokalnych danych programu Exchange przy użyciu rozwiązania App Policy Protection usługi Intune i funkcji dostępu warunkowego <!-- 1056954 -->
Teraz możesz użyć rozwiązania App Policy Protection i funkcji dostępu warunkowego usługi Intune w celu ochrony dostępu do lokalnych danych programu Exchange za pomocą programu Outlook Mobile. Aby dodać lub zmodyfikować zasady ochrony aplikacji w witrynie Azure Portal, wybierz pozycję **Microsoft Intune** > **Aplikacje mobilne** > **Zasady ochrony aplikacji**. Przed użyciem tej funkcji upewnij się, że spełnione są [Wymagania dotyczące programu Outlook dla systemów iOS i Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="week-of-march-26-2018"></a>Tydzień od 26 marca 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Alerty dotyczące wygasających aplikacji biznesowych (LOB) dla systemu iOS dla usługi Microsoft Intune <!-- 748789 -->

W witrynie Azure Portal usługa Intune powiadomi Cię o aplikacjach biznesowych dla systemu iOS, które wkrótce wygasną. Po przekazaniu nowej wersji aplikacji biznesowej dla systemu iOS usługa Intune usunie powiadomienie o wygaśnięciu z listy aplikacji. Powiadomienie o wygaśnięciu będzie aktywne tylko dla nowo przekazanych aplikacji biznesowych dla systemu iOS. Ostrzeżenie zostanie wyświetlone 30 dni przed wygaśnięciem profilu aprowizacji aplikacji biznesowych dla systemu iOS. Po jego wygaśnięciu stan alertu zostanie zmieniony na Wygasł.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Dostosowywanie motywów aplikacji Portal firmy za pomocą kodów szesnastkowych <!--1049561 -->

Kolor motywów w aplikacjach Portal firmy można dostosować przy użyciu kodów szesnastkowych. Po wprowadzeniu kodu szesnastkowego usługa Intune określa kolor tekstu, który zapewni najwyższy poziom kontrastu między tekstem a tłem. Podgląd koloru tekstu i logo firmy na tle wybranego koloru możesz wyświetlić, wybierając pozycję **Aplikacje mobilne** > **Portal firmy**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup dla programu Android Enterprise <!-- 1813081 -->

System Android Enterprise (wcześniej znany jako Android for Work) obsługuje dołączanie i wykluczanie grup, ale nie obsługuje wstępnie utworzonych grup wbudowanych **Wszyscy użytkownicy** i **Wszystkie urządzenia**. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Nowe usprawnienia zabezpieczeń w usłudze Intune <!-- 1637539 -->   

Wprowadziliśmy przełącznik w usłudze Intune na platformie Azure, którego klienci autonomicznej usługi Intune mogą użyć w celu traktowania urządzeń bez żadnych przypisanych zasad jako **zgodne** (wyłączona funkcja zabezpieczeń) lub **niezgodne** (włączona funkcja zabezpieczeń). W ten sposób dostęp do zasobów będzie możliwy dopiero po ocenie zgodności urządzenia.

Wpływ tej funkcji na klientów będzie zależeć od tego, czy zostały już przypisane zasady zgodności, czy nie.

- W przypadku nowych oraz istniejących kont i braku przypisanych do urządzeń zasad zgodności, przełącznik zostanie automatycznie ustawiony w na wartość **Zgodne**. Ta funkcja jest domyślnie wyłączona w konsoli. Nie wpływa to w żaden sposób na użytkowników końcowych.
- W przypadku istniejących kont i posiadania jakichkolwiek urządzeń z przypisanymi do nich zasad zgodności, przełącznik zostanie automatycznie ustawiony na wartość **Niezgodne**. Wraz z wprowadzeniem aktualizacji z marca ta funkcja jest domyślnie włączona.

W przypadku używania zasad zgodności z dostępem warunkowym i włączenia tej funkcji wszystkie urządzenia, które nie mają przypisanych jakichkolwiek zasad zgodności, zostaną zablokowane przez funkcję dostępu warunkowego. Skojarzeni z tymi urządzeniami użytkownicy końcowi, którzy wcześniej mieli dostęp do poczty e-mail, utracą ten dostęp, chyba że do wszystkich urządzeń zostaną przypisane jakiekolwiek zasady zgodności.   

Pamiętaj, że chociaż domyślny stan przełącznika jest wyświetlany w interfejsie użytkownika od razu po wprowadzeniu aktualizacji usługi Intune z marca, stan tego przełącznika nie jest od razu wymuszany. Wszelkie zmiany dotyczące tego przełącznika nie będą miały wpływu na zgodność urządzenia do momentu wprowadzenia pakietu testowego na koncie z działającym przełącznikiem. Poinformujemy Cię za pośrednictwem Centrum wiadomości o zakończeniu wprowadzania pakietu testowego na koncie. Może to potrwać kilka dni po zaktualizowaniu usługi Intune w marcu.

**Dodatkowe informacje**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Ulepszone wykrywanie zdjęcia zabezpieczeń systemu <!-- 846515 -->

Ulepszone wykrywanie zdjęcia zabezpieczeń systemu jest nowym ustawieniem zgodności, które usprawnia sposób, w jaki usługa Intune ocenia urządzenia ze zdjętymi zabezpieczeniami systemu. To ustawienie powoduje częstsze ewidencjonowanie urządzenia w usłudze Intune z wykorzystaniem usług lokalizacyjnych urządzenia, co ma wpływ na użycie baterii.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetowanie haseł dla urządzeń z systemem Android O <!-- 1238299 -->
Możliwe będzie resetowanie haseł zarejestrowanych urządzeń z systemem Android 8.0 z profilami służbowymi. Po wysłaniu żądania „Resetuj hasło” do urządzenia z systemem Android 8.0 ustawi ono nowe hasło odblokowania urządzenia lub test zarządzanego profilu dla bieżącego użytkownika. Hasło lub test jest wysyłany i zaczyna obowiązywać natychmiast.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Określanie zasad zgodności dla urządzeń w grupach urządzeń<!--1307012 -->

Możesz określać zasady zgodności dla użytkowników w grupach użytkowników. Ta aktualizacja wprowadza również możliwość określania zasad zgodności dla urządzeń w grupach urządzeń. Urządzenia określone jako część grupy urządzeń nie będą otrzymywać żadnych akcji dotyczących zgodności.

#### <a name="new-management-name-column----1333586---"></a>Nowa kolumna Nazwa zarządzania <!-- 1333586 -->
 W bloku urządzeń dostępna jest nowa kolumna **Nazwa zarządzania**. Jest to generowana automatycznie, nieedytowalna nazwa przypisywana każdemu urządzeniu na podstawnie następującego wzoru:
- Nazwa domyślna dla wszystkich urządzeń: <username><em><devicetype></em><enrollmenttimestamp>
- W przypadku urządzeń dodanych zbiorczo: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Jest to opcjonalna kolumna w bloku urządzeń. Domyślnie jest ona niedostępna i można do niej uzyskać dostęp tylko przy użyciu selektora kolumn. Ta nowa kolumna nie ma wpływu na nazwę urządzenia.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>W przypadku urządzeń z systemem iOS co 15 minut jest wyświetlany monit o ustawienie numeru PIN <!--1550837 -->
Po zastosowaniu zasad zgodności lub konfiguracji względem urządzenia z systemem iOS użytkownikom będzie wyświetlany co 15 minut monit o ustawienie numeru PIN. Monity będą wyświetlane, dopóki numer PIN nie zostanie ustawiony.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Planowanie aktualizacji automatycznych <!--1805514 -->
Usługa Intune zapewnia kontrolę nad instalowaniem aktualizacji automatycznych za pomocą [ustawień pierścienia aktualizacji systemu Windows](windows-update-for-business-configure.md). Ta aktualizacja wprowadza możliwość zaplanowania cyklicznych aktualizacji, w tym tygodnia, dnia i godziny.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Użyj pełnej nazwy wyróżniającej jako podmiotu dla certyfikatu protokołu SCEP <!--2221763 -->
Podczas tworzenia profilu certyfikatu SCEP należy wprowadzić nazwę podmiotu. Ta aktualizacja wprowadza możliwość używania pełnej nazwy wyróżniającej jako tematu. W obszarze **Nazwa podmiotu** wybierz pozycję **Niestandardowa** i wprowadź wartość `CN={{OnPrem_Distinguished_Name}}`. Aby użyć zmiennej `{{OnPrem_Distinguished_Name}}`, zsynchronizuj atrybut użytkownika `onpremisesdistingishedname` z usługą Azure AD za pomocą narzędzia [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Włączanie funkcji udostępniania kontaktów przy użyciu połączenia Bluetooth — Android for Work <!--1098983 -->
Domyślnie system Android uniemożliwia synchronizowanie kontaktów z profilu służbowego z urządzeniami Bluetooth. W związku z tym kontakty profilu służbowego nie są wyświetlane w identyfikatorze dzwoniącego w przypadku urządzeń Bluetooth.

Ta aktualizacja wprowadza nowe ustawienie w obszarze **Android for Work** > **Ograniczenia dotyczące urządzeń** > **Ustawienia profilu służbowego**:
- Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth

Administrator usługi Intune może skonfigurować te ustawienia, aby włączyć udostępnianie. Jest to przydatne podczas parowania urządzenia z samochodowym urządzeniem Bluetooth, które w sposób bezobsługowy wyświetla identyfikator dzwoniącego. Po włączeniu tej funkcji kontakty profilu służbowego są wyświetlane. Jeśli funkcja nie zostanie włączona, kontakty profilu służbowego nie będą wyświetlane.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Konfigurowanie programu Gatekeeper w celu kontrolowania źródła pobierania aplikacji systemu macOS <!-- 1690459 -->

Możliwe jest skonfigurowanie programu Gatekeeper do ochrony urządzeń przed aplikacjami przez kontrolowanie lokalizacji, z których można pobierać aplikacje. Można skonfigurować następujące źródła pobierania: **Sklep Mac App Store**, **Sklep Mac App Store i zidentyfikowani deweloperzy** lub **Dowolne**. Ponadto możliwe jest skonfigurowanie, czy użytkownicy mogą instalować aplikacje, przytrzymując klawisz Control i klikając przyciskiem myszy, aby przesłonić kontrolki programu Gatekeeper.

Te ustawienia można znaleźć w obszarze **Konfiguracja urządzenia** -> **Utwórz profil** -> **macOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurowanie zapory aplikacji dla komputerów Mac <!-- 1690461 -->

Możesz konfigurować zaporę aplikacji dla komputerów Mac. Dzięki temu można kontrolować połączenia dla poszczególnych aplikacji, a nie dla poszczególnych portów. Ułatwia to uzyskanie korzyści z ochrony zapewnianej przez zaporę oraz ułatwia uniemożliwianie niepożądanym aplikacjom przejmowania kontroli na portami sieciowymi otwartymi dla wiarygodnych aplikacji.

Tę funkcję można znaleźć w obszarze **Konfiguracja urządzenia** -> **Utwórz profil** -> **macOS** -> **Endpoint Protection**.

Po włączeniu ustawienia Zapora możesz skonfigurować zaporę przy pomocy dwóch strategii:

- Blokowanie wszystkich połączeń przychodzących

   Możesz zablokować wszystkie połączenia przychodzące dla urządzeń docelowych. Jeśli postanowisz to zrobić, połączenia przychodzące zostaną zablokowane dla wszystkich aplikacji.

- Zezwalanie na określone aplikacje lub ich blokowanie

   Możesz zezwalać określonym aplikacjom na odbieranie połączeń przychodzących lub blokować im tę możliwość. Możesz także włączyć tryb niewidzialności, aby uniemożliwić wysyłanie odpowiedzi na żądania sondowania.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Szczegółowe kody błędów i komunikaty <!-- 1376342 -->

W konfiguracji urządzenia są widoczne bardziej szczegółowe kody błędów i komunikaty o błędach. Dzięki ulepszonemu raportowaniu można zobaczyć ustawienia, stan tych ustawień oraz szczegóły dotyczące rozwiązywania problemów.

##### <a name="more-information"></a>Więcej informacji

- Blokowanie wszystkich połączeń przychodzących

   Uniemożliwia to wszystkim usługom udostępniania (takim jak Udostępnianie plików czy Udostępnianie ekranu) odbieranie połączeń przychodzących. Usługi systemu, które nadal mogą odbierać połączenia przychodzące, to:
  - configd — implementuje protokół DHCP oraz inne usługi konfiguracji sieci
  - mDNSResponder — implementuje usługę Bonjour
  - racoon — implementuje protokołu IPSec

    Aby móc korzystać z usług udostępniania, upewnij się, że ustawienie **Połączenia przychodzące** ma wartość **Nie skonfigurowano** (a nie **Zablokowane**).

- Tryb niewidzialności

   Włącz tę opcję, aby zapobiec odpowiadaniu przez komputer na żądania sondowania. Komputer nadal odpowiada na żądania przychodzące dla autoryzowanych aplikacji. Nieoczekiwane żądania, takie jak ICMP (ping), są ignorowane.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Wyłączenie testów po ponownym uruchomieniu urządzenia <!--1805490 -->
Usługa Intune zapewnia kontrolę nad [zarządzaniem aktualizacjami oprogramowania]](windows-update-for-business-configure.md). Ta aktualizacja udostępnia właściwość <strong>Testy po ponownym uruchomieniu</strong>, która jest domyślnie włączona. Aby pominąć typowe testy przeprowadzane po ponownym uruchomieniu urządzenia (takie jak aktywni użytkownicy, poziom naładowania baterii itp.), wybierz pozycję <strong>Pomiń</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nowe kanały systemu Windows 10 Insider Preview dostępne dla pierścieni wdrażania <!-- 1746293 -->
Masz teraz możliwość wybrania następujących kanałów obsługi systemu Windows 10 Insider Preview podczas tworzenia pierścienia wdrażania systemu Windows 10:
- Kompilacja Windows Insider &#8208; wersja szybka
- Kompilacja Windows Insider &#8208; wersja wolna
- Wydanie kompilacji Windows Insider 

Aby uzyskać więcej informacji o tych kanałach, zobacz [Manage Insider Preview Builds](https://insider.windows.com/en-us/for-business-organization-admin/) (Zarządzanie kompilacjami Insider Preview).   
Aby uzyskać więcej informacji na temat tworzenia kanałów wdrażania w usłudze Intune, zobacz [Zarządzanie aktualizacjami oprogramowania w usłudze Intune](windows-update-for-business-configure.md).

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Ulepszona rejestracja za pomocą aplikacji Portal firmy <!-- 1874230 eeready-->
Użytkownicy rejestrujący urządzenia za pomocą aplikacji Portal firmy w systemie Windows 10 (kompilacja 1703 i nowsza) mogą teraz wykonać pierwszy krok rejestracji bez wychodzenia z aplikacji.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>Urządzenia HoloLens i Surface Hub są teraz wyświetlane na liście urządzeń <!--1725868 -->
Dodaliśmy obsługę wyświetlania urządzeń HoloLens i Surface Hub zarejestrowanych w usłudze Intune do aplikacji Portal firmy dla systemu Android.

#### <a name="custom-book-categories-for-volume-purchase-progream-vpp-ebooks----1488911---"></a>Niestandardowe kategorie książek dla książek elektronicznych programu zakupów zbiorczych (VPP) <!-- 1488911 -->
Możliwe jest tworzenie niestandardowych kategorii książek elektronicznych, a następnie przypisywanie do tych kategorii książek elektronicznych programu VPP. Użytkownicy końcowi będą mogli wtedy wyświetlać nowo utworzone kategorie książek elektronicznych oraz książki przypisane do tych kategorii. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami i książkami kupionymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Zmiana obsługi opcji wysyłania opinii w aplikacji Portal firmy dla systemu Windows <!-- 2070166 -->
Od dnia 30 kwietnia 2018 r. opcja **Prześlij opinię** w aplikacji Portal firmy dla systemu Windows działa tylko na urządzeniach z wersją Rocznicowa aktualizacja systemu Windows 10 (1607) lub nowszą. Opcja wysyłania opinii nie jest już obsługiwana podczas korzystania z aplikacji Portal firmy dla systemu Windows w przypadku systemu:  
- Windows 10, wersja 1507  
- Windows 10, wersja 1511  
- Windows Phone 8,1 

Jeśli na Twoim urządzeniu jest uruchomiony system Windows 10 RS1 lub nowszy, pobierz najnowszą wersję aplikacji Portal firmy systemu Windows dostępną w sklepie Store. Jeśli używasz nieobsługiwanej wersji, przekaż opinię za pośrednictwem następujących kanałów: 
- Aplikacja Centrum opinii w systemie Windows 10
- Wiadomość e-mail na adres WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nowe ustawienia funkcji Windows Defender Application Guard <!-- 1631890 -->

- **Włącz przyspieszanie grafiki**: administratorzy mogą włączyć wirtualny procesor graficzny dla funkcji Windows Defender Application Guard. To ustawienie umożliwia procesorowi CPU przekazanie renderowania grafiki do procesora vGPU. Może to poprawić wydajność podczas pracy z witrynami internetowymi bogatymi w grafikę lub podczas oglądania filmu wideo znajdującego się w kontenerze.

- **Zapisywanie plików na hoście**: Administratorzy mogą włączyć przekazywanie plików z przeglądarki Microsoft Edge działającej w kontenerze do systemu plików hosta. Włączenie tej opcji pozwala użytkownikom na pobieranie plików z przeglądarki Microsoft Edge w kontenerze do systemu plików hosta.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Zasady ochrony funkcji zarządzania aplikacjami mobilnymi określane na podstawie stanu zarządzania <!-- 1665993 -->
Możliwe jest określanie zasad zarządzania aplikacjami mobilnymi na podstawie stanu zarządzania urządzenia:
- **Urządzenia z systemem Android** — możliwe jest określanie urządzeń niezarządzanych, urządzeń zarządzanych w usłudze Intune oraz zarządzanych w usłudze Intune profilów programu Android Enterprise (znanego wcześniej jako Android for Work).
- **Urządzenia z systemem iOS** — możliwe jest określanie urządzeń niezarządzanych (tylko dla funkcji zarządzania aplikacjami mobilnymi) lub urządzeń zarządzanych w usłudze Intune.

    > [!NOTE]
    > - W kwietniu 2018 wprowadzona zostanie obsługa systemu iOS dla tej funkcji.

Aby uzyskać więcej informacji, zobacz [Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Ulepszenia języka aplikacji w aplikacji Portal firmy dla systemu Windows <!-- 1683758 -->
Poprawiliśmy język w aplikacji Portal firmy dla systemu Windows 10, aby była ona bardziej przyjazna dla użytkownika i właściwa dla Twojej firmy. Aby wyświetlić niektóre przykładowe obrazy przedstawiające wprowadzone aktualizacje, zobacz [Co nowego w aplikacji interfejsu użytkownika](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Nowości w naszej dokumentacji dotyczące ochrony prywatności użytkowników <!-- 1440709 -->
W ramach dążenia do zapewnienia użytkownikom końcowym większej kontroli nad ich danymi i ochroną prywatności zostały opublikowane aktualizacje dotyczące naszej dokumentacji, w których opisano sposób wyświetlania i usuwania danych przechowywanych lokalnie przy użyciu aplikacji Portal firmy. Te aktualizacje można znaleźć w następujących artykułach:

- **Android**: [Jak usunąć urządzenie z systemem Android z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android (jeśli użytkownik odrzucił warunki użytkowania**: [Usuwanie urządzenia z zarządzania w przypadku odrzucenia warunków użytkowania](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Usuwanie urządzenia z systemem iOS z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Usuwanie urządzenia z systemem Windows z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>Tydzień od 19 marca 2018 r.

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Eksportowanie wszystkich urządzeń do plików CSV w przeglądarce IE, Edge lub Chrome <!-- 2258071 -->
W obszarze **Urządzenia** > **Wszystkie urządzenia** możesz **wyeksportować** urządzenia do sformatowanej listy w pliku CSV. Użytkownicy przeglądarki Internet Explorer (IE) posiadający ponad 10 000 urządzeń mogą pomyślnie wyeksportować swoje urządzenia do wielu plików. Każdy plik może zawierać maksymalnie 10 000 urządzeń.

Użytkownicy przeglądarek Edge i Chrome posiadający ponad 30 000 urządzeń mogą pomyślnie wyeksportować swoje urządzenia do wielu plików. Każdy plik może zawierać maksymalnie 30 000 urządzeń.

Funkcja [zarządzania urządzeniami](device-management.md) zawiera bardziej szczegółowe informacje dotyczące działań, które można wykonać względem zarządzanych urządzeń.

## <a name="week-of-march-12-2018"></a>Tydzień od 12 marca 2018 r.

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->

Korzystając z usługi Azure Active Directory (Azure AD), można teraz ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure. Aby uzyskać dodatkowe informacje, zobacz [Access controls in Azure Active Directory conditional access (Elementy kontroli dostępu dla dostępu warunkowego w usłudze Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aktualizacje wizualne aplikacji Portal firmy dla systemu Android <!--976944 -->

Zaktualizowaliśmy aplikację Portal firmy dla systemu Android, aby była zgodna z wytycznymi [Material Design](https://material.io/) systemu Android. Obrazy nowych ikon możesz zobaczyć w artykule [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nowe ustawienia funkcji Windows Defender Exploit Guard <!-- 1631893 -->

Udostępniono sześć nowych ustawień funkcji <strong>Zmniejszenie obszaru ataków</strong> oraz rozszerzono możliwości funkcji <strong>Kontrolowany dostęp do folderów: Ochrona folderów</strong>. Te ustawienia można znaleźć w obszarze: Konfiguracja urządzenia\Profile\
Utwórz profil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków

|Nazwa ustawienia  |Opcje ustawienia  |Opis  |
|---------|---------|---------|
|Zaawansowana ochrona przed oprogramowaniem wymuszającym okup|Włączone, Inspekcja, Nieskonfigurowane|Użyj agresywnej ochrony przed oprogramowaniem wymuszającym okup.|
|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows|Włączone, Inspekcja, Nieskonfigurowane|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe).|
|Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI.|
|Niezaufane i niepodpisane procesy uruchamiane z dysku USB|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB.|
|Pliki wykonywalne, które nie spełniają kryteriów występowania, wieku lub listy zaufanych|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj uruchamianie plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych.|

#### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

|              Nazwa ustawienia               |                                                              Opcje ustawienia                                                              | Opis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrona folderów (już zaimplementowano) | Nieskonfigurowane, Włączone, Tylko inspekcja (już zaimplementowano)<br><br> <strong>Nowe</strong><br>Blokuj modyfikację dysku, Inspekcja modyfikacji dysku |             |

Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.<br><br>**Włącz**: zapobiegaj modyfikowaniu i usuwaniu plików w folderach chronionych oraz zapisywaniu danych w sektorach dysku przez niezaufane aplikacje.<br><br>
**Blokuj tylko modyfikowanie dysku**:<br>Blokuj zapisywanie danych w sektorach dysku przez niezaufane aplikacje. Niezaufane aplikacje nadal mogą modyfikować i usuwać pliki w folderach chronionych.

## <a name="week-of-february-19-2018"></a>Tydzień od 19 lutego 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 -->

Usługa Intune obsługuje teraz rejestrowanie urządzeń z maksymalnie 100 różnymi kontami usług [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) i [Apple School Manager](apple-school-manager-set-up-ios.md). Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Wyświetlanie ograniczeń rejestracji dla poszczególnych użytkowników <!-- 1634444 eeready wnready -->
W bloku **Rozwiązywanie problemów** możesz teraz wyświetlić [ograniczenia rejestracji](enrollment-restrictions-set.md) obowiązujące poszczególnych użytkowników, wybierając pozycję **Ograniczenia rejestracji** z listy **Przypisania**.

### <a name="device-management"></a>Zarządzanie urządzeniami
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Raporty dotyczące stanu zagrożenia i stanu kondycji programu Windows Defender <!--854704 -->

Zrozumienie stanu i kondycji programu Windows Defender ma kluczowe znaczenie w zarządzaniu komputerami z systemem Windows.  Dzięki tej aktualizacji usługa Intune dodaje nowe raporty i akcje do stanu i kondycji agenta programu Windows Defender. Za pomocą zbiorczego raportu stanu w [obciążeniu Zgodność urządzenia](compliance-policy-monitor.md) można wyświetlić urządzenia, dla których trzeba wykonać jedną z następujących czynności:
- Aktualizacja sygnatur
- Uruchom ponownie
- Ręczna interwencja
- Pełne skanowanie
- Inne stany agentów, które wymagają interwencji

Raport szczegółowy dla każdej kategorii stanu zawiera listę poszczególnych komputerów osobistych, które wymagają uwagi, lub takich, których stan jest zgłaszany jako **Czysty**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nowe ustawienia prywatności dla ograniczeń urządzenia <!--1308926 -->
Dla urządzeń dostępne są teraz [dwa nowe ustawienia prywatności](device-restrictions-windows-10.md#privacy):
- **Publikuj działania użytkownika**: ustaw tę pozycję na wartość **Blokuj**, aby uniemożliwić udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań.
- **Tylko działania lokalne**: ustaw tę pozycję na wartość **Blokuj**, aby uniemożliwić udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań jedynie na podstawie działań lokalnych.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nowe ustawienia przeglądarki Microsoft Edge <!--1469166 -->
Dla urządzeń z przeglądarką Microsoft Edge są dostępne [dwa nowe ustawienia](device-restrictions-windows-10.md#edge-browser): **Ścieżka do pliku ulubionych** i **Zmiany w ulubionych**.

### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Wyjątki protokołu dla aplikacji <!--1035509 -->

W zasadach transferu danych funkcji zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune można teraz tworzyć wyjątki, aby umożliwiać korzystanie z określonych aplikacji niezarządzanych. Takie aplikacje muszą być uznane za zaufane przez dział IT. Poza utworzonymi wyjątkami transfer danych nadal jest ograniczony do aplikacji, które są zarządzane przez usługę Intune, gdy zasady transferu danych mają ustawienie **Tylko aplikacje zarządzane**. Ograniczenia można tworzyć za pomocą protokołów (system iOS) lub pakietów (system Android).

Na przykład można dodać pakiet Webex jako wyjątek do zasad transferu danych MAM. Pozwoli to na otwieranie linków Webex w wiadomości e-mail zarządzanego programu Outlook bezpośrednio w aplikacji Webex. Transfer danych będzie w dalszym ciągu ograniczony w innych aplikacjach niezarządzanych. Aby uzyskać więcej informacji, zobacz [Wyjątki od zasad przesyłania danych dla aplikacji](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dane zaszyfrowane przy użyciu funkcji Windows Information Protection (WIP) w wynikach wyszukiwania systemu Windows <!-- 1469193 -->
Ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia teraz kontrolowanie, czy dane zaszyfrowane przy użyciu funkcji WIP będą uwzględniane w wynikach wyszukiwania systemu Windows. Ustaw tę opcję zasad ochrony aplikacji, wybierając pozycję **Zezwalaj indeksatorowi programu Microsoft Windows Search na wyszukiwanie zaszyfrowanych elementów** w obszarze **Ustawienia zaawansowane** zasad funkcji Windows Information Protection. Zasady ochrony aplikacji muszą być ustawione na platformę systemu *Windows 10*, a zasady aplikacji **Stan rejestracji** muszą być ustawione na wartość **Z rejestracją**. Aby uzyskać więcej informacji, zobacz [Zezwalanie indeksatorowi programu Microsoft Windows Search na wyszukiwanie zaszyfrowanych elementów](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurowanie mobilnej aplikacji MSI korzystającej z samoaktualizacji <!-- 1740840 -->
Znaną mobilną aplikację MSI, która korzysta z samoaktualizacji, można skonfigurować tak, aby ignorowała proces sprawdzania wersji. Ta możliwość jest przydatna, aby uniknąć sytuacji wyścigu. Sytuacja wyścigu może wystąpić na przykład wtedy, gdy aplikacja jest automatycznie aktualizowana przez dewelopera, a równocześnie jest aktualizowana przez usługę Intune. Obie aktualizacje mogą próbować wymusić na kliencie systemu Windows daną wersję aplikacji, co może powodować konflikt. W przypadku tych automatycznie aktualizowanych aplikacji MSI możesz skonfigurować ustawienie **Ignoruj wersję aplikacji** w bloku **Informacje o aplikacji**. Gdy to ustawienie zostanie przełączone na wartość **Tak**, usługa Microsoft Intune będzie ignorować wersję aplikacji zainstalowanej na kliencie systemu Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Powiązane zestawy licencji aplikacji obsługiwane w usłudze Intune <!-- 1864117 -->
Usługa Intune w witrynie Azure Portal obsługuje teraz powiązane zestawy licencji aplikacji jako jeden element aplikacji w interfejsie użytkownika. Ponadto wszelkie aplikacje licencjonowane w trybie offline synchronizowane ze sklepem Microsoft Store dla Firm zostaną skonsolidowane w jeden wpis aplikacji i wszelkie szczegóły wdrożenia z indywidualnych pakietów zostaną migrowane do tego pojedynczego wpisu. Aby wyświetlić powiązane zestawy licencji aplikacji w witrynie Azure Portal, wybierz pozycję **Licencje aplikacji** w bloku **Aplikacje mobilne**.

### <a name="device-configuration"></a>Konfiguracja urządzenia
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Rozszerzenia plików funkcji Windows Information Protection (WIP) do automatycznego szyfrowania <!-- 1463582 -->
Ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia teraz określenie, które rozszerzenia mają być automatycznie szyfrowane podczas kopiowania danych z udziału bloków komunikatu serwera (SMB) w obrębie firmy, jak określono w zasadach funkcji WIP.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Konfigurowanie ustawień kont zasobów dla urządzeń Surface Hub

Ustawienia kont zasobów dla urządzeń Surface Hub można teraz konfigurować zdalnie.

Konto zasobu jest używane przez urządzenie Surface Hub do uwierzytelniania względem programu Skype/Exchange, co pozwala przyłączyć je do spotkania.
Zaleca się utworzenie unikatowego konta zasobu, aby urządzenie Surface Hub było wyświetlane w ramach spotkania jako sala konferencyjna.
Na przykład konto zasobu takie jak **Sala konferencyjna B41/6233**.

> [!NOTE]
> - Jeśli pozostawisz puste pola, spowoduje to zastąpienie atrybutów skonfigurowanych wcześniej na urządzeniu.
>
> - Właściwości konta zasobu mogą się dynamicznie zmieniać na urządzeniu Surface Hub. Jeśli na przykład rotacja hasła jest włączona. W związku z tym możliwe jest, że minie trochę czasu, zanim wartości w konsoli platformy Azure będą odzwierciedlać rzeczywiste wartości na urządzeniu.
>
>   Aby poznać bieżącą konfigurację na urządzeniu Surface Hub, informacje o koncie zasobu mogą zostać uwzględnione w spisie sprzętu (który jest już wykonywany z 7-dniowym interwałem) lub jako właściwości tylko do odczytu. Aby poprawić dokładność danych po przeprowadzeniu akcji zdalnej, można pobrać stan parametrów natychmiast po wykonaniu akcji w celu zaktualizowania konta/parametrów na urządzeniu Surface Hub.


##### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków


|Nazwa ustawienia  |Opcje ustawienia  |Opis  |
|---------|---------|---------|
|Wykonywanie chronionej hasłem zawartości wykonywalnej z wiadomości e-mail|Blokuj, Inspekcja, Nieskonfigurowane|Nie zezwalaj na uruchamianie chronionych hasłem plików wykonywalnych pobranych z poczty e-mail.|
|Zaawansowana ochrona przed oprogramowaniem wymuszającym okup|Włączone, Inspekcja, Nieskonfigurowane|Użyj agresywnej ochrony przed oprogramowaniem wymuszającym okup.|
|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows|Włączone, Inspekcja, Nieskonfigurowane|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe).|
|Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI.|
|Niezaufane i niepodpisane procesy uruchamiane z dysku USB|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB.|
|Pliki wykonywalne, które nie spełniają kryteriów występowania, wieku lub listy zaufanych|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj uruchamianie plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych.|

##### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

|              Nazwa ustawienia               |                                                              Opcje ustawienia                                                              | Opis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrona folderów (już zaimplementowano) | Nieskonfigurowane, Włączone, Tylko inspekcja (już zaimplementowano)<br><br> <strong>Nowe</strong><br>Blokuj modyfikację dysku, Inspekcja modyfikacji dysku |             |

Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.<br><br>**Włącz**: zapobiegaj modyfikowaniu i usuwaniu plików w folderach chronionych oraz zapisywaniu danych w sektorach dysku przez niezaufane aplikacje.<br><br>
**Blokuj tylko modyfikowanie dysku**:<br>Blokuj zapisywanie danych w sektorach dysku przez niezaufane aplikacje. Niezaufane aplikacje nadal mogą modyfikować i usuwać pliki w folderach chronionych.

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Dodatki do ustawień zabezpieczeń systemu dla zasad zgodności systemu Windows 10 lub nowszego <!--1704133-->

Dostępne są teraz dodatki do ustawień zgodności systemu Windows 10, w tym możliwość wymagania zapory oraz programu antywirusowego Windows Defender.


### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach
### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Obsługa aplikacji offline ze Sklepu Microsoft dla Firm <!--1222672-->
Aplikacje offline zakupione w Sklepie Microsoft dla Firm są teraz synchronizowane z witryną Azure Portal. Można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, nie przez sklep.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Uniemożliwianie użytkownikom końcowym ręcznego dodawania i usuwania kont w profilu służbowym <!-- 1728700 -->

Podczas wdrażania aplikacji usługi Gmail w profilu programu Android for Work można teraz uniemożliwić użytkownikom końcowym ręczne dodawanie i usuwanie kont w profilu służbowym przy użyciu ustawienia **Dodawanie i usuwanie kont** w profilu ograniczeń programu Android for Work.

## <a name="week-of-february-5-2018"></a>Tydzień od 5 lutego 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nowa opcja uwierzytelniania użytkownika na potrzeby rejestracji zbiorczej firmy Apple <!-- 747625 eeready -->

> [!NOTE]
> Dla nowych dzierżawców jest to widoczne od razu. W przypadku istniejących dzierżaw wdrażanie tej funkcji potrwa do końca kwietnia. Do czasu ukończenia tego procesu możesz nie mieć dostępu do tych nowych funkcji.

Usługa Intune zapewnia teraz możliwość uwierzytelniania urządzeń przy użyciu aplikacji Portal firmy dla następujących metod rejestracji:

- Program Device Enrollment Program firmy Apple
- Apple School Manager
- Rejestracja programu Apple Configurator

Korzystając z opcji obejmującej Portal firmy, można wymusić uwierzytelnianie wieloskładnikowe usługi Azure Active Directory bez blokowania tych metod rejestracji.

W przypadku użycia opcji obejmującej Portal firmy usługa Intune pomija uwierzytelnianie użytkownika w Asystencie ustawień systemu iOS w celu rejestracji koligacji użytkownika. Oznacza to, że urządzenie zostaje początkowo zarejestrowane jako urządzenie bez użytkownika, dlatego nie otrzymuje konfiguracji ani zasad dotyczących grup użytkowników. Otrzymuje tylko konfiguracje i zasady dotyczące grup urządzeń. Jednak usługa Intune automatycznie zainstaluje aplikację Portal firmy na urządzeniu. Pierwszy użytkownik, który uruchomi aplikację Portal firmy i zaloguje się w niej, zostanie skojarzony z urządzeniem w usłudze Intune. Użytkownik otrzyma wówczas konfiguracje i zasady dotyczące grup użytkowników. Skojarzenia z użytkownikiem nie można zmienić bez ponownego wykonania rejestracji.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 eeready -->

Usługa Intune obsługuje teraz rejestrowanie urządzeń z maksymalnie 100 różnych kont usług Apple Device Enrollment Program (DEP) i Apple School Manager. Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Drukowanie zdalne za pośrednictwem sieci zabezpieczonej <!-- 1709994  -->
Rozwiązania bezprzewodowego drukowania mobilnego PrinterOn umożliwią użytkownikom drukowanie zdalne z dowolnego miejsca i w dowolnym czasie za pośrednictwem sieci zabezpieczonej. Rozwiązania PrinterOn będą zintegrowane z zestawem Intune APP SDK dla systemów iOS i Android. Możliwe będzie określenie zasad ochrony aplikacji dla danej aplikacji przy użyciu bloku **Zasady ochrony aplikacji** usługi Intune w konsoli administratora. Użytkownicy końcowi będą mogli pobrać aplikację „PrinterOn for Microsoft” za pośrednictwem sklepu Play lub iTunes i używać jej w środowisku usługi Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Obsługa rejestracji, które używają menedżera rejestracji urządzeń, w aplikacji Portal firmy dla systemu macOS <!-- 1352411 -->

Użytkownicy mogą teraz używać menedżera rejestracji urządzeń podczas rejestrowania za pomocą aplikacji Portal firmy dla systemu macOS.

## <a name="week-of-january-29-2018"></a>Tydzień od 29 stycznia 2018 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną<!-- 1639263 -->
Strona przeglądu zawiera teraz alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną. Kliknięcie alertu dotyczącego pojedynczego tokenu spowoduje przejście do strony szczegółów tokenu.  Po kliknięciu alertu dotyczącego wielu tokenów nastąpi przejście do listy wszystkich tokenów z informacjami o ich stanie. Administratorzy powinni odnawiać tokeny przed datą wygaśnięcia.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Zdalna obsługa polecenia wymazywania dla urządzeń z systemem macOS <!-- 1438084 -->

Administratorzy mogą zdalnie wydać polecenie „Erase” („Wymaż”) dla urządzeń z systemem macOS.

> [!IMPORTANT]
> Polecenia wymazywania nie można cofnąć, dlatego należy korzystać z niego z rozwagą.

Polecenie wymazywania powoduje usunięcie wszystkich danych, w tym systemu operacyjnego, z urządzenia. Powoduje również usunięcie urządzenia z zarządzania przy użyciu usługi Intune. Ostrzeżenie dla użytkownika nie jest wyświetlane i wymazywanie następuje natychmiast po wykonaniu polecenia.

Musisz skonfigurować 6-cyfrowy numer PIN odzyskiwania. Za pomocą tego numeru PIN można odblokować wymazane urządzenie, po czym rozpocznie się ponowna instalacja systemu operacyjnego. Po rozpoczęciu operacji wymazywania numer PIN jest wyświetlany na pasku stanu, w bloku przeglądu urządzenia w usłudze Intune. Numer PIN jest widoczny podczas całego procesu wymazywania. Po zakończeniu wymazywania urządzenie całkowicie znika z zarządzania w usłudze Intune. Należy pamiętać, aby zarejestrować numer PIN odzyskiwania, dzięki czemu osoba przywracająca urządzenie będzie mogła go użyć.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odwołanie licencji dla tokenu programu zakupów zbiorczych dla systemu iOS <!-- 820870 -->
Możesz odwołać licencję wszystkich aplikacji dla systemu iOS zakupionych w ramach programu zakupów zbiorczych (VPP) dla danego tokenu programu VPP.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odwołanie aplikacji dla systemu iOS zakupionych w ramach programu zakupów zbiorczych  <!-- 820863 -->
Dla danego urządzenia z zainstalowaną przynajmniej jedną aplikacją dla systemu iOS zakupioną w ramach programu zakupów zbiorczych (Volume-Purchase Program — VPP) możesz odwołać skojarzoną licencję aplikacji urządzenia dla tego urządzenia. Odwołanie licencji aplikacji nie spowoduje odinstalowania powiązanych aplikacji VPP z urządzenia. Aby odinstalować aplikację VPP, należy zmienić akcję przypisywania na **Odinstaluj**. Aby uzyskać więcej informacji, zobacz temat [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Przypisywanie aplikacji mobilnych usługi Office 365 do urządzeń z systemami iOS i Android przy użyciu wbudowanego typu aplikacji <!-- 1332318 -->
**Wbudowany** typ aplikacji ułatwia tworzenie aplikacji usługi Office 365 oraz ich przypisywanie do zarządzanych urządzeń z systemami iOS i Android. Są to na przykład aplikacje usługi 0365, takie jak Word, Excel, PowerPoint i OneDrive. Do typu aplikacji można przypisać określone aplikacje, a następnie zmodyfikować konfigurację informacji o aplikacji.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup <!-- 1406920 -->

Podczas przypisywania aplikacji i po wybraniu typu przypisania możesz wybrać grupy, które mają być dołączone, a także grupy, które mają zostać wykluczone.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Zasady konfiguracji aplikacji możesz przypisywać do grup, dołączając i wykluczając przypisania <!-- 1480316 -->

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników i urządzeń za pomocą kombinacji dołączania i wykluczania przypisań. Przypisania można wybrać jako niestandardowy wybór grup albo jako grupę wirtualną. Grupa wirtualna może obejmować **wszystkich użytkowników**, **wszystkie urządzenia** lub **wszystkich użytkowników i wszystkie urządzenia**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10 <!-- 903672(archived), 1119689 -->  
Możesz tworzyć zasady uaktualniania wersji systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wersji systemu Windows 10, zobacz artykuł [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zasady dostępu warunkowego dla usługi Intune są dostępne tylko w witrynie Azure Portal <!-- 1737088 1634311 -->

Począwszy od tego wydania, musisz konfigurować zasady dostępu warunkowego i zarządzać nimi w witrynie [Azure Portal](https://portal.azure.com) w bloku **Azure Active Directory** > **Dostęp warunkowy**. Dla wygody możesz przejść do tego bloku z usługi Intune w witrynie Azure Portal w obszarze **Intune** > **Dostęp warunkowy**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizacje wiadomości e-mail dotyczących zgodności <!--1637547 -->

Wiadomość e-mail wysłana w celu zgłoszenia niezgodnego urządzenia zawiera szczegóły dotyczące niezgodnego urządzenia.


## <a name="week-of-january-22-2018"></a>Tydzień od 22 stycznia 2018 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nowa funkcja akcji „Rozwiąż” dla urządzeń z systemem Android <!--1583480-->

Aplikacja Portal firmy dla systemu Android rozwija akcję „Rozwiąż” dla pozycji **Zaktualizuj ustawienia urządzenia**, aby rozwiązać [problemy dotyczące szyfrowania urządzenia](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Zdalne blokowanie dostępne w aplikacji Portal firmy dla systemu Windows 10 <!--676506-->
Użytkownicy końcowi mogą teraz zdalnie blokować swoje urządzenia w aplikacji Portal firmy dla systemu Windows 10. Opcja nie będzie wyświetlana dla wybranego urządzenia lokalnego, którego aktywnie używają.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Łatwiejsze rozwiązywanie problemów ze zgodnością aplikacji Portal firmy dla systemu Windows 10<!--676546-->
Użytkownicy końcowi mający urządzenia z systemem Windows będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem.

## <a name="week-of-december-11-2017"></a>Tydzień 11 grudnia 2017 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nowe ustawienie automatycznego ponownego wdrażania<!-- 1469168 -->
Ustawienie **Automatyczne ponowne wdrażanie** pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania. To ustawienie można znaleźć w obszarze Windows 10 > Ograniczenia dotyczące urządzeń > Ogólne > Automatyczne ponowne wdrażanie. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 w usłudze Intune](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Obsługa dodatkowych wersji źródła w zasadach uaktualniania wersji systemu Windows 10 <!-- 903672,  1119689 -->
Zasady uaktualniania wersji systemu Windows 10 umożliwiają teraz uaktualnianie dodatkowych wersji systemu Windows 10 (Windows 10 Pro, Windows 10 Pro for Education, Windows 10 Cloud itp.). Przed tą wersją obsługiwane ścieżki uaktualniania wersji były bardziej ograniczone. Więcej szczegółów znajduje się w temacie [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nowe ustawienia profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center (WDSC)<!-- 1335507 -->

Usługa Intune została wzbogacona o nową sekcję ustawień profilu konfiguracji urządzenia w obszarze Ochrona punktu końcowego o nazwie **Windows Defender Security Center**. Administratorzy IT mogą skonfigurować, do których filarów aplikacji Windows Defender Security Center użytkownicy końcowi mogą uzyskać dostęp. Jeśli administrator IT ukrywa filar w aplikacji Windows Defender Security Center, wszystkie powiadomienia powiązane z ukrytym filarem nie będą wyświetlane na urządzeniu użytkownika.

Poniżej wymieniono filary, które administratorzy mogą ukryć w ustawieniach profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center:
- Ochrona przed wirusami i zagrożeniami
- Wydajność i kondycja urządzenia
- Zapora i ochrona sieci
- Kontrola aplikacji i przeglądarki
- Opcje rodziny

Administratorzy IT mogą również dostosować to, które powiadomienia będą otrzymywać użytkownicy. Na przykład można określić, czy użytkownicy będą otrzymywać wszystkie powiadomienia generowane w ramach widocznych filarów w aplikacji WDSC, czy tylko powiadomienia krytyczne. Powiadomienia niekrytyczne obejmują okresowe podsumowania działania programu antywirusowego Windows Defender i powiadomienia po zakończeniu skanowania. Wszystkie pozostałe powiadomienia są traktowane jako krytyczne. Ponadto można również dostosować zawartość powiadomień, na przykład można podać informacje kontaktowe do działu IT do osadzenia w powiadomieniach wyświetlanych na rządzeniach użytkowników.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Obsługa wielu łączników na potrzeby obsługi certyfikatów protokołu SCEP i PFX <!-- 1361755 -->

Klienci, którzy korzystają z lokalnego łącznika usługi NDES w celu dostarczania certyfikatów do urządzeń, mogą teraz skonfigurować wiele łączników w jednej dzierżawie.

Ta nowa możliwość obsługuje następujący scenariusz:

- **Wysoka dostępność**

Każdy łącznik usługi NDES ściąga żądania certyfikatu z usługi Intune.  Jeśli jeden łącznik usługi NDES przejdzie do trybu offline, inny łącznik może dalej przetwarzać żądania.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Nazwa podmiotu klienta może zawierać zmienną AAD_DEVICE_ID <!-- 1468599 -->

Tworząc profil certyfikatu SCEP w usłudze Intune, można teraz użyć zmiennej AAD_DEVICE_ID podczas kompilowania niestandardowej nazwy podmiotu.   Gdy żądanie certyfikatu jest przesyłane przy użyciu tego profilu SCEP, zmienna jest zastępowana identyfikatorem urządzenia usługi AAD należącym do urządzenia wysyłającego żądanie certyfikatu.


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Zarządzanie urządzeniami z systemem macOS zarejestrowanymi w programie Jamf przy użyciu aparatu zgodności urządzenia usługi Intune <!-- 1592747 -->
Korzystając z programu Jamf, można teraz wysyłać informacje o stanie urządzenia z systemem macOS do usługi Intune, która następnie oceni je pod kątem zgodności z zasadami określonymi w konsoli usługi Intune. W oparciu o stan zgodności urządzenia, a także pozostałe warunki (takie jak lokalizacja, ryzyko związane z użytkownikiem itp.) dostęp warunkowy będzie wymuszać zgodność dla urządzeń z systemem macOS uzyskujących dostęp do chmury i lokalnych aplikacji połączonych z usługą Azure Active Directory oraz usługą Office 365. Dowiedz się więcej o [konfigurowaniu integracji programu Jamf](conditional-access-integrate-jamf.md) i [wymuszaniu zgodności dla urządzeń zarządzanych przez program Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nowa akcja dotycząca urządzenia z systemem iOS <!-- 1424701 -->

Możliwe jest teraz zamykanie nadzorowanych urządzeń z systemem iOS 10.3. Ta akcja natychmiast wyłącza urządzenie bez ostrzeżenia dla użytkownika końcowego. Akcję **Wyłącz (tylko nadzorowane)** można znaleźć we właściwościach urządzenia po wybraniu urządzenia w obciążeniu **Urządzenie**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Blokowanie zmian daty/godziny na urządzeniach z systemem Samsung Knox<!-- 1468103 -->

Dodaliśmy nową funkcję, która pozwala na blokowanie zmian daty i godziny na urządzeniach z systemem Samsung Knox. Ta funkcja jest dostępna po wybraniu opcji **Profile konfiguracji urządzeń** > **Ograniczenia dotyczące urządzeń (Android)** > **Ogólne**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Obsługa konta zasobu Surface Hub <!-- 1566442  -->

Dodano nową akcję urządzenia, która umożliwia administratorom określanie i aktualizowanie konta zasobu skojarzonego z rozwiązaniem Surface Hub.

Konto zasobu jest używane przez rozwiązanie Surface Hub do uwierzytelniania w programie Skype/Exchange, co pozwala przyłączyć je do spotkania. Można utworzyć unikatowe konto zasobu, aby rozwiązanie Surface Hub było wyświetlane w spotkaniu jako sala konferencyjna. Na przykład konto zasobu może być widoczne jako *Sala konferencyjna B41/6233*. Konto zasobu (nazywane kontem urządzenia) dla rozwiązania Surface Hub zwykle trzeba skonfigurować dla lokalizacji sali konferencyjnej i gdy trzeba zmienić inne parametry konta zasobu.

Gdy administratorzy chcą zaktualizować konto zasobu na urządzeniu, muszą podać bieżące poświadczenia usługi Active Directory/Azure Active Directory skojarzone z tym urządzeniem. Jeśli dla urządzenia jest włączona funkcja rotacji haseł, administratorzy muszą przejść do usługi Azure Active Directory, aby znaleźć hasło.

> [!NOTE]
> Wszystkie pola są wysyłane w pakiecie i zastępują wszystkie pola skonfigurowane wcześniej. Puste pola również zastępują pola istniejące.

Poniżej przedstawiono ustawienia, które mogą skonfigurować administratorzy:

- **Konto zasobu**
   - **Użytkownik Active Directory**

      Nazwa_domeny\nazwa_użytkownika lub główna nazwa użytkownika (UPN): user@domainname.com

   - **Hasło**

- **Opcjonalne parametry konta zasobu** (trzeba je ustawić przy użyciu określonego konta zasobu)

   - **Okres rotacji hasła**

     Ze względów bezpieczeństwa zapewnia co tydzień automatyczną aktualizację hasła konta przez rozwiązanie Surface Hub. Aby skonfigurować jakiekolwiek parametry po włączeniu tej opcji, należy najpierw zresetować hasło konta w usłudze Azure Active Directory.

   - **Adres SIP (Session Initiation Protocol)**

     Używany tylko wtedy, gdy wykrywanie automatyczne zakończy się niepowodzeniem.

   - **Poczta e-mail**

     Adres e-mail konta urządzenia/zasobu.

   - **Serwer Exchange**

     Wymagany tylko wtedy, gdy wykrywanie automatyczne zakończy się niepowodzeniem.

   - **Synchronizacja kalendarza**

     Określa, czy jest włączona synchronizacja kalendarza oraz pozostałe usługi serwera Exchange. Na przykład: synchronizacja spotkania.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalacja aplikacji pakietu Office na urządzeniach z systemem macOS<!-- 1494311 -->
Można teraz instalować aplikacje pakietu Office na urządzeniach z systemem macOS. Ten nowy typ aplikacji umożliwi instalację programów Word, Excel, PowerPoint, Outlook i OneNote. Do aplikacji dołączony jest program Microsoft AutoUpdate (MAU), który pomaga zapewnić ich bezpieczeństwo i aktualność.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Usuwanie tokenu programu zakupów zbiorczych dla systemu iOS <!-- 820879 -->
Istnieje możliwość usunięcia tokenu programu Volume Purchasing Program (VPP) systemu iOS przy użyciu konsoli. Może to być konieczne w przypadku występowania zduplikowanych wystąpień tokenu programu VPP.

### <a name="intune-apps"></a>Aplikacje usługi Intune


### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nowa kolekcja jednostek o nazwie Bieżący użytkownik jest ograniczona do danych aktualnie aktywnych użytkowników <!-- 1667026 -->

Kolekcja jednostek **Users** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

Z kolei nowa kolekcja jednostek **Bieżący użytkownik** zawiera tylko tych użytkowników, którzy nie zostali usunięci. Kolekcja jednostek **Bieżący użytkownik** zawiera tylko aktualnie aktywnych użytkowników. Aby uzyskać informacje o kolekcji jednostek **bieżącego użytkownika**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Zaktualizowane interfejsy API programu Graph <!-- 1736360 -->

W tej wersji zaktualizowaliśmy kilka interfejsów API programu Graph dla usługi Intune, które są dostępne w wersji beta. Aby uzyskać więcej informacji, sprawdź miesięczny [dziennik zmian interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).

## <a name="week-of-december-4-2017"></a>Tydzień 4 grudnia 2017 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Usługa Intune obsługuje niedozwolone aplikacje rozwiązania Windows Information Protection <!-- 1479103 -->
Niedozwolone aplikacje można określić w usłudze Intune. Jeśli aplikacja zostanie ustawiona jako niedozwolona, nie może uzyskiwać dostępu do informacji firmowych. Jest to sytuacja odwrotna, co w przypadku listy dozwolonych aplikacji. Aby uzyskać więcej informacji, zobacz [Zalecana lista niedozwolonych aplikacji na potrzeby rozwiązania Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>Tydzień 27 listopada 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Rozwiązywanie problemów z rejestracją <!-- 746324 -->

Problemy z rejestracją są teraz widoczne dla użytkownika w obszarze roboczym **Rozwiązywanie problemów**. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Ograniczenia rejestracji przypisane do grupy <!-- 747598 -->

Administratorzy usługi Intune będą mogli [tworzyć niestandardowe ograniczenia rejestracji dotyczące typu urządzeń i limitu urządzeń dla grup użytkowników](enrollment-restrictions-set.md).

Witryna Azure Portal usługi Intune pozwala utworzyć maksymalnie 25 wystąpień poszczególnych typów ograniczeń, które można przypisać do grup użytkowników. Ograniczenia przypisane do grupy zastępują ograniczenia domyślne.

Wszystkie wystąpienia typu ograniczenia są przechowywane na ściśle uporządkowanej liście. Porządek ten określa wartości priorytetów na potrzeby rozwiązywania konfliktów. Jeśli użytkownika dotyczy więcej niż jedno wystąpienie ograniczeń, pod uwagę brane jest tylko wystąpienie o najwyższej wartości priorytetu. Priorytet danego wystąpienia można zmienić, przeciągając je do innej pozycji na liście.

Funkcja ta zostanie udostępniona podczas migracji ustawień programu Android for Work z menu rejestracji programu Android for Work do menu ograniczeń rejestracji. Ponieważ ta migracja może zająć kilka dni, zanim zostanie włączone przypisanie grupy do ograniczeń rejestracji, konto może zostać uaktualnione o inne funkcje wprowadzane w wersji listopadowej.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Obsługa wielu łączników usługi rejestracji urządzeń sieciowych (NDES) <!-- 1528104 -->

Usługa rejestracji urządzeń sieciowych (Network Device Enrollment Service, NDES) umożliwia urządzeniom przenośnym działającym bez poświadczeń domeny uzyskiwanie certyfikatów przy użyciu dodatku Prosty protokół rejestrowania certyfikatów (Simple Certificate Enrollment Protocol, SCEP).
Aktualizacja wprowadza obsługę wielu łączników usługi NDES.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Zarządzanie urządzeniami programu Android for Work w sposób niezależny od urządzeń z systemem Android <!-- 1490731 EEready-->

Usługa Intune obsługuje zarządzanie rejestracją urządzeń programu Android for Work w sposób niezależny od platformy Android. Opcje zarządzania tymi ustawieniami są dostępne w obszarze **Rejestrowanie urządzenia** > **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń**. (Wcześniej znajdowały się one w obszarze **Rejestrowanie urządzeń** > **Rejestracja w programie Android for Work** > **Ustawienia rejestracji programu Android for Work**).

Domyślnie ustawienia urządzeń programu Android for Work są takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.

Jeśli zablokujesz rejestrację urządzeń osobistych w programie Android for Work, będzie można rejestrować tylko firmowe urządzenia z systemem Android.

Podczas pracy z nowymi ustawieniami zwróć uwagę na następujące kwestie:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Jeśli wcześniej nie dodano rejestracji w programie Android for Work

Nowa platforma Android for Work jest zablokowana w domyślnych ograniczeniach typów urządzeń. Po dodaniu tej funkcji możesz zezwolić urządzeniom na rejestrację w programie Android for Work. Aby to zrobić, zastąp domyślne ograniczenie typów urządzeń — zmień je lub utwórz nowe ograniczenie.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Jeśli dodano rejestrację w programie Android for Work

Jeśli wcześniej dołączono do programu, sytuacja zależy od wybranego ustawienia:

| Ustawienie | Stan programu Android for Work w domyślnym ograniczeniu typów urządzeń | Uwagi |
| --- | --- | --- |
| **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** | Zablokowane | Wszystkie urządzenia z systemem Android należy zarejestrować bez programu Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** | Dozwolone | Wszystkie urządzenia z systemem Android, które obsługują program Android for Work, należy zarejestrować w programie Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko dla użytkowników w tych grupach** | Zablokowane | Utworzono oddzielne zasady ograniczeń typów urządzeń, które przesłaniają domyślne zasady. Zasady te definiują wcześniej wybrane grupy, zezwalając na rejestrację w programie Android for Work. Użytkownicy z wybranych grup zachowają możliwość rejestrowania urządzeń programu Android for Work. Pozostali użytkownicy nie mogą rejestrować się w programie Android for Work. |

We wszystkich przypadkach zamierzone zasady są zachowywane. Nie są wymagane żadne działania użytkownika w celu zachowania możliwości korzystania z programu Android for Work w środowisku — zarówno w skali ogólnej, jak i w odniesieniu do poszczególnych grup.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Raport instalacji aplikacji został zaktualizowany, aby obejmować stan Oczekująca instalacja <!-- 1249446 -->  

Raport **Stan instalacji aplikacji**, dostępny dla każdej aplikacji za pośrednictwem listy **Aplikacja** w obciążeniu **Aplikacje mobilne**, zawiera teraz licznik **Oczekująca instalacja** dla użytkowników i urządzeń.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Interfejs API spisu aplikacji dla systemu iOS 11 na potrzeby wykrywania zagrożeń mobilnych<!-- 1391759 -->

Usługa Intune zbiera informacje dotyczące spisu aplikacji z urządzeń osobistych i firmowych i udostępnia je dostawcom usługi wykrywania zagrożeń mobilnych, na przykład aplikacji Lookout for Work. Możesz zbierać informacje o spisie aplikacji z urządzeń z systemem iOS 11 lub nowszym.

**Spis aplikacji**  
Spisy pochodzące zarówno z urządzeń osobistych, jak i urządzeń firmowych z systemem iOS 11 lub nowszym są wysyłane do dostawcy usługi MTD. Spis aplikacji zawiera następujące dane:

 - Identyfikator aplikacji
 - Wersja aplikacji
 - Krótki numer wersji
 - Nazwa aplikacji
 - Rozmiar pakietu aplikacji
 - Dynamiczny rozmiar aplikacji
 - Wskazanie, czy aplikacja została zweryfikowana
 - Wskazanie, czy aplikacja jest zarządzana


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune <!-- 1463747 wnready -->
Dostępne są teraz nowe procesy i narzędzia służące do przenoszenia użytkowników i ich urządzeń z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune w witrynie Azure Portal, co umożliwia wykonywanie następujących zadań:
- Kopiowanie zasad i profilów z konsoli programu Configuration Manager do usługi Intune w witrynie Azure Portal
- Przenoszenie podzbioru użytkowników do usługi Intune w witrynie Azure Portal przy zachowaniu pozostałych w ramach hybrydowego zarządzania urządzeniami przenośnymi
- Migrowanie urządzeń do usługi Intune w witrynie Azure Portal bez konieczności ich ponownego rejestrowania

Aby uzyskać więcej informacji, zobacz [Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->
Gdy łącznik programu Exchange utworzy połączenie z programem Exchange za pomocą określonego zabezpieczenia dostępu kodu, będzie mieć możliwość odnajdywania innych zabezpieczeń dostępu kodu. Jeśli podstawowe zabezpieczenia dostępu kodu będą niedostępne, łącznik przejdzie w tryb failover, korzystając z innych zabezpieczeń dostępu kodu (jeśli będą dostępne) do momentu przywrócenia dostępności podstawowych zabezpieczeń dostępu kodu. Szczegółowe informacje znajdują się w temacie [Obsługa wysokiej dostępności łącznika lokalnego programu Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Zdalne ponowne uruchamianie urządzenia z systemem iOS (tylko tryb nadzorowany) <!-- 1424595 -->

Przy użyciu akcji urządzenia możesz teraz wyzwolić ponowne uruchomienie nadzorowanego urządzenia z systemem iOS 10.3 lub nowszym. Aby uzyskać więcej informacji na temat używania akcji ponownego uruchamiania urządzenia, zobacz [Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune](device-restart.md).

> [!Note]
> To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS z blokadą opartą na kodzie dostępu nie połączą się z siecią Wi-Fi po ponownym uruchomieniu. Ponadto nawiązanie połączenia z serwerem może nie być możliwe.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Obsługa logowania jednokrotnego dla systemu iOS <!-- 1333645 -->  

Użytkownicy systemu iOS mogą korzystać z logowania jednokrotnego. Aplikacje dla systemu iOS, które poszukują poświadczeń użytkownika w ładunku logowania jednokrotnego, zachowują swoją funkcjonalność po zaktualizowaniu konfiguracji ładunku. Nazwę główną i obszar można również skonfigurować przy użyciu nazwy UPN i identyfikatora urządzenia w usłudze Intune. Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Dodanie aplikacji „Znajdź mój iPhone” dla urządzeń osobistych <!--1427287-->
Może teraz sprawdzić, czy urządzenia z systemem iOS mają włączoną blokadę aktywacji. Funkcja ta była wcześniej dostępna w klasycznym portalu usługi Intune.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Zdalne blokowanie urządzeń zarządzanych z systemem macOS przy użyciu usługi Intune <!-- 1437691 -->

Zgubione urządzenie z systemem macOS można zablokować przez ustawienie 6-cyfrowego numeru PIN odzyskiwania. Gdy blokada jest aktywna, do momentu wysłania innej akcji urządzenia na ekranie jest widoczny blok **Przegląd urządzenia** z monitem o numer PIN.

Aby uzyskać więcej informacji, zobacz [Zdalne blokowanie urządzeń zarządzanych przy użyciu usługi Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Obsługa nowych szczegółów profilu SCEP <!-- 1559808 -->

Administratorzy mogą teraz określić dodatkowe ustawienia podczas tworzenia profilu SCEP na platformach Windows, iOS, macOS i Android.  Można na przykład ustawić kod IMEI, numer seryjny lub nazwę pospolitą obejmującą adres e-mail w formacie nazwy podmiotu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachowywanie danych podczas resetowania do ustawień fabrycznych <!--1588489 -->
W przypadku resetowania do ustawień fabrycznych systemu Windows 10 w wersji 1709 oraz nowszych dostępna jest nowa funkcja. Administratorzy mogą wskazać, czy informacje o rejestracji urządzenia i inne aprowizowane dane mają zostać zachowane podczas resetowania urządzenia do ustawień fabrycznych.

Podczas resetowania do ustawień fabrycznych są zachowywane następujące dane:
- Konta użytkowników skojarzone z urządzeniem
- Stan komputera (dołączenie do domeny, dołączenie do usługi Azure Active Directory)
- Rejestracja w usłudze zarządzania urządzeniami przenośnymi
- Aplikacje zainstalowane przez producenta OEM (aplikacje ze Sklepu i aplikacje Win32)
- Profil użytkownika
- Dane użytkownika przechowywane poza profilem użytkownika
- Informacje o logowaniu automatycznym użytkownika

Następujące dane nie są zachowywane:
- Pliki użytkownika
- Aplikacje zainstalowane przez użytkownika (aplikacje ze Sklepu i aplikacje Win32)
- Ustawienia urządzenia inne niż domyślne

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Wyświetlanie przypisań pierścienia aktualizacji systemu Windows 10 <!-- 1621837 -->
Podczas **rozwiązywania problemów** są widoczne wszystkie przypisania pierścieni aktualizacji systemu Windows 10 dla aktualnie wybranego użytkownika.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Ustawienia częstotliwości raportowania usługi Zaawansowana ochrona przed zagrożeniami usługi Windows Defender <!-- 1455974  -->
Usługa Zaawansowana ochrona przed zagrożeniami usługi Windows Defender (WDATP, Windows Defender Advanced Threat Protection) pozwala administratorom zmieniać częstotliwość raportowania dla zarządzanych urządzeń. Nowa opcja — **Usprawnij częstotliwość raportowania danych telemetrycznych** — umożliwia usłudze WDATP częstsze zbieranie danych i ocenianie ryzyka. Domyślne ustawienie raportowania pozwala zoptymalizować szybkość i wydajność. Zwiększenie częstotliwości raportowania może być przydatne w przypadku urządzeń narażonych na wysokie ryzyko. To ustawienie znajduje się w profilu usługi **Windows Defender ATP** w **konfiguracji urządzeń**.

#### <a name="audit-updates----1412961---"></a>Aktualizacje inspekcji <!-- 1412961 -->  
Inspekcje w usłudze Intune udostępniają rejestr operacji zmian dotyczących usługi Intune.  Wszystkie operacje tworzenia, aktualizowania, usuwania i zadań zdalnych są przechwytywane i przechowywane przez jeden rok.  Witryna Azure Portal udostępnia filtrowany widok danych inspekcji poszczególnych obciążeń z ostatnich 30 dni.  Dostępny jest odpowiedni interfejs API programu Graph, umożliwiający pobieranie danych inspekcji z ostatniego roku.

Inspekcje można znaleźć w grupie **MONITOR**. Dla każdego obciążenia dostępny jest element menu **Dzienniki inspekcji**.




## <a name="week-of-november-20-2017"></a>Tydzień 20 listopada 2017 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="google-play-protect-support-on-android----908720---"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720 -->

Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje teraz funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet. Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania.
Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play. Jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect, dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy.

- Dowiedz się [Jak utworzyć zasady zgodności urządzenia w celu włączenia funkcji Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protokół tekstowy dostępny w aplikacjach zarządzanych <!-- 1414050  -->

Aplikacje zarządzane przez zestaw SDK aplikacji usługi Intune mogą wysyłać wiadomości SMS.

## <a name="week-of-november-13-2017"></a>Tydzień 13 listopada 2017 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Aplikacja Portal firmy dla systemu macOS jest dostępna <!--1541700-->
Aplikacja Portal firmy w usłudze Intune dla systemu macOS została zaktualizowana i zoptymalizowana, aby prawidłowo wyświetlać wszystkie informacje i powiadomienia o zgodności potrzebne użytkownikom do wszystkich zarejestrowanych urządzeń. Po wdrożeniu aplikacji Portal firmy w usłudze Intune na urządzeniu usługa Microsoft AutoUpdate dla systemu macOS zapewni jej aktualizacje. Nową wersję aplikacji Portal firmy w usłudze Intune dla systemu macOS można pobrać, logując się do witryny sieci Web aplikacji Portal firmy w usłudze Intune przy użyciu urządzenia z systemem macOS.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Aplikacja Microsoft Planner znajduje się obecnie na liście zarządzania aplikacjami mobilnymi (MAM) zawierającej zatwierdzone aplikacje<!-- 1248473 -->
Aplikacja Microsoft Planner dla systemów iOS i Android należy obecnie do zatwierdzonych aplikacji funkcji zarządzania aplikacjami mobilnymi (MAM). Aplikację można skonfigurować za pomocą bloku Intune App Protection w witrynie Azure Portal na potrzeby wszystkich dzierżaw.
- Więcej informacji znajduje się na [liście zatwierdzonych aplikacji w funkcji zarządzania aplikacjami mobilnymi ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Częstotliwość aktualizacji wymagań dotyczących sieci VPN dla aplikacji na urządzeniach z systemem iOS <!-- 1547061 -->  
Administratorzy mogą obecnie usuwać wymagania dotyczące sieci VPN dla aplikacji na urządzeniach z systemem iOS; operacja obejmie urządzenia po kolejnym zaewidencjonowaniu w usłudze Intune, które zwykle następuje w ciągu 15 minut.  

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Obsługa pakietu administracyjnego programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->
Pakiet administracyjny programu System Center Operations Manager (SCOM) dla łącznika programu Exchange jest obecnie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Dzięki tej funkcji dostępne są różne sposoby monitorowania usługi, jeśli trzeba rozwiązać problemy.

## <a name="week-of-november-6-2017"></a>Tydzień 6 listopada 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Współzarządzanie dla urządzeń z systemem Windows 10 <!-- 1243445 -->
Współzarządzanie to rozwiązanie, które łączy zarządzanie tradycyjne z nowoczesnym i udostępnia ścieżkę umożliwiającą wprowadzanie zmian przy użyciu podejścia etapowego. Zasadniczo współzarządzanie jest rozwiązaniem, w którym urządzenia z systemem Windows 10 są jednocześnie zarządzane przez program Configuration Manager i usługę Microsoft Intune, a także połączone z usługami Active Directory (AD) i Azure Active Directory (Azure AD).  Taka konfiguracja umożliwia przyszłą modernizację w tempie odpowiednim dla organizacji, jeśli nie można przenieść wszystkiego naraz.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Ograniczanie rejestracji systemu Windows na podstawie wersji systemu operacyjnego <!-- 245498 -->
Jako administrator usługi Intune możesz teraz określić minimalną i maksymalną wersję systemu Windows 10 na potrzeby rejestracji urządzeń. Ograniczenia te można ustawić w bloku **Konfiguracja platformy**.

Usługa Intune będzie nadal obsługiwała rejestrowanie komputerów i telefonów z systemem Windows 8.1. Jednak tylko wersje systemu Windows 10 można ustawić z limitami minimalnym i maksymalnym. Aby zezwolić na rejestrowanie urządzeń z systemem w wersji 8.1, minimalny limit należy pozostawić pusty.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alerty dla urządzeń nieprzypisanych w programie Windows AutoPilot <!-- 1631236 -->
Dostępny jest nowy alert dotyczący urządzeń nieprzypisanych w programie Windows AutoPilot na stronie **Microsoft Intune** > **Rejestracja urządzeń** > **Przegląd**. Ten alert pokazuje, ile urządzeń z programu AutoPilot nie ma przypisanych profilów wdrożenia programu AutoPilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń w programie Windows AutoPilot. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Przycisk Odśwież dla listy urządzeń <!-- 1333581 -->
Ponieważ lista urządzeń nie jest odświeżana automatycznie, można teraz używać nowego przycisku Odśwież, który służy do aktualizowania urządzeń wyświetlanych na liście.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Obsługa urzędu certyfikacji (CA) Symantec Cloud <!-- 1333638 -->    
Usługa Intune obsługuje teraz urząd certyfikacji Symantec Cloud, co pozwala łącznikowi Intune Certificate Connector na wystawianie certyfikatów PKCS z urzędu certyfikacji Symantec Cloud dla urządzeń zarządzanych przez usługę Intune. Jeśli łącznik certyfikatów usługi Intune jest już używany z urzędem certyfikacji (CA) firmy Microsoft, można wykorzystać istniejącą konfigurację łącznika certyfikatów usługi Intune w celu dodania obsługi urzędu certyfikacji firmy Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nowe elementy dodane do spisu urządzeń <!--1404455 -->
Na potrzeby [spisu wykonywanego przez zarejestrowane urządzenia](device-inventory.md) są teraz dostępne następujące nowe elementy:

- Adres MAC sieci Wi-Fi
- Całkowita ilość miejsca
- Całkowita ilość wolnego miejsca
- MEID
- Nazwa operatora subskrybenta


### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Ustawianie dostępu dla aplikacji według minimalnego poziomu poprawki zabezpieczeń systemu Android na urządzeniu<!-- 1278463 -->   
Administrator może zdefiniować minimalny poziom poprawki zabezpieczeń systemu Android, który musi być zainstalowany na urządzeniu, aby można było uzyskać dostęp do aplikacji zarządzanej na koncie zarządzanym.

> [!Note]  
> Ta funkcja ogranicza poprawki zabezpieczeń opublikowane przez firmę Google wyłącznie na urządzeniach z systemem Android 6.0 lub nowszym.

#### <a name="app-conditional-launch-support----1193313---"></a>Obsługa uruchamiania warunkowego aplikacji <!-- 1193313 -->
Administratorzy IT mogą teraz określić za pośrednictwem portalu administracyjnego platformy Azure wymaganie, aby podczas uruchamiania aplikacji było wymuszane wprowadzenie hasła, zamiast wprowadzania kodu liczbowego PIN za pośrednictwem funkcji zarządzania aplikacjami mobilnymi (MAM). W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. W tej wersji usługi Intune ta funkcja jest dostępna **tylko w systemie iOS**. Usługa Intune obsługuje hasło w podobny sposób jak kod liczbowy PIN — określa minimalną długość, umożliwiając powtarzanie znaków i sekwencji. Funkcja ta wymaga udziału aplikacji (tj. WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu Intune App SDK przy użyciu kodu dla tej funkcji, dzięki czemu ustawienia kodu dostępu zostaną wymuszone w aplikacjach docelowych.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numery wersji aplikacji biznesowych w raporcie o stanie instalacji urządzenia <!-- 1233999 -->
W tej wersji w raporcie o stanie instalacji urządzenia wyświetlane są numery wersji aplikacji biznesowych dla systemów iOS i Android. Korzystając z tych informacji, można rozwiązywać problemy z aplikacjami lub znajdować urządzenia z nieaktualnymi wersjami aplikacji.


### <a name="device-configuration"></a>Konfiguracja urządzenia
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratorzy mogą teraz konfigurować ustawienia zapory na urządzeniu za pomocą profilu konfiguracji urządzenia <!-- 951708 -->   
Administratorzy mogą włączać zaporę dla urządzeń, a także konfigurować różne protokoły dla domeny oraz sieci prywatnych i publicznych.  Ustawienia zapory można znaleźć w profilu „Ochrona punktów końcowych”.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Funkcja Windows Defender Application Guard ułatwia ochronę urządzeń przed niezaufanymi witrynami w sposób zdefiniowany przez Twoją organizację <!-- 958257 -->   
Używając przepływu pracy funkcji Windows Information Protection lub nowego profilu „Granica sieci” w konfiguracjach urządzeń, administratorzy mogą definiować witryny jako „zaufane” lub „firmowe”. Wszystkie witryny wyświetlane w przeglądarce Microsoft Edge, które nie znajdują się w granicach zaufanej sieci na urządzeniu z 64-bitowym systemem Windows 10, są otwierane w przeglądarce na komputerze wirtualnym funkcji Hyper-V.

Funkcję Application Guard można znaleźć w profilach konfiguracji urządzeń w profilu „Ochrona punktów końcowych”. W tym miejscu administratorzy mogą skonfigurować interakcję między zwirtualizowaną przeglądarką a komputerem hosta, zaufanymi i niezaufanymi witrynami oraz danymi magazynowania generowanymi w zwirtualizowanej przeglądarce. Aby można było używać funkcji Application Guard na urządzeniu, najpierw należy skonfigurować granicę sieci. Dla jednego urządzenia należy określić tylko jedną granicę sieci.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Funkcja Windows Defender Application Control w systemie Windows 10 Enterprise udostępnia tryb ufania tylko autoryzowanym aplikacjom <!-- 1031096 -->    
Tysiące nowych, złośliwych plików tworzonych każdego dnia powodują, że walka ze złośliwym oprogramowaniem przy użyciu wykrywania wirusów w oparciu o ich sygnatury może nie zapewniać już odpowiedniej obrony przed nowymi atakami. Korzystając z funkcji Windows Defender Application Control w systemie Windows 10 Enterprise, można zmienić konfigurację urządzenia z trybu, w którym aplikacje są zaufane, dopóki nie zostaną zablokowane przez program antywirusowy lub inne rozwiązanie z zakresu zabezpieczeń, na tryb, w którym system operacyjny ufa tylko aplikacjom autoryzowanym przez przedsiębiorstwo. Zaufanie do aplikacji można przypisać za pomocą funkcji Windows Defender Application Control.

Korzystając z usługi Intune, można skonfigurować zasady kontroli aplikacji w trybie „tylko do inspekcji” lub w trybie wymuszania. Aplikacje działające w trybie „tylko do inspekcji” nie są blokowane. Tryb „tylko do inspekcji” rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta. Można również określić, czy mogą być uruchamiane wyłącznie składniki systemu Windows i aplikacje ze sklepu Microsoft Store, czy również inne aplikacje o dobrej reputacji zdefiniowane przez usługę Intelligent Security Graph.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard to nowy zestaw funkcji zapobiegania nieautoryzowanemu dostępowi do systemu Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard zawiera reguły niestandardowe, które ograniczają podatność aplikacji na wykorzystanie luk w zabezpieczeniach, zapobiega zagrożeniom w makrach i skryptach, automatycznie blokuje połączenia sieciowe z adresami IP o niskiej reputacji, a także umożliwia zabezpieczenie danych przed oprogramowaniem wymuszającym okup i nieznanymi zagrożeniami. Windows Defender Exploit Guard obejmuje następujące składniki:

- **Attack Surface Reduction (ASR)** zawiera reguły, które pozwalają zapobiegać zagrożeniom występującym w makrach, skryptach i wiadomościach e-mail.
- **Controlled Folder Access** automatycznie blokuje dostęp do zawartości do folderów chronionych.
- **Network Filter** blokuje połączenie wychodzące z dowolnej aplikacji do adresu IP/domeny o niskiej reputacji.
- **Exploit Protection** zapewnia ograniczenia pamięci, przepływu sterowania i zasad, które umożliwiają ochronę aplikacji przed lukami w zabezpieczeniach.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10 <!-- 790537 -->

Rozszerzenie do zarządzania usługi Intune pozwala przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie uzupełnia możliwości funkcji zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nowe ustawienia ograniczeń urządzeń z systemem Windows 10      <!-- 1308850 -->
-    Wiadomości (tylko dla urządzeń przenośnych) — wyłączenie testowania lub wiadomości MMS
-    Hasło — ustawienia umożliwiające włączanie standardu FIPS i uwierzytelnianie za pomocą dodatkowych urządzeń z usługą Windows Hello 
-    Ekran — ustawienia umożliwiające włączanie i wyłączanie skalowania graficznego interfejsu użytkownika dla starszych aplikacji

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Ograniczenia urządzeń z systemem Windows 10 do trybu kiosku <!-- 1308872 -->   
Możesz ograniczyć użytkowników urządzeń z systemem Windows 10 do trybu kiosku, który ogranicza użytkownikom dostęp tylko do zestawu wstępnie zdefiniowanych aplikacji.  Aby to zrobić, należy utworzyć profil ograniczenia urządzenia z systemem Windows 10 i określić ustawienia kiosku.

Tryb kiosku obsługuje dwa tryby: **pojedynczej aplikacji** (pozwala użytkownikowi na uruchomienie tylko jednej aplikacji) lub **wielu aplikacji** (zezwala na dostęp do zestawu aplikacji).  Aby określić obsługiwane aplikacje, należy zdefiniować konto użytkownika i nazwę urządzenia.  Zalogowany użytkownik ma dostęp ograniczony do zdefiniowanych aplikacji.  Aby dowiedzieć się więcej, zobacz [AssignedAccess CSP (Dostawca usługi konfiguracji AssignedAccess)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Wymagania trybu kiosku:

- Usługa Intune musi być urzędem zarządzania urządzeniami przenośnymi.
- Aplikacje muszą być już zainstalowane na urządzeniu docelowym.
- Urządzenie musi być [poprawnie udostępniane](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nowy profil konfiguracji urządzeń do tworzenia granic sieci <!-- 1311967 -->   
Wśród profilów konfiguracji urządzeń można znaleźć nowy profil konfiguracji urządzeń o nazwie **Granica sieci**. Ten profil umożliwia zdefiniowanie zasobów online, które mają być uważane za firmowe i zaufane. Granicę sieci dla urządzenia należy zdefiniować *przed* użyciem na urządzeniu funkcji takich jak Windows Defender Application Guard i Windows Information Protection. Dla każdego urządzenia należy określić tylko jedną granicę sieci.

Jako zasoby, które mają zostać uznane za zaufane, można zdefiniować zasoby chmury przedsiębiorstwa, zakresy adresów IP i wewnętrzne serwery proxy. Zdefiniowana granica sieci może być używana przez inne funkcje, takie jak Windows Defender Application Guard i Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Dwa dodatkowe ustawienia usługi Windows Defender Antivirus <!-- 1338409 -->  
**Poziom blokowania plików**

| | |
|---|---|
| Nieskonfigurowane | **Nieskonfigurowane** używa domyślnego poziomu blokowania usługi Windows Defender Antivirus i zapewnia silne wykrywanie bez zwiększania ryzyka wykrywania prawidłowych plików. |
| Wysoki | **Wysoki** stosuje silny poziom wykrywania.
| Wysoki +  | **Wysoki +** zapewnia wysoki poziom z dodatkowymi środkami ochronnymi, które mogą mieć wpływ na wydajność klienta.
| Zero tolerancji  | **Zero tolerancji** blokuje wszystkie nieznane pliki wykonywalne. |

Chociaż jest to mało prawdopodobne, ustawienie **Wysoki** może powodować wykrywanie niektórych prawidłowych plików.
Zalecamy ustawienie domyślnego poziomu blokowania plików **Nieskonfigurowane**.

**Zwiększenie limitu czasu dla skanowania plików w chmurze**  

| | |
|--|--|
| Liczba sekund (0–50) | Należy określić maksymalny czas, przez który usługa Windows Defender Antivirus powinna blokować plik podczas oczekiwania na wynik z chmury. Wartość domyślna wynosi 10 sekund: dodatkowy czas określony w tym miejscu (maksymalnie 50 sekund) jest dodawany do tych 10 sekund. W większości przypadków skanowanie trwa znacznie krócej niż wartość maksymalna. Wydłużenie czasu pozwala chmurze na staranne zbadanie podejrzanych plików. Zalecamy włączenie tego ustawienia i określenie co najmniej 20 dodatkowych sekund. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Dodano sieć VPN Citrix dla urządzeń z systemem Windows 10 <!-- 1512457 -->  
Można skonfigurować sieć VPN Citrix dla swoich urządzeń z systemem Windows 10. Sieć VPN Citrix można wybrać na liście *Wybierz typ połączenia* w bloku **Podstawowa sieć VPN** podczas konfigurowania sieci VPN dla systemu Windows 10 i nowszych.

> [!Note]
> Konfiguracja serwera Citrix istniała dla systemów iOS i Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Połączenia sieci Wi-Fi obsługują klucze wstępne w systemie iOS<!-- 1550823 -->
Klienci mogą skonfigurować profile sieci Wi-Fi, aby używać kluczy wstępnych (PSK) dla połączeń WPA/WPA2 Personal na urządzeniach z systemem iOS. Te profile są wypychane na urządzenie użytkownika, kiedy urządzenie jest zarejestrowane w usłudze Intune.

Po wypchnięciu profilu do urządzenia następny krok zależy od konfiguracji profilu.  Jeśli ustawiono wartość Połącz automatycznie, połączenie z siecią jest nawiązywane automatycznie, kiedy jest potrzebne.  Jeśli w profilu ustawiono ręczne połączenie, użytkownik musi ręcznie uaktywnić połączenie.  

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Dostęp do dzienników zarządzanych aplikacji dla systemu iOS <!-- 1469920 -->
Użytkownicy końcowi z zainstalowanym programem Managed Browser mogą teraz wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft i wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS.

Dowiedz się, jak włączyć tryb rozwiązywania problemów w programie Managed Browser na urządzeniu z systemem iOS, zobacz [jak uzyskać dostęp do dzienników zarządzanych aplikacji przy użyciu programu Managed Browser w systemie iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS w wersji 2.9.0 <!-- 1417174 -->

Ulepszono przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS. Używany język jest bardziej przyjazny dla użytkownika i tam, gdzie było to możliwe, ekrany zostały połączone. Język jest lepiej dostosowany do Twojej firmy, ponieważ w tekście instalatora używana jest jej nazwa. Ten zaktualizowany przepływ pracy można wyświetlić na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Jednostka użytkownika zawiera najnowsze dane użytkownika w modelu danych magazynu danych <!-- 1544273 -->
Pierwsza wersja modelu danych magazynu danych usługi Intune zawierała tylko ostatnie, historyczne dane usługi Intune. Podczas tworzenia raportu nie było możliwe uchwycenie bieżącego stanu użytkownika. Po wprowadzeniu tej aktualizacji **jednostka użytkownika** jest wypełniana najnowszymi danymi użytkownika.


## <a name="notices"></a>Uwagi

### <a name="plan-for-change-new-windows-10-setting-for-kiosk-configuration-in-intune----1560072---"></a>Planowanie zmian: nowe ustawienie systemu Windows 10 dla konfiguracji kiosku w usłudze Intune <!-- 1560072 -->
Zmieniamy sposób oraz miejsce konfiguracji systemu Windows 10 1709 i nowszego (RS3 i nowszy) w witrynie Azure Portal usługi Intune.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie? 
Z naszych danych wynika, że używasz ustawienia Windows 10 > Ograniczenia dotyczące urządzeń > Ustawienie kiosku (wersja zapoznawcza). Nazwa tego ustawienia zostanie zmieniona w maju w interfejsie użytkownika na Windows 10 > Ograniczenia dotyczące urządzeń > Kiosk (przestarzałe), aby wskazać, że jego używanie nie jest zalecane. To ustawienie będzie jednak nadal działać do momentu aktualizacji usługi Intune w lipcu. Następnie zostanie ustawione jako przestarzałe w ramach zaplecza i nie będzie dłużej działać. Jako alternatywę w maju wydamy nowy profil konfiguracji urządzenia, Windows 10 > Kiosk, zawierający ustawienia służące do konfigurowania kiosków w systemie Windows 10 RS4 lub nowszym.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?  
Po wydaniu aktualizacji usługi Intune pod koniec maja zostaną udostępnione instrukcje dotyczące testowania oraz weryfikowania, czy można przeprowadzić migrację konfiguracji kiosku z systemu Windows 10 RS3 do systemu Windows 10 RS4. Użyj tych instrukcji, aby skonfigurować urządzenia jako kioski przy użyciu nowego profilu konfiguracji urządzenia dla kiosków.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Ta zmiana wpłynie zarówno na klientów z autonomiczną usługą Intune, jak i na klientów ze środowiskami hybrydowymi (usługą Intune z programem Configuration Manager). Ta integracja pomoże uprościć administrowanie chmurą. Teraz wystarczy przejść do tylko jednego bloku na platformie Azure — bloku usługi Intune — w celu zarządzania grupami, zasadami, aplikacjami i urządzeniami przenośnymi.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Otaguj usługę Intune jako ulubioną zamiast bloku usługi Intune App Protection i zapoznaj się z przepływem pracy zasad ochrony aplikacji w bloku aplikacji mobilnych w usłudze Intune. Przez krótki okres będzie działać przekierowanie, a następnie blok App Protection zostanie usunięty. Wszystkie zasady usługi App Protection są już dostępne w usłudze Intune i można modyfikować dowolne zasady dostępu warunkowego, postępując zgodnie z następującą dokumentacją: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Dodatkowe informacje**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Planowanie zmian: zmiany w obsłudze wtyczki zestawu SDK aplikacji usługi Microsoft Intune dla oprogramowania Cordova
Usługa Intune kończy obsługę [wtyczki zestawu Microsoft Intune App SDK dla oprogramowania Cordova](app-sdk-cordova.md) z dniem 1 maja 2018 r. W zamian zalecamy używanie dostępnego w usłudze Intune narzędzia opakowującego aplikacje, aby przygotować swoje aplikacje oparte na oprogramowaniu Cordova do zapewnienia zarządzania i dostępności w usłudze Intune. Gdy ta zmiana zacznie obowiązywać, wtyczka zestawu Microsoft Intune App SDK dla oprogramowania Cordova nie będzie już utrzymywana ani nie będzie otrzymywać aktualizacji. Deweloperzy aplikacji nie będą mogli używać tej wtyczki. Usługa Intune planuje kontynuowanie obsługi aplikacji skompilowanych przy użyciu oprogramowania Cordova. Jednak wszelkie aplikacje skompilowane z użyciem wtyczki zestawu Microsoft Intune App SDK dla oprogramowania Cordova będą miały ograniczoną funkcjonalność w usłudze Intune. Po opakowaniu za pomocą dostępnego w usłudze Intune narzędzia opakowującego aplikacje można wdrożyć aplikacje dla użytkowników końcowych w zwykły sposób. W przypadku aplikacji systemu Android opartych na oprogramowaniu Cordova, które są publikowane w sklepie Google Play:
- Użytkownicy końcowi zostaną poproszeni o podanie poświadczeń, aby uzyskać zasady usługi Intune przy pierwszym uruchomieniu.
- Aplikacje powinny zostać opublikowane w sklepie z aplikacjami przeznaczonym dla użytkowników usługi Intune, na przykład „Contoso App for Intune”.

Aby uzyskać więcej informacji o narzędziu do opakowywania aplikacji, zobacz [Narzędzie opakowujące aplikacje dla systemu iOS](app-wrapper-prepare-ios.md) i [Narzędzie opakowujące aplikacje dla systemu Android](app-wrapper-prepare-android.md). Wszelkie problemy lub pytania należy zgłaszać na adres [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com).

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Planowanie zmian: już teraz zacznij zarządzać urządzeniami przenośnymi za pomocą usługi Intune na platformie Azure <!-- 1227338 -->
Ponad rok temu ogłosiliśmy [publiczną wersję zapoznawczą usługi Intune na platformie Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/), a sześć miesięcy temu opublikowaliśmy [ogólnie dostępną wersję nowego środowiska pracy administratora](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) dla usługi Intune. 31 sierpnia 2018 r. wyłączymy funkcję zarządzania urządzeniami przenośnymi w klasycznej konsoli programu Silverlight dla klientów korzystających z autonomicznej usługi Intune. Zamiast tego na potrzeby zarządzania urządzeniami przenośnymi można używać [usługi Intune na platformie Azure](https://aka.ms/Intune_on_Azure). Jeśli nadal używasz konsoli klasycznej do zarządzania urządzeniami przenośnymi, zapoznaj się z usługą Intune na platformie Azure. Ta zmiana nie powinna mieć żadnego wpływu na użytkowników końcowych. Program Silverlight będzie nadal umożliwiał zarządzanie komputerami klasycznymi. Więcej informacji na temat tej zmiany i jej wpływu na Ciebie znajduje się [tutaj](https://aka.ms/Intune_on_Azure_mdm).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 roku wymagają przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Jeśli istniejące konto nie ma dostępu do witryny Azure Portal, zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska.

## <a name="whats-coming"></a>Wkrótce

### <a name="local-device-security-option-settings----1251887---"></a>Ustawienia opcji zabezpieczeń urządzenia lokalnego <!-- 1251887 -->
Na urządzeniach z systemem Windows 10 będzie można włączać ustawienia zabezpieczeń przy użyciu nowych ustawień opcji zabezpieczeń urządzenia lokalnego. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Aktualizacja nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968-->

W kwietniu wprowadzimy nowe środowisko witryny internetowej Portal firmy zawierające aktualizacje interfejsu użytkownika, usprawnione przepływy pracy i ulepszone ułatwienia dostępu. Będzie ono obejmować ulepszenia oparte na potrzebach klientów, takie jak udostępnianie aplikacji i lepsza ogólna wydajność, które zapewnią użytkownikom większy komfort pracy.
Na podstawie opinii klientów dodaliśmy nowe funkcje, które znacznie udoskonalą istniejącą funkcjonalność i użyteczność:

-   Ulepszenia interfejsu użytkownika w całej witrynie internetowej
-   Możliwość udostępniania bezpośrednich linków do aplikacji
- Zwiększona wydajność dużych wykazów aplikacji

Nie musisz niczego robić, aby przygotować się do tej zmiany. Powiadomimy Cię, gdy zaktualizowana witryna internetowa Portal firmy będzie dla Ciebie dostępna. Może być jednak konieczne zaktualizowanie zrzutów ekranu w dokumentach użytkownika końcowego. Pamiętaj, że może być też konieczne zaktualizowanie dokumentacji dla aplikacji Portal firmy w systemie iOS, ponieważ witryna internetowa obsługuje sekcję **Aplikacje** aplikacji systemu iOS. Przykładowy obraz jest widoczny na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. W naszym [blogu pomocy technicznej usługi Intune](https://aka.ms/compportalats) będziemy umieszczać szczegółowe informacje.



## <a name="see-also"></a>Zobacz też
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/cloud-platform/roadmap)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
