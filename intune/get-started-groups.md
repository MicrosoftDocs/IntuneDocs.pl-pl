---
title: Wprowadzenie do grup
titleSuffix: Azure portal
description: "Umieszczaj użytkowników w grupach, aby ułatwić zarządzanie zasadami i aplikacjami, do których mogą uzyskiwać dostęp."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63a35c04a14ebd79ac55f1dab2680d70008ee0ed
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-groups"></a>Wprowadzenie do grup

Grupy służą do zarządzania użytkownikami i sterowania dostępem pracowników do zasobów firmy. Te zasoby mogą być częścią katalogu lub mogą to być zasoby zewnętrzne, takie jak aplikacje SaaS lub witryny programu SharePoint.

Usługa Microsoft Intune używa usługi Azure Active Directory (Azure AD) w celu zarządzania dostępem do zasobów firmy. Ten dostęp jest kontrolowany przy użyciu ról w katalogu. Usługa Intune następnie zarządza tym dostępem dla urządzeń przenośnych, co umożliwia członkom tej grupy dostęp do zasobów.

## <a name="how-do-i-create-a-group"></a>Jak mogę utworzyć grupę?

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Za pomocą pola **Wyszukaj zasoby** wyszukaj usługę **Intune**.
3. Po otwarciu bloku **Microsoft Intune** wybierz opcję **Grupy**.
4. W bloku **Użytkownicy i grupy — wszystkie grupy** wybierz polecenie **Nowa grupa**.
5. W bloku **Grupa** dodaj **nazwę** i **opis** grupy.
6. Ustaw opcję **Typ członkostwa** na wartość **Przypisany**. Nie włączaj opcji **Włącz funkcje pakietu Office** dla grupy testowej.
7. Kliknij przycisk **Utwórz**.

Jeśli grupa została pomyślnie utworzona, powinna zostać wyświetlona na liście **Wszystkie grupy**. Jeśli grupa nie znajduje się na tej liście, spróbuj utworzyć inną grupę.

## <a name="next-steps"></a>Następne kroki

[Wprowadzenie do zasad](get-started-policies.md) — utwórz zasady, aby uniemożliwić użytkownikom wykonywanie nieautoryzowanych działań na swoich urządzeniach.

## <a name="learn-more"></a>Dowiedz się więcej

* [Set enrollment restrictions using groups in Intune (Ustawianie ograniczeń rejestrowania przy użyciu grup w usłudze Intune)](groups-add.md)
* [Manage access to company resources using groups in Azure Active Directory (Zarządzanie dostępem do zasobów firmy przy użyciu grup w usłudze Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
