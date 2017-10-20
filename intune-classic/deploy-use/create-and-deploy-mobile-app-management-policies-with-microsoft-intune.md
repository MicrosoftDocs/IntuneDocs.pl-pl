---
title: "Tworzenie i wdrażanie zasad MAM"
description: "Postępuj zgodnie z instrukcjami krok po kroku w tym temacie, aby utworzyć i wdrożyć zasady zarządzania aplikacjami mobilnymi."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93ec41c756c802986b85a45f53329ef6daba6c08
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a>Tworzenie i wdrażanie zasad ochrony aplikacji przy użyciu usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym temacie opisano proces tworzenia zasad ochrony aplikacji w witrynie **Azure Portal**. Witryna Azure Portal to nowa konsola administracyjna do tworzenia zasad ochrony aplikacji. Do ich tworzenia zalecane jest użycie tego portalu. Portal Azure obsługuje następujące scenariusze zarządzania aplikacjami mobilnymi:

- Urządzenia zarejestrowane w usłudze Intune.
- Urządzenia zarządzane przez rozwiązanie MDM innej firmy.
- Urządzenia niezarządzane przez żadne rozwiązanie MDM (BYOD).

>[!IMPORTANT]
Jeśli zarządzasz urządzeniami za pomocą **konsoli administracyjnej usługi Intune**, weź pod uwagę następujące informacje:

> * Zasady ochrony aplikacji, które obsługują aplikacje na potrzeby urządzeń przenośnych zarejestrowanych w usłudze Intune, możesz utworzyć przy użyciu [konsoli administracyjnej usługi Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
> * Zasad ochrony aplikacji utworzonych w konsoli administracyjnej usługi Intune nie można zaimportować do witryny Azure Portal.  Zasady ochrony aplikacji należy ponownie utworzyć w witrynie Azure Portal.

> * W konsoli administracyjnej usługi Intune mogą nie być wyświetlane wszystkie ustawienia zasad ochrony aplikacji. Witryna Azure Portal to nowa konsola administracyjna do tworzenia zasad ochrony aplikacji.

> * Aby wdrożyć aplikacje zarządzane, należy utworzyć zasady ochrony aplikacji w konsoli administracyjnej usługi Intune. W takim przypadku można utworzyć zasady ochrony aplikacji zarówno w konsoli administracyjnej usługi Intune, jak i w witrynie Azure Portal. Konsola administracyjna usługi Intune umożliwia wdrażanie aplikacji zarządzanych, a witryna Azure Portal to nowa konsola administracyjna, która udostępnia wszystkie ustawienia zasad ochrony aplikacji.

> * Jeśli utworzysz zasady ochrony aplikacji zarówno za pomocą konsoli administracyjnej usługi Intune, jak i witryny Azure Portal, dla aplikacji zostaną zastosowane zasady utworzone w witrynie Azure Portal.

Aby wyświetlić listę zasad obsługiwanych na platformach Android i iOS, wybierz jeden z następujących elementów:

> [!div class="op_single_selector"]
- [Zasady systemu iOS](ios-mam-policy-settings.md)
- [Zasady systemu Android](android-mam-policy-settings.md)

- Bardziej szczegółowy opis działania zasad ochrony aplikacji i scenariuszy obsługiwanych przy użyciu zasad ochrony aplikacji usługi Intune znajduje się w temacie [Ochrona danych aplikacji przy użyciu zasad ochrony aplikacji](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

##  <a name="create-an-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji
Zasady ochrony aplikacji tworzy się w witrynie Azure Portal. Jeśli używasz witryny Azure Portal po raz pierwszy, przeczytaj artykuł [Azure Portal — zasady ochrony aplikacji usługi Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md), aby zapoznać się z tą witryną. Zanim utworzysz zasady ochrony aplikacji, przejrzyj informacje w sekcji [Wymagania wstępne i pomoc techniczna](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

Wykonaj poniższe kroki, aby utworzyć zasady ochrony aplikacji:

1. Przejdź do witryny [Azure Portal](https://portal.azure.com) i podaj swoje poświadczenia.

2. Wybierz opcję **Więcej usług**, a następnie wpisz „Intune”.

3. Wybierz opcję **Ochrona aplikacji w usłudze Intune**.

4. Wybierz pozycje **Zarządzanie aplikacjami mobilnymi usługi Intune &gt; Ustawienia**, aby otworzyć blok **Wszystkie ustawienia**.

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  W bloku **Wszystkie ustawienia** wybierz pozycję **Zasady aplikacji**. Spowoduje to otwarcie bloku **Zasady aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące. Wybierz pozycję **Dodaj zasady**.

    ![Zrzut ekranu przedstawiający blok zasad aplikacji z podświetloną opcją menu Dodaj zasady ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  Wpisz nazwę zasad, dodaj ich krótki opis i wybierz typ platformy do utworzenia zasad dla systemu iOS lub Android. Dla każdej platformy można utworzyć większą liczbę zasad.

    ![Zrzut ekranu przedstawiający blok Dodawanie zasad](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Wybierz pozycję **Aplikacje**, aby otworzyć **blok Aplikacje**, w którym jest wyświetlana lista dostępnych aplikacji. Z listy wybierz jedną lub więcej aplikacji do powiązania z tworzonymi zasadami. Po wybraniu aplikacji wybierz opcję **Wybierz** w dolnej części bloku **Aplikacje**, aby zapisać wybrane opcje.

    > [!IMPORTANT]
    > W celu utworzenia zasad należy wybrać co najmniej jedną aplikację.

5.  W bloku **Dodawanie zasad** wybierz pozycję **Skonfiguruj wymagane ustawienia**, aby otworzyć blok ustawień zasad.

    Istnieją dwie kategorie ustawień zasad, **Przeniesienie danych** i **Dostęp**.  Zasady przeniesienia danych stosują się do przenoszenia danych do i z aplikacji, podczas gdy zasady dostępu określają metodę dostępu użytkownika końcowego do aplikacji w kontekście pracy.
    Ustawienia zasad mają wartości domyślne, co ułatwia rozpoczęcie pracy. Jeśli wartości domyślne spełniają Twoje wymagania, nie musisz wprowadzać żadnych zmian.

    > [!TIP]
    > Te ustawienia zasad obowiązują tylko w przypadku stosowania aplikacji w kontekście pracy.  W przypadku gdy użytkownik końcowy używa aplikacji do wykonywania zadań osobistych, zasady te nie obowiązują.

    ![Zrzut ekranu przedstawiający blok ustawień z blokiem Dodawanie zasad](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w bloku **Dodawanie zasad** . Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

    ![Zrzut ekranu przedstawiający blok Dodawanie zasad z informacją o tym, że aplikacje i ustawienia zostały skonfigurowane](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

Po zakończeniu tworzenia zasad zgodnie z opisem w poprzedniej procedurze nie są one wdrażane dla żadnych użytkowników. Aby wdrożyć zasady, zobacz następującą sekcję: „Wdrażanie zasad dla użytkowników”.

> [!IMPORTANT]
> Jeśli utworzysz zasady ochrony aplikacji dla aplikacji przy pomocy konsoli administracyjnej usługi Intune oraz zasady ochrony aplikacji przy pomocy witryny Azure Portal, pierwszeństwo będą miały zasady utworzone w witrynie Azure Portal. Jednak raportowanie w konsoli usługi Intune lub programu Configuration Manager będzie zgłaszać ustawienia zasad utworzonych w konsoli administracyjnej usługi Intune. Na przykład:
>
> -   W konsoli administracyjnej usługi Intune utworzono zasady ochrony aplikacji, które blokują kopiowanie danych z aplikacji.
> -   W konsoli platformy Azure utworzono zasady ochrony aplikacji, które zezwalają na kopiowanie danych z aplikacji.
> -   Obie zasady zostały skojarzone z jedną aplikacją.
> -   Priorytet ma zasada utworzona w konsoli platformy Azure, która umożliwia kopiowanie.
> -   Jednak stan i raporty w konsoli usługi Intune będą niepoprawnie wskazywać blokowanie kopiowania.

## <a name="line-of-business-lob-apps-optional"></a>Aplikacje biznesowe (LOB) (opcjonalnie)

Począwszy od wersji Intune 1703, podczas tworzenia nowych zasad ochrony aplikacji możesz dodawać do usługi Intune aplikacje biznesowe. Umożliwia to definiowanie zasad ochrony aplikacji biznesowych przy użyciu zestawu SDK MAM bez konieczności żądania pełnych uprawnień do wdrażania aplikacji.
/intune/app-sdk-get-started
> [!TIP]
> Aplikacje biznesowe możesz również dodawać do usługi Intune podczas realizacji przepływu pracy [zestawu SDK aplikacji usługi Intune](/intune/app-sdk-get-started).

> [!IMPORTANT]
> Jeśli użytkownicy mają tylko określone uprawnienia do wdrażania aplikacji MAM, a nie pełne uprawnienia, które umożliwiałyby im wdrożenie dowolnej aplikacji w usłudze Intune, nie mogą realizować przepływu pracy zestawu SDK usługi Intune, ale wciąż mogą dodawać swoje aplikacje biznesowe za pomocą przepływu pracy tworzenia zasad ochrony aplikacji MAM.

### <a name="to-add-lob-apps-ios-and-android"></a>Aby dodać aplikacje biznesowe (iOS i Android)

1.  W bloku Dodawanie zasad wybierz pozycję **Aplikacje**, aby otworzyć blok Aplikacje.

    ![Blok Dodawanie zasad MAM](../media/AppManagement/mam-lob-apps-1.png)

2.  Kliknij pozycję **Więcej aplikacji**, wprowadź **identyfikator pakietu** (dla systemu iOS), **identyfikator pakietu** (dla systemu Android), a następnie kliknij pozycję Wybierz, aby dodać aplikacje biznesowe.

    ![Blok Więcej aplikacji MAM](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a>Aby dodać aplikacje biznesowe (Windows)

> [!IMPORTANT]
> Podczas tworzenia nowych zasad ochrony aplikacji musisz z listy rozwijanej platform wybrać system Windows 10.

1.  W bloku Dodawanie zasad wybierz pozycję **Aplikacje dozwolone** lub **Aplikacje wykluczone**, aby otworzyć blok Aplikacje dozwolone lub Aplikacje wykluczone.

    > [!NOTE]
    >
    - **Aplikacje dozwolone**: są to aplikacje, które muszą stosować się do tych zasad.
    - **Aplikacje wykluczone**: te aplikacje nie podlegają tym zasadom i mogą uzyskiwać dostęp do danych firmowych bez ograniczeń.
<br></br>
2. W bloku Aplikacje dozwolone lub Aplikacje wykluczone kliknij pozycję **Dodaj aplikacje**. Możesz dodać zalecane aplikacje firmy Microsoft, aplikacje ze sklepu lub aplikacje klasyczne.

    a.  **Aplikacje zalecane:** wstępnie wypełniona lista aplikacji (przede wszystkim pakietu Office), które pozwalamy administratorom łatwo importować do zasad.

    b.  **Aplikacje ze sklepu:** administrator może dodać do zasad dowolną aplikację ze sklepu Windows.

    c.  **Aplikacje klasyczne systemu Windows:** administrator może dodać do zasad dowolne aplikacje klasyczne systemu Windows (np. plik exe, dll itd.).

## <a name="deploy-a-policy-to-users"></a>Wdrażanie zasad dla użytkowników

1.  W bloku **Zasady** wybierz pozycję **Grupy użytkowników**, co spowoduje otwarcie bloku **Grupy użytkowników**. Wybierz pozycję **Dodaj grupę użytkowników** w bloku **Grupy użytkowników**, aby otworzyć blok **Dodawanie grupy użytkowników**.

    ![Zrzut ekranu przedstawiający blok Grupy użytkowników z podświetloną opcją menu Dodaj grupę użytkowników](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  W bloku **Dodawanie grupy użytkowników** zostanie wyświetlona lista grup użytkowników. Jest to lista wszystkich grup zabezpieczeń w usłudze **Azure Active Directory**. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie wybierz pozycję **Wybierz**. Wybranie pozycji **Wybierz** wdraża zasady dla użytkowników.

    ![Zrzut ekranu przedstawiający blok Dodaj grupę użytkowników z listą użytkowników usługi Azure Active Directory](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    Zasady zostały utworzone i wdrożone dla użytkowników.

Zasady wpływają tylko na użytkowników, którym przypisano licencje usługi Intune. Zasady nie wpływają na użytkowników należących do wybranej grupy zabezpieczeń, którym nie przypisano licencji usługi Intune.

>[!IMPORTANT]
> Jeśli używasz usługi Intune z programem Configuration Manager do zarządzania urządzeniami z systemami Android i iOS, zasady są stosowane tylko do użytkowników należących bezpośrednio do wybranej grupy. Nie mają one wpływu na członków grup podrzędnych zagnieżdżonych w wybranej grupie.

Użytkownicy końcowi mogą pobrać aplikacje ze sklepu App Store lub Google Play. Aby uzyskać więcej informacji, zobacz:
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](/intune/end-user-mam-apps-android)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a>Zmiana istniejących zasad
Możesz edytować istniejące zasady i zastosować je do użytkowników docelowych. Jednak w przypadku zmiany istniejących zasad użytkownicy zalogowani do aplikacji zobaczą zmiany dopiero po 8 godzinach.

Aby zobaczyć efekt zmian natychmiast, użytkownik końcowy musi wylogować się z aplikacji i ponownie do niej zalogować.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Aby zmienić listę aplikacji powiązanych z zasadami

1.  W bloku **Zasady aplikacji** wybierz zasady, które chcesz zmienić. Spowoduje to otwarcie bloku specyficznego dla właśnie wybranych zasad.

    ![Zrzut ekranu przedstawiający istniejące zasady otwarte w oddzielnym bloku](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  W bloku zasad wybierz pozycję **Aplikacje docelowe**, aby otworzyć listę aplikacji.

3.  Usuń lub dodaj aplikacje do listy i wybierz pozycję **Zapisz**, aby zapisać zmiany.

### <a name="to-change-the-list-of-user-groups"></a>Aby zmienić listę grup użytkowników

1.  W bloku **Zasady aplikacji** wybierz zasady, które chcesz zmienić. Spowoduje to otwarcie bloku specyficznego dla wybranych zasad.

2.  W bloku zasad wybierz pozycję **Grupy użytkowników**, aby otworzyć blok **Grupa użytkowników** z listą bieżących grup użytkowników, których dotyczą dane zasady.

3.  Aby dodać nową grupę użytkowników do zasad, wybierz pozycję **Dodaj grupę użytkowników** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby wdrożyć zasady dla wybranej grupy.

    ![Zrzut ekranu przedstawiający blok Dodaj grupę użytkowników z dwoma wybranymi grupami użytkowników](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Aby usunąć grupę użytkowników, wyróżnij grupę użytkowników, którą chcesz usunąć. Następnie kliknij przycisk wielokropka (...) i wybierz polecenie **Usuń**, aby usunąć grupę użytkowników.

    ![Zrzut ekranu przedstawiający opcję Usuń ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>Aby zmienić ustawienia zasad

1.  W bloku **Zasady aplikacji** wybierz zasady, które chcesz zmienić. Spowoduje to otwarcie bloku specyficznego dla właśnie wybranych zasad.

    ![Zrzut ekranu przedstawiający istniejące zasady otwarte w oddzielnym bloku ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Wybierz pozycję **Ustawienia zasad**, aby otworzyć blok **Ustawienia zasad**.

3.  Zmień ustawienia i wybierz ikonę **Zapisz**, aby zapisać zmiany.

    ![Zrzut ekranu przedstawiający blok Ustawienia zasad z opcją zapisu w menu u góry](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>Ustawienia zasad
Aby wyświetlić pełną listę ustawień zasad dla systemów iOS i Android, wybierz jeden z następujących elementów:

> [!div class="op_single_selector"]
- [Zasady systemu iOS](ios-mam-policy-settings.md)
- [Zasady systemu Android](android-mam-policy-settings.md)

## <a name="next-steps"></a>Następne kroki
[Monitorowanie zgodności i stanu użytkownika](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Zobacz także
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](/intune/end-user-mam-apps-android)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](/intune/end-user-mam-apps-ios)
