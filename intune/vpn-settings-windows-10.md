---
title: Wyświetlanie ustawień sieci VPN w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się więcej o dostępnych ustawieniach sieci VPN w usłudze Microsoft Intune, ich użyciu oraz działaniu, w tym o regułach ruchu, dostępie warunkowym oraz ustawieniach DNS i serwera proxy dla urządzeń z systemem Windows 10 oraz urządzeń z systemem Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 9464b73acc43b9625560156617359c374d7100fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Przeczytaj informacje o ustawieniach sieci VPN w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Możesz skonfigurować połączenia sieci VPN przy użyciu usługi Intune. W tym artykule opisano te ustawienia, reguły ruchu, dostęp warunkowy oraz ustawienia DNS i serwera proxy.

Te ustawienia mają zastosowanie do:

- urządzeń z systemem Windows 10,
- urządzeń z systemem Holographic Windows for Business.

W zależności od wybranych ustawień niektórych wartości nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Serwery**: umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia się łączą.
  - **Dodaj**: otwiera okno **Dodaj wiersz**, w którym możesz wprowadzić następujące informacje:
    - **Opis**: umożliwia podanie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**
    - **Adres IP lub nazwa FQDN**: umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia się łączą, np. **192.168.1.1** lub **vpn.contoso.com**
    - **Serwer domyślny**: określa ten serwer jako serwer domyślny używany przez urządzenia do nawiązania połączenia. Ustaw tylko jeden serwer jako domyślny.
  - **Importuj**: umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te serwery do listy **Serwery**.
  - **Eksportuj**: umożliwia wyeksportowanie listy serwerów do pliku CSV (plik wartości rozdzielanych przecinkami)

**Typ połączenia**: umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:

- **Automatyczne**
- **Check Point Capsule VPN**
- **Sieć VPN Citrix**
- **SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Grupa lub domena logowania** (tylko dla SonicWALL Mobile Connect): nie można ustawić tej właściwości w profilu sieci VPN. Zamiast tego rozwiązanie Mobile Connect analizuje tę wartość, jeśli nazwa użytkownika i domeny zostały wprowadzone w formacie `username@domain` lub `DOMAIN\username`.

**Niestandardowy kod XML**/**Kod XML protokołu EAP**: umożliwia wprowadzenie niestandardowych poleceń XML do konfiguracji połączenia z siecią VPN.

**Przykład dotyczący Pulse Secure:**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Przykład dotyczący CheckPoint Mobile VPN:**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Przykład dotyczący SonicWALL Mobile Connect:**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Przykład dotyczący F5 Edge Client:**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Więcej informacji na temat pisania niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producenta.

Aby uzyskać więcej informacji na temat tworzenia niestandardowych poleceń XML protokołu EAP, zobacz [EAP configuration (Konfiguracja protokołu EAP)](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Podziel tunelowanie**: ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.
- **Podziel trasy tunelowania dla tego połączenia VPN**: umożliwia dodanie opcjonalnych tras dla dostawców sieci VPN innej firmy. Wprowadź prefiks docelowy i rozmiar prefiksu dla każdego miejsca docelowego.

## <a name="apps-and-traffic-rules"></a>Reguły dotyczące aplikacji i ruchu

**Ogranicz połączenie sieci VPN do tych aplikacji**: włącz to ustawienie, aby tylko wybrane aplikacje mogły korzystać z połączenia VPN.
**Skojarzone aplikacje**: podaj listę aplikacji, które automatycznie będą używać połączenia VPN. Typ aplikacji określa identyfikator aplikacji. W przypadku aplikacji uniwersalnej podaj nazwę rodziny pakietów. W przypadku aplikacji klasycznej podaj ścieżkę pliku aplikacji.

>[!IMPORTANT]
>Zalecamy zabezpieczenie wszystkich list aplikacji utworzonych dla sieci VPN dla poszczególnych aplikacji. Jeśli nieautoryzowany użytkownik wprowadzi zmiany na liście, po czym zaimportujesz listę do sieci VPN aplikacji, możesz potencjalnie autoryzować dostęp za pośrednictwem sieci VPN do aplikacji, które nie powinny mieć dostępu. Jednym ze sposobów na zabezpieczenie listy aplikacji jest użycie listy kontroli dostępu (ACL).

**Reguły ruchu sieciowego dla tego połączenia sieci VPN**: wybierz protokoły oraz zakresy portów i adresów lokalnych oraz zdalnych, które mają być włączone dla połączenia sieci VPN. Jeśli nie utworzysz reguły ruchu sieciowego, wszystkie protokoły, porty i zakresy adresów zostaną włączone. Po utworzeniu reguły połączenie sieci VPN będzie używało tylko protokołów, portów i zakresów adresów wybranych w tej regule.

## <a name="conditional-access"></a>Dostęp warunkowy

**Dostęp warunkowy dla tego połączenia VPN**: umożliwia przepływ zgodności urządzenia od klienta. Po włączeniu klient VPN będzie podejmować próby komunikacji z usługą Azure Active Directory, aby uzyskać certyfikat do użycia na potrzeby uwierzytelniania. Sieć VPN należy skonfigurować do używania uwierzytelniania certyfikatów, a serwer sieci VPN musi mieć relację zaufania z serwerem zwracanym przez usługę Azure Active Directory.

**Logowanie jednokrotne z certyfikatem alternatywnym**: na potrzeby zgodności urządzeń użyj certyfikatu innego niż certyfikat uwierzytelniania sieci VPN podczas uwierzytelniania Kerberos. Wprowadź certyfikat z następującymi ustawieniami:

- **Rozszerzone użycie klucza**: nazwa rozszerzonego użycia klucza (EKU).
- **Identyfikator obiektu**: identyfikator obiektu dla EKU.
- **Skrót wystawcy**: odcisk palca certyfikatu logowania jednokrotnego.

## <a name="dns-settings"></a>Ustawienia DNS

**Nazwy i serwery DNS dla tego połączenia sieci VPN**: umożliwia wybór serwerów DNS, które będą używane przez połączenie sieci VPN po jego nawiązaniu.
Dla każdego serwera wprowadź:
- **Nazwa DNS**
- **Serwer DNS**
- **Serwer proxy**

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Automatycznie wykrywaj ustawienia proxy**: umożliwia określenie, czy urządzenia mają automatycznie wykrywać ustawienia połączenia w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy.
- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Wprowadź **Adres URL serwera proxy**, np. `http://proxy.contoso.com`, który zawiera plik konfiguracji.
- **Użyj serwera proxy**: włącz tę opcję, aby ręcznie wprowadzić ustawienia serwera proxy.
  - **Adres**: wprowadź adres serwera proxy (jako adres IP)
  - **Numer portu**: wprowadź numer portu skojarzony z serwerem proxy
- **Pomijaj serwer proxy dla adresów lokalnych**: zaznacz to ustawienie, aby serwer proxy nie był używany dla wprowadzonych adresów lokalnych w przypadku, gdy serwer sieci VPN wymaga połączenia za pośrednictwem serwera proxy.
