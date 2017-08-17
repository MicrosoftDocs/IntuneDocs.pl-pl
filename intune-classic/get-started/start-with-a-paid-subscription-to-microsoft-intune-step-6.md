---
title: "Wdrażanie zasad i aplikacji"
description: "Można włączyć ustawienia zasad i wdrożyć aplikacje, które będą stosowane zaraz po zarejestrowaniu urządzeń do zarządzania."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0d1e88db4a0da250f449c8e87f674f7694904d7b
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2017
---
# <a name="create-policies-and-publish-apps"></a>Tworzenie zasad i publikowanie aplikacji

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera informacje dla administratorów usługi Intune dotyczące tworzenia zasad i publikowania aplikacji, które można następnie wdrażać na zarządzanych urządzeniach.

Przed rozpoczęciem rejestrowania aplikacji w usłudze Intune można włączyć ustawienia zasad i aplikacji, które zostaną wdrożone od razu po rozpoczęciu zarządzania urządzeniami. Zasady usługi Intune udostępniają ustawienia, które ułatwiają sterowanie ustawieniami zabezpieczeń na urządzeniach przenośnych, obsługę ustawień Zapory systemu Windows i programu Endpoint Protection dla komputerów oraz wdrażanie aplikacji. Można konfigurować zasady oraz dodawać i wdrażać aplikacje, aby urządzenia otrzymywały ustawienia i aplikacje od razu po zarejestrowaniu w usłudze Intune.

Zasady i aplikacje są powiązane z określoną platformą.

## <a name="manage-device-settings"></a>Zarządzanie ustawieniami urządzenia

 Ustawienia zasad urządzenia są konfigurowane i zarządzane w odniesieniu do poszczególnych platform. Poniższe linki zawierają listy dostępnych ustawień dla odpowiednich platform:

- [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android i Samsung KNOX Standard](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (komputery i urządzenia mobilne)](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Team](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Komputery z systemem Windows z uruchomionym klientem oprogramowania usługi Intune](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Dowiedz się więcej na temat sposobu [zarządzania ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Dodawanie i wdrażanie aplikacji

Istnieją dwa sposoby dodawania aplikacji do usługi Intune, a następnie wdrażania ich na zarządzanych urządzeniach:
- **Wymagana instalacja** — aplikacje są automatycznie instalowane na zarządzanych urządzeniach.
- **Dostępna instalacja** — aplikacje są wyświetlane w aplikacji Portal firmy w usłudze Intune, dzięki czemu użytkownicy mogą wybrać, czy mają być instalowane na ich urządzeniach.

### <a name="add-apps"></a>Dodawanie aplikacji

Najpierw musisz udostępnić aplikacje w usłudze Intune za pomocą jednej z następujących metod:
- [Dodawanie aplikacji dla zarejestrowanych urządzeń](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Dodawanie aplikacji dla komputerów klienckich z oprogramowaniem usługi Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Wdrażanie aplikacji

Gdy aplikacja jest już dostępna w usłudze Intune, możesz wdrożyć ją na zarządzanych urządzeniach:
- [Wdrażanie aplikacji na urządzeniach](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Wdrażanie aplikacji kupionych w ramach zakupów zbiorczych:
    - [iOS — program zakupów zbiorczych](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Sklep Microsoft dla Firm](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](/intune-classic/deploy-use/android-for-work-apps)

    Po skonfigurowaniu aplikacji do wdrożenia możesz [skonfigurować aplikacje](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Organizowanie użytkowników i urządzeń**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Dostosowywanie Portalu firmy** &rarr;](/intune/company-portal-customize)  
