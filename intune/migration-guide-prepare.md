---
title: "Przygotowanie usługi Intune do zarządzania urządzeniami mobilnymi"
description: "Celem tego artykułu jest ułatwienie czytelnikom oceny wymagań biznesowych i technicznych przed rozpoczęciem migracji do usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 65e3bb4b6a4e6e8dcfa1dd16738ae47758f4fb9b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>Faza 1: Przygotowanie usługi Intune do zarządzania urządzeniami przenośnymi (MDM)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Przed szczegółowym zapoznaniem się z zagadnieniami dotyczącymi konfigurowania usługi Intune przyjrzyjmy się wymaganiom organizacji w zakresie zarządzania urządzeniami przenośnymi (MDM, Mobile Device Management). Raporty na temat aktywnych użytkowników pochodzące od bieżącego dostawcy usług MDM mogą ułatwić określenie krytycznych grup użytkowników. Kolejnym krokiem będzie znajdowanie odpowiedzi na pytania zawarte w [sekcji dotyczącej określania wymagań w zakresie MDM](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>Określanie wymagań w zakresie MDM

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Jakimi urządzeniami trzeba zarządzać?

-   Które [platformy](/intune-classic/get-started/supported-mobile-devices-and-computers) muszą mieć zapewnioną obsługę?

-   Czy obsługiwane urządzenia należą do firmy czy są objęte modelem BYOD?

-   Jakie połączenia są używane? Wi-Fi, VPN czy sieć komórkowa?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Jakie czynności będą wykonywać użytkownicy na zarządzanych urządzeniach?

-   Czy trzeba aprowizować aplikacje dla użytkowników końcowych?

-   Czy są używane niestandardowe aplikacje biznesowe? Czy tylko aplikacje z publicznego sklepu?

-   Czy trzeba aprowizować konta e-mail?

### <a name="what-kinds-of-users"></a>Jacy użytkownicy będą korzystać z rozwiązania?

-   Ilu użytkowników będzie korzystać z jednego urządzenia?

-   Jakie Warunki użytkowania są potrzebne?

    -   Na tym etapie należy odpowiednio wcześnie konsultować się z działem prawnym.

    -   Jaka lokalizacja jest wymagana?

-   Czy użytkownicy są ogólnie obeznani z technologiami i rozwiązaniami informatycznymi?

### <a name="what-is-your-device-security-policy"></a>Jakie zasady zabezpieczeń urządzeń są używane?

-   Czy jest potrzebne szyfrowanie na poziomie urządzenia?

-   Jaka jest długość kodów dostępu/kodów PIN do urządzeń?

-   Czy konieczne jest wyłączenie funkcji urządzeń lub nałożenie ograniczeń na wybrane elementy ich działania?

    -   Przy użyciu profilów konfiguracji urządzeń można kontrolować różne ustawienia specyficzne dla danej platformy, na przykład wyłączyć aparat fotograficzny lub wymusić tryb korzystania tylko z jednej aplikacji.
<br></br>
-   Jakie rodzaje uwierzytelniania muszą być obsługiwane?

    -   Jeśli potrzebne jest uwierzytelnianie oparte na certyfikatach, to jakie certyfikaty należy aprowizować?

        -   Usługa Intune może aprowizować certyfikaty z profilami dostępu do zasobów dla zarejestrowanych urządzeń.
<br></br>
    -   Jaka infrastruktura kluczy publicznych (PKI) musi być obsługiwana?
<br></br>
-   Czy obsługa wirtualnych sieci prywatnych (VPN) odbywa się na poziomie aplikacji czy urządzenia?

    -   Intune może udostępniać konfiguracje sieci VPN dla innych dostawców sieci VPN.
<br></br>
-   Czy jest dopuszczalne stosowanie tymczasowych wyjątków dla niektórych wymagań w celu uniknięcia przestoju? Czy urządzenia z dostępem muszą zawsze spełniać wszystkie wymagania dotyczące zabezpieczeń?

## <a name="additional-information"></a>Dodatkowe informacje

-   Aby bardziej szczegółowo zapoznać się z procesem oceny wymagań w zakresie zarządzania urządzeniami przenośnymi w organizacjach z różnych branż, przejrzyj te [analizy przypadków](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune).

## <a name="next-steps"></a>Następne kroki

[Konfiguracja podstawowa](migration-guide-setup.md)
