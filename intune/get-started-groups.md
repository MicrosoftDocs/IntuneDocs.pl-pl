---
title: Wprowadzenie do grup
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
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-groups"></a>Wprowadzenie do grup

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

Usługa Microsoft Intune używa usługi Azure Active Directory (Azure AD) do [zarządzanie dostępem do zasobów firmy](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). Ten dostęp jest kontrolowany przy użyciu ról w katalogu. Usługa Intune następnie zarządza tym dostępem dla urządzeń przenośnych, co umożliwia członkom tej grupy dostęp do zasobów.

__Jak utworzyć grupę?__

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Przy użyciu funkcji **Wyszukiwanie zasobów** wyszukaj **użytkowników i grupy**.
3. Po otwarciu bloku **Użytkownicy i grupy** wybierz opcję **Wszystkie grupy**.
4. W bloku **Użytkownicy i grupy — wszystkie grupy** wybierz polecenie **Nowa grupa**.
5. W bloku **Grupa** dodaj **nazwę** i **opis** grupy.
6. Ustaw opcję **Typ członkostwa** na wartość **Przypisany**. Nie włączaj opcji **Włącz funkcje pakietu Office** dla grupy testowej.
7. Kliknij przycisk **Utwórz**.

Jeśli grupa została pomyślnie utworzona, powinna zostać wyświetlona na liście **Wszystkie grupy**. Jeśli grupa nie znajduje się na tej liście, spróbuj utworzyć inną grupę.
