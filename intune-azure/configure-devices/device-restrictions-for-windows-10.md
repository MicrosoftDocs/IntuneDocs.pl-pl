---
title: "Ustawienia ograniczeń urządzenia w usłudze Intune dla systemu Windows 10 | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji urządzeń z systemem Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 422826ded029eb8f17856e47e98f5a09dc36bc08


---

# <a name="windows-10-and-later-device-restriction-settings-in-intune-azure-preview"></a>Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Ogólne
-   **Przechwytywanie ekranu** — umożliwia użytkownikowi przechwytywanie ekranu urządzenia w formie obrazu. (Tylko Windows 10 Mobile)
-   **Kopiuj i wklej (tylko urządzenia przenośne)** — umożliwia kopiowanie i wklejanie między aplikacjami na urządzeniu.
-   **Ręczne wyrejestrowanie**— umożliwia użytkownikowi ręczne usunięcie konta firmowego z urządzenia.
-   **Ręczne instalowanie głównego certyfikatu** -  
-   **Przesyłanie danych diagnostycznych** — możliwe wartości to:
    -       **Brak** — do firmy Microsoft nie są wysyłane żadne dane.
    -       **Podstawowe** — do firmy Microsoft są wysyłane ograniczone informacje.
    -       **Rozszerzone** — do firmy Microsoft są wysyłane rozszerzone dane diagnostyczne.
    -       **Pełne** — wysyłane są te same dane, co w przypadku wartości Rozszerzone, oraz dodatkowe dane dotyczące stanu urządzenia.
-   **Aparat fotograficzny** — umożliwia lub blokuje użycie aparatu fotograficznego urządzenia.
-   **Magazyn wymienny** — określa, czy na urządzeniu można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD.
-   **Geolokalizacja** — określa, czy urządzenie może używać informacji z usług lokalizacyjnych.
-   **Udostępnianie Internetu** — umożliwia udostępnianie połączenia internetowego przy użyciu urządzenia.
-   **Resetowanie telefonu** — określa, czy użytkownik może zresetować urządzenie do ustawień fabrycznych.
-   **Połączenie USB** — określa, czy urządzenia mogą uzyskiwać dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB.
-   **Tryb ochrony przed kradzieżą** — włącza tryb systemu Windows do ochrony przed kradzieżą.
-   **Powiadomienia centrum akcji** — włącza lub wyłącza powiadomienia centrum akcji na ekranie blokady urządzenia (tylko system Windows 10 Mobile).
-   **Cortana** — włącza lub wyłącza asystenta głosowego Cortana.
-   **Nagrywanie głosu** — umożliwia lub blokuje użycie rejestratora głosu na urządzeniu.

## <a name="password"></a>Hasło
-   **Wymagane jest hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
-   **Wymagany typ hasła** — określa, czy hasło musi być wyłącznie numeryczne, czy też alfanumeryczne.
-   **Minimalna długość hasła** — dotyczy tylko systemu Windows 10 Mobile.
-   **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — jeśli na urządzeniu z systemem Windows 10 jest włączona funkcja BitLocker, po określonej liczbie nieudanych prób logowania zostanie ono przełączone w tryb odzyskiwania funkcji BitLocker. Jeśli na urządzeniu nie jest włączona funkcja BitLocker, to ustawienie nie będzie miało zastosowania.
Na urządzeniach z systemem Windows 10 Mobile: po określonej liczbie niepowodzeń logowania urządzenie zostanie wyczyszczone.
-   **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
-   **Wygaśnięcie hasła (dni)** — określa czas, po którym należy zmienić hasło urządzenia.
-   **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.
-   **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności** — określa, że użytkownik musi wprowadzić hasło, aby odblokować urządzenie (tylko system Windows 10 Mobile).
-   **Szyfrowanie** — włącza szyfrowanie na urządzeniach docelowych (tylko system Windows 10 Mobile).
## <a name="app-store"></a>App Store

-   **App Store (tylko dla urządzeń przenośnych)** — umożliwia lub blokuje korzystanie ze sklepu z aplikacjami na urządzeniach z systemem Windows 10 Mobile.
## <a name="edge-browser"></a>Przeglądarka Microsoft Edge
-   **Przeglądarka Microsoft Edge (tylko urządzenia przenośne)** — umożliwia korzystanie z przeglądarki Edge na urządzeniu.
-   **SmartScreen** — włącza lub wyłącza filtr SmartScreen, który blokuje fałszywe witryny sieci Web.
-   **Wysyłaj nagłówki Nie śledź** — umożliwia skonfigurowanie przeglądarki Edge do wysyłania nagłówków „Nie śledź” do witryn sieci Web odwiedzanych przez użytkowników.
-   **Pliki cookie** — umożliwia przeglądarce na urządzeniu zapisywanie plików cookie z Internetu.
-   **JavaScript** — umożliwia uruchamianie skryptów (takich jak JavaScript) w przeglądarce Edge.
-   **Wyskakujące okienka** — umożliwia blokowanie wyskakujących okienek w przeglądarce.<br>(Dotyczy tylko systemu Windows 10 Desktop).
-   **Sugestie wyszukiwania** — umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz.
-   **Wysyłaj ruch intranetowy do programu Internet Explorer** — umożliwia użytkownikom otwieranie intranetowych witryn sieci Web w programie Internet Explorer. <br>(Tylko system Windows 10 Desktop).
-   **Autowypełnianie** — umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce.<br>(Tylko Windows 10 Desktop)
-   **Menedżer haseł** — włącza lub wyłącza funkcję menedżera haseł w przeglądarce Edge.
-   **Lokalizacja listy witryn trybu przedsiębiorstwa** — określa lokalizację listy witryn sieci Web, które można otwierać w trybie przedsiębiorstwa. Użytkownicy nie mogą edytować tej listy.<br>(Tylko system Windows 10 Desktop).
## <a name="cloud-and-storage"></a>Chmura i magazyn
-   **Konto Microsoft** — umożliwia użytkownikowi skojarzenie konta Microsoft z urządzeniem.
-   **Konto inne niż Microsoft** — umożliwia użytkownikowi dodanie na urządzeniu kont poczty e-mail, które nie są skojarzone z kontem Microsoft.
-   **Synchronizacja ustawień dla konta Microsoft** — zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między różnymi urządzeniami.
## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność
-   **Roaming danych** — umożliwia roaming między sieciami podczas uzyskiwania dostępu do danych.
-   **Sieć VPN przez sieć komórkową** — określa, czy urządzenie połączone z siecią komórkową może uzyskiwać dostęp do sieci VPN.
-   **Roaming sieci VPN przez sieć komórkową** — określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej.
-   **Bluetooth** — określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
-   **Odnajdowanie Bluetooth** — umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
-   **Rozgłaszanie Bluetooth** — umożliwia odbieranie reklam przez urządzenie za pośrednictwem połączenia Bluetooth.
-   **NFC** — umożliwia użytkownikowi włączanie i konfigurowanie funkcji komunikacji zbliżeniowej na urządzeniu.
-   **Wi-Fi** — umożliwia użytkownikowi włączanie i konfigurowanie sieci Wi-Fi na urządzeniu (tylko system Windows 10 Mobile).
-   **Automatycznie łącz się z hotspotami Wi-Fi** — umożliwia automatyczne łączenie się przy użyciu urządzenia z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.
-   **Ręczna konfiguracja sieci Wi-Fi** — określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi (tylko system Windows 10 Mobile).
## <a name="defender"></a>Usługa Defender

-   **Monitorowanie w czasie rzeczywistym** — włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania.
-   **Monitorowanie zachowania** — umożliwia usłudze Defender sprawdzanie urządzeń pod kątem określonych wzorców podejrzanej aktywności.
-   **Network Inspection System (NIS)** — system inspekcji sieci (NIS, Network Inspection System) zapewnia ochronę urządzenia przed sieciowymi programami wykorzystującymi luki w zabezpieczeniach, używając sygnatur znanych luk w zabezpieczeniach z centrum Microsoft Endpoint Protection, co pomaga wykrywać i blokować ruch złośliwego oprogramowania.
-   **Skanuj wszystkie pobrane pliki** — określa, czy usługa Defender ma skanować wszystkie pliki pobierane z Internetu.
-   **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft** — umożliwia usłudze Defender skanowanie skryptów używanych przez przeglądarkę Internet Explorer.
-   **Dostęp użytkownika końcowego do narzędzia Defender** —określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników końcowych.
Jeśli to ustawienie zostanie zmienione, zmiany zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika końcowego.
-   **Interwał aktualizacji sygnatur (w godzinach)** — określa interwał sprawdzania dostępności nowych plików sygnatur przez usługę Defender.
-   **Monitoruj działanie plików i programów** — zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach.
-   **Dni przed usunięciem złośliwego oprogramowania poddanego kwarantannie** — umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane.
-   **Limit wykorzystania procesora CPU podczas skanowania** —pozwala ograniczyć użycie procesora CPU dozwolone dla procesów skanowania (w skali od **1** do **100**).
-   **Skanuj pliki archiwów** — zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.
-   **Skanuj przychodzące wiadomości e-mail** — zezwala usłudze Defender na skanowanie wiadomości e-mail dostarczanych do urządzenia.
-   **Skanuj dyski wymienne podczas pełnego skanowania** —umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.
-   **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania** — umożliwia usłudze Defender skanowanie plików na zamapowanych dyskach sieciowych.<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
-   **Skanuj pliki otwierane z folderów sieciowych** — umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach dostępnych za pośrednictwem ścieżki UNC).
Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
-   **Ochrona w chmurze** — zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.
-   **Monituj użytkowników przed przesłaniem próbki** — określa, czy do firmy Microsoft są automatycznie wysyłane pliki, które mogą wymagać dalszej analizy ze strony firmy Microsoft w celu określenia, czy są złośliwe.
-   **Godzina przeprowadzania codziennego szybkiego skanowania** — umożliwia zaplanowanie szybkiego skanowania wykonywanego codziennie o wybranej godzinie.
-   **Typ skanowania systemu do wykonania** — pozwala określić poziom skanowania wykonywanego w przypadku planowania skanowania systemu.
## <a name="defender-exclusions"></a>Wykluczenia programu Defender

-   **Pliki i foldery do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych plików lub folderów lub większej ich liczby, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.
-   **Rozszerzenia plików do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych rozszerzeń plików lub większej ich liczby, np. **JPG** lub **TXT**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym lub skanowania planowanego.
-   **Procesy do wyłączenia ze skanów i ochrony w czasie rzeczywistym** — umożliwia dodanie do listy wykluczeń pojedynczych procesów typu **EXE**, **COM** lub **SCR** lub większej ich liczby. Te procesy nie będą uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.



<!--HONumber=Feb17_HO1-->


