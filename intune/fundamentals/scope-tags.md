---
title: Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu dystrybuowanych w usłudze Intune | Microsoft Docs
description: Tagi zakresu umożliwiają filtrowanie profilów konfiguracji dla określonych ról.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.technology: ''
ms.assetid: a21d3039-f2ed-4f43-b6fa-d00c071edbc4
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6b92dca399afeb035bf58d998efdd469318de389
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504946"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej

Za pomocą kontroli dostępu opartej na rolach i tagów zakresu możesz upewnić się, że odpowiedni administratorzy mają właściwe uprawnienia dostępu i wgląd we właściwe obiekty usługi Intune. Role określają dostęp, jaki administratorzy mają do poszczególnych obiektów. Tagi zakresu określają obiekty widoczne dla administratorów.

Na przykład załóżmy, że administrator biura regionalnego w Seattle ma przypisaną rolę Menedżer zasad i profilów. Chcesz, aby ten administrator widział tylko profile i zasady dotyczące urządzeń z Seattle oraz tylko nimi mógł zarządzać. Aby skonfigurować ten dostęp, należy:

1. Utwórz tag zakresu o nazwie Seattle.
2. Utwórz przypisanie roli dla roli Menedżer zasad i profilów z następującymi elementami: 
    - Członkowie (grupy) = grupa zabezpieczeń o nazwie Administratorzy IT Seattle. Wszyscy administratorzy w tej grupie mają uprawnienia do zarządzania zasadami i profilami użytkowników/urządzeń w grupie Zakres (grupy).
    - Zakres (grupy) = grupa zabezpieczeń o nazwie Użytkownicy Seattle. Profilami i zasadami wszystkich użytkowników/urządzeń w tej grupie mogą zarządzać administratorzy z grupy Członkowie (grupy). 
    - Zakres (tagi) = Seattle. Administratorzy z grupy Członkowie (grupy) widzą obiekty usługi Intune, które mają również tag zakresu Seattle.
3. Dodaj tag zakresu Seattle do zasad i profilów, do których mają mieć dostęp administratorzy z grupy Członkowie (grupy).
4. Dodaj tag zakresu Seattle do urządzeń, które mają być widoczne dla administratorów z grupy Członkowie (grupy). 

## <a name="default-scope-tag"></a>Domyślny tag zakresu
Domyślny tag zakresu jest automatycznie dodawany do wszystkich nieoznakowanych obiektów, które obsługują Tagi zakresu.

Funkcja domyślnego tagu zakresu jest podobna do funkcji zakresów zabezpieczeń w programie System Center Configuration Manager. 

## <a name="to-create-a-scope-tag"></a>Aby utworzyć tag zakresu

1. W usłudze Intune wybierz pozycję **Role** > **Zakres (tagi)**  > **Utwórz**.

    ![Zrzut ekranu przedstawiający tworzenie tagu zakresu.](./media/scope-tags/create-scope-tag.png)

3. Jeśli chcesz, aby wszystkie urządzenia były określone w określonych grupach, wybierz pozycję **Przypisz tag zakresu do wszystkich urządzeń w wybranych grupach**.
    1. Na stronie **Wybierz grupy do dołączenia** wybierz grupy zawierające urządzenia, do których chcesz przypisać ten tag zakresu.
    2. Wybierz pozycję **Wybierz**.
4. Wybierz pozycję **Utwórz**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Aby przypisać tag zakresu do roli

1. W usłudze Intune wybierz pozycję **Role** > **Wszystkie role** > wybierz rolę > **Przypisania** > **Przypisz**.

    ![Zrzut ekranu przedstawiający przypisywanie zakresu do roli.](./media/scope-tags/assign-scope-to-role.png)

2. Wypełnij pola **Nazwa przypisania** i **Opis**.
3. Wybierz pozycję **Członkowie (grupy)**  > **Dodaj** > wybierz grupy, które mają być objęte tym przypisaniem > **Wybierz** > **OK**. Użytkownicy w tej grupie będą mieć uprawnienia do zarządzania użytkownikami/urządzeniami w zakresie (grupy).

    ![Zrzut ekranu przedstawiający wybieranie grup członków.](./media/scope-tags/select-member-groups.png)

4. Jeśli chcesz zarządzać użytkownikami/urządzeniami w konkretnym zestawie grup, wybierz pozycję **Zakres (grupy)**  > **Wybrane grupy** > **Wybierz grupy do uwzględnienia**> wybierz grupy > **Wybierz** > **OK**. Wszyscy użytkownicy/urządzenia w tej grupie będą zarządzani przez administratorów należących do członków (grupy).

    ![Zrzut ekranu przedstawiający wybieranie grup zakresu.](./media/scope-tags/select-scope-groups.png)

    Ewentualnie możesz wybrać pozycję **Wszystkie urządzenia**, **Wszyscy użytkownicy** lub **Wszyscy użytkownicy i wszystkie urządzenia**.

    ![Zrzut ekranu przedstawiający inne opcje wybierania grup zakresu.](./media/scope-tags/scope-group-other-options.png)
    
5. Wybierz pozycję **Zakres (tagi)**  > **Dodaj** > wybierz tagi, które chcesz dodać do tej roli > **Wybierz** > **OK**. Użytkownicy w elementach członkowskich (grupy) będą mieli dostęp do obiektów usługi Intune, które również mają ten sam tag zakresu.

    ![Zrzut ekranu przedstawiający wybieranie tagów zakresu.](./media/scope-tags/select-scope-tags.png)

6. Wybierz przycisk **OK**. 

## <a name="assign-scope-tags-to-other-objects"></a>Przypisywanie tagów zakresu do innych obiektów

W przypadku obiektów, które obsługują Tagi zakresu, Tagi zakresu są zwykle wyświetlane w obszarze **Właściwości**. Na przykład aby przypisać tag zakresu do profilu konfiguracji, wykonaj następujące kroki:

1. W usłudze Intune wybierz pozycję **Konfiguracja urządzeń** > **Profile** > utwórz profil.

    ![Zrzut ekranu przedstawiający wybieranie profilu.](./media/scope-tags/choose-profile.png)

2. Wybierz pozycję **Właściwości** > **Zakres (tagi)**  > **Dodaj**.

    ![Zrzut ekranu przedstawiający dodawanie tagów zakresu.](./media/scope-tags/add-scope-tags.png)

3. W obszarze **Wybór tagów** wybierz tagi, które chcesz dodać do profilu.
4. Wybierz pozycję **Wybierz** > **OK** > **Zapisz**.


## <a name="scope-tag-details"></a>Szczegóły tagu zakresu
Podczas pracy z tagami zakresu należy pamiętać o następujących szczegółach: 

- Można przypisać znaczniki zakresu do typu obiektu usługi Intune, Jeśli dzierżawca może mieć wiele wersji tego obiektu (takich jak przydziały ról lub aplikacje).
  Następujące obiekty usługi Intune są wyjątkami od tej reguły i nie obsługują obecnie tagów zakresu:
    - Profile systemu Windows ESP
    - Kategorie urządzeń
    - Ograniczenia rejestracji
    - Identyfikatory urządzeń firmowych
    - Urządzenia z autopilotażem
    - Lokalizacje zgodności urządzeń
    - Urządzenia Jamf
- Aplikacje i książki elektroniczne programu VPP skojarzone z tokenem VPP dziedziczą znaczniki zakresu przypisane do skojarzonego tokenu VPP.
- Urządzenia Device Enrollment Program (DEP) i profile programu DEP skojarzone z tokenem DEP dziedziczą znaczniki zakresu przypisane do skojarzonego tokenu programu DEP.
- Gdy administrator utworzy obiekt w usłudze Intune, wszelkie tagi zakresu przypisane do tego administratora zostaną automatycznie przypisane do tego nowego obiektu.
- Kontrola dostępu oparta na rolach usługi Intune nie ma zastosowania do ról usługi Azure Active Directory. W związku z tym role administratorów usługi Intune i administratorów globalnych mają pełny dostęp administracyjny do usługi Intune niezależnie od tego, jakie mają tagi zakresu.
- Jeśli przypisanie roli nie ma tagu Scope, administrator IT może zobaczyć wszystkie obiekty w oparciu o uprawnienia administratorów IT. Administratorzy, którzy nie mają tagów zakresu, zasadniczo mają wszystkie znaczniki zakresu.
- Możesz przypisywać tylko tag zakresu, który masz w swoim przypisaniu roli.
- Jako grup docelowych możesz używać tylko grup wymienionych w grupie Zakres (grupy) Twojego przypisania roli.
- Jeśli do Twojej roli jest przypisany tag zakresu, nie możesz usunąć wszystkich tagów zakresu przypisanych do obiektu usługi Intune. Wymagany jest co najmniej jeden dodatkowy tag zakresu.

## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak Tagi zakresu działają, gdy istnieje [wiele przypisań ról](role-based-access-control.md#multiple-role-assignments).
Zarządzanie własnymi [rolami](role-based-access-control.md) i [profilami](../configuration/device-profile-assign.md).
