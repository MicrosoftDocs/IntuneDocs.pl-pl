---
title: "Narzędzie Mobile Threat Defense usługi Intune | Microsoft Docs"
description: "Ochrona dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c3c5126b1c9437c2689b162c28e1a60e5dc4b108
ms.openlocfilehash: ad39f4b2cc4a51346fcf226dc07208af336d3581
ms.lasthandoff: 03/22/2017


---

# <a name="intune-mobile-threat-defense-connectors"></a>Łączniki Mobile Threat Defense usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Łączniki Mobile Threat Defense usługi Intune umożliwiają wykorzystanie wybranego dostawcy narzędzie Mobile Threat Defense jako źródła informacji dla zasad zgodności i zasad dostępu warunkowego. Umożliwia to administratorom IT dodanie warstwy zabezpieczeń do zasobów firmy, takich jak Exchange i Sharepoint, w szczególności związanych z zagrożonymi urządzeniami przenośnymi.

## <a name="what-problem-does-this-solve"></a>Jaki problem to rozwiązuje?

Firmy muszą chronić dane poufne przed pojawiającymi się zagrożeniami, do których zalicza się zagrożenia fizyczne, związane z aplikacją lub siecią, a także luki w zabezpieczeniach systemu operacyjnego.
Wcześniej firmy aktywnie chroniły komputery przed atakami, pozostawiając urządzenia przenośne bez monitorowania i ochrony. Platformy urządzeń przenośnych mają wbudowaną ochronę polegającą na izolacji aplikacji i weryfikacji sklepów z aplikacjami, ale platformy te nadal są narażone na zaawansowane ataki. Obecnie coraz więcej pracowników korzysta w swojej pracy z urządzeń i wymaga dostępu do poufnych informacji. Urządzenia muszą być chronione przed coraz bardziej zaawansowanymi atakami.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Jak działają łączniki Mobile Threat Defense usługi Intune?

Łącznik chroni zasoby firmy, tworząc kanał komunikacji między usługą Intune a wybranym dostawcą narzędzi Mobile Threat Defense. Partnerzy narzędzi Mobile Threat Defense usługi Intune oferują intuicyjne, łatwe do wdrożenia aplikacje dla urządzeń przenośnych, które aktywnie skanują i analizują informacje o zagrożeniach oraz udostępniają je usłudze Intune do celów raportowania lub wymuszania. Na przykład, jeśli połączona aplikacja Mobile Threat Defense zgłasza dostawcy narzędzi Mobile Threat Defense, że telefon w sieci jest podłączony do sieci narażonej na ataki typu Man in the Middle, informacja ta jest udostępniana i przypisywana do odpowiedniego poziomu ryzyka (niski/średni/wysoki). Dane te można porównać ze skonfigurowanymi w usłudze Intune dozwolonymi poziomami ryzyka w celu określenia, czy dostęp do określonych wybranych zasobów należy cofnąć na czas zagrożenia urządzenia.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Gdy urządzenie jest uznawane za zainfekowane przez rozwiązanie Mobile Threat Defense:

![Urządzenie zainfekowane w rozwiązaniu Mobile Threat Defense](../media/mtp/MTD-image-1.png)

Dostęp jest udzielany po skorygowaniu urządzenia:

![Udzielono dostępu do aplikacji Mobile Threat Defense](../media/mtp/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Partnerzy narzędzi Mobile Threat Defense

Dowiedz się, jak chronić dostęp do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji przy użyciu:

- [Lookout](https://docs.microsoft.com/intune/deploy-use/lookout-mobile-threat-defense-connector)
- [Skycure](https://docs.microsoft.com/intune/deploy-use/skycure-mobile-threat-defense-connector)
