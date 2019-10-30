---
title: Zasady zgodności urządzeń w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: 'Wprowadzenie do następujących zagadnień: korzystanie z zasad zgodności urządzeń, omówienie stanu i poziomów ważności, korzystanie ze stanu InGracePeriod, praca z dostępem warunkowym, obsługa urządzeń bez przypisanych zasad oraz różnice w zgodności między witryną Azure Portal i portalem klasycznym w usłudze Microsoft Intune'
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 967bf9937c71ff3ca7277f43fd969291eb5af6de
ms.sourcegitcommit: c2e62f1ebdf75599c8e544287123c602f0f15f2b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "72749168"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Ustawianie zasad na urządzeniach w celu umożliwienia dostępu do zasobów w organizacji za pomocą usługi Intune

Wiele rozwiązań do zarządzania urządzeniami mobilnymi (MDM) pomaga chronić dane organizacji, wymagając od użytkowników i urządzeń spełnienia pewnych wymagań. W usłudze Intune ta funkcja jest nazywana „zasadami zgodności”. Zasady zgodności definiują reguły i ustawienia, które użytkownicy i urządzenia muszą spełnić, aby były zgodne. Używając tych zasad w połączeniu z dostępem warunkowym, administratorzy mogą blokować użytkowników i urządzenia niespełniające warunków reguł.

Na przykład administrator usługi Intune może wymagać, aby:

- Użytkownicy końcowi używali hasła do uzyskiwania dostępu do danych organizacji na urządzeniach przenośnych
- Urządzenie nie miało złamanych zabezpieczeń ani odblokowanego dostępu do konta root
- Na urządzeniu zainstalowano minimalną lub maksymalną wersję systemu operacyjnego
- Poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia

Ta funkcja służy również do monitorowania stanu zgodności na urządzeniach w organizacji.

> [!IMPORTANT]
> Usługa Intune wykonuje wszystkie oceny zgodności na urządzeniu zgodnie z jego harmonogramem ewidencjonowania. Szacowane czasy odświeżania znajdują się w sekcji dotyczącej [cyklów odświeżania zasad i profilów](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

- When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

- 3 days after initial noncompliance state, a follow up reminder is sent to the user.

- 5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

- 7 days after initial noncompliance state, access to company resources is blocked. This requires that you have Conditional Access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement Conditional Access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="device-compliance-policies-work-with-azure-ad"></a>Współdziałanie zasad zgodności urządzeń z usługą Azure AD

Usługa Intune używa [dostępu warunkowego](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) usługi Azure Active Directory (AD) (link otwiera inną witrynę internetową Docs), aby ułatwić wymuszanie zgodności. Gdy urządzenie jest rejestrowane w usłudze Intune, rozpoczyna się proces rejestracji w usłudze Azure AD, a informacje o urządzeniu są aktualizowane w usłudze Azure AD. Jedną z kluczowych informacji jest stan zgodności urządzenia. Stan zgodności jest używany przez zasady dostępu warunkowego do blokowania lub udostępniania poczty e-mail i innych zasobów organizacji.

- Artykuł [Co to jest zarządzanie urządzeniami w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction) to fantastyczny zasób dotyczący przyczyn i sposobów rejestrowania urządzeń w usłudze Azure AD.

- Ta funkcja została opisana w sekcjach dotyczących [dostępu warunkowego](conditional-access.md) i [typowych sposobów korzystania z dostępu warunkowego](conditional-access-intune-common-ways-use.md), ponieważ jest związana z usługą Intune.

## <a name="ways-to-use-device-compliance-policies"></a>Sposoby korzystania z zasad zgodności urządzeń

### <a name="with-conditional-access"></a>Z dostępem warunkowym

W przypadku urządzeń zgodnych z regułami zasad możesz udzielić im dostępu do poczty e-mail i innych zasobów organizacji. Jeśli urządzenia nie są zgodne z regułami zasad, nie uzyskają dostępu do zasobów organizacji. To jest dostęp warunkowy.

### <a name="without-conditional-access"></a>Bez dostępu warunkowego

Zasady zgodności można stosować również bez dostępu warunkowego. Jeśli zasady zgodności są stosowane niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład można uzyskać raport z liczbą urządzeń, które nie są szyfrowane, lub z informacją o urządzeniach, w których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Jeśli zasady zgodności są stosowane bez dostępu warunkowego, dostęp do zasobów organizacji nie jest ograniczany.

## <a name="ways-to-deploy-device-compliance-policies"></a>Sposoby wdrażania zasad zgodności urządzeń

Zasady zgodności można wdrożyć dla użytkowników w grupach użytkowników lub urządzeń w grupach urządzeń. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność wszystkich urządzeń użytkownika. Na urządzeniach z systemem Windows 10 w wersji 1803 lub nowszej zaleca się wdrażanie do grupy urządzeń, *jeśli* użytkownik podstawowy nie zarejestrował urządzenia. Użycie grup urządzeń w tym scenariuszu ułatwia raportowanie zgodności.

Usługa Intune oferuje również zestaw wbudowanych ustawień zasad zgodności. Następujące zasady wbudowane są oceniane na wszystkich urządzeniach zarejestrowanych w usłudze Intune:

- **Oznacz urządzenia bez przypisanych zasad zgodności jako**: ta właściwość ma dwie wartości:

  - **Zgodne** (*domyślna*): funkcja zabezpieczeń wyłączona
  - **Niezgodne**: funkcja zabezpieczeń włączona

  Jeśli do urządzenia nie są przypisane zasady zgodności, jest ono domyślnie traktowane jako zgodne. Jeśli używasz dostępu warunkowego wykorzystując zasady zgodności, zalecamy zmianę domyślnego ustawienia na **Niezgodne**. Jeśli użytkownik końcowy jest niezgodny, ponieważ zasady nie zostały przypisane, w [aplikacji Portal firmy](../apps/company-portal-app.md) zostanie wyświetlony komunikat `No compliance policies have been assigned`.

- **Rozszerzone wykrywanie jailbreaku**: włączenie tego ustawienia powoduje, że urządzenia z systemem iOS są częściej ewidencjonowane w usłudze Intune. Włączenie tej właściwości powoduje użycie usług lokalizacyjnych urządzenia i wpływa na użycie baterii. Dane lokalizacji użytkownika nie są przechowywane przez usługę Intune.

  Włączenie tego ustawienia wymaga, aby na urządzeniach:
  - Włączyć usługi lokalizacyjne na poziomie systemu operacyjnego.
  - Zezwolić aplikacji Portal firmy na użycie usług lokalizacyjnych.
  - Oceniać i zgłaszać stan jailbreaku do usługi Intune co najmniej raz na 72 godziny. Jeśli te warunki nie są spełnione, urządzenie jest oznaczane jako niezgodne. Ocena jest wyzwalana przez otwarcie aplikacji Portal firmy lub fizyczne przeniesienie urządzenia o 500 metrów lub więcej. Jeśli urządzenie nie zostanie przeniesione o 500 metrów w ciągu 72 godzin, użytkownik musi otworzyć aplikację Portal firmy w celu przeprowadzenia rozszerzonej oceny pod kątem wykonania jailbreaku.

- **Okres ważności stanu zgodności (dni)** : podaj okres zgłaszania stanu urządzenia dla wszystkich odebranych zasad zgodności. Urządzenia, które nie zwrócą stanu w tym okresie, są traktowane jako niezgodne. Wartość domyślna to 30 dni.

Te wbudowane zasady umożliwiają monitorowanie tych ustawień. Usługa Intune również [odświeża lub sprawdza aktualizacje](create-compliance-policy.md#refresh-cycle-times) w różnych interwałach w zależności od platformy urządzenia. Pomocnym zasobem jest artykuł [Typowe pytania, problemy i rozwiązania związane z zasadami i profilami urządzeń w usłudze Microsoft Intune](../configuration/device-profile-troubleshoot.md).

Raporty zgodności to doskonały sposób na sprawdzanie stanu urządzeń. Wskazówki można znaleźć w artykule [Monitor compliance policies](compliance-policy-monitor.md) (Monitorowanie zasad zgodności).

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Niezgodność i dostęp warunkowy na różnych platformach

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

---------------------------

|**Ustawienie zasad**| **Platforma** |
| --- | ----|
| **Konfiguracja kodu PIN lub hasła** | - **System Android 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Android Enterprise**: Poddane kwarantannie  <br>  <br>- **System iOS 8.0 lub nowszy**: Skorygowane<br>- **System macOS 10.11 lub nowszy**: Skorygowane  <br>  <br>- **System Windows 8.1 lub nowszy**: Skorygowane<br>- **System Windows Phone 8.1 lub nowszy**: Skorygowane|
| **Szyfrowanie urządzenia** | - **System Android 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Android Enterprise**: Poddane kwarantannie<br><br>- **System iOS 8.0 lub nowszy**: Skorygowane (przez ustawienie kodu PIN)<br>- **System macOS 10.11 lub nowszy**: Skorygowane (przez ustawienie kodu PIN)<br><br>- **System Windows 8.1 lub nowszy**: Nie dotyczy<br>- **System Windows Phone 8.1 lub nowszy**: Skorygowane |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | - **System Android 4.0 lub nowszy**: Poddane kwarantannie (to nie jest ustawienie)<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Poddane kwarantannie (to nie jest ustawienie)<br>- **System Android Enterprise**: Poddane kwarantannie (to nie jest ustawienie)<br><br>- **System iOS 8.0 lub nowszy**: Poddane kwarantannie (to nie jest ustawienie)<br>- **System macOS 10.11 lub nowszy**: Nie dotyczy<br><br>- **System Windows 8.1 lub nowszy**: Nie dotyczy<br>- **System Windows Phone 8.1 lub nowszy**: Nie dotyczy |
| **Profil e-mail** | - **System Android 4.0 lub nowszy**: Nie dotyczy<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Nie dotyczy<br>- **System Android Enterprise**: Nie dotyczy<br><br>- **System iOS 8.0 lub nowszy**: Poddane kwarantannie<br>- **System macOS 10.11 lub nowszy**: Poddane kwarantannie<br><br>- **System Windows 8.1 lub nowszy**: Nie dotyczy<br>- **System Windows Phone 8.1 lub nowszy**: Nie dotyczy |
| **Minimalna wersja systemu operacyjnego** | - **System Android 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Android Enterprise**: Poddane kwarantannie<br><br>- **System iOS 8.0 lub nowszy**: Poddane kwarantannie<br>- **System macOS 10.11 lub nowszy**: Poddane kwarantannie<br><br>- **System Windows 8.1 lub nowszy**: Poddane kwarantannie<br>- **System Windows Phone 8.1 lub nowszy**: Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | - **System Android 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Poddane kwarantannie<br>- **System Android Enterprise**: Poddane kwarantannie<br><br>- **System iOS 8.0 lub nowszy**: Poddane kwarantannie<br>- **System macOS 10.11 lub nowszy**: Poddane kwarantannie<br><br>- **System Windows 8.1 lub nowszy**: Poddane kwarantannie<br>- **System Windows Phone 8.1 lub nowszy**: Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** | - **System Android 4.0 lub nowszy**: Nie dotyczy<br>- **System Samsung Knox Standard 4.0 lub nowszy**: Nie dotyczy<br>- **System Android Enterprise**: Nie dotyczy<br><br>- **System iOS 8.0 lub nowszy**: Nie dotyczy<br>- **System macOS 10.11 lub nowszy**: Nie dotyczy<br><br>- **Systemy Windows 10 i Windows 10 Mobile**: Poddane kwarantannie<br>- **System Windows 8.1 lub nowszy**: Poddane kwarantannie<br>- **System Windows Phone 8.1 lub nowszy**: Nie dotyczy |

---------------------------

**Skorygowane**: system operacyjny urządzenia wymusza zgodność. Na przykład użytkownik jest zmuszony do ustawienia kodu PIN.

**Poddane kwarantannie**: system operacyjny urządzenia nie wymusza zgodności. Na przykład urządzenia z systemami Android i Android Enterprise nie zmuszają użytkownika do szyfrowania urządzeń. Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Jeśli użytkownik podlega zasadom dostępu warunkowego, urządzenie zostanie zablokowane.
- Aplikacja Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasyczny portal Azure a Witryna Azure Portal

Główna różnica w przypadku korzystania z zasad zgodności urządzeń w witrynie Azure Portal:

- W witrynie Azure Portal zasady zgodności są tworzone oddzielnie dla każdej z obsługiwanych platform.
- W klasycznym portalu Azure zasady zgodności urządzeń są wspólne dla wszystkich obsługiwanych platform.

<!--- - In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

- In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

Zasady zgodności urządzeń tworzone w [klasycznym portalu Azure](https://manage.microsoft.com) nie są dostępne w [witrynie Azure Portal](https://portal.azure.com). Nadal jednak będą one stosowane dla użytkowników i będzie możliwe zarządzanie nimi za pośrednictwem klasycznego portalu Azure.

Aby korzystać z funkcji dotyczących zgodności urządzeń w witrynie Azure Portal, musisz utworzyć tam nowe zasady zgodności urządzeń. Jeśli w witrynie Azure Portal przypiszesz zasady zgodności urządzeń do użytkownika, do którego zostały również przypisane zasady zgodności urządzeń z portalu klasycznego, to zasady zgodności urządzeń z witryny Azure Portal będą mieć pierwszeństwo przed zasadami utworzonymi w portalu klasycznym.

## <a name="next-steps"></a>Następne kroki

- [Utwórz zasady](create-compliance-policy.md) i wyświetl wymagania wstępne.
- Zobacz ustawienia zgodności dla różnych platform urządzeń:

  - [Android](compliance-policy-create-android.md)
  - [Android Enterprise](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows Holographic for Business](compliance-policy-create-windows.md#windows-holographic-for-business)
  - [Windows Phone 8.1](compliance-policy-create-windows-8-1.md)
  - [Windows 8.1 lub nowszy](compliance-policy-create-windows-8-1.md)
  - [Windows 10 lub nowszy](compliance-policy-create-windows.md)

- [Dokumentacja jednostek zasad](../reports-ref-policy.md) zawiera informacje na temat jednostek zasad magazynu Data Warehouse w usłudze Intune.
