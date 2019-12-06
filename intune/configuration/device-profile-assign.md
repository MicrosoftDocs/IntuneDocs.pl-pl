---
title: Przypisywanie profili urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przypisz zasady i profile urządzeń do użytkowników i urządzeń za pomocą witryny Azure Portal. Dowiedz się, jak wykluczyć grupy z przypisania profilu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2019
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
ms.openlocfilehash: 275b3961e87f0d0eda8299337fe3fb7ac89ef03b
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2019
ms.locfileid: "74261686"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Przypisywanie profili użytkowników i urządzeń w usłudze Microsoft Intune

Tworzony przez Ciebie profil obejmuje wszystkie wprowadzone ustawienia. Następnym krokiem jest wdrożenie lub „przypisanie” profilu do grup użytkowników lub urządzeń usługi Azure Active Directory (Azure AD). Po przypisaniu użytkownicy i urządzenia otrzymują swój profil, a wprowadzone ustawienia są stosowane.

W tym artykule pokazano, jak przypisać profil, i przedstawiono niektóre informacje na temat używania tagów zakresu w profilach.

> [!NOTE]  
> Po usunięciu profilu lub gdy nie jest on już przypisany do urządzenia, ustawienie może zachować istniejącą wartość. Ustawienie nie zostanie przywrócone do wartości domyślnej. Aby zmienić ustawienie na inną wartość, utwórz nowy profil i przypisz go.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Upewnij się, że masz rolę umożliwiającą przypisywanie profilów. Aby uzyskać więcej informacji, zobacz [Kontrola dostępu oparta na rolach (RBAC) w usłudze Microsoft Intune](../fundamentals/role-based-access-control.md).

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

**Tagi zakresu** to doskonały sposób przypisywania i filtrowania profilów do określonych grup, takich jak pracownicy działu kadr lub wszyscy pracownicy w stanie Północna Karolina w USA. Więcej informacji można znaleźć w artykule [Use RBAC and scope tags for distributed IT](../fundamentals/scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

Na urządzeniach z systemem Windows 10 możesz dodać **reguły stosowania**, aby profil był stosowany tylko do określonej wersji systemu operacyjnego lub określonego wydania systemu Windows. [Reguły stosowania](device-profile-create.md#applicability-rules) zawierają więcej informacji.

## <a name="user-groups-vs-device-groups"></a>Grupy użytkowników a grupy urządzeń

Wielu użytkowników pyta, kiedy używać grup użytkowników, a kiedy grup urządzeń. Odpowiedź zależy od tego, co jest nam potrzebne. Oto kilka wskazówek na początek.

### <a name="device-groups"></a>Grupy urządzeń

Jeśli chcesz stosować ustawienia do urządzenia niezależnie od tego, kto się do niego zalogował, przypisz profil do grupy urządzeń. Ustawienia przypisane do grupy urządzeń są zawsze związane z urządzeniem, nie z użytkownikiem.

Przykład:

- Grupy urządzeń nadają się do zarządzania urządzeniami niemającymi dedykowanych użytkowników. Na przykład metkownice i urządzenia skanujące zapasy magazynowe są używane przez wielu zmieniających się użytkowników i przypisane do konkretnego magazynu. Należy je zebrać w grupę urządzeń i przypisać profil do tej grupy.

- Tworzysz [profil interfejsu komunikacji oprogramowania układowego urządzenia (DFCI) usługi Intune ](device-firmware-configuration-interface-windows.md) uaktualniający ustawienia systemu BIOS. Na przykład konfigurujesz ten profil do wyłączenia kamery urządzenia lub opcji rozruchu umożliwiających użytkownikom uruchomienie innego systemu operacyjnego. To dobry przykład profilu do przypisania do grupy urządzeń.

- Na pewnych konkretnych urządzeniach z systemem Windows chcesz zawsze sprawować kontrolę nad niektórymi ustawieniami programu Microsoft Edge — niezależnie od tego, kto używa urządzenia. Na przykład chcesz zablokować możliwość pobierania, ograniczyć pliki cookie do bieżącej sesji przeglądania i usunąć historię przeglądania. Określone urządzenia z systemem Windows należy w ramach tego scenariusza umieścić w grupie urządzeń. Następnie utwórz [szablon administracyjny usługi Intune](administrative-templates-windows.md), dodaj powyższe ustawienia urządzenia, po czym przypisz profil do grupy urządzeń.

Podsumowując: z grup urządzeń należy korzystać wtedy, gdy nie ma znaczenia, kto (i czy w ogóle ktokolwiek) zalogował się na urządzeniu. Chcesz, aby ustawienia zawsze były obecne na urządzeniu.

### <a name="user-groups"></a>Grupy użytkowników

Ustawienia profilu stosowane do grup użytkowników są zawsze powiązane z użytkownikiem i przechodzą wraz z nim na kolejne urządzenia, na których się loguje. Użytkownicy często mają kilka urządzeń — np. służbowy notebook Surface Pro i prywatne urządzenie z systemem iOS. Jest też zrozumiałe, że uzyskują dostęp do poczty e-mail i innych zasobów organizacji na wszystkich tych urządzeniach.

Przykład:

- Chcesz umieścić ikonę pomocy technicznej dla wszystkich użytkowników na wszystkich ich urządzeniach. W tym scenariuszu należy umieścić tych użytkowników w grupie użytkowników i przypisać profil ikony pomocy technicznej do tej grupy.
- Użytkownik otrzymuje nowe urządzenie należące do organizacji. Użytkownik loguje się na urządzeniu przy użyciu konta domeny. Urządzenie jest automatycznie rejestrowane w usłudze Azure AD i automatycznie zarządzane przez usługę Intune. To dobry przykład profilu do przypisania do grupy użytkowników.
- Za każdym razem, gdy użytkownik loguje się do urządzenia, chcemy kontrolować funkcje w aplikacjach, takich jak OneDrive lub Office. W tym scenariuszu należy przypisać ustawienia profilu usługi OneDrive lub pakietu Office do grupy użytkowników.

  Na przykład chcesz zablokować niezaufane kontrolki ActiveX w aplikacjach pakietu Office. Możesz utworzyć [szablon administracyjny usługi Intune](administrative-templates-windows.md), dodać to ustawienie urządzenia, po czym przypisać profil do grupy urządzeń.

Podsumowując: z grup użytkowników należy korzystać wówczas, gdy ustawienia i reguły mają zawsze być związane z użytkownikiem, niezależnie od używanego przezeń urządzenia.

## <a name="exclude-groups-from-a-profile-assignment"></a>Wykluczanie grup z przypisania profilu

Profile konfiguracji urządzeń w usłudze Intune umożliwiają dołączanie i wykluczanie grup z przypisania profilów.

Najlepszym rozwiązaniem jest utworzenie i przypisanie profilów przeznaczonych specjalnie dla grup użytkowników. Ponadto należy utworzyć i przypisać różne profile przeznaczone specjalnie dla grup urządzeń. Aby uzyskać więcej informacji na temat grup, zobacz [Dodawanie grup w celu organizowania użytkowników i urządzeń](../fundamentals/groups-add.md).

W przypadku przypisywania profilów skorzystaj z poniższej tabeli podczas dołączania i wykluczania grup. Znacznik wyboru oznacza, że przypisanie jest obsługiwane:

![Obsługiwane opcje dołączają grupy do przypisania profilu lub wykluczają grupy z przypisania profilu](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>Co należy wiedzieć

- Wykluczenie ma pierwszeństwo przed dołączeniem w następujących scenariuszach tego samego typu grupy:

  - Dołączanie grup użytkowników i wykluczanie grup użytkowników
  - Dołączanie grup urządzeń i wykluczanie grup urządzeń

  Załóżmy na przykład, że przypisano profil urządzenia do grupy użytkowników **Wszyscy użytkownicy firmowi**, ale z wykluczeniem członków grupy użytkowników **Wyższa kadra kierownicza**. Ponieważ obie grupy są grupami użytkowników, zasady otrzymają **wszyscy użytkownicy firmowi** z wyjątkiem **wyższej kadry kierowniczej**.

- Usługa Intune nie ocenia relacji między użytkownikami i grupami urządzeń. Jeśli przypiszesz profile do grup mieszanych, wyniki mogą być niezgodne z oczekiwaniami.

  Przypiszesz na przykład profil urządzenia do grupy użytkowników **Wszyscy użytkownicy**, ale wykluczysz grupę urządzeń **Wszystkie urządzenia osobiste**. W przypadku tego przypisania profilu do grupy mieszanej profil otrzyma grupa **Wszyscy użytkownicy**. Wykluczenie nie ma zastosowania.

  W związku z tym nie zaleca się przypisywania profilów do grup mieszanych.

## <a name="next-steps"></a>Następne kroki

Zobacz artykuł dotyczący [monitorowania profilów urządzeń](device-profile-monitor.md), aby uzyskać wskazówki dotyczące monitorowania profilów i urządzeń z uruchomionymi profilami.
