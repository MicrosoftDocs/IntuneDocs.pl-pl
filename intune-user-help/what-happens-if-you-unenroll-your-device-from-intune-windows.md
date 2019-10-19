---
title: Co się dzieje w przypadku wyrejestrowania urządzenia z systemem Windows? | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6e3f61fc84458525ae2ff62887d64baea9542
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505945"
---
# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a>Co się dzieje w przypadku wyrejestrowania urządzenia z systemem Windows usługi Intune?

Użyj linków po prawej stronie w obszarze **W tym artykule**, aby wyszukać informacje dotyczące rodzaju urządzenia, z którego korzystasz.


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a>Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista

- Urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z Portalu firmy.

- W przypadku zainstalowania oprogramowania klienta usługi Intune zostanie ono usunięte z komputera.

- Program Intune Endpoint Protection zostanie usunięty z komputera. Jeśli na komputerze jest zainstalowane inne oprogramowanie do ochrony przed wirusami, ale jest ono wyłączone, po usunięciu programu Intune Endpoint Protection będzie je można ponownie włączyć. Po usunięciu komputera z Portalu firmy należy go sprawdzić.

    > [!IMPORTANT]
    > Jeśli inne oprogramowanie ochrony przed wirusami nie zostanie ponownie włączone lub żadne inne oprogramowanie tego typu nie jest zainstalowane, komputer może być narażony na ataki wirusów i złośliwego oprogramowania.

- Wszystkie ustawienia zmienione na urządzeniu podczas dodawania go (np. wyłączenie aparatu) nie mają już zastosowania.

- Z usługi Intune komputerowi nie są już przekazywane automatyczne aktualizacje oprogramowania ani aktualizacje oprogramowania antywirusowego. Jednak, w zależności od konfiguracji, komputer może nadal otrzymywać aktualizacje w ramach usług Windows Server Update Services, Windows Update lub Microsoft Update.

Ponadto w przypadku systemu Windows 8.1:

- Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

- Niektóre aplikacje pocztowe, np. Windows Mail, mogą utracić dostęp do firmowej poczty e-mail przechowywanej na urządzeniu.

- Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

- Możesz utracić dostęp z urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

## <a name="windows-10-mobile-and-windows-phone-81"></a>Systemy Windows 10 Mobile i Windows Phone 8.1

- Aplikacja Portal firmy jest odinstalowywana z tego urządzenia. To znaczy, że urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z poziomu aplikacji Portal firmy ani witryny sieci Web Portal firmy.

- Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

- Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.

    > [!IMPORTANT]
    > Jedynym wyjątkiem są zasady szyfrowania, które nadal są stosowane. Jeśli zgodnie z zasadami firmy urządzenie z systemem Windows Phone zostało zaszyfrowane, jedynym sposobem na jego odszyfrowanie jest jego zresetowanie przy użyciu menu **Ustawienia**.

## <a name="windows-rt-running-windows-81"></a>Windows RT — system Windows 8.1

- Aplikacja Portal firmy jest odinstalowywana z tego urządzenia. To znaczy, że urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z Portalu firmy.

- Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

- Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.

- Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

- Możesz utracić dostęp z urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

- Niektóre aplikacje pocztowe, np. Windows Mail, mogą utracić dostęp do firmowej poczty e-mail przechowywanej na urządzeniu.

Usunięcie urządzenia z systemem Windows RT wywoła następujące konsekwencje:

- Aplikacja Portal firmy jest odinstalowywana z tego urządzenia. To znaczy, że urządzenie nie jest już wyświetlane w Portalu firmy i nie możesz już instalować aplikacji z Portalu firmy.

- Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

- Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.

Jeśli masz pytania, skontaktuj się z działem pomocy technicznej Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
