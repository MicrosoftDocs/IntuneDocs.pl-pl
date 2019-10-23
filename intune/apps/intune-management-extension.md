---
title: Dodawanie skryptów programu PowerShell dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Tworzenie i uruchamianie skryptów programu PowerShell, przypisywanie zasad skryptu do grup usługi Azure Active Directory, używanie raportów w celu monitorowania skryptów oraz kroki umożliwiające usunięcie skryptów dodawanych na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune. Zobacz też niektóre typowe problemy i rozwiązania.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94653c51bccc59fde93fdacc16f2b83e7860346b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72497792"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune

Rozszerzenie do zarządzania usługi Microsoft Intune służy do przekazywania skryptów programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie do zarządzania rozbudowuje funkcję zarządzania urządzeniami mobilnymi (MDM) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania.

Ta funkcja ma zastosowanie do:

- System Windows 10 lub nowszy

## <a name="move-to-modern-management"></a>Migracja do nowoczesnego zarządzania

Środowisko informatyczne użytkowników końcowych przechodzi transformację cyfrową. Klasyczne, tradycyjne środowisko informatyczne jest oparte na pojedynczej platformie urządzeń, urządzeniach należących do firm, użytkownikach pracujących w biurze i różnych ręcznych, reaktywnych procesach informatycznych. Nowoczesne miejsce pracy obsługuje wiele platform, które należą do użytkowników i do firmy, umożliwia użytkownikom pracę w dowolnym miejscu oraz zapewnia zautomatyzowane i proaktywne procesy informatyczne.

Usługi zarządzania urządzeniami przenośnymi, takie jak Microsoft Intune, mogą zarządzać urządzeniami mobilnymi i stacjonarnymi z systemem Windows 10. Wbudowany klient zarządzania systemu Windows 10 komunikuje się z usługą Intune w celu uruchamiania zadań zarządzania przedsiębiorstwem. Istnieją pewne zadania, których możesz potrzebować, takie jak zaawansowana konfiguracja urządzeń i rozwiązywanie problemów. Na potrzeby zarządzania aplikacjami Win32 możesz użyć funkcji [zarządzania aplikacjami Win32](app-management.md) na urządzeniach z systemem Windows 10.

Rozszerzenie do zarządzania usługi Intune uzupełnia funkcje usług MDM dostarczanych z systemem Windows 10. Można tworzyć skrypty programu PowerShell do uruchamiania na urządzeniach z systemem Windows 10. Na przykład można utworzyć skrypt programu PowerShell, który wykonuje zaawansowane zadania konfiguracji urządzeń. Następnie można przekazać ten skrypt do usługi Intune, przypisać go do grupy w usłudze Azure Active Directory (AD) i uruchomić. Następnie można monitorować stan uruchomienia skryptu od początku do końca.

## <a name="prerequisites"></a>Wymagania wstępne

Rozszerzenie do zarządzania usługi Intune ma poniższe wymagania wstępne. Gdy wymagania wstępne zostaną spełnione, rozszerzenie do zarządzania usługi Intune zainstaluje się automatycznie po przypisaniu skryptu programu PowerShell lub aplikacji Win32 do użytkownika bądź urządzenia.

- W urządzeniach działa system Windows 10 w wersji 1607 lub nowszej. Jeśli urządzenie zostało zarejestrowane w ramach [automatycznej rejestracji zbiorczej](../enrollment/windows-bulk-enroll.md), w urządzeniach musi działać system Windows 10 w wersji 1703 lub nowszej. Rozszerzenie zarządzania usługi Intune nie jest obsługiwane w systemie Windows 10 w trybie S, ponieważ ten tryb nie zezwala na uruchamianie aplikacji spoza sklepu. 
  
- Urządzenia przyłączone do usługi Azure Active Directory (AD), w tym:  
  
  - Dołączone do hybrydowej usługi Azure AD: Urządzenia przyłączone do usługi Azure Active Directory (AD) i lokalnej usługi Active Directory (AD). Aby uzyskać wskazówki, zobacz [Planowanie implementacji przyłączenia do hybrydowej usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).

- Urządzenia zarejestrowane w usłudze Intune, w tym:

  - Urządzenia zarejestrowane w zasadach grupy (GPO). Aby uzyskać wskazówki, zobacz [Automatyczne rejestrowanie urządzenia z systemem Windows 10 za pomocą zasad grupy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).
  
  - Urządzenia ręcznie zarejestrowane w usłudze Intune:
  
    - [Automatyczna rejestracja w usłudze Intune](../enrollment/quickstart-setup-auto-enrollment.md) została włączona w usłudze Azure AD. Użytkownik końcowy loguje się do urządzenia przy użyciu konta użytkownika lokalnego, ręcznie przyłącza urządzenie do usługi Azure AD, a następnie loguje się do urządzenia przy użyciu konta usługi Azure AD.
    
    LUB  
    
    - Użytkownik loguje się do urządzenia przy użyciu swojego konta usługi Azure AD, a następnie rejestruje się w usłudze Intune.

  - Urządzenia współzarządzane używające programu Configuration Manager i usługi Intune. Upewnij się, że obciążenie **Aplikacje klienckie** zostało ustawione na **pilotażową usługę Intune** lub **usługę Intune**. Zapoznaj się z poniższymi artykułami w celu uzyskania wskazówek: 
  
    - [Co to jest współzarządzanie](https://docs.microsoft.com/sccm/comanage/overview) 
    - [Obciążenie Aplikacje klienckie](https://docs.microsoft.com/sccm/comanage/workloads#client-apps)
    - [Przełączanie obciążeń programu Configuration Manager do usługi Intune](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads)
  
> [!TIP]
> Upewnij się, że urządzenia zostały [przyłączone](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) do usługi Azure AD. Urządzenia, które zostały tylko [zarejestrowane](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) w usłudze Azure AD, nie będą otrzymywać skryptów.

## <a name="create-a-script-policy-and-assign-it"></a>Tworzenie zasad skryptu i ich przypisywanie

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzenia** > **Skrypty programu PowerShell** > **Dodaj**.

    ![Dodawanie i używanie skryptów programu PowerShell w usłudze Microsoft Intune](./media/intune-management-extension/mgmt-extension-add-script.png)

3. W obszarze **Podstawy** wprowadź następujące właściwości i wybierz przycisk **Dalej**:
    - **Nazwa**: Wprowadź nazwę skryptu programu PowerShell. 
    - **Opis**: Wprowadź opis skryptu programu PowerShell. To ustawienie jest opcjonalne, ale zalecane.
4. W obszarze **Ustawienia skryptu** wprowadź następujące właściwości i wybierz przycisk **Dalej**:
    - **Lokalizacja skryptu**: Przejdź do skryptu programu PowerShell. Rozmiar skryptu musi być mniejszy niż 200 KB (ASCII).
    - **Uruchom ten skrypt, korzystając z poświadczeń użytych do logowania**: Wybierz opcję **Tak**, aby uruchomić skrypt na urządzeniu przy użyciu poświadczeń użytkownika. Wybierz opcję **Nie** (ustawienie domyślne), aby uruchomić skrypt w kontekście systemu. Wielu administratorów wybiera opcję **Tak**. Jeśli skrypt musi być uruchamiany w kontekście systemu, wybierz opcję **Nie**.
    - **Wymuszaj sprawdzanie podpisu skryptu**: Wybierz opcję **Tak**, jeśli skrypt musi zostać podpisany przez zaufanego wydawcę. Wybierz opcję **Nie** (ustawienie domyślne), jeśli podpis skryptu nie jest wymagany. 
    - **Uruchom skrypt na 64-bitowym hoście programu PowerShell**: Wybierz opcję **Tak**, aby uruchomić skrypt na 64-bitowym hoście programu PowerShell (PS) w 64-bitowej architekturze klienta. Wybierz opcję **Nie** (ustawienie domyślne), aby uruchomić skrypt na 32-bitowym hoście programu PowerShell.

      Wybierając opcję **Tak** lub **Nie**, skorzystaj z poniższej tabeli przedstawiającej działanie nowych i istniejących zasad:

      | Uruchamianie skryptu na 64-bitowym hoście programu PS | Architektura klienta | Nowy skrypt programu PS | Skrypt programu PS dla istniejących zasad |
      | --- | --- | --- | --- | 
      | Nie | 32-bitowa  | 32-bitowy host programu PS jest obsługiwany | Uruchamiany tylko na 32-bitowym hoście programu PS, który działa w architekturach 32-bitowej i 64-bitowej. |
      | Tak | 64-bitowa | Skrypt jest uruchamiany na 64-bitowym hoście programu PS w architekturach 64-bitowych. W przypadku uruchomienia w środowisku 32-bitowym skrypt jest uruchamiany na 32-bitowym hoście programu PS. | Skrypt jest uruchamiany na 32-bitowym hoście programu PS. W przypadku zmiany tego ustawienia na opcję 64-bitową skrypt jest otwierany (nie jest uruchamiany) na 64-bitowym hoście programu PS i następuje raportowanie wyników. W przypadku uruchomienia w środowisku 32-bitowym skrypt jest uruchamiany na 32-bitowym hoście programu PS. |

5. Wybierz pozycję **Tagi zakresu**. Tagi zakresu są opcjonalne. W artykule [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](../fundamentals/scope-tags.md) znajduje się więcej informacji.

    Aby dodać tag zakresu:

    1. Wybierz kolejno pozycje **Wybierz zakres tagów** > wybierz istniejący tag zakresu z listy > **Wybierz**.

    2. Po zakończeniu wybierz przycisk **Dalej**.

6. Wybierz pozycję **Przypisania** > **Wybierz grupy do uwzględnienia**. Zostanie wyświetlona Istniejąca lista grup usługi Azure AD.

    1. Wybierz co najmniej jedną grupę obejmującą użytkowników, których urządzenia otrzymują skrypt. Wybierz pozycję **Wybierz**. Wybrane grupy zostaną wyświetlone na liście i zostaną im przypisane zasady.

        > [!NOTE]
        > Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń urządzeń lub użytkowników usługi Azure AD.

    2. Wybierz pozycję **Dalej**.

        ![Przypisywanie lub wdrażanie skryptu programu PowerShell do grup urządzeń w usłudze Microsoft Intune](./media/intune-management-extension/mgmt-extension-assignments.png)

7. W obszarze **Przejrzyj i dodaj** zostanie wyświetlone podsumowanie skonfigurowanych ustawień. Wybierz pozycję **Dodaj**, aby zapisać skrypt. Po wybraniu pozycji **Dodaj** zasady zostaną wdrożone w wybranych grupach.

## <a name="important-considerations"></a>Ważne zagadnienia

- Jeśli skrypty zostały ustawione na kontekst użytkownika, a użytkownik końcowy ma uprawnienia administratora, domyślnie skrypt programu PowerShell jest uruchamiany w obrębie uprawnienia administratora.

- Użytkownicy końcowi nie muszą logować się na urządzeniu, aby wykonywać skrypty programu PowerShell.

- Klient rozszerzenia do zarządzania usługi Intune co godzinę oraz po każdym ponownym uruchomieniu sprawdza, czy w usłudze Intune pojawiły się nowe skrypty lub zmiany skryptów. Po przypisaniu zasad do grup usługi Azure AD skrypt programu PowerShell jest uruchamiany, a wyniki jego działania są zgłaszane. Ponowne wykonanie skryptu następuje dopiero w przypadku zmiany w skrypcie lub zasadach.

## <a name="monitor-run-status"></a>Monitorowanie stanu uruchomienia

Stan uruchamiania skryptów programu PowerShell można monitorować dla użytkowników i urządzeń w witrynie Azure Portal.

W obszarze **Skrypty programu PowerShell** wybierz skrypt do monitorowania, wybierz pozycję **Monitoruj**, a następnie wybierz jeden z następujących raportów:

- **Stan urządzenia**
- **Stan użytkownika**

## <a name="intune-management-extension-logs"></a>Dzienniki rozszerzenia do zarządzania usługi Intune

Typowa lokalizacja dzienników agenta na maszynie klienta to folder `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Do wyświetlenia plików dzienników możesz użyć narzędzia [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools). 

![Zrzut ekranu lub przykładowe dzienniki agenta cmtrace w usłudze Microsoft Intune](./media/apps-win32-app-management/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Usuwanie skryptu

W obszarze **Skrypty programu PowerShell** kliknij skrypt prawym przyciskiem myszy i wybierz pozycję **Usuń**.

## <a name="common-issues-and-resolutions"></a>Typowe problemy i rozwiązania

### <a name="issue-intune-management-extension-doesnt-download"></a>Problem: Rozszerzenie do zarządzania usługi Intune nie jest pobierane

**Możliwe rozwiązania**:

- Urządzenie nie jest przyłączone do usługi Azure AD. Urządzenia muszą spełniać [wymagania wstępne](#prerequisites) (w tym artykule). 
- Do grup, do których należy użytkownik lub urządzenie, nie są przypisane skrypty programu PowerShell ani aplikacje Win32.
- Nie można zaewidencjonować urządzenia w usłudze Intune z powodu braku dostępu do Internetu, braku dostępu do usług powiadomień WNS itp.
- Urządzenie jest w trybie S. Rozszerzenie zarządzania usługi Intune nie jest obsługiwane w urządzeniach działających w trybie S. 

Aby sprawdzić, czy urządzenie jest zarejestrowane automatycznie, możesz wykonać następujące czynności:

  1. Przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
  2. Wybierz dołączone konto > **Informacje**.
  3. W obszarze **Zaawansowany raport diagnostyczny** wybierz pozycję **Utwórz raport**.
  4. Otwórz element `MDMDiagReport` w przeglądarce internetowej.
  5. Wyszukaj właściwość **MDMDeviceWithAAD**. Jeśli właściwość istnieje, urządzenie jest rejestrowane automatycznie. Jeśli ta właściwość nie istnieje, urządzenie nie jest automatycznie rejestrowane.

[Włączanie automatycznej rejestracji systemu Windows 10](../enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) obejmuje konfigurację automatycznej rejestracji w usłudze Intune.

### <a name="issue-powershell-scripts-do-not-run"></a>Problem: Nie można uruchomić skryptów programu PowerShell

**Możliwe rozwiązania**:

- Skrypty programu PowerShell nie są uruchamiane przy każdym logowaniu. Są uruchamiane w następujących sytuacjach:

  - Skrypt jest przypisany do urządzenia
  - W przypadku zmiany skryptu przekaż go i przypisz skrypt do użytkownika lub urządzenia
  
    > [!TIP]
    > **Rozszerzenie zarządzania usługi Microsoft Intune** to usługa, która działa w urządzeniu jak inne usługi na liście aplikacji usług (services.msc). Po ponownym uruchomieniu urządzenia ta usługa może również zostać ponownie uruchomiona i może wyszukać przypisane skrypty programu PowerShell w usłudze Intune. Jeśli usługa **Rozszerzenie zarządzania usługi Microsoft Intune** ma ustawienie Ręcznie, nie zostanie ponownie uruchomiona po ponownym uruchomieniu urządzenia.

- Upewnij się, że urządzenia zostały [przyłączone do usługi Azure AD](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Urządzenia, które zostały tylko przyłączone do miejsca pracy lub organizacji ([zarejestrowane](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) w usłudze Azure AD), nie będą otrzymywać skryptów.
- Klient rozszerzenia do zarządzania usługi Intune co godzinę sprawdza, czy nie ma zmian skryptu lub zasad w usłudze Intune.
- Upewnij się, że rozszerzenie do zarządzania usługi Intune zostało pobrane do folderu `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Skrypty nie działają na urządzeniach Surface Hub lub w systemie Windows 10 w trybie S.
- Sprawdź dzienniki pod kątem błędów. Zobacz [Dzienniki rozszerzenia do zarządzania usługi Intune](#intune-management-extension-logs) (w tym artykule).
- W przypadku ewentualnych problemów z uprawnieniami upewnij się, że właściwości skryptu programu PowerShell zostały ustawione na `Run this script using the logged on credentials`. Sprawdź również, czy zalogowany użytkownik ma odpowiednie uprawnienia do uruchamiania skryptu.

- Aby wyizolować problemy dotyczące skryptów, wykonaj następujące czynności:

  - Sprawdź konfigurację wykonywania programu PowerShell w urządzeniach. Aby uzyskać wskazówki, zobacz [Zasady wykonywania programu PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6).
  - Uruchom przykładowy skrypt za pomocą rozszerzenia zarządzania usługi Intune. Na przykład utwórz katalog `C:\Scripts` i przydziel wszystkim prawa do pełnej kontroli. Uruchom poniższy skrypt:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Jeśli uruchamianie się powiedzie, powinien zostać utworzony plik output.txt z tekstem „Script worked” (Skrypt zadziałał).

  - Aby przetestować wykonywanie skryptu bez usługi Intune, uruchom skrypty na koncie systemu za pomocą [narzędzia psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) w środowisku lokalnym:

    `psexec -i -s`  
    
  - Jeśli skrypt zgłasza, że został wykonany, ale w rzeczywistości do tego nie doszło, usługa antywirusowa może umieszczać element AgentExecutor w piaskownicy. Poniższy skrypt zawsze zgłasza błąd w usłudze Intune. Testowo można użyć tego skryptu:
  
    ```powershell
    Write-Error -Message "Forced Fail" -Category OperationStopped
    mkdir "c:\temp" 
    echo "Forced Fail" | out-file c:\temp\Fail.txt
    ```

    Jeśli skrypt zgłasza powodzenie, przyjrzyj plik `AgentExecutor.log`, aby potwierdzić, że występuje błąd. Jeśli skrypt zostaje wykonany, długość powinna wynosić > 2.

  - Aby zapisać pliki .error i .output, poniższy fragment kodu wykonuje skrypt przy użyciu elementu AgentExecutor w PSx86 (`C:\Windows\SysWOW64\WindowsPowerShell\v1.0`). Dzienniki są zapisywane w celu przejrzenia przez użytkownika. Należy pamiętać, że rozszerzenie Intune Management Extension czyści dzienniki po wykonaniu skryptu:
  
    ```powershell
    $scriptPath = read-host "Enter the path to the script file to execute"
    $logFolder = read-host "Enter the path to a folder to output the logs to"
    $outputPath = $logFolder+"\output.output"
    $errorPath =  $logFolder+"\error.error"
    $timeoutPath =  $logFolder+"\timeout.timeout"
    $timeoutVal = 60000 
    $PSFolder = "C:\Windows\SysWOW64\WindowsPowerShell\v1.0"
    $AgentExec = "C:\Program Files (x86)\Microsoft Intune Management Extension\agentexecutor.exe"
    &$AgentExec -powershell  $scriptPath $outputPath $errorPath $timeoutPath $timeoutVal $PSFolder 0 0
    ```

## <a name="next-steps"></a>Następne kroki

[Monitorowanie](../device-profile-monitor.md) i [rozwiązywanie problemów](../device-profile-troubleshoot.md) z profilami.
