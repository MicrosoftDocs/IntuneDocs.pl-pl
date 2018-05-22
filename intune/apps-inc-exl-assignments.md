---
title: Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak możesz użyć usługi Microsoft Intune do dołączania i wykluczania przypisań aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4a2afba3eafb32a06ff19e2cbbf3b87d27edccf0
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune

W usłudze Intune można określić, kto ma dostęp do aplikacji, przypisując grupy użytkowników do dołączenia i wykluczenia. Przed przypisaniem grup do aplikacji musisz ustawić typ przypisania aplikacji. Typ przypisania sprawia, że aplikacja jest dostępna lub wymagana bądź odinstalowuje aplikację. 

Aby ustawić dostępność aplikacji, przypisania aplikacji można dołączać do grupy użytkowników lub urządzeń i wykluczać je z nich za pomocą kombinacji przypisań dołączania i wykluczania grupy. Ta możliwość może być przydatna, gdy udostępniasz aplikację przez dołączenie dużej grupy, a następnie zawężasz wybranych użytkowników, wyłączając również mniejszą grupę. Mniejsza grupa może być grupą testową lub grupą wykonawczą. 

Gdy wykluczasz grupy z przypisania aplikacji, musisz wykluczyć tylko grupy użytkowników lub tylko grupy urządzeń. Nie można wykluczyć kombinacji grup użytkowników i grup urządzeń. 

Podczas wykluczania grup usługa Intune nie uwzględnia żadnych skojarzeń użytkowników z urządzeniami. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń raczej nie przyniesie oczekiwanych rezultatów. Dołączanie ma pierwszeństwo przed wykluczeniem. Jeśli na przykład aplikacja systemu iOS jest przeznaczona dla **Wszystkich użytkowników** i wyklucza **Wszystkie urządzenia iPad**, wynik netto jest taki, że dowolny użytkownik korzystający z urządzenia iPad nadal uzyskuje aplikację. Jeśli jednak aplikacja systemu iOS jest przeznaczona dla **Wszystkich urządzeń** i wyklucza **Wszystkie urządzenia iPad**, wdrożenie będzie udane.  

> [!NOTE]
> Jeśli ustawiasz przypisanie grupy do aplikacji, typ **Nie dotyczy** jest przestarzały i został zastąpiony przez funkcjonalność wykluczania grupy. 
>
> Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia**. Grupy oferują wbudowane optymalizacje dla wygody użytkownika. Zdecydowanie zaleca się używanie tych grup dla wszystkich użytkowników i wszystkich urządzeń zamiast wszelkich grup „wszyscy użytkownicy” lub „wszystkie urządzenia”, które mogły zostać utworzone samodzielnie.  
>
> System Android Enterprise (wcześniej znany jako Android for Work) obsługuje dołączanie i wykluczanie grup. Można użyć wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji Android Enterprise. 


## <a name="include-and-exclude-groups-when-assigning-apps"></a>Dołączanie i wykluczanie grup podczas przypisywania aplikacji 
Aby przypisać aplikację do grup za pomocą dołączania i wykluczania przypisania:
1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W menu usługi **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku **Aplikacje mobilne** wybierz pozycję **Aplikacje**. Zostanie wyświetlona lista dodanych aplikacji.
5. Wybierz aplikację, którą chcesz przypisać. Na pulpicie nawigacyjnym zostaną wyświetlone informacje o aplikacji. 
6. W sekcji **Zarządzaj** menu wybierz pozycję **Przypisania**. 

    ![Przypisania aplikacji usługi Intune](./media/apps-inc-exl-01.png)
7. Wybierz pozycję **Dodaj grupę**, aby dodać grupy użytkowników, którzy są przypisani do aplikacji. 
8. W okienku **Dodawanie grupy** wybierz **typ przypisania** spośród dostępnych typów przypisania.
9. Jako typ przypisania wybierz pozycję **Dostępne z rejestracją lub bez niej**.

    ![Przypisania aplikacji usługi Intune — Dodaj grupę](./media/apps-inc-exl-02.png)
10. Wybierz pozycję **Uwzględnione grupy**, aby wybrać grupę użytkowników, którym chcesz udostępnić tę aplikację.

    > [!NOTE]
    > Jeśli w przypadku dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, jest ona wstępnie wybierana i nie można jej zmienić dla innych typów dołączania przypisania. Użytej grupy nie można zastosować jako grupy dołączonej.

11. Wybierz pozycję **Tak**, aby udostępnić tę aplikację wszystkim użytkownikom.

    ![Przypisania aplikacji usługi Intune — Dołącz grupę](./media/apps-inc-exl-03.png)
12. Wybierz przycisk **OK**, aby ustawić grupę do dołączenia.
13. Wybierz pozycję **Wykluczone grupy**, aby wybrać grupy użytkowników, które mają nie mieć dostępu do tej aplikacji. 
14. Wybierz grupy do wykluczenia. Spowoduje to, że ta aplikacja będzie już niedostępna dla tych grup.

    ![Przypisania aplikacji usługi Intune — Wykluczenie grup](./media/apps-inc-exl-04.png)
15. Wybierz pozycję **Wybierz**, aby ukończyć wybór grup.
16. W okienku **Dodawanie grupy** wybierz przycisk **OK**. Zostanie wyświetlona lista **Przypisania** aplikacji.
17. Kliknij przycisk **Zapisz**, aby uaktywnić przypisania grup dla aplikacji.

W przypadku tworzenia przypisań grup już przypisane grupy nie są dostępne do modyfikowania. Jeśli chcesz wybrać grupę, która jest obecnie niedostępna, najpierw usuń aplikację z listy przypisanych aplikacji. 

Aby edytować przypisania, na liście **Przypisania** aplikacji wybierz wiersz zawierający określone przypisanie, które chcesz zmienić. Możesz również usunąć przypisanie, wybierając wielokropek (**…**) na końcu wiersza i wybierz pozycję **Usuń**. Aby zmienić widok listy **Przypisania**, pogrupuj ją według pozycji **Typ przypisania** lub **Dołączenia/wykluczenia**.

![Przypisania aplikacji usługi Intune — Kończenie](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o dołączaniu i wykluczaniu przypisań grup dla aplikacji, zobacz [Blog usługi Microsoft Intune](https://aka.ms/new_app_assignment_process).
- Dowiedz się, jak [monitorować informacje o aplikacji i przypisania](apps-monitor.md).
