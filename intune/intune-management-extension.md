---
title: "Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10"
titlesuffix: Azure portal
description: "Dowiedz się, jak przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10."
keywords: 
author: dougeby
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 237d6d090d0aae7f9a0853839b72d55618f4607e
ms.sourcegitcommit: af958afce3070a3044aafea490c8afc55301d9df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2017
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10
Rozszerzenie do zarządzania usługi Intune pozwala przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie do zarządzania uzupełnia możliwości funkcji zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania.

## <a name="moving-to-modern-management"></a>Migracja do nowoczesnego zarządzania
Środowisko informatyczne użytkowników końcowych przechodzi transformację cyfrową. Klasyczne, tradycyjne środowisko informatyczne opiera się na pojedynczej platformie urządzeń, urządzeniach należących do firm, użytkownikach pracujących w biurze i różnych ręcznych, reaktywnych procesach informatycznych. Nowoczesne miejsce pracy obsługuje jednak wiele platform urządzeń, które należą zarówno do użytkowników, jak i do firmy, umożliwia użytkownikom pracę w dowolnym miejscu oraz zapewnia zautomatyzowane i proaktywne procesy informatyczne. 

Usługi MDM, takie jak Microsoft Intune, pozwalają zarządzać urządzeniami z systemem Windows 10 za pomocą protokołu zarządzania MDM. Wbudowany klient zarządzania systemu Windows 10 jest w stanie komunikować się z usługą Intune na potrzeby wykonywania zadań zarządzania przedsiębiorstwem. Ułatwia to wprowadzanie nowoczesnego zarządzania na urządzeniach z systemem Windows 10. Niekiedy jednak są potrzebne pewne funkcje, takie jak zaawansowana konfiguracja urządzeń, rozwiązywanie problemów i zarządzanie starszymi aplikacjami Win32, które aktualnie nie są dostępne w usługach MDM systemu Windows 10. Aby korzystać z tych funkcji, w niektórych przypadkach uruchamia się na urządzeniach z systemem Windows 10 oprogramowanie klienckie usługi Intune. W wyniku tego nie można korzystać z nowych możliwości zapewnianych przez usługi MDM systemu Windows 10. [Porównaj różnice między oprogramowaniem klienckim usługi Intune a usługami MDM systemu Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

Rozszerzenie do zarządzania usługi Intune uzupełnia możliwości usług MDM dostarczanych z systemem Windows 10. Można tworzyć skrypty programu PowerShell do uruchamiania na urządzeniach z systemem Windows 10, które zapewniają wymagane możliwości. Można na przykład utworzyć skrypt programu PowerShell, który instaluje starszą aplikację Win32 na urządzeniach z systemem Windows 10, przekazać go do usługi Intune, przypisać do grupy usługi Azure Active Directory (AD) i uruchomić na urządzeniach z systemem Windows 10. Następnie można monitorować stan uruchomienia skryptu na urządzeniach z systemem Windows 10 od początku do końca.

## <a name="prerequisites"></a>Wymagania wstępne
Rozszerzenie do zarządzania usługi Intune ma następujące wymagania wstępne:
- Urządzenia muszą być przyłączone do usługi Azure AD
- Na urządzeniach musi działać system Windows 10 w wersji 1607 lub nowszej

## <a name="create-a-powershell-script-policy"></a>Tworzenie zasad skryptu programu PowerShell 
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
4. W bloku **Konfiguracja urządzeń** wybierz pozycję **Zarządzaj** > **Skrypty programu PowerShell**.
5. W bloku **Skrypty programu PowerShell** wybierz pozycję **Dodaj skrypt**.
6. W bloku **Dodaj skrypt programu PowerShell** wprowadź **nazwę** i **opis** skryptu programu PowerShell.
7. Aby podać **lokalizację skryptu**, przeglądaj w poszukiwaniu skryptu programu PowerShell. Rozmiar skryptu musi być mniejszy niż 10 KB (ASCII) lub 5 KB (Unicode).
8. Wybierz pozycję **Konfiguruj**, a następnie określ, czy skrypt ma być uruchamiany przy użyciu poświadczeń użytkownika na urządzeniu (**Tak**), czy w kontekście systemu (**Nie**). Domyślnie skrypt jest uruchamiany w kontekście systemu. Wybierz pozycję **Tak**, chyba że skrypt musi zostać uruchomiony w kontekście systemu. 
  ![Blok Dodaj skrypt programu PowerShell](./media/mgmt-extension-add-script.png)
9. Określ, czy skrypt musi być podpisany przez zaufanego wydawcę (**Tak**). Domyślnie nie jest wymagane, aby skrypt był podpisany. 
10. Kliknij przycisk **OK**, a następnie kliknij przycisk **Utwórz**, aby zapisać skrypt.

## <a name="assign-a-powershell-script-policy"></a>Przypisywanie zasad skryptu programu PowerShell
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
4. W bloku **Konfiguracja urządzeń** wybierz pozycję **Zarządzaj** > **Skrypty programu PowerShell**.
5. W bloku **Skrypty programu PowerShell** wybierz skrypt do przypisania, a następnie wybierz pozycję **Zarządzaj** > **Przypisania**.
  ![Blok Dodaj skrypt programu PowerShell](./media/mgmt-extension-assignments.png)
 
6. Wybierz pozycję **Wybierz grupy**, aby wyświetlić listę dostępnych grup usługi Azure AD. 
7. Wybierz grupy, a następnie kliknij przycisk **Wybierz**, aby przypisać zasady do wybranych grup.

Rozszerzenie do zarządzania usługi Intune synchronizuje informacje z usługą Intune co godzinę. Po przypisaniu zasad do grup usługi Azure AD skrypt programu PowerShell będzie uruchamiany, a wyniki jego działania będą zgłaszane. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>Monitorowanie stanu uruchamiania skryptów programu PowerShell
Stan uruchamiania skryptów programu PowerShell można monitorować dla użytkowników i urządzeń w witrynie Azure Portal.
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
4. W bloku **Konfiguracja urządzeń** wybierz pozycję **Zarządzaj** > **Skrypty programu PowerShell**.
5. W bloku **Skrypty programu PowerShell** wybierz skrypt do monitorowania, wybierz pozycję **Monitoruj**, a następnie jeden z następujących raportów:
   - **Stan urządzenia**
   - **Stan użytkownika**
