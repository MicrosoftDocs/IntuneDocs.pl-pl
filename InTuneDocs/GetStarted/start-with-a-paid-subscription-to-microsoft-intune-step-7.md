---
# required metadata

title: Dostosowywanie Portalu firmy | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Dostosuj portal firmy
Portal [!INCLUDE[wit_iwportal_1](../includes/wit_iwportal_1_md.md)] jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.

> [!TIP]
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.

Dostosowywanie Portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. Aby wykonać to zadanie, wystarczy zalogować się do [konsoli administratora usługi Microsoft](https://manage.microsoft.com) jako administrator dzierżawy lub usługi, wybrać pozycje **Administrator** &gt; **Portal firmy**, a następnie skonfigurować ustawienia Portalu firmy.

![Ustawienia Portalu firmy w obszarze roboczym Administrator konsoli administracyjnej](./media/companyportal.png)

## Informacje kontaktowe i zasady zachowania poufności informacji firmy
Nazwa firmy jest wyświetlana jako tytuł Portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie Kontakt z działem IT w Portalu firmy na komputerach użytkowników. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Nazwa firmy|40|Ta nazwa jest wyświetlana jako tytuł Portalu firmy.|
    |Imię i nazwisko osoby kontaktowej w dziale IT|40|Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**.|
    |Numer telefonu działu IT|20|Ten numer kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**.|
    |Adres e-mail działu IT|40|Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie **alias@nazwadomeny.com**..|
    |Dodatkowe informacje|120|Wyświetlane na stronie **Kontakt z działem IT**.|
    |Adres URL zasad zachowania poufności informacji firmy|79|Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w Portalu firmy linki do informacji o prywatności. Należy wprowadzić prawidłowy adres URL w formacie https://www.contoso.com.|

## Kontakt z pomocą techniczną
Witryna sieci Web z pomocą techniczną wyświetlana w Portalu firmy umożliwia użytkownikom dostęp do pomocy online.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Adres URL witryny sieci Web pomocy technicznej|150|Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL należy wpisać w formacie https://www.contoso.com. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje.|
    |Nazwa witryny sieci Web|40|Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w Portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat **Przejdź do witryny sieci Web działu IT**.|

## Dostosowywanie oznaczeń marki
Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.

|Nazwa pola|Więcej informacji|
    |----------|----------------|
    |Kolor motywu|Wybierz kolor motywu, który ma zostać zastosowany do Portalu firmy.|
    |Uwzględnij logo firmowe|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w Portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło Portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.|
    |Wybierz tło dla aplikacji Portal firmy dla systemu [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|To ustawienie ma wpływ wyłącznie na tło w aplikacji Portal firmy systemu [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Po zapisaniu zmian można użyć linków dostępnych na dole strony **Portal firmy** w konsoli administracyjnej, aby wyświetlić witrynę sieci Web Portal firmy. Tych linków nie można zmienić. Po zalogowaniu użytkownika wyświetlane linki odpowiadają subskrypcjom w Portalu firmy.

### Następne kroki
Gratulacje! Krok 7 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony..
>[!div class="step-by-step"]

>[&larr; **Tworzenie zasad i aplikacji**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Rejestrowanie urządzeń** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  


<!--HONumber=May16_HO1-->


