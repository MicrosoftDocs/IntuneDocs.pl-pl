---
title: Wskazówki dotyczące rozwiązywania problemów z zasadami funkcji BitLocker w Microsoft Intune
titleSuffix: Microsoft Intune
description: Zawiera opis sposobu włączania szyfrowania funkcją BitLocker na urządzeniu przy użyciu zasad usługi Intune oraz sposobu weryfikowania, czy zasady zostały pomyślnie wdrożone na urządzeniu.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
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
ms.openlocfilehash: 744277b0e49a4e3ca8b0fa3bac43c666110bb8a3
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410337"
---
# <a name="troubleshoot-bitlocker-policies-in-microsoft-intune"></a>Rozwiązywanie problemów z zasadami funkcji BitLocker w Microsoft Intune

Ten artykuł może pomóc administratorom usługi Intune zrozumieć, jak urządzenia z systemem Windows 10 konfigurują funkcję BitLocker na podstawie zasad usługi Intune. Ten artykuł zawiera również wskazówki dotyczące rozwiązywania problemów z ustawieniami funkcji BitLocker na urządzeniach zarządzanych za pomocą usługi Intune.  

## <a name="understanding-bitlocker"></a>Informacje o funkcji BitLocker

Szyfrowanie dysków funkcją BitLocker to usługa oferowana przez systemy operacyjne Microsoft Windows, która umożliwia użytkownikom szyfrowanie danych na ich dyskach twardych. Funkcja BitLocker obsługuje szyfrowanie dysków systemu operacyjnego, dysków nośników wymiennych i stałych dysków danych. Funkcja BitLocker obsługuje również szyfrowanie 256-bitowe w celu zapewnienia lepszej ochrony poufnych danych.  

Za pomocą Microsoft Intune masz następujące metody zarządzania funkcją BitLocker na urządzeniach z systemem Windows 10:

- **Zasady konfiguracji urządzeń** — niektóre wbudowane opcje zasad są dostępne w usłudze Intune podczas tworzenia profilu konfiguracji urządzenia w celu zarządzania programem Endpoint Protection. Aby znaleźć te opcje, [Utwórz profil urządzenia dla programu Endpoint Protection](endpoint-protection-configure.md#create-a-device-profile-containing-endpoint-protection-settings), wybierając opcję **Windows 10 i nowsze** dla *platformy*, a następnie wybierając kategorię **szyfrowanie systemu Windows** dla *ustawień*. 

   Informacje o dostępnych opcjach i funkcjach można znaleźć tutaj: [szyfrowanie systemu Windows](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption).

- **Linie bazowe zabezpieczeń** - [linie bazowe zabezpieczeń](security-baselines.md) są znanymi grupami ustawień i wartości domyślnych, które są zalecane przez odpowiedni zespół ds. zabezpieczeń, aby pomóc w zabezpieczaniu urządzeń z systemem Windows. Różne źródła linii bazowej, takie jak *linia bazowa zabezpieczeń MDM* lub usługa *Microsoft Defender ATP* , mogą zarządzać tymi samymi ustawieniami, a także różnymi ustawieniami. Mogą również zarządzać tymi samymi ustawieniami, którymi zarządzasz przy użyciu zasad konfiguracji urządzeń. 

Oprócz usługi Intune możliwe jest, że ustawienia funkcji BitLocker są zarządzane przy użyciu innych metod, takich jak zasady grupy, lub ręcznie ustawiane przez użytkownika urządzenia.

Niezależnie od tego, jak ustawienia są stosowane do urządzenia, zasady funkcji BitLocker używają [dostawcy CSP funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) do konfigurowania szyfrowania na urządzeniu. Funkcja BitLocker CSP jest wbudowana w system Windows i gdy usługa Intune wdraża zasady funkcji BitLocker na przypisanym urządzeniu, jest to dostawca usług kryptograficznych funkcji BitLocker na urządzeniu, które zapisuje odpowiednie wartości w rejestrze systemu Windows, aby ustawienia zasad mogły obowiązywać.

Jeśli chcesz dowiedzieć się więcej o funkcji BitLocker, zobacz następujące zasoby:

- [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Omówienie i wymagania funkcji BitLocker — często zadawane pytania](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq)

Teraz, gdy masz ogólne informacje o tym, czym są te zasady i jak działają, zobacz, jak można sprawdzić, czy ustawienia funkcji BitLocker zostały pomyślnie zastosowane dla klienta systemu Windows.

## <a name="verify-the-source-of-bitlocker-settings"></a>Weryfikowanie źródła ustawień funkcji BitLocker

Podczas badania problemu z funkcją BitLocker na urządzeniu z systemem Windows 10 należy najpierw określić, czy problem dotyczy usługi Intune, czy powiązany z systemem Windows. Po poznaniu najprawdopodobniej źródła błędu możesz skoncentrować działania związane z rozwiązywaniem problemów w odpowiednim miejscu i w razie potrzeby uzyskać pomoc techniczną od właściwego zespołu.  

Pierwszym krokiem jest określenie, czy zasady usługi Intune zostały pomyślnie wdrożone na urządzeniu docelowym. W poniższym przykładzie istnieją zasady konfiguracji urządzeń, które wdrażają ustawienia szyfrowania systemu Windows (BitLocker), jak pokazano poniżej:

![Zasady konfiguracji urządzeń szyfrowania systemu Windows z ustawieniami](./media/troubleshooting-bitlocker-policies/settings.png)

Jak upewnić się, że ustawienia zostały zastosowane do urządzenia docelowego? Poniżej przedstawiono kilka sposobów, aby to zrobić.

### <a name="device-configuration-policy-device-status"></a>Stan urządzenia zasad konfiguracji urządzenia  

W przypadku konfigurowania funkcji BitLocker za pomocą zasad konfiguracji urządzeń można sprawdzić stan zasad w portalu usługi Intune.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **urządzenia** > **profile konfiguracji** , a następnie wybierz profil, który zawiera ustawienia funkcji BitLocker.

3. Po wybraniu profilu, który chcesz wyświetlić, wybierz pozycję **stan urządzenia**. Urządzenia przypisane do tego profilu są wyświetlane, a kolumna *stan urządzenia* wskazuje, czy urządzenie pomyślnie wdrożyło profil.

Pamiętaj, że istnieje opóźnienie między urządzeniem, które otrzymuje zasady funkcji BitLocker, a dysk jest w pełni szyfrowany.  

### <a name="use-control-panel-on-the-client"></a>Korzystanie z panelu sterowania na kliencie  

Na urządzeniu, na którym włączono funkcję BitLocker i zaszyfrowaną dysk, można wyświetlić stan funkcji BitLocker z poziomu panelu sterowania urządzenia. Na urządzeniu Otwórz **Panel sterowania** > **System i zabezpieczenia** > **szyfrowanie dysków funkcją BitLocker**. Potwierdzenie jest wyświetlane jak pokazano na poniższej ilustracji.  

![Funkcja BitLocker jest włączona w panelu sterowania](./media/troubleshooting-bitlocker-policies/control-panel.png)

### <a name="use-a-command-prompt"></a>Używanie wiersza polecenia  

Na urządzeniu, na którym włączono funkcję BitLocker i zaszyfrowaną dysk, Uruchom wiersz polecenia z poświadczeniami administratora, a następnie uruchom `manage-bde -status`. Rezultaty powinny przypominać następujący przykład:  
![wynik polecenia stanu](./media/troubleshooting-bitlocker-policies/command.png)

W przykładzie:

- **Ochrona za pomocą funkcji BitLocker** jest **włączona**
- **Procent szyfrowania** to **100%**
- **Metoda szyfrowania** to **XTS-AES 256**

**Ochronę kluczy** można także sprawdzić, uruchamiając następujące polecenie:

```cmd
Manage-bde -protectors -get c:
```

Lub przy użyciu programu PowerShell:

```powershell
Confirm-SecureBootUEFI
```

### <a name="review-the-devices-registry-key-configuration"></a>Przejrzyj konfigurację klucza rejestru urządzeń

Po pomyślnym wdrożeniu zasad funkcji BitLocker na urządzeniu Wyświetl następujący klucz rejestru na urządzeniu, na którym można sprawdzić konfigurację ustawień funkcji BitLocker: *HKEY_LOCAL_MACHINE \software\microsoft\policymanager\current\device\bitlocker*. Przykład:

![Klucz rejestru funkcji BitLocker](./media/troubleshooting-bitlocker-policies/registry.png)

Te wartości są konfigurowane przez dostawcę CSP funkcji BitLocker. Sprawdź, czy wartości kluczy pasują do ustawień określonych w źródle zasad szyfrowania systemu Windows w usłudze Intune. Aby uzyskać więcej informacji na temat każdego z tych ustawień, zobacz [Funkcja BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

> [!NOTE]
> Podgląd zdarzeń systemu Windows zawiera również różne informacje związane z funkcją BitLocker. Istnieje zbyt wiele elementów, ale wyszukiwanie **interfejsu API funkcji BitLocker** zapewnia wiele przydatnych informacji.

### <a name="check-the-mdm-diagnostics-report"></a>Sprawdź raport diagnostyczny MDM

Na urządzeniu, na którym włączono funkcję BitLocker, można wygenerować i wyświetlić raport diagnostyczny MDM z urządzenia docelowego, aby upewnić się, że zasady funkcji BitLocker są obecne. Jeśli ustawienia zasad są widoczne w raporcie, jest to kolejna wskazująca, że zasady zostały pomyślnie wdrożone. W celu przechwycenia raportu diagnostycznego MDM z urządzenia z systemem Windows *pomocna przez firmę Microsoft* .

> [!VIDEO https://www.youtube.com/embed/WKxlcjV4TNE]

Podczas analizowania raportu diagnostyki MDM, zawartość może wydawać się nieco trudne. Poniżej przedstawiono przykład pokazujący sposób skorelowania zawartości raportu z ustawieniami w zasadach:

![Przykład raportu diagnostyki MDM](./media/troubleshooting-bitlocker-policies/report.png)

Wynik wyniki przedstawia wartości, które odpowiadają wartościom z zasad funkcji BitLocker:

![Wyniki wyjściowe pokazują wartości ](./media/troubleshooting-bitlocker-policies/output.png)

Wyniki wyjściowe diagnostyki MDM:

```asciidoc
EncryptionMethodWithXtsOsDropDown: 7 (The value 7 refers to the 256 bit encryption)
EncryptionMethodWithXtsFdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
EncryptionMethodWithXtsRdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
```

Można odwołać się do [dokumentacji dostawcy CSP funkcji BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) , aby zobaczyć, co oznacza każda wartość. W tym przykładzie fragment kodu jest współużytkowany na poniższej ilustracji.

![Cele wartości](./media/troubleshooting-bitlocker-policies/shared-example.png)

Podobnie można zobaczyć wszystkie wartości i sprawdzić je w łączu funkcji BitLocker dostawcy CSP.

> [!TIP]
> Głównym celem raportu diagnostycznego zarządzania urządzeniami przenośnymi jest pomoc pomoc techniczna firmy Microsoft podczas rozwiązywania problemów. Jeśli otworzysz przypadek pomocy technicznej dla usługi Intune, a problem dotyczy klientów z systemem Windows, zawsze warto zebrać ten raport i dołączyć go do żądania pomocy technicznej.

## <a name="troubleshooting-bitlocker-policy"></a>Rozwiązywanie problemów z zasadami funkcji BitLocker

Teraz warto zastanowić się, jak upewnić się, że zasady funkcji BitLocker zostały pomyślnie wdrożone przez usługę Intune, które w praktyce umożliwiają konfigurację funkcji BitLocker w systemie WIndows.

**Nie można nawiązać połączenia z urządzeniem,** ponieważ zasady usługi Intune nie są dostępne w żadnej pojemności:

- **Czy urządzenie zostało prawidłowo zarejestrowane w usłudze Microsoft Intune?** Jeśli nie, musisz rozwiązać ten problem przed rozwiązywaniem problemów specyficznych dla zasad. Pomoc dotyczącą rozwiązywania problemów z rejestracją systemu Windows można znaleźć [tutaj](../enrollment/troubleshoot-windows-enrollment-errors.md).

- **Czy na urządzeniu istnieje aktywne połączenie sieciowe?** Jeśli urządzenie jest w trybie samolotowym lub wyłączone, lub jeśli użytkownik ma urządzenie w lokalizacji bez usługi, zasady nie zostaną dostarczone lub zastosowane do momentu przywrócenia łączności sieciowej.

- **Czy zasady funkcji BitLocker zostały wdrożone w prawidłowym użytkowniku lub grupie urządzeń?** Sprawdź, czy prawidłowy użytkownik lub urządzenie jest członkiem grupy docelowej.

**Zasady są obecne, ale nie wszystkie ustawienia zostały skonfigurowane pomyślnie** — gdy zasady usługi Intune docierają do urządzenia, ale nie wszystkie konfiguracje są ustawione:

- **Czy wdrożenie całej zasady nie powiedzie się lub czy tylko niektóre ustawienia nie mają zastosowania?** Jeśli znajdziesz siebie w scenariuszu, w którym tylko niektóre ustawienia zasad nie są stosowane, sprawdź następujące zagadnienia:

  1. **Nie wszystkie ustawienia funkcji BitLocker są obsługiwane we wszystkich wersjach systemu Windows**.
     Zasady znajdują się na urządzeniu jako pojedynczej jednostce, dlatego jeśli niektóre ustawienia mają zastosowanie, a inne nie, można mieć pewność, że zasady są odbierane. W tym scenariuszu istnieje możliwość, że wersja systemu Windows na urządzeniu nie obsługuje ustawień problemów. Aby uzyskać szczegółowe informacje na temat wymagań dotyczących wersji poszczególnych ustawień, zobacz [Funkcja BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) w dokumentacji systemu Windows.

  2. **Funkcja BitLocker nie jest obsługiwana przez żaden sprzęt**.
     Nawet jeśli masz odpowiednią wersję systemu Windows, istnieje możliwość, że sprzęt urządzenia nie spełnia wymagań szyfrowania funkcji BitLocker. [Wymagania systemowe dotyczące funkcji BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements) można znaleźć w dokumentacji systemu Windows, ale główne elementy do sprawdzenia polegają na tym, że urządzenie ma zgodny mikroukład modułu TPM (1,2 lub nowszy) oraz system BIOS lub oprogramowanie układowe UEFI zgodne z Trusted Computing Group (TCG).

**Przykładowe badanie**

- Zasady funkcji BitLocker są wdrażane na urządzeniu z systemem Windows 10, a ustawienie **Szyfruj urządzenia** pokazuje stan **błędu** w portalu.

- Jak sugeruje nazwa, to ustawienie umożliwia administratorowi wymaganie włączenia szyfrowania przy użyciu *funkcji BitLocker > szyfrowanie urządzenia*. Korzystając z wymienionych wcześniej porad dotyczących rozwiązywania problemów, należy najpierw sprawdzić raport diagnostyczny MDM. Raport potwierdza, że poprawne zasady zostały wdrożone na urządzeniu:

  ![Raport potwierdza, że na urządzeniu wdrożono poprawne zasady](./media/troubleshooting-bitlocker-policies/mdm-report.png)

- Zweryfikowano również sukces w rejestrze:

  ![Wartość rejestru RequiredDeviceEncryption pokazuje 1](./media/troubleshooting-bitlocker-policies/registry-confirm.png)

- Następnie sprawdź stan modułu TPM przy użyciu programu PowerShell i Znajdź, że moduł TPM nie jest dostępny na urządzeniu:

  ![Sprawdzony stan modułu TPM przy użyciu programu PowerShell](./media/troubleshooting-bitlocker-policies/tpm-command.png)

- Ponieważ funkcja BitLocker korzysta z modułu TPM, można zakończyć, że funkcja BitLocker nie powiedzie się z powodu problemu z usługą Intune lub zasad, ale zamiast tego, ponieważ samo urządzenie nie ma układu TPM lub moduł TPM jest wyłączony w systemie BIOS.

  Dodatkową wskazówką można potwierdzić w Podgląd zdarzeń systemu Windows w obszarze **Dziennik aplikacji i usług** > **Windows** > **BitLocker API**. W dzienniku zdarzeń **interfejsu API funkcji BitLocker** znajdziesz zdarzenie o identyfikatorze 853, co oznacza, że moduł TPM nie jest dostępny:

  ![Identyfikator zdarzenia 853](./media/troubleshooting-bitlocker-policies/event-error.png)

  > [!NOTE]
  > Stan modułu TPM można także sprawdzić, uruchamiając program **TPM. msc** na urządzeniu.

## <a name="summary"></a>Podsumowanie

W przypadku rozwiązywania problemów z zasadami funkcji BitLocker w usłudze Intune i sprawdzenia, czy zasady docierają do zamierzonego urządzenia, można bezpiecznie założyć, że problem nie jest bezpośrednio związany z usługą Intune. Problem jest bardziej prawdopodobnie związany z systemem operacyjnym Windows lub sprzętem. W takim przypadku Rozpocznij wyszukiwanie w innych obszarach, takich jak Konfiguracja modułu TPM lub interfejs UEFI i bezpieczny rozruch.

## <a name="next-steps"></a>Następne kroki  

Poniżej podano więcej zasobów, które mogą pomóc podczas pracy z funkcją BitLocker:

- [Dokumentacja produktu BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Wymagania systemowe funkcji BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements)
- [BitLocker — często zadawane pytania](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)
- [Dokumentacja funkcji BitLocker dostawcy CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)
- [Ustawienia zasad szyfrowania systemu Windows w usłudze Intune](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption)
- [Niezależne od sprzętu automatyczne szyfrowanie funkcji BitLocker za pomocą usługi AAD/MDM](https://blogs.technet.microsoft.com/home_is_where_i_lay_my_head/2017/06/07/hardware-independent-automatic-bitlocker-encryption-using-aadmdm/)
- [Zasady programu CSP dla szyfrowania funkcji BitLocker na urządzeniach z obsługą autopilotażu](https://techcommunity.microsoft.com/t5/Windows-10-security/CSP-policy-for-bitLocker-encryption-on-autopilot-devices/m-p/284537)
- [Przewodnik po tworzeniu i wdrażaniu zasad funkcji BitLocker za pomocą usługi Intune](https://blogs.technet.microsoft.com/cbernier/2017/07/11/windows-10-intune-windows-bitlocker-management-yes/)