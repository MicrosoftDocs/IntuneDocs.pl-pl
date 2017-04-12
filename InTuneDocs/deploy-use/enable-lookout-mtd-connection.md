---
title: "Włączanie aplikacji usługi Lookout MTP w usłudze Intune | Microsoft Docs"
description: "Włącz ochronę przed zagrożeniami mobilnymi w konsoli administracyjnej usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: d2a10a0e14d9b0b4d2e3f8e2715b47d984e5aa66
ms.lasthandoff: 03/21/2017


---

# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>Włączanie połączenia z usługą Lookout MTD w klasycznej konsoli usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Aby włączyć połączenie z usługą Lookout Mobile Threat Defense (MTD) w usłudze Intune, należy wcześniej skonfigurować łącznik usługi Intune w konsoli usługi Lookout.  Jeśli jeszcze tego nie zrobiono, należy [skonfigurować subskrypcję usługi Lookout Mobile Threat Defense](set-up-your-subscription-with-lookout-mtp.md).

Aby włączyć połączenie z usługą Lookout MTP w usłudze Intune, na stronie **Administracja** w [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Integracja z usługami innych firm**. Wybierz pozycję **Stan usługi Lookout** i włącz opcję **Synchronizacja z usługą MTP** za pomocą przycisku przełączania.

![zrzut ekranu przedstawiający stronę synchronizacji usługi Lookout z wyróżnionym przyciskiem przełączania włączania](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> **Konieczne jest** skonfigurowanie aplikacji Lookout for Work przed utworzeniem reguł zasad zgodności i skonfigurowaniem dostępu warunkowego. Zapewni to, że dana aplikacja będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

Wykonanie tej czynności oznacza zakończenie konfigurowania integracji usług Intune i Lookout w konsoli administratora usługi Intune.  Następne kilka kroków dotyczących implementacji tego rozwiązania obejmuje wdrażanie [aplikacji Lookout for Work](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps) i konfigurowanie zasad [zgodności](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Następne kroki
[Konfigurowanie aplikacji Lookout for Work](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)

