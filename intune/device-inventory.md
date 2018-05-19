---
title: Wyświetlanie szczegółów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetl szczegóły urządzeń, w tym system operacyjny, miejsce do magazynowania, producenta i model. Pobierz listę zainstalowanych aplikacji, sprawdź zasady zgodności i skonfiguruj program TeamViewer za pomocą usługi Microsoft Intune na platformie Azure. Podobnie jak w przypadku wyświetlania spisu urządzeń, którymi zarządzasz.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f66c0695c7e3d1f4bb7a5ca3abceeb13f6af41f2
ms.sourcegitcommit: 3c4ea8d6809a63042705b5ed4f25ba80f522070e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2018
---
# <a name="see-device-details-in-intune"></a>Wyświetlanie szczegółów urządzenia w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Funkcja **Urządzenia** udostępnia dodatkowe szczegóły dotyczące zarządzanych urządzeń, w tym informacje o ich sprzęcie i zainstalowanych aplikacjach.

W tym artykule przedstawiono sposób wyświetlania wszystkich urządzeń i ich właściwości w witrynie Azure Portal.

## <a name="view-the-device-details"></a>Wyświetlanie szczegółów urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**, a następnie wybierz jedno z wymienionych na liście urządzeń, aby otworzyć jego szczegóły:

   - **Omówienie** zawiera nazwę urządzenia oraz listę niektórych kluczowych właściwości urządzenia, w tym informację o tym, czy jest to urządzenie BYOD, kiedy zostało zaewidencjonowane itp. Wybierz opcję **Więcej**, aby wykonać następujące czynności:
     - Usuwanie danych firmy
     - Usuwanie urządzenia
     - Zdalne blokowanie urządzenia
     - Wymazywanie
     - Uruchamianie sesji pomocy zdalnej
   - Za pomocą opcji **Właściwości** możesz przypisać [utworzoną kategorię urządzeń](device-group-mapping.md) i zmienić własność urządzenia na urządzenie osobiste lub urządzenie firmowe.
   - **Sprzęt** — zawiera wiele szczegółów dotyczących urządzenia, w tym identyfikator urządzenia, system operacyjny wraz z wersją, miejsce do magazynowania, model i producenta, ustawienia dostępu warunkowego oraz inne informacje.
   - **Odnalezione aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione jako zainstalowane na urządzeniu przez usługę Intune, wraz z wersjami aplikacji. Możesz też **wyeksportować** listę aplikacji do pliku CSV.
   - **Zgodność urządzenia** — wyświetla wszystkie przypisane zasady zgodności oraz informację o tym, czy urządzenie jest zgodne.
   - **Konfiguracja urządzenia** — zawiera wszystkie zasady konfiguracji urządzeń przypisane do urządzenia oraz informację o tym, czy wdrożenie zasad powiodło się.

Usługa Intune zbiera listę aplikacji tylko na urządzeniach należących do firmy. Aplikacje nie są sprawdzane na urządzeniach osobistych. W przypadku komputerów z systemem Windows 10 wyszczególniane są tylko aplikacje nowoczesne na urządzeniach należących do firmy. Usługa Intune nie zbiera informacji o aplikacjach Win32 na urządzeniu. W zależności od operatora danego urządzenia mogą nie zostać zebrane wszystkie aplikacje.

|Platforma|Urządzenia osobiste|Urządzenia należące do firmy|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (bez klienta programu Configuration Manager)|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|
|Windows 8.1 (bez klienta programu Configuration Manager)|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|  
|Windows Phone 8|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|  
|Windows RT|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|  
|iOS|Tylko aplikacje zarządzane|Wszystkie aplikacje zainstalowane na urządzeniu|
|macOS|Wszystkie aplikacje zainstalowane na urządzeniu|Wszystkie aplikacje zainstalowane na urządzeniu|  
|Android|Tylko aplikacje zarządzane|Wszystkie aplikacje zainstalowane na urządzeniu|  

## <a name="next-steps"></a>Następne kroki
Zobacz, co jeszcze możesz zrobić, aby [zarządzać urządzeniami](device-management.md) przy użyciu usługi Intune.