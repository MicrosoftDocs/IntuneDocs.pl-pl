---
title: Co to jest usługa Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się, jak usługa Microsoft Intune pełni rolę składnika zarządzania urządzeniami przenośnymi (MDM, mobile device management) i zarządzania aplikacjami mobilnymi (MAM, mobile app management) rozwiązania Enterprise Mobility + Security oraz jak pomaga w ochronie danych firmy.
keywords: co to jest usługa Intune
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/14/2019
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3c03c67a99b78804c999250f8d1148a4b3d1d97
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504767"
---
# <a name="microsoft-intune-is-an-mdm-and-mam-provider-for-your-devices"></a>Usługa Microsoft Intune jest dostawcą rozwiązań zarządzania urządzeniami mobilnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM) dla urządzeń

Microsoft Intune to usługa chmurowa, której głównym celem jest zarządzanie urządzeniami mobilnymi (MDM, mobile device management) i zarządzanie aplikacjami mobilnymi (MAM, mobile application management). Usługa Intune jest zawarta w pakiecie [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) firmy Microsoft i pozwala użytkownikom na wydajną pracę przy zachowaniu ochrony danych organizacji. Integruje się ona z innymi usługami, takimi jak Microsoft 365 i Azure Active Directory (Azure AD) w celu kontrolowania dostępu użytkowników do poszczególnych zasobów, oraz z usługą Azure Information Protection w celu ochrony danych. Używając jej wraz z rozwiązaniem Microsoft 365, możesz zapewnić produktywność pracowników na wszystkich urządzeniach, z których korzystają, przy jednoczesnym zachowaniu bezpieczeństwa informacji należących do organizacji.

![Obraz architektury usługi Intune](./media/what-is-intune/intunearch_sm.png)

Wyświetl [powiększony](./media/what-is-intune/intunearchitecture.svg) diagram architektury usługi Intune.

Usługa Intune umożliwia:

- Wybranie opcji działania w 100% w chmurze przy użyciu usługi Intune lub opcji [współzarządzania](https://docs.microsoft.com/sccm/comanage/overview) za pomocą rozwiązania Configuration Manager i usługi Intune.
- Ustawienie reguł i skonfigurowanie ustawień na urządzeniach osobistych i należących do organizacji w celu uzyskiwania dostępu do danych i sieci.
- Wdrażanie i uwierzytelnianie aplikacji na urządzeniach — lokalnie i na urządzeniach przenośnych.
- Ochronę informacji firmowych za pomocą kontrolowania sposobu, w jaki użytkownicy uzyskują dostęp do informacji i je udostępniają.
- Zapewnienie zgodności urządzeń i aplikacji z wymaganiami bezpieczeństwa.

## <a name="manage-devices"></a>Zarządzaj urządzeniami

W usłudze Intune możesz zarządzać urządzeniami, korzystając z podejścia, które jest dla Ciebie odpowiednie. W przypadku urządzeń należących do organizacji możesz mieć pełną kontrolę nad urządzeniami — nad ustawieniami, funkcjami i zabezpieczeniami. W przypadku tego podejścia urządzenia i użytkownicy tych urządzeń rejestrują się w usłudze Intune. Po zarejestrowaniu otrzymują Twoje reguły i ustawienia za pośrednictwem zasad skonfigurowanych w usłudze Intune. Możesz na przykład ustawić wymaganie hasła i numeru PIN, utworzyć połączenie sieci VPN, skonfigurować ochronę przed zagrożeniami i nie tylko.

W przypadku urządzeń osobistych lub urządzeń BYOD użytkownicy mogą nie chcieć, aby administratorzy organizacji mieli nad nimi pełną kontrolę. W tym podejściu możesz dać użytkownikom opcje do wyboru. Na przykład użytkownicy [rejestrują](../enrollment/device-enrollment.md) swoje urządzenia, jeśli chcą mieć pełny dostęp do zasobów organizacji. Jeśli użytkownicy chcą mieć dostęp tylko do poczty e-mail lub aplikacji Microsoft Teams, możesz użyć zasad ochrony aplikacji, które wymagają uwierzytelniania wieloskładnikowego w celu korzystania z tych aplikacji.

Jeśli urządzenia są zarejestrowane i zarządzane w usłudze Intune, administratorzy mogą wykonywać następujące czynności:

- Wyświetlanie zarejestrowanych urządzeń i pobieranie spisu urządzeń uzyskujących dostęp do zasobów organizacji.
- Konfigurowanie urządzeń, aby spełniały standardy zabezpieczeń i kondycji. Na przykład prawdopodobnie zechcesz zablokować urządzenia ze zdjętymi zabezpieczeniami systemu.
- Wypychanie certyfikatów do urządzeń, aby użytkownicy mogli łatwo uzyskiwać dostęp do sieci Wi-Fi lub łączyć się z siecią firmową za pośrednictwem sieci VPN.
- Wyświetlanie raportów dotyczących użytkowników i urządzeń, które są zgodne i niezgodne.
- Usuwanie danych organizacji, jeśli urządzenie zostanie utracone, skradzione lub nie będzie już używane.

**Zasoby online**:

- [Co to jest rejestrowanie urządzenia?](../enrollment/device-enrollment.md)

- [Stosowanie funkcji i ustawień na urządzeniach przy użyciu profilów urządzeń](../configuration/device-profiles.md)

- [Ochrona danych za pomocą usługi Microsoft Intune](../protect/device-protect.md)

## <a name="manage-apps"></a>Zarządzanie aplikacjami

Zarządzanie aplikacjami mobilnymi (MAM) w usłudze Intune jest przeznaczone do ochrony danych organizacji na poziomie aplikacji, w tym także aplikacji niestandardowych i aplikacji ze sklepu. Rozwiązanie do zarządzania aplikacjami może być używane na urządzeniach należących do organizacji i na urządzeniach osobistych.

Gdy aplikacje są zarządzane w usłudze Intune, administratorzy mogą wykonywać następujące czynności:

- Dodawanie i przypisywanie aplikacji mobilnych do grup użytkowników i urządzeń, w tym do użytkowników w określonych grupach, urządzeń w określonych grupach i nie tylko.
- Konfigurowanie aplikacji w celu uruchamiania ich z włączonymi określonymi ustawieniami oraz aktualizowanie już istniejących aplikacji na urządzeniu.
- Wyświetlanie raportów na temat używanych aplikacji i śledzenie ich użycia.
- Wykonywanie czyszczenia selektywnego, czyli usuwanie z aplikacji tylko danych organizacji.

Jednym ze sposobów zapewniania bezpieczeństwa aplikacji mobilnych przez usługę Intune jest użycie **[zasad ochrony aplikacji](../apps/app-protection-policy.md)** . Zasady ochrony aplikacji:

- Używają tożsamości usługi Azure AD, aby odizolować dane organizacji od danych osobistych. Dzięki temu dział IT organizacji nie ma wglądu w informacje osobiste. Dane, do których dostęp jest uzyskiwany przy użyciu poświadczeń organizacji, są chronione za pomocą dodatkowych zabezpieczeń.
- Pomagają zabezpieczyć dostęp na urządzeniach osobistych przez ograniczenie akcji, które użytkownicy mogą wykonywać, takich jak kopiowanie i wklejanie, zapisywanie i przeglądanie.
- Mogą być tworzone i wdrażane na urządzeniach zarejestrowanych w usłudze Intune, zarejestrowanych w innej usłudze MDM lub nie zarejestrowanych w żadnej usłudze MDM. Na zarejestrowanych urządzeniach zasady ochrony aplikacji mogą stanowić dodatkową warstwę ochrony.

Na przykład użytkownik loguje się na urządzeniu przy użyciu poświadczeń organizacji. Tożsamość organizacji umożliwia dostęp do danych, do których nie można uzyskać dostępu za pomocą tożsamości osobistej. Podczas używania danych organizacji zasady ochrony aplikacji kontrolują sposób ich zapisywania i udostępniania. Kiedy użytkownicy logują się przy użyciu tożsamości osobistej, te same zabezpieczenia nie są stosowane. W ten sposób dział IT sprawuje kontrolę nad danymi organizacji, a użytkownik końcowy kontroluje swoje dane osobiste i utrzymuje ich prywatność.

Usługi Intune można używać z innymi usługami w pakiecie EMS. Ta funkcja zapewnia organizacji zabezpieczenia aplikacji mobilnych dużo większe niż to, co oferuje jakikolwiek system operacyjny czy aplikacja. Aplikacje zarządzane za pomocą pakietu EMS mają dostęp do szerszego zakresu funkcji zabezpieczeń aplikacji mobilnych i danych.

![Obraz zawierający poziomy zabezpieczeń danych zarządzania aplikacją](./media/what-is-intune/managing-mobile-apps.png)

## <a name="compliance-and-conditional-access"></a>Zgodność i dostęp warunkowy

Usługa Intune integruje się z usługą Azure AD, aby udostępnić szeroką gamę scenariuszy kontroli dostępu. Możesz na przykład wymagać, aby urządzenia mobilne były zgodne ze standardami organizacji zdefiniowanymi w usłudze Intune, zanim uzyskają dostęp do zasobów sieciowych, takich jak poczta e-mail lub program SharePoint. Podobnie możesz zablokować usługi, aby były one dostępne tylko dla określonego zestawu aplikacji mobilnych. Na przykład można zablokować usługę Exchange Online, aby dostęp do niej był możliwy tylko za pomocą programu Outlook lub Outlook Mobile.

**Zasoby online**:

- [Ustawianie reguł na urządzeniach w celu umożliwienia dostępu do zasobów organizacji](../protect/device-compliance-get-started.md)

- [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](../protect/conditional-access-intune-common-ways-use.md)

## <a name="how-to-get-intune"></a>Jak uzyskać usługę Intune

Dostęp do usługi Intune:

- Jako autonomiczna [usługa platformy Azure](https://go.microsoft.com/fwlink/?linkid=2090973)
- W ramach rozwiązania [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune) i [Microsoft 365 Government](https://www.microsoft.com/microsoft-365/government)
- Jako rozwiązanie [zarządzania urządzeniami mobilnymi w usłudze Office 365](https://support.office.com/article/choose-between-mdm-for-office-365-and-microsoft-intune-c93d9ab9-efb2-4349-9b93-30c30562ee22), które składa się z pewnych ograniczonych funkcji usługi Intune

Usługa Intune jest używana w wielu sektorach, takich jak [organizacje rządowe](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description), [edukacja](https://www.microsoft.com/en-us/education/intune), [kioski lub urządzenia dedykowane](../configuration/kiosk-settings.md) w branży produkcyjnej i sprzedaży detalicznej i wiele innych.

## <a name="next-steps"></a>Następne kroki

- Przeczytaj o [typowych problemach biznesowych, które usługa Intune pomaga rozwiązywać](https://docs.microsoft.com/intune/common-scenarios).
- Rozpocznij od [30-dniowej wersji próbnej usługi Intune](free-trial-sign-up.md).
- Zaplanuj [migrację do usługi Intune](migration-guide.md).
- Korzystając z bezpłatnej wersji próbnej lub subskrypcji, wykonaj kroki przewodnika [Szybki start: Tworzenie profilu poczty e-mail urządzenia dla systemu iOS](../configuration/quickstart-email-profile.md).
