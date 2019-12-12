---
title: Ustawienia zgodności dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem Android w usłudze Microsoft Intune. Możesz między innymi ustawić reguły dotyczące haseł, wybrać minimalną lub maksymalną wersję systemu operacyjnego, ograniczyć określone aplikacje czy zablokować ponowne używanie haseł.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8efb9dcf9129375252b5d9a7d1e6255dce39625c
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73801409"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem Android umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem Android za pomocą usługi Intune. Możesz stosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi oznaczać urządzenia z odblokowanym dostępem do konta root lub zdjętymi zabezpieczeniami systemu jako niezgodne, określać dozwolony poziom zagrożenia, czy włączać funkcję Google Play Protect.

Ta funkcja ma zastosowanie do:

- Administrator urządzenia z systemem Android

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W obszarze **platforma**wybierz pozycję **administrator urządzenia z systemem Android**.

## <a name="device-health"></a>Kondycja urządzenia

- **Urządzenia z odblokowanym dostępem**:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Blokuj** — urządzenia z odblokowanym dostępem do konta root (ze zdjętymi zabezpieczeniami systemu) są oznaczane jako niezgodne.

- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**:

  Użyj tego ustawienia, aby uzyskać ocenę ryzyka z podłączonej usługi mobilnej ochrony przed zagrożeniami jako warunek zgodności.
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności. 
  - **Zabezpieczone** — ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski** — urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni** — urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** — ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

### <a name="google-play-protect"></a>Funkcja Google Play Protect

- **Skonfigurowano Usługi Google Play**:

  Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google.

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.  
  - **Wymagaj** — wymagane jest zainstalowanie i włączenie aplikacji usług Google Play.  

- **Aktualny dostawca zabezpieczeń**:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — wymagane jest, aby aktualny dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach.

- **Skanowanie aplikacji pod kątem zagrożeń**:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — wymaganie włączenia funkcji **Weryfikuj aplikacje** w systemie Android.

  > [!NOTE]
  > Na platformie systemu Android w starszej wersji ta funkcja jest ustawieniem zgodności. Usługa Intune może tylko sprawdzić, czy to ustawienie zostało włączone na poziomie urządzenia.

- **Zaświadczanie urządzeń SafetyNet**:

  wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

> [!NOTE]
> Aby skonfigurować ustawienia funkcji Google Play Protect za pomocą zasad ochrony aplikacji, zobacz [Ustawienia zasad ochrony aplikacji usługi Intune](../apps/app-protection-policy-settings-android.md#conditional-launch) dla systemu Android.

## <a name="device-properties"></a>Właściwości urządzenia

### <a name="operating-system-version"></a>Wersja systemu operacyjnego 

- **Minimalna wersja systemu operacyjnego**:

  jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

  *Domyślnie żadna wersja nie jest skonfigurowana*.

- **Maksymalna wersja systemu operacyjnego**:

  jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

  *Domyślnie żadna wersja nie jest skonfigurowana*.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

<!-- Removed
- **Minimum password length**: Enter the minimum number of digits or characters that the user's password must have.   


- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

- **Password expiration (days)**: Select the number of days before the password expires and the user must create a new password.

- **Number of previous passwords to prevent reuse**: Enter the number of recent passwords that can't be reused. Use this setting to restrict the user from creating previously used passwords.

-->

- **Wymagaj hasła do odblokowania urządzeń przenośnych**:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń.

- **Wymagany typ hasła**:

  określ, czy w skład hasła powinny wchodzić tylko cyfry, czy też ma być wymagana kombinacja cyfr i innych znaków. Dostępne opcje:

  - **Domyślne urządzenie** — aby oszacować zgodność haseł, należy wybrać siłę hasła inną niż **Domyślna**.
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa** — powtarzające się lub kolejne cyfry (np. `1111` albo `1234`) są niedozwolone.
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**:  
  *Obsługiwane w systemie Android 4,0 i nowszych wersjach lub KNOX 4,0 i nowszych.*

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — Zaszyfruj magazyn danych na urządzeniach. Urządzenia są szyfrowane po wybraniu ustawienia **Wymagaj hasła do odblokowania urządzeń przenośnych**.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Blokuj aplikacje z nieznanych źródeł**:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - Blokuj **blokowanie** urządzeń z zabezpieczeniami > źródła z włączonymi **źródłami** (*obsługiwane w systemie Android 4,0 za pomocą systemu Android 7. x). Nieobsługiwane przez Android 8.0 i nowsze*).

  Aby ładować aplikacje bezpośrednio, nieznane źródła muszą być dozwolone. W przypadku braku bezpośredniego ładowania aplikacji Android ustaw dla tej funkcji wartość **Blokuj**, aby włączyć te zasady zgodności.

  > [!IMPORTANT]
  > Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Blokuj aplikacje z nieznanych źródeł**. Te zasady zgodności należy wymuszać tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

- **Integralność środowiska uruchomieniowego aplikacji Portal firmy**:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — wybierz opcję *Wymagaj*, aby sprawdzać, czy aplikacja Portal firmy spełnia wszystkie poniższe wymagania:

    - Ma zainstalowane domyślne środowisko uruchomieniowe
    - Jest poprawnie podpisana
    - Nie jest w trybie debugowania
    - Została zainstalowana ze znanego źródła

- **Blokuj debugowanie USB na urządzeniu** *(Android 4,2 lub nowszy)* :

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Blokuj** — używanie funkcji debugowania USB na urządzeniach będzie zablokowane.

- **Minimalny poziom poprawek zabezpieczeń** *(Android 6,0 lub nowszy)* :

  wybierz poziom najstarszej poprawki bezpieczeństwa, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie `YYYY-MM-DD`.

  *Domyślnie żadna Data nie jest skonfigurowana*.

- **Aplikacje z ograniczeniami**:

  wprowadź wartości **Nazwa aplikacji** oraz **Identyfikator pakietu aplikacji** dla aplikacji, które mają być ograniczone, a następnie wybierz pozycję **Dodaj**. Urządzenie, na którym zainstalowano co najmniej jedną ograniczoną aplikację, jest oznaczane jako niezgodne.

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z rozwiązaniem Android Enterprise](compliance-policy-create-android-for-work.md).
