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
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: 1297522d0f7b52ebe14eb7b938f3458e7308ae27


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Włączanie połączenia z usługą Lookout MTP w konsoli administracyjnej usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Aby włączyć połączenie z usługą Lookout MTP w usłudze Intune, należy wcześniej skonfigurować łącznik usługi Intune w konsoli usługi Lookout.  Jeśli jeszcze tego nie zrobiono, należy [skonfigurować subskrypcję przy użyciu usługi Lookout do ochrony urządzeń przenośnych przed zagrożeniami](set-up-your-subscription-with-lookout-mtp.md).

Aby włączyć połączenie z usługą Lookout MTP w usłudze Intune, na stronie **Administracja** w [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Integracja z usługami innych firm**. Wybierz pozycję **Stan usługi Lookout** i włącz opcję **Synchronizacja z usługą MTP** za pomocą przycisku przełączania.

![zrzut ekranu przedstawiający stronę synchronizacji usługi Lookout z wyróżnionym przyciskiem przełączania włączania](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> **Konieczne jest** skonfigurowanie aplikacji Lookout for Work przed utworzeniem reguł zasad zgodności i skonfigurowaniem dostępu warunkowego. Zapewni to, że dana aplikacja będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

Wykonanie tej czynności oznacza zakończenie konfigurowania integracji usług Intune i Lookout w konsoli administratora usługi Intune.  Następne kilka kroków dotyczących implementacji tego rozwiązania obejmuje wdrażanie [aplikacji Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) i konfigurowanie zasad [zgodności](enable-device-threat-protection-rule-in-compliance-policy.md).


## <a name="next-steps"></a>Następne kroki
[Konfigurowanie aplikacji Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Jan17_HO2-->


