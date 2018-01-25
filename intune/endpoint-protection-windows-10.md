---
title: "Ustawienia programu Endpoint Protection usługi Intune dla systemu Windows 10"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień programu Endpoint Protection, na przykład funkcji BitLocker, na urządzeniach z systemem Windows 10."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 01/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8393699a06def8f01c9f70561bb1894bb7cba04e
ms.sourcegitcommit: 967a7c23b863123398c40b812e2eb02c921a0afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/18/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil programu Endpoint Protection umożliwia kontrolowanie funkcji zabezpieczeń na urządzeniach z systemem Windows 10, takich jak funkcja BitLocker i usługa Windows Defender.

Skorzystaj z informacji w tym temacie, aby dowiedzieć się, jak tworzyć profile programu Endpoint Protection.

> [!Note]
> Te ustawienia nie są obsługiwane w systemie Windows 10 w wersjach Home i Professional.

## <a name="create-an-endpoint-protection-profile"></a>Tworzenie profilu programu Endpoint Protection

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu funkcji urządzenia.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Endpoint Protection**.
7. Skonfiguruj odpowiednie ustawienia. Zapoznaj się ze szczegółowymi informacjami w tym temacie, aby lepiej zrozumieć działanie poszczególnych ustawień. Gdy skończysz, wybierz przycisk **OK**.
8. Wróć do bloku **Tworzenie profilu**, a następnie wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Funkcja Application Guard jest dostępna tylko dla urządzeń z systemem Windows 10 (wersja 64-bitowa). Użycie tego profilu spowoduje zainstalowanie składnika Win32, aby aktywować funkcję Application Guard.

- **Application Guard** — otwieranie niezatwierdzonych witryn w zwirtualizowanym kontenerze przeglądania funkcji Hyper-V.
- **Zachowanie schowka** — wybierz dozwolone akcje kopiowania i wklejania między komputerem lokalnym a przeglądarką wirtualną funkcji Application Guard.
- **Zawartość zewnętrzna w witrynach przedsiębiorstw** — blokowanie ładowania zawartości z niezatwierdzonych witryn internetowych.
- **Drukuj z przeglądarki wirtualnej** — zezwalanie drukarkom PDF, XPS, lokalnym i/lub sieciowym na drukowanie zawartości z przeglądarki wirtualnej.
- **Zbieraj dzienniki** — zbieranie dzienników dla zdarzeń występujących w sesji przeglądania funkcji Application Guard.
- **Zachowuj dane przeglądarki generowane przez użytkownika** — zezwala na zapisywanie danych użytkownika (na przykład haseł, ulubionych i plików cookie) utworzonych podczas wirtualnej sesji przeglądania funkcji Application Guard.


## <a name="windows-defender-firewall"></a>Zapora Windows Defender

### <a name="global-settings"></a>Ustawienia globalne

Te ustawienia mają zastosowanie do wszystkich typów urządzeń.

- **Protokół transferu plików** — blokowanie stanowego protokołu FTP.
- **Czas bezczynności skojarzeń zabezpieczeń przed usunięciem** — skojarzenia zabezpieczeń są usuwane po wykryciu braku ruchu sieciowego przez *n* sek.
- **Kodowanie kluczy wstępnych** — kodowanie kluczy wstępnych przy użyciu kodowania UTF-8.
- **Wykluczenia IPsec** — konfigurowanie wykluczenia określonego ruchu z protokołu IPsec, w tym opcji **Odnajdywanie sąsiadujących kodów typu IPv6 protokołu ICMP**, **Protokół ICMP**, **Odnajdywanie routera kodów typu IPv6 protokołu ICMP** i **Ruch sieciowy DHCP IPv4 i IPv6**.
- **Weryfikacja listy odwołania certyfikatów** — ustawianie wartości określającej sposób wymuszania weryfikacji listy odwołania certyfikatów, w tym opcji **Wyłącz weryfikację listy CRL**, **Niepowodzenie weryfikacji listy CRL tylko w przypadku odwołanego certyfikatu** i **Niepowodzenie weryfikacji listy CRL przy dowolnym błędzie**.
- **Odpowiednio uzgodnij zestaw uwierzytelniania dla modułu kluczy** — ustawianie modułów kluczy w celu ignorowania całego zestawu uwierzytelniania, jeśli nie obsługują wszystkich pakietów uwierzytelniania w tym zestawie.
- **Kolejkowanie pakietów** — określa sposób włączania skalowania oprogramowania po stronie odbierającej w przypadku zaszyfrowanego odbierania i przekazywania w postaci zwykłego tekstu dla scenariusza z bramą tunelu IPsec. Zapewnia to zachowanie kolejności pakietów.

### <a name="network-settings"></a>Ustawienia sieciowe

Te ustawienia mają zastosowanie do sieci określonych typów, w tym **sieci z domeną (w miejscu pracy)**, **sieci prywatnej (wykrywalnej)** i **sieci publicznej (niewykrywalnej)**.

#### <a name="general-settings"></a>Ustawienia ogólne

- **Zapora Windows Defender** — włączenie tego ustawienia powoduje blokowanie ruchu sieciowego.
- **Tryb niewidzialności** — blokowanie działania zapory w trybie niewidzialności. Blokowanie to pozwala również zablokować **wykluczanie pakietów zabezpieczonych przez protokół IPsec**.
- **Chronione** — włączenie tego ustawienia i ustawienia zapory powoduje blokowanie całego ruchu przychodzącego.
- **Odpowiedzi emisji pojedynczej na multiemisję/emisje** — blokowanie odpowiedzi emisji pojedynczej na multiemisję/emisje. Zwykle nie chcesz otrzymywać odpowiedzi emisji pojedynczej na komunikaty multiemisji lub emisji, ponieważ takie odpowiedzi mogą wskazywać na atak typu „odmowa usługi” lub osobę atakującą próbującą sondować znany aktywny komputer.
- **Powiadomienia przychodzące** — blokowanie wyświetlania powiadomień użytkownikom, gdy nasłuchiwanie przez aplikację na porcie jest zablokowane.
- **Domyślna akcja dla połączeń przychodzących** — blokowanie domyślnej akcji, którą zapora wykonuje dla połączeń przychodzących.

#### <a name="rule-merging"></a>Scalanie reguł

- **Reguły zapory Windows Defender autoryzowanych aplikacji z magazynu lokalnego** — stosowanie autoryzowanych reguł zapory w magazynie lokalnym w celu rozpoznawania i wymuszania.
- **Globalne reguły zapory Windows Defender portów z magazynu lokalnego** — stosowanie globalnych reguł zapory portów w magazynie lokalnym w celu rozpoznawania i wymuszania.
- **Reguły zapory Windows Defender z magazynu lokalnego** — stosowanie globalnych reguł zapory w magazynie lokalnym w celu rozpoznawania i wymuszania.
- **Reguły protokołu IPsec z magazynu lokalnego** — stosowanie reguł zabezpieczeń połączeń z magazynu lokalnego, niezależnie od wersji reguł zabezpieczeń schematu lub połączenia.

## <a name="windows-defender-smartscreen-settings"></a>Ustawienia filtru Windows Defender SmartScreen

- **Filtr SmartScreen dla aplikacji i plików** — Włącz filtr Windows SmartScreen na potrzeby wykonywania plików i uruchamiania aplikacji.
- **Wykonywanie niezweryfikowanych plików** — Blokuj użytkownikowi końcowemu możliwość uruchamiania plików, które nie zostały zweryfikowane przez filtr Windows SmartScreen.

## <a name="windows-encryption"></a>Szyfrowanie systemu Windows

### <a name="windows-settings"></a>Ustawienia systemu Windows

Te ustawienia dotyczą wszystkich wersji systemu Windows 10.

- **Szyfruj urządzenia** — jeśli to ustawienie jest włączone, użytkownicy są monitowani o włączenie szyfrowania urządzenia. Ponadto użytkownicy zostaną poproszeni o potwierdzenie, że nie zostało włączone szyfrowanie od innego dostawcy. Jeśli szyfrowanie systemu Windows jest włączone, gdy inna metoda szyfrowania jest aktywna, urządzenie może pracować niestabilnie.
- **Szyfruj kartę pamięci** — włącz to ustawienie, aby zaszyfrować wszystkie wymienne karty pamięci używane przez urządzenie.


### <a name="bitlocker-base-settings"></a>Podstawowe ustawienia funkcji BitLocker

Podstawowe ustawienia to uniwersalne ustawienia funkcji BitLocker dla wszystkich typów dysków danych. Ustawienia zasad grupy funkcji BitLocker zarządzają zadaniami szyfrowania dysku lub opcjami konfiguracji, które użytkownik końcowy może modyfikować w przypadku wszystkich typów dysków z danymi.

- **Ostrzeżenie dotyczące innego szyfrowania dysku** — wyłączanie ostrzeżenia dotyczącego innego szyfrowania dysków na komputerach użytkowników końcowych.
- **Konfiguruj metody szyfrowania** — włącz to ustawienie, aby skonfigurować algorytmy szyfrowania na potrzeby systemu operacyjnego, danych i dysków wymiennych.
    - **Szyfrowanie dla dysków z systemami operacyjnymi** — wybierz metodę szyfrowania dla dysków z systemami operacyjnymi. Zaleca się użycie algorytmu XTS-AES.
    - **Szyfrowanie dla stałych dysków danych** — wybierz metodę szyfrowania dla stałych (wbudowanych) dysków danych. Zaleca się użycie algorytmu XTS-AES.
    - **Szyfrowanie dla wymiennych dysków danych** — wybierz metodę szyfrowania dla wymiennych dysków danych. Jeśli dysk wymienny jest używany z urządzeniami z systemem innym niż Windows 10, zaleca się użycie algorytmu AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Ustawienia funkcji BitLocker dla dysku z systemem operacyjnym

Te ustawienia dotyczą w szczególności dysków danych systemu operacyjnego.

- **Dodatkowe uwierzytelnianie podczas uruchamiania** — skonfiguruj wymagania dotyczące uwierzytelniania dla uruchamiania komputera, w tym użycie modułu TPM (Trusted Platform Module).
    - **Funkcja BitLocker z niezgodnym mikroukładem modułu TPM**
    - **Uruchomienie zgodnego modułu TPM** — pozwala określić, czy mikroukład TPM jest dozwolony, niedozwolony czy wymagany.
    - **Numer PIN uruchomienia zgodnego modułu TPM** — pozwala określić, czy użycie numeru PIN uruchomienia dla mikroukładu TPM ma być dozwolone, niedozwolone czy wymagane.
    - **Klucz uruchomienia zgodnego modułu TPM** — pozwala określić, czy użycie numeru PIN uruchomienia dla mikroukładu TPM ma być dozwolone, niedozwolone czy wymagane.
    - **Klucz uruchomienia i numer PIN zgodnego modułu TPM** — pozwala określić, czy użycie klucza uruchomienia i numeru PIN dla mikroukładu TPM ma być dozwolone, niedozwolone czy wymagane.
- **Minimalna długość numeru PIN** — włącz to ustawienie, aby skonfigurować minimalną długość numeru PIN uruchomienia modułu TPM.
    - **Minimalna liczba znaków** — wprowadź liczbę znaków wymaganą dla numeru PIN uruchomienia z przedziału **4**-**20** znaków.
- **Odzyskiwanie dysku systemu operacyjnego** — włącz to ustawienie, aby określić sposób odzyskiwania dysków z systemem operacyjnym chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.
    - **Agent odzyskiwania danych oparty na certyfikatach** — Włącz to ustawienie, aby możliwe było używanie agentów odzyskiwania danych względem dysków z systemem operacyjnym chronionych przez funkcję BitLocker.
    - **Tworzenie hasła odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Tworzenie klucza odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom wyświetlanie lub zmianę opcji odzyskiwania po włączeniu funkcji BitLocker.
    - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS** — umożliwia zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Active Directory.
    - **Informacje dotyczące odzyskiwania funkcji BitLocker przechowywane w usługach AD DS** — pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Active Directory. Wybierz spośród opcji:
        - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
        - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
    - **Przechowuj informacje dotyczące odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom włączenie funkcji BitLocker, chyba że urządzenie jest przyłączone do domeny, a informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Active Directory.
- **Komunikat odzyskiwania i adres URL przed rozruchem** — włącz to ustawienie, aby skonfigurować komunikat i adres URL wyświetlane na ekranie odzyskiwania kluczy przed rozruchem.
    - **Komunikat odzyskiwania przed rozruchem** — pozwala określić sposób wyświetlania użytkownikom komunikatu odzyskiwania przed rozruchem. Wybierz spośród opcji:
        - **Użyj domyślnego komunikatu i adresu URL dotyczącego odzyskiwania**
        - **Użyj pustego komunikatu i adresu URL dotyczącego odzyskiwania**
        - **Użyj niestandardowego komunikatu dotyczącego odzyskiwania**
        - **Użyj niestandardowego adresu URL odzyskiwania**


### <a name="bitlocker-fixed-data-drive-settings"></a>Ustawienia stałych dysków danych w funkcji BitLocker

- **Dostęp do zapisu dla stałych dysków danych, które nie są chronione przez funkcję BitLocker** — jeśli to ustawienie jest włączone, ochrona za pomocą funkcji BitLocker musi być włączona na wszystkich stałych lub wbudowanych dyskach danych, aby możliwy był na nich zapis.
- **Odzyskiwanie dysku stałego** — włącz to ustawienie, aby określić sposób odzyskiwania dysków stałych chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.
    - **Agent odzyskiwania danych** — Włącz to ustawienie, aby możliwe było używanie agentów odzyskiwania danych względem dysków stałych chronionych przez funkcję BitLocker.
    - **Tworzenie hasła odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
    - **Tworzenie klucza odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom wyświetlanie lub zmianę opcji odzyskiwania po włączeniu funkcji BitLocker.
    - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS** — umożliwia zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Active Directory.
    - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS** — pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Active Directory. Wybierz spośród opcji:
        - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
        - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
    - **Przechowuj informacje dotyczące odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom włączenie funkcji BitLocker, chyba że urządzenie jest przyłączone do domeny, a informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Ustawienia wymiennych dysków danych w funkcji BitLocker

- **Dostęp do zapisu dla wymiennych dysków danych, które nie są chronione przez funkcję BitLocker** — określ, czy dla wymiennych dysków magazynu wymagane jest szyfrowanie za pomocą funkcji BitLocker.
  - **Dostęp do zapisu dla urządzeń skonfigurowanych w innej organizacji** — określ, czy możliwy ma być zapis na wymiennych dyskach danych, które należą do innej organizacji.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Usługa [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) służy do zarządzania obszarem ataków i zmniejszania obszaru ataków w aplikacjach używanych przez pracowników.

### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków

Ułatwia [blokowanie akcji i aplikacji](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) zwykle używanych przez złośliwe oprogramowanie wyszukujące luki w zabezpieczeniach do infekowania maszyn.

#### <a name="rules-to-prevent-office-macro-threats"></a>Reguły zapobiegania zagrożeniom ze strony makr pakietu Office

Zablokuj aplikacjom pakietu Office możliwość wykonywania następujących akcji:

- **Wstrzykiwanie do innych procesów przez aplikacje pakietu Office (bez wyjątków)**
- **Tworzenie zawartości wykonywalnej przez makra i aplikacje pakietu Office**
- **Uruchamianie procesów podrzędnych przez aplikacje pakietu Office**
- **Importowanie elementów Win32 z kodu makr w pakiecie Office**

#### <a name="rules-to-prevent-script-threats"></a>Reguły zapobiegania zagrożeniom ze strony skryptów

Blokowanie tych elementów pomaga zapobiegać zagrożeniom ze strony skryptów:

- **Zaciemniony kod w plikach js/vbs/ps i makrach**
- **Wykonywanie ładunku pobranego z Internetu przez pliki js/vbs (bez wyjątków)**

#### <a name="rules-to-prevent-email-threats"></a>Reguły zapobiegania zagrożeniom ze strony poczty e-mail

Blokowanie tych elementów pomaga zapobiegać zagrożeniom ze strony poczty e-mail:

- **Wykonywanie zawartości wykonywalnej (exe, dll, ps, js, vbs itd.) pochodzącej z wiadomości e-mail (poczty internetowej lub klienta poczty) (bez wyjątków)**

#### <a name="attack-surface-reduction-exceptions"></a>Wyjątki zmniejszenia obszaru ataków

- **Pliki i foldery do wykluczenia z reguł zmniejszenia obszaru ataków** — zaimportuj/dodaj listę lokalizacji do wykluczenia ze skonfigurowanych reguł.

### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

Pomaga chronić cenne dane przed złośliwymi aplikacjami i zagrożeniami, takimi jak oprogramowanie wymuszające okup.

- **Ochrona folderów** — chroni pliki i foldery przed niepożądanymi zmianami przez złośliwe aplikacje. Możesz zaimportować **listę aplikacji, które mają dostęp do chronionych folderów**, lub dodać je ręcznie. Możesz również dodać **listę dodatkowych folderów, które muszą być chronione**, korzystając z przekazywania lub dodając je ręcznie.

### <a name="network-filtering"></a>Filtrowanie sieci

Blokuje połączenia wychodzące z dowolnych aplikacji do adresów IP/domen o niskiej reputacji.

### <a name="exploit-protection"></a>Exploit Protection

Blokowanie **edytowania interfejsu ochrony przed programami wykorzystującymi luki w zabezpieczeniach przez użytkowników** przez przekazywanie pliku XML, który umożliwia konfigurowanie ograniczeń pamięci, przepływu sterowania i zasad, które umożliwiają ochronę aplikacji przed lukami w zabezpieczeniach.

Aby włączyć ochronę przed programami wykorzystującymi luki w zabezpieczeniach, utwórz plik XML reprezentujący wybrane ustawienia ograniczania ryzyka dla aplikacji i systemu. Możesz to zrobić przy użyciu jednej z dwóch metod:

 1. Program PowerShell: Użyj jednego lub kilku z poleceń cmdlet programu PowerShell Get-ProcessMitigation, Set-ProcessMitigation i ConvertTo-ProcessMitigationPolicy, aby skonfigurować ustawienia ograniczania ryzyka i wyeksportować ich reprezentację w formacie XML.

 2. Interfejs użytkownika usługi Windows Defender Security Center: W usłudze Windows Defender Security Center kliknij pozycję Sterowanie aplikacjami i przeglądarką, a następnie przewiń w dół wyświetlonego ekranu i znajdź funkcję Exploit Protection. Najpierw skonfiguruj ustawienia ograniczania ryzyka na kartach Ustawienia systemowe i Ustawienia programu. Następnie użyj linku Eksportuj ustawienia w dolnej części ekranu, aby wyeksportować ich reprezentację w formacie XML.

## <a name="windows-defender-application-control"></a>Kontrola aplikacji usługi Windows Defender

Użyj **zasad integralności kodu kontroli aplikacji**, aby wybrać dodatkowe aplikacje, które muszą być poddawane inspekcji przez usługę Windows Defender Security Center lub którym ta usługa może ufać. Składniki systemu Windows i wszystkie aplikacje ze Sklepu Windows są automatycznie zaufane do uruchomienia.

Aplikacje działające w trybie „tylko do inspekcji” nie będą blokowane. Tryb „tylko do inspekcji” rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta.

## <a name="windows-defender-security-center"></a>Windows Defender Security Center

Aplikacja usługi Windows Defender Security Center działa jako osobna aplikacja lub proces z każdej z poszczególnych funkcji i wyświetla powiadomienia za pośrednictwem centrum akcji. Pełni rolę modułu zbierającego lub jednego miejsca służącego do wyświetlania stanu oraz wykonywania niektórych czynności konfiguracyjnych dla każdej funkcji. Dowiedz się więcej z dokumentacji [usługi Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplikacja i powiadomienia usługi Windows Defender Security Center

Zablokuj dostęp użytkowników do różnych obszarów aplikacji usługi Windows Defender Security Center. Ukrywanie sekcji spowoduje również blokowanie pokrewnych powiadomień.

- **Ochrona przed wirusami i zagrożeniami**
- **Wydajność i kondycja urządzenia**
- **Zapora i ochrona sieci**
- **Kontrola aplikacji i przeglądarki**
- **Opcje rodziny**
- **Powiadomienia z wyświetlanych obszarów aplikacji** — wybierz, które powiadomienia mają być wyświetlane użytkownikom końcowym. Powiadomienia niekrytyczne obejmują podsumowania działania programu antywirusowego Windows Defender, w tym powiadomienia po zakończeniu skanowania. Wszystkie pozostałe powiadomienia są traktowane jako krytyczne.

#### <a name="it-contact-information"></a>Informacje kontaktowe działu IT

Podaj informacje kontaktowe działu IT do wyświetlania w aplikacji Windows Defender Security Center i powiadomieniach aplikacji. Można wybrać opcję **Wyświetlaj w aplikacji i powiadomieniach**, **Wyświetlaj tylko w aplikacji**, **Wyświetlaj tylko w powiadomieniach** lub **Nie wyświetlaj**. Należy określić **nazwę organizacji IT** i co najmniej jedną z następujących opcji kontaktu:

- **Numer telefonu lub identyfikator Skype działu IT**
- **Adres e-mail działu IT**
- **Adres URL witryny internetowej pomocy technicznej**

## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).
