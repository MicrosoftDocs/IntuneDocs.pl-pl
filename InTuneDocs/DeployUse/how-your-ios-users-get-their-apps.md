---
title: "Jak użytkownicy systemu iOS uzyskują aplikacje | Microsoft Intune"
description: "Metody udostępniania aplikacji dla systemu iOS użytkownikom końcowym"
keywords: 
author: Staciebarker
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
ms.sourcegitcommit: 9f1946c02c6267a22844106e8f72555ec5e9cabb
ms.openlocfilehash: 212dcd31697180dae61569dda13b56704a079bf4


---


# Jak użytkownicy systemu iOS uzyskują aplikacje

Dzięki tym informacjom można zrozumieć, jak i gdzie użytkownicy końcowi uzyskują aplikacje, które rozprowadzasz przez usługę Microsoft Intune.

**Aplikacje wymagane** — aplikacje, które są wymagane przez administratora i są instalowane na urządzeniu z minimalnym udziałem użytkownika, w zależności od platformy.

**Aplikacje dostępne** — aplikacje znajdujące się na liście aplikacji w Portalu firmy, które użytkownik może opcjonalnie zainstalować.

**Aplikacje zarządzane** — aplikacje, którymi można zarządzać za pomocą zasad i które zostały „opakowane” przez usługę Intune lub utworzone przy użyciu zestawu Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tymi aplikacjami można zarządzać za pomocą usługi Intune i można w ich przypadku stosować zasady aplikacji.

**Aplikacje niezarządzane** — aplikacje, którymi można zarządzać za pomocą zasad, ale które nie zostały opakowane przez usługę Intune lub które nie zawierają zestawu Intune MAM SDK. W przypadku tych aplikacji nie można stosować zasad aplikacji.

Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu z aplikacjami, w związku z czym użytkownicy muszą korzystać z różnych widoków, aby znaleźć wszystkie swoje aplikacje. Aplikacje dla każdego z kafelków widocznych na stronie Aplikacje w aplikacji Portal firmy są dostępne w następujących lokalizacjach:

- Kafelek **Aplikacje firmowe** pozwala przejść do listy wszystkich aplikacji na karcie **WSZYSTKIE** [witryny sieci Web Portal firmy](http://portal.manage.microsoft.com).

- Kafelek **Inne aplikacje** pozwala obecnie przejść do widoku aplikacji Portal firmy zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest dozwolone zgodnie z zasadami firmy Apple. Lista obejmuje wszystkie aplikacje z wyjątkiem aplikacji biznesowych i zarządzanych pochodzących ze sklepu z aplikacjami.

- Kafelek **Kategorie** pozwala obecnie przejść do widoku aplikacji Portal firmy, w którym wyświetlana jest lista kategorii aplikacji.

    ![ios-how-to-sync-device-with-intune](./media/ios-sync-comp-portal-apps.png)


###Zobacz także
[Jak użytkownicy systemu Android uzyskują aplikacje](how-your-android-users-get-their-apps.md)</br>
[Jak użytkownicy systemu Windows uzyskują aplikacje](how-your-windows-users-get-their-apps.md)



<!--HONumber=Aug16_HO4-->


