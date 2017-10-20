---
title: Wczesna wersja
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: abb5612545174e3fd134c38fb763e02d379b50d0
ms.sourcegitcommit: b330045a4f9a807e6e2772c4ed4e1e1148e1f1f9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>Wersja wczesna usługi Microsoft Intune — październik 2017

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

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Rozwiązywanie problemów z rejestracją <!--- 746324 --->  
Problemy z rejestracją będą widoczne dla użytkownika w obszarze roboczym Rozwiązywanie problemów. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratorzy mogą teraz konfigurować ustawienia zapory na urządzeniu za pomocą profilu konfiguracji urządzenia <!-- 951708 -->   
Administratorzy mogą włączać zaporę dla urządzeń, a także konfigurować różne protokoły dla domeny oraz sieci prywatnych i publicznych.  Ustawienia zapory można znaleźć w profilu „Ochrona punktów końcowych”.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Funkcja Windows Defender Application Guard ułatwia ochronę urządzeń przed niezaufanymi witrynami w sposób zdefiniowany przez Twoją organizację <!-- 958257 -->   
Używając przepływu pracy funkcji Windows Information Protection lub nowego profilu „Granica sieci” w konfiguracjach urządzeń, administratorzy mogą definiować witryny jako „zaufane” lub „firmowe”. Wszystkie witryny wyświetlane w przeglądarce Microsoft Edge, które nie znajdują się w granicach zaufanej sieci na urządzeniu z 64-bitowym systemem Windows 10, są otwierane w przeglądarce na komputerze wirtualnym funkcji Hyper-V.

Funkcję Application Guard można znaleźć w profilach konfiguracji urządzeń w profilu „Ochrona punktów końcowych”. W tym miejscu administratorzy mogą skonfigurować interakcję między zwirtualizowaną przeglądarką a komputerem hosta, zaufanymi i niezaufanymi witrynami oraz danymi magazynowania generowanymi w zwirtualizowanej przeglądarce. Aby można było używać funkcji Application Guard na urządzeniu, najpierw należy skonfigurować granicę sieci. Dla jednego urządzenia należy określić tylko jedną granicę sieci.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Funkcja Windows Defender Application Guard w systemie Windows 10 Enterprise udostępnia tryb ufania tylko autoryzowanym aplikacjom <!-- 1031096 -->    
Tysiące nowych, złośliwych plików tworzonych każdego dnia powodują, że walka ze złośliwym oprogramowaniem przy użyciu wykrywania wirusów w oparciu o ich sygnatury może nie zapewniać już odpowiedniej obrony przed nowymi atakami. Korzystając z funkcji Windows Defender Application Guard w systemie Windows 10 Enterprise, można zmienić konfigurację urządzenia z trybu, w którym aplikacje są zaufane, dopóki nie zostaną zablokowane przez program antywirusowy lub inne rozwiązanie z zakresu zabezpieczeń, na tryb, w którym system operacyjny ufa tylko aplikacjom autoryzowanym przez przedsiębiorstwo. Zaufanie do aplikacji można przypisać za pomocą funkcji Windows Defender Application Guard.

Korzystając z usługi Intune, można skonfigurować zasady kontroli aplikacji w trybie „tylko do inspekcji” lub w trybie wymuszania. Aplikacje działające w trybie „tylko do inspekcji” nie będą blokowane. Tryb „tylko do inspekcji” rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta. Można również określić, czy mogą być uruchamiane wyłącznie składniki systemu Windows i aplikacje ze Sklepu Windows, czy również inne aplikacje o dobrej reputacji zdefiniowane przez usługę Intelligent Security Graph.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nowa strona stanu rejestracji dla rejestracji systemu Windows 10 <!--1063201-->    
Teraz można skonfigurować powitanie, które jest wyświetlane, gdy użytkownicy rejestrują urządzenia z systemem Windows 10. Na **ekranie stanu rejestracji** można skonfigurować niestandardowy komunikat i hiperlink, które będą wyświetlane użytkownikom końcowym podczas rejestrowania ich urządzeń z systemem Windows 10.  **Ekran stanu rejestracji** zapewni również użytkownikom końcowym widok postępu ustawień zasad stosowanych do ich urządzeń.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard to nowy zestaw funkcji zapobiegania nieautoryzowanemu dostępowi do systemu Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard zawiera reguły niestandardowe, które ograniczają podatność aplikacji na wykorzystanie luk w zabezpieczeniach, zapobiega zagrożeniom w makrach i skryptach, automatycznie blokuje połączenia sieciowe z adresami IP o niskiej reputacji, a także umożliwia zabezpieczenie danych przed oprogramowaniem wymuszającym okup i nieznanymi zagrożeniami. Windows Defender Exploit Guard obejmuje następujące składniki:

- **Attack Surface Reduction (ASR)** zawiera reguły, które pozwalają zapobiegać zagrożeniom występującym w makrach, skryptach i wiadomościach e-mail.
- **Controlled Folder Access** automatycznie blokuje dostęp do zawartości do folderów chronionych.
- **Network Filter** blokuje połączenie wychodzące z dowolnej aplikacji do adresu IP/domeny o niskiej reputacji.
- **Exploit Protection** zapewnia ograniczenia pamięci, przepływu sterowania i zasad, które umożliwiają ochronę aplikacji przed lukami w zabezpieczeniach.

### <a name="app-conditional-launch-support----1193313---"></a>Obsługa uruchamiania warunkowego aplikacji <!-- 1193313 -->
Administratorzy IT mogą teraz określić za pośrednictwem portalu administracyjnego platformy Azure wymaganie, aby podczas uruchamiania aplikacji było wymuszane wprowadzenie hasła, zamiast wprowadzania kodu liczbowego PIN za pośrednictwem funkcji zarządzania aplikacjami mobilnymi (MAM). W przypadku skonfigurowania tej opcji użytkownik będzie musiał określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. W tej wersji usługi Intune ta funkcja jest dostępna **tylko w systemie iOS**. Usługa Intune obsługuje hasło w podobny sposób jak kod liczbowy PIN — określa minimalną długość, umożliwiając powtarzanie znaków i sekwencji. Ta funkcja wymaga udziału aplikacji (tj. WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu SDK aplikacji Intune. Kod dla tej funkcji zastępuje ustawienia hasła, które mają być wymuszane w aplikacji docelowej.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numery wersji aplikacji biznesowych w raporcie o stanie instalacji urządzenia <!-- 1233999 -->  
W raporcie o stanie instalacji urządzenia będą wyświetlane numery wersji aplikacji biznesowych dla systemów iOS i Android. Korzystając z tych informacji, można rozwiązywać problemy z aplikacjami lub znajdować urządzenia z nieaktualnymi wersjami aplikacji.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Współzarządzanie dla urządzeń z systemem Windows 10 <!-- 124445 -->
Współzarządzanie to rozwiązanie, które łączy zarządzanie tradycyjne z nowoczesnym i udostępnia ścieżkę umożliwiającą wprowadzanie zmian przy użyciu podejścia etapowego. Zasadniczo współzarządzanie jest rozwiązaniem, w którym urządzenia z systemem Windows 10 są jednocześnie zarządzane przez program Configuration Manager i usługę Microsoft Intune, a także połączone z usługami Active Directory (AD) i Azure Active Directory (Azure AD).  Taka konfiguracja umożliwia przyszłą modernizację w tempie odpowiednim dla organizacji, jeśli nie można przenieść wszystkiego naraz.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Ustawianie dostępu dla aplikacji według minimalnego poziomu poprawki zabezpieczeń systemu Android na urządzeniu<!-- 1278463 -->   
Administrator będzie mógł zdefiniować minimalny poziom poprawki zabezpieczeń systemu Android, który musi być zainstalowany na urządzeniu, aby można było uzyskać dostęp do aplikacji zarządzanej na koncie zarządzanym.

> [!Note]  
> Ta funkcja ogranicza poprawki zabezpieczeń opublikowane przez firmę Google wyłącznie na urządzeniach z systemem Android 6.0 lub nowszym.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nowe ustawienia ograniczeń urządzeń z systemem Windows 10      <!-- 1308850 -->
-    Wiadomości (tylko dla urządzeń przenośnych) — wyłączenie testowania lub wiadomości MMS
-    Hasło — ustawienia umożliwiające włączanie standardu FIPS i uwierzytelnianie za pomocą dodatkowych urządzeń z usługą Windows Hello 
-    Ekran — ustawienia umożliwiające włączanie i wyłączanie skalowania graficznego interfejsu użytkownika dla starszych aplikacji


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Ograniczenia urządzeń z systemem Windows 10 do trybu kiosku <!-- 1308872 -->   
Będzie możliwe ograniczanie użytkowników urządzeń z systemem Windows 10 do trybu kiosku, który ogranicza użytkownikom dostęp tylko do zestawu wstępnie zdefiniowanych aplikacji.  Aby to zrobić, należy utworzyć profil ograniczenia urządzenia z systemem Windows 10 i określić ustawienia kiosku.

Tryb kiosku obsługuje dwa tryby: **pojedynczej aplikacji** (pozwala użytkownikowi na uruchomienie tylko jednej aplikacji) lub **wielu aplikacji** (zezwala na dostęp do zestawu aplikacji).  Aby określić obsługiwane aplikacje, należy zdefiniować konto użytkownika i nazwę urządzenia.  Zalogowany użytkownik ma dostęp ograniczony do zdefiniowanych aplikacji.  Aby dowiedzieć się więcej, zobacz [AssignedAccess CSP (Dostawca usługi konfiguracji AssignedAccess)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Wymagania trybu kiosku:

- Usługa Intune musi być urzędem zarządzania urządzeniami przenośnymi.
- Aplikacje muszą być już zainstalowane na urządzeniu docelowym.
- Urządzenie musi być [poprawnie udostępniane](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nowy profil konfiguracji urządzeń do tworzenia granic sieci <!-- 1311967 -->   
Utworzyliśmy profil konfiguracji urządzeń o nazwie **Granica sieci**, który można znaleźć wśród innych profilów konfiguracji urządzeń. Ten profil umożliwia zdefiniowanie zasobów online, które mają być uważane za firmowe i zaufane. Granicę sieci dla urządzenia należy zdefiniować *przed* użyciem na urządzeniu funkcji takich jak Windows Defender Application Guard i Windows Information Protection. Dla każdego urządzenia należy określić tylko jedną granicę sieci.

Jako zasoby, które mają zostać uznane za zaufane, można zdefiniować zasoby chmury przedsiębiorstwa, zakresy adresów IP i wewnętrzne serwery proxy. Zdefiniowana granica sieci może być używana przez inne funkcje, takie jak Windows Defender Application Guard i Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Dwa dodatkowe ustawienia usługi Windows Defender Antivirus <!-- 1338409 -->  
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


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Obsługa urzędu certyfikacji (CA) Symantec Cloud <!-- 1333638 -->    
Usługa Intune obsługuje teraz urząd certyfikacji Symantec Cloud, co pozwala łącznikowi Intune Certificate Connector na wystawianie certyfikatów PKCS z urzędu certyfikacji Symantec Cloud dla urządzeń zarządzanych przez usługę Intune. Jeśli łącznik Intune Certificate Connector jest już używany z urzędem certyfikacji (CA) Microsoft, można wykorzystać istniejącą konfigurację łącznika Intune Certificate Connector w celu dodania obsługi urzędu certyfikacji Symantec.


### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w Portalu firmy <!--1490692-->  
Ulepszamy przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android. Język będzie bardziej przyjazny dla użytkownika i specyficzny dla firmy, a w miarę możliwości ekrany będą połączone. 

### <a name="block-unsupported-samsung-knox-device-activation------1490695----"></a>Blokowanie nieobsługiwanej aktywacji urządzenia z systemem Samsung Knox <!--- 1490695 --->  
Aplikacja Portal firmy próbuje uaktywnić system Samsung KNOX podczas rejestracji w systemie MDM tylko wtedy, gdy urządzenie znajduje się na [liście obsługiwanych urządzeń z systemem KNOX](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Dzięki temu ograniczeniu można uniknąć błędów aktywacji systemu KNOX, które uniemożliwiają rejestrację w systemie MDM. Urządzenia, które nie obsługują aktywacji systemu Samsung KNOX, są rejestrowane jako standardowe urządzenia z systemem Android. Urządzenia firmy Samsung mogą mieć pewne numery modelu, które obsługują system KNOX, podczas gdy inne go nie obsługują. Przed zakupem i wdrożeniem urządzeń firmy Samsung należy sprawdzić zgodność systemu Knox u odsprzedawcy urządzenia.

Poniższa lista modeli zawiera urządzenia firmy Samsung, które nie obsługują systemu KNOX i są rejestrowane jako urządzenia z natywnym systemem Android przez aplikację Portal firmy dla systemu Android:

| **Nazwa urządzenia** | **Numery modelu urządzenia** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Dodano sieć VPN Citrix dla urządzeń z systemem Windows 10 <!-- 1512457 -->  
Klient będzie mógł skonfigurować sieć VPN Citrix dla swoich urządzeń z systemem Windows 10. Sieć VPN Citrix można wybrać na liście *Wybierz typ połączenia* w bloku **Podstawowa sieć VPN** podczas konfigurowania sieci VPN dla systemu Windows 10 i nowszych.

> [!Note]
> Konfiguracja serwera Citrix istniała dla systemów iOS i Android.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720  -->  
Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet.  Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania. Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play.  Dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy, jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uniemożliwianie użytkownikom urządzeń z systemem Android zmiany daty i godziny ich urządzeń <!-- 1333292 -->
Można użyć [niestandardowych zasad urządzeń z systemem Android](custom-settings-android.md), aby uniemożliwić użytkownikom urządzeń z systemem Android zmianę daty i godziny urządzenia.
W tym celu należy skonfigurować niestandardowe zasady systemu Android, korzystając z identyfikatora URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange, wybrać dla niego wartość **TRUE**, a następnie przypisać go do wymaganych grup.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Wyświetlanie przypisań zasad ochrony aplikacji w celu rozwiązywania problemów <!--  1475003 -->
W nadchodzącym wydaniu opcja **zasad ochrony aplikacji** zostanie dodana do listy rozwijanej **Przypisania** dostępnej w bloku rozwiązywania problemów. Teraz możesz wybrać zasady ochrony aplikacji, aby wyświetlić zasady ochrony aplikacji przypisane do wybranych użytkowników.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Tworzenie aplikacji dla systemu iOS ograniczonych do określonych regionalnych sklepów Apple App Store <!-- 1281692 -->
Podczas tworzenia zarządzanej aplikacji przeznaczonej do sklepu Apple App Store można określić ustawienia regionalne dla kraju.

> [!NOTE]  
> Obecnie można tworzyć wyłącznie zarządzane aplikacje dla sklepu Apple App Store dostępne w amerykańskiej wersji strony sklepu.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Wybór krajowego sklepu Apple do synchronizacji aplikacji VPP <!-- 1332311 -->  
Podczas przekazywania tokenu programu VPP będzie można skonfigurować krajowy sklep do obsługi programu zakupów zbiorczych (VPP, ang. Volume Purchase Program). Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.

> [!NOTE]  
> Obecnie usługa Intune synchronizuje tylko aplikacje VPP z krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnego z ustawieniami regionalnymi usługi Intune dla lokalizacji, w której została utworzona dzierżawa usługi Intune.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizacja aplikacji VPP dla systemu iOS z licencją użytkownika i urządzenia <!-- 1305564 -->  
Można skonfigurować token programu VPP systemu iOS pod kątem aktualizacji wszystkich aplikacji zakupionych dla danego tokenu za pośrednictwem usługi Intune. Usługa Intune wykryje aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypchnie je do urządzenia po jego zaewidencjonowaniu.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 Team <!--- 1308838  -->
Dodajemy wiele nowych ustawień profilu ograniczeń urządzenia z systemem Windows 10 Team ułatwiających kontrolę urządzeń Surface Hub.
Aby uzyskać więcej informacji o tym profilu, zobacz artykuł [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md) (Ustawienia ograniczeń urządzenia z systemem Windows 10 Team).

### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10 <!-- 903672(archived), 1119689 -->  
Można utworzyć zasady uaktualniania wydania systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wydania systemu Windows 10, zobacz artykuł [How to configure Windows 10 edition upgrades (Jak skonfigurować uaktualnienia wydania systemu Windows 10)](edition-upgrade-configure-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Zdalna pomoc techniczna dla urządzeń z systemem Windows i Windows Mobile <!-- 1070473 -->    
Usługa Intune będzie umożliwiać korzystanie z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Windows i Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Skanowanie urządzeń z użyciem usługi Windows Defender <!-- 1280988  1280990   -->
Na zarządzanych urządzeniach z systemem Windows 10 możliwe będzie uruchomienie **szybkiego skanowania** i **pełnego skanowania** oraz przeprowadzenie **aktualizacji sygnatur** z użyciem programu antywirusowego Windows Defender. W bloku przeglądu urządzenia wybierz akcję do przeprowadzenia na urządzeniu. Przed wysłaniem polecenia do urządzenia zostanie wyświetlony monit o potwierdzenie akcji. 

**Szybkie skanowanie**: szybkie skanowanie obejmuje lokalizacje, w których złośliwe oprogramowanie rejestruje się w celu umożliwienia jego uruchomienia, np. klucze rejestru i znane foldery uruchamiania systemu Windows. Szybkie skanowanie trwa średnio pięć minut. W połączeniu z ustawieniem **zawsze włączonej ochrony w czasie rzeczywistym**, które skanuje pliki, gdy są one otwierane i zamykane, a także za każdym razem, gdy użytkownik przejdzie do folderu, szybkie skanowanie pomaga chronić przed złośliwym oprogramowaniem, które może być obecne w systemie lub w jądrze. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Pełne skanowanie**: pełne skanowanie przydaje się w przypadku urządzeń, w których wystąpiło zagrożenie związane ze złośliwym oprogramowaniem, ponieważ pozwala określić, czy istnieją nieaktywne składniki, które wymagają dokładniejszego czyszczenia; funkcja umożliwia także uruchamianie skanowania na żądanie. Pełne skanowanie może trwać godzinę. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Zaktualizuj sygnatury**: polecenie aktualizacji sygnatur powoduje aktualizację definicji i sygnatur złośliwego oprogramowania programu antywirusowego Windows Defender. Można w ten sposób upewnić się, że program antywirusowy Windows Defender skutecznie wykrywa złośliwe oprogramowanie. Ta funkcja jest dostępna wyłącznie dla urządzeń z systemem Windows 10 i wymaga połączenia z Internetem. 

### <a name="bitlocker-device-configuration----1397398---"></a>Konfiguracja urządzenia z użyciem funkcji BitLocker <!-- 1397398 -->  
Wybierając kolejno **Szyfrowanie systemu Windows > Ustawienia podstawowe**, można uzyskać dostęp do nowego ustawienia **Ostrzeżenie dotyczące innego szyfrowania dysku**, które pozwala wyłączyć [monit ostrzegawczy](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) dotyczący innego szyfrowania, które mogło zostać użyte na urządzeniu użytkownika.  Przed rozpoczęciem konfiguracji funkcji BitLocker na urządzeniu zostanie wyświetlony monit ostrzegawczy wymagający zgody użytkownika; konfiguracja funkcji BitLocker będzie blokowana do czasu potwierdzenia przez użytkownika końcowego.  Nowe ustawienie wyłącza ostrzeżenie użytkownika końcowego.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Utrzymanie aplikacji Portal firmy w systemach Windows 8.1 i Windows Phone 8.1 <!--1428681-->
Począwszy od października 2017 roku aplikacje Portal firmy zostaną utrzymane w systemach Windows 8.1 i Windows Phone 8.1. Oznacza to, że aplikacje i istniejące scenariusze, np. scenariusze rejestracji i zgodności, będą nadal obsługiwane przez te platformy. Aplikacje te będą nadal dostępne do pobrania za pośrednictwem istniejących kanałów, takich jak Sklep Microsoft. 

Po zatwierdzeniu utrzymania tych aplikacji będą dla nich udostępniane wyłącznie krytyczne aktualizacje zabezpieczeń. Nie będzie dla nich żadnych dodatkowych aktualizacji i nie będą w nich udostępniane żadne nowe funkcje. W celu skorzystania z nowych funkcji zalecamy aktualizację urządzenia do systemu Windows 10 lub Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokowanie kopiowania i wklejania między profilami służbowymi i osobistymi w aplikacji Android for Work <!-- 1098994 -->   
Profil służbowy w programie Android for Work będzie można skonfigurować w taki sposób, aby kopiowanie i wklejanie danych między aplikacjami służbowymi i osobistymi było blokowane. To nowe ustawienie można znaleźć w profilu **Ograniczenia urządzenia** platformy **Android for Work** w obszarze **Ustawienia profilu służbowego**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nowe zachowanie aplikacji Portal firmy dla systemu Android z profilami służbowymi <!---1485783--->
Po zarejestrowaniu urządzenia z programem Android for Work i z profilem służbowym to właśnie aplikacja Portal firmy w profilu służbowym wykonuje na urządzeniu zadania z zakresu zarządzania. Jeśli użytkownik nie korzysta w profilu osobistym z aplikacji z obsługą zasad zarządzania aplikacjami mobilnymi (MAM), aplikacja Portal firmy dla systemu Android nie pełni już żadnej roli. Aby ulepszyć środowisko pracy w profilu służbowym, po pomyślnej rejestracji profilu służbowego usługa Intune automatycznie ukrywa aplikację Portal firmy z profilu osobistego.

Aplikację Portal firmy dla systemu Android można w dowolnym momencie włączyć w profilu osobistym, wybierając [aplikację Portal firmy w Sklepie Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) i wybierając opcję **Włącz**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Zarządzanie aplikacjami mobilnymi usługi Intune i dodatki dla aplikacji Outlook dla systemu Android <!-- 1450688 -->
W ciągu kilku tygodni zespół Office ogłosi dodatki dla programu Outlook dla systemu Android. Wspomniany zestaw dodatków istnieje już w programie Outlook w systemach Windows i iOS, w aplikacji Outlook Web App oraz w aplikacji dla komputerów Mac. Ponieważ dodatki są zarządzane przez program Exchange, użytkownicy otrzymają możliwość kopiowania i udostępniania danych i wiadomości między programem Outlook i niezarządzanymi aplikacjami zgodnymi z dodatkami, chyba że dostęp do dodatków zostanie wyłączony przez administratora programu Exchange. 

Aby zarządzać uprawnieniami użytkowników w zakresie dostępu do dodatków, skontaktuj się z administratorem programu Exchange i upewnij się, że zasady ochrony danych funkcji MAM mają zastosowanie do dodatków.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli obowiązujące zasady programu Exchange zostały już skonfigurowane pod kątem uniemożliwienia ładowania bezpośredniego dodatków lub ich instalowania, lektura reszty tego artykułu mija się z celem. Zasady zarządzania aplikacjami mobilnymi będą stosowane zgodnie z wybranymi ustawieniami. Należy jednak pamiętać, że jeśli zasady funkcji MAM zostały skonfigurowane pod kątem ograniczenia operacji wycinania, kopiowania i wklejania danych w programie Outlook dla systemu Android, a w programie Exchange nie ustawiono zasad dotyczących dodatków, domyślne ustawienie będzie umożliwiać użytkownikom instalowanie dodatków programu Outlook. Dodatki te mają dostęp do treści, tematu i innych właściwości wiadomości. Możliwość instalowania dodatków przez użytkownika można wyłączyć. Aby to zrobić, administrator programu Exchange musi usunąć role „Moje aplikacje z portalu Marketplace” i „Moje aplikacje niestandardowe”.

Zmiana ustawienia w programie Exchange ma zastosowanie do programu Outlook dla systemu Windows i iOS, aplikacji Outlook Web App, aplikacji dla komputerów Mac i dla urządzeń przenośnych. 

#### <a name="what-do-i-need-to-do"></a>Co mam zrobić?
Już dzisiaj przejrzyj zasady programu Exchange. Poinformuj personel działu IT i pracowników pomocy technicznej. Zwróć się do naszego zespołu pomocy technicznej ze wszelkimi konkretnymi pytaniami i wątpliwościami. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->
Będzie można tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta.




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Akcje w przypadku niezgodności <!--730266  846515 -->     
*Akcje w przypadku niezgodności* to nowa funkcja zasad zgodności, która umożliwia podejmowanie akcji na urządzeniach, które są niezgodne. Możesz określić jedną lub wiele akcji oraz przedział czasu, w którym te akcje muszą zostać wykonane. Na przykład możesz za pomocą poczty e-mail powiadomić użytkowników niezgodnych urządzeń, gdy tylko ich urządzenia staną się niezgodne, lub za pośrednictwem dostępu warunkowego zablokować niezgodnym urządzeniom dostęp do zasobów firmowych po 3-dniowym okresie karencji.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nowy raport, który zawiera listę urządzeń dla systemu iOS ze starszymi wersjami systemu iOS   <!-- 1352223 -->
Raport **Nieaktualne urządzenia z systemem iOS** będzie dostępny z poziomu obszaru roboczego **Aktualizacje oprogramowania**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS i które mają dostępne aktualizacje. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10
<!--- 978575, 1308849, -->
Dodajemy nowe ustawienia do profilu ograniczeń urządzenia z systemem Windows 10 w kategorii Windows Defender SmartScreen.

Aby uzyskać szczegółowe informacje o profilu ograniczeń urządzenia z systemem Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Obsługa programu Android for Work dla usługi Lookout <!-- 1087312 -->   
Łącznik usługi Intune z usługą Lookout będzie obsługiwać urządzenia z programem Android for Work w przypadku korzystania z aplikacji Lookout for Work. Można wdrożyć aplikację Lookout wewnątrz lub na zewnątrz kontenera.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Narzędzia deweloperskie usług Intune App Protection i Citrix MDX <!-- 709185 -->
Urządzeniami i aplikacjami można zarządzać przy użyciu kombinacji usług Citrix XenMobile MDX i Microsoft Intune. Umożliwia ona zarządzanie aplikacjami za pomocą zasad usługi Intune App Protection przy równoczesnym wykorzystaniu technologii mVPN firmy Citrix.

Możesz odnaleźć repozytorium kodu, które zawiera narzędzie opakowujące aplikacje usługi Intune i zestawu Intune App SDK dla systemu iOS i Android zintegrowane z technologią mVPN Citrix MDX.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium — nowy partner usługi Mobile Threat Defense <!-- 954681 -->
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune?
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->   
Można mieć wiele ról serwera dostępu klienta (CAS) dla łącznika lokalnego programu Exchange. Jeśli na przykład główny serwer dostępu klienta ulegnie awarii, łącznik programu Exchange odbierze zapytanie w celu powrotu do innych serwerów dostępu klienta. Ta funkcja pozwala zagwarantować nieprzerwane działanie usługi.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->   
Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange będzie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Ten pakiet administracyjny zapewnia różne sposoby monitorowania usługi Intune w przypadku konieczności rozwiązywania problemów.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!---1171127, 1326920 --->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane przed początkiem października, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.


## <a name="intune-apps"></a>Aplikacje usługi Intune

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Ulepszone wskazówki dotyczące żądania dostępu do kontaktów na urządzeniach z systemem Android <!--1484985-->   
Aplikacja Portal firmy dla systemu Android często wymaga od użytkownika końcowego zaakceptowania uprawnień do kontaktów. Jeśli użytkownik końcowy odmówi dostępu, zobaczy w aplikacji powiadomienie z alertem dotyczącym przyznania aplikacji dostępu warunkowego.

### <a name="secure-startup-remediation-for-android---1490712--"></a>Korygowanie bezpiecznego uruchamiania dla systemu Android <!--1490712-->     
Użytkownicy końcowi mający urządzenia z systemem Android będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem.


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Przekierowywanie użytkowników systemu macOS do naszej nowej aplikacji Portal firmy <!--1380728-->   
Gdy użytkownik końcowy zaloguje się do witryny internetowej Portal firmy, aby zarejestrować swoje urządzenie z systemem macOS, w celu ukończenia procesu zostanie przekierowany na stronę pobierania nowej aplikacji Portal firmy dla systemu macOS. Dotyczy to urządzeń z systemem macOS w wersji OS X El Capitan 10.11 lub nowszym. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Obsługa uwierzytelniania opartego na certyfikatach w Portalu firmy dla systemu iOS <!--1029830-->
W aplikacji Portal firmy dla systemu iOS dodaliśmy obsługę uwierzytelniania opartego na certyfikatach (CBA). Użytkownicy korzystający z uwierzytelniania CBA wprowadzają swoją nazwę użytkownika, a następnie wybierają link „Zaloguj się przy użyciu certyfikatu”. Uwierzytelnianie CBA jest już obsługiwane w aplikacji Portal firmy dla systemów Android i Windows. Więcej informacji na ten temat można znaleźć na stronie [logowania się w aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->

### <a name="search-improvements-to-the-company-portal-website---1331697--"></a>Ulepszenia wyszukiwania w witrynie internetowej Portal firmy <!--1331697-->  
Ulepszyliśmy możliwości wyszukiwania naszych aplikacji, zaczynając od [witryny internetowej Portal firmy](https://portal.manage.microsoft.com). Wyszukiwanie będzie teraz przeprowadzane dodatkowo według kategorii aplikacji, a nie tylko pól nazwy i opisu. Wyniki będą domyślnie posortowane malejąco według zgodności. 

Użytkownicy systemu iOS również skorzystają z tej zmiany, ponieważ witryna internetowa Portal firmy jest też używana jako część aplikacji Portal firmy dla systemu iOS. Aplikacje Portal firmy dla systemów Android i Windows otrzymają analogiczne aktualizacje w najbliższych miesiącach.

Nadal dostrajamy sposób śledzenia zgodności, więc prosimy o informacje, jak to działa (link „Opinia” u dołu witryny internetowej Portal firmy).

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Dodanie akcji odświeżenia do aplikacji Portal firmy dla systemu Windows 10 <!--1132468-->  
Aplikacja Portal firmy dla systemu Windows 10 pozwoli użytkownikom odświeżać dane w aplikacji poprzez przeciągnięcie ekranu lub — w przypadku komputerów — naciśnięcie klawisza F5.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikacje dostępne z rejestracją lub bez rejestracji można teraz instalować bez monitów o rejestrację. <!-- 1334712 -->
Aplikacje firmowe, które udostępniono z rejestracją lub bez rejestracji w aplikacji Portal firmy dla systemu Android, można zainstalować bez monitu o rejestrację.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Wyświetlanie dużych ikon w aplikacji Portal firmy dla systemu iOS <!-- 1454593 -->
Naprawiamy znany problem ze sposobem wyświetlania ikon aplikacji Portal firmy dla systemu iOS na kafelku aplikacji. Przesłane ikony aplikacji o rozmiarach 120 x 120 pikseli lub większe są teraz wyświetlane w [witrynie sieci Web portalu firmy] (https://portal.manage.microsoft.com) i na stronie aplikacji Portal firmy dla systemu iOS w pełnym rozmiarze kafelka aplikacji.

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Obsługa aplikacji Intune Managed Browser dla systemu iOS i Android <!-- 1374196 -->
Od października 2017 r. aplikacja Intune Managed Browser w aplikacji dla systemu Android będzie obsługiwać tylko urządzenia z systemem Android 4.4 lub nowszym. Aplikacja Intune Managed Browser dla systemu iOS będzie obsługiwać wyłącznie urządzenia z systemem iOS 9.0 i nowszym. Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Ulepszony komunikat o błędzie, gdy użytkownik osiągnie maksymalną liczbę urządzeń, które można zarejestrować <!-- 1270370 -->
Zamiast ogólnego komunikatu o błędzie, użytkownicy końcowi widzą przyjazny komunikat o błędzie z akcjami: „Zarejestrowano maksymalną liczbę urządzeń dozwoloną przez administratora IT. Usuń zarejestrowane urządzenie lub skontaktuj się z administratorem IT w celu uzyskania pomocy”.




## <a name="notices"></a>Uwagi

### <a name="device-and-app-management-integration----677972---"></a>Integracja zarządzania urządzeniami i aplikacjami <!-- 677972 -->   
Teraz, gdy funkcje zarządzania urządzeniami przenośnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM) usługi Intune są już dostępne w witrynie Azure Portal, usługa Intune rozpoczęła integrowanie środowiska pracy administratora IT wokół zarządzania aplikacjami i urządzeniami. Zmiany mają na celu uproszczenie środowiska zarządzania urządzeniami i aplikacjami.

Dowiedz się więcej na temat zmian funkcji MDM i MAM ogłoszonych w [blogu zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->   
Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.


### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nowa ścieżka dla urządzeń zarządzanych w interfejsie API programu Graph <!-- 1586728 -->  
W październikowej wersji usługi Intune zmieniamy ścieżkę dostępu do urządzeń zarządzanych w wersji beta interfejsu API programu Graph.

| | |
|--|--|
| Bieżąca ścieżka |  https://graph.microsoft.com/beta/managedDevices |
| Nowa ścieżka | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Obie ścieżki będą działać przez cały październik. Po wydaniu październikowej wersji usługi będzie działać tylko nowa ścieżka.  Jeśli dostęp do urządzeń zarządzanych jest uzyskiwany za pomocą interfejsu API programu Graph, należy zaktualizować skrypty i aplikacje oraz sprawdzić, czy działają z nową ścieżką. Informacje na temat dodatkowych zmian zawiera comiesięczny [wykaz zmian interfejsu API programu Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/changelog).

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
