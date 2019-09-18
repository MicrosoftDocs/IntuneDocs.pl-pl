---
title: Tworzenie roli niestandardowej w usłudze Intune
description: Dowiedz się, jak utworzyć rolę niestandardową w usłudze Microsoft Intune.
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
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 10366a41be05dbedee5cd84a1222a727a02a1b93
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071479"
---
# <a name="create-a-custom-role-in-intune"></a>Tworzenie roli niestandardowej w usłudze Intune

W usłudze Intune można utworzyć rolę niestandardową, która zawiera wszystkie uprawnienia wymagane dla funkcji określonego zadania. Na przykład jeśli grupa działu IT zarządza aplikacjami, zasadami i profilami konfiguracji, można dodać wszystkie te uprawnienia razem do jednej roli niestandardowej. Utworzoną rolę niestandardową można [przypisać](assign-role.md) do użytkowników, którzy potrzebują tych uprawnień.

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune**

## <a name="to-create-a-custom-role"></a>Aby utworzyć rolę niestandardową

1. Zaloguj się do [witryny Azure Portal](https://portal.azure.com) przy użyciu poświadczeń usługi Intune.

2. W menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3. Wybierz pozycję **Intune** > **Role** > **Wszystkie role** > **Dodaj**.

4. W bloku **Dodaj rolę niestandardową** wprowadź nazwę i opis nowej roli, a następnie kliknij pozycję **Uprawnienia**.

5. W bloku **Uprawnienia** wybierz uprawnienia do użycia w ramach tej roli. Użyj [tabeli Intune RBAC](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) aby określić uprawnienia, które chcesz zastosować.

6. W bloku **Zakres (tagi)** wybierz tagi dla tej roli. Rola ta umożliwia dostęp do zasobów, które również mają te tagi.

7. Gdy wszystko będzie gotowe, wybierz przycisk **OK**.

8. W bloku **Dodaj rolę niestandardową** kliknij pozycję **Utwórz**. Nowa rola zostanie wyświetlona na liście w bloku **Role usługi Intune — Wszystkie role**.

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie roli do użytkownika](assign-role.md)
- [Dowiedz się więcej na temat kontroli dostępu opartej na rolach w usłudze Intune](role-based-access-control.md)
