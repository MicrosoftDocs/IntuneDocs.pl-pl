---
title: Usługa Mobile Threat Defense w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Usługa Mobile Threat Defense (MTD) w usłudze Intune razem z partnerem usługi Mobile Threat Defense umożliwia ochronę dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5329e23ee6307f86c7b1fcaead0cb24b8271443c
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041618"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Co to jest integracja usługi Mobile Threat Defense z usługą Intune?
Usługa Intune może integrować dane od dostawcy usługi Mobile Threat Defense jako źródło informacji dla zasad zgodności i reguł dostępu warunkowego. Informacje te ułatwiają ochronę firmowych zasobów, takich jak programy Exchange i SharePoint, ponieważ umożliwiają blokowanie dostępu z urządzeń przenośnych, których bezpieczeństwo zostało naruszone.  

## <a name="what-problem-does-this-solve"></a>Jaki problem to rozwiązuje?
Integracja informacji od dostawcy usługi Mobile Threat Defense ułatwia ochronę zasobów firmy przed zagrożeniami występującymi na platformach urządzeń przenośnych.  

Zazwyczaj firmy aktywnie chronią komputery przed atakami i lukami w zabezpieczeniach, ale urządzenia przenośne są pozostawiane bez monitorowania i ochrony. Platformy urządzeń przenośnych mają wbudowaną ochronę polegającą na izolacji aplikacji i weryfikacji sklepów z aplikacjami, ale platformy te nadal są narażone na zaawansowane ataki. Coraz więcej osób korzysta w swojej pracy z urządzeń i wymaga dostępu do poufnych informacji. Informacje od dostawcy usługi Mobile Threat Defense pomagają chronić urządzenia i zasoby przed coraz bardziej zaawansowanymi atakami.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Jak działają łączniki Mobile Threat Defense usługi Intune?

Łącznik Mobile Threat Defense pozwala utworzyć kanał komunikacji między usługą Intune a wybranym dostawcą narzędzi Mobile Threat Defense. Partnerzy udostępniający rozwiązanie Mobile Threat Defense dla usługi Intune oferują intuicyjne, łatwe do wdrożenia aplikacje dla urządzeń przenośnych. Aplikacje te aktywnie skanują i analizują informacje o zagrożeniach w celu udostępniania ich usłudze Intune. Usługa Intune może użyć tych danych do tworzenia raportów lub wymuszania stosowania zasad.  

Przykład: Połączona aplikacja Mobile Threat Defense przesyła do dostawcy usługi Mobile Threat Defense informację o tym, że telefon w Twojej sieci jest aktualnie połączony z siecią, która jest narażona na ataki typu Man in the Middle. Informacja ta jest przypisywana do odpowiedniego poziomu ryzyka (niski, średni lub wysoki). Dane te są następnie porównywane ze skonfigurowanymi w usłudze Intune dozwolonymi poziomami ryzyka. Na podstawie tego porównania można cofnąć dostęp do wybranych zasobów na czas zagrożenia urządzenia.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Jakie dane zbiera usługa Intune na potrzeby ochrony przed zagrożeniami mobilnymi?

Usługa Intune, jeśli jest włączona, zbiera informacje dotyczące spisu aplikacji zarówno z urządzeń osobistych, jak i firmowych i udostępnia je dostawcom usługi ochrony przed zagrożeniami mobilnymi (MTD), na przykład aplikacji Lookout for Work. Możesz zbierać informacje o spisie aplikacji od użytkowników urządzeń z systemem iOS.

Konieczne jest wyrażenie zgody na uczestnictwo w tej usłudze; żadne informacje o spisie aplikacji nie są domyślnie udostępniane. Administrator usługi Intune musi włączyć synchronizację aplikacji dla urządzeń z systemem iOS w ustawieniach usługi zanim zostaną udostępnione jakiekolwiek informacje dotyczące spisu aplikacji.

**Spis aplikacji**  
W przypadku włączenia synchronizacji aplikacji dla urządzeń z systemem iOS spisy zarówno z urządzeń z systemem iOS będących własnością firmy, jak i poszczególnych osób są wysyłane do dostawcy usługi MTD. Spis aplikacji zawiera następujące dane:

 - Identyfikator aplikacji
 - Wersja aplikacji
 - Krótki numer wersji
 - Nazwa aplikacji
 - Rozmiar pakietu aplikacji
 - Dynamiczny rozmiar aplikacji
 - Czy aplikacja została zweryfikowana
 - Czy aplikacja jest zarządzana

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Gdy urządzenie jest uznawane za zainfekowane przez rozwiązanie Mobile Threat Defense:

![Obraz przedstawiający urządzenie zainfekowane w rozwiązaniu Mobile Threat Defense](./media/MTD-image-1.png)

Dostęp jest udzielany po skorygowaniu urządzenia:

![Obraz przedstawiający udzielony dostęp do usługi Mobile Threat Defense](./media/MTD-image-2.png)

> [!NOTE] 
> Używanie wielu dostawców rozwiązania Mobile Threat Defense w usłudze Intune nie jest obsługiwane. Występowanie wielu włączonych narzędzi MTD wymusi zainstalowanie i zeskanowanie wszystkich aplikacji MTD na urządzeniach pod kątem zagrożeń.

## <a name="mobile-threat-defense-partners"></a>Partnerzy narzędzi Mobile Threat Defense

Dowiedz się, jak chronić dostęp do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji przy użyciu:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- Wandera (szczegóły dostępne wkrótce)
