---
title: "Skojarzenie urządzenia użytkownika — magazyn danych usługi Intune | Microsoft Docs"
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
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2017
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
