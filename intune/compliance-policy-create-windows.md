---
title: Tworzenie zasad zgodności urządzeń z systemem Windows w usłudze Microsoft Intune — Azure | Microsoft Intune
description: 'Utwórz lub skonfiguruj zasady zgodności urządzenia w usłudze Microsoft Intune w przypadku urządzeń z systemem Windows Phone 8.1, Windows 8.1 i nowszym oraz Windows 10 i nowszym. Sprawdź zgodność następujących elementów: minimalna i maksymalna wersja systemu operacyjnego, ustawianie ograniczeń i długości hasła, wymaganie funkcji BitLocker, sprawdzanie rozwiązań antywirusowych innych firm, ustawianie dopuszczalnego poziomu zagrożenia i włączanie szyfrowania w magazynie danych, z uwzględnieniem urządzeń Surface Hub i systemu Windows Holographic for Business.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: e0772f4e577f6660926f6827a7fda8e51bcdd280
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182962"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Dodawanie zasad zgodności urządzeń z systemem Windows w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń w usłudze Intune dla systemu Windows określają reguły i ustawienia, które urządzenia z systemem Windows muszą spełnić, aby zostały uznane za zgodne. Można je wykorzystać do dostępu warunkowego, aby zezwolić na dostęp do zasobów firmy lub go zablokować. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

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

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. W obszarze **Platforma** wybierz pozycję **Windows Phone 8.1**, **Windows 8.1 i nowsze** lub **Windows 10 i nowsze**.
6. Wybierz pozycję **Konfiguruj ustawienia** i wprowadź wartości ustawień **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu**. Po zakończeniu wybierz kolejno przycisk **OK** i pozycję **Utwórz**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="windows-81-devices-policy-settings"></a>Ustawienia zasad dla urządzeń z systemem Windows 8.1

Te ustawienia zasad są stosowane do urządzeń z następującymi platformami:

- Windows Phone 8,1
- Windows 8.1 i nowsze

### <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

Komputery z systemem Windows 8.1 zwracają wersję **3**. Jeśli ustawiono regułę wersji systemu operacyjnego Windows na wartość Windows 8.1, urządzenie jest zgłaszane jako niezgodne nawet wtedy, gdy działa na nim system Windows 8.1.

### <a name="system-security"></a>Zabezpieczenia systemu

#### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.

  W przypadku urządzeń z systemem Windows, które są dostępne przy użyciu konta Microsoft, sprawdzanie zasad zgodności zakończy się niepowodzeniem:
  - Jeśli minimalna długość hasła jest większa niż osiem znaków
  - Lub jeśli minimalna liczba zestawów znaków jest większa niż dwa

- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
  
  - **Liczba znaków innych niż alfanumeryczne w haśle**: jeśli pozycja **Wymagany typ hasła** została ustawiona na wartość **Alfanumeryczne**, to ustawienie określa minimalną wymaganą liczbę zestawów znaków do użycia w haśle. Są cztery zestawy znaków:
    - Małe litery
    - Wielkie litery
    - Symbole
    - Liczby

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika. W przypadku urządzeń z systemem Windows, do których uzyskuje się dostęp przy użyciu konta Microsoft, sprawdzanie zasad zgodności kończy się niepowodzeniem, jeśli minimalna długość hasła jest większa niż osiem znaków lub minimalna liczba zestawów znaków jest większa niż dwa.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

#### <a name="encryption"></a>Szyfrowanie

- **Wymagaj szyfrowania na urządzeniu przenośnym**: wartość **Wymagaj** oznacza, że urządzenie musi zostać zaszyfrowane w celu połączenia się z zasobami magazynu danych.

## <a name="windows-10-and-later-policy-settings"></a>Ustawienia zasad dla systemu Windows 10 i nowszych

### <a name="device-health"></a>Device health

- **Wymagaj funkcji BitLocker**: po włączeniu funkcji BitLocker urządzenie może chronić dane przechowywane na dysku przed nieautoryzowanym dostępem, gdy system jest wyłączony lub przechodzi w stan hibernacji. Szyfrowanie dysków funkcją BitLocker szyfruje wszystkie dane przechowywane na woluminie systemu operacyjnego Windows. Funkcja BitLocker używa modułu TPM do ochrony systemu operacyjnego i danych użytkownika. Zapewnia ona także, że komputer nie zostanie naruszony nawet wtedy, gdy zostanie zgubiony, skradziony lub pozostawiony bez nadzoru. Jeśli komputer jest wyposażony w zgodny moduł TPM, funkcja BitLocker używa go do zablokowania kluczy szyfrowania służących do ochrony danych. W związku z tym klucze będą niedostępne, dopóki moduł TPM nie zweryfikuje stanu komputera.
- **Wymagaj włączenia bezpiecznego rozruchu w urządzeniu**: po włączeniu funkcji bezpiecznego rozruchu system musi włączać się do fabrycznie zaufanego stanu. Ponadto po włączeniu funkcji bezpiecznego rozruchu podstawowe składniki używane do uruchamiania urządzenia muszą mieć prawidłowe podpisy kryptograficzne, które są podpisami zaufanymi dla organizacji, która wyprodukowała urządzenie. Oprogramowanie układowe UEFI sprawdza podpis, zanim pozwoli na uruchomienie komputera. Jeśli jakiekolwiek pliki zostały zmodyfikowane, co spowodowało uszkodzenie ich podpisu, system nie uruchomi się.

  > [!NOTE]
  > Ustawienie **Wymagaj włączenia bezpiecznego rozruchu na urządzeniu** jest obsługiwane na urządzeniach z modułami TPM 1.2 i 2.0. W przypadku urządzeń, które nie obsługują modułu TPM 2.0 ani nowszego, stan zasad w usłudze Intune ma wartość **Niezgodne**. Jest to ograniczenie usługi [zaświadczania o kondycji urządzenia](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation) w systemie Windows 10.

- **Wymagaj integralności kodu**: integralność kodu jest funkcją, która weryfikuje integralność pliku sterownika lub pliku systemowego zawsze wtedy, gdy jest ładowany do pamięci. Funkcja integralności kodu wykrywa, czy do jądra jest ładowany niepodpisany plik sterownika lub plik systemowy. Sprawdza także, czy plik systemowy został zmodyfikowany przez złośliwe oprogramowanie uruchomione przez konto użytkownika z uprawnieniami administratora.

Aby uzyskać szczegółowe informacje o sposobie działania usługi HAS, zobacz [Zaświadczanie o kondycji CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).

### <a name="device-properties"></a>Właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: wprowadź minimalną dozwoloną wersję w formacie numerycznym **główna.pomocnicza.kompilacja.aktualizacja_zbiorcza**. Aby uzyskać prawidłową wartość, otwórz wiersz polecenia i wpisz `ver`. Polecenie `ver` zwraca wersję w następującym formacie:

  `Microsoft Windows [Version 10.0.17134.1]`

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż określona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Maksymalna wersja systemu operacyjnego**: wprowadź maksymalną dozwoloną wersję w formacie numerycznym **główna.pomocnicza.kompilacja.poprawka**. Aby uzyskać prawidłową wartość, otwórz wiersz polecenia i wpisz `ver`. Polecenie `ver` zwraca wersję w następującym formacie:

  `Microsoft Windows [Version 10.0.17134.1]`

  Jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

- **Wymagana minimalna wersja systemu operacyjnego dla urządzeń przenośnych**: wprowadź minimalną dozwoloną wersję w formacie numerycznym główna.pomocnicza.kompilacja.

  Jeśli urządzenie ma wcześniejszą wersję systemu operacyjnego niż określona, zostanie zgłoszone jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Wymagana maksymalna wersja systemu operacyjnego dla urządzeń przenośnych**: wprowadź maksymalną dozwoloną wersję w formacie numerycznym główna.pomocnicza.kompilacja.

  Jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

- **Prawidłowe kompilacje systemów operacyjnych**: wprowadź zakres dopuszczalnych wersji systemu operacyjnego, w tym wersję minimalną i maksymalną. Możesz również **wyeksportować** listę plików wartości rozdzielanych przecinkami (CSV), która będzie zawierać dopuszczalne numery kompilacji systemu operacyjnego.

### <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

#### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Typ hasła**: określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).

  - **Liczba znaków innych niż alfanumeryczne w haśle**: jeśli pozycja **Wymagany typ hasła** została ustawiona na wartość **Alfanumeryczne**, to ustawienie określa minimalną wymaganą liczbę zestawów znaków do użycia w haśle. Są cztery zestawy znaków:
    - Małe litery
    - Wielkie litery
    - Symbole
    - Liczby

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.
- **Wymagaj hasła, gdy urządzenie wraca ze stanu bezczynności (Mobile i Holographic)**: wymuszaj wprowadzanie haseł przez użytkowników za każdym razem, gdy urządzenie wraca ze stanu bezczynności.

#### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu**: wybierz pozycję **Wymagaj**, aby szyfrować magazyn danych na urządzeniach.

  > [!NOTE]
  > Ustawienie **Szyfrowanie magazynu danych na urządzeniu** ogólnie sprawdza, czy na urządzeniu jest stosowane szyfrowanie. Aby uzyskać bardziej niezawodne ustawienie szyfrowania, rozważ użycie opcji **Wymagaj funkcji BitLocker**, która korzysta z zaświadczania o kondycji urządzenia systemu Windows w celu weryfikowania stanu funkcji BitLocker na poziomie modułu TPM.

#### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Oprogramowanie antywirusowe**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antywirusowych zarejestrowanych w Centrum zabezpieczeń systemu Windows, na przykład rozwiązań firmy Symantec i usługi Windows Defender. W przypadku wybrania ustawienia **Nieskonfigurowane** usługa Intune nie będzie wykonywać sprawdzania w poszukiwaniu jakichkolwiek rozwiązań antywirusowych zainstalowanych na urządzeniu.
- **Program antyszpiegowski**: w przypadku wybrania ustawienia **Wymagaj** możesz sprawdzić zgodność przy użyciu rozwiązań antyszpiegowskich zarejestrowanych w Centrum zabezpieczeń systemu Windows, na przykład rozwiązań firmy Symantec i usługi Windows Defender. W przypadku wybrania ustawienia **Nieskonfigurowane** usługa Intune nie będzie wykonywać sprawdzania w poszukiwaniu jakichkolwiek rozwiązań antyszpiegowskich zainstalowanych na urządzeniu.

### <a name="windows-defender-atp"></a>Zaawansowana ochrona przed zagrożeniami w usłudze Windows Defender

- **Wymagaj, aby urządzenie było na poziomie niższym lub równym ocenie ryzyka maszyny**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z usług ochrony przed zagrożeniami jako warunek zgodności. Wybierz maksymalny dozwolony poziom zagrożenia:
  - **Czyste**: ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające jakikolwiek poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
  
  Aby skonfigurować usługę Windows Defender ATP (Advanced Threat Protection) jako usługę do ochrony przed zagrożeniami, zobacz [Włączanie usługi Windows Defender ATP z dostępem warunkowym](advanced-threat-protection.md).

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

System Windows Holographic for Business używa platformy **Windows 10 i nowsze**. System Windows Holographic for Business obsługuje następujące ustawienie:

- **Zabezpieczenia systemu** > **Szyfrowanie** > **Szyfrowanie magazynu danych na urządzeniu**.

Aby sprawdzić szyfrowanie urządzenia na urządzeniu Microsoft HoloLens, zobacz [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) (Weryfikowanie szyfrowania urządzenia).

## <a name="surface-hub"></a>Surface Hub
Urządzenie Surface Hub używa platformy **Windows 10 i nowsze**. Urządzenia Surface Hub są obsługiwane pod kątem zgodności i dostępu warunkowego. Aby włączyć te funkcje na urządzeniach Surface Hub, zalecamy [włączanie automatycznej rejestracji systemu Windows 10](windows-enroll.md) w usłudze Intune (wymaga to również użycia usługi Azure Active Directory (AAD)) i ustawianie urządzeń Surface Hub jako docelowych grup urządzeń. Urządzenia Surface Hub należy przyłączyć do usługi Azure Active Directory, aby funkcje zgodności i dostępu warunkowego działały.

Zobacz temat [Konfigurowanie rejestracji dla urządzeń z systemem Windows](windows-enroll.md) w celu uzyskania wytycznych.

## <a name="assign-user-or-device-groups"></a>Przypisywanie grup użytkowników lub urządzeń

1. Wybierz skonfigurowane przez siebie zasady. Dostęp do istniejących zasad można uzyskać po wybraniu pozycji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie pozycję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure AD.
3. Wybierz pozycję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników lub urządzeń, których mają dotyczyć te zasady, a następnie wybierz pozycję **Zapisz**, aby wdrożyć zasady.

Zasady zostały zastosowane. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)
