---
# required metadata

title: Informacje o zasadach usługi Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Informacje o zasadach usługi Microsoft Intune

Użyj informacji w tym temacie, aby określić zasady usługi Microsoft Intune, których należy użyć do zarządzania urządzeniami.

> [!TIP]
> Aby uzyskać szczegółowe informacje na temat używania zasad, zobacz temat [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).


## Zasady konfiguracji systemu Android

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Konfiguracja niestandardowa (system Android 4 lub nowszy, system Samsung KNOX Standard 4.0 lub nowszy)**|Wdrożenie ustawień OMA-URI, takich jak ustawienia sieci Wi-Fi, których można użyć do kontrolowania funkcji urządzenia. Jest to przydatne tylko w przypadku, gdy konieczne ustawienie jest niedostępne w zasadach konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Android w usłudze Microsoft Intune](android-policy-settings-in-microsoft-intune.md).|
|**Profil poczty e-mail (system Samsung KNOX Standard 4.0 lub nowszy)**|Tworzenie, wdrażanie i monitorowanie ustawień poczty e-mail programu Exchange ActiveSync na zarządzanych urządzeniach. Umożliwia to użytkownikom dostęp do firmowej poczty e-mail na urządzeniach osobistych, przy czym nie muszą oni przeprowadzać żadnej konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Konfiguracja ogólna (system Android 4 lub nowszy, system Samsung KNOX Standard 4.0 lub nowszy)**|Skonfigurowanie ustawień zabezpieczeń i funkcjonalnych urządzenia przenośnego.<br />Określenie aplikacji, które są zgodne lub niezgodne, a następnie składanie raportu, gdy są one używane.<br />Skonfigurowanie trybu kiosku, który umożliwia działanie tylko określonych funkcji, na przykład umożliwia uruchamianie tylko jednej aplikacji na urządzeniu lub wyłącza przyciski głośności.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Android w usłudze Microsoft Intune](android-policy-settings-in-microsoft-intune.md).|
|**Profil certyfikatu PKCS #12 (PFX) (system Android 4 lub nowszy)**|Za pomocą tego profilu możesz utworzyć i wdrożyć ustawienia PFX dotyczące żądań certyfikatów urządzeń.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil certyfikatu protokołu SCEP (system Android 4 i nowsze)**|Konfigurowanie certyfikatu protokołu SCEP (Simple Certificate Enrollment Protocol), którego można użyć w połączeniu z zaufanym certyfikatem urządzenia przenośnego do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil zaufanego certyfikatu (system Android 4 i nowsze)**|Konfigurowanie zaufanego certyfikatu urządzenia przenośnego, którego można użyć do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil sieci VPN (system Android 4 i nowsze)**|Konfigurowanie i wdrażanie ustawień, które zapewniają użytkownikom bezpieczny dostęp do sieci firmowej z urządzenia przenośnego. Wdrażając te ustawienia, możesz zminimalizować ilość pracy wymaganej od użytkownika końcowego do nawiązania połączenia z siecią firmową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia VPN w usłudze Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**Profil sieci Wi-Fi (system Android 4 i nowsze)**|Konfigurowanie i wdrażanie ustawień sieci bezprzewodowej dla użytkowników w organizacji. Wdrażając te ustawienia, można zminimalizować działania użytkowników końcowych wymagane w celu połączenia z siecią bezprzewodową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Zasady konfiguracji systemu iOS

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Konfiguracja niestandardowa (system iOS 7.1 lub nowszy)**|Wdrażanie profili konfiguracji, które zostały utworzone za pomocą narzędzia Apple Configurator, na urządzeniach z systemem iOS. Jest to przydatne tylko w przypadku, gdy konieczne ustawienie jest niedostępne w zasadach konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu iOS w usłudze Microsoft Intune](ios-policy-settings-in-microsoft-intune.md).|
|**Profil poczty e-mail (system iOS 7.1 lub nowszy)**|Tworzenie, wdrażanie i monitorowanie ustawień poczty e-mail programu Exchange ActiveSync na zarządzanych urządzeniach. Umożliwia to użytkownikom dostęp do firmowej poczty e-mail na urządzeniach osobistych, przy czym nie muszą oni przeprowadzać żadnej konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Konfiguracja ogólna (system iOS 7.1 lub nowszy)**|Skonfigurowanie ustawień zabezpieczeń i funkcjonalnych urządzenia przenośnego.<br />- Określenie aplikacji, które są zgodne lub niezgodne, a następnie zgłaszanie, gdy są one używane.<br />Skonfigurowanie trybu kiosku, który umożliwia działanie tylko określonych funkcji, na przykład umożliwia uruchamianie tylko jednej aplikacji na urządzeniu lub wyłącza przyciski głośności.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu iOS w usłudze Microsoft Intune](ios-policy-settings-in-microsoft-intune.md).|
|**Profil certyfikatu protokołu SCEP (system iOS 7.1 lub nowszy)**|Konfigurowanie certyfikatu protokołu SCEP (Simple Certificate Enrollment Protocol), którego można użyć w połączeniu z zaufanym certyfikatem urządzenia przenośnego do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil zaufanego certyfikatu (system iOS 7.1 lub nowszy)**|Konfigurowanie zaufanego certyfikatu urządzenia przenośnego, którego można użyć do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil sieci VPN (system iOS 7.1 lub nowszy)**|Konfigurowanie i wdrażanie ustawień, które zapewniają użytkownikom bezpieczny dostęp do sieci firmowej z urządzenia przenośnego. Wdrażając te ustawienia, możesz zminimalizować ilość pracy wymaganej od użytkownika końcowego do nawiązania połączenia z siecią firmową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia VPN w usłudze Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**Profil sieci Wi-Fi (system iOS 7.1 lub nowszy)**|Konfigurowanie i wdrażanie ustawień sieci bezprzewodowej dla użytkowników w organizacji. Wdrażając te ustawienia, można zminimalizować działania użytkowników końcowych wymagane w celu połączenia z siecią bezprzewodową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|
|**Zasady konfiguracji aplikacji mobilnych (system iOS 7.1 i nowsze)**|Zasady konfiguracji aplikacji mobilnych umożliwiają automatyczne określanie wartości ustawień, które mogą być wymagane, jeśli użytkownik uruchamia aplikację w systemie iOS.<br /><br />Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).|

## Zasady konfiguracji systemu Mac OS X

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Konfiguracja niestandardowa (system Mac OS X 10.9 i nowsze)**|Wdrażanie profilów konfiguracji, które zostały utworzone za pomocą narzędzia Apple Configurator, na komputerach Mac. Jest to przydatne tylko w przypadku, gdy konieczne ustawienie jest niedostępne w zasadach konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Mac OS X w usłudze Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Konfiguracja ogólna (system Mac OS X 10.9 i nowsze)**|Skonfigurowanie ustawień zabezpieczeń i funkcjonalnych urządzenia przenośnego.<br />Określenie aplikacji, które są zgodne lub niezgodne, a następnie składanie raportu, gdy są one używane.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Mac OS X w usłudze Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Profil certyfikatu protokołu SCEP (system Mac OS X 10.9 i nowsze)**|Konfigurowanie certyfikatu protokołu SCEP (Simple Certificate Enrollment Protocol), którego można użyć w połączeniu z zaufanym certyfikatem urządzenia przenośnego do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil zaufanego certyfikatu (system Mac OS X 10.9 i nowsze)**|Konfigurowanie zaufanego certyfikatu urządzenia przenośnego, którego można użyć do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil sieci VPN (system Mac OS X 10.9 i nowsze)**|Konfigurowanie i wdrażanie ustawień, które zapewniają użytkownikom bezpieczny dostęp do sieci firmowej z urządzenia przenośnego. Wdrażając te ustawienia, możesz zminimalizować ilość pracy wymaganej od użytkownika końcowego do nawiązania połączenia z siecią firmową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia VPN w usłudze Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**Profil sieci Wi-Fi (system Mac OS X 10.9 lub nowszy)**|Konfigurowanie i wdrażanie ustawień sieci bezprzewodowej dla użytkowników w organizacji. Wdrażając te ustawienia, można zminimalizować działania użytkowników końcowych wymagane w celu połączenia z siecią bezprzewodową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Zasady konfiguracji systemu Windows
Dotyczy tylko systemu Windows Phone i zarejestrowanych urządzeń systemu Windows.

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Konfiguracja niestandardowa (system Windows 10 Desktop i Mobile lub nowszy)**|Wdrażanie ustawień OMA-URI, których można użyć do kontrolowania funkcji urządzenia. Jest to przydatne tylko w przypadku, gdy konieczne ustawienie jest niedostępne w zasadach konfiguracji.<br />    Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md).|
|**Konfiguracja niestandardowa (system Windows Phone 8.1 lub nowszy)**|Wdrażanie ustawień OMA-URI, których można użyć do kontrolowania funkcji urządzenia. Jest to przydatne tylko w przypadku, gdy konieczne ustawienie jest niedostępne w zasadach konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows Phone 8.1 w usłudze Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Zasady uaktualniania wersji (system Windows 10 Desktop i nowsze)**<br><br>**Zasady uaktualniania wersji (system Windows 10 Holographic i nowsze)**|Konfigurowanie i wdrażanie zasad zawierających informacje o licencji lub kluczu produktu używane do aktualizowania urządzeń z systemem Windows 10 do nowszej wersji<br><br>Aby uzyskać więcej informacji, zobacz [Ustawienia zasad uaktualniania wersji w usłudze Microsoft Intune](edition-upgrade-policy-settings-in-microsoft-intune.md).|  
|**Profil poczty e-mail (system Windows Phone 8 i nowsze)**<br /><br />**Profil poczty e-mail (system Windows 10 Desktop oraz Mobile i nowsze)**|Tworzenie, wdrażanie i monitorowanie ustawień poczty e-mail programu Exchange ActiveSync na zarządzanych urządzeniach. Umożliwia to użytkownikom dostęp do firmowej poczty e-mail na urządzeniach osobistych, przy czym nie muszą oni przeprowadzać żadnej konfiguracji.<br /><br />Aby uzyskać więcej informacji, zobacz [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Konfiguracja ogólna (system Windows 10 Desktop i Mobile lub nowszy)**|Konfigurowanie ustawień zabezpieczeń i funkcjonalnych zarejestrowanych urządzeń przenośnych z systemem Windows 10 Desktop i Mobile.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md).|
|**Konfiguracja ogólna (system Windows 10 Team i nowsze)**|Konfigurowanie ustawień zabezpieczeń i funkcjonalnych zarejestrowanych urządzeń z systemem Windows 10 Team (na przykład urządzenia Surface Hub).<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad konfiguracji systemu Windows Team w usłudze Microsoft Intune](windows-team-configuration-policy-settings-in-microsoft-intune.md).|
|**Konfiguracja ogólna (system Windows 8.1 lub nowszy)**|Konfigurowanie ustawień zabezpieczeń i funkcjonalnych zarejestrowanego urządzenia przenośnego z systemem Windows.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows w usłudze Microsoft Intune](windows-configuration-policy-settings-in-microsoft-intune.md).|
|**Konfiguracja ogólna (system Windows Phone 8.1 lub nowszy)**|Skonfigurowanie ustawień zabezpieczeń i funkcjonalnych urządzenia przenośnego.<br />Określenie aplikacji, których użytkownicy mogą lub nie mogą używać, i blokowanie instalacji lub użycia niezgodnych aplikacji.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows Phone 8.1 w usłudze Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Profil certyfikatu PKCS #12 (PFX) (system Windows 10 Desktop i Mobile lub nowszy)**|Za pomocą tego profilu możesz utworzyć i wdrożyć ustawienia PFX dotyczące żądań certyfikatów urządzeń.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil certyfikatu protokołu SCEP (system Windows 8.1 i nowsze)**<br /><br />**Profil certyfikatu protokołu SCEP (system Windows Phone 8.1 i nowsze)**|Konfigurowanie certyfikatu protokołu SCEP (Simple Certificate Enrollment Protocol), którego można użyć w połączeniu z zaufanym certyfikatem urządzenia przenośnego do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil certyfikatu protokołu SCEP (system Windows 8.1 i nowsze)**<br /><br />**Profil zaufanego certyfikatu (system Windows Phone 8.1 i nowsze)**|Konfigurowanie zaufanego certyfikatu urządzenia przenośnego, którego można użyć do uwierzytelniania urządzeń przenośnych. Umożliwia im to dostęp do zasobów sieciowych, takich jak zasoby konfigurowane za pomocą profili sieci Wi-Fi i VPN.<br /><br />Aby uzyskać więcej informacji, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune](secure-resource-access-with-certificate-profiles.md)).|
|**Profil sieci VPN (system Windows 10 Desktop i Mobile oraz nowsze)**<br /><br />**Profil sieci VPN (system Windows 8.1 i nowsze)**<br /><br />**Profil sieci VPN (system Windows Phone 8.1 i nowsze)**|Konfigurowanie i wdrażanie ustawień, które zapewniają użytkownikom bezpieczny dostęp do sieci firmowej z urządzenia przenośnego. Wdrażając te ustawienia, możesz zminimalizować ilość pracy wymaganej od użytkownika końcowego do nawiązania połączenia z siecią firmową.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia VPN w usłudze Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**Importowanie konfiguracji sieci Wi-Fi**|Importowanie i wdrażanie konfiguracji sieci Wi-Fi systemu Windows, które zostały wcześniej wyeksportowane do pliku.<br /><br />Aby uzyskać więcej informacji, zobacz [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Zasady dotyczące oprogramowania

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Zasady programu Managed Browser (system Android 4 i nowsze)**<br /><br />**Zasady programu Managed Browser (system iOS 7.1 i nowsze)**|Określenie witryn sieci Web, do których użytkownicy mogą mieć dostęp lub do których nie mogą mieć dostępu, gdy używają aplikacji Managed Browser.<br /><br />Aby uzyskać więcej informacji, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).|
|**Zasady zarządzania aplikacjami mobilnymi (system Android 4 i nowsze)**<br /><br />**Zasady zarządzania aplikacjami mobilnymi (system iOS 7.1 i nowsze)**|Modyfikowanie funkcji wdrażanych aplikacji w taki sposób, aby nie naruszały firmowych zasad dotyczących zgodności i zabezpieczeń. Na przykład w aplikacji można ograniczyć wykonywanie operacji wycinania, kopiowania i wklejania lub skonfigurować aplikację tak, aby wszystkie linki sieci Web były otwierane w programie Managed Browser.<br /><br />Aby uzyskać więcej informacji, zobacz [Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)|

## Typowe ustawienia urządzeń przenośnych

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Zasady programu Exchange ActiveSync**|Konfigurowanie ustawień zabezpieczeń i funkcjonalnych urządzenia przenośnego zarządzanego przez program Exchange ActiveSync.<br /><br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad programu Exchange ActiveSync w usłudze Microsoft Intune](exchange-activesync-policy-settings-in-microsoft-intune.md).|
|**Zasady zabezpieczeń urządzeń przenośnych**|<ul><li>Konfigurowanie ustawień urządzeń przenośnych (wszystkie platformy), w tym:<br /><br /><ul><li>Zabezpieczenia</li><li>Szyfrowanie</li><li>System</li><li>Poczta e-mail</li><li>Aplikacje</li></ul></li></ul> **Ważne:** usługa Microsoft Intune obejmuje teraz oddzielne **zasady konfiguracji** dotyczące każdej platformy urządzeń, a zasady te zawierają najbardziej aktualne ustawienia, których można użyć. Można nadal używać zasad zabezpieczeń urządzenia przenośnego i wszystkie istniejące wdrożenia będą nadal działać, ale należy zaplanować jak najszybszą migrację do nowych zasad konfiguracji.<br />Aby uzyskać więcej informacji, zobacz [Ustawienia zasad zabezpieczeń urządzeń przenośnych w usłudze Microsoft Intune](mobile-device-security-policy-settings-in-microsoft-intune.md).|

## Zasady warunkowego dostępu i zgodności

### Dostęp warunkowy

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Zasady usługi Exchange Online**<br /><br />**Zasady lokalnej instalacji programu Exchange**|Zarządzanie dostępem do poczty e-mail programu Microsoft Exchange z urządzeń, które nie są zarządzane przez usługę Intune lub które nie są zgodne z utworzonymi zasadami zgodności.<br /><br />Aby uzyskać więcej informacji, zobacz [Ograniczanie dostępu poczty e-mail do usługi Exchange Online i nowego środowiska usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune](restrict-access-to-exchange-online-with-microsoft-intune.md).|
|**Zasady usługi SharePoint Online**|Zarządzanie dostępem do usługi SharePoint Online z urządzeń, które nie są zarządzane przez usługę Intune lub które nie są zgodne z utworzonymi zasadami zgodności.<br /><br />Aby uzyskać więcej informacji, zobacz [Ograniczanie dostępu do usługi SharePoint Online przy użyciu usługi Microsoft Intune](restrict-access-to-sharepoint-online-with-microsoft-intune.md).|
|**Skype dla firm**|Zarządzanie dostępem do usługi Skype dla firm z urządzeń, które nie są zarządzane przez usługę Intune lub które nie są zgodne z utworzonymi zasadami zgodności.<br /><br />Aby uzyskać więcej informacji, zobacz [Ograniczanie dostępu do usługi Skype dla firm przy użyciu usługi Microsoft Intune](restrict-access-to-skype-for-business-online-with-microsoft-intune.md).|
> [!NOTE]
> Zasad dostępu warunkowego nie wdraża się dla użytkowników ani urządzeń. Zamiast tego konfiguruje się wymagane zasady i są one stosowane do wszystkich grup, których dotyczą.

### Zasady zgodności

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Zasady zgodności**|Definiowanie poziomu zgodności dla urządzeń, a następnie zgłaszanie niezgodnych urządzeń. Te zasady są używane przez funkcję dostępu warunkowego. Służą do oceniania, czy dostęp urządzenia do usługi powinien zostać zablokowany.<br /><br />Aby uzyskać więcej informacji, zobacz [Zasady zgodności urządzeń w usłudze Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).|

## Zarządzanie komputerami z systemem Windows

|Nazwa zasad|Cel używania|
|---------------|------------------------|
|**Ustawienia agenta usługi Microsoft Intune**|Konfigurowanie klienta komputerowego usługi Intune na komputerach, w tym ustawień następujących funkcji:<br /><br />- Program Endpoint Protection<br />- Aktualizacje oprogramowania<br />- Harmonogram sprawdzania zasad<br /><br />Ten typ zasad można wdrożyć tylko w grupach urządzeń.<br /><br />Klienci usługi Intune pobierają nowe i zaktualizowane zasady zgodnie z ustawieniem **Częstotliwość wykrywania aktualizacji i aplikacji** (domyślnie jest to 8 godzin). Możesz jednak wymusić odświeżenie zasad na komputerach w dowolnym momencie.<br /><br />Aby uzyskać więcej informacji, zobacz [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Ustawienia programu Microsoft Intune Center**|Konfigurowanie szczegółów wyświetlanych w programie Microsoft Intune Center na zarządzanych komputerach.<br /><br />Ten typ zasad można wdrożyć tylko w grupach urządzeń.<br /><br />Aby uzyskać więcej informacji, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).|
|**Ustawienia Zapory systemu Windows**|Konfigurowanie ustawień Zapory systemu Windows i wyjątków dla typowej komunikacji sieciowej na komputerach, w tym następujących funkcjonalności:<br /><br />- Usługa BranchCache<br />- Pomoc zdalna<br />- Udostępnianie multimediów<br /><br />Ten typ zasad można wdrożyć tylko w grupach urządzeń.<br /><br />Aby uzyskać więcej informacji, zobacz [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).|

### Zobacz też

[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


