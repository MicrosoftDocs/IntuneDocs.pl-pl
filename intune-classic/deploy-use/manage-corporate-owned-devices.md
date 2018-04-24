---
title: Zarządzanie urządzeniami należącymi do firmy
description: Rejestruj urządzenia należące do firmy na różne sposoby, w zależności od rodzaju urządzenia, sposobu jego zakupu i potrzeb organizacji.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4d224ceb819b6b0b4be0596c46d7bb20a98ddd97
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Rejestrowanie urządzeń firmowych przy użyciu usługi Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Urządzenia należące do organizacji lub firmy mogą być rejestrowane w celu zarządzania przez usługę Intune na wiele sposobów, w zależności od rodzaju urządzenia, sposobu jego zakupu i potrzeb organizacji. Firmowe urządzenia można również rejestrować (oraz zarządzać nimi) przez zainstalowanie aplikacji Portal firmy, podobnie jak w scenariuszu „przynieś własne urządzenie” (BYOD, bring your own device).

Domyślnie w usłudze Intune mogą być rejestrowane urządzenia dla dowolnej platformy. Aby zablokować możliwość rejestrowania urządzeń, zaloguj się do [portalu administracyjnego usługi Microsoft Intune](https://manage.microsoft.com), korzystając z poświadczeń administratora. Wybierz pozycję **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Reguły rejestracji**, a następnie wyczyść pola wyboru odpowiadające platformom, które chcesz zablokować.

## <a name="enroll-corporate-owned-ios-devices"></a>Rejestrowanie firmowych urządzeń z systemem iOS

Metody rejestrowania urządzeń firmowych są dobrym wyborem w scenariuszu „wybierz własne urządzenie” (CYOD, choose your own device). W środowisku CYOD organizacja pokrywa koszty urządzenia wybranego przez użytkownika i zarządza tym urządzeniem.

Jeśli użytkownicy mają do wyboru urządzenia z systemem iOS, możesz wstępnie skonfigurować rejestrację tak, aby urządzenie było zarządzane za pomocą usługi Intune od momentu pierwszego uruchomienia go przez użytkownika. Usługa Intune obsługuje rejestrowanie urządzeń w ramach programu [Device Enrollment Program (DEP) firmy Apple](ios-device-enrollment-program-in-microsoft-intune.md) lub przy użyciu programu Apple Configurator działającego na komputerze Mac, który umożliwia rejestrację [bezpośrednią](ios-direct-enrollment-in-microsoft-intune.md) lub z wykorzystaniem [Asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Dowiedz się, jak [rejestrować firmowe urządzenia z systemem iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Tworzenie konta menedżera rejestracji urządzeń

W usłudze Intune możesz utworzyć konto menedżera rejestracji urządzeń (DEM, device enrollment manager) przeznaczone dla jednego użytkownika, aby zarządzać dużą liczbą urządzeń przenośnych w organizacji. Po utworzeniu konta DEM oznaczony menedżer konta może zarejestrować więcej niż 15 urządzeń, co jest dopuszczalną liczbą urządzeń rejestrowanych przez użytkownika standardowego.

Konto DEM służy do rejestrowania tylko tych urządzeń, które nie są używane przez pojedynczego, określonego użytkownika. Tego rodzaju urządzenia nadają się do wykorzystania w punktach sprzedaży lub na potrzeby użycia aplikacji narzędziowych, ale są złym rozwiązaniem dla użytkowników, którzy potrzebują dostępu do poczty e-mail lub zasobów firmowych.

Dowiedz się, jak [zarejestrować firmowe urządzenia przy użyciu konta DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Rejestrowanie urządzeń firmowych z systemem Windows 10 Enterprise

Jeśli w Twojej organizacji używasz usługi Azure Active Directory Premium lub Microsoft Enterprise Mobility Suite, możesz [zarejestrować urządzenia z systemem Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Jeśli użytkownik na urządzeniu doda konto służbowe, urządzenie zostanie automatycznie oznaczone jako „firmowe”.

## <a name="import-imei-numbers"></a>Importowanie numerów IMEI

Wielu producentów urządzeń przenośnych oznacza swoje urządzenia unikatowym numerem, zwanym międzynarodowym numerem identyfikującym urządzenia przenośne (IMEI, International Mobile Equipment Identity). Możesz zaimportować numery IMEI urządzeń należących do organizacji. Gdy urządzenie jest zarządzane przez usługę Intune, zostaje oznaczone jako urządzenie firmowe.

Dowiedz się, jak [oznaczać firmowe urządzenia przy użyciu numerów IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Identyfikowanie urządzeń firmowych

Usługa Intune rozpoznaje urządzenie jako „firmowe” w przypadku spełnienia dowolnego z poniższych warunków:

 - Urządzenie zostało [zarejestrowane przy użyciu konta DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (wszystkie platformy).
 - Urządzenie zostało zarejestrowane przy użyciu [programu DEP firmy Apple](ios-device-enrollment-program-in-microsoft-intune.md) lub [programu Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (tylko system iOS).
 - Producent urządzenia [wstępnie zadeklarował urządzenie przy użyciu numerów IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (wszystkie platformy z numerami IMEI).
 - Urządzenie zostało zarejestrowane w usłudze [Azure Active Directory lub Enterprise Mobility Suite jako urządzenie z systemem Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (tylko system Windows 10).

Jeśli urządzenie zostało oznaczone jako firmowe, zobaczysz wartość **Należące do firmy** w kolumnie **Własność** dla tego rekordu urządzenia w konsoli administratora. 
