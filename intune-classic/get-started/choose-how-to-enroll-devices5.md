---
title: Wybieranie metody rejestrowania urządzeń przenośnych
description: Odpowiedz na kilka pytań, aby zdecydować, w jaki sposób ma się odbywać rejestrowanie urządzeń przenośnych w usłudze Intune
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: dougeby
ms.date: 03/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: c7e750d308c4167dd6e99f503ed52d3a96ea630b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Wybieranie metody rejestrowania urządzeń przenośnych

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Twoje odpowiedzi na tę serię pytań pomogą określić najlepszą metodę rejestracji dla urządzeń, którymi zarządzasz.

## <a name="how-will-you-manage-shared-ios-devices"></a>**Jak można zarządzać udostępnionymi urządzeniami z systemem iOS?**

> [!div class="button"]
> [Rejestracja programu DEP dla systemu iOS >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
> [Rejestracja bezpośrednia systemu iOS >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
> [Rejestracja za pomocą menedżera rejestracji urządzeń >](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane za pomocą profilu DEP.

  - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień. Jeśli nie chcesz resetować urządzeń do ustawień fabrycznych, użyj rejestracji bezpośredniej.

  - **Menedżer rejestracji urządzeń** — menedżer rejestracji urządzeń usługi Intune umożliwia menedżerowi lub administratorowi zarejestrowanie wielu urządzeń przenośnych za pomocą jednego konta użytkownika. Urządzenia te nie mają koligacji użytkownika (tzn. dedykowanych użytkowników) i muszą być rejestrowane przez zainstalowanie aplikacji Portal firmy i zalogowanie się do niej.

> [!div class="button"]
> [< Wstecz](choose-how-to-enroll-devices3.md)
