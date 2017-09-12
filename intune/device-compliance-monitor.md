---
title: "Monitorowanie zgodności urządzenia"
titlesuffix: Azure portal
description: "Informacje dotyczące monitorowania zgodności urządzenia."
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
ms.openlocfilehash: 65b156923a38d9b3d976604819ede300f063a88b
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-monitor-device-compliance-in-intune"></a>Monitorowanie zgodności urządzenia w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W bloku **Przegląd** możesz wyświetlić podsumowanie stanu **profilów zgodności**.
Po kliknięciu poszczególnych wykresów możesz uzyskać dostęp do szczegółowych informacji. W przypadku skonfigurowania wielu profilów zgodności możesz także wyświetlić stan każdej zasady, przechodząc do bloku zasady, a następnie wybierając pozycję **Raporty** w sekcji **Zarządzaj**.  Poniżej przedstawiono szczegółowe informacje o dostępnych raportach.

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
