---
# required metadata

title: Rejestrowanie urządzeń przenośnych w wersji ewaluacyjnej | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie urządzeń przenośnych w wersji ewaluacyjnej i instalowanie aplikacji
Aby skonfigurować zarządzanie urządzeniami przenośnymi za pomocą usługi Intune, należy najpierw ustawić urząd zarządzania urządzeniami przenośnymi, włączyć zarządzanie dla platform urządzeń oraz zarejestrować urządzenia w aplikacji Portal firmy. Następnie możesz wdrożyć opublikowaną przez siebie aplikację Microsoft Skype.

## Przygotowywanie usługi do zarządzania urządzeniami

1.  **Wybierz usługę Intune jako swój urząd zarządzania urządzeniami przenośnymi**

    W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi**. Wybierz pozycję **Zadania** > **Ustaw urząd MDM**, a następnie wybierz pozycję **Tak** w oknie dialogowym **Urząd MDM**.

2.  **Włącz rozwiązanie MDM dla danej platformy urządzenia**

    Włącz zarządzanie urządzeniami przenośnymi dla platformy urządzenia, którą chcesz zarządzać. Wymagania różnią się w zależności od używanej platformy:

    -   **iOS i Mac OS X**: zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android**: urządzenia przenośne z systemem Android umożliwiają użytkownikom rejestrację przy użyciu aplikacji Portal firmy dostępnej w sklepie Google Play. Nie jest wymagana dodatkowa konfiguracja w usłudze Intune.

    -   **Windows Phone**: zobacz [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Rejestrowanie urządzeń testowych

### iOS i Mac OS X
Zainstaluj aplikację **Portal firmy usługi Microsoft Intune** firmy Microsoft Corporation dostępną w sklepie App Store i zaloguj się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune. Wyświetl **zarejestrowane urządzenia** , aby dodać własne urządzenie.

### Android
Zainstaluj aplikację **Portal firmy usługi Intune** firmy Microsoft Corporation dostępną w sklepie [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) i zaloguj się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune.

### Windows Phone 8,1
Użytkownicy instalują aplikację **Portal firmy** firmy Microsoft Corporation dostępną w Sklepie Windows Phone i logują się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune.  Wyświetl **zarejestrowane urządzenia** , aby dodać własne urządzenie.

 ### Windows Phone 8.0
 Użytkownicy klikają pozycję **ustawienia systemu** &gt; **aplikacje firmowe** i logują się przy użyciu dodanych wcześniej poświadczeń użytkownika usługi Intune. Aplikacja Portal firmy jest wdrażana na telefonie.

Po wyświetleniu monitu o **adres serwera**wpisz „manage.microsoft.com”.


## Instalowanie wcześniej wdrożonej aplikacji
Otwórz Portal firmy na urządzeniu przenośnym, wybierz pozycję **Aplikacje**, a następnie zainstaluj aplikację **Microsoft Skype**..

Aby dowiedzieć się więcej na temat zarządzania urządzeniami przenośnymi przy użyciu usługi Intune, zobacz [Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)..

### Następne kroki
Gratulacje! Krok 5 przewodnika *wersji ewaluacyjnej usługi Microsoft Intune* właśnie został ukończony.

>[!div class="step-by-step"]

>[&larr; **Tworzenie zasad**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Opcje i dodatki** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  


<!--HONumber=May16_HO1-->


