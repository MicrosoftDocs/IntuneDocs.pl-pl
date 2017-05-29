---
title: "Ustawianie ograniczeń rejestracji w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: ograniczanie rejestrowania według platform i ustawianie limitu rejestracji urządzeń w usłudze Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d99f7ca5b5e96a7ab113a14d36f0fef474411836
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji 

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Możesz ustawić typy oraz maksymalną liczbę urządzeń, które będzie można zarejestrować. W bloku Ograniczenia rejestracji możesz ustawić:

- platformy, na których będzie możliwa rejestracja, oraz czy ma być blokowana rejestracja urządzeń z systemami Android i iOS będących własnością osobistą;

- maksymalną liczbę urządzeń, które użytkownik może zarejestrować.

## <a name="set-device-type-restrictions"></a>Ustawianie ograniczeń typu urządzeń

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Ograniczenia rejestracji**.

3. W obszarze **Ograniczenia typu urządzeń** wybierz pozycję **Domyślne**.

4. W bloku **Wszyscy użytkownicy** wybierz pozycję **Platformy**.

5. Dla platform, które mogą dokonywać rejestracji w usłudze Intune, wybierz pozycję **Zezwalaj**. Dla platform, w przypadku których chcesz zablokować możliwość rejestrowania, wybierz pozycję **Zablokuj**. Wartość domyślna tego ustawienia to **Zezwalaj**. 

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

4. W bloku **Wszyscy użytkownicy** wybierz pozycję **Limit urządzeń**.

5. Wybierz maksymalną liczbę urządzeń, które użytkownik może zarejestrować, a następnie wybierz pozycję **Zapisz**.

