---
title: "Specjalne zagadnienia dotyczące migracji"
description: "W tym artykule przedstawiono zagadnienia specjalne dotyczące migracji, które należy uwzględnić przed rozpoczęciem kampanii migracji."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7ff1180275fddc7f0d6ef957c4680d7c34ad471e
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2017
---
# <a name="special-migration-considerations"></a>Specjalne zagadnienia dotyczące migracji

Istnieją pewne specjalne zagadnienia dotyczące migracji, które mogą mieć zastosowanie w zależności od istniejącego środowiska MDM innego dostawcy.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Resetowanie do ustawień fabrycznych na potrzeby programu Device Enrollment Program (DEP) firmy Apple

W ramach programu Device Enrollment Program (DEP) firmy Apple są wybierane konfiguracje urządzeń, które nie mogą zostać usunięte przez użytkownika końcowego. Aby zachować funkcje zaawansowanego zarządzania dostępne w ramach programu DEP, przed zarejestrowaniem urządzenia w usłudze Intune należy przywrócić ustawienia domyślne urządzenia przez reset do ustawień fabrycznych.

Aby dalej używać programu DEP do zarządzania urządzeniami w usłudze Intune, [skonfiguruj rejestrację urządzeń z systemem iOS za pomocą programu Device Enrollment Program](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Następne kroki

[Faza 2: Kampania migracji](migration-guide-campaign.md)
