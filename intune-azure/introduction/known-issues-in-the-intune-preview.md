---
title: "Znane problemy w wersji zapoznawczej usługi Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się więcej o znanych problemach w wersji zapoznawczej"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Znane problemy w wersji zapoznawczej usługi Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Zapoznaj się z tym tematem, aby dowiedzieć się więcej o wszelkich znanych problemach w wersji zapoznawczej usługi Intune.

Aby zgłosić błąd, którego nie ma na tej liście, [otwórz żądanie pomocy technicznej](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Możesz poprosić o dodanie nowej funkcji do usługi Intune, wysyłając raport z witryny [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="administration-and-accounts"></a>Administracja i konta

- Administratorzy globalni (określani także mianem administratorów dzierżawy) mogą w dalszym ciągu wykonywać codzienne zadania administracyjne, nie korzystając z oddzielnej licencji usługi Intune ani pakietu Enterprise Mobility Suite (EMS). Jeśli jednak administratorzy globalni zechcą korzystać z tej usługi na przykład w celu zarejestrowania swoich własnych urządzeń lub urządzeń firmowych albo zechcą korzystać z Portalu firmy w usłudze Intune, wówczas będą potrzebować licencji na usługę Intune lub pakiet EMS, podobnie jak każdy inny użytkownik.

## <a name="apple-enrollment-profile-migration"></a>Migracja profilu rejestracji firmy Apple
- W ciągu następnych kilku miesięcy usługa Intune umożliwi zarządzanie programem Device Enrollment Program firmy Apple i rejestracją Apple Configurator za pomocą nowej witryny Azure Portal. Jeśli token programu Device Enrollment Program firmy Apple zostanie usunięty i nie nastąpi pobranie uaktualnionego tokenu, oryginalny token zostanie przywrócony w nowej witrynie Azure Portal w ramach migracji konta usługi Intune. Aby usunąć ten token i zapobiec rejestracji DEP, wystarczy usunąć token w witrynie Azure Portal. 

