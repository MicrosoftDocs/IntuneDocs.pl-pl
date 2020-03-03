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
ms.openlocfilehash: 19fff092f7eccfc6de2a027c7834c52698176cbf
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569170"
---
# <a name="assign-a-role-to-an-intune-user"></a>Przypisywanie roli do użytkownika usługi Intune

Do użytkownika usługi Intune możesz przypisać rolę [wbudowaną](role-based-access-control.md#built-in-roles) lub [niestandardową](create-custom-role.md).

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune**

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Administracja dzierżawą** > **Role** > **Wszystkie role**.

2. W bloku **Role usługi Intune — Wszystkie role** wybierz rolę wbudowaną, którą chcesz przypisać > **Przypisania** > **Przypisz**.

5. Na stronie **Podstawowe** uzupełnij pole **Nazwa przypisania** i opcjonalne pole **Opis przypisania**, a następnie wybierz pozycję **Dalej**.

6. Na stronie **Grupy administracyjne** wybierz grupę, do której należy użytkownik, któremu chcesz nadać uprawnienia. Wybierz pozycję **Dalej**.

7. Na stronie **Zakres (grupy)** wybierz grupę, do której należą użytkownicy/urządzenia, którymi będzie mógł zarządzać wskazany wcześniej członek. Wybierz pozycję **Next** (Dalej).

8. Na stronie **Zakres (tagi)** wybierz tagi, w których zostanie zastosowane to przypisanie roli. Wybierz pozycję **Next** (Dalej).

9. Na stronie **Przeglądanie + tworzenie** po zakończeniu wybierz pozycję **Utwórz**. Nowe przypisanie zostanie wyświetlone na liście przypisań.

## <a name="next-steps"></a>Następne kroki
- [Dowiedz się więcej na temat kontroli dostępu opartej na rolach w usłudze Intune](role-based-access-control.md)
- [Tworzenie roli niestandardowej](create-custom-role.md)


