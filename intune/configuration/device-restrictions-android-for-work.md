---
title: Ustawienia urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Na urządzeniach z systemem Android Enterprise lub Android for Work ogranicz ustawienia na urządzeniu, w tym kopiowanie i wklejanie, wyświetlanie powiadomień, uprawnienia aplikacji, udostępnianie danych, długość hasła, liczba nieudanych prób jego wprowadzenia, odblokowywanie za pomocą odcisku palca, ponowne użycie hasła oraz włączenie udostępniania kontaktów służbowych przez Bluetooth. Skonfiguruj urządzenie jako kiosk urządzenia dedykowanego w celu uruchamiania jednej aplikacji lub wielu aplikacji.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 904c3d2267decdfa3929bf29376c05a995c77eb8
ms.sourcegitcommit: f5108039f0ade52e95ea3ac1da1aa16d02224af3
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2019
ms.locfileid: "74946661"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem Android Enterprise. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, uruchamiać aplikacje na dedykowanych urządzeniach, kontrolować zabezpieczenia i nie tylko.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Tylko właściciel urządzenia

Te ustawienia dotyczą typów rejestracji w systemie Android Enterprise, w których usługa Intune kontroluje całe urządzenie, takie jak w pełni zarządzane lub dedykowane urządzenia z systemem Android Enterprise.

### <a name="general-settings"></a>Ustawienia ogólne

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów w urządzeniu. Zapobiega również wyświetlaniu zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Niewymagane** zezwala na dostęp do aparatu urządzenia.
- **Domyślne zasady uprawnień**: to ustawienie określa domyślne zasady uprawnień dla żądań uprawnień w środowisku uruchomieniowym. Dopuszczalne wartości to:
  - **Ustawienie domyślne urządzenia**: użyte zostaną ustawienia domyślne urządzenia.
  - **Monituj**: użytkownik jest monitowany o zatwierdzenie uprawnień.
  - **Automatycznie udzielaj**: uprawnienia są automatycznie udzielane.
  - **Automatycznie odmawiaj**: uprawnienia są automatycznie odrzucane.
- **Zmiany daty i godziny**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom ręczne ustawianie daty i godziny. Pozycja **Nieskonfigurowane** umożliwia użytkownikom ustawianie określonej daty i godziny na urządzeniu.
- **Zmiany woluminów**: **blokowanie** uniemożliwia użytkownikom zmianę woluminu urządzenia, a także wyciszenie woluminu głównego. Pozycja **Nieskonfigurowane** umożliwia korzystanie z ustawień głośności na urządzeniu.
- **Resetowanie do ustawień fabrycznych**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom używanie opcji resetowania do ustawień fabrycznych w ustawieniach urządzenia. Pozycja **Nieskonfigurowane** pozwala użytkownikom na używanie tego ustawienia na urządzeniu.
- **Bezpieczny rozruch**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom ponowne uruchamianie urządzenia w trybie awaryjnym. Pozycja **Nieskonfigurowane** pozwala użytkownikom na ponowne uruchamianie urządzenia w trybie awaryjnym.
- **Pasek stanu**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do paska stanu, w tym do powiadomień i szybkich ustawień. Pozycja **Nieskonfigurowane** zezwala użytkownikom na dostęp do paska stanu.
- **Usługi roamingu danych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming danych w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.
- **Zmiany ustawienia sieci Wi-Fi**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom zmienianie ustawień sieci Wi-Fi utworzonych przez właściciela urządzenia. Użytkownicy mogą tworzyć własne konfiguracje sieci Wi-Fi. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień sieci Wi-Fi na urządzeniu.
- **Konfiguracja punktu dostępu sieci Wi-Fi**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom tworzenie lub zmienianie konfiguracji sieci Wi-Fi. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień sieci Wi-Fi na urządzeniu.
- **Konfiguracja połączenia Bluetooth**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom konfigurowanie połączenia Bluetooth na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie połączenia Bluetooth na urządzeniu.
- **Tethering i dostęp do hotspotów**: wybierz pozycję **Blokuj**, aby uniemożliwić tethering i uzyskiwanie dostępu do przenośnych hotspotów. Pozycja **Nieskonfigurowane** zezwala na tethering i dostęp do przenośnych hotspotów.
- **Pamięć USB**: wybierz pozycję **Zezwalaj**, aby uzyskiwać dostęp do pamięci USB na urządzeniu. Pozycja **Nieskonfigurowane** uniemożliwia dostęp do pamięci USB.
- **Transfer plików USB**: wybierz pozycję **Blokuj**, aby uniemożliwić przesyłanie plików za pośrednictwem USB. Pozycja **Nieskonfigurowane** pozwala na transfer plików.
- **Nośniki zewnętrzne**: wybierz pozycję **Blokuj**, aby uniemożliwić korzystanie z nośników zewnętrznych i łączenie się z nimi na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na użycie nośników zewnętrznych na urządzeniu.
- **Przesyłaj dane za pomocą komunikacji NFC**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie technologii NFC (Near Field Communication) do przesyłania danych z aplikacji. Pozycja **Nieskonfigurowane** umożliwia używanie technologii NFC do udostępniania danych między urządzeniami.
- **Funkcje debugowania**: wybierz pozycję **Zezwalaj**, aby umożliwić użytkownikom korzystanie z funkcji debugowania na urządzeniu. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom korzystanie z funkcji debugowania na urządzeniu.
- **Dostosowanie mikrofonu**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom wyłączanie wyciszania mikrofonu i dostosowywanie jego głośności. Pozycja **Nieskonfigurowane** umożliwia użytkownikom używanie i dostosowywanie głośności mikrofonu na urządzeniu.
- **Adresy e-mail związane z ochroną po zastosowaniu funkcji resetowania do ustawień fabrycznych**: wybierz pozycję **Adresy e-mail konta Google**. Wprowadź adresy e-mail administratorów urządzenia, którzy mogą je odblokować po wyczyszczeniu zawartości. Pamiętaj, aby oddzielić adresy e-mail średnikami w następujący sposób: `admin1@gmail.com;admin2@gmail.com`. Jeśli nie wprowadzono adresu e-mail, każda osoba może odblokować urządzenie po przywróceniu go do ustawień fabrycznych. Te wiadomości e-mail mają zastosowanie tylko w przypadku uruchomienia resetowania do ustawień fabrycznych, takich jak uruchomienie resetowania do ustawień fabrycznych za pomocą menu odzyskiwanie.
- **Wyjście bezpieczeństwa sieci**: wybierz pozycję **Włącz**, aby umożliwić użytkownikom włączanie funkcji wyjścia bezpieczeństwa sieci. Jeśli podczas uruchamiania urządzenia nie nawiązano połączenia sieciowego, wyjście bezpieczeństwa wyświetli prośbę o tymczasowe połączenie z siecią i odświeżenie zasad urządzenia. Po zastosowaniu zasad sieć tymczasowa zostanie zapomniana, a urządzenie będzie kontynuować rozruch. Ta funkcja powoduje połączenie urządzeń z siecią, jeśli:
  - W ostatnich zasadach nie ma odpowiedniej sieci.
  - Urządzenie jest uruchamiane w aplikacji w trybie blokady zadania.
  - Użytkownik nie może używać ustawień urządzenia.

  Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom włączanie funkcji wyjścia bezpieczeństwa sieci na urządzeniu.

- **Aktualizacja systemu**: wybierz opcję, aby określić sposób obsługi aktualizacji bezprzewodowych przez urządzenie:
  - **Ustawienie domyślne urządzenia**: użyte zostaną ustawienia domyślne urządzenia.
  - **Automatyczne**: aktualizacje są automatycznie instalowane bez interakcji z użytkownikiem. Ustawienie tych zasad powoduje natychmiastowe instalowanie wszystkich oczekujących aktualizacji.
  - **Odłożone**: instalowanie aktualizacji jest odkładane o 30 dni. Po upływie tych 30 dni system Android monituje użytkownika o zainstalowanie aktualizacji. Producenci urządzeń i operatorzy mogą uniemożliwiać (wykluczać) odkładanie ważnych aktualizacji zabezpieczeń. Aktualizacja podlegająca takiemu wykluczeniu powoduje wyświetlenie użytkownikowi powiadomienia systemowego na urządzeniu.
  - **Okno obsługi**: aktualizacje są instalowane automatycznie w ramach codziennego okna obsługi skonfigurowanego w usłudze Intune. Próba instalacji jest podejmowana codziennie przez 30 dni i może zakończyć się niepowodzeniem ze względu na brak miejsca lub niski poziom baterii. Po upływie 30 dni system Android monituje użytkownika o instalację. To okno jest też używane do instalowania aktualizacji aplikacji ze sklepu Play. Tej opcji należy używać w przypadku urządzeń dedykowanych, takich jak kioski, ponieważ umożliwia ona aktualizowanie aplikacji na pierwszym planie dedykowanych urządzeń z pojedynczymi aplikacjami.

- **Okna powiadomień**: po ustawieniu opcji **Wyłącz** powiadomienia wyświetlane w oknach, w tym powiadomienia wyskakujące, powiadomienia o połączeniach przychodzących, połączeniach wychodzących, alerty systemowe i błędy systemowe, nie są wyświetlane na urządzeniu. Po ustawieniu opcji **Nieskonfigurowane** zostanie użyte domyślne ustawienie systemu operacyjnego, co może prowadzić do wyświetlania powiadomień.
- **Pomiń wskazówki dotyczące pierwszego użycia**: **Włącz** ukrywanie lub pomijanie sugestii z aplikacji, które przechodzenia przez samouczki lub wskazówki podczas uruchamiania aplikacji. Po ustawieniu opcji **Nieskonfigurowane** zostanie użyte domyślne ustawienie systemu operacyjnego, co może prowadzić do wyświetlania tych sugestii podczas uruchamiania aplikacji.

### <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

- **Skanowanie aplikacji pod kątem zagrożeń**: wybranie opcji **Wymagaj** (ustawienie domyślne) umożliwia skanowanie aplikacji przez usługę Google Play Protect przed instalacją i po instalacji. W przypadku wykrycia zagrożenia może pojawić się monit o usunięcie aplikacji z urządzenia. Wybranie opcji **Nieskonfigurowane** uniemożliwia skanowanie aplikacji przez usługę Google Play Protect.

### <a name="dedicated-device-settings"></a>Ustawienia dedykowanego urządzenia

Te ustawienia umożliwiają skonfigurowanie trybu kiosku na dedykowanych urządzeniach. Urządzenie można skonfigurować do uruchamiania pojedynczej aplikacji lub wielu aplikacji. Gdy urządzenie jest ustawione w trybie kiosku, dostępne są tylko dodane aplikacje. Te ustawienia mają zastosowanie do urządzeń dedykowanych z systemem Android Enterprise. Nie mają one zastosowania do w pełni zarządzanych urządzeń z systemem Android Enterprise.

**Tryb kiosku**: wybierz, czy na urządzeniu będzie uruchamiana jedna aplikacja czy wiele aplikacji.

- **Pojedyncza aplikacja**: użytkownicy mogą uzyskiwać dostęp tylko do jednej aplikacji na urządzeniu. Po uruchomieniu urządzenia zostanie uruchomiona tylko określona aplikacja. Użytkownicy nie mogą otwierać nowych aplikacji ani zmieniać uruchomionej aplikacji.

  - **Wybierz zarządzaną aplikację**: wybierz z listy aplikację z zarządzanego sklepu Google Play.

    Jeśli nie masz listy aplikacji, [dodaj wybrane aplikacje dla systemu Android](../apps/apps-add-android-for-work.md) do urządzenia. Pamiętaj, aby [przypisać aplikację](../apps/apps-deploy.md) do grupy urządzeń utworzonej na potrzeby dedykowanych urządzeń.

  > [!IMPORTANT]
  > W przypadku korzystania z trybu kiosku jednostronicowego aplikacje telefoniczne mogą nie działać prawidłowo. 
  
- **Wiele aplikacji**: użytkownicy mogą uzyskiwać dostęp do ograniczonego zestawu aplikacji na urządzeniu. Po uruchomieniu urządzenia zostaną uruchomione tylko dodane aplikacje. Można również dodać linki internetowe, które użytkownicy będą mogli otwierać. Po zastosowaniu zasad użytkownicy widzą ikony dozwolonych aplikacji na ekranie głównym.

  > [!IMPORTANT]
  > W przypadku dedykowanych urządzeń z wieloma aplikacjami [aplikacja Zarządzany ekran główny](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) ze sklepu Google Play **musi zostać**:
  >   - [Dodana jako aplikacja kliencka](../apps/apps-add-android-for-work.md) w usłudze Intune
  >   - [Przypisana do grupy urządzeń](../apps/apps-deploy.md) utworzonej na potrzeby dedykowanych urządzeń
  >
  > Aplikacja **Zarządzany ekran główny** nie musi znajdować się w profilu konfiguracji, ale trzeba ją dodać jako aplikację kliencką. Gdy aplikacja **Zarządzany ekran główny** zostanie dodana jako aplikacja kliencka, wszystkie inne aplikacje dodane w profilu konfiguracji będą wyświetlane jako ikony w aplikacji **Zarządzany ekran główny**.
  >
  > W przypadku korzystania z trybu kiosku dla aplikacji telefoner/aplikacje telefoniczne mogą nie działać prawidłowo. 

  - **Dodaj**: Wybierz swoje aplikacje z listy.

    Jeśli na liście nie ma aplikacji **Zarządzany ekran główny**, [dodaj ją ze sklepu Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Pamiętaj, aby [przypisać aplikację](../apps/apps-deploy.md) do grupy urządzeń utworzonej na potrzeby dedykowanych urządzeń.

    Na urządzeniu możesz również dodać inne [aplikacje dla systemu Android](../apps/apps-add-android-for-work.md) i [aplikacje internetowe](../apps/web-app.md) utworzone przez organizację. Pamiętaj, aby [przypisać aplikację](../apps/apps-deploy.md) do grupy urządzeń utworzonej na potrzeby dedykowanych urządzeń.

  - **Wirtualny przycisk Strona główna**: przycisk miękkiego klawisza, który zwraca użytkowników do zarządzanego ekranu głównego, aby użytkownicy mogli przełączać się między aplikacjami. Dostępne opcje:

    - **Nie skonfigurowano** (domyślnie): przycisk główny nie jest wyświetlany. Aby przełączać się między aplikacjami, użytkownicy muszą używać przycisku Wstecz.
    - **Przesuń w górę**: przycisk Home ukazuje się, gdy użytkownik szybko przesuwa się w urządzeniu.
    - **Przestawne**: pokazuje trwały, swobodny przycisk na urządzeniu.

  - **Wyjdź z trybu kiosku**: wybierz pozycję **Włącz**, aby umożliwić administratorom tymczasowe wstrzymywanie trybu kiosku w celu zaktualizowania urządzenia. Aby skorzystać z tej funkcji, administrator wykonuje następujące czynności:
  
    1. Wybiera przycisk Wstecz do momentu wyświetlenia przycisku **Wyjdź z kiosku**. 
    2. Wybiera przycisk **Wyjdź z kiosku**, a następnie wprowadza numer PIN dla opcji **Kod wychodzenia z trybu kiosku**.
    3. Po zakończeniu wybierz **zarządzaną aplikację ekranu głównego** . Ten krok powoduje ponowne zablokowanie urządzenia w trybie kiosku z wieloma aplikacjami.

      Jeśli ustawienie **nie zostanie skonfigurowane**, Administratorzy nie mogą wstrzymać trybu kiosku. Jeśli administrator wybiera przycisk Wstecz, a następnie przycisk **Wyjdź z kiosku**, pojawia się komunikat z informacją o tym, że kod dostępu jest wymagany.

    - **Kod wychodzenia z trybu kiosku**: wprowadź numer PIN składający się z 4–6 cyfr. Administrator używa tego numeru PIN do tymczasowego wstrzymywania trybu kiosku.

  - **Ustaw tło przy użyciu niestandardowego adresu URL**: wprowadź adres URL, aby dostosować ekran tła na dedykowanym urządzeniu.

    > [!NOTE]
    > W większości przypadków na początku zaleca się wybranie następujących rozmiarów obrazów:
    >
    > - Telefon: 1080 x 1920 pikseli
    > - Tablet: 1920 x 1080 pikseli
    >
    > Aby uzyskać najlepszy komfort i najwyższy poziom szczegółowości obrazu, zaleca się tworzenie zasobów obrazów dla poszczególnych urządzeń zgodnie ze specyfikacją wyświetlacza.
    >
    > Nowoczesne wyświetlacze mają wyższe gęstości pikseli i umożliwiają wyświetlanie obrazów 2K/4K.

  - **Konfiguracja sieci Wi-Fi**: wartość **Włącz** pokazuje formant sieci Wi-Fi na zarządzanym ekranie głównym oraz umożliwia użytkownikom końcowym łączenie się z różnymi sieciami WiFi. Włączenie tej funkcji powoduje włączenie lokalizacji urządzenia. **Nieskonfigurowane** (domyślnie) nie pokazuje kontrolki Wi-Fi na zarządzanym ekranie głównym. Uniemożliwia to użytkownikom łączenie się z sieciami Wi-Fi przy użyciu zarządzanego ekranu głównego.

  - **Konfiguracja Bluetooth**: **enable** wyświetla kontrolkę Bluetooth na zarządzanym ekranie głównym i umożliwia użytkownikom końcowym parowanie urządzeń za pośrednictwem połączenia Bluetooth. Włączenie tej funkcji powoduje włączenie lokalizacji urządzenia. **Nie skonfigurowano** (domyślnie) formant Bluetooth nie jest wyświetlany na zarządzanym ekranie głównym. Uniemożliwia to użytkownikom konfigurowanie urządzeń Bluetooth i parowania przy użyciu zarządzanego ekranu głównego.

  - **Flashlight Access**: **enable** pokazuje kontrolkę Flashlight na zarządzanym ekranie głównym, a użytkownicy końcowi mogą włączać lub wyłączać Flashlight. **Nie skonfigurowano** (wartość domyślna) nie pokazuje formantu Flashlight na zarządzanym ekranie głównym. Uniemożliwia to użytkownikom korzystanie z Flashlight przy użyciu zarządzanego ekranu głównego.

  - **Sterowanie woluminem multimedialnym**: **enable** pokazuje formant głośności multimediów na zarządzanym ekranie głównym i umożliwia użytkownikom końcowym dostosowanie woluminu multimedialnego urządzenia przy użyciu suwaka. **Nie skonfigurowano** (domyślnie) nie pokazuje kontroli głośności multimediów na zarządzanym ekranie głównym. Uniemożliwia to użytkownikom dostosowanie woluminu multimedialnego urządzenia przy użyciu zarządzanego ekranu głównego, chyba że ich przyciski sprzętowe go obsługują. 

  - **Tryb wygaszacza ekranu**: **enable** wyświetla wygaszacz ekranu na zarządzanym ekranie głównym, gdy urządzenie jest zablokowane lub przekracza limit czasu. **Nie skonfigurowano** (domyślnie) nie jest wyświetlany wygaszacz ekranu na zarządzanym ekranie głównym.

    Gdy ta funkcja jest włączona, należy również skonfigurować:

    - **Ustaw niestandardowy obraz wygaszacza ekranu**: wprowadź adres URL do niestandardowego formatu PNG, jpg, JPEG, GIF, BMP, WEBP lub ICOimage. Wprowadź na przykład:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.webp`

      Jeśli adres URL nie zostanie wprowadzony, zostanie użyty domyślny obraz urządzenia, jeśli istnieje obraz domyślny.
      
      > [!TIP]
      > Obsługiwane są wszystkie adresy URL zasobów plików, które mogą być przekształcone w mapę bitową.

    - **Liczba sekund, przez które urządzenie wyświetla wygaszacz ekranu przed wyłączeniem ekranu**: Wybierz, jak długo urządzenie ma wyświetlać wygaszacz ekranu. Wprowadź wartość z zakresu od 0-9999999 sekund. Wartość domyślna to `0` sekund. Jeśli pole pozostanie puste, lub ma wartość zero (`0`), wygaszacz ekranu będzie aktywny do momentu, gdy użytkownik nie współdziała z urządzeniem.
    - **Liczba sekund, przez które urządzenie jest nieaktywne przed wyświetleniem wygaszacza ekranu**: Określ, jak długo urządzenie jest bezczynne przed wyświetleniem ekranu. Wprowadź wartość z zakresu od 1-9999999 sekund. Wartość domyślna to `30` sekund. Należy wprowadzić liczbę większą od zera (`0`).
    - **Wykryj nośnik przed uruchomieniem wygaszacza ekranu**: **enable** (domyślnie) nie pokazuje wygaszacza ekranu, jeśli audio lub wideo są odtwarzane na urządzeniu. **Nieskonfigurowane** — wyświetla wygaszacz ekranu, nawet w przypadku odtwarzania dźwięku lub wideo.

### <a name="device-password-settings"></a>Ustawienia haseł urządzeń

- **Wyłącz pozycję Zablokuj ekran**: wybierz pozycję **Wyłącz**, aby uniemożliwić użytkownikom używanie funkcji blokady ekranu Blokada klawiatury na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z funkcji blokady klawiatury.
- **Wyłączone funkcje ekranu blokady**: jeśli blokada klawiatury jest włączona na urządzeniu, wybierz funkcje, które mają zostać wyłączone. Na przykład po zaznaczeniu opcji **Zabezpiecz aparat** funkcja aparatu zostanie wyłączona na urządzeniu. Wszystkie funkcje, które nie są zaznaczone, są włączone na urządzeniu.

  Te funkcje są dostępne dla użytkowników, gdy urządzenie jest zablokowane. Zaznaczone funkcje nie będą widoczne ani dostępne dla użytkowników.

- **Wymagany typ hasła**: określ typ hasła wymagany dla urządzenia. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Hasło jest wymagane, brak ograniczeń**
  - **Słabe elementy biometryczne**: [silne i słabe elementy biometryczne](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (zostanie otwarta witryna internetowa systemu Android)
  - **Numeryczne**: hasło może się składać tylko z cyfr, takich jak `123456789`. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Alfabetyczne**: wymagane są litery alfabetu. Cyfry ani symbole nie są wymagane. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Alfanumeryczne**: obejmuje wielkie litery, małe litery i cyfry. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Alfanumeryczne z symbolami**: obejmuje wielkie litery, małe litery, cyfry, znaki interpunkcyjne i symbole. Wprowadź też następujące ustawienia:

    - **Minimalna długość hasła**: podaj minimalną długość hasła (od 4 do 16 znaków).
    - **Wymagana liczba znaków**: podaj wymaganą liczbę znaków w haśle (od 0 do 16 znaków).
    - **Wymagana liczba małych liter**: podaj wymaganą liczbę małych liter w haśle (od 0 do 16 znaków).
    - **Wymagana liczba wielkich liter**: podaj wymaganą liczbę wielkich liter w haśle (od 0 do 16 znaków).
    - **Wymagana liczba znaków innych niż litery**: podaj wymaganą liczbę znaków innych niż litery w alfabecie, które muszą być zawarte w haśle (od 0 do 16 znaków).
    - **Wymagana liczba znaków numerycznych**: podaj wymaganą liczbę cyfr (`1`, `2`, `3` itd.) w haśle (od 0 do 16 znaków).
    - **Wymagana liczba symboli**: podaj wymaganą liczbę symboli (`&`, `#`, `%` itd.) w haśle (od 0 do 16 znaków).

- **Liczba dni, po których hasło wygasa**: podaj liczbę dni, po której należy zmienić hasło urządzenia (od 1 do 365). Na przykład aby wymusić zmianę hasła po upływie 60 dni, wprowadź `60`. Gdy hasło wygaśnie, użytkownicy będą monitowani o utworzenie nowego hasła.
- **Wymagana liczba haseł przed ponownym użyciem starego hasła przez użytkownika**: podaj liczbę kolejnych haseł, których nie można użyć ponownie (od 1 do 24). To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: wprowadź liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem urządzenia (od 4 do 11).

### <a name="power-settings"></a>Ustawienia zasilania

- **Ekran czasu do zablokowania**: Wprowadź maksymalny czas, jaki użytkownik może ustawić do momentu zablokowania urządzenia. Jeśli na przykład ustawisz to ustawienie na **10 minut**, użytkownicy będą mogli ustawić czas od 15 sekund do 10 minut. Jeśli ustawiono wartość **nie skonfigurowano** (wartość domyślna), usługa Intune nie zmieni ani nie kontroluje tego ustawienia.

- **Włączony ekran, gdy urządzenie jest podłączone**: wybierz źródła zasilania. Jeśli urządzenie będzie podłączone do jednego z nich, ekran urządzenia będzie włączony.

### <a name="users-and-accounts-settings"></a>Ustawienia użytkowników i kont

- **Dodawanie nowych użytkowników**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom dodawanie nowych użytkowników. Każdy użytkownik ma na urządzeniu obszar osobisty, który zawiera niestandardowe ekrany główne, konta, aplikacje i ustawienia. Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom dodawanie innych użytkowników na urządzeniu.
- **Usuwanie użytkowników**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom usuwanie użytkowników. Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom usuwanie innych użytkowników z urządzenia.
- **Zmiany konta** (tylko urządzenia dedykowane): wybierz opcję **Blokuj** , aby uniemożliwić użytkownikom modyfikowanie kont. Pozycja **Nieskonfigurowane** (domyślna) umożliwia użytkownikom aktualizowanie kont użytkowników na urządzeniu.

  > [!NOTE]
  > To ustawienie nie jest uznawane za urządzenia właściciel urządzenia (w pełni zarządzane). Jeśli skonfigurujesz to ustawienie, to ustawienie zostanie zignorowane i nie będzie miało wpływu.

- **Osobiste konta Google**: **blokowanie** uniemożliwia użytkownikom dodawanie do urządzenia osobistego konta Google. **Nie skonfigurowano** (domyślnie) umożliwia użytkownikom dodawanie osobistych kont Google.

### <a name="applications"></a>Aplikacje

- **Zezwalaj na instalację z nieznanych źródeł**: wybierz pozycję **Zezwalaj**, aby umożliwić użytkownikom włączanie opcji **Nieznane źródła**. To ustawienie umożliwia instalację aplikacji z nieznanych źródeł, innych niż Sklep Google Play. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom włączanie opcji **Nieznane źródła**.
- **Zezwalaj na dostęp do wszystkich aplikacji w sklepie Google Play**: po ustawieniu opcji **Zezwalaj** użytkownicy mogą uzyskiwać dostęp do wszystkich aplikacji w Sklepie Google Play. Nie mają oni dostępu do aplikacji zablokowanych przez administratora w obszarze [Aplikacje klienckie](../apps/apps-add-android-for-work.md). Po wybraniu opcji **Nieskonfigurowane** użytkownicy mogą uzyskiwać dostęp tylko do aplikacji udostępnionych przez administratora w Sklepie Google Play lub wymaganych w obszarze [Aplikacje klienckie](../apps/apps-add-android-for-work.md).
- **Automatyczne aktualizacje aplikacji**: wybierz moment instalowania aktualizacji automatycznych. Dostępne opcje:
  - **Nieskonfigurowany**
  - **Wybór użytkownika**
  - **Nigdy**
  - **Tylko sieć Wi-Fi**
  - **Zawsze**

### <a name="connectivity"></a>Łączność

- **Zawsze włączona sieć VPN**: wybierz pozycję **Włącz**, aby ustawić klienta sieci VPN tak, aby automatycznie łączył się i przywracał połączenie z siecią VPN. Zawsze włączone połączenia sieci VPN pozostają aktywne lub natychmiast łączą się, gdy użytkownik zablokuje urządzenie, urządzenie uruchomi się ponownie lub zmieni się sieć bezprzewodowa. 

  Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć zawsze włączoną sieć VPN dla wszystkich klientów sieci VPN.

  > [!IMPORTANT]
  > Należy pamiętać, aby dla jednego urządzenia wdrożyć tylko jedne zasady zawsze włączonej sieci VPN. Wdrażanie wielu zasad zawsze włączonej sieci VPN dla jednego urządzenia nie jest obsługiwane.

- **Klient sieci VPN**: wybierz klienta sieci VPN, który obsługuje opcję Zawsze włączone. Dostępne opcje:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Niestandardowy
    - **Identyfikator pakietu**: wprowadź identyfikator pakietu aplikacji w sklepie Google Play. Jeśli na przykład adresem URL aplikacji w sklepie Play jest `https://play.google.com/store/details?id=com.contosovpn.android.prod`, to identyfikatorem pakietu jest `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Wybrany klient sieci VPN musi być zainstalowany na urządzeniu i musi obsługiwać sieć VPN dla aplikacji w profilach służbowych. W przeciwnym razie wystąpi błąd. 
  > - Należy zatwierdzić aplikację klienta sieci VPN w **zarządzanymi sklepie Google Play**, zsynchronizować aplikację z usługą Intune i wdrożyć aplikację na urządzeniu. Po wykonaniu tej czynności aplikacja jest zainstalowana w profilu służbowym użytkownika.
  > - Nadal musisz skonfigurować klienta sieci VPN z [profilem sieci VPN](vpn-settings-android-enterprise.md)lub za pośrednictwem [profilu konfiguracji aplikacji](../apps/app-configuration-policies-use-android.md).
  > - Mogą wystąpić znane problemy podczas korzystania z sieci VPN dla aplikacji z programem F5 Access dla systemu Android 3.0.4. Aby uzyskać więcej informacji, zobacz [opublikowane przez firmę F5 informacje o wersji programu F5 Access dla systemu Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android).

- **Tryb blokady**: wybierz pozycję **Włącz**, aby wymusić korzystanie z tunelu sieci VPN przez cały ruch sieciowy. Jeśli nie nawiązano połączenia z siecią VPN, urządzenie nie będzie mieć dostępu do sieci.

  Wybierz pozycję **Nieskonfigurowane**, aby zezwolić ruchowi na przepływ przez tunel VPN lub sieć komórkową.

- **Zalecany globalny serwer proxy**: wybierz opcję **Włącz** , aby dodać globalny serwer proxy do urządzeń. Po włączeniu ruchu HTTP i HTTPS, w tym niektórych aplikacji na urządzeniu, użyj wprowadzonego serwera proxy. Ten serwer proxy jest tylko rekomendacją. Niektóre aplikacje nie będą korzystać z serwera proxy. **Nieskonfigurowane** (domyślnie) nie dodaje zalecanego globalnego serwera proxy.

  Aby uzyskać więcej informacji na temat tej funkcji, zobacz [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (otwiera witrynę systemu Android).

  Po włączeniu należy również wprowadzić **Typ** serwera proxy. Dostępne opcje:

  - **Bezpośredni**: Wybierz tę opcję, aby ręcznie wprowadzić szczegóły serwera proxy, w tym:
    - **Host**: Wprowadź nazwę hosta lub adres IP serwera proxy. Na przykład wprowadź adres `proxy.contoso.com` lub `127.0.0.1`.
    - **Numer portu**: wprowadź numer portu TCP używany przez serwer proxy. Na przykład wprowadź `8080`.
    - **Wykluczone hosty**: wprowadź listę nazw hostów lub adresów IP, które nie korzystają z serwera proxy. Ta lista może zawierać symbol wieloznaczny gwiazdki (`*`) i wiele hostów rozdzielonych średnikami (`;`) bez spacji. Na przykład wprowadź `127.0.0.1;web.contoso.com;*.microsoft.com`.

  - **Konfiguracja serwera proxy**: wprowadź **adres URL PAC** do skryptu automatycznej konfiguracji serwera proxy. Na przykład wprowadź `https://proxy.contoso.com/proxy.pac`.

    Aby uzyskać więcej informacji na temat plików PAC, zobacz [plik automatycznej konfiguracji serwera proxy (PAC)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (otwiera witrynę firmy innej niż Microsoft).

## <a name="work-profile-only"></a>Tylko profil służbowy

Te ustawienia mają zastosowanie do typów rejestracji w systemie Android Enterprise, w których usługa Intune kontroluje tylko profil służbowy, taki jak rejestracja profilu służbowego systemu Android na urządzeniu osobistym lub przynoszącym własne urządzenie (BYOD).

### <a name="work-profile-settings"></a>Ustawienia profilu służbowego

#### <a name="general"></a>Ogólne

- **Kopiuj i wklejaj między profilem służbowym a osobistym**: wybierz pozycję **Blokuj**, aby uniemożliwić kopiowanie i wklejanie między aplikacjami służbowymi i osobistymi. Pozycja **Nieskonfigurowane** umożliwia użytkownikom udostępnianie danych aplikacjom w profilu osobistym przy użyciu kopiowania i wklejania. 
- **Udostępnianie danych między profilami służbowym i osobistym**: wybierz, czy aplikacje w profilu służbowym mogą udostępniać dane aplikacjom w profilu osobistym. Możesz na przykład sterować akcjami udostępniania, takimi jak opcja **Udostępnij…**, w aplikacjach. w przeglądarce Chrome. To ustawienie nie ma zastosowania do zachowania schowka w zakresie kopiowania/wklejania. Opcje udostępniania:
  - **Ustawienie domyślne urządzenia**: domyślne zachowanie urządzenia w zakresie udostępniania, które różni się w zależności od wersji systemu Android. Udostępnianie danych z profilu osobistego w profilu służbowym jest domyślnie dozwolone. Udostępnianie danych z profilu służbowego w profilu osobistym jest domyślnie zablokowane. To ustawienie zapobiega udostępnianiu danych z profilu służbowego w profilu osobistym. Firma Google nie blokuje udostępniania z profilu osobistego do profilu służbowego na urządzeniach z systemem w wersji 6.0 lub nowszej.
  - **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępnienia z profilu osobistego**: umożliwia włączenie wbudowanej funkcji systemu Android pozwalającej na udostępnianie danych z profilu osobistego w profilu służbowym. Gdy ta opcja jest włączona, żądanie udostępnienia z aplikacji w profilu osobistym umożliwi udostępnianie danych aplikacjom w profilu służbowym. Jest to domyślne ustawienie w przypadku urządzeń z systemem Android w wersji wcześniejszej niż 6.0.
  - **Nie Zezwalaj na udostępnianie między granicami**: Zapobiega udostępnianiu między profilami służbowymi i osobistymi.
  - **Brak ograniczeń dotyczących udostępniania**: włącza udostępnianie przez granicę profilu służbowego w obu kierunkach. Po wybraniu tego ustawienia aplikacje w profilu służbowym mogą udostępniać dane niewskazanym aplikacjom w profilu osobistym. To ustawienie pozwala zarządzanym aplikacjom z profilu służbowego udostępniać dane aplikacjom w niezarządzanym obszarze urządzenia. Dlatego należy go używać ostrożnie.

- **Powiadomienia profilu służbowego przy zablokowanym urządzeniu**: pozwala określić, czy aplikacje z profilu służbowego mogą pokazywać dane w powiadomieniach, gdy urządzenie jest zablokowane. Pozycja **Blokuj** powoduje, że dane nie są wyświetlane. Pozycja **Nieskonfigurowane** powoduje wyświetlanie danych.
- **Domyślne uprawnienia aplikacji**: powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android 6, użytkownik jest monitowany o udzielenie określonych uprawnień wymaganych przez aplikacje, gdy aplikacja jest uruchamiana. To ustawienie zasad pozwala określić, czy użytkownicy są monitowani o nadanie uprawnień wszystkim aplikacjom w profilu służbowym. Można na przykład przypisać aplikację do profilu służbowego, który wymaga dostępu do lokalizacji. Standardowo aplikacja monituje użytkownika o zatwierdzenie lub odrzucenie dostępu aplikacji do lokalizacji. Należy użyć tych zasad, aby automatycznie udzielić uprawnień bez wyświetlania monitu, automatycznie odmówić uprawnień bez wyświetlania monitu lub pozwolić użytkownikowi końcowemu zdecydować. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Monit**
  - **Automatyczne udzielaj**
  - **Automatyczne odmawiaj**

  Zasad konfiguracji aplikacji można także użyć do nadania uprawnień dla poszczególnych aplikacji (**Aplikacje klienckie** > **Zasady konfiguracji aplikacji**).

- **Dodawanie i usuwanie kont**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom końcowym ręczne dodawanie i usuwanie kont w profilu służbowym. Na przykład w przypadku wdrożenia aplikacji Gmail w profilu służbowym systemu Android można uniemożliwić użytkownikom końcowym dodawanie i usuwanie kont w tym profilu służbowym. Pozycja **Nieskonfigurowane** zezwala na dodawanie kont w profilu służbowym.  

- **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**: umożliwia dostęp do kontaktów służbowych z innego urządzenia, takiego jak samochód, sparowanego za pomocą połączenia Bluetooth. Domyślnie to ustawienie nie jest skonfigurowane i kontakty służbowe nie są wyświetlane. Wybierz pozycję **Włącz**, aby zezwolić na udostępnianie i wyświetlić kontakty z profilu służbowego. To ustawienie dotyczy urządzeń z systemem Android w wersji 6.0 i nowszych oraz profilem służbowym. Włączenie tego ustawienia może umożliwić niektórym urządzeniom Bluetooth zapisanie w pamięci podręcznej kontaktów służbowych przy pierwszym połączeniu. Wyłączenie tych zasad po przeprowadzeniu początkowego parowania/synchronizacji może nie spowodować usunięcia kontaktów służbowych z urządzenia Bluetooth.

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów na urządzeniu w profilu służbowym. Zapobiega również wyświetlaniu zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo. Pozycja **Nieskonfigurowane** umożliwia tworzenie zrzutów ekranu.

- **Wyświetlanie identyfikatora rozmówcy dla kontaktu służbowego w profilu osobistym**: po włączeniu (pozycja **Nieskonfigurowane**) szczegóły rozmówcy dla kontaktu służbowego są wyświetlane w profilu osobistym. Po wybraniu pozycji **Blokuj** numer rozmówcy dla kontaktu służbowego nie jest wyświetlany w profilu osobistym. Dotyczy systemu operacyjnego Android w wersji 6.0 i nowszych wersji.

- **Wyszukiwanie kontaktów służbowych w profilu osobistym**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom wyszukiwanie kontaktów służbowych w aplikacjach w profilu osobistym. Pozycja **Niewymagane** umożliwia wyszukiwanie kontaktów służbowych w profilu osobistym.

- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu w profilu służbowym. To ustawienie nie wpływa na aparat w profilu osobistym. Pozycja **Niewymagane** zezwala na dostęp do aparatu w profilu służbowym.

- **Zezwalaj na widżety z aplikacji profilu służbowego**: **enable** umożliwia użytkownikom końcowym umieszczanie widżetów uwidocznionych przez aplikacje na ekranie głównym. **Nie skonfigurowano** (ustawienie domyślne) — wyłącza tę funkcję.

  Na przykład program Outlook jest instalowany w profilach służbowych użytkowników. Po wybraniu opcji **Włącz**, użytkownicy mogą umieścić widżet porządku na ekranie głównym urządzenia.

#### <a name="work-profile-password"></a>Hasło profilu służbowego

- **Wymagaj hasła profilu służbowego**: ma zastosowanie do systemu Android 7.0 lub nowszego z włączonym profilem służbowym. Wybierz pozycję **Wymagaj**, aby wprowadzić zasady kodu dostępu, które będą mieć zastosowanie wyłącznie do aplikacji w profilu służbowym. Domyślnie użytkownik końcowy może używać dwóch różnych kodów PIN lub wybrać opcję połączenia zdefiniowanych kodów PIN w celu uzyskania kodu PIN o większej sile. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi używanie aplikacji służbowych bez wprowadzania hasła.
- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**16**).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem profilu służbowego**: określ, po jakim czasie następuje zablokowanie profilu służbowego. Użytkownik musi następnie wprowadzić swoje poświadczenia, aby odzyskać dostęp.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim profil służbowy zostanie wyczyszczony z urządzenia.
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**).
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom końcowym użycie skanera linii papilarnych w celu odblokowania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikom na odblokowywanie urządzeń przy użyciu odcisku palca w profilu służbowym.
- **Blokada Smart Lock i inni agenci zaufania**: wybierz pozycję **Blokuj**, aby uniemożliwić funkcji Smart Lock lub innym agentom zaufania dostosowywanie ustawień blokady ekranu na zgodnych urządzeniach. Ta funkcja, znana także jako agent zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie znajduje się w zaufanej lokalizacji. Na przykład można obejść hasło profilu służbowego, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

### <a name="device-password"></a>Hasło urządzenia

Te ustawienia hasła są stosowane w profilach osobistych na urządzeniach korzystających z profilu służbowego.

- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**14**).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określ, po jakim czasie braku aktywności następuje automatyczne zablokowanie urządzenia
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim zostaną wyczyszczone wszystkie dane z urządzenia
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**)
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu odcisku palca.
- **Blokada Smart Lock i inni agenci zaufania**: wybierz pozycję **Blokuj**, aby uniemożliwić funkcji Smart Lock lub innym agentom zaufania dostosowywanie ustawień blokady ekranu na zgodnych urządzeniach. Ta funkcja, znana także jako agent zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie znajduje się w zaufanej lokalizacji. Na przykład można obejść hasło profilu służbowego, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

### <a name="system-security"></a>Zabezpieczenia systemu

- **Skanowanie aplikacji pod kątem zagrożeń**: pozycja **Wymagaj** wymusza włączenie ustawienia **Weryfikuj aplikacje** w profilach służbowych i osobistych.

   > [!Note]
   > To ustawienie działa tylko w przypadku urządzeń z systemem Android 8 (Oreo) lub nowszym.

- **Zapobiegaj instalacji aplikacji z nieznanych źródeł w profilu osobistym**: Po zaprojektowaniu urządzenia z systemem Android Enterprise profile służbowe nie mogą instalować aplikacji ze źródeł innych niż Sklep Play. Ze względu na to, że urządzenia profilu służbowego są przeznaczone do podwójnego profilu:

  - Profil służbowy zarządzany przy użyciu zarządzania urządzeniami przenośnymi.
  - Profil osobisty odizolowany od zarządzania urządzeniami przenośnymi.

  To ustawienie umożliwia administratorom większą kontrolę nad instalacjami aplikacji z nieznanych źródeł. **Nie skonfigurowano** (wartość domyślna) umożliwia instalowanie aplikacji z nieznanych źródeł w profilu osobistym. **Blokuj** uniemożliwia instalacje aplikacji ze źródeł innych niż Sklep Play w profilu osobistym.

### <a name="connectivity"></a>Łączność

- **Zawsze włączona sieć VPN**: wybierz pozycję **Włącz**, aby ustawić klienta sieci VPN tak, aby automatycznie łączył się i przywracał połączenie z siecią VPN. Zawsze włączone połączenia sieci VPN pozostają aktywne lub natychmiast łączą się, gdy użytkownik zablokuje urządzenie, urządzenie uruchomi się ponownie lub zmieni się sieć bezprzewodowa. 

  Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć zawsze włączoną sieć VPN dla wszystkich klientów sieci VPN.

  > [!IMPORTANT]
  > Należy pamiętać, aby dla jednego urządzenia wdrożyć tylko jedne zasady zawsze włączonej sieci VPN. Wdrażanie wielu zasad zawsze włączonej sieci VPN dla jednego urządzenia nie jest obsługiwane.

- **Klient sieci VPN**: wybierz klienta sieci VPN, który obsługuje opcję Zawsze włączone. Dostępne opcje:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Niestandardowy
    - **Identyfikator pakietu**: wprowadź identyfikator pakietu aplikacji w sklepie Google Play. Jeśli na przykład adresem URL aplikacji w sklepie Play jest `https://play.google.com/store/details?id=com.contosovpn.android.prod`, to identyfikatorem pakietu jest `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Wybrany klient sieci VPN musi być zainstalowany na urządzeniu i musi obsługiwać sieć VPN dla aplikacji w profilach służbowych. W przeciwnym razie wystąpi błąd. 
  > - Należy zatwierdzić aplikację klienta sieci VPN w **zarządzanymi sklepie Google Play**, zsynchronizować aplikację z usługą Intune i wdrożyć aplikację na urządzeniu. Po wykonaniu tej czynności aplikacja jest zainstalowana w profilu służbowym użytkownika.
  > - Mogą wystąpić znane problemy podczas korzystania z sieci VPN dla aplikacji z programem F5 Access dla systemu Android 3.0.4. Aby uzyskać więcej informacji, zobacz [opublikowane przez firmę F5 informacje o wersji programu F5 Access dla systemu Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android).

- **Tryb blokady**: wybierz pozycję **Włącz**, aby wymusić korzystanie z tunelu sieci VPN przez cały ruch sieciowy. Jeśli nie nawiązano połączenia z siecią VPN, urządzenie nie będzie mieć dostępu do sieci.

  Wybierz pozycję **Nieskonfigurowane**, aby zezwolić ruchowi na przepływ przez tunel VPN lub sieć komórkową.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Możesz również utworzyć profile kiosku urządzenia dedykowanego dla urządzeń z systemem [Android](device-restrictions-android.md#kiosk) i [Windows 10](kiosk-settings.md).

## <a name="see-also"></a>Zobacz także

[Configuring and troubleshooting Android enterprise devices in Microsoft Intune](https://support.microsoft.com/help/4476974) (Konfigurowanie urządzeń z systemem Android Enterprise i rozwiązywanie problemów z nimi w usłudze Microsoft Intune)
