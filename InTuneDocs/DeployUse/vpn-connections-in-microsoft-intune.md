---
title: "Połączenia VPN | Microsoft Intune"
description: "Za pomocą profilów sieci VPN możesz wdrażać ustawienia sieci VPN dla użytkowników i urządzeń w organizacji."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 8d83e576c0c3e85c435e6738e3236f6cd4c43ccd


---

# Połączenia VPN w usłudze Microsoft Intune
 Wirtualne sieci prywatne (VPN) pozwalają zapewnić użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Użytkownicy zdalni mogą dzięki temu pracować tak, jakby ich urządzenia były fizycznie połączone z siecią. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. Za pomocą opcji w obszarze **Profile sieci VPN** w usłudze Microsoft Intune możesz wdrażać ustawienia sieci VPN dla użytkowników i urządzeń w swojej organizacji. Przez wdrożenie tych ustawień można maksymalnie ułatwić użytkownikom końcowym nawiązywanie połączeń z zasobami w sieci firmowej.

Na przykład: chcesz udostępnić wszystkim urządzeniom z systemem iOS ustawienia wymagane do połączenia z udziałem plików w sieci firmowej. Możesz utworzyć profil sieci VPN zawierający ustawienia wymagane do połączenia z siecią firmową, a następnie wdrożyć go dla wszystkich użytkowników mających urządzenia z systemem iOS. Użytkownicy będą widzieli połączenie VPN na liście dostępnych połączeń i będą mogli łatwo nawiązać połączenie.

Za pomocą profili sieci VPN można konfigurować następujące typy urządzeń:

* Urządzenia z systemem Android 4 i nowszymi
* Urządzenia z systemem iOS 7.1 i nowszymi
* Urządzenia z systemem Mac OS X 10.9 i nowszymi
* Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
* Urządzenia z systemem Windows Phone 8.1 lub nowszym
* Urządzenia z systemem Windows 10 Desktop i Mobile

Opcje konfiguracji profilu sieci VPN różnią się w zależności od wybranego typu urządzenia.

## Typy połączeń z siecią VPN

Usługa Intune umożliwia tworzenie profilów sieci VPN korzystających z następujących typów połączeń:




Typ połączenia |iOS i Mac OS X  |Android|Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8,1|Windows 10 Desktop i Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Tak |Tak   |Nie    |     Nie    |Nie  |Nie    | Tak (OMA-URI, tylko urządzenia przenośne)|     
Pulse Secure|Tak  |Tak |Tak   |Nie  |Tak  |Tak| Tak|        
F5 Edge Client|Tak |Tak |Tak |Nie  |Tak  |   Tak |  Tak|   
Dell SonicWALL Mobile Connect|Tak |Tak |Tak |Nie  |Tak |Tak |Tak|         
CheckPoint Mobile VPN|Tak |Tak |Tak |Tak |Tak|Tak|Tak|
Microsoft SSL (SSTP)|Nie |Nie |Nie |Nie |Nie|Nie|VPNv1 OMA-URI*|
Tryb automatyczny firmy Microsoft|Nie |Nie |Nie |Nie |Nie|Tak (OMA-URI)|Tak|
IKEv2|Profil niestandardowy systemu iOS|Nie |Nie |Nie |Nie|Tak (OMA-URI)|Tak|
PPTP|Profil niestandardowy systemu iOS|Nie |Nie |Nie |Nie|Nie|Tak|
L2TP|Profil niestandardowy systemu iOS|Nie |Nie |Nie |Nie|Tak (OMA-URI)|Tak|

\* Bez dodatkowych ustawień, które w przeciwnym razie są dostępne w systemie Windows 10.

> [!IMPORTANT] Aby używanie profili sieci VPN wdrożonych na urządzeniu było możliwe, należy zainstalować odpowiednią do profilu aplikację VPN. W temacie [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md) znajdziesz informacje, które pomogą Ci we wdrażaniu odpowiedniej aplikacji w usłudze Intune.  

 Dowiedz się, jak utworzyć niestandardowe profile sieci VPN za pomocą ustawienia identyfikatora URI w temacie [Konfiguracje niestandardowe dla profilów sieci VPN](custom-configurations-for-vpn-profiles.md).     

## Jak są zabezpieczone profile sieci VPN

Profile sieci VPN mogą wykorzystywać różne typy połączeń i protokoły różnych producentów. Połączenia te są zwykle chronione przy użyciu jednej z dwóch metod:

### Certyfikaty

Podczas tworzenia profilu sieci VPN wybierasz profil certyfikatu SCEP lub PFX utworzony wcześniej w usłudze Intune.

Jest on znany pod nazwą certyfikatu tożsamości i jest używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub certyfikatu głównego), który został utworzony do określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest wdrażany na komputerze przeprowadzającym uwierzytelnienie połączenia z siecią VPN — zazwyczaj jest to serwer sieci VPN.

Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).

### Nazwa użytkownika i hasło

Użytkownik jest uwierzytelniany w sieci VPN przez podanie swojej nazwy użytkownika i hasła.

## Tworzenie profilu sieci VPN

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady > Dodaj zasady**.
2. Wybierz szablon nowych zasad, rozwijając odpowiedni typ urządzenia, a następnie wybierz profil sieci VPN dla tego urządzenia:
    * **Profil sieci VPN (system Android 4 i nowsze)**
    * **Profil sieci VPN (system iOS 7.1 i nowsze)**
    * **Profil sieci VPN (system Mac OS X 10.9 i nowsze)**
    * **Profil sieci VPN (system Windows 8.1 i nowsze)**
    * **Profil sieci VPN (system Windows Phone 8.1 i nowsze)**
    * **Profil sieci VPN (system Windows 10 Desktop i Mobile oraz nowsze)**

    Tworzyć i wdrażać można tylko niestandardowe zasady profilu sieci VPN. Zalecane ustawienia są niedostępne.

3. Skorzystaj z poniższej tabeli, aby skonfigurować ustawienia profilu sieci VPN:

Nazwa ustawienia  |Więcej informacji  
---------|---------
**Nazwa**     |Wprowadzenie unikatowej nazwy profilu sieci VPN pomaga zidentyfikować te zasady w konsoli usługi Intune.         
**Opis**     |Podaj opis, który umożliwia identyfikowanie profilu sieci VPN, i inne istotne informacje ułatwiające znalezienie go.         
**Nazwa połączenia VPN (wyświetlana dla użytkowników)**     |Wprowadź nazwę profilu sieci VPN. Jest to nazwa, którą użytkownicy zobaczą na liście dostępnych połączeń VPN na swoich urządzeniach.         
**Typ połączenia**     |  Wybierz jeden z następujących typów połączeń do użycia w danym profilu sieci VPN: **Cisco AnyConnect** (niedostępne dla systemów Windows 8.1 i Windows Phone 8.1), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**
**Opis serwera sieci VPN**     | Wprowadź opis serwera sieci VPN, z którym będą łączyć się urządzenia. **Przykład:** Serwer sieci VPN firmy Contoso Jeśli typ połączenia to **F5 Edge Client**, użyj pola **Lista serwerów**, aby określić listę opisów i adresów IP serwerów.
**Adres IP lub nazwa FQDN serwera**    |Podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym będą łączyć się urządzenia. **Przykłady:** 192.168.1.1, vpn.contoso.com.  Jeśli typ połączenia to **F5 Edge Client**, użyj pola **Lista serwerów**, aby określić listę opisów i adresów IP serwerów.         |         
**Lista serwerów**     |Wybierz pozycję **Dodaj**, aby dodać nowy serwer sieci VPN do użycia na potrzeby połączenia z siecią VPN. Możesz również określić, który serwer będzie serwerem domyślnym dla danego połączenia. Ta opcja jest wyświetlana tylko wtedy, gdy typ połączenia to **F5 Edge Client**.         
**Wyślij cały ruch sieciowy przez połączenie VPN**     |Jeśli zaznaczysz tę opcję, cały ruch sieciowy będzie przesyłany przez połączenie VPN. Jeśli nie zaznaczysz tej opcji, po połączeniu z serwerem sieci VPN innej firmy klient będzie w sposób dynamiczny negocjował trasy tunelowania podzielonego. Tylko połączenia z siecią firmową są przesyłane przez tunel VPN. Tunelowanie VPN nie jest używane w przypadku łączenia się z zasobami przez Internet.
**Metoda uwierzytelniania**| Wybierz metodę uwierzytelniania stosowaną dla tego połączenia z siecią VPN: **Certyfikaty** lub **Nazwa użytkownika i hasło**. (Ustawienie Nazwa użytkownika i hasło jest niedostępne, gdy typ połączenia to Cisco AnyConnect.) Opcja **Metoda uwierzytelniania** jest niedostępna dla systemu Windows 8.1
**Pamiętaj poświadczenia użytkownika przy każdym logowaniu**|Wybierz tę opcję, aby zapamiętać poświadczenia użytkownika, dzięki czemu użytkownik nie będzie musiał wprowadzać ich za każdym razem, gdy nawiązuje połączenie.
**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Wybierz wcześniej utworzony certyfikat SCEP klienta, który będzie używany do uwierzytelniania połączenia z siecią VPN. Aby uzyskać więcej informacji o sposobie używania profilów certyfikatów w usłudze Intune, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md). Ta opcja jest wyświetlana tylko wtedy, gdy metoda uwierzytelniania to **Certyfikaty**.
**Rola**| Określ nazwę roli użytkownika, która ma dostęp do tego połączenia. Rola użytkownika definiuje ustawienia osobiste i opcje oraz włączenie lub wyłączenie określonych funkcji dostępu. Ta opcja jest wyświetlana tylko wtedy, gdy typ połączenia to **Pulse Secure**.
**Obszar**|Określ nazwę obszaru uwierzytelniania, który ma być używany. Obszar uwierzytelniania to grupa zasobów uwierzytelniania używana przez typ połączenia Pulse Secure. Ta opcja jest wyświetlana tylko wtedy, gdy typ połączenia to **Pulse Secure**.
**Grupa lub domena logowania**|Określ nazwę grupy lub domeny logowania, z którą chcesz nawiązać połączenie. Ta opcja jest wyświetlana tylko wtedy, gdy typ połączenia to **Dell SonicWALL Mobile Connect**.
**Odcisk palca**|Określ ciąg znaków, na przykład „kod odcisku palca firmy Contoso”, który będzie używany do sprawdzenia, czy dany serwer sieci VPN jest zaufany. Odcisk palca można: Wysłać do klienta, który będzie wówczas traktował każdy serwer przedstawiający ten sam odcisk palca podczas połączenia jako zaufany. Jeśli urządzenie nie otrzymało jeszcze odcisku palca, zostanie wyświetlony monit dotyczący zaufania serwerowi sieci VPN, z którym jest nawiązywane połączenie, zawierający odcisk palca (użytkownik samodzielnie weryfikuje odcisk palca i wybiera pozycję **ufaj**, aby nawiązać połączenie). Ta opcja jest wyświetlana tylko wtedy, gdy typ połączenia to **CheckPoint Mobile VPN**.
**Sieć VPN dla aplikacji**|Wybierz tę opcję, jeśli chcesz powiązać to połączenie VPN z aplikacją dla systemu iOS lub Mac OS X, tak aby połączenie było otwierane w momencie uruchomienia aplikacji. Podczas wdrażania oprogramowania możesz powiązać ten profil sieci VPN z aplikacją. Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md)
**Automatycznie wykrywaj ustawienia proxy** (tylko systemy iOS, Mac OS X, Windows 8.1 i Windows Phone 8.1)|Jeśli serwer sieci VPN wymaga połączenia przez serwer proxy, określ, czy chcesz, aby urządzenia automatycznie wykrywały ustawienia połączenia. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
**Użyj skryptu automatycznej konfiguracji** (tylko systemy iOS, Mac OS X, Windows 8.1 i Windows Phone 8.1)|Jeśli serwer sieci VPN wymaga połączenia przez serwer proxy, określ, czy chcesz używać skryptu automatycznej konfiguracji do określenia ustawień, a następnie wprowadź adres URL pliku zawierającego ustawienia. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
**Użyj serwera proxy** (tylko systemy iOS, Mac OS X, Windows 8.1 i Windows Phone 8.1)|Jeśli serwer sieci VPN wymaga połączenia przez serwer proxy, zaznacz tę opcję, a następnie wprowadź adres i numer portu serwera proxy. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
**Pomiń ustawienia serwera proxy dla adresów lokalnych** (tylko systemy iOS, Mac OS X, Windows 8.1 i Windows Phone 8.1)|Jeśli serwer sieci VPN wymaga połączenia przez serwer proxy, zaznacz tę opcję, aby serwer proxy nie był używany dla określonych adresów lokalnych. Więcej informacji znajduje się w dokumentacji systemu Windows Server.
**Niestandardowy plik XML** (systemy Windows 8.1 i nowsze oraz Windows Phone 8.1 i nowsze)|Umożliwia określenie niestandardowych poleceń XML do konfiguracji połączenia z siecią VPN. Przykłady: Dla programu **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Dla programu **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Dla programu **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Dla programu **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Więcej informacji na temat tworzenia niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producentów.
**Lista wyszukiwania sufiksów DNS** (tylko system Windows Phone 8.1)|Wprowadź jeden sufiks DNS w każdym wierszu. Wszystkie wprowadzone sufiksy DNS będą wyszukiwane podczas łączenia z witryną internetową za pomocą nazwy skróconej. Na przykład podaj sufiksy DNS **domena1.contoso.com** i **domena2.contoso.com**, odwiedź adres URL **http://mojawitryna**, a zostaną wyszukane adresy URL **http://mojawitryna.domena1.contoso.com** i **http://mojawitryna.domena2.contoso.com**.
**Obejdź sieć VPN w przypadku połączenia z firmową siecią Wi-Fi** (tylko system Windows Phone 8.1)|W przypadku wybrania tej opcji połączenie z siecią VPN nie będzie używane, jeśli urządzenie jest połączone z firmową siecią Wi-Fi.
**Obejdź sieć VPN w przypadku połączenia z domową siecią Wi-Fi** (tylko system Windows Phone 8.1)|W przypadku wybrania tej opcji połączenie z siecią VPN nie będzie używane, jeśli urządzenie jest połączone z domową siecią Wi-Fi.

Następujące dodatkowe ustawienia są dostępne dla urządzeń z systemem Windows 10 Desktop i Windows 10 Mobile

Nazwa ustawienia  |Więcej informacji  
---------|---------
**Reguły ruchu sieciowego**| Reguły umożliwiają ustawianie protokołów, portów lokalnych i zdalnych oraz zakresów adresów, które mają zostać włączone dla połączenia sieci VPN. Jeśli nie utworzysz reguły ruchu sieciowego, wszystkie protokoły, porty i zakresy adresów zostaną włączone. Po utworzeniu reguły tylko protokoły, porty i zakresy adresów wybrane w tej regule lub regułach dodatkowych będą używane przez połączenie VPN.
**Trasy**|Trasy do użycia przez połączenie sieci VPN.
**Serwery DNS**| Serwery DNS używane przez połączenie VPN po jego nawiązaniu.         
**Skojarzone aplikacje**     | Możesz podać listę aplikacji, które będą automatycznie korzystać z połączenia VPN. Typ aplikacji określa identyfikator aplikacji. W przypadku aplikacji uniwersalnych podaj nazwę rodziny pakietów, a w przypadku aplikacji klasycznych podaj ścieżkę pliku aplikacji.          


> [!IMPORTANT] Zalecamy zabezpieczenie wszystkich list aplikacji kompilowanych do użytku w konfiguracji sieci VPN aplikacji. Jeśli nieautoryzowany użytkownik zmodyfikuje listę, po czym zaimportujesz listę do sieci VPN aplikacji, możesz potencjalnie autoryzować dostęp za pośrednictwem sieci VPN do aplikacji, które nie powinny mieć dostępu. Jednym ze sposobów na zabezpieczenie listy aplikacji jest użycie listy kontroli dostępu (ACL).

Oto przykład sytuacji, w której można zastosować ustawień granic firmowych. Aby dla pulpitu zdalnego włączyć tylko sieć VPN, należy utworzyć regułę ruchu sieciowego umożliwiającą ruch protokołu numer 27 w porcie zewnętrznym 3996. Sieć VPN nie będzie używana w przypadku pozostałego ruchu.

Definiowanie tras w ramach granic firmowych jest przydatne, jeśli typ połączenia VPN nie zezwala na określanie sposobu obsługi ruchu w przypadku tunelowania podzielonego. W takiej sytuacji do utworzenia listy tras, na których będzie używana sieć VPN, należy użyć ustawienia **Trasy**.

Tworząc niestandardową wartość ustawienia OMA-URI, można ograniczyć użycie sieci VPN na urządzeniu z systemem Windows 10 do określonych aplikacji.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady** .

## Wdrażanie zasad

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycję **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — wybierz pozycję **Anuluj**.


Po pomyślnym wdrożeniu użytkownicy będą widzieli wprowadzoną przez Ciebie nazwę połączenia VPN na liście połączeń VPN na swoich urządzeniach.

W podsumowaniu stanu i alertach na stronie **Przegląd** obszaru roboczego **Zasady** są pokazane problemy z zasadami, które wymagają Twojej uwagi. Ponadto w obszarze roboczym Pulpit nawigacyjny jest wyświetlane podsumowanie stanu.

### Zobacz także
[Konfiguracje niestandardowe dla profilów sieci VPN](Custom-configurations-for-VPN-profiles.md)
[Sieć VPN dla aplikacji systemu Android korzystających z połączenia Pulse Secure](per-app-vpn-for-android-pulse-secure.md)



<!--HONumber=Jul16_HO3-->


