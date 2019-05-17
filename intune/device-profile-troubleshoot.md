---
title: Rozwiązywanie problemów z profilami urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Typowe pytania i odpowiedzi związane z zasadami i profilami urządzeń, w tym zmiany w profilach niezastosowane wobec urządzeń i użytkowników, czas wypychania nowych zasad do urządzeń, ustawienia stosowane w przypadku wielu zasad, co się stanie po usunięciu profilu i inne informacje związane z usługą Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12ac2b93126f271bf4918c6a914dedc7a22c1010
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461009"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Typowe pytania, problemy i rozwiązania związane z zasadami i profilami urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uzyskaj odpowiedzi na pytania często zadawane podczas pracy z zasadami i profilami urządzeń w usłudze Intune. Ten artykuł zawiera także listę interwałów czasu zaewidencjonowania, dalsze szczegóły dotyczące konfliktów i inne informacje.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Dlaczego użytkownik nie otrzymuje nowego profilu po zmianie hasła lub kodu dostępu w istniejącym profilu sieci Wi-Fi?

W ramach tej procedury utworzysz profil sieci Wi-Fi firmy, wdrożysz profil w grupie, zmienisz hasło i zapiszesz profil. Jeśli profil ulegnie zmianom, niektórzy użytkownicy mogą nie otrzymać nowego profilu.

Aby zminimalizować ten problem, skonfiguruj sieć Wi-Fi dla gości. Jeśli firmowa sieć Wi-Fi ulegnie awarii, użytkownicy będą mogli połączyć się z siecią Wi-Fi dla gości. Należy włączyć wszelkie ustawienia związane z automatycznym nawiązywaniem połączenia. Wdróż profil sieci Wi-Fi dla gości u wszystkich użytkowników.

Niektóre zalecenia dodatkowe:  

- Jeśli sieć Wi-Fi, z którą nawiązujesz połączenie, używa hasła lub kodu dostępu, upewnij się, że możesz łączyć się bezpośrednio z routerem sieci Wi-Fi. Możesz przeprowadzić test za pomocą urządzenia z systemem iOS.
- Po pomyślnym nawiązaniu połączenia z punktem końcowym sieci Wi-Fi (routerem sieci Wi-Fi) zanotuj identyfikator SSID i używane poświadczenia (tą wartością jest hasło lub kod dostępu).
- Wprowadź identyfikator SSID i poświadczenia (hasło lub kod dostępu) w polu Klucz wstępny. 
- Przeprowadź wdrożenie w grupie testowej, zawierającej ograniczoną liczbę użytkowników, najlepiej tylko w zespole IT. 
- Zsynchronizuj urządzenie z systemem iOS z usługą Intune. Zarejestruj się, jeśli jeszcze nie dokonano rejestracji. 
- Ponownie przetestuj połączenie z tym samym punktem końcowym sieci Wi-Fi (jak wspomniano w pierwszym kroku).
- Przeprowadź wdrożenie w większych grupach i ostatecznie dla wszystkich oczekiwanych użytkowników w organizacji. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Jak długo trwa pobieranie zasad lub aplikacji na urządzenia przenośne po ich przypisaniu?

Po przypisaniu zasad lub aplikacji usługa Intune natychmiast rozpoczyna powiadamianie urządzenia o konieczności jego zaewidencjonowania przez usługę Intune. Powiadamianie zazwyczaj zajmuje mniej niż pięć minut.

Jeśli urządzenie nie zostanie zaewidencjonowane w celu pobrania zasad po pierwszym powiadomieniu, usługa Intune przeprowadzi trzy kolejne próby. Urządzenie w trybie offline (np. wyłączone lub niepodłączone do sieci) może nie odbierać powiadomień. W takim przypadku urządzenie pobiera zasady podczas następnego zaplanowanego ewidencjonowania przy użyciu usługi Intune, czyli:

| Platforma | Cykl odświeżania|
| --- | --- |
| iOS | Co 6 godzin |
| macOS | Co 6 godzin |
| Android | Co 8 godzin |
| Komputery z systemem Windows 10 zarejestrowane jako urządzenia | Co 8 godzin |
| Windows Phone | Co 8 godzin |
| Windows 8.1 | Co 8 godzin |

Jeśli urządzenie zostało ostatnio zarejestrowane, ewidencjonowanie jest uruchamiane częściej:

| Platforma | Częstotliwość |
| --- | --- |
| iOS | Co 15 minut przez 6 godzin, a następnie co 6 godzin |  
| Mac OS X | Co 15 minut przez 6 godzin, a następnie co 6 godzin | 
| Android | Co 3 minuty przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 
| Windows Phone | Co 5 minut przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 
| Komputery z systemem Windows zarejestrowane jako urządzenia | Co 3 minuty przez 30 minut, a następnie co 8 godzin | 

W dowolnym momencie użytkownicy mogą otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast wyszukiwać aktualizacje profilów.

W przypadku urządzeń bez koligacji użytkownika częstotliwość synchronizacji natychmiast po rejestracji może być różna i wynosić od kilku godzin do jednego dnia lub więcej. Usługa Intune wysyła żądania w różnych interwałach w celu zaewidencjonowania urządzenia w usłudze Intune. Jednak wykonanie zaewidencjonowania nadal należy do urządzenia. Nie można przewidzieć, ile czasu zajmie ukończenie ewidencjonowania na urządzeniu po początkowej rejestracji. Zależy to również od typu rejestracji urządzenia, a także zasad i profilów przypisanych do urządzenia. Po zarejestrowaniu urządzenia i zastosowaniu wszystkich początkowych zasad urządzenie przeważnie wyszukuje nowe zasady co 6–8 godzin.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Jakie akcje mogą spowodować natychmiastowe wysłanie powiadomienia do urządzenia z usługi Intune?

Urządzenia są zaewidencjonowywane przy użyciu usługi Intune po otrzymaniu powiadomienia z poleceniem zaewidencjonowania lub podczas zaplanowanego zaewidencjonowania. Jeśli akcja, taka jak blokowanie, resetowanie kodu dostępu, przypisywanie aplikacji, przypisywanie profilu lub zasad, została rozpoczęta dla określonego urządzenia lub użytkownika, usługa Intune natychmiast powiadamia urządzenie o konieczności jego zaewidencjonowania w celu odbierania aktualizacji.

Inne zmiany, takie jak zmiana informacji kontaktowych w portalu firmy, nie powodują natychmiastowego wysłania powiadomienia do urządzeń.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Jeśli do tego samego użytkownika lub urządzenia przypisano wiele zasad, jak mogę zidentyfikować ustawienia do zastosowania?

Jeśli co najmniej dwie zasady zostały przypisane do tego samego użytkownika lub urządzenia, ustawienie jest stosowane na poziomie indywidualnego ustawienia:

- Ustawienia zasad zgodności mają zawsze pierwszeństwo przed ustawieniami profilu konfiguracji.

- Jeśli ocena zasad zgodności dotyczy tego samego ustawienia w innych zasadach zgodności, zostanie zastosowane najbardziej restrykcyjne ustawienie zasad zgodności.

- Jeśli ustawienie zasad konfiguracji powoduje konflikt z ustawieniem w innych zasadach konfiguracji, ten konflikt jest wyświetlany w usłudze Intune. Należy ręcznie rozwiązać te konflikty.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Co się dzieje, gdy zasady ochrony aplikacji powodują konflikt? Które z nich są stosowane w aplikacji?

Wartości powodujące konflikt to najbardziej restrykcyjne ustawienia dostępne w zasadach ochrony aplikacji, *z wyjątkiem* pól wprowadzania liczb, takich jak liczba prób wpisania numeru PIN przed zresetowaniem. Pola wprowadzania liczb są ustawiane na wartości, który zostałyby użyte w przypadku utworzenia zasad zarządzania aplikacjami mobilnymi przy użyciu opcji zalecanych ustawień.

Konflikty występują, jeśli dwa ustawienia profilów są takie same. Można na przykład skonfigurować dwie identyczne zasady zarządzania aplikacjami różniące się jedynie ustawieniem kopiowania/wklejania. W tym scenariuszu operacja kopiowania/wklejania jest ustawiana na najbardziej restrykcyjną wartość, ale pozostałe ustawienia są stosowane zgodnie z konfiguracją.

Zasady są wdrażane w aplikacji i zaczynają obowiązywać. Następuje wdrożenie drugich zasad. W tym scenariuszu pierwsze zasady mają pierwszeństwo i są nadal stosowane. Drugie zasady powodują wystąpienie konfliktu. Jeśli obydwie zasady zostaną zastosowane w tym samym czasie, tj. żadne zasady nie będą mieć pierwszeństwa, i jedne, i drugie zasady są w konflikcie. Wszystkie ustawienia powodujące konflikt są ustawiane na bardziej restrykcyjne wartości.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co się stanie w przypadku konfliktu zasad niestandardowych systemu iOS?

Usługa Intune nie ocenia ładunku plików konfiguracji firmy Apple lub niestandardowych zasad OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Służy ona jedynie jako mechanizm dostarczania.

Podczas przypisywania niestandardowych zasad potwierdź, że skonfigurowane ustawienia nie pozostają w konflikcie z zasadami zgodności, konfiguracji lub innymi zasadami niestandardowymi. Jeśli zasady niestandardowe i ich ustawienia wchodzą w konflikt, ustawienia zostaną zastosowane losowo.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co się stanie, gdy profil zostanie usunięty lub nie będzie już miał zastosowania?

Usunięcie profilu lub usunięcie urządzenia z grupy zawierającej profil powoduje usunięcie profilu i ustawień z urządzenia, jak opisano poniżej:

- Profile sieci Wi-Fi, sieci VPN, certyfikatu i poczty e-mail: te profile są usuwane ze wszystkich obsługiwanych zarejestrowanych urządzeń.
- Wszystkie pozostałe typy profilów:  

  - **Urządzenia z systemami Windows i Android**: ustawienia nie są usuwane z urządzenia
  - **Urządzenia z systemem Windows Phone 8.1**: Następujące ustawienia zostaną usunięte:  
  
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Profil ograniczeń urządzenia został zmieniony, ale zmiany nie zostały zastosowane

Po ustawieniu urządzenia z systemem Windows Phone nie zezwalają na obniżenie bezpieczeństwa zasad zabezpieczeń przy użyciu usługi MDM lub EAS. Na przykład opcja **Minimalna liczba znaków hasła** została ustawiona na wartość 8. Spróbuj zmniejszyć jej wartość do 4. Bardziej restrykcyjny profil został już zastosowany do urządzenia.

Aby zmienić wartość na obniżającą poziom zabezpieczeń profilu, zresetuj zasady zabezpieczeń. Na przykład w systemie Windows 8.1 na pulpicie szybko przesuń palcem od prawej strony > wybierz pozycję **Ustawienia** > **Panel sterowania**. Wybierz aplet **Konta użytkowników** . W menu nawigacji po lewej stronie (u dołu ekranu) znajduje się link **Resetuj zasady zabezpieczeń**. Wybierz go, a następnie wybierz opcję **Resetuj zasady**.

W przypadku innych urządzeń MDM, takich jak urządzenia z systemem Android, Windows Phone 8.1 lub nowszym, iOS oraz Windows 10, zastosowanie mniej restrykcyjnego profilu może wymagać wycofania i ponownego zarejestrowania urządzenia w usłudze Intune.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Niektóre ustawienia w profilu systemu Windows 10 zwracają komunikat „Nie dotyczy”

Niektóre ustawienia na urządzeniach z systemem Windows 10 mogą być wyświetlane jako „Nie dotyczy”. Oznacza to, że to konkretne ustawienie nie jest obsługiwane w wersji lub wydaniu systemu Windows uruchomionym na urządzeniu. Ten komunikat może być wyświetlany z następujących powodów:

- Ustawienie jest dostępne tylko dla nowszych wersji systemu Windows, a nie dla bieżącej wersji systemu operacyjnego urządzenia.
- Ustawienie jest dostępne tylko dla konkretnych wersji systemu Windows lub jednostek SKU, na przykład Home, Professional, Enterprise lub Education.

Aby dowiedzieć się więcej na temat wymagań dotyczących ustawień dla konkretnych wersji lub jednostek SKU, zobacz [Configuration Service Provider (CSP) reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (Dokumentacja dostawcy usług konfiguracji — CSP).

## <a name="next-steps"></a>Następne kroki

Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
