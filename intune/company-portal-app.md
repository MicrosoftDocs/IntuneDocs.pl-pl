---
title: Konfigurowanie aplikacji Portal firmy
titleSuffix: Microsoft Intune
description: Informacje dotyczące zastosowania znakowania firmowego do aplikacji Portal firmy usługi Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5a7213608a8147178633ccd8129ab40eef5d4a15
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portal firmy usługi Microsoft Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.        

> [!Tip]        
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.       

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. W tym celu w obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Konfiguracja** > **Znakowanie Portalu firmy**, po czym skonfiguruj wymagane ustawienia.      

## <a name="company-contact-information-and-privacy-statement"></a>Informacje kontaktowe i zasady zachowania poufności informacji firmy        
Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie **Kontakt z działem IT** w portalu firmy na komputerach użytkowników. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.

Pola oznaczone gwiazdką (*) są obowiązkowe.       


| Nazwa pola | Długość maksymalna | Więcej informacji |
|---|---|---|
|**Nazwa firmy**| 40 | Ta nazwa jest wyświetlana jako tytuł portalu firmy. |
|**Imię i nazwisko osoby do kontaktu w dziale IT** | 40 | Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**. |
|**Numer telefonu działu IT** | 20 | Ten numer kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. |
|**Adres e-mail działu IT**| 40 | Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie `alias@domainname.com`. |
| **Dodatkowe informacje**|    120     | Wyświetlane na stronie **Kontakt z działem IT**. |
| **Adres URL zasad zachowania poufności informacji firmy** |     79     | Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Musisz podać prawidłowy adres URL w postaci `<https://www.contoso.com>`. |

## <a name="support-contacts"></a>Kontakt z pomocą techniczną     
Witryna sieci Web z pomocą techniczną wyświetlana w portalu firmy umożliwia użytkownikom dostęp do pomocy online.        

|Nazwa pola|Długość maksymalna|Więcej informacji|
|---|---|---|
|**Adres URL witryny sieci Web pomocy technicznej**|150|Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL należy wpisać w formacie **https://www.contoso.com**. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje.|
|**Nazwa witryny sieci Web pomocy technicznej**|40|Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat Przejdź do witryny sieci Web działu IT.

## <a name="company-branding-customization"></a>Dostosowywanie oznaczeń marki       
Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.     

|Nazwa pola|Więcej informacji|
|---|---|
|**Kolor motywu**|Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy. Możesz użyć selektora kolorów lub wprowadzić konkretny kod szesnastkowy.|
|**Wyświetl logo firmy**|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.<br>Można również wyświetlić nazwę firmy wprowadzoną obok załadowanego logo.|

Po zapisaniu zmian można wybrać pozycję **Podgląd ustawień w portalu sieci Web usługi Intune**, aby zobaczyć, jak wyglądają konfiguracje.
