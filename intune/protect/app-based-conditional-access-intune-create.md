---
title: Konfigurowanie zasad dostępu warunkowego opartego na aplikacji w usłudze Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak utworzyć zasady dostępu warunkowego na podstawie aplikacji przy użyciu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9cbe57d0cf69f036cd36d2c1b95c48b198645e7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723089"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Konfigurowanie zasad dostępu warunkowego na podstawie aplikacji

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Skonfiguruj zasady dostępu warunkowego na podstawie aplikacji dla aplikacji znajdujących się na liście zatwierdzonych aplikacji. Lista zatwierdzonych aplikacji składa się z aplikacji, które zostały przetestowane przez firmę Microsoft.

> [!IMPORTANT]
> W tym artykule przedstawiono kroki dodawania zasad dostępu warunkowego opartego na aplikacji. Tych samych kroków można używać podczas dodawania aplikacji takich jak SharePoint Online, Microsoft Teams i Microsoft Exchange Online z listy zatwierdzonych aplikacji.

## <a name="create-app-based-conditional-access-policies"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji
Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure Active Directory (Azure AD). Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*. Oznacza to, że nie trzeba przełączać się między usługami Intune i Azure AD, aby skonfigurować zasady.

> [!IMPORTANT]
> Do utworzenia zasad dostępu warunkowego w portalu usługi Intune potrzebna jest licencja usługi Azure AD w wersji Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji

> [!IMPORTANT]
> Zanim zaczniesz korzystać z zasad dostępu warunkowego bazującego na aplikacjach, musisz do swoich aplikacji zastosować [zasady ochrony aplikacji usługi Intune](../apps/app-protection-policies.md).

1. Na **pulpicie nawigacyjnym usługi Intune** wybierz pozycję **Dostęp warunkowy**.

2. W okienku **Zasady** wybierz pozycję **Nowe zasady**, aby utworzyć nowe zasady dostępu warunkowego na podstawie aplikacji.

4. Po wprowadzeniu nazwy zasad i skonfigurowaniu ustawień dostępnych w sekcji **Przypisania** wybierz pozycję **Udziel** w sekcji **Kontrole dostępu**.

5. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**, wybierz pozycję **Wybierz**, a następnie wybierz pozycję **Utwórz** w celu zapisania nowych zasad.

## <a name="next-steps"></a>Następne kroki
[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](app-modern-authentication-block.md)

## <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji przy użyciu zasad ochrony aplikacji](../apps/app-protection-policies.md)
[Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
