---
title: Konfiguracja rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android
titlesuffix: Microsoft Intune
description: Dowiedz się, jak rejestrować w pełni zarządzane urządzenia z systemem Android w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 482ae185f221b3ff77534c1cfd8cccd8278965b7
ms.sourcegitcommit: 84ab7a49aad853591a4ae362382f293e29b360df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2019
ms.locfileid: "56156172"
---
# <a name="set-up-intune-enrollment-of-android-fully-managed-devices-preview"></a>Konfiguracja rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android (wersja zapoznawcza)

W pełni zarządzane urządzenia z systemem Android to urządzenia należące do firmy skojarzone z jednym użytkownikiem i wykorzystywane wyłącznie do pracy, a nie do celów osobistych. Administratorzy mogą zarządzać całym urządzeniem i wymuszać kontrolki zasad niedostępne dla profilów służbowych, takie jak:
- zezwalanie na instalowanie aplikacji tylko z zarządzanego sklepu Google Play,
- blokowanie dezinstalacji aplikacji zarządzanych,
- uniemożliwianie użytkownikom przywracania ustawień fabrycznych urządzenia i tak dalej.

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na urządzeniach z rozwiązaniem Android enterprise, w tym na w pełni zarządzanych urządzeniach z systemem Android. Aby uzyskać szczegółowe informacje na temat rozwiązania Android enterprise, zobacz [wymagania dotyczące rozwiązania Android enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Wymagania techniczne

Do zarządzania w pełni zarządzanymi urządzeniami z systemem Android niezbędna jest autonomiczna dzierżawa usługi Intune. Zarządzanie w pełni zarządzanymi urządzeniami nie jest dostępne w trybie hybrydowym (połączenie programu SCCM) ani w starszej konsoli zarządzania programu Silverlight.

Urządzenia muszą spełniać następujące wymagania, aby mogły być zarządzane jako w pełni zarządzane urządzenia z systemem Android:

- System operacyjny Android w wersji 5.1 lub nowszy.
- Na urządzeniach musi działać kompilacja systemu Android obsługująca łączność z usługami Google Mobile Services (GMS). Urządzenia muszą mieć dostępne usługi GMS i muszą być w stanie połączyć się z usługami GMS.

Jeśli powyższe wymagania są spełnione, nie ma żadnych ograniczeń dotyczących producenta urządzenia/producenta OEM.

## <a name="set-up-android-fully-managed-device-management"></a>Konfigurowanie zarządzania w pełni zarządzanymi urządzeniami z systemem Android

Aby skonfigurować zarządzanie w pełni zarządzanymi urządzeniami z systemem Android, wykonaj następujące kroki:

1. Aby przygotować się do zarządzania urządzeniami przenośnymi, należy [ustawić urząd zarządzania urządzeniami przenośnymi (MDM) na wartość **Microsoft Intune**](mdm-authority-set.md). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.
2. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android enterprise](connect-intune-android-enterprise.md).
3. [Włącz urządzenia użytkowników należące do firmy](#enable-corporate-owned-user-devices)
4. [Zarejestruj w pełni zarządzane urządzenia](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Włączanie urządzeń użytkowników należących do firmy

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Rejestracja urządzeń** > **Rejestracja systemu Android** > **W pełni zarządzane urządzenia użytkowników należące do firmy (wersja zapoznawcza)**.
2. W obszarze **Zezwalaj użytkownikom na rejestrowanie urządzeń będących własnością firmy** wybierz pozycję **Tak**.

Jeśli to ustawienie będzie miało wartość **Tak**, udostępni Ci token rejestrowania (ciąg losowy) i kod QR dla dzierżawy usługi Intune. Ten jeden token rejestracji jest ważny dla wszystkich użytkowników i nigdy nie wygasa. W zależności od systemu operacyjnego Android i wersji urządzenia możesz użyć tokenu lub kodu QR, aby zarejestrować urządzenie kiosku.

## <a name="enroll-the-fully-managed-devices"></a>Rejestrowanie w pełni zarządzanych urządzeń
Teraz możesz [zarejestrować w pełni zarządzane urządzenia](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Zagadnienia dotyczące tej funkcji w wersji zapoznawczej
Ta publiczna wersja zapoznawcza zawiera podstawowy zestaw funkcji dla w pełni zarządzanego zestawu rozwiązań systemu Android. Chcemy poznać Twoją opinię na temat korzystania z funkcji w wersji zapoznawczej. Możesz ją przesłać przy użyciu dowolnego kanału komunikacji z zespołem (na przykład za pomocą witryny [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Ta wersja zapoznawcza obsługuje następujące funkcje dla w pełni zarządzanych urządzeń z systemem Android:
- Rejestrowanie urządzeń przy użyciu funkcji NFC, wpisu tokenu, kodu QR i funkcji Zero Touch
- Konfiguracja urządzeń dla grup użytkowników
- Dystrybucja i konfiguracja aplikacji dla grup użytkowników


Korzystając z tych funkcji w wersji zapoznawczej, należy pamiętać o następujących kwestiach:
- Funkcje w wersji zapoznawczej nie są zalecane w przypadku wdrożeń o znaczeniu krytycznym lub wdrożeń produkcyjnych. 
- Funkcje w wersji zapoznawczej są implementowane z zachowaniem standardów produkcyjnych usługi Microsoft Intune. Jednak nie wszystkie funkcje usługi Intune są dostępne do użytku na w pełni zarządzanych urządzeniach użytkowników z systemem Android. Funkcje w wersji zapoznawczej są wyraźnie oznaczone etykietą „(wersja zapoznawcza)” w konsoli usługi Intune. 
- Funkcje w wersji zapoznawczej są w pełni obsługiwane za pośrednictwem zwykłych kanałów pomocy technicznej usługi Intune.
- Rejestracja w pełni zarządzanych urządzeń z systemem Android przy użyciu programu Samsung Knox Mobile Enrollment nie jest obsługiwana w wersji zapoznawczej. 
- Korzystanie z aplikacji Portal firmy usługi Intune nie jest obsługiwane na w pełni zarządzanych urządzeniach z systemem Android. 
- Funkcje usługi Intune, takie jak dostęp warunkowy, zasady ochrony aplikacji i wdrażanie certyfikatu, nie są obsługiwane w wersji zapoznawczej. 
- Określanie celu grupy urządzeń dla dowolnego profilu bądź aplikacji nie jest obsługiwane w wersji zapoznawczej. Obsługiwane jest tylko określanie celu grupy użytkowników. 
- Nie ma interfejsu użytkownika pierwszej klasy dla konfigurowania poczty e-mail, sieci Wi-Fi lub sieci VPN. Aby skonfigurować obsługiwane ustawienia konfiguracji aplikacji, użyj zasad konfiguracji aplikacji.

## <a name="next-steps"></a>Następne kroki
- [Dodawanie zasad konfiguracji w pełni zarządzanych urządzeń z systemem Android](device-restrictions-android-for-work.md#device-owner-only)
- [Konfigurowanie zasad konfiguracji aplikacji dla w pełni zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md)

