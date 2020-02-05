---
title: Konfigurowanie rozwiązania Wandera Mobile Security za pomocą usługi Intune
titleSuffix: Intune on Azure
description: Sposób konfigurowania rozwiązania Wandera Mobile Security w usłudze Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3ee253b50ea525f7d156c77a83f486cf990da030
ms.sourcegitcommit: af384c46ec8d8def6aa32c3b89947748dc6fd28f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/22/2020
ms.locfileid: "76517460"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Łącznik Wandera Mobile Threat Defense w usłudze Intune  

Kontroluj dostęp urządzeń przenośnych do zasobów firmy przy użyciu dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez firmę Wandera. Wandera to rozwiązanie obrony przed zagrożeniami mobilnymi (MTD, Mobile Threat Defense), które można zintegrować z usługą Microsoft Intune.  Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń przez usługę Wandera. Są to na przykład:
- Luki w zabezpieczeniach systemu operacyjnego
- Zainstalowane złośliwe aplikacje
- Złośliwe profile sieci
- Cryptojacking (złośliwe wydobywanie kryptowalut)

Zasady *dostępu warunkowego* można skonfigurować w oparciu o ocenę ryzyka rozwiązania Wandera włączaną przy użyciu zasad zgodności urządzeń usługi Intune. Zasady oceny ryzyka mogą zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i usługa Wandera Mobile Threat Defense chronią zasoby firmy?  

Aplikację mobilną Wandera można bezproblemowo zainstalować przy użyciu usługi Microsoft Intune. Ta aplikacja przechwytuje dane telemetryczne systemu plików, stosu sieci, urządzenia oraz aplikacji (jeśli są dostępne). Te informacje są synchronizowane z usługą chmurową Wandera w celu oceny ryzyka związanego z zagrożeniami mobilnymi dotyczącego urządzenia. Tę klasyfikację poziomu ryzyka można skonfigurować tak, aby odpowiadała określonym potrzebom, w konsoli rozwiązania Wandera — RADAR.

Zasady zgodności w usłudze Intune zawierają regułę dotyczącą usługi MTD opartą na ocenie ryzyka firmy Wandera. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

W przypadku urządzeń, które nie są zgodne, dostęp do zasobów, takich jak usługa Office 365, może zostać zablokowany. Użytkownicy zablokowanych urządzeń otrzymają wskazówki z aplikacji Wandera dotyczące rozwiązania problemu i odzyskania dostępu.

## <a name="supported-platforms"></a>Obsługiwane platformy  

Po zarejestrowaniu w usłudze Intune rozwiązanie Wandera jest obsługiwane na następujących platformach:

- System Android 5.0 i nowsze  
- System iOS 10.2 lub nowszy  

Aby uzyskać więcej informacji na temat platformy i urządzenia, zobacz [witrynę internetową firmy Wandera](https://www.wandera.com/mobile-threat-defense/).

## <a name="prerequisites"></a>Wymagania wstępne  

- Subskrypcja usługi Microsoft Intune  
- Azure Active Directory  
- Wandera Mobile Threat Defense (dawniej Wandera Secure)  

Aby uzyskać więcej informacji, zobacz [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono typowe scenariusze podczas korzystania z usługi Wandera MTD z usługą Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji  

Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach dostęp do najczęściej używanych narzędzi do czasu usunięcia zagrożenia. Typowe blokady obejmują:  
- Łączenie z firmową pocztą e-mail  
- Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy  
- Uzyskiwanie dostępu do aplikacji firmowych  

**Blokowanie po wykryciu złośliwych aplikacji**:

![Koncepcyjny obraz przedstawiający wykrycie złośliwych aplikacji](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Dostęp udzielany po skorygowaniu**: 

![Koncepcyjny obraz przedstawiający dostęp udzielany po skorygowaniu](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci  

Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.  

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi**:  

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Dostęp udzielany po skorygowaniu**:  

![Dostęp udzielany po skorygowaniu](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych**:  

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Dostęp udzielany po skorygowaniu**:  

![Dostęp udzielany po skorygowaniu — przykład dla programu SharePoint](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Następne kroki

- [Integracja rozwiązania Wandera z usługą Intune](wandera-mtd-connector-integration.md)
- [Konfigurowanie aplikacji Wandera](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Tworzenie zasad zgodności urządzenia rozwiązania Wandera](mtd-device-compliance-policy-create.md)
- [Włączanie łącznika Wandera MTD](mtd-connector-enable.md)
