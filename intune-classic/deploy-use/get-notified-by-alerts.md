---
title: "Uzyskiwanie powiadomień dzięki alertom | Microsoft Docs"
description: "Dowiedz się, jak alerty pozwalają na bieżąco śledzić, co dzieje się w usłudze Microsoft Intune."
keywords: 
author: nathbarn
ms.author: angrobe
manager: angrobe
ms.date: 8/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714 0433 4bd5 a934 8d0b477f28e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune classic
ms.openlocfilehash: 1e7ad299b91fe8e258d6769eed6f199bdb7f0537
ms.sourcegitcommit: 12b2111839e648f85374c1c0db4288f08e0ef85d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2018
---
#  <a name="use-alerts-to-get-notified-by-microsoft-intune"></a>Uzyskiwanie powiadomień dzięki alertom w usłudze Microsoft Intune

[!INCLUDE[classic portal](../includes/classic-portal.md)]

Alerty pozwalają na bieżąco śledzić, co dzieje się w usłudze Microsoft Intune. Na przykład alerty mogą wyświetlać powiadomienia o następujących zdarzeniach:
- Problem z programem Exchange Connector, który ma wpływ na zarządzanie urządzeniami przenośnymi
- Znaleziono złośliwe oprogramowanie na komputerze
- Wykryto konflikt między dwiema zasadami usługi Intune
- Wdrażanie oprogramowania klienckiego usługi Intune nie powiodło się

## <a name="how-alerts-work"></a>Jak działają alerty

Alerty są generowane na podstawie **typów alertów** — zestawu wstępnie skonfigurowanych reguł wbudowanych w usługę Intune. Na przykład typ alertu **Magazyn w chmurze ma 10% lub mniej wolnego miejsca** powiadamia użytkownika, gdy kończy się miejsce do przechowywania aplikacji w chmurze. Można włączyć lub wyłączyć typy alertów i skonfigurować właściwości dla każdego typu alertu. Na przykład za pomocą powyższego typu alertów można skonfigurować:

- **Stan:** Określa, czy typ alertu jest włączony czy wyłączony.
- **Ważność:** Jak poważny jest ten alert?

|Ważność|Szczegóły|
|--|---|
|**Alert krytyczny**|Wskazuje poważny problem, który powinien być sprawdzony jak najszybciej, na przykład wykryto złośliwe oprogramowanie na komputerze.|
|**Alert ostrzegawczy**|Wskazuje problem, który obecnie nie jest poważny, ale może stać się poważny, jeśli się nim nie zajmiesz, na przykład aktualizacje zabezpieczeń oczekują na zainstalowanie.|
|**Alert informacyjny**|Wskazuje informacje, które nie są krytyczne dla działania, na przykład informacje o tym, że dostępna jest nowa wersja programu Exchange Connector.|

Inne typy alertów mogą zawierać różne elementy, które można skonfigurować, takie jak procent urządzeń, których musi dotyczyć problem, aby alert został wygenerowany.

**Gdy kryteria typu alertu zostaną spełnione, alert zostanie wygenerowany i pokazany w konsoli administracyjnej usługi Intune.**

Ponadto można skonfigurować usługę Intune do powiadamiania o wygenerowaniu alertu pocztą e-mail.

## <a name="set-up-alerts"></a>Konfigurowanie alertów

W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Administracja** &gt; **Alerty i powiadomienia**, a następnie wybierz jedno z następujących zadań:

|Zadanie|Opis|
|---|------|
|**Typy alertów**|Wybierz typ alertu, który chcesz skonfigurować, a następnie wykonaj jedną z następujących czynności:<br /><br />Wybierz pozycję **Konfiguruj**. W oknie dialogowym **Konfigurowanie typu alertu** skonfiguruj odpowiednie ustawienia, a następnie wybierz przycisk **OK**.<br /><br />**Włącz** lub **wyłącz** alert.<br /><br />Rozwiń węzeł **Typy alertów** i wybierz kategorię, aby wyświetlić tylko typy alertów z tej kategorii.|
|**Adresaci**|Wybierz pozycję **Dodaj**, aby dodać nowy adres e-mail, na który będą wysyłane skonfigurowane powiadomienia e-mail.<br /><br />Możesz również **edytować** lub **usuwać** istniejących odbiorców.<br /><br />Aby otrzymywać powiadomienia, musisz również dodać ten adres e-mail jako adresata w obszarze **Reguły powiadomień**.|
|**Reguły powiadomień**|Służą do konfigurowania reguł określających, do kogo będą wysyłane alerty w wiadomościach e-mail. Można:<br /><br />**Wybrać istniejącą regułę**   Wybierz regułę, a następnie wybierz pozycję **Wybierz adresatów**. Następnie możesz wybrać wszystkich adresatów, którzy otrzymają wiadomość e-mail po wygenerowaniu alertu spełniającego daną regułę.<br /><br />**Utworzyć nową regułę**   Wprowadź nazwę reguły, wybierz kategorie i ważność alertów stosowanych w przypadku zasad, wybierz grupy urządzeń, których dotyczy reguła, a następnie wybierz użytkowników, którzy otrzymają wiadomości e-mail po wygenerowaniu alertu.<br /><br />Możesz również **włączyć**, **wyłączyć**, **edytować**lub **usunąć** istniejącą regułę.|

## <a name="working-with-alerts"></a>Praca z alertami

Aby wyświetlić alerty w [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com), wybierz pozycję **Alerty**, a następnie typ alertu do wyświetlenia.

Użyj poniższych opcji pomagających w pracy z alertami z konsoli administratora usługi Intune.

|Opcja|Opis|
|-----|----|
|**Wyświetlanie aktywnych alertów**|Wybierz jedną z opcji:<br /><br />**Wyświetl podsumowanie alertów**   W obszarze roboczym **Pulpit nawigacyjny** najważniejsze błędy są wyświetlane w okienku alertów. Wybierz okienko, aby zobaczyć więcej szczegółowych informacji.<br /><br />Ponadto możesz wyświetlić podsumowanie alertu na stronie **Przegląd** obszaru roboczego **Alerty** .<br /><br />**Wyświetl wszystkie alerty**   W obszarze roboczym **Alerty** wybierz pozycję **Wszystkie alerty**.|
|**Wyświetlanie uwag**|Wybierz jedną z opcji:<br /><br />W obszarze roboczym **Pulpit nawigacyjny** wybierz pozycję **Powiadomienia**.<br /><br />W obszarze roboczym **Alerty** wybierz pozycję **Wszystkie alerty** &gt; **Powiadomienia**.|
|**Zamykanie alertu**|Na liście alertów wybierz alert do zamknięcia, a następnie wybierz pozycję **Zamknij alert**.<br /><br />Zamknięte alerty zostaną trwale usunięte po 90 dniach.|
|**Ponowne uaktywnianie zamkniętego alertu**|Na liście alertów z listy rozwijanej **Filtry** wybierz pozycję **Zamknięte**.<br /><br />Na liście zamkniętych alertów wybierz alert, który chcesz ponownie uaktywnić, a następnie wybierz pozycję **Uaktywnij ponownie alert**.|

Alerty usługi Intune pozostają aktywne przez 30 dni lub do czasu, aż:

- Problem, który spowodował wygenerowanie alertu, zostanie rozwiązany.
- Alert zostaje ręcznie zamknięty.

Zamknięte alerty można ponownie aktywować w ciągu 30 dni od zamknięcia. Po 30 dniach zamknięte i nieaktywne alerty są usuwane z usługi Intune.

> [!TIP]
> Jeśli ten sam alert jest generowany przez urządzenia z różnymi systemami operacyjnymi, na liście alertów może być wyświetlanych wiele wersji tego samego alertu.
