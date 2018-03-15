---
title: "Monitorowanie informacji o aplikacji i przypisań"
titlesuffix: Microsoft Intune
description: "Informacje pozwalające monitorować stan aplikacji przypisanej do użytkowników lub urządzeń."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b88530ef790dd181e81e420c158867d29d1d0d58
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune zapewnia szereg sposobów monitorowania właściwości zarządzanych aplikacji oraz stanu ich przypisania.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pozycję **Aplikacje mobilne**, a następnie **Aplikacje** w grupie **Zarządzaj**.
5. W bloku listy aplikacji wybierz aplikację. Zostanie wyświetlony blok **Stan instalacji urządzenia** dla aplikacji <*nazwa aplikacji*> .

## <a name="app-overview-blade"></a>Blok przeglądu aplikacji

Możesz użyć bloku <*nazwa aplikacji*> **Stan instalacji urządzenia**, aby zweryfikować szczegółowe informacje dotyczące stanu aplikacji w środowisku.

### <a name="essentials"></a>Podstawy

Sekcja **Podstawy** zawiera następujące informacje dotyczące aplikacji:

 - **Wydawca**  
Wydawca aplikacji.
 - **System operacyjny**  
System operacyjny aplikacji (Windows, iOS, Android itp.)
 - **Utworzenie**  
Godzina utworzenia tej poprawki.
 - **Przypisane**  
**Tak** lub **Nie** — czy aplikacja została przypisana.

### <a name="status"></a>Stan
Każdy wykres pokazuje liczby dla bieżącego stanu:

 - **Zainstalowane**  
Liczba zainstalowanych aplikacji.
 - **Niezainstalowane**  
Liczba niezainstalowanych aplikacji.
 - **Oczekująca instalacja**  
Liczba aplikacji, których instalacja trwa.
 - **Niepowodzenie**  
Liczba instalacji zakończonych niepowodzeniem.
 - **Nieznane**  
Liczba aplikacji z nieznanym stanem.

### <a name="device-status"></a>Stan urządzenia

Stan urządzenia. Wykres pierścieniowy przedstawiający stan instalacji aplikacji na urządzeniach. Kliknij wykres, aby otworzyć listę szczegółowych informacji o stanie urządzenia. Tabela szczegółów zawiera następujące kolumny:

 - **Nazwa urządzenia**  
Nazwa urządzenia na platformach, które umożliwiają nadanie nazwy urządzeniu. Na innych platformach usługa Intune utworzy nazwę na podstawie innych właściwości. Ten atrybut nie może być dostępny dla wszystkich urządzeń.
 - **Nazwa użytkownika**  
Nazwa użytkownika.
 - **Platforma**  
System operacyjny urządzenia (Windows, iOS, Android itp.)
 - **Wersja**  
Numer wersji aplikacji. W przypadku aplikacji biznesowych jest wyświetlany pełny numer wersji. Pełny numer wersji identyfikuje określone wydanie aplikacji. Numer ma postać _wersja_(_kompilacja_), na przykład 2.2(2.2.17560800).
 - **Stan**  
Stan aplikacji.
 - **Szczegóły stanu**  
Szczegółowe informacje o stanie.
 - **Ostatnie zaewidencjonowanie**  
Data ostatniej synchronizacji urządzenia z usługą Intune.


### <a name="user-status"></a>Stan użytkownika

Stan użytkownika. Wykres pierścieniowy przedstawiający stan instalacji aplikacji według użytkowników. Kliknij wykres, aby otworzyć listę szczegółowych informacji o stanie urządzenia. Tabela szczegółów zawiera następujące kolumny:
 - **Nazwa**  
Nazwa użytkownika w usłudze Azure AD.
 - **Nazwa użytkownika**  
Unikatowa nazwa użytkownika.
 - **Instalacje**  
Liczba instalacji aplikacji użytych przez użytkownika.
 - **Niepowodzenia**  
Liczba instalacji zakończonych niepowodzeniem według użytkownika.
 - **Niezainstalowane**  
Liczba aplikacji niezainstalowanych przez użytkownika.


## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się więcej na temat pracy z danymi usługi Intune, zobacz [Korzystanie z magazynu danych usługi Intune](reports-nav-create-intune-reports.md).
