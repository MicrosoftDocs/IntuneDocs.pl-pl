---
title: Wczesna wersja
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ac9cb0ad7d1b5e2c29e80f16c172f41c08d3a15d
ms.sourcegitcommit: 5fd17a57989c6da3d325ed2e0018ce16fe20bb79
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>Wczesna wersja usługi Microsoft Intune — styczeń 2018

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

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Łatwiejsze rozwiązywanie problemów ze zgodnością aplikacji Portal firmy dla systemu Windows 10<!--676546 -->

Użytkownicy końcowi mający urządzenia z systemem Windows będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem. 

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nowa opcja uwierzytelniania użytkownika na potrzeby rejestracji zbiorczej firmy Apple <!-- 747625 -->
Usługa Intune zapewni możliwość uwierzytelniania urządzeń przy użyciu aplikacji Portal firmy dla następujących metod rejestracji:

- Program Device Enrollment Program firmy Apple
- Apple School Manager
- Rejestracja programu Apple Configurator

Korzystając z opcji obejmującej Portal firmy, można wymusić uwierzytelnianie wieloskładnikowe usługi Azure Active Directory bez blokowania tych metod rejestracji.

W przypadku użycia opcji obejmującej Portal firmy usługa Intune pomija uwierzytelnianie użytkownika w Asystencie ustawień systemu iOS w celu rejestracji koligacji użytkownika. Oznacza to, że urządzenie zostaje początkowo zarejestrowane jako urządzenie bez użytkownika i dlatego nie otrzymuje konfiguracji ani zasad dotyczących grup użytkowników. Otrzymuje tylko konfiguracje i zasady dotyczące grup urządzeń. Jednak usługa Intune automatycznie zainstaluje aplikację Portal firmy na urządzeniu. Pierwszy użytkownik, który uruchomi aplikację Portal firmy i zaloguje się w niej, zostanie skojarzony z urządzeniem w usłudze Intune. Użytkownik otrzyma wówczas konfiguracje i zasady dotyczące grup użytkowników. Skojarzenia z użytkownikiem nie można zmienić bez ponownego wykonania rejestracji.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 -->
Usługa Intune będzie obsługiwać rejestrowanie urządzeń z maksymalnie 100 różnych kont usług Apple Device Enrollment Program (DEP) i Apple School Manager. Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>Wybieranie kategorii urządzeń przy użyciu ustawień opcji Uzyskaj dostęp do miejsca pracy lub nauki <!-- 1058963 eeready --> 
Jeśli włączono [mapowanie grup urządzeń](https://docs.microsoft.com/en-us/intune/device-group-mapping), w systemie Windows 10 po dokonaniu rejestracji przy użyciu przycisku **Połącz** w obszarze **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** lub w trakcie pracy w środowisku gotowym do użycia zostanie wyświetlony monit o wybranie kategorii urządzenia.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Określanie zasad zgodności dla urządzeń w grupach urządzeń<!--1307012 -->

Możesz określać zasady zgodności dla użytkowników w grupach użytkowników. Możesz także określać zasady zgodności dla urządzeń w grupach urządzeń. 

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup <!-- 1406920 -->

Podczas przypisywania aplikacji i po wybraniu typu przypisania będzie można wybrać grupy, które mają być uwzględnione, a także grupy, które mają zostać wykluczone. Będzie można również użyć wstępnie utworzonych grup (Wszyscy użytkownicy, Wszystkie urządzenia i Wszyscy użytkownicy+urządzenia) jako tych, które mają być uwzględnione.

### <a name="remote-erase-command-support----1438084---"></a>Zdalna obsługa polecenia wymazywania <!-- 1438084 -->

Administratorzy będą mogli zdalnie wydać polecenie „Erase” („Wymaż”).

> [!IMPORTANT]
> Polecenia wymazywania nie można cofnąć, dlatego należy korzystać z niego z rozwagą.

Polecenie wymazywania powoduje usunięcie wszystkich danych, w tym systemu operacyjnego, z urządzenia. Powoduje również usunięcie urządzenia z zarządzania przy użyciu usługi Intune. Ostrzeżenie dla użytkownika nie jest wyświetlane i wymazywanie następuje natychmiast po wykonaniu polecenia.

Można skonfigurować 6-cyfrowy numer PIN odzyskiwania. Za pomocą tego numeru PIN można odblokować wymazane urządzenie, po czym rozpocznie się ponowna instalacja systemu operacyjnego. Po rozpoczęciu operacji wymazywania numer PIN jest wyświetlany na pasku stanu, w bloku przeglądu urządzenia w usłudze Intune. Numer PIN jest widoczny podczas całego procesu wymazywania. Po zakończeniu wymazywania urządzenie całkowicie znika z zarządzania w usłudze Intune. Należy pamiętać, aby zarejestrować numer PIN odzyskiwania, dzięki czemu osoba przywracająca urządzenie będzie mogła go użyć.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dane zaszyfrowane przy użyciu funkcji Windows Information Protection (WIP) w wynikach wyszukiwania systemu Windows <!-- 1469193 -->

Nowe ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia kontrolowanie, czy dane zaszyfrowane przy użyciu funkcji WIP będą uwzględniane w wynikach wyszukiwania systemu Windows.

### <a name="website-learning-mode----1631908---"></a>Tryb nauki witryny sieci Web<!-- 1631908 -->

Usługa Intune wprowadzi rozszerzenie trybu nauki funkcji Windows Information Protection (WIP). Oprócz wyświetlania informacji o aplikacjach z włączoną funkcją WIP będzie można wyświetlać podsumowanie urządzeń, które udostępniły dane robocze witrynom sieci Web. Dzięki tym informacjom można ustalić, które witryny sieci Web należy dodać do zasad WIP dotyczących grupy i użytkownika.

### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizacje wiadomości e-mail dotyczących zgodności <!--1637547 -->

Wiadomość e-mail wysłana w celu zgłoszenia niezgodnego urządzenia będzie zawierać szczegóły dotyczące niezgodnego urządzenia. Informacje na ten temat będzie można znaleźć w zaktualizowanej wersji następującego artykułu: [Automatyzacja akcji w przypadku niezgodności](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zasady dostępu warunkowego dla usługi Intune są dostępne tylko w witrynie Azure Portal <!-- 1737088 1634311 --> 
Obszary konfigurowania dostępu warunkowego oraz zarządzania nim zostaną uproszczone. Konfigurowanie zasad i zarządzanie nimi będzie odbywać się w witrynie [Azure Portal](https://portal.azure.com), po wybraniu opcji **Azure Active Directory** > **Dostęp warunkowy**. Dla wygody użytkowników przejście do tego bloku będzie również możliwe z usługi Intune w witrynie Azure Portal, po wybraniu opcji **Intune** > **Dostęp warunkowy**.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną<!-- 1639263 -->
Strona przeglądu będzie zawierać alerty dotyczące wygasłych tokenów i tokenów, które wkrótce wygasną. Kliknięcie alertu dotyczącego pojedynczego tokenu spowoduje przejście do strony szczegółów tokenu.  Po kliknięciu alertu dotyczącego wielu tokenów nastąpi przejście do listy wszystkich tokenów z informacjami o ich stanie. Administratorzy powinni odnawiać tokeny przed datą wygaśnięcia.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Drukowanie zdalne za pośrednictwem sieci zabezpieczonej <!-- 1709994  -->
Rozwiązania bezprzewodowego drukowania mobilnego PrinterOn umożliwią użytkownikom drukowanie zdalne z dowolnego miejsca i w dowolnym czasie za pośrednictwem sieci zabezpieczonej. Rozwiązania PrinterOn będą zintegrowane z zestawem Intune APP SDK dla systemów iOS i Android. Możliwe będzie określenie zasad ochrony aplikacji dla danej aplikacji przy użyciu bloku **Zasady ochrony aplikacji** usługi Intune w konsoli administratora. Użytkownicy końcowi będą mogli pobrać aplikację „PrinterOn for Microsoft” za pośrednictwem sklepu Play lub iTunes i używać jej w środowisku usługi Intune.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Zatwierdzanie aplikacji Portal firmy dla programu Android for Work <!--1797090 -->
Jeśli organizacja korzysta z programu Android for Work, należy ręcznie zatwierdzić aplikację Portal firmy dla systemu Android, dzięki czemu będzie ona nadal otrzymywać aktualizacje automatyczne z zarządzanego sklepu Google Play.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Interfejs API programu Microsoft Graph dla usługi Intune — ogólna dostępność <!-- 1833289 -->
Interfejsy API programu Microsoft Graph w usłudze Intune zapewnią programowy dostęp do danych i metod na potrzeby automatyzacji działań administracyjnych dla usługi Intune.  Dzięki **ogólnej dostępności** tych interfejsów API klienci, partnerzy i deweloperzy będą mogli używać interfejsów API do integracji z rozwiązaniami wewnętrznymi lub komercyjnymi, które są związane z obsługą usługi Intune bądź wymagają takiej obsługi, albo z innymi usługami firmy Microsoft dostępnymi za pośrednictwem programu Microsoft Graph. 

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odwołanie aplikacji dla systemu iOS zakupionych w ramach programu zakupów zbiorczych  <!-- 820863 -->
Dla danego urządzenia z zainstalowaną przynajmniej jedną aplikacją dla systemu iOS zakupioną w ramach programu zakupów zbiorczych (Volume-Purchase Program — VPP) będzie można odwołać skojarzoną licencję aplikacji urządzenia dla tego urządzenia. Odwołanie licencji aplikacji nie spowoduje odinstalowania powiązanych aplikacji VPP z urządzenia. Aby odinstalować aplikację VPP, należy zmienić akcję przypisywania na **Odinstaluj**. Aby uzyskać więcej informacji, zobacz temat [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odwołanie licencji dla tokenu programu zakupów zbiorczych dla systemu iOS <!-- 820870 -->
Istnieje możliwość odwołania licencji wszystkich aplikacji dla systemu iOS zakupionych w ramach programu zakupów zbiorczych (VPP) dla danego tokenu programu VPP.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Raportowanie zaewidencjonowania urządzenia NAC (Network Access Control) <!-- 1232250 -->
Przed wprowadzeniem tej zmiany administratorzy IT nie mogli określić po stronie usługi Intune, czy urządzenie zarządzane w ramach NAC komunikowało się z rozwiązaniem NAC czy nie. Gdy urządzenie zarządzane w ramach NAC nie komunikuje się z rozwiązaniem NAC, urządzenie jest traktowane przez rozwiązanie NAC jako niezgodne i zostaje zablokowane przez to rozwiązanie, a następnie przez zasady dostępu warunkowego oparte na stanie zgodności urządzenia.

Dzięki tej zmianie administratorzy IT wiedzą, które urządzenia zarządzane w ramach NAC pomyślnie nawiązały komunikację z rozwiązaniem NAC, a które nie. Ta nowa możliwość obejmuje dwie nowe funkcje monitorowania znajdujące się w obciążeniu Zgodność urządzeń w usłudze Intune. Poniżej podano używane statystyki:
- **Średnia liczba wywołań NAC w ciągu ostatniej godziny**
- **Ostatnie żądanie przychodzące NAC (data/godzina)**

### <a name="new-ios-device-action------1244701---"></a>Nowa akcja dotycząca urządzenia z systemem iOS <!-- 1244701 -->
Można zamknąć nadzorowane urządzenia z systemem iOS 10.3. Ta akcja natychmiast wyłącza urządzenie bez ostrzeżenia dla użytkownika końcowego. Akcję **Wyłącz (tylko nadzorowane)** można znaleźć we właściwościach urządzenia po wybraniu urządzenia w obciążeniu **Urządzenie**.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Usługa Intune obejmuje teraz operację przenoszenia konta<!-- 1573558, 1579830 -->
Funkcja **Przenoszenie konta** migruje dzierżawę z jednej jednostki skalowania Azure (ASU) na inną. Funkcji **Przenoszenie konta** można użyć w obu scenariuszach inicjowanych przez klienta, kiedy klient dzwoni do zespołu pomocy technicznej usługi Intune z prośbą o przeniesienie, oraz w scenariuszu inicjowanym przez Microsoft, w którym firma Microsoft musi wprowadzić zmiany na zapleczu usługi. W trakcie **przenoszenia konta** dzierżawa działa w trybie tylko do odczytu (ROM). Operacje usług, takie jak rejestrowanie, zmiana nazwy urządzenia, aktualizowanie stanu zgodności, w okresie ROM zakończą się niepowodzeniem.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Przypisywanie aplikacji mobilnych usługi Office 365 do urządzeń z systemami iOS i Android przy użyciu wbudowanego typu aplikacji <!-- 1332318 -->
**Wbudowany** typ aplikacji ułatwia tworzenie aplikacji usługi Office 365 oraz ich przypisywanie do zarządzanych urządzeń z systemami iOS i Android. Są to na przykład aplikacje usługi 0365, takie jak Word, Excel, PowerPoint i OneDrive. Do typu aplikacji można przypisać określone aplikacje, a następnie zmodyfikować konfigurację informacji o aplikacji.


### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>Zmiana rozwiązywania konfliktów przypisania dla aplikacji ze sklepu dla systemu iOS <!-- 1480316 -->
Użytkownicy końcowi mogą zauważyć zmiany w dostępności aplikacji ze sklepu dla systemu iOS. Obecnie aplikacja przypisana do dwóch grup — **Wymagane i dostępne** i **Nie dotyczy** — między którymi występuje konflikt, jest rozpoznawana jako należąca do grupy **Wymagane i dostępne**. Po wprowadzeniu tej zmiany w przypadku takiego konfliktu aplikacja będzie rozpoznawana jako należąca do grupy **Nie dotyczy**.

Ma to na celu wyeliminowanie pomyłek związanych z przypisaniem aplikacji do wielu grup o różnym przeznaczeniu.

Jeśli chcesz udostępnić aplikację w Portalu pracowników przetwarzających informacje i Portalu firmy przed wydaniem listopadowej wersji usługi, masz dwie opcje:

1. Usunięcie przypisania **Nie dotyczy** z grupy.
2. Utworzenie nowej grupy, która nie zawiera elementów członkowskich z przypisaniem **Wymagane i dostępne**, i przypisanie tej grupy jako **Nie dotyczy**.

Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune (Jak przypisać aplikacje do grup w usłudze Microsoft Intune)](apps-deploy.md).

> [!Note]
> Po wydaniu nowej wersji nie będzie możliwe wyświetlanie ani modyfikowanie przypisań aplikacji w ramach zarządzania urządzeniami mobilnymi za pomocą konsoli klasycznej usługi Intune. Można jednak zarządzać przypisaniami aplikacji przy użyciu konsoli platformy Azure lub interfejsu API programu Intune Graph.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Zarządzanie urządzeniami programu Android for Work w sposób niezależny od urządzeń z systemem Android <!-- 1490731 -->
Usługa Intune będzie obsługiwać zarządzanie rejestracją urządzeń programu Android for Work w sposób niezależny od platformy Android. Opcje zarządzania tymi ustawieniami są dostępne w obszarze **Rejestrowanie urządzenia** > **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń**. (Wcześniej znajdowały się one w obszarze **Rejestrowanie urządzeń** > **Rejestracja w programie Android for Work** > **Ustawienia rejestracji programu Android for Work**).

Domyślnie ustawienia urządzeń programu Android for Work będą takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.
 
Jeśli zablokujesz rejestrację urządzeń osobistych w programie Android for Work, będzie można rejestrować tylko firmowe urządzenia z systemem Android.

Podczas pracy z nowymi ustawieniami zwróć uwagę na następujące kwestie:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Jeśli wcześniej nie dodano rejestracji w programie Android for Work
Nowa platforma Android for Work jest zablokowana w domyślnych ograniczeniach typów urządzeń. Po dodaniu tej funkcji możesz zezwolić urządzeniom na rejestrację w programie Android for Work. Aby to zrobić, zastąp domyślne ograniczenie typów urządzeń — zmień je lub utwórz nowe ograniczenie.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Jeśli dodano rejestrację w programie Android for Work
Jeśli wcześniej dołączono do programu, sytuacja zależy od wybranego ustawienia:

| Ustawienie | Stan programu Android for Work w domyślnym ograniczeniu typów urządzeń | Uwagi |
| --- | --- | --- |
| **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** | Zablokowane | Wszystkie urządzenia z systemem Android należy zarejestrować bez programu Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** | Dozwolone | Wszystkie urządzenia z systemem Android, które obsługują program Android for Work, należy zarejestrować w programie Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko dla użytkowników w tych grupach** | Zablokowane | Utworzono oddzielne zasady ograniczeń typów urządzeń, które przesłaniają domyślne zasady. Zasady te definiują wcześniej wybrane grupy, zezwalając na rejestrację w programie Android for Work. Użytkownicy z wybranych grup zachowają możliwość rejestrowania urządzeń programu Android for Work. Pozostali użytkownicy nie mogą rejestrować się w programie Android for Work. |

We wszystkich przypadkach zamierzone zasady są zachowywane. Nie są wymagane żadne działania użytkownika w celu zachowania możliwości korzystania z programu Android for Work w środowisku — zarówno w skali ogólnej, jak i w odniesieniu do poszczególnych grup.

Zmiany zostaną wprowadzone wraz z listopadową aktualizacją, ale ich wdrożenie na danym koncie może trochę potrwać. Gdy zmiany zostaną zastosowane na Twoim koncie, otrzymasz powiadomienie w portalu usługi Office 365.


### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurowanie numeru PIN aplikacji dla systemu iOS <!-- 1586774 -->
Już wkrótce będzie można wymagać wprowadzenia numeru PIN dla aplikacji docelowych z systemem iOS. Wymaganie wprowadzenia numeru PIN i datę wygaśnięcia liczoną w dniach można skonfigurować za pośrednictwem witryny Azure Portal. W razie potrzeby będzie można narzucić wymaganie używania nowego numeru PIN w celu uzyskania dostępu do aplikacji dla systemu iOS. Ta funkcja będzie dostępna tylko dla aplikacji dla systemu iOS, dla których włączono ochronę aplikacji przy użyciu zestawu SDK aplikacji usługi Intune.


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Obsługa zasad uaktualniania wydania systemu Windows 10 <!-- 903672(archived), 1119689 -->  
Można utworzyć zasady uaktualniania wydania systemu Windows 10, które umożliwią uaktualnienie urządzeń z systemem Windows 10 do systemu Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education oraz Windows 10 Professional Education N. Aby uzyskać szczegółowe informacje dotyczące uaktualnień wydania systemu Windows 10, zobacz artykuł [How to configure Windows 10 edition upgrades (Jak skonfigurować uaktualnienia wydania systemu Windows 10)](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Obsługa programu Android for Work dla usługi Lookout <!-- 1087312 -->   
Łącznik usługi Intune z usługą Lookout będzie obsługiwać urządzenia z programem Android for Work w przypadku korzystania z aplikacji Lookout for Work. Można wdrożyć aplikację Lookout wewnątrz lub na zewnątrz kontenera.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Narzędzia deweloperskie usług Intune App Protection i Citrix MDX <!-- 709185 -->
Urządzeniami i aplikacjami można zarządzać przy użyciu kombinacji usług Citrix XenMobile MDX i Microsoft Intune. Umożliwia ona zarządzanie aplikacjami za pomocą zasad usługi Intune App Protection przy równoczesnym wykorzystaniu technologii mVPN firmy Citrix.

Możesz odnaleźć repozytorium kodu, które zawiera narzędzie opakowujące aplikacje usługi Intune i zestawu Intune App SDK dla systemu iOS i Android zintegrowane z technologią mVPN Citrix MDX.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Przekierowywanie użytkowników systemu macOS do naszej nowej aplikacji Portal firmy <!--1380728-->   
Gdy użytkownik końcowy zaloguje się do witryny internetowej Portal firmy, aby zarejestrować swoje urządzenie z systemem macOS, w celu ukończenia procesu zostanie przekierowany na stronę pobierania nowej aplikacji Portal firmy dla systemu macOS. Dotyczy to urządzeń z systemem macOS w wersji OS X El Capitan 10.11 lub nowszym. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Obsługa aplikacji Intune Managed Browser dla systemu iOS i Android <!-- 1374196 -->
Od października 2017 r. aplikacja Intune Managed Browser w aplikacji dla systemu Android będzie obsługiwać tylko urządzenia z systemem Android 4.4 lub nowszym. Aplikacja Intune Managed Browser dla systemu iOS będzie obsługiwać wyłącznie urządzenia z systemem iOS 9.0 i nowszym. Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Ulepszony komunikat o błędzie, gdy użytkownik osiągnie maksymalną liczbę urządzeń, które można zarejestrować <!-- 1270370 -->
Zamiast ogólnego komunikatu o błędzie użytkownicy końcowi urządzeń z systemem Android zobaczą przyjazny komunikat o błędzie umożliwiający wykonanie akcji: „Zarejestrowano maksymalną liczbę urządzeń dozwoloną przez administratora IT. Usuń zarejestrowane urządzenie lub skontaktuj się z administratorem IT w celu uzyskania pomocy”.




## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.




### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
