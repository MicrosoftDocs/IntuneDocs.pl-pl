---
title: Rejestrowanie urządzeń za pomocą rozwiązania Windows AutoPilot
titleSuffix: Microsoft Intune
description: Dowiedz się, jak zarejestrować urządzenia z systemem Windows 10 za pomocą rozwiązania Windows AutoPilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: c96f211f18168c8ae55f0ca2391c6c140caef649
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138724"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Rejestrowanie urządzeń za pomocą rozwiązania Windows AutoPilot
Rozwiązanie Windows AutoPilot upraszcza aprowizowanie urządzeń. Tworzenie i konserwacja niestandardowych obrazów systemów operacyjnych zajmuje dużo czasu. Trzeba również poświęcić czas na stosowanie tych niestandardowych obrazów systemów operacyjnych na nowych urządzeniach w celu przygotowania ich do użycia przed przekazaniem użytkownikom końcowym. Dzięki usłudze Microsoft Intune i rozwiązaniu AutoPilot można przekazać nowe urządzenia użytkownikom końcowym bez konieczności tworzenia, konserwowania i stosowania niestandardowych obrazów systemów operacyjnych do urządzeń. Jeśli do zarządzania urządzeniami z rozwiązaniem AutoPilot używasz usługi Intune, możesz zarządzać zasadami, profilami, aplikacjami i nie tylko po ich zarejestrowaniu. Aby zapoznać się z korzyściami, scenariuszami i wymaganiami wstępnymi, zobacz [Overview of Windows AutoPilot (Przegląd rozwiązania Windows AutoPilot)](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Wymagania wstępne
- [Włączona funkcja automatycznej rejestracji w systemie Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Subskrypcja usługi Azure Active Directory — wersja Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Dodawanie urządzeń

Urządzenia rozwiązania AutoPilot z systemem Windows można dodawać przez zaimportowanie pliku CSV z odpowiednimi informacjami.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Urządzenia**  >  **Import**.

    ![Zrzut ekranu przedstawiający urządzenia rozwiązania AutoPilot z systemem Windows](media/enrollment-autopilot/autopilot-import-device.png)

2. W obszarze **Dodawanie urządzeń rozwiązania AutoPilot z systemem Windows** przejdź do pliku CSV z informacjami o urządzeniach, które chcesz dodać. Plik powinien zawierać numery seryjne, identyfikatory produktów systemu Windows, skróty sprzętu i opcjonalnie identyfikatory zamówień urządzeń.

    ![Zrzut ekranu przedstawiający dodawanie urządzeń rozwiązania AutoPilot z systemem Windows](media/enrollment-autopilot/autopilot-import-device2.png)

3. Wybierz pozycję **Importuj**, aby rozpocząć importowanie informacji o urządzeniu. Importowanie może potrwać kilka minut.

4. Po ukończeniu importowania wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Windows AutoPilot**  >  **Urządzenia**  >  **Synchronizacja**. Zostanie wyświetlony komunikat o synchronizacji w toku. Proces może potrwać kilka minut, w zależności od tego, ile urządzeń jest synchronizowanych.

5. Odśwież widok, aby zobaczyć nowe urządzenia.

## <a name="create-an-autopilot-device-group"></a>Tworzenie grupy urządzeń rozwiązania AutoPilot

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Grupy**.
2. W bloku **Grupa**:
    1. Dla ustawienia **Typ grupy** wybierz pozycję **Zabezpieczenia**.
    2. Wpisz odpowiedni tekst w polach **Nazwa grupy** i **Opis grupy**.
    3. Dla ustawienia **Typ członkostwa** wybierz pozycję **Przypisane** lub **Urządzenie dynamiczne**.
3. Jeśli w poprzednim kroku wybrano pozycję **Przypisane** dla ustawienia **Typ członkostwa**, to w bloku **Grupa** wybierz pozycję **Członkowie** i dodaj urządzenia rozwiązania AutoPilot do grupy.
    Urządzenia rozwiązania AutoPilot, które nie zostały jeszcze zarejestrowane, to urządzenia, których nazwa jest taka sama jak ich numer seryjny.
4. Jeśli powyżej wybrano pozycję **Urządzenie dynamiczne** dla ustawienia **Typ członkostwa**, to w bloku **Grupa** wybierz pozycję **Dynamiczne urządzenia członkowskie** i wpisz dowolny poniższy kod w polu **Reguła zaawansowana**.
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania AutoPilot, wpisz `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania AutoPilot z określonym identyfikatorem zamówienia, wpisz: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania AutoPilot z określonym identyfikatorem zamówienia zakupu, wpisz: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po dodaniu kodu w polu **Reguła zaawansowana** wybierz pozycję **Zapisz**.
5. Wybierz pozycję **Utwórz**.



## <a name="create-an-autopilot-deployment-profile"></a>Tworzenie profilu wdrażania rozwiązania AutoPilot
Profile wdrażania rozwiązania AutoPilot służą do konfigurowania urządzeń z rozwiązaniem AutoPilot.
1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Profile wdrażania**  >  **Utwórz profil**.
2. Podaj **nazwę** i opcjonalny **opis**.
3. Dla ustawienia **Tryb wdrażania** wybierz jedną z tych dwóch opcji:
    - **Sterowane przez użytkownika**: urządzenia z tym profilem są skojarzone z użytkownikiem rejestrującym urządzenie. Poświadczenia użytkownika są wymagane do aprowizacji urządzenia.
    - **Wdrażanie samodzielne (wersja zapoznawcza)**: (system Windows 10 Insider Preview w kompilacji 17672 lub nowszy) urządzenia z tym profilem nie są skojarzone z użytkownikiem rejestrującym urządzenie. Poświadczenia użytkownika nie są wymagane do aprowizacji urządzenia.
4. W polu **Dołącz do usługi Azure AD jako** wybierz pozycję **Dołączono do usługi Azure AD**.
5. Wybierz pozycję **Środowisko gotowe do użycia (OOBE, Out-of-box experience)**, skonfiguruj poniższe opcje, a następnie wybierz przycisk **Zapisz**:
    - **Język (region)***: wybierz język do użycia dla urządzenia. Ta opcja jest dostępna tylko w przypadku wybrania pozycji **Wdrażanie samodzielne** dla ustawienia **Tryb wdrażania**.
    - **Automatycznie skonfiguruj klawiaturę***: jeśli wybrano pozycję **Język (region)**, pomiń stronę wyboru klawiatury. Ta opcja jest dostępna tylko w przypadku wybrania pozycji **Wdrażanie samodzielne** dla ustawienia **Tryb wdrażania**.
    - **Umowa licencyjna użytkownika oprogramowania (EULA, End User License Agreement)**: (system Windows 10 w wersji 1709 lub nowszej) określ, czy umowa licencyjna użytkownika oprogramowania ma być pokazywana użytkownikom.
    - **Ustawienia prywatności**: określ, czy ustawienia prywatności mają być pokazywane użytkownikom.
    - **Typ konta użytkownika**: wybierz typ konta użytkownika (**Administrator** lub **Standardowe** konto użytkownika). 

6. Wybierz pozycję **Utwórz**, aby utworzyć profil. Profil wdrażania rozwiązania AutoPilot jest teraz dostępny do przypisania do urządzeń.

* Pola **Język (region)** i **Automatycznie skonfiguruj klawiaturę** są dostępne tylko w przypadku wybrania pozycji **Wdrażanie samodzielne (wersja zapoznawcza)** dla ustawienia **Tryb wdrażania** (system Windows 10 Insider Preview w kompilacji 17672 lub nowszy).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Przypisywanie profilu wdrażania rozwiązania AutoPilot do grupy urządzeń

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Profile wdrażania**, a następnie wybierz profil.
2. W bloku określonego profilu wybierz pozycję **Przypisania**. 
3. Wybierz pozycję **Wybierz grupy**, a następnie w bloku **Wybieranie grup** wybierz grupy, do których chcesz przypisać profil, a następnie wybierz pozycję **Wybierz**.

## <a name="edit-an-autopilot-deployment-profile"></a>Edytowanie profilu wdrażania rozwiązania AutoPilot
Po utworzeniu profilu wdrażania rozwiązania AutoPilot możesz edytować niektóre jego części.   

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia**.
2. W obszarze **Rejestracja w systemie Windows** w sekcji **Windows AutoPilot** wybierz pozycję **Profile wdrażania**.
3. Wybierz profil, który chcesz edytować.
4. Kliknij pozycję **Właściwości** po lewej stronie, aby zmienić nazwę lub opis profilu wdrażania. Po wprowadzeniu zmian kliknij pozycję **Zapisz**.
5. Kliknij pozycję **Ustawienia**, aby wprowadzić zmiany do ustawień trybu OOBE. Po wprowadzeniu zmian kliknij pozycję **Zapisz**.

> [!NOTE]
> Zmiany w profilu są stosowane do urządzeń przypisanych do tego profilu. Zaktualizowany profil nie zostanie jednak zastosowany do urządzenia już zarejestrowanego w usłudze Intune, dopóki nie zostanie zresetowane i ponownie zarejestrowane.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alerty dla urządzeń nieprzypisanych w programie Windows AutoPilot <!-- 163236 -->
Możesz wyświetlić alert, aby sprawdzić, ile urządzeń z programu AutoPilot nie ma przypisanych profili wdrażania programu AutoPilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń w programie Windows AutoPilot.

Aby wyświetlić alerty dotyczące nieprzypisanych urządzeń, w [usłudze Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Przegląd**  >  **Nieprzypisane urządzenia**.  

## <a name="delete-autopilot-devices"></a>Usuwanie urządzeń z rozwiązaniem AutoPilot

Możesz usuwać urządzenia rozwiązania Windows AutoPilot, które nie zostały zarejestrowane.

1. Jeśli urządzenia są zarejestrowane w usłudze Intune, musisz najpierw [usunąć je z portalu usługi Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia**.

3. W obszarze **urządzeń rozwiązania AutoPilot z systemem Windows** wybierz urządzenia do usunięcia, a następnie wybierz pozycję **Usuń**.

4. Potwierdź usunięcie, wybierając pozycję **Tak**. Proces usuwania może potrwać kilka minut.

## <a name="using-autopilot-in-other-portals"></a>Używanie rozwiązania AutoPilot w innych portalach
Jeśli nie interesuje Cię zarządzanie urządzeniami przenośnymi, rozwiązania AutoPilot możesz używać na przykład w połączeniu ze sklepem Microsoft Store dla Firm. Używanie innych portali jest opcjonalne. My zalecamy, aby do zarządzania wdrożeniami rozwiązania AutoPilot używać samej usługi Intune. Jeśli używasz usługi Intune i innego portalu, usługa Intune nie może:
- Wyświetlać zmian w profilach utworzonych w usłudze Intune, ale edytowanych w innym portalu.
- Synchronizować profilów utworzonych w innym portalu.
- Wyświetlać zmian w przypisaniach profilów wykonanych w innym portalu.
- Synchronizować przypisań profilów wykonanych w innym portalu.
- Wyświetlać zmian wprowadzonych na liście urządzeń w innym portalu

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu rozwiązania Windows AutoPilot dla zarejestrowanych urządzeń z systemem Windows 10 dowiedz się, jak zarządzać tymi urządzeniami. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](https://docs.microsoft.com/intune/device-management)
