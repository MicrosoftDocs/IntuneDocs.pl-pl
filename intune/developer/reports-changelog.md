---
title: Dziennik zmian magazynu danych usługi Intune
titleSuffix: Microsoft Intune
description: Ten temat zawiera listę zmian interfejsu API magazynu danych usługi Microsoft Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a1e797f1ed7b0e60d0f9550eaa9e571b8701ca4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733520"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Dziennik zmian dla interfejsu API magazynu danych usługi Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bądź na bieżąco z aktualizacjami magazynu danych usługi Intune.

## <a name="1903-part-2"></a>1903 (część 2)
_Wydanie: kwiecień 2019 r._

### <a name="beta-changes"></a>Zmiany w wersji beta

W poniższej tabeli wymieniono ostatnio usunięte kolekcje oraz kolekcje zastępujące je w magazynie danych usługi Intune.

|    Kolekcja                          |    Zmiana     |    Dodatkowe informacje                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    mobileAppDeviceUserInstallStatus    |    Zostaną usunięte    |    Zamiast tego użyj kolekcji [mobileAppInstallStatusCounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts).                                                                                                                                                                                                                                                                     |
|    enrollmentTypes                     |    Zostaną usunięte    |    Zamiast tego użyj kolekcji [deviceEnrollmentTypes](intune-data-warehouse-collections.md#deviceenrollmenttypes).                                                                                                                                                                                                                                                                                      |
|    mdmStatuses                         |    Zostaną usunięte    |    Zamiast tego użyj kolekcji [complianceStates](intune-data-warehouse-collections.md#compliancestates).                                                                                                                                                                                                                                                                                               |
|    workPlaceJoinStateTypes             |    Zostaną usunięte    |    Zamiast tego użyj właściwości `azureAdRegistered` w kolekcjach [devices](intune-data-warehouse-collections.md#devices) i [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories).                                                                                                                                                                                                             |
|    clientRegistrationStateTypes        |    Zostaną usunięte    |    Zamiast tego użyj kolekcji [deviceRegistrationStates](intune-data-warehouse-collections.md#deviceregistrationstates).                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Zostaną usunięte    |    Zamiast tego użyj kolekcji [users](intune-data-warehouse-collections.md#users).                                                                                                                                                                                                                                                                                                      |
|    MdmDeviceInventoryHistories         |    Zostaną usunięte    |    Wiele właściwości było nadmiarowych, a niektóre można teraz znaleźć w kolekcjach [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) i [devices](intune-data-warehouse-collections.md#devices). Wszelkie właściwości z kolekcji **mdmDeviceInventoryHistories**, których nie ma teraz w tych dwóch kolekcjach, są już niedostępne. Zobacz szczegóły poniżej.    |

Poniższa tabela zawiera listę właściwości poprzednio znajdujących się w kolekcji **mdmDeviceInventoryHistories** oraz wprowadzonych zmian i zastąpień. Wszystkie właściwości z kolekcji **mdmDeviceInventoryHistories**, których nie ma na poniższej liście, zostały usunięte.

|    Poprzednia właściwość                |    Zmiana/zastąpienie                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    cellularTechnology          |    cellularTechnology w kolekcji devices                                     |
|    deviceClientId              |    deviceId w kolekcji devices                                               |
|    deviceManufacturer          |    manufacturer w kolekcji devices                                           |
|    deviceModel                 |    model w kolekcji devices                                                  |
|    deviceName                  |    deviceName w kolekcji devices                                             |
|    deviceOsPlatform            |    deviceTypeKey w kolekcji devices                                          |
|    deviceOsVersion             |    osVersion w kolekcji devicePropertyHistories                              |
|    deviceType                  |    deviceTypeKey w kolekcji devices, z odwołaniem do kolekcji deviceTypes    |
|    encryptionState             |    Właściwość encryptionState w kolekcji devices                           |
|    exchangeActiveSyncId        |    Właściwość easDeviceId w kolekcji devices                               |
|    exchangeDeviceId            |    easDeviceId w kolekcji devices                                            |
|    imei                        |    imei w kolekcji devices                                                   |
|    isSupervised                |    Właściwość isSupervised w kolekcji devices                              |
|    jailBroken                  |    jailBroken w kolekcji devicePropertyHistories                             |
|    meid                        |    Właściwość meid w kolekcji devices                                      |
|    oem                         |    manufacturer w kolekcji devices                                           |
|    osName                      |    deviceTypeKey w kolekcji devices, z odwołaniem do kolekcji deviceTypes    |
|    phoneNumber                 |    phoneNumber w kolekcji devices                                            |
|    platformType                |    model w kolekcji devices                                                  |
|    product                     |    deviceTypeKey w kolekcji devices                                          |
|    productVersion              |    osVersion w kolekcji devicePropertyHistories                              |
|    serialNumber                |    serialNumber w kolekcji devices                                           |
|    storageFree                 |    Właściwość freeStorageSpaceInBytes w kolekcji devices                   |
|    storageTotal                |    Właściwość totalStorageSpaceInBytes w kolekcji devices                |
|    subscriberCarrierNetwork    |    Właściwość subscriberCarrier w kolekcji devices                         |
|    wifimac                     |    wiFiMacAddress w kolekcji devices                                         |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories): 

|    Poprzednia właściwość                  |    Zmiana/zastąpienie                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, z odwołaniem do kolekcji deviceCategories       |
|    certExpirationDate            |    Zostaną usunięte                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime w kolekcji devices                           |
|    deviceTypeKey                 |    deviceTypeKey w kolekcji devices                              |
|    easID                         |    easDeviceId w kolekcji devices                                |
|    enrolledByUser                |    userId w kolekcji devices                                     |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey w kolekcji devices                    |
|    graphDeviceIsCompliant        |    Zostaną usunięte                                                          |
|    graphDeviceIsManaged          |    Zostaną usunięte                                                          |
|    lastContact                   |    lastSyncDateTime w kolekcji devices                           |
|    lastContactNotification       |    Zostaną usunięte                                                          |
|    lastContactWorkplaceJoin      |    Zostaną usunięte                                                          |
|    lastExchangeStatusUtc         |    Zostaną usunięte                                                          |
|    lastModifiedDateTimeUTC       |    Zostaną usunięte                                                          |
|    lastPolicyUpdateUtc           |    Zostaną usunięte                                                          |
|    managementAgentKey            |    managementStateKey                                               |
|    manufacturer                  |    manufacturer w kolekcji devices                               |
|    mdmStatusKey                  |    complianceStateKey, z odwołaniem do kolekcji complianceStates    |
|    model                         |    model w kolekcji devices                                      |
|    osFamily                      |    operatingSystem w kolekcji devices                            |
|    osRevisionNumber              |    osVersion w kolekcji devices                                  |
|    processorArchitecture         |    Zostaną usunięte                                                          |
|    referenceId                   |    azureAdDeviceId w kolekcji devices                            |
|    serialNumber                  |    serialNumber w kolekcji devices                               |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [devices](intune-data-warehouse-collections.md#devices): 

|    Poprzednia właściwość                  |    Zmiana/zastąpienie                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, z odwołaniem do kolekcji deviceCategories       |
|    certExpirationDate            |    Zostaną usunięte                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime                                                 |
|    easId                         |    easDeviceId                                                      |
|    enrolledByUser                |    userId                                                           |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey                                          |
|    graphDeviceIsCompliant        |    Zostaną usunięte                                                          |
|    graphDeviceIsManaged          |    Zostaną usunięte                                                          |
|    lastContact                   |    lastSyncDateTime                                                 |
|    lastContactNotification       |    Zostaną usunięte                                                          |
|    lastContactWorkplaceJoin      |    Zostaną usunięte                                                          |
|    lastExchangeStatusUtc         |    Zostaną usunięte                                                          |
|    lastPolicyUpdateUtc           |    Zostaną usunięte                                                          |
|    mdmStatusKey                  |    complianceStateKey, z odwołaniem do kolekcji complianceStates    |
|    osFamily                      |    operatingSystem                                                  |
|    processorArchitecture         |    Zostaną usunięte                                                          |
|    referenceId                   |    azureAdDeviceId                                                  |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities): 

|    Poprzednia właściwość         |    Zmiana/zastąpienie         |
|-------------------------|-------------------------------|
|    enrollmentTypeKey    |    deviceEnrollmentTypeKey    |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [mamApplications](intune-data-warehouse-collections.md#mamapplications): 

|    Poprzednia właściwość       |    Zmiana/zastąpienie    |
|-----------------------|--------------------------|
|    applicationKey     |    mamApplicationKey     |
|    applicationName    |    mamApplicationName    |
|    applicationId      |    mamApplicationId      |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [mamApplicationInstances](intune-data-warehouse-collections.md#mamapplicationinstances): 

|    Poprzednia właściwość     |    Zmiana/zastąpienie    |
|---------------------|--------------------------|
|    applicationId    |    mamApplicationId      |
|    deviceId         |    mamDeviceId           |
|    deviceType       |    mamDeviceType         |
|    deviceName       |    mamDeviceName         |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [mamCheckins](intune-data-warehouse-collections.md#mamcheckins): 

|    Poprzednia właściwość      |    Zmiana/zastąpienie    |
|----------------------|--------------------------|
|    applicationKey    |    mamApplicationKey     |

W poniższej tabeli wymieniono zmiany właściwości w kolekcji [users](intune-data-warehouse-collections.md#users): 

|    Poprzednia właściwość             |    Zmiana/zastąpienie    |
|-----------------------------|--------------------------|
|    startDateInclusiveUtc    |    Zostaną usunięte               |
|    endDateInclusiveUtc      |    Zostaną usunięte               |
|    isCurrent                |    Zostaną usunięte               |

## <a name="1903"></a>1903
_Wydanie: marzec 2019 r._

### <a name="v10-changes-reflecting-back-to-beta"></a>Zmiany w wersji 1.0 odzwierciedlane wstecznie w wersji beta
Gdy wersja 1.0 zadebiutowała w wydaniu 1808, różniła się pod pewnymi istotnymi względami od wersji beta interfejsu API. W wydaniu 1903 te zmiany zostaną odzwierciedlone z powrotem w wersji beta interfejsu API. Jeśli masz ważne raporty korzystające z wersji beta interfejsu API, zdecydowanie zalecamy przełączenie tych raportów do wersji 1.0 w celu uniknięcia zmian powodujących niezgodności. Aby uzyskać więcej informacji na temat wersji interfejsu API magazynu danych oraz zgodności z poprzednimi wersjami, zobacz [Informacje o wersji interfejsu API](../reports-api-url.md). 

## <a name="1902"></a>1902 
_Wydane w lutym 2019 r._

### <a name="power-bi-compliance-app"></a>Aplikacja Power BI Compliance 

Można uzyskiwać dostęp do magazynu danych usługi Intune w usłudze Power BI Online przy użyciu aplikacji [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Za pomocą tej aplikacji usługi Power BI możesz teraz uzyskiwać dostęp do wstępnie utworzonych raportów i udostępniać je bez żadnej konfiguracji i bez opuszczania przeglądarki internetowej. 

> [!NOTE]
> W aplikacji Intune Compliance można zastosować dwa dodatkowe filtry.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Dodawanie dodatkowych filtrów do aplikacji Intune Compliance
1. Otwórz aplikację [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) w przeglądarce internetowej.
2. Kliknij pozycję **Non-Compliant Devices** (Niezgodne urządzenia) i wybierz pozycję **Non-Compliant** (Niezgodne) w filtrze **complianceStatus**. 
3. Kliknij pozycję **Unknown Devices** (Nieznane urządzenia) i wybierz pozycję **Not Yet Available** (Jeszcze niedostępne) w filtrze **complianceStatus**. 

## <a name="1812"></a>1812 
_Wydanie: grudzień 2018 r._

### <a name="enrollment-activities-collection-released-to-v10"></a>Wydano wersję 1.0 kolekcji działań rejestracji 

Kolekcja działań rejestracji jest teraz dostępna w wersji 1.0. Dzięki tej kolekcji możesz poznać liczbę niepowodzeń rejestracji oraz jej trend w danym środowisku. Aby uzyskać więcej informacji, zobacz [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories) i [enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons).

## <a name="1808"></a>1808
_Wydanie: sierpień 2018 r._

### <a name="v10-collections"></a>Kolekcje w wersji 1.0  

Teraz można używać wersji 1.0 magazynu danych usługi Intune, ustawiając parametr zapytania `api-version=v1.0`. Aktualizacje kolekcji w magazynie danych są z natury addytywne i nie przerywają działania istniejących scenariuszy.

### <a name="enrollment-activities-collection-released-to-beta"></a>Wydano wersję beta kolekcji działań rejestracji

Nowa kolekcja `Enrollment Activities` została wydana do wersji beta. Możesz jej użyć, aby zrozumieć, jak działa Twoja rejestracja. W tym celu zapoznaj się z najczęściej występującymi problemami. 


## <a name="1805"></a>1805
_Wydanie: maj 2018 r._

### <a name="correction-to-device-count-in-devices-collection"></a>Korekta liczby urządzeń w kolekcji **Urządzenia** 

W kolekcji **Urządzenia** wprowadzono poprawkę, która może obniżyć całkowitą liczbę urządzeń filtrowanych przy użyciu atrybutu `isDeleted`. Ten spadek to wynik wprowadzenia korekty — to nie jest błąd. Aby uzyskać więcej informacji dotyczących kolekcji **Urządzenia**, zobacz [Dokumentacja jednostek zasad](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Wydanie: styczeń 2018 r._

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Uwierzytelnianie tylko aplikacji w magazynie danych usługi Intune <!-- 1867540 -->

Aplikację można skonfigurować przy użyciu usługi Azure Active Directory (Azure AD) i uwierzytelnić w magazynie danych usługi Intune. Aby uzyskać więcej informacji, zobacz [Uwierzytelnianie tylko aplikacji w magazynie danych usługi Intune](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Wymagania dotyczące poświadczeń usług Azure AD i Intune <!-- 2077525 -->

- Licencja usługi Intune nie musi już być przypisana do użytkownika podczas uzyskiwania dostępu do magazynu danych usługi Intune (dotyczy to także interfejsu API).
- Nazwa roli usługi Intune została zmieniona z **Raporty** na **Magazyn danych usługi Intune**. 

    Aby uzyskać więcej informacji, zobacz [Wymagania dotyczące poświadczeń usług Azure AD i Intune](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Opcje zapytania OData <!-- 2077711 -->

Parametru <code>$select</code> można użyć jako parametru zapytania OData. Bieżąca wersja obsługuje następujące parametry zapytania OData: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> i <code>$top</code>. Aby uzyskać więcej informacji, zobacz [Opcje zapytania OData](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Nowe jednostki w modelu danych magazynu danych <!-- 2077804 -->

- Dodano jednostkę [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md). Jednostka **MobileAppDeviceUserInstallStatus** reprezentuje stan instalacji aplikacji mobilnej dla danego urządzenia i użytkownika.
- Dodano jednostkę [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstates). Jednostka **MobileAppInstallState** reprezentuje stan instalacji aplikacji mobilnej po jej przypisaniu do grupy zawierającej urządzenia, użytkowników lub obie te kategorie. 

## <a name="1710"></a>1710
_Wydanie: listopad 2017 r._

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Nowa kolekcja jednostek o nazwie Bieżący użytkownik jest ograniczona do danych aktualnie aktywnych użytkowników <!-- 1544273 -->

Kolekcja jednostek **Users** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

Z kolei nowa kolekcja jednostek **Bieżący użytkownik** zawiera tylko tych użytkowników, którzy nie zostali usunięci. Kolekcja jednostek **Bieżący użytkownik** zawiera tylko aktualnie aktywnych użytkowników. Aby uzyskać informacje o kolekcji jednostek **bieżącego użytkownika**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](../reports-ref-current-user.md).

## <a name="1709"></a>1709
_Wydanie: październik 2017 r._

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->

Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta. Aby uzyskać więcej informacji, zobacz temat [Skojarzenie urządzenia użytkownika](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nowe jednostki w modelu danych magazynu danych <!-- 1479526 --><!-- -->

- Dodano jednostkę [**UserDeviceAssociation**](reports-ref-user-device.md). Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji. Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia.  
- Jednostka, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), dodana. Jednostka **IntuneManagementExtension** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje, takie jak wersja i stan instalacji.

## <a name="next-steps"></a>Następne kroki
- Dowiedz się, [co nowego w usłudze Intune w każdym tygodniu](../fundamentals/whats-new.md). Możesz również sprawdzić informacje o nadchodzących zmianach, ważnych powiadomieniach dotyczących usługi oraz poprzednich wersjach.
- Zapoznaj się z [blogiem usługi Microsoft Intune](https://go.microsoft.com/fwlink/?LinkID=273882).