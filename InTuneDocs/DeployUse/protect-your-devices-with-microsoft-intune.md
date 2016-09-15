---
title: "Ochrona urządzeń | Microsoft Intune"
description: "Poznaj sposoby, za pomocą których usługa Intune chroni urządzenia przed nieautoryzowanym dostępem i innymi zagrożeniami."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3e761ed60fe3df81061023aa31e0545aeeadd316
ms.openlocfilehash: be5051c46e1ef04ea140c9d440720f570edcbd1e


---

# Ochrona danych za pomocą usługi Microsoft Intune

Usługa Microsoft Intune oferuje pełny zestaw możliwości, aby pomóc w ochronie zarządzanych urządzeń i danych przechowywanych na tych urządzeniach. Ten temat zawiera podstawowe informacje o tych możliwościach i o tym, jak możesz dowiedzieć się więcej.

## Ogólne sposoby ochrony wszystkich urządzeń

### Konfiguracja urządzenia
[Zasady konfiguracji](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) usługi Intune ułatwiają ochronę i konfigurowanie urządzeń poprzez kontrolowanie wielu ustawień i funkcji. Na przykład:
- Możesz ograniczyć użycie funkcji sprzętu na urządzeniu, takich jak funkcje aparatu lub Bluetooth.
- Możesz skonfigurować zgodne i niezgodne aplikacje. Otrzymasz alert w przypadku zainstalowania niezgodnej aplikacji (a niektóre platformy mogą faktycznie zablokować instalację).

### Resetowanie kodów dostępu użytkowników z zablokowanym dostępem do urządzeń
Ponieważ pierwszym środkiem ochrony danych firmy na urządzeniach przenośnych jest wymaganie stosowania kodów dostępu do urządzenia, czasami trzeba [zresetować kod dostępu](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) lub umożliwić to pracownikowi przez usunięcie kodu dostępu albo zdalne ustawienie tymczasowego kodu dostępu. Możesz również [zdalnie zablokować urządzenie](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) w przypadku jego utraty lub kradzieży.

### Wycofywanie urządzeń i usuwanie danych
Gdy konieczne jest [wycofanie urządzenia z zarządzania w usłudze Intune](retire-devices-from-microsoft-intune-management) (na przykład użytkownik opuszcza organizację albo w przypadku utraty lub kradzieży urządzenia), prawdopodobnie będzie pożądane usunięcie danych z tego urządzenia. Usługa Intune udostępnia szereg metod w celu zapewnienia bezpieczeństwa danych firmowych.

### Wymaganie zgodności urządzeń
Usługa Intune obsługuje [zasady zgodności urządzeń](introduction-to-device-compliance-policies-in-microsoft-intune) umożliwiające ocenę (i w niektórych przypadkach korygowanie) urządzeń, które nie są zgodne z określonymi regułami. Można na przykład otrzymywać raporty o urządzeniach z systemem iOS, na których zdjęto zabezpieczenia systemu, o tym, czy urządzenia są szyfrowane, lub czy urządzenia z systemem Windows 10 są zgłaszane jako będące w dobrej kondycji przez usługę zaświadczania o kondycji.

### Ochrona aplikacji i danych, których używają
Usługa Intune zapewnia szereg funkcji pomagających chronić aplikacje i ich dane. Na przykład za pomocą zasad zarządzania aplikacjami mobilnymi (MAM) można uniemożliwić wykonywanie kopii zapasowych danych z chronionej aplikacji, ograniczyć kopiowanie i wklejanie do innych aplikacji, wymagać kodu PIN w celu uzyskania dostępu do aplikacji itp. Aby uzyskać więcej informacji o ochronie aplikacji, zobacz temat [Ochrona aplikacji i danych w usłudze Microsoft Intune](protect-apps-and-data-with-microsoft-intune).

## Dodatkowe możliwości dla urządzeń z systemem Windows

### Dodawanie kolejnej warstwy ochrony dla urządzeń z systemem Windows
[Uwierzytelnianie wieloskładnikowe (MFA)](protect-windows-devices-with-multi-factor-authentication.md) to bezpieczniejsza metoda uwierzytelniania użytkowników urządzeń z systemem Windows lub Windows Phone w sieci.  Usługa MFA wymaga potwierdzenia tożsamości użytkownika nie tylko przy użyciu nazwy użytkownika i hasła, ale też za pośrednictwem połączenia telefonicznego lub wiadomości SMS.

### Sterowanie ustawieniami usługi Windows Hello for Business na urządzeniach z systemem Windows
Usługa Intune umożliwia integrację z usługą [Windows Hello for Business](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (dawniej Microsoft Passport), czyli alternatywną metodę logowania dla systemu Windows 10 i nowszych korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej.

## Dodatkowe możliwości dla urządzeń z systemem iOS

### Obchodzenie blokady aktywacji na urządzeniach z systemem iOS
Blokada aktywacji to funkcja, która ułatwia ochronę urządzeń użytkowników. Wymaga podania identyfikatora firmy Apple i hasła przed wymazaniem lub ponownym aktywowaniem urządzenia. Jednak może to prowadzić do problemów, na przykład jeśli użytkownik opuści firmę bez usunięcia blokady. [Funkcja pominięcia blokady aktywacji systemu iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) umożliwia usunięcie blokady z nadzorowanych urządzeń z systemem iOS, pozwalając na ich ponowne przydzielenie lub skasowanie.



## Ochrona komputerów z systemem Windows zarządzanych za pomocą klienta usługi Intune
Usługa Intune w dalszym ciągu obsługuje zasady zabezpieczeń na komputerach z systemem Windows, które nie są rejestrowane, ale zarządzane przy użyciu oprogramowania klienckiego komputera z usługą Intune. Aby dowiedzieć się, jak przy użyciu tych zasad można zabezpieczyć komputery z systemem Windows, zobacz [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Ochrona komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune przy użyciu zasad).



<!--HONumber=Sep16_HO1-->


