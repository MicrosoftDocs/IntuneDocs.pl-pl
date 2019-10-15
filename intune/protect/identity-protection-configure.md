---
title: Używanie numeru PIN do logowania się do urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Użyj funkcji Windows Hello dla firm, aby zezwolić użytkownikom na logowanie do urządzeń przy użyciu numeru PIN, odcisku palca i innych opcji. Utwórz profil konfiguracji ochrony tożsamości w usłudze Intune dla urządzeń z systemem Windows 10 urządzenia przy użyciu tych ustawień i przypisz profil do grup użytkowników i grup urządzeń.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d81396dda2cbd8129d9bbcae961435b99946d74
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721308"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Korzystanie z funkcji Windows Hello dla firm na urządzeniach z systemem Windows 10 z usługą Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Funkcja Windows Hello dla firm to metoda logowania do urządzeń z systemem Windows przez zastępowanie haseł, kart inteligentnych i wirtualnych kart inteligentnych. Usługa Intune oferuje wbudowane ustawienia, dzięki którym administratorzy mogą konfigurować funkcję Windows Hello dla firm i jej używać. Tych ustawień można na przykład używać w celu:

- Włączania funkcji Windows Hello dla firm dla urządzeń i użytkowników
- Ustawiania wymagań dotyczących numeru PIN urządzenia, w tym minimalnej i maksymalnej długości numeru PIN
- Zezwalania na gesty, takie jak odcisk palca, których użytkownicy mogą (lub nie mogą) używać do logowania się na urządzeniach

Ta funkcja ma zastosowanie do urządzenia z systemem:

- System Windows 10 lub nowszy
- Windows 10 Mobile
- Windows Holographic for Business

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu należy wypchnąć lub wdrożyć te ustawienia do grup użytkowników i urządzeń w organizacji.

W tym artykule przedstawiono sposób tworzenia profilu konfiguracji urządzenia. Listę wszystkich ustawień i ich zadań można znaleźć w temacie [Windows 10 device settings to enable Windows Hello for Business](identity-protection-windows-settings.md) (Ustawienia urządzeń z systemem Windows 10 służące do włączania funkcji Windows Hello dla firm).

## <a name="create-the-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**. Usługa Windows Hello dla firm jest obsługiwana tylko na urządzeniach z systemem Windows 10 lub nowszym.
    - **Typ profilu**: wybierz pozycję **Identity protection**.
    - **Skonfiguruj usługę Windows Hello dla firm**: wybierz sposób konfigurowania usługi Windows Hello dla firm. Dostępne opcje:

        - **Nieskonfigurowane**: [aprowizuje usługę Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) na urządzeniu. Podczas przypisywania profilów ochrony tożsamości tylko do użytkowników wartością domyślną kontekstu urządzenia jest **Nieskonfigurowane**.
        - **Wyłączone**: wybierz tę opcję, jeśli nie chcesz używać usługi Windows Hello dla firm. Ta opcja powoduje wyłączenie usługi Windows Hello dla firm dla wszystkich użytkowników.
        - **Włączone**: wybierz tę opcję, aby przeprowadzać [aprowizowanie](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning), i skonfiguruj ustawienia usługi Windows Hello dla firm w usłudze Intune. wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie:

            - [Windows 10 device settings to enable Windows Hello for Business](identity-protection-windows-settings.md) (Ustawienia urządzeń z systemem Windows 10 służące do włączania funkcji Windows Hello dla firm)

4. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil został utworzony i wyświetlony na liście profilów. Następnie [przypisz](../configuration/device-profile-assign.md) ten profil do grup użytkowników i urządzeń stosownie do potrzeb.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/identity-protection-configure/disable-android-camera.png)

-->

## <a name="next-steps"></a>Następne kroki

- Zapoznaj się z listą wszystkich [ustawień i ich zadaniami](identity-protection-windows-settings.md).
- [Przypisywanie profilu](../configuration/device-profile-assign.md) i [monitorowanie jego stanu](../configuration/device-profile-monitor.md).