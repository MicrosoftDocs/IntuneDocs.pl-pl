---
title: Inspekcja zmiany i zdarzeń w Microsoft Intune — Azure | Dokumentacja firmy Microsoft
description: Dowiedz się, jak przeglądać dzienniki inspekcji służące do rejestrowania działań usługi Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93072ba4730de0252f54d93fa1169062d496ce38
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394905"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Korzystaj z dzienników inspekcji do śledzenia i monitorowania zdarzeń w programie Microsoft Intune

Dzienniki inspekcji uwzględniają rekord działań, które generują zmiany w usłudze Microsoft Intune. Tworzyć, aktualizować (edytować), usuwanie, przypisywanie i akcje zdalne tworzenie zdarzeń inspekcji, które Administratorzy mogą sprawdzić dla większości obciążeń usługi Intune. Inspekcja jest włączona domyślnie dla wszystkich klientów. Nie można wyłączyć.

> [!NOTE]
> Zdarzenia inspekcji rozpoczęto nagrywanie wydawania funkcji grudnia 2017 r. Wcześniejsze zdarzenia nie są dostępne.

## <a name="who-can-access-the-data"></a>Kto może uzyskać dostęp do danych?

Dzienniki inspekcji mogą przeglądać użytkownicy z następującymi uprawnieniami:

- Administrator globalny
- Administrator usługi Intune
- Administratorzy przypisani do roli usługi Intune z uprawieniami **Dane inspekcji** - **Odczyt**

## <a name="audit-logs-for-intune-workloads"></a>Dzienniki inspekcji dla obciążeń usługi Intune

Dzienniki inspekcji można przeglądać w grupie monitorowania dla poszczególnych obciążeń usługi Intune:

1. W witrynie [Azure Portal](https://portal.azure.com/) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz obciążenie, aby przejrzeć dzienniki inspekcji. Na przykład wybierz **urządzeń**.
3. W obszarze **monitorowanie**, wybierz **dzienniki inspekcji**.

## <a name="route-logs-to-azure-monitor"></a>Kierowanie dzienników do usługi Azure Monitor

Dzienniki inspekcji i operacyjne dzienniki też mogą być kierowane do usługi Azure Monitor. W **dzienniki inspekcji**, wybierz opcję **Eksportuj ustawienia danych**:

![Dane dziennika są eksportowane do usługi Azure monitor, wybierając pozycję Ustawienia danych eksportu w usłudze Intune](./media/audit-logs-export-data-settings.png)

Więcej informacji na temat tej funkcji zawiera artykuł [Send log data to storage, event hubs, or log analytics](review-logs-using-azure-monitor.md) (Wysyłanie danych dziennika do magazynu, centrów zdarzeń lub analizy dzienników).

## <a name="review-audit-events"></a>Przeglądanie zdarzeń inspekcji

![Wybierz dzienniki inspekcji w usłudze Intune, aby zobaczyć akcje i daty, kiedy wystąpiły zdarzenia](./media/monitor-audit-logs.png "dzienniki inspekcji")

Domyślny widok listy dziennika inspekcji zawiera następujące elementy:

- Data i godzina wystąpienia
- Zainicjowane przez (aktor)
- Nazwa aplikacji
- Aktywność
- Elementy docelowe
- Kategoria
- Stan

Aby wyświetlić bardziej szczegółowe informacje o zdarzeniu, wybierz element na liście:

![Uzyskiwanie bardziej szczegółowych informacji na temat kto zrobił, co w inspekcji dzienników w usłudze Intune](./media/monitor-audit-log-detail.png "szczegółach dziennika inspekcji")

> [!NOTE]
> **Zainicjowane przez (Aktor)** zawiera informacje na temat opracowywali zadania i gdzie zostało uruchomione. Na przykład, jeśli działanie zostanie uruchomione w usłudze Intune w witrynie Azure Portal, w obszarze **Aplikacja** zawsze jest podane **rozszerzenie portalu usługi Microsoft Intune**, a w obszarze **Identyfikator aplikacji** zawsze znajduje się ten sam identyfikator GUID.
> 
> Sekcja **Elementy docelowe** zawiera wiele elementów docelowych oraz właściwości, które zostały zmienione.  

## <a name="filter-audit-events"></a>Filtrowanie zdarzeń inspekcji

Każde obciążenie zawiera element menu, który wstępnie filtruje kategorię zdarzeń inspekcji skojarzoną z danym okienkiem. Oddzielna opcja filtrowania umożliwia zmianę kategorii na inną oraz filtrowanie szczegółów akcji zdarzeń w ramach danej kategorii. Możesz wyszukiwać według nazwy UPN, takich jak użytkownik, który wykonał akcję. Filtr zakresu dat umożliwia ustawienie opcji 24 godzin, 7 dni lub 30 dni. Domyślnie są pokazywane zdarzenia inspekcji z ostatnich 30 dni.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Korzystanie z interfejsów API programu Graph w celu pobrania zdarzeń inspekcji

Aby uzyskać szczegółowe informacje dotyczące jednego roku zdarzeń inspekcji przy użyciu interfejsu API programu graph, zobacz [listy auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Następne kroki

[Wyślij dane dzienników z magazynem, usługa event hubs lub dziennika analizy](review-logs-using-azure-monitor.md).

[Przejrzyj dzienniki ochrony aplikacji klienta](app-protection-policy-settings-log.md).
