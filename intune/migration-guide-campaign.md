---
title: Rozpoczęcie kampanii migracji do usługi Intune
titleSuffix: Microsoft Intune
description: Ten artykuł zawiera wskazówki dotyczące sposobu rozpoczęcia kampanii migracji do usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e409683c294b9d0321458f40c9b7f66bc3660ac
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046510"
---
# <a name="phase-2-migration-campaign"></a>Faza 2. Kampania migracji

Należy wybrać podejście do migracji najodpowiedniejsze z punktu widzenia potrzeb organizacji i dostosowywać taktykę wdrażania w oparciu o konkretne wymagania. W pozostałej części tego przewodnika przedstawiono narzędzia niezbędne do osiągnięcia celu, jakim jest rejestracja urządzeń użytkowników w usłudze Intune.

## <a name="keys-to-a-successful-migration"></a>Czynniki o kluczowym znaczeniu dla pomyślnego przeprowadzenia migracji

Oto czynniki kluczowe do pomyślnego przeprowadzenia migracji z rozwiązania MDM innej firmy do usługi Intune:

-   Zrozumiałe i pomocne komunikaty mogą zminimalizować niezadowolenie i przestoje użytkowników końcowych.

-   Należy pamiętać o przygotowaniu konkretnych, szczegółowych instrukcji dotyczących migracji.

-   Wszystkie zarządzane urządzenia muszą zostać wyrejestrowane z istniejącej usługi MDM, zanim możliwa będzie ich rejestracja w usłudze Intune.

-   Użytkownikom końcowym należy przekazać wskazówki od istniejącego dostawcy usług MDM dotyczące sposobu wyrejestrowania urządzeń.

-   Kampanię należy realizować etapami. Warto rozpocząć od programu pilotażowego obejmującego swoim zasięgiem małą grupę użytkowników, a następnie stopniowo dodawać kolejne grupy użytkowników — aż do pełnego wdrożenia.

-   W każdym cyklu należy monitorować obciążenie zespołu pomocy technicznej i śledzić wskaźnik pomyślnych rejestracji. Należy uwzględnić w harmonogramie dodatkowy czas, aby móc dokonać oceny kryteriów powodzenia dla każdej z grup przed migracją kolejnej grupy. Wdrożenie pilotażowe powinno pozwolić określić, czy:

    -   Wskaźniki pomyślnych rejestracji i niepowodzeń są zgodne z oczekiwaniami.

    -   Produktywność użytkowników:

        -   Zasoby firmowe, takie jak sieć VPN, sieć Wi-Fi, poczta e-mail i certyfikaty, działają prawidłowo.

        -   Aprowizowane aplikacje są dostępne.

    -   Bezpieczeństwo danych:

        -   Raportowanie zgodności jest realizowane.

        -   Zabezpieczenia aplikacji mobilnych są wymuszane.

Jeśli pierwsza faza migracji przebiegła pomyślnie, można powtórzyć [cykl migracji](migration-guide-cycle.md) w celu przeprowadzenia kolejnej fazy.

-   Powtarzaj realizowane etapowo cykle, aż wszyscy użytkownicy zostaną zmigrowani do usługi Intune.

-   Upewnij się, że zespół pomocy technicznej jest w stanie zapewnić wsparcie użytkownikom końcowym w toku całej kampanii migracji. Umożliwiaj użytkownikom dobrowolną migrację do czasu oszacowania, jak duże obciążenie zespołu pomocy technicznej powoduje migracja.

-   Nie wyznaczaj ostatecznego terminu rejestracji urządzeń do czasu, gdy zespół pomocy technicznej będzie w stanie zapewnić obsługę pozostałym użytkownikom.

> [!IMPORTANT]
> Nie konfiguruj równocześnie usługi Intune i istniejącego rozwiązania MDM innej firmy pod kątem kontroli dostępu do zasobów takich, jak usługi Exchange i SharePoint Online. Co więcej, urządzenia nie mogą być jednocześnie zarejestrowane w dwóch rozwiązaniach.

## <a name="next-steps"></a>Następne kroki

Przygotuj własny [plan komunikacji](migration-guide-communication-plan.md).
