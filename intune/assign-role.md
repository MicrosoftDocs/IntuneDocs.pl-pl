---
title: Przypisywanie roli do użytkownika usługi Intune
description: Dowiedz się, jak przypisać rolę wbudowaną lub niestandardową do użytkownika w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a22fef1c04ae52a8a4cc65eaadc1ef6fcd524c19
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043590"
---
# <a name="assign-a-role-to-an-intune-user"></a>Przypisywanie roli do użytkownika usługi Intune

Do użytkownika usługi Intune możesz przypisać rolę [wbudowaną](role-based-access-control.md#built-in-roles) lub [niestandardową](create-custom-role.md).

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune**

Aby uzyskać pełną listę uprawnień dla poszczególnych ról wbudowanych, zobacz [Tabela kontroli RBAC przy użyciu usługi Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).

2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.

3. W bloku **Intune** wybierz pozycję **Role** > **Wszystkie role**.

4. W bloku **Role usługi Intune — Wszystkie role** wybierz rolę wbudowaną, którą chcesz przypisać.

5. W bloku <*nazwa roli*> — **Przegląd** wybierz kolejno pozycje **Zarządzaj** > **Przypisania**.

6. W bloku roli niestandardowej wybierz pozycję **Przypisz**.

7. W bloku **Przypisania ról** wprowadź **nazwę przypisania** i opcjonalnie **opis przypisania** danego przypisania.

8. W obszarze **Członkowie (grupy)** wybierz grupę, do której należy użytkownik, któremu chcesz nadać uprawnienia.

9. W obszarze **Zakres (grupy)** wybierz grupę, do której należą użytkownicy/urządzenia, którymi będzie mógł zarządzać wskazany wcześniej członek.

10. W obszarze **Zakres (tagi)** wybierz tagi, w których zostanie zastosowane to przypisanie roli.

11. Gdy wszystko będzie gotowe, wybierz przycisk **OK**. Nowe przypisanie zostanie wyświetlone na liście przypisań.


## <a name="next-steps"></a>Następne kroki
- [Dowiedz się więcej na temat kontroli dostępu opartej na rolach w usłudze Intune](role-based-access-control.md)
- [Tworzenie roli niestandardowej](create-custom-role.md)
