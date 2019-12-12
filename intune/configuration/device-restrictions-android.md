---
title: Ustawienia ograniczeń urządzeń dla systemu Android w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Zobacz listę wszystkich ustawień urządzenia z systemem Android, które można kontrolować i ograniczać w usłudze Microsoft Intune. Te ustawienia służą do kontrolowania hasła, uzyskiwania dostępu do sklepu Google Play, zezwalania na aplikacje lub ich zabraniania, kontrolowania ustawień przeglądarki, blokowania aplikacji, tworzenia kopii zapasowej w usłudze Google Cloud oraz kontrolowania opcji dotyczących wiadomości, głosu, roamingu danych, sieci Wi-Fi i połączenia Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfc791450eec9f17be68228bb291ca89fd7d88ce
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506814"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-lists-in-intune"></a>Listy ustawień ograniczeń urządzeń z systemami Android i Samsung Knox Standard w usłudze Intune

W tym artykule opisano wszystkie ustawienia ograniczeń urządzenia, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z systemem Android.

>[!TIP]
>Jeśli żądane ustawienia nie są dostępne, możesz skonfigurować urządzenia przy użyciu [profilu niestandardowego](../custom-settings-android.md).

## <a name="general"></a>Ogólne

- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu. Pozycja **Nieskonfigurowane** zezwala na dostęp do aparatu urządzenia.
- **Kopiuj i wklej (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić kopiowanie i wklejanie. Pozycja **Nieskonfigurowane** umożliwia używanie funkcji kopiowania i wklejania na urządzeniu.
- **Udostępnianie schowka między aplikacjami (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić korzystanie ze schowka w celu kopiowania i wklejania między aplikacjami. Pozycja **Nieskonfigurowane** umożliwia wykorzystanie schowka do kopiowania i wklejania między aplikacjami.
- **Przesyłanie danych diagnostycznych (tylko rozwiązanie Samsung Knox)** : pozycja **Blokuj** uniemożliwia użytkownikowi przesyłanie danych diagnostycznych z urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na przesyłanie danych.
- **Czyszczenie (tylko rozwiązanie Samsung Knox)** : umożliwia użytkownikowi uruchamianie akcji [czyszczenia](../remote-actions/devices-wipe.md).
- **Geolokalizacja (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby wyłączyć używanie informacji o lokalizacji na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia urządzeniu korzystanie z informacji o lokalizacji.
- **Wyłączanie zasilania (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikowi wyłączanie zasilania urządzenia. Jeśli to ustawienie zostanie wyłączone, nie będzie można zdefiniować ustawienia **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** i nie będzie ono działać. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi wyłączanie urządzenia.
- **Przechwytywanie ekranu (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
- **Asystent głosowy (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby wyłączyć usługę S Voice. Pozycja **Nieskonfigurowane** umożliwia korzystanie z usługi i aplikacji S Voice na urządzeniu. To ustawienie nie ma zastosowania w przypadku asystenta Bixby ani asystenta głosowego ułatwień dostępu, który odczytuje zawartość ekranu na głos.
- **YouTube (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom korzystanie z aplikacji YouTube. Pozycja **Nieskonfigurowane** umożliwia używanie aplikacji YouTube na urządzeniu.
- **Urządzenia udostępnione (tylko rozwiązanie Samsung Knox)** : umożliwia skonfigurowanie zarządzanego urządzenia z systemem Samsung Knox Standard jako urządzenia udostępnionego. Po wybraniu ustawienia**Zezwalaj** użytkownicy końcowi mogą zalogować się na urządzeniu i wylogować się z niego przy użyciu swoich poświadczeń usługi Azure AD. Urządzenie pozostaje zarządzane, niezależnie od tego, czy jest używane.</br>Gdy jest używana z profilem certyfikatu SCEP, funkcja ta umożliwia użytkownikom końcowym udostępnianie urządzenia z tym samym zestawem aplikacji wszystkim użytkownikom. Jednak każdy użytkownik ma własny certyfikat użytkownika SCEP. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane. Funkcja ta jest ograniczona tylko do aplikacji LOB. </br>Pozycja **Nieskonfigurowane** uniemożliwia wielu użytkownikom końcowym logowanie do aplikacji Portal firmy na urządzeniu przy użyciu poświadczeń usługi Azure AD.
- **Zablokuj możliwość zmiany daty i godziny (Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikowi zmianę ustawień daty i godziny na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień daty i godziny.

## <a name="password"></a>Hasło

- **Hasło**: pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. Pozycja **Nieskonfigurowane** umożliwia użytkownikom uzyskiwanie dostępu do urządzenia bez wprowadzania hasła.

    > [!NOTE]
    > Urządzenia Samsung Knox automatycznie wymagają 4-cyfrowego kodu PIN podczas rejestracji w usłudze zarządzania urządzeniami przenośnymi. Urządzenia z natywnym systemem Android mogą automatycznie wymagać kodu PIN w celu zapewnienia zgodności z dostępem warunkowym.

- **Minimalna długość hasła**: wprowadź minimalną długość hasła, które musi podać użytkownik (od 4 do 16 znaków).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: wprowadź maksymalną dopuszczalną liczbę minut braku aktywności przed automatycznym zablokowaniem ekranu. Na urządzeniu użytkownik końcowy nie może ustawić wartości czasu przekraczającej czas skonfigurowany w profilu. Użytkownik końcowy może ustawić niższą wartość czasu. Na przykład jeśli profil jest ustawiony na 15 minut, użytkownik końcowy może ustawić tę wartość na 5 minut. Użytkownik końcowy nie może ustawić tej wartości na 30 minut. 
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: wprowadź liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem zawartości urządzenia.
- **Wygaśnięcie hasła (dni)** : wprowadź liczbę dni, po której należy zmienić hasło urządzenia.
- **Wymagany typ hasła**: wprowadź wymagany poziom złożoności hasła oraz określ możliwość stosowania urządzeń biometrycznych. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone.<sup>1</sup>
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu używaniu poprzednich haseł**: nie dopuszcza do tego, by użytkownik końcowy utworzył hasło, które było wcześniej używane.
- **Odblokowywanie odciskiem palca (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić użycie odcisku palca do odblokowywania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu odcisku palca.
- **Blokada Smart Lock i inni agenci zaufania**: wybierz pozycję **Blokuj**, aby uniemożliwić funkcji Smart Lock lub innym agentom zaufania dostosowywanie ustawień blokady ekranu (Samsung KNOX Standard 5.0+). Ta funkcja telefonu, zwana również czasami agentem zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie znajduje się w zaufanej lokalizacji. Na przykład można skorzystać z tej funkcji, gdy urządzenie zostało połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.
- **Szyfrowanie**: wybierz pozycję **Wymagaj**, aby szyfrować pliki na urządzeniu. Nie wszystkie urządzenia obsługują szyfrowanie. W celu użycia tej funkcji można również: 
  1. Ustawić opcję **Hasło** na **Wymagaj**.
  2. Ustawić opcję **Wymagany typ hasła** na **Co najmniej numeryczne**.
  3. Ustaw opcję **Minimalna długość hasła** na co najmniej 4, aby poprawnie zgłaszać zgodność tego ustawienia.

  > [!NOTE]
  > Jeśli zasady szyfrowania są wymuszane, urządzenia Samsung Knox wymagają od użytkowników ustawienia złożonego 6-znakowego hasła jako kodu dostępu urządzenia.

<sup>1</sup> Przed przypisaniem tego ustawienia do urządzeń upewnij się, że aplikacja Portal firmy została zaktualizowana na tych urządzeniach do najnowszej wersji.

W przypadku ustawienia opcji **Wymagany typ hasła** na **Złożona wartość liczbowa** i przypisania jej do urządzenia z systemem Android w wersji starszej niż 5.0 wystąpi następujące zachowanie:

- Jeśli na urządzeniu jest uruchomiona aplikacja Portal firmy w wersji wcześniejszej niż 1704, do urządzenia nie będą mieć zastosowania żadne zasady dotyczące numeru PIN, a w witrynie Azure Portal zostanie pokazany błąd.
- Jeśli uruchomiona jest aplikacja Portal firmy w wersji 1704 lub nowszej, można stosować tylko prosty numer PIN. To ustawienie nie jest obsługiwane w wersjach systemu Android wcześniejszych niż 5.0. W witrynie Azure Portal nie jest wyświetlany żaden błąd.

## <a name="google-play-store"></a>Sklep Google Play

- **Sklep Google Play (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom korzystanie ze sklepu Google Play. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi uzyskiwanie dostępu do sklepu Google Play na urządzeniu.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Użyj tych ustawień, aby umożliwić lub uniemożliwić korzystanie z określonych aplikacji na urządzeniu. Ta funkcja jest obsługiwana na urządzeniach z systemem Android i rozwiązaniem Samsung Knox Standard:

- **Aplikacje zabronione**: lista aplikacji niezarządzanych przez usługę Intune, których nie chcesz instalować na urządzeniu. Jeśli użytkownik instaluje aplikację z tej listy, otrzymujesz powiadomienie z usługi Intune.
- **Aplikacje zatwierdzone**: lista aplikacji, które użytkownicy mogą instalować. Aby zachować zgodność, użytkownicy nie mogą instalować innych aplikacji. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.

Aby dodać aplikację do tych list, możesz:

- **Dodać** adres URL sklepu Google Play dla wybranej aplikacji. Aby na przykład dodać aplikację Pulpit zdalny firmy Microsoft dla systemu Android, wprowadź `https://play.google.com/store/apps/details?id=com.microsoft.rdc.android`. Aby znaleźć adres URL aplikacji, otwórz [sklep Google Play](https://play.google.com/store/apps) i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop Play Store` lub `Microsoft Planner`. Wybierz aplikację i skopiuj adres URL.
- Zaimportować plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu <*adres URL aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>. Możesz również **wyeksportować** istniejącą listę, który zawiera listę aplikacji z ograniczeniami w tym samym formacie.

> [!IMPORTANT]
> Profile urządzeń, które używają ustawień aplikacji z ograniczeniami, należy przypisać do grup użytkowników.

## <a name="browser"></a>Przeglądarka

- **Przeglądarka internetowa (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić używanie domyślnej przeglądarki internetowej na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia korzystanie z domyślnej przeglądarki internetowej urządzenia.
- **Autowypełnianie (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić automatyczne uzupełnianie tekstu w przeglądarce. Pozycja **Nieskonfigurowane** umożliwia korzystanie z funkcji automatycznego wypełniania w przeglądarce internetowej.
- **Pliki cookie (tylko rozwiązanie Samsung Knox)** : wybierz sposób obsługi plików cookie z witryn internetowych na urządzeniu. Dostępne opcje:
  - Zezwalaj
  - Blokuj wszystkie pliki cookie
  - Zezwalaj na pliki cookie z odwiedzonych witryn internetowych
  - Zezwalaj na pliki cookie z aktualnej witryny internetowej
- **JavaScript (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić uruchamianie skryptów języka Java w przeglądarce internetowej. Pozycja **Nieskonfigurowane** umożliwia przeglądarce internetowej urządzenia uruchamianie skryptów Java.
- **Wyskakujące okienka (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić wyświetlanie wyskakujących okienek w przeglądarce internetowej. Pozycja **Nieskonfigurowane** umożliwia wyświetlane wyskakujących okienek w przeglądarce internetowej.

## <a name="allow-or-block-apps"></a>Zezwalanie na aplikacje lub ich blokowanie

Te ustawienia umożliwiają zezwalanie na działanie aplikacji, ich blokowanie lub ukrywanie na urządzeniach z systemem Samsung Knox Standard. Aplikacji, które zostały ukryte, użytkownik nie może otwierać ani uruchamiać.

Dostępne opcje:

- **Aplikacje, które mogą być instalowane (tylko rozwiązanie Samsung Knox Standard)**
- **Aplikacje, których uruchamianie jest blokowane (tylko rozwiązanie Samsung Knox Standard)**
- **Aplikacje ukryte przed użytkownikiem (tylko rozwiązanie Samsung Knox Standard)**

Dla każdego ustawienia dodaj listę aplikacji. Dostępne opcje:

- **Dodaj aplikacje według nazwy pakietu**: opcja używana głównie w odniesieniu do aplikacji biznesowych. Wprowadź nazwę aplikacji i nazwę pakietu aplikacji.
- **Dodaj aplikacje według adresu URL**: wprowadź nazwę aplikacji i jej adres URL w sklepie Google Play.
- **Dodaj aplikację ze sklepu**: wybierz aplikację z istniejącej listy aplikacji, którymi zarządzasz w usłudze Intune.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Kopia zapasowa Google (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić synchronizowanie urządzenia z kopią zapasową Google. Pozycja **Nieskonfigurowane** pozwala na korzystanie z kopii zapasowych w usłudze Google.
- **Automatyczna synchronizacja z kontem Google (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić działanie funkcji automatycznej synchronizacji konta Google na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na automatyczną synchronizację ustawień konta Google.
- **Magazyn wymienny (tylko rozwiązanie Samsung Knox)** : wybierz **Blokuj**, aby uniemożliwić korzystanie z magazynu wymiennego na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie na urządzeniu magazynu wymiennego, takiego jak karta SD.
- **Szyfrowanie na kartach pamięci (tylko rozwiązanie Samsung Knox)** : pozycja **Wymagaj** wymusza szyfrowanie kart pamięci. Pozycja **Nieskonfigurowane** zezwala na używanie niezaszyfrowanych kart pamięci. Nie wszystkie urządzenia obsługują szyfrowanie kart pamięci. Aby to sprawdzić, skontaktuj się z producentem urządzenia.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Roaming danych (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić roaming danych w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.
- **Wiadomości SMS/MMS (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić obsługę wiadomości tekstowych na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia korzystanie z wiadomości SMS i MMS na urządzeniu.
- **Wybieranie głosowe (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom korzystanie z funkcji wybierania głosowego na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia wybieranie głosowe na urządzeniu.
- **Roaming połączeń głosowych (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić roaming połączeń głosowych w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.
- **Bluetooth (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić używanie połączenia Bluetooth na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie połączenia Bluetooth na urządzeniu.
- **NFC (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby zatrzymać działanie technologii NFC (Near Field Communication). Pozycja **Nieskonfigurowane** umożliwia wykonywanie operacji korzystających z komunikacji zbliżeniowej na obsługiwanych urządzeniach.
- **Wi-Fi (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić używanie sieci Wi-Fi na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie funkcji sieci Wi-Fi na urządzeniu.
- **Tethering Wi-Fi (tylko rozwiązanie Samsung Knox)** : wybierz pozycję **Blokuj**, aby uniemożliwić używanie tetheringu sieci Wi-Fi na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia korzystanie z funkcji tetheringu sieci Wi-Fi urządzenia.

## <a name="kiosk"></a>Kiosk

Ustawienia kiosku dotyczą tylko urządzeń z rozwiązaniem Samsung Knox Standard i odnoszą się wyłącznie do aplikacji zarządzanych za pomocą usługi Intune.

- Dodaj aplikacje, które chcesz uruchomić, gdy urządzenie będzie działać w trybie kiosku. W trybie kiosku tylko dodane aplikacje są uruchamiane. Aplikacje, które nie zostały dodane, nie będą uruchamiane. Wstępnie zainstalowane przeglądarki nie są uruchamiane jako aplikacje, gdy urządzenie działa w trybie kiosku. Jeśli wymagana jest przeglądarka, rozważ użycie programu [Managed Browser](../apps/app-configuration-managed-browser.md).

  Opcje aplikacji:

  - **Dodaj aplikacje według nazwy pakietu**: opcja używana głównie w odniesieniu do aplikacji biznesowych. Wprowadź nazwę aplikacji i nazwę pakietu aplikacji.
  - **Dodaj aplikacje według adresu URL**: wprowadź nazwę aplikacji i jej adres URL w sklepie Google Play.
  - **Dodaj aplikację ze sklepu**: wybierz aplikację z istniejącej listy aplikacji, którymi zarządzasz w usłudze Intune.

- **Przycisk usypiania ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie przycisku usypiania ekranu lub go ukryć. Pozycja **Nieskonfigurowane** włącza przycisk usypiania/budzenia ekranu na urządzeniu.
- **Przyciski regulacji głośności**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikowi dostosowywanie głośności, wyłączając przyciski regulacji głośności. Pozycja **Nieskonfigurowane** umożliwia korzystanie z przycisków regulacji głośności na urządzeniu.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](../device-profile-monitor.md).

Można również utworzyć profile kiosku dla urządzeń z systemem [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) i [Windows 10](kiosk-settings.md).
