---
title: Przewodnik — Tworzenie szablonu administracyjnego w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W tym samouczku (przewodniku) za pomocą usługi Microsoft Intune skonfigurujemy szablony ADMX pakietu Office, systemu Windows i programu Microsoft Edge na urządzeniach z systemem Windows 10 i nowszych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a96f291203e1513ab89196b26a7802856f90e048
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77688093"
---
# <a name="tutorial-use-the-cloud-to-configure-group-policy-on-windows-10-devices-with-admx-templates-and-microsoft-intune"></a>Samouczek: Use the cloud to configure group policy on Windows 10 devices with ADMX templates and Microsoft Intune (Używanie chmury do konfigurowania zasad grupy na urządzeniach z systemem Windows 10 za pomocą szablonów ADMX i usługi Microsoft Intune)

> [!NOTE]
> Ten samouczek powstał na potrzeby warsztatów technicznych na konferencję Microsoft Ignite. Ma więcej wymagań wstępnych niż typowe samouczki, ponieważ porównuje używanie i konfigurowanie zasad ADMX w usłudze Intune i w środowisku lokalnym.

Szablony administracyjne zasad grupy, nazywane także szablonami ADMX, obejmują ustawienia, które można skonfigurować na urządzeniach z systemem Windows 10, w tym na komputerach. Ustawienia szablonu ADMX są dostępne dla różnych usług. Te ustawienia są używane przez dostawców zarządzania urządzeniami mobilnymi (MDM), takich jak Microsoft Intune. Umożliwiają na przykład włączanie pomysłów dotyczących projektów w programie PowerPoint, ustawianie strony głównej w przeglądarce Microsoft Edge, blokowanie kontrolek ActiveX w programie Internet Explorer itd.

Szablony ADMX są dostępne dla następujących usług:

- **Microsoft Edge**: Pobierz z witryny [pliku zasad przeglądarki Microsoft Edge](https://www.microsoftedgeinsider.com/en-us/enterprise).
- **Office**: Pobierz z witryny [Office 365 ProPlus, Office 2019 i Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).
- **Windows**: Wbudowane w systemie operacyjnym Windows 10.

Aby uzyskać więcej informacji na temat zasad ADMX, zobacz [Understanding ADMX-backed policies](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) (Omówienie zasad opartych na formacie ADMX).

W usłudze Microsoft Intune te szablony są wbudowane i dostępne jako profile **Szablony administracyjne**. W tym profilu skonfigurujesz ustawienia, które mają zostać uwzględnione, a następnie „przypiszesz” ten profil do swoich urządzeń.

W tym samouczku wykonasz następujące czynności:

> [!div class="checklist"]
> * Wprowadzenie do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
> * Utworzenie grup użytkowników i grup urządzeń.
> * Porównanie ustawień w usłudze Intune z ustawieniami ADMX w środowisku lokalnym.
> * Utworzenie różnych szablonów administracyjnych i skonfigurowanie ustawień przeznaczonych dla różnych grup.

W ramach tego laboratorium zdobędziesz umiejętności umożliwiające rozpoczęcie zarządzania użytkownikami oraz wdrażania szablonów administracyjnych przy użyciu usługi Intune i platformy Microsoft 365.

Ta funkcja ma zastosowanie do:

- Windows 10 w wersji 1703 i nowszych

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja platformy Microsoft 365 E3 lub E5 obejmująca usługi Intune i Azure Active Directory (AD) — wersja Premium. Jeśli nie masz subskrypcji E3 lub E5, [wypróbuj ją bezpłatnie](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365?view=o365-worldwide).

  Aby uzyskać więcej informacji na temat zawartości różnych licencji platformy Microsoft 365, zobacz [Przekształcanie przedsiębiorstwa dzięki platformie Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

- Usługa Microsoft Intune jest skonfigurowana jako **urząd zarządzania urządzeniami mobilnymi usługi Intune**. Aby uzyskać więcej informacji, zobacz [Ustawianie urzędu zarządzania urządzeniami mobilnymi](../fundamentals/mdm-authority-set.md).

  > [!div class="mx-imgBorder"]
  > ![Ustawianie urzędu zarządzania urządzeniami mobilnymi na usługę Microsoft Intune w stanie dzierżawy](./media/tutorial-walkthrough-administrative-templates/tenant-status.png)

- Na lokalnym kontrolerze domeny usługi Active Directory:

  1. Skopiuj następujące szablony pakietu Office i programu Microsoft Edge do [magazynu centralnego (folder SYSVOL)](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra):

      - [Szablony administracyjne pakietu Office](https://www.microsoft.com/download/details.aspx?id=49030)
      - [Szablony administracyjne przeglądarki Microsoft Edge > Plik zasad](https://www.microsoftedgeinsider.com/en-us/enterprise)

  2. Utwórz zasady grupy, aby wypychać te szablony do komputera administratora systemu Windows 10 Enterprise w tej samej domenie, w której znajduje się kontroler domeny. W tym samouczku:

      - Zasady grupy utworzone przez nas za pomocą tych szablonów noszą nazwę **OfficeandEdge**. Ta nazwa będzie widoczna na ilustracjach.
      - Używany przez nas komputer administratora systemu Windows 10 Enterprise jest nazywany **komputerem administratora**.

      W niektórych organizacjach administrator domeny ma dwa konta — typowe konto służbowe domeny oraz drugie konto administratora domeny używane tylko do wykonywania zadań administratora domeny, takich jak zasady grupy.

      Ten **komputer administratora** jest przeznaczony dla administratorów w celu logowania się przy użyciu konta administratora domeny oraz uzyskiwania dostępu do narzędzi opracowanych na potrzeby zarządzania zasadami grupy.

- Na tym **komputerze administratora**:

  - Zaloguj się przy użyciu konta administratora domeny.

  - Zainstaluj narzędzia **RSAT: Group Policy Management Tools**:

    1. Otwórz aplikację **Ustawienia** > **Aplikacje** > **Funkcje opcjonalne** > **Dodaj funkcję**.
    2. Wybierz pozycję **RSAT: Group Policy Management Tools** > **Zainstaluj**.

        Zaczekaj, aż system Windows zainstaluje funkcję. Po zakończeniu będzie ona widoczna w aplikacji **Narzędzia administracyjne systemu Windows**.

        > [!div class="mx-imgBorder"]
        > ![Aplikacje narzędzi administracyjnych systemu Windows, w tym aplikacja Zarządzanie zasadami grupy](./media/tutorial-walkthrough-administrative-templates/windows-administrative-tools-app.png)

  - Upewnij się, że masz dostęp do Internetu oraz uprawnienia administratora do subskrypcji platformy Microsoft 365, która obejmuje centrum administracyjne programu Endpoint Manager.

## <a name="open-the-endpoint-manager-admin-center"></a>Otwieranie centrum administracyjnego programu Endpoint Manager

1. Otwórz przeglądarkę internetową typu Chromium, na przykład Microsoft Edge w wersji 77 lub nowszej.
2. Przejdź do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) (https://devicemanagement.microsoft.com). Zaloguj się przy użyciu następującego konta:

    **Użytkownik**: Wprowadź konto administratora swojej subskrypcji dzierżawy platformy Microsoft 365.  
    **Hasło**: Wprowadź jego hasło.

To centrum administracyjne koncentruje się na zarządzaniu urządzeniami i obejmuje usługi platformy Azure, takie jak Azure AD i Intune. Być może nie widzisz marek **Azure Active Directory** i **Intune**, ale ich używasz.

Centrum administracyjne programu Endpoint Manager można również otworzyć z poziomu [centrum administracyjnego platformy Microsoft 365](https://admin.microsoft.com):

1. Przejdź do witryny [https://admin.microsoft.com](https://admin.microsoft.com).
2. Zaloguj się przy użyciu konta administratora swojej subskrypcji dzierżawy platformy Microsoft 365.
3. W obszarze **Centra administracyjne** wybierz pozycję **Wszystkie centra administracyjne** > **Endpoint Management**. Zostanie otwarte centrum administracyjne programu Endpoint Manager.

    > [!div class="mx-imgBorder"]
    > ![Wyświetlanie wszystkich centrów administracyjnych w centrum administracyjnym platformy Microsoft 365](./media/tutorial-walkthrough-administrative-templates/microsoft365-admin-centers.png)

## <a name="create-groups-and-add-users"></a>Tworzenie grup i dodawanie użytkowników

Zasady lokalne są stosowane w następującej kolejności: lokalne, witryna, domena i jednostka organizacyjna. W tej hierarchii zasady jednostki organizacyjnej zastępują zasady lokalne, zasady domeny zastępują zasady witryny itd.

W usłudze Intune zasady są stosowane do utworzonych użytkowników i grup. Nie ma żadnej hierarchii. Jeśli dwie zasady aktualizują to samo ustawienie, występuje konflikt. Jeśli istnieje konflikt między dwiema zasadami zgodności, stosowane są zasady najbardziej restrykcyjne. Jeśli istnieje konflikt między dwoma profilami konfiguracji, ustawienie nie jest stosowane. Aby uzyskać więcej informacji, zobacz [Typowe pytania, problemy i rozwiązania dotyczące zasad i profili urządzeń](device-profile-troubleshoot.md#if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied).

W następnych krokach utworzysz grupy zabezpieczeń i dodasz użytkowników do grup. Użytkownika można dodać do wielu grup. Jest rzeczą normalną, że użytkownicy mogą mieć po kilka urządzeń, na przykład Surface Pro do pracy i urządzenie przenośne z systemem Android do użytku osobistego. Jest też zrozumiałe, że uzyskują oni dostęp do zasobów organizacyjnych na wszystkich tych urządzeniach.

1. W centrum administracyjnym programu Endpoint Manager wybierz pozycję **Grupy** > **Nowa grupa**.

2. Podaj następujące ustawienia:

    - **Typ grupy**: Wybierz pozycję **Zabezpieczenia**.
    - **Nazwa grupy**: Wprowadź **Wszystkie urządzenia uczniów z systemem Windows 10**.
    - **Typ członkostwa**: Wybierz pozycję **Przypisane**.

3. Wybierz pozycję **Członkowie** i dodaj kilka urządzeń.

    Dodawanie urządzeń jest opcjonalne. Ma ono na celu przećwiczenie tworzenia grup i poznanie sposobu dodawania urządzeń. Jeśli korzystasz z tego samouczka w środowisku produkcyjnym, uważaj, co robisz.

4. Wybierz pozycję **Wybierz** > **Utwórz**, aby zapisać zmiany.

    Nie widzisz swojej grupy? Wybierz pozycję **Odśwież**.

5. Wybierz pozycję **Nowa grupa** i wprowadź następujące ustawienia:

    - **Typ grupy**: Wybierz pozycję **Zabezpieczenia**.
    - **Nazwa grupy**: Wprowadź **Wszystkie urządzenia z systemem Windows**.
    - **Typ członkostwa**: Wybierz pozycję **Urządzenie dynamiczne**.
    - **Dynamiczne urządzenia członkowskie**: Skonfiguruj zapytanie:

        - **Właściwość**: Wybierz pozycję **deviceOSType**.
        - **Operator**: Wybierz pozycję **Równa się**.
        - **Wartość**: Wprowadź **Windows**.

        1. Wybierz pozycję **Dodaj wyrażenie**. Wyrażenie jest wyświetlane w polu **Składnia reguł**:

            > [!div class="mx-imgBorder"]
            > ![Tworzenie zapytania dynamicznego i dodawanie wyrażenia w szablonie administracyjnym usługi Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/dynamic-group-query.png)

            Użytkownicy i urządzenia spełniający wprowadzone kryteria są automatycznie dodawani do grup dynamicznych. W tym przykładzie urządzenia są automatycznie dodawane do tej grupy, gdy systemem operacyjnym jest Windows. Jeśli korzystasz z tego samouczka w środowisku produkcyjnym, zachowaj ostrożność. Celem jest przećwiczenie tworzenia grup dynamicznych.

        2. Wybierz pozycję **Zapisz** > **Utwórz**, aby zapisać zmiany.

6. Utwórz grupę **Wszyscy nauczyciele** z następującymi ustawieniami:

    - **Typ grupy**: Wybierz pozycję **Zabezpieczenia**.
    - **Nazwa grupy**: Wprowadź **Wszyscy nauczyciele**.
    - **Typ członkostwa**: Wybierz pozycję **Użytkownik dynamiczny**.
    - **Dynamiczne elementy członkowskie użytkownika**: Skonfiguruj zapytanie:

      - **Właściwość**: Wybierz **dział**.
      - **Operator**: Wybierz pozycję **Równa się**.
      - **Wartość**: Wprowadź **Nauczyciele**.

        1. Wybierz pozycję **Dodaj wyrażenie**. Wyrażenie jest wyświetlane w polu **Składnia reguł**.

            Użytkownicy i urządzenia spełniający wprowadzone kryteria są automatycznie dodawani do grup dynamicznych. W tym przykładzie użytkownicy są automatycznie dodawani do tej grupy, gdy należą do działu Nauczyciele. Dział i inne właściwości można wprowadzić podczas dodawania użytkowników do organizacji. Jeśli korzystasz z tego samouczka w środowisku produkcyjnym, zachowaj ostrożność. Celem jest przećwiczenie tworzenia grup dynamicznych.

        2. Wybierz pozycję **Zapisz** > **Utwórz**, aby zapisać zmiany.

### <a name="talking-points"></a>Najważniejsze zagadnienia

- Grupy dynamiczne są funkcją w usłudze Azure AD — wersja Premium. Jeśli nie masz usługi Azure AD — wersja Premium, Twoja licencja pozwala na tworzenie tylko grup przypisanych. Aby uzyskać więcej informacji na temat grup dynamicznych, zobacz:

  - [Dynamic Group Membership in Azure Active Directory (Part 1)](https://blogs.technet.microsoft.com/pauljones/2017/08/28/dynamic-group-membership-in-azure-active-directory-part-1/) (Członkostwo w grupie dynamicznej w usłudze Azure Active Directory — część 1)
  - [Dynamic Group Membership in Azure Active Directory (Part 2)](https://blogs.technet.microsoft.com/pauljones/2017/08/29/dynamic-group-membership-in-azure-active-directory-part-2/) (Członkostwo w grupie dynamicznej w usłudze Azure Active Directory — część 2)

- Usługa Azure AD — wersja Premium zawiera inne usługi, które są często używane podczas zarządzania aplikacjami i urządzeniami, takie jak [uwierzytelnianie wieloskładnikowe (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) i [dostęp warunkowy](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

- Wielu administratorów pyta, kiedy używać grup użytkowników, a kiedy grup urządzeń. Aby uzyskać wskazówki, zobacz [Grupy użytkowników a grupy urządzeń](device-profile-assign.md#user-groups-vs-device-groups).

- Pamiętaj, że użytkownik może należeć do wielu grup. Zastanów się, jakie inne dynamiczne grupy użytkowników i urządzeń można utworzyć, na przykład:

  - Wszyscy uczniowie
  - Wszystkie urządzenia z systemem Android
  - Wszystkie urządzenia z systemem iOS/iPadOS
  - Marketing
  - Kadry
  - Wszyscy pracownicy z Charlotte
  - Wszyscy pracownicy z Redmond
  - Administratorzy IT z Wybrzeża Zachodniego
  - Administratorzy IT z Wybrzeża Wschodniego

Utworzonych użytkowników i grupy można też zobaczyć w [centrum administracyjnym platformy Microsoft 365](https://admin.microsoft.com), usłudze Azure AD w witrynie Azure Portal i [usłudze Microsoft Intune w witrynie Azure Portal](https://go.microsoft.com/fwlink/?linkid=2090973). Na potrzeby subskrypcji dzierżawy możesz tworzyć grupy we wszystkich tych obszarach i nimi zarządzać. **Jeśli Twoim celem jest zarządzanie urządzeniami, korzystaj z [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)** .

### <a name="review-group-membership"></a>Przeglądanie członkostwa w grupie

1. W centrum administracyjnym programu Endpoint Manager wybierz pozycję **Użytkownicy** > wybierz nazwę istniejącego użytkownika.

    > [!div class="mx-imgBorder"]
    > ![W centrum administracyjnym programu Endpoint Manager wybierz pozycję Użytkownicy](./media/tutorial-walkthrough-administrative-templates/select-users-endpoint-manager-admin-center.png)

2. Przejrzyj niektóre z informacji, które można dodać lub zmienić. Na przykład zapoznaj się z właściwościami, które można konfigurować, takimi jak Stanowisko, Dział, Miasto, Lokalizacja biura itd. Tych właściwości można używać w zapytaniach dynamicznych podczas tworzenia grup dynamicznych.
3. Wybierz pozycję **Grupy**, aby wyświetlić członkostwo tego użytkownika. Możesz również usunąć użytkownika z grupy.
4. Wybierz niektóre z pozostałych opcji, aby wyświetlić więcej informacji i dostępne czynności. Na przykład przyjrzyj się przypisanej licencji, urządzeniom użytkownika itd.

### <a name="what-did-i-just-do"></a>Co właśnie zrobiliśmy?

W centrum administracyjnym programu Endpoint Manager utworzyliśmy nowe grupy zabezpieczeń oraz dodaliśmy istniejących użytkowników i urządzenia do tych grup. Będziemy używać tych grup w kolejnych krokach tego samouczka.

## <a name="create-a-template-in-intune"></a>Tworzenie szablonu w usłudze Intune

W tej sekcji utworzymy szablon administracyjny w usłudze Intune, przyjrzymy się niektórym ustawieniom w aplikacji **Zarządzanie zasadami grupy** i porównamy je z tymi samymi ustawieniami w usłudze Intune. Celem jest wyświetlenie tego samego ustawienia w zasadach grupy i w usłudze Intune.

1. W centrum administracyjnym programu Endpoint Manager wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
2. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład wprowadź **Szablon administracyjny — urządzenia uczniów z systemem Windows 10**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
    - **Typ profilu**: Wybierz pozycję **Szablony administracyjne**.

3. Wybierz przycisk **Utwórz**. Z listy rozwijanej **Wybierz kategorię** wybierz pozycję **Wszystkie produkty**. Zostaną wyświetlone wszystkie ustawienia. W tych ustawieniach zwróć uwagę na następujące właściwości:

    - **Ścieżka** do zasad jest taka sama jak w przypadku aplikacji Zarządzanie zasadami grupy lub GPEdit.
    - To ustawienie dotyczy użytkowników lub urządzeń.

### <a name="open-group-policy-management"></a>Otwieranie aplikacji Zarządzanie zasadami grupy

W tej sekcji pokażemy zasady w usłudze Intune i odpowiadające im zasady w aplikacji Edytor zarządzania zasadami grupy.

#### <a name="compare-a-device-policy"></a>Porównanie zasad urządzenia

1. Na **komputerze administratora** otwórz aplikację **Zarządzanie zasadami grupy**.

    Ta aplikacja jest instalowana z narzędziami **RSAT: Group Policy Management Tools**, które są opcjonalną funkcją instalowaną w systemie Windows. [Wymagania wstępne](#prerequisites) (w tym artykule) zawierają listę czynności niezbędnych do ich zainstalowania.

2. Rozwiń węzeł **Domeny** > wybierz swoją domenę. Na przykład wybierz domenę **contoso.net**.
3. Kliknij prawym przyciskiem myszy zasady **OfficeandEdge** > **Edytuj**. Zostanie otwarta aplikacja Edytor zarządzania zasadami grupy.

    > [!div class="mx-imgBorder"]
    > ![Kliknięcie prawym przyciskiem myszy zasad grupy ADMX Office and Edge i wybranie pozycji Edytuj](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management.png)

    **OfficeandEdge** to zasady grupy zawierające szablony ADMX pakietu Office i przeglądarki Microsoft Edge. Te zasady zostały opisane w [wymaganiach wstępnych](#prerequisites) (w tym artykule).

4. Rozwiń węzeł **Konfiguracja komputera** > **Zasady** > **Szablony administracyjne** > **Panel sterowania** > **Personalizacja**. Zwróć uwagę na dostępne ustawienia.

    > [!div class="mx-imgBorder"]
    > ![Rozwijanie węzła Konfiguracja komputera w aplikacji Edytor zarządzania zasadami grupy i przechodzenie do obszaru Personalizacja](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management-editor-admx-policy.png)

    Kliknij dwukrotnie pozycję **Zapobiegaj włączaniu kamery na ekranie blokady** i zobacz dostępne opcje:

    > [!div class="mx-imgBorder"]
    > ![Wyświetlanie opcji ustawień konfiguracji komputera w zasadach grupy](./media/tutorial-walkthrough-administrative-templates/prevent-enabling-lock-screen-camera-admx-policy.png)

5. W centrum administracyjnym zarządzania urządzeniami przejdź do szablonu o nazwie **Szablon administracyjny — urządzenia uczniów z systemem Windows 10**.
6. Z listy rozwijanej wybierz pozycję **Wszystkie produkty**, a następnie wyszukaj tekst **personalizacja**:

    > [!div class="mx-imgBorder"]
    > ![Wyszukiwanie personalizacji w szablonie administracyjnym w usłudze Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/search-personalization-administrative-template.png)

    Zwróć uwagę na dostępne ustawienia.

    Typ ustawienia to **Urządzenie**, a ścieżka to **\Panel sterowania\Personalizacja**. Ta ścieżka jest podobna do widzianej niedawno w aplikacji Edytor zarządzania zasadami grupy. Jeśli otworzysz to ustawienie, zobaczysz te same opcje **Nieskonfigurowane**, **Włączone** i **Wyłączone**, które były widoczne w aplikacji Edytor zarządzania zasadami grupy.

#### <a name="compare-a-user-policy"></a>Porównywanie zasad użytkownika

1. W szablonie administracyjnym wyszukaj pozycję **Przeglądanie InPrivate**. Zwróć uwagę na ścieżkę oraz na to, że ustawienie dotyczy użytkowników i urządzeń.

2. W aplikacji **Edytor zarządzania zasadami grupy** znajdź pasujące ustawienia użytkownika i urządzenia:

    - Urządzenie: Rozwiń węzeł **Konfiguracja komputera** > **Zasady** > **Szablony administracyjne** > **Składniki systemu Windows** > **Internet Explorer** > **Prywatność** > **Wyłącz przeglądanie InPrivate**.
    - Użytkownik: Rozwiń węzeł **Konfiguracja użytkownika** > **Zasady** > **Szablony administracyjne** > **Składniki systemu Windows** > **Internet Explorer** > **Prywatność** > **Wyłącz przeglądanie InPrivate**.

    > [!div class="mx-imgBorder"]
    > ![Wyłączanie przeglądania InPrivate w programie Internet Explorer przy użyciu szablonu ADMX](./media/tutorial-walkthrough-administrative-templates/group-policy-turn-off-inprivate-browsing.png)

> [!TIP]
> Aby wyświetlić wbudowane zasady systemu Windows, możesz również użyć narzędzia GPEdit (aplikacji **Edytuj zasady grupy**).

#### <a name="compare-an-edge-policy"></a>Porównanie zasad programu Edge

1. W centrum administracyjnym zarządzania urządzeniami przejdź do szablonu o nazwie **Szablon administracyjny — urządzenia uczniów z systemem Windows 10**.
2. Z listy rozwijanej wybierz pozycję **Edge w wersji 77 lub nowszej**.
3. Wyszukaj tekst **uruchomienie**. Zwróć uwagę na dostępne ustawienia.
4. W aplikacji Edytor zarządzania zasadami grupy znajdź następujące ustawienia:

    - Urządzenie: Rozwiń węzeł **Konfiguracja komputera** > **Zasady** > **Szablony administracyjne** > **Microsoft Edge** > **Uruchomienie, strona główna i strona nowej karty**.
    - Użytkownik: Rozwiń węzeł **Konfiguracja użytkownika** > **Zasady** > **Szablony administracyjne** > **Microsoft Edge** > **Uruchomienie, strona główna i strona nowej karty**

### <a name="what-did-i-just-do"></a>Co właśnie zrobiliśmy?

W usłudze Intune utworzyliśmy szablon administracyjny. W tym szablonie wyszukaliśmy kilka ustawień ADMX, a następnie wyszukaliśmy te same ustawienia ADMX w aplikacji Zarządzanie zasadami grupy.

## <a name="add-settings-to-the-students-admin-template"></a>Dodawanie ustawień do szablonu administracyjnego Uczniowie

W tym szablonie skonfigurujemy niektóre ustawienia programu Internet Explorer w celu zablokowania urządzeń współużytkowanych przez wielu uczniów.

1. W szablonie **Szablon administracyjny —urządzenia uczniów z systemem Windows 10** wyszukaj tekst **Wyłącz przeglądanie InPrivate** i wybierz zasady urządzenia:

    > [!div class="mx-imgBorder"]
    > ![Wyłączanie zasad urządzenia Przeglądanie InPrivate w szablonie administracyjnym w usłudze Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/turn-off-inprivate-browsing-administrative-template.png)

2. W tym oknie zwróć uwagę na opis i wartości, które można ustawić. Te opcje są podobne do zawartości widocznej w zasadach grupy.
3. Wybierz pozycję **Włączone** > **OK**, aby zapisać zmiany.
4. Skonfiguruj również poniższe ustawienia programu Internet Explorer. Nie zapomnij nacisnąć przycisku **OK**, aby zapisać zmiany.

    - **Zezwalaj na przeciąganie i upuszczanie lub kopiowanie i wklejanie plików**
      - **Typ**: Urządzenie
      - **Ścieżka**: \Składniki systemu Windows\Internet Explorer\Internetowy panel sterowania\Strona zabezpieczeń\Strefa internetowa
      - **Wartość**: Wyłączone

    - **Zapobiegaj ignorowaniu błędów certyfikatów**
      - **Typ**: Urządzenie
      - **Ścieżka**: \Składniki systemu Windows\Internet Explorer\Internetowy panel sterowania
      - **Wartość**: Włączono

    - **Wyłącz zmienianie ustawień strony głównej**
      - **Typ**: Użytkownik
      - **Ścieżka**: \Składniki systemu Windows\Internet Explorer
      - **Wartość**: Włączono
      - **Strona główna**: Wprowadź adres URL, na przykład `contoso.com`.

5. Wyczyść filtr wyszukiwania. Zwróć uwagę, że skonfigurowane ustawienia znajdują się u góry:

    > [!div class="mx-imgBorder"]
    > ![Skonfigurowane ustawienia są wyświetlane w górnej części okna usługi Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/configured-settings-administrative-template.png)

### <a name="assign-your-template"></a>Przypisywanie szablonu

1. W szablonie wybierz pozycję **Przypisania**. Może być konieczne zamknięcie szablonu, a następnie wybranie go z listy **Urządzenia — Profile konfiguracji**:

    > [!div class="mx-imgBorder"]
    > ![Wybieranie profilu szablonu administracyjnego z listy profilów konfiguracji urządzeń w usłudze Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/filter-administrative-template-device-configuration-profiles-list.png)

2. Wybierz pozycję **Wybierz grupy do uwzględnienia**. Zostanie wyświetlona lista istniejących użytkowników i grup.
3. Wybierz utworzoną wcześniej grupę **Wszystkie urządzenia uczniów z systemem Windows 10** > **Wybierz**.

    Jeśli korzystasz z tego samouczka w środowisku produkcyjnym, rozważ dodanie pustych grup. Celem jest przećwiczenie przypisywania szablonu.

4. **Zapisz** zmiany.

Po zapisaniu profilu zostanie on zastosowany do urządzeń w momencie ich zaewidencjonowania w usłudze Intune. Jeśli urządzenia mają połączenie z Internetem, może to nastąpić od razu. Aby uzyskać więcej informacji na temat czasu odświeżania zasad, zobacz [Jak długo trwa pobieranie zasad, profilu lub aplikacji na urządzenia po ich przypisaniu](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Podczas przypisywania rygorystycznych lub restrykcyjnych zasad i profilów nie blokuj siebie. Rozważ utworzenie grupy, która będzie wykluczona z zasad i profilów. Ma to na celu zapewnienie sobie możliwości rozwiązywania problemów. Monitoruj tę grupę, aby upewnić się, że jest ona używana zgodnie z zamierzeniami.

### <a name="what-did-i-just-do"></a>Co właśnie zrobiliśmy?

W centrum administracyjnym programu Endpoint Manager utworzyliśmy profil konfiguracji urządzenia w szablonie administracyjnym i przypisaliśmy ten profil do utworzonej grupy.

## <a name="create-a-onedrive-template"></a>Tworzenie szablonu usługi OneDrive

W tej sekcji utworzysz szablon administracyjny usługi OneDrive w usłudze Intune w celu sterowania niektórymi ustawieniami. Te konkretne ustawienia zostały wybrane, ponieważ są często używane przez organizacje.

1. Utwórz kolejny profil (**Urządzenia** > **Profile konfiguracji** > **Utwórz profil**).

2. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź **Szablon administracyjny — zasady usługi OneDrive dotyczące wszystkich użytkowników systemu Windows 10**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
    - **Typ profilu**: Wybierz pozycję **Szablony administracyjne**.

3. Wybierz przycisk **Utwórz**.
4. Z listy rozwijanej wybierz pozycję **Office**.
5. **Włącz** poniższe ustawienia. Nie zapomnij nacisnąć przycisku **OK**, aby zapisać zmiany.

    - **Logowanie użytkowników w trybie dyskretnym do klienta synchronizacji usługi OneDrive przy użyciu poświadczeń systemu Windows**
    - **Korzystanie z plików usługi OneDrive na żądanie**
    - **Uniemożliwianie użytkownikom synchronizacji osobistych kont usługi OneDrive**

Ustawienia będą wyglądać podobnie do następujących:

> [!div class="mx-imgBorder"]
> ![Tworzenie szablonu administracyjnego usługi OneDrive w usłudze Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/one-drive-administrative-template.png)

Aby uzyskać więcej informacji na temat ustawień klienta usługi OneDrive, zobacz [Use Group Policy to control OneDrive sync client settings](https://docs.microsoft.com/onedrive/use-group-policy) (Sterowanie ustawieniami klienta synchronizacji usługi OneDrive przy użyciu zasad grupy).

### <a name="assign-your-template"></a>Przypisywanie szablonu

1. W szablonie wybierz pozycję **Przypisania**.
2. Wybierz pozycję **Wybierz grupy do uwzględnienia**. Zostanie wyświetlona lista istniejących użytkowników i grup.
3. Wybierz utworzoną wcześniej grupę **Wszystkie urządzenia z systemem Windows** > **Wybierz**.

    Jeśli korzystasz z tego samouczka w środowisku produkcyjnym, rozważ dodanie pustych grup. Celem jest przećwiczenie przypisywania szablonu.

4. **Zapisz** zmiany.

W tym momencie utworzyliśmy kilka szablonów administracyjnych i przypisaliśmy je do utworzonych grup. Następnym krokiem jest utworzenie szablonu administracyjnego przy użyciu programu Windows PowerShell i interfejsu API programu Microsoft Graph dla usługi Intune.

## <a name="optional-create-a-policy-using-powershell-and-graph-api"></a>Opcjonalnie: Tworzenie zasad przy użyciu programu PowerShell i interfejsu API programu Graph

W tej sekcji wykorzystano poniższe zasoby. Zainstalujemy te zasoby w ramach tej sekcji.

- [Zestaw SDK programu PowerShell usługi Intune](https://github.com/microsoft/Intune-PowerShell-SDK)
- [Interfejs API programu Microsoft Graph dla usługi Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)

1. Na **komputerze administratora** otwórz program **Windows PowerShell** jako administrator:

    1. Na pasku wyszukiwania wprowadź **powershell**.
    2. Kliknij prawym przyciskiem myszy pozycję **Windows PowerShell** > **Uruchom jako administrator**.

    > [!div class="mx-imgBorder"]
    > ![Uruchamianie programu Windows PowerShell jako administrator](./media/tutorial-walkthrough-administrative-templates/run-windows-powershell-administrator.png)

2. Pobierz i ustaw zasady wykonywania.

    1. Wprowadź: `get-ExecutionPolicy`

        Zapisz ustawienie, którym może mieć wartość **Ograniczone**. Po zakończeniu pracy z samouczkiem przywróć oryginalną wartość.

    2. Wprowadź: `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`

    3. Wprowadź `Y`, aby dokonać zmiany.

    Zasady wykonywania programu PowerShell pomagają zapobiegać wykonywaniu złośliwych skryptów. Aby uzyskać więcej informacji, zobacz [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) (Zasady wykonywania — informacje).

3. Wprowadź: `Install-Module -Name Microsoft.Graph.Intune`

    Wprowadź `Y`, jeśli:

    - Zostanie wyświetlona prośba o zainstalowanie dostawcy NuGet
    - Zostanie wyświetlona prośba o zainstalowanie modułów z niezaufanego repozytorium

    Może to zająć kilka minut. Po zakończeniu zostanie wyświetlony wiersz polecenia podobny do następującego:

    > [!div class="mx-imgBorder"]
    > ![Wiersz polecenia programu Windows PowerShell po zainstalowaniu modułu](./media/tutorial-walkthrough-administrative-templates/powershell-prompt.png)

4. W przeglądarce internetowej przejdź do witryny [https://github.com/Microsoft/Intune-PowerShell-SDK/releases](https://github.com/Microsoft/Intune-PowerShell-SDK/releases) i wybierz plik **Intune-PowerShell-SDK_v6.1907.00921.0001.zip**.

    1. Wybierz pozycję **Zapisz jako** i wybierz folder, który zapamiętasz. Dobrym wyborem jest `c:\psscripts`.
    2. Otwórz folder, kliknij prawym przyciskiem myszy plik ZIP > **Wyodrębnij wszystkie** > **Wyodrębnij**. Struktura folderów wygląda podobnie do następującego folderu:

        > [!div class="mx-imgBorder"]
        > ![Struktura folderów zestawu SDK programu PowerShell usługi Intune po wyodrębnieniu](./media/tutorial-walkthrough-administrative-templates/psscripts-directory.png)

5. Na karcie **Widok** zaznacz pozycję **Rozszerzenia nazw plików**:

    > [!div class="mx-imgBorder"]
    > ![Wybieranie rozszerzeń nazw plików na karcie Widok w Eksploratorze](./media/tutorial-walkthrough-administrative-templates/file-names-extension.png)

6. W folderze przejdź do folderu `c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471`. Kliknij prawym przyciskiem myszy każdy plik DLL > **Właściwości** > **Odblokuj**.

    > [!div class="mx-imgBorder"]
    > ![Odblokowywanie bibliotek DLL](./media/tutorial-walkthrough-administrative-templates/unblock-dll.png)

7. W aplikacji **Windows PowerShell** wprowadź:

    ```powershell
    Import-Module c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471\Microsoft.Graph.Intune.psd1
    ```

    Jeśli zostanie wyświetlony monit o uruchomienie plików od niezaufanego wydawcy, wprowadź `R`.

8. Szablony administracyjne usługi Intune używają programu Graph w wersji beta:

    1. Wprowadź: `Update-MSGraphEnvironment -SchemaVersion 'beta'`

    2. Wprowadź: `Connect-MSGraph -AdminConsent`

    3. Po wyświetleniu monitu zaloguj się przy użyciu tego samego konta administratora platformy Microsoft 365. Te polecenia cmdlet tworzą zasady w organizacji dzierżawcy.

        **Użytkownik**: Wprowadź konto administratora swojej subskrypcji dzierżawy platformy Microsoft 365.  
        **Hasło**: Wprowadź jego hasło.

    4. Wybierz pozycję **Zaakceptuj**.

9. Utwórz profil konfiguracji **Konfiguracja testu**. Wprowadź:

    ```powershell
    $configuration = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations -Content '{"displayName":"Test Configuration","description":"A test configuration created through PS"}' -HttpMethod POST
    ```

    Po pomyślnym wykonaniu tych poleceń cmdlet zostanie utworzony profil. Aby potwierdzić, przejdź do centrum administracyjnego programu Endpoint Manager > **Profile konfiguracji**. Twój profil **Konfiguracja testu** powinien być widoczny na liście.

10. Pobierz wszystkie elementy SettingDefinitions. Wprowadź:

    ```powershell
    $settingDefinitions = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions -HttpMethod GET
    ```

11. Znajdź identyfikator definicji przy użyciu nazwy wyświetlanej ustawienia. Wprowadź:

    ```powershell
    $desiredSettingDefinition = $settingDefinitions.value | ? {$_.DisplayName -Match "Silently sign in users to the OneDrive sync client with their Windows credentials"}
    ```

12. Skonfiguruj ustawienie. Wprowadź:

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues" -Content ("{""enabled"":""true"",""configurationType"":""policy"",""definition@odata.bind"":""https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions('$($desiredSettingDefinition.id)')""}") -HttpMethod POST
    ```

    ```powershell
    Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -Content ("{""enabled"":""false""}") -HttpMethod PATCH
    ```

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -HttpMethod GET
    ```

### <a name="see-your-policy"></a>Wyświetlanie zasad

1. W centrum administracyjnym programu Endpoint Manager > **Profile konfiguracji** > **Odśwież**.
2. Wybierz swój profil **Konfiguracja testu** > **Ustawienia**.
3. Z listy rozwijanej wybierz pozycję **Wszystkie produkty**.

Zobaczysz, że ustawienie **Logowanie użytkowników w trybie dyskretnym do klienta synchronizacji usługi OneDrive przy użyciu poświadczeń systemu Windows** zostało skonfigurowane.

## <a name="policy-best-practices"></a>Najlepsze rozwiązania dotyczące zasad

Podczas tworzenia zasad i profilów w usłudze Intune warto rozważyć pewne zalecenia i najlepsze rozwiązania. Aby uzyskać więcej informacji, zobacz [Najlepsze rozwiązania dotyczące zasad i profilów](device-profile-create.md#recommendations).

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Gdy nie będą już więcej potrzebne, możesz:

- Usunąć utworzone grupy:

  - **Wszystkie urządzenia uczniów z systemem Windows 10**
  - **Wszystkie urządzenia z systemem Windows**
  - **Wszyscy nauczyciele**

- Usunąć utworzone szablony administracyjne:

  - **Szablon administracyjny — urządzenia uczniów z systemem Windows 10**
  - **Szablon administracyjny — zasady usługi OneDrive dotyczące wszystkich użytkowników systemu Windows 10**
  - **Konfiguracja testu**

- Przywrócić oryginalną wartość ustawienia zasad wykonywania programu Windows PowerShell. Poniższy przykład powoduje ustawienie zasad wykonywania na Ograniczone:

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy Restricted
  ```

## <a name="next-steps"></a>Następne kroki

W ramach tego samouczka lepiej poznaliśmy [centrum administracyjne programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), utworzyliśmy grupy dynamiczne przy użyciu konstruktora zapytań oraz utworzyliśmy w usłudze Intune szablony administracyjne w celu skonfigurowania [ustawień ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies). Porównaliśmy także użycie szablonów ADMX w środowisku lokalnym i w chmurze w usłudze Intune. Dodatkowo za pomocą poleceń cmdlet programu PowerShell utworzyliśmy szablon administracyjny.

Aby uzyskać więcej informacji na temat szablonów administracyjnych w usłudze Intune, zobacz:

> [!div class="nextstepaction"]
> [Korzystanie z szablonów systemu Windows 10 umożliwiających konfigurowanie ustawień zasad grupy w usłudze Intune](administrative-templates-windows.md)
