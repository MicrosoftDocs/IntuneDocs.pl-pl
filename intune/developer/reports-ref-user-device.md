---
title: Skojarzenie urządzenia użytkownika — magazyn danych usługi Intune
titleSuffix: Microsoft Intune
description: Jednostka UserDeviceAssociation zawiera skojarzenia urządzeń użytkowników w organizacji.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f04575ce32d3d02a1869ed8c3225905b9e6b7dc
ms.sourcegitcommit: 7cc45ef52dda08479bc6bdff7d11d2f6c0e7b93b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "74899273"
---
# <a name="reference-for-user-device-association-entity"></a>Dokumentacja jednostki Skojarzenie urządzenia użytkownika

Jednostka **userDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji.

## <a name="userdeviceassociations"></a>userDeviceAssociations


|        Nazwa        |                                           Opis                                            |        Przykład         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      userKey       |              Unikatowy identyfikator użytkownika w magazynie danych. (Klucz zastępczy).               |          123           |
|     deviceKey      |                      Unikatowy identyfikator urządzenia w magazynie danych.                      |          123           |
| createdDateTimeUTC |           Data i godzina utworzenia skojarzenia urządzenia użytkownika, w formacie UTC.           | 2016-11-23 12:00:00 |
|     isDeleted      | Wskazuje, że użytkownik wyrejestrował urządzenie i skojarzenie nie jest już aktualne. |       Prawda/Fałsz       |
|  endedDateTimeUTC  |              Data i godzina (czas UTC) zmiany właściwości IsDeleted na wartość <strong>True</strong>.               | 2017-06-23 12:00:00 |

## <a name="next-steps"></a>Następne kroki

- Dowiedz się więcej o [magazynie danych usługi Intune](../reports-nav-create-intune-reports.md).
