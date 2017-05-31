---
title: "Tworzenie profilów konfiguracji urządzeń w usłudze Intune| Wersja zapoznawcza usługi Intune Azure"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: wskazówki dotyczące tworzenia profilów konfiguracji urządzeń usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a719b3f53076a55f1e888a9ddf8e98c7074dd25f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Jak utworzyć profile konfiguracji urządzeń w usłudze Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
2. W bloku z listą profilów wybierz pozycję **Utwórz profil**.
3. W bloku **Utwórz profil** określ następujące pozycje:
    - **Nazwa** — wprowadź opisową nazwę nowego profilu.
    - **Opis** — wprowadź opcjonalny opis profilu.
    - **Platforma** — wybierz typ platformy dla profilu, który ma zostać utworzony.
    - **Typ profilu** — wybierz typ profilu, który ma zostać utworzony. Lista dostępnych typów różni się w zależności od wybranej platformy.
    - **Ustawienia** — zapoznaj się z poniższymi tematami zawierającymi informacje o ustawieniach dla poszczególnych typów profilów:
        -  [Ustawienia funkcji urządzeń](device-features-configure.md)
        -  [Ustawienia ograniczeń dotyczących urządzeń](device-restrictions-configure.md)
        -  [Ustawienia poczty e-mail](email-settings-configure.md)
        -  [Ustawienia sieci VPN](vpn-settings-configure.md)
        -  [Ustawienia sieci Wi-Fi](wi-fi-settings-configure.md)
        -  [Ustawienia uaktualniania wersji systemu Windows 10](edition-upgrade-configure-windows-10.md)
        -  [Ustawienia certyfikatów](certificates-configure.md)
        -  [Ustawienia usługi Windows Information Protection](windows-information-protection-configure.md)
        -  [Ustawienia rozwiązań dla edukacji](education-settings-configure.md)
        -  [Ustawienia niestandardowe](custom-settings-configure.md)

    ![Utwórz profil urządzenia](./media/create-device-profile.png)
4. Po zakończeniu procesu konfiguracji ustawień wybierz w bloku **Utwórz profil** polecenie **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).


### <a name="next-steps"></a>Następne kroki
Informacje dotyczące sposobu przypisywania profilów urządzeń znajdują się w artykule [How to assign device profiles with Microsoft Intune](device-profile-assign.md) (Jak przypisywać profile urządzeń przy użyciu usługi Microsoft Intune).

