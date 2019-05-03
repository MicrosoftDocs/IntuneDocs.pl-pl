---
title: Ustawienia urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetlenie listy wszystkich ustawień których można użyć, gdy ustawienia zgodności dla urządzeń z system android dla firm w programie Microsoft Intune. Ustaw reguły hasła, wybierz wersję systemu operacyjnego minimalnej lub maksymalnej, ograniczyć określone aplikacje, uniemożliwić ponowne używanie haseł i innych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16db0acab84a1095c40e9a92648c75c2581187cd
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423564"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia systemu android Enterprise na potrzeby oznaczania urządzenia jako zgodne lub niezgodne, przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wymieniono i opisano ustawienia zgodności różnych, które można skonfigurować na urządzeniach przedsiębiorstwa z systemem Android w usłudze Intune. W ramach rozwiązania do zarządzania (urządzeniami przenośnymi MDM) urządzenia przenośnego te ustawienia służą do oznaczania urządzenia z odblokowanym dostępem (których zdjęto zabezpieczenia systemu) jako niezgodne, Ustaw dozwolony poziom zagrożenia, należy włączyć Google Play Protect i nie tylko.

Ta funkcja ma zastosowanie do:

- Android Enterprise

Jako administrator usługi Intune należy użyć tych ustawień zgodności w celu ochrony zasobów organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **Android enterprise**.

## <a name="device-health"></a>Device health

- **Urządzenia z odblokowanym dostępem**: wybierz opcję **Blokuj**, aby oznaczyć urządzenia z dostępem do konta root (w przypadku których wykonano jailbreak) jako niezgodne. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

### <a name="google-play-protect"></a>Ochrona sklepu Google Play

- **Skonfigurowano usługi Google Play**: **Wymagaj** zainstalowania i włączenia aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Aktualny dostawca zabezpieczeń**: **Wymagaj**, aby zaktualizowany dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Zaświadczenie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowane** (wartość domyślna): ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

> [!NOTE]
> Na urządzeniach z systemami przedsiębiorstwa z systemem Android **skanowania zagrożeń w aplikacjach** jest zasad konfiguracji urządzeń. Przy użyciu zasad konfiguracji, Administratorzy mogą włączać ustawienia na urządzeniu. Zobacz [Ustawienia ograniczeń urządzenia z rozwiązaniem Android Enterprise](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Ustawienia właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia i w konsekwencji uzyskanie dostępu do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. W takiej sytuacji użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. To ustawienie jest stosowane na poziomie urządzenia. Jeśli hasło ma być wymagane tylko na poziomie profilu służbowego, należy użyć zasad konfiguracji. Zobacz [Ustawienia konfiguracji urządzenia z systemem Android Enterprise](device-restrictions-android-for-work.md).
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko cyfry, czy też ma być wymagana kombinacja cyfr i innych znaków. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne** (wartość domyślna)
  - **Wartość liczbowa/złożona**
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę ostatnich haseł, których ponowne użycie nie jest możliwe. To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu**: wybierz pozycję **Wymagaj**, aby szyfrować magazyn danych na urządzeniach. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. 

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

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

- [Dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md) i [za pomocą tagów zakresu zasad filtr](scope-tags.md).
- [Monitorowanie zasad zgodności](compliance-policy-monitor.md).
- [Ustawienia zasad zgodności dla urządzeń z systemem Android](compliance-policy-create-android.md)
