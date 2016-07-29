---
title: "Zarządzanie aplikacjami ze Sklepu Windows dla firm | Microsoft Intune"
description: "Połącz usługę Intune ze Sklepem Windows dla firm, aby wdrażać aplikacje zakupione zbiorczo z poziomu konsoli usługi Intune i zarządzać nimi"
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 07079b6566bec45593bb9ae49272aa7154a7174d


---

# Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm za pomocą usługi Microsoft Intune
[Sklep Windows dla firm](https://www.microsoft.com/business-store) to miejsce, w którym można znaleźć i zakupić aplikacje dla całej organizacji, pojedynczo lub zbiorczo. Łącząc Sklep Windows z usługą Microsoft Intune, można zarządzać aplikacjami zakupionymi zbiorczo z poziomu konsoli usługi Intune, np.:
* Można zsynchronizować listę aplikacji zakupionych w sklepie za pośrednictwem usługi Intune.
* Aplikacje, które są synchronizowane, zostają wyświetlone w konsoli administracyjnej usługi Intune. Można je wdrażać w taki sam sposób, jak wszystkie inne aplikacje.
* Można śledzić liczbę dostępnych i używanych licencji w konsoli administracyjnej usługi Intune.
* Usługa Intune blokuje wdrażanie i instalację aplikacji, jeśli nie ma wystarczającej liczby dostępnych licencji.

## Przed rozpoczęciem
Przed rozpoczęciem synchronizowania i wdrażania aplikacji ze Sklepu Windows dla firm przejrzyj następujące informacje:
* Musisz skonfigurować usługę Intune jako urząd zarządzania urządzeniami przenośnymi w Twojej organizacji. Aby uzyskać więcej informacji, zobacz [Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)
* Musisz mieć zarejestrowane konto w Sklepie Windows dla firm
* Po powiązaniu konta w Sklepie Windows dla firm z usługą Intune nie będzie można zmienić konta na inne.
* Aplikacje zakupione w sklepie nie mogą być ręcznie dodawane do usługi Intune ani z niej usuwane. Aplikacje mogą być jedynie synchronizowane ze Sklepem Windows dla firm.
* Usługa Intune synchronizuje tylko licencjonowane aplikacje nabyte w Sklepie Windows dla firm.
* Urządzenia muszą być przyłączone do domeny usługi Active Directory lub dołączone do miejsca pracy, aby móc używać tej funkcji.
* Zarejestrowane urządzenia muszą używać wersji 1511 systemu Windows 10.

## Skojarz konto w Sklepie Windows dla firm z usługą Intune
Przed włączeniem synchronizacji w konsoli usługi Intune należy skonfigurować konto w sklepie, aby używało usługi Intune jako narzędzia do zarządzania:
1. Upewnij się, że logujesz się do Sklepu Windows dla firm za pomocą tego samego konta dzierżawy, z którego korzystasz do logowania się do usługi Intune.
2. W Sklepie dla firm wybierz opcję **Ustawienia** > **Narzędzia do zarządzania**.
3. Na stronie Narzędzia do zarządzania wybierz opcję **Dodaj narzędzie do zarządzania**, a następnie wybierz pozycję Microsoft Intune.

Teraz możesz przejść do konfigurowania synchronizacji w konsoli Intune.

## Konfigurowanie synchronizacji

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Administracja**.
2. W obszarze roboczym **Administracja** rozwiń węzeł **Zarządzanie urządzeniami przenośnymi**, a następnie kliknij pozycję **Sklep dla firm**.
3. Na stronie **Sklepu Windows dla firm** wykonaj następujące czynności:
* Jeśli jeszcze tego nie zrobiono, kliknij link do rejestracji w Sklepie Windows dla firm
* Po zarejestrowaniu się kliknij opcję **Konfiguracja synchronizacji**
4. W oknie dialogowym **Konfiguracja synchronizacji aplikacji Sklepu Windows dla firm** wybierz pozycję **Włącz synchronizację Sklepu Windows dla firm**.
5. Z listy rozwijanej **Język** wybierz język, w którym aplikacje ze Sklepu Windows dla firm będą wyświetlane w konsoli usługi Intune. Niezależnie od języka, w którym są wyświetlane, aplikacje zostaną zainstalowane w języku użytkownika końcowego, o ile będzie dostępny.
6. Kliknij przycisk **OK**.

## Synchronizacja aplikacji

1. Na stronie **Sklepu Windows dla firm** kliknij opcję **Synchronizuj teraz**, aby zsynchronizować aplikacje zakupione w sklepie za pomocą usługi Intune.
2. W obszarze roboczym **Aplikacje** kliknij opcję **Zarządzane oprogramowanie** > **Licencjonowane oprogramowanie**, aby wyświetlić dostępne aplikacje i upewnić się, że zakupione aplikacje zostały zaimportowane prawidłowo.
Aplikacje w tym węźle są wyświetlane z całkowitą liczbą posiadanych licencji oraz liczbą dostępnych licencji.

## Wdrażanie aplikacji

Aplikacje ze sklepu wdraża się w taki sam sposób, jak każdą inną aplikację usługi Intune. Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Gdy wdrażasz aplikację ze Sklepu Windows dla firm, licencja jest zużywana przez każdego użytkownika, który zainstaluje aplikację. Jeśli zużyjesz wszystkie dostępne licencje dla wdrażanej aplikacji, nie będziesz w stanie wdrożyć większej liczby kopii aplikacji. W takim przypadku należy wykonać jedną z następujących czynności:
* Odinstaluj aplikację z niektórych urządzeń
* Zmniejsz zakres bieżącego wdrożenia i nakieruj je tylko na użytkowników, dla których masz wystarczającą liczbę licencji
* Kup więcej kopii aplikacji w Sklepie Windows dla firm


### Zobacz także
[Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)





<!--HONumber=Jul16_HO4-->


