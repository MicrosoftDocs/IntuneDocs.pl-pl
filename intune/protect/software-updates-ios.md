---
title: Konfigurowanie zasad aktualizacji oprogramowania systemu iOS/iPadOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune utwórz lub dodaj zasady konfiguracji ograniczające automatyczną instalację aktualizacji oprogramowania na urządzeniach z systemem iOS/iPadOS. Możesz wybrać datę i godzinę, kiedy aktualizacje mają nie być instalowane. Możesz także przypisać te zasady do grup, użytkowników lub urządzeń i sprawdzać, czy wystąpiły błędy instalacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/20/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77d4a90bb2eaa8434ff9c05362dcb0d7cb270651
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576155"
---
# <a name="add-iosipados-software-update-policies-in-intune"></a>Dodawanie zasad aktualizacji oprogramowania dla systemu iOS/iPadOS w usłudze Intune

Zasady aktualizacji oprogramowania umożliwiają wymuszenie automatycznej instalacji aktualizacji systemu operacyjnego na urządzeniach nadzorowanych z systemem iOS/iPadOS. Nadzorowane urządzenia to te, które zostały zarejestrowane przy użyciu usługi Apple Business Manager lub Apple School Manager. Konfigurując zasady wdrażania aktualizacji, można wykonać następujące czynności:

- Wybranie wdrażania *najnowszej aktualizacji*, która jest dostępna, lub wybranie wdrażania starszej aktualizacji według numeru wersji aktualizacji, jeśli nie chce się wdrażać najnowszej aktualizacji. W przypadku wybrania wdrażania starszej aktualizacji należy również ustawić zasady konfiguracji urządzenia, aby ograniczyć widoczność aktualizacji oprogramowania.
- Określenie harmonogramu, który wyznacza czas instalowania aktualizacji. Harmonogramy mogą być równie proste jak instalowanie aktualizacji przy następnym zameldowaniu urządzenia, albo obejmować utworzenie zakresów dat i godzin, w których aktualizacje mogą być instalowane lub w których instalacja jest zablokowana.

Ta funkcja ma zastosowanie do:

- systemu iOS w wersji 10.3 lub nowszej (w trybie nadzorowanym)

Domyślnie urządzenie melduje się w usłudze Intune mniej więcej co 8 godzin. Jeśli aktualizacja jest dostępna w ramach zasad aktualizacji, urządzenie pobierze aktualizację. Następnie urządzenie zainstaluje aktualizację przy następnym zameldowaniu się w ramach konfiguracji harmonogramu. Chociaż proces aktualizacji nie obejmuje zwykle żadnej interakcji z użytkownikiem, jeśli urządzenie ma kod dostępu, użytkownik musi wprowadzić go w celu rozpoczęcia aktualizacji oprogramowania. Profile nie uniemożliwiają użytkownikom ręcznego aktualizowania systemu operacyjnego. Użytkownikom można uniemożliwić ręczne aktualizowanie systemu operacyjnego przy użyciu zasad konfiguracji urządzeń w celu ograniczenia widoczności aktualizacji oprogramowania.

## <a name="configure-the-policy"></a>Konfigurowanie zasad

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Zasady aktualizacji dla systemu iOS/iPadOS** > **Utwórz profil**.
3. Na karcie **Podstawowe** podaj nazwę tych zasad, podaj opis (opcjonalnie), a następnie wybierz przycisk **Dalej**.

   ![Karta Podstawowe](./media/software-updates-ios/basics-tab.png)

4. Na karcie **Aktualizuj ustawienia zasad** skonfiguruj następujące opcje:

   1. **Wybierz wersję do zainstalowania**. Można wybrać jedną z następujących opcji:

      - *Najnowsza aktualizacja*. Spowoduje to wdrożenie ostatnio wydanej aktualizacji dla systemu iOS/iPadOS.
      - Wszystkie poprzednie wersje, które są dostępne w polu listy rozwijanej. W przypadku wybrania poprzedniej wersji należy również wdrożyć zasady konfiguracji urządzeń, aby opóźnić widoczność aktualizacji oprogramowania.

   2. **Typ harmonogramu**: Skonfiguruj harmonogram dla tych zasad:

      - *Aktualizuj przy następnym meldowaniu*: Aktualizacja zostanie zainstalowana na urządzeniu, gdy następnym razem zamelduje się ono w usłudze Intune. Jest to najprostsza opcja i nie ma żadnych dodatkowych konfiguracji.
      - *Aktualizuj w zaplanowanym czasie*: Skonfiguruj co najmniej jeden przedział czasu, w którym aktualizacja zostanie zainstalowana po zameldowaniu.
      - *Aktualizuj poza zaplanowanym czasem*: Skonfiguruj co najmniej jeden przedział czasu, w którym aktualizacje nie będą instalowane po zameldowaniu.

   3. **Harmonogram tygodniowy**: W przypadku wybrania typu harmonogramu innego niż *Aktualizuj przy następnym meldowaniu* skonfiguruj następujące opcje:

      ![Przykład wyboru aktualizacji w zaplanowanym czasie](./media/software-updates-ios/scheduled-time.png)

      - **Strefa czasowa**: Wybierz strefę czasową.
      - **Przedział czasu**: Zdefiniuj co najmniej jeden blok czasu, który ogranicza godziny instalowania aktualizacji. Rezultat poniższych opcji zależy od wybranego typu harmonogramu. W przypadku używania dnia rozpoczęcia i dnia zakończenia są obsługiwane bloki w nocy. Dostępne opcje:

        - **Dzień rozpoczęcia**: Wybierz dzień, w którym rozpoczyna się przedział harmonogramu.
        - **Godzina rozpoczęcia**: Wybierz godzinę dnia, o której rozpoczyna się przedział harmonogramu. Jeśli na przykład wybierzesz godzinę 5:00 i ustawisz typ harmonogramu *Aktualizuj w zaplanowanym czasie*, 5:00 będzie godziną, o której aktualizacje mogą zacząć być instalowane. W przypadku wybrania typu harmonogramu *Aktualizuj poza zaplanowanym czasem* 5:00 będzie godziną rozpoczęcia okresu czasu, w którym aktualizacje nie mogą być instalowane.
        - **Dzień zakończenia**: Wybierz dzień, w którym kończy się przedział harmonogramu.
        - **Godzina zakończenia**: Wybierz godzinę dnia, o której kończy się przedział harmonogramu. Jeśli na przykład wybierzesz godzinę 1:00 i ustawisz typ harmonogramu *Aktualizuj w zaplanowanym czasie*, 1:00 będzie godziną, o której aktualizacje nie mogą już być instalowane. W przypadku wybrania typu harmonogramu *Aktualizuj poza zaplanowanym czasem* 1:00 będzie godziną rozpoczęcia okresu czasu, w którym aktualizacje mogą być instalowane.

       Jeśli nie skonfigurujesz godzin rozpoczęcia ani zakończenia, konfiguracja nie będzie nakładała żadnych ograniczeń, a aktualizacje będą mogły być instalowane w dowolnym momencie.  

       > [!NOTE]
       > Aby opóźnić widoczność aktualizacji oprogramowania o określony czas na nadzorowanych urządzeniach z systemem iOS/iPadOS, skonfiguruj te ustawienia w obszarze [Ograniczenia urządzeń](../configuration/device-restrictions-ios.md#general). Zasady aktualizacji oprogramowania zastępują wszelkie ograniczenia dotyczące urządzeń. Po ustawieniu zasad aktualizacji oprogramowania i ograniczeń w celu opóźnienia widoczności aktualizacji oprogramowania urządzenie wymusza aktualizację oprogramowania zgodnie z zasadami. Ograniczenie jest stosowane, aby użytkownicy nie widzieli opcji aktualizowania urządzenia. Aktualizacja jest wypychana zgodnie z zasadami aktualizacji systemu iOS.

   Po wprowadzeniu konfiguracji w pozycji *Aktualizuj ustawienia zasad* wybierz przycisk **Dalej**.

5. Jeśli chcesz zastosować tagi do zasad aktualizacji, na karcie **Tagi zakresu** wybierz pozycję **+ Wybierz zakres tagów**, aby otworzyć okienko *Wybierz tagi*.

   - W okienku **Wybierz tagi** wybierz jeden lub większą liczbę tagów, a następnie kliknij pozycję **Wybierz**, aby dodać je do zasad i wrócić do okienka *Wybierz tagi*.

   Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**, aby przejść do karty *Przypisania*.

6. Na karcie **Przypisania** wybierz pozycję **+ Wybierz grupy do uwzględnienia**, a następnie przypisz zasady aktualizacji do co najmniej jednej grupy. Użyj opcji **+ Wybierz grupy do wykluczenia**, aby dopracować przypisanie. Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**, aby kontynuować.

   Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności aktualizacji. Te zasady obsługują również urządzenia bez użytkowników.

7. Na karcie **Przeglądanie + tworzenie** przejrzyj ustawienia i wybierz pozycję **Utwórz**, gdy wszystko będzie gotowe do zapisania zasad aktualizacji systemu iOS/iPadOS. Nowe zasady zostaną wyświetlone na liście zasad aktualizacji systemu iOS/iPadOS.

Aby uzyskać wskazówki od członków zespołu pomocy technicznej usługi Intune, zobacz [Delay visibility of software updates in Intune for supervised devices (Opóźnianie widoczności aktualizacji oprogramowania w usłudze Intune w przypadku urządzeń nadzorowanych)](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Zarządzanie urządzeniami mobilnymi firmy Apple nie zezwala na wymuszanie instalowania aktualizacji na urządzeniach według określonej godziny lub daty. Nie można używać zasad aktualizacji oprogramowania usługi Intune do zmiany na starszą lub mniej zaawansowaną wersję systemu operacyjnego na urządzeniu.

## <a name="edit-a-policy"></a>Edytowanie zasad

Istnieje możliwość edytowania istniejących zasad, w tym zmiany godzin ograniczonych:

1. Wybierz pozycję **Urządzenia** > **Zasady aktualizacji dla systemu iOS**. Wybierz zasady, które chcesz edytować.

2. Podczas wyświetlania karty **Właściwości** zasad wybierz opcję **Edytuj** dla strony zasad, którą chcesz zmodyfikować.

   ![Edytowanie zasad](./media/software-updates-ios/edit-policy.png)

3. Po wprowadzeniu zmiany wybierz opcję **Przejrzyj i zapisz** > **Zapisz**, aby zapisać zmiany, a następnie wróć do karty *Właściwości* zasad.

> [!NOTE]
> Jeśli pozycje **Godzina rozpoczęcia** i **Godzina zakończenia** są ustawione na wartość 0:00, usługa Intune nie będzie stosowała ograniczeń dotyczących instalowania aktualizacji. Oznacza to, że wszystkie konfiguracje dla opcji **Wybierz czas, aby zapobiegać instalowaniu aktualizacji** będą ignorowane, a aktualizacje będą mogły być instalowane w dowolnym momencie.

## <a name="monitor-device-installation-failures"></a>Monitorowanie niepowodzeń instalacji na urządzeniach

<!-- 1352223 -->
W obszarze **Aktualizacje oprogramowania** > **Niepowodzenia instalacji dla urządzeń z systemem iOS** jest wyświetlana lista nadzorowanych urządzeń z systemem iOS/iPadOS objętych zasadami aktualizacji, dla których podjęto próbę aktualizacji i które nie mogły zostać zaktualizowane. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. Aktualne urządzenia w dobrej kondycji nie są wyświetlane na liście. Stan „Aktualne” oznacza urządzenie korzystające z najnowszej aktualizacji, którą obsługuje.

## <a name="next-steps"></a>Następne kroki

[Monitorowanie stanu](../configuration/device-profile-monitor.md).
