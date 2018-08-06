---
title: Tworzenie zasad zgodności urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz lub skonfiguruj zasady zgodności urządzenia w usłudze Microsoft Intune dla urządzeń z systemem macOS w celu skorzystania z ochrony integralności systemu, ustaw minimalną i maksymalną wersję systemu operacyjnego, określ wymagania dotyczące hasła i zaszyfruj magazyn danych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6bbb09944db602b4b5a70c89e8089b1692c45223
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321445"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Dodawanie zasad zgodności dla urządzeń z systemem macOS w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń z systemem macOS w usłudze Intune określają reguły i ustawienia, które urządzenia z systemem macOS muszą spełniać, aby zapewnić zgodność. Gdy zasady zgodności urządzeń są używane z zasadami dostępu warunkowego, można umożliwić lub zablokować dostęp do zasobów firmy. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego:

---------------------------

| Ustawienie zasad | System macOS 10.11 i nowsze |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** | Skorygowane |   
| **Szyfrowanie urządzenia** | Skorygowane (przez ustawienie kodu PIN) |
| **Profil e-mail** | Poddane kwarantannie |
|**Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |

---------------------------

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. Na przykład użytkownik jest zmuszony do ustawienia kodu PIN.

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. W polu **Platforma** wybierz opcję **macOS**. Wybierz opcję **Konfigurowanie ustawień** i wprowadź wartości ustawień dla pól **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu**. Po zakończeniu wybierz kolejno przycisk **OK** i pozycję **Utwórz**.

## <a name="device-health"></a>Kondycja urządzenia

- **Wymagaj ochrony integralności systemu**: ustaw tę opcję na wartość **Wymagaj** w celu sprawdzenia, czy urządzenia z systemem macOS mają włączone ustawienie [Ochrona integralności systemu](https://support.apple.com/HT204899).

## <a name="device-properties"></a>Właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
- **Liczba znaków innych niż alfanumeryczne w haśle**: określ minimalną liczbę znaków specjalnych (takich jak &, #, % i !), którą musi zawierać hasło.

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

    > [!IMPORTANT]
    > W przypadku zmiany wymagania dotyczącego hasła na urządzeniu z systemem macOS zmiana będzie obowiązywać dopiero od następnej zmiany hasła przez użytkownika. Jeśli na przykład ustawiono ograniczenie długości hasła do ośmiu cyfr, a na urządzeniu z systemem macOS jest obecnie stosowane hasło o długości sześciu cyfr, urządzenie pozostanie zgodne, dopóki użytkownik nie zaktualizuje swojego hasła na tym urządzeniu.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu**: wybierz pozycję **Wymagaj**, aby szyfrować magazyn danych na urządzeniach.

### <a name="device-security"></a>Zabezpieczenia urządzeń
Zapora chroni urządzenia przed nieautoryzowanym dostępem sieciowym. Zapora umożliwia sterowanie połączeniami dla poszczególnych aplikacji. 

- **Zapora**: wybierz pozycję **Włącz**, aby ułatwić ochronę urządzeń przed nieautoryzowanym dostępem. Włączenie tej funkcji umożliwia obsługę przychodzących połączeń internetowych i używanie trybu niewidzialności. Wybranie pozycji **Nieskonfigurowane** (wartość domyślna) spowoduje wyłączenie zapory i zezwolenie na ruch sieciowy (nie będzie on blokowany).
- **Połączenia przychodzące**: **blokuj** wszystkie przychodzące połączenia sieciowe poza wymaganymi dla podstawowych usług internetowych, np. DHCP, Bonjour i IPSec. To ustawienie blokuje również wszystkie usługi udostępniania, w tym udostępnianie ekranu, dostęp zdalny, udostępnianie utworów muzycznych w usłudze iTunes i inne. Wybranie pozycji **Nieskonfigurowane** (wartość domyślna) spowoduje zezwolenie na połączenia przychodzące i udostępnianie usług. 
- **Tryb niewidzialności**: **włącz** tryb niewidzialności, aby zapobiegać odpowiadaniu przez komputer na żądania sondowania, które mogą być wykonywane przez złośliwych użytkowników. Gdy ta opcja jest włączona, urządzenie nadal odpowiada na przychodzące żądania w przypadku autoryzowanych aplikacji. Wybranie pozycji **Nieskonfigurowane** (wartość domyślna) spowoduje wyłączenie trybu niewidzialności.

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

1. Wybierz skonfigurowane przez siebie zasady. Dostęp do istniejących zasad można uzyskać po wybraniu pozycji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie wybierz opcję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz opcję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

> [!TIP]
> Domyślnie urządzenia sprawdzają zgodność co 8 godzin. Jednak użytkownicy mogą wymusić uruchomienie tego procesu za pomocą aplikacji Portal firmy w usłudze Intune.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)
