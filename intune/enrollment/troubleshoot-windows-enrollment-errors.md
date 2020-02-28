---
title: Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestie dotyczące rozwiązywania niektórych typowych problemów występujących podczas rejestrowania urządzeń z systemem Windows w usłudze Intune.
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
ms.openlocfilehash: dae8e92209a8640ab3254e073d3043d390c3791b
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514255"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune

Ten artykuł ułatwia administratorom usługi Intune zrozumienie i rozwiązywanie problemów podczas rejestrowania urządzeń z systemem Windows w usłudze Intune.

## <a name="prerequisites"></a>Wymagania wstępne
Przed rozpoczęciem rozwiązywania problemów należy zebrać pewne podstawowe informacje. Te informacje mogą pomóc w skuteczniejszym zrozumieniu problemu i skróceniu czasu jego rozwiązywania.

Zbierz następujące informacje o problemie:
- Czy do użytkownika przypisano prawidłową licencję usługi Intune? Aby użytkownicy mogli rejestrować swoje urządzenia, muszą mieć przypisaną wymaganą licencję.
- Czy na urządzeniu z systemem Windows została zainstalowana najnowsza aktualizacja? Niektóre funkcje usługi Intune współpracują tylko z najnowszą wersją systemu Windows. Istnieje wiele poprawek dla znanych problemów dostępnych za pośrednictwem witryny Windows Update. Zastosowanie wszystkich najnowszych aktualizacji często rozwiązuje problem z rejestracją urządzenia z systemem Windows. 
- Jaki jest dokładny komunikat o błędzie?
- Gdzie jest widoczny komunikat o błędzie?
- Kiedy problem zaczął występować? Czy rejestracja kiedykolwiek zadziałała? 
- Na jakiej platformie (Android, iOS/iPadOS, Windows) występuje problem?
- Ilu użytkowników dotyczy błąd? Czy problem dotyczy wszystkich użytkowników, czy tylko niektórych?
- Na ilu urządzeniach występuje problem? Czy problem dotyczy wszystkich urządzeń, czy tylko niektórych?
- Jaki urząd oprogramowania MDM jest stosowany?
- Jak odbywa się rejestracja? Czy jest stosowana strategia „Przynieś własne urządzenie” (BYOD), czy też program Apple Device Enrollment Program (DEP) z profilami rejestracji?

## <a name="error-messages"></a>Komunikaty o błędach

### <a name="this-user-is-not-authorized-to-enroll"></a>Ten użytkownik nie ma autoryzacji do przeprowadzenia rejestracji.

Błąd 0x801c003: „Ten użytkownik nie ma autoryzacji do przeprowadzenia rejestracji. Spróbuj ponownie lub skontaktuj się z administratorem systemu, podając mu kod błędu (0x801c0003)”.
Błąd 80180003: „Wystąpił problem. Ten użytkownik nie ma autoryzacji do przeprowadzenia rejestracji. Spróbuj ponownie lub skontaktuj się z administratorem systemu, podając mu kod błędu 80180003”.

**Przyczyna:** Dowolny z następujących warunków: 

- Użytkownik zarejestrował już maksymalną dozwoloną liczbę urządzeń w usłudze Intune.    
- Urządzenie jest blokowane przez ograniczenia dotyczące typów urządzeń.    
- Na komputerze działa system Windows 10 Home. Jednak rejestracja w usłudze Intune lub dołączenie do usługi Azure AD jest obsługiwane tylko w systemie Windows 10 Pro i nowszych wersjach.

#### <a name="resolution"></a>Rozwiązanie
Istnieje kilka możliwych rozwiązań tego problemu:

##### <a name="remove-devices-that-were-enrolled"></a>Usuwanie zarejestrowanych urządzeń
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).    
2. Przejdź do pozycji **Użytkownicy** > **Wszyscy użytkownicy**.    
3. Wybierz odpowiednie konto użytkownika, a następnie kliknij pozycję **Urządzenia**.    
4. Wybierz wszystkie nieużywane lub niepożądane urządzenia, a następnie kliknij pozycję **Usuń**. 

##### <a name="increase-the-device-enrollment-limit"></a>Zwiększanie limitu rejestracji urządzeń

> [!NOTE]
> Ta metoda zwiększa limit rejestracji urządzeń dla wszystkich użytkowników, a nie tylko dla użytkownika, którego dotyczy problem.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Przejdź do pozycji **Urządzenia** > **Ograniczenia rejestracji** > **Domyślne** (w obszarze **Ograniczenia limitu urządzeń**) > **Właściwości** > **Edytuj** (obok pozycji **Limit urządzeń**) > zwiększ **Limit urządzeń** (maksymalnie 15) > **Przejrzyj i zapisz**.    
 

##### <a name="check-device-type-restrictions"></a>Sprawdzanie ograniczeń typu urządzenia
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) przy użyciu konta administratora globalnego.
2. Przejdź do pozycji **Urządzenia** > **Ograniczenia rejestracji**, a następnie wybierz ograniczenie **domyślne** w obszarze **Ograniczenia typów urządzeń**.    
3. Wybierz pozycję **Platformy**, a następnie wybierz pozycję **Zezwalaj** dla pozycji **Windows (MDM)** .

    > [!IMPORTANT]
    > Jeśli bieżące ustawienie ma już wartość **Zezwalaj**, zmień ją na wartość **Blokuj**, zapisz ustawienie, a następnie zmień je z powrotem na **Zezwalaj** i ponownie zapisz ustawienie. Spowoduje to zresetowanie ustawienia rejestracji.

4. Poczekaj około 15 minut, a następnie ponownie zarejestruj urządzenie, którego dotyczy problem.    

##### <a name="upgrade-windows-10-home"></a>Uaktualnianie systemu Windows 10 Home
[Uaktualnij system Windows 10 Home do systemu Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) lub nowszej wersji. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Ten użytkownik nie może przeprowadzać rejestracji.

Błąd 0x801c0003: „Ten użytkownik nie może przeprowadzać rejestracji. Spróbuj ponownie lub skontaktuj się z administratorem systemu, podając mu kod błędu (801c0003)”.

**Przyczyna:** Ustawienie **Użytkownicy mogą dołączać urządzania do usługi Azure AD** ma wartość **Brak**. Uniemożliwia to nowym użytkownikom dołączanie urządzeń do usługi Azure AD. Dlatego rejestracja w usłudze Intune kończy się niepowodzeniem.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/) jako administrator.    
2. Przejdź do pozycji **Azure Active Directory** > **Urządzenia** > **Ustawienia urządzenia**.    
3. Ustaw pozycję **Użytkownicy mogą dołączać urządzenia do usługi Azure AD** na wartość **Wszystko**.    
4. Ponownie zarejestruj urządzenie.   

### <a name="the-device-is-already-enrolled"></a>Urządzanie zostało już zarejestrowane.

Błąd 8018000a: „Wystąpił problem. Urządzanie zostało już zarejestrowane.  Możesz skontaktować się z administratorem systemu, podając mu kod błędu 8018000a”.

**Przyczyna:** Jeden z następujących warunków został spełniony:
- Inny użytkownik zarejestrował już urządzenie w usłudze Intune lub dołączył je do usługi Azure AD. Aby określić, czy wystąpiła taka sytuacja, przejdź do pozycji **Ustawienia** > **Konta** > **Dostęp z miejsca pracy**. Poszukaj komunikatu podobnego do następującego: „Inny użytkownik w systemie jest już połączony ze szkołą lub miejscem pracy. Usuń to połączenie ze szkołą lub miejscem pracy i spróbuj ponownie”.    

#### <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, użyj jednej z następujących metod:

##### <a name="remove-the-other-work-or-school-account"></a>Usuwanie innego konta służbowego
1. Wyloguj się z systemu Windows, a następnie zaloguj się przy użyciu innego konta zastosowanego podczas rejestrowania lub dołączania urządzenia.    
2. Przejdź do pozycji **Ustawienia** > **Konta** > **Dostęp z miejsca pracy**, a następnie usuń konto służbowe.
3. Wyloguj się z systemu Windows, a następnie zaloguj się przy użyciu swojego konta.    
4. Zarejestruj urządzenie w usłudze Intune lub dołącz urządzenie do usługi Azure AD. 



### <a name="this-account-is-not-allowed-on-this-phone"></a>To konto nie jest dozwolone na tym telefonie.

Błąd: „To konto nie jest dozwolone na tym telefonie. Upewnij się, że podane informacje są poprawne, a następnie spróbuj ponownie lub poproś o pomoc dział pomocy technicznej firmy”.

**Przyczyna:** Użytkownik, który próbował zarejestrować urządzenie, nie ma prawidłowej licencji usługi Intune.

#### <a name="resolution"></a>Rozwiązanie
Przypisz do użytkownika prawidłową licencję usługi Intune, a następnie zarejestruj urządzenie.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>Wygląda na to, że punkt końcowy warunków użytkowania oprogramowania MDM nie został poprawnie skonfigurowany.

**Przyczyna:** Jeden z następujących warunków został spełniony: 
 - W dzierżawie jest używane oprogramowanie do zarządzania urządzeniami przenośnymi (MDM) dla usługi Office 365 i usługi Intune, a użytkownik, który próbuje zarejestrować urządzenie, nie ma prawidłowej licencji usługi Intune lub licencji usługi Office 365.     
- Warunki i postanowienia dotyczące oprogramowania MDM w usłudze Azure AD są puste lub nie zawierają poprawnego adresu URL.    

#### <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, zastosuj jedną z następujących metod: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Przypisywanie użytkownikowi prawidłowej licencji
Przejdź do [centrum administracyjnego platformy Microsoft 365](https://portal.office.com/adminportal/home), a następnie przypisz do użytkownika licencję usługi Intune lub usługi Office 365.

##### <a name="correct-the-mdm-terms-of-use-url"></a>Poprawienie adresu URL warunków użytkowania oprogramowania MDM
  1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/), a następnie wybierz pozycję **Azure Active Directory**.    
  2. Wybierz pozycję **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)** , a następnie kliknij pozycję **Microsoft Intune**.    
  3. Wybierz pozycję **Przywróć domyślne adresy URL oprogramowania MDM**, a następnie sprawdź, czy **adres URL warunków użytkowania oprogramowania MDM** został ustawiony na **https://portal.manage.microsoft.com/TermsofUse.aspx** .    
  4. Wybierz polecenie **Zapisz**.    


### <a name="something-went-wrong"></a>Wystąpił problem.

Błąd 80180026: „Wystąpił problem. Upewnij się, że używasz poprawnych informacji logowania oraz że Twoja organizacja korzysta z tej funkcji. Spróbuj ponownie lub skontaktuj się z administratorem systemu, podając mu kod błędu 80180026”.

**Przyczyna:** Ten błąd może wystąpić podczas próby dołączenia komputera z systemem Windows 10 do usługi Azure AD i zostaną spełnione następujące warunki: 
- Automatyczna rejestracja w usłudze MDM została włączona na platformie Azure.    
- Klient komputera usługi Intune (agent komputera usługi Intune) został zainstalowany na komputerze z systemem Windows 10.

#### <a name="resolution"></a>Rozwiązanie
Aby rozwiązać ten problem, użyj jednej z następujących metod:

##### <a name="disable-mdm-automatic-enrollment-in-azure"></a>Wyłącz automatyczną rejestrację w oprogramowaniu MDM na platformie Azure.
1. Zaloguj się do [portalu Azure](https://portal.azure.com/).    
2. Przejdź do obszaru **Azure Active Directory** > **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)**  > **Microsoft Intune**.    
3. Ustaw pozycję **Zakres użytkownika oprogramowania MDM** na wartość **Brak**, a następnie kliknij przycisk **Zapisz**.    
     
##### <a name="uninstall"></a>Odinstalowanie
Odinstaluj agenta klienta usługi Intune na komputerze.    

### <a name="the-software-cannot-be-installed"></a>Nie można zainstalować oprogramowania.

Błąd: „Nie można zainstalować oprogramowania, 0x80cf4017”.

**Przyczyna:** Oprogramowanie klienckie jest nieaktualne.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Przejdź do pozycji **Administracja** > **Pobieranie oprogramowania klienckiego**, a następnie kliknij pozycję **Pobierz oprogramowanie klienckie**.    
3. Zapisz pakiet instalacyjny, a następnie zainstaluj oprogramowanie klienckie. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Ten certyfikat konta jest nieprawidłowy i może być wygasły.

Błąd: „Ten certyfikat konta jest nieprawidłowy i może być wygasły, 0x80cf4017”.

**Przyczyna:** Oprogramowanie klienckie jest nieaktualne.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Przejdź do pozycji **Administracja** > **Pobieranie oprogramowania klienckiego**, a następnie kliknij pozycję **Pobierz oprogramowanie klienckie**.    
3. Zapisz pakiet instalacyjny, a następnie zainstaluj oprogramowanie klienckie.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Twoja organizacja nie obsługuje tej wersji systemu Windows. 

Błąd: „Wystąpił problem. Twoja organizacja nie obsługuje tej wersji systemu Windows.  (0x80180014)”

**Przyczyna:** Rejestracja w oprogramowaniu MDM systemu Windows została wyłączona w dzierżawie usługi Intune.

#### <a name="resolution"></a>Rozwiązanie
Aby rozwiązać ten problem w środowisku autonomicznym usługi Intune, wykonaj następujące kroki: 
 
1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Urządzenia** > **Ograniczenia rejestracji** > wybierz ograniczenie dotyczące typu urządzeń.    
2. Wybierz pozycję **Właściwości** > **Edytuj** (obok obszaru **Ustawienia platformy**) > **Zezwalaj** w obszarze **Windows (MDM)** .    
3. Kliknij pozycję **Przejrzyj i zapisz**.    

### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Wystąpił błąd konfiguracji podczas rejestracji zbiorczej.

**Przyczyna:** Konta użytkowników usługi Azure AD w pakiecie konta (Package_GUID) dla odpowiedniego pakietu aprowizacyjnego nie mogą dołączać urządzeń do usługi Azure AD. Te konta usługi Azure AD są tworzone automatycznie podczas konfigurowania pakietu aprowizacyjnego za pomocą programu Windows Configuration Designer (WCD) lub aplikacji Set up School PCs. Te konta są następnie używane do dołączania urządzeń do usługi Azure AD.

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/) jako administrator.    
2. Przejdź kolejno do pozycji **Azure Active Directory > Urządzenia > Ustawienia urządzenia**.    
3. Ustaw pozycję **Użytkownicy mogą dołączać urządzenia do usługi Azure AD** na wartość **Wszystko** lub **Wybrane**.

   W przypadku wybrania opcji **Wybrane**kliknij pozycję **Wybrane**, a następnie kliknij pozycję **Dodaj członków**, aby dodać wszystkich użytkowników, którzy mogą dołączać swoje urządzenia do usługi Azure AD. Upewnij się, że dodano wszystkie konta usługi Azure AD dla pakietu aprowizacyjnego.
 
Aby uzyskać więcej informacji dotyczących sposobu tworzenia pakietu aprowizacyjnego dla programu Windows Configuration Designer, zobacz temat [Create a provisioning package for Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package) (Tworzenie pakietu aprowizacyjnego dla systemu Windows 10).

Aby uzyskać więcej informacji na temat aplikacji Set up School PCs, zobacz artykuł [Use the Set up School PCs app](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app) (Korzystanie z aplikacji Set up School PCs).


### <a name="auto-mdm-enroll-failed"></a>Automatyczne rejestrowanie w oprogramowaniu MDM: niepowodzenie 

Podczas próby automatycznego zarejestrowania urządzenia z systemem Windows 10 przy użyciu zasad grupy występują następujące problemy: 
- W Harmonogramie zadań w obszarze **Microsoft** > **Windows** > **EnterpriseMgmt** wynik ostatniego uruchomienia zadania **Harmonogram utworzony przez klienta rejestracji do automatycznego rejestrowania w oprogramowaniu MDM z usługi AAD** jest następujący: **Zdarzenie 76, automatyczne rejestrowanie w oprogramowaniu MDM: niepowodzenie (nieznany kod błędu Win32: 0x8018002b)**       
- W Podglądzie zdarzeń następujące zdarzenie jest rejestrowane w obszarze **Dzienniki aplikacji i usług/Microsoft/Windows/DeviceManagement-Enterprise-Diagnostics-Provider/Admin**:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Przyczyna:** Jeden z następujących warunków został spełniony: 
- Nazwa UPN zawiera niezweryfikowaną lub niepodlegającą routingowi domenę, taką jak .local (na przykład joe@contoso.local).    
- **Zakres użytkownika oprogramowania MDM** został ustawiony na wartość **Brak**. 

#### <a name="resolution"></a>Rozwiązanie
Jeśli nazwa UPN zawiera niezweryfikowaną lub niepodlegającą routingowi domenę, wykonaj następujące kroki: 

1. Na serwerze z uruchomionymi usługami Active Directory Domain Services (AD DS) otwórz okno **Użytkownicy i komputery usługi Active Directory**, wpisując ciąg **dsc.msc** w oknie dialogowym **uruchamiania**, a następnie kliknij przycisk **OK**.    
2. Kliknij pozycję **Użytkownicy** w domenie, a następnie wykonaj następujące czynności:  
    - Jeśli istnieje tylko jeden użytkownik, którego dotyczy problem, kliknij użytkownika prawym przyciskiem myszy, a następnie kliknij polecenie **Właściwości**. Na karcie **Konto** na liście rozwijanej sufiksów nazwy UPN w obszarze **Nazwa logowania użytkownika** wybierz prawidłowy sufiks nazwy UPN, taki jak contoso.com, a następnie kliknij przycisk **OK**.    
    - Jeśli istnieje wielu użytkowników, których dotyczy problem, wybierz użytkowników i w menu **Akcja** kliknij pozycję **Właściwości**. Na karcie **Konto** zaznacz pole wyboru **Sufiks nazwy UPN**, z listy rozwijanej wybierz prawidłowy sufiks nazwy UPN, taki jak contoso.com, a następnie kliknij przycisk **OK**.
3. Poczekaj na następną synchronizację lub wymuś synchronizację różnicową z serwera synchronizacji, uruchamiając następujące polecenia w wierszu polecenia z podwyższonym poziomem uprawnień w programie PowerShell:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

Jeśli pozycja **Zakres użytkownika oprogramowania MDM** ma wartość **Brak**, wykonaj następujące kroki: 
 
1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/), a następnie wybierz pozycję **Azure Active Directory**.
2. Wybierz pozycję **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)** , a następnie wybierz pozycję **Microsoft Intune**.    
3. Ustaw **zakres użytkownika oprogramowania MDM** na wartość **Wszyscy**. Możesz również ustawić **zakres użytkownika MDM** na wartość **Niektórzy**, a następnie wybrać grupy, które mogą automatycznie rejestrować urządzenia z systemem Windows 10.    
4. Ustaw **zakres użytkownika mam** na wartość **Brak**.


### <a name="an-error-occurred-while-creating-autopilot-profile"></a>Wystąpił błąd podczas tworzenia profilu rozwiązania Autopilot.

**Przyczyna:** Określony format nazwy w szablonie nazwy urządzenia nie spełnia wymagań. Na przykład w makrze numeru seryjnego są używane małe litery: %serial% zamiast %SERIAL%.

#### <a name="resolution"></a>Rozwiązanie

Upewnij się, że format nazwy spełnia następujące wymagania:

- Utwórz unikatową nazwę dla każdego z urządzeń. Nazwy muszą mieć co najwyżej 15 znaków i mogą zawierać litery, (a–z, A–Z), cyfry (0–9) i łączniki (-).
- Nazwy nie mogą zawierać samych cyfr.
- Nazwy nie mogą zawierać spacji.
- Użyj makra %SERIAL%, aby dodać numer seryjny specyficzny dla sprzętu. Możesz też użyć makra %RAND: <liczba cyfr>%, aby dodać losowy ciąg numeryczny zawierający następującą liczbę cyfr: < liczba cyfr>. Na przykład makro MYPC-%RAND:6% generuje nazwę MYPC-123456.

### <a name="something-went-wrong-oobeidps"></a>Wystąpił problem. OOBEIDPS.

**Przyczyna:** Ten problem występuje, gdy istnieje serwer proxy, zapora lub inne urządzenie sieciowe, które blokuje dostęp do dostawcy tożsamości.

#### <a name="resolution"></a>Rozwiązanie
Upewnij się, że wymagany dostęp do usług internetowych dla rozwiązania Autopilot nie został zablokowany. Aby uzyskać więcej informacji, zobacz temat [Windows Autopilot networking requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements-network) (Wymagania dotyczące sieci w rozwiązaniu Windows Autopilot).


### <a name="registering-your-device-for-mobile-management-failed3-0x801c03ea"></a>Rejestrowanie urządzenia na potrzeby zarządzania urządzeniami przenośnymi (Niepowodzenie:3, 0x801C03EA).

**Przyczyna:** Urządzenie ma mikroukład modułu TPM obsługujący wersję 2.0, ale nie został jeszcze uaktualniony do wersji 2.0.

#### <a name="resolution"></a>Rozwiązanie
Uaktualnij mikroukład modułu TPM do wersji 2.0.

Jeśli problem będzie się powtarzać, sprawdź, czy to samo urządzenie należy do dwóch przypisanych grup, a każda grupa ma przypisany inny profil rozwiązania Autopilot. Jeśli urządzenie znajduje się w dwóch grupach, określ, który profil rozwiązania Autopilot ma być stosowany do urządzenia, a następnie usuń przypisanie innego profilu.

Aby uzyskać więcej informacji na temat sposobu wdrażania urządzenia z systemem Windows w trybie kiosku przy użyciu rozwiązania Autopilot, zobacz artykuł [Deploying a kiosk using Windows Autopilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/) (Wdrażanie kiosku przy użyciu rozwiązania Windows Autopilot).


### <a name="securing-your-hardware-failed-0x800705b4"></a>Zabezpieczanie sprzętu (niepowodzenie: 0x800705b4).

Błąd 800705b4: 
```
Securing your hardware (Failed: 0x800705b4)
Joining your organization's network (Previous step failed)
Registering your device for mobile management (Previous step failed)
```

**Przyczyna:** Docelowe urządzenie z systemem Windows nie spełnia żadnego z następujących wymagań:

- Urządzenie musi mieć fizyczny mikroukład modułu TPM 2.0. Urządzenia z wirtualnymi modułami TPM (na przykład maszyny wirtualne funkcji Hyper-V) lub mikroukłady modułu TPM 1.2 nie współpracują z trybem wdrażania samoobsługowego.
- Na urządzeniu musi działać jedna z następujących wersji systemu Windows:
    - Windows 10, kompilacja 1703 lub nowsza.
    - W przypadku korzystania z opcji dołączenia do hybrydowej usługi Azure AD: system Windows 10, kompilacja 1809 lub nowsza.


#### <a name="resolution"></a>Rozwiązanie
Upewnij się, że urządzenie docelowe spełnia oba wymagania opisane w sekcji **Przyczyna**.

Aby uzyskać więcej informacji na temat sposobu wdrażania urządzenia z systemem Windows w trybie kiosku przy użyciu rozwiązania Autopilot, zobacz artykuł [Deploying a kiosk using Windows Autopilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/) (Wdrażanie kiosku przy użyciu rozwiązania Windows Autopilot).


### <a name="something-went-wrong-error-code-80070774"></a>Wystąpił problem. Kod błędu 80070774.

Błąd 0x80070774: Wystąpił problem. Upewnij się, że używasz poprawnych informacji logowania oraz że Twoja organizacja korzysta z tej funkcji. Spróbuj ponownie lub skontaktuj się z administratorem systemu, podając mu kod błędu 80070774.

Ten problem zwykle występuje przed ponownym uruchomieniem urządzenia w scenariuszu rozwiązania Autopilot obejmującym hybrydową usługę Azure AD, gdy w urządzeniu wystąpi przekroczenie limitu czasu na początkowym ekranie logowania. Oznacza to, że nie można odnaleźć kontrolera domeny lub połączyć się z nim ze względu na problemy z łącznością. Urządzenie mogło również przejść do stanu, w którym nie można dołączyć go do domeny.

**Przyczyna:** Najbardziej typową przyczyną jest użycie opcji dołączenia do hybrydowej usługi Azure AD, gdy funkcja przypisywania użytkownika została skonfigurowana w profilu rozwiązania Autopilot. Użycie funkcji przypisywania użytkownika powoduje wykonanie dołączenia do usługi Azure AD w urządzeniu podczas korzystania z początkowego ekranu logowania, co powoduje, że urządzenie znajduje w stanie uniemożliwiającym dołączenie go do domeny lokalnej. Dlatego funkcja przypisywania użytkownika powinna być używana tylko w standardowym scenariuszu rozwiązania Autopilot dotyczącym dołączania do usługi Azure AD.  Ta funkcja nie powinna być używana w scenariuszach dołączania do hybrydowej usługi Azure AD.

#### <a name="resolution"></a>Rozwiązanie

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję > **Urządzenia** > **Windows** > **Urządzenia z systemem Windows**.
2. Wybierz urządzenie, na którym występuje problem > kliknij przycisk z wielokropkiem (...) po prawej stronie.
3. Wybierz pozycję **Anuluj przypisanie użytkownika** i poczekaj na zakończenie procesu.
4. Przed podjęciem ponownej próby pracy w środowisku OOBE sprawdź, czy przypisano profil rozwiązania Autopilot dotyczący hybrydowej usługi Azure AD.

#### <a name="second-resolution"></a>Drugie rozwiązanie
Jeśli problem będzie się powtarzać, na serwerze hostującym program Intune Connector w celu dołączania domeny offline sprawdź, czy zdarzenie o identyfikatorze 30312 zostało zarejestrowane w dzienniku usługi ODJ Connector. Zdarzenie 30312 jest podobne do następującego:

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

Ten problem jest zwykle spowodowany przez nieprawidłowe delegowanie uprawnień do jednostki organizacyjnej, w której są tworzone urządzenia rozwiązania Windows Autopilot. Aby uzyskać więcej informacji, zobacz temat [Zwiększanie limitu kont komputerów w jednostce organizacyjnej](windows-autopilot-hybrid.md#increase-the-computer-account-limit-in-the-organizational-unit).

1. Otwórz narzędzie **Użytkownicy i komputery usługi Active Directory (DSA.msc)** .
2. Kliknij prawym przyciskiem myszy jednostkę organizacyjną, która będzie używana do tworzenia komputerów dołączonych do hybrydowej usługi Active Directory, a następnie wybierz pozycję **Deleguj kontrolę**.
3. W kreatorze **Delegowanie kontroli** wybierz pozycję **Dalej** > **Dodaj** > **Typy obiektów**.
4. W okienku **Typy obiektów** zaznacz pole wyboru **Komputery**, a następnie wybierz przycisk **OK**.
5. W okienku **Wybieranie: użytkownicy**, **komputery** lub **grupy** w polu **Wprowadź nazwy obiektów do wybrania** wprowadź nazwę komputera, na którym zainstalowano łącznik.
6. Wybierz pozycję **Sprawdź nazwy** w celu zweryfikowania wpisu > **OK** > **Dalej**.
7. Wybierz pozycję **Utwórz zadanie niestandardowe do delegowania** > **Dalej**.
8. Zaznacz pole wyboru **Tylko następujące obiekty w tym folderze**, a następnie zaznacz pola wyboru **Obiekty komputerów**, **Utwórz wybrane obiekty w tym folderze** i **Usuń wybrane obiekty w tym folderze**.
9. Wybierz pozycję **Dalej**.
10. W obszarze **Uprawnienia** zaznacz pole wyboru **Pełna kontrola**. Ta akcja powoduje zaznaczenie wszystkich innych opcji.
11. Wybierz pozycję **Dalej** > **Zakończ**.

### <a name="the-enrollment-status-page-times-out-before-the-sign-in-screen"></a>Limit czasu strony ze stanem rejestracji jest przekraczany przed przejściem do ekranu logowania

**Przyczyna:** Ten problem może wystąpić, jeśli zostaną spełnione wszystkie następujące warunki:
- Używasz strony ze stanem rejestracji do śledzenia aplikacji ze sklepu Microsoft Store dla Firm.
- Masz zasady dostępu warunkowego usługi Azure AD, które używają funkcji kontroli wymagającej oznaczenia urządzenia jako zgodnego.
- Zasady mają zastosowanie do wszystkich aplikacji w chmurze i aplikacji systemu Windows.

#### <a name="resolution"></a>Rozwiązanie:
Wypróbuj jedną z następujących czynności:
- Ustaw urządzenia jako elementy docelowe zasad zgodności usługi Intune. Upewnij się, że zgodność można określić, zanim użytkownik się zaloguje.
- Użyj licencjonowania w trybie offline dla aplikacji ze sklepu. Dzięki temu klient systemu Windows nie będzie musiał sprawdzać w sklepie Microsoft Store przed określeniem zgodności urządzenia.



## <a name="next-steps"></a>Następne kroki

- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Zadaj pytanie na forum usługi Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Sprawdź blog zespołu pomocy technicznej usługi Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Sprawdź blog dotyczący pakietu Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Uzyskaj pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md)
- [Znajdowanie błędów rejestracji współzarządzania](https://docs.microsoft.com/configmgr/comanage/how-to-monitor#enrollment-errors)
