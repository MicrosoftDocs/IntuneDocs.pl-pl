---
title: "Dziennik zmian magazynu danych usługi Intune | Microsoft Docs"
description: "Lista zmian w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d1078dfeebae22f0754502935c983db13de60a60
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/30/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Dziennik zmian dla interfejsu API magazynu danych usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bądź na bieżąco z aktualizacjami magazynu danych usługi Intune.

## <a name="1710"></a>1710
_Wydanie: listopad 2017 r._

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Nowa kolekcja jednostek o nazwie Bieżący użytkownik jest ograniczona do danych aktualnie aktywnych użytkowników <!-- 1544273 -->

Kolekcja jednostek **Users** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

Z kolei nowa kolekcja jednostek **Bieżący użytkownik** zawiera tylko tych użytkowników, którzy nie zostali usunięci. Kolekcja jednostek **Bieżący użytkownik** zawiera tylko aktualnie aktywnych użytkowników. Aby uzyskać informacje o kolekcji jednostek **bieżącego użytkownika**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Wydanie: październik 2017 r._

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->

Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta. Aby uzyskać więcej informacji, zobacz temat [Skojarzenie urządzenia użytkownika](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nowe jednostki w modelu danych magazynu danych <!-- 1479526 --><!-- -->

 - Dodano jednostkę [**UserDeviceAssociation**](reports-ref-user-device.md). Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji. Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia.  
 - Jednostka, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), dodana. Jednostka **IntuneManagementExtension** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje, takie jak wersja i stan instalacji.

## <a name="next-steps"></a>Następne kroki
 - Dowiedz się, [co nowego w usłudze Intune w każdym tygodniu](whats-new.md). Możesz również sprawdzić informacje o nadchodzących zmianach, ważnych powiadomieniach dotyczących usługi oraz poprzednich wersjach.
 - Zapoznaj się z [blogiem usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
