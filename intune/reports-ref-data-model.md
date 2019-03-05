---
title: Model danych magazynu danych
titlesuffix: Microsoft Intune
description: Magazyn danych usługi Microsoft Intune każdego dnia próbkuje dane, aby przedstawić widok historyczny ciągle zmieniającego się środowiska mobilnego.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e305d419a101410a9a934a200dfcfb1c3488ff7
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238289"
---
# <a name="microsoft-intune-data-warehouse-data-model"></a>Model danych magazynu danych usługi Microsoft Intune

Magazyn danych usługi Intune codziennie próbkuje dane w celu udostępnienia historycznego widoku ciągle zmieniającego się środowiska urządzeń przenośnych. Widok składa się z jednostek powiązanych w czasie.

## <a name="entities-entity-sets"></a>Jednostki: zestawy jednostek

Magazyn uwidacznia dane w następujących kategoriach wysokiego poziomu:

  -  Aplikacje z włączoną ochroną aplikacji i ich użycie
  -  Zarejestrowane urządzenia, właściwości i spis
  -  Spis aplikacji i oprogramowania
  -  Zasady zgodności i konfiguracji urządzenia

Te obszary zawierają jednostki, które mają znaczenie dla danego środowiska usługi Intune. Szczegółowe informacje dotyczące zestawów jednostek można znaleźć w następujących tematach:

  -  [Aplikacja](reports-ref-application.md)
  -  [Data](reports-ref-date.md)
  -  [Urządzenia](reports-ref-devices.md)
  -  [Rozszerzenie do zarządzania usługi Intune](reports-ref-intunemanagementextension.md)
  -  [Zasady](reports-ref-policy.md)
  -  [Zarządzanie aplikacjami mobilnymi (MAM)](reports-ref-mobile-app-management.md)
  -  [User](reports-ref-user.md)
  -  [Bieżący użytkownik](reports-ref-current-user.md)
  -  [Skojarzenie urządzenia użytkownika](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a>Relacje: model o schemacie gwiazdy

Magazyn organizuje jednostki w relacje zrozumiałe dla typu pytań, które chcesz zadać. Na przykład możesz sprawdzić liczbę instalacji wewnętrznie opracowanych aplikacji systemu Android. Struktura magazynu danych umożliwia szczegółowy wgląd w środowisko mobilne. Z kolei narzędzia analityczne, takie jak usługa Microsoft Power BI, mogą przy użyciu modelu danych magazynu danych tworzyć wizualizacje i dynamiczne pulpity nawigacyjne.

Jednostki i relacje korzystają z modelu o schemacie gwiazdy. W schemacie gwiazdy fakty są korelowane w wymiarze czasu. W kontekście modelu *fakt* to pomiar ilościowy, na przykład liczba urządzeń, liczba aplikacji lub czas rejestracji. Tabele faktów przechowują duże ilości danych. Mogą stać się bardzo duże, dlatego zwykle ograniczają informacje do 30 dni. *Wymiar* udostępnia kontekst dla faktów. Podczas gdy fakt reprezentuje to, co się stało, to wymiar wskazuje, kogo to dotyczy. Tabele wymiarów, takie jak tabela **Użytkownik**, są mniejsze i mogą przechowywać dane przez dłuższy czas niż tabele faktów. 

Model schematu gwiazdy jest zoptymalizowany pod kątem elastyczności i analizy danych, aby umożliwić tworzenie raportów potrzebnych do zrozumienia ewoluującego środowiska mobilnego.

## <a name="time-daily-snapshots"></a>Godzina: dzienne migawki

Magazyn jest elementem podrzędnym względem danych w usłudze Intune. Usługa Intune wykonuje dzienną migawkę codziennie o północy czasu UTC i przechowuje ją w magazynie. Czasy przechowywania migawek w różnych tabelach faktów różnią się. Niektóre mogą je utrzymywać przez siedem dni, inne 30 dni, a niektóre nawet dłużej.

## <a name="next-steps"></a>Następne kroki

 - Więcej informacji na temat sposobu, w jaki magazyn danych śledzi okres istnienia użytkownika w usłudze Intune, można znaleźć w temacie [Reprezentacja okresu istnienia użytkownika w magazynie danych usługi Intune](reports-ref-user-timeline.md).
 - Więcej informacji na temat pracy z magazynami danych można znaleźć w temacie [Create First Data WareHouse](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse) (Tworzenie pierwszego magazynu danych).
 - Więcej na temat pracy z usługą Power BI i magazynem danych można dowiedzieć się z tematu [Create a new Power BI report by importing a dataset](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/) (Tworzenie nowego raportu usługi Power BI przez importowanie zestawu danych). 
