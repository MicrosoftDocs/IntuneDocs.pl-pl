---
title: Zarządzanie aplikacjami mobilnymi (MAM)
titlesuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Zarządzanie aplikacjami mobilnymi kolekcji jednostki w interfejsie API magazynu danych usługi Microsoft Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8f9313b35e6cb9da5d517e8f06e04c5a567612f4
ms.sourcegitcommit: 445a54dc6826a549d770a9953549ae2191d391c2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727537"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Dokumentacja jednostek zarządzania aplikacjami mobilnymi (MAM)

Kategoria **Zarządzanie aplikacjami mobilnymi** zawiera jednostki dla aplikacji mobilnych, takie jak:

  -  Aplikacje
  -  wystąpień
  -  Stan zameldowania
  -  Stan kondycji
  -  Stan zasad
  -  Stan rejestracji
  -  Typy platform

## <a name="mamapplication"></a>MamApplication

Jednostka **MamApplication** tworzy listę aplikacji biznesowych (LOB), które są zarządzane za pomocą zarządzania aplikacjami mobilnymi (MAM) bez rejestracji w Twoim przedsiębiorstwie.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| ApplicationKey |Unikatowy identyfikator aplikacji MAM w magazynie danych. |123 |
| ApplicationName |Nazwa aplikacji MAM. |„Word” |
| ApplicationId |Identyfikator aplikacji dla aplikacji MAM. |b66bc706-ffff-7437-0340-032819502773 |
| IsDeleted |Wskazuje, czy ten rekord aplikacji MAM został zaktualizowany. <br>True — aplikacja MAM ma nowy rekord ze zaktualizowanymi polami w tej tabeli. <br>False — to jest najnowszy rekord dla tej aplikacji MAM. |Prawda/Fałsz |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tej aplikacji MAM w magazynie danych. |2016-11-23 12:00:00 |
| DeletedDateUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True. |2016-11-23 12:00:00 |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tej aplikacji MAM w magazynie danych. |2016-11-23 12:00:00 |

## <a name="mamapplicationinstance"></a>MamApplicationInstance

Jednostka **MamApplicationInstance** tworzy listę zarządzanych aplikacji zarządzania aplikacjami mobilnymi (MAM) jako pojedynczych wystąpień na użytkownika na urządzeniu. Wszyscy użytkownicy i urządzenia wymienieni w jednostce są chronieni, jakby mieli przypisane do siebie co najmniej jedne zasady MAM.


|          Właściwość          |                                                                                                  Opis                                                                                                  |               Przykład                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   ApplicationInstanceKey   |                                                               Unikatowy identyfikator wystąpienia aplikacji MAM w magazynie danych — klucz zastępczy.                                                                |                 123                  |
|           UserId           |                                                                              Identyfikator użytkownika, który ma zainstalowaną tę aplikację MAM.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              Unikatowy identyfikator wystąpienia aplikacji MAM — podobny do wartości ApplicationInstanceKey, ale identyfikator jest kluczem naturalnym.                                              | b66bc706-ffff-7437-0340-032819502773 |
|       ApplicationId        |                                                                                        Identyfikator aplikacji dla tej aplikacji MAM                                                                                         |  com.microsoft.groupies-daily.<IOS>  |
|     ApplicationVersion     |                                                                                     Wersja aplikacji dla tej aplikacji MAM.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 Data utworzenia tego rekordu wystąpienia aplikacji MAM. Wartość może być równa null.                                                                 |        2016-11-23 12:00:00        |
|          Platforma          |                                                                          Platforma urządzenia, na której zainstalowano tę aplikację MAM.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Wersja platformy urządzenia, na której jest zainstalowana ta aplikacja MAM.                                                                       |                 2.2                  |
|         SdkVersion         |                                                                            Wersja zestawu SDK MAM, za pomocą którego aplikacja MAM została opakowana.                                                                            |                 3.2                  |
|          DeviceId          |                                                                          Identyfikator urządzenia dla urządzenia, na którym zainstalowano tę aplikację MAM.                                                                          | b66bc706-ffff-7437-0340-032819502773 |
|         DeviceName         |                                                                         Nazwa urządzenia dla urządzenia, na którym zainstalowano tę aplikację MAM.                                                                         |              „MyDevice”              |
|         IsDeleted          | Wskazuje, czy ten rekord wystąpienia aplikacji MAM został zaktualizowany. <br>True — to wystąpienie aplikacji MAM ma nowy rekord ze zaktualizowanymi polami w tej tabeli. <br>False — to jest najnowszy rekord dla tego wystąpienia aplikacji MAM. |              Prawda/Fałsz              |
|   StartDateInclusiveUTC    |                                                              Data i godzina w formacie UTC utworzenia tego wystąpienia aplikacji MAM w magazynie danych.                                                               |        2016-11-23 12:00:00        |
|       DeletedDateUTC       |                                                                             Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True.                                                                              |        2016-11-23 12:00:00        |
| RowLastModifiedDateTimeUTC |                                                           Data i godzina w formacie UTC ostatniej modyfikacji tego wystąpienia aplikacji MAM w magazynie danych.                                                            |        2016-11-23 12:00:00        |

## <a name="mamcheckin"></a>MamCheckin

Jednostka **MamCheckin** reprezentuje dane zebrane po zameldowaniu wystąpienia aplikacji zarządzania aplikacjami mobilnymi (MAM) przez usługę Intune. 

> [!Note]  
> Gdy wystąpienie aplikacji zostanie zameldowane wiele razy w ciągu dnia, magazyn danych zapisuje to jako jedno zameldowanie.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania aplikacji MAM w magazynie danych. | 20160703 |
| ApplicationInstanceKey |Klucz wystąpienia aplikacji skojarzony z zameldowaniem tej aplikacji MAM. |1900-02-05 12:00:00 |
| UserKey |Klucz użytkownika skojarzony z zameldowaniem tej aplikacji MAM. |1900-12-01 12:00:00 |
| ApplicationKey |Klucz aplikacji MAM, która została zameldowana. |1900-01-10 12:00:00 |
| DeviceHealthKey |Klucz kondycji urządzenia skojarzony z zameldowaniem tej aplikacji MAM. |1900-02-01 12:00:00 |
| PlatformKey |Reprezentuje platformę urządzenia skojarzonego z zameldowaniem tej aplikacji MAM. |1900-01-01 12:00:00 |
| EffectiveAppliedPolicyKey |Reprezentuje efektywnie zastosowane zasady skojarzone z aplikacją MAM, która została zameldowana. Efektywne zastosowanie zasad jest wynikiem scalenia wszystkich zasad dotyczących danej aplikacji i użytkownika. |1900-02-05 12:00:00 |
| LastCheckInDate |Data i godzina ostatniego zameldowania tej aplikacji MAM. Wartość może być równa null. |2016-11-23 12:00:00 |

## <a name="mamdevicehealth"></a>MamDeviceHealth

Jednostka **MamDeviceHealth** reprezentuje urządzenia, które mają wdrożone zasady zarządzania aplikacjami mobilnymi (MAM), nawet jeśli zdjęto z nich zabezpieczenia systemu.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| DeviceHealthKey |Unikatowy identyfikator urządzenia i jego skojarzonej kondycji w magazynie danych — klucz zastępczy. |1900-01-01 12:00:00 |
| DeviceHealth |Unikatowy identyfikator urządzenia i jego skojarzonej kondycji — podobny do wartości DeviceHealthKey, ale identyfikator jest kluczem naturalnym. |1900-01-01 12:00:00 |
| DeviceHealthName |Reprezentuje stan urządzenia. <br>Not available — brak informacji o tym urządzeniu. <br>Healthy — urządzenie nie ma zdjętych zabezpieczeń systemu. <br>Unhealthy — urządzenie ma zdjęte zabezpieczenia systemu. |Not Available Healthy Unhealthy |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji kondycji konkretnego urządzenia MAM w magazynie danych. |2016-11-23 12:00:00 |

## <a name="mameffectivepolicy"></a>MamEffectivePolicy

Jednostka **MamEffectivePolicy** zawiera listę wszystkich efektywnych zasad zarządzania aplikacjami mobilnymi (MAM) stosowanych w Twojej organizacji. Efektywne zastosowanie zasad jest wynikiem scalenia wszystkich zasad dotyczących danej aplikacji i użytkownika.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| EffectivePolicyKey |Unikatowy identyfikator efektywnych zasad MAM w magazynie danych. |2 |
| RealPolicyKey |Unikatowy identyfikator zasad MAM utworzonych przez informatyka. |1 |
| RowCreatedDateTimeUtc |Data i godzina w formacie UTC utworzenia efektywnych zasad MAM w magazynie danych. |2016-11-23 12:00:00 |

## <a name="mamglobalapplication"></a>MamGlobalApplication

Jednostka **MamGlobalApplication** tworzy listę aplikacji ze sklepu, które są zarządzane za pomocą zarządzania aplikacjami mobilnymi (MAM) bez rejestracji w Twoim przedsiębiorstwie.


|          Właściwość          |                                               Opis                                               |           Przykład            |
|----------------------------|---------------------------------------------------------------------------------------------------------|------------------------------|
|       ApplicationKey       |          Unikatowy identyfikator aplikacji ze sklepu w magazynie danych, znany jako klucz zastępczy.          |             123              |
|       ApplicationId        | Unikatowy identyfikator aplikacji ze sklepu. Identyfikator jest podobny do wartości ApplicationKey, ale jest kluczem naturalnym.  | com.microsoft.skydrive.<ios> |
|      ApplicationName       |                                      Nazwa globalnej aplikacji MAM.                                       |           SkyDrive           |
| RowLastModifiedDateTimeUTC | Data i godzina w formacie UTC ostatniej modyfikacji konkretnej globalnej aplikacji MAM w magazynie danych. |    2016-11-23 12:00:00    |

## <a name="mamplatform"></a>MamPlatform

Jednostka **MamPlatform** tworzy listę nazw platform i typów, na których zainstalowano aplikację zarządzania aplikacjami mobilnymi (MAM).


|          Właściwość          |                                    Opis                                    |                         Przykład                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        PlatformKey         |     Unikatowy identyfikator platformy w magazynie danych — klucz zastępczy.      |                           123                           |
|          Platforma          | Unikatowy identyfikator platformy — podobny do wartości PlatformKey, ale jest kluczem naturalnym. |                           123                           |
|        PlatformName        |                                   Nazwa platformy                                   | Niedostępny <br>Brak <br>Windows <br>System iOS <br>Urządzenia z systemem Android. |
| RowLastModifiedDateTimeUTC | Data i godzina w formacie UTC ostatniej modyfikacji tej platformy w magazynie danych.  |                 2016-11-23 12:00:00                  |

