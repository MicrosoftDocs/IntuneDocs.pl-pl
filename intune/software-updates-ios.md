---
title: "Konfigurowanie zasad aktualizacji systemu iOS w usłudze Microsoft Intune"
titlesuffix: 
description: "Skonfiguruj zasady aktualizacji systemu iOS, aby wymusić automatyczna instalację najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Konfigurowanie zasad aktualizacji systemu iOS w usłudze Microsoft Intune
Zasady aktualizacji systemu iOS umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS. Możesz skonfigurować dni i godziny, w których urządzenia nie powinny być aktualizowane.

## <a name="configure-the-ios-update-policy"></a>Konfigurowanie zasad aktualizacji systemu iOS
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
2. W okienku usługi **Intune** wybierz pozycję **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**.
4. W okienku zasad wybierz pozycję **Utwórz**, a następnie wprowadź nazwę i opis zasad.
5. Wybierz opcję **Ustawienia** > **Konfiguruj**, a następnie wprowadź szczegóły dotyczące czasu, w którym wobec urządzeń z systemem iOS nie będzie wymuszać się instalowania najnowszych aktualizacji.
6. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w okienku **Tworzenie zasad aktualizacji**. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

Profil zostanie utworzony i wyświetlony w okienku listy zasad aktualizacji systemu iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Przypisywanie zasad aktualizacji systemu iOS do użytkowników
Aby przypisać użytkownikom zasady aktualizacji systemu iOS, wybierz skonfigurowane przez siebie zasady. Istniejące zasady można znaleźć w okienku **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**.
1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Zostanie otwarte okienko, w którym można wybrać grupy zabezpieczeń usługi Azure Active Directory i przypisywać je do zasad.
2. Wybierz pozycję **Wybrane grupy**, aby otworzyć okienko, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.
3. Wybierz pozycję **Zapisz**, aby wdrożyć zasady dla użytkowników.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji.

## <a name="change-the-restricted-days-for-the-policy"></a>Zmiana ograniczonych dni dla zasad
1. W okienku **Aktualizacje oprogramowania** wybierz pozycję **Zasady aktualizacji systemu iOS**.
2. Wybierz zasady aktualizacji systemu iOS, które chcesz zaktualizować.
3. Wybierz opcję **Właściwości** > **Ustawienia** i zaktualizuj informacje dotyczące ograniczonych dni.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Monitorowanie urządzeń ze starszymi wersjami systemu iOS
<!-- 1352223 -->
Raport **Nieaktualne urządzenia z systemem iOS** jest dostępny z poziomu okienka **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS i których nie można było zaktualizować. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie.
