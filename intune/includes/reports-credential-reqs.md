---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830504"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Wymagania dotyczące poświadczeń usług Azure AD i Intune

Uwierzytelnianie i autoryzacja są oparte na poświadczeniach usługi Azure AD i kontroli dostępu opartej na rolach (RBAC). Wszyscy administratorzy globalni i administratorzy usługi Intune dla dzierżawy domyślnie mają dostęp do magazynu danych. Przy użyciu ról usługi Intune możesz zapewnić dostęp dla większej liczby użytkowników, dając im dostęp do zasobu **magazynu danych usługi Intune**.

Wymagania dotyczące dostępu do magazynu danych usługi Intune (w tym interfejsu API) są następujące:

- Użytkownik musi być:
  - administratorem globalnym usługi Azure AD,
  - administratorem usługi Intune,
  - użytkownikiem mającym oparty na roli dostęp do zasobu **magazynu danych usługi Intune**
  - Uwierzytelnianie bez użytkowników przy użyciu [uwierzytelniania tylko aplikacji](../developer/data-warehouse-app-only-auth.md) 
