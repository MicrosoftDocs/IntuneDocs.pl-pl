---
title: "Określanie docelowych grup i harmonogramów wdrożenia usługi Intune | Microsoft Docs"
description: "W tym artykule zawarto informacje ułatwiające określenie docelowych grup i harmonogramów wdrożenia dla implementacji tylko w chmurze usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2a970badf5ac18a05115a72dc267ee455ba4628d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="develop-an-intune-rollout-plan"></a>Opracowywanie planu wdrożenia usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Informacje przedstawione w tej sekcji ułatwiają określenie grup organizacyjnych, których będzie dotyczyć wdrożenie usługi Intune, harmonogramu wdrożenia dla każdej z tych grup oraz metod rejestracji, które zostaną użyte.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Określanie docelowych grup i harmonogramów wdrożenia usługi Intune

Należy najpierw określić grupy, które zostaną objęte wdrożeniem usługi Intune. Grupy docelowe zostały wcześniej omówione w sekcji opisującej scenariusze przypadków użycia usługi Intune.

Następnie należy określić harmonogramy, zgodnie z którym dla poszczególnych grup będzie miało miejsce wdrożenie usługi Intune. Zwykle wymaga to dyskusji w ramach zespołu wdrożenia usługi Intune i grup docelowych w celu określenia najbardziej odpowiedniego harmonogramu wdrożenia dla każdej grupy.

Na przykład zespół wdrożenia usługi Intune w celu ustalenia harmonogramu wdrożenia może omówić takie czynniki, jak gotowość grupy do przeprowadzania zmian, liczba użytkowników i urządzeń, typy platformy urządzeń, wymagania, lokalizacja geograficzna oraz ryzyko biznesowe.

Organizacje często decydują się rozpocząć wdrożenie usługi Intune od projektu pilotażowego skierowanego do małej grupy użytkowników w dziale IT. Pilotaż można następnie rozszerzyć, aby obejmował szerszą grupę użytkowników z działu IT i uczestników z innych grup organizacyjnych. Po pomyślnym przeprowadzeniu pilotażu organizacje są gotowe do rozpoczęcia pełnego wdrożenia produkcyjnego obejmującego pozostałe grupy w organizacji. Poniżej przedstawiono przykłady różnych grup i faz wdrożenia:

-   **Pilotaż:** pierwsza faza wdrożenia powinna dotyczyć użytkowników pilotażowych. Użytkownicy pilotażowi powinni wiedzieć, że są pierwszymi użytkownikami nowego rozwiązania i wyrazić chęć przekazania opinii w celu poprawienia konfiguracji, dokumentacji i powiadomień, co ułatwi pracę wszystkich innych użytkowników w późniejszych fazach wdrożenia. Tymi użytkownikami nie powinni być dyrektorzy ani osoby VIP.

-   **Działy:** dla każdego działu może zostać przeprowadzona osobna faza wdrożenia. Ten scenariusz będzie dotyczyć od razu całego działu. W tym typie wdrożenia w poszczególnych fazach urządzenia przenośne będą prawdopodobnie używane w taki sam sposób i będą uzyskiwać dostęp do tych samych aplikacji. Użytkownicy najprawdopodobniej będą mieć również te same typy zasad.

-   **Lokalizacja geograficzna:** ten typ wdrożenia polega na przeprowadzeniu wdrożenia dla wszystkich użytkowników w określonej lokalizacji geograficznej — może to być ten sam kontynent, kraj, region lub budynek tej samej firmy. Ten typ wdrożenia etapowego umożliwia skoncentrowanie się na określonych lokalizacjach użytkowników. Może to zapewnić bardziej [dokładne](#user-assisted-enrollment) podejście z powodu ograniczenia liczby lokalizacji, w których jednocześnie ma miejsce wdrożenie usługi Intune. Ponieważ istnieje możliwość, że różne działy lub przypadki użycia znajdują się w tej samej lokalizacji, różne przypadki użycia mogą być wdrażane w tym samym czasie.

-   **Platforma:** ten typ wdrożenia polega na wdrożeniu podobnych platform w tym samym czasie. Przykładem może być wdrożenie wszystkich urządzeń z systemem iOS w pierwszym miesiącu, następnie urządzeń z system Android, a na końcu urządzeń z systemem Windows. Ten typ wdrożenia etapowego upraszcza kwestię pomocy technicznej. W takiej sytuacji pomoc techniczna musi obsługiwać tylko jedna platformę jednocześnie.

Oto przykład planu wdrożenia usługi Intune, który obejmuje grupy docelowe i przedziały czasu:

| **Faza wdrożenia** | **Lipiec** | **Sierpień** | **Wrzesień** | **Październik** |
|:---:|:---:|:---:|:---:|:---:|
| Ograniczony pilotaż | Dział IT (50 użytkowników) |  |  |  |                                                         
| Rozszerzony pilotaż | Dział IT (200 użytkowników), kierownictwo działu IT (10 użytkowników) |  |  |  |                                                         
| Faza 1 wdrożenia produkcyjnego |  | Sprzedaż i marketing (2000 użytkowników) |  |  |
| Faza 2 wdrożenia produkcyjnego |  |  | Sprzedaż detaliczna (1000 użytkowników) |  |
| Faza 3 wdrożenia produkcyjnego |  |  |  | Kadry (50 użytkowników), księgowość (40 użytkowników), kierownictwo (30 użytkowników) |

## <a name="determine-the-intune-enrollment-approach"></a>Określenie podejścia do wdrożenia usługi Intune

Po określeniu grup docelowych i harmonogramów wdrożenia usługi Intune następnym krokiem jest wybranie najbardziej odpowiedniego podejścia do wdrożenia usługi Intune dla każdej grupy. Istnieją różne metody wdrożenia, których organizacje mogą użyć na potrzeby wdrożenia usługi Intune. Typowe metody wdrożenia to samoobsługa użytkowników, asystowana rejestracja użytkowników i podejście techniczne.

### <a name="user-self-service"></a>Samoobsługa użytkowników

W tym podejściu użytkownik jest odpowiedzialny za rejestrowanie własnego urządzenia, zazwyczaj postępując zgodnie z instrukcjami dotyczącymi rejestracji dostarczonymi przez jego organizację IT. To podejście jest najczęściej stosowane w organizacjach i jest bardziej skalowalne niż asystowana rejestracja użytkowników.

### <a name="user-assisted-enrollment"></a>Asystowana rejestracja użytkowników

Jest to określane jako podejście „dokładne”, zgodnie z którym członek zespołu IT asystuje użytkownikom podczas procesu rejestracji — osobiście lub za pomocą programu Skype. Ta metoda jest często stosowana w przypadku kadry kierowniczej i innych grup, które mogą wymagać większej pomocy podczas procesu rejestracji.

### <a name="it-tech-fair"></a>Podejście techniczne

Inną opcja rejestracji użytkowników w usłudze Intune jest wykorzystanie podejścia technicznego. W takim przypadku grupa IT utworzy punkt asysty rejestrowania w usłudze Intune, gdzie użytkownicy będą mogli uzyskiwać informacje dotyczące rejestracji w usłudze Intune, zadawać pytania i uzyskiwać pomoc dotyczącą procesu rejestracji. Użycie tej opcji może być korzystne zarówno dla grupy pracowników IT, jak i użytkowników, szczególnie podczas wczesnych faz wdrażania usługi Intune.

Oto przykład planu wdrożenia usługi Intune przy użyciu grup docelowych, osi czasu i metod rejestracji:

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

## <a name="next-section"></a>Następna sekcja

W następnej sekcji zawarto wskazówki dotyczące [opracowywania planu komunikacji związanego z wdrożeniem usługi Intune](section-5-develop-a-rollout-communication-plan.md).

