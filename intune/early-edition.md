---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99b1436fdf718b54f54f7e90835668d4a632b7ce
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>Wczesna wersja usługi Microsoft Intune — marzec 2018

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

### <a name="enhanced-jailbreak-detection----846515---"></a>Ulepszone wykrywanie zdjęcia zabezpieczeń systemu <!-- 846515 -->

Ulepszone wykrywanie zdjęcia zabezpieczeń systemu jest nowym ustawieniem zgodności, które usprawni sposób, w jaki usługa Intune ocenia urządzenia ze zdjętymi zabezpieczeniami systemu. To ustawienie spowoduje częstsze ewidencjonowanie urządzenia w usłudze Intune z wykorzystaniem usług lokalizacyjnych urządzenia, co będzie miało wpływ na użycie baterii.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Możliwość wdrożenia wymaganych aplikacji biznesowych (LOB) dla wszystkich użytkowników urządzeń z systemem Windows 10 Desktop <!-- 1627835 RS4 -->
Klienci będą mogli wdrażać wymagane aplikacje biznesowe systemu Windows 10 oraz instalować je w kontekstach urządzeń. Umożliwi to udostępnienie tych aplikacji wszystkim użytkownikom urządzenia. Dotyczy to tylko urządzeń z systemem Windows 10 Desktop.

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Wygasające aplikacje biznesowe (LOB) dla usługi Microsoft Intune <!-- 748789 -->
W witrynie Azure Portal usługa Intune powiadomi Cię o aplikacjach biznesowych, które wkrótce wygasną. Po przekazaniu nowej wersji aplikacji biznesowej usługa Intune usunie powiadomienie o wygaśnięciu z listy aplikacji.

### <a name="company-portal-enrollment-improved----1874230--"></a>Ulepszona rejestracja za pomocą aplikacji Portal firmy <!-- 1874230-->
Użytkownicy rejestrujący urządzenia za pomocą aplikacji Portal firmy w systemie Windows 10 w wersji 1703 i wyższej będą mogli wykonać pierwszy krok rejestracji bez wychodzenia z aplikacji.

### <a name="new-management-name-column----1333586---"></a>Nowa kolumna Nazwa zarządzania <!-- 1333586 -->
Do bloku urządzeń zostanie dodana nowa kolumna **Nazwa zarządzania**. Jest to generowana automatycznie, nieedytowalna nazwa przypisywana każdemu urządzeniu na podstawnie następującego wzoru:
- Nazwa domyślna dla wszystkich urządzeń: <username>_<devicetype>_<enrollmenttimestamp>
- W przypadku urządzeń dodanych zbiorczo: <PackageId/ProfileId>_<DeviceType>_<EnrollmentTime>

Jest to opcjonalna kolumna w bloku urządzeń. Domyślnie będzie ona niedostępna i można do niej uzyskać dostęp tylko za pośrednictwem selektora kolumn. Ta nowa kolumna nie ma wpływu na nazwę urządzenia.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Nowe ustawienia profilu konfiguracji urządzenia powiadomień w aplikacji Windows Defender Security Center (WDSC)<!-- 1631906 -->

Do profilu konfiguracji urządzenia powiadomień w aplikacji Windows Defender Security Center (WDSC) zostaną dodane trzy nowe ustawienia.

Administratorzy będą mogli wykonywać następujące czynności:

- Ukrywanie filaru Tożsamość
- Ukrywanie filaru Sprzęt i jego ustawień podrzędnych
- Ukrywanie filaru Oprogramowanie wymuszające okup (przywracanie plików w usłudze OneDrive dla Firm)

Po ukryciu tych filarów przed aplikacją WDSC użytkownicy końcowi nie będą mogli konfigurować tych ustawień i nie będą generowane żadne powiadomienia dotyczące ukrytych składników.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Zasady zarządzania aplikacjami mobilnymi określane na podstawie stanu zarządzania <!-- 1665993 -->

Możliwe będzie określanie zasad zarządzania aplikacjami mobilnymi na podstawie stanu zarządzania urządzenia:

- **Urządzenia z systemem iOS** — możliwe będzie określanie urządzeń niezarządzanych (tylko dla usługi zarządzania aplikacjami mobilnymi) lub urządzeń zarządzanych w usłudze Intune.
- **Urządzenia z systemem Android** — możliwe będzie określanie urządzeń niezarządzanych, urządzeń zarządzanych w usłudze Intune oraz zarządzanych w usłudze Intune profilów programu Android Enterprise (znanego wcześniej jako Android for Work).

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>Konfigurowanie programu Gatekeeper w celu kontrolowania źródła pobierania aplikacji systemu macOS <!-- 1690459-->

Możliwe będzie skonfigurowanie programu Gatekeeper do ochrony urządzeń przed aplikacjami przez kontrolowanie lokalizacji, z których można pobierać aplikacje. Możliwe będzie skonfigurowanie następujących źródeł pobierania: **Sklep Mac App Store**, **Sklep Mac App Store i zidentyfikowani deweloperzy** lub **Dowolne**. Ponadto będzie możliwe skonfigurowanie, czy użytkownicy mogą instalować aplikacje, przytrzymując klawisz Control i klikając przyciskiem myszy, aby przesłonić kontrolki programu Gatekeeper.

Te ustawienia można znaleźć w obszarze **Konfiguracja urządzenia** -> **Utwórz profil** -> **macOS** -> **Endpoint Protection**.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurowanie zapory aplikacji dla komputerów Mac <!-- 1690461 -->

Możliwe będzie skonfigurowanie zapory aplikacji dla komputerów Mac. Dzięki temu można kontrolować połączenia dla poszczególnych aplikacji, a nie dla poszczególnych portów. Ułatwia to uzyskanie korzyści z ochrony zapewnianej przez zaporę oraz ułatwia uniemożliwianie niepożądanym aplikacjom przejmowania kontroli na portami sieciowymi otwartymi dla wiarygodnych aplikacji.

Tę funkcję można znaleźć w obszarze **Konfiguracja urządzenia** -> **Utwórz profil** -> **macOS** -> **Endpoint Protection**.

Po włączeniu ustawienia Zapora możesz skonfigurować zaporę przy pomocy dwóch strategii:

- Blokowanie wszystkich połączeń przychodzących

   Możesz zablokować wszystkie połączenia przychodzące dla urządzeń docelowych. Jeśli postanowisz to zrobić, połączenia przychodzące zostaną zablokowane dla wszystkich aplikacji.

- Zezwalanie na określone aplikacje lub ich blokowanie

   Możesz zezwalać określonym aplikacjom na odbieranie połączeń przychodzących lub blokować im tę możliwość. Możesz także włączyć tryb niewidzialności, aby uniemożliwić wysyłanie odpowiedzi na żądania sondowania.

#### <a name="more-information"></a>Więcej informacji

- Blokowanie wszystkich połączeń przychodzących

   Uniemożliwia to wszystkim usługom udostępniania (takim jak Udostępnianie plików czy Udostępnianie ekranu) odbieranie połączeń przychodzących. Usługi systemu, które nadal mogą odbierać połączenia przychodzące, to:
   - configd — implementuje protokół DHCP oraz inne usługi konfiguracji sieci
   - mDNSResponder — implementuje usługę Bonjour
   - racoon — implementuje protokołu IPSec

   Aby móc korzystać z usług udostępniania, upewnij się, że ustawienie **Połączenia przychodzące** ma wartość **Nie skonfigurowano** (a nie **Zablokowane**).

- Tryb niewidzialności

   Włącz tę opcję, aby zapobiec odpowiadaniu przez komputer na żądania sondowania. Komputer nadal odpowiada na żądania przychodzące dla autoryzowanych aplikacji. Nieoczekiwane żądania, takie jak ICMP (ping), są ignorowane.


### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Zaktualizujemy środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy wprowadzimy aktualizację aplikacji Portal firmy dla systemu Android dzielącą element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Niestandardowe kategorie książek dla książek elektronicznych programu zakupów zbiorczych (VPP) <!-- 1488911 -->
Możliwe będzie tworzenie niestandardowych kategorii książek elektronicznych, a następnie przypisywanie do tych kategorii książek elektronicznych programu VPP. Użytkownicy końcowi będą mogli wtedy wyświetlać nowo utworzone kategorie książek elektronicznych oraz książki przypisane do tych kategorii.

### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868--"></a>Urządzenia HoloLens i Surface Hub są teraz wyświetlane na liście urządzeń <!--1725868-->

Dodajemy obsługę wyświetlania urządzeń HoloLens i Surface Hub zarejestrowanych w usłudze Intune do aplikacji Portal firmy dla systemu Android.

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Obsługa zasad ochrony aplikacji usługi Intune w przeglądarce Edge dla urządzeń przenośnych <!-- 1817882 -->

Przeglądarka Microsoft Edge dla urządzeń przenośnych będzie obsługiwała zasady ochrony aplikacji zdefiniowane w usłudze Intune.

### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763-eeready--"></a>Użyj pełnej nazwy wyróżniającej jako podmiotu dla certyfikatu protokołu SCEP <!--2221763 eeready-->
Podczas tworzenia profilu certyfikatu SCEP należy wprowadzić nazwę podmiotu. Możliwe będzie użycie pełnej nazwy wyróżniającej jako podmiotu. W obszarze **Nazwa podmiotu** wybierz pozycję **Niestandardowa** i wprowadź wartość `CN={{OnPrem_Distinguished_Name}}`. Aby użyć zmiennej `{{OnPrem_Distinguished_Name}}`, zsynchronizuj atrybut użytkownika `onpremisesdistingishedname` z usługą Azure AD za pomocą narzędzia [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837-eeready--"></a>W przypadku urządzeń z systemem iOS co 15 minut jest wyświetlany monit o ustawienie numeru PIN <!--1550837 eeready-->
Po zastosowaniu zasad zgodności lub konfiguracji do urządzenia z systemem iOS użytkownikom będzie wyświetlany co 15 minut monit o ustawienie numeru PIN. Monity będą wyświetlane, dopóki numer PIN nie zostanie ustawiony.

### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983-eeready--"></a>Włączanie funkcji udostępniania kontaktów przy użyciu połączenia Bluetooth — Android for Work <!--1098983 eeready-->
Domyślnie system Android uniemożliwia synchronizowanie kontaktów z profilu służbowego z urządzeniami Bluetooth. W związku z tym kontakty profilu służbowego nie są wyświetlane w identyfikatorze dzwoniącego w przypadku urządzeń Bluetooth.

Dostępne będzie nowe ustawienie w obszarze **Android for Work** > **Ograniczenia dotyczące urządzeń** > **Ustawienia profilu służbowego**:
- Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth

Administrator usługi Intune może skonfigurować te ustawienia, aby włączyć udostępnianie. Jest to przydatne podczas parowania urządzenia z samochodowym urządzeniem Bluetooth, które w sposób bezobsługowy wyświetla identyfikator dzwoniącego. Po włączeniu tej funkcji kontakty profilu służbowego są wyświetlane. Jeśli funkcja nie zostanie włączona, kontakty profilu służbowego nie będą wyświetlane.

Dotyczy: urządzenia z systemem Android w wersji 6.0 i nowszych z profilem służbowym.

### <a name="schedule-your-automatic-updates---1805514---"></a>Planowanie aktualizacji automatycznych <!--1805514 -->

Usługa Intune zapewnia kontrolę nad instalowaniem aktualizacji automatycznych za pomocą [ustawień pierścienia aktualizacji systemu Windows](windows-update-for-business-configure.md). Możliwe będzie zaplanowanie cyklicznych aktualizacji, w tym tygodnia, dnia i godziny.

### <a name="disable-checks-on-device-restart---1805490---"></a>Wyłączenie testów po ponownym uruchomieniu urządzenia <!--1805490 -->

Usługa Intune zapewnia kontrolę nad [zarządzaniem aktualizacjami oprogramowania](windows-update-for-business-configure.md). Właściwość **Testy po ponownym uruchomieniu** zostanie dodana i będzie domyślnie włączona. Aby pominąć typowe testy przeprowadzane po ponownym uruchomieniu urządzenia (takie jak aktywni użytkownicy, poziom naładowania baterii itp.), wybierz pozycję **Pomiń**.

<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nowy wykres trendu niepowodzeń rejestracji i tabela z przyczynami niepowodzeń <!-- 1471783 -->

Na stronie przeglądu rejestracji będzie można wyświetlić trend niepowodzeń rejestracji i pięć najczęstszych przyczyn niepowodzeń. Klikając wykres lub tabelę, będzie można przejść do szczegółów, aby znaleźć porady dotyczące rozwiązywania problemów i sugestie dotyczące korygowania.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Dostosowywanie motywów aplikacji Portal firmy za pomocą kodów szesnastkowych <!--1049561 -->

Kolor motywów w aplikacjach Portal firmy będzie można dostosowywać przy użyciu kodów szesnastkowych. Po wprowadzeniu kodu szesnastkowego usługa Intune określi kolor tekstu, który zapewni najwyższy poziom kontrastu między tekstem a tłem, zgodnie ze [standardami WCAG 2.0](http://www.w3.org/TR/WCAG20). Podgląd koloru tekstu i logo firmy na tle wybranego koloru możesz wyświetlić, wybierając pozycję **Aplikacje mobilne** > **Portal firmy**.

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Nowe ustawienia funkcji Windows Defender Credential Guard dodane do ustawień programu Endpoint Protection <!--1102252 -->

Nowe ustawienia funkcji [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] zostaną dodane do obszaru **Konfiguracja urządzenia** > **Profile** > **Endpoint protection**. Zostaną dodane następujące ustawienia:

- Poziom zabezpieczeń platformy: określ, czy poziom zabezpieczeń platformy zostanie włączony przy następnym ponownym uruchomieniu. Zabezpieczenia oparte na wirtualizacji wymagają bezpiecznego rozruchu. Opcjonalnie zabezpieczenia oparte na wirtualizacji można włączyć przy użyciu ochrony bezpośredniego dostępu do pamięci (DMA, direct memory access). Ochrona DMA wymaga obsługi sprzętowej i będzie można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach.
- Zabezpieczenia oparte na wirtualizacji: określ, czy zabezpieczenia oparte na wirtualizacji zostaną włączone przy następnym ponownym uruchomieniu.
- Windows Defender Credential Guard: włącz funkcję Credential Guard z zabezpieczeniami opartymi na wirtualizacji, aby ułatwić zapewnienie ochrony poświadczeń, przy następnym ponownym uruchomieniu, gdy poziom zabezpieczeń platformy z bezpiecznym rozruchem i zabezpieczenia oparte na wirtualizacji są włączone. Dostępne opcje: **Wyłączone**, **Włączone z blokadą UEFI**, **Włączone bez blokady** i **Nieskonfigurowane**.
  - Opcja „Wyłączone” zdalnie wyłącza funkcję Credential Guard, jeśli została ona wcześniej włączona za pomocą opcji „Włączone bez blokady”.

  - Opcja „Włączone z blokadą UEFI” zapewnia, że funkcji Credential Guard nie będzie można wyłączyć za pomocą klucza rejestru ani przy użyciu zasad grupy. Aby wyłączyć funkcję Credential Guard po użyciu tego ustawienia, należy ustawić zasady grupy na opcję „Wyłączone” i usunąć funkcję zabezpieczeń z każdego komputera, gdy użytkownik jest fizycznie przy komputerze, w celu wyczyszczenia konfiguracji utrwalonej w interfejsie UEFI. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

  - Opcja „Włączone bez blokady” umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 (wersja 1511) lub nowszy.

  - Opcja „Nieskonfigurowane” pozostawia niezdefiniowane ustawienie zasad. Zasady grupy nie zapisują ustawienia zasad w rejestrze, więc nie ma ono wpływu na komputery ani użytkowników. Jeśli w rejestrze znajduje się bieżące ustawienie, nie zostanie ono zmodyfikowane.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetowanie haseł dla urządzeń z systemem Android O <!-- 1238299 -->
Będzie można resetować hasła zarejestrowanych urządzeń z systemem Android O. Po wysłaniu żądania „Resetuj hasło” do urządzenia z systemem Android O ustawi ono nowe hasło odblokowania urządzenia lub wezwanie zarządzanego profilu dla bieżącego użytkownika. Hasło lub wezwanie jest wysyłane w zależności od tego, czy urządzenie ma właściciela profilu, czy właściciela urządzenia, i zaczyna obowiązywać natychmiast.

### <a name="local-device-security-option-settings----1251887---"></a>Ustawienia opcji zabezpieczeń urządzenia lokalnego <!-- 1251887 -->
Na urządzeniach z systemem Windows 10 będzie można włączać ustawienia zabezpieczeń przy użyciu nowych ustawień opcji zabezpieczeń urządzenia lokalnego. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nowe ustawienia drukarek dla profili edukacyjnych <!-- 1308900 -->

W przypadku profili edukacyjnych będą dostępne nowe ustawienia w kategorii **Drukarki**: **Drukarki**, **Drukarka domyślna**, **Dodaj nowe drukarki**.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Konfiguracja aprowizacji aplikacji systemu iOS <!-- 1581650 -->
Aby zapobiec wygaśnięciu aplikacji, będzie można przypisywać profile aprowizacji aplikacji systemu iOS przez uwzględnienie lub wykluczenie grup zabezpieczeń.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nowe ustawienia funkcji Windows Defender Application Guard <!-- 1631890 -->

- **Włącz przyspieszanie grafiki**

Administratorzy będą mogli włączyć wirtualny procesor graficzny dla funkcji Windows Defender Application Guard. To ustawienie umożliwia procesorowi CPU przekazanie renderowania grafiki do procesora vGPU. Może to poprawić wydajność podczas pracy z witrynami internetowymi bogatymi w grafikę lub podczas oglądania filmu wideo znajdującego się w kontenerze.

- **SaveFilestoHost**

Administratorzy będą mogli włączyć przekazywanie plików z przeglądarki Microsoft Edge działającej w kontenerze do systemu plików hosta. Włączenie tej opcji pozwoli użytkownikom na pobieranie plików z przeglądarki Microsoft Edge w kontenerze do systemu plików hosta.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup dla programu Android Enterprise <!-- 1813081 -->
Podczas przypisywania aplikacji i po wybraniu typu przypisania program Android Enterprise (wcześniej znany jako Android for Work) będzie obsługiwać funkcję wykluczania.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Określanie zasad zgodności dla urządzeń w grupach urządzeń<!--1307012 -->

Możesz określać zasady zgodności dla użytkowników w grupach użytkowników. Możesz także określać zasady zgodności dla urządzeń w grupach urządzeń.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurowanie numeru PIN aplikacji dla systemu iOS <!-- 1586774 -->
Już wkrótce będzie można wymagać wprowadzenia numeru PIN dla aplikacji docelowych z systemem iOS. Wymaganie wprowadzenia numeru PIN i datę wygaśnięcia liczoną w dniach można skonfigurować za pośrednictwem witryny Azure Portal. W razie potrzeby będzie można narzucić wymaganie używania nowego numeru PIN w celu uzyskania dostępu do aplikacji dla systemu iOS. Ta funkcja będzie dostępna tylko dla aplikacji dla systemu iOS, dla których włączono ochronę aplikacji przy użyciu zestawu SDK aplikacji usługi Intune.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>Przekierowywanie użytkowników systemu macOS do nowej aplikacji Portal firmy <!--1380728-->   
Gdy użytkownik końcowy zaloguje się do witryny internetowej Portal firmy, aby zarejestrować swoje urządzenie z systemem macOS, w celu ukończenia procesu zostanie przekierowany na stronę pobierania nowej aplikacji Portal firmy dla systemu macOS. Dotyczy to urządzeń z systemem macOS w wersji OS X El Capitan 10.11 lub nowszym. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Ulepszony komunikat o błędzie, gdy użytkownik osiągnie maksymalną liczbę urządzeń, które można zarejestrować <!-- 1270370 -->
Zamiast ogólnego komunikatu o błędzie użytkownicy końcowi urządzeń z systemem Android zobaczą przyjazny komunikat o błędzie umożliwiający wykonanie akcji: „Zarejestrowano maksymalną liczbę urządzeń dozwoloną przez administratora IT. Usuń zarejestrowane urządzenie lub skontaktuj się z administratorem IT w celu uzyskania pomocy”.



## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.



### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
