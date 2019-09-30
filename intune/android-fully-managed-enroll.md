---
title: Konfiguracja rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android Enterprise
titleSuffix: Microsoft Intune
description: Dowiedz się, jak rejestrować w pełni zarządzane urządzenia z systemem Android Enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0035f8d5cd67a995924f7d07a662d8c0671bf063
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163779"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices"></a>Konfiguracja rejestracji w pełni zarządzanych urządzeń z systemem Android Enterprise w usłudze Intune 

W pełni zarządzane urządzenia z systemem Android Enterprise to urządzenia należące do firmy skojarzone z jednym użytkownikiem i wykorzystywane wyłącznie do pracy, a nie do celów osobistych. Administratorzy mogą zarządzać całym urządzeniem i wymuszać kontrolki zasad niedostępne dla profilów służbowych, takie jak:
- Zezwalanie na instalowanie aplikacji tylko z zarządzanego sklepu Google Play.
- Blokowanie dezinstalacji aplikacji zarządzanych.
- Uniemożliwianie użytkownikom przywracania ustawień fabrycznych urządzenia itd.

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na urządzeniach z rozwiązaniem Android Enterprise, w tym na w pełni zarządzanych urządzeniach z systemem Android Enterprise. Aby uzyskać szczegółowe informacje na temat rozwiązania Android Enterprise, zobacz [wymagania dotyczące rozwiązania Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Wymagania techniczne

Do zarządzania w pełni zarządzanymi urządzeniami z systemem Android Enterprise niezbędna jest autonomiczna dzierżawa usługi Intune. Zarządzanie w pełni zarządzanymi urządzeniami nie jest dostępne w trybie hybrydowym (połączenie programu Configuration Manager) ani w starszej konsoli zarządzania programu Silverlight.

Urządzenia muszą spełniać następujące wymagania, aby mogły być zarządzane jako w pełni zarządzane urządzenia z systemem Android Enterprise:

- System operacyjny Android w wersji 6.0 lub nowszy.
- Na urządzeniach musi działać kompilacja systemu Android obsługująca łączność z usługami Google Mobile Services (GMS). Urządzenia muszą mieć dostępne usługi GMS i muszą być w stanie połączyć się z usługami GMS.

Jeśli powyższe wymagania są spełnione, nie ma żadnych ograniczeń dotyczących producenta urządzenia/producenta OEM.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Konfigurowanie zarządzania w pełni zarządzanymi urządzeniami z systemem Android Enterprise

Aby skonfigurować zarządzanie w pełni zarządzanymi urządzeniami z systemem Android Enterprise, wykonaj następujące kroki:

1. Aby przygotować się do zarządzania urządzeniami przenośnymi, należy [ustawić urząd zarządzania urządzeniami przenośnymi (MDM) na wartość **Microsoft Intune**](mdm-authority-set.md). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.
2. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android Enterprise](connect-intune-android-enterprise.md).
3. [Włącz urządzenia użytkowników należące do firmy](#enable-corporate-owned-user-devices)
4. [Zarejestruj w pełni zarządzane urządzenia](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Włączanie urządzeń użytkowników należących do firmy

1. Zaloguj się w usłudze [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierz pozycje **Rejestrowanie urządzenia** > **Rejestracja systemu Android** > **W pełni zarządzane urządzenia użytkowników należące do firmy**.
2. W obszarze **Zezwalaj użytkownikom na rejestrowanie urządzeń będących własnością firmy** wybierz pozycję **Tak**.

> [!NOTE]
> Jeśli masz zdefiniowane zasady dostępu warunkowego usługi Azure AD, które korzystają z opcji kontroli *Wymagaj, aby urządzenie zostało oznaczone jako zgodne* i dotyczą **wszystkich aplikacji w chmurze**, **systemu Android** oraz **przeglądarek** — musisz wykluczyć aplikację **Microsoft Intune** w chmurze z tych zasad. Dzieje się tak, ponieważ podczas procesów instalacji systemu Android karta przeglądarki Chrome jest używana do uwierzytelniania użytkowników podczas rejestracji. Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją dotyczącą dostępu warunkowego w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

Jeśli to ustawienie będzie miało wartość **Tak**, udostępni Ci token rejestrowania (ciąg losowy) i kod QR dla dzierżawy usługi Intune. Ten jeden token rejestracji jest ważny dla wszystkich użytkowników i nigdy nie wygasa. W zależności od systemu operacyjnego Android i wersji urządzenia możesz użyć tokenu lub kodu QR, aby zarejestrować urządzenie kiosku.

## <a name="enroll-the-fully-managed-devices"></a>Rejestrowanie w pełni zarządzanych urządzeń
Teraz możesz [zarejestrować w pełni zarządzane urządzenia](android-dedicated-devices-fully-managed-enroll.md).

## <a name="next-steps"></a>Następne kroki
- [Dodawanie zasad konfiguracji w pełni zarządzanych urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md#device-owner-only)
- [Konfigurowanie zasad konfiguracji aplikacji dla w pełni zarządzanych urządzeń z systemem Android Enterprise](app-configuration-policies-use-android.md)

