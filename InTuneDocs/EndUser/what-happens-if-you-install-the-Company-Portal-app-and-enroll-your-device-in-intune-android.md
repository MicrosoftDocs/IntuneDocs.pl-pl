---
title: "Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Android w usłudze Intune? | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d22f5aea-7be4-419b-b51b-a522ca037b69
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: df5cf2d5a78ccf58ba5920ad1856675538794874


---


# Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Android w usłudze Intune?

Po zainstalowaniu aplikacji Portal firmy i zarejestrowaniu urządzenia z systemem Android w usłudze Intune można używać aplikacji Portal firmy, aby:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych

-   Pobierać aplikacje firmowe z Portalu firmy

-   Automatycznie konfigurować firmowe konto e-mail

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży

Zarejestrowanie urządzenia z systemem Android spowoduje nadanie administratorowi IT uprawnień dostępu do tego urządzenia. Administratorzy mogą wykonywać następujące czynności:

-   Resetować urządzenie do domyślnych ustawień fabrycznych. Jest to przydatne w przypadku utracenia lub kradzieży urządzenia.

-   Usuń wszystkie dane dotyczące firmy. Dane osobowe oraz ustawienia użytkownika nie zostaną usunięte.

-   Wymagać ustawienia na urządzeniu hasła lub numeru PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do urządzenia lub jego zresetowanie do domyślnych ustawień fabrycznych (co może obejmować usunięcie danych).

-   Wymagać od użytkownika zaakceptowania postanowień.

-   Włączać lub wyłączać aparat w urządzeniu.

-   Wymusić zaszyfrowanie wszystkich danych na urządzeniu włącznie z danymi osobowymi i firmowymi. Pozwala to chronić dane w przypadku utracenia lub kradzieży urządzenia.

-   Po dodaniu urządzenia do aplikacji Portal firmy co około 8 godzin będą wykonywane następujące czynności:

    -   Pobieranie wszystkich aktualizacji aplikacji lub zasad udostępnionych przez administratora IT.

    -   Wysyłanie wszystkich aktualizacji spisu sprzętu (aktualizacje te nie zawierają danych osobowych).

    -   Wysyłanie wszystkich aktualizacji spisu aplikacji firmowych (aktualizacje te nie zawierają danych osobowych).

Potrzebujesz pomocy? Skontaktuj się z administratorem IT (sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com), aby uzyskać informacje kontaktowe) lub napisz do zespołu ds. systemu Android firmy Microsoft: wintunedroidfbk@microsoft.com.


### Zobacz także
[Korzystanie z urządzenia z systemem Android i usługi Intune](using-your-android-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


