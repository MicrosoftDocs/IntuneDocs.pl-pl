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
ms.openlocfilehash: 179d135ee8e216495cd7435bf38d8087e5c990e8
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74188275"
---
# <a name="learn-about-conditional-access-and-intune"></a>Więcej informacji na temat dostępu warunkowego i usługi Intune

Dzięki dostępowi warunkowemu możesz kontrolować urządzenia i aplikacje, które mogą nawiązywać połączenie z pocztą e-mail i zasobami firmy. 

Pakiet Enterprise Mobility + Security (EMS) nie jest produktem autonomicznym. Jest to rozwiązanie, które jest stosowane do wszystkich usług i produktów wchodzących w skład pakietu EMS. Dostęp warunkowy zapewnia pełną kontrolę dostępu, co pozwala zabezpieczyć dane firmowe, udostępniając użytkownikom środowisko, które umożliwia wykonywanie pracy w najbardziej wydajny sposób na dowolnym urządzeniu i w dowolnym miejscu.

Można określić warunki, które blokują dostęp do danych firmowych na podstawie lokalizacji, urządzeń, stanu użytkownika i ważności aplikacji.

> [!NOTE]
> Z możliwości dostępu warunkowego można również korzystać w [usługach Office 365](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Diagram dostępu warunkowego](./media/conditional-access/ca-diagram-1.png)

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
