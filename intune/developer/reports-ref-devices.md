---
title: Urządzenia — magazyn danych usługi Intune
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Urządzenia w kolekcji jednostki w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 85b6d49f435ec45a2c6a2b81387ea25a1c15299b
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654077"
---
# <a name="reference-for-devices-entities"></a>Odwołanie do jednostek urządzeń

Kategoria **devices** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje, takie jak:

- Typ urządzenia
- Rejestrowanie urządzenia i stan rejestracji
- Własność urządzeń
- Stan zarządzania urządzeniem
- Przynależność urządzenia do stanu usługi Azure AD
- Stan rejestracji
- Historyczne informacje o urządzeniu
- Spis aplikacji na urządzeniu

## <a name="devicetypes"></a>deviceTypes

Jednostka **deviceTypes** reprezentuje typ urządzenia przywoływany przez inne jednostki magazynu danych. Typ urządzenia zwykle opisuje model urządzenia, producenta lub kombinację obu tych informacji.

| Właściwość  | Opis |
|---------|------------|
| deviceTypeID |Unikatowy identyfikator typu urządzenia |
| deviceTypeKey |Unikatowy identyfikator typu urządzenia w magazynie danych — klucz zastępczy |
| deviceTypeName |Typ urządzenia |

### <a name="example"></a>Przykład

| deviceTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Komputery |Komputer z systemem Windows |
| 1 |Windows RT |Urządzenie z systemem Windows RT |
| 2 |WinMO6 |Urządzenie z systemem Windows Mobile 6.0 |
| 3 |Nokia |Urządzenie firmy Nokia |
| 4 |WindowsPhone |Urządzenie z systemem Windows Phone |
| 5 |Mac |Urządzenie Mac |
| 6 |WinCE |Urządzenia z systemem Windows CE |
| 7 |WinEmbedded |Urządzenie z systemem Windows Embedded |
| 8 |iPhone |Urządzenie iPhone |
| 9 |iPad |Urządzenie iPad |
| 10 |iPod |Urządzenie iPod |
| 11 |Android |Urządzenie z systemem Android zarządzane przy użyciu administratora urządzenia |
| 12 |ISocConsumer |Urządzenie iSoc Consumer |
| 14 |MacMDM |Urządzenie z systemem Mac OS X zarządzane za pomocą wbudowanego agenta MDM |
| 15 |HoloLens |Urządzenie HoloLens |
| 16 |SurfaceHub |Urządzenie Surface Hub |
| 17 |AndroidForWork |Urządzenie z systemem Android zarządzane przy pomocy właściciela profilu systemu Android |
| 100 |Blackberry |Urządzenie Blackberry |
| 101 |Palm |Urządzenie Palm |
| 255 |Nieznane |Nieznany typ urządzenia |

## <a name="enrollmentactivities"></a>enrollmentActivities 
Jednostka **enrollmentActivity** wskazuje działanie rejestracji urządzenia.

| Właściwość                      | Opis                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Klucz daty zarejestrowania tego działania rejestracji.               |
| deviceEnrollmentTypeKey       | Klucz typu rejestracji.                                        |
| deviceTypeKey                 | Klucz typu urządzenia.                                                |
| enrollmentEventStatusKey      | Klucz stanu wskazujący powodzenie lub niepowodzenie rejestracji.    |
| enrollmentFailureCategoryKey  | Klucz kategorii niepowodzenia rejestracji (jeśli rejestracja nie powiodła się).        |
| enrollmentFailureReasonKey    | Klucz przyczyny niepowodzenia rejestracji (jeśli rejestracja nie powiodła się).          |
| osVersion                     | Wersja systemu operacyjnego urządzenia.                               |
| count                         | Łączna liczba działań rejestracji zgodnych z powyższymi klasyfikacjami.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
Jednostka **enrollmentEventStatus** wskazuje wynik rejestracji urządzenia.

| Właściwość                   | Opis                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| enrollmentEventStatusKey   | Unikatowy identyfikator stanu rejestracji w magazynie danych (klucz zastępczy)  |
| enrollmentEventStatusName  | Nazwa stanu rejestracji. Zobacz poniższe przykłady.                            |

### <a name="example"></a>Przykład

| enrollmentEventStatusName  | Opis                            |
|----------------------------|----------------------------------------|
| Powodzenie                    | Rejestracja urządzenia zakończona powodzeniem         |
| Niepowodzenie                     | Rejestracja urządzenia zakończona niepowodzeniem             |
| Niedostępny              | Niedostępny stan rejestracji.  |

## <a name="enrollmentfailurecategories"></a>enrollmentFailureCategories 
Jednostka **EnrollmentFailureCategory** wskazuje, dlaczego rejestracja urządzenia się nie powiodła. 

| Właściwość                       | Opis                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| enrollmentFailureCategoryKey   | Unikatowy identyfikator kategorii niepowodzenia rejestracji w magazynie danych (klucz zastępczy)  |
| enrollmentFailureCategoryName  | Nazwa kategorii niepowodzenia rejestracji. Zobacz poniższe przykłady.                            |

### <a name="example"></a>Przykład

| enrollmentFailureCategoryName   | Opis                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Nie dotyczy                  | Kategoria niepowodzenia rejestracji nie ma zastosowania.                                                            |
| Niedostępny                   | Kategoria niepowodzenia rejestracji nie jest dostępna.                                                             |
| Nieznane                         | Nieznany błąd.                                                                                                |
| Uwierzytelnianie                  | Nie można przeprowadzić uwierzytelniania.                                                                                        |
| Autoryzacja                   | Wywołanie zostało uwierzytelnione, ale nie zostało autoryzowane do rejestracji.                                                         |
| AccountValidation               | Nie można zweryfikować konta na potrzeby rejestracji. (Konto zablokowane, rejestracja nie jest włączona)                      |
| UserValidation                  | Nie można zweryfikować użytkownika. (Użytkownik nie istnieje, brak licencji)                                           |
| DeviceNotSupported              | Urządzenie nie jest obsługiwane w zakresie zarządzania urządzeniami przenośnymi.                                                         |
| InMaintenance                   | Konto jest poddawane konserwacji.                                                                                    |
| BadRequest                      | Klient wysłał żądanie, którego usługa nie rozumie lub nie obsługuje.                                        |
| FeatureNotSupported             | Funkcje używane przez tę rejestrację nie są obsługiwane dla tego konta.                                        |
| EnrollmentRestrictionsEnforced  | Ograniczenia rejestracji skonfigurowane przez administratora spowodowały zablokowanie rejestracji.                                          |
| ClientDisconnected              | Upłynął limit czasu dla klienta lub rejestracja została przerwana przez użytkownika końcowego.                                                        |
| UserAbandonment                 | Rejestracja została porzucona przez użytkownika końcowego. (Użytkownik końcowy rozpoczął dołączanie, ale nie ukończył go w odpowiednim czasie)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
Jednostka **EnrollmentFailureReason** wskazuje bardziej szczegółową przyczynę niepowodzenia rejestracji urządzenia w ramach kategorii niepowodzenia.  

| Właściwość                     | Opis                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| enrollmentFailureReasonKey   | Unikatowy identyfikator przyczyny niepowodzenia rejestracji w magazynie danych (klucz zastępczy)  |
| enrollmentFailureReasonName  | Nazwa przyczyny niepowodzenia rejestracji. Zobacz poniższe przykłady.                            |

### <a name="example"></a>Przykład

| enrollmentFailureReasonName      | Opis                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nie dotyczy                   | Przyczyna niepowodzenia rejestracji nie ma zastosowania.                                                                                                                                                       |
| Niedostępny                    | Przyczyna niepowodzenia rejestracji nie jest dostępna.                                                                                                                                                        |
| Nieznane                          | Nieznany błąd.                                                                                                                                                                                         |
| UserNotLicensed                  | Użytkownik nie został odnaleziony w usłudze Intune lub nie ma ważnej licencji.                                                                                                                                     |
| UserUnknown                      | Użytkownik nie jest znany usłudze Intune.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Tylko jeden użytkownik może zarejestrować urządzenie. To urządzenie zostało już wcześniej zarejestrowane przez innego użytkownika.                                                                                                                |
| EnrollmentOnboardingIssue        | Urząd zarządzania urządzeniami przenośnymi (MDM, mobile device management) usługi Intune nie został jeszcze skonfigurowany.                                                                                                                                 |
| AppleChallengeIssue              | Instalacja profilu zarządzania systemu iOS została opóźniona lub zakończyła się niepowodzeniem.                                                                                                                                         |
| AppleOnboardingIssue             | Do rejestracji w usłudze Intune wymagany jest certyfikat wypychania MDM firmy Apple.                                                                                                                                       |
| DeviceCap                        | Użytkownik próbował zarejestrować więcej urządzeń, niż jest to dozwolone.                                                                                                                                        |
| AuthenticationRequirementNotMet  | Autoryzacja tego żądania nie powiodła się w usłudze rejestracji usługi Intune.                                                                                                                                            |
| UnsupportedDeviceType            | To urządzenie nie spełnia minimalnych wymagań dotyczących rejestracji w usłudze Intune.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Rejestracja tego urządzenia nie powiodła się ze względu na skonfigurowaną regułę ograniczeń rejestracji.                                                                                                                          |
| BulkDeviceNotPreregistered       | Nie odnaleziono numeru IMEI (International Mobile Equipment Identity) lub numeru seryjnego urządzenia.  Bez tego identyfikatora urządzenia są rozpoznawane jako urządzenia osobiste, które są obecnie zablokowane.  |
| FeatureNotSupported              | Użytkownik próbował uzyskać dostęp do funkcji, która nie została jeszcze udostępniona wszystkim klientom lub nie jest zgodna z konfiguracją usługi Intune.                                                            |
| UserAbandonment                  | Rejestracja została porzucona przez użytkownika końcowego. (Użytkownik końcowy rozpoczął dołączanie, ale nie ukończył go w odpowiednim czasie)                                                                                           |
| APNSCertificateExpired           | Nie można zarządzać urządzeniami firmy Apple, jeśli certyfikat wypychania MDM firmy Apple wygasł.                                                                                                                            |
## <a name="ownertypes"></a>ownerTypes

Jednostka **enrollmentType** wskazuje, czy urządzenie jest firmowe, osobiste czy nieznane.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| ownerTypeID |Unikatowy identyfikator typu właściciela. | |
| ownerTypeKey |Unikatowy identyfikator typu właściciela w magazynie danych — klucz zastępczy. | |
| ownerTypeName |Reprezentuje typ właściciela urządzeń:  <br>Corporate — urządzenie jest własnością przedsiębiorstwa. <br>Personal — urządzenie jest własnością osobistą (BYOD).  <br>Unknown — brak informacji o tym urządzeniu. |Corporate Personal Unknown |

> [!Note]  
> Na potrzeby właściwości `ownerTypeName` w usłudze Azure AD należy podczas tworzenia grup dynamicznych dla urządzeń ustawić wartość filtru `deviceOwnership` na `Company`. Aby uzyskać więcej informacji, zobacz [Reguły urządzeń](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>managementStates

Jednostka **managementStates** zawiera szczegółowe informacje dotyczące stanu urządzenia. Szczegóły mogą być przydatne w przypadkach, gdy są stosowane akcje zdalne, a urządzenie ma zdjęte zabezpieczenia lub odblokowany dostęp do konta root.

| Właściwość  | Opis |
|---------|------------|
| managementStateID | Unikatowy identyfikator stanu zarządzania. |
| managementStateKey | Unikatowy identyfikator stanu zarządzania w magazynie danych — klucz zastępczy. |
| managementStateName | Wskazuje stan zdalnej akcji zastosowanej do tego urządzenia. |

### <a name="example"></a>Przykład

| managementStateID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Zarządzani | Zarządzane bez żadnych oczekujących akcji zdalnych. |
| 1 |RetirePending | Dla tego urządzenia istnieje oczekujące polecenie wycofania. |
| 2 |RetireFailed | Polecenie wycofania nie powiodło się na tym urządzeniu. |
| 3 |WipePending | Dla tego urządzenia istnieje oczekujące polecenie wyczyszczenia. |
| 4 |WipeFailed | Polecenie wyczyszczenia nie powiodło się na tym urządzeniu. |
| 5 |Nieprawidłowy | Stan złej kondycji. |
| 6 |DeletePending | Dla tego urządzenia istnieje oczekujące polecenie usunięcia. |
| 7 |RetireIssued | Wydano polecenie wycofania tego urządzenia. |
| 8 |WipeIssued | Wydano polecenie wyczyszczenia. |
| 9 |WipeCanceled | Anulowano polecenie wyczyszczenia. |
| 10 |RetireCanceled | Anulowano polecenie wycofania. |
| 11 |Discovered | Urządzenie jest nowo odnalezione przez usługę Intune, przy czym po zameldowaniu po raz pierwszy następuje przeniesienie do stanu -Zarządzane-. |

## <a name="managementagenttypes"></a>managementAgentTypes

Jednostka **managementAgentType** reprezentuje agentów używanych do zarządzania urządzeniem.

| Właściwość  | Opis |
|---------|------------|
| managementAgentTypeID | Unikatowy identyfikator typu agenta zarządzania. |
| managementAgentTypeKey | Unikatowy identyfikator typu agenta zarządzania w magazynie danych — klucz zastępczy. |
| managementAgentTypeName |Wskazuje, jaki rodzaj agenta służy do zarządzania urządzeniem. |

### <a name="example"></a>Przykład

| ManagementAgentTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 1 |EAS | Urządzenie jest zarządzane przy użyciu programu Exchange Active Sync |
| 2 |MDM | Urządzenie jest zarządzane przy użyciu agenta MDM |
| 3 |EasMdm | Urządzenie jest zarządzane zarówno przez program Exchange Active Sync, jak i agenta MDM |
| 4 |IntuneClient | Urządzenie jest zarządzane przez agenta PC usługi Intune |
| 5 |EasIntuneClient | Urządzenie jest zarządzane zarówno przez program Exchange Active Sync, jak i agenta PC usługi Intune |
| 8 |ConfigManagerClient | Urządzenie jest zarządzane przez agenta programu Configuration Manager |
| 16 |Nieznane | Nieznany typ agenta zarządzania |

## <a name="devices"></a>devices

Jednostka **devices** zawiera listę wszystkich zarejestrowanych urządzeń w obszarze zarządzania oraz odpowiadające im właściwości.

|          Właściwość          |                                                                                       Opis                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| deviceKey                  | Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy.                                                                                                               |
| deviceId                   | Unikatowy identyfikator urządzenia.                                                                                                                                                     |
| deviceName                 | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune tworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| deviceTypeKey              | Klucz atrybutu typu urządzenia dla tego urządzenia.                                                                                                                                    |
| deviceRegistrationState    | Klucz atrybutu stanu rejestracji klienta dla tego urządzenia.                                                                                                                      |
| ownerTypeKey               | Klucz atrybutu typu właściciela dla tego urządzenia: corporate (firmowy), personal (osobisty) lub unknown (nieznany).                                                                                                    |
| enrolledDateTime           | Data i godzina rejestracji urządzenia.                                                                                                                                         |
| lastSyncDateTime           | Ostatnie znane zaewidencjonowanie urządzenia w usłudze Intune.                                                                                                                                              |
| managementAgentKey         | Klucz agenta zarządzania skojarzony z tym urządzeniem.                                                                                                                             |
| managementStateKey         | Klucz stanu zarządzania skojarzony z tym urządzeniem, wskazujący najnowszy stan zdalnej akcji lub to, czy zostały złamane ograniczenia albo odblokowany dostęp do konta root.                                                |
| azureADDeviceId            | Identyfikator deviceID na platformie Azure dla tego urządzenia.                                                                                                                                                  |
| azureADRegistered          | Wskazuje, czy urządzenie zostało zarejestrowane w usłudze Azure Active Directory.                                                                                                                             |
| deviceCategoryKey          | Klucz kategorii skojarzony z tym urządzeniem.                                                                                                                                     |
| deviceEnrollmentType       | Klucz typu rejestracji skojarzony z tym urządzeniem wskazujący metodę rejestracji.                                                                                             |
| complianceStateKey         | Klucz stanu zgodności skojarzony z tym urządzeniem.                                                                                                                             |
| osVersion                  | Wersja systemu operacyjnego urządzenia.                                                                                                                                                |
| easDeviceId                | Identyfikator programu Exchange ActiveSync urządzenia.                                                                                                                                                  |
| serialNumber               | SerialNumber                                                                                                                                                                           |
| userId                     | Unikatowy identyfikator użytkownika skojarzony z urządzeniem.                                                                                                                           |
| rowLastModifiedDateTimeUTC | Data i godzina ostatniej modyfikacji tego użytkownika w magazynie danych (czas UTC).                                                                                                       |
| manufacturer               | Producent urządzenia                                                                                                                                                             |
| model                      | Model urządzenia                                                                                                                                                                    |
| operatingSystem            | System operacyjny urządzenia. Windows, iOS itp.                                                                                                                                   |
| isDeleted                  | Plik binarny pokazujący, czy urządzenie zostało usunięte.                                                                                                                                 |
| androidSecurityPatchLevel  | Poziom poprawki zabezpieczeń systemu Android                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Stan urządzenia w trybie nadzorowanym                                                                                                                                                               |
| freeStorageSpaceInBytes    | Ilość wolnego miejsca w bajtach.                                                                                                                                                                 |
| totalStorageSpaceInBytes   | Całkowita ilość miejsca w bajtach.                                                                                                                                                                |
| encryptionState            | Stan szyfrowania urządzenia.                                                                                                                                                      |
| subscriberCarrier          | Operator subskrybenta urządzenia                                                                                                                                                       |
| phoneNumber                | Numer telefonu urządzenia                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| cellularTechnology         | Technologia sieci komórkowej urządzenia                                                                                                                                                    |
| WiFiMacAddress             | Wi-Fi MAC                                                                                                                                                                              |
| ICCD                       | Identyfikator karty zintegrowanego obwodu                                                                                                                                                     |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

Jednostka **devicePropertyHistory** ma takie same właściwości, jak tabela urządzeń i codzienne migawki każdego rekordu urządzenia w ciągu ostatnich 90 dni. Kolumna DateKey wskazuje dzień dla każdego wiersza.

|          Właściwość          |                                                                                      Opis                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| dateKey                    | Odwołanie do tabeli dat wskazujące dzień.                                                                                                                                          |
| deviceKey                  | Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy. To jest odwołanie do tabeli urządzenia, która zawiera identyfikator urządzenia usługi Intune.                               |
| deviceName                 | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| deviceRegistrationStateKey | Klucz atrybutu stanu rejestracji urządzenia dla tego urządzenia.                                                                                                                    |
| ownerTypeKey               | Klucz atrybutu typu właściciela dla tego urządzenia: corporate (firmowy), personal (osobisty) lub unknown (nieznany).                                                                                                  |
| managementStateKey         | Klucz stanu zarządzania skojarzony z tym urządzeniem, wskazujący najnowszy stan zdalnej akcji lub to, czy zostały złamane ograniczenia albo odblokowany dostęp do konta root.                                                |
| azureADRegistered          | Wskazuje, czy urządzenie zostało zarejestrowane w usłudze Azure Active Directory.                                                                                                                             |
| complianceStateKey         | Klucz właściwości ComplianceState.                                                                                                                                                            |
| OSVersion                  | Wersja systemu operacyjnego.                                                                                                                                                                          |
| jailBroken                 | Wskazuje, czy urządzenie ma złamane zabezpieczenia lub odblokowany dostęp do konta root.                                                                                                                                         |
| deviceCategoryKey          | Klucz atrybutu kategorii urządzenia dla tego urządzenia. 

