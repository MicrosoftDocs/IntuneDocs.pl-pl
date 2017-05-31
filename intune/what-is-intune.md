---
title: "Wprowadzenie do usługi Intune w wersji zapoznawczej witryny Azure Portal"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: uzyskaj podstawowe informacje o usłudze Intune w wersji zapoznawczej portalu Azure i o sposobach, w jakie może ona ułatwić zarządzanie urządzeniami."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d7ff50eb821e0927c3c6ea21f3cdb1257762a0
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Wprowadzenie do usługi Microsoft Intune w wersji zapoznawczej portalu Azure


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Usługa Microsoft Intune jest przenoszona do portalu Azure, co oznacza, że używane przez Ciebie przepływy pracy i funkcje ulegną zmianie.
Nowy portal oferuje wersję zapoznawczą nowych i zaktualizowanych funkcji w witrynie Azure Portal, w której możesz zarządzać urządzeniami przenośnymi, komputerami i aplikacjami w swojej organizacji.
Ostatecznie na platformę Azure zostaną przeniesione wszystkie funkcje usługi Intune, ale już dziś w portalu Azure można wykonać wiele zadań usługi Intune. Ponieważ nowe środowisko jest dostępne w wersji zapoznawczej, niektóre funkcje mogą jeszcze nie znajdować się w portalu. Szczegółowe informacje można znaleźć w sekcji [Co nowego](#whats-new).

> [!IMPORTANT]
> **Nie widzisz jeszcze nowego portalu?**<br>
> Firma Microsoft rozpoczęła już opracowywanie wersji zapoznawczej, aby wybrać dzierżawy. Migracja istniejących dzierżaw do nowego środowiska pracy rozpocznie się na początku roku kalendarzowego 2017. Przed migracją swojej dzierżawy otrzymasz powiadomienie w Centrum wiadomości biurowych.
>
> Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim przepływy pracy procesu Rejestracja Apple będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.


W tej bibliotece znajdziesz nową dokumentację produktu, która będzie stale aktualizowana podczas udostępniania wersji zapoznawczej. Jeśli masz sugestie dotyczące tego, co powinno się tu znaleźć, wystaw opinię w komentarzach do tematu. Chętnie poznamy Twoje zdanie.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

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
Ta sekcja zawiera informacje o [nowościach](whats-new.md), [znanych problemach](known-issues.md), [sposobach uzyskiwania pomocy technicznej](get-support.md) oraz [rozpoczynaniu pracy z bezpłatną wersją próbną](free-trial-sign-up.md) usługi Intune.
### <a name="plan-and-design"></a>Planowanie i projektowanie
Informacje ułatwiające [planowanie i projektowanie](/intune-classic/plan-and-design/introduction) środowiska usługi Intune.
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
[Więcej informacji na temat użytkowników z zarządzanymi urządzeniami i sortowaniu zasobów według grup](user-management.md).
### <a name="groups"></a>Grupy
[Dowiedz się, jak używać grup usługi Azure Active Directory w usłudze Intune](groups-get-started.md)
### <a name="intune-roles"></a>Role usługi Intune
[Decyduj, kto może wykonywać różne akcje usługi Intune i kogo mogą one dotyczyć](role-based-access-control.md). Możesz użyć wbudowanych ról, które obejmują kilka typowych scenariuszy usługi Intune, lub utworzyć własne.
### <a name="software-updates"></a>Aktualizacje oprogramowania
[Dowiedz się, jak konfigurować aktualizacje oprogramowania dla urządzeń z systemem Windows 10](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Co nowego

[Dowiedz się, co nowego w wersji zapoznawczej](whats-new.md).

