---
title: "Zarządzanie firmowymi urządzeniami | Microsoft Intune"
description: "Wprowadź urządzenia firmowe (COD) do systemu zarządzania na wiele sposobów, w zależności od urządzenia, sposobu jego zakupu oraz potrzeb organizacji."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecfeb73efed4a47256275120c52de232c556adfe
ms.openlocfilehash: 58efadf2f9fc34a31070aff93e86083583630caa


---

# Rejestrowanie firmowych urządzeń w usłudze Microsoft Intune
Urządzenia należące do organizacji lub firmy (COD) mogą być wprowadzane do systemu zarządzania w usłudze Intune na wiele sposobów, w zależności od urządzenia, sposobu jego zakupu i potrzeb organizacji. Firmowe urządzenia można również rejestrować (oraz zarządzać nimi) przez zainstalowanie aplikacji Portal firmy, podobnie jak w przypadku strategii „przynieś własne urządzenie” (BYOD, bring your own device).

## Firmowe urządzenia z systemem iOS
Te metody rejestracji są odpowiednie w scenariuszach „Wybierz własne urządzenie” (CYOD), w których organizacja kupuje urządzenia dla użytkowników, ale chce zachować możliwość zarządzania urządzeniem. Jeśli dana organizacja nabyła urządzenia z systemem iOS, można wstępnie zorganizować rejestrację w taki sposób, że urządzenie zostanie dołączone do systemu zarządzania, gdy użytkownik włączy je pierwszy raz. Usługa Intune obsługuje rejestrowanie urządzeń w ramach programu [Device Enrollment Program (DEP) firmy Apple](ios-device-enrollment-program-in-microsoft-intune.md) lub przy użyciu programu Apple Configurator działającego na komputerze Mac, który umożliwia rejestrację [bezpośrednią](ios-direct-enrollment-in-microsoft-intune.md) lub z wykorzystaniem [asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Rejestrowanie firmowych urządzeń z systemem iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Menedżer rejestracji urządzeń
Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika, zwanego kontem menedżera rejestracji urządzeń. Po utworzeniu konta menedżera rejestracji urządzeń menedżer może użyć tego konta do zarejestrowania większej liczby urządzeń. Domyślnie normalni użytkownicy mogą rejestrować do pięciu urządzeń. Rejestrowanie urządzeń za pomocą menedżera rejestrowania urządzeń działa tylko wobec urządzeń, które nie są wykorzystywane przez konkretnego użytkownika. Takie urządzenia nadają się do wykorzystania w punktach sprzedaży lub na potrzeby użycia aplikacji narzędziowych, ale są złym rozwiązaniem dla użytkowników, którzy potrzebują dostępu do poczty e-mail lub zasobów firmowych.

[Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Rejestrowanie firmowych komputerów z systemem Windows 10

Jeśli Twoja organizacja ma usługę Azure Active Directory w wersji Premium (AADP) lub pakiet Enterprise Management Suite (EMS), możesz [zarejestrować system Windows 10 dla przedsiębiorstw](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview), a komputery zostaną automatycznie oznaczone jako „firmowe” po dodaniu przez użytkowników swojego konta służbowego.

## Określanie urządzeń jako firmowe

Urządzenia firmowe są wyświetlane jako **Firmowe** w obszarze **Własność** na listach urządzeń. Urządzenia mogą zostać określone jako firmowe na następujące sposoby:

 - [Rejestracja przy użyciu menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Rejestracja przy użyciu programu [Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) firmy Apple lub narzędzia [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)
 - [Wstępna deklaracja urządzeń za pomocą numerów IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Rejestracja w usłudze Azure Active Directory lub pakiecie Enterprise Management Suite urządzeń z systemem Windows 10](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI)

Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) są często stosowanymi przez producentów oznaczeniami urządzeń przenośnych. Administratorzy usługi Intune mogą importować numery IMEI dla urządzeń, których właścicielem jest firma. Gdy urządzenie jest zarządzane przez usługę Intune, zostaje ono oznakowane jako urządzenie należące do firmy.

[Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO4-->


