---
title: "Określanie wymagań scenariusza przypadku użycia usługi Intune | Microsoft Docs"
description: "W tym artykule zawarto informacje ułatwiające określenie wymagań scenariusza przypadku użycia i podrzędnego przypadku użycia usługi Intune dla opartego tylko na chmurze wdrożenia usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Określanie wymagań scenariusza przypadku użycia usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

W tej sekcji określisz wymagania dla każdej grupy organizacyjnej w ramach poszczególnych scenariuszy przypadków użycia. Ten proces ułatwi Ci lepsze przygotowanie innych obszarów planowania wdrożenia usługi Intune, takich jak architektura i projektowanie, dołączanie oraz wdrażanie. Może się on również okazać pomocny w zidentyfikowaniu potencjalnych luk i wyzwań powiązanych z projektem wdrożenia usługi Intune.

Poszczególne scenariusze przypadków użycia/podrzędnych przypadków użycia i powiązane z nimi grupy organizacyjne oraz platformy urządzeń przenośnych mogą mieć różne zestawy wymagań. Na przykład firmowy scenariusz przypadku użycia może wymagać zarejestrowania urządzeń w usłudze Intune z bardziej restrykcyjnym zestawem ustawień urządzenia (np. 6-znakowy numer PIN, wyłączenie możliwości tworzenia kopii zapasowej w chmurze) w porównaniu ze scenariuszem przypadku użycia „Przynieś własne urządzenie” (BYOD) wymagającym mniej restrykcyjnych ustawień (np. 4-znakowy numer PIN, możliwość tworzenia kopii zapasowej w chmurze).

Poszczególne grupy organizacyjne dla firmowego scenariusza przypadku użycia mogą również mieć różne zestawy wymagań (np. ustawienia numeru PIN, profile sieci Wi-Fi lub VPN, wdrożone aplikacje). Wymagania mogą być także zdeterminowane przez możliwości platformy urządzenia przenośnego (np. czytnik linii papilarnych, profil e-mail).

Oto kilka przykładów wymagań dotyczących przypadków użycia w organizacji z różnymi zestawami wymagań dla poszczególnych scenariuszy przypadków użycia/podrzędnych przypadków użycia, grup organizacyjnych i platform urządzeń przenośnych. Poniższa tabela może również służyć jako wzór do wprowadzania wymagań przypadków użycia w Twojej organizacji:

| **Przypadki użycia** | **Podrzędne przypadki użycia** | **Grupy** | **Platformy systemu operacyjnego urządzenia** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Firmowe | Pracownik przetwarzający informacje | Kadry, księgowość | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |                                                          
| Firmowe | Kierownictwo | Kadry, księgowość | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |                                                         
| Firmowe | Kiosk | Sprzedaż detaliczna | Android | Ustawienia urządzenia, profile, aplikacje |
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Pracownik przetwarzający informacje | Marketing, sprzedaż | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |                                                         
| „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) | Kierownictwo | Marketing, sprzedaż | iOS | Bezpieczna poczta e-mail, ustawienia urządzenia, profile, aplikacje |

## <a name="examples-of-requirements"></a>Przykładowe wymagania

Oto kilka dodatkowych przykładowych elementów, których można użyć w kolumnie „Wymagania” w powyższej tabeli:

- **Bezpieczna poczta e-mail**
    - Dostęp warunkowy dla lokalnego programu Exchange/usługi Exchange Online
    - Zasady ochrony aplikacji Outlook
<br></br>
- **Ustawienia urządzenia**
    - Ustawienie 4- lub 6-znakowego numeru PIN
    - Ograniczenie możliwości tworzenia kopii zapasowej w chmurze
<br></br>
- **Profile**
    - Wi-Fi
    - VPN
    - Poczta e-mail (Windows 10 Mobile)
<br></br>
- **Aplikacje**
    - Usługa Office 365 z zasadami ochrony aplikacji
    - Aplikacje biznesowe z zasadami ochrony aplikacji

## <a name="next-section"></a>Następna sekcja

W następnej sekcji zawarto wskazówki dotyczące [opracowywania planu wdrożenia usługi Intune](section-4-develop-a-rollout-plan.md).



<!--HONumber=Dec16_HO5-->


