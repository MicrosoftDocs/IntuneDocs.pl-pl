---
title: "Dzienniki inspekcji dla działań usługi Intune"
description: "Dowiedz się, jak przeglądać dzienniki inspekcji służące do rejestrowania działań usługi Intune"
keywords: 
author: dougeby
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 55499bc8126958918ac2494fc86059eb3d331c69
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="audit-logs-for-intune-activities"></a>Dzienniki inspekcji dla działań usługi Intune
Dzienniki inspekcji stanowią rekord działań, które generują zmiany w usłudze Microsoft Intune. Możesz tworzyć, aktualizować (edytować), usuwać i przypisywać akcje lub zadania zdalne, a także generować zdarzenia inspekcji, które można przeglądać. Możesz przeglądać dzienniki inspekcji dla większości obciążeń usługi Intune. Inspekcja jest domyślnie włączona dla wszystkich klientów i nie można jej wyłączyć. Rejestrowanie zdarzeń inspekcji rozpoczęto w dniu wydania funkcji w grudniu 2017 r. Wcześniejsze zdarzenia są niedostępne.

## <a name="who-can-access-the-data"></a>Kto może uzyskać dostęp do danych?
Dzienniki inspekcji mogą przeglądać użytkownicy z następującymi uprawnieniami:
- Administrator globalny
- Administrator usługi Intune
- Administratorzy przypisani do roli usługi Intune z uprawieniami **Dane inspekcji** - **Odczyt**

## <a name="audit-logs-for-intune-workloads"></a>Dzienniki inspekcji dla obciążeń usługi Intune
Dzienniki inspekcji można przeglądać w grupie monitorowania dla poszczególnych obciążeń usługi Intune.  
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W okienku **Intune** wybierz obciążenie, dla którego chcesz przejrzeć dzienniki inspekcji, na przykład **Urządzenia**.
4. W grupie **Monitorowanie** dla danego obciążenia wybierz pozycję **Dzienniki inspekcji**.

## <a name="review-audit-events"></a>Przeglądanie zdarzeń inspekcji
![Dzienniki inspekcji](./media/monitor-audit-logs.png "Dzienniki inspekcji")

Domyślny widok listy dziennika inspekcji zawiera następujące elementy:    

- data i godzina wystąpienia
- Zainicjowane przez (aktor)
- Nazwa aplikacji
- Aktywność
- Elementy docelowe
- Kategoria
- Stan

Kliknięcie elementu w widoku listy powoduje wyświetlenie wszystkich dostępnych szczegółów na jego temat.

![Dzienniki inspekcji](./media/monitor-audit-log-detail.png "Dzienniki inspekcji")

> [!Note]    
> Sekcja **Zainicjowane przez (aktor)** w szczegółach dziennika inspekcji zawiera informacje o tym, kto wykonał działanie i gdzie zostało ono wykonane. Na przykład, jeśli działanie zostanie wykonane w usłudze Intune w witrynie Azure Portal, w obszarze **Aplikacja** zawsze jest podane **rozszerzenie portalu usługi Microsoft Intune**, a w obszarze **Identyfikator aplikacji** zawsze znajduje się ten sam identyfikator GUID. 
>    
> Sekcja **Elementy docelowe** może zawierać wiele elementów docelowych oraz właściwości, które zostały zmienione.  


## <a name="filter-audit-events"></a>Filtrowanie zdarzeń inspekcji
Każde obciążenie zawiera element menu, który wstępnie filtruje kategorię zdarzeń inspekcji skojarzoną z danym okienkiem. Oddzielna opcja filtrowania umożliwia zmianę kategorii na inną oraz filtrowanie szczegółów akcji zdarzeń w ramach danej kategorii. Można wyszukiwać dane według nazwy UPN (na przykład użytkownika, który wykonał akcję). Filtr zakresu dat umożliwia ustawienie opcji 24 godzin, 7 dni lub 30 dni. Domyślnie są wyświetlane zdarzenia inspekcji z ostatnich 30 dni.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Korzystanie z interfejsów API programu Graph w celu pobrania zdarzeń inspekcji
Aby uzyskać szczegółowe informacje na temat korzystania z interfejsu API programu Graph w celu pobrania zdarzeń inspekcji z ostatniego roku, zobacz temat [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list) (Wyświetlanie listy obiektów auditEvent).