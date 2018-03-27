---
title: Włączanie usługi Lookout MTP w usłudze Intune
description: Włącz ochronę przed zagrożeniami mobilnymi w konsoli administracyjnej usługi Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99c9952b8df3e9b4b1992cbc45366a5ceed458aa
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Włączanie połączenia z usługą Lookout MTD w portalu klasycznym usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Aby włączyć połączenie z usługą Lookout Mobile Threat Defense (MTD) w usłudze Intune, należy wcześniej skonfigurować łącznik usługi Intune w konsoli usługi Lookout.  Jeśli jeszcze tego nie zrobiono, należy [skonfigurować subskrypcję usługi Lookout Mobile Threat Defense](setup-your-lookout-mtd-subscription.md).

Aby włączyć połączenie z usługą Lookout MTP w usłudze Intune, na stronie **Administracja** w [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Integracja z usługami innych firm**. Wybierz pozycję **Stan usługi Lookout** i włącz opcję **Synchronizacja z usługą MTP** za pomocą przycisku przełączania.

![zrzut ekranu przedstawiający stronę synchronizacji usługi Lookout z wyróżnionym przyciskiem przełączania włączania](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> **Konieczne jest** skonfigurowanie aplikacji Lookout for Work przed utworzeniem reguł zasad zgodności i skonfigurowaniem dostępu warunkowego. Zapewni to, że dana aplikacja będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

Wykonanie tej czynności oznacza zakończenie konfigurowania integracji usług Intune i Lookout w konsoli administratora usługi Intune.  Następne kilka kroków dotyczących implementacji tego rozwiązania obejmuje wdrażanie zasad [aplikacji Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Następne kroki
[Konfigurowanie aplikacji Lookout for Work](/intune-classic/deploy-use/device-threat-protection-apps)
