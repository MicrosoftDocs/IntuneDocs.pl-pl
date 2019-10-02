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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d1e13801e3235831081be76ddfe5c8f5872e2077
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728523"
---
# <a name="remotely-restart-devices-with-intune"></a>Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja urządzenia **Uruchom ponownie** powoduje ponowne uruchomienie wybranego urządzenia. Właściciel urządzenia nie jest automatycznie powiadamiany o ponownym uruchomieniu, dlatego ta akcja może doprowadzić do utraty wykonanej pracy.

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

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie, wybierz pozycję **Więcej**, a następnie wybierz akcję zdalną urządzenia **Uruchom ponownie**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan akcji **Uruchom ponownie**, wybierz pozycję **Urządzenia** > **Akcje urządzenia**.
