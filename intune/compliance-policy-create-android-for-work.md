---
title: Tworzenie zasad zgodności rozwiązania Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Twórz lub konfiguruj zasady zgodności urządzeń usługi Microsoft Intune dla urządzeń z rozwiązaniem Android Enterprise albo urządzeń z profilami służbowymi. Można wybrać, czy zezwolić na dostęp urządzeniom z wyłączonymi zabezpieczeniami systemu, ustawić dopuszczalny poziom zagrożenia, sprawdzić, czy jest zainstalowana aplikacja Google Play, wprowadzić minimalną i maksymalną wersję systemu operacyjnego, określić wymagania dotyczące hasła i zezwalać na aplikacje ładowane bezpośrednio.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: aab8208865fb072170a670d1da25e7f02448c38f
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642867"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Dodawanie zasad zgodności dla urządzeń z rozwiązaniem Android Enterprise w usłudze Intune

Zasady zgodności urządzeń to kluczowa funkcja w przypadku ochrony zasobów organizacji za pomocą usługi Intune. W usłudze Intune możesz utworzyć reguły, które muszą być spełniane przez urządzenia, i ustawienia, które muszą być na nich określone, aby można je było uznać za zgodne, np. długość hasła. Jeśli urządzenie nie jest zgodne, możesz wtedy zablokować dostęp do danych i zasobów przy użyciu [dostępu warunkowego](conditional-access.md). 

Ponadto możesz uzyskiwać raporty dotyczące urządzeń i podejmować działania w przypadku braku zgodności, np. wysłać wiadomość e-mail z powiadomieniem do użytkownika. Aby dowiedzieć się więcej na temat zasad zgodności urządzeń i wymagań wstępnych, zobacz temat [Wprowadzenie do zgodności urządzeń](device-compliance-get-started.md).

Ten artykuł zawiera listę ustawień, których możesz używać w zasadach zgodności dla urządzeń z rozwiązaniem Android Enterprise.

## <a name="non-compliance-and-conditional-access"></a>Brak zgodności i dostęp warunkowy

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

--------------------------

|**ustawienie zasad**| **Profil rozwiązania Android Enterprise** |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** |  Poddane kwarantannie |
| **Szyfrowanie urządzenia** |  Poddane kwarantannie |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie) |
| **profil e-mail** | Nie dotyczy |
| **Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** |Nie dotyczy |

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. Na przykład użytkownik jest zmuszony do ustawienia kodu PIN.

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. Na przykład urządzenia z systemem Android nie zmuszają użytkownika do szyfrowania urządzeń. Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

  - Jeśli użytkownik podlega zasadom dostępu warunkowego, urządzenie zostanie zablokowane.
  - Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. W polu **Platforma** wybierz opcję **Android enterprise**. 
5. Wybierz pozycję **Konfiguruj ustawienia**. Wprowadź wartości ustawień **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu** zgodnie z opisem w tym artykule.

## <a name="device-health"></a>Device health

- **Urządzenia z odblokowanym dostępem**: wybierz opcję **Blokuj**, aby oznaczyć urządzenia z odblokowanym dostępem (w przypadku których wykonano jailbreak) jako niezgodne. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:
  - **Zabezpieczone**: ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
- **Skonfigurowano Usługi Google Play**: **Wymagaj** zainstalowania i włączenia aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Aktualny dostawca zabezpieczeń**: **Wymagaj**, aby aktualny dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Zaświadczanie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowane** (wartość domyślna): ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

#### <a name="threat-scan-on-apps"></a>Skanowanie aplikacji pod kątem zagrożeń

Na urządzeniach z rozwiązaniem Android Enterprise ustawienie **Skanowanie aplikacji pod kątem zagrożeń** to zasady konfiguracji. Zobacz [Ustawienia ograniczeń urządzenia z rozwiązaniem Android Enterprise](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Ustawienia właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia i w konsekwencji uzyskanie dostępu do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. W takiej sytuacji użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: pozycja **Wymagaj** wymusza na użytkownikach wprowadzanie hasła podczas uzyskiwania dostępu do swoich urządzeń. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. To ustawienie jest stosowane na poziomie urządzenia. Jeśli hasło ma być wymagane tylko na poziomie profilu służbowego, należy użyć zasad konfiguracji. Zobacz [Ustawienia konfiguracji urządzenia z systemem Android Enterprise](device-restrictions-android-for-work.md).
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko cyfry, czy też ma być wymagana kombinacja cyfr i innych znaków. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne** (wartość domyślna)
  - **Wartość liczbowa/złożona**
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których wygasa hasło i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę ostatnich haseł, których nie można użyć ponownie. To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**: wybierz pozycję **Wymagaj**, aby szyfrować magazyn danych na urządzeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. 

  Nie musisz konfigurować tego ustawienia, ponieważ urządzenia z profilami służbowymi systemu Android wymuszają szyfrowanie.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Blokuj aplikacje z nieznanych źródeł**: **Blokuj** urządzenia z włączonymi źródłami „Zabezpieczenia > Nieznane źródła” (obsługiwane w systemach Android od wersji 4.0 do wersji 7.x, nieobsługiwane w systemach Android 8.0 i nowszych). W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  Aby ładować aplikacje bezpośrednio, nieznane źródła muszą być dozwolone. W przypadku braku bezpośredniego ładowania aplikacji Android ustaw dla tej funkcji wartość **Blokuj**, aby włączyć te zasady zgodności. 

  > [!IMPORTANT]
  > Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Blokuj aplikacje z nieznanych źródeł**. Te zasady zgodności należy wymuszać tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

  Nie musisz konfigurować tego ustawienia, ponieważ urządzenia z profilami służbowymi systemu Android zawsze ograniczają instalację z nieznanych źródeł.

- **Integralność środowiska uruchomieniowego aplikacji Portal firmy**: wybierz opcję **Wymagaj**, aby sprawdzać, czy aplikacja Portal firmy spełnia wszystkie poniższe wymagania:

  - Ma zainstalowane domyślne środowisko uruchomieniowe
  - Jest poprawnie podpisana
  - Nie jest w trybie debugowania
  - Została zainstalowana ze znanego źródła

  W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

- **Blokuj debugowanie USB na urządzeniu**: wybierz opcję **Blokuj**, aby zablokować używanie funkcji debugowania USB na urządzeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  Nie musisz konfigurować tego ustawienia, ponieważ debugowanie USB jest wyłączane na urządzeniach z profilami służbowymi systemu Android.

- **Minimalny poziom poprawki bezpieczeństwa**: wybierz poziom najstarszej poprawki bezpieczeństwa, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie *RRRR-MM-DD*.

Po zakończeniu wybierz przycisk **OK** > **OK**, aby zapisać zmiany.

## <a name="actions-for-noncompliance"></a>Akcje w przypadku niezgodności

Wybierz pozycję **Akcje w przypadku niezgodności**. Domyślna akcja natychmiast oznacza urządzenie jako niezgodne.

Ten harmonogram oznaczania urządzenia jako niezgodnego możesz zmienić (np. oznaczać je po jednym dniu). Możesz również skonfigurować drugą akcję, która wysyła wiadomość e-mail do użytkownika, gdy urządzenie nie jest zgodne.

Sekcja dotycząca [dodawania akcji dla niezgodnych urządzeń](actions-for-noncompliance.md) zawiera więcej informacji, między innymi o tworzeniu wiadomości e-mail z powiadomieniem do użytkowników.

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
[Ustawienia zasad zgodności dla systemu Android](compliance-policy-create-android.md)
