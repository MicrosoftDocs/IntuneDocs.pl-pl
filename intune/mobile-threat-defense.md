---
title: Usługa Mobile Threat Defense w usłudze Microsoft Intune
titleSuffix: ''
description: Usługa Mobile Threat Defense (MTD) w usłudze Intune razem z partnerem usługi Mobile Threat Defense umożliwia ochronę dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 11/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6dae7f6973f6259284fc21e5e4b8e98b67517102
ms.sourcegitcommit: 973a06f4a35b74314fece2bae17dd6885b4211c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42823005"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Co to jest integracja usługi Mobile Threat Defense z usługą Intune?


Łączniki Mobile Threat Defense usługi Intune umożliwiają wykorzystanie wybranego dostawcy narzędzie Mobile Threat Defense jako źródła informacji dla zasad zgodności i zasad dostępu warunkowego. Umożliwia to administratorom IT dodanie warstwy zabezpieczeń do zasobów firmy, takich jak Exchange i Sharepoint, w szczególności związanych z zagrożonymi urządzeniami przenośnymi.

## <a name="what-problem-does-this-solve"></a>Jaki problem to rozwiązuje?

Firmy muszą chronić dane poufne przed pojawiającymi się zagrożeniami, do których zalicza się zagrożenia fizyczne, związane z aplikacją lub siecią, a także luki w zabezpieczeniach systemu operacyjnego.

Wcześniej firmy aktywnie chroniły komputery przed atakami, pozostawiając urządzenia przenośne bez monitorowania i ochrony. Platformy urządzeń przenośnych mają wbudowaną ochronę polegającą na izolacji aplikacji i weryfikacji sklepów z aplikacjami, ale platformy te nadal są narażone na zaawansowane ataki. Obecnie coraz więcej pracowników korzysta w swojej pracy z urządzeń i wymaga dostępu do poufnych informacji. Urządzenia muszą być chronione przed coraz bardziej zaawansowanymi atakami.

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Jak działają łączniki Mobile Threat Defense usługi Intune?

Łącznik chroni zasoby firmy, tworząc kanał komunikacji między usługą Intune a wybranym dostawcą narzędzi Mobile Threat Defense. Partnerzy narzędzi Mobile Threat Defense usługi Intune oferują intuicyjne, łatwe do wdrożenia aplikacje dla urządzeń przenośnych, które aktywnie skanują i analizują informacje o zagrożeniach oraz udostępniają je usłudze Intune do celów raportowania lub wymuszania. 

Jeśli na przykład połączona aplikacja Mobile Threat Defense zgłasza dostawcy narzędzi Mobile Threat Defense, że telefon w sieci jest podłączony do sieci narażonej na ataki typu Man in the Middle, informacja ta jest udostępniana i przypisywana do odpowiedniego poziomu ryzyka (niski/średni/wysoki). Dane te można porównać ze skonfigurowanymi w usłudze Intune dozwolonymi poziomami ryzyka w celu określenia, czy dostęp do określonych wybranych zasobów należy cofnąć na czas zagrożenia urządzenia.

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
