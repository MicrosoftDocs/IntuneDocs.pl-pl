---
title: "Ustawianie ograniczeń rejestracji w usłudze Intune"
titleSuffix: Intune on Azure
description: "Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz określić, które urządzenia mogą być rejestrowane w celu zarządzania za pomocą usługi Intune. Użyj portalu usługi Intune, aby ustawić następujące ograniczenia dotyczące rejestrowania urządzeń:

- Maksymalna liczba zarejestrowanych urządzeń
- Platformy urządzeń, które można zarejestrować:
  - Android
  - iOS
  - macOS
  - Windows
- Ograniczenia urządzeń prywatnych (tylko z systemem iOS i Android)

>[!NOTE]
>Ograniczenia rejestrowania nie są funkcją zabezpieczeń. Urządzenia, na których złamano zabezpieczenia, mogą błędnie podawać swój charakter. Te ograniczenia stanowią optymalną barierę dla niezłośliwych użytkowników.

## <a name="set-device-type-restrictions"></a>Ustawianie ograniczeń typu urządzeń
Domyślne ograniczenia rejestracji są stosowane do wszystkich użytkowników, którym nie przypisano ograniczeń rejestracji o wyższym priorytecie.  
1. W portalu usługi Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Ograniczenia rejestracji**.
![Zrzut ekranu przedstawiający obszar roboczy ograniczania urządzeń z domyślnymi ograniczeniami dotyczącymi typu i liczby urządzeń.](media/device-restrictions-set-default.png)
2. W obszarze **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń** wybierz pozycję **Domyślne**.
3. W obszarze **Wszyscy użytkownicy** wybierz pozycję **Platformy**. Wybierz pozycję **Zezwalaj** lub **Blokuj** dla każdej platformy:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Kliknij polecenie **Zapisz**.
4. W obszarze **Wszyscy użytkownicy** wybierz pozycję **Konfiguracje platformy** i wybierz następujące konfiguracje:
  - **Własność użytkownika** — określ, czy **zezwalać**, czy **blokować** urządzenia z systemami Android i iOS.
  ![Zrzut ekranu przedstawiający obszar roboczy ograniczania urządzeń z domyślnymi konfiguracjami platformy urządzeń i widocznymi skonfigurowanymi ustawieniami urządzeń będących własnością użytkownika.](media/device-restrictions-platform-configurations.png)
  Kliknij polecenie **Zapisz**.

>[!NOTE]
>Jeśli zablokujesz rejestrację prywatnych urządzeń z systemem Android, urządzenia z programem Android for Work nadal będą mogły być rejestrowane.

## <a name="set-device-limit-restrictions"></a>Ustawianie ograniczeń limitu urządzeń
Domyślne ograniczenia rejestracji są stosowane do wszystkich użytkowników, którym nie przypisano ograniczeń rejestracji o wyższym priorytecie.  
1. W portalu usługi Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Ograniczenia rejestracji**.
2. Wybierz pozycję **Ograniczenia rejestracji** > **Ograniczenia limitu urządzeń**.
3. W obszarze **Wszyscy użytkownicy** wybierz pozycję **Limit urządzeń**. Określ maksymalną liczbę zarejestrowanych urządzeń na użytkownika.  
![Zrzut ekranu przedstawiający blok ograniczeń dotyczących limitu liczby urządzeń z ograniczeniami limitu liczby urządzeń.](./media/device-restrictions-limit.png)

  Kliknij polecenie **Zapisz**.
