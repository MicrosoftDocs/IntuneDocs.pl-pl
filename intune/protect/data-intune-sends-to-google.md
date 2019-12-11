---
title: Dane wysyłane przez usługę Intune do Google
titleSuffix: Microsoft Intune
description: Lista danych, które usługa Intune wysyła do firmy Google.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f6ab8a4e8e46373a536949c13ceaebb267f34cd
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504456"
---
# <a name="data-intune-sends-to-google"></a>Dane wysyłane przez usługę Intune do Google

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gdy zarządzanie urządzeniami przedsiębiorstwa z systemem Android jest włączone na urządzeniu, usługa Microsoft Intune nawiązuje połączenie z firmą Google i udostępnia informacje o użytkowniku i o urządzeniu firmie Google. Zanim usługa Microsoft Intune będzie mogła nawiązać połączenie, musisz utworzyć konto Google.

Poniższa tabela zawiera dane, które usługa Microsoft Intune wysyła do firmy Google, gdy zarządzanie urządzeniem jest włączone na urządzeniu:


| Dane wysyłane do firmy Google | Szczegóły | Sposób użycia | Przykład |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Tworzony przez firmę Google podczas wiązania konta Gmail z usługą Intune. | Podstawowy identyfikator służący do komunikacji między usługą Intune i firmą Google.  Ta komunikacja obejmuje ustawianie zasad, zarządzanie urządzeniami i wiązanie/usuwanie powiązania przedsiębiorstwa z systemem Android przy użyciu usługi Intune. | Unikatowy identyfikator, przykładowy format: LC04eik8a6 |
| Treść zasad | Tworzona w usłudze Intune podczas zapisywania nowej aplikacji lub zasad konfiguracji. | Stosowanie zasad do urządzeń. | To jest kolekcja wszystkich skonfigurowanych ustawień zasad aplikacji lub konfiguracji. Może zawierać informacje o kliencie, jeśli zostanie udostępniona jako część zasad, np. nazwy sieci, nazwy aplikacji oraz ustawienia specyficzne dla aplikacji. |
| Dane urządzenia | Urządzenia do scenariuszy profilu pracy rozpoczynają się od rejestracji w usłudze Intune. Urządzenia do scenariuszy zarządzanego urządzenia rozpoczynają się od rejestracji w firmie Google. | Informacje o danych urządzenia są przesyłane między usługą Intune i firmą Google na potrzeby różnych akcji, takich jak stosowanie zasad, zarządzanie urządzeniem i ogólne raportowanie. | **Unikatowy identyfikator reprezentujący nazwę urządzenia.** Przykład: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Unikatowy identyfikator reprezentujący nazwę użytkownika.** Przykład: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Stan urządzenia.** Przykłady: aktywne, wyłączone, aprowizowanie.<br>**Stany zgodności.** Przykłady: ustawienie nieobsługiwane, brak wymaganych aplikacji<br>**Informacje o oprogramowaniu.** Przykłady: wersje oprogramowania i poziom poprawki.<br>**Informacje o sieci.** Przykłady: IMEI, MEID, WifiMacAddress<br>**Ustawienia urządzenia.** Przykłady: informacje na temat poziomów szyfrowania i określenie, czy urządzenie dopuszcza nieznane aplikacje.<br> Poniżej zamieszczono przykładowy komunikat JSON. |
| newPassword | Pochodzi z usługi Intune. | Resetowanie kodu dostępu urządzenia. | Ciąg reprezentujący nowe hasło. |
| Użytkownik Google | Google | Zarządzanie profilem roboczym dla scenariuszy profilu pracy (BYOD). | Unikatowy identyfikator reprezentujący połączone konto Gmail. Przykład: 114223373813435875042 |
| Dane aplikacji | Tworzone w usłudze Intune podczas zapisywania zasad aplikacji. |  | Ciąg nazwy aplikacji. Przykład: app:com.microsoft.windowsintune.companyportal |
| Konto usługi Enterprise | Tworzone w firmie Google na żądanie usługi Intune. | Służy do uwierzytelniania między usługą Intune i firmą Google na potrzeby transakcji dotyczących tego klienta. | Istnieje kilka części:<br> **Identyfikator przedsiębiorstwa**: opisany wcześniej.<br>**Nazwa UPN**: wygenerowana nazwa UPN używana podczas uwierzytelniania w imieniu klienta.<br>Przykład: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Klucz**: zakodowany za pomocą kodowania Base64 obiekt blob używany w żądaniach uwierzytelniania, który jest przechowywany w usłudze w postaci zaszyfrowanej, ale wygląda jak poniżej:<br> Unikatowy identyfikator reprezentujący klucz klienta<br>Przykład: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |


Aby zaprzestać zarządzania urządzeniami przedsiębiorstwa z systemem Android za pomocą usługi Microsoft Intune i usunąć dane, musisz wyłączyć zarządzanie urządzeniem przedsiębiorstwa z systemem Android przez usługę Microsoft Intune i usunąć swoje konto Google. Zobacz informacje o koncie Google, aby dowiedzieć się, jak zarządzać kontem.


