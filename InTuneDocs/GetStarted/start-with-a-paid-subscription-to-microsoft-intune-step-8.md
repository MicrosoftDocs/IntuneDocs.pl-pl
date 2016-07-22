---
# required metadata

title: Rejestrowanie urządzeń przenośnych i instalowanie aplikacji | Usługa Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie urządzeń przenośnych i instalowanie aplikacji
Aby skonfigurować zarządzanie urządzeniami przenośnymi za pomocą usługi Intune, musisz najpierw ustawić urząd zarządzania urządzeniami przenośnymi, włączyć zarządzanie platformami urządzeń i zarejestrować swoje urządzenia w aplikacji Portal firmy. Następnie możesz wdrożyć aplikację Microsoft Skype opublikowaną w kroku 6.

## Włączanie zarządzania urządzeniami i rejestracja urządzeń

1.  **Wybierz usługę Intune jako swój urząd zarządzania urządzeniami przenośnymi**
    W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Administracja** > **Zarządzanie urządzeniami przenośnymi**, a następnie wybierz pozycję **Ustaw urząd MDM** w obszarze **Zadania**.  Wybierz przycisk **Tak** w oknie dialogowym Urząd MDM.
    ![Konsola administracyjna. Konfigurowanie usługi Intune jako urzędu MDM](./media/mdmAuthority.png)

2.  **Włącz rozwiązanie MDM dla danej platformy urządzenia**
    Włącz zarządzanie urządzeniami przenośnymi dla platformy urządzenia, którą chcesz zarządzać. Wymagania różnią się w zależności od używanej platformy:

    -   **iOS i Mac OS X**: zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: zobacz [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **System Android**: urządzenia przenośne z systemem Android umożliwiają użytkownikom rejestrację przy użyciu aplikacji portalu firmy dostępnej w sklepie [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). Nie jest wymagana dodatkowa konfiguracja w usłudze Intune.

3.  **Rejestrowanie urządzeń**:

    -   **System Android** — zainstaluj aplikację **Portal firmy usługi Intune** firmy Microsoft Corporation, dostępną w sklepie [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), i zaloguj się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune.

    -   **Systemy iOS i Mac OS X** — zainstaluj aplikację **Portal firmy usługi Microsoft Intune** firmy Microsoft Corporation, dostępną w sklepie App Store, i zaloguj się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune. Wyświetl **zarejestrowane urządzenia** , aby dodać własne urządzenie.

    -   **System Windows Phone 8.1** — użytkownicy instalują aplikację **Portal firmy**, udostępnianą przez firmę Microsoft Corporation w Sklepie Windows Phone, i logują się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune.  Wyświetl **zarejestrowane urządzenia** , aby dodać własne urządzenie.

    -   **System Windows Phone 8.0** — użytkownicy klikają opcje **Ustawienia systemu** &gt; **Aplikacje firmowe** i logują się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune. Aplikacja portalu firmy jest wdrażana na telefonie.

    Po wyświetleniu monitu o **adres serwera**wpisz „manage.microsoft.com”.

## Instalowanie aplikacji na zarejestrowanym urządzeniu
W [kroku 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) tego przewodnika Szybki start aplikacja Skype została opublikowana w niestandardowej grupie Użytkownicy usługi Intune. Teraz ta aplikacja zostanie zainstalowana na nowo zarejestrowanym urządzeniu.

Otwórz portal firmy na zarejestrowanym urządzeniu przenośnym, wybierz pozycję **Aplikacje**, a następnie zainstaluj aplikację **Microsoft Skype**..

Aby dowiedzieć się więcej na temat zarządzania urządzeniami przenośnymi przy użyciu usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], zobacz [Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)..


### Następne kroki
Gratulacje! Ostatni krok *przewodnika Szybki start dotyczącego usługi Intune* został ukończony. Wstępna konfiguracja została ukończona, dlatego możesz rozważyć możliwość włączenia dodatkowych funkcji zarządzania urządzeniami przenośnymi (MDM).

>[!div class="step-by-step"]

>[&larr; **Rejestrowanie urządzeń**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Zadania po konfiguracji** &rarr;](.\post-configuration-tasks.md)  


<!--HONumber=May16_HO1-->


