---
title: "Skojarzenie urządzenia użytkownika — magazyn danych usługi Intune | Microsoft Docs"
description: "Lista zmian w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 45c3e14631fdfe74cafea4a0965efac51386524a
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2018
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
