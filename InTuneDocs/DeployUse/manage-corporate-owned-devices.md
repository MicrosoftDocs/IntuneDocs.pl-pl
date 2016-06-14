---
# required metadata

title: Zarządzanie urządzeniami firmowymi w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie firmowych urządzeń w usłudze Microsoft Intune
Urządzenia należące do organizacji lub firmy (COD) mogą być wprowadzane do systemu zarządzania na wiele sposobów, w zależności od urządzenia i sposobu jego zakupu.

## Firmowe urządzenia z systemem iOS
Te metody rejestracji są odpowiednie w scenariuszach „Wybierz własne urządzenie” (CYOD), w których organizacja kupuje urządzenia dla użytkowników, ale chce zachować możliwość zarządzania urządzeniem. Jeśli dana organizacja nabyła urządzenia z systemem iOS, można wstępnie zorganizować rejestrację w taki sposób, że urządzenie zostanie dołączone do systemu zarządzania, gdy użytkownik włączy je pierwszy raz. Usługa Intune obsługuje rejestrowanie urządzeń w ramach programu [Device Enrollment Program (DEP) firmy Apple](ios-device-enrollment-program-in-microsoft-intune.md) lub przy użyciu programu Apple Configurator działającego na komputerze Mac, który umożliwia rejestrację [bezpośrednią](ios-direct-enrollment-in-microsoft-intune.md) lub z wykorzystaniem [asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Rejestrowanie firmowych urządzeń z systemem iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Menedżer rejestracji urządzeń
Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika, zwanego kontem menedżera rejestracji urządzeń. Po utworzeniu konta menedżera rejestracji urządzeń menedżer może użyć tego konta do zarejestrowania większej liczby urządzeń. Domyślnie normalni użytkownicy mogą rejestrować do pięciu urządzeń. Rejestrowanie urządzeń za pomocą menedżera rejestrowania urządzeń działa tylko wobec urządzeń, które nie są wykorzystywane przez konkretnego użytkownika. Takie urządzenia nadają się do wykorzystania w punktach sprzedaży lub do użycia aplikacji narzędziowych, ale są złym rozwiązaniem dla użytkowników, którzy potrzebują dostępu do poczty e-mail lub zasobów firmowych.

[Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Określanie urządzeń należących do firmy z międzynarodowymi identyfikatorami urządzeń przenośnych (IMEI, International Mobile Equipment Identity)
Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) są często stosowanymi przez producentów oznaczeniami urządzeń przenośnych. Administratorzy usługi Intune mogą importować numery IMEI dla urządzeń, których właścicielem jest firma. Gdy urządzenie jest zarządzane przez usługę Intune, można oznakować je jako urządzenie należące do firmy i zastosować wobec niego odpowiednie zasady.

[Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


