---
title: Korzystanie z magazynu danych usługi Intune
titlesuffix: Microsoft Intune
description: Przy użyciu magazynu danych usługi Intune możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3112683d44b7c4d4a3e9d1bccc6fb8c06450600
ms.sourcegitcommit: fdc6261f4ed695986e06d18353c10660a4735362
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2019
ms.locfileid: "58069122"
---
# <a name="use-the-microsoft-intune-data-warehouse"></a>Korzystanie z magazynu danych usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Przy użyciu magazynu danych usługi Intune możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa. Na przykład niektóre raporty zawierają następujące informacje:
-   Trendy rejestracji użytkowników w usłudze Intune w celu zoptymalizowania zakupu licencji
-   Podział na wersje aplikacji i systemów operacyjnych w celu przejrzenia stanu urządzeń przenośnych
-   Trendy rejestracji i zgodności urządzeń w celu bezproblemowego wdrożenia aktualizacji zasad

## <a name="data-warehouse-benefits"></a>Korzyści związane z magazynem danych

Magazyn danych zapewnia dostęp do większej ilości informacji o środowisku mobilnym niż witryna Azure Portal. Dzięki magazynowi danych usługi Intune możesz uzyskać dostęp do następujących elementów:

  -  Dane historyczne usługi Intune
  -  Dane odświeżane codziennie
  -  Model danych korzystający ze standardu OData

> [!Note]
> Jeśli korzystasz ze współzarządzanego zarządzania urządzeniami przenośnymi za pomocą programu System Center Configuration Manager i usługi Microsoft Intune, musisz pobierać dane z programu Configuration Manager. Magazyn danych usługi Intune zawiera tylko dane usługi Intune. Pulpit nawigacyjny usługi Power BI w programie Configuration Manager można użyć dla niestandardowych raportów. Aby uzyskać więcej informacji, zapoznaj się z artykułami „[Announcing the Power BI solution template for System Center Configuration Manager”]( https://powerbi.microsoft.com/blog/sccm-solution-template) („Przedstawiamy szablon rozwiązania Power BI dla programu System Center Configuration Manager”) i „[Power BI content for Dynamics 365](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page)” („Zawartość usługi Power Bi dla usługi Dynamics 365”).

> [!Important]  
> Teraz można używać wersji 1.0 magazynu danych usługi Intune, ustawiając parametr zapytania  `api-version=v1.0`. Aktualizacje kolekcji w magazynie danych są z natury addytywne i nie przerywają działania istniejących scenariuszy.<br><br>
> Możesz zapoznać się z najnowszymi funkcjami magazynu danych, korzystając z wersji beta. Aby można było korzystać z wersji beta, adres URL musi zawierać parametr zapytania  `api-version=beta`. Wersja beta umożliwia korzystanie z funkcji jeszcze przed ich ogólnym udostępnieniem jako obsługiwana usługa. W miarę dodawania nowych funkcji do usługi Intune zachowanie wersji beta i kontrakty danych mogą ulec zmianie. Każdy kod niestandardowy lub narzędzia raportowania zależne od wersji beta mogą przestać działać po zainstalowaniu aktualizacji.

## <a name="next-steps"></a>Następne kroki

- Uzyskaj link i uzyskaj wgląd przy użyciu usługi Power BI. Aby uzyskać instrukcje, zobacz [Nawiązywanie połączenia z magazynem danych usługi Intune przy użyciu usługi Power BI](reports-proc-get-a-link-powerbi.md).
- Za pomocą swojego linku utwórz niestandardowy raport w usłudze Power BI. Aby uzyskać instrukcje, zobacz [Tworzenie raportu w usłudze Power BI na podstawie źródła danych OData](reports-proc-create-with-odata.md).
- Uzyskaj więcej informacji o interfejsie API magazynu danych usługi Intune, modelu danych i relacjach między jednostkami<!-- , and an example of creating a custom client to retrieve data,--> Zobacz artykuł [Interfejs API magazynu danych usługi Intune](reports-nav-intune-data-warehouse.md).
