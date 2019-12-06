---
title: Microsoft Intune reports
titleSuffix: Microsoft Intune
description: Usługa Intune udostępnia określone typy raportów z ukierunkowanymi widokami, które zawierają spójne i aktualne dane.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 05258c5363b43398dee1815bb91c50878803e426
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74391945"
---
# <a name="intune-reports"></a>Raporty usługi Intune
Raporty usługi Microsoft Intune umożliwiają wydajniejsze i proaktywne monitorowanie kondycji i działania punktów końcowych w całej organizacji, a także udostępniają inne dane raportowania w usłudze Intune. Możliwe będzie wyświetlanie na przykład raportów dotyczących zgodności urządzeń, kondycji urządzeń i trendów urządzeń. Ponadto można tworzyć raporty niestandardowe, aby uzyskać bardziej szczegółowe dane. 

> [!NOTE]
> Zmiany raportowania usługi Intune będą wprowadzane stopniowo, aby ułatwić przygotowanie i dostosowanie się do nowej struktury.

Typy raportów zorganizowano w następujących obszarach koncentracji:
- **Operacyjne** — Zapewniają aktualne, ukierunkowane dane, które ułatwiają skoncentrowanie uwagi i podejmowanie działań. Te raporty będą najbardziej przydatne dla administratorów, ekspertów w różnych dziedzinach i pracowników pomocy technicznej.
- **Organizacyjne** — Zawierają szersze podsumowanie widoku ogólnego, na przykład stan zarządzania urządzeniami. Te raporty będą najbardziej przydatne dla menadżerów i administratorów.
- **Historyczne** — Przedstawiają wzorce i trendy w wybranym okresie. Te raporty będą najbardziej przydatne dla menadżerów i administratorów.
- **Specjalistyczne** — Umożliwiają tworzenie własnych niestandardowych raportów przy użyciu danych pierwotnych. Te raporty będą najbardziej przydatne dla administratorów.

Platforma raportowania oferuje spójne i bardziej kompleksowe środowisko raportowania. Dostępne raporty zapewniają następujące funkcje:
- **Wyszukiwanie i sortowanie** — można wyszukiwać i sortować w każdej kolumnie, niezależnie od wielkości zestawu danych.
- **Stronicowanie danych** — można skanować dane na podstawie stronicowania: strona po stronie lub przechodząc do określonej strony.
- **Wydajność** — można szybko generować i wyświetlać raporty utworzone dla dużych dzierżaw.
- **Eksportowanie** — można szybko eksportować dane raportowania wygenerowane dla dużych dzierżaw.

### <a name="who-can-access-the-data"></a>Kto może uzyskać dostęp do danych?

Dzienniki mogą przeglądać użytkownicy z następującymi uprawnieniami:

- Administrator globalny
- Administrator usługi Intune
- Administratorzy przypisani do roli usługi Intune z uprawieniami **Odczyt**

## <a name="non-compliant-devices-report-operational"></a>Raport dotyczący niezgodnych urządzeń (operacyjny)
Raport dotyczący niezgodnych urządzeń zawiera dane, które są na ogół używane przez dział pomocy technicznej lub administratorów w celu identyfikowania problemów i ich rozwiązywania. Dane znajdujące się w tych raportach są aktualne, wyróżniają nieoczekiwane zachowania i umożliwiają podejmowanie działań. Raport jest dostępny obok obciążenia, dzięki czemu raport dotyczący niezgodnych urządzeń jest dostępny bez opuszczania aktywnych przepływów pracy. Ten raport zawiera funkcje filtrowania, wyszukiwania, stronicowania i sortowania. Ponadto można przechodzić do szczegółów, aby ułatwić rozwiązywanie problemów.

Aby wyświetlić raport **Niezgodne urządzenia**, wykonaj następujące czynności:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzeń** > **Niezgodne urządzenia**.

    ![Raport dotyczący niezgodnych urządzeń](./media/intune-reports/intune-reports-02.png)

## <a name="device-compliance-report-organizational"></a>Raport dotyczący zgodności urządzeń (organizacyjny)
Raporty dotyczące zgodności urządzeń z założenia mają być rozległe i zapewniać bardziej tradycyjny widok raportowania danych służący do identyfikowania zagregowanych metryk. Ten raport jest przeznaczony do pracy z dużymi zestawami danych w celu uzyskania pełnego obrazu zgodności urządzeń. Na przykład raport dotyczący zgodności urządzeń dla zgodnych urządzeń pokazuje wszystkie stany zgodności dla urządzeń, aby zapewnić szerszy widok danych niezależnie od wielkości zestawu danych. Ten raport przedstawia pełny podział rekordów, a także wygodną wizualizację zagregowanych metryk. Ten raport można wygenerować, stosując filtry i wybierając przycisk „Generuj raport”. Spowoduje to odświeżenie danych w celu wyświetlenia najnowszego stanu z możliwością wyświetlania pojedynczych rekordów, które składają się na zagregowane dane. Podobnie jak większość raportów na nowej platformie, te rekordy można sortować i przeszukiwać, aby skoncentrować się na potrzebnych informacjach. 

Aby wyświetlić wygenerowany raport stanu urządzenia, wykonaj następujące czynności:
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Raporty**, aby wyświetlić podsumowanie raportów.
3. Wybierz pozycję **Zgodność urządzenia**.
4. Wybierz filtry **Stan zgodności**, **System operacyjny** i **Własność**, aby uściślić raport.
5. Kliknij pozycję **Generuj raport** (lub **Generuj ponownie**), aby pobrać bieżące dane.

    ![Raport dotyczący zgodności urządzeń](./media/intune-reports/intune-reports-02a.png)

    > [!NOTE]
    > Ten raport **Zgodność urządzeń** zawiera sygnaturę czasową ostatniego wygenerowania raportu. 

Aby uzyskać powiązane informacje, zobacz [Wymuszanie zgodności usługi Microsoft Defender ATP z dostępem warunkowym w usłudze Intune](~/protect/advanced-threat-protection.md).

## <a name="reports-summary"></a>Podsumowanie raportów 

Raport dotyczący zgodności urządzeń jest dostępny jako raport podsumowania w obciążeniu **Raporty**. Aby wyświetlić raport dotyczący zgodności urządzeń, wykonaj następujące kroki:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Raporty**, aby wyświetlić podsumowanie raportów.

    ![Podsumowanie raportów w usłudze Intune](./media/intune-reports/intune-reports-01.png)

## <a name="device-compliance-trend-report-historical"></a>Raport dotyczący trendów zgodności urządzeń (historyczny)
Raportów dotyczących trendów zgodności urządzeń będą używać raczej administratorzy i architekci, aby identyfikować długoterminowe trendy zgodności urządzeń. Zagregowane dane są wyświetlane dla pewnego okresu czasu i są przydatne w przypadku podejmowania decyzji dotyczących przyszłych inwestycji, kierowania usprawnieniami procesów lub inicjowania sprawdzania wszelkich anomalii. Aby zobaczyć konkretne trendy, można również zastosować filtry. Dane dostarczane przez ten raport są migawką bieżącego stanu dzierżawy (niemal w czasie rzeczywistym). 

Raport dotyczący trendu zgodności urządzeń dla trendów zgodności urządzeń może przedstawiać trend stanów zgodności urządzeń w danym okresie czasu. Można określić, gdzie występowały szczyty zgodności, i odpowiednio skupić czas i nakład pracy.

Aby wyświetlić raport **Trendy**, wykonaj następujące czynności:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Raporty** > **Trendy**, aby wyświetlić trend zgodności urządzenia dla 60 dni.

    ![Raport trendów w usłudze Intune](./media/intune-reports/intune-reports-03.png)

## <a name="azure-monitor-integration-reports-specialist"></a>Raporty dotyczące integracji usługi Azure Monitor (specjalistyczne)
Aby uzyskać potrzebne dane, możesz dostosować własne raporty. Dane w raportach będą opcjonalnie dostępne za pośrednictwem usługi [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) przy użyciu usługi [Log Analytics](reports.md#log-analytics) i [skoroszytów usługi Azure Monitor](reports.md#workbooks). Te rozwiązania umożliwiają tworzenie zapytań niestandardowych, konfigurowanie alertów i tworzenie pulpitów nawigacyjnych w celu wyświetlania danych zgodności urządzeń w wybrany sposób. Ponadto dzienniki aktywności można przechowywać na koncie usługi Azure Storage, integrować je z raportami za pomocą [narzędzi zarządzania informacjami i zdarzeniami zabezpieczeń (SIEM)](https://docs.microsoft.com/microsoft-365/security/office-365-security/siem-server-integration) i korelować raporty z dziennikami aktywności usługi Azure AD. Na potrzeby raportowania niestandardowego, oprócz importowania pulpitów nawigacyjnych, można również używać skoroszytów usługi Azure Monitor.

> [!NOTE]
> Złożone funkcje raportowania wymagają subskrypcji platformy Azure.

Przykładem specjalistycznego raportu może być skorelowanie danych dotyczących własności urządzenia z danymi rejestracji platformy w raporcie niestandardowym. Następnie ten raport niestandardowy może być wyświetlany na istniejącym pulpicie nawigacyjnym w portalu usługi Azure Active Directory.

Aby tworzyć i wyświetlać raporty niestandardowe, wykonaj następujące czynności:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Raporty** > **Ustawienia diagnostyczne** i dodaj [ustawienie diagnostyczne](reports.md#diagnostic-settings).

    ![Podsumowanie raportów w usłudze Intune](./media/intune-reports/intune-reports-04.png)

3. Kliknij pozycję **Dodaj ustawienie diagnostyczne**, aby wyświetlić okienko **Ustawienia diagnostyczne**. 
4. Dodaj **nazwę** ustawień diagnostycznych. 
5. Wybierz pozycję **Wyślij do usługi Log Analytics** i wybierz ustawienia **DeviceComplianceOrg**.

    ![Podsumowanie raportów w usłudze Intune](./media/intune-reports/intune-reports-04a.png)

6. Kliknij polecenie **Zapisz**.
7. Następnie wybierz pozycję **Analiza dzienników**, aby utworzyć i uruchomić nowe zapytanie dziennika przy użyciu usługi [Log Analytics](reports.md#log-analytics).

   ![Log Analytics — zapytanie dziennika](./media/intune-reports/intune-reports-05.png)

8. Wybierz pozycję **Skoroszyty**, aby utworzyć lub otworzyć raport interaktywny przy użyciu [skoroszytów usługi Azure Monitor](reports.md#workbooks).

   ![Skoroszyty — raporty interaktywne](./media/intune-reports/intune-reports-07.png)

### <a name="diagnostic-settings"></a>Ustawienia diagnostyczne
Każdy zasób platformy Azure wymaga własnego ustawienia diagnostycznego. Ustawienie diagnostyczne definiuje dla zasobu następujące elementy:

- Kategorie dzienników i danych metryk wysyłanych do miejsc docelowych zdefiniowanych w ustawieniu. Dostępne kategorie różnią się w zależności od typu zasobu.
- Co najmniej jedno miejsce docelowe do wysłania dzienników. Bieżące miejsca docelowe obejmują obszar roboczy usługi Log Analytics, usługę Event Hubs i usługę Azure Storage.
- Zasady przechowywania dla danych przechowywanych w usłudze Azure Storage.

Pojedyncze ustawienie diagnostyczne może definiować jedno z każdego miejsca docelowego. Jeśli chcesz wysyłać dane do więcej niż jednego określonego typu miejsca docelowego (na przykład do dwóch różnych obszarów roboczych usługi Log Analytics), utwórz wiele ustawień. Każdy zasób może mieć do 5 ustawień diagnostycznych.

Aby uzyskać więcej informacji na temat ustawień diagnostycznych, zobacz [Tworzenia ustawienia diagnostycznego w celu zbierania dzienników platformy i metryk na platformie Azure](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings).

### <a name="log-analytics"></a>Usługa Log Analytics
Usługa Log Analytics to podstawowe narzędzie w witrynie Azure Portal do pisania zapytań dziennika i interaktywnego analizowania wyników zapytań. Nawet jeśli zapytanie dziennika jest używane w innym miejscu usługi Azure Monitor, zwykle jest ono pisane i testowane przy użyciu usługi Log Analytics. Aby uzyskać szczegółowe informacje na temat używania usługi Log Analytics i tworzenia zapytań dziennika, zobacz [Omówienie zapytań dziennika w usłudze Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview). 

### <a name="workbooks"></a>Skoroszyty
Skoroszyty łączą tekst, zapytania usługi Analytics, metryki platformy Azure i parametry w rozbudowanych raportach interaktywnych. Skoroszyty mogą być edytowane przez innych członków zespołu, którzy mają dostęp do tych samych zasobów platformy Azure. Aby uzyskać więcej informacji na temat skoroszytów, zobacz [Skoroszyty usługi Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/app/usage-workbooks). Ponadto możesz pracować z szablonami skoroszytów i je współtworzyć. Aby uzyskać więcej informacji, zobacz [Szablony skoroszytów usługi Azure Monitor](https://go.microsoft.com/fwlink/?linkid=867045).

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej o następujących technologiach:
- [Blog — platforma raportowania usługi Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553)
- [Azure Monitor](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-activity-logs-azure-monitor)
- [Co to jest usługa Log Analytics?](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview#what-is-log-analytics)
- [Zapytania dziennika](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview)
- [Wprowadzenie do usługi Log Analytics w usłudze Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/get-started-portal)
- [Skoroszyty usługi Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/app/usage-workbooks)
- [Zarządzanie informacjami i zdarzeniami zabezpieczeń (SIEM)](https://docs.microsoft.com/microsoft-365/security/office-365-security/siem-server-integration)
