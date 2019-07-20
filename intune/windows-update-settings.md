---
title: Ustawienia usługi Windows Update dla Firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Ustawienia usługi Windows Update dla Firm na urządzeniach z systemem Windows 10, które można wdrożyć przy użyciu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e9baf3593883cf2fa2402a0b4daec638a336366
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884193"
---
# <a name="windows-update-settings-for-intune"></a>Ustawienia aktualizacji systemu Windows dla usługi Intune  

Zapoznaj się z ustawieniami aktualizacji systemu Windows 10 [konfigurowanymi i zarządzanymi](windows-update-for-business-configure.md) przy użyciu usługi Microsoft Intune.  

W przypadku konfigurowania ustawień pierścieni aktualizacji systemu Windows 10 w usłudze Intune konfigurujesz ustawienia usługi Windows Update. Jeśli ustawienie aktualizacji systemu Windows ma zależność wersji systemu Windows 10, zależność wersji jest zapisywana w obszarze szczegółów ustawień.  

## <a name="update-settings"></a>Ustawienia aktualizacji  

Ustawienia aktualizacji umożliwiają kontrolowanie elementów pobieranych przez urządzenie oraz momentu ich pobrania. Zapoznaj się z dokumentacją systemu Windows, aby uzyskać więcej informacji na temat zachowania poszczególnych ustawień.  

### <a name="servicing-channel"></a>Kanał obsługi  

- **Domyślny**: kanał półroczny (kierowany)  
- **Dokumentacja dotycząca systemu Windows**: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
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
 


### <a name="microsoft-product-updates"></a>Aktualizacje produktów firmy Microsoft  

- **Domyślnie**: Zezwalaj
- **Dokumentacja dotycząca systemu Windows**: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Wybierz pozycję *Zezwalaj*, aby skanować w poszukiwaniu aktualizacji aplikacji z usługi Microsoft Update.    

### <a name="windows-drivers"></a>Sterowniki systemu Windows  

- **Domyślnie**: Zezwalaj
- **Dokumentacja dotycząca systemu Windows**: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Wybierz pozycję *Zezwalaj*, aby uwzględniać sterowniki z usługi Windows Update podczas aktualizacji

### <a name="quality-update-deferral-period-days"></a>Okres odroczenia aktualizacji dotyczących jakości (dni)  

- **Domyślnie**: 0  
- **Dokumentacja dotycząca systemu Windows**: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Określ liczbę dni odroczenia aktualizacji dotyczących jakości: od 0 do 30. Jest to okres stosowany oprócz każdego okresu odroczenia stanowiącego część wybranego kanału usługi. Okres odroczenia rozpoczyna się po odebraniu zasad przez urządzenie.  

Aktualizacje dotyczące jakości są zazwyczaj poprawkami oraz ulepszeniami istniejących funkcji systemu Windows.  

### <a name="feature-update-deferral-period-days"></a>Okres odroczenia aktualizacji funkcji (dni)  

- **Domyślnie**: 0  
- **Dokumentacja dotycząca systemu Windows**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Określ liczbę dni odroczenia aktualizacji funkcji. Jest to okres stosowany oprócz każdego okresu odroczenia stanowiącego część wybranego kanału usługi. Okres odroczenia rozpoczyna się po odebraniu zasad przez urządzenie.  
Obsługiwany okres odroczenia:  

- *System Windows w wersji 1709 lub nowszej*: 0 do 365 dni  
- *System Windows w wersji 1703*: 0 do 180 dni  

Aktualizacje dotyczące funkcji są zazwyczaj nowymi funkcjami systemu Windows.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Ustawianie okresu odinstalowywania aktualizacji funkcji (2–60 dni)  

- **Domyślne**: 10  
- **Dokumentacja dotycząca systemu Windows**: [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Skonfiguruj czas, po którym nie można odinstalować aktualizacji funkcji.  

Po upływie tego okresu elementy poprzedniej aktualizacji są usuwane z urządzenia i nie można odinstalować w celu przywrócenia poprzedniej wersji aktualizacji.  

Na przykład rozważ użycie pierścienia aktualizacji z okresem odinstalowywania aktualizacji funkcji o długości 20 dni. Po 25 dniach decydujesz się na wycofanie najnowszej aktualizacji funkcji i użycie opcji Odinstaluj.  Urządzenia, na których aktualizacja funkcji została zainstalowana ponad 20 dni temu, nie mogą jej odinstalować, ponieważ niezbędne elementy zostały usunięte w ramach konserwacji urządzenia. Natomiast urządzenia, na których aktualizacja funkcji została zainstalowana maksymalnie 19 dni temu, mogą odinstalować aktualizację, jeśli zostaną pomyślnie zaewidencjonowane w celu odebrania polecenia odinstalowania przed przekroczeniem 20-dniowego okresu odinstalowywania.  


## <a name="user-experience-settings"></a>Ustawienia środowiska użytkownika  

Ustawienia środowiska użytkownika umożliwiają kontrolowanie środowiska użytkownika końcowego pod kątem ponownego uruchamiania urządzenia i przypomnień. Zapoznaj się z dokumentacją systemu Windows, aby uzyskać więcej informacji na temat zachowania poszczególnych ustawień.  

### <a name="automatic-update-behavior"></a>Zachowanie automatycznych aktualizacji  

- **Domyślnie**: automatycznie instaluj i uruchamiaj ponownie w zaplanowanym czasie  
- **Dokumentacja dotycząca systemu Windows**: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Wybierz sposób instalowania automatycznych aktualizacji oraz — w razie potrzeby — moment ponownego uruchomienia urządzenia.  

Zapoznaj się z dokumentacją systemu Windows, aby uzyskać pełne informacje na temat następujących obsługiwanych opcji:  

- **Powiadamiaj o pobieraniu** — powiadamianie użytkownika przed pobraniem aktualizacji. Użytkownicy wybierają opcję pobierania i instalowania aplikacji.  

- **Automatycznie instaluj podczas konserwacji** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie jest wymagane, użytkownicy są monitowani o wykonanie tej czynności przez maksymalnie siedem dni, a następnie ponowne uruchomienie jest wymuszane.  

  Ta opcja może powodować automatyczne ponowne uruchamianie urządzenia po zainstalowaniu aktualizacji. Użyj ustawień **godzin aktywnego użytkowania**, aby zdefiniować okres, podczas którego operacje automatycznego ponownego uruchamiania są blokowane:  

  - **Początek godzin aktywnego użytkowania**: określ godzinę rozpoczęcia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
    **Dokumentacja dotycząca Windows**: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Domyślnie**: 8:00  
  
  - **Koniec godzin aktywnego użytkowania**: określ godzinę zakończenia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
    **Dokumentacja dotycząca systemu Windows**: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Domyślnie**: 17:00  

- **Automatycznie instaluj i ponownie uruchamiaj podczas konserwacji** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie urządzenia jest wymagane, jest ono wykonywane, gdy urządzenie nie jest używane. (Jest to wartość domyślna w przypadku urządzeń niezarządzanych).  

  Ta opcja może powodować automatyczne ponowne uruchamianie urządzenia po zainstalowaniu aktualizacji. Sposób korzystania z ustawień **godzin aktywnego użytkowania** nie został opisany w ustawieniach usługi Windows Update, ale są one używane przez usługę Intune do zdefiniowania okresu, w trakcie którego operacje automatycznego ponownego uruchamiania są blokowane:  

  - **Początek godzin aktywnego użytkowania**: określ godzinę rozpoczęcia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
    **Dokumentacja dotycząca Windows**: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Domyślnie**: 8:00  

  - **Koniec godzin aktywnego użytkowania**: określ godzinę zakończenia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
    **Dokumentacja dotycząca systemu Windows**: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Domyślnie**: 17:00  

- **Automatycznie instaluj i uruchamiaj ponownie w zaplanowanym czasie** — określ dzień i godzinę instalacji. Jeśli nie zostaną one podane, instalacja będzie uruchamiana codziennie o 3:00, po czym nastąpi 15-minutowe odliczanie do ponownego uruchomienia. Zarejestrowane użycia mogą opóźnić odliczanie i ponowne uruchamianie.  
  
  Ta opcja obsługuje dodatkowe ustawienia.  
  **Dokumentacja dotycząca systemu Windows**: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Częstotliwość automatycznego zachowania**: za pomocą tego ustawienia możesz planować instalowanie aktualizacji, w tym tydzień, dzień i godzinę.  
    **Domyślnie**: Co tydzień

  - **Planowany dzień instalacji**: określ dzień tygodnia, w którym chcesz instalować aktualizacje.  
    **Domyślnie**: Dowolny dzień  

  - **Planowana godzina instalacji**: określ godzinę, o której chcesz instalować aktualizacje.  
    **Domyślnie**: 3:00  

- **Automatycznie instaluj i uruchamiaj ponownie bez kontroli użytkownika końcowego** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie urządzenia jest wymagane, jest ono wykonywane, gdy urządzenie nie jest używane. Ta opcja powoduje ustawienie okienka sterowania dla użytkowników końcowych na typ „tylko do odczytu”.  

- **Resetuj do domyślnych** — przywracanie pierwotnych ustawień automatycznych aktualizacji na maszynach z systemem Windows 10 z aktualizacją z października 2018 r. lub nowszą.  


### <a name="restart-checks"></a>Testy po ponownym uruchomieniu  

- **Domyślnie**: Zezwalaj  
- **Dokumentacja dotycząca systemu Windows**: [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

To ustawienie ma różne wyniki w zależności od wersji systemu Windows na urządzeniach:  

- System Windows w wersji 1703 i starszych: po ponownym uruchomieniu urządzenia przeprowadzane są testy obejmujące aktywnych użytkowników, poziom naładowania baterii, uruchomione gry oraz inne. Aby pominąć te testy po ponownym uruchomieniu urządzenia, wybierz pozycję **Pomiń**.  
- Od systemu Windows w wersji 1709: w trakcie godzin aktywnego użytkowania następujące procesy nie są uruchamiane w przypadku aktualizacji: skanowanie, pobieranie, instalowanie i ponowne uruchamianie. Po godzinach aktywnego użytkowania procesy aktualizacji są uruchamiane i mogą wybudzić urządzenie ze stanu uśpienia oraz skanować, pobierać, instalować i ponownie uruchamiać urządzenie, o ile sprawdzanie baterii i zasilania zakończy się wynikiem pozytywnym. Aby uzyskać więcej informacji, zobacz [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>Blokowanie wstrzymywania aktualizacji systemu Windows przez użytkownika  

- **Domyślnie**: Zezwalaj  
- **Dokumentacja dotycząca systemu Windows**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Zezwala użytkownikowi na wstrzymywanie instalacji aktualizacji lub blokuje tę możliwość. 

### <a name="block-user-from-scanning-for-windows-updates"></a>Blokowanie użytkownikowi możliwości skanowania w poszukiwaniu aktualizacji systemu Windows  
- **Domyślnie**: Zezwalaj
- **Dokumentacja dotycząca systemu Windows**: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

Określa, czy dostęp użytkownika do skanowania w poszukiwaniu aktualizacji systemu Windows jest dozwolony, czy zablokowany. Jeśli na przykład skonfigurowano *blokowanie*, użytkownicy nie mogą uzyskiwać dostępu do funkcji skanowania w poszukiwaniu, pobierania ani instalowania aktualizacji systemu Windows.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>Wymaganie zatwierdzenia przez użytkownika w przypadku ponownego uruchamiania poza godzinami pracy  

- **Domyślnie**: Nie skonfigurowano  
- **Dokumentacja dotycząca systemu Windows**: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Wybierz pozycję *Wymagaj*, aby wymagać od użytkownika zatwierdzenia ponownego uruchomienia urządzenia poza godzinami pracy.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Przypominanie użytkownikowi o wymaganym automatycznym ponownym uruchomieniu przy użyciu przypomnienia możliwego do odrzucenia (godziny)  

- **Domyślnie**: *to ustawienie nie jest domyślnie skonfigurowane, a użytkownicy nie otrzymują przypomnienia*.  
- **Dokumentacja dotycząca systemu Windows**: [Update/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Określ, jak długo przed automatycznym ponownym uruchomieniem powiadomienie możliwe do odrzucenia ma być wyświetlane na urządzeniu użytkownika w celu przypomnienia mu o tym ponownym uruchomieniu. Obsługiwane są następujące wartości godzin: **2**, **4**, **8**, **12** lub **24**.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Przypominanie użytkownikowi o wymaganym automatycznym ponownym uruchomieniu przy użyciu przypomnienia trwałego (minuty)  

- **Domyślnie**: *to ustawienie nie jest domyślnie skonfigurowane, a użytkownicy nie otrzymują przypomnienia*.  
- **Dokumentacja dotycząca systemu Windows**: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Określ, jak długo przed automatycznym ponownym uruchomieniem ostrzeżenie niemożliwe do odrzucenia ma być wyświetlane na urządzeniu użytkownika w celu przypomnienia mu o tym ponownym uruchomieniu. Obsługiwane są następujące wartości minut: **15**, **30** lub **60**.  

### <a name="windows-update-notification-level"></a>Poziom powiadomień usługi Windows Update  
- **Domyślnie**: Użyj domyślnych powiadomień usługi Windows Update 
- **Dokumentacja dotycząca systemu Windows**: [Update/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

Określ poziom powiadomień usługi Windows Update wyświetlanych użytkownikom. To ustawienie nie steruje tym, jak i kiedy aktualizacje są pobierane ani instalowane.

### <a name="allow-user-to-restart-engaged-restart"></a>Zezwalanie użytkownikowi na ponowne uruchamianie (ponowne uruchomienie wymagające interwencji użytkownika)  

- **Domyślnie**: Nie skonfigurowano  
- **Dokumentacja dotycząca systemu Windows**: *Nie dotyczy*  
- **Wersja systemu Windows**: ustawienie obsługiwane w systemie Windows 10 w wersji 1803 i nowszych  

  > [!NOTE]  
  > W systemie Windows 10 w wersji 1809 wprowadzono dodatkowe ustawienia ponownego uruchamiania wymagającego interwencji użytkownika, które umożliwiają stosowanie oddzielnych ustawień aktualizacji dotyczących funkcji i jakości. Natomiast ustawienia zarządzane przez usługę Intune nie są oddzielnie stosowane do różnych typów aktualizacji. W zamian usługa Intune stosuje te same wartości w przypadku aktualizacje dotyczące funkcji i jakości.  

Wybranie wartości **Wymagane** powoduje włączenie opcji ponownego uruchomienia wymagającego interwencji użytkownika dla aktualizacji systemu Windows 10. Te opcje angażują użytkownika urządzenia, aby pomagał w zarządzaniu czasem ponownego uruchamiania urządzenia po zainstalowaniu aktualizacji, która wymaga ponownego uruchomienia.  

Aby uzyskać więcej informacji na temat tej opcji, zobacz sekcję [Engaged restart](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) (Ponowne uruchomienie wymagające interwencji użytkownika) w dokumentacji systemu Windows 10 dotyczącej wdrażania aktualizacji.  

Poniższe ustawienia są używane do kontrolowania czasu wykonywania akcji ponownego uruchomienia wymagającego interwencji użytkownika.  

- **Przenoś użytkowników do ponownego uruchomienia wymagającego interwencji użytkownika po automatycznym ponownym uruchomieniu (dni)**  
  - **Domyślnie**: domyślnie to ustawienie nie jest skonfigurowane, ale obsługuje wartość z zakresu od **2** do **30**.  
  - **Dokumentacja dotycząca systemu Windows**: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Określ, jak długo po zainstalowaniu aktualizacji na urządzeniu ma rozpocząć się zachowanie ponownego uruchomienia wymagającego interwencji użytkownika. Po skonfigurowanej liczbie dni użytkownicy otrzymają monit o ponowne uruchomienie urządzenia.  

- **Odłóż przypomnienie o ponownym uruchomieniu wymagającym interwencji użytkownika (dni)**  
  - **Domyślnie**: domyślnie to ustawienie nie jest skonfigurowane, ale obsługuje wartość z zakresu od **1** do **3**.  
  - **Dokumentacja dotycząca systemu Windows**: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Określ, o ile można odłożyć monit o ponowne uruchomienie.  Po zakończeniu okresu odłożenia monit o ponowne uruchomienie pojawi się jeszcze raz. Użytkownik może nadal odkładać przypomnienie do momentu osiągnięcia terminu instalacji.  

- **Ustaw termin oczekujących ponownych uruchomień (dni)**  
  - **Domyślnie**: domyślnie to ustawienie nie jest skonfigurowane, ale obsługuje wartość z zakresu od **2** do **30**.  
  - **Dokumentacja dotycząca systemu Windows**: [Update/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Określ maksymalną liczbę dni oczekiwania po rozpoczęciu zachowania ponownego uruchomienia wymagającego interwencji użytkownika, aż urządzenie wymusi wymagane ponowne uruchomienie. To ponowne uruchomienie spowoduje monitowanie użytkowników o zapisanie pracy.

### <a name="delivery-optimization-download-mode"></a>Tryb pobierania optymalizacji dostarczania  

Optymalizacja dostarczania nie jest już skonfigurowana w ramach pierścienia aktualizacji systemu Windows 10 w obszarze Aktualizacje oprogramowania. Optymalizacja dostarczania jest teraz konfigurowana za pośrednictwem konfiguracji urządzenia. Poprzednie konfiguracje są nadal dostępne w konsoli. Możesz usunąć poprzednie konfiguracje, edytując je tak, aby były *Nieskonfigurowane*, ale poza tym nie mogą być modyfikowane. 

Aby uniknąć konfliktu pomiędzy nowymi i starymi zasadami, zobacz [Przechodzenie z istniejących pierścieni aktualizacji do optymalizacji dostarczania](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization), a następnie przenieś ustawienia do profilu optymalizacji dostarczania.
