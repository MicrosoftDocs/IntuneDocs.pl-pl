---
title: Ustawienia i funkcje urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Omówienie różnych profilów urządzeń usługi Microsoft Intune. Uzyskaj informacje na temat funkcji, ograniczeń, poczty e-mail, sieci Wi-Fi, sieć VPN, wiedzy, certyfikatów, uaktualniania systemu Windows 10, funkcji BitLocker i usługi Microsoft Defender, usługi Windows Information Protection, szablonów administracyjnych i niestandardowych ustawień konfiguracji w witrynie Azure Portal. Te profile służą do zarządzania danymi i urządzeniami oraz ich ochrony w Twojej firmie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0dd9eddd986e6717e6bf706b02a7b06f712a032
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059893"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Stosowanie funkcji i ustawień w urządzeniach przy użyciu profilów urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Microsoft Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są dodawane do „profili konfiguracji”. Możesz utworzyć profile dla różnych urządzeń i różnych platform, w tym systemów iOS, Android i Windows. Następnie użyj usługi Intune, aby zastosować lub „przypisać” profil na urządzeniach.

Jako część rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych profilów konfiguracji w celu wykonywania różnych zadań. Oto kilka przykładów profilów:

- W urządzeniach z systemem Windows 10 użyj szablonu profilu, który blokuje kontrolki ActiveX w programie Internet Explorer.
- W urządzeniach z systemem iOS lub macOS zezwól użytkownikom na korzystanie z drukarek AirPrint w Twojej organizacji.
- Umożliwiaj lub blokuj dostęp do funkcji Bluetooth w urządzeniu.
- Utwórz profil sieci WiFi lub VPN, który zapewnia różnym urządzeniom dostęp do sieci firmowej.
- Zarządzaj aktualizacjami oprogramowania, łącznie z czasem ich instalacji.
- Uruchom urządzenie z systemem Android jako dedykowane urządzenie kiosku, które umożliwia uruchamianie jednej lub wielu aplikacji.

Ten artykuł zawiera omówienie różnych profilów, które możesz utworzyć. Profile te umożliwiają lub uniemożliwiają korzystanie z niektórych funkcji urządzenia.

## <a name="administrative-templates"></a>Szablony administracyjne

[Szablony administracyjne](administrative-templates-windows.md) obejmują setki ustawień, które można skonfigurować dla programu Internet Explorer, usługi OneDrive, pulpitu zdalnego, programów Word, Excel i innych programów pakietu Office.

Te szablony zapewniają administratorom uproszczony widok ustawień przypominający zasady grupy, ale są w pełni oparte na chmurze.

Ta funkcja obsługuje systemy:

- Windows 10 1809 i nowsze wersje – obsługiwane oprogramowanie układowe.

## <a name="certificates"></a>Certyfikaty

[Certyfikaty](../protect/certificates-configure.md) umożliwiają konfigurowanie certyfikatów zaufanych, SCEP i PKCS przypisywanych do urządzenia. Te certyfikaty uwierzytelniają profile sieci Wi-Fi i VPN oraz profile poczty e-mail.

Ta funkcja obsługuje systemy: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10 lub nowszym

## <a name="custom-profile"></a>Profil niestandardowy

[Ustawienia niestandardowe](custom-settings-configure.md) umożliwiają administratorom przypisywanie ustawień urządzenia, które nie są wbudowane w usługę Intune. Na urządzeniach z systemem Android można wprowadzić wartości identyfikatora OMA-URI. W przypadku urządzeń z systemem iOS można zaimportować plik konfiguracyjny utworzony za pomocą programu Apple Configurator.

Ta funkcja obsługuje systemy:

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8,1

## <a name="delivery-optimization"></a>Optymalizacja dostarczania

[Optymalizacja dostarczania](delivery-optimization-windows.md) zapewnia lepsze środowisko dostarczania aktualizacji oprogramowania. Te ustawienia są zastępowane ustawieniami z obszaru **Aktualizacja oprogramowania** > **Pierścień aktualizacji systemu Windows 10**.

Ustawienia te służą do kontrolowania sposobu pobierania aktualizacji oprogramowania na urządzenia w organizacji. Na przykład można zezwolić użytkownikom na pobieranie własnych aktualizacji lub uzyskiwanie aktualizacji za pomocą usług w chmurze optymalizacji dostarczania w profilu urządzenia.

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym

## <a name="device-features"></a>Funkcje urządzenia

Profil [Funkcje urządzenia](device-features-configure.md) steruje funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i komunikaty na ekranie blokady.

Ta funkcja obsługuje systemy:

- iOS/iPadOS
- macOS

## <a name="device-firmware-configuration-interface"></a>Interfejs konfiguracji oprogramowania układowego urządzenia

[Interfejs konfiguracji oprogramowania układowego urządzenia ](device-firmware-configuration-interface-windows.md) (DFCI) umożliwia administratorom włączanie lub wyłączanie ustawień interfejsu UEFI (BIOS) za pomocą usługi Intune. Te ustawienia umożliwiają podwyższenie poziomu zabezpieczeń na poziomie oprogramowania układowego, które jest zwykle bardziej odporne na złośliwe ataki.

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym

## <a name="device-restrictions"></a>Ograniczenia dotyczące urządzeń

Profil [Ograniczenia urządzenia](device-restrictions-configure.md) steruje zabezpieczeniami, sprzętem, udostępnianiem danych i kolejnymi ustawieniami urządzeń. Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia. 

Ta funkcja obsługuje systemy:

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 10 lub nowszym
- Zespół ds. systemu Windows 10

## <a name="edition-upgrade"></a>Zasady uaktualniania wersji

Profil [Uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md) umożliwia automatyczne uaktualnianie urządzeń z niektórymi wersjami systemu Windows 10.

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym

## <a name="education"></a>Edukacja

Profil [Ustawienia edukacji — Windows 10](education-settings-configure.md) umożliwia konfigurowanie opcji [aplikacji systemu Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). Po skonfigurowaniu tych opcji do czasu ukończenia testu nie można uruchomić na urządzeniu żadnych innych aplikacji.

Profil [Ustawienia edukacyjne — iOS](../fundamentals/education-settings-configure-ios-shared.md) korzysta z aplikacji Classroom dla systemu iOS, która pomaga nauczycielom w prowadzeniu nauczania oraz kontrolowaniu urządzeń uczniów w klasie. Możesz skonfigurować urządzenia iPad w taki sposób, aby wielu uczniów mogło współużytkować jedno urządzenie.

## <a name="email"></a>Poczta e-mail

W obszarze [Ustawienia poczty e-mail](email-settings-configure.md) można tworzyć, przypisywać i monitorować ustawienia poczty e-mail programu Exchange ActiveSync na urządzeniach. Profile poczty e-mail pomagają zapewnić spójność i zmniejszają liczbę interwencji obsługi oraz umożliwiają użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie. 

Ta funkcja obsługuje systemy: 

- Android
- Android Enterprise
- iOS/iPadOS
- Windows Phone 8,1
- Windows 10 lub nowszym

## <a name="endpoint-protection"></a>Program Endpoint Protection

Profil [Ustawienia programu Endpoint Protection dla systemu Windows 10](../protect/endpoint-protection-windows-10.md) umożliwia konfigurowanie ustawień funkcji BitLocker i usługa Microsoft Defender dla urządzeń z systemem Windows 10.

Aby dołączyć usługę Microsoft Defender Advanced Threat Protection do usługi Microsoft Intune, zobacz temat [Configure endpoints using Mobile Device Management (MDM) tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-mdm) (Konfigurowanie punktów końcowych przy użyciu narzędzi do zarządzania urządzeniami mobilnymi).

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym

## <a name="esim-cellular---public-preview"></a>Sieć komórkowa eSIM — publiczna wersja zapoznawcza

[Profile sieci komórkowej eSIM](esim-device-configuration.md) umożliwiają administratorom konfigurowanie planów danych komórkowych na zarządzanych urządzeniach w celu uzyskania dostępu do Internetu i danych. Po otrzymaniu kodów aktywacji od operatora sieci komórkowej należy zaimportować je w usłudze Intune, a następnie przypisać je do urządzeń obsługujących kartę eSIM.

Ta funkcja obsługuje systemy:

- Windows 10 Fall Creators Update i nowsze

## <a name="extensions"></a>Rozszerzenia

Opcja [Rozszerzenia jądra](kernel-extensions-overview-macos.md) umożliwia administratorom dodawanie funkcji lub programów na poziomie jądra na urządzeniach z systemem macOS. Skonfiguruj te ustawienia, aby ufać wszystkim rozszerzeniom określonego dewelopera lub partnera lub zezwalać na określone rozszerzenia jądra.

Ta funkcja obsługuje systemy:

- macOS

## <a name="identity-protection"></a>Identity Protection

Usługa [Identity Protection](../protect/identity-protection-configure.md) steruje środowiskiem usługi Windows Hello dla firm na urządzeniach z systemem Windows 10 i Windows 10 Mobile. Skonfiguruj te ustawienia, aby udostępnić usługę Windows Hello dla firm dla użytkowników i urządzeń oraz określić wymagania dotyczące numerów PIN urządzenia i gestów.  

Ta funkcja obsługuje systemy:  

- Windows 10 lub nowszym
- Windows Holographic for Business  

## <a name="kiosk"></a>Kiosk

Profil [Ustawienia kiosku](kiosk-settings.md) służy do konfigurowania urządzenia pod kątem uruchamiania jednej lub wielu aplikacji. Możesz również dostosować inne funkcje kiosku, w tym menu Start i przeglądarkę internetową.

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym

Ustawienia kiosku są również dostępne jako ograniczenia urządzenia z systemem [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) i [ios](device-restrictions-ios.md#kiosk).

## <a name="oemconfig"></a>OEMConfig

[OEMConfig](android-oem-configuration-overview.md) to standard, który umożliwia producentom OEM (producentom oryginalnego sprzętu) i rozwiązaniom EMM (Enterprise Mobility Management) tworzenie i obsługę funkcji specyficznych dla producentów OEM w ustandaryzowany sposób na urządzeniach z systemem Android Enterprise. Za pomocą aplikacji OEMConfig producent OEM tworzy schemat definiujący funkcje zarządzania specyficzne dla producenta OEM i osadza je w aplikacji przekazanej do sklepu Google Play. Usługa Intune odczytuje schemat z aplikacji, dzięki czemu administratorzy usługi Intune mogą konfigurować ustawienia w schemacie.

Ta funkcja obsługuje systemy:

- Android Enterprise (OEMConfig)

## <a name="powershell-scripts"></a>Skrypty środowiska PowerShell

[Skrypty środowiska PowerShell na urządzeniach z systemem Windows 10](../apps/intune-management-extension.md) używają rozszerzenia do zarządzania usługi Intune do przekazywania skryptów środowiska PowerShell w usłudze Intune, a następnie uruchamiania tych skryptów na urządzeniach. Sprawdź również, co jest wymagane do korzystania z rozszerzenia, jak dodać je do usługi Intune oraz inne ważne informacje.


Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym
- Windows Holographic for Business

## <a name="shared-multi-user-device"></a>Urządzenie udostępnione używane przez wielu użytkowników

Profile [Windows 10](shared-user-device-settings-windows.md) i [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) obejmują ustawienia zarządzania urządzeniami z wieloma użytkownikami, nazywanymi urządzeniami udostępnionymi lub komputerami udostępnionymi. Możesz określić, czy użytkownik zalogowany do urządzenia może zmieniać opcje uśpienia lub zapisywać pliki w urządzeniu. W innym przykładzie w celu zaoszczędzenia miejsca możesz utworzyć profil, który usuwa nieaktywne poświadczenia z urządzeń Windows HoloLens.

Te ustawienia urządzeń udostępnionych z wieloma użytkownikami pozwalają administratorowi sterowanie niektórymi funkcjami urządzeń i zarządzać tymi urządzeniami udostępnionymi przy użyciu usługi Intune.

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym
- Windows Holographic for Business

## <a name="update-policies"></a>Zasady aktualizacji

W sekcji [Zasady aktualizacji systemu iOS](../protect/software-updates-ios.md) pokazano, jak utworzyć i przypisać zasady systemu iOS w celu zainstalowania aktualizacji oprogramowania na urządzeniach z systemem iOS. Można również sprawdzić stan instalacji.

Aby uzyskać informacje o zasadach aktualizacji urządzeń z systemem Windows, zobacz [Optymalizacja dostarczania](delivery-optimization-windows.md). 

Ta funkcja obsługuje systemy:

- iOS/iPadOS

## <a name="vpn"></a>VPN

Profil [Ustawienia sieci VPN](vpn-settings-configure.md) przypisuje profile sieci VPN do użytkowników i urządzeń w organizacji w taki sposób, aby łączenie się z siecią było łatwe i bezpieczne. 

Wirtualne sieci prywatne (VPN) zapewniają Twoim użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. 

Ta funkcja obsługuje systemy: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10 lub nowszym

## <a name="wi-fi"></a>Wi-Fi

Profil [Ustawienia sieci Wi-Fi](wi-fi-settings-configure.md) przypisuje ustawienia sieci bezprzewodowej do użytkowników i urządzeń. W przypadku przypisania profilu sieci Wi-Fi Twoi użytkownicy uzyskają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia. 

Ta funkcja obsługuje systemy: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 (tylko import)
- Windows 10 lub nowszym

## <a name="windows-information-protection-profile"></a>Profil usługi Windows Information Protection

Profil [Windows Information Protection](../protect/windows-information-protection-configure.md) ułatwia ochronę przed wyciekami danych bez zakłócania pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, których pracownicy używają w pracy. Korzystanie z zestawu funkcji Windows Information Protection nie wymaga zmian środowiska ani innych aplikacji.

Ta funkcja obsługuje systemy:

- Windows 10 lub nowszym

## <a name="zebra-mobility-extensions-mx"></a>Zebra Mobility Extensions (MX)

Funkcja [Zebra Mobility Extensions (MX)](android-zebra-mx-overview.md) pozwala administratorom na używanie urządzeń Zebra i zarządzanie nimi w usłudze Intune. Należy utworzyć profile rozwiązania StageNow z wybranymi ustawieniami, a następnie przypisać i wdrożyć te profile na urządzeniach Zebra przy użyciu usługi Intune. Artykuł [StageNow logs and common issues](android-zebra-mx-logs-troubleshoot.md) (Dzienniki rozwiązania StageNow i typowe problemy) jest doskonałym zasobem ułatwiającym rozwiązywanie problemów z profilami oraz zapoznanie się potencjalnym problemami w przypadku korzystania z rozwiązania StageNow.

Ta funkcja obsługuje systemy:

- Android (Mobility Extensions)

## <a name="manage-and-troubleshoot"></a>Zarządzanie i rozwiązywanie problemów

[Zarządzaj profilami](device-profile-monitor.md), aby sprawdzić stan urządzeń i przypisane profile. Możesz też pomóc w rozwiązywaniu konfliktów, sprawdzając ustawienia powodujące konflikt i profile, które uwzględniają te ustawienia. Artykuł [Typowe problemy i rozwiązania](device-profile-troubleshoot.md) pomaga administratorom w pracy z profilami. Pokazuje on, co się dzieje podczas usuwania profilu, co powoduje wysyłanie powiadomień do urządzeń i przedstawia inne informacje.

## <a name="next-steps"></a>Następne kroki

Wybierz platformę i rozpocznij pracę.
