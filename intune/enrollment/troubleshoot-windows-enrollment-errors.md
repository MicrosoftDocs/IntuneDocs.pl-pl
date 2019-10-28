---
title: Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestie dotyczące rozwiązywania niektórych typowych problemów podczas rejestrowania urządzeń z systemem Windows w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5776ebf3241968cca6da537bb58b7ab2a06f00ba
ms.sourcegitcommit: f12bd2ce10b6241715bae2d2857f33c474287166
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2019
ms.locfileid: "72892540"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune

Ten artykuł ułatwia administratorom usługi Intune zrozumienie i rozwiązywanie problemów podczas rejestrowania urządzeń z systemem Windows w usłudze Intune.

## <a name="prerequisites"></a>Wymagania wstępne
Przed rozpoczęciem rozwiązywania problemów należy zebrać podstawowe informacje. Te informacje mogą pomóc w lepszym zrozumieniu problemu i skrócić czas, aby znaleźć rozwiązanie.

Zbierz następujące informacje o problemie:
- Czy do użytkownika jest przypisana prawidłowa licencja usługi Intune? Aby użytkownicy mogli rejestrować swoje urządzenia, muszą mieć przypisaną wymaganą licencję.
- Czy Najnowsza aktualizacja jest zainstalowana na urządzeniu z systemem Windows? Niektóre funkcje usługi Intune współpracują tylko z najnowszą wersją systemu Windows. Istnieje wiele poprawek znanych problemów dostępnych za poorednictwem Windows Update. Zastosowanie wszystkich najnowszych aktualizacji często rozwiązuje problem z rejestracją urządzenia z systemem Windows. 
- Jaki jest dokładny komunikat o błędzie?
- Gdzie zobaczysz komunikat o błędzie?
- Kiedy problem zaczął występować? Czy rejestracja została kiedykolwiek zadziałała? 
- Na jakiej platformie (Android, iOS, Windows) występuje problem?
- Ilu użytkowników dotyczy ten wpływ? Czy wszyscy użytkownicy mają te same lub tylko niektóre?
- Ile urządzeń ma wpływ? Czy dotyczy to wszystkich urządzeń?
- Co to jest urząd MDM? Jeśli jest System Center Configuration Manager, jakiej wersji Configuration Manager są używane?
- Jak odbywa się rejestracja? Czy jest to "Dobierz własne urządzenie" (BYOD), czy Apple Device Enrollment Program (DEP) z profilami rejestracji?

## <a name="error-messages"></a>Komunikaty o błędach

### <a name="this-user-is-not-authorized-to-enroll"></a>Ten użytkownik nie ma autoryzacji do rejestracji.

Błąd 0x801c003: "ten użytkownik nie ma autoryzacji do rejestracji. Możesz spróbować wykonać tę operację ponownie lub skontaktować się z administratorem systemu, podając kod błędu (0x801c0003).
Błąd 80180003: „Wystąpił problem. Ten użytkownik nie ma autoryzacji do rejestracji. Możesz spróbować wykonać tę operację ponownie lub skontaktować się z administratorem systemu, podając kod błędu 80180003. "

**Przyczyna:** Dowolny z następujących warunków: 

- Użytkownik zarejestrował już maksymalną dozwoloną liczbę urządzeń w usłudze Intune.    
- Urządzenie jest blokowane przez ograniczenia typu urządzenia.    
- Na komputerze jest uruchomiony system Windows 10 Home. Jednak rejestracja w usłudze Intune lub dołączenie do usługi Azure AD jest obsługiwana tylko w systemie Windows 10 Pro i nowszych wersjach.

#### <a name="resolution"></a>Rozwiązanie
Istnieje kilka możliwych rozwiązań tego problemu:

##### <a name="remove-devices-that-were-enrolled"></a>Usuń urządzenia, które zostały zarejestrowane
1. Zaloguj się do [portalu Azure](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).    
2. Przejdź do pozycji **użytkownicy**  > **Wszyscy użytkownicy**.    
3. Wybierz odpowiednie konto użytkownika, a następnie kliknij pozycję **urządzenia**.    
4. Wybierz wszystkie nieużywane lub niechciane urządzenia, a następnie kliknij przycisk **Usuń**. 

##### <a name="increase-the-device-enrollment-limit"></a>Zwiększanie limitu rejestracji urządzeń

> [!NOTE]
> Ta metoda zwiększa limit rejestracji urządzeń dla wszystkich użytkowników, a nie tylko dla danego użytkownika.

1. Zaloguj się do [portalu Azure](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).
2. Przejdź do pozycji **rejestracja urządzeń**  > **ograniczenia rejestracji**, a następnie wybierz pozycję **ograniczenia limitu urządzeń**.    
3. Zwiększ wartość **limitu urządzeń**. 

##### <a name="check-device-type-restrictions"></a>Sprawdzanie ograniczeń typu urządzenia
1. Zaloguj się do [portalu usługi Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) przy użyciu konta administratora globalnego.
2. Przejdź do pozycji **rejestracja urządzeń**  > **ograniczenia rejestracji**, a następnie wybierz **domyślne** ograniczenie w obszarze **ograniczenia typu urządzenia**.    
3. Wybierz pozycję **platformy**, a następnie wybierz pozycję **Zezwalaj** na **system Windows (MDM)** .

    > [!IMPORTANT]
    > Jeśli bieżące ustawienie jest już **dozwolone**, zmień je na **Blokuj**, Zapisz ustawienie, a następnie zmień je z powrotem, aby **pozostawić** ponownie i zapisać ustawienia. Spowoduje to zresetowanie ustawienia rejestracji.

4. Poczekaj około 15 minut, a następnie ponownie zarejestruj to urządzenie.    

##### <a name="upgrade-windows-10-home"></a>Uaktualnij system Windows 10 Home
[Uaktualnij system Windows 10 Home do systemu Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) lub nowszego. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Nie można zarejestrować tego użytkownika.

Błąd 0x801c0003: "nie można zarejestrować tego użytkownika. Możesz spróbować ponownie lub skontaktować się z administratorem systemu, podając kod błędu 801c0003 ".

**Przyczyna:** **Użytkownicy mogą dołączać urządzenia do ustawienia usługi Azure AD** ma wartość **Brak**. Uniemożliwia to nowym użytkownikom dołączanie urządzeń do usługi Azure AD. Dlatego Rejestracja w usłudze Intune kończy się niepowodzeniem.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do [Azure Portal](https://portal.azure.com/) jako administrator.    
2. Przejdź do **pozycji Azure Active Directory**  > **urządzenia** > **Ustawienia urządzenia**.    
3. Ustaw pozycję **Użytkownicy mogą dołączać urządzenia do usługi Azure AD** na wartość **Wszystko**.    
4. Ponownie zarejestruj urządzenie.   

### <a name="the-device-is-already-enrolled"></a>Urządzanie zostało już zarejestrowane.

Błąd 8018000a: "Wystąpił problem. Urządzanie zostało już zarejestrowane.  Możesz skontaktować się z administratorem systemu, podając kod błędu 8018000a ".

**Przyczyna:** Jeden z następujących warunków jest spełniony:
- Inny użytkownik zarejestrował już urządzenie w usłudze Intune lub przyłączył urządzenie do usługi Azure AD. Aby określić, czy jest to przypadek, przejdź do pozycji **ustawienia**  > **konta**  > **dostęp do**zasobów. Poszukaj komunikatu podobnego do następującego: "inny użytkownik w systemie jest już połączony z siecią służbową lub szkołą. Usuń to połączenie służbowe i spróbuj ponownie. "    
- Agent klienta Configuration Manager jest zainstalowany na komputerze.    

#### <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, należy użyć jednej z następujących metod:

##### <a name="remove-the-other-work-or-school-account"></a>Usuń inne konto służbowe
1. Wyloguj się z systemu Windows, a następnie zaloguj się przy użyciu innego konta, które zostało zarejestrowane lub dołączone do urządzenia.    
2. Przejdź do pozycji **ustawienia**  > **konta**  > **dostęp do zasobów służbowych**, a następnie usuń konto służbowe.
3. Wyloguj się z systemu Windows, a następnie zaloguj się przy użyciu swojego konta.    
4. Zarejestrowanie urządzenia w usłudze Intune lub dołączenie urządzenia do usługi Azure AD. 

##### <a name="remove-the-configuration-manager-client"></a>Usuń klienta programu Configuration Manager
Usuń klienta Configuration Manager, a następnie ponownie Zarejestruj urządzenie.



### <a name="this-account-is-not-allowed-on-this-phone"></a>To konto nie jest dozwolone na tym telefonie.

Błąd: "to konto nie jest dozwolone na tym telefonie. Upewnij się, że podane informacje są poprawne, a następnie spróbuj ponownie lub zażądaj pomocy technicznej od firmy ".

**Przyczyna:** Użytkownik, który próbował zarejestrować urządzenie, nie ma prawidłowej licencji usługi Intune.

#### <a name="resolution"></a>Rozwiązanie
Przypisz użytkownikowi prawidłową licencję usługi Intune, a następnie Zarejestruj urządzenie.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>Wygląda na to, że punkt końcowy warunków użytkowania zarządzania urządzeniami przenośnymi nie został poprawnie skonfigurowany.

**Przyczyna:** Jeden z następujących warunków jest spełniony: 
 - W dzierżawie należy używać zarówno funkcji zarządzania urządzeniami przenośnymi (MDM) dla pakietu Office 365 i usługi Intune, a użytkownik próbujący zarejestrować urządzenie nie ma prawidłowej licencji usługi Intune ani licencji pakietu Office 365.     
- Warunki i postanowienia dotyczące zarządzania urządzeniami przenośnymi w usłudze Azure AD są puste lub nie zawierają poprawnego adresu URL.    

#### <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, należy użyć jednej z następujących metod: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Przypisywanie użytkownikowi prawidłowej licencji
Przejdź do [Centrum administracyjnego Microsoft 365](https://portal.office.com/adminportal/home), a następnie przypisz do użytkownika licencję usługi Intune lub pakietu Office 365.

##### <a name="correct-the-mdm-terms-of-use-url"></a>Popraw adres URL warunków użytkowania MDM
  1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/), a następnie wybierz pozycję **Azure Active Directory**.    
  2. Wybierz pozycję **mobilność (MDM i mam)** , a następnie kliknij pozycję **Microsoft Intune**.    
  3. Wybierz pozycję **Przywróć domyślne adresy URL zarządzania urządzeniami przenośnymi**, a następnie sprawdź, czy **adres URL warunków użytkowania MDM** jest ustawiony na **https://portal.manage.microsoft.com/TermsofUse.aspx** .    
  4. Wybierz polecenie **Zapisz**.    


### <a name="something-went-wrong"></a>Wystąpił problem.

Błąd 80180026: „Wystąpił problem. Potwierdź, że używasz informacji o prawidłowym logowaniu i że Twoja organizacja korzysta z tej funkcji. Możesz spróbować wykonać tę operację ponownie lub skontaktować się z administratorem systemu, podając kod błędu 80180026. "

**Przyczyna:** Ten błąd może wystąpić podczas próby dołączenia komputera z systemem Windows 10 do usługi Azure AD i są spełnione następujące warunki: 
- Automatyczna rejestracja w usłudze MDM jest włączona na platformie Azure.    
- Na komputerze z systemem Windows 10 jest zainstalowany klient usługi Intune (Agent komputera usługi Intune) lub agent klienta Configuration Manager.

#### <a name="resolution"></a>Rozwiązanie
Aby rozwiązać ten problem, należy użyć jednej z następujących metod:

##### <a name="disable-mdm-automatic-enrollment-in-azure"></a>Wyłącz automatyczną rejestrację w usłudze MDM na platformie Azure.
1. Zaloguj się do [portalu Azure](https://portal.azure.com/).    
2. Przejdź do **Azure Active Directory**  > **Mobility (MDM i MAM)**  > **Microsoft Intune**.    
3. Ustaw **zakres użytkownika MDM** na **Brak**, a następnie kliknij przycisk **Zapisz**.    
     
##### <a name="uninstall"></a>Odinstalowanie
Odinstaluj klienta komputera lub Configuration Manager agenta klienta usługi Intune z komputera.    

### <a name="the-software-cannot-be-installed"></a>Nie można zainstalować oprogramowania.

Błąd: "nie można zainstalować oprogramowania, 0x80cf4017."

**Przyczyna:** Oprogramowanie klienckie jest nieaktualne.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Przejdź do pozycji **administracja**  > **Pobierz oprogramowanie klienckie**, a następnie kliknij pozycję **Pobierz oprogramowanie klienckie**.    
3. Zapisz pakiet instalacyjny, a następnie zainstaluj oprogramowanie klienta programu. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Ten certyfikat konta jest nieprawidłowy i może być wygasły.

Błąd: „Ten certyfikat konta jest nieprawidłowy i może być wygasły, 0x80cf4017”.

**Przyczyna:** Oprogramowanie klienckie jest nieaktualne.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Przejdź do pozycji **administracja**  > **Pobierz oprogramowanie klienckie**, a następnie kliknij pozycję **Pobierz oprogramowanie klienckie**.    
3. Zapisz pakiet instalacyjny, a następnie zainstaluj oprogramowanie klienta programu.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Twoja organizacja nie obsługuje tej wersji systemu Windows. 

Błąd: "Wystąpił problem. Twoja organizacja nie obsługuje tej wersji systemu Windows.  (0x80180014) "

**Przyczyna:** Rejestracja w usłudze MDM systemu Windows jest wyłączona w dzierżawie usługi Intune.

#### <a name="resolution"></a>Rozwiązanie
Aby rozwiązać ten problem w środowisku autonomicznym usługi Intune, wykonaj następujące kroki: 
 
1. Zaloguj się do [Azure Portal](https://portal.azure.com/) jako administrator.    
2. Wybierz pozycję **Intune** po lewej stronie, a następnie przejdź do pozycji **Rejestracja urządzenia**  > **ograniczenia rejestracji**.    
3. W obszarze **ograniczenia typu urządzenia**kliknij pozycję **platformy**, a następnie wybierz pozycję **Zezwalaj** na **system Windows (MDM)** .    
4. Kliknij polecenie **Zapisz**.    
 
Aby rozwiązać ten problem w przypadku hybrydowego zarządzania urządzeniami przenośnymi za pomocą usługi Intune i Configuration Manager, wykonaj następujące kroki: 
1. Otwórz konsolę programu Configuration Manager.    
2. Wybierz pozycję **Administracja**, a następnie wybierz pozycję **Cloud Services**.    
3. Kliknij prawym przyciskiem myszy **Microsoft Intune subskrypcję**, a następnie wybierz pozycję **Konfiguruj platformy > Windows**.    
4. Zaznacz **opcję Włącz rejestrację systemu Windows**  > **Zastosuj**  > **OK**.  


### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Wystąpił błąd instalacji podczas rejestracji zbiorczej.

**Przyczyna:** Konta użytkowników usługi Azure AD w pakiecie konta (Package_GUID) dla odpowiedniego pakietu aprowizacji nie mogą dołączać urządzeń do usługi Azure AD. Te konta usługi Azure AD są tworzone automatycznie podczas konfigurowania pakietu aprowizacji za pomocą programu Windows Configuration Designer (WCD) lub aplikacji do konfigurowania komputerów szkolnych. te konta są następnie używane do przyłączania urządzeń do usługi Azure AD.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do [Azure Portal](https://portal.azure.com/) jako administrator.    
2. Przejdź do pozycji **Azure Active Directory urządzenia > > ustawienia urządzenia**.    
3. Ustaw pozycję **Użytkownicy mogą dołączać urządzenia do usługi Azure AD** na wartość **Wszystko** lub **Wybrane**.

   W przypadku wybrania opcji **wybrane**kliknij pozycję **wybrane**, a następnie kliknij pozycję **Dodaj członków** , aby dodać wszystkich użytkowników, którzy mogą przyłączać swoje urządzenia do usługi Azure AD. Upewnij się, że dodano wszystkie konta usługi Azure AD dla pakietu aprowizacji.
 
Aby uzyskać więcej informacji o sposobie tworzenia pakietu aprowizacji dla programu Windows Configuration Designer, zobacz [Tworzenie pakietu aprowizacji dla systemu Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package).

Aby uzyskać więcej informacji na temat aplikacji do konfigurowania komputerów szkolnych, zobacz [Korzystanie z aplikacji Konfigurowanie komputerów szkolnych](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app).


### <a name="auto-mdm-enroll-failed"></a>Rejestrowanie automdm: nie powiodło się 

Podczas próby zarejestrowania urządzenia z systemem Windows 10 automatycznie przy użyciu zasady grupy można napotkać następujące problemy: 
- W Harmonogram zadań, w obszarze **Microsoft**  > **Windows**  > **EnterpriseMgmt**, ostatni wynik uruchomienia **harmonogramu utworzonego przez klienta rejestracji na potrzeby automatycznego rejestrowania w usłudze MDM w** ramach zadania usługi AAD jest następujący: **zdarzenie 76 Rejestrowanie automdm: niepowodzenie (nieznany kod błędu Win32:0x8018002b)**       
- W Podgląd zdarzeń następujące zdarzenie jest rejestrowane w obszarze **Dzienniki aplikacji i usług/Microsoft/Windows/DeviceManagement-Enterprise-Diagnostics-Provider/admin**:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Przyczyna:** Jeden z następujących warunków jest spełniony: 
- Nazwa UPN zawiera niezweryfikowaną lub nierutowaną domenę, taką jak. Local (na przykład joe@contoso.local).    
- **Zakres użytkownika MDM** ma wartość **none**. 

#### <a name="resolution"></a>Rozwiązanie
Jeśli nazwa UPN zawiera niezweryfikowaną lub nierutowaną domenę, wykonaj następujące kroki: 

1. Na serwerze, na którym jest uruchomiony program Active Directory Domain Services (AD DS), Otwórz **Active Directory Użytkownicy i komputery** , wpisując **DSA. msc** w oknie dialogowym **uruchamiania** , a następnie kliknij przycisk **OK**.    
2. Kliknij pozycję **Użytkownicy** w domenie, a następnie wykonaj następujące czynności:  
    - Jeśli istnieje tylko jeden użytkownik, którego dotyczy problem, kliknij prawym przyciskiem myszy użytkownika, a następnie kliknij polecenie **Właściwości**. Na karcie **konto** na liście rozwijanej SUFIKS nazwy UPN w obszarze **Nazwa logowania użytkownika**wybierz prawidłowy sufiks upn, taki jak contoso.com, a następnie kliknij przycisk **OK**.    
    - Jeśli istnieje wielu użytkowników, których dotyczy problem, wybierz użytkowników, w menu **Akcja** kliknij polecenie **Właściwości**. Na karcie **konto** zaznacz pole wyboru **sufiks nazwy UPN** , wybierz prawidłowy sufiks upn, taki jak contoso.com na liście rozwijanej, a następnie kliknij przycisk **OK**.
3. Zaczekaj na następną synchronizację lub Wymuś synchronizację Delta z serwera synchronizacji, uruchamiając następujące polecenia w wierszu programu PowerShell z podwyższonym poziomem uprawnień:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

Jeśli **zakres użytkownika MDM** ma wartość **Brak**, wykonaj następujące czynności: 
 
1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/), a następnie wybierz pozycję **Azure Active Directory**.
2. Wybierz pozycję **mobilność (MDM i mam)** , a następnie wybierz pozycję **Microsoft Intune**.    
3. Ustaw **zakres użytkownika MDM** na **wszystkie**. Lub ustaw **zakres użytkownika MDM** na **kilka**, a następnie wybierz grupy, które mogą automatycznie rejestrować swoje urządzenia z systemem Windows 10.    
4. Ustaw **zakres użytkownika mam** na **Brak**.


### <a name="an-error-occurred-while-creating-autopilot-profile"></a>Wystąpił błąd podczas tworzenia profilu autopilotażu.

**Przyczyna:** Określony format nazwy urządzenia nie spełnia wymagań. Na przykład użyjesz małych liter dla makra szeregowego, takiego jak% serial% zamiast% SERIAL%.

#### <a name="resolution"></a>Rozwiązanie

Upewnij się, że format nazewnictwa spełnia następujące wymagania:

- Utwórz unikatową nazwę dla każdego z urządzeń. Nazwy muszą mieć co najwyżej 15 znaków i mogą zawierać litery, (a–z, A–Z), cyfry (0–9) i łączniki (-).
- Nazwy nie mogą zawierać samych cyfr.
- Nazwy nie mogą zawierać spacji.
- Użyj makra %SERIAL%, aby dodać numer seryjny specyficzny dla sprzętu. Można też użyć wartości% RAND: < liczba cyfr >% makro, aby dodać losowy ciąg liczb, a ciąg zawiera < liczbę cyfr > cyfr. Na przykład MYPC-% RAND: 6% generuje nazwę, taką jak MYPC-123456.

### <a name="something-went-wrong-oobeidps"></a>Wystąpił problem. OOBEIDPS.

**Przyczyna:** Ten problem występuje, gdy istnieje serwer proxy, zapora lub inne urządzenie sieciowe, które blokuje dostęp do dostawcy tożsamości (dostawcy tożsamości).

#### <a name="resolution"></a>Rozwiązanie
Upewnij się, że wymagany dostęp do usług internetowych dla autopilotażu nie jest zablokowany. Aby uzyskać więcej informacji, zobacz [wymagania dotyczące sieci pilotażowej dla systemu Windows](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements-network).


### <a name="registering-your-device-for-mobile-management-failed3-0x801c03ea"></a>Rejestrowanie urządzenia na potrzeby zarządzania urządzeniami przenośnymi (Niepowodzenie: 3, 0x801C03EA).

**Przyczyna:** Urządzenie ma mikroukład modułu TPM obsługujący wersję 2,0, ale jeszcze nie został uaktualniony do wersji 2,0.

#### <a name="resolution"></a>Rozwiązanie
Uaktualnij mikroukład modułu TPM do wersji 2,0.

Jeśli problem będzie nadal występować, sprawdź, czy to samo urządzenie należy do dwóch przypisanych grup, a każda grupa ma przypisany inny profil autopilotażu. Jeśli znajduje się w dwóch grupach, należy określić, który profil autopilotażu ma być stosowany do urządzenia, a następnie usunąć przypisanie innego profilu.

Aby uzyskać więcej informacji na temat sposobu wdrażania urządzenia z systemem Windows w trybie kiosku przy użyciu programu pilotażowego, zobacz [wdrażanie kiosku przy użyciu funkcji autopilotażu systemu Windows](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/).


### <a name="securing-your-hardware-failed-0x800705b4"></a>Zabezpieczanie sprzętu (Niepowodzenie: 0x800705b4).

800705b4 błędu: 
```
Securing your hardware (Failed: 0x800705b4)
Joining your organization's network (Previous step failed)
Registering your device for mobile management (Previous step failed)
```

**Przyczyna:** Urządzenie z systemem Windows nie spełnia żadnego z następujących wymagań:

- Urządzenie musi mieć fizyczny mikroukład modułu TPM 2,0. Urządzenia z wirtualną moduły TPM (na przykład maszyny wirtualne funkcji Hyper-V) lub wiórów modułu TPM 1,2 nie współpracują z trybem samoobsługowego wdrażania.
- Na urządzeniu musi być uruchomiona jedna z następujących wersji systemu Windows:
    - Windows 10 w wersji 1703 lub nowszej.
    - W przypadku użycia hybrydowego sprzężenia usługi Azure AD w systemie Windows 10 w wersji 1809 lub nowszej.


#### <a name="resolution"></a>Rozwiązanie
Upewnij się, że urządzenie skierowane spełnia oba wymagania opisane w sekcji **Przyczyna** .

Aby uzyskać więcej informacji na temat sposobu wdrażania urządzenia z systemem Windows w trybie kiosku przy użyciu programu pilotażowego, zobacz [wdrażanie kiosku przy użyciu funkcji autopilotażu systemu Windows](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/).


### <a name="something-went-wrong-error-code-80070774"></a>Wystąpił problem. Kod błędu 80070774.

Błąd 0x80070774: Wystąpił problem. Potwierdź, że używasz informacji o prawidłowym logowaniu i że Twoja organizacja korzysta z tej funkcji. Możesz spróbować wykonać tę operację ponownie lub skontaktować się z administratorem systemu, podając kod błędu 80070774.

Ten problem zwykle występuje przed ponownym uruchomieniem urządzenia w scenariuszu autopilotażu hybrydowego usługi Azure AD, gdy urządzenie przejdzie w trakcie początkowego ekranu logowania. Oznacza to, że nie można odnaleźć kontrolera domeny lub został on pomyślnie osiągnięty ze względu na problemy z łącznością. Lub że urządzenie przeszedł do stanu, którego nie można przyłączyć do domeny.

**Przyczyna:** Najbardziej typową przyczyną jest użycie sprzężenia hybrydowego usługi Azure AD, a funkcja Przypisz użytkownika jest konfigurowana w profilu autopilotażu. Użycie funkcji Assign User powoduje wykonanie sprzężenia usługi Azure AD na urządzeniu podczas początkowego ekranu logowania, który umieszcza urządzenie w stanie, w którym nie może dołączyć do domeny lokalnej. W związku z tym funkcja Assign User powinna być używana tylko w standardowym scenariuszu usługi Azure AD Join.  Ta funkcja nie powinna być używana w scenariuszach sprzężenia hybrydowego usługi Azure AD.

#### <a name="resolution"></a>Rozwiązanie

1. Przejdź do usługi **Intune**  >  **rejestracji urządzeń**  > **rejestracji systemu Windows**  > **urządzeń**.
2. Wybierz urządzenie, na którym występuje problem > kliknij przycisk wielokropka (...) po prawej stronie.
3. Wybierz opcję **Cofnij przypisanie użytkownika** i poczekaj na zakończenie procesu.
4. Przed podjęciem ponownej próby OOBE Sprawdź, czy jest przypisany profil autopilotażu usługi Azure AD.

#### <a name="second-resolution"></a>Druga rozdzielczość
Jeśli problem będzie się powtarzać, na serwerze, który jest hostem domeny offline przyłączanie łącznika usługi Intune, sprawdź, czy zdarzenie o IDENTYFIKATORze 30312 jest rejestrowane w dzienniku ODJ. Zdarzenie 30312 jest podobne do następujących:

```
Log Name:      ODJ Connector Service
Source:        ODJ Connector Service Source
Event ID:      30132
Level:         Error
Description:
{
          "Metric":{
                   "Dimensions":{
                             "RequestId":"<RequestId>",
                             "DeviceId":"<DeviceId>",
                             "DomainName":"contoso.com",
                             "ErrorCode":"5",
                             "RetryCount":"1",
                              "ErrorDescription":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation",
                              "InstanceId":"<InstanceId>",
                              "DiagnosticCode":"0x00000800",
                              "DiagnosticText":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation [Exception Message: \"DiagnosticException: 0x00000800. Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation\"] [Exception Message: \"Failed to call NetProvisionComputerAccount machineName=<ComputerName>\"]"
                   },
                   "Name":"RequestOfflineDomainJoinBlob_Failure",
                   "Value":0
          }
}
```

Ten problem jest zwykle spowodowany przez nieprawidłowe delegowanie uprawnień do jednostki organizacyjnej, w której są tworzone urządzenia z systemem Windows. Aby uzyskać więcej informacji, zobacz [zwiększenie limitu kont komputerów w jednostce organizacyjnej](windows-autopilot-hybrid.md#increase-the-computer-account-limit-in-the-organizational-unit).

1. Otwórz narzędzie **Użytkownicy i komputery usługi Active Directory (DSA.msc)** .
2. Kliknij prawym przyciskiem myszy jednostkę organizacyjną, która będzie używana do tworzenia komputerów dołączonych do hybrydowej usługi Active Directory, a następnie wybierz pozycję **Deleguj kontrolę**.
3. W kreatorze **Delegowanie kontroli** wybierz pozycję **Dalej** > **Dodaj** > **Typy obiektów**.
4. W okienku **Typy obiektów** zaznacz pole wyboru **Komputery**, a następnie wybierz przycisk **OK**.
5. W okienku **Wybieranie: użytkownicy**, **komputery** lub **grupy** w polu **Wprowadź nazwy obiektów do wybrania** wprowadź nazwę komputera, na którym zainstalowano łącznik.
6. Wybierz pozycję **Sprawdź nazwy** , aby sprawdzić poprawność wpisu > **OK**  > **dalej**.
7. Wybierz pozycję **Utwórz zadanie niestandardowe do delegowania** > **Dalej**.
8. Zaznacz pole wyboru **Tylko następujące obiekty w tym folderze**, a następnie zaznacz pola wyboru **Obiekty komputerów**, **Utwórz wybrane obiekty w tym folderze** i **Usuń wybrane obiekty w tym folderze**.
9. Wybierz pozycję **Dalej**.
10. W obszarze **Uprawnienia** zaznacz pole wyboru **Pełna kontrola**. Ta akcja powoduje zaznaczenie wszystkich innych opcji.
11. Wybierz pozycję **dalej**  > **Zakończ**.

## <a name="next-steps"></a>Następne kroki

- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Zadaj pytanie na forum usługi Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Sprawdź Blog zespołu pomocy technicznej Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Zapoznaj się z blogiem dotyczącym pakietu Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Uzyskaj pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md)
- [Znajdowanie błędów rejestracji współzarządzania](https://docs.microsoft.com/sccm/comanage/how-to-monitor#enrollment-errors)