---
title: "Aktywowanie trybu zgubienia urządzenia z systemem iOS przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Włączanie lub uruchamianie trybu zgubienia w celu dostosowania komunikatu wyświetlanego na ekranie blokady zgubionego lub skradzionego urządzenia z systemem iOS za pomocą usługi Microsoft Intune. Uzyskiwanie szczegółowych informacji dotyczących zabezpieczeń i ochrony prywatności podczas korzystania z akcji Tryb zgubienia."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47d6314dfaed546e5b4cff7f93a5540ba512bde9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Włączanie trybu zgubienia na urządzeniach z systemem iOS przy użyciu usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Tryb zgubienia** ułatwia włączenie trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS. Ten tryb pozwala wprowadzić komunikat i numer telefonu, który jest wyświetlany na ekranie blokady urządzenia. Aby użyć trybu zgubienia, urządzenie musi być urządzeniem z systemem iOS należącym do firmy i objętym trybem nadzorowanym.

## <a name="supported-platforms"></a>Obsługiwane platformy

- iOS 9.3 i nowsze

Ta funkcja **nie jest** obsługiwana w przypadku następujących platform: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Włączanie trybu zgubienia

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną **Tryb zgubienia**.
5. W obszarze **Tryb zgubienia** włącz tę funkcję. Następnie wprowadź komunikat, który ma być wyświetlany, oraz numer telefonu do kontaktu.
6. Wybierz przycisk **OK**, aby zapisać zmiany.

Po włączeniu trybu zgubienia wszystkie sposoby korzystania z urządzenia zostaną zablokowane. Użytkownik końcowy nie może uzyskać dostępu do urządzenia aż do momentu wyłączenia przez Ciebie trybu utraty. Przy włączonym trybie zgubienia można skorzystać z akcji [Zlokalizuj urządzenie](device-locate.md), aby dowiedzieć się, gdzie urządzenie się znajduje.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie utraty oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji żadne informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po włączeniu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w portalu Azure.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- We wprowadzonym komunikacie do wyświetlenia na ekranie blokady należy uwzględnić szczegółowe informacje umożliwiające zwrot utraconego urządzenia.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan włączenia trybu zgubienia, otwórz obszar **Urządzenia** i wybierz pozycję **Akcje urządzenia**.