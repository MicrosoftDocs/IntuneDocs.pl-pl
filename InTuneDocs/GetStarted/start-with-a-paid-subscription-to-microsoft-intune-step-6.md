---
title: "Wdrażanie zasad i aplikacji | Microsoft Intune"
description: "Można włączyć ustawienia zasad i wdrożyć aplikacje, które będą stosowane zaraz po zarejestrowaniu urządzeń do zarządzania."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d2a3e5c05180c1a3f2ee3bf91813df3b5fa7bc6
ms.openlocfilehash: 679c49d135c9161ecae5db704a3f6c96add003dc


---

# <a name="create-policies-and-publish-apps"></a>Tworzenie zasad i publikowanie aplikacji
Przed rozpoczęciem rejestrowania aplikacji w usłudze Intune można włączyć ustawienia zasad i aplikacji, które zostaną wdrożone od razu po rozpoczęciu zarządzania urządzeniami. Zasady usługi Intune udostępniają ustawienia, które ułatwiają sterowanie ustawieniami zabezpieczeń na urządzeniach przenośnych, obsługę ustawień Zapory systemu Windows i programu Endpoint Protection dla komputerów oraz wdrażanie aplikacji. Można konfigurować zasady oraz dodawać i wdrażać aplikacje, aby urządzenia otrzymywały ustawienia i aplikacje od razu po zarejestrowaniu w usłudze Intune.

Zasady i aplikacje są powiązane z określoną platformą.

## <a name="manage-device-settings"></a>Zarządzanie ustawieniami urządzenia

 Ustawienia zasad urządzenia są konfigurowane i zarządzane w odniesieniu do poszczególnych platform. Zasady można konfigurować dla następujących platform:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android i Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (na komputer i wersja Mobile)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Team](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Komputery z systemem Windows z uruchomionym klientem oprogramowania usługi Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Dowiedz się więcej na temat sposobu [zarządzania ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Dodawanie i wdrażanie aplikacji

Istnieją dwa sposoby dodawania aplikacji do usługi Intune, a następnie wdrażania ich na zarządzanych urządzeniach:
- **Wymagana instalacja** — aplikacje są automatycznie instalowane na zarządzanych urządzeniach.
- **Dostępna instalacja** — aplikacje są wyświetlane w aplikacji Portal firmy w usłudze Intune, dzięki czemu użytkownicy mogą wybrać, czy mają być instalowane na ich urządzeniach.

### <a name="add-apps"></a>Dodawanie aplikacji

Najpierw musisz udostępnić aplikacje w usłudze Intune za pomocą jednej z następujących metod:
- [Dodawanie aplikacji dla zarejestrowanych urządzeń](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Dodawanie aplikacji dla komputerów klienckich z oprogramowaniem usługi Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Wdrażanie aplikacji

Gdy aplikacja jest już dostępna w usłudze Intune, możesz wdrożyć ją na zarządzanych urządzeniach:
- [Wdrażanie aplikacji na urządzeniach](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Wdrażanie aplikacji kupionych w ramach zakupów zbiorczych:
    - [iOS — program zakupów zbiorczych](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Sklep Windows dla firm](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    Po skonfigurowaniu aplikacji do wdrożenia możesz [skonfigurować aplikacje](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) i [monitorować aplikacje](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).


### <a name="next-steps"></a>Następne kroki
Gratulacje! Krok 6 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony.

>[!div class="step-by-step"]

>[&larr; **Organizowanie użytkowników i urządzeń**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Dostosowywanie Portalu firmy** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Nov16_HO4-->


