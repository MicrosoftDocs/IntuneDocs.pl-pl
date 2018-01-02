---
title: "Aplikacje — wprowadzenie"
titlesuffix: Azure portal
description: "Znajduj i dodawaj aplikacje do urządzeń, aby umożliwić pracownikom wykonywanie zadań."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb02c362f056c454f4d141ce7ae20b9c3ca8035d
ms.sourcegitcommit: a7c1e10e615e5c975bb5d52eca986c5cf5287687
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2017
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
4. Wybierz pozycję **Dodaj**, następnie wybierz pozycję **iOS** w obszarze **Aplikacja ze sklepu** jako **typ aplikacji**.
5. Wybierz pozycję **Wybierz aplikację**, aby wyświetlić blok **Wyszukaj w sklepie App Store**.
6. W polu tekstowym wyszukaj aplikację, która zostanie przypisana do urządzenia. Wybierz aplikację, a następnie wybierz pozycję **Wybierz**.
7. W bloku **Dodawanie aplikacji** wybierz pozycję **Informacje o aplikacji**, a następnie upewnij się, że wszystkie informacje o aplikacji zostały wypełnione. Można dodać inne opcjonalne szczegóły, aby ułatwić organizowanie tej aplikacji, takie jak **Właściciel**, **Uwagi**, **Deweloper** oraz **Adres URL zasad ochrony prywatności** na potrzeby firmowych zasad ochrony prywatności.
8. Upewnij się, że wybrano pozycję **Tak** dla opcji **Wyświetlaj jako polecaną aplikację w Portalu firmy**, a następnie wybierz przycisk **OK**.
9. W bloku **Dodaj aplikację** wybierz pozycję **Dodaj**, aby dodać aplikację. Spowoduje to przejście do obszaru **Omówienie** . Wybierz pozycję **Przypisania**, a następnie kliknij pozycję **Wybierz grupy**, aby przypisać je do grupy testowej. Ustaw aplikację jako **dostępną** do pobrania. Aplikacja powinna wtedy być wyświetlana jako **polecana** na urządzeniu testowym.

## <a name="learn-more"></a>Dowiedz się więcej

* [What is app management with Intune? (Co to jest zarządzanie aplikacjami przy użyciu usługi Intune?)](app-management.md)
* [Przegląd cyklu życia aplikacji](app-lifecycle.md)
* [Co to są zasady ochrony aplikacji?](app-protection-policy.md)
