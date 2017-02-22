---
title: "Tworzenie profilów konfiguracji urządzeń usługi Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: wskazówki dotyczące tworzenia profilów konfiguracji urządzeń usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 6c6ac8112a6b6413df635607a24d0d06466c0b88


---

# <a name="how-to-create-device-configuration-profiles"></a>Tworzenie profilów konfiguracji urządzeń 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


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
        -  [Ustawienia ograniczeń dotyczących urządzeń](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [Ustawienia poczty e-mail](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [Ustawienia sieci VPN](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Ustawienia sieci Wi-Fi](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Ustawienia uaktualniania wersji systemu Windows 10](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Ustawienia certyfikatów](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Ustawienia usługi Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Ustawienia rozwiązań dla edukacji](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Ustawienia niestandardowe](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Utwórz profil urządzenia](./media/create-device-profile.png)
4. Po zakończeniu procesu konfiguracji ustawień wybierz w bloku **Utwórz profil** polecenie **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).


### <a name="next-steps"></a>Następne kroki
Informacje dotyczące sposobu przypisywania profilów urządzeń znajdują się w artykule [How to assign device profiles with Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles) (Jak przypisywać profile urządzeń przy użyciu usługi Microsoft Intune).



<!--HONumber=Feb17_HO1-->


