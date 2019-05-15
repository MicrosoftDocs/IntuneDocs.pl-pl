---
title: Ustawienia urządzenia z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodawaj, konfiguruj lub twórz ustawienia na urządzeniach z systemem macOS w celu ograniczenia funkcji, na przykład ustawiania wymagań dotyczących haseł, kontrolowania zablokowanego ekranu, używania wbudowanych aplikacji, dodawania ograniczonych lub zatwierdzonych aplikacji, obsługi urządzeń z funkcją Bluetooth, łączenia z chmurą na potrzeby tworzenia kopii zapasowych i magazynowania, włączania trybu kiosku, dodawania domen oraz kontrolowania sposobu, w jaki użytkownicy pracują z przeglądarką internetową Safari w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5feec66e791da4038bd069cdad69a7ba573f27f3
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798381"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem macOS. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, zezwalać na działanie konkretnych aplikacji lub je ograniczać i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem macOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji ograniczeń urządzenia](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Ogólne

- **Blokuj wyszukiwanie definicji**: pozycja **Blokuj** uniemożliwia użytkownikom wyróżnianie wyrazu, a następnie wyszukiwanie jego definicji na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do funkcji wyszukiwania definicji.
- **Blokuj dyktowanie**: pozycja **Blokuj** uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na korzystanie z wprowadzania tekstu przez dyktowanie.
- **Blokuj buforowanie zawartości**: wybierz opcję **Nieskonfigurowane** (ustawienie domyślne), aby włączyć buforowanie zawartości. Funkcja buforowania zawartości umożliwia przechowywanie danych aplikacji, danych przeglądarki internetowej, pobranych plików i innej zawartości lokalnie na urządzeniu. Wybierz opcję **Blokuj**, aby te dane nie były przechowywane w pamięci podręcznej.

  Aby uzyskać więcej informacji na temat buforowania zawartości w systemie MacOS, zobacz [Manage content caching on Mac (Zarządzanie buforowaniem zawartości na komputerze Mac)](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (link otwiera inną witrynę internetową).

  Ta funkcja ma zastosowanie do:  
  - System macOS 10.13 i nowsze

- **Odrocz aktualizacje oprogramowania**: jeśli jest wybrana opcja **Nieskonfigurowane** (ustawienie domyślne), aktualizacje oprogramowania są wyświetlane na urządzeniu w momencie ich publikacji przez firmę Apple. Na przykład jeśli firma Apple opublikuje aktualizację systemu macOS określonego dnia, ta aktualizacja będzie naturalnie widoczna na urządzeniu w okolicy tego terminu. Aktualizacje kompilacji inicjatora są udostępniane bez opóźnień.

  Pozycja **Włącz** umożliwia opóźnienie momentu wyświetlenia aktualizacji oprogramowania na urządzeniach o określony czas z przedziału 0–90 dni. To ustawienie nie określa momentu instalowania lub nieinstalowania aktualizacji. 

  - **Opóźnij widoczność aktualizacji oprogramowania**: wprowadź wartość z zakresu 0–90 dni. Po upływie czasu opóźnienia użytkownicy otrzymują powiadomienie o aktualizacji do najnowszej wersji systemu operacyjnego dostępnej w momencie wyzwolenia opóźnienia.

    Na przykład jeśli aktualizacja systemu macOS została udostępniona **1 stycznia**, a ustawienie **Opóźnij widoczność** ma wartość **5 dni**, ta aktualizacja nie będzie początkowo widoczna na urządzeniach jako dostępna. Będzie ona dostępna do instalacji przez użytkowników końcowych **szóstego dnia** po publikacji.

    Ta funkcja ma zastosowanie do:  
    - System macOS 10.13.4 i nowsze

## <a name="password"></a>Hasło

- **Hasło**: pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. Pozycja **Nieskonfigurowane** (ustawienie domyślne) oznacza brak wymagania wprowadzenia hasła i brak innych ograniczeń, takich jak blokada zbyt prostych haseł czy ustawienie minimalnej długości hasła.
  - **Wymagany typ hasła**: określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry). To ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.
  - **Liczba znaków innych niż alfanumeryczne w haśle**: określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol, na przykład „**?**”.
  - **Minimalna długość hasła**: określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
  - **Proste hasła**: umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
  - **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**: określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
  - **Wygaśnięcie hasła (dni)**: określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
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

- **Blokuj autowypełnianie w przeglądarce Safari**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania w przeglądarce Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom zmianę ustawień automatycznego uzupełniania w przeglądarce internetowej.
- **Blokuj aplikację Aparat**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aparatu urządzenia.
- **Blokuj usługę Apple Music**: pozycja **Blokuj** przywraca aplikację do obsługi muzyki do trybu klasycznego i wyłącza usługę Music. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple Music.
- **Blokuj wyniki funkcji Spotlight z Internetu**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.
- **Blokuj transfer plików za pomocą programu iTunes**: opcja **Blokuj** wyłącza usługi udostępniania plików w aplikacji. Dostępne w systemie macOS 10.13 i nowszych wersjach. Opcja **Nieskonfigurowane** (ustawienie domyślne) zezwala na usługi udostępniania plików w aplikacji.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

- Lista **Aplikacje zabronione**: lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać. Użytkownicy nadal będą mogli zainstalować zabronioną aplikację, ale jeśli to zrobią, ten fakt zostanie zgłoszony administratorowi.
- Lista **Zatwierdzone aplikacje**: lista aplikacji, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Użytkownicy nadal będą mogli zainstalować aplikację, której nie ma na liście dozwolonych. Jeśli jednak to zrobią, ten fakt zostanie zgłoszony administratorowi.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i identyfikator pakietu aplikacji (np. *com.apple.calculator*).

## <a name="connected-devices"></a>Połączone urządzenia

- **Blokuj usługę AirDrop**: pozycja **Blokuj** uniemożliwia używanie funkcji AirDrop na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
- **Blokuj automatyczne odblokowywanie za pomocą urządzenia Apple Watch**: ustawienie **Blokuj** uniemożliwia użytkownikom odblokowywanie urządzenia z systemem macOS przy użyciu urządzenia Apple Watch. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom odblokowywanie urządzenia z systemem macOS przy użyciu urządzenia Apple Watch.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Blokuj synchronizowanie pęku kluczy z usługą iCloud**: wybierz pozycję **Blokuj**, aby wyłączyć synchronizowanie poświadczeń przechowywanych w pęku kluczy z usługą iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom synchronizację tych poświadczeń.
- **Blokuj synchronizowanie dokumentów z usługą iCloud**: pozycja **Blokuj ** uniemożliwia synchronizowanie dokumentów i danych w usłudze iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia synchronizowanie dokumentów i par klucz-wartość w obszarze magazynu usługi iCloud.
- **Blokuj wykonywanie kopii zapasowych poczty w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie aplikacji Poczta systemu macOS w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie aplikacji Poczta w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych kontaktów w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie kontaktów z urządzenia w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) zezwala na synchronizowanie kontaktów w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych kalendarza w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie aplikacji Kalendarz systemu macOS w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie aplikacji Kalendarz w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych przypomnień w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie aplikacji Przypomnienia systemu macOS w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie aplikacji Przypomnienia w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych zakładek w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie zakładek z urządzenia w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie zakładek w usłudze iCloud.
- **Blokuj wykonywanie kopii zapasowych notatek w usłudze iCloud**: opcja **Blokuj** uniemożliwia synchronizowanie notatek z urządzenia w usłudze iCloud. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizowanie notatek w usłudze iCloud.

## <a name="domains"></a>Domains

- **Adres URL domeny poczty e-mail**: dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy otrzymają wiadomość e-mail z domeny innej niż skonfigurowana, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu MacOS jako niezaufana.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Możesz również skonfigurować ograniczenia dotyczące funkcji i ustawień urządzenia z systemem [iOS](device-restrictions-ios.md).
