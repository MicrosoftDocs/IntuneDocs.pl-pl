---
title: Ograniczanie funkcji urządzeń przy użyciu zasad w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie profilu urządzenia w celu ograniczenia funkcji na urządzeniach z systemem Android, macOS, iOS, iPadOS, Windows Phone oraz Windows 10 w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfa640d5858479b5f98009e92f005312966f536a
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755282"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Konfiguracja ustawień ograniczeń urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune zawiera zasady ograniczania urządzeń, które ułatwiają administratorom kontrolowanie urządzeń z systemami Android, iOS, macOS i Windows. Te ograniczenia umożliwiają kontrolę szerokiego zakresu ustawień i funkcji w celu ochrony zasobów organizacji. Administratorzy mogą na przykład:

- zezwalać na używanie aparatu urządzenia lub je blokować;
- kontrolować dostęp do sklepu Google Play, sklepów z aplikacjami, wyświetlania dokumentów i gier;
- blokować aplikacje wbudowane lub tworzyć listę aplikacji, które są dozwolone lub zabronione;
- zezwalać na tworzenie kopii zapasowych plików w chmurze i na kontach magazynu lub blokować tę funkcję;
- ustawiać minimalną długość hasła i blokować proste hasła.

Te funkcje są dostępne w usłudze Intune i są konfigurowane przez administratora. „Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można wypychać lub wdrażać profil na urządzeniach w organizacji.

W tym artykule przedstawiono sposób tworzenia profilu ograniczeń urządzenia. Zawiera on również listę wszystkich dostępnych ustawień dla różnych platform.

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę zasad. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Dobra nazwa zasad to na przykład **iOS: Blokowanie aparatu na urządzeniach**.
    - **Opis**: wprowadź opis zasad. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:  

        - **Android**
        - **Android enterprise**
        - **iOS/iPadOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 lub nowszy**
        - **Windows 10 lub nowszy**

    - **Typ profilu**: Wybierz pozycję **Ograniczenia dotyczące urządzeń**.

        Aby utworzyć profil ograniczeń dotyczących urządzeń z systemem Windows 10 Team, np. urządzeń Surface Hub, wybierz pozycję **Ograniczenia dotyczące urządzeń (Windows 10 Team)** .

4. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Wybierz platformę dla ustawień szczegółowych:

    - [Ustawienia systemu Android](../device-restrictions-android.md)
    - [Ustawienia systemu Android Enterprise](../device-restrictions-android-for-work.md)
    - [Ustawienia systemu iOS/iPadOS](device-restrictions-ios.md)
    - [Ustawienia systemu macOS](device-restrictions-macos.md)
    - [Ustawienia systemu Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Ustawienia systemu Windows 10](device-restrictions-windows-10.md)
    - [Ustawienia systemu Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Ustawienia systemu Windows Holographic for Business](device-restrictions-windows-holographic.md)

5. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil został utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](../device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/device-restrictions-configure/disable-android-camera.png)

-->
