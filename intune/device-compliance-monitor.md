---
title: Monitorowanie zgodności urządzenia
titlesuffix: Microsoft Intune
description: Informacje dotyczące monitorowania zgodności urządzenia.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b6c86b8f365f5ac3e65e91725e9fcd29ccd9ef58
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187027"
---
# <a name="monitor-device-compliance-in-intune"></a>Monitorowanie zgodności urządzenia w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W bloku **Przegląd** możesz wyświetlić podsumowanie stanu **profilów zgodności**.
Po kliknięciu poszczególnych wykresów możesz uzyskać dostęp do szczegółowych informacji. Jeśli skonfigurowano wiele profilów zgodności, stan zasad można wyświetlić w bloku zasad w obszarze **Zarządzaj** > **Raporty**.

##  <a name="device-compliance"></a>Zgodność urządzeń

Widok zbiorczy raportu zgodności urządzeń zawiera listę zagregowanych informacji o liczbie urządzeń przesyłających raporty w jednym z następujących stanów:

- **Zgodne**: urządzenie zostało niedawno poddane ocenie i jest zgodne z określonymi ustawieniami profilu zgodności.
- **Niezgodne**: urządzenie zostało poddane ocenie i uznane za niezgodne.  Jeśli dla profilu skonfigurowano okres prolongaty, upłynął on, co spowodowało przełączenie urządzenia w stan niezgodności.
- **Okres prolongaty**: urządzenie zostało poddane ocenie i uznane za niezgodne. Jednak przed oznaczeniem urządzenia jako niezgodnego musi upłynąć okres prolongaty.

Przechodząc do poszczególnych sekcji, możesz uzyskać szczegółowe informacje o konkretnych urządzeniach i użytkownikach.

## <a name="setting-compliance"></a>Zgodność ustawienia

Raport zgodności ustawienia zawiera szczegóły każdego ustawienia zgodności, takie jak:

- Liczba urządzeń, które są niezgodne z ustawieniem.
- Platforma, do której ustawienie ma zastosowanie.

Możesz sprawdzić szczegóły każdego z ustawień, aby wyświetlić więcej informacji na temat profilów, w ramach których te ustawienia zostały włączone, a także sprawdzić wartość ustawienia.
