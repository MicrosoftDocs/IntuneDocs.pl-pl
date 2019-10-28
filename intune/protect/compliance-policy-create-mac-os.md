---
title: Ustawienia zgodności dla urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem macOS w usłudze Microsoft Intune. Możesz między innymi wymagać stosowania ochrony integralności systemu firmy Apple, określać ograniczenia dotyczące haseł, wymagać zapory oraz zezwalać na użycie programu Gatekeeper.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
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
ms.openlocfilehash: 518f0b825b71a9773ed66dd480b329e998f919c4
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813503"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem macOS umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem macOS za pomocą usługi Intune. Możesz zastosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi określić minimalną lub maksymalną wersję systemu operacyjnego lub ustawić wygasanie haseł.

Ta funkcja ma zastosowanie do:

- macOS

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **macOS**.

## <a name="device-health"></a>Kondycja urządzenia

- **Wymagaj ochrony integralności systemu**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** -Wymagaj, aby urządzenia MacOS miały [ochronę integralności systemu](https://support.apple.com/HT204899) (zostanie otwarta witryna sieci Web firmy Apple).  

## <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego**:  
  Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik urządzenia może zdecydować się na jego uaktualnienie. Następnie może uzyskać dostęp do zasobów organizacji.

- **Dozwolona maksymalna wersja systemu operacyjnego**:  
  Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik urządzenia zostanie poproszony o skontaktowanie się z administratorem IT. Urządzenie nie może uzyskiwać dostępu do zasobów organizacji do momentu zmiany reguły na dopuszczającą daną wersję systemu operacyjnego.

- **Minimalna wersja kompilacji systemu operacyjnego**:  
  gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić minimalny numer kompilacji dozwolony na urządzeniu.

- **Maksymalna wersja kompilacji systemu operacyjnego**:  
  gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić maksymalny numer kompilacji dozwolony na urządzeniu.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**:  
  - **Nie skonfigurowano** (*wartość domyślna*)
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń.

- **Proste hasła**:  
  - **Nie skonfigurowano** (*Domyślnie*) — użytkownicy mogą tworzyć hasła proste, podobne do **1234** lub **1111**.
  - **Blokuj** — użytkownicy nie mogą tworzyć prostych haseł, takich jak **1234** lub **1111**.

- **Minimalna długość hasła**:  
  wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.

- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).

- **Liczba znaków innych niż alfanumeryczne w haśle**:  
  wprowadź minimalną liczbę znaków specjalnych, takich jak `&`, `#`, `%`, `!` itp., którą musi zawierać hasło.

  Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**:  
  wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni)** :  
  wybierz liczbę dni, po których wygasa hasło i należy utworzyć nowe.

- **Liczba poprzednich haseł, których nie można użyć ponownie**:  
  wprowadź liczbę wcześniej używanych haseł, których nie można użyć ponownie.
> [!IMPORTANT]
> W przypadku zmiany wymagania dotyczącego hasła na urządzeniu z systemem macOS zmiana będzie obowiązywać dopiero od następnej zmiany hasła przez użytkownika. Jeśli na przykład ustawiono ograniczenie długości hasła do ośmiu cyfr, a na urządzeniu z systemem macOS jest obecnie stosowane hasło o długości sześciu cyfr, urządzenie pozostanie zgodne, dopóki użytkownik nie zaktualizuje swojego hasła na tym urządzeniu.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**:  
  - **Nie skonfigurowano** (*wartość domyślna*)
  - **Wymagaj** — wybierz pozycję *Wymagaj*, aby szyfrować magazyn danych na urządzeniach.

### <a name="device-security"></a>Zabezpieczenia urządzeń

Zapora chroni urządzenia przed nieautoryzowanym dostępem sieciowym. Zapora umożliwia sterowanie połączeniami dla poszczególnych aplikacji. 

- **Zapora**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — to ustawienie spowoduje wyłączenie zapory i zezwolenie na ruch sieciowy (nie będzie on blokowany).
  - **Włącz** — wybierz pozycję *Włącz*, aby ułatwić ochronę urządzeń przed nieautoryzowanym dostępem. Włączenie tej funkcji umożliwia obsługę przychodzących połączeń internetowych i używanie trybu niewidzialności. 

- **Połączenia przychodzące**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — spowoduje zezwolenie na połączenia przychodzące i udostępnianie usług.
  - **Blokuj** — blokowanie wszystkich połączeń przychodzących poza połączeniami wymaganymi dla podstawowych usług internetowych, np. DHCP, Bonjour i IPSec. To ustawienie blokuje również wszystkie usługi udostępniania, w tym udostępnianie ekranu, dostęp zdalny, udostępnianie utworów muzycznych w usłudze iTunes i inne.  

- **Tryb niewidzialności**:  
  - **Nieskonfigurowane** (*Domyślnie*) — to ustawienie powoduje wyłączenie trybu niewidzialności.
  - **Włącz** — włącz tryb niewidzialności, aby zapobiegać odpowiadaniu przez komputer na żądania sondowania, które mogą być wykonywane przez złośliwych użytkowników. Gdy ta opcja jest włączona, urządzenie nadal odpowiada na przychodzące żądania w przypadku autoryzowanych aplikacji.  

### <a name="gatekeeper"></a>Program Gatekeeper

Aby uzyskać więcej informacji, zobacz [Gatekeeper on macOS (Program Gatekeeper w systemie macOS](https://support.apple.com/HT202491) — link otwiera witrynę internetową firmy Apple).

**Zezwalaj na aplikacje pobrane z tych lokalizacji**: umożliwia instalowanie na urządzeniach obsługiwanych aplikacji z różnych lokalizacji. Dostępne opcje lokalizacji:

- **Nie skonfigurowano** (*wartość domyślna*) — opcja strażnika nie ma wpływu na zgodność lub brak zgodności.  
- **Mac App Store** — zezwala na instalowanie aplikacji tylko ze sklepu Mac App Store. Nie można instalować aplikacji od innych firm ani zidentyfikowanych deweloperów. Jeśli użytkownik wybierze program Gatekeeper w celu zainstalowania aplikacji spoza sklepu Mac App Store, urządzenie zostanie uznane za niezgodne.
- **Mac App Store i zidentyfikowani deweloperzy** — zezwala na instalowanie aplikacji ze sklepu Mac App Store oraz od zidentyfikowanych deweloperów. System macOS sprawdza tożsamość deweloperów oraz przeprowadza kilka innych testów, aby zweryfikować integralność aplikacji. Jeśli użytkownik wybierze program Gatekeeper w celu zainstalowania aplikacji z innego źródła, urządzenie zostanie uznane za niezgodne.
- **Dowolne miejsce** — instalować można aplikacje z dowolnego miejsca i od dowolnego dewelopera. To najmniej bezpieczna opcja.
 

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem iOS](compliance-policy-create-ios.md).