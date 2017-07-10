---
title: "Ustawianie źródła zarządzania urządzeniem przenośnym"
titleSuffix: Intune on Azure
description: "Informacje na temat ustawiania urzędu zarządzania urządzeniami mobilnymi w usłudze Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 449c45e0edcc0d0a33352ba154ad68fa6c4725c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Ustawianie źródła zarządzania urządzeniem przenośnym

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.

Możliwe są następujące konfiguracje:

- **Autonomiczna usługa Intune** — zarządzanie tylko w chmurze konfigurowane przy użyciu witryny Azure Portal. Ta konfiguracja zawiera pełny zestaw funkcji oferowanych przez usługę Intune. [Ustaw urząd MDM w konsoli usługi Intune](#mdm-authority-set-to-intune).

- **Hybrydowa usługa Intune** — integracja rozwiązania usługi Intune w chmurze z programem System Center Configuration Manager. Konfigurowanie usługi Intune odbywa się przy użyciu konsoli programu Configuration Manager. [Ustaw urząd MDM w programie Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Zarządzanie urządzeniami przenośnymi w usłudze Office 365** — integracja usługi Office 365 z rozwiązaniem usługi Intune w chmurze. Konfigurowanie usługi Intune odbywa się przy użyciu centrum administracyjnego usługi Office 365. Ta konfiguracja zawiera podzbiór możliwości dostępnych w ramach autonomicznej usługi Intune. Ustaw urząd MDM przy użyciu centrum administracyjnego usługi Office 365.

>[!IMPORTANT]    
W programie Configuration Manager w wersji 1610 lub nowszej i w usłudze Microsoft Intune w wersji 1705 można zmienić urząd certyfikacji MDM bez konieczności kontaktowania się Pomocą techniczną firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. Szczegółowe informacje można znaleźć w sekcji [Co należy zrobić, jeśli wybrano błędne ustawienie urzędu MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Ustawianie urzędu MDM na usługę Intune

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
  ![Zrzut ekranu przedstawiający obciążenie Rozwiązywanie problemów z usługą Intune z linkiem Wybierz użytkownika](media/set-mdm-auth.png)
2. W bloku Intune wybierz pozycję **Rejestracja urządzenia**, a następnie wybierz pozycję **Przegląd**.

3. W bloku **Rozpocznij zarządzanie urządzeniami** wybierz pozycję **Ustaw urząd certyfikacji MDM na usługę Intune**. Zostanie wyświetlony komunikat z potwierdzeniem pomyślnego ustawienia urzędu certyfikacji MDM na usługę Intune.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.
