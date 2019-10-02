---
title: Raport szyfrowania dotyczący zaszyfrowanych urządzeń w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Przejrzyj raport stanu szyfrowania urządzeń z systemem iOS lub Windows i uzyskaj dostęp do kluczy odzyskiwania funkcji BitLocker i FileVault z poziomu portalu usługi Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c123de600d91f2ba44f9ae728d7f21c8adebed25
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727834"
---
# <a name="monitor-device-encryption-with-intune"></a>Monitorowanie szyfrowania urządzeń w usłudze Intune   

Raport szyfrowania w usłudze Microsoft Intune to scentralizowana lokalizacja umożliwiająca wyświetlanie szczegółowych informacji o stanie szyfrowania urządzenia i znajdowanie opcji zarządzania kluczami odzyskiwania urządzeń. Dostępne opcje klucza odzyskiwania zależą od typu urządzenia, którego szczegóły są wyświetlane.  

Aby znaleźć raport, zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Konfiguracja urządzenia**, a następnie w obszarze *Monitor* wybierz opcję **Raport szyfrowania**.  

## <a name="view-encryption-details"></a>Wyświetlanie szczegółów szyfrowania  

W raporcie szyfrowania znajdują się najważniejsze szczegóły dotyczące obsługiwanych urządzeń, którymi zarządzasz. W poniższych sekcjach zawarto opis informacji przedstawianych w raporcie w usłudze Intune.  
 
### <a name="prerequisites"></a>Wymagania wstępne:  

Raport szyfrowania obsługuje raportowanie na urządzeniach z następującymi wersjami systemu operacyjnego:  
- macOS 10.13 lub nowszy  
- Windows w wersji 1607 lub nowszej  

### <a name="report-details"></a>Szczegóły raportu  

W okienku Raport szyfrowania jest wyświetlana lista zarządzanych urządzeń z ogólnymi informacjami dotyczącymi tych urządzeń. Jeśli wybierzesz urządzenie z listy, możesz przejść do jego szczegółów i wyświetlić dodatkowe informacje w okienku [Stan szyfrowania urządzenia](#device-encryption-status).  

- **Nazwa urządzenia** — nazwa urządzenia.  
- **System operacyjny** — platforma urządzenia, na przykład Windows lub macOS.  
- **Wersja systemu operacyjnego** — wersja systemu Windows lub macOS na urządzeniu.  
- **Wersja modułu TPM** *(dotyczy tylko systemu Windows 10)* — wersja mikroukładu Trusted Platform Module (TPM) w urządzeniu z systemem Windows 10.  
- **Gotowość szyfrowania** — ocena gotowości urządzeń do obsługi odpowiedniej technologii szyfrowania, takiej jak BitLocker lub FileVault. Urządzenia są identyfikowane jako:  
  - **Gotowe**: Urządzenia może zostać zaszyfrowane przy użyciu zasad rozwiązania MDM, ale musi spełniać następujące wymagania:  
    
    **Urządzenia z systemem macOS**:  
    - MacOS w wersji 10.13 lub nowszej  
    
    **Urządzenia z systemem Windows 10**:  
    - wersja 1703 lub nowsza typu *Business*, *Enterprise*, *Education* lub wersja 1809 lub nowsza typu *Pro*  
    - Urządzenie musi mieć mikroukład TPM  
    
    Aby uzyskać więcej informacji, zobacz artykuł [Dostawca usług konfiguracji funkcji BitLocker — CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) w dokumentacji systemu Windows.  

  - **Niegotowe**: Urządzenie nie obsługuje pełnych możliwości szyfrowania, lecz obsługuje szyfrowanie w pewnym stopniu. Na przykład urządzenie z systemem Windows może zostać zaszyfrowane ręcznie przez użytkownika lub za pomocą zasad grupy, które można skonfigurować pod kątem szyfrowania bez modułu TPM.
  - **Nie dotyczy**: Nie ma wystarczających informacji do sklasyfikowania urządzenia.  

- **Stan szyfrowania** — określa, czy dysk systemu operacyjnego jest zaszyfrowany.  

- **Główna nazwa użytkownika** — podstawowy użytkownik urządzenia.  

### <a name="device-encryption-status"></a>Stan szyfrowania urządzenia  

Po wybraniu urządzenia z raportu szyfrowania usługa Intune wyświetla okienko **Stan szyfrowania urządzenia**. Okienko zawiera następujące szczegółowe informacje:  

- **Nazwa urządzenia** — wyświetlana nazwa urządzenia.  

- **Gotowość szyfrowania** — ocena gotowości urządzenia do obsługi szyfrowania za pomocą zasad rozwiązania MDM.  
  
  Przykład: Jeśli gotowość urządzenia z systemem Windows 10 ma wartość *Niegotowe*, takie urządzenie może nadal obsługiwać szyfrowanie. Aby gotowość urządzenia mogła mieć wartość *Gotowe*, urządzenie z systemem Windows 10 musi mieć mikroukład TPM. Mikroukłady TPM nie są wymagane do obsługi szyfrowania. (Aby uzyskać więcej informacji, zobacz *Gotowość szyfrowania* w poprzedniej sekcji).  

- **Stan szyfrowania** — określa, czy dysk systemu operacyjnego jest zaszyfrowany. Do wyświetlenia raportowania stanu szyfrowania urządzenia lub zmiany tego stanu w usłudze Intune może upłynąć do 24 godzin. Ten czas jest potrzebny na szyfrowanie systemu operacyjnego i raport zwrotny urządzenia do usługi Intune.  

  Aby przyspieszyć raportowanie stanu szyfrowania usługi FileVault w celu uzyskania informacji przed standardowym czasem ewidencjonowania urządzenia, poproś użytkowników o zsynchronizowanie urządzeń po zakończeniu szyfrowania.  

- **Profile** — lista profilów *konfiguracji urządzenia*, które dotyczą danego urządzenia i są skonfigurowane z następującymi wartościami:  

  - macOS:
    - Typ profilu = *Endpoint Protection*  
    - Ustawienie > FileVault > FileVault = *Włączone*

  - Windows 10:
    - Typ profilu = *Endpoint Protection*  
    - Ustawienia > Szyfrowanie systemu Windows > Szyfruj urządzenia = *Wymagane*  

  Ta lista profilów może być przydatna do identyfikowania poszczególnych zasad na potrzeby przeglądu, jeśli w obszarze *Podsumowanie stanu profilu* są sygnalizowane problemy.  

- **Podsumowanie stanu profilu** — podsumowanie profilów dotyczących tego urządzenia. Podsumowanie reprezentuje najmniej sprzyjające warunki w ramach odpowiednich profilów. Na przykład jeśli tylko jeden z odpowiednich profilów daje w wyniku błąd, w obszarze *Podsumowanie stanu profilu* będzie wyświetlany stan *Błąd*.  
  
  Aby wyświetlić więcej szczegółów stanu, przejdź do pozycji **Intune** > **Konfiguracja urządzeń** > **Profile** i wybierz profil. Opcjonalnie wybierz pozycję **Stan urządzenia**, a następnie wybierz urządzenie.  

- **Szczegóły stanu** — zaawansowane szczegółowe informacje dotyczące stanu szyfrowania urządzenia.  

  > [!IMPORTANT]  
  > W przypadku urządzeń z systemem Windows 10 usługa Intune wyświetla *szczegóły stanu* tylko dla urządzeń z systemem *Windows 10 April 2019 Update* lub nowszym.  
  
  To pole zawiera informacje dotyczące każdego występującego błędu, który można wykryć. Tych informacji możesz użyć, aby dowiedzieć się, dlaczego urządzenie nie jest gotowe do szyfrowania.  

  Poniżej przedstawiono przykłady szczegółów stanu, które może raportować usługa Intune:  
  
  **macOS**:
  - Klucz odzyskiwania nie został jeszcze pobrany i zapisany. Najprawdopodobniej urządzenie nie zostało odblokowane lub nie zostało zaewidencjonowane.  
 
    *Rozważ następujące kwestie: Ten wynik nie musi reprezentować stanu błędu, tylko stan tymczasowy, który może być spowodowany oczekiwaniem urządzenia na skonfigurowanie depozytu dla kluczy odzyskiwania, co musi zostać zrobione przed wysłaniem żądania szyfrowania do urządzenia. Ten stan może również wskazywać, że urządzenie pozostaje zablokowane lub nie zostało ostatnio zaewidencjonowane w usłudze Intune. Wreszcie, ponieważ szyfrowanie FileVault nie rozpoczyna się, dopóki urządzenie nie zostanie podłączone do zasilania (ładowanie), istnieje możliwość, że użytkownik otrzymał klucz odzyskiwania dla urządzenia, które nie jest jeszcze zaszyfrowane*.  

  - Użytkownik ma odroczone szyfrowanie lub obecnie trwa proces szyfrowania.  
 
    *Rozważ następujące kwestie: Użytkownik nie wylogował się jeszcze po odebraniu żądania szyfrowania, co jest czynnością niezbędną, aby program FileVault mógł zaszyfrować urządzenie, lub użytkownik ręcznie odszyfrował urządzenie. Usługa Intune nie może uniemożliwić użytkownikowi odszyfrowania urządzenia.*  

  - Urządzenie zostało już zaszyfrowane. Użytkownik urządzenia musi odszyfrować urządzenie, aby kontynuować.  
 
    *Rozważ następujące kwestie: Usługa Intune nie może skonfigurować programu FileVault na urządzeniu, które zostało już zaszyfrowane. Zamiast tego użytkownik musi ręcznie odszyfrować swoje urządzenie, aby można było nim zarządzać przy użyciu zasad konfiguracji urządzeń i usługi Intune*. 
 
  - W systemie MacOS Catalina i nowszym program FileVault wymaga, aby użytkownik zatwierdził swój profil zarządzania.  
 
    *Rozważ następujące kwestie: Począwszy od wersji 10.15 (Catalina) systemu MacOS, zatwierdzenie przez użytkownika ustawień rejestracji może doprowadzić do sytuacji, że użytkownik będzie musiał ręcznie zatwierdzić szyfrowanie FileVault. Aby uzyskać więcej informacji, zobacz [Rejestracja zatwierdzona przez użytkownika](../enrollment/macos-enroll.md) w dokumentacji usługi Intune*.  

  - Nieznane.  

    *Rozważ następujące kwestie: Jedną z możliwych przyczyn nieznanego stanu jest to, że urządzenie zostało zablokowane, a usługa Intune nie może uruchomić procesu depozytu lub szyfrowania. Po odblokowaniu urządzenia proces będzie kontynuowany*.  

  **Windows 10**:  
  - Zasady funkcji BitLocker wymagają zgody użytkownika na uruchomienie Kreatora szyfrowania dysków funkcją BitLocker w celu rozpoczęcia szyfrowania woluminu systemu operacyjnego, lecz użytkownik nie wyraził zgody.  
  
  - Metoda szyfrowania woluminu systemu operacyjnego nie jest zgodna z zasadami funkcji BitLocker.  
  
  - Zasady funkcji BitLocker wymagają ochrony woluminu systemu operacyjnego za pomocą modułu TPM, lecz moduł TPM nie jest używany.  
  
  - Zasady funkcji BitLocker wymagają ochrony woluminu systemu operacyjnego wyłącznie za pomocą modułu TPM, lecz ochrona za pomocą modułu TPM nie jest używana.  
  
  - Zasady funkcji BitLocker wymagają ochrony woluminu systemu operacyjnego za pomocą modułu TPM i numeru PIN, lecz ochrona za pomocą modułu TPM i numeru PIN nie jest używana.  
  
  - Zasady funkcji BitLocker wymagają ochrony woluminu systemu operacyjnego za pomocą modułu TPM i klucza uruchomienia, lecz ochrona za pomocą modułu TPM i klucza uruchomienia nie jest używana.  
  
  - Zasady funkcji BitLocker wymagają ochrony woluminu systemu operacyjnego za pomocą modułu TPM, numeru PIN i klucza uruchomienia, lecz ochrona za pomocą modułu TPM, numeru PIN i klucza uruchomienia nie jest używana.  
  
  - Wolumin systemu operacyjnego nie jest chroniony.  
  
  - Utworzenie kopii zapasowej klucza odzyskiwania nie powiodło się.  
  
  - Dysk stały nie jest chroniony.  
  
  - Metoda szyfrowania dysku stałego nie jest zgodna z zasadami funkcji BitLocker.  
  
  - Zasady funkcji BitLocker dotyczące szyfrowania dysków wymagają, aby użytkownik był zalogowany jako Administrator, lub, jeśli urządzenie jest dołączone do usługi Azure AD, zasady AllowStandardUserEncryption muszą mieć wartość 1.  
  
  - Środowisko odzyskiwania systemu Windows (WinRE) nie jest skonfigurowane.  
  
  - Moduł TPM nie jest dostępny dla funkcji BitLocker, ponieważ nie ma go, dostęp do niego został zablokowany w rejestrze lub system operacyjny znajduje się na dysku wymiennym.  
  
  - Moduł TPM nie jest gotowy do użycia przez funkcję BitLocker.  
  
  - Sieć jest niedostępna, a jest to wymagane do utworzenia kopii zapasowej klucza odzyskiwania.  

## <a name="export-report-details"></a>Eksportowanie szczegółów raportu 
Podczas przeglądania okienka Raport szyfrowania możesz wybrać pozycję **Eksportuj**, aby utworzyć możliwy do pobrania plik *CSV* ze szczegółami raportu.  Ten raport zawiera szczegółowe informacje z okienek *Raport szyfrowania* i *Stan szyfrowania urządzenia* dla każdego urządzenia, którym zarządzasz.   
 
  
![Eksportowanie szczegółów](./media/encryption-monitor/export.png) 
 
Ten raport może służyć do identyfikowania problemów dotyczących grup urządzeń. Na przykład ten raport może być pomocny przy identyfikowaniu listy urządzeń z systemem macOS, które zgłaszają problem, że *program FileVault został już włączony przez użytkownika*. Pozwala to znaleźć urządzenia, które muszą zostać ręcznie odszyfrowane, zanim usługa Intune będzie mogła zarządzać ustawieniami programu FileVault.  
 
## <a name="filevault-recovery-keys"></a>Klucze odzyskiwania programu FileVault   
Gdy usługa Intune po raz pierwszy szyfruje urządzenie z systemem macOS za pomocą programu FileVault, jest tworzony osobisty klucz odzyskiwania. Po zaszyfrowaniu ten klucz prywatny jest wyświetlany jednorazowo na urządzeniu dla użytkownika końcowego.  
 
W przypadku urządzeń zarządzanych usługa Intune może umieścić kopię tego osobistego klucza odzyskiwania w depozycie. Dzięki deponowaniu kluczy administratorzy usługi Intune mogą obracać klucze w celu zapewnienia ochrony urządzeń, a użytkownicy mogą odzyskiwać utracone lub obrócone osobiste klucze odzyskiwania.  
 
Usługa Intune obsługuje wiele opcji obracania i przywracania osobistych kluczy odzyskiwania. Jednym z powodów, dla których należy obrócić klucz, jest utrata lub narażenie na ryzyko bieżącego klucza osobistego.  
 
> [!IMPORTANT]  
>  Urządzenia, które są szyfrowane przez użytkowników, a nie przez usługę Intune, nie mogą być zarządzane przez tę usługę. Oznacza to, że usługa Intune nie może deponować osobistych kluczy odzyskiwania dla tych urządzeń ani zarządzać obracaniem kluczy odzyskiwania.  Aby usługa Intune mogła zarządzać programem FileVault i kluczami odzyskiwania dla urządzenia, użytkownik musi najpierw odszyfrować swoje urządzenie, a następnie zezwolić usłudze Intune na jego zaszyfrowanie.  

### <a name="rotate-recovery-keys"></a>Obracanie kluczy odzyskiwania  

- **Obracanie automatyczne**: Jako administrator możesz skonfigurować ustawienie „Wymiana osobistego klucza odzyskiwania” programu FileVault w taki sposób, aby co pewien czas automatycznie były generowane nowe klucze odzyskiwania.  Nowo wygenerowany klucz dla urządzenia nie jest prezentowany użytkownikowi. Zamiast tego użytkownik musi go uzyskać od administratora lub przy użyciu aplikacji Portal firmy.  

- **Obracanie ręczne**: Jako administrator możesz wyświetlać informacje o urządzeniu zarządzanym za pomocą usługi Intune i zaszyfrowanym przy użyciu programu FileVault. Jeśli chcesz, możesz zdecydować się na ręczne obracanie klucza odzyskiwania dla urządzeń firmowych. Nie możesz obracać kluczy odzyskiwania dla urządzeń osobistych.  

  Aby obrócić klucz odzyskiwania: 
  1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), przejdź do pozycji  **Urządzenia** , a następnie w obszarze Zarządzaj wybierz opcję  **Wszystkie urządzenia**.  
  2. Z listy urządzeń wybierz zaszyfrowane urządzenie, dla którego chcesz obrócić klucz. Następnie w obszarze Monitorowanie wybierz pozycję  **Klucze odzyskiwania**.  
  3. W okienku Klucze odzyskiwania wybierz pozycję **Obróć klucz odzyskiwania funkcji FileVault**.  
  
     Przy następnym zaewidencjonowaniu urządzenia w usłudze Intune klucz osobisty zostanie obrócony. W razie konieczności użytkownik końcowy może uzyskać nowy klucz za pomocą portalu firmy. 


### <a name="recover-recovery-keys"></a>Odzyskiwanie kluczy odzyskiwania  
- **Administrator**: Administratorzy nie mogą wyświetlać osobistych kluczy odzyskiwania dla urządzeń zaszyfrowanych za pomocą programu FileVault.  

- **Użytkownik końcowy**: Użytkownicy końcowi mogą wyświetlać bieżący osobisty klucz odzyskiwania dla każdego z zarządzanych przez siebie urządzeń w witrynie internetowej Portal firmy na dowolnym urządzeniu. Nie można wyświetlić kluczy odzyskiwania w aplikacji Portal firmy.  

 
  Aby wyświetlić klucz odzyskiwania:  
  1. Zaloguj się do witryny internetowej *Intune — Portal firmy* z dowolnego urządzenia.  
  2. W portalu przejdź do pozycji **Urządzenia** i wybierz urządzenie z systemem macOS zaszyfrowane za pomocą programu FileVault.  
  3. Wybierz pozycję **Pobierz klucz odzyskiwania**. Zostanie wyświetlony bieżący klucz odzyskiwania.  
 

## <a name="bitlocker-recovery-keys"></a>Klucze odzyskiwania funkcji BitLocker  

Usługa Intune udostępnia blok usługi Azure AD dla funkcji BitLocker, dzięki czemu można wyświetlić identyfikatory klucza i klucze odzyskiwania funkcji BitLocker dla urządzeń z systemem Windows 10 z poziomu portalu usługi Intune.  Aby urządzenie było dostępne, jego klucze muszą znajdować się w depozycie usługi Azure AD. 
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), przejdź do pozycji **Urządzenia**, a następnie w obszarze *Zarządzaj* wybierz opcję **Wszystkie urządzenia**.  

2. Wybierz urządzenie z listy, a następnie w obszarze *Monitor* wybierz opcję **Klucze odzyskiwania**.  
  
Jeśli klucze są dostępne w usłudze Azure AD, są wyświetlane następujące informacje:
- Identyfikator klucza funkcji BitLocker  
- Klucz odzyskiwania funkcji BitLocker  
- Typ napędu  

Jeśli klucze nie są dostępne w usłudze Azure AD, usługa Intune wyświetli komunikat *Nie znaleziono klucza funkcji BitLocker dla tego urządzenia*.  

Informacje dotyczące funkcji BitLocker można uzyskać przy użyciu [dostawcy usług konfiguracji funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). Dostawca usług kryptograficznych funkcji BitLocker jest obsługiwany w systemie Windows 10 w wersji 1703 i nowszych oraz Windows 10 Pro w wersji 1809 i nowszych.  

## <a name="next-steps"></a>Następne kroki  

Utwórz zasady [zgodności urządzenia](compliance-policy-create-windows.md).
