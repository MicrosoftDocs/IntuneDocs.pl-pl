---
title: Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: 'Istnieje możliwość wyświetlenia następujących informacji usługi Intune dotyczących urządzeń z systemem iOS: ustawienia konfiguracji wirtualnej sieci prywatnej (VPN) ze szczegółami połączenia, metody uwierzytelniania, dzielenie tuneli w ustawieniach podstawowych, niestandardowe ustawienia sieci VPN z identyfikatorem i parami klucz-wartość, ustawienia sieci VPN dla aplikacji obejmujące adresy URL przeglądarki Safari, sieci VPN na żądanie z identyfikatorami SSID lub domenami wyszukiwania DNS, ustawienia serwera proxy obejmujące skrypt konfiguracji, adres IP lub FQDN i port TCP.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ce970f942d8ea20eb9ea593c23160757122926e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, za pomocą których można skonfigurować połączenia sieci VPN na urządzeniach z systemem iOS.

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę podczas przeglądania na urządzeniu listy dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN** — podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.
- **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
  - **Certyfikaty**: w obszarze **Certyfikat uwierzytelniania** wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. Artykuł [Configure certificates (Konfigurowanie certyfikatów)](certificates-configure.md) zawiera pewne wskazówki dotyczące profili certyfikatów.
  - **Nazwa użytkownika i hasło**: użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Typ połączenia**: umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix**
  - **Niestandardowa sieć VPN**

- **Podziel tunelowanie**: ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

## <a name="custom-vpn-settings"></a>Niestandardowe ustawienia sieci VPN

W przypadku wybrania opcji **Niestandardowa sieć VPN** jako typ połączenia skonfiguruj także następujące ustawienia:

- **Identyfikator sieci VPN**: to jest identyfikator używanej aplikacji sieci VPN udostępniony przez dostawcę sieci VPN.
- **Podaj pary klucza i wartości dla atrybutów niestandardowej sieci VPN**: dodaj lub zaimportuj **klucze** i **wartości**, aby dostosować połączenie sieci VPN. Te wartości również są zwykle dostarczane przez dostawcę sieci VPN.

## <a name="apps-per-app-vpn-settings"></a>Ustawienia aplikacji (sieć VPN dla aplikacji)

- **Sieć VPN dla aplikacji**: włącz tę opcję, jeśli chcesz użyć adresów URL umożliwiających nawiązanie połączenia sieci VPN podczas korzystania z przeglądarki Safari. Aby skonfigurować sieć VPN dla aplikacji, musisz wybrać metodę uwierzytelniania **Certyfikaty** w ustawieniach podstawowych sieci VPN.
  - **Adresy URL przeglądarki Safari wyzwalające tę sieć VPN**: wybierz, aby dodać jeden lub wiele adresów URL witryn internetowych. Odwiedzenie tych adresów URL powoduje nawiązanie połączenia VPN.

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

- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Podaj **adres URL serwera proxy**, np. **http://proxy.contoso.com**, który zawiera plik konfiguracji.
- **Adres**: podaj adres IP dla w pełni kwalifikowanej nazwy hosta serwera proxy.
- **Numer portu**: podaj numer portu skojarzony z serwerem proxy.
