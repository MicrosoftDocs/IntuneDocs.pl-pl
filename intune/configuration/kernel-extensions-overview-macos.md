---
title: Tworzenie profilu urządzenia rozszerzeń jądra systemu macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodaj lub utwórz profil urządzenia z systemem macOS, a następnie skonfiguruj rozszerzenia jądra, aby zezwalać na przesłonięcie użytkownika, dodaj identyfikator zespołu oraz pakiet i identyfikator zespołu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/25/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8a516ce9dda525d5c7a48fcbc2c799471489d0d
ms.sourcegitcommit: ff254acb94df88afc3e3e7b878084052adf40745
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77600246"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Dodawanie rozszerzeń jądra systemu macOS w usłudze Intune

> [!NOTE]
> Rozszerzenia jądra systemu macOS są zastępowane rozszerzeniami systemowymi. Aby uzyskać więcej informacji, zobacz [Support tip: Using system extensions instead of kernel extensions for macOS Catalina 10.15 in Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-using-system-extensions-instead-of-kernel-extensions/ba-p/1191413) (Porada pomocy technicznej: korzystanie z rozszerzeń systemowych zamiast rozszerzeń jądra w przypadku systemu macOS Catalina 10.15 w usłudze Intune).

Na urządzeniach z systemem macOS można dodawać funkcje na poziomie jądra. Te funkcje uzyskują dostęp do części systemu operacyjnego, do których nie mogą uzyskać dostępu zwykłe programy. Organizacja może mieć określone potrzeby lub wymagania, które nie są dostępne w aplikacji, funkcji urządzenia i tak dalej. 

Aby dodać rozszerzenia jądra, które zawsze mogą być ładowane na urządzeniach, dodaj „rozszerzenia jądra” (KEXT) w usłudze Microsoft Intune, a następnie wdróż te rozszerzenia na urządzeniach.

Na przykład masz program skanujący w poszukiwaniu wirusów, który skanuje urządzenie pod kątem złośliwej zawartości. To rozszerzenie jądra programu antywirusowego można dodać jako dozwolone rozszerzenie jądra w usłudze Intune. Następnie „przypisz” rozszerzenie do urządzeń z systemem macOS.

Dzięki tej funkcji administratorzy mogą zezwalać użytkownikom na przesłanianie rozszerzeń jądra, dodawanie identyfikatorów zespołów i dodawanie określonych rozszerzeń jądra w usłudze Intune.

Ta funkcja ma zastosowanie do:

- System macOS 10.13.2 lub nowszy

Aby można było korzystać z tej funkcji, urządzenia muszą spełniać następujące wymagania:

- Muszą być zarejestrowane w usłudze Intune w ramach programu Device Enrollment Program (DEP) firmy Apple. Aby uzyskać więcej informacji, zobacz [Automatyczne rejestrowanie urządzeń z systemem macOS](../enrollment/device-enrollment-program-enroll-macos.md).

  LUB

- Muszą być zarejestrowane w usłudze Intune w ramach „rejestracji zatwierdzonej przez użytkownika” (termin firmy Apple). Aby uzyskać więcej informacji, zobacz [Prepare for changes to kernel extensions in macOS High Sierra (Przygotowanie do zmian w zakresie rozszerzeń jądra w systemie macOS High Sierra)](https://support.apple.com/en-us/HT208019) (otwiera witrynę internetową firmy Apple).

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można następnie wypychać lub wdrażać profil na urządzeniach z systemem macOS w organizacji.

W tym artykule przedstawiono sposób tworzenia profilu konfiguracji urządzenia za pomocą rozszerzeń jądra w usłudze Intune.

> [!TIP]
> Aby uzyskać więcej informacji na temat rozszerzeń jądra, zobacz [omówienie rozszerzeń jądra](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (otwiera witrynę internetową firmy Apple).

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Możesz dodać niepodpisane starsze rozszerzenia jądra.
- Upewnij się, że wprowadzono poprawny identyfikator zespołu i identyfikator pakietu rozszerzenia jądra. Usługa Intune nie weryfikuje wprowadzonych wartości. Jeśli wprowadzisz nieprawidłowe informacje, rozszerzenie nie będzie działało na urządzeniu. Identyfikator zespołu ma dokładnie 10 znaków alfanumerycznych. 

> [!NOTE]
> Firma Apple udostępniła informacje dotyczące podpisywania i poświadczania dla całego oprogramowania. W systemie macOS 10.14.5 lub nowszym rozszerzenia jądra wdrożone za pośrednictwem usługi Intune nie muszą być zgodne z zasadami poświadczania firmy Apple.
>
> Informacje o tych zasadach poświadczania oraz o wszelkich aktualizacjach lub zmianach można znaleźć w następujących zasobach:
>
> - [Notarizing your app before distribution (Poświadczanie aplikacji przed dystrybucją)](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (otwiera witrynę firmy Apple) 
> - [Prepare for changes to kernel extensions in macOS High Sierra (Przygotowanie do zmian w zakresie rozszerzeń jądra w systemie macOS High Sierra)](https://support.apple.com/en-us/HT208019) (otwiera witrynę internetową firmy Apple)

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **macOS**
    - **Typ profilu**: Wybierz pozycję **Rozszerzenia**.
    - **Ustawienia**: wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie:

        - [macOS](kernel-extensions-settings-macos.md)

4. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. Pamiętaj, aby [przypisać profil](../device-profile-assign.md) i [monitorować jego stan](../device-profile-monitor.md).

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](../device-profile-monitor.md).
