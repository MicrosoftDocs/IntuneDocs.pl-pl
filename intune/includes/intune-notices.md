---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: a2675b1b601261e673923ab5e3ac41d0f3d83264
ms.sourcegitcommit: 71b0cd7b81178e2f9e9f80830fa9a7985781628b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73057322"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune.

### <a name="plan-for-change-the-server-side-logging-for-siri-commands-setting-will-be-removed-from-the-intune-console----5468501--"></a>Planowanie zmian: Ustawienie „Rejestrowanie poleceń Siri po stronie serwera” zostanie usunięte z konsoli usługi Intune <!-- 5468501-->

Planujemy usunąć ustawienie „Rejestrowanie poleceń Siri po stronie serwera” z konsoli usługi Intune w ramach listopadowej aktualizacji usługi Intune. Ta zmiana wynika z tego, że firma Apple już usunęła to ustawienie po swojej stronie.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po wdrożeniu listopadowej aktualizacja (1911) około połowy listopada zobaczysz, że to ustawienie zostało usunięte z menu ograniczeń urządzenia (Aplikacje wbudowane) dla profilów konfiguracji systemu iOS w konsoli usługi Intune. Może ono pojawić się w zasadach i profilu zarządzania docelowego urządzenia, ale nie będzie miało wpływu na Twoje urządzenie. Nie przewidujemy znacznego wpływu tej zmiany na funkcjonalność, ponieważ obecnie to ustawienie na urządzeniach nie działa, mimo że jest widoczne w profilu zarządzania.

Możesz wybrać jedną z dwóch ścieżek:
- Jeśli chcesz usunąć to ustawienie z zasad, możesz przejść do profilu, który zawiera to ustawienie, wykonać drobną edycję i zapisać zasady. Zasady zostaną ponownie przetworzone w wewnętrznej bazie danych i ustawienie zostanie z nich usunięte.
- Jeśli zdecydujesz się nie wykonywać tego działania, użytkownicy końcowi będą widzieć to ustawienie w profilu zarządzania urządzenia, ale nie będzie ono miało żadnego efektu.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Możesz podjąć odpowiednie działania zgodnie z powyższą sekcją lub pozostawić zasady bez zmian. Gdy ta zmiana zostanie wdrożona, zaktualizujemy stronę nowości i dokumentację.

### <a name="end-of-support-for-legacy-pc-management"></a>Koniec wsparcia dla zarządzania starszymi komputerami

Zarządzanie starszymi komputerami nie będzie obsługiwane od 15 października 2020. Uaktualnij urządzenia do systemu Windows 10 i zarejestruj je ponownie jako urządzenia MDM, aby mogły być dalej zarządzane przez usługę Intune.

[Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Zmniejszenie wsparcia dla administratora urządzeń z systemem Android 
Administrator urządzeń z systemem Android (czasami określany mianem „starszego sposobu” zarządzania systemem Android, opublikowany z systemem Android 2.2) to metoda zarządzania urządzeniami z systemem Android. Jednak obecnie jest dostępna ulepszona funkcja zarządzania w systemie [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (wydanie z systemem Android 5.0). Dążąc do przejścia do nowoczesnego, bardziej zaawansowanego i bezpieczniejszego zarządzania urządzeniami, firma Google ogranicza wsparcie administratora urządzeń w nowych wersjach systemu Android.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Te zmiany w usłudze Google wpłyną na użytkowników usługi Intune w następujący sposób:  
- Usługa Intune będzie w stanie obsługiwać urządzenia z systemem Android 10 i nowszym (znanym także jako Android Q) zarządzane przez administratora urządzeń tylko do lata 2020 r. Wtedy można spodziewać się wydania kolejnej głównej wersji systemu Android.   
- Urządzenia zarządzane przez administratora urządzeń z systemem Android 10 lub nowszym po upływie lata 2020 r. nie będą mogły być już w pełni zarządzane.       
- Nie ma to wpływu na urządzenia z systemem Android zarządzane przez administratora urządzeń, które mają nadal zainstalowany system Android w wersji starszej niż Android 10. Mogą one być nadal w pełni zarządzane przez administratora urządzeń.    
- W przypadku wszystkich urządzeń z systemem Android 10 lub nowszym firma Google ograniczyła możliwość uzyskania dostępu do informacji o identyfikatorze urządzenia przez agentów zarządzania przez administratora urządzeń, takich jak Portal firmy. Ma to wpływ na następujące funkcje usługi Intune po aktualizacji urządzenia do systemu Android 10 lub nowszego:  
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

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizacja aplikacji Portal firmy dla systemu Android do najnowszej wersji <!--4536963-->
W ramach usługi Intune okresowo wydawane są aktualizacje aplikacji Portal firmy dla systemu Android. W listopadzie 2018 roku opublikowaliśmy aktualizację portalu firmy uwzględniającą przełącznik zaplecza, aby przygotować się do zmiany wprowadzonej przez firmę Google, przechodzącej ze swojej dotychczasowej platformy powiadomień do usługi Google Firebase Cloud Messaging (FCM). Po wycofaniu przez Google obecnej platformy powiadomień i przejściu do usługi FCM użytkownicy końcowi będą musieli zaktualizować swoją aplikację Portal firmy do wersji z listopada 2018 r. lub nowszej, aby zachować możliwość komunikowania się ze sklepem Google Play.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Nasza telemetria wskazuje, że masz urządzenia z aplikacją Portal firmy w wersji wcześniejszej niż 5.0.4269.0. Jeśli ta lub nowsza wersja aplikacji Portal firmy nie zostanie zainstalowana, akcje inicjowane na urządzeniu przez specjalistę IT, takie jak czyszczenie, resetowanie hasła, instalowanie dostępnych i wymaganych aplikacji oraz rejestrowanie certyfikatów mogą nie działać zgodnie z oczekiwaniami. Jeśli Twoje urządzenia są zarejestrowane w usłudze Intune za pomocą rozwiązania MDM, wersje oraz użytkowników aplikacji Portal firmy możesz wyświetlić, przechodząc do obszaru Aplikacje klienckie — Odnalezione aplikacje. Wybierając wcześniejsze wersje aplikacji Portal firmy, będzie można zobaczyć, którzy użytkownicy końcowi mają urządzenia z niezaktualizowaną wersją aplikacji.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poproś użytkowników końcowych urządzeń z systemem Android, które nie zostały zaktualizowane, aby zaktualizowali aplikację Portal firmy za pośrednictwem sklepu Google Play. Powiadom dział pomocy technicznej w przypadku, gdy użytkownik nie wybrał opcji automatycznego aktualizowania aplikacji Portal firmy. Skorzystaj z linku w sekcji *Dodatkowe informacje*, aby dowiedzieć się więcej na temat platformy FCM i zmiany wprowadzanej przez firmę Google.

#### <a name="additional-information"></a>Dodatkowe informacje
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-full-screen-experience-coming-to-intune---4593669--"></a>Nowe funkcje obsługi pełnego ekranu w usłudze Intune <!--4593669-->
Usługa Intune w witrynie Azure Portal zyska zaktualizowany interfejs użytkownika funkcji tworzenia i edytowania danych. Nowy interfejs uprości istniejące przepływy pracy dzięki zastosowaniu formatu kreatorów w obrębie pojedynczego bloku. Zmiana ta pozwoli pozbyć się natłoku widocznych jednocześnie bloków, a także wyeliminować konieczność przechodzenia do szczegółów bloków podczas zadań związanych z tworzeniem i edytowaniem informacji. Przepływy pracy dotyczące tworzenia zostaną ponadto zaktualizowane o funkcję przypisań (z wyjątkiem przypisywania aplikacji).

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Obsługa pełnego ekranu w usłudze Intune zostanie wprowadzona zarówno w witrynie portal.azure.com, jak i devicemanagement.microsoft.com w ciągu najbliższych kilku miesięcy. Aktualizacja interfejsu użytkownika nie będzie miała wpływu na działanie istniejących zasad i profilów, ale przepływ pracy ulegnie drobnym zmianom. Na przykład podczas tworzenia nowych zasad będzie można już na tym etapie ustawić niektóre przypisania, zamiast robić to później, już po utworzeniu zasad. *Dodatkowe informacje* o tym, jak te nowe funkcje będą wyglądać w konsoli (wraz ze zrzutami ekranu), można znaleźć we wpisie na blogu.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Nie trzeba podejmować żadnych działań, ale w razie potrzeby można rozważyć zaktualizowanie wskazówek dla specjalistów IT. Naszą dokumentację będziemy aktualizować w miarę wdrażania nowych funkcji w kolejnych blokach usługi Intune w witrynie Azure Portal.

#### <a name="additional-information"></a>Dodatkowe informacje 
https://aka.ms/intune_fullscreen

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

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7----3042987---"></a>Plan zmian w usłudze Intune: Bliski koniec wsparcia dla systemu Windows 7 <!-- 3042987 -->
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
