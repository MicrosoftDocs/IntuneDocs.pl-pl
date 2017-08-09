---
title: "Punkt końcowy interfejsu API magazynu danych usługi Intune | Microsoft Docs"
description: "Temat referencyjny opisujący strukturę adresu URL interfejsu API."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Punkt końcowy interfejsu API magazynu danych usługi Intune

Możesz korzystać z interfejsu API magazynu danych usługi Intune przy użyciu konta z kontrolą dostępu opartej na określonych rolach oraz przy użyciu poświadczeń usługi Azure AD. Następnie należy autoryzować klienta REST w usłudze Azure AD przy użyciu protokołu OAuth 2.0. I wreszcie należy utworzyć opisowy adres URL do wywołania zasobu magazynu danych.

## <a name="azure-ad-and-intune-credential-requirements"></a>Wymagania dotyczące poświadczeń usług Azure AD i Intune

Uwierzytelnianie i autoryzacja są oparte na poświadczeniach usługi Azure AD i kontroli dostępu opartej na rolach (RBAC). Wszyscy administratorzy globalni i administratorzy usługi Intune dla dzierżawy domyślnie mają dostęp do interfejsu API. Przy użyciu ról usługi Intune możesz zapewnić dostęp dla większej liczby użytkowników, dając im dostęp do **zasobu raportowania**.

Wymagania dotyczące dostępu do interfejsu API są następujące:

  -  Licencja usługi Intune musi być przypisana do użytkownika
  -  Użytkownik musi być:
      -  administratorem globalnym usługi Azure AD,
      -  administratorem usługi Intune,
      -  użytkownikiem z dostępem opartym na rolach do zasobu **Raporty**.

## <a name="authorization"></a>Autoryzacja

Przy użyciu protokołu OAuth 2.0 usługa Azure Active Directory (Azure AD) umożliwia autoryzację dostępu do aplikacji internetowych i internetowych interfejsów API w dzierżawie usługi Azure AD. Ten przewodnik jest niezależny od języka i opisano w nim, jak wysyłać oraz odbierać komunikaty HTTP bez użycia jakichkolwiek bibliotek typu open-source. Przepływ kodu autoryzacji OAuth 2.0 opisano w [sekcji 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) specyfikacji protokołu OAuth 2.0.

Aby uzyskać więcej informacji, zobacz [Autoryzacja dostępu do aplikacji sieci Web przy użyciu protokołu OAuth 2.0 i usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Struktura adresu URL interfejsu API

Punkty końcowe interfejsu API magazynu danych odczytują jednostki dla każdego zestawu. Interfejs API obsługuje czasownik HTTP **GET** i podzestaw opcji zapytania.

Adres URL dla usługi Intune ma następujący format:  
https://fef.{***lokalizacja***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***kolekcja-jednostek***}?api-version={***wersja-interfejsu-API***}

Adres URL zawiera następujące elementy:

| Element | Przykład | Opis |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Bazowy adres URL można znaleźć, wyświetlając blok interfejsu API magazynu danych w witrynie Azure Portal. |
| entity-collection | daty | Nazwa kolekcji jednostek usługi OData. Aby uzyskać więcej informacji na temat kolekcji i jednostek w modelu danych, zobacz [Model danych](reports-ref-data-model.md). |
| api-version | beta | Wersja interfejsu API, do którego chcesz uzyskać dostęp. Aby uzyskać więcej informacji, zobacz [Wersja](#API-version-information). |


## <a name="api-version-information"></a>Informacje o wersji interfejsu API

Bieżąca wersja interfejsu API to: `beta`. 

## <a name="odata-query-options"></a>Opcje zapytania OData

Bieżąca wersja obsługuje następujące parametry zapytania OData: `$skip, $top, $filter, $orderby`.