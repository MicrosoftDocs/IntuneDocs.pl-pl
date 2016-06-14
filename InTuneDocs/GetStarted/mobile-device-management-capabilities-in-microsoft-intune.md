---
# required metadata

title: Możliwości zarządzania urządzeniami przenośnymi w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Możliwości zarządzania urządzeniami przenośnymi w usłudze Microsoft Intune

Usługa Microsoft Intune umożliwia zarządzanie różnymi urządzeniami poprzez *zarejestrowanie* ich w usłudze. Użytkownicy mogą następnie korzystać z *portalu firmy*, aby wykonywać szereg operacji, takich jak rejestrowanie swoich urządzeń, przeglądanie i instalowanie aplikacji, upewnianie się, że urządzenie jest zgodne z zasadami firmy i kontaktowanie się z pomocą techniczną IT.
Ten temat zawiera pełną listę możliwości, jakie daje zarejestrowanie urządzenia.

Wszystkie procesy, takie jak zarządzanie, tworzenie spisów oraz wdrażanie, inicjowanie obsługi administracyjnej i wycofywanie aplikacji, są obsługiwane za pośrednictwem konsoli administracyjnej usługi Intune. Użytkownicy uzyskują dostęp do portalu firmy, w którym mogą instalować aplikacje, rejestrować i usuwać urządzenia oraz uzyskiwać pomoc w kontaktowaniu się z działem IT lub pomocą techniczną.



## Konfiguracja i zabezpieczenia urządzeń

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Zasady konfiguracji<br><br>Zasady niestandardowe|Zasady konfiguracji urządzeń przenośnych umożliwiają zarządzanie wieloma ustawieniami i funkcjami urządzeń przenośnych w organizacji. Na przykład istnieje możliwość wymagania hasła, ograniczenia liczby nieudanych prób, ograniczenia liczby minut przed włączeniem blokady ekranu, ustawienia okresu ważności hasła i uniemożliwienia podania wcześniej używanych haseł. Można także kontrolować sposób korzystania z funkcji sprzętu i oprogramowania, na przykład aparatu urządzenia lub przeglądarki sieci Web.<br><br>Użyj zasad niestandardowych, gdy zasady konfiguracji nie zawierają wymaganego ustawienia. W przypadku urządzeń z systemem iOS można importować ustawienia wyeksportowane za pomocą narzędzia Apple Configurator. W przypadku innych urządzeń można użyć ustawień OMA-URI w celu skonfigurowania ustawień i funkcji na urządzeniu.|[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Zdalne czyszczenie, zdalne blokowanie i resetowanie kodu dostępu|Usuwaj poufne dane w przypadku utracenia lub kradzieży urządzenia. Na przykład można zdalnie zablokować urządzenie, przywrócić go do ustawień fabrycznych lub wyczyścić z niego dane firmowe.<br>Możesz resetować kody dostępu, jeśli użytkownicy utracą dostęp do swoich urządzeń, blokować utracone lub skradzione urządzenia, a nawet czyścić znajdujące się na nich dane.|[Łatwiejsza ochrona urządzeń za pomocą funkcji zdalnego blokowania i resetowania kodu dostępu](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) oraz [Wycofywanie urządzeń z zarządzania w usłudze Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Tryb kiosku|Umożliwia zablokowanie niektórych funkcji urządzeń przenośnych, takich jak przechwytywanie ekranu i przycisk zasilania. Umożliwia także ograniczenie urządzeń do uruchamiania tylko jednej, określonej aplikacji.|[Ustawienia zasad konfiguracji systemu iOS w usłudze Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Zarządzanie aplikacjami

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Wdrażanie aplikacji i zarządzanie nimi|Oferuje szeroką gamę narzędzi służących do zarządzania aplikacjami mobilnymi przez cały cykl ich życia, w tym wdrażania aplikacji z plików instalacyjnych i sklepów z aplikacjami, szczegółowego monitorowania stanu aplikacji i usuwania aplikacji.|[Wdrażanie aplikacji w usłudze Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Zgodne i niezgodne aplikacje|Umożliwia określanie list zgodnych aplikacji (które użytkownicy mogą instalować) i niezgodnych aplikacji (których użytkownicy nie mogą instalować).|[Ustawienia zasad systemu iOS w usłudze Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Zarządzanie aplikacjami mobilnymi|Skonfiguruj ograniczenia dla aplikacji za pomocą zarządzania aplikacjami mobilnymi dla urządzeń zarządzanych za pomocą usługi Intune, jak i urządzeń, które nie są zarządzane przez usługę Intune. Pomaga to w zwiększeniu bezpieczeństwa danych firmowych przez ograniczenie możliwości wykonywania operacji, takich jak kopiowanie i wklejanie, tworzenia zewnętrznych kopii zapasowych danych i transferu danych między aplikacjami.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Przygotowanie aplikacji systemu iOS do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Microsoft Intune](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Przygotowanie aplikacji systemu Android do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Microsoft Intune](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Konfiguracja aplikacji mobilnych|Zasady konfiguracji aplikacji mobilnych umożliwiają określanie wartości ustawień aplikacji systemu iOS, które mogą być wymagane, gdy użytkownik uruchamia aplikację. Aplikacja może na przykład wymagać, aby użytkownik określił numer portu w danych logowania. Może to usprawnić konfigurowanie aplikacji i ograniczyć liczbę wezwań pomocy technicznej.|[Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Managed Browser|Po wdrożeniu programu Managed Browser dla użytkowników, możesz skonfigurować jego zasady w celu kontrolowania witryn sieci Web, które użytkownicy mogą odwiedzać. Ponadto dla programu Managed Browser możesz również stosować zasady zarządzania aplikacjami mobilnymi.|[Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Usługa Microsoft Passport|Usługa Intune pozwala na integrację z usługą Microsoft Passport for Work, czyli alternatywną metodą logowania dla systemu Windows 10 korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej.|[Sterowanie ustawieniami usługi Microsoft Passport na urządzeniach z usługą Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Dostęp do zasobów firmy

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Profile certyfikatów|Twórz i wdrażaj profile zaufanych certyfikatów i certyfikaty SCEP (Simple Certificate Enrollment Protocol), które mogą być używane do zabezpieczania i uwierzytelniania profili sieci Wi-Fi i VPN oraz profili poczty e-mail.|[Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Profile sieci Wi-Fi|Wdrażaj ustawienia sieci bezprzewodowej dla użytkowników. Wdrażając te ustawienia, można zminimalizować działania użytkowników końcowych wymagane w celu połączenia z siecią firmową.|[Połączenia Wi-Fi w usłudze Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Profile poczty e-mail|Twórz i wdrażaj ustawienia poczty e-mail na urządzeniach. Umożliwia to użytkownikom dostęp do firmowej poczty e-mail na urządzeniach osobistych, przy czym nie muszą oni przeprowadzać żadnej konfiguracji.|[Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Profile sieci VPN|Wdrażaj ustawienia sieci VPN dla użytkowników i urządzeń w Twojej organizacji. Przez wdrożenie tych ustawień można maksymalnie ułatwić użytkownikom końcowym nawiązywanie połączeń z zasobami w sieci firmowej.|[Połączenia VPN w usłudze Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Zasady dostępu warunkowego|Zarządzanie dostępem do poczty e-mail programu Microsoft Exchange i usługi SharePoint Online z urządzeń, które nie są zarządzane przez usługę Intune.|[Ograniczanie dostępu do poczty e-mail i programu SharePoint przy użyciu usługi Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Spis i raportowanie

|Możliwość|Szczegóły|Więcej informacji|
|--------------|-----------|--------------------|
|Spis i raportowanie|Wyszukuj informacje o zarządzanych urządzeniach i oprogramowaniu, którego używają.<br /><br />Możesz filtrować te raporty na kilka różnych sposobów, np. według platformy urządzenia lub według tego, czy urządzenie jest zgodne ze standardami firmy.|[Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](/intune/understand-explore/understand-microsoft-intune-operations-by-using-reports)|

### Zobacz także
[Możliwości zarządzania komputerami z systemem Windows w usłudze Microsoft Intune](/intune/understand-explore/windows-pc-management-capabilities-in-microsoft-intune)


<!--HONumber=May16_HO1-->


