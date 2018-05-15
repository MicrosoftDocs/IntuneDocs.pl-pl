---
title: Konfigurowanie ustawień sieci VPN systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się więcej o dostępnych ustawieniach sieci VPN w usłudze Microsoft Intune, ich użyciu oraz działaniu, w tym o regułach ruchu, dostępie warunkowym oraz ustawieniach DNS i serwera proxy dla urządzeń z systemem Windows 10 oraz urządzeń z systemem Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: d41ec494672340a9f5751e6fc40edf1a7b06bb40
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="windows-10-vpn-settings-in-intune"></a>Ustawienia sieci VPN systemu Windows 10 w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Możesz skonfigurować połączenia sieci VPN przy użyciu usługi Intune. W tym artykule opisano te ustawienia, reguły ruchu, dostęp warunkowy oraz ustawienia DNS i serwera proxy.

Te ustawienia mają zastosowanie do:

- urządzeń z systemem Windows 10,
- urządzeń z systemem Holographic Windows for Business.

W zależności od wybranych ustawień niektórych wartości nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Serwery**: umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia się łączą. Podczas dodawania serwera należy podać następujące informacje:
  - **Opis**: umożliwia podanie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**
  - **Adres IP lub nazwa FQDN**: umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia się łączą, np. **192.168.1.1** lub **vpn.contoso.com**
  - **Serwer domyślny**: określa ten serwer jako serwer domyślny używany przez urządzenia do nawiązania połączenia. Ustaw tylko jeden serwer jako domyślny.
  - **Importuj**: umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te serwery do listy **Serwery**.
  - **Eksportuj**: umożliwia wyeksportowanie listy serwerów do pliku CSV (plik wartości rozdzielanych przecinkami)

- **Typ połączenia**: umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWALL Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Automatyczne**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  Po wybraniu typu połączenia sieci VPN może również być konieczne zdefiniowanie następujących ustawień:  
    - **Zawsze włączone**: włącz, aby automatycznie łączyć się z połączeniem sieci VPN po wystąpieniu następujących sytuacji: 
      - Użytkownik zaloguje się na urządzeniu
      - Sieć na urządzeniu zostanie zmieniona
      - Ekran na urządzeniu zostanie włączony ponownie po wyłączeniu 

    - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania użytkowników na serwerze sieci VPN. Użycie **certyfikatów** powoduje udostępnienie rozszerzonych możliwości, takich jak środowisko bezobsługowe, sieć VPN na żądanie i sieć VPN dla aplikacji.
    - **Pamiętaj poświadczenia przy każdym logowaniu**: wybierz tę opcję, aby poświadczenia uwierzytelniania były buforowane.
    - **Niestandardowy kod XML**: wprowadź niestandardowe polecenia XML do konfiguracji połączenia z siecią VPN.
    - **Kod EAP XML**: wprowadź polecenia EAP XML do konfiguracji połączenia z siecią VPN.

#### <a name="pulse-secure-example"></a>Przykład rozwiązania Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>Przykład rozwiązania F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>Przykład rozwiązania SonicWall Mobile Connect
**Grupa lub domena logowania**: nie można ustawić tej właściwości w profilu sieci VPN. Zamiast tego rozwiązanie Mobile Connect analizuje tę wartość, jeśli nazwa użytkownika i domeny zostały wprowadzone w formacie `username@domain` lub `DOMAIN\username`.

Przykład:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### <a name="checkpoint-mobile-vpn-example"></a>Przykład rozwiązania CheckPoint Mobile VPN

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### <a name="writing-custom-xml"></a>Pisanie niestandardowego kodu XML
Więcej informacji na temat pisania niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producenta.

Aby uzyskać więcej informacji na temat tworzenia niestandardowych poleceń XML protokołu EAP, zobacz [EAP configuration (Konfiguracja protokołu EAP)](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## <a name="apps-and-traffic-rules"></a>Reguły dotyczące aplikacji i ruchu

- **Skojarz PWT lub aplikacje z tą siecią VPN**: włącz to ustawienie, aby tylko wybrane aplikacje mogły korzystać z połączenia VPN. Dostępne opcje:

  - **Skojarz PWT z tym połączeniem**: wprowadź **domenę PWT dla tego połączenia**
  - **Skojarz aplikacje z tym połączeniem**: możesz **ograniczyć połączenie z siecią VPN do tych aplikacji**, a następnie dodać **skojarzone aplikacje**. Wprowadzone aplikacje będą automatycznie korzystać z połączenia z siecią VPN. Typ aplikacji określa identyfikator aplikacji. W przypadku aplikacji uniwersalnej podaj nazwę rodziny pakietów. W przypadku aplikacji klasycznej podaj ścieżkę pliku aplikacji.
  >[!IMPORTANT]
  >Zalecamy zabezpieczenie wszystkich list aplikacji utworzonych dla sieci VPN dla poszczególnych aplikacji. Jeśli nieautoryzowany użytkownik wprowadzi zmiany na liście, po czym zaimportujesz listę do sieci VPN aplikacji, możesz potencjalnie autoryzować dostęp za pośrednictwem sieci VPN do aplikacji, które nie powinny mieć dostępu. Jednym ze sposobów na zabezpieczenie listy aplikacji jest użycie listy kontroli dostępu (ACL).

- **Reguły ruchu sieciowego dla tego połączenia sieci VPN**: wybierz protokoły oraz zakresy portów i adresów lokalnych oraz zdalnych, które mają być włączone dla połączenia sieci VPN. Jeśli nie utworzysz reguły ruchu sieciowego, wszystkie protokoły, porty i zakresy adresów zostaną włączone. Po utworzeniu reguły połączenie sieci VPN będzie używało tylko protokołów, portów i zakresów adresów wybranych w tej regule.

## <a name="conditional-access"></a>Dostęp warunkowy

- **Dostęp warunkowy dla tego połączenia VPN**: umożliwia przepływ zgodności urządzenia od klienta. Po włączeniu klient VPN będzie podejmować próby komunikacji z usługą Azure Active Directory (AD), aby uzyskać certyfikat do użycia na potrzeby uwierzytelniania. Sieć VPN należy skonfigurować do używania uwierzytelniania certyfikatów, a serwer sieci VPN musi mieć relację zaufania z serwerem zwracanym przez usługę Azure AD.

- **Logowanie jednokrotne z certyfikatem alternatywnym**: na potrzeby zgodności urządzeń użyj certyfikatu innego niż certyfikat uwierzytelniania sieci VPN podczas uwierzytelniania Kerberos. Wprowadź certyfikat z następującymi ustawieniami:

  - **Nazwa**: nazwa ulepszonego użycia klucza (EKU, extended key usage)
  - **Identyfikator obiektu**: identyfikator obiektu dla EKU.
  - **Skrót wystawcy**: odcisk palca certyfikatu logowania jednokrotnego.

## <a name="dns-settings"></a>Ustawienia DNS

**Domena i serwery dla tego połączenia VPN**: dodaj domeny i serwer DNS do użycia w sieci VPN. Możesz wybrać serwery DNS do użycia przez połączenie z siecią VPN po jego nawiązaniu. Dla każdego serwera wprowadź:
- **Domeny**
- **Serwer DNS**
- **Serwer proxy**

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Wprowadź **Adres URL serwera proxy**, np. `http://proxy.contoso.com`, który zawiera plik konfiguracji.
- **Adres**: wprowadź adres serwera proxy, taki adres IP lub `vpn.contoso.com`
- **Numer portu**: wprowadź numer portu TCP używany przez serwer proxy
- **Nie używaj serwera proxy dla adresów lokalnych**: jeśli nie chcesz używać serwera proxy dla adresów lokalnych, wybierz pozycję Włącz. To ustawienie ma zastosowanie, jeśli serwer sieci VPN wymaga połączenia przez serwer proxy.

## <a name="split-tunneling"></a>Tunelowanie podzielone

- **Podziel tunelowanie**: ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.
- **Podziel trasy tunelowania dla tego połączenia VPN**: umożliwia dodanie opcjonalnych tras dla dostawców sieci VPN innej firmy. Wprowadź prefiks docelowy i rozmiar prefiksu dla każdego połączenia.
