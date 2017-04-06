---
title: "Rozpoczęcie kampanii migracji do usługi Intune | Microsoft Docs"
description: "Celem tego artykułu jest przedstawienie wskazówek dotyczących sposobu rozpoczęcia kampanii migracji."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 506b0360fb7b1f28c4c9ad3265e24c0ffa0b065d
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-migration-campaign"></a>Faza 2: Kampania migracji

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Organizacje powinny wybierać podejścia do migracji najodpowiedniejsze z punktu widzenia ich potrzeb i dostosowywać taktykę wdrażania w oparciu o konkretne wymagania. W pozostałej części tego przewodnika mowa jest o narzędziach niezbędnych do osiągnięcia celu, jakim jest rejestracja urządzeń użytkowników w usłudze Intune.

## <a name="keys-to-a-successful-migration"></a>Czynniki o kluczowym znaczeniu dla pomyślnego przeprowadzenia migracji

Poniższe kwestie mają zasadnicze znaczenie podczas migracji z usługi MDM innej firmy do usługi Intune:

-   Komunikacja ma decydujące znaczenie dla skrócenia przestojów i zwiększenia zadowolenia użytkownika końcowego.

-   Należy pamiętać o przygotowaniu konkretnych, szczegółowych instrukcji dotyczących migracji.

-   Wszystkie zarządzane urządzenia muszą zostać wyrejestrowane z istniejącej usługi MDM przed ich rejestracją w usłudze Intune.

-   Użytkownikom końcowym należy przekazać wskazówki od istniejącego dostawcy usług MDM dotyczące sposobu wyrejestrowania urządzeń.

-   Kampanię należy realizować etapami. Warto rozpocząć od programu pilotażowego obejmującego swoim zasięgiem małą grupę użytkowników, a następnie stopniowo dodawać kolejne grupy użytkowników — aż do pełnego wdrożenia.

-   W każdym cyklu należy monitorować obciążenie zespołu pomocy technicznej i śledzić wskaźnik pomyślnych rejestracji. Należy uwzględnić w harmonogramie dodatkowy czas, aby móc dokonać oceny kryteriów powodzenia dla każdej z grup przed migracją kolejnej grupy. Wdrożenie pilotażowe powinno pozwolić określić, czy:

    -   Wskaźniki pomyślnych rejestracji i niepowodzeń są zgodne z oczekiwaniami.

    -   Produktywność użytkowników:

        -   Zasoby firmowe, takie jak sieć VPN, sieć Wi-Fi, poczta e-mail i certyfikaty, działają prawidłowo.

        -   Udostępnione aplikacje są dostępne.

    -   Bezpieczeństwo danych:

        -   Raportowanie zgodności

        -   Zabezpieczenia aplikacji mobilnych są wymuszane

-   Po pomyślnym przeprowadzeniu pierwszej fazy migracji możesz powtórzyć cykl migracji (opisany poniżej w sekcji poświęconej typowemu cyklowi migracji) w celu przeprowadzenia kolejnej fazy.

-   Powtarzaj realizowane etapowo cykle, aż wszyscy użytkownicy zostaną zmigrowani do usługi Intune.

-   Upewnij się, że zespół pomocy technicznej jest w stanie zapewnić wsparcie użytkownikom końcowym w toku całej kampanii migracji. Umożliwiaj użytkownikom dobrowolną migrację do czasu oszacowania, jak duże obciążenie zespołu pomocy technicznej powoduje migracja.

-   Nie wyznaczaj ostatecznego terminu rejestracji urządzeń do czasu, gdy zespół pomocy technicznej będzie w stanie zapewnić obsługę pozostałym użytkownikom.

> [!IMPORTANT] 
> Nie konfiguruj równocześnie usługi Intune i istniejącego rozwiązania MDM innej firmy pod kątem kontroli dostępu do zasobów takich, jak usługi Exchange i SharePoint Online. Co więcej, urządzenia nie mogą być jednocześnie zarejestrowane w dwóch rozwiązaniach.

## <a name="next-steps"></a>Następne kroki

[Faza 2: Plan komunikacji](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

