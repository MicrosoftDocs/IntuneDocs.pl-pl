---
title: Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: 'Istnieje możliwość wyświetlenia następujących informacji usługi Microsoft Intune dotyczących urządzeń z systemem iOS: ustawienia konfiguracji wirtualnej sieci prywatnej (VPN) ze szczegółami połączenia, metody uwierzytelniania, dzielenie tuneli w ustawieniach podstawowych, niestandardowe ustawienia sieci VPN z identyfikatorem i parami klucz-wartość, ustawienia sieci VPN dla aplikacji obejmujące adresy URL przeglądarki Safari, sieci VPN na żądanie z identyfikatorami SSID lub domenami wyszukiwania DNS, ustawienia serwera proxy obejmujące skrypt konfiguracji, adres IP lub FQDN i port TCP.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: deb6a230573ff20237e6eee386052baba472832a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313874"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, za pomocą których można skonfigurować połączenia sieci VPN na urządzeniach z systemem iOS.

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN
Rzeczywiste ustawienia, które widzisz na poniższej liście, są określane przez typ połączenia sieci VPN, który wybierzesz.  
- **Nazwa połączenia**: użytkownicy końcowi widzą tę nazwę podczas przeglądania na urządzeniu listy dostępnych połączeń sieci VPN.
- **Niestandardowa nazwa domeny** (tylko rozwiązania Zscaler): wstępnie wypełnij pole logowania aplikacji rozwiązania Zscaler nazwą domeny, do której należą Twoi użytkownicy. Na przykład jeśli nazwa użytkownika to **Joe@contoso.net**, domena **contoso.net** statycznie pojawi się w polu po otwarciu aplikacji. Jeśli nie wpiszesz nazwy domeny, zostanie użyta część domeny w nazwie UPN w usłudze Azure Active Directory.
- **Adres IP lub nazwa FQDN**: adres IP lub w pełni kwalifikowana nazwa domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**. 
- **Nazwa organizacji w chmurze** (tylko rozwiązania Zscaler): wpisz nazwę chmury, gdzie Twoja organizacja jest aprowizowana. Szukaj w adresie URL, którego używasz do logowania się do rozwiązania Zscaler, aby znaleźć nazwę.  
- **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. 
  - **Certyfikaty**: w obszarze **Certyfikat uwierzytelniania** wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. Artykuł [Konfigurowanie certyfikatów](certificates-configure.md) zawiera pewne wskazówki dotyczące profili certyfikatów.
  - **Nazwa użytkownika i hasło**: użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.  

    > [!NOTE]
    > Jeśli w przypadku sieci VPN Cisco IPsec używana jest metoda uwierzytelniania polegająca na podaniu nazwy użytkownika i hasła, użytkownicy końcowi muszą dostarczyć wspólny klucz tajny za pomocą niestandardowego profilu programu Apple Configurator.
  
- **Typ połączenia**: umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
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
  - **Zscaler**: wymaga integracji rozwiązania Zscaler Private Access (ZPA) z kontem usługi Azure Active Directory. Aby uzyskać szczegółowe instrukcje, zobacz [dokumentację rozwiązania Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
  - **Niestandardowa sieć VPN**    

    > [!NOTE]
    > Firmy Cisco, Citrix, F5 i Palo Alto ogłosiły, że ich starsi klienci nie będą działać w nadchodzącej wersji systemu iOS 12. Należy przeprowadzić migrację do nowych aplikacji tak szybko, jak to możliwe. Aby uzyskać więcej informacji, zobacz [blog zespołu pomocy technicznej usługi Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

* **Wykluczone adresy URL** (tylko rozwiązania Zscaler): po nawiązaniu połączenia z siecią VPN rozwiązania Zscaler wymienione adresy URL są dostępne poza chmurą Zscaler. 

- **Podziel tunelowanie**: ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.   

## <a name="custom-vpn-settings"></a>Niestandardowe ustawienia sieci VPN

W przypadku wybrania pozycji **Niestandardowa sieć VPN** jako typu połączenia skonfiguruj także następujące ustawienia. Te ustawienia są również widoczne dla połączeń rozwiązania Zscaler i Citrix.

- **Identyfikator sieci VPN**: to jest identyfikator używanej aplikacji sieci VPN udostępniony przez dostawcę sieci VPN.
- **Podaj pary klucz/wartość dla atrybutów niestandardowej sieci VPN Twojej organizacji**: dodaj lub zaimportuj **klucze** i **wartości**, aby dostosować połączenie swojej sieci VPN. Te wartości również są zwykle dostarczane przez dostawcę sieci VPN.

## <a name="automatic-vpn-settings"></a>Ustawienia automatycznego połączenia VPN

- **Sieć VPN dla aplikacji**: wybranie tej opcji umożliwia używanie sieci VPN dla aplikacji, co pozwala automatycznie wyzwolić połączenie sieci VPN w przypadku otwarcia określonych aplikacji. Oprócz wybrania tej opcji należy skojarzyć aplikacje z tym profilem sieci VPN. Aby uzyskać więcej informacji, zapoznaj się z [instrukcjami dotyczącymi konfigurowania sieci VPN dla systemu iOS](vpn-setting-configure-per-app.md). 
  - Ustawienie **Typ dostawcy** jest dostępne tylko dla połączenia Pulse Secure i niestandardowej sieci VPN.
  - Podczas korzystania z profilów **sieci VPN dla aplikacji** w systemie iOS przy użyciu typu połączenia Pulse Secure lub niestandardowej sieci VPN możesz użyć tunelowania w warstwie aplikacji (app-proxy) lub tunelowania w warstwie pakietów (packet-tunnel). Ustaw wartość **ProviderType** na **app-proxy** dla tunelowania w warstwie aplikacji lub na **packet-tunnel** dla tunelowania w warstwie pakietu. Jeśli nie masz pewności, której wartości użyć, zapoznaj się z dokumentacją dostawcy sieci VPN. 
  - **Adresy URL przeglądarki Safari wyzwalające tę sieć VPN**: wybierz, aby dodać jeden lub wiele adresów URL witryn internetowych. Gdy te adresy URL zostaną otwarte za pomocą przeglądarki Safari na urządzeniu, połączenie sieci VPN zostanie nawiązane automatycznie.

- **Sieć VPN na żądanie**: skonfiguruj reguły warunkowe, które kontrolują moment inicjowania połączenia sieci VPN. Na przykład możesz utworzyć warunek określający, że połączenie sieci VPN jest używane tylko w sytuacji, gdy urządzenie nie jest połączone z siecią Wi-Fi firmy. Inna możliwość to utworzenie warunku, zgodnie z którym połączenie sieci VPN nie będzie inicjowane, jeśli urządzenie nie może uzyskać dostępu do określonej domeny wyszukiwania DNS.

  - **Identyfikatory SSID lub domeny wyszukiwania DNS**: wybierz, czy ten warunek będzie używać **identyfikatorów SSID** sieci bezprzewodowej, czy **domen wyszukiwania DNS**. Kliknij przycisk **Dodaj**, aby skonfigurować co najmniej jeden identyfikator SSID lub domenę wyszukiwania.
  - **Sonda ciągu adresu URL**: opcjonalne. Podaj adres URL, którego reguła używa jako adresu testowego. Jeśli urządzenie, na którym ten profil jest zainstalowany, może uzyskać dostęp do tego adresu URL bez przekierowania, połączenie VPN jest nawiązywane i urządzenie łączy się z docelowym adresem URL. Użytkownik nie widzi witryny sondy ciągu adresu URL. Przykładem sondy ciągu adresu URL jest adres inspekcji serwera internetowego, który umożliwia sprawdzenie zgodności urządzeń przed nawiązaniem połączenia z siecią VPN. Inną możliwością jest testowanie przez adres URL możliwości łączenia się sieci VPN z witryną, zanim urządzenie połączy się z docelowym adresem URL za pośrednictwem sieci VPN.
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

- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Podaj **adres URL serwera proxy**, np. **http://proxy.contoso.com**, który zawiera plik konfiguracji.
- **Adres**: podaj adres IP dla w pełni kwalifikowanej nazwy hosta serwera proxy.
- **Numer portu**: podaj numer portu skojarzony z serwerem proxy.

## <a name="next-step"></a>Następny krok
[Tworzenie profilów sieci VPN w usłudze Intune](vpn-settings-configure.md)  
