---
ms.openlocfilehash: 76706fb39c3c5a69cba4fbf3f57c0b58d92e4a27
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67560012"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Wymagania dotyczące poświadczeń usług Azure AD i Intune

Uwierzytelnianie i autoryzacja są oparte na poświadczeniach usługi Azure AD i kontroli dostępu opartej na rolach (RBAC). Wszyscy administratorzy globalni i administratorzy usługi Intune dla dzierżawy domyślnie mają dostęp do magazynu danych. Przy użyciu ról usługi Intune możesz zapewnić dostęp dla większej liczby użytkowników, dając im dostęp do zasobu **magazynu danych usługi Intune**.

Wymagania dotyczące dostępu do magazynu danych usługi Intune (w tym interfejsu API) są następujące:

  - Użytkownik musi być:
      - administratorem globalnym usługi Azure AD,
      - administratorem usługi Intune,
      - użytkownikiem mającym oparty na roli dostęp do zasobu **magazynu danych usługi Intune**
      - Uwierzytelnianie bez użytkowników przy użyciu [uwierzytelniania tylko aplikacji](../data-warehouse-app-only-auth.md) 
