---
title: Instalowanie aplikacji Portal firmy dla systemu Windows | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 926e09173918488d6beb1f0e3f725a0cff2971b4
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2017
---
# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-windows-device-in-intune"></a>Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia z systemem Windows w usłudze Intune?

Podczas instalowania aplikacji Portal firmy, a następnie używania jej do zarejestrowania urządzenia z systemem Windows lub Windows Phone, pozwalasz działowi pomocy technicznej Twojej firmy na zarządzanie urządzeniem, aby zachować bezpieczeństwo danych służbowych. W tym temacie opisano, co się dzieje w przypadku urządzeń z systemem starszym niż Windows 10. W przypadku urządzeń z systemem Windows 10 zobacz [temat pokrewny](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## <a name="what-happens-to-all-windows-devices-after-enrollment"></a>Co się dzieje na wszystkich urządzeniach z systemem Windows po rejestracji
Zarejestrowanie urządzenia z systemem Windows lub Windows Phone w usłudze Intune pozwala:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych.

-   Pobierać aplikacje firmowe z witryny sieci Web Portal firmy. (__Uwaga__: w przypadku systemów Windows 7 i Vista aplikacje firmowe można pobierać tylko z witryny sieci Web Portal firmy).

-   Automatycznie konfigurować służbowe konto e-mail.

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży.

Zarejestrowanie urządzenia spowoduje nadanie działowi pomocy technicznej Twojej firmy uprawnień, które pozwalają mu:

-   Resetować urządzenie do domyślnych ustawień fabrycznych. Jest to przydatne w przypadku utracenia lub kradzieży urządzenia.

-   Usuwać tylko pliki związane z firmą i aplikacje biznesowe. *Dane osobiste oraz ustawienia użytkownika nie zostaną usunięte.*

-   Dział pomocy technicznej Twojej firmy będzie widzieć oprogramowanie zainstalowane na urządzeniu (z uwzględnieniem oprogramowania zainstalowanego przez użytkownika).

-   Ustawiać na Twoim urządzeniu wymagania, takie jak wymaganie ustawienia hasła lub numeru PIN urządzenia, aby pomóc w ochronie danych firmy. Dział pomocy technicznej Twojej firmy może także ograniczać to, ile razy można wprowadzić niepoprawne hasło, i może zablokować dostęp do urządzenia, jeśli spróbujesz zbyt wiele razy.

-   Wymagać od Ciebie szyfrowania danych na urządzeniu, aby chronić dane firmy na wypadek utraty lub kradzieży urządzenia.

-   Wymagać od użytkownika zaakceptowania postanowień.

-   Uniemożliwić robienie zdjęć danym związanym z firmą.

## <a name="what-happens-to-all-windows-pcs-after-enrollment"></a>Co się dzieje na wszystkich komputerach z systemem Windows po rejestracji

-  Na komputerze zostanie zainstalowane oprogramowanie umożliwiające działowi pomocy technicznej Twojej firmy zarządzanie komputerem oraz pozwalające użytkownikowi na uzyskanie dostępu do zasobów firmy, takich jak aplikacje czy informacje pomocy technicznej. Dział pomocy technicznej Twojej firmy może automatycznie aktualizować to oprogramowanie.

-  Na komputerze można zainstalować program Intune Endpoint Protection. To oprogramowanie wyszukuje wirusy i złośliwe oprogramowanie.

-  Dział pomocy technicznej Twojej firmy może zbierać lub usuwać dane z dysku twardego Twojego komputera.

-  Dział pomocy technicznej Twojej firmy może instalować na Twoim komputerze aplikacje i aktualizacje.

## <a name="what-happens-every-eight-hours-after-device-enrollment"></a>Co się dzieje co 8 godzin po rejestracji urządzenia

Mniej więcej co 8 godzin zarejestrowane urządzenia wykonują następujące czynności:

-   Pobieranie wszystkich aktualizacji aplikacji lub zasad udostępnionych przez dział pomocy technicznej Twojej firmy.

-   Wysyłanie wszystkich aktualizacji spisu sprzętu.

-   Wysyłanie wszystkich aktualizacji spisu aplikacji firmowych.

Jeśli masz pytania, skontaktuj się z działem pomocy technicznej Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com).
