---
title: "Monitorowanie zgodności urządzenia"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e073ca318d7db23239fc68b79718198dbee54b6e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-monitor-device-compliance-in-intune-azure-preview"></a>Monitorowanie zgodności urządzeń w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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

Możesz sprawdzić szczegóły każdego z ustawień, aby wyświetlić więcej informacji na temat profilów, w ramach których te ustawienia zostały włączone, a także sprawdzić wartość ustawienia.

