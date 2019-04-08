---
title: Skojarzenie urządzenia użytkownika — magazyn danych usługi Intune
titleSuffix: Microsoft Intune
description: Jednostka UserDeviceAssociation zawiera skojarzenia urządzeń użytkowników w organizacji.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 466066faf03cbdf560697a04310eac844d4f1b87
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798264"
---
# <a name="reference-for-user-device-association-entity"></a>Dokumentacja jednostki Skojarzenie urządzenia użytkownika

Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Nazwa        |                                           Opis                                            |        Przykład         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Unikatowy identyfikator użytkownika w magazynie danych. (Klucz zastępczy).               |          123           |
|     DeviceKey      |                      Unikatowy identyfikator urządzenia w magazynie danych.                      |          123           |
| CreatedDateTimeUTC |           Data i godzina utworzenia skojarzenia urządzenia użytkownika, w formacie UTC.           | 2016-11-23 12:00:00 |
|     IsDeleted      | Wskazuje, że użytkownik wyrejestrował urządzenie i skojarzenie nie jest już aktualne. |       Prawda/Fałsz       |
|  EndedDateTimeUTC  |              Data i godzina (czas UTC) zmiany właściwości IsDeleted na wartość <strong>True</strong>.               | 2017-06-23 12:00:00 |

## <a name="next-steps"></a>Następne kroki

- Dowiedz się więcej o [magazynie danych usługi Intune](reports-nav-create-intune-reports.md).
