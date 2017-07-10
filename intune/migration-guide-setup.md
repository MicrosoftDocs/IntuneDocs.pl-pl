---
title: "Konfiguracja podstawowa usługi Intune"
description: "Celem tego artykułu jest przedstawienie niezbędnych instrukcji dotyczących konfigurowania usługi Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Konfiguracja podstawowa

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Po dokonaniu oceny środowiska należy rozpocząć konfigurowanie usługi Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Zależności zewnętrzne dla wdrożenia usługi Intune

### <a name="identity"></a>Tożsamość

Usługa Intune wymaga usługi Azure Active Directory (AAD) jako dostawcy tożsamości i grup użytkowników.

-   Dowiedz się więcej o [wymaganiach dotyczących tożsamości](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Dowiedz się więcej o [wymaganiach dotyczących synchronizacji katalogów](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Dowiedz się więcej o [wymaganiach dotyczących uwierzytelniania wieloskładnikowego](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Dowiedz się więcej na temat [planowania grup użytkowników i urządzeń](/intune/users-permissions-add).

-   Dowiedz się, [jak tworzyć grupy użytkowników i urządzeń](/intune/groups-get-started).

Jeśli Twoja organizacja używa już usługi Office 365, istotne jest, czy usługa Intune używa tego samego środowiska usługi Azure Active Directory.

### <a name="pki-optional"></a>Infrastruktura PKI (opcjonalnie)

Jeśli w usłudze Intune planowane jest użycie uwierzytelniania opartego na certyfikatach wraz z profilami sieci VPN, sieci Wi-Fi lub poczty e-mail, należy upewnić się, że istnieje obsługiwana [infrastruktura PKI](/intune/certificates-configure), za pomocą której można tworzyć i wdrażać profile certyfikatów.

Więcej informacji o konfigurowaniu certyfikatów w usłudze Intune można znaleźć poniżej.

-   [Jak skonfigurować infrastrukturę certyfikatów dla profilu SCEP](/intune/certificates-scep-configure).

-   [Jak skonfigurować infrastrukturę certyfikatów dla profilu PFX](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Lista zadań konfiguracji usługi Intune

### <a name="task-1-intune-subscription"></a>Zadanie 1. Subskrypcja usługi Intune

Aby można było przeprowadzić migrację do usługi Intune, należy dysponować subskrypcją usługi Intune.

-   Na [tej stronie](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) można znaleźć instrukcje dotyczące poniższych zagadnień:

    -   Tworzenie nowej subskrypcji usługi Intune połączonej z nową dzierżawą usługi AAD.

    -   Łączenie subskrypcji usługi Intune przez zalogowanie się do istniejącej dzierżawy usługi AAD.

### <a name="task-2-assign-intune-user-licenses"></a>Zadanie 2. Przypisanie licencji użytkowników usługi Intune

-   Dowiedz się, [jak przypisać licencje użytkowników usługi Intune](licenses-assign.md).

-   Jeśli masz nową dzierżawę usługi Azure Active Directory, dowiedz się, [jak utworzyć nowych użytkowników lub zsynchronizować użytkowników z lokalnej usługi Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Zadanie 3. Ustawianie urzędu MDM na usługę Intune

Usługą Intune można zarządzać za pomocą witryny Azure Portal lub konsoli programu Configuration Manager w wersji Current Branch. Jeśli nie jest konieczna integracja usługi Intune z wdrożeniem programu Configuration Manager w wersji Current Branch, zaleca się zarządzanie tą usługą przy użyciu witryny [Azure Portal](https://portal.azure.com).

Aby umożliwić korzystanie z usługi Intune za pomocą witryny Azure Portal, ustaw urząd MDM na usługę **Intune**. Użycie innego urzędu MDM pozwala usłudze Intune przenieść funkcje zarządzania MDM do alternatywnych konsoli zarządzania firmy Microsoft. Takie przypadki występują rzadko.

> [!IMPORTANT]
> Jeśli pierwszy raz przenosisz funkcje zarządzania urządzeniami przenośnymi do usługi Intune, należy ustawić urząd MDM na usługę Intune.

-   Dowiedz się, [jak ustawić urząd zarządzania urządzeniami przenośnymi](/intune/mdm-authority-set).

## <a name="next-step"></a>Następny krok

[Konfiguracja zasad zarządzania urządzeniami i aplikacjami](migration-guide-configure-policies.md)
