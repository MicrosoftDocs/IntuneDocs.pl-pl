---
title: Zarządzanie łączeniem użytkownik-urządzenie dla komputerów z systemem Windows
titlesuffix: Microsoft Intune
description: Jak połączyć użytkownika z komputerem z systemem Windows zarządzanym przez usługę Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: b0024b246ea4ce39ba2a0bc4dd6237e82f79427f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460482"
---
# <a name="manage-user-device-linking-for-windows-pcs"></a>Zarządzanie łączeniem użytkownik-urządzenie dla komputerów z systemem Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Informacje w tym temacie dotyczą tylko komputerów z systemem Windows, które są zarządzane jako komputery osobiste przy użyciu oprogramowania klienckiego usługi Intune. 

Przed wdrożeniem oprogramowania dla użytkownika należy połączyć użytkownika z komputerem. Użytkownika można połączyć z wieloma komputerami, ale każdy komputer można połączyć tylko z jednym użytkownikiem. Użytkownicy są automatycznie łączeni ze wszystkimi komputerami, które są przez nich rejestrowane w usłudze Intune przy użyciu portalu firmy.

Aby połączyć użytkownika z komputerem:

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, który chcesz połączyć z użytkownikiem).

2. Wybierz komputer, który chcesz połączyć z użytkownikiem, a następnie wybierz pozycję **Połącz użytkownika**.

   W oknie dialogowym **Łączenie użytkownika** jest wyświetlana lista dostępnych użytkowników z następującymi informacjami: nazwa wyświetlana, identyfikator użytkownika i liczba komputerów, z którymi dany użytkownik jest obecnie połączony. Jeśli użytkownik został już połączony z wybranym komputerem, jego nazwa i identyfikator są wyświetlane w obszarze **Bieżący użytkownik**. Jeśli komputer nie został połączony z żadnym użytkownikiem, w obszarze **Bieżący użytkownik** zostanie wyświetlony tekst **Brak użytkownika**.

3. Wykonaj jedną z następujących czynności:

   - Aby pozostawić komputer połączony z bieżącym użytkownikiem (jeśli istnieje), wybierz pozycję **Anuluj**.

   - Aby usunąć połączenie z bieżącym użytkownikiem (jeśli istnieje), wybierz pozycję <strong>Usuń połączenie **&gt;** OK</strong>.

   - Aby połączyć komputer z nowym użytkownikiem, wybierz użytkownika na liście **Wszyscy użytkownicy**. Potwierdź, że dane użytkownika są prawidłowe, a następnie wybierz pozycję **OK**.

> [!TIP]
> Jeśli chcesz ograniczyć użytkownikom końcowym możliwość łączenia z komputerami, włącz opcję **Ogranicz użytkownikowi możliwość łączenia z komputerami** w zasadach **Ustawienia agenta usługi Microsoft Intune**.

### <a name="see-also"></a>Zobacz także

[Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta oprogramowania usługi Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
