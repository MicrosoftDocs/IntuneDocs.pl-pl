---
# required metadata

title: Zarządzanie alertami | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zarządzanie alertami w usłudze Microsoft Intune
Obszar roboczy **Alerty** w konsoli administracyjnej usługi Intune pozwala ocenić ogólną kondycję urządzeń w Twojej organizacji i zidentyfikować problemy.

#### Aby wyświetlić aktywne alerty

1.  W konsoli administracyjnej usługi Intune wykonaj jedną z następujących czynności:

    -   **Aby wyświetlić ogólne informacje o alertach**, w tym trzy najważniejsze alerty i łączną liczbę aktywnych alertów, kliknij pozycję **Przegląd systemu**. Możesz kliknąć linki w tych alertach, aby przejść do bardziej szczegółowych informacji.

    -   **Aby wyświetlić dane podsumowania alertów**, kliknij kolejno pozycje **Alerty &gt; Przegląd**. Na stronie **Przegląd alertów** w obszarze **Podsumowanie typów alertów** jest wyświetlane podsumowanie alertów. Alerty krytyczne są wyświetlane jako pierwsze. Możesz kliknąć linki w tych alertach, aby przejść do bardziej szczegółowych informacji.

        > [!NOTE]
        > W niektórych przypadkach określony typ alertu może pojawiać się wielokrotnie na liście **Podsumowanie typów alertów**.
        > 
        > N a tej liście mogą się na przykład pojawić poniższe wystąpienia typu alertu Wolne miejsce na dysku logicznym:
        > 
        > -   3 — Wolne miejsce na dysku logicznym
        > -   2 — Wolne miejsce na dysku logicznym
        > 
        > Dzieje się tak, gdy ten sam typ alertu zostanie wygenerowany dla urządzeń z różnymi systemami operacyjnymi. W tym przykładzie pierwsze wystąpienie typu alertu Wolne miejsce na dysku logicznym, 3 — Wolne miejsce na dysku logicznym, mogło zostać wygenerowane przez komputery z systemem Windows® 7. Drugie wystąpienie typu alertu Wolne miejsce na dysku logicznym mogło zostać wygenerowane przez komputery z systemem Windows Vista®.

    -   **Aby wyświetlić wszystkie aktywne alerty**, kliknij kolejno pozycje **Alerty &gt; Wszystkie alerty**. Na stronie **Alerty** zostanie wyświetlona lista wszystkich aktywnych alertów, która zawiera następujące kolumny:

        1.  **Nazwa** — nazwa typu alertu, który wygenerował alert.

        2.  **Źródło** — link do źródła alertu. Jeśli dla progu wyświetlania typu alertu ustawiono wartość **Wyświetl wszystko**, link ten będzie wyświetlać pojedyncze urządzenie. Jeśli dla progu wyświetlania typu alertu ustawiono określoną wartość, link ten wyświetla listę wszystkich urządzeń, których dotyczy alert.

        3.  **Ostatnia aktualizacja** — wskazuje godzinę ostatniej modyfikacji alertu. Jeśli alert został zamknięty, wyświetlany jest czas zamknięcia alertu.

        4.  **Ważność** — wskazuje ważność alertu.

## Wyświetlanie alertów tablicy powiadomień
Alerty tablicy powiadomień udostępniają ważne zawiadomienia dotyczące usługi, na przykład informacje o zbliżającym się uaktualnieniu, konserwacji lub przestoju usługi. Korzystając z poniższej procedury, możesz przeglądać alerty tablicy powiadomień i zarządzać nimi .

#### Aby wyświetlić alerty tablicy powiadomień i zarządzać nimi

1.  W konsoli administracyjnej usługi Intune kliknij pozycję **Przegląd systemu**.

2.  Ważne zawiadomienia dotyczące usługi są wyświetlane w obszarze **Tablica powiadomień**.

3.  Aby wyeksportować alert tablicy powiadomień do pliku CSV (pliku z wartościami rozdzielanymi przecinkami) lub pliku HTML, w witrynie kliknij kolejno pozycje **Alerty &gt; Wszystkie alerty &gt; Powiadomienia**. Wybierz powiadomienie, kliknij ikonę eksportowania listy, a następnie postępuj zgodnie z instrukcjami.

## Przeglądanie stanów usługi Intune
W obszarze roboczym **Przegląd systemu** przejrzyj podsumowania stanów systemu dotyczące programu Endpoint Protection, aktualizacji, kondycji agenta, zasad i oprogramowania, aby zidentyfikować problemy wymagające Twojej natychmiastowej uwagi i ustalić ich priorytety. Link do podsumowania **Stan usługi** jest również udostępniany w komunikatach o błędach, gdy działanie systemu zostanie zakłócone. W podsumowaniu **Stan usługi** są wyświetlane szczegóły dotyczące problemów w poszczególnych lokalizacjach, a także godzina ostatniej aktualizacji podsumowania.

#### Aby wyświetlić stan subskrypcji

1.  W konsoli administracyjnej usługi Intune kliknij pozycję **Przegląd systemu**.

2.  W obszarze **Stan systemu** możesz zbadać stan poszczególnych składników usługi Microsoft Intune. Wiele elementów zawiera linki umożliwiające przejście do bardziej szczegółowych informacji. Na przykład w obszarze **Endpoint Protection** wybranie liczby wystąpień spowoduje wyświetlenie obszaru roboczego **Endpoint Protection** zawierającego listę wykrytego złośliwego oprogramowania. Wybranie liczby urządzeń spowoduje wyświetlenie obszaru roboczego **Grupy** zawierającego listę urządzeń, na których wykryto złośliwe oprogramowanie.

## Zamykanie i ponowne uaktywnianie alertów
Alerty usługi Intune pozostają aktywne, dopóki nie wystąpi jedno z poniższych zdarzeń:

-   Problem, który spowodował wygenerowanie alertu, zostaje rozwiązany .

-   Alert zostaje ręcznie zamknięty.

-   Mija 5 dni od wygenerowania alertu. Po upływie 45 dni alert wygasa i zostaje automatycznie zamknięty.

Alerty oznaczone jako zamknięte są trwale usuwane po 90 dniach.

#### Aby ręcznie zamknąć alert

1.  W konsoli administracyjnej usługi Intune wykonaj jedną z następujących czynności:

    1.  **Aby zamknąć alert z poziomu listy alertów** — kliknij kolejno pozycje **Alerty &gt; Wszystkie alerty**. Wybierz alert, a następnie kliknij pozycję **Zamknij alert**.

    2.  **Aby zamknąć alert dla określonego urządzenia** — kliknij kolejno pozycje **Grupy &gt; Wszystkie urządzenia**. Wybierz urządzenie i kliknij pozycję **Wyświetl właściwości**. Następnie na karcie **Alerty** wybierz alert i kliknij pozycję **Zamknij alert**.

    3.  **Aby zamknąć alert tablicy powiadomień** — kliknij pozycję **Przegląd systemu**. Kliknij ikonę **X** obok alertu tablicy powiadomień.

#### Aby wyświetlić i ponownie uaktywnić zamknięte alerty

1.  W konsoli administracyjnej usługi Intune kliknij kolejno pozycje **Alerty &gt; Wszystkie alerty**..

2.  Na liście **Filtry** kliknij pozycję **Zamknięte**.

    W okienku listy zarządzania są wyświetlane nazwy alertów oraz dodatkowe informacje o alertach . Szczegóły wybranego alertu są wyświetlane w okienku podglądu.

3.  Aby ponownie uaktywnić wybrany alert, kliknij pozycję **Uaktywnij ponownie alert**.

### Zobacz także
[Bądź na bieżąco dzięki alertom w usłudze Microsoft Intune](get-notified-by-microsoft-intune-alerts.md)



<!--HONumber=May16_HO1-->


