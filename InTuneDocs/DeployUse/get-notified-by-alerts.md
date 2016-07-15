---
title: "Uzyskiwanie powiadomień dzięki alertom | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e929a95d95b71e22d46e124f1a423af7046b0539
ms.openlocfilehash: f1dd166b7b1278003ac8785b8be07c29396dfe8c


---

# Uzyskiwanie powiadomień dzięki alertom w usłudze Microsoft Intune
Alerty pozwalają na bieżąco śledzić, co dzieje się w usłudze Microsoft Intune.

Na przykład alerty mogą wyświetlać powiadomienia o następujących zdarzeniach:

-   Problem z programem Exchange Connector, który ma wpływ na zarządzanie urządzeniami przenośnymi

-   Znaleziono złośliwe oprogramowanie na komputerze

-   Wykryto konflikt między dwiema zasadami usługi Intune


## Jak działają alerty
Alerty są generowane na podstawie **typów alertów** — zestawu wstępnie skonfigurowanych reguł wbudowanych w usługę Intune. Na przykład typ alertu **Magazyn w chmurze ma 10% lub mniej wolnego miejsca** powiadamia użytkownika, gdy kończy się miejsce do przechowywania aplikacji w chmurze. Można włączyć lub wyłączyć i skonfigurować właściwości dla każdego typu alertu. Na przykład za pomocą powyższego typu alertów można skonfigurować:

-   **Stan:** Określa, czy typ alertu jest włączony czy wyłączony.

-   **Ważność:** Jak poważny jest ten alert?


|Ważność|Szczegóły|
|--------|-------|
    |![Alert krytyczny](../media/Critical-Alert.jpg)|Wskazuje poważny problem, który powinien być sprawdzony jak najszybciej, na przykład jeśli wykryto złośliwe oprogramowanie na komputerze.|
    |![Alert ostrzegawczy](../media/Warning-Alert.jpg)|Wskazuje problem, który obecnie nie jest poważny, ale może stać się poważny, jeśli się nim nie zajmiesz, na przykład aktualizacje zabezpieczeń oczekujące na zainstalowanie.|
    |![Alert informacyjny](../media/Informational-Alert.jpg)|Wskazuje informacje, które nie są krytyczne dla działania, na przykład informacje o tym, że dostępna jest nowa wersja programu Exchange Connector.|

Inne typy alertów mogą zawierać różne elementy, które można skonfigurować, takie jak procent urządzeń, których musi dotyczyć problem, zanim alert zostanie wygenerowany.

**Gdy kryteria typu alertu zostaną spełnione, alert zostaje wygenerowany i wyświetlony w konsoli administracyjnej usługi Intune.**

Ponadto można skonfigurować usługę Intune do powiadamiania o wygenerowaniu alertu pocztą e-mail.

## Konfigurowanie alertów
W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja** &gt; **Alerty i powiadomienia**, a następnie wybierz jedno z następujących zadań konfiguracji:

|Zadanie|Opis|
|--------|---------------|
|**Typy alertów**|Wybierz typ alertu, który chcesz skonfigurować, a następnie wykonaj jedną z następujących czynności:<br /><br />Wybierz pozycję **Konfiguruj**. W oknie dialogowym **Konfigurowanie typu alertu** skonfiguruj odpowiednie ustawienia, a następnie wybierz przycisk **OK**.<br /><br />**Włącz** lub **wyłącz** alert.<br /><br />Rozwiń węzeł **Typy alertów** i wybierz kategorię, aby wyświetlić tylko typy alertów z tej kategorii.|
|**Adresaci**|Wybierz pozycję **Dodaj**, aby dodać nowy adres e-mail, na który będą wysyłane skonfigurowane powiadomienia e-mail.<br /><br />Możesz również **edytować** lub **usuwać** istniejących odbiorców.<br /><br />Aby otrzymywać powiadomienia, musisz również dodać ten adres e-mail jako adresata w obszarze **Reguły powiadomień**.|
|**Reguły powiadomień**|Służą do konfigurowania reguł określających, do kogo będą wysyłane alerty w wiadomościach e-mail. Można:<br /><br />**Wybrać istniejącą regułę** — wybierz regułę, a następnie wybierz pozycję **Wybierz adresatów**. Następnie możesz wybrać wszystkich adresatów, którzy otrzymają wiadomość e-mail po wygenerowaniu alertu spełniającego daną regułę.<br /><br />**Utworzyć nową regułę** — wprowadź nazwę reguły, wybierz kategorie i ważność alertów stosowanych w przypadku zasad, wybierz grupy urządzeń, których dotyczy reguła, a następnie wybierz użytkowników, którzy otrzymają wiadomości e-mail po wygenerowaniu alertu.<br /><br />Możesz również **włączyć**, **wyłączyć**, **edytować**lub **usunąć** istniejącą regułę.|

## Praca z alertami
Użyj poniższych opcji pomagających w pracy z alertami z konsoli administratora usługi Intune.

|Opcja|Opis|
|----------|---------------|
|**Wyświetlanie aktywnych alertów**|Wybierz jedną z opcji:<br /><br />**Wyświetl podsumowanie alertów** — w obszarze roboczym **Pulpit nawigacyjny** najważniejsze błędy są wyświetlane w okienku alertów. Wybierz okienko, aby zobaczyć więcej szczegółowych informacji.<br /><br />Ponadto możesz wyświetlić podsumowanie alertu na stronie **Przegląd** obszaru roboczego **Alerty** .<br /><br />**Wyświetl wszystkie alerty** — w obszarze roboczym **Alerty** wybierz pozycję **Wszystkie alerty**.|
|**Wyświetlanie uwag**|Wybierz jedną z opcji:<br /><br />W obszarze roboczym **Pulpit nawigacyjny** wybierz pozycję **Powiadomienia**.<br /><br />W obszarze roboczym **Alerty** wybierz pozycję **Wszystkie alerty** &gt; **Powiadomienia**.|
|**Zamykanie alertu**|Na liście alertów wybierz alert do zamknięcia, a następnie wybierz pozycję **Zamknij alert**.<br /><br />Zamknięte alerty zostaną trwale usunięte po 90 dniach.|
|**Ponowne uaktywnianie zamkniętego alertu**|Na liście alertów z listy rozwijanej **Filtry** wybierz pozycję **Zamknięte**.<br /><br />Na liście zamkniętych alertów wybierz alert, który chcesz ponownie uaktywnić, a następnie wybierz pozycję **Uaktywnij ponownie alert**.|
Alerty usługi Intune pozostają aktywne do czasu, aż:

-   Problem, który spowodował wygenerowanie alertu, zostanie rozwiązany.

-   Alert zostanie ręcznie zamknięty.

-   Upłynie 45 dni od czasu wygenerowania alertu

> [!TIP]
> Jeśli ten sam alert jest generowany przez urządzenia z różnymi systemami operacyjnymi, na liście alertów może być wyświetlanych wiele wersji tego samego alertu.

### Zobacz także
[Monitorowanie i raporty w usłudze Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


