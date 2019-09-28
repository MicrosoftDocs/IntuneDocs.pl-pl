---
title: Ustawienia sieci VPN w usłudze Microsoft Intune dla urządzeń z systemem Windows Phone 8.1
titleSuffix: ''
description: Informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows Phone 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bd79e13c285fd75c2c2abbdf8f1628d9cd09c8d
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "71302724"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-phone-81"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows Phone 8.1.


W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli jest ono ustawione na wartość **Skonfigurowane**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli jest ono ustawione na wartość **Nieskonfigurowane**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
- **Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy widzą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Metoda uwierzytelniania** — umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
  - **Certyfikaty** — w obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej szczegółowych informacji o profilach certyfikatów, zobacz artykuł [Konfigurowanie certyfikatów](certificates-configure.md).
  - **Nazwa użytkownika i hasło** — użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Serwery** — umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia się łączą.
  - **Dodaj** — otwiera blok **Dodaj wiersz**, w którym można określić następujące informacje:
    - **Opis** — umożliwia określenie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**.
    - **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia się łączą. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
    - **Serwer domyślny** — określa ten serwer jako serwer domyślny używany przez urządzenia do nawiązania połączenia. Upewnij się, że tylko jeden serwer jest ustawiony jako domyślny.
  - **Importuj** — umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te dane do listy **Serwery**.
  - **Eksportuj** — umożliwia wyeksportowanie listy serwerów do pliku CSV (plik wartości rozdzielany przecinkami).

- **Pomijaj sieć VPN w firmowej sieci Wi-Fi** — włącz tę opcję, aby określić, że połączenie z siecią VPN nie będzie używane, gdy urządzenie jest połączone z firmową siecią Wi-Fi.
- **Pomijaj sieć VPN w domowej sieci Wi-Fi** — włącz tę opcję, aby określić, że połączenie z siecią VPN nie będzie używane, gdy urządzenie jest połączone z domową siecią Wi-Fi.

- **Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

- **Grupa lub domena logowania** (tylko dla SonicWall Mobile Connect) — umożliwia określenie nazwy grupy lub domeny logowania, z którą chcesz nawiązać połączenie.
- **Rola** (tylko dla Pulse Secure) — umożliwia określenie nazwy roli użytkownika, która ma dostęp do tego połączenia. Rola użytkownika definiuje ustawienia osobiste i opcje oraz włączenie lub wyłączenie określonych funkcji dostępu.
- **Obszar** (tylko dla Pulse Secure) — umożliwia określenie nazwy obszaru uwierzytelniania, który ma być używany. Obszar uwierzytelniania to grupa zasobów uwierzytelniania używana przez typ połączenia Pulse Secure.

- **Lista przeszukiwania sufiksów DNS** - korzystając z opcji **Dodaj**, możesz dodać jeden lub więcej sufiksów DNS. Wszystkie wprowadzone sufiksy DNS są wyszukiwane podczas łączenia z witryną internetową za pomocą nazwy skróconej. Na przykład określ sufiksy usługi DNS **domena1.contoso.com** i **domena2.contoso.com**, a następnie otwórz adres URL `http://mywebsite`, aby przeszukać adresy URL `http://mywebsite.domain1.contoso.com` i `http://mywebsite.domain2.contoso.com`.

- **Niestandardowy kod XML** — określ niestandardowe polecenia XML do konfiguracji połączenia z siecią VPN.

    **Przykład dotyczący Pulse Secure:**

```xml
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Przykład dotyczący CheckPoint Mobile VPN:**

```xml
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Przykład dotyczący SonicWall Mobile Connect:**

```xml
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Przykład dotyczący F5 Edge Client:**

```xml
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Więcej informacji na temat tworzenia niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producenta.

- **Podziel tunelowanie** - wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.




## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Automatycznie wykrywaj ustawienia proxy** — umożliwia określenie, czy urządzenia mają automatycznie wykrywać ustawienia połączenia w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
- **Skrypt konfiguracji automatycznej** — umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Podaj **adres URL serwera proxy**, np. `http://proxy.contoso.com`, który zawiera plik konfiguracji.
- **Użyj serwera proxy** — włącz tę opcję, jeśli chcesz ręcznie wprowadzić ustawienia serwera proxy.
  - **Adres** — wprowadź adres serwera proxy (jako adres IP).
  - **Numer portu** — wprowadź numer portu skojarzony z serwerem proxy.
- **Pomijaj serwer proxy dla adresów lokalnych** — zaznacz tę opcję, aby serwer proxy nie był używany dla określonych adresów lokalnych w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
