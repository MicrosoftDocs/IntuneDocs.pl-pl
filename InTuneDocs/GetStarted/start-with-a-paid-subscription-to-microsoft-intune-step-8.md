---
title: "Włączanie rejestracji urządzeń | Microsoft Intune"
description: "Ustawianie urzędu zarządzania urządzeniami przenośnymi i włączanie rejestracji urządzeń z systemami iOS, Windows, Android i Mac."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: ca6e016927da1de6604b0c6a2924702ec90c9fab


---

# <a name="enroll-mobile-devices-and-install-an-app"></a>Rejestrowanie urządzeń przenośnych i instalowanie aplikacji
Aby skonfigurować zarządzanie urządzeniami przenośnymi za pomocą usługi Intune, należy najpierw ustawić *urząd zarządzania urządzeniami przenośnymi*, który identyfikuje usługę umożliwiającą zarządzanie urządzeniami skojarzonymi z kontem. W tych wskazówkach przyjęto założenie, że zamiast programu System Center Configuration Manager będzie używana usługa Intune. Po ustawieniu urzędu zarządzania urządzeniami przenośnymi można włączyć zarządzanie dla platform urządzeń i zarejestrować urządzenia w aplikacji Portal firmy.

## <a name="enable-device-enrollment"></a>Włączanie rejestracji urządzeń

1. **Wybierz usługę Intune jako swój urząd zarządzania urządzeniami przenośnymi**
   . W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Administracja** > **Zarządzanie urządzeniami przenośnymi** i wybierz opcję **Set MDM Authority** (Ustaw urząd MDM) w obszarze **Zadania**.  

2. Wybierz przycisk **Tak** w oknie dialogowym Urząd MDM.

    ![Konsola administracyjna. Konfigurowanie usługi Intune jako urzędu MDM](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>Wybieranie sposobu rejestrowania urządzeń

Usługa Intune może zarządzać urządzeniami w różny sposób w zależności od wymagań Twojej firmy. „Przynieś własne urządzenie” (BYOD), urządzenia należące do firmy, „Wybierz własne urządzenie” (CYOD) i urządzenia działające w trybie kiosku to tylko kilka dostępnych scenariuszy rejestracji.

Wykonaj te kroki, aby [wybrać sposób rejestrowania urządzeń](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Włącz rozwiązanie MDM dla danej platformy urządzenia
W celu ustanowienia relacji między dostawcą platformy a dzierżawą usługi Intune należy włączyć rejestrację urządzeń iOS, Mac i Android for Work. Na urządzeniach z systemami Windows i Android nie trzeba wykonywać dodatkowych czynności, ale w przypadku urządzeń z systemem Windows można uprościć rejestrację urządzeń dla użytkowników, tworząc specjalny wpis DNS w rejestrze.

Włącz zarządzanie urządzeniami dla platformy urządzenia, którą chcesz zarządzać. Wymagania różnią się w zależności od używanej platformy:

-  [iOS i Mac OS](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [Windows (komputer)](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Windows 10 Mobile i Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

Po włączeniu rejestracji użytkownicy mogą pobrać aplikację Portal firmy na urządzenie i ukończyć proces rejestracji urządzenia.

### <a name="enable-company-owned-device-enrollment"></a>Włączanie rejestracji urządzeń należących do firmy
Możesz również włączyć różne scenariusze [rejestracji urządzeń należących do firmy](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices), takie jak:
- [Program Device Enrollment Program firmy Apple](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Rejestracja za pośrednictwem asystenta ustawień programu Apple Configurator](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Rejestracja za pośrednictwem asystenta ustawień programu Apple Configurator](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Menedżer rejestracji urządzeń](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Następne kroki
Gratulacje! Ostatni krok *przewodnika Szybki start dotyczącego usługi Intune* został ukończony. Wstępna konfiguracja została ukończona, dlatego możesz rozważyć możliwość włączenia dodatkowych funkcji zarządzania urządzeniami przenośnymi (MDM).

>[!div class="step-by-step"]

>[&larr; **Rejestrowanie urządzeń**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Zadania po konfiguracji** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Nov16_HO4-->


