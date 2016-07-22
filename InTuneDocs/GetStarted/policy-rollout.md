---
# required metadata

title: Wdrażanie zasad | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wdrażanie zasad
Ten temat zawiera zalecenia dotyczące etapowego wdrażania zasad w usłudze Microsoft Intune. Takie podejście stosuje się do pierwszych zasad stosowanych w nowym wdrożeniu usługi Intune, a także do zasad dodawanych do istniejącego wdrożenia.

Ogólne informacje o etapach wdrażania zamieszczono w temacie [Etapy wdrażania usługi Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md)..

### Etapy wdrażania zasad
Etapy wdrażania zasad są następujące:

-   Zakres projektu

-   Weryfikacja koncepcji

-   Pilotaż

-   Wdrożenie w przedsiębiorstwie

-   Działanie i obsługa

## Zakres projektu
Zdefiniuj zakres wdrożenia zasad usługi Intune:

-   W przypadku nowego wdrożenia będzie to wymagało zdefiniowania wszystkich zachowań urządzeń i wymagań dotyczących zabezpieczeń, które chcesz utworzyć przy użyciu zestawu zasad.

-   Określ urządzenia i użytkowników, na których te zasady będą miały wpływ.

-   Zaprojektuj grupy użytkowników i urządzeń, aby zapewnić sobie możliwość odpowiedniego stosowania nowych zasad.

-   Ustal, czy będą istnieć ograniczenia lub wymagania związane z poszczególnymi systemami operacyjnymi, które będą wpływać na cele zasad.

-   Uwzględnij charakterystykę projektowania zasad, na przykład typ zasad i szablon do użycia.

-   Bez względu na to, czy uruchamiasz swój pierwszy zestaw zasad, czy dodajesz nowe zasady do istniejącego zestawu zasad, weź pod uwagę interakcje różnych zasad i prawdopodobne zachowania urządzeń. Problemy i konflikty dotyczące interakcji zasad można wykryć w fazie pilotażu, ale wyeliminowanie konfliktów na wczesnym etapie planowania ułatwia wykonywanie pilotażu.

## Weryfikacja koncepcji
Na etapie weryfikacji koncepcji należy przetestować wdrażanie zasad w środowisku laboratoryjnym dla skonfigurowanych urządzeń i użytkowników wyłącznie w celach testowych.

-   W etapie tym powinien uczestniczyć dział pomocy technicznej, co umożliwi poznanie problemów, które mogą wystąpić podczas pilotażu i wdrożenia produkcyjnego. Informacje o rozwiązywaniu problemów są dostępne w temacie [Rozwiązywanie problemów z zasadami w usłudze Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)..

-   Na tym etapie procesu należy opracować plany informowania użytkowników wdrożenia pilotażowego i produkcyjnego. Plan powinien obejmować co najmniej zachowania urządzenia, które ulegną zmianom, oraz okoliczności tych zmian, ich cele biznesowe, a także działania, jakie należy podjąć w przypadku napotkania problemów — zarówno informacje o samodzielnej pomocy, jak i sposobie kontaktu z pomocą techniczną.

## Pilotaż
Podczas etapu pilotażowego następuje wdrożenie zasad dla niewielkiej liczby użytkowników i urządzeń testowych. W przypadku pilotażu zasad w usłudze Intune istnieje kilka zagadnień, które należy uwzględnić:

-   Grupa testowa powinna być reprezentatywna dla grupy, do której zostaną zastosowane zasady podczas wdrożenia w środowisku produkcyjnym.

-   Poinformuj dział pomocy technicznej o zmianie zasad i upewnij się, że jest on przygotowany do udzielania pomocy użytkownikom w grupie testowej.

-   Aktywuj plan informowania użytkowników etapu pilotażowego.

-   Na początku pilotaż może być realizowany w trybie izolowanym, w którym urządzenie nie podlega innym zasadom, co mogłoby powodować konflikty i niezamierzone zachowanie.

-   Ostateczny test musi uwzględniać nowe zasady i wszystkie istniejące zasady, które będą stosowane względem tego samego urządzenia.

## Wdrożenie w przedsiębiorstwie

-   Na podstawie wyników pilotażu dostosuj planowane zasady, aby wyeliminować konflikty zasad i nieprzewidziane zachowanie.

-   Powiadom dział pomocy technicznej o harmonogramie wdrażania w przedsiębiorstwie. Przygotuj mechanizmy, które umożliwią reagowanie na prośby o pomoc oraz dostosowywanie wdrożenia w razie potrzeby.

-   Przygotuj się do rozwiązywania problemów z zasadami w razie ich wystąpienia.

-   Aktywuj plan informowania użytkowników etapu produkcyjnego.

-   Stosuj zasady stopniowo względem kolejnych grup, monitorując stan zasad dla urządzeń, których dotyczą, i śledząc żądania pomocy technicznej, które mogą być powiązane z nowymi zasadami.

## Działanie i obsługa
**Działanie:** monitoruj konsolę usługi Intune pod kątem alertów oraz problemów dotyczących użytkowników i urządzeń, a ponadto sprawdzaj, czy zasady działają zgodnie z projektem.

**Pomoc techniczna:** zadbaj o to, aby powiadomić dział pomocy technicznej o wszelkich zmianach zasad, które wpłyną na środowisko użytkowników, ponieważ mogą one wywołać żądania pomocy technicznej.


### Zobacz także
[Przygotowywanie się do skonfigurowania zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Rozwiązywanie problemów dotyczących zasad w usłudze Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)


<!--HONumber=May16_HO1-->


