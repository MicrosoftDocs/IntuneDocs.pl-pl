---
title: "Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune? | Dokumentacja firmy Microsoft"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: ae372c141ffd98d280715c454057284c4bd3d6e9


---


# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-windows-device-in-intune"></a>Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune?

Podczas instalowania aplikacji Portal firmy, a następnie używania jej do zarejestrowania urządzenia z systemem Windows lub Windows Phone pozwalasz administratorowi IT na zarządzanie urządzeniem, aby zachować bezpieczeństwo danych służbowych. W tym temacie opisano, co się dzieje w przypadku urządzeń z systemem starszym niż Windows 10. W przypadku urządzeń z systemem Windows 10 zobacz [temat pokrewny](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## <a name="what-happens-to-all-windows-devices-after-enrollment"></a>Co się dzieje na wszystkich urządzeniach z systemem Windows po rejestracji
Zarejestrowanie urządzenia z systemem Windows lub Windows Phone w usłudze Intune pozwala:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych.

-   Pobierać aplikacje firmowe z witryny sieci Web Portal firmy. (W przypadku systemów Windows 7 i Vista można pobierać aplikacje firmowe tylko z witryny sieci Web Portal firmy).

-   Automatycznie konfigurować służbowe konto e-mail.

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży.

Zarejestrowanie urządzenia spowoduje nadanie administratorowi IT uprawnień, które pozwalają mu:

-   Resetować urządzenie do domyślnych ustawień fabrycznych. Jest to przydatne w przypadku utracenia lub kradzieży urządzenia.

-   Usuwać tylko pliki związane z firmą i aplikacje biznesowe. *Dane osobiste oraz ustawienia użytkownika nie zostaną usunięte.*

-   Administrator IT będzie widzieć oprogramowanie zainstalowane na urządzeniu (z uwzględnieniem oprogramowania zainstalowanego przez użytkownika).

-   Ustawiać na Twoim urządzeniu wymagania, takie jak wymaganie ustawienia hasła lub numeru PIN urządzenia, aby pomóc w ochronie danych firmy. Administrator IT może także ograniczać to, ile razy można wprowadzić niepoprawne hasło, i może zablokować dostęp do urządzenia, jeśli spróbujesz zbyt wiele razy.

-   Wymagać od Ciebie szyfrowania danych na urządzeniu, aby chronić dane firmy na wypadek utraty lub kradzieży urządzenia.

-   Wymagać od użytkownika zaakceptowania postanowień.

-   Uniemożliwić robienie zdjęć danym związanym z firmą.

## <a name="what-happens-to-all-windows-pcs-after-enrollment"></a>Co się dzieje na wszystkich komputerach z systemem Windows po rejestracji

-  Na komputerze zostanie zainstalowane oprogramowanie umożliwiające administratorowi IT zarządzanie komputerem oraz pozwalające użytkownikowi na uzyskanie dostępu do zasobów firmy, takich jak aplikacje czy informacje pomocy technicznej. Administrator IT może automatycznie aktualizować to oprogramowanie.

-  Na komputerze można zainstalować program Intune Endpoint Protection. To oprogramowanie wyszukuje wirusy i złośliwe oprogramowanie.

-  Administrator IT może zbierać lub usuwać dane z dysku twardego komputera.

-  Administrator IT może instalować na komputerze aplikacje i aktualizacje.

## <a name="what-happens-every-eight-hours-after-device-enrollment"></a>Co się dzieje co 8 godzin po rejestracji urządzenia
Mniej więcej co 8 godzin zarejestrowane urządzenia wykonują następujące czynności:

-   Pobieranie wszystkich aktualizacji aplikacji lub zasad udostępnionych przez administratora IT.

-   Wysyłanie wszystkich aktualizacji spisu sprzętu.

-   Wysyłanie wszystkich aktualizacji spisu aplikacji firmowych.

Jeśli masz pytania, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO2-->


