---
title: Oś czasu jednostki Użytkownik w magazynie danych
titleSuffix: Microsoft Intune
description: Dowiedz się, jak magazyn danych usługi Microsoft Intune reprezentuje użytkowników na osi czasu.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 363D148E-688F-4830-B6DE-AB4FE3648817
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fa483a49ad7fa44172a83f024540a75d1d881dc
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040920"
---
# <a name="user-lifetime-representation-in-the-microsoft-intune-data-warehouse"></a>Reprezentacja okresu istnienia użytkownika w magazynie danych usługi Microsoft Intune

Migawki danych przechowywanych w magazynie danych usługi Intune w ciągu miesiąca mogą posłużyć do odpowiedzi na pytania dotyczące trendów w czasie. Na przykład można przyjrzeć się liczbie użytkowników dodawanych w ciągu miesiąca. Można również dowiedzieć się, jaka jest liczba użytkowników usuniętych z systemu.

W celu umożliwienia tego typu analizy magazyn danych przechowuje informacje historyczne. Magazyn danych może śledzić okres istnienia jednostki. Magazyn rejestruje chwilę, w której jednostka została utworzona, kiedy zmienił się jej stan oraz kiedy została usunięta. Dzięki danym historycznym przechwytywanym za pomocą codziennych migawek pomiarów ilościowych można porównać dany dzień z dniem poprzednim i tak dalej.

Praca z okresami istnienia jednostek może sprawiać problemy, ponieważ jednostki zmieniają stan. Oznacza to, że jeśli analizujesz migawkę w dniu 30, rekord użytkownika może nie występować w danych w stanie aktywnym. W dniach 29-28 rekord jednostki może istnieć jako aktywny. Z kolei przed dniem 28 użytkownik w ogóle nie istniał.

Ten scenariusz może się stać bardziej zrozumiały, jeśli przeanalizujemy okres istnienia jednostki.

Załóżmy, że użytkownik, **Jan Kowalski**, pobiera przypisaną mu licencję w dniu 1 czerwca 2017 r., co spowoduje, że w tabeli **Użytkownik** znajdzie się następujący wpis: 
 
| Nazwa wyświetlana | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Jan Kowalski | FAŁSZ | 06/01/2017 | 12/31/9999 | PRAWDA
 
Jan Kowalski rezygnuje ze swojej licencji w dniu 25 lipca 2017 r. Tabela **Użytkownik** zawiera następujące wpisy. Zmiany w istniejących rekordach są `marked`. 

| Nazwa wyświetlana | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Jan Kowalski | FAŁSZ | 06/01/2017 | `07/26/2017` | `FALSE` 
| Jan Kowalski | PRAWDA | 07/26/2017 | 12/31/9999 | PRAWDA 

Pierwszy wiersz wskazuje, że Jan Kowalski istniał w usłudze Intune od dnia 2017-06-01 do 2017-07-25. Drugi rekord wskazuje, że użytkownik został usunięty w dniu 2017-07-25 i nie jest już obecny w usłudze Intune.

A teraz załóżmy, że Jan Kowalski pobiera nową przypisaną licencję w dniu 31 sierpnia 2017 r., co spowoduje, że w tabeli Użytkownik znajdą się następujące wpisy:
 
| Nazwa wyświetlana | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Jan Kowalski | FAŁSZ | 06/01/2017 | 07/26/2017 | FAŁSZ 
| Jan Kowalski | PRAWDA | 07/26/2017 | `08/31/2017` | `FALSE` 
| Jan Kowalski | FAŁSZ | 08/31/2017 | 12/31/9999 | PRAWDA 
 
Osoba, która chce wyświetlić bieżący stan wszystkich użytkowników, będzie chciała zastosować filtr, gdzie `IsCurrent = TRUE`. 
 
Osoba, która chce wyświetlić tylko istniejących użytkowników, będzie chciała zastosować filtr, gdzie `IsCurrent = TRUE AND IsDeleted = FALSE`.

## <a name="dimension-tables-in-the-entity-lifetime"></a>Tabele wymiarów w okresie istnienia jednostki

W celu zachowania historii zmian stanu jednostek usługa Intune nie usuwa rekordów. Zamiast tego oznacza rekord jako usunięty. Ta operacja nosi nazwę usuwania nietrwałego. Tabele wymiarów wykorzystują różne kolumny metadanych do śledzenia okresu istnienia rekordów. 

Do najczęściej używanych kolumn metadanych należą: 

| Nazwa właściwości metadanych  | Interpretacja wartości |
|--|--|
| IsDeleted | Wskazuje, czy jednostka została usunięta w usłudze Intune. |
| StartDateInclusiveUTC  | Data w formacie UTC określająca, kiedy jednostka została załadowana do magazynu danych usługi Intune. Jednostka mogła zostać utworzona zanim została zaimportowana do magazynu danych usługi Intune. |
| DeletedDateUTC  | Data w formacie UTC określająca, kiedy jednostka została usunięta w usłudze Intune. |  

Każda kolumna metadanych, której nazwa zaczyna się od prefiksu **Row**, jak **RowLastModifiedDateTimeUTC**, wskazuje, kiedy rekord został utworzony lub zmodyfikowany w magazynie danych usługi Intune. Magazyn jest elementem podrzędnym względem danych w usłudze Intune. Ta wartość nie ma związku z okresem istnienia jednostki w usłudze Intune.  
 
Każda osoba, która chce zobaczyć tylko te jednostki wymiaru, które obecnie istnieją, może zastosować filtr, w którym **IsDeleted = FAŁSZ**.

## <a name="next-steps"></a>Następne kroki

 - Aby dowiedzieć się więcej o jednostce **Bieżący użytkownik**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).
 - Aby dowiedzieć się więcej o jednostce **Użytkownik**, zobacz temat [Dokumentacja jednostki użytkownika](reports-ref-user.md).
