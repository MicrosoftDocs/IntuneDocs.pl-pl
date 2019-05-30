---
title: Specjalne zagadnienia dotyczące migracji
titleSuffix: Microsoft Intune
description: W tym artykule przedstawiono zagadnienia specjalne dotyczące migracji, które należy uwzględnić przed rozpoczęciem kampanii migracji do usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f700a93c9640381e33b4b1d1fd442f9442acbe1
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050518"
---
# <a name="special-migration-considerations"></a>Specjalne zagadnienia dotyczące migracji

Istnieją pewne specjalne zagadnienia dotyczące migracji, które mogą mieć zastosowanie w zależności od istniejącego środowiska MDM innego dostawcy.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Czyszczenie dla programu Device Enrollment Program (DEP) firmy Apple

W ramach programu Device Enrollment Program (DEP) firmy Apple są wybierane konfiguracje urządzeń, które nie mogą zostać usunięte przez użytkownika końcowego. Aby zachować funkcje zaawansowanego zarządzania dostępne w ramach programu DEP, przed zarejestrowaniem urządzenia w usłudze Intune należy przywrócić ustawienia domyślne urządzenia za pomocą czyszczenia.

Aby dalej używać programu DEP do zarządzania urządzeniami w usłudze Intune, [skonfiguruj rejestrację urządzeń z systemem iOS za pomocą programu Device Enrollment Program](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Następne kroki

[Faza 2. Kampania migracji](migration-guide-campaign.md)
