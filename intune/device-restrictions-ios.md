---
title: Ustawienia urządzenia z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodawaj, konfiguruj lub twórz ustawienia na urządzeniach z systemem iOS w celu ograniczenia funkcji, na przykład ustawiania wymagań dotyczących haseł, kontrolowania zablokowanego ekranu, używania wbudowanych aplikacji, dodawania ograniczonych lub zatwierdzonych aplikacji, obsługi urządzeń z funkcją Bluetooth, łączenia z chmurą na potrzeby tworzenia kopii zapasowych i magazynowania, włączania trybu kiosku, dodawania domen oraz kontrolowania sposobu, w jaki użytkownicy pracują z przeglądarką internetową Safari w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune; seodec18
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 80eb088063522ba3acb293776064fd98846b9a3e
ms.sourcegitcommit: 8e3a20b2ad59d3a6789ee81b9cbe6d2c711da11d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54380500"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem iOS. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, zezwalać na działanie konkretnych aplikacji lub je ograniczać i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem iOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem
[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md).

## <a name="general"></a>Ogólne

- **Udostępnij dane użycia**: wybierz pozycję **Blokuj**, aby uniemożliwić urządzeniu wysyłanie danych diagnostycznych i danych użycia do firmy Apple. Pozycja **Nieskonfigurowane** umożliwia wysyłanie tych danych.
  - **Przesyłanie danych diagnostycznych**: pozycja **Blokuj** uniemożliwia użytkownikowi zmianę ustawień analizy aplikacji i przesyłania danych diagnostycznych w obszarze **Diagnostyka i użycie** (ustawienia urządzenia). Aby użyć tego ustawienia, urządzenie musi być w trybie nadzorowanym (iOS 9.3.2+). Pozycja **Nieskonfigurowane** umożliwia użytkownikowi zmianę tych ustawień urządzenia.
- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów w urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
  - **Zdalny podgląd ekranu za pomocą aplikacji Classroom (tylko nadzorowany)**: wybierz opcję **Blokuj**, aby nie był możliwy zdalny podgląd ekranu urządzenia za pomocą aplikacji Classroom. Aby użyć tego ustawienia, urządzenie musi być w trybie nadzorowanym (iOS 9.3+). Pozycja **Nieskonfigurowane** umożliwia aplikacji Classroom firmy Apple wyświetlanie ekranu.
  - **Obserwacja ekranu bez monitowania za pomocą aplikacji Classroom (tylko nadzorowany)**: w przypadku ustawienia pozycji **Zezwalaj** nauczyciele mogą dyskretnie obserwować ekrany urządzeń z systemem iOS przy użyciu aplikacji Classroom bez wiedzy uczniów. Urządzenia uczniów zarejestrowanych na zajęcia za pomocą aplikacji Classroom automatycznie udzielają uprawnień nauczycielowi na danym kursie. Pozycja **Nieskonfigurowane** uniemożliwia korzystanie z tej funkcji.
- **Niezaufane certyfikaty protokołu TLS**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie niezaufanych certyfikatów protokołu Transport Layer Security (TLS) na urządzeniu. Pozycja **Nieskonfigurowane** pozwala na korzystanie z certyfikatów protokołu TLS.
- **Zaufanie do aplikacji dla przedsiębiorstw**: wybierz pozycję **Blokuj**, aby usunąć przycisk **Ufaj deweloperowi aplikacji dla przedsiębiorstw** w obszarze Ustawienia > Ogólne > Zarządzanie profilami i urządzeniami na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi wybranie ufania aplikacjom, które nie zostały pobrane ze sklepu z aplikacjami.
- **Modyfikacja konta (tylko nadzorowany)**: po ustawieniu pozycji **Blokuj** użytkownik nie może aktualizować ustawień specyficznych dla urządzenia z poziomu aplikacji obsługującej ustawienia systemu iOS. Na przykład użytkownik nie może tworzyć nowych kont urządzenia lub zmieniać nazwy użytkownika albo hasła. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę tych ustawień.
  Ta funkcja ma również zastosowanie w przypadku ustawień dostępnych z poziomu aplikacji z ustawieniami dla systemu iOS, takich jak Poczta, Kontakty, Kalendarz, Twitter i inne. Ta funkcja nie ma zastosowania w przypadku aplikacji z ustawieniami konta, których nie można skonfigurować z poziomu aplikacji obsługującej ustawienia dla systemu iOS, na przykład aplikacji Microsoft Outlook.
- **Włączanie ograniczeń w ustawieniach urządzenia (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom włączanie ograniczeń w ustawieniach urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na konfigurowanie ograniczeń urządzenia (np. kontroli rodzicielskiej) na urządzeniu.
- **Użyj funkcji wymazania całej zawartości i wszystkich ustawień z urządzenia (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby użytkownicy nie mogli korzystać z opcji wymazywania całej zawartości i wszystkich ustawień z urządzenia (tylko nadzorowany). Pozycja **Nieskonfigurowane** zapewnia użytkownikom dostęp do tych ustawień.
- **Modyfikacja nazwy urządzenia (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby nie można było zmienić nazwy urządzenia. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi zmianę nazwy urządzenia.
- **Modyfikacja ustawień powiadamiania (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby nie można było zmieniać ustawień powiadamiania. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na zmianę ustawień powiadomień urządzenia.
- **Modyfikacja tapety (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia zmianę tapety. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi zmianę tapety na urządzeniu.
- **Modyfikacja ustawień zaufania aplikacji przedsiębiorstwa (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikowi zmianę ustawień zaufania aplikacji przedsiębiorstwa na urządzeniach nadzorowanych. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi ufanie aplikacjom, które nie zostały pobrane ze sklepu z aplikacjami.
- **Zmiany profilu konfiguracji (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia zmiany profilów konfiguracji na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na instalowanie profilów konfiguracji.
- **Blokada aktywacji (tylko nadzorowany)**: wybierz pozycję **Zezwalaj**, aby umożliwić stosowanie blokady aktywacji na nadzorowanych urządzeniach z systemem iOS. Blokada aktywacji utrudnia ponowne aktywowanie utraconego lub skradzionego urządzenia.
- **Blokuj usuwanie aplikacji (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom usuwanie aplikacji. Pozycja **Nieskonfigurowane** pozwala użytkownikom na usuwanie aplikacji z urządzenia.
- **Blokuje tryb ograniczony USB (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby wyłączyć tryb ograniczony USB na urządzeniach w trybie nadzorowanym. Tryb ograniczony USB uniemożliwia akcesoriom USB wymienianie danych z urządzeniem zablokowanym przez ponad godzinę. Pozycja **Nieskonfigurowane** zezwala na stosowanie trybu ograniczonego USB.
- **Wymuszanie automatycznej daty i godziny (tylko nadzorowany)**: pozycja **Wymagaj** wymusza automatyczne ustawianie daty i godziny na urządzeniach nadzorowanych. Strefa czasowa urządzenia jest aktualizowana, gdy urządzenie ma połączenie komórkowe lub sieć Wi-Fi z włączonymi usługami lokalizacji.
- **Wymagaj, aby uczniowie prosili o zezwolenie na opuszczenie kursu aplikacji Classroom (tylko nadzorowany)**: pozycja **Wymagaj** wymusza, aby uczniowie zarejestrowani na niezarządzanych zajęciach prosili nauczyciela o pozwolenie na opuszczenie kursu przy użyciu aplikacji Classroom. Dostępne tylko w systemie iOS 11.3+. Pozycja **Nieskonfigurowane** oznacza, że uczeń nie musi prosić o pozwolenie.
- **Zezwalaj na bezprzewodowe aktualizacje infrastruktury PKI**: pozycja **Zezwalaj** pozwala użytkownikom na otrzymywanie aktualizacji oprogramowania bez podłączania urządzeń do komputera.
- **Ograniczanie śledzenia reklam**: wybierz pozycję **Ogranicz**, aby wyłączyć identyfikator treści reklamowych urządzenia. Pozycja **Nieskonfigurowane** powoduje, że identyfikator pozostaje włączony.
- **Blokowanie tworzenia sieci VPN (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikom tworzenie ustawień konfiguracji sieci VPN. Pozycja **Nieskonfigurowane** pozwala użytkownikom na tworzenie sieci VPN na urządzeniu.

## <a name="configurations-requiring-supervision"></a>Konfiguracje wymagające nadzoru

Tryb nadzorowany systemu iOS można włączyć tylko podczas początkowego konfigurowania urządzenia za pośrednictwem programu Device Enrollment Program firmy Apple lub programu Apple Configurator. Po włączeniu trybu nadzorowanego na urządzeniu można skonfigurować następujące funkcje za pomocą usługi Intune:

- Blokada aplikacji (tryb jednej aplikacji) 
- Globalny serwer proxy HTTP 
- Obejście blokady aktywacji 
- Autonomiczny tryb jednej aplikacji 
- Filtr zawartości internetowej 
- Ustawianie tła i ekranu blokady 
- Dyskretne wypychanie aplikacji 
- Zawsze włączona sieć VPN 
- Zezwalanie wyłącznie na instalację zarządzanych aplikacji 
- iBookstore 
- iMessages 
- Centrum gier 
- AirDrop 
- AirPlay 
- Parowanie hostów 
- Synchronizacja z chmurą 
- Wyszukiwanie Spotlight 
- Handoff 
- Wymazywanie urządzenia 
- Interfejs użytkownika ograniczeń 
- Instalacja profilów konfiguracji przez interfejs użytkownika 
- News 
- Skróty klawiaturowe 
- Modyfikacje kodu dostępu 
- Zmiany nazwy urządzenia 
- Automatyczne pobieranie aplikacji 
- Zmiany zaufania aplikacji przedsiębiorstwa 
- Apple Music 
- Mail Drop 
- Parowanie z zegarkiem Apple Watch 

> [!NOTE]
> Firma Apple potwierdza, że w 2019 r. niektóre ustawienia będą dostępne wyłącznie w trybie nadzorowanym. Zalecamy wzięcie tego pod uwagę podczas używania tych ustawień zamiast czekania, aż firma Apple przeprowadzi ich migrację do trybu nadzorowanego:
> - Instalowanie aplikacji przez użytkowników końcowych
> - Usuwanie aplikacji
> - FaceTime
> - Safari
> - iTunes
> - Zawartość dla dorosłych
> - Dokumenty i dane iCloud
> - Gry dla wielu graczy
> - Dodaj przyjaciół centrum gier
> - Siri

## <a name="password"></a>Hasło

- **Hasło**: Wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia. Pozycja Nieskonfigurowane umożliwia użytkownikom uzyskiwanie dostępu do urządzenia bez wprowadzania hasła.
  - **Proste hasła**: wybierz pozycję **Blokuj**, aby wymagać bardziej złożonych haseł. Pozycja **Nieskonfigurowane** zezwala na proste hasła, takie jak `0000` i `1234`.
  - **Wymagany typ hasła**: wybierz typ hasła, którego wymaga organizacja. Dostępne opcje:
    - **Ustawienie domyślne urządzenia**
    - **Numeryczne**
    - **Alfanumeryczne**
  - **Liczba znaków innych niż alfanumeryczne w haśle**: wprowadź liczbę znaków symboli, takich jak `#` lub `@`, którą musi zawierać hasło.
  - **Minimalna długość hasła**: podaj minimalną długość hasła, które musi wprowadzić użytkownik (od 4 do 14 znaków).
  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: wprowadź liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem urządzenia (od 1 do 11).
  - **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**<sup>1</sup>: podaj, jak długo urządzenie pozostanie bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło. Jeśli wprowadzony czas jest dłuższy niż aktualnie ustawiony na urządzeniu, urządzenie ignoruje wprowadzony przez Ciebie czas. Obsługiwane na urządzeniach z systemem iOS 8.0 i nowszym.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**<sup>1</sup>: wprowadź maksymalną dopuszczalną liczbę minut braku aktywności przed automatycznym zablokowaniem ekranu. Jeśli wprowadzony czas jest dłuższy niż aktualnie ustawiony na urządzeniu, urządzenie ignoruje wprowadzony przez Ciebie czas.
  - **Wygaśnięcie hasła (dni)**: wprowadź liczbę dni, po której należy zmienić hasło urządzenia.
  - **Zapobiegaj ponownemu używaniu poprzednich haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła.
  - **Odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie odcisku palca do odblokowywania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu odcisku palca.
- **Modyfikacja kodu dostępu (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić zmianę, dodanie lub usunięcie kodu dostępu. Po zablokowaniu tej funkcji zmiany ograniczeń kodu dostępu są ignorowane na urządzeniach nadzorowanych. Pozycja **Nieskonfigurowane** umożliwia dodawanie, zmienianie lub usuwanie kodów dostępu.
  - **Modyfikacja odcisku palca (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia zmianę, dodawanie lub usuwanie odcisków palców identyfikatora TouchID. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi aktualizowanie odcisków palców identyfikatora TouchID na urządzeniu.
- **Blokuj automatyczne wypełnianie haseł (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie funkcji automatycznego wypełniania haseł w systemie iOS. Wybranie pozycji **Blokuj** ma również następujące skutki:
  - Użytkownicy nie są monitowani o użycie zapisanego hasła w przeglądarce Safari ani innych aplikacjach.
  - Automatyczne silne hasła są wyłączone i silne hasła nie są zalecane dla użytkowników.

  Pozycja **Nieskonfigurowane** zezwala na te funkcje.

- **Blokuj zbliżeniowe żądania haseł (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby urządzenie użytkownika nie żądało haseł od urządzeń znajdujących się w pobliżu. Pozycja **Nieskonfigurowane** zezwala na te żądania haseł.
- **Blokuj udostępnianie haseł (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia udostępnianie haseł między urządzeniami przy użyciu funkcji AirDrop. Pozycja **Nieskonfigurowane** umożliwia udostępnianie haseł.

<sup>1</sup>W przypadku skonfigurowania ustawień **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** i **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** są one stosowane jedno po drugim. Na przykład jeśli wartość obu ustawień jest ustawiona na **5** minut, ekran wyłącza się automatycznie po pięciu minutach, a urządzenie jest blokowane po kolejnych pięciu minutach. Jednak jeśli użytkownik wyłączy ekranie ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie jeśli użytkownik wyłączy ekran, po pięciu minutach urządzenie zostanie zablokowane.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

- **Dostęp do centrum sterowania, gdy urządzenie jest zablokowane**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane.
- **Powiadomienia, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia dostęp do powiadomień, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na dostęp do powiadomień bez odblokowywania urządzenia.
- **Powiadomienia aplikacji Portfel, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane.
- **Widok Dzisiaj, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia użytkownikowi dostęp do widoku Dzisiaj, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi wyświetlanie widoku Dzisiaj, gdy urządzenie jest zablokowane.

## <a name="app-store-doc-viewing-gaming"></a>Sklep App Store, wyświetlanie dokumentów, granie

- **Sklep z aplikacjami**: pozycja **Blokuj** uniemożliwia dostęp do sklepu z aplikacjami na urządzeniach nadzorowanych. Pozycja **Nieskonfigurowane** zezwala na dostęp.
  - **Instalowanie aplikacji ze sklepu z aplikacjami (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby zablokować sklep z aplikacjami na ekranie głównym urządzenia. Użytkownicy końcowi nadal mogą instalować aplikacje przy użyciu programu iTunes lub Apple Configurator. Pozycja **Nieskonfigurowane** umożliwia na korzystanie ze sklepu z aplikacjami na ekranie głównym.
  - **Automatyczne pobieranie aplikacji (tylko tryb nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić automatyczne pobieranie aplikacji zakupionych na innych urządzeniach. Nie wpływa to na aktualizacje istniejących aplikacji. Pozycja **Nieskonfigurowane** umożliwia pobieranie aplikacji zakupionych na innych urządzeniach z systemem iOS na urządzenie użytkownika.
- **Hasło dostępu do sklepu z aplikacjami**: pozycja **Wymagaj** wymusza na użytkowniku wprowadzenie hasła przed odwiedzeniem sklepu z aplikacjami. Pozycja **Nieskonfigurowane** umożliwia użytkownikom uzyskiwanie dostępu do sklepu za aplikacjami bez wprowadzania hasła.
- **Zakupy w aplikacji**: wybierz pozycję **Blokuj**, aby uniemożliwić dokonywanie zakupów w aplikacji ze sklepu. Pozycja **Nieskonfigurowane** zezwala na zakupy w sklepie w uruchomionej aplikacji.
- **Jawna zawartość programu iTunes — muzyka, podcasty lub wiadomości (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić ujawnianie zawartości programu iTunes: muzyki, podkastów lub wiadomości. Pozycja **Nieskonfigurowane** zezwala urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych.
- **Pobieranie ze sklepu iBook zawartości oznaczonej jako „Erotyka”**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom pobieranie ze sklepu iBook multimediów oznaczonych jako erotyka. Pozycja **Nieskonfigurowane** zezwala użytkownikom na pobieranie ze sklepu iBook książek z kategorii „Erotyka”.
- **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych**: pozycja **Blokuj** uniemożliwia wyświetlanie dokumentów innych niż firmowe w aplikacjach niezarządzanych. Pozycja **Nieskonfigurowane** zezwala na wyświetlanie dokumentów firmowych w dowolnej aplikacji. Na przykład chcesz uniemożliwić użytkownikom zapisywanie plików z aplikacji OneDrive w aplikacji Dropbox. Skonfiguruj to ustawienie jako **Blokuj**. Jeśli urządzenie otrzymało zasady (na przykład po ponownym uruchomieniu), nie ma już możliwości zapisywania.
  - **Zezwalaj aplikacjom zarządzanym na zapisywanie kontaktów na kontach niezarządzanych kontaktów**: po ustawieniu opcji **Zezwalaj** użytkownicy mogą dodawać lub synchronizować informacje kontaktowe dowolnej osoby w programie Outlook, w tym kontakty biznesowe i firmowe, przy użyciu wbudowanej aplikacji Kontakty na urządzeniu. Po ustawieniu opcji **Nieskonfigurowane** użytkownicy nie mogą dodawać kontaktów programu Outlook do wbudowanej aplikacji Kontakty na urządzeniu.
  
    Aby użyć tego ustawienia, skonfiguruj ustawienie **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych** na wartość **Blokuj**.
  
- **Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych**: pozycja **Blokuj** uniemożliwia wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych. Pozycja **Nieskonfigurowane** zezwala na wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.
  - **Zezwalaj niezarządzanym aplikacjom na odczytywanie z kont kontaktów zarządzanych**: ustawienie opcji **Zezwalaj** powoduje, że użytkownicy mogą dodawać informacje kontaktowe dowolnej osoby z aplikacji iContacts do programu Outlook. Ustawienie opcji **Nieskonfigurowane** zapobiega odczytywaniu informacji z wbudowanej aplikacji Kontakty na urządzeniu oraz uniemożliwia usuwanie duplikatów.
  
    Aby użyć tego ustawienia, skonfiguruj ustawienie **Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych** na wartość **Blokuj**.
  
- **Traktuj usługę AirDrop jako niezarządzane miejsce docelowe**: pozycja **Wymagaj** wymusza traktowanie usługi AirDrop jako niezarządzanego miejsca docelowego upuszczania. Uniemożliwia to aplikacjom zarządzanym wysyłanie danych przy użyciu usługi AirDrop. 
- **Dodawanie znajomych do usługi Game Center (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikom dodawanie znajomych do usługi Game Center. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi dodawanie znajomych do usługi Game Center.
- **Game Center (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia korzystanie z aplikacji Game Center. Pozycja **Nieskonfigurowane** umożliwia używanie aplikacji Game Center na urządzeniu.
- **Gry dla wielu graczy (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić korzystanie z gier dla wielu graczy. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na gry dla wielu graczy na urządzeniu.
- **Region klasyfikacji**: wybierz region klasyfikacji, którego chcesz użyć w przypadku dozwolonych plików do pobrania. Następnie wybierz dozwoloną klasyfikację dla kategorii **Filmy** i **Programy TV**.
- **Aplikacje**: wybierz dozwoloną klasyfikację wiekową dla aplikacji, które użytkownicy mogą pobierać, lub wybierz pozycję **Zezwalaj na wszystkie aplikacje**.

## <a name="built-in-apps"></a>Aplikacje wbudowane

- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na dostęp do aparatu urządzenia.
  - **FaceTime**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji FaceTime. Pozycja **Nieskonfigurowane** zezwala na dostęp do aplikacji FaceTime na urządzeniu.
- **Siri**: pozycja **Blokuj** uniemożliwia dostęp do programu Siri. Pozycja **Nieskonfigurowane** umożliwia korzystanie z asystenta głosowego Siri na urządzeniu.
  - **Program Siri, gdy urządzenie jest zablokowane**: wybierz pozycję **Blokuj** aby uniemożliwić dostęp do programu Siri, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** umożliwia korzystanie z asystenta głosowego Siri na zablokowanym urządzeniu.
  - **Filtr wulgaryzmów Siri (tylko nadzorowany)**: pozycja **Wymagaj** uniemożliwia dyktowanie lub wypowiadanie wulgaryzmów przez Siri.
  - **Wyszukiwanie zawartości wygenerowanej przez użytkowników z sieci Internet przez Siri (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia programowi Siri dostęp do witryn internetowych w celu udzielania odpowiedzi na pytania. Pozycja **Nieskonfigurowane** zezwala programowi Siri na dostęp do zawartości wygenerowanej przez użytkowników z Internetu.
- **Apple News (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji Apple News na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie aplikacji Apple News.
- **Sklep iBooks (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia dostęp do sklepu iBooks. Pozycja **Nieskonfigurowane** pozwala użytkownikom na przeglądanie i kupowanie książek w sklepie iBooks.
- **Aplikacja Wiadomości na urządzeniu (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby użytkownicy nie mogli używać aplikacji Wiadomości na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia wysyłanie i odbieranie wiadomości tekstowych przy użyciu aplikacji Wiadomości.
- **Podcasty (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikom używanie aplikacji Podcasty. Pozycja **Nieskonfigurowane** umożliwia używanie aplikacji Podcasty.
- **Usługa Music (tylko nadzorowany)**: pozycja **Blokuj** przywraca aplikację do obsługi muzyki do trybu klasycznego i wyłącza usługę Music. Pozycja **Nieskonfigurowane** umożliwia używanie aplikacji Apple Music.
- **Usługa iTunes Radio (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikom korzystanie z aplikacji iTunes Radio. Pozycja **Nieskonfigurowane** umożliwia używanie aplikacji iTunes Radio.
- **Zmiany ustawień aplikacji Znajdź moich znajomych (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia zmiany ustawień aplikacji Znajdź moich znajomych. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi zmienianie ustawień aplikacji Znajdź moich znajomych.
- **Wyszukiwanie Spotlight wyników z Internetu (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.
- **Blokowanie usuwania aplikacji systemowych z urządzenia (tylko nadzorowany)**: wybranie pozycji **Blokuj** wyłącza możliwość usuwania aplikacji systemowych z urządzenia. Pozycja **Nieskonfigurowane** pozwala użytkownikom na usuwanie aplikacji systemowych.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

- **Aplikacje zabronione**: lista aplikacji niezarządzanych przez usługę Intune, które nie powinny być instalowane na urządzeniu. Jeśli użytkownik instaluje aplikację z tej listy, otrzymujesz powiadomienie z usługi Intune.
- **Aplikacje zatwierdzone**: lista aplikacji, które użytkownicy mogą instalować. Aby zachować zgodność, użytkownicy nie mogą instalować innych aplikacji. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Jeśli użytkownik instaluje aplikację z tej listy, otrzymujesz powiadomienie z usługi Intune.

Aby dodać aplikacje do tych list, możesz:

- **Dodać** adres URL sklepu z aplikacjami iTunes dla wybranej aplikacji. Na przykład w celu dodania aplikacji folderów roboczych systemu Microsoft wprowadź `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Aby znaleźć adres URL aplikacji, otwórz sklep iTunes App Store i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop` lub `Microsoft Word`. Wybierz aplikację i skopiuj adres URL.

  Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć zadania **Kopiuj link**, aby uzyskać adres URL aplikacji.

- Zaimportować plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app url>, <app name>, <app publisher>`. Możesz również wyeksportować istniejącą listę, który zawiera listę aplikacji z ograniczeniami w tym samym formacie.

> [!IMPORTANT]
> Profile urządzeń, które używają ustawień aplikacji z ograniczeniami, należy przypisać do grup użytkowników.

## <a name="show-or-hide-apps-supervised-only"></a>Pokaż lub ukryj aplikacje (tylko nadzorowany)

Na liście Pokaż lub ukryj aplikacje możesz skonfigurować jedną z następujących list na urządzeniach nadzorowanych z systemem iOS 9.3 lub nowszym.

- **Ukryte aplikacje**: wprowadź listę aplikacji ukrywanych przed użytkownikami. Użytkownicy nie mogą wyświetlać ani otwierać tych aplikacji.
- **Widoczne aplikacje**: wprowadź listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Aby dodać aplikacje do tych list, możesz:

- **Dodać** adres URL sklepu z aplikacjami iTunes dla wybranej aplikacji. Na przykład w celu dodania aplikacji folderów roboczych systemu Microsoft wprowadź `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Aby znaleźć adres URL aplikacji, otwórz sklep iTunes App Store i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop` lub `Microsoft Word`. Wybierz aplikację i skopiuj adres URL.

  Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć zadania **Kopiuj link**, aby uzyskać adres URL aplikacji.

- Zaimportować plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app url>, <app name>, <app publisher>`. Możesz również wyeksportować istniejącą listę, który zawiera listę aplikacji z ograniczeniami w tym samym formacie.

## <a name="wireless"></a>Sieć bezprzewodowa

- **Roaming danych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming danych w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.
- **Globalne pobieranie w tle podczas roamingu**: pozycja **Blokuj** uniemożliwia używanie funkcji globalnego pobierania w tle podczas roamingu w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala urządzeniu na pobieranie danych, np. wiadomości e-mail, w roamingu w sieci komórkowej.
- **Wybieranie głosowe**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom korzystanie z funkcji wybierania głosowego na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia wybieranie głosowe na urządzeniu.
- **Roaming połączeń głosowych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming połączeń danych w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.
- **Zmiany ustawień użycia danych komórkowych aplikacji (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić zmiany ustawień użycia danych komórkowych aplikacji. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi kontrolowanie, które aplikacje mogą korzystać z danych komórkowych.
- **Osobisty hotspot**: pozycja **Blokuj** uniemożliwia używanie urządzenia jako osobistego hotspotu. To ustawienie może być niezgodne w przypadku niektórych operatorów. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Dołączaj do sieci Wi-Fi wyłącznie za pomocą profilów konfiguracji (tylko nadzorowany)**: pozycja **Wymagaj** wymusza użycie na urządzeniu tylko sieci Wi-Fi, które zostały skonfigurowane przy użyciu profilu konfiguracji usługi Intune. Pozycja **Nieskonfigurowane** zezwala urządzeniu na korzystanie z innych sieci Wi-Fi.
- **Zasady użycia danych komórkowych (tylko aplikacje zarządzane)**: zdefiniuj typy danych, których aplikacje zarządzane mogą używać podczas pracy w sieciach komórkowych. Dostępne opcje:
  - **Zablokuj użycie danych komórkowych**: zablokuj użycie danych komórkowych dla **wszystkich zarządzanych aplikacji** lub **wybierz określone aplikacje**.
  - **Zablokuj użycie danych komórkowych podczas roamingu**: zablokuj użycie danych komórkowych podczas roamingu dla **wszystkich zarządzanych aplikacji** lub **wybierz określone aplikacje**.

## <a name="connected-devices"></a>Połączone urządzenia

- **AirDrop (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia używanie funkcji AirDrop na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
- **Parowanie z urządzeniem Apple Watch (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia parowanie urządzenia z urządzeniem Apple Watch. Pozycja **Nieskonfigurowane** zezwala na parowanie urządzenia z zegarkiem Apple Watch.
- **Wykrywanie nadgarstka przez sparowane urządzenie Apple Watch**: pozycja **Wymagaj** wymusza używanie funkcji wykrywania nadgarstka na sparowanym zegarku Apple Watch. Jeśli ta opcja jest wymagana, zegarek Apple Watch nie będzie wyświetlać powiadomień, kiedy nie będzie znajdować się na nadgarstku użytkownika. 
- **Modyfikacja protokołu Bluetooth (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikowi końcowemu zmianę ustawień protokołu Bluetooth na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi zmianę tych ustawień.
- **Parowanie hosta na potrzeby kontrolowania urządzeń, z którymi można parować urządzenie z systemem iOS (tylko nadzorowany)**: pozycja **Nieskonfigurowane** zezwala na parowanie hostów w celu umożliwienia administratorowi kontrolowania tego, z którymi urządzeniami może być sparowane urządzenie z systemem iOS. Pozycja **Blokuj** uniemożliwia parowanie hosta.
- **Wymagaj hasła parowania dla wychodzących żądań AirPlay**: pozycja **Wymagaj** umożliwia wymaganie hasła parowania, gdy użytkownik używa funkcji AirPlay do strumieniowego przesyłania zawartości do innych urządzeń firmy Apple. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi przesyłanie strumieniowe zawartości przy użyciu funkcji AirPlay bez wprowadzania hasła.
- **Blokuj funkcję AirPrint (tylko nadzorowany)**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie funkcji AirPrint na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z funkcji AirPrint.
  - **Blokuj przechowywanie poświadczeń AirPrint w pęku kluczy (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia korzystanie z magazynu pęku kluczy do przechowywania nazwy użytkownika i hasła na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia przechowywanie nazwy użytkownika i hasła funkcji AirPrint w aplikacji pęku kluczy.
  - **Wymagaj zaufanego certyfikatu TLS na potrzeby funkcji AirPrint (tylko nadzorowany)**: pozycja **Wymagaj** wymusza użycie zaufanych certyfikatów na potrzeby komunikacji dotyczącej drukowania przy użyciu protokołu TLS.
  - **Blokuj odnajdywanie drukarek AirPrint za pomocą protokołu iBeacon (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia złośliwym sygnałom nawigacyjnym funkcji AirPrint Bluetooth wyłudzanie informacji dotyczących ruchu sieciowego. Pozycja **Nieskonfigurowane** zezwala na reklamy drukarek AirPrint na urządzeniu.

## <a name="keyboard-and-dictionary"></a>Klawiatura i słownik

- **Wyszukiwanie definicji słów (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikom wyróżnianie wyrazu, a następnie wyszukiwanie jego definicji na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na dostęp do funkcji wyszukiwania definicji.
- **Klawiatury predykcyjne (tylko nadzorowany)**: pozycja **Nieskonfigurowane** umożliwia korzystanie z klawiatur predykcyjnych sugerujących wyrazy, które użytkownik może chcieć wpisać. Pozycja **Blokuj** uniemożliwia użycie tej funkcji.
- **Korekta automatyczna (tylko nadzorowany)**: pozycja **Nieskonfigurowane** pozwala na automatyczne poprawianie błędnie napisanych wyrazów przez urządzenie. Pozycja **Blokuj** uniemożliwia korzystanie z autokorekty.
- **Funkcja sprawdzania pisowni klawiatury (tylko nadzorowany)**: pozycja **Nieskonfigurowane** umożliwia używanie sprawdzania pisowni na urządzeniu. Pozycja **Blokuj** pozwala na sprawdzanie pisowni.
- **Skróty klawiaturowe (tylko nadzorowany)**: pozycja **Nieskonfigurowane** umożliwia używanie skrótów klawiaturowych na urządzeniu. Pozycja **Blokuj** uniemożliwia użytkownikowi korzystanie ze skrótów klawiaturowych.
- **Dyktowanie (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z wprowadzania tekstu przez dyktowanie.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Tworzenie kopii zapasowych w usłudze iCloud**: pozycja **Nieskonfigurowane** umożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud. Pozycja **Blokuj** uniemożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud.
- **Synchronizowanie dokumentów z usługą iCloud (tylko nadzorowany)**: pozycja **Nieskonfigurowane** umożliwia synchronizowanie dokumentów i par klucz-wartość w obszarze magazynu usługi iCloud. Pozycja **Blokuj** uniemożliwia synchronizowanie dokumentów i danych w usłudze iCloud.
- **Synchronizowanie strumienia zdjęć z usługą iCloud**: pozycja **Nieskonfigurowane** umożliwia użytkownikom włączanie funkcji **Mój strumień zdjęć** na urządzeniu, co pozwala na synchronizowanie z usługą iCloud i udostępnianie zdjęć na wszystkich urządzeniach użytkownika. Pozycja **Blokuj** zezwala na synchronizację funkcji Strumień zdjęć w usłudze iCloud.
- **Szyfrowana kopia zapasowa**: pozycja **Wymagaj** umożliwia wymaganie szyfrowania wszystkich kopii zapasowych urządzenia.
- **Biblioteka zdjęć usługi iCloud**: ustaw tę opcję na pozycję **Blokuj**, aby wyłączyć możliwość używania biblioteki zdjęć usługi iCloud do przechowywania zdjęć i klipów wideo w chmurze. Wszystkie zdjęcia, które nie zostały w pełni pobrane z biblioteki zdjęć iCloud na urządzenie, są usuwane z urządzenia. Pozycja **Nieskonfigurowane** umożliwia używanie biblioteki zdjęć iCloud.
- **Zarządzane aplikacje są synchronizowane z chmurą**: pozycja **Nieskonfigurowane** zezwala aplikacjom zarządzanym usługi Intune na synchronizowanie danych z kontem użytkownika w usłudze iCloud. Pozycja **Blokuj** uniemożliwia taką synchronizację danych z usługą iCloud.
- **Udostępniony strumień zdjęć**: wybierz pozycję **Blokuj**, aby wyłączyć funkcję **Udostępnianie zdjęć w usłudze iCloud** na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia przesyłanie strumieniowe udostępnionych zdjęć.
- **Kontynuacja aktywności**: pozycja **Nieskonfigurowane** umożliwia użytkownikom kontynuowanie pracy rozpoczętej na urządzeniu z systemem iOS na innym urządzeniu z systemem iOS lub macOS (program Handoff). Pozycja **Blokuj** uniemożliwia użycie programu Handoff.
- **Blokuj synchronizowanie pęku kluczy z usługą iCloud**: wybierz pozycję **Blokuj**, aby wyłączyć synchronizowanie poświadczeń przechowywanych w pęku kluczy z usługą iCloud. Pozycja **Nieskonfigurowane** umożliwia użytkownikom synchronizację tych poświadczeń.
- **Blokuj tworzenie kopii zapasowych książek przedsiębiorstwa**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom tworzenie kopii zapasowej książek przedsiębiorstwa. Pozycja **Nieskonfigurowane** umożliwia użytkownikom tworzenie kopii zapasowych tych książek.
- **Blokuj synchronizację metadanych książek przedsiębiorstwa (notatki i wyróżnienia)**: pozycja **Blokuj** uniemożliwia synchronizowanie notatek i wyróżnień w książkach przedsiębiorstwa. Pozycja **Nieskonfigurowane** zezwala na synchronizowanie.

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonomiczny tryb jednej aplikacji (tylko tryb nadzorowany)

Użyj tych ustawień w celu skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w autonomicznym trybie pojedynczej aplikacji. Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane. Może ono uruchamiać wyłącznie tę aplikację. Na przykład dodaj aplikację, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

Aby dodać aplikacje, możesz wykonać następujące czynności:

- Wprowadź **nazwę aplikacji** i **identyfikator pakietu aplikacji**, a następnie wybierz pozycję **Dodaj**. Sekcja [Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS](#bundle-id-reference-for-built-in-ios-apps) (w tym artykule) zawiera niektóre aplikacje i ich identyfikatory.
- **Zaimportuj** plik CSV zawierający listę nazw aplikacji i ich identyfikatorów pakietu. Lub **wyeksportuj**  istniejącą listę, która zawiera aplikacje.

## <a name="kiosk-supervised-only"></a>Kiosk (tylko nadzorowany)

- **Aplikacja do uruchamiania w trybie kiosku**: wybierz typ aplikacji, które chcesz uruchomić w trybie kiosku. Dostępne opcje: 
  - **Aplikacja ze Sklepu**: wprowadź adres URL aplikacji w sklepie iTunes
  - **Zarządzana aplikacja**: wybierz aplikację dodaną do usługi Intune
  - **Wbudowana aplikacja**: wprowadź [identyfikator pakietu](#bundle-id-reference-for-built-in-ios-apps) wbudowanej aplikacji

- **Obsługa dotykowa z ułatwieniami**: pozycja **Wymagaj** wymusza ustawienie ułatwień dostępu Obsługa dotykowa z ułatwieniami na urządzeniu. Ta funkcja pomaga użytkownikom wykonywać na ekranie gesty, które mogą okazać się trudne. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Odwróć kolory**: pozycja **Wymagaj** wymusza użycie ułatwień dostępu Odwróć kolory, co umożliwia użytkownikom niedowidzącym zmienianie ustawień ekranu. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Dźwięk mono**: pozycja **Wymagaj** wymaga ustawienia ułatwienia dostępu Dźwięk mono na urządzeniu. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **VoiceOver**: pozycja **Wymagaj** wymusza użycie na urządzeniu ustawienia ułatwień dostępu VoiceOver, aby tekst na ekranie mógł być odczytywany na głos. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Powiększenie**: pozycja **Wymagaj** wymusza użycie ustawienia Powiększenie na urządzeniu, aby umożliwić użytkownikom powiększenie obrazu wyświetlanego na ekranie za pomocą dotyku. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Blokada automatyczna**: pozycja **Zezwalaj** pozwala na automatyczne blokowanie urządzenia. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Przełącznik dzwonka**: pozycja **Zezwalaj** pozwala na użycie przełącznika dzwonka (wyciszenie) na urządzeniu. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Obrót ekranu**: pozycja **Zezwalaj** pozwala na zmianę orientacji ekranu przy obrocie urządzenia. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Przycisk usypiania ekranu**: wybierz pozycję **Zezwalaj**, aby wyłączyć przycisk usypiania/budzenia ekranu na urządzeniu. Pozycja **Nieskonfigurowane** włącza tę funkcję.
- **Dotyk**: pozycja **Blokuj** wyłącza ekran dotykowy na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z ekranu dotykowego.
- **Przyciski regulacji głośności**: pozycja **Zezwalaj** pozwala na użycie przycisków regulacji głośności na urządzeniu. Pozycja **Nieskonfigurowane** wyłącza przyciski regulacji głośności.
- **Wspomagająca kontrola dotykowa**: pozycja **Zezwalaj** pozwala użytkownikom na korzystanie z funkcji obsługi dotykowej z ułatwieniami. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Odwróć kontrolę kolorów**: pozycja **Zezwalaj** pozwala na zmianę ustawienia funkcji Odwróć kolory, które umożliwiają użytkownikowi dostosowanie jej do własnych potrzeb. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Mów przy wybranym tekście**: pozycja **Zezwalaj** umożliwia użycie ustawienia ułatwień dostępu Czytaj zaznaczenie na urządzeniu. Ta funkcja odczytuje tekst, który użytkownik wybierze przy użyciu głosu. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Kontrola VoiceOver**: pozycja **Zezwalaj** umożliwia zmiany podkładu głosowego, aby zezwolić użytkownikom na aktualizowanie ustawień funkcji VoiceOver, takich jak szybkość odczytywania tekstu na głos. Pozycja **Nieskonfigurowane** uniemożliwia zmiany podkładu głosowego.
- **Ustawianie powiększania**: pozycja **Zezwalaj** umożliwia użytkownikowi zmienianie powiększenia. Pozycja **Nieskonfigurowane** uniemożliwia zmiany powiększenia.

> [!NOTE]
> Aby można było skonfigurować urządzenie z systemem iOS do obsługi trybu kiosku, należy najpierw użyć narzędzia Apple Configurator lub programu Apple Device Enrollment Program w przełączenia go do trybu nadzorowanego. Zapoznaj się z przewodnikiem firmy Apple dotyczącym korzystania z narzędzia Apple Configurator.
> Jeśli wprowadzona aplikacja systemu iOS zostanie zainstalowana po przypisaniu profilu, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS

Ta lista zawiera identyfikatory pakietu typowych wbudowanych aplikacji systemu iOS. Aby wyszukać identyfikatory pakietu innych aplikacji, skontaktuj się z dostawcą oprogramowania.

| Identyfikator pakietu                   | Nazwa aplikacji     | Wydawca |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | App Store    | Apple     |
| com.apple.calculator        | Kalkulator   | Apple     |
| com.apple.mobilecal         | Kalendarz     | Apple     |
| com.apple.camera            | Aparat fotograficzny       | Apple     |
| com.apple.mobiletimer       | Zegar        | Apple     |
| com.apple.compass           | Kompas      | Apple     |
| com.apple.MobileAddressBook | Kontakty     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.mobileme.fmf1     | Moi znajomi | Apple     |
| com.apple.mobileme.fmip1    | Znajdź mój iPhone  | Apple     |
| com.apple.gamecenter        | Centrum gier  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Kondycja       | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Mapy         | Apple     |
| com.apple.MobileSMS         | Komunikaty     | Apple     |
| com.apple.Music             | Muzyka        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Uwagi        | Apple     |
| com.apple.Numbers           | Liczby      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Zdjęcia       | Apple     |
| com.apple.podcasts          | Podcasty     | Apple     |
| com.apple.reminders         | Przypomnienia    | Apple     |
| com.apple.MobileSafari      | Safari       | Apple     |
| com.apple.Preferences       | Ustawienia     | Apple     |
| com.apple.stocks            | Giełda       | Apple     |
| com.apple.tips              | Porady         | Apple     |
| com.apple.videos            | Filmy       | Apple     |
| com.apple.VoiceMemos        | Dyktafon   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Zegarek        | Apple     |
| com.apple.weather           | Pogoda      | Apple     |

## <a name="safari"></a>Safari

- **Safari (tylko nadzorowany)**: pozycja **Blokuj** uniemożliwia korzystanie z przeglądarki Safari na urządzeniu. Pozycja **Nieskonfigurowane** pozwala użytkownikom na używanie przeglądarki Safari.
- **Autowypełnianie**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania w przeglądarce Safari na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień automatycznego uzupełniania w przeglądarce internetowej.
- **Pliki cookie**: wybierz sposób obsługi plików cookie na urządzeniu. Dostępne opcje:
  - Zezwalaj
  - Blokuj wszystkie pliki cookie
  - Zezwalaj na pliki cookie z odwiedzonych witryn internetowych
  - Zezwalaj na pliki cookie z aktualnej witryny internetowej
- **JavaScript**: pozycja **Blokuj** uniemożliwia uruchamianie skryptów języka Java w przeglądarce na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na używanie skryptów języka Java.
- **Ostrzeżenia przed oszustwem**: pozycja **Wymagaj** wymusza pokazywanie ostrzeżeń o oszustwie w przeglądarce internetowej na urządzeniu. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Wyskakujące okienka**: pozycja **Blokuj** umożliwia blokowanie wyskakujących okienek w przeglądarce internetowej. Pozycja **Nieskonfigurowane** umożliwia blokowanie wyskakujących okienek.

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nieoznaczone domeny poczty e-mail

W obszarze **Adres URL domeny poczty e-mail** dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy końcowi otrzymają wiadomość e-mail z domeny innej niż wprowadzona, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu iOS jako niezaufana.

### <a name="managed-web-domains"></a>Zarządzane domeny sieci Web

W obszarze **Adres URL domeny internetowej** dodaj do listy co najmniej jeden adres URL. Dokumenty pobierane z wprowadzonych domen są uznawane za zarządzane. To ustawienie ma zastosowanie wyłącznie do dokumentów pobieranych przy użyciu przeglądarki Safari.

### <a name="safari-password-autofill-domains"></a>Domeny automatycznego wypełniania haseł w programie Safari

W obszarze **Adres URL domeny** dodaj do listy co najmniej jeden adres URL. Użytkownicy mogą zapisywać wyłącznie hasła witryn sieci Web dla adresów URL znajdujących się na tej liście. To ustawienie dotyczy wyłącznie przeglądarki Safari oraz urządzeń z systemem iOS w wersji 9.3 lub nowszym działających w trybie nadzorowanym. Jeśli nie podasz żadnych adresów URL, użytkownicy będą mogli zapisywać hasła ze wszystkich witryn sieci Web.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Możesz również skonfigurować ograniczenia dotyczące urządzenia i ustawienia na urządzeniu z systemem [macOS](device-restrictions-macos.md).
