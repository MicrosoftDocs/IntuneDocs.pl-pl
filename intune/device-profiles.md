---
title: Ustawienia i funkcje urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przegląd różnych profilów urządzeń usługi Microsoft Intune, takich jak na przykład funkcje, ograniczenia, poczta e-mail, sieć Wi-Fi, sieć VPN, wiedza, certyfikaty, uaktualnianie systemu Windows 10, funkcji BitLocker i usługi Windows Defender, usługa Windows Information Protection, szablony administracyjne i niestandardowe ustawienia konfiguracji w witrynie Azure Portal. Te profile służą do zarządzania danymi i urządzeniami oraz ich ochrony w Twojej firmie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: bc28bca31c43140a7bca528655825bab60c53be1
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203522"
---
# <a name="apply-features-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Stosowanie ustawień funkcji w urządzeniach przy użyciu profili urządzeń w usłudze Microsoft Intune

Usługa Microsoft Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są dodawane do „profili konfiguracji”. Możesz tworzyć profile dla różnych urządzeń różnych platform, w tym systemów iOS, Android i Windows, a następnie zastosować profil za pomocą usługi Intune do urządzeń w Twojej organizacji.

Oto kilka przykładów profilów:

- W urządzeniach z systemem Windows 10 użyj szablonu profilu, który blokuje kontrolki ActiveX w programie Internet Explorer.
- W urządzeniach z systemem iOS lub macOS zezwól użytkownikom na korzystanie z drukarek AirPrint w Twojej organizacji.
- Umożliwiaj lub blokuj dostęp do funkcji Bluetooth w urządzeniu.
- Utwórz profil sieci WiFi lub VPN, który zapewnia różnym urządzeniom dostęp do sieci firmowej.
- Zarządzaj aktualizacjami oprogramowania, łącznie z czasem ich instalacji.
- Uruchom dedykowane urządzenie kiosku z systemem Android, które umożliwia uruchamianie jednej lub wielu aplikacji.

Ten artykuł zawiera instrukcje dotyczące tworzenia profilu oraz omówienie różnych typów profili, które można utworzyć. Profile te umożliwiają lub uniemożliwiają korzystanie z niektórych funkcji urządzenia.

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.

2. Wybierz pozycję **Konfiguracja urządzenia**. Do wyboru są następujące opcje:

    - **Omówienie**: lista stanów profilów oraz dodatkowe szczegółowe informacje o profilach przypisanych do użytkowników i urządzeń.
    - **Zarządzanie**: tworzenie profili urządzeń, przekazywanie niestandardowych [skryptów programu PowerShell](intune-management-extension.md) do uruchamiania w profilu i dodawanie planów danych do urządzeń korzystających z karty [eSIM](esim-device-configuration.md).
    - **Monitorowanie**: sprawdzanie stanu profilu (powodzenie lub niepowodzenie) oraz wyświetlanie dzienników dotyczących profili.
    - **Instalator**: dodawanie urzędu certyfikacji SCEP lub PFX albo włączanie [zarządzania wydatkami telekomunikacyjnymi](telecom-expenses-monitor.md) w profilu.

3. Wybierz pozycję **Profile**  >  **Utwórz profil**. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę profilu.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:  

       - **Android**
       - **Android enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 lub nowszy**
       - **Windows 10 lub nowszy**

   - **Typ profilu**: Wybierz typ ustawień, który chcesz utworzyć. Wyświetlana lista zależy od wybranej **platformy**:

       - [Szablony administracyjne](administrative-templates-windows.md)
       - [Niestandardowe](custom-settings-configure.md)
       - [Optymalizacja dostarczania](delivery-optimization-windows.md)
       - [Funkcje urządzenia](device-features-configure.md)
       - [Ograniczenia dotyczące urządzeń](device-restrictions-configure.md)
       - [Uaktualnianie wersji i przełącznik trybów](edition-upgrade-configure-windows-10.md)
       - [Edukacja](education-settings-configure.md)
       - [Poczta e-mail](email-settings-configure.md)
       - [Program Endpoint Protection](endpoint-protection-configure.md)
       - [Identity Protection](identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [Certyfikat PKCS](certficates-pfx-configure.md)
       - [Certyfikat SCEP](certificates-scep-configure.md)
       - [Zaufany certyfikat](certificates-configure.md)
       - [Zasady aktualizacji](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Zaawansowana ochrona przed zagrożeniami w usłudze Windows Defender](advanced-threat-protection.md)
       - [Rozwiązanie Windows Information Protection](windows-information-protection-configure.md)

     Jeśli na przykład wybierzesz platformę **iOS**, opcje typu profilu będą wyglądać podobnie do następujących:

     ![Tworzenie profilu systemu iOS w usłudze Intune](./media/create-device-profile.png)

4. Wybierz pozycję **Ustawienia**. Ustawienia są zorganizowane według kategorii. Wybierz kategorię, aby wyświetlić listę wszystkich ustawień, które można skonfigurować.

5. Po zakończeniu wybierz pozycję **OK**  >  **Utwórz**, aby zapisać zmiany.

Aby dowiedzieć się więcej na temat różnych typów profili, przeczytaj następne sekcje w tym artykule.

## <a name="administrative-templates-preview"></a>Szablony administracyjne (wersja zapoznawcza)

[Szablony administracyjne](administrative-templates-windows.md) obejmują setki ustawień, które można skonfigurować dla programu Internet Explorer, usługi OneDrive, pulpitu zdalnego, programów Word, Excel i innych programów pakietu Office oraz wiele innych ustawień.

Te szablony zapewniają administratorom uproszczony widok ustawień przypominający zasady grupy, ale są w pełni oparte na chmurze. 

Ta funkcja obsługuje systemy:

- System Windows 10 lub nowszy

## <a name="device-features"></a>Funkcje urządzenia

Profil [Funkcje urządzenia](device-features-configure.md) steruje funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i komunikaty na ekranie blokady.

Ta funkcja obsługuje systemy:

- iOS 
- macOS

## <a name="device-restrictions"></a>Ograniczenia dotyczące urządzeń

Profil [Ograniczenia urządzenia](device-restrictions-configure.md) steruje zabezpieczeniami, sprzętem, udostępnianiem danych i kolejnymi ustawieniami urządzeń. Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia. 

Ta funkcja obsługuje systemy:

- Android
- Android Enterprise
- iOS
- macOS
- Windows 10
- Zespół ds. systemu Windows 10

## <a name="delivery-optimization"></a>Optymalizacja dostarczania

[Optymalizacja dostarczania](delivery-optimization-windows.md) zapewnia lepsze środowisko dostarczania aktualizacji oprogramowania. Te ustawienia są zastępowane ustawieniami z obszaru **Aktualizacja oprogramowania** > **Pierścień aktualizacji systemu Windows 10**.

Ustawienia te służą do kontrolowania sposobu pobierania aktualizacji oprogramowania na urządzenia w organizacji. Na przykład można zezwolić użytkownikom na pobieranie własnych aktualizacji lub uzyskiwanie aktualizacji za pomocą usług w chmurze optymalizacji dostarczania w profilu urządzenia.

Ta funkcja obsługuje systemy:

- System Windows 10 lub nowszy

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

Ustawienia kiosku są również dostępne jako ograniczenia urządzenia z systemem [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) i [ios](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>Poczta e-mail

W obszarze [Ustawienia poczty e-mail](email-settings-configure.md) można tworzyć, przypisywać i monitorować ustawienia poczty e-mail programu Exchange ActiveSync na urządzeniach. Profile poczty e-mail pomagają zapewnić spójność i zmniejszają liczbę interwencji obsługi oraz umożliwiają użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie. 

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

[Profile sieci komórkowej eSIM](esim-device-configuration.md) umożliwiają administratorom konfigurowanie planów danych komórkowych na zarządzanych urządzeniach w celu uzyskania dostępu do Internetu i danych. Po otrzymaniu kodów aktywacji od operatora sieci komórkowej należy zaimportować je w usłudze Intune, a następnie przypisać je do urządzeń obsługujących kartę eSIM.

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

Aby uzyskać informacje o zasadach aktualizacji urządzeń z systemem Windows, zobacz [Optymalizacja dostarczania](delivery-optimization-windows.md). 

Ta funkcja obsługuje systemy:
- iOS

## <a name="certificates"></a>Certyfikaty

Profil [Certyfikaty](certificates-configure.md) umożliwia skonfigurowanie zaufanych certyfikatów oraz certyfikatów SCEP i PKCS, które są przypisywane do urządzeń i być używane do uwierzytelniania sieci Wi-Fi, sieci VPN oraz profilów poczty e-mail.

Ta funkcja obsługuje systemy: 

- Android
- iOS
- Windows Phone 8,1
- Windows 8.1
- Windows 10

## <a name="windows-information-protection-profile"></a>Profil usługi Windows Information Protection

Profil [Windows Information Protection](windows-information-protection-configure.md) ułatwia ochronę przed wyciekami danych bez zakłócania pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, których pracownicy używają w pracy. Korzystanie z zestawu funkcji Windows Information Protection nie wymaga zmian środowiska ani innych aplikacji.

Ta funkcja obsługuje systemy:

- System Windows 10 lub nowszy

## <a name="shared-multi-user-device"></a>Urządzenie udostępnione używane przez wielu użytkowników

Profile [Windows 10](shared-user-device-settings-windows.md) i [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) obejmują ustawienia zarządzania urządzeniami z wieloma użytkownikami, nazywanymi urządzeniami udostępnionymi lub komputerami udostępnionymi. Możesz określić, czy użytkownik zalogowany do urządzenia może zmieniać opcje uśpienia lub zapisywać pliki w urządzeniu. W innym przykładzie możesz utworzyć zasady, które usuwają nieaktywne poświadczeń z urządzeń Windows HoloLens, aby zaoszczędzić miejsce.

Te ustawienia urządzeń udostępnionych z wieloma użytkownikami pozwalają administratorowi sterowanie niektórymi funkcjami urządzeń i zarządzać tymi urządzeniami udostępnionymi przy użyciu usługi Intune.

Ta funkcja obsługuje systemy:

- System Windows 10 lub nowszy
- Windows Holographic for Business

## <a name="custom-profile"></a>Profil niestandardowy

[Ustawienia niestandardowe](custom-settings-configure.md) umożliwiają administratorom przypisywanie ustawień urządzenia, które nie są wbudowane w usługę Intune. Na przykład na urządzeniach z systemem Android można wprowadzić wartości identyfikatora OMA-URI. W przypadku urządzeń z systemem iOS można zaimportować plik konfiguracyjny utworzony za pomocą programu Apple Configurator. 

Ta funkcja obsługuje systemy:

- Android
- iOS
- macOS
- Windows Phone 8,1

## <a name="manage-and-troubleshoot"></a>Zarządzanie i rozwiązywanie problemów

[Zarządzaj profilami](device-profile-monitor.md), aby sprawdzić stan urządzeń i przypisane profile. Możesz też pomóc w rozwiązywaniu konfliktów, sprawdzając ustawienia powodujące konflikt i profile, które zawierają te ustawienia. [Typowe problemy i rozwiązania](device-profile-troubleshoot.md) obejmują pytania i odpowiedzi ułatwiające pracę z profilami, w tym zachowanie w przypadku usunięcia profilu, przyczyny wysyłania powiadomień do urządzeń i nie tylko.

## <a name="next-steps"></a>Następne kroki
Wybierz platformę i rozpocznij pracę:

