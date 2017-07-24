---
title: Wczesna wersja
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b8d281e3af2458bd5ab343dfa5123b31075d28ed
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2017
---
# <a name="the-early-edition-for-microsoft-intune---july-2017"></a>Wczesna wersja usługi Microsoft Intune — lipiec 2017

**Wczesna wersja** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane w bardzo ograniczonym zakresie i mogą ulec zmianie. Nie należy udostępniać tych informacji poza firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
>Dla usługi Intune opracowywane są następujące zmiany. Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>usługa Intune w witrynie Azure Portal

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Łatwiejsza instalacja aplikacji usługi Office 365 <!--- 1121362 --->
Nowy typ aplikacji usługi **Office 365 ProPlus** ułatwia przypisywanie aplikacji usługi Office 365 ProPlus do zarządzanych urządzeń z najnowszą wersją systemu Windows 10. Ponadto użytkownicy posiadający licencje na programy Microsoft Project i Microsoft Visio będą mogli je zainstalować. Aplikacje są ze sobą powiązane i będą wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nowa akcja urządzenia wymuszająca synchronizację urządzeń z usługą Intune <!-- 711369 -->    
Dodajemy nową akcję urządzenia, która wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady.  Ta akcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane ewidencjonowanie.

### <a name="actions-for-non-compliance----730266--"></a>Akcje w przypadku niezgodności <!--730266-->     
*Akcje w przypadku niezgodności* to nowa funkcja zasad zgodności, która umożliwia podejmowanie akcji na urządzeniach, które są niezgodne. Możesz określić jedną lub wiele akcji oraz przedział czasu, w którym te akcje muszą zostać wykonane. Na przykład możesz za pomocą poczty e-mail powiadomić użytkowników niezgodnych urządzeń, gdy tylko ich urządzenia staną się niezgodne, lub za pośrednictwem dostępu warunkowego zablokować niezgodnym urządzeniom dostęp do zasobów firmowych po 3-dniowym okresie karencji.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser-----682951----"></a>Nowe ustawienia konfiguracji aplikacji dla Intune Managed Browser<!--- 682951 --->
Dodamy kolejne konfiguracje dla aplikacji Intune Managed Browser. Będzie można skonfigurować domyślną stronę główną i zakładki do przeglądarki przy użyciu zasad konfiguracji aplikacji.

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Wprowadzanie ograniczeń rejestracji urządzeń z systemem Android lub iOS na podstawie wersji systemu operacyjnego <!--- 1333256,  1245463 --->  
Usługa Intune obsługuje teraz ograniczanie rejestracji urządzeń z systemem Android lub iOS na podstawie numeru wersji systemu operacyjnego. W obszarze **Intune**  >  **Ograniczenia rejestracji**  >  **Ograniczenie typu urządzenia**  >  **Domyślne**  >  **Ograniczenia platformy** administrator IT może teraz ustawić konfigurację platformy tak, aby ograniczyć rejestrację, podając minimalną i maksymalną dopuszczalną wartość systemu operacyjnego. Wersje systemu operacyjnego Android muszą być określone w formacie wersja_główna.wersja_pomocnicza.kompilacja.poprawka, gdzie wersja główna i poprawka są opcjonalne. Wersje systemu iOS muszą być określone w formacie wersja_główna.wersja_pomocnicza.kompilacja, gdzie kompilacja jest opcjonalna.

>[!NOTE]
>To ustawienie nie ogranicza rejestracji w ramach programów rejestracji firmy Apple, które obejmują program Device Enrollment Program firmy Apple i usługę Apple School Manager, i programu Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Ograniczanie rejestracji urządzeń osobistych z systemem Android, iOS lub macOS <!--- 1333272,  1333275, 1245709 --->
Usługa Intune obsługuje teraz ograniczanie rejestracji urządzeń osobistych z systemem iOS, Android lub macOS przy użyciu numerów seryjnych urządzeń. Niektóre urządzenia nie zgłaszają numerów seryjnych. Aby uzyskać szczegółowe informacje, skontaktuj się z producentami urządzeń. Przekazanie numerów seryjnych do usługi Intune pozwala wstępnie zadeklarować urządzenia jako firmowe. Ograniczenia rejestracji umożliwiają blokowanie urządzeń osobistych („Przynieś własne urządzenie” — BYOD), aby umożliwić rejestrację tylko dla urządzeń należących do firmy.

Aby zaimportować numery seryjne w portalu usługi Intune, przejdź do lokalizacji **Rejestracja urządzeń**  >  **Identyfikatory urządzeń firmowych** i kliknij pozycję **Dodaj**, a następnie przekaż plik CSV (bez nagłówka, dwóch kolumn numeru seryjnego i takich szczegółów jak numery IMEI).  Aby ograniczyć urządzenia osobiste, przejdź do lokalizacji **Rejestracja urządzeń**  >  **Ograniczenia rejestracji**. W obszarze **Ograniczenia typu urządzeń** wybierz pozycję **Domyślne**, a następnie wybierz pozycję **Konfiguracje platform**. Możesz wybrać pozycję **Zezwalaj** lub **Blokuj** dla urządzeń osobistych z systemem iOS, Android lub macOS. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS <!-- 777100 -->   
W obszarze roboczym aktualizacji oprogramowania będą dostępne nowe zasady, które będą umożliwiać wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS. Ponadto będzie można wyświetlić nowy raport dotyczący urządzeń ze starszymi wersjami systemu iOS oraz podsumowanie z przyczynami ich nieaktualności.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Nowe ustawienia umożliwiające zezwalanie na działanie aplikacji i ich blokowanie na urządzeniach z systemem Samsung KNOX Standard <!-- 822899,  1305423-->   
Dodajemy nowe [ustawienia ograniczeń urządzeń](device-restrictions-android.md) pozwalające określić następujące listy aplikacji:
  - Aplikacje, które użytkownicy mogą instalować
  - Aplikacje, których użytkownicy nie mogą uruchamiać
  - Aplikacje ukryte przed użytkownikiem na urządzeniu  

Możesz określić aplikacji przy użyciu adresu URL, nazwy pakietu lub zarządzanej przez Ciebie listy aplikacji.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Obsługa programu Android for Work dla usługi Lookout <!-- 1087312 -->   
Łącznik usługi Intune z usługą Lookout będzie obsługiwać urządzenia z programem Android for Work w przypadku korzystania z aplikacji Lookout for Work. Będzie można wdrożyć aplikację Lookout wewnątrz lub na zewnątrz kontenera.


### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651--and--1172027----"></a>Check Point SandBlast Mobile — nowy partner usługi Mobile Threat Defense <!-- 954651  and  1172027 ? -->  
Dostęp urządzeń przenośnych do zasobów firmy będzie można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Check Point SandBlast Mobile. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune?
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Check Point SandBlast Mobile. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Check Point SandBlast Mobile włączane przy użyciu zasad zgodności urządzeń usługi Intune. Możesz zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium — nowy partner usługi Mobile Threat Defense <!-- 954681 -->
Dostęp urządzeń przenośnych do zasobów firmy będzie można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune?
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->   
Będzie można mieć wiele ról serwera dostępu klienta (CAS) dla łącznika lokalnego programu Exchange. Jeśli na przykład główny serwer dostępu klienta ulegnie awarii, łącznik programu Exchange odbierze zapytanie w celu powrotu do innych serwerów dostępu klienta. Ta funkcja pozwala zagwarantować nieprzerwane działanie usługi.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->   
Pakiet administracyjny programu System Center Operations Manager dla łącznika programu Exchange będzie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Zapewni to różne sposoby monitorowania usługi Intune w przypadku konieczności rozwiązywania problemów.

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Obsługa dostępu warunkowego w przypadku urządzeń Mac <!-- 720172 -->   
Wkrótce będzie można ustawić zasady dostępu warunkowego, które wymagają zarejestrowania urządzeń Mac w usłudze Intune i ich zgodności z zasadami zgodności urządzeń usługi Intune. Na przykład użytkownicy mogą pobrać aplikację Portal firmy w usłudze Intune dla systemu macOS i zarejestrować swoje urządzenia Mac w usłudze Intune. Usługa Intune ocenia, czy urządzenie Mac jest zgodne z wymaganiami, między innymi przez sprawdzenie numeru PIN, szyfrowania, wersji systemu operacyjnego i integralności systemu.

### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!---1164477--->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. Od grudnia zostanie zablokowany dostęp do wszystkich zasobów firmy, w tym wiadomości e-mail. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!---1171127, 1326920 --->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane przed początkiem października, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.





### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Przypomnienie dotyczące obsługi platformy: podstawowa obsługa systemu Windows Phone 8.1 zakończy się 11 lipca 2017 r. <!-- 1327781 -->  
11 lipca 2017 r. zakończy się wsparcie podstawowe dla platformy Windows Phone 8.1. Nie ma to wpływu na pomoc techniczną dla komputerów z systemem Windows 8.1.

Nie ma to bezpośredniego wpływu na urządzenia z systemem Windows Phone 8.1 zarządzane przez usługę Intune. Zarejestrowane urządzenia będą nadal działać, a wszystkie zasady, konfiguracje i aplikacje będą nadal działać zgodnie z oczekiwaniami. Nie ma żadnych ulepszeń przeznaczonych dla platformy Windows Phone 8.1 w usłudze Intune ani dla aplikacji Portal firmy systemu Windows Phone 8.1.

Zalecamy możliwie najwcześniejsze uaktualnienie kwalifikujących się urządzeń z systemem Windows Phone 8.1 do systemu Windows 10 Mobile. 




## <a name="intune-apps"></a>Aplikacje usługi Intune

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Ulepszone środowisko logowania w aplikacjach Portalu firmy dla wszystkich platform <!--User Story 1132123-->    
Informujemy o zmianie, która zostanie wprowadzona w ciągu następnych kilku miesięcy i ułatwi logowanie w aplikacjach Portal firmy w usłudze Intune dla systemów Android, iOS i Windows. Nowe środowisko użytkownika zostanie udostępnione automatycznie na wszystkich platformach aplikacji Portal firmy, gdy zmiana ta zostanie wprowadzona w usłudze Azure AD. Ponadto użytkownicy mogą teraz logować się do Portalu firmy za pomocą innego urządzenia, korzystając z wygenerowanego kodu jednorazowego. Ta opcja jest szczególnie przydatna w sytuacji, gdy niezbędne jest zalogowanie się bez użycia poświadczeń.

Zrzuty ekranu przedstawiające poprzednie środowisko logowania, nowe środowisko logowania z poświadczeniami oraz nowe środowisko logowania za pomocą innego urządzenia można znaleźć na stronie [Co nowego w interfejsie aplikacji](whats-new-app-ui.md).

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Tryb jasny i ciemny dostępne dla aplikacji Portal firmy dla systemu Windows 10 <!---676547--->
Użytkownicy końcowi będą mogli dostosować tryb kolorów aplikacji Portal firmy dla systemu Windows 10. Użytkownik będzie mógł wprowadzić zmiany w sekcji Ustawienia w aplikacji Portal firmy. Zmiana zostanie zastosowana po ponownym uruchomieniu aplikacji przez użytkownika. W przypadku systemu Windows 10 w wersji 1607 lub nowszej domyślnie jest używany tryb aplikacji określony w ustawieniach systemowych. W przypadku komputerów z systemem Windows 10 w wersji 1511 lub wcześniejszej domyślnie jest używany jasny tryb aplikacji.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Umożliwianie użytkownikom tagowania grupy urządzeń w aplikacji Portal firmy dla systemu Windows 10 <!---807046-->    
Użytkownicy końcowi będą mogli wybrać grupę, do której ma należeć ich urządzenie, przez otagowanie jej bezpośrednio z poziomu aplikacji Portal firmy dla systemu Windows 10.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zezwalanie użytkownikom na dostęp do aplikacji Portal firmy dla systemu Android bez rejestracji <!---1169910--->  
Wkrótce użytkownicy końcowi nie będą musieli rejestrować urządzeń, aby uzyskać dostęp do aplikacji Portal firmy dla systemu Android. Użytkownicy końcowi w organizacjach używających zasad ochrony aplikacji nie będą już otrzymywać monitów o zarejestrowanie swoich urządzeń po otwarciu aplikacji Portal firmy. Ponadto użytkownicy końcowi będą mogli instalować aplikacje z poziomu aplikacji Portal firmy bez konieczności rejestrowania urządzeń. 

### <a name="users-who-are-signed-in-to-exchange-can-automatically-access-the-company-portal-website-on-windows-10-devices---1323204--"></a>Użytkownicy zalogowani do programu Exchange mogą automatycznie uzyskiwać dostęp do witryny internetowej Portal firmy na urządzeniach z systemem Windows 10 <!--1323204-->  
Użytkownicy systemu Windows 10, którzy zostali już uwierzytelnieni w programie Exchange, otrzymali wiadomość e-mail dotyczącą kwarantanny w ramach dostępu warunkowego i kliknęli link w wiadomości e-mail, nie będą już musieli ponownie uwierzytelniać się w przeglądarce przed rozpoczęciem konfiguracji dostępu do zasobów firmy.


## <a name="notices"></a>Uwagi

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->   
Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->   
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w portalu Azure w wersji zapoznawczej. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planowane zmiany: zmiany w usłudze Intune dotyczące witryny Intune Partner Portal <!-- 1050016 -->
Wraz z aktualizacją usługi w połowie maja 2017 r. strona Intune Partner zostanie usunięta z witryny manage.microsoft.com.  

Administratorzy partnerów nie będą już mogli wyświetlać strony Intune Partner ani podejmować na niej działań w imieniu swoich klientów. Zamiast tego konieczne będzie zalogowanie się w jednym z dwóch innych portali firmy Microsoft dla partnerów.

Logowanie się na zarządzane konta klientów będzie możliwe zarówno w [Centrum partnerskim firmy Microsoft](https://partnercenter.microsoft.com/), jak i w [Centrum administracyjnym dla partnerów usługi Microsoft Office 365](https://portal.office.com/). Aby kontynuować czynności partnerskie, należy korzystać z dowolnej z tych witryn do zarządzania klientami.



### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
