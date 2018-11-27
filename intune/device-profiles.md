---
title: Profile urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przegląd różnych profilów urządzeń usługi Microsoft Intune, takich jak na przykład funkcje, ograniczenia, poczta e-mail, sieć Wi-Fi, sieć VPN, wiedza, certyfikaty, uaktualnianie systemu Windows 10, funkcji BitLocker i usługi Windows Defender, usługa Windows Information Protection i niestandardowe ustawienia konfiguracji w witrynie Azure Portal. Te profile służą do zarządzania danymi i urządzeniami oraz ich ochrony w Twojej firmie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: ec3535004dccedb5b0310f4ecc10bb5c93f0ea43
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186889"
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Co to są profile urządzeń w usłudze Microsoft Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Microsoft Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są zarządzane przy użyciu profilów. Oto kilka przykładów profilów: 

- Profil sieci Wi-Fi, który zapewnia różnym urządzeniom dostęp do firmowej sieci Wi-Fi
- Profil sieci VPN, który zapewnia różnym urządzeniom dostęp do serwera sieci VPN w sieci firmowej

Ten artykuł zawiera omówienie różnych profilów, które można utworzyć dla urządzeń. Profile te umożliwiają lub uniemożliwiają korzystanie z niektórych funkcji urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem
Aby wyświetlić dostępne funkcje, otwórz witrynę [Azure Portal](https://portal.azure.com), a następnie otwórz zasób usługi Intune. 

**Konfiguracja urządzenia** obejmuje następujące opcje:

- **Omówienie**: lista stanów profilów oraz dodatkowe szczegółowe informacje o profilach przypisanych do użytkowników i urządzeń
- **Zarządzanie**: tworzenie profilów urządzeń i przekazywanie niestandardowych [skryptów programu PowerShell](intune-management-extension.md) do uruchamiania w profilu
- **Monitorowanie**: sprawdzanie stanu profilu (powodzenie lub niepowodzenie) oraz wyświetlanie dzienników dotyczących profilów
- **Instalator**: dodawanie urzędu certyfikacji (SCEP lub PFX) lub włączanie zarządzania wydatkami telekomunikacyjnymi w profilu

## <a name="create-the-profile"></a>Tworzenie profilu

[Tworzenie profilów urządzeń](device-profile-create.md) — ten temat zawiera szczegółowe wskazówki krok po kroku, aby utworzyć profil. 

## <a name="device-features---ios-and-macos"></a>Funkcje urządzeń — system iOS i macOS

Profil [Funkcje urządzenia](device-features-configure.md) steruje funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i udostępniane konfiguracje urządzeń.

Ta funkcja obsługuje systemy:
- iOS 
- macOS


## <a name="device-restrictions"></a>Ograniczenia dotyczące urządzeń
Profil [Ograniczenia urządzenia](device-restrictions-configure.md) steruje zabezpieczeniami, sprzętem, udostępnianiem danych i kolejnymi ustawieniami urządzeń. Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia. 

Ta funkcja obsługuje systemy:

- Android
- iOS
- macOS
- Windows 10
- Zespół ds. systemu Windows 10

## <a name="endpoint-protection"></a>Program Endpoint Protection
Profil [Ustawienia programu Endpoint Protection dla systemu Windows 10](endpoint-protection-windows-10.md) umożliwia konfigurowanie ustawień funkcji BitLocker i usługa Windows Defender dla urządzeń z systemem Windows 10.

Aby dołączyć zaawansowaną ochronę przed zagrożeniami w usłudze Windows Defender do usługi Microsoft Intune, zobacz [Configure endpoints using Mobile Device Management (MDM) tools (Konfigurowanie punktów końcowych przy użyciu narzędzi do zarządzania urządzeniami przenośnymi)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Ta funkcja obsługuje systemy:
- System Windows 10 lub nowszy

## <a name="identity-protection"></a>Identity Protection
Usługa [Identity Protection](identity-protection-configure.md) steruje środowiskiem usługi Windows Hello dla firm na urządzeniach z systemem Windows 10 i Windows 10 Mobile. Skonfiguruj te ustawienia, aby udostępnić usługę Windows Hello dla firm dla użytkowników i urządzeń oraz określić wymagania dotyczące numerów PIN urządzenia i gestów.  

Ta funkcja obsługuje systemy:  
- System Windows 10 lub nowszy
- Windows Holographic for Business  

## <a name="kiosk"></a>Kiosk

Profil [Ustawienia kiosku](kiosk-settings.md) służy do konfigurowania urządzenia pod kątem uruchamiania jednej lub wielu aplikacji. Możesz również dostosować inne funkcje kiosku, w tym menu Start i przeglądarkę internetową.

Ta funkcja obsługuje systemy:
- System Windows 10 lub nowszy

## <a name="email"></a>Poczta e-mail
Profil [Ustawienia poczty e-mail](email-settings-configure.md) profil tworzy, przypisuje i monitoruje ustawienia poczty e-mail programu Exchange ActiveSync na urządzeniach. Profile poczty e-mail zapewniają spójność i zmniejszają liczbę interwencji obsługi oraz umożliwiają użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- Windows Phone 8,1
- Windows 10

## <a name="vpn"></a>VPN
Profil [Ustawienia sieci VPN](vpn-settings-configure.md) przypisuje profile sieci VPN do użytkowników i urządzeń w organizacji w taki sposób, aby łączenie się z siecią było łatwe i bezpieczne. 

Wirtualne sieci prywatne (VPN) zapewniają Twoim użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- macOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10

## <a name="wi-fi"></a>Wi-Fi
Profil [Ustawienia sieci Wi-Fi](wi-fi-settings-configure.md) przypisuje ustawienia sieci bezprzewodowej do użytkowników i urządzeń. W przypadku przypisania profilu sieci Wi-Fi Twoi użytkownicy uzyskają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia. 

Ta funkcja obsługuje systemy: 

- Android
- iOS
- macOS
- Windows 8.1 (tylko import)

## <a name="esim-cellular---public-preview"></a>Sieć komórkowa eSIM — publiczna wersja zapoznawcza

[Profile sieci komórkowej eSIM](esim-device-configuration.md) umożliwiają konfigurowanie planów danych komórkowych na zarządzanych urządzeniach w celu uzyskania dostępu do Internetu i danych.  Po otrzymaniu kodów aktywacji od operatora sieci komórkowej zaimportować je w usłudze Intune, a następnie przypisać je do urządzeń obsługujących kartę eSIM.

Ta funkcja obsługuje systemy:
- Windows 10 Fall Creators Update i nowsze

## <a name="education"></a>Edukacja
Profil [Ustawienia edukacji — Windows 10](education-settings-configure.md) umożliwia konfigurowanie opcji [aplikacji systemu Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). Po skonfigurowaniu tych opcji do czasu ukończenia testu nie można uruchomić na urządzeniu żadnych innych aplikacji.

Profil [Ustawienia edukacyjne — iOS](education-settings-configure-ios-shared.md) korzysta z aplikacji Classroom dla systemu iOS, która pomaga nauczycielom w prowadzeniu nauczania oraz kontrolowaniu urządzeń uczniów w klasie. Możesz skonfigurować urządzenia iPad w taki sposób, aby wielu uczniów mogło współużytkować jedno urządzenie.

## <a name="edition-upgrade"></a>Zasady uaktualniania wersji
Profil [Uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md) umożliwia automatyczne uaktualnianie urządzeń z niektórymi wersjami systemu Windows 10.

Ta funkcja obsługuje systemy: 
- System Windows 10 lub nowszy

## <a name="update-policies"></a>Zasady aktualizacji
W sekcji [Zasady aktualizacji systemu iOS](software-updates-ios.md) pokazano, jak utworzyć i przypisać zasady systemu iOS w celu zainstalowania aktualizacji oprogramowania na urządzeniach z systemem iOS. Można również sprawdzić stan instalacji.

Ta funkcja obsługuje systemy:
- iOS

## <a name="certificates"></a>Certyfikaty
Profil [Certyfikaty](certificates-configure.md) umożliwia skonfigurowanie zaufanych certyfikatów oraz certyfikatów SCEP i PKCS, które mogą zostać przypisane do urządzeń i być używane do uwierzytelniania sieci Wi-Fi, sieci VPN oraz profilów poczty e-mail.

Ta funkcja obsługuje systemy: 

- Android
- iOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10

## <a name="windows-information-protection-profile"></a>Profil usługi Windows Information Protection
Profil [Windows Information Protection](windows-information-protection-configure.md) ułatwia ochronę przed wyciekami danych bez zakłócania pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, których pracownicy używają w pracy. Robi to bez konieczności wprowadzania zmian środowiska lub innych aplikacji.

Ta funkcja obsługuje systemy:
- System Windows 10 lub nowszy

## <a name="custom-profile"></a>Profil niestandardowy
Profil [Ustawienia niestandardowe](custom-settings-configure.md) obejmuje możliwość przypisania ustawień urządzenia, które nie są wbudowane w usłudze Intune. Na przykład na urządzeniach z systemem Android można wprowadzić wartości identyfikatora OMA-URI. W przypadku urządzeń z systemem iOS można zaimportować plik konfiguracyjny utworzony za pomocą programu Apple Configurator. 

Ta funkcja obsługuje systemy:

- Android
- iOS
- macOS
- Windows Phone 8,1

## <a name="manage-and-troubleshoot"></a>Zarządzanie i rozwiązywanie problemów

[Zarządzaj profilami](device-profile-monitor.md), aby sprawdzić stan urządzeń i przypisane profile. Możesz też pomóc w rozwiązywaniu konfliktów, sprawdzając ustawienia powodujące konflikt i profile, które zawierają te ustawienia. [Typowe problemy i rozwiązania](device-profile-troubleshoot.md) obejmują listę pytań i odpowiedzi ułatwiających pracę z profilami, w tym zachowanie w przypadku usunięcia profilu, przyczyny wysyłania powiadomień do urządzeń i nie tylko.