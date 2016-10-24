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
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a5f80058e004f119acc9a918123c897b72b71314
ms.openlocfilehash: 026ac12f12046f59eaac6e8bedc0669bcd93fb75


---
# Wybieranie metody rejestrowania urządzeń przenośnych

Twoje odpowiedzi na tę serię pytań pomogą określić najlepszą metodę rejestracji dla urządzeń, którymi zarządzasz.


## **Jak można zarządzać udostępnionymi urządzeniami z systemem iOS?**

  > [!div class="button"]
  [Rejestracja programu DEP dla systemu iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)<br>[Rejestracja bezpośrednia systemu iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)<br>[Rejestracja za pomocą menedżera rejestracji urządzeń >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane za pomocą profilu DEP.

  - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień. Jeśli nie chcesz resetować urządzeń do ustawień fabrycznych, użyj rejestracji bezpośredniej.

  - **Menedżer rejestracji urządzeń** — menedżer rejestracji urządzeń usługi Intune umożliwia menedżerowi lub administratorowi zarejestrowanie wielu urządzeń przenośnych za pomocą jednego konta użytkownika. Urządzenia te nie mają koligacji użytkownika (tzn. dedykowanych użytkowników) i muszą być rejestrowane przez zainstalowanie aplikacji Portal firmy i zalogowanie się do niej.

  > [!div class="button"]
  [< Wstecz](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO5-->


