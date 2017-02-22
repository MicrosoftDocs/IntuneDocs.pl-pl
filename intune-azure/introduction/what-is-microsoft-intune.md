---
title: "Wprowadzenie do usługi Intune w wersji zapoznawczej portalu Azure | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: uzyskaj podstawowe informacje o usłudze Intune w wersji zapoznawczej portalu Azure i o sposobach, w jakie może ona ułatwić zarządzanie urządzeniami."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 01/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: f7f6dd79531d8d69eda3ed80bbb1cddf2692ab81


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Wprowadzenie do usługi Microsoft Intune w wersji zapoznawczej portalu Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Microsoft Intune jest przenoszona do portalu Azure, co oznacza, że używane przez Ciebie przepływy pracy i funkcje ulegną zmianie.
Nowy portal oferuje wersję zapoznawczą nowych i zaktualizowanych funkcji w portalu Azure Portal, w którym możesz zarządzać urządzeniami przenośnymi, komputerami i aplikacjami w swojej organizacji.
Ostatecznie wszystkie funkcje usługi Intune zostaną przeniesione na platformę Azure, ale już dziś można wykonać niektóre zadania usługi Intune w portalu Azure. Ponieważ nowe środowisko jest dostępne w wersji zapoznawczej, niektóre funkcje mogą jeszcze nie znajdować się w portalu. Szczegółowe informacje można znaleźć w sekcji [Co nowego w wersji zapoznawczej](#what's-new-in-the-preview).

> [!IMPORTANT]
> **Nie widzisz jeszcze nowego portalu?**<br>
> Firma Microsoft rozpoczęła już opracowywanie wersji zapoznawczej, aby wybrać dzierżawy. Migracja istniejących dzierżaw do nowego środowiska pracy rozpocznie się na początku roku kalendarzowego 2017. Przed migracją swojej dzierżawy otrzymasz powiadomienie w Centrum wiadomości biurowych. Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).


W tej bibliotece znajdziesz nową dokumentację produktu, która będzie stale aktualizowana podczas udostępniania wersji zapoznawczej. Jeśli masz sugestie dotyczące tego, co powinno się tu znaleźć, wystaw opinię w komentarzach do tematu. Chętnie poznamy Twoje zdanie.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Do najważniejszych elementów nowego środowiska należą:

- Zintegrowana konsola dla wszystkich składników Enterprise Mobility + Security (EMS)
- Konsola oparta na języku HTML, skonstruowana zgodnie ze standardami sieci Web
- Obsługa interfejsu API programu Microsoft Graph w celu zautomatyzowania wielu działań
- Grupy usługi Azure AD w celu zapewnienia zgodności wszystkich aplikacji Azure
- Obsługa większości nowoczesnych przeglądarek sieci Web

Jeśli szukasz dokumentacji klasycznej konsoli usługi Intune, zobacz [bibliotekę dokumentacji usługi Intune](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Przed rozpoczęciem

Aby skorzystać z usługi Intune w portalu Azure Portal, musisz mieć konto administratora i konto dzierżawy usługi Intune. W celu utworzenia konta można zarejestrować się [tutaj](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Obsługiwane przeglądarki internetowe w portalu Azure

Portal Azure działa na większości współczesnych komputerów osobistych, komputerów Mac i tabletów. Telefony komórkowe nie są obsługiwane.
Obecnie obsługiwane są następujące przeglądarki:

- Microsoft Edge (najnowsza wersja)
- Microsoft Internet Explorer 11
- Safari (najnowsza wersja, tylko Mac)
- Chrome (najnowsza wersja)
- Firefox (najnowsza wersja)

Najnowsze informacje o obsługiwanych przeglądarkach można uzyskać [tutaj](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Co znajduje się w tej bibliotece?

Dokumentacja odzwierciedla układ portalu usługi Intune, co ułatwia znalezienie potrzebnych informacji.

![Obciążenia portalu Azure](./media/azure-portal-workloads.png)

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>Rejestrowanie urządzeń
Jak zarządzać urządzeniami za pomocą usługi Intune.
[Przeczytaj więcej](/intune-azure/enroll-devices/what-is)
### <a name="devices--groups"></a>Urządzenia i grupy
Ustal, jakimi urządzeniami zarządzasz, za pomocą spisu i raportów.
[Przeczytaj więcej](/intune-azure/manage-devices/what-is)
### <a name="manage-users"></a>Zarządzanie użytkownikami
Uzyskaj informacje na temat użytkowników urządzeń, którymi zarządzasz.
[Przeczytaj więcej](/intune-azure/manage-users/what-is)
### <a name="manage-apps"></a>Zarządzanie aplikacjami
Zawiera informacje o sposobie publikowania, konfigurowania i ochrony aplikacji oraz zarządzania nimi.
[Przeczytaj więcej](/intune-azure/manage-apps/what-is-app-management)
### <a name="configure-devices"></a>Konfigurowanie urządzeń
Zawiera informacje o profilach, których można użyć do skonfigurowania ustawień i funkcji na urządzeniach, którymi zarządzasz.
[Przeczytaj więcej](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="set-device-compliance"></a>Ustaw zgodność urządzenia
Zdefiniuj poziom zgodności urządzeń, a następnie zgłoś wszystkie niezgodne urządzenia [Przeczytaj więcej](/intune-azure/set-device-compliance/what-is-device-compliance)
### <a name="conditional-access"></a>Dostęp warunkowy
Ogranicz dostęp do usług programu Exchange w zależności od określonych warunków.
[Przeczytaj więcej](/intune-azure/conditional-access/what-is-conditional-access)
### <a name="access-control"></a>Kontrola dostępu
Decyduj, kto może wykonywać różne akcje usługi Intune, i kogą mogą one dotyczyć. Możesz użyć wbudowanych ról, które obejmują kilka typowych scenariuszy usługi Intune, lub utworzyć własne.
[Przeczytaj więcej](/intune-azure/access-control/role-based-access-control)


## <a name="whats-new"></a>Co nowego?

[Dowiedz się, co nowego w wersji zapoznawczej](/intune-azure/introduction/whats-new).


<!--HONumber=Feb17_HO1-->


