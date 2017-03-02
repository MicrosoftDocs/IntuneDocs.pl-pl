---
title: "Tworzenie zasad zgodności dla systemu Windows"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące tworzenia zasad zgodności dla urządzeń z systemem Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 13fc7783-d4de-47d0-b1b8-4c8710a9e6ab
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 5a50f4abea58a39b18347d03bb1553856d592c93
ms.lasthandoff: 02/18/2017


---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune-azure-preview"></a>Tworzenie zasad zgodności dla urządzeń z systemem Windows w wersji zapoznawczej usługi Intune Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zasady zgodności są tworzone dla każdej platformy.  Zasady zgodności można tworzyć w witrynie Azure Portal. Aby dowiedzieć się więcej na temat tego, czym są zasady zgodności, zobacz artykuł [What is a device compliance](what-is-device-compliance.md) (Czym jest zgodność z urządzeniem). Aby dowiedzieć się więcej o wymaganiach wstępnych, które należy spełnić przed utworzeniem zasad zgodności, zobacz artykuł [Get started with device compliance](get-started-with-device-compliance.md) (Wprowadzenie do zgodności z urządzeniem).

W tabeli poniżej opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

---------------------------

| **Ustawienie zasad** | **Windows 8.1 lub nowszy** | **Windows Phone 8.1 lub nowszy** |
|----| ----| --- |
| **Konfiguracja kodu PIN lub hasła** | Skorygowane | Skorygowane |   
| **Szyfrowanie urządzenia** | Nie dotyczy | Skorygowane |   
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Nie dotyczy | Nie dotyczy |  
| **Profil e-mail** | Nie dotyczy | Nie dotyczy |   
| **Minimalna wersja systemu operacyjnego** | Poddane kwarantannie | Poddane kwarantannie |   
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie | Poddane kwarantannie |   
| **Zaświadczanie o kondycji systemu Windows** | Poddane kwarantannie: Windows 10 i Windows 10 Mobile|Nie dotyczy: Windows 8.1 |

-------------------------------

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).+

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenia nie są zgodne, zostaną wykonane następujące akcje:+

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Tworzenie zasad zgodności w witrynie Azure Portal

1. W bloku **Intune** wybierz pozycję **Ustaw zgodność urządzenia**. W obszarze **Zarządzaj** wybierz pozycję **Wszystkie zasady zgodności urządzeń** i wybierz przycisk **Utwórz**.
2. Wpisz nazwę, opis i wybierz platformę, której te zasady mają dotyczyć.
3. Wybierz pozycję **Wymagania zgodności**, aby otworzyć blok wymagań zgodności.  Możesz określić ustawienia **Zabezpieczenia**, **Kondycja urządzenia** i **Właściwości urządzenia**, a gdy wszystko będzie gotowe, wybierz przycisk **Ok**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Aby przypisać użytkownikom zasady zgodności, wybierz skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w bloku **Zgodność — zasady**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie bloku, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.
2. Wybierz pozycję **Wybierz grupy**, aby otworzyć blok, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.  Wybranie pozycji **Wybierz** powoduje wdrożenie zasad dla użytkowników.

Zasady zostały zastosowane do użytkowników.  Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę pozycję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia.
- **Zezwalaj na proste hasła:** ustaw tę opcję na wartość **Tak**, aby zezwolić użytkownikom na tworzenie prostych haseł, takich jak „**1234**” lub „**1111**”.
- **Minimalna długość hasła:** określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła:** określ, czy użytkownicy muszą utworzyć hasła **alfanumeryczne**, czy też **numeryczne**.

W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli minimalna długość hasła jest większa niż osiem znaków lub minimalna liczba zestawów znaków jest większa niż dwa.

- **Minimalna liczba zestawów znaków:** jeśli parametr **Wymagany typ hasła** ma wartość **Alfanumeryczne**, wtedy to ustawienie określa minimalną liczbę zestawów znaków użytych w haśle. Są cztery zestawy znaków:
  - Małe litery
  - Wielkie litery
  - Symbole
  - Liczby

Im większa liczba zostanie podana dla tego ustawienia, tym bardziej skomplikowane hasła będą musieli tworzyć użytkownicy. W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli minimalna długość hasła jest większa niż osiem znaków lub minimalna liczba zestawów znaków jest większa niż dwa.

- **Liczba minut braku aktywności, zanim będzie wymagane hasło:** określa czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (w dniach):** wybierz liczbę dni, po których hasło użytkownika wygasa i należy utworzyć nowe.
- **Pamiętaj historię haseł:** używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.
- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.
- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownicy końcowi otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

**To ustawienie dotyczy tylko urządzeń z systemem Windows 10 Mobile.**

### <a name="encryption"></a>Szyfrowanie

- **Wymagaj szyfrowania na urządzeniu przenośnym:** ustaw tę opcję na wartość **Tak**, aby wymagać zaszyfrowania urządzenia w celu połączenia się z zasobami.



## <a name="device-health-settings"></a>Ustawienia kondycji urządzenia

- **Wymagaj, aby urządzenia były zgłaszane jako urządzenia o dobrej kondycji:** możesz ustawić regułę wymagającą od urządzeń z systemem **Windows 10 Mobile** zgłoszenia dobrej kondycji w nowych lub istniejących zasadach zgodności. Jeśli ustawienie jest włączone, urządzenia z systemem Windows 10 są oceniane za pośrednictwem usługi zaświadczania o kondycji (HAS, Health Attestation Service) dla następujących punktów danych:
  - **Funkcja BitLocker jest włączona:** po włączeniu funkcji BitLocker urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub zahibernowany. Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika oraz zapewnia, że komputer nie zostanie naruszony nawet wtedy, gdy zostanie pozostawiony bez nadzoru, zgubiony lub skradziony. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.
  - **Integralność kodu jest włączona:** integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci. Funkcja integralności kodu wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy lub czy plik systemowy został zmodyfikowany przez złośliwe oprogramowanie, które zostało uruchomione przez konto użytkownika z uprawnieniami administratora.
  - **Bezpieczny rozruch jest włączony:** po włączeniu funkcji bezpiecznego rozruchu system musi włączać się do fabrycznie zaufanego stanu. Ponadto po włączeniu funkcji bezpiecznego rozruchu podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, które są podpisami zaufanymi dla organizacji, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI sprawdza to, zanim pozwoli na uruchomienie komputera. Jeśli jakiekolwiek pliki zostały zmodyfikowane, co spowodowało uszkodzenie ich podpisu, system nie uruchomi się.

Aby uzyskać informacje o sposobie działania usługi HAS, zobacz [Zaświadczanie o kondycji CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Minimalna długość hasła:** — opcja obsługiwana w systemie Windows 8.1.

Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli **Minimalna długość hasła** jest większa niż 8 znaków lub **Minimalna liczba zestawów znaków** jest większa niż 2.

- **Wymagany typ hasła:** opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

Określ, czy użytkownicy muszą tworzyć hasła **alfanumeryczne**, czy też **numeryczne**.

- **Minimalna liczba zestawów znaków:** opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1. Jeśli parametr **Wymagany typ hasła** ma wartość **Alfanumeryczne**, wówczas to ustawienie określa minimalną liczbę zestawów znaków użytych w haśle. Są cztery zestawy znaków:
  - Małe litery
  - Wielkie litery
  - Symbole
  - Liczby: im większa liczba zostanie podana dla tego ustawienia, tym bardziej skomplikowane hasła będą musieli tworzyć użytkownicy.

W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem, jeśli **Minimalna długość hasła** jest większa niż 8 znaków lub **Minimalna liczba zestawów znaków** jest większa niż 2.

- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

Określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

Wybierz liczbę dni, po których hasło użytkownika wygasa i należy utworzyć nowe.

- **Pamiętaj historię haseł:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

Używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** — opcja obsługiwana w systemach Windows RT, Windows RT 8.1 i Windows 8.1.

Jeśli jest zaznaczona opcja **Pamiętaj historię haseł:**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.


## <a name="device-health-settings"></a>Ustawienia kondycji urządzenia

- **Wymagaj, aby urządzenia były zgłaszane jako urządzenia o dobrej kondycji:** — opcja obsługiwana na urządzeniach z systemem Windows 10. Można ustawić zasady, które będą wymagać od urządzeń z systemem Windows 10 zgłoszenia dobrej kondycji w nowych lub istniejących zasadach zgodności. Jeśli ustawienie jest włączone, urządzenia z systemem Windows 10 są oceniane za pośrednictwem usługi zaświadczania o kondycji (HAS, Health Attestation Service) dla następujących punktów danych:
  - **Funkcja BitLocker jest włączona:** po włączeniu funkcji BitLocker urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub zahibernowany. Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika oraz zapewnia, że komputer nie zostanie naruszony nawet wtedy, gdy zostanie pozostawiony bez nadzoru, zgubiony lub skradziony. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.
  - **Integralność kodu jest włączona:** integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci. Funkcja integralności kodu wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy lub czy plik systemowy został zmodyfikowany przez złośliwe oprogramowanie, które zostało uruchomione przez konto użytkownika z uprawnieniami administratora.
  - **Bezpieczny rozruch jest włączony:** po włączeniu funkcji bezpiecznego rozruchu system musi włączać się do fabrycznie zaufanego stanu. Ponadto po włączeniu funkcji bezpiecznego rozruchu podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, które są podpisami zaufanymi dla organizacji, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI sprawdza to, zanim pozwoli na uruchomienie komputera. Jeśli jakiekolwiek pliki zostały zmodyfikowane, co spowodowało uszkodzenie ich podpisu, system nie uruchomi się.
  - **Usługa wczesnej ochrony przed złośliwym kodem jest włączona:** usługa wczesnej ochrony przed złośliwym kodem zapewnia ochronę komputerów w sieci podczas uruchamiania i przed zainicjowaniem sterowników firm trzecich.

Aby uzyskać informacje o sposobie działania usługi HAS, zobacz [Zaświadczanie o kondycji CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** — opcja obsługiwana w systemach Windows 8.1 i Windows 10.

W tym miejscu podaj wersję w formacie główna.pomocnicza.kompilacja. Numer wersji musi odpowiadać wersji zwracanej przez polecenie ```winver```.

Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż określona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** — opcja obsługiwana w systemach Windows 8.1 i Windows 10.

Jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

Aby znaleźć wersję systemu operacyjnego do użycia w ustawieniach **Wymagana minimalna wersja systemu operacyjnego** i **Dozwolona maksymalna wersja systemu operacyjnego**, uruchom polecenie **winver** w wierszu polecenia. Polecenie winver zwraca zgłoszoną wersję systemu operacyjnego.+

- Komputery z systemem Windows 8.1 zwracają wersję **3**. Jeśli ustawiono regułę wersji systemu operacyjnego Windows na wartość Windows 8.1, urządzenie jest zgłaszane jako niezgodne nawet wtedy, gdy działa na nim system Windows 8.1.
- W przypadku komputerów z systemem operacyjnym Windows 10 należy ustawić wersję &quot;10.0&quot; z dołączonym numerem kompilacji systemu operacyjnego zwróconym przez polecenie winver.

<!--- ## Next steps

[How to monitor device compliance](monitor-device-compliance.md)--->

