---
title: Aplikacja | Microsoft Docs
description: "Temat referencyjny dotyczący kategorii Aplikacja w kolekcji jednostek w interfejsie API magazynu danych usługi Intune."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e12792445b36ba6657cbe6b2f6c924f6d97fe3c
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2017
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
| AppKey |Unikatowy identyfikator aplikacji |123 |
| ApplicationId |Unikatowy identyfikator aplikacji — podobny do AppKey, ale ten klucz jest kluczem naturalnym. |b66bc706-ffff-7437-0340-032819502773 |
| Przegląd |Wersja zgodna z podaną przez administratora podczas przekazywania pliku binarnego |2 |
| Tytuł |Tytuł aplikacji |Excel |
| Wydawca |Wydawca aplikacji |Microsoft |
| UploadState |Stan przekazania aplikacji |1 |
| AppTypeKey |Odwołanie do jednostki AppType opisanej w następującej sekcji. | |
| VppProgramTypeKey |Odwołanie do jednostki VppProgramType opisanej poniżej | |
| CreationTime |Godzina utworzenia oceny |2016-11-23 12:00:00 |
| ModifiedTime |Godzina ostatniej zmiany dotyczącej oceny |2016-11-23 12:00:00 |
| Size |Rozmiar pliku binarnego | |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tej oceny aplikacji w magazynie danych |2016-11-23 12:00:00 |
| EndDateExclusiveUTC |Data i godzina w formacie UTC utracenia ważności przez tę ocenę aplikacji |2016-11-23 12:00:00 |
| IsCurrent |Wskazuje, czy ta wersja aplikacji jest aktualna w magazynie danych, czy nie |True/False |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tej wersji aplikacji w magazynie danych |2016-11-23 12:00:00 |

## <a name="appinstallertypes"></a>AppInstallerTypes

Jednostka **AppInstallerTypes** przedstawia źródło instalacji aplikacji.

| Właściwość  | Opis |
|---------|------------|
| AppTypeID |Identyfikator typu |
| AppTypeKey |Klucz zastępczy klucza |
| AppTypeName |Typ aplikacji |

## <a name="example"></a>Przykład

| AppTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Aplikacja ze sklepu dla systemu Android |Aplikacja ze sklepu dla systemu Android |
| 1 |Aplikacja LOB dla systemu Android |Aplikacja biznesowa dla systemu Android |
| 2 |Zarządzana aplikacja ze sklepu dla systemu Android (MAM) |Aplikacja ze sklepu dla systemu Android mająca włączone zarządzanie |
| 3 |Aplikacja ze sklepu dla systemu iOS |Aplikacja ze sklepu dla systemu iOS |
| 4 |Aplikacja LOB dla systemu iOS |Aplikacja biznesowa dla systemu iOS |
| 5 |Zarządzana aplikacja ze sklepu dla systemu iOS (MAM?) |Aplikacja ze sklepu dla systemu iOS mająca włączone zarządzanie |
| 6 |Pakiet O365 Pro Plus |Pakiet Office 365 Pro Plus dla systemu Windows 10 |
| 7 |Aplikacja internetowa |Aplikacja internetowa |
| 8 |Aplikacja ze sklepu dla systemu Windows Phone 8.1 |Aplikacja ze sklepu dla systemu Windows Phone 8.1 |
| 9 |Aplikacja ze Sklepu Windows |Aplikacja ze Sklepu Windows |
| 10 |Aplikacja LOB dla systemu Windows |Aplikacja biznesowa AppX dla systemu Windows |
| 11 |Aplikacja MSI dla systemu Windows Mobile |Aplikacja biznesowa MSI dla systemu Windows Mobile |
| 12 |Aplikacja LOB dla systemu Windows Phone |Aplikacja biznesowa dla systemu Windows Phone |

## <a name="applicationtypes"></a>ApplicationTypes

Jednostka **ApplicationTypes** zawiera listę możliwych typów aplikacji.

| Właściwość  | Opis |
|---------|------------|
| ApplicationTypeID |Identyfikator typu |
| ApplicationTypeKey |Klucz zastępczy klucza |
| ApplicationTypeName |Typ aplikacji |

## <a name="example"></a>Przykład

| ApplicationTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |InHouse |Aplikacja utworzona w firmie |
| 1 |DeepLink |Link do aplikacji w sklepie z aplikacjami |
| 2 |WebLink |Link do aplikacji internetowej |

## <a name="managedsoftwaretypes"></a>ManagedSoftwareTypes

Jednostka **ManagedSoftwareTypes** zawiera listę możliwych typów oprogramowania zarządzanego dla aplikacji.

| Właściwość  | Opis |
|---------|------------|
| SoftwareTypeID |Identyfikator typu |
| SoftwareTypeKey |Klucz zastępczy klucza |
| SoftwareTypeName |Typ oprogramowania |

## <a name="example"></a>Przykład

| SoftwareTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Komputery |Aplikacja klasyczna |
| 2 |Update |Aktualizacja systemu Windows |
| 5 |SideCarAgent | |
| 1 |Urządzenia przenośne |Aplikacja mobilna |
| 3 |WebLink |Link internetowy |
| 4 |VppDeepLink |Link do aplikacji w sklepie z aplikacjami, która jest częścią programu VPP (Volume Purchase Program) |

## <a name="vppprogramtypes"></a>VppProgramTypes

Jednostka **VppProgramTypes** zawiera listę możliwych typów programów VPP dla aplikacji.

| Właściwość  | Opis |
|---------|------------|
| VppProgramTypeID |Identyfikator typu |
| VppProgramTypeKey |Klucz zastępczy klucza |
| VppProgramTypeName |Typ programu VPP |

## <a name="example"></a>Przykład

| VppProgramID  | Nazwa | Opis |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |Program VPP firmy Microsoft |
| 00000000-0000-0000-0000-000000000000 |Jeszcze niedostępne |Wartość domyślna: No VPP (Brak VPP) |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |Program VPP firmy Apple |
