---
title: "Ustawienia konfiguracji urządzenia udostępnianego dla urządzeń z systemem iOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune umożliwiających wyświetlanie informacji na ekranie blokady urządzenia z systemem iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c5473a280551ab74f781a2de682d7e5922491e98
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Ustawienia konfiguracji udostępnionego urządzenia umożliwiające wyświetlanie komunikatów na ekranie blokady urządzenia z systemem iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ustawienia konfiguracji udostępnionego urządzenia umożliwiają określenie opcjonalnego tekstu wyświetlanego w oknie logowania i na ekranie blokady. Można na przykład wprowadzić komunikat „W razie zgubienia zwróć do” oraz informacje dotyczące tagu zasobu. 

>[!IMPORTANT]
> Ta funkcja jest obsługiwana na nadzorowanych urządzeniach z systemem iOS w wersji 9.3 lub nowszej.

## <a name="create-shared-device-settings"></a>Tworzenie ustawień udostępnionego urządzenia

1. W bloku **Funkcje urządzenia** wybierz pozycję **Konfiguracja urządzenia udostępnianego (tylko nadzorowane)**.
2. W bloku **Konfiguracja urządzenia udostępnianego (tylko nadzorowane)** skonfiguruj następujące ustawienia:
    - **Informacje dotyczące tagu zasobu** — wprowadź informacje o tagu zasobu urządzenia. Na przykład: **Własność firmy Contoso Corp**. Wprowadzone informacje zostaną zastosowane do wszystkich urządzeń, do których zostanie przypisany ten profil.
    - **Przypis dolny ekranu blokady** — wprowadź informację, która może ułatwić zwrot urządzenia w przypadku jego utraty lub kradzieży. Na przykład: **W razie znalezienia zadzwoń: „numer”**.
3. Gdy skończysz, wybieraj przycisk **OK**, aż powrócisz do bloku **Utwórz profil**, a następnie wybierz pozycję **Utwórz**. 


## <a name="next-steps"></a>Następne kroki

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).
