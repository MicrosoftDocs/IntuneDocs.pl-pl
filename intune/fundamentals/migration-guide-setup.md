---
title: Podstawowa konfiguracja usługi Microsoft Intune
description: Ten artykuł zawiera niezbędne instrukcje dotyczące konfigurowania usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ca0983b7b637b7e85bef97cd77e6c870c4e43eb
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510014"
---
# <a name="basic-setup"></a>Konfiguracja podstawowa

Po dokonaniu oceny środowiska należy rozpocząć konfigurowanie usługi Microsoft Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Zależności zewnętrzne dla wdrożenia usługi Intune

### <a name="identity"></a>Tożsamość

Usługa Intune wymaga usługi Azure Active Directory (AAD) jako dostawcy tożsamości i grup użytkowników. Dowiedz się więcej na następujące tematy:

- [Wymagania dotyczące tożsamości](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

- [Wymagania dotyczące synchronizacji katalogu](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

- [Uwierzytelnianie wieloskładnikowe](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

- [Planowanie grup użytkowników i urządzeń](users-add.md)

- [Sposoby tworzenia grup użytkowników i urządzeń](groups-get-started.md)

Jeśli Twoja organizacja używa już usługi Office 365, usługa Intune musi używać tego samego środowiska usługi Azure Active Directory.

### <a name="pki-optional"></a>Infrastruktura PKI (opcjonalnie)

Jeśli w usłudze Intune planowane jest użycie uwierzytelniania opartego na certyfikatach wraz z profilami sieci VPN, sieci Wi-Fi lub poczty e-mail, należy upewnić się, że istnieje obsługiwana [infrastruktura PKI](../protect/certificates-configure.md), za pomocą której można tworzyć i wdrażać profile certyfikatów. Dowiedz się więcej o konfigurowaniu certyfikatów w usłudze Intune:

- [Jak skonfigurować infrastrukturę certyfikatów dla profilu SCEP](/intune/certificates-scep-configure)

- [Jak skonfigurować infrastrukturę certyfikatów dla profilu PFX](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Lista zadań konfiguracji usługi Intune

### <a name="task-1-intune-subscription"></a>Zadanie 1. Subskrypcję usługi Intune

Aby można było przeprowadzić migrację do usługi Intune, należy dysponować subskrypcją usługi Intune.

- Na [tej stronie](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) można znaleźć instrukcje dotyczące poniższych zagadnień:

  - Tworzenie nowej subskrypcji usługi Intune połączonej z nową dzierżawą usługi AAD.

  - Łączenie subskrypcji usługi Intune przez zalogowanie się do istniejącej dzierżawy usługi AAD.

### <a name="task-2-assign-intune-user-licenses"></a>Zadanie 2. Przypisanie licencji użytkowników usługi Intune

- Dowiedz się, [jak przypisać licencje użytkowników usługi Intune](licenses-assign.md).

- Jeśli masz nową dzierżawę usługi Azure Active Directory, dowiedz się, [jak utworzyć nowych użytkowników lub zsynchronizować użytkowników z lokalnej usługi Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Zadanie 3. Ustawianie usługi Intune jako urzędu rozwiązania MDM

Usługą Intune można zarządzać za pomocą witryny Azure Portal lub konsoli programu Configuration Manager w wersji Current Branch. Jeśli nie jest konieczna integracja usługi Intune z wdrożeniem programu Configuration Manager w wersji Current Branch, zalecamy zarządzanie tą usługą przy użyciu witryny [Azure Portal](https://portal.azure.com).

Aby umożliwić korzystanie z usługi Intune za pomocą witryny Azure Portal, ustaw urząd MDM na usługę **Intune**. Użycie innego urzędu MDM pozwala usłudze Intune przenieść funkcje zarządzania MDM do alternatywnych konsoli zarządzania firmy Microsoft. Takie przypadki występują rzadko.

> [!IMPORTANT]
> Jeśli pierwszy raz przenosisz funkcje zarządzania urządzeniami przenośnymi do usługi Intune, należy ustawić urząd MDM na usługę Intune.

Dowiedz się, [jak ustawić urząd zarządzania urządzeniami przenośnymi](mdm-authority-set.md).

## <a name="next-step"></a>Następny krok

Skonfiguruj [zasady zarządzania urządzeniami i aplikacjami](../migration-guide-configure-policies.md).
