---
title: Wprowadzenie do aplikacji w usłudze Microsoft Intune
titlesuffix: ''
description: Znajduj i dodawaj aplikacje do urządzeń, aby umożliwić pracownikom wykonywanie zadań.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d99812c57596e10d0cdfa2c0f4504f8a6ac583c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Wprowadzenie do dodawania aplikacji w usłudze Microsoft Intune

Aby móc przypisywać, monitorować, konfigurować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. Usługa Intune obsługuje różne typy aplikacji. Ponadto dostępne opcje różnią się dla poszczególnych typów aplikacji.

Usługa Intune pozwala dodawać i przypisywać następujące typy aplikacji do urządzeń firmowych:
- **Aplikacje ze sklepu** — dla urządzeń z systemem iOS, w przypadku których konieczne jest zastosowanie dodatkowych czynności związanych z zarządzaniem aplikacjami mobilnymi dostępnymi w sklepie App Store.
- **Aplikacje pisane wewnętrznie (biznesowe)** — używane w przypadku przekazywania pliku, który jest pobierany na urządzenia użytkowników.
- **Aplikacje wbudowane** — w przypadku przypisywania nadzorowanych zarządzanych aplikacji, takich jak aplikacje usługi Office 365, do urządzeń z systemem iOS i Android.
- **Aplikacje w Internecie** — usługa Intune tworzy skrót do aplikacji internetowej na ekranie głównym urządzenia.

## <a name="how-do-i-assign-a-public-store-app"></a>Jak mogę przypisać aplikację ze sklepu publicznego?

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pozycję **Aplikacje mobilne**, a następnie wybierz pozycję **Aplikacje**.
4. Wybierz pozycję **Dodaj**, a następnie wybierz pozycję **iOS** jako **typ aplikacji**.
5. Wybierz pozycję **Wybierz aplikację**, aby wyświetlić okienko **Wyszukaj w sklepie App Store**.
6. W polu tekstowym wyszukaj aplikację, która zostanie przypisana do urządzenia. Wybierz aplikację, a następnie wybierz pozycję **Wybierz**.
7. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**, a następnie upewnij się, że wszystkie informacje o aplikacji zostały wypełnione. Można dodać inne opcjonalne szczegóły, aby ułatwić organizowanie tej aplikacji, takie jak **Właściciel**, **Uwagi**, **Deweloper** oraz **Adres URL zasad ochrony prywatności** na potrzeby firmowych zasad ochrony prywatności.
8. Upewnij się, że wybrano pozycję **Tak** dla opcji **Wyświetlaj jako polecaną aplikację w Portalu firmy**, a następnie wybierz przycisk **OK**.
9. W okienku **Dodaj aplikację** wybierz pozycję **Dodaj**, aby dodać aplikację. Ta akcja powoduje przejście do **omówienia** danej aplikacji. Wybierz pozycję **Przypisania**, a następnie kliknij pozycję **Dodaj grupę**, aby przypisać ją do grupy testowej. Ustaw aplikację jako **dostępną** do pobrania. Aplikacja powinna wtedy być wyświetlana jako **polecana** na urządzeniu testowym.


- [Jak przypisać aplikacje do grup](apps-deploy.md)

## <a name="learn-more"></a>Dowiedz się więcej

* [What is app management with Intune? (Co to jest zarządzanie aplikacjami przy użyciu usługi Intune?)](app-management.md)
* [Przegląd cyklu życia aplikacji](app-lifecycle.md)
* [Co to są zasady ochrony aplikacji?](app-protection-policy.md)
