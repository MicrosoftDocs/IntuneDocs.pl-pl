---
title: Konfigurowanie zasad aktualizacji systemu iOS
titleSuffix: Intune on Azure
description: "Skonfiguruj zasady aktualizacji systemu iOS, aby wymusić automatyczna instalację najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: d4af2d58ec21c54362cf451eac1a33b2088885d5
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2017
---
# <a name="configure-ios-update-policies"></a>Konfigurowanie zasad aktualizacji systemu iOS
Zasady aktualizacji systemu iOS umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS. Możesz skonfigurować dni i godziny, w których urządzenia nie powinny być aktualizowane.

## <a name="configure-the-ios-update-policy"></a>Konfigurowanie zasad aktualizacji systemu iOS
1. Przejdź do bloku usługi Intune w witrynie Azure Portal.
2. W bloku usługi **Intune** wybierz opcję **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**.
4. W bloku zasad wybierz opcję **Utwórz**, a następnie wprowadź nazwę i opis zasad.
5. Wybierz opcję **Ustawienia** > **Konfiguruj**, a następnie wprowadź szczegóły dotyczące czasu, w którym wobec urządzeń z systemem iOS nie będzie wymuszać się instalowania najnowszych aktualizacji.
6. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w bloku **Utwórz zasady aktualizacji**. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

Profil zostanie utworzony i wyświetlony w bloku zasad aktualizacji systemu iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Przypisywanie zasad aktualizacji systemu iOS do użytkowników
Aby przypisać użytkownikom zasady aktualizacji systemu iOS, wybierz skonfigurowane przez siebie zasady. Istniejące zasady można znaleźć w bloku **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**.
1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie bloku, w którym można wybrać grupy zabezpieczeń usługi Azure Active Directory i przypisać je do zasad.
2. Wybierz pozycję **Wybierz grupy**, aby otworzyć blok, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD. Wybierz pozycję **Wybierz**, aby wdrożyć zasady dla użytkowników.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji.

## <a name="change-the-restricted-days-for-the-policy"></a>Zmiana ograniczonych dni dla zasad
1. W bloku **Aktualizacje oprogramowania** wybierz opcję **Zasady aktualizacji systemu iOS**.
2. Wybierz zasady aktualizacji systemu iOS, które chcesz zaktualizować.
3. Wybierz opcję **Właściwości** i zaktualizuj informacje dotyczące ograniczonych dni.
