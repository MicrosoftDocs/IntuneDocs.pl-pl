---
title: Ustawienia urządzenia z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodawaj, konfiguruj lub twórz ustawienia na urządzeniach z systemem iOS w celu ograniczania funkcji, na przykład ustawiania wymagań dotyczących haseł, kontrolowania zablokowanego ekranu, używania wbudowanych aplikacji, dodawania ograniczonych lub zatwierdzonych aplikacji, obsługi urządzeń z funkcją Bluetooth, łączenia z chmurą na potrzeby tworzenia kopii zapasowych i magazynowania, włączania trybu kiosku, dodawania domen oraz kontrolowania sposobu, w jaki użytkownicy pracują z przeglądarką internetową Safari w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 476817b70f18fdd45a678ef3e12d1d3312c03dd3
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206537"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem iOS lub iPadOS. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, zezwalać na działanie konkretnych aplikacji lub je ograniczać i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem iOS.

> [!TIP]
> Te ustawienia korzystają z ustawień zarządzania urządzeniami przenośnymi firmy Apple. Aby uzyskać więcej informacji na temat tych ustawień, zobacz [ustawień zarządzania urządzeniami przenośnymi firmy Apple](https://support.apple.com/guide/mdm/welcome/web) (otwiera witrynę sieci Web firmy Apple).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji ograniczeń urządzenia](../device-restrictions-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji, z uwzględnieniem niektórych ustawień, które są stosowane do wszystkich opcji rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [rejestracji w systemie iOS](../ios-enroll.md).

## <a name="general"></a>Ogólne

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Udostępnij dane użycia**: wybierz pozycję **Blokuj**, aby uniemożliwić urządzeniu wysyłanie danych diagnostycznych i danych użycia do firmy Apple. Pozycja **Nieskonfigurowane** (domyślna) umożliwia wysyłanie tych danych.

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów w urządzeniu. W systemie iOS 9,0 i nowszych jest również blokowane nagrywanie ekranu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu lub pliku wideo.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Niezaufane certyfikaty protokołu TLS**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie niezaufanych certyfikatów protokołu Transport Layer Security (TLS) na urządzeniu. Pozycja **Nieskonfigurowane** (ustawienie domyślne) pozwala na korzystanie z certyfikatów protokołu TLS.
- **pozycja** **Blokuj** uniemożliwia użytkownikom otrzymywanie aktualizacji oprogramowania, chyba że urządzenie zostało podłączone do komputera. Pozycja **Nie skonfigurowano** (wartość domyślna) umożliwia urządzeniu otrzymywanie aktualizacji oprogramowania bez połączenia z komputerem.
- **Ograniczanie śledzenia reklam**: wybierz pozycję **Ogranicz**, aby wyłączyć identyfikator treści reklamowych urządzenia. Pozycja **Nieskonfigurowane** (ustawienie domyślne) powoduje, że identyfikator pozostaje włączony.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Modyfikowanie ustawień przesyłania diagnostyki**: Pozycja **Blokuj** uniemożliwia użytkownikowi zmianę ustawień analizy aplikacji i przesyłania danych diagnostycznych w obszarze **Diagnostyka i użycie** (ustawienia urządzenia). Pozycja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi zmianę tych ustawień urządzenia.

  Aby użyć tego ustawienia, należy ustawić ustawienie **Udostępnij dane użycia**, aby **bloku**.

  Ta funkcja ma zastosowanie do:  
  - System iOS 9.3.2 i nowsze

- **Blokuj zdalne obserwowanie ekranów przez aplikację Classroom**: wybierz opcję **Blokuj**, aby nie był możliwy zdalny podgląd ekranu urządzenia za pomocą aplikacji Classroom. Pozycja **Nieskonfigurowane** (domyślna) umożliwia aplikacji Classroom firmy Apple wyświetlanie ekranu.

  Aby użyć tego ustawienia, należy ustawić **przechwytywania ekranu** ustawienia **zablokować**.

  Ta funkcja ma zastosowanie do:  
  - System iOS 9.3 i nowsze

- **Obserwacja ekranu bez monitowania za pomocą aplikacji Classroom**: w przypadku ustawienia pozycji **Zezwalaj** nauczyciele mogą dyskretnie obserwować ekrany urządzeń z systemem iOS przy użyciu aplikacji Classroom bez wiedzy uczniów. Urządzenia uczniów zarejestrowanych na zajęcia za pomocą aplikacji Classroom automatycznie udzielają uprawnień nauczycielowi na danym kursie. Pozycja **Nie skonfigurowano** (ustawienie domyślne) blokuje tę funkcję.

  Aby użyć tego ustawienia, należy ustawić **przechwytywania ekranu** ustawienia **zablokować**.

- **Zaufanie do aplikacji dla przedsiębiorstw**: wybierz pozycję **Blokuj**, aby usunąć przycisk **Ufaj deweloperowi aplikacji dla przedsiębiorstw** w obszarze Ustawienia > Ogólne > Zarządzanie profilami i urządzeniami na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi określenie, że ufa aplikacjom, które nie zostały pobrane ze sklepu z aplikacjami.
- **Modyfikacja konta**: po ustawieniu pozycji **Blokuj** użytkownik nie może aktualizować ustawień specyficznych dla urządzenia z poziomu aplikacji obsługującej ustawienia systemu iOS. Na przykład użytkownik nie może tworzyć nowych kont urządzenia lub zmieniać nazwy użytkownika albo hasła. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikom zmianę tych ustawień.

  Ta funkcja ma również zastosowanie w przypadku ustawień dostępnych z poziomu aplikacji z ustawieniami dla systemu iOS, takich jak Poczta, Kontakty, Kalendarz, Twitter i inne. Ta funkcja nie ma zastosowania w przypadku aplikacji z ustawieniami konta, których nie można skonfigurować z poziomu aplikacji obsługującej ustawienia dla systemu iOS, na przykład aplikacji Microsoft Outlook.

- **Czas korzystania z urządzenia**: Wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom określanie własnych ograniczeń w obszarze ustawień urządzenia Czas korzystania z urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na konfigurowanie ograniczeń urządzenia (na przykład kontroli rodzicielskiej oraz ograniczeń dotyczących zawartości i prywatności) na urządzeniu.

  Poprzednio to ustawienie nosiło nazwę **Włączenie ograniczeń w ustawieniach urządzenia**. Wpływ tej zmiany:  
  
  - System iOS 11.4.1 i starsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie własnych ograniczeń w ustawieniach urządzenia. Zachowanie jest takie samo, nie wprowadzono zmian dotyczących użytkowników końcowych.
  - System iOS 12.0 i nowsze: Opcja **Blokuj** uniemożliwia użytkownikom końcowym określanie własnych ustawień w obszarze **Czas korzystania z urządzenia** w ustawieniach urządzenia (Ustawienia > Ogólne > Czas korzystania z urządzenia), w tym ograniczeń dotyczących zawartości i prywatności. Na urządzeniach uaktualnionych do wersji systemu iOS 12.0 w ustawieniach urządzenia nie będzie już wyświetlana karta ograniczeń (Ustawienia > Ogólne > Zarządzanie urządzeniami > Profil zarządzania > Ograniczenia). Te ustawienia znajdują się teraz w obszarze **Czas korzystania z urządzenia**.
  
- **Użyj opcji wymazywania z urządzenia całej zawartości i wszystkich ustawień**: Wybierz pozycję **Blokuj**, aby użytkownicy nie mogli korzystać z opcji wymazywania całej zawartości i wszystkich ustawień z urządzenia. Opcja **Nieskonfigurowane** (domyślna) zapewnia użytkownikom dostęp do tych ustawień.
- **Modyfikacja nazwy urządzenia**: wybierz pozycję **Blokuj**, aby nie można było zmienić nazwy urządzenia. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi zmianę nazwy urządzenia.
- **Modyfikowanie ustawień powiadomień**: wybierz pozycję **Blokuj**, aby nie można było zmieniać ustawień powiadamiania. Opcja **Nieskonfigurowane** (domyślna) zezwala użytkownikowi na zmianę ustawień powiadomień urządzenia.
- **Modyfikowanie tapety**: pozycja **Blokuj** uniemożliwia zmianę tapety. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi zmianę tapety na urządzeniu.
- **Modyfikowanie ustawień zaufania aplikacji dla przedsiębiorstw**: pozycja **Blokuj** uniemożliwia użytkownikowi zmianę ustawień zaufania aplikacji przedsiębiorstwa na urządzeniach nadzorowanych. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi ufanie aplikacjom, które nie zostały pobrane ze sklepu z aplikacjami.
- **Zmiany profilu konfiguracji**: pozycja **Blokuj** uniemożliwia zmiany profilów konfiguracji na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) zezwala użytkownikowi na instalowanie profilów konfiguracji.
- **Blokada aktywacji**: wybierz pozycję **Zezwalaj**, aby umożliwić stosowanie blokady aktywacji na nadzorowanych urządzeniach z systemem iOS. Blokada aktywacji utrudnia ponowne aktywowanie utraconego lub skradzionego urządzenia.
- **Blokuj usuwanie aplikacji**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom usuwanie aplikacji. Opcja **Nieskonfigurowane** (domyślna) pozwala użytkownikom na usuwanie aplikacji z urządzenia.
- **Zezwalaj na akcesoria USB, gdy urządzenie jest zablokowane**: **Zezwalaj** umożliwia akcesoria USB wymianę danych z urządzeniem, które zostało zablokowane przez ponad godzinę. Pozycja **Nie skonfigurowano** (wartość domyślna) nie aktualizuje trybu ograniczonego USB na urządzeniu, a akcesoria USB nie mogą przesyłać danych z urządzenia zablokowanego przez ponad godzinę.
- **Wymuszaj automatyczne ustawianie daty i godziny**: pozycja **Wymagaj** wymusza automatyczne ustawianie daty i godziny na urządzeniach nadzorowanych. Strefa czasowa urządzenia jest aktualizowana, gdy urządzenie ma połączenie komórkowe lub sieć Wi-Fi z włączonymi usługami lokalizacji.
- **Wymagaj, aby uczeń prosił o pozwolenie na opuszczenie przedmiotu w aplikacji Classroom**: pozycja **Wymagaj** wymusza, aby uczniowie zarejestrowani na niezarządzanych zajęciach prosili nauczyciela o pozwolenie na opuszczenie kursu przy użyciu aplikacji Classroom. Opcja **Nieskonfigurowane** (domyślna) oznacza, że uczeń nie musi prosić o pozwolenie.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.3 i nowsze

- **Zezwalaj aplikacji Classroom na blokowanie aplikacji i blokowanie urządzenia bez monitu**: Pozycja **Włącz** umożliwia nauczycielowi blokowanie aplikacji lub urządzeń za pomocą aplikacji Classroom bez monitowania uczniów. Blokowanie aplikacji oznacza, że na urządzeniu można uzyskać dostęp tylko do aplikacji określonych przez nauczyciela. Pozycja **Nieskonfigurowane** (ustawienie domyślne) uniemożliwia nauczycielowi blokowanie aplikacji lub urządzeń za pomocą aplikacji Classroom bez monitowania uczniów.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze

- **Automatycznie dołączaj do zajęć w aplikacji Classroom bez monitu**: Pozycja **Włącz** automatycznie zezwala uczniom na dołączanie do zajęć w aplikacji Classroom bez monitowania nauczyciela. Pozycja **Nieskonfigurowane** (ustawienie domyślne) powoduje wyświetlenie nauczycielowi monitu o uczniach, którzy chcą dołączyć do zajęć w aplikacji Classroom.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze

- **Blokuj tworzenie sieci VPN**: pozycja **Blokuj** uniemożliwia użytkownikom tworzenie ustawień konfiguracji sieci VPN. Opcja **Nieskonfigurowane** (domyślna) pozwala użytkownikom na tworzenie sieci VPN na urządzeniu.
- **Modyfikowanie ustawień karty eSIM**: Pozycja **Blokuj** uniemożliwia użytkownikom dodawanie i usuwanie planów komórkowych w ustawieniach karty eSIM urządzenia. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikom zmianę tych ustawień.

  Ta funkcja ma zastosowanie do:  
  - System iOS 12.1 i nowsze

- **Odrocz aktualizacje oprogramowania**: Jeśli jest wybrana opcja **Nieskonfigurowane** (ustawienie domyślne), aktualizacje oprogramowania są wyświetlane na urządzeniu w momencie ich publikacji przez firmę Apple. Na przykład jeśli firma Apple opublikuje aktualizację systemu iOS określonego dnia, ta aktualizacja będzie naturalnie widoczna na urządzeniu w okolicy tego terminu.

  Pozycja **Włącz** umożliwia opóźnienie momentu wyświetlenia aktualizacji oprogramowania na urządzeniach o określony czas z przedziału 0–90 dni. To ustawienie nie określa momentu instalowania lub nieinstalowania aktualizacji. 

  - **Opóźnij widoczność aktualizacji oprogramowania**: Wprowadź wartość z zakresu od 0 do 90 dni. Po upływie czasu opóźnienia użytkownicy otrzymują powiadomienie o aktualizacji do najnowszej wersji systemu operacyjnego dostępnej w momencie wyzwolenia opóźnienia.

    Na przykład jeśli wersja systemu iOS 12.a została udostępniona **1 stycznia**, a ustawienie **Opóźnij widoczność** ma wartość **5 dni**, wersja systemu iOS 12.a nie będzie początkowo widoczna na urządzeniach użytkowników końcowych jako dostępna aktualizacja. Będzie ona dostępna do instalacji przez użytkowników końcowych **szóstego dnia** po publikacji.

    To ustawienie ma zastosowanie do:  
    - System iOS 11.3 i nowsze

## <a name="password"></a>Hasło

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Hasło**: Pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom uzyskiwanie dostępu do urządzenia bez wprowadzania hasła.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

> [!IMPORTANT]
> Jeśli skonfigurujesz dowolne ustawienie hasła na urządzeniach zarejestrowanych przez użytkownika, ustawienia w obszarze **Proste hasła** są automatycznie ustawiane na wartość **Blokuj** i jest wymuszany 6-cyfrowy numer PIN.
>
> Można na przykład skonfigurować ustawienie **Wygaśnięcie hasła** i wypchnąć te zasady do urządzeń zarejestrowanych przez użytkownika. Na urządzeniach występują następujące zdarzenia:
>
> - Ustawienie **Wygaśnięcie hasła** jest ignorowane.
> - Proste hasła, takie jak `1111` lub `1234`, nie są dozwolone.
> - 6-cyfrowy numer PIN jest wymuszany.

- **Proste hasła**: wybierz pozycję **Blokuj**, aby wymagać bardziej złożonych haseł. Pozycja **Nieskonfigurowane** zezwala na proste hasła, takie jak `0000` i `1234`.

- **Wymagany typ hasła**: wybierz typ hasła, którego wymaga organizacja. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Numeryczne**
  - **Alfanumeryczne**
- **Liczba znaków innych niż alfanumeryczne w haśle**: wprowadź liczbę znaków symboli, takich jak `#` lub `@`, którą musi zawierać hasło.

- **Minimalna długość hasła**: Podaj minimalną długość hasła, które musi wprowadzić użytkownik (od 4 do 14 znaków). Na urządzeniach zarejestrowanych przez użytkownika wprowadź długość od 4 do 6 znaków.
  
  > [!NOTE]
  > W przypadku urządzeń, które są zarejestrowane przez użytkownika, użytkownicy mogą ustawić numer PIN większy niż 6 cyfr. Ale na urządzeniu nie ma więcej niż 6 cyfr. Na przykład administrator ustawia minimalną długość do `8`. Na urządzeniach zarejestrowanych przez użytkownika użytkownicy są zobowiązani tylko do ustawienia 6-cyfrowy numer PIN. Usługa Intune nie wymusza numeru PIN większego niż 6 cyfr na urządzeniach zarejestrowanych przez użytkownika.

- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: Wprowadź liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem urządzenia (od 4 do 11).
  
  System iOS ma wbudowane zabezpieczenia, które mogą mieć wpływ na to ustawienie. Na przykład system iOS może opóźnić wyzwolenie zasad w zależności od liczby niepowodzeń logowania. Może również rozważyć wielokrotne wprowadzenie tego samego kodu dostępu jako jednej próby. Przewodnik po zabezpieczeniach [systemu iOS firmy Apple](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) (otwiera witrynę sieci Web firmy Apple), jest dobrym zasobem i zawiera bardziej szczegółowe informacje dotyczące kodów dostępu.
  
- **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**<sup>1</sup>: podaj, jak długo urządzenie pozostanie bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło. Jeśli wprowadzony czas jest dłuższy niż aktualnie ustawiony na urządzeniu, urządzenie ignoruje wprowadzony przez Ciebie czas. Obsługiwane na urządzeniach z systemem iOS 8.0 i nowszym.

- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**<sup>1</sup>: wprowadź maksymalną dopuszczalną liczbę minut braku aktywności przed automatycznym zablokowaniem ekranu.

  **Opcje systemu iOS**:  

  - **Nie skonfigurowano** (wartość domyślna): usługa Intune nie dotyka tego ustawienia.
  - **Natychmiast**: blokady ekranu po 30 sekundach braku aktywności.
  - **1**: blokady ekranu po 1 minucie braku aktywności.
  - **2**: blokady ekranu po 2 minutach braku aktywności.
  - **3**: blokady ekranu po 3 minutach braku aktywności.
  - **4**: blokady ekranu po 4 minutach braku aktywności.
  - **5**: blokady ekranu po 5 minutach braku aktywności.
    
  **opcje iPadOS**:  

  - **Nie skonfigurowano** (wartość domyślna): usługa Intune nie dotyka tego ustawienia.
  - **Natychmiast**: blokady ekranu po 2 minutach braku aktywności.
  - **2**: blokady ekranu po 2 minutach braku aktywności.
  - **5**: blokady ekranu po 5 minutach braku aktywności.
  - **10**: blokady ekranu po 10 minutach braku aktywności.
  - **15**: blokady ekranu po 15 minutach braku aktywności.

  Jeśli wartość nie ma zastosowania do systemu iOS lub iPadOS, firma Apple używa najbliższej *wartości najniższej*. Jeśli na przykład wprowadzisz `4` minut, iPadOS urządzenia używają `2` minut. Jeśli wprowadzisz `10` minut, urządzenia z systemem iOS używają `5` minut. Jest to ograniczenie firmy Apple.
  
  > [!NOTE]
  > Interfejs użytkownika usługi Intune dla tego ustawienia nie oddziela obsługiwanych wartości systemu iOS i iPadOS. Interfejs użytkownika może zostać zaktualizowany w przyszłej wersji.

- **Wygaśnięcie hasła (dni)** : wprowadź liczbę dni, po której należy zmienić hasło urządzenia.
- **Zapobiegaj ponownemu używaniu poprzednich haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła.
- **Identyfikator dotyku i identyfikator funkcji Odblokuj**: wybierz pozycję **Blokuj**, aby zapobiec użyciu odcisku palca lub kroju ekranu do odblokowania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu tych metod.

  Zablokowanie tego ustawienia zapobiega także użyciu uwierzytelniania FaceID w celu odblokowania urządzenia.

  Identyfikator kroju dotyczy:  
  - System iOS 11.0 i nowsze

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Modyfikowanie kodu dostępu**: wybierz pozycję **Blokuj**, aby uniemożliwić zmianę, dodanie lub usunięcie kodu dostępu. Po zablokowaniu tej funkcji zmiany ograniczeń kodu dostępu są ignorowane na urządzeniach nadzorowanych. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia dodawanie, zmienianie lub usuwanie kodów dostępu.

  - **Zmiana identyfikatora dotyku i identyfikatora kroju**: **bloku** uniemożliwia użytkownikowi zmianę, dodanie lub usunięcie odcisków palców funkcji touchid oraz identyfikatora ekranu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi aktualizowanie odcisków palców funkcji TouchID lub danych funkcji Face ID na urządzeniu.

    Zablokowanie tego ustawienia powoduje również zatrzymanie zmiany, dodania lub usunięcia uwierzytelniania FaceID przez użytkownika.

    Identyfikator kroju dotyczy:  
    - System iOS 11.0 i nowsze

- **Blokuj automatyczne wypełnianie haseł**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie funkcji automatycznego wypełniania haseł w systemie iOS. Wybranie opcji **Blokuj** ma również następujące skutki:

  - Użytkownicy nie są monitowani o użycie zapisanego hasła w przeglądarce Safari ani innych aplikacjach.
  - Automatyczne silne hasła są wyłączone i silne hasła nie są zalecane dla użytkowników.

  Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te funkcje.

- **Blokuj zbliżeniowe żądania haseł**: wybierz pozycję **Blokuj**, aby urządzenie użytkownika nie żądało haseł od urządzeń znajdujących się w pobliżu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te żądania haseł.
- **Blokuj udostępnianie haseł**: pozycja **Blokuj** uniemożliwia udostępnianie haseł między urządzeniami przy użyciu funkcji AirDrop. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia udostępnianie haseł.
- **Wymagaj uwierzytelniania za pomocą funkcji Touch ID lub Face ID przy automatycznym wypełnianiu haseł lub informacji o kartach kredytowych**: Jeśli jest ustawiona opcja **Wymagaj**, użytkownicy będą musieli uwierzytelnić się za pomocą funkcji TouchID lub FaceID, aby w przeglądarce Safari lub innych aplikacjach mogły zostać automatycznie wypełnione hasła lub informacje o kartach kredytowych. Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom samodzielne decydowanie o tej funkcji w ustawieniach urządzenia.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze
  
<sup>1</sup>W przypadku skonfigurowania ustawień **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** i **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** są one stosowane jedno po drugim. Na przykład jeśli wartość obu ustawień jest ustawiona na **5** minut, ekran wyłącza się automatycznie po pięciu minutach, a urządzenie jest blokowane po kolejnych pięciu minutach. Jednak jeśli użytkownik wyłączy ekran ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie jeśli użytkownik wyłączy ekran, po pięciu minutach urządzenie zostanie zablokowane.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Dostęp do centrum sterowania, gdy urządzenie jest zablokowane**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikom na dostęp do aplikacji Centrum sterowania, gdy urządzenie jest zablokowane.
- **Powiadomienia, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia dostęp do powiadomień, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na dostęp do powiadomień bez odblokowywania urządzenia.
- **Widok Dzisiaj, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia użytkownikowi dostęp do widoku Dzisiaj, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi wyświetlanie widoku Dzisiaj, gdy urządzenie jest zablokowane.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Powiadomienia aplikacji Portfel, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane.

## <a name="app-store-doc-viewing-gaming"></a>Sklep App Store, wyświetlanie dokumentów, granie

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych**: Pozycja **Blokuj** uniemożliwia wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na wyświetlanie dokumentów firmowych w dowolnej aplikacji. Na przykład chcesz uniemożliwić użytkownikom zapisywanie plików z aplikacji OneDrive w aplikacji Dropbox. Skonfiguruj to ustawienie jako **Blokuj**. Jeśli urządzenie otrzymało zasady (na przykład po ponownym uruchomieniu), nie ma już możliwości zapisywania.


  > [!NOTE]
  > Po zablokowaniu tego ustawienia są również blokowane klawiatury innych firm zainstalowane ze sklepu App Store.

  - **Zezwalaj niezarządzanym aplikacjom na odczytywanie z zarządzanych kont kontaktów**: gdy ustawienie **Zezwalaj na używanie**, niezarządzanych aplikacji, takich jak wbudowana aplikacja dla systemu iOS, może odczytywać i uzyskiwać dostęp do informacji kontaktowych z zarządzanych aplikacji, w tym aplikacji mobilnej Outlook. Ustawienie opcji **Nieskonfigurowane** (wartość domyślna) zapobiega odczytywaniu informacji z wbudowanej aplikacji Kontakty na urządzeniu oraz uniemożliwia usuwanie duplikatów.  
  
    To ustawienie umożliwia lub uniemożliwia odczytywanie informacji kontaktowych. Nie kontroluje synchronizowania kontaktów między aplikacjami.
  
    Aby użyć tego ustawienia, skonfiguruj ustawienie **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych** na wartość **Blokuj**.

  Aby uzyskać więcej informacji na temat tych dwóch ustawień i ich wpływu na synchronizację eksportu kontaktów z programu Outlook dla systemu iOS, zobacz [wskazówki dotyczące obsługi: Użyj niestandardowych ustawień profilu usługi Intune przy użyciu aplikacji natywnych kontaktów systemu iOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453).

- **Traktuj usługę AirDrop jako niezarządzane miejsce docelowe**: pozycja **Wymagaj** wymusza traktowanie usługi AirDrop jako niezarządzanego miejsca docelowego upuszczania. Uniemożliwia to aplikacjom zarządzanym wysyłanie danych przy użyciu usługi AirDrop. 
- **Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych**: pozycja **Blokuj** uniemożliwia wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.

  Ustawienie **bloku** uniemożliwia również synchronizację z synchronizacją eksportu w programie Outlook dla systemu iOS. Aby uzyskać więcej informacji, zobacz temat [support Tip: Włączanie synchronizacji kontaktów z programem Outlook iOS przy użyciu kontrolek MDM iOS12](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Wymagaj hasła sklepu iTunes dla wszystkich**zakupów: **wymaga, aby** użytkownikowi wprowadzić hasło identyfikatora Apple ID dla każdego zakupu w aplikacji lub ITunes. **Nieskonfigurowane** (domyślnie) umożliwia zakupy bez monitowania o podanie hasła za każdym razem.
- **Zakupy w aplikacji**: wybierz pozycję **Blokuj**, aby uniemożliwić dokonywanie zakupów w aplikacji ze sklepu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na zakupy w sklepie w uruchomionej aplikacji.
- **Pobieranie ze sklepu iBook zawartości oznaczonej jako „Erotyka”** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom pobieranie ze sklepu iBook multimediów oznaczonych jako erotyka. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikom na pobieranie książek z kategorii „Erotyka”.
- **Zezwalaj zarządzanym aplikacjom na zapisywanie kontaktów na niezarządzanych kontach kontaktów**: po ustawieniu opcji **Zezwalaj** użytkownicy mogą dodawać lub synchronizować informacje kontaktowe dowolnej osoby w programie Outlook, w tym kontakty biznesowe i firmowe, przy użyciu wbudowanej aplikacji Kontakty na urządzeniu. Jeśli ustawienie **nie zostało skonfigurowane** (domyślnie), aplikacje zarządzane nie mogą zapisywać ani synchronizować informacji kontaktowych z wbudowaną aplikacją kontaktów systemu iOS na urządzeniu.
  
  Aby użyć tego ustawienia, skonfiguruj ustawienie **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych** na wartość **Blokuj**.

- **Region klasyfikacji**: wybierz region klasyfikacji, którego chcesz użyć w przypadku dozwolonych plików do pobrania. Następnie wybierz dozwoloną klasyfikację dla kategorii **Filmy**, **Programy TV** i **Aplikacje**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Sklep z aplikacjami**: pozycja **Blokuj** uniemożliwia dostęp do sklepu z aplikacjami na urządzeniach nadzorowanych. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

  - **Instalowanie aplikacji ze sklepu App Store**: wybierz pozycję **Blokuj**, aby zablokować sklep z aplikacjami na ekranie głównym urządzenia. Użytkownicy końcowi nadal mogą instalować aplikacje przy użyciu programu iTunes lub Apple Configurator. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala na korzystanie ze sklepu z aplikacjami na ekranie głównym.
  - **Automatyczne pobieranie aplikacji**: wybierz pozycję **Blokuj**, aby uniemożliwić automatyczne pobieranie aplikacji zakupionych na innych urządzeniach. Nie wpływa to na aktualizacje istniejących aplikacji. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia pobieranie aplikacji zakupionych na innych urządzeniach z systemem iOS na dane urządzenie.

- **Jawna zawartość programu iTunes — muzyka, podcasty lub wiadomości**: wybierz pozycję **Blokuj**, aby uniemożliwić ujawnianie zawartości programu iTunes: muzyki, podkastów lub wiadomości. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych. System iOS 13 i nowsze mogą wymagać tylko nadzorowanych urządzeń. 

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Dodawanie znajomych do usługi Game Center**: pozycja **Blokuj** uniemożliwia użytkownikom dodawanie znajomych do usługi Game Center. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi dodawanie znajomych do usługi Game Center.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Game Center**: pozycja **Blokuj** uniemożliwia korzystanie z aplikacji Game Center. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Game Center na urządzeniu.
- **Gry dla wielu graczy (tylko nadzorowany)** : wybierz pozycję **Blokuj**, aby uniemożliwić korzystanie z gier dla wielu graczy. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na gry dla wielu graczy na urządzeniu.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Dostęp do dysku sieciowego w aplikacji plików**: przy użyciu protokołu SMB (Server Message Block), urządzenia mogą uzyskać dostęp do plików lub innych zasobów na serwerze sieciowym. **Wartość Wyłącz** uniemożliwia dostęp do plików na sieciowym dysku SMB. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.

  Ta funkcja ma zastosowanie do:  
  - iOS i iPadOS 13,0 i nowsze

## <a name="built-in-apps"></a>Aplikacje wbudowane

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Siri**: pozycja **Blokuj** uniemożliwia dostęp do programu Siri. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia korzystanie z asystenta głosowego Siri na urządzeniu.
  - **Program Siri, gdy urządzenie jest zablokowane**: wybierz pozycję **Blokuj** aby uniemożliwić dostęp do programu Siri, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia korzystanie z asystenta głosowego Siri na zablokowanym urządzeniu.

- **Ostrzeżenia o oszustwach w przeglądarce Safari**: pozycja **Wymagaj** wymusza pokazywanie ostrzeżeń o oszustwie w przeglądarce internetowej na urządzeniu. **Nie skonfigurowano** (ustawienie domyślne) — wyłącza tę funkcję.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Wyniki z sieci Internet w wyszukiwaniach funkcji Spotlight**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.

- **Pliki cookie w przeglądarce Safari**: wybierz sposób obsługi plików cookie na urządzeniu. Dostępne opcje:
  - Zezwalaj
  - Blokuj wszystkie pliki cookie
  - Zezwalaj na pliki cookie z odwiedzonych witryn internetowych
  - Zezwalaj na pliki cookie z aktualnej witryny internetowej

- **Obsługa języka JavaScript w przeglądarce Safari**: pozycja **Blokuj** uniemożliwia uruchamianie skryptów języka Java w przeglądarce na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia korzystanie z Cortany.

- **Okna wyskakujące w przeglądarce Safari**: pozycja **Blokuj** umożliwia blokowanie wyskakujących okienek w przeglądarce internetowej. Pozycja **Nieskonfigurowane** umożliwia blokowanie wyskakujących okienek.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aparatu urządzenia.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

  - **FaceTime**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji FaceTime. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aplikacji FaceTime na urządzeniu.

    Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Filtr przekleństw funkcji Siri**: pozycja **Wymagaj** uniemożliwia dyktowanie lub wypowiadanie wulgaryzmów przez Siri.

  Aby użyć tego ustawienia, należy ustawić ustawienie **Siri**, aby **bloku**.

- **Używaj funkcji Siri do wykonywania zapytań o wygenerowaną przez użytkowników zawartość z Internetu**: pozycja **Blokuj** uniemożliwia programowi Siri dostęp do witryn internetowych w celu udzielania odpowiedzi na pytania. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala programowi Siri na dostęp do zawartości wygenerowanej przez użytkowników z Internetu.

  Aby użyć tego ustawienia, należy ustawić ustawienie **Siri**, aby **bloku**.

- **Apple News**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji Apple News na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple News.
- **Sklep iBooks**: pozycja **Blokuj** uniemożliwia dostęp do sklepu iBooks. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala użytkownikom na przeglądanie i kupowanie książek w sklepie iBooks.
- **Aplikacja messages na urządzeniu**: **Block** uniemożliwia użytkownikom korzystanie z aplikacji messages for iMessage. Jeśli urządzenie obsługuje wiadomości SMS, użytkownik może nadal wysyłać i odbierać wiadomości tekstowe przy użyciu programu SMS. **Nie skonfigurowano** (domyślnie) umożliwia korzystanie z aplikacji messages do wysyłania i odczytywania wiadomości za pośrednictwem Internetu.
- **Podcasty**: pozycja **Blokuj** uniemożliwia użytkownikom używanie aplikacji Podcasty. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Podcasty.
- **Usługa Music**: pozycja **Blokuj** przywraca aplikację do obsługi muzyki do trybu klasycznego i wyłącza usługę Music. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple Music.
- **Usługa iTunes Radio**: pozycja **Blokuj** uniemożliwia użytkownikom korzystanie z aplikacji iTunes Radio. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji iTunes Radio.
- **sklepu iTunes**: nie **skonfigurowany** (domyślnie) zezwala na dostęp do programu iTunes na urządzeniach. **Blokuj** uniemożliwia użytkownikom korzystanie z programu iTunes na urządzeniu. 

  Ta funkcja ma zastosowanie do:  
  - System iOS 4.0 i nowsze

- **Znajdź mój iPhone**: nie **skonfigurowany** (domyślnie) umożliwia korzystanie z funkcji Znajdź moją aplikację w celu uzyskania przybliżonej lokalizacji urządzenia. **Blok** zapobiega tej funkcji w aplikacji Znajdź moją aplikację. 

  Ta funkcja ma zastosowanie do:  
  - iOS 13,0 i iPadOS 13,0 i nowsze

- **Znajdź moich znajomych**: nie **skonfigurowany** (domyślnie) umożliwia korzystanie z funkcji Znajdź moją aplikację w celu znalezienia rodziny i znajomych z urządzenia firmy Apple lub iCloud.com. **Blok** zapobiega tej funkcji w aplikacji Znajdź moją aplikację.

  Ta funkcja ma zastosowanie do:  
  - iOS 13,0 i iPadOS 13,0 i nowsze

- **Zmiany ustawień aplikacji Znajdź moich znajomych**: pozycja **Blokuj** uniemożliwia zmiany ustawień aplikacji Znajdź moich znajomych. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi zmienianie ustawień aplikacji Znajdź moich znajomych.

- **Wyniki z sieci Internet w wyszukiwaniach funkcji Spotlight**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.

- **Blokuj usuwanie aplikacji systemowych z urządzenia**: wybranie pozycji **Blokuj** wyłącza możliwość usuwania aplikacji systemowych z urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala użytkownikom na usuwanie aplikacji systemowych.

- **Safari**: pozycja **Blokuj** uniemożliwia korzystanie z przeglądarki Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala użytkownikom na używanie przeglądarki Safari.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Autowypełnianie w przeglądarce Safari**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania w przeglądarce Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom zmianę ustawień automatycznego uzupełniania w przeglądarce internetowej.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Typ listy aplikacji z ograniczeniami**: Utwórz listę aplikacji, których użytkownicy nie mogą instalować ani używać. Dostępne opcje:

  - **Nie skonfigurowano** (wartość domyślna): nie ma żadnych ograniczeń z usługi Intune. Użytkownicy mają dostęp do przypisywanych aplikacji oraz wbudowanych aplikacji.
  - **Aplikacje zabronione**: Aplikacje niezarządzane przez usługę Intune, które nie powinny być instalowane na urządzeniu. Użytkownicy nie mogą instalować zabronionej aplikacji. Jednak jeśli użytkownik zainstaluje aplikację z tej listy, zostanie ona zgłoszona w usłudze Intune.
  - **Aplikacje zatwierdzone**: Aplikacje, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Użytkownicy nadal będą mogli zainstalować aplikację, której nie ma na liście dozwolonych. Ale jeśli tak, jest on raportowany w usłudze Intune.

Aby dodać aplikacje do tych list, możesz:

- **Dodać** adres URL sklepu z aplikacjami iTunes dla wybranej aplikacji. Na przykład w celu dodania aplikacji Foldery robocze firmy Microsoft wprowadź `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` lub `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`.

  Aby znaleźć adres URL aplikacji, otwórz sklep iTunes App Store i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop` lub `Microsoft Word`. Wybierz aplikację i skopiuj adres URL.

  Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć zadania **Kopiuj link**, aby uzyskać adres URL aplikacji.

- **Zaimportować** plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app url>, <app name>, <app publisher>`. Możesz również **wyeksportować** istniejącą listę, która zawiera listę aplikacji z ograniczeniami w tym samym formacie.

> [!IMPORTANT]
> Profile urządzeń, które używają ustawień aplikacji z ograniczeniami, należy przypisać do grup użytkowników.

## <a name="show-or-hide-apps"></a>Pokaż lub ukryj aplikacje

Dotyczy urządzeń z systemem iOS w wersji 9,3 lub nowszej.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Typ listy aplikacji**: Utwórz listę aplikacji do pokazania lub ukrycia. Możesz pokazać lub ukryć wbudowane aplikacje i aplikacje biznesowe. Witryna sieci Web firmy Apple zawiera listę [wbudowane aplikacje firmy Apple](https://support.apple.com/HT208094). Dostępne opcje:

  - **Ukryte aplikacje**: wprowadź listę aplikacji ukrywanych przed użytkownikami. Użytkownicy nie mogą wyświetlać ani otwierać tych aplikacji.
  
    Firma Apple uniemożliwia ukrywanie niektórych natywnych aplikacji. Nie można na przykład ukryć **ustawień** lub **aplikacji** dla portfela na urządzeniu. [Usuń wbudowane aplikacje firmy Apple](https://support.apple.com/HT208094) wyświetla listę aplikacji, które mogą być ukryte.
  
  - **Widoczne aplikacje**: wprowadź listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

- **URL aplikacji**: wprowadź adres URL aplikacji ze sklepu, który ma być wyświetlany lub ukryty. Przykład:

  - Aby dodać aplikację Foldery robocze firmy Microsoft, wprowadź `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` lub `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`. 

  - Aby dodać aplikację Microsoft Word, wprowadź `https://itunes.apple.com/de/app/microsoft-word/id586447913` lub `https://apps.apple.com/de/app/microsoft-word/id586447913`.

  Aby znaleźć adres URL aplikacji, otwórz sklep iTunes App Store i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop` lub `Microsoft Word`. Wybierz aplikację i skopiuj adres URL.

  Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć zadania **Kopiuj link**, aby uzyskać adres URL aplikacji.
  
  Aby uzyskać więcej informacji na temat lokalizowania identyfikatora pakietu, zobacz [jak znaleźć identyfikator pakietu dla aplikacji systemu iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).

- **Identyfikator pakietu aplikacji**: Wprowadź [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) żądanej aplikacji. Możesz pokazać lub ukryć wbudowane aplikacje i aplikacje biznesowe. Witryna sieci Web firmy Apple zawiera listę [wbudowane aplikacje firmy Apple](https://support.apple.com/HT208094).
- **Nazwa aplikacji**: Wprowadź nazwę żądanej aplikacji. Możesz pokazać lub ukryć wbudowane aplikacje i aplikacje biznesowe. Witryna sieci Web firmy Apple zawiera listę [wbudowane aplikacje firmy Apple](https://support.apple.com/HT208094).
- **Wydawca**: Podaj wydawcę odpowiedniej aplikacji.

Aby dodać aplikacje, możesz wykonać następujące czynności:

- **Dodaj**: Wybierz, aby utworzyć listę aplikacji.
- **Zaimportować** plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app url>, <app name>, <app publisher>`. Lub **Eksportuj**, aby utworzyć listę dodanych aplikacji z ograniczeniami w tym samym formacie.

## <a name="wireless"></a>Sieć bezprzewodowa

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

Uwaga wymagana w przypadku roamingu danych (Porada lub ważna Uwaga, aby pomóc w nieporozumieniu klienta): to ustawienie nie będzie widoczne w profilu zarządzania urządzenia wskazanego. Oznacza to, że to ustawienie jest traktowane jako akcja urządzenia zdalnego, a przy każdym zmianie stanu roamingu danych na urządzeniu zostanie ono zablokowane ponownie przez usługę Intune. Mimo że nie znajduje się on w profilu zarządzania, działa, jeśli jest wyświetlany jako powodzenie z raportowania w konsoli administracyjnej. 
- **Roaming danych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming danych w sieci komórkowej. Opcja **Nieskonfigurowane** (domyślna) zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.

  > [!IMPORTANT]
  > To ustawienie jest traktowane jako akcja urządzenia zdalnego. To ustawienie nie jest wyświetlane w profilu zarządzania na urządzeniu. Za każdym razem, gdy stan roamingu danych zostanie zmieniony na urządzeniu, **roaming danych** jest blokowany przez usługę Intune. Jeśli w usłudze Intune stan raportowania zawiera sukces, należy sprawdzić, czy działa, nawet jeśli ustawienie nie jest wyświetlane w profilu zarządzania na urządzeniu.

- **Globalne pobieranie w tle podczas roamingu**: pozycja **Blokuj** uniemożliwia używanie funkcji globalnego pobierania w tle podczas roamingu w sieci komórkowej. Opcja **Nieskonfigurowane** (domyślna) zezwala urządzeniu na pobieranie danych, np. wiadomości e-mail, podczas roamingu w sieci komórkowej.
- **Wybieranie głosowe**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom korzystanie z funkcji wybierania głosowego na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia wybieranie głosowe na urządzeniu.
- **Roaming połączeń głosowych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming połączeń danych w sieci komórkowej. Opcja **Nieskonfigurowane** (domyślna) zezwala na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.
- **Osobisty hotspot**: Opcja **Blokuj** wyłącza osobisty hotspot na urządzeniu użytkownika przy każdej synchronizacji urządzenia. To ustawienie może być niezgodne w przypadku niektórych operatorów. Opcja **Nieskonfigurowane** (ustawienie domyślne) zachowuje domyślną konfigurację osobistego hotspotu ustawioną przez użytkownika.

  > [!IMPORTANT]
  > To ustawienie jest traktowane jako akcja urządzenia zdalnego. To ustawienie nie jest wyświetlane w profilu zarządzania na urządzeniu. Za każdym razem, gdy osobisty stan hotspotu zmieni się na urządzeniu, **osobisty hotspot** jest blokowany przez usługę Intune. Jeśli w usłudze Intune stan raportowania zawiera sukces, należy sprawdzić, czy działa, nawet jeśli ustawienie nie jest wyświetlane w profilu zarządzania na urządzeniu.

- **Zasady użycia danych komórkowych (tylko aplikacje zarządzane)** : zdefiniuj typy danych, których aplikacje zarządzane mogą używać podczas pracy w sieciach komórkowych. Dostępne opcje:
  - **Zablokuj użycie danych komórkowych**: zablokuj użycie danych komórkowych dla **wszystkich zarządzanych aplikacji** lub **wybierz określone aplikacje**.
  - **Zablokuj użycie danych komórkowych podczas roamingu**: zablokuj użycie danych komórkowych podczas roamingu dla **wszystkich zarządzanych aplikacji** lub **wybierz określone aplikacje**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Zmiany w ustawieniach wykorzystania danych komórkowych przez aplikację**: wybierz pozycję **Blokuj**, aby uniemożliwić zmiany ustawień użycia danych komórkowych aplikacji. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi kontrolowanie, które aplikacje mogą korzystać z danych komórkowych.
- **Zmiany w ustawieniach planu komórkowego**: Pozycja **Blokuj** uniemożliwia użytkownikom zmianę jakichkolwiek ustawień planu komórkowego. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom wprowadzanie zmian.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze

- **Modyfikacja użytkownika osobistego hotspotu**: po ustawieniu na **bloku**użytkownik nie będzie mógł zmienić ustawienia osobistego hotspotu. **Nie skonfigurowano** (domyślnie) umożliwia użytkownikom końcowym Włączanie lub wyłączanie osobistego hotspotu.

  W przypadku zablokowania tego ustawienia i zablokowania **osobistego ustawienia** hotspotu prywatny punkt hotspotu jest wyłączony.

  Ta funkcja ma zastosowanie do:  
  - System iOS 12.2 i nowsze

- **Dołączaj do sieci Wi-Fi wyłącznie za pomocą profilów konfiguracji**: pozycja **Wymagaj** wymusza użycie na urządzeniu tylko sieci Wi-Fi, które zostały skonfigurowane przy użyciu profilu konfiguracji usługi Intune. Opcja **Nieskonfigurowane** (domyślna) zezwala urządzeniu na korzystanie z innych sieci Wi-Fi.
- **Sieć Wi-Fi jest zawsze włączona**: gdy ustawienie **Wymagaj**, Sieć Wi-Fi zostanie włączona w aplikacji ustawienia. Nie można jej wyłączyć w ustawieniach ani w centrum sterowania, nawet gdy urządzenie jest w trybie samolotowym. **Nie skonfigurowano** (domyślnie) umożliwia użytkownikowi kontrolowanie włączania lub wyłączania sieci Wi-Fi.

  Skonfigurowanie tego ustawienia nie uniemożliwia użytkownikom wyboru sieci Wi-Fi.

  Ta funkcja ma zastosowanie do:  
  - iOS i iPadOS 13,0 i nowsze

## <a name="connected-devices"></a>Połączone urządzenia

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Wykrywanie nadgarstka przez sparowane urządzenie Apple Watch**: pozycja **Wymagaj** wymusza używanie funkcji wykrywania nadgarstka na sparowanym zegarku Apple Watch. Jeśli ta opcja jest wymagana, zegarek Apple Watch nie będzie wyświetlać powiadomień, kiedy nie będzie znajdować się na nadgarstku użytkownika. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Wymagaj hasła parowania dla wychodzących żądań AirPlay**: pozycja **Wymagaj** umożliwia wymaganie hasła parowania, gdy użytkownik używa funkcji AirPlay do strumieniowego przesyłania zawartości do innych urządzeń firmy Apple. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi przesyłanie strumieniowe zawartości przy użyciu funkcji AirPlay bez wprowadzania hasła.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **AirDrop**: pozycja **Blokuj** uniemożliwia używanie funkcji AirDrop na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
- **Parowanie z urządzeniem Apple Watch (tylko nadzorowany)** : pozycja **Blokuj** uniemożliwia parowanie urządzenia z urządzeniem Apple Watch. Opcja **Nieskonfigurowane** (domyślna) zezwala na parowanie urządzenia z zegarkiem Apple Watch.
- **Modyfikowanie ustawień funkcji Bluetooth**: pozycja **Blokuj** uniemożliwia użytkownikowi końcowemu zmianę ustawień protokołu Bluetooth na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi zmianę tych ustawień.
- **Parowanie hosta na potrzeby kontrolowania urządzeń, z którymi można parować urządzenie z systemem iOS**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) zezwala na parowanie hostów w celu umożliwienia administratorowi kontrolowania tego, z którymi urządzeniami może być sparowane urządzenie z systemem iOS. Pozycja **Blokuj** uniemożliwia parowanie hosta.
- **Blokuj funkcję AirPrint**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie funkcji AirPrint na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) zezwala użytkownikowi na korzystanie z funkcji AirPrint.
  - **Blokuj przechowywanie poświadczeń funkcji AirPrint w pęku kluczy**: pozycja **Blokuj** uniemożliwia korzystanie z magazynu pęku kluczy do przechowywania nazwy użytkownika i hasła na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia przechowywanie nazwy użytkownika i hasła funkcji AirPrint w aplikacji pęku kluczy.
  - **Wymagaj zaufanego certyfikatu protokołu TLS dla funkcji AirPrint**: pozycja **Wymagaj** wymusza użycie zaufanych certyfikatów na potrzeby komunikacji dotyczącej drukowania przy użyciu protokołu TLS.
  - **Blokuj odnajdywanie drukarek AirPrint za pomocą protokołu iBeacon**: pozycja **Blokuj** uniemożliwia złośliwym sygnałom nawigacyjnym funkcji AirPrint Bluetooth wyłudzanie informacji dotyczących ruchu sieciowego. Opcja **Nieskonfigurowane** (domyślna) zezwala na ogłaszanie drukarek AirPrint na urządzeniu.
- **Blokuj konfigurowanie nowych urządzeń w pobliżu**: Pozycja **Blokuj** wyłącza monitowanie o konfigurację nowych urządzeń znajdujących się w pobliżu. Opcja **Nieskonfigurowane** (ustawienie domyślne) zezwala na monitowanie użytkowników o połączenie z innymi urządzeniami firmy Apple znajdującymi się w pobliżu.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze

- **Dostęp do plików na dysku USB**: urządzenia mogą łączyć i otwierać pliki na dysku USB. **Wartość Wyłącz** uniemożliwia dostęp urządzenia do dysku USB w aplikacji pliki, gdy port USB jest połączony z urządzeniem. Wyłączenie tej funkcji blokuje również użytkownikom końcowym przesyłanie plików na dysk USB podłączony do urządzenia iPad. **Nie skonfigurowano** (domyślnie) umożliwia dostęp do dysku USB w aplikacji pliki.

  Ta funkcja ma zastosowanie do:  
  - iOS i iPadOS 13,0 i nowsze

## <a name="keyboard-and-dictionary"></a>Klawiatura i słownik

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Wyszukiwanie definicji słów**: pozycja **Blokuj** uniemożliwia użytkownikom wyróżnianie wyrazu, a następnie wyszukiwanie jego definicji na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do funkcji wyszukiwania definicji.
- **Klawiatury predykcyjne**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia korzystanie z klawiatur predykcyjnych sugerujących wyrazy, które użytkownik może chcieć wpisać. Pozycja **Blokuj** uniemożliwia użycie tej funkcji.
- **Autokorekta**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) pozwala na automatyczne poprawianie błędnie napisanych wyrazów przez urządzenie. Pozycja **Blokuj** uniemożliwia korzystanie z autokorekty.
- **Funkcja sprawdzania pisowni klawiatury (tylko tryb nadzorowany)** : pozycja **Nieskonfigurowane** umożliwia używanie sprawdzania pisowni na urządzeniu. Pozycja **Blokuj** pozwala na sprawdzanie pisowni.
- **Skróty klawiaturowe (tylko tryb nadzorowany)** : pozycja **Nieskonfigurowane** umożliwia używanie skrótów klawiaturowych na urządzeniu. Pozycja **Blokuj** uniemożliwia użytkownikowi korzystanie ze skrótów klawiaturowych.
- **Dyktowanie**: pozycja **Blokuj** uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na korzystanie z wprowadzania tekstu przez dyktowanie.
- **QuickPath**: nie **skonfigurowany** (domyślnie) umożliwia użytkownikom korzystanie z QuickPath, co umożliwia ciągłe wprowadzanie danych na klawiaturze urządzenia. Użytkownicy mogą pisać przez szybkie przesuwanie klawiszy w celu utworzenia słów. **Blokuj** uniemożliwia użytkownikom korzystanie z QuickPath. 

  Ta funkcja ma zastosowanie do:  
  - iOS 13,0 i iPadOS 13,0 i nowsze

## <a name="cloud-and-storage"></a>Chmura i magazyn

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia dotyczą: wszystkie typy rejestracji

- **Szyfrowana kopia zapasowa**: pozycja **Wymagaj** umożliwia wymaganie szyfrowania wszystkich kopii zapasowych urządzenia.
- **Zarządzane aplikacje są synchronizowane z chmurą**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) zezwala aplikacjom zarządzanym usługi Intune na synchronizowanie danych z kontem użytkownika w usłudze iCloud. Pozycja **Blokuj** uniemożliwia taką synchronizację danych z usługą iCloud.
- **Blokuj tworzenie kopii zapasowych książek przedsiębiorstwa**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom tworzenie kopii zapasowej książek przedsiębiorstwa. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom tworzenie kopii zapasowych tych książek.
- **Blokuj synchronizację metadanych książek przedsiębiorstwa (notatki i wyróżnienia)** : pozycja **Blokuj** uniemożliwia synchronizowanie notatek i wyróżnień w książkach przedsiębiorstwa. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia synchronizowanie.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Synchronizowanie strumienia zdjęć z usługą iCloud**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom włączanie funkcji **Mój strumień zdjęć** na urządzeniu, co pozwala na synchronizowanie z usługą iCloud i udostępnianie zdjęć na wszystkich urządzeniach użytkownika. Pozycja **Blokuj** zezwala na synchronizację funkcji Strumień zdjęć w usłudze iCloud. Zablokowanie tej funkcji może spowodować utratę danych. 
- **Biblioteka zdjęć usługi iCloud**: ustaw tę opcję na pozycję **Blokuj**, aby wyłączyć możliwość używania biblioteki zdjęć usługi iCloud do przechowywania zdjęć i klipów wideo w chmurze. Wszystkie zdjęcia, które nie zostały w pełni pobrane z biblioteki zdjęć iCloud na urządzenie, są usuwane z urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie biblioteki zdjęć iCloud.
- **Udostępniony strumień zdjęć**: wybierz pozycję **Blokuj**, aby wyłączyć funkcję **Udostępnianie zdjęć w usłudze iCloud** na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia przesyłanie strumieniowe udostępnionych zdjęć.
- **przekazanie**: nie **skonfigurowany** (domyślnie) pozwala użytkownikom na uruchamianie pracy na urządzeniu z systemem iOS, a następnie kontynuować pracę uruchomioną na innym urządzeniu z systemem iOS lub macOS. Pozycja **Blokuj** uniemożliwia użycie programu Handoff.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Tworzenie kopii zapasowych w usłudze iCloud**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud. Pozycja **Blokuj** uniemożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Blokuj synchronizowanie dokumentów z usługą iCloud**: Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia synchronizowanie dokumentów i par klucz-wartość w obszarze magazynu usługi iCloud. Pozycja **Blokuj** uniemożliwia synchronizowanie dokumentów i danych w usłudze iCloud.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

- **Blokuj synchronizowanie pęku kluczy z usługą iCloud**: wybierz pozycję **Blokuj**, aby wyłączyć synchronizowanie poświadczeń przechowywanych w pęku kluczy z usługą iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom synchronizację tych poświadczeń.

  Począwszy od systemu iOS 13,0, to ustawienie wymaga nadzorowanych urządzeń.

## <a name="autonomous-single-app-mode"></a>Autonomiczny tryb pojedynczej aplikacji

Użyj tych ustawień w celu skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w autonomicznym trybie pojedynczej aplikacji. Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane. Może ono uruchamiać wyłącznie tę aplikację. Na przykład dodaj aplikację, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Nazwa aplikacji**: Wprowadź nazwę żądanej aplikacji.
- **Identyfikator pakietu aplikacji**: Wprowadź [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) żądanej aplikacji.
- **Dodaj**: Wybierz, aby utworzyć listę aplikacji.

Możesz również **zaimportować** plik CSV zawierający listę nazw aplikacji i ich identyfikatorów pakietu. Lub **wyeksportuj** istniejącą listę, która zawiera aplikacje.

## <a name="kiosk"></a>Kiosk

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Aplikacja do uruchamiania w trybie kiosku**: wybierz typ aplikacji, które chcesz uruchomić w trybie kiosku. Dostępne opcje:
  - **Nieskonfigurowane** (wartość domyślna): Ustawienia kiosku nie są stosowane. Urządzenie nie zostanie uruchomione w trybie kiosku.
  - **Aplikacja ze Sklepu**: Wprowadź adres URL aplikacji w sklepie iTunes.
  - **Zarządzana aplikacja**: Wybierz aplikację dodaną do usługi Intune.
  - **Wbudowana aplikacja**: Wprowadź [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) wbudowanej aplikacji.

- **Obsługa dotykowa z ułatwieniami**: pozycja **Wymagaj** wymusza ustawienie ułatwień dostępu Obsługa dotykowa z ułatwieniami na urządzeniu. Ta funkcja pomaga użytkownikom wykonywać na ekranie gesty, które mogą okazać się trudne. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Odwróć kolory**: pozycja **Wymagaj** wymusza użycie ułatwień dostępu Odwróć kolory, co umożliwia użytkownikom niedowidzącym zmienianie ustawień ekranu. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Dźwięk mono**: pozycja **Wymagaj** wymaga ustawienia ułatwienia dostępu Dźwięk mono na urządzeniu. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **sterowania głosem**: **wymaga** umożliwia sterowanie głosem na urządzeniu i pozwala użytkownikom w pełni kontrolować system operacyjny za pomocą poleceń Siri. **Nie skonfigurowano** wyłącza kontrolę głosu na urządzeniu.

  To ustawienie ma zastosowanie do:  
  - System iOS 13.0 i nowsze
  - System iPadOS 13.0 i nowsze
  
  > [!TIP]
  > Jeśli masz aplikacje LOB dostępne dla Twojej organizacji i nie **kontroli głosu** gotowych na dzień 0 w przypadku wersji iOS 13,0, zalecamy pozostawienie tego ustawienia jako **nie skonfigurowane**.

- **VoiceOver**: pozycja **Wymagaj** wymusza użycie na urządzeniu ustawienia ułatwień dostępu VoiceOver, aby tekst na ekranie mógł być odczytywany na głos. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Powiększenie**: pozycja **Wymagaj** wymusza użycie ustawienia Powiększenie na urządzeniu, aby umożliwić użytkownikom powiększenie obrazu wyświetlanego na ekranie za pomocą dotyku. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Automatyczne blokowanie**: **bloku** uniemożliwia automatyczne blokowanie urządzenia. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Przełącznik dzwonka**: Pozycja **Blokuj** uniemożliwia użycie przełącznika dzwonka (wyciszenie) na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Obrót ekranu**: Pozycja **Blokuj** uniemożliwia zmianę orientacji ekranu przy obrocie urządzenia. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Przycisk usypiania ekranu**: Wybierz pozycję **Blokuj**, aby wyłączyć przycisk usypiania/budzenia ekranu na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Dotyk**: pozycja **Blokuj** wyłącza ekran dotykowy na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z ekranu dotykowego.
- **Przyciski regulacji głośności**: pozycja **Zezwalaj** pozwala na użycie przycisków regulacji głośności na urządzeniu. Pozycja **Nieskonfigurowane** wyłącza przyciski regulacji głośności.
- **Wspomagająca kontrola dotykowa**: pozycja **Zezwalaj** pozwala użytkownikom na korzystanie z funkcji obsługi dotykowej z ułatwieniami. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Odwróć kontrolę kolorów**: pozycja **Zezwalaj** pozwala na zmianę ustawienia funkcji Odwróć kolory, które umożliwiają użytkownikowi dostosowanie jej do własnych potrzeb. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Mów przy wybranym tekście**: pozycja **Zezwalaj** umożliwia użycie ustawienia ułatwień dostępu Czytaj zaznaczenie na urządzeniu. Ta funkcja odczytuje tekst, który użytkownik wybierze przy użyciu głosu. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Modyfikowanie kontrolki głosowej**: **umożliwia** użytkownikom zmianę stanu kontroli głosu na ich urządzeniach. **Nie skonfigurowano** uniemożliwia użytkownikom zmianę stanu kontroli głosu na ich urządzeniach.

  To ustawienie ma zastosowanie do:  
  - System iOS 13.0 i nowsze
  - System iPadOS 13.0 i nowsze

- **Kontrola VoiceOver**: pozycja **Zezwalaj** umożliwia zmiany podkładu głosowego, aby zezwolić użytkownikom na aktualizowanie ustawień funkcji VoiceOver, takich jak szybkość odczytywania tekstu na głos. Pozycja **Nieskonfigurowane** uniemożliwia zmiany podkładu głosowego.
- **Ustawianie powiększania**: pozycja **Zezwalaj** umożliwia użytkownikowi zmienianie powiększenia. Pozycja **Nieskonfigurowane** uniemożliwia zmiany powiększenia.

> [!NOTE]
> Aby można było skonfigurować urządzenie z systemem iOS do obsługi trybu kiosku, należy najpierw użyć narzędzia Apple Configurator lub programu Apple Device Enrollment Program w przełączenia go do trybu nadzorowanego. Zapoznaj się z przewodnikiem firmy Apple dotyczącym korzystania z narzędzia Apple Configurator.
> Jeśli wprowadzona aplikacja systemu iOS zostanie zainstalowana po przypisaniu profilu, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: Rejestracja urządzenia, automatyczna rejestracja urządzeń (nadzorowane)

- **Nieoznaczone domeny poczty e-mail** > **Adres URL domeny poczty e-mail**: Dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy końcowi otrzymają wiadomość e-mail z domeny innej niż wprowadzona, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu iOS jako niezaufana.

- **Zarządzane domeny sieci Web** > **Adres URL domeny sieci Web**: dodaj do listy co najmniej jeden adres URL. Dokumenty pobierane z wprowadzonych domen są uznawane za zarządzane. To ustawienie ma zastosowanie wyłącznie do dokumentów pobieranych przy użyciu przeglądarki Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia dotyczą: automatyczne rejestrowanie urządzeń (nadzorowane)

- **Domeny automatycznego wypełniania haseł w programie Safari** > **Adres URL domeny**: Dodaj do listy co najmniej jeden adres URL. Użytkownicy mogą zapisywać wyłącznie hasła witryn sieci Web dla adresów URL znajdujących się na tej liście. To ustawienie dotyczy wyłącznie przeglądarki Safari oraz urządzeń działających w trybie nadzorowanym. Jeśli nie podasz żadnych adresów URL, użytkownicy będą mogli zapisywać hasła ze wszystkich witryn internetowych.

  To ustawienie ma zastosowanie do:  
  - System iOS 9.3 i nowsze

## <a name="settings-that-require-supervised-mode"></a>Ustawienia, które wymagają trybu nadzorowanego

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
>
> - Instalowanie aplikacji przez użytkowników końcowych
> - Usuwanie aplikacji
> - FaceTime
> - Safari
> - iTunes
> - Zawartość dla dorosłych
> - Dokumenty i dane iCloud
> - Gry dla wielu graczy
> - Dodawanie znajomych w aplikacji Game Center
> - Siri

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](../device-profile-monitor.md).

Możesz również skonfigurować ograniczenia dotyczące funkcji i ustawień urządzenia z systemem [macOS](device-restrictions-macos.md).
