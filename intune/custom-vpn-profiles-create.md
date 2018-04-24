---
title: Tworzenie niestandardowych profilów sieci VPN w usłudze Microsoft Intune
titleSuffix: ''
description: Konfiguracje niestandardowe umożliwiają tworzenie profilów sieci VPN w usłudze Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Jak tworzyć niestandardowe profile sieci VPN w usłudze Microsoft Intune

Zasady konfiguracji niestandardowych usługi Intune umożliwiają tworzenie profilów sieci VPN dla następujących platform:

* System Android 4 lub nowszy
* Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
* System Windows Phone 8.1 lub nowszy
* Zarejestrowane urządzenia z systemem Windows 10 Desktop 
* Windows 10 Mobile

Ten typ zasad może być przydatny, gdy standardowe zasady sieci VPN usługi Intune nie zawierają ustawień, których chcesz użyć.

## <a name="to-create-a-custom-configuration-policy"></a>Aby utworzyć niestandardowe zasady konfiguracji:

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
5. W okienku profilów wybierz pozycję **Utwórz profil**.
6. W okienku **Tworzenie profilu** wprowadź wartość w polach **Nazwa** i **Opis** dotyczących profilu sieci VPN.
7. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci VPN. Obecnie dla ustawień niestandardowych urządzenia można wybrać jedną z następujących platform:
    - **Android**
    - **Android for Work**
    - **iOS** (konfiguracja przy użyciu pliku wyeksportowanego z narzędzia Apple Configurator).
    - **macOS** (konfiguracja przy użyciu pliku wyeksportowanego z narzędzia Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. W okienku **Ustawienia niestandardowe OMA-URI** dla każdego ustawienia identyfikatora URI, które chcesz określić, wybierz przycisk **Dodaj**, podaj wymagane informacje, a następnie wybierz przycisk **OK**. Przykład:

   ![Okno dialogowe konfiguracji niestandardowej profilu VPN](./media/Intune_Add_VPN_URI.png)

4.  Po wprowadzeniu wszystkich potrzebnych ustawień identyfikatora URI wybierz przycisk **OK**, a następnie w okienku **Tworzenie profilu** wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).




