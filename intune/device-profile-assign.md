---
title: Przypisywanie profili urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przypisz zasady i profile urządzeń do użytkowników i urządzeń za pomocą witryny Azure Portal. Dowiedz się, jak wykluczyć grupy z przypisania profilu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c950efdd95fd8d856ec677385712a022dead870
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570510"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Przypisywanie profili użytkowników i urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tworzony przez Ciebie profil obejmuje wszystkie wprowadzone ustawienia. Następnym krokiem jest wdrożenie lub „przypisanie” profilu do grup użytkowników lub urządzeń usługi Azure Active Directory (Azure AD). Po przypisaniu użytkownicy i urządzenia otrzymują swój profil, a wprowadzone ustawienia są stosowane.

W tym artykule pokazano, jak przypisać profil, i przedstawiono niektóre informacje na temat używania tagów zakresu w profilach.

## <a name="assign-a-device-profile"></a>Przypisywanie profilu urządzenia

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile**. Zostanie wyświetlona lista wszystkich profilów.
3. Wybierz profil, który chcesz przypisać > **Przypisania**.
4. Wybierz **dołączenie** lub **wykluczenie** grup, a następnie wybierz grupy. Wybierane grupy są grupami usługi Azure AD. Aby wybrać wiele grup, możesz nacisnąć i przytrzymać klawisz **Ctrl**, a następnie wybrać grupy.

    ![Zrzut ekranu przedstawiający opcje dołączania grup do przypisania profilu i wykluczania grup z przypisania profilu](./media/group-include-exclude.png)

5. **Zapisz** zmiany.

### <a name="evaluate-how-many-users-are-targeted"></a>Ocenianie, ilu użytkowników jest uwzględnianych

Po przypisaniu tego profilu możesz również **ocenić**, ilu użytkowników jest uwzględnianych. Ta funkcja oblicza liczbę użytkowników; nie oblicza liczby urządzeń.

1. W usłudze Intune wybierz pozycję **Konfiguracja urządzeń** > **Profile**.
2. Wybierz profil > **Przypisania** > **Oceń**. Zostanie wyświetlony komunikat z informacją o liczbie użytkowników uwzględnionych w tym profilu.

Jeśli przycisk **Oceń** jest szary, upewnij się, że profil został przypisany do co najmniej jednej grupy.


## <a name="use-scope-tags"></a>Korzystanie z tagów zakresu

Podczas tworzenia lub aktualizacji profilu możesz dodać do niego tagi zakresu.

**Tagi zakresu** to doskonały sposób przypisywania i filtrowania zasad do określonych grup, takich jak pracownicy działu kadr lub wszyscy pracownicy w stanie Północna Karolina w USA. Więcej informacji można znaleźć w artykule [Use RBAC and scope tags for distributed IT](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

## <a name="exclude-groups-from-a-profile-assignment"></a>Wykluczanie grup z przypisania profilu

Profile konfiguracji urządzeń w usłudze Intune umożliwiają wykluczanie grup z przypisania zasad. Można na przykład przypisać profil urządzenia do grupy **Wszyscy użytkownicy firmowi**, ale z wykluczeniem członków grupy **Wyższa kadra kierownicza**.

W przypadku wykluczania grup, tylko użytkowników lub tylko grup urządzeń (a nie obu rodzajów grup) z przypisania usługa Intune nie uwzględnia relacji między użytkownikami a urządzeniami. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń może nie przynieść oczekiwanych rezultatów. Jeśli są używane mieszane grupy lub występują inne konflikty, operacja dołączania ma pierwszeństwo przed operacją wykluczania.

Możesz na przykład chcieć przypisać profil urządzenia do wszystkich urządzeń w organizacji z wyjątkiem kiosków. Musisz dołączyć grupę **Wszyscy użytkownicy**, ale wykluczyć grupę **Wszystkie urządzenia**. Zasady zostaną wtedy zastosowane do wszystkich użytkowników i ich urządzeń, nawet jeśli dane urządzenie użytkownika należy do grupy **Wszystkie urządzenia**.

Operacja wykluczenia uwzględnia tylko bezpośrednich członków grupy. Nie obejmuje urządzeń skojarzonych z użytkownikiem. Jednak urządzenia nieskojarzone z żadnym użytkownikiem nie otrzymają zasad. Dzieje się tak, ponieważ te urządzenia nie mają relacji z grupą **Wszyscy użytkownicy**.

Jeśli dołączysz grupę **Wszystkie urządzenia**, a wykluczysz grupę **Wszyscy użytkownicy**, zasady zostaną zastosowane do wszystkich urządzeń. W tym przypadku celem jest wykluczenie z zasad urządzeń, które są skojarzone z użytkownikami. Jednak urządzenia nie zostaną wykluczone, ponieważ funkcja wykluczania porównuje tylko członków grup.

## <a name="next-steps"></a>Następne kroki

Zobacz artykuł dotyczący [monitorowania profilów urządzeń](device-profile-monitor.md), aby uzyskać wskazówki dotyczące monitorowania profilów i urządzeń z uruchomionymi profilami.