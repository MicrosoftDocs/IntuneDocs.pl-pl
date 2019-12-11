---
title: Kierowanie dzienników do usługi Azure Monitor przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Używaj ustawień diagnostyki do wysyłania dzienników inspekcji i dzienników operacyjnych w usłudze Microsoft Intune na konto magazynu, centrów zdarzeń lub analizy dzienników na platformie Azure. Wybierz, jak długo chcesz przechowywać dane, i zobacz niektóre szacowane koszty w przypadku użycia innego rozmiaru dzierżaw.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 95191d64-9895-4f2e-8c5b-f0e85be086d8
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66acf4d8b88097c3262f44493ab72b3900781eed
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504965"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Wysyłanie danych dzienników do magazynu, centrów zdarzeń lub analizy dzienników w usłudze Intune (wersja zapoznawcza)

Usługa Microsoft Intune obejmuje wbudowane dzienniki, które zawierają informacje o środowisku:

- **Dzienniki inspekcji** zawierają szczegółowe informacje dotyczące różnych zdarzeń lub zadań, które zachodzą w usłudze Intune.
- **Dzienniki operacyjne (wersja zapoznawcza)** zawierają szczegółowe informacje dotyczące użytkowników i urządzeń, których rejestracja zakończyła się powodzeniem (lub niepowodzeniem), a także szczegółowe informacje o niezgodnych urządzeniach.
- **Dzienniki organizacyjne zgodności urządzeń (wersja zapoznawcza)** zawierają raport organizacyjny dotyczący zgodności urządzeń w usłudze Intune oraz szczegółowe informacje o niezgodnych urządzeniach.

Te dzienniki można również wysyłać do usługi Azure Monitor, łącznie z informacjami na temat kont magazynu, centrów zdarzeń i analizy dzienników. W szczególności możesz wykonywać następujące czynności:

* Archiwizowanie dzienników usługi Intune na koncie usługi Azure Storage w celu przechowywania danych lub archiwizowanie danych na określony czas.
* Przesyłanie strumieniowe dzienników usługi Intune do analizy w centrum zdarzeń platformy Azure za pomocą popularnych narzędzi do zarządzania informacjami i zdarzeniami zabezpieczeń (SIEM, Security Information and Event Management), takich jak Splunk i QRadar.
* Integrowanie dzienników usługi Intune z własnymi niestandardowymi rozwiązaniami do obsługi dzienników przez ich przesyłanie strumieniowe do centrum zdarzeń.
* Wysyłanie dzienników usługi Intune do usługi Log Analytics w celu umożliwienia korzystania z rozbudowanych wizualizacji, monitorowania i obsługi alertów dotyczących połączonych danych.

Te funkcje są częścią **ustawień diagnostyki** w usłudze Intune.

W tym artykule dowiesz się, jak używać **ustawień diagnostyki** do wysyłania danych dzienników do różnych usług, zapoznasz się z przykładami i szacowanymi kosztami oraz znajdziesz odpowiedzi na często zadawane pytania. Po włączeniu tej funkcji dzienniki będą kierowane do wybranej usługi Azure Monitor.

## <a name="prerequisites"></a>Wymagania wstępne

Do korzystania z tej funkcji są potrzebne następujące elementy:

* Subskrypcja platformy Azure: jeśli nie masz subskrypcji platformy Azure, możesz [utworzyć konto bezpłatnej wersji próbnej](https://azure.microsoft.com/free/).
* Środowisko (dzierżawa) usługi Microsoft Intune na platformie Azure
* Użytkownik pełniący rolę **administratora globalnego** lub **administratora usługi Intune** w dzierżawie usługi Intune.

W zależności od tego, dokąd chcesz przekierowywać dane z dziennika inspekcji, musisz mieć jedną z następujących usług:

* [Konto usługi Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-account-overview) z uprawnieniami *ListKeys*. Zalecamy użycie ogólnego konta magazynu, a nie konta magazynu obiektów blob. Informacje o cenach magazynu można znaleźć na stronie [kalkulatora cen usługi Azure Storage](https://azure.microsoft.com/pricing/calculator/?service=storage). 
* [Przestrzeń nazw usługi Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) na potrzeby integracji z rozwiązaniami innych firm.
* [Obszar roboczy usługi Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) na potrzeby wysyłania dzienników do usługi Log Analytics.

## <a name="send-logs-to-azure-monitor"></a>Wysyłanie dzienników do usługi Azure Monitor

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W obszarze **Monitorowanie** wybierz pozycję **Ustawienia diagnostyki**. Po pierwszym otwarciu tej funkcji włącz ją. W przeciwnym razie dodaj ustawienie.

    ![Włączanie ustawień diagnostyki w usłudze Intune w celu wysyłania dzienników do usługi Azure Monitor](./media/review-logs-using-azure-monitor/diagnostics-settings-turn-on.png)

3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź nazwę ustawień diagnostyki. To ustawienie obejmuje wszystkie wprowadzane właściwości. Na przykład wprowadź `Route audit logs to storage account`.
    - **Zarchiwizuj na koncie magazynu**: zapisuje dane dzienników na koncie usługi Azure Storage. Użyj tej opcji, jeśli chcesz zapisywać lub archiwizować dane.

        1. Wybierz tę opcję > **Konfiguruj**. 
        2. Wybierz istniejące konto magazynu z listy > **OK**.

    - **Przesyłaj strumieniowo do centrum zdarzeń**: przesyła strumieniowo dzienniki do centrum zdarzeń na platformie Azure. Jeśli chcesz analizować dane dzienników przy użyciu narzędzi SIEM, takich jak Splunk i QRadar, wybierz tę opcję.

        1. Wybierz tę opcję > **Konfiguruj**. 
        2. Wybierz istniejącą przestrzeń nazw i zasady centrum zdarzeń z listy > **OK**.

    - **Wyślij do usługi Log Analytics**: wysyła dane do usługi Azure Log Analytics. Jeśli chcesz używać wizualizacji, monitorowania i alertów dla dzienników, wybierz tę opcję.

        1. Wybierz tę opcję > **Konfiguruj**. 
        2. Utwórz nowy obszar roboczy, a następnie wprowadź szczegóły tego obszaru roboczego. Lub wybierz istniejący obszar roboczy z listy > **OK**.

            Artykuł [Azure log analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) (Obszar roboczy usługi Azure Log Analytics) zawiera bardziej szczegółowe informacje na temat tych ustawień.

    - **LOG** > **AuditLogs**: wybierz tę opcję, aby wysyłać [dzienniki inspekcji w usłudze Intune](../monitor-audit-logs.md) do konta magazynu, centrum zdarzeń lub analizy dzienników. Dzienniki inspekcji przedstawiają historię każdego zadania, które generuje zmiany w usłudze Intune, w tym informacje na temat czasu wykonania zadania i wykonującego je użytkownika.

      Jeśli chcesz użyć konta magazynu, wprowadź również liczbę dni zachowywania danych (okres przechowywania). Aby zachować dane na zawsze, należy ustawić pozycję **Przechowywanie (dni)** na `0` (zero).

    - **LOG** > **OperationalLogs**: Dzienniki operacyjne (wersja zapoznawcza) zawierają informacje dotyczące użytkowników i urządzeń, których rejestracja w usłudze Intune zakończyła się powodzeniem (lub niepowodzeniem). Dostępne są również informacje o niezgodnych urządzeniach. Wybierz tę opcję, aby wysyłać dzienniki rejestracji w usłudze Intune do konta magazynu, centrum zdarzeń lub analizy dzienników.

      Jeśli chcesz użyć konta magazynu, wprowadź również liczbę dni zachowywania danych (okres przechowywania). Aby zachować dane na zawsze, należy ustawić pozycję **Przechowywanie (dni)** na `0` (zero).

      > [!NOTE]
      > Dzienniki operacyjne są dostępne w wersji zapoznawczej. Aby przekazać opinię, w tym informacje zawarte w dziennikach operacyjnych, przejdź do witryny [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback).

    - **DZIENNIK** > **DeviceComplianceOrg**: Dzienniki organizacyjne zgodności urządzeń (wersja zapoznawcza) zawierają raport organizacyjny dotyczący zgodności urządzeń w usłudze Intune oraz informacje o niezgodnych urządzeniach. Wybierz tę opcję, aby wysyłać dzienniki zgodności do konta magazynu, centrum zdarzeń lub analizy dzienników.

      Jeśli chcesz użyć konta magazynu, wprowadź również liczbę dni zachowywania danych (okres przechowywania). Aby zachować dane na zawsze, należy ustawić pozycję **Przechowywanie (dni)** na `0` (zero).
 
      > [!NOTE]
      > Dzienniki organizacyjne zgodności urządzeń są dostępne w wersji zapoznawczej. Aby przekazać opinię, w tym informacje zawarte w raporcie, przejdź do witryny [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback).

    Po zakończeniu ustawienia będą wyglądać podobnie do następujących: 

    ![Przykładowy obraz przedstawiający wysyłanie dzienników inspekcji w usłudze Intune na konto usługi Azure Storage](./media/review-logs-using-azure-monitor/diagnostics-settings-example.png)

4. **Zapisz** zmiany. Ustawienie zostanie wyświetlone na liście. Po jego utworzeniu można zmienić ustawienia, wybierając kolejno pozycje **Edytuj ustawienie** > **Zapisz**.

## <a name="use-audit-logs-throughout-intune"></a>Korzystanie z dzienników inspekcji w usłudze Intune

Eksportowane dzienniki inspekcji mogą także zawierać informacje z innych części usługi Intune, m.in. dotyczące rejestracji, zgodności, konfiguracji, urządzeń i aplikacji klienckich.

Na przykład aby wyeksportować dzienniki inspekcji z modułu zgodności urządzeń:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzeń** > **Monitor** > **Dzienniki inspekcji**:

    ![Wybieranie dzienników inspekcji w celu przesłania danych usługi Intune do magazynu usługi Azure Monitor, centrów zdarzeń lub analizy](./media/review-logs-using-azure-monitor/audit-logs-under-monitor-in-compliance.png)

3. Wybierz pozycję **Eksportuj ustawienia danych**. Możesz włączyć opcję **Ustawienia diagnostyki**, jeśli jeszcze nie jest włączona. Możesz również wybrać miejsce, do którego mają zostać wysłane dzienniki, co zostało opisane w temacie [Wysyłanie dzienników do usługi Azure Monitor](#send-logs-to-azure-monitor) (w tym artykule).

## <a name="cost-considerations"></a>Zagadnienia dotyczące kosztów

Jeśli masz już licencję usługi Microsoft Intune, potrzebujesz subskrypcji platformy Azure, aby skonfigurować konto magazynu i centrum zdarzeń. Subskrypcja platformy Azure jest zazwyczaj bezpłatna. Płacisz jednak za zasoby platformy Azure, w tym za konto magazynu na potrzeby archiwizacji i centrum zdarzeń na potrzeby przesyłania strumieniowego. Ilość danych i koszty różnią się w zależności od rozmiaru dzierżawy.

### <a name="storage-size-for-activity-logs"></a>Rozmiar magazynu dla dzienników aktywności

Każde zdarzenie dziennika inspekcji używa około 2 KB magazynu danych. W przypadku dzierżawy ze 100 000 użytkowników może wystąpić około 1,5 mln zdarzeń dziennie. Będziesz potrzebować około 3 GB magazynu danych na dzień. Ponieważ operacje zapisu odbywają się zwykle w partiach 5-minutowych, można oczekiwać około 9000 operacji zapisu miesięcznie.

W poniższych tabelach przedstawiono szacowane koszty w zależności od rozmiaru dzierżawy. Zawierają one również konto magazynu ogólnego przeznaczenia v2 w regionie Zachodnie stany USA z opcją przechowywania danych przez co najmniej jeden rok. Aby uzyskać szacunkową wartość dla woluminu danych oczekiwanego w przypadku dzienników, użyj [kalkulatora cen usługi Azure Storage](https://azure.microsoft.com/pricing/details/storage/blobs/).

**Dziennik inspekcji z 100 000 użytkowników**

| | |
|---|---|
|Zdarzenia na dzień| 1,5 mln|
|Szacowany wolumin danych na miesiąc| 90 GB|
|Szacowany koszt miesięczny (USD)| 1,93 USD|
|Szacowany koszt roczny (USD)| 23,12 USD|

**Dziennik inspekcji z 1000 użytkowników**

| | |
|---|---|
|Zdarzenia na dzień| 15 000|
|Szacowany wolumin danych na miesiąc| 900 MB|
|Szacowany koszt miesięczny (USD)| 0,02 USD|
|Szacowany koszt roczny (USD)| 0,24 USD|

### <a name="event-hub-messages-for-activity-logs"></a>Komunikaty centrum zdarzeń dla dzienników aktywności

Zdarzenia są zazwyczaj dzielone na partie w pięciominutowych interwałach i wysyłane jako jeden komunikat ze wszystkimi zdarzeniami w danym przedziale czasu. Maksymalny rozmiar komunikatu w centrum zdarzeń wynosi 256 KB. Jeśli całkowity rozmiar wszystkich komunikatów w przedziale czasu przekroczy ten wolumin, zostanie wysłanych wiele komunikatów.

Na przykład w przypadku dużych dzierżaw z ponad 100 000 użytkowników przeważnie występuje około 18 zdarzeń na sekundę. Oznacza to 5400 zdarzeń co pięć minut (300 sekund x 18 zdarzeń). Dzienniki inspekcji to około 2 KB na zdarzenie. Oznacza to 10,8 MB danych. Dlatego w tym interwale pięciominutowym do centrum zdarzeń zostaną wysłane 43 komunikaty.

Poniższa tabela zawiera szacunkowe koszty na miesiąc dla centrum zdarzeń w wersji podstawowej w regionie Zachodnie stany USA w zależności od woluminu danych zdarzeń. Aby uzyskać szacunkową wartość dla woluminu danych oczekiwanego w przypadku dzienników, użyj [kalkulatora cen usługi Event Hubs](https://azure.microsoft.com/pricing/details/event-hubs/).

**Dziennik inspekcji z 100 000 użytkowników**

| | |
|---|---|
|Zdarzenia na sekundę| 18|
|Zdarzenia na interwał pięciominutowy| 5400|
|Wolumin na interwał| 10,8 MB|
|Komunikaty na interwał| 43|
|Komunikaty na miesiąc| 371 520|
|Szacowany koszt miesięczny (USD)| 10,83 USD|

**Dziennik inspekcji z 1000 użytkowników**

| | |
|---|---|
|Zdarzenia na sekundę|0,1 |
|Zdarzenia na interwał pięciominutowy| 52|
|Wolumin na interwał|104 KB |
|Komunikaty na interwał|1 |
|Komunikaty na miesiąc|8640 |
|Szacowany koszt miesięczny (USD)|10,80 |

### <a name="log-analytics-cost-considerations"></a>Kwestie związane z kosztami usługi Log Analytics

Aby zapoznać się z kosztami związanymi z zarządzaniem obszarem roboczym usługi Log Analytics, zobacz temat [Manage cost by controlling data volume and retention in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage) (Zarządzanie kosztami przez kontrolowanie woluminu danych i przechowywania w usłudze Log Analytics).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

Uzyskaj odpowiedzi na często zadawane pytania oraz informacje o wszelkich znanych problemach z dziennikami usługi Intune w usłudze Azure Monitor.

### <a name="which-logs-are-included"></a>Które dzienniki są uwzględniane?

Dzienniki inspekcji i dzienniki operacyjne (wersja zapoznawcza) są dostępne w przypadku routingu wykonywanego przy użyciu tej funkcji.

### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>Kiedy po wykonaniu akcji odpowiednie dzienniki zostaną wyświetlone w centrum zdarzeń?

Dzienniki są zwykle wyświetlane w centrum zdarzeń w ciągu kilku minut po wykonaniu akcji. Więcej informacji można znaleźć w temacie [Co to jest usługa Azure Event Hubs?](https://docs.microsoft.com/azure/event-hubs/).

### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>Kiedy po wykonaniu akcji odpowiednie dzienniki zostaną wyświetlone na koncie magazynu?

W przypadku kont magazynu platformy Azure opóźnienie wynosi od 5 do 15 minut po uruchomieniu akcji.

### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>Co się stanie, jeśli administrator zmieni okres przechowywania ustawienia diagnostyki?

Nowe zasady przechowywania są stosowane do dzienników zebranych po zmianie. Dzienniki zebrane przed zmianą zasad pozostają niezmienione.

### <a name="how-much-does-it-cost-to-store-my-data"></a>Ile kosztuje przechowywanie moich danych?

Koszty magazynowania zależą od rozmiaru dzienników i wybranego okresu przechowywania. Aby uzyskać listę szacowanych kosztów dzierżaw, które zależą od woluminu wygenerowanego dziennika, zobacz sekcję [Rozmiar magazynu dla dzienników aktywności](#storage-size-for-activity-logs) (w tym artykule).

### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Ile kosztuje przesyłanie strumieniowe moich danych do centrum zdarzeń?

Koszty przesyłania strumieniowego zależą od liczby komunikatów, które otrzymujesz za minutę. Szczegółowe informacje na temat sposobu obliczania kosztów oraz szacunkowych kosztów w zależności od liczby komunikatów można znaleźć w sekcji [Komunikaty centrum zdarzeń dla dzienników aktywności](#event-hub-messages-for-activity-logs) (w tym artykule).

### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Jak mogę zintegrować dzienniki inspekcji usługi Intune z moim systemem SIEM?

Użyj usługi Azure Monitor z usługą Event Hubs w celu przesyłania strumieniowego dzienników do systemu SIEM. Najpierw [prześlij strumieniowo dzienniki do centrum zdarzeń](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub). Następnie [skonfiguruj narzędzie SIEM](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) w skonfigurowanym centrum zdarzeń. 

### <a name="what-siem-tools-are-currently-supported"></a>Które narzędzia SIEM są obecnie obsługiwane?

Obecnie usługa Azure Monitor jest obsługiwana przez narzędzia [Splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar i [Sumo Logic](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (link otwiera nową witrynę internetową). Aby uzyskać więcej informacji na temat działania łączników, zobacz temat [Stream Azure monitoring data to an event hub for consumption by an external tool](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) (Przesyłanie strumieniowe danych monitorowania platformy Azure do centrum zdarzeń na potrzeby użycia w narzędziu zewnętrznym).

### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Czy mogę uzyskiwać dostęp do danych z centrum zdarzeń bez użycia zewnętrznego narzędzia SIEM?

Tak. Aby uzyskać dostęp do dzienników z aplikacji niestandardowej, możesz użyć [interfejsu API usługi Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph).

### <a name="what-data-is-stored"></a>Jakie dane są przechowywane?

Usługa Intune nie przechowuje żadnych danych przesyłanych przez potok. Usługa Intune kieruje dane do potoku usługi Azure Monitor w obrębie urzędu dzierżawy. Aby uzyskać więcej informacji, zobacz temat [Azure Monitor — przegląd](https://docs.microsoft.com/azure/azure-monitor/overview).

## <a name="next-steps"></a>Następne kroki

* [Archiwizowanie dzienników aktywności na koncie usługi Azure Storage](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Kierowanie dzienników aktywności do centrum zdarzeń](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Integrate activity logs with Log Analytics](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics) (Integrowanie dzienników aktywności przy użyciu usługi Log Analytics)
