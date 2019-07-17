---
title: Raport szyfrowania i klucze funkcji BitLocker w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Przejrzyj raport stanu szyfrowania urządzeń i uzyskaj dostęp do kluczy odzyskiwania funkcji BitLocker z poziomu portalu usługi Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b4c7e4b2d35eb2662ca74660e2133dcd2c89f0a1
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883374"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>Monitorowanie funkcji BitLocker i szyfrowania urządzeń  
Usługa Intune udostępnia scentralizowaną lokalizację na potrzeby określania stanu szyfrowania urządzeń z systemem Windows 10 oraz ułatwia dostęp do ważnych informacji dotyczących funkcji BitLocker z urządzeń znajdujących się w usłudze Azure Active Directory (Azure AD).  

- Funkcja [Raport szyfrowania](#encryption-report) udostępnia szczegółowe informacje dotyczące stanu szyfrowania urządzeń i ich gotowości. Szczegóły raportu mogą pomóc w zidentyfikowaniu problemów uniemożliwiających pomyślne zaszyfrowanie urządzeń, które mają być chronione.  
- Funkcja [Wyświetl szczegóły funkcji BitLocker](#bitlocker-recovery-keys) umożliwia pobranie identyfikatora klucza i kluczy odzyskiwania dla urządzeń z portalu usługi Intune.  

## <a name="encryption-report"></a>Raport szyfrowania
Funkcja Raport szyfrowania umożliwia wyświetlenie szczegółów dotyczących stanu szyfrowania urządzeń z systemem Windows 10.  

Aby znaleźć raport, zaloguj się do usługi [Intune](https://aka.ms/intuneportal) i przejdź do pozycji **Konfiguracja urządzenia**, a następnie w obszarze *Monitor* wybierz opcję **Raport szyfrowania**.  

### <a name="prerequisites"></a>Wymagania wstępne:
Aby urządzenie pojawiło się w raporcie, musi działać na nim system Windows w wersji 1607 lub nowszej.  

### <a name="report-details"></a>Szczegóły raportu
Raport zawiera **nazwy urządzeń** z systemem Windows 10 i dotyczące ich ogólne informacje, w tym następujące pozycje:  
- **Wersja systemu operacyjnego** — wersja systemu Windows.  
- **Wersja modułu TPM** — wersja mikroukładu Trusted Platform Module (TPM) w urządzeniu.  
- **Gotowość szyfrowania** — ocena gotowości urządzeń do obsługi szyfrowania za pomocą funkcji BitLocker. Urządzenia mogą być określone jako:
  - **Gotowe**: Urządzenia może zostać zaszyfrowane przy użyciu zasad rozwiązania MDM, które wymagają urządzenia z modułem TPM oraz spełnienia następujących wymagań dotyczących wersji systemu Windows 10 i jednostki SKU:
    - Wersja 1703 lub nowsza edycji Business, Enterprise lub Education
    - Wersja 1809 lub nowsza edycji Pro  
  
    Aby uzyskać więcej informacji, zobacz artykuł [Dostawca usług konfiguracji funkcji BitLocker — CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) w dokumentacji systemu Windows.  

  - **Niegotowe**: Urządzenie nie obsługuje pełnych możliwości szyfrowania, lecz obsługuje szyfrowanie w pewnym stopniu. Na przykład urządzenie może zostać zaszyfrowane ręcznie przez użytkownika lub za pomocą zasad grupy, które można skonfigurować pod kątem szyfrowania bez modułu TPM.
  - **Nie dotyczy**: Nie ma wystarczających informacji do sklasyfikowania urządzenia.  

- **Stan szyfrowania** — określa, czy dysk systemu operacyjnego jest zaszyfrowany. 


### <a name="device-encryption-status"></a>Stan szyfrowania urządzenia
Po wybraniu urządzenia usługa Intune wyświetla okienko **Stan szyfrowania urządzenia**.

Okienko zawiera następujące szczegółowe informacje:  
- **Nazwa urządzenia** — wyświetlana nazwa urządzenia.  
- **Gotowość szyfrowania** — ocena gotowości urządzenia do obsługi szyfrowania za pomocą funkcji BitLocker. Stan szyfrowania dla urządzenia może mieć wartość *Zaszyfrowane*, nawet jeśli jego gotowość szyfrowania ma wartość *Niegotowe*, ponieważ nie ma modułu TPM. (Zobacz Gotowość szyfrowania w poprzedniej sekcji, aby uzyskać więcej informacji).
- **Stan szyfrowania** — określa, czy dysk systemu operacyjnego jest zaszyfrowany. Do rozpoczęcia raportowania stanu szyfrowania urządzeń lub zmiany tego stanu w usłudze Intune może upłynąć do 24 godzin.  
- **Profile** — lista profilów *konfiguracji urządzenia*, które dotyczą danego urządzenia, obejmująca następujący typ profilu i następujące ustawienia:  
  - Typ profilu = *Endpoint Protection*  
  - Ustawienia > Szyfrowanie systemu Windows > Szyfruj urządzenia = *Wymagane*  

  Ta lista może być przydatna podczas wyszukiwania poszczególnych zasad na potrzeby przeglądu, jeśli podsumowanie stanu profilu wskazuje na istnienie problemów.  

- **Podsumowanie stanu profilu** — podsumowanie profilów dotyczących tego urządzenia. Podsumowanie reprezentuje najmniej sprzyjające warunki w ramach wszystkich stosujących się profilów. Na przykład jeśli jeden z profilów daje w wyniku błąd, podsumowanie stanu profilu będzie wyświetlać stan *Błąd*.  
- **Szczegóły stanu** — zaawansowane szczegółowe informacje dotyczące stanu szyfrowania urządzenia. 
  > [!NOTE]  
  > Usługa Intune wyświetla *szczegóły stanu* tylko dla urządzeń z systemem *Windows 10 April 2019 Update* lub nowszym.
  
  To pole zawiera informacje dotyczące każdego występującego błędu, który można wykryć. Tych informacji możesz użyć, aby dowiedzieć się, dlaczego urządzenie nie jest gotowe do szyfrowania.  

  Poniżej przedstawiono przykłady szczegółów stanu, które może raportować usługa Intune:  

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
Utwórz zasady [zgodności urządzenia](compliance-policy-create-windows.md) dla urządzeń z systemem Windows 10 w celu skonfigurowania funkcji BitLocker i szyfrowania.
