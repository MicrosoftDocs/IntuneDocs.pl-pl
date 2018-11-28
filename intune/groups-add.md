---
title: Dodawanie grup w celu zorganizowania użytkowników i urządzeń
titlesuffix: Microsoft Intune
description: Możesz dodawać grupy, aby organizować użytkowników i urządzenia na podstawie lokalizacji geograficznej, działu lub kryteriów dotyczących sprzętu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7a6fffaa0ae35675538d04b91980799d7d8aa80d
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181296"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Dodawanie grup w celu zorganizowania użytkowników i urządzeń
Do zarządzania urządzeniami i użytkownikami w usłudze Intune służą grupy usługi Azure Active Directory (AD). Jako administrator usługi Intune możesz skonfigurować grupy zgodnie z potrzebami organizacji. Utwórz grupy w celu zorganizowania użytkowników i urządzeń według lokalizacji geograficznej, działu lub parametrów sprzętowych. Użyj grup, aby zarządzać zadaniami na dużą skalę. Możesz na przykład ustawić zasady dla wielu użytkowników lub wdrożyć aplikacje na zestawie urządzeń.

Dodawać można następujące typy grup:
- **Grupy przypisane** — ręczne dodawanie użytkowników lub urządzeń do grup statycznych
- **Grupy dynamiczne** — (przy użyciu usługi Azure Active Directory — wersja Premium) umożliwiają dynamiczne tworzenie grup użytkowników lub urządzeń zdefiniowanych za pomocą prostych lub zaawansowanych reguł

## <a name="add-a-new-group"></a>Dodawanie nowej grupy

Aby utworzyć nową grupę, wykonaj następujące czynności.
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Grupy**, a następnie wybierz pozycję **Nowa grupa** w okienku **Wszystkie grupy**.
   ![Zrzut ekranu przedstawiający witrynę Azure Portal z wybraną pozycją Nowa grupa](./media/groups-add-new.png)
4. Dla pozycji **Typ grupy** wybierz jedną z następujących opcji:
    - **Zabezpieczenia**: grupy zabezpieczeń to odpowiedni zasób do użycia podczas wypełniania grup użytkowników. Grupy zabezpieczeń określają, kto ma dostęp do określonych zasobów, dlatego można je łatwo przekształcić w grupy użytkowników usługi Intune. Wszystkie grupy zabezpieczeń, które są synchronizowane z usługi Active Directory do usługi Azure Active Directory albo które są tworzone bezpośrednio w usłudze Azure Active Directory za pośrednictwem centrum administracyjnego usługi Office 365 lub usługi Azure Portal, są dostępne w momencie tworzenia grup użytkowników w usłudze Intune.
    - **Office 365**

5. Wpisz wartości **Nazwa** i **Opis** dla nowej grupy. Te właściwości są wyświetlane tylko w portalu zarządzania i nie są widoczne dla użytkowników.

6. Wybierz opcję w obszarze **Typ członkostwa**:
   - **Przypisane**, aby utworzyć grupę z ręcznie przypisanymi członkami. Dowiedz się więcej o [przypisanych grupach usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Użytkownik dynamiczny**, aby utworzyć grupę użytkowników zdefiniowaną za pomocą **zapytania dynamicznego**.
   - **Urządzenie dynamiczne**, aby utworzyć grupę urządzeń zdefiniowaną za pomocą **zapytania dynamicznego**.

   ![Zrzut ekranu przedstawiający właściwości grupy w usłudze Intune](./media/groups-add-properties.png)

   Usługa Azure AD umożliwia tworzenie grup dynamicznych na podstawie reguł, które definiują członkostwo. Dowiedz się, jak [tworzyć grupy dynamiczne oparte na atrybutach](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

7. Możesz wybrać pozycję **Włącz funkcje pakietu Office**, aby zezwolić członkom grup użytkowników na dostęp do udostępnionych aplikacji usługi Office 365. Dowiedz się więcej na temat [grup usługi Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
8. Wybierz pozycję **Utwórz**, aby dodać nową grupę.

## <a name="groups-and-policies"></a>Grupy i zasady

Podczas tworzenia grup należy wziąć pod uwagę sposób stosowania [zasad](device-compliance-get-started.md). Na przykład mogą istnieć zasady przeznaczone dla systemów operacyjnych urządzeń i zasady przeznaczone dla różnych ról w organizacji lub jednostek organizacyjnych zdefiniowanych już w usłudze Active Directory. Przydatne może być posiadanie oddzielnych grup urządzeń dla systemu iOS, Android i Windows, a także grupy użytkowników dla poszczególnych ról organizacyjnych.

Prawdopodobnie warto również utworzyć zasady domyślne dotyczące wszystkich grup i urządzeń w celu ustalenia podstawowych wymagań zgodności w firmie. Następnie można utworzyć bardziej szczegółowe zasady dla najszerszych kategorii użytkowników i urządzeń. Można na przykład utworzyć zasady poczty e-mail dla każdego systemu operacyjnego urządzenia.



## <a name="see-also"></a>Zobacz też
- [Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klasyczne grupy usługi Intune w witrynie Azure Portal](groups-get-started.md)
