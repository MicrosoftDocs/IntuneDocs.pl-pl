---
title: Używanie usługi Sophos Mobile z usługą Intune
titleSuffix: Intune on Azure
description: Sposób używania rozwiązania Sophos Mobile w usłudze Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f41d5d1ec3e302a277fe5e6ff6af9d33a7e89517
ms.sourcegitcommit: d21539e52631c589bfeaa182418390f66672736c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/01/2020
ms.locfileid: "75564921"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Łącznik Sophos Mobile Threat Defense w usłudze Intune
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Sophos Mobile — rozwiązania usługi Mobile Threat Defense (MTD) zintegrowanego z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną aplikacją Sophos Mobile.
Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Sophos Mobile włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i rozwiązanie Sophos Mobile ułatwiają ochronę zasobów firmy?
Aplikacja Sophos Mobile dla systemów Android i iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Sophos Mobile w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.
Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Sophos Mobile Threat Defense, która jest oparta na ocenie ryzyka Sophos Mobile. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone. Jeśli okaże się, że urządzenie nie jest zgodne, użytkownikom zostanie zablokowany dostęp do takich zasobów firmowych jak usługa Exchange Online lub SharePoint Online. Użytkownicy otrzymają z aplikacji Sophos Mobile zainstalowanej na ich urządzeniach wskazówki dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.  

## <a name="sample-scenarios"></a>Przykładowe scenariusze
Poniżej przedstawiono kilka typowych scenariuszy.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji
Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach następujące akcje do czasu usunięcia zagrożenia:
- Łączenie z firmową pocztą e-mail
- Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy
- Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji**:
 
![Koncepcyjny obraz przedstawiający wykrycie złośliwych aplikacji](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Dostęp udzielany po skorygowaniu**:  
![Koncepcyjny obraz przedstawiający dostęp udzielany po skorygowaniu](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci  
Wykrywanie zagrożeń dla sieci, takich jak ataki typu Man-in-the-middle, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.  

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi**:  
![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Dostęp udzielany po skorygowaniu**:   
![Dostęp udzielany po skorygowaniu](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci  
Wykrywanie zagrożeń dla sieci, takich jak ataki typu Man-in-the-middle i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.  

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych**:   
![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Dostęp udzielany po skorygowaniu**:  
![Dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Obsługiwane platformy  
- System Android 5.0 i nowsze
- System iOS 11.0 i nowsze

## <a name="prerequisites"></a>Wymagania wstępne  
- Azure Active Directory Premium
- Subskrypcja usługi Microsoft Intune 
- Subskrypcja usługi Sophos Mobile Threat Defense

Aby uzyskać więcej informacji, zobacz [witrynę internetową Sophos](https://www.sophos.com/en-us/products/mobile-control.aspx).

## <a name="next-steps"></a>Następne kroki  
- [Integracja rozwiązania Sophos z usługą Intune](sophos-mtd-connector-integration.md)
- [Konfiguracja aplikacji Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Tworzenie zasad zgodności urządzenia Sophos](mtd-device-compliance-policy-create.md)
- [Włączanie łącznika Sophos MTD](mtd-connector-enable.md)
