---
title: Tworzenie raportu w usłudze Power BI na podstawie źródła danych OData
titlesuffix: Microsoft Intune
description: Tworzenie wizualizacji w formie mapy drzewa w programie Power BI Desktop za pomocą interakcyjnego filtru z interfejsu API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c38b3f0656f6b285c38da39971f9f124b5448c14
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229517"
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>Tworzenie raportu w usłudze Power BI na podstawie źródła danych OData

W tym artykule wyjaśniono, jak utworzyć wizualizację w formie mapy drzewa, posługując się programem Power BI Desktop z interakcyjnym filtrem. Przykładowo dyrektor finansowy mógł poprosić o informacje o tym, jak wygląda ogólny rozkład urządzeń w porównaniu z samymi urządzeniami firmowymi i samymi urządzeniami osobistymi. Mapa drzewa daje wgląd w ogólną liczbę urządzeń różnych typów. Możesz zobaczyć liczbę urządzeń z systemami iOS, Android i Windows, które należą do firmy lub do pracowników.

### <a name="overview-of-creating-the-chart"></a>Przegląd tworzenia wykresu

Aby utworzyć ten wykres:
1. Zainstalujesz program Power BI Desktop, jeśli jeszcze go nie masz.
2. Połączysz się z modelem danych magazynu danych usługi Intune, aby pobrać bieżące dane dla modelu.
3. Utworzysz relacje modelu danych lub będziesz nimi zarządzać.
4. Utworzysz wykres z danymi z tabeli **devices**.
5. Utworzysz filtr interakcyjny.
6. Wyświetlisz gotowy wykres.

### <a name="a-note-about-tables-and-entities"></a>Uwaga dotycząca tabel i jednostek

W usłudze Power BI pracuje się z tabelami. Tabela zawiera pola danych. Każde pole danych ma typ danych. Pole może zawierać tylko dane o określonym typie danych. Typy danych to liczby, tekst, daty i tak dalej. Tabele w usłudze Power BI są podczas ładowania modelu wypełniane najnowszymi danymi historycznymi dzierżawy. Chociaż konkretne dane zmieniają się w czasie, struktura tabeli pozostaje niezmienna, chyba że zaktualizowany zostanie bazowy model danych.

Nieco mylące może być użycie terminów _jednostka_ i _tabela_. Model danych jest dostępny za pośrednictwem źródła danych OData. Kontenery, które w usłudze Power BI są nazywane tabelami, w środowisku OData nazywane są jednostkami. Oba te terminy odnoszą się do tego samego elementu do przechowywania danych.

## <a name="install-power-bi-desktop"></a>Instalowanie programu Power BI Desktop

Zainstaluj najnowszą wersję aplikacji Power BI Desktop. Aplikację Power BI Desktop możesz pobrać z witryny: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Łączenie się ze źródłem danych OData dla magazynu danych usługi Intune swojej dzierżawy

> [!Note]  
> Wymagane jest uprawnienie do **raportów** w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Autoryzacja](reports-api-url.md).

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Otwórz okienko **Magazyn danych usługi Intune**.
4. Skopiuj adres URL niestandardowego źródła danych. Na przykład: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Otwórz aplikację Power BI Desktop.
6. Wybierz kolejno pozycje **Pobierz dane** > **Źródło danych Odata**.
7. Wklej adres URL niestandardowego źródła danych w polu adresu URL w oknie **Źródło danych OData**.
8. Wybierz pozycję **Podstawowe**.

    ![Źródło danych OData dla magazynu danych usługi Intune dzierżawy](media/reports-create-01-odatafeed.png)

9. Wybierz przycisk **OK**.
10. Wybierz pozycję **Konto organizacji**, a następnie zaloguj się za pomocą poświadczeń usługi Intune.

    ![Poświadczenia konta organizacyjnego](media/reports-create-02-org-account.png)

11. Wybierz polecenie **Połącz**. Zostanie otwarty Nawigator z listą tabel w magazynie danych usługi Intune.

    ![Zrzut ekranu przedstawiający Nawigator — lista tabel magazynu danych](media/reports-create-02-loadentities.png)

12. Wybierz tabele **devices** i **ownerTypes**.  Wybierz polecenie **Załaduj**. Usługa Power BI załaduje dane do modelu.

## <a name="create-a-relationship"></a>Tworzenie relacji

Zaimportować możesz wiele tabel, aby przeanalizować nie tylko dane w pojedynczej tabeli, ale także powiązane dane w różnych tabelach.  Usługa PowerBI ma funkcję o nazwie **autowykrywanie**, która próbuje automatycznie znaleźć i utworzyć relacje. Tabele w magazynie danych zostały zbudowane tak, aby współpracowały z funkcją autowykrywania usługi Power BI. Jednak nawet wtedy, gdy usługa PowerBI nie wykryje automatycznie relacji, nadal masz możliwość zarządzania nimi.

![Zarządzanie relacjami pokrewnych danych w tabelach](media/reports-create-03-managerelationships.png)

1. Wybierz pozycję **Zarządzaj relacjami**.
2. Jeśli usługa Power BI nie wykryła jeszcze relacji, wybierz pozycję **Wykryj automatycznie**.

Relacja jest wyświetlana w kolumnach Od i Do. W tym przykładzie pole danych **ownerTypeKey** w tabeli **devices** jest połączone z polem danych **ownerTypeKey** w tabeli **ownerTypes**. Relacja zostanie użyta do wyszukania zwykłej nazwy dla kodu typu urządzenia w tabeli **devices**.

## <a name="create-a-treemap-visualization"></a>Tworzenie wizualizacji w formie mapy drzewa

Wykres mapy drzewa pokazuje hierarchiczne dane w postaci pól zawierających pola. Każda gałąź hierarchii to pole zawierające mniejsze pola reprezentujące podgałęzie. W programie Power BI Desktop możesz utworzyć mapę drzewa z danymi usługi Intune.

![Wizualizacje mapy drzewa usługi Power BI](media/reports-create-03-treemap.png)

1. Wybierz typ wykresu. Wybierz pozycję **Mapa drzewa**.
2. W modelu danych znajdź tabelę **devices**.
3. Rozwiń **tabelę devices** i w panelu **Pola** wybierz pole danych **manufacturer**.
4. Przeciągnij pole danych **manufacturer** na wykres mapy drzewa na kanwie raportu.
5. Przeciągnij pole danych **deviceKey** z tabeli **devices** do sekcji **Wartości** w okienku **Wizualizacje** i upuść je na pole z etykietą **Upuść pole danych tutaj**.  

Masz teraz wizualizację pokazującą rozkład producentów urządzeń w organizacji.

![Mapa drzewa z danymi — rozkład producentów urządzeń](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Dodawanie filtru

Do mapy drzewa możesz dodać filtr, aby za pomocą aplikacji odpowiedzieć na inne pytania.


1. Aby dodać filtr, wybierz kanwę raportu, a następnie wybierz **ikonę fragmentatora** (![Mapa drzewa z modelem danych i obsługiwanymi relacjami](media/reports-create-slicer.png)) w obszarze **Wizualizacje**.
2. Znajdź tabelę **ownerTypes** i przeciągnij pole danych **ownerTypeName** do sekcji **Filtry** w panelu **Wizualizacje**.  

   W tabeli devices znajduje się pole danych **OwnerTypeKey**, które zawiera kod informujący o tym, czy urządzenie jest własnością firmy, czy prywatną. Ponieważ za pomocą tego filtru chcesz pokazać przyjazne nazwy, znajdź tabelę **ownerTypes** i przeciągnij pole **ownerTypeName**. Ten przykład pokazuje, jak model danych obsługuje relacje między tabelami.

![Mapa drzewa z filtrem — obsługuje relacje między tabelami](media/reports-create-08_ownertype.png)

Masz teraz interakcyjny filtr, za pomocą którego możesz się przełączać między urządzeniami firmowymi i prywatnymi. Użyj tego filtru, aby zobaczyć zmiany w rozkładzie.

1. Wybierz pozycję **Firmowe**, aby zobaczyć rozkład urządzeń firmowych.
2. Wybierz pozycję **Osobiste**, aby zobaczyć urządzenia prywatne.

## <a name="next-steps"></a>Następne kroki

 - Dowiedz się więcej o [tworzeniu i zarządzaniu relacjami](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) w programie Power BI Desktop z dokumentacji usługi Power BI.
 - Zapoznaj się z [modelem magazynu danych usługi Intune](https://docs.microsoft.com/intune/reports-ref-data-model).
