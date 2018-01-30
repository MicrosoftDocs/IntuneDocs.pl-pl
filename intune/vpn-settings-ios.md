---
title: "Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń VPN na urządzeniach z systemem iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3db57b851c405758c9cccdc3e70c96ca9e76000
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a>Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN


**Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia się łączą. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda uwierzytelniania** — umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
    - **Certyfikaty** — w obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej informacji o profilach certyfikatów, zobacz temat dotyczący [konfigurowania certyfikatów](certificates-configure.md).
    - **Nazwa użytkownika i hasło** — użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPSec)**
    - **Citrix**
    - **Niestandardowa sieć VPN**
- **Podziel tunelowanie** - wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.


## <a name="custom-vpn-settings"></a>Niestandardowe ustawienia sieci VPN

W przypadku wybrania opcji **Niestandardowa sieć VPN** jako typ połączenia skonfiguruj następujące ustawienia dodatkowe:

- **Identyfikator sieci VPN** To jest identyfikator używanej aplikacji sieci VPN dostarczony przez dostawcę sieci VPN.
- **Podaj pary klucza i wartości dla atrybutów niestandardowej sieci VPN** Dodaj lub importuj **Klucze** i **Wartości**, aby dostosować połączenie VPN. Te wartości również są zwykle dostarczane przez dostawcę sieci VPN.

## <a name="apps-per-app-vpn-settings"></a>Ustawienia aplikacji (sieć VPN dla aplikacji)

- **Sieć VPN dla aplikacji** — włącz tę opcję, jeśli chcesz, aby odwiedzenie określonych adresów URL podczas korzystania z przeglądarki Safari powodowało nawiązanie połączenia VPN. Aby można było skonfigurować tę opcję, należy wybrać pozycję **Certyfikaty** jako metodę uwierzytelniania w podstawowych ustawieniach sieci VPN.
- **Określ adresy URL, które powodują nawiązanie połączenia VPN podczas korzystania z przeglądarki Safari** — kliknij przycisk Dodaj, aby dodać jeden lub więcej adresów URL witryn internetowych. Odwiedzenie tych adresów URL powoduje nawiązanie połączenia VPN.

- **Reguły na żądanie** — to ustawienie umożliwia skonfigurowanie reguł warunkowych, które są stosowane po zainicjowaniu połączenia VPN. Na przykład można utworzyć warunek określający, że połączenie sieci VPN jest używane tylko w sytuacji, gdy urządzenie nie jest połączone z jedną z sieci Wi-Fi firmy. Można również utworzyć warunek, zgodnie z którym połączenie VPN nie będzie inicjowane, jeśli urządzenie nie może uzyskać dostępu do określonej domeny wyszukiwania DNS.

    - **Identyfikatory SSID lub domeny wyszukiwania DNS** — wybierz, czy ten warunek będzie używać **identyfikatorów SSID** sieci bezprzewodowej, czy **domen wyszukiwania DNS**. Kliknij przycisk Dodaj, aby skonfigurować jeden lub większą liczbę identyfikatorów SSID lub domen wyszukiwania.
    - **Sonda ciągu adresu URL** — opcjonalnie można podać adres URL używany przez regułę do celów testowych. Jeśli urządzenie, na którym ten profil jest zainstalowany, może uzyskać dostęp do tego adresu URL bez przekierowania, połączenie VPN jest nawiązywane i urządzenie łączy się z docelowym adresem URL. Użytkownik nie będzie widział witryny sondy ciągu adresu URL. Przykładem sondy ciągu adresu URL jest adres inspekcji serwera sieci Web, która sprawdza zgodność urządzeń przed nawiązaniem połączenia z siecią VPN. Inną możliwością jest testowanie przez adres URL możliwości łączenia się sieci VPN z witryną, zanim urządzenie połączy się z docelowym adresem URL za pośrednictwem sieci VPN.
    - **Akcja domeny** — wybierz jedną z następujących pozycji:
        - Połącz w razie potrzeby — 
        - Nigdy nie łącz — 
    - **Akcja** — wybierz jedną z następujących pozycji:
        - Połącz — 
        - Oceń połączenie — 
        - Ignoruj — 
        - Rozłącz — 


## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Skrypt konfiguracji automatycznej** — umożliwia skonfigurowanie serwera proxy przy użyciu pliku. W polu **Adres URL serwera proxy** wprowadź adres URL (na przykład **http://proxy.contoso.com**), który zawiera plik konfiguracji.
- **Adres** — wprowadź adres serwera proxy (jako adres IP).
- **Numer portu** — wprowadź numer portu skojarzony z serwerem proxy.