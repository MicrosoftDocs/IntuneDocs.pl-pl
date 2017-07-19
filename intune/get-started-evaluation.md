---
title: "Wprowadzenie do usługi Intune"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Co to jest usługa Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Usługa Microsoft Intune w witrynie Azure Portal](./media/generic-intune-azure.png)

Usługa Microsoft Intune to jedna z najnowszych usług platformy Azure. Oferuje ona narzędzia do zarządzania firmowymi urządzeniami przenośnymi, komputerami i aplikacjami, które są [regularnie aktualizowane](whats-new.md). Oprócz nowoczesnej konsoli platformy Azure usługa Intune umożliwia również używanie konsoli klasycznej. Konsola klasyczna to pierwsza wersja usługi Intune, za pomocą której [zarządzanie komputerami z systemem Windows odbywa się nadal przy użyciu klienta oprogramowania usługi Intune](/intune-classic/deploy-use/pc-management-comparison.md). Portal klasyczny zbudowany na podstawie programu Silverlight jest używany do wykonywania niewielkiej liczby zadań. Wszystkie inne czynności, w tym zarządzanie urządzeniami przenośnymi i aplikacjami, odbywa się w witrynie Azure Portal. W przewodniku z wprowadzeniem przedstawione zostały podstawowe zadania, które należy wykonać w celu pomyślnego używania usługi Intune w witrynie Azure Portal.

![Blok pomocy i obsługi technicznej dostępny w dolnej części listy akcji na lewym pasku bocznym usługi Intune.](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Jakie funkcje zapewnia usługa Intune w witrynie Azure Portal?

W usłudze Intune w witrynie Azure Portal dostępne są następujące funkcje:

* Zintegrowana konsola dla wszystkich składników pakietu [Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security)
* Konsola oparta na języku HTML utworzona zgodnie ze standardami internetowymi, która obsługuje [nowoczesne przeglądarki internetowe](supported-devices-browsers.md)
* [Grupy usługi Azure Active Directory](groups-get-started.md) w celu zapewnienia zgodności wszystkich aplikacji platformy Azure
* Automatyzacja za pośrednictwem [interfejsu API programu Microsoft Graph](intune-graph-apis.md)

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy aktywować konto administratora i konto dzierżawy usługi Intune. W celu utworzenia tych kont możesz zarejestrować się [tutaj](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Aktualni subskrybenci mogą również wykonać te czynności w ramach aktywnej dzierżawy. Upewnij się, że praca odbywa się tylko na urządzeniach testowych.

Upewnij się również, że jesteś administratorem globalnym w swojej organizacji — tylko wtedy możliwe będzie wykonanie wszystkich zadań w przewodniku.
