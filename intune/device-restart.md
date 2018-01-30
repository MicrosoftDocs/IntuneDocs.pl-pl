---
title: "Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak zdalnie ponownie uruchamiać urządzenia za pomocą akcji ponownego uruchomienia urządzenia."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9afe804d2f9e48e27ced4bd92959cd065f6ec89a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Uruchom ponownie** powoduje ponowne uruchomienie wybranego urządzenia. Właściciel urządzenia nie jest automatycznie powiadamiany o ponownym uruchomieniu, dlatego ta akcja może doprowadzić do utraty wykonanej pracy.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana dla systemu Windows 8.1 i nowszego
- Windows Phone — obsługiwana dla systemu Windows Phone 8.1 i nowszego
- iOS — obsługiwana

    > [!Note]  
    > To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS z blokadą opartą na kodzie dostępu nie połączą się z siecią Wi-Fi po ponownym uruchomieniu. Ponadto nawiązanie połączenia z serwerem może nie być możliwe.
- macOS — nieobsługiwana
- Android — nieobsługiwana

## <a name="how-to-restart-a-device"></a>Jak ponownie uruchomić urządzenie

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz akcję zdalną urządzenia **Uruchom ponownie**.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji, należy w bloku **Urządzenia i grupy** wybrać pozycję **Akcje urządzenia**.
