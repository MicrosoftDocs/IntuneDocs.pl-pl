---
title: "Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące synchronizacji aplikacji ze Sklepu Windows dla firm w usłudze Intune, a następnie przypisywania ich i śledzenia."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d02d7c3367e18c96cc1d72de3a3a0ef581ef63ff
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Jak zarządzać aplikacjami zakupionymi w Sklepie Windows dla firm za pomocą usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


[Sklep Windows dla firm](https://www.microsoft.com/business-store) to miejsce, w którym można znaleźć i zakupić aplikacje dla całej organizacji, pojedynczo lub zbiorczo. Łącząc sklep z usługą Microsoft Intune, można zarządzać aplikacjami nabytymi w ramach zakupów zbiorczych bezpośrednio w portalu usługi Intune. Na przykład:
* Można zsynchronizować listę aplikacji zakupionych w sklepie za pośrednictwem usługi Intune.
* Aplikacje, które są synchronizowane, zostają wyświetlone w konsoli administracyjnej usługi Intune. Można je przypisać w taki sam sposób, jak wszystkie inne aplikacje.
* Można śledzić liczbę dostępnych i używanych licencji w konsoli administracyjnej usługi Intune.
* Usługa Intune blokuje wdrażanie i instalację aplikacji, jeśli nie ma wystarczającej liczby dostępnych licencji.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem synchronizowania i wdrażania aplikacji ze Sklepu Windows dla firm przejrzyj następujące informacje:
* Musisz skonfigurować usługę Intune jako urząd zarządzania urządzeniami przenośnymi w Twojej organizacji.
* Musisz mieć zarejestrowane konto w Sklepie Windows dla firm.
* Po powiązaniu konta w Sklepie Windows dla firm z usługą Intune nie będzie można zmienić konta na inne.
* Aplikacje zakupione w sklepie nie mogą być ręcznie dodawane do usługi Intune ani z niej usuwane. Aplikacje mogą być jedynie synchronizowane ze Sklepem Windows dla firm.
* Usługa Intune synchronizuje tylko licencjonowane aplikacje nabyte w Sklepie Windows dla firm.
* Aby móc używać tej funkcji, urządzenia muszą być przyłączone do usług domenowych Active Directory lub dołączone do miejsca pracy.
* Zarejestrowane urządzenia muszą używać systemu Windows 10 w wersji 1511 lub nowszej.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Skojarz konto w Sklepie Windows dla firm z usługą Intune
Przed włączeniem synchronizacji w konsoli usługi Intune należy skonfigurować konto w sklepie, aby używało usługi Intune jako narzędzia do zarządzania:
1. Upewnij się, że logujesz się w Sklepie Windows dla firm za pomocą tego samego konta dzierżawy, którego używasz do logowania się do usługi Intune.
2. W Sklepie dla firm wybierz opcję **Ustawienia** > **Narzędzia do zarządzania**.
3. Na stronie Narzędzia do zarządzania wybierz opcję **Dodaj narzędzie do zarządzania**, a następnie wybierz pozycję **Microsoft Intune**.

> [!NOTE]
> Wcześniej w przypadku wdrażania aplikacji ze Sklepu Windows dla firm za pomocą więcej niż jednego narzędzia do zarządzania można było skojarzyć ze Sklepem Windows dla firm tylko jedno z tych narzędzi. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager).

Teraz możesz przejść do konfigurowania synchronizacji w konsoli Intune.

## <a name="configure-synchronization"></a>Konfigurowanie synchronizacji

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
1. W bloku **Aplikacje mobilne** wybierz kolejno pozycje **Instalacja** > **Sklep Windows dla firm**.
2. Kliknij przycisk **Włącz**.
3. Jeśli jeszcze tego nie zrobiono, kliknij link do rejestracji w Sklepie Windows dla firm i skojarz swoje konto zgodnie ze wcześniejszym opisem.
5. Z listy rozwijanej **Język** wybierz język, w którym aplikacje ze Sklepu Windows dla firm będą wyświetlane w portalu usługi Intune. Niezależnie od języka, w którym są wyświetlane, aplikacje zostaną zainstalowane w języku użytkownika końcowego, o ile będzie dostępny.
6. Kliknij przycisk **Synchronizuj**, aby pobrać aplikacje zakupione w Sklepie Windows do usługi Intune.

## <a name="synchronize-apps"></a>Synchronizacja aplikacji

1. W obciążeniu **Zarządzaj aplikacjami** wybierz kolejno pozycje **Instalacja** > **Sklep Windows dla firm**.
2. Kliknij przycisk **Synchronizuj**, aby pobrać aplikacje zakupione w Sklepie Windows do usługi Intune.

## <a name="assign-apps"></a>Przypisywanie aplikacji

Aplikacje ze sklepu przypisuje się w taki sam sposób, jak każdą inną aplikację usługi Intune. Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](deploy-apps.md) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune). Jednak zamiast przypisywać aplikacje ze strony **Wszystkie aplikacje**, można przypisać je ze strony **Aplikacje z licencją**.

W przypadku przypisania aplikacji ze Sklepu Windows dla firm licencja będzie używana przez każdego użytkownika, który zainstaluje aplikację. Jeśli zużyjesz wszystkie dostępne licencje dla wdrażanej aplikacji, nie będziesz w stanie wdrożyć większej liczby kopii aplikacji. W takim przypadku należy wykonać jedną z następujących czynności:
* Odinstaluj aplikację z niektórych urządzeń.
* Zmniejsz zakres bieżącego wdrożenia i skieruj je tylko do użytkowników, dla których masz wystarczającą liczbę licencji.
* Kup więcej kopii aplikacji w Sklepie Windows dla firm.

> [!Important]
> Wdrożone aplikacje są dostępne tylko dla użytkownika, który pierwotnie zarejestrował urządzenie. Inni użytkownicy nie mogą uzyskiwać dostępu do aplikacji.

