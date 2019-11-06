---
title: Przegląd cyklu życia aplikacji dla usługi Microsoft Intune
description: Dowiedz się więcej na temat cyklu życia aplikacji zarządzanych w usłudze Microsoft Intune. Cykl życia aplikacji obejmuje dodawanie, wdrażanie, konfigurowanie, ochronę i wycofywanie aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: apps; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: ef958468feb7e36f894537989675977e1d96bf8c
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414734"
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Przegląd cyklu życia aplikacji w usłudze Microsoft Intune

Cykl życia aplikacji w usłudze Microsoft Intune rozpoczyna się po dodaniu aplikacji i jest realizowany przez dodatkowe fazy aż do usunięcia aplikacji. Zrozumienie tych faz pozwala uzyskać szczegółowe informacje konieczne do rozpoczęcia zarządzania aplikacjami w usłudze Intune.

![Cykl życia aplikacji — dodawanie, wdrażanie, konfigurowanie, ochrona i wycofywanie.](./media/app-lifecycle/app-lifecycle.png "cykl życia aplikacji usługi Intune")

## <a name="add"></a>Dodaj

Pierwszym etapem wdrożenia aplikacji jest dodanie aplikacji, którą chcesz zarządzać i przypisać, do usługi Intune. Istnieje wiele różnych typów aplikacji, z którymi można pracować, ale podstawowe procedury dla wszystkich są takie same. Za pomocą usługi Intune możesz dodawać różne typy aplikacji, w tym aplikacje napisane w firmie (biznesowe), aplikacje ze sklepu, aplikacje wbudowane i aplikacje w Internecie. Aby uzyskać więcej informacji na temat tych typów aplikacji, zobacz [Jak dodawać aplikacje do usługi Microsoft Intune](apps-add.md).

## <a name="deploy"></a>Wdróż program

Po dodaniu aplikacji do usługi Intune możesz tę aplikację [przypisać do użytkowników oraz do urządzeń, którymi zarządzasz](apps-deploy.md). Usługa Intune ułatwia ten proces, a po wdrożeniu aplikacji możesz [monitorować sukces](apps-monitor.md) wdrożenia z poziomu usługi Intune w witrynie Azure Portal. Ponadto niektóre sklepy z aplikacjami, takie jak [Apple](vpp-apps-ios.md) i [Windows](windows-store-for-business.md), pozwalają na zakup zbiorczych licencji na aplikacje dla firm. Usługa Intune może synchronizować dane z tymi sklepami, aby umożliwić wdrażanie licencji i śledzenie ich użycia dla tych typów aplikacji bezpośrednio z Konsoli administracyjnej usługi Intune.

## <a name="configure"></a>Konfiguracja

W ramach cyklu życia aplikacji regularnie wydawane są nowe wersje aplikacji. Usługa Intune udostępnia narzędzia do łatwego [aktualizowania wdrożonych aplikacji](apps-add.md) do nowszej wersji. Ponadto dla niektórych aplikacji można skonfigurować dodatkowe funkcje, na przykład:

- [Zasady konfiguracji aplikacji systemu iOS](app-configuration-policies-use-ios.md) pozwalają określać ustawienia dla zgodnych aplikacji systemu iOS, które będą używane po uruchomieniu aplikacji. Na przykład aplikacja może wymagać określonych ustawień oznaczania marką lub nazwy serwera, z którym musi nawiązać połączenie.
- [Zasady przeglądarki zarządzanej](app-configuration-managed-browser.md) pomagają w konfigurowaniu ustawień dla przeglądarki zarządzanej przez usługę Intune, która zastępuje domyślną przeglądarkę urządzenia i umożliwia ograniczenie witryn sieci Web, które użytkownicy mogą odwiedzać.

## <a name="protect"></a>Ochrona

Usługa Intune zapewnia wiele sposobów ochrony danych w aplikacjach. Główne sposoby są następujące:

- [Dostęp warunkowy](../protect/conditional-access.md) pozwalający na kontrolowanie dostępu do poczty e-mail i innych usług w oparciu o określone kryteria, takie jak typy urządzeń albo spełnienie wdrożonych [zasad zgodności urządzeń](../protect/device-compliance-get-started.md).
- [Zasady ochrony aplikacji](app-protection-policy.md) współpracujące z poszczególnymi aplikacjami, aby chronić dane firmowe, z których te aplikacje korzystają. Na przykład można ograniczyć kopiowanie danych między aplikacjami niezarządzanymi i zarządzanymi albo zapobiec uruchamianiu aplikacji na urządzeniach ze zdjętymi zabezpieczeniami lub z odblokowanym kontem root.

## <a name="retire"></a>Wycofaj

W dłuższej perspektywie czasu prawdopodobne jest, że wdrożone aplikacje staną się nieaktualne i konieczne będzie ich usunięcie. Usługa Intune ułatwia [wycofywanie aplikacji](../remote-actions/device-management.md).

## <a name="next-steps"></a>Następne kroki

- Dowiedz się więcej na temat [zarządzania aplikacjami w usłudze Microsoft Intune](app-management.md)
