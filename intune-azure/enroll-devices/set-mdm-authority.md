---
title: "Ustawianie urzędu zarządzania urządzeniami przenośnymi | Wersja zapoznawcza usługi Intune Azure | Microsoft Docs"
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawiania urzędu zarządzania urządzeniami przenośnymi w usłudze Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 72a162175e278faa236add5698d65233fa851c7b

---

# <a name="set-the-mobile-device-management-authority"></a>Ustawianie źródła zarządzania urządzeniem przenośnym 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ustawienie urzędu zarządzania urządzeniami przenośnymi określa sposób zarządzania urządzeniami. Możliwe są następujące konfiguracje:

- **Autonomiczna usługa Intune** — zarządzanie tylko w chmurze konfigurowane przy użyciu witryny Azure Portal. Ta konfiguracja zawiera pełny zestaw funkcji oferowanych przez usługę Intune.

- **Hybrydowa usługa Intune** — integracja rozwiązania usługi Intune w chmurze z programem System Center Configuration Manager. Konfigurowanie usługi Intune odbywa się przy użyciu konsoli programu Configuration Manager.

- **Zarządzanie urządzeniami przenośnymi w usłudze Office 365** — integracja usługi Office 365 z rozwiązaniem usługi Intune w chmurze. Konfigurowanie usługi Intune odbywa się przy użyciu centrum administracyjnego usługi Office 365. Ta konfiguracja zawiera podzbiór możliwości dostępnych w ramach autonomicznej usługi Intune.

>[!IMPORTANT]
>Aby zmienić urząd zarządzania urządzeniami przenośnymi po jego ustawieniu, należy skontaktować się z [pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune), dlatego warto starannie dokonać wyboru.

**Aby ustawić urząd zarządzania urządzeniami przenośnymi:**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie wybierz pozycję **Przegląd**.

3. W bloku **Rozpocznij zarządzanie urządzeniami** wybierz pozycję **Ustaw urząd certyfikacji MDM na usługę Intune**. Zostanie wyświetlony komunikat z potwierdzeniem pomyślnego ustawienia urzędu certyfikacji MDM na usługę Intune.



<!--HONumber=Feb17_HO3-->


