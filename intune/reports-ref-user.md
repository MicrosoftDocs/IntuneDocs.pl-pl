---
title: "Użytkownik | Microsoft Docs"
description: "Temat referencyjny dotyczący kategorii Użytkownik kolekcji jednostek w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b9739299c52c668117116f54c08715f1218d130
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-user-entity"></a>Dokumentacja jednostki użytkownika

Kategoria **Użytkownik** zawiera jednostkę **User**, która definiuje właściwości użytkownika i agenta w modelu danych.

**User**

Jednostka **User** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| UserKey |Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy |123 |
| UserId |Unikatowy identyfikator użytkownika — podobny do UserKey, ale jest kluczem naturalnym |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Adres e-mail użytkownika |John@constoso.com |
| Nazwa wyświetlana |Nazwa wyświetlana użytkownika |Michał |
| IntuneLicensed |Określa, czy użytkownik ma licencję usługi Intune, czy nie. |True/False |
| IsDeleted |Wskazuje, czy ten rekord użytkownika został zaktualizowany.  True — użytkownik ma nowy rekord ze zaktualizowanymi polami w tej tabeli. False — to jest najnowszy rekord dla tego użytkownika. |Prawda/Fałsz |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tego użytkownika w magazynie danych |2016-11-23 12:00:00 |
| EndDateExclusiveUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True |2016-11-23 12:00:00 |
| IsCurrent |Wskazuje, czy ten rekord użytkownika jest aktualny w magazynie danych, czy nie |True/False |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tego użytkownika w magazynie danych |2016-11-23 12:00:00 |

