---
title: Profile urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przegląd różnych profilów urządzeń usługi Microsoft Intune, takich jak na przykład funkcje, ograniczenia, poczta e-mail, sieć Wi-Fi, sieć VPN, wiedza, certyfikaty, uaktualnianie systemu Windows 10, funkcji BitLocker i usługi Windows Defender, usługa Windows Information Protection i niestandardowe ustawienia konfiguracji w witrynie Azure Portal. Te profile służą do zarządzania danymi i urządzeniami oraz ich ochrony w Twojej firmie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b942f794136ce1a1d7851b0b04d6df70ea7174c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Co to są profile urządzeń w usłudze Microsoft Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Microsoft Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są zarządzane przy użyciu profilów. Oto kilka przykładów profilów: 

- Profil sieci Wi-Fi, który zapewnia różnym urządzeniom dostęp do firmowej sieci Wi-Fi
- Profil sieci VPN, który zapewnia różnym urządzeniom dostęp do serwera sieci VPN w sieci firmowej

Ten temat zawiera omówienie różnych profilów, które można utworzyć dla urządzeń. Profile te umożliwiają lub uniemożliwiają korzystanie z niektórych funkcji urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem
Aby wyświetlić dostępne funkcje, otwórz witrynę [Azure Portal](https://portal.azure.com), a następnie otwórz zasób usługi Intune. 

**Konfiguracja urządzenia** obejmuje następujące opcje:

- **Omówienie**: lista stanów profilów oraz dodatkowe szczegółowe informacje o profilach przypisanych do użytkowników i urządzeń
- **Zarządzanie**: tworzenie profilów urządzeń i przekazywanie niestandardowych [skryptów programu PowerShell](intune-management-extension.md) do uruchamiania w profilu
- **Monitorowanie**: sprawdzanie stanu profilu (powodzenie lub niepowodzenie) oraz wyświetlanie dzienników dotyczących profilów
- **Instalator**: dodawanie urzędu certyfikacji (SCEP lub PFX) lub włączanie zarządzania wydatkami telekomunikacyjnymi w profilu

## <a name="create-the-profile"></a>Tworzenie profilu

[Tworzenie profilów urządzeń](device-profile-create.md) — ten temat zawiera szczegółowe wskazówki krok po kroku, aby utworzyć profil. 

## <a name="device-features-profile"></a>Profil Funkcje urządzenia

Profil [Funkcje urządzenia](device-features-configure.md) steruje funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i udostępniane konfiguracje urządzeń.

Ta funkcja obsługuje systemy:  
- iOS 
- macOS

## <a name="device-restrictions-profile"></a>Profil Ograniczenia dotyczące urządzeń
Profil [Ograniczenia urządzenia](device-restrictions-configure.md) steruje zabezpieczeniami, sprzętem, udostępnianiem danych i kolejnymi ustawieniami urządzeń. Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- macOS
- Windows 10
- Zespół ds. systemu Windows 10

## <a name="email-profile"></a>Profil e-mail
Profil [Ustawienia poczty e-mail](email-settings-configure.md) profil tworzy, przypisuje i monitoruje ustawienia poczty e-mail programu Exchange ActiveSync na urządzeniach. Profile poczty e-mail zapewniają spójność i zmniejszają liczbę interwencji obsługi oraz umożliwiają użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- Windows Phone 8,1
- Windows 10

## <a name="wi-fi-profile"></a>Profil sieci Wi-Fi
Profil [Ustawienia sieci Wi-Fi](wi-fi-settings-configure.md) przypisuje ustawienia sieci bezprzewodowej do użytkowników i urządzeń. W przypadku przypisania profilu sieci Wi-Fi Twoi użytkownicy uzyskają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- macOS
- Windows 8.1 (tylko import)

## <a name="vpn-profile"></a>Profil sieci VPN
Profil [Ustawienia sieci VPN](vpn-settings-configure.md) przypisuje profile sieci VPN do użytkowników i urządzeń w organizacji w taki sposób, aby łączenie się z siecią było łatwe i bezpieczne. 

Wirtualne sieci prywatne (VPN) zapewniają Twoim użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- macOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10

## <a name="education-profile"></a>Profil edukacji
Profil [Ustawienia edukacji](education-settings-configure.md) umożliwia konfigurowanie opcji [aplikacji systemu Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). Po skonfigurowaniu tych opcji do czasu ukończenia testu nie można uruchomić na urządzeniu żadnych innych aplikacji.

## <a name="certificates-profile"></a>Profil Certyfikaty
Profil [Certyfikaty](certificates-configure.md) umożliwia skonfigurowanie zaufanych certyfikatów oraz certyfikatów SCEP i PKCS, które mogą zostać przypisane do urządzeń i być używane do uwierzytelniania sieci Wi-Fi, sieci VPN oraz profilów poczty e-mail.

Ta funkcja obsługuje systemy: 

- Android
- iOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10

## <a name="edition-upgrade-profile"></a>Profil Uaktualnianie wersji
Profil [Uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md) umożliwia automatyczne uaktualnianie urządzeń z niektórymi wersjami systemu Windows 10.

Ta funkcja obsługuje systemy: tylko Windows 10

## <a name="endpoint-protection-profile"></a>Profil programu Endpoint Protection
Profil [Ustawienia programu Endpoint Protection dla systemu Windows 10](endpoint-protection-windows-10.md) umożliwia konfigurowanie ustawień funkcji BitLocker i usługa Windows Defender dla urządzeń z systemem Windows 10.

Aby dołączyć zaawansowaną ochronę przed zagrożeniami w usłudze Windows Defender do usługi Microsoft Intune, zobacz [Configure endpoints using Mobile Device Management (MDM) tools (Konfigurowanie punktów końcowych przy użyciu narzędzi do zarządzania urządzeniami przenośnymi)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Ta funkcja obsługuje systemy: tylko Windows 10

## <a name="windows-information-protection-profile"></a>Profil usługi Windows Information Protection
Profil [Windows Information Protection](windows-information-protection-configure.md) ułatwia ochronę przed wyciekami danych bez zakłócania pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, których pracownicy używają w pracy. Robi to bez konieczności wprowadzania zmian środowiska lub innych aplikacji.

Ta funkcja obsługuje systemy: tylko Windows 10

## <a name="custom-profile"></a>Profil niestandardowy
Profil [Ustawienia niestandardowe](custom-settings-configure.md) obejmuje możliwość przypisania ustawień urządzenia, które nie są wbudowane w usłudze Intune. Na przykład na urządzeniach z systemem Android można wprowadzić wartości identyfikatora OMA-URI. W przypadku urządzeń z systemem iOS można zaimportować plik konfiguracyjny utworzony za pomocą programu Apple Configurator. 

Ta funkcja obsługuje systemy:

- Android
- iOS
- macOS
- Windows Phone 8,1