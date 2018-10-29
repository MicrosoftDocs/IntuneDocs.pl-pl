---
title: Punkt końcowy interfejsu API magazynu danych usługi Intune
titlesuffix: Microsoft Intune
description: Temat referencyjny opisujący strukturę adresu URL interfejsu API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d552ec61d148d0489dc263405eac52448c10f9ef
ms.sourcegitcommit: 24d9ae0396ca410f72cc061a3c4c402835ef32a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2018
ms.locfileid: "49642909"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Punkt końcowy interfejsu API magazynu danych usługi Intune

Możesz korzystać z interfejsu API magazynu danych usługi Intune przy użyciu konta z kontrolą dostępu opartej na określonych rolach oraz przy użyciu poświadczeń usługi Azure AD. Następnie należy autoryzować klienta REST w usłudze Azure AD przy użyciu protokołu OAuth 2.0. I wreszcie należy utworzyć opisowy adres URL do wywołania zasobu magazynu danych.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

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
| entity-collection | daty | Nazwa kolekcji jednostek usługi OData. Aby uzyskać więcej informacji na temat kolekcji i jednostek w modelu danych, zobacz [Model danych](reports-ref-data-model.md). |
| api-version | beta | Wersja interfejsu API, do którego chcesz uzyskać dostęp. Aby uzyskać więcej informacji, zobacz [Wersja](#API-version-information). |
| maxhistorydays | 7 | (Opcjonalnie) Maksymalna liczba dni historii do pobrania. Ten parametr można podać dla każdej kolekcji, ale zostanie on zastosowany tylko do tych kolekcji, które zawierają ciąg `dateKey` jako część właściwości klucza. Aby uzyskać więcej informacji, zobacz [Filtry zakresów DateKey](reports-api-url.md#datekey-range-filters). |

## <a name="api-version-information"></a>Informacje o wersji interfejsu API

Bieżąca wersja interfejsu API to: `beta`. 

## <a name="odata-query-options"></a>Opcje zapytania OData

Bieżąca wersja obsługuje następujące parametry zapytania OData: `$filter, $orderby, $select, $skip,` i `$top`.

## <a name="datekey-range-filters"></a>Filtry zakresów DateKey

Filtry zakresów `DateKey` pozwalają ograniczyć ilość danych do pobrania dla niektórych kolekcji z właściwością klucza `dateKey`. Filtru `DateKey` można użyć, aby zoptymalizować wydajność usługi, podając następujący parametr zapytania `$filter`:

1.  Tylko filtr `DateKey` w parametrze `$filter` obsługujący operatory `lt/le/eq/ge/gt` i dołączany do operatora logicznego `and`, gdzie mogą być one zamapowane na datę rozpoczęcia i/lub datę zakończenia.
2.  Parametr `maxhistorydays` jest udostępniany jako niestandardowa opcja zapytania.<br>

## <a name="filter-examples"></a>Przykłady filtrów

> [!NOTE]
> Przykłady filtrów zakładają, że dzisiejsza data to 21/02/2018.

|                             Filtr                             |           Optymalizacja wydajności           |                                          Opis                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Pełne                                      |    Zwraca dane o wartości `DateKey` z zakresu od 20180214 do 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Pełne                                      |    Zwraca dane o wartości `DateKey` równej 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Pełne                                      |    Zwraca dane o wartości `DateKey` z zakresu od 20180214 do 20180220.                                     |
|    `maxhistorydays=7&$filter=Id gt 1`                            |    Częściowe, identyfikator większy niż 1 nie będzie optymalizowany    |    Zwraca dane o wartości `DateKey` z zakresu od 20180214 do 20180221 i z identyfikatorem większym niż 1.             |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Pełne                                      |    Zwraca dane o wartości `DateKey` równej 20180214. Parametr `maxhistorydays` jest ignorowany.                            |
|    `$filter=DateKey eq 20180214 and Id gt 1`                     |    Brak                                      |    Nie jest traktowane jako filtr zakresu `DateKey`, w związku z czym nie zwiększa wydajności.                              |
|    `$filter=DateKey ne 20180214`                                 |    Brak                                      |    Nie jest traktowane jako filtr zakresu `DateKey`, w związku z czym nie zwiększa wydajności.                              |
|    `maxhistorydays=7&$filter=DateKey eq 20180214 and Id gt 1`    |    Brak                                      |    Nie jest traktowane jako filtr zakresu `DateKey`, w związku z czym nie zwiększa wydajności. Parametr `maxhistorydays` jest ignorowany.    |
