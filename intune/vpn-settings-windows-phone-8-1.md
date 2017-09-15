---
title: "Ustawienia sieci VPN dla urządzeń z systemem Windows Phone 8.1 w usłudze Intune"
titleSuffix: Azure portal
description: "Dowiedz się więcej o ustawieniach usługi Intune służących do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows Phone 8.1."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: debfe6cde108daf88db8d18db1e7da2186fc32ea
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Ustawienia sieci VPN dla urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
- **Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy zobaczą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Metoda uwierzytelniania** — umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
    - **Certyfikaty** — w obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej szczegółowych informacji o profilach certyfikatów, zobacz artykuł [Konfigurowanie certyfikatów](certificates-configure.md).
    - **Nazwa użytkownika i hasło** — użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Serwery** — umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia będą się łączyć.
    - **Dodaj** — otwiera blok **Dodaj wiersz**, w którym można określić następujące informacje:
        - **Opis** — umożliwia określenie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**.
        - **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia będą się łączyć. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
        - **Serwer domyślny** — określa ten serwer jako serwer domyślny używany przez urządzenia do ustanowienia połączenia. Upewnij się, że tylko jeden serwer jest ustawiony jako domyślny.
    - **Importuj** — umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te dane do listy **Serwery**.
    - **Eksportuj** — umożliwia wyeksportowanie listy serwerów do pliku CSV (plik wartości rozdzielany przecinkami).

- **Pomijaj sieć VPN w firmowej sieci Wi-Fi** — włącz tę opcję, aby określić, że połączenie z siecią VPN nie będzie używane, gdy urządzenie jest połączone z firmową siecią Wi-Fi.
- **Pomijaj sieć VPN w domowej sieci Wi-Fi** — włącz tę opcję, aby określić, że połączenie z siecią VPN nie będzie używane, gdy urządzenie jest połączone z domową siecią Wi-Fi.

- **Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
    - **Check Point Capsule VPN**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Grupa lub domena logowania** (tylko dla Dell SonicWALL Mobile Connect) — umożliwia określenie nazwy grupy lub domeny logowania, z którą chcesz nawiązać połączenie.
- **Rola** (tylko dla Pulse Secure) — umożliwia określenie nazwy roli użytkownika, która ma dostęp do tego połączenia. Rola użytkownika definiuje ustawienia osobiste i opcje oraz włączenie lub wyłączenie określonych funkcji dostępu.
- **Obszar** (tylko dla Pulse Secure) — umożliwia określenie nazwy obszaru uwierzytelniania, który ma być używany. Obszar uwierzytelniania to grupa zasobów uwierzytelniania używana przez typ połączenia Pulse Secure.

- **Lista przeszukiwania sufiksów DNS** - korzystając z opcji **Dodaj**, możesz dodać jeden lub więcej sufiksów DNS. Wszystkie wprowadzone sufiksy DNS będą wyszukiwane podczas łączenia z witryną sieci Web za pomocą nazwy skróconej. Na przykład w przypadku podania sufiksów DNS **domena1.contoso.com** i **domena2.contoso.com** i odwiedzenia adresu URL **http://mojawitryna**, zostaną wyszukane adresy URL **http://mojawitryna.domena1.contoso.com** i **http://mojawitryna.domena2.contoso.com**.

- **Niestandardowy kod XML** — określ niestandardowe polecenia XML do konfiguracji połączenia z siecią VPN.

    **Przykład dotyczący Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Przykład dotyczący CheckPoint Mobile VPN:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Przykład dotyczący Dell SonicWALL Mobile Connect:**
```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Przykład dotyczący F5 Edge Client:**
```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Więcej informacji na temat tworzenia niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producenta.

- **Podziel tunelowanie** - wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu użyje połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.




## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Automatycznie wykrywaj ustawienia proxy** — umożliwia określenie, czy urządzenia mają automatycznie wykrywać ustawienia połączenia w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
- **Skrypt konfiguracji automatycznej** — umożliwia skonfigurowanie serwera proxy przy użyciu pliku. W polu **Adres URL serwera proxy** wprowadź adres URL (na przykład **http://proxy.contoso.com**), który zawiera plik konfiguracji.
- **Użyj serwera proxy** — włącz tę opcję, jeśli chcesz ręcznie wprowadzić ustawienia serwera proxy.
    - **Adres** — wprowadź adres serwera proxy (jako adres IP).
    - **Numer portu** — wprowadź numer portu skojarzony z serwerem proxy.
- **Pomijaj serwer proxy dla adresów lokalnych** — zaznacz tę opcję, aby serwer proxy nie był używany dla określonych adresów lokalnych w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
