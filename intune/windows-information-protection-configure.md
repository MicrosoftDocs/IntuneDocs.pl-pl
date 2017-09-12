---
title: "Konfigurowanie ustawienia funkcji Windows Information Protection — usługa Intune"
titleSuffix: Azure portal
description: "Informacje o ustawieniach usługi Intune, których można użyć do zarządzania funkcją Windows Information Protection."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9eab6d6acae7965b319f4aa74aba2f8f3401d801
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Jak skonfigurować ustawienia funkcji Windows Information Protection w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wraz z coraz większą liczbą urządzeń należących do pracowników w przedsiębiorstwie zwiększa się również ryzyko przypadkowych przecieków danych za pośrednictwem aplikacji i usług, które są poza kontrolą przedsiębiorstwa, takich jak poczta e-mail, media społecznościowe i chmura publiczna. Ma to na przykład miejsce, gdy pracownik wysyła najnowsze obrazy inżynieryjne z osobistego konta e-mail, kopiuje i wkleja informacje o produkcie do tweeta lub zapisuje raport sprzedaży w toku do magazynu w chmurze publicznej.

Rozwiązanie **Windows Information Protection** ułatwia ochronę przed takimi potencjalnymi wyciekami danych, nie zakłócając przy tym w żaden sposób sposobu pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, które pracownik zabiera ze sobą do pracy — wszystko to bez konieczności wprowadzania zmian w środowisku lub innych aplikacjach.

Te zasady usługi Intune służą do zarządzania listą aplikacji chronionych przez rozwiązanie Windows Information Protection, lokalizacjami sieciowymi przedsiębiorstwa, poziomem ochrony i ustawieniami szyfrowania.

>[!NOTE]
> Aby używać aplikacji Portal firmy systemu Windows 10 z funkcją Windows Information Protection, należy dodać aplikację Portal firmy w trybie działania **Wyklucz** funkcji Windows Information Protection. 

### <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji, zobacz [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Chroń dane przedsiębiorstwa przy użyciu rozwiązania Windows Information Protection).
