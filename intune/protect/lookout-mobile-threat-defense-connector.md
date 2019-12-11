---
title: Łącznik usługi Lookout MTD w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat integracji usługi Intune z usługą Lookout Mobile Threat Defense (MTD) w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0123647fb1e8a1d52506ad0753906f974103aad
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502215"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Łącznik usługi Lookout Mobile Endpoint Security w usłudze Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować dzięki ocenie ryzyka przeprowadzanej przez usługę Lookout — rozwiązaniu usługi Mobile Threat Defense zintegrowanemu z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń przez usługę Lookout. Są to na przykład:
- Luki w zabezpieczeniach systemu operacyjnego
- Zainstalowane złośliwe aplikacje
- Złośliwe profile sieci

W oparciu o ocenę ryzyka przeprowadzaną za pomocą usługi Lookout (włączaną przy użyciu zasad zgodności usługi Intune) można skonfigurować zasady dostępu warunkowego. Za pomocą ustawień można dopuszczać lub blokować niezgodne urządzenia na podstawie wykrytych zagrożeń.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>W jaki sposób usługa Intune i usługa Lookout Mobile Endpoint Security pomagają chronić zasoby firmy?
Aplikacja mobilna usługi Lookout, **Lookout for work**, jest instalowana i działa na urządzeniach przenośnych. Ta aplikacja przechwytuje dane systemu plików, stosu sieci oraz dane telemetryczne urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Lookout w chmurze w celu ocenienia ryzyka dotyczącego urządzenia pod kątem zagrożeń urządzeń przenośnych. Klasyfikację poziomu ryzyka dla zagrożeń można zmienić w konsoli usługi Lookout, aby była zgodna z wymaganiami.  

Zasady zgodności w usłudze Intune zawierają regułę dla usługi Lookout Mobile Threat Defense, która jest oparta na ocenie ryzyka przeprowadzanej przez usługę Lookout. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli się okaże, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do zasobów, takich jak usługa Exchange Online czy SharePoint Online. Użytkownicy korzystający z zablokowanych urządzeń zostaną poinformowani o czynnościach, które należy wykonać w celu rozwiązania problemu i ponownego uzyskania dostępu. Te wskazówki są wyświetlane w aplikacji Lookout for work.

## <a name="supported-platforms"></a>Obsługiwane platformy  
Po zarejestrowaniu w usłudze Intune narzędzie Lookout jest obsługiwane na następujących platformach:
* **Android 4.1 i nowsze**  
* **iOS 8 i nowsze**  

Aby uzyskać dodatkowe informacje o pomocy technicznej dotyczącej platformy i języka, odwiedź [witrynę internetową firmy Lookout](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Wymagania wstępne
* Subskrypcja korporacyjna usługi Lookout Mobile Endpoint Security  
* Subskrypcja usługi Microsoft Intune
* Azure Active Directory Premium
* Pakiet Enterprise Mobility and Security (EMS) E3 lub E5 z licencjami przypisanymi do użytkowników.  

Aby uzyskać więcej informacji, zobacz [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono typowe scenariusze podczas korzystania z usługi Mobile Endpoint Security z usługą Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji
Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach następujące funkcje do czasu usunięcia zagrożenia:
* Łączenie z firmową pocztą e-mail
* Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy
* Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Obraz koncepcyjny przedstawiający blokowanie dostępu przez zasady z powodu wykrycia złośliwych aplikacji](./media/lookout-mobile-threat-defense-connector/malicious-apps-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Obraz koncepcyjny przedstawiający udzielenie dostępu do urządzeń po skorygowaniu](./media/lookout-mobile-threat-defense-connector/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci
Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci przez Wi-Fi:**

![Obraz przedstawiający blokowanie dostępu do sieci Wi-Fi z powodu wykrycia zagrożeń sieciowych](./media/lookout-mobile-threat-defense-connector/network-wifi-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Obraz koncepcyjny przedstawiający dostęp warunkowy zezwalający na dostęp po skorygowaniu](./media/lookout-mobile-threat-defense-connector/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Obraz koncepcyjny przedstawiający blokowanie dostępu do usługi SharePoint Online](./media/lookout-mobile-threat-defense-connector/network-spo-blocked.png)


**Dostęp udzielany po skorygowaniu:**

![Obraz koncepcyjny przedstawiający zezwolenie na dostęp po skorygowaniu zagrożenia dotyczącego sieci](./media/lookout-mobile-threat-defense-connector/network-spo-unblocked.png)

## <a name="next-steps"></a>Następne kroki
Oto główne kroki, które należy wykonać, aby zaimplementować to rozwiązanie:
1. [Konfigurowanie integracji usługi Lookout](lookout-mtd-connector-integration.md)
2. [Włączanie usługi Mobile Endpoint Security w usłudze Intune](mtd-connector-enable.md)
3. [Dodawanie i przypisywanie aplikacji Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4. [Konfigurowanie zasad zgodności urządzeń usługi Lookout](mtd-device-compliance-policy-create.md)
