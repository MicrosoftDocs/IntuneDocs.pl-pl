---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511344"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Wymagania dotyczące poświadczeń usług Azure AD i Intune

Uwierzytelnianie i autoryzacja są oparte na poświadczeniach usługi Azure AD i kontroli dostępu opartej na rolach (RBAC). Wszyscy administratorzy globalni i administratorzy usługi Intune dla dzierżawy domyślnie mają dostęp do magazynu danych. Przy użyciu ról usługi Intune możesz zapewnić dostęp dla większej liczby użytkowników, dając im dostęp do zasobu **magazynu danych usługi Intune**.

Wymagania dotyczące dostępu do magazynu danych usługi Intune (w tym interfejsu API) są następujące:

  -  Użytkownik musi być:
      -  administratorem globalnym usługi Azure AD,
      -  administratorem usługi Intune,
      -  użytkownikiem mającym oparty na roli dostęp do zasobu **magazynu danych usługi Intune**
      -  Uwierzytelnianie bez użytkowników przy użyciu [uwierzytelniania tylko aplikacji](../data-warehouse-app-only-auth.md) 
