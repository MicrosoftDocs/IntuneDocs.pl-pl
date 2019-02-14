---
title: Dodawanie skryptów programu PowerShell w usłudze Microsoft Intune dla urządzeń z systemem Windows 10 — Azure | Microsoft Docs
description: Dodawanie skryptów programu PowerShell, przypisywanie zasad skryptu do grup usługi Azure Active Directory, używanie raportów w celu monitorowania skryptów oraz kroki umożliwiające usunięcie skryptów dodawanych na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune. Zobacz też niektóre typowe problemy i rozwiązania.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 444fd63f8c582d35891dfa5aedb9eadd6626e541
ms.sourcegitcommit: 4bd992da609b8bcc85edc2d64fe8128546aa4617
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55303399"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10

Rozszerzenie do zarządzania usługi Intune służy do przekazywania skryptów programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie do zarządzania rozbudowuje funkcję zarządzania urządzeniami mobilnymi (MDM) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania.

## <a name="moving-to-modern-management"></a>Migracja do nowoczesnego zarządzania

Środowisko informatyczne użytkowników końcowych przechodzi transformację cyfrową. Klasyczne, tradycyjne środowisko informatyczne opiera się na pojedynczej platformie urządzeń, urządzeniach należących do firm, użytkownikach pracujących w biurze i różnych ręcznych, reaktywnych procesach informatycznych. Nowoczesne miejsce pracy obsługuje wiele platform, które należą do użytkowników i do firmy, umożliwia użytkownikom pracę w dowolnym miejscu oraz zapewnia zautomatyzowane i proaktywne procesy informatyczne.

Usługi zarządzania urządzeniami przenośnymi, takie jak Microsoft Intune, mogą zarządzać urządzeniami mobilnymi i stacjonarnymi z systemem Windows 10. Wbudowany klient zarządzania systemu Windows 10 komunikuje się z usługą Intune w celu uruchamiania zadań zarządzania przedsiębiorstwem. Istnieją pewne zadania, których możesz potrzebować, takie jak zaawansowana konfiguracja urządzeń, rozwiązywanie problemów i zarządzanie starszymi aplikacjami Win32, a które aktualnie nie są dostępne w oprogramowaniu MDM dla systemu Windows 10. Aby korzystać z tych funkcji, możesz uruchomić oprogramowanie klienckie usługi Intune na urządzeniach z systemem Windows 10. [Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi](pc-management-comparison.md) to świetny zasób.

Rozszerzenie do zarządzania usługi Intune uzupełnia funkcje usług MDM dostarczanych z systemem Windows 10. Można tworzyć skrypty programu PowerShell do uruchamiania na urządzeniach z systemem Windows 10. Można na przykład utworzyć skrypt programu PowerShell, który instaluje starszą aplikację Win32, przekazać go do usługi Intune, przypisać do grupy usługi Azure Active Directory (AD) i uruchomić. Następnie można monitorować stan uruchomienia skryptu od początku do końca.

## <a name="prerequisites"></a>Wymagania wstępne

Rozszerzenie do zarządzania usługi Intune ma następujące wymagania wstępne:

- Urządzenia muszą być przyłączone do usługi Azure AD oraz w niej zarejestrowane, a usługa Azure AD musi być skonfigurowana na potrzeby [automatycznej rejestracji w usłudze Intune](windows-enroll.md#enable-windows-10-automatic-enrollment). Rozszerzenie zarządzania w usłudze Intune obsługuje urządzenia dołączone do usługi Azure AD, urządzenia dołączone do domeny hybrydowej oraz wspólnie zarządzane, zarejestrowane urządzenia z systemem Windows.
- Na urządzeniach musi działać system Windows 10 w wersji 1607 lub nowszej.
- Agent rozszerzenia zarządzania usługi Intune jest instalowany, gdy skrypt programu PowerShell lub aplikacja Win32 jest wdrażana do grupy zabezpieczeń użytkowników lub urządzeń.

## <a name="create-a-powershell-script-policy"></a>Tworzenie zasad skryptu programu PowerShell 

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > wpisz nazwę usługi **Intune** w filtrze > wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Konfiguracja urządzenia** > **Skrypty programu PowerShell** > **Dodaj**.
3. Wprowadź **nazwę** i **opis** skryptu programu PowerShell. Aby podać **lokalizację skryptu**, przejdź do skryptu programu PowerShell. Rozmiar skryptu musi być mniejszy niż 200 KB (ASCII) lub 100 KB (Unicode).
4. Wybierz pozycję **Konfiguruj**. Następnie określ, czy skrypt ma być uruchamiany przy użyciu poświadczeń użytkownika na urządzeniu (**Tak**), czy w kontekście systemu (**Nie**). Domyślnie skrypt jest uruchamiany w kontekście systemu. Wybierz pozycję **Tak**, chyba że skrypt musi zostać uruchomiony w kontekście systemu. 
  ![Okienko Dodaj skrypt programu PowerShell](./media/mgmt-extension-add-script.png)
5. Określ, czy skrypt musi zostać podpisany przez zaufanego wydawcę (**Tak**). Domyślnie nie jest wymagane, aby skrypt był podpisany. 
6. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**, aby zapisać skrypt.

## <a name="assign-a-powershell-script-policy"></a>Przypisywanie zasad skryptu programu PowerShell

1. W obszarze **Skrypty programu PowerShell** wybierz skrypt do przypisania, a następnie wybierz pozycję **Zarządzaj** > **Przypisania**.

    ![Okienko Dodaj skrypt programu PowerShell](./media/mgmt-extension-assignments.png)

2. Wybierz pozycję **Wybierz grupy**, aby wyświetlić listę dostępnych grup usługi Azure AD. 
3. Wybierz co najmniej jedną grupę obejmującą użytkowników, których urządzenia otrzymują skrypt. Użyj pozycji **Wybierz**, aby przypisać zasady do wybranych grup.

> [!NOTE]
> - Użytkownicy końcowi nie muszą logować się na urządzeniu, aby wykonywać skrypty programu PowerShell.
> - Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń urządzeń usługi Azure AD.
> - Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń użytkowników usługi Azure AD.

Rozszerzenie do zarządzania usługi Intune przeprowadza sprawdzenie w usłudze Intune co godzinę. Po przypisaniu zasad do grup usługi Azure AD skrypt programu PowerShell jest uruchamiany, a wyniki jego działania są zgłaszane.

## <a name="monitor-run-status-for-powershell-scripts"></a>Monitorowanie stanu uruchamiania skryptów programu PowerShell

Stan uruchamiania skryptów programu PowerShell można monitorować dla użytkowników i urządzeń w witrynie Azure Portal.

W obszarze **Skrypty programu PowerShell** wybierz skrypt do monitorowania, wybierz pozycję **Monitoruj**, a następnie wybierz jeden z następujących raportów:

- **Stan urządzenia**
- **Stan użytkownika**

## <a name="troubleshoot-powershell-scripts"></a>Rozwiązywanie problemów ze skryptami programu PowerShell

Typowa lokalizacja dzienników agenta na maszynie klienta to folder `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Do wyświetlenia plików dzienników możesz użyć narzędzia [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools). 

![Zrzut ekranu dzienników agenta](./media/apps-win32-app-10.png)  

## <a name="delete-a-powershell-script"></a>Usuwanie skryptu programu PowerShell

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

#### <a name="issue-the-powershell-scripts-do-not-run"></a>Problem: Nie można uruchomić skryptów programu PowerShell

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
