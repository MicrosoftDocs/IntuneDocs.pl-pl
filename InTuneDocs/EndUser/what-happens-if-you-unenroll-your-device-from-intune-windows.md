---
title: "Co się dzieje w przypadku wyrejestrowania urządzenia z systemem Windows usługi Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8975e57c604565c57c86472564ab660aed560a7b
ms.openlocfilehash: 22179d5d80d2b24e61778249367bec6845290206


---


# Co się dzieje w przypadku wyrejestrowania urządzenia z systemem Windows usługi Intune?

Użyj linków po prawej stronie w obszarze **W tym artykule**, aby wyszukać informacje dotyczące rodzaju urządzenia, z którego korzystasz.


## Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista

-   Urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z Portalu firmy.

-   W przypadku zainstalowania oprogramowania klienta usługi Intune zostanie ono usunięte z komputera.

-   Program Intune Endpoint Protection zostanie usunięty z komputera. Jeśli na komputerze jest zainstalowane inne oprogramowanie do ochrony przed wirusami, ale jest ono wyłączone, po usunięciu programu Intune Endpoint Protection będzie je można ponownie włączyć. Po usunięciu komputera z Portalu firmy należy go sprawdzić.

    > [!IMPORTANT]
    > Jeśli inne oprogramowanie ochrony przed wirusami nie zostanie ponownie włączone lub żadne inne oprogramowanie tego typu nie jest zainstalowane, komputer może być narażony na ataki wirusów i złośliwego oprogramowania.

-   Wszystkie ustawienia zmienione na urządzeniu podczas dodawania go (np. wyłączenie aparatu) nie mają już zastosowania.

-   Z usługi Intune komputerowi nie są już przekazywane automatyczne aktualizacje oprogramowania ani aktualizacje oprogramowania antywirusowego. Jednak, w zależności od konfiguracji, komputer może nadal otrzymywać aktualizacje w ramach usług Windows Server Update Services, Windows Update lub Microsoft Update.

Ponadto w przypadku systemu Windows 8.1:

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Niektóre aplikacje pocztowe, np. Windows Mail, mogą utracić dostęp do firmowej poczty e-mail przechowywanej na urządzeniu.

-   Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

-   Możesz utracić dostęp z urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

## Systemy Windows 10 Mobile i Windows Phone 8.1

-   Aplikacja Portal firmy jest odinstalowywana z tego urządzenia. To znaczy, że urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z poziomu aplikacji Portal firmy ani witryny sieci Web Portal firmy.

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.

    > [!IMPORTANT]
    > Jedynym wyjątkiem są zasady szyfrowania, które nadal są stosowane. Jeśli zgodnie z zasadami firmy urządzenie z systemem Windows Phone zostało zaszyfrowane, jedynym sposobem na jego odszyfrowanie jest jego zresetowanie przy użyciu menu **Ustawienia**.

## Windows RT — system Windows 8.1

-   Aplikacja Portal firmy jest odinstalowywana z tego urządzenia. To znaczy, że urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z Portalu firmy.

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.

-   Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

-   Możesz utracić dostęp z urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

-   Niektóre aplikacje pocztowe, np. Windows Mail, mogą utracić dostęp do firmowej poczty e-mail przechowywanej na urządzeniu.

Usunięcie urządzenia z systemem Windows RT wywoła następujące konsekwencje:

-   Aplikacja Portal firmy jest odinstalowywana z tego urządzenia. To znaczy, że urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z Portalu firmy.

-   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

-   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.

Jeśli masz pytania, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO3-->


