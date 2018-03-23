---
title: Przebieg typowego cyklu migracji do usługi Intune
titlesuffix: Microsoft Intune
description: W tym artykule wyjaśniono przebieg cyklu migracji do usługi Microsoft Intune i przedstawiono przykłady, które ułatwią Ci obsługę tych cykli.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 238ea903353b75a69d1c2fe2a836f9e89992d2d7
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2018
---
# <a name="typical-migration-cycle"></a>Typowy cykl migracji

Organizacje często rozpoczynają migrację do usługi Intune od realizacji niewielkiego programu pilotażowego obejmującego swoim zasięgiem wybranych użytkowników z działu IT. Ponadto w celu pomyślnego określenia ram czasowych migracji organizacja może stanąć przed koniecznością omówienia takich kwestii, jak gotowość grupy do zmiany, liczba użytkowników, złożoność, wymagania, lokalizacja i ryzyko biznesowe.

Poniżej przedstawiono przykładowy sposób, w jaki można uwzględnić w harmonogramie grupy docelowe:

  | **Grupy docelowe poddane migracji** | **Okres 1** | **Okres 2** | **Okres 3** | **Okres 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Mały program pilotażowy w dziale IT (50 użytkowników) | Ogłoszenie planu | Przekazanie instrukcji dotyczących rejestrowania | Wyznaczenie ostatecznego terminu | Wymuszenie dostępu warunkowego |  |                                                        
| Rozszerzony program pilotażowy w dziale IT (200 użytkowników) |  | Ogłoszenie planu | Przekazanie instrukcji dotyczących rejestrowania | Wyznaczenie ostatecznego terminu | Wymuszenie dostępu warunkowego |
| Faza 1 migracji: zaawansowani użytkownicy (2000) |  |  | Ogłoszenie planu | Przekazanie instrukcji dotyczących rejestrowania | Wyznaczenie ostatecznego terminu |
| Faza 2 migracji: wschodnie stany USA |  |  |  | Ogłoszenie planu | Przekazanie instrukcji dotyczących rejestrowania |
| Wszystkie regiony |  |  |  |  | Ogłoszenie planu |

## <a name="customer-migration-case-study"></a>Analiza przypadku migracji klienta

### <a name="adatum-corporation"></a>Adatum Corporation

Zobacz, [jak firma Adatum Corporation poradziła sobie z procesem migracji z usługi MDM innej firmy do usługi Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Monitorowanie migracji

Usługa Intune zapewnia wiele sposobów na monitorowanie migracji:

* Widoki grup użytkowników usługi Intune

* Zestaw wbudowanych raportów

* Alerty w obrębie konsoli

Prześledź liczbę użytkowników rejestrujących urządzenia w kolejnych fazach, aby wykonać następujące czynności:

-   Ocena skuteczności planu komunikacji.

-   Szacunkowa ocena wpływu wymuszania dostępu warunkowego.


## <a name="post-migration"></a>Po migracji

Po przeprowadzeniu migracji do usługi Intune zrezygnuj z usługi poprzedniego dostawcy rozwiązań MDM i anuluj subskrypcję usługi. Ponadto usuń wszelkie niepotrzebne wymagania dotyczące infrastruktury, postępując zgodnie z instrukcjami dostawcy rozwiązania MDM.
