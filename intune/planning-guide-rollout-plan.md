---
title: Określanie grup przeznaczonych do wdrożenia i harmonogramów
titlesuffix: Microsoft Intune
description: Ten artykuł pomaga określić grupy do wdrożenia w usłudze Microsoft Intune i harmonogramy tych wdrożeń.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ce6292d11b6b33bd6355074cabb3eed77fa5826
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2018
---
# <a name="develop-a-rollout-plan"></a>Opracowywanie planu wdrażania

Plan wdrożenia identyfikuje grupy organizacyjne, które mają zostać przeznaczone do wdrożenia w usłudze Intune, harmonogramy wdrożenia dla każdej grupy oraz metody rejestracji, które zostaną użyte.

## <a name="targeted-groups-and-timeframes"></a>Docelowe grupy i harmonogramy

Najpierw przejrzyj grupy, które zostały przeznaczone do wdrożenia w usłudze Intune i zidentyfikowane w [scenariuszach przypadków użycia](planning-guide-scenarios.md).

Następnie określ harmonogramy dla wszystkich grup docelowych. Zadanie to zwykle wymaga dyskusji w ramach zespołu wdrożenia usługi Intune i grup docelowych w celu określenia najbardziej odpowiedniego harmonogramu wdrożenia dla każdej grupy. Kwestie, które należy poruszyć podczas takiej dyskusji:
* Gotowość grupy do zmian
* Liczba użytkowników i urządzeń
* Typy platform urządzeń
* Wymagania
* Położenie geograficzne
* Ryzyko biznesowe

## <a name="rollout-phases"></a>Etapy wdrażania
Organizacje często decydują się rozpocząć wdrożenie usługi Intune od projektu pilotażowego skierowanego do małej grupy użytkowników w dziale IT. Projekt pilotażowy można następnie tak rozszerzyć, aby objął większą grupę użytkowników z działu IT oraz członków innych grup organizacyjnych.

### <a name="pilot"></a>Pilotaż
Pierwsza faza wdrożenia powinna dotyczyć użytkowników pilotażowych. Użytkownicy pilotażowi powinni mieć świadomość tego, że są pierwszymi użytkownikami korzystającymi z nowego rozwiązania. Powinni wyrazić chęć przekazywania opinii w celu poprawienia konfiguracji, dokumentacji i powiadomień, co ułatwi pracę wszystkim innym użytkownikom w późniejszych fazach wdrożenia. Tymi użytkownikami nie powinno być kierownictwo ani osoby VIP.

Projekt pilotażowy to doskonała okazja do przetestowania [wyzwań](planning-guide-deployment-goals.md) oraz dostosowania zebranych wcześniej [wymagań](planning-guide-requirements.md).

Uwzględnij plan [komunikacji](planning-guide-communication-plan.md), plan [pomocy technicznej](planning-guide-support-plan.md) oraz [testowanie i weryfikację](planning-guide-test-validation.md) w celu rozwiązania wszelkich problemów, póki wpływ na użytkowników jest wciąż niewielki.

### <a name="production-rollout"></a>Wdrożenie produkcyjne
Po ukończeniu projektu pilotażowego można rozpocząć pełne wdrożenie produkcyjne przeznaczone dla pozostałych grup w organizacji. Niektóre przykłady różnych grup i faz wdrożenia:

-   **Działy** <br/>Dla każdego działu może zostać przeprowadzona osobna faza wdrożenia. Proces obejmuje cały dział. W tym typie wdrożenia użytkownicy z każdego działu zwykle używają urządzenia mobilnego w taki sam sposób i będą uzyskiwać dostęp do tych samych aplikacji. Użytkownicy będą mieli prawdopodobnie te same typy zasad.

-   **Położenie geograficzne** <br/>W tej metodzie wdrożenie dotyczy wszystkich użytkowników w określonym położeniu geograficznym — może to być ten sam kontynent, kraj, region lub budynek jednej firmy. Ten typ wdrożenia etapowego umożliwia skoncentrowanie się na określonych lokalizacjach użytkowników. Może to zapewnić bardziej [dokładne](#user-assisted-enrollment) podejście z powodu ograniczenia liczby lokalizacji, w których jednocześnie ma miejsce wdrożenie usługi Intune. Ponieważ istnieje możliwość, że różne działy lub przypadki użycia znajdują się w tej samej lokalizacji, różne przypadki użycia mogą być wdrażane w tym samym czasie.

-   **Platforma** <br/>Ten typ wdrożenia polega na wdrożeniu podobnych platform w tym samym czasie. Przykładem może być wdrożenie wszystkich urządzeń z systemem iOS w pierwszym miesiącu, następnie urządzeń z system Android, a na końcu urządzeń z systemem Windows. Ten typ wdrożenia etapowego upraszcza pomoc techniczną, ponieważ musiałaby ona obsługiwać jednorazowo tylko jedną platformę.

Oto przykład planu wdrożenia usługi Intune, który obejmuje grupy docelowe i przedziały czasu:

| **Faza wdrożenia** | **Lipiec** | **Sierpień** | **Wrzesień** | **Październik** |
|:---:|:---:|:---:|:---:|:---:|
| Ograniczony pilotaż | Dział IT (50 użytkowników) |  |  |  |                                                         
| Rozszerzony pilotaż | Dział IT (200 użytkowników), kierownictwo działu IT (10 użytkowników) |  |  |  |                                                         
| Faza 1 wdrożenia produkcyjnego |  | Sprzedaż i marketing (2000 użytkowników) |  |  |
| Faza 2 wdrożenia produkcyjnego |  |  | Sprzedaż detaliczna (1000 użytkowników) |  |
| Faza 3 wdrożenia produkcyjnego |  |  |  | Kadry (50 użytkowników), księgowość (40 użytkowników), kierownictwo (30 użytkowników) |

Możesz [pobrać szablon powyższej tabeli](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), aby wprowadzić fazy wdrożenia swojej organizacji.
## <a name="match-rollout-groups-to-enrollment-approaches"></a>Dopasowanie grup wdrożenia do metod rejestracji

Po określeniu grup docelowych i harmonogramów wdrożenia usługi Intune następnym krokiem jest wybranie najbardziej odpowiedniej metody wdrożenia usługi Intune dla każdej grupy. Można użyć różnych metod rejestracji:
* Samoobsługa użytkowników
* Asystowana rejestracja użytkowników
* Podejście techniczne

### <a name="user-self-service"></a>Samoobsługa użytkowników

W tym przypadku użytkownik jest odpowiedzialny za zarejestrowanie własnego urządzenia — zazwyczaj postępując zgodnie z instrukcjami rejestracji dostarczonymi przez jego organizację IT. Ta metoda jest najczęściej stosowana w organizacjach i jest bardziej skalowalna niż asystowana rejestracja użytkowników.

### <a name="user-assisted-enrollment"></a>Rejestracja przy pomocy użytkownika

Nazywamy ją metodą dokładną. Członek zespołu IT pomaga użytkownikowi w procesie rejestracji, osobiście lub za pośrednictwem programu Skype. Ta metoda jest często stosowana w przypadku kadry kierowniczej i innych grup, które mogą wymagać większej pomocy podczas procesu rejestracji.

### <a name="it-tech-fair"></a>Podejście techniczne

Inną opcja rejestracji użytkowników w usłudze Intune jest wykorzystanie podejścia technicznego. W takim przypadku grupa IT utworzy punkt asysty rejestrowania w usłudze Intune, gdzie użytkownicy będą mogli uzyskiwać informacje dotyczące rejestracji w usłudze Intune, zadawać pytania i uzyskiwać pomoc dotyczącą procesu rejestracji. Użycie tej opcji może być korzystne zarówno dla grupy pracowników IT, jak i użytkowników — szczególnie podczas wczesnych faz wdrażania usługi Intune.

Oto zaktualizowany przykład powyższego planu wdrożenia usługi Intune obejmujący metody rejestracji:

| **Faza wdrożenia** | **Lipiec** | **Sierpień** | **Wrzesień** | **Październik** |
|:---:|:---:|:---:|:---:|:---:|
| Ograniczony pilotaż |  |  |  |  |                                                         
| Samoobsługa | IT |  |  |  |
| Rozszerzony pilotaż |  |  |  |  |                                                         
| Samoobsługa | IT |  |  |  |
| Dokładny | Kierownictwo działu IT |  |  |  |
| Faza 1 wdrożenia produkcyjnego |  | Sprzedaż i marketing |  |  |
| Samoobsługa |  | Sprzedaż i marketing |  |  |
| Faza 2 wdrożenia produkcyjnego |  |  | Sprzedaż detaliczna |  |
| Samoobsługa |  |  |  |  |
| Faza 3 wdrożenia produkcyjnego |  |  | Sprzedaż detaliczna |  |
| Samoobsługa |  |  |  | Kadry, księgowość |
| Dokładny |  |  |  | Kierownictwo |

## <a name="next-steps"></a>Następne kroki

W następnej sekcji zawarto wskazówki dotyczące [opracowywania planu komunikacji związanego z wdrożeniem usługi Intune](planning-guide-communication-plan.md).
