---
title: Dodawanie skryptów programu PowerShell dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Tworzenie i uruchamianie skryptów programu PowerShell, przypisywanie zasad skryptu do grup usługi Azure Active Directory, używanie raportów w celu monitorowania skryptów oraz kroki umożliwiające usunięcie skryptów dodawanych na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune. Zobacz też niektóre typowe problemy i rozwiązania.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66a23b75913f6465064a988bd8f2ba9c2b4c36d6
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514143"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune

Rozszerzenie do zarządzania usługi Microsoft Intune służy do przekazywania skryptów programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie do zarządzania rozbudowuje funkcję zarządzania urządzeniami mobilnymi (MDM) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania.

Ta funkcja ma zastosowanie do:

- System Windows 10 lub nowszy

## <a name="move-to-modern-management"></a>Migracja do nowoczesnego zarządzania

Środowisko informatyczne użytkowników końcowych przechodzi transformację cyfrową. Klasyczne, tradycyjne środowisko informatyczne jest oparte na pojedynczej platformie urządzeń, urządzeniach należących do firm, użytkownikach pracujących w biurze i różnych ręcznych, reaktywnych procesach informatycznych. Nowoczesne miejsce pracy obsługuje wiele platform, które należą do użytkowników i do firmy, umożliwia użytkownikom pracę w dowolnym miejscu oraz zapewnia zautomatyzowane i proaktywne procesy informatyczne.

Usługi zarządzania urządzeniami przenośnymi, takie jak Microsoft Intune, mogą zarządzać urządzeniami mobilnymi i stacjonarnymi z systemem Windows 10. Wbudowany klient zarządzania systemu Windows 10 komunikuje się z usługą Intune w celu uruchamiania zadań zarządzania przedsiębiorstwem. Istnieją pewne zadania, których możesz potrzebować, takie jak zaawansowana konfiguracja urządzeń i rozwiązywanie problemów. Na potrzeby zarządzania aplikacjami Win32 możesz użyć funkcji [zarządzania aplikacjami Win32](apps-win32-app-management.md) na urządzeniach z systemem Windows 10.

Rozszerzenie do zarządzania usługi Intune uzupełnia funkcje usług MDM dostarczanych z systemem Windows 10. Można tworzyć skrypty programu PowerShell do uruchamiania na urządzeniach z systemem Windows 10. Można na przykład utworzyć skrypt programu PowerShell, który przeprowadza zaawansowane konfiguracje urządzeń, przekazuje skrypt do usługi Intune, przypisuje go do grupy usługi Azure Active Directory (AD) i uruchamia ten skrypt. Następnie można monitorować stan uruchomienia skryptu od początku do końca.

## <a name="prerequisites"></a>Wymagania wstępne

Rozszerzenie do zarządzania usługi Intune ma następujące wymagania wstępne:

- Urządzenia muszą być przyłączone do usługi Azure AD oraz w niej zarejestrowane, a usługi Azure AD i Intune muszą być skonfigurowane na potrzeby [automatycznej rejestracji](quickstart-setup-auto-enrollment.md). Rozszerzenie do zarządzania w usłudze Intune obsługuje urządzenia dołączone do usługi Azure AD, urządzenia dołączone do domeny hybrydowej usługi Azure AD oraz wspólnie zarządzane, zarejestrowane urządzenia z systemem Windows.
- Na urządzeniach musi działać system Windows 10 w wersji 1607 lub nowszej.
- Agent rozszerzenia zarządzania usługi Intune jest instalowany, gdy skrypt programu PowerShell lub aplikacja Win32 jest wdrażana do grupy zabezpieczeń użytkowników lub urządzeń.

## <a name="create-a-script-policy"></a>Tworzenie zasad skryptu 

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzenia** > **Skrypty programu PowerShell** > **Dodaj**.
3. Wprowadź następujące właściwości:
    - **Nazwa**: Wprowadź nazwę skryptu programu PowerShell. 
    - **Opis**: Wprowadź opis skryptu programu PowerShell. To ustawienie jest opcjonalne, ale zalecane. 
    - **Lokalizacja skryptu**: Przejdź do skryptu programu PowerShell. Rozmiar skryptu musi być mniejszy niż 200 KB (ASCII).
4. Wybierz pozycję **Konfiguruj**, a następnie wprowadź następujące właściwości:
    - **Uruchom ten skrypt, korzystając z poświadczeń użytych do logowania**: Wybierz opcję **Tak**, aby uruchomić skrypt na urządzeniu przy użyciu poświadczeń użytkownika. Wybierz opcję **Nie** (ustawienie domyślne), aby uruchomić skrypt w kontekście systemu. Wielu administratorów wybiera opcję **Tak**. Jeśli skrypt musi być uruchamiany w kontekście systemu, wybierz opcję **Nie**.
    - **Wymuszaj sprawdzanie podpisu skryptu**: Wybierz opcję **Tak**, jeśli skrypt musi zostać podpisany przez zaufanego wydawcę. Wybierz opcję **Nie** (ustawienie domyślne), jeśli podpis skryptu nie jest wymagany. 
    - **Uruchom skrypt na 64-bitowym hoście programu PowerShell**: Wybierz opcję **Tak**, aby uruchomić skrypt na 64-bitowym hoście programu PowerShell (PS) w 64-bitowej architekturze klienta. Wybierz opcję **Nie** (ustawienie domyślne), aby uruchomić skrypt na 32-bitowym hoście programu PowerShell.

      Wybierając opcję **Tak** lub **Nie**, skorzystaj z poniższej tabeli przedstawiającej działanie nowych i istniejących zasad:

      | Uruchamianie skryptu na 64-bitowym hoście programu PS | Architektura klienta | Nowy skrypt programu PS | Skrypt programu PS dla istniejących zasad |
      | --- | --- | --- | --- | 
      | Nie | 32-bitowa  | 32-bitowy host programu PS jest obsługiwany | Uruchamiany tylko na 32-bitowym hoście programu PS, który działa w architekturach 32-bitowej i 64-bitowej. |
      | Tak | 64-bitowa | Skrypt jest uruchamiany na 64-bitowym hoście programu PS w architekturach 64-bitowych. W przypadku uruchomienia w środowisku 32-bitowym skrypt jest uruchamiany na 32-bitowym hoście programu PS. | Skrypt jest uruchamiany na 32-bitowym hoście programu PS. W przypadku zmiany tego ustawienia na opcję 64-bitową skrypt jest otwierany (nie jest uruchamiany) na 64-bitowym hoście programu PS i następuje raportowanie wyników. W przypadku uruchomienia w środowisku 32-bitowym skrypt jest uruchamiany na 32-bitowym hoście programu PS. |

    ![Dodawanie i używanie skryptów programu PowerShell w usłudze Microsoft Intune](./media/mgmt-extension-add-script.png)
5. Wybierz pozycję **OK** > **Utwórz**, aby zapisać skrypt.

## <a name="assign-the-policy"></a>Przypisywanie zasad

1. W obszarze **Skrypty programu PowerShell** wybierz skrypt do przypisania, a następnie wybierz pozycję **Zarządzaj** > **Przypisania**.

    ![Przypisywanie lub wdrażanie skryptu programu PowerShell do grup urządzeń w usłudze Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Wybierz pozycję **Wybierz grupy**, aby wyświetlić listę dostępnych grup usługi Azure AD. 
3. Wybierz co najmniej jedną grupę obejmującą użytkowników, których urządzenia otrzymują skrypt. Użyj pozycji **Wybierz**, aby przypisać zasady do wybranych grup.

> [!NOTE]
> - Użytkownicy końcowi nie muszą logować się na urządzeniu, aby wykonywać skrypty programu PowerShell.
> - Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń urządzeń usługi Azure AD.
> - Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń użytkowników usługi Azure AD.

Klient rozszerzenia do zarządzania usługi Intune co godzinę oraz po każdym ponownym uruchomieniu sprawdza, czy w usłudze Intune pojawiły się nowe skrypty lub zmiany skryptów. Po przypisaniu zasad do grup usługi Azure AD skrypt programu PowerShell jest uruchamiany, a wyniki jego działania są zgłaszane. Ponowne wykonanie skryptu następuje dopiero w przypadku zmiany w skrypcie lub zasadach.

## <a name="monitor-run-status"></a>Monitorowanie stanu uruchomienia

Stan uruchamiania skryptów programu PowerShell można monitorować dla użytkowników i urządzeń w witrynie Azure Portal.

W obszarze **Skrypty programu PowerShell** wybierz skrypt do monitorowania, wybierz pozycję **Monitoruj**, a następnie wybierz jeden z następujących raportów:

- **Stan urządzenia**
- **Stan użytkownika**

## <a name="troubleshoot-scripts"></a>Rozwiązywanie problemów ze skryptami

Typowa lokalizacja dzienników agenta na maszynie klienta to folder `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Do wyświetlenia plików dzienników możesz użyć narzędzia [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools). 

![Zrzut ekranu lub przykładowe dzienniki agenta cmtrace w usłudze Microsoft Intune](./media/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Usuwanie skryptu

W obszarze **Skrypty programu PowerShell** kliknij skrypt prawym przyciskiem myszy i wybierz pozycję **Usuń**.

## <a name="common-issues-and-resolutions"></a>Typowe problemy i rozwiązania

Skrypty programu PowerShell nie są uruchamiane przy każdym logowaniu. Są one uruchamiane wyłącznie po ponownym uruchomieniu lub jeśli usługa **rozszerzenia do zarządzania usługi Microsoft Intune** zostanie ponownie uruchomiona. Klient rozszerzenia do zarządzania usługi Intune co godzinę sprawdza, czy nie ma zmian skryptu lub zasad w usłudze Intune.

#### <a name="issue-intune-management-extension-doesnt-download"></a>Problem: Rozszerzenie do zarządzania usługi Intune nie jest pobierane

**Możliwe rozwiązania**:

- Upewnij się, że urządzenia są automatycznie rejestrowane w usłudze Azure AD. W tym celu na urządzeniu: 

  1. Przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
  2. Wybierz dołączone konto > **Informacje**.
  3. W obszarze **Zaawansowany raport diagnostyczny** wybierz pozycję **Utwórz raport**.
  4. Otwórz element `MDMDiagReport` w przeglądarce internetowej i przejdź do sekcji **Zarejestrowane źródła konfiguracji**.
  5. Poszukaj właściwości **MDMDeviceWithAAD**. Jeśli ta właściwość nie istnieje, urządzenie nie jest automatycznie rejestrowane.

    Odpowiednie kroki zostały opisane w sekcji [Włączanie automatycznej rejestracji urządzeń](windows-enroll.md#enable-windows-10-automatic-enrollment) z systemem Windows 10.

#### <a name="issue-powershell-scripts-do-not-run"></a>Problem: Nie można uruchomić skryptów programu PowerShell

**Możliwe rozwiązania**:

- Upewnij się, że rozszerzenie do zarządzania usługi Intune zostało pobrane do folderu `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Skrypty nie działają na urządzeniach Surface Hub.
- Sprawdź dzienniki w folderze `\ProgramData\Microsoft\IntuneManagementExtension\Logs` pod kątem błędów.
- W przypadku ewentualnych problemów z uprawnieniami upewnij się, że właściwości skryptu programu PowerShell zostały ustawione na `Run this script using the logged on credentials`. Sprawdź również, czy zalogowany użytkownik ma odpowiednie uprawnienia do uruchamiania skryptu.
- Aby odizolować problemy ze skryptami, uruchom przykładowy skrypt. Na przykład utwórz katalog `C:\Scripts` i przydziel wszystkim prawa do pełnej kontroli. Uruchom poniższy skrypt:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Jeśli uruchamianie się powiedzie, powinien zostać utworzony plik output.txt z tekstem „Script worked” (Skrypt zadziałał).

- Aby przetestować wykonywanie skryptu bez usługi Intune, uruchom skrypty w kontekście systemowym za pomocą [narzędzia psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) w środowisku lokalnym:

  `psexec -i -s`

## <a name="next-steps"></a>Następne kroki

[Monitorowanie](device-profile-monitor.md) i [rozwiązywanie problemów](device-profile-troubleshoot.md) z profilami.
