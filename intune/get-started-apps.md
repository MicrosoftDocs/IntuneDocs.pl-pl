---
title: "Aplikacje — wprowadzenie"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a086da185681a91daad214f1be2d4ff0e2827fbb
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-with-apps"></a>Aplikacje — wprowadzenie

![Obraz przedstawiający dodawanie aplikacji Microsoft Word.](/intune/media/generic-add-apps.png)

Urządzenia służbowe są bezużyteczne, jeśli nie znajdują się na nich odpowiednie aplikacje. Usługa Intune obsługuje kilka różnych sposobów wdrażania aplikacji na urządzeniach firmowych:

* **Instalatory oprogramowania**: używane w przypadku przekazywania pliku, który jest pobierany na urządzeniach użytkowników
* __Linki zewnętrzne__: używane w przypadku aplikacji znajdującej się w publicznym sklepie z aplikacjami lub aplikacji internetowej
* **Aplikacje zarządzane**: dla urządzeń z systemem iOS, w przypadku których konieczne jest zastosowanie dodatkowych czynności związanych z zarządzaniem aplikacjami mobilnymi dla aplikacji dostępnych w sklepie App Store

W tym przypadku wdrożenie odbędzie się za pomocą jednej z szybszych metod wdrażania aplikacji, czyli przypisania aplikacji ze sklepu publicznego.

__Jak przypisać aplikację ze sklepu publicznego?__

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Za pomocą pola **Wyszukaj zasoby** wyszukaj usługę **Intune**.
3. Wybierz pozycję **Aplikacje mobilne**, a następnie wybierz pozycję **Aplikacje**.
4. Wybierz pozycję **Dodaj**, następnie wybierz pozycję **Aplikacja ze sklepu iOS** jako **typ aplikacji**.
5. W polu tekstowym wyszukaj aplikację, która zostanie przypisana do urządzenia. Wybierz aplikację, a następnie wybierz przycisk **OK**.
6. W bloku **Dodawanie aplikacji** wybierz pozycję **Informacje o aplikacji**, a następnie upewnij się, że wszystkie informacje o aplikacji zostały wypełnione. Można dodać inne opcjonalne szczegóły, aby ułatwić organizowanie tej aplikacji, takie jak **Właściciel**, **Uwagi**, **Deweloper** oraz **Adres URL zasad ochrony prywatności** na potrzeby firmowych zasad ochrony prywatności.
7. Upewnij się, że wybrano pozycję Tak dla opcji Wyświetlaj jako polecaną aplikację w Portalu firmy, a następnie wybierz przycisk OK.
8. Wybierz pozycję **Dodaj**, aby dodać aplikację. Spowoduje to przejście do obszaru **Omówienie** . Wybierz pozycję **Przypisania**, a następnie kliknij pozycję **Wybierz grupy**, aby przypisać je do grupy testowej. Ustaw aplikację jako **dostępną** do pobrania. Aplikacja powinna wtedy być wyświetlana jako **polecana** na urządzeniu testowym.
