---
title: Ustawienia ochrony dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Na urządzeniach z systemem Windows 10 możesz użyć ustawień programu Endpoint Protection lub skonfigurować je, aby włączyć w usłudze Microsoft Intune usługę Windows Defender, w tym program Application Guard, zaporę, filtr SmartScreen, szyfrowanie i funkcję BitLocker, program Exploit Guard, kontrolę aplikacji, Centrum zabezpieczeń i zabezpieczenia na urządzeniach lokalnych.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4c2df888e146a7f240530e5cbc6628dbce34cb61
ms.sourcegitcommit: b0b1030017e741d92c508130447a8242d9ad7a51
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58343001"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Ustawienia systemu Windows 10 (oraz nowszych wersji) służące do ochrony urządzeń przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Microsoft Intune zawiera wiele ustawień pomocnych w ochronie urządzeń. W tym artykule opisano wszystkie ustawienia, które można włączyć i skonfigurować na urządzeniach z systemem Windows 10 lub nowszym. Te ustawienia są tworzone w profilu konfiguracji ochrony punktu końcowego w usłudze Intune w celu sterowania zabezpieczeniami i obejmują m.in. funkcję BitLocker i usługę Windows Defender.

Aby skonfigurować program antywirusowy Windows Defender, zobacz [Ograniczenia dotyczące urządzeń z systemem Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia ochrony punktu końcowego](endpoint-protection-configure.md).

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Obsługiwany w następujących wersjach systemu Windows 10:

- Enterprise
- Professional

Podczas korzystania z przeglądarki Microsoft Edge program Windows Defender Application Guard chroni Twoje środowisko przed witrynami, które nie zostały uznane za zaufane przez Twoją organizację. Gdy użytkownicy odwiedzają witryny, które nie zostały wymienione w granicach sieci izolowanej, witryny te są otwierane w ramach sesji przeglądania wirtualnego funkcji Hyper-V. Witryny są definiowane przez granicę sieci, która jest konfigurowana w konfiguracji urządzenia.

Funkcja Application Guard jest dostępna tylko dla urządzeń z systemem Windows 10 (wersja 64-bitowa). Użycie tego profilu powoduje zainstalowanie składnika Win32 w celu aktywowania funkcji Application Guard.

- **Application Guard**: opcja **Włącz dla przeglądarki Edge** włącza tę funkcję, która otwiera niezaufane witryny w zwirtualizowanym kontenerze przeglądania funkcji Hyper-V. **Nieskonfigurowane** (ustawienie domyślne) oznacza, że wszystkie witryny (zaufanych i niezaufanych) otworzy się na urządzeniu.
- **Zachowanie schowka**: wybierz dozwolone akcje kopiowania i wklejania między komputerem lokalnym a przeglądarką wirtualną funkcji Application Guard.
- **Zawartość zewnętrzna w witrynach przedsiębiorstw**: **Blokuj** — blokowanie ładowania zawartości z niezatwierdzonych witryn internetowych. **Nie skonfigurowano** (ustawienie domyślne) — witryny inne niż przedsiębiorstw można otwierać na urządzeniu.
- **Drukuj z przeglądarki wirtualnej**: wybierz opcję **Zezwalaj**, aby zezwolić drukarkom PDF, XPS, lokalnym i/lub sieciowym na drukowanie zawartości z przeglądarki wirtualnej. **Nie skonfigurowano** (ustawienie domyślne) — wyłączenie wszystkich funkcji drukowania.
- **Zbieraj dzienniki**: **Zezwalaj** — zbieranie dzienników dla zdarzeń występujących w sesji przeglądania funkcji Application Guard. **Nie skonfigurowano** (ustawienie domyślne) — żadne dzienniki w sesji przeglądania nie są zbierane.
- **Zachowuj dane przeglądarki generowane przez użytkownika**: opcja **Zezwalaj** powoduje zapisywanie danych użytkownika (na przykład haseł, ulubionych i plików cookie) utworzonych podczas wirtualnej sesji przeglądania funkcji Application Guard. **Nie skonfigurowano** (ustawienie domyślne) — odrzucanie plików i danych pobranych przez użytkownika przy ponownym uruchomieniu urządzenia lub gdy użytkownik wylogowuje się.
- **Przyspieszanie grafiki**: opcja **Włącz** umożliwia szybsze ładowanie witryn internetowych z dużą ilością grafiki oraz wideo dzięki dostępowi do wirtualnego procesora GPU. **Nie skonfigurowano** (ustawienie domyślne) — używa procesora CPU urządzenia do przetwarzania grafiki, nie używa wirtualnego procesora GPU.
- **Pobierz pliki do systemu plików hosta**: **Włącz** — umożliwienie użytkownikom pobierania plików ze zwirtualizowanej przeglądarki do systemu operacyjnego hosta. **Nie skonfigurowano** (ustawienie domyślne) — przechowywanie plików lokalnie na urządzeniu, pliki nie są pobierane do systemu plików hosta.

## <a name="windows-defender-firewall"></a>Zapora Windows Defender

Obsługiwany w następujących wersjach systemu Windows 10:
- Domowy
- Professional
- Służbowy
- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise

### <a name="global-settings"></a>Ustawienia globalne

Te ustawienia mają zastosowanie do wszystkich typów urządzeń.

- **Protokół transferu plików**: **Blokuj** — wyłączenie stanowego protokołu FTP. **Nie skonfigurowano** (ustawienie domyślne) — zapora wykonuje filtrowanie stanowego protokołu FTP, aby zezwalać na dodatkowe połączenia.
- **Czas bezczynności skojarzeń zabezpieczeń przed usunięciem**: skojarzenia zabezpieczeń są usuwane po wykryciu braku ruchu sieciowego przez *n* sek. Wprowadź czas bezczynności w sekundach.
- **Kodowanie kluczy wstępnych**: opcja **Włącz** umożliwia używanie kodowania UTF-8 dla kluczy wstępnych. **Nie skonfigurowano** (ustawienie domyślne) — używanie wartości magazynu lokalnego.
- **Wykluczenia IPsec**: konfigurowanie wykluczenia określonego ruchu z protokołu IPsec, w tym opcji:
  - **Odnajdywanie sąsiadujących kodów typu IPv6 protokołu ICMP**
  - **Protokół ICMP**
  - **Odnajdywanie routera kodów typu IPv6 protokołu ICMP**
  - **Ruch sieciowy DHCP IPv4 i IPv6**
- **Weryfikacja listy odwołania certyfikatów**: Wybierz, jak urządzenie sprawdza listy odwołania certyfikatów. Dostępne opcje: **Wyłącz weryfikację listy CRL**, **Niepowodzenie weryfikacji listy CRL tylko w przypadku odwołanego certyfikatu** i **Niepowodzenie weryfikacji listy CRL przy dowolnym błędzie**.
- **Odpowiednio uzgodnij zestaw uwierzytelniania dla modułu kluczy**: **Włącz**, aby moduły kluczy MUSIAŁY ignorować tylko pakiety uwierzytelniania, których nie obsługują. W przypadku ustawienia **Nie skonfigurowano** moduły kluczy MUSZĄ ignorować cały zestaw uwierzytelniania, jeśli nie obsługują wszystkich pakietów uwierzytelniania określonych w zestawie.
- **Kolejkowanie pakietów**: wprowadź sposób włączania skalowania oprogramowania po stronie odbierającej w przypadku zaszyfrowanego odbierania i przekazywania w postaci zwykłego tekstu dla scenariusza z bramą tunelu IPsec. To ustawienie potwierdza zachowanie kolejności pakietów.

### <a name="network-settings"></a>Ustawienia sieciowe

Te ustawienia mają zastosowanie do sieci określonych typów, w tym **sieci z domeną (w miejscu pracy)**, **sieci prywatnej (wykrywalnej)** i **sieci publicznej (niewykrywalnej)**.

#### <a name="general-settings"></a>Ustawienia ogólne  
- **Zapora Windows Defender**: opcja **Włącz** powoduje włączenie zapory i zabezpieczeń zaawansowanych. **Nie skonfigurowano** (ustawienie domyślne) — zezwala na cały ruch sieciowy niezależnie od ustawień innych zasad.
- **Tryb niewidzialności**: **Blokuj** — blokowanie działania zapory w trybie niewidzialności. Blokowanie trybu niewidzialności pozwala również zablokować **wykluczanie pakietów zabezpieczonych przez protokół IPsec**. **Nie skonfigurowano** (ustawienie domyślne) — pozwala na działanie zapory w trybie niewidzialności, co pomaga zapobiegać odpowiedziom na żądania sondowania.
- **Z osłoną**: **Blokuj** —powoduje wyłączenie tej funkcji. **Nie skonfigurowano** (ustawienie domyślne) — włącza to ustawienie. Gdy to ustawienie i Zapora Windows Defender są włączone, cały ruch przychodzący jest blokowany bez względu na inne ustawienia zasad.
- **Odpowiedzi emisji pojedynczej na multiemisję/emisje**: **Blokuj** — uniemożliwia odpowiedzi emisji pojedynczej na multiemisję/emisje. Zazwyczaj nie chcesz otrzymywać odpowiedzi emisji pojedynczej na komunikaty multiemisji lub emisji. Te odpowiedzi mogą wskazywać na atak typu „odmowa usługi” (DOS) lub na to, że osoba atakująca próbuje sondować znany komputer na żywo. **Nie skonfigurowano** (ustawienie domyślne) — włącza to ustawienie.
- **Powiadomienia przychodzące**: **Blokuj** — wyłącza wyświetlanie powiadomień użytkownikom, gdy nasłuchiwanie przez aplikację na porcie jest zablokowane. **Nie skonfigurowano** (ustawienie domyślne) — włącza to ustawienie i powiadomienia mogą być wyświetlane użytkownikom, gdy nasłuchiwanie przez aplikację na porcie jest zablokowane.
- **Domyślna akcja dla połączeń przychodzących**: opcja **Blokuj** powoduje blokowanie domyślnej akcji, którą zapora wykonuje dla połączeń przychodzących. **Nie skonfigurowano** (ustawienie domyślne) — domyślna akcja zapory jest uruchamiana dla połączeń przychodzących.

#### <a name="rule-merging"></a>Scalanie reguł

- **Reguły zapory Windows Defender autoryzowanych aplikacji z magazynu lokalnego**: opcja **Włącz** powoduje stosowanie reguł zapory w magazynie lokalnym, które będą uznawane i wymuszane. **Nie skonfigurowano** (ustawienie domyślne) — autoryzowane reguły zapory w magazynie lokalnym są ignorowane i nie są wymuszane.
- **Globalne reguły zapory Windows Defender portów z magazynu lokalnego**: opcja **Włącz** powoduje stosowanie globalnych reguł portów zapory w magazynie, które będą uznawane i wymuszane. **Nie skonfigurowano** (ustawienie domyślne) — globalne reguły zapory portów w magazynie lokalnym są ignorowane i nie są wymuszane.
- **Reguły zapory Windows Defender z magazynu lokalnego**: opcja **Włącz** powoduje stosowanie globalnych reguł zapory w magazynie lokalnym, które będą uznawane i wymuszane. **Nie skonfigurowano** (ustawienie domyślne) — reguły zapory z magazynu lokalnego są ignorowane i nie są wymuszane.
- **Reguły protokołu IPsec z magazynu lokalnego**: opcja **Włącz** powoduje stosowanie reguł zabezpieczeń połączeń z magazynu lokalnego niezależnie od wersji reguł zabezpieczeń schematu lub połączenia. **Nie skonfigurowano** (ustawienie domyślne) — reguły zabezpieczeń połączeń z magazynu lokalnego są ignorowane i nie są wymuszane, niezależnie od wersji reguł zabezpieczeń schematu lub połączenia.

## <a name="windows-defender-smartscreen-settings"></a>Ustawienia filtru Windows Defender SmartScreen

Obsługiwane w następujących wersjach systemu Windows 10 z zainstalowaną przeglądarką Microsoft Edge:
- Domowy
- Professional
- Służbowy
- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise

**Ustawienia**:

- **Filtr SmartScreen dla aplikacji i plików**: **Włącz** — włącza filtr Windows SmartScreen na potrzeby wykonywania plików i uruchamiania aplikacji. Filtr SmartScreen jest opartym na chmurze składnikiem chroniącym przed wyłudzaniem informacji i złośliwym oprogramowaniem. **Nie skonfigurowano** (ustawienie domyślne) — wyłącza filtr SmartScreen.
- **Wykonywanie niezweryfikowanych plików**: **Blokuj** — blokowanie użytkownikom końcowym możliwości uruchamiania plików, które nie zostały zweryfikowane przez filtr Windows SmartScreen. **Nie skonfigurowano** (ustawienie domyślne) — powoduje wyłączenie tej funkcji i umożliwia użytkownikom końcowym uruchamianie plików, które nie zostały zweryfikowane.

## <a name="windows-encryption"></a>Szyfrowanie systemu Windows

### <a name="windows-settings"></a>Ustawienia systemu Windows

Obsługiwany w następujących wersjach systemu Windows 10:

- Professional
- Służbowy
- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise

**Ustawienia**:

- **Szyfruj urządzenia**: **Wymagaj** — użytkownicy są monitowani o włączenie szyfrowania urządzenia. W zależności od wersji systemu Windows i konfiguracji systemu użytkownikom może być wyświetlany jeden z następujących monitów:  
  - Monit o potwierdzenie, że nie włączono szyfrowania od innego dostawcy
  - Monit o wyłączenie szyfrowania dysków funkcją Bitlocker, a następnie ponowne włączenie funkcji Bitlocker
    
    Jeśli szyfrowanie systemu Windows jest włączone, gdy inna metoda szyfrowania jest aktywna, urządzenie może pracować niestabilnie. 
- **Szyfruj kartę pamięci (tylko urządzenia mobilne)**: **Wymagaj** — wymagane będzie szyfrowanie wszystkich wymiennych kart pamięci używanych przez urządzenie. **Nie skonfigurowano** (ustawienie domyślne) — nie wymaga szyfrowania karty pamięci i nie monituje użytkownika o włączenie szyfrowania. To ustawienie dotyczy tylko urządzeń z systemem Windows 10 Mobile.

### <a name="bitlocker-base-settings"></a>Podstawowe ustawienia funkcji BitLocker

Obsługiwany w następujących wersjach systemu Windows 10:

- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise
- Professional

Podstawowe ustawienia to uniwersalne ustawienia funkcji BitLocker dla wszystkich typów dysków danych. Te ustawienia zarządzają zadaniami szyfrowania dysku lub opcjami konfiguracji, które użytkownik końcowy może modyfikować w przypadku wszystkich typów dysków z danymi.

- **Ostrzeżenie dotyczące innego szyfrowania dysku**: wybranie wartości **Blokuj** spowoduje wyłączenie ostrzeżenia dotyczącego używania innej usługi szyfrowania dysku na urządzeniu. Ustawienie na wartość **Nie skonfigurowano** (ustawienie domyślne) zezwala na wyświetlanie ostrzeżeń.
    - **Zezwolić użytkownikom standardowym włączyć szyfrowanie w usłudze Azure AD Join**: po wybraniu **Zezwalaj**, standardowych użytkowników/użytkowników niebędących administratorami można włączyć szyfrowanie funkcją BitLocker, gdy użytkownik jest zalogowany. To ustawienie dotyczy tylko urządzeń dołączonych do usługi Azure Active Directory (Azure ADJ, Azure Active Directory Joined). Pozycja **Nieskonfigurowane** zezwala tylko administratorom na włączanie szyfrowania przy użyciu funkcji BitLocker na urządzeniu.
      
      To ustawienie dotyczy tylko urządzeń dołączonych do usługi Azure Active Directory (Azure ADJ, Azure Active Directory Joined). Wymaga ono również, aby ustawienie **Ostrzeżenie dotyczące innego szyfrowania dysku** miało wartość **Blokuj**.
- **Konfiguruj metody szyfrowania**: **włącz** to ustawienie, aby skonfigurować algorytmy szyfrowania na potrzeby systemu operacyjnego, danych i dysków wymiennych. W przypadku ustawienia tej opcji na wartość **Nie skonfigurowano** (ustawienie domyślne) funkcja BitLocker używa 128-bitowego szyfrowania XTS-AES jako domyślnej metody szyfrowania lub używa metody szyfrowania określonej przez dowolny skrypt instalacji.
  - **Szyfrowanie dla dysków z systemami operacyjnymi**: wybierz metodę szyfrowania dla dysków z systemami operacyjnymi. Zaleca się użycie algorytmu XTS-AES.
  - **Szyfrowanie dla stałych dysków danych**: wybierz metodę szyfrowania dla stałych (wbudowanych) dysków danych. Zaleca się użycie algorytmu XTS-AES.
  - **Szyfrowanie dla wymiennych dysków danych**: wybierz metodę szyfrowania dla wymiennych dysków danych. Jeśli dysk wymienny jest używany z urządzeniami z systemem innym niż Windows 10, zaleca się użycie algorytmu AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Ustawienia funkcji BitLocker dla dysku z systemem operacyjnym
Obsługiwany w następujących wersjach systemu Windows 10:

- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise
- Professional

Te ustawienia dotyczą w szczególności dysków danych systemu operacyjnego.

- **Dodatkowe uwierzytelnianie podczas uruchamiania**: wybierz wartość **Wymagaj**, aby skonfigurować wymagania dotyczące uwierzytelniania na potrzeby uruchamiania komputera, w tym użycie modułu TPM (Trusted Platform Module). Wybierz wartość **Nie skonfigurowano** (ustawienie domyślne), aby skonfigurować tylko podstawowe opcje na urządzeniach z modułem TPM.
  - **Funkcja BitLocker z niezgodnym mikroukładem modułu TPM**: **Blokuj** (wyłącz) — blokowanie używania funkcji BitLocker, gdy urządzenie nie ma zgodnego mikroukładu modułu TPM. **Nie skonfigurowano** — użytkownicy mogą używać funkcji BitLocker bez zgodnego mikroukładu modułu TPM. Funkcja BitLocker może wymagać hasła lub klucza uruchomienia.
  - **Uruchamianie zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania mikroukładu modułu TPM.
  - **Numer PIN uruchamiania zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania numeru PIN podczas uruchamiania mikroukładu modułu TPM. Włączenie numeru PIN uruchomienia wymaga interakcji użytkownika końcowego. 
  - **Klucz uruchamiania zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania klucza podczas uruchamiania mikroukładu modułu TPM. Włączenie klucza uruchomienia wymaga interakcji użytkownika końcowego. 
  - **Klucz i numer PIN uruchamiania zgodnego modułu TPM**: wybierz opcję zezwalania, blokowania lub wymagania klucza i numeru PIN uruchamiania dla mikroukładu modułu TPM. Włączenie klucza i numeru PIN uruchomienia wymaga interakcji użytkownika końcowego.
- **Minimalna długość numeru PIN**: **włącz** to ustawienie, aby skonfigurować minimalną długość numeru PIN uruchomienia modułu TPM. W przypadku ustawienia **Nie skonfigurowano** (domyślne) użytkownicy mogą skonfigurować kod PIN uruchamiania o dowolnej długości od 6 do 20 cyfr.
  - **Minimalna liczba znaków**: wprowadź liczbę znaków wymaganą dla numeru PIN uruchomienia z przedziału **4**-**20** znaków.
- **Odzyskiwanie dysku systemu operacyjnego**: opcja **Włącz** aktywuje to ustawienie, umożliwiając określenie sposobu odzyskiwania dysków z systemem operacyjnym chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne. **Nie skonfigurowano** (ustawienie domyślne) — obsługiwane są domyślne opcje odzyskiwania w przypadku odzyskiwania funkcji BitLocker. Domyślnie agent DRA jest dozwolony, opcje odzyskiwania, w tym hasło odzyskiwania i klucz odzyskiwania, są wybierane przez użytkownika, i nie jest tworzona kopia zapasowa informacji odzyskiwania w usługach AD DS.
  - **Agent odzyskiwania danych oparty na certyfikatach**: ustawienie wartości **Blokuj** uniemożliwia używanie agentów odzyskiwania danych względem dysków z systemem operacyjnym chronionych przez funkcję BitLocker. Ustawienie na wartość **Nie skonfigurowano** (ustawienie domyślne) włącza tę funkcję, która umożliwia używanie agentów odzyskiwania danych względem dysków z systemem operacyjnym chronionych przez funkcję BitLocker.
  - **Tworzenie hasła odzyskiwania przez użytkownika**: wybierz, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
  - **Tworzenie klucza odzyskiwania przez użytkownika**: wybierz, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
  - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker**: **Blokuj** — uniemożliwia użytkownikom wyświetlanie i zmianę opcji odzyskiwania. **Nie skonfigurowano** (ustawienie domyślne) — użytkownicy mogą wyświetlać i zmieniać opcje odzyskiwania po włączeniu funkcji BitLocker.
  - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS**: opcja **Włącz** powoduje zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Azure Active Directory. **Nie skonfigurowano** (ustawienie domyślne) — informacje odzyskiwania nie są przechowywane w usłudze Azure Active Directory.
  - **Informacje dotyczące odzyskiwania funkcji BitLocker przechowywane w usługach AD DS**: pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Azure Active Directory. Wybierz spośród opcji:
    - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
    - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
  - **Przechowuj informacje dotyczące odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker**: opcja **Wymagaj** tego ustawienia uniemożliwia użytkownikom włączenie funkcji BitLocker, chyba że informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Azure Active Directory (AD). **Nie skonfigurowano** (ustawienie domyślne) — umożliwia użytkownikom włączenie funkcji BitLocker, nawet jeśli informacje odzyskiwania nie zostały pomyślnie zapisane w usłudze Azure AD.
- **Komunikat odzyskiwania i adres URL przed rozruchem**: **włącz** to ustawienie, aby skonfigurować komunikat i adres URL wyświetlane na ekranie odzyskiwania kluczy przed rozruchem. **Nie skonfigurowano** (ustawienie domyślne) — wyłącza tę funkcję.
  - **Komunikat odzyskiwania przed rozruchem**: pozwala określić sposób wyświetlania użytkownikom komunikatu odzyskiwania przed rozruchem. Wybierz spośród opcji:
    - **Użyj domyślnego komunikatu i adresu URL dotyczącego odzyskiwania**
    - **Użyj pustego komunikatu i adresu URL dotyczącego odzyskiwania**
    - **Użyj niestandardowego komunikatu dotyczącego odzyskiwania**
    - **Użyj niestandardowego adresu URL odzyskiwania**

### <a name="bitlocker-fixed-data-drive-settings"></a>Ustawienia stałych dysków danych w funkcji BitLocker

Obsługiwany w następujących wersjach systemu Windows 10:

- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise
- Professional

**Ustawienia**:

- **Dostęp do zapisu dla stałych dysków danych, które nie są chronione przez funkcję BitLocker**: ustaw wartość **Blokuj**, aby udzielić dostępu tylko do odczytu do dysków z danymi, które nie są chronione za pomocą funkcji BitLocker. **Nie skonfigurowano** (ustawienie domyślne) — umożliwienie dostęp do odczytu i zapisu do dysków danych, które nie są chronione przez funkcję BitLocker.
- **Odzyskiwanie dysku stałego**: opcja **Włącz** tego ustawienia umożliwia określenie sposobu odzyskiwania dysków stałych chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne. **Nie skonfigurowano** (ustawienie domyślne) — wyłącza tę funkcję.
  - **Agent odzyskiwania danych**: **Blokuj** — uniemożliwia używanie agenta odzyskiwania danych za pomocą edytora zasad dysków stałych chronionych przez funkcję BitLocker. **Nie skonfigurowano** (ustawienie domyślne) — umożliwia używanie agentów odzyskiwania danych względem dysków stałych chronionych przez funkcję BitLocker.
  - **Tworzenie hasła odzyskiwania przez użytkownika**: pozwala określić, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
  - **Tworzenie klucza odzyskiwania przez użytkownika**: pozwala określić, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
  - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker**: **Blokuj** — uniemożliwia użytkownikom wyświetlanie i zmianę opcji odzyskiwania. **Nie skonfigurowano** (ustawienie domyślne) — użytkownicy mogą wyświetlać i zmieniać opcje odzyskiwania po włączeniu funkcji BitLocker.
  - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usłudze Azure Active Directory**: opcja **Włącz** powoduje przechowywanie informacji odzyskiwania funkcji BitLocker w usłudze Azure Active Directory (Azure AD). **Nie skonfigurowano** (ustawienie domyślne) — informacje odzyskiwania nie są przechowywane w usłudze Azure AD.
  - **Informacje dotyczące odzyskiwania funkcji BitLocker przechowywane w usłudze Azure Active Directory**: pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Azure AD. Dostępne opcje:
    - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
    - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
  - **Przechowuj informacje dotyczące odzyskiwania w usłudze Azure Active Directory przed włączeniem funkcji BitLocker**: opcja **Wymagaj** tego ustawienia uniemożliwia użytkownikom włączenie funkcji BitLocker, chyba że informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Azure AD. **Nie skonfigurowano** (ustawienie domyślne) — umożliwia użytkownikom włączenie funkcji BitLocker, nawet jeśli informacje odzyskiwania nie zostały pomyślnie zapisane w usłudze Azure AD.

### <a name="bitlocker-removable-data-drive-settings"></a>Ustawienia wymiennych dysków danych w funkcji BitLocker

Obsługiwany w następujących wersjach systemu Windows 10:

- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise
- Professional

**Ustawienia**:

- **Dostęp do zapisu dla wymiennych dysków danych, które nie są chronione przez funkcję BitLocker**: ustaw wartość **Blokuj**, aby udzielić dostępu tylko do odczytu do dysków z danymi, które nie są chronione za pomocą funkcji BitLocker. **Nie skonfigurowano** (ustawienie domyślne) — umożliwienie dostęp do odczytu i zapisu do dysków danych, które nie są chronione przez funkcję BitLocker.
  - **Dostęp do zapisu dla urządzeń skonfigurowanych w innej organizacji**: **Blokuj**  — umożliwia dostęp do zapisu do urządzeń skonfigurowanych w innej organizacji. **Nie skonfigurowano** (ustawienie domyślne) — nie zezwala na dostęp do zapisu.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Obsługiwany w następujących wersjach systemu Windows 10:

- Domowy
- Professional
- Służbowy
- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise

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

> [!IMPORTANT]
> Aby zezwolić na prawidłowej instalacji i wykonywania aplikacji LOB Win32, ustawienia ochrony przed złośliwym kodem powinno wykluczać następujące katalogi ze skanowania:<p>
> **Na X64 komputerów klienckich**:<br>
> *C:\Program pliki (x86) \Microsoft Intune Zarządzanie Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Na X86 komputerów klienckich**:<br>
> *C:\Program Files\Microsoft Intune Zarządzanie Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

Pomaga chronić cenne dane przed złośliwymi aplikacjami i zagrożeniami, takimi jak oprogramowanie wymuszające okup.

- **Ochrona folderów**: chroni pliki i foldery przed niepożądanymi zmianami przez złośliwe aplikacje. Możesz zaimportować **listę aplikacji, które mają dostęp do chronionych folderów**, lub dodać je ręcznie. Możesz również dodać **listę dodatkowych folderów, które muszą być chronione**, korzystając z przekazywania lub dodając je ręcznie.

### <a name="network-filtering"></a>Filtrowanie sieci

- **Ochrony sieciowej**: chroni połączenia wychodzące z dowolnej aplikacji do niskiej reputacji adresów IP lub domen. Celem jest ochrona użytkowników końcowych z aplikacji z dostępem do wyłudzania, obsługa wykorzystać witryn i złośliwej zawartości w Internecie. Zapobiega również wyświetlaniu przeglądarek innych firm na połączenie z niebezpiecznych witryn.

  Dostępne opcje:

  - **Nie skonfigurowano** (ustawienie domyślne) — wyłącza tę funkcję. Użytkownicy i aplikacje nie są blokowane pozwalać na połączenie z niebezpiecznych domen. Administratorzy nie zobaczą tego działania w usłudze Windows Defender Security Center.
  - **Włącz** powoduje włączenie ochrony sieci, bloki użytkowników i aplikacji na połączenie z niebezpiecznych domen. Administratorzy będą mogli zobaczyć działania w usłudze Windows Defender Security Center.
  - **Tylko inspekcja**: Użytkownicy i aplikacje nie są zablokowane na połączenie z niebezpiecznych domen. Administratorzy będą mogli zobaczyć działania w usłudze Windows Defender Security Center.

  [Usługa Defender/EnableNetworkProtection dostawcy usług Kryptograficznych](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

### <a name="exploit-protection"></a>Exploit Protection

Aby używać funkcji ochrony przed programami wykorzystującymi luki w zabezpieczeniach, utwórz plik XML zawierający odpowiednie ustawienia ograniczania ryzyka dla aplikacji i systemu. Dostępne są dwie metody:

 1. Program PowerShell: użyj jednego lub kilku z poleceń cmdlet programu PowerShell: Get-ProcessMitigation, Set-ProcessMitigation i ConvertTo-ProcessMitigationPolicy. Polecenia cmdlet służą do konfigurowania ustawień ograniczania ryzyka i eksportowania ich reprezentacji w formacie XML.

 2. Interfejs użytkownika usługi Windows Defender Security Center: W usłudze Windows Defender Security Center kliknij pozycję Sterowanie aplikacjami i przeglądarką, a następnie przewiń w dół wyświetlonego ekranu i znajdź funkcję Exploit Protection. Najpierw skonfiguruj ustawienia ograniczania ryzyka na kartach Ustawienia systemowe i Ustawienia programu. Następnie użyj linku Eksportuj ustawienia w dolnej części ekranu, aby wyeksportować ich reprezentację w formacie XML.

Blokowanie **edytowania interfejsu ochrony przed programami wykorzystującymi luki w zabezpieczeniach przez użytkowników** przez przekazywanie pliku XML, który umożliwia konfigurowanie ograniczeń pamięci, przepływu sterowania i zasad. Ustawienia w pliku XML mogą być używane do blokowania aplikacji przed programami wykorzystującymi luki w zabezpieczeniach. **Nie skonfigurowano** (ustawienie domyślne) — konfiguracja niestandardowa nie jest wypychana. 

## <a name="windows-defender-application-control"></a>Kontrola aplikacji usługi Windows Defender

Obsługiwany w następujących wersjach systemu Windows 10:

**Zarządzanie urządzeniami mobilnymi**: 
- Professional
- Służbowy
- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise

**Zarządzanie zasadami grupy**: 
- Enterprise

Użyj **zasad integralności kodu kontroli aplikacji**, aby wybrać dodatkowe aplikacje, które będą poddawane inspekcji przez usługę Windows Defender Security Center lub którym ta usługa może ufać. Składniki systemu Windows i wszystkie aplikacje ze Sklepu Windows są automatycznie zaufane do uruchomienia.

Aplikacje działające w trybie **Tylko inspekcja** nie są blokowane. Tryb **tylko do inspekcji** rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta.

Po włączeniu kontrolę aplikacji można wyłączyć tylko przez zmianę trybu z **Wymuszanie** na **Tylko inspekcja**. Zmiana trybu z **Wymuszanie** na **Nieskonfigurowane** skutkuje tym, że kontrola aplikacji nadal jest wymuszana na przypisanych urządzeniach.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

Obsługiwany w następujących wersjach systemu Windows 10:

- Enterprise

Funkcja Windows Defender Credential Guard chroni przed atakami polegającymi na kradzieży poświadczeń. Izoluje ona wpisy tajne, tak aby tylko uprzywilejowane oprogramowanie systemu mogło uzyskiwać do nich dostęp.

Ustawienia funkcji **Credential Guard** obejmują następujące opcje:

- **Wyłącz**: zdalnie wyłącza funkcję Credential Guard, jeśli została ona wcześniej włączona za pomocą opcji **Włączone bez blokady UEFI**.

- **Włącz z blokadą UEFI**: funkcji Credential Guard nie można wyłączyć za pomocą klucza rejestru ani zasad grupy.

    > [!NOTE]
    > Jeśli używasz tego ustawienia i chcesz później wyłączyć funkcję Credential Guard, musisz ustawić zasady grupy na **Wyłączone**. Musisz również fizycznie wyczyścić informacje o konfiguracji interfejsu UEFI z każdego komputera. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

- **Włącz bez blokady UEFI**: umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 w wersji 1511 lub nowszej.

Po włączeniu funkcji Credential Guard są również włączane następujące wymagane funkcje:

- **Zabezpieczenia oparte na wirtualizacji** (VBS): funkcja włączana podczas następnego rozruchu. Zabezpieczenia oparte na wirtualizacji używają funkcji Hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń.
- **Bezpieczny rozruch z bezpośrednim dostępem do pamięci**: włącza zabezpieczenia VBS z ochroną przy użyciu funkcji bezpiecznego rozruchu i bezpośredniego dostępu do pamięci (DMA). Ochrona DMA wymaga obsługi sprzętowej i można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach.

## <a name="windows-defender-security-center"></a>Windows Defender Security Center

Obsługiwany w następujących wersjach systemu Windows 10:

- Domowy
- Professional
- Służbowy
- Enterprise
- Edukacja
- Urządzenia przenośne
- Mobile Enterprise

Usługa Windows Defender Security Center działa jako osobna aplikacja lub proces z każdej z poszczególnych funkcji. Wyświetla ona powiadomienia za pośrednictwem centrum akcji. Pełni rolę modułu zbierającego lub jednego miejsca służącego do wyświetlania stanu oraz uruchamiania niektórych czynności konfiguracyjnych dla każdej funkcji. Dowiedz się więcej z dokumentacji [usługi Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

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

Obsługiwany w następujących wersjach systemu Windows 10:
 
- Domowy
- Professional
- Służbowy
- Enterprise
- Edukacja

Te opcje umożliwiają konfigurowanie ustawień zabezpieczeń lokalnych na urządzeniach z systemem Windows 10.

### <a name="accounts"></a>Konta

- **Dodaj nowe konta Microsoft**: **Blokuj** — uniemożliwia użytkownikom dodawanie nowych kont Microsoft na tym komputerze. **Nie skonfigurowano** (ustawienie domyślne) — użytkownicy mogą używać kont Microsoft na urządzeniu.
- **Zdalne logowanie bez hasła**: opcja **Blokuj**  umożliwia tylko kontom lokalnym z pustymi hasłami logowanie się przy użyciu klawiatury urządzenia. **Nie skonfigurowano** (ustawienie domyślne) — umożliwia kontom lokalnym z pustymi hasłami logowanie się z lokalizacji innych niż urządzenie fizyczne.

#### <a name="admin"></a>Administracja

- **Konto administratora lokalnego**: ustaw na wartość **Włączone**, aby włączyć konto administratora lokalnego. Ustaw na wartość **Nie skonfigurowano** (ustawienie domyślne), aby wyłączyć konto administratora lokalnego.
- **Zmień nazwę konta administratora**: definiowanie innej nazwy konta do skojarzenia z identyfikatorem zabezpieczeń (SID) dla konta administratora.

#### <a name="guest"></a>Gość

- **Konto gościa**: ustaw na wartość **Włączone**, aby włączyć lokalne konto gościa. Ustaw na wartość **Nie skonfigurowano** (ustawienie domyślne), aby wyłączyć lokalne konto gościa.
- **Zmień nazwę konta gościa**: definiowanie innej nazwy konta do skojarzenia z identyfikatorem zabezpieczeń (SID) dla konta gościa.

### <a name="devices"></a>Devices

- **Oddokuj urządzenie bez logowania**: ustaw na wartość **Blokuj**, aby użytkownicy mogli bezpiecznie oddokować urządzenie przez naciśnięcie fizycznego przycisku wysuwania zadokowanego urządzenia przenośnego. Ustawienie **Nie skonfigurowano** (ustawienie domyślne) wymaga od użytkownika zalogowania się na urządzeniu w celu otrzymania uprawnień do oddokowania urządzenia.
- **Instaluj sterowniki drukarek udostępnionych**: **Włączone** — powoduje, że każdy użytkownik może instalować sterownik drukarki w ramach łączenia z drukarką udostępnioną. **Nie skonfigurowano** (ustawienie domyślne) — tylko administratorzy mogą instalować sterownik drukarki w ramach łączenia z drukarką udostępnioną.
- **Ogranicz dostęp do dysku CD-ROM do aktywnego użytkownika lokalnego**: kiedy to ustawienie jest **Włączone**, tylko interaktywnie zalogowany użytkownik może korzystać z nośników CD-ROM. Jeśli te zasady są włączone, a żaden użytkownik nie jest zalogowany interaktywnie, napęd CD-ROM jest dostępny za pośrednictwem sieci. W przypadku ustawienia **Nie skonfigurowano** (ustawienie domyślne) każdy użytkownik ma dostęp do napędu CD-ROM.
- **Formatowanie i wysuwanie nośnika wymiennego**: definiowanie, kto może formatować i wysuwać nośnik wymienny systemu plików NTFS:
  - **Nieskonfigurowany**
  - **Administratorzy**
  - **Administratorzy i użytkownicy zaawansowani**
  - **Administratorzy i użytkownicy interaktywni**

### <a name="interactive-logon"></a>Logowanie interakcyjne

- **Minuty braku aktywności ekranu blokady przed aktywowaniem wygaszacza ekranu**: podaj maksymalną liczbę minut braku aktywności na ekranie logowania pulpitu interaktywnego przed uruchomieniem wygaszacza ekranu.
- **Wymagaj kombinacji CTRL+ALT+DEL do zalogowania**: ustaw na wartość **Włącz**, aby użytkownicy mogli się logować bez naciskania kombinacji klawiszy CTRL+ALT+DEL. Ustaw na wartość **Nie skonfigurowano** (ustawienie domyślne), aby wymagać od użytkowników naciśnięcia kombinacji klawiszy CTRL+ALT+DEL przed zalogowaniem się do systemu Windows.
- **Zachowanie przy usuwaniu karty inteligentnej**: określa, co się stanie, gdy karta inteligentna zalogowanego użytkownika zostanie usunięta z czytnika kart inteligentnych. Dostępne opcje:

  - **Zablokuj stację roboczą**: stacja robocza zostanie zablokowana po wyjęciu karty inteligentnej. Ta opcja umożliwia użytkownikom opuszczenie miejsca pracy i zabranie ze sobą karty inteligentnej przy jednoczesnym zachowaniu chronionej sesji.
  - **Wymuszaj wylogowanie**: użytkownik jest automatycznie wylogowywany po wyjęciu karty inteligentnej.
  - **Rozłącz, gdy istnieje sesja usług pulpitu zdalnego**: usunięcie karty inteligentnej powoduje rozłączenie sesji bez wylogowywania użytkownika. Ta opcja umożliwia użytkownikowi włożenie karty inteligentnej i wznowienie sesji w późniejszym czasie lub na innym komputerze z czytnikiem kart inteligentnych bez konieczności ponownego logowania się. Jeśli sesja jest lokalna, te zasady działają tak samo, jak w przypadku opcji Zablokuj stację roboczą.

    Dalsze szczegóły można znaleźć w temacie dotyczącym [opcji zabezpieczeń LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior).

#### <a name="display"></a>Wyświetlanie

- **Informacje o użytkowniku na ekranie blokady**: konfigurowanie informacji o użytkowniku wyświetlanych po zablokowaniu sesji. Jeśli nie zostaną one skonfigurowane, będzie pokazywana nazwa wyświetlana użytkownika, domena i nazwa użytkownika.
  - **Nieskonfigurowany**  
  - **Nazwa wyświetlana użytkownika, domena i nazwa użytkownika**
  - **Tylko nazwa wyświetlana użytkownika**
  - **Nie wyświetlaj informacji o użytkowniku**
- **Ukryj ostatniego zalogowanego użytkownika**: **Włącz** — powoduje ukrywanie nazwy użytkownika. **Nie skonfigurowano** (ustawienie domyślne) — powoduje wyświetlanie nazwy użytkownika.
- **Ukryj nazwę użytkownika podczas logowania**: **Włącz** — powoduje ukrywanie nazwy użytkownika. **Nie skonfigurowano** (ustawienie domyślne) — powoduje wyświetlanie nazwy użytkownika.
- **Tytuł komunikatu logowania**: ustaw tytuł komunikatu dla użytkowników próbujących się zalogować.
- **Tekst komunikatu logowania**: ustaw tekst komunikatu dla użytkowników próbujących się zalogować.

### <a name="network-access-and-security"></a>Dostęp do sieci i jej zabezpieczenia

- **Dostęp anonimowy do nazwanych potoków i udziałów**: ustawienie na wartość **Nie skonfigurowano** (ustawienie domyślnie) ogranicza dostęp anonimowy do ustawień udziałów i nazwanych potoków. Dotyczy ustawień, do których można uzyskiwać anonimowy dostęp.
- **Anonimowe wyliczanie kont SAM**: **umożliwia** użytkownikom anonimowym wyliczanie kont SAM. System Windows pozwala użytkownikom anonimowym na wyliczanie nazw kont domeny i udziałów sieciowych.
- **Anonimowe wyliczanie kont SAM i udziałów**: ustawienie na wartość **Nie skonfigurowano** (ustawienie domyślne) oznacza, że użytkownicy anonimowi mogą wyliczać nazwy kont domen i udziałach sieciowych. Aby zapobiec anonimowemu wyliczaniu kont SAM i udziałów, ustaw na wartość **Blokuj**.
- **Wartość skrótu programu LAN Manager przechowywana przy zmianie hasła**: podczas kolejnej zmiany hasła **zezwól** na przechowywanie wartości skrótu dla nowego hasła przez program LAN Manager (LM). W przypadku ustawienia na wartość **Nie skonfigurowano** (ustawienie domyślne) wartość skrótu nie będzie przechowywana.
- **Żądania uwierzytelniania protokołu PKU2U**: **blokuj** żądania uwierzytelniania protokołu PKU2U do tego urządzenia w celu używania tożsamości online. Ustawienie na wartość **Nie skonfigurowano** (ustawienie domyślne) zezwala na te żądania.
- **Ogranicz zdalne połączenia RPC do Menedżera kont zabezpieczeń**: Ustaw **Zezwalaj** odrzucanie użytkowników i grup z wprowadzeniem zdalne wywołania RPC do Menedżera (kont zabezpieczeń), która przechowuje konta użytkowników i hasła. **Zezwalaj na** również pozwala zmienić domyślny ciąg języka definicji deskryptorów zabezpieczeń (SDDL), aby jawnie zezwolić lub odmówić użytkownikom i grupom na wykonywanie tych zdalnych połączeń. **Nieskonfigurowane** (domyślnie) korzysta z domyślnego deskryptora zabezpieczeń i umożliwiają użytkownikom i grupom na wykonywanie zdalnych połączeń RPC do Menedżera kont zabezpieczeń.
  - **Deskryptor zabezpieczeń**

### <a name="recovery-console-and-shutdown"></a>Konsola odzyskiwania i zamykanie

- **Wyczyść plik stronicowania pamięci wirtualnej podczas zamykania**: ustaw na wartość **Włącz**, aby plik stronicowania pamięci wirtualnej był czyszczony podczas wyłączania urządzenia. W przypadku ustawienia na wartość **Nie skonfigurowano** pamięć wirtualna nie będzie usuwana.
- **Zamknięcie bez zalogowania**: opcja **Blokuj** powoduje ukrycie opcji zamknięcia na ekranie logowania systemu Windows. Użytkownicy muszą zalogować się do urządzenia, a następnie je zamknąć. **Nie skonfigurowano** (ustawienie domyślne) — umożliwia użytkownikom zamknięcie urządzenia z poziomu ekranu logowania systemu Windows.

### <a name="user-account-control"></a>Kontrola konta użytkownika

- **Integralność automatyzacji interfejsu użytkownika bez bezpiecznej lokalizacji**: w przypadku ustawienia opcji **Blokuj** tylko aplikacje w bezpiecznej lokalizacji w systemie plików są uruchamiane przy użyciu poziomu integralności UIAccess. **Nie skonfigurowano** (ustawienie domyślne) umożliwia uruchamianie aplikacji z poziomem integralności UIAccess, nawet jeśli aplikacje nie znajdują się w bezpiecznej lokalizacji w systemie plików.
- **Wirtualizuj błędy zapisu plików i rejestru w lokalizacjach poszczególnych użytkowników**: po ustawieniu **włączone**, aplikacje, które zapisu danych do chronionych lokalizacji kończy się niepowodzeniem. Po ustawieniu **nieskonfigurowane** (ustawienie domyślne), zapis aplikacji, błędy są przekierowywane w czasie wykonywania do zdefiniowanych lokalizacji użytkownika dla systemu plików i rejestru.
- **Podnieś poziom uprawnień tylko w przypadku plików wykonywalnych, które zostały podpisane i zweryfikowane**: ustaw na wartość **Włącz**, aby wymuszać weryfikację ścieżki certyfikacji PKI dla danego pliku wykonywalnego przed zezwoleniem na jego uruchomienie. Ustaw na wartość **Nie skonfigurowano** (ustawienie domyślne), aby nie wymuszać weryfikacji ścieżki certyfikacji PKI dla danego pliku wykonywalnego przed zezwoleniem na jego uruchomienie.

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
- **Kieruj monity o podniesienie uprawnień do interaktywnego pulpitu użytkownika**: **Włącz**, aby umożliwiać kierowanie wszystkich żądań podniesienia uprawnień do interaktywnego pulpitu użytkownika, a nie do bezpiecznego pulpitu. Używane są ustawienia zasad zachowania monitu dla administratorów i użytkowników standardowych. **Nie skonfigurowano** (wartość domyślna) — wymusza kierowanie wszystkich żądań podniesienia uprawnień do bezpiecznego pulpitu bez względu na ustawienia zasad zachowania monitu dla administratorów i użytkowników standardowych.
- **Monituj o podniesienie poziomu uprawnień w przypadku instalacji aplikacji**: w przypadku ustawienia opcji **Włączone** pakiety instalacyjne aplikacji nie są wykrywane ani monitowane o podniesienie poziomu uprawnień. W przypadku ustawienia na wartość **Nie skonfigurowano** (ustawienie domyślne) użytkownik jest monitowany o podanie nazwy użytkownika administracyjnego i hasła, gdy pakiet instalacyjny aplikacji wymaga podwyższonego poziomu uprawnień.
- **Monituj o podniesienie poziomu uprawnień automatyzacji interfejsu użytkownika bez bezpiecznego pulpitu**: **Włącz**, aby zezwalać aplikacjom z poziomem UIAccess na monitowanie o podniesienie uprawnień bez używania bezpiecznego pulpitu. W przypadku ustawienia wartości **Nie skonfigurowano** (ustawienie domyślne) monity o podniesienie uprawnień korzystają z bezpiecznego pulpitu.

#### <a name="admin-approval-mode-settings"></a>Ustawienia trybu zatwierdzania przez administratora

- **Tryb zatwierdzania przez administratora dla wbudowanego administratora**: **Włączone** — wbudowane konto administratora używa trybu zatwierdzania przez administratora. Każda operacja, która wymaga podniesienia uprawnień, monituje użytkownika o zatwierdzenie operacji. **Nie skonfigurowano** (ustawienie domyślne) — uruchamia wszystkie aplikacje z pełnymi uprawnieniami administratora.
- **Uruchom wszystkich administratorów w trybie zatwierdzania przez administratora**: ustawienie opcji **Włączone** powoduje wyłączenie trybu zatwierdzania przez administratora i wszystkich powiązanych ustawień zasad funkcji Kontrola konta użytkownika. **Nie skonfigurowano** (ustawienie domyślne) włącza tryb zatwierdzania przez administratora.

### <a name="microsoft-network-client"></a>Klient sieci firmy Microsoft

- **Podpisuj cyfrowo komunikację (za zgodą serwera)**: określa, czy klient SMB negocjuje podpisywanie pakietów SMB. Jeśli ta opcja jest **nieskonfigurowana** lub włączona (ustawienie domyślne), klient sieci firmy Microsoft żąda od serwera podpisania pakietów SMB podczas konfigurowania sesji. Jeśli podpisywanie pakietów jest włączone na serwerze, ma miejsce negocjowanie podpisywania pakietów. Jeśli ta opcja jest **wyłączona**, klient SMB nigdy nie negocjuje podpisywania pakietów SMB.
- **Wyślij niezaszyfrowane hasło w celu nawiązania połączenia z innymi serwerami SMB**: jeśli ta opcja jest **włączona**, przekierowanie bloku komunikatów serwera (SMB) może wysyłać hasła w postaci zwykłego tekstu do serwerów SMB firm innych niż Microsoft, które nie obsługują szyfrowania hasła podczas uwierzytelniania. Gdy jest **nieskonfigurowana** (ustawienie domyślne), hasła są szyfrowane.

### <a name="microsoft-network-server"></a>Serwer sieci Microsoft

- **Podpisuj cyfrowo komunikację (za zgodą klienta)**: określa, czy serwer SMB negocjuje podpisywanie pakietów SMB z klientami, którzy wykonują żądanie. W przypadku ustawienia na wartość **Włącz** serwer sieci Microsoft negocjuje podpisywanie pakietów SMB zgodnie z żądaniem klienta. Oznacza to, że jeśli podpisywanie pakietów zostało włączone na kliencie, jest negocjowane podpisywanie pakietów. Jeśli ta opcja jest ustawiona na wartość **Nie skonfigurowano** lub jest wyłączona (ustawienie domyślne), klient SMB nigdy nie negocjuje podpisywania pakietów SMB.
- **Podpisuj cyfrowo komunikację (zawsze)**: określa, czy podpisywanie pakietów jest wymagane przez składnik serwera SMB. Jeśli ta opcja jest ustawiona na wartość **Włącz**, serwer sieci Microsoft nie komunikuje się z klientem sieci Microsoft, chyba że klient zgadza się na podpisywanie pakietów SMB. Jeśli ta opcja jest ustawiona na wartość **Nie skonfigurowano** lub wyłączona (ustawienie domyślne), podpisywanie pakietów jest negocjowane między klientem a serwerem.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Skonfiguruj ustawienia ochrony punktu końcowego na urządzeniach z systemem [macOS](endpoint-protection-macos.md).
