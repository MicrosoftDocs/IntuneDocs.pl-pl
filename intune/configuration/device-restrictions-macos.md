---
title: Ustawienia urządzenia z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodawaj, konfiguruj lub twórz ustawienia na urządzeniach z systemem macOS w celu ograniczenia funkcji, na przykład ustawiania wymagań dotyczących haseł, kontrolowania zablokowanego ekranu, używania wbudowanych aplikacji, dodawania ograniczonych lub zatwierdzonych aplikacji, obsługi urządzeń z funkcją Bluetooth, łączenia z chmurą na potrzeby tworzenia kopii zapasowych i magazynowania, włączania trybu kiosku, dodawania domen oraz kontrolowania sposobu, w jaki użytkownicy pracują z przeglądarką internetową Safari w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b2efdc04414d29fc1d8d200525cb3a4a880ec01
ms.sourcegitcommit: e9cf372711ff186ed468b01a9204631a139bd8e5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "72776882"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem macOS. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, zezwalać na działanie konkretnych aplikacji lub je ograniczać i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem macOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji ograniczeń urządzenia](../device-restrictions-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [Rejestrowanie macOS](../macos-enroll.md).

## <a name="general"></a>Ogólne

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Wyszukiwanie definicji**: opcja **Blokuj** uniemożliwia użytkownikowi zaznaczenie słowa i wyszukanie jego definicji na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do funkcji wyszukiwania definicji.
- **Dyktowanie**: pozycja **Blokuj** uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na korzystanie z wprowadzania tekstu przez dyktowanie.
- **Buforowanie zawartości**: wybierz opcję **Nieskonfigurowane** (ustawienie domyślne), aby włączyć buforowanie zawartości. Funkcja buforowania zawartości umożliwia przechowywanie danych aplikacji, danych przeglądarki internetowej, pobranych plików i innej zawartości lokalnie na urządzeniu. Wybierz opcję **Blokuj**, aby te dane nie były przechowywane w pamięci podręcznej.

  Aby uzyskać więcej informacji na temat buforowania zawartości w systemie MacOS, zobacz [Manage content caching on Mac (Zarządzanie buforowaniem zawartości na komputerze Mac)](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (link otwiera inną witrynę internetową).

  Ta funkcja ma zastosowanie do:  
  - System macOS 10.13 i nowsze

- **Odrocz aktualizacje oprogramowania**: jeśli jest wybrana opcja **Nieskonfigurowane** (ustawienie domyślne), aktualizacje oprogramowania są wyświetlane na urządzeniu w momencie ich publikacji przez firmę Apple. Na przykład jeśli firma Apple opublikuje aktualizację systemu macOS określonego dnia, ta aktualizacja będzie naturalnie widoczna na urządzeniu w okolicy tego terminu. Aktualizacje kompilacji inicjatora są udostępniane bez opóźnień.

  Pozycja **Włącz** umożliwia opóźnienie momentu wyświetlenia aktualizacji oprogramowania na urządzeniach o określony czas z przedziału 0–90 dni. To ustawienie nie określa momentu instalowania lub nieinstalowania aktualizacji. 

  - **Opóźnij widoczność aktualizacji oprogramowania**: wprowadź wartość z zakresu 0–90 dni. Po upływie czasu opóźnienia użytkownicy otrzymują powiadomienie o aktualizacji do najnowszej wersji systemu operacyjnego dostępnej w momencie wyzwolenia opóźnienia.

    Na przykład jeśli aktualizacja systemu macOS została udostępniona **1 stycznia**, a ustawienie **Opóźnij widoczność** ma wartość **5 dni**, ta aktualizacja nie będzie widoczna na urządzeniach jako dostępna. Będzie ona dostępna do instalacji przez użytkowników końcowych **szóstego dnia** po publikacji.

    Ta funkcja ma zastosowanie do:  
    - System macOS 10.13.4 i nowsze

- **Zrzuty ekranu**: urządzenie musi być zarejestrowane w zautomatyzowanym rejestrowaniu urządzeń firmy Apple (DEP). Po ustawieniu opcji **Blokuj**użytkownicy nie mogą zapisać zrzutu ekranu ekranu. Zapobiega także obserwowanie ekranów zdalnych przez aplikację klasy. **Nie skonfigurowano** (domyślnie) umożliwia użytkownikom przechwytywanie zrzutów ekranu i umożliwia aplikacji klasy wyświetlanie ekranów zdalnych.

### <a name="settings-apply-to-automated-device-enrollment"></a>Ustawienia dotyczą: automatyczna rejestracja urządzeń

- **Obserwacja ekranu zdalnego za pomocą aplikacji klasy**: **Wyłącz** uniemożliwianie nauczycielom korzystanie z aplikacji klasy do wyświetlania ekranów studentów. **Nie skonfigurowano** (domyślnie) umożliwia nauczycielom wyświetlanie ekranów swoich uczniów.

  Aby użyć tego ustawienia, ustaw ustawienie ustawienia **zrzutu ekranu** na wartość **Nieskonfigurowane** (zrzuty ekranu są dozwolone).

- **Niewyświetlane obserwacje ekranu według aplikacji klasy**: **Zezwól** umożliwia nauczycielom wyświetlanie ekranów studentów bez konieczności wyrażania zgody studenta. **Nie skonfigurowano** (wartość domyślna) wymaga, aby student mógł wyrazić zgodę, zanim nauczyciel zobaczy ekrany.

  Aby użyć tego ustawienia, ustaw ustawienie ustawienia **zrzutu ekranu** na wartość **Nieskonfigurowane** (zrzuty ekranu są dozwolone).

- **Studenci muszą zażądać uprawnień do opuszczenia klasy klas**: **Wymagaj** , aby studenci zarejestrowali się w niezarządzanym kursie z zajęć, aby uzyskać zatwierdzenie w nauczycielu w celu opuszczenia kursu. **Nie skonfigurowano** (domyślnie) pozwala studentowi na pozostawienie kursu przy każdym wyborze ucznia.

- **Nauczyciele mogą automatycznie blokować urządzenia lub aplikacje w aplikacji klasy**: **Zezwól** , aby nauczyciele blokowały urządzenie lub aplikację ucznia bez zgody ucznia. **Nieskonfigurowane** (domyślnie) wymaga od ucznia zgody przed zablokowaniem przez nauczyciela urządzenia lub aplikacji.

- **Studenci mogą automatycznie dołączać klasę klasy**: **Zezwól** zezwala studentom na dołączanie do klasy bez monitowania nauczycieli. **Nie skonfigurowano** (domyślnie) wymaga zatwierdzenia nauczyciela do przyłączenia do klasy.

## <a name="password"></a>Hasło

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Hasło**: pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. **Nieskonfigurowane** (domyślnie) nie wymaga hasła. Nie wymusi również żadnych ograniczeń, takich jak blokowanie prostych haseł lub Ustawianie minimalnej długości.
  - **Wymagany typ hasła**: określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry).

    Ta funkcja ma zastosowanie do:  
    - System macOS 10.10.3 i nowsze

  - **Liczba znaków innych niż alfanumeryczne w haśle**: określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol, na przykład „ **?** ”.
  - **Minimalna długość hasła**: określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
  - **Proste hasła**: umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
  - **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**: określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
  - **Wygaśnięcie hasła (dni)** : określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
  - **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe, od **1** do **24**.

- **Zablokuj użytkownikowi możliwość modyfikacji kodu dostępu**: wybierz pozycję **Blokuj**, aby uniemożliwić zmianę, dodanie lub usunięcie kodu dostępu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia dodawanie, zmienianie lub usuwanie kodów dostępu.
- **Blokuj odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie odcisku palca do odblokowywania urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu odcisku palca.

- **Blokuj automatyczne wypełnianie haseł**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie funkcji automatycznego wypełniania haseł w systemie macOS. Wybranie opcji **Blokuj** ma również następujące skutki:

  - Użytkownicy nie są monitowani o użycie zapisanego hasła w przeglądarce Safari ani innych aplikacjach.
  - Automatyczne silne hasła są wyłączone i silne hasła nie są zalecane dla użytkowników.

  Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te funkcje.

- **Blokuj zbliżeniowe żądania haseł**: wybierz pozycję **Blokuj**, aby urządzenie użytkownika nie żądało haseł od urządzeń znajdujących się w pobliżu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te żądania haseł.

- **Blokowanie udostępniania haseł**: pozycja **Blokuj** uniemożliwia udostępnianie haseł między urządzeniami przy użyciu funkcji AirDrop. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia udostępnianie haseł.

## <a name="built-in-apps"></a>Aplikacje wbudowane

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Blokuj autowypełnianie w przeglądarce Safari**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania w przeglądarce Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom zmianę ustawień automatycznego uzupełniania w przeglądarce internetowej.
- **Blokuj aplikację Aparat**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aparatu urządzenia.
- **Blokuj usługę Apple Music**: pozycja **Blokuj** przywraca aplikację do obsługi muzyki do trybu klasycznego i wyłącza usługę Music. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple Music.
- **Blokuj wyniki funkcji Spotlight z Internetu**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.
- **Blokuj transfer plików za pomocą programu iTunes**: opcja **Blokuj** wyłącza usługi udostępniania plików w aplikacji. Opcja **Nieskonfigurowane** (ustawienie domyślne) zezwala na usługi udostępniania plików w aplikacji.

  Ta funkcja ma zastosowanie do:  
  - System macOS 10.13 i nowsze

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Typ listy aplikacji z ograniczeniami**: Utwórz listę aplikacji, których użytkownicy nie mogą instalować ani używać. Dostępne opcje:

  - **Nie skonfigurowano** (domyślnie): nie ma żadnych ograniczeń z usługi Intune. Użytkownicy mają dostęp do przypisywanych aplikacji oraz wbudowanych aplikacji.
  - **Aplikacje zabronione**: aplikacje niezarządzane przez usługę Intune, których nie chcesz instalować na urządzeniu. Użytkownicy nie mogą instalować zabronionej aplikacji. Jednak jeśli użytkownik zainstaluje aplikację z tej listy, zostanie ona zgłoszona w usłudze Intune.
  - **Zatwierdzone aplikacje**: aplikacje, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Użytkownicy nadal będą mogli zainstalować aplikację, której nie ma na liście dozwolonych. Ale jeśli tak, jest on raportowany w usłudze Intune.
- **Identyfikator pakietu aplikacji**: podaj [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) odpowiedniej aplikacji. Możesz pokazać lub ukryć wbudowane aplikacje i aplikacje biznesowe. Witryna sieci Web firmy Apple zawiera listę [wbudowanych aplikacji firmy Apple](https://support.apple.com/HT208094).
- **Nazwa aplikacji**: podaj nazwę odpowiedniej aplikacji. Możesz pokazać lub ukryć wbudowane aplikacje i aplikacje biznesowe. Witryna sieci Web firmy Apple zawiera listę [wbudowanych aplikacji firmy Apple](https://support.apple.com/HT208094).
- **Wydawca**: podaj wydawcę odpowiedniej aplikacji.

Aby dodać aplikacje do tych list, możesz:

- **Dodaj**: Wybierz, aby utworzyć listę aplikacji.
- **Zaimportować** plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app bundle ID>, <app name>, <app publisher>`. Możesz też **wyeksportować** , aby utworzyć listę dodanych aplikacji w tym samym formacie.

## <a name="connected-devices"></a>Połączone urządzenia

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Blokuj usługę AirDrop**: pozycja **Blokuj** uniemożliwia używanie funkcji AirDrop na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
- **Blokuj automatyczne odblokowywanie za pomocą urządzenia Apple Watch**: ustawienie **Blokuj** uniemożliwia użytkownikom odblokowywanie urządzenia z systemem macOS przy użyciu urządzenia Apple Watch. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom odblokowywanie urządzenia z systemem macOS przy użyciu urządzenia Apple Watch.

## <a name="cloud-and-storage"></a>Chmura i magazyn

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Blokuj synchronizowanie pęku kluczy z usługą iCloud**: wybierz pozycję **Blokuj**, aby wyłączyć synchronizowanie poświadczeń przechowywanych w pęku kluczy z usługą iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom synchronizację tych poświadczeń.
- **Blokuj synchronizowanie dokumentów z usługą iCloud**: pozycja **Blokuj**  uniemożliwia synchronizowanie dokumentów i danych w usłudze iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia synchronizowanie dokumentów i par klucz-wartość w obszarze magazynu usługi iCloud.
- **Blokuj wykonywanie kopii zapasowych poczty w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie aplikacji Poczta systemu macOS w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie aplikacji Poczta w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych kontaktów w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie kontaktów z urządzenia w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) zezwala na synchronizowanie kontaktów w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych kalendarza w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie aplikacji Kalendarz systemu macOS w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie aplikacji Kalendarz w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych przypomnień w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie aplikacji Przypomnienia systemu macOS w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie aplikacji Przypomnienia w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych zakładek w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie zakładek z urządzenia w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie zakładek w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych notatek w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie notatek z urządzenia w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie notatek w usłudze iCloud.
- **Zablokuj bibliotekę zdjęć iCloud**: **Blokuj** wyłącza bibliotekę zdjęć iCloud i uniemożliwia synchronizowanie zdjęć z urządzeń w usłudze iCloud. Zdjęcia niepobrane w pełni z biblioteki iCloud Photo Library są usuwane z magazynu lokalnego na urządzeniu. **Nie skonfigurowano** (domyślnie) umożliwia synchronizowanie zdjęć między urządzeniem a biblioteką zdjęć iCloud.
- **Oddanie**: **nie skonfigurowano** (domyślnie) umożliwia użytkownikom uruchamianie pracy na urządzeniu macOS, a następnie kontynuuje pracę uruchomioną na innym urządzeniu z systemem iOS lub macOS. **Blokuj** uniemożliwia funkcję przestawiania na urządzeniu. 

  Ta funkcja ma zastosowanie do:  
  - System macOS 10.15 i nowsze

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ustawienia dotyczą: rejestracja urządzeń i automatyczna rejestracja urządzeń

- **Adres URL domeny poczty e-mail**: **dodaj** do listy co najmniej jeden adres URL. Gdy użytkownicy otrzymają wiadomość e-mail z domeny innej niż skonfigurowana, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu macOS jako niezaufana.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](../device-profile-monitor.md).

Możesz również skonfigurować ograniczenia dotyczące funkcji i ustawień urządzenia z systemem [iOS](../device-restrictions-ios.md).
