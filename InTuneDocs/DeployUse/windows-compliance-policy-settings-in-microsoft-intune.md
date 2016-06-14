---
# required metadata

title: Ustawienia zasad zgodności dla urządzeń z systemem Windows | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ustawienia zasad zgodności dla urządzeń z systemem Windows w usłudze Microsoft Intune

Ustawienia zasad opisane w tym temacie mają zastosowanie do urządzeń, na których działa system operacyjny Windows. Konkretna obsługiwana wersja systemu Windows jest podana w odpowiedniej sekcji poniżej.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Android](android-compliance-policy-settings-in-microsoft-intune.md)

## Ustawienia zasad zgodności dla urządzeń z systemem Windows Phone
Ustawienia wymienione w tej sekcji są obsługiwane w systemie Windows Phone 8.1 lub nowszym.

## Ustawienia zabezpieczeń systemu
### Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę opcję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed
  uzyskaniem dostępu do urządzenia.

- **Zezwalaj na proste hasła:** ustaw tę opcję
   na wartość **Tak**, aby zezwolić użytkownikom na tworzenie prostych haseł,
   takich jak „**1234**” lub „**1111**”.

-  **Minimalna długość hasła:**
  określ minimalną liczbę cyfr lub znaków, które
  musi zawierać hasło użytkownika.
- **Wymagany typ hasła:** określ, czy użytkownicy muszą utworzyć
hasła **alfanumeryczne**, czy też **numeryczne**.

  W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli minimalna długość hasła jest większa niż osiem znaków lub minimalna liczba zestawów znaków jest większa niż dwa.

- **Minimalna liczba zestawów znaków:** jeśli opcja **Wymagany typ hasła** jest ustawiona na wartość
**Alfanumeryczne**, to ustawienie określa minimalną liczbę
zestawów znaków, które musi zawierać hasło. Są cztery zestawy znaków:
  -   Małe litery
  -   Wielkie litery
  -   Symbole
  -   Liczby

  Im większa liczba zostanie podana dla tego ustawienia, tym bardziej skomplikowane hasła będą musieli tworzyć użytkownicy. W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli minimalna długość hasła jest większa niż osiem znaków lub minimalna liczba zestawów znaków jest większa niż dwa.
- **Liczba minut braku aktywności, zanim będzie wymagane hasło:** określa czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** Wybierz liczbę dni, po których hasło użytkownika wygasa
  i należy utworzyć nowe.

- **Pamiętaj historię haseł:** użyj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi
  ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli wybrano opcję **Pamiętaj historię haseł**, określ
  liczbę wcześniej używanych haseł, których nie można użyć ponownie.
- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownicy końcowi otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

  **To ustawienie dotyczy tylko urządzeń z systemem Windows 10 Mobile.**
### Szyfrowanie
- **Wymagaj szyfrowania na urządzeniu przenośnym:** ustaw tę opcję na wartość **Tak**, aby wymagać
  zaszyfrowania urządzenia w celu połączenia się z zasobami.

## Ustawienia kondycji urządzenia
- **Wymagaj, aby urządzenia były zgłaszane jako urządzenia o dobrej kondycji:** możesz ustawić regułę wymagającą od urządzeń z systemem **Windows 10 Mobile** zgłoszenia dobrej kondycji w nowych lub istniejących zasadach zgodności.  Jeśli ustawienie jest włączone, urządzenia z systemem Windows 10 są oceniane za pośrednictwem usługi zaświadczania o kondycji (HAS, Health Attestation Service) dla następujących punktów danych:
  -  **Funkcja BitLocker jest włączona:** po włączeniu funkcji BitLocker urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub zahibernowany. Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika. Funkcja pomaga upewnić się, że komputer nie jest modyfikowany, nawet wtedy, gdy zostanie pozostawiony bez nadzoru, zgubiony lub skradziony. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.
  -  **Integralność kodu jest włączona:** integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci. Funkcja integralności kodu wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy lub czy plik systemowy został zmodyfikowany przez złośliwe oprogramowanie, które zostało uruchomione przez konto użytkownika z uprawnieniami administratora.
  - **Bezpieczny rozruch jest włączony:** po włączeniu funkcji bezpiecznego rozruchu system musi włączać się do fabrycznie zaufanego stanu. Ponadto po włączeniu funkcji bezpiecznego rozruchu podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, które są podpisami zaufanymi dla organizacji, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI dokonuje weryfikacji tych elementów, zanim umożliwi uruchomienie urządzenia. Jeśli jakiekolwiek pliki zostały zmodyfikowane, co spowodowało uszkodzenie ich podpisu, system nie uruchomi się.

  Aby uzyskać informacje o sposobie działania usługi HAS, zobacz [Zaświadczanie o kondycji CSP](https://msdn.microsoft.com/library/dn934876.aspx).
##  Ustawienia właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej
    wersji systemu operacyjnego, zostaje zgłoszone jako niezgodne.
    Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta
    z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.


## Ustawienia zasad zgodności dla komputerów z systemem Windows
Ustawienia wymienione w tej sekcji są obsługiwane na komputerach z systemem Windows.
## Ustawienia zabezpieczeń systemu
### Hasło
- **Minimalna długość hasła:** — opcja obsługiwana w systemie Windows 8.1.

  Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

  W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli **Minimalna długość hasła** jest większa niż 8 znaków lub **Minimalna liczba zestawów znaków** jest większa niż 2.

- **Wymagany typ hasła:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

  Określ, czy użytkownicy muszą utworzyć hasła **Alfanumeryczne**, czy też **Numeryczne**.

- **Minimalna liczba zestawów znaków:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1. Jeśli parametr **Wymagany typ hasła** ma wartość **Alfanumeryczne**, wówczas to ustawienie określa minimalną liczbę zestawów znaków użytych w haśle. Są cztery zestawy znaków:
  -   Małe litery
  -   Wielkie litery
  -   Symbole
  -   Liczby: im większa liczba zostanie podana dla tego ustawienia, tym bardziej skomplikowane hasła będą musieli tworzyć użytkownicy.

  W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli **Minimalna długość hasła** jest większa niż 8 znaków lub **Minimalna liczba zestawów znaków** jest większa niż 2.
- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

  Określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

  Wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.

- **Pamiętaj historię haseł:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

  Używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.
- **Zapobiegaj ponownemu używaniu poprzednich haseł:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

  Jeśli jest zaznaczona opcja **Pamiętaj historię haseł:**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.

## Ustawienia kondycji urządzenia
- **Wymagaj, aby urządzenia były zgłaszane jako urządzenia o dobrej kondycji:** — opcja obsługiwana na urządzeniach z systemem Windows 10.
Można ustawić zasady, które będą wymagać od urządzeń z systemem Windows 10 zgłoszenia dobrej kondycji w nowych lub istniejących zasadach zgodności.  Jeśli ustawienie jest włączone, urządzenia z systemem Windows 10 są oceniane za pośrednictwem usługi zaświadczania o kondycji (HAS, Health Attestation Service) dla następujących punktów danych:
  -  **Funkcja BitLocker jest włączona:** po włączeniu funkcji BitLocker urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub zahibernowany. Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika. Funkcja pomaga upewnić się, że komputer nie jest modyfikowany, nawet wtedy, gdy zostanie pozostawiony bez nadzoru, zgubiony lub skradziony. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.
  -  **Integralność kodu jest włączona:** integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci. Funkcja integralności kodu wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy lub czy plik systemowy został zmodyfikowany przez złośliwe oprogramowanie, które zostało uruchomione przez konto użytkownika z uprawnieniami administratora.
  - **Bezpieczny rozruch jest włączony:** po włączeniu funkcji bezpiecznego rozruchu system musi włączać się do fabrycznie zaufanego stanu. Ponadto po włączeniu funkcji bezpiecznego rozruchu podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, które są podpisami zaufanymi dla organizacji, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI dokonuje weryfikacji tych elementów, zanim umożliwi uruchomienie urządzenia. Jeśli jakiekolwiek pliki zostały zmodyfikowane, co spowodowało uszkodzenie ich podpisu, system nie uruchomi się.
  - **Usługa wczesnej ochrony przed złośliwym kodem jest włączona:** usługa wczesnej ochrony przed złośliwym kodem zapewnia ochronę komputerów w sieci podczas uruchamiania i przed zainicjowaniem sterowników firm trzecich.

  Aby uzyskać informacje o sposobie działania usługi HAS, zobacz [Zaświadczanie o kondycji CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## Ustawienia właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** — opcja obsługiwana w systemach Windows 8.1 i Windows 10.

  W tym miejscu podaj wersję w formacie główna.pomocnicza.kompilacja. Numer wersji musi odpowiadać wersji zwracanej przez polecenie winver.

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż określona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** — opcja obsługiwana w systemach Windows 8.1 i Windows 10.

  Jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

Aby znaleźć wersję systemu operacyjnego do użycia w ustawieniach **Wymagana minimalna wersja systemu operacyjnego** i **Dozwolona maksymalna wersja systemu operacyjnego**, uruchom polecenie **winver** w wierszu polecenia. Polecenie winver zwraca zgłoszoną wersję systemu operacyjnego.
- Komputery z systemem Windows 8.1 zwracają wersję **6.3**.    Jeśli ustawiono regułę wersji systemu operacyjnego Windows na wartość Windows 8.1, urządzenie jest zgłaszane jako niezgodne nawet wtedy, gdy działa na nim system Windows 8.1.
- W przypadku komputerów z systemem operacyjnym Windows 10 należy ustawić wersję „10.0” z dołączonym numerem kompilacji systemu operacyjnego zwróconym przez polecenie winver. Na przykład może to wyglądać mniej więcej tak: 10.0.10586.
> ![CA_Win10OSVersion](./media/ca_win10-os-version.png)


<!--HONumber=May16_HO1-->


