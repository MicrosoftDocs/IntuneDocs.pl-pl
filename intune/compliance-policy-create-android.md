---
title: Tworzenie zasad zgodności urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Można tworzyć i konfigurować zasady zgodności w usłudze Microsoft Intune dla urządzeń z systemem Android. Można wybrać, czy zezwolić na dostęp urządzeniom z wyłączonymi zabezpieczeniami systemu, ustawić dopuszczalny poziom zagrożenia, sprawdzić, czy jest zainstalowana aplikacja Google Play, wprowadzić minimalną i maksymalną wersję systemu operacyjnego, określić wymagania dotyczące hasła i zezwalać na aplikacje ładowane bezpośrednio.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cb5fc7256e68b8ea10ba1b3ddd7cfe6ed44bd544
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180616"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Dodawanie zasad zgodności dla urządzeń z systemem Android w usłudze Intune

Zasady zgodności urządzeń w usłudze Intune dla systemu Android określają reguły i ustawienia, które urządzenia z systemem Android muszą spełnić, aby zostały uznane za zgodne. Można je wykorzystać do stosowania [dostępu warunkowego](conditional-access.md), aby zezwolić na dostęp do zasobów organizacji lub go zablokować. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. 

Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

Ten temat zawiera listę ustawień, których możesz używać w zasadach zgodności dla urządzeń z systemem Android.

## <a name="non-compliance-and-conditional-access"></a>Brak zgodności i dostęp warunkowy

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

--------------------

|**Ustawienie zasad**| **System Android 4.0 lub nowszy, system Samsung Knox Standard 4.0 lub nowszy** |
| --- | ----|
| **Konfiguracja kodu PIN lub hasła** |  Poddane kwarantannie |
| **Szyfrowanie urządzenia** | Poddane kwarantannie |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie) |
| **profil e-mail** | Nie dotyczy |
| **Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** |   Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** | Nie dotyczy |

--------------------------

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. Na przykład użytkownik jest zmuszony do ustawienia kodu PIN.

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. Na przykład urządzenia z systemem Android nie zmuszają użytkownika do szyfrowania urządzeń. Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

  - Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
  - Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. W polu **Platforma** wybierz opcję **Android**. 
5. Wybierz pozycję **Konfiguruj ustawienia**. Wprowadź wartości ustawień **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu** zgodnie z opisem w tym artykule.

## <a name="device-health"></a>Device health

- **Urządzenia z odblokowanym dostępem**: wybierz opcję **Blokuj**, aby oznaczyć urządzenia z dostępem do konta root (w przypadku których wykonano jailbreak) jako niezgodne. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
- **Skonfigurowano usługi Google Play**: **Wymagaj** zainstalowania i włączenia aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Aktualny dostawca zabezpieczeń**: **Wymagaj**, aby zaktualizowany dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Skanowanie aplikacji pod kątem zagrożeń**: **Wymagaj** włączenia w systemie Android funkcji **Weryfikuj aplikacje**. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  > [!NOTE]
  > Na platformie systemu Android w starszej wersji ta funkcja jest ustawieniem zgodności. Usługa Intune może tylko sprawdzić, czy to ustawienie zostało włączone na poziomie urządzenia.

- **Zaświadczenie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowane** (wartość domyślna): ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko cyfry, czy też ma być wymagana kombinacja cyfr i innych znaków. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne** (wartość domyślna)
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry (np. `1111` albo `1234`) są niedozwolone.
  - **Co najmniej alfabetyczne** 
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę ostatnich haseł, których ponowne użycie nie jest możliwe. To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu** (Android 4.0 i nowsze wersje lub KNOX 4.0 i nowsze wersje): wybierz opcję **Wymagaj**, aby zaszyfrować na urządzeniach magazyn danych. Urządzenia są szyfrowane po wybraniu ustawienia **Wymagaj hasła do odblokowania urządzeń przenośnych**. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Blokuj aplikacje z nieznanych źródeł**: **Blokuj** urządzenia z włączonymi źródłami „Zabezpieczenia > Nieznane źródła” (obsługiwane w systemach Android od wersji 4.0 do wersji 7.x, nieobsługiwane w systemach Android 8.0 i nowszych). W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  Aby ładować aplikacje bezpośrednio, nieznane źródła muszą być dozwolone. W przypadku braku bezpośredniego ładowania aplikacji Android ustaw dla tej funkcji wartość **Blokuj**, aby włączyć te zasady zgodności. 

  > [!IMPORTANT]
  > Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Blokuj aplikacje z nieznanych źródeł**. Te zasady zgodności należy wymuszać tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

- **Integralność środowiska uruchomieniowego aplikacji Portal firmy**: wybierz opcję **Wymagaj**, aby sprawdzać, czy aplikacja Portal firmy spełnia wszystkie poniższe wymagania:

  - Ma zainstalowane domyślne środowisko uruchomieniowe
  - Jest poprawnie podpisana
  - Nie jest w trybie debugowania
  - Została zainstalowana ze znanego źródła

  W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

- **Blokuj debugowanie USB na urządzeniu** (Android 4.2 i nowsze): wybierz pozycję **Blokuj**, aby uniemożliwić używanie funkcji debugowania USB na urządzeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Minimalny poziom poprawki bezpieczeństwa** (Android 6.0 lub nowszy): wybierz poziom najstarszej poprawki zabezpieczeń, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie `YYYY-MM-DD`.
- **Ograniczone aplikacje**: wprowadź wartości **Nazwa aplikacji** oraz **Identyfikator pakietu aplikacji** dla aplikacji, które mają być ograniczone. Wybierz pozycję **Dodaj**. Urządzenie, na którym zainstalowano co najmniej jedną ograniczoną aplikację, jest oznaczane jako niezgodne.

Po zakończeniu wybierz przycisk **OK** > **OK**, aby zapisać zmiany.

## <a name="locations"></a>Lokalizacje

W swoich zasadach dokonuj wyboru spośród istniejących lokalizacji. Nie masz jeszcze lokalizacji? Wskazówki możesz znaleźć w temacie [Korzystanie z lokalizacji (ogrodzenia sieci) w usłudze Intune](use-network-locations.md).

1. Wybierz pozycję **Lokalizacje**.
2. Na liście zaznacz swoją lokalizację, a następnie wybierz pozycję **Wybierz**.
3. **Zapisz** zasady.

## <a name="actions-for-noncompliance"></a>Akcje w przypadku niezgodności

Wybierz pozycję **Akcje w przypadku niezgodności**. Domyślna akcja natychmiast oznacza urządzenie jako niezgodne.

Ten harmonogram oznaczania urządzenia jako niezgodnego możesz zmienić (np. oznaczać je po jednym dniu). Możesz również skonfigurować drugą akcję, która wysyła wiadomość e-mail do użytkownika, gdy urządzenie nie jest zgodne.

Sekcja dotycząca [dodawania akcji dla niezgodnych urządzeń](actions-for-noncompliance.md) zawiera więcej informacji, między innymi o tworzeniu wiadomości e-mail z powiadomieniem do użytkowników.

Na przykład używasz funkcji Lokalizacje i dodasz lokalizację w zasadach zgodności. Domyślna akcja w przypadku niezgodności jest stosowana, gdy zostanie wybrana co najmniej jedna lokalizacja. Jeśli urządzenie nie jest połączone z wybranymi lokalizacjami, jest natychmiast uznawane za niezgodne. Użytkownikom można przyznać okres prolongaty, np. jeden dzień.

## <a name="scope-tags"></a>Tagi zakresu

Tagi zakresu to doskonały sposób przypisywania zasad do określonych grup, np. Sprzedaż, Inżynieria, Kadry itd. Tagi zakresu można dodać do zasad zgodności. Zobacz [Używanie tagów zakresu do filtrowania zasad](scope-tags.md). 

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Po utworzeniu zasady nie działają, dopóki nie zostaną przypisane. Aby przypisać zasady: 

1. Wybierz skonfigurowane przez siebie zasady. Dostęp do istniejących zasad można uzyskać po wybraniu pozycji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie wybierz opcję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz opcję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, będą oceniane pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)  
[Ustawienia zasad zgodności dla rozwiązania Android Enterprise](compliance-policy-create-android-for-work.md)
