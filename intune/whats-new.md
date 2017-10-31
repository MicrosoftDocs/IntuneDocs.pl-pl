---
title: "Co nowego w usłudze Microsoft Intune"
titlesuffix: Azure portal
description: "Dowiedz się, co nowego w witrynie Azure Portal usługi Intune"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b669268073e4484738e93fd2909b905242732664
ms.sourcegitcommit: b8d3f8da6d8c2bd5d6140d538193a02d5875aefb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również dowiedzieć się o [nadchodzących zmianach](#whats-coming), [ważnych powiadomieniach](#notices) o usłudze oraz uzyskać informacje o [poprzednich wersjach](whats-new-archive.md).

> [!Note]
> Wiele z tych funkcji będzie również w przyszłości obsługiwane dla wdrożeń hybrydowych przy użyciu programu Configuration Manager. Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-october-23-2017"></a>Tydzień 23 października 2017 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Obsługa uwierzytelniania opartego na certyfikatach w Portalu firmy dla systemu iOS <!--1029830-->
W aplikacji Portal firmy dla systemu iOS dodaliśmy obsługę uwierzytelniania opartego na certyfikatach (CBA). Użytkownicy korzystający z uwierzytelniania CBA wprowadzają swoją nazwę użytkownika, a następnie wybierają link „Zaloguj się przy użyciu certyfikatu”. Uwierzytelnianie CBA jest już obsługiwane w aplikacji Portal firmy dla systemów Android i Windows. Więcej informacji na ten temat można znaleźć na stronie [logowania się w aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

## <a name="week-of-october-16-2017"></a>Tydzień 16 października 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Obsługa programu Windows AutoPilot Deployment w usłudze Microsoft Intune <!-- 747617  -->
Przy użyciu programu usługi Microsoft Intune z programem Windows AutoPilot Deployment możesz umożliwiać użytkownikom aprowizację urządzeń firmowych bez angażowania w to działu IT. Możesz dostosować tryb OOBE i przeprowadzić użytkowników przez proces dołączania urządzenia do usługi Azure AD i jego rejestracji w usłudze Intune. Dzięki współdziałaniu usługi Microsoft Intune i programu Windows AutoPilot nie ma potrzeby wdrażania i utrzymywania obrazów systemu operacyjnego ani zarządzania nimi. Aby uzyskać szczegółowe informacje, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Szybki start dla rejestracji urządzeń <!-- 1425655 --> 
Szybki start jest teraz dostępny w **rejestracji urządzeń** i zawiera tabelę odwołań dla zarządzania platformami i konfigurowania procesu rejestracji. Krótki opis każdego elementu i linki do dokumentacji z instrukcjami krok po kroku ułatwiają rozpoczęcie pracy.

#### <a name="device-categorization----1427491---"></a>Kategoryzacja urządzeń <!-- 1427491 -->
Zestawienie platform zarejestrowanych urządzeń w bloku **Urządzenia > Przegląd** organizuje urządzenia według platform, w tym systemów Android, iOS, macOS, Windows i Windows Mobile.  Urządzenia z innymi systemami operacyjnymi znajdują się w grupie „Inne”.  Są to urządzenia wyprodukowane przez firmy Blackberry, NOKIA i inne.  

Aby dowiedzieć się, których urządzeń w dzierżawie to dotyczy, wybierz pozycję **Zarządzaj > Wszystkie urządzenia**, a następnie przy użyciu funkcji **Filtruj** ogranicz pole **System operacyjny**.

### <a name="device-management"></a>Zarządzanie urządzeniami
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium — nowy partner usługi Mobile Threat Defense <!-- 954681 -->  
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować przy użyciu dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 <!--- 978575, 1308849, -->  
Dodajemy nowe ustawienia do profilu ograniczeń urządzenia z systemem Windows 10 w kategorii Windows Defender SmartScreen.

Aby uzyskać szczegółowe informacje o profilu ograniczeń urządzenia z systemem Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Zdalna pomoc techniczna dla urządzeń z systemem Windows i Windows Mobile <!-- 1070473 -->  
Usługa Intune umożliwia teraz korzystanie z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Windows i Windows Mobile.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Skanowanie urządzeń z użyciem usługi Windows Defender <!-- 1280988  1280990   -->
Na zarządzanych urządzeniach z systemem Windows 10 możliwe jest teraz uruchomienie **szybkiego skanowania** i **pełnego skanowania** oraz przeprowadzenie **aktualizacji sygnatur** z użyciem programu antywirusowego Windows Defender. W bloku przeglądu urządzenia wybierz akcję do przeprowadzenia na urządzeniu. Przed wysłaniem polecenia do urządzenia zostanie wyświetlony monit o potwierdzenie akcji. 

**Szybkie skanowanie**: szybkie skanowanie obejmuje lokalizacje, w których złośliwe oprogramowanie rejestruje się w celu umożliwienia jego uruchomienia, np. klucze rejestru i znane foldery uruchamiania systemu Windows. Szybkie skanowanie trwa średnio pięć minut. W połączeniu z ustawieniem **zawsze włączonej ochrony w czasie rzeczywistym**, które skanuje pliki, gdy są one otwierane i zamykane, a także za każdym razem, gdy użytkownik przejdzie do folderu, szybkie skanowanie pomaga chronić przed złośliwym oprogramowaniem, które może być obecne w systemie lub w jądrze. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Pełne skanowanie**: pełne skanowanie przydaje się w przypadku urządzeń, w których wystąpiło zagrożenie związane ze złośliwym oprogramowaniem, ponieważ pozwala określić, czy istnieją nieaktywne składniki, które wymagają dokładniejszego czyszczenia; funkcja umożliwia także uruchamianie skanowania na żądanie. Pełne skanowanie może trwać godzinę. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Zaktualizuj sygnatury**: polecenie aktualizacji sygnatur powoduje aktualizację definicji i sygnatur złośliwego oprogramowania programu antywirusowego Windows Defender. Można w ten sposób upewnić się, że program antywirusowy Windows Defender skutecznie wykrywa złośliwe oprogramowanie. Ta funkcja jest dostępna wyłącznie dla urządzeń z systemem Windows 10 i wymaga połączenia z Internetem. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Przycisk Włącz/Wyłącz został usunięty ze strony urzędu certyfikacji usługi Intune w witrynie Azure Portal usługi Intune <!-- 1400455 -->
 Eliminujemy dodatkowy krok z konfiguracji łącznika certyfikatów w usłudze Intune. Obecnie należy pobrać łącznik certyfikatów, a następnie włączyć go w konsoli usługi Intune. Jeśli jednak wyłączysz łącznik w konsoli usługi Intune, łącznik wciąż wydaje certyfikaty.

##### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Począwszy od października przycisk Włącz/Wyłącz nie będzie już wyświetlany na stronie urzędu certyfikacji w witrynie Azure Portal. Funkcje łącznika pozostają bez zmian. Certyfikaty są wciąż wdrażane na urządzeniach zarejestrowanych w usłudze Intune. Nadal możesz pobrać i zainstalować łącznik certyfikatów. Aby zatrzymać wydawanie certyfikatów, zamiast wyłączać łącznik certyfikatów należy go teraz odinstalować.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli łącznik certyfikatów jest obecnie wyłączony, należy go odinstalować.



### <a name="device-configuration"></a>Konfiguracja urządzenia
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 Team <!--- 1308838 -->
W tym wydaniu dodaliśmy wiele nowych ustawień profilu ograniczeń urządzenia z systemem Windows 10 Team ułatwiających kontrolę urządzeń Surface Hub.

Aby uzyskać więcej informacji o tym profilu, zobacz artykuł [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md) (Ustawienia ograniczeń urządzenia z systemem Windows 10 Team).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uniemożliwianie użytkownikom urządzeń z systemem Android zmiany daty i godziny ich urządzeń <!-- 1333292 -->
Można użyć [niestandardowych zasad urządzeń z systemem Android](custom-settings-android.md), aby uniemożliwić użytkownikom urządzeń z systemem Android zmianę daty i godziny urządzenia.

W tym celu należy skonfigurować niestandardowe zasady systemu Android, korzystając z identyfikatora URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Dla powyższego identyfikatora URI należy wybrać wartość **TRUE**, a następnie przypisać go do wymaganych grup.

#### <a name="bitlocker-device-configuration----1397398---"></a>Konfiguracja urządzenia z użyciem funkcji BitLocker <!-- 1397398 -->
Wybierając pozycję **Szyfrowanie systemu Windows > Ustawienia podstawowe**, można uzyskać dostęp do nowego ustawienia **Ostrzeżenie dotyczące innego szyfrowania dysku** pozwalającego wyłączyć [monit ostrzegawczy](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) dotyczący innego szyfrowania, które mogło zostać użyte na urządzeniu użytkownika.  Przed rozpoczęciem konfiguracji funkcji BitLocker na urządzeniu zostanie wyświetlony monit ostrzegawczy wymagający zgody użytkownika końcowego; konfiguracja funkcji BitLocker będzie blokowana do czasu potwierdzenia przez użytkownika końcowego.  Nowe ustawienie wyłącza ostrzeżenie użytkownika końcowego.


### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Aplikacje programu Volume Purchase Program for Business będą się teraz synchronizowały z dzierżawą usługi Intune <!-- 800882 -->  
Deweloperzy innych firm mogą prywatnie dystrybuować aplikacje do autoryzowanych członków programu Volume Purchase Program (VPP) for Business określonych w usłudze iTunes Connect. Ci członkowie programu VPP for Business mogą zalogować się do sklepu Volume Purchase Program App Store i zakupić ich aplikacje.

W tej wersji aplikacje programu VPP for Business zakupione przez użytkownika końcowego będą się teraz synchronizowały z ich dzierżawami usługi Intune.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Wybór krajowego sklepu Apple do synchronizacji aplikacji VPP <!-- 1332311 -->  
Podczas przekazywania tokenu programu VPP można skonfigurować krajowy sklep do obsługi programu zakupów zbiorczych (VPP, ang. Volume Purchase Program). Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.

> [!NOTE]  
> Obecnie usługa Intune synchronizuje tylko aplikacje VPP z krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnego z ustawieniami regionalnymi usługi Intune dla lokalizacji, w której została utworzona dzierżawa usługi Intune.




### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokowanie kopiowania i wklejania między profilami służbowymi i osobistymi w aplikacji Android for Work <!-- 1098994 -->
W tej wersji można skonfigurować profil służbowy w programie Android for Work w taki sposób, aby kopiowanie i wklejanie danych między aplikacjami służbowymi i osobistymi było blokowane. To nowe ustawienie można znaleźć w profilu **Ograniczenia urządzenia** platformy **Android for Work** w obszarze **Ustawienia profilu służbowego**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Tworzenie aplikacji dla systemu iOS ograniczonych do określonych regionalnych sklepów Apple App Store <!-- 1281692 -->
Podczas tworzenia zarządzanej aplikacji przeznaczonej do sklepu Apple App Store można określić ustawienia regionalne dla kraju.

> [!Note]  
> Obecnie można tworzyć wyłącznie zarządzane aplikacje dla sklepu Apple App Store dostępne w amerykańskiej wersji strony sklepu.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizacja aplikacji VPP dla systemu iOS z licencją użytkownika i urządzenia <!-- 1305564 -->  
Można skonfigurować token programu VPP systemu iOS pod kątem aktualizacji wszystkich aplikacji zakupionych dla danego tokenu za pośrednictwem usługi Intune. Usługa Intune wykryje aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypchnie je do urządzenia po jego zaewidencjonowaniu.

Aby poznać procedurę ustawiania tokenu VPP i włączania automatycznych aktualizacji, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych] (/intune/vpp-apps-ios).



### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->
Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Przegląd zasad zgodności pod kątem pierścieni aktualizacji systemu Windows 10 <!-- 1067886 -->
Można przejrzeć raport zasad odnoszący się do pierścieni aktualizacji systemu Windows 10, przechodząc do obszaru Aktualizacje oprogramowania > Stan wdrożenia według pierścienia aktualizacji. Raport zasad zawiera stan wdrożenia dla skonfigurowanych pierścieni aktualizacji. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nowy raport, który zawiera listę urządzeń dla systemu iOS ze starszymi wersjami systemu iOS   <!-- 1352223 -->
Raport **Nieaktualne urządzenia z systemem iOS** jest dostępny z poziomu obszaru roboczego **Aktualizacje oprogramowania**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS i które mają dostępne aktualizacje. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Wyświetlanie przypisań zasad ochrony aplikacji w celu rozwiązywania problemów <!--  1475003 -->
W nadchodzącym wydaniu opcja **zasad ochrony aplikacji** zostanie dodana do listy rozwijanej **Przypisania** dostępnej w bloku rozwiązywania problemów. Teraz możesz wybrać zasady ochrony aplikacji, aby wyświetlić zasady ochrony aplikacji przypisane do wybranych użytkowników.



## <a name="week-of-october-2-2017"></a>Tydzień 2 października 2017 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w Portalu firmy <!--1490692-->
Ulepszyliśmy przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android. Język jest bardziej przyjazny dla użytkownika i specyficzny dla Twojej firmy, a w miarę możliwości ekrany zostały połączone. Możesz to zobaczyć na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Ulepszone wskazówki dotyczące żądania dostępu do kontaktów na urządzeniach z systemem Android <!--1484985-->

Aplikacja Portal firmy dla systemu Android często wymaga od użytkownika końcowego zaakceptowania uprawnień do kontaktów. Jeśli użytkownik końcowy odmówi dostępu, zobaczy w aplikacji powiadomienie z alertem dotyczącym przyznania aplikacji dostępu warunkowego. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Korygowanie bezpiecznego uruchamiania dla systemu Android <!--1490712-->

Użytkownicy końcowi mający urządzenia z systemem Android będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Dodatkowe powiadomienia wypychane dla użytkowników końcowych w aplikacji Portal firmy dla systemu Android Oreo <!--1475932-->

Użytkownicy końcowi będą widzieli dodatkowe powiadomienia, gdy aplikacja Portal firmy dla systemu Android Oreo wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune. Powoduje to zwiększenie przejrzystości dla użytkowników końcowych przez informowanie ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na ich urządzeniach. Jest to część ogólnej [optymalizacji interfejsu użytkownika aplikacji Portal firmy](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) dla aplikacji Portal firmy dla systemu Android Oreo. 

Istnieją dodatkowe optymalizacje dla nowych elementów interfejsu użytkownika, które są włączone w systemie Android Oreo.  Użytkownicy końcowi zobaczą dodatkowe powiadomienia, które będą wskazywać im, kiedy Portal firmy wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune.  Powoduje to zwiększenie przejrzystości dla użytkowników końcowych dzięki informowaniu ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na urządzeniu.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nowe zachowanie aplikacji Portal firmy dla systemu Android z profilami służbowymi <!---1485783--->

Po zarejestrowaniu urządzenia z programem Android for Work i z profilem służbowym to właśnie aplikacja Portal firmy w profilu służbowym wykonuje na urządzeniu zadania z zakresu zarządzania. 

Jeśli użytkownik nie korzysta w profilu osobistym z aplikacji z obsługą zasad zarządzania aplikacjami mobilnymi (MAM), aplikacja Portal firmy dla systemu Android nie pełni już żadnej roli. Aby ulepszyć środowisko pracy w profilu służbowym, po pomyślnej rejestracji profilu służbowego usługa Intune automatycznie ukrywa aplikację Portal firmy z profilu osobistego.

Aplikację Portal firmy dla systemu Android można w dowolnym momencie włączyć w profilu osobistym, wybierając [aplikację Portal firmy w Sklepie Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) i wybierając opcję **Włącz**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Utrzymanie aplikacji Portal firmy w systemach Windows 8.1 i Windows Phone 8.1 <!--1428681-->

Począwszy od października 2017 roku aplikacje Portal firmy zostaną utrzymane w systemach Windows 8.1 i Windows Phone 8.1. Oznacza to, że aplikacje i istniejące scenariusze, np. scenariusze rejestracji i zgodności, będą nadal obsługiwane przez te platformy. Aplikacje te będą nadal dostępne do pobrania za pośrednictwem istniejących kanałów, takich jak Sklep Microsoft. 

Po zatwierdzeniu utrzymania tych aplikacji będą dla nich udostępniane wyłącznie krytyczne aktualizacje zabezpieczeń. Nie będzie dla nich żadnych dodatkowych aktualizacji i nie będą w nich udostępniane żadne nowe funkcje. W celu skorzystania z nowych funkcji zalecamy aktualizację urządzenia do systemu Windows 10 lub Windows 10 Mobile. 


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Blokowanie nieobsługiwanej rejestracji urządzenia z systemem Samsung Knox <!--- 1490695 --->

Aplikacja Portal firmy tylko próbuje zarejestrować obsługiwane urządzenia z systemem Samsung Knox. Aby uniknąć błędów aktywacji systemu KNOX, które uniemożliwią rejestrację w systemie MDM, próba rejestracji urządzenia nastąpi tylko wtedy, gdy urządzenie znajduje się na [liście urządzeń opublikowanej przez firmę Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Urządzenia firmy Samsung mogą mieć numery modelu, które obsługują system KNOX, podczas gdy inne go nie obsługują. Sprawdź zgodność systemu Knox u odsprzedawcy urządzenia przed zakupem i wdrożeniem. Pełną listę zweryfikowanych urządzeń możesz znaleźć w [ustawieniach zasad systemu Android i systemu Samsung KNOX Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!---1171126, 1326920 --->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Powiadamianie użytkowników końcowych o informacjach o urządzeniu widocznych na zarejestrowanych urządzeniach <!--1165314-->
Dodajemy element **Typ własności** do ekranu Szczegóły urządzenia we wszystkich aplikacjach Portal firmy. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z artykułu [Jakie informacje może wyświetlać Twoja firma?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Zostanie to wdrożone we wszystkich aplikacjach Portal firmy w najbliższej przyszłości. Zapowiedzieliśmy to dla systemu iOS we [wrześniu](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Tydzień 25 września 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="intune-supports-ios-11---1428975--"></a>Usługa Intune obsługuje system iOS 11 <!--1428975-->
Usługa Intune obsługuje system iOS 11. Zostało to wcześniej zapowiedziane na [blogu dotyczącym pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!---1164477--->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. 

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Dodanie akcji odświeżenia do aplikacji Portal firmy dla systemu Windows 10 <!--1132468-->
Aplikacja Portal firmy dla systemu Windows 10 pozwala użytkownikom odświeżać dane w aplikacji poprzez przeciągnięcie ekranu lub — w przypadku komputerów — naciśnięcie klawisza F5.



## <a name="notices"></a>Uwagi

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nowa ścieżka dla urządzeń zarządzanych w interfejsie API programu Graph <!-- 1586728 -->
Zmieniamy ścieżkę dostępu do urządzeń zarządzanych w wersji beta interfejsu API programu Graph. 

| | |
|--|--|
| Bieżąca ścieżka |  https://graph.microsoft.com/beta/managedDevices |
| Nowa ścieżka | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Obie ścieżki będą działać przez cały październik. Po wydaniu październikowej wersji usługi będzie działać tylko nowa ścieżka.  Jeśli dostęp do urządzeń zarządzanych jest uzyskiwany za pomocą interfejsu API programu Graph, należy zaktualizować skrypty i aplikacje oraz sprawdzić, czy działają z nową ścieżką. Informacje na temat dodatkowych zmian zawiera comiesięczny [wykaz zmian interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 roku wymagają przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do witryny Azure portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal
Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Wkrótce

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS w usłudze Intune <!-- 1164474  -->
Wkrótce pojawi się nowa wersja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która obejmie tylko urządzenia z systemem iOS 9.0 lub nowszym. Wersja aplikacji Portal firmy obsługująca system iOS 8 będzie przez krótki okres nadal dostępna. Jeśli jednak są również używane aplikacje systemu iOS z obsługą funkcji MAM, obsługiwany jest system iOS 9.0 i nowsze wersje, więc należy zadbać o to, aby użytkownicy końcowi zaktualizowali system operacyjny do najnowszej wersji. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Informujemy o tym z wyprzedzeniem, mimo że nie podajemy konkretnych dat, aby zapewnić klientom czas na zaplanowanie działań. Zadbaj o to, aby użytkownicy zaktualizowali system do wersji iOS 9 lub nowszej, a po opublikowaniu aplikacji Portal firmy zwróć się do użytkowników końcowych o zaktualizowanie aplikacji Portal firmy.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Zalecamy powiadomienie użytkowników, aby przeprowadzili aktualizację do wersji iOS 9.0 lub nowszej w celu pełnego korzystania z nowych funkcji usługi Intune.  Zachęć użytkowników do zainstalowania nowej wersji aplikacji Portal firmy i korzystania z dostępnych w niej nowych funkcji.

Przejdź do usługi Intune w witrynie Azure Portal i wyświetl obszar Urządzenia > Wszystkie urządzenia. Przefiltruj widok według wersji systemu iOS, aby wyświetlić wszystkie bieżące urządzenia z systemami operacyjnymi wcześniejszym niż iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS.

Udostępniliśmy wersję aplikacji Portal firmy dla systemu iOS przy użyciu programu Apple TestFlight, który wymusza nowe wymagania ATS. Jeśli chcesz ją wypróbować, aby sprawdzić swoją zgodność z ATS, wyślij na adres e-mail <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> wiadomość ze swoim imieniem i nazwiskiem, adresem e-mail i nazwą firmy. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

## <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
