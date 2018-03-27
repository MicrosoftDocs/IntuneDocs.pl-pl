---
title: Zarządzanie aplikacjami ze Sklepu Microsoft dla Firm
description: Połącz usługę Intune ze Sklepem Microsoft dla Firm, aby wdrażać aplikacje zakupione zbiorczo z poziomu konsoli usługi Intune i zarządzać nimi
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 02/02/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 50fc27efc34ab6c13fad714e41be0d87c5ab0df9
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Zarządzanie aplikacjami zakupionymi w Sklepie Microsoft dla Firm za pomocą usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Sklep Microsoft dla Firm](https://www.microsoft.com/business-store) to miejsce, w którym można znaleźć i zakupić aplikacje dla całej organizacji, pojedynczo lub zbiorczo. Łącząc Sklep Windows z usługą Microsoft Intune, można zarządzać aplikacjami zakupionymi zbiorczo z poziomu konsoli usługi Intune. Przykład:
* Można zsynchronizować listę aplikacji zakupionych w sklepie za pośrednictwem usługi Intune.
* Aplikacje, które są synchronizowane, zostają wyświetlone w konsoli administracyjnej usługi Intune. Można je wdrażać w taki sam sposób, jak wszystkie inne aplikacje.
* Można śledzić liczbę dostępnych i używanych licencji w konsoli administracyjnej usługi Intune.
* Usługa Intune blokuje wdrażanie i instalację aplikacji, jeśli nie ma wystarczającej liczby dostępnych licencji.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem synchronizowania i wdrażania aplikacji ze Sklepu Microsoft dla Firm przejrzyj następujące informacje:
* Musisz skonfigurować usługę Intune jako urząd zarządzania urządzeniami przenośnymi w Twojej organizacji. Aby uzyskać więcej informacji, zobacz [Wymagania wstępne dotyczące rejestrowania urządzeń w usłudze Microsoft Intune](prerequisites-for-enrollment.md).
* Musisz mieć zarejestrowane konto w Sklepie Microsoft dla Firm.
* Po powiązaniu konta w Sklepie Windows dla firm z usługą Intune nie będzie można zmienić konta na inne.
* Aplikacje zakupione w sklepie nie mogą być ręcznie dodawane do usługi Intune ani z niej usuwane. Aplikacje mogą być jedynie synchronizowane ze Sklepem Microsoft dla Firm.
* Usługa Intune synchronizuje tylko licencjonowane aplikacje nabyte w Sklepie Microsoft dla Firm.
* Urządzenia muszą być przyłączone do usług domenowych Active Directory lub dołączone do miejsca pracy, aby móc używać tej funkcji.
* Zarejestrowane urządzenia muszą używać wersji 1511 systemu Windows 10.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Kojarzenie konta w Sklepie Microsoft dla Firm z usługą Intune
Przed włączeniem synchronizacji w konsoli usługi Intune należy skonfigurować konto w sklepie, aby używało usługi Intune jako narzędzia do zarządzania:
1. Upewnij się, że logujesz się w Sklepie Windows dla firm za pomocą tego samego konta dzierżawy, którego używasz do logowania się do usługi Intune.
2. W Sklepie dla firm wybierz opcję **Ustawienia** > **Narzędzia do zarządzania**.
3. Na stronie Narzędzia do zarządzania wybierz opcję **Dodaj narzędzie do zarządzania**, a następnie wybierz pozycję **Microsoft Intune**.

> [!NOTE]
> Wcześniej w przypadku wdrażania aplikacji ze Sklepu Microsoft dla Firm za pomocą więcej niż jednego narzędzia do zarządzania można było skojarzyć ze Sklepem Microsoft dla Firm tylko jedno z tych narzędzi. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager).

Teraz możesz przejść do konfigurowania synchronizacji w konsoli Intune.

## <a name="configure-synchronization"></a>Konfigurowanie synchronizacji

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja**.
2. W obszarze roboczym **Administracja** rozwiń węzeł **Zarządzanie urządzeniami przenośnymi** > **Windows**, a następnie wybierz pozycję **Sklep dla firm**.
3. Na stronie **Sklepu Microsoft dla firm** wykonaj następujące czynności:
 * Jeśli jeszcze tego nie zrobiono, kliknij link do rejestracji w Sklepie Microsoft dla Firm.
 * Po zarejestrowaniu się wybierz opcję **Konfiguruj synchronizację**.
4. W oknie dialogowym **Konfiguracja synchronizacji aplikacji Sklepu Microsoft dla Firm** wybierz pozycję **Włącz synchronizację Sklepu Microsoft dla Firm**.
5. Z listy rozwijanej **Język** wybierz język, w którym aplikacje ze Sklepu Microsoft dla Firm będą wyświetlane w konsoli usługi Intune. Niezależnie od języka, w którym są wyświetlane, aplikacje zostaną zainstalowane w języku użytkownika końcowego, o ile będzie dostępny.
6. Kliknij przycisk **OK**.

## <a name="synchronize-apps"></a>Synchronizacja aplikacji

1. Na stronie **Sklepu Microsoft dla Firm** wybierz opcję **Synchronizuj teraz**, aby zsynchronizować aplikacje zakupione w sklepie za pomocą usługi Intune.
2. W obszarze roboczym **Aplikacje** wybierz pozycję **Aplikacje** > **Aplikacje kupione w ramach zakupów zbiorczych**, aby wyświetlić aplikacje, które można wdrożyć, i upewnić się, że zakupione aplikacje zostały zaimportowane prawidłowo. Aplikacje w tym węźle są wyświetlane z całkowitą liczbą posiadanych licencji oraz liczbą dostępnych licencji.
Można na przykład dokonać zakupu aplikacji Portal firmy (licencjonowanej online) ze Sklepu Microsoft dla Firm, zsynchronizować ją z konsolą usługi Intune, a następnie wdrożyć ją jako aplikację wymaganą w wybranych urządzeniach systemu Windows 10. 


## <a name="deploy-apps"></a>Wdrażanie aplikacji

Aplikacje ze sklepu wdraża się w taki sam sposób, jak każdą inną aplikację usługi Intune. Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md).
W przypadku wdrożenia aplikacji ze Sklepu Microsoft dla Firm licencja będzie używana przez każdego użytkownika, który zainstaluje aplikację. Jeśli zużyjesz wszystkie dostępne licencje dla wdrażanej aplikacji, nie będziesz w stanie wdrożyć większej liczby kopii aplikacji. W takim przypadku należy wykonać jedną z następujących czynności:
* Odinstaluj aplikację z niektórych urządzeń.
* Zmniejsz zakres bieżącego wdrożenia i skieruj je tylko do użytkowników, dla których masz wystarczającą liczbę licencji.
* Kup więcej kopii aplikacji w Sklepie Microsoft dla Firm.

> [!Important]
> Wdrożone aplikacje są dostępne tylko dla użytkownika, który pierwotnie zarejestrował urządzenie. Inni użytkownicy nie mogą uzyskiwać dostępu do aplikacji.


### <a name="see-also"></a>Zobacz też
[Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)
