---
title: "Przewodnik po migracji funkcji zarządzania urządzeniami przenośnymi (MDM) do usługi Intune | Microsoft Docs"
description: "Ten przewodnik zawiera szczegółowe instrukcje umożliwiające klientom przejście przez różne etapy migracji od innego dostawcy usług MDM do usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Przewodnik po migracji do usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Graficzne przedstawienie przewodnika po migracji funkcji MDM do usługi Intune](../media/MDM-migration-guide-art.PNG)

Aby migracja do usługi Intune zakończyła się powodzeniem, należy rozpocząć od opracowania dobrego planu, który uwzględnia bieżące środowisko MDM, cele biznesowe i wymagania techniczne. Dodatkowym wymogiem jest współpraca z najważniejszymi uczestnikami projektu, którzy udzielą wsparcia podczas prac nad planem migracji.

Ten przewodnik zawiera szczegółowe instrukcje umożliwiające przejście przez różne etapy migracji od innego dostawcy usług MDM do usługi Intune.

## <a name="whats-included-in-this-guide"></a>Co zawiera ten przewodnik?

Ten przewodnik składa się z dwóch faz obejmujących zadania, strategie i wskazówki taktyczne, które ułatwiają kompleksowe przejście przez proces migracji funkcji MDM do usługi Intune.

-   [Faza 1: Przygotowanie usługi Intune do zarządzania urządzeniami przenośnymi (MDM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Ocena wymagań dotyczących migracji funkcji MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Konfiguracja podstawowa](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Konfiguracja zasad zarządzania urządzeniami i aplikacjami](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Konfiguracja zasad ochrony aplikacji (opcjonalnie)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Specjalne zagadnienia dotyczące migracji](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [Faza 2: Kampania migracji](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [Plan komunikacji](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Typowy cykl migracji](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [Monitorowanie migracji](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Zadania po migracji](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Założenia

-   Usługa Intune została już oceniona w środowisku weryfikacji koncepcji i zamierzasz jej używać jako rozwiązania MDM w Twojej organizacji.

-   Znasz już usługę Intune i jej funkcje. 

> [!NOTE]
> Aby dowiedzieć się więcej na temat usługi Intune przed przeprowadzeniem migracji, zapoznaj się z [przewodnikiem dotyczącym oceny usługi Intune](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune).

## <a name="before-you-begin"></a>Przed rozpoczęciem

Ważne jest, aby mieć świadomość, że nowe wdrożenie usługi Intune może się różnić od starego wdrożenia funkcji MDM. W przeciwieństwie do tradycyjnych usług MDM działanie usługi Intune skupia się na kontroli dostępu opartej na tożsamościach. Oznacza to, że do kontrolowania dostępu do danych firmowych z urządzeń przenośnych spoza obwodu sieci organizacji nie jest wymagane sieciowe urządzenie proxy. Firma Microsoft oferuje rozwiązania do zabezpieczania usług danych w samej chmurze. Jest to pakiet ściśle zintegrowanych usług w chmurze, zbiorczo określany jako rozwiązanie Enterprise Client + Security.

-   Zapoznaj się z [typowymi sposobami korzystania z usługi Intune](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune) i zacznij szukać odpowiedzi na pytania zawarte w części [Faza 1: Określanie wymagań w zakresie MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Następne kroki

[Faza 1: Przygotowanie usługi Intune do zarządzania urządzeniami przenośnymi (MDM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

