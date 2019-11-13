---
title: Korzystanie z niestandardowych ustawień urządzenia w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu umożliwiającego korzystanie z ustawień niestandardowych na urządzeniach z systemem Windows Phone, Windows 8.1, Windows 10 lub nowszym, Android, Android Enterprise, macOS oraz iOS za pomocą usługi Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c815a2c911dba6d17fc864b446122931fa88e91
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755385"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Tworzenie profilu z ustawieniami niestandardowymi w usłudze Intune

## <a name="what-are-custom-profiles"></a>Czym są profile niestandardowe

Usługa Microsoft Intune zawiera wiele wbudowanych ustawień do kontrolowania różnych funkcji na urządzeniu. Profile niestandardowe można również tworzyć. Profile niestandardowe świetnie się sprawdzają, gdy chcesz użyć ustawień i funkcji urządzenia, które nie są wbudowane w usłudze Intune. Takie profile zawierają funkcje i ustawienia, które możesz kontrolować na urządzeniach w organizacji. Możesz na przykład utworzyć profil niestandardowy, który ustawia tę samą funkcję dla każdego urządzenia z systemem iOS.

Aby uzyskać więcej informacji na temat profilów konfiguracji, zobacz [Co to są profile urządzeń w usłudze Microsoft Intune?](device-profiles.md). 

Ten artykuł zawiera linki do instrukcji tworzenia profilów niestandardowych dla systemów Android, Android Enterprise, iOS, macOS i Windows.

## <a name="available-platforms"></a>Dostępne platformy

Konfiguracja ustawień niestandardowych przebiega różnie w zależności od platformy. Na przykład w celu sterowania funkcjami urządzeń z systemami Android i Windows można określić wartości Open Mobile Alliance Uniform Resource Identifier (OMA-URI). W przypadku urządzeń firmy Apple można zaimportować plik utworzony za pomocą programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) lub [Apple Profile Manager](https://support.apple.com/profile-manager).

Profile niestandardowe są tworzone podobnie, jak profile wbudowane, i są dostępne na następujących platformach:

- [Android](../custom-settings-android.md)
- [Android Enterprise](../custom-settings-android-for-work.md)
- [iOS/iPadOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Następne kroki

Wybierz platformę i rozpocznij pracę:

- [Android](../custom-settings-android.md)
- [Android Enterprise](../custom-settings-android-for-work.md)
- [iOS/iPadOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
