---
title: Interfejs API magazynu danych usługi Intune
titlesuffix: Microsoft Intune
description: Przy użyciu interfejsu API magazynu danych usługi Intune możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 885487e6c21800742247a3e1e12d07f03aaefd9e
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223734"
---
#  <a name="intune-data-warehouse-api"></a>Interfejs API magazynu danych usługi Intune

Przy użyciu interfejsu API magazynu danych usługi Intune możesz uzyskać dostęp do danych usługi Intune w formacie czytelnym dla komputerów i użyć tych danych w swoim ulubionym narzędziu analitycznym. Przy użyciu interfejsu API możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa. Interfejs API korzysta z protokołu OData, który jest zgodny z wzorcami standardowymi w następujących kwestiach:

  -   Nagłówki żądania i odpowiedzi
  -   Kody stanu
  -   Metody HTTP
  -   Konwencje adresów URL
  -   Typy multimediów
  -   Formaty ładunków
  -   Opcje zapytania

OData (Open Data Protocol) to organizacja zajmująca się rozwojem standardu informacji strukturyzowanych (OASIS, Organization for the Advancement of Structured Information Standards), który definiuje najlepsze rozwiązania w zakresie tworzenia i używania interfejsów API RESTful. Magazyn danych usługi Intune korzysta z protokołu OData w wersji 4.0.

W sekcji informacji referencyjnych można znaleźć przegląd punktów końcowych, obsługiwane metody HTTP, formaty ładunków zwrotnych i dokumentację modelu danych magazynu danych usługi Intune.

> [!Important]  
> Możesz zapoznać się z najnowszymi funkcjami magazynu danych, korzystając z wersji beta. Aby skorzystać z wersji beta, adres URL musi zawierać parametr zapytania `api-version=beta`. Wersja beta umożliwia korzystanie z funkcji jeszcze przed ich ogólnym udostępnieniem jako obsługiwana usługa. W miarę dodawania nowych funkcji do usługi Intune zachowanie wersji beta i kontrakty danych mogą ulec zmianie. Każdy kod niestandardowy lub narzędzia raportowania zależne od wersji beta mogą przestać działać po zainstalowaniu aktualizacji. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

## <a name="odata-custom-client"></a>Klient niestandardowy OData

Dostęp do modelu danych magazynu danych usługi Intune można uzyskać za pośrednictwem punktów końcowych RESTful. Aby uzyskać dostęp do danych, należy autoryzować klienta w usłudze Azure Active Directory (Azure AD) przy użyciu protokołu OAuth 2.0. Najpierw skonfiguruj aplikację internetową i aplikację kliencką na platformie Azure, a następnie udziel uprawnień klientowi. Klient lokalny uzyska autoryzację, a następnie będzie mógł komunikować się z punktami końcowymi magazynu danych.

Aby uzyskać więcej informacji, zobacz [Pobieranie danych z interfejsu API magazynu danych za pomocą klienta REST](reports-proc-data-rest.md)

> [!Note]  
> Przykłady kodu można znaleźć w [repozytorium GitHub magazynu danych usługi Intune](https://github.com/Microsoft/Intune-Data-Warehouse) w usłudze Github.

## <a name="interacting-with-the-api"></a>Interakcja z interfejsem API

Interfejs API wymaga autoryzacji w usłudze Azure AD. Usługa Azure AD korzysta z protokołu OAuth 2.0. Po autoryzacji możesz uzyskać dane z interfejsu API, używając czasownika HTTP GET i kontaktując się z uwidocznionymi kolekcjami jednostek. Aby uzyskać szczegółowe informacje, zobacz:

 -  [Autoryzacja](reports-api-url.md)
 -  [Struktura adresu URL interfejsu API](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Model danych magazynu danych usługi Intune

Usługa OData definiuje abstrakcyjny model danych i protokół, które umożliwiają dowolnemu klientowi uzyskanie dostępu do informacji uwidocznionych przez dowolne źródło danych. Temat w dokumentacji dotyczący modelu danych zawiera wyjaśnienie przestrzeni nazw, jednostek i obiektów zwrotnych w modelu danych magazynu danych usługi Intune. Aby uzyskać więcej informacji, zobacz [Model danych magazynu danych](reports-ref-data-model.md).

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej na temat pracy z usługą Azure AD, czytając artykuł [Scenariusze uwierzytelniania dla usługi Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

Źródła danych OData znajdziesz w witrynie [odata.org](http://www.odata.org).
  
Zapoznaj się ze standardem OData w wersji 4.0 na stronie [OData w wersji 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
