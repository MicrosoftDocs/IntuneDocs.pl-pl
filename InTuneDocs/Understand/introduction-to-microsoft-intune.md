---
title: "Wprowadzenie do usługi Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4dc67dd71aa49b4227c30f094a2596ea3ab35492
ms.openlocfilehash: a9ae645034acbc4cf9d43c852fa0554e150f6bf0


---

# Wprowadzenie do usługi Intune
Usługa Microsoft Intune stanowi „ramię zarządzania” pakietu Microsoft Enterprise Mobility + Security (EMS, wcześniej Enterprise Mobility Suite). Podstawowym przeznaczeniem rozwiązań Enterprise Mobility jest zapewnienie pracownikom produktywności na wszystkich urządzeniach, z których korzystają, przy jednoczesnym zachowaniu bezpieczeństwa informacji należących do organizacji.  

Pakiet EMS to kompletny, zintegrowany pakiet rozwiązań Enterprise Mobility obejmujący rozwiązania do kontroli dostępu, zarządzania, potwierdzania tożsamości, zapewniania produktywności i ochrony danych. Udostępnia efektywny sposób wdrażania i obsługi rozwiązania zapewniającego mobilność.  

![Wizja mobilności w przedsiębiorstwach](..\media\em-vision.png)

Usługa Intune pomaga zarządzać urządzeniami przenośnymi i aplikacjami mobilnymi. Jest ściśle zintegrowana z usługą Azure Active Directory (Azure AD), co umożliwia kontrolowanie tożsamości i dostępu, a także z usługą Azure Rights Management (Azure RMS) na potrzeby ochrony danych.  

Typowe problemy biznesowe, które pomaga rozwiązywać usługa Intune:

* Ochrona lokalnej infrastruktury poczty e-mail i współpracy w sposób umożliwiający dostęp do nich z urządzeń przenośnych i aplikacji w Internecie.
* Ochrona infrastruktury usługi Office 365 w sposób umożliwiający bezpieczny dostęp do niej z urządzeń przenośnych i aplikacji w Internecie.
* Umożliwianie organizacji wydawania telefonów komórkowych pracownikom.
* Umożliwianie organizacji zapewniania urządzeń współużytkowanych o ograniczonej funkcjonalności pracownikom zadaniowym.
* Umożliwianie organizacji implementowania bezpiecznej strategii „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) czyli strategii korzystania z urządzeń osobistych.
* Umożliwianie organizacji obsługi pracowników uzyskujących dostęp do usługi Office 365 z urządzeń i aplikacji, które nie są przez nią kontrolowane, na przykład kiosków na targach.

Podstawowe narzędzia, które oferuje usługa Intune:
* **Zarządzanie urządzeniami przenośnymi (MDM, mobile device management)**: możliwość rejestrowania urządzeń w usłudze Intune w sposób umożliwiający aprowizowanie, konfigurowanie i monitorowanie tych urządzeń oraz wykonywanie na nich akcji, takich jak czyszczenie danych.
* **Zarządzanie aplikacjami mobilnymi (MAM, mobile application management)**: możliwość publikowania, wypychania, konfigurowania, zabezpieczania, monitorowania i aktualizacji aplikacji mobilnych dla użytkowników.
* **Zabezpieczanie aplikacji mobilnych**: w ramach zarządzania aplikacjami mobilnymi usługa ułatwia zabezpieczanie danych mobilnych poprzez izolowanie danych osobistych od danych firmowych, dzięki czemu możliwe jest selektywne czyszczenie danych firmowych.

Te narzędzia są używane w różnych kombinacjach, dzięki którym możliwe jest realizowanie powyższych typowych scenariuszy biznesowych. Na przykład w przypadku scenariuszy z urządzeniami współużytkowanymi w znacznym stopniu wykorzystywane jest zarządzanie urządzeniami przenośnymi. Scenariusze BYOD są zwykle oparte na zarządzaniu aplikacjami mobilnymi. Natomiast scenariusze z telefonami firmowymi są oparte na obu tych strategiach zarządzania. Prawie wszystkie scenariusze korzystają z zabezpieczeń aplikacji mobilnych.

W niniejszej dokumentacji wyjaśniamy sposób korzystania z narzędzi udostępnianych przez usługę Intune w celu obsługi różnych scenariuszy biznesowych.  Prezentujemy również zasady używania tych narzędzi z usługami Office 365, Azure AD, Azure RMS i innymi częściami pakietu Mobility Suite firmy Microsoft. W ten sposób przedstawimy szerszy obraz popularnych zastosowań tych rozwiązań, ich potencjalne zastosowania w Twoim środowisku i procedury ich wdrażania. Opisywane rozwiązania są elastyczne i mogą być dostosowywane do szerokiej gamy scenariuszy wykraczających poza przedstawione przykłady.

### Następne kroki
* Przeczytaj o pewnych [typowych sposobach korzystania z usługi Intune](common-ways-to-use-intune.md).
* Zapoznaj się z produktem, korzystając [z 30-dniowej wersji próbnej usługi Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md).
* Poznaj [wymagania techniczne i możliwości](/intune/get-started/what-to-know-before-you-start-microsoft-intune) usługi Intune.



<!--HONumber=Jul16_HO3-->


