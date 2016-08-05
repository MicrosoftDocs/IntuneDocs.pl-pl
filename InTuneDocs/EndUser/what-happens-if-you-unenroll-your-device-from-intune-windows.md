---
title: "Co się dzieje w przypadku wyrejestrowania urządzenia z systemem Windows usługi Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 05/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: noindex,nofollow
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 80ebf1a56106ad4e66d2d791ab98edae1ab11505
ms.openlocfilehash: 0ea2148553e978deb44b8640332394a536838220


---


# Co się dzieje w przypadku wyrejestrowania urządzenia z systemem Windows usługi Intune?

Aby uzyskać dodatkowe informacje na temat zachodzących działań, użyj linku znajdującego się powyżej w sekcji „W tym artykule” odpowiedniego dla typu używanego urządzenia.

- [Windows 10 Mobile, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 lub Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows RT — system Windows 8.1 lub Windows RT](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Urządzenie nie będzie już wyświetlane w Portalu firmy i nie będzie już można instalować aplikacji z Portalu firmy.

-   W przypadku zainstalowania oprogramowania klienta usługi Intune zostanie ono usunięte z komputera.

-   Program Intune Endpoint Protection zostanie usunięty z komputera. Jeśli na komputerze jest zainstalowane inne oprogramowanie do ochrony przed wirusami, ale jest ono wyłączone, po usunięciu programu Intune Endpoint Protection będzie je można ponownie włączyć. Po usunięciu komputera z Portalu firmy należy go sprawdzić.

    > [!IMPORTANT]
    > Jeśli inne oprogramowanie ochrony przed wirusami nie zostanie ponownie włączone lub żadne inne oprogramowanie tego typu nie jest zainstalowane, komputer może być narażony na ataki wirusów i złośliwego oprogramowania.

-   Wszystkie ustawienia na urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu) nie będzie miało dłużej zastosowania.

-   Z usługi Intune komputerowi nie będą już przekazywane automatyczne aktualizacje oprogramowania ani aktualizacje oprogramowania antywirusowego. Jednak w zależności od konfiguracji komputer może nadal otrzymywać aktualizacje w ramach usług Windows Server Update Services, Windows Update lub Microsoft Update.

Ponadto w przypadku systemu Windows 8.1:

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Niektóre aplikacje poczty, np. Windows Mail, mogą utracić dostęp do firmowej poczty e-mail przechowywanej na urządzeniu.

-   Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

-   Użytkownik może utracić dostęp za pośrednictwem urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

## Windows 10 Mobile, Windows Phone 8.1 lub Windows Phone 8

-   Aplikacja Portal firmy zostanie odinstalowana z urządzenia, co oznacza, że urządzenie nie będzie dłużej wyświetlane w Portalu firmy, a użytkownik nie będzie mógł instalować aplikacji z Portalu firmy lub witryny sieci Web Portal firmy.

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go, np. wyłączenie aparatu lub wymaganie hasła o określonej długości, nie będą miały dłużej zastosowania.

    > [!IMPORTANT]
    > Jedynym wyjątkiem są zasady szyfrowania, które nadal będą stosowane. Jeśli urządzenie z systemem Windows Phone zostało zaszyfrowane zgodnie z wymaganiami nakładanymi przez zasady firmy, jedynym sposobem na jego odszyfrowanie jest jego zresetowanie w menu **Ustawienia** w systemie Windows Phone.

## Windows RT — system Windows 8.1 lub Windows RT

-   Aplikacja Portal firmy zostanie odinstalowana z urządzenia, co oznacza, że urządzenie nie będzie dłużej wyświetlane w Portalu firmy i nie będzie można instalować aplikacji z Portalu firmy.

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go, np. wyłączenie aparatu lub wymaganie hasła o określonej długości, nie będą miały dłużej zastosowania.

-   Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

-   Użytkownik może utracić dostęp za pośrednictwem urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

-   Niektóre aplikacje poczty, np. Windows Mail, mogą utracić dostęp do firmowej poczty e-mail przechowywanej na urządzeniu.

Usunięcie urządzenia z systemem Windows RT wywoła następujące konsekwencje:

-   Aplikacja Portal firmy zostanie odinstalowana z urządzenia, co oznacza, że urządzenie nie będzie dłużej wyświetlane w Portalu firmy i nie będzie można instalować aplikacji z Portalu firmy.

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go, np. wyłączenie aparatu lub wymaganie hasła o określonej długości, nie będą miały dłużej zastosowania.

Jeśli masz pytania, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

### Zobacz także
[Korzystanie z urządzenia z systemem Windows i usługi Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO1-->


