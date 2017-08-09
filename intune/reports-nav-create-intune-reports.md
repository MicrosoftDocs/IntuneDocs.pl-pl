---
title: "Korzystanie z magazynu danych usługi Intune | Microsoft Docs"
description: "Przy użyciu magazynu danych usługi Intune możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2017
---
# <a name="use-the-intune-data-warehouse"></a>Korzystanie z magazynu danych usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Przy użyciu magazynu danych usługi Intune możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa. Na przykład niektóre raporty zawierają następujące informacje:
-   Trendy rejestracji użytkowników w usłudze Intune w celu zoptymalizowania zakupu licencji
-   Podział na wersje aplikacji i systemów operacyjnych w celu przejrzenia stanu urządzeń przenośnych
-   Trendy rejestracji i zgodności urządzeń w celu bezproblemowego wdrożenia aktualizacji zasad

Magazyn danych zapewnia dostęp do większej ilości informacji o środowisku mobilnym niż witryna Azure Portal. Dzięki magazynowi danych usługi Intune możesz uzyskać dostęp do następujących elementów:

  -  Dane historyczne usługi Intune
  -  Dane odświeżane codziennie
  -  Model danych korzystający ze standardu OData

> [!Important]  
> Możesz zapoznać się z najnowszymi funkcjami magazynu danych, korzystając z wersji beta. Aby skorzystać z wersji beta, adres URL musi zawierać parametr zapytania `api-version=beta`. Wersja beta umożliwia korzystanie z funkcji jeszcze przed ich ogólnym udostępnieniem jako obsługiwana usługa. W miarę dodawania nowych funkcji do usługi Intune zachowanie wersji beta i kontrakty danych mogą ulec zmianie. Każdy kod niestandardowy lub narzędzia raportowania zależne od wersji beta mogą przestać działać po zainstalowaniu aktualizacji. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Następne kroki**

- Uzyskaj link i uzyskaj wgląd przy użyciu usługi Power BI. Aby uzyskać instrukcje, zobacz [Nawiązywanie połączenia z magazynem danych usługi Intune przy użyciu usługi Power BI](reports-proc-get-a-link-powerbi.md).
- Uzyskaj więcej informacji o interfejsie API magazynu danych usługi Intune, modelu danych i relacjach między jednostkami<!-- , and an example of creating a custom client to retrieve data,--> — zobacz [Interfejs API magazynu danych usługi Intune](reports-nav-intune-date-warehouse.md).