---
title: Punkt końcowy interfejsu API magazynu danych usługi Intune
titleSuffix: Microsoft Intune
description: W tym temacie referencyjnym opisano strukturę adresu URL interfejsu API magazynu danych usługi Microsoft Intune. Podano też przykłady filtrów.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f73e80fed5de74bc074e26502270467b7d846e5c
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940142"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Punkt końcowy interfejsu API magazynu danych usługi Intune

Możesz korzystać z interfejsu API magazynu danych usługi Intune przy użyciu konta z kontrolą dostępu opartej na określonych rolach oraz przy użyciu poświadczeń usługi Azure AD. Następnie należy autoryzować klienta REST w usłudze Azure AD przy użyciu protokołu OAuth 2.0. I wreszcie należy utworzyć opisowy adres URL do wywołania zasobu magazynu danych.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autoryzacja

Przy użyciu protokołu OAuth 2.0 usługa Azure Active Directory (Azure AD) umożliwia autoryzację dostępu do aplikacji internetowych i internetowych interfejsów API w dzierżawie usługi Azure AD. Ten przewodnik jest niezależny od języka i opisano w nim, jak wysyłać oraz odbierać komunikaty HTTP bez użycia jakichkolwiek bibliotek typu open-source. Przepływ kodu autoryzacji OAuth 2.0 opisano w [sekcji 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) specyfikacji protokołu OAuth 2.0.

Aby uzyskać więcej informacji, zobacz [Autoryzacja dostępu do aplikacji internetowych przy użyciu protokołu OAuth 2.0 i usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Struktura adresu URL interfejsu API

Punkty końcowe interfejsu API magazynu danych odczytują jednostki dla każdego zestawu. Interfejs API obsługuje czasownik HTTP **GET** i podzestaw opcji zapytania.

Adres URL dla usługi Intune ma następujący format:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> W powyższym adresie URL zastąp ciągi `{location}`, `{entity-collection}` i `{api-version}` na podstawie informacji podanych w poniższej tabeli.

Adres URL zawiera następujące elementy:

| Element | Przykład | Opis |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Bazowy adres URL można znaleźć, wyświetlając blok interfejsu API magazynu danych w witrynie Azure Portal. |
| entity-collection | devicePropertyHistories | Nazwa kolekcji jednostek usługi OData. Aby uzyskać więcej informacji na temat kolekcji i jednostek w modelu danych, zobacz [Model danych](reports-ref-data-model.md). |
| api-version | beta | Wersja interfejsu API, do którego chcesz uzyskać dostęp. Aby uzyskać więcej informacji, zobacz [Wersja](reports-api-url.md#api-version-information). |
| maxhistorydays | 7 | (Opcjonalnie) Maksymalna liczba dni historii do pobrania. Ten parametr można podać dla każdej kolekcji, ale zostanie on zastosowany tylko do tych kolekcji, które zawierają ciąg `dateKey` jako część właściwości klucza. Aby uzyskać więcej informacji, zobacz [Filtry zakresów DateKey](reports-api-url.md#datekey-range-filters). |

## <a name="api-version-information"></a>Informacje o wersji interfejsu API

Teraz można używać wersji 1.0 magazynu danych usługi Intune, ustawiając parametr zapytania  `api-version=v1.0`. Aktualizacje kolekcji w magazynie danych są z natury addytywne i nie przerywają działania istniejących scenariuszy.

Możesz zapoznać się z najnowszymi funkcjami magazynu danych, korzystając z wersji beta. Aby można było korzystać z wersji beta, adres URL musi zawierać parametr zapytania  `api-version=beta`. Wersja beta umożliwia korzystanie z funkcji jeszcze przed ich ogólnym udostępnieniem jako obsługiwana usługa. W miarę dodawania nowych funkcji do usługi Intune zachowanie wersji beta i kontrakty danych mogą ulec zmianie. Każdy kod niestandardowy lub narzędzia raportowania zależne od wersji beta mogą przestać działać po zainstalowaniu aktualizacji.

## <a name="odata-query-options"></a>Opcje zapytania OData

Bieżąca wersja obsługuje następujące parametry zapytania OData: `$filter`, `$select`, `$skip,` i `$top`. W przypadku parametru `$filter` mogą być obsługiwane tylko wartości `DateKey` lub `RowLastModifiedDateTimeUTC`, jeśli te kolumny są dostępne, a wszelkie inne właściwości będą wyzwalać nieprawidłowe żądanie.

## <a name="datekey-range-filters"></a>Filtry zakresów DateKey

Filtry zakresów `DateKey` pozwalają ograniczyć ilość danych do pobrania dla niektórych kolekcji z właściwością klucza `dateKey`. Filtru `DateKey` można użyć, aby zoptymalizować wydajność usługi, podając następujący parametr zapytania `$filter`:

1. Tylko filtr `DateKey` w parametrze `$filter` obsługujący operatory `lt/le/eq/ge/gt` i dołączany do operatora logicznego `and`, gdzie mogą być one zamapowane na datę rozpoczęcia i/lub datę zakończenia.
2. Parametr `maxhistorydays` jest udostępniany jako niestandardowa opcja zapytania.<br>

## <a name="filter-examples"></a>Przykłady filtrów

> [!NOTE]
> Przykłady filtrów zakładają, że dzisiejsza data to 21/02/2019.

|                             Filtr                             |           Optymalizacja wydajności           |                                          Opis                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Pełna                                      |    Zwraca dane o wartości `DateKey` z zakresu od 20180214 do 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Pełna                                      |    Zwraca dane o wartości `DateKey` równej 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Pełna                                      |    Zwraca dane o wartości `DateKey` z zakresu od 20180214 do 20180220.                                     |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Pełna                                      |    Zwraca dane o wartości `DateKey` równej 20180214. Parametr `maxhistorydays` jest ignorowany.                            |
|    `$filter=RowLastModifiedDateTimeUTC ge 2018-02-21T23:18:51.3277273Z`                                |    Pełna                                       |    Zwraca dane o wartości `RowLastModifiedDateTimeUTC` większej lub równej `2018-02-21T23:18:51.3277273Z`.                             |
