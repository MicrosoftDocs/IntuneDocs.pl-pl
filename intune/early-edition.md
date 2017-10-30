---
title: Wczesna wersja
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a2e6fd2381286aa652a04b5ed34ab21c57ed85f6
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2017
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



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Dodano sieć VPN Citrix dla urządzeń z systemem Windows 10 <!-- 1512457 -->  
Klient będzie mógł skonfigurować sieć VPN Citrix dla swoich urządzeń z systemem Windows 10. Sieć VPN Citrix można wybrać na liście *Wybierz typ połączenia* w bloku **Podstawowa sieć VPN** podczas konfigurowania sieci VPN dla systemu Windows 10 i nowszych.

> [!Note]
> Konfiguracja serwera Citrix istniała dla systemów iOS i Android.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720  -->  
Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet.  Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania. Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play.  Dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy, jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10 <!-- 903672(archived), 1119689 -->  
Można utworzyć zasady uaktualniania wydania systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wydania systemu Windows 10, zobacz artykuł [How to configure Windows 10 edition upgrades (Jak skonfigurować uaktualnienia wydania systemu Windows 10)](edition-upgrade-configure-windows-10.md).


### <a name="intune-mam-and-outlook-for-android-add-ins-----1450688---"></a>Zarządzanie aplikacjami mobilnymi usługi Intune i dodatki dla aplikacji Outlook dla systemu Android <!-- 1450688 -->
W ciągu kilku tygodni zespół Office ogłosi dodatki dla programu Outlook dla systemu Android. Wspomniany zestaw dodatków istnieje już w programie Outlook w systemach Windows i iOS, w aplikacji Outlook Web App oraz w aplikacji dla komputerów Mac. Ponieważ dodatki są zarządzane przez program Exchange, użytkownicy otrzymają możliwość kopiowania i udostępniania danych i wiadomości między programem Outlook i niezarządzanymi aplikacjami zgodnymi z dodatkami, chyba że dostęp do dodatków zostanie wyłączony przez administratora programu Exchange. 

Aby zarządzać uprawnieniami użytkowników w zakresie dostępu do dodatków, skontaktuj się z administratorem programu Exchange i upewnij się, że zasady ochrony danych funkcji MAM mają zastosowanie do dodatków.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli obowiązujące zasady programu Exchange zostały już skonfigurowane pod kątem uniemożliwienia ładowania bezpośredniego dodatków lub ich instalowania, lektura reszty tego artykułu mija się z celem. Zasady zarządzania aplikacjami mobilnymi będą stosowane zgodnie z wybranymi ustawieniami. Należy jednak pamiętać, że jeśli zasady funkcji MAM zostały skonfigurowane pod kątem ograniczenia operacji wycinania, kopiowania i wklejania danych w programie Outlook dla systemu Android, a w programie Exchange nie ustawiono zasad dotyczących dodatków, domyślne ustawienie będzie umożliwiać użytkownikom instalowanie dodatków programu Outlook. Dodatki te mają dostęp do treści, tematu i innych właściwości wiadomości. Możliwość instalowania dodatków przez użytkownika można wyłączyć. Aby to zrobić, administrator programu Exchange musi usunąć role „Moje aplikacje z portalu Marketplace” i „Moje aplikacje niestandardowe”.

Zmiana ustawienia w programie Exchange ma zastosowanie do programu Outlook dla systemu Windows i iOS, aplikacji Outlook Web App, aplikacji dla komputerów Mac i dla urządzeń przenośnych. 

#### <a name="what-do-i-need-to-do"></a>Co mam zrobić?
Już dzisiaj przejrzyj zasady programu Exchange. Poinformuj personel działu IT i pracowników pomocy technicznej. Zwróć się do naszego zespołu pomocy technicznej ze wszelkimi konkretnymi pytaniami i wątpliwościami. 




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Akcje w przypadku niezgodności <!--730266  846515 -->     
*Akcje w przypadku niezgodności* to nowa funkcja zasad zgodności, która umożliwia podejmowanie akcji na urządzeniach, które są niezgodne. Możesz określić jedną lub wiele akcji oraz przedział czasu, w którym te akcje muszą zostać wykonane. Na przykład możesz za pomocą poczty e-mail powiadomić użytkowników niezgodnych urządzeń, gdy tylko ich urządzenia staną się niezgodne, lub za pośrednictwem dostępu warunkowego zablokować niezgodnym urządzeniom dostęp do zasobów firmowych po 3-dniowym okresie karencji.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Obsługa programu Android for Work dla usługi Lookout <!-- 1087312 -->   
Łącznik usługi Intune z usługą Lookout będzie obsługiwać urządzenia z programem Android for Work w przypadku korzystania z aplikacji Lookout for Work. Można wdrożyć aplikację Lookout wewnątrz lub na zewnątrz kontenera.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Narzędzia deweloperskie usług Intune App Protection i Citrix MDX <!-- 709185 -->
Urządzeniami i aplikacjami można zarządzać przy użyciu kombinacji usług Citrix XenMobile MDX i Microsoft Intune. Umożliwia ona zarządzanie aplikacjami za pomocą zasad usługi Intune App Protection przy równoczesnym wykorzystaniu technologii mVPN firmy Citrix.

Możesz odnaleźć repozytorium kodu, które zawiera narzędzie opakowujące aplikacje usługi Intune i zestawu Intune App SDK dla systemu iOS i Android zintegrowane z technologią mVPN Citrix MDX.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->   
Można mieć wiele ról serwera dostępu klienta (CAS) dla łącznika lokalnego programu Exchange. Jeśli na przykład główny serwer dostępu klienta ulegnie awarii, łącznik programu Exchange odbierze zapytanie w celu powrotu do innych serwerów dostępu klienta. Ta funkcja pozwala zagwarantować nieprzerwane działanie usługi.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->   
Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange będzie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Ten pakiet administracyjny zapewnia różne sposoby monitorowania usługi Intune w przypadku konieczności rozwiązywania problemów.


## <a name="intune-apps"></a>Aplikacje usługi Intune


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Przekierowywanie użytkowników systemu macOS do naszej nowej aplikacji Portal firmy <!--1380728-->   
Gdy użytkownik końcowy zaloguje się do witryny internetowej Portal firmy, aby zarejestrować swoje urządzenie z systemem macOS, w celu ukończenia procesu zostanie przekierowany na stronę pobierania nowej aplikacji Portal firmy dla systemu macOS. Dotyczy to urządzeń z systemem macOS w wersji OS X El Capitan 10.11 lub nowszym. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Obsługa uwierzytelniania opartego na certyfikatach w Portalu firmy dla systemu iOS <!--1029830-->
W aplikacji Portal firmy dla systemu iOS dodaliśmy obsługę uwierzytelniania opartego na certyfikatach (CBA). Użytkownicy korzystający z uwierzytelniania CBA wprowadzają swoją nazwę użytkownika, a następnie wybierają link „Zaloguj się przy użyciu certyfikatu”. Uwierzytelnianie CBA jest już obsługiwane w aplikacji Portal firmy dla systemów Android i Windows. Więcej informacji na ten temat można znaleźć na stronie [logowania się w aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikacje dostępne z rejestracją lub bez rejestracji można teraz instalować bez monitów o rejestrację. <!-- 1334712 -->
Aplikacje firmowe, które udostępniono z rejestracją lub bez rejestracji w aplikacji Portal firmy dla systemu Android, można zainstalować bez monitu o rejestrację.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Obsługa aplikacji Intune Managed Browser dla systemu iOS i Android <!-- 1374196 -->
Od października 2017 r. aplikacja Intune Managed Browser w aplikacji dla systemu Android będzie obsługiwać tylko urządzenia z systemem Android 4.4 lub nowszym. Aplikacja Intune Managed Browser dla systemu iOS będzie obsługiwać wyłącznie urządzenia z systemem iOS 9.0 i nowszym. Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Ulepszony komunikat o błędzie, gdy użytkownik osiągnie maksymalną liczbę urządzeń, które można zarejestrować <!-- 1270370 -->
Zamiast ogólnego komunikatu o błędzie, użytkownicy końcowi widzą przyjazny komunikat o błędzie z akcjami: „Zarejestrowano maksymalną liczbę urządzeń dozwoloną przez administratora IT. Usuń zarejestrowane urządzenie lub skontaktuj się z administratorem IT w celu uzyskania pomocy”.




## <a name="notices"></a>Uwagi

### <a name="device-and-app-management-integration----677972---"></a>Integracja zarządzania urządzeniami i aplikacjami <!-- 677972 -->   
Teraz, gdy funkcje zarządzania urządzeniami przenośnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM) usługi Intune są już dostępne w witrynie Azure Portal, usługa Intune rozpoczęła integrowanie środowiska pracy administratora IT wokół zarządzania aplikacjami i urządzeniami. Zmiany mają na celu uproszczenie środowiska zarządzania urządzeniami i aplikacjami.

Dowiedz się więcej na temat zmian funkcji MDM i MAM ogłoszonych w [blogu zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).




### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
