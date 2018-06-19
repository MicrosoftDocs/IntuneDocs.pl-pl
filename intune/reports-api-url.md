---
title: Punkt końcowy interfejsu API magazynu danych usługi Intune
titlesuffix: Microsoft Intune
description: Temat referencyjny opisujący strukturę adresu URL interfejsu API magazynu danych usługi Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f99ce2ae7937fe0b90353037e72f453a703dd8c
ms.sourcegitcommit: 49dc405bb26270392ac010d4729ec88dfe1b68e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2018
ms.locfileid: "34224232"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Punkt końcowy interfejsu API magazynu danych usługi Intune

Możesz korzystać z interfejsu API magazynu danych usługi Intune przy użyciu konta z kontrolą dostępu opartej na określonych rolach oraz przy użyciu poświadczeń usługi Azure AD. Następnie należy autoryzować klienta REST w usłudze Azure AD przy użyciu protokołu OAuth 2.0. I wreszcie należy utworzyć opisowy adres URL do wywołania zasobu magazynu danych.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autoryzacja

Przy użyciu protokołu OAuth 2.0 usługa Azure Active Directory (Azure AD) umożliwia autoryzację dostępu do aplikacji internetowych i internetowych interfejsów API w dzierżawie usługi Azure AD. Ten przewodnik jest niezależny od języka i opisano w nim, jak wysyłać oraz odbierać komunikaty HTTP bez użycia jakichkolwiek bibliotek typu open-source. Przepływ kodu autoryzacji OAuth 2.0 opisano w [sekcji 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) specyfikacji protokołu OAuth 2.0.

Aby uzyskać więcej informacji, zobacz [Autoryzacja dostępu do aplikacji sieci Web przy użyciu protokołu OAuth 2.0 i usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Struktura adresu URL interfejsu API

Punkty końcowe interfejsu API magazynu danych odczytują jednostki dla każdego zestawu. Interfejs API obsługuje czasownik HTTP **GET** i podzestaw opcji zapytania.

Adres URL dla usługi Intune ma następujący format:  
`https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}`

Adres URL zawiera następujące elementy:

| Element | Przykład | Opis |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Bazowy adres URL można znaleźć, wyświetlając blok interfejsu API magazynu danych w witrynie Azure Portal. |
| entity-collection | daty | Nazwa kolekcji jednostek usługi OData. Aby uzyskać więcej informacji na temat kolekcji i jednostek w modelu danych, zobacz [Model danych](reports-ref-data-model.md). |
| api-version | beta | Wersja interfejsu API, do którego chcesz uzyskać dostęp. Aby uzyskać więcej informacji, zobacz [Wersja](#API-version-information). |


## <a name="api-version-information"></a>Informacje o wersji interfejsu API

Bieżąca wersja interfejsu API to: `beta`. 

## <a name="odata-query-options"></a>Opcje zapytania OData

Bieżąca wersja obsługuje następujące parametry zapytania OData: `$filter, $orderby, $select, $skip,` i `$top`.
