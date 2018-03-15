---
title: "Rozwiązywanie problemów z profilami urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs"
description: "Typowe problemy związane z profilami urządzeń, w tym zmiany w profilach niezastosowane wobec niektórych urządzeń i użytkowników, czas wypchnięcia nowych zasad do urządzeń, ustawienia stosowane w przypadku wielu zasad, co się stanie po usunięciu profilu i inne informacje związane z usługą Microsoft Intune w witrynie Azure Portal"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 1/17/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73bac7c139a0dd42734ce6528172aeba2cb7b40c
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="common-issues-and-resolutions-with-device-profiles-in-microsoft-intune"></a>Typowe problemy dotyczące profilów urządzeń w usłudze Microsoft Intune i sposoby ich rozwiązania

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Rozwiązywanie typowych problemów związanych z użytkowaniem profilów urządzeń w usłudze Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Dlaczego użytkownik nie otrzymuje nowego profilu po zmianie hasła lub kodu dostępu w istniejącym profilu sieci Wi-Fi? 
W ramach tej procedury utworzysz profil sieci Wi-Fi firmy, wdrożysz profil w grupie, zmienisz hasło i zapiszesz profil. Jeśli profil ulegnie zmianom, niektórzy użytkownicy mogą nie otrzymać nowego profilu.

Aby zminimalizować ten problem, skonfiguruj sieć Wi-Fi dla gości. Jeśli firmowa sieć Wi-Fi ulegnie awarii, użytkownicy będą mogli połączyć się z siecią Wi-Fi dla gości. Należy włączyć wszelkie ustawienia związane z automatycznym nawiązywaniem połączenia. Wdróż profil sieci Wi-Fi dla gości u wszystkich użytkowników.

Niektóre zalecenia dodatkowe:  

- Ponieważ sieć Wi-Fi, z którą nawiązujesz połączenie, używa hasła lub kodu dostępu, upewnij się, że możesz łączyć się bezpośrednio z routerem sieci Wi-Fi. Możesz przeprowadzić test za pomocą urządzenia z systemem iOS.
- Po pomyślnym nawiązaniu połączenia z punktem końcowym sieci Wi-Fi (routerem sieci Wi-Fi) zanotuj identyfikator SSID i używane poświadczenia (tą wartością jest hasło lub kod dostępu).
- Wprowadź identyfikator SSID i poświadczenia (hasło lub kod dostępu) w polu Klucz wstępny. 
- Przeprowadź wdrożenie w grupie testowej, zawierającej ograniczoną liczbę użytkowników, najlepiej tylko w zespole IT. 
- Zsynchronizuj urządzenie z systemem iOS z usługą Intune. Zarejestruj się, jeśli jeszcze nie dokonano rejestracji. 
- Ponownie przetestuj połączenie z tym samym punktem końcowym sieci Wi-Fi (jak wspomniano w pierwszym kroku).
- Przeprowadź wdrożenie w większych grupach i ostatecznie dla wszystkich oczekiwanych użytkowników w organizacji. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Jak długo trwa pobieranie zasad lub aplikacji na urządzenia przenośne po ich przypisaniu?
Po przypisaniu zasad lub aplikacji usługa Intune natychmiast rozpoczyna powiadamianie urządzenia o konieczności jego zaewidencjonowania przez usługę Intune. Powiadamianie zazwyczaj zajmuje mniej niż pięć minut.

Jeśli urządzenie nie zostanie zaewidencjonowane w celu pobrania zasad po wysłaniu pierwszego powiadomienia, usługa Intune przeprowadzi trzy kolejne próby. Jeśli urządzenie działa w trybie offline (na przykład zostało wyłączone lub nie zostało podłączone do sieci), może nie odbierać powiadomień. W takim przypadku urządzenie pobiera zasady podczas następnego zaplanowanego zaewidencjonowania przy użyciu usługi Intune w następujący sposób:

- iOS i macOS: co sześć godzin
- Android: co osiem godzin
- Windows Phone: co osiem godzin
- Komputery z systemem Windows 8.1 i Windows 10 zarejestrowane jako urządzenia: co osiem godzin

Jeśli urządzenie zostało właśnie zarejestrowane, częstotliwość zaewidencjonowania jest większa:

- iOS i macOS: co 15 minut przez sześć godzin, a następnie co sześć godzin
- Android: co trzy minuty przez 15 minut, następnie co 15 minut przez dwie godziny, a następnie co osiem godzin
- Windows Phone: co pięć minut przez 15 minut, następnie co 15 minut przez dwie godziny, a następnie co osiem godzin
- Komputery z systemem Windows zarejestrowane jako urządzenia: co trzy minuty przez 30 minut, a następnie co osiem godzin

Użytkownicy mogą także otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast w dowolnym momencie wyszukać zasady.

W przypadku urządzeń bez koligacji użytkownika częstotliwość synchronizacji natychmiast po rejestracji może być różna i wynosić od kilku godzin do jednego dnia lub więcej. Usługa Intune wysyła żądania w różnych interwałach w celu zaewidencjonowania urządzenia przy użyciu usługi. Jednak wykonanie zaewidencjonowania nadal należy do urządzenia. Po początkowej rejestracji, w zależności od typu rejestracji urządzenia oraz zasad i profilów przypisanych do urządzenia, nie można przewidzieć, jak długo zajmie urządzeniu ukończenie tego zaewidencjonowania. Jednak po zarejestrowaniu urządzenia i zastosowaniu wszystkich początkowych zasad urządzenie typowo będzie wyszukiwać nowe zasady co około sześć godzin.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Jakie akcje mogą spowodować natychmiastowe wysłanie powiadomienia do urządzenia z usługi Intune?
Urządzenia są zaewidencjonowywane przy użyciu usługi Intune po otrzymaniu powiadomienia z poleceniem zaewidencjonowania lub podczas zaplanowanego zaewidencjonowania. Jeśli akcja, taka jak czyszczenie, blokowanie, resetowanie kodu dostępu, przypisywanie aplikacji, przypisywanie profilu lub przypisywanie zasad, została rozpoczęta dla określonego urządzenia lub użytkownika, usługa Intune natychmiast powiadomi urządzenie o konieczności jego zaewidencjonowania w usłudze Intune w celu odbierania aktualizacji.

Inne zmiany, takie jak zmiana informacji kontaktowych w Portalu firmy, nie powodują natychmiastowego wysłania powiadomienia do urządzeń.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Jeśli do tego samego użytkownika lub urządzenia przypisano wiele zasad, jak mogę zidentyfikować ustawienia do zastosowania?
Jeśli co najmniej dwie zasady są przypisane do tego samego użytkownika lub urządzenia, ocena ustawień do zastosowania odbywa się na poziomie indywidualnego ustawienia:

-   Ustawienia zasad zgodności mają zawsze pierwszeństwo przed ustawieniami zasad konfiguracji

-   Jeśli ocena zasad zgodności dotyczy tego samego ustawienia w innych zasadach zgodności, zostanie zastosowane najbardziej restrykcyjne ustawienie zasad zgodności.

-   Jeśli ustawienie zasad konfiguracji powoduje konflikt z ustawieniem w innych zasadach konfiguracji, ten konflikt jest wyświetlany w witrynie Azure Portal. W tym scenariuszu należy ręcznie rozwiązać te konflikty.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Co się dzieje, gdy zasady ochrony aplikacji powodują konflikt? Które z nich są stosowane w aplikacji?
Wartości powodujące konflikt to najbardziej restrykcyjne ustawienia dostępne w zasadach ochrony aplikacji, z wyjątkiem pól wprowadzania liczb (na przykład liczby prób wpisania numeru PIN przed zresetowaniem). Pola wprowadzania liczb są ustawiane na wartości, który zostałyby użyte w przypadku utworzenia zasad zarządzania aplikacjami mobilnymi w konsoli przy użyciu opcji zalecanych ustawień.

Konflikty występują, jeśli dwa ustawienia profilów są takie same. Można na przykład skonfigurować dwie identyczne zasady zarządzania aplikacjami różniące się jedynie ustawieniem kopiowania/wklejania. W tym scenariuszu operacja kopiowania/wklejania jest ustawiana na najbardziej restrykcyjną wartość, ale pozostałe ustawienia są stosowane zgodnie z konfiguracją.

Jeśli jeden profil zostaje przypisany do aplikacji i zaczyna obowiązywać, po czym zostaje przypisany drugi profil, pierwszy z nich ma pierwszeństwo i nadal jest stosowany, natomiast drugi powoduje wystąpienie konfliktu. Jeśli oba profile są stosowane w tym samym czasie, tj. żaden nie ma pierwszeństwa, oba profile są w konflikcie. Wszystkie ustawienia powodujące konflikt są ustawiane na bardziej restrykcyjne wartości.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co się stanie w przypadku konfliktu zasad niestandardowych systemu iOS?
Usługa Intune nie ocenia ładunku plików konfiguracji firmy Apple ani niestandardowego profilu OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Służy ona jedynie jako mechanizm dostarczania.

Podczas przypisywania profilu niestandardowego upewnij się, że skonfigurowane ustawienia nie pozostają w konflikcie z zasadami zgodności, konfiguracją lub innymi zasadami niestandardowymi. Jeśli profil niestandardowy i jego ustawienia wchodzą w konflikt, ustawienia zostaną zastosowane losowo.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co się stanie, gdy profil zostanie usunięty lub nie będzie już miał zastosowania?
Usunięcie profilu lub usunięcie urządzenia z grupy zawierającej profil powoduje usunięcie profilu i ustawień z urządzenia zgodnie z następującymi listami:

- Profile sieci Wi-Fi, sieci VPN, certyfikatu i poczty e-mail: te profile są usuwane ze wszystkich obsługiwanych zarejestrowanych urządzeń.
- Wszystkie pozostałe typy profilów:  
    - **Urządzenia z systemami Windows i Android**: ustawienia nie są usuwane z urządzenia
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
        - Zezwalaj na resetowanie do ustawień fabrycznych
        - Zezwalaj na połączenia Bluetooth
        - Zezwalaj na komunikację NFC
        - Zezwalaj na połączenia Wi-Fi

    - **iOS**: wszystkie ustawienia są usuwane, z wyjątkiem:
        - Zezwalaj na roaming połączeń głosowych
        - Zezwalaj na roaming danych
        - Zezwalaj na automatyczną synchronizację podczas roamingu

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Profil ograniczeń urządzenia został zmieniony, ale zmiany nie zostały zastosowane
Urządzenia z systemem Windows Phone nie zezwalają na obniżenie bezpieczeństwa zasad zabezpieczeń ustawionych wcześniej przy użyciu usługi MDM lub EAS. Na przykład po ustawieniu dla zasady **Minimalna liczba znaków hasła** wartości 8 nastąpiła próba jej zmniejszenia do 4. Bardziej restrykcyjny profil został już zastosowany do urządzenia.

Zmiana profilu na wartość mniej bezpieczną w zależności od platformy urządzenia będzie wiązać się ze zresetowaniem zasad zabezpieczeń. Na przykład w systemie Windows na pulpicie szybko przesuń palcem od prawej strony i wybierz pozycję **Ustawienia** > **Panel sterowania**. Wybierz aplet **Konta użytkowników** .

W menu nawigacji po lewej stronie (u dołu ekranu) znajduje się link **Resetuj zasady zabezpieczeń**. Wybierz go, a następnie wybierz opcję **Resetuj zasady**. W przypadku innych urządzeń MDM, takich jak urządzenia z systemami Android, Windows Phone 8.1 lub nowszym oraz iOS, zastosowanie mniej restrykcyjnego profilu może wymagać wycofania i ponownego zarejestrowania urządzenia w usłudze.

## <a name="next-steps"></a>Następne kroki
Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).