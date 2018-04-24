---
title: Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj profil urządzenia w usłudze Microsoft Intune, w tym wybierz typ platformy i skonfiguruj ustawienia w witrynie Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3d46960e6ea7e2ae9bed6c0016ddc309bd15f572
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Tworzenie profilu urządzenia w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Tworzenie profilu
1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** i wyszukaj usługę **Microsoft Intune**.

2. W obszarze **Microsoft Intune** wybierz pozycję **Konfiguracja urządzeń**, a następnie **Profile**. Następnie wybierz opcję **Utwórz profil**.

3. Wprowadź następujące właściwości:

   - **Nazwa**: wprowadź opisową nazwę nowego profilu.
   - **Opis:** wprowadź opis profilu. (Jest to opcjonalne, ale zalecane).
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

     ![Zrzut ekranu opcji Utwórz profil](./media/create-device-profile.png)

4. Po zakończeniu wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na liście.


## <a name="next-steps"></a>Następne kroki
Aby przypisywać profile urządzeń, zobacz [How to assign device profiles with Microsoft Intune (Jak przypisywać profile urządzeń przy użyciu usługi Microsoft Intune)](device-profile-assign.md).
