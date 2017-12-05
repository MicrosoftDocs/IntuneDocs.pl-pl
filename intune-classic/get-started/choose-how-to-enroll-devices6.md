---
title: "Wybieranie metody rejestrowania urządzeń przenośnych"
description: "Odpowiedz na kilka pytań, aby zdecydować, w jaki sposób ma się odbywać rejestrowanie urządzeń przenośnych w usłudze Intune"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 364f67222ec44754dcee9fea6475777822a9886e
ms.sourcegitcommit: 70dc0aaad51b447e173b663d1092d993dc81ffdd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2017
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Wybieranie metody rejestrowania urządzeń przenośnych

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Twoje odpowiedzi na tę serię pytań pomogą określić najlepszą metodę rejestracji dla urządzeń, którymi zarządzasz.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Jak można zarządzać dedykowanymi urządzeniami należącymi do firmy?**

  > [!div class="button"]
[Program DEP dla systemu iOS >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[Asystent ustawień systemu iOS >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[Oznaczanie numerami IMEI >](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Należące do firmy urządzenia z dedykowanymi użytkownikami można zarejestrować na następujące sposoby:

  - **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane w usłudze Intune.

  - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień.

  - **Oznaczanie numerami IMEI** — importując międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) urządzeń należących do firmy, można oznaczyć je jako urządzenia należące do firmy w usłudze Intune. Jest to jedyny sposób pozwalający zidentyfikować należące do firmy dedykowane (przeznaczone do użytku przez jednego użytkownika) urządzenia z systemem Windows i Android. Urządzenia z systemem iOS, które nie zostaną zarejestrowane przy użyciu programu Device Enrollment Program firmy Apple lub programu Apple Configurator, mogą również być oznaczane numerem IMEI. Po wstępnym zadeklarowaniu urządzenia, które ma na celu oznaczenie go jako „firmowe”, można przekazać urządzenia użytkownikom. Następnie użytkownicy mogą zarejestrować swoje urządzenia jako urządzenia dedykowane, instalując aplikację Portal firmy, aby uzyskać dostęp do zasobów firmowych, np. poczty e-mail, aplikacji i innych danych.

> [!div class="button"]
[< Wstecz](choose-how-to-enroll-devices3.md)
