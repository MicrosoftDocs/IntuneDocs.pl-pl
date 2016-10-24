---
title: "Jak użytkownicy systemu iOS uzyskują aplikacje | Microsoft Intune"
description: "Metody udostępniania aplikacji dla systemu iOS użytkownikom końcowym"
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 37841027c7ae040163440a19f9e163fb4eb87233
ms.openlocfilehash: ad780fb3403f6caaee1218d785a5cad326c18df5


---


# Jak użytkownicy systemu iOS uzyskują aplikacje

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune.

**Aplikacje wymagane** — aplikacje, które są wymagane przez administratora i są instalowane na urządzeniu z minimalnym udziałem użytkownika, w zależności od platformy.

**Aplikacje dostępne** — aplikacje znajdujące się na liście aplikacji w Portalu firmy, które użytkownik może opcjonalnie zainstalować.

**Aplikacje zarządzane** — aplikacje, którymi można zarządzać za pomocą zasad i które zostały „opakowane” przez usługę Intune lub utworzone przy użyciu zestawu Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tymi aplikacjami można zarządzać za pomocą usługi Intune i można w ich przypadku stosować zasady aplikacji.

**Aplikacje niezarządzane** — aplikacje, którymi można zarządzać za pomocą zasad, ale które nie zostały opakowane przez usługę Intune lub które nie zawierają zestawu Intune MAM SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu App Store. Aby obejść ten problem, kafelki w aplikacji Portal firmy działającej w systemie iOS umożliwiają przechodzenie do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich aplikacji.

- Kafelek **Aplikacje firmowe** pozwalał poprzednio przejść do listy wszystkich aplikacji na karcie WSZYSTKIE w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com). Jego działanie nie ulegnie zmianie. Nazwa kafelka została zmieniona na **Wszystkie aplikacje**.

- Kafelek **Inne aplikacje** pozwalał poprzednio przejść w ramach aplikacji Portal firmy do widoku zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest możliwe zgodnie z zasadami firmy Apple. Nazwa kafelka została zmieniona na **Polecane aplikacje**, a jego naciśnięcie spowoduje przejście na kartę POLECANE w witrynie sieci Web Portal firmy.

-  Kafelek **Kategorie** pozwalał poprzednio przejść w ramach aplikacji Portal firmy do widoku zawierającego kategorie aplikacji. Nazwa kafelka nie uległa zmianie, ale jego naciśnięcie będzie teraz powodować przejście na kartę KATEGORIE w witrynie sieci Web Portal firmy.
Zaktualizowane zrzuty ekranu możesz znaleźć w temacie [Ulepszenia w sposobie uzyskiwania aplikacji przez użytkowników końcowych systemu iOS](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).



### Zobacz także
[Jak użytkownicy systemu Android uzyskują aplikacje](how-your-android-users-get-their-apps.md)

[Jak użytkownicy systemu Windows uzyskują aplikacje](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


