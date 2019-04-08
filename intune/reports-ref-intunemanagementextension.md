---
title: Jednostka IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Jednostka IntuneManagementExtension kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea55c92fb3254b6e610bec1074e35d9d9c32cd18
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798004"
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
| ExtensionState |Kondycja jednostki IntuneManagementExtension. | Dobra kondycja |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

Jednostka **IntuneManagementExtension** zawiera listę kondycji jednostki IntuneManagementExtension na każdym urządzeniu z systemem Windows 10 dziennie.
Dane są zachowywane przez ostatnie 60 dni. 


|      Właściwość       |                         Opis                         | Przykład |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Unikatowy identyfikator daty.                |   123   |
|      TenantKey      |              Unikatowy identyfikator dzierżawy.               |   456   |
|      DeviceKey      |              Unikatowy identyfikator urządzenia.               |   789   |
| ExtensionVersionKey | Unikatowy identyfikator wersji jednostki IntuneManagementExtension. |    1    |
|  ExtensionStateKey  |             Unikatowy identyfikator kondycji.              |    2    |

