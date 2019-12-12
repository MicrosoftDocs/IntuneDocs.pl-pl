---
title: Zarządzanie aplikacjami mobilnymi (MAM)
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Zarządzanie aplikacjami mobilnymi kolekcji jednostki w interfejsie API magazynu danych usługi Microsoft Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: eb1833a6a54fe0a7f78958e653468921df952b4d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505697"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Dokumentacja jednostek zarządzania aplikacjami mobilnymi (MAM)

Kategoria **Zarządzanie aplikacjami mobilnymi** zawiera jednostki dla aplikacji mobilnych, takie jak:

- Aplikacje
- wystąpień
- Stan zameldowania
- Stan kondycji
- Stan zasad
- Stan rejestracji
- Typy platform

## <a name="mamapplications"></a>mamApplications

Jednostka **mamApplication** tworzy listę aplikacji biznesowych (LOB), które są zarządzane za pomocą oprogramowania do zarządzania aplikacjami mobilnymi (MAM) bez rejestracji w przedsiębiorstwie.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| mamApplicationKey |Unikatowy identyfikator aplikacji MAM. | 432 |
| mamApplicationName |Nazwa aplikacji MAM. |Przykładowa nazwa aplikacji MAM |
| mamApplicationId |Identyfikator aplikacji MAM. | 123 |
| isDeleted |Wskazuje, czy ten rekord aplikacji MAM został zaktualizowany. <br>True — aplikacja MAM ma nowy rekord ze zaktualizowanymi polami w tej tabeli. <br>False — to jest najnowszy rekord dla tej aplikacji MAM. |Prawda/Fałsz |
| startDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tej aplikacji MAM w magazynie danych. |2016-11-23 12:00:00 |
| deletedDateUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True. |2016-11-23 12:00:00 |
| rowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tej aplikacji MAM w magazynie danych. |2016-11-23 12:00:00 |


## <a name="mamapplicationinstances"></a>mamApplicationInstances

Jednostka **mamApplicationInstance** tworzy listę zarządzanych aplikacji zarządzania aplikacjami mobilnymi (MAM) jako pojedynczych wystąpień na użytkownika na urządzeniu. Wszyscy użytkownicy i urządzenia wymienieni w jednostce są chronieni, jakby mieli przypisane do siebie co najmniej jedne zasady MAM.


|          Właściwość          |                                                                                                  Opis                                                                                                  |               Przykład                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   applicationInstanceKey   |                                                               Unikatowy identyfikator wystąpienia aplikacji MAM w magazynie danych — klucz zastępczy.                                                                |                 123                  |
|           userId           |                                                                              Identyfikator użytkownika, który ma zainstalowaną tę aplikację MAM.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   applicationInstanceId    |                                              Unikatowy identyfikator wystąpienia aplikacji MAM — podobny do wartości ApplicationInstanceKey, ale identyfikator jest kluczem naturalnym.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Identyfikator aplikacji MAM, dla której utworzono to wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
|     applicationVersion     |                                                                                     Wersja aplikacji dla tej aplikacji MAM.                                                                                      |                  2                   |
|        createdDate         |                                                                 Data utworzenia tego rekordu wystąpienia aplikacji MAM. Wartość może być równa null.                                                                 |        2016-11-23 12:00:00        |
|          platform          |                                                                          Platforma urządzenia, na której zainstalowano tę aplikację MAM.                                                                           |                  2                   |
|      platformVersion       |                                                                      Wersja platformy urządzenia, na której jest zainstalowana ta aplikacja MAM.                                                                       |                 2.2                  |
|         sdkVersion         |                                                                            Wersja zestawu SDK MAM, za pomocą którego aplikacja MAM została opakowana.                                                                            |                 3.2                  |
| mamDeviceId | Identyfikator urządzenia, z którym zostało skojarzone wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
| mamDeviceType | Typ urządzenia, z którym jest skojarzone wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
| mamDeviceName | Nazwa urządzenia, z którym jest skojarzone wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
|         isDeleted          | Wskazuje, czy ten rekord wystąpienia aplikacji MAM został zaktualizowany. <br>True — to wystąpienie aplikacji MAM ma nowy rekord ze zaktualizowanymi polami w tej tabeli. <br>False — to jest najnowszy rekord dla tego wystąpienia aplikacji MAM. |              Prawda/Fałsz              |
|   startDateInclusiveUtc    |                                                              Data i godzina w formacie UTC utworzenia tego wystąpienia aplikacji MAM w magazynie danych.                                                               |        2016-11-23 12:00:00        |
|       deletedDateUtc       |                                                                             Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True.                                                                              |        2016-11-23 12:00:00        |
| rowLastModifiedDateTimeUtc |                                                           Data i godzina w formacie UTC ostatniej modyfikacji tego wystąpienia aplikacji MAM w magazynie danych.                                                            |        2016-11-23 12:00:00        |


## <a name="mamcheckins"></a>mamCheckins

Jednostka **mamCheckin** reprezentuje dane zebrane po zaewidencjonowaniu wystąpienia aplikacji zarządzania aplikacjami mobilnymi (MAM) przez usługę Intune. 

> [!Note]  
> Gdy wystąpienie aplikacji zostanie zameldowane wiele razy w ciągu dnia, magazyn danych zapisuje to jako jedno zameldowanie.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| dateKey |Klucz daty zarejestrowania zameldowania aplikacji MAM w magazynie danych. | 20160703 |
| applicationInstanceKey |Klucz wystąpienia aplikacji skojarzony z zameldowaniem tej aplikacji MAM. | 123 |
| userKey |Klucz użytkownika skojarzony z zameldowaniem tej aplikacji MAM. | 4323 |
| mamApplicationKey |Klucz aplikacji skojarzonej z zameldowaniem aplikacji MAM. | 432 |
| deviceHealthKey |Klucz kondycji urządzenia skojarzony z zameldowaniem tej aplikacji MAM. | 321 |
| platformKey |Reprezentuje platformę urządzenia skojarzonego z zameldowaniem tej aplikacji MAM. |123 |
| effectiveAppliedPolicyKey |Reprezentuje efektywnie zastosowane zasady skojarzone z aplikacją MAM, która została zameldowana. Efektywne zastosowanie zasad jest wynikiem scalenia wszystkich zasad dotyczących danej aplikacji i użytkownika. | 322 |
| pastCheckInDate |Data i godzina ostatniego zameldowania tej aplikacji MAM. Wartość może być równa null. |2016-11-23 12:00:00 |


## <a name="mamdevicehealth"></a>mamDeviceHealth

Jednostka **mamDeviceHealth** reprezentuje urządzenia, które mają wdrożone zasady zarządzania aplikacjami mobilnymi (MAM), nawet jeśli zdjęto z nich zabezpieczenia systemu.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| deviceHealthKey |Unikatowy identyfikator urządzenia i jego skojarzonej kondycji w magazynie danych — klucz zastępczy. |123 |
| deviceHealth |Unikatowy identyfikator urządzenia i jego skojarzonej kondycji — podobny do wartości DeviceHealthKey, ale identyfikator jest kluczem naturalnym. |b66bc706-ffff-7777-0340-032819502773 |
| deviceHealthName |Reprezentuje stan urządzenia. <br>Not available — brak informacji o tym urządzeniu. <br>Healthy — urządzenie nie ma zdjętych zabezpieczeń systemu. <br>Unhealthy — urządzenie ma zdjęte zabezpieczenia systemu. |Not Available Healthy Unhealthy |
| rowLastModifiedDateTimeUtc |Data i godzina w formacie UTC ostatniej modyfikacji kondycji konkretnego urządzenia MAM w magazynie danych. |2016-11-23 12:00:00 |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

Jednostka **mamEffectivePolicy** zawiera listę wszystkich efektywnych zasad zarządzania aplikacjami mobilnymi (MAM) stosowanych w Twojej organizacji. Efektywne zastosowanie zasad jest wynikiem scalenia wszystkich zasad dotyczących danej aplikacji i użytkownika.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| effectivePolicyKey |Unikatowy identyfikator efektywnych zasad MAM w magazynie danych. |2 |
| realPolicyKey |Unikatowy identyfikator zasad MAM utworzonych przez informatyka. |1 |
| rowCreatedDateTimeUtc |Data i godzina w formacie UTC utworzenia efektywnych zasad MAM w magazynie danych. |2016-11-23 12:00:00 |

## <a name="mamplatforms"></a>mamPlatforms

Jednostka **mamPlatform** tworzy listę nazw platform i typów, na których zainstalowano aplikację zarządzania aplikacjami mobilnymi (MAM).


|          Właściwość          |                                    Opis                                    |                         Przykład                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        platformKey         |     Unikatowy identyfikator platformy w magazynie danych — klucz zastępczy.      |                           123                           |
|          platform          | Unikatowy identyfikator platformy — podobny do wartości PlatformKey, ale jest kluczem naturalnym. |                           123                           |
|        platformName        |                                   Nazwa platformy                                   | Niedostępny <br>Brak <br>Windows <br>System iOS <br>Urządzenia z systemem Android. |
| rowLastModifiedDateTimeUtc | Data i godzina w formacie UTC ostatniej modyfikacji tej platformy w magazynie danych.  |                 2016-11-23 12:00:00                  |

