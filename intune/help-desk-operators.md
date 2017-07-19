---
title: "Portal pomocy technicznej służący do rozwiązywania problemów"
titleSuffix: Intune on Azure
description: "Personel działu pomocy korzysta z tego portalu do rozwiązywania problemów technicznych użytkowników"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Pomoc użytkownikom w Portalu rozwiązywania problemów w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Portal służący do rozwiązywania problemów pozwala operatorom pomocy technicznej i administratorom usługi Intune wyświetlać informacje dotyczące użytkowników w celu rozwiązywania zgłoszonych przez nich problemów. Organizacje, w których pracują operatorzy pomocy technicznej, mogą przypisać rolę **Operator pomocy technicznej** do grupy użytkowników, którzy będą wówczas mogli pomagać użytkownikom, korzystając z bloku Rozwiązywanie problemów.

Jeśli na przykład użytkownik zgłasza do działu pomocy technicznej problem techniczny dotyczący usługi Intune, operator pomocy technicznej wprowadza imię i nazwisko użytkownika. Usługa Intune wyświetla odpowiednie informacje, które mogą ułatwić rozwiązanie wielu problemów warstwy 1 dotyczących stanu użytkownika, błędów instalacji aplikacji czy też problemów ze zgodnością. Przykłady problemów, które można rozwiązać w ten sposób:
- Urządzenie nie odpowiada
-   Urządzenie nie pobiera ustawień sieci VPN lub Wi-Fi
-   Nie można zainstalować aplikacji


## <a name="add-help-desk-operators"></a>Dodawanie operatorów pomocy technicznej
Administrator usługi Intune może przypisywać użytkownikom uprawnienia operatorów pomocy technicznej na dwa sposoby:
- Przypisanie wbudowanej roli **Operator pomocy technicznej**
- Utworzenie i przypisanie roli niestandardowej

## <a name="assign-help-desk-operator-role"></a>Przypisywanie roli operatora pomocy technicznej
Jako administrator usługi Intune możesz przypisać rolę operatora pomocy technicznej do grupy użytkowników. Członkowie tej grupy mogą korzystać z portalu administratora. Aby mieć dostęp do portalu usługi Intune, każdy operator pomocy technicznej musi mieć licencję na usługę Intune. Dowiedz się, jak [przypisywać licencje na usługę Intune](licenses-assign.md).

1. Jako administrator usługi Intune zaloguj się do portalu usługi Intune i wybierz pozycję **Role usługi Intune**.
2. W obszarze obciążenia **Role usługi Intune** wybierz pozycję **Operator pomocy technicznej** > **Przypisania**, a następnie wybierz pozycję **Przypisz**.
  ![Zrzut ekranu portalu usługi Intune przedstawiający wyróżnione role usługi Intune oraz listę wbudowanych ról, takich jak Operator pomocy technicznej, wyróżnioną pozycję Przypisania i czerwoną otoczkę wokół pozycji Przypisz](./media/help-desk-user-assign.png)
3. Uzupełnij pola **Nazwa przypisania** (wymagane) i **Opis przypisania** (opcjonalne), a następnie przypisz elementy zbiorów **Członkowie (grupy)** i **Zakres (grupy)**.
4. Członkowie roli operatorów pomocy technicznej mogą od tego momentu używać portalu rozwiązywania problemów.

Aby uzyskać więcej informacji o rolach usługi Intune, zobacz temat [Role usługi Intune (RBAC)](role-based-access-control.md).

## <a name="create-a-custom-role-for-troubleshooting"></a>Tworzenie roli niestandardowej na potrzeby rozwiązywania problemów
Jako administrator usługi Intune możesz utworzyć rolę niestandardową umożliwiającą użytkownikom korzystanie z portalu rozwiązywania problemów przy użyciu uprawnień, które odpowiadają wymaganiom danej organizacji. Aby uzyskać więcej informacji o rolach usługi Intune, zobacz temat [Role usługi Intune (RBAC)](role-based-access-control.md).

![Zrzut ekranu portalu usługi Intune przedstawiający wyróżnione role usługi Intune oraz listę wbudowanych ról, takich jak Operator pomocy technicznej](./media/help-desk-user-add.png)

Aby używać konsoli usługi Intune w widoku pomocy technicznej, niestandardowa rola dotycząca pomocy technicznej powinna dysponować następującymi uprawnieniami:
- MobileApps: Odczyt
- ManagedApps: Odczyt
- ManagedDevices: Odczyt
- Organization: Odczyt

## <a name="access-the-troubleshooting-portal"></a>Dostęp do portalu rozwiązywania problemów

Personel działu pomocy i administratorzy usługi Intune mogą uzyskać dostęp do portalu rozwiązywania problemów na dwa sposoby:
- Otwórz w przeglądarce sieci Web stronę [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting).
- W portalu usługi Intune wybierz pozycję **Pomoc i obsługa techniczna** > **Rozwiązywanie problemów**.

![Zrzut ekranu przedstawiający obciążenie Rozwiązywanie problemów z usługą Intune z linkiem Wybierz użytkownika](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Korzystanie z portalu rozwiązywania problemów

Aby wyświetlić informacje o użytkownikach, w portalu rozwiązywania problemów można wybrać opcję **Wybierz użytkownika**. Informacje o użytkowniku mogą ułatwić zrozumienie bieżącego stanu użytkowników i ich urządzeń. W portalu rozwiązywania problemów dostępne są następujące szczegóły dotyczące rozwiązywania problemów:
- **Stan dzierżawy**
- **Stan użytkownika**
- **Urządzenia** i akcje urządzenia
- **Członkostwo w grupach**
- **Stan ochrony aplikacji**
