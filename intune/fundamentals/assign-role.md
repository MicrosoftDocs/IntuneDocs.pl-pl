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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 780a248f16a8a5028875c9c2401921ea23d0af24
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540932"
---
# <a name="assign-a-role-to-an-intune-user"></a>Przypisywanie roli do użytkownika usługi Intune

Do użytkownika usługi Intune możesz przypisać rolę [wbudowaną](role-based-access-control.md#built-in-roles) lub [niestandardową](create-custom-role.md).

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune**

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Administracja dzierżawą** > **Role** > **Wszystkie role**.

2. W bloku **Role usługi Intune — Wszystkie role** wybierz rolę wbudowaną, którą chcesz przypisać.

3. W bloku <*nazwa roli*> — **Przegląd** wybierz kolejno pozycje **Zarządzaj** > **Przypisania**.

4. W bloku roli niestandardowej wybierz pozycję **Przypisz**.

5. W bloku **Przypisania ról** wprowadź **nazwę przypisania** i opcjonalnie **opis przypisania** danego przypisania.

6. W obszarze **Członkowie (grupy)** wybierz grupę, do której należy użytkownik, któremu chcesz nadać uprawnienia.

7. W obszarze **Zakres (grupy)** wybierz grupę, do której należą użytkownicy/urządzenia, którymi będzie mógł zarządzać wskazany wcześniej członek.

8. W obszarze **Zakres (tagi)** wybierz tagi, w których zostanie zastosowane to przypisanie roli.

9. Gdy wszystko będzie gotowe, wybierz przycisk **OK**. Nowe przypisanie zostanie wyświetlone na liście przypisań.


## <a name="next-steps"></a>Następne kroki
- [Dowiedz się więcej na temat kontroli dostępu opartej na rolach w usłudze Intune](role-based-access-control.md)
- [Tworzenie roli niestandardowej](create-custom-role.md)
