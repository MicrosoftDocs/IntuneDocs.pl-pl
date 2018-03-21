---
title: "Wyświetlanie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Wyświetl szczegóły urządzenia, w tym systemy operacyjne, miejsce do magazynowania, producenta, model i inne. Pobierz listę zainstalowanych aplikacji, sprawdź zasady zgodności, skonfiguruj program TeamViewer i nie tylko w usłudze Microsoft Intune na platformie Azure. Podobnie jak w przypadku wyświetlania spisu urządzeń, którymi zarządzasz."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 934ba0853f8bee851f7027580c276a9fff911b7f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="see-device-details-in-intune"></a>Wyświetlanie szczegółów urządzenia w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkcja **Urządzenia** udostępnia dodatkowe szczegóły na urządzeniach zarządzanych, w tym informacje o ich sprzęcie i zainstalowanych aplikacjach. 

W tym artykule przedstawiono sposób wyświetlania wszystkich urządzeń i ich właściwości w witrynie Azure Portal.

## <a name="view-your-device-details"></a>Wyświetlanie szczegółów urządzenia

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**. W obszarze Urządzenia masz kilka opcji:

  - **Przegląd** Pobranie informacji o zarejestrowanych urządzeniach i systemach operacyjnych działających na każdym z nich.
  - **Zarządzanie** — aby wyświetlić listę wszystkich zarządzanych urządzeń, wybierz opcję **Wszystkie urządzenia** lub **Urządzenia w usłudze Azure AD**.
    Wybierz jedno z urządzeń na liście. Ten krok powoduje otwarcie okienka <*nazwa urządzenia*> **Omówienie**, w którym można wybrać następujące opcje:
    - **Omówienie** — wyświetlanie nazwy urządzenia, jego właściciela, jeśli jest to urządzenie w modelu „Przynieś własne urządzenie” (BYOD), czasu jego zameldowania i innych informacji
    - **Sprzęt** — wyświetlanie ilości wolnego miejsca, modelu i producenta oraz dodatkowych szczegółowych informacji o urządzeniu
    - **Odnalezione aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione jako zainstalowane na urządzeniu przez usługę Intune
    - **Zgodność urządzenia** — wyświetla stan wszystkich zasad zgodności przypisanych do urządzenia
    - **Konfiguracja urządzenia** — wyświetla stan zgodności wszystkich zasad konfiguracji przypisanych do urządzenia
- **Monitoruj** — wybranie opcji **Akcje urządzenia** umożliwia wyświetlenie listy akcji urządzenia, które zostały wykonane na zarządzanych urządzeniach wraz z bieżącym stanem tych akcji. **Dzienniki inspekcji** wyświetlają stan różnych zadań.
- **Konfiguracja** > **Łącznik programu TeamViewer** — umożliwia skonfigurowanie administrowania zdalnego na urządzeniach przy użyciu oprogramowania TeamViewer. Aby uzyskać szczegółowe informacje, zobacz [Zapewnienie pomocy zdalnej dla urządzeń z systemem Android zarządzanych przy użyciu usługi Intune](device-profile-android-teamviewer.md).

Usługa Intune zbiera listę aplikacji tylko na urządzeniach należących do firmy. Aplikacje nie są sprawdzane na urządzeniach osobistych. W przypadku komputerów z systemem Windows 10 wyszczególniane są tylko aplikacje nowoczesne na urządzeniach należących do firmy. Usługa Intune nie zbiera informacji o aplikacjach Win32 na urządzeniu. W zależności od użycia operatora przez urządzenia nie wszystkie aplikacje mogą być zbierane.

## <a name="next-steps"></a>Następne kroki
Zobacz, co jeszcze możesz zrobić, aby [zarządzać urządzeniami](device-management.md) przy użyciu usługi Intune.
