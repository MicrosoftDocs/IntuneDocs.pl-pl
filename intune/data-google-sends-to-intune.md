---
title: Dane wysyłane do usługi Intune przez Google
titleSuffix: Microsoft Intune
description: Lista danych, które firma Google wysyła do usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 368205b63fcd360adf66f964c6cae087f6da3dfc
ms.sourcegitcommit: 2162ed46d939b4a9b85fa4e7e9943f2fb5948f1e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2018
---
# <a name="data-google-sends-to-intune"></a>Dane wysyłane do usługi Intune przez Google

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gdy zarządzanie urządzeniami przedsiębiorstwa z systemem Android zostanie włączone na urządzeniu, usługa Microsoft Intune nawiązuje połączenie z firmą Google, a informacje o użytkowniku i urządzeniu będą udostępniane między usługą Intune i firmą Google. Zanim usługa Microsoft Intune będzie mogła nawiązać połączenie, musisz utworzyć konto Google.

Poniższa tabela zawiera dane, które firma Google wysyła do usługi Intune po włączeniu zarządzania urządzeniami na urządzeniu:


| Dane wysyłane do usługi Intune przez firmę Google | Szczegóły | Służy do | Przykład |
|:---:|:---:|:---:|:---:|
| Dane przedsiębiorstwa | Identyfikatory przedsiębiorstwa dla klienta w firmie Google. | Łączy informacje o kliencie między usługą Intune i firmą Google. | **enterpriseId** — przykład: LC04eik8a6.<br>**Nazwa**. Nazwa administratora wprowadzona podczas konfigurowania przedsiębiorstwa z systemem Android. Przykład: Jan Kowalski.<br>**Adres e-mail administratora**. Adres YourAdmin@gmail.com użyty podczas konfigurowania przedsiębiorstwa używającego systemu Android. |
| Dane aplikacji | Dane związane z zarządzanymi aplikacjami ze Sklepu Play. | Określanie aplikacji docelowych dla użytkowników lub urządzeń jako dostępnych lub wymaganych. | **Nazwa aplikacji** — przykład: Aplikacja spisu magazynowego Contoso.<br>**Unikatowy identyfikator reprezentujący aplikację** — przykład: app:com.Contoso.Warehouse.InventoryTracking |
| Konto usługi | Unikatowe konto wewnętrznej usługi firmy Google do użycia w przypadku wywołań określonego klienta. | Używane na potrzeby wykonywania wywołań do firmy Google w imieniu klienta (w celu wyświetlania aplikacji, urządzeń i innych elementów) | **Nazwa** — przykład: InternalAccount@InternalService.com.<br>**Klucze** — przykład: ServiceAccountPassword |


Aby zaprzestać zarządzania urządzeniami przedsiębiorstwa z systemem Android za pomocą usługi Microsoft Intune i usunąć dane, musisz wyłączyć zarządzanie urządzeniem przedsiębiorstwa z systemem Android przez usługę Microsoft Intune i usunąć swoje konto Google. Zobacz informacje o koncie Google, aby dowiedzieć się, jak zarządzać kontem.


