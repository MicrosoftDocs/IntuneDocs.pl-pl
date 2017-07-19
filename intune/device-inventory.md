---
title: "Wyświetlanie spisu urządzeń usługi Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak wyświetlić urządzenia zarządzane za pomocą usługi Intune oraz uzyskaj informacje dotyczące sprzętu i zainstalowanych aplikacji."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dae92c117bcf8a4a8ff133ed613f9f77ea0c07c2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-view-intune-device-inventory"></a>Jak wyświetlać spis urządzeń usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pakiet roboczy **Urządzenia** zawiera szczegółowe informacje dotyczące zarządzanych urządzeń, m.in. możliwości sprzętu oraz zainstalowanych na nim aplikacji. 

Aby wyświetlić spis urządzeń:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.

Wybierz jedną z następujących opcji:

- **Przegląd** Pobranie informacji o zarejestrowanych urządzeniach i systemach operacyjnych działających na każdym z nich.
- **Zarządzanie** — opcja **Wszystkie urządzenia** umożliwia wyświetlenie listy wszystkich zarządzanych urządzeń.
    Wybierz jedno z urządzeń na liście, aby otworzyć blok <*nazwa urządzenia*> **Przegląd**, w którym można wybrać jedną z opcji:
    - **Przegląd** — wyświetlenie ogólnych informacji dotyczących urządzenia, w tym informacji o jego nazwie, właścicielu, czy jest to urządzenie BYOD, kiedy zostało zewidencjonowane itd.
    ![Przegląd urządzenia](./media/device-overview.png)
    - **Sprzęt** — wyświetlenie szczegółowych informacji dotyczących urządzenia, w tym ilości wolnego miejsca, modelu i producenta oraz innych danych.
    ![Spis sprzętu zarządzanego urządzenia](./media/hardware-inventory.png)
    - **Odnalezione aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione na urządzeniu przez usługę Intune.
    ![Węzeł odnalezionych aplikacji](./media/detected-applications.png)
    - **Zgodność urządzenia** — wyświetla stan wszystkich zasad zgodności przypisanych do urządzenia.
    - **Konfiguracja urządzenia** — wyświetla stan wszystkich zasad konfiguracji przypisanych do urządzenia.
- **Monitoruj** Wybranie opcji **Akcje urządzenia** umożliwia wyświetlenie listy akcji urządzenia, które zostały wykonane na zarządzanych urządzeniach wraz z bieżącym stanem tych akcji.
- **Konfiguracja** > **Łącznik programu TeamViewer** — umożliwia skonfigurowanie administrowania zdalnego na urządzeniach przy użyciu oprogramowania TeamViewer. Aby uzyskać szczegółowe informacje, zobacz [Zapewnienie pomocy zdalnej dla urządzeń z systemem Android zarządzanych przy użyciu usługi Intune](/intune/device-profile-android-teamviewer).


