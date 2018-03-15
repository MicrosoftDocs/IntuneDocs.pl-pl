---
title: "Wprowadzenie do aplikacji w usłudze Microsoft Intune"
titlesuffix: 
description: "Znajduj i dodawaj aplikacje do urządzeń, aby umożliwić pracownikom wykonywanie zadań."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Wprowadzenie do dodawania aplikacji w usłudze Microsoft Intune

Aby móc przypisywać, monitorować, konfigurować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. Usługa Intune obsługuje różne typy aplikacji. Ponadto dostępne opcje różnią się dla poszczególnych typów aplikacji.

Usługa Intune pozwala dodawać i przypisywać następujące typy aplikacji do urządzeń firmowych:
- **Aplikacje ze sklepu** — dla urządzeń z systemem iOS, w przypadku których konieczne jest zastosowanie dodatkowych czynności związanych z zarządzaniem aplikacjami mobilnymi dostępnymi w sklepie App Store.
- **Aplikacje pisane wewnętrznie (biznesowe)** — używane w przypadku przekazywania pliku, który jest pobierany na urządzenia użytkowników.
- **Aplikacje wbudowane** — w przypadku przypisywania nadzorowanych zarządzanych aplikacji, takich jak aplikacje usługi Office 365, do urządzeń z systemem iOS i Android. 
- **Aplikacje w Internecie** — usługa Intune tworzy skrót do aplikacji internetowej na ekranie głównym urządzenia.

## <a name="how-do-i-assign-a-public-store-app"></a>Jak mogę przypisać aplikację ze sklepu publicznego?

Poniższy przykład zawiera kroki związane z dodawaniem aplikacji systemu iOS w usłudze Microsoft Intune.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w sekcji **Zarządzaj**.
5. Wybierz opcję **Dodaj** po prawej stronie okienka **Aplikacje**.
6. Na liście **Typ aplikacji** wybierz opcję **iOS** w obszarze dostępnych typów **aplikacji ze sklepu**.
6. Wybierz opcję **Wyszukaj w sklepie App Store**.
7. W bloku **Wyszukaj w sklepie App Store** najpierw wybierz ustawienia regionalne kraju na potrzeby sklepu App Store.
8. Wpisz nazwę (lub jej część) w polu wyszukiwania. Usługa Intune wyszuka nazwę w sklepie i powróci do listy wyników spełniających kryterium.
9. Wybierz aplikację z listy, a następnie kliknij przycisk **Wybierz**.
10. Wybierz opcję **Informacje o aplikacji**, aby skonfigurować informacje dotyczące aplikacji.
11. (Opcjonalnie) Dodaj szczegóły, aby ułatwić organizowanie tej aplikacji, takie jak **Właściciel**, **Uwagi**, **Deweloper** oraz **Adres URL zasad ochrony prywatności** (kierujący do firmowych zasad ochrony prywatności).
12. Wybierz pozycję **Tak** dla opcji **Wyświetlaj jako polecaną aplikację w Portalu firmy**. 
13. Kliknij przycisk **OK** po dodaniu wszystkich niezbędnych informacji dotyczących aplikacji.
14. Kliknij opcję **Dodaj** w bloku **Dodawanie aplikacji**. Spowoduje to przejście do obszaru **Omówienie** aplikacji. 

## <a name="next-steps"></a>Następne kroki

Teraz, po dodaniu aplikacji do usługi Intune, możesz przypisać grupy pracowników, którzy będą mogli używać aplikacji na swoich urządzeniach.

- [Jak przypisać aplikacje do grup](apps-deploy.md)
- 
## <a name="learn-more"></a>Dowiedz się więcej

* [What is app management with Intune? (Co to jest zarządzanie aplikacjami przy użyciu usługi Intune?)](app-management.md)
* [Przegląd cyklu życia aplikacji](app-lifecycle.md)
* [Co to są zasady ochrony aplikacji?](app-protection-policy.md)
