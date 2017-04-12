---
title: "Włączenie usługi Skycure Mobile Threat Defense w usłudze Intune | Dokumentacja firmy Microsoft"
description: "Włącz usługę Skycure Mobile Threat Defense w klasycznej konsoli usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Włączenie usługi Skycure Mobile Threat Defense w usłudze Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Aby włączyć połączenie z usługą Skycure Mobile Threat Defense (MTD) w usłudze Intune, należy wcześniej skonfigurować [Łącznik usługi Intune w konsoli usługi Skycure](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Aby włączyć połączenie z usługą Skycure MTD w usłudze Intune

1.  Przejdź do [klasycznej konsoli usługi Intune](https://manage.microsoft.com/) i wprowadź swoje poświadczenia.

2.  Wybierz opcję **Administrator** &gt; **Integracja z usługą innej firmy**, następnie wybierz opcję **Stan programu Skycure** i włącz opcję **Synchronizacja z MTD** za pomocą przycisku przełącznika.

    ![Włączanie przełącznika Skycure w klasycznej konsoli usługi Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Przed utworzeniem reguł zasad zgodności i skonfigurowaniem dostępu warunkowego należy skonfigurować aplikację Skycure. Zapewni to, że dana aplikacja będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

Wykonanie tej czynności oznacza zakończenie konfigurowania integracji programu Skycure i usługi Intune w konsoli administratora usługi Intune. Następnych kilka kroków dotyczących implementacji tego rozwiązania obejmuje wdrażanie aplikacji Skycure for Work i konfigurowanie zasad zgodności.

## <a name="next-steps"></a>Następne kroki

[Utworzenie zasad zgodności usługi Skycure Mobile Threat Defense](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

