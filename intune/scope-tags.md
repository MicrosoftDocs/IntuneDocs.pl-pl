---
title: Filtrowanie zasad przy użyciu tagów zakresu w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Tagi zakresu umożliwiają filtrowanie profilów konfiguracji dla określonych ról.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb57ea2ef5c99c58968ee25b3a75b2165ece787a
ms.sourcegitcommit: 0adb41c0640743d5cb726e66ad2427e3ad6faf20
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/29/2019
ms.locfileid: "58658553"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Użyj kontroli dostępu opartej na rolach (RBAC) i tagi zakresu dla rozproszonego IT

Aby upewnić się, że odpowiednie Administratorzy mają odpowiednich uprawnień dostępu i widoczność odpowiednie obiekty usługi Intune, można użyć tagów kontroli i zakres dostępu opartej na rolach. Role określają, jakie dostępu administratorzy mieli do obiektów. Tagi zakresu określić obiekty, które Administratorzy mogą zobaczyć.

Na przykład załóżmy, że administrator biuro regionalne Seattle przypisany do roli Menedżer zasad i profilów. Chcesz, aby ten administrator zobaczenie i zarządzanie tylko profile i zasady, które dotyczą tylko urządzeń z Seattle. Aby to zrobić, jak:

1. Utwórz tag zakresu o nazwie Seattle.
2. Tworzenie przypisania roli dla roli Menedżer zasad i profilów za pomocą: 
    - Członkowie (grupy) = grupę zabezpieczeń o nazwie Administratorzy Seattle IT. Wszyscy administratorzy w tej grupie mają uprawnienia do zarządzania zasadami i profilami użytkowników/urządzeń, w zakresie (grupy).
    - Zakres (grupy) = zabezpieczeń Seattle o nazwie grupy użytkowników. Wszystkich użytkowników/urządzeń w tej grupie może mieć ich profile i zasady, zarządzane przez administratorów w usłudze członkowie (grupy). 
    - Zakres (tagi) = Seattle. Urządzenia, które mają również tag zakresu Seattle widoczną dla administratorów w elemencie członkowskim (grupy).
3. Dodaj tag zakresu Seattle do zasad i profilów, które chcesz, aby administratorzy (grupy), aby można było uzyskać dostęp do elementów członkowskich.
4. Dodaj tag zakresu Seattle do urządzeń, które mają być widoczne dla administratorów w usłudze członkowie (grupy). 


## <a name="to-create-a-scope-tag"></a>Aby utworzyć tag zakresu

1. W usłudze Intune, wybierz **role** > **zakres (tagi)** > **Utwórz**.

    ![Zrzut ekranu przedstawiający utwórz tag zakresu.](./media/scope-tags/create-scope-tag.png)

2. Podaj **nazwę** i **opis**.
3. Wybierz pozycję **Utwórz**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Aby przypisać tag zakresu do roli

1. W usłudze Intune, wybierz **role** > **wszystkie role** > Wybierz rolę > **przypisania** > **przypisać**.

    ![Zrzut ekranu przedstawiający przypisywanie zakresie do roli.](./media/scope-tags/assign-scope-to-role.png)

2. Podaj **nazwa przypisania** i **opis**.
3. Wybierz **członkowie (grupy)** > **Dodaj** > Wybierz grupy, które mają w ramach tego przypisania > **wybierz**  >   **OK**. mUsers w tej grupie mają uprawnienia do zarządzania zasadami i profilami użytkowników/urządzeń, w zakresie (grupy).

    ![Zrzut ekranu przedstawiający wybranego elementu członkowskiego grupy.](./media/scope-tags/select-member-groups.png)

4. Do użytkowników/urządzeń, konkretny zestaw grup zarządzania, należy wybrać **zakres (grupy)** > **wybrane grupy** > **wybierz grupy do uwzględnienia**> Wybierz grupy > **wybierz** > **OK**. Wszystkich użytkowników/urządzeń w tej grupie może mieć ich profile i zasady zarządzanego przez administratorów w elementach członkowskich (grupa).

    ![Zrzut ekranu przedstawiający wybierz zakres grupy.](./media/scope-tags/select-scope-groups.png)

    Alternatywnie można wybrać **urządzeniom**, **wszyscy użytkownicy**, lub **wszyscy użytkownicy i wszystkie urządzenia**.

    ![Zrzut ekranu przedstawiający inne opcje wybierz zakres grupy.](./media/scope-tags/scope-group-other-options.png)
    
5. Wybierz **zakres (tagi)** > **Dodaj** > Wybierz tagi, które chcesz dodać do tej roli > **wybierz** > **OK**. Użytkownicy w członkowie (grupy) mają dostęp do zasad i profilów, które również mają tego samego tagu zakresu.

    ![Zrzut ekranu przedstawiający tagi zaznacz zakresu.](./media/scope-tags/select-scope-tags.png)

6. Wybierz przycisk **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Aby dodać tag zakresu do profilu konfiguracji
1. W usłudze Intune, wybierz **konfiguracji urządzenia** > **profile** > Wybierz profil.

    ![Zrzut ekranu przedstawiający wybierz profil.](./media/scope-tags/choose-profile.png)

2. Wybierz **właściwości** > **zakres (tagi)** > **Dodaj**.

    ![Zrzut ekranu przedstawiający dodawanie tagów zakresu.](./media/scope-tags/add-scope-tags.png)

3. W obszarze **zaznacz znaczniki**, wybierać znaczniki, które chcesz dodać do profilu.
4. Wybierz **wybierz** > **OK** > **Zapisz**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Aby przypisać tagu zakresu zasad konfiguracji aplikacji
W przypadku urządzeń z **typ rejestracji urządzenia** równa **urządzeń zarządzanych przy użyciu**:
1. Wybierz **aplikacje klienckie** > **zasady konfiguracji aplikacji** > Wybierz zasady konfiguracji aplikacji.
2. Wybierz **właściwości** > **zakres (tagi)** > wybierać znaczniki, którą chcesz przypisać do zasad.

W przypadku urządzeń z **typ rejestracji urządzenia** równa **aplikacje zarządzane przez**:
1. Wybierz **aplikacje klienckie** > **zasady konfiguracji aplikacji** > Wybierz zasady konfiguracji aplikacji.
2. Wybierz **zakres (tagi)** > wybierać znaczniki, którą chcesz przypisać do zasad.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Przypisywanie tagu zakresu do profilu aprowizacji aplikacji systemu iOS
1. W usłudze Intune, wybierz **aplikacje klienckie** > **profilów aprowizacji aplikacji dla systemu iOS** > Wybierz profil.
2. Wybierz **właściwości** > **zakres (tagi)** > Wybierz znaczników według których chcesz przypisać do profilu.
3. Wybierz **wybierz** > **OK** > **Zapisz**.

## <a name="scope-tag-details"></a>Szczegóły tagu zakresu
Podczas pracy z tagami zakres, należy pamiętać o tych szczegółów:

- Obecnie można przypisać tagi zakresu do:
    - Przypisania ról
    - Zasady zgodności urządzenia
    - Profile konfiguracji urządzeń
    - Windows 10 aktualizacje pierścienie
    - Urządzenia zarządzane
    - Aplikacje
    - Zasady konfiguracji aplikacji — zarządzanych urządzeń
    - Skrypty środowiska Powershell
    - Tokeny usługi DEP
    - Profil aprowizowania aplikacji dla systemu iOS
- Gdy administrator tworzy obiekt w usłudze Intune, wszystkie tagi zakresu przypisane do tego administratora zostanie automatycznie przypisany do nowego obiektu.
- Kontroli RBAC usługi Intune nie ma zastosowania do ról usługi Azure Active Directory. Dlatego role Administratorzy usługi Intune i Administratorzy globalni mają administratora pełnego dostępu do usługi Intune, niezależnie od tego, jakie tagi zakresu mają.
- Administratorzy w przypisaniu roli, przy użyciu tagów zakresu można również wyświetlić obiekty usługi Intune z Brak tagów zakresu.
- Można przypisać tylko tag zakresu, które masz w swoje przypisania roli.
- Możesz to zrobić tylko grup docelowych, które są wymienione w zakres (grupy) przypisanie roli.
- Tag zakresu przypisane do roli użytkownika nie może usunąć wszystkie tagi zakresu do obiektu usługi Intune. Wymagany jest co najmniej jeden zakres znacznik.

## <a name="next-steps"></a>Następne kroki

Zarządzanie własnymi [rolami](role-based-access-control.md) i [profilami](device-profile-assign.md).
