---
title: Konfigurowanie zasad aktualizacji oprogramowania systemu iOS w usłudze Microsoft Intune
titlesuffix: ''
description: Skonfiguruj zasady aktualizacji systemu iOS, aby wymusić automatyczna instalację najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 1d4223ae4feb417f77909b320cd0295347b44461
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31836592"
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Konfigurowanie zasad aktualizacji systemu iOS w usłudze Microsoft Intune

Zasady aktualizacji oprogramowania umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji systemu operacyjnego na urządzeniach nadzorowanych z systemem iOS 10.3 lub nowszym. Ta funkcja jest dostępna tylko na urządzeniach nadzorowanych. Możesz skonfigurować dni i godziny, w których urządzenia nie powinny być aktualizowane. 

Gdy urządzenie się melduje, co około 8 godzin, jeśli jest dostępna aktualizacja i nie jest to zastrzeżony czas, urządzenie podejmie próbę pobrania i zainstalowania najnowszej aktualizacji systemu operacyjnego. Aktualizacja urządzenia nie wymaga interakcji użytkownika. Zasady nie uniemożliwiają użytkownikom aktualizowania systemu operacyjnego.

## <a name="configure-the-ios-update-policy"></a>Konfigurowanie zasad aktualizacji systemu iOS
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku usługi **Intune** wybierz pozycję **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**.
4. W okienku zasad wybierz pozycję **Utwórz**, a następnie wprowadź nazwę i opis zasad.
5. Wybierz opcję **Ustawienia** > **Konfiguruj**, a następnie wprowadź szczegóły dotyczące czasu, w którym wobec urządzeń z systemem iOS nie będzie wymuszać się instalowania najnowszych aktualizacji. Skonfigurować możesz dni tygodnia, strefę czasową, godzinę rozpoczęcia i godzinę zakończenia.
6. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w okienku **Tworzenie zasad aktualizacji**. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

Profil zostanie utworzony i wyświetlony w okienku listy zasad aktualizacji systemu iOS. Zarządzanie urządzeniami przenośnymi firmy Apple nie umożliwia wymuszenia instalacji aktualizacji przez urządzenie o wybranej godzinie lub w wybranym dniu. 

## <a name="change-the-restricted-times-for-the-policy"></a>Zmiana zastrzeżonego czasu dla zasad

1.  W bloku **Aktualizacje oprogramowania** wybierz opcję **Zasady aktualizacji systemu iOS**.
2.  Wybierz zasady aktualizacji systemu iOS, które chcesz zaktualizować.
3.  Wybierz pozycję **Właściwości** i zaktualizuj informacje dotyczące zastrzeżonego czasu.
4.  Wybieranie dni tygodnia
5.  Strefa czasowa, w której te zasady zostaną zastosowane
6.  Godzina rozpoczęcia i zakończenia w przypadku godzin zabronionych

## <a name="assign-an-ios-update-policy-to-users"></a>Przypisywanie zasad aktualizacji systemu iOS do użytkowników

Aby przypisać użytkownikom zasady aktualizacji systemu iOS, wybierz skonfigurowane przez siebie zasady. Istniejące zasady można znaleźć w okienku **Aktualizacje oprogramowania** > **Zasady aktualizacji systemu iOS**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Zostanie otwarte okienko, w którym można wybrać grupy zabezpieczeń usługi Azure Active Directory i przypisywać je do zasad.
2. Wybierz pozycję **Wybrane grupy**, aby otworzyć okienko, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD. Określ, kto ma dostęp do zasad, przypisując grupy do dołączenia oraz do wykluczenia.
3. Wybierz pozycję **Zapisz**, aby wdrożyć zasady dla użytkowników.

Zasady zostały zastosowane do użytkowników lub urządzeń. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji. Te zasady obsługują również urządzenia bez użytkowników.

## <a name="monitor-ios-device-installation-failures"></a>Monitorowanie niepowodzeń instalacji na urządzeniach z systemem iOS
<!-- 1352223 -->
Raport **Niepowodzenia instalacji na urządzeniach z systemem iOS** jest dostępny z poziomu okienka **Aktualizacje oprogramowania**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS, które podjęły próbę przeprowadzenia aktualizacji oraz których nie można było zaktualizować. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. Aktualne urządzenia w dobrej kondycji nie będą wyświetlane na liście. „Aktualne” oznacza urządzenie korzystające z najnowszej aktualizacji, którą obsługuje.

