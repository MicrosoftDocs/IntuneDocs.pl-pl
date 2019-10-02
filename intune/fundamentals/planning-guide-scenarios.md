---
title: Identyfikowanie scenariuszy przypadków użycia
titleSuffix: Microsoft Intune
description: W tym artykule zawarto informacje ułatwiające zidentyfikowanie scenariuszy przypadków użycia i podrzędnych przypadków użycia usługi Intune dla opartej tylko na chmurze implementacji usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c852d89a12e2f06b2286699bc262a8e2f5b3d203
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727210"
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Identyfikowanie scenariuszy przypadków użycia zarządzania urządzeniami mobilnymi

Identyfikowanie scenariuszy przypadków użycia jest ważnym elementem procesu planowania pomyślnego wdrożenia usługi Intune. Scenariusze przypadków użycia są przydatne, ponieważ umożliwiają podzielenie użytkowników na grupy zarządzane według typu lub roli użytkownika i własności urządzenia użytkownika (np. własność firmy lub osobista).

Omówmy kilka przykładów, aby ułatwić organizacji identyfikowanie scenariuszy przypadków użycia usługi Intune, a także grup organizacyjnych i platform urządzeń mobilnych skojarzonych z poszczególnymi przypadkami użycia.

## <a name="device-ownership"></a>Własność urządzeń
Można rozpocząć od określenia celów wdrażania usługi Intune w organizacji, aby pomóc w określeniu głównych scenariuszy przypadków użycia dla danego wdrożenia. W zakresie planu wdrożenia usługi Intune należy odpowiedzieć na następujące pytania:

- Czy planowana jest obsługa urządzeń należących do firmy?

- Czy planowana jest obsługa urządzeń, które są własnością osobistą (BYOD)?

Nie są to opcje wzajemnie wykluczające. Może się okazać, że aby spełnić cele organizacji, potrzebna będzie obsługa obu form własności urządzeń. Podrzędne przypadki użycia ułatwią ustalenie, gdzie można zastosować różne zasady zarządzania urządzeniami.

### <a name="user-type-or-device-role"></a>Typ użytkownika lub rola urządzenia

Ustal, czy każdy scenariusz przypadków użycia obejmuje również podrzędne przypadki użycia. Na przykład organizacja mogła zidentyfikować wymagania związane z obsługą firmowego scenariusza przypadków użycia, który zawiera dodatkowe podrzędne przypadki użycia w oparciu o typ użytkownika lub rolę urządzenia, np.:

- Pracownik przetwarzający informacje

- Kierownik

- Kiosk

Oto kilka przykładów scenariuszy przypadków użycia i podrzędnych przypadków użycia:

| **Przypadki użycia** | **Podrzędne przypadki użycia** |
|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje |              
| Firmowe | Kierownictwo |           
| Firmowe | Kiosk |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje |           
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownictwo |

Możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), aby wprowadzić scenariusze przypadków użycia i podrzędnych przypadków użycia w swojej organizacji.

## <a name="organizational-groups-for-your-scenarios"></a>Grupy organizacyjne dla scenariuszy

Następnie należy zidentyfikować grupy organizacyjne, które są skojarzone z poszczególnymi scenariuszami przypadków użycia i podrzędnych przypadków użycia. Przykład:

| **Przypadki użycia** | **Podrzędne przypadki użycia** | **Grupy organizacyjne** |
|:---:|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje | Kadry, księgowość |               
| Firmowe | Kierownik | Kadry, księgowość |            
| Firmowe | Kiosk | Sprzedaż detaliczna |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje | Marketing, sprzedaż |            
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownik | Marketing, sprzedaż |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Platformy urządzeń mobilnych dla scenariuszy

Kolejnym krokiem jest zidentyfikowanie platform urządzeń mobilnych skojarzonych z poszczególnymi scenariuszami przypadków użycia. Może ich być więcej niż jedna.

Na przykład firmowy scenariusz przypadków użycia może obsługiwać platformy urządzeń iOS i Android Samsung Knox. Zasady BYOD mogą obejmować obsługę dodatkowych platform urządzeń mobilnych, takich jak Android (w wersjach innych niż Samsung Knox) i Windows 10 Mobile. Opierając się na powyższych przykładach, skojarzyliśmy platformy urządzeń mobilnych z poszczególnymi scenariuszami przypadków użycia.

| **Przypadki użycia** | **Podrzędne przypadki użycia** | **Grupy** | **Platformy urządzeń** |   
|:---:|:---:|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje | Kadry, księgowość | iOS |                                                           
| Firmowe | Kierownictwo | Kadry, księgowość | iOS |                                                           
| Firmowe | Kiosk | Sprzedaż detaliczna | Android |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje | Marketing, sprzedaż | iOS |                                                           
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownictwo | Marketing, sprzedaż | iOS |

## <a name="next-steps"></a>Następne kroki

Następna sekcja zawiera wskazówki dotyczące [identyfikowania wymagań usługi Intune dla każdego scenariusza przypadków użycia](../planning-guide-requirements.md).
