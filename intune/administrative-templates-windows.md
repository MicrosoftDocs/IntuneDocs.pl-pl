---
title: Używanie szablonów dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Szablony administracyjne w usłudze Microsoft Intune umożliwiają tworzenie grup ustawień dla urządzeń z systemem Windows 10. Użyj tych ustawień w profilu konfiguracji urządzenia, aby sterować programami pakietu Office, zabezpieczać funkcje w programie Internet Explorer, kontrolować dostęp do usługi OneDrive, korzystać z funkcji pulpitu zdalnego, włączać autoodtwarzanie, konfigurować ustawienia zarządzania energią, używać drukowania HTTP, używać różnych opcji logowania użytkowników oraz sterować rozmiarem dziennika zdarzeń.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36076aab02f16937066cb3d47d573f7c74dd6277
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55833620"
---
# <a name="windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Szablony systemu Windows 10 umożliwiające konfigurowanie ustawień zasad grupy w usłudze Microsoft Intune

Podczas zarządzania urządzeniami w organizacji można utworzyć grupę ustawień stosowanych do różnych grup urządzeń. Na przykład masz kilka grup urządzeń. Dla grupy A chcesz przypisać określony zestaw ustawień. Dla grupy B chcesz przypisać inny zestaw ustawień. Możesz też użyć prostego widoku ustawień, który można skonfigurować.

Możesz wykonać to zadanie przy użyciu **szablonów administracyjnych** w usłudze Microsoft Intune. Szablony administracyjne obejmują setki ustawień, które sterują funkcjami w programie Internet Explorer, w programach pakietu Microsoft Office i na pulpicie zdalnym oraz dostępem do usługi OneDrive, a także pozwalają użyć hasła obrazkowego lub numeru PIN, aby się zalogować i nie tylko. Te szablony przypominają ustawienia zasad grupy (GPO) w usłudze Active Directory (AD) i obejmują [ustawienia obsługiwane przez format ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) używające formatu XML. Jednak szablony w usłudze Intune są w pełni oparte na chmurze. Umożliwiają prostsze konfigurowanie ustawień i znajdowanie odpowiednich ustawień.

**Szablony administracyjne** są wbudowane w usłudze Intune i nie wymagają dostosowywania, w tym korzystania z identyfikatora OMA-URI. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień szablonu jako pojedynczego miejsca do zarządzania urządzeniami z systemem Windows 10.

W tym artykule przedstawiono procedurę tworzenia szablonu dla urządzeń z systemem Windows 10 i pokazano, jak filtrować wszystkie dostępne ustawienia w usłudze Microsoft Intune. Podczas tworzenia szablonu jest tworzony profil konfiguracji urządzenia. Następnie można przypisać lub wdrożyć ten profil w urządzeniach z systemem Windows 10 w organizacji.

> [!NOTE]
> Szablony administracyjne są obsługiwane w przypadku urządzeń autonomicznych. Nie są one obecnie obsługiwane przez współzarządzane urządzenia programu System Center Configuration Manager (SCCM).

## <a name="create-a-template"></a>Utworzenie szablonu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź nazwę profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
    - **Typ profilu**: Wybierz pozycję **Szablony administracyjne (wersja zapoznawcza)**.

4. Wybierz przycisk **Utwórz**. W nowym oknie wybierz pozycję **Ustawienia**. Zostanie wyświetlone każde ustawienie. Można użyć strzałek Wstecz i Dalej, aby zobaczyć więcej ustawień:

    ![Wyświetlanie przykładowej listy ustawień i używanie przycisków Wstecz i Dalej](./media/administrative-templates-windows/sample-settings-list-next-page.png)

5. Wybierz dowolne ustawienie. Na przykład wybierz pozycję **Zezwalaj na pobieranie plików**. Zostanie wyświetlony szczegółowy opis ustawienia. Wybierz pozycję **Włącz** lub **Wyłącz** albo pozostaw ustawienie **Nie skonfigurowano** (ustawienie domyślne). Ponadto w szczegółowym opisie wyjaśniono, co się dzieje w przypadku wybrania pozycji **Włącz**, **Wyłącz** lub **Nie skonfigurowano**.
6. Wybierz przycisk **OK**, aby zapisać zmiany.

Kontynuuj przeglądanie listy ustawień, a następnie skonfiguruj ustawienia, których chcesz użyć w środowisku. Poniżej przedstawiono kilka przykładów:

- Użyj ustawienia **Ustawienia powiadomień makr języka VBA**, aby obsługiwać makra języka VBA w różnych programach pakietu Microsoft Office, łącznie z programami Word i Excel.
- Użyj ustawienia **Zezwalaj na pobieranie plików**, aby umożliwić lub uniemożliwić pobieranie z programu Internet Explorer.
- Użyj ustawienia **Wymagaj hasła przy wznawianiu pracy komputera (podłączony zasilacz)**, aby monitować użytkowników o podanie hasła podczas wznawiania pracy urządzenia z trybu uśpienia.
- Użyj ustawienia **Pobierz niepodpisane kontrolki ActiveX**, aby uniemożliwić użytkownikom pobieranie niepodpisanych kontrolek ActiveX z programu Internet Explorer.
- Użyj ustawienia **Wyłącz Przywracanie systemu**, aby umożliwić lub uniemożliwić użytkownikom uruchamianie przywracania systemu w urządzeniu.
- I wiele więcej...

## <a name="find-some-settings"></a>Znajdowanie ustawień

W tych szablonach istnieją setki dostępnych ustawień. Aby ułatwić znajdowanie konkretnych ustawień, użyj wbudowanych funkcji:

- W szablonie wybierz kolumnę **Ustawienia**, **Stan** lub **Ścieżka**, aby posortować listę. Na przykład wybierz kolumnę **Ścieżka**, aby wyświetlić wszystkie ustawienia w ścieżce `Microsoft Excel`:

  ![Kliknij pozycję Ścieżka, aby posortować listę alfabetycznie](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- W szablonie użyj pola **Wyszukaj**, aby znaleźć konkretne ustawienia. Wyszukaj na przykład tekst `copy`. Zostaną wyświetlone wszystkie ustawienia z tekstem `copy`:

  ![Kliknij pozycję Ścieżka, aby posortować listę alfabetycznie](./media/administrative-templates-windows/search-copy-settings.png)

  W następnym przykładzie wyszukaj `microsoft word`. Zostaną wyświetlone wszystkie ustawienia, które można ustawić dla programu Microsoft Word. Wyszukaj `explorer`, aby wyświetlić wszystkie ustawienia programu Internet Explorer, które można dodać do szablonu.

## <a name="next-steps"></a>Następne kroki

Szablon został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz szablon (nazywany też profilem)](device-profile-assign.md) i [będziesz monitorować jego stan](device-profile-monitor.md).
