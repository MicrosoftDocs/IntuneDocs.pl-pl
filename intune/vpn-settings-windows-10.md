---
title: Ustawienia sieci VPN systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się więcej o wszystkich dostępnych ustawieniach sieci VPN w usłudze Microsoft Intune, ich użyciu oraz działaniu, w tym o regułach ruchu, dostępie warunkowym oraz ustawieniach DNS i serwera proxy dla urządzeń z systemami Windows 10 i Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a35ebcf6ecbaaa746a6da98c5bd5c13ca9a7b130
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2019
ms.locfileid: "71302736"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Ustawienia urządzeń z systemami Windows 10 i Windows Holographic umożliwiające dodanie połączeń sieci VPN przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Używając usługi Microsoft Intune, możesz dodać i skonfigurować połączenia sieci VPN dla urządzeń. W tym artykule wymieniono i opisano ustawienia i funkcje, które są najczęściej używane podczas tworzenia wirtualnych sieci prywatnych (VPN, virtual private network). Te ustawienia i funkcje sieci VPN są używane w profilach konfiguracji urządzeń w usłudze Intune, które są wypychane do urządzeń lub na nich wdrażane. 

Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwolić na działanie funkcji (takich jak używanie dostawcy sieci VPN, aktywowanie opcji „zawsze włączone”, używanie systemu DNS, dodawanie serwera proxy i nie tylko) lub je wyłączyć.

Te ustawienia dotyczą urządzeń z systemami:

- Windows 10
- Windows Holographic for Business

W zależności od wybranych ustawień niektórych wartości nie będzie można skonfigurować.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia sieci VPN](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Serwery**: umożliwia dodanie jednego lub większej liczby serwerów sieci VPN, z którymi urządzenia się łączą. Podczas dodawania serwera należy podać następujące informacje:
  - **Opis**: umożliwia podanie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**
  - **Adres IP lub nazwa FQDN**: umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny (FQDN) serwera sieci VPN, z którym urządzenia się łączą, np. **192.168.1.1** lub **vpn.contoso.com**
  - **Serwer domyślny**: określa ten serwer jako serwer domyślny używany przez urządzenia do nawiązania połączenia. Ustaw tylko jeden serwer jako domyślny.
  - **Importuj**: umożliwia przejście do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te serwery do listy **Serwery**.
  - **Eksportuj**: umożliwia wyeksportowanie listy serwerów do pliku CSV (plik wartości rozdzielanych przecinkami)

- **Rejestrowanie adresów IP przy użyciu wewnętrznego serwera DNS**: wybierz opcję **Włącz**, aby skonfigurować profil sieci VPN w systemie Windows 10 i dynamicznie rejestrować adresy IP przypisane do interfejsu sieci VPN przy użyciu wewnętrznego serwera DNS. Wybierz opcję **Wyłącz**, aby nie rejestrować dynamicznie adresów IP.

- **Typ połączenia**: umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWALL Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Networks GlobalProtect**
  - **Automatyczne**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  Po wybraniu typu połączenia sieci VPN może również być konieczne zdefiniowanie następujących ustawień:  
  - **Zawsze włączone**: wybierz opcję **Włącz**, aby automatycznie łączyć się z połączeniem sieci VPN po wystąpieniu następujących zdarzeń: 
    - Użytkownik zaloguje się na urządzeniu
    - Sieć na urządzeniu zostanie zmieniona
    - Ekran na urządzeniu zostanie włączony ponownie po wyłączeniu 

  - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania użytkowników na serwerze sieci VPN. Użycie **certyfikatów** powoduje udostępnienie rozszerzonych funkcji, takich jak środowisko bezobsługowe, sieć VPN na żądanie i sieć VPN dla aplikacji.
  - **Pamiętaj poświadczenia przy każdym logowaniu**: wybierz tę opcję, aby poświadczenia uwierzytelniania były buforowane.
  - **Niestandardowy kod XML**: wprowadź niestandardowe polecenia XML do konfiguracji połączenia z siecią VPN.
  - **Kod EAP XML**: wprowadź polecenia EAP XML do konfiguracji połączenia z siecią VPN.

### <a name="pulse-secure-example"></a>Przykład rozwiązania Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

### <a name="f5-edge-client-example"></a>Przykład rozwiązania F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

### <a name="sonicwall-mobile-connect-example"></a>Przykład rozwiązania SonicWall Mobile Connect
**Grupa lub domena logowania**: nie można ustawić tej właściwości w profilu sieci VPN. Zamiast tego rozwiązanie Mobile Connect analizuje tę wartość, jeśli nazwa użytkownika i domeny zostały wprowadzone w formacie `username@domain` lub `DOMAIN\username`.

Przykład:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

### <a name="checkpoint-mobile-vpn-example"></a>Przykład rozwiązania CheckPoint Mobile VPN

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

### <a name="writing-custom-xml"></a>Pisanie niestandardowego kodu XML
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

- **Dostęp warunkowy dla tego połączenia VPN**: umożliwia przepływ zgodności urządzenia od klienta. Po włączeniu klient VPN komunikuje się z usługą Azure Active Directory (AD), aby uzyskać certyfikat do użycia na potrzeby uwierzytelniania. Sieć VPN należy skonfigurować do używania uwierzytelniania certyfikatów, a serwer sieci VPN musi mieć relację zaufania z serwerem zwracanym przez usługę Azure AD.

- **Logowanie jednokrotne z certyfikatem alternatywnym**: na potrzeby zgodności urządzeń użyj certyfikatu innego niż certyfikat uwierzytelniania sieci VPN podczas uwierzytelniania Kerberos. Wprowadź certyfikat z następującymi ustawieniami:

  - **Nazwa**: nazwa ulepszonego użycia klucza (EKU, extended key usage)
  - **Identyfikator obiektu**: identyfikator obiektu dla EKU.
  - **Skrót wystawcy**: odcisk palca certyfikatu logowania jednokrotnego.

## <a name="dns-settings"></a>Ustawienia DNS

- **Lista wyszukiwania sufiksów DNS**: w obszarze **Sufiksy DNS** wprowadź sufiks DNS i wybierz polecenie **Dodaj**. Możesz dodać wiele sufiksów.

  Korzystając z sufiksów DNS, możesz wyszukać zasób sieciowy za pomocą jego krótkiej nazwy, zamiast w pełni kwalifikowanej nazwy domeny (FQDN). Podczas wyszukiwania przy użyciu krótkiej nazwy sufiks jest automatycznie określany przez serwer DNS. Na przykład sufiks `utah.contoso.com` znajduje się na liście sufiksów DNS. Wyślij polecenie ping `DEV-comp`. W tym scenariuszu jest on rozpoznawany jako `DEV-comp.utah.contoso.com`.

  Sufiksy DNS są rozpoznawane w podanej kolejności; ponadto można zmienić kolejność. Na przykład sufiksy `colorado.contoso.com` i `utah.contoso.com` są na liście sufiksów DNS i oba zawierają zasób o nazwie `DEV-comp`. Ponieważ sufiks `colorado.contoso.com` jest pierwszy na liście, zostaje rozpoznany jako `DEV-comp.colorado.contoso.com`.
  
  Aby zmienić kolejność, kliknij symbol kropek po lewej stronie sufiksu DNS, a następnie przeciągnij sufiks do góry:

  ![Wybór symbolu trzech kropek oraz kliknięcie i przeciągnięcie sufiksu DNS w celu jego przeniesienia](./media/vpn-settings-windows10-move-dns-suffix.png)

- **Reguły tabeli zasad rozpoznawania nazw (NRPT)** : reguły dotyczące tabeli zasad rozpoznawania nazw (NRPT) definiują sposób, w jaki usługa DNS rozpoznaje nazwy po nawiązaniu połączenia z siecią VPN. Po ustanowieniu połączenia z siecią VPN możesz wybrać serwery DNS, których to połączenie będzie używać.

  Do tabeli możesz dodać reguły, które zawierają domenę, serwer DNS, serwer proxy i inne szczegóły umożliwiające rozpoznanie wprowadzonej domeny. Połączenie sieci VPN korzysta z tych reguł, kiedy użytkownicy łączą się z wprowadzonymi domenami.

  Wybierz pozycję **Dodaj**, aby dodać nową regułę. Dla każdego serwera wprowadź:

  - **Domena**: wprowadź w pełni kwalifikowaną nazwę domeny (FQDN) lub sufiks DNS, aby zastosować regułę. Możesz również wprowadzić znak kropki (.) na początku sufiksu DNS. Na przykład wprowadź adres `contoso.com` lub `.allcontososubdomains.com`.
  - **Serwer DNS**: wprowadź adres IP lub serwer DNS, który umożliwia rozpoznanie domeny. Na przykład wprowadź adres `10.0.0.3` lub `vpn.contoso.com`.
  - **Serwer proxy**: wprowadź internetowy serwer proxy, który umożliwia rozpoznanie domeny. Na przykład wprowadź `http://proxy.com`.
  - **Połącz automatycznie**: po wybraniu pozycji **Włączone** urządzenie automatycznie łączy się z siecią VPN po nawiązaniu połączenia z wprowadzoną domeną, np. `contoso.com`. Po wybraniu pozycji **Nie skonfigurowano** (ustawienie domyślne), urządzenie nie łączy się automatycznie z siecią VPN
  - **Trwała**: po wybraniu pozycji **Włączone** reguła pozostaje w tabeli zasad rozpoznawania nazw (NRPT), dopóki nie zostanie ręcznie usunięta z urządzenia, nawet po rozłączeniu z siecią VPN. W przypadku ustawienia opcji **Nie skonfigurowano** (ustawienie domyślne) reguły tabeli NRPT w profilu sieci VPN są usuwane z urządzenia po rozłączeniu z siecią VPN.

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Wprowadź **Adres URL serwera proxy**, np. `http://proxy.contoso.com`, który zawiera plik konfiguracji.
- **Adres**: wprowadź adres serwera proxy, taki adres IP lub `vpn.contoso.com`
- **Numer portu**: wprowadź numer portu TCP używany przez serwer proxy
- **Nie używaj serwera proxy dla adresów lokalnych**: jeśli nie chcesz używać serwera proxy dla adresów lokalnych, wybierz pozycję Włącz. To ustawienie ma zastosowanie, jeśli serwer sieci VPN wymaga połączenia przez serwer proxy.

## <a name="split-tunneling"></a>Tunelowanie podzielone

- **Podziel tunelowanie**: ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.
- **Podziel trasy tunelowania dla tego połączenia VPN**: umożliwia dodanie opcjonalnych tras dla dostawców sieci VPN innej firmy. Wprowadź prefiks docelowy i rozmiar prefiksu dla każdego połączenia.

## <a name="trusted-network-detection"></a>Wykrywanie zaufanych sieci

**Sufiksy DNS zaufanych sieci**: kiedy użytkownicy są już połączeni z zaufaną siecią, możesz uniemożliwić urządzeniom automatyczne nawiązywanie połączenia z innymi sieciami VPN.

W polu **Sufiksy DNS** wprowadź sufiks DNS, któremu chcesz zaufać, na przykład contoso.com, i wybierz pozycję **Dodaj**. Możesz dodać dowolną liczbę sufiksów.

Jeśli użytkownik będzie połączony z sufiksem DNS znajdującym się na liście, to nie będzie automatycznie łączyć się z innymi sieciami VPN. Użytkownik będzie nadal używać listy wprowadzonych zaufanych sufiksów DNS. Zaufana sieć jest nadal używana, nawet jeśli ustawiono automatyczne wyzwalacze.

Jeśli na przykład użytkownik jest już połączony z zaufanym sufiksem DNS, to ignorowane są następujące automatyczne wyzwalacze. W szczególności sufiksy DNS na liście anulują wszystkie inne automatyczne wyzwalacze połączenia, w tym:

- Zawsze włączone
- Wyzwalacz oparty na aplikacjach
- Automatyczny wyzwalacz DNS

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Konfigurowanie ustawień sieci VPN na urządzeniach z systemami [Android](vpn-settings-android.md), [iOS](vpn-settings-ios.md) i [macOS](vpn-settings-macos.md).
