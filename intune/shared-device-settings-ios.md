---
title: "Ustawienia konfiguracji urządzenia udostępnianego dla urządzeń z systemem iOS w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień umożliwiających wyświetlanie informacji na ekranie blokady urządzenia z systemem iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6a2aba8b2f062a3e06d517a572992b84fd977514
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Ustawienia konfiguracji urządzenia udostępnianego umożliwiające wyświetlanie komunikatów na ekranie blokady urządzenia z systemem iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ustawienia konfiguracji urządzenia udostępnianego umożliwiają określenie opcjonalnego tekstu wyświetlanego w oknie logowania i na ekranie blokady (np. komunikatu „W razie zgubienia zwróć do” i informacji dotyczących tagu zasobu). 

>[!IMPORTANT]
> Ta funkcja jest obsługiwana na nadzorowanych urządzeniach z systemem iOS w wersji 9.3 lub nowszej.

1. W bloku **Funkcje urządzenia** wybierz pozycję **Konfiguracja urządzenia udostępnianego (tylko nadzorowane)**.
2. W bloku **Konfiguracja urządzenia udostępnianego (tylko nadzorowane)** skonfiguruj następujące ustawienia:
    - **Informacje dotyczące tagu zasobu** — wprowadź informacje o tagu zasobu urządzenia. Na przykład: **Własność firmy Contoso Corp**. Wprowadzone informacje zostaną zastosowane do wszystkich urządzeń, do których zostanie przypisany ten profil.
    - **Przypis dolny ekranu blokady** — wprowadź informację, która może ułatwić zwrot urządzenia w przypadku jego utraty lub kradzieży. Na przykład: **W razie znalezienia proszę o telefon pod numer ...**.
3. Gdy skończysz, wybieraj przycisk **OK**, aż powrócisz do bloku **Utwórz profil**, a następnie wybierz pozycję **Utwórz**. 

