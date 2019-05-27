---
title: Dokumentacja jednostek aplikacji
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Aplikacja w kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: deea42bf9ef35d173761fddb16aa43eaa8876269
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041080"
---
# <a name="reference-for-application-entities"></a>Dokumentacja jednostek aplikacji

Kategoria **Aplikacja** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje takie jak:

  -  Wersje aplikacji
  -  Źródło instalacji aplikacji
  -  Typ deweloperów, którzy utworzyli aplikację
  -  Zarządzane typy oprogramowania dla aplikacji, na przykład **sidecar** lub **desktop**
  -  Stan Programu zakupów zbiorczych (VPP) aplikacji

## <a name="apprevision"></a>AppRevision

Jednostka **AppRevision** przedstawia wszystkie wersje aplikacji.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| AppKey |Unikatowy identyfikator aplikacji. |123 |
| ApplicationId |Unikatowy identyfikator aplikacji — podobny do AppKey, ale ten klucz jest kluczem naturalnym. |b66bc706-ffff-7437-0340-032819502773 |
| Przegląd |Wersja zgodna z podaną przez administratora podczas przekazywania pliku binarnego. |2 |
| Tytuł |Tytuł aplikacji. |Excel |
| Wydawca |Wydawca aplikacji. |Microsoft |
| UploadState |Stan przekazania aplikacji. |1 |
| AppTypeKey |Odwołanie do jednostki AppType opisanej w następującej sekcji. | |
| VppProgramTypeKey |Odwołanie do jednostki VppProgramType opisanej poniżej. | |
| CreationTime |Godzina utworzenia tej poprawki. |2016-11-23 12:00:00 |
| ModifiedTime |Godzina ostatniej zmiany dotyczącej tej poprawki. |2016-11-23 12:00:00 |
| Size |Rozmiar pliku binarnego. | |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tej poprawki aplikacji w magazynie danych. |2016-11-23 12:00:00 |
| EndDateExclusiveUTC |Data i godzina w formacie UTC utraty ważności przez tę poprawkę aplikacji. |2016-11-23 12:00:00 |
| IsCurrent |Wskazuje, czy ta wersja aplikacji jest aktualna w magazynie danych, czy nie. |Prawda/Fałsz |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tej wersji aplikacji w magazynie danych. |2016-11-23 12:00:00 |

## <a name="apptypes"></a>AppTypes

Jednostka **AppTypes** przedstawia źródło instalacji aplikacji.

| Właściwość  | Opis |
|---------|------------|
| AppTypeID |Identyfikator typu |
| AppTypeKey |Klucz zastępczy klucza |
| AppTypeName |Typ aplikacji |

### <a name="example"></a>Przykład

| AppTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Aplikacja ze sklepu dla systemu Android | Aplikacja ze sklepu dla systemu Android. |
| 1 |Aplikacja LOB dla systemu Android | Aplikacja biznesowa dla systemu Android. |
| 2 |Zarządzana aplikacja ze sklepu dla systemu Android (MAM) | Aplikacja ze sklepu dla systemu Android mająca włączone zarządzanie. |
| 3 |Aplikacja ze sklepu dla systemu iOS | Aplikacja ze sklepu dla systemu iOS. |
| 4 |Aplikacja LOB dla systemu iOS | Aplikacja biznesowa dla systemu iOS. |
| 5 |Zarządzana aplikacja ze sklepu dla systemu iOS (MAM?) | Aplikacja ze sklepu dla systemu iOS mająca włączone zarządzanie. |
| 6 |Pakiet O365 Pro Plus | Pakiet Office 365 Pro Plus dla systemu Windows 10. |
| 7 |Aplikacja internetowa | Aplikacja internetowa. |
| 8 |Aplikacja ze sklepu dla systemu Windows Phone 8.1 | Aplikacja ze sklepu dla systemu Windows Phone 8.1. |
| 9 |Aplikacja ze Sklepu Windows | Aplikacja ze Sklepu Windows. |
| 10 |Aplikacja LOB dla systemu Windows | Aplikacja biznesowa AppX dla systemu Windows. |
| 11 |Aplikacja MSI dla systemu Windows Mobile | Aplikacja biznesowa MSI. |
| 12 |Aplikacja LOB dla systemu Windows Phone | Aplikacja biznesowa dla systemu Windows Phone. |


## <a name="vppprogramtypes"></a>VppProgramTypes

Jednostka **VppProgramTypes** zawiera listę możliwych typów programów VPP dla aplikacji.

| Właściwość  | Opis |
|---------|------------|
| VppProgramTypeID | Identyfikator typu. |
| VppProgramTypeKey | Klucz zastępczy klucza. |
| VppProgramTypeName | Typ programu VPP. |

### <a name="example"></a>Przykład

| VppProgramID  | Nazwa | Opis |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Program VPP firmy Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Jeszcze niedostępne | Wartość domyślna: No VPP (Brak VPP). |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Program VPP firmy Apple. |



## <a name="applicationinventory"></a>ApplicationInventory

Jednostka **ApplicationInventory** tworzy listę aplikacji znalezionych na urządzeniu w czasie zbierania spisu.

| Właściwość  | Opis |
|---------|------------|
| DeviceKey | To jest odwołanie do tabeli urządzenia, która zawiera identyfikator urządzenia usługi Intune. |
| DateKey | Odwołanie do tabeli dat wskazujące dzień spisu. |
| ApplicationName | Nazwa aplikacji. |
| ApplicationVersion | Wersja aplikacji. |
| BundleSize | Rozmiar aplikacji w bajtach. |

## <a name="mobileappinstallstate"></a>MobileAppInstallState

Jednostka **MobileAppInstallState** reprezentuje stan instalacji aplikacji mobilnej po jej przypisaniu do grupy zawierającej urządzenia, użytkowników lub obie te kategorie.

| Właściwość | Opis |
|---|---|
| AppInstallStateKey | Unikatowy identyfikator stanu instalacji aplikacji dla konta użytkownika. |
| AppInstallState | Wartość wyliczenia stanu instalacji aplikacji. |
| AppInstallStateName | Nazwa stanu instalacji aplikacji. |



