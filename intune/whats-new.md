---
title: "Co nowego w usłudze Microsoft Intune"
titlesuffix: Azure portal
description: "Dowiedz się, co nowego w witrynie Azure Portal usługi Intune"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/18/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d48664186b1914d30757557bd97d3d61b6410338
ms.sourcegitcommit: 695bf70a79e20a17168c061afbb675b73ea999f7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2017
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

## <a name="week-of-september-11-2017"></a>Tydzień 11 września 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-o----1475932---"></a>Dodatkowe powiadomienia wypychane dla użytkowników końcowych w aplikacji Portal firmy dla systemu Android O <!---1475932--->

Użytkownicy końcowi będą widzieli dodatkowe powiadomienia, gdy aplikacja Portal firmy dla systemu Android O wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune. Powoduje to zwiększenie przejrzystości dla użytkowników końcowych przez informowanie ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na ich urządzeniach. Jest to część ogólnej [optymalizacji interfejsu użytkownika aplikacji Portal firmy](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) dla aplikacji Portal firmy dla systemu Android O. 

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Powiadamianie użytkowników końcowych, o widocznych w systemie iOS informacjach o urządzeniu <!--739894--> 

Dodaliśmy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu iOS. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie Informacje. 

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zezwalanie użytkownikom na dostęp do aplikacji Portal firmy dla systemu Android bez rejestracji <!---1169910--->

Wkrótce użytkownicy końcowi nie będą musieli rejestrować urządzeń, aby uzyskać dostęp do aplikacji Portal firmy dla systemu Android. Użytkownicy końcowi w organizacjach używających zasad ochrony aplikacji nie będą już otrzymywać monitów o zarejestrowanie swoich urządzeń po otwarciu aplikacji Portal firmy. Ponadto użytkownicy końcowi będą mogli instalować aplikacje z poziomu aplikacji Portal firmy bez konieczności rejestrowania urządzeń. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Bardziej zrozumiałe komunikaty w aplikacji Portal firmy dla systemu Android <!---1396349--->  

Proces rejestracji w aplikacji Portal firmy dla systemu Android został uproszczony poprzez dodanie nowego tekstu w celu ułatwienia użytkownikom końcowym przeprowadzenia procesu rejestracji. Jeśli masz dokumentację rejestracji niestandardowej, możesz ją zaktualizować, aby odzwierciedlić nowe ekrany. Przykładowe obrazy można znaleźć na naszej stronie [aktualizacji interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune](whats-new-app-ui.md#week-of-september-11-2017).

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Dodanie aplikacji Portal firmy dla systemu Windows 10 do zasad zezwoleń funkcji Windows Information Protection <!-- 677129 -->

Aplikacja Portal firmy dla systemu Windows 10 została zaktualizowana w celu umożliwienia obsługi funkcji Windows Information Protection (WIP). Aplikację można dodać do zasad zezwoleń funkcji WIP. Dzięki tej zmianie nie trzeba dodawać żadnych aplikacji do listy **Wyklucz**. 


## <a name="week-of-august-21-2017"></a>Tydzień od 21 sierpnia 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń
#### <a name="improvements-to-device-overview----1404453---"></a>Ulepszenia w zakresie przeglądu urządzeń <!-- 1404453 -->  
Dzięki ulepszeniom przegląd urządzeń wyświetla teraz zarejestrowane urządzenia, ale pomija urządzenia zarządzane przez program Exchange ActiveSync. Urządzenia programu Exchange ActiveSync nie mają tych samych opcji zarządzania co zarejestrowane urządzenia. Aby wyświetlić liczbę zarejestrowanych urządzeń i liczbę zarejestrowanych urządzeń według platformy, w usłudze Intune w witrynie Azure Portal przejdź do pozycji **Urządzenia** > **Przegląd**.

### <a name="device-management"></a>Zarządzanie urządzeniami
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Ulepszenia dotyczące spisu urządzeń zebranego przez usługę Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
W tym przypadku wprowadziliśmy następujące ulepszenia dotyczące informacji o spisie zbieranych przez zarządzane urządzenia:
 
-   W przypadku urządzeń z systemem Android możesz teraz dodać do spisu urządzeń kolumnę wyświetlającą poziom ostatniej poprawki dla każdego urządzenia. Dodaj kolumnę **Poziom poprawek bezpieczeństwa** do listy urządzeń, aby to zobaczyć.
-   Podczas filtrowania widoku urządzeń możesz teraz filtrować urządzenia według daty ich zarejestrowania. Możesz na przykład wyświetlić tylko urządzenia, które zostały zarejestrowane po określonej dacie.
-   Wprowadziliśmy ulepszenia dotyczące filtra używanego przez element **Data ostatniego zaewidencjonowania**.
-   Na liście urządzeń możesz teraz wyświetlić numery telefonów urządzeń będących własnością firmy.
Ponadto przy użyciu okienka filtru możesz wyszukiwać urządzenia według numeru telefonu.
 
Aby uzyskać więcej informacji na temat spisu urządzeń, zobacz [Jak wyświetlać spis urządzeń usługi Intune](device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>Obsługa dostępu warunkowego w przypadku urządzeń z systemem macOS 
<!-- 720172 -->
Możesz teraz ustawić zasady dostępu warunkowego, które wymagają zarejestrowania urządzeń Mac w usłudze Intune i ich zgodności z zasadami zgodności urządzeń usługi Intune. Na przykład użytkownicy mogą pobrać aplikację Portal firmy w usłudze Intune dla systemu macOS i zarejestrować swoje urządzenia Mac w usłudze Intune. Usługa Intune ocenia, czy urządzenie Mac jest zgodne z wymaganiami, między innymi przez sprawdzenie numeru PIN, szyfrowania, wersji systemu operacyjnego i integralności systemu.

- Dowiedz się więcej o [obsłudze dostępu warunkowego w przypadku urządzeń z systemem macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikacja Portal firmy dla urządzeń z systemem macOS jest dostępna w publicznej wersji zapoznawczej <!---1484796--->
Aplikacja Portal firmy dla urządzeń z systemem macOS jest teraz dostępna w ramach publicznej wersji zapoznawczej dostępu warunkowego pakietu Enterprise Mobility + Security. Ta wersja obsługuje system macOS w wersji 10.11 i nowszych. Pobierz aplikację: [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Nowe ustawienia ograniczeń urządzenia z systemem Windows 10    
<!--1063965, 1308850  -->
W tej wersji dodano nowe ustawienia profilu [ograniczeń urządzenia z systemem Windows 10](/intune/device-restrictions-windows-10) w następujących kategoriach:

-   Windows Defender SmartScreen
-   App Store

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizacje profilu urządzenia usługi Endpoint Protection dla systemu Windows 10 dla ustawień funkcji BitLocker
<!--1459533 -->    
W tej wersji wprowadziliśmy następujące ulepszenia dotyczące sposobu działania ustawień funkcji BitLocker w profilu urządzenia usługi Endpoint Protection dla systemu Windows 10:
 
W obszarze **Ustawienia funkcji BitLocker dla dysku systemu operacyjnego** wybranie wartości **Blokuj** dla ustawienia **Funkcja BitLocker z niezgodnym modułem TPM** w rzeczywistości zezwalało na używanie funkcji BitLocker. Ten błąd został rozwiązany i funkcja BitLocker jest blokowana, gdy zostanie wybrane odpowiednie ustawienie.
W obszarze **Ustawienia funkcji BitLocker dla dysku systemu operacyjnego** w przypadku ustawienia **Agent odzyskiwania danych oparty na certyfikatach** możesz teraz jawnie blokować agenta odzyskiwania danych opartego na certyfikatach. Jednak domyślnie agent nie jest blokowany.
W obszarze **Ustawienia stałych dysków danych w funkcji BitLocker** w przypadku ustawienia **Agent odzyskiwania danych ** możesz teraz jawnie blokować agenta odzyskiwania danych.
Aby uzyskać więcej informacji, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji](endpoint-protection-windows-10.md).


### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nowe środowisko logowania dla użytkowników aplikacji Portal firmy w systemie Android i użytkowników zasady ochrony aplikacji <!-- 621669 -->
Użytkownicy końcowi mogą teraz przeglądać aplikacje, zarządzać urządzeniami i wyświetlać informacje kontaktowe dla działu IT przy użyciu aplikacji Portal firmy dla systemu Android bez rejestrowania urządzeń z systemem Android. Ponadto jeśli użytkownik końcowy używa aplikacji chronionej przez zasady usługi Intune App Protection i uruchamia Portal firmy dla systemu Android, nie otrzymuje już monitu o zarejestrowanie urządzenia.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nowe ustawienie w aplikacji Portal firmy dla systemu Android umożliwiające przełączanie optymalizacji baterii <!--1405990-->
Strona **Ustawienia** w aplikacji Portal firmy dla systemu Android zawiera nowe ustawienie, które umożliwia użytkownikom proste wyłączanie optymalizacji baterii dla aplikacji Portal firmy i Microsoft Authenticator. Nazwa aplikacji wyświetlana w ustawieniu będzie różnić się w zależności od aplikacji, która zarządza kontem służbowym. Zalecamy, aby użytkownicy wyłączali optymalizację baterii w celu poprawy wydajności aplikacji służbowych, które synchronizują pocztę e-mail i dane. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Obsługa wielu tożsamości w programie OneNote dla systemu iOS      <!-- 1234281 -->
Użytkownicy końcowi mogą teraz używać w programie OneNote dla systemu iOS różnych kont (służbowych i osobistych). Zasady ochrony aplikacji można stosować do danych firmowych w notesach służbowych bez wpływu na notesy osobiste. Zasady mogą na przykład zezwalać użytkownikowi na wyszukiwanie informacji w notesie służbowym, ale uniemożliwią kopiowanie i wklejanie danych firmowych z notesu służbowego do notesu osobistego.
 
- Dowiedz się więcej o aplikacjach, które obsługują [ochronę aplikacji i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nowe ustawienia umożliwiające zezwalanie na działanie aplikacji i ich blokowanie na urządzeniach z systemem Samsung KNOX Standard
<!-- 1305423 822899-->  
W tej wersji dodajemy nowe [ustawienia ograniczeń urządzeń](device-restrictions-android.md) pozwalające określić następujące listy aplikacji:
 
- Aplikacje, które użytkownicy mogą instalować
- Aplikacje, których użytkownicy nie mogą uruchamiać
- Aplikacje ukryte przed użytkownikiem na urządzeniu
 
Możesz określić aplikacji przy użyciu adresu URL, nazwy pakietu lub zarządzanej przez Ciebie listy aplikacji.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link do nowego opartego na aplikacji interfejsu użytkownika zasad dostępu warunkowego usługi Azure AD z usługi Intune
<!-- 1016201 -->
Administratorzy IT mogą teraz ustawiać zasady dostępu warunkowego opartego na aplikacji za pomocą nowego interfejsu użytkownika zasad dostępu warunkowego w obciążeniu usługi Azure AD. Dostęp warunkowy oparty na aplikacji, który znajduje się w sekcji usługi Intune App Protection w witrynie Azure Portal, pozostanie w tym miejscu i będzie wymuszany równolegle. Wygodny link do nowego interfejsu użytkownika zasad dostępu warunkowego jest dostępny z poziomu obciążenia usługi Intune.

- Dowiedz się więcej o [dostępie warunkowym opartym na aplikacji w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).


## <a name="notices"></a>Uwagi

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Zaktualizowano adresy IP dla usługi Intune <!-- 1175274 -->
[Zaktualizowana lista nazw DNS i adresów IP](/intune/network-bandwidth-use) jest dostępna dla ustawień serwera proxy zapory.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Używanie usługi Azure Active Directory do dostępu warunkowego <!-- 967947 -->
Dostęp warunkowy jest dostępny w sekcji usługi Azure Active Directory witryny Azure Portal i zapewnia bardziej wydajną i elastyczną platformę do ustawiania zasad dla aplikacji w chmurze, takich jak Office 365 Exchange Online i SharePoint Online.  Użyj bloku **Dostęp warunkowy w usłudze Azure Active Directory** zamiast konsoli usługi Intune, aby skonfigurować zasady. Zasady istniejące w konsoli usługi Intune trzeba utworzyć ponownie w witrynie Azure Portal. Aby uzyskać więcej informacji, zobacz temat [Tworzenie zasad dostępu warunkowego w usłudze Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 roku wymagają przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do witryny Azure portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal
Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Wkrótce

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>Aplikacja Mail dla systemu iOS 11 będzie obsługiwać protokół OAuth <!---1196951--->
Dostęp warunkowy przy użyciu usługi Intune obsługuje bezpieczniejsze uwierzytelnianie na urządzeniach z systemem iOS przy użyciu protokołu OAuth. W aplikacji Portal firmy będzie dostępny inny przepływ dla systemu iOS umożliwiający bezpieczniejsze uwierzytelnianie. Gdy użytkownicy końcowi spróbują się zalogować do nowego konta programu Exchange w aplikacji Mail, zostanie im wyświetlony monit widoku internetowego. Po rejestracji w usłudze Intune użytkownikom zostanie wyświetlony monit o zezwolenie natywnej aplikacji Mail na dostęp do certyfikatu. Większość użytkowników końcowych nie zobaczy już żadnych wiadomości e-mail poddanych kwarantannie. Istniejące konta e-mail nadal będą korzystać z podstawowego protokołu uwierzytelniania, więc ci użytkownicy wciąż będą otrzymywać wiadomości e-mail poddane kwarantannie. Środowisko logowania dla użytkowników końcowych jest podobne do tego w aplikacjach mobilnych pakietu Office.

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


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS.

Udostępniliśmy wersję aplikacji Portal firmy dla systemu iOS przy użyciu programu Apple TestFlight, który wymusza nowe wymagania ATS. Jeśli chcesz ją wypróbować, aby sprawdzić swoją zgodność z ATS, wyślij na adres e-mail <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> wiadomość ze swoim imieniem i nazwiskiem, adresem e-mail i nazwą firmy. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
