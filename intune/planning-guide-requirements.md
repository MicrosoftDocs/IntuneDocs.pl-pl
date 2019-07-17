---
title: Określanie wymagań scenariusza przypadku użycia
titleSuffix: Microsoft Intune
description: W tym artykule zawarto informacje ułatwiające określenie wymagań scenariusza przypadku użycia i podrzędnego przypadku użycia usługi Intune dla opartego tylko na chmurze wdrożenia usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 703509c316a22995d26223f6c386de0a2ec66c31
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882717"
---
# <a name="determine-use-case-scenario-requirements"></a>Określanie wymagań scenariusza przypadku użycia

W tej sekcji określisz wymagania dla każdej grupy organizacyjnej w ramach poszczególnych scenariuszy przypadków użycia. Ten proces ułatwi Ci lepsze przygotowanie innych obszarów planowania wdrożenia usługi Intune, takich jak architektura i projektowanie, dołączanie oraz wdrażanie. Może się on również okazać pomocny w zidentyfikowaniu potencjalnych luk i wyzwań powiązanych z projektem wdrożenia usługi Intune.

Poszczególne scenariusze przypadków użycia/podrzędnych przypadków użycia i powiązane z nimi grupy organizacyjne oraz platformy urządzeń mobilnych mogą mieć różne zestawy wymagań. Na przykład firmowy scenariusz przypadku użycia może wymagać, by rejestracja urządzeń w usłudze Intune odbywała się przy użyciu bardziej restrykcyjnych ustawień urządzenia, takich jak 6-znakowy kod PIN lub wyłączenie kopii zapasowej w chmurze. Twój scenariusz przypadku użycia BYOD („Przynieś własne urządzenie”) może być mniej restrykcyjny i umożliwiać stosowanie 4-znakowego kodu PIN i kopii zapasowej w chmurze.

Poszczególne grupy organizacyjne dla firmowego scenariusza przypadku użycia mogą również mieć różne zestawy wymagań (np. ustawienia numeru PIN, profile sieci Wi-Fi lub VPN, wdrożone aplikacje). Wymagania mogą być także zdeterminowane przez możliwości platformy urządzenia mobilnego (np. czytnik linii papilarnych, profil e-mail).

Oto kilka przykładów wymagań dotyczących przypadków użycia w organizacji z różnymi zestawami wymagań dla poszczególnych scenariuszy przypadków użycia/podrzędnych przypadków użycia, grup organizacyjnych i platform urządzeń mobilnych. Poniższa tabela może również służyć jako wzór do wprowadzania wymagań przypadków użycia w Twojej organizacji:

| **Przypadki użycia** | **Podrzędne przypadki użycia** | **Grupy** | **Platformy urządzeń** | **Wymagania** |
|:---:|:---:|:---:|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje | Kadry, księgowość | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |                                                          
| Firmowe | Kierownictwo | Kadry, księgowość | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |                                                         
| Firmowe | Kiosk | Sprzedaż detaliczna | Android | Ustawienia urządzenia, profile, aplikacje |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje | Marketing, sprzedaż | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |                                                         
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownictwo | Marketing, sprzedaż | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |

Możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), aby wprowadzić wymagania przypadków użycia i podrzędnych przypadków użycia w Twojej organizacji.


## <a name="examples-of-requirements"></a>Przykładowe wymagania

Oto kilka dodatkowych przykładowych elementów, których można użyć w kolumnie „Wymagania”:

- **Bezpieczna poczta e-mail**
  - Dostęp warunkowy do lokalnego programu Exchange/usługi Exchange Online
  - Zasady ochrony aplikacji Outlook

- **Ustawienia urządzenia**
  - Ustawienie 4- lub 6-znakowego numeru PIN
  - Ograniczenie możliwości tworzenia kopii zapasowej w chmurze

- **Profile**
  - Wi-Fi
  - VPN
  - Poczta e-mail (Windows 10 Mobile)

- **Aplikacje**
  - Usługa Office 365 z zasadami ochrony aplikacji
  - Aplikacje biznesowe z zasadami ochrony aplikacji

## <a name="next-steps"></a>Następne kroki

W następnej sekcji zawarto wskazówki dotyczące [opracowywania planu wdrożenia usługi Intune](planning-guide-rollout-plan.md).
