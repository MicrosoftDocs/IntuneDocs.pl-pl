---
title: Ustawienia zgodności dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem Windows 10 lub Windows Holographic oraz urządzeń Surface Hub w usłudze Microsoft Intune. Możesz między innymi sprawdzać zgodność z wymaganiami dotyczącymi minimalnej i maksymalnej wersji systemu operacyjnego, określać długość hasła i inne ograniczenia, sprawdzać stosowanie partnerskich rozwiązań antywirusowych czy włączać szyfrowanie magazynu danych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2e427fe0889dcfb51ba5be322ed4db566cc29e9d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502470"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem Windows 10 lub nowszym umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem Windows 10 lub nowszym za pomocą usługi Intune. Możesz stosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi wymagać korzystania z funkcji BitLocker, określać minimalną i maksymalną wersję systemu operacyjnego oraz określać poziom ryzyka na potrzeby zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender.

Ta funkcja ma zastosowanie do:

- System Windows 10 lub nowszy
- Windows Holographic for Business
- Surface Hub

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.

## <a name="device-health"></a>Device health

- **Wymagaj funkcji BitLocker**: po wybraniu opcji **Wymagaj** urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub przechodzi w stan hibernacji. Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika. Pomaga także zagwarantować, że zabezpieczenia nie zostaną naruszone nawet wtedy, gdy komputer zostanie zgubiony, skradziony lub pozostawiony bez nadzoru. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.

  W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna) to ustawienie nie jest oceniane na potrzeby określenia zgodności.

- **Wymagaj włączenia bezpiecznego rozruchu w urządzeniu**: po wybraniu opcji **Wymagaj** system musi włączać się do fabrycznie zaufanego stanu. W takiej sytuacji podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, uznawane za zaufane przez organizację, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI sprawdza podpis, zanim pozwoli na uruchomienie komputera. Jeśli jakiekolwiek pliki zostaną naruszone, co spowoduje uszkodzenie ich podpisu, system nie zostanie uruchomiony.

  W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna) to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  > [!NOTE]
  > Ustawienie **Wymagaj włączenia bezpiecznego rozruchu na urządzeniu** jest obsługiwane na niektórych urządzeniach z modułami TPM 1.2 i 2.0. W przypadku urządzeń, które nie obsługują modułu TPM 2.0 ani nowszego, stan zasad w usłudze Intune ma wartość **Niezgodne**. Aby uzyskać więcej informacji na temat obsługiwanych wersji, zobacz [Device Health Attestation (Zaświadczanie o kondycji urządzenia)](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Wymagaj integralności kodu**: integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci. Po wybraniu opcji **Wymagaj** funkcja integralności kodu wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy. Wykrywa ona także sytuację, w której plik systemowy został zmieniony przez złośliwe oprogramowanie uruchomione przez konto użytkownika z uprawnieniami administratora.

  W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna) to ustawienie nie jest oceniane na potrzeby określenia zgodności.

Więcej zasobów:

- Artykuł [Health Attestation CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) (Zaświadczanie o kondycji CSP) zawiera szczegółowe informacje na temat sposobu działania usługi HAS.
- [Support Tip: Using Device Health Attestation Settings as Part of Your Intune Compliance Policy](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643) (Porada pomocy technicznej: korzystanie z ustawień zaświadczania o kondycji urządzenia w ramach zasad zgodności usługi Intune)

## <a name="device-properties"></a>Właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: wprowadź minimalną dozwoloną wersję w formacie numerycznym **główna.pomocnicza.kompilacja.aktualizacja_zbiorcza**. Aby uzyskać prawidłową wartość, otwórz wiersz polecenia i wpisz `ver`. Polecenie `ver` zwraca wersję w następującym formacie:

  `Microsoft Windows [Version 10.0.17134.1]`

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż wprowadzona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może wybrać opcję uaktualnienia urządzenia. Po uaktualnieniu użytkownik będzie mógł uzyskiwać dostęp do zasobów firmy.

- **Maksymalna wersja systemu operacyjnego**: wprowadź maksymalną dozwoloną wersję w formacie numerycznym **główna.pomocnicza.kompilacja.poprawka**. Aby uzyskać prawidłową wartość, otwórz wiersz polecenia i wpisz `ver`. Polecenie `ver` zwraca wersję w następującym formacie:

  `Microsoft Windows [Version 10.0.17134.1]`

  Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie będzie mogło uzyskiwać dostępu do zasobów organizacji, dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego.

- **Wymagana minimalna wersja systemu operacyjnego dla urządzeń przenośnych**: wprowadź minimalną dozwoloną wersję w formacie numerycznym główna.pomocnicza.kompilacja.

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż wprowadzona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może wybrać opcję uaktualnienia urządzenia. Po uaktualnieniu użytkownik będzie mógł uzyskiwać dostęp do zasobów firmy.

- **Wymagana maksymalna wersja systemu operacyjnego dla urządzeń przenośnych**: wprowadź maksymalną dozwoloną wersję w formacie numerycznym główna.pomocnicza.kompilacja.

  Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie będzie mogło uzyskiwać dostępu do zasobów organizacji, dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego.

- **Prawidłowe kompilacje systemów operacyjnych**: wprowadź zakres dopuszczalnych wersji systemu operacyjnego, w tym wersję minimalną i maksymalną. Możesz również **wyeksportować** listę plików wartości rozdzielanych przecinkami (CSV), która będzie zawierać dopuszczalne numery kompilacji systemu operacyjnego.

## <a name="configuration-manager-compliance"></a>Zgodność w programie Configuration Manager

Dotyczy tylko współzarządzanych urządzeń z systemem Windows 10 lub nowszym. Urządzenia przeznaczone tylko dla usługi Intune zwracają stan Niedostępne.

- **Wymagaj zgodności urządzenia z poziomu programu System Center Configuration Manager**: wybierz pozycję **Wymagaj**, aby wymuszać zgodność wszystkich ustawień (elementów konfiguracji) w programie System Center Configuration Manager. 

  Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie jest niezgodne w usłudze Intune.
  
  Pozycja **Nieskonfigurowane** oznacza, że usługa Intune nie sprawdza zgodności żadnego z ustawień programu Configuration Manager.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia. Gdy **nie zostanie skonfigurowana**, usługa Intune nie oceni urządzenia pod kątem zgodności z ustawieniami haseł.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Typ hasła**: wybierz wymagany typ hasła lub numeru PIN. Dostępne opcje:

  - **Ustawienie domyślne urządzenia**: Wymagaj hasła, NUMERYCZNego numeru PIN lub ALFANUMERYCZNEGO kodu PIN
  - Wartość **numeryczna**: Wymagaj hasła lub numerycznego numeru PIN
  - **Alfanumeryczne**: Wymagaj hasła lub ALFANUMERYCZNEGO kodu PIN. Należy również wybrać **złożoność hasła**: 
    
    - **Wymagaj cyfr i małych liter**
    - **Wymagaj cyfr, małych liter i wielkich liter**
    - **Wymagaj cyfr, małych i wielkich liter oraz znaków specjalnych**

    > [!TIP]
    > Zasady haseł alfanumerycznych mogą być złożone. Zachęcamy administratorów do odczytywania dostawców usług, aby uzyskać więcej informacji:
    >
    > - [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [DeviceLock/MinDevicePasswordComplexCharacters CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)** : wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe, z zakresu 1–730.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.
- **Wymagaj hasła, gdy urządzenie wraca ze stanu bezczynności (Mobile i Holographic)** : wymuszaj wprowadzanie haseł przez użytkowników za każdym razem, gdy urządzenie wraca ze stanu bezczynności.

  > [!IMPORTANT]
  > Kiedy wymóg dotyczący hasła zostanie zmieniony na komputerze z systemem Windows, użytkownicy będą musieli się do niego dostosować przy następnym logowaniu, ponieważ to właśnie wtedy urządzenie przechodzi ze stanu bezczynności w stan aktywności. Użytkownicy, których hasła spełniają wymagania, także zostaną poproszeniu o zmianę hasła.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu**: wybierz pozycję **Wymagaj**, aby szyfrować magazyn danych na urządzeniach.

  > [!NOTE]
  > Ustawienie **Szyfrowanie magazynu danych na urządzeniu** ogólnie sprawdza, czy na urządzeniu jest stosowane szyfrowanie. Aby uzyskać bardziej niezawodne ustawienie szyfrowania, rozważ użycie opcji **Wymagaj funkcji BitLocker**, która korzysta z zaświadczania o kondycji urządzenia systemu Windows w celu weryfikowania stanu funkcji BitLocker na poziomie modułu TPM.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Zapora**: Ustaw opcję **Wymagaj** , aby włączyć zaporę usługi Microsoft Defender, i uniemożliwić użytkownikom jej wyłączenie. **Nie skonfigurowano** (wartość domyślna) nie steruje zaporą programu Microsoft Defender ani nie zmienia istniejących ustawień.

  [Dostawca CSP zapory](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Jeśli urządzenie zostanie natychmiast zsynchronizowane po ponownym uruchomieniu lub natychmiast zsynchronizuje wznawianie z uśpienia, to ustawienie może zgłosić **błąd**. Ten scenariusz może nie wpływać na ogólny stan zgodności urządzenia. Aby ponownie oszacować stan zgodności, należy ręcznie [zsynchronizować urządzenie](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

- **Moduł TPM (TPM)** : w przypadku wybrania opcji **Wymagaj**usługa Intune sprawdza wersję pod kątem zgodności. Urządzenie jest zgodne, jeśli wersja mikroukładu modułu TPM jest większa od 0 (zero). Urządzenie nie jest zgodne, jeśli na urządzeniu nie ma wersji modułu TPM. Gdy **nie zostanie skonfigurowana**, usługa Intune nie sprawdza urządzenia pod kątem wersji mikroukładu modułu TPM.

  [DeviceStatus CSP — węzeł DeviceStatus/TPM/SpecificationVersion](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Oprogramowanie antywirusowe**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antywirusowych zarejestrowanych w [Centrum zabezpieczeń systemu Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), na przykład rozwiązań firmy Symantec i usługi Microsoft Defender. W przypadku wybrania ustawienia **Nieskonfigurowane** usługa Intune nie będzie wykonywać sprawdzania w poszukiwaniu jakichkolwiek rozwiązań antywirusowych zainstalowanych na urządzeniu.
- **Oprogramowanie antyszpiegowskie**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antyszpiegowskich zarejestrowanych w [Centrum zabezpieczeń systemu Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), na przykład rozwiązań firmy Symantec i usługi Microsoft Defender. W przypadku wybrania ustawienia **Nieskonfigurowane** usługa Intune nie będzie wykonywać sprawdzania w poszukiwaniu jakichkolwiek rozwiązań antyszpiegowskich zainstalowanych na urządzeniu.

### <a name="defender"></a>Usługa Defender

- Ochrona **przed złośliwym oprogramowaniem usługi Microsoft Defender**: Ustaw opcję **Wymagaj** , aby włączyć usługę Microsoft Defender Anti-Malware, i uniemożliwić użytkownikom jej wyłączenie. **Nie skonfigurowano** (domyślnie) nie steruje usługą ani nie zmienia istniejących ustawień.
- **Minimalna wersja programu Microsoft Defender chroniącego przed złośliwym kodem**: wprowadź minimalną dozwoloną wersję usługi Microsoft Defender Anti-Malware. Na przykład wprowadź `4.11.0.0`. Jeśli pole pozostanie puste, można użyć dowolnej wersji usługi Microsoft Defender Anti-Malware.
- **Aktualna usługa Microsoft Defender ochrony przed złośliwym kodem**: kontroluje aktualizacje oprogramowania antywirusowego zabezpieczeń systemu Windows i ochrony przed zagrożeniami na urządzeniach. **Wymagaj** wymuszania Aktualności analizy zabezpieczeń programu Microsoft Defender. **Nieskonfigurowane** (domyślnie) nie wymusza żadnych wymagań.

  [Aktualizacje analizy zabezpieczeń dla programu Microsoft Defender Antivirus i innych programów chroniących przed złośliwym oprogramowaniem firmy Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates) mają więcej informacji na temat analizy zabezpieczeń.

- **Ochrona**w czasie rzeczywistym: **wymagane** jest włączenie ochrony w czasie rzeczywistym, która skanuje w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niechciane oprogramowanie. **Nie skonfigurowano** (domyślnie) nie kontroluje tej funkcji ani nie zmienia istniejących ustawień.

  [Usługa Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Usługa Microsoft Defender ATP

- **Wymagaj, aby urządzenie było na poziomie niższym lub równym ocenie ryzyka maszyny**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z usług ochrony przed zagrożeniami jako warunek zgodności. Wybierz maksymalny dozwolony poziom zagrożenia:

  - **Czyste**: ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
  
  Aby skonfigurować usługę Microsoft Defender ATP (Advanced Threat Protection) jako usługę do ochrony przed zagrożeniami, zobacz [Włączanie usługi Microsoft Defender ATP z dostępem warunkowym](advanced-threat-protection.md).

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

System Windows Holographic for Business używa platformy **Windows 10 i nowsze**. System Windows Holographic for Business obsługuje następujące ustawienie:

- **Zabezpieczenia systemu** > **Szyfrowanie** > **Szyfrowanie magazynu danych na urządzeniu**.

Aby sprawdzić szyfrowanie urządzenia na urządzeniu Microsoft HoloLens, zobacz [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) (Weryfikowanie szyfrowania urządzenia).

## <a name="surface-hub"></a>Surface Hub

Urządzenie Surface Hub używa platformy **Windows 10 i nowsze**. Urządzenia Surface Hub są obsługiwane pod kątem zgodności i dostępu warunkowego. Aby włączyć te funkcje na urządzeniach Surface Hub, zalecamy [włączenie automatycznej rejestracji systemu Windows 10](../enrollment/windows-enroll.md) w usłudze Intune (wymaga to użycia usługi Azure Active Directory — Azure AD) i ustawienie urządzeń Surface Hub jako docelowych grup urządzeń. Urządzenia Surface Hub należy przyłączyć do usługi Azure AD, aby funkcje zgodności i dostępu warunkowego działały.

Zobacz temat [Konfigurowanie rejestracji dla urządzeń z systemem Windows](../enrollment/windows-enroll.md) w celu uzyskania wytycznych.

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem Windows 8.1](compliance-policy-create-windows-8-1.md).
