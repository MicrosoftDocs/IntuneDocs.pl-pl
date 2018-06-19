---
title: Ustawienia sieci VPN w usłudze Microsoft Intune dla urządzeń z systemem Windows 8.1
titleSuffix: ''
description: Informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 30aa56913cc3bda2d1c8b8b67e982c565c44a2a8
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834174"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Windows 8.1 w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows 8.1.

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN


- **Zastosuj wszystkie ustawienia tylko do systemu Windows 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli jest ono ustawione na wartość **Skonfigurowane**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows 8.1. Jeśli jest ono ustawione na wartość **Nieskonfigurowane**, ustawienia te zostaną również zastosowane do urządzeń z systemem Windows 10.
- **Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy widzą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Serwery** — umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia się łączą.
    - **Dodaj** — otwiera stronę **Dodaj wiersz**, na której można określić następujące informacje:
        - **Opis** — umożliwia określenie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**.
        - **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia się łączą. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
        - **Serwer domyślny** — określa ten serwer jako serwer domyślny używany przez urządzenia do nawiązania połączenia. Upewnij się, że tylko jeden serwer jest ustawiony jako domyślny.
    - **Importuj** — umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te dane do listy **Serwery**.
    - **Eksportuj** — eksportuje listę serwerów do pliku CSV.

- **Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
- **Check Point Capsule VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Grupa lub domena logowania** (tylko dla SonicWall Mobile Connect) — umożliwia określenie nazwy grupy lub domeny logowania, z którą chcesz nawiązać połączenie.

- **Rola** (tylko dla Pulse Secure) — umożliwia określenie nazwy roli użytkownika, która ma dostęp do tego połączenia. Rola użytkownika definiuje ustawienia osobiste i opcje oraz włączenie lub wyłączenie określonych funkcji dostępu.

- **Obszar** (tylko dla Pulse Secure) — umożliwia określenie nazwy obszaru uwierzytelniania, który ma być używany. Obszar uwierzytelniania to grupa zasobów uwierzytelniania używana przez typ połączenia Pulse Secure.


- **Niestandardowy kod XML** — określ niestandardowe polecenia XML do konfiguracji połączenia z siecią VPN.

**Przykład dotyczący Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Przykład dotyczący CheckPoint Mobile VPN:**
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Przykład dotyczący SonicWall Mobile Connect:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Przykład dotyczący F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Więcej informacji na temat tworzenia niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producenta.


## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Automatycznie wykrywaj ustawienia proxy** — umożliwia określenie, czy urządzenia mają automatycznie wykrywać ustawienia połączenia w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
- **Skrypt konfiguracji automatycznej** — umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Podaj **adres URL serwera proxy**, np. **http://proxy.contoso.com**, który zawiera plik konfiguracji.
- **Użyj serwera proxy** — włącz tę opcję, jeśli chcesz ręcznie wprowadzić ustawienia serwera proxy.
    - **Adres** — wprowadź adres serwera proxy (jako adres IP).
    - **Numer portu** — wprowadź numer portu skojarzony z serwerem proxy.
- **Pomijaj serwer proxy dla adresów lokalnych** — zaznacz tę opcję, aby serwer proxy nie był używany dla określonych adresów lokalnych w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
