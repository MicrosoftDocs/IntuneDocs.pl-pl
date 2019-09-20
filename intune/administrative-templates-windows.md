---
title: Używanie szablonów dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Szablony administracyjne w usłudze Microsoft Intune umożliwiają tworzenie grup ustawień dla urządzeń z systemem Windows 10. Użyj tych ustawień w profilu konfiguracji urządzenia, aby sterować programami pakietu Office, przeglądarką Microsoft Edge, zabezpieczać funkcje w programie Internet Explorer, kontrolować dostęp do usługi OneDrive, korzystać z funkcji pulpitu zdalnego, włączać autoodtwarzanie, konfigurować ustawienia zarządzania energią, używać drukowania HTTP, używać różnych opcji logowania użytkowników oraz sterować rozmiarem dziennika zdarzeń.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b41405e2256d6d2608b05a9c7e8a40cbb3ab349
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071068"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Korzystanie z szablonów systemu Windows 10 umożliwiających konfigurowanie ustawień zasad grupy w usłudze Microsoft Intune

Podczas zarządzania urządzeniami w organizacji można utworzyć grupy ustawień, które będą stosowane do różnych grup urządzeń. Na przykład masz kilka grup urządzeń. Dla grupy A chcesz przypisać określony zestaw ustawień. Dla grupy B chcesz przypisać inny zestaw ustawień. Możesz też użyć prostego widoku ustawień, który można skonfigurować.

Możesz wykonać to zadanie przy użyciu **szablonów administracyjnych** w usłudze Microsoft Intune. Szablony administracyjne obejmują setki ustawień, które sterują funkcjami w przeglądarce Microsoft Edge w wersji 77 lub nowszej, programie Internet Explorer, w programach pakietu Microsoft Office, na pulpicie zdalnym, w usłudze OneDrive, dotyczącymi haseł i numerów PIN i nie tylko. Te ustawienia umożliwiają administratorom grup zarządzanie zasadami grupy przy użyciu chmury.

Ustawienia systemu Windows są podobne do ustawień zasad grupy (GPO) w usłudze Active Directory (AD). Te ustawienia są wbudowane w systemie Windows i są [ustawieniami obsługiwanymi przez pliki ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies), które używają formatu XML. Ustawienia pakietu Office i przeglądarki Microsoft Edge są pozyskiwane w ramach plików ADMX i używają ustawień ADMX w [plikach szablonów administracyjnych pakietu Office](https://www.microsoft.com/download/details.aspx?id=49030) i [plikach szablonów administracyjnych przeglądarki Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise). Jednak szablony usługi Intune są w pełni oparte na chmurze. Umożliwiają proste konfigurowanie ustawień i znajdowanie odpowiednich ustawień.

**Szablony administracyjne** są wbudowane w usłudze Intune i nie wymagają dostosowywania, w tym korzystania z identyfikatora OMA-URI. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień szablonu jako pojedynczego miejsca do zarządzania urządzeniami z systemem Windows 10.

W tym artykule przedstawiono procedurę tworzenia szablonu dla urządzeń z systemem Windows 10 i pokazano, jak filtrować wszystkie dostępne ustawienia w usłudze Intune. Podczas tworzenia szablonu jest tworzony profil konfiguracji urządzenia. Następnie można przypisać lub wdrożyć ten profil w urządzeniach z systemem Windows 10 w organizacji.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Niektóre z tych ustawień są dostępne od systemu Windows 10 w wersji 1703 (RS2). Niektóre ustawienia są niedostępne w niektórych wersjach systemu Windows. W celu uzyskania dostępu do najlepszego środowiska zaleca się użycie systemu Windows 10 Enterprise w wersji 1903 (19H1) lub nowszego.

- Ustawienia systemu Windows używają [dostawców CSP zasad systemu Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies). Dostawcy CSP działają w różnych wersjach systemu Windows, takich jak Home, Professional, Enterprise i tak dalej. Aby sprawdzić, czy dostawca CSP działa w określonej wersji, przejdź do artykułu dotyczącego [dostawców CSP zasad systemu Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies).

## <a name="create-a-template"></a>Tworzenie szablonu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź nazwę profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
    - **Typ profilu**: Wybierz pozycję **Szablony administracyjne**.

4. Wybierz przycisk **Utwórz**. W nowym oknie wybierz pozycję **Ustawienia**. Zostanie wyświetlone każde ustawienie. Można użyć strzałek Wstecz i Dalej, aby zobaczyć więcej ustawień:

    ![Wyświetlanie przykładowej listy ustawień i używanie przycisków Wstecz i Dalej](./media/administrative-templates-windows/administrative-templates-sample-settings-list.png)

    > [!TIP]
    > Ustawienia systemu Windows w usłudze Intune są skorelowane z lokalną ścieżką zasad grupy wyświetlaną w Edytorze lokalnych zasad grupy (`gpedit`).

5. Domyślnie na liście rozwijanej jest wyświetlana pozycja **Wszystkie produkty**. Na liście można także filtrować ustawienia w celu wyświetlania tylko ustawień systemu **Windows**, tylko ustawień pakietu **Office** lub tylko ustawień przeglądarki **Edge w wersji 77 lub nowszej**:

    ![Filtrowanie listy w celu wyświetlenia wszystkich ustawień systemu Windows lub pakietu Office w szablonach administracyjnych w usłudze Intune](./media/administrative-templates-windows/administrative-templates-choose-windows-office-all-products.png)

    > [!NOTE]
    > Ustawienia przeglądarki Microsoft Edge dotyczą następujących systemów:
    >
    > - Microsoft Edge w wersji 77 lub nowszej. Aby skonfigurować przeglądarkę Microsoft Edge w wersji 45 lub starszej, zobacz sekcję [Ustawienia ograniczeń urządzenia w przeglądarce Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).
    > - Windows 10 RS4 i nowsze z zainstalowaną aktualizacją [KB 4512509](https://support.microsoft.com/kb/4512509)
    > - Windows 10 RS5 i nowsze z zainstalowaną aktualizacją [KB 4512534](https://support.microsoft.com/kb/4512534)
    > - Windows 10 19H1 i nowsze z zainstalowaną aktualizacją [KB 4512941](https://support.microsoft.com/kb/4512941)

6. Wybierz dowolne ustawienie. Na przykład odfiltruj listę przy użyciu pozycji **Office**, a następnie wybierz pozycję **Aktywuj przeglądanie z ograniczeniami**. Zostanie wyświetlony szczegółowy opis ustawienia. Wybierz pozycję **Włączone** lub **Wyłączone** albo pozostaw ustawienie **Nieskonfigurowane** (wartość domyślna). Ponadto w szczegółowym opisie wyjaśniono, co się dzieje w przypadku wybrania pozycji **Włączone**, **Wyłączone** lub **Nieskonfigurowane**.
7. Wybierz przycisk **OK**, aby zapisać zmiany.

Kontynuuj przeglądanie listy ustawień, a następnie skonfiguruj ustawienia, których chcesz użyć w środowisku. Poniżej przedstawiono kilka przykładów:

- Użyj ustawienia **Ustawienia powiadomień makr języka VBA**, aby obsługiwać makra języka VBA w różnych programach pakietu Microsoft Office, łącznie z programami Word i Excel.
- Użyj ustawienia **Zezwalaj na pobieranie plików**, aby umożliwić lub uniemożliwić pobieranie z programu Internet Explorer.
- Użyj ustawienia **Wymagaj hasła przy wznawianiu pracy komputera (podłączony zasilacz)** , aby monitować użytkowników o podanie hasła podczas wznawiania pracy urządzenia z trybu uśpienia.
- Użyj ustawienia **Pobierz niepodpisane kontrolki ActiveX**, aby uniemożliwić użytkownikom pobieranie niepodpisanych kontrolek ActiveX z programu Internet Explorer.
- Użyj ustawienia **Wyłącz Przywracanie systemu**, aby umożliwić lub uniemożliwić użytkownikom uruchamianie przywracania systemu w urządzeniu.
- Użyj ustawienia **Zezwalaj na importowanie ulubionych**, aby umożliwić lub uniemożliwić użytkownikom importowanie elementów ulubionych z innej przeglądarki do przeglądarki Microsoft Edge.
- I wiele więcej...

## <a name="find-some-settings"></a>Znajdowanie ustawień

W tych szablonach istnieją setki dostępnych ustawień. Aby ułatwić znajdowanie konkretnych ustawień, użyj wbudowanych funkcji:

- W szablonie wybierz kolumnę **Ustawienia**, **Stan**, **Typ ustawienia** lub **Ścieżka**, aby posortować listę. Na przykład wybierz kolumnę **Ścieżka**, aby wyświetlić wszystkie ustawienia w ścieżce `Microsoft Excel`:

  ![Klikanie ścieżki w celu wyświetlenia wszystkich ustawień pogrupowanych według zasad grupy lub ścieżki ADMX w szablonach administracyjnych w usłudze Intune](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- W szablonie użyj pola **Wyszukaj**, aby znaleźć konkretne ustawienia. Możesz wyszukiwać według ścieżki lub tytułu ustawienia. Wyszukaj na przykład tekst `copy`. Zostaną wyświetlone wszystkie ustawienia z tekstem `copy`:

  ![Wyszukiwanie tekstu „copy” w celu wyświetlenia wszystkich ustawień systemu Windows lub pakietu Office w szablonach administracyjnych w usłudze Intune](./media/administrative-templates-windows/search-copy-settings.png) 

  W następnym przykładzie wyszukaj `microsoft word`. Zostaną wyświetlone wszystkie ustawienia, które można ustawić dla programu Microsoft Word. Wyszukaj `explorer`, aby wyświetlić wszystkie ustawienia programu Internet Explorer, które można dodać do szablonu.

## <a name="next-steps"></a>Następne kroki

Szablon został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz szablon (nazywany też profilem)](device-profile-assign.md) i [będziesz monitorować jego stan](device-profile-monitor.md).
