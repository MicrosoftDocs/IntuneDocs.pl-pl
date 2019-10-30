---
title: Monitorowanie informacji o aplikacji i przypisań
titleSuffix: Microsoft Intune
description: Informacje pozwalające monitorować stan aplikacji przypisanej do użytkowników lub urządzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ee22ee435830137a423423aa692376aabbb6cecb
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585414"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune oferuje kilka sposobów monitorowania właściwości zarządzanych aplikacji oraz stanu przypisania aplikacji.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W sekcji **Zarządzaj** menu wybierz pozycję **Aplikacje**.
5. Na liście aplikacji wybierz aplikację do monitorowania. Zostanie wyświetlone okienko aplikacji, które zawiera przegląd stanu urządzenia i stanu użytkownika.

> [!NOTE]
> Aplikacje w sklepie dla systemu Android, które są wdrażane jako **dostępne**, nie zgłaszają swojego stanu instalacji.
>
> W przypadku aplikacji zarządzanych ze sklepu Google Play wdrożonych na urządzeniach z profilem służbowym systemu Android Enterprise można wyświetlić stan i numer wersji aplikacji zainstalowanej na urządzeniu za pomocą usługi Intune. 

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
> Należy pamiętać, że aplikacje biznesowe systemu Android (.APK) wdrożone przy użyciu opcji **Dostępne z rejestracją lub bez niej** zgłaszają stan instalacji aplikacji tylko w przypadku zarejestrowanych urządzeń. Stan instalacji aplikacji jest niedostępny dla urządzeń, których nie zarejestrowano w usłudze Intune.

### <a name="device-install-status"></a>Stan instalacji urządzenia

Lista stanu urządzenia zostanie pokazana po wybraniu pozycji **Stan instalacji urządzenia** w sekcji **Monitorowanie** menu. Tabela szczegółów zawiera następujące kolumny:

| **Kolumna urządzenia**      | **Opis**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nazwa urządzenia**      | Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut jest niedostępny w przypadku innych urządzeń.                                                                       |
| **Nazwa użytkownika**        | Nazwa użytkownika.                                                                                                                                                                                                                                      |
| **Platforma**         | System operacyjny urządzenia (Windows, iOS, Android itp.).                                                                                                                                                                                           |
| **Wersja**          | Numer wersji aplikacji. W przypadku aplikacji biznesowych (LOB) i aplikacji ze sklepu Microsoft Store dla Firm jest pokazywany pełny numer wersji. Pełny numer wersji identyfikuje określone wydanie aplikacji. Numer ma postać _wersja_(_kompilacja_), Na przykład 2.2(2.2.17560800). W przypadku standardowych aplikacji z witryny Store wersje nie są wyświetlane. |
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

- Aby dowiedzieć się więcej na temat pracy z danymi usługi Intune, zobacz [Korzystanie z magazynu danych usługi Intune](../reports-nav-create-intune-reports.md).
- Aby dowiedzieć się więcej na temat zasad konfiguracji aplikacji, zobacz [Zasady konfiguracji aplikacji usługi Intune](app-configuration-policies-overview.md).
