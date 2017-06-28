---
title: "Tworzenie niestandardowych profilów sieci VPN w usłudze Microsoft Intune"
titleSuffix: Intune on Azure
description: "Konfiguracje niestandardowe umożliwiają tworzenie profilów sieci VPN w usłudze Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 11da0d31a9a00364a6105006c3e75b6bb6f2cb77
ms.contentlocale: pl-pl
ms.lasthandoff: 06/08/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Jak tworzyć niestandardowe profile sieci VPN w usłudze Microsoft Intune

## <a name="create-a-custom-configuration"></a>Tworzenie konfiguracji niestandardowej
Zasady konfiguracji niestandardowych usługi Intune umożliwiają tworzenie profilów sieci VPN dla następujących urządzeń:

* Urządzenia z systemem Android 4 i nowszym
* Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
* Urządzenia z systemem Windows Phone 8.1 lub nowszym
* Zarejestrowane urządzenia z systemem Windows 10 Desktop 
* Urządzenia z systemem Windows 10 Mobile

Ten typ zasad może być przydatny, gdy standardowe zasady sieci VPN usługi Intune nie zawierają odpowiednich ustawień.

## <a name="to-create-a-custom-configuration-policy"></a>Aby utworzyć niestandardowe zasady konfiguracji:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
4. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
5. W bloku profilów wybierz pozycję **Utwórz profil**.
6. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu sieci VPN.
7. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci VPN. Obecnie dla ustawień niestandardowych urządzenia można wybrać jedną z następujących platform:
    - **Android**
    - **iOS** (konfiguracja przy użyciu pliku wyeksportowanego z narzędzia Apple Configurator).
    - **macOS** (konfiguracja przy użyciu pliku wyeksportowanego z narzędzia Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. W bloku **Ustawienia niestandardowe OMA-URI** dla każdego ustawienia identyfikatora URI, które chcesz określić, wybierz przycisk **Dodaj**, podaj wymagane informacje, a następnie wybierz przycisk **OK**. Przykład:

   ![Okno dialogowe konfiguracji niestandardowej profilu VPN](./media/Intune_Add_VPN_URI.png)

4.  Po wprowadzeniu wszystkich potrzebnych ustawień identyfikatora URI wybierz przycisk **OK**, a następnie w bloku **Utwórz profil** wybierz przycisk **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).





