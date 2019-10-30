---
title: Przypisywanie profili urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przypisz zasady i profile urządzeń do użytkowników i urządzeń za pomocą witryny Azure Portal. Dowiedz się, jak wykluczyć grupy z przypisania profilu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26ed23e4d9d267e37ba5088fa32234c27e3935b6
ms.sourcegitcommit: 9a2ddcec73b37a118908b63d8e5252835f257618
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2019
ms.locfileid: "72550808"
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

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile**. Zostanie wyświetlona lista wszystkich profilów.
3. Wybierz profil, który chcesz przypisać > **Przypisania**.
4. Wybierz **dołączenie** lub **wykluczenie** grup, a następnie wybierz grupy. Wybierane grupy są grupami usługi Azure AD. Aby wybrać wiele grup, możesz nacisnąć i przytrzymać klawisz **Ctrl**, a następnie wybrać grupy.

    ![Zrzut ekranu przedstawiający opcje dołączania grup do przypisania profilu i wykluczania grup z przypisania profilu](./media/device-profile-assign/group-include-exclude.png)

5. **Zapisz** zmiany.

### <a name="evaluate-how-many-users-are-targeted"></a>Ocenianie, ilu użytkowników jest uwzględnianych

Po przypisaniu tego profilu możesz również **ocenić**, ilu użytkowników jest uwzględnianych. Ta funkcja oblicza liczbę użytkowników; nie oblicza liczby urządzeń.

1. W usłudze Intune wybierz pozycję **Konfiguracja urządzeń** > **Profile**.
2. Wybierz profil > **Przypisania** > **Oceń**. Zostanie wyświetlony komunikat z informacją o liczbie użytkowników uwzględnionych w tym profilu.

Jeśli przycisk **Oceń** jest szary, upewnij się, że profil został przypisany do co najmniej jednej grupy.

## <a name="use-scope-tags-or-applicability-rules"></a>Używanie tagów zakresu lub reguł stosowania

Podczas tworzenia lub aktualizacji profilu możesz dodać do niego tagi zakresu i reguły stosowania.

**Tagi zakresu** to doskonały sposób przypisywania i filtrowania zasad do określonych grup, takich jak pracownicy działu kadr lub wszyscy pracownicy w stanie Północna Karolina w USA. Więcej informacji można znaleźć w artykule [Use RBAC and scope tags for distributed IT](../fundamentals/scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

Na urządzeniach z systemem Windows 10 możesz dodać **reguły stosowania**, aby profil był stosowany tylko do określonej wersji systemu operacyjnego lub określonego wydania systemu Windows. [Reguły stosowania](device-profile-create.md#applicability-rules) zawierają więcej informacji.

## <a name="exclude-groups-from-a-profile-assignment"></a>Wykluczanie grup z przypisania profilu

Profile konfiguracji urządzeń w usłudze Intune umożliwiają wykluczanie grup z przypisania zasad.

Usługa Intune nie sprawdza relacji między użytkownikami i grupami urządzeń. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń może nie przynieść oczekiwanych rezultatów. W scenariuszach „grupa użytkowników do grupy użytkowników” i „grupa urządzeń do grupy urządzeń” wykluczenia mają pierwszeństwo przed dołączaniem.

Załóżmy na przykład, że przypisano profil urządzenia do grupy użytkowników **Wszyscy użytkownicy firmowi**, ale z wykluczeniem członków grupy użytkowników **Wyższa kadra kierownicza**. Ponieważ obydwie grupy są grupami użytkowników, wszyscy członkowie grupy **Wyższa kadra kierownicza** są wykluczeni z tej zasady, mimo że są członkami grupy dołączania **Wszyscy użytkownicy firmowi**.

Dołączenie ma pierwszeństwo przed wykluczeniem w przypadku grup mieszanych, takich jak „grupa użytkowników do grupy urządzeń” lub „grupa urządzeń do grupy użytkowników”.

Załóżmy na przykład, że chcesz przypisać profil urządzenia do wszystkich użytkowników w organizacji z wyjątkiem kiosków. Musisz dołączyć grupę **Wszyscy użytkownicy**, ale wykluczyć grupę **Wszystkie urządzenia**. Zasady zostaną wtedy zastosowane do wszystkich użytkowników i ich urządzeń, nawet jeśli dane urządzenie użytkownika należy do grupy **Wszystkie urządzenia**.

Operacja wykluczenia uwzględnia tylko bezpośrednich członków grupy. Nie obejmuje urządzeń skojarzonych z użytkownikiem. Jednak urządzenia nieskojarzone z żadnym użytkownikiem nie otrzymają zasad. Dzieje się tak, ponieważ urządzenia bez użytkowników nie mają relacji z grupą **Wszyscy użytkownicy**.

Jeśli dołączysz grupę **Wszystkie urządzenia**, a wykluczysz grupę **Wszyscy użytkownicy**, zasady zostaną zastosowane do wszystkich urządzeń. W tym przypadku celem jest wykluczenie z zasad urządzeń, które są skojarzone z użytkownikami. Jednak urządzenia nie zostaną wykluczone, ponieważ funkcja wykluczania porównuje tylko członków grup.

## <a name="next-steps"></a>Następne kroki

Zobacz artykuł dotyczący [monitorowania profilów urządzeń](device-profile-monitor.md), aby uzyskać wskazówki dotyczące monitorowania profilów i urządzeń z uruchomionymi profilami.
