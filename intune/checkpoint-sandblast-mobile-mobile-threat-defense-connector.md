---
title: "Łącznik aplikacji mobilnej Check Point SandBlast Mobile z usługą Intune"
titlesuffix: Azure portal
description: "Integracja rozwiązania Check Point SandBlast z usługą Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09a8914be00b7af039257fe0759967b7f5a90c5e
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2018
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Łącznik rozwiązania Check Point SandBlast Mobile Threat Defense z usługą Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Check Point SandBlast Mobile. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną aplikacją Check Point SandBlast Mobile.

Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Check Point SandBlast Mobile włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i program Check Point SandBlast Mobile ułatwiają ochronę zasobów firmy?

Aplikacja Check Point SandBlast Mobile dla systemu Android i iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Check Point SandBlast w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Check Point SandBlast Mobile Threat Defense, która jest oparta na ocenie ryzyka Check Point SandBlast. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone. Jeśli okaże się, że urządzenie nie jest zgodne, użytkownikom zostanie zablokowany dostęp do takich zasobów firmowych jak usługa Exchange Online lub SharePoint Online. Użytkownicy otrzymają wskazówki z aplikacji mobilnej Check Point SandBlast zainstalowanej na ich urządzeniach dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Check Point MTD block when malicious apps are detected](./media/checkpoint-MTD-2.PNG)

**Access granted on remediation:**

![Check Point MTD access granted](./media/checkpoint-MTD-3.PNG)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Check Point MTD block network access through Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Access granted on remediation:**

![Check Point MTD Wi-Fi access granted](./media/checkpoint-MTD-5.PNG)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Check Point MTD block SharePoint Online access](./media/checkpoint-MTD-6.PNG)

**Access granted on remediation:**

![Check Point MTD SharePoint Online access granted](./media/checkpoint-MTD-7.PNG)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
    -   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

- [Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)

- [Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)
