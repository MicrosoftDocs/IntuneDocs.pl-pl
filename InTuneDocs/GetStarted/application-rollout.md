---
title: "Wdrażanie aplikacji | Microsoft Intune"
description: "Zalecenia dotyczące etapowego wdrażania aplikacji w usłudze Microsoft Intune."
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2427768c0ca73d20140462946ba2984b7999d864
ms.openlocfilehash: d72247936a0dec8e2e00d107c0d52c1568a92c03


---

# Wdrażanie aplikacji
Ten temat zawiera zalecenia dotyczące etapowego wdrażania aplikacji w usłudze Microsoft Intune. Ogólne informacje o etapach wdrażania zamieszczono w temacie [Etapy wdrażania usługi Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Etapy wdrażania aplikacji
Etapy wdrażania aplikacji to:

-   Zakres projektu

-   Weryfikacja koncepcji

-   Pilotaż

-   Wdrożenie w przedsiębiorstwie

-   Działanie i obsługa

## Zakres projektu
Rozważ następujące opcje:

-   Zadanie wykonywane przez użytkowników, które powinna umożliwiać aplikacja.

-   Dostosowanie aplikacji do użytkowników i ich urządzeń (wszystkie systemy operacyjne, które będą prawdopodobnie używane).

-   Sprawdź, czy instalator wybranej aplikacji jest obsługiwany przez funkcję dystrybucji aplikacji w usłudze Intune, zgodnie z opisem w temacie [Dodawanie aplikacji za pomocą usługi Microsoft Intune](/intune/deploy-use/add-apps).

-   Upewnij się, że zainstalowano wymagane wstępnie składniki dla dystrybucji aplikacji. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Określ, czy typ aplikacji jest obsługiwany przez usługę Intune.

-   Sprawdź, czy dysponujesz miejscem do magazynowania w chmurze wystarczającym do przekazania aplikacji. Instrukcje dotyczące kupowania dodatkowego miejsca do magazynowania znajdują się w temacie [Dodawanie aplikacji za pomocą usługi Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> Możesz pobrać ten [szablon planowania dla aplikacji mobilnych](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59), który będzie pomocny w procesie wdrażania.

## Weryfikacja koncepcji
Na etapie weryfikacji koncepcji należy przetestować wdrażanie aplikacji w środowisku laboratoryjnym dla skonfigurowanych urządzeń i użytkowników wyłącznie w celach testowych.

-   W etapie tym powinien uczestniczyć dział pomocy technicznej, co umożliwi poznanie problemów, które mogą wystąpić podczas pilotażu i wdrożenia produkcyjnego. Informacje o rozwiązywaniu problemów są dostępne w temacie [Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   Na tym etapie procesu należy opracować plany informowania użytkowników wdrożenia pilotażowego i produkcyjnego. Plan powinien obejmować co najmniej nazwę wdrażanej aplikacji, sposób i termin uzyskania jej przez użytkowników, cel biznesowy wdrożenia, a także działania, które należy podjąć w przypadku napotkania problemów — zarówno informacje o samodzielnej pomocy, jak i sposobie kontaktu z pomocą techniczną.

## Pilotaż
Podczas etapu pilotażowego następuje wdrożenie aplikacji dla niewielkiej liczby użytkowników i urządzeń testowych. Rozważ następujące opcje:

-   Upewnij się, że grupa testowa jest reprezentatywna dla użytkowników i urządzeń, którzy będą korzystać z aplikacji po jej wdrożeniu produkcyjnym.

-   Poinformuj dział pomocy technicznej o wdrożeniu aplikacji i upewnij się, że jest on przygotowany do udzielania pomocy użytkownikom w grupie testowej.

-   Wybierz użytkowników testowych, którzy będą korzystać z aplikacji w typowy sposób i odpowiednio zgłaszać problemy administratorom etapu pilotażowego.

-   Aktywuj plan informowania użytkowników etapu pilotażowego.

## Wdrożenie w przedsiębiorstwie

-   Użyj wyników pilotażu do zmodyfikowania wdrożenia w przedsiębiorstwie.

-   Powiadom dział pomocy technicznej o harmonogramie wdrażania aplikacji. Przygotuj mechanizmy, które umożliwią reagowanie na prośby o pomoc oraz dostosowywanie wdrożenia w razie potrzeby.

-   Przygotuj się do rozwiązywania problemów z wdrożeniem w razie ich wystąpienia.

-   Aktywuj plan informowania użytkowników etapu produkcyjnego.

-   Zastosuj etapowe podejście do wdrażania aplikacji, dodając stopniowo grupy w celu zapewnienia bezproblemowego przebiegu wdrożenia.

## Działanie i obsługa
**Działanie:** Monitoruj konsolę usługi Intune pod kątem alertów oraz problemów dotyczących użytkowników i urządzeń, aby zapewnić przebieg dystrybucji aplikacji zgodnie z planem.

**Pomoc techniczna:** Upewnij się, że dział pomocy technicznej wie o wszelkich zmianach w dostępności aplikacji, które mogą skutkować prośbami o pomoc.

### Zobacz także
[Wdrażanie aplikacji](/intune/deploy-use/deploy-apps)

[Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Jul16_HO3-->


