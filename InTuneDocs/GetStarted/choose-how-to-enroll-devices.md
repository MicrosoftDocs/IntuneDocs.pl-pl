---
# required metadata

title: Wybieranie metody rejestrowania urządzeń przenośnych | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wybieranie metody rejestrowania urządzeń przenośnych

Rejestracja urządzenia przenośnego to proces, dzięki któremu smartfony, tablety i komputery mogą być zarządzane przez usługę Microsoft Intune. Jako administrator musisz określić, jak najlepiej zarejestrować urządzenia, w oparciu o następujące informacje:

 -  Własność (osobiste lub należące do firmy)
 -  Sposób użycia (udostępnione lub osobiste)
 -  Platforma (iOS, Android, Windows Phone, komputer z systemem Windows, komputer Mac)

Odpowiedzi na następujące pytania pomogą określić najlepszą metodę rejestracji dla zarządzanych urządzeń.

## **Czy pracownicy przynoszą własne urządzenia, czy są one udostępniane przez organizację?**

  **Urządzenia należące do użytkowników** — rejestracja „BYOD” (przynieś własne urządzenie): użytkownicy mogą rejestrować urządzenia, aby uzyskać dostęp do zasobów firmy, takich jak poczta e-mail, aplikacje firmowe, dane firmowe i pomoc techniczna. **Urządzenia należące do firmy** (COD) są dostarczane pracownikom przez organizację w celu spełnienia danego wymagania biznesowego.
  > [!div class="button"]   [Rejestracja BYOD >](#byod-device-enrollment) [Rejestracja COD](cod-device-enrollment)

### Rejestracja urządzeń BYOD

Rejestracja BYOD wymaga zainstalowania na urządzeniach użytkowników aplikacji Portal firmy usługi Intune. Następnie można uruchomić aplikację i zarejestrować urządzenie, podając poświadczenia służbowe. Jeśli usługa Intune znajdzie licencję dla tych poświadczeń, urządzenie zostanie dodane do konsoli administracyjnej usługi Intune i odbierze zasady z usługi Intune, aby umożliwić dostęp do zasobów firmy.

**Wybierz typ urządzenia:**

> [!div class="op_single_selector"]
- [Konfigurowanie zarządzania systemem Android przy użyciu usługi Microsoft Intune](..deploy-use/set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](..deploy-use/set-up-windows-phone-management-with-microsoft-intune.md)
- [Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune](..deploy-use/set-up-windows-device-management-with-microsoft-intune.md)


### Rejestracja urządzeń COD

Urządzenia należące do firmy można zarejestrować w celu obsługi modelu użytkowników dedykowanych lub urządzenia udostępnionego.  **Urządzenia udostępnione** nie mają jednego użytkownika i zazwyczaj nie są konfigurowane do uzyskiwania dostępu do poczty e-mail. Do takich urządzeń należą urządzenia z kiosku lub urządzenia przeznaczone do konkretnych zadań, które użytkownicy pobierają z puli, a następnie zwracają. Zalecane metody rejestracji urządzeń zależą od platformy urządzeń. **Urządzenia dedykowane** są wydawane poszczególnym użytkownikom, muszą być śledzone jako zasoby firmowe, podczas gdy użytkownicy mają możliwość uzyskania dostępu do poczty e-mail i danych na spersonalizowanych urządzeniach. Zalecane metody rejestracji urządzeń zależą od platformy urządzeń.

## **Czy urządzenia należące do firmy są udostępniane, czy mają dedykowanych użytkowników?**

> [!div class="button"] [Udostępnione >](#Shared-company-owned-devices) [Dedykowane >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Udostępnione urządzenia należące do firmy

Te urządzenia nie mają jednego użytkownika i zazwyczaj nie są konfigurowane do uzyskiwania dostępu do poczty e-mail. Do takich urządzeń należą urządzenia z kiosku lub urządzenia przeznaczone do konkretnych zadań, które użytkownicy pobierają z puli, a następnie zwracają. Zalecane metody rejestracji urządzeń zależą od platformy urządzeń.

  - **Urządzenia z systemem Windows i Android** — *menedżer rejestracji urządzeń* jest kontem usługi Intune, które może służyć do rejestracji wielu udostępnionych urządzeń przy użyciu aplikacji Portal firmy.
  > [!div class="button"]   [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Rejestracja urządzeń udostępnionych z systemem iOS

Preferowana metoda rejestracji urządzeń udostępnionych z systemem iOS należących do firmy zależy od sposobu zakupu tych urządzeń i zarządzania nimi:

  - **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane za pomocą profilu DEP.
  - **Apple Configurator na komputerze Mac (Mac)** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień. Jeśli nie chcesz resetować urządzeń do ustawień fabrycznych, użyj rejestracji bezpośredniej.
  - **Żadne z powyższych** — jeśli nie możesz lub nie chcesz użyć metod rejestracji opartych na programie DEP firmy Apple lub narzędziu Apple Configurator, skorzystaj z menedżera rejestracji urządzeń usługi Intune.

  **Wybierz:**
    > [!div class="button"]      [Rejestracja DEP >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Rejestracja bezpośrednia >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

  > [!div class="button"]     [Rejestracja za pomocą menedżera DEM >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Użytkownicy indywidualni** — urządzenia należące do firmy, które są wydawane poszczególnym użytkownikom, muszą być śledzone jako zasoby firmowe, podczas gdy użytkownicy mają możliwość uzyskania dostępu do poczty e-mail i danych na urządzeniach osobistych. Zalecane metody rejestracji urządzeń zależą od platformy urządzeń.

  - **Urządzenia z systemem Windows i Android** — importując międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) urządzeń należących do firmy, można oznaczyć je jako urządzenia należące do firmy w usłudze Intune. Następnie użytkownicy mogą zarejestrować swoje urządzenia jako urządzenia osobiste, instalując aplikację Portal firmy, aby uzyskać dostęp do zasobów firmowych, np. poczty e-mail, aplikacji i innych danych.
  > [!div class="button"]   [Oznaczanie za pomocą numeru IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **Urządzenia z systemem iOS** — udostępnionymi urządzeniami z systemem iOS można zarządzać na trzy sposoby.  **Jak można rejestrować udostępnione urządzenia z systemem iOS?**

    - **Program Device Enrollment Program firmy Apple (DEP)** — wobec urządzeń z systemem iOS zakupionych lub zarządzanych w programie DEP można zastosować profil rejestracji. Gdy użytkownicy włączają urządzenia po raz pierwszy, urządzenia pobierają profil DEP i są rejestrowane zgodnie z profilem.
    > [!div class="button"]     [Rejestracja DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator na komputerze Mac** — program Apple Configurator jest aplikacją firmy Apple uruchamianą na komputerach Mac. Urządzenia z systemem iOS można podłączyć do komputera Mac za pomocą kabla USB, aby zainstalować profil rejestracji na urządzeniu. Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień.

    Jeśli nie chcesz resetować urządzeń do ustawień fabrycznych, użyj rejestracji bezpośredniej.
    Jeśli możesz zresetować urządzenia do ustawień fabrycznych w celu ich rejestracji, użyj rejestracji za pomocą asystenta ustawień.
    > [!div class="button"] [Rejestracja asystenta ustawień systemu iOS](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][Rejestracja bezpośrednia systemu iOS](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Żadne z powyższych** — jeśli nie możesz lub nie chcesz użyć metod rejestracji opartych na programie DEP firmy Apple lub narzędziu Apple Configurator, importując międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) urządzeń należących do firmy, możesz oznaczyć je jako urządzenia należące do firmy w usłudze Intune. Następnie użytkownicy mogą zarejestrować swoje urządzenia jako urządzenia osobiste, instalując aplikację Portal firmy, aby uzyskać dostęp do zasobów firmowych, np. poczty e-mail, aplikacji i innych danych. > [!div class="button"][Oznaczanie urządzeń numerami IMEI](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO2-->


