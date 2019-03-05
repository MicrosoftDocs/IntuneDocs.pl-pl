---
title: Konfigurowanie aplikacji Portal firmy
titleSuffix: Microsoft Intune
description: Informacje dotyczące zastosowania znakowania firmowego do aplikacji Portal firmy usługi Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c61eb47f29b201997d04fa6b1405ad2f186e4fcc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237201"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portal firmy usługi Microsoft Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.        

> [!Tip]        
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy. Należy pamiętać, że użytkownicy muszą mieć przypisaną licencję usługi Intune, aby uzyskiwać dostęp do witryny internetowej Portal firmy.

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. W tym celu w obciążeniu **Aplikacje klienckie** wybierz kolejno pozycje **Konfiguracja** > **Znakowanie Portalu firmy**, po czym skonfiguruj wymagane ustawienia.  

> [!Note]       
> Jeśli używasz platformy Azure Government, użytkownik końcowy ma możliwość zdecydowania o sposobie udostępnienia dzienników aplikacji, gdy rozpocznie proces uzyskiwania pomocy dotyczącej problemu. Jeśli jednak nie używasz platformy Azure Government, aplikacja Portal firmy w systemie Windows 10 będzie wysyłać dzienniki aplikacji bezpośrednio do firmy Microsoft, gdy użytkownik zainicjuje proces w celu uzyskania pomocy dotyczącej problemu. Wysłanie dzienników aplikacji do firmy Microsoft ułatwi rozwiązywanie i usuwanie problemów. 

## <a name="company-information-and-privacy-statement"></a>Informacje o firmie i zasady zachowania poufności informacji        
Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.

Pola oznaczone gwiazdką (*) są obowiązkowe.       


| Nazwa pola | Długość maksymalna | Więcej informacji |
|---|---|---|
|**Nazwa firmy**| 40 | Ta nazwa jest wyświetlana jako tytuł Portalu firmy i będzie pojawiać się jako tekst w całym środowisku użytkownika usługi Intune. |
| **Adres URL zasad zachowania poufności informacji** |     79     | Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Musisz podać prawidłowy adres URL w postaci `<https://www.contoso.com>`. |

## <a name="support-information"></a>Informacje dotyczące pomocy technicznej      
Wprowadź informacje dotyczące pomocy technicznej w firmie, aby udostępnić pracownikom dane kontaktowe do użycia w przypadku pytań związanych z usługą Intune.          

|Nazwa pola|Długość maksymalna|Więcej informacji|
|---|---|---|
|**Nazwa kontaktu** | 40 | Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**. |
|**Numer telefonu** | 20 | Ten numer kontaktowy jest wyświetlany na stronie **informacji kontaktowych działu IT** i umożliwia pracownikom kontaktowanie się z pomocą techniczną. |
|**Adres e-mail**| 40 | Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie `alias@domainname.com`. |
|**Nazwa witryny internetowej**| 40 | Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat Przejdź do witryny sieci Web działu IT. |
|**Adres URL witryny internetowej**| 150 | Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL musi mieć postać `https://www.contoso.com`. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje. |
| **Dodatkowe informacje**| 120 | Wyświetlane na stronie **Kontakt z działem IT**. |


## <a name="company-identity-branding-customization"></a>Dostosowywanie znakowania tożsamości firmy      
Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.     

### <a name="theme-color-and-logo-in-the-company-portal"></a>Kolor motywu i logo w Portalu firmy
Zastosuj kolor motywu w Portalu firmy. Wybierz kolor standardowy lub wprowadź sześciocyfrowy kod szesnastkowy koloru niestandardowego.

|Nazwa pola|Więcej informacji|
|---|---|
|**Wybierz kolor standardowy lub wprowadź sześciocyfrowy kod szesnastkowy**| Wybierz pozycję **Standardowy**, aby wybrać kolor. Wybierz pozycję **Niestandardowy**, aby wybrać kolor na podstawie wartości kodu szesnastkowego.|
|**Wybierz kolor motywu**| Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy. Możesz użyć koloru standardowego lub wprowadzić konkretny kod szesnastkowy. |
|**Wyświetl**| Wybierz, czy mają być wyświetlane **logo i nazwa firmy**, **tylko logo firmy** czy **tylko nazwa firmy**. |
|**Przekaż logo firmy**|Możesz przekazać logo firmy, aby było wyświetlane w Portalu firmy. Kolor tekstu jest wybierany automatycznie, aby zapewnić najwyższy poziom kontrastu. Aby uzyskać najlepszy wygląd, przekaż logo z przezroczystym tłem.<p><ul><li>Maksymalny rozmiar obrazu: 400 piks. x 400 piks.</li><li>Maksymalny rozmiar pliku: 750 KB</li><li>Typ pliku: PNG, JPG lub JPEG</li></ul>|

Po przekazaniu logo w obszarze podglądu będą wyświetlane logo i kolor motywu. Jeśli wybrano wyświetlanie nazwy firmy, będzie ona wyświetlana w kolorze czarnym lub białym w Portalu firmy. Jej kolor zostanie wybrany automatycznie, aby zapewnić najwyższy poziom kontrastu na podstawie koloru motywu. Nazwa firmy nie będzie wyświetlana w obszarze podglądu na ekranie. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Logo do użycia na białym lub jasnym tle
Wybierz logo, które będzie wyglądać najlepiej na białym lub jasnym tle.

|Nazwa pola|Więcej informacji|
|---|---|
|**Przekaż logo**| Ta opcja jest dostępna, jeśli logo firmy ma być wyświetlane. Aby uzyskać najlepszy wygląd, przekaż logo z przezroczystym tłem.<p><ul><li>Maksymalny rozmiar obrazu: 400 piks. x 400 piks.</li><li>Maksymalny rozmiar pliku: 750 KB</li><li>Typ pliku: PNG, JPG lub JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Obraz marki dla Portalu firmy

Możesz wyświetlać obraz marki Twojej firmy. Po zapisaniu zmian można wybrać pozycję **Podgląd ustawień** w portalu internetowym usługi Intune w górnej części bloku, aby zobaczyć, jak będą wyglądać konfiguracje. Podgląd obrazu marki jest dostępny tylko w urządzeniu z systemem iOS, a nie w portalu internetowym usługi Intune. 

|Nazwa pola|Więcej informacji|
|---|---|
|**Przekaż obraz marki**| Ta opcja umożliwia wyświetlanie obrazu tła na stronie profilu użytkownika w aplikacji Portal firmy.<p>*Uwaga*: wyświetlany obraz może wyglądać inaczej na różnych platformach.<p><ul><li>Zalecana szerokość obrazu: mniej niż 1125 pikseli, ale nie mniej niż 640 pikseli</li><li>Maksymalny rozmiar obrazu: 1,3 MB</li><li>Typ pliku: PNG, JPG lub JPEG</li></ul>|

Odpowiedni obraz marki wzmacnia pozytywne wrażenie marki, co pozwala zwiększyć zaufanie użytkownika w Portalu firmy. Poniżej przedstawiono porady, które warto wziąć pod uwagę podczas nabywania, wybierania i optymalizowania obrazu dla Portalu firmy. 

- Skontaktuj się z działem marketingu lub działem graficznym. Być może są już dostępne zatwierdzone obrazy marki. Mogą one również pomóc w optymalizacji obrazów. 

- Rozważ użycie obrazu w orientacji poziomej i pionowej. Obraz powinien mieć wystarczającą ilość tła wokół punktu centralnego. Obraz może zostać przycięty inaczej w zależności od rozmiaru, orientacji i platformy urządzenia. 

- Nie używaj ogólnego obrazu. Obraz powinien odzwierciedlać markę firmy i kojarzyć się użytkownikom z firmą. Jeśli nie masz własnego obrazu, lepszym rozwiązaniem jest brak obrazu niż użycie ogólnego obrazu, który nie ma znaczenia dla użytkownika. 

- Usuń niepotrzebne metadane. Plik obrazu może zawierać metadane, takie jak profil aparatu, lokalizację geograficzną, tytuł, podpis itp. Użyj narzędzia do optymalizacji obrazów, aby usunąć te informacje w celu zachowania jakości przy spełnieniu wymagania dotyczącego limitu rozmiaru pliku. 

Po dodaniu lub zmodyfikowaniu obrazu marki w usłudze Intune użytkownik końcowy może nie widzieć zmiany w urządzeniach z systemem iOS do momentu, gdy aplikacja Portal firmy rozpozna zmianę podczas uruchamiania, a następnie zostanie ponownie uruchomiona w celu wyświetlenia obrazu marki. 

### <a name="brand-image-examples"></a>Przykłady obrazu marki

Na poniższej ilustracji przedstawiono przykład obrazu marki urządzenia iPad:

![Zrzut ekranu przedstawiający przykład obrazu marki urządzenia iPhone](media/company-portal-app/company-portal-app-03.png)

Na poniższej ilustracji przedstawiono przykład obrazu marki urządzenia iPhone:

![Zrzut ekranu przedstawiający przykład obrazu marki urządzenia iPad](media/company-portal-app/company-portal-app-02.png)

## <a name="windows-company-portal-keyboard-shortcuts"></a>Skróty klawiaturowe w aplikacji Portal firmy dla systemu Windows

Użytkownicy końcowi mogą wyzwalać akcje nawigacji, aplikacji i urządzeń w aplikacji Portal firmy dla systemu Windows za pomocą skrótów klawiaturowych (akceleratorów).

Poniższe skróty klawiaturowe są dostępne w aplikacji Portal firmy dla systemu Windows.

| Obszar | Opis | Skrót klawiaturowy |
|:------------------:|:--------------:|:-----------------:|
| Menu nawigacji | Nawigacja | Alt + M |
|  | Domowy | Alt + H |
|  | Wszystkie aplikacje | Alt + A |
|  | Zainstalowane aplikacje | ALT + I |
|  | Wyślij opinię | Alt + F |
|  | Mój profil | Alt + U |
|  | Ustawienia | Alt + T |
| Strona główna — kafelek urządzenia | Zmień nazwę | F2 |
|  | Usuń | CTRL + D lub Delete |
|  | Sprawdź dostęp | Ctrl + M lub F9 |
| Szczegóły urządzenia | Zmień nazwę | F2 |
|  | Usuń | CTRL + D lub Delete |
|  | Sprawdź dostęp | Ctrl + M lub F9 |
| Szczegóły aplikacji | Instalowanie | CTRL + I |

Użytkownicy końcowi będą również mogli zobaczyć dostępne skróty w aplikacji Portal firmy dla systemu Windows.

![Zrzut ekranu przedstawiający dostępne skróty w Portalu firmy dla systemu Windows](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>Następne kroki

- [Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10 przy użyciu usługi Microsoft Intune](store-apps-company-portal-app.md)
