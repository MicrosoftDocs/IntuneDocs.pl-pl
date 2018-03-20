---
title: "Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune"
titlesuffix: 
description: "Dowiedz się, jak możesz użyć usługi Microsoft Intune do dołączania i wykluczania przypisań aplikacji."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dbe8669dc2bf448e0738147758d90ba6d2d69b06
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune

Przy użyciu usługi Intune możesz określić, kto ma dostęp do aplikacji, przypisując grupy zarówno do dołączania, jak i wykluczania. Jednak przed przypisaniem grup do aplikacji musisz ustawić typ przypisania aplikacji. Typ przypisania sprawia, że aplikacja jest dostępna lub wymagana bądź odinstalowuje aplikację. 

W przypadku skupienia się na dostępności aplikacji przypisania aplikacji można dołączać do grupy użytkowników lub urządzeń i wykluczać je z nich za pomocą kombinacji przypisań dołączania i wykluczania grupy. Ta możliwość może być przydatna, gdy udostępniasz aplikację przez dołączenie dużej grupy, a następnie zawężasz wybranych użytkowników, wyłączając również mniejszą grupę. Mniejsza grupa może być grupą testową lub grupą wykonawczą. 

Gdy wykluczasz grupy z przypisania aplikacji, musisz wykluczyć tylko grupy użytkowników lub urządzeń, ale nie kombinację tych grup. Podczas wykluczania grup usługa Intune nie uwzględnia żadnych skojarzeń użytkowników z urządzeniami. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń raczej nie przyniesie oczekiwanych rezultatów, ponieważ dołączenie będzie miało pierwszeństwo przed wykluczeniem. Jeśli na przykład aplikacja systemu iOS jest przeznaczona dla **Wszystkich użytkowników** i wyklucza **Wszystkie urządzenia iPad**, wynikiem netto będzie to, że dowolny użytkownik korzystający z urządzenia iPad nadal uzyska aplikację. Jeśli jednak aplikacja systemu iOS jest przeznaczona do **Wszystkich urządzeń** i wyklucza **Wszystkie urządzenia iPad**, wdrożenie będzie udane.  

>[!NOTE]
>Podczas ustawiania przypisania grupy do aplikacji typ **Nie dotyczy** jest przestarzały i został zastąpiony przez funkcjonalność wykluczania grupy. 
>
>Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika. Zdecydowanie zaleca się używanie tych grup dla wszystkich użytkowników i wszystkich urządzeń zamiast wszelkich grup „Wszyscy użytkownicy” lub „Wszystkie urządzenia”, które mogły zostać utworzone samodzielnie.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Dołączanie i wykluczanie grup podczas przypisywania aplikacji 
Aby przypisać aplikację do grup za pomocą dołączania i wykluczania przypisania:
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W bloku usługi Microsoft Intune wybierz pozycję **Aplikacje mobilne**.
4. Wybierz pozycję **Aplikacje** z bloku **Aplikacje mobilne**. Zostanie wyświetlona lista dodanych aplikacji.
5. Wybierz aplikację, którą chcesz przypisać. Zostanie wyświetlony pulpit nawigacyjny związany z aplikacją. 
6. Wybierz pozycję **Przypisania** w sekcji **Zarządzaj**. 

    ![Przypisania aplikacji usługi Intune](./media/apps-inc-exl-01.png)
7. Wybierz pozycję **Dodaj grupę**, aby dodać grupy użytkowników, którzy są przypisani do aplikacji. 
8. Wybierz pozycję **Typ przypisania** spośród dostępnych typów przypisania w okienku **Dodaj grupę**.
9. Jako typ przypisania wybierz pozycję **Dostępne z rejestracją lub bez niej**.

    ![Przypisania aplikacji usługi Intune — Dodaj grupę](./media/apps-inc-exl-02.png)
10. Wybierz pozycję **Objęte grupy**, aby wybrać grupę użytkowników, którym chcesz udostępnić tę aplikację.

    >[!NOTE]
    >Jeśli podczas dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, zostanie ona wstępnie wybrana i nie będzie zmieniana dla innych typów dołączania przypisania. W związku z tym tej grupy, który została użyta, nie można użyć jako dołączonej grupy.

11. Wybierz pozycję **Tak**, aby udostępnić tę aplikację wszystkim użytkownikom.

    ![Przypisania aplikacji usługi Intune — Dołącz grupę](./media/apps-inc-exl-03.png)
12. Kliknij przycisk **OK**, aby ustawić grupę do dołączenia.
13. Wybierz pozycję **Wykluczone grupy**, aby wybrać grupy użytkowników, które mają nie mieć dostępu do tej aplikacji. 
14. Wybierz grupy do wykluczenia, co spowoduje niedostępność tej aplikacji.

    ![Przypisania aplikacji usługi Intune — Wykluczenie grup](./media/apps-inc-exl-04.png)
15. Kliknij pozycję **Wybierz**, aby zakończyć wybór grup.
16. Kliknij przycisk **OK** w bloku **Dodaj grupę**. Zostanie wyświetlona lista **Przypisania** aplikacji.
17. Kliknij przycisk **Zapisz**, aby uaktywnić przypisania grup dla aplikacji.

Podczas przypisywania grup te grupy, które już zostały przypisane lub wybrane, są wyłączone. Jeśli chcesz wybrać grupę, która jest obecnie wyłączona, usuń ją z listy przypisanych aplikacji. Możesz edytować przypisania na liście **Przypisania** aplikacji, zaznaczając wiersz zawierający określone przypisanie, które chcesz zmienić. Ponadto możesz usunąć przypisania, klikając wielokropek (...) na końcu wiersza i wybierając pozycję **Usuń**. Można też zmienić widok listy **Przypisania**, wybierając grupowanie według pozycji **Typ przypisania** lub **Dołączenia/wykluczenia**.

![Przypisania aplikacji usługi Intune — Kończenie](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o dołączaniu i wykluczaniu przypisań grup dla aplikacji, zobacz [Blog usługi Microsoft Intune](https://aka.ms/new_app_assignment_process).
- [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md)