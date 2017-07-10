---
title: "Jak użytkownicy systemu Android uzyskują aplikacje"
description: "Metody udostępniania aplikacji dla systemu Android użytkownikom końcowym"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4f0364750edf2e97e2b621c27fb25bea8e0f537c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="how-your-android-users-get-their-apps"></a>Jak użytkownicy systemu Android uzyskują aplikacje

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi systemu Android uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune. Informacje mogą się różnić w zależności od typu urządzenia (urządzenia z natywnym systemem Android lub urządzenia z rozwiązaniem Samsung Knox Standard).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Natywne urządzenia z systemem Android (inne niż Samsung Knox Standard)

| Typ aplikacji | Aplikacje biznesowe (LOB) | Aplikacje Sklepu Play  |
| ------------- |-------------| -----|
| Aplikacje dostępne      | Użytkownicy naciskają opcję **instaluj** w portalu firmy. Pojawi się powiadomienie, które użytkownicy muszą nacisnąć, aby rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. | Użytkownicy naciskają aplikację w portalu firmy i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację.|
| Required apps      | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie, aby rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie.    | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. |

## <a name="samsung-knox-standard-android-devices"></a>Urządzenia z systemem Android Samsung Knox Standard

| Typ aplikacji | Aplikacje biznesowe (LOB) | Aplikacje Sklepu Play  |
| ------------- |-------------| -----|
| Aplikacje dostępne      | Użytkownicy naciskają opcję **instaluj** w portalu firmy. Aplikacja zostanie zainstalowana bez dalszej interwencji użytkownika. | Użytkownicy naciskają aplikację w portalu firmy i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację.|
| Required apps      | Aplikacja zostanie zainstalowana bez żadnej interwencji użytkownika.    | Użytkownicy otrzymują powiadomienie, którego nie można odrzucić, wskazujące, że powinni zainstalować aplikację. Użytkownicy naciskają powiadomienie i zostają przeniesieni do strony aplikacji w Sklepie Play, skąd mogą rozpocząć instalację. Po zakończeniu instalacji powiadomienie zniknie. |

Aplikacje mogą być zarządzane lub niezarządzane, zgodnie z poniższym opisem. Proces konfigurowania aplikacji jako aplikacji zarządzanych jest taki sam dla wszystkich typów urządzeń z systemem Android.

**Aplikacje zarządzane** — są to aplikacje, którymi można zarządzać za pomocą zasad. Zostały one „opakowane” w usłudze Intune lub skompilowane przy użyciu zestawu Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tymi aplikacjami można zarządzać za pomocą usługi Intune i można w ich przypadku stosować zasady aplikacji.

**Aplikacje niezarządzane** — są to aplikacje, którymi nie można zarządzać za pomocą zasad. Nie zostały one opakowane w usłudze Intune lub nie zawierają zestawu Intune MAM SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

### <a name="see-also"></a>Zobacz też
[Dodawanie aplikacji za pomocą usługi Microsoft Intune](apps-add.md)

[Jak użytkownicy systemu iOS uzyskują aplikacje](end-user-apps-ios.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](end-user-apps-windows.md)
