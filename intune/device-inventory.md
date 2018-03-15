---
title: "Wyświetlanie spisu urządzeń usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak wyświetlić urządzenia zarządzane za pomocą usługi Intune oraz uzyskaj informacje dotyczące sprzętu i zainstalowanych aplikacji."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 772e2b1380626384d618e653b90b31a1f421eb72
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-view-intune-device-inventory"></a>Jak wyświetlać spis urządzeń usługi Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pakiet roboczy **Urządzenia** zawiera szczegółowe informacje dotyczące zarządzanych urządzeń, m.in. możliwości sprzętu oraz zainstalowanych na nim aplikacji. 

Aby wyświetlić spis urządzeń:

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.

Wybierz jedną z następujących opcji:

- **Przegląd** Pobranie informacji o zarejestrowanych urządzeniach i systemach operacyjnych działających na każdym z nich.
- **Zarządzanie** — opcja **Wszystkie urządzenia** umożliwia wyświetlenie listy wszystkich zarządzanych urządzeń.
    Wybierz jedno z urządzeń na liście, aby otworzyć blok <*nazwa urządzenia*> **Przegląd**, w którym można wybrać jedną z opcji:
    - **Przegląd** — wyświetlenie ogólnych informacji dotyczących urządzenia, w tym informacji o jego nazwie, właścicielu, czy jest to urządzenie BYOD, kiedy zostało zewidencjonowane itd.
    - **Sprzęt** — wyświetlenie szczegółowych informacji dotyczących urządzenia, w tym ilości wolnego miejsca, modelu i producenta oraz innych danych.
    - **Odnalezione aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione na urządzeniu przez usługę Intune.
    - **Zgodność urządzenia** — wyświetla stan wszystkich zasad zgodności przypisanych do urządzenia.
    - **Konfiguracja urządzenia** — wyświetla stan wszystkich zasad konfiguracji przypisanych do urządzenia.
- **Monitoruj** — wybranie opcji **Akcje urządzenia** umożliwia wyświetlenie listy akcji urządzenia, które zostały wykonane na zarządzanych urządzeniach wraz z bieżącym stanem tych akcji.
- **Konfiguracja** > **Łącznik programu TeamViewer** — umożliwia skonfigurowanie administrowania zdalnego na urządzeniach przy użyciu oprogramowania TeamViewer. Aby uzyskać szczegółowe informacje, zobacz [Zapewnienie pomocy zdalnej dla urządzeń z systemem Android zarządzanych przy użyciu usługi Intune](/intune/device-profile-android-teamviewer).

Usługa Intune zbiera spis aplikacji tylko na urządzeniach należących do firmy. Aplikacje nie są spisywane na urządzeniach osobistych. W przypadku komputerów z systemem Windows 10 na urządzeniach należących do firmy zbierany jest tylko spis aplikacji nowoczesnych. Usługa Intune nie zbiera informacji o aplikacjach Win32 na urządzeniu. Zależnie od operatora używanego dla urządzeń mogą nie być zbierane wszystkie pozycje spisu.
