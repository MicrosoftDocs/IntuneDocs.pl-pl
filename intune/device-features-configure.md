---
title: Tworzenie profilu urządzenia z systemem iOS lub macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil urządzenia z systemem iOS lub macOS, a następnie skonfiguruj ustawienia funkcji AirPrint, układu ekranu głównego, powiadomień aplikacji, urządzenia udostępnionego, logowania jednokrotnego i filtru zawartości internetowej w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aad3ad2a4f2e45fd94de057500686a718e8ee024
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839473"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Dodawanie ustawień funkcji urządzenia z systemem iOS lub macOS w usłudze Intune

Usługa Intune oferuje wiele funkcji i ustawień, które pomagają administratorom kontrolować urządzenia z systemami iOS i macOS. Administratorzy mogą na przykład:

- Zezwalać użytkownikom na dostęp do drukarek AirPrint w sieci
- Dodawać aplikacje i foldery do ekranu głównego, w tym dodawać nowe strony
- Wybierać, czy i jak będą wyświetlane powiadomienia w aplikacji
- Konfigurować ekran blokady, aby pokazywać komunikat lub tag zasobu, szczególnie w przypadku urządzeń udostępnionych
- Oferować użytkownikom bezpieczne środowisko logowania jednokrotnego w celu udostępniania poświadczeń między aplikacjami
- Filtrować witryny internetowe, które używają języka dla dorosłych, oraz zezwalać na określone witryny internetowe lub je blokować

Te funkcje są dostępne w usłudze Intune i są konfigurowane przez administratora. „Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można następnie wypychać lub wdrażać profil na urządzeniach z systemem iOS i macOS w organizacji.

W tym artykule przedstawiono sposób tworzenia profilu konfiguracji urządzenia. Zawiera on również listę wszystkich dostępnych ustawień dla urządzeń z systemem [iOS](ios-device-features-settings.md) i [macOS](macos-device-features-settings.md).

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz platformę:
        - **iOS**
        - **macOS**
    - **Typ profilu**: wybierz pozycję **Funkcje urządzenia**.
    - **Ustawienia**: wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. Gdy wszystko będzie gotowe, wybierz przycisk **OK** i wybierz pozycję **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Wyświetl wszystkie ustawienia funkcji urządzenia dla urządzeń z systemem [iOS](ios-device-features-settings.md) i [macOS](macos-device-features-settings.md).
