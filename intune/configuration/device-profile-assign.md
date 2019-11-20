---
title: Przypisywanie profili urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przypisz zasady i profile urządzeń do użytkowników i urządzeń za pomocą witryny Azure Portal. Dowiedz się, jak wykluczyć grupy z przypisania profilu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae8bc7d5797a2ba6404331166e9d955bbb2fadf9
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059578"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Przypisywanie profili użytkowników i urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tworzony przez Ciebie profil obejmuje wszystkie wprowadzone ustawienia. Następnym krokiem jest wdrożenie lub „przypisanie” profilu do grup użytkowników lub urządzeń usługi Azure Active Directory (Azure AD). Po przypisaniu użytkownicy i urządzenia otrzymują swój profil, a wprowadzone ustawienia są stosowane.

W tym artykule pokazano, jak przypisać profil, i przedstawiono niektóre informacje na temat używania tagów zakresu w profilach.

> [!NOTE]  
> Gdy zasady zostaną usunięte lub nie będą już przypisane do urządzenia, ustawienie może zachować istniejącą wartość. Ustawienie nie zostanie przywrócone do wartości domyślnej. Aby zmienić ustawienie na inną wartość, utwórz nowe zasady i przypisz je.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Upewnij się, że masz odpowiednią rolę do przypisywania zasad. Aby uzyskać więcej informacji, zobacz [Kontrola dostępu oparta na rolach (RBAC) w usłudze Microsoft Intune](../fundamentals/role-based-access-control.md).

## <a name="assign-a-device-profile"></a>Przypisywanie profilu urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji**. Zostanie wyświetlona lista wszystkich profilów.
3. Wybierz profil, który chcesz przypisać > **Przypisania**.
4. Wybierz **dołączenie** lub **wykluczenie** grup, a następnie wybierz grupy. Wybierane grupy są grupami usługi Azure AD. Aby wybrać wiele grup, możesz nacisnąć i przytrzymać klawisz **Ctrl**, a następnie wybrać grupy.

    ![Zrzut ekranu przedstawiający opcje dołączania grup do przypisania profilu i wykluczania grup z przypisania profilu](./media/device-profile-assign/group-include-exclude.png)

5. **Zapisz** zmiany.

### <a name="evaluate-how-many-users-are-targeted"></a>Ocenianie, ilu użytkowników jest uwzględnianych

Po przypisaniu tego profilu możesz również **ocenić**, ilu użytkowników jest uwzględnianych. Ta funkcja oblicza liczbę użytkowników; nie oblicza liczby urządzeń.

1. W centrum administracyjnym wybierz pozycję **Urządzenia** > **Profile konfiguracji**.
2. Wybierz profil > **Przypisania** > **Oceń**. Zostanie wyświetlony komunikat z informacją o liczbie użytkowników uwzględnionych w tym profilu.

Jeśli przycisk **Oceń** jest szary, upewnij się, że profil został przypisany do co najmniej jednej grupy.

## <a name="use-scope-tags-or-applicability-rules"></a>Używanie tagów zakresu lub reguł stosowania

Podczas tworzenia lub aktualizacji profilu możesz dodać do niego tagi zakresu i reguły stosowania.

**Tagi zakresu** to doskonały sposób przypisywania i filtrowania zasad do określonych grup, takich jak pracownicy działu kadr lub wszyscy pracownicy w stanie Północna Karolina w USA. Więcej informacji można znaleźć w artykule [Use RBAC and scope tags for distributed IT](../fundamentals/scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

Na urządzeniach z systemem Windows 10 możesz dodać **reguły stosowania**, aby profil był stosowany tylko do określonej wersji systemu operacyjnego lub określonego wydania systemu Windows. [Reguły stosowania](device-profile-create.md#applicability-rules) zawierają więcej informacji.

## <a name="exclude-groups-from-a-profile-assignment"></a>Wykluczanie grup z przypisania profilu

Profile konfiguracji urządzeń w usłudze Intune umożliwiają dołączanie i wykluczanie grup z przypisania zasad.

Najlepszym rozwiązaniem jest utworzenie i przypisanie zasad przeznaczonych specjalnie dla grup użytkowników. Ponadto należy utworzyć i przypisać różne zasady przeznaczone specjalnie dla grup urządzeń. Aby uzyskać więcej informacji na temat grup, zobacz [Dodawanie grup w celu organizowania użytkowników i urządzeń](../fundamentals/groups-add.md).

W przypadku przypisywania zasad skorzystaj z poniższej tabeli podczas dołączania i wykluczania grup. Znacznik wyboru oznacza, że przypisanie jest obsługiwane:

![Obsługiwane opcje dołączają grupy do przypisania profilu lub wykluczają grupy z przypisania profilu](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>Co należy wiedzieć

- Wykluczenie ma pierwszeństwo przed dołączeniem w następujących scenariuszach tego samego typu grupy:

  - Dołączanie grup użytkowników i wykluczanie grup użytkowników
  - Dołączanie grup urządzeń i wykluczanie grup urządzeń

  Załóżmy na przykład, że przypisano profil urządzenia do grupy użytkowników **Wszyscy użytkownicy firmowi**, ale z wykluczeniem członków grupy użytkowników **Wyższa kadra kierownicza**. Ponieważ obie grupy są grupami użytkowników, zasady otrzymają **wszyscy użytkownicy firmowi** z wyjątkiem **starszej kadry kierowniczej**.

- Usługa Intune nie ocenia relacji między użytkownikami i grupami urządzeń. Jeśli przypiszesz zasady do grup mieszanych, wyniki mogą być niezgodne z oczekiwaniami.

  Przypiszesz na przykład profil urządzenia do grupy użytkowników **Wszyscy użytkownicy**, ale wykluczysz grupę urządzeń **Wszystkie urządzenia osobiste**. W tym mieszanym przypisaniu zasad grupy zasady otrzyma grupa **Wszyscy użytkownicy**. Wykluczenie nie ma zastosowania.

  W związku z tym nie zaleca się przypisywania zasad do grup mieszanych.

## <a name="next-steps"></a>Następne kroki

Zobacz artykuł dotyczący [monitorowania profilów urządzeń](device-profile-monitor.md), aby uzyskać wskazówki dotyczące monitorowania profilów i urządzeń z uruchomionymi profilami.
