---
title: Dokumentacja jednostek aplikacji
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Aplikacja w kolekcji jednostek w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
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
ms.openlocfilehash: a5436de6b972e5cbe8b2b17d42f0974cb38df47e
ms.sourcegitcommit: c3ac858bbadb63d248ed54069e48160d703bbaf2
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313814"
---
# <a name="reference-for-application-entities"></a>Dokumentacja jednostek aplikacji

Kategoria **Aplikacja** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje takie jak:

- Wersje aplikacji
- Źródło instalacji aplikacji
- Typ deweloperów, którzy utworzyli aplikację
- Zarządzane typy oprogramowania dla aplikacji, na przykład **sidecar** lub **desktop**
- Stan Programu zakupów zbiorczych (VPP) aplikacji

## <a name="apprevisions"></a>appRevisions

Jednostka **appRevision** przedstawia listę wszystkich wersji aplikacji.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| appKey |Unikatowy identyfikator aplikacji. |123 |
| applicationId |Unikatowy identyfikator aplikacji — podobny do AppKey, ale ten klucz jest kluczem naturalnym. |b66bc706-ffff-7437-0340-032819502773 |
| revision |Wersja zgodna z podaną przez administratora podczas przekazywania pliku binarnego. |2 |
| title |Tytuł aplikacji. |Excel |
| publisher |Wydawca aplikacji. |Microsoft |
| uploadState |Stan przekazania aplikacji. |1 |
| appTypeKey |Odwołanie do jednostki AppType opisanej w następującej sekcji. | |
| vppProgramTypeKey |Odwołanie do jednostki VppProgramType opisanej poniżej. | |
| creationTime |Godzina utworzenia tej poprawki. |2016-11-23 12:00:00 |
| modifiedTime |Godzina ostatniej zmiany dotyczącej tej poprawki. |2016-11-23 12:00:00 |
| rozmiar |Rozmiar pliku binarnego. | |
| startDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tej poprawki aplikacji w magazynie danych. |2016-11-23 12:00:00 |
| endDateExclusiveUTC |Data i godzina w formacie UTC utraty ważności przez tę poprawkę aplikacji. |2016-11-23 12:00:00 |
| isCurrent |Wskazuje, czy ta wersja aplikacji jest aktualna w magazynie danych, czy nie. |Prawda/Fałsz |
| rowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tej wersji aplikacji w magazynie danych. |2016-11-23 12:00:00 |

## <a name="apptypes"></a>appTypes

Jednostka **appType** przedstawia źródło instalacji aplikacji.

| Właściwość  | Opis |
|---------|------------|
| appTypeID |Identyfikator typu |
| appTypeKey |Klucz zastępczy klucza |
| appTypeName |Typ aplikacji |

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


## <a name="vppprogramtypes"></a>vppProgramTypes

Jednostka **vppProgramType** zawiera listę możliwych typów programów VPP dla aplikacji.

| Właściwość  | Opis |
|---------|------------|
| vppProgramTypeID | Identyfikator typu. |
| vppProgramTypeKey | Klucz zastępczy klucza. |
| vppProgramTypeName | Typ programu VPP. |

### <a name="example"></a>Przykład

| VppProgramID  | Nazwa | Opis |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Program VPP firmy Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Jeszcze niedostępne | Wartość domyślna: No VPP (Brak VPP). |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Program VPP firmy Apple. |



## <a name="applicationinventories"></a>applicationInventories

Jednostka **applicationInventory** tworzy listę aplikacji znalezionych na urządzeniu w czasie zbierania spisu.

| Właściwość  | Opis |
|---------|------------|
| deviceKey | To jest odwołanie do tabeli urządzenia, która zawiera identyfikator urządzenia usługi Intune. |
| dateKey | Odwołanie do tabeli dat wskazujące dzień spisu. |
| applicationName | Nazwa aplikacji. |
| applicationVersion | Wersja aplikacji. |
| bundleSize | Rozmiar aplikacji w bajtach. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

Jednostka **mobileAppInstallState** reprezentuje stan instalacji aplikacji mobilnej po przypisaniu jej do grupy zawierającej urządzenia, użytkowników lub obie te kategorie.

| Właściwość | Opis |
|---|---|
| appInstallStateKey | Unikatowy identyfikator stanu instalacji aplikacji dla konta użytkownika. |
| appInstallState | Wartość wyliczenia stanu instalacji aplikacji. |
| appInstallStateName | Nazwa stanu instalacji aplikacji. |



