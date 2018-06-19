---
title: Wprowadzenie do usługi Intune w witrynie Azure Portal
titlesuffix: ''
description: Usługa Microsoft Intune jest dostępna w witrynie Azure Portal. Uzyskaj podstawowe informacje na temat usługi Intune w witrynie Azure Portal.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: 4dee2c2204b90a35f0b03e2cd78a6662f67f680d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31032646"
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Wprowadzenie do usługi Microsoft Intune w witrynie Azure Portal


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podobnie jak inne usługi platformy Azure, usługa Microsoft Intune jest dostępna w witrynie Azure Portal. Wybierając usługę **Intune** w witrynie Azure Portal, możesz zarządzać urządzeniami przenośnymi, komputerami i aplikacjami organizacji.

> [!NOTE]
> Jeśli używano poprzedniej wersji usługi Microsoft Intune, przydatne mogą być następujące informacje:
>     * [Dokąd została przeniesiona funkcja usługi Intune na platformie Azure?](ui-changes.md) to artykuł, w którym można znaleźć opis określonych przepływów pracy i interfejsów użytkownika, które zmieniły się wraz z przejściem na platformę Azure.
>     * [Klasyczne grupy usługi Intune w witrynie Azure Portal](groups-get-started.md) to artykuł, w którym opisano wpływ przejścia do grup zabezpieczeń usługi Azure Active Directory na potrzeby zarządzania grupami.

Najważniejsze funkcje środowiska usługi Microsoft Intune w witrynie Azure Portal obejmują:

- Zintegrowana konsola dla wszystkich składników Enterprise Mobility + Security (EMS)
- Konsola oparta na języku HTML, skonstruowana zgodnie ze standardami sieci Web
- Obsługa interfejsu API programu Microsoft Graph w celu zautomatyzowania wielu działań
- Grupy usługi Azure Active Directory (AD) w celu zapewnienia zgodności wszystkich aplikacji Azure
- Obsługa większości nowoczesnych przeglądarek sieci Web

## <a name="before-you-start"></a>Przed rozpoczęciem

Aby skorzystać z usługi Intune w portalu Azure Portal, musisz mieć konto administratora i konto dzierżawy usługi Intune. [Utwórz konto](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), jeśli jeszcze go nie masz.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Obsługiwane przeglądarki internetowe w portalu Azure

Portal Azure działa na większości współczesnych komputerów osobistych, komputerów Mac i tabletów. Telefony komórkowe nie są obsługiwane.
Obecnie obsługiwane są następujące przeglądarki:

- Microsoft Edge (najnowsza wersja)
- Microsoft Internet Explorer 11
- Safari (najnowsza wersja, tylko Mac)
- Chrome (najnowsza wersja)
- Firefox (najnowsza wersja)

Sprawdź najnowsze informacje o obsługiwanych przeglądarkach w witrynie [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="microsoft-intune-in-the-azure-portal"></a>Usługa Microsoft Intune w witrynie Azure Portal

Usługę Microsoft Intune można znaleźć w witrynie [Azure Portal](https://portal.azure.com). Na platformie Azure jest dostępnych wiele usług, ale ze znacznej ich części prawdopodobnie nie będziesz regularnie korzystać. Aby uzyskać krótki przewodnik po dostosowywaniu środowiska portalu, zobacz [Wprowadzenie do usługi Intune w witrynie Azure Portal](get-started-azure.md).

## <a name="the-microsoft-intune-documentation"></a>Dokumentacja usługi Microsoft Intune

Ten temat, jak również cały zestaw dokumentacji usługi Microsoft Intune, są stale aktualizowane. Jeśli masz sugestie dotyczące tego, co powinno się tu znaleźć, dodaj swoją opinię w komentarzach do tematu. Chętnie poznamy Twoje zdanie.

Dokumentacja odzwierciedla układ usługi Microsoft Intune w witrynie Azure Portal (pokazany poniżej), aby ułatwić znajdowanie potrzebnych informacji.

![Obciążenia portalu Azure](./media/azure-portal-workloads.png)

### <a name="documentation-guide"></a>Przewodnik po dokumentacji

Skorzystaj z poniższej tabeli, aby szybko odnaleźć i zrozumieć główne obszary usługi Microsoft Intune.

| Sekcja                                                      | Opis                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Wprowadzenie i rozpoczynanie pracy](introduction-intune.md)       | Omówienie podstaw usługi Intune, w tym:<br /> — Typowe rozwiązania<br /> — Sposób, w jaki działa usługa Microsoft Intune<br /> — Zarządzanie urządzeniami w usłudze Intune<br /> — Zarządzanie aplikacjami w usłudze Intune<br /> — Zarządzania mobilnością w przedsiębiorstwie (Enterprise Mobility Management, EMM) z rejestracją lub bez rejestracji urządzeń                                                         |
| [Planowanie i projektowanie](planning-guide.md)                         | Wskazówki ułatwiające pomyślnie zaplanowanie i zaprojektowanie środowiska usługi Microsoft Intune.                                                                                                                                                                                                             |
| [Rejestrowanie urządzeń](device-enrollment.md)                    | Dowiedz się, jak usługa Microsoft Intune pomaga zarządzać urządzeniami pracowników, rejestrując urządzenia w usłudze Intune. Istnieje kilka metod rejestrowania urządzeń pracowników.                                                                                                         |
| [Zgodność urządzeń](device-compliance.md)                    | Zasady zgodności urządzeń usługi Intune służą do definiowania reguł i ustawień, z którymi urządzenie musi być zgodne, aby było uważane za spełniające zasady usługi Microsoft Intune. Przykładami zgodności są na przykład wymaganie hasła do uzyskiwania dostępu do urządzenia, szyfrowanie urządzeń i wymaganie minimalnej wersji systemu operacyjnego. |
| [Konfiguracja urządzeń](device-profiles.md)                   | Skonfiguruj ustawienia i funkcje na wszystkich urządzeniach zarządzanych za pomocą usługi Microsoft Intune przez utworzenie profilów urządzeń. Możesz na przykład skonfigurować takie funkcje jak powiadomienia, udostępnianie danych, obsługa poczty e-mail, łączność Wi-Fi, certyfikaty i program Endpoint Protection.              |
| [Urządzenia](device-management.md)                              | Upewnij się, że zarządzane urządzenia udostępniają zasoby, których użytkownicy końcowi potrzebują do wykonania swojej pracy, a jednocześnie chroń dane firmy przed ryzykiem. Zarządzaj urządzeniami, przeglądając spis urządzeń pracowników i wykonując akcje urządzeń zdalnych.                                                      |
| [Aplikacje mobilne](app-management.md)                             | Informacje o sposobie dodawania, wdrażania, monitorowania, konfigurowania i ochrony aplikacji.                                                                                                                                                                                                                             |
| [Dostęp warunkowy](conditional-access.md)                  | Definiowanie warunków opartych na urządzeniach i opartych na aplikacjach dla bramy dostępu do danych firmowych.                                                                                                                                                                                                            |
| [Użytkownicy](users-add.md)                                        | Dowiedz się, jak dodać użytkowników, urządzenia i aplikacje, którymi zarządzasz.                                                                                                                                                                                                                                           |
| [Grupy](groups-get-started.md)                              | Dowiedz się, jak możesz utworzyć grupy w usłudze Intune i zarządzać nimi. Przy użyciu grup możesz szybko przypisać zasady konfiguracji i ochrony aplikacji i urządzeń.                                                                                                                                             |
| [Role usługi Intune](role-based-access-control.md)                 | Informacje o sposobie kontrolowania tego, kto może wykonywać różne akcje usługi Intune i jak są stosowane te akcje. Możesz użyć wbudowanych ról, które obejmują kilka typowych scenariuszy usługi Intune, lub utworzyć własne.                                                                                 |
| [Aktualizacje oprogramowania](windows-update-for-business-configure.md) | Dowiedz się, jak konfigurować aktualizacje oprogramowania dla urządzeń z systemem Windows 10.                                                                                                                                                                                                                                  |

## <a name="whats-new"></a>Co nowego

Aby dowiedzieć się więcej o najnowszych funkcjach usługi Microsoft Intune, zobacz [Co nowego](whats-new.md).
