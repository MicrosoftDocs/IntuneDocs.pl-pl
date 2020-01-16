---
title: Ustawienia zgodności dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem Windows 10 lub Windows Holographic oraz urządzeń Surface Hub w usłudze Microsoft Intune. Możesz między innymi sprawdzać zgodność z wymaganiami dotyczącymi minimalnej i maksymalnej wersji systemu operacyjnego, określać długość hasła i inne ograniczenia, sprawdzać stosowanie partnerskich rozwiązań antywirusowych czy włączać szyfrowanie magazynu danych.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ca5d475f92cbe3298689273dcdf0da1644078b2
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547031"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem Windows 10 lub nowszym umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem Windows 10 lub nowszym za pomocą usługi Intune. Możesz stosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi wymagać korzystania z funkcji BitLocker, określać minimalną i maksymalną wersję systemu operacyjnego oraz określać poziom ryzyka na potrzeby zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender.

Ta funkcja ma zastosowanie do:

- Windows 10 lub nowszym
- Windows Holographic for Business
- Surface Hub

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.

## <a name="device-health"></a>Kondycja urządzenia

### <a name="windows-health-attestation-service-evaluation-rules"></a>Reguły oceny usługi zaświadczeń o kondycji systemu Windows

- **Wymagaj funkcji BitLocker**:  
   Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika. Pomaga także zagwarantować, że zabezpieczenia nie zostaną naruszone nawet wtedy, gdy komputer zostanie zgubiony, skradziony lub pozostawiony bez nadzoru. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.  

   - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
   - **Wymagaj** — urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub przechodzi w stan hibernacji.  


- **Wymagaj włączenia bezpiecznego rozruchu na urządzeniu**:  
    - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
    - **Wymagaj** — system jest wymuszany do rozruchu w stanie zaufanym fabryki. Podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, uznawane za zaufane przez organizację, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI sprawdza podpis, zanim pozwoli na uruchomienie komputera. Jeśli jakiekolwiek pliki zostaną naruszone, co spowoduje uszkodzenie ich podpisu, system nie zostanie uruchomiony.

  > [!NOTE]
  > Ustawienie **Wymagaj włączenia bezpiecznego rozruchu na urządzeniu** jest obsługiwane na niektórych urządzeniach z modułami TPM 1.2 i 2.0. W przypadku urządzeń, które nie obsługują modułu TPM 2.0 ani nowszego, stan zasad w usłudze Intune ma wartość **Niezgodne**. Aby uzyskać więcej informacji na temat obsługiwanych wersji, zobacz [Device Health Attestation (Zaświadczanie o kondycji urządzenia)](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Wymagaj integralności kodu**:  
  integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci.
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  -  **Wymagaj** — wymagana jest funkcja integralności kodu, która wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy. Wykrywa ona także sytuację, w której plik systemowy jest zmieniany przez złośliwe oprogramowanie lub uruchamiany przez konto użytkownika z uprawnieniami administratora.

Więcej zasobów:

- Aby uzyskać szczegółowe informacje o działaniu usługi zaświadczania o kondycji, zobacz [CSP zaświadczania o kondycji](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).
- [Support Tip: Using Device Health Attestation Settings as Part of Your Intune Compliance Policy](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643) (Porada pomocy technicznej: korzystanie z ustawień zaświadczania o kondycji urządzenia w ramach zasad zgodności usługi Intune).

## <a name="device-properties"></a>Właściwości urządzenia

### <a name="operating-system-version"></a>Wersja systemu operacyjnego

- **Minimalna wersja systemu operacyjnego**:  
  wprowadź minimalną dozwoloną wersję w formacie numerycznym **główna.pomocnicza.kompilacja.aktualizacja_zbiorcza**. Aby uzyskać prawidłową wartość, otwórz wiersz polecenia i wpisz `ver`. Polecenie `ver` zwraca wersję w następującym formacie:

  `Microsoft Windows [Version 10.0.17134.1]`

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż wprowadzona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może wybrać opcję uaktualnienia urządzenia. Po uaktualnieniu użytkownik będzie mógł uzyskiwać dostęp do zasobów firmy.

- **Maksymalna wersja systemu operacyjnego**:  
  wprowadź maksymalną dozwoloną wersję w formacie numerycznym **główna.pomocnicza.kompilacja.poprawka**. Aby uzyskać prawidłową wartość, otwórz wiersz polecenia i wpisz `ver`. Polecenie `ver` zwraca wersję w następującym formacie:

  `Microsoft Windows [Version 10.0.17134.1]`

  Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie będzie mogło uzyskiwać dostępu do zasobów organizacji, dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego.

- **Minimalna wersja systemu operacyjnego wymagana dla urządzeń przenośnych**:  
  wprowadź minimalną dozwoloną wersję w formacie numerycznym główna.pomocnicza.kompilacja.

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż wprowadzona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może wybrać opcję uaktualnienia urządzenia. Po uaktualnieniu użytkownik będzie mógł uzyskiwać dostęp do zasobów firmy.

- **Maksymalna wersja systemu operacyjnego wymagana dla urządzeń przenośnych**:  
  wprowadź maksymalną dozwoloną wersję w formacie numerycznym główna.pomocnicza.kompilacja.

  Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie będzie mogło uzyskiwać dostępu do zasobów organizacji, dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego.

- **Prawidłowe kompilacje systemów operacyjnych**:  
  wprowadź zakres dopuszczalnych wersji systemu operacyjnego, w tym wersję minimalną i maksymalną. Możesz również **wyeksportować** listę plików wartości rozdzielanych przecinkami (CSV), która będzie zawierać dopuszczalne numery kompilacji systemu operacyjnego.

## <a name="configuration-manager-compliance"></a>Zgodność w programie Configuration Manager

Dotyczy tylko współzarządzanych urządzeń z systemem Windows 10 lub nowszym. Urządzenia przeznaczone tylko dla usługi Intune zwracają stan Niedostępne.

- **Wymagaj zgodności urządzenia z poziomu programu Configuration Manager**  
  - **Nieskonfigurowane** (*wartość domyślna*) — usługa Intune nie sprawdza zgodności żadnego z ustawień programu Configuration Manager.
  - **Wymagaj** — wymagana jest zgodność wszystkich ustawień (elementów konfiguracji) w programie Configuration Manager.  

    Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie jest niezgodne w usłudze Intune.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń. 

- **Proste hasła**:  
  - **Nie skonfigurowano** (*domyślne*) — użytkownicy mogą tworzyć proste hasła, takie jak **1234** lub **1111**.
  - **Blokuj** — użytkownicy nie mogą tworzyć prostych haseł, takich jak **1234** lub **1111**.

- **Typ hasła**:  
  wybierz wymagany typ hasła lub numeru PIN. Dostępne opcje:
  - **Domyślne** urządzenia (*domyślne*) — Wymagaj hasła, numerycznego numeru PIN lub alfanumerycznego kodu
  - **Numeryczne** — Wymagaj hasła lub numerycznego numeru PIN
  - **alfanumeryczne** — Wymagaj hasła lub alfanumerycznego kodu PIN.  
  
  Po ustawieniu na *alfanumeryczne* dostępne są następujące ustawienia:  
  - **Złożoność hasła**:  
    Dostępne opcje: 
    - **Wymagaj cyfr i małych liter** (*domyślne*)
    - **Wymagaj cyfr oraz małych i wielkich liter**
    - **Wymagaj cyfr, małych i wielkich liter oraz znaków specjalnych**

    > [!TIP]
    > Zasady haseł alfanumerycznych mogą być złożone. Zachęcamy administratorów do odczytywania dostawców usług, aby uzyskać więcej informacji:
    >
    > - [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [DeviceLock/MinDevicePasswordComplexCharacters CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimalna długość hasła**:  
  wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**:  
  wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni)** :  
  wprowadź liczbę dni, po których wygasa hasło i należy utworzyć nowe, z zakresu 1–730.

- **Liczba poprzednich haseł, których nie można użyć ponownie**:  
  wprowadź liczbę wcześniej używanych haseł, których nie można użyć ponownie.

- **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności (systemy Mobile i Holographic)** :  
  - **Nie skonfigurowano** (*wartość domyślna*)
  - **Wymagaj** — od użytkowników wymagane jest wprowadzanie hasła za każdym razem, gdy urządzenie wraca ze stanu bezczynności.

  > [!IMPORTANT]
  > Kiedy wymóg dotyczący hasła zostanie zmieniony na komputerze z systemem Windows, użytkownicy będą musieli się do niego dostosować przy następnym logowaniu, ponieważ to właśnie wtedy urządzenie przechodzi ze stanu bezczynności w stan aktywności. Użytkownicy, których hasła spełniają wymagania, także zostaną poproszeniu o zmianę hasła.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**:  
  To ustawienie ma zastosowanie do wszystkich dysków na urządzeniu.
  - **Nie skonfigurowano** (*wartość domyślna*)
  - **Wymagaj** — wybierz pozycję *Wymagaj*, aby szyfrować magazyn danych na urządzeniach.

  > [!NOTE]
  > Ustawienie **Szyfrowanie magazynu danych na urządzeniu** ogólnie sprawdza, czy na urządzeniu jest stosowane szyfrowanie. Aby uzyskać bardziej niezawodne ustawienie szyfrowania, rozważ użycie opcji **Wymagaj funkcji BitLocker**, która korzysta z zaświadczania o kondycji urządzenia systemu Windows w celu weryfikowania stanu funkcji BitLocker na poziomie modułu TPM.

### <a name="device-security"></a>Zabezpieczenia urządzeń  

- **Zapora**:  
  - **Nie skonfigurowano** (*domyślne*) — usługa Intune nie kontroluje zapory Microsoft Defender ani nie zmienia istniejących ustawień.
  - **Wymagaj** Włącz zaporę usługi Microsoft Defender i uniemożliwiaj jej wyłączenie.  

  [Dostawca CSP zapory](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Jeśli urządzenie zostanie natychmiast zsynchronizowane po ponownym uruchomieniu lub natychmiast zsynchronizuje wznawianie z trybu uśpienia, to ustawienie może być zgłaszane jako **błąd**. Ten scenariusz może nie wpływać na ogólny stan zgodności urządzenia. Aby ponownie oszacować stan zgodności, ręcznie [zsynchronizować](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)urządzeń.

- **Moduł TPM (Trusted Platform Module)** :  
  - **Nie skonfigurowano** (*domyślne*) — usługa Intune nie sprawdza urządzenia pod kątem wersji mikroukładu modułu TPM.
  - **Wymagaj** — usługa Intune sprawdza, czy wersja mikroukładu modułu TPM jest zgodna ze zgodnością. Urządzenie jest zgodne, jeśli wersja mikroukładu modułu TPM jest większa niż **0** (zero). Urządzenie nie jest zgodne, jeśli na urządzeniu nie ma wersji modułu TPM.  

  [DeviceStatus CSP — węzeł DeviceStatus/TPM/SpecificationVersion](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Oprogramowanie antywirusowe**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — usługa Intune nie będzie wykonywać sprawdzania w poszukiwaniu jakichkolwiek rozwiązań antywirusowych zainstalowanych na urządzeniu. 
  - **Wymagaj** — sprawdzanie zgodności przy użyciu rozwiązań antywirusowych zarejestrowanych w [Centrum zabezpieczeń systemu Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), na przykład rozwiązań firmy Symantec i usługi Microsoft Defender.

- **Program antyszpiegowski**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — usługa Intune nie będzie wykonywać sprawdzania w poszukiwaniu jakichkolwiek rozwiązań antyszpiegowskich zainstalowanych na urządzeniu.
  - **Wymagaj** — sprawdzanie zgodności przy użyciu rozwiązań antyszpiegowskich zarejestrowanych w [Centrum zabezpieczeń systemu Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), na przykład rozwiązań firmy Symantec i usługi Microsoft Defender.  

### <a name="defender"></a>Usługa Defender

*Następujące ustawienia zgodności są obsługiwane w systemie Windows 10 Desktop.*

- **Microsoft Defender Antimalware**  
  - **Nie skonfigurowano** (*domyślne*) — usługa Intune nie kontroluje usługi ani nie zmienia istniejących ustawień.
  - **Wymagaj** Włącz usługę Microsoft Defender Anti-złośliwe oprogramowanie i uniemożliwiaj użytkownikom jej wyłączenie.

- **Minimalna wersja usługi Microsoft Defender Antimalware**  
  Wprowadź minimalną dozwoloną wersję usługi Microsoft Defender chroniącej przed złośliwym oprogramowaniem. Na przykład wprowadź `4.11.0.0`. Jeśli pole pozostanie puste, można użyć dowolnej wersji usługi Microsoft Defender Anti-Malware.  

  *Domyślnie żadna wersja nie jest skonfigurowana*.

- **Aktualna analiza zabezpieczeń usługi Microsoft Defender Antimalware**  
  Kontroluje aktualizacje oprogramowania antywirusowego zabezpieczeń systemu Windows i ochrony przed zagrożeniami na urządzeniach.
  - **Nie skonfigurowano** (*domyślne*) — usługa Intune nie wymusza żadnych wymagań.
  - **Wymagaj**, aby analiza zabezpieczeń usługi Microsoft Defender była aktualna.

  [Usługa Defender/Health/SignatureOutOfDate CSP](https://docs.microsoft.com/windows/client-management/mdm/defender-csp)
  
  Aby uzyskać więcej informacji, zobacz [aktualizacji analizy zabezpieczeń dla programu Microsoft Defender Antivirus i innych](https://www.microsoft.com/en-us/wdsi/defenderupdates)ochrony przed złośliwym oprogramowaniem firmy Microsoft.

- **Ochrona w czasie rzeczywistym**:  
  - **Nie skonfigurowano** (*domyślne*) — usługa Intune nie kontroluje tej funkcji ani nie zmienia istniejących ustawień.
  - **Wymagaj** Włącz ochronę w czasie rzeczywistym, która skanuje w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niechciane oprogramowanie.  

  [Usługa Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Usługa Microsoft Defender ATP

### <a name="microsoft-defender-advanced-threat-protection-rules"></a>Reguły zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender

- **Wymagaj, aby urządzenie było na poziomie niższym lub równym ocenie ryzyka maszyny**:  
  użyj tego ustawienia, aby uzyskać ocenę ryzyka z usług ochrony przed zagrożeniami jako warunek zgodności. Wybierz maksymalny dozwolony poziom zagrożenia:
  - **Nie skonfigurowano** (*wartość domyślna*)  
  - **Czyste** — ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu zostanie ono ocenione jako niezgodne.
  - **Niski** — urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni** — urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** — ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
  
  Aby skonfigurować usługę Microsoft Defender ATP (Advanced Threat Protection) jako usługę do ochrony przed zagrożeniami, zobacz [Włączanie usługi Microsoft Defender ATP z dostępem warunkowym](advanced-threat-protection.md).


## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

System Windows Holographic for Business używa platformy **Windows 10 i nowsze**. System Windows Holographic for Business obsługuje następujące ustawienie:

- **Zabezpieczenia systemu** > **Szyfrowanie** > **Szyfrowanie magazynu danych na urządzeniu**.

Aby sprawdzić szyfrowanie urządzenia na urządzeniu Microsoft HoloLens, zobacz [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) (Weryfikowanie szyfrowania urządzenia).

## <a name="surface-hub"></a>Surface Hub

Urządzenie Surface Hub używa platformy **Windows 10 i nowsze**. Urządzenia Surface Hub są obsługiwane pod kątem zgodności i dostępu warunkowego. Aby włączyć te funkcje na urządzeniach Surface Hub, zalecamy [włączenie automatycznej rejestracji systemu Windows 10](../enrollment/windows-enroll.md) w usłudze Intune (wymaga to użycia usługi Azure Active Directory — Azure AD) i ustawienie urządzeń Surface Hub jako docelowych grup urządzeń. Urządzenia Surface Hub należy przyłączyć do usługi Azure AD, aby funkcje zgodności i dostępu warunkowego działały.

W celu uzyskania wytycznych zobacz informacje na temat [konfigurowania rejestracji dla urządzeń z systemem Windows](../enrollment/windows-enroll.md).

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem Windows 8.1](compliance-policy-create-windows-8-1.md).
