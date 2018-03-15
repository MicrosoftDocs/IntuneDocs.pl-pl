---
title: "Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs"
description: "Dodawanie lub konfigurowanie profilu urządzenia w usłudze Microsoft Intune, w tym wybieranie typu platformy i konfigurowanie ustawień w witrynie Azure Portal"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c40fd13a46a61ec0ee05efba7ece7653f5de90ca
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Tworzenie profilu urządzenia w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Tworzenie profilu
1. W witrynie [Azure Portal](https://portal.azure.com) wybierz opcję **Wszystkie usługi** i wyszukaj usługę **Microsoft Intune**.

2. W obszarze **Microsoft Intune** wybierz pozycję **Konfiguracja urządzeń**, wybierz pozycję **Profile**, a następnie wybierz pozycję **Utwórz profil**.

3. Wprowadź następujące właściwości: 

    - **Nazwa**: wprowadź opisową nazwę nowego profilu
    - **Opis**: opcjonalny, ale zalecany. Wprowadź opis profilu.
    - **Platforma**: wybierz typ platformy:  

        - **Android**
        - **Android for Work**
        - **iOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 lub nowszy**
        - **Windows 10 lub nowszy**

    - **Typ profilu**: wybierz typ, który ma zostać utworzony. Lista zależy od wybranej platformy.
    - **Ustawienia**: ustawienia poszczególnych typów profilów opisano w następujących tematach:

        -  [Ustawienia funkcji urządzeń](device-features-configure.md)
        -  [Ustawienia ograniczeń dotyczących urządzeń](device-restrictions-configure.md)
        -  [Ustawienia poczty e-mail](email-settings-configure.md)
        -  [Ustawienia sieci VPN](vpn-settings-configure.md)
        -  [Ustawienia sieci Wi-Fi](wi-fi-settings-configure.md)
        -  [Ustawienia uaktualniania wersji systemu Windows 10](edition-upgrade-configure-windows-10.md)
        -  [Ustawienia certyfikatów](certificates-configure.md)
        -  [Ustawienia usługi Windows Information Protection](windows-information-protection-configure.md)
        -  [Ustawienia rozwiązań dla edukacji](education-settings-configure.md)
        -  [Ustawienia niestandardowe](custom-settings-configure.md)

    ![Wprowadzanie ustawień w celu utworzenia profilu urządzenia](./media/create-device-profile.png)

4. Po zakończeniu wybierz pozycję **Utwórz**. 

Profil zostanie utworzony i wyświetlony na liście. Aby przypisać ten profil do grup, zobacz [How to assign device profiles (Jak przypisywać profile urządzeń)](device-profile-assign.md).


## <a name="next-steps"></a>Następne kroki
Aby przypisywać profile urządzeń, zobacz [How to assign device profiles with Microsoft Intune (Jak przypisywać profile urządzeń przy użyciu usługi Microsoft Intune)](device-profile-assign.md).