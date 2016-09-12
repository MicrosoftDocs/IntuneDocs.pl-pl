---
title: "Ograniczanie dostępu do poczty e-mail i usług O365 | Microsoft Intune"
description: "W tym temacie opisano, jak dostęp warunkowy może służyć do umożliwienia dostępu do firmowej poczty e-mail i danych firmowych w usłudze SharePoint Online i innych usługach tylko ze zgodnych urządzeń."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 536d34e618efdc78b3103a3b1b36f13fb784781c


---

# Ograniczanie dostępu do poczty e-mail, usługi O365 i innych usług przy użyciu usługi Microsoft Intune
Możliwe jest ograniczenie dostępu do poczty e-mail i usług O365 firmy za pomocą dostępu warunkowego usługi Microsoft Intune. Możliwość dostępu warunkowego usługi Intune pozwala na zapewnienie, że dostęp do poczty e-mail i usług O365 w Twojej firmie jest ograniczony do urządzeń, które są zgodne z ustawionymi zasadami.
## W jaki sposób działa dostęp warunkowy?
Ustawienia zasad zgodności są używane do oceny zgodności urządzenia. Zasady dostępu warunkowego używają tej oceny do ograniczenia dostępu do określonej usługi lub zezwolenia na taki dostęp. Jeśli zasady dostępu warunkowego są stosowane w połączeniu z zasadami zgodności, to tylko zgodne urządzenia będą miały dostęp do usługi. Zasady zgodności i zasady dostępu warunkowego są wdrażane dla użytkownika. Wszystkie urządzenia, których użytkownik używa do uzyskiwania dostępu do usług, są sprawdzane pod kątem zgodności z zasadami.

Należy pamiętać, że użytkownik używający urządzenia musi mieć na nim wdrożone zasady zgodności, aby urządzenie mogło zostać ocenione pod kątem zgodności.
Jeśli na urządzeniu nie wdrożono żadnych zasad zgodności dla użytkownika, to urządzenie będzie traktowane jako zgodne i nie będą stosowane żadne ograniczenia dostępu.

Gdy urządzenia nie spełniają warunków ustawionych w zasadach, użytkownik końcowy jest przeprowadzany przez procedurę rejestracji urządzenia i rozwiązywania problemu, w związku z którym urządzenie nie może być zgodne.

Typowy przepływ dostępu warunkowego:

![Diagram przedstawiający punkty decyzyjne używane do określenia, czy urządzenie ma mieć dostęp do usługi, czy ma być blokowane](../media/ConditionalAccess4.png)

## Jak skonfigurować dostęp warunkowy?
Użyj warunkowego dostępu do zarządzania dostępem do następujących programów i usług firmy Microsoft: **lokalny program Exchange**, **usługa Exchange Online**, **usługa Exchange Online w wersji dedykowanej**, **usługa SharePoint Online** i **usługa Skype dla firm Online**.

Aby skonfigurować dostęp warunkowy, skonfiguruj zasady zgodności urządzeń i zasady dostępu warunkowego.

Zasady zgodności zawierają ustawienia, takie jak kod dostępu i szyfrowanie, oraz określają, czy urządzenie nie ma zdjętych zabezpieczeń. Urządzenie musi spełniać te reguły, aby można je było uważać za zgodne.

Możliwe jest ustawienie zasad dostępu warunkowego w celu ograniczenia dostępu w oparciu o:
- Stan zgodności urządzenia.
- Platformę, na której działa urządzenie.
- Typ aplikacji używanych do uzyskiwania dostępu do usług.

W odróżnieniu od innych zasad usługi Intune, zasady dostępu warunkowego nie są wdrażane przez Ciebie. Zamiast tego po skonfigurowaniu zasad i wybraniu użytkowników, którzy powinni je posiadać, zasady są stosowane do wszystkich użytkowników docelowych. Jeśli zasady obejmują użytkownika, każde używane przez niego urządzenie musi być zgodne, aby mógł uzyskać dostęp do zasobów.


## Następne kroki
1. [Dowiedz się więcej o zasadach zgodności urządzenia i sposobie ich działania ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Tworzenie zasad zgodności](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Utwórz zasady dostępu warunkowego dla jednego z następujących przypadków:
> [!div class="op_single_selector"]
  - [Tworzenie zasad dostępu warunkowego dla usługi Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla lokalnego programu Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla nowej usługi Exchange Online w wersji dedykowanej](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla starszej usługi Exchange Online w wersji dedykowanej](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla usługi SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla usługi Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla usługi Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->


