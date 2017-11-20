---
title: Jednostka IntuneManagementExtension | Microsoft Docs
description: "Temat referencyjny dotyczący kategorii Jednostka IntuneManagementExtension kolekcji jednostek w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 30908e4dbb55e16db0e253330175f65fb127d523
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2017
---
# <a name="reference-for-intune-management-extension"></a>Dokumentacja rozszerzenia do zarządzania usługi Intune

Kategoria **IntuneManagementExtension** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje takie jak:

  -  Wersje jednostki IntuneManagementExtension
  -  Stan instalacji jednostki IntuneManagementExtension

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

Jednostka **IntuneManagementExtensionVersion** wyświetla listę wszystkich wersji używanych przez jednostkę IntuneManagementExtension.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| ExtensionVersionKey |Unikatowy identyfikator wersji jednostki IntuneManagementExtension. | 1 |
| ExtensionVersion |Czterocyfrowy numer wersji. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

Jednostka **IntuneManagementExtensionHealthState** zawiera listę wszystkich możliwych stanów kondycji jednostki IntuneManagementExtension.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| ExtensionStateKey |Unikatowy identyfikator kondycji. | 2 |
| ExtensionState |Kondycja jednostki IntuneManagementExtension. | W dobrej kondycji |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

Jednostka **IntuneManagementExtension** zawiera listę kondycji jednostki IntuneManagementExtension na każdym urządzeniu z systemem Windows 10 dziennie.
Dane są zachowywane przez ostatnie 60 dni. 

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Unikatowy identyfikator daty. | 123 |
| TenantKey |Unikatowy identyfikator dzierżawy. | 456 |
| DeviceKey |Unikatowy identyfikator urządzenia. | 789 |
| ExtensionVersionKey |Unikatowy identyfikator wersji jednostki IntuneManagementExtension. | 1 |
| ExtensionStateKey|Unikatowy identyfikator kondycji. | 2 |