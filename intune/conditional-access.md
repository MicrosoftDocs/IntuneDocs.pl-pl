---
title: "Dostęp warunkowy przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Poznaj sposoby definiowania warunków, które muszą spełniać użytkownicy i urządzenia, aby uzyskać dostęp do zasobów firmy w usłudze Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1cd12a105142d5e537da487e3bd9297ef83ddcb3
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="whats-conditional-access"></a>Co to jest dostęp warunkowy?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W tym temacie opisano funkcję dostępu warunkowego stosowaną w pakiecie Enterprise Mobility + Security (EMS), a w dalszej kolejności wspólne scenariusze w zakresie dostępu warunkowego w usłudze Intune.

Dostęp warunkowy w pakiecie Enterprise Mobility + Security (EMS) nie jest produktem autonomicznym. Jest rozwiązaniem, które obejmuje wszystkie usługi i produkty będące częścią pakietu EMS. Zapewnia pełną kontrolę dostępu, co pozwala zabezpieczyć dane firmowe, udostępniając użytkownikom środowisko, które umożliwia wykonywanie pracy w najbardziej wydajny sposób na dowolnym urządzeniu i w dowolnym miejscu.

Można określić warunki, które blokują dostęp do danych firmowych na podstawie lokalizacji, urządzeń, stanu użytkownika i ważności aplikacji.

> [!NOTE] 
> Z możliwości dostępu warunkowego można również korzystać w [usługach Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Diagram architektury dostępu warunkowego](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Dostęp warunkowy przy użyciu usługi Intune

Usługa Intune dodaje zasady zgodności urządzeń przenośnych oraz zarządzania aplikacjami pozwalające obsługiwać rozwiązanie dostępu warunkowego w pakiecie EMS.

![Usługa Intune i dostęp warunkowy podczas korzystania z pakietu EMS](./media/intune-with-ca-1.png)

Sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune:

-   **Dostęp warunkowy oparty na urządzeniach**

    -   Dostęp warunkowy do lokalnego programu Exchange

    -   Dostęp warunkowy w oparciu o kontrolę dostępu do sieci

    -   Dostęp warunkowy w oparciu o ryzyko dotyczące urządzenia

    -   Dostęp warunkowy dla komputerów z systemem Windows

        -   Urządzenia należące do firmy

        -   „Przynieś własne urządzenie” (BYOD)

-   **Dostęp warunkowy na podstawie aplikacji**

## <a name="next-steps"></a>Następne kroki

[Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md)
