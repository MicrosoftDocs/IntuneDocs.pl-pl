---
title: Aktywowanie trybu zgubienia urządzenia z systemem iOS przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Włącz lub uruchom tryb zgubienia w celu dostosowania komunikatu wyświetlanego na ekranie blokady zgubionego lub skradzionego urządzenia z systemem iOS za pomocą usługi Microsoft Intune. Uzyskaj szczegółowe informacje dotyczące zabezpieczeń i ochrony prywatności podczas korzystania z akcji Tryb zgubienia.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ac83160e6604b7a679e03bb244e1dd5081a5fc5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728640"
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Włączanie trybu zgubienia na urządzeniach z systemem iOS przy użyciu usługi Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja urządzenia **Tryb zgubienia** ułatwia włączenie trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS. Ten tryb pozwala wprowadzić komunikat i numer telefonu, które będą wyświetlane na ekranie blokady urządzenia. Aby użyć trybu zgubienia, urządzenie musi być urządzeniem z systemem iOS należącym do firmy i objętym trybem nadzorowanym.

## <a name="supported-platforms"></a>Obsługiwane platformy

- iOS 9.3 i nowsze

Ta funkcja nie jest obsługiwana w przypadku następujących platform: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Włączanie trybu zgubienia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS, a następnie wybierz pozycję **...więcej**. Następnie wybierz zdalną akcję **Tryb zgubienia**.
5. W obszarze **Tryb zgubienia** włącz tę funkcję. Następnie wprowadź komunikat, który ma być wyświetlany, oraz numer telefonu do kontaktu.
6. Wybierz przycisk **OK**, aby zapisać zmiany.

Po włączeniu trybu zgubienia wszystkie sposoby korzystania z urządzenia zostaną zablokowane. Użytkownik końcowy nie może uzyskać dostępu do urządzenia aż do momentu wyłączenia przez Ciebie trybu utraty. Przy włączonym trybie zgubienia można skorzystać z akcji [Zlokalizuj urządzenie](device-locate.md), aby dowiedzieć się, gdzie urządzenie się znajduje.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie utraty oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji żadne informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po użyciu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w witrynie Azure Portal.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- We wprowadzonym komunikacie do wyświetlenia na ekranie blokady należy uwzględnić szczegółowe informacje umożliwiające zwrot utraconego urządzenia.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan włączenia trybu zgubienia, otwórz obszar **Urządzenia** i wybierz pozycję **Akcje urządzenia**.
