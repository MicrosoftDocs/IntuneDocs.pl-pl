---
title: Przewodnik po migracji funkcji zarządzania urządzeniami mobilnymi do usługi Intune
titleSuffix: Microsoft Intune
description: Ten przewodnik zawiera szczegółowe instrukcje umożliwiające przejście przez różne etapy migracji od innego dostawcy usług MDM do usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: e293140838cd772dea4cdf810623cfe92fa0fe9e
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61512993"
---
# <a name="intune-migration-guide"></a>Przewodnik po migracji do usługi Intune

![Graficzne przedstawienie przewodnika po migracji funkcji MDM do usługi Microsoft Intune](./media/MDM-migration-guide-art.PNG)

Aby migracja do usługi Microsoft Intune zakończyła się powodzeniem, należy rozpocząć od opracowania dobrego planu, który uwzględnia bieżące środowisko zarządzania urządzeniami mobilnymi (MDM), cele biznesowe i wymagania techniczne. Dodatkowym wymogiem jest uwzględnienie najważniejszych uczestników projektu, którzy udzielą wsparcia podczas prac nad planem migracji.

Ten przewodnik zawiera szczegółowe instrukcje umożliwiające przejście przez różne etapy migracji od innego dostawcy usług MDM do usługi Intune.

## <a name="whats-included-in-this-guide"></a>Co zawiera ten przewodnik?

Ten przewodnik dzieli proces migracji na dwie fazy, z których każda obejmuje zadania, strategie i wskazówki taktyczne, które ułatwiają kompleksowe przejście przez proces migracji funkcji MDM do usługi Intune.

-   [Faza 1. Przygotowanie usługi Intune do zarządzania urządzeniami mobilnymi](migration-guide-prepare.md)

    -   [Ocena wymagań dotyczących migracji funkcji MDM](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Konfiguracja podstawowa](migration-guide-setup.md)

    -   [Konfiguracja zasad zarządzania urządzeniami i aplikacjami](migration-guide-configure-policies.md)

    -   [Konfiguracja zasad ochrony aplikacji](migration-guide-app-protection-policies.md)

    -   [Specjalne zagadnienia dotyczące migracji](migration-guide-considerations.md)

-   [Faza 2. Kampania migracji](migration-guide-campaign.md)

    -   [Plan komunikacji](migration-guide-communication-plan.md)

    -   [Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego](migration-guide-drive-adoption.md)

    -   [Typowy cykl migracji](migration-guide-cycle.md)
        -   [Monitorowanie migracji](migration-guide-cycle.md#monitoring-migration)
        -   [Zadania po migracji](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Założenia

-   Usługa Intune została już oceniona w środowisku weryfikacji koncepcji i zamierzasz jej używać jako rozwiązania MDM w Twojej organizacji.

-   Znasz już usługę Intune i jej funkcje.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Ważne jest, aby mieć świadomość, że nowe wdrożenie usługi Intune może się różnić od starego wdrożenia funkcji MDM. W przeciwieństwie do tradycyjnych usług MDM działanie usługi Intune skupia się na kontroli dostępu opartej na tożsamościach. Oznacza to, że do kontrolowania dostępu do danych firmowych z urządzeń przenośnych spoza obwodu sieci organizacji nie jest wymagane sieciowe urządzenie proxy. Firma Microsoft oferuje rozwiązania do zabezpieczania usług danych w samej chmurze. Jest to pakiet ściśle zintegrowanych usług w chmurze, zbiorczo określany jako rozwiązanie Enterprise Client + Security.

-   Przejrzyj [typowe sposoby korzystania z usługi Intune](common-scenarios.md).

## <a name="next-steps"></a>Następne kroki

[Faza 1. Przygotowanie usługi Intune do zarządzania urządzeniami mobilnymi](migration-guide-prepare.md)
