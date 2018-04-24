---
title: Ustawienia konfiguracji urządzeń udostępnianych dla urządzeń z systemem iOS w usłudze Microsoft Intune
titlesuffix: ''
description: Informacje na temat ustawień usługi Microsoft Intune umożliwiających wyświetlanie informacji na ekranie blokady urządzeń z systemem iOS.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73c4f96e3057227bc601175c4e8f42802eb322bc
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Ustawienia konfiguracji udostępnionego urządzenia umożliwiające wyświetlanie komunikatów na ekranie blokady urządzenia z systemem iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia usługi Microsoft Intune umożliwiające wyświetlanie informacji na ekranie blokady urządzeń z systemem iOS.

Ustawienia konfiguracji udostępnionego urządzenia umożliwiają określenie opcjonalnego tekstu wyświetlanego w oknie logowania i na ekranie blokady. Można na przykład wprowadzić komunikat „W razie zgubienia zwróć do” oraz informacje dotyczące tagu zasobu. 

>[!IMPORTANT]
> Ta funkcja jest obsługiwana na nadzorowanych urządzeniach z systemem iOS w wersji 9.3 lub nowszej.

## <a name="create-shared-device-settings"></a>Tworzenie ustawień udostępnionego urządzenia

1. Z obszaru [Usługa Intune w witrynie Azure Portal](https://portal.azure.com) przejdź do obszaru [**Funkcje urządzenia** w obszarze konfiguracji urządzenia](device-features-configure.md). 
1. W okienku **Funkcje urządzenia** wybierz pozycję **Konfiguracja urządzenia udostępnianego (tylko nadzorowane)**.
2. W okienku **Konfiguracja urządzenia udostępnianego (tylko nadzorowane)** skonfiguruj następujące ustawienia:
    - **Informacje dotyczące tagu zasobu** — wprowadź informacje o tagu zasobu urządzenia. Na przykład: **Własność firmy Contoso Corp**. Wprowadzone informacje zostaną zastosowane do wszystkich urządzeń, do których zostanie przypisany ten profil.
    - **Przypis dolny ekranu blokady** — wprowadź informację, która może ułatwić zwrot urządzenia w przypadku jego utraty lub kradzieży. Na przykład: **W razie znalezienia zadzwoń: „numer”**.
3. Gdy skończysz, wybieraj przycisk **OK**, aż powrócisz do okienka **Utwórz profil**, a następnie wybierz pozycję **Utwórz**. 


## <a name="next-steps"></a>Następne kroki

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).
