---
title: Jak użytkownicy systemu Android uzyskują aplikacje
description: Metody udostępniania aplikacji dla systemu Android użytkownikom końcowym
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 878e4d0854722d82eab0545cf3a1ba743f2c52db
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="how-your-android-users-get-their-apps"></a>Jak użytkownicy systemu Android uzyskują aplikacje

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi systemu Android uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune. Informacje mogą się różnić w zależności od typu urządzenia (urządzenia z natywnym systemem Android lub urządzenia z rozwiązaniem Samsung Knox Standard).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Natywne urządzenia z systemem Android (inne niż Samsung Knox Standard)

| Typ aplikacji | Aplikacje biznesowe (LOB) | Aplikacje Sklepu Play  |
| ------------- |-------------| -----|
| Aplikacje dostępne      | Użytkownicy naciskają opcję **instaluj** w portalu firmy. Pojawi się powiadomienie, które użytkownicy muszą nacisnąć, aby rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. | Użytkownicy naciskają aplikację w portalu firmy i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację.|
| Required apps      | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie, aby rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie.    | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. |

Użytkownicy końcowi muszą zezwolić na instalację z nieznanych źródeł, aby instalować [aplikacje biznesowe](lob-apps-android.md). Znajdują się one zwykle znajdują się w dwóch różnych miejscach:

* **System Android 7.1.2 i starsze**: **Ustawienia** > **Zabezpieczenia** > **Nieznane źródła**
* **System Android 8.0 i nowsze**: **Ustawienia** > **Aplikacje i powiadomienia** > **Specjalny dostęp do aplikacji** > **Zainstaluj nieznane aplikacje** > **Portal firmy** > **Zezwól z tego źródła**

W takim przypadku aplikacja Portal firmy będzie informować i bezpośrednio prowadzić użytkownika końcowego do odpowiedniego ustawienia. 


## <a name="samsung-knox-standard-android-devices"></a>Urządzenia z systemem Android Samsung Knox Standard

| Typ aplikacji | Aplikacje biznesowe (LOB) | Aplikacje Sklepu Play  |
| ------------- |-------------| -----|
| Aplikacje dostępne      | Użytkownicy naciskają opcję **instaluj** w portalu firmy. Aplikacja zostanie zainstalowana bez dalszej interwencji użytkownika. | Użytkownicy naciskają aplikację w portalu firmy i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację.|
| Required apps      | Aplikacja zostanie zainstalowana bez żadnej interwencji użytkownika.    | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. |

Aplikacje mogą być zarządzane lub niezarządzane, zgodnie z poniższym opisem. Proces konfigurowania aplikacji jako aplikacji zarządzanych jest taki sam dla wszystkich typów urządzeń z systemem Android.

**Aplikacje zarządzane** — są to aplikacje, którymi można zarządzać za pomocą zasad. Zostały one „opakowane” przez usługę Intune lub utworzone z użyciem zestawu Intune App SDK. Tymi aplikacjami można zarządzać za pomocą usługi Intune i można w ich przypadku stosować zasady aplikacji.

**Aplikacje niezarządzane** — są to aplikacje, którymi nie można zarządzać za pomocą zasad. Nie zostały one opakowane przez usługę Intune lub nie zawierają zestawu Intune App SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

### <a name="see-also"></a>Zobacz też
[Dodawanie aplikacji za pomocą usługi Microsoft Intune](apps-add.md)

[Jak użytkownicy systemu iOS uzyskują aplikacje](end-user-apps-ios.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](end-user-apps-windows.md)
