---
title: Konfigurowanie zasad aktualizacji oprogramowania systemu iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune utwórz lub dodaj zasady konfiguracji ograniczające automatyczną instalację aktualizacji oprogramowania na urządzeniach z systemem iOS. Możesz wybrać datę i godzinę, kiedy aktualizacje mają nie być instalowane. Możesz także przypisać te zasady do grup, użytkowników lub urządzeń i sprawdzać, czy wystąpiły błędy instalacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f9750603d19d9b19697c7d2660351c4586432f6
ms.sourcegitcommit: a7c35efb31c4efd816bd4aba29240013965aee92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "73984193"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Dodawanie zasad aktualizacji oprogramowania dla systemu iOS w usłudze Intune

Zasady aktualizacji oprogramowania umożliwiają wymuszenie automatycznej instalacji najnowszej dostępnej aktualizacji systemu operacyjnego na urządzeniach nadzorowanych z systemem iOS. Podczas konfigurowania zasad możesz dodać dni i godziny, kiedy nie chcesz, aby na urządzeniach były instalowane aktualizacje.

Ta funkcja ma zastosowanie do:

- systemu iOS w wersji 10.3 lub nowszej (w trybie nadzorowanym)

Urządzenie sprawdza zasady usługi Intune miej więcej co 8 godzin. Jeśli dostępna jest aktualizacja, urządzenie pobierze ją i zainstaluje. Procedura nie zostanie przeprowadzona w ograniczonych godzinach. Chociaż proces aktualizacji nie obejmuje zwykle żadnej interakcji z użytkownikiem, jeśli urządzenie ma kod dostępu, użytkownik będzie musiał wprowadzić go w celu rozpoczęcia aktualizacji oprogramowania. Dotyczy to systemu iOS 10.3 i jego nowszych wersji. Zasady nie uniemożliwiają użytkownikom ręcznego aktualizowania systemu operacyjnego.

## <a name="configure-the-policy"></a>Konfigurowanie zasad

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Aktualizacje oprogramowania** > **Zasady aktualizacji dla systemu iOS** > **Utwórz**.
3. Na karcie **Podstawowe** podaj nazwę tych zasad, podaj opis (opcjonalnie), a następnie wybierz przycisk **Dalej**.

   ![Karta Podstawowe](./media/software-updates-ios/basics-tab.png) 

4. Na karcie **Aktualizuj ustawienia zasad** określ ograniczony horyzont czasowy, w którym nie będzie stosowane wymuszanie instalacji aktualizacji.  
   - Nocne bloki nie są obsługiwane i mogą nie działać. Na przykład nie należy konfigurować zasad z opcją *Godzina rozpoczęcia* ustawioną na godzinę 20:00 i opcją *Godzina zakończenia* ustawioną na godzinę 6:00.
   - Zasada, która rozpoczyna się o godzinie 12:00 i kończy się o godzinie 12:00, jest wartościowana jako 0 godzin, a nie 24 godziny. Ta konfiguracja nie powoduje żadnych ograniczeń.

   Podczas ustawiania przedziału czasu z ograniczeniami wprowadź następujące informacje:

   - **Dni**: Wybierz dni tygodnia, w które aktualizacje nie będą instalowane. Na przykład zaznacz pozycje Poniedziałek, Środa i Piątek, aby zapobiec instalowaniu aktualizacji w te dni.
   - **Strefa czasowa**: Wybierz strefę czasową.
   - **Godzina rozpoczęcia**: Wybierz godzinę rozpoczęcia horyzontu czasowego z ograniczeniami. Na przykład wprowadzenie wartości 5:00 spowoduje, że aktualizacje nie będą instalowane począwszy od godziny 5:00.
   - **Godzina zakończenia**: Wybierz godzinę zakończenia horyzontu czasowego z ograniczeniami. Na przykład wprowadzenie wartości 1:00 spowoduje, że aktualizacje będą mogły być instalowane od godziny 1:00.
  
   > [!IMPORTANT]  
   > Zasada, która ma *Godzinę rozpoczęcia* i *Godzinę zakończenia* ustawioną na 12:00, jest wartościowana jako 0 godzin, a nie 24 godziny. W takim przypadku nie będą wprowadzane żadne ograniczenia.  
    
   Aby opóźnić widoczność aktualizacji oprogramowania o określony czas na nadzorowanych urządzeniach z systemem iOS, skonfiguruj te ustawienia w obszarze [Ograniczenia urządzeń](../configuration/device-restrictions-ios.md#general). Zasady aktualizacji oprogramowania zastępują wszelkie ograniczenia dotyczące urządzeń. Po ustawieniu zasad aktualizacji oprogramowania i ograniczeń w celu opóźnienia widoczności aktualizacji oprogramowania urządzenie wymusza aktualizację oprogramowania zgodnie z zasadami. Ograniczenie jest stosowane, aby użytkownicy nie widzieli opcji aktualizowania urządzenia. Aktualizacja jest wypychana w przedziale czasu zgodnie z zasadami aktualizacji systemu iOS.

   Po wprowadzeniu konfiguracji w pozycji *Aktualizuj ustawienia zasad* wybierz przycisk **Dalej**. 

5. Jeśli chcesz zastosować tagi do zasad aktualizacji, na karcie **Tagi zakresu** wybierz pozycję **+ Wybierz zakres tagów**, aby otworzyć okienko *Wybierz tagi*.
   
   - W okienku **Wybierz tagi** wybierz jeden lub większą liczbę tagów, a następnie kliknij pozycję **Wybierz**, aby dodać je do zasad i wrócić do okienka *Wybierz tagi*.  

   Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**, aby przejść do karty *Przypisania*.

6. Na karcie **Przypisania** wybierz pozycję **+ Wybierz grupy do uwzględnienia**, a następnie przypisz zasady aktualizacji do co najmniej jednej grupy. Użyj opcji **+ Wybierz grupy do wykluczenia**, aby dopracować przypisanie. Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**, aby kontynuować. 

   Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji. Te zasady obsługują również urządzenia bez użytkowników.

7. Na karcie **Przeglądanie + tworzenie** przejrzyj ustawienia i wybierz pozycję **Utwórz**, gdy wszystko będzie gotowe do zapisania zasad aktualizacji systemu iOS. Nowe zasady zostaną wyświetlone na liście zasad aktualizacji systemu iOS.


Aby uzyskać wskazówki od członków zespołu pomocy technicznej usługi Intune, zobacz [Delay visibility of software updates in Intune for supervised devices (Opóźnianie widoczności aktualizacji oprogramowania w usłudze Intune w przypadku urządzeń nadzorowanych)](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Zarządzanie urządzeniami mobilnymi firmy Apple nie zezwala na wymuszanie instalowania aktualizacji na urządzeniach według określonej godziny lub daty.

## <a name="edit-a-policy"></a>Edytowanie zasad
Istnieje możliwość edytowania istniejących zasad, w tym zmiany godzin ograniczonych:

1. W pozycji **Aktualizacje oprogramowania** wybierz opcję **Zasady aktualizacji systemu iOS**, a następnie wybierz zasady, które chcesz edytować.

2. Podczas wyświetlania karty **Właściwości** zasad wybierz opcję **Edytuj** dla strony zasad, którą chcesz zmodyfikować.  
   ![Edytuj zasady](./media/software-updates-ios/edit-policy.png)   

3. Po wprowadzeniu zmiany wybierz opcję **Przejrzyj i zapisz** > **Zapisz**, aby zapisać zmiany, a następnie wróć do karty *Właściwości* zasad.  
 
> [!NOTE]
> Jeśli pozycje **Godzina rozpoczęcia** i **Godzina zakończenia** są ustawione na wartość 0:00, usługa Intune nie będzie stosowała ograniczeń dotyczących instalowania aktualizacji. Oznacza to, że wszystkie konfiguracje dla opcji **Wybierz czas, aby zapobiegać instalowaniu aktualizacji** będą ignorowane, a aktualizacje będą mogły być instalowane w dowolnym momencie.  


## <a name="monitor-device-installation-failures"></a>Monitorowanie niepowodzeń instalacji na urządzeniach
<!-- 1352223 -->
W obszarze **Aktualizacje oprogramowania** > **Niepowodzenia instalacji dla urządzeń z systemem iOS** jest wyświetlana lista nadzorowanych urządzeń z systemem iOS objętych zasadami aktualizacji, dla których podjęto próbę aktualizacji i które nie mogły zostać zaktualizowane. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. Aktualne urządzenia w dobrej kondycji nie są wyświetlane na liście. Stan „Aktualne” oznacza urządzenie korzystające z najnowszej aktualizacji, którą obsługuje.

## <a name="next-steps"></a>Następne kroki

[Monitorowanie stanu](../configuration/device-profile-monitor.md).
