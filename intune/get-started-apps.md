---
title: "Aplikacje — wprowadzenie"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 71093f8ac17fc6d6938f5c263a40204f89419726
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-apps"></a>Aplikacje — wprowadzenie

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune obsługuje kilka różnych sposobów wdrażania aplikacji na urządzeniach firmowych:

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
