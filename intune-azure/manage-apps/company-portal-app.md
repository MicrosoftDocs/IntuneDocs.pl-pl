---
title: "Konfigurowanie aplikacji Portal firmy | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące zastosowania znakowania firmowego do aplikacji Portal firmy usługi Intune. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 142b57f48c2950f6eecc228decfa06ce44c76319
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Portal firmy usługi Microsoft Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.

> [!Tip]
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. W tym celu w obciążeniu **Zarządzaj aplikacjami** wybierz kolejno pozycje **Instalacja** > **Znakowanie Portalu firmy**, po czym skonfiguruj wymagane ustawienia.

## <a name="company-contact-information-and-privacy-statement"></a>Informacje kontaktowe i zasady zachowania poufności informacji firmy
Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie **Kontakt z działem IT** w portalu firmy na komputerach użytkowników. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.


|Nazwa pola|Długość maksymalna|Więcej informacji|
|-|-|-|
|**Nazwa firmy**|40|Ta nazwa jest wyświetlana jako tytuł portalu firmy.|
|**Imię i nazwisko osoby do kontaktu w dziale IT**|40|Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**.|
|**Numer telefonu działu IT**|20|Ten numer kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**.|
|Adres e-mail działu IT|40|Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie **alias@domainname.com**.|
|**Dodatkowe informacje**|120|Wyświetlane na stronie **Kontakt z działem IT**.|
|**Adres URL zasad zachowania poufności informacji firmy**|79|Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Należy wprowadzić prawidłowy adres URL w formacie **https://www.contoso.com**.|

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
|**Kolor motywu**|Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy.|
|**Wyświetl logo firmy**|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.<br>Można również wyświetlić nazwę firmy wprowadzoną obok załadowanego logo.|

Po zapisaniu zmian można wybrać pozycję **Podgląd ustawień w portalu sieci Web usługi Intune**, aby zobaczyć, jak wyglądają konfiguracje.

