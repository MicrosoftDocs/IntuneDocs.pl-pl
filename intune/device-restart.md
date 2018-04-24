---
title: Ponowne uruchamianie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Ponownie uruchom urządzenia z systemem Windows i iOS przy użyciu usługi Microsoft Intune w witrynie Azure Portal za pomocą zdalnej akcji Uruchom ponownie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f8aadebceed9c58717801b374a3a5d776926343
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Uruchom ponownie** powoduje ponowne uruchomienie wybranego urządzenia. Właściciel urządzenia nie jest automatycznie powiadamiany o ponownym uruchomieniu, dlatego ta akcja może doprowadzić do utraty wykonanej pracy.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana dla systemu Windows 8.1 i nowszego
- Windows Phone — obsługiwana dla systemu Windows Phone 8.1 i nowszego
- iOS — obsługiwana

    > [!Note]  
    > To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS zablokowane przy użyciu kodu dostępu nie dołączają ponownie do sieci Wi-Fi po ponownym uruchomieniu. Po ponownym uruchomieniu urządzenie może nie być w stanie nawiązać komunikacji z serwerem.
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="restart-a-device"></a>Ponowne uruchamianie urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie, wybierz pozycję **Więcej**, a następnie wybierz akcję zdalną urządzenia **Uruchom ponownie**.

## <a name="next-steps"></a>Następne kroki

- Aby wyświetlić stan akcji **Uruchom ponownie**, wybierz pozycję **Urządzenia** > **Akcje urządzenia**.
