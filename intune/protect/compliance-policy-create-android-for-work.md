---
title: Ustawienia zgodności dla urządzeń z rozwiązaniem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z rozwiązaniem Android Enterprise w usłudze Microsoft Intune. Możesz między innymi ustawić reguły dotyczące haseł, wybrać minimalną lub maksymalną wersję systemu operacyjnego, ograniczyć określone aplikacje czy zablokować ponowne używanie haseł.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/07/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 163f5dd246fb17e7d67a8baffbae9926f2f4bc79
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256445"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z rozwiązaniem Android Enterprise umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z rozwiązaniem Android Enterprise za pomocą usługi Intune. Możesz stosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi oznaczać urządzenia z odblokowanym dostępem do konta root lub zdjętymi zabezpieczeniami systemu jako niezgodne, określać dozwolony poziom zagrożenia, czy włączać funkcję Google Play Protect.

Ta funkcja ma zastosowanie do:

- Android Enterprise

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

> [!IMPORTANT]
> Zasady zgodności mają zastosowanie także do dedykowanych urządzeń z systemem Android Enterprise. Jeśli zasady zgodności są przypisane do dedykowanego urządzenia, urządzenie może być widoczne jako **niezgodne**. Dostęp warunkowy i wymuszanie zgodności nie są dostępne na dedykowanych urządzeniach. Pamiętaj, aby wykonać zadania lub akcje służące zapewnieniu zgodności dedykowanych urządzeń z przypisanymi zasadami.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **Android Enterprise**.

## <a name="device-owner"></a>Właściciel urządzenia

### <a name="device-health"></a>Kondycja urządzenia

- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: Wybierz maksymalny dozwolony poziom zagrożenia urządzenia oceniony przez usługę [Mobile Threat Defense](mobile-threat-defense.md). Urządzenia powyżej tego poziomu zagrożenia są oznaczane jako niezgodne. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Zabezpieczone** — ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski** — urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni** — urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** — ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
  
> [!NOTE] 
> Wszyscy dostawcy usługi Mobile Threat Defense (MTD) są obsługiwani we wdrożeniach właściciela urządzenia z systemem Android Enterprise przy użyciu konfiguracji aplikacji. Skontaktuj się z dostawcą usługi MTD, aby uzyskać dokładną konfigurację potrzebną do obsługi platform właścicieli urządzeń z systemem Android Enterprise w usłudze Intune.

#### <a name="google-play-protect"></a>Funkcja Google Play Protect

- **Zaświadczanie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

### <a name="device-properties"></a>Właściwości urządzenia

#### <a name="operating-system-version"></a>Wersja systemu operacyjnego

- **Minimalna wersja systemu operacyjnego**: Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może uaktualnić swoje urządzenie, a następnie uzyskiwać dostęp do zasobów firmy.

  *Domyślnie żadna wersja nie jest skonfigurowana*.

- **Maksymalna wersja systemu operacyjnego**: Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie będzie mogło uzyskiwać dostępu do zasobów organizacji, dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego.

  *Domyślnie żadna wersja nie jest skonfigurowana*.

- **Minimalny poziom poprawki bezpieczeństwa**:  wybierz poziom najstarszej poprawki bezpieczeństwa, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie RRRR-MM-DD.

  *Domyślnie żadna data nie jest skonfigurowana*.


### <a name="system-security"></a>Zabezpieczenia systemu

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń.
  - **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko cyfry, czy też ma być wymagana kombinacja cyfr i innych znaków. Dostępne opcje:
    - **Ustawienie domyślne urządzenia** — aby ocenić zgodność haseł, należy wybrać siłę hasła inną niż **Ustawienie domyślne urządzenia**.  
    - **Hasło jest wymagane, brak ograniczeń**
    - **Słabe elementy biometryczne** - [silne i słabe elementy biometryczne](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (zostanie otwarta witryna internetowa systemu Android).
    - **Numeryczne** (*wartość domyślna*): Hasło może się składać tylko z cyfr, na przykład `123456789`. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
    - **Złożona wartość liczbowa** — powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
    - **Alfabetyczne** — wymagane są litery alfabetu. Cyfry ani symbole nie są wymagane. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
    - **Alfanumeryczne** — obejmuje wielkie litery, małe litery i cyfry. Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
    - **Alfanumeryczne z symbolami** — obejmuje wielkie litery, małe litery, cyfry, znaki interpunkcyjne i symbole. Wprowadź też następujące ustawienia:
    
    W zależności od wybranego *typu hasła* dostępne są następujące ustawienia:  
    - **Minimalna długość hasła**: Podaj minimalną długość hasła (od 4 do 16 znaków).  

    - **Wymagana liczba znaków**: Podaj wymaganą liczbę znaków w haśle (od 0 do 16 znaków).

    - **Wymagana liczba małych liter**: Podaj wymaganą liczbę małych liter w haśle (od 0 do 16 znaków).

    - **Wymagana liczba wielkich liter**: Podaj wymaganą liczbę wielkich liter w haśle (od 0 do 16 znaków).

    - **Wymagana liczba znaków innych niż litery**: Podaj wymaganą liczbę znaków innych niż litery w alfabecie, które muszą być zawarte w haśle (od 0 do 16 znaków).

    - **Wymagana liczba znaków numerycznych**: Podaj wymaganą liczbę cyfr (`1`, `2`, `3` itd.) w haśle (od 0 do 16 znaków).
    
    - **Wymagana liczba symboli**: Podaj wymaganą liczbę symboli (`&`, `#`, `%` itd.) w haśle (od 0 do 16 znaków).
 
- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło. Dostępne opcje obejmują ustawienie domyślne *Nie skonfigurowano* oraz wartości od *1 minuty* do *8 godzin*.

- **Liczba dni, po których hasło wygasa**: Podaj liczbę dni, po której należy zmienić hasło urządzenia (od 1 do 365). Na przykład aby wymusić zmianę hasła po upływie 60 dni, wprowadź `60`. Gdy hasło wygaśnie, użytkownicy będą monitowani o utworzenie nowego hasła.

   *Domyślnie żadna wartość nie jest skonfigurowana*.

- **Wymagana liczba haseł przed ponownym użyciem starego hasła przez użytkownika**: Podaj liczbę kolejnych haseł, których nie można użyć ponownie (od 1 do 24). To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.  

    *Domyślnie żadna wersja nie jest skonfigurowana*.

#### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — szyfruj magazyn danych na swoich urządzeniach.  

  Nie musisz konfigurować tego ustawienia, ponieważ urządzenia z rozwiązaniem Android Enterprise wymuszają szyfrowanie.

## <a name="work-profile"></a>Profil służbowy

### <a name="device-health"></a>Kondycja urządzenia

- **Urządzenia z odblokowanym dostępem**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Blokuj** — urządzenia z odblokowanym dostępem do konta root (ze zdjętymi zabezpieczeniami systemu) są oznaczane jako niezgodne.  

- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: Wybierz maksymalny dozwolony poziom zagrożenia urządzenia oceniony przez usługę [Mobile Threat Defense](mobile-threat-defense.md). Urządzenia powyżej tego poziomu zagrożenia są oznaczane jako niezgodne. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:

  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Zabezpieczone** — ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu, zostanie ono ocenione jako niezgodne.
  - **Niski** — urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni** — urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** — ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

#### <a name="google-play-protect"></a>Funkcja Google Play Protect

- **Skonfigurowano Usługi Google Play**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — wymagane jest zainstalowanie i włączenie aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google. 
  
- **Aktualny dostawca zabezpieczeń**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — wymagane jest, aby aktualny dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach. 
  
- **Zaświadczanie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

> [!NOTE]
> Na urządzeniach z rozwiązaniem Android Enterprise pozycja **Skanowanie aplikacji pod kątem zagrożeń** określa zasady konfiguracji urządzenia. Za pomocą zasad konfiguracji administratorzy mogą włączać ustawienia na urządzeniu. Zobacz [Ustawienia ograniczeń urządzenia z rozwiązaniem Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Właściwości urządzenia

#### <a name="operating-system-version"></a>Wersja systemu operacyjnego

- **Minimalna wersja systemu operacyjnego**: Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może uaktualnić swoje urządzenie, a następnie uzyskiwać dostęp do zasobów firmy.

  *Domyślnie żadna wersja nie jest skonfigurowana*.

- **Maksymalna wersja systemu operacyjnego**: Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie będzie mogło uzyskiwać dostępu do zasobów organizacji, dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego.

  *Domyślnie żadna wersja nie jest skonfigurowana*.

### <a name="system-security"></a>Zabezpieczenia systemu

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności. 
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń.  

  To ustawienie jest stosowane na poziomie urządzenia. Jeśli hasło ma być wymagane tylko na poziomie profilu służbowego, należy użyć zasad konfiguracji. Zobacz [Ustawienia konfiguracji urządzenia z systemem Android Enterprise](../configuration/device-restrictions-android-for-work.md).

- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko cyfry, czy też ma być wymagana kombinacja cyfr i innych znaków. Dostępne opcje:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne** (*wartość domyślna*): Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Złożona wartość liczbowa**: Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Co najmniej alfabetyczne**: Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Co najmniej alfanumeryczne**: Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).
  - **Co najmniej alfanumeryczne z symbolami**: Podaj **minimalną długość hasła**, które musi wprowadzić użytkownik (od 4 do 16 znaków).

  W zależności od wybranego *typu hasła* dostępne są następujące ustawienia:  
  - **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło. Dostępne opcje obejmują ustawienie domyślne *Nie skonfigurowano* oraz wartości od *1 minuty* do *8 godzin*.

  - **Liczba dni, po których hasło wygasa**: Podaj liczbę dni, po której należy zmienić hasło urządzenia (od 1 do 365). Na przykład aby wymusić zmianę hasła po upływie 60 dni, wprowadź `60`. Gdy hasło wygaśnie, użytkownicy będą monitowani o utworzenie nowego hasła.

  - **Minimalna długość hasła**: Podaj minimalną długość hasła (od 4 do 16 znaków). 
  
  - **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę ostatnich haseł, których nie można użyć ponownie. To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.

#### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych urządzenia**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — szyfruj magazyn danych na swoich urządzeniach.  

  Nie musisz konfigurować tego ustawienia, ponieważ urządzenia z rozwiązaniem Android Enterprise wymuszają szyfrowanie.

#### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Blokuj aplikacje z nieznanych źródeł**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Blokuj** — blokuj urządzenia z włączonymi źródłami **Zabezpieczenia** > **Nieznane źródła**. (*Obsługiwane w systemach Android od wersji 4.0 do wersji 7.x. Nieobsługiwane w systemach Android w wersji 8.0 i nowszych*).  

  Aby ładować aplikacje bezpośrednio, nieznane źródła muszą być dozwolone. W przypadku braku bezpośredniego ładowania aplikacji Android ustaw dla tej funkcji wartość **Blokuj**, aby włączyć te zasady zgodności.

  > [!IMPORTANT]
  > Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Blokuj aplikacje z nieznanych źródeł**. Te zasady zgodności należy wymuszać tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

  Nie musisz konfigurować tego ustawienia, ponieważ urządzenia z rozwiązaniem Android Enterprise zawsze ograniczają instalację z nieznanych źródeł.

- **Integralność środowiska uruchomieniowego aplikacji Portal firmy**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — wybierz opcję *Wymagaj*, aby sprawdzać, czy aplikacja Portal firmy spełnia wszystkie poniższe wymagania:
    - Ma zainstalowane domyślne środowisko uruchomieniowe
    - Jest poprawnie podpisana
    - Nie jest w trybie debugowania
    - Została zainstalowana ze znanego źródła

- **Blokuj debugowanie USB na urządzeniu**: 
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Blokuj** — używanie funkcji debugowania USB na urządzeniach będzie zablokowane.  

  Nie musisz konfigurować tego ustawienia, ponieważ debugowanie USB jest domyślnie wyłączone na urządzeniach z rozwiązaniem Android Enterprise.

- **Minimalny poziom poprawki bezpieczeństwa**:  wybierz poziom najstarszej poprawki bezpieczeństwa, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie RRRR-MM-DD.

  *Domyślnie żadna data nie jest skonfigurowana*.

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem Android](compliance-policy-create-android.md).
