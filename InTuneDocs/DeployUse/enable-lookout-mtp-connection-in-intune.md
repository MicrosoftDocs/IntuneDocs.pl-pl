---
title: "Włączanie aplikacji usługi Lookout MTP w usłudze Intune | Microsoft Intune"
description: "Włącz ochronę przed zagrożeniami mobilnymi w konsoli administracyjnej usługi Intune."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ceaeba74f8671caf4125252fce02fd06752c3fe8
ms.openlocfilehash: 2052aca24baa752bc4fad3bd7a75f8efa109e9e9


---

# Włączanie połączenia z usługą Lookout MTP w konsoli administracyjnej usługi Intune
W tym temacie opisano sposób włączania połączenia z usługą MTP w usłudze Intune. Łącznik usługi Intune w konsoli usługi Lookout powinien zostać skonfigurowany przed wykonaniem tego kroku.  Jeśli jeszcze tego nie zrobiono, wykonaj kroki opisane w temacie [Konfigurowanie subskrypcji przy użyciu aplikacji Lookout do ochrony urządzeń przenośnych przed zagrożeniami](set-up-your-subscription-with-lookout-mtp.md).

Aby włączyć połączenie z usługą Lookout MTP w usłudze Intune, na stronie **Administracja** w [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Integracja z usługami innych firm**. Wybierz pozycję **Stan usługi Lookout** i włącz opcję **Synchronizacja z usługą MTP** za pomocą przycisku przełączania.

![zrzut ekranu przedstawiający stronę synchronizacji usługi Lookout z wyróżnionym przyciskiem przełączania włączania](../media/mtp/lookout-intune-synchronization.png)

Wykonanie tej czynności oznacza zakończenie konfigurowania integracji usług Intune i Lookout w konsoli administratora usługi Intune.  Następne kilka kroków dotyczących implementacji tego rozwiązania obejmuje wdrażanie [aplikacji Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) i konfigurowanie zasad [zgodności](enable-device-threat-protection-rule-in-compliance-policy.md).

>[!IMPORTANT]
> **Konieczne jest** skonfigurowanie aplikacji Lookout for Work przed utworzeniem reguł zasad zgodności i skonfigurowaniem dostępu warunkowego. Zapewni to, że dana aplikacja będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.
## Następne kroki
[Konfigurowanie aplikacji Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Sep16_HO4-->


