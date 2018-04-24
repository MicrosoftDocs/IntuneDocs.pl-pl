---
title: Łącznik Lookout Mobile Threat Defense
description: Chroń dostęp do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji przy użyciu łącznika Lookout Mobile Threat Defense i usługi Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 85a296c28658b8eb3db5e5e99dcd573b3b98e0ea
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Łącznik Lookout Mobile Threat Defense z usługą Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować dzięki ocenie ryzyka przeprowadzanej przez usługę Lookout — rozwiązaniu usługi Mobile Threat Defense zintegrowanemu z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń przez usługę Lookout. Są to na przykład:
- Luki w zabezpieczeniach systemu operacyjnego
- Zainstalowane złośliwe aplikacje
- Złośliwe profile sieci

W oparciu o ocenę ryzyka przeprowadzaną za pomocą usługi Lookout (włączaną przy użyciu zasad zgodności usługi Intune) można skonfigurować zasady dostępu warunkowego. Za pomocą ustawień można dopuszczać lub blokować niezgodne urządzenia na podstawie wykrytych zagrożeń.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>W jaki sposób usługa Intune i usługa Lookout Mobile Threat Defense chronią zasoby firmy?
Aplikacja mobilna usługi Lookout, **Lookout for work**, jest instalowana i działa na urządzeniach przenośnych. Ta aplikacja przechwytuje dane systemu plików, stosu sieci oraz dane telemetryczne urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Lookout w chmurze w celu ocenienia ryzyka dotyczącego urządzenia pod kątem zagrożeń urządzeń przenośnych. Klasyfikację poziomu ryzyka dla zagrożeń można zmienić w konsoli usługi Lookout, aby była zgodna z wymaganiami.  

Zasady zgodności w usłudze Intune zawierają regułę dla usługi Lookout Mobile Threat Defense, która jest oparta na ocenie ryzyka przeprowadzanej przez usługę Lookout. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli się okaże, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do zasobów, takich jak usługa Exchange Online czy SharePoint Online. Użytkownicy korzystający z zablokowanych urządzeń zostaną poinformowani o czynnościach, które należy wykonać w celu rozwiązania problemu i ponownego uzyskania dostępu. Te wskazówki są wyświetlane w aplikacji Lookout for work.

## <a name="supported-platforms"></a>Obsługiwane platformy:
Po zarejestrowaniu w usłudze Intune narzędzie Lookout jest obsługiwane na następujących platformach:
* **Android 4.1 i nowsze**
* **iOS 8 i nowsze**. Aby uzyskać dodatkowe informacje o pomocy technicznej dotyczącej platformy i języka, odwiedź [witrynę sieci Web usługi Lookout](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Wymagania wstępne:
* Subskrypcja usługi Microsoft Intune
* Azure Active Directory
* Subskrypcja korporacyjna usługi Lookout Mobile Endpoint Security  

Aby uzyskać więcej informacji, zobacz [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Przykładowe scenariusze
Poniżej przedstawiono kilka typowych scenariuszy:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji
Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach następujące funkcje do czasu usunięcia zagrożenia:
* Łączenie z firmową pocztą e-mail
* Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy
* Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**
![diagram przedstawiający blokowanie dostępu przez zasady dostępu warunkowego, gdy urządzenie zostanie uznane za niezgodne z powodu znajdujących się na nim złośliwych aplikacji](../media/mtp/malicious-apps-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający zasady dostępu warunkowego udzielające dostępu, gdy urządzenie jest uznane za zgodne po skorygowaniu](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci
Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**
![diagram przedstawiający dostęp warunkowy blokujący dostęp do sieci Wi-Fi na podstawie zagrożeń sieciowych](../media/mtp/network-wifi-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający dostęp warunkowy, który zezwala na dostęp po skorygowaniu zagrożenia](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Diagram przedstawiający dostęp warunkowy blokujący dostęp urządzenia do usługi SharePoint Online w oparciu o wykryte zagrożenie](../media/mtp/network-spo-blocked.png)


**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający dostęp warunkowy zezwalający na dostęp po skorygowaniu zagrożenia dotyczącego sieci](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Następne kroki
Oto główne kroki, które należy wykonać, aby zaimplementować to rozwiązanie:
1.  [Konfigurowanie subskrypcji usługi Lookout](setup-your-lookout-mtd-subscription.md)
2.  [Włączanie usługi Lookout Mobile Threat Defense w usłudze Intune](enable-lookout-mtd-connection.md)
3.  [Konfigurowanie i wdrażanie aplikacji Lookout Mobile Threat Defense](configure-deploy-lookout-for-work-app.md)
4.  [Konfigurowanie zasad zgodności urządzeń usługi Lookout](create-lookout-device-compliance-policy.md)
5.  [Rozwiązywanie problemów z integracją usługi Lookout Mobile Threat Defense](/intune-classic/troubleshoot/device-threat-protection-troubleshooting)
