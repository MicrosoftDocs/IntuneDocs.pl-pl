---
title: "Specjalne zagadnienia dotyczące migracji"
description: "Celem tego artykułu jest przedstawienie specjalnych zagadnień dotyczących migracji, jakie należy uwzględnić przed rozpoczęciem kampanii migracji."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Specjalne zagadnienia dotyczące migracji

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Istnieją pewne specjalne zagadnienia dotyczące migracji, które mogą mieć zastosowanie w zależności od istniejącego środowiska MDM innego dostawcy.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Resetowanie do ustawień fabrycznych na potrzeby programu Device Enrollment Program (DEP) firmy Apple

W ramach programu Device Enrollment Program (DEP) firmy Apple są wybierane konfiguracje urządzeń, które nie mogą zostać usunięte przez użytkownika końcowego. Aby zachować funkcje zaawansowanego zarządzania dostępne w ramach programu DEP, przed zarejestrowaniem urządzenia w usłudze Intune należy przywrócić ustawienia domyślne urządzenia poprzez reset do ustawień fabrycznych.

Aby dalej używać programu DEP do zarządzania urządzeniami w usłudze Intune, [skonfiguruj rejestrację urządzeń z systemem iOS za pomocą programu Device Enrollment Program](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Następne kroki 

[Faza 2: Kampania migracji](migration-guide-campaign.md)
