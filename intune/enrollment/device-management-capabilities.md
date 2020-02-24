---
title: Możliwości zarządzania urządzeniami w usłudze Microsoft Intune
description: Przeczytaj ten temat, aby dowiedzieć się, jak usługa Intune może pomóc w zarządzaniu zarejestrowanymi urządzeniami.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3bb0dd0fa4402421db83d41e4731ca144be24133
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415329"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Możliwości zarządzania zarejestrowanymi urządzeniami w usłudze Microsoft Intune

Usługa Microsoft Intune umożliwia zarządzanie różnymi urządzeniami przez *zarejestrowanie* ich w usłudze. Możesz rejestrować niektóre typy urządzeń samodzielnie lub użytkownicy mogą rejestrować urządzenia za pośrednictwem aplikacji *Portal firmy*. Dzięki rejestracji mogą oni przeglądać i instalować aplikacje, zapewniać zgodność swoich urządzeń z zasadami firmy oraz kontaktować się z pomocą techniczną IT.

Ten artykuł zawiera pełną listę możliwości uzyskiwanych po zarejestrowaniu urządzeń.

Procesy zarządzania, tworzenia spisów oraz wdrażania, aprowizowania i wycofywania aplikacji są obsługiwane za pośrednictwem usługi Intune w witrynie Azure Portal.

Użytkownicy uzyskują dostęp do portalu firmy, który umożliwia instalowanie aplikacji, rejestrowanie i usuwanie urządzeń oraz kontaktowanie się z działem IT lub pomocą techniczną.



## <a name="device-security-and-configuration"></a>Konfiguracja i zabezpieczenia urządzeń

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Zasady konfiguracji<br><br>Zasady niestandardowe| Umożliwiają zarządzanie wieloma ustawieniami i funkcjami urządzeń przenośnych w organizacji. Na przykład istnieje możliwość wymagania hasła, ograniczenia liczby nieudanych prób, ograniczenia czasu przed włączeniem blokady ekranu, ustawienia wygasania haseł i uniemożliwienia podania wcześniej używanych haseł. Można także kontrolować sposób korzystania z funkcji sprzętu i oprogramowania, na przykład aparatu urządzenia lub przeglądarki sieci Web.<br><br>Użyj zasad niestandardowych, gdy zasady konfiguracji nie zawierają wymaganego ustawienia. W przypadku urządzeń z systemem iOS/iPadOS można importować ustawienia wyeksportowane za pomocą narzędzia Apple Configurator. W przypadku innych urządzeń można użyć ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania ustawień i funkcji na urządzeniu.|[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](../protect/device-compliance-get-started.md)|
|Zdalne czyszczenie, zdalne blokowanie i resetowanie kodu dostępu|Służy do usuwania poufnych danych w przypadku utracenia lub kradzieży urządzenia. Na przykład można zdalnie zablokować urządzenie, przywrócić go do ustawień fabrycznych lub wyczyścić z niego dane firmowe.<br><br>Możesz resetować kody dostępu, jeśli użytkownicy utracą dostęp do swoich urządzeń, blokować utracone lub skradzione urządzenia, a nawet czyścić znajdujące się na nich dane.|Łatwiejsza ochrona urządzeń za pomocą funkcji [zdalnego blokowania](../remote-actions/device-remote-lock.md) i [resetowania kodu dostępu](../remote-actions/device-passcode-reset.md)|
|Tryb kiosku|Umożliwia zablokowanie niektórych funkcji urządzeń przenośnych, takich jak przechwytywanie ekranu i przycisk zasilania. Umożliwia także ograniczenie urządzeń do uruchamiania tylko jednej, określonej aplikacji. |[Ustawienia zasad konfiguracji systemu iOS w usłudze Microsoft Intune](../configuration/device-restrictions-ios.md)|
|Resetowanie rozwiązania Autopilot|Wysyła zadanie do urządzenia w celu zdalnego uruchomienia procesu resetowania, dzięki czemu pracownicy działu IT ani inni administratorzy nie będą musieli przechodzić do poszczególnych urządzeń w celu uruchomienia procesu. Użycie na urządzeniu resetowania w programie Autopilot spowoduje usunięcie użytkownika podstawowego urządzenia. Następny użytkownik, który zarejestruje się po zresetowaniu, zostanie ustawiony jako użytkownik podstawowy.|[Zdalne resetowanie rozwiązania Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset#reset-devices-with-remote-windows-autopilot-reset)|

## <a name="app-management"></a>Zarządzanie aplikacjami

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Wdrażanie aplikacji i zarządzanie nimi|Oferuje szeroką gamę narzędzi służących do zarządzania aplikacjami mobilnymi przez cały cykl ich życia, w tym wdrażania aplikacji z plików instalacyjnych i sklepów z aplikacjami, szczegółowego monitorowania stanu aplikacji i usuwania aplikacji.|[Wdrażanie aplikacji w usłudze Microsoft Intune](../apps/apps-deploy.md)|
|Zgodne i niezgodne aplikacje|Umożliwia określanie list zgodnych aplikacji (które użytkownicy mogą instalować) i niezgodnych aplikacji (których użytkownicy nie mogą instalować).|[Ustawienia zasad systemu iOS w usłudze Microsoft Intune](../configuration/device-restrictions-ios.md)|
|Zarządzanie aplikacjami mobilnymi|Służy do konfigurowania ograniczeń aplikacji za pomocą zarządzania aplikacjami mobilnymi dla wszystkich urządzeń zarządzanych i niezarządzanych przez usługę Intune. Można zwiększyć bezpieczeństwo danych firmowych przez ograniczenie możliwości wykonywania operacji, takich jak kopiowanie i wklejanie, tworzenie zewnętrznych kopii zapasowych danych oraz przesyłanie danych między aplikacjami.|[Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](../developer/app-wrapper-prepare-android.md)|
|Konfiguracja aplikacji mobilnych systemu iOS|Używa zasad konfiguracji aplikacji mobilnych umożliwiających określanie wartości ustawień aplikacji systemu iOS/iPadOS, które mogą być wymagane, gdy użytkownik uruchamia aplikację. Aplikacja może na przykład wymagać, aby użytkownik określił numer portu lub dane logowania. Można usprawnić konfigurowanie aplikacji i ograniczyć liczbę zgłoszeń do pomocy technicznej.|[Konfigurowanie aplikacji systemu iOS/iPadOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](../apps/app-configuration-policies-use-ios.md)|
|Profile aprowizacji aplikacji mobilnych systemu iOS/iPadOS|Ułatwia wdrażanie profilów aprowizacji w aplikacjach systemu iOS/iPadOS, które niedługo wygasną. |[Używanie zasad profilów aprowizacji aplikacji mobilnych systemu iOS/iPadOS, aby zapobiec wygaśnięciu aplikacji](../apps/app-provisioning-profile-ios.md)|
|Managed Browser|Służy do konfigurowania zasad programu Managed Browser w celu kontrolowania witryn sieci Web, które użytkownicy mogą odwiedzać. Ponadto dla programu Managed Browser możesz również stosować zasady zarządzania aplikacjami mobilnymi.|[Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](../apps/app-configuration-managed-browser.md)|
|Windows Hello for Business|Pozwala na integrację z usługą Windows Hello for Business, czyli alternatywną metodą logowania dla systemu Windows 10 korzystającą z lokalnej usługi Active Directory lub Azure Active Directory w celu zastąpienia haseł, kart inteligentnych lub wirtualnych kart inteligentnych.|[Sterowanie ustawieniami usługi Windows Hello dla firm na urządzeniach za pomocą usługi Microsoft Intune](../protect/windows-hello.md)|
|Aplikacje nabyte zbiorczo|Ułatwia zarządzanie aplikacjami zakupionymi w ramach programu zakupów zbiorczych przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana.|[Zarządzanie aplikacjami zakupionymi zbiorczo za pomocą usługi Microsoft Intune](../apps/vpp-apps.md)|

## <a name="company-resource-access"></a>Dostęp do zasobów firmy

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Profile certyfikatów|Służą do tworzenia i wdrażania profilów zaufanych certyfikatów i certyfikatów SCEP (Simple Certificate Enrollment Protocol), które mogą być używane do zabezpieczania i uwierzytelniania profili sieci Wi-Fi i VPN oraz profili poczty e-mail.|[Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](../protect/certificates-configure.md)|
|Profile sieci Wi-Fi|Służą do wdrażania ustawień sieci bezprzewodowej dla użytkowników. Wdrażając te ustawienia, można zminimalizować działania użytkowników wymagane w celu połączenia z siecią firmową.|[Połączenia Wi-Fi w usłudze Microsoft Intune](../configuration/wi-fi-settings-configure.md)|
|Profile poczty e-mail|Umożliwiają tworzenie i wdrażanie ustawień poczty e-mail na urządzeniach, aby użytkownicy mogli uzyskiwać dostęp do firmowej poczty e-mail na urządzeniach osobistych bez konieczności samodzielnego przeprowadzania konfiguracji.|[Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](../configuration/email-settings-configure.md)|
|Profile sieci VPN|Umożliwiają wdrażanie ustawień sieci VPN dla użytkowników i urządzeń w Twojej organizacji. Przez wdrożenie tych ustawień można maksymalnie ułatwić użytkownikom nawiązywanie połączeń z zasobami w sieci firmowej.|[Połączenia VPN w usłudze Microsoft Intune](../configuration/device-profiles.md#vpn)|
|Zasady dostępu warunkowego|Służą do zarządzania dostępem do poczty e-mail programu Microsoft Exchange i usługi SharePoint Online z urządzeń, które nie są zarządzane przez usługę Intune.|[Ograniczanie dostępu do poczty e-mail i programu SharePoint przy użyciu usługi Microsoft Intune](../protect/app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Następne kroki

[Zobacz listę urządzeń, którymi można zarządzać](../remote-actions/device-management.md).
