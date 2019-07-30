---
title: Ustawienia punktów odniesienia zabezpieczeń usługi Intune w usłudze Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender
titleSuffix: Microsoft Intune
description: Ustawienia punktów odniesienia zabezpieczeń obsługiwane przez usługę Intune na potrzeby zarządzania usługą Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eee3d4187dd513cd3945e86aff478fe96b341660
ms.sourcegitcommit: 1d4aec7b79c70d35ec3fc29df6ff9c6a1403412e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/25/2019
ms.locfileid: "68491927"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Ustawienia punktów odniesienia zabezpieczeń usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender dla usługi Intune

Zapoznaj się z ustawieniami punktów odniesienia zabezpieczeń usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (wcześniej Zaawansowana ochrona przed zagrożeniami w usłudze Windows Defender), które są obsługiwane przez usługę Microsoft Intune. Ustawienia domyślne punktu odniesienia usługi Zaawansowana ochrona przed zagrożeniami (ATP) reprezentują zalecaną konfigurację usługi ATP i mogą nie odpowiadać wartościom domyślnym innych punktów odniesienia zabezpieczeń.  

Punkty odniesienia zabezpieczeń usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender są dostępne, jeśli środowisko spełnia wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](advanced-threat-protection.md#prerequisites). 

Ta linia bazowa jest zoptymalizowana pod kątem urządzeń fizycznych i nie jest obecnie zalecana do użycia w maszynach wirtualnych lub punktach końcowych infrastruktury VDI. Niektóre ustawienia punktu odniesienia mogą mieć wpływ na zdalne sesje interaktywne w zwirtualizowanych środowiskach. Aby uzyskać więcej informacji, zobacz [Increase compliance to the Microsoft Defender ATP security baseline (Zwiększanie zgodności z punktem odniesienia zabezpieczeń usługi Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) w dokumentacji systemu Windows.


> [!NOTE]  
> Ustawienia punktów odniesienia usługi ATP są dostępne w **wersji zapoznawczej**. W okresie obowiązywania wersji zapoznawczej lista dostępnych ustawień oraz kolejność prezentowania tych ustawień może nie być zgodna z tym, co jest dostępne w portalu.  
>
> Po przeniesieniu ustawień punktów odniesienia poza wersję zapoznawczą ta zawartość zostanie zaktualizowana tak, aby odzwierciedlać aktualną listę ustawień punktów odniesienia zabezpieczeń obsługiwanych przez usługę Intune.

## <a name="application-guard"></a>Application Guard  
Więcej informacji można znaleźć na stronie [WindowsDefenderApplicationGuard CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) (WindowsDefenderApplicationGuard — dostawca usługi konfiguracji).  

Podczas korzystania z przeglądarki Microsoft Edge program Microsoft Defender Application Guard chroni Twoje środowisko przed witrynami, które nie zostały uznane za zaufane przez Twoją organizację. Gdy użytkownicy odwiedzają witryny, które nie zostały wymienione w granicach sieci izolowanej, witryny te są otwierane w ramach sesji przeglądania wirtualnego funkcji Hyper-V. Zaufane witryny są definiowane za pomocą granicy sieci.  

- **Application Guard** - *Settings/AllowWindowsDefenderApplicationGuard*  
  Wybierz pozycję *Tak*, aby włączyć tę funkcję, która otwiera niezaufane witryny w zwirtualizowanym kontenerze przeglądania funkcji Hyper-V. Po ustawieniu opcji na wartość *Nieskonfigurowane* wszystkie witryny (zaufane i niezaufane) będą otwierane na urządzeniu, a nie w zwirtualizowanym kontenerze.  

  **Domyślne**: Tak
 
  - **Zawartość zewnętrzna w witrynach przedsiębiorstw** - *Settings/BlockNonEnterpriseContent*  
    Wybierz pozycję *Tak*, aby zablokować ładowanie zawartości z niezatwierdzonych witryn internetowych. Po ustawieniu pozycji *Nieskonfigurowane* na urządzeniu będzie można otwierać witryny inne niż przedsiębiorstw. 
 
    **Domyślne**: Tak

  - **Zachowanie schowka** - *Settings/ClipboardSettings*  
    Wybierz dozwolone akcje kopiowania i wklejania między komputerem lokalnym a przeglądarką wirtualną funkcji Application Guard.  Dostępne opcje:
    - *Nieskonfigurowane*  
    - *Blokuj obydwa* — nie można przesyłać danych między komputerem i przeglądarką wirtualną.  
    - *Blokuj z hosta do kontenera* — nie można przesyłać danych z komputera do przeglądarki wirtualnej.
    - *Blokuj z kontenera do hosta* — nie można przesyłać danych z przeglądarki wirtualnej do komputera hosta.
    - *Nie blokuj żadnych* — blokady zawartości nie istnieją.  

    **Domyślne**: Blokuj obydwa  

- **Zasady izolacji sieci systemu Windows — nazwy domen sieciowych przedsiębiorstwa**  
  Więcej informacji można znaleźć na stronie [Policy CSP - NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) (Dostawca usługi konfiguracji — NetworkIsolation) w dokumentacji systemu Windows.
  
  Określ listę zasobów przedsiębiorstwa jako domeny, zakresy adresów IP i granice sieci, które są hostowane w chmurze. Ta lista będzie traktowana przez funkcję Application Guard jako witryny przedsiębiorstwa.  

  **Domyślne**: securitycenter.windows.com

## <a name="application-reputation"></a>Reputacja aplikacji  

Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) w dokumentacji systemu Windows.

- **Blokuj wykonywanie niezweryfikowanych plików**  
    Zablokuj użytkownikowi możliwość uruchamiania niezweryfikowanych plików. Po ustawieniu pozycji *Nieskonfigurowane* pracownicy mogą ignorować ostrzeżenia filtru SmartScreen i uruchamiać złośliwe pliki. Ustaw pozycję *Tak*, aby pracownicy nie mogli ignorować ostrzeżeń filtru SmartScreen ani uruchamiać złośliwych plików.  
  
    **Domyślne**: Tak

- **Wymagaj filtra SmartScreen dla aplikacji i plików**  
  Ustaw pozycję *Tak*, aby włączyć filtr SmartScreen dla systemu Windows.  

  **Domyślne**: Tak

## <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków  

- **Uruchamianie typu procesów podrzędnych przez aplikacje pakietu Office**  
  [Reguły zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Blokuj* aplikacje pakietu Office nie będą mogły tworzyć procesów podrzędnych. Aplikacje pakietu Office obejmują programy Word, Excel, PowerPoint, OneNote i Access. Tworzenie procesu podrzędnego to typowe zachowanie złośliwego oprogramowania, szczególnie w przypadku ataków opartych na makrach, które polegają na próbie uruchomienia lub pobrania złośliwych plików wykonywalnych za pomocą aplikacji pakietu Office.  

  **Domyślne**: Blokuj

- **Typ wykonywania pobranego ładunku skryptu**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) — określ poziom wykrywania potencjalnie niechcianych aplikacji, które przeprowadzają pobieranie lub podejmują próbę instalacji.  

  **Domyślne**: Blokuj 

- **Typ zapobiegania kradzieży poświadczeń**  
  Ustaw pozycję *Włącz*, aby [chronić pochodne poświadczenia domeny przy użyciu funkcji Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard). Funkcja Windows Defender Credential Guard używa zabezpieczeń opartych na wirtualizacji do izolowania kluczy tajnych, aby tylko uprzywilejowane oprogramowanie systemowe mogło uzyskiwać do nich dostęp. Nieautoryzowany dostęp do tych kluczy tajnych może prowadzić do ataków przy użyciu skradzionych poświadczeń, takich jak „pass the hash” lub „pass the ticket”. Funkcja Windows Defender Credential Guard zapobiega atakom przez ochronę skrótów haseł NTLM, biletów uprawniających do przyznawania biletów protokołu Kerberos i poświadczeń przechowywanych przez aplikacje, takich jak poświadczenia domeny.  

  **Domyślne**: Włącz

- **Typ wykonywania zawartości wiadomości e-mail**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Blokuj* ta reguła blokuje możliwość uruchamiania następujących typów plików z wiadomości e-mail w programie Microsoft Outlook lub poczcie internetowej (np. Gmail.com lub Outlook.com):  

  - Pliki wykonywalne (takie jak exe, dll lub scr)  
  - Pliki skryptów (takie jak plik ps programu PowerShell, plik vbs języka Visual Basic lub plik js języka JavaScript)  
  - Pliki archiwum skryptów  

  **Domyślne**: Blokuj

- **Uruchamianie programu Adobe Reader w procesie podrzędnym**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — *włącz* tę regułę, aby blokować tworzenie procesu podrzędnego w programie Adobe Reader. Za pośrednictwem inżynierii społecznej lub programów wykorzystujących luki w zabezpieczeniach złośliwe oprogramowanie może pobierać i uruchamiać dodatkowe ładunki, a także może wydostać się z programu Adobe Reader.  

  **Domyślne**: Włącz

- **Typ zaciemnionego kodu makra skryptu**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — złośliwe oprogramowanie i inne zagrożenia mogą próbować zaciemniać lub ukrywać złośliwy kod w niektórych plikach skryptów. Ta reguła uniemożliwia uruchamianie skryptów, które wydają się zaciemnione.  
    
  **Domyślne**: Blokuj

- **Niezaufany typ procesu USB**  
  [Reguły zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Blokuj* nie można uruchamiać niepodpisanych lub niezaufanych plików wykonywalnych z wymiennych dysków USB i kart SD.

  Pliki wykonywalne to:
  - Pliki wykonywalne (takie jak exe, dll lub scr)
  - Pliki skryptów (takie jak plik ps programu PowerShell, plik vbs języka Visual Basic lub plik js języka JavaScript)  

  **Domyślne**: Blokuj

- **Typ wstrzykiwania innych procesów aplikacji pakietu Office**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Blokuj* aplikacje pakietu Office, w tym programy Word, Excel, PowerPoint i OneNote, nie mogą wstrzykiwać kodu do innych procesów. Wstrzyknięcie kodu jest zazwyczaj używane przez złośliwe oprogramowanie, aby uruchomić złośliwy kod w celu ukrycia aktywności przed aparatami skanowania antywirusowego.  

  **Domyślne**: Blokuj

- **Kod makr w pakiecie Office zezwala na typ importu elementów Win32**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Blokuj* ta reguła próbuje zablokować pliki pakietu Office, które zawierają kod makra umożliwiający importowanie bibliotek DLL systemu Win32. Pliki pakietu Office to pliki programów Word, Excel, PowerPoint i OneNote. Złośliwe oprogramowanie może używać kodu makra w plikach pakietu Office, aby importować i ładować biblioteki DLL Win32, za pomocą których są następnie wykonywane wywołania interfejsu API w celu dalszego zainfekowania systemu.  

  **Domyślne**: Blokuj

- **Uruchamianie aplikacji komunikacyjnych pakietu Office w procesie podrzędnym**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Włącz* ta reguła uniemożliwia tworzenie procesów podrzędnych w programie Outlook. Blokując tworzenie procesu podrzędnego, ta reguła zapewnia ochronę przed atakami przy użyciu inżynierii społecznej i uniemożliwia wykorzystywanie luki w zabezpieczeniach programu Outlook przy użyciu kodu programu wykorzystującego luki tego typu.  

  **Domyślne**: Włącz

- **Tworzenie wykonywalnej zawartości lub typ uruchamiania aplikacji pakietu Office**  
  [Reguła zmniejszania obszaru podatnego na ataki](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) — po ustawieniu pozycji *Blokuj* aplikacje pakietu Office nie mogą tworzyć zawartości wykonywalnej. Aplikacje pakietu Office obejmują programy Word, Excel, PowerPoint, OneNote i Access.  

  Ta reguła dotyczy typowego zachowania używanego przez podejrzane i złośliwe dodatki oraz skrypty (rozszerzenia), które powoduje tworzenie lub uruchamianie plików wykonywalnych. Jest to typowa technika złośliwego oprogramowania. Używanie rozszerzeń przez aplikacje pakietu Office jest zablokowane. Zazwyczaj te rozszerzenia używają hosta skryptów systemu Windows (pliki wsh), aby uruchamiać skrypty, które automatyzują określone zadania lub udostępniają dodatkowe funkcje utworzone przez użytkownika.

  **Domyślne**: Blokuj

## <a name="bitlocker"></a>Funkcja BitLocker  

Więcej informacji można znaleźć na stronie [BitLocker Group Policy settings](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) (Ustawienia zasad grupy funkcji BitLocker) w dokumentacji systemu Windows.  

- **Szyfruj urządzenia**  
  Wybierz pozycję *Tak*, aby włączyć szyfrowanie urządzenia funkcją BitLocker. W zależności od urządzeń sprzętowych i wersji systemu Windows użytkownicy urządzeń mogą zostać poproszeni o sprawdzenie, czy na urządzeniu nie działa szyfrowanie innej firmy. Włączanie szyfrowania systemu Windows, gdy jest aktywne szyfrowane innej firmy, spowoduje, że urządzenie stanie się niestabilne.  

   **Domyślne**: Tak

- **Zasady dysków wymiennych funkcji BitLocker**  
  Wartości tych zasad określają siłę szyfru, którego funkcja BitLocker używa do szyfrowania dysków wymiennych. Przedsiębiorstwa kontrolują poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli wybierzesz pozycję *Tak*, aby włączyć to ustawienie, możesz skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk jest używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane. 

  W przypadku zasad dysków wymiennych funkcji BitLocker skonfiguruj następujące ustawienia:

  - **Wymagaj szyfrowania do zapisu**  
    **Domyślne**: Tak

  - **Metoda szyfrowania**  
    **Domyślne**: 128-bitowe szyfrowanie AES CBC

- **Zasady dysków stałych funkcji BitLocker**  
  Wartości tych zasad określają siłę szyfru, którego funkcja BitLocker używa do szyfrowania dysków stałych. Przedsiębiorstwa mogą kontrolować poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli włączysz to ustawienie, możesz skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk jest używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane.

  W przypadku zasad dysków stałych funkcji BitLocker skonfiguruj następujące ustawienia:

  - **Wymagaj szyfrowania do zapisu**  
    **Domyślne**: Tak

  - **Metoda szyfrowania**  
    **Domyślne**: 128-bitowe szyfrowanie AES XTS

- **Zasady dysków systemowych funkcji BitLocker**  
  Wartości tych zasad określają siłę szyfru, którego funkcja BitLocker używa do szyfrowania dysku systemowego. Przedsiębiorstwa mogą kontrolować poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli włączysz to ustawienie, możesz skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk jest używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane.  

  W przypadku zasad dysków systemowych funkcji BitLocker skonfiguruj następujące ustawienia:  

  - **Metoda szyfrowania**  
    **Domyślne**: 128-bitowe szyfrowanie AES XTS

## <a name="device-control"></a>Sterowanie urządzeniami  

- **Skanuj dyski wymienne podczas pełnego skanowania**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) — po ustawieniu pozycji *Tak* usługa Defender skanuje dyski wymienne, takie jak dyski flash, pod kątem złośliwego i niechcianego oprogramowania podczas pełnego skanowania. Program antywirusowy Defender skanuje wszystkie pliki na urządzeniach USB, zanim będzie można uruchomić pliki na urządzeniu USB.

  Powiązane ustawienia na tej liście: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Domyślne**: Tak

- **Wyliczanie urządzeń zewnętrznych niezgodnych z ochroną DMA jądra**  
   Zobacz sekcję *DmaGuard/DeviceEnumerationPolicy* w artykule [Policy CSP - DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy) (Dostawca usługi konfiguracji — DmaGuard)

  Te zasady są przeznaczone do zapewniania dodatkowych zabezpieczeń przed zewnętrznymi urządzeniami obsługującymi technologię DMA. Zapewniają one lepszą kontrolę nad wyliczaniem zewnętrznych urządzeń obsługujących technologię DMA, które są niezgodne z piaskownicowaniem i izolacją pamięci urządzenia z technologią DMA.

  Te zasady są stosowane tylko wtedy, gdy ochrona DMA jądra jest obsługiwana i włączana przez systemowe oprogramowanie układowe. Ochrona DMA jądra to funkcja platformy, której nie można kontrolować za pośrednictwem zasad i której nie może kontrolować użytkownik urządzenia. Musi ona być obsługiwana przez system w momencie produkcji. 

  Aby sprawdzić, czy system obsługuje ochronę DMA jądra, uruchom plik MSINFO32.exe w systemie i sprawdź pole *Ochrona DMA jądra* na stronie Podsumowanie.  

  Dostępne opcje: 
  - *Ustawienie domyślne urządzenia* — po zalogowaniu się lub odblokowaniu ekranu urządzenia ze sterownikami zgodnymi z ponownym mapowaniem technologii DMA mogą przeprowadzać wyliczanie w dowolnym momencie. Urządzenia ze sterownikami niezgodnymi z ponownym mapowaniem DMA będą wyliczane tylko po odblokowaniu ekranu przez użytkownika
  - *Zezwalaj na wszystkie* — wszystkie zewnętrzne urządzenia PCIe obsługujące technologię DMA będą wyliczane w dowolnym momencie
  - *Blokuj wszystkie* — urządzenia ze sterownikami zgodnymi z ponownym mapowaniem DMA mogą być wyliczane w dowolnym momencie. Urządzenia ze sterownikami niezgodnymi z ponownym mapowaniem DMA nie będą nigdy mogły uruchamiać ani wykonywać technologii DMA.

  **Domyślne**: Ustawienie domyślne urządzenia

- **Instalacja urządzeń sprzętowych według identyfikatorów urządzeń**  
  [DeviceInstallation/PreventInstallationOfMatchingDeviceIDs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) — te zasady umożliwiają określenie listy identyfikatorów sprzętu Plug and Play i zgodnych identyfikatorów urządzeń, których nie można zainstalować w systemie Windows. To ustawienie zasad ma pierwszeństwo przed innymi ustawieniami zasad, które umożliwiają zainstalowanie urządzenia w systemie Windows. Jeśli to ustawienie zasad zostanie włączone (ustawione na *Blokuj instalację urządzeń sprzętowych*), system Windows nie będzie mógł zainstalować urządzenia, którego identyfikator sprzętu lub zgodny identyfikator jest na utworzonej przez Ciebie liście. Jeśli włączysz to ustawienie zasad na serwerze usług pulpitu zdalnego, zasady będą wpływać na przekierowywanie określonych urządzeń z klienta usług pulpitu zdalnego na serwer usług pulpitu zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane (ustawione na *Zezwalaj na instalację urządzeń sprzętowych*), urządzenia będą mogły zostać zainstalowane i zaktualizowane zgodnie z innymi ustawieniami zasad.  

  **Domyślne**: blokuj instalację urządzeń sprzętowych  

  W przypadku wybrania pozycji *Blokuj instalację urządzeń sprzętowych* są dostępne następujące ustawienia.
  - **Usuń zgodne urządzenia sprzętowe**  
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według identyfikatorów urządzeń* ma wartość *Blokuj instalację urządzeń sprzętowych*.  

    **Domyślne:** : *brak konfiguracji domyślnej*

  - **Zablokowane identyfikatory urządzeń sprzętowych**  
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według identyfikatorów urządzeń* ma wartość *Blokuj instalację urządzeń sprzętowych*. Aby skonfigurować to ustawienie, rozwiń opcję, wybierz pozycję **+ Dodaj**, a następnie określ identyfikator urządzenia sprzętowego, które chcesz zablokować.  

    **Domyślne**: *Żadne urządzenia nie są blokowane*  

- **Blokuj bezpośredni dostęp do pamięci**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess) — to ustawienie zasad służy do blokowania bezpośredniego dostępu do pamięci dla wszystkich podrzędnych portów PCI z możliwością podłączenia podczas pracy na urządzeniu, dopóki użytkownik nie zaloguje się do systemu Windows. Po zalogowaniu się przez użytkownika system Windows wyliczy urządzenia PCI podłączone do portów PCI podłączenia hosta. Za każdym razem, gdy użytkownik zablokuje maszynę, bezpośredni dostęp do pamięci zostaje zablokowany na portach PCI z możliwością podłączenia podczas pracy bez urządzeń podrzędnych, dopóki użytkownik nie zaloguje się ponownie. Urządzenia, które były już wyliczone po odblokowaniu maszyny, będą w dalszym ciągu działać do czasu odłączenia. 

  To ustawienie zasad jest wymuszane tylko wtedy, gdy jest włączone szyfrowanie funkcją BitLocker lub szyfrowanie urządzenia.  

  **Domyślne**: Tak


- **Instalacja urządzeń sprzętowych według klas konfiguracji**  
  [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses) — te zasady służą do określenia listy unikatowych identyfikatorów globalnych (GUID) klas konfiguracji urządzeń dla sterowników urządzeń, których nie można zainstalować w systemie Windows. To ustawienie zasad ma pierwszeństwo przed innymi ustawieniami zasad, które umożliwiają zainstalowanie urządzenia w systemie Windows. Jeśli to ustawienie zasad zostanie włączone (ustawione na wartość *Blokuj instalacje urządzenia sprzętowego*), system Windows nie będzie mógł instalować ani aktualizować sterowników urządzeń, których identyfikatory GUID klas konfiguracji urządzeń są na utworzonej przez Ciebie liście. Jeśli włączysz to ustawienie zasad na serwerze usług pulpitu zdalnego, będzie ono wpływać na przekierowywanie określonych urządzeń z klienta usług pulpitu zdalnego na serwer usług pulpitu zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane (ustawione na wartość *Zezwalaj na instalację urządzeń sprzętowych*), system Windows będzie mógł instalować i aktualizować urządzenia zgodnie z innymi ustawieniami zasad.  

  **Domyślne**: blokuj instalację urządzeń sprzętowych

  W przypadku wybrania pozycji *Blokuj instalację urządzeń sprzętowych* są dostępne następujące ustawienia.  

  - **Usuń zgodne urządzenia sprzętowe**  
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według klas konfiguracji* ma wartość *Blokuj instalację urządzeń sprzętowych*.  
 
    **Domyślne:** : *brak konfiguracji domyślnej*  

  - **Zablokowane identyfikatory urządzeń sprzętowych**  
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie Instalacja urządzeń sprzętowych według klas konfiguracji ma wartość Blokuj instalację urządzeń sprzętowych. Aby skonfigurować to ustawienie, rozwiń opcję, wybierz pozycję **+ Dodaj**, a następnie określ identyfikator urządzenia sprzętowego, które chcesz zablokować.  
 
    **Domyślne**: *Żadne urządzenia nie są blokowane*

## <a name="endpoint-detection-and-response"></a>Wykrywanie punktów końcowych i reagowanie na nie  
Więcej informacji można znaleźć na stronie [WindowsAdvancedThreatProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) (WindowsAdvancedThreatProtection — dostawca usługi konfiguracji).  

- **Usprawnij częstotliwość raportowania danych telemetrycznych** - *Configuration/TelemetryReportingFrequency*  

  Usprawnij częstotliwość raportowania danych telemetrycznych usługi Zaawansowana ochrona przed zagrożeniami programu Microsoft Defender.  

  **Domyślne**: Tak

- **Udostępnianie próbek dla wszystkich plików** - *Configuration/SampleSharing*  

  Zwraca lub ustawia parametr konfiguracji udostępniania próbek zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender.  

  **Domyślne**: Tak

## <a name="exploit-protection"></a>Exploit Protection  

- **Plik XML ochrony przed programami wykorzystującymi luki w zabezpieczeniach**  
  Aby uzyskać więcej informacji, zobacz artykuł [Import, export, and deploy exploit protection configurations ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/import-export-exploit-protection-emet-xml) (Importowanie, eksportowanie i wdrażanie konfiguracji programów wykorzystujących luki w zabezpieczeniach) w dokumentacji systemu Windows.  

  Umożliwia administratorowi IT wypchnięcie konfiguracji reprezentującej środki zaradcze dla żądanego systemu i żądanej aplikacji do wszystkich urządzeń w organizacji. Konfiguracja jest reprezentowana przez kod XML. 

  Ochrona przed programami wykorzystującymi luki w zabezpieczeniach pomaga chronić urządzenia przed złośliwym oprogramowaniem, które rozpowszechnia się i infekuje za pomocą programów wykorzystujących luki w zabezpieczeniach. Aby utworzyć zestaw środków zaradczych (nazywanych konfiguracją), użyj aplikacji zabezpieczeń systemu Windows lub programu PowerShell. Możesz następnie wyeksportować tę konfigurację w pliku XML i udostępnić ją w wielu maszynach w sieci, aby wszystkie z nich korzystały z tego samego zestawu ustawień ograniczania ryzyka.
 
  Możesz też przekonwertować i zaimportować istniejący plik XML konfiguracji EMET do pliku XML konfiguracji ochrony.

- **Blokuj zastępowanie w obszarze ochrony przed programami wykorzystującymi luki w zabezpieczeniach**  
  [WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride) — ustaw pozycję *Tak*, aby uniemożliwić użytkownikom wprowadzanie zmian w obszarze ustawień ochrony przed programami wykorzystującymi luki w zabezpieczeniach w usłudze Windows Defender Security Center. Jeśli wyłączysz to urządzenie lub go nie skonfigurujesz, użytkownicy lokalni będą mogli wprowadzać zmiany w obszarze ustawień ochrony przed programami wykorzystującymi luki w zabezpieczeniach.  
  **Domyślne**: Tak  

- **Kontrolowany dostęp do folderów**  
  Zobacz sekcje [Defender/ControlledFolderAccessAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessallowedapplications) i [Defender/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 
  
   Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.

  **Domyślne**: Tryb inspekcji

## <a name="web--network-protection"></a>Ochrona Internetu i sieci  

- **Typ ochrony sieci**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) — te zasady umożliwiają włączanie lub wyłączanie ochrony sieci w funkcji Windows Defender Exploit Guard. Ochrona sieci w funkcji Windows Defender Exploit Guard chroni pracowników używających dowolnej aplikacji przed wyłudzeniem informacji, witrynami hostującymi programy wykorzystujące luki w zabezpieczeniach i złośliwą zawartością w Internecie. Obejmuje to blokadę połączeń w przeglądarkach innych firm z niebezpiecznymi witrynami.  

  Po ustawieniu pozycji *Włącz* lub *Tryb inspekcji* użytkownicy nie mogą wyłączyć ochrony sieci, a do wyświetlania informacji dotyczących prób nawiązania połączenia można użyć usługi Windows Defender Security Center.  
 
  - Pozycja *Włącz* zablokuje użytkownikom i aplikacjom możliwość łączenia z niebezpiecznymi domenami.  
  - Pozycja *Tryb inspekcji* nie blokuje użytkownikom i aplikacjom możliwości łączenia z niebezpiecznymi domenami.  

  Po ustawieniu pozycji *Zdefiniowane przez użytkownika* możliwość łączenia użytkowników i aplikacji z niebezpiecznymi domenami nie jest blokowana, a informacje o połączeniach nie są dostępne w usłudze Windows Defender Security Center.  

  **Domyślne**: Tryb inspekcji

- **Wymagaj filtra SmartScreen dla programu Microsoft Edge**  
  [Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) — przeglądarka Microsoft Edge domyślnie używa filtra SmartScreen w usłudze Windows Defender, aby chronić użytkowników przed potencjalnym wyłudzeniem informacji i złośliwym oprogramowaniem. Domyślnie te zasady są włączone (ustawione na wartość *Tak*), a po ich włączeniu użytkownicy nie mogą wyłączać filtru SmartScreen w usłudze Windows Defender.  Jeśli obowiązujące zasady mają wartość Nieskonfigurowane, użytkownicy mogą wyłączyć filtr SmartScreen w usłudze Windows Defender, pozostawiając w ten sposób urządzenia bez ochrony.  

  **Domyślne**: Tak
  
- **Blokuj dostęp do złośliwych witryn**  
  [Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride) — domyślnie przeglądarka Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych witryn, dzięki czemu użytkownicy mogą kontynuować korzystanie z witryny. Jeśli te zasady są włączone (ustawione na wartość *Tak*) przeglądarka Microsoft Edge uniemożliwia użytkownikom pomijanie ostrzeżeń i dalsze korzystanie z witryny.  

  **Domyślne**: Tak

- **Blokowanie pobierania niezweryfikowanych plików**  
  [Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles) — domyślnie przeglądarka Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych plików, dzięki czemu mogą kontynuować pobieranie niezweryfikowanych plików. Jeśli te zasady są włączone (ustawione na wartość *Tak*), użytkownicy nie mogą pomijać ostrzeżeń ani pobierać niezweryfikowanych plików.  

  **Domyślne**: Tak

## <a name="windows-defender-anti-virus----settings-review-pending-for-this-section"></a>Program antywirusowy usługi Windows Defender [ustawienia z tej sekcji oczekują na przegląd]

Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) w dokumentacji systemu Windows.

- **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning) — ustaw pozycję *Tak*, aby zezwolić na użycie funkcjonalności skanowania skryptów usługi Windows Defender.  

  **Domyślne**: Tak

- **Skanuj przychodzące wiadomości e-mail**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) — ustaw pozycję *Tak*, aby zezwolić na użycie funkcjonalności skanowania wiadomości e-mail usługi Windows Defender.  

  **Domyślne**: Tak

- **Typ zgody na przesyłanie przykładów usługi Defender**  
  [Defender/SubmitSamplesConsent](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) — sprawdza poziom zgody użytkownika na wysyłanie danych w usłudze Windows Defender. Jeśli udzielono już wymaganej zgody, usługa Windows Defender prześle dane. W przeciwnym razie (jeśli użytkownik wybrał, aby nigdy nie wyświetlać pytania) przed wysłaniem danych zostanie uruchomiony interfejs użytkownika z pytaniem o zgodę użytkownika (jeśli *Ochrona świadczona w chmurze* została ustawiona na *Tak*).  

  **Domyślne**: automatycznie wyślij bezpieczne próbki

- **Network Inspection System (NIS)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) — blokuj złośliwy ruch sieciowy wykryty przez podpisy w systemie Network Inspection System (NIS).  
 
  **Domyślne**: Tak

- **Interwał aktualizacji sygnatur (w godzinach)**  
  [Defender/SignatureUpdateInterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) — określ, jak często urządzenie sprawdza dostępność nowych aktualizacji podpisu usługi Defender (w godzinach).  
 
  **Domyślne**: 4

- **Skonfiguruj niski priorytet procesora CPU dla zaplanowanego skanowania**  
  [Defender/EnableLowCPUPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority) — po ustawieniu pozycji *Tak* priorytet procesora CPU w przypadku skanowania jest ustawiony na niski. Jeśli wartość to *Nieskonfigurowane*, nie są wprowadzane żadne zmiany priorytetu procesora CPU dla zaplanowanego skanowania.  

    **Domyślne**: Tak

- **Defender — blokuj ochronę przy dostępie**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection) — po ustawieniu pozycji *Tak* opcja Windows Defender — ochrona przy dostępie będzie włączona.  

  **Domyślne**: Tak

- **Typ skanowania systemu do wykonania**  
  [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter) — typ skanowania w usłudze Defender.  

  **Domyślne**: Szybkie skanowanie

- **Skanuj wszystkie pobrane pliki**  
  [Defender/AllowIOAVProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) — po ustawieniu pozycji *Tak* usługa Defender skanuje wszystkie pobrane pliki i załączniki.  

  **Domyślne**: Tak

- **Dni przed usunięciem złośliwego oprogramowania poddanego kwarantannie**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) — określ liczbę dni przechowywania elementów poddanych kwarantannie w systemie przed ich automatycznym usunięciem. Po ustawieniu tej opcji na zero elementy poddane kwarantannie nigdy nie będą automatycznie usuwane.  

  **Domyślnie**: 0

- **Czas rozpoczęcia planowanego skanowania**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime) — zaplanuj czas skanowania urządzeń w usłudze Defender. 
  
  Powiązana opcja na tej liście: *Defender/ScheduleScanDay*   

  **Domyślne**: 2:00

- **Ochrona w chmurze**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) — po ustawieniu pozycji *Tak* usługa Windows Defender wysyła do firmy Microsoft informacje dotyczące wszystkich znalezionych problemów. Firma Microsoft przeanalizuje te informacje, dowie się więcej na temat problemów wpływających na Ciebie i innych klientów oraz zaoferuje ulepszone rozwiązania.

  Jeśli te zasady zostaną ustawione na *Tak*, będzie można używać *typu zgody na przesyłanie przykładów w usłudze Defender*, aby przyznawać użytkownikom kontrolę nad wysyłaniem informacji z urządzenia.  

  **Domyślne**: Tak

- **Działanie dotyczące potencjalnie niechcianej aplikacji w usłudze Defender**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) — program antywirusowy Windows Defender może identyfikować i blokować pobieranie i instalowanie *potencjalnie niechcianych aplikacji* w punktach końcowych w sieci. 
 
  - Po ustawieniu pozycji *Blokuj* usługa Windows Defender blokuje potencjalnie niechciane aplikacje i wyświetla je w historii razem z innymi zagrożeniami.
  - Po ustawieniu pozycji *Inspekcja* usługa Windows Defender wykrywa potencjalnie niechciane aplikacje, ale ich nie blokuje. Informacje o aplikacjach, w stosunku do których usługa Windows Defender podjęłaby akcję, można znaleźć, przeszukując zdarzenia utworzone przez usługę Windows Defender w składniku Podgląd zdarzeń.  
  - Po ustawieniu pozycji *Ustawienie domyślne urządzenia* ochrona potencjalnie niechcianych aplikacji jest wyłączona.  
 
  **Domyślne**: Blokuj

- **Defender — rozszerzony limit czasu dla chmury**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout) — określ maksymalny dodatkowy czas, przez który Program antywirusowy Windows Defender powinien blokować plik podczas oczekiwania na wynik z chmury. Podstawowy czas oczekiwania przez usługę Windows Defender to 10 sekund. Dodatkowy czas określony w tym miejscu (maksymalnie 50 sekund) jest dodawany do tych 10 sekund. W większości przypadków skanowanie trwa krócej niż wartość maksymalna. Wydłużenie czasu pozwala chmurze na staranne zbadanie podejrzanych plików.  

  Domyślnie wartość rozszerzonego czasu ma wartość 0 (ustawienie wyłączone). Usługa Intune zaleca włączenie tego ustawienia i określenie co najmniej 20 dodatkowych sekund.  
 
  **Domyślnie**: 0

- **Skanuj pliki archiwum**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning) — ustaw pozycję *Tak*, aby usługa Windows Defender skanowała pliki archiwum.  

  **Domyślne**: Tak

- **Defender — harmonogram skanowania systemu**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday) — zaplanuj, w którym dniu usługa Defender będzie skanować urządzenia. 
 
  Powiązana opcja na tej liście: *Defender/ScheduleScanTime*

  **Domyślne**: Zdefiniowane przez użytkownika

- **Monitorowanie zachowania**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) — ustaw pozycję *Tak*, aby włączyć funkcję monitorowania zachowania usługi Windows Defender. Osadzone w systemie Windows 10 czujniki funkcji monitorowania zachowania usługi Windows Defender zbierają i przetwarzają sygnały dotyczące zachowania z systemu operacyjnego i wysyłają te dane czujników do prywatnego izolowanego wystąpienia usługi Microsoft Defender ATP w chmurze.  

  **Domyślne**: Tak

- **Skanuj pliki otwierane z folderów sieciowych**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) — ustaw pozycję *Tak*, aby usługa Windows Defender skanowała pliki w sieci. Użytkownik nie będzie mógł usunąć wykrytego złośliwego oprogramowania z plików tylko do odczytu.  

  **Domyślne**: Tak

- **Poziom blokady chmury w usłudze Defender**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) — użyj tych zasad, aby określić, jaki poziom agresywności reprezentuje Program antywirusowy Windows Defender podczas blokowania i skanowania podejrzanych plików. Dostępne opcje:

  - Wysoki — agresywne blokowanie nieznanych plików przy jednoczesnej optymalizacji wydajności klienta (większe prawdopodobieństwo wyników fałszywie dodatnich)
  - Wysoki plus — agresywne blokowanie nieznanych plików i stosowanie dodatkowych środków ochrony (może wpływać na wydajność klienta)
  - Zero tolerancji — blokowanie wszystkich nieznanych plików wykonywalnych

  **Domyślne**: nieskonfigurowane

- **Monitorowanie w czasie rzeczywistym**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring) — ustaw pozycję *Tak*, aby umożliwić monitorowanie usługi Windows Defender w czasie rzeczywistym.  

  **Domyślne**: Tak

- **Limit wykorzystania procesora CPU podczas skanowania**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) — określ użycie maksymalne średnie użycie procesora (%), z którego usługa Windows Defender może skorzystać podczas skanowania.  

  **Domyślne**: 50

- **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives) — ustaw pozycję *Tak*, aby usługa Windows Defender skanowała pliki w sieci. Użytkownik nie może usuwać wykrytego złośliwego oprogramowania z plików tylko do odczytu.

  Powiązane ustawienie na tej liście: *Defender/AllowScanningNetworkFiles*

  **Domyślne**: Tak

- **Blokuj użytkownikom końcowym dostęp do oprogramowania Defender**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess) — ustaw pozycję *Tak*, aby blokować użytkownikom końcowym dostęp do interfejsu użytkownika usługi Windows Defender w ich urządzeniu.  

  **Domyślne**: Tak

- **Czas rozpoczęcia szybkiego skanowania**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) — zaplanuj czas w ciągu dnia na uruchomienie szybkiego skanowania w usłudze Defender.  

  **Domyślne**: 2:00

## <a name="windows-defender-firewall"></a>Zapora Windows Defender
Więcej informacji można znaleźć na stronie [Firewall CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) (Zapora — dostawca usługi konfiguracji) w dokumentacji systemu Windows.

- **Czas bezczynności skojarzeń zabezpieczeń przed usunięciem** - *MdmStore/Global/SaIdleTime*   
  Skojarzenia zabezpieczeń są usuwane po wykryciu braku ruchu sieciowego przez tę liczbę sekund.  
  **Domyślne**: 300

- **Protokół transferu plików** - *MdmStore/Global/DisableStatefulFtp*   
  Blokuje stanowy protokół transferu plików (FTP).  
  **Domyślne**: Tak

- **Kolejkowanie pakietów** - *MdmStore/Global/EnablePacketQueue*    
  Określ sposób włączania skalowania oprogramowania po stronie odbierającej w przypadku zaszyfrowanego odbierania i przekazywania w postaci zwykłego tekstu dla scenariusza z bramą tunelu IPsec. Zapewnia to zachowanie kolejności pakietów.  
  **Domyślne**: Ustawienie domyślne urządzenia

- **Domena profilu zapory** - *FirewallRules/FirewallRuleName/Profiles*  
  Określa profile, do których należy reguła: Domena, Prywatny, Publiczny. Ta wartość reprezentuje profil sieci, które zostały połączone z domeną.  

  Dostępne ustawienia:  
  - **Wymagane odpowiedzi emisji pojedynczej na multiemisję/emisje**  
    **Domyślne**: Tak

  - **Reguły autoryzowanych aplikacji scalone z zasad grupy**  
    **Domyślne**: Tak

  - **Powiadomienia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Globalne reguły portów scalone z zasad grupy**  
    **Domyślne**: Tak

  - **Tryb niewidzialności zablokowany**  
    **Domyślne**: Tak

  - **Zapora włączona**  
    **Domyślne**: Dozwolone

  - **Reguły zabezpieczeń połączeń niescalone z zasad grupy**  
    **Domyślne**: Tak

  - **Reguły zasad niescalone z zasad grupy**  
    **Domyślne**: Tak

- **Publiczny profil zapory** - *FirewallRules/FirewallRuleName/Profiles*  
  Określa profile, do których należy reguła: Domena, Prywatny, Publiczny. Ta wartość reprezentuje profil sieci publicznych. Te sieci są klasyfikowane jako publiczne przez administratorów na hoście serwera. Klasyfikacja odbywa się po pierwszym połączeniu hosta z siecią. Przeważnie takie sieci znajdują się na lotniskach, w kawiarniach i w innych miejscach, w których elementy równorzędne w sieci lub administrator sieci nie jest zaufany.  

  Dostępne ustawienia:

  - **Połączenia przychodzące zablokowane**  
    **Domyślne**: Tak 

  - **Wymagane odpowiedzi emisji pojedynczej na multiemisję/emisje**  
    **Domyślne**: Tak  

  - **Tryb niewidzialności wymagany**  
    **Domyślne**: Tak 
 
  - **Połączenia wychodzące wymagane**  
    **Domyślne**: Tak  

  - **Reguły autoryzowanych aplikacji scalone z zasad grupy**  
    **Domyślne**: Tak  

  - **Powiadomienia przychodzące zablokowane**  
    **Domyślne**: Tak  

  - **Globalne reguły portów scalone z zasad grupy**  
    **Domyślne**: Tak

  - **Tryb niewidzialności zablokowany**  
    **Domyślne**: Tak

  - **Zapora włączona**  
    **Domyślne**: Dozwolone  

  - **Reguły zabezpieczeń połączeń niescalone z zasad grupy**  
    **Domyślne**: Tak  

  - **Ruch przychodzący wymagany**  
    **Domyślne**: Tak

  - **Reguły zasad niescalone z zasad grupy**  
    **Domyślne**: Tak  

- **Prywatny profil zapory** - *FirewallRules/FirewallRuleName/Profiles*  
  Określa profile, do których należy reguła: Domena, Prywatny, Publiczny. Ta wartość reprezentuje profil sieci prywatnych.  

  Dostępne ustawienia: 

  - **Połączenia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Wymagane odpowiedzi emisji pojedynczej na multiemisję/emisje**  
    **Domyślne**: Tak

  - **Tryb niewidzialności wymagany**  
    **Domyślne**: Tak

  - **Połączenia wychodzące wymagane**  
    **Domyślne**: Tak

  - **Powiadomienia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Globalne reguły portów scalone z zasad grupy**  
    **Domyślne**: Tak

  - **Tryb niewidzialności zablokowany**  
    **Domyślne**: Tak  

  - **Zapora włączona**  
    **Domyślne**: Dozwolone

  - **Reguły autoryzowanych aplikacji niescalone z zasad grupy**  
    **Domyślne**: Tak

  - **Reguły zabezpieczeń połączeń niescalone z zasad grupy**  
    **Domyślne**: Tak

  - **Ruch przychodzący wymagany**  
    **Domyślne**: Tak

  - **Reguły zasad niescalone z zasad grupy**  
    **Domyślne**: Tak  

- **Metoda kodowania klucza wstępnego zapory**  
  **Domyślne**: UTF8

- **Weryfikacja listy odwołania certyfikatów**  
  **Domyślne**: Ustawienie domyślne urządzenia

## <a name="windows-hello-for-business"></a>Windows Hello for Business  

Więcej informacji można znaleźć na stronie [PassportForWork CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) (PassportForWork — dostawca usługi konfiguracji) w dokumentacji systemu Windows.

- **Skonfiguruj funkcję Windows Hello dla firm** - *TenantId/Policies/UsePassportForWork*    
  Funkcja Windows Hello dla firm to alternatywna metoda logowania do systemu Windows przez zastępowanie haseł, kart inteligentnych i wirtualnych kart inteligentnych.  

  - W przypadku ustawienia *opcji tak*Włącz tę zasadę, a urządzenie zainicjuje funkcję Windows Hello dla firm.  
  - Jeśli ustawiono wartość *nie skonfigurowano*, linia bazowa nie ma wpływu na ustawienie zasad urządzenia. Oznacza to, że jeśli funkcja Windows Hello dla firm została wyłączona na urządzeniu, zostanie wyłączona. Jeśli jest włączona, pozostanie włączona. 

  Nie można wyłączyć usługi Windows Hello dla firm za jej podstawą. Można wyłączyć funkcję Windows Hello dla firm podczas konfigurowania [rejestracji systemu Windows](windows-hello.md)lub jako część profilu konfiguracji urządzenia na potrzeby [ochrony tożsamości](identity-protection-configure.md).  

Funkcja Windows Hello dla firm to alternatywna metoda logowania do systemu Windows przez zastępowanie haseł, kart inteligentnych i wirtualnych kart inteligentnych.  

  Jeśli włączysz to ustawienie zasad lub go nie skonfigurujesz, urządzenie będzie aprowizować funkcję Windows Hello dla firm. Jeśli wyłączysz to ustawienie zasad, urządzenie nie będzie aprowizować funkcji Windows Hello dla firm dla żadnego użytkownika.

  Usługa Intune nie obsługuje wyłączania usługi Windows Hello. W zamian można skonfigurować zasady, aby włączyć funkcję Windows Hello dla firm (pozycja Tak) lub aby nie konfigurować usługi Windows Hello bezpośrednio (pozycja Nieskonfigurowane). W przypadku pozycji Nieskonfigurowane urządzenie może uzyskać konfigurację za pomocą innych zasad, które mogą włączać lub wyłączać tę funkcję.  

  **Domyślne**: Tak  

- **Wymagaj małych liter w numerze PIN** - *TenantId/Policies/PINComplexity/LowercaseLetters*  
  **Domyślne**: Dozwolone  

- **Wymagaj znaków specjalnych w numerze PIN** - *TenantId/Policies/PINComplexity/SpecialCharacters*  
  **Domyślne**: Dozwolone  

- **Wymagaj wielkich liter w numerze PIN** - *TenantId/Policies/PINComplexity/LowercaseLetters*   
  **Domyślne**: Dozwolone  

