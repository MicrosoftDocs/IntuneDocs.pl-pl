---
title: Dane wysyłane do usługi Intune przez Google
titleSuffix: Microsoft Intune
description: Lista danych, które firma Google wysyła do usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 914ce3aa15099b7692d524dbfa368f99f0d092e8
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504493"
---
# <a name="data-google-sends-to-intune"></a>Dane wysyłane do usługi Intune przez Google

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gdy zarządzanie urządzeniami przedsiębiorstwa z systemem Android zostanie włączone na urządzeniu, usługa Microsoft Intune nawiązuje połączenie z firmą Google, a informacje o użytkowniku i urządzeniu będą udostępniane między usługą Intune i firmą Google. Zanim usługa Microsoft Intune będzie mogła nawiązać połączenie, musisz utworzyć konto Google.

Poniższa tabela zawiera dane, które firma Google wysyła do usługi Intune po włączeniu zarządzania urządzeniami na urządzeniu:


| Dane wysyłane do usługi Intune przez firmę Google | Szczegóły | Sposób użycia | Przykład |
|:---:|:---:|:---:|:---:|
| Dane przedsiębiorstwa | Identyfikatory przedsiębiorstwa dla klienta w firmie Google. | Łączy informacje o kliencie między usługą Intune i firmą Google. | **enterpriseId** — przykład: LC04eik8a6.<br>**Nazwa**. Nazwa administratora wprowadzona podczas konfigurowania przedsiębiorstwa z systemem Android. Przykład: Jan Kowalski.<br>**Adres e-mail administratora**. Adres YourAdmin@gmail.com użyty podczas konfigurowania przedsiębiorstwa używającego systemu Android. |
| Dane aplikacji | Dane związane z zarządzanymi aplikacjami ze Sklepu Play. | Określanie aplikacji docelowych dla użytkowników lub urządzeń jako dostępnych lub wymaganych. | **Nazwa aplikacji** — przykład: Aplikacja spisu magazynowego Contoso.<br>**Unikatowy identyfikator reprezentujący aplikację** — przykład: app:com.Contoso.Warehouse.InventoryTracking |
| Konto usługi | Unikatowe konto wewnętrznej usługi firmy Google do użycia w przypadku wywołań określonego klienta. | Używane na potrzeby wykonywania wywołań do firmy Google w imieniu klienta (w celu wyświetlania aplikacji, urządzeń i innych elementów) | **Nazwa** — przykład: InternalAccount@InternalService.com.<br>**Klucze** — przykład: ServiceAccountPassword |


Aby zaprzestać zarządzania urządzeniami przedsiębiorstwa z systemem Android za pomocą usługi Microsoft Intune i usunąć dane, musisz wyłączyć zarządzanie urządzeniem przedsiębiorstwa z systemem Android przez usługę Microsoft Intune i usunąć swoje konto Google. Zobacz informacje o koncie Google, aby dowiedzieć się, jak zarządzać kontem.


