---
title: Ustawienia urządzenia z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titlesuffix: ''
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
ms.openlocfilehash: 4fa6a68d1b5a8d2ccf87587ecab36c7807770d48
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565353"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem macOS. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, zezwalać na działanie konkretnych aplikacji lub je ograniczać i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem macOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Tworzenie profilu konfiguracji urządzenia ograniczenia](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Ogólne

- **Blokuj wyszukiwanie definicji**: pozycja **Blokuj** uniemożliwia użytkownikom wyróżnianie wyrazu, a następnie wyszukiwanie jego definicji na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do funkcji wyszukiwania definicji.
- **Blokuj dyktowanie**: pozycja **Blokuj** uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na korzystanie z wprowadzania tekstu przez dyktowanie.
- **Blokuj buforowanie zawartości**: Wybierz **nieskonfigurowane** (ustawienie domyślne), aby włączyć buforowanie zawartości. Buforowanie zawartości przechowuje dane aplikacji, danych przeglądarki sieci web, pliki do pobrania i więcej lokalnie na urządzeniu. Wybierz **bloku** aby zapobiec te dane są przechowywane w pamięci podręcznej.

  Aby uzyskać więcej informacji na temat buforowania zawartości w systemie macOS, zobacz [Zarządzanie buforowanie zawartości na komputerze Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (otwiera innej witryny sieci Web).

  Ta funkcja ma zastosowanie do:  
  - System macOS 10.13 i nowsze

- **Odroczenie aktualizacji oprogramowania (tylko tryb nadzorowany)**: po ustawieniu **nieskonfigurowane** (ustawienie domyślne), aktualizacje oprogramowania są wyświetlane na urządzeniu z Apple zwalnia je. Na przykład jeśli aktualizację systemu macOS pobiera wydany przez firmę Apple w określonym dniu, następnie aktualizacja naturalnie pojawia się na urządzeniu wokół daty wydania.

  **Włącz** umożliwia opóźnienie podczas aktualizacji oprogramowania są wyświetlane na urządzeniach z 0 – 90 dni. To ustawienie nie kontroluje, kiedy aktualizacje są lub nie są zainstalowane. 

  - **Opóźnienie widoczność aktualizacji oprogramowania**: wprowadź wartość z zakresu od 0 – 90 dni. Po upływie czasu opóźnienia użytkownicy otrzymują powiadomienie o aktualizacji do najnowszej wersji systemu operacyjnego dostępnej w momencie wyzwolenia opóźnienia.

    Na przykład, jeśli aktualizacja z systemem macOS jest dostępna w **1 stycznia**, i **opóźnienie widoczność** jest ustawiona na **5 dni**, a następnie aktualizacja nie jest wyświetlana jako dostępna aktualizacja, na urządzeniach. Na **szósty dzień** opublikowania wersji, że jest dostępna aktualizacja, a użytkownicy końcowi mogą zainstalować ją.

    Ta funkcja ma zastosowanie do:  
    - System macOS 10.13.4 i nowsze

## <a name="password"></a>Hasło

- **Hasło**: pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. **Nieskonfigurowane** (ustawienie domyślne) nie wymaga hasła, a nie wymusić wszelkie ograniczenia, takie jak blokowanie proste hasła lub ustawienie minimalnej długości.
  - **Wymagany typ hasła**: określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry). To ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.
  - **Liczba znaków innych niż alfanumeryczne w haśle**: określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol, na przykład „**?**”.
  - **Minimalna długość hasła**: określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
  - **Proste hasła**: umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
  - **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**: określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
  - **Wygaśnięcie hasła (dni)**: określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
  - **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe, od **1** do **24**.

- **Zablokuj użytkownikowi możliwość modyfikowania kodu dostępu**: Wybierz **bloku** przestanie kodu dostępu z zmieniany dodany lub usunięty. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia dodawanie, zmienianie lub usuwanie kodów dostępu.
- **Blokuj odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie odcisku palca do odblokowywania urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu odcisku palca.

- **Blokuj automatyczne wypełnianie haseł**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie funkcji automatycznego wypełniania haseł w systemie macOS. Wybieranie **bloku** ma również następujące znaczenie:

  - Użytkownicy nie są monitowani o użycie zapisanego hasła w przeglądarce Safari ani innych aplikacjach.
  - Automatyczne silne hasła są wyłączone i silne hasła nie są zalecane dla użytkowników.

  Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te funkcje.

- **Blokuj zbliżeniowe żądania haseł**: wybierz pozycję **Blokuj**, aby urządzenie użytkownika nie żądało haseł od urządzeń znajdujących się w pobliżu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te żądania haseł.

- **Blokowanie udostępniania haseł**: pozycja **Blokuj** uniemożliwia udostępnianie haseł między urządzeniami przy użyciu funkcji AirDrop. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia udostępnianie haseł.

## <a name="built-in-apps"></a>Aplikacje wbudowane

- **Blokuj autowypełnianie w przeglądarce Safari**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania w przeglądarce Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom zmianę ustawień automatycznego uzupełniania w przeglądarce internetowej.
- **Blokuj aplikację Aparat**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aparatu urządzenia.
- **Blokuj usługę Apple Music**: pozycja **Blokuj** przywraca aplikację do obsługi muzyki do trybu klasycznego i wyłącza usługę Music. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple Music.
- **Wyniki wyszukiwania w Internecie Spotlight bloku**: **bloku** zatrzymuje Spotlight z powrotem żadnych wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.
- **Transfer plików bloku za pomocą programu iTunes**: **bloku** wyłącza usługi udostępniania plików w aplikacji. Dostępne w systemie macOS 10.13 i nowszych wersjach. **Nieskonfigurowane** (ustawienie domyślne) umożliwia usługi udostępniania plików w aplikacji.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

- Lista **Aplikacje zabronione**: lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać. Użytkownicy nie są można zapobiec zainstalowaniu zabronionej aplikacji, ale jeśli tak, jest zgłaszany do administratora.
- Lista **Zatwierdzone aplikacje**: lista aplikacji, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Użytkownicy nie mogli instalowanie znajdującym się na liście zatwierdzonych aplikacji. Jednak jeśli tak, jest zgłaszany do administratora.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i identyfikator pakietu aplikacji (np. *com.apple.calculator*).

## <a name="connected-devices"></a>Połączone urządzenia

- **Blokuj usługę AirDrop**: pozycja **Blokuj** uniemożliwia używanie funkcji AirDrop na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
- **Blok Apple Watch automatyczne odblokowywanie**: **bloku** uniemożliwia użytkownikom odblokowywanie urządzeń z systemem macOS przy użyciu ich Apple Watch. **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom w celu odblokowania urządzenia z systemem macOS przy użyciu ich Apple Watch.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Blokuj synchronizowanie pęku kluczy z usługą iCloud**: wybierz pozycję **Blokuj**, aby wyłączyć synchronizowanie poświadczeń przechowywanych w pęku kluczy z usługą iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom synchronizację tych poświadczeń.
- **Blokuj Synchronizowanie dokumentów w usłudze iCloud**: **bloku** uniemożliwia Synchronizowanie dokumentów i danych w usłudze iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia synchronizowanie dokumentów i par klucz-wartość w obszarze magazynu usługi iCloud.
- **Blokuj kopii zapasowej wiadomości E-mail w usłudze iCloud**: **bloku** uniemożliwia synchronizowanie do aplikacji Poczta systemu macOS w usłudze iCloud. **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizację poczty w usłudze iCloud.
- **Blokuj skontaktuj się z kopii zapasowej w usłudze iCloud**: **bloku** uniemożliwia synchronizowanie kontaktów urządzenia w usłudze iCloud. **Nieskonfigurowane** (wartość domyślna) zezwala na synchronizację kontaktów przy użyciu usługi iCloud.
- **Zablokować kalendarz kopii zapasowej w usłudze iCloud**: **bloku** uniemożliwia Synchronizowanie aplikacji kalendarza z systemem macOS w usłudze iCloud. **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizacja kalendarza w usłudze iCloud.
- **Blokuj przypomnienie kopii zapasowej w usłudze iCloud**: **bloku** uniemożliwia Synchronizowanie aplikacji przypomnienia z systemem macOS w usłudze iCloud. **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizację przypomnienia w usłudze iCloud.
- **Blokuj kopii zapasowej zakładki w usłudze iCloud**: **bloku** uniemożliwia Synchronizowanie urządzeń zakładki w usłudze iCloud. **Nieskonfigurowane** (ustawienie domyślne) umożliwia synchronizację zakładki w usłudze iCloud.
- **Blokuj informacje o kopii zapasowej w usłudze iCloud**: **bloku** uniemożliwia Synchronizowanie urządzeń, informacje o usłudze iCloud. **Nieskonfigurowane** (wartość domyślna) zezwala na synchronizację Notes w usłudze iCloud.

## <a name="domains"></a>Domains

- **Adres URL domeny poczty e-mail**: dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy otrzymają wiadomość e-mail z domeny innej niż skonfigurowana, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu MacOS jako niezaufana.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również ograniczyć funkcji i ustawień urządzenia, na [iOS](device-restrictions-ios.md) urządzeń.