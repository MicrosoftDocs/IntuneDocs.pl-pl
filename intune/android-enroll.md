---
title: Rejestrowanie urządzeń z systemem Android w usłudze Intune
titlesuffix: Microsoft Intune
description: Informacje o sposobie rejestrowania urządzeń z systemem Android w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b7652c8c4f471a0a0c32da23d8ac1859e84eb13
ms.sourcegitcommit: e8aaa0955d13fa6c9d5f35a730ad06509ce88d0b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2018
ms.locfileid: "39400355"
---
# <a name="enroll-android-devices"></a>Rejestrowanie urządzeń z systemem Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz zarządzać następującymi urządzeniami z systemem Android:
- Urządzenia z systemem Android, w tym urządzenia z systemem Samsung Knox Standard.
- Urządzenia z rozwiązaniem Android enterprise, w tym [urządzenia z profilem służbowym Android](#enable-enrollment-of-android-for-work-devices) i urządzenia kiosku z systemem Android.

Urządzenia z systemem Samsung Knox Standard są obsługiwane w przypadku zarządzania wieloma użytkownikami za pomocą usługi Intune. Oznacza to, że użytkownicy mogą zalogować się na urządzeniu i wylogować się z niego przy użyciu swoich poświadczeń usługi Azure AD. Urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane. Po zalogowaniu się użytkownicy otrzymują dostęp do aplikacji oraz zostają wobec nich zastosowane zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

## <a name="prerequisite"></a>Wymaganie wstępne

Aby przygotować się do zarządzania urządzeniami przenośnymi, należy ustawić urząd zarządzania urządzeniami przenośnymi (MDM) na wartość **Microsoft Intune**. Instrukcje znajdują się w artykule [Set the MDM authority](mdm-authority-set.md) (Ustawianie urzędu MDM). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.

## <a name="set-up-android-enrollment"></a>Konfiguracja rejestrowania urządzeń z systemem Android

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem Android i Samsung Knox Standard. Po spełnieniu wymagań wstępnych administratorzy muszą jedynie [poinformować użytkowników o tym, jak mogą zarejestrować swoje urządzenia](/intune-user-help/enroll-your-device-in-intune-android).

Po wykonaniu rejestracji przez użytkownika można zacząć zarządzać jego urządzeniami w usłudze Intune, w tym [przypisywać zasady zgodności](compliance-policy-create-android.md), [zarządzać aplikacjami](app-management.md) i nie tylko.

Aby uzyskać informacje o innych zadaniach użytkowników, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Aby zablokować rejestrowanie urządzeń z systemem Android lub tylko urządzeń z systemem Android będących własnością użytkowników, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

## <a name="set-up-android-enterprise-enrollment"></a>Konfigurowanie rejestracji rozwiązania Android enterprise

Android enterprise to zestaw funkcji i usług dostępnych na urządzeniach z systemem Android, które oddzielają osobiste aplikacje i dane od profilu służbowego zawierającego służbowe aplikacje i dane. Urządzenia z rozwiązaniem Android enterprise obejmują urządzenia z profilem służbowym i kioski. 

Aby skonfigurować rejestrację urządzeń z rozwiązaniem Android enterprise, należy najpierw [połączyć rozwiązanie Android enterprise z usługą Intune](connect-intune-android-enterprise.md). Po ukończeniu tego kroku można wykonać następujące czynności:

[Konfigurowanie rejestracji profilu służbowego systemu Android](android-work-profile-enroll.md)
[Konfigurowanie rejestracji kiosków z systemem Android](android-kiosk-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Środowisko użytkownika końcowego podczas rejestrowania urządzenia z rozwiązaniem Samsung Knox
Podczas rejestrowania urządzeń z rozwiązaniem Samsung Knox należy uwzględnić kilka zagadnień:
-   Nawet jeśli żadne zasady nie wymagają numeru PIN, urządzenie musi mieć co najmniej czterocyfrowy numer PIN, aby można było je zarejestrować. Jeśli urządzenie nie ma numeru PIN, dla użytkownika zostanie wyświetlony monit z żądaniem jego utworzenia.
-   Nie ma żadnych interakcji użytkownika dla certyfikatów WPJ (Workplace Join Certificate).
-   Monit zawiera informacje o rejestracji w usłudze i możliwościach aplikacji.
-   Monit zawiera informacje o rejestracji urządzenia z rozwiązaniem Knox i o możliwościach rozwiązania Knox.
-   Jeśli zasady szyfrowania są wymuszane, użytkownicy muszą ustawić sześcioznakowe hasło złożone jako kod dostępu urządzenia.
-   Nie są wyświetlane żadne dodatkowe monity dotyczące instalowania certyfikatów wypchniętych przez usługę na potrzeby dostępu do zasobów firmy.
- Niektóre starsze urządzenia z rozwiązaniem Knox monitują użytkownika w związku z dodatkowymi certyfikatami używanymi na potrzeby dostępu do zasobów firmy.
- Jeśli instalowanie certyfikatu WPJ na urządzeniu Samsung Mini nie powiedzie się z błędem **Nie znaleziono certyfikatu** lub **Nie można zarejestrować urządzenia**, zainstaluj najnowsze aktualizacje oprogramowania układowego firmy Samsung.
