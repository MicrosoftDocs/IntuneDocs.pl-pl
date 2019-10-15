---
title: Zasady ochrony komputerów z systemem Windows
titleSuffix: Microsoft Intune
description: Użyj tych zasad w celu zapewnienia bezpieczeństwa komputerom z systemem Windows, gdy są one zarządzane przez oprogramowanie klienckie usługi Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2019
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c4ddb5708b6ea43a1054ca07893eb8a09b5ff29
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736211"
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a>Stosowanie zasad w celu ochrony komputerów z systemem Windows, na których działa oprogramowanie klienckie usługi Intune

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

Usługa Microsoft Intune oferuje trzy zasady, których można używać w celu zapewnienia bezpieczeństwa komputerom z systemem Windows zarządzanych przez [oprogramowanie klienckie usługi Intune](../manage-windows-pcs-with-microsoft-intune.md).


## <a name="software-updates"></a>Aktualizacje oprogramowania

Usługa Intune ułatwia [aktualizowanie zarządzanych komputerów z systemem Windows](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md), ponieważ informuje o dostępności istotnych aktualizacji firmy Microsoft i innych firm. Następnie można zatwierdzić lub odrzucić te aktualizacje. Zatwierdzone aktualizacje zostaną automatycznie zainstalowane na wszystkich odpowiednich komputerach.

## <a name="windows-firewall"></a>Zapora systemu Windows

Zapora systemu Windows pomaga chronić komputery z systemem Windows przed hakerami, złośliwym oprogramowaniem i innymi zagrożeniami. Za pomocą usługi Intune możesz [zarządzać ustawieniami i funkcjami zapory systemu Windows](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) na wszystkich zarządzanych komputerach.

## <a name="endpoint-protection"></a>Ochrona punktu końcowego

Jednym z podstawowych zadań administratora IT jest [ochrona zarządzanych komputerów z systemem Windows przed złośliwym oprogramowaniem i wirusami](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md). Usługa Intune integruje się z programem Endpoint Protection i zapewnia ochronę w czasie rzeczywistym przed złośliwym oprogramowaniem, gwarantuje aktualność definicji złośliwego oprogramowania i automatycznie skanuje komputery. Ponadto program Endpoint Protection udostępnia narzędzia, które ułatwiają radzenie sobie z atakami złośliwego oprogramowania i ich monitorowanie.

## <a name="see-also"></a>Zobacz także

[Common questions, issues and resolutions with device policies and profiles (Typowe pytania, problemy i rozwiązania związane z zasadami i profilami urządzeń)](../configuration/device-profile-troubleshoot.md)