---
title: "Dostosowywanie widoków konsoli dla ról administratora | Microsoft Intune"
description: "Skorzystaj z tego tematu, aby filtrować widoki konsoli administracyjnej usługi Intune i umożliwić administratorom wyświetlanie tylko tych elementów, które są im potrzebne w danej roli."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 132648f4c4d13983b169fa8497deae9787fe6db5


---

# Dostosowywanie widoków konsoli usługi Intune zgodnie z rolami administratora
Można filtrować widoki konsoli administracyjnej usługi Microsoft Intune, aby umożliwić administratorom wyświetlanie tylko tych elementów, które są im potrzebne w danej roli. Na przykład można zezwolić operatorom konsoli administracyjnej tylko na aktualizację definicji złośliwego oprogramowania lub resetowanie kodu dostępu na urządzeniach. Można uzyskać taki efekt za pomocą wstępnie ustawionych **oznaczeń** przypisywanych do konkretnych użytkowników. Gdy ci użytkownicy uzyskują dostęp do konsoli administracyjnej, widzą tylko elementy odpowiednie do swojego oznaczenia.

## Jak utworzyć widok niestandardowy

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Administracja** &gt; **Administratorzy usługi**.

2.  Z listy administratorów usługi wybierz użytkownika, którego wyznaczenie chcesz zmienić, a następnie wybierz opcję **Zarządzaj dostępem**.

3.  W oknie dialogowym **Zarządzanie dostępem** wybierz poziom dostępu, który chcesz nadać wybranemu użytkownikowi. Można wybrać jedną z następujących opcji:

    -   **Pełny dostęp**
    -   **Dostęp tylko do odczytu**
    -   **Pomoc techniczna — węzeł Grupy**

    Pełny dostęp i dostęp tylko do odczytu nie wymagają wyjaśnień. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

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

Gdy skonfigurowany przez Ciebie administrator otworzy następnie konsolę administracyjną usługi Intune , otrzyma określony przez Ciebie poziom dostępu.



<!--HONumber=Jul16_HO3-->


