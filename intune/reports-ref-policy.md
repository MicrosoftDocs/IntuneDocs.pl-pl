---
title: Policy
titlesuffix: Microsoft Intune
description: "Temat referencyjny dotyczący kategorii Zasady kolekcji jednostek w interfejsie API magazynu danych usługi Microsoft Intune."
keywords: "Magazyn danych usługi Intune"
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/12/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c5546c686a51170c8c854252cddb048685c6b2d2
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2018
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
| PolicyKey |Unikatowy klucz reprezentujący zasady w magazynie danych. |123 |
| PolicyId |Unikatowy identyfikator zasad w magazynie danych. |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Nazwa zasad. |„Plan bazowy systemu Windows 10” |
| PolicyVersion |Wersja zasad. Po edycji lub zmianie zasad tworzona jest nowa wersja. |1, 2, 3 |
| IsDeleted |Wskazuje, czy rekord zasad został zaktualizowany.  <br>True — zasady mają nowy rekord ze zaktualizowanymi polami. <br>False — najnowszy rekord zasad. |Prawda/Fałsz |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia zasad w magazynie danych. |2016-11-23 12:00:00 |
| DeletedDateUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True. |2016-11-23 12:00:00 |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji zasad w magazynie danych. |2016-11-23 12:00:00 |

## <a name="policytype"></a>PolicyType

Jednostka **PolicyType** zawiera listę typów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| PolicyTypeId |Unikatowy identyfikator zasad w systemie źródłowym. |123 |
| PolicyTypeKey |Unikatowy identyfikator zasad w magazynie danych. |1 |
| PolicyTypeName |Nazwa typu zasad. |Zasady zgodności systemu Windows 10. |

## <a name="deviceconfiguration"></a>DeviceConfiguration

Jednostka **DeviceConfigurationProfileDeviceActivity** zawiera liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład urządzenie jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych. |20160703 |
| Oczekiwanie |Liczba unikatowych urządzeń w stanie Oczekiwanie. |123 |
| Sukces |Liczba unikatowych urządzeń w stanie Sukces. |12 |
| Error |Liczba unikatowych urządzeń w stanie Błąd. |10 |
| Niepowodzenie |Liczba unikatowych urządzeń w stanie Niepowodzenie. |2 |



Jednostka **DeviceConfigurationProfileUserActivity** zawiera liczbę użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład użytkownik jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd.  Jednostka **DeviceConfigurationProfileUserActivity** zawiera liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych. |20160703 |
| Oczekiwanie |Liczba unikatowych użytkowników w stanie Oczekiwanie. |123 |
| Sukces |Liczba unikatowych użytkowników w stanie Sukces. |12 |
| Error |Liczba unikatowych użytkowników w stanie Błąd. |10 |
| Niepowodzenie |Liczba unikatowych użytkowników w stanie Niepowodzenie. |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

Jednostka **PolicyTypeActivity** zawiera łączną liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd. Zawiera listę tych stanów w odniesieniu do profilu konfiguracji urządzeń, profilu konfiguracji aplikacji lub zasad zgodności na dzień.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych. |20160703 |
| PolicyKey |Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName. |Plan bazowy systemu Windows 10 |
| PolicyTypeKey |Typ klucza zasad; można go połączyć z typem zasad w celu otrzymania nazwy typu zasad. |Zasady zgodności systemu Windows 10 |
| Oczekiwanie |Liczba unikatowych urządzeń w stanie Oczekiwanie. |123 |
| Sukces |Liczba unikatowych urządzeń w stanie Sukces. |12 |
| Error |Liczba unikatowych urządzeń w stanie Błąd. |10 |
| Niepowodzenie |Liczba unikatowych urządzeń w stanie Niepowodzenie. |2 |

## <a name="compliance-policy"></a>Zasady zgodności

Dokumentacja interfejsu API zasad zgodności zawiera jednostki, które udostępniają informacje o zasadach zgodności przypisanych do urządzeń.

### <a name="compliancepolicystatusdeviceactivities"></a>CompliancePolicyStatusDeviceActivities

Poniższa tabela zawiera podsumowanie stanu przypisania zasad zgodności do urządzeń. Wyświetla ona liczbę znalezionych urządzeń z poszczególnymi stanami zgodności.


|Właściwość     |Opis  |Przykład  |
|---------|---------|---------|
|DateKey  |Klucz daty utworzenia podsumowania zasad zgodności.|20161204 |
|Nieznane  |Liczba urządzeń, które są w trybie offline lub nie nawiązały łączności z usługą Intune lub Azure AD z innych przyczyn. |5|
|NotApplicable      |Liczba urządzeń, na których nie mają zastosowania zasady zgodności urządzeń przepisane przez administratora.|201 |
|Zgodny      |Liczba urządzeń, które pomyślnie zastosowały co najmniej jedne zasady zgodności urządzenia przepisane przez administratora. |4083 |
|InGracePeriod      |Liczba urządzeń, które nie są zgodne, ale są w okresie prolongaty zdefiniowanym przez administratora. |57|
|NonCompliant      |Liczba urządzeń, na których nie udało się zastosować co najmniej jednej z zasad zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora.|43 |
|Error      |Liczba urządzeń, które nie mogły nawiązać połączenia z usługą Intune lub usługą Azure AD i zwróciły komunikat o błędzie. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>CompliancePolicyStatusDevicePerPolicyActivities 

Poniższa tabela zawiera podsumowanie stanu przypisania zasad zgodności do urządzeń na podstawie zasad i na podstawie typu zasad. Wyświetla ona liczbę znalezionych urządzeń z poszczególnymi stanami zgodności dla każdej przypisanej zasady zgodności.



|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|DateKey  |Klucz daty utworzenia podsumowania zasad zgodności.|20161219|
|PolicyKey     |Klucz zasad zgodności, dla których utworzono podsumowanie. |10178 |
|PolicyPlatformKey      |Klucz typu platformy zasad zgodności, dla którego utworzono podsumowanie.|5|
|Nieznane     |Liczba urządzeń, które są w trybie offline lub nie nawiązały łączności z usługą Intune lub Azure AD z innych przyczyn.|13|
|NotApplicable     |Liczba urządzeń, na których nie mają zastosowania zasady zgodności urządzeń przepisane przez administratora.|3|
|Zgodny      |Liczba urządzeń, które pomyślnie zastosowały co najmniej jedne zasady zgodności urządzenia przepisane przez administratora. |45|
|InGracePeriod      |Liczba urządzeń, które nie są zgodne, ale są w okresie prolongaty zdefiniowanym przez administratora. |3|
|NonCompliant      |Liczba urządzeń, na których nie udało się zastosować co najmniej jednej z zasad zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora.|7|
|Error      |Liczba urządzeń, które nie mogły nawiązać połączenia z usługą Intune lub usługą Azure AD i zwróciły komunikat o błędzie. |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

Poniższa tabela zawiera typy platform wszystkich przypisanych zasad. Typy platform zasad, które nigdy nie zostały przypisane do żadnego urządzenia, nie są obecne w tej tabeli.


|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |Unikatowy klucz typu platformy zasad. |20170519 |
|PolicyPlatformTypeId      |Unikatowy identyfikator typu platformy zasad.|1|
|PolicyPlatformTypeName      |Nazwa typu platformy zasad.|AndroidForWork |

### <a name="policydeviceactivity"></a>PolicyDeviceActivity

Poniższa tabela zawiera liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Liczba odzwierciedla dane dla profilów typów zasad. Jeśli na przykład urządzenie jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka PolicyDeviceActivity przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|DateKey|Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych.|20160703|
|Oczekiwanie|Liczba unikatowych urządzeń w stanie Oczekiwanie.|123|
|Sukces|Liczba unikatowych urządzeń w stanie Sukces.|12|
PolicyKey|Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName.|Plan bazowy systemu Windows 10|
|Error|Liczba unikatowych urządzeń w stanie Błąd.|10|
|Niepowodzenie|Liczba unikatowych urządzeń w stanie Niepowodzenie.|2|

### <a name="policyuseractivity"></a>PolicyUserActivity 

Poniższa tabela zawiera liczbę użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Liczba odzwierciedla dane dla profilów typów zasad. Jeśli na przykład użytkownik jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd. Jednostka PolicyUserActivity przedstawia liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni.

|Właściwość  |Opis  |Przykład  |
|---------|---------|---------|
|DateKey|Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych.|20160703|
|Oczekiwanie|Liczba unikatowych urządzeń w stanie Oczekiwanie.|123|
|Sukces|Liczba unikatowych urządzeń w stanie Sukces.|12|
PolicyKey|Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName.|Plan bazowy systemu Windows 10|
|Error|Liczba unikatowych urządzeń w stanie Błąd.|10|
