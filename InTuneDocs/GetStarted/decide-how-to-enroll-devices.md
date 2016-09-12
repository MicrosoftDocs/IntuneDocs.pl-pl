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
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 90a26e1008a8e0800b07940c11a8adcd00cbb241
ms.openlocfilehash: becbaa195dc3fde6bc0a0edb0916c75a4d07c017


---

# Wybieranie metody rejestrowania urządzeń przenośnych

Rejestracja urządzenia przenośnego to proces, dzięki któremu smartfony, tablety i komputery mogą być zarządzane przez usługę Microsoft Intune. Jako administrator musisz określić, jak najlepiej zarejestrować urządzenia, w oparciu o następujące informacje:

 -  Własność (osobiste lub należące do firmy)
 -  Sposób użycia (udostępnione lub osobiste)
 -  Platforma (iOS, Android, Windows Phone, komputer z systemem Windows, komputer Mac)

Odpowiedzi na następujące pytania pomogą określić najlepszą metodę rejestracji dla zarządzanych urządzeń.

## **Czy pracownicy przynoszą własne urządzenia, czy są one udostępniane przez organizację?**

  - **Urządzenia należące do użytkowników** — rejestracja „BYOD” (przynieś własne urządzenie) — użytkownicy mogą instalować aplikację Portal firmy usługi Intune na urządzeniach, a następnie rejestrować je, aby uzyskać dostęp do zasobów firmy, takich jak poczta e-mail, aplikacje firmowe, dane firmowe i pomoc techniczna.  

  - **Urządzenia należące do firmy** — urządzenia należące do firmy można rejestrować na różne sposoby, w zależności od potrzeb organizacji i typów zarządzanych urządzeń.

> [!div class="button"]
[Rejestracja BYOD >](#what-byod-devices-can-your-users-enroll)   [Rejestracja COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Jakie urządzenia BYOD mogą rejestrować Twoi użytkownicy?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS i Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile i Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [komputery z systemem Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Czy urządzenia należące do firmy są udostępniane, czy mają dedykowanych użytkowników?**

- **Udostępnione urządzenia należące do firmy** — te urządzenia nie mają jednego użytkownika i zazwyczaj nie są konfigurowane do uzyskiwania dostępu do poczty e-mail. Przykładami takich urządzeń są urządzenia z kiosku lub urządzenia przeznaczone do konkretnych zadań, które użytkownicy pobierają z puli, a następnie zwracają. Zalecane metody rejestracji urządzeń zależą od platformy urządzeń.

- **Dedykowani użytkownicy** — urządzenia należące do firmy, które są wydawane poszczególnym użytkownikom, muszą być śledzone jako zasoby firmowe, podczas gdy użytkownicy mają możliwość uzyskania dostępu do poczty e-mail i danych na urządzeniach osobistych. Zalecane metody rejestracji urządzeń zależą od platformy urządzeń.

> [!div class="button"]
[Udostępnione >](#what-operating-system-are-your-shared-devices-running)   [Dedykowane >](#how-will-you-manage-dedicated-ios-devices)


## **Jakiego systemu operacyjnego używają udostępnione urządzenia?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Jak można zarządzać udostępnionymi urządzeniami z systemem iOS?**

- **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane za pomocą profilu DEP.

- **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień. Jeśli nie chcesz resetować urządzeń do ustawień fabrycznych, użyj rejestracji bezpośredniej.

- **Menedżer rejestracji urządzeń** — menedżer rejestracji urządzeń usługi Intune umożliwia menedżerowi lub administratorowi zarejestrowanie wielu urządzeń przenośnych za pomocą jednego konta użytkownika. Urządzenia te nie mają koligacji użytkownika (tzn. dedykowanych użytkowników) i muszą być rejestrowane przez zainstalowanie aplikacji Portal firmy i zalogowanie się do niej.

  > [!div class="button"]
  [Rejestracja programu DEP dla systemu iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Rejestracja bezpośrednia systemu iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [Rejestracja za pomocą menedżera rejestracji urządzeń >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## **Jak można zarządzać dedykowanymi urządzeniami z systemem iOS?**

Należące do firmy urządzenia z dedykowanymi użytkownikami można zarejestrować na następujące sposoby:

- **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane w usłudze Intune.

- **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień.

- **Oznaczanie numerami IMEI** — importując międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) urządzeń należących do firmy, można oznaczyć je jako urządzenia należące do firmy w usłudze Intune. Następnie użytkownicy mogą zarejestrować swoje urządzenia jako urządzenia osobiste, instalując aplikację Portal firmy, aby uzyskać dostęp do zasobów firmowych, np. poczty e-mail, aplikacji i innych danych.

  > [!div class="button"]
  [Oznaczanie numerem IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [Program DEP dla systemu iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Asystent ustawień systemu iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Oznaczanie numerem IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Aug16_HO2-->


