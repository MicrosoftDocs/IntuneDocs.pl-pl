---
title: Skojarzenie urządzenia użytkownika — magazyn danych usługi Intune
titlesuffix: Microsoft Intune
description: Lista zmian w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de14444376cb2998f17f406f084c428523ef4e4f
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2018
---
# <a name="user-device-association"></a>Skojarzenie urządzenia użytkownika

Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji.

| Nazwa               | Opis                                                                                      | Przykład                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Unikatowy identyfikator użytkownika w magazynie danych. (Klucz zastępczy).                              | 123                    |
| DeviceKey          | Unikatowy identyfikator urządzenia w magazynie danych.                                            | 123                    |
| CreatedDateTimeUTC | Data i godzina utworzenia skojarzenia urządzenia użytkownika, w formacie UTC.                                | 2016-11-23 12:00:00 |
| IsDeleted          | Wskazuje, że użytkownik wyrejestrował urządzenie i skojarzenie nie jest już aktualne. | Prawda/Fałsz             |
| EndedDateTimeUTC   | Data i godzina (czas UTC) zmiany właściwości IsDeleted na wartość **True**.                                              | 2017-06-23 12:00:00 |
