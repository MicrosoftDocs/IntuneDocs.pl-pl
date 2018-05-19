---
title: Dodawanie programu Endpoint Protection do systemu Windows 10 w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Na urządzeniach z systemem Windows 10 możesz użyć ustawień programu Endpoint Protection lub skonfigurować je, aby włączyć w usłudze Microsoft Intune usługę Windows Defender, w tym program Application Guard, zaporę, filtr SmartScreen, szyfrowanie i funkcję BitLocker, program Exploit Guard, kontrolę aplikacji, Centrum zabezpieczeń i zabezpieczenia na urządzeniach lokalnych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 069f71d75c0a9c7cec083a929f89a2b39bb4aac5
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Ustawienia programu Endpoint Protection dla systemu Windows 10 (i nowszych) w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil programu Endpoint Protection umożliwia kontrolowanie funkcji zabezpieczeń na urządzeniach z systemem Windows 10, takich jak funkcja BitLocker i usługa Windows Defender.

Skorzystaj z informacji w tym artykule podczas tworzenia profili programu Endpoint Protection. Aby skonfigurować program antywirusowy Windows Defender, zobacz temat [Ograniczenia dotyczące urządzeń z systemem Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus). 

> [!NOTE]
> Te ustawienia nie są obsługiwane w systemie Windows 10 w wersjach Home i Professional.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Podczas korzystania z przeglądarki Microsoft Edge program Windows Defender Application Guard chroni środowiska z witryn, które nie zostały zdefiniowane jako zaufane przez organizację. Gdy użytkownicy odwiedzają witryny, które nie zostały wymienione w granicach sieci izolowanej, witryny są otwierane w ramach sesji przeglądania wirtualnego w funkcji Hyper-V. Witryny są definiowane przez granicę sieci, którą można skonfigurować w konfiguracji urządzenia. 

Funkcja Application Guard jest dostępna tylko dla urządzeń z systemem Windows 10 (wersja 64-bitowa). Użycie tego profilu powoduje zainstalowanie składnika Win32 w celu aktywowania funkcji Application Guard.

- **Application Guard**: otwieranie niezatwierdzonych witryn w zwirtualizowanym kontenerze przeglądania funkcji Hyper-V.
- **Zachowanie schowka**: wybierz dozwolone akcje kopiowania i wklejania między komputerem lokalnym a przeglądarką wirtualną funkcji Application Guard.
- **Zawartość zewnętrzna w witrynach przedsiębiorstw**: blokowanie ładowania zawartości z niezatwierdzonych witryn internetowych.
- **Drukuj z przeglądarki wirtualnej**: zezwalanie drukarkom PDF, XPS, lokalnym i/lub sieciowym na drukowanie zawartości z przeglądarki wirtualnej.
- **Zbieraj dzienniki**: zbieranie dzienników dla zdarzeń występujących w sesji przeglądania funkcji Application Guard.
- **Zachowuj dane przeglądarki generowane przez użytkownika**: umożliwia zapisywanie danych użytkownika (na przykład haseł, ulubionych i plików cookie) utworzonych podczas wirtualnej sesji przeglądania funkcji Application Guard.
- **Przyspieszanie grafiki**: szybsze ładowanie witryn internetowych z dużą ilością grafiki podczas pracy w wirtualnej sesji przeglądania funkcji Application Guard. Witryny internetowe ładują się szybciej dzięki dostępowi do wirtualnego procesora GPU.
- **Pobierz pliki do systemu plików hosta**: umożliwia użytkownikom pobieranie plików ze zwirtualizowanej przeglądarki do systemu operacyjnego hosta.

## <a name="windows-defender-firewall"></a>Zapora Windows Defender

### <a name="global-settings"></a>Ustawienia globalne

Te ustawienia mają zastosowanie do wszystkich typów urządzeń.

- **Protokół transferu plików**: blokowanie stanowego protokołu FTP.
- **Czas bezczynności skojarzeń zabezpieczeń przed usunięciem**: skojarzenia zabezpieczeń są usuwane po wykryciu braku ruchu sieciowego przez *n* sek.
- **Kodowanie kluczy wstępnych**: kodowanie kluczy wstępnych przy użyciu kodowania UTF-8.
- **Wykluczenia IPsec**: konfigurowanie wykluczenia określonego ruchu z protokołu IPsec, w tym opcji **Odnajdywanie sąsiadujących kodów typu IPv6 protokołu ICMP**, **Protokół ICMP**, **Odnajdywanie routera kodów typu IPv6 protokołu ICMP** i **Ruch sieciowy DHCP IPv4 i IPv6**.
- **Weryfikacja listy odwołania certyfikatów**: ustawianie wartości określającej sposób wymuszania weryfikacji listy odwołania certyfikatów, w tym opcji **Wyłącz weryfikację listy CRL**, **Niepowodzenie weryfikacji listy CRL tylko w przypadku odwołanego certyfikatu** i **Niepowodzenie weryfikacji listy CRL przy dowolnym błędzie**.
- **Odpowiednio uzgodnij zestaw uwierzytelniania dla modułu kluczy**: ustawianie modułów kluczy w celu ignorowania całego zestawu uwierzytelniania, jeśli nie obsługują wszystkich pakietów uwierzytelniania w tym zestawie.
- **Kolejkowanie pakietów**: wprowadź sposób włączania skalowania oprogramowania po stronie odbierającej w przypadku zaszyfrowanego odbierania i przekazywania w postaci zwykłego tekstu dla scenariusza z bramą tunelu IPsec. To ustawienie zapewnia zachowanie kolejności pakietów.

### <a name="network-settings"></a>Ustawienia sieciowe

Te ustawienia mają zastosowanie do sieci określonych typów, w tym **sieci z domeną (w miejscu pracy)**, **sieci prywatnej (wykrywalnej)** i **sieci publicznej (niewykrywalnej)**.

#### <a name="general-settings"></a>Ustawienia ogólne

- **Zapora Windows Defender**: włączenie tego ustawienia powoduje blokowanie ruchu sieciowego.
- **Tryb niewidzialności**: blokowanie działania zapory w trybie niewidzialności. Blokowanie trybu niewidzialności pozwala również zablokować **wykluczanie pakietów zabezpieczonych przez protokół IPsec**.
- **Chronione**: włączenie tego ustawienia i ustawienia zapory powoduje blokowanie całego ruchu przychodzącego.
- **Odpowiedzi emisji pojedynczej na multiemisję/emisje**: blokowanie odpowiedzi emisji pojedynczej na multiemisję/emisje. Zazwyczaj nie chcesz otrzymywać odpowiedzi emisji pojedynczej na komunikaty multiemisji lub emisji. Te odpowiedzi mogą wskazywać na atak typu „odmowa usługi” (DOS) lub na to, że osoba atakująca próbuje sondować znany komputer na żywo.
- **Powiadomienia przychodzące**: blokowanie wyświetlania powiadomień użytkownikom, gdy nasłuchiwanie przez aplikację na porcie jest zablokowane.
- **Domyślna akcja dla połączeń przychodzących**: blokowanie domyślnej akcji, którą zapora wykonuje dla połączeń przychodzących.

#### <a name="rule-merging"></a>Scalanie reguł

- **Reguły zapory Windows Defender autoryzowanych aplikacji z magazynu lokalnego**: stosowanie autoryzowanych reguł zapory w magazynie lokalnym w celu rozpoznawania i wymuszania.
- **Globalne reguły zapory Windows Defender portów z magazynu lokalnego**: stosowanie globalnych reguł zapory portów w magazynie lokalnym w celu rozpoznawania i wymuszania.
- **Reguły zapory Windows Defender z magazynu lokalnego**: stosowanie globalnych reguł zapory w magazynie lokalnym w celu rozpoznawania i wymuszania.
- **Reguły protokołu IPsec z magazynu lokalnego**: stosowanie reguł zabezpieczeń połączeń z magazynu lokalnego, niezależnie od wersji reguł zabezpieczeń schematu lub połączenia.

## <a name="windows-defender-smartscreen-settings"></a>Ustawienia filtru Windows Defender SmartScreen

- **Filtr SmartScreen dla aplikacji i plików**: włącz filtr Windows SmartScreen na potrzeby wykonywania plików i uruchamiania aplikacji.
- **Wykonywanie niezweryfikowanych plików**: blokowanie użytkownikowi końcowemu możliwości uruchamiania plików, które nie zostały zweryfikowane przez filtr Windows SmartScreen.

## <a name="windows-encryption"></a>Szyfrowanie systemu Windows

### <a name="windows-settings"></a>Ustawienia systemu Windows

Dwa następujące ustawienia dotyczą wszystkich wersji systemu Windows 10:

- **Szyfruj urządzenia**: jeśli to ustawienie jest włączone, użytkownicy są monitowani o włączenie szyfrowania urządzenia. Ponadto użytkownicy zostaną poproszeni o potwierdzenie, że nie zostało włączone szyfrowanie od innego dostawcy. Jeśli szyfrowanie systemu Windows jest włączone, gdy inna metoda szyfrowania jest aktywna, urządzenie może pracować niestabilnie.
- **Szyfruj kartę pamięci**: włącz to ustawienie, aby zaszyfrować wszystkie wymienne karty pamięci używane przez urządzenie.


### <a name="bitlocker-base-settings"></a>Podstawowe ustawienia funkcji BitLocker

Podstawowe ustawienia to uniwersalne ustawienia funkcji BitLocker dla wszystkich typów dysków danych. Ustawienia zasad grupy funkcji BitLocker zarządzają zadaniami szyfrowania dysku lub opcjami konfiguracji, które użytkownik końcowy może modyfikować w przypadku wszystkich typów dysków z danymi.

- **Ostrzeżenie dotyczące innego szyfrowania dysku**: wyłączanie ostrzeżenia dotyczącego innego szyfrowania dysków na komputerach użytkowników końcowych.
- **Konfiguruj metody szyfrowania**: włącz to ustawienie, aby skonfigurować algorytmy szyfrowania na potrzeby systemu operacyjnego, danych i dysków wymiennych.
  - **Szyfrowanie dla dysków z systemami operacyjnymi**: wybierz metodę szyfrowania dla dysków z systemami operacyjnymi. Zaleca się użycie algorytmu XTS-AES.
  - **Szyfrowanie dla stałych dysków danych**: wybierz metodę szyfrowania dla stałych (wbudowanych) dysków danych. Zaleca się użycie algorytmu XTS-AES.
  - **Szyfrowanie dla wymiennych dysków danych**: wybierz metodę szyfrowania dla wymiennych dysków danych. Jeśli dysk wymienny jest używany z urządzeniami z systemem innym niż Windows 10, zaleca się użycie algorytmu AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Ustawienia funkcji BitLocker dla dysku z systemem operacyjnym

Te ustawienia dotyczą w szczególności dysków danych systemu operacyjnego.

- **Dodatkowe uwierzytelnianie podczas uruchamiania**: skonfiguruj wymagania dotyczące uwierzytelniania na potrzeby uruchamiania komputera, w tym użycie modułu TPM (Trusted Platform Module).
  - **Funkcja BitLocker z niezgodnym mikroukładem modułu TPM**
  - **Uruchamianie zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania mikroukładu modułu TPM.
  - **Numer PIN uruchamiania zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania numeru PIN podczas uruchamiania mikroukładu modułu TPM.
  - **Klucz uruchamiania zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania klucza podczas uruchamiania mikroukładu modułu TPM.
  - **Klucz i numer PIN uruchamiania zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania klucza i numeru PIN uruchamiania dla mikroukładu modułu TPM.
- **Minimalna długość numeru PIN**: włącz to ustawienie, aby skonfigurować minimalną długość numeru PIN uruchomienia modułu TPM.
  - **Minimalna liczba znaków**: wprowadź liczbę znaków wymaganą dla numeru PIN uruchomienia z przedziału **4**-**20** znaków.
- **Odzyskiwanie dysku systemu operacyjnego**: włącz to ustawienie, aby określić sposób odzyskiwania dysków z systemem operacyjnym chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.
  - **Agent odzyskiwania danych oparty na certyfikatach**: włącz to ustawienie, aby możliwe było używanie agentów odzyskiwania danych względem dysków z systemem operacyjnym chronionych przez funkcję BitLocker.
  - **Tworzenie hasła odzyskiwania przez użytkownika**: wybierz, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
  - **Tworzenie klucza odzyskiwania przez użytkownika**: wybierz, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
  - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker**: włącz to ustawienie, aby uniemożliwić użytkownikom wyświetlanie lub zmianę opcji odzyskiwania po włączeniu funkcji BitLocker.
  - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS**: umożliwia zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Active Directory.
  - **Informacje dotyczące odzyskiwania funkcji BitLocker przechowywane w usługach AD DS**: pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Active Directory. Wybierz spośród opcji:
    - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
    - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
  - **Przechowuj informacje dotyczące odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker**: włącz to ustawienie, aby uniemożliwić użytkownikom włączenie funkcji BitLocker, chyba że urządzenie jest przyłączone do domeny, a informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Active Directory.
- **Komunikat odzyskiwania i adres URL przed rozruchem**: włącz to ustawienie, aby skonfigurować komunikat i adres URL wyświetlane na ekranie odzyskiwania kluczy przed rozruchem.
  - **Komunikat odzyskiwania przed rozruchem**: pozwala określić sposób wyświetlania użytkownikom komunikatu odzyskiwania przed rozruchem. Wybierz spośród opcji:
    - **Użyj domyślnego komunikatu i adresu URL dotyczącego odzyskiwania**
    - **Użyj pustego komunikatu i adresu URL dotyczącego odzyskiwania**
    - **Użyj niestandardowego komunikatu dotyczącego odzyskiwania**
    - **Użyj niestandardowego adresu URL odzyskiwania**

### <a name="bitlocker-fixed-data-drive-settings"></a>Ustawienia stałych dysków danych w funkcji BitLocker

- **Dostęp do zapisu dla stałych dysków danych, które nie są chronione przez funkcję BitLocker**: jeśli to ustawienie jest włączone, ochrona za pomocą funkcji BitLocker musi być włączona na wszystkich stałych lub wbudowanych dyskach danych, aby możliwy był na nich zapis.
- **Odzyskiwanie dysku stałego**: włącz to ustawienie, aby określić sposób odzyskiwania dysków stałych chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.
  - **Agent odzyskiwania danych**: włącz to ustawienie, aby możliwe było używanie agentów odzyskiwania danych względem dysków stałych chronionych przez funkcję BitLocker.
  - **Tworzenie hasła odzyskiwania przez użytkownika**: pozwala określić, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
  - **Tworzenie klucza odzyskiwania przez użytkownika**: pozwala określić, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
  - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker**: włącz to ustawienie, aby uniemożliwić użytkownikom wyświetlanie lub zmianę opcji odzyskiwania po włączeniu funkcji BitLocker.
  - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS**: umożliwia zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Active Directory.
  - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS**: pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Active Directory. Wybierz spośród opcji:
    - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
    - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
  - **Przechowuj informacje dotyczące odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker**: włącz to ustawienie, aby uniemożliwić użytkownikom włączenie funkcji BitLocker, chyba że urządzenie jest przyłączone do domeny, a informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Ustawienia wymiennych dysków danych w funkcji BitLocker

- **Dostęp do zapisu dla wymiennych dysków danych, które nie są chronione przez funkcję BitLocker**: określ, czy dla wymiennych dysków magazynu wymagane jest szyfrowanie za pomocą funkcji BitLocker.
  - **Dostęp do zapisu dla urządzeń skonfigurowanych w innej organizacji**: określ, czy możliwy ma być zapis na wymiennych dyskach danych, które należą do innej organizacji.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Usługa [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) służy do zarządzania obszarem ataków i zmniejszania obszaru ataków w aplikacjach używanych przez pracowników.

### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków

- **Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows**

Ułatwia [blokowanie akcji i aplikacji](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) zwykle używanych przez złośliwe oprogramowanie wyszukujące luki w zabezpieczeniach do infekowania maszyn.

#### <a name="rules-to-prevent-office-macro-threats"></a>Reguły zapobiegania zagrożeniom ze strony makr pakietu Office

Zablokuj aplikacjom pakietu Office możliwość wykonywania następujących akcji:

- **Wstrzykiwanie do innych procesów przez aplikacje pakietu Office (bez wyjątków)**
- **Tworzenie zawartości wykonywalnej przez makra i aplikacje pakietu Office**
- **Uruchamianie procesów podrzędnych przez aplikacje pakietu Office**
- **Importowanie elementów Win32 z kodu makr w pakiecie Office**

#### <a name="rules-to-prevent-script-threats"></a>Reguły zapobiegania zagrożeniom ze strony skryptów

Blokowanie następujących elementów pomaga zapobiegać zagrożeniom ze strony skryptów:

- **Zaciemniony kod w plikach js/vbs/ps i makrach**
- **Wykonywanie ładunku pobranego z Internetu przez pliki js/vbs (bez wyjątków)**
- **Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI**
- **Niezaufane i niepodpisane procesy uruchamiane z dysku USB**
- **Pliki wykonywalne, które nie spełniają kryteriów występowania lub wieku albo nie są na liście zaufanych**

#### <a name="rules-to-prevent-email-threats"></a>Reguły zapobiegania zagrożeniom ze strony poczty e-mail

Zablokowanie następujących elementów ułatwia zapobieganie zagrożeniom związanym z pocztą e-mail:

- **Wykonywanie zawartości wykonywalnej (exe, dll, ps, js, vbs itd.) pochodzącej z wiadomości e-mail (poczty internetowej lub klienta poczty) (bez wyjątków)**

#### <a name="rules-to-protect-against-ransomware"></a>Reguły ochrony przed oprogramowaniem wymuszającym okup
- **Zaawansowana ochrona przed oprogramowaniem wymuszającym okup**

> [!TIP]
> Artykuł [Reduce attack surfaces with Windows Defender Exploit Guard (Zmniejszanie obszarów podatnych na ataki za pomocą funkcji Windows Defender Exploit Guard)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) zawiera więcej szczegółowych informacji dotyczących tych reguł.

#### <a name="attack-surface-reduction-exceptions"></a>Wyjątki zmniejszenia obszaru ataków

- **Pliki i foldery do wykluczenia z reguł zmniejszenia obszaru ataków**: zaimportuj/dodaj listę lokalizacji do wykluczenia ze skonfigurowanych reguł.

### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

Pomaga chronić cenne dane przed złośliwymi aplikacjami i zagrożeniami, takimi jak oprogramowanie wymuszające okup.

- **Ochrona folderów**: chroni pliki i foldery przed niepożądanymi zmianami przez złośliwe aplikacje. Możesz zaimportować **listę aplikacji, które mają dostęp do chronionych folderów**, lub dodać je ręcznie. Możesz również dodać **listę dodatkowych folderów, które muszą być chronione**, korzystając z przekazywania lub dodając je ręcznie.

### <a name="network-filtering"></a>Filtrowanie sieci

Blokuje połączenia wychodzące z dowolnych aplikacji do adresów IP/domen o niskiej reputacji.

### <a name="exploit-protection"></a>Exploit Protection

Blokowanie **edytowania interfejsu ochrony przed programami wykorzystującymi luki w zabezpieczeniach przez użytkowników** przez przekazywanie pliku XML, który umożliwia konfigurowanie ograniczeń pamięci, przepływu sterowania i zasad. Ustawienia w pliku XML mogą być używane do blokowania aplikacji przed programami wykorzystującymi luki w zabezpieczeniach.

Aby włączyć ochronę przed programami wykorzystującymi luki w zabezpieczeniach, utwórz plik XML reprezentujący wybrane ustawienia ograniczania ryzyka dla aplikacji i systemu. Możesz to zrobić przy użyciu jednej z dwóch metod:

 1. Program PowerShell: użyj jednego lub kilku z poleceń cmdlet programu PowerShell: Get-ProcessMitigation, Set-ProcessMitigation i ConvertTo-ProcessMitigationPolicy. Polecenia cmdlet służą do konfigurowania ustawień ograniczania ryzyka i eksportowania ich reprezentacji w formacie XML.

 2. Interfejs użytkownika usługi Windows Defender Security Center: W usłudze Windows Defender Security Center kliknij pozycję Sterowanie aplikacjami i przeglądarką, a następnie przewiń w dół wyświetlonego ekranu i znajdź funkcję Exploit Protection. Najpierw skonfiguruj ustawienia ograniczania ryzyka na kartach Ustawienia systemowe i Ustawienia programu. Następnie użyj linku Eksportuj ustawienia w dolnej części ekranu, aby wyeksportować ich reprezentację w formacie XML.

## <a name="windows-defender-application-control"></a>Kontrola aplikacji usługi Windows Defender

Użyj **zasad integralności kodu kontroli aplikacji**, aby wybrać dodatkowe aplikacje, które muszą być poddawane inspekcji przez usługę Windows Defender Security Center lub którym ta usługa może ufać. Składniki systemu Windows i wszystkie aplikacje ze Sklepu Windows są automatycznie zaufane do uruchomienia.

Aplikacje działające w trybie **tylko do inspekcji** nie są blokowane. Tryb **tylko do inspekcji** rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta.

Po włączeniu kontrolę aplikacji można wyłączyć tylko przez zmianę trybu z **Wymuszanie** na **Tylko inspekcja**. Zmiana trybu z **Wymuszanie** na **Nieskonfigurowane** skutkuje tym, że kontrola aplikacji nadal jest wymuszana na przypisanych urządzeniach.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard
Funkcja Windows Defender Credential Guard chroni przed atakami polegającymi na kradzieży poświadczeń. Izoluje ona wpisy tajne, tak aby tylko uprzywilejowane oprogramowanie systemu mogło uzyskiwać do nich dostęp.

Ustawienia funkcji **Credential Guard** obejmują następujące opcje:

- **Wyłączone**: zdalnie wyłącza funkcję Credential Guard, jeśli została ona wcześniej włączona za pomocą opcji **Włączone bez blokady UEFI**.
- **Włączone z blokadą UEFI**: zapewnia, że funkcji Credential Guard nie można wyłączyć za pomocą klucza rejestru ani zasad grupy.

    > [!NOTE]
    > Jeśli używasz tego ustawienia i chcesz później wyłączyć funkcję Credential Guard, musisz ustawić zasady grupy na **Wyłączone**. Musisz również fizycznie wyczyścić informacje o konfiguracji interfejsu UEFI z każdego komputera. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

- **Włączone bez blokady UEFI**: umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 w wersji 1511 lub nowszej.

Po włączeniu funkcji Credential Guard są również włączane następujące wymagane funkcje:

- **Zabezpieczenia oparte na wirtualizacji** (VBS): funkcja włączana podczas następnego rozruchu. Zabezpieczenia oparte na wirtualizacji używają funkcji Hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń.
- **Bezpieczny rozruch z bezpośrednim dostępem do pamięci**: włącza zabezpieczenia VBS z ochroną przy użyciu funkcji bezpiecznego rozruchu i bezpośredniego dostępu do pamięci (DMA). Ochrona DMA wymaga obsługi sprzętowej i można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach.

## <a name="windows-defender-security-center"></a>Windows Defender Security Center

Aplikacja usługi Windows Defender Security Center działa jako osobna aplikacja lub proces z każdej z poszczególnych funkcji. Wyświetla ona powiadomienia za pośrednictwem centrum akcji. Pełni rolę modułu zbierającego lub jednego miejsca służącego do wyświetlania stanu oraz wykonywania niektórych czynności konfiguracyjnych dla każdej funkcji. Dowiedz się więcej z dokumentacji [usługi Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplikacja i powiadomienia usługi Windows Defender Security Center

Zablokuj dostęp użytkowników końcowych do różnych obszarów aplikacji Windows Defender Security Center. Ukrywanie sekcji spowoduje również blokowanie pokrewnych powiadomień.

- **Ochrona przed wirusami i zagrożeniami**
- **Wydajność i kondycja urządzenia**
- **Zapora i ochrona sieci**
- **Kontrola aplikacji i przeglądarki**
- **Opcje rodziny**
- **Powiadomienia z wyświetlanych obszarów aplikacji**: wybierz, które powiadomienia mają być wyświetlane dla użytkowników końcowych. Powiadomienia niekrytyczne obejmują podsumowania działania programu antywirusowego Windows Defender, w tym powiadomienia po zakończeniu skanowania. Wszystkie pozostałe powiadomienia są traktowane jako krytyczne.

#### <a name="it-contact-information"></a>Informacje kontaktowe działu IT

Podaj informacje kontaktowe działu IT do wyświetlania w aplikacji Windows Defender Security Center i powiadomieniach aplikacji. Można wybrać opcję **Wyświetlaj w aplikacji i powiadomieniach**, **Wyświetlaj tylko w aplikacji**, **Wyświetlaj tylko w powiadomieniach** lub **Nie wyświetlaj**. Należy wprowadzić **nazwę organizacji IT** i co najmniej jedną z następujących opcji kontaktu:

- **Numer telefonu lub identyfikator Skype działu IT**
- **Adres e-mail działu IT**
- **Adres URL witryny internetowej pomocy technicznej**

## <a name="local-device-security-options"></a>Opcje lokalnych zabezpieczeń urządzeń

Te opcje umożliwiają konfigurowanie ustawień zabezpieczeń lokalnych na urządzeniach z systemem Windows 10.

### <a name="accounts"></a>Konta

- **Dodaj nowe konta Microsoft**: uniemożliwia użytkownikom dodawanie nowych kont Microsoft na tym komputerze.
- **Zdalne logowanie bez hasła**: włączanie kont lokalnych, które nie są chronione hasłem, w celu logowania się z lokalizacji innych niż urządzenie fizyczne.

#### <a name="admin"></a>Administracja

- **Konto administratora lokalnego**: określanie, czy konto administratora lokalnego jest włączone, czy wyłączone.
- **Zmień nazwę konta administratora**: definiowanie innej nazwy konta do skojarzenia z identyfikatorem zabezpieczeń (SID) dla konta administratora.

#### <a name="guest"></a>Gość

- **Konto gościa**: określanie, czy konto gościa jest włączone, czy wyłączone.
- **Zmień nazwę konta gościa**: definiowanie innej nazwy konta do skojarzenia z identyfikatorem zabezpieczeń (SID) dla konta gościa.

### <a name="devices"></a>Devices

- **Oddokuj urządzenie bez logowania**: uniemożliwia oddokowanie komputera przenośnego bez konieczności logowania.
- **Instaluj sterowniki drukarek udostępnionych**: ograniczanie instalowania sterowników drukarek w ramach łączenia z drukarką udostępnioną tylko do administratorów.
- **Ogranicz dostęp do dysku CD-ROM do aktywnego użytkownika lokalnego**: włączenie tego ustawienia umożliwia tylko interaktywnie zalogowanemu użytkownikowi uzyskiwanie dostępu do nośników CD-ROM
- **Formatowanie i wysuwanie nośnika wymiennego**: definiowanie, kto może formatować i wysuwać nośnik wymienny systemu plików NTFS:
  - **Nieskonfigurowany**
  - **Administratorzy i użytkownicy zaawansowani**
  - **Administratorzy i użytkownicy interaktywni**

### <a name="interactive-logon"></a>Logowanie interakcyjne

- **Minuty braku aktywności ekranu blokady przed aktywowaniem wygaszacza ekranu**: definiowanie maksymalnej liczby minut braku aktywności na ekranie logowania pulpitu interaktywnego przed uruchomieniem wygaszacza ekranu.
- **Wymagaj kombinacji CTRL+ALT+DEL do zalogowania**: aby użytkownik mógł się zalogować, należy nacisnąć kombinację klawiszy CTRL+ALT+DEL.
- **Zachowanie przy usuwaniu karty inteligentnej**: określa, co się stanie, gdy karta inteligentna zalogowanego użytkownika zostanie usunięta z czytnika kart inteligentnych.
Dalsze szczegóły można znaleźć w temacie dotyczącym [opcji zabezpieczeń LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior).

#### <a name="display"></a>Wyświetlanie

- **Informacje o użytkowniku na ekranie blokady**: konfigurowanie informacji o użytkowniku wyświetlanych po zablokowaniu sesji. Jeśli nie zostaną one skonfigurowane, będzie pokazywana nazwa wyświetlana użytkownika, domena i nazwa użytkownika.
  - **Tylko nazwa wyświetlana użytkownika**
  - **Nie wyświetlaj informacji o użytkowniku**
  - **Nieskonfigurowane**: nazwa wyświetlana użytkownika, domena i nazwa użytkownika
- **Ukryj ostatnio zalogowanego użytkownika**: nie jest wyświetlana nazwa użytkownika ostatniej osoby, która zalogowała się na tym urządzeniu.
- **Ukryj nazwę użytkownika podczas logowania**: nazwa użytkownika osoby logującej się do tego urządzenia nie jest wyświetlana po wprowadzeniu poświadczeń i przed wyświetleniem pulpitu urządzenia.
- **Tytuł komunikatu logowania**: ustaw tytuł komunikatu dla użytkowników próbujących się zalogować.
- **Tekst komunikatu logowania**: ustaw tekst komunikatu dla użytkowników próbujących się zalogować.

### <a name="network-access-and-security"></a>Dostęp do sieci i jej zabezpieczenia

- **Dostęp anonimowy do nazwanych potoków i udziałów**: ogranicza dostęp anonimowy do ustawień udziałów i nazwanych potoków. Dotyczy ustawień, do których można uzyskiwać anonimowy dostęp.
- **Anonimowe wyliczanie kont SAM**: umożliwia użytkownikom anonimowym wyliczanie kont SAM. System Windows pozwala użytkownikom anonimowym na wyliczanie nazw kont domeny i udziałów sieciowych.
- **Anonimowe wyliczanie kont SAM i udziałów**: możliwość blokowania anonimowego wyliczania kont SAM i udziałów. System Windows pozwala użytkownikom anonimowym na wyliczanie nazw kont domeny i udziałów sieciowych.
- **Wartość skrótu programu LAN Manager przechowywana przy zmianie hasła**: podczas kolejnej zmiany hasła wybierz, czy wartość skrótu programu LAN Manager (LM) dla nowego hasła ma być przechowywana. Nie jest ona przechowywana domyślnie.
- **Żądania uwierzytelniania protokołu PKU2U**: blokowanie żądań uwierzytelniania protokołu PKU2U do tego urządzenia w celu używania tożsamości online.
- **Ograniczanie połączeń zdalnych zdalnego wywołania procedury z rozwiązaniem SAM**: edytowanie ciągu języka Security Descriptor Definition Language w celu zezwolenia użytkownikom i grupom na wykonywanie zdalnych wywołań do rozwiązania SAM lub odmowy takiego zezwolenia.
- **Deskryptor zabezpieczeń**

### <a name="recovery-console-and-shutdown"></a>Konsola odzyskiwania i zamykanie

- **Wyczyść plik stronicowania pamięci wirtualnej podczas zamykania**: czyszczenie pliku stronicowania pamięci wirtualnej podczas wyłączania urządzenia.
- **Zamknięcie bez logowania**: blokowanie opcji wyłączania komputera z ekranu logowania systemu Windows. W takim przypadku użytkownicy muszą mieć możliwość pomyślnego zalogowania się do komputera przed zamknięciem systemu.

### <a name="user-account-control"></a>Kontrola konta użytkownika

- **Integralność automatyzacji interfejsu użytkownika bez bezpiecznej lokalizacji**: umożliwianie uruchamiania aplikacji z niezabezpieczonych lokalizacji przy użyciu poziomu integralności UIAccess.
- **Wirtualizuj błędy zapisu plików i rejestru w lokalizacji użytkownika**: określanie, czy błędy zapisu aplikacji są przekierowywane do zdefiniowanych lokalizacji w rejestrze i systemie plików, lub czy będzie występować błąd aplikacji.
- **Podnieś poziom uprawnień tylko w przypadku plików wykonywalnych, które zostały podpisane i zweryfikowane**: wymuszanie walidacji ścieżki certyfikacji PKI dla danego pliku wykonywalnego przed zezwoleniem na jego uruchomienie.

#### <a name="uia-elevation-prompt-behavior-settings"></a>Ustawienia zachowania monitu o podniesienie uprawnień automatyzacji interfejsu użytkownika

- **Monit o podniesienie uprawnień dla administratorów**: definiowanie zachowania monitu o podniesienie uprawnień dla administratorów w trybie zatwierdzania przez administratora:
  - **Podnieś bez monitowania**
  - **Monituj o podanie poświadczeń na bezpiecznym pulpicie**
  - **Monituj o zgodę na bezpiecznym pulpicie**
  - **Monituj o poświadczenia**
  - **Monituj o zgodę**
  - **Nieskonfigurowane**: monitowanie o zgodę w przypadku plików binarnych z systemem innym niż Windows
- **Monit o podniesienie uprawnień dla użytkowników standardowych**: definiowanie zachowania monitu o podniesienie uprawnień dla użytkowników standardowych:
  - **Automatycznie odrzucaj żądania podniesienia uprawnień**
  - **Monituj o podanie poświadczeń na bezpiecznym pulpicie**
  - **Nieskonfigurowane**: monitowanie o podanie poświadczeń
- **Kieruj monity o podniesienie uprawnień do interaktywnego pulpitu użytkownika**: umożliwianie przenoszenia wszystkich żądań podniesienia uprawnień do interaktywnego pulpitu użytkownika, a nie do bezpiecznego pulpitu. Używane są ustawienia zasad zachowania monitu dla administratorów i użytkowników standardowych.
- **Monituj o podniesienie poziomu uprawnień w przypadku instalacji aplikacji**: instalacje aplikacji, które wymagają podniesionych uprawnień, będą monitować o podanie poświadczeń administratora.
- **Monituj o podniesienie poziomu uprawnień automatyzacji interfejsu użytkownika bez bezpiecznego pulpitu**: zezwalanie aplikacjom z poziomem UIAccess na monitowanie o podniesienie uprawnień bez używania bezpiecznego pulpitu.

#### <a name="admin-approval-mode-settings"></a>Ustawienia trybu zatwierdzania przez administratora

- **Tryb zatwierdzania przez administratora dla wbudowanego administratora** : definiuje, czy wbudowane konto administratora używa trybu zatwierdzania przez administratora, czy też uruchamia wszystkie aplikacje z pełnymi uprawnieniami administratora.
- **Uruchom wszystkich administratorów w trybie zatwierdzania przez administratora**: definiuje, czy włączono tryb zatwierdzania przez administratora i wszystkie ustawienia zasad funkcji Kontrola konta użytkownika.

### <a name="microsoft-network-client"></a>Klient sieci firmy Microsoft

- **Podpisuj cyfrowo komunikację (za zgodą serwera)**: określa, czy klient SMB podejmuje próbę negocjowania podpisywania pakietów SMB. W przypadku włączenia tej opcji (ustawienie domyślne) klient sieci firmy Microsoft żąda od serwera podpisania pakietów SMB podczas konfigurowania sesji. Jeśli podpisywanie pakietów zostało włączone na serwerze, jest negocjowane podpisywanie pakietów. Jeśli te zasady zostały wyłączone, klient SMB nigdy nie negocjuje podpisywania pakietów SMB.
- **Wyślij niezaszyfrowane hasło w celu nawiązania połączenia z innymi serwerami SMB**: po włączeniu tej opcji przekierowanie bloku komunikatów serwera (SMB) może wysyłać hasła w postaci zwykłego tekstu do serwerów SMB firm innych niż Microsoft, które nie obsługują szyfrowania hasła podczas uwierzytelniania.

### <a name="microsoft-network-server"></a>Serwer sieci Microsoft

- **Podpisuj cyfrowo komunikację (za zgodą klienta)**: określa, czy serwer SMB negocjuje podpisywanie pakietów SMB z klientami, którzy wykonują żądanie. Po włączeniu tej opcji serwer sieci Microsoft negocjuje podpisywanie pakietów SMB zgodnie z żądaniem klienta. Oznacza to, że jeśli podpisywanie pakietów zostało włączone na kliencie, jest negocjowane podpisywanie pakietów. Jeśli ta opcja jest wyłączona (ustawienie domyślne), klient SMB nigdy nie negocjuje podpisywania pakietów SMB.
- **Podpisuj cyfrowo komunikację (zawsze)**: określa, czy podpisywanie pakietów jest wymagane przez składnik serwera SMB. W przypadku włączenia tej opcji serwer sieci Microsoft nie komunikuje się z klientem sieci Microsoft, chyba że klient zgadza się przeprowadzić podpisywanie pakietów SMB. Jeśli ta opcja jest wyłączona (ustawienie domyślne), podpisywanie pakietów jest negocjowane między klientem a serwerem.

## <a name="next-steps"></a>Następne kroki

Aby przypisać ten profil do grup, zobacz [Jak przypisywać profile urządzeń](device-profile-assign.md).
