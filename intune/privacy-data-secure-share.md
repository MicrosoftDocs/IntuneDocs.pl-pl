---
title: Zabezpieczanie i udostępnianie danych w usłudze Intune
description: Informacje o tym, w jaki sposób dane osobowe są zabezpieczane i udostępniane w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 68921fd6-5f50-456c-a3af-83d7bc4b134b
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c7e9fe1b0b54d020c3b3a4368922d570c64ae8ee
ms.sourcegitcommit: 7c41f42d6e398ed46aa602ec8aaa4f39aaf92772
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2019
ms.locfileid: "54325036"
---
# <a name="data-security-and-sharing-in-intune"></a>Zabezpieczanie i udostępnianie danych w usłudze Intune


## <a name="data-security"></a>Bezpieczeństwo danych

Usługa Microsoft Intune jest kluczowym składnikiem oferty usług w chmurze Microsoft Enterprise Mobility and Security Suite. W celu zapewnienia obsługi [strategii zarządzania danymi](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) wszystkie usługi firmy Microsoft w chmurze są opracowywane przy użyciu metodologii [Prywatność firmy Microsoft](https://www.microsoft.com/en-us/trustcenter/privacy) i [Zabezpieczenia firmy Microsoft](https://www.microsoft.com/en-us/trustcenter/security/).  

W przypadku usługi Microsoft Intune są stosowane te same środki techniczne i organizacyjne, które zespoły platformy Microsoft Azure stosują w celu zabezpieczenia przed procesami naruszenia danych.

Aby uzyskać więcej informacji, zobacz [Portal zaufania usług](https://www.microsoft.com/en-us/TrustCenter/stp).

Usługa Intune używa technik minimalizacji danych, takich jak:

- Agregacja
- Opcjonalne zbieranie danych w przypadku niektórych funkcji
- Zmniejszanie dokładności lub poufności danych

Usługa Intune używa również technik takich jak kontrola dostępu na podstawie ról i zabezpieczenia JiT w przypadku zdarzeń obsługi technicznej w celu zapewnienia domyślnej ochrony danych. 

### <a name="data-breach-reporting"></a>Raportowanie naruszenia ochrony danych

Jeśli zdarzenie związane z bezpieczeństwem wymagające zgłoszenia klientowi zostanie zidentyfikowane, klienci są o tym powiadamiani. Proces ten obejmuje współpracę z zespołem usługi Microsoft O365 w celu przekazywania powiadomień o naruszeniach zabezpieczeń wszystkim klientom usługi Microsoft O365, którzy używają usługi Intune.

## <a name="data-sharing"></a>Udostępnianie danych

Gdy administrator dzierżawy włączy określone funkcje (na przykład program Device Enrollment Program firmy Apple), usługa Microsoft Intune uzyskuje zgodę administratora na udostępnienie danych odpowiednim stronom trzecim. W takich przypadkach usługa Intune może udostępniać dane osobowe następującym podmiotom:

- Inne firmy działające jako agenci firmy Microsoft.
- Inne firmy niedziałające jako agenci firmy Microsoft, ale tylko wtedy, gdy administratorzy dzierżawy jawnie udzielą odpowiednich uprawnień usłudze Intune.

Wszystkie inne firmy działające jako agenci firmy Microsoft znajdują się na [liście podwykonawców usług online](https://aka.ms/Online_Serv_Subcontractor_List).

Udostępnianie danych takim jednostkom ma na celu wsparcie obsługi klienta i pomocy technicznej, pomoc w konserwacji usługi oraz w innych operacjach.

Umowa dzierżawy z inną firmą określa, jakie dane osobowe usługi Intune są przechowywane w usłudze tej innej firmy. Daje również usłudze Intune uprawnienia do przesyłania danych do usługi innej firmy.  

Aby zapoznać się z informacjami na temat danych udostępnianych określonym innym firmom, zobacz następujące artykuły:
- [Dane wysyłane przez usługę Intune do firmy Apple](data-intune-sends-to-apple.md)
- [Dane wysyłane przez usługę Intune do firmy Google](data-intune-sends-to-google.md)
- [Dane wysyłane do usługi Intune przez firmę Apple](data-apple-sends-to-intune.md)
- [Dane wysyłane do usługi Intune przez firmę Google](data-google-sends-to-intune.md)
- [Dane wysyłane do usługi Intune przez narzędzie Jamf Pro](data-jamf-sends-to-intune.md)

### <a name="system-center-configuration-manager-data-sharing"></a>Udostępnianie danych programowi System Center Configuration Manager

Usługa Microsoft Intune nie udostępnia żadnych danych programowi System Center Configuration Manager. System Center Configuration Manager jest produktem lokalnym, który jest wdrażany, zarządzany i obsługiwany bezpośrednio przez klienta. Dane diagnostyczne i dane użycia zbierane przez program Configuration Manager są wykorzystywane wyłącznie w celu ulepszenia procesu instalacji, jakości i bezpieczeństwa przyszłych wersji.

Aby dowiedzieć się więcej, zobacz [Dane diagnostyczne i użycia dla programu SCCM](https://docs.microsoft.com/sccm/core/plan-design/diagnostics/diagnostics-and-usage-data.md). 


## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak [wyświetlać i poprawiać](privacy-data-view-correct.md) dane osobowe w usłudze Intune.
