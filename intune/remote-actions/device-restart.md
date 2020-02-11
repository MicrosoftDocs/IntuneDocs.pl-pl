---
title: Ponowne uruchamianie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Ponownie uruchom urządzenia z systemem Windows i iOS przy użyciu usługi Microsoft Intune w witrynie Azure Portal za pomocą zdalnej akcji Uruchom ponownie.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 82ebf35d0eb435f2df4e6cf55274808e6fa690f4
ms.sourcegitcommit: af384c46ec8d8def6aa32c3b89947748dc6fd28f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/22/2020
ms.locfileid: "76517545"
---
# <a name="remotely-restart-devices-with-intune"></a>Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja urządzenia **Uruchom ponownie** powoduje ponowne uruchomienie wybranego urządzenia (w ciągu 5 minut). Właściciel urządzenia nie jest automatycznie powiadamiany o ponownym uruchomieniu, dlatego ta akcja może doprowadzić do utraty wykonanej pracy.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana dla systemu Windows 8.1 i nowszego
- Windows Phone — obsługiwana dla systemu Windows Phone 8.1 i nowszego
- Urządzenia kiosku z systemem Android — obsługiwana w systemie Android 7.0 lub nowszym
- iOS — obsługiwana

    > [!Note]  
    > To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS zablokowane przy użyciu kodu dostępu nie dołączają ponownie do sieci Wi-Fi po ponownym uruchomieniu. Po ponownym uruchomieniu urządzenie może nie być w stanie nawiązać komunikacji z serwerem.
- macOS — nieobsługiwana
- Urządzenia z systemem Android i służbowymi profilami systemu Android — nieobsługiwana

## <a name="restart-a-device"></a>Ponowne uruchamianie urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz pozycję urządzenie > **Uruchom ponownie** > **Tak**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan akcji **Uruchom ponownie**, wybierz pozycję **Urządzenia** > **Akcje urządzenia**.
