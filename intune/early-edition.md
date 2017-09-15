---
title: Wczesna wersja
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31c3d3750aadbe8d302713f081f01f7c51d8ce96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>Wczesna wersja usługi Microsoft Intune — wrzesień 2017

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


### <a name="google-play-protect-support-on-android----908720----"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720  -->  
Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet.  Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania. Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play.  Dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy, jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uniemożliwianie użytkownikom urządzeń z systemem Android zmiany daty i godziny ich urządzeń <!-- 1333292 -->
Można użyć [niestandardowych zasad urządzeń z systemem Android](custom-settings-android.md), aby uniemożliwić użytkownikom urządzeń z systemem Android zmianę daty i godziny urządzenia.
W tym celu należy skonfigurować niestandardowe zasady systemu Android, korzystając z identyfikatora URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Dla powyższego identyfikatora URI należy wybrać wartość **TRUE**, a następnie przypisać go do wymaganych grup.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Wyświetlanie przypisań zasad ochrony aplikacji w celu rozwiązywania problemów <!--  1475003 -->
W nadchodzącym wydaniu opcja **zasad ochrony aplikacji** zostanie dodana do listy rozwijanej **Przypisania** dostępnej w bloku rozwiązywania problemów. Teraz możesz wybrać zasady ochrony aplikacji, aby wyświetlić zasady ochrony aplikacji przypisane do wybranych użytkowników.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Tworzenie aplikacji dla systemu iOS ograniczonych do określonych regionalnych sklepów Apple App Store <!-- 1281692 -->
Podczas tworzenia zarządzanej aplikacji przeznaczonej do sklepu Apple App Store można określić ustawienia regionalne dla kraju.

> [!NOTE]  
> Obecnie można tworzyć wyłącznie zarządzane aplikacje dla sklepu Apple App Store dostępne w amerykańskiej wersji strony sklepu.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Wybór krajowego sklepu Apple do synchronizacji aplikacji VPP <!-- 1332311 -->  
Podczas przekazywania tokenu programu VPP można skonfigurować krajowy sklep do obsługi programu zakupów zbiorczych (VPP, ang. Volume Purchase Program). Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.

> [!NOTE]  
> Obecnie usługa Intune synchronizuje tylko aplikacje VPP z krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnego z ustawieniami regionalnymi usługi Intune dla lokalizacji, w której została utworzona dzierżawa usługi Intune.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizacja aplikacji VPP dla systemu iOS z licencją użytkownika i urządzenia <!-- 1305564 -->  
Można skonfigurować token programu VPP systemu iOS pod kątem aktualizacji wszystkich aplikacji zakupionych dla danego tokenu za pośrednictwem usługi Intune. Usługa Intune wykryje aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypchnie je do urządzenia po jego zaewidencjonowaniu.

### <a name="ios-11-support----1428975---"></a>Obsługa systemu iOS 11 <!-- 1428975 -->
Usługa Intune będzie obsługiwać system iOS 11, gdy zostanie on wydany przez firmę Apple.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 Team <!--- 1308838  -->
W tym wydaniu dodajemy wiele nowych ustawień profilu ograniczeń urządzenia z systemem Windows 10 Team ułatwiających kontrolę urządzeń Surface Hub.
Aby uzyskać więcej informacji o tym profilu, zobacz artykuł [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md) (Ustawienia ograniczeń urządzenia z systemem Windows 10 Team).

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10 <!-- 903672, 1119689 -->  
Można utworzyć zasady uaktualniania wydania systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wydania systemu Windows 10, zobacz artykuł [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md) (Jak skonfigurować uaktualnienia wydania systemu Windows 10).

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Przegląd zasad zgodności pod kątem pierścieni aktualizacji systemu Windows 10 <!-- 1352223 -->  
Można przejrzeć raport zasad odnoszący się do pierścieni aktualizacji systemu Windows 10, przechodząc do obszaru **Aktualizacje oprogramowania** > **Stan wdrożenia według pierścienia aktualizacji**. Raport zasad zawiera stan wdrożenia dla skonfigurowanych pierścieni aktualizacji. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Dodanie aplikacji Portal firmy dla systemu Windows 10 do zasad zezwoleń funkcji Windows Information Protection <!-- 677129 -->  
Aplikacja Portal firmy dla systemu Windows 10 zostanie zaktualizowana w celu umożliwienia obsługi funkcji Windows Information Protection (WIP). Aplikację można dodać do zasad zezwoleń funkcji WIP. Dzięki tej zmianie nie trzeba dodawać żadnych aplikacji do listy **Wyklucz**. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Zdalna pomoc techniczna dla urządzeń z systemem Windows i Windows Mobile <!-- 1070473 -->    
Usługa Intune będzie umożliwiać korzystanie z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Windows i Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Skanowanie urządzeń z użyciem usługi Windows Defender <!-- 1280988  1280990   -->
Na zarządzanych urządzeniach z systemem Windows 10 możliwe będzie uruchomienie **szybkiego skanowania** i **pełnego skanowania** oraz przeprowadzenie **aktualizacji sygnatur** z użyciem programu antywirusowego Windows Defender. W bloku przeglądu urządzenia wybierz akcję do przeprowadzenia na urządzeniu. Przed wysłaniem polecenia do urządzenia zostanie wyświetlony monit o potwierdzenie akcji. 

**Szybkie skanowanie**: szybkie skanowanie obejmuje lokalizacje, w których złośliwe oprogramowanie rejestruje się w celu umożliwienia jego uruchomienia, np. klucze rejestru i znane foldery uruchamiania systemu Windows. Szybkie skanowanie trwa średnio pięć minut. W połączeniu z ustawieniem **zawsze włączonej ochrony w czasie rzeczywistym**, które skanuje pliki, gdy są one otwierane i zamykane, a także za każdym razem, gdy użytkownik przejdzie do folderu, szybkie skanowanie pomaga chronić przed złośliwym oprogramowaniem, które może być obecne w systemie lub w jądrze. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Pełne skanowanie**: pełne skanowanie przydaje się w przypadku urządzeń, w których wystąpiło zagrożenie związane ze złośliwym oprogramowaniem, ponieważ pozwala określić, czy istnieją nieaktywne składniki, które wymagają dokładniejszego czyszczenia; funkcja umożliwia także uruchamianie skanowania na żądanie. Pełne skanowanie może trwać godzinę. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Zaktualizuj sygnatury**: polecenie aktualizacji sygnatur powoduje aktualizację definicji i sygnatur złośliwego oprogramowania programu antywirusowego Windows Defender. Można w ten sposób upewnić się, że program antywirusowy Windows Defender skutecznie wykrywa złośliwe oprogramowanie. Ta funkcja jest dostępna wyłącznie dla urządzeń z systemem Windows 10 i wymaga połączenia z Internetem. 

### <a name="bitlocker-device-configuration----1397398---"></a>Konfiguracja urządzenia z użyciem funkcji BitLocker <!-- 1397398 -->  
Wybierając kolejno **Szyfrowanie systemu Windows > Ustawienia podstawowe**, można uzyskać dostęp do nowego ustawienia **Ostrzeżenie dotyczące innego szyfrowania dysku**, które pozwala wyłączyć [monit ostrzegawczy](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) dotyczący innego szyfrowania, które mogło zostać użyte na urządzeniu użytkownika.  Przed rozpoczęciem konfiguracji funkcji BitLocker na urządzeniu zostanie wyświetlony monit ostrzegawczy wymagający zgody użytkownika końcowego; konfiguracja funkcji BitLocker będzie blokowana do czasu potwierdzenia przez użytkownika końcowego.  Nowe ustawienie wyłącza ostrzeżenie użytkownika końcowego.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Utrzymanie aplikacji Portal firmy w systemach Windows 8.1 i Windows Phone 8.1 <!--1428681-->
Począwszy od października 2017 roku aplikacje Portal firmy zostaną utrzymane w systemach Windows 8.1 i Windows Phone 8.1. Oznacza to, że aplikacje i istniejące scenariusze, np. scenariusze rejestracji i zgodności, będą nadal obsługiwane przez te platformy. Aplikacje te będą nadal dostępne do pobrania za pośrednictwem istniejących kanałów, takich jak Sklep Microsoft. 

Po zatwierdzeniu utrzymania tych aplikacji będą dla nich udostępniane wyłącznie krytyczne aktualizacje zabezpieczeń. Nie będzie dla nich żadnych dodatkowych aktualizacji i nie będą w nich udostępniane żadne nowe funkcje. W celu skorzystania z nowych funkcji zalecamy aktualizację urządzenia do systemu Windows 10 lub Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokowanie kopiowania i wklejania między profilami służbowymi i osobistymi w aplikacji Android for Work <!-- 1098994 -->   
W tej wersji można skonfigurować profil służbowy w programie Android for Work w taki sposób, aby kopiowanie i wklejanie danych między aplikacjami służbowymi i osobistymi było blokowane. To nowe ustawienie można znaleźć w profilu **Ograniczenia urządzenia** platformy **Android for Work** w obszarze **Ustawienia profilu służbowego**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nowe zachowanie aplikacji Portal firmy dla systemu Android z profilami służbowymi <!---1485783--->
Po zarejestrowaniu urządzenia z programem Android for Work i z profilem służbowym to właśnie aplikacja Portal firmy w profilu służbowym wykonuje na urządzeniu zadania z zakresu zarządzania. Jeśli użytkownik nie korzysta w profilu osobistym z aplikacji z obsługą zasad zarządzania aplikacjami mobilnymi (MAM), aplikacja Portal firmy dla systemu Android nie pełni już żadnej roli. Aby ulepszyć środowisko pracy w profilu służbowym, po pomyślnej rejestracji profilu służbowego usługa Intune automatycznie ukrywa aplikację Portal firmy z profilu osobistego.

Aplikację Portal firmy dla systemu Android można w dowolnym momencie włączyć w profilu osobistym, wybierając [aplikację Portal firmy w Sklepie Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) i wybierając opcję **Włącz**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Zarządzanie aplikacjami mobilnymi usługi Intune i dodatki dla aplikacji Outlook dla systemu Android <!-- 1450688 -->
W ciągu kilku tygodni zespół Office ogłosi dodatki dla programu Outlook dla systemu Android. Wspomniany zestaw dodatków istnieje już w programie Outlook w systemach Windows i iOS, w aplikacji Outlook Web App oraz w aplikacji dla komputerów Mac. Ponieważ dodatki są zarządzane przez program Exchange, użytkownicy otrzymają możliwość kopiowania i udostępniania danych i wiadomości między programem Outlook i niezarządzanymi aplikacjami zgodnymi z dodatkami, chyba że dostęp do dodatków zostanie wyłączony przez administratora programu Exchange. 

Aby zarządzać uprawnieniami użytkowników w zakresie dostępu do dodatków, skontaktuj się z administratorem programu Exchange i upewnij się, że zasady ochrony danych funkcji MAM mają zastosowanie do dodatków.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli obowiązujące zasady programu Exchange zostały już skonfigurowane pod kątem uniemożliwienia ładowania bezpośredniego dodatków lub ich instalowania, lektura reszty tego artykułu mija się z celem. Zasady zarządzania aplikacjami mobilnymi będą stosowane zgodnie z wybranymi ustawieniami. Należy jednak pamiętać, że jeśli zasady funkcji MAM zostały skonfigurowane pod kątem ograniczenia operacji wycinania, kopiowania i wklejania danych w programie Outlook dla systemu Android, a w programie Exchange nie ustawiono zasad dotyczących dodatków, domyślne ustawienie będzie umożliwiać użytkownikom instalowanie dodatków programu Outlook. Dodatki te mają dostęp do treści, tematu i innych właściwości wiadomości. Możliwość instalowania dodatków przez użytkowników końcowych można wyłączyć. Aby to zrobić, administrator programu Exchange musi usunąć role „Moje aplikacje z portalu Marketplace” i „Moje aplikacje niestandardowe”. Aby uzyskać więcej informacji, skorzystaj z poniższego łącza do informacji dodatkowych.

Uwaga: zmiana ustawienia w programie Exchange ma zastosowanie do programu Outlook dla systemu Windows i iOS, aplikacji Outlook Web App, aplikacji dla komputerów Mac i dla urządzeń przenośnych. 

#### <a name="what-do-i-need-to-do"></a>Co mam zrobić?
Już dzisiaj przejrzyj zasady programu Exchange. Poinformuj personel działu IT i pracowników pomocy technicznej. Zwróć się do naszego zespołu pomocy technicznej ze wszelkimi konkretnymi pytaniami i wątpliwościami. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->
Będzie można tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>Akcje w przypadku niezgodności <!--730266-->     
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

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Link do nowego interfejsu użytkownika zasad dostępu warunkowego usługi Azure AD z usługi Intune <!-- 1016201 -->
Administratorzy IT mogą ustawiać zasady dostępu warunkowego na podstawie aplikacji za pomocą nowego interfejsu użytkownika zasad dostępu warunkowego w obciążeniu usługi Azure AD. Zasady dostępu warunkowego opartego na aplikacji, które znajdują się w sekcji usługi Intune App Protection na platformie Azure, obecnie pozostają w tym miejscu i są wymuszane równolegle. Wygodny link do nowego interfejsu użytkownika zasad dostępu warunkowego będzie wkrótce dostępny w usłudze Azure AD z poziomu obciążenia usługi Intune.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->   
Można mieć wiele ról serwera dostępu klienta (CAS) dla łącznika lokalnego programu Exchange. Jeśli na przykład główny serwer dostępu klienta ulegnie awarii, łącznik programu Exchange odbierze zapytanie w celu powrotu do innych serwerów dostępu klienta. Ta funkcja pozwala zagwarantować nieprzerwane działanie usługi.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->   
Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange będzie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Ten pakiet administracyjny zapewnia różne sposoby monitorowania usługi Intune w przypadku konieczności rozwiązywania problemów.

### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!---1164477--->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. Od grudnia zostanie zablokowany dostęp do wszystkich zasobów firmy, w tym wiadomości e-mail. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!---1171127, 1326920 --->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane przed początkiem października, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Przypomnienie dotyczące obsługi platformy: podstawowa obsługa systemu Windows Phone 8.1 zakończy się 11 lipca 2017 r. <!-- 1327781 -->  
11 lipca 2017 r. zakończy się wsparcie podstawowe dla platformy Windows Phone 8.1. Nie ma to wpływu na pomoc techniczną dla komputerów z systemem Windows 8.1.

Nie ma to bezpośredniego wpływu na urządzenia z systemem Windows Phone 8.1 zarządzane przez usługę Intune. Zarejestrowane urządzenia będą nadal działać, a wszystkie zasady, konfiguracje i aplikacje będą nadal działać zgodnie z oczekiwaniami. Nie ma żadnych ulepszeń przeznaczonych dla platformy Windows Phone 8.1 w usłudze Intune ani dla aplikacji Portal firmy systemu Windows Phone 8.1.

Zalecamy możliwie najwcześniejsze uaktualnienie kwalifikujących się urządzeń z systemem Windows Phone 8.1 do systemu Windows 10 Mobile. 





## <a name="intune-apps"></a>Aplikacje usługi Intune
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Dodanie akcji odświeżenia do aplikacji Portal firmy dla systemu Windows 10 <!--1132468-->
Aplikacja Portal firmy dla systemu Windows 10 pozwoli użytkownikom odświeżać dane w aplikacji poprzez przeciągnięcie ekranu lub — w przypadku komputerów — naciśnięcie klawisza F5.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikacje dostępne z rejestracją lub bez rejestracji można teraz instalować bez monitów o rejestrację. <!-- 1334712 -->
Aplikacje firmowe, które udostępniono z rejestracją lub bez rejestracji w aplikacji Portal firmy dla systemu Android, można zainstalować bez monitu o rejestrację.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Wyświetlanie dużych ikon w aplikacji Portal firmy dla systemu iOS <!-- 1454593 -->
Naprawiamy znany problem ze sposobem wyświetlania ikon aplikacji Portal firmy dla systemu iOS na kafelku aplikacji. Przesłane ikony aplikacji o rozmiarach 120 x 120 pikseli lub większe są teraz wyświetlane w [witrynie sieci Web portalu firmy] (https://portal.manage.microsoft.com) i na stronie aplikacji Portal firmy dla systemu iOS w pełnym rozmiarze kafelka aplikacji.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Bardziej zrozumiałe komunikaty w aplikacji Portal firmy dla systemu Android <!---1396349--->    
Proces rejestracji w aplikacji Portal firmy dla systemu Android został uproszczony poprzez dodanie nowego tekstu w celu ułatwienia użytkownikom końcowym przeprowadzenia procesu rejestracji. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Obsługa aplikacji Intune Managed Browser dla systemu iOS i Android <!---1374196--->
Od października 2017 r. aplikacja Intune Managed Browser w aplikacji dla systemu Android będzie obsługiwać tylko urządzenia z systemem Android 4.4 lub nowszym. Aplikacja Intune Managed Browser dla systemu iOS będzie obsługiwać wyłącznie urządzenia z systemem iOS 9.0 i nowszym. Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zezwalanie użytkownikom na dostęp do aplikacji Portal firmy dla systemu Android bez rejestracji <!---1169910--->  
Wkrótce użytkownicy końcowi nie będą musieli rejestrować urządzeń, aby uzyskać dostęp do aplikacji Portal firmy dla systemu Android. Użytkownicy końcowi w organizacjach używających zasad ochrony aplikacji nie będą już otrzymywać monitów o zarejestrowanie swoich urządzeń po otwarciu aplikacji Portal firmy. Ponadto użytkownicy końcowi będą mogli instalować aplikacje z poziomu aplikacji Portal firmy bez konieczności rejestrowania urządzeń. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Ulepszony komunikat o błędzie, gdy użytkownik osiągnie maksymalną liczbę urządzeń, które można zarejestrować <!-- 1270370 -->
Zamiast ogólnego komunikatu o błędzie, użytkownicy końcowi widzą przyjazny komunikat o błędzie z akcjami: „Zarejestrowano maksymalną liczbę urządzeń dozwoloną przez administratora IT. Usuń zarejestrowane urządzenie lub skontaktuj się z administratorem IT w celu uzyskania pomocy”.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Powiadamianie użytkowników końcowych, o widocznych w systemie iOS informacjach o urządzeniu <!--739894-->
Dodajemy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu iOS. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie Informacje.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Strony szczegółów aplikacji zawierają nowe informacje dotyczące urządzeń z systemem Android <!--1287476-->
Na stronie szczegółów aplikacji w aplikacji Portal firmy dla systemu Android będą wyświetlane kategorie aplikacji, które administrator IT zdefiniował dla danej aplikacji.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Okna dialogowe zarządzania aplikacjami mobilnymi (MAM) w usłudze Intune mają teraz nowoczesny interfejs <!-- 1199015 -->
Okna dialogowe zarządzania aplikacjami mobilnymi (MAM) w usłudze Intune zostały zaktualizowane i oferują teraz nowoczesny wygląd i działanie. Okna dialogowe funkcjonują tak jak okna w poprzednim stylu.

W nowoczesnych urządzeniach z systemem Android okna dialogowe błędów lub powiadomień wyświetlane przez usługę Intune mają teraz zaktualizowany wygląd i działanie.



## <a name="notices"></a>Uwagi
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->   
Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planowane zmiany: zmiany w usłudze Intune dotyczące witryny Intune Partner Portal <!-- 1050016 -->
Wraz z aktualizacją usługi w połowie maja 2017 r. strona Intune Partner zostanie usunięta z witryny manage.microsoft.com.  

Administratorzy partnerów nie będą już mogli wyświetlać strony Intune Partner ani podejmować na niej działań w imieniu swoich klientów. Zamiast tego konieczne będzie zalogowanie się w jednym z dwóch innych portali firmy Microsoft dla partnerów.

Logowanie się na zarządzane konta klientów będzie możliwe zarówno w [Centrum partnerskim firmy Microsoft](https://partnercenter.microsoft.com/), jak i w [Centrum administracyjnym dla partnerów usługi Microsoft Office 365](https://portal.office.com/). Aby kontynuować czynności partnerskie, należy korzystać z dowolnej z tych witryn do zarządzania klientami.



### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
