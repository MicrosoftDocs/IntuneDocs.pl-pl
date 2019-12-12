---
title: Ustawienia zgodności dla systemu Windows 8.1 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem Windows 8.1 i Windows Phone 8.1 w usłudze Microsoft Intune. Możesz między innymi sprawdzać zgodność z wymaganiami dotyczącymi minimalnej i maksymalnej wersji systemu operacyjnego, określać długość hasła i inne ograniczenia, czy włączać szyfrowanie magazynu danych.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e074d922078a9772ca67a6ebd99948bc3e64601
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72813214"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem Windows 8.1 umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem Windows 8.1 za pomocą usługi Intune. Możesz zastosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi blokować zbyt proste hasła czy określić minimalną lub maksymalną wersję systemu operacyjnego.

Ta funkcja ma zastosowanie do:

- Windows Phone 8,1
- Windows 8.1 i nowsze

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W obszarze **Platforma** wybierz pozycję **Windows Phone 8.1** lub **Windows 8.1 i nowsze**.

## <a name="device-properties"></a>Właściwości urządzenia

### <a name="operating-system-version"></a>Wersja systemu operacyjnego

**System Windows Phone 8.1 lub nowszy**
- **Minimalna wersja systemu operacyjnego dla urządzeń przenośnych**:  
  Wprowadź minimalną dozwoloną wersję. Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik urządzenia może zdecydować się na jego uaktualnienie, co umożliwi mu dostęp do zasobów firmy.

- **Maksymalna wersja systemu operacyjnego dla urządzeń przenośnych**:  
  Wprowadź maksymalną dozwoloną wersję. Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik urządzenia zostanie poproszony o skontaktowanie się z administratorem IT. Urządzenie nie może uzyskiwać dostępu do zasobów organizacyjnych do momentu zmiany reguły na dopuszczającą daną wersję systemu operacyjnego.

**Windows 8.1 lub nowszy**
- **Minimalna wersja systemu operacyjnego**:  
  Wprowadź minimalną dozwoloną wersję. Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik urządzenia może zdecydować się na jego uaktualnienie, co umożliwi mu dostęp do zasobów firmy.

- **Maksymalna wersja systemu operacyjnego**:  
  Wprowadź maksymalną dozwoloną wersję. Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik urządzenia zostanie poproszony o skontaktowanie się z administratorem IT. Urządzenie nie może uzyskiwać dostępu do zasobów organizacyjnych do momentu zmiany reguły na dopuszczającą daną wersję systemu operacyjnego.

Komputery z systemem Windows 8.1 zwracają wersję **3**. Jeśli ustawiono regułę wersji systemu operacyjnego Windows na wartość Windows 8.1, urządzenie jest zgłaszane jako niezgodne nawet wtedy, gdy działa na nim system Windows 8.1.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń.

- **Proste hasła**:  
  - **Nie skonfigurowano** (*Domyślnie*) — użytkownicy mogą tworzyć proste hasła, takie jak **1234** lub **1111**.
  - **Blokuj** — użytkownicy nie mogą tworzyć prostych haseł, takich jak **1234** lub **1111**.  

- **Minimalna długość hasła**:  
  wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.

  W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konto Microsoft, zasady zgodności nie będą oceniane prawidłowo w przypadku spełnienia dowolnego z następujących warunków:  
  - Minimalna długość hasła jest większa niż osiem znaków.
  - Minimalna liczba zestawów znaków jest większa niż dwa.

- **Typ hasła**:  
  określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).

  Po wybraniu opcji *alfanumeryczne*dostępne jest następujące ustawienie.  

  - **Liczba znaków innych niż alfanumeryczne w haśle**:  
    Jeśli *Typ hasła* jest ustawiony na wartość **alfanumeryczne**, Określ minimalną liczbę zestawów znaków, które musi zawierać hasło. Opcje obejmują **od 0** do **4** zestawów, z wartością domyślną **1**.
    
    Są cztery zestawy znaków:
    - Małe litery
    - Wielkie litery
    - Symbole
    - Liczby

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika. W przypadku urządzeń, które są dostępne z konto Microsoft, zasady zgodności nie będą oceniane prawidłowo, jeśli spełniony jest jeden z następujących warunków:

    - Minimalna długość hasła jest większa niż osiem znaków.
    - Minimalna liczba zestawów znaków jest większa niż dwa.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**:  
  wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni)** :  
  wybierz liczbę dni, po których wygasa hasło i użytkownicy muszą utworzyć nowe.

- **Liczba poprzednich haseł, których nie można użyć ponownie**:  
  wprowadź liczbę wcześniej używanych haseł, których nie można użyć ponownie.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**:  
  - **Nie skonfigurowano** (*wartość domyślna*)
  - **Wymagaj** — wybierz pozycję *Wymagaj*, aby szyfrować magazyn danych na urządzeniach.


<!-- not on phone   
- **Require encryption on mobile device**: **Require** the device to be encrypted to connect to data storage resources.
--> 

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem Windows 10 i nowszym](compliance-policy-create-windows.md).