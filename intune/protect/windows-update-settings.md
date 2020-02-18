---
title: Ustawienia usługi Windows Update dla Firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Ustawienia usługi Windows Update dla Firm na urządzeniach z systemem Windows 10, które można wdrożyć przy użyciu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 06982bdf0aff1870f1a759f68bc6cdd48227a3cf
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 02/11/2020
ms.locfileid: "77125000"
---
# <a name="windows-update-settings-for-intune"></a>Ustawienia aktualizacji systemu Windows dla usługi Intune  

Zapoznaj się z ustawieniami aktualizacji systemu Windows 10 [konfigurowanymi i zarządzanymi](windows-update-for-business-configure.md) przy użyciu usługi Microsoft Intune.  

W przypadku konfigurowania ustawień pierścieni aktualizacji systemu Windows 10 w usłudze Intune konfigurujesz ustawienia usługi Windows Update. Jeśli ustawienie aktualizacji systemu Windows ma zależność wersji systemu Windows 10, zależność wersji jest zapisywana w obszarze szczegółów ustawień.  

## <a name="update-settings"></a>Ustawienia aktualizacji  

Ustawienia aktualizacji umożliwiają kontrolowanie elementów pobieranych przez urządzenie oraz momentu ich pobrania. Zapoznaj się z dokumentacją systemu Windows, aby uzyskać więcej informacji na temat zachowania poszczególnych ustawień.  

- **Kanał obsługi**  
  **Ustawienie domyślne**: Półroczny kanał  
  Dostawca usług kryptograficznych Windows Update: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  

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
  **Ustawienie domyślne**:  Zezwalaj  
  Dostawca usług kryptograficznych Windows Update: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

  - **Zezwalaj** — wybierz opcję *Zezwalaj*, aby skanować w poszukiwaniu aktualizacji aplikacji z witryny Microsoft Update.  
  - **Blokuj** — wybierz opcję Blokuj, aby zapobiec skanowaniu w poszukiwaniu aktualizacji aplikacji.  

- **Sterowniki systemu Windows**  
  **Ustawienie domyślne**:  Zezwalaj  
  Dostawca usług kryptograficznych Windows Update: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)  

  - **Zezwalaj** — wybierz opcję *Zezwalaj*, aby uwzględniać sterowniki Windows Update podczas aktualizacji.  
  - **Blokuj** — wybierz opcję Blokuj, aby zapobiec skanowaniu w poszukiwaniu sterowników.  

- **Okres odroczenia aktualizuj dotyczących jakości (dni)**  
  **Ustawienie domyślne**: 0  
  Dostawca usług kryptograficznych Windows Update: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

  Określ liczbę dni odroczenia aktualizacji dotyczących jakości: od 0 do 30. Jest to okres stosowany oprócz każdego okresu odroczenia stanowiącego część wybranego kanału usługi. Okres odroczenia rozpoczyna się po odebraniu zasad przez urządzenie.  

  Aktualizacje dotyczące jakości są zazwyczaj poprawkami oraz ulepszeniami istniejących funkcji systemu Windows.  

- **Okres odroczenia aktualizacji dotyczących funkcji (dni)**  
  **Ustawienie domyślne**: 0  
  Dostawca usług kryptograficznych Windows Update: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

  Określ liczbę dni odroczenia aktualizacji funkcji. Jest to okres stosowany oprócz każdego okresu odroczenia stanowiącego część wybranego kanału usługi. Okres odroczenia rozpoczyna się po odebraniu zasad przez urządzenie.  

  Obsługiwany okres odroczenia:  

  - *System Windows w wersji 1709 lub nowszej* — od 0 do 365 dni  
  - *System Windows w wersji 1703* — od 0 do 180 dni  

  Aktualizacje dotyczące funkcji są zazwyczaj nowymi funkcjami systemu Windows.  

- **Ustawianie okresu odinstalowywania aktualizacji dotyczących funkcji (2–60 dni)**  
  **Ustawienie domyślne**: 10  
  Dostawca usług kryptograficznych Windows Update: [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

  Skonfiguruj czas, po którym nie można odinstalować aktualizacji funkcji.  

  Po upływie tego okresu elementy poprzedniej aktualizacji są usuwane z urządzenia i nie można odinstalować w celu przywrócenia poprzedniej wersji aktualizacji.  

  Na przykład rozważ użycie pierścienia aktualizacji z okresem odinstalowywania aktualizacji funkcji o długości 20 dni. Po 25 dniach decydujesz się na wycofanie najnowszej aktualizacji funkcji i użycie opcji Odinstaluj.  Urządzenia, na których aktualizacja funkcji została zainstalowana ponad 20 dni temu, nie mogą jej odinstalować, ponieważ niezbędne elementy zostały usunięte w ramach konserwacji urządzenia. Natomiast urządzenia, na których aktualizacja funkcji została zainstalowana maksymalnie 19 dni temu, mogą odinstalować aktualizację, jeśli zostaną pomyślnie zaewidencjonowane w celu odebrania polecenia odinstalowania przed przekroczeniem 20-dniowego okresu odinstalowywania.  

## <a name="user-experience-settings"></a>Ustawienia środowiska użytkownika  

Ustawienia środowiska użytkownika umożliwiają kontrolowanie środowiska użytkownika końcowego pod kątem ponownego uruchamiania urządzenia i przypomnień. Zapoznaj się z dokumentacją systemu Windows, aby uzyskać więcej informacji na temat aktualizacji dokumentacji CSP w witrynie Windows Update.  

- **Zachowanie automatycznych aktualizacji**  
  **Ustawienie domyślne**: Instaluj automatycznie podczas konserwacji  
  Dostawca usług kryptograficznych Windows Update: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  Wybierz sposób instalowania automatycznych aktualizacji oraz w razie potrzeby moment ponownego uruchomienia urządzenia.  

  Obsługiwane opcje:  

  - **Powiadamiaj o pobieraniu** — powiadamianie użytkownika przed pobraniem aktualizacji. Użytkownicy wybierają opcję pobierania i instalowania aplikacji.  

  - **Automatycznie instaluj podczas konserwacji** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie jest wymagane, użytkownicy są monitowani o wykonanie tej czynności przez maksymalnie siedem dni, a następnie ponowne uruchomienie jest wymuszane.  

    Ta opcja może powodować automatyczne ponowne uruchamianie urządzenia po zainstalowaniu aktualizacji. Użyj ustawień **godzin aktywnego użytkowania**, aby zdefiniować okres, podczas którego operacje automatycznego ponownego uruchamiania są blokowane:  

    - **Początek godzin aktywnego użytkowania** — określ godzinę rozpoczęcia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Ustawienie domyślne**: 8:00  
      Dostawca usług kryptograficznych Windows Update: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Koniec godzin aktywnego użytkowania** — określ godzinę zakończenia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Ustawienie domyślne**: 17:00  
      Dostawca usług kryptograficznych Windows Update: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatycznie instaluj i ponownie uruchamiaj podczas konserwacji** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie urządzenia jest wymagane, jest ono wykonywane, gdy urządzenie nie jest używane. (Jest to wartość domyślna w przypadku urządzeń niezarządzanych).  

    Ta opcja może powodować automatyczne ponowne uruchamianie urządzenia po zainstalowaniu aktualizacji. Sposób korzystania z ustawień **godzin aktywnego użytkowania** nie został opisany w ustawieniach usługi Windows Update, ale są one używane przez usługę Intune do zdefiniowania okresu, w trakcie którego operacje automatycznego ponownego uruchamiania są blokowane:  

    - **Początek godzin aktywnego użytkowania** — określ godzinę rozpoczęcia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Ustawienie domyślne**: 8:00  
      Dostawca usług kryptograficznych Windows Update: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Koniec godzin aktywnego użytkowania** — określ godzinę zakończenia pomijania ponownych uruchomień z powodu instalacji aktualizacji.  
      **Ustawienie domyślne**: 17:00  
      Dostawca usług kryptograficznych Windows Update: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatycznie instaluj i uruchamiaj ponownie w zaplanowanym czasie** — określ dzień i godzinę instalacji. Jeśli nie zostaną one podane, instalacja będzie uruchamiana codziennie o 3:00, po czym nastąpi 15-minutowe odliczanie do ponownego uruchomienia. Zarejestrowane użycia mogą opóźnić odliczanie i ponowne uruchamianie.   
  Dostawca usług kryptograficznych Windows Update: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

    Ta opcja obsługuje dodatkowe ustawienia.  

    - **Częstotliwość automatycznego zachowania** — za pomocą tego ustawienia możesz planować instalowanie aktualizacji, w tym tydzień, dzień i godzinę.  
      **Ustawienie domyślne**: Co tydzień

    - **Planowany dzień instalacji** — określ dzień tygodnia, w którym chcesz instalować aktualizacje.  
      **Ustawienie domyślne**: Dowolny dzień  

    - **Planowana godzina instalacji** — określ godzinę, o której chcesz instalować aktualizacje.  
      **Ustawienie domyślne**: 3:00  

  - **Automatycznie instaluj i uruchamiaj ponownie bez kontroli użytkownika końcowego** — aktualizacje są pobierane automatycznie, a następnie instalowane podczas automatycznej konserwacji, gdy urządzenie nie jest używane ani zasilane za pomocą baterii. Jeśli ponowne uruchomienie urządzenia jest wymagane, jest ono wykonywane, gdy urządzenie nie jest używane. Ta opcja powoduje ustawienie okienka sterowania dla użytkowników końcowych na typ „tylko do odczytu”.  

  - **Resetuj do domyślnych** — przywracanie pierwotnych ustawień automatycznych aktualizacji na maszynach z systemem Windows 10 z aktualizacją z października 2018 r. lub nowszą.  


- **Testy po ponownym uruchomieniu**  
  **Ustawienie domyślne**: Zezwalaj  
  Dostawca usług kryptograficznych Windows Update: [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

  Aby pominąć te testy po ponownym uruchomieniu urządzenia, wybierz pozycję **Pomiń**. 
  
  To ustawienie ma różne wyniki w zależności od wersji systemu Windows na urządzeniach:  
 
  - *System Windows w wersji 1703 i starszych* — po ponownym uruchomieniu urządzenia przeprowadzane są testy obejmujące aktywnych użytkowników, poziom naładowania baterii, uruchomione gry oraz inne.  
  
  - *System Windows w wersji 1709 i nowszych* — w trakcie godzin aktywnego użytkowania następujące procesy nie są uruchamiane w przypadku aktualizacji: skanowanie, pobieranie, instalowanie i ponowne uruchamianie. Po godzinach aktywnego użytkowania procesy aktualizacji są uruchamiane i mogą wybudzić urządzenie ze stanu uśpienia oraz skanować, pobierać, instalować i ponownie uruchamiać urządzenie, o ile sprawdzanie baterii i zasilania zakończy się wynikiem pozytywnym. 

- **Blokowanie wstrzymywania aktualizacji systemu Windows przez użytkownika**  
  **Ustawienie domyślne**: Zezwalaj  
  Dostawca usług kryptograficznych Windows Update: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

  - **Zezwalaj** — zezwalaj użytkownikom urządzenia na wstrzymanie instalacji aktualizacji.  
  - **Blokuj** — nie zezwalaj użytkownikom urządzenia na wstrzymywanie instalacji aktualizacji.  

- **Blokowanie użytkownikowi możliwości skanowania w poszukiwaniu aktualizacji systemu Windows**  
  **Ustawienie domyślne**: Zezwalaj  
  Dostawca usług kryptograficznych Windows Update: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

  - **Zezwalaj** — zezwalaj użytkownikom urządzenia na używanie skanowania Windows Update w celu znajdowania i pobierania aktualizacji oraz instalowania funkcji.
  - **Blokuj** — nie zezwalaj użytkownikom urządzenia na używanie skanowania Windows Update w celu znajdowania i pobierania aktualizacji oraz instalowania funkcji.  

- **Wymaganie zatwierdzenia przez użytkownika w przypadku ponownego uruchamiania poza godzinami pracy**  
  **Ustawienie domyślne**: Nie skonfigurowano  
  Dostawca usług kryptograficznych Windows Update: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
  - **Nieskonfigurowany**  
  - **Wymagaj** — wymagaj od użytkownika zatwierdzenia ponownego uruchomienia urządzenia poza godzinami pracy.  
   
- **Przypominanie użytkownikowi o wymaganym automatycznym ponownym uruchomieniu przy użyciu przypomnienia możliwego do odrzucenia (godziny)**  
  **Ustawienie domyślne**: 4  
  Dostawca usług kryptograficznych Windows Update: [Update/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

  Określ, jak długo przed automatycznym ponownym uruchomieniem powiadomienie możliwe do odrzucenia ma być wyświetlane na urządzeniu użytkownika w celu przypomnienia mu o tym ponownym uruchomieniu. Obsługiwane są następujące wartości godzin: **2**, **4**, **8**, **12** lub **24**.  
  
  Jeśli wyczyścisz wartość domyślną, to ustawienie przyjmie wartość *Nieskonfigurowane*.  

- **Przypominanie użytkownikowi o wymaganym automatycznym ponownym uruchomieniu przy użyciu przypomnienia trwałego (minuty)**  
  **Ustawienie domyślne**: 15  
  Dostawca usług kryptograficznych Windows Update: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)  

  Określ, jak długo przed automatycznym ponownym uruchomieniem ostrzeżenie niemożliwe do odrzucenia ma być wyświetlane na urządzeniu użytkownika w celu przypomnienia mu o tym ponownym uruchomieniu. Obsługiwane są następujące wartości minut: **15**, **30** lub **60**.  

  Jeśli wyczyścisz wartość domyślną, to ustawienie przyjmie wartość *Nieskonfigurowane*.  

- **Zmień poziom aktualizacji powiadomienia**  
  **Ustawienie domyślne**: Użyj domyślnych powiadomień usługi Windows Update  
  Dostawca usług kryptograficznych Windows Update: [Update/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)
  
  Określ poziom powiadomień usługi Windows Update wyświetlanych użytkownikom. To ustawienie nie steruje tym, jak i kiedy aktualizacje są pobierane ani instalowane.  

  Obsługiwane opcje:
  - **Nieskonfigurowany**
  - **Użyj domyślnych powiadomień usługi Windows Update**
  - **Wyłącz wszystkie powiadomienia oprócz ostrzeżeń o ponownym uruchomieniu**
  - **Wyłącz wszystkie powiadomienia, w tym ostrzeżenia o ponownym uruchomieniu**  

- **Użyj ustawień terminów ostatecznych**  
  **Ustawienie domyślne**: Nie skonfigurowano  
 
  Zezwala użytkownikowi na korzystanie z ustawień terminów ostatecznych.  

  - **Nieskonfigurowany**
  - **Zezwalaj**

  Jeśli ustawiono wartość *Zezwalaj*, można skonfigurować następujące ustawienia dla terminów ostatecznych:

  - **Termin ostateczny aktualizacji funkcji**  
    **Ustawienie domyślne**: *Nieskonfigurowany*  
    Dostawca usług kryptograficznych Windows Update: [Update/ConfigureDeadlineForFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)  

    Określa liczbę dni, po których aktualizacje funkcji zostaną automatycznie zainstalowane na urządzeniu użytkownika (2–30).

  - **Termin ostateczny aktualizacji dotyczących jakości**  
    **Ustawienie domyślne**: *Nieskonfigurowany*  
    Dostawca usług kryptograficznych Windows Update: [Update/ConfigureDeadlineForQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)

    Określa liczbę dni, po których aktualizacje dotyczące jakości zostaną automatycznie zainstalowane na urządzeniu użytkownika (2–30).

  - **Okres prolongaty**  
    **Wartość domyślna**: *Nieskonfigurowany* Dostawca usług kryptograficznych Windows Update: [Update/ConfigureDeadlineGracePeriod]( https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)

    Określa minimalną liczbę dni po terminie ostatecznym do momentu automatycznego ponownego uruchomienia (2–7).

  - **Automatyczny ponowny rozruch przed terminem ostatecznym**  
    **Wartość domyślna**: Tak Dostawca usług kryptograficznych Windows Update: [Update/ConfigureDeadlineNoAutoReboot](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)

    Określa, czy urządzenie powinno zostać automatycznie ponownie uruchomione przed upływem terminu ostatecznego.
    - **Tak**
    - **Nie**

### <a name="delivery-optimization-download-mode"></a>Tryb pobierania optymalizacji dostarczania  

Optymalizacja dostarczania nie jest już skonfigurowana w ramach pierścienia aktualizacji systemu Windows 10 w obszarze Aktualizacje oprogramowania. Optymalizacja dostarczania jest teraz konfigurowana za pośrednictwem konfiguracji urządzenia. Poprzednie konfiguracje są nadal dostępne w konsoli. Możesz usunąć poprzednie konfiguracje, edytując je tak, aby były *Nieskonfigurowane*, ale poza tym nie mogą być modyfikowane. 

Aby uniknąć konfliktu pomiędzy nowymi i starymi zasadami, zobacz [Usuwanie optymalizacji dostarczania z pierścieni aktualizacji systemu Windows 10](../configuration/delivery-optimization-windows.md#remove-delivery-optimization-from-windows-10-update-rings), a następnie przenieś ustawienia do profilu optymalizacji dostarczania.
