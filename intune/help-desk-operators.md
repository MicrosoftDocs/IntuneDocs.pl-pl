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
ms.openlocfilehash: 066f8668ea37e928455792f512e4e337a1f19c20
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2017
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Portal służący do rozwiązywania problemów pozwala operatorom pomocy technicznej i administratorom usługi Intune wyświetlać informacje dotyczące użytkowników w celu rozwiązywania zgłoszonych przez nich problemów. Organizacje, w których pracują operatorzy pomocy technicznej, mogą przypisać rolę **Operator pomocy technicznej** do grupy użytkowników, którzy będą wówczas mogli pomagać użytkownikom, korzystając z bloku Rozwiązywanie problemów.

Jeśli na przykład użytkownik zgłasza do działu pomocy technicznej problem techniczny dotyczący usługi Intune, operator pomocy technicznej wprowadza imię i nazwisko użytkownika. W usłudze Intune wyświetlane są przydatne dane, które mogą ułatwić rozwiązanie wielu problemów warstwy 1, w tym:
- Stan użytkownika
- Przypisania
- Błąd instalacji aplikacji
- Problemy ze zgodnością
- Urządzenie nie odpowiada
-   Urządzenie nie pobiera ustawień sieci VPN lub Wi-Fi
-   Nie można zainstalować aplikacji

## <a name="add-help-desk-operators"></a>Dodawanie operatorów pomocy technicznej
Jako administrator usługi Intune możesz przypisać rolę operatora pomocy technicznej do grupy użytkowników. Członkowie tej grupy mogą korzystać z portalu administratora w celu rozwiązywania problemów użytkowników. Aby mieć dostęp do portalu usługi Intune, każdy operator pomocy technicznej musi mieć licencję na usługę Intune. Dowiedz się, jak [przypisywać licencje na usługę Intune](licenses-assign.md).

Aby dodać użytkowników pomocy technicznej:
1. W razie potrzeby [dodaj użytkowników do usługi Intune](users-add.md).
2. [Utwórz grupę pomocy technicznej](groups-add.md) i dodaj do niej użytkowników.
3. [Przypisz rolę RBAC operatora pomocy technicznej](role-based-access-control.md#built-in-roles)

  ![Zrzut ekranu portalu usługi Intune pokazujący wyróżnione role usługi Intune i listę wbudowanych ról łącznie z rolą operatora pomocy technicznej](./media/help-desk-user-add.png) Możesz też [utworzyć niestandardową rolę](role-based-access-control.md#custom-roles), którą można dalej modyfikować, aby przyznać dostęp operatorom pomocy technicznej.  Operatorzy pomocy technicznej wymagają następujących uprawnień, aby pomóc w rozwiązywaniu problemów użytkownika:
    - MobileApps: Odczyt
    - ManagedApps: Odczyt
    - ManagedDevices: Odczyt
    - Organization: Odczyt
    - DeviceCompliancePolices: Odczyt
    - DeviceConfigurations: Odczyt

4. Aby udzielić operatorom pomocy technicznej uprawnienia do wyświetlania kondycji usługi i otwierania biletów pomocy technicznej dla usługi Intune, [udziel użytkownikom uprawnień administratora](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) jako **Administrator usługi**. Nie nadawaj uprawnienia **Administrator usługi Intune**, ponieważ ta rola katalogu ma więcej uprawnień niż te, które są potrzebne dla operatów pomocy technicznej.

## <a name="access-the-troubleshooting-portal"></a>Dostęp do portalu rozwiązywania problemów

Personel działu pomocy i administratorzy usługi Intune mogą uzyskać dostęp do portalu rozwiązywania problemów na dwa sposoby:
- Otwórz stronę [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) w przeglądarce internetowej, aby wyświetlić tylko portal rozwiązywania problemów.
  ![Zrzut ekranu przedstawiający konsolę rozwiązywania problemów](./media/help-desk-console.png)
- Zaloguj się do witryny Azure Portal, wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**, a następnie przejdź do obszaru **Pomoc i obsługa techniczna** > **Rozwiązywanie problemów**.

Kliknij pozycję **Wybierz użytkownika**, aby wyświetlić użytkownika wraz ze szczegółami, które go dotyczą.

![Zrzut ekranu przedstawiający obciążenie Rozwiązywanie problemów z usługą Intune z linkiem Wybierz użytkownika](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Korzystanie z portalu rozwiązywania problemów

Aby wyświetlić informacje o użytkownikach, w portalu rozwiązywania problemów można wybrać opcję **Wybierz użytkownika**. Informacje o użytkowniku mogą ułatwić zrozumienie bieżącego stanu użytkowników i ich urządzeń. W portalu rozwiązywania problemów dostępne są następujące szczegóły dotyczące rozwiązywania problemów:
- **Stan konta**
- **Stan użytkownika**
- **Urządzenia** z akcjami urządzenia
- **Członkostwo w grupach**
- **Stan ochrony aplikacji**
