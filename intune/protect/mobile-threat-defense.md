---
title: Usługa Mobile Threat Defense w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Usługa Mobile Threat Defense (MTD) w usłudze Intune razem z partnerem usługi Mobile Threat Defense umożliwia ochronę dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f056f665ebee0d1e2315129a4fe739b2c490ca98
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514850"
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integracja narzędzia Mobile Threat Defense z usługą Intune

Usługa Intune może integrować dane od dostawcy usługi Mobile Threat Defense (MTD) jako źródło informacji dla zasad zgodności urządzeń i reguł dostępu warunkowego urządzeń. Informacje te ułatwiają ochronę firmowych zasobów, takich jak programy Exchange i SharePoint, ponieważ umożliwiają blokowanie dostępu z urządzeń przenośnych, których bezpieczeństwo zostało naruszone.

Usługa Intune może używać tych samych danych jako źródła dla niezarejestrowanych urządzeń używających zasad ochrony aplikacji usługi Intune. W związku z tym administratorzy mogą korzystać z tych informacji w celu ochrony danych firmowych w ramach [aplikacji chronionej przez usługę Microsoft Intune](~/apps/apps-supported-intune-apps.md) i do nałożenia blokady lub wykonania selektywnego czyszczenia.

## <a name="protect-corporate-resources"></a>Ochrona zasobów firmowych

Integracja informacji od dostawców usługi MTD ułatwia ochronę zasobów firmy przed zagrożeniami wpływającymi na platformy przenośne.  

Zazwyczaj firmy aktywnie chronią komputery przed atakami i lukami w zabezpieczeniach, ale urządzenia przenośne są pozostawiane bez monitorowania i ochrony. Platformy urządzeń przenośnych mają wbudowaną ochronę polegającą na izolacji aplikacji i weryfikacji sklepów z aplikacjami, ale platformy te nadal są narażone na zaawansowane ataki. Coraz więcej osób korzysta w swojej pracy z urządzeń i wymaga dostępu do poufnych informacji. Informacje od dostawcy usługi MTD pomagają chronić urządzenia i zasoby przed coraz bardziej zaawansowanymi atakami.

## <a name="intune-mobile-threat-defense-connectors"></a>Łączniki Mobile Threat Defense usługi Intune

Łącznik Mobile Threat Defense pozwala utworzyć kanał komunikacji między usługą Intune a wybranym dostawcą narzędzi MTD. Partnerzy udostępniający rozwiązanie MTD dla usługi Intune oferują intuicyjne, łatwe do wdrożenia aplikacje dla urządzeń przenośnych. Aplikacje te aktywnie skanują i analizują informacje o zagrożeniach w celu udostępniania ich usłudze Intune. Usługa Intune może użyć tych danych do tworzenia raportów lub wymuszania stosowania zasad.

Przykład: Połączona aplikacja MTD przesyła do dostawcy usługi MTD informację o tym, że telefon w Twojej sieci jest aktualnie połączony z siecią, która jest narażona na ataki typu Man in the Middle. Informacja ta jest przypisywana do odpowiedniego poziomu ryzyka (niski, średni lub wysoki). Dane te są następnie porównywane ze skonfigurowanymi w usłudze Intune dozwolonymi poziomami ryzyka. Na podstawie tego porównania można cofnąć dostęp do wybranych zasobów na czas zagrożenia urządzenia.

## <a name="data-that-intune-collects-for-mobile-threat-defense"></a>Dane, jakie zbiera usługa Intune na potrzeby usługi Mobile Threat Defense

Usługa Intune, jeśli jest włączona, zbiera informacje dotyczące spisu aplikacji zarówno z urządzeń osobistych, jak i firmowych, i udostępnia je dostawcom usługi MTD, na przykład aplikacji Lookout for Work. Możesz zbierać informacje o spisie aplikacji od użytkowników urządzeń z systemem iOS.

Konieczne jest wyrażenie zgody na uczestnictwo w tej usłudze; żadne informacje o spisie aplikacji nie są domyślnie udostępniane. Administrator usługi Intune musi włączyć **synchronizację aplikacji dla urządzeń z systemem iOS** w ustawieniach łącznika usługi Mobile Threat Defense, zanim zostaną udostępnione jakiekolwiek informacje dotyczące spisu aplikacji.

**Spis aplikacji**  
W przypadku włączenia synchronizacji aplikacji dla urządzeń z systemem iOS/iPadOS spisy zarówno z urządzeń z systemem iOS/iPadOS będących własnością firmy, jak i poszczególnych osób są wysyłane do dostawcy usługi MTD. Spis aplikacji zawiera następujące dane:

- Identyfikator aplikacji
- Wersja aplikacji
- Krótki numer wersji
- Nazwa aplikacji
- Rozmiar pakietu aplikacji
- Dynamiczny rozmiar aplikacji
- Czy aplikacja została zweryfikowana
- Czy aplikacja jest zarządzana

## <a name="sample-scenarios-for-enrolled-devices-using-device-compliance-policies"></a>Przykładowe scenariusze dla zarejestrowanych urządzeń używających zasad zgodności urządzeń

Gdy urządzenie jest uznawane za zainfekowane przez rozwiązanie Mobile Threat Defense:

![Obraz przedstawiający urządzenie zainfekowane w rozwiązaniu Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-1.png)

Dostęp jest udzielany po skorygowaniu urządzenia:

![Obraz przedstawiający udzielony dostęp do usługi Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-2.png)

## <a name="sample-scenarios-for-unenrolled-devices-using-intune-app-protection-policies"></a>Przykładowe scenariusze dla niezarejestrowanych urządzeń używających zasad ochrony aplikacji usługi Intune

Gdy urządzenie jest uznawane za zainfekowane przez rozwiązanie Mobile Threat Defense:<br>
![Obraz przedstawiający zainfekowane urządzenie w usłudze Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-3.png)

Dostęp jest udzielany po skorygowaniu urządzenia:<br>
![Obraz przedstawiający udzielony dostęp do usługi Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-4.png)

> [!NOTE]
> W ramach jednej dzierżawy usługi Intune można korzystać z wielu dostawców rozwiązań obrony urządzeń mobilnych. Jeśli jednak dla jednej platformy zostanie skonfigurowanych dwóch lub więcej dostawców, wszystkie urządzenia korzystające z tej platformy będą musiały mieć zainstalowaną każdą aplikację MTD i przeprowadzać skanowanie pod kątem zagrożeń. Niepowodzenie przesłania aplikacji z jakiejkolwiek skonfigurowanej aplikacji spowoduje oznaczenie urządzenia jako niezgodnego. 

## <a name="mobile-threat-defense-partners"></a>Partnerzy narzędzi Mobile Threat Defense

Dowiedz się, jak chronić dostęp do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji przy użyciu:

- [Lookout for Work](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Wandera Mobile Threat Defense](wandera-mtd-connector.md)
