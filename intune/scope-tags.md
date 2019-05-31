---
title: Filtrowanie zasad przy użyciu tagów zakresu w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Tagi zakresu umożliwiają filtrowanie profilów konfiguracji dla określonych ról.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57a14e1e3c4caea570667096fec71cecf2d88ddf
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045190"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej

Za pomocą kontroli dostępu opartej na rolach i tagów zakresu możesz upewnić się, że odpowiedni administratorzy mają właściwe uprawnienia dostępu i wgląd we właściwe obiekty usługi Intune. Role określają dostęp, jaki administratorzy mają do poszczególnych obiektów. Tagi zakresu określają obiekty widoczne dla administratorów.

Na przykład załóżmy, że administrator biura regionalnego w Seattle ma przypisaną rolę Menedżer zasad i profilów. Chcesz, aby ten administrator widział tylko profile i zasady dotyczące urządzeń z Seattle oraz tylko nimi mógł zarządzać. Aby to zrobić:

1. Utwórz tag zakresu o nazwie Seattle.
2. Utwórz przypisanie roli dla roli Menedżer zasad i profilów z następującymi elementami: 
    - Członkowie (grupy) = grupa zabezpieczeń o nazwie Administratorzy IT Seattle. Wszyscy administratorzy w tej grupie mają uprawnienia do zarządzania zasadami i profilami użytkowników/urządzeń w grupie Zakres (grupy).
    - Zakres (grupy) = grupa zabezpieczeń o nazwie Użytkownicy Seattle. Profilami i zasadami wszystkich użytkowników/urządzeń w tej grupie mogą zarządzać administratorzy z grupy Członkowie (grupy). 
    - Zakres (tagi) = Seattle. Administratorzy z grupy Członkowie (grupy) widzą urządzenia, które mają również tag zakresu Seattle.
3. Dodaj tag zakresu Seattle do zasad i profilów, do których mają mieć dostęp administratorzy z grupy Członkowie (grupy).
4. Dodaj tag zakresu Seattle do urządzeń, które mają być widoczne dla administratorów z grupy Członkowie (grupy). 


## <a name="to-create-a-scope-tag"></a>Aby utworzyć tag zakresu

1. W usłudze Intune wybierz pozycję **Role** > **Zakres (tagi)**  > **Utwórz**.

    ![Zrzut ekranu przedstawiający tworzenie tagu zakresu.](./media/scope-tags/create-scope-tag.png)

2. Podaj **nazwę** i **opis**.
3. Wybierz pozycję **Utwórz**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Aby przypisać tag zakresu do roli

1. W usłudze Intune wybierz pozycję **Role** > **Wszystkie role** > wybierz rolę > **Przypisania** > **Przypisz**.

    ![Zrzut ekranu przedstawiający przypisywanie zakresu do roli.](./media/scope-tags/assign-scope-to-role.png)

2. Wypełnij pola **Nazwa przypisania** i **Opis**.
3. Wybierz pozycję **Członkowie (grupy)**  > **Dodaj** > wybierz grupy, które mają być objęte tym przypisaniem > **Wybierz** > **OK**. Użytkownicy w tej grupie mają uprawnienia do zarządzania zasadami i profilami użytkowników/urządzeń w grupie Zakres (grupy).

    ![Zrzut ekranu przedstawiający wybieranie grup członków.](./media/scope-tags/select-member-groups.png)

4. Jeśli chcesz zarządzać użytkownikami/urządzeniami w konkretnym zestawie grup, wybierz pozycję **Zakres (grupy)**  > **Wybrane grupy** > **Wybierz grupy do uwzględnienia**> wybierz grupy > **Wybierz** > **OK**. Profilami i zasadami wszystkich użytkowników/urządzeń w tej grupie mogą zarządzać administratorzy z grupy Członkowie (grupy).

    ![Zrzut ekranu przedstawiający wybieranie grup zakresu.](./media/scope-tags/select-scope-groups.png)

    Ewentualnie możesz wybrać pozycję **Wszystkie urządzenia**, **Wszyscy użytkownicy** lub **Wszyscy użytkownicy i wszystkie urządzenia**.

    ![Zrzut ekranu przedstawiający inne opcje wybierania grup zakresu.](./media/scope-tags/scope-group-other-options.png)
    
5. Wybierz pozycję **Zakres (tagi)**  > **Dodaj** > wybierz tagi, które chcesz dodać do tej roli > **Wybierz** > **OK**. Użytkownicy w grupie Członkowie (grupy) będą mieli dostęp do zasad i profilów, które mają też ten sam tagu zakresu.

    ![Zrzut ekranu przedstawiający wybieranie tagów zakresu.](./media/scope-tags/select-scope-tags.png)

6. Wybierz przycisk **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Aby dodać tag zakresu do profilu konfiguracji
1. W usłudze Intune wybierz pozycję **Konfiguracja urządzeń** > **Profile** > utwórz profil.

    ![Zrzut ekranu przedstawiający wybieranie profilu.](./media/scope-tags/choose-profile.png)

2. Wybierz pozycję **Właściwości** > **Zakres (tagi)**  > **Dodaj**.

    ![Zrzut ekranu przedstawiający dodawanie tagów zakresu.](./media/scope-tags/add-scope-tags.png)

3. W obszarze **Wybór tagów** wybierz tagi, które chcesz dodać do profilu.
4. Wybierz pozycję **Wybierz** > **OK** > **Zapisz**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Aby przypisać tag zakresu do zasad konfiguracji aplikacji
W przypadku urządzeń z ustawieniem **Typ rejestracji urządzenia** o wartości **Urządzenia zarządzane**:
1. Wybierz pozycję **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** > wybierz zasady konfiguracji aplikacji.
2. Wybierz pozycję **Właściwości** > **Zakres (tagi)** > wybierz tagi, które chcesz przypisać do zasad.

W przypadku urządzeń z ustawieniem **Typ rejestracji urządzenia** o wartości **Aplikacje zarządzane**:
1. Wybierz pozycję **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** > wybierz zasady konfiguracji aplikacji.
2. Wybierz pozycję **Zakres (tagi)** > wybierz tagi, które chcesz przypisać do zasad.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Aby przypisać tag zakresu do profilu aprowizacji aplikacji systemu iOS
1. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Profile aprowizacji aplikacji systemu iOS** > wybierz profil.
2. Wybierz pozycję **Właściwości** > **Zakres (tagi)** > wybierz tagi, które chcesz przypisać do profilu.
3. Wybierz pozycję **Wybierz** > **OK** > **Zapisz**.

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Aby przypisać tag zakresu do tokenu programu zakupów zbiorczych VPP (Volume Purchase Program) firmy Apple
1. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Tokeny VPP firmy Apple** > wybierz token programu VPP.
2. Wybierz pozycję **Zakres (tagi)** > wybierz tagi, które chcesz przypisać do profilu. Aplikacje programu VPP i książki elektroniczne skojarzone z tokenem VPP dziedziczą przypisane tagi.
3. Wybierz pozycję **Wybierz** > **OK** > **Zapisz**.

## <a name="scope-tag-details"></a>Szczegóły tagu zakresu
Podczas pracy z tagami zakresu należy pamiętać o następujących szczegółach:

- Obecnie tagi zakresu można przypisać do następujących elementów:
    - Przypisania ról
    - Zasady zgodności urządzenia
    - Profile konfiguracji urządzeń
    - Pierścienie aktualizacji systemu Windows 10
    - Urządzenia zarządzane
    - Aplikacje
    - Zasady konfiguracji aplikacji — urządzenia zarządzane
    - Skrypty środowiska Powershell
    - Tokeny usługi DEP
    - Profil aprowizowania aplikacji dla systemu iOS
    - Tokeny programu zakupów zbiorczych VPP (Volume Purchase Program)
- Gdy administrator utworzy obiekt w usłudze Intune, wszelkie tagi zakresu przypisane do tego administratora zostaną automatycznie przypisane do tego nowego obiektu.
- Kontrola dostępu oparta na rolach usługi Intune nie ma zastosowania do ról usługi Azure Active Directory. W związku z tym role administratorów usługi Intune i administratorów globalnych mają pełny dostęp administracyjny do usługi Intune niezależnie od tego, jakie mają tagi zakresu.
- Administratorzy w przypisaniu roli z tagami zakresu widzą też obiekty usługi Intune bez tagów zakresu.
- Możesz przypisywać tylko tag zakresu, który masz w swoim przypisaniu roli.
- Jako grup docelowych możesz używać tylko grup wymienionych w grupie Zakres (grupy) Twojego przypisania roli.
- Jeśli do Twojej roli jest przypisany tag zakresu, nie możesz usunąć wszystkich tagów zakresu przypisanych do obiektu usługi Intune. Wymagany jest co najmniej jeden dodatkowy tag zakresu.

## <a name="next-steps"></a>Następne kroki

Zarządzanie własnymi [rolami](role-based-access-control.md) i [profilami](device-profile-assign.md).
