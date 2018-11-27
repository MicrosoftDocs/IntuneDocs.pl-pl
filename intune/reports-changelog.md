---
title: Dziennik zmian magazynu danych usługi Intune
titlesuffix: Microsoft Intune
description: Lista zmian w interfejsie API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: dfdbaffeb8872e8b121d138ee0aca0315279e718
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189949"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Dziennik zmian dla interfejsu API magazynu danych usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bądź na bieżąco z aktualizacjami magazynu danych usługi Intune.

## <a name="1808"></a>1808
_Wydanie: sierpień 2018 r._

### <a name="v10-collections"></a>Kolekcje w wersji 1.0  

Teraz można używać wersji 1.0 magazynu danych usługi Intune, ustawiając parametr zapytania `api-version=v1.0`. Aktualizacje kolekcji w magazynie danych są z natury addytywne i nie przerywają działania istniejących scenariuszy.

### <a name="enrollment-failure-collection-released-to-beta"></a>Niepowodzenie rejestracji — kolekcja wydana do wersji beta

Nowa kolekcja `Enrollment Failure` została wydana do wersji beta. Możesz jej użyć, aby zrozumieć, jak działa Twoja rejestracja. W tym celu zapoznaj się z najczęściej występującymi problemami. 


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

 - Dodano jednostkę [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus). Jednostka **MobileAppDeviceUserInstallStatus** reprezentuje stan instalacji aplikacji mobilnej dla danego urządzenia i użytkownika.
 - Dodano jednostkę [**MobileAppInstallStatus**](reports-ref-application.md#mobileappinstallstate). Jednostka **MobileAppInstallState** reprezentuje stan instalacji aplikacji mobilnej po jej przypisaniu do grupy zawierającej urządzenia, użytkowników lub obie te kategorie. 

## <a name="1710"></a>1710
_Wydanie: listopad 2017 r._

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Nowa kolekcja jednostek o nazwie Bieżący użytkownik jest ograniczona do danych aktualnie aktywnych użytkowników <!-- 1544273 -->

Kolekcja jednostek **Users** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami. Te rekordy obejmują stany użytkowników w okresie zbierania danych, nawet jeśli użytkownik został usunięty. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

Z kolei nowa kolekcja jednostek **Bieżący użytkownik** zawiera tylko tych użytkowników, którzy nie zostali usunięci. Kolekcja jednostek **Bieżący użytkownik** zawiera tylko aktualnie aktywnych użytkowników. Aby uzyskać informacje o kolekcji jednostek **bieżącego użytkownika**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Wydanie: październik 2017 r._

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->

Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta. Aby uzyskać więcej informacji, zobacz temat [Skojarzenie urządzenia użytkownika](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nowe jednostki w modelu danych magazynu danych <!-- 1479526 --><!-- -->

 - Dodano jednostkę [**UserDeviceAssociation**](reports-ref-user-device.md). Jednostka **UserDeviceAssociation** zawiera skojarzenia urządzeń użytkowników w organizacji. Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia.  
 - Jednostka, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), dodana. Jednostka **IntuneManagementExtension** zawiera jednostki dla urządzeń przenośnych, które śledzą informacje, takie jak wersja i stan instalacji.

## <a name="next-steps"></a>Następne kroki
 - Dowiedz się, [co nowego w usłudze Intune w każdym tygodniu](whats-new.md). Możesz również sprawdzić informacje o nadchodzących zmianach, ważnych powiadomieniach dotyczących usługi oraz poprzednich wersjach.
 - Zapoznaj się z [blogiem usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
