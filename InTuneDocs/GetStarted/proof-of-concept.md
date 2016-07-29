---
title: Weryfikacja koncepcji | Microsoft Intune
description: "Zalecenia dotyczące fazy weryfikacji koncepcji wdrożenia usługi Intune."
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f3c97380-23ca-40da-acbc-78108507cad7
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 57f6d51a3f1e05a7edd260b0923d099510114a9f


---

# Weryfikacja koncepcji
W fazie weryfikacji koncepcji należy skoncentrować się na określeniu możliwości spełnienia wymagań firmy przez wdrożenie. Ta faza obejmuje prostą topologię opracowaną w celu sprawdzenia poprawności określonych scenariuszy technicznych.  Wdrożenie powinno znajdować się w środowisku testowym i nie powinno obsługiwać żadnych użytkowników wdrożenia produkcyjnego.

## Dlaczego jest to istotne?
Weryfikacja koncepcji jest istotna dla zrozumienia możliwości wdrożenia przed skierowaniem do użytkowników pilotażowych. Powinna stanowić eksperyment na małą skalę, z którego dowiesz się, jak usługa Microsoft Intune będzie działać w Twoim środowisku. Powinna również umożliwić weryfikację konkretnych scenariuszy przed inwestycją w zasoby wymagane do pilotażu. Wnioski z weryfikacji koncepcji powinny mieć wpływ na projekt pilotażowy i produkcyjny.
Rozpocznij od przejrzenia pytań wstępnych, które mają pomóc w określeniu zakresu i zdefiniowaniu fazy weryfikacji koncepcji.

## Pytania wstępne
Przedyskutuj następujące pytania ze swoim zespołem ds. projektu, aby określić zakres szczegółów dotyczących projektu, odkryć potencjalne ryzyka i zdefiniować zadania możliwe do wykonania.

-   Jakie podstawowe scenariusze musi obsługiwać usługa Intune, aby spełnić wymagania organizacji dotyczące zarządzania urządzeniami?

-   Jakie funkcje chcesz zbadać i zweryfikować?

-   Jakie zasoby muszą być dostępne w środowisku testowym, aby można było zweryfikować te scenariusze?

## Cele w obszarach zainteresowań
Przejrzyj tę sekcję, aby uzyskać wskazówki dotyczące działań w obszarach zainteresowań dla tej fazy wdrożenia.

### Planowanie
Przed wdrożeniem infrastruktury do weryfikacji koncepcji należy znać scenariusze wymagające weryfikacji oraz zasoby niezbędne do przeprowadzenia weryfikacji.

### Pomoc techniczna
Dział pomocy technicznej nie musi przygotowywać się do tej fazy projektu, ponieważ nie obejmuje ona żadnych produkcyjnych użytkowników ani urządzeń. Jednak dla działu pomocy technicznej jest to okazja, aby uzyskać informacje dotyczące wdrażania i działania usługi Intune.

### Informowanie
Zespół techniczny oraz sponsorzy wykonawczy powinni mieć wgląd w postęp testowania scenariuszy. Zespół projektowy powinien mieć świadomość wniosków, które należy uwzględnić w projekcie.

### Szkolenia
Administratorzy, którzy będą zarządzać użytkownikami, urządzeniami, zasadami i aplikacjami, powinni skorzystać z fazy weryfikacji koncepcji jako okazji do poznania konsoli i funkcji usługi Intune.

### Operacje
Weryfikacja koncepcji nie wymaga trwających operacji. Jednak warto, aby zespół operacyjny poznał i zweryfikował określone scenariusze w fazie weryfikacji koncepcji.

## Wprowadzenie — lista kontrolna
Oto lista czynności ułatwiających rozpoczęcie pracy podczas fazy **weryfikacji koncepcji**.

-   Zdefiniuj kryteria sukcesu fazy weryfikacji koncepcji. Powinny one być oparte na weryfikacji wymagań technicznych i biznesowych.

-   Zidentyfikuj zasoby wymagane do weryfikacji scenariuszy testowych.

-   Zidentyfikuj odpowiednie środowiska testowe przypominające środowisko produkcyjne, na przykład wymaganą liczbę urządzeń z różnymi systemami operacyjnymi.

## Najczęstsze wyzwania
Poniżej przedstawiono niektóre wyzwania, które możesz napotkać w fazie **weryfikacji koncepcji**.

-   **Wyzwanie:** Uzyskanie zasobów technicznych i ludzkich wymaganych do weryfikacji scenariuszy przypominających produkcyjne.

    **Środki zaradcze:** Poinformuj wyraźnie, że wnioski uzyskane w środowisku do weryfikacji koncepcji pomogą udoskonalić projekt techniczny i poprawią jakość kolejnych faz. Brak zasobów w fazie weryfikacji koncepcji spowoduje, że wnioski będzie trzeba wyciągnąć po ukończeniu projektu technicznego, co może wymagać zmiany projektu niektórych elementów.

-   **Wyzwanie:** Zdefiniowanie scenariuszy testowych, które będą wymagane w produkcji.

    **Środki zaradcze:** Pracując ze sponsorem wykonawczym, siecią i zespołami użytkowników, poznaj wymagania rozwiązania do zarządzania klientami.

### Następne kroki
[Pilotaż](pilot.md)



<!--HONumber=Jul16_HO3-->


