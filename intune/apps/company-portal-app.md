---
title: Konfigurowanie aplikacji Portal firmy
titleSuffix: Microsoft Intune
description: Informacje dotyczące zastosowania znakowania firmowego do aplikacji Portal firmy usługi Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 419fd15f747c8b41377f3aca94c4b96d7c4910c1
ms.sourcegitcommit: b8127c7a62d9ac4d0f768980fa1424567bb58733
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2019
ms.locfileid: "72350011"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Portal firmy usługi Microsoft Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT. Ponadto aplikacja Portal firmy umożliwia użytkownikom bezpieczne uzyskiwanie dostępu do zasobów firmy. Aplikacja Portal firmy zawiera kilka różnych stron, takich jak Strona główna, Aplikacje, Szczegóły aplikacji, Urządzenia i Szczegóły urządzeń. Aby szybko znaleźć aplikacje w aplikacji Portal firmy, można filtrować aplikacje na stronie Aplikacje.

> [!IMPORTANT]
> W celu zapewnienia obsługi usługi Firebase Cloud Messaging (FCM) firmy Google należy zaktualizować aplikację Portal firmy dla systemu Android do najnowszej wersji. Aby uzyskać więcej informacji, zobacz temat Co nowego — [Aktualizacja aplikacji Portal firmy dla systemu Android do najnowszej wersji](../fundamentals/whats-new.md#update-your-android-company-portal-app-to-the-latest-version-).

> [!Tip]
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy. Należy pamiętać, że użytkownicy muszą mieć przypisaną licencję usługi Intune, aby uzyskiwać dostęp do witryny internetowej Portal firmy.

Dostosowanie Portalu firmy ułatwi zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. W tym celu w portalu usługi Intune wybierz pozycję **Aplikacje klienckie** > **Znakowanie i dostosowywanie**, a następnie skonfiguruj wymagane ustawienia.

Gdy użytkownik będzie instalował aplikację systemu iOS z witryny Portal firmy, zostanie wyświetlony monit. Dzieje się tak, gdy aplikacja systemu iOS jest połączona ze sklepem z aplikacjami, z programem zakupów zbiorczych (VPP) lub z aplikacją biznesową (LOB). Monit umożliwia użytkownikom zaakceptowanie akcji lub zezwolenie na zarządzanie aplikacją. Monit będzie zawierał nazwę firmy, a jeśli nazwa firmy jest niedostępna, będzie wyświetlana pozycja **Portal firmy**. 

> [!Note]
> Jeśli używasz platformy Azure Government, użytkownik końcowy ma możliwość zdecydowania o sposobie udostępnienia dzienników aplikacji, gdy rozpocznie proces uzyskiwania pomocy dotyczącej problemu. Jeśli jednak nie używasz platformy Azure Government, aplikacja Portal firmy w systemie Windows 10 będzie wysyłać dzienniki aplikacji bezpośrednio do firmy Microsoft, gdy użytkownik zainicjuje proces w celu uzyskania pomocy dotyczącej problemu. Wysłanie dzienników aplikacji do firmy Microsoft ułatwi rozwiązywanie i usuwanie problemów. 

## <a name="company-information-and-privacy-statement"></a>Informacje o firmie i zasady zachowania poufności informacji
Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.

| Nazwa pola | Długość maksymalna | Więcej informacji |
|---|---|---|
|**Nazwa firmy**| 40 | Ta nazwa jest wyświetlana jako tytuł Portalu firmy i będzie pojawiać się jako tekst w całym środowisku użytkownika usługi Intune. |
| **Adres URL zasad zachowania poufności informacji** |     79     | Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Musisz podać prawidłowy adres URL w postaci `<https://www.contoso.com>`. |

> [!NOTE]
> Zgodnie z zasadami firm Microsoft i Apple nie sprzedajemy żadnych danych zebranych przez naszą usługę żadnym podmiotom trzecim z jakiegokolwiek powodu.

## <a name="support-information"></a>Informacje dotyczące pomocy technicznej
Wprowadź informacje dotyczące pomocy technicznej w firmie, aby udostępnić pracownikom dane kontaktowe do użycia w przypadku pytań związanych z usługą Intune.

|Nazwa pola|Długość maksymalna|Więcej informacji|
|---|---|---|
|**Nazwa kontaktu** | 40 | Ta nazwa jest wyświetlana na stronie **Pomoc i obsługa techniczna**. |
|**Numer telefonu** | 20 | Ten numer kontaktowy jest wyświetlany na stronie **Pomoc i obsługa techniczna** i umożliwia pracownikom kontaktowanie się z pomocą techniczną. |
|**Adres e-mail**| 40 | Ten adres kontaktowy jest wyświetlany na stronie **Pomoc i obsługa techniczna**. Należy wprowadzić prawidłowy adres e-mail w formacie `alias@domainname.com`. |
|**Nazwa witryny internetowej**| 40 | Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli określisz tylko adres URL witryny internetowej pomocy technicznej i nie podasz przyjaznej nazwy, witryna Kontakt z działem IT będzie wyświetlana na stronie **Pomoc i obsługa techniczna** w aplikacji Portal firmy. |
|**Adres URL witryny internetowej**| 150 | Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL musi mieć postać `https://www.contoso.com`. Jeśli nie określisz adresu URL, w aplikacji Portal firmy na stronie **Pomoc i obsługa techniczna** nie będą wyświetlane żadne informacje dla witryny pomocy technicznej. |
| **Dodatkowe informacje**| 120 | Wyświetlane na stronie **Pomoc i obsługa techniczna**. |


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
|**Przekaż obraz marki**| Ta opcja umożliwia wyświetlanie obrazu marki. W aplikacji Portal firmy dla systemu iOS jest on wyświetlany jako obraz tła na stronie profilu użytkownika.<p><ul><li>Zalecana szerokość obrazu: Większa niż 1125 pikseli (wymagane co najmniej 650 pikseli)</li><li>Maksymalny rozmiar obrazu: 1,3 MB</li><li>Typ pliku: PNG, JPG lub JPEG</li></ul>|

Odpowiedni obraz marki wzmacnia pozytywne wrażenie marki, co pozwala zwiększyć zaufanie użytkownika w Portalu firmy. Poniżej przedstawiono porady, które warto wziąć pod uwagę podczas nabywania, wybierania i optymalizowania obrazu dla Portalu firmy. 

- Skontaktuj się z działem marketingu lub działem graficznym. Być może są już dostępne zatwierdzone obrazy marki. Mogą one również pomóc w optymalizacji obrazów. 

- Rozważ użycie obrazu w orientacji poziomej i pionowej. Obraz powinien mieć wystarczającą ilość tła wokół punktu centralnego. Obraz może zostać przycięty inaczej w zależności od rozmiaru, orientacji i platformy urządzenia. 

- Nie używaj ogólnego obrazu. Obraz powinien odzwierciedlać markę firmy i kojarzyć się użytkownikom z firmą. Jeśli nie masz własnego obrazu, lepszym rozwiązaniem jest brak obrazu niż użycie ogólnego obrazu, który nie ma znaczenia dla użytkownika. 

- Usuń niepotrzebne metadane. Plik obrazu może zawierać metadane, takie jak profil aparatu, lokalizację geograficzną, tytuł, podpis itp. Użyj narzędzia do optymalizacji obrazów, aby usunąć te informacje w celu zachowania jakości przy spełnieniu wymagania dotyczącego limitu rozmiaru pliku. 

Po dodaniu lub zmodyfikowaniu obrazu marki w usłudze Intune użytkownik końcowy może nie widzieć zmiany w urządzeniach z systemem iOS do momentu, gdy aplikacja Portal firmy rozpozna zmianę podczas uruchamiania, a następnie zostanie ponownie uruchomiona w celu wyświetlenia obrazu marki. 

### <a name="brand-image-examples"></a>Przykłady obrazu marki

Na poniższej ilustracji przedstawiono przykład obrazu marki urządzenia iPad:

![Zrzut ekranu przedstawiający przykład obrazu marki urządzenia iPhone](./media/company-portal-app/company-portal-app-03.png)

Na poniższej ilustracji przedstawiono przykład obrazu marki urządzenia iPhone:

![Zrzut ekranu przedstawiający przykład obrazu marki urządzenia iPad](./media/company-portal-app/company-portal-app-02.png)

## <a name="privacy-statement-customization"></a>Dostosowywanie oświadczenia o ochronie prywatności

Możesz dostosować oświadczenie o ochronie prywatności, które jest wyświetlane dla organizacji na zarządzanych urządzeniach z systemem iOS. Ten komunikat zawiera listę elementów, których organizacja nie może zobaczyć ani używać na zarządzanych urządzeniach z systemem iOS.

W obszarze **Dostosowywanie Portalu firmy** > **Komunikat dotyczący zarządzania urządzeniami i prywatności** możesz:

- wybrać pozycję **Domyślne**, aby zaakceptować listę i używać jej w takiej formie, w jakiej została pokazana, lub
- wybrać pozycję **Niestandardowe**, aby dostosować listę elementów, których organizacja nie może zobaczyć ani używać na zarządzanych urządzeniach z systemem iOS. Aby dodać punktory, pogrubienie, kursywę i linki, można użyć znaczników [markdown](https://daringfireball.net/projects/markdown/).

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
| Devices | Dostępne | Ctrl + D |

Użytkownicy końcowi będą również mogli zobaczyć dostępne skróty w aplikacji Portal firmy dla systemu Windows.

![Zrzut ekranu przedstawiający dostępne skróty w Portalu firmy dla systemu Windows](./media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>Samoobsługowe akcje urządzenia użytkownika w aplikacji Portal firmy

Za pomocą aplikacji lub witryny Portal firmy użytkownicy mogą wykonywać akcje na urządzeniach lokalnych lub zdalnych. Akcje, które użytkownik może wykonywać, różnią się w zależności od platformy i konfiguracji urządzenia. We wszystkich przypadkach akcje urządzenia zdalnego mogą być wykonywane tylko przez użytkownika podstawowego.
- **Wycofaj** — Usuwa urządzenie z funkcji zarządzania usługi Intune. W aplikacji i witrynie Portal firmy ta opcja jest widoczna jako **Usuń**.
- **Wyczyść** — Ta akcja inicjuje resetowanie urządzenia. W witrynie Portal firmy ta opcja jest widoczna jako **Resetowanie**, a w aplikacji Portal firmy dla systemu iOS jako **Resetowanie do ustawień fabrycznych**.
- **Zmień nazwę** — Ta akcja zmienia nazwę urządzenia, którą użytkownik widzi w Portalu firmy. Nie zmienia ona nazwy urządzenia lokalnego, tylko pozycję widoczną na liście w Portalu firmy.
- **Synchronizuj** — Ta akcja inicjuje ewidencjonowanie urządzenia w usłudze Intune. Ta opcja jest widoczna jako **Sprawdź stan** w Portalu firmy.
- **Zdalne blokowanie** — Blokuje urządzenie i wymaga podania kodu PIN w celu odblokowania.
- **Resetowanie kodu dostępu** — Ta akcja służy do resetowania kodu dostępu urządzenia. Na urządzeniach z systemem iOS kod dostępu zostanie usunięty i użytkownik końcowy będzie musiał wprowadzić nowy kod w ustawieniach. Na obsługiwanych urządzeniach z systemem Android nowy kod dostępu jest generowany przez usługę Intune i tymczasowo wyświetlany w Portalu firmy.
- **Odzyskiwanie kluczy** — Ta akcja służy do odzyskania osobistego klucza odzyskiwania dla zaszyfrowanych urządzeń z systemem macOS z witryny Portal firmy. 

### <a name="self-service-actions"></a>Akcje samoobsługowe

Niektóre platformy i konfiguracje nie zezwalają na samoobsługowe akcje urządzeń. W poniższej tabeli znajdują się dodatkowe szczegółowe informacje na temat akcji samoobsługowych:

|     Platforma    |    Wycofaj    |    Czyszczenie danych     |    Zmień nazwę <sup>(4)</sup>    |    Synchronizuj    |    Zdalne blokowanie    |    Resetowanie kodu dostępu    |    Odzyskiwanie kluczy    |
|------------------------|--------------------|--------------------|-----------------|-----------------|--------------------------|--------------------------|--------------------|
|    Windows 10<sup>(3)</sup>    |    Dostępne<sup>(1)</sup>    |    Dostępne    |    Dostępne    |    Dostępne    |    Tylko system Windows Phone    |    Tylko system Windows Phone    |    Nie dotyczy    |
|    iOS<sup>(3)</sup>    |    Dostępne    |    Dostępne    |    Dostępne    |    Dostępne    |    Dostępne    |    Dostępne    |    Nie dotyczy    |
|    MacOS<sup>(3)</sup><sup>(5)</sup>    |    Dostępne    |    Nie dotyczy    |    Dostępne    |    Dostępne    |    Dostępne    |    Nie dotyczy    |    Dostępne<sup>(2)</sup>    |
|    Android<sup>(3)</sup>    |    Dostępne<sup>(7)</sup>    |    Dostępne<sup>(7)</sup>    |    Dostępne    |    Dostępne    |    Dostępne    |    Dostępne<sup>(6)</sup>    |    Nie dotyczy    |


<sup>(1)</sup> Wycofanie jest zawsze zablokowane na urządzeniach z systemem Windows dołączonych do usługi Azure AD.<br>
<sup>(2)</sup> Odzyskiwanie klucza osobistego dla systemu macOS jest dostępne tylko w witrynie Portal firmy.<br> 
<sup>(3)</sup> Wszystkie akcje zdalne są wyłączone w przypadku korzystania z rejestracji Menedżera rejestracji urządzeń.<br>
<sup>(4)</sup> Zmiana nazwy zmienia nazwę urządzenia tylko w aplikacji lub w witrynie Portal firmy, a nie na urządzeniu.<br>
<sup>(5)</sup> Zdalne czyszczenie nie jest dostępne na urządzeniach z systemem MacOS.<br>
<sup>(6)</sup> Resetowanie kodu dostępu nie jest obsługiwane w niektórych konfiguracjach systemów Android i Android Enterprise. Aby uzyskać więcej informacji, zobacz [Resetowanie lub usuwanie kodu dostępu urządzenia w usłudze Intune](../remote-actions/device-passcode-reset.md).<br>
<sup>(7)</sup> Wycofywanie i czyszczenie nie jest dostępne w scenariuszach właściciela urządzenia z systemem Android Enterprise (COPE, COBO, COSU).<br> 

## <a name="next-steps"></a>Następne kroki

- [Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10 przy użyciu usługi Microsoft Intune](company-portal-app.md)
