---
title: Wskazówki dotyczące rozwiązywania problemów z zasadami funkcji BitLocker w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Zawiera opis sposobu włączania szyfrowania funkcją BitLocker na urządzeniu przy użyciu zasad usługi Intune oraz sposobu weryfikowania, czy zasady zostały pomyślnie wdrożone na urządzeniu.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3b32268d0b04dee84a737b9a1c768bc4fab7202
ms.sourcegitcommit: 3964e6697b4d43e2c69a15e97c8d16f8c838645b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/21/2020
ms.locfileid: "77556503"
---
# <a name="troubleshoot-bitlocker-policies-in-microsoft-intune"></a>Rozwiązywanie problemów dotyczących zasad funkcji BitLocker w usłudze Microsoft Intune

Ten artykuł może pomóc administratorom usługi Intune zrozumieć, jak urządzenia z systemem Windows 10 konfigurują funkcję BitLocker na podstawie zasad usługi Intune. Ten artykuł zawiera również wskazówki dotyczące rozwiązywania problemów z ustawieniami funkcji BitLocker na urządzeniach zarządzanych za pomocą usługi Intune.  

## <a name="understanding-bitlocker"></a>Informacje o funkcji BitLocker

Szyfrowanie dysków funkcją BitLocker to usługa oferowana przez systemy operacyjne Microsoft Windows, która umożliwia użytkownikom szyfrowanie danych na ich dyskach twardych. Funkcja BitLocker obsługuje szyfrowanie dysków systemu operacyjnego, dysków wymiennych i stałych dysków danych. Funkcja BitLocker obsługuje również szyfrowanie 256-bitowe w celu zapewnienia lepszej ochrony poufnych danych.  

Usługa Microsoft Intune udostępnia następujące metody zarządzania funkcją BitLocker na urządzeniach z systemem Windows 10:

- **Zasady konfiguracji urządzenia** — niektóre wbudowane opcje zasad są dostępne w usłudze Intune podczas tworzenia profilu konfiguracji urządzenia w celu zarządzania ochroną punktu końcowego. Aby znaleźć te opcje, [utwórz profil urządzenia na potrzeby ochrony punktu końcowego](endpoint-protection-configure.md#create-a-device-profile-containing-endpoint-protection-settings), wybierając pozycję **Windows 10 i nowsze** dla ustawienia *Platforma*, a następnie wybierając kategorię **Szyfrowanie systemu Windows** w *ustawieniach*. 

   Informacje o dostępnych opcjach i funkcjach można znaleźć tutaj: [Szyfrowanie systemu Windows](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption).

- **Punkty odniesienia zabezpieczeń** - [Punkty odniesienia zabezpieczeń](security-baselines.md) to znane grupy ustawień i wartości domyślne zalecane przez odpowiedni zespół ds. zabezpieczeń, aby ułatwić zabezpieczanie urządzeń z systemem Windows. Różne źródła punktów odniesienia, takie jak *punkt odniesienia zabezpieczeń MDM* lub *punkt odniesienia usługi Microsoft Defender ATP*, umożliwiają zarządzanie tymi samymi ustawieniami, a także różnymi ustawieniami. Pozwalają również zarządzać tymi samymi ustawieniami, którymi zarządzasz przy użyciu zasad konfiguracji urządzenia. 

Oprócz usługi Intune, w przypadku sprzętu zgodnego z funkcją nowoczesnego wstrzymania i interfejsem HSTI podczas korzystania z jednej z tych funkcji szyfrowanie urządzenia przy użyciu funkcji BitLocker jest automatycznie włączane za każdym razem, gdy użytkownik dołączy urządzenie do usługi Azure AD. Usługa Azure AD udostępnia portal, w którym są również tworzone kopie zapasowe kluczy odzyskiwania, dzięki czemu użytkownicy mogą w razie potrzeby pobrać własny klucz odzyskiwania na potrzeby samoobsługi.

Możliwe jest także, że ustawienia funkcji BitLocker są zarządzane przy użyciu innych metod, takich jak zasady grupy, lub ręcznie ustawiane przez użytkownika urządzenia.

Niezależnie od tego, jak ustawienia są stosowane do urządzenia, zasady funkcji BitLocker używają [dostawcy usług kryptograficznych funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) w celu skonfigurowania szyfrowania na urządzeniu. Dostawca usług kryptograficznych funkcji BitLocker jest wbudowany w system Windows i gdy usługa Intune wdraża zasady funkcji BitLocker na przypisanym urządzeniu, dostawca usług kryptograficznych funkcji BitLocker na urządzeniu zapisuje odpowiednie wartości w rejestrze systemu Windows, aby ustawienia zasad mogły obowiązywać.

Jeśli chcesz dowiedzieć się więcej o funkcji BitLocker, zobacz następujące zasoby:

- [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Omówienie i wymagania dotyczące funkcji BitLocker — często zadawane pytania](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq)

Znasz już ogólne informacje o tym, czym są te zasady i jak działają, więc teraz zobaczysz, jak sprawdzić, czy ustawienia funkcji BitLocker zostały pomyślnie zastosowane do klienta systemu Windows.

## <a name="verify-the-source-of-bitlocker-settings"></a>Weryfikowanie źródła ustawień funkcji BitLocker

Podczas badania problemu z funkcją BitLocker na urządzeniu z systemem Windows 10 należy najpierw określić, czy problem dotyczy usługi Intune czy systemu Windows. Po poznaniu prawdopodobnego źródła problemu możesz skoncentrować działania związane z rozwiązywaniem problemów w odpowiednim miejscu i w razie potrzeby uzyskać pomoc techniczną od właściwego zespołu.  

Pierwszym krokiem jest określenie, czy zasady usługi Intune zostały pomyślnie wdrożone na urządzeniu docelowym. W poniższym przykładzie istnieją zasady konfiguracji urządzeń, które wdrażają ustawienia szyfrowania systemu Windows (BitLocker), jak pokazano poniżej:

![Zasady konfiguracji urządzeń szyfrowania systemu Windows z ustawieniami](./media/troubleshooting-bitlocker-policies/settings.png)

Jak upewnić się, że ustawienia zostały zastosowane do urządzenia docelowego? Poniżej przedstawiono kilka sposobów, jak to zrobić.

### <a name="device-configuration-policy-device-status"></a>Stan urządzenia zasad konfiguracji urządzenia  

W przypadku konfigurowania funkcji BitLocker za pomocą zasad konfiguracji urządzeń można sprawdzić stan zasad w portalu usługi Intune.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia**  >  **Profile konfiguracji**, a następnie wybierz profil, który zawiera ustawienia funkcji BitLocker.

3. Po wybraniu profilu, który chcesz wyświetlić, wybierz pozycję **Stan urządzenia**. Urządzenia przypisane do profilu znajdują się na liście, a kolumna *Stan urządzenia* wskazuje, czy pomyślnie wdrożono profil na urządzeniu.

Pamiętaj, że może być opóźnienie między urządzeniem, które odbiera zasady funkcji BitLocker, a w pełni szyfrowanym dyskiem.  

### <a name="use-control-panel-on-the-client"></a>Korzystanie z panelu sterowania na kliencie  

Na urządzeniu, na którym włączono funkcję BitLocker i zaszyfrowano dysk, można wyświetlić stan funkcji BitLocker z poziomu panelu sterowania urządzenia. Na urządzeniu otwórz pozycję **Panel sterowania**  >  **System i zabezpieczenia**  >  **Szyfrowanie dysków funkcją BitLocker**. Zostanie wyświetlone potwierdzenie, jak pokazano na poniższej ilustracji.  

![Funkcja BitLocker jest włączona w panelu sterowania](./media/troubleshooting-bitlocker-policies/control-panel.png)

### <a name="use-a-command-prompt"></a>Używanie wiersza polecenia  

Na urządzeniu, na którym włączono funkcję BitLocker i zaszyfrowano dysk, uruchom wiersz polecenia z poświadczeniami administratora, a następnie uruchom `manage-bde -status`. Rezultaty powinny przypominać następujący przykład:  
![Wynik polecenia stanu](./media/troubleshooting-bitlocker-policies/command.png)

W przykładzie:

- **Ochrona za pomocą funkcji BitLocker** jest **włączona**
- **Procent szyfrowania** to **100%**
- **Metoda szyfrowania** to **XTS-AES 256**

**Ochronę kluczy** można też sprawdzić, uruchamiając następujące polecenie:

```cmd
Manage-bde -protectors -get c:
```

Lub przy użyciu programu PowerShell:

```powershell
Confirm-SecureBootUEFI
```

### <a name="review-the-devices-registry-key-configuration"></a>Przejrzyj konfigurację klucza rejestru urządzeń

Po pomyślnym wdrożeniu zasad funkcji BitLocker na urządzeniu wyświetl następujący klucz rejestru na urządzeniu, na którym można sprawdzić konfigurację ustawień funkcji BitLocker:  *HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\current\device\BitLocker*. Przykład:

![Klucz rejestru funkcji BitLocker](./media/troubleshooting-bitlocker-policies/registry.png)

Te wartości są konfigurowane przez dostawcę usług kryptograficznych funkcji BitLocker. Sprawdź, czy wartości kluczy pasują do ustawień określonych w źródle zasad szyfrowania systemu Windows w usłudze Intune. Aby uzyskać więcej informacji na temat każdego z tych ustawień, zobacz [Dostawca usług kryptograficznych funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

> [!NOTE]
> Podgląd zdarzeń systemu Windows zawiera też różne informacje związane z funkcją BitLocker. Istnieje zbyt wiele elementów, aby wymienić je tutaj, ale możesz wyszukać **interfejs API funkcji BitLocker**, aby uzyskać wiele przydatnych informacji.

### <a name="check-the-mdm-diagnostics-report"></a>Sprawdzanie raportu diagnostycznego MDM

Na urządzeniu, na którym włączono funkcję BitLocker, można wygenerować i wyświetlić raport diagnostyczny MDM z urządzenia docelowego, aby upewnić się, że zasady funkcji BitLocker są obecne. Jeśli ustawienia zasad są widoczne w raporcie, jest to kolejna informacja o tym, że zasady zostały pomyślnie wdrożone. W klipie wideo z serii *Microsoft Helps* z poniższego linku wyjaśniono, jak przechwycić raport diagnostyczny MDM z urządzenia z systemem Windows.

> [!VIDEO https://www.youtube.com/embed/WKxlcjV4TNE]

Podczas analizowania raportu diagnostycznego MDM zawartość może wydawać się nieco niezrozumiała. Poniżej przedstawiono przykład pokazujący sposób korelowania zawartości raportu z ustawieniami w zasadach:

![Przykład raportu diagnostycznego MDM](./media/troubleshooting-bitlocker-policies/report.png)

Wynik przedstawia wartości, które odpowiadają wartościom z zasad funkcji BitLocker:

![Wynik pokazuje wartości ](./media/troubleshooting-bitlocker-policies/output.png)

Wyniki diagnostyki MDM:

```asciidoc
EncryptionMethodWithXtsOsDropDown: 7 (The value 7 refers to the 256 bit encryption)
EncryptionMethodWithXtsFdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
EncryptionMethodWithXtsRdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
```

Możesz zapoznać się z [dokumentacją dostawcy usług kryptograficznych funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp), aby zobaczyć, co oznacza każda wartość. W tym przykładzie na poniższej ilustracji przedstawiono udostępniony fragment kodu.

![Cele wartości](./media/troubleshooting-bitlocker-policies/shared-example.png)

Podobnie można zobaczyć wszystkie wartości i sprawdzić je za pomocą linku dostawcy usług kryptograficznych funkcji BitLocker.

> [!TIP]
> Głównym celem raportu diagnostycznego MDM jest ułatwienie zespołowi pomocy technicznej firmy Microsoft rozwiązywania problemów. Jeśli otworzysz zgłoszenie do pomocy technicznej dla usługi Intune, a problem dotyczy klientów systemu Windows, zawsze warto zebrać ten raport i dołączyć go do wniosku o pomoc techniczną.

## <a name="troubleshooting-bitlocker-policy"></a>Rozwiązywanie problemów z zasadami funkcji BitLocker

Wiesz już, jak upewnić się, że zasady funkcji BitLocker zostały pomyślnie wdrożone przez usługę Intune, które przekazują konfigurację funkcji BitLocker do dostawcy usług kryptograficznych funkcji BitLocker w systemie Windows.

**Nie można przekazać zasad do urządzenia** — jeśli zasady usługi Intune nie są obecne w żadnej pojemności:

- **Czy urządzenie zostało prawidłowo zarejestrowane w usłudze Microsoft Intune?** Jeśli nie, musisz rozwiązać ten problem przed rozwiązywaniem problemów specyficznych dla zasad. Pomoc dotyczącą rozwiązywania problemów z rejestracją systemu Windows można znaleźć [tutaj](../enrollment/troubleshoot-windows-enrollment-errors.md).

- **Czy na urządzeniu istnieje aktywne połączenie sieciowe?** Jeśli urządzenie jest w trybie samolotowym, jest wyłączone lub znajduje się w lokalizacji bez zasięgu usług, zasady nie zostaną dostarczone ani zastosowane, dopóki nie zostanie przywrócone połączenie sieciowe.

- **Czy zasady funkcji BitLocker zostały wdrożone u prawidłowego użytkownika lub we właściwej grupie urządzeń?** Sprawdź, czy prawidłowy użytkownik lub urządzenie należą do grup docelowych.

**Zasady są obecne, ale nie wszystkie ustawienia zostały pomyślnie skonfigurowane** — gdy zasady usługi Intune docierają do urządzenia, ale nie wszystkie konfiguracje są ustawione:

- **Czy wdrożenie wszystkich zasad kończy się niepowodzeniem, czy nie można zastosować tylko niektórych ustawień?** W przypadku scenariusza, w którym tylko niektóre ustawienia zasad nie są stosowane, sprawdź następujące kwestie:

  1. **Nie wszystkie ustawienia funkcji BitLocker są obsługiwane we wszystkich wersjach systemu Windows**.
     Zasady znajdują się na urządzeniu jako pojedyncza jednostka, dlatego jeśli niektóre ustawienia zostaną zastosowane, a inne nie, można mieć pewność, że zasady zostały odebrane. W tym scenariuszu istnieje możliwość, że wersja systemu Windows na urządzeniu nie obsługuje ustawień powodujących problemy. Aby uzyskać szczegółowe informacje na temat wymagań dotyczących wersji dla każdego ustawienia, zobacz [Dostawca usług kryptograficznych funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) w dokumentacji systemu Windows.

  2. **Funkcja BitLocker nie jest obsługiwana na wszystkich urządzeniach**.
     Nawet jeśli masz odpowiednią wersję systemu Windows, istnieje możliwość, że sprzęt nie spełnia wymagań dotyczących szyfrowania funkcją BitLocker. [Wymagania systemowe dotyczące funkcji BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements) można znaleźć w dokumentacji systemu Windows, ale główne kwestie do sprawdzenia to, czy urządzenie ma zgodny układ TPM (1.2 lub nowszy) oraz system BIOS lub oprogramowanie układowe UEFI zgodne ze standardem Trusted Computing Group (TCG).
     
**Szyfrowanie funkcją BitLocker nie jest przeprowadzane w trybie dyskretnym** — skonfigurowano zasady programu Endpoint Protection z ustawieniem „Ostrzeżenie dotyczące innego szyfrowania dysków” i nadal pojawia się kreator szyfrowania:

- **Potwierdź, że wersja systemu Windows obsługuje szyfrowanie dyskretne** Wymaga to co najmniej wersji 1803. Jeśli użytkownik nie jest administratorem na urządzeniu, wymaga ono co najmniej wersji 1809. Ponadto w wersji 1809 dodano obsługę urządzeń, które nie obsługują nowoczesnego wstrzymania

**Urządzenie szyfrowane funkcją BitLocker jest wyświetlane jako niezgodne z zasadami zgodności usługi Intune** — problem występuje, gdy szyfrowanie za pomocą funkcji BitLocker nie zostało zakończone. W zależności od takich czynników, jak rozmiar dysku, liczba plików i ustawienia funkcji BitLocker, szyfrowanie za pomocą funkcji BitLocker może zająć dużo czasu. Po zakończeniu szyfrowania urządzenie będzie wyświetlane jako zgodne. Urządzenia mogą być również tymczasowo niezgodne bezpośrednio po ostatniej instalacji aktualizacji systemu Windows.

**Urządzenia są szyfrowane przy użyciu algorytmu 128-bitowego, a w zasadach jest podana wersja 256-bitowa** — domyślnie system Windows 10 zaszyfruje dysk przy użyciu 128-bitowego szyfrowania XTS-AES. Zapoznaj się z tym przewodnikiem, aby [ustawić 256-bitowe szyfrowanie dla funkcji BitLocker podczas pracy z rozwiązaniem Autopilot](https://techcommunity.microsoft.com/t5/intune-customer-success/setting-256-bit-encryption-for-bitlocker-during-autopilot-with/ba-p/323791#).


**Przykładowe badanie**

- Zasady funkcji BitLocker są wdrażane na urządzeniu z systemem Windows 10, a ustawienie **Szyfrowanie urządzeń** powoduje wyświetlenie stanu **Błąd** w portalu.

- Jak sugeruje nazwa, to ustawienie umożliwia administratorowi wymaganie włączenia szyfrowania przy użyciu pozycji *BitLocker > Szyfrowanie urządzeń*. Korzystając z wymienionych wcześniej porad dotyczących rozwiązywania problemów, najpierw sprawdź raport diagnostyczny MDM. Raport pozwala sprawdzić, czy poprawne zasady zostały wdrożone na urządzeniu:

  ![Raport pozwala sprawdzić, czy poprawne zasady zostały wdrożone na urządzeniu](./media/troubleshooting-bitlocker-policies/mdm-report.png)

- Powodzenie można też sprawdzić w rejestrze:

  ![Wartość rejestru RequiredDeviceEncryption wynosi 1](./media/troubleshooting-bitlocker-policies/registry-confirm.png)

- Następnie sprawdź stan modułu TPM przy użyciu programu PowerShell i okazuje się, że moduł TPM nie jest dostępny na urządzeniu:

  ![Sprawdzony stan modułu TPM przy użyciu programu PowerShell](./media/troubleshooting-bitlocker-policies/tpm-command.png)

- Ponieważ funkcja BitLocker korzysta z modułu TPM, można stwierdzić, że funkcja BitLocker nie kończy działania niepowodzeniem z powodu problemu z usługą Intune lub zasad, ale dlatego, że urządzenie nie ma układu TPM lub moduł TPM jest wyłączony w systemie BIOS.

  Dodatkowa wskazówka: możesz sprawdzić to samo w podglądzie zdarzeń systemu Windows w obszarze **Dzienniki aplikacji i usług**  >  **Microsoft**  >  **Windows**  >  **Interfejs API funkcji BitLocker**. W dzienniku zdarzeń **Interfejs API funkcji BitLocker** można znaleźć zdarzenie o identyfikatorze 853, co oznacza, że moduł TPM nie jest dostępny:

  ![Identyfikator zdarzenia 853](./media/troubleshooting-bitlocker-policies/event-error.png)

  > [!NOTE]
  > Stan modułu TPM można także sprawdzić, uruchamiając **tpm.msc** na urządzeniu.

## <a name="summary"></a>Podsumowanie

W przypadku rozwiązywania problemów z zasadami funkcji BitLocker w usłudze Intune i sprawdzania, czy zasady docierają do zamierzonego urządzenia, można założyć, że problem nie jest bezpośrednio związany z usługą Intune. Problem jest prawdopodobnie związany z systemem operacyjnym Windows lub sprzętem. W takim przypadku zacznij szukać w innych obszarach, takich jak konfiguracja modułu TPM lub interfejs UEFI i bezpieczny rozruch.

## <a name="next-steps"></a>Następne kroki  

Poniżej podano więcej zasobów, które mogą pomóc podczas pracy z funkcją BitLocker:

- [Dokumentacja produktu BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Wymagania systemowe funkcji BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements)
- [BitLocker — często zadawane pytania](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)
- [Dokumentacja dostawcy usług kryptograficznych funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)
- [Ustawienia zasad szyfrowania systemu Windows w usłudze Intune](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption)
- [Niezależne od sprzętu automatyczne szyfrowanie funkcją BitLocker za pomocą usługi AAD/MDM](https://blogs.technet.microsoft.com/home_is_where_i_lay_my_head/2017/06/07/hardware-independent-automatic-bitlocker-encryption-using-aadmdm/)
- [Zasady dostawcy usług kryptograficznych na potrzeby szyfrowania funkcją BitLocker na urządzeniach z obsługą funkcji Autopilot](https://techcommunity.microsoft.com/t5/Windows-10-security/CSP-policy-for-bitLocker-encryption-on-autopilot-devices/m-p/284537)
- [Przewodnik po tworzeniu i wdrażaniu zasad funkcji BitLocker za pomocą usługi Intune](https://blogs.technet.microsoft.com/cbernier/2017/07/11/windows-10-intune-windows-bitlocker-management-yes/)
