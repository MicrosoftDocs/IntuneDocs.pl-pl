---
title: "Przegląd cyklu życia aplikacji | Microsoft Intune"
description: "Dowiedz się więcej na temat cyklu życia aplikacji zarządzanych przez usługę Intune — od momentu ich dodania do ich ewentualnego wycofania."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 4c62e63b624165982fbbcd1765b14abe6ec0ae96


---

# Przegląd cyklu życia aplikacji

Cykl życia aplikacji w usłudze Intune rozpoczyna się po dodaniu aplikacji i jest realizowany przez dodatkowe fazy aż do usunięcia aplikacji.

![Cykl życia aplikacji](./media/app-lifecycle.png "the Intune app lifecycle")

## Dodaj

Pierwszym etapem wdrożenia aplikacji jest dodanie do usługi Intune aplikacji, którą chcesz zarządzać i wdrożyć. Istnieje wiele różnych typów aplikacji, z którymi można pracować, ale podstawowe procedury dla wszystkich są takie same. Usługa Intune umożliwia dodawanie aplikacji zarówno dla [zarejestrowanych urządzeń](add-apps-for-mobile-devices-in-microsoft-intune.md), jak i [komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## Wdróż

Po dodaniu aplikacji do usługi Intune możesz tę aplikację [wdrożyć na urządzeniach, którymi zarządzasz](deploy-apps.md). Usługa Intune ułatwia ten proces, a po wdrożeniu aplikacji możesz [monitorować sukces](monitor-apps-in-microsoft-intune.md) wdrożenia z konsoli administracyjnej usługi Intune. Ponadto niektóre sklepy z aplikacjami, takie jak [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) i [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md), pozwalają na zakup zbiorczych licencji na aplikacje dla firm. Usługa Intune może synchronizować dane z tymi sklepami, aby umożliwić wdrażanie licencji i śledzenie ich użycia dla tych typów aplikacji bezpośrednio z Konsoli administracyjnej usługi Intune.

## Konfiguracja

W ramach cyklu życia aplikacji regularnie wydawane są nowe wersje aplikacji. Usługa Intune udostępnia narzędzia do łatwego [aktualizowania wdrożonych aplikacji](update-apps-using-microsoft-intune.md) do nowszej wersji. Ponadto dla niektórych aplikacji można skonfigurować dodatkowe funkcje, na przykład:
- [Zasady konfiguracji aplikacji systemu iOS](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) pozwalają określać ustawienia dla zgodnych aplikacji systemu iOS, które będą używane po uruchomieniu aplikacji. Na przykład aplikacja może wymagać określonych ustawień oznaczania marką lub nazwy serwera, z którym ma nawiązać połączenie.
- [Zasady przeglądarki zarządzanej](manage-internet-access-using-managed-browser-policies.md) pomagają w konfigurowaniu ustawień dla przeglądarki zarządzanej przez usługę Intune, która zastępuje domyślną przeglądarkę urządzenia i umożliwia ograniczenie witryn sieci Web, które użytkownicy mogą odwiedzać.

## Ochrona

Usługa Intune zapewnia wiele sposobów ochrony danych w aplikacjach. Główne sposoby są następujące:
- [Dostęp warunkowy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) pozwala na kontrolowanie dostępu do poczty e-mail i innych usług w oparciu o określone kryteria, takie jak typy urządzeń albo spełnienie wdrożonych [zasad zgodności urządzeń](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- [Zarządzanie aplikacjami mobilnymi (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) współpracuje z poszczególnymi aplikacjami, aby chronić dane firmowe, z których te aplikacje korzystają. Na przykład można ograniczyć kopiowanie danych między aplikacjami niezarządzanymi i zarządzanymi albo zapobiec uruchamianiu aplikacji na urządzeniach ze zdjętymi zabezpieczeniami lub z odblokowanym kontem root.

## Wycofaj

W dłuższej perspektywie czasu prawdopodobne jest, że wdrożone aplikacje staną się nieaktualne i konieczne będzie ich usunięcie. Usługa Intune ułatwia [wycofywanie aplikacji](retire-apps-using-microsoft-intune.md).



<!--HONumber=Oct16_HO4-->


