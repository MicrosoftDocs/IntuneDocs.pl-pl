---
title: Tworzenie profilu urządzenia rozszerzenia jądra systemu macOS usłudze Microsoft Intune — Azure | Dokumentacja firmy Microsoft
titleSuffix: ''
description: Dodawanie lub tworzenie profilu urządzenia z systemem macOS, a następnie skonfiguruj rozszerzenia jądra, aby zezwolić na zastąpienie użytkowników, Dodawanie identyfikatora zespołu i identyfikator pakietu i zespołu w programie Microsoft Intune.
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
ms.openlocfilehash: fd2e03c09cb2bed49ee7607283bf63e2c3ae67da
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403909"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Dodawanie rozszerzeń do jądra systemu macOS w usłudze Intune

Na urządzeniach z systemem macOS można dodać funkcje na poziomie jądra. Te funkcje dostępu do części systemu operacyjnego, które programy regularne nie może uzyskać dostępu. Twoja organizacja może mieć określonych potrzeb i wymagań, które nie są dostępne w aplikacji, funkcja urządzenia i tak dalej. 

Aby dodać rozszerzenia jądra, które są zawsze mogą ładować na urządzeniach, należy dodać "jądra rozszerzenia" (KEXT) Microsoft Intune, a następnie Wdróż te rozszerzenia na urządzeniach z systemem.

Na przykład masz program skanowanie wirusów, skanowania urządzenia pod kątem złośliwej zawartości. Można dodać tego antywirusowe rozszerzenia jądra programu jako rozszerzenie jądra dozwolonych w usłudze Intune. Następnie "Przypisz" rozszerzenie dla urządzeń z systemem macOS.

Za pomocą tej funkcji Administratorzy mogą umożliwiać użytkownikom do zastąpienia rozszerzenia jądra, Dodaj identyfikatory zespołu i dodawanie rozszerzenia jądra określonej w usłudze Intune.

Ta funkcja ma zastosowanie do:

- System macOS 10.13.2 lub nowszy

Aby użyć tej funkcji, urządzenia muszą być:

- Zarejestrowane w usłudze Intune przy użyciu programu Apple Device Enrollment Program (DEP). [Automatyczne rejestrowanie urządzeń z systemem macOS](device-enrollment-program-enroll-macos.md) zawiera więcej informacji.

  LUB

- Zarejestrowane w usłudze Intune przy użyciu "rejestracji użytkownika zatwierdzone" (warunek firmy Apple). [Przygotowanie do zmiany z rozszerzeniami jądra w systemie macOS High Sierra](https://support.apple.com/en-us/HT208019) (otwiera witrynę sieci web firmy Apple) zawiera więcej informacji.

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można następnie wypychać lub wdrażać profil na urządzeniach z systemem macOS w organizacji.

W tym artykule pokazano, jak utworzyć profil konfiguracji urządzenia w usłudze Intune przy użyciu rozszerzenia jądra.

> [!TIP]
> Aby uzyskać więcej informacji na temat rozszerzeń jądra, zobacz [Przegląd rozszerzeń jądra](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (otwiera witrynę sieci web firmy Apple).

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Można dodać rozszerzenia bez znaku starszych jądra.
- Pamiętaj wprowadzić identyfikator właściwego zespołu i identyfikator rozszerzenia jądra. Usługa Intune nie weryfikuje wartości, które należy wprowadzić. Jeśli wprowadzasz błędne informacje, rozszerzenie nie będzie działać na urządzeniu.

> [!NOTE]
> Apple opublikowała informacje dotyczące podpisywania i notarization całego oprogramowania. W systemie macOS 10.14.5 i nowsze, jądra rozszerzenia wdrożone za pośrednictwem usługi Intune trzeba było zgodne z zasadami notarization firmy Apple.
>
> Instrukcje dotyczące tych zasad notarization i wszelkie aktualizacje i zmiany zobacz następujące zasoby:
>
>  - [Przed dystrybucją aplikacji notarizing](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (otwiera witrynę sieci web firmy Apple) 
>  - [Przygotowanie do zmiany z rozszerzeniami jądra w systemie macOS High Sierra](https://support.apple.com/en-us/HT208019) (otwiera witrynę sieci web firmy Apple)

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę nowego profilu.
    - **Opis:** wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz pozycję **macOS**
    - **Typ profilu**: Wybierz **rozszerzenia**.
    - **Ustawienia**: wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie:

        - [macOS](kernel-extensions-settings-macos.md)

4. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).
