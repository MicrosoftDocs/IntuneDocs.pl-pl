---
title: Ustawienia ograniczeń urządzeń dla systemu Android w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Zobacz listę wszystkich ustawień urządzenia z systemem Android, które można kontrolować i ograniczać w usłudze Microsoft Intune. Te ustawienia służą do kontrolowania hasła, uzyskiwania dostępu do sklepu Google Play, zezwalania na aplikacje lub ich zabraniania, kontrolowania ustawień przeglądarki, blokowania aplikacji, tworzenia kopii zapasowej w usłudze Google Cloud oraz kontrolowania opcji dotyczących wiadomości, głosu, roamingu danych, sieci Wi-Fi i połączenia Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e3b356cc7c09b00916c24340dbbe1923540889b
ms.sourcegitcommit: 1134ecd733356277b40eb1c7f2b318b36d387e00
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2018
ms.locfileid: "50915737"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings---intune"></a>Ustawienia ograniczeń urządzeń z systemami Android i Samsung Knox Standard w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano wszystkie ustawienia ograniczeń urządzenia, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z systemem Android.

>[!TIP]
>Jeśli żądane ustawienia nie są dostępne, możesz skonfigurować urządzenia przy użyciu [profilu niestandardowego](custom-settings-android.md).

## <a name="general"></a>Ogólne

- **Aparat fotograficzny** — umożliwia korzystanie z aparatu fotograficznego urządzenia.
- **Kopiuj i wklej (tylko rozwiązanie Samsung Knox)** — umożliwia używanie funkcji kopiowania i wklejania na urządzeniu.
- **Udostępnianie schowka między aplikacjami (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie ze schowka w celu kopiowania i wklejania między aplikacjami.
- **Przesyłanie danych diagnostycznych (tylko rozwiązanie Samsung Knox)** — uniemożliwia użytkownikowi przesyłanie danych diagnostycznych z urządzenia.
- **Czyszczenie (tylko rozwiązanie Samsung Knox)** — umożliwia użytkownikowi przeprowadzenie [czyszczenia](devices-wipe.md) na urządzeniu.
- **Geolokalizacja (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z informacji o lokalizacji na urządzeniu.
- **Wyłączanie (tylko rozwiązanie Samsung Knox)** — umożliwia użytkownikowi wyłączanie urządzenia.<br>Po wyłączeniu nie można ustawić opcji **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**.
- **Przechwytywanie ekranu (tylko rozwiązanie Samsung Knox)** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
- **Asystent głosowy (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z usługi i aplikacji S Voice na urządzeniu. Nie dotyczy asystenta Bixby ani asystenta głosowego ułatwień dostępu, który odczytuje zawartość ekranu na głos.
- **Usługa YouTube (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z aplikacji YouTube na urządzeniu.
- **Urządzenia udostępnione (tylko rozwiązanie Samsung Knox)** — umożliwia skonfigurowanie zarządzanego urządzenia z systemem Samsung Knox Standard jako urządzenia udostępnionego. W tym trybie użytkownicy końcowi mogą zalogować się na urządzeniu i wylogować się z niego przy użyciu swoich poświadczeń usługi Azure AD. Urządzenie nadal będzie zarządzane, niezależnie od tego, czy jest używane.<br>Gdy jest używana w połączeniu z profilem certyfikatu SCEP, funkcja ta umożliwia użytkownikom końcowym udostępnianie urządzenia z tym samym zestawem aplikacji wszystkim użytkownikom, ale przy użyciu ich własnych certyfikatów użytkownika SCEP.  Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.  Funkcja ta jest ograniczona tylko do aplikacji LOB.
- **Zablokuj możliwość zmiany daty i godziny (Samsung Knox)** — uniemożliwia użytkownikowi zmianę ustawień daty i godziny na urządzeniu. 

## <a name="password"></a>Hasło

- **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.|Tak|Tak|

    > [!NOTE]
    > Urządzenia Samsung Knox automatycznie wymagają 4-cyfrowego kodu PIN podczas rejestracji w usłudze zarządzania urządzeniami przenośnymi. Urządzenia z natywnym systemem Android mogą automatycznie wymagać kodu PIN w celu osiągnięcia zgodności z dostępem warunkowym.

- **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od 4 do 16 znaków).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — wprowadź maksymalną dopuszczalną liczbę minut braku aktywności przed automatycznym zablokowaniem ekranu. Na urządzeniu użytkownik końcowy nie może ustawić wartości czasu przekraczającej czas skonfigurowany w profilu. Użytkownik końcowy może ustawić niższą wartość czasu. Na przykład jeśli profil jest ustawiony na 15 minut, użytkownik końcowy może ustawić tę wartość na 5 minut. Użytkownik końcowy nie może ustawić tej wartości na 30 minut. 
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem zawartości urządzenia.
- **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
-  **Wymagany typ hasła** — określa wymagany poziom złożoności hasła oraz możliwość stosowania urządzeń biometrycznych. Wybierz spośród opcji:
    - **Ustawienie domyślne urządzenia**
    - **Zabezpieczenia biometryczne na niskim poziomie**
    - **Co najmniej numeryczne**
    - **Złożona wartość liczbowa** — powtarzające się lub kolejne cyfry (np. „1111” lub „1234”) są niedozwolone.<sup>1</sup>
    - **Co najmniej alfabetyczne**
    - **Co najmniej alfanumeryczne**
    - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu używaniu poprzednich haseł** —nie dopuszcza do tego, by użytkownik końcowy utworzył hasło, które było wcześniej używane.
- **Odblokowywanie odciskiem palca (tylko rozwiązanie Samsung Knox)** — umożliwia odblokowywanie obsługiwanych urządzeń odciskiem palca.
- **Blokada Smart Lock i inni agenci zaufania** — umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach z systemem Android (tylko system Samsung Knox Standard 5.0 lub nowszy). Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji. Na przykład można z tego skorzystać, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.
- **Szyfrowanie** — wymaga szyfrowania plików na urządzeniu.

    > [!NOTE]
    > Jeśli zasady szyfrowania są wymuszane, urządzenia Samsung Knox wymagają od użytkowników ustawienia złożonego 6-znakowego hasła jako kodu dostępu urządzenia.

<sup>1</sup> Przed przypisaniem tego ustawienia do urządzeń upewnij się, że aplikacja Portal firmy została zaktualizowana na tych urządzeniach do najnowszej wersji.

W przypadku skonfigurowania ustawienia **Złożona wartość liczbowa** i jego przypisania do urządzenia z systemem Android w wersji starszej niż 5.0 wystąpią opisane poniżej konsekwencje.
- Jeśli na urządzeniu jest uruchomiona aplikacja Portal firmy w wersji wcześniejszej niż 1704, do urządzenia nie będą mieć zastosowania żadne zasady dotyczące numeru PIN, a w witrynie Azure Portal będzie wyświetlany błąd.
- Jeśli uruchomiona jest aplikacja Portal firmy w wersji 1704 lub nowszej, można stosować tylko prosty numer PIN. To ustawienie nie jest obsługiwane w wersjach systemu Android wcześniejszych niż 5.0. W witrynie Azure Portal nie jest wyświetlany błąd.


## <a name="google-play-store"></a>Sklep Google Play

- **Sklep Google Play (tylko rozwiązanie Samsung Knox)** — umożliwia użytkownikowi dostęp do sklepu Google Play na urządzeniu.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z poniższych list dla urządzeń z systemami Android i Samsung Knox Standard:

Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których instalacja i uruchomienie przez użytkowników są zgłaszane.
Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.
Profile urządzeń zawierające ustawienia aplikacji z ograniczeniami należy przypisać do grup użytkowników.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji zgodnych i niezgodnych, wykonaj następujące działania:

W sekcji [Aplikacje w sklepie Google Play](https://play.google.com/store/apps) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj jej adres URL do schowka. Możesz teraz użyć tego adresu URL na listach zgodnych lub niezgodnych aplikacji.

Przykład: wyszukaj w [sekcji aplikacji sklepu Google Play](https://play.google.com/store/apps) aplikację **Microsoft Planner**. Użyj następującego adresu URL: **https://play.google.com/store/apps/details?id=com.microsoft.planner**.

### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć opcję **Importuj**, aby pobrać listę z pliku CSV. Użyj formatu <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*> lub kliknij przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.      

## <a name="browser"></a>Przeglądarka

- **Przeglądarka internetowa (tylko rozwiązanie Samsung Knox)** — określa, czy na urządzeniu można używać domyślnej przeglądarki internetowej.
- **Automatyczne wypełnianie (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z funkcji automatycznego wypełniania w przeglądarce internetowej.
- **Pliki cookie (tylko rozwiązanie Samsung Knox)** — umożliwia używanie plików cookie przez przeglądarkę internetową na urządzeniu.
- **Język JavaScript (tylko rozwiązanie Samsung Knox)** — umożliwia uruchamianie skryptów Java w przeglądarce internetowej na urządzeniu.
- **Okienka wyskakujące (tylko rozwiązanie Samsung Knox)** — umożliwia blokowanie wyskakujących okienek w przeglądarce internetowej.

## <a name="allow-or-block-apps"></a>Zezwalanie na aplikacje lub ich blokowanie

Te ustawienia pozwalają wskazać aplikacje, które mogą być instalowane lub uruchamiane wyłącznie na urządzeniach z rozwiązaniem Samsung Knox Standard.
Ponadto można również wskazać zainstalowane aplikacje ukryte dla użytkownika urządzenia. Użytkownicy nie mogą uruchamiać tych aplikacji.

- **Aplikacje, które mogą być instalowane (tylko rozwiązanie Samsung Knox Standard)**
- **Aplikacje, których uruchamianie jest blokowane (tylko rozwiązanie Samsung Knox Standard)**
- **Aplikacje ukryte przed użytkownikiem (tylko rozwiązanie Samsung Knox Standard)**

Dla każdego ustawienia skonfiguruj listę aplikacji, wykonując jedną z następujących czynności:

- **Dodaj aplikacje według nazwy pakietu** — opcja używana głównie w odniesieniu do aplikacji biznesowych. Wprowadź nazwę aplikacji i nazwę pakietu aplikacji.
- **Dodaj aplikacje według adresu URL** — wprowadź nazwę aplikacji i jej adres URL w sklepie Google Play.
- **Dodaj aplikacje zarządzane** — wybierz odpowiednią aplikację z listy aplikacji zarządzanych przy użyciu usługi Intune.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Kopia zapasowa w usłudze Google (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z funkcji tworzenia kopii zapasowych w usłudze Google.
- **Automatyczna synchronizacja konta Google (tylko rozwiązanie Samsung Knox)** — umożliwia automatyczną synchronizację ustawień konta Google.
- **Magazyn wymienny (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie na urządzeniu z magazynu wymiennego, np. karty SD.
- **Szyfrowanie na kartach pamięci (tylko rozwiązanie Samsung Knox)** — określa, czy karta pamięci urządzenia musi być szyfrowana.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Roaming połączeń do transmisji danych (tylko rozwiązanie Samsung Knox)** — umożliwia roaming danych, gdy urządzenie jest połączone z siecią komórkową.
- **Wiadomości SMS/MMS (tylko rozwiązanie Samsung Knox)** — umożliwia obsługę wiadomości SMS i MMS na urządzeniu.
- **Wybieranie głosowe (tylko rozwiązanie Samsung Knox)** — włącza lub wyłącza funkcję wybierania głosowego na urządzeniu.
- **Roaming połączeń głosowych (tylko rozwiązanie Samsung Knox)** — umożliwia roaming połączeń głosowych, gdy urządzenie jest połączone z siecią komórkową.
- **Łączność Bluetooth (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z łączności Bluetooth na urządzeniu.
- **Łączność NFC (tylko rozwiązanie Samsung Knox)** — umożliwia wykonywanie operacji korzystających z komunikacji zbliżeniowej na obsługiwanych urządzeniach.
- **Sieć Wi-Fi (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z funkcji sieci Wi-Fi na urządzeniu.
- **Tethering Wi-Fi (tylko rozwiązanie Samsung Knox)** — umożliwia korzystanie z funkcji tetheringu Wi-Fi na urządzeniu.

## <a name="kiosk"></a>Kiosk

Ustawienia kiosku dotyczą tylko urządzeń z rozwiązaniem Samsung Knox Standard i odnoszą się wyłącznie do aplikacji zarządzanych za pomocą usługi Intune.

- **Wybierz zarządzaną aplikację** — wybierz jedną z poniższych opcji, aby dodać co najmniej jedną zarządzaną aplikację, którą można uruchomić, gdy urządzenie jest w trybie kiosku. Na tym urządzeniu nie można uruchamiać żadnych innych aplikacji. Wstępnie zainstalowanych przeglądarek nie można zdefiniować jako aplikacji, która może zostać uruchomiona, gdy urządzenie jest w trybie kiosku. Jeśli wymagana jest przeglądarka, rozważ użycie programu [Managed Browser](app-configuration-managed-browser.md).
    - **Dodaj aplikacje według nazwy pakietu**
    - **Dodaj aplikacje przez adres URL**
    - **Dodaj aplikacje zarządzane**.
- **Przycisk usypiania ekranu** — włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.
- **Przyciski regulacji głośności** — włącza lub wyłącza przyciski regulacji głośności na urządzeniu.


## <a name="next-steps"></a>Następne kroki

Nadal korzystając z instrukcji opisanych w temacie [Jak skonfigurować ustawienia ograniczeń urządzeń](device-restrictions-configure.md) utwórz, a następnie przypisz profil ograniczeń urządzenia.
