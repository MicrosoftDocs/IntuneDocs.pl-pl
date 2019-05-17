---
title: Zarządzanie aplikacjami zakupionymi zbiorczo lub aplikacjami bezpłatnymi ze sklepu Microsoft Store dla Firm
titleSuffix: Microsoft Intune
description: Informacje dotyczące synchronizacji aplikacji zakupionych (lub bezpłatnych) w usłudze Intune z poziomu sklepu Microsoft Store dla Firm.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67d99977776657219638980eb6de8a4079384185
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587505"
---
# <a name="how-to-manage-volume-purchased-or-free-apps-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Jak zarządzać aplikacjami zakupionymi zbiorczo (lub bezpłatnymi) w sklepie Microsoft Store dla Firm za pomocą usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[Sklep Microsoft dla Firm](https://www.microsoft.com/business-store) to miejsce, w którym można znaleźć i zakupić aplikacje dla całej organizacji, pojedynczo lub zbiorczo. Łącząc sklep z usługą Microsoft Intune, można zarządzać aplikacjami nabytymi w ramach zakupów zbiorczych bezpośrednio w witrynie Azure Portal. Przykład:
* Można zsynchronizować listę aplikacji zakupionych w sklepie (lub bezpłatnych) za pośrednictwem usługi Intune.
* Zsynchronizowane aplikacje są wyświetlane w konsoli administracyjnej usługi Intune. Można je przypisać w taki sam sposób, jak wszystkie inne aplikacje.
* Można śledzić liczbę dostępnych i używanych licencji w konsoli administracyjnej usługi Intune.
* Usługa Intune blokuje przypisywanie i instalację aplikacji, jeśli nie ma wystarczającej liczby dostępnych licencji.
* Aplikacje zarządzane przez sklep Microsoft Store dla Firm będą automatycznie odwoływać licencje, gdy użytkownik opuści firmę lub gdy administrator usunie użytkownika i jego urządzenia.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem synchronizowania i przypisywania aplikacji ze Sklepu Microsoft dla Firm przejrzyj następujące informacje:

- Skonfiguruj usługę Intune jako urząd zarządzania urządzeniami przenośnymi w Twojej organizacji.
- Musisz mieć zarejestrowane konto w Sklepie Microsoft dla Firm.
- Po powiązaniu konta w sklepie Microsoft Store dla Firm z usługą Intune nie będzie można zmienić konta na inne.
- Aplikacje zakupione w sklepie nie mogą być ręcznie dodawane do usługi Intune ani z niej usuwane. Aplikacje mogą być jedynie synchronizowane ze Sklepem Microsoft dla Firm.
- Licencjonowane aplikacje zakupione w sklepie Microsoft Store dla Firm zarówno w trybie online, jak i w trybie offline są synchronizowane w portalu usługi Intune. Następnie można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. 
- Instalacje aplikacji online są zarządzane przez sklep.
- Aplikacje w trybie offline, które są bezpłatne, mogą być również synchronizowane z usługą Intune. Te aplikacje są instalowane przez usługę Intune, a nie przez sklep.
- Aby móc używać tej funkcji, urządzenia muszą być przyłączone do usługi Active Directory Domain Services lub dołączone w miejscu pracy.
- Zarejestrowane urządzenia muszą używać systemu Windows 10 w wersji 1511 lub nowszej.

Ponadto powiązane zestawy i aplikacje licencjonowane w trybie offline synchronizowane ze sklepem Microsoft Store dla Firm będą teraz konsolidowane w jeden wpis aplikacji w interfejsie użytkownika. Wszelkie szczegóły wdrożenia z indywidualnych pakietów zostaną poddane migracji do pojedynczego wpisu. Aby wyświetlić powiązane zestawy w witrynie Azure Portal, wybierz pozycję **Licencje aplikacji** w bloku **Aplikacje klienckie**.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Kojarzenie konta w Sklepie Microsoft dla Firm z usługą Intune
Przed włączeniem synchronizacji w konsoli usługi Intune należy skonfigurować konto w sklepie, aby używało usługi Intune jako narzędzia do zarządzania:
1. Upewnij się, że logujesz się w sklepie [Microsoft Store dla Firm](https://www.microsoft.com/business-store) za pomocą tego samego konta dzierżawy, którego używasz do logowania się do usługi Intune.
2. W sklepie Store dla Firm wybierz kartę **Zarządzaj**, wybierz pozycję **Ustawienia** i wybierz kartę **Rozpowszechniaj**.
3. Jeśli usługa **Microsoft Intune** nie jest dostępna jako wybrane narzędzie do zarządzania urządzeniami przenośnymi, wybierz **pozycję Dodaj narzędzie do zarządzania**, aby dodać usługę **Microsoft Intune**. Jeśli nie masz usługi **Microsoft Intune** aktywowanej jako narzędzie do zarządzania urządzeniami przenośnymi, kliknij pozycję **Aktywuj** obok pozycji **Microsoft Intune**. Pamiętaj, że powinno się aktywować usługę **Microsoft Intune**, a nie pozycję **Rejestracja w usłudze Microsoft Intune**.

> [!NOTE]
> Wcześniej można było skojarzyć tylko jedno narzędzie do zarządzania, aby przypisać aplikację za pomocą Sklepu Microsoft dla Firm. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager). 

Teraz możesz przejść do konfigurowania synchronizacji w konsoli Intune.

## <a name="configure-synchronization"></a>Konfigurowanie synchronizacji

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
1. W okienku **Aplikacje klienckie** wybierz kolejno pozycje **Konfiguracja** > **Microsoft Store dla Firm**.
2. Kliknij przycisk **Włącz**.
3. Jeśli jeszcze tego nie zrobiono, kliknij link, aby zarejestrować się w Sklepie Microsoft dla Firm i skojarzyć swoje konto zgodnie z wcześniejszym opisem.
5. Z listy rozwijanej **Język** wybierz język, w którym aplikacje ze sklepu Microsoft Store dla Firm są wyświetlane w witrynie Azure Portal. Niezależnie od języka, w którym są wyświetlane, aplikacje są instalowane w języku użytkownika końcowego, o ile będzie dostępny.
6. Kliknij przycisk **Synchronizuj**, aby pobrać aplikacje zakupione w Sklepie Microsoft do usługi Intune.

## <a name="synchronize-apps"></a>Synchronizacja aplikacji

1. W obciążeniu **Aplikacje klienckie** wybierz kolejno pozycje **Konfiguracja** > **Sklep Microsoft dla Firm**.
2. Kliknij przycisk **Synchronizuj**, aby pobrać aplikacje zakupione w Sklepie Microsoft do usługi Intune.

## <a name="assign-apps"></a>Przypisywanie aplikacji

Aplikacje ze sklepu przypisuje się w taki sam sposób, jak każdą inną aplikację usługi Intune. Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune). 

Aplikacje w trybie offline można zastosować do grup użytkowników, grup urządzeń lub grup użytkowników i urządzeń.
Aplikacje w trybie offline można zainstalować dla określonego użytkownika na urządzeniu lub dla wszystkich użytkowników na urządzeniu. 


W przypadku przypisania aplikacji ze Sklepu Microsoft dla Firm licencja będzie używana przez każdego użytkownika, który zainstaluje aplikację. Jeśli zużyjesz wszystkie dostępne licencje dla przypisanej aplikacji, nie można będzie przypisać większej liczby kopii aplikacji. Wykonaj jedno z następujących działań:
* Odinstaluj aplikację z niektórych urządzeń.
* Zmniejsz zakres bieżącego przypisania i skieruj je tylko do użytkowników, dla których masz wystarczającą liczbę licencji.
* Kup więcej kopii aplikacji w Sklepie Microsoft dla Firm.

## <a name="remove-apps"></a>Usuwanie aplikacji

Aby usunąć aplikację synchronizowaną ze sklepem Microsoft Store dla firm, należy zalogować się do sklepu Microsoft Store dla firm i zwrócić aplikację. Proces jest taki sam, bez względu na to, czy aplikacja jest bezpłatna, czy nie. W przypadku aplikacji bezpłatnej sklep zwróci 0 USD. W poniższym przykładzie przedstawiono zwrot pieniędzy za bezpłatną aplikację. 

![Zrzut ekranu przedstawiający szczegóły usuwania aplikacji](./media/microsoft-store-for-business-01.png)

> [!NOTE]
> Ukrycie aplikacji w sklepie prywatnym nie zapobiega synchronizowaniu jej przez usługę Intune. W celu całkowitego usunięcia aplikacji należy uzyskać zwrot jej kosztów.

## <a name="next-steps"></a>Następne kroki

- [Zarządzanie aplikacjami i książkami kupionymi w ramach zakupów zbiorczych w usłudze Microsoft Intune](vpp-apps.md)
