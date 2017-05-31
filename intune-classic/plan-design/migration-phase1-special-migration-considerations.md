---
title: "Specjalne zagadnienia dotyczące migracji | Microsoft Docs"
description: "Celem tego artykułu jest przedstawienie specjalnych zagadnień dotyczących migracji, jakie należy uwzględnić przed rozpoczęciem kampanii migracji."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7e0adb862d8c60805b3b34406e193df5a93be381
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-special-migration-considerations"></a>Faza 1: Specjalne zagadnienia dotyczące migracji

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Istnieją pewne specjalne zagadnienia dotyczące migracji, które mogą mieć zastosowanie w zależności od istniejącego środowiska MDM innego dostawcy.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Resetowanie do ustawień fabrycznych na potrzeby programu Device Enrollment Program (DEP) firmy Apple

W ramach programu Device Enrollment Program (DEP) firmy Apple są wybierane konfiguracje urządzeń, które nie mogą zostać usunięte przez użytkownika końcowego. Aby zachować funkcje zaawansowanego zarządzania dostępne w ramach programu DEP, przed zarejestrowaniem urządzenia w usłudze Intune należy przywrócić ustawienia domyślne urządzenia poprzez reset do ustawień fabrycznych.

Aby w dalszym ciągu używać programu DEP do zarządzania urządzeniami w usłudze Intune:

1.  Dodaj obsługę [programu DEP w usłudze Intune](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

2.  Przejdź do swojego konta w programie DEP firmy Apple i [przypisz numery seryjne urządzeń należących do programu DEP](https://help.apple.com/deployment/business/#/tesf9562af26) z istniejącego rozwiązania MDM do usługi Intune.

3.  [Zsynchronizuj](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) swoje konto DEP z usługą Intune.

4.  [Utwórz i przypisz](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) odpowiednie profile rejestracji w programie DEP do numerów seryjnych w usłudze Intune.

5.  Zresetuj urządzenia do ustawień fabrycznych (zdalnie — za pośrednictwem bieżącego rozwiązania MDM — lub ręcznie na poszczególnych urządzeniach).

6.  Przekaż urządzenia użytkownikom końcowym.

## <a name="next-steps"></a>Następne kroki 

[Faza 2: Kampania migracji](/intune-classic/plan-design/migration-phase2-migration-campaign)

