---
title: Rejestrowanie urządzeń za pomocą rozwiązania Windows Autopilot
titleSuffix: Microsoft Intune
description: Dowiedz się, jak zarejestrować urządzenia z systemem Windows 10 za pomocą rozwiązania Windows Autopilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6df8922f9f7252c493b4a2119814c0001245fa8b
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550007"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Rejestrowanie urządzeń z systemem Windows w usłudze Intune za pomocą rozwiązania Windows Autopilot  
Rozwiązanie Windows Autopilot upraszcza rejestrowanie urządzeń w usłudze Intune. Tworzenie i konserwacja niestandardowych obrazów systemów operacyjnych zajmuje dużo czasu. Trzeba również poświęcić czas na stosowanie tych niestandardowych obrazów systemów operacyjnych na nowych urządzeniach w celu przygotowania ich do użycia przed przekazaniem użytkownikom końcowym. Dzięki usłudze Microsoft Intune i rozwiązaniu Autopilot można przekazać nowe urządzenia użytkownikom końcowym bez konieczności tworzenia, konserwowania i stosowania niestandardowych obrazów systemów operacyjnych do urządzeń. Jeśli do zarządzania urządzeniami z rozwiązaniem Autopilot używasz usługi Intune, możesz zarządzać zasadami, profilami, aplikacjami i nie tylko po ich zarejestrowaniu. Aby zapoznać się z korzyściami, scenariuszami i wymaganiami wstępnymi, zobacz [Overview of Windows Autopilot (Przegląd rozwiązania Windows Autopilot)](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

Istnieją cztery typy wdrażania w rozwiązaniu Autopilot: [Tryb samodzielnego wdrażania](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) dla kiosków, znakowania cyfrowego lub udostępnionego urządzenia, [White Glove](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) umożliwiający partnerom lub personelowi działu IT wstępną aprowizację komputera z systemem Windows 10, aby był w pełni skonfigurowany i gotowy do użytku w firmie, rozwiązanie [Autopilot dla istniejących urządzeń](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) umożliwiające łatwe wdrażanie najnowszej wersji systemu Windows 10 na istniejących urządzeniach, a także [tryb sterowany przez użytkownika](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) dla tradycyjnych użytkowników. 


## <a name="prerequisites"></a>Wymagania wstępne
- [Subskrypcja usługi Intune](licenses.md)
- [Włączona funkcja automatycznej rejestracji w systemie Windows](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Subskrypcja usługi Azure Active Directory — wersja Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Jak uzyskać plik CSV do zaimportowania w usłudze Intune

Aby uzyskać więcej informacji, zobacz artykuł objaśniający polecenie cmdlet programu PowerShell.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Dodawanie urządzeń

Urządzenia rozwiązania Autopilot z systemem Windows można dodawać przez zaimportowanie pliku CSV z odpowiednimi informacjami.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Urządzenia**  >  **Import**.

    ![Zrzut ekranu przedstawiający urządzenia rozwiązania Autopilot z systemem Windows](media/enrollment-autopilot/autopilot-import-device.png)

2. W obszarze **Dodawanie urządzeń rozwiązania AutoPilot z systemem Windows** przejdź do pliku CSV z informacjami o urządzeniach, które chcesz dodać. Plik CSV powinien zawierać listę numerów seryjnych, opcjonalnych identyfikatorów produktów systemu Windows, skrótów sprzętu, opcjonalnie tagów grup urządzeń i opcjonalnie przypisanego użytkownika. Lista możesz mieć maksymalnie 500 wierszy. Użyj poniższego formatu nagłówka i wiersza:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

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
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot, wpisz: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Pole tagu grupy usługi Intune jest mapowane na atrybut OrderID urządzenia w usłudze Azure AD. Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym tagiem grupy (OrderID), trzeba wpisać: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia zakupu, wpisz: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po dodaniu kodu w polu **Reguła zaawansowana** wybierz pozycję **Zapisz**.
5. Wybierz pozycję **Utwórz**.  

## <a name="create-an-autopilot-deployment-profile"></a>Tworzenie profilu wdrażania rozwiązania Autopilot
Profile wdrażania rozwiązania Autopilot służą do konfigurowania urządzeń z rozwiązaniem Autopilot.
1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Profile wdrażania**  >  **Utwórz profil**.
2. Na stronie **Podstawowe** wypełnij pole **Nazwa** i opcjonalne pole **Opis**.

    ![Zrzut ekranu strony Podstawowe](media/enrollment-autopilot/create-profile-basics.png)

3. Jeśli chcesz, aby wszystkie urządzenia w przypisanych grupach dokonywały automatycznej konwersji do rozwiązania Autopilot, ustaw opcję **Konwertuj wszystkie wybrane urządzenia na potrzeby rozwiązania Autopilot** na wartość **Tak**. Wszystkie urządzenia bez rozwiązania Autopilot w przypisanych grupach będą rejestrować się za pomocą usługi wdrażania rozwiązania Autopilot. Przetwarzanie rejestracji może potrwać do 48 godzin. Jeśli urządzenie nie zostało zarejestrowane i je zresetowano, rozwiązanie Autopilot przeprowadzi jego rejestrację. Po zarejestrowaniu urządzenia w ten sposób wyłączenie tej opcji lub usunięcie przypisania profilu nie spowoduje usunięcia urządzenia z usługi wdrażania rozwiązania Autopilot. Zamiast tego należy [bezpośrednio usunąć urządzenie](enrollment-autopilot.md#delete-autopilot-devices).
4. Wybierz pozycję **Dalej**.
5. Na stronie **Środowisko gotowe do użycia (OOBE, Out-of-box experience)** dla pozycji **Tryb wdrożenia** wybierz jedną z następujących dwóch opcji:
    - **Sterowane przez użytkownika**: Urządzenia z tym profilem są skojarzone z użytkownikiem rejestrującym urządzenie. Poświadczenia użytkownika są wymagane do rejestracji urządzenia.
    - **Wdrażanie samodzielne (wersja zapoznawcza)** : (wymaga systemu Windows 10 w wersji 1809 lub nowszej) urządzenia z tym profilem nie są skojarzone z użytkownikiem rejestrującym urządzenie. Poświadczenia użytkownika nie są wymagane do zarejestrowania urządzenia.

    ![Zrzut ekranu strony OOBE](media/enrollment-autopilot/create-profile-outofbox.png)

6. W polu **Dołącz do usługi Azure AD jako** wybierz pozycję **Dołączono do usługi Azure AD**.
7. Skonfiguruj następujące opcje:
    - **Umowa licencyjna użytkownika oprogramowania (EULA)** : (system Windows 10 w wersji 1709 lub nowszej) wybierz, jeśli chcesz, aby umowa licencyjna użytkownika oprogramowania była pokazywana użytkownikom.
    - **Ustawienia prywatności**: wybierz, jeśli chcesz, aby ustawienia prywatności były pokazywane użytkownikom.
    >[!IMPORTANT]
    >Wartość domyślna dla ustawienia Dane diagnostyczne różni się w zależności od wersji systemu Windows. W przypadku urządzeń z systemem Windows 10 w wersji 1903 jest ustawiona wartość domyślna Pełne podczas korzystania z gotowego środowiska obsługi. Aby uzyskać więcej informacji, zobacz [Dane diagnostyczne systemu Windows](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) <br>
    
    - **Ukryj zmianę opcji konta (wymaga systemu Windows 10 w wersji 1809 lub nowszej)** : wybierz pozycję **Ukryj**, aby zapobiec wyświetlaniu zmian opcji konta na stronach logowania i błędów domeny firmy. Ta opcja wymaga [skonfigurowania znakowania firmowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Typ konta użytkownika**: wybierz typ konta użytkownika (**Administrator** lub **Standardowe** konto użytkownika).
    - **Zezwalaj na tryb OOBE White Glove** (wymaga systemu Windows 10 w wersji 1903 lub nowszej; [dodatkowe wymagania fizyczne](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): wybierz pozycję **Tak**, aby zezwolić na obsługę trybu White Glove.
    - **Zastosuj szablon nazwy urządzenia** (wymaga systemu Windows 10 w wersji 1809 lub nowszej): wybierz pozycję **Tak**, aby utworzyć szablon do stosowania podczas określania nazwy urządzenia w trakcie rejestracji. Nazwy mogą mieć co najwyżej 15 znaków i zawierać litery, cyfry i łączniki. Nazwy nie mogą zawierać samych cyfr. Użyj [makro %SERIAL%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp), aby dodać numer seryjny specyficzny dla sprzętu. Ewentualnie możesz zastosować [makro %RAND:x%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp), aby dodać losowy ciąg cyfr, gdzie x odpowiada liczbie cyfr do dodania. 
    - **Język (region)** \*: wybierz język do użycia dla urządzenia. Ta opcja jest dostępna tylko w przypadku wybrania pozycji **Wdrażanie samodzielne** dla ustawienia **Tryb wdrażania**.
    - **Automatycznie skonfiguruj klawiaturę**\*: jeśli wybrano pozycję **Język (region)** , wybierz pozycję **Tak**, aby pominąć stronę wyboru klawiatury. Ta opcja jest dostępna tylko w przypadku wybrania pozycji **Wdrażanie samodzielne** dla ustawienia **Tryb wdrażania**.
8. Wybierz pozycję **Dalej**.
9. Na stronie **Tagi zakresu** opcjonalnie dodaj tagi zakresu, które chcesz zastosować do tego profilu. Więcej informacji na temat tagów zakresu można znaleźć w artykule [Use role-based access control and scope tags for distributed IT](scope-tags.md) (Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej).
10. Wybierz pozycję **Dalej**.
11. Na stronie **Przypisania** wybierz opcję **Wybrane grupy** dla ustawienia **Przypisz do**.

    ![Zrzut ekranu strony przypisań](media/enrollment-autopilot/create-profile-assignments.png)

12. Kliknij pozycję **Wybierz grupy do uwzględnienia** i wskaż grupy, które chcesz uwzględnić w tym profilu.
13. Jeśli chcesz wykluczyć jakieś grupy, kliknij pozycję **Wybierz grupy do wykluczenia** i wskaż grupy, które chcesz wykluczyć.
14. Wybierz pozycję **Dalej**.
15. Na stronie **Przeglądanie + tworzenie** wybierz pozycję **Utwórz**, aby utworzyć profil.

    ![Zrzut ekranu strony przeglądania](media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Usługa Intune będzie okresowo sprawdzać, czy w przypisanych grupach znajdują się nowe urządzenia, a następnie rozpoczynać proces przypisywania profili do tych urządzeń. Ten proces może potrwać kilka minut. Przed wdrożeniem urządzenia upewnij się, że ten proces został zakończony.  Stan profilu powinien się zmienić z „Nieprzypisane” na „Przypisywanie”, a następnie na „Przypisano” w obszarze **Rejestrowanie urządzeń** > **Rejestracja urządzeń z systemem Windows** > **Urządzenia**.

## <a name="edit-an-autopilot-deployment-profile"></a>Edytowanie profilu wdrażania rozwiązania Autopilot
Po utworzeniu profilu wdrażania rozwiązania Autopilot możesz edytować niektóre jego części.   

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia**.
2. W obszarze **Rejestracja w systemie Windows** w sekcji **Windows Autopilot** wybierz pozycję **Profile wdrażania**.
3. Wybierz profil, który chcesz edytować.
4. Kliknij pozycję **Właściwości** po lewej stronie, aby zmienić nazwę lub opis profilu wdrażania. Po wprowadzeniu zmian kliknij pozycję **Zapisz**.
5. Kliknij pozycję **Ustawienia**, aby wprowadzić zmiany do ustawień trybu OOBE. Po wprowadzeniu zmian kliknij pozycję **Zapisz**.

> [!NOTE]
> Zmiany w profilu są stosowane do urządzeń przypisanych do tego profilu. Zaktualizowany profil nie zostanie jednak zastosowany do urządzenia już zarejestrowanego w usłudze Intune, dopóki nie zostanie zresetowane i ponownie zarejestrowane.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alerty dla urządzeń nieprzypisanych w rozwiązaniu Windows Autopilot  <!-- 163236 -->  

Alerty pokażą, ile urządzeń rozwiązania Autopilot nie ma profilów wdrażania rozwiązania Autopilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń rozwiązania Windows Autopilot.


Aby wyświetlić alerty dotyczące nieprzypisanych urządzeń, w [usłudze Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Przegląd**  >  **Nieprzypisane urządzenia**.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Przypisywanie użytkownika do określonego urządzenia rozwiązania Autopilot

Możesz przypisać użytkownika do określonego urządzenia rozwiązania Autopilot. To przypisanie wstępnie wypełnia dane użytkownika z usługi Azure Active Directory na [oznaczonej marką firmy](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) stronie logowania podczas instalowania systemu Windows. Pozwala ono ustawić też niestandardową nazwę powitania. Nie powoduje to wstępnego wypełnienia ani modyfikacji logowania w systemie Windows. W ten sposób można przypisać tylko licencjonowanych użytkowników usługi Intune.

Wymagania wstępne: Skonfigurowany Portal firmy usługi Azure Active Directory oraz system Windows 10 w wersji 1809 lub nowszej.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia** > wybierz urządzenie > **Przypisz użytkownika**.

    ![Zrzut ekranu przypisywania użytkownika](media/enrollment-autopilot/assign-user.png)

2. Wybierz użytkownika platformy Azure mającego licencję na korzystanie z usługi Intune, a następnie wybierz pozycję **Wybierz**.

    ![Zrzut ekranu wybranego użytkownika](media/enrollment-autopilot/select-user.png)

3. W polu **Nazwa przyjazna dla użytkownika** wpisz przyjazną nazwę lub po prostu zaakceptuj wartość domyślną. Ten ciąg to przyjazna nazwa, która jest wyświetlana podczas logowania użytkownika w trakcie instalowania systemu Windows.

    ![Zrzut ekranu przedstawiający przyjazną nazwę](media/enrollment-autopilot/friendly-name.png)

4. Wybierz przycisk **OK**.


## <a name="delete-autopilot-devices"></a>Usuwanie urządzeń rozwiązania Autopilot

Możesz usuwać urządzenia rozwiązania Windows Autopilot, które nie zostały zarejestrowane w usłudze Intune:

- Usuń urządzenia z rozwiązania Windows Autopilot, wybierając pozycje **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia**. Wybierz urządzenia, które chcesz usunąć, a następnie wybierz pozycję **Usuń**. Usuwanie urządzenia z rozwiązania Windows Autopilot może potrwać kilka minut.

Całkowite usunięcie urządzenia z dzierżawy wymaga usunięcia rekordów urządzenia z usług Intune i Azure Active Directory oraz rozwiązania Windows Autopilot. Wszystko to można zrobić z usługi Intune:

1. Jeśli urządzenia są zarejestrowane w usłudze Intune, musisz najpierw [usunąć je z bloku wszystkich urządzeń w usłudze Intune](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Usuń urządzenia z urządzeń usługi Azure Active Directory, wybierając pozycje **Urządzenia** > **Urządzenia usługi Azure AD**.

3. Usuń urządzenia z rozwiązania Windows Autopilot, wybierając pozycje **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia**. Wybierz urządzenia, które chcesz usunąć, a następnie wybierz pozycję **Usuń**. Usuwanie urządzenia z rozwiązania Windows Autopilot może potrwać kilka minut.

## <a name="using-autopilot-in-other-portals"></a>Używanie rozwiązania Autopilot w innych portalach
Jeśli nie interesuje Cię zarządzanie urządzeniami przenośnymi, rozwiązania Autopilot możesz używać w innych portalach. Używanie innych portali jest opcjonalne. My zalecamy, aby do zarządzania wdrożeniami rozwiązania Autopilot używać samej usługi Intune. Gdy używasz usługi Intune i innego portalu, usługa Intune nie może:  

- Wyświetlać zmian w profilach utworzonych w usłudze Intune, ale edytowanych w innym portalu.
- Synchronizować profilów utworzonych w innym portalu.
- Wyświetlać zmian w przypisaniach profilów wykonanych w innym portalu.
- Synchronizować przypisań profilów wykonanych w innym portalu.
- Wyświetlać zmian wprowadzonych na liście urządzeń w innym portalu

## <a name="windows-autopilot-for-existing-devices"></a>Rozwiązanie Windows Autopilot dla istniejących urządzeń

Możliwe jest grupowanie urządzeń z systemem Windows według identyfikatora korelatora podczas rejestrowania przy użyciu [rozwiązania Autopilot dla istniejących urządzeń](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) za pośrednictwem programu Configuration Manager. Identyfikator korelatora jest parametrem pliku konfiguracji rozwiązania Autopilot. [Atrybut enrollmentProfileName urządzenia w usłudze Azure AD ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) zostanie automatycznie ustawiony na wartość „OfflineAutopilotprofile-\<identyfikator korelatora\>”. Dzięki temu można tworzyć dowolne grupy dynamiczne usługi Azure AD na podstawie identyfikatora korelatora przy użyciu atrybutu enrollmentprofileName.

>[!WARNING] 
> Ponieważ identyfikator korelatora nie jest wstępnie umieszczony w usłudze Intune, urządzenie może zgłosić dowolny identyfikator korelatora. Jeśli użytkownik utworzy identyfikator korelatora pasujący do nazwy profilu rozwiązania Autopilot lub profilu programu DEP firmy Apple, urządzenie zostanie dodane do dowolnej dynamicznej grupy urządzeń usługi Azure AD na podstawie atrybutu enrollmentProfileName. Aby uniknąć tego konfliktu:
> - Zawsze twórz reguły grupy dynamicznej wymagające dopasowania względem *całej* wartości atrybutu enrollmentProfileName.
> - Nigdy nie nadawaj profilom rozwiązania Autopilot lub programu DEP firmy Apple nazw rozpoczynających się od „OfflineAutopilotprofile-”.

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu rozwiązania Windows Autopilot dla zarejestrowanych urządzeń z systemem Windows 10 dowiedz się, jak zarządzać tymi urządzeniami. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](https://docs.microsoft.com/intune/device-management)
