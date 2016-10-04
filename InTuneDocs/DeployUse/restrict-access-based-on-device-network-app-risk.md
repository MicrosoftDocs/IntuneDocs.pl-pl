---
title: "Ograniczanie dostępu przy użyciu ochrony urządzeń przed zagrożeniami | Microsoft Intune"
description: "Ograniczanie dostępu do zasobów firmy oparte na ryzyku dotyczącym urządzeń, sieci i aplikacji."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 550fbbf94f46eee23e77ebf7f9177148882f28e2
ms.openlocfilehash: 758e4408fa7119ed4ebb82e98b850be5b1f318b4


---

# Ograniczanie dostępu do zasobu firmy oparte na ryzyku dotyczącym urządzeń, sieci i aplikacji
Kontrolowanie dostępu z urządzeń przenośnych do zasobów firmy jest możliwe dzięki ocenie ryzyka przeprowadzanej przez usługę Lookout — rozwiązanie do ochrony urządzeń przed zagrożeniami zintegrowane z usługą Microsoft Intune. Ryzyko oceniane jest na podstawie danych telemetrycznych zbieranych z urządzeń przez usługę Lookout. Dane te dotyczą luk w zabezpieczeniach systemu operacyjnego, zainstalowanych złośliwych aplikacji i profilów sieci. Opierając się na ocenie ryzyka, można skonfigurować zasady dostępu warunkowego w usłudze Intune i zezwolić lub zablokować urządzenia, które zostały uznane za niezgodne z powodu zagrożeń, jakie na nich wykryto.  Ta funkcja jest obecnie obsługiwana tylko przez urządzenia z systemem **Android** w wersji **4.1 i nowsze**, które są zarejestrowane w usłudze Microsoft Intune.  Aby uzyskać informacje o platformach i językach obsługiwanych przez rozwiązanie Lookout, zobacz ten [artykuł](https://personal.support.lookout.com/hc/en-us/articles/114094140253).
## Jaki problem to rozwiązuje?
Firmy i organizacje muszą chronić dane poufne przed pojawiającymi się zagrożeniami, do których zalicza się zagrożenia fizyczne, związane z aplikacją lub siecią, a także luki w zabezpieczeniach systemu operacyjnego.

W przeszłości firmy i organizacje przyjmowały aktywną postawę w stosunku do ochrony komputerów przed złośliwymi atakami. Telefony komórkowe stanowią obecnie obszar, który jest bardzo często niechroniony. Mimo że platformy urządzeń przenośnych mają wbudowaną ochronę systemu operacyjnego korzystającą z takich technik, jak izolacja aplikacji i weryfikacja sklepów z aplikacjami, platformy te nadal są narażone na zaawansowane ataki. W związku z tym, że urządzenia przenośne są coraz częściej używane w czasie pracy przez pracowników korzystających z dostępu do informacji, które mogą być cenne i poufne, takie urządzenia muszą być chronione przed różnego rodzaju zaawansowanymi atakami.

Usługa Intune daje możliwość kontrolowania dostępu do zasobów i danych firmy w ramach oceny ryzyka, którą zapewnia rozwiązanie do ochrony urządzeń przed zagrożeniami, takie jak Lookout.

## W jaki sposób usługa Intune i rozwiązanie Lookout do ochrony urządzeń przed zagrożeniami zabezpieczają zasoby firmy?
Aplikacja mobilna firmy Lookout (Lookout for Work), działająca na urządzeniach przenośnych, przechwytuje system plików, stos sieci i telemetrię urządzenia oraz aplikacji (jeśli jest dostępna) i wysyła te dane do usługi w chmurze oferowanej w ramach usługi Lookout do ochrony urządzeń przed zagrożeniami. Wszystkie te czynności mają na celu oszacowanie pod kątem zagrożeń średniego ryzyka dotyczącego urządzenia przenośnego. Dzięki konsoli usługi Lookout można również zmienić klasyfikację poziomu ryzyka dla zagrożeń zgodnie ze swoimi potrzebami.  
Zasady zgodności w usłudze Intune zawierają teraz nową regułę dla usługi Lookout przeznaczonej do ochrony urządzeń przenośnych przed zagrożeniami, która jest oparta na ocenie ryzyka przeprowadzanej przez usługę Lookout. Gdy ta reguła jest włączona, usługa Microsoft Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli urządzenie jest określone jako niezgodne z zasadami zgodności, dostęp do zasobów takich usług jak Exchange Online i SharePoint Online można zablokować za pomocą zasad dostępu warunkowego. Gdy dostęp jest zablokowany, użytkownicy końcowi otrzymują przewodnik, który ma pomóc rozwiązać ten problem i uzyskać dostęp do zasobów firmy. Przewodnik jest uruchamiany za pośrednictwem aplikacji Lookout for Work.

## Przykładowe scenariusze
Poniżej przedstawiono kilka typowych scenariuszy:
### Zagrożenie ze strony złośliwych aplikacji:
Po wykryciu na urządzeniu złośliwych aplikacji, takich jak złośliwe oprogramowanie, można zablokować takie urządzenie przed:
* Łączeniem z firmową pocztą e-mail, zanim problem związany z zagrożeniem zostanie rozwiązany.
* Synchronizowaniem plików firmowych za pomocą aplikacji OneDrive do pracy.
* Uzyskiwaniem dostępu do aplikacji biznesowych o znaczeniu krytycznym.

**Zablokowany dostęp po wykryciu złośliwych aplikacji:**
![diagram przedstawiający blokowanie dostępu przez zasady dostępu warunkowego, gdy urządzenie zostanie uznane za niezgodne z powodu znajdujących się na nim złośliwych aplikacji](../media/mtp/malicious-apps-blocked.png)

**Urządzenie zostało odblokowane i może uzyskać dostęp do zasobów firmy po skorygowaniu zagrożenia:**

![Diagram przedstawiający zasady dostępu warunkowego udzielające dostępu, gdy urządzenie jest uznane za zgodne po skorygowaniu](../media/mtp/malicious-apps-unblocked.png)
### Zagrożenie dla sieci:
Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle i ograniczanie dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Zablokowany dostęp do sieci za pośrednictwem sieci Wi-Fi:**
![diagram przedstawiający dostęp warunkowy blokujący dostęp do sieci Wi-Fi w oparciu o zagrożenia dotyczące sieci](../media/mtp/network-wifi-blocked.png)

**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający dostęp warunkowy, który zezwala na dostęp po skorygowaniu zagrożenia](../media/mtp/network-wifi-unblocked.png)
### Zagrożenie dla sieci (blokowanie dostępu do usługi SharePoint Online):

Wykrywanie zagrożeń dla sieci, takich jak ataki typu man-in-the-middle i blokowanie synchronizacji plików firmy w oparciu o ryzyko dotyczące urządzenia.

**Zablokowany dostęp do usługi SharePoint Online w oparciu o zagrożenie dotyczące sieci wykryte na urządzeniu:**

![Diagram przedstawiający dostęp warunkowy blokujący dostęp urządzenia do usługi SharePoint Online w oparciu o wykryte zagrożenie](../media/mtp/network-spo-blocked.png)


**Dostęp udzielany po skorygowaniu:**

![Diagram przedstawiający dostęp warunkowy zezwalający na dostęp po skorygowaniu zagrożenia dotyczącego sieci](../media/mtp/network-spo-unblocked.png)

## Następne kroki
Oto główne kroki, które należy wykonać, aby zaimplementować to rozwiązanie:
1.  [Konfigurowanie subskrypcji przy użyciu usługi Lookout do ochrony urządzeń przenośnych przed zagrożeniami](set-up-your-subscription-with-lookout-mtp.md)
2.  [Włączanie połączenia usługi Lookout MTP dla usługi Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Konfigurowanie i wdrażanie aplikacji Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Konfigurowanie zasad zgodności](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Rozwiązywanie problemów dotyczących integracji z aplikacją Lookout](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Sep16_HO4-->


