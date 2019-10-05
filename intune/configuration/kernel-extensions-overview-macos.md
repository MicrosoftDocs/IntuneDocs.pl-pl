---
title: Tworzenie profilu urządzenia rozszerzeń jądra macOS Microsoft Intune na platformie Azure | Microsoft Docs
titleSuffix: ''
description: Dodaj lub Utwórz profil urządzenia macOS, a następnie skonfiguruj rozszerzenia jądra, aby zezwalać na przesłonięcie użytkowników, Dodawanie identyfikatora zespołu oraz pakiet i identyfikator zespołu w Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9832089cf73405a9e39795b076e9ead84bc7d7cd
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734456"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Dodawanie rozszerzeń jądra macOS w usłudze Intune

Na urządzeniach z systemem macOS można dodawać funkcje na poziomie jądra. Te funkcje uzyskują dostęp do części systemu operacyjnego, do których nie mogą uzyskać dostępu zwykłe programy. Organizacja może mieć określone potrzeby lub wymagania, które nie są dostępne w aplikacji, funkcji urządzenia i tak dalej. 

Aby dodać rozszerzenia jądra, które są zawsze dozwolone do ładowania na urządzeniach, należy dodać "rozszerzenia jądra" (KEXT) w Microsoft Intune, a następnie wdrożyć te rozszerzenia na urządzeniach.

Na przykład masz program skanujący wirusa, który skanuje urządzenie pod kątem złośliwej zawartości. To rozszerzenie jądra programu antywirusowego można dodać jako dozwolone rozszerzenie jądra w usłudze Intune. Następnie "Przypisz" rozszerzenie do urządzeń z macOS.

Dzięki tej funkcji Administratorzy mogą zezwalać użytkownikom na przesłanianie rozszerzeń jądra, Dodawanie identyfikatorów zespołów i dodawanie określonych rozszerzeń jądra w usłudze Intune.

Ta funkcja ma zastosowanie do:

- System macOS 10.13.2 lub nowszy

Aby można było korzystać z tej funkcji, urządzenia muszą być:

- Zarejestrowane w usłudze Intune przy użyciu Device Enrollment Program firmy Apple (DEP). [Automatyczne rejestrowanie urządzeń macOS](../enrollment/device-enrollment-program-enroll-macos.md) ma więcej informacji.

  LUB

- Zarejestrowane w usłudze Intune z "rejestracją zatwierdzone przez użytkownika" (termin firmy Apple). [Przygotuj się do zmian rozszerzeń jądra w MacOS wysoka Sierra](https://support.apple.com/en-us/HT208019) (otwiera witrynę sieci Web firmy Apple), aby uzyskać więcej informacji.

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można następnie wypychać lub wdrażać profil na urządzeniach z systemem macOS w organizacji.

W tym artykule opisano sposób tworzenia profilu konfiguracji urządzenia przy użyciu rozszerzeń jądra w usłudze Intune.

> [!TIP]
> Aby uzyskać więcej informacji na temat rozszerzeń jądra, zobacz [Omówienie rozszerzenia jądra](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (otwiera witrynę sieci Web firmy Apple).

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Można dodać niepodpisane starsze rozszerzenia jądra.
- Upewnij się, że wprowadzono poprawny identyfikator zespołu i identyfikator pakietu rozszerzenia jądra. Usługa Intune nie sprawdza poprawności wprowadzonych wartości. Jeśli wprowadzisz nieprawidłowe informacje, rozszerzenie nie będzie działało na urządzeniu.

> [!NOTE]
> Firma Apple wydała informacje dotyczące podpisywania i notarization dla całego oprogramowania. W systemie macOS 10.14.5 i nowszych rozszerzenia jądra wdrożone za poorednictwem usługi Intune nie muszą spełniać zasad notarization firmy Apple.
>
> Aby uzyskać informacje o tych zasadach notarization oraz o wszelkich aktualizacjach lub zmianach, zobacz następujące zasoby:
>
> - [Notarizing aplikację przed dystrybucją](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (otwiera witrynę sieci Web firmy Apple) 
> - [Przygotuj się do zmian rozszerzeń jądra w MacOS High Sierra](https://support.apple.com/en-us/HT208019) (otwiera witrynę sieci Web firmy Apple)

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę nowego profilu.
    - **Opis:** wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz pozycję **macOS**
    - **Typ profilu**: wybierz pozycję **rozszerzenia**.
    - **Ustawienia**: wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie:

        - [macOS](kernel-extensions-settings-macos.md)

4. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. Pamiętaj, aby [przypisać profil](../device-profile-assign.md) i [monitorować jego stan](../device-profile-monitor.md).

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](../device-profile-monitor.md).
