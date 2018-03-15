---
title: "Dane wysyłane przez usługę Intune do Google"
titlesuffix: Azure portal
description: "Lista danych, które usługa Intune wysyła do firmy Google."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5f8c71115b8c3ee761fbc8d303f87e8aaabd5e1
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2018
---
# <a name="data-intune-sends-to-google"></a>Dane wysyłane przez usługę Intune do Google

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gdy zarządzanie urządzeniami z systemem Android jest włączone na urządzeniu, usługa Microsoft Intune nawiązuje połączenie z firmą Google i udostępnia informacje o użytkowniku i o urządzeniu firmie Google. Zanim usługa Microsoft Intune będzie mogła nawiązać połączenie, musisz utworzyć konto Google.

Poniższa tabela zawiera dane, które usługa Microsoft Intune wysyła do firmy Google, gdy zarządzanie urządzeniem jest włączone na urządzeniu:


| Dane wysyłane do firmy Google | Szczegóły | Służy do | Przykład |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Tworzony przez firmę Google podczas wiązania konta Gmail z usługą Intune. | Podstawowy identyfikator służący do komunikacji między usługą Intune i firmą Google.  Ta komunikacja obejmuje ustawianie zasad, zarządzanie urządzeniami i wiązanie/usuwanie powiązania przedsiębiorstwa z systemem Android przy użyciu usługi Intune. | Unikatowy identyfikator, przykładowy format: LC04eik8a6 |
| Treść zasad | Tworzona w usłudze Intune podczas zapisywania nowej aplikacji lub zasad konfiguracji. | Stosowanie zasad do urządzeń. | To jest kolekcja wszystkich skonfigurowanych ustawień zasad aplikacji lub konfiguracji. Może zawierać informacje o kliencie, jeśli zostanie udostępniona jako część zasad, np. nazwy sieci, nazwy aplikacji oraz ustawienia specyficzne dla aplikacji. |
| Dane urządzenia | Urządzenia do scenariuszy profilu pracy rozpoczynają się od rejestracji w usłudze Intune. Urządzenia do scenariuszy zarządzanego urządzenia rozpoczynają się od rejestracji w firmie Google. | Informacje o danych urządzenia są przesyłane między usługą Intune i firmą Google na potrzeby różnych akcji, takich jak stosowanie zasad, zarządzanie urządzeniem i ogólne raportowanie. | **Unikatowy identyfikator reprezentujący nazwę urządzenia.** Przykład: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Unikatowy identyfikator reprezentujący nazwę użytkownika.** Przykład: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Stan urządzenia.** Przykłady: aktywne, wyłączone, aprowizowanie.<br>**Stany zgodności.** Przykłady: ustawienie nieobsługiwane, brak wymaganych aplikacji<br>**Informacje o oprogramowaniu.** Przykłady: wersje oprogramowania i poziom poprawki.<br>**Informacje o sieci.** Przykłady: IMEI, MEID, WifiMacAddress<br>**Ustawienia urządzenia.** Przykłady: informacje na temat poziomów szyfrowania i określenie, czy urządzenie dopuszcza nieznane aplikacje.<br> Poniżej zamieszczono przykładowy komunikat JSON. |
| newPassword | Pochodzi z usługi Intune. | Resetowanie kodu dostępu urządzenia. | Ciąg reprezentujący nowe hasło. |
| Użytkownik Google | Google | Zarządzanie profilem roboczym dla scenariuszy profilu pracy (BYOD). | Unikatowy identyfikator reprezentujący połączone konto Gmail. Przykład: 114223373813435875042 |
| Dane aplikacji | Tworzone w usłudze Intune podczas zapisywania zasad aplikacji. |  | Ciąg nazwy aplikacji. Przykład: app:com.microsoft.windowsintune.companyportal |
| Konto usługi Enterprise | Tworzone w firmie Google na żądanie usługi Intune. | Służy do uwierzytelniania między usługą Intune i firmą Google na potrzeby transakcji dotyczących tego klienta. | Istnieje kilka części:<br> **Identyfikator przedsiębiorstwa**: opisany wcześniej.<br>**Nazwa UPN**: wygenerowana nazwa UPN używana podczas uwierzytelniania w imieniu klienta.<br>Przykład: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Klucz**: zakodowany za pomocą kodowania Base64 obiekt blob używany w żądaniach uwierzytelniania, który jest przechowywany w usłudze w postaci zaszyfrowanej, ale wygląda jak poniżej:<br> Unikatowy identyfikator reprezentujący klucz klienta<br>Przykład: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Przykład danych urządzenia**

Oto przykładowy komunikat urządzenia JSON od firmy Google:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Aby zaprzestać zarządzania urządzeniami z systemem Android za pomocą usługi Microsoft Intune i usunąć dane, musisz zarówno wyłączyć zarządzanie urządzeniem z systemem Android przez usługę Microsoft Intune, jak również usunąć swoje konto Google. Zobacz informacje o koncie Google, aby dowiedzieć się, jak zarządzać kontem.


