---
title: Łącznik Pradeo Mobile Threat Defense z usługą Intune
titleSuffix: Intune on Azure
description: Skonfiguruj łącznik usługi Pradeo Mobile Threat Defense z usługą Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cde4d389-1770-4226-85a3-a2f3b3fb92a3
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 980138015cdbe063d6d4b05eb6dd8ab70be4b601
ms.sourcegitcommit: 84c79ceea27f7411528defc5ee8ba35ae2bf473c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67512240"
---
# <a name="pradeo-mobile-threat-defense-connector-with-intune"></a>Łącznik Pradeo Mobile Threat Defense z usługą Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Pradeo — rozwiązania usługi Mobile Threat Defense (MTD) zintegrowanego z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną aplikacją Pradeo.

Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Pradeo włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-pradeo-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i program Pradeo ułatwiają ochronę zasobów firmy?

Aplikacja Pradeo dla systemów Android i iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Pradeo w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Pradeo Mobile Threat Defense, która jest oparta na ocenie ryzyka Pradeo. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone. Jeśli okaże się, że urządzenie nie jest zgodne, użytkownikom zostanie zablokowany dostęp do takich zasobów firmowych jak usługa Exchange Online lub SharePoint Online. Użytkownicy otrzymają wskazówki z aplikacji Pradeo zainstalowanej na ich urządzeniach dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono kilka typowych scenariuszy.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji

Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach następujące akcje do czasu usunięcia zagrożenia:

-   Łączenie z firmową pocztą e-mail

-   Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy

-   Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Koncepcyjny obraz przedstawiający wykrycie złośliwych aplikacji](./media/pradeo_maliciousapps_blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu po wykryciu złośliwych aplikacji](./media/pradeo_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/pradeo_network_wifi_blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Koncepcyjny obraz przedstawiający dostęp udzielany po skorygowaniu](./media/pradeo_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu **Man-in-the-middle** i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/pradeo_network_spo_blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Koncepcyjny obraz przedstawiający dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](./media/pradeo_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Obsługiwane platformy

-   **System Android 4.0.3 i nowsze**

-   **System iOS 7 i nowsze**

## <a name="prerequisites"></a>Wymagania wstępne

-   Azure Active Directory Premium

-   Subskrypcja usługi Microsoft Intune

-   Subskrypcja usługi Pradeo Security for Mobile Threat Defense

    -   Aby uzyskać więcej informacji, zobacz [witrynę internetową Pradeo](https://www.pradeo.com/en-US/mobile-threat-protection).

## <a name="next-steps"></a>Następne kroki

- [Integracja usługi Pradeo z usługą Intune](pradeo-mtd-connector-integration.md)

- [Konfiguracja aplikacji Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Tworzenie zasad zgodności urządzenia Pradeo](mtd-device-compliance-policy-create.md)

- [Włączanie łącznika Pradeo MTD](mtd-connector-enable.md)
