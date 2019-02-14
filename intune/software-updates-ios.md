---
title: Konfigurowanie zasad aktualizacji oprogramowania systemu iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune utwórz lub dodaj zasady konfiguracji ograniczające automatyczną instalację aktualizacji oprogramowania na urządzeniach z systemem iOS zarządzanych lub nadzorowany przez usługę Intune. Możesz wybrać datę i godzinę, kiedy aktualizacje mają nie być instalowane. Możesz także przypisać te zasady do grup, użytkowników lub urządzeń i sprawdzać, czy wystąpiły błędy instalacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: cce77976ea0cb31596ca0a1fd6c4becc9e3cee34
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55833603"
---
# <a name="configure-ios-update-policies-in-intune"></a>Konfigurowanie zasad aktualizacji systemu iOS w usłudze Intune

Zasady aktualizacji oprogramowania umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji systemu operacyjnego na urządzeniach nadzorowanych z systemem iOS. Ta funkcja jest dostępna tylko na urządzeniach nadzorowanych. Podczas konfigurowania zasad możesz dodać dni i godziny, kiedy nie chcesz, aby na urządzeniach były instalowane aktualizacje. 

Urządzenie sprawdza zasady usługi Intune miej więcej co 8 godzin. Jeśli aktualizacja jest dostępna i nie jest to czas zastrzeżony, urządzenie pobiera i instaluje najnowszą aktualizację systemu operacyjnego. Aktualizacja urządzenia nie wymaga interakcji użytkownika. Zasady nie uniemożliwiają użytkownikom ręcznego aktualizowania systemu operacyjnego.

Ta funkcja obsługuje urządzenia z systemem iOS w wersji 10.3 lub nowszej. Ustawienie opóźnienia jest dostępne w systemie iOS w wersji 11.3 i nowszych.

## <a name="configure-the-policy"></a>Konfigurowanie zasad
1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aktualizacje oprogramowania** > **Zasady aktualizacji dla systemu iOS** > **Utwórz**.
4. Wprowadź nazwę i opis zasad.
5. Wybierz pozycję **Ustawienia**. 

    Wprowadź szczegóły dotyczące czasu, kiedy na urządzeniach z systemem iOS nie jest wymuszana instalacja najnowszych aktualizacji. Te ustawienia tworzą przedział czasu z ograniczeniami. Możesz skonfigurować **dni** tygodnia, **strefę czasową**, **godzinę rozpoczęcia**, **godzinę zakończenia** oraz to, czy **opóźniać widoczność aktualizacji oprogramowania (w dniach)**, aby wprowadzić użytkowników. Możesz wybrać zakres opóźnienia aktualizacji oprogramowania z przedziału od 1 do 90 dni. Po upływie czasu opóźnienia użytkownicy otrzymują powiadomienie o aktualizacji do najnowszej wersji systemu operacyjnego dostępnej w momencie wyzwolenia opóźnienia. Aby zrezygnować z ustawienia opóźnienia aktualizacji oprogramowania, wprowadź wartość 0. Te ustawienia aktualizacji będą stosowane tylko na nadzorowanych urządzeniach z systemem iOS.
  
    Na przykład jeśli system iOS 12.a jest dostępny **1 stycznia** i ustawienie **Opóźnij aktualizacje systemu operacyjnego** ma wartość **5 dni**, ta konkretna wersja nie będzie wyświetlana jako dostępna aktualizacja na żadnym urządzeniu użytkownika końcowego przypisanym do tego profilu. **Szóstego dnia** po wydaniu aktualizacja będzie wyświetlana jako dostępna, a wszyscy użytkownicy końcowi będą mogli zainicjować aktualizację.


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

