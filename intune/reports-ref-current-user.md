---
title: Bieżący użytkownik — magazyn danych usługi Intune
titlesuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Bieżący użytkownik kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b9fdd1891f8a0e893d61ac3a0b40dac5a01f602c
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851342"
---
# <a name="reference-for-current-user-entity"></a>Dokumentacja jednostki bieżącego użytkownika

Kategoria **Bieżący użytkownik** zawiera właściwości użytkownika w modelu danych. Kolekcja jednostek **Bieżący użytkownik** jest ograniczona do aktualnie aktywnych użytkowników. Jednostka zawiera wszystkich użytkowników usługi Azure Active Directory, którzy mają obecnie przypisaną licencję. Licencja może być licencją usługi Intune, licencją hybrydową lub licencją usługi Microsoft Office 365. Jeśli użytkownik został usunięty, nie będzie reprezentowany w kolekcji bieżącego użytkownika. Aby uzyskać informacje na temat kolekcji, która zawiera historię zmian stanu użytkownika, zobacz temat [Dokumentacja jednostki użytkownika](reports-ref-user.md).


## <a name="current-user"></a>Bieżący użytkownik

Jednostka **Current User** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| UserKey |Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy. |123 |
| UserId |Unikatowy identyfikator użytkownika — podobny do UserKey, ale jest kluczem naturalnym. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Adres e-mail użytkownika. |John@constoso.com |
| UPN | Główna nazwa użytkownika. | John@constoso.com |
| Nazwa wyświetlana |Nazwa wyświetlana użytkownika. |Michał |
| IntuneLicensed |Określa, czy użytkownik ma licencję usługi Intune, czy nie. |Prawda/Fałsz |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tego użytkownika w magazynie danych. |2016-11-23 12:00:00 |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tego użytkownika w magazynie danych. |2016-11-23 12:00:00 |

## <a name="next-steps"></a>Następne kroki
 - Aby rozszerzyć dane użytkowników o tych użytkowników, którzy obecnie nie są aktywni, można użyć kolekcji jednostek **Użytkownicy**. Aby uzyskać więcej informacji, zobacz temat [Dokumentacja jednostki użytkownika](reports-ref-user.md).
 - Więcej na temat sposobu, w jaki magazyn danych śledzi okres istnienia użytkownika w usłudze Intune, można dowiedzieć się z tematu [Reprezentacja okresu istnienia użytkownika w magazynie danych usługi Intune](reports-ref-user-timeline.md).
