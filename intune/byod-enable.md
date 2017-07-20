---
title: "Włączanie modelu BYOD w usłudze Microsoft Intune"
description: 
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 880b83a63eefe13a96ab8838c7092c185aa32cd0
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2017
---
# <a name="enable-byod-with-intune"></a>Włączanie modelu BYOD w usłudze Intune

Ten temat zawiera opis ogólnego przepływu pracy dotyczącego konfigurowania usługi Intune tak, aby organizacja mogła korzystać z rozwiązania typu „przynieś własne urządzenie” (BYOD). Zadanie to zostało uporządkowane w postaci trzech procesów oraz linków do pomocniczych tematów z instrukcjami.

Przepływ pracy został podzielony na trzy poniższe procesy. Aspekty poszczególnych procesów można dostosować tak, aby spełnić wymagania organizacji.

-   **[Rejestrowanie urządzeń i sprawdzanie zgodności](#enroll-devices-and-check-for-compliance)** — ta sekcja opisuje, jak można umożliwić użytkownikom rejestrowanie urządzeń osobistych do zarządzania przez usługę Intune. Usługa Intune zarządza urządzeniami z systemami iOS, macOS, Android i Windows. Ta sekcja opisuje również sposób wdrażania zasad na urządzeniach oraz sprawdzania, czy spełniają one podstawowe wymagania dotyczące zabezpieczeń.

- **[Udostępnianie zasobów firmy](#provide-access-to-company-resources)** — w tej sekcji przedstawiono, jak z pomocą działu IT użytkownicy mogą łatwo i bezpiecznie uzyskiwać dostęp do zasobów firmy. W tym celu należy wdrożyć profile dostępu na zarządzanych urządzeniach. W tej sekcji wyjaśniono również, jak zarządzać wdrożeniami aplikacji kupionych w ramach zakupów zbiorczych przy użyciu usługi Intune.

-   **[Ochrona danych firmowych](#protect-company-data)** — w tej sekcji wyjaśniono, jak zapewnić warunkowy dostęp do zasobów firmowych, chronić się przed utratą danych oraz usuwać firmowe aplikacje i dane z urządzeń, które nie są już potrzebne do pracy albo zostały zagubione albo skradzione.

[![Diagram przedstawiający ogólny przepływ pracy umożliwiający stosowanie rozwiązania BYOD z usługą Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Przed rozpoczęciem
Aby umożliwić użytkownikom rejestrowanie urządzeń, musisz najpierw przygotować samą usługę Intune. W tym celu [przypisz licencje do użytkowników](licenses-assign.md) i [ustaw urząd zarządzania urządzeniami przenośnymi](mdm-authority-set.md).

W tym czasie pamiętaj również o [dostosowaniu portalu firmy](company-portal-customize.md). Dodaj znaki firmowe i udostępnij użytkownikom informacje dotyczące pomocy technicznej. Spowoduje to utworzenie zaufanego środowiska rejestracji i pomocy technicznej dla użytkowników.

## <a name="enroll-devices-and-check-for-compliance"></a>Rejestrowanie urządzeń i sprawdzanie zgodności

Po przygotowaniu usługi Intune musisz spełnić różne wymagania dotyczące rejestracji dla różnych typów urządzeń, którymi chcesz zarządzać. Proces rejestrowania urządzeń do zarządzania jest prosty, ale różni się nieco w zależności od typu urządzenia.

-   **Urządzenia z systemem iOS i Mac** — aby rejestrować urządzenia iPad i iPhone oraz urządzenia z systemem MacOS, należy uzyskać [certyfikat usługi Apple Push Notification service (APNs)](apple-mdm-push-certificate-get.md). Po przekazaniu certyfikatu usługi APNs do usługi Intune użytkownicy mogą [rejestrować urządzenia z systemem iOS](/intune-user-help/enroll-your-device-in-intune-ios) za pomocą aplikacji Portal firmy, a także korzystać z witryny Portal firmy w celu [rejestrowania urządzeń z systemem MacOS](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Urządzenia z systemem Android** — żadne działania nie są konieczne, aby przygotować usługę Intune do rejestrowania urządzeń z systemem Android. Użytkownicy mogą po prostu [rejestrować swoje urządzenia z systemem Android](/intune-user-help/enroll-your-device-in-intune-android.md) na potrzeby zarządzania przy użyciu aplikacji Portal firmy dostępnej w sklepie Google Play.

-   **Telefony i komputery z systemem Windows** — należy [ustawić alias DNS dla serwera rejestracji](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium), aby ułatwić rejestrowanie urządzeń z systemem Windows. Użytkownicy mogą również [rejestrować urządzenia z systemem Windows](/intune-user-help/enroll-your-w10-phone-or-w10-pc-windows) przez dodanie konta służbowego.

  - Jeśli korzystasz z usługi Azure AD Premium, możesz ułatwić użytkownikom rejestrowanie urządzeń z systemem Windows, [włączając funkcję automatycznego rejestrowania](windows-enroll.md). Ta funkcja automatycznie rejestruje urządzenie w usłudze Intune, gdy użytkownik dodaje konto służbowe w celu zarejestrowania urządzenia osobistego. Działa ona również w przypadku urządzenia należącego do firmy, które jest przyłączane do usługi Azure AD w organizacji.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Sprawdzanie, czy zarządzane urządzenia spełniają podstawowe wymogi bezpieczeństwa

Gdy użytkownicy zarejestrują swoje urządzenia do zarządzania, dział IT musi upewnić się, że urządzenia używane do uzyskiwania dostępu do danych i aplikacji firmowych spełniają podstawowe wymogi bezpieczeństwa. Te reguły mogą obejmować wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzeń oraz szyfrowanie danych przechowywanych na urządzeniach. Zestaw takich reguł jest nazywany [zasadami zgodności](device-compliance.md).

Podczas [tworzenia zasad zgodności](device-compliance-get-started.md) dla użytkownika wszystkie urządzenia zarządzane przez użytkownika w usłudze Intune są sprawdzane pod kątem tego, czy spełniają podstawowe wymogi bezpieczeństwa zdefiniowane w zasadach BYOD. Gdy urządzenie zostanie sprawdzone pod kątem zgodności z zasadami, jego stan jest zgłaszany do usługi Intune. W niektórych przypadkach użytkownicy mogą zostać poproszeni o poprawienie ustawień, takich jak numer PIN lub szyfrowanie urządzenia. W innych sytuacjach aplikacja Portal firmy po prostu powiadamia użytkownika o ustawieniach, które nie są zgodne z naszymi zasadami.

## <a name="provide-access-to-company-resources"></a>Zapewnianie dostępu do zasobów firmowych

Pierwszą rzeczą, której większość pracowników chce od swoich urządzeń przenośnych, jest dostęp do firmowej poczty e-mail i dokumentów. Oczekują, że będzie to możliwe bez konieczności wykonywania złożonych procedur ani kontaktowania się z pomocą techniczną. Usługa Intune ułatwia [tworzenie i wdrażanie ustawień poczty e-mail](conditional-access-intune-common-ways-use.md) do natywnych aplikacji poczty e-mail wstępnie zainstalowanych na urządzeniach przenośnych.
<!--- this was old link: (https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune). check with Andre--->

> [!NOTE]
> Usługa Intune obsługuje konfigurację profilu poczty e-mail programu Android for Work dla aplikacji poczty e-mail Gmail i Nine Work ze sklepu Google Play.

Usługa Intune pomaga również kontrolować i chronić dostęp do lokalnych danych firmowych, gdy użytkownicy pracują poza siedzibą firmy. Profile sieci [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), sieci [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) i poczty e-mail w usłudze Intune działają razem w celu udzielania użytkownikom dostępu do plików i zasobów potrzebnych im do pracy niezależnie od miejsca, w którym się znajdują. Za pomocą serwera proxy aplikacji usługi Azure Active Directory oraz dostępu warunkowego można uzyskiwać bezpieczny dostęp do lokalnie hostowanych usług i aplikacji sieci Web firmy oraz chronić je.

### <a name="manage-volume-purchased-apps"></a>Zarządzanie aplikacjami nabytymi w ramach zakupów zbiorczych
Usługa Intune ułatwia wykonywanie następujących czynności:
* Importowanie informacji o licencjach zbiorczych z dowolnego sklepu z aplikacjami
* Śledzenie liczby użytych licencji
* Uniemożliwianie użytkownikom instalowania większej liczby kopii aplikacji niż posiadana
* [Dostarczanie aplikacji ze sklepu na urządzenia zarządzane](apps-deploy.md)
* Kierowanie aplikacji na urządzenia niezarządzane przy użyciu witryny internetowej portalu firmy

Za pomocą usługi Intune można również zarządzać aplikacjami zakupionymi zbiorczo w sklepie iOS App Store i Sklepie Windows dla firm oraz wdrażać te aplikacje. Dzięki temu można zmniejszyć koszty administracyjne związane ze monitorowaniem aplikacji nabytych w ramach zakupów zbiorczych.

> [!TIP]
> Możesz [skonfigurować logowanie jednokrotne (SSO) przy użyciu programu Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Logowanie jednokrotne umożliwia użytkownikom logowanie do aplikacji przy użyciu nazwy i hasła użytkownika domeny, których używają lokalnie. Ponadto można [zapewnić dostęp internetowy do hostowanych lokalnie aplikacji sieci Web](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) za pomocą serwera proxy aplikacji usługi Azure Active Directory.

-   [Zarządzanie aplikacjami nabytymi w ramach zakupów zbiorczych na urządzeniach z systemem iOS](vpp-apps-ios.md). Wiele licencji dla aplikacji z systemem iOS można zakupić za pośrednictwem programu [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/). Należy skonfigurować konto VPP w witrynie internetowej firmy Apple i przekazać token VPP firmy Apple do usługi Intune. Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

-   [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm](windows-store-for-business.md). [Sklep Windows dla firm](https://www.microsoft.com/business-store) to miejsce, w którym można znaleźć i zakupić aplikacje dla całej organizacji, pojedynczo lub zbiorczo. Łącząc sklep z usługą Intune, można zarządzać aplikacjami nabytymi w ramach zakupów zbiorczych bezpośrednio w portalu usługi Intune.

## <a name="protect-company-data"></a>Ochrona zasobów firmy

Usługa Intune chroni dane firmowe dzięki zastosowaniu wielu warstw technologicznych. W warstwie tożsamości funkcja dostępu warunkowego chroni dostęp do usług. Dostęp warunkowy umożliwia tylko zarządzanym i zgodnym urządzeniom dostęp do zasobów firmy. W warstwie aplikacji klienta funkcja zarządzania aplikacjami mobilnymi chroni przed utratą danych.  Zasady ochrony aplikacji uniemożliwiają przenoszenie danych do aplikacji lub lokalizacji magazynu, które nie są chronione. Zasady te pozwalają również na czyszczenie danych firmowych w przypadku utraty lub kradzieży urządzenia.

### <a name="enforce-conditional-access-to-company-resources"></a>Wymuszanie dostępu warunkowego do zasobów firmy

Zasady zgodności można połączyć z [zasadami dostępu warunkowego](device-compliance.md), aby sprawdzić, czy urządzenia spełniają podstawowe wymogi bezpieczeństwa określone w zasadach BYOD. Jeśli urządzenie nie spełnia wymagań, zasady są wymuszane i następuje odmowa dostępu do momentu, gdy urządzenie będzie spełniać wymagania związane z zasadami. Dzięki temu tylko zarządzane i zgodne urządzenia będą miały dostęp do danych firmowych z takich usług jak Exchange ([lokalna instalacja programu Exchange](exchange-connector-install.md) lub [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online czy Skype dla firm Online.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Zasady dostępu warunkowego nie będą działać, jeśli nie wdrożono żadnych zasad zgodności, względem których można by zweryfikować zgodność.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Ochrona przed utratą danych firmowych danych za pomocą zasad ochrony aplikacji

Dzięki zasadom ochrony aplikacji w usłudze Intune możesz wybrać sposób uzyskiwania dostępu do danych — z rejestracją urządzeń lub bez niej. Ta wszechstronność umożliwia ochronę danych firmowych, dlatego nawet wtedy, gdy użytkownik nie zarejestruje urządzenia w usłudze Intune, nadal będzie mógł bezpiecznie uzyskiwać dostęp do danych firmowych.

Do ochrony danych firmowych, do których użytkownicy uzyskują dostęp ze swoich urządzeń z systemami iOS i Android, można używać [zasad zarządzania aplikacjami mobilnymi w usłudze Intune](app-protection-policies.md). Używając tych zasad na poziomie aplikacji, można kontrolować sposób używania i udostępniania danych firmowych przez użytkowników, nawet jeśli samo urządzenie nie jest zarządzane przez usługę Intune.

W przypadku zarządzanych urządzeń z systemem Windows 10 to samo można osiągnąć, korzystając z [zasad funkcji Windows Information Protection (WIP)](app-protection-policies-configure-windows-10.md). Te zasady działają bez zakłócania działania środowiska pracowników. Nie wymagają one zmian w środowisku sieci lub innych aplikacjach.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Usuwanie danych firmowych bez ingerowania w dane osobiste

Gdy urządzenie nie jest już potrzebne do pracy, jego przeznaczenie zmieni się lub po prostu zostanie zgubione, musisz mieć możliwość usunięcia z niego aplikacji i danych firmy. Do tego celu można użyć możliwości selektywnego i pełnego czyszczenia danych usługi Intune. Użytkownicy mogą również zdalnie wyczyścić własne urządzenia z Portalu firmy usługi Intune, jeśli zarejestrowali je w usłudze Intune.

[Pełne czyszczenie danych](devices-wipe.md) przywraca domyślne ustawienia fabryczne urządzenia przez usunięcie wszystkich danych i ustawień użytkownika. [Selektywne czyszczenie danych ](devices-wipe.md#selective-wipe) powoduje usunięcie tylko danych firmy z urządzenia i pozostawienie osobistych danych użytkowników bez zmian.

Po zainicjowaniu urządzenie natychmiast rozpoczyna proces czyszczenia selektywnego w celu wyłączenia go z zarządzania. Po zakończeniu procesu wszystkie dane firmy będą usunięte, a nazwa urządzenia zostanie usunięta z konsoli administratora usługi Intune. Kończy to cykl zarządzania urządzeniem.
