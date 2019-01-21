---
title: Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj profil urządzenia w usłudze Microsoft Intune, w tym wybierz typ platformy i skonfiguruj ustawienia w witrynie Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cb6e3f0a9f62348d55b5dc2284c1007ea7faf088
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203216"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Tworzenie profilu urządzenia w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.

2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.

3. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: wybierz typ platformy:  

       - **Android**
       - **Android enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 lub nowszy**
       - **Windows 10 lub nowszy**

   - **Typ profilu**: wybierz typ, który ma zostać utworzony. Lista zależy od wybranej platformy.
   - **Ustawienia**: Ustawienia poszczególnych typów profilów opisano w następujących artykułach:

       -  [Funkcje urządzenia](device-features-configure.md)
       -  [Ograniczenia dotyczące urządzeń](device-restrictions-configure.md)
       -  [Program Endpoint Protection](endpoint-protection-configure.md)
       -  [Identity Protection](identity-protection-configure.md)  
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
