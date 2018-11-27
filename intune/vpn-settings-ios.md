---
title: Dodawanie ustawień sieci VPN do urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune na urządzeniach z systemem iOS dodaj lub utwórz profil konfiguracji sieci VPN, korzystając z ustawień konfiguracji wirtualnej sieci prywatnej (VPN, virtual private network), w tym szczegółów połączenia, metod uwierzytelniania i dzielenia tuneli w ustawieniach podstawowych; niestandardowych ustawień sieci VPN z identyfikatorem i parami klucz-wartość; ustawień sieci VPN dla poszczególnych aplikacji, obejmujących adresy URL przeglądarki Safari oraz sieci VPN na żądanie z identyfikatorami SSID lub domenami wyszukiwania DNS; a także ustawień serwera proxy, obejmujących skrypt konfiguracji, adres IP lub nazwę FQDN i port TCP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ea127fb72a2e24343185d06e26d883e1183e7c2b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185563"
---
# <a name="configure-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune

Usługa Microsoft Intune obejmuje wiele ustawień sieci VPN, które mogą być wdrażane na urządzeniach z systemem iOS. Te ustawienia są używane do tworzenia i konfigurowania połączeń sieci VPN z siecią Twojej organizacji. W tym artykule opisano te ustawienia. Niektóre ustawienia są dostępne tylko dla niektórych klientów sieci VPN, takich jak Citrix, Zscaler itp.

## <a name="connection-type"></a>Typ połączenia

Umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: dotyczy aplikacji [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) w wersji 4.0.5x i starszej.
- **Cisco AnyConnect**: dotyczy aplikacji [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) w wersji 4.0.7x i nowszej.
- **SonicWall Mobile Connect**
- **F5 Access Legacy**: dotyczy aplikacji F5 Access w wersji 2.1 i starszej.
- **F5 Access**: dotyczy aplikacji F5 Access w wersji 3.0 i nowszej.
- **Palo Alto Networks GlobalProtect (starsza wersja)**: dotyczy aplikacji Palo Alto Networks GlobalProtect w wersji 4.1 i starszej.
- **Palo Alto Networks GlobalProtect**: dotyczy aplikacji Palo Alto Networks GlobalProtect w wersji 5.0 i nowszej.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Sieć VPN Citrix**
- **Citrix SSO**
- **Zscaler**: wymaga integracji rozwiązania Zscaler Private Access (ZPA) z kontem usługi Azure AD. Aby uzyskać szczegółowe instrukcje, zobacz [dokumentację rozwiązania Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
- **Niestandardowa sieć VPN**

> [!NOTE]
> Firmy Cisco, Citrix, F5 i Palo Alto ogłosiły, że ich starsi klienci nie działają w systemie iOS 12. Należy przeprowadzić migrację do nowych aplikacji tak szybko, jak to możliwe. Aby uzyskać więcej informacji, zobacz [blog zespołu pomocy technicznej usługi Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

Ustawienia wymienione na poniższej liście są określane przez wybrany typ połączenia VPN.  

- **Nazwa połączenia**: użytkownicy końcowi widzą tę nazwę podczas przeglądania na urządzeniu listy dostępnych połączeń sieci VPN.
- **Niestandardowa nazwa domeny** (tylko rozwiązania Zscaler): wstępnie wypełnij pole logowania aplikacji rozwiązania Zscaler nazwą domeny, do której należą Twoi użytkownicy. Jeśli na przykład nazwa użytkownika to `Joe@contoso.net`, domena `contoso.net` statycznie pojawi się w polu po otwarciu aplikacji. Jeśli nie wprowadzisz nazwy domeny, zostanie użyta część domeny w nazwie UPN w usłudze Azure Active Directory (AD).
- **Adres IP lub nazwa FQDN**: adres IP lub w pełni kwalifikowana nazwa domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład wprowadź adres `192.168.1.1` lub `vpn.contoso.com`.
- **Nazwa chmury organizacji** (tylko rozwiązanie Zscaler): wprowadź nazwę chmury, w której aprowizowano Twoją organizację. Tę nazwę możesz znaleźć w adresie URL, którego używasz do logowania się do rozwiązania Zscaler.  
- **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. 
  - **Certyfikaty**: w obszarze **Certyfikat uwierzytelniania** wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. Artykuł [Konfigurowanie certyfikatów](certificates-configure.md) zawiera pewne wskazówki dotyczące profili certyfikatów.
  - **Nazwa użytkownika i hasło**: użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.  

    > [!NOTE]
    > Jeśli w przypadku sieci VPN Cisco IPsec używana jest metoda uwierzytelniania polegająca na podaniu nazwy użytkownika i hasła, użytkownicy końcowi muszą dostarczyć wspólny klucz tajny za pomocą niestandardowego profilu programu Apple Configurator.

- **Wykluczone adresy URL** (tylko rozwiązania Zscaler): po nawiązaniu połączenia z siecią VPN rozwiązania Zscaler wymienione adresy URL są dostępne poza chmurą Zscaler. 

- **Podziel tunelowanie**: ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

- **Identyfikator sieci VPN** (niestandardowa sieć VPN, Zscaler i Citrix): identyfikator używanej aplikacji sieci VPN udostępniany przez dostawcę sieci VPN.
  - **Podaj pary klucz/wartość dla atrybutów niestandardowej sieci VPN Twojej organizacji**: dodaj lub zaimportuj **klucze** i **wartości**, aby dostosować połączenie swojej sieci VPN. Pamiętaj, że te wartości są zwykle dostarczane przez dostawcę sieci VPN.

- **Włączanie kontroli dostępu do sieci (NAC)** (tylko aplikacja Citrix SSO): po wybraniu pozycji **Zgadzam się** identyfikator urządzenia będzie uwzględniany w profilu sieci VPN. Ten identyfikator może służyć do uwierzytelniania w sieci VPN w celu zezwolenia na dostęp do sieci lub uniemożliwienia tego dostępu.

  **W przypadku korzystania z aplikacji Citrix SSO z aplikacją Gateway** pamiętaj, aby:

  - Upewnić się, że używasz aplikacji Citrix Gateway 12.0.59 lub nowszej.
  - Upewnić się, że użytkownicy zainstalowali na swoich urządzeniach aplikację Citrix SSO 1.1.6 lub nowszą.
  - Zintegrować aplikację Citrix Gateway z usługą Intune na potrzeby kontroli dostępu do sieci zgodnie z opisem w przewodniku wdrażania [Integrating Microsoft Intune/Enterprise Mobility Suite with NetScaler (LDAP+OTP Scenario)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf) (Integrowanie usługi Microsoft Intune/pakietu Enterprise Mobility Suite z rozwiązaniem NetScaler (scenariusz LDAP+OTP)) firmy Citrix.
  - Włączyć kontrolę dostępu do sieci w profilu sieci VPN.

  Ważne informacje:  

  - Po włączeniu kontroli dostępu do sieci połączenie z siecią VPN jest rozłączane co 24 godziny.
  - Identyfikator urządzenia jest częścią profilu, ale nie jest widoczny w usłudze Intune. Ten identyfikator nie jest nigdzie zapisywany przez firmę Microsoft ani nie jest przez nią udostępniany. Po dodaniu obsługi przez partnerów sieci VPN klient sieci VPN, taki jak Citrix SSO, będzie mógł pobrać identyfikator i wysłać zapytanie do usługi Intune, aby potwierdzić, że urządzenie jest zarejestrowane, oraz określić, czy profil sieci VPN jest zgodny.
  - Aby usunąć to ustawienie, ponownie utwórz profil i nie wybieraj pozycji **Zgadzam się**. Następnie ponownie przypisz profil.

## <a name="automatic-vpn-settings"></a>Ustawienia automatycznego połączenia VPN

- **Sieć VPN dla aplikacji**: włącza sieć VPN dla aplikacji. Umożliwia automatyczne wyzwalanie połączenia sieci VPN po otworzeniu konkretnych aplikacji. Ponadto skojarz aplikacje z tym profilem sieci VPN. Aby uzyskać więcej informacji, zapoznaj się z [instrukcjami dotyczącymi konfigurowania sieci VPN dla aplikacji w systemie iOS](vpn-setting-configure-per-app.md).
  - **Typ dostawcy**: dostępne tylko dla połączenia Pulse Secure i niestandardowej sieci VPN.
  - Podczas korzystania z profilów **Sieć VPN dla aplikacji** w systemie iOS przy użyciu typu połączenia Pulse Secure lub niestandardowej sieci VPN wybierz tunelowanie w warstwie aplikacji (app-proxy) lub tunelowanie w warstwie pakietów (packet-tunnel). Ustaw opcję **Typ dostawcy** na wartość **app-proxy** w celu tunelowania w warstwie aplikacji lub **packet-tunnel** w celu tunelowania w warstwie pakietów. Jeśli nie masz pewności, której wartości użyć, zapoznaj się z dokumentacją dostawcy sieci VPN.
  - **Adresy URL przeglądarki Safari wyzwalające tę sieć VPN**: dodaj jeden lub wiele adresów URL witryn internetowych. Gdy te adresy URL zostaną otwarte za pomocą przeglądarki Safari na urządzeniu, połączenie sieci VPN zostanie nawiązane automatycznie.

- **Sieć VPN na żądanie**: skonfiguruj reguły warunkowe, które kontrolują moment rozpoczęcia połączenia sieci VPN. Na przykład utwórz warunek określający, że połączenie sieci VPN jest używane tylko w sytuacji, gdy urządzenie nie jest połączone z siecią Wi-Fi firmy. Inna możliwość to utworzenie warunku, zgodnie z którym połączenie sieci VPN nie będzie inicjowane, jeśli urządzenie nie może uzyskać dostępu do wprowadzonej domeny wyszukiwania DNS.

  - **Identyfikatory SSID lub domeny wyszukiwania DNS**: wybierz, czy ten warunek będzie używać **identyfikatorów SSID** sieci bezprzewodowej, czy **domen wyszukiwania DNS**. Kliknij przycisk **Dodaj**, aby skonfigurować co najmniej jeden identyfikator SSID lub domenę wyszukiwania.
  - **Sonda ciągu adresu URL**: opcjonalne. Podaj adres URL, którego reguła używa jako adresu testowego. Jeśli urządzenie z tym profilem uzyska dostęp do tego adresu URL bez przekierowania, połączenie sieci VPN zostanie zainicjowane. Następnie urządzenie połączy się z docelowym adresem URL. Użytkownik nie widzi witryny sondy ciągu adresu URL. Przykładem sondy ciągu adresu URL jest adres inspekcji serwera internetowego, który umożliwia sprawdzenie zgodności urządzeń przed nawiązaniem połączenia z siecią VPN. Inną możliwością jest testowanie przez adres URL możliwości łączenia się sieci VPN z witryną, zanim urządzenie połączy się z docelowym adresem URL za pośrednictwem sieci VPN.
  - **Akcja domeny**: wybierz jedną z następujących pozycji:
    - Połącz w razie potrzeby
    - Nigdy nie łącz
  - **Akcja**: wybierz jedną z następujących pozycji:
    - Connect
    - Oceń połączenie
    - Ignoruj
    - Rozłącz

## <a name="proxy-settings"></a>Ustawienia serwera proxy

Jeśli używasz serwera proxy, skonfiguruj następujące ustawienia. Ustawienia serwera proxy nie są dostępne dla połączeń sieci VPN rozwiązania Zscaler.  

- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Wprowadź **Adres URL serwera proxy** (np. `http://proxy.contoso.com`), który uwzględnia plik konfiguracji.
- **Adres**: podaj adres IP dla w pełni kwalifikowanej nazwy hosta serwera proxy.
- **Numer portu**: podaj numer portu skojarzony z serwerem proxy.

## <a name="next-step"></a>Następny krok
[Tworzenie profilów sieci VPN w usłudze Intune](vpn-settings-configure.md)  
