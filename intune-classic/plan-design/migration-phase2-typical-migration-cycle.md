---
title: "Przebieg typowego cyklu migracji do usługi Intune | Microsoft Docs"
description: "Celem tego artykułu jest wyjaśnienie, jak przebiega cykl migracji do usługi Intune i przedstawienie przykładowych sposobów obsługi cyklu przez klienta."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7130d09d7340aba94f3f9ac72743a281e0aa45ca
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-typical-migration-cycle"></a>Faza 2: Typowy cykl migracji

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

- Zobacz, [jak firma Adatum Corporation poradziła sobie z procesem migracji z usługi MDM innej firmy do usługi Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Monitorowanie migracji

Usługa Microsoft Intune zapewnia wiele sposobów na monitorowanie migracji:

1.  Widoki grup użytkowników usługi Intune

2.  Zestaw wbudowanych raportów

3.  Alerty w obrębie konsoli

Należy śledzić liczbę użytkowników rejestrujących urządzenia w kolejnych fazach, co pozwoli wykonać następujące czynności:

-   Ocena skuteczności planu komunikacji.

-   Szacunkowa ocena wpływu wymuszania dostępu warunkowego.

Dowiedz się, [jak monitorować migrację do usługi Intune](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports).

## <a name="post-migration"></a>Po migracji

Po przeprowadzeniu migracji do usługi Intune należy zrezygnować z usługi poprzedniego dostawcy rozwiązań MDM i/lub anulować subskrypcję usługi. Ponadto należy usunąć wszelkie niepotrzebne wymagania dotyczące infrastruktury, postępując zgodnie z instrukcjami dostawcy rozwiązania MDM.

