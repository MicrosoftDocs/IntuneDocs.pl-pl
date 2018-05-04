---
title: Tworzenie zasad zgodności urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz lub skonfiguruj zasady zgodności urządzenia w usłudze Microsoft Intune dla urządzeń z systemem macOS w celu skorzystania z ochrony integralności systemu, ustaw minimalną i maksymalną wersję systemu operacyjnego, określ wymagania dotyczące hasła i zaszyfruj magazyn danych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a797c68ca43a6173a4bac70e914d3f763ce5e6d0
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Dodawanie zasad zgodności dla urządzeń z systemem macOS w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń z systemem macOS w usłudze Intune określają reguły i ustawienia, które urządzenia z systemem macOS muszą spełniać, aby zapewnić zgodność. Gdy zasady zgodności urządzeń są używane z zasadami dostępu warunkowego, można umożliwić lub zablokować dostęp do zasobów firmy. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej na temat zasad zgodności urządzeń i wymagań wstępnych, zobacz temat [Wprowadzenie do zgodności urządzeń](device-compliance-get-started.md).

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
5. W polu **Platforma** wybierz opcję **macOS**. Wybierz opcję **Konfigurowanie ustawień** i wprowadź wartości ustawień dla pól **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu**. Gdy wszystko będzie gotowe, wybierz opcję **OK** i **Utwórz**.

## <a name="device-health"></a>Kondycja urządzenia

- **Wymagaj ochrony integralności systemu**: ustaw tę opcję na wartość **Wymagaj** w celu sprawdzenia, czy urządzenia z systemem macOS mają włączone ustawienie [Ochrona integralności systemu](https://support.apple.com/HT204899).

## <a name="device-properties"></a>Właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Proste hasła**: ustaw tę opcję na wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie takich haseł, jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **Numeryczne** czy ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
- **Liczba znaków innych niż alfanumeryczne w haśle**: określ minimalną liczbę znaków specjalnych (takich jak &, #, % i !), którą musi zawierać hasło.

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (w dniach)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

    > [!IMPORTANT]
    > W przypadku zmiany wymagania dotyczącego hasła na urządzeniu z systemem macOS zmiana będzie obowiązywać dopiero od następnej zmiany hasła przez użytkownika. Jeśli na przykład ustawiono ograniczenie długości hasła do ośmiu cyfr, a na urządzeniu z systemem macOS jest obecnie stosowane hasło o długości sześciu cyfr, urządzenie pozostanie zgodne, dopóki użytkownik nie zaktualizuje swojego hasła na tym urządzeniu.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu**: wybierz opcję **Wymagaj**, aby zaszyfrować na urządzeniach magazyn danych.

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

1. Wybierz zasady, które zostały przez Ciebie skonfigurowane. Dostęp do istniejących zasad można uzyskać po wybraniu opcji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie wybierz opcję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz opcję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

> [!TIP]
> Domyślnie urządzenia sprawdzają zgodność co 8 godzin. Jednak użytkownicy mogą wymusić uruchomienie tego procesu za pomocą aplikacji Portal firmy w usłudze Intune.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)