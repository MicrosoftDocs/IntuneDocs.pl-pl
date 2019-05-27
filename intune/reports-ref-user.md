---
title: Użytkownik — magazyn danych usługi Intune
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Użytkownik kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0551327bfe2b320bb91699e1176985bbdf94de92
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045226"
---
# <a name="reference-for-user-entity"></a>Informacje dotyczące jednostki User (Użytkownik)

Kategoria **Użytkownik** zawiera jednostkę **User**, która definiuje właściwości użytkownika w modelu danych.

## <a name="user"></a>Użytkownik

Jednostka **User** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami.

Kolekcja jednostek **User** zawiera dane użytkownika. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych z poprzedniego miesiąca. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

|          Właściwość          |                                                                                                           Opis                                                                                                          |                Przykład               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy.                                                                                                                                                         | 123                                  |
| UserId                     | Unikatowy identyfikator użytkownika — podobny do UserKey, ale jest kluczem naturalnym.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | Adres e-mail użytkownika.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Główna nazwa użytkownika.                                                                                                                                                                                               | John@constoso.com                    |
| Nazwa wyświetlana                | Nazwa wyświetlana użytkownika.                                                                                                                                                                                                      | Michał                                 |
| IntuneLicensed             | Określa, czy użytkownik ma licencję usługi Intune, czy nie.                                                                                                                                                                              | True/False                           |
| IsDeleted                  | Wskazuje, czy wszystkie licencje użytkownika wygasły i czy użytkownik został z tego powodu usunięty z usługi Intune. Dla pojedynczego rekordu ta flaga nie zmienia się. Zamiast tego tworzony jest nowy rekord odpowiadający nowemu stanowi użytkownika. | Prawda/Fałsz                           |
| RowLastModifiedDateTimeUTC | Data i godzina ostatniej modyfikacji rekordu w magazynie danych w formacie UTC                                                                                                                                                 | 23.11.2016 0:00                      |


## <a name="next-steps"></a>Następne kroki
 - Aby ograniczyć dane użytkownika do użytkowników, którzy są obecnie aktywni, można użyć kolekcji jednostek **Bieżący użytkownik**. Aby uzyskać więcej informacji, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).
 - Więcej informacji na temat sposobu, w jaki magazyn danych śledzi okres istnienia użytkownika w usłudze Intune, można znaleźć w temacie [Reprezentacja okresu istnienia użytkownika w magazynie danych usługi Intune](reports-ref-user-timeline.md).
