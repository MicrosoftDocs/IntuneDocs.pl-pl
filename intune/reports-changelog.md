---
title: "Dziennik zmian magazynu danych usługi Intune | Microsoft Docs"
description: "Lista zmian w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b81846c2e45f968184d50d2ea7c50aabb86b4964
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Dziennik zmian dla interfejsu API magazynu danych usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bądź na bieżąco z aktualizacjami magazynu danych usługi Intune.

## <a name="1710"></a>1710
_Wydanie: październik 2017 r._

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Jednostka użytkownika zawiera najnowsze dane użytkownika w modelu danych magazynu danych <!-- 1544273 -->

Pierwsza wersja modelu danych magazynu danych usługi Intune zawierała tylko ostatnie, historyczne dane usługi Intune. Podczas tworzenia raportu nie było możliwe uchwycenie bieżącego stanu użytkownika. Po wprowadzeniu tej aktualizacji [**jednostka użytkownika**](reports-ref-user.md) będzie wypełniana najnowszymi danymi użytkownika.

### <a name="new-entity-in-the-in-data-warehouse-data-model----1479526---"></a>Nowa jednostka w modelu danych magazynu danych <!-- 1479526 -->

Dodano jednostkę [**UserDeviceAssociation**](reports-ref-user-device.md). Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji.

## <a name="next-steps"></a>Następne kroki
 - Dowiedz się, [co nowego w usłudze Intune w każdym tygodniu](whats-new.md). Możesz również sprawdzić informacje o nadchodzących zmianach, ważnych powiadomieniach dotyczących usługi oraz poprzednich wersjach. 
 - Zapoznaj się z [blogiem usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).