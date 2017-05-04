---
title: "Znane problemy w wersji zapoznawczej usługi Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się więcej o znanych problemach w wersji zapoznawczej"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 08e2f65bcd600489f6599d37e5ef56c205176cd7
ms.lasthandoff: 04/25/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Znane problemy w wersji zapoznawczej usługi Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Zapoznaj się z tym tematem, aby dowiedzieć się więcej o wszelkich znanych problemach w wersji zapoznawczej usługi Intune.

Aby zgłosić błąd, którego nie ma na tej liście, [otwórz żądanie pomocy technicznej](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Możesz poprosić o dodanie nowej funkcji do usługi Intune, wysyłając raport z witryny [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Grupy utworzone przez usługę Intune podczas migracji mogą mieć wpływ na funkcjonalność innych produktów firmy Microsoft

W przypadku migracji z klasycznej usługi Intune do witryny Azure Portal może zostać wyświetlona nowa grupa o nazwie **Wszyscy użytkownicy — b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Grupa ta zawiera wszystkich użytkowników usługi Azure Active Directory, nie tylko licencjonowanych użytkowników usługi Intune. Może to spowodować problemy z pozostałymi produktami firmy Microsoft, jeśli spodziewasz się, że niektórzy bieżący lub nowi użytkownicy nie są członkami żadnych grup.

### <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Zmodyfikowanie grup utworzonych przez usługę Intune podczas migracji spowoduje opóźnienie migracji

Podczas przygotowań do migracji grupy są kopiowane z usługi Intune do usługi Azure AD. Wszelkie dalsze zmiany wprowadzone w klasycznym portalu Intune zostaną zaktualizowane w grupie usługi Azure AD. Jednak zmian wprowadzonych w usłudze Azure AD nie będzie można z powrotem zsynchronizować z klasyczną konsolą usługi Intune. Może to spowodować niepowodzenie migracji do witryny Azure Portal oraz opóźnienia migracji.

### <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Zasady zgodności pochodzące z usługi Intune nie będą wyświetlane w nowej konsoli 

Wszystkie zasady zgodności utworzone w klasycznym portalu usługi Intune są migrowane, ale nie są wyświetlane w witrynie Azure Portal. Jest to spowodowane zmianami projektowymi w witrynie Azure Portal. Zasady zgodności utworzone w klasycznym portalu usługi Intune są mimo to wymuszane, ale trzeba je wyświetlać i edytować w portalu klasycznym.
Ponadto nowe zasady zgodności tworzone w witrynie Azure Portal nie będą widoczne w portalu klasycznym.
Więcej informacji znajduje się w artykule [Co to jest zgodność urządzeń](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance).




### <a name="administration-and-accounts"></a>Administracja i konta

Administratorzy globalni (określani także mianem administratorów dzierżawy) mogą w dalszym ciągu wykonywać codzienne zadania administracyjne, nie korzystając z oddzielnej licencji usługi Intune ani pakietu Enterprise Mobility Suite (EMS). Jeśli jednak administratorzy globalni zechcą korzystać z tej usługi na przykład w celu zarejestrowania swoich własnych urządzeń lub urządzeń firmowych albo zechcą korzystać z Portalu firmy w usłudze Intune, wówczas będą potrzebować licencji na usługę Intune lub pakiet EMS, podobnie jak każdy inny użytkownik.

### <a name="apple-enrollment-profile-migration"></a>Migracja profilu rejestracji firmy Apple
W ciągu następnych kilku miesięcy usługa Intune umożliwi zarządzanie programem Device Enrollment Program firmy Apple i rejestracją Apple Configurator za pomocą nowej witryny Azure Portal. Jeśli token programu Device Enrollment Program firmy Apple zostanie usunięty i nie nastąpi pobranie uaktualnionego tokenu, oryginalny token zostanie przywrócony w nowej witrynie Azure Portal w ramach migracji konta usługi Intune. Aby usunąć ten token i zapobiec rejestracji DEP, wystarczy usunąć token w witrynie Azure Portal. 

