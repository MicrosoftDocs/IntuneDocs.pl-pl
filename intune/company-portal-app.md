---
title: Konfigurowanie aplikacji Portal firmy
titleSuffix: Microsoft Intune
description: Informacje dotyczące zastosowania znakowania firmowego do aplikacji Portal firmy usługi Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4535bdfa9b801c605c70c0a9dad900d76044eab4
ms.sourcegitcommit: c78923b0d5b320322c828b1bbea2deb9062e30d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/05/2018
ms.locfileid: "37844984"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portal firmy usługi Microsoft Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.        

> [!Tip]        
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.       

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. W tym celu w obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Konfiguracja** > **Znakowanie Portalu firmy**, po czym skonfiguruj wymagane ustawienia.  

> [!Note]       
> Gdy użytkownik zainicjuje przepływ pracy w celu uzyskania pomocy dotyczącej problemu, aplikacja Portal firmy w systemie Windows 10 wyśle dzienniki aplikacji bezpośrednio do firmy Microsoft. Ułatwia to rozwiązywanie i usuwanie problemów, które zostały zgłoszone firmie Microsoft.  

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


## <a name="company-branding-customization"></a>Dostosowywanie oznaczeń marki       
Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.     

### <a name="theme-color"></a>Kolor motywu
Zastosuj kolor motywu w Portalu firmy. Wybierz kolor standardowy lub wprowadź sześciocyfrowy kod szesnastkowy koloru niestandardowego.

|Nazwa pola|Więcej informacji|
|---|---|
|**Typ koloru**| Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy. Możesz użyć koloru standardowego lub wprowadzić konkretny kod szesnastkowy. |
|**Wybierz kolor** lub **Kod szesnastkowy koloru**| Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy. Możesz użyć koloru standardowego lub wprowadzić konkretny kod szesnastkowy. Te opcje są dostępne w zależności od wybranego **typu koloru**.  |

### <a name="company-logo"></a>Logo firmy
Przekaż logo firmy, aby było widoczne w całym środowisku użytkownika usługi Intune.

|Nazwa pola|Więcej informacji|
|---|---|
|**Wyświetl logo firmy**|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. |
|**Przekaż logo do użycia na tle koloru motywu**| Ta opcja jest dostępna, jeśli logo firmy ma być wyświetlane. Plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 400 pikseli i mieć rozmiar nie większy niż 750 KB. |
|**Przekaż logo do użycia na jasnym tle**| Ta opcja jest dostępna, jeśli logo firmy ma być wyświetlane. Plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 400 pikseli i mieć rozmiar nie większy niż 750 KB. |
|**Wyświetl nazwę firmy obok logo**| Wybierz tę opcję, aby wyświetlić wprowadzoną nazwę firmy obok załadowanego logo. |

Po zapisaniu zmian można wybrać pozycję **Podgląd ustawień w portalu internetowym usługi Intune** w górnej części bloku, aby zobaczyć, jak będą wyglądać konfiguracje.
