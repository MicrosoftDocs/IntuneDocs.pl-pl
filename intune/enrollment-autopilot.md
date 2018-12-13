---
title: Rejestrowanie urządzeń za pomocą rozwiązania Windows Autopilot
titleSuffix: Microsoft Intune
description: Dowiedz się, jak zarejestrować urządzenia z systemem Windows 10 za pomocą rozwiązania Windows Autopilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3a0f9a55fd3d5db8b36db09f4a83d5c09db29725
ms.sourcegitcommit: b93db06ba435555f5b126f97890931484372fcfb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2018
ms.locfileid: "52829117"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Rejestrowanie urządzeń za pomocą rozwiązania Windows Autopilot  
Rozwiązanie Windows Autopilot upraszcza rejestrowanie urządzeń. Tworzenie i konserwacja niestandardowych obrazów systemów operacyjnych zajmuje dużo czasu. Trzeba również poświęcić czas na stosowanie tych niestandardowych obrazów systemów operacyjnych na nowych urządzeniach w celu przygotowania ich do użycia przed przekazaniem użytkownikom końcowym. Dzięki usłudze Microsoft Intune i rozwiązaniu Autopilot można przekazać nowe urządzenia użytkownikom końcowym bez konieczności tworzenia, konserwowania i stosowania niestandardowych obrazów systemów operacyjnych do urządzeń. Jeśli do zarządzania urządzeniami z rozwiązaniem Autopilot używasz usługi Intune, możesz zarządzać zasadami, profilami, aplikacjami i nie tylko po ich zarejestrowaniu. Aby zapoznać się z korzyściami, scenariuszami i wymaganiami wstępnymi, zobacz [Overview of Windows Autopilot (Przegląd rozwiązania Windows Autopilot)](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Wymagania wstępne
- [Włączona funkcja automatycznej rejestracji w systemie Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Subskrypcja usługi Azure Active Directory — wersja Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Jak uzyskać plik CSV do zaimportowania w usłudze InTune

Zobacz artykuł przedstawiający polecenie cmdlet programu powershell, aby uzyskać więcej informacji na temat jego użycia.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo/1.3/Content/Get-WindowsAutoPilotInfo.ps1)

## <a name="add-devices"></a>Dodawanie urządzeń

Urządzenia rozwiązania Autopilot z systemem Windows można dodawać przez zaimportowanie pliku CSV z odpowiednimi informacjami.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Urządzenia**  >  **Import**.

    ![Zrzut ekranu przedstawiający urządzenia rozwiązania Autopilot z systemem Windows](media/enrollment-autopilot/autopilot-import-device.png)

2. W obszarze **Dodawanie urządzeń rozwiązania AutoPilot z systemem Windows** przejdź do pliku CSV z informacjami o urządzeniach, które chcesz dodać. Plik powinien zawierać listę numerów seryjnych, identyfikatorów produktów systemu Windows, skrótów sprzętu i opcjonalnie identyfikatorów zamówień urządzeń.

    ![Zrzut ekranu przedstawiający dodawanie urządzeń rozwiązania Autopilot z systemem Windows](media/enrollment-autopilot/autopilot-import-device2.png)

3. Wybierz pozycję **Importuj**, aby rozpocząć importowanie informacji o urządzeniu. Importowanie może potrwać kilka minut.

4. Po ukończeniu importowania wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Windows Autopilot** > **Urządzenia** > **Synchronizacja**. Zostanie wyświetlony komunikat o synchronizacji w toku. Proces może potrwać kilka minut, w zależności od tego, ile urządzeń jest synchronizowanych.

5. Odśwież widok, aby zobaczyć nowe urządzenia.

## <a name="create-an-autopilot-device-group"></a>Tworzenie grupy urządzeń rozwiązania Autopilot

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycje **Grupy** > **Nowa grupa**.
2. W bloku **Grupa**:
    1. Dla ustawienia **Typ grupy** wybierz pozycję **Zabezpieczenia**.
    2. Wpisz odpowiedni tekst w polach **Nazwa grupy** i **Opis grupy**.
    3. Dla ustawienia **Typ członkostwa** wybierz pozycję **Przypisane** lub **Urządzenie dynamiczne**.
3. Jeśli w poprzednim kroku wybrano pozycję **Przypisane** dla ustawienia **Typ członkostwa**, to w bloku **Grupa** wybierz pozycję **Członkowie** i dodaj urządzenia rozwiązania Autopilot do grupy.
    Urządzenia rozwiązania Autopilot, które nie zostały jeszcze zarejestrowane, to urządzenia, których nazwa jest taka sama jak ich numer seryjny.
4. Jeśli powyżej wybrano pozycję **Urządzenie dynamiczne** dla ustawienia **Typ członkostwa**, to w bloku **Grupa** wybierz pozycję **Dynamiczne urządzenia członkowskie** i wpisz dowolny poniższy kod w polu **Reguła zaawansowana**.
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot, wpisz `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia, wpisz: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia zakupu, wpisz: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po dodaniu kodu w polu **Reguła zaawansowana** wybierz pozycję **Zapisz**.
5. Wybierz pozycję **Utwórz**.  

## <a name="create-an-autopilot-deployment-profile"></a>Tworzenie profilu wdrażania rozwiązania Autopilot
Profile wdrażania rozwiązania Autopilot służą do konfigurowania urządzeń z rozwiązaniem Autopilot.
1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Profile wdrażania**  >  **Utwórz profil**.
2. Podaj **nazwę** i opcjonalny **opis**.
3. Jeśli chcesz, aby wszystkie urządzenia w przypisanych grupach dokonywały automatycznej konwersji do rozwiązania Autopilot, ustaw opcję **Konwertuj wszystkie wybrane urządzenia na potrzeby rozwiązania Autopilot** na wartość **Tak**. Wszystkie urządzenia bez rozwiązania Autopilot w przypisanych grupach będą rejestrować się za pomocą usługi wdrażania rozwiązania Autopilot. Przetwarzanie rejestracji może potrwać do 48 godzin. Jeśli urządzenie nie zostało zarejestrowane i je zresetowano, rozwiązanie Autopilot przeprowadzi jego rejestrację. Po zarejestrowaniu urządzenia w ten sposób wyłączenie tej opcji lub usunięcie przypisania profilu nie spowoduje usunięcia urządzenia z usługi wdrażania rozwiązania Autopilot. Zamiast tego należy [bezpośrednio usunąć urządzenie](enrollment-autopilot.md#delete-autopilot-devices).
4. Dla ustawienia **Tryb wdrażania** wybierz jedną z tych dwóch opcji:
    - **Sterowane przez użytkownika**: urządzenia z tym profilem są skojarzone z użytkownikiem rejestrującym urządzenie. Poświadczenia użytkownika są wymagane do rejestracji urządzenia.
    - **Wdrażanie samodzielne (wersja zapoznawcza)**: (wymaga najnowszej [kompilacji Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/at-work-pro/)) urządzenia z tym profilem nie są kojarzone z użytkownikiem rejestrującym urządzenie. Poświadczenia użytkownika nie są wymagane do zarejestrowania urządzenia.
5. W polu **Dołącz do usługi Azure AD jako** wybierz pozycję **Dołączono do usługi Azure AD**.
6. Wybierz pozycję **Środowisko gotowe do użycia (OOBE, Out-of-box experience)**, skonfiguruj poniższe opcje, a następnie wybierz przycisk **Zapisz**:
    - **Język (region)**\*: wybierz język do użycia dla urządzenia. Ta opcja jest dostępna tylko w przypadku wybrania pozycji **Wdrażanie samodzielne** dla ustawienia **Tryb wdrażania**.
    - **Automatycznie skonfiguruj klawiaturę**\*: jeśli wybrano pozycję **Język (region)**, wybierz pozycję **Tak**, aby pominąć stronę wyboru klawiatury. Ta opcja jest dostępna tylko w przypadku wybrania pozycji **Wdrażanie samodzielne** dla ustawienia **Tryb wdrażania**.
    - **Umowa licencyjna użytkownika oprogramowania (EULA, End User License Agreement)**: (system Windows 10 w wersji 1709 lub nowszej) wybierz, jeśli chcesz, aby umowa licencyjna użytkownika oprogramowania była pokazywana użytkownikom.
    - **Ustawienia prywatności**: wybierz, jeśli chcesz, aby ustawienia prywatności były pokazywane użytkownikom.
    - **Ukryj zmianę opcji konta (tylko niejawny program testów systemu Windows)**: wybierz pozycję **Ukryj**, aby zapobiec wyświetlaniu zmian opcji konta na stronach logowania i błędu domeny firmy. Ta opcja wymaga [skonfigurowania znakowania firmowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Typ konta użytkownika**: wybierz typ konta użytkownika (**Administrator** lub **Standardowe** konto użytkownika).
    - **Zastosuj szablon nazwy komputera (tylko niejawny program testów systemu Windows)**: wybierz pozycję **Tak**, aby utworzyć szablon do stosowania podczas określania nazwy urządzenia w trakcie rejestracji. Nazwy mogą mieć co najwyżej 15 znaków i zawierać litery, cyfry i łączniki. Nazwy nie mogą zawierać samych cyfr. Użyj [makro %SERIAL%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp), aby dodać numer seryjny specyficzny dla sprzętu. Ewentualnie możesz zastosować [makro %RAND:x%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp), aby dodać losowy ciąg cyfr, gdzie x odpowiada liczbie cyfr do dodania. 

6. Wybierz pozycję **Utwórz**, aby utworzyć profil. Profil wdrażania rozwiązania Autopilot jest teraz dostępny do przypisania do urządzeń.

* Pola **Język (region)** i **Automatycznie skonfiguruj klawiaturę** są dostępne tylko w przypadku wybrania pozycji **Wdrażanie samodzielne (wersja zapoznawcza)** dla ustawienia **Tryb wdrażania** (wymaga najnowszej [kompilacji systemu Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/at-work-pro/)).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Przypisywanie profilu wdrażania rozwiązania Autopilot do grupy urządzeń

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Profile wdrażania**, a następnie wybierz profil.
2. W bloku określonego profilu wybierz pozycję **Przypisania**. 
3. Wybierz pozycję **Wybierz grupy**, a następnie w bloku **Wybieranie grup** wybierz grupy, do których chcesz przypisać profil, a następnie wybierz pozycję **Wybierz**.

## <a name="edit-an-autopilot-deployment-profile"></a>Edytowanie profilu wdrażania rozwiązania Autopilot
Po utworzeniu profilu wdrażania rozwiązania Autopilot możesz edytować niektóre jego części.   

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia**.
2. W obszarze **Rejestracja w systemie Windows** w sekcji **Windows Autopilot** wybierz pozycję **Profile wdrażania**.
3. Wybierz profil, który chcesz edytować.
4. Kliknij pozycję **Właściwości** po lewej stronie, aby zmienić nazwę lub opis profilu wdrażania. Po wprowadzeniu zmian kliknij pozycję **Zapisz**.
5. Kliknij pozycję **Ustawienia**, aby wprowadzić zmiany do ustawień trybu OOBE. Po wprowadzeniu zmian kliknij pozycję **Zapisz**.

> [!NOTE]
> Zmiany w profilu są stosowane do urządzeń przypisanych do tego profilu. Zaktualizowany profil nie zostanie jednak zastosowany do urządzenia już zarejestrowanego w usłudze Intune, dopóki nie zostanie zresetowane i ponownie zarejestrowane.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alerty dla urządzeń nieprzypisanych w rozwiązaniu Windows Autopilot <!-- 163236 -->  

Alerty pokażą, ile urządzeń rozwiązania Autopilot nie ma profilów wdrażania rozwiązania Autopilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń rozwiązania Windows Autopilot.


Aby wyświetlić alerty dotyczące nieprzypisanych urządzeń, w [usłudze Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Przegląd**  >  **Nieprzypisane urządzenia**.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Przypisywanie użytkownika do określonego urządzenia rozwiązania Autopilot

Możesz przypisać użytkownika do określonego urządzenia rozwiązania Autopilot. To przypisanie wstępnie wypełnia dane użytkownika z usługi Azure Active Directory na [oznaczonej marką firmy](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) stronie logowania podczas instalowania systemu Windows. Pozwala ono ustawić też niestandardową nazwę powitania. Nie powoduje to wstępnego wypełnienia ani modyfikacji logowania w systemie Windows. W ten sposób można przypisać tylko licencjonowanych użytkowników usługi Intune.

Wymagania wstępne: aplikacja Portal firmy w usłudze Azure Active Directory została skonfigurowana i używasz najnowszej [kompilacji systemu Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/at-work-pro/).

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia** > wybierz urządzenie > **Przypisz użytkownika**.

    ![Zrzut ekranu przypisywania użytkownika](media/enrollment-autopilot/assign-user.png)

2. Wybierz użytkownika platformy Azure mającego licencję na korzystanie z usługi Intune, a następnie wybierz pozycję **Wybierz**.

    ![Zrzut ekranu wybranego użytkownika](media/enrollment-autopilot/select-user.png)

3. W polu **Nazwa przyjazna dla użytkownika** wpisz przyjazną nazwę lub po prostu zaakceptuj wartość domyślną. Ten ciąg to przyjazna nazwa, która jest wyświetlana podczas logowania użytkownika w trakcie instalowania systemu Windows.

    ![Zrzut ekranu przedstawiający przyjazną nazwę](media/enrollment-autopilot/friendly-name.png)

4. Wybierz przycisk **OK**.


## <a name="delete-autopilot-devices"></a>Usuwanie urządzeń rozwiązania Autopilot

Możesz usuwać urządzenia rozwiązania Windows Autopilot, które nie zostały zarejestrowane.

1. Jeśli urządzenia są zarejestrowane w usłudze Intune, musisz najpierw [usunąć je z portalu usługi Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia**.

3. W obszarze **urządzeń rozwiązania Autopilot z systemem Windows** wybierz urządzenia do usunięcia, a następnie wybierz pozycję **Usuń**.

4. Potwierdź usunięcie, wybierając pozycję **Tak**. Proces usuwania może potrwać kilka minut.

## <a name="using-autopilot-in-other-portals"></a>Używanie rozwiązania Autopilot w innych portalach
Jeśli nie interesuje Cię zarządzanie urządzeniami przenośnymi, rozwiązania Autopilot możesz używać w innych portalach. Używanie innych portali jest opcjonalne. My zalecamy, aby do zarządzania wdrożeniami rozwiązania Autopilot używać samej usługi Intune. Gdy używasz usługi Intune i innego portalu, usługa Intune nie może:  

- Wyświetlać zmian w profilach utworzonych w usłudze Intune, ale edytowanych w innym portalu.
- Synchronizować profilów utworzonych w innym portalu.
- Wyświetlać zmian w przypisaniach profilów wykonanych w innym portalu.
- Synchronizować przypisań profilów wykonanych w innym portalu.
- Wyświetlać zmian wprowadzonych na liście urządzeń w innym portalu

## <a name="windows-autopilot-for-existing-devices"></a>Rozwiązanie Windows Autopilot dla istniejących urządzeń

Możliwe jest grupowanie urządzeń z systemem Windows według identyfikatora korelatora podczas rejestrowania przy użyciu [rozwiązania Autopilot dla istniejących urządzeń](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) za pośrednictwem programu Configuration Manager. Identyfikator korelatora jest parametrem pliku konfiguracji rozwiązania Autopilot. [Atrybut enrollmentProfileName urządzenia w usłudze Azure AD ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) zostanie automatycznie ustawiony na wartość „OfflineAutopilotprofile-\<identyfikator korelatora\>”. Dzięki temu można tworzyć dowolne grupy dynamiczne usługi Azure AD na podstawie identyfikatora korelatora przy użyciu atrybutu enrollmentprofileName.

>[!WARNING] 
> Ponieważ identyfikator korelatora nie jest wstępnie umieszczony w usłudze Intune, urządzenie może zgłosić dowolny identyfikator korelatora. Jeśli użytkownik utworzy identyfikator korelatora pasujący do nazwy profilu rozwiązania Autopilot lub profilu programu DEP firmy Apple, urządzenie zostanie dodane do dowolnej dynamicznej grupy urządzeń usługi Azure AD na podstawie atrybutu enrollmentProfileName. Aby uniknąć tego konfliktu:
> - Zawsze twórz reguły grupy dynamicznej wymagające dopasowania względem *całej* wartości atrybutu enrollmentProfileName.
> - Nigdy nie nadawaj profilom rozwiązania Autopilot lub programu DEP firmy Apple nazw rozpoczynających się od „OfflineAutopilotprofile-”.

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu rozwiązania Windows Autopilot dla zarejestrowanych urządzeń z systemem Windows 10 dowiedz się, jak zarządzać tymi urządzeniami. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](https://docs.microsoft.com/intune/device-management)
