---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: b59419be9f381a1c646a7778b73ed172526f6ef6
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188436"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune.

### <a name="update-your-intune-outlook-app-protection-policies-app--2576686--"></a>Aktualizowanie zasad ochrony aplikacji programu Outlook w usłudze Intune<!--2576686-->
Jeśli w Centrum wiadomości otrzymasz informację MC195618, może być konieczne wykonanie akcji. Jak opisano w planie platformy Microsoft 365, w obszarach oznaczonych identyfikatorami funkcji: 56325 i 56326, usługi Intune i Outlook dla systemów iOS i Android wdrażają obsługę ograniczania poufnych danych w powiadomieniach e-mail i przypomnień w kalendarzu. W wyniku tych ulepszeń program Outlook dla systemów iOS i Android będzie usuwał obsługę kilku kluczy konfiguracji aplikacji ochrony danych, które są obecnie używane do zarządzania powiadomieniami.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Chociaż nowe funkcje nie zostały jeszcze opublikowane, gdy to się stanie, następujące klucze konfiguracji aplikacji nie będą już działać w programie Outlook dla systemów iOS i Android:
- com.microsoft.outlook.Mail.NotificationsEnabled
- com.microsoft.outlook.Mail.NotificationsEnabled.UserChangeAllowed
- com.microsoft.outlook.Calendar.NotificationsEnabled
- com.microsoft.outlook.Calendar.NotificationsEnabled.UserChangeAllowed

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jako przygotowanie do pracy z nową funkcją zalecamy skonfigurowanie ustawienia ochrony danych zasad ochrony aplikacji w usłudze Intune o nazwie „Powiadomienia dotyczące danych organizacji” na wartość „Blokuj dane organizacji”. Od 16 grudnia 2019 r. program Outlook dla systemów iOS i Android będzie używać ustawienia ochrony danych „Powiadomienia dotyczące danych organizacji” i nie będzie już obsługiwać wymienionych kluczy. Skonfigurowanie tego nowego ustawienia zagwarantuje, że poufne dane nie zostaną ujawnione, gdy powyższe klucze konfiguracji nie będą już obsługiwane. Ponadto w programie Outlook będzie zapewniany dodatkowy poziom szczegółowości, gdy ustawienie ochrony danych „Powiadomienia dotyczące danych organizacji” zostanie ustawione na wartość „Blokuj dane organizacji” przy użyciu dodatkowego ustawienia konfiguracji aplikacji „Powiadomienia kalendarza”. Kombinacja ustawień zasad ochrony aplikacji i tego ustawienia konfiguracji aplikacji ogranicza informacje poufne w powiadomieniach pocztowych, jednocześnie dostarczając poufne informacje w powiadomieniach kalendarza, dzięki czemu użytkownicy mogą szybko przejść do swoich spotkań w powiadomieniu lub w centrum powiadomień.

#### <a name="additional-information"></a>Dodatkowe informacje
Aby uzyskać więcej informacji na temat ustawień zasad ochrony aplikacji i ustawień programu Outlook, zobacz:
- [Ustawienia zasad ochrony aplikacji, Android](../apps/app-protection-policy-settings-android.md)
- [Ustawienia zasad ochrony aplikacji, iOS](../apps/app-protection-policy-settings-ios.md)
- [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android)


### <a name="intune-plan-for-change-windows-10-version-1703-company-portal-moving-out-of-support--5026679--"></a>Plan zmian w usłudze Intune: Windows 10, wersja 1703 — zakończenie wsparcia programu Portal firmy<!--5026679-->
System Windows 10 w wersji 1703 (znanej również jako Windows 10, RS2) zakończył cykl życia wersji dla przedsiębiorstw i wersji EDU 8 października 2019 r. Usługa Intune zakończy obsługę odpowiedniej aplikacji Portal firmy dla wersji RS2/RS1 w dniu 26 grudnia 2019 r.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Nie będą widoczne nowe funkcje w określonej wersji aplikacji Portal firmy, choć ta wersja będzie obsługiwana do 26 grudnia 2019 r. (między innymi w razie potrzeby będą udostępniane aktualizacje zabezpieczeń do niej). Ponieważ jednak po zakończeniu cyklu życia system Windows 10 w wersji 1703 nie będzie otrzymywał aktualizacji zabezpieczeń, zdecydowanie zalecamy zaktualizowanie systemu Windows na urządzeniach do nowszej wersji i zapewnienie najnowszej wersji aplikacji Portal firmy w celu otrzymywania nowych i dodatkowych funkcji.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Czynności, jakie należy wykonać, zależą od konfiguracji środowiska. Zazwyczaj należy po prostu sprawdzić, na których urządzeniach zainstalowano starszą wersję systemu operacyjnego lub aplikacji Portal firmy, i uaktualnić je. Aby skonfigurować pierścienie aktualizacji systemu Windows 10, zaloguj się do usługi Intune -> wybierz kolejno opcje Aktualizacje oprogramowania — Pierścienie aktualizacji systemu Windows 10. Najnowsza wersja aplikacji Portal firmy to 10.3.5601.0. Należy poinformować użytkowników o konieczności uzyskania jej ze sklepu Microsoft Store w celu zachowania zgodności z przyszłymi wersjami. Najnowsze wersje można także instalować na urządzeniach z systemem Windows za pomocą usługi Intune i sklepu [Microsoft Store dla Firm](https://docs.microsoft.com/intune/windows-store-for-business).

#### <a name="additional-information"></a>Dodatkowe informacje
[Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10 przy użyciu usługi Microsoft Intune](https://docs.microsoft.com/intune/store-apps-company-portal-app)


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
- Usługa Intune będzie w stanie obsługiwać urządzenia z systemem Android 10 i nowszym (znanym także jako Android Q) zarządzane przez administratora urządzeń tylko do lata 2020 r. Wtedy można spodziewać się wydania kolejnej głównej wersji systemu Android.   
- Urządzenia zarządzane przez administratora urządzeń z systemem Android 10 lub nowszym po upływie lata 2020 r. nie będą mogły być już w pełni zarządzane.       
- Nie ma to wpływu na urządzenia z systemem Android zarządzane przez administratora urządzeń, które mają nadal zainstalowany system Android w wersji starszej niż Android 10. Mogą one być nadal w pełni zarządzane przez administratora urządzeń.    
- W przypadku wszystkich urządzeń z systemem Android 10 lub nowszym firma Google ograniczyła możliwość uzyskania dostępu do informacji o identyfikatorze urządzenia przez agentów zarządzania przez administratora urządzeń, takich jak Portal firmy. To ograniczenie ma wpływ na następujące funkcje usługi Intune po aktualizacji urządzenia do systemu Android 10 lub nowszego:  
    - Przestanie działać kontrola dostępu do sieci dla sieci VPN.   
    - Zidentyfikowanie urządzeń jako należących do firmy przy użyciu numerów IMEI lub numerów seryjnych nie oznacza, że urządzenia zostaną automatycznie oznaczone jako należące do firmy.  
    - Numer IMEI i numer seryjny nie będą już widoczne dla administratorów IT w usłudze Intune. 
        > [!NOTE]
        > Dotyczy to tylko urządzeń z systemem Android 10 i nowszym zarządzanych przez administratora urządzeń, a nie dotyczy urządzeń zarządzanych za pomocą systemu Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Aby uniknąć ograniczenia funkcjonalności, które pojawią się w lecie 2020 r., zalecamy co następuje:
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


