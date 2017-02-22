---
title: "Ustawianie ograniczeń rejestracji w usłudze Intune | Wersja zapoznawcza usługi Intune Azure | Microsoft Docs"
description: "Wersja zapoznawcza usługi Intune Azure: ograniczanie rejestrowania według platform i ustawianie limitu rejestracji urządzeń w usłudze Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: c4fa22fad4df9c0e4699cf258eb9518a1534bb94

---

# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Możesz ustawić typy oraz maksymalną liczbę urządzeń, które będzie można zarejestrować. W bloku Ograniczenia rejestracji możesz ustawić:

- platformy, na których będzie możliwa rejestracja, oraz czy ma być blokowana rejestracja urządzeń z systemami Android i iOS będących własnością osobistą;

- maksymalną liczbę urządzeń, które użytkownik może zarejestrować.

## <a name="set-device-type-restrictions"></a>Ustawianie ograniczeń typu urządzeń

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Ograniczenia rejestracji**.

3. W obszarze **Ograniczenia typu urządzeń** wybierz pozycję **Domyślne**.

4. W bloku **Wszyscy użytkownicy** wybierz pozycję **Platformy**.

5. Dla platform, w przypadku których jest możliwe rejestrowanie w usłudze Intune, wybierz pozycję **Zezwalaj**. Dla platform, w przypadku których chcesz zablokować możliwość rejestrowania, wybierz pozycję **Zablokuj**. Wartość domyślna tego ustawienia to **Zezwalaj**. 

    >[!NOTE]
    >Te ustawienia nie zezwalają ani nie blokują rejestracji systemu Windows używających oprogramowania klienckiego usługi Intune. Te ustawienia mają wpływ tylko na rejestrację przy użyciu funkcji zarządzania urządzeniami przenośnymi. 

6. Wybierz pozycję **Zapisz**.

7. Wybierz pozycję **Konfiguracje platform**.

8. Zdecyduj, czy **zezwolić** na rejestrowanie urządzeń z systemem iOS będących własnością osobistą, czy **zablokować** taką możliwość.

9. Wybierz pozycję **Zapisz**.

## <a name="set-device-limit-restrictions"></a>Ustawianie ograniczeń limitu urządzeń

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Ograniczenia rejestracji**.

3. W obszarze **Ograniczenia limitu urządzeń** wybierz pozycję **Domyślne**.

4. W bloku **Wszyscy użytkownicy** wybierz pozycję **Limit urządzenia**.

5. Wybierz maksymalną liczbę urządzeń, które użytkownik może zarejestrować, a następnie wybierz pozycję **Zapisz**.



<!--HONumber=Feb17_HO3-->


