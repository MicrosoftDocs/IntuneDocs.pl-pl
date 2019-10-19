---
title: Użytkownik — magazyn danych usługi Intune
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Użytkownik kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 996e28f9dceff88637c93e667597e3364215b965
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505636"
---
# <a name="reference-for-user-entity"></a>Informacje dotyczące jednostki User (Użytkownik)

Kategoria **Użytkownicy** zawiera jednostkę **user**, która definiuje właściwości użytkownika w modelu danych.

## <a name="users"></a>użytkownicy

Jednostka **user** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami.

Kolekcja jednostek **user** zawiera dane użytkowników. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych z poprzedniego miesiąca. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

|          Właściwość          |                                                                                                           Opis                                                                                                          |                Przykład               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| userKey                    | Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy.                                                                                                                                                         | 123                                  |
| userId                     | Unikatowy identyfikator użytkownika — podobny do UserKey, ale jest kluczem naturalnym.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| userEmail                  | Adres e-mail użytkownika.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Główna nazwa użytkownika.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Nazwa wyświetlana użytkownika.                                                                                                                                                                                                      | Michał                                 |
| intuneLicensed             | Określa, czy użytkownik ma licencję usługi Intune, czy nie.                                                                                                                                                                              | Prawda/Fałsz                           |
| isDeleted                  | Wskazuje, czy wszystkie licencje użytkownika wygasły i czy użytkownik został z tego powodu usunięty z usługi Intune. Dla pojedynczego rekordu ta flaga nie zmienia się. Zamiast tego tworzony jest nowy rekord odpowiadający nowemu stanowi użytkownika. | Prawda/Fałsz                           |
| RowLastModifiedDateTimeUTC | Data i godzina ostatniej modyfikacji rekordu w magazynie danych w formacie UTC                                                                                                                                                 | 23.11.2016 0:00                      |


## <a name="next-steps"></a>Następne kroki
- Aby ograniczyć dane użytkownika do użytkowników, którzy są obecnie aktywni, można użyć kolekcji jednostek **Bieżący użytkownik**. Aby uzyskać więcej informacji, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](../reports-ref-current-user.md).
- Więcej informacji na temat sposobu, w jaki magazyn danych śledzi okres istnienia użytkownika w usłudze Intune, można znaleźć w temacie [Reprezentacja okresu istnienia użytkownika w magazynie danych usługi Intune](reports-ref-user-timeline.md).
