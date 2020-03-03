---
title: Konfigurowanie usługi Microsoft Intune
description: Wymogi i wymagania wstępne dotyczące korzystania z subskrypcji usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/20/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b12781c55abc3ce7d9e964b0f139fc4c1d1fd69b
ms.sourcegitcommit: 67f926ba83f8a955e16b741a610ad84d6044f8f9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/21/2020
ms.locfileid: "77529366"
---
# <a name="set-up-intune"></a>Konfigurowanie usługi Intune

Te kroki konfiguracji ułatwiają włączenie zarządzania urządzeniami przenośnymi (MDM, mobile device management) w usłudze Intune. Urządzenia muszą być zarządzane, aby można było zapewnić użytkownikom dostęp do zasobów firmy lub zarządzać ustawieniami tych urządzeń.

Niektóre kroki, takie jak skonfigurowanie subskrypcji usługi Intune i ustawienie urzędu MDM, są wymagane w większości scenariuszy. Inne kroki, np. skonfigurowanie domeny niestandardowej lub dodanie aplikacji, są opcjonalne i zależą od potrzeb firmy.

Jeśli obecnie używasz programu Microsoft Endpoint Configuration Manager do zarządzania komputerami i serwerami, możesz [za pomocą współzarządzania podpiąć program Configuration Manager pod chmurę](https://docs.microsoft.com/configmgr/comanage/overview).

>[!TIP]
>W przypadku zakupu co najmniej 150 licencji na usługę Intune w uprawniającym planie można skorzystać z usługi *Asysta centrum rozwiązania FastTrack*. Ta usługa zapewnia pomoc specjalistów firmy Microsoft przy przygotowaniu środowiska usługi Intune. Zobacz [Asysta centrum rozwiązania FastTrack dla pakietu Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).

| Kroki | Stan  |
|---|---|
|   1   | [Obsługiwane konfiguracje](supported-devices-browsers.md) — informacje, które należy znać przed rozpoczęciem. Obejmuje to obsługiwane konfiguracje i wymagania sieciowe.|
|   2   |  [Logowanie do usługi Intune](account-sign-up.md) — zaloguj się do subskrypcji wersji próbnej lub utwórz nową subskrypcję usługi Intune. |
|   3   | [Konfigurowanie nazwy domeny](custom-domain-name-configure.md) — skonfiguruj rejestrację systemu DNS, aby połączyć nazwę domeny firmy z usługą Intune. Dzięki temu użytkownicy będą mogli używać znanej domeny podczas łączenia się z usługą Intune i korzystania z zasobów. |
|   4   | [Dodawanie użytkowników](users-add.md) i [grup](../groups-add.md) — dodaj użytkowników i grupy lub połącz się z usługą Active Directory, aby zsynchronizować się z usługą Intune. Jest to wymagane, chyba że urządzenia to kioski bez użytkowników. Grupy służą do przypisywania aplikacji, ustawień i innych zasobów.|
|   5   | [Przypisywanie licencji](../licenses-assign.md) — nadaj użytkownikom uprawnienia do korzystania z usługi Intune. Każdy użytkownik i każde urządzenie bez użytkownika wymaga licencji usługi Intune na potrzeby dostępu do usługi. |
|   6   | [Ustawianie urzędu zarządzania urządzeniami mobilnymi](../mdm-authority-set.md) — uprość zadania związane z zarządzaniem dzięki grupom użytkowników i urządzeń. Grupy służą do przypisywania aplikacji, ustawień i innych zasobów. |
|   7   | [Dodawanie aplikacji](../apps/apps-add.md) — aplikacje możesz przypisywać do grup oraz instalować automatycznie lub opcjonalnie. |
|   8   | [Konfigurowanie urządzeń](../configuration/device-profiles.md) — skonfiguruj profile na potrzeby zarządzania ustawieniami urządzeń. Za pomocą profili urządzeń możesz wstępnie konfigurować ustawienia poczty e-mail, sieci VPN, sieci Wi-Fi i funkcji urządzeń. Dzięki nim możesz również ograniczyć urządzenia, aby pomóc w ochronie danych i urządzeń. |
|   9   |  [Dostosowywanie portalu firmy](../apps/company-portal-app.md) — dostosuj portal firmy usługi Intune, za pomocą którego użytkownicy rejestrują urządzenia i instalują aplikacje. Te ustawienia są wyświetlane zarówno w aplikacji Portal firmy, jak i w witrynie internetowej Portal firmy usługi Intune.       |
|  10   | [Włączanie rejestrowania urządzeń](mdm-authority-set.md) — włącz zarządzanie urządzeniami z systemem iOS/iPadOS, Windows, Android i Mac przy użyciu usługi Intune, ustawiając urząd MDM i włączając określone platformy. |
|  11   |  [Konfigurowanie zasad aplikacji](../apps/app-protection-policy.md) — określ konkretne ustawienia na podstawie zasad ochrony aplikacji w usłudze Microsoft Intune. |
