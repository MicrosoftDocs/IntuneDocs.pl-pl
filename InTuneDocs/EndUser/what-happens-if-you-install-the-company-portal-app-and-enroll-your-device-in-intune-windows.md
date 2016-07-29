---
title: "Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: noindex,nofollow
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 618e2abda642c3b9b2e813824dfd4235c9309faa
ms.openlocfilehash: 8b6e9b1bbf2d870b57dfcd7cdefefa2550d07d14


---


# Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune?

Podczas instalowania aplikacji Portal firmy, a następnie używania jej do zarejestrowania urządzenia z systemem Windows lub Windows Phone, pozwalasz administratorowi IT na zarządzanie urządzeniem, aby zachować bezpieczeństwo danych służbowych, zgodnie z poniższym opisem dla urządzeń z systemem wcześniejszym niż Windows 10. Aby uzyskać informacje o urządzeniach z systemem Windows 10, zobacz [tę stronę](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Co się dzieje na wszystkich urządzeniach z systemem Windows po rejestracji
Po zarejestrowaniu urządzenia systemu Windows lub Windows Phone w usłudze Intune można:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych

-   Pobierać aplikacje firmowe z witryny internetowej Portal firmy (dla systemów Windows 7 i Vista można pobierać aplikacje firmowe tylko z witryny sieci Web Portal firmy)

-   Automatycznie konfigurować konto e-mail firmy lub szkoły

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży

Zarejestrowanie urządzenia spowoduje nadanie administratorowi IT uprawnień, które pozwalają mu:

-   Resetować urządzenie do domyślnych ustawień fabrycznych. Jest to przydatne w przypadku utracenia lub kradzieży urządzenia.

-   Usuwać wszystkie dane dotyczące firmy oraz zainstalowane aplikacje biznesowe. Dane osobowe oraz ustawienia użytkownika nie zostaną usunięte.

-   Administrator IT może pobrać spis wszystkich programów zainstalowanych na komputerze, włącznie z oprogramowaniem zainstalowanym przez użytkownika.

-   Wymagać ustawienia na urządzeniu hasła lub numeru PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do urządzenia lub jego zresetowanie do domyślnych ustawień fabrycznych (co może obejmować usunięcie danych).

-   Wymusić zaszyfrowanie wszystkich danych na urządzeniu, co pomaga chronić dane w przypadku utracenia lub kradzieży urządzenia.

-   Wymagać od użytkownika zaakceptowania postanowień.

-   Administrator IT może wprowadzać zasady na komputerze. Od użytkownika może być na przykład wymagane, aby ustawił na komputerze hasło lub numer PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do komputera lub usunięcie wszystkich danych z dysku twardego.

-   Wyłączyć kartę SD.

## Co się dzieje na wszystkich komputerach z systemem Windows po rejestracji

-  Na komputerze zostanie zainstalowane oprogramowanie umożliwiające administratorowi IT zarządzanie komputerem oraz pozwalające użytkownikowi na uzyskanie dostępu do zasobów firmy, takich jak aplikacje czy informacje pomocy technicznej. Administrator IT może automatycznie aktualizować to oprogramowanie.

-  Na komputerze można zainstalować program Intune Endpoint Protection. To oprogramowanie, które wyszukuje wirusy i złośliwe oprogramowanie.

-  Administrator IT może pobrać spis wszystkich programów zainstalowanych na komputerze, włącznie z oprogramowaniem zainstalowanym przez użytkownika.

-  Konieczne może być zaakceptowanie warunków i postanowień.

-  Administrator IT może zbierać lub usuwać dane z dysku twardego komputera. Administrator IT może również usunąć cały dysk twardy.

-  Administrator IT może instalować na komputerze aplikacje i aktualizacje.

-  Administrator IT może wprowadzać zasady na komputerze. Od użytkownika może być na przykład wymagane, aby ustawił na komputerze hasło lub numer PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do komputera lub usunięcie wszystkich danych z dysku twardego.


## Co się dzieje co 8 godzin po rejestracji urządzenia
Mniej więcej co 8 godzin zarejestrowane urządzenia wykonują następujące czynności:

-   Pobieranie wszystkich aktualizacji aplikacji lub zasad udostępnionych przez administratora IT.

-   Wysyłanie wszystkich aktualizacji spisu sprzętu.

-   Wysyłanie wszystkich aktualizacji spisu aplikacji firmowych.

Kroki rejestracji opisano w artykule [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](enroll-your-device-in-intune-windows.md). Aby dowiedzieć się, co Twój administrator IT może zobaczyć na Twoim urządzeniu, zobacz [Jakie dane może wyświetlać mój administrator IT, gdy zarejestruję swoje urządzenie w usłudze Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Jeśli masz pytania, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

### Zobacz także
[Korzystanie z urządzenia z systemem Windows i usługi Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO4-->


