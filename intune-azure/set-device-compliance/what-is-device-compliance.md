---
title: "Zgodność urządzeń | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: w tym temacie można znaleźć informacje na temat zgodności urządzeń w usłudze Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Co to jest zgodność urządzeń w wersji zapoznawczej usługi Intune Azure?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Aby pomóc chronić dane firmy, należy się upewnić, że urządzenia używane do uzyskiwania dostępu do aplikacji oraz danych firmowych spełniają pewne reguły. Te reguły mogą obejmować wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzeń oraz szyfrowanie danych przechowywanych na urządzeniach. Zestaw takich reguł jest nazywany **zasadami zgodności**.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Jak używać zasad zgodności urządzeń?
Zasad zgodności można używać łącznie z zasadami dostępu warunkowego, aby zezwolić na dostęp do poczty e-mail i innych usług tylko tym urządzeniom, które spełniają reguły zasad zgodności.

Zasady zgodności można również stosować niezależnie od dostępu warunkowego.
Jeśli zasady zgodności są stosowane niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład można uzyskać raport z liczbą urządzeń, które nie są szyfrowane, lub z informacją o urządzeniach, na których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Ale jeśli zasady zgodności są stosowane niezależnie, to nie istnieją żadne domyślne ograniczenia dostępu do zasobów firmowych.

Zasady zgodności wdraża się dla użytkowników. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika. Aby uzyskać informacje o tym, ile czasu potrzeba na otrzymanie zasad przez urządzenia przenośne po wdrożeniu tych zasad, zobacz artykuł Zarządzanie ustawieniami i funkcjami urządzeń.

##  <a name="concepts"></a>Pojęcia
Poniżej przedstawiono niektóre terminy i pojęcia, które są przydatne do zrozumienia sposobu używania zasad zgodności.

### <a name="compliance-requirements"></a>Wymagania dotyczące zgodności
Wymagania dotyczące zgodności są zasadniczo regułami, takimi jak wymaganie podania numeru PIN urządzenia lub szyfrowanie, które można określić jako wymagane lub niewymagane w ramach zasad zgodności.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Różnice między klasyczną konsolą administracyjną usługi Intune i usługą Intune w portalu Azure


Jeśli masz doświadczenie z klasyczną konsolą administracyjną Intune, zwróć uwagę na następujące różnice, by ułatwić przejście na nowy przepływ pracy zgodności urządzeń w portalu Azure:


-   W portalu Azure zasady zgodności są tworzone oddzielnie dla każdej z obsługiwanych platform. W konsoli administracyjnej usługi Intune te same zasady zgodności były wspólne dla wszystkich obsługiwanych platform.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Następne kroki

[Rozpoczęcie pracy z zasadami zgodności](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


