---
title: "Włączanie rejestracji urządzeń"
description: "Ustawianie urzędu zarządzania urządzeniami przenośnymi i włączanie rejestracji urządzeń z systemami iOS, Windows, Android i Mac."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6b860e0cb2475542a5b079508f71af096c4285b6
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="enable-enrollment-for-mobile-devices"></a>Włączenie rejestracji dla urządzeń przenośnych

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym temacie opisano sposób, w jaki administrator może włączyć rejestrację urządzeń przenośnych. Aby uzyskać pomoc dotyczącą używania usługi Intune na telefonie, zobacz artykuł [Wykonywanie pracy przy użyciu urządzeń zarządzanych](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).

Aby skonfigurować zarządzanie urządzeniami przenośnymi za pomocą usługi Intune, należy najpierw ustawić *urząd zarządzania urządzeniami przenośnymi*, który identyfikuje usługę umożliwiającą zarządzanie urządzeniami skojarzonymi z kontem. W tych wskazówkach przyjęto założenie, że zamiast programu System Center Configuration Manager będzie używana usługa Intune. Po ustawieniu urzędu zarządzania urządzeniami przenośnymi można włączyć zarządzanie dla platform urządzeń i zarejestrować urządzenia w aplikacji Portal firmy.

## <a name="enable-device-enrollment"></a>Włączanie rejestracji urządzeń

1. **Wybierz usługę Intune jako swój urząd zarządzania urządzeniami przenośnymi**. W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Administracja** > **Zarządzanie urządzeniami przenośnymi** i wybierz opcję **Ustaw urząd MDM** w obszarze **Zadania**.  

2. Wybierz przycisk **Tak** w oknie dialogowym Urząd MDM.

    ![Konsola administracyjna. Konfigurowanie usługi Intune jako urzędu MDM](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a>Wybieranie sposobu rejestrowania urządzeń

Usługa Intune może zarządzać urządzeniami w różny sposób w zależności od wymagań Twojej firmy. „Przynieś własne urządzenie” (BYOD), urządzenia należące do firmy, „Wybierz własne urządzenie” (CYOD) i urządzenia działające w trybie kiosku to tylko kilka dostępnych scenariuszy rejestracji.

Wykonaj te kroki, aby [wybrać sposób rejestrowania urządzeń](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Włącz rozwiązanie MDM dla danej platformy urządzenia
W celu ustanowienia relacji między dostawcą platformy a dzierżawą usługi Intune należy włączyć rejestrację urządzeń iOS, Mac i Android for Work. Na urządzeniach z systemami Windows i Android nie trzeba wykonywać dodatkowych czynności, ale w przypadku urządzeń z systemem Windows można uprościć rejestrację urządzeń dla użytkowników, tworząc specjalny wpis DNS w rejestrze.

Włącz zarządzanie urządzeniami dla platformy urządzenia, którą chcesz zarządzać. Wymagania różnią się w zależności od używanej platformy:

- [iOS i Mac OS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Windows 10 i Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [Komputer PC z systemem Windows](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (klient oprogramowania usługi Intune)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

Po włączeniu rejestracji użytkownicy mogą pobrać aplikację Portal firmy na urządzenie i ukończyć proces rejestracji urządzenia.

### <a name="enable-company-owned-device-enrollment"></a>Włączanie rejestracji urządzeń należących do firmy
Możesz również włączyć różne scenariusze [rejestracji urządzeń należących do firmy](/intune-classic/deploy-use/manage-corporate-owned-devices), takie jak:
- [Program Device Enrollment Program firmy Apple](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Rejestracja za pośrednictwem asystenta ustawień programu Apple Configurator](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Rejestracja bezpośrednia w narzędziu Apple Configurator](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Menedżer rejestracji urządzeń](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Następne kroki
Gratulacje! Ostatni krok *przewodnika Szybki start dotyczącego usługi Intune* został ukończony. Wstępna konfiguracja została ukończona, dlatego możesz rozważyć możliwość włączenia dodatkowych funkcji zarządzania urządzeniami przenośnymi (MDM).

>[!div class="step-by-step"]
>[&larr; **Rejestrowanie urządzeń**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Zadania po konfiguracji** &rarr;](.\post-configuration-tasks.md)  
