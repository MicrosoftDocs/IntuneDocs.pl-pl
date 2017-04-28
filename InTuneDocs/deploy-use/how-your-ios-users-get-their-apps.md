---
title: "Jak użytkownicy systemu iOS uzyskują aplikacje | Microsoft Docs"
description: "Metody udostępniania aplikacji dla systemu iOS użytkownikom końcowym"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 02e54d4ae2ffa860fb95725c74fdff913e88365b
ms.lasthandoff: 04/24/2017


---


# <a name="how-your-ios-users-get-their-apps"></a>Jak użytkownicy systemu iOS uzyskują aplikacje

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune.

**Aplikacje wymagane** — aplikacje, które są wymagane przez administratora i są instalowane na urządzeniu z minimalnym udziałem użytkownika, w zależności od platformy.

**Aplikacje dostępne** — aplikacje znajdujące się na liście aplikacji w Portalu firmy, które użytkownik może opcjonalnie zainstalować.

**Aplikacje zarządzane** — aplikacje, którymi można zarządzać za pomocą zasad i które zostały „opakowane” przez usługę Intune lub utworzone przy użyciu zestawu Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tymi aplikacjami można zarządzać za pomocą usługi Intune i można w ich przypadku stosować zasady aplikacji.

**Aplikacje niezarządzane** — aplikacje, którymi można zarządzać za pomocą zasad, ale które nie zostały opakowane przez usługę Intune lub które nie zawierają zestawu Intune MAM SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu App Store. Aby obejść ten problem, kafelki w aplikacji Portal firmy działającej w systemie iOS umożliwiają przechodzenie do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich aplikacji.

Zarejestrowani użytkownicy uzyskują aplikacje, naciskając następujące kafelki na ekranie Aplikacje w aplikacji Portal firmy:

- Kafelek **Wszystkie aplikacje** pozwala przejść do listy wszystkich aplikacji na karcie WSZYSTKIE [witryny sieci Web Portal firmy](https://portal.manage.microsoft.com).

- Kafelek **Polecane aplikacje** pozwala przejść na kartę POLECANE w witrynie sieci Web Portal firmy.

- Kafelek **Kategorie** pozwala przejść na kartę KATEGORIE w witrynie sieci Web Portal firmy.


![Ekran aplikacji Portal firmy iOS](./media/ios-cp-app-main-apps-screen.png)

Aby uzyskać informacje dotyczące sposobu dodawania aplikacji i umieszczania ich w tych kafelkach, zobacz [Dodawanie aplikacji dla zarejestrowanych urządzeń do usługi Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Zobacz też
[Jak użytkownicy systemu Android uzyskują aplikacje](how-your-android-users-get-their-apps.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](how-your-windows-users-get-their-apps.md)

