---
title: Konfigurowanie zasad aktualizacji oprogramowania systemu iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune utwórz lub dodaj zasady konfiguracji ograniczające automatyczną instalację aktualizacji oprogramowania na urządzeniach z systemem iOS zarządzanych lub nadzorowany przez usługę Intune. Możesz wybrać datę i godzinę, kiedy aktualizacje mają nie być instalowane. Możesz także przypisać te zasady do grup, użytkowników lub urządzeń i sprawdzać, czy wystąpiły błędy instalacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf07f942feeab0a73c01625f90c04ec3b989c1c2
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044853"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Dodawanie zasad aktualizacji oprogramowania dla systemu iOS w usłudze Intune

Zasady aktualizacji oprogramowania umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji systemu operacyjnego na urządzeniach nadzorowanych z systemem iOS. Podczas konfigurowania zasad możesz dodać dni i godziny, kiedy nie chcesz, aby na urządzeniach były instalowane aktualizacje. 

Ta funkcja ma zastosowanie do:

- systemu iOS w wersji 10.3 lub nowszej (w trybie nadzorowanym)

Urządzenie sprawdza zasady usługi Intune miej więcej co 8 godzin. Jeśli aktualizacja jest dostępna i nie jest to czas zastrzeżony, urządzenie pobiera i instaluje najnowszą aktualizację systemu operacyjnego. Aktualizacja urządzenia nie wymaga interakcji użytkownika. Zasady nie uniemożliwiają użytkownikom ręcznego aktualizowania systemu operacyjnego.

## <a name="configure-the-policy"></a>Konfigurowanie zasad

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Aktualizacje oprogramowania** > **Zasady aktualizacji dla systemu iOS** > **Utwórz**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź nazwę zasad aktualizacji oprogramowania. Na przykład wprowadź `iOS restricted update times`.
    - **Opis**: Wprowadź opis zasad. To ustawienie jest opcjonalne, ale zalecane.

4. Wybierz pozycję **Ustawienia > Konfiguruj**. Podaj następujące ustawienia:

    - **Wybierz czas, aby zapobiegać instalowaniu aktualizacji**: Określ ograniczony horyzont czasowy, w którym nie będzie stosowane wymuszanie instalacji aktualizacji. 
      - Nocne bloki nie są obsługiwane i mogą nie działać. Na przykład nie należy konfigurować zasad z opcją *Godzina rozpoczęcia* ustawioną na godzinę 20:00 i opcją *Godzina zakończenia* ustawioną na godzinę 6:00.
      - Zasada, która rozpoczyna się o godzinie 12:00 i kończy się o godzinie 12:00, jest wartościowana jako 0 godzin, a nie 24 godziny, co powoduje, że nie są nakładane żadne ograniczenia.

      Podczas ustawiania przedziału czasu z ograniczeniami wprowadź następujące informacje:

      - **Dni**: Wybierz dni tygodnia, w które aktualizacje nie będą instalowane. Na przykład zaznacz pozycje Poniedziałek, Środa i Piątek, aby zapobiec instalowaniu aktualizacji w te dni.
      - **Strefa czasowa**: Wybierz strefę czasową.
      - **Godzina rozpoczęcia**: Wybierz godzinę rozpoczęcia horyzontu czasowego z ograniczeniami. Na przykład wprowadzenie wartości 5:00 spowoduje, że aktualizacje nie będą instalowane począwszy od godziny 5:00.
      - **Godzina zakończenia**: Wybierz godzinę zakończenia horyzontu czasowego z ograniczeniami. Na przykład wprowadzenie wartości 1:00 spowoduje, że aktualizacje będą mogły być instalowane od godziny 1:00.

    - **Opóźnij widoczność aktualizacji oprogramowania dla użytkowników końcowych bez żadnych zmian zaplanowanych aktualizacji (dni)**: 

      **To ustawienie zostało przeniesione do obszaru [Ograniczenia dotyczące urządzeń](device-restrictions-ios.md#general). Zostanie ono usunięte z tej lokalizacji w portalu**. W tym miejscu można wprowadzać tymczasowe zmiany istniejących zasad. W ciągu około miesiąca to ustawienie zostanie usunięte z istniejących zasad.

      Aby ograniczyć wpływ, zalecamy następujące działania:
        - Usuń istniejące zasady z tej lokalizacji w portalu.
        - Utwórz nowe [zasady ograniczeń urządzenia](device-restrictions-ios.md#general).
        - Ustaw docelowych użytkowników takich samych jak w oryginalnych zasadach.

      Jeśli występuje konflikt, to ustawienie nie będzie miało żadnego znaczenia, *chyba że* te dwie wartości są identyczne. Aby uniknąć konfliktu, zmień lub usuń istniejące zasady z tej lokalizacji w portalu.
      > [! Ważne]  
      > Zasada, która ma *Godzinę rozpoczęcia* i *Godzinę zakończenia* ustawioną na 12:00, jest wartościowana jako 0 godzin, a nie 24 godziny. W takim przypadku nie będą wprowadzane żadne ograniczenia.  

5. Wybierz opcję **OK** > **Utwórz**, aby zapisać zmiany i utworzyć zasady.

Profil zostanie utworzony i wyświetlony na liście zasad.

Aby uzyskać wskazówki od członków zespołu pomocy technicznej usługi Intune, zobacz [Delay visibility of software updates in Intune for supervised devices (Opóźnianie widoczności aktualizacji oprogramowania w usłudze Intune w przypadku urządzeń nadzorowanych)](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Zarządzanie urządzeniami mobilnymi firmy Apple nie zezwala na wymuszanie instalowania aktualizacji na urządzeniach według określonej godziny lub daty.

## <a name="change-the-restricted-times-for-the-policy"></a>Zmiana zastrzeżonego czasu dla zasad

1. W obszarze **Aktualizacje oprogramowania** wybierz pozycję **Zasady aktualizacji dla systemu iOS**.
2. Wybierz istniejące zasady > **Właściwości**.
3. Zaktualizuj czas z ograniczeniami:

    1. Wybieranie dni tygodnia
    2. Wybierz strefę czasową, w której te zasady są stosowane
    3. Wprowadź godzinę rozpoczęcia i zakończenia w przypadku godzin zabronionych

    > [!NOTE]
    > Jeśli pozycje **Godzina rozpoczęcia** i **Godzina zakończenia** są ustawione na wartość 0:00, usługa Intune nie będzie stosowała ograniczeń dotyczących instalowania aktualizacji. Oznacza to, że wszystkie konfiguracje dla opcji **Wybierz czas, aby zapobiegać instalowaniu aktualizacji** będą ignorowane, a aktualizacje będą mogły być instalowane w dowolnym momencie.  

## <a name="assign-the-policy-to-users"></a>Przypisywanie zasad do użytkowników

Istniejące zasady są przypisywane do grup, użytkowników lub urządzeń. Po przypisaniu zasady są stosowane.

1. W obszarze **Aktualizacje oprogramowania** wybierz pozycję **Zasady aktualizacji dla systemu iOS**.
2. Wybierz istniejące zasady > **Przypisania**. 
3. Wybierz grupy, użytkowników lub urządzenia usługi Azure Active Directory, które chcesz dołączyć do tych zasad lub z nich wykluczyć.
4. Wybierz pozycję **Zapisz**, aby wdrożyć zasady dla grup.

Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji. Te zasady obsługują również urządzenia bez użytkowników.

## <a name="monitor-device-installation-failures"></a>Monitorowanie niepowodzeń instalacji na urządzeniach
<!-- 1352223 -->
W obszarze **Aktualizacje oprogramowania** > **Niepowodzenia instalacji dla urządzeń z systemem iOS** jest wyświetlana lista nadzorowanych urządzeń z systemem iOS objętych zasadami aktualizacji, dla których podjęto próbę aktualizacji i które nie mogły zostać zaktualizowane. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. Aktualne urządzenia w dobrej kondycji nie są wyświetlane na liście. Stan „Aktualne” oznacza urządzenie korzystające z najnowszej aktualizacji, którą obsługuje.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
