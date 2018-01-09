---
title: "Korzystanie z magazynu danych usługi Intune | Microsoft Docs"
description: "Przy użyciu magazynu danych usługi Intune możesz tworzyć raporty zapewniające wgląd w środowisko mobilne przedsiębiorstwa."
keywords: "Magazyn danych usługi Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 338536d975ca3810df3c909964ac13b396097db8
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2018
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

> [!Note]
> Jeśli korzystasz z hybrydowego zarządzania urządzeniami przenośnymi za pomocą programu System Center Configuration Manager i usługi Microsoft Intune, musisz pobierać dane z programu SCCM. Magazyn danych usługi Intune zawiera tylko dane usługi Intune. Do tworzenia niestandardowych raportów można używać pulpitu nawigacyjnego usługi Power BI w programie SCCM. Aby uzyskać więcej informacji, zobacz [Announcing the Power BI solution template for System Center Configuration Manager (Przedstawiamy szablon rozwiązania Power BI dla programu System Center Configuration Manager)]( https://powerbi.microsoft.com/blog/sccm-solution-template) i [Create a Power BI report and dashboard (Tworzenie raportu i pulpitu nawigacyjnego usługi Power BI)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard).


> [!Important]  
> Możesz zapoznać się z najnowszymi funkcjami magazynu danych, korzystając z wersji beta. Aby skorzystać z wersji beta, adres URL musi zawierać parametr zapytania `api-version=beta`. Wersja beta umożliwia korzystanie z funkcji jeszcze przed ich ogólnym udostępnieniem jako obsługiwana usługa. W miarę dodawania nowych funkcji do usługi Intune zachowanie wersji beta i kontrakty danych mogą ulec zmianie. Każdy kod niestandardowy lub narzędzia raportowania zależne od wersji beta mogą przestać działać po zainstalowaniu aktualizacji.

**Następne kroki**

- Uzyskaj link i uzyskaj wgląd przy użyciu usługi Power BI. Aby uzyskać instrukcje, zobacz [Nawiązywanie połączenia z magazynem danych usługi Intune przy użyciu usługi Power BI](reports-proc-get-a-link-powerbi.md).
- Za pomocą swojego linku utwórz niestandardowy raport w usłudze Power BI. Aby uzyskać instrukcje, zobacz [Tworzenie raportu w usłudze Power BI na podstawie źródła danych OData](reports-proc-create-with-odata.md).
- Uzyskaj więcej informacji o interfejsie API magazynu danych usługi Intune, modelu danych i relacjach między jednostkami<!-- , and an example of creating a custom client to retrieve data,--> — zobacz [Interfejs API magazynu danych usługi Intune](reports-nav-intune-data-warehouse.md).