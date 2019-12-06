---
title: Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak możesz użyć usługi Microsoft Intune do dołączania i wykluczania przypisań aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f073c8ad7a8e087a791ee756683011fac6947162
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547964"
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune

W usłudze Intune można określić, kto ma dostęp do aplikacji, przypisując grupy użytkowników do dołączenia i wykluczenia. Przed przypisaniem grup do aplikacji musisz ustawić typ przypisania aplikacji. Typ przypisania sprawia, że aplikacja jest dostępna lub wymagana bądź odinstalowuje aplikację. 

Aby ustawić dostępność aplikacji, przypisania aplikacji można dołączać do grupy użytkowników lub urządzeń i wykluczać je z nich za pomocą kombinacji przypisań dołączania i wykluczania grupy. Ta możliwość może być przydatna, gdy udostępniasz aplikację przez dołączenie dużej grupy, a następnie zawężasz wybranych użytkowników, wyłączając również mniejszą grupę. Mniejsza grupa może być grupą testową lub grupą wykonawczą. 

Najlepszym rozwiązaniem jest utworzenie i przypisanie aplikacji przeznaczonych dla grup użytkowników i oddzielnie dla grup urządzeń. Aby uzyskać więcej informacji na temat grup, zobacz [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md).  

Istnieją ważne scenariusze dotyczące dołączania lub wykluczania przypisań aplikacji:

- Wykluczenie ma pierwszeństwo przed dołączeniem w następujących scenariuszach tego samego typu grupy:
    - Dołączanie grup użytkowników i wykluczanie grup użytkowników podczas przypisywania aplikacji
    - Dołączanie grup urządzeń i wykluczanie grup urządzeń podczas przypisywania aplikacji

    Jeśli na przykład grupa urządzeń zostanie przypisana do grupy użytkowników **Wszyscy użytkownicy w firmie**, ale członkowie grupy użytkowników **Kadra kierownicza wyższego szczebla** zostaną wykluczeni, grupa **Wszyscy użytkownicy w firmie** z wyjątkiem grupy **Kadra kierownicza wyższego szczebla** uzyska przypisanie, ponieważ obie grupy są grupami użytkowników.
- Usługa Intune nie ocenia relacji między użytkownikami i grupami urządzeń. Jeśli przypiszesz aplikacje do grup mieszanych, wyniki mogą być niezgodne z oczekiwaniami.

    Przypiszesz na przykład grupę urządzeń do grupy użytkowników **Wszyscy użytkownicy**, ale wykluczysz grupę urządzeń **Wszystkie urządzenia osobiste**. W tym mieszanym przypisaniu aplikacji grupy aplikację otrzyma grupa **Wszyscy użytkownicy**. Wykluczenie nie ma zastosowania.

W związku z tym nie zaleca się przypisywania aplikacji do grup mieszanych.

> [!NOTE]
> Jeśli ustawiasz przypisanie grupy do aplikacji, typ **Nie dotyczy** jest przestarzały i został zastąpiony przez funkcjonalność wykluczania grupy. 
>
> Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia**. Grupy oferują wbudowane optymalizacje dla wygody użytkownika. Zdecydowanie zaleca się używanie tych grup dla wszystkich użytkowników i wszystkich urządzeń zamiast wszelkich grup „wszyscy użytkownicy” lub „wszystkie urządzenia”, które mogły zostać utworzone samodzielnie.  
>
> Rozwiązanie Android enterprise obsługuje dołączanie i wykluczanie grup. Można użyć wbudowanych grup **Wszyscy użytkownicy** i **Wszystkie urządzenia** na potrzeby przypisywania aplikacji Android enterprise. 

## <a name="include-and-exclude-groups-when-assigning-apps"></a>Dołączanie i wykluczanie grup podczas przypisywania aplikacji 
Aby przypisać aplikację do grup za pomocą dołączania i wykluczania przypisania:
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W okienku **Aplikacje klienckie** wybierz pozycję **Aplikacje**. Zostanie wyświetlona lista dodanych aplikacji.
5. Wybierz aplikację, którą chcesz przypisać. Na pulpicie nawigacyjnym zostaną wyświetlone informacje o aplikacji. 
6. W sekcji **Zarządzaj** menu wybierz pozycję **Przypisania**. 

    ![Uwzględnianie przypisań aplikacji podczas przypisywania aplikacji](./media/apps-inc-exl-assignments/apps-inc-exl-01.png)
7. Wybierz pozycję **Dodaj grupę**, aby dodać grupy użytkowników, którzy są przypisani do aplikacji. 
8. W okienku **Dodawanie grupy** wybierz **typ przypisania** spośród dostępnych typów przypisania.
9. Jako typ przypisania wybierz pozycję **Dostępne z rejestracją lub bez niej**.

    ![Przypisania aplikacji usługi Intune — Dodaj grupę](./media/apps-inc-exl-assignments/apps-inc-exl-02.png)
10. Wybierz pozycję **Uwzględnione grupy**, aby wybrać grupę użytkowników, którym chcesz udostępnić tę aplikację.

    > [!NOTE]
    > Jeśli w przypadku dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, jest ona wstępnie wybierana i nie można jej zmienić dla innych typów dołączania przypisania. Użytej grupy nie można zastosować jako grupy dołączonej.

11. Wybierz pozycję **Tak**, aby udostępnić tę aplikację wszystkim użytkownikom.

    ![Przypisania aplikacji usługi Intune — Dołącz grupę](./media/apps-inc-exl-assignments/apps-inc-exl-03.png)
12. Wybierz przycisk **OK**, aby ustawić grupę do dołączenia.
13. Wybierz pozycję **Wykluczone grupy**, aby wybrać grupy użytkowników, które mają nie mieć dostępu do tej aplikacji. 
14. Wybierz grupy do wykluczenia. Spowoduje to, że ta aplikacja będzie już niedostępna dla tych grup.

    ![Przypisania aplikacji usługi Intune — Wykluczenie grup](./media/apps-inc-exl-assignments/apps-inc-exl-04.png)
15. Wybierz pozycję **Wybierz**, aby ukończyć wybór grup.
16. W okienku **Dodawanie grupy** wybierz przycisk **OK**. Zostanie wyświetlona lista **Przypisania** aplikacji.
17. Kliknij przycisk **Zapisz**, aby uaktywnić przypisania grup dla aplikacji.

W przypadku tworzenia przypisań grup już przypisane grupy nie są dostępne do modyfikowania. Jeśli chcesz wybrać grupę, która jest obecnie niedostępna, najpierw usuń aplikację z listy przypisanych aplikacji. 

Aby edytować przypisania, na liście **Przypisania** aplikacji wybierz wiersz zawierający określone przypisanie, które chcesz zmienić. Możesz również usunąć przypisanie, wybierając wielokropek ( **…** ) na końcu wiersza i wybierz pozycję **Usuń**. Aby zmienić widok listy **Przypisania**, pogrupuj ją według pozycji **Typ przypisania** lub **Dołączenia/wykluczenia**.

![Przypisania aplikacji usługi Intune — Kończenie](./media/apps-inc-exl-assignments/apps-inc-exl-05.png)

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o dołączaniu i wykluczaniu przypisań grup dla aplikacji, zobacz [Blog usługi Microsoft Intune](https://aka.ms/new_app_assignment_process).
- Dowiedz się, jak [monitorować informacje o aplikacji i przypisania](apps-monitor.md).
