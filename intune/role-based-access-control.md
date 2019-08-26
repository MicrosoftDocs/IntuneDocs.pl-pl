---
title: Kontrola dostępu oparta na rolach (RBAC) w usłudze Microsoft Intune
description: Dowiedz się, jak kontrola dostępu oparta na rolach pozwala określić, kto może wykonywać akcje i wprowadzać zmiany w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83b1de6c246baaef54a31c0b3f4c5094d066c64d
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "69549964"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Kontrola dostępu oparta na rolach (RBAC) w usłudze Microsoft Intune

Kontrola dostępu oparta na rolach (RBAC) ułatwia zarządzanie osobami mającymi dostęp do zasobów organizacji i czynnościami, które mogą one wykonywać na tych zasobach.  Aby ograniczyć elementy, które mogą widzieć i zmieniać użytkownicy usługi Intune, należy im [przypisać role](assign-role.md). Każda rola ma zestaw uprawnień, które określają, do jakich elementów mają dostęp użytkownicy z taką rolą i jakie zmiany mogą wprowadzać w ramach organizacji.

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune** (znany także jako **administrator Intune**)

Porady i sugestie dotyczące kontroli RBAC usługi Intune możesz znaleźć w tej serii pięciu filmów wideo, które zawierają przykłady i przewodniki: [1](https://www.youtube.com/watch?v=5deXLMLcnKY), [2](https://www.youtube.com/watch?v=38dnMBLuxbQ), [3](https://www.youtube.com/watch?v=6vqg9cAkMbY), [4](https://www.youtube.com/watch?v=5yOLajFFMHE), [5](https://www.youtube.com/watch?v=P5DDvsSF4Wk).

## <a name="roles"></a>Role
Rola definiuje zestaw uprawnień przyznawanych dla użytkowników przypisanych do tej roli.
Możesz używać zarówno ról wbudowanych, jak i niestandardowych. Role wbudowane sprawdzają się dobrze w typowych scenariuszach usługi Intune. Możesz też [tworzyć własne role niestandardowe](create-custom-role.md) z dokładnym zestawem wymaganych uprawnień. Niektóre role usługi Azure Active Directory mają uprawnienia usługi Intune.
Aby wyświetlić rolę, wybierz pozycję **Intune** > **Role** > **Wszystkie role** i wybierz konkretną rolę. Zostaną wyświetlone następujące strony:

- **Właściwości**: nazwa roli, jej opis, typ, przypisania i tagi zakresu. 
- **Uprawnienia**: długa lista przełączników definiujących uprawnienia, jakie ma rola.
- **Przypisania**: lista [przypisań ról]( assign-role.md) określających, którzy użytkownicy mają dostęp do konkretnych użytkowników/urządzeń. Rola może mieć wiele przypisań, a użytkownik może występować w wielu przypisaniach.

### <a name="built-in-roles"></a>Wbudowane role
Wbudowane role można przypisywać do grup bez konieczności dalszej konfiguracji. Nie można usuwać ani edytować nazwy, opisu, typu ani uprawnień roli wbudowanej. Aby uzyskać pełną listę uprawnień dla poszczególnych ról wbudowanych, zobacz [Tabela kontroli RBAC przy użyciu usługi Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

- **Pracownik punktu pomocy**: wykonuje zadania zdalne na użytkownikach i urządzeniach i może przypisywać aplikacje lub zasady do użytkowników lub urządzeń.
- **Menedżer zasad i profilów**: zarządza zasadami zgodności, profilami konfiguracji, rejestracją Apple, identyfikatorami urządzeń firmowych oraz punktami odniesienia zabezpieczeń.
- **Operator tylko do odczytu**: wyświetla informacje o użytkownikach, urządzeniach, rejestracji, konfiguracji i aplikacji. Nie można wprowadzać zmian w usłudze Intune.
- **Menedżer aplikacji**: zarządza aplikacjami mobilnymi i zarządzanymi, może odczytywać informacje o urządzeniu i może wyświetlać profile konfiguracji urządzeń.
- **Administrator ról usługi Intune**: zarządza niestandardowymi rolami usługi Intune i dodaje przypisania dla wbudowanych ról usługi Intune. Jest to jedyna rola usługi Intune, która może przypisywać uprawnienia administratorom.
- **Administrator szkoły**: zarządza urządzeniami z systemem Windows 10 w usłudze [Intune for Education](introduction-intune-education.md).

### <a name="custom-roles"></a>Role niestandardowe
Istnieje możliwość utworzenia własnych ról z niestandardowymi uprawnieniami. Więcej informacji o niestandardowych rolach znajduje się w sekcji [Tworzenie roli niestandardowej](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Role usługi Azure Active Directory z dostępem do usługi Intune
| Rola usługi Azure Active Directory | Wszystkie dane usługi Intune | Dane inspekcji usługi Intune |
| --- | :---: | :---: |
| Administrator globalny | Odczyt/zapis | Odczyt/zapis |
| Administrator usługi Intune | Odczyt/zapis | Odczyt/zapis |
| Administrator dostępu warunkowego | Brak | Brak |
| Administrator zabezpieczeń | Tylko do odczytu | Tylko do odczytu |
| Operator zabezpieczeń | Tylko do odczytu | Tylko do odczytu |
| Czytelnik zabezpieczeń | Tylko do odczytu | Tylko do odczytu |
| Administrator zgodności | Brak | Tylko do odczytu |
| Administrator danych zgodności | Brak | Tylko do odczytu |

> [!TIP]
> Usługa Intune wyświetla również trzy rozszerzenia usługi Azure AD: **Użytkownicy**, **Grupy** oraz **Dostęp warunkowy**, które są kontrolowane za pomocą usługi Azure AD RBAC. Ponadto **Administrator konta użytkownika** wykonuje tylko działania użytkownika/grupy usługi AAD i nie ma pełnych uprawnień do wykonywania wszystkich działań w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Kontrola RBAC w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).
### <a name="roles-created-in-the-intune-classic-portal"></a>Role utworzone w portalu klasycznym usługi Intune
Tylko użytkownicy usługi Intune **Administratorzy usługi** z pełnymi uprawnieniami są migrowani z portalu klasycznego usługi Intune do usługi Intune w witrynie Azure Portal. Musisz ponownie przypisać użytkowników usługi Intune z rolą **Administratorzy usługi** z dostępem „Tylko do odczytu” lub „Pomoc techniczna” do ról usługi Intune w witrynie Azure Portal i usunąć ich z portalu klasycznego.
> [!IMPORTANT]
> Może być konieczne zachowanie dostępu Administratora usługi Intune w portalu klasycznym, jeśli administratorzy będą nadal potrzebować dostępu do zarządzania komputerami przy użyciu usługi Intune.

## <a name="role-assignments"></a>Przypisania ról
Przypisanie roli definiuje:

- którzy użytkownicy są przypisani do roli,
- jakie zasoby są dla nich widoczne,
- jakie zasoby mogą zmieniać.

Do użytkowników można przypisywać zarówno role niestandardowe, jak i wbudowane. Aby mieć przypisaną rolę usługi Intune, użytkownik musi mieć licencję usługi Intune.
Aby wyświetlić przypisanie roli, wybierz pozycję **Intune** > **Role** > **Wszystkie role**, a następnie wybierz rolę i przypisanie. Zostaną wyświetlone następujące strony:

- **Właściwości**: nazwa przypisania, jego opis, rola, członkowie, zakresy i tagi.
- **Elementy członkowskie**: wszyscy użytkownicy w wyświetlonych grupach zabezpieczeń platformy Azure mają uprawnienie do zarządzania użytkownikami/urządzeniami, które są wymienione w obszarze Zakres (grupy).
- **Zakres (grupy)** : wszyscy użytkownicy i wszystkie urządzenia w ramach tych grup zabezpieczeń platformy mogą być zarządzane przez użytkowników wymienionych w obszarze Członkowie.
- **[Zakres (tagi)](scope-tags.md)** : użytkownicy wymienieni w obszarze Członkowie mogą wyświetlać zasoby mające te same tagi zakresu.

### <a name="multiple-role-assignments"></a>Przypisania wielu ról
Jeśli użytkownik ma wiele przypisań ról, uprawnienia i tagi zakresu w ramach tych przypisań ról mają wpływ na różne obiekty w następujący sposób:

- Przypisane uprawnienia i tagi zakresu mają zastosowanie tylko do obiektów (takich jak zasady lub aplikacje) będących w zakresie (grupach) tego przypisania roli. Przypisane uprawnienia i tagi zakresu nie mają zastosowania do obiektów znajdujących się w innych przypisaniach ról, chyba że inne przypisania jawnie je nadają.
- Inne uprawnienia (np. do tworzenia, odczytu, aktualizacji, usuwania) i tagi zakresu mają zastosowanie do wszystkich obiektów tego samego typu (na przykład do wszystkich zasad lub wszystkich aplikacji) we wszystkich przypisaniach użytkownika.
- Uprawnienia do obiektów różnych typów (na przykład do zasad lub aplikacji) i odpowiednie tagi zakresu nie mają zastosowania do siebie nawzajem. Na przykład uprawnienie do odczytu dla zasad nie zapewnia uprawnienia do odczytu dla aplikacji w przypisaniach użytkownika.

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie roli do użytkownika](assign-role.md)
- [Tworzenie roli niestandardowej](create-custom-role.md)
