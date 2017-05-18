---
title: "Dostosowywanie widoków konsoli dla ról administratora | Microsoft Docs"
description: "Skorzystaj z tego tematu, aby filtrować widoki konsoli administracyjnej usługi Intune i umożliwić administratorom wyświetlanie tylko tych elementów, które są im potrzebne w danej roli."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: ee35fb2c8e39af099fb061211ea1fdf767230217
ms.lasthandoff: 12/30/2016


---

# <a name="customize-intune-console-views-according-to-admin-roles"></a>Dostosowywanie widoków konsoli usługi Intune zgodnie z rolami administratora

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Można filtrować widoki konsoli administracyjnej usługi Microsoft Intune, aby umożliwić administratorom wyświetlanie tylko tych elementów, które są im potrzebne w danej roli. Na przykład można zezwolić operatorom konsoli administracyjnej tylko na aktualizację definicji złośliwego oprogramowania lub resetowanie kodu dostępu na urządzeniach. Można uzyskać taki efekt za pomocą wstępnie ustawionych **oznaczeń** przypisywanych do konkretnych użytkowników. Gdy ci użytkownicy uzyskują dostęp do konsoli administracyjnej, mogą zobaczyć tylko elementy odpowiednie do swojego oznaczenia.

## <a name="to-create-a-custom-view"></a>Aby utworzyć widok niestandardowy

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Administracja** &gt; **Administratorzy usługi**.

2.  Z listy administratorów usługi wybierz użytkownika, którego wyznaczenie chcesz zmienić, a następnie wybierz opcję **Zarządzaj dostępem**.

3.  W oknie dialogowym **Zarządzanie dostępem** wybierz poziom dostępu, który chcesz nadać wybranemu użytkownikowi. Można wybrać jedną z następujących opcji:

    -   **Pełny dostęp**
    -   **Dostęp tylko do odczytu**
    -   **Pomoc techniczna — węzeł Grupy**

    Pełny dostęp i dostęp tylko do odczytu nie wymagają wyjaśnień. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

    **Pomoc techniczna — węzeł Grupy** ogranicza elementy, które administrator może zobaczyć, i zadania, które może wykonać, do następujących:

    -   Wyświetlać listy użytkowników i urządzeń. Administrator nie może używać filtrów do modyfikowania widoku. Natomiast Ty możesz użyć filtrowania grup w celu modyfikacji tego, co administrator może zobaczyć. Aby uzyskać więcej informacji, zobacz [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Drukować listę użytkowników i urządzeń.

    -   Eksportować listę użytkowników i urządzeń

    -   Wyświetlać właściwości użytkownika lub urządzenia.

    -   Wykonywać następujące zadania zdalne:

        -   Uruchamianie pełnego skanowania pod kątem złośliwego oprogramowania

        -   Uruchamianie szybkiego skanowania pod kątem złośliwego oprogramowania

        -   Ponowne uruchamianie komputera

        -   Aktualizacja definicji złośliwego oprogramowania

        -   Odświeżanie zasad

        -   Odświeżanie magazynu

        -   Zdalne blokowanie urządzenia

        -   Resetowanie kodu dostępu

Gdy skonfigurowany przez Ciebie administrator otworzy następnie konsolę administracyjną usługi Intune, otrzyma określony przez Ciebie poziom dostępu.

