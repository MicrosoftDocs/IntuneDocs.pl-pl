---
title: "Zgodność urządzeń"
titleSuffix: Intune on Azure
description: "W tym temacie można znaleźć informacje na temat zgodności urządzeń w usłudze Microsoft Intune."
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
ms.custom: intune-azure
ms.openlocfilehash: a747d577a28433635883ad6c4fe4c858e75902d0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="what-is-device-compliance-in-intune"></a>Co to jest zgodność urządzeń w usłudze Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń definiują reguły i ustawienia, z którymi urządzenie musi być zgodne, aby można je było uważać za spełniające zasady dostępu warunkowego do usług Intune i EMS. Zasady zgodności urządzeń mogą być również wykorzystane do monitorowania i rozwiązywania problemów ze zgodnością urządzeń. 

Do reguł tych należą następujące elementy:

- Używanie hasła dostępu do urządzenia
- Encryption
- Określanie, czy urządzenie ma złamane zabezpieczenia lub odblokowany dostęp do konta root
- Minimalna wymagana wersja systemu operacyjnego
- Dozwolona maksymalna wersja systemu operacyjnego
- Urządzenie musi być co najmniej na poziomie obrony przed zagrożeniami mobilnymi

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

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

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Jak używać zasad zgodności urządzeń?

### <a name="using-ems-conditional-access"></a>Przy użyciu dostępu warunkowego usługi EMS
Zasad zgodności można używać z zasadami dostępu warunkowego usługi EMS, aby zezwolić na dostęp do poczty e-mail i innych zasobów firmowych tylko tym urządzeniom, które spełniają co najmniej jedną regułę zasad zgodności.

### <a name="not-using-ems-conditional-access"></a>Bez użycia dostępu warunkowego usługi EMS
Zasady zgodności można również stosować niezależnie od dostępu warunkowego usługi EMS.
Jeśli zasady zgodności są stosowane niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład można uzyskać raport z liczbą urządzeń, które nie są szyfrowane, lub z informacją o urządzeniach, w których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Ale jeśli zasady zgodności są stosowane niezależnie, to nie istnieją żadne domyślne ograniczenia dostępu do zasobów firmowych.

Zasady zgodności wdraża się dla użytkowników. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika. Aby uzyskać informacje o tym, ile czasu potrzeba na otrzymanie zasad przez urządzenia przenośne po wdrożeniu tych zasad, zobacz artykuł Zarządzanie ustawieniami i funkcjami urządzeń.

##  <a name="intune-classic-admin-console-vs-intune-on-the-azure-portal"></a>Klasyczna konsola administracyjna usługi Intune a usługa Intune w witrynie Azure Portal

Jeśli masz doświadczenie z klasyczną konsolą administracyjną Intune, zwróć uwagę na następujące różnice, by ułatwić sobie przejście na nowy przepływ pracy zgodności urządzeń w portalu Azure:

-   W portalu Azure zasady zgodności są tworzone oddzielnie dla każdej z obsługiwanych platform. W konsoli administracyjnej usługi Intune te same zasady zgodności były wspólne dla wszystkich obsługiwanych platform.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-on-the-azure-portal"></a>Migracja z klasycznej konsoli usługi Intune do usługi Intune w witrynie Azure Portal

Zasady zgodności urządzeń utworzone w [klasycznej konsoli usługi Intune](https://manage.microsoft.com) nie są wyświetlane w nowym [portalu usługi Intune Azure](https://portal.azure.com). Nadal będą one jednak mieć zastosowanie do użytkowników i będzie można nimi zarządzać za pośrednictwem klasycznej konsoli usługi Intune.

Aby móc korzystać z nowych funkcji związanych ze zgodnością urządzeń dostępnych w portalu usługi Intune Azure, musisz utworzyć nowe zasady zgodności urządzeń w witrynie Intune Azure Portal. Jeśli przypiszesz w witrynie Intune Azure Portal nowe zasady zgodności urządzenia do użytkownika, do którego zostały również przypisane zasady zgodności urządzenia z portalu klasycznego Intune, to zasady zgodności urządzenia z witryny Intune Azure Portal będą mieć pierwszeństwo przed zasadami utworzonymi w klasycznej konsoli usługi Intune.

##  <a name="next-steps"></a>Następne kroki

[Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md)


<!---### See also

Conditional access--->
