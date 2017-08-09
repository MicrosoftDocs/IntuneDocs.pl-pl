---
title: Zasady | Microsoft Docs
description: "Temat referencyjny dotyczący kategorii Zasady kolekcji jednostek w interfejsie API magazynu danych usługi Microsoft Intune."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6af0ff1f463c153e62f6df63ce811076c5f692f2
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-policy-entities"></a>Dokumentacja jednostek zasad

Kategoria **Zasady** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje takie jak:

  -  Spis profilów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności  
  -  Liczba urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień  
  -  Liczba użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień  
  -  Łączna liczba urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd  

## <a name="policy"></a>Policy

Jednostka **Policy** zawiera listę profilów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| PolicyKey |Unikatowy klucz reprezentujący zasady w magazynie danych |123 |
| PolicyId |Unikatowy identyfikator zasad w magazynie danych |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Nazwa zasad |„Plan bazowy systemu Windows 10” |
| PolicyVersion |Wersja zasad. Po edycji lub zmianie zasad tworzona jest nowa wersja. |1, 2, 3 |
| IsDeleted |Wskazuje, czy rekord zasad został zaktualizowany.  True — zasady mają nowy rekord ze zaktualizowanymi polami. False — najnowszy rekord zasad. |True/False |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia zasad w magazynie danych |2016-11-23 12:00:00 |
| DeletedDateUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True |2016-11-23 12:00:00 |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji zasad w magazynie danych |2016-11-23 12:00:00 |

## <a name="policytype"></a>PolicyType

Jednostka **PolicyType** zawiera listę typów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| PolicyTypeId |Unikatowy identyfikator zasad w systemie źródłowym |123 |
| PolicyTypeKey |Unikatowy identyfikator zasad w magazynie danych |1 |
| PolicyTypeName |Nazwa typu zasad. |Zasady zgodności systemu Windows 10 |

## <a name="deviceconfiguration"></a>DeviceConfiguration

Jednostka **DeviceConfigurationProfileDeviceActivity** zawiera liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład urządzenie jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych |20160703 |
| Oczekiwanie |Liczba unikatowych urządzeń w stanie Oczekiwanie |123 |
| Sukces |Liczba unikatowych urządzeń w stanie Sukces |12 |
| Błąd |Liczba unikatowych urządzeń w stanie Błąd |10 |
| Niepowodzenie |Liczba unikatowych urządzeń w stanie Niepowodzenie |2 |

## <a name="userconfiguration"></a>UserConfiguration

Jednostka **UserConfigurationProfileDeviceActivity** zawiera liczbę użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład użytkownik jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd.  Jednostka **UserConfigurationProfileDeviceActivity** zawiera liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych |20160703 |
| Oczekiwanie |Liczba unikatowych użytkowników w stanie Oczekiwanie |123 |
| Sukces |Liczba unikatowych użytkowników w stanie Sukces |12 |
| Błąd |Liczba unikatowych użytkowników w stanie Błąd |10 |
| Niepowodzenie |Liczba unikatowych użytkowników w stanie Niepowodzenie |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

Jednostka **PolicyTypeActivity** zawiera łączną liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd. Zawiera listę tych stanów w odniesieniu do profilu konfiguracji urządzeń, profilu konfiguracji aplikacji lub zasad zgodności na dzień.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych |20160703 |
| PolicyKey |Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName |Plan bazowy systemu Windows 10 |
| PolicyTypeKey |Typ klucza zasad; można go połączyć z typem zasad w celu otrzymania nazwy typu zasad |Zasady zgodności systemu Windows 10 |
| Pending |Liczba unikatowych urządzeń w stanie Oczekiwanie |123 |
| Succeeded |Liczba unikatowych urządzeń w stanie Sukces |12 |
| Error |Liczba unikatowych urządzeń w stanie Błąd |10 |
| Fail- |Liczba unikatowych urządzeń w stanie Niepowodzenie |2 |