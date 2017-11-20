---
title: "Rozwiązywanie problemów z profilami urządzeń w usłudze Microsoft Intune"
titlesuffix: Azure portal
description: "Informacje zawarte w tym temacie ułatwiają rozwiązywanie problemów z profilami urządzeń usługi Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff950ce35c491ca576dc9cc77ab561e2cfef0381
ms.sourcegitcommit: 1df625330f4e8f7f661b5f2b9f16b5590971838d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2017
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Rozwiązywanie problemów z profilami urządzeń w usłudze Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Informacje przedstawione w tym temacie ułatwiają rozwiązywanie typowych problemów związanych z profilami urządzeń w usłudze Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Dlaczego użytkownik nie otrzymuje nowego profilu po zmianie hasła lub kodu dostępu w istniejącym profilu sieci Wi-Fi? 
Po utworzeniu profilu sieci Wi-Fi firmy, wdrożeniu profilu w grupie, zmianie hasła i zapisaniu profilu, możesz spodziewać się, że użytkownik otrzyma nowy profil. Jednak użytkownik może nie otrzymać nowego profilu. 

Aby zminimalizować ten problem, upewnij się, że masz skonfigurowaną sieć Wi-Fi gościa, aby użytkownik przechodził do sieci Wi-Fi gościa w razie awarii firmowej sieci Wi-Fi. Wymagane jest włączenie ustawienia Połącz automatycznie. Ten profil sieci Wi-Fi gościa musi być wdrożony dla wszystkich użytkowników.

Istnieją pewne dodatkowe najlepsze rozwiązania, które możesz zastosować:
- Ponieważ sieć Wi-Fi, z którą nawiązujesz połączenie, przyjmuje hasło lub kod dostępu, upewnij się, że możesz łączyć się bezpośrednio z routerem sieci Wi-Fi. Możesz przeprowadzić test za pomocą urządzenia z systemem iOS.
- Po pomyślnym nawiązaniu połączenia z punktem końcowym sieci Wi-Fi (routerem sieci Wi-Fi) zanotuj identyfikator SSID i używane poświadczenia (hasło lub kod dostępu).
- Wprowadź identyfikator SSID i poświadczenia (hasło lub kod dostępu) w polu Klucz wstępny. 
- Przeprowadź wdrożenie w grupie testowej, zawierającej ograniczoną liczbę użytkowników, najlepiej tylko w zespole IT. 
- Zsynchronizuj urządzenie z systemem iOS z usługą Intune. Zarejestruj się, jeśli jeszcze nie dokonano rejestracji. 
- Ponownie przetestuj połączenie z tym samym punktem końcowym sieci Wi-Fi (jak wspomniano w pierwszym kroku).
- Przeprowadź wdrożenie w większych grupach i ostatecznie dla wszystkich oczekiwanych użytkowników w organizacji. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Jak długo trwa pobieranie zasad lub aplikacji na urządzenia przenośne po ich przypisaniu?
Po przypisaniu zasad lub aplikacji usługa Intune natychmiast podejmuje próby powiadomienia urządzenia o konieczności jego zaewidencjonowania przez usługę Intune. Trwa to zazwyczaj mniej niż pięć minut.

Jeśli urządzenie nie zostanie zaewidencjonowane w celu pobrania zasad po wysłaniu pierwszego powiadomienia, usługa Intune przeprowadzi trzy kolejne próby.  Jeśli urządzenie działa w trybie offline (na przykład zostało wyłączone lub nie zostało podłączone do sieci), może nie odbierać powiadomień. W takim przypadku urządzenie pobierze zasady podczas następnego zaplanowanego zaewidencjonowania przy użyciu usługi Intune w następujący sposób:

- iOS i macOS: co 6 godzin.
- Android: co 8 godzin.
- Windows Phone: co 8 godzin.
- Komputery z systemem Windows 8.1 i Windows 10 zarejestrowane jako urządzenia: co 8 godzin.

Jeśli urządzenie zostało właśnie zarejestrowane, częstotliwość zaewidencjonowania będzie większa:

- iOS i macOS: co 15 minut przez 6 godzin, a następnie co 6 godzin.
- Android: co 3 minuty przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin.
- Windows Phone: co 5 minut przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin.
- Komputery z systemem Windows zarejestrowane jako urządzenia: co 3 minuty przez 30 minut, a następnie co 8 godzin.

Użytkownicy mogą także otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast w dowolnym momencie wyszukać zasady.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Jakie akcje mogą spowodować natychmiastowe wysłanie powiadomienia do urządzenia z usługi Intune?
Urządzenia są zaewidencjonowywane przy użyciu usługi Intune po otrzymaniu powiadomienia z poleceniem zaewidencjonowania lub podczas zaplanowanego zaewidencjonowania.  Jeśli akcja, taka jak czyszczenie, blokowanie, resetowanie kodu dostępu, przypisywanie aplikacji, przypisywanie profilu (sieci Wi-Fi, VPN, poczty e-mail itd.) lub przypisywanie zasad, zostanie rozpoczęta dla określonego urządzenia lub użytkownika, usługa Intune natychmiast podejmie próbę powiadomienia urządzenia o konieczności jego zaewidencjonowania w usłudze Intune w celu odbierania aktualizacji.

Inne zmiany, takie jak zmiana informacji kontaktowych w Portalu firmy, nie powodują natychmiastowego wysłania powiadomienia do urządzeń.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Jeśli do tego samego użytkownika lub urządzenia przypisano wiele zasad, jak mogę zidentyfikować ustawienia, które zostaną zastosowane?
Jeśli co najmniej dwie zasady są przypisane do tego samego użytkownika lub urządzenia, ocena stosowanych ustawień odbywa się na poziomie indywidualnego ustawienia:

-   Ustawienia zasad zgodności mają zawsze pierwszeństwo przed ustawieniami zasad konfiguracji.

-   Jeśli ocena dotyczy tego samego ustawienia w innych zasadach zgodności, zostanie zastosowane najbardziej restrykcyjne ustawienie zasad zgodności.

-   Jeśli ustawienie zasad konfiguracji powoduje konflikt z ustawieniem w innych zasadach konfiguracji, ten konflikt zostanie wyświetlony w witrynie Azure Portal. Takie konflikty należy rozwiązać ręcznie.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Co się dzieje, gdy zasady ochrony aplikacji powodują konflikt? Które z nich zostaną zastosowane w aplikacji?
Wartości powodujące konflikt to najbardziej restrykcyjne ustawienia dostępne w zasadach ochrony aplikacji, z wyjątkiem pól wprowadzania liczb (na przykład liczby prób wpisania numeru PIN przed zresetowaniem).  Pola wprowadzania liczb zostaną ustawione na wartości, który zostałyby użyte w przypadku utworzenia zasad zarządzania aplikacjami mobilnymi w konsoli przy użyciu opcji zalecanych ustawień.

Konflikty występują, jeśli dwa ustawienia profilów są takie same.  Można na przykład skonfigurować dwie identyczne zasady zarządzania aplikacjami różniące się jedynie ustawieniem kopiowania/wklejania.  W tym scenariuszu operacja kopiowania/wklejania zostanie ustawiona na najbardziej restrykcyjną wartość, ale pozostałe ustawienia będą stosowane zgodnie z konfiguracją.

Jeśli jeden profil zostaje przypisany do aplikacji i zaczyna obowiązywać, po czym zostaje przypisany drugi profil, pierwszy z nich będzie mieć pierwszeństwo i nadal będzie stosowany, natomiast drugi spowoduje wystąpienie konfliktu. Jeśli oba profile zostaną zastosowane w tym samym czasie, tj. żaden nie będzie mieć pierwszeństwa, oba profile będą w konflikcie. Wszystkie ustawienia powodujące konflikt zostaną ustawione na bardziej restrykcyjne wartości.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co się stanie w przypadku konfliktu zasad niestandardowych systemu iOS?
Usługa Intune nie ocenia ładunku plików konfiguracji firmy Apple ani niestandardowego profilu OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Służy ona jedynie jako mechanizm dostarczania.

Podczas przypisywania profilu niestandardowego upewnij się, że skonfigurowane ustawienia nie pozostają w konflikcie z zasadami zgodności, konfiguracją lub innymi zasadami niestandardowymi. Jeśli wystąpią konflikty ustawień profilu niestandardowego, ustawienia będą stosowane w kolejności losowej.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co się stanie, gdy profil zostanie usunięty lub nie będzie już miał zastosowania?
Usunięcie profilu lub usunięcie urządzenia z grupy, do której przypisano profil, powoduje usunięcie profilu i ustawień z urządzenia zgodnie z następującymi listami.

### <a name="enrolled-devices"></a>zarejestrowane urządzenia

- Profile sieci Wi-Fi, sieci VPN, certyfikatu i poczty e-mail: te profile są usuwane ze wszystkich obsługiwanych zarejestrowanych urządzeń.
- Wszystkie pozostałe typy profilów:
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
        - Zezwalaj na resetowanie do ustawień fabrycznych
        - Zezwalaj na połączenia Bluetooth
        - Zezwalaj na komunikację NFC
        - Zezwalaj na połączenia Wi-Fi

    - **iOS**: wszystkie ustawienia są usuwane, z wyjątkiem:
        - Zezwalaj na roaming połączeń głosowych
        - Zezwalaj na roaming danych
        - Zezwalaj na automatyczną synchronizację podczas roamingu

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Profil ograniczeń urządzenia został zmieniony, ale zmiany nie zostały zastosowane
Urządzenia z systemem Windows Phone nie zezwalają na obniżenie bezpieczeństwa zasad zabezpieczeń ustawionych wcześniej za pośrednictwem usługi MDM lub EAS. Na przykład po ustawieniu dla zasady **Minimalna liczba znaków hasła** wartości 8 nastąpiła próba jej zmniejszenia do 4. Bardziej restrykcyjny profil został już zastosowany do urządzenia.

Zmiana profilu na wartość mniej bezpieczną w zależności od platformy urządzenia może wymagać zresetowania zasad zabezpieczeń.
Na przykład w systemie Windows na pulpicie szybko przesuń palcem z prawej strony, aby otworzyć pasek **Panele funkcji** i wybierz pozycję **Ustawienia** &gt; **Panel sterowania**.  Wybierz aplet **Konta użytkowników** .
W menu nawigacji po lewej stronie u dołu ekranu znajduje się link **Resetuj zasady zabezpieczeń** . Wybierz go, a następnie wybierz przycisk **Resetuj zasady** .
W przypadku innych urządzeń MDM, takich jak urządzenia z systemami Android, Windows Phone 8.1 lub nowszym oraz iOS, zastosowanie mniej restrykcyjnego profilu może wymagać wycofania i ponownego zarejestrowania urządzenia w usłudze.


### <a name="next-steps"></a>Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](get-support.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).