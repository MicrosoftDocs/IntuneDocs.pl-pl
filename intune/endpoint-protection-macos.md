---
title: Dodawanie programu Endpoint Protection w systemie macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Na urządzeniach z systemem macOS użyj programu Gatekeeper, aby określić, gdzie można instalować aplikacje (z uwzględnieniem sklepu Mac App Store). Ponadto włącz lub skonfiguruj zaporę, aby zezwolić na wybrane aplikacje, zablokować wybrane aplikacje, użyć trybu ukrywania, a nawet zablokować wybrane typy połączeń przychodzących przy użyciu usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 49194d49658042802cbc1148276445008ee1b09f
ms.sourcegitcommit: c3ae3c3dc46b62d9191813d25a196874ba4927be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/28/2018
ms.locfileid: "30254557"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Ustawienia programu Endpoint Protection w usłudze Intune dla systemu macOS

W tym artykule opisano ustawienia programu Endpoint Protection, które można skonfigurować dla urządzeń z systemem macOS. Te ustawienia obejmują ustawienia programu Gatekeeper oraz zapory na tych urządzeniach. Można je skonfigurować przy użyciu profilu urządzenia w usłudze Microsoft Intune.

## <a name="gatekeeper"></a>Program Gatekeeper

- **Zezwalaj na aplikacje pobrane z tych lokalizacji**: ogranicza aplikacje w oparciu o miejsce, z którego zostały pobrane. Celem jest ochrona urządzeń przed złośliwym oprogramowaniem oraz zezwalanie tylko na aplikacje z zaufanych źródeł. Opcje zezwalania: 
  - **Mac App Store**
  - **Mac App Store i zidentyfikowani deweloperzy**
  - **Dowolne miejsce**

- **Użytkownik może zastąpić program Gatekeeper**: zapobiega zastępowaniu ustawień programu Gatekeeper przez użytkowników, a także uniemożliwia użytkownikom stosowanie kombinacji Control + kliknięcie w celu instalacji aplikacji. Po włączeniu ustawienia użytkownicy mogą użyć kombinacji Control + kliknięcie na dowolnej aplikacji i zainstalować ją.

## <a name="firewall"></a>Zapora

Użyj zapory, aby blokować połączenia według poszczególnych aplikacji, a nie według portów. Użycie ustawień dla poszczególnych aplikacji umożliwia łatwiejsze uzyskanie korzyści z ochrony za pomocą zapory. Ponadto takie rozwiązanie pomaga zapobiegać przejmowaniu przez niepożądane aplikacje portów sieciowych, które są otwarte dla aplikacji dozwolonych.

- **Użyj zapory, aby chronić urządzenia przed nieautoryzowanym dostępem sieciowym poprzez kontrolowanie połączeń dla poszczególnych aplikacji.**
  - **Zapora**: włącz zaporę, aby skonfigurować obsługę połączeń przychodzących w danym środowisku.
  - **Połączenia przychodzące**: blokuj wszystkie połączenia przychodzące poza połączeniami wymaganymi dla podstawowych usług internetowych, np. DHCP, Bonjour i IPSec. Ta funkcja blokuje również wszystkie usługi udostępniania, takie jak Udostępnianie plików czy Udostępnianie ekranu. Jeśli używasz usług udostępniania, zachowaj to ustawienie jako **Nieskonfigurowane**.

- **Zezwalanie lub blokowanie połączeń przychodzących dla określonych aplikacji**
  - **Aplikacje dozwolone**: wybierz aplikacje, które są jawnie dozwolone do odbierania połączeń przychodzących.
  - **Aplikacje zablokowane**: wybierz aplikacje, które powinny blokować połączenia przychodzące.
  - **Tryb niewidzialności**: aby zapobiegać odpowiadaniu przez komputer na żądania sondowania, włącz tryb niewidzialności. Urządzenie nadal odpowiada na przychodzące żądania w przypadku autoryzowanych aplikacji. Nieoczekiwane żądania, takie jak ICMP (ping), są ignorowane.
