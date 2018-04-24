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
ms.openlocfilehash: aed2bec6e6fea40fdbd78bc487896d167d036f06
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portal firmy usługi Microsoft Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.        

> [!Tip]        
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.       

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. W tym celu w obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Konfiguracja** > **Znakowanie Portalu firmy**, po czym skonfiguruj wymagane ustawienia.      

## <a name="company-contact-information-and-privacy-statement"></a>Informacje kontaktowe i zasady zachowania poufności informacji firmy        
Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie **Kontakt z działem IT** w portalu firmy na komputerach użytkowników. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.        


|                   Nazwa pola                   | Długość maksymalna |                                                                                                 Więcej informacji                                                                                                 |
|------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <strong>Nazwa firmy</strong>          |     40     |                                                                            Ta nazwa jest wyświetlana jako tytuł portalu firmy.                                                                            |
|  <strong>Imię i nazwisko osoby do kontaktu w dziale IT</strong>   |     40     |                                                                         Ta nazwa jest wyświetlana na stronie <strong>Kontakt z działem IT</strong>.                                                                          |
|  <strong>Numer telefonu działu IT</strong>   |     20     |                                                                    Ten numer kontaktowy jest wyświetlany na stronie <strong>Kontakt z działem IT</strong>.                                                                     |
|  <strong>Adres e-mail działu IT</strong>  |     40     |                       Ten adres kontaktowy jest wyświetlany na stronie <strong>Kontakt z działem IT</strong>. Należy wprowadzić prawidłowy adres e-mail w formacie <strong>alias@domainname.com</strong>.                       |
|    <strong>Dodatkowe informacje</strong>     |    120     |                                                                                Wyświetlane na stronie <strong>Kontakt z działem IT</strong>.                                                                                |
| <strong>Adres URL zasad zachowania poufności informacji firmy</strong> |     79     | Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Należy wprowadzić prawidłowy adres URL w formacie <strong><https://www.contoso.com></strong>. |

## <a name="support-contacts"></a>Kontakt z pomocą techniczną     
Witryna sieci Web z pomocą techniczną wyświetlana w portalu firmy umożliwia użytkownikom dostęp do pomocy online.        



|Nazwa pola|Długość maksymalna|Więcej informacji|        
|-|-|-|     
|**Adres URL witryny sieci Web pomocy technicznej**|150|Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL należy wpisać w formacie **https://www.contoso.com**. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje.|        
|**Nazwa witryny sieci Web pomocy technicznej**|40|Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat Przejdź do witryny sieci Web działu IT.       

## <a name="company-branding-customization"></a>Dostosowywanie oznaczeń marki       
Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.     



|Nazwa pola|Więcej informacji|       
|-|-|       
|**Kolor motywu**|Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy. Możesz użyć selektora kolorów lub wprowadzić konkretny kod szesnastkowy.|      
|**Wyświetl logo firmy**|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.<br>Można również wyświetlić nazwę firmy wprowadzoną obok załadowanego logo.|      

Po zapisaniu zmian można wybrać pozycję **Podgląd ustawień w portalu sieci Web usługi Intune**, aby zobaczyć, jak wyglądają konfiguracje.
