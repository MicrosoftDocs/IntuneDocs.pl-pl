---
title: Dokumentacja jednostek zasad
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Zasady kolekcji jednostek w interfejsie API magazynu danych usługi Microsoft Intune.
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
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 64fc1bab596715be80fd3a91c003cac1176fe787
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490278"
---
# <a name="reference-for-policy-entities"></a>Dokumentacja jednostek zasad

Kategoria **policies** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje, takie jak:

- Spis profilów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności  
- Liczba urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień  
- Liczba użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień  
- Łączna liczba urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd  

## <a name="policies"></a>policies

Jednostka **policy** zawiera listę profilów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| policyKey |Unikatowy klucz reprezentujący zasady w magazynie danych. |123 |
| policyId |Unikatowy identyfikator zasad w magazynie danych. |b66bc706-ffff-7437-0340-032819502773 |
| policyName |Nazwa zasad. |„Plan bazowy systemu Windows 10” |
| policyVersion |Wersja zasad. Po edycji lub zmianie zasad tworzona jest nowa wersja. |1, 2, 3 |
| isDeleted |Wskazuje, czy rekord zasad został zaktualizowany.  <br>True — zasady mają nowy rekord ze zaktualizowanymi polami. <br>False — najnowszy rekord zasad. |Prawda/Fałsz |
| startDateInclusiveUTC |Data i godzina w formacie UTC utworzenia zasad w magazynie danych. |2016-11-23 12:00:00 |
| deletedDateUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True. |2016-11-23 12:00:00 |
| rowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji zasad w magazynie danych. |2016-11-23 12:00:00 |

## <a name="policytypes"></a>policyTypes

Jednostka **policyType** zawiera listę typów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| policyTypeId |Unikatowy identyfikator zasad w systemie źródłowym. |123 |
| policyTypeKey |Unikatowy identyfikator zasad w magazynie danych. |1 |
| policyTypeName |Nazwa typu zasad. |Zasady zgodności systemu Windows 10. |

## <a name="device-configuration"></a>Konfiguracja urządzenia

Jednostka **deviceConfigurationProfileDeviceActivity** zawiera liczbę **urządzeń** w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład **urządzenie** jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| dateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych. |20160703 |
| Oczekiwanie |Liczba unikatowych urządzeń w stanie Oczekiwanie. |123 |
| Sukces |Liczba unikatowych urządzeń w stanie Sukces. |12 |
| Błąd |Liczba unikatowych urządzeń w stanie Błąd. |10 |
| Niepowodzenie |Liczba unikatowych urządzeń w stanie Niepowodzenie. |2 |

Jednostka **deviceConfigurationProfileUserActivity** zawiera liczbę **użytkowników** w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład **użytkownik** jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd.  Jednostka **deviceConfigurationProfileUserActivity** zawiera liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| dateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych. |20160703 |
| Oczekiwanie |Liczba unikatowych użytkowników w stanie Oczekiwanie. |123 |
| Sukces |Liczba unikatowych użytkowników w stanie Sukces. |12 |
| Błąd |Liczba unikatowych użytkowników w stanie Błąd. |10 |
| Niepowodzenie |Liczba unikatowych użytkowników w stanie Niepowodzenie. |2 |

## <a name="policytypeactivities"></a>policyTypeActivities

Jednostka **policyTypeActivity** zawiera łączną liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd. Zawiera listę tych stanów w odniesieniu do profilu konfiguracji urządzeń, profilu konfiguracji aplikacji lub zasad zgodności na dzień.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| dateKey |Klucz dateKey zarejestrowania zaewidencjonowania profilu konfiguracji urządzeń w magazynie danych. |20160703 |
| policyKey |Klucz policyKey można połączyć z zasadami w celu otrzymania jednostki policyName. |Plan bazowy systemu Windows 10 |
| policyTypeKey |Typ klucza zasad; można go połączyć z typem zasad w celu otrzymania nazwy typu zasad. |Zasady zgodności systemu Windows 10 |
| Oczekiwanie |Liczba unikatowych urządzeń w stanie Oczekiwanie. |123 |
| Sukces |Liczba unikatowych urządzeń w stanie Sukces. |12 |
| Błąd |Liczba unikatowych urządzeń w stanie Błąd. |10 |
| Niepowodzenie |Liczba unikatowych urządzeń w stanie Niepowodzenie. |2 |

## <a name="compliance-policy"></a>Zasady zgodności

Dokumentacja interfejsu API zasad zgodności zawiera jednostki, które udostępniają informacje o zasadach zgodności przypisanych do urządzeń.

### <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities

Poniższa tabela zawiera podsumowanie stanu przypisania zasad zgodności do urządzeń. Wyświetla ona liczbę znalezionych urządzeń z poszczególnymi stanami zgodności.


|Właściwość     |Opis  |Przykład  |
|---------|---------|---------|
|dateKey  |Klucz daty utworzenia podsumowania zasad zgodności.|20161204 |
|unknown  |Liczba urządzeń, które są w trybie offline lub nie nawiązały łączności z usługą Intune lub Azure AD z innych przyczyn. |5|
|notApplicable      |Liczba urządzeń, na których nie mają zastosowania zasady zgodności urządzeń przepisane przez administratora.|201 |
|compliant      |Liczba urządzeń, które pomyślnie zastosowały co najmniej jedne zasady zgodności urządzenia przepisane przez administratora. |4083 |
|inGracePeriod      |Liczba urządzeń, które nie są zgodne, ale są w okresie prolongaty zdefiniowanym przez administratora. |57|
|nonCompliant      |Liczba urządzeń, na których nie udało się zastosować co najmniej jednej z zasad zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora.|43 |
|Błąd      |Liczba urządzeń, które nie mogły nawiązać połączenia z usługą Intune lub usługą Azure AD i zwróciły komunikat o błędzie. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities 

Poniższa tabela zawiera podsumowanie stanu przypisania zasad zgodności do urządzeń na podstawie zasad i na podstawie typu zasad. Wyświetla ona liczbę znalezionych urządzeń z poszczególnymi stanami zgodności dla każdej przypisanej zasady zgodności.



|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|dateKey  |Klucz daty utworzenia podsumowania zasad zgodności.|20161219|
|policyKey     |Klucz zasad zgodności, dla których utworzono podsumowanie. |10178 |
|policyPlatformKey      |Klucz typu platformy zasad zgodności, dla którego utworzono podsumowanie.|5|
|unknown     |Liczba urządzeń, które są w trybie offline lub nie nawiązały łączności z usługą Intune lub Azure AD z innych przyczyn.|13|
|notApplicable     |Liczba urządzeń, na których nie mają zastosowania zasady zgodności urządzeń przepisane przez administratora.|3|
|compliant      |Liczba urządzeń, które pomyślnie zastosowały co najmniej jedne zasady zgodności urządzenia przepisane przez administratora. |45|
|inGracePeriod      |Liczba urządzeń, które nie są zgodne, ale są w okresie prolongaty zdefiniowanym przez administratora. |3|
|nonCompliant      |Liczba urządzeń, na których nie udało się zastosować co najmniej jednej z zasad zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora.|7|
|Błąd      |Liczba urządzeń, które nie mogły nawiązać połączenia z usługą Intune lub usługą Azure AD i zwróciły komunikat o błędzie. |3|

### <a name="policyplatformtypes"></a>policyPlatformTypes

Poniższa tabela zawiera typy platform wszystkich przypisanych zasad. Typy platform zasad, które nigdy nie zostały przypisane do żadnego urządzenia, nie są obecne w tej tabeli.


|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|policyPlatformTypeKey      |Unikatowy klucz typu platformy zasad. |20170519 |
|policyPlatformTypeId      |Unikatowy identyfikator typu platformy zasad.|1|
|policyPlatformTypeName      |Nazwa typu platformy zasad.|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

Poniższa tabela zawiera liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Liczba odzwierciedla dane dla profilów typów zasad. Jeśli na przykład urządzenie jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka policyDeviceActivity przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|dateKey|Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych.|20160703|
|Oczekiwanie|Liczba unikatowych urządzeń w stanie Oczekiwanie.|123|
|Sukces|Liczba unikatowych urządzeń w stanie Sukces.|12|
|policyKey|Klucz policyKey można połączyć z zasadami w celu otrzymania jednostki policyName.|Plan bazowy systemu Windows 10|
|Błąd|Liczba unikatowych urządzeń w stanie Błąd.|10|
|Niepowodzenie|Liczba unikatowych urządzeń w stanie Niepowodzenie.|2|

### <a name="policyuseractivities"></a>policyUserActivities

Poniższa tabela zawiera liczbę użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Liczba odzwierciedla dane dla profilów typów zasad. Jeśli na przykład użytkownik jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd. Jednostka PolicyUserActivity przedstawia liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni.


| Właściwość  |                                         Opis                                         |       Przykład       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  dateKey  | Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych. |      20160703       |
|  Oczekiwanie  |                         Liczba unikatowych urządzeń w stanie Oczekiwanie.                          |         123         |
| Sukces |                         Liczba unikatowych urządzeń w stanie Sukces.                          |         12          |
| policyKey |                 Klucz policyKey można połączyć z zasadami w celu otrzymania jednostki policyName.                 | Plan bazowy systemu Windows 10 |
|   Błąd   |                          Liczba unikatowych urządzeń w stanie Błąd.                           |         10          |

