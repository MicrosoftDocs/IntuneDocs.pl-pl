---
title: Łącznik rozwiązania Zimperium MTD w usłudze Intune
titleSuffix: Intune on Azure
description: Dowiedz się więcej na temat integracji usługi Intune z usługą Zimperium Mobile Threat Defense w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 33d4039e430699c5b8e15c1f9b817d8e2a25d029
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728068"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Łącznik rozwiązania Zimperium Mobile Threat Defense z usługą Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować przy użyciu dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną aplikacją Zimperium.

Zasady dostępu warunkowego można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez aplikację Zimperium włączaną przy użyciu zasad zgodności urządzeń usługi Intune. Zasady oceny ryzyka mogą zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i rozwiązanie Zimperium ułatwiają ochronę zasobów firmy?

Aplikacja Zimperium dla systemu Android i iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Zimperium w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Zimperium Mobile Threat Defense, która jest oparta na ocenie ryzyka Zimperium. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone. Jeśli okaże się, że urządzenie nie jest zgodne, użytkownikom zostanie zablokowany dostęp do takich zasobów firmowych jak usługa Exchange Online lub SharePoint Online. Użytkownicy otrzymają wskazówki z aplikacji Zimperium zainstalowanej na ich urządzeniach dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej znajduje się kilka scenariuszy dotyczących integracji rozwiązania Zimperium z usługą Intune:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji

Po wykryciu na urządzeniach złośliwego oprogramowania możesz zablokować na nich następujące funkcje do czasu usunięcia zagrożenia:

- Łączenie z firmową pocztą e-mail

- Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy

- Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Koncepcyjny obraz przedstawiający wykrycie złośliwych aplikacji](./media/zimperium-mobile-threat-defense-connector/Maliciousapps_blocked_Zimperium.png)

**Dostęp udzielany po skorygowaniu:**

![Koncepcyjny obraz przedstawiający dostęp udzielany po skorygowaniu](./media/zimperium-mobile-threat-defense-connector/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/zimperium-mobile-threat-defense-connector/network_wifi_blocked_Zimperium.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu](./media/zimperium-mobile-threat-defense-connector/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i blokowanie synchronizacji plików firmowych w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/zimperium-mobile-threat-defense-connector/network_spo_blocked_Zimperium.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](./media/zimperium-mobile-threat-defense-connector/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Obsługiwane platformy

- **Android 4.1 i nowsze**

- **iOS 8 i nowsze**

## <a name="prerequisites"></a>Wymagania wstępne

- Azure Active Directory Premium

- Subskrypcja usługi Microsoft Intune

- Subskrypcja usługi Zimperium Mobile Threat Defense

  - Aby uzyskać więcej informacji, odwiedź [witrynę internetową Zimperium](https://www.zimperium.com/zips-mobile-ips).

## <a name="next-steps"></a>Następne kroki

- [Integracja rozwiązania Zimperium z usługą Intune](zimperium-mtd-connector-integration.md)

- [Konfigurowanie aplikacji Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Tworzenie zasad zgodności urządzenia usługi Zimperium](mtd-device-compliance-policy-create.md)

- [Włączanie łącznika rozwiązania Zimperium MTD](mtd-connector-enable.md)