---
title: "Wybieranie metody rejestrowania urządzeń przenośnych | Microsoft Intune"
description: "Odpowiedz na kilka pytań, aby zdecydować, w jaki sposób ma się odbywać rejestrowanie urządzeń przenośnych w usłudze Intune"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: e1fe6b167b7d46f03472833bc1c3c19030f47bce
ms.openlocfilehash: 38dce11fa7df302bc2dffc3a2352d516c873fedb


---
# Wybieranie metody rejestrowania urządzeń przenośnych

Twoje odpowiedzi na tę serię pytań pomogą określić najlepszą metodę rejestracji dla urządzeń, którymi zarządzasz.

## **Jak można zarządzać dedykowanymi urządzeniami z systemem iOS?**

  > [!div class="button"]
  [Oznaczanie numerem IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [Program DEP dla systemu iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Asystent ustawień systemu iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Oznaczanie numerem IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Należące do firmy urządzenia z dedykowanymi użytkownikami można zarejestrować na następujące sposoby:

  - **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane w usłudze Intune.

  - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień.

  - **Oznaczanie numerami IMEI** — importując międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) urządzeń należących do firmy, można oznaczyć je jako urządzenia należące do firmy w usłudze Intune. Następnie użytkownicy mogą zarejestrować swoje urządzenia jako urządzenia osobiste, instalując aplikację Portal firmy, aby uzyskać dostęp do zasobów firmowych, np. poczty e-mail, aplikacji i innych danych.

  > [!div class="button"]
  [< Wstecz](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO2-->


