---
title: Ochrona danych za pomocą usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Poznaj sposoby, za pomocą których usługa Intune chroni urządzenia przed nieautoryzowanym dostępem i innymi zagrożeniami.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19cad6ede0f3d3fb87e067d6bdcdfa5adf0219bf
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721412"
---
# <a name="protect-devices-with-microsoft-intune"></a>Ochrona danych za pomocą usługi Microsoft Intune

Usługa Microsoft Intune pomaga chronić zarządzane urządzenia i dane przechowywane na tych urządzeniach.

## <a name="device-configuration"></a>Konfiguracja urządzenia
[Zasady konfiguracji](../configuration/device-profiles.md) usługi Intune ułatwiają ochronę i konfigurowanie urządzeń przez kontrolowanie wielu ustawień i funkcji. Przykład:

- Możesz ograniczyć użycie funkcji sprzętu na urządzeniu, takich jak funkcje aparatu lub Bluetooth.
- Możesz skonfigurować zgodne i niezgodne aplikacje. Otrzymasz alert w przypadku zainstalowania niezgodnej aplikacji (a niektóre platformy mogą faktycznie zablokować instalację).

## <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Resetowanie kodów dostępu użytkowników z zablokowanym dostępem do urządzeń
Ponieważ pierwszym środkiem ochrony danych firmy na urządzeniach przenośnych jest wymaganie stosowania kodów dostępu do urządzenia, czasami trzeba [zresetować kod dostępu](../remote-actions/device-passcode-reset.md) lub umożliwić to pracownikowi przez usunięcie kodu dostępu albo zdalne ustawienie tymczasowego kodu dostępu. Możesz również [zdalnie zablokować urządzenie](../remote-actions/device-remote-lock.md) w przypadku jego utraty lub kradzieży.

## <a name="retire-devices-and-remove-data"></a>Wycofywanie urządzeń i usuwanie danych
Gdy konieczne jest [wycofanie urządzenia z zarządzania w usłudze Intune](../remote-actions/devices-wipe.md) (na przykład użytkownik opuszcza organizację albo w przypadku utraty lub kradzieży urządzenia), prawdopodobnie będzie pożądane usunięcie danych z tego urządzenia. Usługa Intune udostępnia szereg metod w celu zapewnienia stałego bezpieczeństwa danych firmowych.

## <a name="require-devices-to-be-compliant"></a>Wymaganie zgodności urządzeń
Usługa Intune obsługuje [zasady zgodności urządzeń](device-compliance-get-started.md) umożliwiające ocenę (i w niektórych przypadkach korygowanie) urządzeń, które nie są zgodne z określonymi regułami. Można na przykład uzyskać raporty dotyczące:
- urządzeń z systemem iOS ze zdjętymi zabezpieczeniami.
- urządzeń zaszyfrowanych lub niezaszyfrowanych.
- kondycji urządzeń z systemem Windows 10 (określonej przez usługę zaświadczania o kondycji).

## <a name="protect-apps-and-the-data-they-use"></a>Ochrona aplikacji i danych, których używają
Usługa Intune zapewnia szereg funkcji pomagających chronić aplikacje i ich dane. Na przykład zasady zarządzania aplikacjami mobilnymi mogą:
- uniemożliwiać tworzenie kopii zapasowych danych z poziomu chronionej aplikacji
- ograniczać kopiowanie i wklejanie w innych aplikacjach
- wymagać kodu PIN w celu uzyskania dostępu do aplikacji. Aby uzyskać więcej informacji, zobacz [Ochrona aplikacji i danych w usłudze Microsoft Intune](../apps/app-protection-policy.md)

## <a name="add-an-additional-layer-of-protection-to-devices"></a>Dodawanie kolejnej warstwy ochrony do urządzeń
[Uwierzytelnianie wieloskładnikowe (MFA)](../enrollment/multi-factor-authentication.md) to bezpieczniejsza metoda uwierzytelniania użytkowników urządzeń w sieci.  Usługa MFA wymaga potwierdzenia tożsamości użytkownika nie tylko przy użyciu nazwy użytkownika i hasła, ale też za pośrednictwem połączenia telefonicznego lub wiadomości SMS.

## <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Sterowanie ustawieniami usługi Windows Hello for Business na urządzeniach z systemem Windows
Usługa Intune umożliwia integrację z usługą [Windows Hello for Business](windows-hello.md), czyli alternatywną metodę logowania dla systemu Windows 10 i nowszych korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej.

## <a name="bypass-activation-lock-on-ios-devices"></a>Obchodzenie blokady aktywacji na urządzeniach z systemem iOS
Blokada aktywacji to funkcja, która ułatwia ochronę urządzeń użytkowników. Ta funkcja wymaga, aby użytkownicy wprowadzali swój identyfikator Apple ID i hasło przed wymazaniem lub ponownym uaktywnieniem urządzenia. Ta funkcja może jednak prowadzić do problemów, jeśli użytkownik na przykład opuści firmę bez usunięcia blokady. [Funkcja pominięcia blokady aktywacji systemu iOS](../remote-actions/device-activation-lock-bypass.md) umożliwia usunięcie blokady z nadzorowanych urządzeń z systemem iOS, pozwalając na ich ponowne przydzielenie lub skasowanie.

## <a name="next-steps"></a>Następne kroki

Zapoznaj się z informacjami na temat usługi [Mobile Threat Defense](mobile-threat-defense.md)
