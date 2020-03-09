---
title: Aktywowanie trybu zgubienia urządzenia z systemem iOS/iPadOS przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Włącz lub uruchom tryb zgubienia w celu dostosowania komunikatu wyświetlanego na ekranie blokady zgubionego lub skradzionego urządzenia z systemem iOS/iPadOS za pomocą usługi Microsoft Intune. Uzyskaj szczegółowe informacje dotyczące zabezpieczeń i ochrony prywatności podczas korzystania z akcji Tryb zgubienia.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 96e037b3d4bcec09765a0228e4f35041fe316cf6
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782175"
---
# <a name="enable-lost-mode-on-iosipados-devices-with-intune"></a>Włączanie trybu zgubienia na urządzeniach z systemem iOS/iPadOS przy użyciu usługi Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja urządzenia **Tryb zgubienia** ułatwia włączenie trybu zgubienia na zgubionych lub skradzionych urządzeniach z systemem iOS/iPadOS. Ten tryb pozwala wprowadzić komunikat i numer telefonu, które będą wyświetlane na ekranie blokady urządzenia. Aby użyć trybu zgubienia, urządzenie musi być urządzeniem z systemem iOS/iPadOS należącym do firmy i objętym trybem nadzorowanym.

## <a name="supported-platforms"></a>Obsługiwane platformy

- iOS 9.3 i nowsze
- iPadOS 13.0 lub nowszy

Ta funkcja nie jest obsługiwana w przypadku następujących platform: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Włączanie trybu zgubienia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie z systemem iOS/iPadOS, a następnie wybierz pozycję **Tryb zgubienia (tylko tryb nadzorowany)** .
5. W obszarze **Tryb zgubienia**wybierz pozycję **Włącz**.
6. W polu **Komunikat wyświetlany na ekranie blokady** wpisz komunikat, który ma być wyświetlany na ekranie blokady urządzenia.
7. Opcjonalnie wprowadź numer telefonu w polu **Numer telefonu do wyświetlenia**.
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
