---
title: Tworzenie grupy w usłudze Microsoft Intune
titleSuffix: ''
description: Umieszczaj użytkowników w grupach, aby ułatwić zarządzanie zasadami i aplikacjami, do których mogą uzyskiwać dostęp.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d039cfe5509990ff15fe8a1cb476ad44037d60df
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Tworzenie grupy w celu zarządzania użytkownikami i dostępem do danych

Grupy służą do zarządzania użytkownikami i sterowania dostępem pracowników do zasobów firmy. Te zasoby mogą być częścią katalogu lub mogą to być zasoby zewnętrzne, takie jak aplikacje SaaS lub witryny programu SharePoint.

Usługa Microsoft Intune używa usługi Azure Active Directory (Azure AD) w celu zarządzania dostępem do zasobów firmy. Ten dostęp jest kontrolowany przy użyciu ról w katalogu. Usługa Intune następnie zarządza tym dostępem dla urządzeń przenośnych, co umożliwia członkom tej grupy dostęp do zasobów.

## <a name="how-do-i-create-a-group"></a>Jak mogę utworzyć grupę?

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Po otwarciu okienka **Microsoft Intune** wybierz opcję **Grupy**.
4. W okienku **Użytkownicy i grupy — Wszystkie grupy** wybierz polecenie **Nowa grupa**.
5. W okienku **Grupa** wybierz pozycję **Typ grupy**.
5. Dodaj wartości w polach **Nazwa** i **Opis** dla grupy.
6. Ustaw opcję **Typ członkostwa** na wartość **Przypisany**. Nie włączaj opcji **Włącz funkcje pakietu Office** dla grupy testowej.
7. Wybierz **elementy członkowskie** grupy.
7. Kliknij przycisk **Utwórz**.

Jeśli grupa została pomyślnie utworzona, powinna zostać wyświetlona na liście **Wszystkie grupy**. Jeśli grupa nie znajduje się na tej liście, spróbuj utworzyć inną grupę.

## <a name="next-steps"></a>Następne kroki

[Wprowadzenie do zasad](get-started-policies.md) — utwórz zasady, aby uniemożliwić użytkownikom wykonywanie nieautoryzowanych działań na swoich urządzeniach.

## <a name="learn-more"></a>Dowiedz się więcej

* [Set enrollment restrictions using groups in Intune (Ustawianie ograniczeń rejestrowania przy użyciu grup w usłudze Intune)](groups-add.md)
* [Manage access to company resources using groups in Azure Active Directory (Zarządzanie dostępem do zasobów firmy przy użyciu grup w usłudze Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
