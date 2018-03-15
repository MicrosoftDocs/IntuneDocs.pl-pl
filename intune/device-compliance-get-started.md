---
title: "Zasady zgodności urządzeń w usłudze Microsoft Intune"
titleSuffix: 
description: "Informacje na temat zgodności urządzeń w usłudze Microsoft Intune"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9e3a7bdf3ddf6ad77a82ac6dc7075d696fbe6497
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="get-started-with-microsoft-intune-device-compliance-policies"></a>Wprowadzenie do zasad zgodności urządzeń w usłudze Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń w usłudze Intune służą do definiowania reguł i ustawień, z którymi urządzenie musi być zgodne, aby było uważane za spełniające zasady usługi Intune.

Do reguł tych należą następujące elementy:

- Używanie hasła dostępu do urządzenia

- Szyfrowanie

- Określanie, czy urządzenie ma złamane zabezpieczenia lub odblokowany dostęp do konta root

- Minimalna wymagana wersja systemu operacyjnego

- Dozwolona maksymalna wersja systemu operacyjnego

- Urządzenie musi być co najmniej na poziomie obrony przed zagrożeniami mobilnymi

Zasady zgodności urządzeń mogą być również używane do monitorowania stanu zgodności urządzeń.

## <a name="device-compliance-requirements"></a>Wymagania dotyczące zgodności urządzeń

Wymagania dotyczące zgodności są zasadniczo regułami, takimi jak wymaganie podania numeru PIN urządzenia lub szyfrowanie, które można określić jako wymagane lub niewymagane w ramach zasad zgodności.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="pre-requisites"></a>Wymagania wstępne

Należy posiadać następujące subskrypcje, aby móc korzystać z zasad zgodności urządzeń z usługą Intune:

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Obsługiwane platformy:

-   Android

-   iOS

-   macOS (wersja zapoznawcza)

-   Windows 8.1

-   Windows Phone 8,1

-   Windows 10

> [!IMPORTANT]
> Urządzenia muszą być zarejestrowane w usłudze Intune, aby mogły raportować swoje stany zgodności.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Jak zasady zgodności urządzeń usługi Intune działają z usługą Azure AD

Gdy urządzenie jest rejestrowane w usłudze Intune, ma miejsce proces rejestracji w usłudze Azure AD, który służy do aktualizowania atrybutów urządzenia o dodatkowe informacje w usłudze Azure AD. Jedną z kluczowych informacji o urządzeniu jest jego stan zgodności, który jest używany przez zasady dostępu warunkowego do blokowania dostępu do poczty e-mail i innych zasobów firmowych lub zezwalania na taki dostęp.

- Dowiedz się więcej o [procesie rejestracji w usłudze Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>Przypisywanie wynikowego stanu profilu konfiguracji urządzenia

Jeśli do urządzenia jest przypisanych wiele profilów konfiguracji i dla co najmniej dwóch przypisanych profilów konfiguracji ma ono różne stany zgodności, należy przypisać jeden wynikowy stan zgodności. To przypisanie jest oparte na poziomie ważności koncepcyjnej przypisanym do poszczególnych stanów zgodności. Poszczególnym stanom zgodności odpowiadają następujące poziomy ważności:


|Stan  |Ważność  |
|---------|---------|
|Oczekiwanie     |1|
|Sukces     |2|
|Niepowodzenie     |3|
|Error     |4|

Wynikowy stan co najmniej dwóch profilów konfiguracji zostaje przypisany przez wybranie najwyższego poziomu ważności ze wszystkich profilów przypisanych do urządzenia.

Na przykład urządzenie może mieć przypisane trzy profile: stan Pending (oczekiwanie, ważność = 1), stan Succeeded (powodzenie, ważność = 2) i stan Error (błąd, ważność = 4). Stan Error ma najwyższy poziom ważności, dlatego zostaje on przypisany jako wynikowy stan zgodności dla wszystkich trzech profilów.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>Przypisywanie stanu InGracePeriod w przypadku braku przypisania zasad zgodności

Stan InGracePeriod zasad zgodności to wartość ustalana przez uwzględnienie kombinacji okresu prolongaty urządzenia i stanu rzeczywistego urządzenia względem przypisanych zasad zgodności. 

W szczególności gdy urządzenie ma stan niezgodności (NonCompliant) dla przypisanych zasad zgodności oraz:

- do urządzenia nie przypisano okresu prolongaty, przypisaną wartością zasad zgodności jest NonCompliant.
- do urządzenia przypisano okres prolongaty, który wygasł, przypisaną wartością zasad zgodności jest NonCompliant.
- do urządzenia przypisano okres prolongaty, którego termin przypada w przyszłości, przypisaną wartością zasad zgodności jest InGracePeriod.

Poniższa tabela zawiera podsumowanie poprzednich punktów:


|Rzeczywisty stan zgodności|Wartość przypisanego okresu prolongaty|Ostateczny stan zgodności|
|---------|---------|---------|
|NonCompliant |Nie przypisano okresu prolongaty |NonCompliant |
|NonCompliant |Data przeszła|NonCompliant|
|NonCompliant |Data przyszła|InGracePeriod|

Aby uzyskać więcej informacji na temat monitorowania zasad zgodności urządzeń, zobacz [Monitor Intune Device compliance policies](compliance-policy-monitor.md) (Monitorowanie zasad zgodności urządzeń w usłudze Intune).

### <a name="assigning-a-resulting-compliance-policy-status"></a>Przypisywanie wynikowego stanu zasad zgodności

Jeśli do urządzenia jest przypisanych wiele zasad zgodności i dla co najmniej dwóch przypisanych zasad zgodności ma ono różne stany zgodności, należy przypisać jeden wynikowy stan zgodności. To przypisanie jest oparte na poziomie ważności koncepcyjnej przypisanym do poszczególnych stanów zgodności. Poszczególnym stanom zgodności odpowiadają następujące poziomy ważności: 

|Stan  |Ważność  |
|---------|---------|
|Nieznane     |1|
|NotApplicable     |2|
|Zgodny|3|
|InGracePeriod|4|
|NonCompliant|5|
|Error|6|

Wynikowy stan wielu zasad zgodności zostaje ustalony przez wybranie najwyższego poziomu ważności ze wszystkich zasad przypisanych do urządzenia.
 
Na przykład urządzenie może mieć przypisane trzy rodzaje zasad zgodności: stan Unknown (nieznany, ważność = 1), stan Compliant (zgodne, ważność = 3) i stan InGracePeriod (prolongata, ważność = 4). Stan InGracePeriod ma najwyższy poziom ważności, dlatego zostaje on przypisany jako wynikowy stan zgodności dla wszystkich trzech profilów.  

##  <a name="ways-to-use-device-compliance-policies"></a>Sposoby korzystania z zasad zgodności urządzeń

### <a name="with-conditional-access"></a>Z dostępem warunkowym
Zasad zgodności można używać z zasadami dostępu warunkowego, aby zezwolić na dostęp do poczty e-mail i innych zasobów firmowych tylko tym urządzeniom, które spełniają co najmniej jedną regułę zasad zgodności.

### <a name="without-conditional-access"></a>Bez dostępu warunkowego
Zasady zgodności można również stosować niezależnie od dostępu warunkowego. Jeśli zasady zgodności są stosowane niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład można uzyskać raport z liczbą urządzeń, które nie są szyfrowane, lub z informacją o urządzeniach, w których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Ale jeśli zasady zgodności są stosowane niezależnie, to nie istnieją żadne domyślne ograniczenia dostępu do zasobów firmowych.

Zasady zgodności wdraża się dla użytkowników. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika. Aby uzyskać informacje o tym, ile czasu potrzeba na otrzymanie zasad przez urządzenia przenośne po wdrożeniu tych zasad, zobacz [Rozwiązywanie problemów z profilami urządzeń w usłudze Microsoft Intune](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

#### <a name="actions-for-non-compliance"></a>Akcje w przypadku niezgodności

Akcje dotyczące niezgodności umożliwiają skonfigurowanie uporządkowanej w czasie sekwencji akcji, które są stosowane do urządzeń niespełniających kryteriów zasad zgodności. Aby uzyskać więcej informacji, zobacz [Automatyzacja akcji w przypadku niezgodności](actions-for-noncompliance.md).

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Porównanie sposobu korzystania z zasad zgodności urządzeń w klasycznym portalu usługi Intune z Witryna Azure Portal

Zapoznanie się z głównymi różnicami ułatwi przejście do nowego przepływu pracy zasad zgodności urządzeń w witrynie Azure Portal.

- W portalu Azure zasady zgodności są tworzone oddzielnie dla każdej z obsługiwanych platform.
- W klasycznym portalu usługi Intune te same zasady zgodności urządzeń były wspólne dla wszystkich obsługiwanych platform.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Migrowanie zasad zgodności urządzeń z klasycznego portalu usługi Intune do witryny Azure Portal

Zasady zgodności urządzeń utworzone w [klasycznym portalu usługi Intune](https://manage.microsoft.com) nie są wyświetlane w nowej witrynie [Azure Portal usługi Intune](https://portal.azure.com). Nadal będą one jednak mieć zastosowanie do użytkowników i możliwe będzie zarządzanie nimi za pośrednictwem klasycznego portalu usługi Intune.

Aby móc korzystać z nowych funkcji związanych ze zgodnością urządzeń dostępnych w witrynie Azure Portal, należy w tej witrynie utworzyć nowe zasady zgodności urządzeń. Jeśli w witrynie Azure Portal przypiszesz nowe zasady zgodności urządzeń do użytkownika, do którego zostały również przypisane zasady zgodności urządzeń z klasycznego portalu usługi Intune, to zasady zgodności urządzeń z witryny Azure Portal usługi Intune będą mieć pierwszeństwo przed zasadami utworzonymi w klasycznym portalu usługi Intune.

##  <a name="next-steps"></a>Następne kroki

- Utwórz zasady zgodności urządzeń dla następujących platform:

   - [Android](compliance-policy-create-android.md)
   - [Android for Work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Aby uzyskać informacje na temat jednostek zasad magazynu danych usługi Intune, zobacz [Dokumentacja jednostek zasad](reports-ref-policy.md).
