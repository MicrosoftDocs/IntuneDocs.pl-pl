---
title: Przygotowanie usługi Intune do zarządzania urządzeniami mobilnymi
titlesuffix: Microsoft Intune
description: Przed migracją do usługi Microsoft Intune należy ocenić wymagania techniczne i biznesowe.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: 1e21fef5102b22dfe698a9adb73736508452acfe
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186379"
---
# <a name="phase-1-prepare-microsoft-intune-for-mobile-device-management-mdm"></a>Faza 1: Przygotowanie usługi Microsoft Intune do zarządzania urządzeniami przenośnymi (MDM)

Przed szczegółowym zapoznaniem się z zagadnieniami dotyczącymi konfigurowania usługi Intune przyjrzyjmy się wymaganiom organizacji w zakresie zarządzania urządzeniami przenośnymi (MDM, Mobile Device Management). Przydatne może być uruchomienie raportów aktywnych użytkowników w bieżącym dostawcy rozwiązania do zarządzania urządzeniami przenośnymi w celu zidentyfikowania krytycznych grup użytkowników. Następnie można rozpocząć odpowiadanie na pytania z sekcji [Określanie wymagań w zakresie MDM](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>Określanie wymagań w zakresie MDM

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Jakimi urządzeniami trzeba zarządzać?

-   Które [platformy](supported-devices-browsers.md) muszą mieć zapewnioną obsługę?

-   Czy obsługiwane urządzenia należą do firmy czy są osobiste?

-   Jakie połączenia są używane? Wi-Fi, VPN czy sieć komórkowa?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Jakie czynności będą wykonywać użytkownicy na zarządzanych urządzeniach?

-   Czy trzeba aprowizować aplikacje dla użytkowników końcowych?

-   Czy są używane niestandardowe aplikacje biznesowe? Czy tylko aplikacje z publicznego sklepu?

-   Czy trzeba aprowizować konta e-mail?

### <a name="what-kinds-of-users"></a>Jacy użytkownicy będą korzystać z rozwiązania?

-   Ilu użytkowników będzie korzystać z jednego urządzenia?

-   Jakie warunki użytkowania są potrzebne?

    -   Na tym etapie należy odpowiednio wcześnie konsultować się z działem prawnym.
    -   Jaka lokalizacja jest wymagana?

-   Czy użytkownicy są ogólnie obeznani z technologiami i rozwiązaniami informatycznymi?

### <a name="what-is-your-device-security-policy"></a>Jakie zasady zabezpieczeń urządzeń są używane?

- Czy jest potrzebne szyfrowanie na poziomie urządzenia?

- Jaka jest bieżąca długość kodów dostępu/kodów PIN do urządzeń?

- Czy konieczne jest wyłączenie funkcji urządzeń lub nałożenie ograniczeń na wybrane elementy ich działania? Przy użyciu profilów konfiguracji urządzeń można kontrolować różne ustawienia specyficzne dla danej platformy — można na przykład:
    - Wyłączyć aparat fotograficzny
    - Wymusić tryb korzystania tylko z jednej aplikacji<br/>

- Jakie rodzaje uwierzytelniania muszą być obsługiwane? Jeśli potrzebne jest uwierzytelnianie oparte na certyfikatach, to jakie certyfikaty należy aprowizować?
  - Usługa Intune może aprowizować certyfikaty z profilami dostępu do zasobów dla zarejestrowanych urządzeń.
  -   Jaka infrastruktura kluczy publicznych (PKI) musi być obsługiwana?
  <br></br>
- Czy obsługa wirtualnych sieci prywatnych (VPN) odbywa się na poziomie aplikacji czy urządzenia?

  -   Intune może udostępniać konfiguracje sieci VPN dla innych dostawców sieci VPN.
  <br/><br/>
- Czy jest dopuszczalne stosowanie tymczasowych wyjątków dla niektórych wymagań w celu uniknięcia przestoju? Czy urządzenia z dostępem muszą zawsze spełniać wszystkie wymagania dotyczące zabezpieczeń?

## <a name="next-steps"></a>Następne kroki
Przejrzyj te [analizy przypadków](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune), aby zapoznać się z procesem oceny wymagań w zakresie zarządzania urządzeniami przenośnymi w organizacjach z różnych branż.

Zapoznaj się z [podstawową konfiguracją usługi Intune](migration-guide-setup.md).
