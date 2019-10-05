---
title: Ustawienia zgodności dla systemu Windows 8.1 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem Windows 8.1 i Windows Phone 8.1 w usłudze Microsoft Intune. Możesz między innymi sprawdzać zgodność z wymaganiami dotyczącymi minimalnej i maksymalnej wersji systemu operacyjnego, określać długość hasła i inne ograniczenia, czy włączać szyfrowanie magazynu danych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f37fbd4cf2cc67e8e102ae5bdd4647e0073aa2da
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733026"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem Windows 8.1 umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem Windows 8.1 za pomocą usługi Intune. Możesz zastosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi blokować zbyt proste hasła czy określić minimalną lub maksymalną wersję systemu operacyjnego.

Ta funkcja ma zastosowanie do:

- Windows Phone 8,1
- Windows 8.1 i nowsze

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W obszarze **Platforma** wybierz pozycję **Windows Phone 8.1** lub **Windows 8.1 i nowsze**.

## <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego**: wprowadź minimalną wymaganą wersję. Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego**: wprowadź maksymalną dozwoloną wersję. jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż wprowadzona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Urządzenie nie może uzyskiwać dostępu do zasobów organizacji do momentu zmiany reguły na dopuszczającą daną wersję systemu operacyjnego.

Komputery z systemem Windows 8.1 zwracają wersję **3**. Jeśli ustawiono regułę wersji systemu operacyjnego Windows na wartość Windows 8.1, urządzenie jest zgłaszane jako niezgodne nawet wtedy, gdy działa na nim system Windows 8.1.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.

  W przypadku urządzeń z systemem Windows, które są dostępne przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem:
  - Jeśli minimalna długość hasła jest większa niż osiem znaków
  - Lub jeśli minimalna liczba zestawów znaków jest większa niż dwa

- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
  
  - **Liczba znaków innych niż alfanumeryczne w haśle**: jeśli pozycja **Wymagany typ hasła** została ustawiona na wartość **Alfanumeryczne**, to ustawienie określa minimalną wymaganą liczbę zestawów znaków do użycia w haśle. Są cztery zestawy znaków:
    - Małe litery
    - Wielkie litery
    - Symbole
    - Liczby

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika. W przypadku urządzeń, które są dostępne przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem:

    - Jeśli minimalna długość hasła jest większa niż osiem znaków
    - Lub jeśli minimalna liczba zestawów znaków jest większa niż dwa

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)** : wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

### <a name="encryption"></a>Szyfrowanie

- **Wymagaj szyfrowania na urządzeniu przenośnym**: wartość **Wymagaj** oznacza, że urządzenie musi zostać zaszyfrowane w celu połączenia się z zasobami magazynu danych.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem Windows 10 i nowszym](compliance-policy-create-windows.md).