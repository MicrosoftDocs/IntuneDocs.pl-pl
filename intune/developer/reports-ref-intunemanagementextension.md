---
title: Jednostka IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Jednostka IntuneManagementExtension kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19b63172c8901059239c44aaf56fc49f0d7a01ad
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940401"
---
# <a name="reference-for-intune-management-extensions"></a>Dokumentacja rozszerzeń do zarządzania usługi Intune

Kategoria **intuneManagementExtensions** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje, takie jak:

- Wersje jednostki IntuneManagementExtension
- Stan instalacji jednostki IntuneManagementExtension

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

Jednostka **intuneManagementExtensionVersion** wyświetla listę wszystkich wersji używanych przez jednostkę intuneManagementExtensions.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| extensionVersionKey |Unikatowy identyfikator wersji jednostki intuneManagementExtensions. | 1 |
| extensionVersion |Czterocyfrowy numer wersji. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

Jednostka **intuneManagementExtensionHealthState** zawiera listę wszystkich możliwych stanów kondycji jednostki intuneManagementExtensions.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| extensionStateKey |Unikatowy identyfikator kondycji. | 2 |
| extensionState |Kondycja jednostki IntuneManagementExtension. | Dobra kondycja |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

Jednostka **intuneManagementExtension** zawiera listę kondycji jednostki intuneManagementExtensions na każdym urządzeniu z systemem Windows 10 dziennie.
Dane są zachowywane przez ostatnie 60 dni. 


|      Właściwość       |                         Opis                         | Przykład |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Unikatowy identyfikator daty.                |   123   |
|      tenantKey      |              Unikatowy identyfikator dzierżawy.               |   456   |
|      deviceKey      |              Unikatowy identyfikator urządzenia.               |   789   |
| extensionVersionKey | Unikatowy identyfikator wersji jednostki intuneManagementExtension. |    1    |
|  extensionStateKey  |             Unikatowy identyfikator kondycji.              |    2    |

