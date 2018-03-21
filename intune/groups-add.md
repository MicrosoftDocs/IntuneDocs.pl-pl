---
title: "Dodawanie grup w celu zorganizowania użytkowników i urządzeń"
titlesuffix: Microsoft Intune
description: "Możesz dodawać grupy, aby organizować użytkowników i urządzenia na podstawie lokalizacji geograficznej, działu lub kryteriów dotyczących sprzętu."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7d2b551832d8d0e467d079df673954318623e4c
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Dodawanie grup w celu zorganizowania użytkowników i urządzeń
Do zarządzania urządzeniami i użytkownikami w usłudze Intune służą grupy usługi Azure Active Directory (AD). Jako administrator usługi Intune możesz skonfigurować grupy zgodnie z potrzebami organizacji. Utwórz grupy w celu zorganizowania użytkowników i urządzeń według lokalizacji geograficznej, działu lub parametrów sprzętowych. Użyj grup, aby zarządzać zadaniami na dużą skalę. Możesz na przykład ustawić zasady dla wielu użytkowników lub wdrożyć aplikacje na zestawie urządzeń.

W tym temacie wyjaśniono, jak dodać grupy do użytku w usłudze Intune.

Dodawać można następujące typy grup:
- **Grupy przypisane** — ręczne dodawanie użytkowników lub urządzeń do grup statycznych
- **Grupy dynamiczne** — (przy użyciu usługi Azure Active Directory — wersja Premium) umożliwiają dynamiczne tworzenie grup użytkowników lub urządzeń zdefiniowanych za pomocą prostych lub zaawansowanych reguł

## <a name="add-a-new-group"></a>Dodawanie nowej grupy

Aby utworzyć nową grupę, wykonaj następujące czynności.
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Grupy**, a następnie wybierz pozycję **Nowa grupa** w okienku **Wszystkie grupy**.
  ![Zrzut ekranu przedstawiający witrynę Azure Portal z wybraną pozycją Nowa grupa](./media/groups-add-new.png)
2. Określ wartości w polach **Typ grupy**, **Nazwa** i **Opis** dla nowej grupy. Te właściwości są wyświetlane tylko w portalu zarządzania i nie są widoczne dla użytkowników.

3. Wybierz opcję w obszarze **Typ członkostwa**:
  - **Przypisane**, aby utworzyć grupę z ręcznie przypisanymi członkami. Dowiedz się więcej o [przypisanych grupach usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Użytkownik dynamiczny**, aby utworzyć grupę użytkowników zdefiniowaną za pomocą **zapytania dynamicznego**.
  - **Urządzenie dynamiczne**, aby utworzyć grupę urządzeń zdefiniowaną za pomocą **zapytania dynamicznego**.

  ![Zrzut ekranu przedstawiający właściwości grupy w usłudze Intune](./media/groups-add-properties.png)

  Usługa Azure AD umożliwia tworzenie grup dynamicznych na podstawie reguł, które definiują członkostwo. Dowiedz się, jak [tworzyć grupy dynamiczne oparte na atrybutach](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Możesz wybrać pozycję **Włącz funkcje pakietu Office**, aby zezwolić członkom grup użytkowników na dostęp do udostępnionych aplikacji usługi Office 365. Dowiedz się więcej na temat [grup usługi Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Wybierz pozycję **Utwórz**, aby dodać nową grupę.

## <a name="see-also"></a>Zobacz też
- [Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klasyczne grupy usługi Intune w witrynie Azure Portal](groups-get-started.md)
