---
title: Dostosowywanie Portalu firmy | Microsoft Intune
description: "Portal firmy w usłudze Intune umożliwia użytkownikom wykonywanie typowych zadań, takich jak rejestrowanie urządzeń, instalowanie aplikacji i wyszukiwanie informacji działu IT."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 15ef5c5b7f4c8aa2ceaa6867306e0e82a9835b02


---

# <a name="customize-the-company-portal"></a>Dostosuj portal firmy
Portal firmy usługi Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.

Portal firmy usługi Intune zapewnia użytkownikom dostęp do firmowych danych i aplikacji. Portal firmy jest dostępny w dwóch formach:

-   **Aplikacja Portal firmy:** aplikacja dostępna na urządzeniach zarządzanych za pomocą usługi Intune. Dowiedz się więcej o aplikacjach Portal firmy dla systemów [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-ios-or-mac-os-x-device-with-intune) i [Windows](/Intune/EndUser/using-your-windows-device-with-intune).


- **Witryna sieci Web Portal firmy:** witryna sieci Web, która umożliwia użytkownikom końcowym wykonywanie większości zadań, które można wykonywać w aplikacji Portal firmy. Adres URL witryny Portal firmy w usłudze Intune to [http://portal.manage.microsoft.com](http://portal.manage.microsoft.com). Dowiedz się więcej o tej witrynie sieci Web w artykule [Using the Intune Company Portal website](/Intune/EndUser/using-the-intune-company-portal-website) (Korzystanie z witryny sieci Web Portal firmy usługi Intune).

> [!TIP]
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.

Niektóre z zadań, które użytkownicy mogą wykonać w portalu firmy, to:

-   Rejestrowanie urządzeń
-   Wyświetlanie stanu urządzeń
-   Resetowanie swojego urządzenia
-   Resetowanie swojego hasła
-   Zdalne blokowanie swojego urządzenia
-   Pobieranie oprogramowania wdrażanego w organizacji
-   Kontaktowanie się z działem IT w celu uzyskania pomocy technicznej

> [!NOTE]
> Aplikacja Portal firmy jest jeszcze niedostępna w niektórych krajach.
> __System iOS__: Aplikacja Portal firmy dla systemu iOS jest opublikowana we [wszystkich dostępnych regionach](https://go.microsoft.com/fwlink/?linkid=831284) dla sklepu Apple iOS App Store.
> __System Android__: Aplikacja Portal firmy dla systemu Android nie jest obecnie dostępna w Chinach. W przypadku tych krajów alternatywnym rozwiązaniem jest [bezpośrednie ładowanie aplikacji Portal firmy w wersji dla systemu Android](https://www.microsoft.com/en-us/download/details.aspx?id=49140).  

## <a name="customize-company-portal-settings"></a>Dostosowywanie ustawień aplikacji Portal firmy
Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. Zaloguj się do [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) jako administrator dzierżawy lub usługi, wybierz kolejno pozycje **Administracja** &gt; **Portal firmy**, a następnie skonfiguruj ustawienia aplikacji Portal firmy.

![Ustawienia portalu firmy w obszarze roboczym Administrator konsoli administracyjnej](./media/companyportal.png)

## <a name="company-contact-information-and-privacy-statement"></a>Informacje kontaktowe i zasady zachowania poufności informacji firmy
Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie Kontakt z działem IT w portalu firmy na komputerach użytkowników. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Nazwa firmy|40|Ta nazwa jest wyświetlana jako tytuł portalu firmy.|
    |Imię i nazwisko osoby kontaktowej w dziale IT|40|Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**.|
    |Numer telefonu działu IT|20|Ten numer kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**.|
    |Adres e-mail działu IT|40|Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie **alias@domainname.com**.|
    |Dodatkowe informacje|120|Wyświetlane na stronie **Kontakt z działem IT**.|
    |Adres URL zasad zachowania poufności informacji firmy|79|Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Należy wprowadzić prawidłowy adres URL w formacie https://www.contoso.com.|

## <a name="support-contacts"></a>Kontakt z pomocą techniczną
Witryna sieci Web z pomocą techniczną wyświetlana w portalu firmy umożliwia użytkownikom dostęp do pomocy online.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Adres URL witryny sieci Web pomocy technicznej|150|Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL należy wpisać w formacie https://www.contoso.com. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje.|
    |Nazwa witryny sieci Web|40|Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat **Przejdź do witryny sieci Web działu IT**.|

## <a name="company-branding-customization"></a>Dostosowywanie oznaczeń marki
Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.

|Nazwa pola|Więcej informacji|
    |----------|----------------|
    |Kolor motywu|Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy.|
    |Uwzględnij logo firmowe|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.|
    |Wybierz tło dla aplikacji Portal firmy dla systemu [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|To ustawienie ma wpływ wyłącznie na tło w aplikacji Portal firmy systemu [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Po zapisaniu zmian można użyć linków dostępnych na dole strony **Portal firmy** w konsoli administracyjnej, aby wyświetlić witrynę sieci Web Portal firmy. Tych linków nie można zmienić. Po zalogowaniu użytkownika wyświetlane linki odpowiadają subskrypcjom w Portalu firmy.

### <a name="next-steps"></a>Następne kroki
Gratulacje! Krok 7 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony.
>[!div class="step-by-step"]

>[&larr;**Tworzenie zasad i aplikacji**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)        [**Rejestrowanie urządzeń** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Nov16_HO4-->


