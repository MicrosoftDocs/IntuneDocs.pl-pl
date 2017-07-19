---
title: "Ustawianie ograniczeń rejestracji w usłudze Intune"
titleSuffix: Intune on Azure
description: "Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2c9d10e4e2a1d2a745b9e327bf9a8a9cd99e5ce4
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2017
---
# <a name="add-groups-in-intune"></a>Dodawanie grup w usłudze Intune
Do zarządzania urządzeniami i użytkownikami w usłudze Intune służą grupy usługi Azure Active Directory (AD). Jako administrator usługi Intune możesz skonfigurować grupy zgodnie z potrzebami organizacji. Utwórz grupy w celu zorganizowania użytkowników i urządzeń według lokalizacji geograficznej, działu lub parametrów sprzętowych. Użyj grup, aby zarządzać zadaniami na dużą skalę. Możesz na przykład ustawić zasady dla wielu użytkowników lub wdrożyć aplikacje na zestawie urządzeń.

W tym temacie wyjaśniono, jak dodać grupy do użytku w usłudze Intune.

Dodawać można następujące typy grup:
- **Grupy przypisane** — ręczne dodawanie użytkowników lub urządzeń do grup statycznych
- **Grupy dynamiczne** — (Azure Active Directory Premium) dynamiczne tworzenie grup użytkowników lub urządzeń zdefiniowanych za pomocą prostych lub zaawansowanych reguł

## <a name="add-a-new-group"></a>Dodawanie nowej grupy

Aby utworzyć nową grupę, wykonaj następujące czynności.
1. W portalu usługi Intune wybierz pozycję **Grupy**, a następnie wybierz pozycję **Nowa grupa** w bloku **Wszystkie grupy**.
  ![Zrzut ekranu przedstawiający portal usługi Intune z wybraną pozycją Nowa grupa](./media/groups-add-new.png)
2. Określ wartości w polach **Nazwa** i **Opis** dla nowej grupy. Te właściwości są wyświetlane tylko w portalu usługi Intune i nie są widoczne dla użytkowników.

3. Wybierz opcję w obszarze **Typ członkostwa**:
  - **Przypisane**, aby utworzyć grupę z ręcznie przypisanymi członkami. Dowiedz się więcej o [przypisanych grupach usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Użytkownik dynamiczny**, aby utworzyć grupę użytkowników zdefiniowaną za pomocą **zapytania dynamicznego**.
  - **Urządzenie dynamiczne**, aby utworzyć grupę urządzeń zdefiniowaną za pomocą **zapytania dynamicznego**.

  ![Zrzut ekranu przedstawiający właściwości grupy usługi Intune z pozycjami Nazwa, Opis, Typ członkostwa, Włącz funkcje pakietu Office i Członkowie](./media/groups-add-properties.png)

  Usługa Azure AD umożliwia tworzenie grup dynamicznych na podstawie reguł, które definiują członkostwo. Dowiedz się, jak [tworzyć grupy dynamiczne oparte na atrybutach](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Możesz wybrać pozycję **Włącz funkcje pakietu Office**, aby zezwolić członkom grup użytkowników na dostęp do udostępnionych aplikacji usługi Office 365.
5. Wybierz pozycję **Utwórz**, aby dodać nową grupę.

## <a name="see-also"></a>Zobacz także
[Manage access to resources with Azure Active Directory groups (Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
[Klasyczne grupy usługi Intune w witrynie Azure Portal](groups-get-started.md)
