---
title: Jak użytkownicy systemu iOS uzyskują aplikacje
description: Metody udostępniania aplikacji dla systemu iOS użytkownikom końcowym
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc298691ea3df923d1804005be61217325f52112
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510274"
---
# <a name="how-your-ios-users-get-their-apps"></a>Jak użytkownicy systemu iOS uzyskują aplikacje

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune.

**Aplikacje wymagane** — aplikacje, które są wymagane przez administratora i są instalowane na urządzeniu z minimalnym udziałem użytkownika, w zależności od platformy.

**Aplikacje dostępne** — aplikacje znajdujące się na liście aplikacji w Portalu firmy, które użytkownik może opcjonalnie zainstalować.

**Aplikacje zarządzane** — Aplikacje, które mogą być zarządzane za pomocą zasad i które zostały „opakowane” przez usługę Intune lub utworzone przy użyciu zestawu Intune App Software Development Kit (SDK). Tymi aplikacjami można zarządzać za pomocą usługi Intune i można do nich stosować zasady ochrony aplikacji.

**Aplikacje niezarządzane** — aplikacje, które użytkownicy mogą pobrać ze sklepu App Store systemu iOS, niezintegrowane z zestawem Intune App SDK. Usługa Intune nie kontroluje dystrybucji, selektywnego czyszczenia tych aplikacji ani zarządzania nimi.  

Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu App Store. Aby obejść ten problem, kafelki w aplikacji Portal firmy działającej w systemie iOS umożliwiają przechodzenie do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich aplikacji.

Zarejestrowani użytkownicy uzyskują aplikacje, naciskając następujące kafelki na ekranie Aplikacje w aplikacji Portal firmy:

- Kafelek **Wszystkie aplikacje** pozwala przejść do listy wszystkich aplikacji na karcie WSZYSTKIE [witryny sieci Web Portal firmy](https://portal.manage.microsoft.com).

- Kafelek **Polecane aplikacje** pozwala przejść na kartę POLECANE w witrynie sieci Web Portal firmy.

- Kafelek **Kategorie** pozwala przejść na kartę KATEGORIE w witrynie sieci Web Portal firmy.


![Ekran aplikacji Portal firmy iOS](./media/end-user-apps-ios/ios-cp-app-main-apps-screen.png)

Aby dowiedzieć się więcej o dodawaniu aplikacji, zobacz temat [Jak dodawać aplikacje do usługi Microsoft Intune](../apps/apps-add.md).

## <a name="see-also"></a>Zobacz także
[Jak użytkownicy systemu Android uzyskują aplikacje](end-user-apps-android.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](end-user-apps-windows.md)
