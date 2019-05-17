---
title: Monitorowanie informacji o aplikacji i przypisań
titleSuffix: Microsoft Intune
description: Informacje pozwalające monitorować stan aplikacji przypisanej do użytkowników lub urządzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b3cba546be350f47c1a57f47b8eddf85323dc74
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567234"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune oferuje kilka sposobów monitorowania właściwości zarządzanych aplikacji oraz stanu przypisania aplikacji.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W menu **Intune** wybierz opcję **Aplikacje klienckie**.
4. W sekcji **Zarządzaj** menu wybierz pozycję **Aplikacje**.
5. Na liście aplikacji wybierz aplikację do monitorowania. Zostanie wyświetlone okienko aplikacji, które zawiera przegląd stanu urządzenia i stanu użytkownika.

> [!NOTE]
> Aplikacje systemu Android ze Sklepu wdrażane jako **Dostępne** oraz aplikacje LOB systemu Android wdrażane jako **Dostępne z rejestracją lub bez niej** nie zgłaszają stanu instalacji.

## <a name="app-overview-pane"></a>Okienko przeglądu aplikacji

W okienku aplikacji możesz przejrzeć szczegółowe informacje dotyczące stanu aplikacji w środowisku.

### <a name="essentials"></a>Essentials
Sekcja **Podstawy** zawiera następujące informacje dotyczące aplikacji:

 | **Szczegóły aplikacji**            | **Opis**                                                      |
|------------------------|------------------------------------------------------------------|
| **Wydawca**          | Wydawca aplikacji.                                            |
| **System operacyjny**   | System operacyjny aplikacji (Windows, iOS, Android itp.). |
| **Utworzono**             | Data i godzina utworzenia tej poprawki. <b>**Uwaga**: ta wartość daty jest aktualizowana, gdy administrator IT zmienia metadane aplikacji, takie jak kategoria aplikacji lub opis aplikacji.                        |
| **Przypisane**           | Czy aplikacja została przypisana (**Tak** lub **Nie**).                  |

### <a name="device-and-user-status-graphs"></a>Wykresy stanu urządzenia i użytkowników
Wykresy pokazują liczbę aplikacji dla następujących stanów:

| **Stan urządzenia**       | **Opis**                                       |
|-----------------------|-------------------------------------------------------|
| **Zainstalowane**         | Liczba zainstalowanych aplikacji.                         |
| **Niezainstalowane**     | Liczba niezainstalowanych aplikacji.                     |
| **Niepowodzenie**            | Liczba instalacji zakończonych niepowodzeniem.                   |
| **Oczekująca instalacja**   | Liczba aplikacji, których instalacja trwa. |
| **Nie dotyczy**           | Liczba aplikacji, w przypadku których stan nie ma zastosowania.            |

> [!NOTE]
> Liczba wykrytych aplikacji może być niezgodna z liczbą stanu instalacji aplikacji. Możliwe przyczyny niespójności to:
>    - Ukierunkowana zmiana zainstalowanej aplikacji zarządzanej może spowodować spadek liczby instalacji w bloku stanu, ale będzie nadal zgłaszana w wykrytych aplikacjach.
>    - Przeznaczenie tej samej aplikacji dla wielu wystąpień w dzierżawie spowoduje wygenerowanie różnych liczników z powodu potencjalnego nakładania się użytkowników lub urządzeń. W każdym wystąpieniu aplikacji będą liczeni nakładający się użytkownicy, ale odnalezione aplikacje będą mieć powielone liczby.
>    - Odnalezione aplikacje i stan aplikacji są zbierane w różnych przedziałach czasowych, które mogą spowodować rozbieżności liczby aplikacji.
> 
> Ponadto, aplikacje systemu Android wdrożone przy użyciu opcji **Dostępne z rejestracją lub bez niej** zgłaszają stan instalacji aplikacji tylko w przypadku zarejestrowanych urządzeń. Stan instalacji aplikacji jest niedostępny dla urządzeń, których nie zarejestrowano w usłudze Intune.

### <a name="device-install-status"></a>Stan instalacji urządzenia

Lista stanu urządzenia zostanie pokazana po wybraniu pozycji **Stan instalacji urządzenia** w sekcji **Monitorowanie** menu. Tabela szczegółów zawiera następujące kolumny:

| **Kolumna urządzenia**      | **Opis**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nazwa urządzenia**      | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut jest niedostępny w przypadku innych urządzeń.                                                                       |
| **Nazwa użytkownika**        | Nazwa użytkownika.                                                                                                                                                                                                                                      |
| **Platforma**         | System operacyjny urządzenia (Windows, iOS, Android itp.).                                                                                                                                                                                           |
| **Wersja**          | Numer wersji aplikacji. W przypadku aplikacji biznesowych (LOB) jest pokazywany pełny numer wersji. Pełny numer wersji identyfikuje określone wydanie aplikacji. Numer ma postać _wersja_(_kompilacja_), Na przykład 2.2(2.2.17560800). W przypadku aplikacji ze sklepu wersje nie są wyświetlane. |
| **Stan**           | Stan aplikacji.                                                                                                                                                                                                                                     |
| **Szczegóły stanu**   | Szczegółowe informacje o stanie.                                                                                                                                                                                                                                     |
| **Ostatnie zaewidencjonowanie**    | Data ostatniej synchronizacji urządzenia z usługą Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Stan instalacji użytkownika

Lista stanów użytkownika zostanie pokazana po wybraniu pozycji **Stan instalacji użytkownika** w sekcji **Monitorowanie** menu. Tabela szczegółów zawiera następujące kolumny:

| **Kolumna użytkownika**     | **Opis**                           |
|---------------------|-------------------------------------------|
| **Nazwa**            | Nazwa użytkownika w usłudze Azure Active Directory.         |
| **Nazwa użytkownika**       | Unikatowa nazwa użytkownika.              |
| **Instalacje**   | Liczba aplikacji zainstalowanych przez użytkownika. |
| **Niepowodzenia**        | Liczba nieudanych instalacji aplikacji dla użytkownika.     |
| **Niezainstalowane**   | Liczba aplikacji niezainstalowanych przez użytkownika. |


## <a name="next-steps"></a>Następne kroki

- Aby dowiedzieć się więcej na temat pracy z danymi usługi Intune, zobacz [Korzystanie z magazynu danych usługi Intune](reports-nav-create-intune-reports.md).
- Aby dowiedzieć się więcej na temat zasad konfiguracji aplikacji, zobacz [Zasady konfiguracji aplikacji usługi Intune](app-configuration-policies-overview.md).
