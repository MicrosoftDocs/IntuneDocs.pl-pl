---
title: Ustawienia usługi Windows Update dla Firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Ustawienia usługi Windows Update dla Firm na urządzeniach z systemem Windows 10, które można wdrożyć przy użyciu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5aaa964151477896c236e504ec9b378cf580e838
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736380"
---
# <a name="windows-update-settings-for-intune"></a>Ustawienia aktualizacji systemu Windows dla usługi Intune  

Zapoznaj się z ustawieniami aktualizacji systemu Windows 10 [konfigurowanymi i zarządzanymi](windows-update-for-business-configure.md) przy użyciu usługi Microsoft Intune.  

W przypadku konfigurowania ustawień pierścieni aktualizacji systemu Windows 10 w usłudze Intune konfigurujesz ustawienia usługi Windows Update. Jeśli ustawienie aktualizacji systemu Windows ma zależność wersji systemu Windows 10, zależność wersji jest zapisywana w obszarze szczegółów ustawień.  

## <a name="update-settings"></a>Ustawienia aktualizacji  

Ustawienia aktualizacji umożliwiają kontrolowanie elementów pobieranych przez urządzenie oraz momentu ich pobrania. Zapoznaj się z dokumentacją systemu Windows, aby uzyskać więcej informacji na temat zachowania poszczególnych ustawień.  

- **Kanał obsługi**  
  **Domyślnie**: Półroczny kanał  
  Windows Update CSP: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  

  Ustaw kanał (gałąź), z którego urządzenie ma otrzymywać aktualizacje systemu Windows. Różne kanały mogą używać innych okresów odroczenia przed dostarczeniem aktualizacji.  

  Na przykład opcja *Półroczny kanał* ma odroczenie o długości sześciu miesięcy. Jeśli używasz tego kanału bez dodatkowych odroczeń związanych z ustawieniem, urządzenie instaluje aktualizację sześć miesięcy po jej wydaniu.  

  Obsługiwane kanały aktualizacji:  

  - Półroczny kanał  
  - Półroczny kanał (kierowany)  
  - Niejawny program testów systemu Windows — szybki  
  - Niejawny program testów systemu Windows — wolny  
  - Wydanie w ramach niejawnego programu testów systemu Windows  

  Jeśli wybierzesz kanał niejawnego programu testów, usługa Intune automatycznie konfiguruje ustawienie aktualizacji Windows [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds), aby kompilacja niejawnego programu testów działała.  


  > [!IMPORTANT]  
  > Począwszy od systemu Windows w wersji 1903, opcja *Półroczny kanał (kierowany)* (SAC-T) została wycofana z użytku. Po tej zmianie opcja SAC-T połączyła się z opcją *Półroczny kanał*. Aby dowiedzieć się więcej na temat tej zmiany oraz jej wpływu na usługę Windows Update dla Firm, zobacz wpis w blogu dla profesjonalistów IT zajmujących się systemem Windows: [Windows Update for Business and the retirement of SAC-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523) (Windows Update dla Firm i wycofanie opcji SAC-T).  
 
- **Aktualizacje produktów firmy Microsoft**  
  **Domyślnie**: Zezwalaj  
  Windows Update CSP: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

  - **Zezwalaj** — wybierz opcję *Zezwalaj* na skanowanie w poszukiwaniu aktualizacji aplikacji z Microsoft Update.  
  - **Blokuj — wybierz** blok, aby zapobiec skanowaniu aktualizacji aplikacji.  

- **Sterowniki systemu Windows**  
  **Domyślnie**: Zezwalaj  
  Windows Update CSP: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)  

  - **Zezwalaj** na wybór opcji *Zezwalaj na* Windows Update sterowniki podczas aktualizacji.  
  - **Blokuj-zaznacz** blok, aby zapobiec skanowaniu sterowników.  

- **Okres odroczenia aktualizuj dotyczących jakości (dni)**  
  **Domyślnie**: 0  
  Windows Update CSP: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

  Określ liczbę dni odroczenia aktualizacji dotyczących jakości: od 0 do 30. Jest to okres stosowany oprócz każdego okresu odroczenia stanowiącego część wybranego kanału usługi. Okres odroczenia rozpoczyna się po odebraniu zasad przez urządzenie.  

  Aktualizacje dotyczące jakości są zazwyczaj poprawkami oraz ulepszeniami istniejących funkcji systemu Windows.  

- **Okres odroczenia aktualizacji dotyczących funkcji (dni)**  
  **Domyślnie**: 0  
  Windows Update CSP: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

  Określ liczbę dni odroczenia aktualizacji funkcji. Jest to okres stosowany oprócz każdego okresu odroczenia stanowiącego część wybranego kanału usługi. Okres odroczenia rozpoczyna się po odebraniu zasad przez urządzenie.  

  Obsługiwany okres odroczenia:  

  - *System Windows w wersji 1709 lub nowszej* — od 0 do 365 dni  
  - *System Windows w wersji 1703* — od 0 do 180 dni  

  Aktualizacje dotyczące funkcji są zazwyczaj nowymi funkcjami systemu Windows.  

- **Ustawianie okresu odinstalowywania aktualizacji dotyczących funkcji (2–60 dni)**  
  **Domyślne**: 10  
  Windows Update CSP: [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

  Skonfiguruj czas, po którym nie można odinstalować aktualizacji funkcji.  

  Po upływie tego okresu elementy poprzedniej aktualizacji są usuwane z urządzenia i nie można odinstalować w celu przywrócenia poprzedniej wersji aktualizacji.  

  Na przykład rozważ użycie pierścienia aktualizacji z okresem odinstalowywania aktualizacji funkcji o długości 20 dni. Po 25 dniach decydujesz się na wycofanie najnowszej aktualizacji funkcji i użycie opcji Odinstaluj.  Urządzenia, na których aktualizacja funkcji została zainstalowana ponad 20 dni temu, nie mogą jej odinstalować, ponieważ niezbędne elementy zostały usunięte w ramach konserwacji urządzenia. Natomiast urządzenia, na których aktualizacja funkcji została zainstalowana maksymalnie 19 dni temu, mogą odinstalować aktualizację, jeśli zostaną pomyślnie zaewidencjonowane w celu odebrania polecenia odinstalowania przed przekroczeniem 20-dniowego okresu odinstalowywania.  

## <a name="user-experience-settings"></a>Ustawienia środowiska użytkownika  

Ustawienia środowiska użytkownika umożliwiają kontrolowanie środowiska użytkownika końcowego pod kątem ponownego uruchamiania urządzenia i przypomnień. Zapoznaj się z dokumentacją systemu Windows, aby uzyskać więcej informacji na temat aktualizacji dokumentacji CSP w witrynie Windows Update.  

- **Zachowanie automatycznych aktualizacji**  
  **Domyślnie**: Instaluj automatycznie podczas konserwacji  
  Windows Update CSP: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  Wybierz sposób instalowania automatycznych aktualizacji oraz w razie potrzeby moment ponownego uruchomienia urządzenia.  

  Obsługiwane opcje:  

  - **Powiadamiaj o pobieraniu** — powiadamianie użytkownika przed pobraniem aktualizacji. Użytkownicy wybierają opcję pobierania i instalowania aplikacji.  

  - **Automatycznie instaluj podczas konserwacji** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie jest wymagane, użytkownicy są monitowani o wykonanie tej czynności przez maksymalnie siedem dni, a następnie ponowne uruchomienie jest wymuszane.  

    Ta opcja może powodować automatyczne ponowne uruchamianie urządzenia po zainstalowaniu aktualizacji. Użyj ustawień **godzin aktywnego użytkowania**, aby zdefiniować okres, podczas którego operacje automatycznego ponownego uruchamiania są blokowane:  

    - **Początek godzin aktywnego użytkowania** — określ godzinę rozpoczęcia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Domyślnie**: 8:00  
      Windows Update CSP: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Koniec godzin aktywnego użytkowania** — określ godzinę zakończenia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Domyślnie**: 17:00  
      Windows Update CSP: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatycznie instaluj i ponownie uruchamiaj podczas konserwacji** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie urządzenia jest wymagane, jest ono wykonywane, gdy urządzenie nie jest używane. (Jest to wartość domyślna w przypadku urządzeń niezarządzanych).  

    Ta opcja może powodować automatyczne ponowne uruchamianie urządzenia po zainstalowaniu aktualizacji. Sposób korzystania z ustawień **godzin aktywnego użytkowania** nie został opisany w ustawieniach usługi Windows Update, ale są one używane przez usługę Intune do zdefiniowania okresu, w trakcie którego operacje automatycznego ponownego uruchamiania są blokowane:  

    - **Początek godzin aktywnego użytkowania** — określ godzinę rozpoczęcia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Domyślnie**: 8:00  
      Windows Update CSP: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Koniec godzin aktywnego użytkowania** — określ godzinę zakończenia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Domyślnie**: 17:00  
      Windows Update CSP: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatycznie instaluj i uruchamiaj ponownie w zaplanowanym czasie** — określ dzień i godzinę instalacji. Jeśli nie zostaną one podane, instalacja będzie uruchamiana codziennie o 3:00, po czym nastąpi 15-minutowe odliczanie do ponownego uruchomienia. Zarejestrowane użycia mogą opóźnić odliczanie i ponowne uruchamianie.   
  Windows Update CSP: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

    Ta opcja obsługuje dodatkowe ustawienia.  

    - **Częstotliwość automatycznego zachowania** — za pomocą tego ustawienia możesz planować instalowanie aktualizacji, w tym tydzień, dzień i godzinę.  
      **Domyślnie**: Co tydzień

    - **Planowany dzień instalacji** — określ dzień tygodnia, w którym chcesz instalować aktualizacje.  
      **Domyślnie**: Dowolny dzień  

    - **Planowana godzina instalacji** — określ godzinę, o której chcesz instalować aktualizacje.  
      **Domyślnie**: 3:00  

  - **Automatycznie instaluj i uruchamiaj ponownie bez kontroli użytkownika końcowego** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie urządzenia jest wymagane, jest ono wykonywane, gdy urządzenie nie jest używane. Ta opcja powoduje ustawienie okienka sterowania dla użytkowników końcowych na typ „tylko do odczytu”.  

  - **Resetuj do domyślnych** — przywracanie pierwotnych ustawień automatycznych aktualizacji na maszynach z systemem Windows 10 z aktualizacją z października 2018 r. lub nowszą.  


- **Testy po ponownym uruchomieniu**  
  **Domyślnie**: Zezwalaj  
  Windows Update CSP: [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

  Aby pominąć te testy po ponownym uruchomieniu urządzenia, wybierz pozycję **Pomiń**. 
  
  To ustawienie ma różne wyniki w zależności od wersji systemu Windows na urządzeniach:  
 
  - *System Windows w wersji 1703 i starszych* — po ponownym uruchomieniu urządzenia przeprowadzane są testy obejmujące aktywnych użytkowników, poziom naładowania baterii, uruchomione gry oraz inne.  
  
  - *System Windows w wersji 1709 i nowszych* — w trakcie godzin aktywnego użytkowania następujące procesy nie są uruchamiane w przypadku aktualizacji: skanowanie, pobieranie, instalowanie i ponowne uruchamianie. Po godzinach aktywnego użytkowania procesy aktualizacji są uruchamiane i mogą wybudzić urządzenie ze stanu uśpienia oraz skanować, pobierać, instalować i ponownie uruchamiać urządzenie, o ile sprawdzanie baterii i zasilania zakończy się wynikiem pozytywnym. 

- **Blokowanie wstrzymywania aktualizacji systemu Windows przez użytkownika**  
  **Domyślnie**: Zezwalaj  
  Windows Update CSP: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

  - **Zezwalaj** — Zezwalaj użytkownikom urządzenia na wstrzymanie instalacji aktualizacji.  
  - **Blokuj** — Uniemożliwianie użytkownikom urządzenia wstrzymywania instalacji aktualizacji.  

- **Blokowanie użytkownikowi możliwości skanowania w poszukiwaniu aktualizacji systemu Windows**  
  **Domyślnie**: Zezwalaj  
  Windows Update CSP: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

  - **Zezwalaj** — Zezwalaj użytkownikom urządzenia na używanie Windows Update skanowania w celu znalezienia i pobrania aktualizacji oraz zainstalowania funkcji.
  - **Blokuj** — Uniemożliwianie użytkownikom urządzenia dostępu do Windows Update skanowania, pobierania aktualizacji i instalowania funkcji.  

- **Wymaganie zatwierdzenia przez użytkownika w przypadku ponownego uruchamiania poza godzinami pracy**  
  **Domyślnie**: Nie skonfigurowano  
  Windows Update CSP: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
  - **Nieskonfigurowany**  
  - **Wymagaj** — wymagaj od użytkownika zatwierdzenia ponownego uruchomienia urządzenia poza godzinami pracy.  
   
- **Przypominanie użytkownikowi o wymaganym automatycznym ponownym uruchomieniu przy użyciu przypomnienia możliwego do odrzucenia (godziny)**  
  **Domyślne**: 4  
  Windows Update CSP: [Update/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

  Określ, jak długo przed automatycznym ponownym uruchomieniem powiadomienie możliwe do odrzucenia ma być wyświetlane na urządzeniu użytkownika w celu przypomnienia mu o tym ponownym uruchomieniu. Obsługiwane są następujące wartości godzin: **2**, **4**, **8**, **12** lub **24**.  
  
  Jeśli wyczyścisz wartość domyślną, to ustawienie *nie zostanie skonfigurowane*.  

- **Przypominanie użytkownikowi o wymaganym automatycznym ponownym uruchomieniu przy użyciu przypomnienia trwałego (minuty)**  
  **Domyślne**: 15  
  Windows Update CSP: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)  

  Określ, jak długo przed automatycznym ponownym uruchomieniem ostrzeżenie niemożliwe do odrzucenia ma być wyświetlane na urządzeniu użytkownika w celu przypomnienia mu o tym ponownym uruchomieniu. Obsługiwane są następujące wartości minut: **15**, **30** lub **60**.  

  Jeśli wyczyścisz wartość domyślną, to ustawienie *nie zostanie skonfigurowane*.  

- **Zmień poziom aktualizacji powiadomienia**  
  **Domyślnie**: Użyj domyślnych powiadomień usługi Windows Update  
  Windows Update CSP: [Update/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)
  
  Określ poziom powiadomień usługi Windows Update wyświetlanych użytkownikom. To ustawienie nie steruje tym, jak i kiedy aktualizacje są pobierane ani instalowane.  

  Obsługiwane opcje:
  - **Nieskonfigurowany**
  - **Użyj domyślnych powiadomień usługi Windows Update**
  - **Wyłącz wszystkie powiadomienia, wykluczając ostrzeżenia o ponownym uruchomieniu**
  - **Wyłącz wszystkie powiadomienia, w tym ostrzeżenia o ponownym uruchomieniu**  

- **Zezwalanie użytkownikowi na ponowne uruchamianie (ponowne uruchomienie wymagające interwencji użytkownika)**  
  **Domyślnie**: Nie skonfigurowano  
  > [!IMPORTANT]  
  > Ustawienia *ponownego uruchamiania* nie są już zalecane do użycia. Zamiast tego należy użyć nowych ustawień *terminu ostatecznego* , które zastępują ustawienia *ponownego uruchomienia* . Usługa Intune będzie cofać [obsługę ustawień *ponownego uruchamiania* ](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) w przyszłej aktualizacji.

  Ponowne uruchomienie jest obsługiwane w systemie Windows 10 w wersji 1803 lub nowszej. 

  > [!NOTE]  
  > W systemie Windows 10 w wersji 1809 wprowadzono dodatkowe ustawienia ponownego uruchamiania wymagającego interwencji użytkownika, które umożliwiają stosowanie oddzielnych ustawień aktualizacji dotyczących funkcji i jakości. Natomiast ustawienia zarządzane przez usługę Intune nie są oddzielnie stosowane do różnych typów aktualizacji. W zamian usługa Intune stosuje te same wartości w przypadku aktualizacje dotyczące funkcji i jakości.  
  
  - **Nieskonfigurowany**  
  - **Wymagane** — ustaw na *Wymagane*, aby włączyć opcje ponownego uruchomienia wymagającego interwencji użytkownika dla aktualizacji systemu Windows 10. Te opcje angażują użytkownika urządzenia, aby pomagał w zarządzaniu czasem ponownego uruchamiania urządzenia po zainstalowaniu aktualizacji, która wymaga ponownego uruchomienia.  

  Aby uzyskać więcej informacji na temat tej opcji, zobacz sekcję [Engaged restart](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) (Ponowne uruchomienie wymagające interwencji użytkownika) w dokumentacji systemu Windows 10 dotyczącej wdrażania aktualizacji.  

  Poniższe ustawienia są używane do kontrolowania czasu wykonywania akcji ponownego uruchomienia wymagającego interwencji użytkownika.  

  - **Przenoś użytkowników do ponownego uruchomienia wymagającego interwencji użytkownika po automatycznym ponownym uruchomieniu (dni)**  
    **Domyślnie**: nie skonfigurowano Windows Update CSP: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
    
    Określ wartość **2** do **30**, aby wskazać, jak długo po zainstalowaniu aktualizacji na urządzeniu ma rozpocząć się zachowanie ponownego uruchomienia wymagającego interwencji użytkownika. Po skonfigurowanej liczbie dni użytkownicy otrzymają monit o ponowne uruchomienie urządzenia.  

  - **Odłóż przypomnienie o ponownym uruchomieniu wymagającym interwencji użytkownika (dni)**  
    **Domyślnie**: Nie skonfigurowano    
    Windows Update CSP: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
    
    Określ wartość z przewidzianą od **1** do **3** dla czasu, w którym można przełożyć monit o ponowne uruchomienie.  Po zakończeniu okresu odłożenia monit o ponowne uruchomienie pojawi się jeszcze raz. Użytkownik może nadal odkładać przypomnienie do momentu osiągnięcia terminu instalacji.  

  - **Ustaw termin oczekujących ponownych uruchomień (dni)**  
    **Domyślnie**: Nie skonfigurowano  
    Windows Update CSP: [Update/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  
    Określ wartość **2** do **30** jako maksymalną liczbę dni oczekiwania po rozpoczęciu zachowania ponownego uruchomienia wymagającego interwencji użytkownika, aż urządzenie wymusi wymagane ponowne uruchomienie. To ponowne uruchomienie spowoduje monitowanie użytkowników o zapisanie pracy.

- **Użyj ustawień terminu ostatecznego**  
  **Domyślnie**: Nie skonfigurowano  
  > [!IMPORTANT]  
  > Począwszy od aktualizacji z sierpnia dla usługi Intune, zalecamy użycie następujących ustawień terminu ostatecznego, które zastępują ustawienia ponownego uruchamiania. Usługa Intune spowoduje [wycofanie pomocy technicznej dla ustawień *ponownego uruchamiania* ](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) w przyszłej aktualizacji do usługi Intune.  

  Zezwala użytkownikowi na korzystanie z ustawień terminu ostatecznego.  

  - **Nieskonfigurowany**
  - **Zezwalaj**

  Jeśli ustawiono wartość *Zezwalaj*, można skonfigurować następujące ustawienia dla terminów:

  - **Termin ostateczny aktualizacji funkcji**  
    **Domyślnie**: 7  
    Windows Update CSP: [Update/ConfigureDeadlineForFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)  

    Określa liczbę dni, przez które użytkownik ma automatycznie instalować aktualizacje funkcji (2-30).

  - **Termin ostateczny aktualizacji dotyczących jakości**  
    **Domyślnie**: 7  
    Windows Update CSP: [Update/ConfigureDeadlineForQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)

    Określa liczbę dni, przez które użytkownik przed aktualizacjami jakości będzie automatycznie instalowany na swoich urządzeniach (2-30).

  - **Okres prolongaty**  
    **Wartość domyślna**: 2 Windows Update dostawcy usług kryptograficznych: [Update/ConfigureDeadlineGracePeriod]( https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)

    Określa minimalną liczbę dni po terminie ostatecznym do momentu automatycznego ponownego uruchomienia (0-7).

  - **Automatyczny ponowny rozruch przed terminem ostatecznym**  
    **Wartość domyślna**: tak Windows Update dostawcy usług kryptograficznych: [Update/ConfigureDeadlineNoAutoReboot](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)

    Określa, czy urządzenie powinno zostać rozruchem automatycznym przed upływem terminu ostatecznego.
    - **Tak**
    - **Nie**




### <a name="delivery-optimization-download-mode"></a>Tryb pobierania optymalizacji dostarczania  

Optymalizacja dostarczania nie jest już skonfigurowana w ramach pierścienia aktualizacji systemu Windows 10 w obszarze Aktualizacje oprogramowania. Optymalizacja dostarczania jest teraz konfigurowana za pośrednictwem konfiguracji urządzenia. Poprzednie konfiguracje są nadal dostępne w konsoli. Możesz usunąć poprzednie konfiguracje, edytując je tak, aby były *Nieskonfigurowane*, ale poza tym nie mogą być modyfikowane. 

Aby uniknąć konfliktu pomiędzy nowymi i starymi zasadami, zobacz [Przechodzenie z istniejących pierścieni aktualizacji do optymalizacji dostarczania](../configuration/delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization), a następnie przenieś ustawienia do profilu optymalizacji dostarczania.
