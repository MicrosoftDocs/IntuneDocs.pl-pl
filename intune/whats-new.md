---
title: "Co nowego w usłudze Microsoft Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, co nowego w witrynie Azure Portal usługi Intune"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f915c805b20e88c661ad52e280a31054bbebce02
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również dowiedzieć się o [nadchodzących zmianach](#whats-coming), [ważnych powiadomieniach](#notices) o usłudze oraz uzyskać informacje o [poprzednich wersjach](whats-new-archive.md).

> [!Note]
> Wiele z tych funkcji będzie również w przyszłości obsługiwane dla wdrożeń hybrydowych przy użyciu programu Configuration Manager. Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Intune apps
-->   

## <a name="week-of-july-31-2017"></a>Tydzień od 31 lipca 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Wprowadzanie ograniczeń rejestracji urządzeń z systemem Android lub iOS na podstawie wersji systemu operacyjnego <!--- 1333256,  1245463 --->
Usługa Intune obsługuje teraz ograniczanie rejestracji urządzeń z systemem Android lub iOS na podstawie numeru wersji systemu operacyjnego. W obszarze **Ograniczenie typu urządzenia** administrator IT może teraz ustawić konfigurację platformy w taki sposób, aby ograniczyć rejestrację, podając minimalną i maksymalną dopuszczalną wartość systemu operacyjnego. Wersje systemu operacyjnego Android muszą być określone jako wersja_główna.wersja_pomocnicza.kompilacja.wydanie, gdzie wersja_pomocnicza, kompilacja i wydanie są opcjonalne. Wersje systemu operacyjnego iOS muszą być określone jako wersja_główna.wersja_pomocnicza.kompilacja, gdzie wersja_pomocnicza i kompilacja są opcjonalne. Dowiedz się więcej o [ograniczeniach rejestracji urządzenia](enrollment-restrictions-set.md).

>[!NOTE]
>Nie ograniczaj rejestracji za pomocą programów rejestracji firmy Apple lub narzędzia Apple Configurator.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Ograniczanie rejestracji urządzeń osobistych z systemem Android, iOS lub macOS <!--- 1333272,  1333275, 1245709 --->
Usługa Intune może ograniczać rejestrację urządzenia osobistego, stosując białą listę numerów IMEI urządzeń firmowych. Ta funkcjonalność usługi Intune została teraz rozszerzona na systemy iOS, Android i macOS przy użyciu numerów seryjnych urządzeń. Przekazanie numerów seryjnych do usługi Intune pozwala wstępnie zadeklarować urządzenia jako firmowe. Ograniczenia rejestracji umożliwiają blokowanie urządzeń osobistych („Przynieś własne urządzenie” — BYOD), aby umożliwić rejestrację tylko dla urządzeń należących do firmy. Dowiedz się więcej o [ograniczeniach rejestracji urządzenia](enrollment-restrictions-set.md).

Aby zaimportować numery seryjne, przejdź do pozycji **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych** i kliknij pozycję **Dodaj**, a następnie przekaż plik CSV (bez nagłówka, dwie kolumny numeru seryjnego i szczegóły, takie jak numery IMEI).  Aby ograniczyć urządzenia osobiste, przejdź do lokalizacji **Rejestracja urządzeń**  >  **Ograniczenia rejestracji**. W obszarze **Ograniczenia typu urządzeń** wybierz pozycję **Domyślne**, a następnie wybierz pozycję **Konfiguracje platform**. Możesz wybrać pozycję **Zezwalaj** lub **Blokuj** dla urządzeń osobistych z systemem iOS, Android lub macOS. 


### <a name="device-management"></a>Zarządzanie urządzeniami   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nowa akcja urządzenia wymuszająca synchronizację urządzeń z usługą Intune <!-- 711369 -->
W tym wydaniu dodaliśmy nową akcję urządzenia, która wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady.  Ta akcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane ewidencjonowanie.
Aby uzyskać więcej informacji, zobacz [Synchronize device (Synchronizowanie urządzenia)](device-sync.md)

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS <!-- 777100 -->
W obszarze roboczym aktualizacji oprogramowania są dostępne nowe zasady, które umożliwiają wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS. Aby uzyskać więcej informacji, zobacz [Configure iOS update policies (Konfigurowanie zasad aktualizacji systemu iOS)](/intune/software-updates-ios)


#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile — nowy partner usługi Mobile Threat Defense <!-- 954651, 1172027 -->
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Checkpoint SandBlast Mobile. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzenia przenośne zintegrowane z usługą Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune?
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Checkpoint SandBlast Mobile. Zasady dostępu warunkowego usług EMS możesz skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Checkpoint SandBlast Mobile włączane przy użyciu zasad zgodności urządzeń usługi Intune. Możesz zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia.


### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Wdrażanie aplikacji jako dostępnych w Sklepie Microsoft dla Firm <!-- 748101 -->
W tej wersji administratorzy mogą teraz przypisać Sklep Microsoft dla Firm jako dostępny. W przypadku ustawienia jako dostępny użytkownicy końcowi mogą zainstalować aplikację z aplikacji Portal firmy lub witryny internetowej bez przekierowania do sklepu Microsoft.


### <a name="intune-apps"></a>Aplikacje usługi Intune  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizacje interfejsu użytkownika witryny internetowej Portal firmy <!--1313244 part 1-->
Wprowadziliśmy kilka aktualizacji interfejsu użytkownika [witryny internetowej Portal firmy](https://portal.manage.microsoft.com) w celu ulepszenia środowiska użytkownika końcowego.

- __Ulepszenia kafelków aplikacji__ — ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem określanym na podstawie dominującego koloru ikony (jeśli można będzie go wykryć). O ile będzie to miało zastosowanie, to tło zastąpi szare obramowanie, które było wcześniej widoczne na kafelkach aplikacji.

    Witryna internetowa Portal firmy wyświetla w nadchodzącej wersji duże ikony, jeśli tylko to możliwe. Zalecamy, aby administratorzy IT podczas publikowania aplikacji korzystali z ikon o wysokiej rozdzielczości o rozmiarze co najmniej 120 x 120 pikseli. 

- __Zmiany nawigacji__ — elementy paska nawigacji zostały przeniesione do menu typu „hamburger” znajdującego się w lewym górnym rogu. Strona Kategorie została usunięta. Użytkownicy mogą teraz filtrować zawartość według kategorii podczas przeglądania.

- __Aktualizacje sekcji Polecane aplikacje__ — do witryny dodaliśmy dedykowaną stronę, na której użytkownicy mogą przeglądać aplikacje wybrane przez Ciebie do polecania. Dostosowaliśmy również interfejs użytkownika w sekcji Polecane na stronie głównej.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Obsługa aplikacji iBooks w witrynie internetowej Portal firmy <!--1231841-->
Dodaliśmy dedykowaną stronę do witryny internetowej Portal firmy, która umożliwia użytkownikom przeglądanie i pobieranie plików iBooks. 

### <a name="reporting"></a>Raportowanie

#### <a name="intune-data-warehouse-public-preview"></a>Magazyn danych usługi Intune (publiczna wersja zapoznawcza)

Magazyn danych usługi Intune każdego dnia próbkuje dane, aby przedstawić widok historyczny Twojej dzierżawy. Możesz uzyskać dostęp do danych za pomocą pliku usługi Power BI (PBIX), linku usługi OData, która jest zgodna z wieloma narzędziami analitycznymi, lub interakcji z interfejsem API REST. Aby uzyskać więcej informacji, zobacz [Korzystanie z magazynu danych usługi Intune](reports-nav-create-intune-reports.md).


## <a name="week-of-july-23rd-2017"></a>Tydzień od 23 lipca 2017 r.

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Tryb jasny i ciemny dostępne dla aplikacji Portal firmy dla systemu Windows 10 <!---676547--->
Użytkownicy końcowi będą mogli dostosować tryb kolorów aplikacji Portal firmy dla systemu Windows 10. Użytkownik będzie mógł wprowadzić zmiany w sekcji Ustawienia w aplikacji Portal firmy. Zmiana zostanie zastosowana po ponownym uruchomieniu aplikacji przez użytkownika. W przypadku systemu Windows 10 w wersji 1607 lub nowszej domyślnie będzie używany tryb aplikacji określony w ustawieniach systemowych. W przypadku systemu Windows 10 w wersji 1511 lub wcześniejszej domyślnie będzie używany jasny tryb aplikacji.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Umożliwianie użytkownikom tagowania grupy urządzeń w aplikacji Portal firmy dla systemu Windows 10 <!---807046-->
Użytkownicy końcowi mogą teraz wybrać grupę, do której ma należeć ich urządzenie, przez otagowanie jej bezpośrednio z poziomu aplikacji Portal firmy dla systemu Windows 10.




## <a name="notices"></a>Uwagi

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Zaktualizowano adresy IP dla usługi Intune <!-- 1175274 -->
[Zaktualizowana lista nazw DNS i adresów IP](/intune/network-bandwidth-use) jest dostępna dla ustawień serwera proxy zapory.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Używanie usługi Azure Active Directory do dostępu warunkowego <!-- 967947 -->
Dostęp warunkowy jest dostępny w sekcji usługi Azure Active Directory konsoli platformy Azure i zapewnia bardziej wydajną i elastyczną platformę do ustawiania zasad dla aplikacji w chmurze, takich jak Office 365 Exchange Online i SharePoint Online.  Użyj bloku **Dostęp warunkowy w usłudze Azure Active Directory**, zamiast klasycznej konsoli usługi Intune, aby skonfigurować zasady. Zasady istniejące w klasycznej konsoli usługi Intune trzeba utworzyć ponownie w konsoli platformy Azure. Aby uzyskać więcej informacji, zobacz temat [Tworzenie zasad dostępu warunkowego w usłudze Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 roku wymagają przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do witryny Azure portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal
Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Wkrótce

### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!---1164477--->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Aktualizacje interfejsu użytkownika witryny internetowej Portal firmy <!--1313244 part 2-->
__Aktualizacje sekcji Polecane aplikacje__  
Do witryny dodaliśmy dedykowaną stronę, na której użytkownicy mogą przeglądać aplikacje wybrane przez Ciebie do polecania. Dostosowaliśmy również interfejs użytkownika w sekcji Polecane na stronie głównej. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!---1171127, 1326920 --->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane przed początkiem października, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Przypomnienie dotyczące obsługi platformy: wsparcie podstawowe dla systemu Windows Phone 8.1 zakończyło się 11 lipca 2017 r.
<!-- 1327781 -->
11 lipca 2017 r. zakończyło się wsparcie podstawowe dla platformy Windows Phone 8.1. Nie ma to wpływu na pomoc techniczną dla komputerów z systemem Windows 8.1.

Nie ma to bezpośredniego wpływu na urządzenia z systemem Windows Phone 8.1 zarządzane przez usługę Intune. Zarejestrowane urządzenia będą nadal działać, a wszystkie zasady, konfiguracje i aplikacje będą nadal działać zgodnie z oczekiwaniami. Nie ma żadnych ulepszeń przeznaczonych dla platformy Windows Phone 8.1 w usłudze Intune ani dla aplikacji Portal firmy systemu Windows Phone 8.1.

Zalecamy możliwie najwcześniejsze uaktualnienie kwalifikujących się urządzeń z systemem Windows Phone 8.1 do systemu Windows 10 Mobile. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS w usłudze Intune <!-- 1164474  -->
Wkrótce pojawi się nowa wersja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która obejmie tylko urządzenia z systemem iOS 9.0 lub nowszym. Wersja aplikacji Portal firmy obsługująca system iOS 8 będzie przez krótki okres nadal dostępna. Jeśli jednak są również używane aplikacje systemu iOS z obsługą funkcji MAM, obsługiwany jest system iOS 9.0 i nowsze wersje, więc należy zadbać o to, aby użytkownicy końcowi zaktualizowali system operacyjny do najnowszej wersji. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Informujemy o tym z wyprzedzeniem, mimo że nie podajemy konkretnych dat, aby zapewnić klientom czas na zaplanowanie działań. Zadbaj o to, aby użytkownicy zaktualizowali system do wersji iOS 9 lub nowszej, a po opublikowaniu aplikacji Portal firmy zwróć się do użytkowników końcowych o zaktualizowanie aplikacji Portal firmy.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Zalecamy powiadomienie użytkowników, aby przeprowadzili aktualizację do wersji iOS 9.0 lub nowszej w celu pełnego korzystania z nowych funkcji usługi Intune.  Zachęć użytkowników do zainstalowania nowej wersji aplikacji Portal firmy i korzystania z dostępnych w niej nowych funkcji.

Przejdź do usługi Intune w witrynie Azure Portal i wyświetl obszar Urządzenia > Wszystkie urządzenia. Przefiltruj widok według wersji systemu iOS, aby wyświetlić wszystkie bieżące urządzenia z systemami operacyjnymi wcześniejszym niż iOS 9.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planowane zmiany: zmiany w usłudze Intune dotyczące witryny Intune Partner Portal <!-- 1050016 -->
Wraz z aktualizacją usługi w połowie maja 2017 r. strona Intune Partner zostanie usunięta z witryny manage.microsoft.com.  

Administratorzy partnerów nie będą już mogli wyświetlać strony Intune Partner ani podejmować na niej działań w imieniu swoich klientów. Zamiast tego konieczne będzie zalogowanie się w jednym z dwóch innych portali firmy Microsoft dla partnerów.

Logowanie się na zarządzane konta klientów będzie możliwe zarówno w [Centrum partnerskim firmy Microsoft](https://partnercenter.microsoft.com/), jak i w [Centrum administracyjnym dla partnerów usługi Microsoft Office 365](https://portal.office.com/). Aby kontynuować czynności partnerskie, należy korzystać z dowolnej z tych witryn do zarządzania klientami.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS.

Udostępniliśmy wersję aplikacji Portal firmy dla systemu iOS przy użyciu programu Apple TestFlight, który wymusza nowe wymagania ATS. Jeśli chcesz ją wypróbować, aby sprawdzić swoją zgodność z ATS, wyślij na adres e-mail <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> wiadomość ze swoim imieniem i nazwiskiem, adresem e-mail i nazwą firmy. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
