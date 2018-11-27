---
title: Zasady dotyczące urządzeń, profilów oraz pytania i odpowiedzi dla usługi Intune — Azure | Microsoft Docs
description: Przeczytaj informacje na temat różnych zasad i profilów, których możesz używać w usłudze Microsoft Intune, łącznie z zasadami konfigurowania urządzeń, uzyskiwania dostępu do zasobów firmy, włączania dostępu warunkowego i rejestrowania urządzeń firmowych. Możesz też uzyskać odpowiedzi na często zadawane pytania.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3b1115a91707c639caba6410ace3c2e255e40a39
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185002"
---
# <a name="manage-settings-and-features-on-your-devices-with-intune-policies"></a>Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Intune

*Zasady* usługi Microsoft Intune są grupami ustawień kontrolujących funkcje na komputerach i urządzeniach przenośnych. Tworzysz zasady, używając szablonów zawierających zalecane lub niestandardowe ustawienia. Następnie wdrażasz je w grupach urządzeń lub użytkowników.

## <a name="types-of-policies"></a>Typy zasad

Zasady usługi Intune można podzielić na następujące kategorie. Używana kategoria wpływa na sposób tworzenia i wdrażania zasad.

- **Zasady konfiguracji**: często używane do zarządzania ustawieniami zabezpieczeń i funkcjami na urządzeniach, łącznie z dostępem do zasobów firmy. Rozpocznij pracę w [profilach urządzeń usługi Intune](device-profiles.md).
- **Zasady zgodności urządzeń**: definiują reguły i ustawienia, z którymi urządzenie musi być zgodne, aby można je było uważać za spełniające zasady dostępu warunkowego. Zasady zgodności mogą być również wykorzystane do monitorowania i rozwiązywania kwestii związanych ze zgodnością urządzeń niezależnie od dostępu warunkowego. Rozpocznij pracę w [zasadach zgodności urządzeń](device-compliance-get-started.md).
- **Zasady dostępu warunkowego**: ułatwiają zabezpieczanie poczty e-mail i innych usług w oparciu o wprowadzone warunki. [Co to jest dostęp warunkowy](conditional-access.md) i [typowe sposoby korzystania z dostępu warunkowego](conditional-access-intune-common-ways-use.md) są dobrymi zasobami, od których można rozpocząć pracę.
- **Zasady rejestracji urządzeń firmowych**: aby uzyskać informacje na temat zasad rejestracji urządzeń firmowych, zobacz [Rejestrowanie urządzeń z systemem iOS](ios-enroll.md).

## <a name="frequently-asked-questions-about-intune-policies"></a>Często zadawane pytania dotyczące zasad usługi Intune

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-being-deployed"></a>Jak długo trwa pobieranie zasad lub aplikacji przeznaczonych dla urządzeń przenośnych po ich wdrożeniu?
Po wdrożeniu zasad lub aplikacji usługa Intune natychmiast rozpoczyna powiadamianie urządzenia o konieczności jego zaewidencjonowania przez usługę Intune. Ten krok trwa zazwyczaj mniej niż pięć minut.

Jeśli urządzenie nie zostanie zaewidencjonowane w celu pobrania zasad po wysłaniu pierwszego powiadomienia, usługa Intune przeprowadzi trzy kolejne próby.  Jeśli urządzenie działa w trybie offline (tak, jak wtedy, gdy zostało wyłączone lub nie zostało podłączone do sieci), może nie odbierać powiadomień. W takim przypadku urządzenie pobiera zasady podczas następnego zaplanowanego ewidencjonowania przy użyciu usługi Intune w następujący sposób:

| Platforma | Częstotliwość ewidencjonowania |
| --- | --- |
| iOS | Co 6 godzin | 
| Mac OS X | Co 6 godzin |
| Android | Co 8 godzin | 
| Windows Phone | Co 8 godzin | 
| Windows 8.1  | Co 8 godzin |  
| Komputery z systemem Windows 10 zarejestrowane jako urządzenia | Co 8 godzin | 

Jeśli urządzenie zostało właśnie zarejestrowane, częstotliwość ewidencjonowania jest większa:

| Platforma | Częstotliwość |
| --- | --- |
| iOS | Co 15 minut przez 6 godzin, a następnie co 6 godzin |  
| Mac OS X | Co 15 minut przez 6 godzin, a następnie co 6 godzin | 
| Android | Co 3 minuty przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 
| Windows Phone | Co 5 minut przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 
| Komputery z systemem Windows zarejestrowane jako urządzenia | Co 3 minuty przez 30 minut, a następnie co 8 godzin | 

Użytkownicy mogą także otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast w dowolnym momencie wyszukać zasady.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Jakie akcje mogą spowodować natychmiastowe wysłanie powiadomienia do urządzenia z usługi Intune?
Urządzenia są ewidencjonowane przy użyciu usługi Intune po otrzymaniu powiadomienia z poleceniem zaewidencjonowania lub podczas zaplanowanego ewidencjonowania.  Jeśli akcja, taka jak czyszczenie, blokowanie, resetowanie kodu dostępu, wdrażanie aplikacji, wdrażanie profilu (Wi-Fi, VPN, poczta e-mail) lub wdrażanie zasad, zostanie rozpoczęta dla określonego urządzenia lub użytkownika, usługa Intune natychmiast podejmie próbę powiadomienia urządzenia o konieczności zaewidencjonowania w usłudze Intune.

Inne zmiany, takie jak zmiana informacji kontaktowych w portalu firmy, nie powodują natychmiastowego wysłania powiadomienia do urządzeń.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-are-applied"></a>Jeśli dla tego samego użytkownika lub urządzenia wdrożono wiele zasad, jak mogę zidentyfikować zastosowane ustawienia?
Jeśli co najmniej dwie zasady są wdrażane dla tego samego użytkownika lub urządzenia, ocena ustawień do zastosowania odbywa się na poziomie indywidualnego ustawienia:

- Ustawienia zasad zgodności mają zawsze pierwszeństwo przed ustawieniami zasad konfiguracji.

- Jeśli ocena dotyczy tego samego ustawienia w innych zasadach zgodności, zostanie zastosowane najbardziej restrykcyjne ustawienie zasad zgodności.

- Jeśli ustawienie zasad konfiguracji powoduje konflikt z ustawieniem w innych zasadach konfiguracji, ten konflikt jest wyświetlany w usłudze Intune. Należy ręcznie rozwiązać te konflikty.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-applies-to-the-app"></a>Co się stanie w przypadku wystąpienia konfliktu zasad zarządzania aplikacjami mobilnymi? Która z nich ma zastosowanie do aplikacji?
Wartości powodujące konflikt to najbardziej restrykcyjne ustawienia dostępne w zasadach zarządzania aplikacjami mobilnymi, z wyjątkiem pól wprowadzania liczb (służących na przykład do podejmowania prób wpisania kodu PIN przed zresetowaniem).  Pola wprowadzania liczb są ustawiane na wartości, który zostałyby użyte w przypadku utworzenia zasad zarządzania aplikacjami mobilnymi w konsoli przy użyciu opcji zalecanych ustawień.

Konflikty występują, jeśli dwa ustawienia zasad są takie same.  Można na przykład skonfigurować dwie identyczne zasady zarządzania aplikacjami różniące się jedynie ustawieniem kopiowania/wklejania.  W tym scenariuszu operacja kopiowania/wklejania jest ustawiana na najbardziej restrykcyjną wartość, ale pozostałe ustawienia są stosowane zgodnie z konfiguracją.

Jeśli jedne zasady zostały wdrożone w aplikacji i obowiązują, a następnie wdrażane są drugie, pierwsza aplikacja ma pierwszeństwo i jest stosowana. Drugie zasady spowodują wystąpienie konfliktu. Jeśli zostaną one zastosowane w tym samym czasie, tj. żadne zasady nie będą mieć pierwszeństwa, i jedne, i drugie zasady są w konflikcie. Wszystkie ustawienia powodujące konflikt są ustawiane na bardziej restrykcyjne wartości.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Co się stanie w przypadku konfliktu zasad niestandardowych systemu iOS?
Usługa Intune nie ocenia ładunku plików konfiguracji firmy Apple lub niestandardowych zasad OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Służy ona jedynie jako mechanizm dostarczania.

Podczas wdrażania niestandardowych zasad potwierdź, że skonfigurowane ustawienia nie pozostają w konflikcie z zasadami zgodności, konfiguracji lub innymi zasadami niestandardowymi. Jeśli wystąpi konflikt zasad niestandardowych z ustawieniami, ustawienia będą stosowane w kolejności losowej.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Co się stanie, gdy zasady zostaną usunięte lub nie będą już miały zastosowania?
Usunięcie zasad lub usunięcie urządzenia z grupy, w której zostały wdrożone zasady, powoduje usunięcie zasad i ustawień z urządzenia zgodnie z następującymi listami.

#### <a name="enrolled-devices"></a>zarejestrowane urządzenia

- Profile sieci Wi-Fi, sieci VPN, certyfikatu i poczty e-mail: te profile są usuwane ze wszystkich obsługiwanych zarejestrowanych urządzeń.
- Wszystkie inne typy zasad:
  - **Urządzenia z systemami Windows i Android**: ustawienia nie są usuwane z urządzenia.
  - **Urządzenia z systemem Windows Phone 8.1**: następujące ustawienia są usuwane:
    - Wymagaj hasła do odblokowania urządzeń przenośnych
    - Zezwalaj na proste hasła
    - Minimalna długość hasła
    - Wymagany typ hasła
    - Wygaśnięcie hasła w dniach
    - Pamiętaj historię haseł
    - Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia
    - Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła
    - Wymagany typ hasła — minimalna liczba zestawów znaków
    - Zezwalaj na używanie aparatu
    - Wymagaj szyfrowania na urządzeniu przenośnym
    - Zezwalaj na używanie magazynu wymiennego
    - Zezwalaj na używanie przeglądarki sieci Web
    - Zezwalaj na korzystanie ze sklepu z aplikacjami
    - Zezwalaj na przechwytywanie ekranu
    - Zezwalaj na używanie funkcji geolokalizacji
    - Zezwalaj na konto Microsoft
    - Zezwalaj na kopiowanie i wklejanie
    - Zezwalaj na tethering Wi-Fi
    - Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi
    - Zezwalaj na raportowanie informacji o punktach hotspot Wi-Fi
    - Zezwalaj na czyszczenie
    - Zezwalaj na połączenia Bluetooth
    - Zezwalaj na komunikację NFC
    - Zezwalaj na połączenia Wi-Fi

  - **iOS**: wszystkie ustawienia są usuwane, z wyjątkiem:
    - Zezwalaj na roaming połączeń głosowych
    - Zezwalaj na roaming danych
    - Zezwalaj na automatyczną synchronizację podczas roamingu

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Gdzie mogę znaleźć pomoc w rozwiązywaniu problemów dotyczących zasad?

Zobacz [Rozwiązywanie problemów z zasadami](troubleshoot-policies-in-microsoft-intune.md).
