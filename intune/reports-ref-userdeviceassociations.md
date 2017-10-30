---
title: "Skojarzenie urządzenia użytkownika | Microsoft Docs"
description: "Temat dokumentacji dotyczący kategorii Skojarzenie urządzenia użytkownika kolekcji jednostek w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Dokumentacja jednostki Skojarzenie urządzenia użytkownika

Kategoria **Skojarzenie urządzenia użytkownika** zawiera jednostkę **Skojarzenie urządzenia użytkownika** służącą do definiowania skojarzeń urządzeń w organizacji.

**Skojarzenie urządzenia użytkownika**

Jednostka **Skojarzenie urządzenia użytkownika** reprezentuje skojarzenia definiowania urządzeń w organizacji.

| Nazwa               | Opis                                                                                      | Przykład                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy.                             | 123                    |
| DeviceKey          | Unikatowy identyfikator urządzenia w magazynie danych.                                           | 123                    |
| CreatedDateTimeUTC | Data i godzina (czas UTC) utworzenia skojarzenia urządzenia użytkownika.                               | 2016-11-23 12:00:00 |
| IsDeleted          | Wskazuje, że użytkownik wyrejestrował urządzenie i skojarzenie nie jest już aktualne. | Prawda                   |
| EndedDateTimeUTC   | Data i godzina (czas UTC) zmiany właściwości IsDeleted na wartość **True**.                                         | 2017-06-23 12:00:00 |