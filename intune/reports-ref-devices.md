---
title: Urządzenia — magazyn danych usługi Intune
titleSuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Urządzenia w kolekcji jednostki w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c361c6054cf52c802155587084eaea76e024f78c
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59429186"
---
# <a name="reference-for-devices-entities"></a>Odwołanie do jednostek urządzeń

Kategoria **Urządzenia** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje takie jak:

  -  Typ urządzenia
  -  Rejestrowanie urządzenia i stan rejestracji
  -  Własność urządzeń
  -  Stan zarządzania urządzeniem
  -  Przynależność urządzenia do stanu usługi Azure AD
  -  Stan rejestracji
  -  Historyczne informacje o urządzeniu
  -  Spis aplikacji na urządzeniu

## <a name="devicetypes"></a>DeviceTypes

Jednostka **DeviceTypes** reprezentuje typ urządzenia przywoływany przez inne jednostki magazynu danych. Typ urządzenia zwykle opisuje model urządzenia, producenta lub kombinację obu tych informacji.

| Właściwość  | Opis |
|---------|------------|
| DeviceTypeID |Unikatowy identyfikator typu urządzenia |
| DeviceTypeKey |Unikatowy identyfikator typu urządzenia w magazynie danych — klucz zastępczy |
| DeviceTypeName |Typ urządzenia |

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
| 15 |HoloLens |Urządzenia HoloLens |
| 16 |SurfaceHub |Urządzenie Surface Hub |
| 17 |AndroidForWork |Urządzenie z systemem Android zarządzane przy pomocy właściciela profilu systemu Android |
| 100 |Blackberry |Urządzenie Blackberry |
| 101 |Palm |Urządzenie Palm |
| 255 |Nieznane |Nieznany typ urządzenia |

## <a name="enrollmentactivities"></a>enrollmentActivities 
Jednostka **EnrollmentActivity** wskazuje działanie rejestracji urządzenia.

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
Jednostka **EnrollmentEventStatus** wskazuje wynik rejestracji urządzenia.

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
| Uwierzytelnianie                  | Uwierzytelnianie nie powiodło się.                                                                                        |
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
## <a name="ownertypes"></a>OwnerTypes

Jednostka **EnrollmentTypes** wskazuje, czy urządzenie jest firmowe, osobiste czy nieznane.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| ownerTypeID |Unikatowy identyfikator typu właściciela. | |
| ownerTypeKey |Unikatowy identyfikator typu właściciela w magazynie danych — klucz zastępczy. | |
| ownerTypeName |Reprezentuje typ właściciela urządzeń:  <br>Firmowe — urządzenie jest własnością przedsiębiorstwa. <br>Personal — urządzenie jest własnością osobistą (BYOD).  <br>Unknown — brak informacji o tym urządzeniu. |Nieznany osobistych firmowych |

> [!Note]  
> Aby uzyskać `ownerTypeName` w usługi Azure AD podczas tworzenia grup dynamicznych w przypadku urządzeń, należy ustawić wartość filtru `deviceOwnership` jako `Company`. Aby uzyskać więcej informacji, zobacz [reguły dla urządzeń](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>ManagementStates

Jednostka **ManagementStates** zawiera szczegółowe informacje dotyczące stanu urządzenia. Szczegóły mogą być przydatne w przypadkach, gdy są stosowane akcje zdalne, a urządzenie ma zdjęte zabezpieczenia lub odblokowany dostęp do konta root.

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

## <a name="managementagenttypes"></a>ManagementAgentTypes

Jednostka **ManagementAgentTypes** reprezentuje agentów używanych do zarządzania urządzeniem.

| Właściwość  | Opis |
|---------|------------|
| ManagementAgentTypeID | Unikatowy identyfikator typu agenta zarządzania. |
| ManagementAgentTypeKey | Unikatowy identyfikator typu agenta zarządzania w magazynie danych — klucz zastępczy. |
| ManagementAgentTypeName |Wskazuje, jaki rodzaj agenta służy do zarządzania urządzeniem. |

### <a name="example"></a>Przykład

| ManagementAgentTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 1 |EAS | Urządzenie jest zarządzane przy użyciu programu Exchange Active Sync |
| 2 |MDM | Urządzenie jest zarządzane przy użyciu agenta MDM |
| 3 |EasMdm | Urządzenie jest zarządzane zarówno przez program Exchange Active Sync, jak i agenta MDM |
| 4 |IntuneClient | Urządzenie jest zarządzane przez agenta PC usługi Intune |
| 5 |EasIntuneClient | Urządzenie jest zarządzane zarówno przez program Exchange Active Sync, jak i agenta PC usługi Intune |
| 8 |ConfigManagerClient | Urządzenie jest zarządzane przez agenta programu System Center Configuration Manager |
| 16 |Nieznane | Nieznany typ agenta zarządzania |

## <a name="devices"></a>Devices

Jednostka **Devices** zawiera listę wszystkich zarejestrowanych urządzeń w obszarze zarządzania oraz odpowiadające im właściwości.

|          Właściwość          |                                                                                       Opis                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy.                                                                                                               |
| DeviceId                   | Unikatowy identyfikator urządzenia.                                                                                                                                                     |
| DeviceName                 | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune tworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| DeviceTypeKey              | Klucz atrybutu typu urządzenia dla tego urządzenia.                                                                                                                                    |
| DeviceRegistrationState    | Klucz atrybutu stanu rejestracji klienta dla tego urządzenia.                                                                                                                      |
| OwnerTypeKey               | Klucz atrybutu typu właściciela dla tego urządzenia: corporate (firmowy), personal (osobisty) lub unknown (nieznany).                                                                                                    |
| EnrolledDateTime           | Data i godzina rejestracji urządzenia.                                                                                                                                         |
| LastSyncDateTime           | Ostatnie znane zaewidencjonowanie urządzenia w usłudze Intune.                                                                                                                                              |
| ManagementAgentKey         | Klucz agenta zarządzania skojarzony z tym urządzeniem.                                                                                                                             |
| ManagementStateKey         | Klucz stanu zarządzania skojarzony z tym urządzeniem, wskazujący najnowszy stan zdalnej akcji lub to, czy zostały złamane ograniczenia albo odblokowany dostęp do konta root.                                                |
| AzureADDeviceId            | Identyfikator deviceID na platformie Azure dla tego urządzenia.                                                                                                                                                  |
| AzureADRegistered          | Wskazuje, czy urządzenie zostało zarejestrowane w usłudze Azure Active Directory.                                                                                                                             |
| DeviceCategoryKey          | Klucz kategorii skojarzony z tym urządzeniem.                                                                                                                                     |
| DeviceEnrollmentType       | Klucz typu rejestracji skojarzony z tym urządzeniem wskazujący metodę rejestracji.                                                                                             |
| ComplianceStateKey         | Klucz stanu zgodności skojarzony z tym urządzeniem.                                                                                                                             |
| OSVersion                  | Wersja systemu operacyjnego urządzenia.                                                                                                                                                |
| EasDeviceId                | Identyfikator programu Exchange ActiveSync urządzenia.                                                                                                                                                  |
| SerialNumber               | SerialNumber                                                                                                                                                                           |
| UserId                     | Unikatowy identyfikator użytkownika skojarzony z urządzeniem.                                                                                                                           |
| RowLastModifiedDateTimeUTC | Data i godzina ostatniej modyfikacji tego użytkownika w magazynie danych (czas UTC).                                                                                                       |
| Producent               | Producent urządzenia                                                                                                                                                             |
| Model                      | Model urządzenia                                                                                                                                                                    |
| OperatingSystem            | System operacyjny urządzenia. Windows, iOS itp.                                                                                                                                   |
| IsDeleted                  | Plik binarny pokazujący, czy urządzenie zostało usunięte.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Poziom poprawki zabezpieczeń systemu Android                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Stan urządzenia w trybie nadzorowanym                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Ilość wolnego miejsca w bajtach.                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Całkowita ilość miejsca w bajtach.                                                                                                                                                                |
| EncryptionState            | Stan szyfrowania urządzenia.                                                                                                                                                      |
| SubscriberCarrier          | Operator subskrybenta urządzenia                                                                                                                                                       |
| PhoneNumber                | Numer telefonu urządzenia                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| CellularTechnology         | Technologia sieci komórkowej urządzenia                                                                                                                                                    |
| WiFiMacAddress             | Wi-Fi MAC                                                                                                                                                                              |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

Jednostka **DevicePropertyHistory** ma takie same właściwości, jak tabela urządzeń i codzienne migawki każdego rekordu urządzenia dziennie w ciągu ostatnich 90 dni. Kolumna DateKey wskazuje dzień dla każdego wiersza.

|          Właściwość          |                                                                                      Opis                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | Odwołanie do tabeli dat wskazujące dzień.                                                                                                                                          |
| DeviceKey                  | Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy. To jest odwołanie do tabeli urządzenia, która zawiera identyfikator urządzenia usługi Intune.                               |
| DeviceName                 | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| DeviceRegistrationStateKey | Klucz atrybutu stanu rejestracji urządzenia dla tego urządzenia.                                                                                                                    |
| OwnerTypeKey               | Klucz atrybutu typu właściciela dla tego urządzenia: corporate (firmowy), personal (osobisty) lub unknown (nieznany).                                                                                                  |
| ManagementStateKey         | Klucz stanu zarządzania skojarzony z tym urządzeniem, wskazujący najnowszy stan zdalnej akcji lub to, czy zostały złamane ograniczenia albo odblokowany dostęp do konta root.                                                |
| AzureADRegistered          | Wskazuje, czy urządzenie zostało zarejestrowane w usłudze Azure Active Directory.                                                                                                                             |
| ComplianceStateKey         | Klucz właściwości ComplianceState.                                                                                                                                                            |
| OSVersion                  | Wersja systemu operacyjnego.                                                                                                                                                                          |
| JailBroken                 | Wskazuje, czy urządzenie ma złamane zabezpieczenia lub odblokowany dostęp do konta root.                                                                                                                                         |
| DeviceCategoryKey          | Klucz atrybutu kategorii urządzenia dla tego urządzenia. 

## <a name="applicationinventory"></a>ApplicationInventory

Jednostka **ApplicationInventory** tworzy listę aplikacji znalezionych na urządzeniu w czasie zbierania spisu.


|      Właściwość      |                       Opis                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Odwołanie do tabeli urządzeń.               |
|   ApplicationKey   | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |

