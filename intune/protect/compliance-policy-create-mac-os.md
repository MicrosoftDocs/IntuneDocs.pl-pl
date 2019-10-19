---
title: Ustawienia zgodności dla urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem macOS w usłudze Microsoft Intune. Możesz między innymi wymagać stosowania ochrony integralności systemu firmy Apple, określać ograniczenia dotyczące haseł, wymagać zapory oraz zezwalać na użycie programu Gatekeeper.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cada774003f73f487f87ed8051115dfcaaae6a20
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502491"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem macOS umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem macOS za pomocą usługi Intune. Możesz zastosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi określić minimalną lub maksymalną wersję systemu operacyjnego lub ustawić wygasanie haseł.

Ta funkcja ma zastosowanie do:

- macOS

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **macOS**.

## <a name="device-health"></a>Kondycja urządzenia

- **Wymagaj ochrony integralności systemu**: ustaw tę opcję na wartość **Wymagaj** w celu sprawdzenia, czy urządzenia z systemem macOS mają włączone ustawienie [Ochrona integralności systemu](https://support.apple.com/HT204899) (link otwiera witrynę internetową firmy Apple). W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna) to ustawienie nie jest oceniane na potrzeby określenia zgodności.

## <a name="device-properties"></a>Właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.
- **Minimalna wersja kompilacji systemu operacyjnego**: gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić minimalny numer kompilacji dozwolony na urządzeniu.
- **Maksymalna wersja kompilacji systemu operacyjnego**: gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić maksymalny numer kompilacji dozwolony na urządzeniu.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
- **Liczba znaków innych niż alfanumeryczne w haśle**: określ minimalną liczbę znaków specjalnych (takich jak `&`, `#`, `%` i `!`), którą musi zawierać hasło.

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)** : wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

    > [!IMPORTANT]
    > W przypadku zmiany wymagania dotyczącego hasła na urządzeniu z systemem macOS zmiana będzie obowiązywać dopiero od następnej zmiany hasła przez użytkownika. Jeśli na przykład ustawiono ograniczenie długości hasła do ośmiu cyfr, a na urządzeniu z systemem macOS jest obecnie stosowane hasło o długości sześciu cyfr, urządzenie pozostanie zgodne, dopóki użytkownik nie zaktualizuje swojego hasła na tym urządzeniu.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu**: wybierz pozycję **Wymagaj**, aby szyfrować magazyn danych na urządzeniach.

### <a name="device-security"></a>Zabezpieczenia urządzeń

Zapora chroni urządzenia przed nieautoryzowanym dostępem sieciowym. Zapora umożliwia sterowanie połączeniami dla poszczególnych aplikacji. 

- **Zapora**: wybierz pozycję **Włącz**, aby ułatwić ochronę urządzeń przed nieautoryzowanym dostępem. Włączenie tej funkcji umożliwia obsługę przychodzących połączeń internetowych i używanie trybu niewidzialności. Wybranie pozycji **Nieskonfigurowane** (wartość domyślna) spowoduje wyłączenie zapory i zezwolenie na ruch sieciowy (nie będzie on blokowany).
- **Połączenia przychodzące**: wybierz opcję **Blokuj**, aby blokować wszystkie połączenia przychodzące poza połączeniami wymaganymi dla podstawowych usług internetowych, np. DHCP, Bonjour i IPSec. To ustawienie blokuje również wszystkie usługi udostępniania, w tym udostępnianie ekranu, dostęp zdalny, udostępnianie utworów muzycznych w usłudze iTunes i inne. Wybranie pozycji **Nieskonfigurowane** (wartość domyślna) spowoduje zezwolenie na połączenia przychodzące i udostępnianie usług.
- **Tryb niewidzialności**: wybierz pozycję **Włącz**, aby zapobiegać odpowiadaniu przez komputer na żądania sondowania, które mogą być wykonywane przez złośliwych użytkowników. Gdy ta opcja jest włączona, urządzenie nadal odpowiada na przychodzące żądania w przypadku autoryzowanych aplikacji. Wybranie pozycji **Nieskonfigurowane** (wartość domyślna) spowoduje wyłączenie trybu niewidzialności.

### <a name="gatekeeper"></a>Program Gatekeeper

Aby uzyskać więcej informacji, zobacz [Gatekeeper on macOS (Program Gatekeeper w systemie macOS](https://support.apple.com/HT202491) — link otwiera witrynę internetową firmy Apple).

**Zezwalaj na aplikacje pobrane z tych lokalizacji**: umożliwia instalowanie na urządzeniach obsługiwanych aplikacji z różnych lokalizacji. Dostępne opcje lokalizacji:

- **Nieskonfigurowane**: wartość domyślna. Opcja Gatekeeper nie ma wpływu na zgodność lub jej brak. 
- **Mac App Store**: zezwala na instalowanie aplikacji tylko ze sklepu Mac App Store. Nie można instalować aplikacji od innych firm ani zidentyfikowanych deweloperów. Jeśli użytkownik wybierze program Gatekeeper w celu zainstalowania aplikacji spoza sklepu Mac App Store, urządzenie zostanie uznane za niezgodne.
- **Mac App Store i zidentyfikowani deweloperzy**: zezwala na instalowanie aplikacji ze sklepu Mac App Store oraz od zidentyfikowanych deweloperów. System macOS sprawdza tożsamość deweloperów oraz przeprowadza kilka innych testów, aby zweryfikować integralność aplikacji. Jeśli użytkownik wybierze program Gatekeeper w celu zainstalowania aplikacji z innego źródła, urządzenie zostanie uznane za niezgodne.
- **Dowolne miejsce**: instalować można aplikacje z dowolnego miejsca i od dowolnego dewelopera. To najmniej bezpieczna opcja.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem iOS](compliance-policy-create-ios.md).