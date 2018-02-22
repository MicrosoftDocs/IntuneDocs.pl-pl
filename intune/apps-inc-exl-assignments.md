---
title: "Dołączanie i wykluczanie przypisań aplikacji"
titlesuffix: Microsoft Intune
description: "Dowiedz się, jak możesz użyć usługi Intune do dołączania i wykluczania przypisań aplikacji."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune

Przy użyciu usługi Intune możesz określić, kto ma dostęp do aplikacji, przypisując grupy zarówno do dołączania, jak i wykluczania. Przypisania aplikacji można dołączać do grupy użytkowników lub urządzeń i wykluczać je z nich za pomocą kombinacji przypisań dołączania i wykluczania grupy. Po wybraniu aplikacji możesz wybrać sposób jej przypisania. Ta możliwość może być przydatna, gdy udostępniasz aplikację przez dołączenie dużej grupy, a następnie zawężasz wybranych użytkowników, wyłączając również mniejszą grupę. Mniejsza grupa może być grupą testową lub grupą wykonawczą. 

Gdy wykluczasz grupy z przypisania, musisz wykluczyć tylko grupy użytkowników lub urządzeń, ale nie kombinację tych grup. Podczas wykluczania grup usługa Intune nie uwzględnia żadnych skojarzeń użytkowników z urządzeniami. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń raczej nie przyniesie oczekiwanych rezultatów, ponieważ dołączenie będzie miało pierwszeństwo przed wykluczeniem. Jeśli na przykład aplikacja systemu iOS jest przeznaczona dla **Wszystkich użytkowników** i wyklucza **Wszystkie urządzenia iPad**, wynikiem netto będzie to, że dowolny użytkownik korzystający z urządzenia iPad nadal uzyska aplikację. Jeśli jednak aplikacja systemu iOS jest przeznaczona do **Wszystkich urządzeń** i wyklucza **Wszystkie urządzenia iPad**, wdrożenie będzie udane.  

>[!NOTE]
>Podczas ustawiania przypisania grupy do aplikacji typ **Nie dotyczy** jest przestarzały i został zastąpiony przez funkcjonalność wykluczania grupy. 
>
>Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika. Zdecydowanie zaleca się używanie tych grup dla wszystkich użytkowników i wszystkich urządzeń zamiast wszelkich grup „Wszyscy użytkownicy” lub „Wszystkie urządzenia”, które mogły zostać utworzone samodzielnie.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Dołączanie i wykluczanie grup podczas przypisywania aplikacji 
Aby przypisać aplikację do grup za pomocą dołączania i wykluczania przypisania:
1. W bloku usługi Microsoft Intune wybierz pozycję **Aplikacje mobilne**.
2. Wybierz pozycję **Aplikacje** z bloku **Aplikacje mobilne**. Zostanie wyświetlona lista dodanych aplikacji.
3. Wybierz aplikację, którą chcesz przypisać. Zostanie wyświetlony pulpit nawigacyjny związany z aplikacją. 
4. Wybierz pozycję **Przypisania** w sekcji **Zarządzaj**. 

    ![Przypisania aplikacji usługi Intune](./media/apps-inc-exl-01.png)
5. Wybierz pozycję **Dodaj grupę**, aby dodać grupy użytkowników, którzy są przypisani do aplikacji. 
6. Wybierz pozycję **Typ przypisania** spośród dostępnych typów przypisania w bloku **Dodaj grupę**.
7. Jako typ przypisania wybierz pozycję **Dostępne z rejestracją lub bez niej**.

    ![Przypisania aplikacji usługi Intune — Dodaj grupę](./media/apps-inc-exl-02.png)
8. Wybierz pozycję **Objęte grupy**, aby wybrać grupę użytkowników, którym chcesz udostępnić tę aplikację.

    >[!NOTE]
    >Jeśli podczas dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, zostanie ona wstępnie wybrana i nie będzie zmieniana dla innych typów dołączania przypisania. W związku z tym tej grupy, który została użyta, nie można użyć jako dołączonej grupy.

9. Wybierz pozycję **Tak**, aby udostępnić tę aplikację wszystkim użytkownikom.

    ![Przypisania aplikacji usługi Intune — Dołącz grupę](./media/apps-inc-exl-03.png)
10. Kliknij przycisk **OK**, aby ustawić grupę do dołączenia.
11. Wybierz pozycję **Wykluczone grupy**, aby wybrać grupy użytkowników, które mają nie mieć dostępu do tej aplikacji. 
12. Wybierz grupy do wykluczenia, co spowoduje niedostępność tej aplikacji.

    ![Przypisania aplikacji usługi Intune — Wykluczenie grup](./media/apps-inc-exl-04.png)
13. Kliknij pozycję **Wybierz**, aby zakończyć wybór grup.
14. Kliknij przycisk **OK** w bloku **Dodaj grupę**. Zostanie wyświetlona lista **Przypisania** aplikacji.
15. Kliknij przycisk **Zapisz**, aby uaktywnić przypisania grup dla aplikacji.

Podczas przypisywania grup te grupy, które już zostały przypisane lub wybrane, są wyłączone. Jeśli chcesz wybrać grupę, która jest obecnie wyłączona, usuń ją z listy przypisanych aplikacji. Możesz edytować przypisania na liście **Przypisania** aplikacji, zaznaczając wiersz zawierający określone przypisanie, które chcesz zmienić. Ponadto możesz usunąć przypisania, klikając wielokropek (...) na końcu wiersza i wybierając pozycję **Usuń**. Można też zmienić widok listy **Przypisania**, wybierając grupowanie według pozycji **Typ przypisania** lub **Dołączenia/wykluczenia**.

![Przypisania aplikacji usługi Intune — Kończenie](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Następne kroki

* Aby uzyskać więcej informacji o dołączaniu i wykluczaniu przypisań grup dla aplikacji, zobacz [Blog usługi Microsoft Intune](https://aka.ms/new_app_assignment_process).
