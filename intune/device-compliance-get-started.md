---
title: Zasady zgodności urządzeń w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Wymagania dotyczące korzystania z zasad zgodności urządzeń, omówienie stanu i poziomów ważności, korzystanie ze stanu InGracePeriod, praca z dostępem warunkowym, obsługa urządzeń bez przypisanych zasad oraz różnice w zgodności między witryną Azure Portal i portalem klasycznym w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 226713d893e05c2c2aeea49cde2ce92591d06391
ms.sourcegitcommit: 1134ecd733356277b40eb1c7f2b318b36d387e00
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2018
ms.locfileid: "50915703"
---
# <a name="get-started-with-device-compliance-policies-in-intune"></a>Wprowadzenie do zasad zgodności urządzeń w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Wymagania dotyczące zgodności to zasadniczo reguły, takie jak wymóg stosowania numeru PIN urządzenia lub stosowania szyfrowania. Zasady zgodności urządzeń służą do definiowania reguł i ustawień, które muszą zostać zastosowane na urządzeniu, aby było uważane za zgodne. Reguły obejmują:

- Używanie hasła dostępu do urządzenia

- Szyfrowanie

- Określanie, czy urządzenie ma złamane zabezpieczenia lub odblokowany dostęp do konta root

- Minimalna wymagana wersja systemu operacyjnego

- Dozwolona maksymalna wersja systemu operacyjnego

- Urządzenie musi być na poziomie usługi Mobile Threat Defense lub niższym

Zasady zgodności urządzeń mogą być również używane do monitorowania stanu zgodności urządzeń.

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

## <a name="prerequisites"></a>Wymagania wstępne
Do korzystania z zasad zgodności urządzeń są wymagane następujące elementy:

- Użyj następujących subskrypcji:

  - Intune
  - Usługa Azure Active Directory (AD) — wersja Premium

- Użyj obsługiwanej platformy:

  - Android
  - iOS
  - macOS (wersja zapoznawcza)
  - Windows 8.1
  - Windows Phone 8,1
  - Windows 10

- Urządzenia muszą być zarejestrowane w usłudze Intune, aby mogły zgłaszać stan zgodności.

- Urządzenia zarejestrowane dla jednego użytkownika lub urządzenia bez użytkownika podstawowego są obsługiwane. Wiele kontekstów użytkownika nie jest obsługiwanych.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Jak zasady zgodności urządzeń usługi Intune działają z usługą Azure AD

Gdy urządzenie jest rejestrowane w usłudze Intune, rozpoczyna się proces rejestracji w usłudze Azure AD, który aktualizuje atrybuty urządzenia w usłudze Azure AD. Jedną z kluczowych informacji jest stan zgodności urządzenia. Stan zgodności jest używany przez zasady dostępu warunkowego do blokowania lub udostępniania poczty e-mail i innych zasobów firmy.

Artykuł [Azure AD registration process (Proces rejestracji w usłudze Azure AD)](https://docs.microsoft.com/azure/active-directory/device-management-introduction) zawiera więcej informacji.

### <a name="assign-a-resulting-device-configuration-profile-status"></a>Przypisywanie wynikowego stanu profilu konfiguracji urządzenia

Jeśli urządzenie ma wiele profilów konfiguracji i dla co najmniej dwóch przypisanych profilów konfiguracji ma ono różne stany zgodności, to zostanie przypisany jeden wynikowy stan zgodności. To przypisanie jest oparte na poziomie ważności koncepcyjnej przypisanym do poszczególnych stanów zgodności. Poszczególnym stanom zgodności odpowiadają następujące poziomy ważności:

|Stan  |Ważność  |
|---------|---------|
|Oczekiwanie     |1|
|Sukces     |2|
|Niepowodzenie     |3|
|Error     |4|

Jeśli urządzenie ma przypisanych wiele profilów konfiguracji, to do urządzenia jest przypisywany najwyższy spośród poziomów ważności wszystkich profili.

Na przykład urządzenie może mieć przypisane trzy profile: stan Pending (oczekiwanie, ważność = 1), stan Succeeded (powodzenie, ważność = 2) i stan Error (błąd, ważność = 4). Stan Error ma najwyższy poziom ważności, dlatego wszystkie trzy profile mają stan zgodności Error.

### <a name="assign-an-ingraceperiod-status"></a>Przypisywanie stanu InGracePeriod

Stan InGracePeriod zasad zgodności jest wartością. Tę wartość określa kombinacja okresu prolongaty urządzenia oraz rzeczywistego stanu urządzenia dla zasad zgodności.

W szczególności gdy urządzenie ma stan niezgodności (NonCompliant) dla przypisanych zasad zgodności oraz:

- do urządzenia nie przypisano okresu prolongaty — przypisaną wartością zasad zgodności jest NonCompliant
- do urządzenia przypisano okres prolongaty, który wygasł — przypisaną wartością zasad zgodności jest NonCompliant
- do urządzenia przypisano okres prolongaty, którego termin przypada w przyszłości — przypisaną wartością zasad zgodności jest InGracePeriod

Poniższa tabela zawiera podsumowanie tych informacji:

|Rzeczywisty stan zgodności|Wartość przypisanego okresu prolongaty|Ostateczny stan zgodności|
|---------|---------|---------|
|NonCompliant |Nie przypisano okresu prolongaty |NonCompliant |
|NonCompliant |Data przeszła|NonCompliant|
|NonCompliant |Data przyszła|InGracePeriod|

Aby uzyskać więcej informacji na temat monitorowania zasad zgodności urządzeń, zobacz [Monitor Intune Device compliance policies](compliance-policy-monitor.md) (Monitorowanie zasad zgodności urządzeń w usłudze Intune).

### <a name="assign-a-resulting-compliance-policy-status"></a>Przypisywanie wynikowego stanu zasad zgodności

Jeśli urządzenie ma wiele zasad zgodności i dla co najmniej dwóch przypisanych zasad zgodności ma ono różne stany zgodności, zostanie przypisany jeden wynikowy stan zgodności. To przypisanie jest oparte na poziomie ważności koncepcyjnej przypisanym do poszczególnych stanów zgodności. Poszczególnym stanom zgodności odpowiadają następujące poziomy ważności:

|Stan  |Ważność  |
|---------|---------|
|Nieznane     |1|
|NotApplicable     |2|
|Zgodny|3|
|InGracePeriod|4|
|NonCompliant|5|
|Error|6|

Jeśli urządzenie ma wiele zasad zgodności, do urządzenia jest przypisywany najwyższy spośród poziomów ważności wszystkich zasad.

Na przykład urządzenie może mieć przypisane trzy rodzaje zasad zgodności: stan Unknown (nieznany, ważność = 1), stan Compliant (zgodne, ważność = 3) i stan InGracePeriod (prolongata, ważność = 4). Stan InGracePeriod ma najwyższy poziom ważności, dlatego wszystkie trzy zasady mają stan zgodności InGracePeriod.

## <a name="ways-to-use-device-compliance-policies"></a>Sposoby korzystania z zasad zgodności urządzeń

#### <a name="with-conditional-access"></a>Z dostępem warunkowym
W przypadku urządzeń zgodnych z regułami zasad możesz udzielić im dostępu do poczty e-mail i innych zasobów firmy. Jeśli urządzenia nie są zgodne z regułami zasad, to nie uzyskają dostępu do zasobów firmy. To jest dostęp warunkowy.

#### <a name="without-conditional-access"></a>Bez dostępu warunkowego
Zasady zgodności można również stosować bez dostępu warunkowego. Jeśli zasady zgodności są stosowane niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład można uzyskać raport z liczbą urządzeń, które nie są szyfrowane, lub z informacją o urządzeniach, w których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Jeśli zasady zgodności są stosowane bez dostępu warunkowego, dostęp do zasobów firmy nie jest ograniczany.

## <a name="ways-to-deploy-device-compliance-policies"></a>Sposoby wdrażania zasad zgodności urządzeń
Zasady zgodności można wdrożyć dla użytkowników w grupach użytkowników lub urządzeń w grupach urządzeń. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność wszystkich urządzeń użytkownika. Na urządzeniach z systemem Windows 10 w wersji 1803 lub nowszej zaleca się wdrażanie do grupy urządzeń, *jeśli* użytkownik podstawowy nie zarejestrował urządzenia. Użycie grup urządzeń w tym scenariuszu ułatwia raportowanie zgodności.

Zestaw wbudowanych **ustawień zasad zgodności** (witryna Azure Portal > Zgodność urządzenia) ocenianych na wszystkich urządzeniach zarejestrowanych w usłudze Intune. Należą do nich:

- **Oznacz urządzenia bez przypisanych zasad zgodności jako**: ta właściwość ma dwie wartości:

  - **Zgodne**: funkcja zabezpieczeń wyłączona
  - **Niezgodne** (domyślna): funkcja zabezpieczeń włączona

  Jeśli urządzenie nie ma przypisanych zasad zgodności, jest ono traktowane jako niezgodne. Domyślnie urządzenia są oznaczone jako **Zgodne**. Jeśli korzystasz z dostępu warunkowego, zalecamy zmianę ustawienia na **Niezgodne**. Jeśli użytkownik jest niezgodny, ponieważ zasady nie są przypisane, w aplikacji Portal firmy zostanie wyświetlony komunikat `No compliance policies have been assigned`.

- **Rozszerzone wykrywanie jailbreaku**: włączenie tego ustawienia powoduje, że urządzenia z systemem iOS są częściej ewidencjonowane w usłudze Intune. Włączenie tej właściwości powoduje użycie usług lokalizacyjnych urządzenia i wpływa na użycie baterii. Dane lokalizacji użytkownika nie są przechowywane przez usługę Intune.

  Włączenie tego ustawienia wymaga, aby na urządzeniach:
  - Włączyć usługi lokalizacyjne na poziomie systemu operacyjnego
  - Zezwolić aplikacji Portal firmy na użycie usług lokalizacyjnych
  - Oceniać i zgłaszać stan jailbreaku do usługi Intune co najmniej raz na 72 godziny. Jeśli te warunki nie są spełnione, urządzenie jest oznaczane jako niezgodne. Ocena jest wyzwalana przez otwarcie aplikacji Portal firmy lub fizyczne przeniesienie urządzenia o 500 metrów lub więcej.

- **Okres ważności stanu zgodności (dni)**: podaj okres zgłaszania stanu urządzenia dla wszystkich odebranych zasad zgodności. Urządzenia, które nie zwrócą stanu w tym okresie, są traktowane jako niezgodne. Wartość domyślna to 30 dni.

Wszystkie urządzenia mają **wbudowane zasady zgodności urządzeń** (witryna Azure Portal > Zgodność urządzenia > Zgodność z zasadami). Wbudowane zasady umożliwiają monitorowanie tych ustawień.

Aby uzyskać informacje o czasie potrzebnym na odebranie zasad przez urządzenia mobilne po wdrożeniu tych zasad, zobacz artykuł [Rozwiązywanie problemów z profilami urządzeń](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Raporty zgodności to doskonały sposób na sprawdzanie stanu urządzeń. Przewodnik znajduje się w artykule [Monitor compliance policies (Monitorowanie zasad zgodności)](compliance-policy-monitor.md).

### <a name="actions-for-noncompliance"></a>Akcje w przypadku niezgodności
Istnieje możliwość skonfigurowania uporządkowanej w czasie sekwencji akcji, które stosują się do urządzeń niespełniających kryteriów zasad zgodności. Te akcje dotyczące niezgodności można zautomatyzować zgodnie z opisem w artykule [Automate actions for noncompliance (Automatyzowanie akcji dla stanu niezgodności)](actions-for-noncompliance.md).

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasyczny portal Azure a Witryna Azure Portal

Główna różnica w przypadku korzystania z zasad zgodności urządzeń w witrynie Azure Portal:

- W witrynie Azure Portal zasady zgodności są tworzone oddzielnie dla każdej z obsługiwanych platform.
- W klasycznym portalu Azure zasady zgodności urządzeń są wspólne dla wszystkich obsługiwanych platform.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Zasady zgodności urządzeń w klasycznym portalu Azure i w witrynie Azure Portal

Zasady zgodności urządzeń tworzone w [klasycznym portalu Azure](https://manage.microsoft.com) nie są dostępne w [witrynie Azure Portal](https://portal.azure.com). Nadal jednak będą one stosowane dla użytkowników i będzie możliwe zarządzanie nimi za pośrednictwem klasycznego portalu Azure.

Aby korzystać z funkcji dotyczących zgodności urządzeń w witrynie Azure Portal, musisz utworzyć tam nowe zasady zgodności urządzeń. Jeśli w witrynie Azure Portal przypiszesz zasady zgodności urządzeń do użytkownika, do którego zostały również przypisane zasady zgodności urządzeń z portalu klasycznego, to zasady zgodności urządzeń z witryny Azure Portal będą mieć pierwszeństwo przed zasadami utworzonymi w portalu klasycznym.

## <a name="next-steps"></a>Następne kroki

- Utwórz zasady zgodności urządzeń dla następujących platform:

  - [Android](compliance-policy-create-android.md)
  - [Profil służbowy systemu Android](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Aby uzyskać informacje na temat jednostek zasad magazynu danych usługi Intune, zobacz [Dokumentacja jednostek zasad](reports-ref-policy.md).
