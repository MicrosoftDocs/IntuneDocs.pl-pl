---
title: Łącznik usługi Lookout MTD w usłudze Microsoft Intune
titlesuffix: ''
description: Dowiedz się więcej na temat integracji usługi Intune z usługą Lookout Mobile Threat Defense (MTD) w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/09/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a10c392f91c3c2992f1eebf8e71814520fbb4aa0
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231937"
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Łącznik Lookout Mobile Threat Defense z usługą Intune

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować dzięki ocenie ryzyka przeprowadzanej przez usługę Lookout — rozwiązaniu usługi Mobile Threat Defense zintegrowanemu z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń przez usługę Lookout. Są to na przykład:
- Luki w zabezpieczeniach systemu operacyjnego
- Zainstalowane złośliwe aplikacje
- Złośliwe profile sieci

W oparciu o ocenę ryzyka przeprowadzaną za pomocą usługi Lookout (włączaną przy użyciu zasad zgodności usługi Intune) można skonfigurować zasady dostępu warunkowego. Za pomocą ustawień można dopuszczać lub blokować niezgodne urządzenia na podstawie wykrytych zagrożeń.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>W jaki sposób usługa Intune i usługa Lookout Mobile Threat Defense chronią zasoby firmy?
Aplikacja mobilna usługi Lookout, **Lookout for work**, jest instalowana i działa na urządzeniach przenośnych. Ta aplikacja przechwytuje dane systemu plików, stosu sieci oraz dane telemetryczne urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Lookout w chmurze w celu ocenienia ryzyka dotyczącego urządzenia pod kątem zagrożeń urządzeń przenośnych. Klasyfikację poziomu ryzyka dla zagrożeń można zmienić w konsoli usługi Lookout, aby była zgodna z wymaganiami.  

Zasady zgodności w usłudze Intune zawierają regułę dla usługi Lookout Mobile Threat Defense, która jest oparta na ocenie ryzyka przeprowadzanej przez usługę Lookout. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli się okaże, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do zasobów, takich jak usługa Exchange Online czy SharePoint Online. Użytkownicy korzystający z zablokowanych urządzeń zostaną poinformowani o czynnościach, które należy wykonać w celu rozwiązania problemu i ponownego uzyskania dostępu. Te wskazówki są wyświetlane w aplikacji Lookout for work.

## <a name="supported-platforms"></a>Obsługiwane platformy
Po zarejestrowaniu w usłudze Intune narzędzie Lookout jest obsługiwane na następujących platformach:
* **Android 4.1 i nowsze**
* **iOS 8 i nowsze**. Aby uzyskać dodatkowe informacje o pomocy technicznej dotyczącej platformy i języka, odwiedź [witrynę sieci Web usługi Lookout](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Wymagania wstępne
* Subskrypcja usługi Microsoft Intune
* Azure Active Directory
* Subskrypcja korporacyjna usługi Lookout Mobile Endpoint Security  

Aby uzyskać więcej informacji, zobacz [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono typowe scenariusze podczas korzystania z usługi Lookout Mobile Threat Defense z usługą Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji
Po wykryciu na urządzeniach złośliwego oprogramowania można zablokować na tych urządzeniach następujące funkcje do czasu usunięcia zagrożenia:
* Łączenie z firmową pocztą e-mail
* Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy
* Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![diagram przedstawiający blokowanie dostępu przez zasady dostępu warunkowego, gdy urządzenie zostanie uznane za niezgodne z powodu znajdujących się na nim złośliwych aplikacji](./media/malicious-apps-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający zasady dostępu warunkowego udzielające dostępu, gdy urządzenie jest uznane za zgodne po skorygowaniu](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci
Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci przez Wi-Fi:**

![diagram przedstawiający dostęp warunkowy blokujący dostęp do sieci Wi-Fi na podstawie zagrożeń sieciowych](./media/network-wifi-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający dostęp warunkowy, który zezwala na dostęp po skorygowaniu zagrożenia](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Diagram przedstawiający dostęp warunkowy blokujący dostęp urządzenia do usługi SharePoint Online w oparciu o wykryte zagrożenie](./media/network-spo-blocked.png)


**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający dostęp warunkowy zezwalający na dostęp po skorygowaniu zagrożenia dotyczącego sieci](./media/network-spo-unblocked.png)

## <a name="next-steps"></a>Następne kroki
Oto główne kroki, które należy wykonać, aby zaimplementować to rozwiązanie:
1.  [Konfigurowanie integracji usługi Lookout](lookout-mtd-connector-integration.md)
2.  [Włączanie usługi Lookout Mobile Threat Defense w usłudze Intune](mtd-connector-enable.md)
3.  [Dodawanie i przypisywanie aplikacji Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [Konfigurowanie zasad zgodności urządzeń usługi Lookout](mtd-device-compliance-policy-create.md)
