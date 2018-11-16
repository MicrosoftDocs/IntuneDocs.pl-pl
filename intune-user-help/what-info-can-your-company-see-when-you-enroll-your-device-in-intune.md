---
title: Jakie informacje może wyświetlać Twoja firma, gdy zarejestrujesz swoje urządzenie?
description: Objaśnia, co dział IT może zobaczyć bądź nie na Twoim zarządzanym urządzeniu.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.openlocfilehash: 63295d7e05889f5a8beb44e399f36a4fbe27544d
ms.sourcegitcommit: 76c7b315b83eb6cb5b996facf1d250fb3e22f1bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2018
ms.locfileid: "51276119"
---
# <a name="what-information-can-my-organization-see-when-i-enroll-my-device"></a>Jakie informacje może zobaczyć moja organizacja, gdy zarejestruję swoje urządzenie?

Gdy zarejestrujesz urządzenie w usłudze Microsoft Intune, Twoja organizacja nie będzie widzieć Twoich informacji osobistych. Gdy rejestrujesz urządzenie, dajesz organizacji uprawnienia do wyświetlania określonych fragmentów informacji na swoim urządzeniu, takich jak model urządzenia i jego numer seryjny. Organizacja używa tych informacji w celu ochrony danych firmowych znajdujących się na urządzeniu.

**Czego Twoja organizacja nigdy nie zobaczy:**

- Historia połączeń i przeglądania sieci Web
- Wiadomości e-mail i SMS
- Kontakty
- Kalendarz
-   Hasła
- Obrazy, w tym dane z aparatu i aplikacji Zdjęcia
- Pliki

**Co Twoja organizacja widzi zawsze:**

- Model urządzenia, np. Google Pixel
- Producent urządzenia, na przykład Microsoft
- Wersja systemu operacyjnego, na przykład iOS 12.0.1
- Nazwy aplikacji, na przykład Microsoft Word: na urządzeniach osobistych Twoja organizacja może wyświetlać tylko spis aplikacji zarządzanych. Na urządzeniach należących do firmy organizacja może wyświetlać spis wszystkich aplikacji.
- Właściciel urządzenia
- Nazwa urządzenia
- Numer seryjny urządzenia
- IMEI

**Co organizacja może widzieć:**

-  Numer telefonu: w przypadku urządzeń **należących do firmy** może być widoczny Twój pełny numer telefonu. W przypadku urządzeń **prywatnych** dla organizacji widoczne są wyłącznie cztery ostatnie cyfry Twojego numeru telefonu. **Typ własności** poszczególnych urządzeń można sprawdzić, otwierając stronę **Szczegóły urządzenia** odnoszącą się do tego urządzenia.
- Ilość wolnego miejsca na urządzeniu: jeśli nie możesz zainstalować wymaganej aplikacji, organizacja może zobaczyć ilość wolnego miejsca na urządzeniu, aby sprawdzić, czy miejsca nie jest za mało.  
-  Lokalizacja: organizacja nigdy nie widzi lokalizacji urządzenia; wyjątkiem są nadzorowane urządzenia z systemem iOS, które zostały utracone. [Jak to sprawdzić?](https://go.microsoft.com/fwlink/?linkid=853816)
- Spis aplikacji: organizacja korzystająca z usługi Mobile Threat Defense może przeglądać dodatkowe informacje o aplikacjach na urządzeniu z systemem iOS. Dowiedz się więcej na temat usługi [Mobile Threat Defense](you-are-prompted-to-install-mtd-ios.md).
- Informacje o sieci: niektóre informacje na temat połączeń sieciowych dla urządzeń z systemem Android mogą być dostępne dla działu pomocy technicznej Twojej organizacji. Na przykład jeśli organizacja wymaga, aby urządzenia znajdowały się w konkretnym budynku, urządzenie będzie identyfikować sieć, do której jest podłączone. 
