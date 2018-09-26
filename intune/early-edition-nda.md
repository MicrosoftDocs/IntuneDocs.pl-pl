---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/4/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: beee1462c1b6e683287b4d304df386ce525be820
ms.sourcegitcommit: 8fdddb684ecf5eabf071907168413bcd89a2f702
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141647"
---
# <a name="the-early-edition-for-microsoft-intune---september-2018"></a>Wczesna wersja usługi Microsoft Intune — wrzesień 2018

> [!Note]
> Powiadomienie dotyczące umowy o zachowaniu poufności: dla usługi Intune opracowywane są następujące zmiany. Te informacje są udostępniane pod rygorem umowy o zachowaniu poufności w bardzo ograniczonym zakresie. Nie wolno publikować żadnych tych informacji w mediach społecznościowych ani w publicznych witrynach internetowych, takich jak Twitter, UserVoice, Reddit itd. 

**Wczesna wersja** zawiera listę funkcji udostępnianych w ramach umowy o zachowaniu poufności, które zostaną wprowadzone w przyszłych wydaniach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie publikuj tweetów, wpisów na platformie UserVoice ani w inny sposób nie udostępniaj tych informacji poza swoją firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1809 start -->

### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices-----1248496----"></a>Dostęp do konta użytkownika w przypadku aplikacji usługi Intune na zarządzanych urządzeniach z systemami Android i iOS <!-- ! 1248496  -->

Jako administrator usługi Microsoft Intune będziesz mieć możliwość kontrolowania kont użytkownika dodawanych do aplikacji Microsoft Office na urządzeniach zarządzanych. Będzie również można ograniczać dostęp tylko do dozwolonych kont użytkowników w organizacji oraz blokować konta osobiste na zarejestrowanych urządzeniach. 

### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10----1333668---"></a>Tworzenie sufiksów DNS w profilach konfiguracji sieci VPN na urządzeniach z systemem Windows 10 <!-- 1333668 -->
Podczas tworzenia profilu konfiguracji urządzenia sieci VPN (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** (platforma) > **VPN** (typ profilu)) wprowadzasz pewne ustawienia systemu DNS. Będziesz też mieć możliwość wprowadzenia wielu **sufiksów DNS** w usłudze Intune. Korzystając z sufiksów DNS, możesz wyszukać zasób sieciowy za pomocą jego krótkiej nazwy, zamiast w pełni kwalifikowanej nazwy domeny (FQDN). Ta aktualizacja umożliwia również zmianę kolejności sufiksów DNS w usłudze Intune.
Pole [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md#dns-settings) zawiera aktualnie ustawienia systemu DNS.
Dotyczy urządzeń z systemem Windows 10

### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Obsługa zawsze włączonej sieci VPN dla profilów roboczych systemu Android dla firm <!-- 1333705 -->
Będziesz mieć możliwość używania zawsze włączonych połączeń sieci VPN na urządzeniach z systemem Android dla firm dzięki zarządzanym profilom służbowym. Zawsze włączone połączenia sieci VPN pozostają aktywne lub są natychmiast przywracane, gdy użytkownik odblokuje urządzenie, gdy urządzenie uruchomi się ponownie lub gdy zmieni się sieć bezprzewodowa. Połączenie można również przenieść do trybu „blokady”, który powoduje zablokowanie całego ruchu sieciowego do momentu uaktywnienia połączenia sieci VPN.
Ustawienie zawsze włączonej sieci VPN będzie znajdować się w oknie ustawień **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**  >  **System Android dla firm** (platformy) > **Ograniczenia dotyczące urządzeń** w obszarze **Tylko profile robocze** (typ profilu) > **Łączność**. 

### <a name="outlook-for-ios-and-android-app-configuration-policy---1828527---"></a>Zasady konfiguracji aplikacji Outlook dla systemów iOS i Android <!--1828527 -->
Będziesz mieć możliwość utworzenia zasad aplikacji Outlook dla systemów iOS i Android w systemie iOS. Dodatkowe ustawienia konfiguracji będą dodawane po włączeniu w aplikacji Outlook dla systemów iOS i Android.

### <a name="remotely-lock-noncompliant-devices----2064495---"></a>Zdalne blokowanie niezgodnych urządzeń <!-- 2064495 -->
Gdy urządzenie jest niezgodne, będziesz mieć możliwość utworzenia akcji dotyczącej zasad zgodności, która zdalnie zablokuje urządzenie. W obszarze Intune > **Zgodność urządzenia** utwórz nowe zasady lub wybierz istniejące. Wybierz kolejno pozycje **Akcje dotyczące niezgodności** > **Dodaj** i wybierz opcję zdalnego blokowania urządzenia.
Obsługiwane na: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- System Windows Phone 8.1 lub nowszy 

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Ustawienia transferu danych aplikacji usługi Intune w urządzeniach z systemem iOS zarejestrowanych w oprogramowaniu MDM <!-- 2244713 -->
Będziesz mieć możliwość oddzielenia kontroli ustawień transferu danych aplikacji usługi Intune na urządzeniach z systemem iOS zarejestrowanych w oprogramowaniu MDM od określania tożsamości zarejestrowanego użytkownika. Administratorzy nieużywający narzędzia IntuneMAMUPN nie zaobserwują zmiany zachowania. Jeśli ta funkcja jest dostępna, administratorzy używający narzędzia IntuneMAMUPN do kontrolowania zachowania transferu danych na zarejestrowanych urządzeniach powinni przejrzeć nowe ustawienia i odpowiednio zaktualizować ustawienia aplikacji.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Używanie klucza wstępnego w profilu sieci Wi-Fi systemu Windows 10 <!-- 2662938 -->
Będziesz mieć możliwość użycia klucza wstępnego (PSK) z protokołem zabezpieczeń WPA/WPA2-Personal do uwierzytelniania profilu konfiguracji sieci Wi-Fi dla systemu Windows 10.
Obecnie trzeba zaimportować profil sieci Wi-Fi lub utworzyć profil niestandardowy, aby korzystać z klucza wstępnego. Obszar [Ustawienia sieci Wi-Fi dla systemu Windows 10](wi-fi-settings-windows.md) zawiera listę bieżących ustawień. 

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>Częstotliwość synchronizacji urządzeń rozwiązania Autopilot zwiększona do 12 godzin <!-- 2753673 -->
Urządzenia rozwiązania Autopilot będą synchronizowane co 12 godzin, zamiast co 24 godziny.

### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Stosowanie profilu rozwiązania Autopilot do zarejestrowanych urządzeń z systemem Windows 10, które nie zostały jeszcze zarejestrowane w rozwiązaniu Autopilot <!-- 1558983 -->
Profil rozwiązania Autopilot możesz zastosować do zarejestrowanych urządzeń z systemem Windows 10, które nie zostały jeszcze zarejestrowane w rozwiązaniu Autopilot. W profilu rozwiązania Autopilot wybierz opcję **Convert all targeted devices to Autopilot** (Konwertuj wszystkie wybrane urządzenia na potrzeby rozwiązania Autopilot), aby automatycznie rejestrować urządzenia bez rozwiązania Autopilot w usłudze wdrażania rozwiązania Autopilot. Przetwarzanie rejestracji może potrwać do 48 godzin. Jeśli urządzenie nie zostało zarejestrowane i je zresetowano, rozwiązanie Autopilot przeprowadzi jego aprowizację. 

### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564--"></a>Tworzenie i przypisywanie wielu profilów strony ze stanem rejestracji do grup usługi Azure AD <!-- 2526564-->
Będziesz mieć możliwość tworzenia i przypisywania wielu profilów strony ze stanem rejestracji do grup usługi Azure AAD.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Zmienianie nazwy węzła i aktualizacje strony docelowej usługi Intune <!--2867309 -->
Aktualizacje strony docelowej usługi Intune będą obejmować nowe i zmienione kafelki i wykresy służące do monitorowania, które poprawią jakość wizualizacji danych. Nazwa węzła **Aplikacje mobilne** zostanie zmieniona na **Aplikacje klienckie**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Zwiększony dostęp użytkowników końcowych przy użyciu aplikacji Portal firmy <!-- 772203 -->
Użytkownicy końcowi będą mogli uzyskiwać dostęp do kluczowych akcji dotyczących kont, takich jak resetowanie haseł oraz profil usługi AAD, z aplikacji Portal firmy.

### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Wystawianie certyfikatów protokołu SCEP dla urządzeń bez użytkowników <!-- 1744554 -->
Obecnie certyfikaty są wystawiane dla użytkowników. Będziesz mieć możliwość wystawiania certyfikatów protokołu SCEP dla urządzeń, w tym urządzeń bez użytkowników, takich jak kioski (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** (platforma) > **Certyfikat SCEP** (profil)). Inne aktualizacje to:
- Właściwość **Podmiot** w profilu SCEP jest teraz niestandardowym polem tekstowym i może zawierać nowe zmienne. 
- Właściwość **Alternatywna nazwa podmiotu (SAN)** w profilu SCEP ma teraz format tabeli i może zawierać nowe zmienne. W tabeli administrator może dodać atrybut i wypełnić wartość w niestandardowym polu tekstowym. Nazwa SAN będzie obsługiwać następujące atrybuty: 
  - systemem DNS,
  - Adres e-mail
  - UPN — te nowe zmienne można dodawać z tekstem statycznym w polu tekstowym wartości niestandardowej. Na przykład atrybut systemu DNS można dodać jako `DNS = {{AzureADDeviceId}}.domain.com`.
  > [!NOTE]
  > Nawiasy klamrowe, średniki i symbole potoku „{}; |” nie będą działać w tekście statycznym nazwy SAN. W nawiasy klamrowe należy ująć tylko jedną z nowych zmiennych certyfikatu urządzenia do zaakceptowania: `Subject` lub `Subject alternative name`. Nowe zmienne certyfikatu urządzenia:  
```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - Zmienna `{{FullyQualifiedDomainName}}` działa tylko w przypadku urządzeń z systemem Windows i urządzeń przyłączonych do domeny. 
>  -  Podczas określania właściwości urządzenia, takich jak numer IMEI, numer seryjny i w pełni kwalifikowana nazwa domeny w obrębie podmiotu lub nazwy SAN dla certyfikatu urządzenia, należy pamiętać, że te właściwości mogą zostać sfałszowane przez osobę z dostępem do urządzenia. 

Podczas tworzenia profilu konfiguracji protokołu w obszarze [Tworzenie profilu certyfikatu protokołu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) będą znajdować się bieżące zmienne. 

Dotyczy: system Windows 10 i nowsze oraz system iOS, obsługiwane w sieci Wi-Fi



<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token VPP firmy Apple używany przez inne rozwiązanie MDM <!-- 1488946 -->
Usługa Intune wykryje i wyświetli szczegółowe informacje, jeśli token programu VPP (Volume Purchase Program) jest używany zarówno przez usługę Intune, jak i inne rozwiązanie MDM.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>Numer wersji i numer kompilacji systemu iOS są wyświetlane <!-- 1892471 -->
W polu **Zgodność urządzenia** > **Zgodność urządzenia** jest wyświetlana wersja systemu operacyjnego iOS. W ramach przyszłej aktualizacji będzie także wyświetlany numer kompilacji.
Po wydaniu aktualizacji zabezpieczeń firma Apple zwykle pozostawia numer wersji bez zmian, lecz aktualizuje numer kompilacji. Wyświetlając numer kompilacji, można łatwo sprawdzić, czy aktualizacja luk w zabezpieczeniach została zainstalowana.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Wycofane urządzenia na pulpicie nawigacyjnym zgodności urządzeń <!-- 1981119 -->
W ramach przyszłej aktualizacji wycofane urządzenia zostaną usunięte z pulpitu nawigacyjnego zgodności urządzeń. Spowoduje to zmianę liczb dotyczących zgodności.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Zmiana w procesie aktualizacji łączników lokalnych <!-- 2277554 -->
Na podstawie opinii klientów zmienimy sposób aktualizacji łączników lokalnych. Po początkowej instalacji łącznika lokalnego aktualizacje będą wykonywane automatycznie. Ta zmiana rozpocznie się od nowego łącznika certyfikatów PFX usługi Microsoft Intune, a następnie będzie wdrażana dla innych typów łączników lokalnych. 

### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224-eeready---"></a>System Windows 10 i nowsze Ulepszenia profilu kiosku w witrynie Azure Portal <!-- 2748224 eeready -->
Profil konfiguracji urządzenia typu Kiosk systemu Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** (platforma) > **Kiosk (wersja zapoznawcza)** (typ profilu)) zostanie udoskonalony: 
- Obecnie w jednym urządzeniu można utworzyć wiele profilów kiosku. Dzięki tej aktualizacji usługa Intune będzie obsługiwać tylko jeden profil kiosku na urządzenie. Jeśli nadal potrzebujesz wielu profilów kiosku w jednym urządzeniu, możesz użyć niestandardowego identyfikatora URI.
W profilu **Kiosk z wieloma aplikacjami** można wybrać rozmiar kafelka aplikacji oraz porządek **układu menu Start** w siatce aplikacji. Jeśli wolisz szersze możliwości dostosowywania, możesz kontynuować przekazywanie pliku XML.
- Ustawienia przeglądarki kiosku są przenoszone do ustawień **kiosku**. Obecnie ustawienia **przeglądarki internetowej kiosku** mają własną kategorię w witrynie Azure Portal.
Dotyczy: system Windows 10 lub nowszy

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Ulepszone środowisko aplikacji Portal firmy dla użytkowników menedżera rejestracji urządzeń <!-- 675800 -->
Gdy menedżer rejestracji urządzeń loguje się do aplikacji Portal firmy dla systemu Windows, w aplikacji będzie wyświetlane tylko bieżące, uruchomione urządzenie menedżera rejestracji urządzeń. To ulepszenie ograniczy występowanie przekroczeń limitu czasu, które wcześniej miały miejsce, gdy aplikacja podejmowała próbę załadowania wszystkich urządzeń zarejestrowanych w menedżerze rejestracji urządzeń.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **System Windows 10**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP jest używany token programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Dodatkowe ustawienia zabezpieczeń dla Instalatora Windows <!-- 2282430 -->
Będziesz mieć możliwość zezwolenia użytkownikom na kontrolowanie instalacji aplikacji. Po włączeniu tej funkcji instalacje, które w przeciwnym razie mogły zostać zatrzymane z powodu naruszenia zabezpieczeń, będą kontynuowane. Będziesz mieć możliwość przekierowania Instalatora Windows tak, aby używał podwyższonego poziomu uprawnień podczas instalowania dowolnego programu w systemie. Ponadto możliwe będzie indeksowanie elementów funkcji Windows Information Protection (WIP) oraz przechowywanie związanych z nimi metadanych w niezaszyfrowanej lokalizacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie będą indeksowane i nie będą wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Funkcje tych opcji będą domyślnie wyłączone. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Klawiatury innych firm mogą zostać zablokowane przez ustawienia aplikacji w systemie iOS <!-- 1248481 -->
Na urządzeniach z systemem iOS administratorzy usługi Intune będą mogli zablokować możliwość korzystania z klawiatur innych firm podczas uzyskiwania dostępu do danych organizacji w aplikacjach chronionych przez zasady. Gdy zasady ochrony aplikacji są ustawione na blokowanie klawiatur innych firm, użytkownik urządzenia otrzyma komunikat podczas pierwszej próby interakcji z danymi firmowymi przy użyciu klawiatury innej firmy. Wszystkie opcje inne niż klawiatura macierzysta zostaną zablokowane, a użytkownicy urządzenia nie będą ich widzieć. Użytkownicy urządzenia zobaczą tylko raz komunikat w oknie dialogowym. 

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pakiety językowe usługi Office 365 Pro Plus <!-- 1833450 -->
Jako administrator usługi Intune będziesz mieć możliwość wdrożenia dodatkowych języków dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje mobilne** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w bloku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w bloku **Ustawienia pakietu aplikacji**.

<!-- 1805 start -->

### <a name="require-non-biometric-after-specified-timeout----1506985---"></a>Wymaganie danych niebiometrycznych po upłynięciu określonego limitu czasu <!-- 1506985 --> 

Wymagając niebiometrycznego kodu PIN po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) przez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia będą miały wpływ na użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia te umożliwią administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji** > **Dodaj zasadę** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień.

<!-- 1803 start -->

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android zostanie zaktualizowane, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy aplikacja Portal firmy dla systemu Android zostanie zaktualizowana, aby podzielić element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



