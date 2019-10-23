---
title: Dostęp warunkowy w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak definiować warunki, które muszą spełniać użytkownicy, urządzenia i aplikacje, aby uzyskać dostęp do zasobów firmy w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb9dd31c87d27ec7885d25269988cfd968e81e08
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504566"
---
# <a name="learn-about-conditional-access-and-intune"></a>Więcej informacji na temat dostępu warunkowego i usługi Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dostęp warunkowy dotyczy sposobów kontrolowania urządzeń i aplikacji, które mogą nawiązywać połączenie z pocztą e-mail i zasobami firmy. W tym temacie uzyskasz informacje dotyczące dostępu warunkowego opartego na urządzeniach i aplikacjach, a także poznasz typowe scenariusze dotyczące używania dostępu warunkowego za pomocą usługi Intune.

Dostęp warunkowy w pakiecie Enterprise Mobility + Security (EMS) nie jest produktem autonomicznym. Jest rozwiązaniem, które obejmuje wszystkie usługi i produkty będące częścią pakietu EMS. Zapewnia pełną kontrolę dostępu, co pozwala zabezpieczyć dane firmowe, udostępniając użytkownikom środowisko, które umożliwia wykonywanie pracy w najbardziej wydajny sposób na dowolnym urządzeniu i w dowolnym miejscu.

Można określić warunki, które blokują dostęp do danych firmowych na podstawie lokalizacji, urządzeń, stanu użytkownika i ważności aplikacji.

> [!NOTE] 
> Z możliwości dostępu warunkowego można również korzystać w [usługach Office 365](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Diagram architektury dostępu warunkowego](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Korzystanie z dostępu warunkowego przy użyciu usługi Intune

Dostęp warunkowy jest funkcją usługi Azure Active Directory dostępną po uzyskaniu licencji na wersję Premium licencji tej usługi. Usługa Intune rozszerza tę funkcję, dodając do rozwiązania zgodność urządzeń przenośnych oraz zarządzanie aplikacjami mobilnymi. 

![Usługa Intune i dostęp warunkowy podczas korzystania z pakietu EMS](./media/conditional-access/intune-with-ca-1.png)

Sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune:

- **Dostęp warunkowy oparty na urządzeniach**

  - Dostęp warunkowy do lokalnego programu Exchange

  - Dostęp warunkowy w oparciu o kontrolę dostępu do sieci

  - Dostęp warunkowy w oparciu o ryzyko dotyczące urządzenia

  - Dostęp warunkowy dla komputerów z systemem Windows

    - Urządzenia należące do firmy

    - „Przynieś własne urządzenie” (BYOD)

- **Dostęp warunkowy na podstawie aplikacji**

## <a name="next-steps"></a>Następne kroki

[Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md)
