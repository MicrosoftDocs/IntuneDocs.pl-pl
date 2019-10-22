---
title: Inspekcja zmian i zdarzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się, jak przeglądać dzienniki inspekcji służące do rejestrowania działań usługi Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd00a0ae4cb6c3b150fe40cfc6cd7b71cfa973f3
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585238"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Śledzenie i monitorowanie zdarzeń w usłudze Microsoft Intune za pomocą dzienników inspekcji

Dzienniki inspekcji uwzględniają rekord działań, które generują zmiany w usłudze Microsoft Intune. Wszystkie akcje tworzenia, aktualizowania (edytowania), usuwania i przypisywania oraz akcje zdalne powodują tworzenie zdarzeń inspekcji, które administratorzy mogą przeglądać dla większości obciążeń usługi Intune. Inspekcja jest domyślnie włączona dla wszystkich klientów. Nie można jej wyłączyć.

> [!NOTE]
> Rejestrowanie zdarzeń inspekcji rozpoczęto wraz z opublikowaniem funkcji w grudniu 2017 r. Wcześniejsze zdarzenia nie są dostępne.

## <a name="who-can-access-the-data"></a>Kto może uzyskać dostęp do danych?

Dzienniki inspekcji mogą przeglądać użytkownicy z następującymi uprawnieniami:

- Administrator globalny
- Administrator usługi Intune
- Administratorzy przypisani do roli usługi Intune z uprawieniami **Dane inspekcji** - **Odczyt**

## <a name="audit-logs-for-intune-workloads"></a>Dzienniki inspekcji dla obciążeń usługi Intune

Dzienniki inspekcji można przeglądać w grupie monitorowania dla poszczególnych obciążeń usługi Intune:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz obciążenie, dla którego chcesz przejrzeć dzienniki inspekcji. Na przykład wybierz pozycję **Urządzenia**.
3. W obszarze **Monitorowanie** wybierz pozycję **Dzienniki inspekcji**.

## <a name="route-logs-to-azure-monitor"></a>Kierowanie dzienników do usługi Azure Monitor

Dzienniki inspekcji i dzienniki operacyjne można też kierować do usługi Azure Monitor. W obszarze **Dzienniki inspekcji** wybierz pozycję **Eksportuj ustawienia danych**:

![Eksportowanie danych dziennika do usługi Azure monitor przez wybranie pozycji Eksportuj ustawienia danych w usłudze Intune](./media/monitor-audit-logs/audit-logs-export-data-settings.png)

> [!NOTE]
> Aby uzyskać więcej informacji na temat tej funkcji i zapoznać się z wymaganiami wstępnymi dotyczącymi korzystania z niej, zobacz [wysyłanie danych dziennika do magazynu, centrów zdarzeń lub usługi log Analytics](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Przeglądanie zdarzeń inspekcji

![Wybieranie dzienników inspekcji w usłudze Intune, aby zobaczyć akcje i daty wystąpienia zdarzeń](./media/monitor-audit-logs/monitor-audit-logs.png "Dzienniki inspekcji")

Domyślny widok listy dziennika inspekcji zawiera następujące elementy:

- Data i godzina wystąpienia
- Zainicjowane przez (aktor)
- Nazwa aplikacji
- Aktywność
- Elementy docelowe
- Kategoria
- Stan

Aby wyświetlić bardziej szczegółowe informacje o zdarzeniu, wybierz element na liście:

![Uzyskiwanie bardziej szczegółowych informacji na temat tego, kto co zrobił, w dziennikach inspekcji w usłudze Intune](./media/monitor-audit-logs/monitor-audit-log-detail.png "|::ref2::|")

> [!NOTE]
> Część **Zainicjowane przez (aktor)** obejmuje informacje na temat tego, kto i gdzie uruchomił zadanie. Na przykład, jeśli działanie zostanie uruchomione w usłudze Intune w witrynie Azure Portal, w obszarze **Aplikacja** zawsze jest podane **rozszerzenie portalu usługi Microsoft Intune**, a w obszarze **Identyfikator aplikacji** zawsze znajduje się ten sam identyfikator GUID.
>
> Sekcja **Elementy docelowe** zawiera wiele elementów docelowych oraz właściwości, które zostały zmienione.  

## <a name="filter-audit-events"></a>Filtrowanie zdarzeń inspekcji

Każde obciążenie zawiera element menu, który wstępnie filtruje kategorię zdarzeń inspekcji skojarzoną z danym okienkiem. Oddzielna opcja filtrowania umożliwia zmianę kategorii na inną oraz filtrowanie szczegółów akcji zdarzeń w ramach danej kategorii. Można wyszukiwać dane według nazwy UPN, na przykład użytkownika, który wykonał akcję. Filtr zakresu dat umożliwia ustawienie opcji 24 godzin, 7 dni lub 30 dni. Domyślnie są pokazywane zdarzenia inspekcji z ostatnich 30 dni.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Korzystanie z interfejsów API programu Graph w celu pobrania zdarzeń inspekcji

Aby uzyskać szczegółowe informacje na temat korzystania z interfejsu API programu Graph w celu pobrania zdarzeń inspekcji z ostatniego roku, zobacz [List auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0) (Wyświetlanie listy obiektów auditEvent).

## <a name="next-steps"></a>Następne kroki

[Wysyłanie danych dzienników do magazynu, centrów zdarzeń lub analizy dzienników](review-logs-using-azure-monitor.md).

[Przejrzyj dzienniki ochrony aplikacji klienta](../apps/app-protection-policy-settings-log.md).
