---
title: Kolekcje magazynu danych usługi Intune
titleSuffix: Microsoft Intune
description: Kolekcje magazynu danych usługi Intune udostępniają szczegółowe informacje związane z interfejsem API magazynu danych.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29f09230-dc56-43db-b599-d961967bda49
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 00a0bd4936d1ad8ba8dd52f1839e7d42505db60e
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59429228"
---
#  <a name="intune-data-warehouse-collections"></a>Kolekcje magazynu danych usługi Intune

Poniższe kolekcje magazynu danych usługi Intune zawierają właściwości, opisy i przykłady dotyczące kolekcji jednostek interfejsu API magazynu danych w wersji 1.0. 

## <a name="apprevisions"></a>appRevisions
Jednostka **appRevision** przedstawia listę wszystkich wersji aplikacji.

|          Właściwość          |                                      Opis                                      |                Przykład               |
|:--------------------------:|:-------------------------------------------------------------------------------------:|:------------------------------------:|
| AppKey                     | Unikatowy identyfikator aplikacji.                                                         | 123                                  |
| ApplicationId              | Unikatowy identyfikator aplikacji — podobny do AppKey, ale ten klucz jest kluczem naturalnym.        | b66bc706-ffff-7437-0340-032819502773 |
| Przegląd                   | Wersja zgodna z podaną przez administratora podczas przekazywania pliku binarnego.                   | 2                                    |
| Tytuł                      | Tytuł aplikacji.                                                                     | Excel                                |
| Wydawca                  | Wydawca aplikacji.                                                                 | Microsoft                            |
| UploadState                | Stan przekazania aplikacji.                                                              | 1                                    |
| AppTypeKey                 | Odwołanie do jednostki AppType opisanej w następującej sekcji.                            | 1                                    |
| VppProgramTypeKey          | Odwołanie do jednostki VppProgramType opisanej poniżej.                                        | 30876                                |
| CreationTime               | Godzina utworzenia tej poprawki.                                            | 23.11.2016 0:00                      |
| ModifiedTime               | Godzina ostatniej zmiany dotyczącej tej poprawki.                            | 23.11.2016 0:00                      |
| Size                       | Rozmiar pliku binarnego w bajtach.                                                          | 120 392 000                          |
| StartDateInclusiveUTC      | Data i godzina utworzenia tej poprawki aplikacji (czas UTC) w magazynie danych.      | 23.11.2016 0:00                      |
| EndDateExclusiveUTC        | Data i godzina utraty ważności przez tę poprawkę aplikacji w formacie UTC.                        | 23.11.2016 0:00                      |
| IsCurrent                  | Wskazuje, czy ta wersja aplikacji jest aktualna w magazynie danych, czy nie.         | Prawda/Fałsz                           |
| RowLastModifiedDateTimeUTC | Data i godzina w formacie UTC ostatniej modyfikacji tej wersji aplikacji w magazynie danych. | 23.11.2016 0:00                      |

## <a name="apptypes"></a>appTypes
Jednostka **appType** przedstawia źródło instalacji aplikacji.

|   Właściwość  |        Opis        |
|:-----------:|:-------------------------:|
| AppTypeID   | Identyfikator typu           |
| AppTypeKey  | Klucz zastępczy klucza |
| AppTypeName | Typ aplikacji                  |

### <a name="example"></a>Przykład

| AppTypeID |                Nazwa               |                     Opis                     |
|:---------:|:---------------------------------:|:---------------------------------------------------:|
| 0         | Aplikacja ze sklepu dla systemu Android               | Aplikacja ze sklepu dla systemu Android.                             |
| 1         | Aplikacja LOB dla systemu Android                 | Aplikacja biznesowa dla systemu Android.                  |
| 2         | Zarządzana aplikacja ze sklepu dla systemu Android (MAM) | Aplikacja ze sklepu dla systemu Android z włączonym zarządzaniem. |
| 3         | Aplikacja ze sklepu dla systemu iOS                   | Aplikacja ze sklepu dla systemu iOS.                                 |
| 4         | Aplikacja LOB dla systemu iOS                     | Aplikacja biznesowa dla systemu iOS.                      |
| 5         | Zarządzana aplikacja ze sklepu dla systemu iOS (MAM)     | Aplikacja ze sklepu dla systemu iOS z włączonym zarządzaniem.       |
| 6         | Pakiet O365 Pro Plus             | Pakiet Office 365 Pro Plus dla systemu Windows 10.     |
| 7         | Aplikacja internetowa                         | Aplikacja internetowa.                                        |
| 8         | Aplikacja ze sklepu dla systemu Windows Phone 8.1     | Aplikacja ze sklepu dla systemu Windows Phone 8.1.                    |
| 9         | Aplikacja ze Sklepu Windows               | Aplikacja ze Sklepu Windows.                              |
| 10        | Aplikacja LOB dla systemu Windows                | Aplikacja biznesowa AppX dla systemu Windows.              |
| 11        | Aplikacja MSI dla systemu Windows Mobile              | Aplikacja biznesowa MSI.                      |
| 12        | Aplikacja LOB dla systemu Windows Phone           | Aplikacja biznesowa dla systemu Windows Phone.             |

## <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities
Poniższa tabela zawiera podsumowanie stanu przypisania zasad zgodności do urządzeń. Wyświetla ona liczbę znalezionych urządzeń z poszczególnymi stanami zgodności.

|    Właściwość   |                                                                                      Opis                                                                                     |  Przykład |
|:-------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey       | Klucz daty utworzenia podsumowania zasad zgodności.                                                                                                                   | 20161204 |
| Nieznane       | Liczba urządzeń, które są w trybie offline lub nie nawiązały łączności z usługą Intune lub Azure AD z innych przyczyn.                                                                           | 5        |
| NotApplicable | Liczba urządzeń, na których nie mają zastosowania zasady zgodności urządzeń przepisane przez administratora.                                                                                     | 201      |
| Zgodny     | Liczba urządzeń, które pomyślnie zastosowały co najmniej jedne zasady zgodności urządzenia przepisane przez administratora.                                                                        | 4083     |
| InGracePeriod | Liczba urządzeń, które nie są zgodne, ale są w okresie prolongaty zdefiniowanym przez administratora.                                                                                  | 57       |
| NonCompliant  | Liczba urządzeń, na których nie udało się zastosować co najmniej jednej z zasad zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora. | 43       |
|    Error      |    Liczba urządzeń, które nie mogły nawiązać połączenia z usługą Intune lub usługą Azure AD i zwróciły komunikat o błędzie.                                                                          |    3     |

## <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities
Poniższa tabela zawiera podsumowanie stanu przypisania zasad zgodności do urządzeń na podstawie zasad i na podstawie typu zasad. Wyświetla ona liczbę znalezionych urządzeń z poszczególnymi stanami zgodności dla każdej przypisanej zasady zgodności.

|      Właściwość     |                                                                                      Opis                                                                                     |  Przykład |
|:-----------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey           | Klucz daty utworzenia podsumowania zasad zgodności.                                                                                                                   | 20161219 |
| PolicyKey         | Klucz zasad zgodności, dla których utworzono podsumowanie.                                                                                                                   | 10178    |
| PolicyPlatformKey | Klucz typu platformy zasad zgodności, dla którego utworzono podsumowanie.                                                                                            | 5        |
| Nieznane           | Liczba urządzeń, które są w trybie offline lub nie nawiązały łączności z usługą Intune lub Azure AD z innych przyczyn.                                                                           | 13       |
| NotApplicable     | Liczba urządzeń, na których nie mają zastosowania zasady zgodności urządzeń przepisane przez administratora.                                                                                     | 3        |
| Zgodny         | Liczba urządzeń, które pomyślnie zastosowały co najmniej jedne zasady zgodności urządzenia przepisane przez administratora.                                                                        | 45       |
| InGracePeriod     | Liczba urządzeń, które nie są zgodne, ale są w okresie prolongaty zdefiniowanym przez administratora.                                                                                  | 3        |
| NonCompliant      | Liczba urządzeń, na których nie udało się zastosować co najmniej jednej z zasad zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora. | 7        |
| Error             | Liczba urządzeń, które nie mogły nawiązać połączenia z usługą Intune lub usługą Azure AD i zwróciły komunikat o błędzie.                                                                             | 3        |
## <a name="compliancestates"></a>complianceStates

|      Właściwość      |                       Opis                      |
|:------------------:|:------------------------------------------------------:|
| complianceStatus   | Stan zgodności urządzeń z kluczem mdmStatusKey       |
| complianceStateKey | Klucz zgodności umożliwiający dopasowanie urządzenia i stanu zgodności |
| complianceStateID  | Identyfikator umożliwiający dopasowanie stanu zgodności                |

### <a name="example"></a>Przykład

|  complianceStatus  |                       Opis                      |
|:------------------:|:------------------------------------------------------:|
|    Nieznane         |    Nieznane.                                                                        |
|    Zgodny       |    Zgodne.                                                                      |
|    Niezgodny    |       Urządzenie jest niezgodne i użycie w nim zasobów firmowych zostało zablokowane.             |
|    Konflikt        |    Konflikt z innymi regułami.                                                      |
|    Error           |       Błąd.                                                                       |
|    ConfigManager   |    Zarządzane przez program Config Manager.                                                      |
|    InGracePeriod   |       Urządzenie jest niezgodne, ale nadal ma dostęp do zasobów firmowych          |

## <a name="dates"></a>daty
Jednostka **date** reprezentuje daty, które są przywoływane przez wiele jednostek magazynu danych.

|     Właściwość    |                       Opis                      |    Przykład    |
|:---------------:|:------------------------------------------------------:|:-------------:|
| DateKey         | Unikatowy identyfikator danej daty w magazynie danych. | 20160703      |
| FullDate        | Ta data jest reprezentowana w pełnym formacie data/godzina.        | 3.07.2016 0:00 |
| DayOfWeek       | Dzień tygodnia                                            | 1             |
| DayOfMonth      | Dzień miesiąca                                           | 3             |
| DayOfYear       | Dzień roku                                            | 185           |
| WeekOfYear      | Tydzień roku                                           | 28            |
| MonthOfYear     | Miesiąc roku                                      | 7             |
| CalendarQuarter | Kwartał kalendarzowy                                       | 3             |
| CalendarYear    | Rok kalendarzowy                                          | 2016          |
| DateKey         | Unikatowy identyfikator danej daty w magazynie danych. | 20160703      |
| FullDate        | Ta data jest reprezentowana w pełnym formacie data/godzina.        | 3.07.2016 0:00 |
| DayOfWeek       | Dzień tygodnia                                            | 1             |
| DayOfMonth      | Dzień miesiąca                                           | 3             |
| DayOfYear       | Dzień roku                                            | 185           |
| WeekOfYear      | Tydzień roku                                           | 28            |
| MonthOfYear     | Miesiąc roku                                      | 7             |
| CalendarQuarter | Kwartał kalendarzowy                                       | 3             |
| CalendarYear    | Rok kalendarzowy                                          | 2016          |

## <a name="devicecategories"></a>deviceCategories

|      Właściwość      |                                    Opis                                   |                Przykład               |
|:------------------:|:--------------------------------------------------------------------------------:|:------------------------------------:|
| deviceCategoryID   | Unikalny identyfikator kategorii urządzenia.                                       | fb415ba2-7c08-41f6-a5e5-685b50da2c4c |
| deviceCategoryKey  | Unikatowy identyfikator kategorii urządzenia w magazynie danych — klucz zastępczy | 1                                    |
| deviceCategoryName | Nazwa wyświetlana kategorii urządzenia.                                            | Smartfony                          |

## <a name="deviceconfigurationprofiledeviceactivities"></a>deviceConfigurationProfileDeviceActivities
Jednostka **DeviceConfigurationProfileDeviceActivity** zawiera liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład urządzenie jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

|  Właściwość |                                          Opis                                          |  Przykład |
|:---------:|:---------------------------------------------------------------------------------------------:|:--------:|
| DateKey   | Klucz daty zaewidencjonowania profilu konfiguracji urządzeń w magazynie danych. | 20160703 |
| Oczekiwanie   | Liczba unikatowych urządzeń w stanie Oczekiwanie.                                                    | 123      |
| Sukces | Liczba unikatowych urządzeń w stanie Sukces.                                                    | 12       |
| Error     | Liczba unikatowych urządzeń w stanie Błąd.                                                      | 10       |
| Niepowodzenie    | Liczba unikatowych urządzeń w stanie Niepowodzenie.                                                     | 2        |

## <a name="deviceconfigurationprofileuseractivities"></a>deviceConfigurationProfileUserActivities 
Jednostka **DeviceConfigurationProfileUserActivity** zawiera liczbę użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Ta liczba odzwierciedla profile konfiguracji urządzeń przypisane do jednostki. Jeśli na przykład użytkownik jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd. Jednostka **DeviceConfigurationProfileUserActivity** zawiera liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni. 

| Właściwość  | Opis  | Przykład  |
|------------|----------------------------------------------------------------------------------------------|-----------|
| DateKey  | Klucz daty zarejestrowania zameldowania profilu konfiguracji urządzeń w magazynie danych.  | 20160703  |
| Oczekiwanie  | Liczba unikatowych użytkowników w stanie Oczekiwanie.  | 123  |
| Sukces  | Liczba unikatowych użytkowników w stanie Sukces.  | 12  |
| Error  | Liczba unikatowych użytkowników w stanie Błąd.  | 10  |
| Niepowodzenie  | Liczba unikatowych użytkowników w stanie Niepowodzenie.  | 2  |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

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
| DeviceCategoryKey          | Klucz atrybutu kategorii urządzenia dla tego urządzenia.                                                                                                                                    |
## <a name="deviceregistrationstates"></a>deviceRegistrationStates
Jednostka **DeviceRegistrationState** reprezentuje typ rejestracji przywoływany przez inne kolekcje magazynu danych. 

|           Właściwość          |                                     Opis                                     |
|:---------------------------:|:-----------------------------------------------------------------------------------:|
| deviceRegistrationStateID   | Unikatowy identyfikator stanu rejestracji                                            |
| deviceRegistrationStateKey  | Unikatowy identyfikator stanu rejestracji w magazynie danych — klucz zastępczy |
| deviceRegistrationStateName | Stan rejestracji                                                                  |
|    NotRegistered                     |    Niezarejestrowany                                                                                                                                                                  |
|    Zarejestrowany                        |       Zarejestrowany                                                                                                                                                                   |
|    Revoked                           |       Stan oznacza, że administrator IT zablokował klienta i klienta można odblokować. Urządzenie może również być w stanie odwołania po jego wyczyszczeniu lub wycofaniu.        |
|    KeyConflict                       |    Konflikt klucza                                                                                                                                                                    |
|    ApprovalPending                   |    Oczekiwanie na zatwierdzenie                                                                                                                                                                |
|    CertificateReset                  |    Resetowanie certyfikatu                                                                                                                                                               |
|    NotRegisteredPendingEnrollment    |    Niezarejestrowane oczekujące na rejestrację                                                                                                                                               |
|    Nieznane                           |    Nieznany stan                                                                                                                                                                   |

## <a name="devices"></a>devices
Jednostka **device** zawiera listę wszystkich zarejestrowanych urządzeń w obszarze zarządzania oraz odpowiadające im właściwości.

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


## <a name="devicetypes"></a>deviceTypes
Jednostka **deviceType** reprezentuje typ urządzenia przywoływany przez inne jednostki magazynu danych. Typ urządzenia zwykle opisuje model urządzenia, producenta lub kombinację obu tych informacji.

|    Właściwość    |                                  Opis                                 |
|:--------------:|:----------------------------------------------------------------------------:|
| DeviceTypeID   | Unikatowy identyfikator typu urządzenia                                       |
| DeviceTypeKey  | Unikatowy identyfikator typu urządzenia w magazynie danych — klucz zastępczy |
| DeviceTypeName | Typ urządzenia                                                                |

### <a name="example"></a>Przykład

| deviceTypeID |        Nazwa       |                      Opis                      |
|:------------:|:-----------------:|:-----------------------------------------------------:|
| -1           | Niedostępny   | Typ urządzenia jest niedostępny.                     |
| 0            | Komputery           | Komputer z systemem Windows                              |
| 1            | Windows           | Urządzenie z systemem Windows                                      |
| 2            | WinMO6            | Urządzenie z systemem Windows Mobile 6.0                           |
| 3            | Nokia             | Urządzenie firmy Nokia                                        |
| 4            | WindowsPhone      | Urządzenie z systemem Windows Phone                                |
| 5            | Mac               | Urządzenie Mac                                          |
| 6            | WinCE             | Urządzenia z systemem Windows CE                                   |
| 7            | WinEmbedded       | Urządzenie z systemem Windows Embedded                             |
| 8            | iPhone            | Urządzenie iPhone                                       |
| 9            | iPad              | Urządzenie iPad                                         |
| 10           | iPod              | Urządzenie iPod                                         |
| 11           | Android           | Urządzenie z systemem Android zarządzane przy użyciu administratora urządzenia   |
| 12           | ISocConsumer      | Urządzenie iSoc Consumer                                |
| 13           | Unix              | Urządzenie z systemem UNIX                                         |
| 14           | MacMDM            | Urządzenie z systemem Mac OS X zarządzane za pomocą wbudowanego agenta MDM |
| 15           | HoloLens          | Urządzenie HoloLens                                       |
| 16           | SurfaceHub        | Urządzenie Surface Hub                                  |
| 17           | AndroidForWork    | Urządzenie z systemem Android zarządzane przy pomocy właściciela profilu systemu Android  |
| 18           | AndroidEnterprise | Urządzenie z systemem Android Enterprise.                          |
| 100          | Blackberry        | Urządzenie Blackberry                                   |
| 101          | Palm              | Urządzenie Palm                                         |
| 255          | Nieznane           | Nieznany typ urządzenia                                 |

## <a name="deviceenrollmenttypes"></a>deviceEnrollmentTypes
Jednostka **deviceEnrollmentType** wskazuje, jak urządzenie zostało zarejestrowane. Typ rejestracji przechwytuje metodę rejestracji. Przykłady listy różnych typów rejestracji i ich znaczenie.

|         Właściwość         |                                    Opis                                    |
|:------------------------:|:---------------------------------------------------------------------------------:|
| deviceEnrollmentTypeID   | Unikatowy identyfikator typu rejestracji.                                       |
| deviceEnrollmentTypeKey  | Unikatowy identyfikator typu rejestracji w magazynie danych — klucz zastępczy. |
| deviceEnrollmentTypeName | Nazwa typu rejestracji.                                                           |

### <a name="example"></a>Przykład

| enrollmentTypeID |                Nazwa                |                                        Opis                                       |
|:----------------:|:----------------------------------:|:----------------------------------------------------------------------------------------:|
| 0                | Nieznane                            | Typ rejestracji nie został zebrany                                                      |
| 1                | UserEnrollment                     | Rejestracja sterowana przez użytkownika za pośrednictwem kanału BYOD.                                           |
| 2                | DeviceEnrollmentManager            | Rejestracja użytkownika przy użyciu konta menedżera rejestracji urządzeń.                              |
| 3                | AppleBulkWithUser                  | Zbiorcze rejestrowanie firmy Apple przy użyciu żądania użytkownika. (DEP, Apple Configurator)                   |
| 4                | AppleBulkWithoutUser               | Zbiorcze rejestrowanie firmy Apple bez użycia żądania użytkownika.   (DEP, Apple Configurator, Mobile Config) |
| 5                | WindowsAzureADJoin                 | Dołączanie do usługi Windows 10 w usłudze Azure AD.                                                                |
| 6                | WindowsBulkUserless                | Rejestrowanie zbiorcze w systemie Windows 10 za pośrednictwem ICD z certyfikatem.                               |
| 7                | WindowsAutoEnrollment              | Rejestrowanie automatyczne urządzeń z systemem Windows 10.   (Dodaj konto służbowe)                                    |
| 8                | WindowsBulkAzureDomainJoin         | Zbiorcze dołączanie urządzeń z systemem Windows 10 do usługi Azure AD.                                                           |
| 9                | WindowsCoManagement                | Współzarządzanie urządzeniami z systemem Windows 10 wyzwalane przez rozwiązanie AutoPilot lub zasady grupy.                       |
| 10               | WindowsAzureADJoinsUsingDeviceAuth | Dołączanie urządzeń z systemem Windows 10 do usługi Azure AD przy użyciu uwierzytelniania urządzeń.                                            |

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

## <a name="intunemanagementextensions"></a>intuneManagementExtensions
Jednostka **intuneManagementExtension** zawiera listę kondycji jednostki **intuneManagementExtension** na każdym urządzeniu z systemem Windows 10 dziennie. Dane są zachowywane przez ostatnie 60 dni.

|       Właściwość      |                          Opis                          | Przykład |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| DateKey             | Unikatowy identyfikator daty.                                | 123     |
| TenantKey           | Unikatowy identyfikator dzierżawy.                              | 456     |
| DeviceKey           | Unikatowy identyfikator urządzenia.                              | 789     |
| ExtensionVersionKey | Unikatowy identyfikator wersji jednostki IntuneManagementExtension. | 1       |
| ExtensionStateKey   | Unikatowy identyfikator kondycji.                            | 2       |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates
Jednostka **IntuneManagementExtensionHealthState** zawiera listę wszystkich możliwych stanów kondycji jednostki **IntuneManagementExtension**.

|      Właściwość     |                   Opis                  | Przykład |
|:-----------------:|:----------------------------------------------:|:-------:|
| ExtensionStateKey | Unikatowy identyfikator stanu kondycji.           | 2       |
| ExtensionState    | Stan kondycji jednostki IntuneManagementExtension. | Dobra kondycja |

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions
Jednostka **IntuneManagementExtensionVersion** wyświetla listę wszystkich wersji używanych przez jednostkę **IntuneManagementExtension**.

|       Właściwość      |                          Opis                          | Przykład |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| ExtensionVersionKey | Unikatowy identyfikator wersji jednostki IntuneManagementExtension. | 1       |
| ExtensionVersion    | Czterocyfrowy numer wersji.                                   | 1.0.2.0 |

## <a name="mamapplications"></a>MamApplications

Jednostka **MamApplication** tworzy listę aplikacji biznesowych (LOB), które są zarządzane za pomocą zarządzania aplikacjami mobilnymi (MAM) bez rejestracji w Twoim przedsiębiorstwie.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| mamApplicationKey |Unikatowy identyfikator aplikacji MAM. | 432 |
| mamApplicationName |Nazwa aplikacji MAM. |Przykładowa nazwa aplikacji MAM |
| mamApplicationId |Identyfikator aplikacji MAM. | 123 |
| IsDeleted |Wskazuje, czy ten rekord aplikacji MAM został zaktualizowany. <br>True — aplikacja MAM ma nowy rekord ze zaktualizowanymi polami w tej tabeli. <br>False — to jest najnowszy rekord dla tej aplikacji MAM. |Prawda/Fałsz |
| StartDateInclusiveUTC |Data i godzina w formacie UTC utworzenia tej aplikacji MAM w magazynie danych. |2016-11-23 12:00:00 |
| DeletedDateUTC |Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True. |2016-11-23 12:00:00 |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji tej aplikacji MAM w magazynie danych. |2016-11-23 12:00:00 |


## <a name="mamapplicationinstances"></a>MamApplicationInstances

Jednostka **MamApplicationInstance** tworzy listę zarządzanych aplikacji zarządzania aplikacjami mobilnymi (MAM) jako pojedynczych wystąpień na użytkownika na urządzeniu. Wszyscy użytkownicy i urządzenia wymienieni w jednostce są chronieni, jakby mieli przypisane do siebie co najmniej jedne zasady MAM.


|          Właściwość          |                                                                                                  Opis                                                                                                  |               Przykład                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   ApplicationInstanceKey   |                                                               Unikatowy identyfikator wystąpienia aplikacji MAM w magazynie danych — klucz zastępczy.                                                                |                 123                  |
|           UserId           |                                                                              Identyfikator użytkownika, który ma zainstalowaną tę aplikację MAM.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              Unikatowy identyfikator wystąpienia aplikacji MAM — podobny do wartości ApplicationInstanceKey, ale identyfikator jest kluczem naturalnym.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Identyfikator aplikacji MAM, dla której utworzono to wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
|     ApplicationVersion     |                                                                                     Wersja aplikacji dla tej aplikacji MAM.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 Data utworzenia tego rekordu wystąpienia aplikacji MAM. Wartość może być równa null.                                                                 |        2016-11-23 12:00:00        |
|          Platforma          |                                                                          Platforma urządzenia, na której zainstalowano tę aplikację MAM.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Wersja platformy urządzenia, na której jest zainstalowana ta aplikacja MAM.                                                                       |                 2.2                  |
|         SdkVersion         |                                                                            Wersja zestawu SDK MAM, za pomocą którego aplikacja MAM została opakowana.                                                                            |                 3.2                  |
| mamDeviceId | Identyfikator urządzenia, z którym jest skojarzone wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
| mamDeviceType | Typ urządzenia, z którym jest skojarzone wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
| mamDeviceName | Nazwa urządzenia, z którym jest skojarzone wystąpienie aplikacji MAM.   | 2016-11-23 12:00:00   |
|         IsDeleted          | Wskazuje, czy ten rekord wystąpienia aplikacji MAM został zaktualizowany. <br>True — to wystąpienie aplikacji MAM ma nowy rekord ze zaktualizowanymi polami w tej tabeli. <br>False — to jest najnowszy rekord dla tego wystąpienia aplikacji MAM. |              Prawda/Fałsz              |
|   StartDateInclusiveUTC    |                                                              Data i godzina w formacie UTC utworzenia tego wystąpienia aplikacji MAM w magazynie danych.                                                               |        2016-11-23 12:00:00        |
|       DeletedDateUTC       |                                                                             Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True.                                                                              |        2016-11-23 12:00:00        |
| RowLastModifiedDateTimeUTC |                                                           Data i godzina w formacie UTC ostatniej modyfikacji tego wystąpienia aplikacji MAM w magazynie danych.                                                            |        2016-11-23 12:00:00        |

## <a name="mamcheckins"></a>MamCheckins

Jednostka **MamCheckin** reprezentuje dane zebrane po zameldowaniu wystąpienia aplikacji zarządzania aplikacjami mobilnymi (MAM) przez usługę Intune. 

> [!Note]  
> Gdy wystąpienie aplikacji zostanie zameldowane wiele razy w ciągu dnia, magazyn danych zapisuje to jako jedno zameldowanie.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| DateKey |Klucz daty zarejestrowania zameldowania aplikacji MAM w magazynie danych. | 20160703 |
| ApplicationInstanceKey |Klucz wystąpienia aplikacji skojarzony z zameldowaniem tej aplikacji MAM. | 123 |
| UserKey |Klucz użytkownika skojarzony z zameldowaniem tej aplikacji MAM. | 4323 |
| mamApplicationKey |Klucz aplikacji skojarzonej z zameldowaniem aplikacji MAM. | 432 |
| DeviceHealthKey |Klucz kondycji urządzenia skojarzony z zameldowaniem tej aplikacji MAM. | 321 |
| PlatformKey |Reprezentuje platformę urządzenia skojarzonego z zameldowaniem tej aplikacji MAM. |123 |
| LastCheckInDate |Data i godzina ostatniego zameldowania tej aplikacji MAM. Wartość może być równa null. |2016-11-23 12:00:00 |

## <a name="mamdevicehealths"></a>MamDeviceHealths

Jednostka **MamDeviceHealth** reprezentuje urządzenia, które mają wdrożone zasady zarządzania aplikacjami mobilnymi (MAM), nawet jeśli zdjęto z nich zabezpieczenia systemu.

| Właściwość | Opis | Przykład |
|---------|------------|--------|
| DeviceHealthKey |Unikatowy identyfikator urządzenia i jego skojarzonej kondycji w magazynie danych — klucz zastępczy. |123 |
| DeviceHealth |Unikatowy identyfikator urządzenia i jego skojarzonej kondycji — podobny do wartości DeviceHealthKey, ale identyfikator jest kluczem naturalnym. |b66bc706-ffff-7777-0340-032819502773 |
| DeviceHealthName |Reprezentuje stan urządzenia. <br>Not available — brak informacji o tym urządzeniu. <br>Healthy — urządzenie nie ma zdjętych zabezpieczeń systemu. <br>Unhealthy — urządzenie ma zdjęte zabezpieczenia systemu. |Not Available Healthy Unhealthy |
| RowLastModifiedDateTimeUTC |Data i godzina w formacie UTC ostatniej modyfikacji kondycji konkretnego urządzenia MAM w magazynie danych. |2016-11-23 12:00:00 |

## <a name="mamplatforms"></a>MamPlatforms

Jednostka **MamPlatform** tworzy listę nazw platform i typów, na których zainstalowano aplikację zarządzania aplikacjami mobilnymi (MAM).


|          Właściwość          |                                    Opis                                    |                         Przykład                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        PlatformKey         |     Unikatowy identyfikator platformy w magazynie danych — klucz zastępczy.      |                           123                           |
|          Platforma          | Unikatowy identyfikator platformy — podobny do wartości PlatformKey, ale jest kluczem naturalnym. |                           123                           |
|        PlatformName        |                                   Nazwa platformy                                   | Niedostępny <br>Brak <br>Windows <br>System iOS <br>Urządzenia z systemem Android. |
| RowLastModifiedDateTimeUTC | Data i godzina w formacie UTC ostatniej modyfikacji tej platformy w magazynie danych.  |                 2016-11-23 12:00:00                  |

## <a name="managementagenttypes"></a>managementAgentTypes
Jednostka **managementAgentTypes** reprezentuje agentów używanych do zarządzania urządzeniem.

|         Właściwość        |                                       Opis                                       |
|:-----------------------:|:---------------------------------------------------------------------------------------:|
| ManagementAgentTypeID   | Unikatowy identyfikator typu agenta zarządzania.                                         |
| ManagementAgentTypeKey  | Unikatowy identyfikator typu agenta zarządzania w magazynie danych — klucz zastępczy. |
| ManagementAgentTypeName | Wskazuje, jaki rodzaj agenta służy do zarządzania urządzeniem.                              |

### <a name="example"></a>Przykład

| ManagementAgentTypeID |                Nazwa               |                                  Opis                                 |
|:---------------------:|:---------------------------------:|:----------------------------------------------------------------------------:|
| 1                     | EAS                               | Urządzenie jest zarządzane przy użyciu programu Exchange Active Sync                         |
| 2                     | ZARZĄDZANIE URZĄDZENIAMI PRZENOŚNYMI                               | Urządzenie jest zarządzane przy użyciu agenta MDM                                   |
| 3                     | EasMdm                            | Urządzenie jest zarządzane zarówno przez program Exchange Active Sync, jak i agenta MDM        |
| 4                     | IntuneClient                      | Urządzenie jest zarządzane przez agenta PC usługi Intune                               |
| 5                     | EasIntuneClient                   | Urządzenie jest zarządzane zarówno przez program Exchange Active Sync, jak i agenta PC usługi Intune |
| 8                     | ConfigManagerClient               | Urządzenie jest zarządzane przez agenta programu System Center Configuration Manager     |
| 10                    | ConfigurationManagerClientMdm     | Urządzenie jest zarządzane przez program Configuration Manager i oprogramowanie MDM.                    |
| 11                    | ConfigurationManagerCLientMdmEas  | Urządzenie jest zarządzane przez program Configuration Manager, oprogramowanie MDM i rozwiązanie Exchange Active Sync.               |
| 16                    | Nieznane                           | Nieznany typ agenta zarządzania                                              |
| 32                    | Jamf                              | Atrybuty urządzenia są pobierane z narzędzia Jamf.                               |
| 64                    | GoogleCloudDevicePolicyController |  Urządzenie jest zarządzane przez rozwiązanie CloudDPC firmy Google.                                 |

## <a name="managementstates"></a>managementStates
Jednostka **ManagementState** zawiera szczegółowe informacje dotyczące stanu urządzenia. Szczegóły mogą być przydatne w przypadkach, gdy są stosowane akcje zdalne, a urządzenie ma zdjęte zabezpieczenia lub odblokowany dostęp do konta root.

|       Właściwość      |                                     Opis                                    |
|:-------------------:|:----------------------------------------------------------------------------------:|
| managementStateID   | Unikatowy identyfikator stanu zarządzania.                                       |
| managementStateKey  | Unikatowy identyfikator stanu zarządzania w magazynie danych — klucz zastępczy. |
| managementStateName | Wskazuje stan zdalnej akcji zastosowanej do tego urządzenia.                 |

### <a name="example"></a>Przykład

| managementStateID |      Nazwa      |                                                   Opis                                                   |
|:-----------------:|:--------------:|:---------------------------------------------------------------------------------------------------------------:|
| 0                 | Zarządzani        | Zarządzane bez żadnych oczekujących akcji zdalnych.                                                                       |
| 1                 | RetirePending  | Dla tego urządzenia istnieje oczekujące polecenie wycofania.                                                             |
| 2                 | RetireFailed   | Polecenie wycofania nie powiodło się na tym urządzeniu.                                                                      |
| 3                 | WipePending    | Dla tego urządzenia istnieje oczekujące polecenie wyczyszczenia.                                                               |
| 4                 | WipeFailed     | Polecenie wyczyszczenia nie powiodło się na tym urządzeniu.                                                                        |
| 5                 | Nieprawidłowy      | Stan złej kondycji.                                                                                              |
| 6                 | DeletePending  | Dla tego urządzenia istnieje oczekujące polecenie usunięcia.                                                             |
| 7                 | RetireIssued   | Wydano polecenie wycofania tego urządzenia.                                                               |
| 8                 | WipeIssued     | Wydano polecenie wyczyszczenia.                                                                               |
| 9                 | WipeCanceled   | Anulowano polecenie wyczyszczenia.                                                                               |
| 10                | RetireCanceled | Anulowano polecenie wycofania.                                                                             |
| 11                | Discovered     | Urządzenie zostało nowo odnalezione przez usługę Intune, a po zaewidencjonowaniu po raz pierwszy następuje przeniesienie do stanu -Zarządzane-. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates
Jednostka MobileAppInstallState reprezentuje stan instalacji aplikacji mobilnej po przypisaniu jej do grupy zawierającej urządzenia, użytkowników lub obie te kategorie.

|       Właściwość      |                        Opis                       |
|:-------------------:|:--------------------------------------------------------:|
| AppInstallStateKey  | Unikatowy identyfikator stanu instalacji aplikacji dla konta użytkownika. |
| AppInstallState     | Wartość wyliczenia stanu instalacji aplikacji.                     |
| AppInstallStateName | Nazwa stanu instalacji aplikacji.                           |

## <a name="mobileappinstallstatuscounts"></a>mobileAppInstallStatusCounts
Reprezentuje stan instalacji aplikacji mobilnej dla danego docelowego typu urządzenia za pośrednictwem oprogramowania do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune.

|      Właściwość      |                                                          Opis                                                          |
|:------------------:|:-----------------------------------------------------------------------------------------------------------------------------:|
| DateKey            | Klucz daty rejestracji stanu instalacji aplikacji.                                                                     |
| AppKey             | Klucz aplikacji mobilnej używany do identyfikowania wystąpienia AppRevision.                                                          |
| DeviceTypeKey      | Klucz typu urządzenia skojarzony z aplikacją mobilną.                                                              |
| AppInstallStateKey | Klucz stanu instalacji aplikacji używany do identyfikowania wystąpienia elementu MobileAppInstallState.                                         |
| ErrorCode          | Kod błędu zwracany przez instalatora aplikacji, platformę mobilną lub usługę, który odnosi się do instalacji aplikacji. |
| Liczba              | Łączna liczba.                                                                                                                  |

## <a name="ownertypes"></a>ownerTypes
Jednostka **ownerType** wskazuje, czy urządzenie jest firmowe, osobiste czy nieznane.

|    Właściwość   |                                                                                     Opis                                                                                    |           Przykład          |
|:-------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------:|
| ownerTypeID   | Unikatowy identyfikator typu właściciela.                                                                                                                                               |                            |
| ownerTypeKey  | Unikatowy identyfikator typu właściciela w magazynie danych — klucz zastępczy.                                                                                                       |                            |
| ownerTypeName | Reprezentuje typ właściciela urządzenia: Corporate — urządzenie jest własnością przedsiębiorstwa.  Personal — urządzenie jest własnością osobistą (BYOD).   Unknown — brak informacji o tym urządzeniu. | Corporate Personal Unknown |

> [!Note]  
> Na potrzeby filtru `ownerTypeName` w usłudze Azure AD należy podczas tworzenia grup dynamicznych dla urządzeń ustawić wartość parametru `deviceOwnership` na `Company`. Aby uzyskać więcej informacji, zobacz [Reguły urządzeń](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="policies"></a>policies
Jednostka **Policy** zawiera listę profilów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

|          Właściwość          |                                                                       Opis                                                                      |                Przykład               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| PolicyKey                  | Unikatowy klucz reprezentujący zasady w magazynie danych.                                                                                              | 123                                  |
| PolicyId                   | Unikatowy identyfikator zasad w magazynie danych.                                                                                                 | b66bc706-ffff-7437-0340-032819502773 |
| PolicyName                 | Nazwa zasad.                                                                                                                                    | „Plan bazowy systemu Windows 10”                |
| PolicyVersion              | Wersja zasad. Po edycji lub zmianie zasad tworzona jest nowa wersja.                                                             | 1, 2, 3                              |
| IsDeleted                  | Wskazuje, czy rekord zasad został zaktualizowany.  True — zasady mają nowy rekord ze zaktualizowanymi polami.  False — najnowszy rekord zasad. | Prawda/Fałsz                           |
| StartDateInclusiveUTC      | Data i godzina w formacie UTC utworzenia zasad w magazynie danych.                                                                              | 23.11.2016 0:00                      |
| DeletedDateUTC             | Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True.                                                                                                   | 23.11.2016 0:00                      |
| RowLastModifiedDateTimeUTC | Data i godzina w formacie UTC ostatniej modyfikacji zasad w magazynie danych.                                                                        | 23.11.2016 0:00                      |

## <a name="policydeviceactivities"></a>policyDeviceActivities
Poniższa tabela zawiera liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Liczba odzwierciedla dane dla profilów typów zasad. Jeśli na przykład urządzenie jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do urządzenia są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, jednostka spowoduje zwiększenie licznika powodzeń i przełączy urządzenie w stan Błąd. Jednostka **policyDeviceActivity** przedstawia liczbę urządzeń w określonym stanie w danym dniu z 30 ostatnich dni.

|  Właściwość |                                           Opis                                           |        Przykład        |
|:---------:|:-----------------------------------------------------------------------------------------------:|:---------------------:|
| DateKey   | Klucz daty zarejestrowania zaewidencjonowania profilu konfiguracji urządzeń w magazynie danych. | 20160703              |
| Oczekiwanie   | Liczba unikatowych urządzeń w stanie Oczekiwanie.                                                    | 123                   |
| Sukces | Liczba unikatowych urządzeń w stanie Sukces.                                                    | 12                    |
| PolicyKey | Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName.                                  | Plan bazowy systemu Windows 10 |
| Error     | Liczba unikatowych urządzeń w stanie Błąd.                                                      | 10                    |
| Niepowodzenie    | Liczba unikatowych urządzeń w stanie Niepowodzenie.                                                     | 2                     |

## <a name="policyplatformtypes"></a>policyPlatformTypes

|        Właściwość        |                      Opis                      |     Przykład    |
|:----------------------:|:-----------------------------------------------------:|:--------------:|
| PolicyPlatformTypeKey  | Unikatowy klucz typu platformy zasad.        | 20170519       |
| PolicyPlatformTypeId   | Unikatowy identyfikator typu platformy zasad. | 1              |
| PolicyPlatformTypeName | Nazwa typu platformy zasad.              | AndroidForWork |

## <a name="policytypeactivities"></a>policyTypeActivities
Jednostka **PolicyTypeActivity** zawiera łączną liczbę urządzeń w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd. Zawiera listę tych stanów w odniesieniu do profilu konfiguracji urządzeń, profilu konfiguracji aplikacji lub zasad zgodności na dzień.

|    Właściwość   |                                          Opis                                          |           Przykład           |
|:-------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| DateKey       | Klucz daty zarejestrowania zaewidencjonowania profilu konfiguracji urządzeń w magazynie danych. | 20160703                    |
| PolicyKey     | Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName.                                | Plan bazowy systemu Windows 10         |
| PolicyTypeKey | Typ klucza zasad; można go połączyć z typem zasad w celu otrzymania nazwy typu zasad.             | Zasady zgodności systemu Windows 10 |
| Oczekiwanie       | Liczba unikatowych urządzeń w stanie Oczekiwanie.                                                    | 123                         |
| Sukces     | Liczba unikatowych urządzeń w stanie Sukces.                                                    | 12                          |
| Error         | Liczba unikatowych urządzeń w stanie Błąd.                                                      | 10                          |
| Niepowodzenie        | Liczba unikatowych urządzeń w stanie Niepowodzenie.                                                     | 2                           |

## <a name="policytypes"></a>policyTypes
Jednostka **PolicyType** zawiera listę typów konfiguracji urządzeń, profilów konfiguracji aplikacji i zasad zgodności. Za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM) możesz przypisać zasady grupie w przedsiębiorstwie.

|    Właściwość    |                       Opis                      |            Przykład            |
|:--------------:|:------------------------------------------------------:|:-----------------------------:|
| PolicyTypeId   | Unikatowy identyfikator zasad w systemie źródłowym.  | 123                           |
| PolicyTypeKey  | Unikatowy identyfikator zasad w magazynie danych. | 1                             |
| PolicyTypeName | Nazwa typu zasad.                               | Zasady zgodności systemu Windows 10. |

## <a name="policyuseractivities"></a>policyUserActivities
Poniższa tabela zawiera liczbę użytkowników w stanie Sukces, Oczekiwanie, Niepowodzenie lub Błąd na dzień. Liczba odzwierciedla dane dla profilów typów zasad. Jeśli na przykład użytkownik jest w stanie Sukces dla wszystkich przypisanych mu zasad, zwiększa to w danym dniu licznik powodzeń o 1. Jeśli do użytkownika są przypisane dwa profile, jeden w stanie Sukces i drugi w stanie Błąd, uwzględniany jest użytkownik w stanie Błąd. Jednostka **PolicyUserActivity** przedstawia liczbę użytkowników w określonym stanie w danym dniu z 30 ostatnich dni.

|  Właściwość |                                          Opis                                          |       Przykład       |
|:---------:|:---------------------------------------------------------------------------------------------:|:-------------------:|
| DateKey   | Klucz daty zaewidencjonowania profilu konfiguracji urządzeń w magazynie danych. | 20160703            |
| Oczekiwanie   | Liczba unikatowych urządzeń w stanie Oczekiwanie.                                                    | 123                 |
| Sukces | Liczba unikatowych urządzeń w stanie Sukces.                                                    | 12                  |
| PolicyKey | Klucz zasad; można go połączyć z zasadami w celu otrzymania jednostki policyName.                                | Plan bazowy systemu Windows 10 |
| Error     | Liczba unikatowych urządzeń w stanie Błąd.                                                      | 10                  |

## <a name="termsandconditions"></a>termsAndConditions
Jednostka **termsAndConditions** reprezentuje metadane i zawartość danych warunków i postanowień. Zawartość zasad warunków i postanowień jest przedstawiana użytkownikom przy pierwszej próbie zarejestrowania w usłudze Intune, a następnie po edycjach, jeśli administrator wymaga ponownej akceptacji. Umożliwia ona administratorom informowanie o warunkach, na które użytkownik musi wyrazić zgodę, aby urządzenia zostały zarejestrowane w usłudze Intune.

|    Właściwość        |    Opis    |    Przykład        |
|----------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------|
|    termsAndConditionsKey    |    Klucz odpowiadający wpisowi w kolekcji „userTermsAndConditionsAcceptances”    |    123    |
|    termsAndCondidionsId    |    Identyfikator danego wpisu termsAndConditions    |    276edcb7-7440-4339-b6c5-8b6fc556fee6    |
|    termsAndConditionsVersion    |    Wersja danego wpisu warunków i postanowień.    |    1    |
|    name    |    Nazwa danego wpisu warunków i postanowień.        |    Warunki użytkowania usługi Intune     |
|    description    |    Opis danych warunków i postanowień.     |         |
|    title    |    Tytuł danych warunków i postanowień.     |    Firmowe zasady zarządzania urządzeniami        |
|    summaryOfTerms    |    Podsumowanie warunków przekazanych użytkownikowi.     |    Akceptuję warunki i postanowienia.    |
|    termsAndConditionsBodyText    |    Treść danych warunków i postanowień.       |    *Szyfrowanie urządzenia* Wymuszanie 6-cyfrowego numeru PIN    |
|    isDeleted    |    Wartość True lub False wskazująca, czy wartość została usunięta.     |    Fałsz    |
|    startDateInclusiveUTC    |    Data rozpoczęcia obowiązywania warunków i postanowień.     |    23.08.2018 4:01:34    |
|    endDateEclusiveUTC    |    Data zakończenia obowiązywania warunków i postanowień.     |    31.12.9999 0:00:00    |

## <a name="userdeviceassociations"></a>userDeviceAssociations
Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji.

|        Nazwa        |                                             Opis                                            |     Przykład     |
|:------------------:|:--------------------------------------------------------------------------------------------------:|:---------------:|
| UserKey            | Unikatowy identyfikator użytkownika w magazynie danych.   (Klucz zastępczy).                            | 123             |
| DeviceKey          | Unikatowy identyfikator urządzenia w magazynie danych.                                             | 123             |
| CreatedDateTimeUTC | Data i godzina utworzenia skojarzenia urządzenia użytkownika. w formacie UTC.                     | 23.11.2016 0:00 |
| IsDeleted          | Wskazuje, że użytkownik wyrejestrował urządzenie i skojarzenie nie jest już aktualne. | Prawda/Fałsz      |
| EndedDateTimeUTC   | Data i godzina w formacie UTC zmiany właściwości IsDeleted na wartość True.                                               | 23.06.2017 0:00  |

## <a name="users"></a>użytkownicy
Jednostka **user** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami.

Kolekcja jednostek **user** zawiera dane użytkowników. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych z poprzedniego miesiąca. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

|          Właściwość          |                                                                                                           Opis                                                                                                          |                Przykład               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | Unikatowy identyfikator użytkownika w magazynie danych — klucz zastępczy.                                                                                                                                                         | 123                                  |
| UserId                     | Unikatowy identyfikator użytkownika — podobny do UserKey, ale jest kluczem naturalnym.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | Adres e-mail użytkownika.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Główna nazwa użytkownika.                                                                                                                                                                                               | John@constoso.com                    |
| Nazwa wyświetlana                | Nazwa wyświetlana użytkownika.                                                                                                                                                                                                      | Michał                                 |
| IntuneLicensed             | Określa, czy użytkownik ma licencję usługi Intune, czy nie.                                                                                                                                                                              | True/False                           |
| IsDeleted                  | Wskazuje, czy wszystkie licencje użytkownika wygasły i czy użytkownik został z tego powodu usunięty z usługi Intune. Dla pojedynczego rekordu ta flaga nie zmienia się. Zamiast tego tworzony jest nowy rekord odpowiadający nowemu stanowi użytkownika. | Prawda/Fałsz                           |
| RowLastModifiedDateTimeUTC | Data i godzina ostatniej modyfikacji rekordu w magazynie danych w formacie UTC                                                                                                                                                 | 23.11.2016 0:00                      |

## <a name="usertermsandconditionsacceptances"></a>userTermsAndConditionsAcceptances
Jednostka **userTermsAndConditionsAcceptance** reprezentuje stan akceptacji danych zasad warunków i postanowień przez danego użytkownika. Użytkownicy muszą zaakceptować najnowszą wersję warunków, aby zachować dostęp do aplikacji Portal firmy.

|    Właściwość    |    Opis    |    Przykład    |
|-------------------------------|--------------------------------------------------------------------------------|----------------------------|
|    dateKey    |    Klucz odpowiadający wartościom dat w kolekcji „dates”.     |    20180823    |
|    userKey    |    Mapowanie klucza użytkownika na użytkownika w kolekcji „users”.     |    20000    |
|    termsAndConditionsKey    |    Klucz odpowiadający wpisowi w kolekcji „termsAndConditions”    |    1    |
|    acceptedDateTimeUTC    |    Czas zaakceptowania danych warunków i postanowień przez użytkownika    |    23.08.2018 4:01:34    |
|    lastModifiedDateTimeUTC    |    Czas ostatniej modyfikacji tego wpisu.     |    23.08.2018 4:01:34    |

## <a name="vppprogramtypes"></a>vppProgramTypes 
Jednostka **vppProgramType** zawiera listę możliwych typów programów VPP dla aplikacji.

|      Właściwość      |          Opis         |
|:------------------:|:----------------------------:|
| VppProgramTypeID   | Identyfikator typu.           |
| VppProgramTypeKey  | Klucz zastępczy klucza. |
| VppProgramTypeName | Typ programu VPP.          |

### <a name="example"></a>Przykład

|             VppProgramID             |         Nazwa        | Opis                |
|:------------------------------------:|:-------------------:|----------------------------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft           | Program VPP firmy Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Jeszcze niedostępne | Wartość domyślna: No VPP (Brak VPP).   |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple               | Program VPP firmy Apple.     |

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji o magazynie danych usługi Intune, zobacz [Model danych magazynu danych](https://docs.microsoft.com/intune/reports-ref-data-model).

