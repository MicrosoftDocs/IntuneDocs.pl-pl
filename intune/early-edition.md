---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b6ca8108924c6c062da0d0ef56ab5b68635dd9ca
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Wersja wczesna usługi Microsoft Intune — kwiecień 2018

**Wczesna wersja** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie należy udostępniać tych informacji poza firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
>Dla usługi Intune opracowywane są następujące zmiany. Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1804 start -->

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Dodano nowe ustawienia funkcji Windows Defender Credential Guard do ustawień programu Endpoint Protection <!--1102252 --><!--from 1802-->

Nowe ustawienia funkcji [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) zostaną dodane do obszaru **Konfiguracja urządzenia** > **Profile** > **Endpoint Protection**. Zostaną dodane następujące ustawienia:

- Poziom zabezpieczeń platformy: określ, czy poziom zabezpieczeń platformy zostanie włączony przy następnym ponownym uruchomieniu. Zabezpieczenia oparte na wirtualizacji wymagają bezpiecznego rozruchu. Opcjonalnie zabezpieczenia oparte na wirtualizacji można włączyć przy użyciu ochrony bezpośredniego dostępu do pamięci (DMA, direct memory access). Ochrona DMA wymaga obsługi sprzętowej i będzie można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach.
- Zabezpieczenia oparte na wirtualizacji: określ, czy zabezpieczenia oparte na wirtualizacji zostaną włączone przy następnym ponownym uruchomieniu.
- Windows Defender Credential Guard: włącz funkcję Credential Guard z zabezpieczeniami opartymi na wirtualizacji, aby ułatwić zapewnienie ochrony poświadczeń, przy następnym ponownym uruchomieniu, gdy poziom zabezpieczeń platformy z bezpiecznym rozruchem i zabezpieczenia oparte na wirtualizacji są włączone. Dostępne opcje: **Wyłączone**, **Włączone z blokadą UEFI**, **Włączone bez blokady** i **Nieskonfigurowane**.
  - Opcja „Wyłączone” zdalnie wyłącza funkcję Credential Guard, jeśli została ona wcześniej włączona za pomocą opcji „Włączone bez blokady”.

  - Opcja „Włączone z blokadą UEFI” zapewnia, że funkcji Credential Guard nie będzie można wyłączyć za pomocą klucza rejestru ani przy użyciu zasad grupy. Aby wyłączyć funkcję Credential Guard po użyciu tego ustawienia, należy ustawić zasady grupy na opcję „Wyłączone” i usunąć funkcję zabezpieczeń z każdego komputera, gdy użytkownik jest fizycznie przy komputerze, w celu wyczyszczenia konfiguracji utrwalonej w interfejsie UEFI. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

  - Opcja „Włączone bez blokady” umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 (wersja 1511) lub nowszy.

  - Opcja „Nieskonfigurowane” pozostawia niezdefiniowane ustawienie zasad. Zasady grupy nie zapisują ustawienia zasad w rejestrze, więc nie ma ono wpływu na komputery ani użytkowników. Jeśli w rejestrze znajduje się bieżące ustawienie, nie zostanie ono zmodyfikowane.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Obsługa kodu dostępu dla numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi w systemie Android<!-- 1438086 -->

Administratorzy usługi Intune będą mogli określić wymaganie dla uruchamiania aplikacji w celu wymuszenia użycia kodu dostępu zamiast numeru PIN rozwiązania do zarządzania aplikacjami mobilnymi. W przypadku skonfigurowania tej opcji użytkownik będzie musiał określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. Usługa Intune obsługuje kod dostępu podobnie jak istniejący liczbowy numer PIN, umożliwiając ustawienie minimalnej długości oraz reguł powtarzania znaków i sekwencji w konsoli administracyjnej. Ta funkcja wymaga najnowszej wersji aplikacji Portal firmy w systemie Android. Ta funkcja jest już dostępna dla systemu iOS.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Blokowanie aparatu i przechwytywania ekranu w aplikacji Android for Work <!-- 1098977 eeready-->
Podczas konfigurowania ograniczeń urządzenia z systemem Android będzie można zablokować dwie nowe właściwości: 
- Aparat: blokuje dostęp do wszystkich aparatów w urządzeniu
- Przechwytywanie ekranu: blokuje przechwytywanie ekranu i wyświetlanie zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo

Dotyczy aplikacji Android for Work.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Obsługa aplikacji biznesowych dla systemu macOS <!-- 1473977 -->
Usługa Microsoft Intune będzie umożliwiać instalowanie aplikacji biznesowych (LOB) dla systemu macOS z witryny Azure Portal. Aplikację LOB dla systemu macOS będzie można dodać do usługi Intune po jej wstępnym przetworzeniu za pomocą narzędzia dostępnego w usłudze GitHub. W witrynie Azure Portal wybierz pozycję **Aplikacje mobilne** w bloku **Intune**. W bloku **Aplikacje mobilne** wybierz pozycje **Aplikacje** > **Dodaj**. W bloku **Dodaj aplikację** wybierz pozycję **Aplikacja biznesowa**. 

### <a name="support-for-user-less-devices----1637553---"></a>Obsługa urządzeń bez użytkowników <!-- 1637553 -->
Usługa Intune będzie oferować możliwość oceny zgodności urządzenia bez użytkowników, takiego jak Microsoft Surface Hub. Zasady zgodności mogą stosować się do konkretnych urządzeń. Dzięki temu zgodność (i niezgodność) można określić dla urządzeń, które nie mają skojarzonego użytkownika.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Dodatki dla ustawień opcji zabezpieczeń urządzenia lokalnego <!-- 1403702 -->
Będzie można skonfigurować dodatkowe ustawienia opcji zabezpieczeń urządzenia lokalnego dla urządzeń z systemem Windows 10. Dodatkowe ustawienia będą dostępne w następujących obszarach: klient sieci Microsoft, serwer sieci Microsoft, dostęp do sieci i zabezpieczenia oraz logowanie interakcyjne. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Wymagana instalacja zasad, aplikacji oraz profilów certyfikatów i sieciowych <!-- 1553555 -->
Administratorzy będą mogli zablokować dostęp użytkowników końcowych do pulpitu systemu Windows 10 RS4 do momentu zainstalowania zasad, aplikacji oraz profilów certyfikatów i sieciowych przez usługę Intune podczas aprowizowania urządzeń z rozwiązaniem AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Reguły usuwania urządzeń <!-- 1609459 -->
Będą dostępne nowe reguły umożliwiające automatyczne usuwanie urządzeń, które nie zostały zaewidencjonowane przez ustawioną liczbę dni. Aby wyświetlić nową regułę, przejdź do okienka **Intune**, wybierz pozycję **Urządzenia**, a następnie pozycję **Reguły usuwania urządzeń**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokowanie aplikacji i środowisk konsumenckich na urządzeniach z rozwiązaniem AutoPilot w systemie Windows 10 Enterprise RS4<!-- 1621980 -->
Będzie można zablokować instalację aplikacji i środowisk konsumenckich na urządzeniach z systemem Windows 10 Enterprise RS4 i rozwiązaniem AutoPilot. Aby wyświetlić tę funkcję, przejdź do pozycji **Intune** > **Rejestrowanie urządzenia** > **Rejestrowanie systemu Windows** > **Profile AutoPilot systemu Windows** > **Utwórz nowy** > **Ustawienia rejestracji**. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>Zaawansowana ochrona przed zagrożeniami zintegrowana z usługą Intune <!-- 1629303 -->
Funkcja [zaawansowanej ochrony przed zagrożeniami](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) pokazuje poziom ryzyka urządzeń z systemem Windows 10. Podczas oceny urządzeń z systemem Windows 10 pod kątem zgodności przez usługę Intune wynik oceny ryzyka przez funkcję zaawansowanej ochrony przed zagrożeniami jest dołączany do oceny. Funkcja zaawansowanej ochrony przed zagrożeniami w połączeniu z dostępem warunkowym ułatwia ochronę sieci.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nowe kroki rejestracji dla użytkowników na urządzeniach z systemem macOS High Sierra 10.13.2+ <!--1734567 -->
W systemie macOS High Sierra 10.13.2 wprowadzono pojęcie rejestracji w rozwiązaniu MDM „zatwierdzonej przez użytkownika”. W przyszłości zatwierdzone rejestracje będą umożliwiać usłudze Intune zarządzanie niektórymi ustawieniami istotnymi dla zabezpieczeń. Aby uzyskać więcej informacji, zobacz dokumentację pomocy technicznej firmy Apple: https://support.apple.com/HT208019.

Urządzenia zarejestrowane przy użyciu aplikacji Portal firmy dla systemu macOS będą traktowane jako „niezatwierdzone przez użytkownika”, chyba że użytkownik końcowy otworzy preferencje systemu i ręcznie wykona zatwierdzenie. Dlatego aplikacja Portal firmy dla systemu macOS teraz kieruje użytkowników systemu macOS 10.13.2 i nowszych do kroków ręcznego zatwierdzenia rejestracji pod koniec procesu rejestracji. Konsola administracyjna usługi Intune zgłasza fakt zatwierdzenia zarejestrowanego urządzenia przez użytkownika.

### <a name="delete-autopilot-devices----1713650---"></a>Usuwanie urządzeń z rozwiązaniem AutoPilot <!-- 1713650 -->
Administratorzy usługi Intune będą mogli usunąć urządzenia z rozwiązaniem AutoPilot.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Wbudowane grupy Wszyscy użytkownicy i Wszystkie urządzenia na potrzeby przypisywania aplikacji Android for Work (AFW) <!-- 1813073 -->
Będzie dostępna możliwość użycia wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji AFW. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

### <a name="improved-device-deletion-experience---1832333---"></a>Ulepszona funkcja usuwania urządzeń <!--1832333 -->
Nie trzeba już będzie wymagać usunięcia danych firmy ani resetować do ustawień fabrycznych przed usunięciem urządzenia z usługi Intune.

Aby zobaczyć nową funkcję, zaloguj się do usługi Intune i wybierz pozycje **Urządzenia** > **Wszystkie urządzenia** > nazwa urządzenia > **Usuń**.

 Jeśli chcesz nadal otrzymywać powiadomienia o wyczyszczeniu lub wycofaniu, możesz użyć standardowego cyklu życia urządzenia, uruchamiając polecenie **Usuń dane firmy** oraz **Resetuj do ustawień fabrycznych**, a następnie polecenie **Usuń**. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Profile rozwiązania AutoPilot będą stosowane dla grup <!-- 1877935 -->
Obecnie profile wdrażania rozwiązania AutoPilot można przypisać do wybranych urządzeń. Pod koniec kwietnia będzie można przypisywać te profile następująco:
- Utwórz grupy usługi Azure AD, zawierające urządzenia z rozwiązaniem AutoPilot.
- Przypisz wybrane profile do grupy usługi Azure AD. Profil rozwiązania AutoPilot będzie teraz przypisany do urządzeń rozwiązania AutoPilot w tej grupie.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Odtwarzanie dźwięków w systemie iOS w trybie utraty <!-- 1629303 -->
Jeśli urządzenia z systemem iOS nadzorowane w rozwiązaniu do zarządzania urządzeniami przenośnymi są w [trybie utraty](device-lost-mode.md), możesz odtwarzać dźwięk (**Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie z systemem iOS > **Przegląd** > **Więcej**). Dźwięk będzie odtwarzany w sposób ciągły aż do zakończenia trybu utraty na urządzeniu lub wyłączenia przez użytkownika dźwięku na urządzeniu. Dotyczy urządzeń z systemem iOS 9.3 lub nowszym.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Użycie niestandardowej nazwy podmiotu w certyfikacie SCEP <!-- 2064190 -->
Istnieje możliwość użycia nazwy pospolitej **OnPremisesSamAccountName** w niestandardowej nazwie podmiotu dla profilu certyfikatu SCEP. Na przykład możesz użyć nazwy `CN={OnPremisesSamAccountName})`.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Wysyłanie raportów diagnostycznych z aplikacji Portal firmy dla systemu macOS <!-- 2216677 -->
Aplikacja Portal firmy dla urządzeń z systemem macOS będzie aktualizowana pod kątem ulepszenia sposobu raportowania błędów dotyczących usługi Intune przez użytkowników. W aplikacji Portal firmy pracownicy będą mogli:
- Przekazywać raporty diagnostyczne bezpośrednio do zespołu deweloperów firmy Microsoft.
- Wysłać wiadomość e-mail z identyfikatorem zdarzenia do zespołu pomocy technicznej IT firmy.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>Zawsze włączona sieć VPN w systemie Windows 10 <!--1333666 -->

Obecnie opcji [Zawsze włączone](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) można używać na urządzeniach z systemem Windows 10 za pomocą niestandardowego profilu wirtualnej sieci prywatnej (VPN) utworzonego za pomocą identyfikatora URI OMA.

Dzięki tej aktualizacji administratorzy będą mogli włączyć ustawienie Zawsze włączone dla profili sieci VPN systemu Windows 10 bezpośrednio w usłudze Intune za pomocą witryny Azure Portal. Zawsze włączone profile sieci VPN automatycznie nawiążą połączenie, gdy:

- Użytkownik zaloguje się na urządzeniu
- Sieć na urządzeniu zostanie zmieniona
- Ekran na urządzeniu zostanie włączony ponownie po wyłączeniu

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Ulepszona obsługa komunikatów o błędach przekazywania certyfikatu wypychanego przez rozwiązanie MDM firmy Apple <!-- 2172331 -->

Komunikat o błędzie będzie zawierał wyjaśnienie mówiące o tym, że podczas odnawiania istniejącego certyfikatu rozwiązania MDM należy użyć tego samego identyfikatora Apple ID.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Wykres profilów urządzeń i lista stanów obejmuje wszystkie urządzenia w grupie <!-- 1449153 eeready -->
Po skonfigurowaniu profilu urządzenia (**Konfiguracja urządzenia** > **Profile**) wybiera się profil urządzenia, taki jak dotyczący systemu iOS. Ten profil jest przypisywane do grupy, która zawiera urządzenia z systemem iOS i inne. Licznik na wykresie graficznym pokazuje, że profil jest stosowany do urządzeń z systemem iOS *i* innych (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Przegląd**). Po wybraniu wykresu graficznego na karcie **Przegląd** na liście **Stan urządzenia** zostaną wyświetlone wszystkie urządzenia w grupie zamiast tylko urządzeń z systemem iOS. 

Dzięki tej aktualizacji wykres graficzny (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Przegląd**) będzie przedstawiać tylko liczbę dla konkretnego profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy urządzeń z systemem iOS, wykres zawiera tylko liczbę urządzeń z systemem iOS. Po wybraniu wykresu graficznego i otwarciu pozycji **Stan urządzeń** zostaną wyświetlone tylko urządzenia z systemem iOS.

Podczas wprowadzania tej aktualizacji graficzny wykres użytkowników jest tymczasowo usuwany. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Obsługa wielu programów Exchange Connector <!-- 2070451 -->

Nie będzie już ograniczenia do jednego programu Microsoft Intune Exchange Connector na dzierżawę. Usługa Intune będzie obsługiwać wiele programów Microsoft Intune Exchange Connector, dzięki czemu możliwe będzie skonfigurowanie dostępu warunkowego w usłudze Intune przy użyciu wielu lokalnych organizacji programu Exchange.

Dzięki lokalnemu łącznikowi programu Exchange w usłudze Intune możesz zarządzać dostępem urządzeń do lokalnych skrzynek pocztowych programu Exchange na podstawie tego, czy urządzenie jest zarejestrowane w usłudze Intune i jest zgodne z zasadami zgodności urządzeń usługi Intune. Aby skonfigurować łącznik, pobierz lokalny łącznik programu Exchange z witryny Azure Portal i zainstaluj go na serwerze w organizacji programu Exchange. Na pulpicie nawigacyjnym usługi Microsoft Intune wybierz pozycję **Dostęp lokalny**, a następnie w obszarze **Konfiguracja** wybierz pozycję **Łącznik Exchange ActiveSync**. Pobierz lokalny łącznik programu Exchange i zainstaluj go na serwerze w organizacji programu Exchange. Ponieważ nie ma już ograniczenia do jednego łącznika programu Exchange na dzierżawę, jeśli masz dodatkowe organizacje programu Exchange, możesz wykonać te same czynności, aby pobrać i zainstalować łącznik dla każdej dodatkowej organizacji programu Exchange.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Nadchodząca obsługa klienta oprogramowania Cisco AnyConnect dla systemu iOS <!-- 1333708 -->

Nowe profile sieci VPN utworzone dla oprogramowania Cisco AnyConnect będą działały z wersją oprogramowania Cisco AnyConnect 4.0.7x i wyższymi. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS; w przypadku systemów Android i macOS oraz programu Android for Work nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.

#### <a name="more-information"></a>Więcej informacji

Aby włączyć obsługę nowej aplikacji, musisz utworzyć nowy profil sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS, ponieważ nowa aplikacja Cisco AnyConnect oraz aplikacja Cisco Legacy AnyConnect to oddzielne aplikacje. Jeśli zarządzasz klientem oprogramowania AnyConnect w danym środowisku, musisz wdrożyć także nową aplikację Cisco AnyConnect. Aby wykonać uaktualnienie musisz także usunąć profil sieci VPN oprogramowania Cisco Legacy AnyConnect oraz aplikację Cisco Legacy AnyConnect.

W początkowym wydaniu integracja kontroli dostępu do sieci (NAC) nie będzie działać w przypadku nowego klienta oprogramowania AnyConnect. Wraz z firmą Cisco pracujemy nad umożliwieniem integracji NAC w przyszłym wydaniu usługi Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Możliwość wdrożenia wymaganych aplikacji biznesowych (LOB) dla wszystkich użytkowników urządzeń z systemem Windows 10 Desktop <!-- 1627835 RS4 -->
Klienci będą mogli wdrażać wymagane aplikacje biznesowe systemu Windows 10 oraz instalować je w kontekstach urządzeń. Umożliwi to udostępnienie tych aplikacji wszystkim użytkownikom urządzenia. Dotyczy to tylko urządzeń z systemem Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Ulepszona rejestracja za pomocą aplikacji Portal firmy <!-- 1874230-->
Użytkownicy rejestrujący urządzenia za pomocą aplikacji Portal firmy w systemie Windows 10 w wersji 1703 i wyższej będą mogli wykonać pierwszy krok rejestracji bez wychodzenia z aplikacji.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Zaktualizujemy środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy wprowadzimy aktualizację aplikacji Portal firmy dla systemu Android dzielącą element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nowe ustawienia drukarek dla profili edukacyjnych <!-- 1308900 -->

W przypadku profili edukacyjnych będą dostępne nowe ustawienia w kategorii **Drukarki**: **Drukarki**, **Drukarka domyślna**, **Dodaj nowe drukarki**.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.




## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.


### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


