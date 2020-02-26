---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 373aeea9ab4fcbd075ac2ab18f205f3ddd191a39
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609300"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune.

### <a name="microsoft-intune-support-for-windows-10-mobile-ending--3544938--"></a>Zakończenie obsługi usługi Microsoft Intune dla systemu Windows 10 Mobile<!--3544938-->
W grudniu 2019 r. zakończono wsparcie podstawowe firmy Microsoft dla systemu Windows 10 Mobile. Jak wspomniano w niniejszym oświadczeniu o obsłudze, użytkownicy systemu Windows 10 Mobile nie będą już uprawnieni do otrzymywania nowych aktualizacji zabezpieczeń, poprawek niezwiązanych z zabezpieczeniami, bezpłatnych opcji asystowanej pomocy technicznej czy aktualizacji zawartości technicznej online firmy Microsoft. W oparciu o tę kończącą się pomoc techniczną dla systemu operacyjnego na urządzenia przenośne 11 maja 2020 r. usługa Microsoft Intune zakończy wsparcie aplikacji Portal firmy dla systemu Windows 10 Mobile oraz wsparcie dla samego systemu operacyjnego Windows 10 Mobile.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli masz urządzenia z systemem Windows 10 Mobile wdrożone w organizacji, to do 11 maja 2020 r. możesz rejestrować nowe urządzenia, dodawać lub usunąć zasady i aplikacje oraz aktualizować dowolne ustawienia zarządzania. Po 11 maja firma Microsoft zatrzyma możliwość rejestrowania nowych urządzeń i ostatecznie usunie możliwość zarządzania systemem Windows 10 Mobile z interfejsu użytkownika usługi Intune. Urządzenia nie będą już ewidencjonować usługi Intune, a firma Microsoft usunie dane dotyczące urządzeń i zasad.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Możesz sprawdzić raporty usługi Intune, aby zobaczyć, na które urządzenia lub użytkowników może to mieć wpływ. Przejdź do pozycji **Urządzenia** > **Wszystkie urządzenia** i filtruj zawartość według systemu operacyjnego. Możesz dodać dodatkowe kolumny, które ułatwią określenie, kto w organizacji ma urządzenia z systemem Windows 10 Mobile. Zażądaj od użytkowników końcowych, aby uaktualnili swoje urządzenia lub przestali korzystać z urządzeń w celu dostępu do zasobów firmowych.



### <a name="plan-for-change-change-in-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--6114580--"></a>Planowanie zmian: Zmiana sposobu rejestrowania dedykowanych urządzeń z systemem Android Enterprise w usłudze Intune<!--6114580-->
W uwagach do wydania listopadowego wspominaliśmy o dodaniu obsługi wdrażania certyfikatów SCEP dla dedykowanych urządzeń z systemem Android Enterprise, aby umożliwić oparty na certyfikatach dostęp do profilów sieci Wi-Fi. Zmiana ta wymagała wprowadzenia drobnych zmian w procesie rejestracji dedykowanych urządzeń z systemem Android Enterprise. W nadchodzącej, marcowej aktualizacji usługi (2003) wprowadzimy dalsze zmiany, o których chcemy tutaj poinformować.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli zarządzasz w swoim środowisku dedykowanymi urządzeniami z systemem Android Enterprise, zauważysz, że w marcu rozpocznie się wprowadzanie pewnych zmian.
- Dedykowane urządzenia z systemem Android zarejestrowane przed 22 listopada 2019 lub przed aktualizacją usługi opatrzoną numerem 1911: Na tych urządzeniach jest zainstalowana aplikacja Microsoft Intune. Certyfikaty SCEP wdrożone na urządzeniach i skojarzone z profilami sieci Wi-Fi zaczną obowiązywać, kiedy zmiany w systemach zaplecza zostaną wprowadzone w usłudze Intune w marcu.
- Urządzenia zarejestrowane po 22 listopada 2019 i przed wprowadzeniem tej zmiany w marcu: Na tych urządzeniach jest zainstalowana aplikacja Microsoft Intune. Certyfikaty SCEP wdrożone na urządzeniach i skojarzone z profilami sieci Wi-Fi będą nadal obowiązywać.
- Nowe dedykowane urządzenia z systemem Android Enterprise zarejestrowane po wprowadzeniu tej zmiany w marcu: Podczas rejestracji użytkownicy końcowi będą widzieli inny zestaw kroków na urządzeniach. Rejestracja nadal będzie zaczynać się tak, jak obecnie (od metody QR, NFC, bezobsługowej lub identyfikatora urządzenia), ale nie pojawi się obowiązkowy krok instalacji aplikacji. Zamiast tego aplikacja Microsoft Intune zostanie automatycznie zainstalowana na urządzeniach. W trakcie tego procesu użytkownicy końcowi nie będą też musieli kliknąć opcji „Włącz agenta usługi Intune”. Na urządzeniach będzie można wdrożyć certyfikaty SCEP skojarzone z profilami sieci Wi-Fi.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Zalecamy zaktualizowanie instrukcji dla użytkowników końcowych i poinformowanie swojej pomocy technicznej o tej zmianie. Zaktualizujemy naszą stronę „Co nowego”, a po rozpoczęciu wprowadzania tej zmiany opublikujemy stosowne powiadomienie w Centrum wiadomości.

#### <a name="additional-information"></a>Dodatkowe informacje
[Obsługa certyfikatów SCEP na dedykowanych urządzeniach z systemem Android Enterprise](https://aka.ms/Dedicated_devices_enrollment)

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Zaktualizowano oświadczenie dotyczące obsługi aplikacji mobilnej „Adobe Acrobat Reader dla usługi Intune"<!--5746776-->
Pod koniec sierpnia poinformowaliśmy w dokumencie MC188653, że okres eksploatacji aplikacji mobilnej Adobe Acrobat dla usługi Intune zakończy się 1 grudnia 2019 r. oraz że firma Adobe planuje obsługę zasad ochrony aplikacji usługi Intune w swojej głównej aplikacji Acrobat Reader. Od tego momentu otrzymaliśmy opinie klientów, którzy twierdzili, że potrzebują więcej czasu, aby administratorzy IT mogli nadal traktować aplikację Adobe Acrobat Reader dla usługi Intune jako docelową, a użytkownicy końcowi mogli zacząć z niej korzystać. Mając na uwadze duże użycie aplikacji Adobe Acrobat Reader dla usługi Intune na urządzeniach użytkowników końcowych oraz jej znaczenie w scenariuszach korporacyjnych, chcemy upewnić się, że wszystkie środowiska spełniają wymagania związane z ochroną aplikacji w organizacji. 

Mimo że w zasadach nadal zalecamy używanie ogólnej aplikacji mobilnej Acrobat Reader, ponieważ aplikacja mobilna Acrobat Reader obsługuje zasady ochrony aplikacji i ma zintegrowany zestaw SDK usługi Intune, aplikacja Adobe Acrobat Reader dla usługi Intune będzie obsługiwana do 31 marca 2020 r. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Otrzymujesz tę wiadomość, ponieważ z naszych raportów wynika, że co najmniej jedne zasady w Twojej organizacji dotyczą aplikacji Adobe Acrobat Reader dla usługi Intune i/lub otrzymano poprzednią komunikację dotyczącą zakończenia okresu eksploatacji. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poinformuj użytkowników końcowych i pomoc techniczną o tej zmianie. W celu ustanowienia kanału obsługi pytań związanych z usługą Intune możesz użyć [funkcji informacji pomocy technicznej aplikacji Portal firmy](../apps/company-portal-app.md#support-information).

#### <a name="additional-information"></a>Dodatkowe informacje
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


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
Aby uzyskać więcej informacji, zapoznaj się z dokumentami dotyczącymi [korzystania z przeglądarki Microsoft Edge z zasadami ochrony aplikacji](../apps/manage-microsoft-edge.md) lub [wpisem w blogu pomocy technicznej](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="end-of-support-for-legacy-pc-management"></a>Koniec wsparcia dla zarządzania starszymi komputerami

Zarządzanie starszymi komputerami nie będzie obsługiwane od 15 października 2020. Uaktualnij urządzenia do systemu Windows 10 i zarejestruj je ponownie jako urządzenia oprogramowania Zarządzanie urządzeniami mobilnymi (MDM), aby mogły być dalej zarządzane przez usługę Intune.

[Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator--5857738--"></a>Zmniejszenie wsparcia dla administratora urządzeń z systemem Android<!--5857738-->
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



