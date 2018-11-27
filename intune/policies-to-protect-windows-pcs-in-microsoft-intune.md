---
title: Zasady ochrony komputerów z systemem Windows
titlesuffix: Microsoft Intune
description: Użyj tych zasad w celu zapewnienia bezpieczeństwa komputerom z systemem Windows, gdy są one zarządzane przez oprogramowanie klienckie usługi Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.openlocfilehash: 17d88b4e4da81f878e8bbdb5e4fde5ad2375dde7
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179870"
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a>Stosowanie zasad w celu ochrony komputerów z systemem Windows, na których działa oprogramowanie klienckie usługi Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Usługa Microsoft Intune oferuje trzy zasady, których można używać w celu zapewnienia bezpieczeństwa komputerom z systemem Windows zarządzanych przez [oprogramowanie klienckie usługi Intune](manage-windows-pcs-with-microsoft-intune.md).


## <a name="software-updates"></a>Aktualizacje oprogramowania

Usługa Intune ułatwia [aktualizowanie zarządzanych komputerów z systemem Windows](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md), ponieważ informuje o dostępności istotnych aktualizacji firmy Microsoft i innych firm. Następnie można zatwierdzić lub odrzucić te aktualizacje. Zatwierdzone aktualizacje zostaną automatycznie zainstalowane na wszystkich odpowiednich komputerach.

## <a name="windows-firewall"></a>Zapora systemu Windows

Zapora systemu Windows pomaga chronić komputery z systemem Windows przed hakerami, złośliwym oprogramowaniem i innymi zagrożeniami. Za pomocą usługi Intune możesz [zarządzać ustawieniami i funkcjami zapory systemu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) na wszystkich zarządzanych komputerach.

## <a name="endpoint-protection"></a>Ochrona punktu końcowego

Jednym z podstawowych zadań administratora IT jest [ochrona zarządzanych komputerów z systemem Windows przed złośliwym oprogramowaniem i wirusami](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md). Usługa Intune integruje się z programem Endpoint Protection i zapewnia ochronę w czasie rzeczywistym przed złośliwym oprogramowaniem, gwarantuje aktualność definicji złośliwego oprogramowania i automatycznie skanuje komputery. Ponadto program Endpoint Protection udostępnia narzędzia, które ułatwiają radzenie sobie z atakami złośliwego oprogramowania i ich monitorowanie.



### <a name="see-also"></a>Zobacz też
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
