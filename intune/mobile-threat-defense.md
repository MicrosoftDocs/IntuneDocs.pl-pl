---
title: "Narzędzie Mobile Threat Defense w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Ochrona dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec45b9445f2737ad99852ebf46cc40c03537a2e5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integracja narzędzia Mobile Threat Defense z usługą Intune


Łączniki Mobile Threat Defense usługi Intune umożliwiają wykorzystanie wybranego dostawcy narzędzie Mobile Threat Defense jako źródła informacji dla zasad zgodności i zasad dostępu warunkowego. Umożliwia to administratorom IT dodanie warstwy zabezpieczeń do zasobów firmy, takich jak Exchange i Sharepoint, w szczególności związanych z zagrożonymi urządzeniami przenośnymi.

## <a name="what-problem-does-this-solve"></a>Jaki problem to rozwiązuje?

Firmy muszą chronić dane poufne przed pojawiającymi się zagrożeniami, do których zalicza się zagrożenia fizyczne, związane z aplikacją lub siecią, a także luki w zabezpieczeniach systemu operacyjnego.
Wcześniej firmy aktywnie chroniły komputery przed atakami, pozostawiając urządzenia przenośne bez monitorowania i ochrony. Platformy urządzeń przenośnych mają wbudowaną ochronę polegającą na izolacji aplikacji i weryfikacji sklepów z aplikacjami, ale platformy te nadal są narażone na zaawansowane ataki. Obecnie coraz więcej pracowników korzysta w swojej pracy z urządzeń i wymaga dostępu do poufnych informacji. Urządzenia muszą być chronione przed coraz bardziej zaawansowanymi atakami.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Jak działają łączniki Mobile Threat Defense usługi Intune?

Łącznik chroni zasoby firmy, tworząc kanał komunikacji między usługą Intune a wybranym dostawcą narzędzi Mobile Threat Defense. Partnerzy narzędzi Mobile Threat Defense usługi Intune oferują intuicyjne, łatwe do wdrożenia aplikacje dla urządzeń przenośnych, które aktywnie skanują i analizują informacje o zagrożeniach oraz udostępniają je usłudze Intune do celów raportowania lub wymuszania. Na przykład, jeśli połączona aplikacja Mobile Threat Defense zgłasza dostawcy narzędzi Mobile Threat Defense, że telefon w sieci jest podłączony do sieci narażonej na ataki typu Man in the Middle, informacja ta jest udostępniana i przypisywana do odpowiedniego poziomu ryzyka (niski/średni/wysoki). Dane te można porównać ze skonfigurowanymi w usłudze Intune dozwolonymi poziomami ryzyka w celu określenia, czy dostęp do określonych wybranych zasobów należy cofnąć na czas zagrożenia urządzenia.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Gdy urządzenie jest uznawane za zainfekowane przez rozwiązanie Mobile Threat Defense:

![Urządzenie zainfekowane w rozwiązaniu Mobile Threat Defense](./media/MTD-image-1.png)

Dostęp jest udzielany po skorygowaniu urządzenia:

![Udzielono dostępu do aplikacji Mobile Threat Defense](./media/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Partnerzy narzędzi Mobile Threat Defense

Dowiedz się, jak chronić dostęp do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji przy użyciu:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)