---
title: Konfigurowanie zasad aktualizacji oprogramowania systemu iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune utwórz lub dodaj zasady konfiguracji ograniczające automatyczną instalację aktualizacji oprogramowania na urządzeniach z systemem iOS zarządzanych lub nadzorowany przez usługę Intune. Możesz wybrać datę i godzinę, kiedy aktualizacje mają nie być instalowane. Możesz także przypisać te zasady do grup, użytkowników lub urządzeń i sprawdzać, czy wystąpiły błędy instalacji.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: b9cc34b2fa45ae447a015f1b3105081041bd0afe
ms.sourcegitcommit: 0a2e737c5520c1a1dec5d732e5df52b5614b27e1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268842"
---
# <a name="configure-ios-update-policies-in-intune"></a>Konfigurowanie zasad aktualizacji systemu iOS w usłudze Intune

Zasady aktualizacji oprogramowania umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji systemu operacyjnego na urządzeniach nadzorowanych z systemem iOS. Ta funkcja jest dostępna tylko na urządzeniach nadzorowanych. Podczas konfigurowania zasad możesz dodać dni i godziny, kiedy nie chcesz, aby na urządzeniach były instalowane aktualizacje. 

Urządzenie sprawdza zasady usługi Intune miej więcej co 8 godzin. Jeśli aktualizacja jest dostępna i nie jest to czas zastrzeżony, urządzenie pobiera i instaluje najnowszą aktualizację systemu operacyjnego. Aktualizacja urządzenia nie wymaga interakcji użytkownika. Zasady nie uniemożliwiają użytkownikom ręcznego aktualizowania systemu operacyjnego.

Ta funkcja obsługuje urządzenia z systemem iOS 10.3 lub nowszym.

## <a name="configure-the-policy"></a>Konfigurowanie zasad
1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aktualizacje oprogramowania** > **Zasady aktualizacji dla systemu iOS** > **Utwórz**.
4. Wprowadź nazwę i opis zasad.
5. Wybierz pozycję **Ustawienia**. 

    Wprowadź szczegóły dotyczące czasu, kiedy na urządzeniach z systemem iOS nie jest wymuszana instalacja najnowszych aktualizacji. Te ustawienia tworzą przedział czasu z ograniczeniami. Skonfigurować możesz dni tygodnia, strefę czasową, godzinę rozpoczęcia i godzinę zakończenia.

6. Wybierz przycisk **OK**, aby zapisać zmiany. Wybierz pozycję **Utwórz**, aby utworzyć zasady.

Profil zostanie utworzony i wyświetlony na liście zasad. Zarządzanie urządzeniami mobilnymi firmy Apple nie zezwala na wymuszanie instalowania aktualizacji na urządzeniach według określonej godziny lub daty. 

## <a name="change-the-restricted-times-for-the-policy"></a>Zmiana zastrzeżonego czasu dla zasad

1. W obszarze **Aktualizacje oprogramowania** wybierz pozycję **Zasady aktualizacji dla systemu iOS**.
2. Wybierz istniejące zasady > **Właściwości**.
3. Zaktualizuj czas z ograniczeniami:

    1. Wybieranie dni tygodnia
    2. Wybierz strefę czasową, w której te zasady są stosowane
    3. Wprowadź godzinę rozpoczęcia i zakończenia w przypadku godzin zabronionych

    > [!NOTE]
    > Jeśli zarówno **Czas rozpoczęcia**, jak i **Czas zakończenia** są ustawione na godzinę 00:00, to opcja czasu konserwacji jest wyłączona.

## <a name="assign-the-policy-to-users"></a>Przypisywanie zasad do użytkowników

Istniejące zasady są przypisywane do grup, użytkowników lub urządzeń. Po przypisaniu zasady są stosowane.

1. W obszarze **Aktualizacje oprogramowania** wybierz pozycję **Zasady aktualizacji dla systemu iOS**.
2. Wybierz istniejące zasady > **Przypisania**. 
3. Wybierz grupy, użytkowników lub urządzenia usługi Azure Active Directory, które chcesz dołączyć do tych zasad lub z nich wykluczyć.
4. Wybierz pozycję **Zapisz**, aby wdrożyć zasady dla grup.

Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji. Te zasady obsługują również urządzenia bez użytkowników.

## <a name="monitor-device-installation-failures"></a>Monitorowanie niepowodzeń instalacji na urządzeniach
W obszarze <!-- 1352223 -->
**Aktualizacje oprogramowania** > **Niepowodzenia instalacji dla urządzeń z systemem iOS** jest wyświetlana lista nadzorowanych urządzeń z systemem iOS objętych zasadami aktualizacji, dla których podjęto próbę aktualizacji i które nie mogły zostać zaktualizowane. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. Aktualne urządzenia w dobrej kondycji nie są wyświetlane na liście. Stan „Aktualne” oznacza urządzenie korzystające z najnowszej aktualizacji, którą obsługuje.

