---
title: "Jak użytkownicy systemu Android uzyskują aplikacje | Microsoft Docs"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e76e17adac581efd64a54d90b23ad52a12417593
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---


# <a name="how-your-android-users-get-their-apps"></a>Jak użytkownicy systemu Android uzyskują aplikacje

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

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
[Dodawanie aplikacji za pomocą usługi Microsoft Intune](/intune-classic/deploy-use/add-apps)

[Jak użytkownicy systemu iOS uzyskują aplikacje](how-your-ios-users-get-their-apps.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](how-your-windows-users-get-their-apps.md)

