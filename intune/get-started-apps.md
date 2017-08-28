---
title: "Aplikacje — wprowadzenie"
titleSuffix: Intune on Azure
description: "Znajduj i dodawaj aplikacje do urządzeń, aby umożliwić pracownikom wykonywanie zadań."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ac2a6f027a78c6b0093a0d299a7cae3265e5954
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-adding-apps"></a>Wprowadzenie do dodawania aplikacji

Usługa Intune obsługuje kilka różnych sposobów wdrażania aplikacji na urządzeniach firmowych:

* **Instalatory oprogramowania**: używane w przypadku przekazywania pliku, który jest pobierany na urządzeniach użytkowników
* __Linki zewnętrzne__: używane w przypadku aplikacji znajdującej się w publicznym sklepie z aplikacjami lub aplikacji internetowej
* **Aplikacje zarządzane**: dla urządzeń z systemem iOS, w przypadku których konieczne jest zastosowanie dodatkowych czynności związanych z zarządzaniem aplikacjami mobilnymi dla aplikacji dostępnych w sklepie App Store

W tym przypadku wdrożenie odbędzie się za pomocą jednej z szybszych metod wdrażania aplikacji, czyli przypisania aplikacji ze sklepu publicznego.

## <a name="how-do-i-assign-a-public-store-app"></a>Jak mogę przypisać aplikację ze sklepu publicznego?

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Za pomocą pola **Wyszukaj zasoby** wyszukaj usługę **Intune**.
3. Wybierz pozycję **Aplikacje mobilne**, a następnie wybierz pozycję **Aplikacje**.
4. Wybierz pozycję **Dodaj**, następnie wybierz pozycję **Aplikacja ze sklepu iOS** jako **typ aplikacji**.
5. W polu tekstowym wyszukaj aplikację, która zostanie przypisana do urządzenia. Wybierz aplikację, a następnie wybierz przycisk **OK**.
6. W bloku **Dodawanie aplikacji** wybierz pozycję **Informacje o aplikacji**, a następnie upewnij się, że wszystkie informacje o aplikacji zostały wypełnione. Można dodać inne opcjonalne szczegóły, aby ułatwić organizowanie tej aplikacji, takie jak **Właściciel**, **Uwagi**, **Deweloper** oraz **Adres URL zasad ochrony prywatności** na potrzeby firmowych zasad ochrony prywatności.
7. Upewnij się, że wybrano pozycję Tak dla opcji Wyświetlaj jako polecaną aplikację w Portalu firmy, a następnie wybierz przycisk OK.
8. Wybierz pozycję **Dodaj**, aby dodać aplikację. Spowoduje to przejście do obszaru **Omówienie** . Wybierz pozycję **Przypisania**, a następnie kliknij pozycję **Wybierz grupy**, aby przypisać je do grupy testowej. Ustaw aplikację jako **dostępną** do pobrania. Aplikacja powinna wtedy być wyświetlana jako **polecana** na urządzeniu testowym.

## <a name="learn-more"></a>Dowiedz się więcej

* [What is app management with Intune? (Co to jest zarządzanie aplikacjami przy użyciu usługi Intune?)](app-management.md)
* [Przegląd cyklu życia aplikacji](app-lifecycle.md)
* [Co to są zasady ochrony aplikacji?](app-protection-policy.md)
