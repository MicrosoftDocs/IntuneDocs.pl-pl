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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68c2dc7df123593513c14e16e2626c7426f50b01
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207421"
---
# <a name="create-a-custom-role-in-intune"></a>Tworzenie roli niestandardowej w usłudze Intune

W usłudze Intune można utworzyć rolę niestandardową, która zawiera wszystkie uprawnienia wymagane dla funkcji określonego zadania. Na przykład jeśli grupa działu IT zarządza aplikacjami, zasadami i profilami konfiguracji, można dodać wszystkie te uprawnienia razem do jednej roli niestandardowej. Utworzoną rolę niestandardową można [przypisać](assign-role.md) do użytkowników, którzy potrzebują tych uprawnień.

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune**

## <a name="to-create-a-custom-role"></a>Aby utworzyć rolę niestandardową

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Role** > **Wszystkie role** > **Dodaj**.

2. W bloku **Dodaj rolę niestandardową** wprowadź nazwę i opis nowej roli, a następnie kliknij pozycję **Uprawnienia**.

3. W bloku **Uprawnienia** wybierz uprawnienia do użycia w ramach tej roli.

4. W bloku **Zakres (tagi)** wybierz tagi dla tej roli. Rola ta umożliwia dostęp do zasobów, które również mają te tagi.

5. Gdy wszystko będzie gotowe, wybierz przycisk **OK**.

6. W bloku **Dodaj rolę niestandardową** kliknij pozycję **Utwórz**. Nowa rola zostanie wyświetlona na liście w bloku **Role usługi Intune — Wszystkie role**.


## <a name="copy-a-role"></a>Kopiowanie roli

Możesz też skopiować istniejącą rolę.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Role** > **Wszystkie role** > wybierz rolę z listy > **Duplikuj**.

2. W obszarze **Zduplikowana rola** wprowadź nazwę. Nazwa powinna być unikatowa.

3. Wszystkie uprawnienia i tagi zakresu z oryginalnej roli będą już zaznaczone. Następnie możesz zmienić zawartość pól **Nazwa**, **Opis**, **Uprawnienia** i **Zakres (tagi)** zduplikowanej roli.

4. Wybierz przycisk **Utwórz**. 

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie roli do użytkownika](assign-role.md)
- [Dowiedz się więcej na temat kontroli dostępu opartej na rolach w usłudze Intune](role-based-access-control.md)
