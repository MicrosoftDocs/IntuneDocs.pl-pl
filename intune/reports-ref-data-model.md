---
title: Model danych magazynu danych | Microsoft Docs
description: "Magazyn danych usługi Intune każdego dnia próbkuje dane, aby przedstawić widok historyczny ciągle zmieniającego się środowiska mobilnego."
keywords: "Magazyn danych usługi Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f720d5f9dbf91d7f098a640d640f8f35136da4fc
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2017
---
# <a name="data-warehouse-data-model"></a>Model danych magazynu danych

Magazyn danych usługi Intune każdego dnia próbkuje dane, aby przedstawić widok historyczny ciągle zmieniającego się środowiska mobilnego.

Dane pobrane z dzierżawy są dodawane do magazynu danych. Magazyn to zestaw jednostek i relacji zrozumiałych dla typu pytań, które chcesz zadać. Możesz na przykład przejrzeć liczbę dziennych instalacji z ostatniego tygodnia aplikacji dla systemu Android opracowanej w firmie, aby sprawdzić, czy trend instalacji jest rosnący. Struktura magazynu danych umożliwia szczegółowy wgląd w środowisko mobilne. Z kolei narzędzia analityczne, takie jak usługa Microsoft Power BI, mogą przy użyciu modelu danych magazynu danych tworzyć wizualizacje i dynamiczne pulpity nawigacyjne.

W strukturze magazynu danych usługi Intune użyto modelu schematu gwiazdy. Schemat gwiazdy rozpoznaje fakty w wymiarze czasu. W kontekście modelu *fakt* to pomiar ilościowy, na przykład liczba urządzeń, liczba aplikacji lub czas rejestracji. W kontekście modelu *wymiar* to zestaw kategorii i ich hierarchiczne relacje. Na przykład dni są pogrupowane w miesiące, a miesiące w lata. Model schematu gwiazdy jest zoptymalizowany pod kątem elastyczności i analizy danych, aby umożliwić tworzenie raportów potrzebnych do zrozumienia ewoluującego środowiska mobilnego.

Magazyn uwidacznia dane w następujących kategoriach wysokiego poziomu:
  -  Aplikacje z włączoną ochroną aplikacji i ich użycie
  -  Zarejestrowane urządzenia, właściwości i spis
  -  Spis aplikacji i oprogramowania
  -  Zasady zgodności i konfiguracji urządzenia

**Zestawy jednostek modelu danych**

W modelu danych zestawy jednostek są nazywane kolekcjami jednostek. Te zestawy zawierają jednostki definiujące dane zebrane w modelu. Każdy zestaw jednostek zapewnia punkt dostępu do modelu danych magazynu danych. Możesz znaleźć szczegółowe informacje dotyczące następujących kategorii jednostek:

  -  [Aplikacja](reports-ref-application.md)
  -  [Data](reports-ref-date.md)
  -  [Urządzenia](reports-ref-devices.md)
  -  [Rozszerzenie do zarządzania usługi Intune](reports-ref-intunemanagementextension.md)
  -  [Zasady](reports-ref-policy.md)
  -  [Zarządzanie aplikacjami mobilnymi (MAM)](reports-ref-mobile-app-management.md)
  -  [User](reports-ref-user.md)
  -  [Skojarzenie urządzenia użytkownika](reports-ref-user-device.md)