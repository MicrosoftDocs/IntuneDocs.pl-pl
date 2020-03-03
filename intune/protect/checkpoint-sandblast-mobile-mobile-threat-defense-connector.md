---
title: Konfigurowanie usługi Check Point SandBlast MTD
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat integracji usługi Intune z usługą Check Point SandBlast Mobile Threat Defense w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b740ed1e16f60b15991f1aa450e623cd20b62ea
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515139"
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Łącznik rozwiązania Check Point SandBlast Mobile Threat Defense z usługą Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Check Point SandBlast Mobile. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną aplikacją Check Point SandBlast Mobile.

Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Check Point SandBlast Mobile włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i program Check Point SandBlast Mobile ułatwiają ochronę zasobów firmy?

Aplikacja Check Point SandBlast Mobile dla systemu Android i iOS/iPadOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Check Point SandBlast w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Check Point SandBlast Mobile Threat Defense, która jest oparta na ocenie ryzyka Check Point SandBlast. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone. Jeśli okaże się, że urządzenie nie jest zgodne, użytkownikom zostanie zablokowany dostęp do takich zasobów firmowych jak usługa Exchange Online lub SharePoint Online. Użytkownicy otrzymają wskazówki z aplikacji mobilnej Check Point SandBlast zainstalowanej na ich urządzeniach dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

Poniżej przedstawiono kilka typowych scenariuszy:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji

Po wykryciu na urządzeniach złośliwego oprogramowania możesz zablokować na nich następujące funkcje do czasu usunięcia zagrożenia:

- Łączenie z firmową pocztą e-mail

- Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy

- Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Usługa MTD firmy Check Point blokuje dostęp po wykryciu złośliwych aplikacji](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-2.PNG)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu usłudze MTD firmy Check Point](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Usługa MTD firmy Check Point blokuje dostęp do sieci za pośrednictwem sieci Wi-Fi](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-4.PNG)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu Wi-Fi usłudze MTD firmy Check Point](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i blokowanie synchronizacji plików firmowych w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Usługa MTD firmy Check Point blokuje dostęp do usługi SharePoint Online](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-6.PNG)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu usłudze MTD firmy Check Point do usługi SharePoint Online](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-7.PNG)

## <a name="supported-platforms"></a>Obsługiwane platformy

- **Android 4.1 i nowsze**

- **iOS 8 i nowsze**

## <a name="pre-requisites"></a>Wymagania wstępne

- Azure Active Directory Premium

- Subskrypcja usługi Microsoft Intune

- Subskrypcja usługi Check Point SandBlast Mobile Threat Defense
  - Zobacz [witrynę internetową Check Point SandBlast](https://www.checkpoint.com/), aby uzyskać więcej informacji.

## <a name="next-steps"></a>Następne kroki

- [Integracja aplikacji Check Point SandBlast i usługi Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Set up CheckPoint SandBlast Mobile app (Konfiguracja aplikacji Check Point SandBlast Mobile)](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Create CheckPoint SandBlast Mobile device compliance policy (Tworzenie zasad zgodności urządzeń aplikacji CheckPoint SandBlast Mobile)](mtd-device-compliance-policy-create.md)

- [Enable CheckPoint SandBlast Mobile MTD connector (Włączanie łącznika usługi Check Point SandBlast Mobile MTD)](mtd-connector-enable.md)
