---
title: Konfigurowanie ustawień sieci VPN na urządzeniach z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune na urządzeniach z systemem iOS dodaj lub utwórz profil konfiguracji sieci VPN, korzystając z ustawień konfiguracji wirtualnej sieci prywatnej (VPN, virtual private network), w tym szczegółów połączenia, metod uwierzytelniania i dzielenia tuneli w ustawieniach podstawowych; niestandardowych ustawień sieci VPN z identyfikatorem i parami klucz-wartość; ustawień sieci VPN dla poszczególnych aplikacji, obejmujących adresy URL przeglądarki Safari oraz sieci VPN na żądanie z identyfikatorami SSID lub domenami wyszukiwania DNS; a także ustawień serwera proxy, obejmujących skrypt konfiguracji, adres IP lub nazwę FQDN i port TCP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9eb7ee99d69fd56707bd9dfe5453ffe0bb107bad
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885656"
---
# <a name="add-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Konfigurowanie ustawień sieci VPN na urządzeniach z systemem iOS w usłudze Microsoft Intune

Usługa Microsoft Intune obejmuje wiele ustawień sieci VPN, które mogą być wdrażane na urządzeniach z systemem iOS. Te ustawienia są używane do tworzenia i konfigurowania połączeń sieci VPN z siecią Twojej organizacji. W tym artykule opisano te ustawienia. Niektóre ustawienia są dostępne tylko dla niektórych klientów sieci VPN, takich jak Citrix, Zscaler itp.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md).

> [!NOTE]
> Te ustawienia są dostępne dla wszystkich typów rejestracji. Aby uzyskać więcej informacji na temat typów rejestracji, zobacz [rejestracji w systemie iOS](../enrollment/ios-enroll.md).

## <a name="connection-type"></a>Typ połączenia

Umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: Dotyczy aplikacji [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) w wersji 4.0.5x i starszej.
- **Cisco AnyConnect**: Dotyczy aplikacji [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) w wersji 4.0.7x i nowszej.
- **SonicWall Mobile Connect**
- **F5 Access Legacy**: Dotyczy aplikacji F5 Access w wersji 2.1 i starszej.
- **F5 Access**: Dotyczy aplikacji F5 Access w wersji 3.0 i nowszej.
- **Palo Alto Networks GlobalProtect (starsza wersja)** : Dotyczy aplikacji Palo Alto Networks GlobalProtect w wersji 4.1 i starszej.
- **Palo Alto Networks GlobalProtect**: Dotyczy aplikacji Palo Alto Networks GlobalProtect w wersji 5.0 i nowszej.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Sieć VPN Citrix**
- **Citrix SSO**
- **Zscaler**: Korzystanie z dostępu warunkowego lub umożliwianie użytkownikom pomijania ekranu logowania Zscaler wymaga integracji rozwiązania Zscaler Private Access (ZPA) z kontem usługi Azure AD. Aby uzyskać szczegółowe instrukcje, zobacz [dokumentację rozwiązania Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad). 
- **IKEv2**: [ustawienia protokołu IKEv2](#ikev2-settings) (w tym artykule) zawiera opis właściwości.
- **Niestandardowa sieć VPN**

> [!NOTE]
> Firmy Cisco, Citrix, F5 i Palo Alto ogłosiły, że ich starsi klienci nie działają w systemie iOS 12. Należy przeprowadzić migrację do nowych aplikacji tak szybko, jak to możliwe. Aby uzyskać więcej informacji, zobacz [blog zespołu pomocy technicznej usługi Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

Ustawienia wymienione na poniższej liście są określane przez wybrany typ połączenia VPN.  

- **Nazwa połączenia**: Użytkownicy końcowi widzą tę nazwę podczas przeglądania na urządzeniu listy dostępnych połączeń sieci VPN.
- **Niestandardowa nazwa domeny** (tylko rozwiązanie Zscaler): Wstępnie wypełnij pole logowania aplikacji rozwiązania Zscaler nazwą domeny, do której należą Twoi użytkownicy. Jeśli na przykład nazwa użytkownika to `Joe@contoso.net`, domena `contoso.net` statycznie pojawi się w polu po otwarciu aplikacji. Jeśli nie wprowadzisz nazwy domeny, zostanie użyta część domeny w nazwie UPN w usłudze Azure Active Directory (AD).
- **Adres IP lub nazwa FQDN**: Adres IP lub w pełni kwalifikowana nazwa domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład wprowadź adres `192.168.1.1` lub `vpn.contoso.com`.
- **Nazwa chmury organizacji** (tylko rozwiązanie Zscaler): Wprowadź nazwę chmury, w której aprowizowano Twoją organizację. Tę nazwę możesz znaleźć w adresie URL, którego używasz do logowania się do rozwiązania Zscaler.  
- **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania urządzeń na serwerze sieci VPN. 
  - **Certyfikaty**: W obszarze **Certyfikat uwierzytelniania** wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. Artykuł [Konfigurowanie certyfikatów](../protect/certificates-configure.md) zawiera pewne wskazówki dotyczące profili certyfikatów.
  - **Nazwa użytkownika i hasło**: Użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.  

    > [!NOTE]
    > Jeśli w przypadku sieci VPN Cisco IPsec używana jest metoda uwierzytelniania polegająca na podaniu nazwy użytkownika i hasła, użytkownicy końcowi muszą dostarczyć wspólny klucz tajny za pomocą niestandardowego profilu programu Apple Configurator.

  - **poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Jeśli nie skonfigurowano pochodnego wystawcy poświadczeń, usługa Intune będzie monitował o dodanie jednego z nich. Aby uzyskać więcej informacji, zobacz [używać poświadczeń pochodnych w Microsoft Intune](../protect/derived-credentials.md).

- **Wykluczone adresy URL** (tylko rozwiązanie Zscaler): Po nawiązaniu połączenia z siecią VPN rozwiązania Zscaler wymienione adresy URL są dostępne poza chmurą Zscaler. 

- **Podziel tunelowanie**: Ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

- **Identyfikator sieci VPN** (niestandardowa sieć VPN, Zscaler i Citrix): Identyfikator używanej aplikacji sieci VPN udostępniany przez dostawcę sieci VPN.
  - **Podaj pary klucz/wartość dla atrybutów niestandardowej sieci VPN Twojej organizacji**: Dodaj lub zaimportuj **klucze** i **wartości**, aby dostosować połączenie swojej sieci VPN. Pamiętaj, że te wartości są zwykle dostarczane przez dostawcę sieci VPN.

- **Włączanie kontroli dostępu do sieci (NAC)** (Citrix SSO, F5 Access): Po wybraniu pozycji **Zgadzam się** identyfikator urządzenia będzie uwzględniany w profilu sieci VPN. Ten identyfikator może służyć do uwierzytelniania w sieci VPN w celu zezwolenia na dostęp do sieci lub uniemożliwienia tego dostępu.

  **W przypadku korzystania z programu F5 Access** pamiętaj, aby:

  - Upewnić się, że używasz systemu F5 BIG-IP w wersji 13.1.1.5. System BIG-IP w wersji 14 nie jest obsługiwany.
  - Zintegrować system BIG-IP z usługą Intune, aby móc korzystać z kontroli dostępu do sieci. Zobacz przewodnik firmy F5 [Overview: Configuring APM for device posture checks with endpoint management systems (Konfigurowanie programu APM pod kątem kontroli stanu urządzenia za pomocą systemów zarządzania punktem końcowym — przegląd)](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
  - Włączyć kontrolę dostępu do sieci w profilu sieci VPN.

  **W przypadku korzystania z aplikacji Citrix SSO z aplikacją Gateway** pamiętaj, aby:

  - Upewnić się, że używasz aplikacji Citrix Gateway 12.0.59 lub nowszej.
  - Upewnić się, że użytkownicy zainstalowali na swoich urządzeniach aplikację Citrix SSO 1.1.6 lub nowszą.
  - Zintegrować aplikację Citrix Gateway z usługą Intune, aby móc korzystać z kontroli dostępu do sieci. Zobacz przewodnik po wdrażaniu produktów firmy Citrix [Integrating Microsoft Intune/Enterprise Mobility Suite with NetScaler (LDAP+OTP Scenario) (Integrowanie usługi Microsoft Intune/pakietu Enterprise Mobility Suite z rozwiązaniem NetScaler — scenariusz LDAP+OTP)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf).
  - Włączyć kontrolę dostępu do sieci w profilu sieci VPN.

  **Ważne informacje**:  

  - Po włączeniu kontroli dostępu do sieci połączenie z siecią VPN jest rozłączane co 24 godziny. Połączenie z siecią VPN można od razu nawiązać ponownie.
  - Identyfikator urządzenia jest częścią profilu, ale nie jest widoczny w usłudze Intune. Ten identyfikator nie jest nigdzie zapisywany przez firmę Microsoft ani nie jest przez nią udostępniany.

  Identyfikator urządzenia, który jest obsługiwany przez partnera udostępniającego sieć VPN, jest dostępny dla klienta sieci VPN, takiego jak Citrix SSO. Klient sieci VPN może następnie wysłać zapytanie do usługi Intune w celu potwierdzenia rejestracji urządzenia oraz ustalenia, czy profil sieci VPN jest zgodny.

  - Aby usunąć to ustawienie, ponownie utwórz profil i nie wybieraj pozycji **Zgadzam się**. Następnie ponownie przypisz profil.

## <a name="ikev2-settings"></a>Ustawienia IKEv2

Te ustawienia mają zastosowanie w przypadku wybrania opcji **typ połączenia** > **IKEv2**.

- **Identyfikator zdalny**: wprowadź adres IP sieci, nazwę FQDN, UserFQDN lub ASN1DN serwera IKEv2. Na przykład wprowadź adres `10.0.0.3` lub `vpn.contoso.com`. Zazwyczaj należy wprowadzić tę samą wartość co [**nazwa połączenia**](#base-vpn-settings) (w tym artykule). Jest to jednak zależne od ustawień serwera IKEv2.

- **Typ uwierzytelniania klienta**: Wybierz sposób uwierzytelniania klienta sieci VPN w sieci VPN. Dostępne opcje:
  - **uwierzytelniania użytkownika** (wartość domyślna): poświadczenia użytkownika uwierzytelniają się w sieci VPN.
  - **uwierzytelniania maszynowego**: poświadczenia urządzenia uwierzytelniają się w sieci VPN.

- **Metoda uwierzytelniania**: Wybierz typ poświadczeń klienta do wysłania do serwera. Dostępne opcje:
  - **certyfikatów**: używa istniejącego profilu certyfikatu do uwierzytelniania w sieci VPN. Upewnij się, że ten profil certyfikatu został już przypisany do użytkownika lub urządzenia. W przeciwnym razie połączenie sieci VPN zakończy się niepowodzeniem.
    - **Typ certyfikatu**: Wybierz typ szyfrowania używany przez certyfikat. Upewnij się, że serwer sieci VPN jest skonfigurowany do akceptowania tego typu certyfikatu. Dostępne opcje:
      - **RSA** (wartość domyślna)
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **nazwy użytkownika i hasła** (tylko uwierzytelnianie użytkownika): gdy użytkownicy łączą się z siecią VPN, są monitowani o podanie nazwy użytkownika i hasła.
  - **Wspólny klucz tajny** (tylko uwierzytelnianie maszynowe): umożliwia wprowadzenie wspólnego klucza tajnego do wysłania do serwera sieci VPN.
    - **Wspólny klucz tajny**: wprowadź wspólny klucz tajny, znany również jako klucz wstępny (PSK). Upewnij się, że wartość jest zgodna ze wspólnym kluczem tajnym skonfigurowanym na serwerze sieci VPN.

- **Nazwa pospolita wystawcy certyfikatu serwera**: umożliwia serwerowi sieci VPN uwierzytelnianie na kliencie sieci VPN. Wprowadź nazwę pospolitą wystawcy certyfikatu (CN) certyfikatu serwera sieci VPN, który jest wysyłany do klienta sieci VPN na urządzeniu. Upewnij się, że wartość nazwy POSPOLITej jest zgodna z konfiguracją na serwerze sieci VPN. W przeciwnym razie połączenie sieci VPN zakończy się niepowodzeniem.
- **Nazwa pospolita certyfikatu serwera**: Wprowadź nazwę POSPOLITą certyfikatu. Jeśli pole pozostanie puste, zostanie użyta wartość identyfikatora zdalnego.

- **Częstotliwość wykrywania martwych elementów równorzędnych**: Określ, jak często klient sieci VPN sprawdza, czy tunel VPN jest aktywny. Dostępne opcje:
  - **Nie skonfigurowano**: używa domyślnego systemu iOS, który może być taki sam jak wybór **medium**.
  - **Brak**: wyłącza wykrywanie utraconych elementów równorzędnych.
  - **Niska**: wysyła komunikat o utrzymywaniu aktywności co 30 minut.
  - **Średni** (domyślnie): wysyła komunikat o utrzymywaniu aktywności co 10 minut.
  - **Wysoka**: wysyła komunikat o utrzymywaniu aktywności co 60 sekund.

- **Minimalny**zakresu wersji TLS: wprowadź minimalną wersję protokołu TLS do użycia. Wprowadź `1.0`, `1.1`lub `1.2`. Jeśli pole pozostanie puste, zostanie użyta wartość domyślna `1.0`.
- **Maksymalny zakres wersji protokołu TLS**: wprowadź maksymalną wersję protokołu TLS do użycia. Wprowadź `1.0`, `1.1`lub `1.2`. Jeśli pole pozostanie puste, zostanie użyta wartość domyślna `1.2`.

> [!NOTE]
> W przypadku korzystania z uwierzytelniania i certyfikatów użytkowników musi być ustawiony minimalny i maksymalny zakres wersji protokołu TLS.

- **Doskonałe utajnienie przekazywania dalej**: wybierz pozycję **Włącz**, aby włączyć doskonałe utajnienie przekazywania (PFS). Doskonałe utajnienie przekazywania to funkcja zabezpieczeń IP, która zmniejsza wpływ na złamanie klucza sesji. **Wartość Wyłącz** (domyślnie) nie używa PFS.
- **Sprawdzanie odwołania certyfikatu**: wybierz pozycję **Włącz**, aby upewnić się, że certyfikaty nie zostaną odwołane przed pomyślnym nawiązaniem połączenia z siecią VPN. To sprawdzenie jest najlepszym nakładem pracy. Jeśli serwer sieci VPN przeprowadził limit czasu przed ustaleniem, czy certyfikat został odwołany, dostęp jest udzielany. **Wartość Wyłącz** (domyślnie) nie sprawdza odwołanych certyfikatów.

- **Konfigurowanie parametrów skojarzenia zabezpieczeń**: nie **skonfigurowany** (domyślnie) używa domyślnego systemu iOS. Wybierz pozycję **Włącz**, aby wprowadzić parametry używane podczas tworzenia skojarzeń zabezpieczeń z serwerem sieci VPN:
  - **Algorytm szyfrowania**: wybierz odpowiedni algorytm:
    - DES
    - 3DES
    - AES-128
    - AES-256 (wartość domyślna)
    - AES-128-GCM
    - AES-256-GCM
  - **Algorytm integralności**: wybierz odpowiedni algorytm:
    - SHA1-96
    - SHA1-160
    - ALGORYTMU SHA2-256 (wartość domyślna)
    - SHA2-384
    - SHA2-512
  - **Grupa Diffie-Hellmana**: wybierz żądaną grupę. Wartość domyślna to grupa `2`.
  - **okresu istnienia** (minuty): Określ, jak długo skojarzenie zabezpieczeń ma być aktywne, dopóki klucze nie zostaną obrócone. Wprowadź wartość całkowitą między `10` i `1440` (1440 minut wynosi 24 godziny). Wartość domyślna to `1440`.

- **Skonfiguruj oddzielny zestaw parametrów dla podrzędnych skojarzeń zabezpieczeń**: system iOS umożliwia skonfigurowanie oddzielnych parametrów dla połączenia IKE i wszystkich połączeń podrzędnych. 

  **Nie skonfigurowano** (wartość domyślna) używa wartości wprowadzonych w poprzedniej **ustawienia** ustawień skojarzeń zabezpieczeń. Wybierz pozycję **Włącz**, aby wprowadzić parametry używane podczas tworzenia *podrzędnych* skojarzenia zabezpieczeń z serwerem sieci VPN:
  - **Algorytm szyfrowania**: wybierz odpowiedni algorytm:
    - DES
    - 3DES
    - AES-128
    - AES-256 (wartość domyślna)
    - AES-128-GCM
    - AES-256-GCM
  - **Algorytm integralności**: wybierz odpowiedni algorytm:
    - SHA1-96
    - SHA1-160
    - ALGORYTMU SHA2-256 (wartość domyślna)
    - SHA2-384
    - SHA2-512
  - **Grupa Diffie-Hellmana**: wybierz żądaną grupę. Wartość domyślna to grupa `2`.
  - **okresu istnienia** (minuty): Określ, jak długo skojarzenie zabezpieczeń ma być aktywne, dopóki klucze nie zostaną obrócone. Wprowadź wartość całkowitą między `10` i `1440` (1440 minut wynosi 24 godziny). Wartość domyślna to `1440`.

## <a name="automatic-vpn-settings"></a>Ustawienia automatycznego połączenia VPN

- **Sieć VPN dla aplikacji**: Włącza sieć VPN dla aplikacji. Umożliwia automatyczne wyzwalanie połączenia sieci VPN po otworzeniu konkretnych aplikacji. Ponadto skojarz aplikacje z tym profilem sieci VPN. Sieć VPN dla aplikacji nie jest obsługiwana w przypadku protokołu IKEv2. Aby uzyskać więcej informacji, zapoznaj się z [instrukcjami dotyczącymi konfigurowania sieci VPN dla aplikacji w systemie iOS](vpn-setting-configure-per-app.md). 
  - **Typ dostawcy**: Dostępne tylko dla połączenia Pulse Secure i niestandardowej sieci VPN.
  - Podczas korzystania z profilów **Sieć VPN dla aplikacji** w systemie iOS przy użyciu typu połączenia Pulse Secure lub niestandardowej sieci VPN wybierz tunelowanie w warstwie aplikacji (app-proxy) lub tunelowanie w warstwie pakietów (packet-tunnel). Ustaw opcję **Typ dostawcy** na wartość **app-proxy** w celu tunelowania w warstwie aplikacji lub **packet-tunnel** w celu tunelowania w warstwie pakietów. Jeśli nie masz pewności, której wartości użyć, zapoznaj się z dokumentacją dostawcy sieci VPN.
  - **Adresy URL przeglądarki Safari, które powodują wyzwolenie tej sieci VPN**: Dodaj jeden lub wiele adresów URL witryn internetowych. Gdy te adresy URL zostaną otwarte za pomocą przeglądarki Safari na urządzeniu, połączenie sieci VPN zostanie nawiązane automatycznie.

- **Sieć VPN na żądanie**: Skonfiguruj reguły warunkowe, które kontrolują moment rozpoczęcia połączenia sieci VPN. Na przykład utwórz warunek określający, że połączenie sieci VPN jest używane tylko w sytuacji, gdy urządzenie nie jest połączone z siecią Wi-Fi firmy. Można też utworzyć warunek — połączenie sieci VPN nie jest inicjowane, jeśli urządzenie nie może uzyskać dostępu do wprowadzonej domeny wyszukiwania DNS.

  - **Identyfikatory SSID lub domeny wyszukiwania DNS**: Wybierz, czy ten warunek będzie używać **identyfikatorów SSID** sieci bezprzewodowej, czy **domen wyszukiwania DNS**. Kliknij przycisk **Dodaj**, aby skonfigurować co najmniej jeden identyfikator SSID lub domenę wyszukiwania.
  - **Sonda ciągu adresu URL**: Opcjonalny. Podaj adres URL, którego reguła używa jako adresu testowego. Jeśli urządzenie uzyska dostęp do tego adresu URL bez przekierowania, połączenie sieci VPN zostanie zainicjowane. Następnie urządzenie połączy się z docelowym adresem URL. Użytkownik nie widzi witryny sondy ciągu adresu URL.

    Na przykład sonda ciągu adresu URL to adres inspekcji serwera internetowego, który umożliwia sprawdzenie zgodności urządzeń przed nawiązaniem połączenia z siecią VPN. Inną możliwością jest testowanie przez adres URL możliwości łączenia się sieci VPN z witryną, zanim urządzenie połączy się z docelowym adresem URL za pośrednictwem sieci VPN.
.
  - **Akcja domeny**: Wybierz jedną z następujących pozycji:
    - Połącz w razie potrzeby
    - Nigdy nie łącz
  - **Akcja**: Wybierz jedną z następujących pozycji:
    - Connect
    - Oceń połączenie
    - Ignoruj
    - Rozłącz

## <a name="proxy-settings"></a>Ustawienia serwera proxy

Jeśli używasz serwera proxy, skonfiguruj następujące ustawienia. Ustawienia serwera proxy nie są dostępne dla połączeń sieci VPN rozwiązania Zscaler.  

- **Skrypt konfiguracji automatycznej**: Użyj pliku do skonfigurowania serwera proxy. Wprowadź **Adres URL serwera proxy** (np. `http://proxy.contoso.com`), który uwzględnia plik konfiguracji.
- **Adres**: Podaj adres IP dla w pełni kwalifikowanej nazwy hosta serwera proxy.
- **Numer portu**: Wprowadź numer portu skojarzony z serwerem proxy.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Skonfiguruj ustawienia sieci VPN na [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md)i [urządzeń z systemem Windows 10](vpn-settings-windows-10.md).
