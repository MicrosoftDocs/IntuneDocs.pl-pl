---
title: "Ustawienia sieci VPN w usłudze Intune dla urządzeń z systemem Windows 10"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień usługi Intune służących do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows 10."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6dd98b176c76e19d6ff261a4dafbabfb9698f787
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Ustawienia sieci VPN dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.


## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN


- **Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy zobaczą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Serwery** — umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia będą się łączyć.
    - **Dodaj** — otwiera blok **Dodaj wiersz**, w którym można określić następujące informacje:
        - **Opis** — umożliwia określenie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**.
        - **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia będą się łączyć. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
        - **Serwer domyślny** — określa ten serwer jako serwer domyślny używany przez urządzenia do ustanowienia połączenia. Upewnij się, że tylko jeden serwer jest ustawiony jako domyślny.
    - **Importuj** — umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te dane do listy **Serwery**.
    - **Eksportuj** — umożliwia wyeksportowanie listy serwerów do pliku CSV (plik wartości rozdzielany przecinkami).

**Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
- **Pulse Secure**
- **F5 Edge Client**
- **Dell SonicWALL Mobile Connect**
- **Check Point Capsule VPN**
- **Automatyczne**
- **IKEv2**
- **L2TP**
- **PPTP**

**Grupa lub domena logowania** (tylko dla Dell SonicWALL Mobile Connect) — umożliwia określenie nazwy grupy lub domeny logowania, z którą chcesz nawiązać połączenie.

**Niestandardowy kod XML**/**Kod XML protokołu EAP** — umożliwia określenie niestandardowych poleceń XML do konfiguracji połączenia z siecią VPN.

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

**Podziel tunelowanie** - wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu użyje połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.
- **Podziel trasy tunelowania dla tego połączenia VPN** — umożliwia dodanie opcjonalnych tras dla dostawców sieci VPN innej firmy. Określ prefiks docelowy i rozmiar prefiksu dla każdego miejsca docelowego.

## <a name="apps-and-traffic-rules"></a>Reguły dotyczące aplikacji i ruchu

**Ogranicz połączenie sieci VPN do tych aplikacji** — włącz tę opcję, aby tylko określone aplikacje mogły korzystać z połączenia VPN.
**Skojarzone aplikacje** — podaj listę aplikacji, które automatycznie będą używać połączenia VPN. Typ aplikacji określa identyfikator aplikacji. W przypadku aplikacji uniwersalnej podaj nazwę rodziny pakietów. W przypadku aplikacji klasycznej podaj ścieżkę pliku aplikacji.

>[!IMPORTANT]
>Zalecamy zabezpieczenie wszystkich list aplikacji kompilowanych do użytku w konfiguracji sieci VPN aplikacji. Jeśli nieautoryzowany użytkownik zmodyfikuje listę, po czym zaimportujesz listę do sieci VPN aplikacji, możesz potencjalnie autoryzować dostęp za pośrednictwem sieci VPN do aplikacji, które nie powinny mieć dostępu. Jednym ze sposobów na zabezpieczenie listy aplikacji jest użycie listy kontroli dostępu (ACL).

**Reguły ruchu sieciowego dla tego połączenia sieci VPN** — wybierz protokoły oraz zakresy portów i adresów lokalnych i zdalnych, które mają być włączone dla połączenia sieci VPN. Jeśli nie utworzysz reguły ruchu sieciowego, wszystkie protokoły, porty i zakresy adresów zostaną włączone. Po utworzeniu reguły połączenie sieci VPN będzie używało tylko protokołów, portów i zakresów adresów wybranych w tej regule.


## <a name="conditional-access"></a>Dostęp warunkowy

**Dostęp warunkowy dla tego połączenia VPN** -
**Logowanie jednokrotne (SSO) z certyfikatem alternatywnym** -
**Rozszerzone użycie klucza** -
**Skrót wydawcy** -

## <a name="dns-settings"></a>Ustawienia DNS

**Nazwy i serwery DNS dla tego połączenia sieci VPN** — umożliwia wybór serwerów DNS, które będą używane przez połączenie sieci VPN po jego nawiązaniu.
Dla każdego serwera określ następujące parametry:
- **Nazwa DNS**
- **Serwer DNS**
- **Serwer proxy**

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Automatycznie wykrywaj ustawienia proxy** — umożliwia określenie, czy urządzenia mają automatycznie wykrywać ustawienia połączenia w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
- **Skrypt konfiguracji automatycznej** — umożliwia skonfigurowanie serwera proxy przy użyciu pliku. W polu **Adres URL serwera proxy** wprowadź adres URL (na przykład **http://proxy.contoso.com**), który zawiera plik konfiguracji.
- **Użyj serwera proxy** — włącz tę opcję, jeśli chcesz ręcznie wprowadzić ustawienia serwera proxy.
    - **Adres** — wprowadź adres serwera proxy (jako adres IP).
    - **Numer portu** — wprowadź numer portu skojarzony z serwerem proxy.
- **Pomijaj serwer proxy dla adresów lokalnych** — zaznacz tę opcję, aby serwer proxy nie był używany dla określonych adresów lokalnych w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
