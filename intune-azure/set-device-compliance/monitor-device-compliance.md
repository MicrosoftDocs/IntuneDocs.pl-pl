---
title: "Jak monitorować zgodność urządzeń | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat monitorowania zgodności urządzeń."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: eb27002f449b3bbebb2a9b4ed780350c71eda881


---
# <a name="how-to-monitor-compliance-in-intune-azure-preview"></a>Jak monitorować zgodność urządzeń w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

W bloku **Przegląd** możesz wyświetlić podsumowanie stanu **profilów zgodności**.
Po kliknięciu poszczególnych wykresów możesz uzyskać dostęp do szczegółowych informacji. W przypadku skonfigurowania wielu profilów zgodności możesz także wyświetlić stan każdej zasady, przechodząc do bloku zasady, a następnie wybierając pozycję **Raporty** w sekcji **Zarządzaj**.  Poniżej przedstawiono szczegółowe informacje o raportach dostępnych dla wersji zapoznawczej.

##  <a name="device-compliance"></a>Zgodność urządzeń

Widok zbiorczy raportu zgodności urządzeń rozpoczyna się od prezentacji zagregowanych informacji o liczbie urządzeń przesyłających raporty i przynależnych do jednej z kategorii:

- **Zgodne**: urządzenie zostało niedawno poddane ocenie pod kątem zgodności i uznane za zgodne z ustawieniami wybranego profilu zgodności.
- **Niezgodne**: urządzenie zostało poddane ocenie i uznane za niezgodne.  Jeśli dla profilu skonfigurowano okres prolongaty, upłynął on, co spowodowało przełączenie urządzenia w stan niezgodności.
- **Okres prolongaty**: urządzenie zostało poddane ocenie i uznane za niezgodne. Jednak przed faktycznym oznaczeniem urządzenia jako niezgodnego musi upłynąć okres prolongaty.

Przechodząc do poszczególnych sekcji, możesz uzyskać szczegółowe informacje o konkretnych urządzeniach i użytkownikach.

## <a name="setting-compliance"></a>Zgodność ustawienia

Raport zgodności ustawienia zawiera szczegóły poszczególnych zgodnych ustawień, takie jak:

- Liczba urządzeń, które są niezgodne z ustawieniem.
- Platforma, do której ustawienie ma zastosowanie.

Możesz sprawdzić szczegóły każdego z ustawień, aby wyświetlić więcej informacji na temat profilów, w ramach których ustawienie zostało włączone, a także sprawdzić skonfigurowaną wartość ustawienia.



<!--HONumber=Feb17_HO1-->


