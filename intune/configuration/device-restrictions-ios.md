---
title: Ustawienia urządzenia z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodawaj, konfiguruj lub twórz ustawienia na urządzeniach z systemem iOS w celu ograniczania funkcji, na przykład ustawiania wymagań dotyczących haseł, kontrolowania zablokowanego ekranu, używania wbudowanych aplikacji, dodawania ograniczonych lub zatwierdzonych aplikacji, obsługi urządzeń z funkcją Bluetooth, łączenia z chmurą na potrzeby tworzenia kopii zapasowych i magazynowania, włączania trybu kiosku, dodawania domen oraz kontrolowania sposobu, w jaki użytkownicy pracują z przeglądarką internetową Safari w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc252068d963d75bf6ade79852d6ba01bda8800b
ms.sourcegitcommit: 9b29478f815e10c46c8030abe0146d601ce0e28c
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051613"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem iOS lub iPadOS. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, zezwalać na działanie konkretnych aplikacji lub je ograniczać i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem iOS.

> [!TIP]
> Korzystają one z ustawień zarządzania urządzeniami mobilnymi firmy Apple. Aby uzyskać więcej informacji na temat tych ustawień, zobacz [Ustawienia zarządzania urządzeniami mobilnymi firmy Apple](https://support.apple.com/guide/mdm/welcome/web) (zostanie otwarta witryna internetowa firmy Apple).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji ograniczeń urządzenia](../device-restrictions-configure.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji, a niektóre z nich dotyczą wszystkich opcji rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [Rejestracja systemu iOS](../ios-enroll.md).

## <a name="general"></a>Ogólne

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Udostępnij dane użycia**: wybierz pozycję **Blokuj**, aby uniemożliwić urządzeniu wysyłanie danych diagnostycznych i danych użycia do firmy Apple. Pozycja **Nieskonfigurowane** (domyślna) umożliwia wysyłanie tych danych.

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów w urządzeniu. W systemie iOS 9.0 i nowszych blokowane jest również nagrywanie ekranu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu lub pliku wideo.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Niezaufane certyfikaty protokołu TLS**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie niezaufanych certyfikatów protokołu Transport Layer Security (TLS) na urządzeniu. Pozycja **Nieskonfigurowane** (ustawienie domyślne) pozwala na korzystanie z certyfikatów protokołu TLS.
- **Blokuj bezprzewodowe aktualizacje infrastruktury PKI**: pozycja **Blokuj** uniemożliwia użytkownikom otrzymywanie aktualizacji oprogramowania, chyba że urządzenie zostało podłączone do komputera. Pozycja **Nie skonfigurowano** (wartość domyślna) umożliwia urządzeniu otrzymywanie aktualizacji oprogramowania bez połączenia z komputerem.
- **Ograniczanie śledzenia reklam**: wybierz pozycję **Ogranicz**, aby wyłączyć identyfikator treści reklamowych urządzenia. Pozycja **Nieskonfigurowane** (ustawienie domyślne) powoduje, że identyfikator pozostaje włączony.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Modyfikowanie ustawień przesyłania diagnostyki**: Pozycja **Blokuj** uniemożliwia użytkownikowi zmianę ustawień analizy aplikacji i przesyłania danych diagnostycznych w obszarze **Diagnostyka i użycie** (ustawienia urządzenia). Pozycja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi zmianę tych ustawień urządzenia.

  Aby użyć tego ustawienia, w ustawieniu **Udostępniaj dane użycia** wybierz pozycję **Blokuj**.

  Ta funkcja ma zastosowanie do:  
  - System iOS 9.3.2 i nowsze

- **Blokuj zdalne obserwowanie ekranów przez aplikację Classroom**: wybierz opcję **Blokuj**, aby nie był możliwy zdalny podgląd ekranu urządzenia za pomocą aplikacji Classroom. Pozycja **Nieskonfigurowane** (domyślna) umożliwia aplikacji Classroom firmy Apple wyświetlanie ekranu.

  Aby użyć tego ustawienia, w ustawieniu **Przechwytywanie ekranu** wybierz pozycję **Blokuj**.

  Ta funkcja ma zastosowanie do:  
  - System iOS 9.3 i nowsze

- **Obserwacja ekranu bez monitowania za pomocą aplikacji Classroom**: w przypadku ustawienia pozycji **Zezwalaj** nauczyciele mogą dyskretnie obserwować ekrany urządzeń z systemem iOS przy użyciu aplikacji Classroom bez wiedzy uczniów. Urządzenia uczniów zarejestrowanych na zajęcia za pomocą aplikacji Classroom automatycznie udzielają uprawnień nauczycielowi na danym kursie. Pozycja **Nie skonfigurowano** (ustawienie domyślne) blokuje tę funkcję.

  Aby użyć tego ustawienia, w ustawieniu **Przechwytywanie ekranu** wybierz pozycję **Blokuj**.

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
- **Zezwalaj na akcesoria USB, gdy urządzenie jest zablokowane**: pozycja **Zezwalaj** umożliwia akcesoriom USB wymianę danych z urządzeniem, które było zablokowane przez dłużej niż godzinę. Pozycja **Nie skonfigurowano** (wartość domyślna) nie aktualizuje trybu ograniczonego USB na urządzeniu, a akcesoria USB nie mogą przesyłać danych z urządzenia zablokowanego przez ponad godzinę.
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

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Hasło**: Pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom uzyskiwanie dostępu do urządzenia bez wprowadzania hasła.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

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

- **Minimalna długość hasła**: Podaj minimalną długość hasła, które musi wprowadzić użytkownik (od 4 do 14 znaków). Na urządzeniach zarejestrowanych przez użytkownika wprowadź od 4 do 6 znaków.
  
  > [!NOTE]
  > W przypadku urządzeń zarejestrowanych przez użytkowników mogą oni ustawić numer PIN o długości większej niż 6 cyfr. Jednak urządzenie nie wymusza więcej niż 6 cyfr. Na przykład administrator ustawia minimalną długość na `8`. Na urządzeniach zarejestrowanych przez użytkowników muszą oni ustawić zaledwie 6-cyfrowy numer PIN. Usługa Intune nie wymusza numeru PIN dłuższego niż 6 cyfr na urządzeniach zarejestrowanych przez użytkowników.

- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: Wprowadź liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem urządzenia (od 4 do 11).
  
  System iOS ma wbudowane zabezpieczenia, które mogą mieć wpływ na to ustawienie. Na przykład system iOS może opóźniać wyzwalanie zasad w zależności od liczby błędów logowania. Może również uznawać wielokrotne wprowadzenie tego samego kodu dostępu za jedną próbę. Przydatnym zasobem jest [Przewodnik po zabezpieczeniach systemu iOS](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) firmy Apple (zostanie otwarta witryna internetowa firmy Apple), który zawiera bardziej szczegółowe informacje na temat kodów dostępu.
  
- **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**<sup>1</sup>: podaj, jak długo urządzenie pozostanie bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło. Jeśli wprowadzony czas jest dłuższy niż aktualnie ustawiony na urządzeniu, urządzenie ignoruje wprowadzony przez Ciebie czas. Obsługiwane na urządzeniach z systemem iOS 8.0 i nowszym.

- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**<sup>1</sup>: wprowadź maksymalną dopuszczalną liczbę minut braku aktywności przed automatycznym zablokowaniem ekranu.

  **Opcje systemu iOS**:  

  - **Nie skonfigurowano** (wartość domyślna): usługa Intune nie zmienia tego ustawienia.
  - **Natychmiast**: ekran blokuje się po upływie 30 s braku aktywności.
  - **1**: ekran blokuje się po upływie 1 min braku aktywności.
  - **2**: ekran blokuje się po upływie 2 min braku aktywności.
  - **3**: ekran blokuje się po upływie 3 min braku aktywności.
  - **4**: ekran blokuje się po upływie 4 min braku aktywności.
  - **5**: ekran blokuje się po upływie 5 min braku aktywności.
    
  **Opcje systemu iPadOS**:  

  - **Nie skonfigurowano** (wartość domyślna): usługa Intune nie zmienia tego ustawienia.
  - **Natychmiast**: ekran blokuje się po upływie 2 min braku aktywności.
  - **2**: ekran blokuje się po upływie 2 min braku aktywności.
  - **5**: ekran blokuje się po upływie 5 min braku aktywności.
  - **10**: ekran blokuje się po upływie 10 min braku aktywności.
  - **15**: ekran blokuje się po upływie 15 min braku aktywności.

  Jeśli wartość nie ma zastosowania do systemu iOS lub iPadOS, firma Apple używa najbardziej zbliżonej *najniższej* wartości. Na przykład jeśli wprowadzisz `4` min, urządzenia z systemem iPadOS użyją `2` min. Jeśli wprowadzisz `10` min, urządzenia z systemem iOS użyją `5` min. Jest to ograniczenie firmy Apple.
  
  > [!NOTE]
  > Interfejs użytkownika usługi Intune w przypadku tego ustawienia nie oddziela wartości obsługiwanych w systemach iOS i iPadOS. Interfejs użytkownika może zostać zaktualizowany w przyszłości.

- **Wygaśnięcie hasła (dni)** : wprowadź liczbę dni, po której należy zmienić hasło urządzenia.
- **Zapobiegaj ponownemu używaniu poprzednich haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła.
- **Odblokowywanie za pomocą funkcji Touch ID i Face ID**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie odcisku palca lub widoku twarzy do odblokowywania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu tych metod.

  Zablokowanie tego ustawienia uniemożliwia także odblokowywanie urządzenia przy użyciu uwierzytelniania FaceID.

  Funkcja Face ID dotyczy:  
  - System iOS 11.0 i nowsze

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Modyfikowanie kodu dostępu**: wybierz pozycję **Blokuj**, aby uniemożliwić zmianę, dodanie lub usunięcie kodu dostępu. Po zablokowaniu tej funkcji zmiany ograniczeń kodu dostępu są ignorowane na urządzeniach nadzorowanych. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia dodawanie, zmienianie lub usuwanie kodów dostępu.

  - **Modyfikacja ustawień funkcji Touch ID i Face ID**: pozycja **Blokuj** uniemożliwia zmianę, dodawanie lub usuwanie odcisków palców identyfikatora TouchID oraz funkcji Face ID. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi aktualizowanie odcisków palców funkcji TouchID lub danych funkcji Face ID na urządzeniu.

    Zablokowanie tego ustawienia uniemożliwia również użytkownikowi zmienianie, dodawanie i usuwanie uwierzytelniania FaceID.

    Funkcja Face ID dotyczy:  
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
  
<sup>1</sup> W przypadku skonfigurowania ustawień **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** i **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** są one stosowane jedno po drugim. Na przykład jeśli wartość obu ustawień jest ustawiona na **5** minut, ekran wyłącza się automatycznie po pięciu minutach, a urządzenie jest blokowane po kolejnych pięciu minutach. Jednak jeśli użytkownik wyłączy ekran ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie jeśli użytkownik wyłączy ekran, po pięciu minutach urządzenie zostanie zablokowane.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Dostęp do centrum sterowania, gdy urządzenie jest zablokowane**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikom na dostęp do aplikacji Centrum sterowania, gdy urządzenie jest zablokowane.
- **Powiadomienia, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia dostęp do powiadomień, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na dostęp do powiadomień bez odblokowywania urządzenia.
- **Widok Dzisiaj, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia użytkownikowi dostęp do widoku Dzisiaj, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi wyświetlanie widoku Dzisiaj, gdy urządzenie jest zablokowane.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Powiadomienia aplikacji Portfel, gdy urządzenie jest zablokowane**: pozycja **Blokuj** uniemożliwia dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na dostęp do aplikacji Portfel, gdy urządzenie jest zablokowane.

## <a name="app-store-doc-viewing-gaming"></a>Sklep App Store, wyświetlanie dokumentów, granie

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych**: Pozycja **Blokuj** uniemożliwia wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na wyświetlanie dokumentów firmowych w dowolnej aplikacji. Na przykład chcesz uniemożliwić użytkownikom zapisywanie plików z aplikacji OneDrive w aplikacji Dropbox. Skonfiguruj to ustawienie jako **Blokuj**. Jeśli urządzenie otrzymało zasady (na przykład po ponownym uruchomieniu), nie ma już możliwości zapisywania.


  > [!NOTE]
  > Po zablokowaniu tego ustawienia blokowane są również klawiatury innych firm zainstalowane ze sklepu App Store.

  - **Zezwalaj niezarządzanym aplikacjom na odczytywanie z kont kontaktów zarządzanych**: po wybraniu pozycji **Zezwalaj** aplikacje niezarządzane, takie jak wbudowana w systemie iOS aplikacja Kontakty, mogą odczytywać informacje kontaktowe i uzyskiwać do nich dostęp z aplikacji zarządzanych, w tym aplikacji mobilnej Outlook. Ustawienie opcji **Nieskonfigurowane** (wartość domyślna) zapobiega odczytywaniu informacji z wbudowanej aplikacji Kontakty na urządzeniu oraz uniemożliwia usuwanie duplikatów.  
  
    To ustawienie umożliwia lub uniemożliwia odczytywanie informacji kontaktowych. Nie kontroluje ono synchronizowania kontaktów między aplikacjami.
  
    Aby użyć tego ustawienia, skonfiguruj ustawienie **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych** na wartość **Blokuj**.

  Aby uzyskać więcej informacji na temat tych dwóch ustawień i ich wpływu na synchronizację eksportu kontaktów z programu Outlook dla systemu iOS, zobacz [Support Tip: Use Intune custom profile settings with the iOS Native Contacts App](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453) (Porada pomocy technicznej: korzystanie z ustawień profilu niestandardowego usługi Intune w natywnej aplikacji Kontakty systemu iOS).

- **Traktuj usługę AirDrop jako niezarządzane miejsce docelowe**: pozycja **Wymagaj** wymusza traktowanie usługi AirDrop jako niezarządzanego miejsca docelowego upuszczania. Uniemożliwia to aplikacjom zarządzanym wysyłanie danych przy użyciu usługi AirDrop. 
- **Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych**: pozycja **Blokuj** uniemożliwia wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.

  Wybranie pozycji **Blokuj** uniemożliwia również synchronizację eksportu kontaktów w programie Outlook dla systemu iOS. Aby uzyskać więcej informacji, zobacz [Support tip: Enabling Outlook iOS Contact Sync with iOS12 MDM Controls](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453) (Porada pomocy technicznej: włączanie synchronizacji kontaktów programu Outlook w systemie iOS za pomocą kontrolek zarządzania urządzeniami mobilnymi systemu iOS12).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Wymagaj hasła sklepu iTunes Store dla wszystkich zakupów**: pozycja **Wymagaj** wymusza na użytkowniku wprowadzanie hasła Apple ID w przypadku każdego zakupu w aplikacji lub w programie iTunes. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala na zakupy bez monitowania za każdym razem o podanie hasła.
- **Zakupy w aplikacji**: wybierz pozycję **Blokuj**, aby uniemożliwić dokonywanie zakupów w aplikacji ze sklepu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na zakupy w sklepie w uruchomionej aplikacji.
- **Pobieranie ze sklepu iBook zawartości oznaczonej jako „Erotyka”** : wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom pobieranie ze sklepu iBook multimediów oznaczonych jako erotyka. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikom na pobieranie książek z kategorii „Erotyka”.
- **Zezwalaj aplikacjom zarządzanym na zapisywanie kontaktów na kontach niezarządzanych kontaktów**: po wybraniu pozycji **Zezwalaj** aplikacje zarządzane, takie jak aplikacja mobilna Outlook, mogą zapisywać i synchronizować informacje kontaktowe, w tym kontakty biznesowe i firmowe, przy użyciu aplikacji Kontakty wbudowanej w systemie iOS. Po wybraniu pozycji **Nieskonfigurowane** (wartość domyślna) aplikacje zarządzane nie mogą zapisywać ani synchronizować informacji kontaktowych z aplikacją Kontakty wbudowaną w systemie iOS na urządzeniu.
  
  Aby użyć tego ustawienia, skonfiguruj ustawienie **Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych** na wartość **Blokuj**.

- **Region klasyfikacji**: wybierz region klasyfikacji, którego chcesz użyć w przypadku dozwolonych plików do pobrania. Następnie wybierz dozwoloną klasyfikację dla kategorii **Filmy**, **Programy TV** i **Aplikacje**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Sklep z aplikacjami**: pozycja **Blokuj** uniemożliwia dostęp do sklepu z aplikacjami na urządzeniach nadzorowanych. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

  - **Instalowanie aplikacji ze sklepu App Store**: wybierz pozycję **Blokuj**, aby zablokować sklep z aplikacjami na ekranie głównym urządzenia. Użytkownicy końcowi nadal mogą instalować aplikacje przy użyciu programu iTunes lub Apple Configurator. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala na korzystanie ze sklepu z aplikacjami na ekranie głównym.
  - **Automatyczne pobieranie aplikacji**: wybierz pozycję **Blokuj**, aby uniemożliwić automatyczne pobieranie aplikacji zakupionych na innych urządzeniach. Nie wpływa to na aktualizacje istniejących aplikacji. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia pobieranie aplikacji zakupionych na innych urządzeniach z systemem iOS na dane urządzenie.

- **Jawna zawartość programu iTunes — muzyka, podcasty lub wiadomości**: wybierz pozycję **Blokuj**, aby uniemożliwić ujawnianie zawartości programu iTunes: muzyki, podkastów lub wiadomości. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych. System iOS 13 i nowsze mogą wymagać tylko urządzeń nadzorowanych. 

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Dodawanie znajomych do usługi Game Center**: pozycja **Blokuj** uniemożliwia użytkownikom dodawanie znajomych do usługi Game Center. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi dodawanie znajomych do usługi Game Center.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Game Center**: pozycja **Blokuj** uniemożliwia korzystanie z aplikacji Game Center. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Game Center na urządzeniu.
- **Gry dla wielu graczy**: wybierz pozycję **Blokuj**, aby uniemożliwić korzystanie z gier dla wielu graczy. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na gry dla wielu graczy na urządzeniu.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Dostęp do dysku sieciowego w aplikacji Pliki**: korzystając z protokołu SMB (Server Message Block), urządzenia mogą uzyskiwać dostęp do plików lub innych zasobów na serwerze sieciowym. Ustawienie **Wyłącz** uniemożliwia dostęp do plików na sieciowym dysku SMB. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.

  Ta funkcja ma zastosowanie do:  
  - Systemy iOS oraz iPadOS 13.0 i nowsze

## <a name="built-in-apps"></a>Aplikacje wbudowane

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Siri**: pozycja **Blokuj** uniemożliwia dostęp do programu Siri. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia korzystanie z asystenta głosowego Siri na urządzeniu.
  - **Program Siri, gdy urządzenie jest zablokowane**: wybierz pozycję **Blokuj** aby uniemożliwić dostęp do programu Siri, gdy urządzenie jest zablokowane. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia korzystanie z asystenta głosowego Siri na zablokowanym urządzeniu.

- **Ostrzeżenia o oszustwach w przeglądarce Safari**: pozycja **Wymagaj** wymusza pokazywanie ostrzeżeń o oszustwie w przeglądarce internetowej na urządzeniu. **Nie skonfigurowano** (ustawienie domyślne) — wyłącza tę funkcję.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Wyniki z sieci Internet w wyszukiwaniach funkcji Spotlight**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.

- **Pliki cookie w przeglądarce Safari**: wybierz sposób obsługi plików cookie na urządzeniu. Dostępne opcje:
  - Zezwalaj
  - Blokuj wszystkie pliki cookie
  - Zezwalaj na pliki cookie z odwiedzonych witryn internetowych
  - Zezwalaj na pliki cookie z aktualnej witryny internetowej

- **Obsługa języka JavaScript w przeglądarce Safari**: pozycja **Blokuj** uniemożliwia uruchamianie skryptów języka Java w przeglądarce na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia korzystanie ze skryptów języka Java.

- **Okna wyskakujące w przeglądarce Safari**: pozycja **Blokuj** umożliwia blokowanie wyskakujących okienek w przeglądarce internetowej. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia blokowanie wyskakujących okienek.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aparatu urządzenia.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

  - **FaceTime**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji FaceTime. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do aplikacji FaceTime na urządzeniu.

    Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Filtr przekleństw funkcji Siri**: pozycja **Wymagaj** uniemożliwia dyktowanie lub wypowiadanie wulgaryzmów przez Siri.

  Aby użyć tego ustawienia, w ustawieniu **Siri** wybierz pozycję **Blokuj**.

- **Używaj funkcji Siri do wykonywania zapytań o wygenerowaną przez użytkowników zawartość z Internetu**: pozycja **Blokuj** uniemożliwia programowi Siri dostęp do witryn internetowych w celu udzielania odpowiedzi na pytania. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala programowi Siri na dostęp do zawartości wygenerowanej przez użytkowników z Internetu.

  Aby użyć tego ustawienia, w ustawieniu **Siri** wybierz pozycję **Blokuj**.

- **Apple News**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aplikacji Apple News na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple News.
- **Sklep iBooks**: pozycja **Blokuj** uniemożliwia dostęp do sklepu iBooks. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala użytkownikom na przeglądanie i kupowanie książek w sklepie iBooks.
- **Aplikacja Wiadomości na urządzeniu**: pozycja **Blokuj** uniemożliwia użytkownikom korzystanie z aplikacji Wiadomości w przypadku funkcji iMessage. Jeśli urządzenie obsługuje wiadomości SMS, użytkownik może nadal wysyłać i odbierać wiadomości tekstowe przy użyciu usługi SMS. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia wysyłanie i czytanie wiadomości przez Internet za pomocą aplikacji Wiadomości.
- **Podcasty**: pozycja **Blokuj** uniemożliwia użytkownikom używanie aplikacji Podcasty. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Podcasty.
- **Usługa Music**: pozycja **Blokuj** przywraca aplikację do obsługi muzyki do trybu klasycznego i wyłącza usługę Music. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji Apple Music.
- **Usługa iTunes Radio**: pozycja **Blokuj** uniemożliwia użytkownikom korzystanie z aplikacji iTunes Radio. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie aplikacji iTunes Radio.
- **Sklep iTunes**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia korzystanie na urządzeniach z usługi iTunes. Pozycja **Blokuj** uniemożliwia użytkownikom korzystanie z usługi iTunes na urządzeniu. 

  Ta funkcja ma zastosowanie do:  
  - System iOS 4.0 i nowsze

- **Znajdź mój iPhone**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia uzyskiwanie przybliżonej lokalizacji urządzenia przy użyciu tej funkcji aplikacji Znajdź. Pozycja **Blokuj** uniemożliwia korzystanie z tej funkcji w aplikacji Znajdź. 

  Ta funkcja ma zastosowanie do:  
  - Systemy iOS 13.0 oraz iPadOS 13.0 i nowsze

- **Znajdź moich znajomych**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia znajdowanie członków rodziny i znajomych z poziomu urządzenia firmy Apple lub witryny iCloud.com przy użyciu tej funkcji aplikacji Znajdź. Pozycja **Blokuj** uniemożliwia korzystanie z tej funkcji w aplikacji Znajdź.

  Ta funkcja ma zastosowanie do:  
  - Systemy iOS 13.0 oraz iPadOS 13.0 i nowsze

- **Zmiany ustawień aplikacji Znajdź moich znajomych**: pozycja **Blokuj** uniemożliwia zmiany ustawień aplikacji Znajdź moich znajomych. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikowi zmienianie ustawień aplikacji Znajdź moich znajomych.

- **Wyniki z sieci Internet w wyszukiwaniach funkcji Spotlight**: pozycja **Blokuj** uniemożliwia funkcji wyszukiwania Spotlight zwracanie wyników z wyszukiwania w Internecie. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.

- **Blokuj usuwanie aplikacji systemowych z urządzenia**: wybranie pozycji **Blokuj** wyłącza możliwość usuwania aplikacji systemowych z urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala użytkownikom na usuwanie aplikacji systemowych.

- **Safari**: pozycja **Blokuj** uniemożliwia korzystanie z przeglądarki Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) pozwala użytkownikom na używanie przeglądarki Safari.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Autowypełnianie w przeglądarce Safari**: pozycja **Blokuj** powoduje wyłączenie funkcji automatycznego wypełniania w przeglądarce Safari na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom zmianę ustawień automatycznego uzupełniania w przeglądarce internetowej.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Typ listy ograniczonych aplikacji**: utwórz listę aplikacji, których użytkownicy nie mogą instalować ani używać. Dostępne opcje:

  - **Nieskonfigurowane** (wartość domyślna): nie ma żadnych ograniczeń ze strony usługi Intune. Użytkownicy mają dostęp do aplikacji przypisywanych przez Ciebie i wbudowanych.
  - **Aplikacje zabronione**: Aplikacje niezarządzane przez usługę Intune, które nie powinny być instalowane na urządzeniu. Użytkownicy nie są chronieni przed zainstalowaniem zabronionej aplikacji. Jednak jeśli użytkownik zainstaluje aplikację z tej listy, zostanie to zgłoszone w usłudze Intune.
  - **Aplikacje zatwierdzone**: Aplikacje, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Użytkownicy nadal będą mogli zainstalować aplikację, której nie ma na liście dozwolonych. Jednak w takim przypadku zostanie to zgłoszone w usłudze Intune.

Aby dodać aplikacje do tych list, możesz:

- **Dodać** adres URL sklepu z aplikacjami iTunes dla wybranej aplikacji. Na przykład w celu dodania aplikacji Foldery robocze firmy Microsoft wprowadź `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` lub `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`.

  Aby znaleźć adres URL aplikacji, otwórz sklep iTunes App Store i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop` lub `Microsoft Word`. Wybierz aplikację i skopiuj adres URL.

  Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć zadania **Kopiuj link**, aby uzyskać adres URL aplikacji.

- **Zaimportować** plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app url>, <app name>, <app publisher>`. Możesz również **wyeksportować** istniejącą listę, która zawiera listę aplikacji z ograniczeniami w tym samym formacie.

> [!IMPORTANT]
> Profile urządzeń, które używają ustawień aplikacji z ograniczeniami, należy przypisać do grup użytkowników.

## <a name="show-or-hide-apps"></a>Pokaż lub ukryj aplikacje

Dotyczy urządzeń z systemem iOS w wersji 9.3 i nowszych.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Typ listy aplikacji**: utwórz listę aplikacji do wyświetlania lub ukrywania. Możesz wyświetlać lub ukrywać aplikacje wbudowane i aplikacje biznesowe. W witrynie internetowej firmy Apple znajduje się lista [wbudowanych aplikacji firmy Apple](https://support.apple.com/HT208094). Dostępne opcje:

  - **Ukryte aplikacje**: wprowadź listę aplikacji ukrywanych przed użytkownikami. Użytkownicy nie mogą wyświetlać ani otwierać tych aplikacji.
  
    Firma Apple uniemożliwia ukrywanie niektórych natywnych aplikacji. Na urządzeniu nie można na przykład ukryć aplikacji **Ustawienia** czy **Wallet**. Na liście [Usuń wbudowane aplikacje firmy Apple](https://support.apple.com/HT208094) znajdują się aplikację, które można ukryć.
  
  - **Widoczne aplikacje**: wprowadź listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

- **Adres URL aplikacji**: wprowadź adres URL aplikacji w sklepie, którą chcesz wyświetlić lub ukryć. Przykład:

  - Aby dodać aplikację Foldery robocze firmy Microsoft, wprowadź `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` lub `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`. 

  - Aby dodać aplikację Microsoft Word, wprowadź `https://itunes.apple.com/de/app/microsoft-word/id586447913` lub `https://apps.apple.com/de/app/microsoft-word/id586447913`.

  Aby znaleźć adres URL aplikacji, otwórz sklep iTunes App Store i wyszukaj aplikację. Wyszukaj na przykład `Microsoft Remote Desktop` lub `Microsoft Word`. Wybierz aplikację i skopiuj adres URL.

  Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć zadania **Kopiuj link**, aby uzyskać adres URL aplikacji.

- **Identyfikator pakietu aplikacji**: Wprowadź [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) żądanej aplikacji. Możesz wyświetlać lub ukrywać aplikacje wbudowane i aplikacje biznesowe. W witrynie internetowej firmy Apple znajduje się lista [wbudowanych aplikacji firmy Apple](https://support.apple.com/HT208094).
- **Nazwa aplikacji**: Wprowadź nazwę żądanej aplikacji. Możesz wyświetlać lub ukrywać aplikacje wbudowane i aplikacje biznesowe. W witrynie internetowej firmy Apple znajduje się lista [wbudowanych aplikacji firmy Apple](https://support.apple.com/HT208094).
- **Wydawca**: Podaj wydawcę odpowiedniej aplikacji.

Aby dodać aplikacje, możesz wykonać następujące czynności:

- **Dodaj**: wybierz, aby utworzyć listę aplikacji.
- **Zaimportować** plik CSV ze szczegółowymi informacjami o aplikacji, w tym z adresem URL. Użyj formatu `<app url>, <app name>, <app publisher>`. Możesz również wybrać pozycję **Eksportuj**, aby utworzyć listę dodanych aplikacji z ograniczeniami w tym samym formacie.

## <a name="wireless"></a>Sieć bezprzewodowa

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

Informacja niezbędna w przypadku roamingu danych (porada lub ważna uwaga pozwalająca uniknąć dezorientacji klientów): To ustawienie nie będzie widoczne w profilu zarządzania urządzenia docelowego. Dzieje się tak dlatego, że to ustawienie jest traktowane jako akcja urządzenia zdalnego, która przy każdej zmianie stanu roamingu danych na urządzeniu będzie ponownie blokowana przez usługę Intune. Mimo że ustawienie nie znajduje się w profilu zarządzania, działa, jeśli w raporcie konsoli administracyjnej akcja jest wyświetlana jako zakończona powodzeniem. 
- **Roaming danych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming danych w sieci komórkowej. Opcja **Nieskonfigurowane** (domyślna) zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.

  > [!IMPORTANT]
  > To ustawienie jest traktowane jako akcja urządzenia zdalnego. Dlatego to ustawienie nie jest wyświetlane w profilu zarządzania na urządzeniu. Za każdym razem, gdy stan roamingu danych zmienia się na urządzeniu, ustawienie **Roaming danych** jest blokowane przez usługę Intune. Jeśli w usłudze Intune stan raportowania pokazuje sukces, wiesz, że ustawienie działa, nawet jeśli nie jest wyświetlane w profilu zarządzania na urządzeniu.

- **Globalne pobieranie w tle podczas roamingu**: pozycja **Blokuj** uniemożliwia używanie funkcji globalnego pobierania w tle podczas roamingu w sieci komórkowej. Opcja **Nieskonfigurowane** (domyślna) zezwala urządzeniu na pobieranie danych, np. wiadomości e-mail, podczas roamingu w sieci komórkowej.
- **Wybieranie głosowe**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom korzystanie z funkcji wybierania głosowego na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia wybieranie głosowe na urządzeniu.
- **Roaming połączeń głosowych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming połączeń danych w sieci komórkowej. Opcja **Nieskonfigurowane** (domyślna) zezwala na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.
- **Osobisty hotspot**: Opcja **Blokuj** wyłącza osobisty hotspot na urządzeniu użytkownika przy każdej synchronizacji urządzenia. To ustawienie może być niezgodne w przypadku niektórych operatorów. Opcja **Nieskonfigurowane** (ustawienie domyślne) zachowuje domyślną konfigurację osobistego hotspotu ustawioną przez użytkownika.

  > [!IMPORTANT]
  > To ustawienie jest traktowane jako akcja urządzenia zdalnego. Dlatego to ustawienie nie jest wyświetlane w profilu zarządzania na urządzeniu. Za każdym razem, gdy stan osobistego hotspotu zmienia się na urządzeniu, ustawienie **Osobisty hotspot** jest blokowane przez usługę Intune. Jeśli w usłudze Intune stan raportowania pokazuje sukces, wiesz, że ustawienie działa, nawet jeśli nie jest wyświetlane w profilu zarządzania na urządzeniu.

- **Zasady użycia danych komórkowych (tylko aplikacje zarządzane)** : zdefiniuj typy danych, których aplikacje zarządzane mogą używać podczas pracy w sieciach komórkowych. Dostępne opcje:
  - **Zablokuj użycie danych komórkowych**: zablokuj użycie danych komórkowych dla **wszystkich zarządzanych aplikacji** lub **wybierz określone aplikacje**.
  - **Zablokuj użycie danych komórkowych podczas roamingu**: zablokuj użycie danych komórkowych podczas roamingu dla **wszystkich zarządzanych aplikacji** lub **wybierz określone aplikacje**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Zmiany w ustawieniach wykorzystania danych komórkowych przez aplikację**: wybierz pozycję **Blokuj**, aby uniemożliwić zmiany ustawień użycia danych komórkowych aplikacji. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi kontrolowanie, które aplikacje mogą korzystać z danych komórkowych.
- **Zmiany w ustawieniach planu komórkowego**: Pozycja **Blokuj** uniemożliwia użytkownikom zmianę jakichkolwiek ustawień planu komórkowego. Opcja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom wprowadzanie zmian.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze

- **Modyfikowanie osobistego hotspotu przez użytkownika**: po wybraniu pozycji **Blokuj** użytkownik nie może zmieniać ustawienia osobistego hotspotu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom końcowym włączanie i wyłączanie ich osobistych hotspotów.

  Jeśli zablokujesz to ustawienie oraz ustawienie **Osobisty hotspot**, osobisty hotspot zostanie wyłączony.

  Ta funkcja ma zastosowanie do:  
  - System iOS 12.2 i nowsze

- **Dołączaj do sieci Wi-Fi wyłącznie za pomocą profilów konfiguracji**: pozycja **Wymagaj** wymusza użycie na urządzeniu tylko sieci Wi-Fi, które zostały skonfigurowane przy użyciu profilu konfiguracji usługi Intune. Opcja **Nieskonfigurowane** (domyślna) zezwala urządzeniu na korzystanie z innych sieci Wi-Fi.

  Po wybraniu pozycji **Wymagaj** upewnij się, że urządzenie ma profil sieci Wi-Fi. Jeśli nie przypiszesz profilu sieci Wi-Fi, to ustawienie może uniemożliwić urządzeniu nawiązywanie połączeń z Internetem. Innymi słowy, jeśli ten profil ograniczeń urządzenia zostanie przypisany wcześniej niż profil sieci Wi-Fi, urządzenie może mieć zablokowaną możliwość łączenia się z Internetem.
  
  Jeśli urządzenie nie może nawiązać połączenia, wyrejestruj je i zarejestruj ponownie z profilem sieci Wi-Fi. Następnie wybierz dla tego ustawienia pozycję **Wymagaj** w profilu ograniczeń urządzenia i przypisz profil do urządzenia.

- **Sieć Wi-Fi jest zawsze włączona**: po wybraniu pozycji **Wymagaj** sieć Wi-Fi jest na stałe włączona w aplikacji Ustawienia. Nie można jej wyłączyć w aplikacji Ustawienia ani w Centrum sterowania, nawet gdy urządzenie jest w trybie samolotowym. Pozycja **Nieskonfigurowane** (wartość domyślna) zapewnia użytkownikowi kontrolę nad włączaniem i wyłączaniem sieci Wi-Fi.

  Skonfigurowanie tego ustawienia nie uniemożliwia użytkownikom wyboru sieci Wi-Fi.

  Ta funkcja ma zastosowanie do:  
  - Systemy iOS oraz iPadOS 13.0 i nowsze

## <a name="connected-devices"></a>Połączone urządzenia

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Wykrywanie nadgarstka przez sparowane urządzenie Apple Watch**: pozycja **Wymagaj** wymusza używanie funkcji wykrywania nadgarstka na sparowanym zegarku Apple Watch. Jeśli ta opcja jest wymagana, zegarek Apple Watch nie będzie wyświetlać powiadomień, kiedy nie będzie znajdować się na nadgarstku użytkownika. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Wymagaj hasła parowania dla wychodzących żądań AirPlay**: pozycja **Wymagaj** umożliwia wymaganie hasła parowania, gdy użytkownik używa funkcji AirPlay do strumieniowego przesyłania zawartości do innych urządzeń firmy Apple. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi przesyłanie strumieniowe zawartości przy użyciu funkcji AirPlay bez wprowadzania hasła.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **AirDrop**: pozycja **Blokuj** uniemożliwia używanie funkcji AirDrop na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
- **Parowanie urządzenia Apple Watch**: pozycja **Blokuj** uniemożliwia parowanie urządzenia z urządzeniem Apple Watch. Opcja **Nieskonfigurowane** (domyślna) zezwala na parowanie urządzenia z zegarkiem Apple Watch.
- **Modyfikowanie ustawień funkcji Bluetooth**: pozycja **Blokuj** uniemożliwia użytkownikowi końcowemu zmianę ustawień protokołu Bluetooth na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia użytkownikowi zmianę tych ustawień.
- **Parowanie hosta na potrzeby kontrolowania urządzeń, z którymi można parować urządzenie z systemem iOS**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) zezwala na parowanie hostów w celu umożliwienia administratorowi kontrolowania tego, z którymi urządzeniami może być sparowane urządzenie z systemem iOS. Pozycja **Blokuj** uniemożliwia parowanie hosta.
- **Blokuj funkcję AirPrint**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie funkcji AirPrint na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) zezwala użytkownikowi na korzystanie z funkcji AirPrint.
  - **Blokuj przechowywanie poświadczeń funkcji AirPrint w pęku kluczy**: pozycja **Blokuj** uniemożliwia korzystanie z magazynu pęku kluczy do przechowywania nazwy użytkownika i hasła na urządzeniu. Opcja **Nieskonfigurowane** (domyślna) umożliwia przechowywanie nazwy użytkownika i hasła funkcji AirPrint w aplikacji pęku kluczy.
  - **Wymagaj zaufanego certyfikatu protokołu TLS dla funkcji AirPrint**: pozycja **Wymagaj** wymusza użycie zaufanych certyfikatów na potrzeby komunikacji dotyczącej drukowania przy użyciu protokołu TLS.
  - **Blokuj odnajdywanie drukarek AirPrint za pomocą protokołu iBeacon**: pozycja **Blokuj** uniemożliwia złośliwym sygnałom nawigacyjnym funkcji AirPrint Bluetooth wyłudzanie informacji dotyczących ruchu sieciowego. Opcja **Nieskonfigurowane** (domyślna) zezwala na ogłaszanie drukarek AirPrint na urządzeniu.
- **Blokuj konfigurowanie nowych urządzeń w pobliżu**: Pozycja **Blokuj** wyłącza monitowanie o konfigurację nowych urządzeń znajdujących się w pobliżu. Opcja **Nieskonfigurowane** (ustawienie domyślne) zezwala na monitowanie użytkowników o połączenie z innymi urządzeniami firmy Apple znajdującymi się w pobliżu.

  Ta funkcja ma zastosowanie do:  
  - System iOS 11.0 i nowsze

- **Dostęp do plików na dysku USB**: urządzenia mogą łączyć się z dyskiem USB i otwierać znajdujące się na nim pliki. Pozycja **Wyłącz** uniemożliwia dostęp urządzenia do dysku USB w aplikacji Pliki, gdy dysk USB jest podłączony do urządzenia. Wyłączenie tej funkcji blokuje również użytkownikom końcowym przesyłanie plików na dysk USB podłączony do urządzenia iPad. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do dysku USB w aplikacji Pliki.

  Ta funkcja ma zastosowanie do:  
  - Systemy iOS oraz iPadOS 13.0 i nowsze

## <a name="keyboard-and-dictionary"></a>Klawiatura i słownik

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Wyszukiwanie definicji słów**: pozycja **Blokuj** uniemożliwia użytkownikom wyróżnianie wyrazu, a następnie wyszukiwanie jego definicji na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na dostęp do funkcji wyszukiwania definicji.
- **Klawiatury predykcyjne**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia korzystanie z klawiatur predykcyjnych sugerujących wyrazy, które użytkownik może chcieć wpisać. Pozycja **Blokuj** uniemożliwia użycie tej funkcji.
- **Autokorekta**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) pozwala na automatyczne poprawianie błędnie napisanych wyrazów przez urządzenie. Pozycja **Blokuj** uniemożliwia korzystanie z autokorekty.
- **Sprawdzanie pisowni dla klawiatury**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie sprawdzania pisowni na urządzeniu. Pozycja **Blokuj** pozwala na sprawdzanie pisowni.
- **Skróty klawiaturowe**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie skrótów klawiaturowych na urządzeniu. Pozycja **Blokuj** uniemożliwia użytkownikowi korzystanie ze skrótów klawiaturowych.
- **Dyktowanie**: pozycja **Blokuj** uniemożliwia użytkownikowi wprowadzanie tekstu przy użyciu głosu. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala użytkownikowi na korzystanie z wprowadzania tekstu przez dyktowanie.
- **QuickPath**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom korzystanie z funkcji QuickPath, która pozwala na ciągłe wprowadzanie danych na klawiaturze urządzenia. Użytkownicy mogą wpisywać słowa, przesuwając szybko po klawiszach. Pozycja **Blokuj** uniemożliwia użytkownikom korzystanie z funkcji QuickPath. 

  Ta funkcja ma zastosowanie do:  
  - Systemy iOS 13.0 oraz iPadOS 13.0 i nowsze

## <a name="cloud-and-storage"></a>Chmura i magazyn

### <a name="settings-apply-to-all-enrollment-types"></a>Ustawienia mają zastosowanie do: Wszystkie typy rejestracji

- **Szyfrowana kopia zapasowa**: pozycja **Wymagaj** umożliwia wymaganie szyfrowania wszystkich kopii zapasowych urządzenia.
- **Zarządzane aplikacje są synchronizowane z chmurą**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) zezwala aplikacjom zarządzanym usługi Intune na synchronizowanie danych z kontem użytkownika w usłudze iCloud. Pozycja **Blokuj** uniemożliwia taką synchronizację danych z usługą iCloud.
- **Blokuj tworzenie kopii zapasowych książek przedsiębiorstwa**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom tworzenie kopii zapasowej książek przedsiębiorstwa. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom tworzenie kopii zapasowych tych książek.
- **Blokuj synchronizację metadanych książek przedsiębiorstwa (notatki i wyróżnienia)** : pozycja **Blokuj** uniemożliwia synchronizowanie notatek i wyróżnień w książkach przedsiębiorstwa. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia synchronizowanie.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Synchronizowanie strumienia zdjęć z usługą iCloud**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikom włączanie funkcji **Mój strumień zdjęć** na urządzeniu, co pozwala na synchronizowanie z usługą iCloud i udostępnianie zdjęć na wszystkich urządzeniach użytkownika. Pozycja **Blokuj** zezwala na synchronizację funkcji Strumień zdjęć w usłudze iCloud. Zablokowanie tej funkcji może spowodować utratę danych. 
- **Biblioteka zdjęć usługi iCloud**: ustaw tę opcję na pozycję **Blokuj**, aby wyłączyć możliwość używania biblioteki zdjęć usługi iCloud do przechowywania zdjęć i klipów wideo w chmurze. Wszystkie zdjęcia, które nie zostały w pełni pobrane z biblioteki zdjęć iCloud na urządzenie, są usuwane z urządzenia. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia używanie biblioteki zdjęć iCloud.
- **Udostępniony strumień zdjęć**: wybierz pozycję **Blokuj**, aby wyłączyć funkcję **Udostępnianie zdjęć w usłudze iCloud** na urządzeniu. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia przesyłanie strumieniowe udostępnionych zdjęć.
- **Handoff**: pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom kontynuowanie pracy rozpoczętej na urządzeniu z systemem iOS na innym urządzeniu z systemem iOS lub macOS. Pozycja **Blokuj** uniemożliwia użycie programu Handoff.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Tworzenie kopii zapasowych w usłudze iCloud**: Pozycja **Nieskonfigurowane** (ustawienie domyślne) umożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud. Pozycja **Blokuj** uniemożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Blokuj synchronizowanie dokumentów z usługą iCloud**: Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia synchronizowanie dokumentów i par klucz-wartość w obszarze magazynu usługi iCloud. Pozycja **Blokuj** uniemożliwia synchronizowanie dokumentów i danych w usłudze iCloud.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

- **Blokuj synchronizowanie pęku kluczy z usługą iCloud**: wybierz pozycję **Blokuj**, aby wyłączyć synchronizowanie poświadczeń przechowywanych w pęku kluczy z usługą iCloud. Pozycja **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom synchronizację tych poświadczeń.

  Począwszy od systemu iOS 13.0, to ustawienie wymaga urządzeń nadzorowanych.

## <a name="autonomous-single-app-mode"></a>Autonomiczny tryb pojedynczej aplikacji

Użyj tych ustawień w celu skonfigurowania urządzeń z systemem iOS/iPadOS, aby uruchamiać określone aplikacje w autonomicznym trybie pojedynczej aplikacji. Gdy ten tryb jest skonfigurowany, a użytkownik uruchomi jedną ze skonfigurowanych aplikacji, urządzenie zostanie ograniczone do tej aplikacji. Przełączanie aplikacji/zadań będzie wyłączone do czasu opuszczenia dozwolonej aplikacji przez użytkownika.

Na przykład w środowisku szkolnym lub uniwersyteckim można dodać aplikację, która umożliwia użytkownikom korzystanie z testów na urządzeniu. Można też ograniczyć urządzenie do aplikacji Portal firmy, dopóki użytkownik końcowy nie uwierzytelni się. Po zakończeniu działań aplikacji przez użytkownika lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Nazwa aplikacji**: Wprowadź nazwę żądanej aplikacji.
- **Identyfikator pakietu aplikacji**: Wprowadź [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) żądanej aplikacji.
- **Dodaj**: wybierz, aby utworzyć listę aplikacji.

Możesz również **zaimportować** plik CSV zawierający listę nazw aplikacji i ich identyfikatorów pakietu. Lub **wyeksportuj** istniejącą listę, która zawiera aplikacje.

## <a name="kiosk"></a>Kiosk

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Aplikacja do uruchamiania w trybie kiosku**: wybierz typ aplikacji, które chcesz uruchomić w trybie kiosku. Dostępne opcje:
  - **Nieskonfigurowane** (wartość domyślna): Ustawienia kiosku nie są stosowane. Urządzenie nie zostanie uruchomione w trybie kiosku.
  - **Aplikacja ze Sklepu**: Wprowadź adres URL aplikacji w sklepie iTunes.
  - **Zarządzana aplikacja**: Wybierz aplikację dodaną do usługi Intune.
  - **Wbudowana aplikacja**: Wprowadź [identyfikator pakietu](bundle-ids-built-in-ios-apps.md) wbudowanej aplikacji.

- **Obsługa dotykowa z ułatwieniami**: pozycja **Wymagaj** wymusza ustawienie ułatwień dostępu Obsługa dotykowa z ułatwieniami na urządzeniu. Ta funkcja pomaga użytkownikom wykonywać na ekranie gesty, które mogą okazać się trudne. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Odwróć kolory**: pozycja **Wymagaj** wymusza użycie ułatwień dostępu Odwróć kolory, co umożliwia użytkownikom niedowidzącym zmienianie ustawień ekranu. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Dźwięk mono**: pozycja **Wymagaj** wymaga ustawienia ułatwienia dostępu Dźwięk mono na urządzeniu. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Sterowanie głosowe**: pozycja **Wymagaj** umożliwia użytkownikom sterowanie urządzeniem za pomocą głosu oraz zapewnia pełną kontrolę nad systemem operacyjnym przy użyciu poleceń Siri. Pozycja **Nieskonfigurowane** powoduje wyłączenie sterowania głosem na urządzeniu.

  To ustawienie ma zastosowanie do:  
  - System iOS 13.0 i nowsze
  - System iPadOS 13.0 i nowsze
  
  > [!TIP]
  > Jeśli dla Twojej organizacji są dostępne aplikacje biznesowe, które nie są gotowe do **sterowania głosem** w momencie wydania systemu iOS 13.0, zalecamy pozostawienie pozycji **Nieskonfigurowane**.

- **VoiceOver**: pozycja **Wymagaj** wymusza użycie na urządzeniu ustawienia ułatwień dostępu VoiceOver, aby tekst na ekranie mógł być odczytywany na głos. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Powiększenie**: pozycja **Wymagaj** wymusza użycie ustawienia Powiększenie na urządzeniu, aby umożliwić użytkownikom powiększenie obrazu wyświetlanego na ekranie za pomocą dotyku. Pozycja **Nieskonfigurowane** nie uruchamia ani nie włącza tej funkcji w trybie kiosku.
- **Blokada automatyczna**: pozycja **Blokuj** uniemożliwia automatyczne blokowanie urządzenia. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Przełącznik dzwonka**: Pozycja **Blokuj** uniemożliwia użycie przełącznika dzwonka (wyciszenie) na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Obrót ekranu**: Pozycja **Blokuj** uniemożliwia zmianę orientacji ekranu przy obrocie urządzenia. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Przycisk usypiania ekranu**: Wybierz pozycję **Blokuj**, aby wyłączyć przycisk usypiania/budzenia ekranu na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na tę funkcję.
- **Dotyk**: pozycja **Blokuj** wyłącza ekran dotykowy na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z ekranu dotykowego.
- **Przyciski regulacji głośności**: pozycja **Blokuj** uniemożliwia korzystanie z przycisków regulacji głośności na urządzeniu. Pozycja **Nieskonfigurowane** włącza przyciski regulacji głośności.
- **Wspomagająca kontrola dotykowa**: pozycja **Zezwalaj** pozwala użytkownikom na korzystanie z funkcji obsługi dotykowej z ułatwieniami. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Odwróć kontrolę kolorów**: pozycja **Zezwalaj** pozwala na zmianę ustawienia funkcji Odwróć kolory, które umożliwiają użytkownikowi dostosowanie jej do własnych potrzeb. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Mów przy wybranym tekście**: pozycja **Zezwalaj** umożliwia użycie ustawienia ułatwień dostępu Czytaj zaznaczenie na urządzeniu. Ta funkcja odczytuje tekst, który użytkownik wybierze przy użyciu głosu. Pozycja **Nieskonfigurowane** wyłącza tę funkcję.
- **Modyfikacja sterowania głosem**: pozycja **Zezwalaj** umożliwia użytkownikom zmianę stanu sterowania głosem na ich urządzeniach. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom zmianę stanu sterowania głosem na ich urządzeniach.

  To ustawienie ma zastosowanie do:  
  - System iOS 13.0 i nowsze
  - System iPadOS 13.0 i nowsze

- **Kontrola VoiceOver**: pozycja **Zezwalaj** umożliwia zmiany podkładu głosowego, aby zezwolić użytkownikom na aktualizowanie ustawień funkcji VoiceOver, takich jak szybkość odczytywania tekstu na głos. Pozycja **Nieskonfigurowane** uniemożliwia zmiany podkładu głosowego.
- **Ustawianie powiększania**: pozycja **Zezwalaj** umożliwia użytkownikowi zmienianie powiększenia. Pozycja **Nieskonfigurowane** uniemożliwia zmiany powiększenia.

> [!NOTE]
> Aby można było skonfigurować urządzenie z systemem iOS do obsługi trybu kiosku, należy najpierw użyć narzędzia Apple Configurator lub programu Apple Device Enrollment Program w przełączenia go do trybu nadzorowanego. Zapoznaj się z przewodnikiem firmy Apple dotyczącym korzystania z narzędzia Apple Configurator.
> Jeśli wprowadzona aplikacja systemu iOS zostanie zainstalowana po przypisaniu profilu, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Rejestrowanie urządzeń, Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Nieoznaczone domeny poczty e-mail** > **Adres URL domeny poczty e-mail**: Dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy końcowi otrzymają wiadomość e-mail z domeny innej niż wprowadzona, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu iOS jako niezaufana.

- **Zarządzane domeny sieci Web** > **Adres URL domeny sieci Web**: dodaj do listy co najmniej jeden adres URL. Dokumenty pobierane z wprowadzonych domen są uznawane za zarządzane. To ustawienie ma zastosowanie wyłącznie do dokumentów pobieranych przy użyciu przeglądarki Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ustawienia mają zastosowanie do: Automatyczne rejestrowanie urządzeń (nadzorowane)

- **Domeny automatycznego wypełniania haseł w programie Safari** > **Adres URL domeny**: Dodaj do listy co najmniej jeden adres URL. Użytkownicy mogą zapisywać wyłącznie hasła witryn sieci Web dla adresów URL znajdujących się na tej liście. To ustawienie dotyczy wyłącznie przeglądarki Safari oraz urządzeń działających w trybie nadzorowanym. Jeśli nie podasz żadnych adresów URL, użytkownicy będą mogli zapisywać hasła ze wszystkich witryn internetowych.

  To ustawienie ma zastosowanie do:  
  - System iOS 9.3 i nowsze

## <a name="settings-that-require-supervised-mode"></a>Ustawienia, które wymagają trybu nadzorowanego

Tryb nadzorowany systemu iOS można włączyć tylko podczas początkowego konfigurowania urządzenia za pośrednictwem programu Device Enrollment Program firmy Apple lub programu Apple Configurator. Po włączeniu trybu nadzorowanego na urządzeniu można skonfigurować następujące funkcje za pomocą usługi Intune:

- Blokada aplikacji (tryb jednej aplikacji) 
- Globalny serwer proxy HTTP 
- Wyłączanie blokady aktywacji 
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
