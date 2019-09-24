---
title: Tworzenie raportu usługi Intune w usłudze Power BI na podstawie kanału informacyjnego OData
titleSuffix: Microsoft Intune
description: Tworzenie wizualizacji w formie mapy drzewa w programie Power BI Desktop za pomocą interakcyjnego filtru z interfejsu API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4494d5f75336f7152668cfa1bb6fa1cd1a94305c
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167864"
---
# <a name="create-an-intune-report-from-the-odata-feed-with-power-bi"></a>Tworzenie raportu usługi Intune w usłudze Power BI na podstawie kanału informacyjnego OData

W tym artykule opisano sposób tworzenia wizualizacji mapy drzewa danych usługi Intune przy użyciu filtru interaktywnego w aplikacji Power BI Desktop. Na przykład dyrektor finansowy chce wiedzieć, jaki odsetek urządzeń w firmie stanowią urządzenia należące do firmy, a jaki urządzenia osobiste. Mapa drzewa daje wgląd w ogólną liczbę urządzeń różnych typów. Możesz zobaczyć liczbę urządzeń z systemami iOS, Android i Windows, które należą do firmy lub do pracowników.

## <a name="overview-of-creating-the-chart"></a>Przegląd tworzenia wykresu

Aby utworzyć ten wykres:
1. Zainstalujesz program Power BI Desktop, jeśli jeszcze go nie masz.
2. Połączysz się z modelem danych magazynu danych usługi Intune, aby pobrać bieżące dane dla modelu.
3. Utworzysz relacje modelu danych lub będziesz nimi zarządzać.
4. Utworzysz wykres z danymi z tabeli **devices**.
5. Utworzysz filtr interakcyjny.
6. Wyświetlisz gotowy wykres.

### <a name="a-note-about-tables-and-entities"></a>Uwaga dotycząca tabel i jednostek

W usłudze Power BI pracuje się z tabelami. Tabela zawiera pola danych. Każde pole danych ma typ danych. Pole może zawierać tylko dane o określonym typie danych. Typy danych to liczby, tekst, daty i tak dalej. Tabele w usłudze Power BI są podczas ładowania modelu wypełniane najnowszymi danymi historycznymi dzierżawy. Chociaż konkretne dane zmieniają się w czasie, struktura tabeli pozostaje niezmienna, chyba że zaktualizowany zostanie bazowy model danych.

Nieco mylące może być użycie terminów *jednostka* i *tabela*. Model danych jest dostępny za pomocą kanału informacyjnego OData (Open Data Protocol). Kontenery, które w usłudze Power BI są nazywane tabelami, w środowisku OData nazywane są jednostkami. Oba te terminy odnoszą się do tego samego elementu do przechowywania danych. Aby uzyskać więcej informacji na temat protokołu OData, zobacz [Omówienie usługi OData](/odata/overview).

## <a name="install-power-bi-desktop"></a>Instalowanie programu Power BI Desktop

Zainstaluj najnowszą wersję aplikacji Power BI Desktop. Aplikację Power BI Desktop możesz pobrać z witryny [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Łączenie się ze źródłem danych OData dla magazynu danych usługi Intune swojej dzierżawy

> [!Note]  
> Wymagane jest uprawnienie do **raportów** w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Autoryzacja](reports-api-url.md).

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Otwórz okienko **Magazyn danych usługi Intune**, klikając link Magazyn danych w obszarze **Inne zadania** po prawej stronie bloku **Microsoft Intune — omówienie**.
3. Skopiuj adres URL niestandardowego źródła danych. Na przykład: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
4. Otwórz aplikację Power BI Desktop.
5. Na pasku menu wybierz kolejno pozycje **Plik** > **Pobierz dane** > **Kanał informacyjny OData**.
6. Wklej niestandardowy adres URL kanału informacyjnego skopiowany z wcześniejszego kroku do pola Adres URL w oknie **Kanał informacyjny OData**.
7. Wybierz pozycję **Podstawowe**.

    ![Źródło danych OData dla magazynu danych usługi Intune dzierżawy](media/reports-create-01-odatafeed.png)

8. Wybierz przycisk **OK**.
9. Wybierz pozycję **Konto organizacji**, a następnie zaloguj się za pomocą poświadczeń usługi Intune.

    ![Poświadczenia konta organizacyjnego](media/reports-create-02-org-account.png)

10. Wybierz polecenie **Połącz**. Zostanie otwarty Nawigator z listą tabel w magazynie danych usługi Intune.

    ![Zrzut ekranu przedstawiający Nawigator — lista tabel magazynu danych](media/reports-create-02-loadentities.png)

11. Wybierz tabele **devices** i **ownerTypes**.  Wybierz polecenie **Załaduj**. Usługa Power BI załaduje dane do modelu.

## <a name="create-a-relationship"></a>Tworzenie relacji

Zaimportować możesz wiele tabel, aby przeanalizować nie tylko dane w pojedynczej tabeli, ale także powiązane dane w różnych tabelach. Usługa Power BI ma funkcję **autodetect**, która podejmuje próbę znalezienia i utworzenia relacji dla użytkownika. Tabele w magazynie danych zostały zbudowane tak, aby współpracowały z funkcją autowykrywania usługi Power BI. Jednak nawet wtedy, gdy usługa Power BI nie znajdzie automatycznie relacji, nadal możesz nimi zarządzać.

![Zarządzanie relacjami pokrewnych danych w tabelach](media/reports-create-03-managerelationships.png)

1. Wybierz pozycję **Zarządzaj relacjami**.
2. Jeśli usługa Power BI nie wykryła jeszcze relacji, wybierz pozycję **Wykryj automatycznie**.

Relacja jest wyświetlana w kolumnach Od i Do. W tym przykładzie pole danych **ownerTypeKey** w tabeli **devices** jest połączone z polem danych **ownerTypeKey** w tabeli **ownerTypes**. Relacja zostanie użyta do wyszukania zwykłej nazwy dla kodu typu urządzenia w tabeli **devices**.

## <a name="create-a-treemap-visualization"></a>Tworzenie wizualizacji w formie mapy drzewa

Wykres mapy drzewa pokazuje hierarchiczne dane w postaci pól zawierających pola. Każda gałąź hierarchii to pole zawierające mniejsze pola reprezentujące podgałęzie. Za pomocą aplikacji Power BI Desktop można utworzyć mapę drzewa danych dzierżawy usługi Intune, która pokazuje względne ilości typów producenta urządzenia.

![Wizualizacje mapy drzewa usługi Power BI](media/reports-create-03-treemap.png)

1. W okienku **Wizualizacje** znajdź i wybierz pozycję **Mapa drzewa**. Wykres **Mapa drzewa** zostanie dodany do kanwy raportu.
2. W okienku **Pola** znajdź tabelę `devices`.
3. Rozwiń tabelę `devices` i wybierz pole danych `manufacturer`.
4. Przeciągnij pole danych `manufacturer` na kanwę raportu i upuść je na wykresie **Mapa drzewa**.
5. Przeciągnij pole danych `deviceKey` z tabeli `devices` do okienka **Wizualizacje** i upuść je w sekcji **Wartości** w polu z napisem **Dodaj pola danych tutaj**.  

Masz teraz wizualizację pokazującą rozkład producentów urządzeń w organizacji.

![Mapa drzewa z danymi — rozkład producentów urządzeń](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Dodawanie filtru

Do mapy drzewa możesz dodać filtr, aby za pomocą aplikacji odpowiedzieć na inne pytania.

1. Aby dodać filtr, wybierz kanwę raportu, a następnie wybierz **ikonę fragmentatora** (![Mapa drzewa z modelem danych i obsługiwanymi relacjami](media/reports-create-slicer.png)) w obszarze **Wizualizacje**. Na kanwie zostanie wyświetlona pusta wizualizacja **Fragmentator**.
2. W okienku **Pola** znajdź tabelę `ownerTypes`.
3. Rozwiń tabelę `ownerTypes` i wybierz pole danych `ownerTypeName`.
4. Przeciągnij pole `onwerTypeName` z tabeli `ownerTypes` do okienka **Filtry** i upuść je w sekcji **Filtry na tej stronie** w polu z napisem **Dodaj pola danych tutaj**.  

   W tabeli `OwnerTypes` znajduje się pole danych o nazwie `OwnerTypeKey`, które zawiera informacje, czy urządzenie należy do firmy, czy jest to urządzenie osobiste. Ponieważ w tym filtrze mają być wyświetlane przyjazne nazwy, poszukaj tabeli `ownerTypes` i przeciągnij **ownerTypeName** do fragmentatora. Ten przykład pokazuje, jak model danych obsługuje relacje między tabelami.

![Mapa drzewa z filtrem — obsługuje relacje między tabelami](media/reports-create-08_ownertype.png)

Masz teraz interakcyjny filtr, za pomocą którego możesz się przełączać między urządzeniami firmowymi i prywatnymi. Użyj tego filtru, aby zobaczyć zmiany w rozkładzie.

1. Wybierz pozycję **Firmowe** w ramach fragmentatora, aby zobaczyć urządzenia należące do firmy.
2. Wybierz pozycję **Osobiste** w ramach fragmentatora, aby zobaczyć urządzenia należące do użytkowników.

## <a name="next-steps"></a>Następne kroki

- Dowiedz się więcej o [tworzeniu i zarządzaniu relacjami](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) w programie Power BI Desktop z dokumentacji usługi Power BI.
- Zapoznaj się z [modelem magazynu danych usługi Intune](reports-ref-data-model.md).
