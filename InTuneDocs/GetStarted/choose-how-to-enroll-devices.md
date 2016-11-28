---
title: "Wybieranie metody rejestrowania urządzeń przenośnych | Microsoft Intune"
description: "Odpowiedz na kilka pytań, aby zdecydować, w jaki sposób ma się odbywać rejestrowanie urządzeń przenośnych w usłudze Intune"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a563105aafb447c6e009cca09645e630709ff72d
ms.openlocfilehash: 143f77bde09648a233ff09e9740668191a50cb1e


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Wybieranie metody rejestrowania urządzeń przenośnych

Odpowiedzi na następujące pytania pomagają określić najlepszą metodę rejestracji dla zarządzanych urządzeń.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Czy pracownicy przynoszą własne urządzenia, czy są one udostępniane przez organizację?**

  - **Urządzenia należące do użytkowników** — rejestracja oparta na modelu „Przynieś własne urządzenie” (BYOD, bring your own device)
  - **Urządzenia należące do firmy** — rejestracja urządzeń należących do firmy (COD, company-owned device)

> [!div class="button"]
[Rejestracja w trybie „Przynieś własne urządzenie” (BYOD, bring your own device) >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[Rejestracja urządzeń należących do firmy (COD, company-owned device) >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Jakie urządzenia BYOD mogą rejestrować użytkownicy?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS i Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile i Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [komputery z systemem Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Czy urządzenia należące do firmy są współużytkowane, czy mają przypisanych użytkowników?**

> [!div class="button"]
[Udostępnione >](#what-operating-system-are-your-shared-devices-running)   [Dedykowane >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Jakiego systemu operacyjnego używają udostępnione urządzenia?**

> [!div class="button"]
[Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Jak można zarządzać udostępnionymi urządzeniami z systemem iOS?**

> [!div class="button"]
[Rejestracja programu DEP dla systemu iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Rejestracja bezpośrednia systemu iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Rejestracja za pomocą menedżera rejestracji urządzeń >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Program Device Enrollment Program firmy Apple (DEP)** — urządzenia z systemem iOS zakupione lub zarządzane w programie DEP można skojarzyć z profilem rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane za pomocą profilu DEP.

  - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj opcji rejestracji za pomocą Asystenta ustawień. Jeśli nie chcesz resetować urządzeń do ustawień fabrycznych, użyj opcji rejestracji bezpośredniej.

  - **Menedżer rejestracji urządzeń (usługa Intune)** — menedżer rejestracji urządzeń usługi Intune umożliwia menedżerowi lub administratorowi zarejestrowanie wielu urządzeń przenośnych za pomocą jednego konta użytkownika. Urządzenia te nie mogą mieć przypisanych użytkowników (tzn. koligacji użytkownika) i muszą być rejestrowane przez zainstalowanie aplikacji Portal firmy i zalogowanie się do niej.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Jak można zarządzać dedykowanymi urządzeniami z systemem iOS?**

> [!div class="button"]
[Program DEP dla systemu iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Asystent ustawień systemu iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Oznaczanie numerem IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Należące do firmy urządzenia z dedykowanymi użytkownikami można zarejestrować na następujące sposoby:

  - **Program Device Enrollment Program firmy Apple (DEP)** — urządzenia z systemem iOS zakupione lub zarządzane w programie DEP można skojarzyć z profilem rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, pobierają one profil DEP i są rejestrowane w usłudze Intune.

  - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj opcji rejestracji za pomocą Asystenta ustawień.

  - **Oznaczanie numerami IMEI** — importując międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) urządzeń należących do firmy, można oznaczyć je jako urządzenia należące do firmy w usłudze Intune. Następnie użytkownicy mogą zarejestrować swoje urządzenia jako urządzenia osobiste, instalując aplikację Portal firmy, aby uzyskać dostęp do zasobów firmowych, na przykład poczty e-mail, aplikacji i innych danych.



<!--HONumber=Nov16_HO4-->


