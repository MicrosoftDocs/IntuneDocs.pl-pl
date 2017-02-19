---
title: "Ochrona dostępu przy użyciu ochrony urządzeń przed zagrożeniami | Microsoft Docs"
description: "Ochrona dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 931f222898a224c2f646ad203f12676c39b78946
ms.openlocfilehash: aaa0965c2bd4d4093da0c57eaa2e3bd05eb6779a


---

# <a name="protect-access-to-company-resource-based-on-device-network-and-application-risk"></a>Ochrona dostępu do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować dzięki ocenie ryzyka przeprowadzanej przez usługę Lookout — rozwiązaniu do ochrony urządzeń przed zagrożeniami zintegrowanemu z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń przez usługę Lookout. Są to na przykład:
- Luki w zabezpieczeniach systemu operacyjnego
- Zainstalowane złośliwe aplikacje
- Złośliwe profile sieci

W oparciu o ocenę ryzyka przeprowadzaną za pomocą usługi Lookout (włączaną przy użyciu zasad zgodności usługi Intune) można skonfigurować zasady dostępu warunkowego. Za pomocą ustawień można dopuszczać lub blokować niezgodne urządzenia na podstawie wykrytych zagrożeń.  

## <a name="what-problem-does-this-solve"></a>Jaki problem to rozwiązuje?
Firmy muszą chronić dane poufne przed pojawiającymi się zagrożeniami, do których zalicza się zagrożenia fizyczne, związane z aplikacją lub siecią, a także luki w zabezpieczeniach systemu operacyjnego.

Wcześniej firmy aktywnie chroniły komputery przed atakami, pozostawiając urządzenia przenośne bez monitorowania i ochrony. Platformy urządzeń przenośnych mają wbudowaną ochronę polegającą na izolacji aplikacji i weryfikacji sklepów z aplikacjami, ale platformy te nadal są narażone na zaawansowane ataki. Obecnie coraz więcej pracowników korzysta w swojej pracy z urządzeń i wymaga dostępu do poufnych informacji. Urządzenia muszą być chronione przed coraz bardziej zaawansowanymi atakami.

Usługa Intune umożliwia kontrolowanie dostępu do zasobów firmy w oparciu o ocenę ryzyka, którą zapewnia rozwiązanie do ochrony urządzeń przed zagrożeniami, takie jak Lookout.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>W jaki sposób usługa Intune i rozwiązanie Lookout do ochrony urządzeń przed zagrożeniami zabezpieczają zasoby firmy?
Aplikacja mobilna usługi Lookout, **Lookout for work**, jest instalowana i działa na urządzeniach przenośnych. Ta aplikacja przechwytuje dane systemu plików, stosu sieci oraz dane telemetryczne urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Lookout w chmurze w celu ocenienia ryzyka dotyczącego urządzenia pod kątem zagrożeń urządzeń przenośnych. Klasyfikację poziomu ryzyka dla zagrożeń można zmienić w konsoli usługi Lookout, aby była zgodna z wymaganiami.  

Zasady zgodności w usłudze Intune zawierają regułę dla usługi Lookout przeznaczonej do ochrony urządzeń przenośnych przed zagrożeniami, która jest oparta na ocenie ryzyka przeprowadzanej przez usługę Lookout. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli się okaże, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do zasobów, takich jak usługa Exchange Online czy SharePoint Online. Użytkownicy korzystający z zablokowanych urządzeń zostaną poinformowani o czynnościach, które należy wykonać w celu rozwiązania problemu i ponownego uzyskania dostępu. Te wskazówki są wyświetlane w aplikacji Lookout for work.

## <a name="supported-platforms"></a>Obsługiwane platformy:
Po zarejestrowaniu w usłudze Intune narzędzie Lookout jest obsługiwane na następujących platformach:
* **Android 4.1 i nowsze**
* **iOS 8 i nowsze**. Aby uzyskać dodatkowe informacje o pomocy technicznej dotyczącej platformy i języka, odwiedź [witrynę sieci Web usługi Lookout](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

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
1.    [Konfigurowanie subskrypcji pod kątem ochrony urządzenia przed zagrożeniami](device-threat-protection-subscription-setup.md)
2.    [Włączanie połączenia z ochroną urządzenia przed zagrożeniami w usłudze Intune](device-threat-protection-enable.md)
3.  [Konfigurowanie i wdrażanie aplikacji ochrony urządzenia przed zagrożeniami](device-threat-protection-apps.md)
4.    [Konfigurowanie zasad zgodności ochrony urządzenia przed zagrożeniami](device-threat-protection-policy.md)
5.    [Rozwiązywanie problemów z integracją ochrony urządzenia przed zagrożeniami](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)



<!--HONumber=Jan17_HO4-->


