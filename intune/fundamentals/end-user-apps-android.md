---
title: Jak użytkownicy systemu Android uzyskują aplikacje
description: Metody udostępniania aplikacji dla systemu Android użytkownikom końcowym
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40e8dd8409f70a70934684c56ed9e9729f4ebf0f
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414602"
---
# <a name="how-your-android-users-get-their-apps"></a>Jak użytkownicy systemu Android uzyskują aplikacje

W tym artykule wyjaśniono, jak i gdzie użytkownicy końcowi systemu Android uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune. Informacje mogą się różnić w zależności od typu urządzenia (urządzenia z natywnym systemem Android lub urządzenia z rozwiązaniem Samsung Knox Standard).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Natywne urządzenia z systemem Android (inne niż Samsung Knox Standard)

| Typ aplikacji | Aplikacje biznesowe (LOB) | Aplikacje Sklepu Play  |
| ------------- |-------------| -----|
| Aplikacje dostępne      | Użytkownicy naciskają opcję **instaluj** w portalu firmy. Pojawi się powiadomienie, które użytkownicy muszą nacisnąć, aby rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. | Użytkownicy naciskają aplikację w witrynie Portal firmy i zostają przeniesieni do strony aplikacji w Sklepie Play. Tutaj rozpoczynają instalację.|
| Required apps      | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie, aby rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie.    | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie i zostają przeniesieni do strony aplikacji w Sklepie Play. Tutaj rozpoczynają instalację. Po zakończeniu instalacji powiadomienie zniknie. |

Użytkownicy końcowi muszą zezwolić na instalację z nieznanych źródeł, aby instalować [aplikacje biznesowe](../apps/lob-apps-android.md). To ustawienie znajduje się zwykle w dwóch różnych miejscach:

* **System Android 7.1.2 i starsze**: **Ustawienia** > **Zabezpieczenia** > **Nieznane źródła**
* **System Android 8.0 i nowsze**: **Ustawienia** > **Aplikacje i powiadomienia** > **Specjalny dostęp do aplikacji** > **Zainstaluj nieznane aplikacje** > **Portal firmy** > **Zezwól z tego źródła**

W takim przypadku aplikacja Portal firmy będzie informować i bezpośrednio prowadzić użytkownika końcowego do odpowiedniego ustawienia. 

## <a name="samsung-knox-standard-android-devices"></a>Urządzenia z systemem Android Samsung Knox Standard

| Typ aplikacji | Aplikacje biznesowe (LOB) | Aplikacje Sklepu Play  |
| ------------- |-------------| -----|
| Aplikacje dostępne      | Użytkownicy naciskają opcję **instaluj** w portalu firmy. Aplikacja zostanie zainstalowana bez dalszej interwencji użytkownika. | Użytkownicy naciskają aplikację w witrynie Portal firmy i zostają przeniesieni do strony aplikacji w Sklepie Play. Tutaj rozpoczynają instalację.|
| Required apps      | Aplikacja zostanie zainstalowana bez żadnej interwencji użytkownika.    | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie i zostają przeniesieni do strony aplikacji w Sklepie Play. Tutaj rozpoczynają instalację. Po zakończeniu instalacji powiadomienie zniknie. |

Aplikacje mogą być zarządzane lub niezarządzane, zgodnie z poniższym opisem. Proces konfigurowania aplikacji jako aplikacji zarządzanych jest taki sam dla wszystkich typów urządzeń z systemem Android.

**Aplikacje zarządzane** — są to aplikacje, którymi można zarządzać za pomocą zasad. Zostały one „opakowane” przez usługę Intune lub utworzone z użyciem zestawu Intune App SDK. Tymi aplikacjami można zarządzać za pomocą usługi Intune i można w ich przypadku stosować zasady aplikacji.

**Aplikacje niezarządzane** — są to aplikacje, którymi nie można zarządzać za pomocą zasad. Nie zostały one opakowane przez usługę Intune lub nie zawierają zestawu Intune App SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

## <a name="zebra-devices-with-zebra-mobility-extensions"></a>Urządzenia Zebra z rozszerzeniami Zebra Mobility Extensions

Usługa Intune używa zestawu narzędzi Zebra Mobility Extensions (MX), aby w tle zainstalować aplikacje na urządzeniach Zebra zarządzanych przez administratora urządzeń. Ta funkcja umożliwia wdrażanie i aktualizowanie aplikacji na urządzeniach Zebra bez interwencji użytkownika. Jeśli zestaw narzędzi MX na urządzeniu jest w wersji 4.2 lub starszej, aplikacje nie są instalowane w trybie dyskretnym. Aby uzyskać więcej informacji, zobacz temat [Full MX Feature Matrix](http://techdocs.zebra.com/mx/compatibility/) (Pełna matryca funkcji zestawu narzędzi MX) w witrynie sieci Web firmy Zebra.

Aplikacje LOB wdrożone na urządzeniach Zebra muszą być zainstalowane z lokalizacji publicznej na urządzeniu. Pakiet aplikacji. apk może być dostępny dla innych aplikacji i usług, które mają również dostęp do magazynu publicznego na urządzeniu. Zwykle dostęp ten występuje w krótkim czasie między ukończeniem pobrania aplikacji i rozpoczęciem instalacji. Ten krótki czas może być okazją do ataku w czasie uaktualniania. Na przykład można wówczas zmienić pakiet .apk. Usługa Intune skraca do minimum czas, jaki usługa .apk spędza w magazynie publicznym, i nie pozwala na instalację niepodpisanych aplikacji. Aby zminimalizować ryzyko związane z bezpieczeństwem, upewnij się, że przekazywane pliki .apk nie zawierają informacji poufnych.

## <a name="see-also"></a>Zobacz także

[Dodawanie aplikacji za pomocą usługi Microsoft Intune](../apps/apps-add.md)

[Jak użytkownicy systemu iOS uzyskują aplikacje](end-user-apps-ios.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](end-user-apps-windows.md)
