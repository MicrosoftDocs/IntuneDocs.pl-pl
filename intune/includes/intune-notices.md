---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: e745290991da4d80c7e3839250edbfdd64ef1b7a
ms.sourcegitcommit: 01c57ac880dcb5f474908977c89810f5bedaf326
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "75760974"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune.

### <a name="updated-feature-new-rbac-role-coming-to-intune--4253397--"></a>Zaktualizowana funkcja: Nowa rola kontroli RBAC wkrótce dostępna w usłudze Intune<!--4253397-->
W ramach styczniowej aktualizacji usługi Intune planujemy wydanie nowej roli zabezpieczeń w usłudze Intune. Ta rola będzie widoczna jako „Menedżer zabezpieczeń punktu końcowego” w usłudze Intune. Jest ona rozszerzeniem roli „Administrator zabezpieczeń” z usługi Azure AD.
 
#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Obecnie istnieją trzy role dostępne w usłudze Azure AD dla specjalistów ds. zabezpieczeń:
- Rola Czytelnik zabezpieczeń w usłudze Azure AD, która zapewnia dostęp tylko do odczytu do usługi Intune.
- Rola Operator zabezpieczeń w usłudze Azure AD, która zapewnia dostęp tylko do odczytu do usługi Intune.
- Administrator zabezpieczeń w usłudze Azure AD. Po opublikowaniu styczniowej aktualizacji usługi Intune oprócz uprawnień tylko do odczytu do usługi Intune nowe uprawnienia udostępniane przez rolę Menedżer zabezpieczeń punktu końcowego będą następujące:
    - Odczytywanie, tworzenie, aktualizowanie, usuwanie i przypisywanie zasad zgodności urządzeń
    - Odczytywanie, usuwanie i aktualizowanie urządzeń zarządzanych
    - Odczytywanie, tworzenie, aktualizowanie, usuwanie i przypisywanie punktów odniesienia zabezpieczeń
    - Odczytywanie i aktualizowanie zadań zabezpieczeń
 
### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Już dzisiaj zapoznaj się z rolami kontroli RBAC w usłudze Intune. Jeśli obecnie używasz tylko ról administratorów globalnych, nie musisz wprowadzać żadnych zmian. Jeśli używasz ról i chcesz korzystać ze stopnia szczegółowości, który zapewnia rola Menedżer zabezpieczeń punktu końcowego, przypisz tę rolę, gdy zostanie udostępniona. Sprawdź stronę [Co nowego](../fundamentals/whats-new.md) dla usługi Intune, aby uzyskać informacje na temat aktualnej wersji tej usługi. 

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Zaktualizowano oświadczenie dotyczące obsługi aplikacji mobilnej „Adobe Acrobat Reader dla usługi Intune"<!--5746776-->
Pod koniec sierpnia poinformowaliśmy w dokumencie MC188653, że okres eksploatacji aplikacji mobilnej Adobe Acrobat dla usługi Intune zakończy się 1 grudnia 2019 r. oraz że firma Adobe planuje obsługę zasad ochrony aplikacji usługi Intune w swojej głównej aplikacji Acrobat Reader. Od tego momentu otrzymaliśmy opinie klientów, którzy twierdzili, że potrzebują więcej czasu, aby administratorzy IT mogli nadal traktować aplikację Adobe Acrobat Reader dla usługi Intune jako docelową, a użytkownicy końcowi mogli zacząć z niej korzystać. Mając na uwadze duże użycie aplikacji Adobe Acrobat Reader dla usługi Intune na urządzeniach użytkowników końcowych oraz jej znaczenie w scenariuszach korporacyjnych, chcemy upewnić się, że wszystkie środowiska spełniają wymagania związane z ochroną aplikacji w organizacji. 

Mimo że w zasadach nadal zalecamy używanie ogólnej aplikacji mobilnej Acrobat Reader, ponieważ aplikacja mobilna Acrobat Reader obsługuje zasady ochrony aplikacji i ma zintegrowany zestaw SDK usługi Intune, aplikacja Adobe Acrobat Reader dla usługi Intune będzie obsługiwana do 31 marca 2020 r. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Otrzymujesz tę wiadomość, ponieważ z naszych raportów wynika, że co najmniej jedne zasady w Twojej organizacji dotyczą aplikacji Adobe Acrobat Reader dla usługi Intune i/lub otrzymano poprzednią komunikację dotyczącą zakończenia okresu eksploatacji. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poinformuj użytkowników końcowych i pomoc techniczną o tej zmianie. W celu ustanowienia kanału obsługi pytań związanych z usługą Intune możesz użyć [funkcji informacji pomocy technicznej aplikacji Portal firmy](../apps/company-portal-app.md#support-information).

#### <a name="additional-information"></a>Dodatkowe informacje
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="end-support-for-windows-phone-81--3544909--"></a>Zakończenie wsparcia systemu Windows Phone 8.1<!--3544909-->
Wsparcie podstawowe firmy Microsoft dla systemu Windows Phone 8.1 zakończyło się w lipcu 2017 r., a wsparcie dodatkowe zakończyło się w czerwcu 2019 r. Aplikacja Portal firmy dla systemu Windows Phone 8.1 działała w trybie podtrzymywania od października 2017 r. Usługa Microsoft Intune zakończy wsparcie dla systemu Windows Phone 8.1 w dniu 20 lutego 2020 r.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po 20 lutego 2020 r. te urządzenia nie będą otrzymywać aktualizacji zabezpieczeń i nie będzie można rejestrować nowych urządzeń. Istniejące urządzenia z systemem Windows Phone 8.1 pozostaną zarejestrowane (zasady, aplikacje, raportowanie), ale warto zapamiętać, że po tej dacie rozwiązywanie problemów dotyczących istniejącej rejestracji nie będzie obsługiwane, ponieważ wsparcie wielu składników, takich jak certyfikaty innych firm, zostało już zakończone na tej platformie. Usługa Intune przestanie testować zgodność między usługą Intune i systemem Windows Phone 8.1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Możesz sprawdzić raporty usługi Intune, aby zobaczyć, na które urządzenia lub użytkowników może to mieć wpływ. Przejdź do pozycji Urządzenia > Wszystkie urządzenia i filtruj zawartość według systemu operacyjnego. Możesz dodać dodatkowe kolumny, które ułatwią określenie, kto w organizacji ma urządzenia z systemem Windows Phone 8.1. Poproś użytkowników końcowych, aby uaktualnili urządzenia do obsługiwanej wersji systemu operacyjnego.


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Wymagane działanie: W celu zapewnienia chronionego środowiska przeglądarki w usłudze Intune należy używać przeglądarki Microsoft Edge.<!--5728447-->
Zgodnie z informacjami rozpowszechnianymi od początku roku przeglądarka Microsoft Edge dla urządzeń mobilnych obsługuje ten sam zestaw funkcji zarządzania co przeglądarka Managed Browser, a przy tym zapewnia użytkownikom końcowym znacznie lepsze środowisko pracy. Aby umożliwić użytkownikom korzystanie z bardziej niezawodnych funkcji przeglądarki Microsoft Edge, przeglądarka Intune Managed Browser zostanie wycofana. Od 27 stycznia 2020 r. usługa Intune nie będzie już obsługiwać przeglądarki Intune Managed Browser.  

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie? 
Począwszy od 1 lutego 2020 r. przeglądarka Intune Managed Browser nie będzie już dostępna w sklepie Google Play ani w sklepie App Store. Wciąż będzie można kierować nowe zasady ochrony aplikacji do przeglądarki Intune Managed Browser, lecz nowi użytkownicy nie będą mogli jej pobierać. Ponadto w systemie iOS nowe klipy internetowe przekazywane do urządzenia zarejestrowanego za pomocą funkcji zarządzania urządzeniami przenośnymi będą otwierane w przeglądarce Microsoft Edge, a nie Intune Managed Browser.  

31 marca 2020 r. przeglądarka Intune Managed Browser zostanie usunięta z konsoli platformy Azure. Oznacza to, że nie można będzie tworzyć nowych zasad dla tej przeglądarki. Nie wpłynie to na używane dotąd zasady przeglądarki Intune Managed Browser. Przeglądarka Intune Managed Browser będzie widoczna w konsoli jako aplikacja biznesowa bez ikony, a istniejące zasady będą wciąż widoczne jako odnoszące się do tej aplikacji. Zostanie również usunięta opcja przekierowywania zawartości sieci Web do przeglądarki Intune Managed Browser w sekcji Ochrona danych zasad ochrony aplikacji.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany? 
Aby zapewnić płynne przejście z przeglądarki Intune Managed Browser na Microsoft Edge, warto aktywnie podjąć następujące działania: 

1. Zasady ochrony aplikacji (znane także jako MAM) oraz ustawienia konfiguracji aplikacji należy kierować do przeglądarki Microsoft Edge w systemach iOS i Android. Można skorzystać z istniejących zasad przeglądarki Intune Managed Browser, kierując je do przeglądarki Microsoft Edge.  
2. Wszystkie aplikacje w środowisku chronione przez MAM powinny mieć opcję „Ogranicz transfer zawartości sieci Web za pomocą innych aplikacji” ustawioną na wartość „Przeglądarki zarządzane przez zasady”. 
3. Wszystkie aplikacje chronione przez MAM powinny mieć ustawienie konfiguracji aplikacji „com.microsoft.intune.useEdge” o wartości prawda. Od przyszłego miesiąca, w wersji 1911, będzie można wykonać kroki 2 i 3, konfigurując ustawienie „Ogranicz transfer zawartości sieci Web za pomocą innych aplikacji” z wartością „Microsoft Edge” wybraną w sekcji Ochrona danych zasad ochrony aplikacji. 

Wkrótce rozpoczniemy obsługę klipów internetowych w systemach iOS i Android. Po jej rozpoczęciu istniejące klipy internetowe trzeba będzie skierować tak, aby były otwierane w przeglądarce Microsoft Edge, a nie Managed Browser. 

#### <a name="additional-information"></a>Dodatkowe informacje
Aby uzyskać więcej informacji, zapoznaj się z dokumentami dotyczącymi [korzystania z przeglądarki Microsoft Edge z zasadami ochrony aplikacji](../apps/manage-microsoft-edge.md) lub [artykułem na blogu wsparcia technicznego](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).

### <a name="plan-for-change-updated-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--5198878--"></a>Planowanie zmian: Zaktualizowane środowisko rejestrowania dedykowanych urządzeń z systemem Android Enterprise w usłudze Intune<!--5198878-->
Wraz z wydaniem listopadowym (czyli 1911) do usługi Intune dodajemy obsługę wdrażania certyfikatów urządzeń SCEP dla dedykowanych urządzeń z systemem Android Enterprise, aby umożliwić dostęp oparty na certyfikatach do profilów sieci Wi-Fi. Ta zmiana obejmuje również pewne drobne zmiany w przepływie podczas rejestrowania dedykowanych urządzeń z systemem Android Enterprise.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli zarządzasz urządzeniami z systemem Android Enterprise, zobaczysz, że w listopadzie rozpocznie się wprowadzanie pewnych zmian.

- W przypadku nowych rejestracji dedykowanych urządzeń z systemem Android Enterprise: Podczas rejestracji użytkownicy końcowi będą widzieli inny zestaw kroków na urządzeniach. Rejestracja nadal będzie zaczynać się tak, jak obecnie (od metody QR, NFC, bezobsługowej lub identyfikatora urządzenia), ale po listopadowym wydaniu usługi pojawi się obowiązkowy krok instalacji aplikacji.
- W przypadku istniejących urządzeń z systemem Android zarejestrowanych jako urządzenia dedykowane: Usługa Intune zacznie automatycznie instalować aplikację Microsoft Intune na urządzeniach, począwszy od pierwszych tygodni listopada. Nie trzeba podejmować żadnych działań. Aplikacja zostanie automatycznie pobrana i zainstalowana na urządzeniach. 

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Należy zaplanować aktualizację przewodnika dla użytkowników końcowych i poinformować swoją pomoc techniczną o tej zmianie. Kliknij pozycję Dodatkowe informacje, aby uzyskać więcej szczegółów i zrzuty ekranu. Zaktualizujemy naszą stronę Co nowego, gdy rozpocznie się wdrażanie tej zmiany.

#### <a name="additional-information"></a>Dodatkowe informacje
[https://aka.ms/Dedicated_devices_enrollment](https://aka.ms/Dedicated_devices_enrollment)

### <a name="end-of-support-for-legacy-pc-management"></a>Koniec wsparcia dla zarządzania starszymi komputerami

Zarządzanie starszymi komputerami nie będzie obsługiwane od 15 października 2020. Uaktualnij urządzenia do systemu Windows 10 i zarejestruj je ponownie jako urządzenia oprogramowania Zarządzanie urządzeniami mobilnymi (MDM), aby mogły być dalej zarządzane przez usługę Intune.

[Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Zmniejszenie wsparcia dla administratora urządzeń z systemem Android 
Administrator urządzeń z systemem Android (czasami określany mianem „starszego sposobu” zarządzania systemem Android, opublikowany z systemem Android 2.2) to metoda zarządzania urządzeniami z systemem Android. Jednak obecnie jest dostępna ulepszona funkcja zarządzania w systemie [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (wydanie z systemem Android 5.0). Dążąc do przejścia do nowoczesnego, bardziej zaawansowanego i bezpieczniejszego zarządzania urządzeniami, firma Google ogranicza wsparcie administratora urządzeń w nowych wersjach systemu Android.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Te zmiany w usłudze Google wpłyną na użytkowników usługi Intune w następujący sposób:  
- Usługa Intune będzie w stanie w pełni obsługiwać urządzenia z systemem Android 10 i nowszymi zarządzanym przez administratora urządzeń tylko do 2. kwartału 2020 r. Urządzenia zarządzane przez administratora urządzeń z systemem Android 10 lub nowszym po tym terminie nie będą mogły być już w pełni zarządzane. W szczególności objęte urządzenia nie będą otrzymywać nowych wymagań dotyczących haseł.
    - W tym terminie zmiana nie będzie mieć wpływu na urządzenia z rozwiązaniem Samsung KNOX, ponieważ integracja usługi Intune z platformą Knox zapewnia rozszerzone wsparcie. Daje to więcej czasu na zaplanowanie przejścia z zarządzania przez administratora urządzeń.    
- Nie ma to wpływu na urządzenia z systemem Android zarządzane przez administratora urządzeń, które mają nadal zainstalowany system Android w wersji starszej niż Android 10. Mogą one być nadal w pełni zarządzane przez administratora urządzeń.    
- W przypadku wszystkich urządzeń z systemem Android 10 lub nowszym firma Google ograniczyła możliwość uzyskania dostępu do informacji o identyfikatorze urządzenia przez agentów zarządzania przez administratora urządzeń, takich jak Portal firmy. To ograniczenie ma wpływ na następujące funkcje usługi Intune po aktualizacji urządzenia do systemu Android 10 lub nowszego:  
    - Przestanie działać kontrola dostępu do sieci dla sieci VPN.   
    - Zidentyfikowanie urządzeń jako należących do firmy przy użyciu numerów IMEI lub numerów seryjnych nie oznacza, że urządzenia zostaną automatycznie oznaczone jako należące do firmy.  
    - Numer IMEI i numer seryjny nie będą już widoczne dla administratorów IT w usłudze Intune. 
        > [!NOTE]
        > Dotyczy to tylko urządzeń z systemem Android 10 i nowszym zarządzanych przez administratora urządzeń, a nie dotyczy urządzeń zarządzanych za pomocą systemu Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Aby uniknąć ograniczenia funkcjonalności, które pojawi się w 3. kwartale 2020 r., zalecamy:
- Nie dołączaj nowych urządzeń do zarządzania przez administratora urządzeń.
- Jeśli przewidujesz, że urządzenie otrzyma aktualizację do systemu Android 10, przeprowadź jego migrację z zarządzania przez administratora urządzeń do zarządzania przez system Android Enterprise lub zasad ochrony aplikacji.

#### <a name="additional-information"></a>Dodatkowe informacje
- [Wskazówki firmy Google dotyczące migracji z zarzadzania przez administratora urządzeń do systemu Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Dokumentacja firmy Google dotycząca planu wycofania interfejsu API administratora urządzeń](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Planowanie zmian: Zestaw Intune App SDK oraz zasady ochrony aplikacji dla systemu Android w nadchodzącej wersji będą obsługiwać system Android 5.0 i nowsze <!--4911065 -->
W nadchodzącej wersji usługa Intune będzie obsługiwać system Android 5.x (Lollipop) i nowsze. Zaktualizuj wszystkie opakowane aplikacje przy użyciu najnowszego zestawu Intune App SDK i zaktualizuj swoje urządzenia.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli nie używasz ani nie planujesz używać zestawu SDK lub zasad ochrony aplikacji dla systemu Android, ta zmiana na Ciebie nie wpłynie. Jeśli używasz zestawu Intune App SDK, pamiętaj, aby zaktualizować go do najnowszej wersji, a także zaktualizować swoje urządzenia do systemu Android 5.x lub nowszego. Jeśli nie przeprowadzisz aktualizacji, aplikacje nie będą otrzymywać aktualizacji, a ich jakość będzie się pogarszać wraz z upływem czasu.

Poniżej znajduje się lista typowych urządzeń rejestrowanych w usłudze Intune z systemem Android w wersji 4.x. Jeśli masz jedno z tych urządzeń, wykonaj odpowiednie kroki, aby upewnić się, że będzie ono obsługiwało system Android w wersji 5.0 lub nowszej lub że zostanie zastąpione urządzeniem obsługującym system Android w wersji 5.0 lub nowszej. Ta lista nie jest wyczerpująca i nie zawiera wszystkich urządzeń, które mogą wymagać oceny:

- Samsung SM-T561  
- Samsung SM-T365
- Samsung GT-I9195
- Samsung SM-G800F
- Samsung SM-G357FZ
- Motorola XT1080
- Samsung GT-I9305
- Samsung SM-T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Opakuj aplikacje przy użyciu najnowszego zestawu Intune App SDK. Możesz również określić ustawienie warunkowego uruchamiania „Wymagaj minimalnej wersji systemu operacyjnego (tylko ostrzeżenie)”, aby powiadomić użytkowników końcowych urządzeń osobistych o uaktualnieniu.

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7---3042987---"></a>Plan zmian w usłudze Intune: Bliski koniec wsparcia dla systemu Windows 7<!-- 3042987 -->
Zgodnie z informacjami opublikowanymi w komunikacie MC148476 we wrześniu 2018 r. i ponownie w komunikacie MC176794 w marcu 2019 r. w dniu 14 stycznia 2020 r. zakończy się rozszerzone wsparcie techniczne systemu Windows 7. W tym czasie w usłudze Intune zostanie wycofana obsługa urządzeń z systemem Windows 7, dzięki czemu będziemy mogli skupić się na inwestowaniu w obsługę nowszych technologii i zapewnianiu wspaniałych nowych możliwości użytkownikom końcowym. Po tej dacie pomoc techniczna i aktualizacje automatyczne pomagające chronić komputer z systemem Windows 7 nie będą już dostępne za pośrednictwem usługi Intune. Firma Microsoft zdecydowanie zaleca przejście do systemu Windows 10 przed styczniem 2020 r., aby uniknąć scenariusza, w którym potrzebna usługa lub pomoc techniczna nie będzie już dostępna. Przeczytaj [tutaj](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) więcej na temat cyklu obsługi technicznej systemu Windows.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Otrzymujesz tę wiadomość, ponieważ obecnie zarządzasz komputerem z systemem Windows 7 przy użyciu starszego agenta oprogramowania usługi Intune. Ponieważ do końca rozszerzonej obsługi technicznej systemu Windows 7 pozostał już niespełna rok, zdecydowanie zachęcamy Twoją organizację do jak najszybszego rozpoczęcia uaktualniania do systemu Windows 10.  

Możliwości zarządzania komputerami są wbudowane bezpośrednio w system operacyjny Windows 10 i nie trzeba już instalować agenta takiego jak oprogramowanie klienckie usługi Intune dla systemu Windows 7. Począwszy od wersji Windows 8.1, firma Microsoft wykorzystuje architekturę zarządzania urządzeniami mobilnymi (MDM) do aprowizowania, konfigurowania i aktualizowania komputerów z systemem Windows oraz zarządzania nimi. Po skonfigurowaniu usługi Intune możesz uprościć rejestrację systemu Windows, [rejestrując komputery z systemem Windows 10 w usłudze Intune](..\windows-enroll.md) za pośrednictwem kanału MDM. Zalecamy, aby do zarządzania komputerami z systemem Windows 10 używać rozwiązania MDM, niewymagającego użycia agentów.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Zachęcamy organizację do natychmiastowego rozważenia tego planu działania:

- Zaplanowanie uaktualnienia floty urządzeń z systemem Windows 7 do systemu Windows 10 i wykonanie tego uaktualnienia przed 14 stycznia 2020 r.
- Zapoznanie się z artykułem dotyczącym [wsparcia wdrożenia systemu Windows 10](https://docs.microsoft.com/windows/deployment/), aby dowiedzieć się więcej na temat uaktualniania posiadanej floty komputerów z systemem Windows 7 do systemu Windows 10.
- Zapoznanie się z ofertą usługi [Desktop App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) w ramach usługi Fast Track, aby uzyskać pomoc w zapewnieniu zgodności aplikacji firmy Microsoft.
- Przeniesienie istniejących urządzeń zarządzanych przez oprogramowanie klienckie usługi Intune do rozwiązania zalecanego przez firmę Microsoft w celu zarządzania systemem Windows 10 przy użyciu funkcji MDM. Rejestrowanie wszystkich nowych komputerów z systemem Windows 10 przy użyciu funkcji MDM dla usługi Intune w witrynie Azure Portal.

Zapoznanie się z tym [wpisem w blogu](https://aka.ms/Windows7_Intune), aby uzyskać więcej informacji.


