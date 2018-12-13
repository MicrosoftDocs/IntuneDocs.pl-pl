---
title: Dodawanie skryptów programu PowerShell w usłudze Microsoft Intune dla urządzeń z systemem Windows 10 — Azure | Microsoft Docs
description: Dodawanie skryptów programu PowerShell, przypisywanie zasad skryptu do grup usługi Azure Active Directory, używanie raportów w celu monitorowania skryptów oraz kroki umożliwiające usunięcie skryptów dodawanych na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2c4fb7000d808d860494d2af572c821b42fa6d5c
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579187"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10
Rozszerzenie do zarządzania usługi Intune pozwala przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie do zarządzania uzupełnia możliwości funkcji zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania.

## <a name="moving-to-modern-management"></a>Migracja do nowoczesnego zarządzania
Środowisko informatyczne użytkowników końcowych przechodzi transformację cyfrową. Klasyczne, tradycyjne środowisko informatyczne opiera się na pojedynczej platformie urządzeń, urządzeniach należących do firm, użytkownikach pracujących w biurze i różnych ręcznych, reaktywnych procesach informatycznych. Nowoczesne miejsce pracy obsługuje jednak wiele platform urządzeń, które należą zarówno do użytkowników, jak i do firmy, umożliwia użytkownikom pracę w dowolnym miejscu oraz zapewnia zautomatyzowane i proaktywne procesy informatyczne. 

Usługi MDM, takie jak Microsoft Intune, pozwalają zarządzać urządzeniami z systemem Windows 10 za pomocą protokołu zarządzania MDM. Wbudowany klient zarządzania systemu Windows 10 jest w stanie komunikować się z usługą Intune na potrzeby wykonywania zadań zarządzania przedsiębiorstwem. Ułatwia to wprowadzanie nowoczesnego zarządzania na urządzeniach z systemem Windows 10. Jednak wbudowane funkcje zarządzania urządzeniami przenośnymi w systemie Windows 10 nie oferują pewnych możliwości, które mogą być potrzebne.

Rozszerzenie do zarządzania usługi Intune uzupełnia możliwości usług MDM dostarczanych z systemem Windows 10. Można tworzyć skrypty programu PowerShell do uruchamiania na urządzeniach z systemem Windows 10, które zapewniają wymagane możliwości. Można utworzyć skrypt programu PowerShell konfigurujący ustawienia niestandardowe, przekazać go do usługi Intune, przypisać do grupy usługi Azure Active Directory (AD) i uruchomić na urządzeniach z systemem Windows 10. Można monitorować stan uruchomienia skryptu na urządzeniach z systemem Windows 10 od początku do końca.

## <a name="prerequisites"></a>Wymagania wstępne
Rozszerzenie do zarządzania usługi Intune ma następujące wymagania wstępne:
- Urządzenia muszą być przyłączone do usługi Azure AD. Rozszerzenie zarządzania w usłudze Intune obsługuje urządzenia dołączone do usługi Azure Active Directory, urządzenia dołączone do domeny hybrydowej oraz wspólnie zarządzane, zarejestrowane urządzenia z systemem Windows.
- Na urządzeniach musi działać system Windows 10 w wersji 1607 lub nowszej.
- Automatyczna rejestracja w usłudze MDM musi zostać [włączona w usłudze Azure AD](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment) i urządzenia muszą być automatycznie rejestrowane w usłudze Intune.

## <a name="create-a-powershell-script-policy"></a>Tworzenie zasad skryptu programu PowerShell 
1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzenia** > **Skrypty programu PowerShell** > **Dodaj**.
4. Wprowadź **nazwę** i **opis** skryptu programu PowerShell. Aby podać **lokalizację skryptu**, przejdź do skryptu programu PowerShell. Skrypt musi mieć rozmiar mniejszy niż 200 KB (ASCII) lub 100 KB (Unicode).
5. Wybierz pozycję **Konfiguruj**. Następnie określ, czy skrypt ma być uruchamiany przy użyciu poświadczeń użytkownika na urządzeniu (**Tak**), czy w kontekście systemu (**Nie**). Domyślnie skrypt jest uruchamiany w kontekście systemu. Wybierz pozycję **Tak**, chyba że skrypt musi zostać uruchomiony w kontekście systemu. 
  ![Okienko Dodaj skrypt programu PowerShell](./media/mgmt-extension-add-script.png)
6. Określ, czy skrypt musi zostać podpisany przez zaufanego wydawcę (**Tak**). Domyślnie nie jest wymagane, aby skrypt był podpisany. 
7. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**, aby zapisać skrypt.

## <a name="assign-a-powershell-script-policy"></a>Przypisywanie zasad skryptu programu PowerShell
1. W obszarze **Skrypty programu PowerShell** wybierz skrypt do przypisania, a następnie wybierz pozycję **Zarządzaj** > **Przypisania**.
  ![Okienko Dodaj skrypt programu PowerShell](./media/mgmt-extension-assignments.png)
 
2. Wybierz pozycję **Wybierz grupy**, aby wyświetlić listę dostępnych grup usługi Azure AD. 
3. Wybierz co najmniej jedną grupę zawierającą użytkowników, których urządzenia otrzymują skrypt. Użyj pozycji **Wybierz**, aby przypisać zasady do wybranych grup.

> [!NOTE]
> - Użytkownicy końcowi nie muszą być zalogowani na urządzeniu, aby wykonywać skrypty programu PowerShell. 
> - Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń urządzeń usługi AAD.

Rozszerzenie do zarządzania usługi Intune synchronizuje informacje z usługą Intune co godzinę. Po przypisaniu zasad do grup usługi Azure AD skrypt programu PowerShell jest uruchamiany, a wyniki jego działania są zgłaszane. 
 
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
