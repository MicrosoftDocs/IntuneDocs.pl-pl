---
title: Specjalne zagadnienia dotyczące migracji
titlesuffix: Microsoft Intune
description: W tym artykule przedstawiono zagadnienia specjalne dotyczące migracji, które należy uwzględnić przed rozpoczęciem kampanii migracji do usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 23619048faca4cdf9d64b15b0db7c09cb958a082
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43314044"
---
# <a name="special-migration-considerations"></a>Specjalne zagadnienia dotyczące migracji

Istnieją pewne specjalne zagadnienia dotyczące migracji, które mogą mieć zastosowanie w zależności od istniejącego środowiska MDM innego dostawcy.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Czyszczenie dla programu Device Enrollment Program (DEP) firmy Apple

W ramach programu Device Enrollment Program (DEP) firmy Apple są wybierane konfiguracje urządzeń, które nie mogą zostać usunięte przez użytkownika końcowego. Aby zachować funkcje zaawansowanego zarządzania dostępne w ramach programu DEP, przed zarejestrowaniem urządzenia w usłudze Intune należy przywrócić ustawienia domyślne urządzenia za pomocą czyszczenia.

Aby dalej używać programu DEP do zarządzania urządzeniami w usłudze Intune, [skonfiguruj rejestrację urządzeń z systemem iOS za pomocą programu Device Enrollment Program](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Następne kroki

[Faza 2: Kampania migracji](migration-guide-campaign.md)
