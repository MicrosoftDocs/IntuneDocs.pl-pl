---
title: Monitorowanie informacji o aplikacji i przypisań
titlesuffix: Microsoft Intune
description: Informacje pozwalające monitorować stan aplikacji przypisanej do użytkowników lub urządzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d1ca013b7000282316a17e02dcb38b3d4f27958
ms.sourcegitcommit: 820f950d1fc80b1eb5db1b0cf77f44d92a969951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune zapewnia szereg sposobów monitorowania właściwości zarządzanych aplikacji oraz stanu ich przypisania.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w grupie **Monitorowanie + zarządzanie**.
3. Wybierz pozycję **Aplikacje mobilne**, a następnie **Aplikacje** w grupie **Zarządzaj**.
5. Na liście aplikacji wybierz aplikację, którą chcesz monitorować. Zostanie wyświetlony blok aplikacji z przeglądem stanu urządzenia i stanu użytkownika.

## <a name="app-overview-blade"></a>Blok przeglądu aplikacji

Możesz użyć bloku konkretnej aplikacji, aby zweryfikować szczegółowe informacje dotyczące stanu aplikacji w środowisku.

### <a name="essentials"></a>Podstawy
Sekcja **Podstawy** zawiera następujące informacje dotyczące aplikacji:

 | **Szczegóły aplikacji**            | **Opis**                                                      |
|------------------------|------------------------------------------------------------------|
| **Wydawca**          | Wydawca aplikacji.                                            |
| **System operacyjny**   | System operacyjny aplikacji (Windows, iOS, Android itp.) |
| **Utworzono**             | Data i godzina utworzenia tej poprawki.                         |
| **Przypisane**           | **Tak** lub **Nie** — czy aplikacja została przypisana.                  |

### <a name="device-and-user-status-graphs"></a>Wykresy stanu urządzenia i użytkowników
Wykresy pokazują liczbę dla następujących stanów:

| **Stan urządzenia**       | **Opis**                                       |
|-----------------------|-------------------------------------------------------|
| **Zainstalowane**         | Liczba zainstalowanych aplikacji.                         |
| **Niezainstalowane**     | Liczba niezainstalowanych aplikacji.                     |
| **Niepowodzenie**            | Liczba instalacji zakończonych niepowodzeniem.                   |
| **Oczekująca instalacja**   | Liczba aplikacji, których instalacja trwa. |
| **Nie dotyczy**           | Liczba aplikacji, w przypadku których stan nie ma zastosowania.            |

### <a name="device-install-status"></a>Stan instalacji urządzenia

Lista stanu urządzenia zostanie wyświetlona po wybraniu pozycji **Stan instalacji urządzenia** w sekcji **Monitorowanie**. Tabela szczegółów zawiera następujące kolumny:

| **Kolumna urządzenia**      | **Opis**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nazwa urządzenia**      | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune tworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń.                                                                       |
| **Nazwa użytkownika**        | Nazwa użytkownika.                                                                                                                                                                                                                                      |
| **Platforma**         | System operacyjny urządzenia (Windows, iOS, Android itp.)                                                                                                                                                                                           |
| **Wersja**          | Numer wersji aplikacji. W przypadku aplikacji biznesowych jest wyświetlany pełny numer wersji. Pełny numer wersji identyfikuje określone wydanie aplikacji. Numer ma postać _wersja_(_kompilacja_), Na przykład 2.2(2.2.17560800) |
| **Stan**           | Stan aplikacji.                                                                                                                                                                                                                                     |
| **Szczegóły stanu**   | Szczegółowe informacje o stanie.                                                                                                                                                                                                                                     |
| **Ostatnie zaewidencjonowanie**    | Data ostatniej synchronizacji urządzenia z usługą Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Stan instalacji użytkownika

Lista stanu użytkownika zostanie wyświetlona po wybraniu sekcji **Stan instalacji użytkownika** w sekcji **Monitorowanie**. Tabela szczegółów zawiera następujące kolumny:

| **Kolumna użytkownika**     | **Opis**                           |
|---------------------|-------------------------------------------|
| **Nazwa**            | Nazwa użytkownika w usłudze Azure AD.         |
| **Nazwa użytkownika**       | Unikatowa nazwa użytkownika.              |
| **Instalacje**   | Liczba instalacji aplikacji użytych przez użytkownika. |
| **Niepowodzenia**        | Liczba instalacji zakończonych niepowodzeniem według użytkownika.     |
| **Niezainstalowane**   | Liczba aplikacji niezainstalowanych przez użytkownika. |


## <a name="next-steps"></a>Następne kroki

- Aby dowiedzieć się więcej na temat pracy z danymi usługi Intune, zobacz [Korzystanie z magazynu danych usługi Intune](reports-nav-create-intune-reports.md).
- Aby dowiedzieć się więcej na temat zasad konfiguracji aplikacji, zobacz [Zasady konfiguracji aplikacji usługi Intune](app-configuration-policies-overview.md).