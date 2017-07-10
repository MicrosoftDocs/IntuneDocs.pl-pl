---
title: "Przewodnik po migracji funkcji zarządzania urządzeniami mobilnymi do usługi Intune"
description: "Ten przewodnik zawiera szczegółowe instrukcje umożliwiające klientom przejście przez różne etapy migracji od innego dostawcy usług MDM do usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="intune-migration-guide"></a>Przewodnik po migracji do usługi Intune

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Graficzne przedstawienie przewodnika po migracji funkcji MDM do usługi Intune](./media/MDM-migration-guide-art.PNG)

Aby migracja do usługi Intune zakończyła się powodzeniem, należy rozpocząć od opracowania dobrego planu, który uwzględnia bieżące środowisko zarządzania urządzeniami mobilnymi (MDM), cele biznesowe i wymagania techniczne. Dodatkowym wymogiem jest współpraca z najważniejszymi uczestnikami projektu, którzy udzielą wsparcia podczas prac nad planem migracji.

Ten przewodnik zawiera szczegółowe instrukcje umożliwiające przejście przez różne etapy migracji od innego dostawcy usług MDM do usługi Intune.

## <a name="whats-included-in-this-guide"></a>Co zawiera ten przewodnik?

Ten przewodnik składa się z dwóch faz obejmujących zadania, strategie i wskazówki taktyczne, które ułatwiają kompleksowe przejście przez proces migracji funkcji MDM do usługi Intune.

-   [Faza 1: Przygotowanie usługi Intune do zarządzania urządzeniami mobilnymi] (migration-guide-prepare.md)

    -   [Ocena wymagań dotyczących migracji funkcji MDM](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Konfiguracja podstawowa](migration-guide-setup.md)

    -   [Konfiguracja zasad zarządzania urządzeniami i aplikacjami](migration-guide-configure-policies.md)

    -   [Konfigurowanie zasad ochrony aplikacji] (migration-guide-app-protection-policies.md)

    -   [Specjalne zagadnienia dotyczące migracji](migration-guide-considerations.md)

-   [Faza 2: Kampania migracji](migration-guide-campaign.md)

    -   [Plan komunikacji](migration-guide-communication-plan.md)

    -   [Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego](migration-guide-drive-adoption.md)
    
    -   [Typowy cykl migracji](migration-guide-cycle.md)
        -   [Monitorowanie migracji](migration-guide-cycle.md#monitoring-migration)
        -   [Zadania po migracji](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Założenia

-   Usługa Intune została już oceniona w środowisku weryfikacji koncepcji i zamierzasz jej używać jako rozwiązania MDM w Twojej organizacji.

-   Znasz już usługę Intune i jej funkcje. 

> [!NOTE]
> Aby dowiedzieć się więcej na temat usługi Intune przed przeprowadzeniem migracji, zapoznaj się z [przewodnikiem dotyczącym oceny usługi Intune](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune).

## <a name="before-you-begin"></a>Przed rozpoczęciem

Ważne jest, aby mieć świadomość, że nowe wdrożenie usługi Intune może się różnić od starego wdrożenia funkcji MDM. W przeciwieństwie do tradycyjnych usług MDM działanie usługi Intune skupia się na kontroli dostępu opartej na tożsamościach. Oznacza to, że do kontrolowania dostępu do danych firmowych z urządzeń przenośnych spoza obwodu sieci organizacji nie jest wymagane sieciowe urządzenie proxy. Firma Microsoft oferuje rozwiązania do zabezpieczania usług danych w samej chmurze. Jest to pakiet ściśle zintegrowanych usług w chmurze, zbiorczo określany jako rozwiązanie Enterprise Client + Security.

-   Przejrzyj [typowe sposoby korzystania z usługi Intune](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="next-steps"></a>Następne kroki

[Faza 1: Przygotowanie usługi Intune do zarządzania urządzeniami mobilnymi] (migration-guide-prepare.md)
