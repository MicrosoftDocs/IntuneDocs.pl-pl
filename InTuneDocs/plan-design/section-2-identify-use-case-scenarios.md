---
title: "Identyfikowanie scenariuszy przypadków użycia usługi Intune | Microsoft Docs"
description: "W tym artykule zawarto informacje ułatwiające określenie scenariuszów przypadków użycia i podrzędnych przypadków użycia usługi Intune dla opartej tylko na chmurze implementacji usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: c834b0282b8f9b47566ab1da2125d993ba8febdf


---

# <a name="identify-intune-use-case-scenarios"></a>Identyfikowanie scenariuszy przypadków użycia usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Scenariusze przypadków użycia zarządzania urządzeniami przenośnymi opisują typ użytkownika lub rolę oraz prawo własności urządzenia (np. firmowego lub osobistego). Scenariusze przypadków użytkownika są przydatne, ponieważ pozwalają podzielić użytkowników na możliwe do zarządzania grupy. Identyfikowanie scenariuszy przypadków użycia jest ważnym elementem procesu planowania pomyślnego wdrożenia usługi Intune.

Omówmy kilka przykładów, aby ułatwić organizacji identyfikowanie scenariuszy przypadków użycia usługi Intune, a także grup organizacyjnych i platform urządzeń przenośnych skojarzonych z poszczególnymi przypadkami użycia.

## <a name="use-case-scenarios"></a>Scenariusze przypadków użycia

Możesz rozpocząć od przekazania do swojej organizacji celów wdrażania usługi Intune, które mają pomóc w określeniu głównych scenariuszy przypadków użycia dla danego wdrożenia. W zakresie planu wdrożenia usługi Intune należy odpowiedzieć na następujące pytania:

-   Czy planowana jest obsługa urządzeń należących do firmy?

-   Czy planowana jest obsługa urządzeń, które są własnością osobistą (BYOD)?

### <a name="sub-use-case-scenarios"></a>Scenariusze podrzędnych przypadków użycia

Po określeniu głównych scenariuszy przypadków użycia należy ustalić, czy poszczególne przypadki użycia zawierają również podrzędne przypadki użycia. Na przykład organizacja może zidentyfikować wymagania związaną z obsługą firmowego przypadku użycia, który zawiera dodatkowe podrzędne przypadki użycia:

-   Pracownik przetwarzający informacje

-   Kierownictwo

-   Kiosk

Oto kilka przykładów scenariuszy przypadków użycia i podrzędnych przypadków użycia. Poniższa tabela może również służyć jako wzór do wprowadzania przypadków użycia i podrzędnych przypadków użycia w Twojej organizacji:

| **Przypadki użycia** | **Podrzędne przypadki użycia** |
|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje |              
| Firmowe | Kierownictwo |           
| Firmowe | Kiosk |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje |           
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownictwo |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>Określanie grup organizacyjnych powiązanych ze scenariuszami przypadków użycia

Następnie należy zidentyfikować grupy organizacyjne, które są skojarzone z poszczególnymi scenariuszami przypadków użycia i podrzędnych przypadków użycia. Poniżej przedstawiono kilka przykładów grup organizacyjnych skojarzonych ze scenariuszami przypadków użycia i podrzędnych przypadków użycia, które mogą służyć jako szablon do wprowadzania informacji o Twojej organizacji:

| **Przypadki użycia** | **Podrzędne przypadki użycia** | **Grupy organizacyjne** |
|:---:|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje | Kadry, księgowość |               
| Firmowe | Kierownik | Kadry, księgowość |            
| Firmowe | Kiosk | Sprzedaż detaliczna |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje | Marketing, sprzedaż |            
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownik | Marketing, sprzedaż |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Identyfikowanie platform urządzeń przenośnych na potrzeby scenariuszy przypadków użycia

W tym miejscu zostaną zidentyfikowane platformy urządzeń przenośnych skojarzone z poszczególnymi scenariuszami przypadków użycia. Na przykład firmowy scenariusz użycia może obsługiwać platformy urządzeń z systemami iOS i Android Samsung KNOX, a Twoje zasady BYOD mogą obejmować obsługę dodatkowych platform urządzeń przenośnych, takich jak Android (system inny niż Samsung KNOX) i Windows 10 Mobile. Poniżej znajduje się przykład platform urządzeń przenośnych skojarzonych z poszczególnymi scenariuszami przypadków użycia. Poniższa tabela może służyć jako wzór do wprowadzania platform urządzeń skojarzonych z ich scenariuszami przypadków użycia:

| **Przypadki użycia** | **Podrzędne przypadki użycia** | **Grupy** | **Platformy urządzeń** |   
|:---:|:---:|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje | Kadry, księgowość | iOS |                                                           
| Firmowe | Kierownictwo | Kadry, księgowość | iOS |                                                           
| Firmowe | Kiosk | Sprzedaż detaliczna | Android |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje | Marketing, sprzedaż | iOS |                                                           
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownictwo | Marketing, sprzedaż | iOS |

## <a name="next-section"></a>Następna sekcja

Następna sekcja zawiera wskazówki dotyczące [identyfikowania wymagań usługi Intune dla każdego scenariusza przypadków użycia](section-3-determine-use-case-requirements.md).



<!--HONumber=Dec16_HO5-->


