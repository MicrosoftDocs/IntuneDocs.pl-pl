---
title: "Jak użytkownicy systemu iOS uzyskują aplikacje"
description: "Metody udostępniania aplikacji dla systemu iOS użytkownikom końcowym"
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31bb6cf7d118e121a5a8d8a74f92c2b3cf5da7bc
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="how-your-ios-users-get-their-apps"></a>Jak użytkownicy systemu iOS uzyskują aplikacje

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune.

**Aplikacje wymagane** — aplikacje, które są wymagane przez administratora i są instalowane na urządzeniu z minimalnym udziałem użytkownika, w zależności od platformy.

**Aplikacje dostępne** — aplikacje znajdujące się na liście aplikacji w Portalu firmy, które użytkownik może opcjonalnie zainstalować.

**Aplikacje zarządzane** — Aplikacje, które mogą być zarządzane za pomocą zasad i które zostały „opakowane” przez usługę Intune lub utworzone przy użyciu zestawu Intune App Software Development Kit (SDK). Tymi aplikacjami można zarządzać za pomocą usługi Intune i można do nich stosować zasady ochrony aplikacji.

**Aplikacje niezarządzane** — aplikacje, którymi można zarządzać za pomocą zasad, ale które nie zostały opakowane przez usługę Intune lub które nie zawierają zestawu Intune App SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu App Store. Aby obejść ten problem, kafelki w aplikacji Portal firmy działającej w systemie iOS umożliwiają przechodzenie do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich aplikacji.

Zarejestrowani użytkownicy uzyskują aplikacje, naciskając następujące kafelki na ekranie Aplikacje w aplikacji Portal firmy:

- Kafelek **Wszystkie aplikacje** pozwala przejść do listy wszystkich aplikacji na karcie WSZYSTKIE [witryny sieci Web Portal firmy](https://portal.manage.microsoft.com).

- Kafelek **Polecane aplikacje** pozwala przejść na kartę POLECANE w witrynie sieci Web Portal firmy.

- Kafelek **Kategorie** pozwala przejść na kartę KATEGORIE w witrynie sieci Web Portal firmy.


![Ekran aplikacji Portal firmy iOS](./media/ios-cp-app-main-apps-screen.png)

Aby uzyskać informacje dotyczące sposobu dodawania aplikacji i umieszczania ich w tych kafelkach, zobacz [Dodawanie aplikacji dla zarejestrowanych urządzeń do usługi Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Zobacz też
[Jak użytkownicy systemu Android uzyskują aplikacje](end-user-apps-android.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](end-user-apps-windows.md)
