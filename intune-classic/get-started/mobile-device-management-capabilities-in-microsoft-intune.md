---
title: "Możliwości zarządzania zarejestrowanymi urządzeniami"
description: "Przeczytaj ten temat, aby dowiedzieć się, jak usługa Intune może pomóc w zarządzaniu zarejestrowanymi urządzeniami."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5fc5e6108e7e7841ed142f24f463d85273ae8a12
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Możliwości zarządzania zarejestrowanymi urządzeniami w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune umożliwia zarządzanie różnymi urządzeniami przez *zarejestrowanie* ich w usłudze. Możesz rejestrować niektóre typy urządzeń samodzielnie lub użytkownicy mogą rejestrować urządzenia za pośrednictwem aplikacji *Portal firmy*. Pozwala im to również wykonywać szereg operacji, takich jak przeglądanie i instalowanie aplikacji, upewnianie się, że urządzenia są zgodne z zasadami firmy, oraz kontaktowanie się z pomocą techniczną IT.

Ten temat zawiera pełną listę możliwości, jakie daje zarejestrowanie urządzenia.

Wszystkie procesy, takie jak zarządzanie, tworzenie spisów oraz wdrażanie, inicjowanie obsługi administracyjnej i wycofywanie aplikacji, są obsługiwane za pośrednictwem konsoli administracyjnej usługi Intune. Użytkownicy uzyskują dostęp do portalu firmy, który umożliwia instalowanie aplikacji, rejestrowanie i usuwanie urządzeń oraz kontaktowanie się z działem IT lub pomocą techniczną.



## <a name="device-security-and-configuration"></a>Konfiguracja i zabezpieczenia urządzeń

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Zasady konfiguracji<br><br>Zasady niestandardowe| Umożliwiają zarządzanie wieloma ustawieniami i funkcjami urządzeń przenośnych w organizacji. Na przykład istnieje możliwość wymagania hasła, ograniczenia liczby nieudanych prób, ograniczenia czasu przed włączeniem blokady ekranu, ustawienia wygasania haseł i uniemożliwienia podania wcześniej używanych haseł. Można także kontrolować sposób korzystania z funkcji sprzętu i oprogramowania, na przykład aparatu urządzenia lub przeglądarki sieci Web.<br><br>Użyj zasad niestandardowych, gdy zasady konfiguracji nie zawierają wymaganego ustawienia. W przypadku urządzeń z systemem iOS można importować ustawienia wyeksportowane za pomocą narzędzia Apple Configurator. W przypadku innych urządzeń można użyć ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania ustawień i funkcji na urządzeniu.|[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)|
|Zdalne czyszczenie, zdalne blokowanie i resetowanie kodu dostępu|Służy do usuwania poufnych danych w przypadku utracenia lub kradzieży urządzenia. Na przykład można zdalnie zablokować urządzenie, przywrócić go do ustawień fabrycznych lub wyczyścić z niego dane firmowe.<br><br>Możesz resetować kody dostępu, jeśli użytkownicy utracą dostęp do swoich urządzeń, blokować utracone lub skradzione urządzenia, a nawet czyścić znajdujące się na nich dane.|[Łatwiejsza ochrona urządzeń za pomocą funkcji zdalnego blokowania i resetowania kodu dostępu](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Tryb kiosku|Umożliwia zablokowanie niektórych funkcji urządzeń przenośnych, takich jak przechwytywanie ekranu i przycisk zasilania. Umożliwia także ograniczenie urządzeń do uruchamiania tylko jednej, określonej aplikacji.|[Ustawienia zasad konfiguracji systemu iOS w usłudze Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Zarządzanie aplikacjami

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Wdrażanie aplikacji i zarządzanie nimi|Oferuje szeroką gamę narzędzi służących do zarządzania aplikacjami mobilnymi przez cały cykl ich życia, w tym wdrażania aplikacji z plików instalacyjnych i sklepów z aplikacjami, szczegółowego monitorowania stanu aplikacji i usuwania aplikacji.|[Wdrażanie aplikacji w usłudze Microsoft Intune](/intune-classic/deploy-use/deploy-apps)|
|Zgodne i niezgodne aplikacje|Umożliwia określanie list zgodnych aplikacji (które użytkownicy mogą instalować) i niezgodnych aplikacji (których użytkownicy nie mogą instalować).|[Ustawienia zasad systemu iOS w usłudze Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Zarządzanie aplikacjami mobilnymi|Służy do konfigurowania ograniczeń aplikacji za pomocą zarządzania aplikacjami mobilnymi dla wszystkich urządzeń zarządzanych i niezarządzanych przez usługę Intune. Pomaga to w zwiększeniu bezpieczeństwa danych firmowych przez ograniczenie możliwości wykonywania operacji, takich jak kopiowanie i wklejanie, tworzenia zewnętrznych kopii zapasowych danych i transferu danych między aplikacjami.|[Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](/intune/app-wrapper-prepare-android)|
|Konfiguracja aplikacji mobilnych systemu iOS|Używa zasad konfiguracji aplikacji mobilnych umożliwiających określanie wartości ustawień aplikacji systemu iOS, które mogą być wymagane, gdy użytkownik uruchamia aplikację. Aplikacja może na przykład wymagać, aby użytkownik określił numer portu lub dane logowania. Może to usprawnić konfigurowanie aplikacji i ograniczyć liczbę zgłoszeń do pomocy technicznej.|[Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Profile aprowizacji aplikacji mobilnych systemu iOS|Ułatwia wdrażanie profilów aprowizacji w aplikacjach systemu iOS, które niedługo wygasną. |[Użyj zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapobiec wygaśnięciu aplikacji](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Managed Browser|Służy do konfigurowania zasad programu Managed Browser w celu kontrolowania witryn sieci Web, które użytkownicy mogą odwiedzać. Ponadto dla programu Managed Browser możesz również stosować zasady zarządzania aplikacjami mobilnymi.|[Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Windows Hello for Business|Pozwala na integrację z usługą Windows Hello for Business, czyli alternatywną metodą logowania dla systemu Windows 10 korzystającą z lokalnej usługi Active Directory lub Azure Active Directory w celu zastąpienia haseł, kart inteligentnych lub wirtualnych kart inteligentnych.|[Sterowanie ustawieniami usługi Windows Hello dla firm na urządzeniach za pomocą usługi Microsoft Intune](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Aplikacje nabyte zbiorczo|Ułatwia zarządzanie aplikacjami zakupionymi w ramach programu zakupów zbiorczych przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana.|[Zarządzanie aplikacjami zakupionymi zbiorczo za pomocą usługi Microsoft Intune](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Dostęp do zasobów firmy

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Profile certyfikatów|Służą do tworzenia i wdrażania profilów zaufanych certyfikatów i certyfikatów SCEP (Simple Certificate Enrollment Protocol), które mogą być używane do zabezpieczania i uwierzytelniania profili sieci Wi-Fi i VPN oraz profili poczty e-mail.|[Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)|
|Profile sieci Wi-Fi|Służą do wdrażania ustawień sieci bezprzewodowej dla użytkowników. Wdrażając te ustawienia, można zminimalizować działania użytkowników wymagane w celu połączenia z siecią firmową.|[Połączenia Wi-Fi w usłudze Microsoft Intune](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Profile poczty e-mail|Służą do tworzenia i wdrażania ustawień poczty e-mail na urządzeniach. Oznacza to, że użytkownicy mogą uzyskiwać dostęp do firmowej poczty e-mail na urządzeniach osobistych bez przeprowadzania żadnej konfiguracji.|[Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|profile sieci VPN,|Umożliwiają wdrażanie ustawień sieci VPN dla użytkowników i urządzeń w Twojej organizacji. Przez wdrożenie tych ustawień można maksymalnie ułatwić użytkownikom nawiązywanie połączeń z zasobami w sieci firmowej.|[Połączenia VPN w usłudze Microsoft Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Zasady dostępu warunkowego|Służą do zarządzania dostępem do poczty e-mail programu Microsoft Exchange i usługi SharePoint Online z urządzeń, które nie są zarządzane przez usługę Intune.|[Ograniczanie dostępu do poczty e-mail i programu SharePoint przy użyciu usługi Microsoft Intune](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Spis i raportowanie

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Spis i raportowanie|Służy do wyszukiwania informacji o zarządzanych urządzeniach i oprogramowaniu, którego te urządzenia używają.|[Uzyskiwanie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|
