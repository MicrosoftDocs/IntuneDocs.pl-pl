---
title: "Użytkownik — magazyn danych usługi Intune | Microsoft Docs"
description: "Temat referencyjny dotyczący kategorii Użytkownik kolekcji jednostek w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 917c9585ffe17f9d090c519f716d284aa1b932b8
ms.sourcegitcommit: b2467a653ffd36c2248a30b69cb88e3dc7cca2ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2017
---
# <a name="reference-for-user-entity"></a>Dokumentacja jednostki użytkownika

Kategoria **Użytkownik** zawiera jednostkę **User**, która definiuje właściwości użytkownika w modelu danych.

## <a name="user"></a>Użytkownik

Jednostka **User** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami.

Kolekcja jednostek **User** zawiera dane użytkownika. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych z poprzedniego miesiąca. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| UserKey |Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy. |123 |
| UserId |Unikatowy identyfikator użytkownika — podobny do UserKey, ale jest kluczem naturalnym. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Adres e-mail użytkownika. |John@constoso.com |
| UPN | Główna nazwa użytkownika. | John@constoso.com |
| Nazwa wyświetlana |Nazwa wyświetlana użytkownika. |Michał |
| IntuneLicensed |Określa, czy użytkownik ma licencję usługi Intune, czy nie. |True/False |
| IsDeleted | Wskazuje, czy wszystkie licencje użytkownika wygasły i czy użytkownik został z tego powodu usunięty z usługi Intune. Dla pojedynczego rekordu ta flaga nie zmienia się. Zamiast tego tworzony jest nowy rekord odpowiadający nowemu stanowi użytkownika. |Prawda/Fałsz |
| StartDateInclusiveUTC |Jeśli flaga IsDeleted = FAŁSZ, data i godzina przypisania licencji użytkownikowi i początku jego obecności w usłudze Intune (w formacie UTC). Jeśli flaga IsDeleted = PRAWDA, data i godzina wygaśnięcia ważności licencji użytkownika i usunięcia go z usługi Intune (w formacie UTC). |2016-11-23 12:00:00 |
| EndDateExclusiveUTC |Jeśli flaga IsDeleted = FAŁSZ, data i godzina wygaśnięcia ważności licencji użytkownika i usunięcia go z usługi Intune (w formacie UTC). Licencja wygasła w pewnym momencie poprzedniego dnia. Jeśli flaga IsDeleted = PRAWDA, data i godzina uzyskania nowej licencji przez użytkownika i ponownego utworzenia go w usłudze Intune (w formacie UTC).  |2016-11-23 12:00:00 |
| IsCurrent |Wskazuje, czy ten rekord reprezentuje najnowszy stan użytkownika. Dla pojedynczego użytkownika może istnieć wiele rekordów, ale tylko jeden z nich reprezentuje bieżący stan.  |Prawda/Fałsz |
| RowLastModifiedDateTimeUTC |Data i godzina ostatniej modyfikacji rekordu w magazynie danych (w formacie UTC)  |2016-11-23 12:00:00 |

## <a name="next-steps"></a>Następne kroki
 - Aby ograniczyć dane użytkownika do użytkowników, którzy są obecnie aktywni, można użyć kolekcji jednostek **Bieżący użytkownik**. Aby uzyskać więcej informacji, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).
 - Aby uzyskać więcej informacji na temat sposobu, w jaki magazyn danych śledzi okres istnienia użytkownika w usłudze Intune, zobacz temat [Reprezentacja okresu istnienia użytkownika w magazynie danych usługi Intune](reports-ref-user-timeline.md).
