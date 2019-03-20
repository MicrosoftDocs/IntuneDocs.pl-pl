---
title: Skojarzenie urządzenia użytkownika — magazyn danych usługi Intune
titlesuffix: Microsoft Intune
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
ms.openlocfilehash: 5d3473b04a1d015f88d27359864a84227215b62a
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565302"
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
