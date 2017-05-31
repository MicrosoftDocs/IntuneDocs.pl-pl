---
title: Dostosowywanie aplikacji Portal firmy | Microsoft Docs
description: "Portal firmy w usłudze Intune umożliwia użytkownikom wykonywanie typowych zadań, takich jak rejestrowanie urządzeń, instalowanie aplikacji i wyszukiwanie informacji działu IT."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: b18b3214bc91eed71fc129949532f611cf277d7a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="customize-the-company-portal"></a>Dostosuj portal firmy

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera informacje dla administratorów dotyczące dostosowywania witryny sieci Web Portal firmy oraz aplikacji Portal firmy w usłudze Intune.

Portal firmy usługi Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.

Portal firmy usługi Intune zapewnia użytkownikom dostęp do firmowych danych i aplikacji. Portal firmy jest dostępny w dwóch formach:

-   **Aplikacja Portal firmy:** aplikacja dostępna na urządzeniach zarządzanych za pomocą usługi Intune. Dowiedz się więcej o aplikacjach Portal firmy dla systemów [Android](/intune-user-help/using-your-android-device-with-intune), [iOS](/intune-user-help/using-your-iOS-or-macOS-device-with-intune) i [Windows](/intune-user-help/using-your-windows-device-with-intune).


- **Witryna sieci Web Portal firmy:** witryna sieci Web, która umożliwia użytkownikom końcowym wykonywanie większości zadań, które można wykonywać w aplikacji Portal firmy. Adres URL witryny Portal firmy w usłudze Intune to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com). Dowiedz się więcej o tej witrynie sieci Web w artykule [Using the Intune Company Portal website](/intune-user-help/using-the-intune-company-portal-website) (Korzystanie z witryny sieci Web Portal firmy usługi Intune).

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
    |Wybierz tło aplikacji Portal firmy dla systemu Windows 8|To ustawienie ma wpływ wyłącznie na tło w aplikacji Portal firmy systemu Windows 8.|


Po zapisaniu zmian można użyć linków dostępnych na dole strony **Portal firmy** w konsoli administracyjnej, aby wyświetlić witrynę sieci Web Portal firmy. Tych linków nie można zmienić. Po zalogowaniu użytkownika wyświetlane linki odpowiadają subskrypcjom w Portalu firmy.

>[!div class="step-by-step"]

>[&larr;**Tworzenie zasad i aplikacji**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)        [**Rejestrowanie urządzeń** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  

