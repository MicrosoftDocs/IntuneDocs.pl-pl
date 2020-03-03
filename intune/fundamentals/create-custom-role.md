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
ms.openlocfilehash: bfa2758546595d1e6237d88e128958c50759eb04
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569187"
---
# <a name="create-a-custom-role-in-intune"></a>Tworzenie roli niestandardowej w usłudze Intune

W usłudze Intune można utworzyć rolę niestandardową, która zawiera wszystkie uprawnienia wymagane dla funkcji określonego zadania. Na przykład jeśli grupa działu IT zarządza aplikacjami, zasadami i profilami konfiguracji, można dodać wszystkie te uprawnienia razem do jednej roli niestandardowej. Utworzoną rolę niestandardową można [przypisać](assign-role.md) do użytkowników, którzy potrzebują tych uprawnień.

Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
- **Administrator globalny**
- **Administrator usługi Intune**

## <a name="to-create-a-custom-role"></a>Aby utworzyć rolę niestandardową

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Administracja dzierżawą** > **Role** > **Wszystkie role** > **Utwórz**.

2. Na stronie **Podstawowe** wprowadź nazwę i opis dla nowej roli, a następnie wybierz pozycję **Dalej**.

3. Na stronie **Uprawnienia** wybierz uprawnienia do użycia w ramach tej roli.

4. Na stronie **Zakres (tagi)** wybierz tagi dla tej roli. Rola ta umożliwia dostęp do zasobów, które również mają te tagi. Wybierz pozycję **Next** (Dalej).

5. Na stronie **Przeglądanie + tworzenie** po zakończeniu wybierz pozycję **Utwórz**. Nowa rola zostanie wyświetlona na liście w bloku **Role usługi Intune — Wszystkie role**.

## <a name="copy-a-role"></a>Kopiowanie roli

Możesz też skopiować istniejącą rolę.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Administracja dzierżawą** > **Role** > **Wszystkie role** > zaznacz pole wyboru dla roli na liście > **Duplikuj**.

2. Na stronie **Podstawowe** wprowadź nazwę. Nazwa powinna być unikatowa.

3. Wszystkie uprawnienia i tagi zakresu z oryginalnej roli będą już zaznaczone. Następnie możesz zmienić zawartość pól **Nazwa**, **Opis**, **Uprawnienia** i **Zakres (tagi)** zduplikowanej roli.

4. Po wprowadzeniu wszystkich żądanych zmian wybierz pozycję **Dalej**, aby przejść do strony **Przeglądanie + tworzenie**. Wybierz przycisk **Utwórz**. 

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie roli do użytkownika](assign-role.md)
- [Dowiedz się więcej na temat kontroli dostępu opartej na rolach w usłudze Intune](role-based-access-control.md)


