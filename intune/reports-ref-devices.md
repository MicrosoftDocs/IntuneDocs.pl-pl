---
title: Urządzenia — magazyn danych usługi Intune
titlesuffix: Microsoft Intune
description: Temat referencyjny dotyczący kategorii Urządzenia w kolekcji jednostki w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
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
ms.openlocfilehash: fe16111095051c1fddb4b87d5b4f815ae2798e92
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566373"
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
| 15 |HoloLens |Urządzenie Holo Lens |
| 16 |SurfaceHub |Urządzenie Surface Hub |
| 17 |AndroidForWork |Urządzenie z systemem Android zarządzane przy pomocy właściciela profilu systemu Android |
| 100 |Blackberry |Urządzenie Blackberry |
| 101 |Palm |Urządzenie Palm |
| 255 |Nieznane |Nieznany typ urządzenia |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

Jednostka **ClientRegistrationStateTypes** reprezentuje typ rejestracji przywoływany przez inne tabele magazynu danych.

| Właściwość  | Opis |
|---------|------------|
| clientRegisterationStateID |Unikatowy identyfikator stanu rejestracji |
| clientRegisterationStateKey |Unikatowy identyfikator stanu rejestracji w magazynie danych — klucz zastępczy |
| clientRegisterationStateName |Stan rejestracji |

### <a name="example"></a>Przykład

| ClientRegisterationStateID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |NotRegistered |Niezarejestrowany |
| 1 |SMSIDConflict |Konflikt identyfikatora SMS |
| 2 |Zarejestrowany |Zarejestrowany |
| 3 |Revoked |Stan oznacza, że administrator IT zablokował klienta i klienta można odblokować. Urządzenie może również być w stanie odwołania po jego wyczyszczeniu lub wycofaniu. |
| 4 |KeyConflict |Konflikt klucza |
| 5 |ApprovalPending |Oczekiwanie na zatwierdzenie |
| 6 |ResetCert |Resetowanie certyfikatu |
| 7 |NotRegisteredPendingEnrollment |Niezarejestrowane oczekujące na rejestrację |
| 8 |Nieznane |Nieznany stan |

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
| UserAbandonment                 | Rejestracja została porzucona przez użytkownika końcowego. (Użytkownik końcowy rozpoczął dołączanie, ale go nie ukończył w odpowiednim czasie)  |

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
| UserAbandonment                  | Rejestracja została porzucona przez użytkownika końcowego. (Użytkownik końcowy rozpoczął dołączanie, ale go nie ukończył w odpowiednim czasie)                                                                                           |
| APNSCertificateExpired           | Nie można zarządzać urządzeniami firmy Apple, jeśli certyfikat wypychania MDM firmy Apple wygasł.                                                                                                                            |

## <a name="enrollmenttypes"></a>EnrollmentTypes

Jednostka **EnrollmentTypes** wskazuje, jak urządzenie zostało zarejestrowane. Typ rejestracji przechwytuje metodę rejestracji. Przykłady listy różnych typów rejestracji i ich znaczenie.

| Właściwość  | Opis |
|---------|------------|
| managementStateID |Unikatowy identyfikator stanu zarządzania. |
| managementStateKey |Unikatowy identyfikator stanu zarządzania w magazynie danych — klucz zastępczy. |
| managementStateName |Wskazuje stan zdalnej akcji zastosowanej do tego urządzenia. |

### <a name="example"></a>Przykład

| enrollmentTypeID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Nieznane |Typ rejestracji nie został zebrany |
| 1 |UserEnrollment |Rejestracja zainicjowana przez użytkownika |
| 2 |DeviceEnrollment |Rejestracja urządzenia z profilem bez użytkowników |
| 3 |DeviceEnrollmentWithUDA |Rejestracja urządzenia z profilem UDA. |
| 4 |AzureDomainJoined |Użytkownik zainicjował rejestrację urządzenia za pomocą usługi Azure Active Directory |
| 5 |UserEnrollmentWithServiceAccount |Użytkownik zainicjował rejestrację za pomocą konta usługi |
| 6 |DepDeviceEnrollment |Rejestracja urządzenia DEP z profilem bez użytkowników |
| 7 |DepDeviceEnrollmentWithUDA |Rejestracja urządzenia DEP z profilem UDA |
| 8 |AutoEnrollment |Łączna rejestracja DRS i MDM dla scenariusza BYOD |

## <a name="ownertypes"></a>OwnerTypes

Jednostka **EnrollmentTypes** wskazuje, czy urządzenie jest firmowe, osobiste czy nieznane.

| Właściwość  | Opis | Przykład |
|---------|------------|--------|
| ownerTypeID |Unikatowy identyfikator typu właściciela. | |
| ownerTypeKey |Unikatowy identyfikator typu właściciela w magazynie danych — klucz zastępczy. | |
| ownerTypeName |Reprezentuje typ właściciela urządzeń:  <br>Firmowe — urządzenie jest własnością przedsiębiorstwa. <br>Personal — urządzenie jest własnością osobistą (BYOD).  <br>Unknown — brak informacji o tym urządzeniu. |Nieznany osobistych firmowych |

> [!Note]  
> Aby uzyskać `ownerTypeName` w usługi Azure AD podczas tworzenia grup dynamicznych w przypadku urządzeń, należy ustawić wartość filtru `deviceOwnership` jako `Company`. Aby uzyskać więcej informacji, zobacz [reguły dla urządzeń](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="mdmstatuses"></a>MdmStatuses

Jednostka **MdmStatuses** wskazuje stan zgodności urządzenia.

| Właściwość  | Opis |
|---------|------------|
| MdmStatusID |Unikatowy identyfikator stanu zgodności |
| MdmStatusKey |Unikatowy identyfikator stanu zgodności w magazynie danych — klucz zastępczy | 
| ComplianceStatus |Stan zgodności urządzenia, powinien mieć jedną z wartości z poniższej tabeli | 


### <a name="example"></a>Przykład

| MdmStatusID  | ComplianceStatus | Opis |
|---------|------------|--------|
| 0 |Nieznane |Stan zgodności urządzenia jest nieznany. |
| 1 |Zgodny |Urządzenie jest zgodne. |
| 2 |Niezgodny |Urządzenie nie jest zgodne. |
| 3 |Konflikt |Zgodność urządzenia spowodowała konflikt. |
| 4 |Error |Wystąpił błąd podczas odczytywania stanu zgodności urządzenia. |


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

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

Jednostka **WorkPlaceJoinStateTypes** reprezentuje stan dołączania urządzenia dla miejsca pracy usługi Azure Active Directory.  Przepływ pracy rejestracji może użyć co najmniej jednego certyfikatu do weryfikacji lub uwierzytelnienia. Gdy rejestruje się urządzenie w miejscu pracy, te certyfikaty są używane do weryfikowania urządzenia i użytkownika. Wystawianie certyfikatów następuje za pośrednictwem serwera prostego protokołu rejestrowania certyfikatów (SCEP). Wartości w jednostce wskazują różne stany, w których może być urządzenie w miarę przechodzenia przez ten proces. Niektóre z tych stanów obejmują niepowodzenie dołączenia do miejsca pracy z powodu niepowodzenia wystawiania wymaganego certyfikatu (z serwera SCEP). Jeśli urządzenie nigdy nie przeszło przez ten przepływ pracy, wartość jest ustawiana na Unknown (Nieznany).

| Właściwość  | Opis |
|---------|------------|
| WorkPlaceJoinStateID | Unikatowy identyfikator stanu dołączania do miejsca pracy |
| WorkPlaceJoinStateKey | Unikatowy identyfikator stanu dołączenia do miejsca pracy w magazynie danych — klucz zastępczy |
| WorkPlaceJoinStateName | Stan dołączenia do miejsca pracy |

### <a name="example"></a>Przykład

| workPlaceJoinStateID  | Nazwa | Opis |
|---------|------------|--------|
| 0 |Nieznane |Jeśli urządzenie nie jest dołączone do miejsca pracy, jest w stanie Unknown (Nieznany) |
| 1 |Sukces |Pomyślnie dołączono do miejsca pracy |
| 2 |FailureToGetScepMetadata |Niepowodzenie pobrania metadanych protokołu SCEP |
| 3 |FailureToGetScepChallenge |Niepowodzenie pobrania żądania protokołu SCEP |
| 4 |DeviceFailureToInstallScepCommand |Niepowodzenie instalacji polecenia SCEP na urządzeniu |
| 5 |DeviceFailureToGetCertificate |Niepowodzenie pobierania certyfikatu za pośrednictwem protokołu SCEP przez urządzenie |
| 6 |DeviceScepPending |Stan oczekiwania; urządzenie nadal realizuje protokół SCEP |
| 7 |DeviceScepFailed |Niepowodzenie instalacji certyfikatu za pośrednictwem protokołu SCEP na urządzeniu |
| 8 |AADValidationFailed |Nie można zweryfikować istnienia urządzenia w usłudze AAD |

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

| Właściwość  | Opis |
|---------|------------|
| DeviceKey | Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy. |
| DeviceId | Unikatowy identyfikator urządzenia. |
| DeviceName | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| DeviceTypeKey | Klucz atrybutu typu urządzenia dla tego urządzenia. |
| ClientRegisterationStateKey | Klucz atrybutu stanu rejestracji klienta dla tego urządzenia. |
| OwnerTypeKey | Klucz atrybutu typu właściciela dla tego urządzenia: corporate (firmowy), personal (osobisty) lub unknown (nieznany). |
| objectSourceKey | Zignoruj tę kolumnę. |
| CreatedDate | Data rejestracji urządzenia. |
| LastContact | Ostatnie znane zameldowanie urządzenia w usłudze Intune. |
| LastContactNotification | Czas ostatniego powiadomienia urządzenia przez usługę Intune o zameldowaniu w usłudze Intune. |
| LastContactWorkplaceJoin | Sygnatura czasowa wskazująca ostatni znany stan dołączenia do miejsca pracy dla tego urządzenia. |
| ManagementAgentKey | Klucz agenta zarządzania skojarzony z tym urządzeniem. |
| ManagementStateKey | Klucz stanu zarządzania skojarzony z tym urządzeniem, wskazujący najnowszy stan zdalnej akcji lub to, czy były złamane ograniczenia lub odblokowany dostęp do konta root. |
| Identyfikator odwołania | Identyfikator urządzenia w usłudze Azure Active Directory. |
| WorkPlaceJoinStateKey | Klucz stanu dołączania do miejsca pracy skojarzony z tym urządzeniem. |
| CategoryId | Zignoruj tę kolumnę. |
| EnrollmentTypeKey | Klucz typu rejestracji skojarzony z tym urządzeniem wskazujący metodę rejestracji. |
| CertExpirationDate | Data wygaśnięcia certyfikatu zarządzania MDM. |
| MdmStatusKey | Klucz dla wartości MdmStatus. |
| OSFamily | Rodzina systemów operacyjnych (Windows, iOS, Android itd.) |
| OSVersion | Wersja systemu operacyjnego |
| OSMajorVersion | Składnik wersji głównej wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| OSMinorVersion | Składnik wersji pomocniczej wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| OSBuildNumber | Składnik wersji kompilacji wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| OSRevisionNumber | Składnik wersji poprawki wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| EasID | Identyfikator EAS tych urządzeń, jeśli urządzenie jest zarządzane przez program Exchange Active Sync. |
| GraphDeviceIsManaged | Ostatni stan zarządzania ustawiony przez usługę Intune w usłudze Azure AD. |
| GraphDeviceIsCompliant | Ostatni stan zgodności ustawiony przez usługę Intune w usłudze Azure AD. |
| SerialNumber | Numer seryjny urządzenia, o ile jest dostępny. |
| EnrolledByUser | Identyfikator użytkownika, który zarejestrował to urządzenie. Odwołuje się do kolumny userId w tabeli użytkownika. |
| RowLastModifiedDateTimeUTC | Czas ostatniej modyfikacji tego rekordu. |
| ProcessorArchitecture | Architektura procesora. |
| DeviceAction | Ostatnia zlecona akcja urządzenia, na razie zignorować. |
| Producent | Producent urządzenia. |
| Model | Model urządzenia. |
| LastPolicyUpdateUtc | Ostatni raz, gdy zaktualizowano zasady na urządzeniu. |
| LastExchangeStatusUtc | Ostatni raz, gdy urządzenie było synchronizowane z programem Exchange. |
| IsDeleted | Ustawione na wartość True, jeśli urządzenie nie jest już zarządzane przez usługę Intune. Zachowuje ostatni znany stan. |
| AndroidSecurityPatchLevel |Data ostatniej poprawki zabezpieczeń urządzenia. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

Jednostka **DevicePropertyHistory** ma takie same właściwości, jak tabela urządzeń i codzienne migawki każdego rekordu urządzenia dziennie w ciągu ostatnich 90 dni. Kolumna DateKey wskazuje dzień dla każdego wiersza.

| Właściwość  | Opis |
|---------|------------|
| DateKey |Odwołanie do tabeli dat wskazujące dzień. |
| DeviceKey |Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy. To jest odwołanie do tabeli urządzenia, która zawiera identyfikator urządzenia usługi Intune. |
| DeviceName |Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| DeviceTypeKey |Klucz atrybutu typu urządzenia dla tego urządzenia. |
| ClientRegisterationStateKey |Klucz atrybutu stanu rejestracji klienta dla tego urządzenia. |
| OwnerTypeKey |Klucz atrybutu typu właściciela dla tego urządzenia: corporate (firmowy), personal (osobisty) lub unknown (nieznany). |
| objectSourceKey |Zignoruj tę kolumnę. |
| CreatedDate |Data rejestracji urządzenia. |
| LastContact |Ostatnie znane zameldowanie urządzenia w usłudze Intune. |
| LastContactNotification |Czas ostatniego powiadomienia urządzenia przez usługę Intune o zameldowaniu w usłudze Intune. |
| LastContactWorkplaceJoin |Sygnatura czasowa wskazująca ostatni znany stan dołączenia do miejsca pracy dla tego urządzenia. |
| ManagementAgentKey |Klucz agenta zarządzania skojarzony z tym urządzeniem. |
| ManagementStateKey |Klucz stanu zarządzania skojarzony z tym urządzeniem, wskazujący najnowszy stan zdalnej akcji lub to, czy były złamane ograniczenia lub odblokowany dostęp do konta root. |
| Identyfikator odwołania |Identyfikator urządzenia w usłudze Azure Active Directory. |
| WorkPlaceJoinStateKey |Klucz stanu dołączania do miejsca pracy skojarzony z tym urządzeniem. |
| CategoryId |Zignoruj tę kolumnę. |
| EnrollmentTypeKey |Klucz typu rejestracji skojarzony z tym urządzeniem wskazujący metodę rejestracji. |
| CertExpirationDate |Data wygaśnięcia certyfikatu zarządzania MDM. |
| MdmStatusKey |Klucz dla wartości MdmStatus. |
| OSFamily |Rodzina systemów operacyjnych (Windows, iOS, Android itd.) |
| OSVersion |Wersja systemu operacyjnego. |
| OSMajorVersion |Składnik wersji głównej wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| OSMinorVersion |Składnik wersji pomocniczej wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| OSBuildNumber |Składnik wersji kompilacji wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| OSRevisionNumber |Składnik wersji poprawki wersji systemu operacyjnego (główna.pomocnicza.kompilacja.poprawka). |
| EasID |Identyfikator EAS tych urządzeń, jeśli urządzenie jest zarządzane przez program Exchange Active Sync. |
| GraphDeviceIsManaged |Ostatni stan zarządzania ustawiony przez usługę Intune w usłudze Azure AD. |
| GraphDeviceIsCompliant |Ostatni stan zgodności ustawiony przez usługę Intune w usłudze Azure AD. |
| SerialNumber |Numer seryjny urządzenia, o ile jest dostępny. |
| EnrolledByUser |Identyfikator użytkownika, który zarejestrował to urządzenie. Odwołuje się do kolumny userId w tabeli użytkownika. |
| RowLastModifiedDateTimeUTC |Czas ostatniej modyfikacji tego rekordu. |
| ProcessorArchitecture |Architektura procesora. |
| DeviceAction |Ostatnia zlecona akcja urządzenia, na razie zignorować. |
| Producent |Producent urządzenia. |
| Model |Model urządzenia. |
| LastPolicyUpdateUtc |Ostatni raz, gdy zaktualizowano zasady na urządzeniu. |
| LastExchangeStatusUtc |Ostatni raz, gdy urządzenie było synchronizowane z programem Exchange. |

## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

Jednostka **MdmDeviceInventoryHistories** zawiera dzienne migawki danych spisu dla urządzeń zarządzanych przez usługę MDM w ciągu ostatnich 90 dni. Kolumna DateKey wskazuje dzień wiersza. Niektóre właściwości mogą nie mieć zastosowania lub nie zostaną wypełnione dla wszystkich urządzeń, więc zapoznaj się z tą stroną, aby uzyskać więcej szczegółowych informacji. Aby uzyskać więcej informacji, zobacz [Understand your devices with inventory in Microsoft Intune](device-inventory.md) (Poznawanie urządzeń za pomocą spisu w usłudze Microsoft Intune).

| Właściwość  | Opis |
|---------|------------|
| DateKey | Odwołanie do tabeli dat wskazujące dzień. |
| DeviceKey |Unikatowy identyfikator urządzenia w magazynie danych — klucz zastępczy. To jest odwołanie do tabeli urządzenia, która zawiera identyfikator urządzenia usługi Intune. |
| DeviceModel |Model urządzenia. |
| System operacyjny |System operacyjny urządzenia. |
| DeviceName |Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń. |
| SoftwareVersion |W większości przypadków jest to wersja systemu operacyjnego. Wyjątkiem są platformy firmy Apple, gdzie różni się od wersji systemu operacyjnego. |
| Imei |Numer IMEI |
| HardwareInventoryTimeUtc |Pierwszy raz, gdy spis został zgłoszony dla tego urządzenia. |
| InventoryModifiedTimeUtc |Ostatni raz inwentaryzacja została zapisana, gdy została wykonana ta migawka. |
| InventoryReportingTimeUtc |Ostatni raz, gdy inwentaryzacja została przeprowadzona dla tego urządzenia. |
| ExchangeActiveSyncId |Identyfikator urządzenia w programie Exchange ActiveSync. |
| ComputerSystemDescription |Opis systemu. |
| ComputerSystemName |Nazwa systemu. |
| ComputerSystemManufacturer |Producent systemu. |
| ComputerSystemModel |Model systemu. |
| UserName |Nazwa użytkownika. |
| OSType |Typ systemu operacyjnego. |
| OSCaption |Podpis systemu operacyjnego. |
| OSName |Nazwa systemu operacyjnego. |
| OSManufacturer |Producent systemu operacyjnego. |
| OSProductSuite |Pakiet produktów systemu operacyjnego. |
| OSProductType |Typ produktu systemu operacyjnego. |
| Locale |Ustawienia regionalne systemu operacyjnego. |
| PhysicalMemoryCapacity |Pojemność pamięci fizycznej (w bajtach). |
| PhysicalMemoryRemovable |Wymienna pamięć fizyczna (w bajtach). |
| SystemEnclosureChassisTypesInnerText |Definiuje typ podstawy systemu dla tego urządzenia. Liczby wskazują następujące wartości:  <br>0 lub puste = nieznany   <br>1 = komputer stacjonarny   <br>2 = laptop  <br>3 = stacja robocza  <br>4 = serwer przedsiębiorstwa  <br>100 = telefon  <br>101 = tablet  <br>102/103 = inny nieznany typ urządzenia przenośnego |
| SystemEnclosureModel |Model obudowy systemu. |
| SystemEnclosureSerialNumber |Numer seryjny obudowy systemu. |
| NetworkAdapterConfigurationText |Tekst konfiguracji z karty sieciowej. |
| MacAddress |Adres MAC. |
| SmsID |Identyfikator urządzenia w usłudze Intune. |
| CertExpiry |Data wygaśnięcia certyfikatu zarządzania MDM. |
| DeviceClientAgentVersion |Wersja agenta klienta. |
| DeviceClientID |Identyfikator klienta urządzenia. |
| SerialNumber |Numer seryjny. |
| DeviceManufacturer |Producent urządzenia. |
| DMVersion |Wersja DM. |
| Wersja oprogramowania układowego |Wersja oprogramowania układowego. |
| HardwareVersion |Wersja sprzętu. |
| PlatformType |Typ platformy. |
| ProcessorLevel |Poziom procesora. |
| ProcessorRevision |Poprawka procesora. |
| Produkt |Produkt. |
| ProductVersion |Wersja produktu. |
| OEM |Producent oryginalnego sprzętu. |
| DeviceBuildVersion |Wersja kompilacji urządzenia. |
| Meid |Identyfikator sprzętu przenośnego. |
| PhoneNumber |Numer telefonu. |
| SubscriberCarrierNetwork |Nazwa sieci telefonicznej operatora. |
| CellularTechnology |Typ sieci telefonicznej operatora (CDMA/GSM). |
| Imsi |Numer IMSI. |
| JailBroken |Wartość True, jeśli urządzenie ma złamane zabezpieczenia lub odblokowany dostęp do konta root. |
| IsActivationLockEnabled |Wartość True, jeśli blokada aktywacji jest włączona |
| DeviceType |Typ urządzenia |
| IsSupervised |Jest nadzorowane |
| DeviceDisplayNumberOfColors |Liczba kolorów wyświetlacza urządzenia |
| HorizontalResolution |Rozdzielczość pozioma ekranu urządzenia |
| VerticalResolution |Rozdzielczość pionowa ekranu urządzenia |
| StorageFree |Ilość wolnego miejsca (w bajtach) |
| StorageTotal |Całkowita ilość miejsca (w bajtach) |
| ProgramFree |Ilość wolnej pamięci programu (w bajtach) |
| ProgramTotal |Łączna ilość wolnej pamięci programu (w bajtach) |
| RemovableStorageFree |Wolne miejsce w magazynie wymiennym (w bajtach) |
| RemovableStorageTotal |Łączne wolne miejsce w magazynie wymiennym (w bajtach) |
| DeviceMemoryDeviceCapacity |Pojemność pamięci urządzenia |
| DeviceMemoryAvailableDeviceCapacity |Dostępna pojemność pamięci urządzenia |
| DeviceOSVersion |Wersja systemu operacyjnego |
| DeviceOSPlatform |Platforma systemu operacyjnego |
| DeviceOSLanguage |Język systemu operacyjnego |
| PasswordMaxAttemptsBeforeWipe |Maksymalna dozwolona liczba prób podania hasła przed wyczyszczeniem urządzenia |
| PasswordMinComplexChars |Minimalna liczba znaków złożonych wymagana w haśle |
| PasswordMinLength |Minimalna wymagana długość hasła |
| PasswordHistory |Hasło — minimalna liczba niezaakceptowanych haseł historycznych |
| PasswordEnabled |Hasło — włączone? |
| PasswordExpiration |Hasło — data wygaśnięcia. |
| AllowRecoveryPassword |Zezwalaj na odzyskiwanie hasła. |
| PasswordAutoLockTimeout |Hasło — limit czasu automatycznej blokady. |
| PasswordType |Typ hasła. |
| BacklightACTimeout |Limit czasu podświetlenia po podłączeniu do źródła zasilania. |
| BacklightBatTimeout |Limit czasu podświetlenie na baterii. |
| PowerBackupPercent |Procent zapasu zasilania. |
| BatteryPercent |Pozostały procent naładowania baterii. |
| PlatformID |Identyfikator platformy. |
| ExchangeDeviceID |Identyfikator urządzenia programu Exchange. |
| SmsProcessorDescription |Opis procesora. |
| OwnerEmailAddress |Adres e-mail właściciela. |
| DeviceOSName |Nazwa systemu operacyjnego. |
| WifiMac |Adres MAC sieci Wi-Fi. |
| EthernetMac |Adres MAC sieci Ethernet. |
| RequireEncryption |Wskazuje, czy urządzenie jest zaszyfrowane, czy nie. |
| ActivationLockBypassCode |Kod obejścia blokady aktywacji. |

## <a name="applicationinventory"></a>ApplicationInventory

Jednostka **ApplicationInventory** tworzy listę aplikacji znalezionych na urządzeniu w czasie zbierania spisu.


|      Właściwość      |                       Opis                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Odwołanie do tabeli urządzeń.               |
|   ApplicationKey   | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (skopiowany z ExchangeDeviceService\DeviceApplication). |

