---
title: "Przegląd cyklu życia aplikacji na potrzeby usługi Intune"
description: "Dowiedz się więcej na temat cyklu życia aplikacji zarządzanych przez usługę Intune — od momentu ich dodania do ich ewentualnego wycofania."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e50e3af525be48bf058dd32bfb7b93508d500a3
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Przegląd cyklu życia aplikacji

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Cykl życia aplikacji w usłudze Intune rozpoczyna się po dodaniu aplikacji i jest realizowany przez dodatkowe fazy aż do usunięcia aplikacji.

![Cykl życia aplikacji](./media/app-lifecycle.png "Cykl życia aplikacji Intune")

## <a name="add"></a>Dodaj

Pierwszym etapem wdrożenia aplikacji jest dodanie aplikacji, którą chcesz zarządzać i przypisać, do usługi Intune. Istnieje wiele różnych typów aplikacji, z którymi można pracować, ale podstawowe procedury dla wszystkich są takie same. Usługa Intune umożliwia dodawanie aplikacji zarówno dla [zarejestrowanych urządzeń](apps-add.md) ([portal klasyczny](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)), jak i dla [komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Wdróż

Po dodaniu aplikacji do usługi Intune możesz tę aplikację [przypisać do użytkowników oraz do urządzeń, którymi zarządzasz](apps-deploy.md) ([portal klasyczny](/intune-classic/deploy-use/deploy-apps)). Usługa Intune ułatwia ten proces, a po wdrożeniu aplikacji możesz [monitorować powodzenie](apps-monitor.md) ([portal klasyczny](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)) wdrożenia z konsoli administracyjnej usługi Intune. Ponadto niektóre sklepy z aplikacjami, takie jak [Apple](vpp-apps-ios.md) ([portal klasyczny](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) i [Windows](windows-store-for-business.md) ([portal klasyczny](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), umożliwiają zakup zbiorczych licencji na aplikacje dla firm. Usługa Intune może synchronizować dane z tymi sklepami, aby umożliwić wdrażanie licencji i śledzenie ich użycia dla tych typów aplikacji bezpośrednio z Konsoli administracyjnej usługi Intune.

## <a name="configure"></a>Konfiguracja

W ramach cyklu życia aplikacji regularnie wydawane są nowe wersje aplikacji. Usługa Intune udostępnia narzędzia do łatwego [aktualizowania wdrożonych aplikacji](apps-add.md) ([portal klasyczny](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) do nowszej wersji. Ponadto dla niektórych aplikacji można skonfigurować dodatkowe funkcje, na przykład:
- [Zasady konfiguracji aplikacji systemu iOS](app-configuration-policies-use-ios.md) ([portal klasyczny](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) pozwalają określać ustawienia dla zgodnych aplikacji systemu iOS, które będą używane po uruchomieniu aplikacji. Na przykład aplikacja może wymagać określonych ustawień oznaczania marką lub nazwy serwera, z którym ma nawiązać połączenie.
- [Zasady przeglądarki zarządzanej](app-configuration-managed-browser.md) ([portal klasyczny](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) pomagają w konfigurowaniu ustawień dla przeglądarki zarządzanej przez usługę Intune, która zastępuje domyślną przeglądarkę urządzenia i umożliwia ograniczenie witryn sieci Web, które użytkownicy mogą odwiedzać.

## <a name="protect"></a>Ochrona

Usługa Intune zapewnia wiele sposobów ochrony danych w aplikacjach. Główne sposoby są następujące:
- [Dostęp warunkowy](conditional-access.md) ([portal klasyczny](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) pozwala na kontrolowanie dostępu do poczty e-mail i innych usług w oparciu o określone kryteria, takie jak typy urządzeń albo spełnienie wdrożonych [zasad zgodności urządzeń](device-compliance.md) ([portal klasyczny](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)).
- [Zasady ochrony aplikacji](app-protection-policy.md) ([portal klasyczny](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) współpracują z poszczególnymi aplikacjami, aby chronić dane firmowe, z których te aplikacje korzystają. Na przykład można ograniczyć kopiowanie danych między aplikacjami niezarządzanymi i zarządzanymi albo zapobiec uruchamianiu aplikacji na urządzeniach ze zdjętymi zabezpieczeniami lub z odblokowanym kontem root.

## <a name="retire"></a>Wycofaj

W dłuższej perspektywie czasu prawdopodobne jest, że wdrożone aplikacje staną się nieaktualne i konieczne będzie ich usunięcie. Usługa Intune ułatwia [wycofywanie aplikacji](device-management.md) ([portal klasyczny](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
