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
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2018
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
