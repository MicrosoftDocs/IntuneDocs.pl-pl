---
title: "Wprowadzenie do usługi Intune w witrynie Azure Portal"
titleSuffix: Intune on Azure
description: "Uzyskaj podstawowe informacje o usłudze Intune w witrynie Azure Portal oraz o sposobach, w jakie może ona ułatwić zarządzanie urządzeniami."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae42ab64945982fedc2d6858e2f3eca8fbed334c
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Wprowadzenie do usługi Microsoft Intune w witrynie Azure Portal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Microsoft Intune jest obecnie dostępna w witrynie Azure Portal, co oznacza, że przepływy pracy i funkcje, które były dotychczas używane, zmieniły się.
Azure Portal oferuje nowe i zaktualizowane funkcje. W witrynie tej można zarządzać urządzeniami mobilnymi, komputerami i aplikacjami w organizacji.

> [!IMPORTANT]
> **Nie widzisz jeszcze nowego portalu?**<br>
> Istniejący dzierżawcy są aktualnie migrowani do nowego środowiska. Przed migracją dzierżawcy zostaje wyświetlone powiadomienie w Office Message Center.
>
> Konta usługi Intune utworzone przed styczniem 2017 r. będą wymagać przeprowadzenia jednorazowej migracji, zanim przepływy pracy procesu Rejestracja Apple będą dostępne na platformie Azure. Harmonogram migracji nie został jeszcze ogłoszony. Jeśli istniejące konto nie ma dostępu do witryny Azure Portal, zaleca się utworzenie konta w wersji próbnej.
>
> Sprawdź listę potencjalnych elementów blokujących https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/


Informacje dotyczące nowego portalu można znaleźć w tej bibliotece i są one na bieżąco aktualizowane. Jeśli masz sugestie dotyczące tego, co powinno się tu znaleźć, dodaj swoją opinię w komentarzach do tematu. Chętnie poznamy Twoje zdanie.

Do najważniejszych elementów nowego środowiska należą:

- Zintegrowana konsola dla wszystkich składników Enterprise Mobility + Security (EMS)
- Konsola oparta na języku HTML, skonstruowana zgodnie ze standardami sieci Web
- Obsługa interfejsu API programu Microsoft Graph w celu zautomatyzowania wielu działań
- Grupy usługi Azure Active Directory (AD) w celu zapewnienia zgodności wszystkich aplikacji Azure
- Obsługa większości nowoczesnych przeglądarek sieci Web

Jeśli szukasz dokumentacji klasycznej konsoli usługi Intune, zobacz [bibliotekę dokumentacji usługi Intune](https://docs.microsoft.com/intune-classic/).

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

## <a name="whats-in-this-library"></a>Co znajduje się w tej bibliotece?

Dokumentacja odzwierciedla układ portalu usługi Intune, co ułatwia znalezienie potrzebnych informacji.

![Obciążenia portalu Azure](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Wprowadzenie i rozpoczynanie pracy
Ta sekcja zawiera [informacje wprowadzające](introduction-intune.md), które ułatwiają rozpoczęcie korzystania z usługi Intune.
### <a name="plan-and-design"></a>Planowanie i projektowanie
Informacje ułatwiające [planowanie i projektowanie](/intune-classic/plan-design/introduction) środowiska usługi Intune.
### <a name="device-enrollment"></a>Rejestrowanie urządzeń
[Jak zarządzać urządzeniami za pomocą usługi Intune](device-enrollment.md).
### <a name="device-compliance"></a>Zgodność urządzeń
[Zdefiniuj poziom zgodności urządzeń, a następnie zgłoś wszystkie niezgodne urządzenia](device-compliance.md).
### <a name="device-configuration"></a>Konfiguracja urządzenia
[Poznaj profile, których można użyć do skonfigurowania ustawień i funkcji na urządzeniach, którymi zarządzasz](device-profiles.md).
### <a name="devices"></a>Urządzenia
[Za pomocą spisu i raportów ustal, jakimi urządzeniami zarządzasz](device-management.md).
### <a name="mobile-apps"></a>Aplikacje mobilne
[Jak publikować, konfigurować i ochronić aplikacje oraz zarządzać nimi](app-management.md).
### <a name="conditional-access"></a>Dostęp warunkowy
[Ogranicz dostęp do usług programu Exchange w zależności od określonych warunków](conditional-access.md).
### <a name="on-premises-access"></a>Dostęp lokalny
[Konfigurowanie dostępu do programu Exchange ActiveSync i lokalnego programu Exchange](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Więcej informacji na temat użytkowników z zarządzanymi urządzeniami i sortowaniu zasobów według grup](users-add.md).
### <a name="groups"></a>Grupy
[Dowiedz się, jak używać grup usługi Azure Active Directory w usłudze Intune](groups-get-started.md)
### <a name="intune-roles"></a>Role usługi Intune
[Decyduj, kto może wykonywać różne akcje usługi Intune i kogo mogą one dotyczyć](role-based-access-control.md). Możesz użyć wbudowanych ról, które obejmują kilka typowych scenariuszy usługi Intune, lub utworzyć własne.
### <a name="software-updates"></a>Aktualizacje oprogramowania
[Dowiedz się, jak konfigurować aktualizacje oprogramowania dla urządzeń z systemem Windows 10](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Co nowego

[Dowiedz się, co nowego w usłudze Intune](whats-new.md).
