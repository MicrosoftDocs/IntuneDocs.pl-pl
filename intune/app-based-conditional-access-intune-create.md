---
title: Konfigurowanie zasad dostępu warunkowego opartego na aplikacji w usłudze Intune
titlesuffix: Microsoft Intune
description: Dowiedz się, jak utworzyć zasady dostępu warunkowego na podstawie aplikacji przy użyciu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 079671064c09c22d151ea71f8b3fb385652aef0f
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816926"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Konfigurowanie zasad dostępu warunkowego na podstawie aplikacji

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Skonfiguruj zasady dostępu warunkowego na podstawie aplikacji dla aplikacji znajdujących się na liście zatwierdzonych aplikacji. Lista zatwierdzonych aplikacji składa się z aplikacji, które zostały przetestowane przez firmę Microsoft.

> [!IMPORTANT]
> W tym artykule przedstawiono kroki dodawania zasad dostępu warunkowego opartego na aplikacji. Tych samych kroków można używać podczas dodawania aplikacji takich jak SharePoint Online, Microsoft Teams i Microsoft Exchange Online z listy zatwierdzonych aplikacji.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Tworzenie zasad dostępu warunkowego bazujących na aplikacjach w obciążeniu usługi Azure AD

Administratorzy mogą tworzyć zasady dostępu warunkowego opartego na aplikacjach z obciążenia usługi Azure AD. Dzięki temu nie trzeba przełączać się między obciążeniami platformy Azure i usługi Intune.

> [!IMPORTANT]
> Aby utworzyć zasady dostępu warunkowego usługi Azure AD w portalu Intune Azure, potrzebna jest licencja usługi Azure AD w wersji Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji

> [!IMPORTANT]
> Zanim zaczniesz korzystać z zasad dostępu warunkowego bazującego na aplikacjach, musisz do swoich aplikacji zastosować [zasady ochrony aplikacji usługi Intune](app-protection-policies.md).

1. Na **pulpicie nawigacyjnym Intune** wybierz pozycję **Dostęp warunkowy**.

2. W okienku **Zasady** wybierz pozycję **Nowe zasady**, aby utworzyć nowe zasady dostępu warunkowego na podstawie aplikacji.

4. Po wprowadzeniu nazwy zasad i skonfigurowaniu ustawień dostępnych w sekcji **Przypisania** wybierz pozycję **Udziel** w sekcji **Kontrole dostępu**.

5. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**, wybierz pozycję **Wybierz**, a następnie wybierz pozycję **Utwórz** w celu zapisania nowych zasad.

## <a name="next-steps"></a>Następne kroki
[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](app-modern-authentication-block.md)

### <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji przy użyciu zasad ochrony aplikacji](app-protection-policies.md)
[Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
