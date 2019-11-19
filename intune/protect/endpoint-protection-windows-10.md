---
title: Ustawienia ochrony dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Na urządzeniach z systemem Windows 10 możesz użyć ustawień programu Endpoint Protection lub skonfigurować je, aby włączyć w usłudze Microsoft Intune usługę Microsoft Defender, w tym program Application Guard, zaporę, filtr SmartScreen, szyfrowanie i funkcję BitLocker, program Exploit Guard, kontrolę aplikacji, Centrum zabezpieczeń i zabezpieczenia na urządzeniach lokalnych.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: karthig
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e2909e7ad1ced9483a6cec58f1f3009f56946f5f
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74058424"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Ustawienia systemu Windows 10 (oraz nowszych wersji) służące do ochrony urządzeń przy użyciu usługi Intune

Usługa Microsoft Intune zawiera wiele ustawień pomocnych w ochronie urządzeń. W tym artykule opisano wszystkie ustawienia, które można włączyć i skonfigurować na urządzeniach z systemem Windows 10 lub nowszym. Te ustawienia są tworzone w profilu konfiguracji ochrony punktu końcowego w usłudze Intune w celu sterowania zabezpieczeniami i obejmują m.in. funkcję BitLocker i usługę Microsoft Defender.  

Aby skonfigurować program antywirusowy Microsoft Defender, zobacz [Ograniczenia dotyczące urządzeń z systemem Windows 10](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).  

## <a name="before-you-begin"></a>Przed rozpoczęciem  

[Utwórz profil konfiguracji urządzenia ochrony punktu końcowego](endpoint-protection-configure.md).  

Aby uzyskać więcej informacji o dostawcach usług konfiguracji (CSP), zobacz [Dokumentacja dostawcy usług konfiguracji](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).  

## <a name="microsoft-defender-application-guard"></a>Ochrona aplikacji w programie Microsoft Defender  

Podczas korzystania z przeglądarki Microsoft Edge program Microsoft Defender Application Guard chroni Twoje środowisko przed witrynami, które nie zostały uznane za zaufane przez Twoją organizację. Gdy użytkownicy odwiedzają witryny, które nie zostały wymienione w granicach sieci izolowanej, witryny te są otwierane w ramach sesji przeglądania wirtualnego funkcji Hyper-V. Witryny są definiowane przez granicę sieci, która jest konfigurowana w konfiguracji urządzenia.  

Funkcja Application Guard jest dostępna tylko dla urządzeń z systemem Windows 10 (wersja 64-bitowa). Użycie tego profilu powoduje zainstalowanie składnika Win32 w celu aktywowania funkcji Application Guard.  

- **Application Guard**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca usług kryptograficznych funkcji Application Guard: [Settings/AllowWindowsDefenderApplicationGuard](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#allowwindowsdefenderapplicationguard)  

  - **Włączone dla usługi Edge** — włącza tę funkcję, która otwiera niezaufane witryny w zwirtualizowanym kontenerze przeglądania funkcji Hyper-V.  
  - **Nieskonfigurowane** — na urządzeniu mogą zostać otwarte wszystkie lokacje (zaufane i niezaufane).  

- **Zachowanie schowka**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca usług kryptograficznych funkcji Application Guard: [Settings/ClipboardSettings](https://go.microsoft.com/fwlink/?linkid=872351)  

  Wybierz dozwolone akcje kopiowania i wklejania między komputerem lokalnym a przeglądarką wirtualną funkcji Application Guard.  
  - **Nieskonfigurowany**  
  - **Zezwalaj na kopiowanie i wklejanie tylko z komputera do przeglądarki**  
  - **Zezwalaj na kopiowanie i wklejanie tylko z przeglądarki do komputera**  
  - **Zezwalaj na kopiowanie i wklejanie między komputerem a przeglądarką**  
  - **Blokuj kopiowanie i wklejanie między komputerem a przeglądarką**  

- **Zawartość schowka**  
  To ustawienie jest dostępne tylko wtedy, gdy *zachowanie schowka* jest ustawione na jedno z ustawień *Zezwalaj* .  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych funkcji Application Guard: [Settings/ClipboardFileType](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#clipboardfiletype)  

  Wybierz dozwoloną zawartość schowka.  
  - **Nieskonfigurowany**  
  - **Tekst**  
  - **Obrazy**  
  - **Tekst i obrazy**  

- **Zawartość zewnętrzna w witrynach przedsiębiorstw**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych funkcji Application Guard: [Settings/BlockNonEnterpriseContent](https://go.microsoft.com/fwlink/?linkid=872352)  

  - **Blokuj** — ładowanie zawartości z niezatwierdzonych witryn internetowych jest blokowane.  
  - **Nie skonfigurowano** — na urządzeniu będzie można otwierać witryny inne niż witryny przedsiębiorstw.  
 
- **Drukuj z przeglądarki wirtualnej**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych funkcji Application Guard: [Settings/PrintingSettings](https://go.microsoft.com/fwlink/?linkid=872354)  

  - **Zezwalaj** — umożliwia drukowanie wybranej zawartości z poziomu przeglądarki wirtualnej.  
  - **Nie skonfigurowano** Wyłącz wszystkie funkcje drukowania.  

  Po *umożliwieniu* drukowania można skonfigurować następujące ustawienie:
  - **Typy drukowania** Wybierz co najmniej jedną z następujących opcji:  
    - PDF  
    - XPS  
    - Drukarki lokalne
    - Drukarki sieciowe  

- **Zbieraj dzienniki**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji Application Guard: [Audit/AuditApplicationGuard](https://go.microsoft.com/fwlink/?linkid=872418)  

  - **Zezwalaj** — zbieranie dzienników dla zdarzeń występujących w sesji przeglądania funkcji Application Guard.  
  - **Nie skonfigurowano** — żadne dzienniki w sesji przeglądania nie są zbierane.  

- **Zachowuj dane przeglądarki generowane przez użytkownika**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych funkcji Application Guard: [Settings/AllowPersistence](https://go.microsoft.com/fwlink/?linkid=872419)  

  - **Zezwalaj** — zezwalanie na zapisywanie danych użytkownika (na przykład haseł, ulubionych i plików cookie) utworzonych podczas wirtualnej sesji przeglądania funkcji Application Guard.  
  - **Nie skonfigurowano** — odrzucanie plików i danych pobranych przez użytkownika przy ponownym uruchomieniu urządzenia lub gdy użytkownik wylogowuje się.  

- **Przyspieszanie grafiki**  
 **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych funkcji Application Guard: [Settings/AllowVirtualGPU](https://go.microsoft.com/fwlink/?linkid=872420)  
      
  - **Włącz** — szybsze ładowanie witryn internetowych z dużą ilością grafiki oraz wideo dzięki dostępowi do wirtualnego procesora GPU.  
  - **Nie skonfigurowano** Użyj procesora CPU urządzenia do grafiki; Nie używaj wirtualnej jednostki przetwarzania grafiki.  

- **Pobierz pliki do systemu plików hosta**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych funkcji Application Guard: [Settings/SaveFilesToHost](https://go.microsoft.com/fwlink/?linkid=872421)  

  - **Włącz** — użytkownicy mogą pobierać pliki ze zwirtualizowanej przeglądarki do systemu operacyjnego hosta.  
  - **Nie skonfigurowano** — przechowywanie plików lokalnie na urządzeniu, pliki nie są pobierane do systemu plików hosta.  

## <a name="microsoft-defender-firewall"></a>Zapora Microsoft Defender  
 
### <a name="global-settings"></a>Ustawienia globalne  

Te ustawienia mają zastosowanie do wszystkich typów urządzeń.  

- **Protokół transferu plików**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca CSP zapory: [MdmStore/Global/DisableStatefulFtp](https://go.microsoft.com/fwlink/?linkid=872536)  

  - **Blokuj** — wyłączenie stanowego protokołu FTP.  
  - **Nie skonfigurowano** — zapora wykonuje filtrowanie stanowego protokołu FTP, aby zezwalać na dodatkowe połączenia.  

- **Czas bezczynności skojarzeń zabezpieczeń przed usunięciem**  
  **Domyślne**: *Nieskonfigurowane*  
   Dostawca CSP zapory: [MdmStore/Global/SaIdleTime](https://go.microsoft.com/fwlink/?linkid=872539)  

   Określ czas bezczynności (w sekundach), po którym skojarzenia zabezpieczeń zostaną usunięte.   

- **Kodowanie kluczy wstępnych**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca CSP zapory: [MdmStore/Global/PresharedKeyEncoding](https://go.microsoft.com/fwlink/?linkid=872541)  

   - **Włącz funkcję** -Koduj wstępnie pochylania klucze przy użyciu kodowania UTF-8.  
   - **Nie skonfigurowano** — Koduj wstępnie pochylania klucze przy użyciu wartości lokalnego magazynu.  

- **Wykluczenia IPsec**  
  **Wartość domyślna**: *0 wybrana*  
   Dostawca CSP zapory: [MdmStore/Global/IPsecExempt](https://go.microsoft.com/fwlink/?linkid=872547)

   Wybierz co najmniej jeden z następujących typów ruchu, który ma zostać wykluczony z protokołu IPsec:  
   - **Odnajdywanie sąsiadujących kodów typu IPv6 protokołu ICMP**  
   - **Protokół ICMP**  
   - **Odnajdywanie routera kodów typu IPv6 protokołu ICMP**  
   - **Ruch sieciowy DHCP IPv4 i IPv6**  

- **Weryfikacja listy odwołania certyfikatów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [MdmStore/Global/CRLcheck](https://go.microsoft.com/fwlink/?linkid=872548)  

  Wybierz, jak urządzenie weryfikuje listę odwołania certyfikatów. Dostępne opcje:  
  - **Wyłącz weryfikację listy CRL**  
  - **Sprawdzanie poprawności listy CRL nie powiodło się tylko dla odwołanego certyfikatu**  
  - **Sprawdzanie poprawności listy CRL nie powiodło się w przypadku napotkanego błędu**.  
 

- **Odpowiednio uzgodnij zestaw uwierzytelniania dla modułu kluczy**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [MdmStore/Global/OpportunisticallyMatchAuthSetPerKM](https://go.microsoft.com/fwlink/?linkid=872550)  
  
  - **Włącz** — moduły kluczy muszą ignorować tylko te pakiety uwierzytelniania, których nie obsługują.  
  - **Nie skonfigurowano** — moduły kluczy muszą ignorować cały zestaw uwierzytelniania, jeśli nie obsługują wszystkich pakietów uwierzytelniania określonych w zestawie.  


- **Kolejkowanie pakietów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [MdmStore/Global/EnablePacketQueue](https://go.microsoft.com/fwlink/?linkid=872551)  

  Określ sposób włączania skalowania oprogramowania po stronie odbierającej w przypadku zaszyfrowanego odbierania i przekazywania w postaci zwykłego tekstu dla scenariusza z bramą tunelu IPsec. To ustawienie potwierdza zachowanie kolejności pakietów. Dostępne opcje:  
  - **Nieskonfigurowany**  
  - **Wyłącz całą usługę kolejkowania pakietów**  
  - **Kolejkowanie tylko szyfrowanych pakietów przychodzących**  
  - **Pakiety Queue po odszyfrowaniu są wykonywane tylko w celu przekazywania**  
  - **Skonfiguruj pakiety przychodzące i wychodzące**  

### <a name="network-settings"></a>Ustawienia sieciowe  

Poniższe ustawienia są wymienione w tym artykule pojedynczo, ale wszystkie dotyczą trzech określonych typów sieci:  
- **Sieć domeny (miejsce pracy)**  
- **Sieć prywatna (wykrywalna)**  
- **Sieć publiczna (niewykrywalna)**  

#### <a name="general-settings"></a>Ustawienia ogólne  

- **Zapora Microsoft Defender**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [EnableFirewall](https://go.microsoft.com/fwlink/?linkid=872558)  
  
  - **Włącz** — włączanie zapory i zabezpieczeń zaawansowanych. 
  - **Nie skonfigurowano** — zezwala na cały ruch sieciowy niezależnie od ustawień innych zasad.  

- **Tryb niewidzialności**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [DisableStealthMode](https://go.microsoft.com/fwlink/?linkid=872559)  
  - **Nieskonfigurowany**  
  - **Blokada** — Zapora nie działa w trybie niewidzialności. Blokowanie trybu niewidzialności pozwala również zablokować **wykluczanie pakietów zabezpieczonych przez protokół IPsec**.  
  - **Zezwalaj** — Zapora działa w trybie niewidzialności, co pomaga w zapobieganiu odpowiedzi na żądania sondowania.  

- **Wykluczanie pakietów zabezpieczonych przez protokół IPsec w trybie niewidzialności**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [DisableStealthModeIpsecSecuredPacketExemption](https://go.microsoft.com/fwlink/?linkid=872560)  

  Ta opcja jest ignorowana, jeśli *tryb niewidzialności* jest ustawiony na *Blokuj*.  

  - **Nieskonfigurowany**  
  - **Blokowanie** — zabezpieczone pakiety IPSec nie odbierają wykluczeń.  
  - **Zezwalaj** — Włącz wykluczenia. Tryb niewidzialności zapory nie może zapobiec odpowiedzi komputera hosta na niechciany ruch sieciowy zabezpieczony przez protokół IPsec.  

- **Z osłoną**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: z [osłoną](https://go.microsoft.com/fwlink/?linkid=872561)  
    - **Nieskonfigurowany**  
    - **Blokuj** — gdy Zapora Microsoft Defender jest włączona i to ustawienie ma wartość *Blokuj*, cały ruch przychodzący jest blokowany niezależnie od innych ustawień zasad. 
    - **Zezwalaj** — gdy jest ustawiony na *Zezwalaj*, to ustawienie jest wyłączone, a ruch przychodzący jest dozwolony na podstawie innych ustawień zasad.

- **Odpowiedzi emisji pojedynczej na multiemisję/emisje**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [DisableUnicastResponsesToMulticastBroadcast](https://go.microsoft.com/fwlink/?linkid=872562)  
  
  Zazwyczaj nie chcesz otrzymywać odpowiedzi emisji pojedynczej na komunikaty multiemisji lub emisji. Te odpowiedzi mogą wskazywać na atak typu „odmowa usługi” (DOS) lub na to, że osoba atakująca próbuje sondować znany komputer na żywo.  
  - **Nieskonfigurowany**  
  - **Blokuj** — nie zezwala na odpowiedzi emisji pojedynczej na emisje multiemisji.  
  - **Zezwalaj** — zezwala na odpowiedzi emisji pojedynczej na emisje multiemisji.  

- **Powiadomienia przychodzące**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [DisableInboundNotifications](https://go.microsoft.com/fwlink/?linkid=8725630)  

  - **Nieskonfigurowany**  
  - **Blokuj** — ukrywa powiadomienia do użycia, gdy aplikacja ma zablokowaną nasłuchiwanie na porcie.  
  - **Zezwalaj** — włącza to ustawienie i powiadomienia mogą być wyświetlane użytkownikom, gdy nasłuchiwanie przez aplikację na porcie jest zablokowane.  

- **Domyślna akcja dla połączeń przychodzących**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [DefaultOutboundAction](https://aka.ms/intune-firewall-outboundaction)  
  
  Skonfiguruj domyślne działanie zapory wykonywanej przez połączenia wychodzące. To ustawienie zostanie zastosowane do systemu Windows w wersji 1809 lub nowszej.  

  - **Nieskonfigurowany**  
  - **Block** — domyślna akcja zapory nie jest uruchamiana dla ruchu wychodzącego, chyba że jest jawnie określona jako nieblokująca.  
  - **Zezwalaj** — domyślne akcje zapory są uruchamiane dla połączeń wychodzących.  

- **Domyślna akcja dla połączeń przychodzących**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [DefaultInboundAction](https://go.microsoft.com/fwlink/?linkid=872564)  
 
  - **Nieskonfigurowany**  
  - **Blokuj** — domyślna akcja zapory nie jest uruchamiana dla połączeń przychodzących.  
  - **Zezwalaj** — domyślne akcje zapory są uruchamiane dla połączeń przychodzących.  

#### <a name="rule-merging"></a>Scalanie reguł  

- **Reguły zapory Microsoft Defender autoryzowanych aplikacji z magazynu lokalnego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [AuthAppsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872565)  

  - **Nieskonfigurowany**  
  - **Blokuj** — reguły zapory autoryzowanych aplikacji w magazynie lokalnym są ignorowane i nie są wymuszane.  
  - **Zezwalaj** — -
   wybierz pozycję **Włącz**, aby zastosować reguły zapory w magazynie lokalnym w celu ich rozpoznawania i wymuszania.  

- **Globalne reguły zapory Microsoft Defender portów z magazynu lokalnego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [GlobalPortsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872566)  

  - **Nieskonfigurowany**  
  - **Block** — reguły zapory portu globalnego w magazynie lokalnym są ignorowane i nie są wymuszane.  
  - **Zezwalaj** — stosowanie globalnych reguł zapory portów w magazynie lokalnym w celu rozpoznawania i wymuszania.  

- **Reguły zapory Microsoft Defender z magazynu lokalnego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [AllowLocalPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872567)  

  - **Nieskonfigurowany**  
  - Reguły zapory **blokowej** z lokalnego magazynu są ignorowane i nie są wymuszane.
  - **Zezwalaj** — stosowanie reguł zapory w magazynie lokalnym w celu rozpoznawania i wymuszania.  

- **Reguły protokołu IPsec z magazynu lokalnego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [AllowLocalIpsecPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872568)  

  - **Nieskonfigurowany**  
  - **Blokuj** — reguły zabezpieczeń połączeń z magazynu lokalnego są ignorowane i nie są wymuszane, niezależnie od wersji reguł zabezpieczeń schematu lub połączenia.  
  - **Zezwalaj** — stosowanie reguł zabezpieczeń połączeń z magazynu lokalnego, niezależnie od wersji reguł zabezpieczeń schematu lub połączenia.  

### <a name="firewall-rules"></a>Reguły zapory  

Można **dodać** co najmniej jedną niestandardową regułę zapory. Aby uzyskać więcej informacji, zobacz [Dodawanie niestandardowych reguł zapory dla urządzeń z systemem Windows 10](endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices).  

Niestandardowe reguły zapory obsługują następujące opcje:  

#### <a name="general-settings"></a>Ustawienia ogólne:  

- **Nazwa**  
  **Wartość domyślna**: *Brak nazwy*  

  Określ przyjazną nazwę dla reguły. Ta nazwa zostanie wyświetlona na liście reguł, aby ułatwić jej identyfikację.  

- **Opis**  
  **Wartość domyślna**: *Brak opisu*  

  Podaj opis reguły.  

- **Kierunek**   
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/Direction](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#direction)  
  
  Określ, czy ta reguła ma zastosowanie do ruchu **przychodzącego**, czy **wychodzącego** . Gdy ustawienie ustawiono jako **Nieskonfigurowane**, reguła automatycznie stosuje się do ruchu wychodzącego.  

- **Akcja**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/Action](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#action)i [FirewallRules/*FirewallRuleName*/Action/Type](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#type)  

  Wybierz pozycję **Zezwalaj** lub **Blokuj**. Po ustawieniu jako **Nieskonfigurowane**, reguła domyślnie zezwala na ruch.  

- **Typ sieci**  
  **Wartość domyślna**: 0 wybrana  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/Profiles](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#profiles)  

  Wybierz do trzech typów sieci, do których należy ta reguła. Dostępne opcje to **domena**, **prywatne**i **publiczne**.  Jeśli nie wybrano żadnych typów sieci, reguła dotyczy wszystkich trzech typów sieci.  

#### <a name="application-settings"></a>Ustawienia aplikacji  

- **Aplikacje**  
  **Wartość domyślna**: Wszystkie  

  Kontrolowanie połączeń dla aplikacji lub programu. Wybierz jedną z następujących opcji, a następnie wykonaj dodatkową konfigurację:  
  - **Nazwa rodziny pakietów** — Podaj nazwę rodziny pakietów. Aby znaleźć nazwę rodziny pakietów, użyj polecenia programu PowerShell **Get-AppxPackage**.   
    Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/App/PackageFamilyName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#packagefamilyname)  
 
  - **Ścieżka pliku** — należy określić ścieżkę pliku do aplikacji na urządzeniu klienckim, która może być ścieżką bezwzględną lub ścieżką względną. Na przykład: C:\Windows\System\Notepad.exe lub%WINDIR%\Notepad.exe.  
    Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/App/FilePath](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#filepath)  

  - **Usługa systemu Windows** — Określ krótką nazwę usługi systemu Windows, jeśli jest to usługa, a nie aplikacja, która wysyła lub odbiera ruch. Aby znaleźć krótką nazwę usługi, należy użyć polecenia programu PowerShell **Get-Service**.  
    Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/App/ServiceName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#servicename)  

  - **Wszystkie**— *żadna dodatkowa konfiguracja nie jest dostępna*.  

#### <a name="ip-address-settings"></a>Ustawienia adresu IP  

Określ adresy lokalne i zdalne, do których zostanie zastosowana ta reguła.  

- **Adresy lokalne**    
  **Wartość domyślna**: dowolny adres  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  

  Wybierz **dowolny adres** lub **określony adres**.  

  W przypadku użycia *określonego adresu*należy dodać jeden lub więcej adresów jako listę adresów lokalnych rozdzielonych przecinkami, które są objęte regułą. Prawidłowe tokeny obejmują:  
  - Użyj gwiazdki "*" dla *dowolnego* adresu lokalnego. Jeśli używasz gwiazdki, musi to być jedyny używany token.  
  - Aby określić podsieć, użyj notacji z maską podsieci lub prefiksem sieci. Jeśli nie zostanie określona ani maska podsieci, ani prefiks sieci, domyślnie maska podsieci to 255.255.255.255.  
  - Prawidłowy adres IPv6.  
  - Zakres adresów IPv4 w formacie "początkowy adres-adres końcowy" bez uwzględniających spacji.  
  - Zakres adresów IPv6 w formacie "początkowy adres-adres końcowy" bez uwzględniających spacji.  

- **Adresy zdalne**  
  **Wartość domyślna**: dowolny adres  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/RemoteAddressRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteaddressranges)  
 
  Wybierz **dowolny adres** lub **określony adres**.  

  W przypadku użycia *określonego adresu*należy dodać jeden lub więcej adresów jako listę adresów zdalnych rozdzielonych przecinkami, które są objęte regułą. W tokenach nie jest rozróżniana wielkość liter. Prawidłowe tokeny obejmują:  
  - Użyj gwiazdki "*" dla *dowolnego* adresu zdalnego. Jeśli używasz gwiazdki, musi to być jedyny używany token.  
  - "Defaultgateway"  
  - "DHCP"  
  - "DNS"  
  - "WINS"  
  - "Intranet" (obsługiwany w systemie Windows w wersji 1809 i nowszych)  
  - "RmtIntranet" (obsługiwane w systemie Windows w wersji 1809 i nowszych)  
  - "Internet" (obsługiwane w systemie Windows w wersji 1809 i nowszych)  
  - "Ply2Renders" (obsługiwane w systemie Windows w wersji 1809 i nowszych)  
  - "LocalSubnet" wskazuje dowolny adres lokalny w podsieci lokalnej.  
  - Aby określić podsieć, użyj notacji z maską podsieci lub prefiksem sieci. Jeśli nie zostanie określona ani maska podsieci, ani prefiks sieci, domyślnie maska podsieci to 255.255.255.255.  
  - Prawidłowy adres IPv6.  
  - Zakres adresów IPv4 w formacie "początkowy adres-adres końcowy" bez uwzględniających spacji.  
  - Zakres adresów IPv6 w formacie "początkowy adres-adres końcowy" bez uwzględniających spacji.  

#### <a name="port-and-protocol-settings"></a>Ustawienia portów i protokołów  
Określ porty lokalne i zdalne, do których zostanie zastosowana ta reguła.  

- **Protokół**  
  **Wartość domyślna**: dowolne  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/Protocol](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#protocol)  
  Wybierz jedną z następujących opcji i wykonaj wszystkie wymagane konfiguracje:  
  - **Wszystkie** — żadna dodatkowa konfiguracja nie jest dostępna.  
  - **TCP** — Konfigurowanie portów lokalnych i zdalnych. Obie opcje obsługują wszystkie porty lub określone porty. Wprowadź określone porty przy użyciu listy rozdzielanej przecinkami.  
    - **Porty lokalne** — dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Porty zdalne** — dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/RemotePortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **UDP** — Konfigurowanie portów lokalnych i zdalnych. Obie opcje obsługują wszystkie porty lub określone porty. Wprowadź określone porty przy użyciu listy rozdzielanej przecinkami.  
    - **Porty lokalne** — dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Porty zdalne** — dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/RemotePortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **Niestandardowy** — Określ niestandardowy numer **protokołu** z prze255.  

#### <a name="advanced-configuration"></a>Konfiguracja zaawansowana  
- **Typy interfejsów**  
  **Wartość domyślna**: 0 wybrana  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/InterfaceTypes](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#interfacetypes)  

  Wybierz jedną z następujących opcji:  
  - **Dostęp zdalny**  
  - **Sieć bezprzewodowa**  
  - **Sieć lokalna**  

- **Zezwalaj tylko na połączenia od tych użytkowników**  
  **Domyślnie**: Wszyscy użytkownicy *(domyślnie są używane, gdy nie określono listy)*  
  Dostawca CSP zapory: [FirewallRules/*FirewallRuleName*/LocalUserAuthorizationList](https://aka.ms/intunefirewallauthorizedusers)  

  Określ listę autoryzowanych użytkowników lokalnych dla tej reguły. Nie można określić listy autoryzowanych użytkowników, jeśli ta reguła ma zastosowanie do usługi systemu Windows.  


## <a name="microsoft-defender-smartscreen-settings"></a>Ustawienia filtru Microsoft Defender SmartScreen  
 
Na urządzeniu musi być zainstalowana przeglądarka Microsoft Edge.  

- **Filtr SmartScreen dla aplikacji i plików**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca usług kryptograficznych SmartScreen: [SmartScreen/EnableSmartScreenInShell](https://go.microsoft.com/fwlink/?linkid=872784)  

  - **Nieskonfigurowane** — wyłącza korzystanie z filtru SmartScreen.  
  - **Włącz** — włącza filtr Windows SmartScreen na potrzeby wykonywania plików i uruchamiania aplikacji. Filtr SmartScreen jest opartym na chmurze składnikiem chroniącym przed wyłudzaniem informacji i złośliwym oprogramowaniem.  

- **Wykonywanie niezweryfikowanych plików**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca usług kryptograficznych SmartScreen: [SmartScreen/PreventOverrideForFilesInShell](https://go.microsoft.com/fwlink/?linkid=872783)

  - **Nie skonfigurowano** — powoduje wyłączenie tej funkcji i umożliwia użytkownikom końcowym uruchamianie plików, które nie zostały zweryfikowane.  
  - **Blokuj** — blokowanie użytkownikom końcowym możliwości uruchamiania plików, które nie zostały zweryfikowane przez filtr Windows SmartScreen.  

## <a name="windows-encryption"></a>Szyfrowanie systemu Windows  
 
### <a name="windows-settings"></a>Ustawienia systemu Windows  

- **Szyfruj urządzenia**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [RequireDeviceEncryption](https://go.microsoft.com/fwlink/?linkid=872523)  

  - **Wymagaj** — użytkownicy są monitowani o włączenie szyfrowania urządzenia. W zależności od wersji systemu Windows i konfiguracji systemu użytkownikom może być wyświetlany jeden z następujących monitów:  
    - Monit o potwierdzenie, że nie włączono szyfrowania od innego dostawcy.  
    - Monit o wyłączenie szyfrowania dysków funkcją BitLocker, a następnie ponowne włączenie funkcji BitLocker.  
  - **Nieskonfigurowany**  
  
  Jeśli szyfrowanie systemu Windows jest włączone, gdy inna metoda szyfrowania jest aktywna, urządzenie może pracować niestabilnie.  

- **Szyfruj kartę pamięci (tylko na urządzeniach przenośnych)**  
  *To ustawienie dotyczy tylko urządzeń z systemem Windows 10 Mobile.*  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [RequireStorageCardEncryption](https://go.microsoft.com/fwlink/?linkid=872524)  

  - **Wymagaj** — wymagane będzie szyfrowanie wszystkich wymiennych kart pamięci używanych przez urządzenie.  
  - **Nie skonfigurowano** — nie wymaga szyfrowania karty pamięci i nie monituje użytkownika o włączenie szyfrowania.  

### <a name="bitlocker-base-settings"></a>Podstawowe ustawienia funkcji BitLocker  

Podstawowe ustawienia to uniwersalne ustawienia funkcji BitLocker dla wszystkich typów dysków danych. Te ustawienia zarządzają zadaniami szyfrowania dysku lub opcjami konfiguracji, które użytkownik końcowy może modyfikować w przypadku wszystkich typów dysków z danymi.  

- **Ostrzeżenie dotyczące innego szyfrowania dysku**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [AllowWarningForOtherDiskEncryption](https://go.microsoft.com/fwlink/?linkid=872525)  

  - **Blokuj** — wyłączenie ostrzeżenia dotyczącego używania innej usługi szyfrowania dysku na urządzeniu.  
  - **Nieskonfigurowane** — umożliwia wyświetlenie ostrzeżenia o innym szyfrowaniu dysków.  

  Po wybraniu opcji *Blokuj*można skonfigurować następujące ustawienie:  

  - **Zezwalaj użytkownikom standardowym na włączanie szyfrowania podczas dołączania do usługi Azure AD**  
    *To ustawienie dotyczy tylko Azure Active Directory urządzeń przyłączonych (Azure PRZYMIOTNIK) i zależy od poprzedniego ustawienia, `Warning for other disk encryption`.*  
    **Domyślnie**: Nie skonfigurowano  
    Dostawca CSP funkcji BitLocker: [AllowStandardUserEncryption](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowstandarduserencryption)

     - **Zezwalaj** — użytkownicy standardowi (inni niż administratorzy) mogą włączyć szyfrowanie funkcji BitLocker podczas logowania.  
     - **Nie skonfigurowano** — tylko administratorzy mogą włączyć szyfrowanie przy użyciu funkcji BitLocker na urządzeniu.  

- **Konfiguruj metody szyfrowania**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [EncryptionMethodByDriveType](https://go.microsoft.com/fwlink/?linkid=872526)  

  - **Włącz** — konfigurowanie algorytmów szyfrowania na potrzeby systemu operacyjnego, danych i dysków wymiennych.  
  - **Nie skonfigurowano** — funkcja BitLocker używa 128-bitowego szyfrowania XTS-AES jako domyślnej metody szyfrowania lub używa metody szyfrowania określonej przez dowolny skrypt instalacji.  

  W przypadku ustawienia pozycji *Włącz* można skonfigurować następujące ustawienia:  

  - **Szyfrowanie dla dysków z systemami operacyjnymi**  
    **Domyślnie**: XTS-AES 128-bit  
   
    Wybierz metodę szyfrowania dla dysków z systemami operacyjnymi. Zaleca się użycie algorytmu XTS-AES.  
    - **AES-CBC 128-bit**  
    - **AES-CBC 256-bit**  
    - **XTS-AES 128-bit**  
    - **XTS-AES 256-bit**  

  - **Szyfrowanie dla stałych dysków danych**  
    **Domyślnie**: AES-CBC 128-bit  
   
    Wybierz metodę szyfrowania dla stałych (wbudowanych) dysków danych. Zaleca się użycie algorytmu XTS-AES.  
    - **AES-CBC 128-bit**  
    - **AES-CBC 256-bit**  
    - **XTS-AES 128-bit**  
    - **XTS-AES 256-bit**  

  - **Szyfrowanie dla wymiennych dysków danych**  
    **Domyślnie**: AES-CBC 128-bit  

    Wybierz metodę szyfrowania dla wymiennych dysków danych. Jeśli dysk wymienny jest używany z urządzeniami z systemem innym niż Windows 10, zaleca się użycie algorytmu AES-CBC.  
    - **AES-CBC 128-bit**  
    - **AES-CBC 256-bit**  
    - **XTS-AES 128-bit**  
    - **XTS-AES 256-bit**  

### <a name="bitlocker-os-drive-settings"></a>Ustawienia funkcji BitLocker dla dysku z systemem operacyjnym  

Te ustawienia dotyczą w szczególności dysków danych systemu operacyjnego.  

- **Dodatkowe uwierzytelnianie podczas uruchamiania**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [SystemDrivesRequireStartupAuthentication](https://go.microsoft.com/fwlink/?linkid=872527)  

  - **Wymagaj** — konfigurowanie wymagań dotyczących uwierzytelniania na potrzeby uruchamiania komputera, w tym użycia modułu TPM (Trusted Platform Module).  
  - **Nieskonfigurowane** — Skonfiguruj tylko podstawowe opcje na urządzeniach z modułem TPM.  

  W przypadku ustawienia pozycji *Wymagaj* można skonfigurować następujące ustawienia:  

  - **Funkcja BitLocker z niezgodnym mikroukładem modułu TPM**  
    **Domyślnie**: Nie skonfigurowano  

    - **Blokuj** — wyłączanie używania funkcji BitLocker, gdy urządzenie nie ma zgodnego mikroukładu modułu TPM.  
    - **Nie skonfigurowano** — użytkownicy mogą używać funkcji BitLocker bez zgodnego mikroukładu modułu TPM. Funkcja BitLocker może wymagać hasła lub klucza uruchomienia.  

  - **Uruchamianie zgodnego modułu TPM**  
    **Domyślnie**: Zezwalaj na moduł TPM  

    Skonfiguruj, czy moduł TPM jest dozwolony, wymagany, czy niedozwolony.  

    - **Zezwalaj na moduł TPM**  
    - **Nie zezwalaj na moduł TPM**  
    - **Wymagaj modułu TPM**  

  - **Numer PIN uruchomienia zgodnego modułu TPM**  
    **Domyślnie**: Zezwalaj na numer PIN uruchomienia z modułem TPM  

    Wybierz opcję zezwalania, blokowania lub wymagania numeru PIN podczas uruchamiania mikroukładu modułu TPM. Włączenie numeru PIN uruchomienia wymaga interakcji użytkownika końcowego.  

    - **Zezwalaj na numer PIN uruchomienia z modułem TPM**  
    - **Nie Zezwalaj na numer PIN uruchomienia z modułem TPM**  
    - **Wymagaj numeru PIN uruchomienia z modułem TPM**

  - **Klucz uruchomienia zgodnego modułu TPM**  
    **Domyślne**: Zezwalaj na klucz uruchomienia z modułem TPM  

    Wybierz opcję zezwalania, blokowania lub wymagania klucza podczas uruchamiania mikroukładu modułu TPM. Włączenie klucza uruchomienia wymaga interakcji użytkownika końcowego.  

    - **Zezwalaj na klucz uruchomienia z modułem TPM**  
    - **Nie Zezwalaj na klucz uruchomienia z modułem TPM**  
    - **Wymagaj klucza uruchomienia z modułem TPM**  

  - **Klucz uruchomienia i numer PIN zgodnego modułu TPM**  
    **Domyślne**: Zezwalaj na klucz uruchomienia i numer PIN z modułem TPM  

    Wybierz opcję zezwalania, blokowania lub wymagania klucza i numeru PIN uruchamiania dla mikroukładu modułu TPM. Włączenie klucza i numeru PIN uruchomienia wymaga interakcji użytkownika końcowego.  
    - **Zezwalaj na klucz uruchomienia i numer PIN z modułem TPM**  
    - **Nie Zezwalaj na klucz uruchomienia i numer PIN z modułem TPM**  
    - **Wymagaj klucza uruchomienia i numeru PIN z modułem TPM**   

- **Minimalna długość numeru PIN**  
    **Domyślnie**: Nie skonfigurowano  
    Dostawca CSP funkcji BitLocker: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)   

    - **Włącz** Skonfiguruj minimalną długość numeru PIN uruchomienia modułu TPM.  
    - **Nie skonfigurowano** — użytkownicy mogą skonfigurować kod PIN uruchamiania o dowolnej długości od 6 do 20 cyfr.  

  Po ustawieniu pozycji *Włącz* można skonfigurować następujące ustawienie:  

  - **Minimalna liczba znaków**  
    **Domyślnie**: *nie skonfigurowano* dostawcy CSP funkcji BitLocker: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)  

    Wprowadź liczbę znaków wymaganą dla numeru PIN uruchomienia z przedziału **4**-**20**.  

- **Odzyskiwanie dysku systemu operacyjnego**  
  **Domyślnie**: Nie skonfigurowano   
  Dostawca CSP funkcji BitLocker: [SystemDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872529)  

  - **Włącz** — określenie sposobu odzyskiwania dysków z systemem operacyjnym chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.  
  - **Nie skonfigurowano** — obsługiwane są domyślne opcje odzyskiwania w przypadku odzyskiwania funkcji BitLocker. Domyślnie agent DRA jest dozwolony, opcje odzyskiwania, w tym hasło odzyskiwania i klucz odzyskiwania, są wybierane przez użytkownika, i nie jest tworzona kopia zapasowa informacji odzyskiwania w usługach AD DS.  

  W przypadku ustawienia pozycji *Włącz* można skonfigurować następujące ustawienia:  

  - **Agent odzyskiwania danych oparty na certyfikatach**  
    **Domyślnie**: Nie skonfigurowano  
     
    - **Blokuj** — uniemożliwia korzystanie z agenta odzyskiwania danych z dyskami systemu operacyjnego chronionych przez funkcję BitLocker.  
    - **Nieskonfigurowane** — Zezwalanie na używanie agentów odzyskiwania danych z dyskami systemu operacyjnego chronionych przez funkcję BitLocker.  

  - **Tworzenie hasła odzyskiwania przez użytkownika**  
    **Wartość domyślna**: zezwalaj na 48-cyfrowe hasło odzyskiwania  

    Wybierz, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
    - **Zezwalaj na 48-cyfrowe hasło odzyskiwania**  
    - **Nie Zezwalaj na 48-cyfrowe hasło odzyskiwania**  
    - **Wymagaj 48-cyfrowego hasła odzyskiwania**  

  - **Tworzenie klucza odzyskiwania przez użytkownika**  
    **Wartość domyślna**: zezwalaj na 256-bitowy klucz odzyskiwania  

    Wybierz, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
    - **Zezwalaj na 256-bitowy klucz odzyskiwania**  
    - **Nie Zezwalaj na 256-bitowy klucz odzyskiwania**  
    - **Wymagaj 256-bitowego klucza odzyskiwania**  

  - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker**  
    **Domyślnie**: Nie skonfigurowano  

    - **Blokuj** — użytkownicy nie mogą wyświetlać ani zmieniać opcji odzyskiwania. Po ustawieniu na 
    - **Nie skonfigurowano** — użytkownicy mogą wyświetlać i zmieniać opcje odzyskiwania po włączeniu funkcji BitLocker. 
 
  - **Zapisz informacje odzyskiwania funkcji BitLocker w Azure Active Directory**  
    **Domyślnie**: Nie skonfigurowano  

    - **Włącz** — zapisuj informacje odzyskiwania funkcji BitLocker w usłudze Azure Active Directory (Azure AD).  
    - **Nie skonfigurowano** — informacje odzyskiwania funkcji BitLocker nie są przechowywane w usłudze AAD.  

  - **Informacje odzyskiwania funkcji BitLocker przechowywane w Azure Active Directory**  
    **Domyślnie**: Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy  

    Pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Azure AD. Wybierz spośród opcji:  
    - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**  
    - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**  

  - **Obrót hasła odzyskiwania opartego na kliencie**  
    **Wartość domyślna**: rotacja kluczy włączona dla urządzeń przyłączonych do usługi Azure AD  
    Dostawca CSP funkcji BitLocker: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    To ustawienie powoduje zainicjowanie rotacji hasła odzyskiwania opartego na kliencie po odzyskaniu dysku systemu operacyjnego (przy użyciu programu Bootmgr lub WinRE).  

    - Nieskonfigurowane  
    - Rotacja kluczy wyłączona  
    - Rotacja kluczy włączona dla usługi Azure AD — podłączona do ICES  
    - Rotacja kluczy włączona dla urządzeń z usługami Azure AD i hybrydowych  

  - **Przechowuj informacje dotyczące odzyskiwania w Azure Active Directory przed włączeniem funkcji BitLocker**  
    **Domyślnie**: Nie skonfigurowano  
 
     Uniemożliwiaj użytkownikom włączanie funkcji BitLocker, chyba że komputer pomyślnie tworzy kopię zapasową informacji odzyskiwania funkcji BitLocker do Azure Active Directory.  

    - **Wymagaj** — uniemożliwia użytkownikom włączenie funkcji BitLocker, chyba że informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Azure AD.  
    - **Nie skonfigurowano** — użytkownicy mogą włączać funkcję BitLocker, nawet jeśli informacje odzyskiwania nie zostały pomyślnie zapisane w usłudze Azure AD.  

- **Komunikat odzyskiwania i adres URL przed rozruchem**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [SystemDrivesRecoveryMessage](https://go.microsoft.com/fwlink/?linkid=872530)  

  - **Włącz** -Skonfiguruj komunikat i adres URL, które są wyświetlane na ekranie odzyskiwania klucza przed rozruchem.  
  - **Nie skonfigurowano** — ta funkcja jest wyłączana.  
  
  Po ustawieniu pozycji *Włącz* można skonfigurować następujące ustawienie:  
  - **Komunikat odzyskiwania przed rozruchem**  
    **Domyślnie**: Użyj domyślnego komunikatu i adresu URL dotyczącego odzyskiwania   
 
    Pozwala określić sposób wyświetlania użytkownikom komunikatu odzyskiwania przed rozruchem. Wybierz spośród opcji:  
    - **Użyj domyślnego komunikatu i adresu URL dotyczącego odzyskiwania**  
    - **Użyj pustego komunikatu i adresu URL dotyczącego odzyskiwania**  
    - **Użyj niestandardowego komunikatu dotyczącego odzyskiwania**  
    - **Użyj niestandardowego adresu URL odzyskiwania**  

### <a name="bitlocker-fixed-data-drive-settings"></a>Ustawienia stałych dysków danych w funkcji BitLocker  

Te ustawienia dotyczą wyłącznie stałych dysków danych.  

- **Dostęp do zapisu dla stałych dysków danych, które nie są chronione przez funkcję BitLocker**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [FixedDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872534)  

  - **Blokuj** — udzielenie dostępu tylko do odczytu do dysków danych, które nie są chronione przez funkcję BitLocker.  
  - **Nie skonfigurowano** — domyślnie dostęp do odczytu i zapisu do dysków danych, które nie są szyfrowane.  

- **Odzyskiwanie dysku stałego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [FixedDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872538)  

  - **Włącz** — określ sposób odzyskiwania dysków stałych chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.  
  - **Nie skonfigurowano** — ta funkcja jest wyłączana.  

  W przypadku ustawienia pozycji *Włącz* można skonfigurować następujące ustawienia:  

  - **Agent odzyskiwania danych**  
    **Domyślnie**: Nie skonfigurowano  
 
    - **Blokuj** — uniemożliwia używanie agenta odzyskiwania danych za pomocą edytora zasad dysków stałych chronionych przez funkcję BitLocker. 
    - **Nie skonfigurowano** — umożliwia używanie agentów odzyskiwania danych względem dysków stałych chronionych przez funkcję BitLocker.  

  - **Tworzenie hasła odzyskiwania przez użytkownika**  
    **Wartość domyślna**: zezwalaj na 48-cyfrowe hasło odzyskiwania  

    Wybierz, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
    - **Zezwalaj na 48-cyfrowe hasło odzyskiwania**  
    - **Nie Zezwalaj na 48-cyfrowe hasło odzyskiwania**  
    - **Wymagaj 48-cyfrowego hasła odzyskiwania**  

  - **Tworzenie klucza odzyskiwania przez użytkownika**  
    **Wartość domyślna**: zezwalaj na 256-bitowy klucz odzyskiwania

    Wybierz, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Zezwalaj na 256-bitowy klucz odzyskiwania**  
    - **Nie Zezwalaj na 256-bitowy klucz odzyskiwania**  
    - **Wymagaj 256-bitowego klucza odzyskiwania**  

  - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker**  
    **Domyślnie**: Nie skonfigurowano  

    - **Blokuj** — użytkownicy nie mogą wyświetlać ani zmieniać opcji odzyskiwania. Po ustawieniu na 
    - **Nie skonfigurowano** — użytkownicy mogą wyświetlać i zmieniać opcje odzyskiwania po włączeniu funkcji BitLocker.
 
  - **Zapisz informacje odzyskiwania funkcji BitLocker w Azure Active Directory**  
    **Domyślnie**: Nie skonfigurowano  

    - **Włącz** — zapisuj informacje odzyskiwania funkcji BitLocker w usłudze Azure Active Directory (Azure AD).  
    - **Nie skonfigurowano** — informacje odzyskiwania funkcji BitLocker nie są przechowywane w usłudze AAD.

  - **Informacje odzyskiwania funkcji BitLocker przechowywane w Azure Active Directory**  
    **Domyślnie**: Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy  

    Pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Azure AD. Wybierz spośród opcji:  
    - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**  
    - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**  

  - **Obrót hasła odzyskiwania opartego na kliencie**  
    **Wartość domyślna**: rotacja kluczy włączona dla urządzeń przyłączonych do usługi Azure AD  
    Dostawca CSP funkcji BitLocker: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    To ustawienie powoduje zainicjowanie rotacji hasła odzyskiwania opartego na kliencie po odzyskaniu dysku systemu operacyjnego (przy użyciu programu Bootmgr lub WinRE).  

    - Nieskonfigurowane  
    - Rotacja kluczy wyłączona  
    - Rotacja kluczy włączona dla usługi Azure AD — podłączona do ICES  
    - Rotacja kluczy włączona dla urządzeń z usługami Azure AD i hybrydowych  

  - **Przechowuj informacje dotyczące odzyskiwania w Azure Active Directory przed włączeniem funkcji BitLocker**  
    **Domyślnie**: Nie skonfigurowano  
 
    Uniemożliwiaj użytkownikom włączanie funkcji BitLocker, chyba że komputer pomyślnie tworzy kopię zapasową informacji odzyskiwania funkcji BitLocker do Azure Active Directory.  

    - **Wymagaj** — uniemożliwia użytkownikom włączenie funkcji BitLocker, chyba że informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Azure AD.  
    - **Nie skonfigurowano** — użytkownicy mogą włączać funkcję BitLocker, nawet jeśli informacje odzyskiwania nie zostały pomyślnie zapisane w usłudze Azure AD.  

### <a name="bitlocker-removable-data-drive-settings"></a>Ustawienia wymiennych dysków danych w funkcji BitLocker  

Te ustawienia są stosowane w odniesieniu do wymiennych dysków danych.  

- **Dostęp do zapisu dla wymiennych dysków danych, które nie są chronione przez funkcję BitLocker**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP funkcji BitLocker: [RemovableDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872540)  

  - **Blokuj** — udzielenie dostępu tylko do odczytu do dysków danych, które nie są chronione przez funkcję BitLocker.  
  - **Nie skonfigurowano** — domyślnie dostęp do odczytu i zapisu do dysków danych, które nie są szyfrowane.  

  Po ustawieniu pozycji *Włącz* można skonfigurować następujące ustawienie:  

  - **Dostęp do zapisu dla urządzeń skonfigurowanych w innej organizacji**  
    **Domyślnie**: Nie skonfigurowano  

    - **Blokuj** — blokowanie dostępu do zapisu dla urządzeń skonfigurowanych w innej organizacji.  
    - **Nie skonfigurowano** — Odmów dostępu do zapisu.  
 
## <a name="microsoft-defender-exploit-guard"></a>Microsoft Defender Exploit Guard  

Używaj [ochrony przed](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) atakami, aby zarządzać i zmniejszać podatność na ataki aplikacji używanych przez pracowników.  

### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków  

Reguły zmniejszenia obszaru ataków pomagają zapobiegać złośliwemu oprogramowaniu, które często używa złośliwego kodu.  

#### <a name="attack-surface-reduction-rules"></a>Reguły zmniejszenia obszaru ataków  

- **Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe)

  Ułatwia blokowanie akcji i aplikacji zwykle używanych przez złośliwe oprogramowanie wyszukujące luki w zabezpieczeniach do infekowania maszyn.  

  - **Nieskonfigurowany**  
  - **Włącz** — flagowanie kradzieży poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe).  
  - **Tylko inspekcja**  

- **Tworzenie procesów z poziomu programu Adobe Reader (beta)**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj tworzenie procesów podrzędnych przez program Adobe Reader](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-adobe-reader-from-creating-child-processes)  

  - **Nieskonfigurowany**  
  - **Włącz** -Blokuj procesy podrzędne tworzone z poziomu programu Adobe Reader.  
  - **Tylko inspekcja**  

#### <a name="rules-to-prevent-office-macro-threats"></a>Reguły zapobiegania zagrożeniom ze strony makr pakietu Office  

Zablokuj aplikacjom pakietu Office możliwość wykonywania następujących akcji:  

- **Wstrzykiwanie do innych procesów przez aplikacje pakietu Office (bez wyjątków)**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Uniemożliwiaj aplikacjom pakietu Office wstrzykiwanie kodu do innych procesów](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-applications-from-injecting-code-into-other-processes)  

  - **Nieskonfigurowany**  
  - Blokuj **blokowanie aplikacji** pakietu Office przed wprowadzaniem do innych procesów.  
  - **Tylko inspekcja**  

- **Tworzenie zawartości wykonywalnej przez makra i aplikacje pakietu Office**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Uniemożliwiaj aplikacjom pakietu Office tworzenie zawartości wykonywalnej](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-applications-from-creating-executable-content)  

  - **Nieskonfigurowany**  
  - Blokowanie **blokowania** przez aplikacje pakietu Office i makra do tworzenia zawartości wykonywalnej.  
  - **Tylko inspekcja**  

- **Uruchamianie procesów podrzędnych przez aplikacje pakietu Office**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Uniemożliwiaj aplikacjom pakietu Office tworzenie procesów podrzędnych](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-all-office-applications-from-creating-child-processes)  

  - **Nieskonfigurowany**  
  - Blokuj **blokowanie procesów** podrzędnych przez aplikacje pakietu Office.  
  - **Tylko inspekcja**  
  
- **Importowanie elementów Win32 z kodu makr w pakiecie Office**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj wywołania interfejsu API systemu Win32 z makr pakietu Office](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-win32-api-calls-from-office-macros)  

  - **Nieskonfigurowany**  
  - Blokuj **blokowanie** importów Win32 z kodu makr w pakiecie Office.  
  - **Tylko inspekcja**  
  
- **Tworzenie procesów z produktów komunikacyjnych pakietu Office**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj tworzenie procesów podrzędnych przez aplikację komunikacyjnej pakietu Office](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-communication-application-from-creating-child-processes)  

  - **Nieskonfigurowany**  
  - **Włącz** — Blokuj Tworzenie procesu podrzędnego z aplikacji komunikacyjnych pakietu Office.  
  - **Tylko inspekcja**  

#### <a name="rules-to-prevent-script-threats"></a>Reguły zapobiegania zagrożeniom ze strony skryptów  

Blokowanie następujących elementów pomaga zapobiegać zagrożeniom ze strony skryptów:  

- **Zaciemniony kod w plikach js/vbs/ps i makrach**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj wykonywanie potencjalnie zaciemnionych skryptów](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-execution-of-potentially-obfuscated-scripts)    

  - **Nieskonfigurowany**  
  - Blokuj **blokowanie wszelkich** zasłoniętych kodu js/vbs/PS/makra.  
  - **Tylko inspekcja**  

- **Wykonywanie ładunku pobranego z Internetu przez pliki js/vbs (bez wyjątków)**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Uniemożliwiaj skryptom JavaScript i VBScript uruchamianie pobranej zawartości wykonywalnej](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-javascript-or-vbscript-from-launching-downloaded-executable-content)  

  - **Nieskonfigurowany**  
  - **Zablokuj** blokowi js/vbs wykonywanie ładunku pobranego z Internetu.  
  - **Tylko inspekcja**  

- **Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)  

  - **Nieskonfigurowany**  
  - **Blokuj** — blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI.  
  
  - **Tylko inspekcja**  

- **Niezaufane i niepodpisane procesy uruchamiane z dysku USB**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-untrusted-and-unsigned-processes-that-run-from-usb)    

  - **Nieskonfigurowany**  
  - **Blokuj** — blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB.  
  - **Tylko inspekcja**  
  
- **Pliki wykonywalne, które nie spełniają kryteriów występowania lub wieku albo nie są na liście zaufanych**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj uruchamianie plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)    

  - **Nieskonfigurowany**  
  - **Blokuj** — blokowanie uruchamiania plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych.  
  - **Tylko inspekcja**  

#### <a name="rules-to-prevent-email-threats"></a>Reguły zapobiegania zagrożeniom ze strony poczty e-mail  

Zablokowanie następujących elementów ułatwia zapobieganie zagrożeniom związanym z pocztą e-mail:  

- **Wykonywanie zawartości wykonywalnej (exe, dll, ps, js, vbs itd.) pochodzącej z wiadomości e-mail (poczty internetowej lub klienta poczty) (bez wyjątków)**  
  **Domyślnie**: Nie skonfigurowano  
  Reguła: [Blokuj zawartość wykonywalną z klienta poczty e-mail i poczty internetowej](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-content-from-email-client-and-webmail)  

  - **Nieskonfigurowany**  
  - **Blokuj** — blokowanie wykonywania zawartości wykonywalnej (exe, dll, ps, js, vbs itd.) pochodzącej z wiadomości e-mail (poczty internetowej lub klienta poczty).  
  - **Tylko inspekcja**  

#### <a name="rules-to-protect-against-ransomware"></a>Reguły ochrony przed oprogramowaniem wymuszającym okup  

- **Zaawansowana ochrona przed oprogramowaniem wymuszającym okup**  
  Domyślnie: Nie skonfigurowano  
  Reguła: [Używanie zaawansowanej ochrony przed oprogramowaniem wymuszającego okup](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#use-advanced-protection-against-ransomware)  

  - **Nieskonfigurowany**  
  - **Włącz** — używanie agresywnej ochrony przed oprogramowaniem wymuszającym okup.  
  - **Tylko inspekcja**  

#### <a name="attack-surface-reduction-exceptions"></a>Wyjątki zmniejszenia obszaru ataków

- **Pliki i foldery do wykluczenia z reguł zmniejszenia obszaru ataków**  
  Dostawca CSP usług Defender: [AttackSurfaceReductionOnlyExclusions](https://go.microsoft.com/fwlink/?linkid=872981)  

  - **Zaimportuj** plik CSV zawierający pliki i foldery, które mają zostać wykluczone z reguł zmniejszenia obszaru ataków.  
  - Ręcznie **Dodaj** lokalne pliki lub foldery.  

> [!IMPORTANT]  
> Aby umożliwić prawidłową instalację i wykonywanie aplikacji LOB dla systemu Win32, ustawienia ochrony przed złośliwym oprogramowaniem powinny wykluczać następujące katalogi ze skanowania:  
> **Na maszynach klienckich z architekturą x64**:  
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*  
> *C:\windows\IMECache*  
>  
> **Na maszynach klienckich z architekturą x86**:  
> *C:\Program Files\Microsoft Intune Management Extension\Content*  
> *C:\windows\IMECache*  

### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów  

Pomaga [chronić cenne dane](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/controlled-folders) przed złośliwymi aplikacjami i zagrożeniami, takimi jak oprogramowanie wymuszające okup.  

- **Ochrona folderów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP usług Defender: [EnableControlledFolderAccess](https://go.microsoft.com/fwlink/?linkid=872614)  

  Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.  

  - **Nieskonfigurowany**  
  - **Włączenie**  
  - **Tylko inspekcja**  
  - **Blokuj modyfikację dysku**  
  - **Przeprowadź inspekcję modyfikacji dysku**  

  W przypadku wybrania konfiguracji innej niż *nieskonfigurowana*można skonfigurować następujące opcje:  
  - **Lista aplikacji, które mają dostęp do folderów chronionych**  
    Dostawca CSP usług Defender: [ControlledFolderAccessAllowedApplications](https://go.microsoft.com/fwlink/?linkid=872616)  

    - **Zaimportuj** plik CSV zawierający listę aplikacji.  
    - Ręcznie **Dodaj** aplikacje do tej listy.  

  - **Lista dodatkowych folderów, które muszą być chronione**  
    Dostawca CSP usług Defender: [ControlledFolderAccessProtectedFolders](https://go.microsoft.com/fwlink/?linkid=872617)  

    - **Zaimportuj** plik CSV, który zawiera listę folderów.  
    - Ręcznie **Dodaj** foldery do tej listy.  

### <a name="network-filtering"></a>Filtrowanie sieci  

Zablokuj połączenia wychodzące z dowolnej aplikacji do adresów IP lub domen z niską reputacją. Filtrowanie sieci jest obsługiwane w trybie inspekcji i blokowania.  

- **Ochrona sieci**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP usług Defender: [EnableNetworkProtection](https://go.microsoft.com/fwlink/?linkid=872618)  

  Zamiarem tego ustawienia jest ochrona użytkowników końcowych z aplikacji z dostępem do wyłudzania informacji, witryn hostingowych wykorzystujących luki w zabezpieczeniach i złośliwej zawartości w Internecie. Uniemożliwia ona również nawiązywanie połączeń z niebezpiecznymi lokacjami przez przeglądarki innych firm.  

  - **Nie skonfigurowano** — ta funkcja jest wyłączana. Użytkownicy i aplikacje nie mają zablokowanych połączeń z niebezpiecznymi domenami. Administratorzy nie zobaczą tego działania w usłudze Microsoft Defender Security Center.  
  - **Włącz** ochronę sieci i Zablokuj użytkownikom i aplikacjom możliwość łączenia się z niebezpiecznymi domenami. Administratorzy zobaczą to działanie w usłudze Microsoft Defender Security Center.  
  - **Tylko Inspekcja**: — Użytkownicy i aplikacje nie mogą łączyć się z niebezpiecznymi domenami. Administratorzy zobaczą to działanie w usłudze Microsoft Defender Security Center.  

### <a name="exploit-protection"></a>Exploit Protection  

- **Przekaż plik XML**  
  **Domyślne**: *Nieskonfigurowane*  

  Aby [chronić urządzenia przed programami wykorzystującymi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)luki w zabezpieczeniach, należy utworzyć plik XML zawierający ustawienia ograniczenia systemu i aplikacji. Istnieją dwie metody tworzenia pliku XML:  

  - *PowerShell* — użyj jednego lub kilku z poleceń cmdlet programu PowerShell: *Get-ProcessMitigation*, *Set-ProcessMitigation* i *ConvertTo-ProcessMitigationPolicy*. Polecenia cmdlet służą do konfigurowania ustawień ograniczania ryzyka i eksportowania ich reprezentacji w formacie XML.  

  - *Interfejs użytkownika usługi Microsoft Defender Security Center* — w usłudze Microsoft Defender Security Center kliknij pozycję Sterowanie aplikacjami i przeglądarką, a następnie przewiń w dół wyświetlonego ekranu i znajdź funkcję Exploit Protection. Najpierw skonfiguruj ustawienia ograniczania ryzyka na kartach Ustawienia systemowe i Ustawienia programu. Następnie użyj linku Eksportuj ustawienia w dolnej części ekranu, aby wyeksportować ich reprezentację w formacie XML.  

- **Edytowanie interfejsu ochrony przed programami wykorzystującymi luki w zabezpieczeniach**  
  **Domyślnie**: Nie skonfigurowano  
  ExploitGuard CSP: [ExploitProtectionSettings](https://go.microsoft.com/fwlink/?linkid=872887)  


  - **Block** -Przekaż plik XML, który umożliwia skonfigurowanie ograniczeń pamięci, przepływu sterowania i zasad. Ustawienia w pliku XML mogą być używane do blokowania aplikacji przed programami wykorzystującymi luki w zabezpieczeniach.  
  - **Nieskonfigurowane** — nie jest używana żadna Konfiguracja niestandardowa.  

## <a name="microsoft-defender-application-control"></a>Kontrola aplikacji usługi Microsoft Defender  

Wybierz dodatkowe aplikacje, które muszą być objęte inspekcją przez program, lub mogą być zaufane do uruchomienia przez program Microsoft Defender Application Control. Składniki systemu Windows i wszystkie aplikacje ze Sklepu Windows są automatycznie zaufane do uruchomienia.  


- **Zasady integralności kodu kontroli aplikacji**  
  **Domyślnie**: Nie skonfigurowano  
   Dostawca CSP: [dostawca usług kryptograficznych funkcji AppLocker](https://go.microsoft.com/fwlink/?linkid=874543)  

  - **Wymuś** — wybierz zasady integralności kodu kontroli aplikacji dla urządzeń użytkowników.  
  
    Po włączeniu kontrolę aplikacji na urządzeniu można wyłączyć ją tylko przez zmianę trybu z *Wymuszanie* na *Tylko inspekcja*. Zmiana trybu z *Wymuszanie* na *Nieskonfigurowane* skutkuje tym, że kontrola aplikacji nadal jest wymuszana na przypisanych urządzeniach.  

  - **Nie skonfigurowano** — Kontrola aplikacji nie została dodana do urządzeń. Ustawienia, które zostały wcześniej dodane, są jednak nadal wymuszane na przypisanych urządzeniach. 
 
  - **Tylko Inspekcja** — aplikacje nie są blokowane. Wszystkie zdarzenia są rejestrowane w dziennikach klienta lokalnego.  

## <a name="microsoft-defender-credential-guard"></a>Ochrona poświadczeń programu Microsoft Defender  

Funkcja Microsoft Defender Credential Guard chroni przed atakami polegającymi na kradzieży poświadczeń. Izoluje ona wpisy tajne, tak aby tylko uprzywilejowane oprogramowanie systemu mogło uzyskiwać do nich dostęp.  

- **Credential Guard**  
  **Domyślne**: Wyłącz  
  [DeviceGuard CSP](https://go.microsoft.com/fwlink/?linkid=872424)  

  - **Wyłącz** — zdalne wyłączanie funkcji Credential Guard, jeśli została ona wcześniej włączona za pomocą opcji **Włączone bez blokady UEFI**.  

  - **Włącz z blokadą UEFI** — funkcji Credential Guard nie można wyłączyć za pomocą klucza rejestru ani zasad grupy.  

    > [!NOTE]
    > Jeśli używasz tego ustawienia i chcesz później wyłączyć funkcję Credential Guard, musisz ustawić zasady grupy na **Wyłączone**. Musisz również fizycznie wyczyścić informacje o konfiguracji interfejsu UEFI z każdego komputera. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.  

  - **Włącz bez blokady UEFI** — umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 w wersji 1511 lub nowszej.  

  Po *włączeniu* funkcji Credential Guard są również włączane następujące wymagane funkcje:  
  
  - **Zabezpieczenia oparte na wirtualizacji** (VBS)  
    Włącza się podczas następnego ponownego uruchomienia komputera. Zabezpieczenia oparte na wirtualizacji używają funkcji Hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń.  
  - **Bezpieczny rozruch z bezpośrednim dostępem do pamięci**  
    Włącza zabezpieczenia VBS z funkcją bezpiecznego rozruchu i bezpośrednim dostępem do pamięci (DMA). Ochrona DMA wymaga obsługi sprzętowej i można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach.  

## <a name="microsoft-defender-security-center"></a>Centrum zabezpieczeń usługi Microsoft Defender  

Centrum zabezpieczeń usługi Microsoft Defender działa jako osobna aplikacja lub proces z każdej z poszczególnych funkcji. Wyświetla ona powiadomienia za pośrednictwem centrum akcji. Pełni rolę modułu zbierającego lub jednego miejsca służącego do wyświetlania stanu oraz uruchamiania niektórych czynności konfiguracyjnych dla każdej funkcji. Dowiedz się więcej z [witryny Microsoft Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) docs.  

### <a name="microsoft-defender-security-center-app-and-notifications"></a>Aplikacja i powiadomienia usługi Centrum zabezpieczeń usługi Microsoft Defender  

Zablokuj dostęp użytkowników końcowych do różnych obszarów aplikacji Centrum zabezpieczeń usługi Microsoft Defender. Ukrywanie sekcji spowoduje również blokowanie pokrewnych powiadomień.  

- **Ochrona przed wirusami i zagrożeniami**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableVirusUI](https://go.microsoft.com/fwlink/?linkid=873662)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar ochrony przed wirusami i zagrożeniami w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień dotyczących ochrony przed wirusami i zagrożeniami.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Ochrona oprogramowania wymuszającego okup**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [HideRansomwareDataRecovery](https://go.microsoft.com/fwlink/?linkid=873664)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar ochrony przy użyciu oprogramowania wymuszającego okup w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień związanych z ochroną oprogramowania wymuszającego okup.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Ochrona konta**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableAccountProtectionUI](https://go.microsoft.com/fwlink/?linkid=873666)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar Ochrona konta w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień związanych z ochroną konta.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Zapora i ochrona sieci**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableNetworkUI](https://go.microsoft.com/fwlink/?linkid=873668)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar Zapora i ochrona sieci w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień dotyczących zapory i ochrony sieci.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Kontrola aplikacji i przeglądarki**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableAppBrowserUI](https://go.microsoft.com/fwlink/?linkid=873669)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar sterowania aplikacji i przeglądarki w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień związanych z aplikacją i formantem przeglądarki.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Ochrona sprzętowa**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableDeviceSecurityUI](https://go.microsoft.com/fwlink/?linkid=873670)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar Ochrona sprzętu w programie Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień dotyczących ochrony sprzętu.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Wydajność i kondycja urządzenia**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableHealthUI](https://go.microsoft.com/fwlink/?linkid=873671)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar wydajność i kondycja urządzenia w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień dotyczących wydajności i kondycji urządzenia.  
  
  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Opcje rodziny**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableFamilyUI](https://go.microsoft.com/fwlink/?linkid=873673)  

  Skonfiguruj, czy użytkownicy końcowi mogą wyświetlać obszar opcji rodziny w usłudze Microsoft Defender Security Center. Ukrycie tej sekcji spowoduje również zablokowanie wszystkich powiadomień — związanych z opcjami rodziny.  
  
  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Powiadomienia z wyświetlanych obszarów aplikacji**  
  **Domyślnie**: Nie skonfigurowano  
  WindowsDefenderSecurityCenter CSP: [DisableNotifications](https://go.microsoft.com/fwlink/?linkid=873675)  

  Wybierz, które powiadomienia mają być wyświetlane użytkownikom końcowym. Powiadomienia niekrytyczne obejmują podsumowania działania programu antywirusowego Microsoft Defender, w tym powiadomienia po zakończeniu skanowania. Wszystkie pozostałe powiadomienia są traktowane jako krytyczne.  

  - **Nieskonfigurowany**  
  - **Blokuj powiadomienia niekrytyczne**  
  - **Blokuj wszystkie powiadomienia**  

- **Ikona Security Center systemu Windows na pasku zadań**  
  **Domyślnie**: Nie skonfigurowano  

  Skonfiguruj wyświetlanie kontrolki obszar powiadomień. Użytkownik musi się wylogować i zalogować się lub uruchomić ponownie komputer, aby to ustawienie zaczęło obowiązywać.  
  
  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Wyczyść przycisk TPM**  
  **Domyślnie**: Nie skonfigurowano  

  Skonfiguruj wyświetlanie przycisku Wyczyść moduł TPM.  
  
  - **Nieskonfigurowany**  
  - **Wyłącz**  

- **Ostrzeżenie dotyczące aktualizacji oprogramowania układowego modułu TPM**  
  **Domyślnie**: Nie skonfigurowano  
  
  Skonfiguruj sposób wyświetlania aktualizacji oprogramowania układowego modułu TPM, gdy zostanie wykryte zagrożone oprogramowanie układowe.  

  - **Nieskonfigurowany**  
  - **Ukryj**  

- **Ochrona przed manipulacjami**  
  **Domyślnie**: Nie skonfigurowano

  Włącz lub Wyłącz ochronę przed naruszeniem na urządzeniach. Aby można było korzystać z ochrony przed naruszeniem, należy [zintegrować usługę Microsoft Defender Advanced Threat Protection z usługą Intune](advanced-threat-protection.md)i mieć [Enterprise Mobility + Security](../fundamentals/licenses.md).  
  - **Nieskonfigurowane** — nie wprowadzono zmian w ustawieniach urządzenia.
  - **Włączona** ochrona przed naruszeniem jest włączona, a ograniczenia są wymuszane na urządzeniach.
  - **Wyłączona** ochrona przed manipulacją jest wyłączona, a ograniczenia nie są wymuszane.

### <a name="it-contact-information"></a>Informacje kontaktowe działu IT  

Podaj informacje kontaktowe działu IT do wyświetlania w aplikacji Centrum zabezpieczeń usługi Microsoft Defender i powiadomieniach aplikacji.  

Można wybrać opcję **Wyświetlaj w aplikacji i powiadomieniach**, **Wyświetlaj tylko w aplikacji**, **Wyświetlaj tylko w powiadomieniach** lub **Nie wyświetlaj**. Należy wprowadzić **nazwę organizacji IT** i co najmniej jedną z następujących opcji kontaktu:  


- **Informacje kontaktowe działu IT**  
  **Domyślne**: nie wyświetlaj  
  WindowsDefenderSecurityCenter CSP: [EnableCustomizedToasts](https://go.microsoft.com/fwlink/?linkid=873676)  
  
  Skonfiguruj miejsce wyświetlania informacji kontaktowych IT użytkownikom końcowym.  
  
  - **Wyświetlaj w aplikacji i powiadomieniach**  
  - **Wyświetlaj tylko w aplikacji**  
  - **Wyświetlaj tylko w powiadomieniach**  
  - **Nie wyświetlaj**  

  Po skonfigurowaniu do wyświetlania można skonfigurować następujące ustawienia:  

  - **Nazwa organizacji IT**  
    **Domyślne**: *Nieskonfigurowane*  
    WindowsDefenderSecurityCenter CSP: [NazwaFirmy](https://go.microsoft.com/fwlink/?linkid=873677)  

  - **Numer telefonu lub identyfikator Skype działu IT**  
    **Domyślne**: *Nieskonfigurowane*  
    WindowsDefenderSecurityCenter CSP: [telefon](https://go.microsoft.com/fwlink/?linkid=873678) 

  - **Adres e-mail działu IT**  
    **Domyślne**: *Nieskonfigurowane*  
    WindowsDefenderSecurityCenter CSP: [email](https://go.microsoft.com/fwlink/?linkid=873679)  

  - **Adres URL witryny internetowej pomocy technicznej**  
    **Domyślne**: *Nieskonfigurowane*  
    WindowsDefenderSecurityCenter CSP: [adres URL](https://go.microsoft.com/fwlink/?linkid=873680)  
 
## <a name="local-device-security-options"></a>Opcje lokalnych zabezpieczeń urządzeń  

Te opcje umożliwiają konfigurowanie ustawień zabezpieczeń lokalnych na urządzeniach z systemem Windows 10.  

### <a name="accounts"></a>Konta  

- **Dodaj nowe konta Microsoft**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [Accounts_BlockMicrosoftAccounts](https://go.microsoft.com/fwlink/?linkid=867916)  


  - **Blokuj** — uniemożliwia użytkownikom dodawanie nowych kont Microsoft na tym komputerze.  
  - **Nie skonfigurowano** — użytkownicy mogą używać kont Microsoft na urządzeniu.  

- **Zdalne logowanie bez hasła**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867890)  


   - **Blokuj** — zezwalanie tylko kontom lokalnym z pustymi hasłami na logowanie się przy użyciu klawiatury urządzenia.  
   - **Nie skonfigurowano** — zezwalanie kontom lokalnym z pustymi hasłami logowanie się z lokalizacji innych niż urządzenie fizyczne.  

#### <a name="admin"></a>Administracja  

- **Konto administratora lokalnego**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867850)  


  - **Blokuj** Zapobiegaj użyciu konta administratora lokalnego.  
  - **Nieskonfigurowany**  

- **Zmień nazwę konta administratora**  
  **Domyślne**: *Nieskonfigurowane*  
  LocalPoliciesSecurityOptions CSP: [Accounts_RenameAdministratorAccount](https://go.microsoft.com/fwlink/?linkid=867917)  
 

  Definiowanie innej nazwy konta do skojarzenia z identyfikatorem zabezpieczeń (SID) dla konta „Administrator”.  

 #### <a name="guest"></a>Gość  

- **Konto gościa**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [LocalPoliciesSecurityOptions](https://go.microsoft.com/fwlink/?linkid=867853)  

  - **Blokuj** — uniemożliwiaj korzystanie z konta gościa.  
  - **Nieskonfigurowany**  

- **Zmień nazwę konta gościa**  
  **Domyślne**: *Nieskonfigurowane*  
  LocalPoliciesSecurityOptions CSP: [Accounts_RenameGuestAccount](https://go.microsoft.com/fwlink/?linkid=867918)  
  
  Definiowanie innej nazwy konta do skojarzenia z identyfikatorem zabezpieczeń (SID) dla konta „Gość”.  

### <a name="devices"></a>Devices  

- **Oddokuj urządzenie bez logowania**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [Devices_AllowUndockWithoutHavingToLogon](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-devices-allowundockwithouthavingtologon)  

  
  - **Blokuj** — użytkownicy mogą bezpiecznie oddokować urządzenie przez naciśnięcie fizycznego przycisku wysuwania zadokowanego urządzenia przenośnego.  
  - **Nieskonfigurowane** — użytkownik musi zalogować się na urządzeniu i odebrać uprawnienia do oddokowania urządzenia.  

- **Zainstaluj sterowniki dla udostępnianych drukarek**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters](https://go.microsoft.com/fwlink/?linkid=867921)  


  - **Włączone** — każdy użytkownik może instalować sterownik drukarki w ramach łączenia z drukarką udostępnioną.  
  - **Nie skonfigurowano** — tylko administratorzy mogą instalować sterownik drukarki w ramach łączenia z drukarką udostępnioną.  

- **Ogranicz dostęp do nośnika CD-ROM dla lokalnego aktywnego użytkownika**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych: [Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly](https://go.microsoft.com/fwlink/?linkid=867922)  


  - **Włączone** — tylko interaktywnie zalogowany użytkownik może korzystać z nośników CD-ROM. Jeśli te zasady są włączone, a żaden użytkownik nie jest zalogowany interaktywnie, napęd CD-ROM jest dostępny za pośrednictwem sieci.  
  - **Nie skonfigurowano** — każdy ma dostęp do dysku CD-ROM.  

- **Sformatuj i wysuń wymienny nośnik**  
  **Domyślne**: Administratorzy  
  Dostawca usług kryptograficznych: [Devices_AllowedToFormatAndEjectRemovableMedia](https://go.microsoft.com/fwlink/?linkid=867920)  
 

  Zdefiniuj, kto może formatować i wysuwać nośnik wymienny systemu plików NTFS:  
  - **Nieskonfigurowany**  
  - **Administratorzy**  
  - **Administratorzy i użytkownicy zaawansowani**  
  - **Administratorzy i użytkownicy interaktywni**  

### <a name="interactive-logon"></a>Logowanie interakcyjne  

- **Liczba minut braku aktywności na ekranie blokady przed aktywowaniem wygaszacza ekranu**  
  **Domyślne**: *Nieskonfigurowane*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MachineInactivityLimit](https://go.microsoft.com/fwlink/?linkid=867891)  


  Wprowadź maksymalną liczbę minut braku aktywności na ekranie logowania pulpitu interakcyjnego przed uruchomieniem wygaszacza ekranu. (**0** - **99999**)  

- **Wymagaj kombinacji CTRL+ALT+DEL do zalogowania**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotRequireCTRLALTDEL](https://go.microsoft.com/fwlink/?linkid=867951)  


  - **Włącz** — użytkownicy mogą się logować bez naciskania kombinacji klawiszy CTRL+ALT+DEL.  
  - **Nie skonfigurowano** — wymagaj od użytkowników naciśnięcia kombinacji klawiszy CTRL+ALT+DEL przed zalogowaniem się do systemu Windows.  

- **Zachowanie po wyjęciu karty inteligentnej**  
  **Domyślne**: Zablokuj stację roboczą   
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_SmartCardRemovalBehavior](https://go.microsoft.com/fwlink/?linkid=868437)  
    
  Określa, co się stanie, gdy karta inteligentna zalogowanego użytkownika zostanie usunięta z czytnika kart inteligentnych. Dostępne opcje:  

  - **Zablokuj stację roboczą** — stacja robocza zostanie zablokowana po wyjęciu karty inteligentnej. Ta opcja umożliwia użytkownikom opuszczenie miejsca pracy i zabranie ze sobą karty inteligentnej przy jednoczesnym zachowaniu chronionej sesji.  
  - **Brak akcji**  
  - **Wymuszaj wylogowanie** — użytkownik jest automatycznie wylogowywany po wyjęciu karty inteligentnej.  
  - **Rozłącz, gdy istnieje sesja usług pulpitu zdalnego** — usunięcie karty inteligentnej powoduje rozłączenie sesji bez wylogowywania użytkownika. Ta opcja umożliwia użytkownikowi włożenie karty inteligentnej i wznowienie sesji w późniejszym czasie lub na innym komputerze z czytnikiem kart inteligentnych bez konieczności ponownego logowania się. Jeśli sesja jest lokalna, te zasady działają tak samo, jak w przypadku opcji Zablokuj stację roboczą.  

#### <a name="display"></a>Wyświetlanie  

- **Informacje o użytkowniku na ekranie blokady**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-displayuserinformationwhenthesessionislocked)  

  Konfigurowanie informacji o użytkowniku wyświetlanych po zablokowaniu sesji. Jeśli nie zostaną one skonfigurowane, będzie pokazywana nazwa wyświetlana użytkownika, domena i nazwa użytkownika.  

  - **Nieskonfigurowany**  
  - **Nazwa wyświetlana użytkownika, domena i nazwa użytkownika**  
  - **Tylko nazwa wyświetlana użytkownika**  
  - **Nie wyświetlaj informacji o użytkowniku**  

- **Ukryj ostatniego zalogowanego użytkownika**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotDisplayLastSignedIn](https://go.microsoft.com/fwlink/?linkid=868437)  
  
  
  - **Włącz** -Ukryj nazwę użytkownika.  
  - **Nieskonfigurowane** — Pokaż ostatnią nazwę użytkownika.  

- **Ukryj nazwę użytkownika podczas logowania**
  **wartość domyślna**: nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotDisplayUsernameAtSignIn](https://go.microsoft.com/fwlink/?linkid=867959)  

  
  - **Włącz** -Ukryj nazwę użytkownika.  
  - **Nieskonfigurowane** — Pokaż ostatnią nazwę użytkownika.  

- **Tytuł komunikatu logowania**  
  **Domyślne**: *Nieskonfigurowane*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MessageTitleForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867964)  

  Ustaw tytuł komunikatu dla użytkowników próbujących się zalogować.  

- **Tekst komunikatu logowania**  
  **Domyślne**: *Nieskonfigurowane*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MessageTextForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867962)  

  Ustaw tekst komunikatu dla użytkowników próbujących się zalogować.  
  
### <a name="network-access-and-security"></a>Dostęp do sieci i jej zabezpieczenia

- **Dostęp anonimowy do nazwanych potoków i udziałów**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares](https://go.microsoft.com/fwlink/?linkid=868432)  

  - **Nie skonfigurowano** — ogranicza dostęp anonimowy do ustawień udziałów i nazwanych potoków. Dotyczy ustawień, do których można uzyskiwać anonimowy dostęp.  
  - **Blokuj** — Wyłącz te zasady, udostępniając dostęp anonimowy.  

- **Anonimowe wyliczanie kont SAM**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts](https://go.microsoft.com/fwlink/?linkid=868434)  
  
  - **Nieskonfigurowane** — użytkownicy anonimowi mogą wyliczać konta sam.  
  - **Blokuj** — uniemożliwia anonimowe wyliczanie kont SAM.  

- **Anonimowe wyliczanie kont SAM i udziałów**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares](https://go.microsoft.com/fwlink/?linkid=868435)  

  - **Nie skonfigurowano** — użytkownicy anonimowi mogą wyliczać nazwy kont domen i udziałach sieciowych.  
  - **Blokuj** — uniemożliwia anonimowe wyliczanie kont SAM i udziałów. 

- **Wartość skrótu programu LAN Manager zapisywana przy zmianie hasła**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange](https://go.microsoft.com/fwlink/?linkid=868431)  
   
  Określ, czy wartość skrótu haseł ma być przechowywana przy następnym zmianie hasła. 
  - **Nieskonfigurowane** — wartość skrótu nie jest zapisywana  
  - **Block** — Menedżer sieci LAN (LM) przechowuje wartość skrótu dla nowego hasła.  

- **Żądania uwierzytelniania protokołu PKU2U**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_AllowPKU2UAuthenticationRequests](https://go.microsoft.com/fwlink/?linkid=867892)  

  - **Nie skonfigurowano**— Zezwalaj na żądania PU2U.  
  - Blokuj **blokowanie żądań** uwierzytelniania protokołu PKU2U na urządzeniu.  

- **Ogranicz zdalne połączenia RPC do Menedżera kont zabezpieczeń**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM](https://go.microsoft.com/fwlink/?linkid=867893)  
  
  - **Nie skonfigurowano** — Użyj domyślnego deskryptora zabezpieczeń, który może pozwolić użytkownikom i grupom na wykonywanie wywołań zdalnego wywołania RPC do Menedżera sam.
  - **Zezwalaj** — Odmów użytkownikom i grupom wykonywania zdalnych wywołań RPC do Menedżera kont zabezpieczeń (sam), w którym są przechowywane konta użytkowników i hasła. Wartość **Zezwalaj** również pozwala zmienić domyślny ciąg języka SDDL (Security Descriptor Definition Language), aby jawnie zezwolić użytkownikom i grupom na wykonywanie tych wywołań zdalnych.  

    - **Deskryptor zabezpieczeń**  
      **Domyślne**: *Nieskonfigurowane*  
    
- **Minimalne zabezpieczenia sesji dla klientów opartych na technologii SSP NTLM**  
  **Wartość domyślna**: brak  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedclients)  
  
  To ustawienie zabezpieczeń pozwala serwerowi na wymaganie negocjacji szyfrowania 128-bitowego i/lub zabezpieczeń sesji NTLMv2.  

  - **Brak**  
  - **Wymagaj zabezpieczeń sesji NTLMv2**  
  - **Wymagaj szyfrowania 128-bitowego**  
  - **Protokół NTLMv2 i szyfrowanie 128-bitowego**  
 
- **Minimalne zabezpieczenia sesji dla serwerów opartych na technologii SSP NTLM**  
  **Wartość domyślna**: brak  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedservers)  

  To ustawienie zabezpieczeń określa, który protokół uwierzytelniania typu żądanie/odpowiedź będzie używany podczas logowania do sieci.  

  - **Brak**  
  - **Wymagaj zabezpieczeń sesji NTLMv2**  
  - **Wymagaj szyfrowania 128-bitowego**  
  - **Protokół NTLMv2 i szyfrowanie 128-bitowego**  

- **Poziom uwierzytelniania programu LAN Manager**  
  **Wartość domyślna**: LM i NTLM  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_LANManagerAuthenticationLevel](https://aka.ms/policy-csp-localpoliciessecurityoptions-lanmanagerauthenticationlevel)  


  - **LM i NTLM**  
  - **LM, NTLM i NTLMv2**  
  - **NTLM**  
  - **Metody**  
  - **NTLMv2 i nie LM**  
  - **NTLMv2, nie LM ani NTLM**  
  
- **Niezabezpieczone logowania gościa**  
  **Domyślnie**: Nie skonfigurowano  
  LanmanWorkstation CSP: [LanmanWorkstation](https://aka.ms/policy-csp-lanmanworkstation-enableinsecureguestlogons)  

  Włączenie tego ustawienia spowoduje odrzucenie niezabezpieczonych logowań gościa przez klienta SMB.  

  - **Nieskonfigurowany**  
  - **Blokuj** — klient SMB odrzuca niezabezpieczone logowania gościa.  

### <a name="recovery-console-and-shutdown"></a>Konsola odzyskiwania i zamykanie  

- **Wyczyść plik stronicowania pamięci wirtualnej podczas zamykania**  
  **Domyślnie**: Nie skonfigurowano  
   LocalPoliciesSecurityOptions CSP: [Shutdown_ClearVirtualMemoryPageFile](https://go.microsoft.com/fwlink/?linkid=867914)  


  - **Włącz** — plik stronicowania pamięci wirtualnej jest czyszczony podczas wyłączania urządzenia.  
  - **Nie skonfigurowano** — pamięć wirtualna nie jest czyszczona.  

- **Zamknij bez logowania**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn](https://go.microsoft.com/fwlink/?linkid=867912)  

  
  - **Blokuj** — ukrywanie opcji zamknięcia na ekranie logowania systemu Windows. Użytkownicy muszą zalogować się do urządzenia, a następnie je zamknąć.  
  - **Nie skonfigurowano** — umożliwia użytkownikom zamknięcie urządzenia z poziomu ekranu logowania systemu Windows.  

### <a name="user-account-control"></a>Kontrola konta użytkownika  

- **Integralność funkcji UIA bez bezpiecznej lokalizacji**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867897)  
  
  - **Bloki** — aplikacje znajdujące się w bezpiecznej lokalizacji w systemie plików będą uruchamiane tylko z integralnością UIAccess.  
  - **Nie skonfigurowano** — umożliwia uruchamianie aplikacji z poziomem integralności UIAccess, nawet jeśli aplikacje nie znajdują się w bezpiecznej lokalizacji w systemie plików.  

- **Wirtualizuj błędy zapisu w plikach i rejestrze w lokalizacjach poszczególnych użytkowników**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations](https://go.microsoft.com/fwlink/?linkid=867900)  

  - **Włączone** — aplikacje, które zapisują dane w lokalizacjach chronionych, kończą się niepowodzeniem.  
  - **Nie skonfigurowano** — błędy zapisu aplikacji są przekierowywane w czasie wykonywania do zdefiniowanych lokalizacji użytkownika dla systemu plików i rejestru.  

- **Podnieś poziom uprawnień tylko plikom wykonywalnym, które są podpisane i zweryfikowane**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867965)  

  - **Włączone** — wymuszanie weryfikacji ścieżki certyfikacji PKI dla danego pliku wykonywalnego przed zezwoleniem na jego uruchomienie.  
  - **Nie skonfigurowano** — brak wymuszania weryfikacji ścieżki certyfikacji PKI dla danego pliku wykonywalnego przed zezwoleniem na jego uruchomienie.  

#### <a name="uia-elevation-prompt-behavior"></a>Zachowanie monitu o podniesienie uprawnień automatyzacji interfejsu użytkownika  

- **Monit o podniesienie uprawnień dla administratorów**  
  **Domyślnie**: monitowanie o zgodę w przypadku plików binarnych z systemem innym niż Windows  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_BehaviorOfTheElevationPromptForAdministrators](https://go.microsoft.com/fwlink/?linkid=867895)  

  Definiowanie zachowania monitu o podniesienie uprawnień dla administratorów w trybie zatwierdzania przez administratora.  

  - **Nieskonfigurowany**  
  - **Podnieś bez monitowania**  
  - **Monituj o podanie poświadczeń na bezpiecznym pulpicie**  
  - **Monituj o poświadczenia**  
  - **Monituj o zgodę**  
  - **Monituj o zgodę w przypadku plików binarnych z systemem innym niż Windows**  


- **Monit o podniesienie uprawnień dla standardowych użytkowników**  
  **Domyślnie**: Monituj o poświadczenia  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers](https://go.microsoft.com/fwlink/?linkid=867896)  

  Definiowanie zachowania monitu o podniesienie uprawnień dla standardowych użytkowników.  

  - **Nieskonfigurowany**  
  - **Automatycznie odrzucaj żądania podniesienia uprawnień**  
  - **Monituj o podanie poświadczeń na bezpiecznym pulpicie**  
  - **Monituj o poświadczenia**  

- **Kieruj monity o podniesienie uprawnień do interakcyjnego pulpitu użytkownika**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation](https://go.microsoft.com/fwlink/?linkid=867899)  


  - **Włączone** — wszystkie żądania podniesienia uprawnień przechodzą do pulpitu użytkownika interakcyjnego, a nie na bezpiecznym pulpicie. Używane są ustawienia zasad zachowania monitu dla administratorów i użytkowników standardowych.  
  - **Nie skonfigurowano** — wymuszanie kierowania wszystkich żądań podniesienia uprawnień do bezpiecznego pulpitu bez względu na ustawienia zasad zachowania monitu dla administratorów i użytkowników standardowych.

- **Monit o podniesienie uprawnień dla instalacji aplikacji**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_DetectApplicationInstallationsAndPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867901)  

   - **Włączone** — pakiety instalacyjne aplikacji nie są wykrywane ani monitowane o podniesienie poziomu uprawnień.
   - **Nie skonfigurowano** — użytkownicy są monitowani o podanie nazwy użytkownika administracyjnego i hasła, gdy pakiet instalacyjny aplikacji wymaga podwyższonego poziomu uprawnień.

- **Monit o podniesienie uprawnień funkcji UIA bez bezpiecznego pulpitu**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_AllowUIAccessApplicationsToPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867894)  

- **Włącz** — zezwalanie aplikacjom z poziomem UIAccess na monitowanie o podniesienie uprawnień bez używania bezpiecznego pulpitu.  
- **Nie skonfigurowano** — Monituj o podniesienie uprawnień przy użyciu bezpiecznego pulpitu.  

#### <a name="admin-approval-mode"></a>Tryb zatwierdzania przez administratora  

- **Tryb zatwierdzania przez administratora dla wbudowanego konta administratora**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_UseAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867902)  

  - **Włączone** — umożliwia używanie trybu zatwierdzania przez administratora dla wbudowanego konta administratora. Każda operacja, która wymaga podniesienia uprawnień, monituje użytkownika o zatwierdzenie operacji.  
  - **Nie skonfigurowano** — uruchamia wszystkie aplikacje z pełnymi uprawnieniami administratora.  

- **Uruchom wszystkich administratorów w trybie zatwierdzania przez administratora**  
  **Domyślne**: nieskonfigurowane  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_RunAllAdministratorsInAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867898)  


  - **Włączone**— Włącz tryb zatwierdzania przez administratora.  
  - **Nie skonfigurowano** — wyłącz tryb zatwierdzania przez administratora i wszystkie powiązane ustawienia zasad funkcji Kontrola konta użytkownika.  

### <a name="microsoft-network-client"></a>Klient sieci firmy Microsoft  

- **Podpisuj cyfrowo komunikację (za zgodą serwera)**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees](https://go.microsoft.com/fwlink/?linkid=868423)  

  Określa, czy klient SMB negocjuje podpisywanie pakietów SMB.  
  - **Blokuj** — klient SMB nigdy nie negocjuje podpisywania pakietów SMB.
  - **Nie skonfigurowano** — klient sieci firmy Microsoft żąda od serwera uruchamiania pakietów SMB podczas konfigurowania sesji. Jeśli podpisywanie pakietów jest włączone na serwerze, ma miejsce negocjowanie podpisywania pakietów.  

- **Wyślij niezaszyfrowane hasło do serwerów SMB innych firm**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers](https://go.microsoft.com/fwlink/?linkid=868426)  


  - **Blokuj** — przekierowanie bloku komunikatów serwera (SMB) może wysyłać hasła w postaci zwykłego tekstu do serwerów SMB firm innych niż Microsoft, które nie obsługują szyfrowania hasła podczas uwierzytelniania.  
  - **Nie skonfigurowano** — Blokuj wysyłanie haseł w postaci zwykłego tekstu. Hasła są szyfrowane.  

- **Podpisuj cyfrowo komunikację (zawsze)**  
  **Domyślnie**: Nie skonfigurowano  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868425)  


  - **Włącz** — klient sieci Microsoft nie komunikuje się z serwerem sieci Microsoft, chyba że serwer zgadza się na podpisywanie pakietów SMB.  
  - **Nie skonfigurowano** — podpisywanie pakietów SMB jest negocjowane między klientem i serwerem.  

### <a name="microsoft-network-server"></a>Serwer sieci Microsoft  
  
- **Podpisuj cyfrowo komunikację (za zgodą klienta)**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych: [MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees](https://go.microsoft.com/fwlink/?linkid=868429)  

  - **Włącz** — serwer sieci Microsoft negocjuje podpisywanie pakietów SMB zgodnie z żądaniem klienta. Oznacza to, że jeśli podpisywanie pakietów zostało włączone na kliencie, jest negocjowane podpisywanie pakietów.  
  - **Nieskonfigurowane** — klient SMB nigdy nie negocjuje podpisywania pakietów SMB.  

- **Podpisuj cyfrowo komunikację (zawsze)**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca usług kryptograficznych: [MicrosoftNetworkServer_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868428)  

  - **Włącz** — serwer sieci Microsoft nie komunikuje się z klientem sieci Microsoft, chyba że klient zgadza się na podpisywanie pakietów SMB.  
  - **Nie skonfigurowano** — podpisywanie pakietów SMB jest negocjowane między klientem i serwerem.  

## <a name="xbox-services"></a>Usługi konsoli Xbox

- **Zadanie zapisywania gier Xbox**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [TaskScheduler/EnableXboxGameSaveTask](https://go.microsoft.com/fwlink/?linkid=875480)  
   
  To ustawienie określa, czy zadanie zapisywania gier Xbox jest włączone czy wyłączone.  
  - **Włączone**
  - **Nieskonfigurowany**

- **Usługa zarządzania akcesoriami konsoli Xbox**  
  **Domyślne**: ręczne  
  Dostawca CSP: [SystemServices/ConfigureXboxAccessoryManagementServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875481)  

  To ustawienie określa typ uruchomienia usługi zarządzania akcesoriami.  
  - **Ręczne**
  - **Automatyczne**
  - **Wyłączone**

- **Usługa zarządzania uwierzytelnianiem w usłudze Xbox Live**  
  **Domyślne**: ręczne  
  Dostawca CSP: [SystemServices/ConfigureXboxLiveAuthManagerServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875482)  
 
  To ustawienie określa typ uruchomienia usługi Menedżera uwierzytelniania na żywo.  
  - **Ręczne**
  - **Automatyczne**
  - **Wyłączone**
 
- **Usługa zapisywania gier Xbox Live**  
  **Domyślne**: ręczne  
  Dostawca CSP: [SystemServices/ConfigureXboxLiveGameSaveServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875483)  

  To ustawienie określa typ uruchomienia usługi zapisywania na żywo.  
  - **Ręczne**
  - **Automatyczne**
  - **Wyłączone**

- **Usługa sieciowa Xbox Live**  
  **Domyślne**: ręczne  
  Dostawca CSP: [SystemServices/ConfigureXboxLiveNetworkingServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875484)  

  To ustawienie określa typ uruchomienia usługi sieciowej.  
  - **Ręczne**
  - **Automatyczne**
  - **Wyłączone**

## <a name="user-rights"></a>Prawa użytkownika

- **Dostęp do Menedżera poświadczeń jako zaufany obiekt wywołujący**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/AccessCredentialManagerAsTrustedCaller](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-accesscredentialmanagerastrustedcaller)

  To prawo użytkownika jest używane przez Menedżera poświadczeń podczas operacji wykonywania kopii zapasowych i przywracania. Zapisane poświadczenia użytkowników mogą zostać naruszone, jeśli to uprawnienie zostanie przyznane innym podmiotom.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Zezwalaj na logowanie lokalne**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/AllowLocalLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-allowlocallogon)

  To prawo użytkownika określa, którzy użytkownicy mogą logować się na komputerze.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Zezwalaj na dostęp z sieci**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/AccessFromNetwork](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-accessfromnetwork)

  To prawo użytkownika określa, którzy użytkownicy i grupy mogą łączyć się z komputerem za pośrednictwem sieci.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Działanie jako część systemu operacyjnego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ActAsPartOfTheOperatingSystem](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-actaspartoftheoperatingsystem)

  Działanie jako część systemu operacyjnego
  - **Nieskonfigurowany**
  - **Zezwalaj**  

- **Tworzenie kopii zapasowej plików i katalogów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/BackupFilesAndDirectories](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-backupfilesanddirectories)

  To prawo użytkownika określa, którzy użytkownicy mogą pomijać uprawnienia do plików, katalogów, rejestru i innych obiektów trwałych podczas tworzenia kopii zapasowych plików i katalogów.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Zmiana czasu systemowego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ChangeSystemTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-changesystemtime)

  To prawo użytkownika określa, którzy użytkownicy i grupy mogą zmieniać godzinę i datę w zegarze wewnętrznym komputera.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Tworzenie obiektów globalnych**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/CreateGlobalObjects](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createglobalobjects)

  To ustawienie zabezpieczeń określa, czy użytkownicy mogą tworzyć obiekty globalne, które są dostępne dla wszystkich sesji. Użytkownicy, którzy mogą tworzyć obiekty globalne, mogą mieć wpływ na procesy działające w ramach sesji innych użytkowników, co może prowadzić do awarii aplikacji lub uszkodzenia danych.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Utwórz plik stronicowania**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/plik stronicowania](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createpagefile)

  To prawo użytkownika określa, którzy użytkownicy i grupy mogą wywoływać wewnętrzny interfejs API w celu utworzenia i zmiany rozmiaru pliku stronicowania.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Utwórz trwałe obiekty udostępnione**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/CreatePermanentSharedObjects](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createpermanentsharedobjects)

  To prawo użytkownika określa, które konta mogą być używane przez procesy do tworzenia obiektu katalogu przy użyciu Menedżera obiektów.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Tworzenie łączy symbolicznych**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/CreateSymbolicLinks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createsymboliclinks)

  To prawo użytkownika określa, czy użytkownik może utworzyć link symboliczny z komputera, na którym są zalogowani.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Utwórz tokeny**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/Untoken](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createtoken)

  To prawo użytkownika określa, którzy użytkownicy/grupy mogą być używani przez procesy do tworzenia tokenów, które mogą być następnie używane w celu uzyskania dostępu do dowolnych zasobów lokalnych, gdy proces używa wewnętrznego interfejsu API do tworzenia tokenu dostępu.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Debugowanie programów**  
  **Domyślnie**: Nie skonfigurowano  
    Dostawca CSP: [UserRights/DebugPrograms](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-debugprograms)

  To prawo użytkownika określa, którzy użytkownicy mogą dołączać debuger do dowolnego procesu lub do jądra.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Odmów dostępu z sieci**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/DenyAccessFromNetwork](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-denyaccessfromnetwork)

  To prawo użytkownika określa, którzy użytkownicy nie mogą uzyskać dostępu do komputera za pośrednictwem sieci.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Odmowa logowania w trybie usługi**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/DenyLocalLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-denylocallogon)

  To ustawienie zabezpieczeń określa, które konta usług nie mogą zarejestrować procesu jako usługi.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Odmowa logowania za pomocą usług pulpitu zdalnego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/DenyRemoteDesktopServicesLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-denyremotedesktopserviceslogon)

  To prawo użytkownika określa, którzy użytkownicy i grupy nie mogą logować się jako klient Usługi pulpitu zdalnego.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Włącz delegowanie**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/EnableDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-enabledelegation)

 To prawo użytkownika określa, którzy użytkownicy mogą ustawić ustawienie zaufany dla delegowania dla obiektu użytkownika lub komputera.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Generowanie inspekcji zabezpieczeń**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/GenerateSecurityAudits](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-generatesecurityaudits)

  To prawo użytkownika określa, które konta mogą być używane przez proces do dodawania wpisów do dziennika zabezpieczeń. Dziennik zabezpieczeń służy do śledzenia nieautoryzowanego dostępu do systemu.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Personifikuj klienta**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ImpersonateClient](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-impersonateclient)

  Przypisanie tego użytkownika do użytkownika pozwala programom działającym w imieniu tego użytkownika na personifikację klienta. Wymaganie tego użytkownika dla tego rodzaju personifikacji uniemożliwia nieautoryzowanemu użytkownikowi nakłanianie klienta do nawiązania połączenia z usługą utworzoną przez siebie, a następnie personifikuje tego klienta, co może podwyższyć poziom uprawnień nieautoryzowanego użytkownika do poziomy administracyjne lub systemowe.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Zwiększ priorytet planowania**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/IncreaseSchedulingPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-increaseschedulingpriority)

  To prawo użytkownika określa, które konta mogą używać procesu z dostępem do właściwości zapisu do innego procesu, aby zwiększyć priorytet wykonywania przypisany do innego procesu.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Ładowanie i zwalnianie sterowników urządzeń**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/LoadUnloadDeviceDrivers](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-loadunloaddevicedrivers)

  To prawo użytkownika określa, którzy użytkownicy mogą dynamicznie ładować i zwalniać sterowniki urządzeń lub inny kod w trybie jądra.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Blokowanie stron w pamięci**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/LockMemory](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-lockmemory)

  To prawo użytkownika określa, które konta mogą używać procesu do przechowywania danych w pamięci fizycznej, co uniemożliwia systemowi stronicowanie danych na dysku wirtualnym.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Zarządzanie dziennikiem inspekcji i zabezpieczeń**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ManageAuditingAndSecurityLog](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-manageauditingandsecuritylog)

  To prawo użytkownika określa, którzy użytkownicy mogą określić opcje inspekcji dostępu do obiektów dla poszczególnych zasobów, takich jak pliki, Active Directory obiekty i klucze rejestru.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Wykonywanie zadań konserwacji woluminów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ManageVolume](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-managevolume)

  To prawo użytkownika określa, którzy użytkownicy i grupy mogą uruchamiać zadania konserwacji na woluminie, na przykład na zdalnej defragmentacji.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Modyfikowanie wartości środowiska oprogramowania układowego**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ModifyFirmwareEnvironment](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-modifyfirmwareenvironment)

  To prawo użytkownika określa, kto może modyfikować wartości środowiska oprogramowania układowego.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Modyfikuj etykietę obiektu**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ModifyObjectLabel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-modifyobjectlabel)

  To prawo użytkownika określa, które konta użytkowników mogą modyfikować etykietę integralności obiektów, takich jak pliki, klucze rejestru lub procesy należące do innych użytkowników.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Profilowanie pojedynczego procesu**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/ProfileSingleProcess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-profilesingleprocess)

  To prawo użytkownika określa, którzy użytkownicy mogą używać narzędzi do monitorowania wydajności do monitorowania wydajności procesów systemu.
  - **Nieskonfigurowany**
  - **Zezwalaj**

- **Zdalne zamykanie**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/RemoteShutdown](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-remoteshutdown)

  To prawo użytkownika określa, którzy użytkownicy mogą zamknąć komputer z lokalizacji zdalnej w sieci. Nieprawidłowe użycie tego prawa użytkownika może spowodować odmowę usługi.
  - **Nieskonfigurowany**
  - **Zezwalaj**
  
- **Przywracanie plików i katalogów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/RestoreFilesAndDirectories](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-restorefilesanddirectories)
  
  To prawo użytkownika określa, którzy użytkownicy mogą pomijać uprawnienia do plików, katalogów, rejestru i innych obiektów trwałych podczas przywracania kopii zapasowej plików i katalogów oraz określać, którzy użytkownicy mogą ustawiać prawidłowy podmiot zabezpieczeń jako właściciela obiektu.
  - **Nieskonfigurowany**
  - **Zezwalaj**
  
- **Przejęcie na własność plików lub obiektów**  
  **Domyślnie**: Nie skonfigurowano  
  Dostawca CSP: [UserRights/TakeOwnership](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-takeownership)

  To prawo użytkownika określa, którzy użytkownicy mogą przejąć własność dowolnego zabezpieczanego obiektu w systemie, w tym Active Directory obiektów, plików i folderów, drukarek, kluczy rejestru, procesów i wątków.
  - **Nieskonfigurowany**
  - **Zezwalaj**

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../configuration/device-profile-assign.md) i będziesz [monitorować jego stan](../configuration/device-profile-monitor.md).  

Skonfiguruj ustawienia ochrony punktu końcowego na urządzeniach z systemem [macOS](endpoint-protection-macos.md).  
