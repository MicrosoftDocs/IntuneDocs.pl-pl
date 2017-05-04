---
title: "Ustawianie źródła zarządzania urządzeniem przenośnym"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawiania urzędu zarządzania urządzeniami przenośnymi w usłudze Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: dc08ba96eeea0ce2aad78e4d6ca0d94e709d885d
ms.openlocfilehash: 6cf7c56924091713f55fe8824fb11e522825b98f
ms.lasthandoff: 04/21/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Ustawianie źródła zarządzania urządzeniem przenośnym

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.

Możliwe są następujące konfiguracje:

- **Autonomiczna usługa Intune** — zarządzanie tylko w chmurze konfigurowane przy użyciu witryny Azure Portal. Ta konfiguracja zawiera pełny zestaw funkcji oferowanych przez usługę Intune. [Ustaw urząd MDM w konsoli usługi Intune](#set-mdm-authority-to-Intune).

- **Hybrydowa usługa Intune** — integracja rozwiązania usługi Intune w chmurze z programem System Center Configuration Manager. Konfigurowanie usługi Intune odbywa się przy użyciu konsoli programu Configuration Manager. [Ustaw urząd MDM w programie Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Zarządzanie urządzeniami przenośnymi w usłudze Office 365** — integracja usługi Office 365 z rozwiązaniem usługi Intune w chmurze. Konfigurowanie usługi Intune odbywa się przy użyciu centrum administracyjnego usługi Office 365. Ta konfiguracja zawiera podzbiór możliwości dostępnych w ramach autonomicznej usługi Intune. Ustaw urząd MDM przy użyciu centrum administracyjnego usługi Office 365.

>[!IMPORTANT]
>Aby zmienić urząd zarządzania urządzeniami przenośnymi po jego ustawieniu, należy skontaktować się z [pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune), dlatego warto starannie dokonać wyboru.

## <a name="set-mdm-authority-to-intune"></a>Ustawianie urzędu MDM na usługę Intune

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
  ![Zrzut ekranu przedstawiający obciążenie Rozwiązywanie problemów z usługą Intune z linkiem Wybierz użytkownika](media/set-mdm-auth.png)
2. W bloku Intune wybierz pozycję **Rejestracja urządzenia**, a następnie wybierz pozycję **Przegląd**.

3. W bloku **Rozpocznij zarządzanie urządzeniami** wybierz pozycję **Ustaw urząd certyfikacji MDM na usługę Intune**. Zostanie wyświetlony komunikat z potwierdzeniem pomyślnego ustawienia urzędu certyfikacji MDM na usługę Intune.

