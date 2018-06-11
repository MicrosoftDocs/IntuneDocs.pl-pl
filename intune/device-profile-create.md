---
title: Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj profil urządzenia w usłudze Microsoft Intune, w tym wybierz typ platformy i skonfiguruj ustawienia w witrynie Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3f62e306574606ffa1eb1e6f242c3cb30b1a9c1b
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744656"
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

       -  [Funkcje urządzenia](device-features-configure.md)
       -  [Ograniczenia dotyczące urządzeń](device-restrictions-configure.md)
       -  [Program Endpoint Protection](endpoint-protection-configure.md)
       -  [Kiosk](kiosk-settings.md)
       -  [Poczta e-mail](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Edukacja dla [systemu Windows 10](education-settings-configure.md) i [systemu iOS](wi-fi-settings-ios.md)
       -  [Windows 10 — uaktualnienie wersji](edition-upgrade-configure-windows-10.md)
       -  [Zasady aktualizacji systemu iOS](software-updates-ios.md)
       -  [Certyfikaty](certificates-configure.md)
       -  [Rozwiązanie Windows Information Protection](windows-information-protection-configure.md)
       -  [Niestandardowe](custom-settings-configure.md)

     ![Zrzut ekranu opcji Utwórz profil](./media/create-device-profile.png)

4. Po zakończeniu wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na liście.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
