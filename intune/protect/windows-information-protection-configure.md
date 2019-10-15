---
title: Ustawienia funkcji Windows Information Protection w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat ustawień usługi Intune, których można użyć do zarządzania funkcją Windows Information Protection.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 61c983bd850100a436ec1b15fab8a4a2be4ab7d4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728133"
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Jak skonfigurować ustawienia funkcji Windows Information Protection w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Wraz z coraz większą liczbą urządzeń należących do pracowników w przedsiębiorstwie zwiększa się również ryzyko przypadkowych przecieków danych za pośrednictwem aplikacji i usług, które są poza kontrolą przedsiębiorstwa, takich jak poczta e-mail, media społecznościowe i chmura publiczna. Ma to na przykład miejsce, gdy pracownik wysyła najnowsze obrazy inżynieryjne z osobistego konta e-mail, kopiuje i wkleja informacje o produkcie do tweeta lub zapisuje raport sprzedaży w toku do magazynu w chmurze publicznej.

Rozwiązanie **Windows Information Protection** ułatwia ochronę przed takimi potencjalnymi wyciekami danych, nie zakłócając przy tym w żaden sposób sposobu pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, które pracownik zabiera ze sobą do pracy — wszystko to bez konieczności wprowadzania zmian w środowisku lub innych aplikacjach.

Te zasady usługi Intune służą do zarządzania listą aplikacji chronionych przez rozwiązanie Windows Information Protection, lokalizacjami sieciowymi przedsiębiorstwa, poziomem ochrony i ustawieniami szyfrowania.

>[!NOTE]
> Aby używać aplikacji Portal firmy systemu Windows 10 z funkcją Windows Information Protection, należy dodać aplikację Portal firmy w trybie działania **Wyklucz** funkcji Windows Information Protection. 

Aby uzyskać więcej informacji, zobacz:
- [Protect your enterprise data using Windows Information Protection (Chronienie danych przedsiębiorstwa przy użyciu rozwiązania Windows Information Protection)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)
- [Create a Windows Information Protection (WIP) policy using the classic console for Microsoft Intune (Tworzenie zasad rozwiązania Windows Information Protection (WIP) przy użyciu konsoli klasycznej dla usługi Microsoft Intune)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Create a Windows Information Protection (WIP) policy with MDM using the Azure portal for Microsoft Intune (Tworzenie zasad rozwiązania Windows Information Protection (WIP) przy użyciu funkcji MDM w witrynie Azure Portal dla usługi Microsoft Intune)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Create a Windows Information Protection (WIP) policy with MAM using the Azure portal for Microsoft Intune (Tworzenie zasad rozwiązania Windows Information Protection (WIP) przy użyciu funkcji MAM w witrynie Azure Portal dla usługi Microsoft Intune)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)