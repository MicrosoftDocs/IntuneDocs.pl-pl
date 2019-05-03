---
title: Tworzenie zasad zgodności urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetlenie listy wszystkich ustawień których można użyć, gdy ustawienia zgodności dla urządzeń z systemem Android w programie Microsoft Intune. Ustaw reguły hasła, wybierz wersję systemu operacyjnego minimalnej lub maksymalnej, ograniczyć określone aplikacje, uniemożliwić ponowne używanie haseł i innych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7670af46657fed048bfe10b8659eae6d45db7620
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423581"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia systemu android na potrzeby oznaczania urządzenia jako zgodne lub niezgodne, przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wymieniono i opisano ustawienia zgodności różnych, które można skonfigurować na urządzeniach z systemem Android w usłudze Intune. W ramach rozwiązania do zarządzania (urządzeniami przenośnymi MDM) urządzenia przenośnego te ustawienia służą do oznaczania urządzenia z odblokowanym dostępem (których zdjęto zabezpieczenia systemu) jako niezgodne, Ustaw dozwolony poziom zagrożenia, należy włączyć Google Play Protect i nie tylko.

Ta funkcja ma zastosowanie do:

- Android

Jako administrator usługi Intune należy użyć tych ustawień zgodności w celu ochrony zasobów organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **Android**.

## <a name="device-health"></a>Device health

- **Urządzenia z odblokowanym dostępem**: wybierz opcję **Blokuj**, aby oznaczyć urządzenia z dostępem do konta root (w przypadku których wykonano jailbreak) jako niezgodne. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

### <a name="google-play-protect"></a>Ochrona sklepu Google Play

- **Skonfigurowano usługi Google Play**: **Wymagaj** zainstalowania i włączenia aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Aktualny dostawca zabezpieczeń**: **Wymagaj**, aby zaktualizowany dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Skanowanie aplikacji pod kątem zagrożeń**: **Wymagaj** włączenia w systemie Android funkcji **Weryfikuj aplikacje**. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  > [!NOTE]
  > Na platformie systemu Android w starszej wersji ta funkcja jest ustawieniem zgodności. Usługa Intune może tylko sprawdzić, czy to ustawienie zostało włączone na poziomie urządzenia.

- **Zaświadczenie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowane** (wartość domyślna): ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

> [!NOTE]
> Aby skonfigurować ustawienia usługi Google Play Protect wiadomości przy użyciu zasad ochrony aplikacji, zobacz [ustawienia zasad ochrony aplikacji usługi Intune](app-protection-policy-settings-android.md#conditional-launch) w systemie Android.

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

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

## <a name="locations"></a>Lokalizacje:

W zasadach możesz wymusić zgodność z przepisami według lokalizacji urządzenia. Wybierz z istniejących lokalizacji. Nie masz jeszcze lokalizacji? Wskazówki możesz znaleźć w temacie [Korzystanie z lokalizacji (ogrodzenia sieci) w usłudze Intune](use-network-locations.md).

1. Wybierz **lokalizacje** > **wybierz lokalizacje**.
2. Z listy, sprawdź swoją lokalizację > **wybierz**.
3. **Zapisz** zasady.

## <a name="next-steps"></a>Następne kroki

- [Dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md) i [za pomocą tagów zakresu zasad filtr](scope-tags.md).
- [Monitorowanie zasad zgodności](compliance-policy-monitor.md).
- [Ustawienia zasad zgodności dla rozwiązania Android Enterprise](compliance-policy-create-android-for-work.md)
