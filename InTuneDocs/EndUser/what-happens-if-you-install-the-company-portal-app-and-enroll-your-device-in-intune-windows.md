---
title: "Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4881d765a6a79d380ab6d3facdb55d9f0c81bf97
ms.openlocfilehash: ac4fdc73122fb5dc82771f174d9bd783c186bf9d


---


# Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune?

Podczas instalowania aplikacji Portal firmy, a następnie używania jej do zarejestrowania urządzenia z systemem Windows lub Windows Phone, pozwalasz administratorowi IT na zarządzanie urządzeniem, aby zachować bezpieczeństwo danych służbowych, zgodnie z poniższym opisem dla urządzeń z systemem wcześniejszym niż Windows 10. Opis dotyczący urządzeń z systemem Windows 10 znajduje się na [tej stronie](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Co się dzieje na wszystkich urządzeniach z systemem Windows po rejestracji
Zarejestrowanie urządzenia z systemem Windows lub Windows Phone w usłudze Intune pozwala:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych

-   Pobierać aplikacje firmowe z witryny internetowej Portal firmy (dla systemów Windows 7 i Vista można pobierać aplikacje firmowe tylko z witryny sieci Web Portal firmy)

-   Automatycznie konfigurować służbowe konto e-mail

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży

Zarejestrowanie urządzenia spowoduje nadanie administratorowi IT uprawnień, które pozwalają mu:

-   Resetować urządzenie do domyślnych ustawień fabrycznych. Jest to przydatne w przypadku utracenia lub kradzieży urządzenia.

-   Usuwać tylko pliki związane z firmą i aplikacje biznesowe. **Dane osobowe oraz ustawienia użytkownika nie zostaną usunięte.**

-   Administrator IT będzie widzieć oprogramowanie zainstalowane na urządzeniu, włącznie z oprogramowaniem zainstalowanym przez Ciebie.

-   Ustawiać na Twoim urządzeniu wymagania, takie jak wymaganie ustawienia hasła lub numeru PIN urządzenia, aby chronić dane firmy. Administrator IT może także ograniczać to, ile razy można wprowadzić niepoprawne hasło, i może zablokować Ci dostęp do urządzenia, jeśli spróbujesz zbyt wiele razy.

-   Wymagać od Ciebie szyfrowania danych na urządzeniu, aby chronić dane firmy na wypadek utraty lub kradzieży urządzenia. 

-   Wymagać od użytkownika zaakceptowania postanowień.

-   Uniemożliwić robienie zdjęć danym związanym z firmą.

## Co się dzieje na wszystkich komputerach z systemem Windows po rejestracji

-  Na komputerze zostanie zainstalowane oprogramowanie umożliwiające administratorowi IT zarządzanie komputerem oraz pozwalające użytkownikowi na uzyskanie dostępu do zasobów firmy, takich jak aplikacje czy informacje pomocy technicznej. Administrator IT może automatycznie aktualizować to oprogramowanie.

-  Na komputerze można zainstalować program Intune Endpoint Protection. To oprogramowanie, które wyszukuje wirusy i złośliwe oprogramowanie.

-  Administrator IT może zbierać lub usuwać dane z dysku twardego komputera.

-  Administrator IT może instalować na komputerze aplikacje i aktualizacje.

## Co się dzieje co 8 godzin po rejestracji urządzenia
Mniej więcej co 8 godzin zarejestrowane urządzenia wykonują następujące czynności:

-   Pobieranie wszystkich aktualizacji aplikacji lub zasad udostępnionych przez administratora IT.

-   Wysyłanie wszystkich aktualizacji spisu sprzętu.

-   Wysyłanie wszystkich aktualizacji spisu aplikacji firmowych.

Jeśli masz pytania, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).




<!--HONumber=Sep16_HO4-->


