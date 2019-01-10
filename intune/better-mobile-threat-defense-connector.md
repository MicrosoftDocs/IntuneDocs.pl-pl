---
title: Łącznik Better Mobile Threat Defense z usługą Intune
titleSuffix: Intune on Azure
description: Konfigurowanie łącznika Better Mobile Threat Defense z usługą Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.openlocfilehash: 313c20699c30d20d1bbc9bb6aea9189a83b61f53
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816637"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Łącznik Better Mobile Threat Defense z usługą Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Better Mobile — rozwiązania usługi Mobile Threat Defense (MTD) zintegrowanego z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną aplikacją Better Mobile.

Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Better Mobile włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>W jaki sposób usługi Intune i Better Mobile ułatwiają ochronę zasobów firmy?

Aplikacja Better Mobile jest instalowana i działa na urządzeniach przenośnych. Ta aplikacja przechwytuje dane systemu plików, stosu sieci, urządzenia oraz dane telemetryczne aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Better Mobile w chmurze w celu ocenienia ryzyka dotyczącego urządzenia pod kątem zagrożeń urządzeń przenośnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Mobile Threat Defense, która jest oparta na ocenie ryzyka Better Mobile. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone. Jeśli okaże się, że urządzenie nie jest zgodne, użytkownikom zostanie zablokowany dostęp do takich zasobów firmowych jak usługa Exchange Online lub SharePoint Online. Użytkownicy otrzymają z aplikacji Better Mobile zainstalowanej na ich urządzeniach wskazówki dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono kilka typowych scenariuszy.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji

Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach następujące akcje do czasu usunięcia zagrożenia:

-   Łączenie z firmową pocztą e-mail

-   Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy

-   Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Obraz przedstawiający wykrycie złośliwych aplikacji](./media/better_mobile_maliciousapps_blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu po wykryciu złośliwych aplikacji](./media/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/better_mobile_network_wifi_blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Obraz przedstawiający dostęp udzielany po skorygowaniu](./media/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu **Man-in-the-middle** i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/better_mobile_network_spo_blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](./media/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Obsługiwane platformy

-   **Android 4.1 i nowsze**

-   **System iOS 8.0 lub nowszy**

## <a name="prerequisites"></a>Wymagania wstępne

-   Azure Active Directory Premium

-   Subskrypcja usługi Microsoft Intune

-   Subskrypcja usługi Better Mobile Threat Defense

    -   Aby uzyskać więcej informacji, zobacz [witrynę internetową usługi Better Mobile](https://www.better.mobi/).

## <a name="next-steps"></a>Następne kroki

- [Integrowanie usługi Better Mobile z usługą Intune](better-mobile-mtd-connector-integration.md)

- [Konfigurowanie aplikacji usługi Better Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Tworzenie zasad zgodności urządzeń w usłudze Better Mobile](mtd-device-compliance-policy-create.md)

- [Włączanie łącznika MTD usługi Better Mobile](mtd-connector-enable.md)