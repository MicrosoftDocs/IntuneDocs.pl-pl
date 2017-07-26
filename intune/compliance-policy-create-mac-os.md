---
title: "Jak tworzyć zasady zgodności dla systemu macOS"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak tworzyć zasady zgodności dla urządzeń z systemem macOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0444183e-f924-4605-96a8-48fdfbc58fd1
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e442a0ee7953fe5474d39e1a29a88dfcca58800d
ms.sourcegitcommit: abd8f9f62751e098f3f16b5b7de7eb006b7510e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2017
---
# <a name="create-a-device-compliance-policy-for-macos-devices-preview-with-intune"></a>Tworzenie zasad zgodności dla urządzeń z systemem macOS (wersja zapoznawcza) za pomocą usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Przed rozpoczęciem

Przed utworzeniem i przypisaniem zasad zgodności urządzeń przejrzyj koncepcje dotyczące zasad zgodności urządzeń usługi Intune.

- Aby dowiedzieć się więcej na temat zasad zgodności urządzeń, zobacz [wprowadzenie do zasad zgodności urządzeń](device-compliance.md).

> [!IMPORTANT]
> Zasady zgodności urządzeń należy utworzyć osobno dla każdej platformy. Ustawienia zasad zgodności urządzeń usługi Intune zależą od możliwości platformy, czyli ustawień dostępnych za pośrednictwem protokołu MDM.

W tabeli poniżej opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

-------------------------------


| **Ustawienie zasad** | **System macOS 10.11 i nowsze** |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** | Skorygowane |   
| **Szyfrowanie urządzenia** | Skorygowane (przez ustawienie kodu PIN) |
| **Profil e-mail** | Poddane kwarantannie |
|**Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |  
| **Zaświadczanie o kondycji systemu Windows** | Nie dotyczy |  
----------------------------


**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenia nie są zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="macos-compliance-policy-settings"></a>Ustawienia zasad zachowania zgodności systemu macOS

Podczas tworzenia nowych zasad zgodności urządzeń za pomocą usługi Intune można dokonywać wyboru z różnych kategorii z różnymi ustawieniami:

- Kondycja urządzenia

- Właściwości urządzenia

- Zabezpieczenia systemu

### <a name="device-health"></a>Kondycja urządzenia

- **Wymagaj ochrony integralności systemu**: ustaw tę opcję na wartość **Wymagaj** w celu sprawdzenia, czy urządzenia z systemem macOS mają włączoną ochronę integralności systemu.

### <a name="device-properties"></a>Właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może wybrać opcję uaktualnienia urządzenia, co umożliwi korzystanie z zasobów firmy.

- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

### <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

#### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: ustaw tę opcję na wartość **Wymagaj**, aby wymagać od użytkowników wprowadzenia hasła przed uzyskaniem dostępu do swojego urządzenia.

- **Proste hasła**: ustaw tę opcję na wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**.

- **Minimalna długość hasła**: określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło.

- **Typ hasła**: określ, czy użytkownik musi utworzyć hasło **alfanumeryczne**, czy **numeryczne**.

- **Liczba znaków niealfanumerycznych w haśle**: jeśli opcja **Wymagany typ hasła** zostanie ustawiony na wartość **Alfanumeryczne**, użyj tego ustawienia do określenia minimalnej liczby zestawów znaków, które muszą zostać użyte w haśle. 

    > [!NOTE]
    > Ustawienie większej liczby spowoduje wymaganie wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

    > [!IMPORTANT]
    > W przypadku urządzeń z systemem macOS to ustawienie oznacza liczbę znaków specjalnych (na przykład **!** , **#**, **&amp;**), które muszą znajdować się w haśle.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.

- **Wygaśnięcie hasła (w dniach)**: wybierz liczbę dni (z zakresu od 1 do 250), po których hasło wygasa i należy utworzyć nowe.

- **Liczba poprzednich haseł, których nie można użyć ponownie** — określ liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

## <a name="to-create-a-device-compliance-policy"></a>Aby utworzyć zasadę zgodności urządzenia

1. Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2. Po pomyślnym zalogowaniu się zostanie wyświetlony **pulpit nawigacyjny platformy Azure**.

3. W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

4. Wybierz pozycję **Intune**. Zostanie wyświetlony **pulpit nawigacyjny usługi Intune**.

5. Wybierz pozycję **Zgodność urządzeń**, a następnie wybierz pozycję **Zasady** w obszarze **Zarządzanie**.

6. Wybierz pozycję **Utwórz zasady**.

7. Wpisz nazwę, opis i wybierz platformę, której te zasady mają dotyczyć.

8. Zostanie otwarty blok **Zasady zgodności systemu macOS**. Wybierz kategorie ustawień zgodności urządzeń — **Zabezpieczenia**, **Kondycja urządzenia** i **Właściwości urządzenia**, aby określić własne ustawienia.

10. Po zakończeniu wybierania ustawień wybierz pozycję **OK** w każdej kategorii ustawień zgodności urządzeń.

11. Wybierz pozycję **OK**, a następnie wybierz pozycję **Utwórz**.

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Aby przypisać użytkownikom zasady zgodności, wybierz skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w bloku **Zgodność — zasady**.

1. Wybierz zasady zgodności urządzeń, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie bloku, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.

2. Wybierz pozycję **Wybierz grupy**, aby otworzyć blok, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.

3. Wybierz pozycję **Wybierz**, a następnie wybierz pozycję **Zapisz**, aby przypisać zasady zgodności urządzeń do grup zabezpieczeń usługi Azure AD.

4. Po przypisaniu zasad zgodności urządzeń do grup można zamknąć blok **Przypisania**.

    > [!TIP]
    > Domyślnie urządzenia sprawdzają zgodność co 8 godzin, ale użytkownicy mogą wymusić ten proces za pomocą aplikacji Portal firmy usługi Intune.

## <a name="next-steps"></a>Następne kroki

[Jak monitorować zasady zgodności urządzeń](compliance-policy-monitor.md)
