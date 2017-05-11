---
title: "Portal pomocy technicznej służący do rozwiązywania problemów | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Personel działu pomocy korzysta z tego portalu do rozwiązywania problemów technicznych użytkowników"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 4916b66e1f2eeabb42401645dbece28dad28eb19
ms.contentlocale: pl-pl
ms.lasthandoff: 04/26/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Pomoc użytkownikom w Portalu rozwiązywania problemów w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Portal służący do rozwiązywania problemów pozwala operatorom pomocy technicznej i administratorom usługi Intune wyświetlać użytkowników i ich urządzenia oraz wykonywać zadania mające na celu rozwiązywanie problemów technicznych związanych z usługą Intune.

## <a name="add-help-desk-operators"></a>Dodawanie operatorów pomocy technicznej
Administrator usługi Intune może przypisywać użytkownikom uprawnienia operatorów pomocy technicznej. Użytkownicy pomocy technicznej mogą dzięki temu wyświetlić zawartość portalu usługi Intune, nie mogą jednak wyświetlać ani wykonywać zadań administracyjnych spoza obciążenia związanego z rozwiązywaniem problemów.

1. Jako administrator usługi Intune zaloguj się do [portalu Azure](https:portal.azure.com) i wybierz kolejno pozycje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. W lewym bloku nawigacyjnym wybierz pozycję **Role usługi Intune**.
3. W obszarze obciążenia **Role usługi Intune** wybierz opcję **Operator pomocy technicznej**, a następnie wybierz pozycję **Przypisz**.
4. Uzupełnij pola **Nazwa przypisania** (wymagane) i **Opis przypisania** (opcjonalne), a następnie przypisz elementy zbiorów **Członkowie (grupy)** i **Zakres (grupy)**.
5. Członkowie roli operatorów pomocy technicznej mogą od tego momentu używać portalu rozwiązywania problemów.

Aby uzyskać więcej informacji o rolach usługi Intune, zobacz temat [Role usługi Intune (RBAC)](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control).

## <a name="access-the-troubleshooting-portal"></a>Dostęp do portalu rozwiązywania problemów

Personel działu pomocy i administratorzy usługi Intune mogą uzyskać dostęp do portalu rozwiązywania problemów na dwa sposoby:
- W [portalu Azure](https://portal.azure.com) należy wybrać kolejno pozycje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**, a następnie wybrać w lewym bloku nawigacyjnym pozycję **Rozwiąż problem**. Inne obciążenia są widoczne w lewym bloku nawigacyjnym, ale są niedostępne.

![Zrzut ekranu przedstawiający obciążenie Rozwiązywanie problemów z usługą Intune z linkiem Wybierz użytkownika](media/help-desk-user.png)
- Otwórz w przeglądarce sieci Web stronę [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting). Widoczny jest wyłącznie portal rozwiązywania problemów.

## <a name="use-the-troubleshooting-portal"></a>Korzystanie z portalu rozwiązywania problemów

W portalu rozwiązywania problemów można wybrać opcję **Wybierz użytkownika**, aby wyświetlić informacje o użytkownikach. Informacje o użytkowniku mogą ułatwić zrozumienie bieżącego stanu użytkowników i ich urządzeń. W portalu rozwiązywania problemów dostępne są następujące szczegóły dotyczące użytkownika usługi Intune i jego urządzenia:
- Informacje o koncie użytkownika
- Członkostwo użytkownika w grupie
- Szczegóły urządzenia

Użytkownicy pomocy technicznej mogą również wykonywać na urządzeniach zadania zdalne, takie jak **Zdalne blokowanie**.

