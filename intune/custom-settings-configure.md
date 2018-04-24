---
title: Korzystanie z niestandardowych ustawień urządzenia w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu umożliwiającego korzystanie z niestandardowych ustawień dla urządzeń z systemami Windows, Android i iOS za pomocą usługi Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce7c263435f92a041b93dc5d34ffa912c6fa87fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Tworzenie profilu z ustawieniami niestandardowymi w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune może nie mieć wbudowanych wszystkich ustawień, których potrzebujesz. Możesz też zechcieć skorzystać z ustawień dostępnych w innych profilach urządzeń. Aby dodać te ustawienia, utwórz profil urządzenia i skonfiguruj go z użyciem niestandardowych ustawień urządzenia.

W tym artykule wymieniono podstawowe kroki tworzenia profilu z ustawieniami niestandardowymi. Zawiera on również linki do szczegółowych opisów tworzenia ustawień niestandardowych dla różnych platform.

## <a name="custom-settings-on-different-platforms"></a>Ustawienia niestandardowe na różnych platformach
Konfiguracja ustawień niestandardowych przebiega różnie w zależności od platformy. Na przykład w celu sterowania funkcjami urządzeń z systemami Android i Windows można określić wartości Open Mobile Alliance Uniform Resource Identifier (OMA-URI). W przypadku urządzeń firmy Apple można zaimportować plik utworzony za pomocą programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. W obszarze **Konfiguracja urządzeń** wybierz pozycję **Profile**, a następnie wybierz pozycję **Utwórz profil**.
4. Wprowadź **nazwę** i **opis** profilu niestandardowego.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której mają zostać zastosowane ustawienia niestandardowe. Można wybrać dowolną z następujących platform:

    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**

6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Poniższe linki dają dostęp do większej ilości szczegółów na temat niestandardowych ustawień dla każdej platformy:

    - [Ustawienia systemu Android](custom-settings-android.md)
    - [Ustawienia systemu iOS](custom-settings-ios.md)
    - [macOS settings](custom-settings-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Windows 10 settings](custom-settings-windows-10.md) (Ustawienia systemu Windows 10)
    - [Ustawienia systemu Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Ustawienia programu Android for Work](custom-settings-android-for-work.md)

8. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na liście profilów. Aby przypisać ten profil do grup, zobacz [Jak przypisywać profile urządzeń](device-profile-assign.md).
